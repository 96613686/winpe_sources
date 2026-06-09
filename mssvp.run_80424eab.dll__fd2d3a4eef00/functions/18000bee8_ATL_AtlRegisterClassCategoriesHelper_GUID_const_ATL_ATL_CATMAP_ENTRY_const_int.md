# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000bee8`
- end: `0x18000c223`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001058c`
- `0x180011f44`
- `0x1800134e0`

## callees

- `0x1800039e0`
- `0x180005210`
- `0x180006270`
- `0x180009eb8`
- `0x18000be84`
- `0x18000bee8`
- `0x18000c344`
- `0x18000d3dc`
- `0x18000ec74`
- `0x18003d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c02d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c047`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c129`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c144`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c02d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c047`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c129`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c144`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000c013`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000c10e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000c013`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000c10e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000bff7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000bff7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bf70`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bf70`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c0d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c1a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c0d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c1a3`

## string_xrefs

- `0x18000c008`: `CLSID\`
- `0x18000c100`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  HKEY v12; // rdi
  LSTATUS v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  LSTATUS v17; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v24 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v24 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v24);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v24);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v24);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v24);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v23 = 0;
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v22[1] = 0;
      v22[0] = 0xFFFFFFFF80000000uLL;
      v22[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, SubKey);
          v12 = (HKEY)v22[0];
        }
      }
      v14 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v14);
      v15 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v15);
      v16 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v16);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, SubKey, 0x20019u) )
      {
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v22);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v23);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x18000bee8  mov     [rsp-8+arg_10], rbx
0x18000beed  mov     [rsp-8+arg_18], rsi
0x18000bef2  push    rbp
0x18000bef3  push    rdi
0x18000bef4  push    r12
0x18000bef6  push    r14
0x18000bef8  push    r15
0x18000befa  lea     rbp, [rsp-150h]
0x18000bf02  sub     rsp, 250h
0x18000bf09  mov     rax, cs:__security_cookie
0x18000bf10  xor     rax, rsp
0x18000bf13  mov     [rbp+170h+var_30], rax
0x18000bf1a  xor     r15d, r15d
0x18000bf1d  xorps   xmm0, xmm0
0x18000bf20  mov     [rsp+270h+var_208], r15
0x18000bf25  mov     r14d, r8d
0x18000bf28  mov     rbx, rdx
0x18000bf2b  mov     rsi, rcx
0x18000bf2e  movups  [rbp+170h+var_1C8], xmm0
0x18000bf32  test    rdx, rdx
0x18000bf35  jz      loc_18000C1E9
0x18000bf3b  lea     rdx, GUID_NULL
0x18000bf42  call    InlineIsEqualGUID
0x18000bf47  test    eax, eax
0x18000bf49  jnz     loc_18000C1E9
0x18000bf4f  lea     rax, [rsp+270h+var_208]
0x18000bf54  xor     edx, edx; pUnkOuter
0x18000bf56  lea     r12d, [r15+1]
0x18000bf5a  mov     [rsp+270h+ppv], rax; ppv
0x18000bf5f  mov     r8d, r12d; dwClsContext
0x18000bf62  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000bf69  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000bf70  call    cs:__imp_CoCreateInstance
0x18000bf76  test    eax, eax
0x18000bf78  js      loc_18000C1E9
0x18000bf7e  cmp     [rbx], r15d
0x18000bf81  jz      short loc_18000BFE0
0x18000bf83  mov     rax, [rbx+8]
0x18000bf87  lea     r9, [rbp+170h+var_1C8]
0x18000bf8b  mov     rcx, [rsp+270h+var_208]
0x18000bf90  mov     r8d, r12d
0x18000bf93  mov     rdx, rsi
0x18000bf96  movups  xmm0, xmmword ptr [rax]
0x18000bf99  movdqu  [rbp+170h+var_1C8], xmm0
0x18000bf9e  mov     rax, [rcx]
0x18000bfa1  test    r14d, r14d
0x18000bfa4  jz      short loc_18000BFC6
0x18000bfa6  cmp     [rbx], r12d
0x18000bfa9  jnz     short loc_18000BFB1
0x18000bfab  mov     rax, [rax+28h]
0x18000bfaf  jmp     short loc_18000BFB5
0x18000bfb1  mov     rax, [rax+38h]
0x18000bfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfba  mov     edi, eax
0x18000bfbc  test    eax, eax
0x18000bfbe  js      loc_18000C1EC
0x18000bfc4  jmp     short loc_18000BFDA
0x18000bfc6  cmp     [rbx], r12d
0x18000bfc9  jnz     short loc_18000BFD1
0x18000bfcb  mov     rax, [rax+30h]
0x18000bfcf  jmp     short loc_18000BFD5
0x18000bfd1  mov     rax, [rax+40h]
0x18000bfd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfda  add     rbx, 10h
0x18000bfde  jmp     short loc_18000BF7E
0x18000bfe0  test    r14d, r14d
0x18000bfe3  jnz     loc_18000C1E9
0x18000bfe9  lea     r8d, [r14+40h]; cchMax
0x18000bfed  mov     rcx, rsi; rguid
0x18000bff0  lea     rdx, [rbp+170h+sz]; lpsz
0x18000bff7  call    cs:__imp_StringFromGUID2
0x18000bffd  mov     esi, 80h
0x18000c002  mov     [rbp+170h+var_1D0], r15
0x18000c006  mov     edx, esi
0x18000c008  lea     r8, aClsid; "CLSID\\"
0x18000c00f  lea     rcx, [rbp+170h+SubKey]
0x18000c013  call    cs:__imp__o_wcscpy_s
0x18000c019  mov     ecx, eax; int
0x18000c01b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000c020  lea     r8, [rbp+170h+sz]
0x18000c027  mov     edx, esi
0x18000c029  lea     rcx, [rbp+170h+SubKey]
0x18000c02d  call    cs:__imp__o_wcscat_s
0x18000c033  mov     ecx, eax; int
0x18000c035  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000c03a  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000c041  mov     edx, esi
0x18000c043  lea     rcx, [rbp+170h+SubKey]
0x18000c047  call    cs:__imp__o_wcscat_s
0x18000c04d  mov     ecx, eax; int
0x18000c04f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000c054  mov     rdi, 0FFFFFFFF80000000h
0x18000c05b  mov     [rbp+170h+var_1E0], r15
0x18000c05f  mov     r14d, 20019h
0x18000c065  mov     [rbp+170h+var_1E8], rdi
0x18000c069  mov     r9d, r14d; unsigned int
0x18000c06c  mov     [rbp+170h+var_1D8], r15
0x18000c070  mov     rdx, rdi; hKey
0x18000c073  mov     [rsp+270h+hKey], r15
0x18000c078  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18000c07c  mov     [rsp+270h+var_1F8], r15
0x18000c081  lea     rcx, [rsp+270h+hKey]; this
0x18000c086  mov     [rbp+170h+var_1F0], r15
0x18000c08a  mov     [rsp+270h+cSubKeys], r15d
0x18000c08f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000c094  test    eax, eax
0x18000c096  jnz     short loc_18000C100
0x18000c098  mov     rcx, [rsp+270h+hKey]; hKey
0x18000c09d  lea     rax, [rsp+270h+cSubKeys]
0x18000c0a2  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000c0a7  xor     r9d, r9d; lpReserved
0x18000c0aa  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000c0af  xor     r8d, r8d; lpcchClass
0x18000c0b2  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000c0b7  xor     edx, edx; lpClass
0x18000c0b9  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000c0be  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18000c0c3  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000c0c8  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000c0cd  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18000c0d2  call    cs:__imp_RegQueryInfoKeyW
0x18000c0d8  lea     rcx, [rsp+270h+hKey]; this
0x18000c0dd  mov     ebx, eax
0x18000c0df  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c0e4  test    ebx, ebx
0x18000c0e6  jnz     short loc_18000C100
0x18000c0e8  cmp     [rsp+270h+cSubKeys], r15d
0x18000c0ed  jnz     short loc_18000C100
0x18000c0ef  lea     rdx, [rbp+170h+SubKey]; wchar_t *
0x18000c0f3  lea     rcx, [rbp+170h+var_1E8]; this
0x18000c0f7  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18000c0fc  mov     rdi, [rbp+170h+var_1E8]
0x18000c100  lea     r8, aClsid; "CLSID\\"
0x18000c107  mov     rdx, rsi
0x18000c10a  lea     rcx, [rbp+170h+SubKey]
0x18000c10e  call    cs:__imp__o_wcscpy_s
0x18000c114  mov     ecx, eax; int
0x18000c116  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000c11b  lea     r8, [rbp+170h+sz]
0x18000c122  mov     rdx, rsi
0x18000c125  lea     rcx, [rbp+170h+SubKey]
0x18000c129  call    cs:__imp__o_wcscat_s
0x18000c12f  mov     ecx, eax; int
0x18000c131  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000c136  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000c13d  mov     rdx, rsi
0x18000c140  lea     rcx, [rbp+170h+SubKey]
0x18000c144  call    cs:__imp__o_wcscat_s
0x18000c14a  mov     ecx, eax; int
0x18000c14c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000c151  mov     r9d, r14d; unsigned int
0x18000c154  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18000c158  mov     rdx, rdi; hKey
0x18000c15b  lea     rcx, [rsp+270h+hKey]; this
0x18000c160  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000c165  test    eax, eax
0x18000c167  jnz     short loc_18000C1CD
0x18000c169  mov     rcx, [rsp+270h+hKey]; hKey
0x18000c16e  lea     rax, [rsp+270h+cSubKeys]
0x18000c173  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000c178  xor     r9d, r9d; lpReserved
0x18000c17b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000c180  xor     r8d, r8d; lpcchClass
0x18000c183  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000c188  xor     edx, edx; lpClass
0x18000c18a  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000c18f  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18000c194  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000c199  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000c19e  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18000c1a3  call    cs:__imp_RegQueryInfoKeyW
0x18000c1a9  lea     rcx, [rsp+270h+hKey]; this
0x18000c1ae  mov     ebx, eax
0x18000c1b0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c1b5  test    ebx, ebx
0x18000c1b7  jnz     short loc_18000C1CD
0x18000c1b9  cmp     [rsp+270h+cSubKeys], r15d
0x18000c1be  jnz     short loc_18000C1CD
0x18000c1c0  lea     rdx, [rbp+170h+SubKey]; wchar_t *
0x18000c1c4  lea     rcx, [rbp+170h+var_1E8]; this
0x18000c1c8  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18000c1cd  lea     rcx, [rsp+270h+hKey]; this
0x18000c1d2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c1d7  lea     rcx, [rbp+170h+var_1E8]; this
0x18000c1db  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c1e0  lea     rcx, [rbp+170h+var_1D0]
0x18000c1e4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c1e9  mov     edi, r15d
0x18000c1ec  lea     rcx, [rsp+270h+var_208]
0x18000c1f1  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18000c1f6  mov     eax, edi
0x18000c1f8  mov     rcx, [rbp+170h+var_30]
0x18000c1ff  xor     rcx, rsp; StackCookie
0x18000c202  call    __security_check_cookie
0x18000c207  lea     r11, [rsp+270h+var_20]
0x18000c20f  mov     rbx, [r11+40h]
0x18000c213  mov     rsi, [r11+48h]
0x18000c217  mov     rsp, r11
0x18000c21a  pop     r15
0x18000c21c  pop     r14
0x18000c21e  pop     r12
0x18000c220  pop     rdi
0x18000c221  pop     rbp
0x18000c222  retn
```
