# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000e5a0`
- end: `0x18000ea60`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012cd4`
- `0x180013fc0`

## callees

- `0x1800024e0`
- `0x18000e5a0`
- `0x18000ec4c`
- `0x18000faf8`
- `0x18005c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e752`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e78e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e8c0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e8fc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e752`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e78e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e8c0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000e8fc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000e70e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000e884`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000e70e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000e884`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e647`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e647`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e6f6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e6f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e7f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e949`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e7f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e949`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e84d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e962`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e9b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e9e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e9f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e84d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e962`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e9b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e9e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e9f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000e83d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000e9a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000e83d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000e9a9`

## string_xrefs

- `0x18000e6fc`: `CLSID\`
- `0x18000e872`: `CLSID\`

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
  int v12; // eax
  int v13; // eax
  int v14; // eax
  HKEY v15; // rdi
  HKEY v16; // rbx
  LSTATUS v17; // esi
  int v18; // eax
  int v19; // eax
  int v20; // eax
  HKEY v21; // rbx
  LSTATUS v22; // esi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v27[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+98h] [rbp-68h] BYREF
  WCHAR SubKey[128]; // [rsp+B0h] [rbp-50h] BYREF
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
      v12 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      if ( v12 )
      {
        if ( v12 == 12 )
          goto LABEL_69;
        if ( v12 == 22 || v12 == 34 )
          goto LABEL_71;
        if ( v12 != 80 )
          goto LABEL_70;
      }
      v13 = _o_wcscat_s(SubKey, 128, sz);
      if ( v13 )
      {
        if ( v13 == 12 )
          goto LABEL_69;
        if ( v13 == 22 || v13 == 34 )
          goto LABEL_71;
        if ( v13 != 80 )
          goto LABEL_70;
      }
      v14 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
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
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult) )
      {
        v16 = phkResult;
        v17 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        if ( v16 )
          RegCloseKey(v16);
        if ( !v17 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, SubKey);
          v15 = (HKEY)v27[0];
        }
      }
      v18 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      if ( v18 )
      {
        if ( v18 == 12 )
          goto LABEL_69;
        if ( v18 == 22 || v18 == 34 )
          goto LABEL_71;
        if ( v18 != 80 )
          goto LABEL_70;
      }
      v19 = _o_wcscat_s(SubKey, 128, sz);
      if ( v19 )
      {
        if ( v19 == 12 )
          goto LABEL_69;
        if ( v19 == 22 || v19 == 34 )
          goto LABEL_71;
        if ( v19 != 80 )
          goto LABEL_70;
      }
      v20 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      if ( !v20 )
      {
LABEL_58:
        hKey = 0;
        if ( !RegOpenKeyExW(v15, SubKey, 0, 0x20019u, &hKey) )
        {
          v21 = hKey;
          v22 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v21 )
            RegCloseKey(v21);
          if ( !v22 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, SubKey);
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
0x18000e5a0  mov     [rsp-8+arg_10], rbx
0x18000e5a5  mov     [rsp-8+arg_18], rsi
0x18000e5aa  push    rbp
0x18000e5ab  push    rdi
0x18000e5ac  push    r12
0x18000e5ae  push    r14
0x18000e5b0  push    r15
0x18000e5b2  lea     rbp, [rsp-140h]
0x18000e5ba  sub     rsp, 240h
0x18000e5c1  mov     rax, cs:__security_cookie
0x18000e5c8  xor     rax, rsp
0x18000e5cb  mov     [rbp+160h+var_30], rax
0x18000e5d2  mov     r14d, r8d
0x18000e5d5  mov     rdi, rdx
0x18000e5d8  mov     rbx, rcx
0x18000e5db  xor     r15d, r15d
0x18000e5de  mov     [rsp+260h+var_1F8], r15
0x18000e5e3  xorps   xmm0, xmm0
0x18000e5e6  movups  [rbp+160h+var_1C8], xmm0
0x18000e5ea  test    rdx, rdx
0x18000e5ed  jnz     short loc_18000E5F4
0x18000e5ef  jmp     loc_18000EA12
0x18000e5f4  mov     eax, cs:GUID_NULL.Data1
0x18000e5fa  cmp     [rcx], eax
0x18000e5fc  jnz     short loc_18000E624
0x18000e5fe  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000e604  cmp     [rcx+4], eax
0x18000e607  jnz     short loc_18000E624
0x18000e609  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000e60f  cmp     [rcx+8], eax
0x18000e612  jnz     short loc_18000E624
0x18000e614  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000e61a  cmp     [rcx+0Ch], eax
0x18000e61d  jnz     short loc_18000E624
0x18000e61f  jmp     loc_18000EA12
0x18000e624  lea     rax, [rsp+260h+var_1F8]
0x18000e629  mov     [rsp+260h+ppv], rax; ppv
0x18000e62e  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000e635  mov     r12d, 1
0x18000e63b  mov     r8d, r12d; dwClsContext
0x18000e63e  xor     edx, edx; pUnkOuter
0x18000e640  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000e647  call    cs:__imp_CoCreateInstance
0x18000e64d  test    eax, eax
0x18000e64f  jns     loc_18000E6D5
0x18000e655  jmp     loc_18000E9FB
0x18000e65a  mov     rax, [rdi+8]
0x18000e65e  movups  xmm0, xmmword ptr [rax]
0x18000e661  movdqu  [rbp+160h+var_1C8], xmm0
0x18000e666  lea     r9, [rbp+160h+var_1C8]
0x18000e66a  mov     r8d, r12d
0x18000e66d  mov     rdx, rbx
0x18000e670  test    r14d, r14d
0x18000e673  jz      short loc_18000E6B5
0x18000e675  cmp     ecx, r12d
0x18000e678  mov     rcx, [rsp+260h+var_1F8]
0x18000e67d  mov     rax, [rcx]
0x18000e680  jnz     short loc_18000E688
0x18000e682  mov     rax, [rax+28h]
0x18000e686  jmp     short loc_18000E68C
0x18000e688  mov     rax, [rax+38h]
0x18000e68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e691  mov     esi, eax
0x18000e693  test    eax, eax
0x18000e695  jns     short loc_18000E6D1
0x18000e697  mov     rcx, [rsp+260h+var_1F8]
0x18000e69c  test    rcx, rcx
0x18000e69f  jz      short loc_18000E6AE
0x18000e6a1  mov     rax, [rcx]
0x18000e6a4  mov     rax, [rax+10h]
0x18000e6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ad  nop
0x18000e6ae  mov     eax, esi
0x18000e6b0  jmp     loc_18000EA14
0x18000e6b5  cmp     ecx, r12d
0x18000e6b8  mov     rcx, [rsp+260h+var_1F8]
0x18000e6bd  mov     rax, [rcx]
0x18000e6c0  jnz     short loc_18000E6C8
0x18000e6c2  mov     rax, [rax+30h]
0x18000e6c6  jmp     short loc_18000E6CC
0x18000e6c8  mov     rax, [rax+40h]
0x18000e6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6d1  add     rdi, 10h
0x18000e6d5  mov     ecx, [rdi]
0x18000e6d7  test    ecx, ecx
0x18000e6d9  jnz     loc_18000E65A
0x18000e6df  test    r14d, r14d
0x18000e6e2  jnz     loc_18000E9FB
0x18000e6e8  lea     r8d, [rcx+40h]; cchMax
0x18000e6ec  lea     rdx, [rbp+160h+sz]; lpsz
0x18000e6f3  mov     rcx, rbx; rguid
0x18000e6f6  call    cs:__imp_StringFromGUID2
0x18000e6fc  lea     r8, aClsid; "CLSID\\"
0x18000e703  mov     ebx, 80h
0x18000e708  mov     edx, ebx
0x18000e70a  lea     rcx, [rbp+160h+SubKey]
0x18000e70e  call    cs:__imp__o_wcscpy_s
0x18000e714  lea     r14d, [rbx-74h]
0x18000e718  lea     r12d, [rbx-30h]
0x18000e71c  test    eax, eax
0x18000e71e  jz      short loc_18000E744
0x18000e720  cmp     eax, r14d
0x18000e723  jz      loc_18000EA3F
0x18000e729  cmp     eax, 16h
0x18000e72c  jz      loc_18000EA55
0x18000e732  cmp     eax, 22h ; '"'
0x18000e735  jz      loc_18000EA55
0x18000e73b  cmp     eax, r12d
0x18000e73e  jnz     loc_18000EA4A
0x18000e744  lea     r8, [rbp+160h+sz]
0x18000e74b  mov     rdx, rbx
0x18000e74e  lea     rcx, [rbp+160h+SubKey]
0x18000e752  call    cs:__imp__o_wcscat_s
0x18000e758  test    eax, eax
0x18000e75a  jz      short loc_18000E780
0x18000e75c  cmp     eax, r14d
0x18000e75f  jz      loc_18000EA3F
0x18000e765  cmp     eax, 16h
0x18000e768  jz      loc_18000EA55
0x18000e76e  cmp     eax, 22h ; '"'
0x18000e771  jz      loc_18000EA55
0x18000e777  cmp     eax, r12d
0x18000e77a  jnz     loc_18000EA4A
0x18000e780  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000e787  mov     rdx, rbx
0x18000e78a  lea     rcx, [rbp+160h+SubKey]
0x18000e78e  call    cs:__imp__o_wcscat_s
0x18000e794  test    eax, eax
0x18000e796  jz      short loc_18000E7BC
0x18000e798  cmp     eax, r14d
0x18000e79b  jz      loc_18000EA3F
0x18000e7a1  cmp     eax, 16h
0x18000e7a4  jz      loc_18000EA55
0x18000e7aa  cmp     eax, 22h ; '"'
0x18000e7ad  jz      loc_18000EA55
0x18000e7b3  cmp     eax, r12d
0x18000e7b6  jnz     loc_18000EA4A
0x18000e7bc  mov     rdi, 0FFFFFFFF80000000h
0x18000e7c3  mov     [rbp+160h+var_1E0], rdi
0x18000e7c7  mov     [rbp+160h+var_1D8], r15
0x18000e7cb  mov     [rbp+160h+var_1D0], r15
0x18000e7cf  mov     rbx, r15
0x18000e7d2  mov     [rsp+260h+cSubKeys], r15d
0x18000e7d7  mov     [rsp+260h+phkResult], r15
0x18000e7dc  lea     rax, [rsp+260h+phkResult]
0x18000e7e1  mov     [rsp+260h+ppv], rax; phkResult
0x18000e7e6  mov     r9d, 20019h; samDesired
0x18000e7ec  xor     r8d, r8d; ulOptions
0x18000e7ef  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000e7f3  mov     rcx, rdi; hKey
0x18000e7f6  call    cs:__imp_RegOpenKeyExW
0x18000e7fc  test    eax, eax
0x18000e7fe  jnz     short loc_18000E872
0x18000e800  mov     rbx, [rsp+260h+phkResult]
0x18000e805  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000e80a  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000e80f  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000e814  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000e819  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000e81e  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000e823  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000e828  lea     rax, [rsp+260h+cSubKeys]
0x18000e82d  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000e832  xor     r9d, r9d; lpReserved
0x18000e835  xor     r8d, r8d; lpcchClass
0x18000e838  xor     edx, edx; lpClass
0x18000e83a  mov     rcx, rbx; hKey
0x18000e83d  call    cs:__imp_RegQueryInfoKeyW
0x18000e843  mov     esi, eax
0x18000e845  test    rbx, rbx
0x18000e848  jz      short loc_18000E856
0x18000e84a  mov     rcx, rbx; hKey
0x18000e84d  call    cs:__imp_RegCloseKey
0x18000e853  mov     rbx, r15
0x18000e856  test    esi, esi
0x18000e858  jnz     short loc_18000E872
0x18000e85a  cmp     [rsp+260h+cSubKeys], r15d
0x18000e85f  jnz     short loc_18000E872
0x18000e861  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000e865  lea     rcx, [rbp+160h+var_1E0]; this
0x18000e869  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000e86e  mov     rdi, [rbp+160h+var_1E0]
0x18000e872  lea     r8, aClsid; "CLSID\\"
0x18000e879  mov     esi, 80h
0x18000e87e  mov     edx, esi
0x18000e880  lea     rcx, [rbp+160h+SubKey]
0x18000e884  call    cs:__imp__o_wcscpy_s
0x18000e88a  test    eax, eax
0x18000e88c  jz      short loc_18000E8B2
0x18000e88e  cmp     eax, r14d
0x18000e891  jz      loc_18000EA3F
0x18000e897  cmp     eax, 16h
0x18000e89a  jz      loc_18000EA55
0x18000e8a0  cmp     eax, 22h ; '"'
0x18000e8a3  jz      loc_18000EA55
0x18000e8a9  cmp     eax, r12d
0x18000e8ac  jnz     loc_18000EA4A
0x18000e8b2  lea     r8, [rbp+160h+sz]
0x18000e8b9  mov     rdx, rsi
0x18000e8bc  lea     rcx, [rbp+160h+SubKey]
0x18000e8c0  call    cs:__imp__o_wcscat_s
0x18000e8c6  test    eax, eax
0x18000e8c8  jz      short loc_18000E8EE
0x18000e8ca  cmp     eax, r14d
0x18000e8cd  jz      loc_18000EA3F
0x18000e8d3  cmp     eax, 16h
0x18000e8d6  jz      loc_18000EA55
0x18000e8dc  cmp     eax, 22h ; '"'
0x18000e8df  jz      loc_18000EA55
0x18000e8e5  cmp     eax, r12d
0x18000e8e8  jnz     loc_18000EA4A
0x18000e8ee  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000e8f5  mov     rdx, rsi
0x18000e8f8  lea     rcx, [rbp+160h+SubKey]
0x18000e8fc  call    cs:__imp__o_wcscat_s
0x18000e902  test    eax, eax
0x18000e904  jz      short loc_18000E92A
0x18000e906  cmp     eax, r14d
0x18000e909  jz      loc_18000EA3F
0x18000e90f  cmp     eax, 16h
0x18000e912  jz      loc_18000EA55
0x18000e918  cmp     eax, 22h ; '"'
0x18000e91b  jz      loc_18000EA55
0x18000e921  cmp     eax, r12d
0x18000e924  jnz     loc_18000EA4A
0x18000e92a  mov     [rsp+260h+hKey], r15
0x18000e92f  lea     rax, [rsp+260h+hKey]
0x18000e934  mov     [rsp+260h+ppv], rax; phkResult
0x18000e939  mov     r9d, 20019h; samDesired
0x18000e93f  xor     r8d, r8d; ulOptions
0x18000e942  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000e946  mov     rcx, rdi; hKey
0x18000e949  call    cs:__imp_RegOpenKeyExW
0x18000e94f  test    eax, eax
0x18000e951  jnz     loc_18000E9DE
0x18000e957  mov     eax, r15d
0x18000e95a  test    rbx, rbx
0x18000e95d  jz      short loc_18000E968
0x18000e95f  mov     rcx, rbx; hKey
0x18000e962  call    cs:__imp_RegCloseKey
0x18000e968  mov     rbx, [rsp+260h+hKey]
0x18000e96d  test    eax, eax
0x18000e96f  jnz     short loc_18000E9DE
0x18000e971  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000e976  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000e97b  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000e980  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000e985  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000e98a  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000e98f  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000e994  lea     rax, [rsp+260h+cSubKeys]
0x18000e999  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000e99e  xor     r9d, r9d; lpReserved
0x18000e9a1  xor     r8d, r8d; lpcchClass
0x18000e9a4  xor     edx, edx; lpClass
0x18000e9a6  mov     rcx, rbx; hKey
0x18000e9a9  call    cs:__imp_RegQueryInfoKeyW
0x18000e9af  mov     esi, eax
0x18000e9b1  test    rbx, rbx
0x18000e9b4  jz      short loc_18000E9C2
0x18000e9b6  mov     rcx, rbx; hKey
0x18000e9b9  call    cs:__imp_RegCloseKey
0x18000e9bf  mov     rbx, r15
0x18000e9c2  test    esi, esi
0x18000e9c4  jnz     short loc_18000E9EC
0x18000e9c6  cmp     [rsp+260h+cSubKeys], r15d
0x18000e9cb  jnz     short loc_18000E9DE
0x18000e9cd  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000e9d1  lea     rcx, [rbp+160h+var_1E0]; this
0x18000e9d5  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000e9da  mov     rdi, [rbp+160h+var_1E0]
0x18000e9de  test    rbx, rbx
0x18000e9e1  jz      short loc_18000E9EC
0x18000e9e3  mov     rcx, rbx; hKey
0x18000e9e6  call    cs:__imp_RegCloseKey
0x18000e9ec  test    rdi, rdi
0x18000e9ef  jz      short loc_18000E9FB
0x18000e9f1  mov     rcx, rdi; hKey
0x18000e9f4  call    cs:__imp_RegCloseKey
0x18000e9fa  nop
0x18000e9fb  mov     rcx, [rsp+260h+var_1F8]
0x18000ea00  test    rcx, rcx
0x18000ea03  jz      short loc_18000EA12
0x18000ea05  mov     rax, [rcx]
0x18000ea08  mov     rax, [rax+10h]
0x18000ea0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea11  nop
0x18000ea12  xor     eax, eax
0x18000ea14  mov     rcx, [rbp+160h+var_30]
0x18000ea1b  xor     rcx, rsp; StackCookie
0x18000ea1e  call    __security_check_cookie
0x18000ea23  lea     r11, [rsp+260h+var_20]
0x18000ea2b  mov     rbx, [r11+40h]
0x18000ea2f  mov     rsi, [r11+48h]
0x18000ea33  mov     rsp, r11
0x18000ea36  pop     r15
0x18000ea38  pop     r14
0x18000ea3a  pop     r12
0x18000ea3c  pop     rdi
0x18000ea3d  pop     rbp
  ... truncated ...
```
