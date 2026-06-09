# OfflineRegistry::MergeHives(ushort const *,void *,std::optional<TokenMap> &,std::vector<std::unique_ptr<PackageInformation,std::default_delete<PackageInformation>>,std::allocator<std::unique_ptr<PackageInformation,std::default_delete<PackageInformation>>>> const &,OfflineRegistry::Hive &,bool)

- ea: `0x18007a650`
- end: `0x18007ad3a`
- name: `?MergeHives@OfflineRegistry@@YAHPEBGPEAXAEAV?$optional@VTokenMap@@@std@@AEBV?$vector@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@V?$allocator@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@@2@@3@AEAVHive@1@_N@Z`
- size: `1770`
- prototype: `__int64 __fastcall(__int64, void *, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180079648`

## callees

- `0x180004f70`
- `0x1800057fc`
- `0x18000ae88`
- `0x18000e074`
- `0x1800125f4`
- `0x180012fb8`
- `0x180013490`
- `0x180013510`
- `0x180014e74`
- `0x180014efc`
- `0x18001cfe0`
- `0x1800210fc`
- `0x180021118`
- `0x180021138`
- `0x18002d56c`
- `0x180032cf0`
- `0x180038de8`
- `0x180038e70`
- `0x180038f88`
- `0x18003a6b0`
- `0x18004f49c`
- `0x180051e1c`
- `0x180061318`
- `0x1800618bc`
- `0x180078b24`
- `0x180078fa8`
- `0x180079180`
- `0x18007a490`
- `0x18007a650`
- `0x180097fb8`
- `0x18009815c`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a7a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a7a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007aba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007aba8`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x18007a7ec`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x18007a7ec`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18007a8a8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18007a8a8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007a8f6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007a921`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007a8f6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007a921`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18007a726`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18007a778`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18007a726`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18007a778`
- `api-ms-win-appmodel-runtime-l1-1-3!GetPackagePathByFullName2` at `0x18007a8dd`
- `api-ms-win-appmodel-runtime-l1-1-3!GetPackagePathByFullName2` at `0x18007a8dd`

## string_xrefs

- `0x18007aca4`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x18007ace9`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x18007acfe`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x18007ac89`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistryutil.cpp`
- `0x18007ad13`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistryutil.cpp`
- `0x18007ad28`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistryutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OfflineRegistry::MergeHives(__int64 a1, void *a2, __int64 a3, __int64 a4, __int64 a5, char a6)
{
  void *v8; // r15
  int v9; // r13d
  unsigned int v10; // r14d
  _QWORD *v11; // rsi
  int v12; // ebx
  bool v13; // r14
  __int64 v14; // r14
  const WCHAR *v15; // rcx
  LONG v16; // eax
  _QWORD *v17; // rbx
  _QWORD *v18; // r15
  const WCHAR *v19; // rcx
  LONG v20; // eax
  int v21; // eax
  int IsWowGuestMachineSupported; // eax
  __int64 v23; // r8
  int v24; // r9d
  _QWORD *v25; // rbx
  const char *v26; // r9
  unsigned int PackagePathByFullName2; // eax
  __int128 *v28; // r8
  __int64 v29; // r9
  __int128 *p_Src; // r8
  const unsigned __int16 *v31; // rcx
  _QWORD *v32; // rdx
  __int64 v33; // r8
  _QWORD *v34; // rax
  _QWORD *v35; // rbx
  __int64 v36; // rdx
  void *v37; // rcx
  __int64 v38; // rax
  _QWORD *v39; // rax
  __int64 v40; // rcx
  _QWORD *v41; // rax
  __int64 v42; // rcx
  void *v43; // rcx
  unsigned __int16 *v44; // rcx
  int v45; // eax
  __int64 v47; // rax
  unsigned int v48; // eax
  unsigned int v49; // [rsp+20h] [rbp-E0h]
  _BYTE v50[5]; // [rsp+40h] [rbp-C0h] BYREF
  char v51; // [rsp+45h] [rbp-BBh]
  unsigned int v52; // [rsp+48h] [rbp-B8h]
  int v53; // [rsp+4Ch] [rbp-B4h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 v55[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 i; // [rsp+60h] [rbp-A0h] BYREF
  void *v57; // [rsp+68h] [rbp-98h]
  __int64 v58; // [rsp+70h] [rbp-90h]
  __int64 v59; // [rsp+78h] [rbp-88h]
  _BYTE v60[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v61[16]; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp-60h] BYREF
  void *Block; // [rsp+A8h] [rbp-58h]
  _BYTE v64[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v65[24]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v66[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v67[16]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v68[40]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v69; // [rsp+120h] [rbp+20h] BYREF
  __int64 v70; // [rsp+130h] [rbp+30h]
  unsigned __int64 v71; // [rsp+138h] [rbp+38h]
  __int128 Src; // [rsp+140h] [rbp+40h] BYREF
  __int128 v73; // [rsp+150h] [rbp+50h]
  unsigned __int16 *v74[3]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v75; // [rsp+178h] [rbp+78h]
  _QWORD v76[4]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR v77[72]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+230h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v8 = a2;
  v57 = a2;
  v58 = a1;
  v59 = a5;
  v9 = 0;
  v53 = 0;
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v66);
  v10 = 0;
  v52 = 0;
  v11 = *(_QWORD **)a4;
  for ( i = *(_QWORD *)(a4 + 8); v11 != (_QWORD *)i; ++v11 )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 48LL))(*v11);
    v13 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11) && v12 == 11 )
    {
      v14 = *v11;
      packageFamilyNameLength = 65;
      v15 = (const WCHAR *)(v14 + 8);
      if ( *(_QWORD *)(v14 + 32) > 7u )
        v15 = *(const WCHAR **)v15;
      v16 = PackageFamilyNameFromFullName(v15, &packageFamilyNameLength, packageFamilyName);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
          (const char *)(unsigned int)v16,
          v49);
      v17 = *(_QWORD **)a4;
      v18 = *(_QWORD **)(a4 + 8);
      while ( 1 )
      {
        if ( v17 == v18 )
        {
          v47 = std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::_Get(v14);
          i = std::wstring::c_str(v47);
          DesktopAppXProvider::FindBasePackageFromResourcePackageFailed<unsigned short const *>(&i);
          v48 = wil::verify_hresult(2147942402LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x91,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
            (const char *)v48,
            v49);
        }
        v55[0] = 65;
        v19 = (const WCHAR *)(*v17 + 8LL);
        if ( *(_QWORD *)(*v17 + 32LL) > 7u )
          v19 = *(const WCHAR **)v19;
        v20 = PackageFamilyNameFromFullName(v19, v55, v77);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x89,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
            (const char *)(unsigned int)v20,
            v49);
        if ( !(unsigned int)_o__wcsicmp(packageFamilyName, v77) )
          break;
        ++v17;
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 48LL))(*v17);
      v8 = v57;
      v13 = 0;
    }
    v21 = 0;
    if ( v12 != 14 )
      v21 = v12;
    if ( !v21 )
    {
      v50[0] = 0;
      IsWowGuestMachineSupported = RtlWow64IsWowGuestMachineSupported(332, v50);
      if ( IsWowGuestMachineSupported < 0 )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x2A,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistryutil.cpp",
          (const char *)(unsigned int)IsWowGuestMachineSupported,
          v49);
      v13 = v50[0] != 0;
    }
    LoggedonUserImpersonation::Impersonate(v61, v8);
    GetPackagePath(v76);
    ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v61);
    v50[0] = 0;
    Src = 0;
    v73 = 0;
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(v58 + 2 * v23) );
    std::wstring::_Construct<1,unsigned short const *>(&Src, v58, v23);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 40LL))(*v11) )
    {
      v25 = (_QWORD *)(*v11 + 8LL);
      if ( *(_QWORD *)(*v11 + 32LL) > 7u )
        v25 = (_QWORD *)*v25;
      if ( !ImpersonateLoggedOnUser(v8) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistryutil.cpp",
          v26);
      v51 = 1;
      v53 = 0;
      PackagePathByFullName2 = GetPackagePathByFullName2(v25, 5, &v53);
      if ( PackagePathByFullName2 == 1168 )
      {
        v51 = 0;
        RevertToSelf();
      }
      else
      {
        if ( PackagePathByFullName2 != 122 && PackagePathByFullName2 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x3F,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistryutil.cpp",
            (const char *)PackagePathByFullName2,
            v49);
        v51 = 0;
        RevertToSelf();
        GetPackageFamilyNameFromFullName(&v69, *v11 + 8LL);
        std::wstring::_Insert<unsigned short>(&Src);
        v28 = &v69;
        if ( v71 > 7 )
          v28 = (__int128 *)v69;
        v29 = -1;
        do
          ++v29;
        while ( *((_WORD *)v28 + v29) );
        std::wstring::_Insert<unsigned short>(&Src);
        std::wstring::~wstring(&v69);
      }
    }
    p_Src = &Src;
    if ( *((_QWORD *)&v73 + 1) > 7u )
      LODWORD(p_Src) = Src;
    LOBYTE(v24) = v13;
    OfflineRegistry::GetPackageHivePath((unsigned int)v74, (unsigned int)v76, (_DWORD)p_Src, v24, (__int64)v50);
    LoggedonUserImpersonation::Impersonate(v60, v8);
    v31 = (const unsigned __int16 *)v74;
    if ( v75 > 7 )
      v31 = v74[0];
    if ( FileExists(v31) )
    {
      v32 = v76;
      if ( *(_BYTE *)(a3 + 56) )
      {
        TokenMap::SetPackageRoot((TokenMap *)a3);
      }
      else
      {
        if ( v76[3] > 7u )
          v32 = (_QWORD *)v76[0];
        v69 = 0;
        v70 = 0;
        v71 = 0;
        v33 = -1;
        do
          ++v33;
        while ( *((_WORD *)v32 + v33) );
        std::wstring::_Construct<1,unsigned short const *>(&v69, v32, v33);
        v34 = (_QWORD *)TokenMap::TokenMap((TokenMap *)&hObject, v8, &v69);
        v35 = v34;
        if ( *(_BYTE *)(a3 + 56) )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
            a3,
            v34);
          v36 = v35[1];
          v35[1] = 0;
          v37 = *(void **)(a3 + 8);
          *(_QWORD *)(a3 + 8) = v36;
          if ( v37 )
            operator delete(v37);
          *(_BYTE *)(a3 + 16) = *((_BYTE *)v35 + 16);
          *(_BYTE *)(a3 + 17) = *((_BYTE *)v35 + 17);
          std::map<std::wstring,TokenMap::TokenMapValue>::operator=(a3 + 24, v35 + 3);
          std::map<std::wstring,TokenMap::TokenMapValue>::operator=(a3 + 40, v35 + 5);
        }
        else
        {
          *(_QWORD *)v55 = a3;
          *(_QWORD *)a3 = *v34;
          *v34 = 0;
          v38 = v34[1];
          v35[1] = 0;
          *(_QWORD *)(a3 + 8) = v38;
          *(_BYTE *)(a3 + 16) = *((_BYTE *)v35 + 16);
          *(_BYTE *)(a3 + 17) = *((_BYTE *)v35 + 17);
          *(_QWORD *)(a3 + 24) = 0;
          *(_QWORD *)(a3 + 32) = 0;
          v39 = operator new(0x98u);
          *v39 = v39;
          v39[1] = v39;
          v39[2] = v39;
          *((_WORD *)v39 + 12) = 257;
          *(_QWORD *)(a3 + 24) = v39;
          *(_QWORD *)(a3 + 24) = v35[3];
          v35[3] = v39;
          v40 = *(_QWORD *)(a3 + 32);
          *(_QWORD *)(a3 + 32) = v35[4];
          v35[4] = v40;
          *(_QWORD *)(a3 + 40) = 0;
          *(_QWORD *)(a3 + 48) = 0;
          v41 = operator new(0x98u);
          *v41 = v41;
          v41[1] = v41;
          v41[2] = v41;
          *((_WORD *)v41 + 12) = 257;
          *(_QWORD *)(a3 + 40) = v41;
          *(_QWORD *)(a3 + 40) = v35[5];
          v35[5] = v41;
          v42 = *(_QWORD *)(a3 + 48);
          *(_QWORD *)(a3 + 48) = v35[6];
          v35[6] = v42;
          *(_BYTE *)(a3 + 56) = 1;
        }
        std::_Tree<std::_Tmap_traits<std::wstring,TokenMap::TokenMapValue,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,TokenMap::TokenMapValue>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,TokenMap::TokenMapValue,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,TokenMap::TokenMapValue>>,0>>(v65);
        std::_Tree<std::_Tmap_traits<std::wstring,TokenMap::TokenMapValue,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,TokenMap::TokenMapValue>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,TokenMap::TokenMapValue,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,TokenMap::TokenMapValue>>,0>>(v64);
        v43 = Block;
        Block = 0;
        if ( v43 )
          operator delete(v43);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
      }
      if ( !*(_BYTE *)(a3 + 56) )
        std::_Throw_bad_optional_access();
      v44 = (unsigned __int16 *)v74;
      if ( v75 > 7 )
        v44 = v74[0];
      v45 = OfflineRegistry::MergeHive(v44, v59, a6);
      v10 = v45 + v52;
      v52 += v45;
      ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v60);
      std::wstring::~wstring(v74);
      std::wstring::~wstring(&Src);
    }
    else
    {
      ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v60);
      std::wstring::~wstring(v74);
      std::wstring::~wstring(&Src);
      v10 = v52;
    }
    v9 |= 1u;
    std::wstring::~wstring(v76);
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v68);
  std::list<std::wstring>::~list<std::wstring>(v67);
  return v10;
}

```

## disassembly

```asm
0x18007a650  push    rbp
0x18007a652  push    rbx
0x18007a653  push    rsi
0x18007a654  push    rdi
0x18007a655  push    r12
0x18007a657  push    r13
0x18007a659  push    r14
0x18007a65b  push    r15
0x18007a65d  lea     rbp, [rsp-1D8h]
0x18007a665  sub     rsp, 2D8h
0x18007a66c  mov     rax, cs:__security_cookie
0x18007a673  xor     rax, rsp
0x18007a676  mov     [rbp+210h+var_50], rax
0x18007a67d  mov     r12, r9
0x18007a680  mov     rdi, r8
0x18007a683  mov     r15, rdx
0x18007a686  mov     [rsp+310h+var_2A8], rdx
0x18007a68b  mov     [rsp+310h+var_2A0], rcx
0x18007a690  mov     rax, [rbp+210h+arg_20]
0x18007a697  mov     [rsp+310h+var_298], rax
0x18007a69c  xor     ebx, ebx
0x18007a69e  mov     r13d, ebx
0x18007a6a1  mov     [rsp+310h+var_2C4], ebx
0x18007a6a5  lea     rcx, [rbp+210h+var_230]
0x18007a6a9  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18007a6ae  nop
0x18007a6af  mov     r14d, ebx
0x18007a6b2  mov     [rsp+310h+var_2C8], ebx
0x18007a6b6  mov     rsi, [r12]
0x18007a6ba  mov     rax, [r12+8]
0x18007a6bf  mov     [rsp+310h+var_2B0], rax
0x18007a6c4  cmp     rsi, rax
0x18007a6c7  jz      loc_18007AC50
0x18007a6cd  mov     rcx, [rsi]
0x18007a6d0  mov     rax, [rcx]
0x18007a6d3  mov     rax, [rax+30h]
0x18007a6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a6dc  mov     ebx, eax
0x18007a6de  mov     rcx, [rsi]
0x18007a6e1  mov     rax, [rcx]
0x18007a6e4  mov     rax, [rax+10h]
0x18007a6e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a6ed  xor     r14d, r14d
0x18007a6f0  test    al, al
0x18007a6f2  jz      loc_18007A7D0
0x18007a6f8  cmp     ebx, 0Bh
0x18007a6fb  jnz     loc_18007A7D0
0x18007a701  mov     r14, [rsi]
0x18007a704  mov     [rsp+310h+packageFamilyNameLength], 41h ; 'A'
0x18007a70c  lea     rcx, [r14+8]
0x18007a710  cmp     qword ptr [r14+20h], 7
0x18007a715  jbe     short loc_18007A71A
0x18007a717  mov     rcx, [rcx]; packageFullName
0x18007a71a  lea     r8, [rbp+210h+packageFamilyName]; packageFamilyName
0x18007a721  lea     rdx, [rsp+310h+packageFamilyNameLength]; packageFamilyNameLength
0x18007a726  call    cs:__imp_PackageFamilyNameFromFullName
0x18007a72d  nop     dword ptr [rax+rax+00h]
0x18007a732  mov     rcx, [rbp+218h]; this
0x18007a739  test    eax, eax
0x18007a73b  js      loc_18007ACFB
0x18007a741  mov     rbx, [r12]
0x18007a745  mov     r15, [r12+8]
0x18007a74a  cmp     rbx, r15
0x18007a74d  jz      loc_18007ACB6
0x18007a753  mov     [rsp+310h+var_2B8], 41h ; 'A'
0x18007a75b  mov     rcx, [rbx]
0x18007a75e  add     rcx, 8
0x18007a762  cmp     qword ptr [rcx+18h], 7
0x18007a767  jbe     short loc_18007A76C
0x18007a769  mov     rcx, [rcx]; packageFullName
0x18007a76c  lea     r8, [rbp+210h+var_170]; packageFamilyName
0x18007a773  lea     rdx, [rsp+310h+var_2B8]; packageFamilyNameLength
0x18007a778  call    cs:__imp_PackageFamilyNameFromFullName
0x18007a77f  nop     dword ptr [rax+rax+00h]
0x18007a784  mov     rcx, [rbp+218h]; this
0x18007a78b  test    eax, eax
0x18007a78d  js      loc_18007ACA1
0x18007a793  lea     rdx, [rbp+210h+var_170]
0x18007a79a  lea     rcx, [rbp+210h+packageFamilyName]
0x18007a7a1  call    cs:__imp__o__wcsicmp
0x18007a7a8  nop     dword ptr [rax+rax+00h]
0x18007a7ad  test    eax, eax
0x18007a7af  jz      short loc_18007A7B7
0x18007a7b1  add     rbx, 8
0x18007a7b5  jmp     short loc_18007A74A
0x18007a7b7  mov     rcx, [rbx]
0x18007a7ba  mov     rax, [rcx]
0x18007a7bd  mov     rax, [rax+30h]
0x18007a7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a7c6  mov     ebx, eax
0x18007a7c8  mov     r15, [rsp+310h+var_2A8]
0x18007a7cd  xor     r14d, r14d
0x18007a7d0  mov     eax, r14d
0x18007a7d3  cmp     ebx, 0Eh
0x18007a7d6  cmovnz  eax, ebx
0x18007a7d9  test    eax, eax
0x18007a7db  jnz     short loc_18007A810
0x18007a7dd  mov     [rsp+310h+var_2D0], r14b
0x18007a7e2  mov     ecx, 14Ch
0x18007a7e7  lea     rdx, [rsp+310h+var_2D0]
0x18007a7ec  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x18007a7f3  nop     dword ptr [rax+rax+00h]
0x18007a7f8  mov     rcx, [rbp+218h]; this
0x18007a7ff  test    eax, eax
0x18007a801  js      loc_18007AD10
0x18007a807  cmp     [rsp+310h+var_2D0], r14b
0x18007a80c  setnz   r14b
0x18007a810  mov     rbx, [rsi]
0x18007a813  add     rbx, 8
0x18007a817  cmp     qword ptr [rbx+18h], 7
0x18007a81c  jbe     short loc_18007A821
0x18007a81e  mov     rbx, [rbx]
0x18007a821  mov     rdx, r15
0x18007a824  lea     rcx, [rbp+210h+var_280]
0x18007a828  call    ?Impersonate@LoggedonUserImpersonation@@SA?AU1@PEAX@Z; LoggedonUserImpersonation::Impersonate(void *)
0x18007a82d  nop
0x18007a82e  mov     rdx, rbx
0x18007a831  lea     rcx, [rbp+210h+var_190]; Src
0x18007a838  call    ?GetPackagePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetPackagePath(ushort const *)
0x18007a83d  nop
0x18007a83e  lea     rcx, [rbp+210h+var_280]; this
0x18007a842  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x18007a847  nop
0x18007a848  xor     ebx, ebx
0x18007a84a  mov     [rsp+310h+var_2D0], bl
0x18007a84e  xorps   xmm0, xmm0
0x18007a851  movups  [rbp+210h+Src], xmm0
0x18007a855  xorps   xmm1, xmm1
0x18007a858  movdqu  [rbp+210h+var_1C0], xmm1
0x18007a85d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007a861  mov     rax, [rsp+310h+var_2A0]
0x18007a866  inc     r8
0x18007a869  cmp     [rax+r8*2], bx
0x18007a86e  jnz     short loc_18007A866
0x18007a870  mov     rdx, rax
0x18007a873  lea     rcx, [rbp+210h+Src]
0x18007a877  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007a87c  nop
0x18007a87d  mov     rcx, [rsi]
0x18007a880  mov     rax, [rcx]
0x18007a883  mov     rax, [rax+28h]
0x18007a887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a88c  test    al, al
0x18007a88e  jz      loc_18007A98C
0x18007a894  mov     rbx, [rsi]
0x18007a897  add     rbx, 8
0x18007a89b  cmp     qword ptr [rbx+18h], 7
0x18007a8a0  jbe     short loc_18007A8A5
0x18007a8a2  mov     rbx, [rbx]
0x18007a8a5  mov     rcx, r15; hToken
0x18007a8a8  call    cs:__imp_ImpersonateLoggedOnUser
0x18007a8af  nop     dword ptr [rax+rax+00h]
0x18007a8b4  mov     rcx, [rbp+218h]; this
0x18007a8bb  xor     edx, edx
0x18007a8bd  test    eax, eax
0x18007a8bf  jz      loc_18007AC89
0x18007a8c5  mov     [rsp+310h+var_2CB], 1
0x18007a8ca  mov     [rsp+310h+var_2C4], edx
0x18007a8ce  xor     r9d, r9d
0x18007a8d1  lea     r8, [rsp+310h+var_2C4]
0x18007a8d6  lea     edx, [r9+5]
0x18007a8da  mov     rcx, rbx
0x18007a8dd  call    cs:__imp_GetPackagePathByFullName2
0x18007a8e4  nop     dword ptr [rax+rax+00h]
0x18007a8e9  cmp     eax, 490h
0x18007a8ee  jnz     short loc_18007A907
0x18007a8f0  xor     ebx, ebx
0x18007a8f2  mov     [rsp+310h+var_2CB], bl
0x18007a8f6  call    cs:__imp_RevertToSelf
0x18007a8fd  nop     dword ptr [rax+rax+00h]
0x18007a902  jmp     loc_18007A98C
0x18007a907  xor     ebx, ebx
0x18007a909  cmp     eax, 7Ah ; 'z'
0x18007a90c  jz      short loc_18007A91D
0x18007a90e  mov     rcx, [rbp+218h]; this
0x18007a915  test    eax, eax
0x18007a917  jnz     loc_18007AD25
0x18007a91d  mov     [rsp+310h+var_2CB], bl
0x18007a921  call    cs:__imp_RevertToSelf
0x18007a928  nop     dword ptr [rax+rax+00h]
0x18007a92d  mov     rdx, [rsi]
0x18007a930  add     rdx, 8
0x18007a934  lea     rcx, [rbp+210h+var_1F0]
0x18007a938  call    ?GetPackageFamilyNameFromFullName@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; GetPackageFamilyNameFromFullName(std::wstring const &)
0x18007a93d  nop
0x18007a93e  mov     eax, 1
0x18007a943  mov     r9d, eax
0x18007a946  lea     r8, asc_1800D7B48; "_"
0x18007a94d  mov     edx, eax
0x18007a94f  lea     rcx, [rbp+210h+Src]; Src
0x18007a953  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18007a958  lea     r8, [rbp+210h+var_1F0]
0x18007a95c  cmp     [rbp+210h+var_1D8], 7
0x18007a961  cmova   r8, qword ptr [rbp+210h+var_1F0]
0x18007a966  or      r9, 0FFFFFFFFFFFFFFFFh
0x18007a96a  inc     r9
0x18007a96d  cmp     [r8+r9*2], bx
0x18007a972  jnz     short loc_18007A96A
0x18007a974  mov     edx, 1
0x18007a979  lea     rcx, [rbp+210h+Src]; Src
0x18007a97d  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18007a982  nop
0x18007a983  lea     rcx, [rbp+210h+var_1F0]; void *
0x18007a987  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007a98c  lea     r8, [rbp+210h+Src]
0x18007a990  cmp     qword ptr [rbp+210h+var_1C0+8], 7
0x18007a995  cmova   r8, qword ptr [rbp+210h+Src]
0x18007a99a  lea     rax, [rsp+310h+var_2D0]
0x18007a99f  mov     [rsp+310h+var_2F0], rax
0x18007a9a4  mov     r9b, r14b
0x18007a9a7  lea     rdx, [rbp+210h+var_190]
0x18007a9ae  lea     rcx, [rbp+210h+var_1B0]
0x18007a9b2  call    ?GetPackageHivePath@OfflineRegistry@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG_NAEA_N@Z; OfflineRegistry::GetPackageHivePath(std::wstring const &,ushort const *,bool,bool &)
0x18007a9b7  nop
0x18007a9b8  mov     rdx, r15
0x18007a9bb  lea     rcx, [rbp+210h+var_290]
0x18007a9bf  call    ?Impersonate@LoggedonUserImpersonation@@SA?AU1@PEAX@Z; LoggedonUserImpersonation::Impersonate(void *)
0x18007a9c4  nop
0x18007a9c5  lea     rcx, [rbp+210h+var_1B0]
0x18007a9c9  cmp     [rbp+210h+var_198], 7
0x18007a9ce  cmova   rcx, [rbp+210h+var_1B0]; unsigned __int16 *
0x18007a9d3  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x18007a9d8  test    al, al
0x18007a9da  jnz     short loc_18007AA04
0x18007a9dc  lea     rcx, [rbp+210h+var_290]; this
0x18007a9e0  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x18007a9e5  nop
0x18007a9e6  lea     rcx, [rbp+210h+var_1B0]; void *
0x18007a9ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007a9ef  nop
0x18007a9f0  lea     rcx, [rbp+210h+Src]; void *
0x18007a9f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007a9f9  nop
0x18007a9fa  mov     r14d, [rsp+310h+var_2C8]
0x18007a9ff  jmp     loc_18007AC31
0x18007aa04  lea     rdx, [rbp+210h+var_190]
0x18007aa0b  cmp     [rdi+38h], bl
0x18007aa0e  jnz     loc_18007ABB6
0x18007aa14  cmp     [rbp+210h+var_178], 7
0x18007aa1c  cmova   rdx, [rbp+210h+var_190]
0x18007aa24  xorps   xmm0, xmm0
0x18007aa27  movups  [rbp+210h+var_1F0], xmm0
0x18007aa2b  mov     [rbp+210h+var_1E0], rbx
0x18007aa2f  mov     [rbp+210h+var_1D8], rbx
0x18007aa33  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007aa37  inc     r8
0x18007aa3a  cmp     [rdx+r8*2], bx
0x18007aa3f  jnz     short loc_18007AA37
0x18007aa41  lea     rcx, [rbp+210h+var_1F0]
0x18007aa45  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007aa4a  mov     r9d, 2
0x18007aa50  lea     r8, [rbp+210h+var_1F0]
0x18007aa54  mov     rdx, r15
0x18007aa57  lea     rcx, [rbp+210h+hObject]
0x18007aa5b  call    ??0TokenMap@@QEAA@PEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TokenMapFlags@@@Z; TokenMap::TokenMap(void *,std::wstring,TokenMapFlags)
0x18007aa60  mov     rbx, rax
0x18007aa63  xor     ecx, ecx
0x18007aa65  cmp     [rdi+38h], cl
0x18007aa68  jz      short loc_18007AABC
0x18007aa6a  mov     rdx, rax
0x18007aa6d  mov     rcx, rdi
0x18007aa70  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18007aa75  mov     rdx, [rbx+8]
0x18007aa79  xor     eax, eax
0x18007aa7b  mov     [rbx+8], rax
0x18007aa7f  mov     rcx, [rdi+8]; Block
0x18007aa83  mov     [rdi+8], rdx
0x18007aa87  test    rcx, rcx
0x18007aa8a  jz      short loc_18007AA91
0x18007aa8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007aa91  mov     al, [rbx+10h]
0x18007aa94  mov     [rdi+10h], al
0x18007aa97  mov     al, [rbx+11h]
0x18007aa9a  mov     [rdi+11h], al
0x18007aa9d  lea     rdx, [rbx+18h]
0x18007aaa1  lea     rcx, [rdi+18h]
0x18007aaa5  call    ??4?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VTokenMapValue@TokenMap@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VTokenMapValue@TokenMap@@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::map<std::wstring,TokenMap::TokenMapValue>::operator=(std::map<std::wstring,TokenMap::TokenMapValue> &&)
0x18007aaaa  lea     rdx, [rbx+28h]
0x18007aaae  lea     rcx, [rdi+28h]
0x18007aab2  call    ??4?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VTokenMapValue@TokenMap@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VTokenMapValue@TokenMap@@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::map<std::wstring,TokenMap::TokenMapValue>::operator=(std::map<std::wstring,TokenMap::TokenMapValue> &&)
0x18007aab7  jmp     loc_18007AB74
0x18007aabc  mov     qword ptr [rsp+310h+var_2B8], rdi
0x18007aac1  mov     rax, [rax]
0x18007aac4  mov     [rdi], rax
0x18007aac7  mov     [rbx], rcx
0x18007aaca  mov     rax, [rbx+8]
0x18007aace  mov     [rbx+8], rcx
0x18007aad2  mov     [rdi+8], rax
0x18007aad6  mov     al, [rbx+10h]
0x18007aad9  mov     [rdi+10h], al
0x18007aadc  mov     al, [rbx+11h]
0x18007aadf  mov     [rdi+11h], al
0x18007aae2  mov     [rdi+18h], rcx
0x18007aae6  mov     [rdi+20h], rcx
0x18007aaea  mov     ecx, 98h; Size
0x18007aaef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007aaf4  mov     rcx, rax
0x18007aaf7  mov     [rax], rax
0x18007aafa  mov     [rax+8], rax
0x18007aafe  mov     [rax+10h], rax
  ... truncated ...
```
