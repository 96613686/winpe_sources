# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180004860`
- end: `0x180004ba4`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `836`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007cfc`
- `0x180007da4`
- `0x180008a0c`

## callees

- `0x180002b00`
- `0x1800030b8`
- `0x180004430`
- `0x180004860`
- `0x180004f44`
- `0x1800063fc`
- `0x18000747c`
- `0x18000a138`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800049ae`
- `msvcrt!wcscat_s` at `0x1800049c8`
- `msvcrt!wcscat_s` at `0x180004aaa`
- `msvcrt!wcscat_s` at `0x180004ac5`
- `msvcrt!wcscat_s` at `0x1800049ae`
- `msvcrt!wcscat_s` at `0x1800049c8`
- `msvcrt!wcscat_s` at `0x180004aaa`
- `msvcrt!wcscat_s` at `0x180004ac5`
- `msvcrt!wcscpy_s` at `0x180004994`
- `msvcrt!wcscpy_s` at `0x180004a8f`
- `msvcrt!wcscpy_s` at `0x180004994`
- `msvcrt!wcscpy_s` at `0x180004a8f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004a53`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004b24`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004a53`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004b24`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800048e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800048e8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004978`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004978`

## string_xrefs

- `0x180004989`: `CLSID\`
- `0x180004a81`: `CLSID\`

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
0x180004860  mov     [rsp-8+arg_10], rbx
0x180004865  mov     [rsp-8+arg_18], rsi
0x18000486a  push    rbp
0x18000486b  push    rdi
0x18000486c  push    r12
0x18000486e  push    r14
0x180004870  push    r15
0x180004872  lea     rbp, [rsp-150h]
0x18000487a  sub     rsp, 250h
0x180004881  mov     rax, cs:__security_cookie
0x180004888  xor     rax, rsp
0x18000488b  mov     [rbp+170h+var_30], rax
0x180004892  xor     r15d, r15d
0x180004895  xorps   xmm0, xmm0
0x180004898  mov     [rsp+270h+var_208], r15
0x18000489d  mov     r14d, r8d
0x1800048a0  mov     rbx, rdx
0x1800048a3  mov     rsi, rcx
0x1800048a6  movups  [rbp+170h+var_1C8], xmm0
0x1800048aa  test    rdx, rdx
0x1800048ad  jz      loc_180004B6A
0x1800048b3  lea     rdx, GUID_NULL
0x1800048ba  call    InlineIsEqualGUID
0x1800048bf  test    eax, eax
0x1800048c1  jnz     loc_180004B6A
0x1800048c7  lea     rax, [rsp+270h+var_208]
0x1800048cc  xor     edx, edx; pUnkOuter
0x1800048ce  lea     r12d, [r15+1]
0x1800048d2  mov     [rsp+270h+ppv], rax; ppv
0x1800048d7  mov     r8d, r12d; dwClsContext
0x1800048da  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800048e1  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800048e8  call    cs:__imp_CoCreateInstance
0x1800048ee  test    eax, eax
0x1800048f0  js      loc_180004B6A
0x1800048f6  jmp     short loc_18000495B
0x1800048f8  mov     rax, [rbx+8]
0x1800048fc  lea     r9, [rbp+170h+var_1C8]
0x180004900  mov     r8d, r12d
0x180004903  mov     rdx, rsi
0x180004906  movups  xmm0, xmmword ptr [rax]
0x180004909  movdqu  [rbp+170h+var_1C8], xmm0
0x18000490e  test    r14d, r14d
0x180004911  jz      short loc_18000493B
0x180004913  cmp     ecx, r12d
0x180004916  mov     rcx, [rsp+270h+var_208]
0x18000491b  mov     rax, [rcx]
0x18000491e  jnz     short loc_180004926
0x180004920  mov     rax, [rax+28h]
0x180004924  jmp     short loc_18000492A
0x180004926  mov     rax, [rax+38h]
0x18000492a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492f  mov     edi, eax
0x180004931  test    eax, eax
0x180004933  js      loc_180004B6D
0x180004939  jmp     short loc_180004957
0x18000493b  cmp     ecx, r12d
0x18000493e  mov     rcx, [rsp+270h+var_208]
0x180004943  mov     rax, [rcx]
0x180004946  jnz     short loc_18000494E
0x180004948  mov     rax, [rax+30h]
0x18000494c  jmp     short loc_180004952
0x18000494e  mov     rax, [rax+40h]
0x180004952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004957  add     rbx, 10h
0x18000495b  mov     ecx, [rbx]
0x18000495d  test    ecx, ecx
0x18000495f  jnz     short loc_1800048F8
0x180004961  test    r14d, r14d
0x180004964  jnz     loc_180004B6A
0x18000496a  lea     r8d, [rcx+40h]; cchMax
0x18000496e  mov     rcx, rsi; rguid
0x180004971  lea     rdx, [rbp+170h+sz]; lpsz
0x180004978  call    cs:__imp_StringFromGUID2
0x18000497e  mov     esi, 80h
0x180004983  mov     [rbp+170h+var_1D0], r15
0x180004987  mov     edx, esi; SizeInWords
0x180004989  lea     r8, aClsid; "CLSID\\"
0x180004990  lea     rcx, [rbp+170h+Destination]; Destination
0x180004994  call    cs:__imp_wcscpy_s
0x18000499a  mov     ecx, eax; int
0x18000499c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800049a1  lea     r8, [rbp+170h+sz]; Source
0x1800049a8  mov     edx, esi; SizeInWords
0x1800049aa  lea     rcx, [rbp+170h+Destination]; Destination
0x1800049ae  call    cs:__imp_wcscat_s
0x1800049b4  mov     ecx, eax; int
0x1800049b6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800049bb  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800049c2  mov     edx, esi; SizeInWords
0x1800049c4  lea     rcx, [rbp+170h+Destination]; Destination
0x1800049c8  call    cs:__imp_wcscat_s
0x1800049ce  mov     ecx, eax; int
0x1800049d0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800049d5  mov     rdi, 0FFFFFFFF80000000h
0x1800049dc  mov     [rbp+170h+var_1E0], r15
0x1800049e0  mov     r14d, 20019h
0x1800049e6  mov     [rbp+170h+var_1E8], rdi
0x1800049ea  mov     r9d, r14d; unsigned int
0x1800049ed  mov     [rbp+170h+var_1D8], r15
0x1800049f1  mov     rdx, rdi; hKey
0x1800049f4  mov     [rsp+270h+hKey], r15
0x1800049f9  lea     r8, [rbp+170h+Destination]; lpSubKey
0x1800049fd  mov     [rsp+270h+var_1F8], r15
0x180004a02  lea     rcx, [rsp+270h+hKey]; this
0x180004a07  mov     [rbp+170h+var_1F0], r15
0x180004a0b  mov     [rsp+270h+cSubKeys], r15d
0x180004a10  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180004a15  test    eax, eax
0x180004a17  jnz     short loc_180004A81
0x180004a19  mov     rcx, [rsp+270h+hKey]; hKey
0x180004a1e  lea     rax, [rsp+270h+cSubKeys]
0x180004a23  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180004a28  xor     r9d, r9d; lpReserved
0x180004a2b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180004a30  xor     r8d, r8d; lpcchClass
0x180004a33  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180004a38  xor     edx, edx; lpClass
0x180004a3a  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180004a3f  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180004a44  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180004a49  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180004a4e  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180004a53  call    cs:__imp_RegQueryInfoKeyW
0x180004a59  lea     rcx, [rsp+270h+hKey]; this
0x180004a5e  mov     ebx, eax
0x180004a60  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004a65  test    ebx, ebx
0x180004a67  jnz     short loc_180004A81
0x180004a69  cmp     [rsp+270h+cSubKeys], r15d
0x180004a6e  jnz     short loc_180004A81
0x180004a70  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180004a74  lea     rcx, [rbp+170h+var_1E8]; this
0x180004a78  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004a7d  mov     rdi, [rbp+170h+var_1E8]
0x180004a81  lea     r8, aClsid; "CLSID\\"
0x180004a88  mov     rdx, rsi; SizeInWords
0x180004a8b  lea     rcx, [rbp+170h+Destination]; Destination
0x180004a8f  call    cs:__imp_wcscpy_s
0x180004a95  mov     ecx, eax; int
0x180004a97  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180004a9c  lea     r8, [rbp+170h+sz]; Source
0x180004aa3  mov     rdx, rsi; SizeInWords
0x180004aa6  lea     rcx, [rbp+170h+Destination]; Destination
0x180004aaa  call    cs:__imp_wcscat_s
0x180004ab0  mov     ecx, eax; int
0x180004ab2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180004ab7  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180004abe  mov     rdx, rsi; SizeInWords
0x180004ac1  lea     rcx, [rbp+170h+Destination]; Destination
0x180004ac5  call    cs:__imp_wcscat_s
0x180004acb  mov     ecx, eax; int
0x180004acd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180004ad2  mov     r9d, r14d; unsigned int
0x180004ad5  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180004ad9  mov     rdx, rdi; hKey
0x180004adc  lea     rcx, [rsp+270h+hKey]; this
0x180004ae1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180004ae6  test    eax, eax
0x180004ae8  jnz     short loc_180004B4E
0x180004aea  mov     rcx, [rsp+270h+hKey]; hKey
0x180004aef  lea     rax, [rsp+270h+cSubKeys]
0x180004af4  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180004af9  xor     r9d, r9d; lpReserved
0x180004afc  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180004b01  xor     r8d, r8d; lpcchClass
0x180004b04  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180004b09  xor     edx, edx; lpClass
0x180004b0b  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180004b10  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180004b15  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180004b1a  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180004b1f  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180004b24  call    cs:__imp_RegQueryInfoKeyW
0x180004b2a  lea     rcx, [rsp+270h+hKey]; this
0x180004b2f  mov     ebx, eax
0x180004b31  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004b36  test    ebx, ebx
0x180004b38  jnz     short loc_180004B4E
0x180004b3a  cmp     [rsp+270h+cSubKeys], r15d
0x180004b3f  jnz     short loc_180004B4E
0x180004b41  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180004b45  lea     rcx, [rbp+170h+var_1E8]; this
0x180004b49  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004b4e  lea     rcx, [rsp+270h+hKey]; this
0x180004b53  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004b58  lea     rcx, [rbp+170h+var_1E8]; this
0x180004b5c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004b61  lea     rcx, [rbp+170h+var_1D0]
0x180004b65  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180004b6a  mov     edi, r15d
0x180004b6d  lea     rcx, [rsp+270h+var_208]
0x180004b72  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004b77  mov     eax, edi
0x180004b79  mov     rcx, [rbp+170h+var_30]
0x180004b80  xor     rcx, rsp; StackCookie
0x180004b83  call    __security_check_cookie
0x180004b88  lea     r11, [rsp+270h+var_20]
0x180004b90  mov     rbx, [r11+40h]
0x180004b94  mov     rsi, [r11+48h]
0x180004b98  mov     rsp, r11
0x180004b9b  pop     r15
0x180004b9d  pop     r14
0x180004b9f  pop     r12
0x180004ba1  pop     rdi
0x180004ba2  pop     rbp
0x180004ba3  retn
```
