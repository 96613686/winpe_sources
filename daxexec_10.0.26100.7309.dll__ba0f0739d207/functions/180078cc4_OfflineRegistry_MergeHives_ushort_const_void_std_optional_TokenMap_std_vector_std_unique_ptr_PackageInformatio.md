# OfflineRegistry::MergeHives(ushort const *,void *,std::optional<TokenMap> &,std::vector<std::unique_ptr<PackageInformation,std::default_delete<PackageInformation>>,std::allocator<std::unique_ptr<PackageInformation,std::default_delete<PackageInformation>>>> const &,OfflineRegistry::Hive &,bool)

- ea: `0x180078cc4`
- end: `0x1800792fb`
- name: `?MergeHives@OfflineRegistry@@YAHPEBGPEAXAEAV?$optional@VTokenMap@@@std@@AEBV?$vector@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@V?$allocator@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@@2@@3@AEAVHive@1@_N@Z`
- size: `1591`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180077cd4`

## callees

- `0x1800053a0`
- `0x180009338`
- `0x18000c37c`
- `0x180010a84`
- `0x180011300`
- `0x180011820`
- `0x1800119a8`
- `0x180013100`
- `0x180013200`
- `0x18001c5a0`
- `0x18002031c`
- `0x180020338`
- `0x180020358`
- `0x18003112c`
- `0x180037468`
- `0x1800374e0`
- `0x180037600`
- `0x18003fab4`
- `0x18004d73c`
- `0x180050100`
- `0x18005f808`
- `0x18005fdec`
- `0x180077174`
- `0x1800775ec`
- `0x180077798`
- `0x180078af4`
- `0x180078cc4`
- `0x180096668`
- `0x1800967b0`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180078e0d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180078e0d`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x180078e58`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x180078e58`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180078f15`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180078f15`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180078f63`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180078f8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180078f63`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180078f8e`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180078d92`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180078de4`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180078d92`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180078de4`
- `api-ms-win-appmodel-runtime-l1-1-3!GetPackagePathByFullName2` at `0x180078f4a`
- `api-ms-win-appmodel-runtime-l1-1-3!GetPackagePathByFullName2` at `0x180078f4a`

## string_xrefs

- `0x180079253`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x180079298`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x1800792ad`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x1800792c2`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistryutil.cpp`
- `0x1800792d7`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistryutil.cpp`
- `0x1800792e9`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistryutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall OfflineRegistry::MergeHives(__int64 a1, void *a2, __int64 a3, __int64 a4, __int64 a5, char a6)
{
  bool v9; // r14
  unsigned int v10; // r15d
  _QWORD *v11; // rdi
  int v12; // ebx
  __int64 v13; // r14
  const WCHAR *v14; // rcx
  LONG v15; // eax
  _QWORD *v16; // rbx
  _QWORD *v17; // r15
  const WCHAR *v18; // rcx
  LONG v19; // eax
  int v20; // eax
  int IsWowGuestMachineSupported; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  _QWORD *v24; // rbx
  const char *v25; // r9
  unsigned int PackagePathByFullName2; // eax
  __int128 *v27; // r8
  __int64 v28; // r9
  __int128 *v29; // r8
  const unsigned __int16 *v30; // rcx
  _QWORD *v31; // rdx
  __int64 v32; // r8
  _QWORD *v33; // rax
  _QWORD *v34; // rbx
  __int64 v35; // rax
  _QWORD *v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rcx
  unsigned __int16 *v40; // rcx
  __int64 v42; // rax
  unsigned int v43; // eax
  _BYTE *v44; // [rsp+20h] [rbp-E0h]
  _BYTE v45[5]; // [rsp+40h] [rbp-C0h] BYREF
  char v46; // [rsp+45h] [rbp-BBh]
  int v47; // [rsp+48h] [rbp-B8h]
  unsigned int v48; // [rsp+4Ch] [rbp-B4h]
  UINT32 packageFamilyNameLength; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 v50[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  _BYTE v55[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v56[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v57[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v58[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v59[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v60[56]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v61; // [rsp+118h] [rbp+18h] BYREF
  __int64 v62; // [rsp+128h] [rbp+28h]
  unsigned __int64 v63; // [rsp+130h] [rbp+30h]
  __int128 v64; // [rsp+138h] [rbp+38h] BYREF
  __int64 v65; // [rsp+148h] [rbp+48h]
  unsigned __int64 v66; // [rsp+150h] [rbp+50h]
  unsigned __int16 *v67[3]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int64 v68; // [rsp+170h] [rbp+70h]
  _QWORD Src[5]; // [rsp+178h] [rbp+78h] BYREF
  WCHAR v70[72]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+230h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v53 = a1;
  v54 = a5;
  v9 = 0;
  v47 = 0;
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v57);
  v10 = 0;
  v48 = 0;
  v11 = *(_QWORD **)a4;
  v52 = *(_QWORD *)(a4 + 8);
  if ( v11 != (_QWORD *)v52 )
  {
    while ( 1 )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 48LL))(*v11);
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11) && v12 == 11 )
      {
        v13 = *v11;
        packageFamilyNameLength = 65;
        v14 = (const WCHAR *)(v13 + 8);
        if ( *(_QWORD *)(v13 + 32) > 7u )
          v14 = *(const WCHAR **)v14;
        v15 = PackageFamilyNameFromFullName(v14, &packageFamilyNameLength, packageFamilyName);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x81,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
            (const char *)(unsigned int)v15,
            (int)v44);
        v16 = *(_QWORD **)a4;
        v17 = *(_QWORD **)(a4 + 8);
        while ( 1 )
        {
          if ( v16 == v17 )
          {
            v42 = std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::_Get(v13);
            v52 = std::wstring::c_str(v42);
            DesktopAppXProvider::FindBasePackageFromResourcePackageFailed<unsigned short const *>(&v52);
            v43 = wil::verify_hresult(2147942402LL);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x91,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
              (const char *)v43,
              (int)v44);
          }
          v50[0] = 65;
          v18 = (const WCHAR *)(*v16 + 8LL);
          if ( *(_QWORD *)(*v16 + 32LL) > 7u )
            v18 = *(const WCHAR **)v18;
          v19 = PackageFamilyNameFromFullName(v18, v50, v70);
          if ( v19 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x89,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
              (const char *)(unsigned int)v19,
              (int)v44);
          if ( !(unsigned int)_o__wcsicmp(packageFamilyName, v70) )
            break;
          ++v16;
        }
        v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 48LL))(*v16);
        v10 = v48;
        v9 = 0;
      }
      v20 = 0;
      if ( v12 != 14 )
        v20 = v12;
      if ( !v20 )
      {
        v45[0] = 0;
        IsWowGuestMachineSupported = RtlWow64IsWowGuestMachineSupported(332, v45);
        if ( IsWowGuestMachineSupported < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x2A,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistryutil.cpp",
            (const char *)(unsigned int)IsWowGuestMachineSupported,
            (int)v44);
        v9 = v45[0] != 0;
      }
      LoggedonUserImpersonation::Impersonate(v56, a2);
      GetPackagePath(Src);
      v47 |= 1u;
      ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v56);
      v45[0] = 0;
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v53 + 2 * v22) );
      std::wstring::_Construct<1,unsigned short const *>(&v61, v53, v22);
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 40LL))(*v11) )
      {
        v24 = (_QWORD *)(*v11 + 8LL);
        if ( *(_QWORD *)(*v11 + 32LL) > 7u )
          v24 = (_QWORD *)*v24;
        if ( !ImpersonateLoggedOnUser(a2) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x33,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistryutil.cpp",
            v25);
        v46 = 1;
        v51 = 0;
        PackagePathByFullName2 = GetPackagePathByFullName2(v24, 5, &v51);
        if ( PackagePathByFullName2 == 1168 )
        {
          v46 = 0;
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
              (unsigned int)v44);
          v46 = 0;
          RevertToSelf();
          GetPackageFamilyNameFromFullName(&v64, *v11 + 8LL);
          std::wstring::insert(&v61, 1);
          v27 = &v64;
          if ( v66 > 7 )
            v27 = (__int128 *)v64;
          v28 = -1;
          do
            ++v28;
          while ( *((_WORD *)v27 + v28) );
          std::wstring::insert(&v61, 1);
          std::wstring::~wstring(&v64);
        }
      }
      v29 = &v61;
      if ( v63 > 7 )
        v29 = (__int128 *)v61;
      v44 = v45;
      LOBYTE(v23) = v9;
      OfflineRegistry::GetPackageHivePath(v67, Src, v29, v23);
      LoggedonUserImpersonation::Impersonate(v55, a2);
      v30 = (const unsigned __int16 *)v67;
      if ( v68 > 7 )
        v30 = v67[0];
      if ( FileExists(v30) )
      {
        v31 = Src;
        if ( *(_BYTE *)(a3 + 56) )
        {
          TokenMap::SetPackageRoot((TokenMap *)a3);
        }
        else
        {
          if ( Src[3] > 7u )
            v31 = (_QWORD *)Src[0];
          v64 = 0;
          v65 = 0;
          v66 = 0;
          v32 = -1;
          do
            ++v32;
          while ( *((_WORD *)v31 + v32) );
          std::wstring::_Construct<1,unsigned short const *>(&v64, v31, v32);
          v33 = (_QWORD *)TokenMap::TokenMap((TokenMap *)v60, a2, &v64);
          v34 = v33;
          if ( *(_BYTE *)(a3 + 56) )
          {
            TokenMap::operator=(a3, v33);
          }
          else
          {
            *(_QWORD *)v50 = a3;
            *(_QWORD *)a3 = *v33;
            *v33 = 0;
            v35 = v33[1];
            v34[1] = 0;
            *(_QWORD *)(a3 + 8) = v35;
            *(_BYTE *)(a3 + 16) = *((_BYTE *)v34 + 16);
            *(_BYTE *)(a3 + 17) = *((_BYTE *)v34 + 17);
            *(_QWORD *)(a3 + 24) = 0;
            *(_QWORD *)(a3 + 32) = 0;
            v36 = operator new(0x98u);
            *v36 = v36;
            v36[1] = v36;
            v36[2] = v36;
            *((_WORD *)v36 + 12) = 257;
            *(_QWORD *)(a3 + 24) = v36;
            *(_QWORD *)(a3 + 24) = v34[3];
            v34[3] = v36;
            v37 = *(_QWORD *)(a3 + 32);
            *(_QWORD *)(a3 + 32) = v34[4];
            v34[4] = v37;
            *(_QWORD *)(a3 + 40) = 0;
            *(_QWORD *)(a3 + 48) = 0;
            v38 = operator new(0x98u);
            *v38 = v38;
            v38[1] = v38;
            v38[2] = v38;
            *((_WORD *)v38 + 12) = 257;
            *(_QWORD *)(a3 + 40) = v38;
            *(_QWORD *)(a3 + 40) = v34[5];
            v34[5] = v38;
            v39 = *(_QWORD *)(a3 + 48);
            *(_QWORD *)(a3 + 48) = v34[6];
            v34[6] = v39;
            *(_BYTE *)(a3 + 56) = 1;
          }
          TokenMap::~TokenMap((TokenMap *)v60);
        }
        if ( !*(_BYTE *)(a3 + 56) )
          std::_Throw_bad_optional_access();
        v40 = (unsigned __int16 *)v67;
        if ( v68 > 7 )
          v40 = v67[0];
        v10 += OfflineRegistry::MergeHive(v40, v54, a6);
        v48 = v10;
      }
      ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v55);
      std::wstring::~wstring(v67);
      std::wstring::~wstring(&v61);
      std::wstring::~wstring(Src);
      if ( ++v11 == (_QWORD *)v52 )
        break;
      v9 = 0;
    }
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v59);
  std::list<std::wstring>::~list<std::wstring>(v58);
  return v10;
}

```

## disassembly

```asm
0x180078cc4  push    rbp
0x180078cc6  push    rbx
0x180078cc7  push    rsi
0x180078cc8  push    rdi
0x180078cc9  push    r12
0x180078ccb  push    r13
0x180078ccd  push    r14
0x180078ccf  push    r15
0x180078cd1  lea     rbp, [rsp-1D8h]
0x180078cd9  sub     rsp, 2D8h
0x180078ce0  mov     rax, cs:__security_cookie
0x180078ce7  xor     rax, rsp
0x180078cea  mov     [rbp+210h+var_50], rax
0x180078cf1  mov     r12, r9
0x180078cf4  mov     rsi, r8
0x180078cf7  mov     r13, rdx
0x180078cfa  mov     [rsp+310h+var_2A0], rcx
0x180078cff  mov     rax, [rbp+210h+arg_20]
0x180078d06  mov     [rsp+310h+var_298], rax
0x180078d0b  xor     r14d, r14d
0x180078d0e  mov     [rsp+310h+var_2C8], r14d
0x180078d13  lea     rcx, [rbp+210h+var_270]
0x180078d17  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180078d1c  nop
0x180078d1d  mov     r15d, r14d
0x180078d20  mov     [rsp+310h+var_2C4], r14d
0x180078d25  mov     rdi, [r12]
0x180078d29  mov     rax, [r12+8]
0x180078d2e  mov     [rsp+310h+var_2A8], rax
0x180078d33  cmp     rdi, rax
0x180078d36  jz      loc_180079211
0x180078d3c  mov     rcx, [rdi]
0x180078d3f  mov     rax, [rcx]
0x180078d42  mov     rax, [rax+30h]
0x180078d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d4b  mov     ebx, eax
0x180078d4d  mov     rcx, [rdi]
0x180078d50  mov     rax, [rcx]
0x180078d53  mov     rax, [rax+10h]
0x180078d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d5c  test    al, al
0x180078d5e  jz      loc_180078E3C
0x180078d64  cmp     ebx, 0Bh
0x180078d67  jnz     loc_180078E3C
0x180078d6d  mov     r14, [rdi]
0x180078d70  mov     [rsp+310h+packageFamilyNameLength], 41h ; 'A'
0x180078d78  lea     rcx, [r14+8]
0x180078d7c  cmp     qword ptr [rcx+18h], 7
0x180078d81  jbe     short loc_180078D86
0x180078d83  mov     rcx, [rcx]; packageFullName
0x180078d86  lea     r8, [rbp+210h+packageFamilyName]; packageFamilyName
0x180078d8d  lea     rdx, [rsp+310h+packageFamilyNameLength]; packageFamilyNameLength
0x180078d92  call    cs:__imp_PackageFamilyNameFromFullName
0x180078d99  nop     dword ptr [rax+rax+00h]
0x180078d9e  mov     rcx, [rbp+218h]; this
0x180078da5  test    eax, eax
0x180078da7  js      loc_1800792AA
0x180078dad  mov     rbx, [r12]
0x180078db1  mov     r15, [r12+8]
0x180078db6  cmp     rbx, r15
0x180078db9  jz      loc_180079265
0x180078dbf  mov     [rsp+310h+var_2B8], 41h ; 'A'
0x180078dc7  mov     rcx, [rbx]
0x180078dca  add     rcx, 8
0x180078dce  cmp     qword ptr [rcx+18h], 7
0x180078dd3  jbe     short loc_180078DD8
0x180078dd5  mov     rcx, [rcx]; packageFullName
0x180078dd8  lea     r8, [rbp+210h+var_170]; packageFamilyName
0x180078ddf  lea     rdx, [rsp+310h+var_2B8]; packageFamilyNameLength
0x180078de4  call    cs:__imp_PackageFamilyNameFromFullName
0x180078deb  nop     dword ptr [rax+rax+00h]
0x180078df0  mov     rcx, [rbp+218h]; this
0x180078df7  test    eax, eax
0x180078df9  js      loc_180079250
0x180078dff  lea     rdx, [rbp+210h+var_170]
0x180078e06  lea     rcx, [rbp+210h+packageFamilyName]
0x180078e0d  call    cs:__imp__o__wcsicmp
0x180078e14  nop     dword ptr [rax+rax+00h]
0x180078e19  test    eax, eax
0x180078e1b  jz      short loc_180078E23
0x180078e1d  add     rbx, 8
0x180078e21  jmp     short loc_180078DB6
0x180078e23  mov     rcx, [rbx]
0x180078e26  mov     rax, [rcx]
0x180078e29  mov     rax, [rax+30h]
0x180078e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e32  mov     ebx, eax
0x180078e34  mov     r15d, [rsp+310h+var_2C4]
0x180078e39  xor     r14d, r14d
0x180078e3c  mov     eax, r14d
0x180078e3f  cmp     ebx, 0Eh
0x180078e42  cmovnz  eax, ebx
0x180078e45  test    eax, eax
0x180078e47  jnz     short loc_180078E7C
0x180078e49  mov     [rsp+310h+var_2D0], r14b
0x180078e4e  mov     ecx, 14Ch
0x180078e53  lea     rdx, [rsp+310h+var_2D0]
0x180078e58  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x180078e5f  nop     dword ptr [rax+rax+00h]
0x180078e64  mov     rcx, [rbp+218h]; this
0x180078e6b  test    eax, eax
0x180078e6d  js      loc_1800792BF
0x180078e73  cmp     [rsp+310h+var_2D0], r14b
0x180078e78  setnz   r14b
0x180078e7c  mov     rbx, [rdi]
0x180078e7f  add     rbx, 8
0x180078e83  cmp     qword ptr [rbx+18h], 7
0x180078e88  jbe     short loc_180078E8D
0x180078e8a  mov     rbx, [rbx]
0x180078e8d  mov     rdx, r13
0x180078e90  lea     rcx, [rbp+210h+var_280]
0x180078e94  call    ?Impersonate@LoggedonUserImpersonation@@SA?AU1@PEAX@Z; LoggedonUserImpersonation::Impersonate(void *)
0x180078e99  nop
0x180078e9a  mov     rdx, rbx
0x180078e9d  lea     rcx, [rbp+210h+Src]; Src
0x180078ea1  call    ?GetPackagePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetPackagePath(ushort const *)
0x180078ea6  or      [rsp+310h+var_2C8], 1
0x180078eab  lea     rcx, [rbp+210h+var_280]; this
0x180078eaf  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x180078eb4  nop
0x180078eb5  xor     ebx, ebx
0x180078eb7  mov     [rsp+310h+var_2D0], bl
0x180078ebb  xorps   xmm0, xmm0
0x180078ebe  movups  [rbp+210h+var_1F8], xmm0
0x180078ec2  mov     [rbp+210h+var_1E8], rbx
0x180078ec6  mov     [rbp+210h+var_1E0], rbx
0x180078eca  or      r8, 0FFFFFFFFFFFFFFFFh
0x180078ece  mov     rax, [rsp+310h+var_2A0]
0x180078ed3  inc     r8
0x180078ed6  cmp     [rax+r8*2], bx
0x180078edb  jnz     short loc_180078ED3
0x180078edd  mov     rdx, rax
0x180078ee0  lea     rcx, [rbp+210h+var_1F8]
0x180078ee4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180078ee9  nop
0x180078eea  mov     rcx, [rdi]
0x180078eed  mov     rax, [rcx]
0x180078ef0  mov     rax, [rax+28h]
0x180078ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ef9  test    al, al
0x180078efb  jz      loc_180078FF9
0x180078f01  mov     rbx, [rdi]
0x180078f04  add     rbx, 8
0x180078f08  cmp     qword ptr [rbx+18h], 7
0x180078f0d  jbe     short loc_180078F12
0x180078f0f  mov     rbx, [rbx]
0x180078f12  mov     rcx, r13; hToken
0x180078f15  call    cs:__imp_ImpersonateLoggedOnUser
0x180078f1c  nop     dword ptr [rax+rax+00h]
0x180078f21  mov     rcx, [rbp+218h]; this
0x180078f28  xor     edx, edx
0x180078f2a  test    eax, eax
0x180078f2c  jz      loc_1800792E9
0x180078f32  mov     [rsp+310h+var_2CB], 1
0x180078f37  mov     [rsp+310h+var_2B0], edx
0x180078f3b  xor     r9d, r9d
0x180078f3e  lea     r8, [rsp+310h+var_2B0]
0x180078f43  lea     edx, [r9+5]
0x180078f47  mov     rcx, rbx
0x180078f4a  call    cs:__imp_GetPackagePathByFullName2
0x180078f51  nop     dword ptr [rax+rax+00h]
0x180078f56  cmp     eax, 490h
0x180078f5b  jnz     short loc_180078F74
0x180078f5d  xor     ebx, ebx
0x180078f5f  mov     [rsp+310h+var_2CB], bl
0x180078f63  call    cs:__imp_RevertToSelf
0x180078f6a  nop     dword ptr [rax+rax+00h]
0x180078f6f  jmp     loc_180078FF9
0x180078f74  xor     ebx, ebx
0x180078f76  cmp     eax, 7Ah ; 'z'
0x180078f79  jz      short loc_180078F8A
0x180078f7b  mov     rcx, [rbp+218h]; this
0x180078f82  test    eax, eax
0x180078f84  jnz     loc_1800792D4
0x180078f8a  mov     [rsp+310h+var_2CB], bl
0x180078f8e  call    cs:__imp_RevertToSelf
0x180078f95  nop     dword ptr [rax+rax+00h]
0x180078f9a  mov     rdx, [rdi]
0x180078f9d  add     rdx, 8
0x180078fa1  lea     rcx, [rbp+210h+var_1D8]
0x180078fa5  call    ?GetPackageFamilyNameFromFullName@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; GetPackageFamilyNameFromFullName(std::wstring const &)
0x180078faa  nop
0x180078fab  mov     eax, 1
0x180078fb0  mov     r9d, eax
0x180078fb3  lea     r8, asc_1800D6848; "_"
0x180078fba  mov     edx, eax
0x180078fbc  lea     rcx, [rbp+210h+var_1F8]
0x180078fc0  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KQEBG0@Z; std::wstring::insert(unsigned __int64,ushort const * const,unsigned __int64)
0x180078fc5  lea     r8, [rbp+210h+var_1D8]
0x180078fc9  cmp     [rbp+210h+var_1C0], 7
0x180078fce  cmova   r8, qword ptr [rbp+210h+var_1D8]
0x180078fd3  or      r9, 0FFFFFFFFFFFFFFFFh
0x180078fd7  inc     r9
0x180078fda  cmp     [r8+r9*2], bx
0x180078fdf  jnz     short loc_180078FD7
0x180078fe1  mov     edx, 1
0x180078fe6  lea     rcx, [rbp+210h+var_1F8]
0x180078fea  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KQEBG0@Z; std::wstring::insert(unsigned __int64,ushort const * const,unsigned __int64)
0x180078fef  nop
0x180078ff0  lea     rcx, [rbp+210h+var_1D8]; void *
0x180078ff4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180078ff9  lea     r8, [rbp+210h+var_1F8]
0x180078ffd  cmp     [rbp+210h+var_1E0], 7
0x180079002  cmova   r8, qword ptr [rbp+210h+var_1F8]
0x180079007  lea     rax, [rsp+310h+var_2D0]
0x18007900c  mov     [rsp+310h+var_2F0], rax
0x180079011  mov     r9b, r14b
0x180079014  lea     rdx, [rbp+210h+Src]
0x180079018  lea     rcx, [rbp+210h+var_1B8]
0x18007901c  call    ?GetPackageHivePath@OfflineRegistry@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG_NAEA_N@Z; OfflineRegistry::GetPackageHivePath(std::wstring const &,ushort const *,bool,bool &)
0x180079021  nop
0x180079022  mov     rdx, r13
0x180079025  lea     rcx, [rbp+210h+var_290]
0x180079029  call    ?Impersonate@LoggedonUserImpersonation@@SA?AU1@PEAX@Z; LoggedonUserImpersonation::Impersonate(void *)
0x18007902e  nop
0x18007902f  lea     rcx, [rbp+210h+var_1B8]
0x180079033  cmp     [rbp+210h+var_1A0], 7
0x180079038  cmova   rcx, [rbp+210h+var_1B8]; unsigned __int16 *
0x18007903d  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x180079042  test    al, al
0x180079044  jz      loc_1800791D7
0x18007904a  lea     rdx, [rbp+210h+Src]
0x18007904e  cmp     [rsi+38h], bl
0x180079051  jnz     loc_18007917F
0x180079057  cmp     [rbp+210h+var_180], 7
0x18007905f  cmova   rdx, [rbp+210h+Src]
0x180079064  xorps   xmm0, xmm0
0x180079067  movups  [rbp+210h+var_1D8], xmm0
0x18007906b  mov     [rbp+210h+var_1C8], rbx
0x18007906f  mov     [rbp+210h+var_1C0], rbx
0x180079073  or      r8, 0FFFFFFFFFFFFFFFFh
0x180079077  inc     r8
0x18007907a  cmp     [rdx+r8*2], bx
0x18007907f  jnz     short loc_180079077
0x180079081  lea     rcx, [rbp+210h+var_1D8]
0x180079085  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007908a  mov     r9d, 2
0x180079090  lea     r8, [rbp+210h+var_1D8]
0x180079094  mov     rdx, r13
0x180079097  lea     rcx, [rbp+210h+var_230]
0x18007909b  call    ??0TokenMap@@QEAA@PEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TokenMapFlags@@@Z; TokenMap::TokenMap(void *,std::wstring,TokenMapFlags)
0x1800790a0  mov     rbx, rax
0x1800790a3  xor     ecx, ecx
0x1800790a5  cmp     [rsi+38h], cl
0x1800790a8  jz      short loc_1800790BA
0x1800790aa  mov     rdx, rax
0x1800790ad  mov     rcx, rsi
0x1800790b0  call    ??4TokenMap@@QEAAAEAV0@$$QEAV0@@Z; TokenMap::operator=(TokenMap &&)
0x1800790b5  jmp     loc_180079172
0x1800790ba  mov     qword ptr [rsp+310h+var_2B8], rsi
0x1800790bf  mov     rax, [rax]
0x1800790c2  mov     [rsi], rax
0x1800790c5  mov     [rbx], rcx
0x1800790c8  mov     rax, [rbx+8]
0x1800790cc  mov     [rbx+8], rcx
0x1800790d0  mov     [rsi+8], rax
0x1800790d4  mov     al, [rbx+10h]
0x1800790d7  mov     [rsi+10h], al
0x1800790da  mov     al, [rbx+11h]
0x1800790dd  mov     [rsi+11h], al
0x1800790e0  mov     [rsi+18h], rcx
0x1800790e4  mov     [rsi+20h], rcx
0x1800790e8  mov     ecx, 98h; Size
0x1800790ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800790f2  mov     rcx, rax
0x1800790f5  mov     [rax], rax
0x1800790f8  mov     [rax+8], rax
0x1800790fc  mov     [rax+10h], rax
0x180079100  mov     word ptr [rax+18h], 101h
0x180079106  mov     [rsi+18h], rax
0x18007910a  mov     rax, [rbx+18h]
0x18007910e  mov     [rsi+18h], rax
0x180079112  mov     [rbx+18h], rcx
0x180079116  mov     rcx, [rsi+20h]
0x18007911a  mov     rax, [rbx+20h]
0x18007911e  mov     [rsi+20h], rax
0x180079122  mov     [rbx+20h], rcx
0x180079126  xor     eax, eax
0x180079128  mov     [rsi+28h], rax
0x18007912c  mov     [rsi+30h], rax
0x180079130  mov     ecx, 98h; Size
0x180079135  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007913a  mov     rcx, rax
0x18007913d  mov     [rax], rax
0x180079140  mov     [rax+8], rax
0x180079144  mov     [rax+10h], rax
0x180079148  mov     word ptr [rax+18h], 101h
0x18007914e  mov     [rsi+28h], rax
0x180079152  mov     rax, [rbx+28h]
0x180079156  mov     [rsi+28h], rax
0x18007915a  mov     [rbx+28h], rcx
0x18007915e  mov     rcx, [rsi+30h]
0x180079162  mov     rax, [rbx+30h]
0x180079166  mov     [rsi+30h], rax
0x18007916a  mov     [rbx+30h], rcx
0x18007916e  mov     byte ptr [rsi+38h], 1
0x180079172  lea     rcx, [rbp+210h+var_230]; this
0x180079176  call    ??1TokenMap@@QEAA@XZ; TokenMap::~TokenMap(void)
0x18007917b  xor     ebx, ebx
0x18007917d  jmp     short loc_180079187
  ... truncated ...
```
