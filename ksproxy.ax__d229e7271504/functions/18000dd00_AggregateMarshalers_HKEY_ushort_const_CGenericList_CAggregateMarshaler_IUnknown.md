# AggregateMarshalers(HKEY__ *,ushort const *,CGenericList<CAggregateMarshaler> *,IUnknown *)

- ea: `0x18000dd00`
- end: `0x18000deec`
- name: `?AggregateMarshalers@@YAJPEAUHKEY__@@PEBGPEAV?$CGenericList@VCAggregateMarshaler@@@@PEAUIUnknown@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, CBaseList *, IUnknown *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d88c`
- `0x1800196f0`

## callees

- `0x18000b2e4`
- `0x18000dd00`
- `0x18001f1d0`
- `0x18001f620`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000de03`
- `ADVAPI32!RegQueryValueExW` at `0x18000de03`
- `ADVAPI32!RegCloseKey` at `0x18000de15`
- `ADVAPI32!RegCloseKey` at `0x18000deb2`
- `ADVAPI32!RegCloseKey` at `0x18000dec3`
- `ADVAPI32!RegCloseKey` at `0x18000de15`
- `ADVAPI32!RegCloseKey` at `0x18000deb2`
- `ADVAPI32!RegCloseKey` at `0x18000dec3`
- `ADVAPI32!RegOpenKeyExW` at `0x18000dd4b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000dd7f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ddc3`
- `ADVAPI32!RegOpenKeyExW` at `0x18000dd4b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000dd7f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ddc3`
- `ADVAPI32!RegEnumKeyW` at `0x18000de9a`
- `ADVAPI32!RegEnumKeyW` at `0x18000de9a`
- `ole32!IIDFromString` at `0x18000de53`
- `ole32!IIDFromString` at `0x18000de53`

## pseudocode

```c
__int64 __fastcall AggregateMarshalers(HKEY a1, const WCHAR *a2, CBaseList *a3, IUnknown *a4)
{
  LSTATUS v6; // eax
  HKEY v7; // rcx
  int v8; // edi
  DWORD v9; // edx
  LSTATUS v10; // ebx
  void *v11; // rax
  char *v12; // rbx
  DWORD cbData; // [rsp+30h] [rbp-89h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-81h] BYREF
  HKEY i; // [rsp+40h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-71h] BYREF
  BYTE Data[16]; // [rsp+50h] [rbp-69h] BYREF
  WCHAR SubKey[64]; // [rsp+60h] [rbp-59h] BYREF

  phkResult = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(a1, a2, 0, 0x20019u, &phkResult) )
  {
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MediaInterfaces", 0, 0x20019u, &hKey);
    v7 = phkResult;
    if ( !v6 )
    {
      v8 = 0;
      cbData = 0;
      v9 = 0;
      for ( i = 0; ; i = 0 )
      {
        *(_OWORD *)Data = 0;
        if ( RegEnumKeyW(v7, v9, SubKey, 0x40u) )
          break;
        if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &i) )
        {
          cbData = 16;
          v10 = RegQueryValueExW(i, L"iid", 0, 0, Data, &cbData);
          RegCloseKey(i);
          if ( v10 )
            *(GUID *)Data = GUID_00000000_0000_0000_0000_000000000000;
          v11 = operator new(0x38u);
          v12 = (char *)v11;
          if ( !v11 )
            break;
          *(_OWORD *)v11 = *(_OWORD *)Data;
          IIDFromString(SubKey, (LPIID)v11 + 1);
          AddAggregateObject(a3, v12, a4, 0);
        }
        v7 = phkResult;
        v9 = ++v8;
        cbData = 0;
      }
      RegCloseKey(hKey);
      v7 = phkResult;
    }
    RegCloseKey(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18000dd00  push    rbp
0x18000dd02  push    rbx
0x18000dd03  push    rsi
0x18000dd04  push    rdi
0x18000dd05  push    r14
0x18000dd07  lea     rbp, [rsp-37h]
0x18000dd0c  sub     rsp, 0F0h
0x18000dd13  mov     rax, cs:__security_cookie
0x18000dd1a  xor     rax, rsp
0x18000dd1d  mov     [rbp+57h+var_30], rax
0x18000dd21  mov     r14, r9
0x18000dd24  mov     [rsp+110h+var_D8], 0
0x18000dd2d  mov     rsi, r8
0x18000dd30  mov     [rbp+57h+hKey], 0
0x18000dd38  lea     rax, [rsp+110h+var_D8]
0x18000dd3d  mov     r9d, 20019h; samDesired
0x18000dd43  xor     r8d, r8d; ulOptions
0x18000dd46  mov     [rsp+110h+phkResult], rax; phkResult
0x18000dd4b  call    cs:__imp_RegOpenKeyExW
0x18000dd52  nop     dword ptr [rax+rax+00h]
0x18000dd57  test    eax, eax
0x18000dd59  jnz     loc_18000DECF
0x18000dd5f  lea     rax, [rbp+57h+hKey]
0x18000dd63  mov     r9d, 20019h; samDesired
0x18000dd69  xor     r8d, r8d; ulOptions
0x18000dd6c  mov     [rsp+110h+phkResult], rax; phkResult
0x18000dd71  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x18000dd78  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dd7f  call    cs:__imp_RegOpenKeyExW
0x18000dd86  nop     dword ptr [rax+rax+00h]
0x18000dd8b  mov     rcx, [rsp+110h+var_D8]
0x18000dd90  test    eax, eax
0x18000dd92  jnz     loc_18000DEC3
0x18000dd98  xor     edi, edi
0x18000dd9a  mov     [rsp+110h+cbData], edi
0x18000dd9e  xor     edx, edx
0x18000dda0  mov     [rbp+57h+var_D0], rdi
0x18000dda4  jmp     loc_18000DE89
0x18000dda9  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ddad  lea     rax, [rbp+57h+var_D0]
0x18000ddb1  mov     r9d, 20019h; samDesired
0x18000ddb7  mov     [rsp+110h+phkResult], rax; phkResult
0x18000ddbc  xor     r8d, r8d; ulOptions
0x18000ddbf  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18000ddc3  call    cs:__imp_RegOpenKeyExW
0x18000ddca  nop     dword ptr [rax+rax+00h]
0x18000ddcf  test    eax, eax
0x18000ddd1  jnz     loc_18000DE70
0x18000ddd7  mov     rcx, [rbp+57h+var_D0]; hKey
0x18000dddb  lea     rax, [rsp+110h+cbData]
0x18000dde0  mov     [rsp+110h+lpcbData], rax; lpcbData
0x18000dde5  lea     rdx, ValueName; "iid"
0x18000ddec  lea     rax, [rbp+57h+Data]
0x18000ddf0  mov     [rsp+110h+cbData], 10h
0x18000ddf8  xor     r9d, r9d; lpType
0x18000ddfb  mov     [rsp+110h+phkResult], rax; lpData
0x18000de00  xor     r8d, r8d; lpReserved
0x18000de03  call    cs:__imp_RegQueryValueExW
0x18000de0a  nop     dword ptr [rax+rax+00h]
0x18000de0f  mov     rcx, [rbp+57h+var_D0]; hKey
0x18000de13  mov     ebx, eax
0x18000de15  call    cs:__imp_RegCloseKey
0x18000de1c  nop     dword ptr [rax+rax+00h]
0x18000de21  test    ebx, ebx
0x18000de23  jz      short loc_18000DE31
0x18000de25  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000de2c  movdqu  xmmword ptr [rbp+57h+Data], xmm0
0x18000de31  mov     ecx, 38h ; '8'; Size
0x18000de36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000de3b  mov     rbx, rax
0x18000de3e  test    rax, rax
0x18000de41  jz      short loc_18000DEAE
0x18000de43  movups  xmm0, xmmword ptr [rbp+57h+Data]
0x18000de47  lea     rdx, [rax+10h]; lpiid
0x18000de4b  lea     rcx, [rbp+57h+SubKey]; lpsz
0x18000de4f  movdqu  xmmword ptr [rax], xmm0
0x18000de53  call    cs:__imp_IIDFromString
0x18000de5a  nop     dword ptr [rax+rax+00h]
0x18000de5f  xor     r9d, r9d
0x18000de62  mov     r8, r14; pUnkOuter
0x18000de65  mov     rdx, rbx; void *
0x18000de68  mov     rcx, rsi; this
0x18000de6b  call    ?AddAggregateObject@@YAJPEAV?$CGenericList@VCAggregateMarshaler@@@@PEAVCAggregateMarshaler@@PEAUIUnknown@@H@Z; AddAggregateObject(CGenericList<CAggregateMarshaler> *,CAggregateMarshaler *,IUnknown *,int)
0x18000de70  mov     rcx, [rsp+110h+var_D8]; hKey
0x18000de75  inc     edi
0x18000de77  mov     edx, edi; dwIndex
0x18000de79  mov     [rsp+110h+cbData], 0
0x18000de81  mov     [rbp+57h+var_D0], 0
0x18000de89  xorps   xmm0, xmm0
0x18000de8c  lea     r8, [rbp+57h+SubKey]; lpName
0x18000de90  mov     r9d, 40h ; '@'; cchName
0x18000de96  movups  xmmword ptr [rbp+57h+Data], xmm0
0x18000de9a  call    cs:__imp_RegEnumKeyW
0x18000dea1  nop     dword ptr [rax+rax+00h]
0x18000dea6  test    eax, eax
0x18000dea8  jz      loc_18000DDA9
0x18000deae  mov     rcx, [rbp+57h+hKey]; hKey
0x18000deb2  call    cs:__imp_RegCloseKey
0x18000deb9  nop     dword ptr [rax+rax+00h]
0x18000debe  mov     rcx, [rsp+110h+var_D8]; hKey
0x18000dec3  call    cs:__imp_RegCloseKey
0x18000deca  nop     dword ptr [rax+rax+00h]
0x18000decf  xor     eax, eax
0x18000ded1  mov     rcx, [rbp+57h+var_30]
0x18000ded5  xor     rcx, rsp; StackCookie
0x18000ded8  call    __security_check_cookie
0x18000dedd  add     rsp, 0F0h
0x18000dee4  pop     r14
0x18000dee6  pop     rdi
0x18000dee7  pop     rsi
0x18000dee8  pop     rbx
0x18000dee9  pop     rbp
0x18000deea  retn
```
