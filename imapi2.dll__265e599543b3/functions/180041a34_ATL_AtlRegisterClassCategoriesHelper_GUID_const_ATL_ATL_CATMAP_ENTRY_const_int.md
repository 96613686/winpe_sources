# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180041a34`
- end: `0x180041d6f`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004203c`
- `0x1800420e4`

## callees

- `0x180006d40`
- `0x18000ea20`
- `0x180011024`
- `0x180011ac4`
- `0x180011c94`
- `0x180011e84`
- `0x1800128c0`
- `0x180041a34`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180041b79`
- `msvcrt!wcscat_s` at `0x180041b93`
- `msvcrt!wcscat_s` at `0x180041c75`
- `msvcrt!wcscat_s` at `0x180041c90`
- `msvcrt!wcscat_s` at `0x180041b79`
- `msvcrt!wcscat_s` at `0x180041b93`
- `msvcrt!wcscat_s` at `0x180041c75`
- `msvcrt!wcscat_s` at `0x180041c90`
- `msvcrt!wcscpy_s` at `0x180041b5f`
- `msvcrt!wcscpy_s` at `0x180041c5a`
- `msvcrt!wcscpy_s` at `0x180041b5f`
- `msvcrt!wcscpy_s` at `0x180041c5a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180041c1e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180041cef`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180041c1e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180041cef`
- `ole32!CoCreateInstance` at `0x180041abc`
- `ole32!CoCreateInstance` at `0x180041abc`
- `ole32!StringFromGUID2` at `0x180041b43`
- `ole32!StringFromGUID2` at `0x180041b43`

## string_xrefs

- `0x180041b54`: `CLSID\`
- `0x180041c4c`: `CLSID\`

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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180041a34  mov     [rsp-8+arg_10], rbx
0x180041a39  mov     [rsp-8+arg_18], rsi
0x180041a3e  push    rbp
0x180041a3f  push    rdi
0x180041a40  push    r12
0x180041a42  push    r14
0x180041a44  push    r15
0x180041a46  lea     rbp, [rsp-150h]
0x180041a4e  sub     rsp, 250h
0x180041a55  mov     rax, cs:__security_cookie
0x180041a5c  xor     rax, rsp
0x180041a5f  mov     [rbp+170h+var_30], rax
0x180041a66  xor     r15d, r15d
0x180041a69  xorps   xmm0, xmm0
0x180041a6c  mov     [rsp+270h+var_208], r15
0x180041a71  mov     r14d, r8d
0x180041a74  mov     rbx, rdx
0x180041a77  mov     rsi, rcx
0x180041a7a  movups  [rbp+170h+var_1C8], xmm0
0x180041a7e  test    rdx, rdx
0x180041a81  jz      loc_180041D35
0x180041a87  lea     rdx, GUID_NULL; struct _GUID *
0x180041a8e  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180041a93  test    eax, eax
0x180041a95  jnz     loc_180041D35
0x180041a9b  lea     rax, [rsp+270h+var_208]
0x180041aa0  xor     edx, edx; pUnkOuter
0x180041aa2  lea     r12d, [r15+1]
0x180041aa6  mov     [rsp+270h+ppv], rax; ppv
0x180041aab  mov     r8d, r12d; dwClsContext
0x180041aae  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180041ab5  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180041abc  call    cs:__imp_CoCreateInstance
0x180041ac2  test    eax, eax
0x180041ac4  js      loc_180041D35
0x180041aca  cmp     [rbx], r15d
0x180041acd  jz      short loc_180041B2C
0x180041acf  mov     rax, [rbx+8]
0x180041ad3  lea     r9, [rbp+170h+var_1C8]
0x180041ad7  mov     rcx, [rsp+270h+var_208]
0x180041adc  mov     r8d, r12d
0x180041adf  mov     rdx, rsi
0x180041ae2  movups  xmm0, xmmword ptr [rax]
0x180041ae5  movdqu  [rbp+170h+var_1C8], xmm0
0x180041aea  mov     rax, [rcx]
0x180041aed  test    r14d, r14d
0x180041af0  jz      short loc_180041B12
0x180041af2  cmp     [rbx], r12d
0x180041af5  jnz     short loc_180041AFD
0x180041af7  mov     rax, [rax+28h]
0x180041afb  jmp     short loc_180041B01
0x180041afd  mov     rax, [rax+38h]
0x180041b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b06  mov     edi, eax
0x180041b08  test    eax, eax
0x180041b0a  js      loc_180041D38
0x180041b10  jmp     short loc_180041B26
0x180041b12  cmp     [rbx], r12d
0x180041b15  jnz     short loc_180041B1D
0x180041b17  mov     rax, [rax+30h]
0x180041b1b  jmp     short loc_180041B21
0x180041b1d  mov     rax, [rax+40h]
0x180041b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b26  add     rbx, 10h
0x180041b2a  jmp     short loc_180041ACA
0x180041b2c  test    r14d, r14d
0x180041b2f  jnz     loc_180041D35
0x180041b35  lea     r8d, [r14+40h]; cchMax
0x180041b39  mov     rcx, rsi; rguid
0x180041b3c  lea     rdx, [rbp+170h+sz]; lpsz
0x180041b43  call    cs:__imp_StringFromGUID2
0x180041b49  mov     esi, 80h
0x180041b4e  mov     [rbp+170h+var_1D0], r15
0x180041b52  mov     edx, esi; SizeInWords
0x180041b54  lea     r8, aClsid; "CLSID\\"
0x180041b5b  lea     rcx, [rbp+170h+Destination]; Destination
0x180041b5f  call    cs:__imp_wcscpy_s
0x180041b65  mov     ecx, eax; int
0x180041b67  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180041b6c  lea     r8, [rbp+170h+sz]; Source
0x180041b73  mov     edx, esi; SizeInWords
0x180041b75  lea     rcx, [rbp+170h+Destination]; Destination
0x180041b79  call    cs:__imp_wcscat_s
0x180041b7f  mov     ecx, eax; int
0x180041b81  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180041b86  lea     r8, aRequiredCatego; "\\Required Categories"
0x180041b8d  mov     edx, esi; SizeInWords
0x180041b8f  lea     rcx, [rbp+170h+Destination]; Destination
0x180041b93  call    cs:__imp_wcscat_s
0x180041b99  mov     ecx, eax; int
0x180041b9b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180041ba0  mov     rdi, 0FFFFFFFF80000000h
0x180041ba7  mov     [rbp+170h+var_1E0], r15
0x180041bab  mov     r14d, 20019h
0x180041bb1  mov     [rbp+170h+var_1E8], rdi
0x180041bb5  mov     r9d, r14d; unsigned int
0x180041bb8  mov     [rbp+170h+var_1D8], r15
0x180041bbc  mov     rdx, rdi; hKey
0x180041bbf  mov     [rsp+270h+hKey], r15
0x180041bc4  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180041bc8  mov     [rsp+270h+var_1F8], r15
0x180041bcd  lea     rcx, [rsp+270h+hKey]; this
0x180041bd2  mov     [rbp+170h+var_1F0], r15
0x180041bd6  mov     [rsp+270h+cSubKeys], r15d
0x180041bdb  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180041be0  test    eax, eax
0x180041be2  jnz     short loc_180041C4C
0x180041be4  mov     rcx, [rsp+270h+hKey]; hKey
0x180041be9  lea     rax, [rsp+270h+cSubKeys]
0x180041bee  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180041bf3  xor     r9d, r9d; lpReserved
0x180041bf6  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180041bfb  xor     r8d, r8d; lpcchClass
0x180041bfe  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180041c03  xor     edx, edx; lpClass
0x180041c05  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180041c0a  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180041c0f  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180041c14  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180041c19  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180041c1e  call    cs:__imp_RegQueryInfoKeyW
0x180041c24  lea     rcx, [rsp+270h+hKey]; this
0x180041c29  mov     ebx, eax
0x180041c2b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180041c30  test    ebx, ebx
0x180041c32  jnz     short loc_180041C4C
0x180041c34  cmp     [rsp+270h+cSubKeys], r15d
0x180041c39  jnz     short loc_180041C4C
0x180041c3b  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180041c3f  lea     rcx, [rbp+170h+var_1E8]; this
0x180041c43  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180041c48  mov     rdi, [rbp+170h+var_1E8]
0x180041c4c  lea     r8, aClsid; "CLSID\\"
0x180041c53  mov     rdx, rsi; SizeInWords
0x180041c56  lea     rcx, [rbp+170h+Destination]; Destination
0x180041c5a  call    cs:__imp_wcscpy_s
0x180041c60  mov     ecx, eax; int
0x180041c62  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180041c67  lea     r8, [rbp+170h+sz]; Source
0x180041c6e  mov     rdx, rsi; SizeInWords
0x180041c71  lea     rcx, [rbp+170h+Destination]; Destination
0x180041c75  call    cs:__imp_wcscat_s
0x180041c7b  mov     ecx, eax; int
0x180041c7d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180041c82  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180041c89  mov     rdx, rsi; SizeInWords
0x180041c8c  lea     rcx, [rbp+170h+Destination]; Destination
0x180041c90  call    cs:__imp_wcscat_s
0x180041c96  mov     ecx, eax; int
0x180041c98  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180041c9d  mov     r9d, r14d; unsigned int
0x180041ca0  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180041ca4  mov     rdx, rdi; hKey
0x180041ca7  lea     rcx, [rsp+270h+hKey]; this
0x180041cac  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180041cb1  test    eax, eax
0x180041cb3  jnz     short loc_180041D19
0x180041cb5  mov     rcx, [rsp+270h+hKey]; hKey
0x180041cba  lea     rax, [rsp+270h+cSubKeys]
0x180041cbf  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180041cc4  xor     r9d, r9d; lpReserved
0x180041cc7  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180041ccc  xor     r8d, r8d; lpcchClass
0x180041ccf  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180041cd4  xor     edx, edx; lpClass
0x180041cd6  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180041cdb  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180041ce0  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180041ce5  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180041cea  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180041cef  call    cs:__imp_RegQueryInfoKeyW
0x180041cf5  lea     rcx, [rsp+270h+hKey]; this
0x180041cfa  mov     ebx, eax
0x180041cfc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180041d01  test    ebx, ebx
0x180041d03  jnz     short loc_180041D19
0x180041d05  cmp     [rsp+270h+cSubKeys], r15d
0x180041d0a  jnz     short loc_180041D19
0x180041d0c  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180041d10  lea     rcx, [rbp+170h+var_1E8]; this
0x180041d14  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180041d19  lea     rcx, [rsp+270h+hKey]; this
0x180041d1e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180041d23  lea     rcx, [rbp+170h+var_1E8]; this
0x180041d27  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180041d2c  lea     rcx, [rbp+170h+var_1D0]
0x180041d30  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180041d35  mov     edi, r15d
0x180041d38  lea     rcx, [rsp+270h+var_208]
0x180041d3d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180041d42  mov     eax, edi
0x180041d44  mov     rcx, [rbp+170h+var_30]
0x180041d4b  xor     rcx, rsp; StackCookie
0x180041d4e  call    __security_check_cookie
0x180041d53  lea     r11, [rsp+270h+var_20]
0x180041d5b  mov     rbx, [r11+40h]
0x180041d5f  mov     rsi, [r11+48h]
0x180041d63  mov     rsp, r11
0x180041d66  pop     r15
0x180041d68  pop     r14
0x180041d6a  pop     r12
0x180041d6c  pop     rdi
0x180041d6d  pop     rbp
0x180041d6e  retn
```
