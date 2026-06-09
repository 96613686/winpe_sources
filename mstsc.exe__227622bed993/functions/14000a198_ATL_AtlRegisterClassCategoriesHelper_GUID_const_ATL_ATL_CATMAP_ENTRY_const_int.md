# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x14000a198`
- end: `0x14000a4d3`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000be64`
- `0x14000cacc`

## callees

- `0x1400095c0`
- `0x1400095f0`
- `0x140009f74`
- `0x14000a198`
- `0x14000a830`
- `0x14000aa34`
- `0x14000b04c`
- `0x14000cf40`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x14000a2c3`
- `msvcrt!wcscpy_s` at `0x14000a3be`
- `msvcrt!wcscpy_s` at `0x14000a2c3`
- `msvcrt!wcscpy_s` at `0x14000a3be`
- `msvcrt!wcscat_s` at `0x14000a2dd`
- `msvcrt!wcscat_s` at `0x14000a2f7`
- `msvcrt!wcscat_s` at `0x14000a3d9`
- `msvcrt!wcscat_s` at `0x14000a3f4`
- `msvcrt!wcscat_s` at `0x14000a2dd`
- `msvcrt!wcscat_s` at `0x14000a2f7`
- `msvcrt!wcscat_s` at `0x14000a3d9`
- `msvcrt!wcscat_s` at `0x14000a3f4`
- `ole32!StringFromGUID2` at `0x14000a2a7`
- `ole32!StringFromGUID2` at `0x14000a2a7`
- `ole32!CoCreateInstance` at `0x14000a220`
- `ole32!CoCreateInstance` at `0x14000a220`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000a382`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000a453`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000a382`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000a453`

## string_xrefs

- `0x14000a2b8`: `CLSID\`
- `0x14000a3b0`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(
        GUID *rguid,
        const struct ATL::_ATL_CATMAP_ENTRY *a2,
        __int64 a3)
{
  int v3; // r14d
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  errno_t v9; // eax
  errno_t v10; // eax
  errno_t v11; // eax
  HKEY v12; // rdi
  LSTATUS v13; // ebx
  errno_t v14; // eax
  errno_t v15; // eax
  errno_t v16; // eax
  LSTATUS v17; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v3 = a3;
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
      if ( v3 )
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
    if ( !v3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v23 = 0;
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v22[1] = 0;
      v22[0] = 0xFFFFFFFF80000000uLL;
      v22[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
          v12 = (HKEY)v22[0];
        }
      }
      v14 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v14);
      v15 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v15);
      v16 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v16);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, Destination, 0x20019u) )
      {
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v22);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v23);
    }
  }
  v8 = 0;
LABEL_26:
  wil::com_ptr_t<IProgressDialog,wil::err_returncode_policy>::~com_ptr_t<IProgressDialog,wil::err_returncode_policy>(
    &ppv,
    a2,
    a3);
  return v8;
}

```

## disassembly

```asm
0x14000a198  mov     [rsp-8+arg_10], rbx
0x14000a19d  mov     [rsp-8+arg_18], rsi
0x14000a1a2  push    rbp
0x14000a1a3  push    rdi
0x14000a1a4  push    r12
0x14000a1a6  push    r14
0x14000a1a8  push    r15
0x14000a1aa  lea     rbp, [rsp-150h]
0x14000a1b2  sub     rsp, 250h
0x14000a1b9  mov     rax, cs:__security_cookie
0x14000a1c0  xor     rax, rsp
0x14000a1c3  mov     [rbp+170h+var_30], rax
0x14000a1ca  xor     r15d, r15d
0x14000a1cd  xorps   xmm0, xmm0
0x14000a1d0  mov     [rsp+270h+var_208], r15
0x14000a1d5  mov     r14d, r8d
0x14000a1d8  mov     rbx, rdx
0x14000a1db  mov     rsi, rcx
0x14000a1de  movups  [rbp+170h+var_1C8], xmm0
0x14000a1e2  test    rdx, rdx
0x14000a1e5  jz      loc_14000A499
0x14000a1eb  lea     rdx, GUID_NULL
0x14000a1f2  call    InlineIsEqualGUID
0x14000a1f7  test    eax, eax
0x14000a1f9  jnz     loc_14000A499
0x14000a1ff  lea     rax, [rsp+270h+var_208]
0x14000a204  xor     edx, edx; pUnkOuter
0x14000a206  lea     r12d, [r15+1]
0x14000a20a  mov     [rsp+270h+ppv], rax; ppv
0x14000a20f  mov     r8d, r12d; dwClsContext
0x14000a212  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x14000a219  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x14000a220  call    cs:__imp_CoCreateInstance
0x14000a226  test    eax, eax
0x14000a228  js      loc_14000A499
0x14000a22e  cmp     [rbx], r15d
0x14000a231  jz      short loc_14000A290
0x14000a233  mov     rax, [rbx+8]
0x14000a237  lea     r9, [rbp+170h+var_1C8]
0x14000a23b  mov     rcx, [rsp+270h+var_208]
0x14000a240  mov     r8d, r12d
0x14000a243  mov     rdx, rsi
0x14000a246  movups  xmm0, xmmword ptr [rax]
0x14000a249  movdqu  [rbp+170h+var_1C8], xmm0
0x14000a24e  mov     rax, [rcx]
0x14000a251  test    r14d, r14d
0x14000a254  jz      short loc_14000A276
0x14000a256  cmp     [rbx], r12d
0x14000a259  jnz     short loc_14000A261
0x14000a25b  mov     rax, [rax+28h]
0x14000a25f  jmp     short loc_14000A265
0x14000a261  mov     rax, [rax+38h]
0x14000a265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a26a  mov     edi, eax
0x14000a26c  test    eax, eax
0x14000a26e  js      loc_14000A49C
0x14000a274  jmp     short loc_14000A28A
0x14000a276  cmp     [rbx], r12d
0x14000a279  jnz     short loc_14000A281
0x14000a27b  mov     rax, [rax+30h]
0x14000a27f  jmp     short loc_14000A285
0x14000a281  mov     rax, [rax+40h]
0x14000a285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a28a  add     rbx, 10h
0x14000a28e  jmp     short loc_14000A22E
0x14000a290  test    r14d, r14d
0x14000a293  jnz     loc_14000A499
0x14000a299  lea     r8d, [r14+40h]; cchMax
0x14000a29d  mov     rcx, rsi; rguid
0x14000a2a0  lea     rdx, [rbp+170h+sz]; lpsz
0x14000a2a7  call    cs:__imp_StringFromGUID2
0x14000a2ad  mov     esi, 80h
0x14000a2b2  mov     [rbp+170h+var_1D0], r15
0x14000a2b6  mov     edx, esi; SizeInWords
0x14000a2b8  lea     r8, aClsid; "CLSID\\"
0x14000a2bf  lea     rcx, [rbp+170h+Destination]; Destination
0x14000a2c3  call    cs:__imp_wcscpy_s
0x14000a2c9  mov     ecx, eax; int
0x14000a2cb  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000a2d0  lea     r8, [rbp+170h+sz]; Source
0x14000a2d7  mov     edx, esi; SizeInWords
0x14000a2d9  lea     rcx, [rbp+170h+Destination]; Destination
0x14000a2dd  call    cs:__imp_wcscat_s
0x14000a2e3  mov     ecx, eax; int
0x14000a2e5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000a2ea  lea     r8, aRequiredCatego; "\\Required Categories"
0x14000a2f1  mov     edx, esi; SizeInWords
0x14000a2f3  lea     rcx, [rbp+170h+Destination]; Destination
0x14000a2f7  call    cs:__imp_wcscat_s
0x14000a2fd  mov     ecx, eax; int
0x14000a2ff  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000a304  mov     rdi, 0FFFFFFFF80000000h
0x14000a30b  mov     [rbp+170h+var_1E0], r15
0x14000a30f  mov     r14d, 20019h
0x14000a315  mov     [rbp+170h+var_1E8], rdi
0x14000a319  mov     r9d, r14d; unsigned int
0x14000a31c  mov     [rbp+170h+var_1D8], r15
0x14000a320  mov     rdx, rdi; hKey
0x14000a323  mov     [rsp+270h+hKey], r15
0x14000a328  lea     r8, [rbp+170h+Destination]; lpSubKey
0x14000a32c  mov     [rsp+270h+var_1F8], r15
0x14000a331  lea     rcx, [rsp+270h+hKey]; this
0x14000a336  mov     [rbp+170h+var_1F0], r15
0x14000a33a  mov     [rsp+270h+cSubKeys], r15d
0x14000a33f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000a344  test    eax, eax
0x14000a346  jnz     short loc_14000A3B0
0x14000a348  mov     rcx, [rsp+270h+hKey]; hKey
0x14000a34d  lea     rax, [rsp+270h+cSubKeys]
0x14000a352  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14000a357  xor     r9d, r9d; lpReserved
0x14000a35a  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14000a35f  xor     r8d, r8d; lpcchClass
0x14000a362  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x14000a367  xor     edx, edx; lpClass
0x14000a369  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x14000a36e  mov     [rsp+270h+lpcValues], r15; lpcValues
0x14000a373  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x14000a378  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x14000a37d  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x14000a382  call    cs:__imp_RegQueryInfoKeyW
0x14000a388  lea     rcx, [rsp+270h+hKey]; this
0x14000a38d  mov     ebx, eax
0x14000a38f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000a394  test    ebx, ebx
0x14000a396  jnz     short loc_14000A3B0
0x14000a398  cmp     [rsp+270h+cSubKeys], r15d
0x14000a39d  jnz     short loc_14000A3B0
0x14000a39f  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x14000a3a3  lea     rcx, [rbp+170h+var_1E8]; this
0x14000a3a7  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x14000a3ac  mov     rdi, [rbp+170h+var_1E8]
0x14000a3b0  lea     r8, aClsid; "CLSID\\"
0x14000a3b7  mov     rdx, rsi; SizeInWords
0x14000a3ba  lea     rcx, [rbp+170h+Destination]; Destination
0x14000a3be  call    cs:__imp_wcscpy_s
0x14000a3c4  mov     ecx, eax; int
0x14000a3c6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000a3cb  lea     r8, [rbp+170h+sz]; Source
0x14000a3d2  mov     rdx, rsi; SizeInWords
0x14000a3d5  lea     rcx, [rbp+170h+Destination]; Destination
0x14000a3d9  call    cs:__imp_wcscat_s
0x14000a3df  mov     ecx, eax; int
0x14000a3e1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000a3e6  lea     r8, aImplementedCat; "\\Implemented Categories"
0x14000a3ed  mov     rdx, rsi; SizeInWords
0x14000a3f0  lea     rcx, [rbp+170h+Destination]; Destination
0x14000a3f4  call    cs:__imp_wcscat_s
0x14000a3fa  mov     ecx, eax; int
0x14000a3fc  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000a401  mov     r9d, r14d; unsigned int
0x14000a404  lea     r8, [rbp+170h+Destination]; lpSubKey
0x14000a408  mov     rdx, rdi; hKey
0x14000a40b  lea     rcx, [rsp+270h+hKey]; this
0x14000a410  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000a415  test    eax, eax
0x14000a417  jnz     short loc_14000A47D
0x14000a419  mov     rcx, [rsp+270h+hKey]; hKey
0x14000a41e  lea     rax, [rsp+270h+cSubKeys]
0x14000a423  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14000a428  xor     r9d, r9d; lpReserved
0x14000a42b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14000a430  xor     r8d, r8d; lpcchClass
0x14000a433  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x14000a438  xor     edx, edx; lpClass
0x14000a43a  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x14000a43f  mov     [rsp+270h+lpcValues], r15; lpcValues
0x14000a444  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x14000a449  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x14000a44e  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x14000a453  call    cs:__imp_RegQueryInfoKeyW
0x14000a459  lea     rcx, [rsp+270h+hKey]; this
0x14000a45e  mov     ebx, eax
0x14000a460  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000a465  test    ebx, ebx
0x14000a467  jnz     short loc_14000A47D
0x14000a469  cmp     [rsp+270h+cSubKeys], r15d
0x14000a46e  jnz     short loc_14000A47D
0x14000a470  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x14000a474  lea     rcx, [rbp+170h+var_1E8]; this
0x14000a478  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x14000a47d  lea     rcx, [rsp+270h+hKey]; this
0x14000a482  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000a487  lea     rcx, [rbp+170h+var_1E8]; this
0x14000a48b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000a490  lea     rcx, [rbp+170h+var_1D0]
0x14000a494  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14000a499  mov     edi, r15d
0x14000a49c  lea     rcx, [rsp+270h+var_208]
0x14000a4a1  call    ??1?$com_ptr_t@UIProgressDialog@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IProgressDialog,wil::err_returncode_policy>::~com_ptr_t<IProgressDialog,wil::err_returncode_policy>(void)
0x14000a4a6  mov     eax, edi
0x14000a4a8  mov     rcx, [rbp+170h+var_30]
0x14000a4af  xor     rcx, rsp; StackCookie
0x14000a4b2  call    __security_check_cookie
0x14000a4b7  lea     r11, [rsp+270h+var_20]
0x14000a4bf  mov     rbx, [r11+40h]
0x14000a4c3  mov     rsi, [r11+48h]
0x14000a4c7  mov     rsp, r11
0x14000a4ca  pop     r15
0x14000a4cc  pop     r14
0x14000a4ce  pop     r12
0x14000a4d0  pop     rdi
0x14000a4d1  pop     rbp
0x14000a4d2  retn
```
