# AMovieSetupRegisterServer

- ea: `0x180025980`
- end: `0x180025cc5`
- name: `AMovieSetupRegisterServer`
- size: `837`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180025658`

## callees

- `0x1800017b0`
- `0x180017ba0`
- `0x180025980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800259b8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800259b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025ab0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025bbd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025c68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025ab0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025bbd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025c68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025ac7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025bd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025c7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025c8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025ac7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025bd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025c7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025c8c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025a1a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025b2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025a1a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025b2f`

## string_xrefs

- `0x1800259d1`: `CLSID\%ls`
- `0x180025c4f`: `ThreadingModel`

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
0x180025980  push    rbp
0x180025982  push    rbx
0x180025983  push    rsi
0x180025984  push    rdi
0x180025985  push    r14
0x180025987  lea     rbp, [rsp-1D0h]
0x18002598f  sub     rsp, 2D0h
0x180025996  mov     rax, cs:__security_cookie
0x18002599d  xor     rax, rsp
0x1800259a0  mov     [rbp+1F0h+var_30], rax
0x1800259a7  mov     rsi, r8
0x1800259aa  mov     rdi, rdx
0x1800259ad  mov     r8d, 27h ; '''; cchMax
0x1800259b3  lea     rdx, [rsp+2F0h+sz]; lpsz
0x1800259b8  call    cs:__imp_StringFromGUID2
0x1800259bf  nop     dword ptr [rax+rax+00h]
0x1800259c4  mov     ebx, 104h
0x1800259c9  lea     r9, [rsp+2F0h+sz]
0x1800259ce  xor     r14d, r14d
0x1800259d1  lea     r8, aClsidLs; "CLSID\\%ls"
0x1800259d8  mov     edx, ebx; unsigned __int64
0x1800259da  mov     [rsp+2F0h+hKey], r14
0x1800259df  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x1800259e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800259e8  mov     [rsp+2F0h+lpdwDisposition], r14; lpdwDisposition
0x1800259ed  lea     rax, [rsp+2F0h+hKey]
0x1800259f2  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1800259f7  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x1800259fb  mov     [rsp+2F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180025a00  xor     r9d, r9d; lpClass
0x180025a03  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x180025a0b  xor     r8d, r8d; Reserved
0x180025a0e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180025a15  mov     [rsp+2F0h+dwOptions], r14d; dwOptions
0x180025a1a  call    cs:__imp_RegCreateKeyExW
0x180025a21  nop     dword ptr [rax+rax+00h]
0x180025a26  test    eax, eax
0x180025a28  jz      short loc_180025A34
0x180025a2a  or      eax, 80070000h
0x180025a2f  jmp     loc_180025CA7
0x180025a34  mov     r9, rdi
0x180025a37  lea     r8, aLs; "%ls"
0x180025a3e  mov     rdx, rbx; unsigned __int64
0x180025a41  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180025a45  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025a4a  mov     r8, rbx
0x180025a4d  lea     rax, [rbp+1F0h+SubKey]
0x180025a51  cmp     [rax], r14w
0x180025a55  jz      short loc_180025A61
0x180025a57  add     rax, 2
0x180025a5b  sub     r8, 1
0x180025a5f  jnz     short loc_180025A51
0x180025a61  mov     rax, r8
0x180025a64  mov     rdx, rbx
0x180025a67  neg     rax
0x180025a6a  mov     rcx, r8
0x180025a6d  sbb     eax, eax
0x180025a6f  sub     rdx, r8
0x180025a72  not     eax
0x180025a74  and     eax, 80070057h
0x180025a79  neg     rcx
0x180025a7c  sbb     r9, r9
0x180025a7f  and     r9, rdx
0x180025a82  test    r8, r8
0x180025a85  jz      loc_180025CA7
0x180025a8b  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180025a90  lea     eax, ds:2[r9*2]
0x180025a98  mov     [rsp+2F0h+samDesired], eax; cbData
0x180025a9c  mov     r9d, 1; dwType
0x180025aa2  lea     rax, [rbp+1F0h+SubKey]
0x180025aa6  xor     r8d, r8d; Reserved
0x180025aa9  xor     edx, edx; lpValueName
0x180025aab  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180025ab0  call    cs:__imp_RegSetValueExW
0x180025ab7  nop     dword ptr [rax+rax+00h]
0x180025abc  mov     edi, eax
0x180025abe  test    eax, eax
0x180025ac0  jz      short loc_180025AE0
0x180025ac2  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180025ac7  call    cs:__imp_RegCloseKey
0x180025ace  nop     dword ptr [rax+rax+00h]
0x180025ad3  or      edi, 80070000h
0x180025ad9  mov     eax, edi
0x180025adb  jmp     loc_180025CA7
0x180025ae0  lea     r9, aInprocserver32; "InprocServer32"
0x180025ae7  mov     [rsp+2F0h+var_298], r14
0x180025aec  lea     r8, aLs; "%ls"
0x180025af3  mov     rdx, rbx; unsigned __int64
0x180025af6  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180025afa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025aff  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180025b04  lea     rax, [rsp+2F0h+var_298]
0x180025b09  mov     [rsp+2F0h+lpdwDisposition], r14; lpdwDisposition
0x180025b0e  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180025b12  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180025b17  xor     r9d, r9d; lpClass
0x180025b1a  mov     [rsp+2F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180025b1f  xor     r8d, r8d; Reserved
0x180025b22  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x180025b2a  mov     [rsp+2F0h+dwOptions], r14d; dwOptions
0x180025b2f  call    cs:__imp_RegCreateKeyExW
0x180025b36  nop     dword ptr [rax+rax+00h]
0x180025b3b  mov     edi, eax
0x180025b3d  test    eax, eax
0x180025b3f  jnz     short loc_180025AC2
0x180025b41  mov     r9, rsi
0x180025b44  lea     r8, aLs; "%ls"
0x180025b4b  mov     rdx, rbx; unsigned __int64
0x180025b4e  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180025b52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025b57  mov     r8, rbx
0x180025b5a  lea     rax, [rbp+1F0h+SubKey]
0x180025b5e  cmp     [rax], r14w
0x180025b62  jz      short loc_180025B6E
0x180025b64  add     rax, 2
0x180025b68  sub     r8, 1
0x180025b6c  jnz     short loc_180025B5E
0x180025b6e  mov     rax, r8
0x180025b71  mov     rdx, rbx
0x180025b74  neg     rax
0x180025b77  mov     rcx, r8
0x180025b7a  sbb     eax, eax
0x180025b7c  sub     rdx, r8
0x180025b7f  not     eax
0x180025b81  and     eax, 80070057h
0x180025b86  neg     rcx
0x180025b89  sbb     r9, r9
0x180025b8c  and     r9, rdx
0x180025b8f  test    r8, r8
0x180025b92  jz      loc_180025CA7
0x180025b98  mov     rcx, [rsp+2F0h+var_298]; hKey
0x180025b9d  lea     eax, ds:2[r9*2]
0x180025ba5  mov     [rsp+2F0h+samDesired], eax; cbData
0x180025ba9  mov     r9d, 1; dwType
0x180025baf  lea     rax, [rbp+1F0h+SubKey]
0x180025bb3  xor     r8d, r8d; Reserved
0x180025bb6  xor     edx, edx; lpValueName
0x180025bb8  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180025bbd  call    cs:__imp_RegSetValueExW
0x180025bc4  nop     dword ptr [rax+rax+00h]
0x180025bc9  mov     edi, eax
0x180025bcb  test    eax, eax
0x180025bcd  jz      short loc_180025BEA
0x180025bcf  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180025bd4  call    cs:__imp_RegCloseKey
0x180025bdb  nop     dword ptr [rax+rax+00h]
0x180025be0  mov     rcx, [rsp+2F0h+var_298]
0x180025be5  jmp     loc_180025AC7
0x180025bea  lea     r9, aBoth; "Both"
0x180025bf1  mov     rdx, rbx; unsigned __int64
0x180025bf4  lea     r8, aLs; "%ls"
0x180025bfb  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180025bff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025c04  mov     rdx, rbx
0x180025c07  lea     rax, [rbp+1F0h+SubKey]
0x180025c0b  cmp     [rax], r14w
0x180025c0f  jz      short loc_180025C1B
0x180025c11  add     rax, 2
0x180025c15  sub     rdx, 1
0x180025c19  jnz     short loc_180025C0B
0x180025c1b  mov     rax, rdx
0x180025c1e  mov     rcx, rdx
0x180025c21  neg     rax
0x180025c24  sbb     eax, eax
0x180025c26  sub     rbx, rdx
0x180025c29  not     eax
0x180025c2b  and     eax, 80070057h
0x180025c30  neg     rcx
0x180025c33  sbb     r8, r8
0x180025c36  and     r8, rbx
0x180025c39  test    rdx, rdx
0x180025c3c  jz      short loc_180025CA7
0x180025c3e  mov     rcx, [rsp+2F0h+var_298]; hKey
0x180025c43  lea     eax, ds:2[r8*2]
0x180025c4b  mov     [rsp+2F0h+samDesired], eax; cbData
0x180025c4f  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180025c56  lea     rax, [rbp+1F0h+SubKey]
0x180025c5a  mov     r9d, 1; dwType
0x180025c60  xor     r8d, r8d; Reserved
0x180025c63  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180025c68  call    cs:__imp_RegSetValueExW
0x180025c6f  nop     dword ptr [rax+rax+00h]
0x180025c74  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180025c79  mov     ebx, eax
0x180025c7b  call    cs:__imp_RegCloseKey
0x180025c82  nop     dword ptr [rax+rax+00h]
0x180025c87  mov     rcx, [rsp+2F0h+var_298]; hKey
0x180025c8c  call    cs:__imp_RegCloseKey
0x180025c93  nop     dword ptr [rax+rax+00h]
0x180025c98  test    ebx, ebx
0x180025c9a  jle     short loc_180025CA5
0x180025c9c  movzx   ebx, bx
0x180025c9f  or      ebx, 80070000h
0x180025ca5  mov     eax, ebx
0x180025ca7  mov     rcx, [rbp+1F0h+var_30]
0x180025cae  xor     rcx, rsp; StackCookie
0x180025cb1  call    __security_check_cookie
0x180025cb6  add     rsp, 2D0h
0x180025cbd  pop     r14
0x180025cbf  pop     rdi
0x180025cc0  pop     rsi
0x180025cc1  pop     rbx
0x180025cc2  pop     rbp
0x180025cc3  retn
```
