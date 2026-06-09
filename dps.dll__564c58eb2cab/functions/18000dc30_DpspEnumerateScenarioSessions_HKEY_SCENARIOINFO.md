# DpspEnumerateScenarioSessions(HKEY__ *,__SCENARIOINFO *)

- ea: `0x18000dc30`
- end: `0x18000de8b`
- name: `?DpspEnumerateScenarioSessions@@YAJPEAUHKEY__@@PEAU__SCENARIOINFO@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(HKEY, struct __SCENARIOINFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000e9d4`

## callees

- `0x180008ea0`
- `0x180009044`
- `0x180009090`
- `0x180009fb0`
- `0x18000dc30`
- `0x18000f298`
- `0x18000f3d0`
- `0x1800178a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ddd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ddd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de60`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000dce0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000dce0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dc8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dd4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dc8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dd4d`

## pseudocode

```c
__int64 __fastcall DpspEnumerateScenarioSessions(HKEY a1, struct __SCENARIOINFO *a2)
{
  __int64 v3; // rdi
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  bool v6; // cc
  DWORD v7; // esi
  int v8; // eax
  int ValueAlloc; // eax
  int v10; // r8d
  HKEY phkResult; // [rsp+60h] [rbp-49h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-39h] BYREF
  struct _GUID v15; // [rsp+80h] [rbp-29h] BYREF
  __int64 v16; // [rsp+90h] [rbp-19h] BYREF
  struct _GUID v17; // [rsp+A0h] [rbp-9h] BYREF
  WCHAR SubKey[16]; // [rsp+B0h] [rbp+7h] BYREF

  hKey = 0;
  phkResult = 0;
  cSubKeys = 0;
  *(_QWORD *)&v15.Data1 = 0;
  v3 = 0;
  v17 = 0;
  v4 = RegOpenKeyExW(a1, L"DiagnosticModules", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 || !hKey )
  {
    hKey = 0;
LABEL_23:
    v6 = v4 <= 0;
    goto LABEL_24;
  }
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v5 = v4;
  v6 = v4 <= 0;
  if ( v4 )
  {
LABEL_24:
    if ( !v6 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_26;
  }
  if ( cSubKeys )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = StringCchPrintfW(SubKey, 0x10u, L"DM%d", ++v7);
      v5 = v8;
      if ( v8 < 0 )
        break;
      v4 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult);
      v5 = v4;
      if ( v4 )
      {
        phkResult = 0;
        goto LABEL_23;
      }
      if ( !phkResult )
      {
        phkResult = 0;
        goto LABEL_26;
      }
      ValueAlloc = WdipRegReadValueAlloc(phkResult, L"DMGUID", (__int64)&v16);
      v3 = *(_QWORD *)&v15.Data1;
      v5 = ValueAlloc;
      if ( ValueAlloc < 0 )
        goto LABEL_26;
      v8 = WdipStringToGuid(*(_QWORD *)&v15.Data1, &v17);
      v5 = v8;
      if ( v8 < 0 )
      {
        v10 = 1131;
        goto LABEL_21;
      }
      v15 = v17;
      if ( (unsigned int)DpspSetScenarioInfoSessionPointer(a2, &v15) != 1 )
        goto LABEL_5;
      WdipFree(v3);
      v3 = 0;
      *(_QWORD *)&v15.Data1 = 0;
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      if ( v7 >= cSubKeys )
        goto LABEL_26;
    }
    v10 = 1102;
LABEL_21:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
      (int)L"DpspEnumerateScenarioSessions",
      v10,
      (int)L"Error = %d",
      v8);
  }
  else
  {
LABEL_5:
    v5 = -2147024809;
  }
LABEL_26:
  WdipFree(v3);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18000dc30  mov     [rsp-8+arg_10], rbx
0x18000dc35  push    rbp
0x18000dc36  push    rsi
0x18000dc37  push    rdi
0x18000dc38  push    r14
0x18000dc3a  push    r15
0x18000dc3c  lea     rbp, [rsp-37h]
0x18000dc41  sub     rsp, 0E0h
0x18000dc48  mov     rax, cs:__security_cookie
0x18000dc4f  xor     rax, rsp
0x18000dc52  mov     [rbp+57h+var_30], rax
0x18000dc56  xor     r15d, r15d
0x18000dc59  lea     rax, [rbp+57h+hKey]
0x18000dc5d  mov     r14, rdx
0x18000dc60  mov     [rbp+57h+hKey], r15
0x18000dc64  xorps   xmm0, xmm0
0x18000dc67  mov     [rbp+57h+var_A0], r15
0x18000dc6b  lea     rdx, aDiagnosticmodu; "DiagnosticModules"
0x18000dc72  mov     [rbp+57h+cSubKeys], r15d
0x18000dc76  mov     r9d, 20019h; samDesired
0x18000dc7c  mov     qword ptr [rbp+57h+var_80.Data1], r15
0x18000dc80  xor     r8d, r8d; ulOptions
0x18000dc83  mov     [rsp+100h+phkResult], rax; phkResult
0x18000dc88  mov     edi, r15d
0x18000dc8b  movups  [rbp+57h+var_60], xmm0
0x18000dc8f  call    cs:__imp_RegOpenKeyExW
0x18000dc95  mov     ebx, eax
0x18000dc97  test    eax, eax
0x18000dc99  jnz     loc_18000DE2B
0x18000dc9f  mov     rcx, [rbp+57h+hKey]; hKey
0x18000dca3  test    rcx, rcx
0x18000dca6  jz      loc_18000DE2B
0x18000dcac  mov     [rsp+100h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000dcb1  lea     rax, [rbp+57h+cSubKeys]
0x18000dcb5  mov     [rsp+100h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000dcba  xor     r9d, r9d; lpReserved
0x18000dcbd  mov     [rsp+100h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000dcc2  xor     r8d, r8d; lpcchClass
0x18000dcc5  mov     [rsp+100h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000dcca  xor     edx, edx; lpClass
0x18000dccc  mov     [rsp+100h+lpcValues], r15; lpcValues
0x18000dcd1  mov     [rsp+100h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000dcd6  mov     [rsp+100h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000dcdb  mov     [rsp+100h+phkResult], rax; lpcSubKeys
0x18000dce0  call    cs:__imp_RegQueryInfoKeyW
0x18000dce6  mov     ebx, eax
0x18000dce8  test    eax, eax
0x18000dcea  jnz     loc_18000DE31
0x18000dcf0  mov     eax, [rbp+57h+cSubKeys]
0x18000dcf3  test    eax, eax
0x18000dcf5  jnz     short loc_18000DD01
0x18000dcf7  mov     ebx, 80070057h
0x18000dcfc  jmp     loc_18000DE3C
0x18000dd01  mov     ebx, r15d
0x18000dd04  mov     esi, r15d
0x18000dd07  test    eax, eax
0x18000dd09  jz      loc_18000DE3C
0x18000dd0f  inc     esi
0x18000dd11  lea     r8, aDmD; "DM%d"
0x18000dd18  mov     r9d, esi
0x18000dd1b  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x18000dd1f  mov     edx, 10h; unsigned __int64
0x18000dd24  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dd29  mov     ebx, eax
0x18000dd2b  test    eax, eax
0x18000dd2d  js      loc_18000DE02
0x18000dd33  mov     rcx, [rbp+57h+hKey]; hKey
0x18000dd37  lea     rax, [rbp+57h+var_A0]
0x18000dd3b  mov     r9d, 20019h; samDesired
0x18000dd41  mov     [rsp+100h+phkResult], rax; phkResult
0x18000dd46  xor     r8d, r8d; ulOptions
0x18000dd49  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18000dd4d  call    cs:__imp_RegOpenKeyExW
0x18000dd53  mov     ebx, eax
0x18000dd55  test    eax, eax
0x18000dd57  jnz     loc_18000DDFC
0x18000dd5d  mov     rcx, [rbp+57h+var_A0]; hKey
0x18000dd61  test    rcx, rcx
0x18000dd64  jz      loc_18000DDF6
0x18000dd6a  lea     rax, [rbp+57h+var_70]
0x18000dd6e  lea     r9, [rbp+57h+var_80]
0x18000dd72  mov     [rsp+100h+phkResult], rax; __int64
0x18000dd77  lea     rdx, aDmguid; "DMGUID"
0x18000dd7e  call    WdipRegReadValueAlloc
0x18000dd83  mov     rdi, qword ptr [rbp+57h+var_80.Data1]
0x18000dd87  mov     ebx, eax
0x18000dd89  test    eax, eax
0x18000dd8b  js      loc_18000DE3C
0x18000dd91  lea     rdx, [rbp+57h+var_60]
0x18000dd95  mov     rcx, rdi
0x18000dd98  call    WdipStringToGuid
0x18000dd9d  mov     ebx, eax
0x18000dd9f  test    eax, eax
0x18000dda1  js      short loc_18000DDEE
0x18000dda3  movaps  xmm0, [rbp+57h+var_60]
0x18000dda7  lea     rdx, [rbp+57h+var_80]; struct _GUID
0x18000ddab  mov     rcx, r14; struct __SCENARIOINFO *
0x18000ddae  movdqa  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x18000ddb3  call    ?DpspSetScenarioInfoSessionPointer@@YAHPEAU__SCENARIOINFO@@U_GUID@@@Z; DpspSetScenarioInfoSessionPointer(__SCENARIOINFO *,_GUID)
0x18000ddb8  cmp     eax, 1
0x18000ddbb  jnz     loc_18000DCF7
0x18000ddc1  mov     rcx, rdi
0x18000ddc4  call    WdipFree
0x18000ddc9  mov     rcx, [rbp+57h+var_A0]; hKey
0x18000ddcd  mov     rdi, r15
0x18000ddd0  mov     qword ptr [rbp+57h+var_80.Data1], r15
0x18000ddd4  test    rcx, rcx
0x18000ddd7  jz      short loc_18000DDE3
0x18000ddd9  call    cs:__imp_RegCloseKey
0x18000dddf  mov     [rbp+57h+var_A0], r15
0x18000dde3  cmp     esi, [rbp+57h+cSubKeys]
0x18000dde6  jb      loc_18000DD0F
0x18000ddec  jmp     short loc_18000DE3C
0x18000ddee  mov     r8d, 46Bh
0x18000ddf4  jmp     short loc_18000DE08
0x18000ddf6  mov     [rbp+57h+var_A0], r15
0x18000ddfa  jmp     short loc_18000DE3C
0x18000ddfc  mov     [rbp+57h+var_A0], r15
0x18000de00  jmp     short loc_18000DE2F
0x18000de02  mov     r8d, 44Eh; int
0x18000de08  movzx   eax, ax
0x18000de0b  lea     r9, aErrorD; "Error = %d"
0x18000de12  lea     rdx, aDpspenumerates_2; "DpspEnumerateScenarioSessions"
0x18000de19  mov     dword ptr [rsp+100h+phkResult], eax; Args
0x18000de1d  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000de24  call    WdipTraceError
0x18000de29  jmp     short loc_18000DE3C
0x18000de2b  mov     [rbp+57h+hKey], r15
0x18000de2f  test    eax, eax
0x18000de31  jle     short loc_18000DE3C
0x18000de33  movzx   ebx, ax
0x18000de36  or      ebx, 80070000h
0x18000de3c  mov     rcx, rdi
0x18000de3f  call    WdipFree
0x18000de44  mov     rcx, [rbp+57h+var_A0]; hKey
0x18000de48  test    rcx, rcx
0x18000de4b  jz      short loc_18000DE57
0x18000de4d  call    cs:__imp_RegCloseKey
0x18000de53  mov     [rbp+57h+var_A0], r15
0x18000de57  mov     rcx, [rbp+57h+hKey]; hKey
0x18000de5b  test    rcx, rcx
0x18000de5e  jz      short loc_18000DE66
0x18000de60  call    cs:__imp_RegCloseKey
0x18000de66  mov     eax, ebx
0x18000de68  mov     rcx, [rbp+57h+var_30]
0x18000de6c  xor     rcx, rsp; StackCookie
0x18000de6f  call    __security_check_cookie
0x18000de74  mov     rbx, [rsp+100h+arg_10]
0x18000de7c  add     rsp, 0E0h
0x18000de83  pop     r15
0x18000de85  pop     r14
0x18000de87  pop     rdi
0x18000de88  pop     rsi
0x18000de89  pop     rbp
0x18000de8a  retn
```
