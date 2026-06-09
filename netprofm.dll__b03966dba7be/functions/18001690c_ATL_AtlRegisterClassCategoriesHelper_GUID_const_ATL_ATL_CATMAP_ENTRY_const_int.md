# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18001690c`
- end: `0x180016c38`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `812`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b690`
- `0x18001cc04`

## callees

- `0x180006b20`
- `0x1800086b0`
- `0x1800120d0`
- `0x180015730`
- `0x1800167fc`
- `0x18001690c`
- `0x180016fb8`
- `0x180017670`
- `0x18001a5d8`
- `0x180043010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180016a4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180016a68`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180016b42`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180016b5d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180016a4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180016a68`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180016b42`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180016b5d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180016a34`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180016b27`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180016a34`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180016b27`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016aea`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016bb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016aea`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016bb8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180016a18`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180016a18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016992`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016992`

## string_xrefs

- `0x180016a29`: `CLSID\`
- `0x180016b19`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(
        GUID *rguid,
        const struct ATL::_ATL_CATMAP_ENTRY *a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // r14d
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rbx
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // edi
  int v10; // eax
  int v11; // eax
  int v12; // eax
  HKEY v13; // rdi
  unsigned int v14; // r9d
  LSTATUS v15; // ebx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // r9d
  LSTATUS v20; // ebx
  HKEY hKey[3]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v23[3]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h] BYREF
  DWORD cSubKeys; // [rsp+98h] [rbp-68h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v27; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a3;
  v5 = a2;
  v27 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL, a3, a4)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v5 )
    {
      v27 = *(_OWORD *)*((_QWORD *)v5 + 1);
      v7 = *(_QWORD *)ppv;
      if ( v4 )
      {
        if ( *(_DWORD *)v5 == 1 )
          v8 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v7 + 40))(ppv, rguid, 1, &v27);
        else
          v8 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v7 + 56))(ppv, rguid, 1, &v27);
        v9 = v8;
        if ( v8 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v5 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v7 + 48))(ppv, rguid, 1, &v27);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v7 + 64))(ppv, rguid, 1, &v27);
      }
      v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v5 + 16);
    }
    if ( !v4 )
    {
      StringFromGUID2(rguid, sz, 64);
      v24 = 0;
      v10 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v11);
      v12 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v12);
      v13 = HKEY_CLASSES_ROOT;
      v23[1] = 0;
      v23[0] = 0xFFFFFFFF80000000uLL;
      v23[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, v14) )
      {
        v15 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v15 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v23, SubKey);
          v13 = (HKEY)v23[0];
        }
      }
      v16 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v16);
      v17 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v17);
      v18 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v18);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v13, SubKey, v19) )
      {
        v20 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v20 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v23, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v23);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v24);
    }
  }
  v9 = 0;
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v9;
}

```

## disassembly

```asm
0x18001690c  mov     [rsp-8+arg_10], rbx
0x180016911  mov     [rsp-8+arg_18], rsi
0x180016916  push    rbp
0x180016917  push    rdi
0x180016918  push    r12
0x18001691a  push    r14
0x18001691c  push    r15
0x18001691e  lea     rbp, [rsp-150h]
0x180016926  sub     rsp, 250h
0x18001692d  mov     rax, cs:__security_cookie
0x180016934  xor     rax, rsp
0x180016937  mov     [rbp+170h+var_30], rax
0x18001693e  xor     r15d, r15d
0x180016941  xorps   xmm0, xmm0
0x180016944  mov     [rbp+170h+var_1D0], r15
0x180016948  mov     r14d, r8d
0x18001694b  mov     rbx, rdx
0x18001694e  mov     rsi, rcx
0x180016951  movups  [rbp+170h+var_1C8], xmm0
0x180016955  test    rdx, rdx
0x180016958  jz      loc_180016BFF
0x18001695e  lea     rdx, GUID_NULL
0x180016965  call    InlineIsEqualGUID
0x18001696a  test    eax, eax
0x18001696c  jnz     loc_180016BFF
0x180016972  lea     rax, [rbp+170h+var_1D0]
0x180016976  xor     edx, edx; pUnkOuter
0x180016978  lea     r12d, [r15+1]
0x18001697c  mov     [rsp+270h+ppv], rax; ppv
0x180016981  mov     r8d, r12d; dwClsContext
0x180016984  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18001698b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180016992  call    cs:__imp_CoCreateInstance
0x180016998  test    eax, eax
0x18001699a  js      loc_180016BFF
0x1800169a0  cmp     [rbx], r15d
0x1800169a3  jz      short loc_180016A01
0x1800169a5  mov     rax, [rbx+8]
0x1800169a9  lea     r9, [rbp+170h+var_1C8]
0x1800169ad  mov     rcx, [rbp+170h+var_1D0]
0x1800169b1  mov     r8d, r12d
0x1800169b4  mov     rdx, rsi
0x1800169b7  movups  xmm0, xmmword ptr [rax]
0x1800169ba  movdqu  [rbp+170h+var_1C8], xmm0
0x1800169bf  mov     rax, [rcx]
0x1800169c2  test    r14d, r14d
0x1800169c5  jz      short loc_1800169E7
0x1800169c7  cmp     [rbx], r12d
0x1800169ca  jnz     short loc_1800169D2
0x1800169cc  mov     rax, [rax+28h]
0x1800169d0  jmp     short loc_1800169D6
0x1800169d2  mov     rax, [rax+38h]
0x1800169d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169db  mov     edi, eax
0x1800169dd  test    eax, eax
0x1800169df  js      loc_180016C02
0x1800169e5  jmp     short loc_1800169FB
0x1800169e7  cmp     [rbx], r12d
0x1800169ea  jnz     short loc_1800169F2
0x1800169ec  mov     rax, [rax+30h]
0x1800169f0  jmp     short loc_1800169F6
0x1800169f2  mov     rax, [rax+40h]
0x1800169f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169fb  add     rbx, 10h
0x1800169ff  jmp     short loc_1800169A0
0x180016a01  test    r14d, r14d
0x180016a04  jnz     loc_180016BFF
0x180016a0a  lea     r8d, [r14+40h]; cchMax
0x180016a0e  mov     rcx, rsi; rguid
0x180016a11  lea     rdx, [rbp+170h+sz]; lpsz
0x180016a18  call    cs:__imp_StringFromGUID2
0x180016a1e  mov     esi, 80h
0x180016a23  mov     [rbp+170h+var_1E0], r15
0x180016a27  mov     edx, esi
0x180016a29  lea     r8, aClsid; "CLSID\\"
0x180016a30  lea     rcx, [rbp+170h+SubKey]
0x180016a34  call    cs:__imp__o_wcscpy_s
0x180016a3a  mov     ecx, eax; int
0x180016a3c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016a41  lea     r8, [rbp+170h+sz]
0x180016a48  mov     edx, esi
0x180016a4a  lea     rcx, [rbp+170h+SubKey]
0x180016a4e  call    cs:__imp__o_wcscat_s
0x180016a54  mov     ecx, eax; int
0x180016a56  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016a5b  lea     r8, aRequiredCatego; "\\Required Categories"
0x180016a62  mov     edx, esi
0x180016a64  lea     rcx, [rbp+170h+SubKey]
0x180016a68  call    cs:__imp__o_wcscat_s
0x180016a6e  mov     ecx, eax; int
0x180016a70  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016a75  mov     rdi, 0FFFFFFFF80000000h
0x180016a7c  mov     [rbp+170h+var_1F0], r15
0x180016a80  mov     rdx, rdi; hKey
0x180016a83  mov     [rsp+270h+var_1F8], rdi
0x180016a88  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180016a8c  mov     [rbp+170h+var_1E8], r15
0x180016a90  lea     rcx, [rsp+270h+hKey]; this
0x180016a95  mov     [rsp+270h+hKey], r15
0x180016a9a  mov     [rsp+270h+var_208], r15
0x180016a9f  mov     [rsp+270h+var_200], r15
0x180016aa4  mov     [rbp+170h+cSubKeys], r15d
0x180016aa8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180016aad  test    eax, eax
0x180016aaf  jnz     short loc_180016B19
0x180016ab1  mov     rcx, [rsp+270h+hKey]; hKey
0x180016ab6  lea     rax, [rbp+170h+cSubKeys]
0x180016aba  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180016abf  xor     r9d, r9d; lpReserved
0x180016ac2  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180016ac7  xor     r8d, r8d; lpcchClass
0x180016aca  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180016acf  xor     edx, edx; lpClass
0x180016ad1  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180016ad6  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180016adb  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180016ae0  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180016ae5  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180016aea  call    cs:__imp_RegQueryInfoKeyW
0x180016af0  lea     rcx, [rsp+270h+hKey]; this
0x180016af5  mov     ebx, eax
0x180016af7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016afc  test    ebx, ebx
0x180016afe  jnz     short loc_180016B19
0x180016b00  cmp     [rbp+170h+cSubKeys], r15d
0x180016b04  jnz     short loc_180016B19
0x180016b06  lea     rdx, [rbp+170h+SubKey]; wchar_t *
0x180016b0a  lea     rcx, [rsp+270h+var_1F8]; this
0x180016b0f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180016b14  mov     rdi, [rsp+270h+var_1F8]
0x180016b19  lea     r8, aClsid; "CLSID\\"
0x180016b20  mov     rdx, rsi
0x180016b23  lea     rcx, [rbp+170h+SubKey]
0x180016b27  call    cs:__imp__o_wcscpy_s
0x180016b2d  mov     ecx, eax; int
0x180016b2f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016b34  lea     r8, [rbp+170h+sz]
0x180016b3b  mov     rdx, rsi
0x180016b3e  lea     rcx, [rbp+170h+SubKey]
0x180016b42  call    cs:__imp__o_wcscat_s
0x180016b48  mov     ecx, eax; int
0x180016b4a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016b4f  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180016b56  mov     rdx, rsi
0x180016b59  lea     rcx, [rbp+170h+SubKey]
0x180016b5d  call    cs:__imp__o_wcscat_s
0x180016b63  mov     ecx, eax; int
0x180016b65  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180016b6a  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180016b6e  mov     rdx, rdi; hKey
0x180016b71  lea     rcx, [rsp+270h+hKey]; this
0x180016b76  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180016b7b  test    eax, eax
0x180016b7d  jnz     short loc_180016BE2
0x180016b7f  mov     rcx, [rsp+270h+hKey]; hKey
0x180016b84  lea     rax, [rbp+170h+cSubKeys]
0x180016b88  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180016b8d  xor     r9d, r9d; lpReserved
0x180016b90  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180016b95  xor     r8d, r8d; lpcchClass
0x180016b98  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180016b9d  xor     edx, edx; lpClass
0x180016b9f  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180016ba4  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180016ba9  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180016bae  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180016bb3  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180016bb8  call    cs:__imp_RegQueryInfoKeyW
0x180016bbe  lea     rcx, [rsp+270h+hKey]; this
0x180016bc3  mov     ebx, eax
0x180016bc5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016bca  test    ebx, ebx
0x180016bcc  jnz     short loc_180016BE2
0x180016bce  cmp     [rbp+170h+cSubKeys], r15d
0x180016bd2  jnz     short loc_180016BE2
0x180016bd4  lea     rdx, [rbp+170h+SubKey]; wchar_t *
0x180016bd8  lea     rcx, [rsp+270h+var_1F8]; this
0x180016bdd  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180016be2  lea     rcx, [rsp+270h+hKey]; this
0x180016be7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016bec  lea     rcx, [rsp+270h+var_1F8]; this
0x180016bf1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016bf6  lea     rcx, [rbp+170h+var_1E0]
0x180016bfa  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180016bff  mov     edi, r15d
0x180016c02  lea     rcx, [rbp+170h+var_1D0]
0x180016c06  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180016c0b  mov     eax, edi
0x180016c0d  mov     rcx, [rbp+170h+var_30]
0x180016c14  xor     rcx, rsp; StackCookie
0x180016c17  call    __security_check_cookie
0x180016c1c  lea     r11, [rsp+270h+var_20]
0x180016c24  mov     rbx, [r11+40h]
0x180016c28  mov     rsi, [r11+48h]
0x180016c2c  mov     rsp, r11
0x180016c2f  pop     r15
0x180016c31  pop     r14
0x180016c33  pop     r12
0x180016c35  pop     rdi
0x180016c36  pop     rbp
0x180016c37  retn
```
