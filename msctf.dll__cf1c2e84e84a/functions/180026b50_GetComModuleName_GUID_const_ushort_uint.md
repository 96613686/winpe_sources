# GetComModuleName(_GUID const &,ushort *,uint)

- ea: `0x180026b50`
- end: `0x180026d20`
- name: `?GetComModuleName@@YAHAEBU_GUID@@PEAGI@Z`
- size: `464`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024b88`
- `0x180026d28`

## callees

- `0x18000fac0`
- `0x180026580`
- `0x180026b50`
- `0x180069160`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026be7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026ca8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026be7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026ca8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026cba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026cf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026cba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026cf1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026c43`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026c43`

## string_xrefs

- `0x180026bb4`: `SOFTWARE\Classes\CLSID\%s\InProcServer32`
- `0x180026c71`: `SOFTWARE\Classes\CLSID\%s\LocalServer32`
- `0x180026c02`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall GetComModuleName(const struct _GUID *a1, unsigned __int16 *a2)
{
  HKEY v3; // rbx
  __int64 result; // rax
  unsigned int v5; // edi
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  void **v8; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v9; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v10[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR String1[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v3 = 0;
  v8 = &CPreloadRegKey::`vftable';
  v9 = 0;
  result = CLSIDToStringW(a1, v10);
  if ( (_DWORD)result )
  {
    StringCchPrintfW(SubKey, 0x104u, L"SOFTWARE\\Classes\\CLSID\\%s\\InProcServer32", v10);
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey)
      || (v3 = hKey, v9 = hKey, CMyRegKey::QueryValueCch((CMyRegKey *)&v8, String1, L"ThreadingModel", 0x104u))
      || (v5 = 1, CompareStringW(0x7Fu, 1u, String1, -1, L"Apartment", -1) != 2)
      || CMyRegKey::QueryValueCch((CMyRegKey *)&v8, a2, 0, 0x104u) )
    {
      StringCchPrintfW(SubKey, 0x104u, L"SOFTWARE\\Classes\\CLSID\\%s\\LocalServer32", v10);
      hKey = 0;
      v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      if ( !v6 )
      {
        if ( v3 )
          v6 = RegCloseKey(v3);
        v3 = hKey;
        v9 = hKey;
      }
      v5 = 0;
      if ( !v6 )
        LOBYTE(v5) = CMyRegKey::QueryValueCch((CMyRegKey *)&v8, a2, 0, 0x104u) == 0;
    }
    if ( v3 )
      RegCloseKey(v3);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180026b50  mov     [rsp-8+arg_10], rbx
0x180026b55  mov     [rsp-8+arg_18], rsi
0x180026b5a  push    rbp
0x180026b5b  push    rdi
0x180026b5c  push    r14
0x180026b5e  lea     rbp, [rsp-3D0h]
0x180026b66  sub     rsp, 4D0h
0x180026b6d  mov     rax, cs:__security_cookie
0x180026b74  xor     rax, rsp
0x180026b77  mov     [rbp+3E0h+var_20], rax
0x180026b7e  mov     rsi, rdx
0x180026b81  lea     rax, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x180026b88  xor     ebx, ebx
0x180026b8a  mov     [rsp+4E0h+var_4A8], rax
0x180026b8f  lea     rdx, [rsp+4E0h+var_490]; unsigned __int16 *
0x180026b94  mov     [rsp+4E0h+var_4A0], rbx
0x180026b99  call    ?CLSIDToStringW@@YAHAEBU_GUID@@PEAG@Z; CLSIDToStringW(_GUID const &,ushort *)
0x180026b9e  test    eax, eax
0x180026ba0  jz      loc_180026CF9
0x180026ba6  mov     r14d, 104h
0x180026bac  lea     r9, [rsp+4E0h+var_490]
0x180026bb1  mov     edx, r14d; unsigned __int64
0x180026bb4  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\CLSID\\%s\\InProcSer"...
0x180026bbb  lea     rcx, [rbp+3E0h+SubKey]; unsigned __int16 *
0x180026bbf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026bc4  lea     rax, [rsp+4E0h+hKey]
0x180026bc9  mov     [rsp+4E0h+hKey], rbx
0x180026bce  mov     r9d, 20019h; samDesired
0x180026bd4  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180026bd9  xor     r8d, r8d; ulOptions
0x180026bdc  lea     rdx, [rbp+3E0h+SubKey]; lpSubKey
0x180026be0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026be7  call    cs:__imp_RegOpenKeyExW
0x180026bed  test    eax, eax
0x180026bef  jnz     short loc_180026C69
0x180026bf1  mov     rbx, [rsp+4E0h+hKey]
0x180026bf6  mov     [rsp+4E0h+var_4A0], rbx
0x180026bfb  test    eax, eax
0x180026bfd  jnz     short loc_180026C69
0x180026bff  mov     r9d, r14d; unsigned int
0x180026c02  lea     r8, aThreadingmodel; "ThreadingModel"
0x180026c09  lea     rdx, [rbp+3E0h+String1]; unsigned __int16 *
0x180026c10  lea     rcx, [rsp+4E0h+var_4A8]; this
0x180026c15  call    ?QueryValueCch@CMyRegKey@@UEAAJPEAGPEBGK@Z; CMyRegKey::QueryValueCch(ushort *,ushort const *,ulong)
0x180026c1a  test    eax, eax
0x180026c1c  jnz     short loc_180026C69
0x180026c1e  or      r9d, 0FFFFFFFFh; cchCount1
0x180026c22  lea     rax, aApartment; "Apartment"
0x180026c29  mov     [rsp+4E0h+cchCount2], r9d; cchCount2
0x180026c2e  lea     r8, [rbp+3E0h+String1]; lpString1
0x180026c35  mov     [rsp+4E0h+phkResult], rax; lpString2
0x180026c3a  lea     edi, [r9+2]
0x180026c3e  mov     edx, edi; dwCmpFlags
0x180026c40  lea     ecx, [rdi+7Eh]; Locale
0x180026c43  call    cs:__imp_CompareStringW
0x180026c49  cmp     eax, 2
0x180026c4c  jnz     short loc_180026C69
0x180026c4e  mov     r9d, r14d; unsigned int
0x180026c51  lea     rcx, [rsp+4E0h+var_4A8]; this
0x180026c56  xor     r8d, r8d; unsigned __int16 *
0x180026c59  mov     rdx, rsi; unsigned __int16 *
0x180026c5c  call    ?QueryValueCch@CMyRegKey@@UEAAJPEAGPEBGK@Z; CMyRegKey::QueryValueCch(ushort *,ushort const *,ulong)
0x180026c61  test    eax, eax
0x180026c63  jz      loc_180026CE9
0x180026c69  lea     r9, [rsp+4E0h+var_490]
0x180026c6e  mov     rdx, r14; unsigned __int64
0x180026c71  lea     r8, aSoftwareClasse_0; "SOFTWARE\\Classes\\CLSID\\%s\\LocalServ"...
0x180026c78  lea     rcx, [rbp+3E0h+SubKey]; unsigned __int16 *
0x180026c7c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026c81  lea     rax, [rsp+4E0h+hKey]
0x180026c86  mov     [rsp+4E0h+hKey], 0
0x180026c8f  mov     r9d, 20019h; samDesired
0x180026c95  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180026c9a  xor     r8d, r8d; ulOptions
0x180026c9d  lea     rdx, [rbp+3E0h+SubKey]; lpSubKey
0x180026ca1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026ca8  call    cs:__imp_RegOpenKeyExW
0x180026cae  test    eax, eax
0x180026cb0  jnz     short loc_180026CCA
0x180026cb2  test    rbx, rbx
0x180026cb5  jz      short loc_180026CC0
0x180026cb7  mov     rcx, rbx; hKey
0x180026cba  call    cs:__imp_RegCloseKey
0x180026cc0  mov     rbx, [rsp+4E0h+hKey]
0x180026cc5  mov     [rsp+4E0h+var_4A0], rbx
0x180026cca  xor     edi, edi
0x180026ccc  test    eax, eax
0x180026cce  jnz     short loc_180026CE9
0x180026cd0  mov     r9d, r14d; unsigned int
0x180026cd3  lea     rcx, [rsp+4E0h+var_4A8]; this
0x180026cd8  xor     r8d, r8d; unsigned __int16 *
0x180026cdb  mov     rdx, rsi; unsigned __int16 *
0x180026cde  call    ?QueryValueCch@CMyRegKey@@UEAAJPEAGPEBGK@Z; CMyRegKey::QueryValueCch(ushort *,ushort const *,ulong)
0x180026ce3  test    eax, eax
0x180026ce5  setz    dil
0x180026ce9  test    rbx, rbx
0x180026cec  jz      short loc_180026CF7
0x180026cee  mov     rcx, rbx; hKey
0x180026cf1  call    cs:__imp_RegCloseKey
0x180026cf7  mov     eax, edi
0x180026cf9  mov     rcx, [rbp+3E0h+var_20]
0x180026d00  xor     rcx, rsp; StackCookie
0x180026d03  call    __security_check_cookie
0x180026d08  lea     r11, [rsp+4E0h+var_10]
0x180026d10  mov     rbx, [r11+30h]
0x180026d14  mov     rsi, [r11+38h]
0x180026d18  mov     rsp, r11
0x180026d1b  pop     r14
0x180026d1d  pop     rdi
0x180026d1e  pop     rbp
0x180026d1f  retn
```
