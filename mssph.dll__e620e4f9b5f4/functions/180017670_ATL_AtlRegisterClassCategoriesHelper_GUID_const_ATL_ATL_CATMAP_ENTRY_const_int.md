# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180017670`
- end: `0x1800179ab`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a73c`
- `0x18001ba7c`
- `0x18001c960`

## callees

- `0x18000a040`
- `0x18000ad30`
- `0x18000fcd0`
- `0x180016634`
- `0x18001760c`
- `0x180017670`
- `0x180017ae4`
- `0x180017dac`
- `0x180019e30`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800177b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800177cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800178b1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800178cc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800177b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800177cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800178b1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800178cc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001779b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180017896`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001779b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180017896`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001777f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001777f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800176f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800176f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001785a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001792b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001785a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001792b`

## string_xrefs

- `0x180017790`: `CLSID\`
- `0x180017888`: `CLSID\`

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
  ATL::CComPtrBase<ICatRegister>::~CComPtrBase<ICatRegister>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180017670  mov     [rsp-8+arg_10], rbx
0x180017675  mov     [rsp-8+arg_18], rsi
0x18001767a  push    rbp
0x18001767b  push    rdi
0x18001767c  push    r12
0x18001767e  push    r14
0x180017680  push    r15
0x180017682  lea     rbp, [rsp-150h]
0x18001768a  sub     rsp, 250h
0x180017691  mov     rax, cs:__security_cookie
0x180017698  xor     rax, rsp
0x18001769b  mov     [rbp+170h+var_30], rax
0x1800176a2  xor     r15d, r15d
0x1800176a5  xorps   xmm0, xmm0
0x1800176a8  mov     [rsp+270h+var_208], r15
0x1800176ad  mov     r14d, r8d
0x1800176b0  mov     rbx, rdx
0x1800176b3  mov     rsi, rcx
0x1800176b6  movups  [rbp+170h+var_1C8], xmm0
0x1800176ba  test    rdx, rdx
0x1800176bd  jz      loc_180017971
0x1800176c3  lea     rdx, GUID_NULL
0x1800176ca  call    InlineIsEqualGUID
0x1800176cf  test    eax, eax
0x1800176d1  jnz     loc_180017971
0x1800176d7  lea     rax, [rsp+270h+var_208]
0x1800176dc  xor     edx, edx; pUnkOuter
0x1800176de  lea     r12d, [r15+1]
0x1800176e2  mov     [rsp+270h+ppv], rax; ppv
0x1800176e7  mov     r8d, r12d; dwClsContext
0x1800176ea  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800176f1  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800176f8  call    cs:__imp_CoCreateInstance
0x1800176fe  test    eax, eax
0x180017700  js      loc_180017971
0x180017706  cmp     [rbx], r15d
0x180017709  jz      short loc_180017768
0x18001770b  mov     rax, [rbx+8]
0x18001770f  lea     r9, [rbp+170h+var_1C8]
0x180017713  mov     rcx, [rsp+270h+var_208]
0x180017718  mov     r8d, r12d
0x18001771b  mov     rdx, rsi
0x18001771e  movups  xmm0, xmmword ptr [rax]
0x180017721  movdqu  [rbp+170h+var_1C8], xmm0
0x180017726  mov     rax, [rcx]
0x180017729  test    r14d, r14d
0x18001772c  jz      short loc_18001774E
0x18001772e  cmp     [rbx], r12d
0x180017731  jnz     short loc_180017739
0x180017733  mov     rax, [rax+28h]
0x180017737  jmp     short loc_18001773D
0x180017739  mov     rax, [rax+38h]
0x18001773d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017742  mov     edi, eax
0x180017744  test    eax, eax
0x180017746  js      loc_180017974
0x18001774c  jmp     short loc_180017762
0x18001774e  cmp     [rbx], r12d
0x180017751  jnz     short loc_180017759
0x180017753  mov     rax, [rax+30h]
0x180017757  jmp     short loc_18001775D
0x180017759  mov     rax, [rax+40h]
0x18001775d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017762  add     rbx, 10h
0x180017766  jmp     short loc_180017706
0x180017768  test    r14d, r14d
0x18001776b  jnz     loc_180017971
0x180017771  lea     r8d, [r14+40h]; cchMax
0x180017775  mov     rcx, rsi; rguid
0x180017778  lea     rdx, [rbp+170h+sz]; lpsz
0x18001777f  call    cs:__imp_StringFromGUID2
0x180017785  mov     esi, 80h
0x18001778a  mov     [rbp+170h+var_1D0], r15
0x18001778e  mov     edx, esi
0x180017790  lea     r8, aClsid; "CLSID\\"
0x180017797  lea     rcx, [rbp+170h+SubKey]
0x18001779b  call    cs:__imp__o_wcscpy_s
0x1800177a1  mov     ecx, eax; int
0x1800177a3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800177a8  lea     r8, [rbp+170h+sz]
0x1800177af  mov     edx, esi
0x1800177b1  lea     rcx, [rbp+170h+SubKey]
0x1800177b5  call    cs:__imp__o_wcscat_s
0x1800177bb  mov     ecx, eax; int
0x1800177bd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800177c2  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800177c9  mov     edx, esi
0x1800177cb  lea     rcx, [rbp+170h+SubKey]
0x1800177cf  call    cs:__imp__o_wcscat_s
0x1800177d5  mov     ecx, eax; int
0x1800177d7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800177dc  mov     rdi, 0FFFFFFFF80000000h
0x1800177e3  mov     [rbp+170h+var_1E0], r15
0x1800177e7  mov     r14d, 20019h
0x1800177ed  mov     [rbp+170h+var_1E8], rdi
0x1800177f1  mov     r9d, r14d; unsigned int
0x1800177f4  mov     [rbp+170h+var_1D8], r15
0x1800177f8  mov     rdx, rdi; hKey
0x1800177fb  mov     [rsp+270h+hKey], r15
0x180017800  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180017804  mov     [rsp+270h+var_1F8], r15
0x180017809  lea     rcx, [rsp+270h+hKey]; this
0x18001780e  mov     [rbp+170h+var_1F0], r15
0x180017812  mov     [rsp+270h+cSubKeys], r15d
0x180017817  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001781c  test    eax, eax
0x18001781e  jnz     short loc_180017888
0x180017820  mov     rcx, [rsp+270h+hKey]; hKey
0x180017825  lea     rax, [rsp+270h+cSubKeys]
0x18001782a  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001782f  xor     r9d, r9d; lpReserved
0x180017832  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180017837  xor     r8d, r8d; lpcchClass
0x18001783a  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001783f  xor     edx, edx; lpClass
0x180017841  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180017846  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18001784b  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180017850  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180017855  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18001785a  call    cs:__imp_RegQueryInfoKeyW
0x180017860  lea     rcx, [rsp+270h+hKey]; this
0x180017865  mov     ebx, eax
0x180017867  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001786c  test    ebx, ebx
0x18001786e  jnz     short loc_180017888
0x180017870  cmp     [rsp+270h+cSubKeys], r15d
0x180017875  jnz     short loc_180017888
0x180017877  lea     rdx, [rbp+170h+SubKey]; wchar_t *
0x18001787b  lea     rcx, [rbp+170h+var_1E8]; this
0x18001787f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180017884  mov     rdi, [rbp+170h+var_1E8]
0x180017888  lea     r8, aClsid; "CLSID\\"
0x18001788f  mov     rdx, rsi
0x180017892  lea     rcx, [rbp+170h+SubKey]
0x180017896  call    cs:__imp__o_wcscpy_s
0x18001789c  mov     ecx, eax; int
0x18001789e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800178a3  lea     r8, [rbp+170h+sz]
0x1800178aa  mov     rdx, rsi
0x1800178ad  lea     rcx, [rbp+170h+SubKey]
0x1800178b1  call    cs:__imp__o_wcscat_s
0x1800178b7  mov     ecx, eax; int
0x1800178b9  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800178be  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800178c5  mov     rdx, rsi
0x1800178c8  lea     rcx, [rbp+170h+SubKey]
0x1800178cc  call    cs:__imp__o_wcscat_s
0x1800178d2  mov     ecx, eax; int
0x1800178d4  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800178d9  mov     r9d, r14d; unsigned int
0x1800178dc  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x1800178e0  mov     rdx, rdi; hKey
0x1800178e3  lea     rcx, [rsp+270h+hKey]; this
0x1800178e8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800178ed  test    eax, eax
0x1800178ef  jnz     short loc_180017955
0x1800178f1  mov     rcx, [rsp+270h+hKey]; hKey
0x1800178f6  lea     rax, [rsp+270h+cSubKeys]
0x1800178fb  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180017900  xor     r9d, r9d; lpReserved
0x180017903  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180017908  xor     r8d, r8d; lpcchClass
0x18001790b  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180017910  xor     edx, edx; lpClass
0x180017912  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180017917  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18001791c  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180017921  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180017926  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18001792b  call    cs:__imp_RegQueryInfoKeyW
0x180017931  lea     rcx, [rsp+270h+hKey]; this
0x180017936  mov     ebx, eax
0x180017938  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001793d  test    ebx, ebx
0x18001793f  jnz     short loc_180017955
0x180017941  cmp     [rsp+270h+cSubKeys], r15d
0x180017946  jnz     short loc_180017955
0x180017948  lea     rdx, [rbp+170h+SubKey]; wchar_t *
0x18001794c  lea     rcx, [rbp+170h+var_1E8]; this
0x180017950  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180017955  lea     rcx, [rsp+270h+hKey]; this
0x18001795a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001795f  lea     rcx, [rbp+170h+var_1E8]; this
0x180017963  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180017968  lea     rcx, [rbp+170h+var_1D0]
0x18001796c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017971  mov     edi, r15d
0x180017974  lea     rcx, [rsp+270h+var_208]
0x180017979  call    ??1?$CComPtrBase@UICatRegister@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICatRegister>::~CComPtrBase<ICatRegister>(void)
0x18001797e  mov     eax, edi
0x180017980  mov     rcx, [rbp+170h+var_30]
0x180017987  xor     rcx, rsp; StackCookie
0x18001798a  call    __security_check_cookie
0x18001798f  lea     r11, [rsp+270h+var_20]
0x180017997  mov     rbx, [r11+40h]
0x18001799b  mov     rsi, [r11+48h]
0x18001799f  mov     rsp, r11
0x1800179a2  pop     r15
0x1800179a4  pop     r14
0x1800179a6  pop     r12
0x1800179a8  pop     rdi
0x1800179a9  pop     rbp
0x1800179aa  retn
```
