# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180006d40`
- end: `0x18000706f`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `815`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007604`
- `0x1800077a4`

## callees

- `0x180003134`
- `0x180004a74`
- `0x18000694c`
- `0x180006b34`
- `0x180006d40`
- `0x1800071c8`
- `0x1800071f4`
- `0x1800075a4`
- `0x180037620`
- `0x180039010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180006e85`
- `msvcrt!wcscat_s` at `0x180006e9f`
- `msvcrt!wcscat_s` at `0x180006f78`
- `msvcrt!wcscat_s` at `0x180006f93`
- `msvcrt!wcscat_s` at `0x180006e85`
- `msvcrt!wcscat_s` at `0x180006e9f`
- `msvcrt!wcscat_s` at `0x180006f78`
- `msvcrt!wcscat_s` at `0x180006f93`
- `msvcrt!wcscpy_s` at `0x180006e6b`
- `msvcrt!wcscpy_s` at `0x180006f5d`
- `msvcrt!wcscpy_s` at `0x180006e6b`
- `msvcrt!wcscpy_s` at `0x180006f5d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006f21`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006fef`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006f21`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006fef`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006e4f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006e4f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006dc8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006dc8`

## string_xrefs

- `0x180006e60`: `CLSID\`
- `0x180006f4f`: `CLSID\`

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
  unsigned int v13; // r9d
  LSTATUS v14; // ebx
  errno_t v15; // eax
  errno_t v16; // eax
  errno_t v17; // eax
  unsigned int v18; // r9d
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
    while ( *(_DWORD *)v4 )
    {
      v26 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v26);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v26);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v26);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v26);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v25 = 0;
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v24[1] = 0;
      v24[0] = 0xFFFFFFFF80000000uLL;
      v24[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, v13) )
      {
        v14 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v14 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, Destination);
          v12 = (HKEY)v24[0];
        }
      }
      v15 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v15);
      v16 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v16);
      v17 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v17);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, Destination, v18) )
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
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x180006d40  mov     [rsp-8+arg_10], rbx
0x180006d45  mov     [rsp-8+arg_18], rsi
0x180006d4a  push    rbp
0x180006d4b  push    rdi
0x180006d4c  push    r12
0x180006d4e  push    r14
0x180006d50  push    r15
0x180006d52  lea     rbp, [rsp-150h]
0x180006d5a  sub     rsp, 250h
0x180006d61  mov     rax, cs:__security_cookie
0x180006d68  xor     rax, rsp
0x180006d6b  mov     [rbp+170h+var_30], rax
0x180006d72  xor     r15d, r15d
0x180006d75  xorps   xmm0, xmm0
0x180006d78  mov     [rsp+270h+var_208], r15
0x180006d7d  mov     r14d, r8d
0x180006d80  mov     rbx, rdx
0x180006d83  mov     rsi, rcx
0x180006d86  movups  [rbp+170h+var_1C8], xmm0
0x180006d8a  test    rdx, rdx
0x180006d8d  jz      loc_180007035
0x180006d93  lea     rdx, GUID_NULL; struct _GUID *
0x180006d9a  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180006d9f  test    eax, eax
0x180006da1  jnz     loc_180007035
0x180006da7  lea     rax, [rsp+270h+var_208]
0x180006dac  xor     edx, edx; pUnkOuter
0x180006dae  lea     r12d, [r15+1]
0x180006db2  mov     [rsp+270h+ppv], rax; ppv
0x180006db7  mov     r8d, r12d; dwClsContext
0x180006dba  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180006dc1  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180006dc8  call    cs:__imp_CoCreateInstance
0x180006dce  test    eax, eax
0x180006dd0  js      loc_180007035
0x180006dd6  cmp     [rbx], r15d
0x180006dd9  jz      short loc_180006E38
0x180006ddb  mov     rax, [rbx+8]
0x180006ddf  lea     r9, [rbp+170h+var_1C8]
0x180006de3  mov     rcx, [rsp+270h+var_208]
0x180006de8  mov     r8d, r12d
0x180006deb  mov     rdx, rsi
0x180006dee  movups  xmm0, xmmword ptr [rax]
0x180006df1  movdqu  [rbp+170h+var_1C8], xmm0
0x180006df6  mov     rax, [rcx]
0x180006df9  test    r14d, r14d
0x180006dfc  jz      short loc_180006E1E
0x180006dfe  cmp     [rbx], r12d
0x180006e01  jnz     short loc_180006E09
0x180006e03  mov     rax, [rax+28h]
0x180006e07  jmp     short loc_180006E0D
0x180006e09  mov     rax, [rax+38h]
0x180006e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e12  mov     edi, eax
0x180006e14  test    eax, eax
0x180006e16  js      loc_180007038
0x180006e1c  jmp     short loc_180006E32
0x180006e1e  cmp     [rbx], r12d
0x180006e21  jnz     short loc_180006E29
0x180006e23  mov     rax, [rax+30h]
0x180006e27  jmp     short loc_180006E2D
0x180006e29  mov     rax, [rax+40h]
0x180006e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e32  add     rbx, 10h
0x180006e36  jmp     short loc_180006DD6
0x180006e38  test    r14d, r14d
0x180006e3b  jnz     loc_180007035
0x180006e41  lea     r8d, [r14+40h]; cchMax
0x180006e45  mov     rcx, rsi; rguid
0x180006e48  lea     rdx, [rbp+170h+sz]; lpsz
0x180006e4f  call    cs:__imp_StringFromGUID2
0x180006e55  mov     esi, 80h
0x180006e5a  mov     [rbp+170h+var_1D0], r15
0x180006e5e  mov     edx, esi; SizeInWords
0x180006e60  lea     r8, aClsid; "CLSID\\"
0x180006e67  lea     rcx, [rbp+170h+Destination]; Destination
0x180006e6b  call    cs:__imp_wcscpy_s
0x180006e71  mov     ecx, eax; int
0x180006e73  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006e78  lea     r8, [rbp+170h+sz]; Source
0x180006e7f  mov     edx, esi; SizeInWords
0x180006e81  lea     rcx, [rbp+170h+Destination]; Destination
0x180006e85  call    cs:__imp_wcscat_s
0x180006e8b  mov     ecx, eax; int
0x180006e8d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006e92  lea     r8, aRequiredCatego; "\\Required Categories"
0x180006e99  mov     edx, esi; SizeInWords
0x180006e9b  lea     rcx, [rbp+170h+Destination]; Destination
0x180006e9f  call    cs:__imp_wcscat_s
0x180006ea5  mov     ecx, eax; int
0x180006ea7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006eac  mov     rdi, 0FFFFFFFF80000000h
0x180006eb3  mov     [rbp+170h+var_1E0], r15
0x180006eb7  mov     rdx, rdi; hKey
0x180006eba  mov     [rbp+170h+var_1E8], rdi
0x180006ebe  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180006ec2  mov     [rbp+170h+var_1D8], r15
0x180006ec6  lea     rcx, [rsp+270h+hKey]; this
0x180006ecb  mov     [rsp+270h+hKey], r15
0x180006ed0  mov     [rsp+270h+var_1F8], r15
0x180006ed5  mov     [rbp+170h+var_1F0], r15
0x180006ed9  mov     [rsp+270h+cSubKeys], r15d
0x180006ede  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180006ee3  test    eax, eax
0x180006ee5  jnz     short loc_180006F4F
0x180006ee7  mov     rcx, [rsp+270h+hKey]; hKey
0x180006eec  lea     rax, [rsp+270h+cSubKeys]
0x180006ef1  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180006ef6  xor     r9d, r9d; lpReserved
0x180006ef9  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180006efe  xor     r8d, r8d; lpcchClass
0x180006f01  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180006f06  xor     edx, edx; lpClass
0x180006f08  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180006f0d  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180006f12  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180006f17  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180006f1c  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180006f21  call    cs:__imp_RegQueryInfoKeyW
0x180006f27  lea     rcx, [rsp+270h+hKey]; this
0x180006f2c  mov     ebx, eax
0x180006f2e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006f33  test    ebx, ebx
0x180006f35  jnz     short loc_180006F4F
0x180006f37  cmp     [rsp+270h+cSubKeys], r15d
0x180006f3c  jnz     short loc_180006F4F
0x180006f3e  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180006f42  lea     rcx, [rbp+170h+var_1E8]; this
0x180006f46  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180006f4b  mov     rdi, [rbp+170h+var_1E8]
0x180006f4f  lea     r8, aClsid; "CLSID\\"
0x180006f56  mov     rdx, rsi; SizeInWords
0x180006f59  lea     rcx, [rbp+170h+Destination]; Destination
0x180006f5d  call    cs:__imp_wcscpy_s
0x180006f63  mov     ecx, eax; int
0x180006f65  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006f6a  lea     r8, [rbp+170h+sz]; Source
0x180006f71  mov     rdx, rsi; SizeInWords
0x180006f74  lea     rcx, [rbp+170h+Destination]; Destination
0x180006f78  call    cs:__imp_wcscat_s
0x180006f7e  mov     ecx, eax; int
0x180006f80  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006f85  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180006f8c  mov     rdx, rsi; SizeInWords
0x180006f8f  lea     rcx, [rbp+170h+Destination]; Destination
0x180006f93  call    cs:__imp_wcscat_s
0x180006f99  mov     ecx, eax; int
0x180006f9b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006fa0  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180006fa4  mov     rdx, rdi; hKey
0x180006fa7  lea     rcx, [rsp+270h+hKey]; this
0x180006fac  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180006fb1  test    eax, eax
0x180006fb3  jnz     short loc_180007019
0x180006fb5  mov     rcx, [rsp+270h+hKey]; hKey
0x180006fba  lea     rax, [rsp+270h+cSubKeys]
0x180006fbf  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180006fc4  xor     r9d, r9d; lpReserved
0x180006fc7  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180006fcc  xor     r8d, r8d; lpcchClass
0x180006fcf  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180006fd4  xor     edx, edx; lpClass
0x180006fd6  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180006fdb  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180006fe0  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180006fe5  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180006fea  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180006fef  call    cs:__imp_RegQueryInfoKeyW
0x180006ff5  lea     rcx, [rsp+270h+hKey]; this
0x180006ffa  mov     ebx, eax
0x180006ffc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007001  test    ebx, ebx
0x180007003  jnz     short loc_180007019
0x180007005  cmp     [rsp+270h+cSubKeys], r15d
0x18000700a  jnz     short loc_180007019
0x18000700c  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180007010  lea     rcx, [rbp+170h+var_1E8]; this
0x180007014  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180007019  lea     rcx, [rsp+270h+hKey]; this
0x18000701e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007023  lea     rcx, [rbp+170h+var_1E8]; this
0x180007027  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000702c  lea     rcx, [rbp+170h+var_1D0]
0x180007030  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180007035  mov     edi, r15d
0x180007038  lea     rcx, [rsp+270h+var_208]
0x18000703d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007042  mov     eax, edi
0x180007044  mov     rcx, [rbp+170h+var_30]
0x18000704b  xor     rcx, rsp; StackCookie
0x18000704e  call    __security_check_cookie
0x180007053  lea     r11, [rsp+270h+var_20]
0x18000705b  mov     rbx, [r11+40h]
0x18000705f  mov     rsi, [r11+48h]
0x180007063  mov     rsp, r11
0x180007066  pop     r15
0x180007068  pop     r14
0x18000706a  pop     r12
0x18000706c  pop     rdi
0x18000706d  pop     rbp
0x18000706e  retn
```
