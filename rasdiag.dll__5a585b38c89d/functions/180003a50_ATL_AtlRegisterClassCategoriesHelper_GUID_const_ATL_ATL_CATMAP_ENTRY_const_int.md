# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180003a50`
- end: `0x180003f77`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1319`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005824`
- `0x180005e50`

## callees

- `0x180003a50`
- `0x18000418c`
- `0x1800042e0`
- `0x18000df10`
- `0x18000f010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180003c14`
- `msvcrt!wcscat_s` at `0x180003c56`
- `msvcrt!wcscat_s` at `0x180003da6`
- `msvcrt!wcscat_s` at `0x180003de8`
- `msvcrt!wcscat_s` at `0x180003c14`
- `msvcrt!wcscat_s` at `0x180003c56`
- `msvcrt!wcscat_s` at `0x180003da6`
- `msvcrt!wcscat_s` at `0x180003de8`
- `msvcrt!wcscpy_s` at `0x180003bca`
- `msvcrt!wcscpy_s` at `0x180003d64`
- `msvcrt!wcscpy_s` at `0x180003bca`
- `msvcrt!wcscpy_s` at `0x180003d64`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003d11`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003ea7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003d11`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003ea7`
- `ADVAPI32!RegOpenKeyExW` at `0x180003cc4`
- `ADVAPI32!RegOpenKeyExW` at `0x180003e3b`
- `ADVAPI32!RegOpenKeyExW` at `0x180003cc4`
- `ADVAPI32!RegOpenKeyExW` at `0x180003e3b`
- `ADVAPI32!RegCloseKey` at `0x180003d27`
- `ADVAPI32!RegCloseKey` at `0x180003e5a`
- `ADVAPI32!RegCloseKey` at `0x180003ebd`
- `ADVAPI32!RegCloseKey` at `0x180003ef0`
- `ADVAPI32!RegCloseKey` at `0x180003f04`
- `ADVAPI32!RegCloseKey` at `0x180003d27`
- `ADVAPI32!RegCloseKey` at `0x180003e5a`
- `ADVAPI32!RegCloseKey` at `0x180003ebd`
- `ADVAPI32!RegCloseKey` at `0x180003ef0`
- `ADVAPI32!RegCloseKey` at `0x180003f04`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003af7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003af7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003bac`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003bac`

## string_xrefs

- `0x180003bb8`: `CLSID\`
- `0x180003d52`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rdi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v10; // rax
  int v11; // ecx
  errno_t v12; // eax
  errno_t v13; // eax
  errno_t v14; // eax
  HKEY v15; // rdi
  HKEY v16; // rbx
  LSTATUS v17; // esi
  errno_t v18; // eax
  errno_t v19; // eax
  errno_t v20; // eax
  HKEY v21; // rbx
  LSTATUS v22; // esi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v27[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+98h] [rbp-68h] BYREF
  wchar_t Destination[128]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = a2;
  ppv = 0;
  v28 = 0;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    return 0;
  }
  if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
LABEL_66:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 0;
  }
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( a3 )
        goto LABEL_66;
      StringFromGUID2(rguid, sz, 64);
      v12 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      if ( v12 )
      {
        if ( v12 == 12 )
          goto LABEL_69;
        if ( v12 == 22 || v12 == 34 )
          goto LABEL_71;
        if ( v12 != 80 )
          goto LABEL_70;
      }
      v13 = wcscat_s(Destination, 0x80u, sz);
      if ( v13 )
      {
        if ( v13 == 12 )
          goto LABEL_69;
        if ( v13 == 22 || v13 == 34 )
          goto LABEL_71;
        if ( v13 != 80 )
          goto LABEL_70;
      }
      v14 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      if ( v14 )
      {
        if ( v14 == 12 )
          goto LABEL_69;
        if ( v14 == 22 || v14 == 34 )
          goto LABEL_71;
        if ( v14 != 80 )
          goto LABEL_70;
      }
      v15 = HKEY_CLASSES_ROOT;
      v27[0] = 0xFFFFFFFF80000000uLL;
      v27[1] = 0;
      v27[2] = 0;
      cSubKeys = 0;
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult) )
      {
        v16 = phkResult;
        v17 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        if ( v16 )
          RegCloseKey(v16);
        if ( !v17 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, Destination);
          v15 = (HKEY)v27[0];
        }
      }
      v18 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      if ( v18 )
      {
        if ( v18 == 12 )
          goto LABEL_69;
        if ( v18 == 22 || v18 == 34 )
          goto LABEL_71;
        if ( v18 != 80 )
          goto LABEL_70;
      }
      v19 = wcscat_s(Destination, 0x80u, sz);
      if ( v19 )
      {
        if ( v19 == 12 )
          goto LABEL_69;
        if ( v19 == 22 || v19 == 34 )
          goto LABEL_71;
        if ( v19 != 80 )
          goto LABEL_70;
      }
      v20 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      if ( !v20 )
      {
LABEL_58:
        hKey = 0;
        if ( !RegOpenKeyExW(v15, Destination, 0, 0x20019u, &hKey) )
        {
          v21 = hKey;
          v22 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v21 )
            RegCloseKey(v21);
          if ( !v22 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, Destination);
            v15 = (HKEY)v27[0];
          }
        }
        if ( v15 )
          RegCloseKey(v15);
        goto LABEL_66;
      }
      if ( v20 != 12 )
      {
        if ( v20 != 22 && v20 != 34 )
        {
          if ( v20 == 80 )
            goto LABEL_58;
LABEL_70:
          ATL::AtlThrowImpl(-2147467259);
        }
LABEL_71:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_69:
      ATL::AtlThrowImpl(-2147024882);
    }
    v28 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( !a3 )
    {
      v10 = *(_QWORD *)ppv;
      if ( v11 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 48))(ppv, rguid, 1, &v28);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 64))(ppv, rguid, 1, &v28);
      goto LABEL_19;
    }
    v6 = *(_QWORD *)ppv;
    v7 = v11 == 1
       ? (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v28)
       : (*(unsigned __int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v28);
    v8 = v7;
    if ( v7 < 0 )
      break;
LABEL_19:
    v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x180003a50  mov     [rsp-8+arg_10], rbx
0x180003a55  mov     [rsp-8+arg_18], rsi
0x180003a5a  push    rbp
0x180003a5b  push    rdi
0x180003a5c  push    r12
0x180003a5e  push    r14
0x180003a60  push    r15
0x180003a62  lea     rbp, [rsp-140h]
0x180003a6a  sub     rsp, 240h
0x180003a71  mov     rax, cs:__security_cookie
0x180003a78  xor     rax, rsp
0x180003a7b  mov     [rbp+160h+var_30], rax
0x180003a82  mov     r14d, r8d
0x180003a85  mov     rdi, rdx
0x180003a88  mov     rbx, rcx
0x180003a8b  xor     r15d, r15d
0x180003a8e  mov     [rsp+260h+var_1F8], r15
0x180003a93  xorps   xmm0, xmm0
0x180003a96  movups  [rbp+160h+var_1C8], xmm0
0x180003a9a  test    rdx, rdx
0x180003a9d  jnz     short loc_180003AA4
0x180003a9f  jmp     loc_180003F28
0x180003aa4  mov     eax, cs:GUID_NULL.Data1
0x180003aaa  cmp     [rcx], eax
0x180003aac  jnz     short loc_180003AD4
0x180003aae  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180003ab4  cmp     [rcx+4], eax
0x180003ab7  jnz     short loc_180003AD4
0x180003ab9  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180003abf  cmp     [rcx+8], eax
0x180003ac2  jnz     short loc_180003AD4
0x180003ac4  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180003aca  cmp     [rcx+0Ch], eax
0x180003acd  jnz     short loc_180003AD4
0x180003acf  jmp     loc_180003F28
0x180003ad4  lea     rax, [rsp+260h+var_1F8]
0x180003ad9  mov     [rsp+260h+ppv], rax; ppv
0x180003ade  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180003ae5  mov     r12d, 1
0x180003aeb  mov     r8d, r12d; dwClsContext
0x180003aee  xor     edx, edx; pUnkOuter
0x180003af0  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180003af7  call    cs:__imp_CoCreateInstance
0x180003afe  nop     dword ptr [rax+rax+00h]
0x180003b03  test    eax, eax
0x180003b05  jns     loc_180003B8B
0x180003b0b  jmp     loc_180003F11
0x180003b10  mov     rax, [rdi+8]
0x180003b14  movups  xmm0, xmmword ptr [rax]
0x180003b17  movdqu  [rbp+160h+var_1C8], xmm0
0x180003b1c  lea     r9, [rbp+160h+var_1C8]
0x180003b20  mov     r8d, r12d
0x180003b23  mov     rdx, rbx
0x180003b26  test    r14d, r14d
0x180003b29  jz      short loc_180003B6B
0x180003b2b  cmp     ecx, r12d
0x180003b2e  mov     rcx, [rsp+260h+var_1F8]
0x180003b33  mov     rax, [rcx]
0x180003b36  jnz     short loc_180003B3E
0x180003b38  mov     rax, [rax+28h]
0x180003b3c  jmp     short loc_180003B42
0x180003b3e  mov     rax, [rax+38h]
0x180003b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b47  mov     esi, eax
0x180003b49  test    eax, eax
0x180003b4b  jns     short loc_180003B87
0x180003b4d  mov     rcx, [rsp+260h+var_1F8]
0x180003b52  test    rcx, rcx
0x180003b55  jz      short loc_180003B64
0x180003b57  mov     rax, [rcx]
0x180003b5a  mov     rax, [rax+10h]
0x180003b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b63  nop
0x180003b64  mov     eax, esi
0x180003b66  jmp     loc_180003F2A
0x180003b6b  cmp     ecx, r12d
0x180003b6e  mov     rcx, [rsp+260h+var_1F8]
0x180003b73  mov     rax, [rcx]
0x180003b76  jnz     short loc_180003B7E
0x180003b78  mov     rax, [rax+30h]
0x180003b7c  jmp     short loc_180003B82
0x180003b7e  mov     rax, [rax+40h]
0x180003b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b87  add     rdi, 10h
0x180003b8b  mov     ecx, [rdi]
0x180003b8d  test    ecx, ecx
0x180003b8f  jnz     loc_180003B10
0x180003b95  test    r14d, r14d
0x180003b98  jnz     loc_180003F11
0x180003b9e  lea     r8d, [rcx+40h]; cchMax
0x180003ba2  lea     rdx, [rbp+160h+sz]; lpsz
0x180003ba9  mov     rcx, rbx; rguid
0x180003bac  call    cs:__imp_StringFromGUID2
0x180003bb3  nop     dword ptr [rax+rax+00h]
0x180003bb8  lea     r8, aClsid; "CLSID\\"
0x180003bbf  mov     ebx, 80h
0x180003bc4  mov     edx, ebx; SizeInWords
0x180003bc6  lea     rcx, [rbp+160h+Destination]; Destination
0x180003bca  call    cs:__imp_wcscpy_s
0x180003bd1  nop     dword ptr [rax+rax+00h]
0x180003bd6  lea     r14d, [rbx-74h]
0x180003bda  lea     r12d, [rbx-30h]
0x180003bde  test    eax, eax
0x180003be0  jz      short loc_180003C06
0x180003be2  cmp     eax, r14d
0x180003be5  jz      loc_180003F56
0x180003beb  cmp     eax, 16h
0x180003bee  jz      loc_180003F6C
0x180003bf4  cmp     eax, 22h ; '"'
0x180003bf7  jz      loc_180003F6C
0x180003bfd  cmp     eax, r12d
0x180003c00  jnz     loc_180003F61
0x180003c06  lea     r8, [rbp+160h+sz]; Source
0x180003c0d  mov     rdx, rbx; SizeInWords
0x180003c10  lea     rcx, [rbp+160h+Destination]; Destination
0x180003c14  call    cs:__imp_wcscat_s
0x180003c1b  nop     dword ptr [rax+rax+00h]
0x180003c20  test    eax, eax
0x180003c22  jz      short loc_180003C48
0x180003c24  cmp     eax, r14d
0x180003c27  jz      loc_180003F56
0x180003c2d  cmp     eax, 16h
0x180003c30  jz      loc_180003F6C
0x180003c36  cmp     eax, 22h ; '"'
0x180003c39  jz      loc_180003F6C
0x180003c3f  cmp     eax, r12d
0x180003c42  jnz     loc_180003F61
0x180003c48  lea     r8, aRequiredCatego; "\\Required Categories"
0x180003c4f  mov     rdx, rbx; SizeInWords
0x180003c52  lea     rcx, [rbp+160h+Destination]; Destination
0x180003c56  call    cs:__imp_wcscat_s
0x180003c5d  nop     dword ptr [rax+rax+00h]
0x180003c62  test    eax, eax
0x180003c64  jz      short loc_180003C8A
0x180003c66  cmp     eax, r14d
0x180003c69  jz      loc_180003F56
0x180003c6f  cmp     eax, 16h
0x180003c72  jz      loc_180003F6C
0x180003c78  cmp     eax, 22h ; '"'
0x180003c7b  jz      loc_180003F6C
0x180003c81  cmp     eax, r12d
0x180003c84  jnz     loc_180003F61
0x180003c8a  mov     rdi, 0FFFFFFFF80000000h
0x180003c91  mov     [rbp+160h+var_1E0], rdi
0x180003c95  mov     [rbp+160h+var_1D8], r15
0x180003c99  mov     [rbp+160h+var_1D0], r15
0x180003c9d  mov     rbx, r15
0x180003ca0  mov     [rsp+260h+cSubKeys], r15d
0x180003ca5  mov     [rsp+260h+phkResult], r15
0x180003caa  lea     rax, [rsp+260h+phkResult]
0x180003caf  mov     [rsp+260h+ppv], rax; phkResult
0x180003cb4  mov     r9d, 20019h; samDesired
0x180003cba  xor     r8d, r8d; ulOptions
0x180003cbd  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180003cc1  mov     rcx, rdi; hKey
0x180003cc4  call    cs:__imp_RegOpenKeyExW
0x180003ccb  nop     dword ptr [rax+rax+00h]
0x180003cd0  test    eax, eax
0x180003cd2  jnz     short loc_180003D52
0x180003cd4  mov     rbx, [rsp+260h+phkResult]
0x180003cd9  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003cde  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003ce3  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003ce8  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003ced  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180003cf2  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003cf7  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003cfc  lea     rax, [rsp+260h+cSubKeys]
0x180003d01  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180003d06  xor     r9d, r9d; lpReserved
0x180003d09  xor     r8d, r8d; lpcchClass
0x180003d0c  xor     edx, edx; lpClass
0x180003d0e  mov     rcx, rbx; hKey
0x180003d11  call    cs:__imp_RegQueryInfoKeyW
0x180003d18  nop     dword ptr [rax+rax+00h]
0x180003d1d  mov     esi, eax
0x180003d1f  test    rbx, rbx
0x180003d22  jz      short loc_180003D36
0x180003d24  mov     rcx, rbx; hKey
0x180003d27  call    cs:__imp_RegCloseKey
0x180003d2e  nop     dword ptr [rax+rax+00h]
0x180003d33  mov     rbx, r15
0x180003d36  test    esi, esi
0x180003d38  jnz     short loc_180003D52
0x180003d3a  cmp     [rsp+260h+cSubKeys], r15d
0x180003d3f  jnz     short loc_180003D52
0x180003d41  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180003d45  lea     rcx, [rbp+160h+var_1E0]; this
0x180003d49  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003d4e  mov     rdi, [rbp+160h+var_1E0]
0x180003d52  lea     r8, aClsid; "CLSID\\"
0x180003d59  mov     esi, 80h
0x180003d5e  mov     edx, esi; SizeInWords
0x180003d60  lea     rcx, [rbp+160h+Destination]; Destination
0x180003d64  call    cs:__imp_wcscpy_s
0x180003d6b  nop     dword ptr [rax+rax+00h]
0x180003d70  test    eax, eax
0x180003d72  jz      short loc_180003D98
0x180003d74  cmp     eax, r14d
0x180003d77  jz      loc_180003F56
0x180003d7d  cmp     eax, 16h
0x180003d80  jz      loc_180003F6C
0x180003d86  cmp     eax, 22h ; '"'
0x180003d89  jz      loc_180003F6C
0x180003d8f  cmp     eax, r12d
0x180003d92  jnz     loc_180003F61
0x180003d98  lea     r8, [rbp+160h+sz]; Source
0x180003d9f  mov     rdx, rsi; SizeInWords
0x180003da2  lea     rcx, [rbp+160h+Destination]; Destination
0x180003da6  call    cs:__imp_wcscat_s
0x180003dad  nop     dword ptr [rax+rax+00h]
0x180003db2  test    eax, eax
0x180003db4  jz      short loc_180003DDA
0x180003db6  cmp     eax, r14d
0x180003db9  jz      loc_180003F56
0x180003dbf  cmp     eax, 16h
0x180003dc2  jz      loc_180003F6C
0x180003dc8  cmp     eax, 22h ; '"'
0x180003dcb  jz      loc_180003F6C
0x180003dd1  cmp     eax, r12d
0x180003dd4  jnz     loc_180003F61
0x180003dda  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180003de1  mov     rdx, rsi; SizeInWords
0x180003de4  lea     rcx, [rbp+160h+Destination]; Destination
0x180003de8  call    cs:__imp_wcscat_s
0x180003def  nop     dword ptr [rax+rax+00h]
0x180003df4  test    eax, eax
0x180003df6  jz      short loc_180003E1C
0x180003df8  cmp     eax, r14d
0x180003dfb  jz      loc_180003F56
0x180003e01  cmp     eax, 16h
0x180003e04  jz      loc_180003F6C
0x180003e0a  cmp     eax, 22h ; '"'
0x180003e0d  jz      loc_180003F6C
0x180003e13  cmp     eax, r12d
0x180003e16  jnz     loc_180003F61
0x180003e1c  mov     [rsp+260h+hKey], r15
0x180003e21  lea     rax, [rsp+260h+hKey]
0x180003e26  mov     [rsp+260h+ppv], rax; phkResult
0x180003e2b  mov     r9d, 20019h; samDesired
0x180003e31  xor     r8d, r8d; ulOptions
0x180003e34  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180003e38  mov     rcx, rdi; hKey
0x180003e3b  call    cs:__imp_RegOpenKeyExW
0x180003e42  nop     dword ptr [rax+rax+00h]
0x180003e47  test    eax, eax
0x180003e49  jnz     loc_180003EE8
0x180003e4f  mov     eax, r15d
0x180003e52  test    rbx, rbx
0x180003e55  jz      short loc_180003E66
0x180003e57  mov     rcx, rbx; hKey
0x180003e5a  call    cs:__imp_RegCloseKey
0x180003e61  nop     dword ptr [rax+rax+00h]
0x180003e66  mov     rbx, [rsp+260h+hKey]
0x180003e6b  test    eax, eax
0x180003e6d  jnz     short loc_180003EE8
0x180003e6f  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003e74  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003e79  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003e7e  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003e83  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180003e88  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003e8d  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003e92  lea     rax, [rsp+260h+cSubKeys]
0x180003e97  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180003e9c  xor     r9d, r9d; lpReserved
0x180003e9f  xor     r8d, r8d; lpcchClass
0x180003ea2  xor     edx, edx; lpClass
0x180003ea4  mov     rcx, rbx; hKey
0x180003ea7  call    cs:__imp_RegQueryInfoKeyW
0x180003eae  nop     dword ptr [rax+rax+00h]
0x180003eb3  mov     esi, eax
0x180003eb5  test    rbx, rbx
0x180003eb8  jz      short loc_180003ECC
0x180003eba  mov     rcx, rbx; hKey
0x180003ebd  call    cs:__imp_RegCloseKey
0x180003ec4  nop     dword ptr [rax+rax+00h]
0x180003ec9  mov     rbx, r15
0x180003ecc  test    esi, esi
0x180003ece  jnz     short loc_180003EFC
0x180003ed0  cmp     [rsp+260h+cSubKeys], r15d
0x180003ed5  jnz     short loc_180003EE8
0x180003ed7  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180003edb  lea     rcx, [rbp+160h+var_1E0]; this
0x180003edf  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003ee4  mov     rdi, [rbp+160h+var_1E0]
0x180003ee8  test    rbx, rbx
0x180003eeb  jz      short loc_180003EFC
0x180003eed  mov     rcx, rbx; hKey
0x180003ef0  call    cs:__imp_RegCloseKey
0x180003ef7  nop     dword ptr [rax+rax+00h]
0x180003efc  test    rdi, rdi
0x180003eff  jz      short loc_180003F11
0x180003f01  mov     rcx, rdi; hKey
0x180003f04  call    cs:__imp_RegCloseKey
0x180003f0b  nop     dword ptr [rax+rax+00h]
0x180003f10  nop
0x180003f11  mov     rcx, [rsp+260h+var_1F8]
0x180003f16  test    rcx, rcx
0x180003f19  jz      short loc_180003F28
  ... truncated ...
```
