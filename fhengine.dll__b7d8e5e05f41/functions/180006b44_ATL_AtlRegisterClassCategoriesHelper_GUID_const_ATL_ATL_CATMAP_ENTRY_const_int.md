# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180006b44`
- end: `0x180006e7f`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800070c4`
- `0x180007294`

## callees

- `0x180002f64`
- `0x1800031b0`
- `0x180004184`
- `0x180004464`
- `0x180004d4c`
- `0x180004f58`
- `0x18000517c`
- `0x180006b44`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180006c89`
- `msvcrt!wcscat_s` at `0x180006ca3`
- `msvcrt!wcscat_s` at `0x180006d85`
- `msvcrt!wcscat_s` at `0x180006da0`
- `msvcrt!wcscat_s` at `0x180006c89`
- `msvcrt!wcscat_s` at `0x180006ca3`
- `msvcrt!wcscat_s` at `0x180006d85`
- `msvcrt!wcscat_s` at `0x180006da0`
- `msvcrt!wcscpy_s` at `0x180006c6f`
- `msvcrt!wcscpy_s` at `0x180006d6a`
- `msvcrt!wcscpy_s` at `0x180006c6f`
- `msvcrt!wcscpy_s` at `0x180006d6a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006d2e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006dff`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006d2e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006dff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006bcc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006bcc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006c53`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006c53`

## string_xrefs

- `0x180006c64`: `CLSID\`
- `0x180006d5c`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
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
  ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x180006b44  mov     [rsp-8+arg_10], rbx
0x180006b49  mov     [rsp-8+arg_18], rsi
0x180006b4e  push    rbp
0x180006b4f  push    rdi
0x180006b50  push    r12
0x180006b52  push    r14
0x180006b54  push    r15
0x180006b56  lea     rbp, [rsp-150h]
0x180006b5e  sub     rsp, 250h
0x180006b65  mov     rax, cs:__security_cookie
0x180006b6c  xor     rax, rsp
0x180006b6f  mov     [rbp+170h+var_30], rax
0x180006b76  xor     r15d, r15d
0x180006b79  xorps   xmm0, xmm0
0x180006b7c  mov     [rsp+270h+var_208], r15
0x180006b81  mov     r14d, r8d
0x180006b84  mov     rbx, rdx
0x180006b87  mov     rsi, rcx
0x180006b8a  movups  [rbp+170h+var_1C8], xmm0
0x180006b8e  test    rdx, rdx
0x180006b91  jz      loc_180006E45
0x180006b97  lea     rdx, GUID_NULL; struct _GUID *
0x180006b9e  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180006ba3  test    eax, eax
0x180006ba5  jnz     loc_180006E45
0x180006bab  lea     rax, [rsp+270h+var_208]
0x180006bb0  xor     edx, edx; pUnkOuter
0x180006bb2  lea     r12d, [r15+1]
0x180006bb6  mov     [rsp+270h+ppv], rax; ppv
0x180006bbb  mov     r8d, r12d; dwClsContext
0x180006bbe  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180006bc5  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180006bcc  call    cs:__imp_CoCreateInstance
0x180006bd2  test    eax, eax
0x180006bd4  js      loc_180006E45
0x180006bda  cmp     [rbx], r15d
0x180006bdd  jz      short loc_180006C3C
0x180006bdf  mov     rax, [rbx+8]
0x180006be3  lea     r9, [rbp+170h+var_1C8]
0x180006be7  mov     rcx, [rsp+270h+var_208]
0x180006bec  mov     r8d, r12d
0x180006bef  mov     rdx, rsi
0x180006bf2  movups  xmm0, xmmword ptr [rax]
0x180006bf5  movdqu  [rbp+170h+var_1C8], xmm0
0x180006bfa  mov     rax, [rcx]
0x180006bfd  test    r14d, r14d
0x180006c00  jz      short loc_180006C22
0x180006c02  cmp     [rbx], r12d
0x180006c05  jnz     short loc_180006C0D
0x180006c07  mov     rax, [rax+28h]
0x180006c0b  jmp     short loc_180006C11
0x180006c0d  mov     rax, [rax+38h]
0x180006c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c16  mov     edi, eax
0x180006c18  test    eax, eax
0x180006c1a  js      loc_180006E48
0x180006c20  jmp     short loc_180006C36
0x180006c22  cmp     [rbx], r12d
0x180006c25  jnz     short loc_180006C2D
0x180006c27  mov     rax, [rax+30h]
0x180006c2b  jmp     short loc_180006C31
0x180006c2d  mov     rax, [rax+40h]
0x180006c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c36  add     rbx, 10h
0x180006c3a  jmp     short loc_180006BDA
0x180006c3c  test    r14d, r14d
0x180006c3f  jnz     loc_180006E45
0x180006c45  lea     r8d, [r14+40h]; cchMax
0x180006c49  mov     rcx, rsi; rguid
0x180006c4c  lea     rdx, [rbp+170h+sz]; lpsz
0x180006c53  call    cs:__imp_StringFromGUID2
0x180006c59  mov     esi, 80h
0x180006c5e  mov     [rbp+170h+var_1D0], r15
0x180006c62  mov     edx, esi; SizeInWords
0x180006c64  lea     r8, aClsid; "CLSID\\"
0x180006c6b  lea     rcx, [rbp+170h+Destination]; Destination
0x180006c6f  call    cs:__imp_wcscpy_s
0x180006c75  mov     ecx, eax; int
0x180006c77  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006c7c  lea     r8, [rbp+170h+sz]; Source
0x180006c83  mov     edx, esi; SizeInWords
0x180006c85  lea     rcx, [rbp+170h+Destination]; Destination
0x180006c89  call    cs:__imp_wcscat_s
0x180006c8f  mov     ecx, eax; int
0x180006c91  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006c96  lea     r8, aRequiredCatego; "\\Required Categories"
0x180006c9d  mov     edx, esi; SizeInWords
0x180006c9f  lea     rcx, [rbp+170h+Destination]; Destination
0x180006ca3  call    cs:__imp_wcscat_s
0x180006ca9  mov     ecx, eax; int
0x180006cab  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006cb0  mov     rdi, 0FFFFFFFF80000000h
0x180006cb7  mov     [rbp+170h+var_1E0], r15
0x180006cbb  mov     r14d, 20019h
0x180006cc1  mov     [rbp+170h+var_1E8], rdi
0x180006cc5  mov     r9d, r14d; unsigned int
0x180006cc8  mov     [rbp+170h+var_1D8], r15
0x180006ccc  mov     rdx, rdi; hKey
0x180006ccf  mov     [rsp+270h+hKey], r15
0x180006cd4  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180006cd8  mov     [rsp+270h+var_1F8], r15
0x180006cdd  lea     rcx, [rsp+270h+hKey]; this
0x180006ce2  mov     [rbp+170h+var_1F0], r15
0x180006ce6  mov     [rsp+270h+cSubKeys], r15d
0x180006ceb  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180006cf0  test    eax, eax
0x180006cf2  jnz     short loc_180006D5C
0x180006cf4  mov     rcx, [rsp+270h+hKey]; hKey
0x180006cf9  lea     rax, [rsp+270h+cSubKeys]
0x180006cfe  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180006d03  xor     r9d, r9d; lpReserved
0x180006d06  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180006d0b  xor     r8d, r8d; lpcchClass
0x180006d0e  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180006d13  xor     edx, edx; lpClass
0x180006d15  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180006d1a  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180006d1f  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180006d24  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180006d29  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180006d2e  call    cs:__imp_RegQueryInfoKeyW
0x180006d34  lea     rcx, [rsp+270h+hKey]; this
0x180006d39  mov     ebx, eax
0x180006d3b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006d40  test    ebx, ebx
0x180006d42  jnz     short loc_180006D5C
0x180006d44  cmp     [rsp+270h+cSubKeys], r15d
0x180006d49  jnz     short loc_180006D5C
0x180006d4b  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180006d4f  lea     rcx, [rbp+170h+var_1E8]; this
0x180006d53  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180006d58  mov     rdi, [rbp+170h+var_1E8]
0x180006d5c  lea     r8, aClsid; "CLSID\\"
0x180006d63  mov     rdx, rsi; SizeInWords
0x180006d66  lea     rcx, [rbp+170h+Destination]; Destination
0x180006d6a  call    cs:__imp_wcscpy_s
0x180006d70  mov     ecx, eax; int
0x180006d72  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006d77  lea     r8, [rbp+170h+sz]; Source
0x180006d7e  mov     rdx, rsi; SizeInWords
0x180006d81  lea     rcx, [rbp+170h+Destination]; Destination
0x180006d85  call    cs:__imp_wcscat_s
0x180006d8b  mov     ecx, eax; int
0x180006d8d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006d92  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180006d99  mov     rdx, rsi; SizeInWords
0x180006d9c  lea     rcx, [rbp+170h+Destination]; Destination
0x180006da0  call    cs:__imp_wcscat_s
0x180006da6  mov     ecx, eax; int
0x180006da8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006dad  mov     r9d, r14d; unsigned int
0x180006db0  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180006db4  mov     rdx, rdi; hKey
0x180006db7  lea     rcx, [rsp+270h+hKey]; this
0x180006dbc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180006dc1  test    eax, eax
0x180006dc3  jnz     short loc_180006E29
0x180006dc5  mov     rcx, [rsp+270h+hKey]; hKey
0x180006dca  lea     rax, [rsp+270h+cSubKeys]
0x180006dcf  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180006dd4  xor     r9d, r9d; lpReserved
0x180006dd7  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180006ddc  xor     r8d, r8d; lpcchClass
0x180006ddf  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180006de4  xor     edx, edx; lpClass
0x180006de6  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180006deb  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180006df0  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180006df5  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180006dfa  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180006dff  call    cs:__imp_RegQueryInfoKeyW
0x180006e05  lea     rcx, [rsp+270h+hKey]; this
0x180006e0a  mov     ebx, eax
0x180006e0c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006e11  test    ebx, ebx
0x180006e13  jnz     short loc_180006E29
0x180006e15  cmp     [rsp+270h+cSubKeys], r15d
0x180006e1a  jnz     short loc_180006E29
0x180006e1c  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180006e20  lea     rcx, [rbp+170h+var_1E8]; this
0x180006e24  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180006e29  lea     rcx, [rsp+270h+hKey]; this
0x180006e2e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006e33  lea     rcx, [rbp+170h+var_1E8]; this
0x180006e37  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006e3c  lea     rcx, [rbp+170h+var_1D0]
0x180006e40  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006e45  mov     edi, r15d
0x180006e48  lea     rcx, [rsp+270h+var_208]
0x180006e4d  call    ??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)
0x180006e52  mov     eax, edi
0x180006e54  mov     rcx, [rbp+170h+var_30]
0x180006e5b  xor     rcx, rsp; StackCookie
0x180006e5e  call    __security_check_cookie
0x180006e63  lea     r11, [rsp+270h+var_20]
0x180006e6b  mov     rbx, [r11+40h]
0x180006e6f  mov     rsi, [r11+48h]
0x180006e73  mov     rsp, r11
0x180006e76  pop     r15
0x180006e78  pop     r14
0x180006e7a  pop     r12
0x180006e7c  pop     rdi
0x180006e7d  pop     rbp
0x180006e7e  retn
```
