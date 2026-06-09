# Discovery::IsValidAuthority(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,AuthenticationContext const &)

- ea: `0x14001088c`
- end: `0x140010cbe`
- name: `?IsValidAuthority@Discovery@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVAuthenticationContext@@@Z`
- size: `1074`
- prototype: `char __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007d8c`

## callees

- `0x140001b60`
- `0x140003044`
- `0x1400032ec`
- `0x140005458`
- `0x140005c80`
- `0x1400061dc`
- `0x14000d310`
- `0x14000f058`
- `0x14000f0f4`
- `0x14000f170`
- `0x14000f1b8`
- `0x14000fa10`
- `0x14000fab8`
- `0x1400100e4`
- `0x140010228`
- `0x1400102e0`
- `0x140010378`
- `0x14001088c`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140010a3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140010b2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140010a3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140010b2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400108e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140010a9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400108e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140010a9e`

## string_xrefs

- `0x14001091f`: `login.microsoftonline.com`
- `0x140010947`: `login.chinacloudapi.cn`
- `0x140010a0f`: `login-us.microsoftonline.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char __fastcall Discovery::IsValidAuthority(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 *Lower; // rax
  volatile signed __int32 *v13; // rdx
  volatile signed __int32 *v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  unsigned __int64 v17; // rcx
  char v18; // si
  __int64 v19; // r9
  unsigned __int64 v20; // r10
  _QWORD *v21; // rax
  __int64 v22; // r14
  __int64 v23; // rdi
  _QWORD *AuthEndpoint; // rbx
  volatile signed __int32 *v25; // rdx
  _QWORD *v26; // rdx
  __int64 v27; // rbx
  volatile signed __int32 *v28; // rdx
  volatile signed __int32 *v30; // [rsp+30h] [rbp-39h] BYREF
  volatile signed __int32 *v31; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v32[2]; // [rsp+40h] [rbp-29h] BYREF
  void *v33; // [rsp+50h] [rbp-19h] BYREF
  __int64 v34; // [rsp+58h] [rbp-11h]
  _QWORD v35[2]; // [rsp+60h] [rbp-9h] BYREF
  char *v36[4]; // [rsp+70h] [rbp+7h] BYREF

  Url::Url((Url *)&v33);
  Url::CreateUrl((__int64)&v33, a1);
  v35[0] = &Discovery::s_CriticalSection;
  EnterCriticalSection(&Discovery::s_CriticalSection);
  if ( !qword_1400460B0 )
  {
    std::wstring::wstring(v36, L"login.windows.net");
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      v4,
      (__int64)v32,
      v36);
    std::wstring::~wstring(v36);
    std::wstring::wstring(v36, L"login.microsoftonline.com");
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      v5,
      (__int64)v32,
      v36);
    std::wstring::~wstring(v36);
    std::wstring::wstring(v36, L"login.chinacloudapi.cn");
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      v6,
      (__int64)v32,
      v36);
    std::wstring::~wstring(v36);
    std::wstring::wstring(v36, L"login.partner.microsoftonline.cn");
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      v7,
      (__int64)v32,
      v36);
    std::wstring::~wstring(v36);
    std::wstring::wstring(v36, L"login.microsoftonline.de");
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      v8,
      (__int64)v32,
      v36);
    std::wstring::~wstring(v36);
    std::wstring::wstring(v36, L"login.microsoftonline.us");
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      v9,
      (__int64)v32,
      v36);
    std::wstring::~wstring(v36);
    std::wstring::wstring(v36, L"login.cloudgovapi.us");
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      v10,
      (__int64)v32,
      v36);
    std::wstring::~wstring(v36);
    std::wstring::wstring(v36, L"login-us.microsoftonline.com");
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      v11,
      (__int64)v32,
      v36);
    std::wstring::~wstring(v36);
  }
  LeaveCriticalSection(&Discovery::s_CriticalSection);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v30,
    *(_QWORD *)(v34 + 24),
    *(unsigned int *)(v34 + 32));
  Lower = (__int64 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v30);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v31,
    Lower);
  v13 = v30 - 6;
  if ( _InterlockedDecrement(v30 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
  v35[0] = &Discovery::s_CriticalSection;
  EnterCriticalSection(&Discovery::s_CriticalSection);
  v14 = v31;
  v15 = std::wstring::wstring(v36, v31);
  if ( v15[3] <= 7u )
    v16 = v15;
  else
    v16 = (_QWORD *)*v15;
  v17 = 0;
  v18 = 1;
  v19 = 0xCBF29CE484222325uLL;
  v20 = 2LL * v15[2];
  if ( v20 )
  {
    do
      v19 = 0x100000001B3LL * (*((unsigned __int8 *)v16 + v17++) ^ (unsigned __int64)v19);
    while ( v17 < v20 );
  }
  v21 = std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
          v17,
          v35,
          (__int64)v15,
          v19);
  v22 = qword_1400460A8;
  if ( v21[1] )
    v22 = v21[1];
  std::wstring::~wstring(v36);
  v23 = qword_1400460A8;
  LeaveCriticalSection(&Discovery::s_CriticalSection);
  if ( _InterlockedDecrement(v14 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
  if ( v22 == v23 )
  {
    Discovery::GetInstanceDiscoveryEndpoint((void **)&v31);
    AuthEndpoint = Discovery::GetAuthEndpoint(v32, (__int64)&v33);
    v30 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v30,
            (__int64)&dword_14003353C) )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v30, &dword_14003353C, 0);
    Discovery::GetTenantDiscoveryEndpoint(v35, (__int64 *)&v31, &v30, (__int64)AuthEndpoint, a2);
    v25 = v30 - 6;
    if ( _InterlockedDecrement(v30 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v25 + 8LL))(*(_QWORD *)v25);
    v26 = (_QWORD *)(v32[0] - 24LL);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v32[0] - 24LL + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
    v27 = v35[0];
    if ( *(_DWORD *)(v35[0] - 16LL) )
      Discovery::AddValidHostToList((const struct Url *)&v33);
    else
      v18 = 0;
    if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v27 - 24) + 8LL))(*(_QWORD *)(v27 - 24));
    v28 = v31 - 6;
    if ( _InterlockedDecrement(v31 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 8LL))(*(_QWORD *)v28);
  }
  Url::~Url(&v33);
  return v18;
}

```

## disassembly

```asm
0x14001088c  mov     [rsp-8+arg_10], rbx
0x140010891  mov     [rsp-8+arg_18], rsi
0x140010896  push    rbp
0x140010897  push    rdi
0x140010898  push    r13
0x14001089a  push    r14
0x14001089c  push    r15
0x14001089e  lea     rbp, [rsp-37h]
0x1400108a3  sub     rsp, 0A0h
0x1400108aa  mov     rax, cs:__security_cookie
0x1400108b1  xor     rax, rsp
0x1400108b4  mov     [rbp+57h+var_30], rax
0x1400108b8  mov     r15, rdx
0x1400108bb  mov     rbx, rcx
0x1400108be  lea     rcx, [rbp+57h+var_70]; this
0x1400108c2  call    ??0Url@@QEAA@XZ; Url::Url(void)
0x1400108c7  nop
0x1400108c8  mov     rdx, rbx
0x1400108cb  lea     rcx, [rbp+57h+var_70]
0x1400108cf  call    ?CreateUrl@Url@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Url::CreateUrl(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400108d4  lea     rbx, ?s_CriticalSection@Discovery@@0VCCriticalSection@ATL@@A; ATL::CCriticalSection Discovery::s_CriticalSection
0x1400108db  mov     [rbp+57h+var_60], rbx
0x1400108df  mov     rcx, rbx; lpCriticalSection
0x1400108e2  call    cs:__imp_EnterCriticalSection
0x1400108e8  nop
0x1400108e9  cmp     cs:qword_1400460B0, 0
0x1400108f1  jnz     loc_140010A38
0x1400108f7  lea     rdx, aLoginWindowsNe; "login.windows.net"
0x1400108fe  lea     rcx, [rbp+57h+var_50]
0x140010902  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140010907  nop
0x140010908  lea     r8, [rbp+57h+var_50]
0x14001090c  lea     rdx, [rbp+57h+var_80]
0x140010910  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x140010915  nop
0x140010916  lea     rcx, [rbp+57h+var_50]
0x14001091a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001091f  lea     rdx, aLoginMicrosoft_0; "login.microsoftonline.com"
0x140010926  lea     rcx, [rbp+57h+var_50]
0x14001092a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14001092f  nop
0x140010930  lea     r8, [rbp+57h+var_50]
0x140010934  lea     rdx, [rbp+57h+var_80]
0x140010938  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x14001093d  nop
0x14001093e  lea     rcx, [rbp+57h+var_50]
0x140010942  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010947  lea     rdx, aLoginChinaclou; "login.chinacloudapi.cn"
0x14001094e  lea     rcx, [rbp+57h+var_50]
0x140010952  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140010957  nop
0x140010958  lea     r8, [rbp+57h+var_50]
0x14001095c  lea     rdx, [rbp+57h+var_80]
0x140010960  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x140010965  nop
0x140010966  lea     rcx, [rbp+57h+var_50]
0x14001096a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001096f  lea     rdx, aLoginPartnerMi; "login.partner.microsoftonline.cn"
0x140010976  lea     rcx, [rbp+57h+var_50]
0x14001097a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14001097f  nop
0x140010980  lea     r8, [rbp+57h+var_50]
0x140010984  lea     rdx, [rbp+57h+var_80]
0x140010988  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x14001098d  nop
0x14001098e  lea     rcx, [rbp+57h+var_50]
0x140010992  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010997  lea     rdx, aLoginMicrosoft_1; "login.microsoftonline.de"
0x14001099e  lea     rcx, [rbp+57h+var_50]
0x1400109a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400109a7  nop
0x1400109a8  lea     r8, [rbp+57h+var_50]
0x1400109ac  lea     rdx, [rbp+57h+var_80]
0x1400109b0  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x1400109b5  nop
0x1400109b6  lea     rcx, [rbp+57h+var_50]
0x1400109ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400109bf  lea     rdx, aLoginMicrosoft; "login.microsoftonline.us"
0x1400109c6  lea     rcx, [rbp+57h+var_50]
0x1400109ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400109cf  nop
0x1400109d0  lea     r8, [rbp+57h+var_50]
0x1400109d4  lea     rdx, [rbp+57h+var_80]
0x1400109d8  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x1400109dd  nop
0x1400109de  lea     rcx, [rbp+57h+var_50]
0x1400109e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400109e7  lea     rdx, aLoginCloudgova; "login.cloudgovapi.us"
0x1400109ee  lea     rcx, [rbp+57h+var_50]
0x1400109f2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400109f7  nop
0x1400109f8  lea     r8, [rbp+57h+var_50]
0x1400109fc  lea     rdx, [rbp+57h+var_80]
0x140010a00  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x140010a05  nop
0x140010a06  lea     rcx, [rbp+57h+var_50]
0x140010a0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010a0f  lea     rdx, aLoginUsMicroso; "login-us.microsoftonline.com"
0x140010a16  lea     rcx, [rbp+57h+var_50]
0x140010a1a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140010a1f  nop
0x140010a20  lea     r8, [rbp+57h+var_50]
0x140010a24  lea     rdx, [rbp+57h+var_80]
0x140010a28  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x140010a2d  nop
0x140010a2e  lea     rcx, [rbp+57h+var_50]
0x140010a32  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010a37  nop
0x140010a38  mov     rcx, rbx; lpCriticalSection
0x140010a3b  call    cs:__imp_LeaveCriticalSection
0x140010a41  mov     rdx, [rbp+57h+var_68]
0x140010a45  mov     r8d, [rdx+20h]
0x140010a49  mov     rdx, [rdx+18h]
0x140010a4d  lea     rcx, [rbp+57h+var_90]
0x140010a51  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x140010a56  nop
0x140010a57  lea     rcx, [rbp+57h+var_90]
0x140010a5b  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x140010a60  mov     rdx, rax
0x140010a63  lea     rcx, [rbp+57h+var_88]
0x140010a67  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140010a6c  nop
0x140010a6d  mov     rdx, [rbp+57h+var_90]
0x140010a71  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140010a75  or      r13d, 0FFFFFFFFh
0x140010a79  mov     eax, r13d
0x140010a7c  lock xadd [rdx+10h], eax
0x140010a81  add     eax, r13d
0x140010a84  test    eax, eax
0x140010a86  jg      short loc_140010A97
0x140010a88  mov     rcx, [rdx]
0x140010a8b  mov     rax, [rcx]
0x140010a8e  mov     rax, [rax+8]
0x140010a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a97  mov     [rbp+57h+var_60], rbx
0x140010a9b  mov     rcx, rbx; lpCriticalSection
0x140010a9e  call    cs:__imp_EnterCriticalSection
0x140010aa4  nop
0x140010aa5  mov     rbx, [rbp+57h+var_88]
0x140010aa9  mov     rdx, rbx
0x140010aac  lea     rcx, [rbp+57h+var_50]
0x140010ab0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140010ab5  mov     r8, rax
0x140010ab8  mov     r10, [rax+10h]
0x140010abc  cmp     qword ptr [rax+18h], 7
0x140010ac1  jbe     short loc_140010AC8
0x140010ac3  mov     rdx, [rax]
0x140010ac6  jmp     short loc_140010ACB
0x140010ac8  mov     rdx, r8
0x140010acb  xor     ecx, ecx
0x140010acd  lea     esi, [rcx+1]
0x140010ad0  mov     r9, 0CBF29CE484222325h
0x140010ada  add     r10, r10
0x140010add  jz      short loc_140010AFC
0x140010adf  movzx   eax, byte ptr [rdx+rcx]
0x140010ae3  xor     r9, rax
0x140010ae6  mov     r11, 100000001B3h
0x140010af0  imul    r9, r11
0x140010af4  add     rcx, rsi
0x140010af7  cmp     rcx, r10
0x140010afa  jb      short loc_140010ADF
0x140010afc  lea     rdx, [rbp+57h+var_60]
0x140010b00  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x140010b05  mov     r14, cs:qword_1400460A8
0x140010b0c  cmp     qword ptr [rax+8], 0
0x140010b11  cmovnz  r14, [rax+8]
0x140010b16  lea     rcx, [rbp+57h+var_50]
0x140010b1a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010b1f  mov     rdi, cs:qword_1400460A8
0x140010b26  lea     rcx, ?s_CriticalSection@Discovery@@0VCCriticalSection@ATL@@A; lpCriticalSection
0x140010b2d  call    cs:__imp_LeaveCriticalSection
0x140010b33  nop
0x140010b34  lea     rdx, [rbx-18h]
0x140010b38  mov     eax, r13d
0x140010b3b  lock xadd [rdx+10h], eax
0x140010b40  add     eax, r13d
0x140010b43  test    eax, eax
0x140010b45  jg      short loc_140010B56
0x140010b47  mov     rcx, [rdx]
0x140010b4a  mov     rax, [rcx]
0x140010b4d  mov     rax, [rax+8]
0x140010b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b56  cmp     r14, rdi
0x140010b59  jnz     loc_140010C8A
0x140010b5f  lea     rcx, [rbp+57h+var_88]
0x140010b63  call    ?GetInstanceDiscoveryEndpoint@Discovery@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; Discovery::GetInstanceDiscoveryEndpoint(void)
0x140010b68  nop
0x140010b69  lea     rdx, [rbp+57h+var_70]
0x140010b6d  lea     rcx, [rbp+57h+var_80]
0x140010b71  call    ?GetAuthEndpoint@Discovery@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVUrl@@@Z; Discovery::GetAuthEndpoint(Url const &)
0x140010b76  mov     rbx, rax
0x140010b79  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010b80  mov     rax, [rcx+18h]
0x140010b84  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b90  add     rax, 18h
0x140010b94  mov     [rbp+57h+var_90], rax
0x140010b98  lea     rdx, dword_14003353C
0x140010b9f  lea     rcx, [rbp+57h+var_90]
0x140010ba3  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140010ba8  test    al, al
0x140010baa  jnz     short loc_140010BC0
0x140010bac  xor     r8d, r8d
0x140010baf  lea     rdx, dword_14003353C
0x140010bb6  lea     rcx, [rbp+57h+var_90]
0x140010bba  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140010bbf  nop
0x140010bc0  mov     [rsp+0C0h+var_A0], r15
0x140010bc5  mov     r9, rbx
0x140010bc8  lea     r8, [rbp+57h+var_90]
0x140010bcc  lea     rdx, [rbp+57h+var_88]
0x140010bd0  lea     rcx, [rbp+57h+var_60]
0x140010bd4  call    ?GetTenantDiscoveryEndpoint@Discovery@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@00AEBVAuthenticationContext@@@Z; Discovery::GetTenantDiscoveryEndpoint(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,AuthenticationContext const &)
0x140010bd9  nop
0x140010bda  mov     rdx, [rbp+57h+var_90]
0x140010bde  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140010be2  mov     eax, r13d
0x140010be5  lock xadd [rdx+10h], eax
0x140010bea  add     eax, r13d
0x140010bed  test    eax, eax
0x140010bef  jg      short loc_140010C01
0x140010bf1  mov     rcx, [rdx]
0x140010bf4  mov     rax, [rcx]
0x140010bf7  mov     rax, [rax+8]
0x140010bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c00  nop
0x140010c01  mov     rdx, [rbp+57h+var_80]
0x140010c05  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140010c09  mov     eax, r13d
0x140010c0c  lock xadd [rdx+10h], eax
0x140010c11  add     eax, r13d
0x140010c14  test    eax, eax
0x140010c16  jg      short loc_140010C27
0x140010c18  mov     rcx, [rdx]
0x140010c1b  mov     rax, [rcx]
0x140010c1e  mov     rax, [rax+8]
0x140010c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c27  mov     rbx, [rbp+57h+var_60]
0x140010c2b  cmp     dword ptr [rbx-10h], 0
0x140010c2f  jnz     short loc_140010C36
0x140010c31  xor     sil, sil
0x140010c34  jmp     short loc_140010C40
0x140010c36  lea     rcx, [rbp+57h+var_70]; struct Url *
0x140010c3a  call    ?AddValidHostToList@Discovery@@SAXAEBVUrl@@@Z; Discovery::AddValidHostToList(Url const &)
0x140010c3f  nop
0x140010c40  lea     rdx, [rbx-18h]
0x140010c44  mov     eax, r13d
0x140010c47  lock xadd [rdx+10h], eax
0x140010c4c  add     eax, r13d
0x140010c4f  test    eax, eax
0x140010c51  jg      short loc_140010C63
0x140010c53  mov     rcx, [rdx]
0x140010c56  mov     rax, [rcx]
0x140010c59  mov     rax, [rax+8]
0x140010c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c62  nop
0x140010c63  mov     rdx, [rbp+57h+var_88]
0x140010c67  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140010c6b  mov     eax, r13d
0x140010c6e  lock xadd [rdx+10h], eax
0x140010c73  add     eax, r13d
0x140010c76  test    eax, eax
0x140010c78  jg      short loc_140010C8A
0x140010c7a  mov     rcx, [rdx]
0x140010c7d  mov     r8, [rcx]
0x140010c80  mov     rax, [r8+8]
0x140010c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c89  nop
0x140010c8a  lea     rcx, [rbp+57h+var_70]; this
0x140010c8e  call    ??1Url@@QEAA@XZ; Url::~Url(void)
0x140010c93  mov     al, sil
0x140010c96  mov     rcx, [rbp+57h+var_30]
0x140010c9a  xor     rcx, rsp; StackCookie
0x140010c9d  call    __security_check_cookie
0x140010ca2  lea     r11, [rsp+0C0h+var_20]
0x140010caa  mov     rbx, [r11+40h]
0x140010cae  mov     rsi, [r11+48h]
0x140010cb2  mov     rsp, r11
0x140010cb5  pop     r15
0x140010cb7  pop     r14
0x140010cb9  pop     r13
0x140010cbb  pop     rdi
0x140010cbc  pop     rbp
0x140010cbd  retn
```
