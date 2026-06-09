# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000eb5c`
- end: `0x18000f01c`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001128c`
- `0x1800134c0`

## callees

- `0x18000eb5c`
- `0x18000f208`
- `0x18000fd78`
- `0x1800181e0`
- `0x180019010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000ed0e`
- `msvcrt!wcscat_s` at `0x18000ed4a`
- `msvcrt!wcscat_s` at `0x18000ee7c`
- `msvcrt!wcscat_s` at `0x18000eeb8`
- `msvcrt!wcscat_s` at `0x18000ed0e`
- `msvcrt!wcscat_s` at `0x18000ed4a`
- `msvcrt!wcscat_s` at `0x18000ee7c`
- `msvcrt!wcscat_s` at `0x18000eeb8`
- `msvcrt!wcscpy_s` at `0x18000ecca`
- `msvcrt!wcscpy_s` at `0x18000ee40`
- `msvcrt!wcscpy_s` at `0x18000ecca`
- `msvcrt!wcscpy_s` at `0x18000ee40`
- `ADVAPI32!RegCloseKey` at `0x18000ee09`
- `ADVAPI32!RegCloseKey` at `0x18000ef1e`
- `ADVAPI32!RegCloseKey` at `0x18000ef75`
- `ADVAPI32!RegCloseKey` at `0x18000efa2`
- `ADVAPI32!RegCloseKey` at `0x18000efb0`
- `ADVAPI32!RegCloseKey` at `0x18000ee09`
- `ADVAPI32!RegCloseKey` at `0x18000ef1e`
- `ADVAPI32!RegCloseKey` at `0x18000ef75`
- `ADVAPI32!RegCloseKey` at `0x18000efa2`
- `ADVAPI32!RegCloseKey` at `0x18000efb0`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000edf9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000ef65`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000edf9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000ef65`
- `ADVAPI32!RegOpenKeyExW` at `0x18000edb2`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ef05`
- `ADVAPI32!RegOpenKeyExW` at `0x18000edb2`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ef05`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ec03`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ec03`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ecb2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ecb2`

## string_xrefs

- `0x18000ecb8`: `CLSID\`
- `0x18000ee2e`: `CLSID\`

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
0x18000eb5c  mov     [rsp-8+arg_10], rbx
0x18000eb61  mov     [rsp-8+arg_18], rsi
0x18000eb66  push    rbp
0x18000eb67  push    rdi
0x18000eb68  push    r12
0x18000eb6a  push    r14
0x18000eb6c  push    r15
0x18000eb6e  lea     rbp, [rsp-140h]
0x18000eb76  sub     rsp, 240h
0x18000eb7d  mov     rax, cs:__security_cookie
0x18000eb84  xor     rax, rsp
0x18000eb87  mov     [rbp+160h+var_30], rax
0x18000eb8e  mov     r14d, r8d
0x18000eb91  mov     rdi, rdx
0x18000eb94  mov     rbx, rcx
0x18000eb97  xor     r15d, r15d
0x18000eb9a  mov     [rsp+260h+var_1F8], r15
0x18000eb9f  xorps   xmm0, xmm0
0x18000eba2  movups  [rbp+160h+var_1C8], xmm0
0x18000eba6  test    rdx, rdx
0x18000eba9  jnz     short loc_18000EBB0
0x18000ebab  jmp     loc_18000EFCE
0x18000ebb0  mov     eax, cs:GUID_NULL.Data1
0x18000ebb6  cmp     [rcx], eax
0x18000ebb8  jnz     short loc_18000EBE0
0x18000ebba  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000ebc0  cmp     [rcx+4], eax
0x18000ebc3  jnz     short loc_18000EBE0
0x18000ebc5  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000ebcb  cmp     [rcx+8], eax
0x18000ebce  jnz     short loc_18000EBE0
0x18000ebd0  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000ebd6  cmp     [rcx+0Ch], eax
0x18000ebd9  jnz     short loc_18000EBE0
0x18000ebdb  jmp     loc_18000EFCE
0x18000ebe0  lea     rax, [rsp+260h+var_1F8]
0x18000ebe5  mov     [rsp+260h+ppv], rax; ppv
0x18000ebea  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000ebf1  mov     r12d, 1
0x18000ebf7  mov     r8d, r12d; dwClsContext
0x18000ebfa  xor     edx, edx; pUnkOuter
0x18000ebfc  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000ec03  call    cs:__imp_CoCreateInstance
0x18000ec09  test    eax, eax
0x18000ec0b  jns     loc_18000EC91
0x18000ec11  jmp     loc_18000EFB7
0x18000ec16  mov     rax, [rdi+8]
0x18000ec1a  movups  xmm0, xmmword ptr [rax]
0x18000ec1d  movdqu  [rbp+160h+var_1C8], xmm0
0x18000ec22  lea     r9, [rbp+160h+var_1C8]
0x18000ec26  mov     r8d, r12d
0x18000ec29  mov     rdx, rbx
0x18000ec2c  test    r14d, r14d
0x18000ec2f  jz      short loc_18000EC71
0x18000ec31  cmp     ecx, r12d
0x18000ec34  mov     rcx, [rsp+260h+var_1F8]
0x18000ec39  mov     rax, [rcx]
0x18000ec3c  jnz     short loc_18000EC44
0x18000ec3e  mov     rax, [rax+28h]
0x18000ec42  jmp     short loc_18000EC48
0x18000ec44  mov     rax, [rax+38h]
0x18000ec48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec4d  mov     esi, eax
0x18000ec4f  test    eax, eax
0x18000ec51  jns     short loc_18000EC8D
0x18000ec53  mov     rcx, [rsp+260h+var_1F8]
0x18000ec58  test    rcx, rcx
0x18000ec5b  jz      short loc_18000EC6A
0x18000ec5d  mov     rax, [rcx]
0x18000ec60  mov     rax, [rax+10h]
0x18000ec64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec69  nop
0x18000ec6a  mov     eax, esi
0x18000ec6c  jmp     loc_18000EFD0
0x18000ec71  cmp     ecx, r12d
0x18000ec74  mov     rcx, [rsp+260h+var_1F8]
0x18000ec79  mov     rax, [rcx]
0x18000ec7c  jnz     short loc_18000EC84
0x18000ec7e  mov     rax, [rax+30h]
0x18000ec82  jmp     short loc_18000EC88
0x18000ec84  mov     rax, [rax+40h]
0x18000ec88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec8d  add     rdi, 10h
0x18000ec91  mov     ecx, [rdi]
0x18000ec93  test    ecx, ecx
0x18000ec95  jnz     loc_18000EC16
0x18000ec9b  test    r14d, r14d
0x18000ec9e  jnz     loc_18000EFB7
0x18000eca4  lea     r8d, [rcx+40h]; cchMax
0x18000eca8  lea     rdx, [rbp+160h+sz]; lpsz
0x18000ecaf  mov     rcx, rbx; rguid
0x18000ecb2  call    cs:__imp_StringFromGUID2
0x18000ecb8  lea     r8, aClsid; "CLSID\\"
0x18000ecbf  mov     ebx, 80h
0x18000ecc4  mov     edx, ebx; SizeInWords
0x18000ecc6  lea     rcx, [rbp+160h+Destination]; Destination
0x18000ecca  call    cs:__imp_wcscpy_s
0x18000ecd0  lea     r14d, [rbx-74h]
0x18000ecd4  lea     r12d, [rbx-30h]
0x18000ecd8  test    eax, eax
0x18000ecda  jz      short loc_18000ED00
0x18000ecdc  cmp     eax, r14d
0x18000ecdf  jz      loc_18000EFFB
0x18000ece5  cmp     eax, 16h
0x18000ece8  jz      loc_18000F011
0x18000ecee  cmp     eax, 22h ; '"'
0x18000ecf1  jz      loc_18000F011
0x18000ecf7  cmp     eax, r12d
0x18000ecfa  jnz     loc_18000F006
0x18000ed00  lea     r8, [rbp+160h+sz]; Source
0x18000ed07  mov     rdx, rbx; SizeInWords
0x18000ed0a  lea     rcx, [rbp+160h+Destination]; Destination
0x18000ed0e  call    cs:__imp_wcscat_s
0x18000ed14  test    eax, eax
0x18000ed16  jz      short loc_18000ED3C
0x18000ed18  cmp     eax, r14d
0x18000ed1b  jz      loc_18000EFFB
0x18000ed21  cmp     eax, 16h
0x18000ed24  jz      loc_18000F011
0x18000ed2a  cmp     eax, 22h ; '"'
0x18000ed2d  jz      loc_18000F011
0x18000ed33  cmp     eax, r12d
0x18000ed36  jnz     loc_18000F006
0x18000ed3c  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000ed43  mov     rdx, rbx; SizeInWords
0x18000ed46  lea     rcx, [rbp+160h+Destination]; Destination
0x18000ed4a  call    cs:__imp_wcscat_s
0x18000ed50  test    eax, eax
0x18000ed52  jz      short loc_18000ED78
0x18000ed54  cmp     eax, r14d
0x18000ed57  jz      loc_18000EFFB
0x18000ed5d  cmp     eax, 16h
0x18000ed60  jz      loc_18000F011
0x18000ed66  cmp     eax, 22h ; '"'
0x18000ed69  jz      loc_18000F011
0x18000ed6f  cmp     eax, r12d
0x18000ed72  jnz     loc_18000F006
0x18000ed78  mov     rdi, 0FFFFFFFF80000000h
0x18000ed7f  mov     [rbp+160h+var_1E0], rdi
0x18000ed83  mov     [rbp+160h+var_1D8], r15
0x18000ed87  mov     [rbp+160h+var_1D0], r15
0x18000ed8b  mov     rbx, r15
0x18000ed8e  mov     [rsp+260h+cSubKeys], r15d
0x18000ed93  mov     [rsp+260h+phkResult], r15
0x18000ed98  lea     rax, [rsp+260h+phkResult]
0x18000ed9d  mov     [rsp+260h+ppv], rax; phkResult
0x18000eda2  mov     r9d, 20019h; samDesired
0x18000eda8  xor     r8d, r8d; ulOptions
0x18000edab  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x18000edaf  mov     rcx, rdi; hKey
0x18000edb2  call    cs:__imp_RegOpenKeyExW
0x18000edb8  test    eax, eax
0x18000edba  jnz     short loc_18000EE2E
0x18000edbc  mov     rbx, [rsp+260h+phkResult]
0x18000edc1  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000edc6  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000edcb  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000edd0  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000edd5  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000edda  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000eddf  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000ede4  lea     rax, [rsp+260h+cSubKeys]
0x18000ede9  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000edee  xor     r9d, r9d; lpReserved
0x18000edf1  xor     r8d, r8d; lpcchClass
0x18000edf4  xor     edx, edx; lpClass
0x18000edf6  mov     rcx, rbx; hKey
0x18000edf9  call    cs:__imp_RegQueryInfoKeyW
0x18000edff  mov     esi, eax
0x18000ee01  test    rbx, rbx
0x18000ee04  jz      short loc_18000EE12
0x18000ee06  mov     rcx, rbx; hKey
0x18000ee09  call    cs:__imp_RegCloseKey
0x18000ee0f  mov     rbx, r15
0x18000ee12  test    esi, esi
0x18000ee14  jnz     short loc_18000EE2E
0x18000ee16  cmp     [rsp+260h+cSubKeys], r15d
0x18000ee1b  jnz     short loc_18000EE2E
0x18000ee1d  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x18000ee21  lea     rcx, [rbp+160h+var_1E0]; this
0x18000ee25  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000ee2a  mov     rdi, [rbp+160h+var_1E0]
0x18000ee2e  lea     r8, aClsid; "CLSID\\"
0x18000ee35  mov     esi, 80h
0x18000ee3a  mov     edx, esi; SizeInWords
0x18000ee3c  lea     rcx, [rbp+160h+Destination]; Destination
0x18000ee40  call    cs:__imp_wcscpy_s
0x18000ee46  test    eax, eax
0x18000ee48  jz      short loc_18000EE6E
0x18000ee4a  cmp     eax, r14d
0x18000ee4d  jz      loc_18000EFFB
0x18000ee53  cmp     eax, 16h
0x18000ee56  jz      loc_18000F011
0x18000ee5c  cmp     eax, 22h ; '"'
0x18000ee5f  jz      loc_18000F011
0x18000ee65  cmp     eax, r12d
0x18000ee68  jnz     loc_18000F006
0x18000ee6e  lea     r8, [rbp+160h+sz]; Source
0x18000ee75  mov     rdx, rsi; SizeInWords
0x18000ee78  lea     rcx, [rbp+160h+Destination]; Destination
0x18000ee7c  call    cs:__imp_wcscat_s
0x18000ee82  test    eax, eax
0x18000ee84  jz      short loc_18000EEAA
0x18000ee86  cmp     eax, r14d
0x18000ee89  jz      loc_18000EFFB
0x18000ee8f  cmp     eax, 16h
0x18000ee92  jz      loc_18000F011
0x18000ee98  cmp     eax, 22h ; '"'
0x18000ee9b  jz      loc_18000F011
0x18000eea1  cmp     eax, r12d
0x18000eea4  jnz     loc_18000F006
0x18000eeaa  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000eeb1  mov     rdx, rsi; SizeInWords
0x18000eeb4  lea     rcx, [rbp+160h+Destination]; Destination
0x18000eeb8  call    cs:__imp_wcscat_s
0x18000eebe  test    eax, eax
0x18000eec0  jz      short loc_18000EEE6
0x18000eec2  cmp     eax, r14d
0x18000eec5  jz      loc_18000EFFB
0x18000eecb  cmp     eax, 16h
0x18000eece  jz      loc_18000F011
0x18000eed4  cmp     eax, 22h ; '"'
0x18000eed7  jz      loc_18000F011
0x18000eedd  cmp     eax, r12d
0x18000eee0  jnz     loc_18000F006
0x18000eee6  mov     [rsp+260h+hKey], r15
0x18000eeeb  lea     rax, [rsp+260h+hKey]
0x18000eef0  mov     [rsp+260h+ppv], rax; phkResult
0x18000eef5  mov     r9d, 20019h; samDesired
0x18000eefb  xor     r8d, r8d; ulOptions
0x18000eefe  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x18000ef02  mov     rcx, rdi; hKey
0x18000ef05  call    cs:__imp_RegOpenKeyExW
0x18000ef0b  test    eax, eax
0x18000ef0d  jnz     loc_18000EF9A
0x18000ef13  mov     eax, r15d
0x18000ef16  test    rbx, rbx
0x18000ef19  jz      short loc_18000EF24
0x18000ef1b  mov     rcx, rbx; hKey
0x18000ef1e  call    cs:__imp_RegCloseKey
0x18000ef24  mov     rbx, [rsp+260h+hKey]
0x18000ef29  test    eax, eax
0x18000ef2b  jnz     short loc_18000EF9A
0x18000ef2d  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000ef32  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000ef37  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000ef3c  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000ef41  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000ef46  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000ef4b  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000ef50  lea     rax, [rsp+260h+cSubKeys]
0x18000ef55  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000ef5a  xor     r9d, r9d; lpReserved
0x18000ef5d  xor     r8d, r8d; lpcchClass
0x18000ef60  xor     edx, edx; lpClass
0x18000ef62  mov     rcx, rbx; hKey
0x18000ef65  call    cs:__imp_RegQueryInfoKeyW
0x18000ef6b  mov     esi, eax
0x18000ef6d  test    rbx, rbx
0x18000ef70  jz      short loc_18000EF7E
0x18000ef72  mov     rcx, rbx; hKey
0x18000ef75  call    cs:__imp_RegCloseKey
0x18000ef7b  mov     rbx, r15
0x18000ef7e  test    esi, esi
0x18000ef80  jnz     short loc_18000EFA8
0x18000ef82  cmp     [rsp+260h+cSubKeys], r15d
0x18000ef87  jnz     short loc_18000EF9A
0x18000ef89  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x18000ef8d  lea     rcx, [rbp+160h+var_1E0]; this
0x18000ef91  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000ef96  mov     rdi, [rbp+160h+var_1E0]
0x18000ef9a  test    rbx, rbx
0x18000ef9d  jz      short loc_18000EFA8
0x18000ef9f  mov     rcx, rbx; hKey
0x18000efa2  call    cs:__imp_RegCloseKey
0x18000efa8  test    rdi, rdi
0x18000efab  jz      short loc_18000EFB7
0x18000efad  mov     rcx, rdi; hKey
0x18000efb0  call    cs:__imp_RegCloseKey
0x18000efb6  nop
0x18000efb7  mov     rcx, [rsp+260h+var_1F8]
0x18000efbc  test    rcx, rcx
0x18000efbf  jz      short loc_18000EFCE
0x18000efc1  mov     rax, [rcx]
0x18000efc4  mov     rax, [rax+10h]
0x18000efc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efcd  nop
0x18000efce  xor     eax, eax
0x18000efd0  mov     rcx, [rbp+160h+var_30]
0x18000efd7  xor     rcx, rsp; StackCookie
0x18000efda  call    __security_check_cookie
0x18000efdf  lea     r11, [rsp+260h+var_20]
0x18000efe7  mov     rbx, [r11+40h]
0x18000efeb  mov     rsi, [r11+48h]
0x18000efef  mov     rsp, r11
0x18000eff2  pop     r15
0x18000eff4  pop     r14
0x18000eff6  pop     r12
0x18000eff8  pop     rdi
0x18000eff9  pop     rbp
  ... truncated ...
```
