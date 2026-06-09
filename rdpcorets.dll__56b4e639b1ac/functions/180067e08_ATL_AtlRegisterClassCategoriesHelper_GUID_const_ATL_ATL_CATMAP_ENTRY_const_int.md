# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180067e08`
- end: `0x180068143`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180069858`
- `0x18006a1c4`
- `0x18006aa60`
- `0x18006aac0`

## callees

- `0x180017508`
- `0x180033da0`
- `0x1800453cc`
- `0x180066e38`
- `0x180067be4`
- `0x180067e08`
- `0x1800684d4`
- `0x18006877c`
- `0x180068cd0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180067f4d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180067f67`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180068049`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180068064`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180067f4d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180067f67`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180068049`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180068064`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067f33`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006802e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067f33`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006802e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180067ff2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800680c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180067ff2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800680c3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180067f17`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180067f17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180067e90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180067e90`

## string_xrefs

- `0x180067f28`: `CLSID\`
- `0x180068020`: `CLSID\`

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
  wil::com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>::~com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180067e08  mov     [rsp-8+arg_10], rbx
0x180067e0d  mov     [rsp-8+arg_18], rsi
0x180067e12  push    rbp
0x180067e13  push    rdi
0x180067e14  push    r12
0x180067e16  push    r14
0x180067e18  push    r15
0x180067e1a  lea     rbp, [rsp-150h]
0x180067e22  sub     rsp, 250h
0x180067e29  mov     rax, cs:__security_cookie
0x180067e30  xor     rax, rsp
0x180067e33  mov     [rbp+170h+var_30], rax
0x180067e3a  xor     r15d, r15d
0x180067e3d  xorps   xmm0, xmm0
0x180067e40  mov     [rsp+270h+var_208], r15
0x180067e45  mov     r14d, r8d
0x180067e48  mov     rbx, rdx
0x180067e4b  mov     rsi, rcx
0x180067e4e  movups  [rbp+170h+var_1C8], xmm0
0x180067e52  test    rdx, rdx
0x180067e55  jz      loc_180068109
0x180067e5b  lea     rdx, GUID_NULL; struct _GUID *
0x180067e62  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180067e67  test    eax, eax
0x180067e69  jnz     loc_180068109
0x180067e6f  lea     rax, [rsp+270h+var_208]
0x180067e74  xor     edx, edx; pUnkOuter
0x180067e76  lea     r12d, [r15+1]
0x180067e7a  mov     [rsp+270h+ppv], rax; ppv
0x180067e7f  mov     r8d, r12d; dwClsContext
0x180067e82  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180067e89  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180067e90  call    cs:__imp_CoCreateInstance
0x180067e96  test    eax, eax
0x180067e98  js      loc_180068109
0x180067e9e  cmp     [rbx], r15d
0x180067ea1  jz      short loc_180067F00
0x180067ea3  mov     rax, [rbx+8]
0x180067ea7  lea     r9, [rbp+170h+var_1C8]
0x180067eab  mov     rcx, [rsp+270h+var_208]
0x180067eb0  mov     r8d, r12d
0x180067eb3  mov     rdx, rsi
0x180067eb6  movups  xmm0, xmmword ptr [rax]
0x180067eb9  movdqu  [rbp+170h+var_1C8], xmm0
0x180067ebe  mov     rax, [rcx]
0x180067ec1  test    r14d, r14d
0x180067ec4  jz      short loc_180067EE6
0x180067ec6  cmp     [rbx], r12d
0x180067ec9  jnz     short loc_180067ED1
0x180067ecb  mov     rax, [rax+28h]
0x180067ecf  jmp     short loc_180067ED5
0x180067ed1  mov     rax, [rax+38h]
0x180067ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067eda  mov     edi, eax
0x180067edc  test    eax, eax
0x180067ede  js      loc_18006810C
0x180067ee4  jmp     short loc_180067EFA
0x180067ee6  cmp     [rbx], r12d
0x180067ee9  jnz     short loc_180067EF1
0x180067eeb  mov     rax, [rax+30h]
0x180067eef  jmp     short loc_180067EF5
0x180067ef1  mov     rax, [rax+40h]
0x180067ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067efa  add     rbx, 10h
0x180067efe  jmp     short loc_180067E9E
0x180067f00  test    r14d, r14d
0x180067f03  jnz     loc_180068109
0x180067f09  lea     r8d, [r14+40h]; cchMax
0x180067f0d  mov     rcx, rsi; rguid
0x180067f10  lea     rdx, [rbp+170h+sz]; lpsz
0x180067f17  call    cs:__imp_StringFromGUID2
0x180067f1d  mov     esi, 80h
0x180067f22  mov     [rbp+170h+var_1D0], r15
0x180067f26  mov     edx, esi
0x180067f28  lea     r8, aClsid; "CLSID\\"
0x180067f2f  lea     rcx, [rbp+170h+SubKey]
0x180067f33  call    cs:__imp__o_wcscpy_s
0x180067f39  mov     ecx, eax; int
0x180067f3b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180067f40  lea     r8, [rbp+170h+sz]
0x180067f47  mov     edx, esi
0x180067f49  lea     rcx, [rbp+170h+SubKey]
0x180067f4d  call    cs:__imp__o_wcscat_s
0x180067f53  mov     ecx, eax; int
0x180067f55  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180067f5a  lea     r8, aRequiredCatego; "\\Required Categories"
0x180067f61  mov     edx, esi
0x180067f63  lea     rcx, [rbp+170h+SubKey]
0x180067f67  call    cs:__imp__o_wcscat_s
0x180067f6d  mov     ecx, eax; int
0x180067f6f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180067f74  mov     rdi, 0FFFFFFFF80000000h
0x180067f7b  mov     [rbp+170h+var_1E0], r15
0x180067f7f  mov     r14d, 20019h
0x180067f85  mov     [rbp+170h+var_1E8], rdi
0x180067f89  mov     r9d, r14d; unsigned int
0x180067f8c  mov     [rbp+170h+var_1D8], r15
0x180067f90  mov     rdx, rdi; hKey
0x180067f93  mov     [rsp+270h+hKey], r15
0x180067f98  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180067f9c  mov     [rsp+270h+var_1F8], r15
0x180067fa1  lea     rcx, [rsp+270h+hKey]; this
0x180067fa6  mov     [rbp+170h+var_1F0], r15
0x180067faa  mov     [rsp+270h+cSubKeys], r15d
0x180067faf  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180067fb4  test    eax, eax
0x180067fb6  jnz     short loc_180068020
0x180067fb8  mov     rcx, [rsp+270h+hKey]; hKey
0x180067fbd  lea     rax, [rsp+270h+cSubKeys]
0x180067fc2  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180067fc7  xor     r9d, r9d; lpReserved
0x180067fca  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180067fcf  xor     r8d, r8d; lpcchClass
0x180067fd2  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180067fd7  xor     edx, edx; lpClass
0x180067fd9  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180067fde  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180067fe3  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180067fe8  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180067fed  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180067ff2  call    cs:__imp_RegQueryInfoKeyW
0x180067ff8  lea     rcx, [rsp+270h+hKey]; this
0x180067ffd  mov     ebx, eax
0x180067fff  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180068004  test    ebx, ebx
0x180068006  jnz     short loc_180068020
0x180068008  cmp     [rsp+270h+cSubKeys], r15d
0x18006800d  jnz     short loc_180068020
0x18006800f  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180068013  lea     rcx, [rbp+170h+var_1E8]; this
0x180068017  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18006801c  mov     rdi, [rbp+170h+var_1E8]
0x180068020  lea     r8, aClsid; "CLSID\\"
0x180068027  mov     rdx, rsi
0x18006802a  lea     rcx, [rbp+170h+SubKey]
0x18006802e  call    cs:__imp__o_wcscpy_s
0x180068034  mov     ecx, eax; int
0x180068036  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18006803b  lea     r8, [rbp+170h+sz]
0x180068042  mov     rdx, rsi
0x180068045  lea     rcx, [rbp+170h+SubKey]
0x180068049  call    cs:__imp__o_wcscat_s
0x18006804f  mov     ecx, eax; int
0x180068051  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180068056  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18006805d  mov     rdx, rsi
0x180068060  lea     rcx, [rbp+170h+SubKey]
0x180068064  call    cs:__imp__o_wcscat_s
0x18006806a  mov     ecx, eax; int
0x18006806c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180068071  mov     r9d, r14d; unsigned int
0x180068074  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180068078  mov     rdx, rdi; hKey
0x18006807b  lea     rcx, [rsp+270h+hKey]; this
0x180068080  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180068085  test    eax, eax
0x180068087  jnz     short loc_1800680ED
0x180068089  mov     rcx, [rsp+270h+hKey]; hKey
0x18006808e  lea     rax, [rsp+270h+cSubKeys]
0x180068093  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180068098  xor     r9d, r9d; lpReserved
0x18006809b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800680a0  xor     r8d, r8d; lpcchClass
0x1800680a3  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800680a8  xor     edx, edx; lpClass
0x1800680aa  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800680af  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800680b4  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800680b9  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800680be  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800680c3  call    cs:__imp_RegQueryInfoKeyW
0x1800680c9  lea     rcx, [rsp+270h+hKey]; this
0x1800680ce  mov     ebx, eax
0x1800680d0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800680d5  test    ebx, ebx
0x1800680d7  jnz     short loc_1800680ED
0x1800680d9  cmp     [rsp+270h+cSubKeys], r15d
0x1800680de  jnz     short loc_1800680ED
0x1800680e0  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x1800680e4  lea     rcx, [rbp+170h+var_1E8]; this
0x1800680e8  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800680ed  lea     rcx, [rsp+270h+hKey]; this
0x1800680f2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800680f7  lea     rcx, [rbp+170h+var_1E8]; this
0x1800680fb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180068100  lea     rcx, [rbp+170h+var_1D0]
0x180068104  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180068109  mov     edi, r15d
0x18006810c  lea     rcx, [rsp+270h+var_208]
0x180068111  call    ??1?$com_ptr_t@UIRdpSideBandDataSource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>::~com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>(void)
0x180068116  mov     eax, edi
0x180068118  mov     rcx, [rbp+170h+var_30]
0x18006811f  xor     rcx, rsp; StackCookie
0x180068122  call    __security_check_cookie
0x180068127  lea     r11, [rsp+270h+var_20]
0x18006812f  mov     rbx, [r11+40h]
0x180068133  mov     rsi, [r11+48h]
0x180068137  mov     rsp, r11
0x18006813a  pop     r15
0x18006813c  pop     r14
0x18006813e  pop     r12
0x180068140  pop     rdi
0x180068141  pop     rbp
0x180068142  retn
```
