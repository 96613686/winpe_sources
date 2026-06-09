# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180007214`
- end: `0x18000754f`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e100`
- `0x18000f2d4`
- `0x180010520`
- `0x1800105c0`

## callees

- `0x180004078`
- `0x18000503c`
- `0x180006f14`
- `0x180007214`
- `0x180007b44`
- `0x18000c05c`
- `0x18000c9f4`
- `0x180010654`
- `0x18002f3b0`
- `0x180030010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180007359`
- `msvcrt!wcscat_s` at `0x180007373`
- `msvcrt!wcscat_s` at `0x180007455`
- `msvcrt!wcscat_s` at `0x180007470`
- `msvcrt!wcscat_s` at `0x180007359`
- `msvcrt!wcscat_s` at `0x180007373`
- `msvcrt!wcscat_s` at `0x180007455`
- `msvcrt!wcscat_s` at `0x180007470`
- `msvcrt!wcscpy_s` at `0x18000733f`
- `msvcrt!wcscpy_s` at `0x18000743a`
- `msvcrt!wcscpy_s` at `0x18000733f`
- `msvcrt!wcscpy_s` at `0x18000743a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800073fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800074cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800073fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800074cf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000729c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000729c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180007323`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180007323`

## string_xrefs

- `0x180007334`: `CLSID\`
- `0x18000742c`: `CLSID\`

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
  _QWORD *v23; // [rsp+A0h] [rbp-60h] BYREF
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
  ATL::CComPtrBase<ITypeLib>::~CComPtrBase<ITypeLib>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x180007214  mov     [rsp-8+arg_10], rbx
0x180007219  mov     [rsp-8+arg_18], rsi
0x18000721e  push    rbp
0x18000721f  push    rdi
0x180007220  push    r12
0x180007222  push    r14
0x180007224  push    r15
0x180007226  lea     rbp, [rsp-150h]
0x18000722e  sub     rsp, 250h
0x180007235  mov     rax, cs:__security_cookie
0x18000723c  xor     rax, rsp
0x18000723f  mov     [rbp+170h+var_30], rax
0x180007246  xor     r15d, r15d
0x180007249  xorps   xmm0, xmm0
0x18000724c  mov     [rsp+270h+var_208], r15
0x180007251  mov     r14d, r8d
0x180007254  mov     rbx, rdx
0x180007257  mov     rsi, rcx
0x18000725a  movups  [rbp+170h+var_1C8], xmm0
0x18000725e  test    rdx, rdx
0x180007261  jz      loc_180007515
0x180007267  lea     rdx, GUID_NULL
0x18000726e  call    InlineIsEqualGUID
0x180007273  test    eax, eax
0x180007275  jnz     loc_180007515
0x18000727b  lea     rax, [rsp+270h+var_208]
0x180007280  xor     edx, edx; pUnkOuter
0x180007282  lea     r12d, [r15+1]
0x180007286  mov     [rsp+270h+ppv], rax; ppv
0x18000728b  mov     r8d, r12d; dwClsContext
0x18000728e  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180007295  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000729c  call    cs:__imp_CoCreateInstance
0x1800072a2  test    eax, eax
0x1800072a4  js      loc_180007515
0x1800072aa  cmp     [rbx], r15d
0x1800072ad  jz      short loc_18000730C
0x1800072af  mov     rax, [rbx+8]
0x1800072b3  lea     r9, [rbp+170h+var_1C8]
0x1800072b7  mov     rcx, [rsp+270h+var_208]
0x1800072bc  mov     r8d, r12d
0x1800072bf  mov     rdx, rsi
0x1800072c2  movups  xmm0, xmmword ptr [rax]
0x1800072c5  movdqu  [rbp+170h+var_1C8], xmm0
0x1800072ca  mov     rax, [rcx]
0x1800072cd  test    r14d, r14d
0x1800072d0  jz      short loc_1800072F2
0x1800072d2  cmp     [rbx], r12d
0x1800072d5  jnz     short loc_1800072DD
0x1800072d7  mov     rax, [rax+28h]
0x1800072db  jmp     short loc_1800072E1
0x1800072dd  mov     rax, [rax+38h]
0x1800072e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e6  mov     edi, eax
0x1800072e8  test    eax, eax
0x1800072ea  js      loc_180007518
0x1800072f0  jmp     short loc_180007306
0x1800072f2  cmp     [rbx], r12d
0x1800072f5  jnz     short loc_1800072FD
0x1800072f7  mov     rax, [rax+30h]
0x1800072fb  jmp     short loc_180007301
0x1800072fd  mov     rax, [rax+40h]
0x180007301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007306  add     rbx, 10h
0x18000730a  jmp     short loc_1800072AA
0x18000730c  test    r14d, r14d
0x18000730f  jnz     loc_180007515
0x180007315  lea     r8d, [r14+40h]; cchMax
0x180007319  mov     rcx, rsi; rguid
0x18000731c  lea     rdx, [rbp+170h+sz]; lpsz
0x180007323  call    cs:__imp_StringFromGUID2
0x180007329  mov     esi, 80h
0x18000732e  mov     [rbp+170h+var_1D0], r15
0x180007332  mov     edx, esi; SizeInWords
0x180007334  lea     r8, aClsid; "CLSID\\"
0x18000733b  lea     rcx, [rbp+170h+Destination]; Destination
0x18000733f  call    cs:__imp_wcscpy_s
0x180007345  mov     ecx, eax; int
0x180007347  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000734c  lea     r8, [rbp+170h+sz]; Source
0x180007353  mov     edx, esi; SizeInWords
0x180007355  lea     rcx, [rbp+170h+Destination]; Destination
0x180007359  call    cs:__imp_wcscat_s
0x18000735f  mov     ecx, eax; int
0x180007361  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007366  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000736d  mov     edx, esi; SizeInWords
0x18000736f  lea     rcx, [rbp+170h+Destination]; Destination
0x180007373  call    cs:__imp_wcscat_s
0x180007379  mov     ecx, eax; int
0x18000737b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007380  mov     rdi, 0FFFFFFFF80000000h
0x180007387  mov     [rbp+170h+var_1E0], r15
0x18000738b  mov     r14d, 20019h
0x180007391  mov     [rbp+170h+var_1E8], rdi
0x180007395  mov     r9d, r14d; unsigned int
0x180007398  mov     [rbp+170h+var_1D8], r15
0x18000739c  mov     rdx, rdi; hKey
0x18000739f  mov     [rsp+270h+hKey], r15
0x1800073a4  lea     r8, [rbp+170h+Destination]; lpSubKey
0x1800073a8  mov     [rsp+270h+var_1F8], r15
0x1800073ad  lea     rcx, [rsp+270h+hKey]; this
0x1800073b2  mov     [rbp+170h+var_1F0], r15
0x1800073b6  mov     [rsp+270h+cSubKeys], r15d
0x1800073bb  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800073c0  test    eax, eax
0x1800073c2  jnz     short loc_18000742C
0x1800073c4  mov     rcx, [rsp+270h+hKey]; hKey
0x1800073c9  lea     rax, [rsp+270h+cSubKeys]
0x1800073ce  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800073d3  xor     r9d, r9d; lpReserved
0x1800073d6  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800073db  xor     r8d, r8d; lpcchClass
0x1800073de  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800073e3  xor     edx, edx; lpClass
0x1800073e5  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800073ea  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800073ef  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800073f4  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800073f9  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800073fe  call    cs:__imp_RegQueryInfoKeyW
0x180007404  lea     rcx, [rsp+270h+hKey]; this
0x180007409  mov     ebx, eax
0x18000740b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007410  test    ebx, ebx
0x180007412  jnz     short loc_18000742C
0x180007414  cmp     [rsp+270h+cSubKeys], r15d
0x180007419  jnz     short loc_18000742C
0x18000741b  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x18000741f  lea     rcx, [rbp+170h+var_1E8]; this
0x180007423  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180007428  mov     rdi, [rbp+170h+var_1E8]
0x18000742c  lea     r8, aClsid; "CLSID\\"
0x180007433  mov     rdx, rsi; SizeInWords
0x180007436  lea     rcx, [rbp+170h+Destination]; Destination
0x18000743a  call    cs:__imp_wcscpy_s
0x180007440  mov     ecx, eax; int
0x180007442  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007447  lea     r8, [rbp+170h+sz]; Source
0x18000744e  mov     rdx, rsi; SizeInWords
0x180007451  lea     rcx, [rbp+170h+Destination]; Destination
0x180007455  call    cs:__imp_wcscat_s
0x18000745b  mov     ecx, eax; int
0x18000745d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007462  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180007469  mov     rdx, rsi; SizeInWords
0x18000746c  lea     rcx, [rbp+170h+Destination]; Destination
0x180007470  call    cs:__imp_wcscat_s
0x180007476  mov     ecx, eax; int
0x180007478  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000747d  mov     r9d, r14d; unsigned int
0x180007480  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180007484  mov     rdx, rdi; hKey
0x180007487  lea     rcx, [rsp+270h+hKey]; this
0x18000748c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007491  test    eax, eax
0x180007493  jnz     short loc_1800074F9
0x180007495  mov     rcx, [rsp+270h+hKey]; hKey
0x18000749a  lea     rax, [rsp+270h+cSubKeys]
0x18000749f  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800074a4  xor     r9d, r9d; lpReserved
0x1800074a7  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800074ac  xor     r8d, r8d; lpcchClass
0x1800074af  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800074b4  xor     edx, edx; lpClass
0x1800074b6  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800074bb  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800074c0  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800074c5  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800074ca  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800074cf  call    cs:__imp_RegQueryInfoKeyW
0x1800074d5  lea     rcx, [rsp+270h+hKey]; this
0x1800074da  mov     ebx, eax
0x1800074dc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800074e1  test    ebx, ebx
0x1800074e3  jnz     short loc_1800074F9
0x1800074e5  cmp     [rsp+270h+cSubKeys], r15d
0x1800074ea  jnz     short loc_1800074F9
0x1800074ec  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x1800074f0  lea     rcx, [rbp+170h+var_1E8]; this
0x1800074f4  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800074f9  lea     rcx, [rsp+270h+hKey]; this
0x1800074fe  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007503  lea     rcx, [rbp+170h+var_1E8]; this
0x180007507  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000750c  lea     rcx, [rbp+170h+var_1D0]
0x180007510  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180007515  mov     edi, r15d
0x180007518  lea     rcx, [rsp+270h+var_208]
0x18000751d  call    ??1?$CComPtrBase@UITypeLib@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITypeLib>::~CComPtrBase<ITypeLib>(void)
0x180007522  mov     eax, edi
0x180007524  mov     rcx, [rbp+170h+var_30]
0x18000752b  xor     rcx, rsp; StackCookie
0x18000752e  call    __security_check_cookie
0x180007533  lea     r11, [rsp+270h+var_20]
0x18000753b  mov     rbx, [r11+40h]
0x18000753f  mov     rsi, [r11+48h]
0x180007543  mov     rsp, r11
0x180007546  pop     r15
0x180007548  pop     r14
0x18000754a  pop     r12
0x18000754c  pop     rdi
0x18000754d  pop     rbp
0x18000754e  retn
```
