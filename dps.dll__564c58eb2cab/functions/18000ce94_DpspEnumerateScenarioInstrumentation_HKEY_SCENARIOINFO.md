# DpspEnumerateScenarioInstrumentation(HKEY__ *,__SCENARIOINFO *)

- ea: `0x18000ce94`
- end: `0x18000d28f`
- name: `?DpspEnumerateScenarioInstrumentation@@YAJPEAUHKEY__@@PEAU__SCENARIOINFO@@@Z`
- size: `1019`
- prototype: `__int64 __fastcall(HKEY, struct __SCENARIOINFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000e9d4`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009090`
- `0x18000c9cc`
- `0x18000ce94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d001`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d014`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d20c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d21f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d232`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d001`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d014`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d20c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d21f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d232`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d049`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d196`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d049`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d196`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000cf53`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d12a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000cf53`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d12a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d0a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d0d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d0a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d0d7`

## pseudocode

```c
__int64 __fastcall DpspEnumerateScenarioInstrumentation(HKEY a1, struct __SCENARIOINFO *a2)
{
  unsigned int v3; // ebx
  WCHAR *v4; // r12
  WCHAR *v5; // r15
  LSTATUS v6; // eax
  bool v7; // cc
  DWORD v8; // ecx
  int v9; // r8d
  DWORD v10; // esi
  bool v11; // cc
  DWORD v12; // r9d
  int v13; // eax
  DWORD v14; // edi
  int v15; // eax
  DWORD lpcbMaxSubKeyLen; // [rsp+60h] [rbp-9h] BYREF
  DWORD v18; // [rsp+64h] [rbp-5h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-1h] BYREF
  DWORD v20; // [rsp+6Ch] [rbp+3h] BYREF
  HKEY v21; // [rsp+70h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+Fh] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+17h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+88h] [rbp+1Fh] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+E8h] [rbp+7Fh] BYREF

  hKey = 0;
  phkResult = 0;
  v21 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v3 = 0;
  cchName = 0;
  v4 = 0;
  v20 = 0;
  v5 = 0;
  lpcbMaxSubKeyLen = 0;
  v18 = 0;
  ftLastWriteTime = 0;
  v6 = RegOpenKeyExW(a1, L"Instrumentation", 0, 0x20019u, &hKey);
  if ( v6 || !hKey )
  {
    hKey = 0;
    if ( !*((_DWORD *)a2 + 7) )
      goto LABEL_37;
    v7 = v6 <= 0;
LABEL_48:
    if ( v7 )
    {
LABEL_49:
      v3 = v6;
      goto LABEL_37;
    }
LABEL_36:
    v3 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_37;
  }
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v7 = v6 <= 0;
  if ( v6 )
    goto LABEL_48;
  v8 = cbMaxSubKeyLen;
  if ( cbMaxSubKeyLen >= 0x7FFFFFFF )
  {
LABEL_5:
    v3 = -2147024362;
    goto LABEL_37;
  }
  if ( !cSubKeys )
  {
    v3 = *((_DWORD *)a2 + 7) != 0 ? 0x80004005 : 0;
    goto LABEL_37;
  }
  ++cbMaxSubKeyLen;
  if ( v8 + 1 != (2 * (v8 + 1)) >> 1 )
    goto LABEL_5;
  v4 = (WCHAR *)WdipAlloc(2 * (v8 + 1));
  if ( v4 )
  {
    v10 = 0;
    if ( !cSubKeys )
      goto LABEL_37;
    while ( 1 )
    {
      WdipFree(v5);
      v5 = 0;
      if ( v21 )
      {
        RegCloseKey(v21);
        v21 = 0;
      }
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      cchName = cbMaxSubKeyLen;
      v6 = RegEnumKeyExW(hKey, v10, v4, &cchName, 0, 0, 0, &ftLastWriteTime);
      v3 = v6;
      v11 = v6 <= 0;
      if ( v6 )
        break;
      v12 = cchName;
      if ( cchName >= 0x7FFFFFFF )
        goto LABEL_5;
      ++cchName;
      v13 = DpspAddRegisteredEventToScenario(hKey, a2, v4, v12 + 1);
      v3 = v13;
      if ( v13 < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
          (int)L"DpspEnumerateScenarioInstrumentation",
          1309,
          (int)L"Error = %d",
          v13);
        goto LABEL_37;
      }
      v6 = RegOpenKeyExW(hKey, v4, 0, 0x20019u, &phkResult);
      v7 = v6 <= 0;
      if ( v6 )
        goto LABEL_48;
      if ( !phkResult )
        goto LABEL_49;
      if ( !RegOpenKeyExW(phkResult, L"EndEvents", 0, 0x20019u, &v21) && v21 )
      {
        v6 = RegQueryInfoKeyW(v21, 0, 0, 0, &v20, &lpcbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
        v7 = v6 <= 0;
        if ( v6 )
          goto LABEL_48;
        ++lpcbMaxSubKeyLen;
        if ( lpcbMaxSubKeyLen != (2 * lpcbMaxSubKeyLen) >> 1 )
          goto LABEL_5;
        v5 = (WCHAR *)WdipAlloc(2 * lpcbMaxSubKeyLen);
        if ( !v5 )
        {
          v9 = 1358;
          goto LABEL_11;
        }
        v14 = 0;
        if ( v20 )
        {
          do
          {
            v18 = lpcbMaxSubKeyLen;
            v6 = RegEnumKeyExW(v21, v14, v5, &v18, 0, 0, 0, &ftLastWriteTime);
            v3 = v6;
            v11 = v6 <= 0;
            if ( v6 )
              goto LABEL_35;
            v15 = DpspAddRegisteredEventToScenario(v21, a2, v5, ++v18);
            v3 = v15;
            if ( v15 < 0 )
            {
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                (int)L"DpspEnumerateScenarioInstrumentation",
                1383,
                (int)L"Error = %d",
                v15);
              goto LABEL_37;
            }
          }
          while ( ++v14 < v20 );
        }
      }
      if ( ++v10 >= cSubKeys )
        goto LABEL_37;
    }
LABEL_35:
    if ( v11 )
      goto LABEL_37;
    goto LABEL_36;
  }
  v9 = 1264;
LABEL_11:
  v3 = -2147024882;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
    (int)L"DpspEnumerateScenarioInstrumentation",
    v9,
    (int)L"Error = %d",
    14);
LABEL_37:
  WdipFree(v4);
  WdipFree(v5);
  if ( v21 )
  {
    RegCloseKey(v21);
    v21 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v3;
}

```

## disassembly

```asm
0x18000ce94  mov     [rsp-8+arg_0], rbx
0x18000ce99  push    rbp
0x18000ce9a  push    rsi
0x18000ce9b  push    rdi
0x18000ce9c  push    r12
0x18000ce9e  push    r13
0x18000cea0  push    r14
0x18000cea2  push    r15
0x18000cea4  lea     rbp, [rsp-27h]
0x18000cea9  sub     rsp, 90h
0x18000ceb0  xor     r13d, r13d
0x18000ceb3  lea     rax, [rbp+57h+hKey]
0x18000ceb7  mov     r14, rdx
0x18000ceba  mov     [rbp+57h+hKey], r13
0x18000cebe  lea     rdx, aInstrumentatio; "Instrumentation"
0x18000cec5  mov     [rbp+57h+var_40], r13
0x18000cec9  mov     r9d, 20019h; samDesired
0x18000cecf  mov     [rbp+57h+var_50], r13
0x18000ced3  xor     r8d, r8d; ulOptions
0x18000ced6  mov     [rbp+57h+cSubKeys], r13d
0x18000ceda  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18000cede  mov     ebx, r13d
0x18000cee1  mov     [rbp+57h+cchName], r13d
0x18000cee5  mov     r12d, r13d
0x18000cee8  mov     [rbp+57h+var_54], r13d
0x18000ceec  mov     r15d, r13d
0x18000ceef  mov     [rbp+57h+var_60], r13d
0x18000cef3  mov     [rbp+57h+var_5C], r13d
0x18000cef7  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r13
0x18000cefb  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000cf00  call    cs:__imp_RegOpenKeyExW
0x18000cf06  test    eax, eax
0x18000cf08  jnz     loc_18000D272
0x18000cf0e  mov     rcx, [rbp+57h+hKey]; hKey
0x18000cf12  test    rcx, rcx
0x18000cf15  jz      loc_18000D272
0x18000cf1b  mov     [rsp+0C0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000cf20  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18000cf24  mov     [rsp+0C0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000cf29  xor     r9d, r9d; lpReserved
0x18000cf2c  mov     [rsp+0C0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000cf31  xor     r8d, r8d; lpcchClass
0x18000cf34  mov     [rsp+0C0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18000cf39  xor     edx, edx; lpClass
0x18000cf3b  mov     [rsp+0C0h+lpcValues], r13; lpcValues
0x18000cf40  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000cf45  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000cf4a  lea     rax, [rbp+57h+cSubKeys]
0x18000cf4e  mov     [rsp+0C0h+phkResult], rax; lpcSubKeys
0x18000cf53  call    cs:__imp_RegQueryInfoKeyW
0x18000cf59  test    eax, eax
0x18000cf5b  jnz     loc_18000D282
0x18000cf61  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x18000cf64  cmp     ecx, 7FFFFFFFh
0x18000cf6a  jb      short loc_18000CF76
0x18000cf6c  mov     ebx, 80070216h
0x18000cf71  jmp     loc_18000D1F3
0x18000cf76  cmp     [rbp+57h+cSubKeys], r13d
0x18000cf7a  jnz     short loc_18000CF8F
0x18000cf7c  mov     eax, [r14+1Ch]
0x18000cf80  neg     eax
0x18000cf82  sbb     ebx, ebx
0x18000cf84  and     ebx, 80004005h
0x18000cf8a  jmp     loc_18000D1F3
0x18000cf8f  inc     ecx
0x18000cf91  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x18000cf94  lea     edx, [rcx+rcx]
0x18000cf97  mov     eax, edx
0x18000cf99  shr     eax, 1
0x18000cf9b  cmp     ecx, eax
0x18000cf9d  jnz     short loc_18000CF6C
0x18000cf9f  mov     ecx, edx
0x18000cfa1  call    WdipAlloc
0x18000cfa6  mov     r12, rax
0x18000cfa9  test    rax, rax
0x18000cfac  jnz     short loc_18000CFE0
0x18000cfae  mov     r8d, 4F0h; int
0x18000cfb4  mov     dword ptr [rsp+0C0h+phkResult], 0Eh; Args
0x18000cfbc  mov     ebx, 8007000Eh
0x18000cfc1  lea     r9, aErrorD; "Error = %d"
0x18000cfc8  lea     rdx, aDpspenumerates_4; "DpspEnumerateScenarioInstrumentation"
0x18000cfcf  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000cfd6  call    WdipTraceError
0x18000cfdb  jmp     loc_18000D1F3
0x18000cfe0  mov     esi, r13d
0x18000cfe3  cmp     [rbp+57h+cSubKeys], r13d
0x18000cfe7  jbe     loc_18000D1F3
0x18000cfed  mov     rcx, r15
0x18000cff0  call    WdipFree
0x18000cff5  mov     rcx, [rbp+57h+var_50]; hKey
0x18000cff9  mov     r15, r13
0x18000cffc  test    rcx, rcx
0x18000cfff  jz      short loc_18000D00B
0x18000d001  call    cs:__imp_RegCloseKey
0x18000d007  mov     [rbp+57h+var_50], r13
0x18000d00b  mov     rcx, [rbp+57h+var_40]; hKey
0x18000d00f  test    rcx, rcx
0x18000d012  jz      short loc_18000D01E
0x18000d014  call    cs:__imp_RegCloseKey
0x18000d01a  mov     [rbp+57h+var_40], r13
0x18000d01e  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000d021  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000d025  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d029  mov     r8, r12; lpName
0x18000d02c  mov     [rbp+57h+cchName], eax
0x18000d02f  mov     edx, esi; dwIndex
0x18000d031  lea     rax, [rbp+57h+ftLastWriteTime]
0x18000d035  mov     [rsp+0C0h+lpcValues], rax; lpftLastWriteTime
0x18000d03a  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpcchClass
0x18000d03f  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r13; lpClass
0x18000d044  mov     [rsp+0C0h+phkResult], r13; lpReserved
0x18000d049  call    cs:__imp_RegEnumKeyExW
0x18000d04f  mov     ebx, eax
0x18000d051  test    eax, eax
0x18000d053  jnz     loc_18000D1E8
0x18000d059  mov     r9d, [rbp+57h+cchName]
0x18000d05d  cmp     r9d, 7FFFFFFFh
0x18000d064  jnb     loc_18000CF6C
0x18000d06a  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d06e  inc     r9d; unsigned int
0x18000d071  mov     r8, r12; unsigned __int16 *
0x18000d074  mov     [rbp+57h+cchName], r9d
0x18000d078  mov     rdx, r14; struct __SCENARIOINFO *
0x18000d07b  call    ?DpspAddRegisteredEventToScenario@@YAJPEAUHKEY__@@PEAU__SCENARIOINFO@@PEAGK@Z; DpspAddRegisteredEventToScenario(HKEY__ *,__SCENARIOINFO *,ushort *,ulong)
0x18000d080  mov     ebx, eax
0x18000d082  test    eax, eax
0x18000d084  js      loc_18000D260
0x18000d08a  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d08e  lea     rax, [rbp+57h+var_40]
0x18000d092  mov     r9d, 20019h; samDesired
0x18000d098  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000d09d  xor     r8d, r8d; ulOptions
0x18000d0a0  mov     rdx, r12; lpSubKey
0x18000d0a3  call    cs:__imp_RegOpenKeyExW
0x18000d0a9  test    eax, eax
0x18000d0ab  jnz     loc_18000D282
0x18000d0b1  mov     rcx, [rbp+57h+var_40]; hKey
0x18000d0b5  test    rcx, rcx
0x18000d0b8  jz      loc_18000D288
0x18000d0be  lea     rax, [rbp+57h+var_50]
0x18000d0c2  mov     r9d, 20019h; samDesired
0x18000d0c8  xor     r8d, r8d; ulOptions
0x18000d0cb  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000d0d0  lea     rdx, aEndevents; "EndEvents"
0x18000d0d7  call    cs:__imp_RegOpenKeyExW
0x18000d0dd  test    eax, eax
0x18000d0df  jnz     loc_18000D1C9
0x18000d0e5  mov     rcx, [rbp+57h+var_50]; hKey
0x18000d0e9  test    rcx, rcx
0x18000d0ec  jz      loc_18000D1C9
0x18000d0f2  mov     [rsp+0C0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000d0f7  lea     rax, [rbp+57h+var_60]
0x18000d0fb  mov     [rsp+0C0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000d100  xor     r9d, r9d; lpReserved
0x18000d103  mov     [rsp+0C0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000d108  xor     r8d, r8d; lpcchClass
0x18000d10b  mov     [rsp+0C0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18000d110  xor     edx, edx; lpClass
0x18000d112  mov     [rsp+0C0h+lpcValues], r13; lpcValues
0x18000d117  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000d11c  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000d121  lea     rax, [rbp+57h+var_54]
0x18000d125  mov     [rsp+0C0h+phkResult], rax; lpcSubKeys
0x18000d12a  call    cs:__imp_RegQueryInfoKeyW
0x18000d130  test    eax, eax
0x18000d132  jnz     loc_18000D282
0x18000d138  mov     ecx, [rbp+57h+var_60]
0x18000d13b  inc     ecx
0x18000d13d  mov     [rbp+57h+var_60], ecx
0x18000d140  lea     edx, [rcx+rcx]
0x18000d143  mov     eax, edx
0x18000d145  shr     eax, 1
0x18000d147  cmp     ecx, eax
0x18000d149  jnz     loc_18000CF6C
0x18000d14f  mov     ecx, edx
0x18000d151  call    WdipAlloc
0x18000d156  mov     r15, rax
0x18000d159  test    rax, rax
0x18000d15c  jz      loc_18000D255
0x18000d162  mov     edi, r13d
0x18000d165  cmp     [rbp+57h+var_54], r13d
0x18000d169  jbe     short loc_18000D1C9
0x18000d16b  mov     eax, [rbp+57h+var_60]
0x18000d16e  lea     r9, [rbp+57h+var_5C]; lpcchName
0x18000d172  mov     rcx, [rbp+57h+var_50]; hKey
0x18000d176  mov     r8, r15; lpName
0x18000d179  mov     [rbp+57h+var_5C], eax
0x18000d17c  mov     edx, edi; dwIndex
0x18000d17e  lea     rax, [rbp+57h+ftLastWriteTime]
0x18000d182  mov     [rsp+0C0h+lpcValues], rax; lpftLastWriteTime
0x18000d187  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpcchClass
0x18000d18c  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r13; lpClass
0x18000d191  mov     [rsp+0C0h+phkResult], r13; lpReserved
0x18000d196  call    cs:__imp_RegEnumKeyExW
0x18000d19c  mov     ebx, eax
0x18000d19e  test    eax, eax
0x18000d1a0  jnz     short loc_18000D1E8
0x18000d1a2  mov     r9d, [rbp+57h+var_5C]
0x18000d1a6  mov     r8, r15; unsigned __int16 *
0x18000d1a9  mov     rcx, [rbp+57h+var_50]; hKey
0x18000d1ad  inc     r9d; unsigned int
0x18000d1b0  mov     rdx, r14; struct __SCENARIOINFO *
0x18000d1b3  mov     [rbp+57h+var_5C], r9d
0x18000d1b7  call    ?DpspAddRegisteredEventToScenario@@YAJPEAUHKEY__@@PEAU__SCENARIOINFO@@PEAGK@Z; DpspAddRegisteredEventToScenario(HKEY__ *,__SCENARIOINFO *,ushort *,ulong)
0x18000d1bc  mov     ebx, eax
0x18000d1be  test    eax, eax
0x18000d1c0  js      short loc_18000D1D6
0x18000d1c2  inc     edi
0x18000d1c4  cmp     edi, [rbp+57h+var_54]
0x18000d1c7  jb      short loc_18000D16B
0x18000d1c9  inc     esi
0x18000d1cb  cmp     esi, [rbp+57h+cSubKeys]
0x18000d1ce  jb      loc_18000CFED
0x18000d1d4  jmp     short loc_18000D1F3
0x18000d1d6  movzx   eax, ax
0x18000d1d9  mov     r8d, 567h
0x18000d1df  mov     dword ptr [rsp+0C0h+phkResult], eax
0x18000d1e3  jmp     loc_18000CFC1
0x18000d1e8  jle     short loc_18000D1F3
0x18000d1ea  movzx   ebx, ax
0x18000d1ed  or      ebx, 80070000h
0x18000d1f3  mov     rcx, r12
0x18000d1f6  call    WdipFree
0x18000d1fb  mov     rcx, r15
0x18000d1fe  call    WdipFree
0x18000d203  mov     rcx, [rbp+57h+var_50]; hKey
0x18000d207  test    rcx, rcx
0x18000d20a  jz      short loc_18000D216
0x18000d20c  call    cs:__imp_RegCloseKey
0x18000d212  mov     [rbp+57h+var_50], r13
0x18000d216  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d21a  test    rcx, rcx
0x18000d21d  jz      short loc_18000D229
0x18000d21f  call    cs:__imp_RegCloseKey
0x18000d225  mov     [rbp+57h+hKey], r13
0x18000d229  mov     rcx, [rbp+57h+var_40]; hKey
0x18000d22d  test    rcx, rcx
0x18000d230  jz      short loc_18000D238
0x18000d232  call    cs:__imp_RegCloseKey
0x18000d238  mov     eax, ebx
0x18000d23a  mov     rbx, [rsp+0C0h+arg_0]
0x18000d242  add     rsp, 90h
0x18000d249  pop     r15
0x18000d24b  pop     r14
0x18000d24d  pop     r13
0x18000d24f  pop     r12
0x18000d251  pop     rdi
0x18000d252  pop     rsi
0x18000d253  pop     rbp
0x18000d254  retn
0x18000d255  mov     r8d, 54Eh
0x18000d25b  jmp     loc_18000CFB4
0x18000d260  movzx   eax, ax
0x18000d263  mov     r8d, 51Dh
0x18000d269  mov     dword ptr [rsp+0C0h+phkResult], eax
0x18000d26d  jmp     loc_18000CFC1
0x18000d272  mov     [rbp+57h+hKey], r13
0x18000d276  cmp     [r14+1Ch], r13d
0x18000d27a  jz      loc_18000D1F3
0x18000d280  test    eax, eax
0x18000d282  jg      loc_18000D1EA
0x18000d288  mov     ebx, eax
0x18000d28a  jmp     loc_18000D1F3
```
