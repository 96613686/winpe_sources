# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180047d5c`
- end: `0x18004806d`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `785`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800492c0`
- `0x180049358`
- `0x180049ed8`

## callees

- `0x180021e18`
- `0x18003655c`
- `0x180047080`
- `0x180047d5c`
- `0x180048214`
- `0x1800483ac`
- `0x180048a7c`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180047e9a`
- `msvcrt!wcscat_s` at `0x180047ead`
- `msvcrt!wcscat_s` at `0x180047f81`
- `msvcrt!wcscat_s` at `0x180047f95`
- `msvcrt!wcscat_s` at `0x180047e9a`
- `msvcrt!wcscat_s` at `0x180047ead`
- `msvcrt!wcscat_s` at `0x180047f81`
- `msvcrt!wcscat_s` at `0x180047f95`
- `msvcrt!wcscpy_s` at `0x180047e87`
- `msvcrt!wcscpy_s` at `0x180047f6d`
- `msvcrt!wcscpy_s` at `0x180047e87`
- `msvcrt!wcscpy_s` at `0x180047f6d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047f31`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047fed`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047f31`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047fed`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180047e6b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180047e6b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047de4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047de4`

## string_xrefs

- `0x180047e7c`: `CLSID\`
- `0x180047f5f`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  HKEY v9; // rdi
  LSTATUS v10; // ebx
  LSTATUS v11; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v16[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v17; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v18; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v18 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v18 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v18);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v18);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v18);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v18);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v17 = 0;
      wcscpy_s(Destination, 0x80u, L"CLSID\\");
      wcscat_s(Destination, 0x80u, sz);
      wcscat_s(Destination, 0x80u, L"\\Required Categories");
      v9 = HKEY_CLASSES_ROOT;
      v16[1] = 0;
      v16[0] = 0xFFFFFFFF80000000uLL;
      v16[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
      {
        v10 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v10 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v16, Destination);
          v9 = (HKEY)v16[0];
        }
      }
      wcscpy_s(Destination, 0x80u, L"CLSID\\");
      wcscat_s(Destination, 0x80u, sz);
      wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v9, Destination, 0x20019u) )
      {
        v11 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v11 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v16, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v16);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v17);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x180047d5c  mov     [rsp-8+arg_10], rbx
0x180047d61  mov     [rsp-8+arg_18], rsi
0x180047d66  push    rbp
0x180047d67  push    rdi
0x180047d68  push    r12
0x180047d6a  push    r14
0x180047d6c  push    r15
0x180047d6e  lea     rbp, [rsp-150h]
0x180047d76  sub     rsp, 250h
0x180047d7d  mov     rax, cs:__security_cookie
0x180047d84  xor     rax, rsp
0x180047d87  mov     [rbp+170h+var_30], rax
0x180047d8e  xor     r15d, r15d
0x180047d91  xorps   xmm0, xmm0
0x180047d94  mov     [rsp+270h+var_208], r15
0x180047d99  mov     r14d, r8d
0x180047d9c  mov     rbx, rdx
0x180047d9f  mov     rsi, rcx
0x180047da2  movups  [rbp+170h+var_1C8], xmm0
0x180047da6  test    rdx, rdx
0x180047da9  jz      loc_180048033
0x180047daf  lea     rdx, GUID_NULL; struct _GUID *
0x180047db6  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180047dbb  test    eax, eax
0x180047dbd  jnz     loc_180048033
0x180047dc3  lea     rax, [rsp+270h+var_208]
0x180047dc8  xor     edx, edx; pUnkOuter
0x180047dca  lea     r12d, [r15+1]
0x180047dce  mov     [rsp+270h+ppv], rax; ppv
0x180047dd3  mov     r8d, r12d; dwClsContext
0x180047dd6  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180047ddd  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180047de4  call    cs:__imp_CoCreateInstance
0x180047dea  test    eax, eax
0x180047dec  js      loc_180048033
0x180047df2  cmp     [rbx], r15d
0x180047df5  jz      short loc_180047E54
0x180047df7  mov     rax, [rbx+8]
0x180047dfb  lea     r9, [rbp+170h+var_1C8]
0x180047dff  mov     rcx, [rsp+270h+var_208]
0x180047e04  mov     r8d, r12d
0x180047e07  mov     rdx, rsi
0x180047e0a  movups  xmm0, xmmword ptr [rax]
0x180047e0d  movdqu  [rbp+170h+var_1C8], xmm0
0x180047e12  mov     rax, [rcx]
0x180047e15  test    r14d, r14d
0x180047e18  jz      short loc_180047E3A
0x180047e1a  cmp     [rbx], r12d
0x180047e1d  jnz     short loc_180047E25
0x180047e1f  mov     rax, [rax+28h]
0x180047e23  jmp     short loc_180047E29
0x180047e25  mov     rax, [rax+38h]
0x180047e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e2e  mov     edi, eax
0x180047e30  test    eax, eax
0x180047e32  js      loc_180048036
0x180047e38  jmp     short loc_180047E4E
0x180047e3a  cmp     [rbx], r12d
0x180047e3d  jnz     short loc_180047E45
0x180047e3f  mov     rax, [rax+30h]
0x180047e43  jmp     short loc_180047E49
0x180047e45  mov     rax, [rax+40h]
0x180047e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e4e  add     rbx, 10h
0x180047e52  jmp     short loc_180047DF2
0x180047e54  test    r14d, r14d
0x180047e57  jnz     loc_180048033
0x180047e5d  lea     r8d, [r14+40h]; cchMax
0x180047e61  mov     rcx, rsi; rguid
0x180047e64  lea     rdx, [rbp+170h+sz]; lpsz
0x180047e6b  call    cs:__imp_StringFromGUID2
0x180047e71  mov     esi, 80h
0x180047e76  mov     [rbp+170h+var_1D0], r15
0x180047e7a  mov     edx, esi; SizeInWords
0x180047e7c  lea     r8, aClsid; "CLSID\\"
0x180047e83  lea     rcx, [rbp+170h+Destination]; Destination
0x180047e87  call    cs:__imp_wcscpy_s
0x180047e8d  lea     r8, [rbp+170h+sz]; Source
0x180047e94  mov     edx, esi; SizeInWords
0x180047e96  lea     rcx, [rbp+170h+Destination]; Destination
0x180047e9a  call    cs:__imp_wcscat_s
0x180047ea0  lea     r8, aRequiredCatego; "\\Required Categories"
0x180047ea7  mov     edx, esi; SizeInWords
0x180047ea9  lea     rcx, [rbp+170h+Destination]; Destination
0x180047ead  call    cs:__imp_wcscat_s
0x180047eb3  mov     rdi, 0FFFFFFFF80000000h
0x180047eba  mov     [rbp+170h+var_1E0], r15
0x180047ebe  mov     r14d, 20019h
0x180047ec4  mov     [rbp+170h+var_1E8], rdi
0x180047ec8  mov     r9d, r14d; unsigned int
0x180047ecb  mov     [rbp+170h+var_1D8], r15
0x180047ecf  mov     rdx, rdi; hKey
0x180047ed2  mov     [rsp+270h+hKey], r15
0x180047ed7  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180047edb  mov     [rsp+270h+var_1F8], r15
0x180047ee0  lea     rcx, [rsp+270h+hKey]; this
0x180047ee5  mov     [rbp+170h+var_1F0], r15
0x180047ee9  mov     [rsp+270h+cSubKeys], r15d
0x180047eee  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180047ef3  test    eax, eax
0x180047ef5  jnz     short loc_180047F5F
0x180047ef7  mov     rcx, [rsp+270h+hKey]; hKey
0x180047efc  lea     rax, [rsp+270h+cSubKeys]
0x180047f01  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180047f06  xor     r9d, r9d; lpReserved
0x180047f09  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180047f0e  xor     r8d, r8d; lpcchClass
0x180047f11  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180047f16  xor     edx, edx; lpClass
0x180047f18  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180047f1d  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180047f22  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180047f27  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180047f2c  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180047f31  call    cs:__imp_RegQueryInfoKeyW
0x180047f37  lea     rcx, [rsp+270h+hKey]; this
0x180047f3c  mov     ebx, eax
0x180047f3e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180047f43  test    ebx, ebx
0x180047f45  jnz     short loc_180047F5F
0x180047f47  cmp     [rsp+270h+cSubKeys], r15d
0x180047f4c  jnz     short loc_180047F5F
0x180047f4e  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180047f52  lea     rcx, [rbp+170h+var_1E8]; this
0x180047f56  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180047f5b  mov     rdi, [rbp+170h+var_1E8]
0x180047f5f  lea     r8, aClsid; "CLSID\\"
0x180047f66  mov     rdx, rsi; SizeInWords
0x180047f69  lea     rcx, [rbp+170h+Destination]; Destination
0x180047f6d  call    cs:__imp_wcscpy_s
0x180047f73  lea     r8, [rbp+170h+sz]; Source
0x180047f7a  mov     rdx, rsi; SizeInWords
0x180047f7d  lea     rcx, [rbp+170h+Destination]; Destination
0x180047f81  call    cs:__imp_wcscat_s
0x180047f87  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180047f8e  mov     rdx, rsi; SizeInWords
0x180047f91  lea     rcx, [rbp+170h+Destination]; Destination
0x180047f95  call    cs:__imp_wcscat_s
0x180047f9b  mov     r9d, r14d; unsigned int
0x180047f9e  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180047fa2  mov     rdx, rdi; hKey
0x180047fa5  lea     rcx, [rsp+270h+hKey]; this
0x180047faa  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180047faf  test    eax, eax
0x180047fb1  jnz     short loc_180048017
0x180047fb3  mov     rcx, [rsp+270h+hKey]; hKey
0x180047fb8  lea     rax, [rsp+270h+cSubKeys]
0x180047fbd  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180047fc2  xor     r9d, r9d; lpReserved
0x180047fc5  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180047fca  xor     r8d, r8d; lpcchClass
0x180047fcd  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180047fd2  xor     edx, edx; lpClass
0x180047fd4  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180047fd9  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180047fde  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180047fe3  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180047fe8  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180047fed  call    cs:__imp_RegQueryInfoKeyW
0x180047ff3  lea     rcx, [rsp+270h+hKey]; this
0x180047ff8  mov     ebx, eax
0x180047ffa  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180047fff  test    ebx, ebx
0x180048001  jnz     short loc_180048017
0x180048003  cmp     [rsp+270h+cSubKeys], r15d
0x180048008  jnz     short loc_180048017
0x18004800a  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x18004800e  lea     rcx, [rbp+170h+var_1E8]; this
0x180048012  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180048017  lea     rcx, [rsp+270h+hKey]; this
0x18004801c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180048021  lea     rcx, [rbp+170h+var_1E8]; this
0x180048025  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18004802a  lea     rcx, [rbp+170h+var_1D0]
0x18004802e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180048033  mov     edi, r15d
0x180048036  lea     rcx, [rsp+270h+var_208]
0x18004803b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048040  mov     eax, edi
0x180048042  mov     rcx, [rbp+170h+var_30]
0x180048049  xor     rcx, rsp; StackCookie
0x18004804c  call    __security_check_cookie
0x180048051  lea     r11, [rsp+270h+var_20]
0x180048059  mov     rbx, [r11+40h]
0x18004805d  mov     rsi, [r11+48h]
0x180048061  mov     rsp, r11
0x180048064  pop     r15
0x180048066  pop     r14
0x180048068  pop     r12
0x18004806a  pop     rdi
0x18004806b  pop     rbp
0x18004806c  retn
```
