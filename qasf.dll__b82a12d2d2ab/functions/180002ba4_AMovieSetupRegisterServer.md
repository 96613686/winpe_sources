# AMovieSetupRegisterServer

- ea: `0x180002ba4`
- end: `0x180002eac`
- name: `AMovieSetupRegisterServer`
- size: `776`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800028b0`

## callees

- `0x180001460`
- `0x1800026d4`
- `0x180002ba4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180002cd9`
- `ADVAPI32!RegCloseKey` at `0x180002dd4`
- `ADVAPI32!RegCloseKey` at `0x180002e6f`
- `ADVAPI32!RegCloseKey` at `0x180002e7a`
- `ADVAPI32!RegCloseKey` at `0x180002cd9`
- `ADVAPI32!RegCloseKey` at `0x180002dd4`
- `ADVAPI32!RegCloseKey` at `0x180002e6f`
- `ADVAPI32!RegCloseKey` at `0x180002e7a`
- `ADVAPI32!RegCreateKeyExW` at `0x180002c38`
- `ADVAPI32!RegCreateKeyExW` at `0x180002d3b`
- `ADVAPI32!RegCreateKeyExW` at `0x180002c38`
- `ADVAPI32!RegCreateKeyExW` at `0x180002d3b`
- `ADVAPI32!RegSetValueExW` at `0x180002cc8`
- `ADVAPI32!RegSetValueExW` at `0x180002dc3`
- `ADVAPI32!RegSetValueExW` at `0x180002e62`
- `ADVAPI32!RegSetValueExW` at `0x180002cc8`
- `ADVAPI32!RegSetValueExW` at `0x180002dc3`
- `ADVAPI32!RegSetValueExW` at `0x180002e62`
- `ole32!StringFromGUID2` at `0x180002bdc`
- `ole32!StringFromGUID2` at `0x180002bdc`

## string_xrefs

- `0x180002bef`: `CLSID\%ls`
- `0x180002e49`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall AMovieSetupRegisterServer(const GUID *a1, __int64 a2, __int64 a3)
{
  LSTATUS v5; // eax
  __int64 result; // rax
  __int64 v7; // r8
  WCHAR *v8; // rax
  LSTATUS v9; // edi
  HKEY v10; // rcx
  __int64 v11; // r8
  WCHAR *v12; // rax
  __int64 v13; // rdx
  WCHAR *v14; // rax
  LSTATUS v15; // ebx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-50h] BYREF

  StringFromGUID2(a1, sz, 39);
  hKey = 0;
  StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ls", sz);
  v5 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0);
  if ( v5 )
    return v5 | 0x80070000;
  StringCchPrintfW(SubKey, 0x104u, L"%ls", a2);
  v7 = 260;
  v8 = SubKey;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  result = v7 == 0 ? 0x80070057 : 0;
  if ( v7 )
  {
    v9 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)SubKey, 2 * (v7 != 0 ? 260 - v7 : 0) + 2);
    if ( v9
      || (phkResult = 0,
          StringCchPrintfW(SubKey, 0x104u, L"%ls", L"InprocServer32"),
          (v9 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2000000u, 0, &phkResult, 0)) != 0) )
    {
      v10 = hKey;
LABEL_9:
      RegCloseKey(v10);
      return v9 | 0x80070000;
    }
    StringCchPrintfW(SubKey, 0x104u, L"%ls", a3);
    v11 = 260;
    v12 = SubKey;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    result = v11 == 0 ? 0x80070057 : 0;
    if ( v11 )
    {
      v9 = RegSetValueExW(phkResult, 0, 0, 1u, (const BYTE *)SubKey, 2 * (v11 != 0 ? 260 - v11 : 0) + 2);
      if ( v9 )
      {
        RegCloseKey(hKey);
        v10 = phkResult;
        goto LABEL_9;
      }
      StringCchPrintfW(SubKey, 0x104u, L"%ls", L"Both");
      v13 = 260;
      v14 = SubKey;
      do
      {
        if ( !*v14 )
          break;
        ++v14;
        --v13;
      }
      while ( v13 );
      result = v13 == 0 ? 0x80070057 : 0;
      if ( v13 )
      {
        v15 = RegSetValueExW(
                phkResult,
                L"ThreadingModel",
                0,
                1u,
                (const BYTE *)SubKey,
                2 * (v13 != 0 ? 260 - v13 : 0) + 2);
        RegCloseKey(hKey);
        RegCloseKey(phkResult);
        if ( v15 > 0 )
          return (unsigned __int16)v15 | 0x80070000;
        return (unsigned int)v15;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002ba4  push    rbp
0x180002ba6  push    rbx
0x180002ba7  push    rsi
0x180002ba8  push    rdi
0x180002ba9  push    r14
0x180002bab  lea     rbp, [rsp-1D0h]
0x180002bb3  sub     rsp, 2D0h
0x180002bba  mov     rax, cs:__security_cookie
0x180002bc1  xor     rax, rsp
0x180002bc4  mov     [rbp+1F0h+var_30], rax
0x180002bcb  mov     rsi, r8
0x180002bce  mov     rdi, rdx
0x180002bd1  mov     r8d, 27h ; '''; cchMax
0x180002bd7  lea     rdx, [rsp+2F0h+sz]; lpsz
0x180002bdc  call    cs:__imp_StringFromGUID2
0x180002be2  mov     ebx, 104h
0x180002be7  lea     r9, [rsp+2F0h+sz]
0x180002bec  xor     r14d, r14d
0x180002bef  lea     r8, aClsidLs; "CLSID\\%ls"
0x180002bf6  mov     edx, ebx; unsigned __int64
0x180002bf8  mov     [rsp+2F0h+hKey], r14
0x180002bfd  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180002c01  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002c06  mov     [rsp+2F0h+lpdwDisposition], r14; lpdwDisposition
0x180002c0b  lea     rax, [rsp+2F0h+hKey]
0x180002c10  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180002c15  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180002c19  mov     [rsp+2F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180002c1e  xor     r9d, r9d; lpClass
0x180002c21  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x180002c29  xor     r8d, r8d; Reserved
0x180002c2c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002c33  mov     [rsp+2F0h+dwOptions], r14d; dwOptions
0x180002c38  call    cs:__imp_RegCreateKeyExW
0x180002c3e  test    eax, eax
0x180002c40  jz      short loc_180002C4C
0x180002c42  or      eax, 80070000h
0x180002c47  jmp     loc_180002E8F
0x180002c4c  mov     r9, rdi
0x180002c4f  lea     r8, aLs; "%ls"
0x180002c56  mov     rdx, rbx; unsigned __int64
0x180002c59  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180002c5d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002c62  mov     r8, rbx
0x180002c65  lea     rax, [rbp+1F0h+SubKey]
0x180002c69  cmp     [rax], r14w
0x180002c6d  jz      short loc_180002C79
0x180002c6f  add     rax, 2
0x180002c73  sub     r8, 1
0x180002c77  jnz     short loc_180002C69
0x180002c79  mov     rax, r8
0x180002c7c  mov     rdx, rbx
0x180002c7f  neg     rax
0x180002c82  mov     rcx, r8
0x180002c85  sbb     eax, eax
0x180002c87  sub     rdx, r8
0x180002c8a  not     eax
0x180002c8c  and     eax, 80070057h
0x180002c91  neg     rcx
0x180002c94  sbb     r9, r9
0x180002c97  and     r9, rdx
0x180002c9a  test    r8, r8
0x180002c9d  jz      loc_180002E8F
0x180002ca3  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180002ca8  lea     eax, ds:2[r9*2]
0x180002cb0  mov     [rsp+2F0h+samDesired], eax; cbData
0x180002cb4  mov     r9d, 1; dwType
0x180002cba  lea     rax, [rbp+1F0h+SubKey]
0x180002cbe  xor     r8d, r8d; Reserved
0x180002cc1  xor     edx, edx; lpValueName
0x180002cc3  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180002cc8  call    cs:__imp_RegSetValueExW
0x180002cce  mov     edi, eax
0x180002cd0  test    eax, eax
0x180002cd2  jz      short loc_180002CEC
0x180002cd4  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180002cd9  call    cs:__imp_RegCloseKey
0x180002cdf  or      edi, 80070000h
0x180002ce5  mov     eax, edi
0x180002ce7  jmp     loc_180002E8F
0x180002cec  lea     r9, aInprocserver32; "InprocServer32"
0x180002cf3  mov     [rsp+2F0h+var_298], r14
0x180002cf8  lea     r8, aLs; "%ls"
0x180002cff  mov     rdx, rbx; unsigned __int64
0x180002d02  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180002d06  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002d0b  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180002d10  lea     rax, [rsp+2F0h+var_298]
0x180002d15  mov     [rsp+2F0h+lpdwDisposition], r14; lpdwDisposition
0x180002d1a  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180002d1e  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180002d23  xor     r9d, r9d; lpClass
0x180002d26  mov     [rsp+2F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180002d2b  xor     r8d, r8d; Reserved
0x180002d2e  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x180002d36  mov     [rsp+2F0h+dwOptions], r14d; dwOptions
0x180002d3b  call    cs:__imp_RegCreateKeyExW
0x180002d41  mov     edi, eax
0x180002d43  test    eax, eax
0x180002d45  jnz     short loc_180002CD4
0x180002d47  mov     r9, rsi
0x180002d4a  lea     r8, aLs; "%ls"
0x180002d51  mov     rdx, rbx; unsigned __int64
0x180002d54  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180002d58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002d5d  mov     r8, rbx
0x180002d60  lea     rax, [rbp+1F0h+SubKey]
0x180002d64  cmp     [rax], r14w
0x180002d68  jz      short loc_180002D74
0x180002d6a  add     rax, 2
0x180002d6e  sub     r8, 1
0x180002d72  jnz     short loc_180002D64
0x180002d74  mov     rax, r8
0x180002d77  mov     rdx, rbx
0x180002d7a  neg     rax
0x180002d7d  mov     rcx, r8
0x180002d80  sbb     eax, eax
0x180002d82  sub     rdx, r8
0x180002d85  not     eax
0x180002d87  and     eax, 80070057h
0x180002d8c  neg     rcx
0x180002d8f  sbb     r9, r9
0x180002d92  and     r9, rdx
0x180002d95  test    r8, r8
0x180002d98  jz      loc_180002E8F
0x180002d9e  mov     rcx, [rsp+2F0h+var_298]; hKey
0x180002da3  lea     eax, ds:2[r9*2]
0x180002dab  mov     [rsp+2F0h+samDesired], eax; cbData
0x180002daf  mov     r9d, 1; dwType
0x180002db5  lea     rax, [rbp+1F0h+SubKey]
0x180002db9  xor     r8d, r8d; Reserved
0x180002dbc  xor     edx, edx; lpValueName
0x180002dbe  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180002dc3  call    cs:__imp_RegSetValueExW
0x180002dc9  mov     edi, eax
0x180002dcb  test    eax, eax
0x180002dcd  jz      short loc_180002DE4
0x180002dcf  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180002dd4  call    cs:__imp_RegCloseKey
0x180002dda  mov     rcx, [rsp+2F0h+var_298]
0x180002ddf  jmp     loc_180002CD9
0x180002de4  lea     r9, aBoth; "Both"
0x180002deb  mov     rdx, rbx; unsigned __int64
0x180002dee  lea     r8, aLs; "%ls"
0x180002df5  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180002df9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002dfe  mov     rdx, rbx
0x180002e01  lea     rax, [rbp+1F0h+SubKey]
0x180002e05  cmp     [rax], r14w
0x180002e09  jz      short loc_180002E15
0x180002e0b  add     rax, 2
0x180002e0f  sub     rdx, 1
0x180002e13  jnz     short loc_180002E05
0x180002e15  mov     rax, rdx
0x180002e18  mov     rcx, rdx
0x180002e1b  neg     rax
0x180002e1e  sbb     eax, eax
0x180002e20  sub     rbx, rdx
0x180002e23  not     eax
0x180002e25  and     eax, 80070057h
0x180002e2a  neg     rcx
0x180002e2d  sbb     r8, r8
0x180002e30  and     r8, rbx
0x180002e33  test    rdx, rdx
0x180002e36  jz      short loc_180002E8F
0x180002e38  mov     rcx, [rsp+2F0h+var_298]; hKey
0x180002e3d  lea     eax, ds:2[r8*2]
0x180002e45  mov     [rsp+2F0h+samDesired], eax; cbData
0x180002e49  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180002e50  lea     rax, [rbp+1F0h+SubKey]
0x180002e54  mov     r9d, 1; dwType
0x180002e5a  xor     r8d, r8d; Reserved
0x180002e5d  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180002e62  call    cs:__imp_RegSetValueExW
0x180002e68  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180002e6d  mov     ebx, eax
0x180002e6f  call    cs:__imp_RegCloseKey
0x180002e75  mov     rcx, [rsp+2F0h+var_298]; hKey
0x180002e7a  call    cs:__imp_RegCloseKey
0x180002e80  test    ebx, ebx
0x180002e82  jle     short loc_180002E8D
0x180002e84  movzx   ebx, bx
0x180002e87  or      ebx, 80070000h
0x180002e8d  mov     eax, ebx
0x180002e8f  mov     rcx, [rbp+1F0h+var_30]
0x180002e96  xor     rcx, rsp; StackCookie
0x180002e99  call    __security_check_cookie
0x180002e9e  add     rsp, 2D0h
0x180002ea5  pop     r14
0x180002ea7  pop     rdi
0x180002ea8  pop     rsi
0x180002ea9  pop     rbx
0x180002eaa  pop     rbp
0x180002eab  retn
```
