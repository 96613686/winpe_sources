# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000399c`
- end: `0x180003e5c`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800054e4`
- `0x180005ae0`

## callees

- `0x18000399c`
- `0x180004048`
- `0x180004164`
- `0x180011340`
- `0x180012010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180003b4e`
- `msvcrt!wcscat_s` at `0x180003b8a`
- `msvcrt!wcscat_s` at `0x180003cbc`
- `msvcrt!wcscat_s` at `0x180003cf8`
- `msvcrt!wcscat_s` at `0x180003b4e`
- `msvcrt!wcscat_s` at `0x180003b8a`
- `msvcrt!wcscat_s` at `0x180003cbc`
- `msvcrt!wcscat_s` at `0x180003cf8`
- `msvcrt!wcscpy_s` at `0x180003b0a`
- `msvcrt!wcscpy_s` at `0x180003c80`
- `msvcrt!wcscpy_s` at `0x180003b0a`
- `msvcrt!wcscpy_s` at `0x180003c80`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003af2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003af2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003a43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003a43`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003c39`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003da5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003c39`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003da5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003d5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003db5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003de2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003df0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003d5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003db5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003de2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003df0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003bf2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003d45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003bf2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003d45`

## string_xrefs

- `0x180003af8`: `CLSID\`
- `0x180003c6e`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000399c  mov     [rsp-8+arg_10], rbx
0x1800039a1  mov     [rsp-8+arg_18], rsi
0x1800039a6  push    rbp
0x1800039a7  push    rdi
0x1800039a8  push    r12
0x1800039aa  push    r14
0x1800039ac  push    r15
0x1800039ae  lea     rbp, [rsp-140h]
0x1800039b6  sub     rsp, 240h
0x1800039bd  mov     rax, cs:__security_cookie
0x1800039c4  xor     rax, rsp
0x1800039c7  mov     [rbp+160h+var_30], rax
0x1800039ce  mov     r14d, r8d
0x1800039d1  mov     rdi, rdx
0x1800039d4  mov     rbx, rcx
0x1800039d7  xor     r15d, r15d
0x1800039da  mov     [rsp+260h+var_1F8], r15
0x1800039df  xorps   xmm0, xmm0
0x1800039e2  movups  [rbp+160h+var_1C8], xmm0
0x1800039e6  test    rdx, rdx
0x1800039e9  jnz     short loc_1800039F0
0x1800039eb  jmp     loc_180003E0E
0x1800039f0  mov     eax, cs:GUID_NULL.Data1
0x1800039f6  cmp     [rcx], eax
0x1800039f8  jnz     short loc_180003A20
0x1800039fa  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180003a00  cmp     [rcx+4], eax
0x180003a03  jnz     short loc_180003A20
0x180003a05  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180003a0b  cmp     [rcx+8], eax
0x180003a0e  jnz     short loc_180003A20
0x180003a10  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180003a16  cmp     [rcx+0Ch], eax
0x180003a19  jnz     short loc_180003A20
0x180003a1b  jmp     loc_180003E0E
0x180003a20  lea     rax, [rsp+260h+var_1F8]
0x180003a25  mov     [rsp+260h+ppv], rax; ppv
0x180003a2a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180003a31  mov     r12d, 1
0x180003a37  mov     r8d, r12d; dwClsContext
0x180003a3a  xor     edx, edx; pUnkOuter
0x180003a3c  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180003a43  call    cs:__imp_CoCreateInstance
0x180003a49  test    eax, eax
0x180003a4b  jns     loc_180003AD1
0x180003a51  jmp     loc_180003DF7
0x180003a56  mov     rax, [rdi+8]
0x180003a5a  movups  xmm0, xmmword ptr [rax]
0x180003a5d  movdqu  [rbp+160h+var_1C8], xmm0
0x180003a62  lea     r9, [rbp+160h+var_1C8]
0x180003a66  mov     r8d, r12d
0x180003a69  mov     rdx, rbx
0x180003a6c  test    r14d, r14d
0x180003a6f  jz      short loc_180003AB1
0x180003a71  cmp     ecx, r12d
0x180003a74  mov     rcx, [rsp+260h+var_1F8]
0x180003a79  mov     rax, [rcx]
0x180003a7c  jnz     short loc_180003A84
0x180003a7e  mov     rax, [rax+28h]
0x180003a82  jmp     short loc_180003A88
0x180003a84  mov     rax, [rax+38h]
0x180003a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a8d  mov     esi, eax
0x180003a8f  test    eax, eax
0x180003a91  jns     short loc_180003ACD
0x180003a93  mov     rcx, [rsp+260h+var_1F8]
0x180003a98  test    rcx, rcx
0x180003a9b  jz      short loc_180003AAA
0x180003a9d  mov     rax, [rcx]
0x180003aa0  mov     rax, [rax+10h]
0x180003aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa9  nop
0x180003aaa  mov     eax, esi
0x180003aac  jmp     loc_180003E10
0x180003ab1  cmp     ecx, r12d
0x180003ab4  mov     rcx, [rsp+260h+var_1F8]
0x180003ab9  mov     rax, [rcx]
0x180003abc  jnz     short loc_180003AC4
0x180003abe  mov     rax, [rax+30h]
0x180003ac2  jmp     short loc_180003AC8
0x180003ac4  mov     rax, [rax+40h]
0x180003ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003acd  add     rdi, 10h
0x180003ad1  mov     ecx, [rdi]
0x180003ad3  test    ecx, ecx
0x180003ad5  jnz     loc_180003A56
0x180003adb  test    r14d, r14d
0x180003ade  jnz     loc_180003DF7
0x180003ae4  lea     r8d, [rcx+40h]; cchMax
0x180003ae8  lea     rdx, [rbp+160h+sz]; lpsz
0x180003aef  mov     rcx, rbx; rguid
0x180003af2  call    cs:__imp_StringFromGUID2
0x180003af8  lea     r8, aClsid; "CLSID\\"
0x180003aff  mov     ebx, 80h
0x180003b04  mov     edx, ebx; SizeInWords
0x180003b06  lea     rcx, [rbp+160h+Destination]; Destination
0x180003b0a  call    cs:__imp_wcscpy_s
0x180003b10  lea     r14d, [rbx-74h]
0x180003b14  lea     r12d, [rbx-30h]
0x180003b18  test    eax, eax
0x180003b1a  jz      short loc_180003B40
0x180003b1c  cmp     eax, r14d
0x180003b1f  jz      loc_180003E3B
0x180003b25  cmp     eax, 16h
0x180003b28  jz      loc_180003E51
0x180003b2e  cmp     eax, 22h ; '"'
0x180003b31  jz      loc_180003E51
0x180003b37  cmp     eax, r12d
0x180003b3a  jnz     loc_180003E46
0x180003b40  lea     r8, [rbp+160h+sz]; Source
0x180003b47  mov     rdx, rbx; SizeInWords
0x180003b4a  lea     rcx, [rbp+160h+Destination]; Destination
0x180003b4e  call    cs:__imp_wcscat_s
0x180003b54  test    eax, eax
0x180003b56  jz      short loc_180003B7C
0x180003b58  cmp     eax, r14d
0x180003b5b  jz      loc_180003E3B
0x180003b61  cmp     eax, 16h
0x180003b64  jz      loc_180003E51
0x180003b6a  cmp     eax, 22h ; '"'
0x180003b6d  jz      loc_180003E51
0x180003b73  cmp     eax, r12d
0x180003b76  jnz     loc_180003E46
0x180003b7c  lea     r8, aRequiredCatego; "\\Required Categories"
0x180003b83  mov     rdx, rbx; SizeInWords
0x180003b86  lea     rcx, [rbp+160h+Destination]; Destination
0x180003b8a  call    cs:__imp_wcscat_s
0x180003b90  test    eax, eax
0x180003b92  jz      short loc_180003BB8
0x180003b94  cmp     eax, r14d
0x180003b97  jz      loc_180003E3B
0x180003b9d  cmp     eax, 16h
0x180003ba0  jz      loc_180003E51
0x180003ba6  cmp     eax, 22h ; '"'
0x180003ba9  jz      loc_180003E51
0x180003baf  cmp     eax, r12d
0x180003bb2  jnz     loc_180003E46
0x180003bb8  mov     rdi, 0FFFFFFFF80000000h
0x180003bbf  mov     [rbp+160h+var_1E0], rdi
0x180003bc3  mov     [rbp+160h+var_1D8], r15
0x180003bc7  mov     [rbp+160h+var_1D0], r15
0x180003bcb  mov     rbx, r15
0x180003bce  mov     [rsp+260h+cSubKeys], r15d
0x180003bd3  mov     [rsp+260h+phkResult], r15
0x180003bd8  lea     rax, [rsp+260h+phkResult]
0x180003bdd  mov     [rsp+260h+ppv], rax; phkResult
0x180003be2  mov     r9d, 20019h; samDesired
0x180003be8  xor     r8d, r8d; ulOptions
0x180003beb  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180003bef  mov     rcx, rdi; hKey
0x180003bf2  call    cs:__imp_RegOpenKeyExW
0x180003bf8  test    eax, eax
0x180003bfa  jnz     short loc_180003C6E
0x180003bfc  mov     rbx, [rsp+260h+phkResult]
0x180003c01  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003c06  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003c0b  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003c10  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003c15  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180003c1a  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003c1f  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003c24  lea     rax, [rsp+260h+cSubKeys]
0x180003c29  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180003c2e  xor     r9d, r9d; lpReserved
0x180003c31  xor     r8d, r8d; lpcchClass
0x180003c34  xor     edx, edx; lpClass
0x180003c36  mov     rcx, rbx; hKey
0x180003c39  call    cs:__imp_RegQueryInfoKeyW
0x180003c3f  mov     esi, eax
0x180003c41  test    rbx, rbx
0x180003c44  jz      short loc_180003C52
0x180003c46  mov     rcx, rbx; hKey
0x180003c49  call    cs:__imp_RegCloseKey
0x180003c4f  mov     rbx, r15
0x180003c52  test    esi, esi
0x180003c54  jnz     short loc_180003C6E
0x180003c56  cmp     [rsp+260h+cSubKeys], r15d
0x180003c5b  jnz     short loc_180003C6E
0x180003c5d  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180003c61  lea     rcx, [rbp+160h+var_1E0]; this
0x180003c65  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003c6a  mov     rdi, [rbp+160h+var_1E0]
0x180003c6e  lea     r8, aClsid; "CLSID\\"
0x180003c75  mov     esi, 80h
0x180003c7a  mov     edx, esi; SizeInWords
0x180003c7c  lea     rcx, [rbp+160h+Destination]; Destination
0x180003c80  call    cs:__imp_wcscpy_s
0x180003c86  test    eax, eax
0x180003c88  jz      short loc_180003CAE
0x180003c8a  cmp     eax, r14d
0x180003c8d  jz      loc_180003E3B
0x180003c93  cmp     eax, 16h
0x180003c96  jz      loc_180003E51
0x180003c9c  cmp     eax, 22h ; '"'
0x180003c9f  jz      loc_180003E51
0x180003ca5  cmp     eax, r12d
0x180003ca8  jnz     loc_180003E46
0x180003cae  lea     r8, [rbp+160h+sz]; Source
0x180003cb5  mov     rdx, rsi; SizeInWords
0x180003cb8  lea     rcx, [rbp+160h+Destination]; Destination
0x180003cbc  call    cs:__imp_wcscat_s
0x180003cc2  test    eax, eax
0x180003cc4  jz      short loc_180003CEA
0x180003cc6  cmp     eax, r14d
0x180003cc9  jz      loc_180003E3B
0x180003ccf  cmp     eax, 16h
0x180003cd2  jz      loc_180003E51
0x180003cd8  cmp     eax, 22h ; '"'
0x180003cdb  jz      loc_180003E51
0x180003ce1  cmp     eax, r12d
0x180003ce4  jnz     loc_180003E46
0x180003cea  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180003cf1  mov     rdx, rsi; SizeInWords
0x180003cf4  lea     rcx, [rbp+160h+Destination]; Destination
0x180003cf8  call    cs:__imp_wcscat_s
0x180003cfe  test    eax, eax
0x180003d00  jz      short loc_180003D26
0x180003d02  cmp     eax, r14d
0x180003d05  jz      loc_180003E3B
0x180003d0b  cmp     eax, 16h
0x180003d0e  jz      loc_180003E51
0x180003d14  cmp     eax, 22h ; '"'
0x180003d17  jz      loc_180003E51
0x180003d1d  cmp     eax, r12d
0x180003d20  jnz     loc_180003E46
0x180003d26  mov     [rsp+260h+hKey], r15
0x180003d2b  lea     rax, [rsp+260h+hKey]
0x180003d30  mov     [rsp+260h+ppv], rax; phkResult
0x180003d35  mov     r9d, 20019h; samDesired
0x180003d3b  xor     r8d, r8d; ulOptions
0x180003d3e  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180003d42  mov     rcx, rdi; hKey
0x180003d45  call    cs:__imp_RegOpenKeyExW
0x180003d4b  test    eax, eax
0x180003d4d  jnz     loc_180003DDA
0x180003d53  mov     eax, r15d
0x180003d56  test    rbx, rbx
0x180003d59  jz      short loc_180003D64
0x180003d5b  mov     rcx, rbx; hKey
0x180003d5e  call    cs:__imp_RegCloseKey
0x180003d64  mov     rbx, [rsp+260h+hKey]
0x180003d69  test    eax, eax
0x180003d6b  jnz     short loc_180003DDA
0x180003d6d  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003d72  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003d77  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003d7c  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003d81  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180003d86  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003d8b  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003d90  lea     rax, [rsp+260h+cSubKeys]
0x180003d95  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180003d9a  xor     r9d, r9d; lpReserved
0x180003d9d  xor     r8d, r8d; lpcchClass
0x180003da0  xor     edx, edx; lpClass
0x180003da2  mov     rcx, rbx; hKey
0x180003da5  call    cs:__imp_RegQueryInfoKeyW
0x180003dab  mov     esi, eax
0x180003dad  test    rbx, rbx
0x180003db0  jz      short loc_180003DBE
0x180003db2  mov     rcx, rbx; hKey
0x180003db5  call    cs:__imp_RegCloseKey
0x180003dbb  mov     rbx, r15
0x180003dbe  test    esi, esi
0x180003dc0  jnz     short loc_180003DE8
0x180003dc2  cmp     [rsp+260h+cSubKeys], r15d
0x180003dc7  jnz     short loc_180003DDA
0x180003dc9  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180003dcd  lea     rcx, [rbp+160h+var_1E0]; this
0x180003dd1  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003dd6  mov     rdi, [rbp+160h+var_1E0]
0x180003dda  test    rbx, rbx
0x180003ddd  jz      short loc_180003DE8
0x180003ddf  mov     rcx, rbx; hKey
0x180003de2  call    cs:__imp_RegCloseKey
0x180003de8  test    rdi, rdi
0x180003deb  jz      short loc_180003DF7
0x180003ded  mov     rcx, rdi; hKey
0x180003df0  call    cs:__imp_RegCloseKey
0x180003df6  nop
0x180003df7  mov     rcx, [rsp+260h+var_1F8]
0x180003dfc  test    rcx, rcx
0x180003dff  jz      short loc_180003E0E
0x180003e01  mov     rax, [rcx]
0x180003e04  mov     rax, [rax+10h]
0x180003e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0d  nop
0x180003e0e  xor     eax, eax
0x180003e10  mov     rcx, [rbp+160h+var_30]
0x180003e17  xor     rcx, rsp; StackCookie
0x180003e1a  call    __security_check_cookie
0x180003e1f  lea     r11, [rsp+260h+var_20]
0x180003e27  mov     rbx, [r11+40h]
0x180003e2b  mov     rsi, [r11+48h]
0x180003e2f  mov     rsp, r11
0x180003e32  pop     r15
0x180003e34  pop     r14
0x180003e36  pop     r12
0x180003e38  pop     rdi
0x180003e39  pop     rbp
  ... truncated ...
```
