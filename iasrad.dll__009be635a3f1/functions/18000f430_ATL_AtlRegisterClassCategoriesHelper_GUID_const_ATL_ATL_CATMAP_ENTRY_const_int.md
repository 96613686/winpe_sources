# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000f430`
- end: `0x18000f774`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `836`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010fec`
- `0x180011094`
- `0x180011c54`

## callees

- `0x180009b30`
- `0x18000adb0`
- `0x18000dc24`
- `0x18000f0c0`
- `0x18000f430`
- `0x18000fa64`
- `0x18000fffc`
- `0x180010818`
- `0x18002e230`
- `0x180030010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000f564`
- `msvcrt!wcscpy_s` at `0x18000f65f`
- `msvcrt!wcscpy_s` at `0x18000f564`
- `msvcrt!wcscpy_s` at `0x18000f65f`
- `msvcrt!wcscat_s` at `0x18000f57e`
- `msvcrt!wcscat_s` at `0x18000f598`
- `msvcrt!wcscat_s` at `0x18000f67a`
- `msvcrt!wcscat_s` at `0x18000f695`
- `msvcrt!wcscat_s` at `0x18000f57e`
- `msvcrt!wcscat_s` at `0x18000f598`
- `msvcrt!wcscat_s` at `0x18000f67a`
- `msvcrt!wcscat_s` at `0x18000f695`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000f623`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000f6f4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000f623`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000f6f4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f548`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f548`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f4b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f4b8`

## string_xrefs

- `0x18000f559`: `CLSID\`
- `0x18000f651`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  int v10; // ecx
  errno_t v11; // eax
  errno_t v12; // eax
  errno_t v13; // eax
  HKEY v14; // rdi
  LSTATUS v15; // ebx
  errno_t v16; // eax
  errno_t v17; // eax
  errno_t v18; // eax
  LSTATUS v19; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v24[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v26 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( 1 )
    {
      v10 = *(_DWORD *)v4;
      if ( !*(_DWORD *)v4 )
        break;
      v26 = *(_OWORD *)*((_QWORD *)v4 + 1);
      if ( a3 )
      {
        v6 = *(_QWORD *)ppv;
        if ( v10 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v26);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v26);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_27;
      }
      else
      {
        v9 = *(_QWORD *)ppv;
        if ( v10 == 1 )
          (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v9 + 48))(ppv, rguid, 1, &v26);
        else
          (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v9 + 64))(ppv, rguid, 1, &v26);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v25 = 0;
      v11 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v11);
      v12 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v12);
      v13 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v13);
      v14 = HKEY_CLASSES_ROOT;
      v24[1] = 0;
      v24[0] = 0xFFFFFFFF80000000uLL;
      v24[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
      {
        v15 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v15 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, Destination);
          v14 = (HKEY)v24[0];
        }
      }
      v16 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v16);
      v17 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v17);
      v18 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v18);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v14, Destination, 0x20019u) )
      {
        v19 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v19 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v24);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v25);
    }
  }
  v8 = 0;
LABEL_27:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x18000f430  mov     [rsp-8+arg_10], rbx
0x18000f435  mov     [rsp-8+arg_18], rsi
0x18000f43a  push    rbp
0x18000f43b  push    rdi
0x18000f43c  push    r12
0x18000f43e  push    r14
0x18000f440  push    r15
0x18000f442  lea     rbp, [rsp-150h]
0x18000f44a  sub     rsp, 250h
0x18000f451  mov     rax, cs:__security_cookie
0x18000f458  xor     rax, rsp
0x18000f45b  mov     [rbp+170h+var_30], rax
0x18000f462  xor     r15d, r15d
0x18000f465  xorps   xmm0, xmm0
0x18000f468  mov     [rsp+270h+var_208], r15
0x18000f46d  mov     r14d, r8d
0x18000f470  mov     rbx, rdx
0x18000f473  mov     rsi, rcx
0x18000f476  movups  [rbp+170h+var_1C8], xmm0
0x18000f47a  test    rdx, rdx
0x18000f47d  jz      loc_18000F73A
0x18000f483  lea     rdx, GUID_NULL
0x18000f48a  call    InlineIsEqualGUID
0x18000f48f  test    eax, eax
0x18000f491  jnz     loc_18000F73A
0x18000f497  lea     rax, [rsp+270h+var_208]
0x18000f49c  xor     edx, edx; pUnkOuter
0x18000f49e  lea     r12d, [r15+1]
0x18000f4a2  mov     [rsp+270h+ppv], rax; ppv
0x18000f4a7  mov     r8d, r12d; dwClsContext
0x18000f4aa  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000f4b1  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000f4b8  call    cs:__imp_CoCreateInstance
0x18000f4be  test    eax, eax
0x18000f4c0  js      loc_18000F73A
0x18000f4c6  jmp     short loc_18000F52B
0x18000f4c8  mov     rax, [rbx+8]
0x18000f4cc  lea     r9, [rbp+170h+var_1C8]
0x18000f4d0  mov     r8d, r12d
0x18000f4d3  mov     rdx, rsi
0x18000f4d6  movups  xmm0, xmmword ptr [rax]
0x18000f4d9  movdqu  [rbp+170h+var_1C8], xmm0
0x18000f4de  test    r14d, r14d
0x18000f4e1  jz      short loc_18000F50B
0x18000f4e3  cmp     ecx, r12d
0x18000f4e6  mov     rcx, [rsp+270h+var_208]
0x18000f4eb  mov     rax, [rcx]
0x18000f4ee  jnz     short loc_18000F4F6
0x18000f4f0  mov     rax, [rax+28h]
0x18000f4f4  jmp     short loc_18000F4FA
0x18000f4f6  mov     rax, [rax+38h]
0x18000f4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ff  mov     edi, eax
0x18000f501  test    eax, eax
0x18000f503  js      loc_18000F73D
0x18000f509  jmp     short loc_18000F527
0x18000f50b  cmp     ecx, r12d
0x18000f50e  mov     rcx, [rsp+270h+var_208]
0x18000f513  mov     rax, [rcx]
0x18000f516  jnz     short loc_18000F51E
0x18000f518  mov     rax, [rax+30h]
0x18000f51c  jmp     short loc_18000F522
0x18000f51e  mov     rax, [rax+40h]
0x18000f522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f527  add     rbx, 10h
0x18000f52b  mov     ecx, [rbx]
0x18000f52d  test    ecx, ecx
0x18000f52f  jnz     short loc_18000F4C8
0x18000f531  test    r14d, r14d
0x18000f534  jnz     loc_18000F73A
0x18000f53a  lea     r8d, [rcx+40h]; cchMax
0x18000f53e  mov     rcx, rsi; rguid
0x18000f541  lea     rdx, [rbp+170h+sz]; lpsz
0x18000f548  call    cs:__imp_StringFromGUID2
0x18000f54e  mov     esi, 80h
0x18000f553  mov     [rbp+170h+var_1D0], r15
0x18000f557  mov     edx, esi; SizeInWords
0x18000f559  lea     r8, aClsid; "CLSID\\"
0x18000f560  lea     rcx, [rbp+170h+Destination]; Destination
0x18000f564  call    cs:__imp_wcscpy_s
0x18000f56a  mov     ecx, eax; int
0x18000f56c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000f571  lea     r8, [rbp+170h+sz]; Source
0x18000f578  mov     edx, esi; SizeInWords
0x18000f57a  lea     rcx, [rbp+170h+Destination]; Destination
0x18000f57e  call    cs:__imp_wcscat_s
0x18000f584  mov     ecx, eax; int
0x18000f586  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000f58b  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000f592  mov     edx, esi; SizeInWords
0x18000f594  lea     rcx, [rbp+170h+Destination]; Destination
0x18000f598  call    cs:__imp_wcscat_s
0x18000f59e  mov     ecx, eax; int
0x18000f5a0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000f5a5  mov     rdi, 0FFFFFFFF80000000h
0x18000f5ac  mov     [rbp+170h+var_1E0], r15
0x18000f5b0  mov     r14d, 20019h
0x18000f5b6  mov     [rbp+170h+var_1E8], rdi
0x18000f5ba  mov     r9d, r14d; unsigned int
0x18000f5bd  mov     [rbp+170h+var_1D8], r15
0x18000f5c1  mov     rdx, rdi; hKey
0x18000f5c4  mov     [rsp+270h+hKey], r15
0x18000f5c9  lea     r8, [rbp+170h+Destination]; lpSubKey
0x18000f5cd  mov     [rsp+270h+var_1F8], r15
0x18000f5d2  lea     rcx, [rsp+270h+hKey]; this
0x18000f5d7  mov     [rbp+170h+var_1F0], r15
0x18000f5db  mov     [rsp+270h+cSubKeys], r15d
0x18000f5e0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000f5e5  test    eax, eax
0x18000f5e7  jnz     short loc_18000F651
0x18000f5e9  mov     rcx, [rsp+270h+hKey]; hKey
0x18000f5ee  lea     rax, [rsp+270h+cSubKeys]
0x18000f5f3  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000f5f8  xor     r9d, r9d; lpReserved
0x18000f5fb  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000f600  xor     r8d, r8d; lpcchClass
0x18000f603  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000f608  xor     edx, edx; lpClass
0x18000f60a  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000f60f  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18000f614  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000f619  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000f61e  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18000f623  call    cs:__imp_RegQueryInfoKeyW
0x18000f629  lea     rcx, [rsp+270h+hKey]; this
0x18000f62e  mov     ebx, eax
0x18000f630  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f635  test    ebx, ebx
0x18000f637  jnz     short loc_18000F651
0x18000f639  cmp     [rsp+270h+cSubKeys], r15d
0x18000f63e  jnz     short loc_18000F651
0x18000f640  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x18000f644  lea     rcx, [rbp+170h+var_1E8]; this
0x18000f648  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000f64d  mov     rdi, [rbp+170h+var_1E8]
0x18000f651  lea     r8, aClsid; "CLSID\\"
0x18000f658  mov     rdx, rsi; SizeInWords
0x18000f65b  lea     rcx, [rbp+170h+Destination]; Destination
0x18000f65f  call    cs:__imp_wcscpy_s
0x18000f665  mov     ecx, eax; int
0x18000f667  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000f66c  lea     r8, [rbp+170h+sz]; Source
0x18000f673  mov     rdx, rsi; SizeInWords
0x18000f676  lea     rcx, [rbp+170h+Destination]; Destination
0x18000f67a  call    cs:__imp_wcscat_s
0x18000f680  mov     ecx, eax; int
0x18000f682  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000f687  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000f68e  mov     rdx, rsi; SizeInWords
0x18000f691  lea     rcx, [rbp+170h+Destination]; Destination
0x18000f695  call    cs:__imp_wcscat_s
0x18000f69b  mov     ecx, eax; int
0x18000f69d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000f6a2  mov     r9d, r14d; unsigned int
0x18000f6a5  lea     r8, [rbp+170h+Destination]; lpSubKey
0x18000f6a9  mov     rdx, rdi; hKey
0x18000f6ac  lea     rcx, [rsp+270h+hKey]; this
0x18000f6b1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000f6b6  test    eax, eax
0x18000f6b8  jnz     short loc_18000F71E
0x18000f6ba  mov     rcx, [rsp+270h+hKey]; hKey
0x18000f6bf  lea     rax, [rsp+270h+cSubKeys]
0x18000f6c4  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000f6c9  xor     r9d, r9d; lpReserved
0x18000f6cc  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000f6d1  xor     r8d, r8d; lpcchClass
0x18000f6d4  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000f6d9  xor     edx, edx; lpClass
0x18000f6db  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000f6e0  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18000f6e5  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000f6ea  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000f6ef  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18000f6f4  call    cs:__imp_RegQueryInfoKeyW
0x18000f6fa  lea     rcx, [rsp+270h+hKey]; this
0x18000f6ff  mov     ebx, eax
0x18000f701  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f706  test    ebx, ebx
0x18000f708  jnz     short loc_18000F71E
0x18000f70a  cmp     [rsp+270h+cSubKeys], r15d
0x18000f70f  jnz     short loc_18000F71E
0x18000f711  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x18000f715  lea     rcx, [rbp+170h+var_1E8]; this
0x18000f719  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000f71e  lea     rcx, [rsp+270h+hKey]; this
0x18000f723  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f728  lea     rcx, [rbp+170h+var_1E8]; this
0x18000f72c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f731  lea     rcx, [rbp+170h+var_1D0]
0x18000f735  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000f73a  mov     edi, r15d
0x18000f73d  lea     rcx, [rsp+270h+var_208]
0x18000f742  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f747  mov     eax, edi
0x18000f749  mov     rcx, [rbp+170h+var_30]
0x18000f750  xor     rcx, rsp; StackCookie
0x18000f753  call    __security_check_cookie
0x18000f758  lea     r11, [rsp+270h+var_20]
0x18000f760  mov     rbx, [r11+40h]
0x18000f764  mov     rsi, [r11+48h]
0x18000f768  mov     rsp, r11
0x18000f76b  pop     r15
0x18000f76d  pop     r14
0x18000f76f  pop     r12
0x18000f771  pop     rdi
0x18000f772  pop     rbp
0x18000f773  retn
```
