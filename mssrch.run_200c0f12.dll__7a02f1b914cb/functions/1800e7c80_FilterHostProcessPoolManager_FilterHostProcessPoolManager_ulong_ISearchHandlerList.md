# FilterHostProcessPoolManager::FilterHostProcessPoolManager(ulong,ISearchHandlerList *)

- ea: `0x1800e7c80`
- end: `0x1800e820c`
- name: `??0FilterHostProcessPoolManager@@QEAA@KPEAUISearchHandlerList@@@Z`
- size: `1420`
- prototype: `FilterHostProcessPoolManager *__fastcall(FilterHostProcessPoolManager *__hidden this, unsigned int, struct ISearchHandlerList *)`
- caller_count: `3`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012365c`
- `0x1801a809c`
- `0x1801a81cc`

## callees

- `0x18000efcc`
- `0x18001b470`
- `0x1800314d0`
- `0x18006ed00`
- `0x18008a0c0`
- `0x1800e2374`
- `0x1800e7000`
- `0x1800e7370`
- `0x1800e73b4`
- `0x1800e7420`
- `0x1800e7c80`
- `0x1800e95f0`
- `0x1800e995c`
- `0x1800f6254`
- `0x1800fe17c`
- `0x18010c02c`
- `0x1801244c0`
- `0x1801a7ddc`
- `0x1801a8020`
- `0x1801a838c`
- `0x1801a8404`
- `0x1801a8844`
- `0x1801a89d0`
- `0x1801aa3e0`
- `0x1801aa5b4`
- `0x1801aa640`
- `0x1801aaacc`
- `0x1801aab20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800e7d00`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800e7d00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e81c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e81d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e81c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e81d7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800e7f35`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800e7f35`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800e7f5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800e7f5d`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateWindowStationW` at `0x1800e7fea`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateWindowStationW` at `0x1800e7fea`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SetProcessWindowStation` at `0x1800e8026`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SetProcessWindowStation` at `0x1800e8026`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateDesktopW` at `0x1800e811b`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateDesktopW` at `0x1800e811b`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
FilterHostProcessPoolManager *__fastcall FilterHostProcessPoolManager::FilterHostProcessPoolManager(
        FilterHostProcessPoolManager *this,
        unsigned int a2,
        struct ISearchHandlerList *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  _QWORD *v8; // rcx
  int PluginResourceManager; // eax
  const char *v10; // r9
  const char *v11; // r9
  const struct ATL::CSid *v12; // rax
  unsigned __int8 v13; // r9
  FilterHostUtils *v14; // rcx
  bool v15; // r8
  const wchar_t *v16; // r8
  const char *v17; // r9
  unsigned __int8 v18; // r9
  bool v19; // r8
  HWINSTA v20; // rax
  const char *v21; // r9
  HWINSTA v22; // rcx
  const char *v23; // r9
  const struct ATL::CSid *v24; // rax
  unsigned __int8 v25; // r9
  FilterHostUtils *v26; // rcx
  const wchar_t *v27; // r8
  unsigned __int8 v28; // r9
  bool v29; // r8
  HDESK v30; // rax
  const char *v31; // r9
  ACCESS_MASK dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  PSID pSid[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v35[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v36[2]; // [rsp+50h] [rbp-B0h] BYREF
  void **v37; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject[2]; // [rsp+68h] [rbp-98h]
  _QWORD v39[2]; // [rsp+78h] [rbp-88h] BYREF
  char v40; // [rsp+88h] [rbp-78h]
  int v41; // [rsp+8Ch] [rbp-74h]
  __int128 v42; // [rsp+90h] [rbp-70h]
  __int64 v43; // [rsp+A0h] [rbp-60h]
  int v44; // [rsp+A8h] [rbp-58h]
  _QWORD v45[2]; // [rsp+B0h] [rbp-50h] BYREF
  char v46; // [rsp+C0h] [rbp-40h]
  int v47; // [rsp+C4h] [rbp-3Ch]
  __int128 v48; // [rsp+C8h] [rbp-38h]
  __int64 v49; // [rsp+D8h] [rbp-28h]
  int v50; // [rsp+E0h] [rbp-20h]
  FilterHostProcessPoolManager *v51; // [rsp+E8h] [rbp-18h]
  struct _SECURITY_ATTRIBUTES lpsa; // [rsp+F0h] [rbp-10h] BYREF
  void **v53; // [rsp+108h] [rbp+8h] BYREF
  struct _SECURITY_ATTRIBUTES sa; // [rsp+118h] [rbp+18h] BYREF
  void **v55; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v56[128]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v51 = this;
  winrt::impl::producers_base<FilterHostProcessPoolManager,std::tuple<IFilterHostProcessPoolManager,IFilterHostManager>>::producers_base<FilterHostProcessPoolManager,std::tuple<IFilterHostProcessPoolManager,IFilterHostManager>>();
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 3) = 1;
  *(_QWORD *)this = &FilterHostProcessPoolManager::`vftable'{for `winrt::impl::producer_convert<FilterHostProcessPoolManager,IFilterHostProcessPoolManager,void>'};
  *((_QWORD *)this + 1) = &winrt::impl::heap_implements<SingleProcessPool>::`vftable'{for `winrt::impl::producer_convert<FilterHostProcessPoolManager,IFilterHostManager,void>'};
  *((_QWORD *)this + 2) = &winrt::impl::heap_implements<DedicatedFilterTypePool>::`vftable';
  *((_BYTE *)this + 32) = 1;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this + 1, 0, 0);
  pSid[1] = (char *)this + 80;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  std::list<std::pair<std::wstring const,winrt::com_ptr<IFilterHostProcess>>>::_Alloc_sentinel_and_proxy((char *)this + 88);
  std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>((char *)this + 104);
  *((_QWORD *)this + 16) = 7;
  *((_QWORD *)this + 17) = 8;
  *((_DWORD *)this + 20) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,PluginResourceManager::PluginAckInfo>>>>>>::_Assign_grow(
    v6,
    16,
    *((_QWORD *)this + 11));
  *((_DWORD *)this + 36) = 120000;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 21) = &RestrictedToken::`vftable';
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 3;
  v7 = 30000;
  if ( a2 >= 0x7530 )
    v7 = a2;
  *((_DWORD *)this + 36) = v7;
  v8 = (_QWORD *)((char *)this + 248);
  if ( a3 )
  {
    *v8 = a3;
    Microsoft::WRL::ComPtr<IFilterHost>::InternalAddRef(v8);
  }
  if ( *((_QWORD *)this + 32) )
    winrt::com_ptr<IDatabase>::unconditional_release_ref((char *)this + 256);
  PluginResourceManager = CreatePluginResourceManager((struct IPluginResourceManager **)this + 32);
  if ( PluginResourceManager < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx",
      (const char *)(unsigned int)PluginResourceManager,
      dwDesiredAccess);
  v37 = &UserToken::`vftable';
  *(_OWORD *)hObject = 0;
  if ( !UserToken::OpenCurrentProcToken((UserToken *)&v37, 0x8Fu) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx",
      v10);
  *((_QWORD *)this + 24) = &v37;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *(SID *)((char *)this + 232) = RestrictedToken::BuiltInSidBase;
  *((_DWORD *)this + 61) = 545;
  if ( !RestrictedToken::CreateToken((FilterHostProcessPoolManager *)((char *)this + 168)) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx",
      v11);
  if ( IsWindowStationFeatureAvailable() )
  {
    v45[1] = 0;
    v46 = 0;
    v47 = 2;
    v45[0] = &ATL::CDacl::`vftable';
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v12 = (const struct ATL::CSid *)ATL::Sids::World(v56);
    ATL::CDacl::AddAllowedAce((ATL::CDacl *)v45, v12, 0x11Bu, v13);
    ATL::CSid::~CSid((ATL::CSid *)v56);
    pSid[0] = 0;
    if ( FilterHostUtils::ShouldRunFilterHostInAppContainer(v14) )
    {
      pSid[0] = 0;
      if ( !ConvertStringSidToSidW(
              L"S-1-15-2-2922806004-2201342939-3402379583-417094435-271215634-1891370830-1688951784",
              pSid) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xFC,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx",
          v17);
      ATL::CSid::CSid((ATL::CSid *)v56, (const struct _SID *)pSid[0], v16);
      ATL::CDacl::AddAllowedAce((ATL::CDacl *)v45, (const struct ATL::CSid *)v56, 0x11Bu, v18);
      ATL::CSid::~CSid((ATL::CSid *)v56);
    }
    v36[0] = &ATL::CSecurityDesc::`vftable';
    v36[1] = 0;
    ATL::CSecurityDesc::SetDacl((ATL::CSecurityDesc *)v36, (const struct ATL::CDacl *)v45, v15);
    ATL::CSecurityAttributes::CSecurityAttributes(
      (ATL::CSecurityAttributes *)&sa,
      (const struct ATL::CSecurityDesc *)v36,
      v19);
    v20 = CreateWindowStationW(L"msswindowstation", 0, 0x11Bu, &sa);
    wil::details::unique_storage<wil::details::resource_policy<HWINSTA__ *,int (*)(HWINSTA__ *),&int CloseWindowStation(HWINSTA__ *),wistd::integral_constant<unsigned __int64,0>,HWINSTA__ *,HWINSTA__ *,0,std::nullptr_t>>::reset(
      (char *)this + 152,
      v20);
    v22 = (HWINSTA)*((_QWORD *)this + 19);
    if ( !v22 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx",
        v21);
    if ( !SetProcessWindowStation(v22) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x112,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx",
        v23);
    v39[1] = 0;
    v40 = 0;
    v41 = 2;
    v39[0] = &ATL::CDacl::`vftable';
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v24 = (const struct ATL::CSid *)ATL::Sids::World(v56);
    ATL::CDacl::AddAllowedAce((ATL::CDacl *)v39, v24, 0xC3u, v25);
    ATL::CSid::~CSid((ATL::CSid *)v56);
    if ( FilterHostUtils::ShouldRunFilterHostInAppContainer(v26) )
    {
      ATL::CSid::CSid((ATL::CSid *)v56, (const struct _SID *)pSid[0], v27);
      ATL::CDacl::AddAllowedAce((ATL::CDacl *)v39, (const struct ATL::CSid *)v56, 0xC3u, v28);
      ATL::CSid::~CSid((ATL::CSid *)v56);
    }
    v35[0] = &ATL::CSecurityDesc::`vftable';
    v35[1] = 0;
    ATL::CSecurityDesc::SetDacl((ATL::CSecurityDesc *)v35, (const struct ATL::CDacl *)v39, (bool)v27);
    ATL::CSecurityAttributes::CSecurityAttributes(
      (ATL::CSecurityAttributes *)&lpsa,
      (const struct ATL::CSecurityDesc *)v35,
      v29);
    v30 = CreateDesktopW(L"mssrestricteddesk", 0, 0, 0, 3u, &lpsa);
    wil::details::unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&int CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>::reset(
      (char *)this + 160,
      v30);
    if ( !*((_QWORD *)this + 20) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx",
        v31);
    v53 = &ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v53);
    v35[0] = &ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v35);
    ATL::CDacl::~CDacl((ATL::CDacl *)v39);
    v55 = &ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v55);
    v36[0] = &ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v36);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(pSid);
    ATL::CDacl::~CDacl((ATL::CDacl *)v45);
  }
  *((_BYTE *)this + 32) = *((_QWORD *)this + 20) != 0;
  v37 = &UserToken::`vftable';
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  hObject[0] = 0;
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  return this;
}

```

## disassembly

```asm
0x1800e7c80  mov     [rsp-8+arg_8], rbx
0x1800e7c85  mov     [rsp-8+arg_10], rsi
0x1800e7c8a  push    rbp
0x1800e7c8b  push    rdi
0x1800e7c8c  push    r12
0x1800e7c8e  push    r14
0x1800e7c90  push    r15
0x1800e7c92  lea     rbp, [rsp-0D0h]
0x1800e7c9a  sub     rsp, 1D0h
0x1800e7ca1  mov     rax, cs:__security_cookie
0x1800e7ca8  xor     rax, rsp
0x1800e7cab  mov     [rbp+0F0h+var_30], rax
0x1800e7cb2  mov     r15, r8
0x1800e7cb5  mov     esi, edx
0x1800e7cb7  mov     r14, rcx
0x1800e7cba  mov     [rbp+0F0h+var_108], rcx
0x1800e7cbe  call    ??0?$producers_base@UFilterHostProcessPoolManager@@V?$tuple@UIFilterHostProcessPoolManager@@UIFilterHostManager@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<FilterHostProcessPoolManager,std::tuple<IFilterHostProcessPoolManager,IFilterHostManager>>::producers_base<FilterHostProcessPoolManager,std::tuple<IFilterHostProcessPoolManager,IFilterHostManager>>(void)
0x1800e7cc3  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800e7cca  mov     qword ptr [r14+18h], 1
0x1800e7cd2  lea     rax, ??_7FilterHostProcessPoolManager@@6B?$producer_convert@UFilterHostProcessPoolManager@@UIFilterHostProcessPoolManager@@X@impl@winrt@@@; const FilterHostProcessPoolManager::`vftable'{for `winrt::impl::producer_convert<FilterHostProcessPoolManager,IFilterHostProcessPoolManager,void>'}
0x1800e7cd9  mov     [r14], rax
0x1800e7cdc  lea     rax, ??_7?$heap_implements@USingleProcessPool@@@impl@winrt@@6B?$producer_convert@UFilterHostProcessPoolManager@@UIFilterHostManager@@X@12@@; const winrt::impl::heap_implements<SingleProcessPool>::`vftable'{for `winrt::impl::producer_convert<FilterHostProcessPoolManager,IFilterHostManager,void>'}
0x1800e7ce3  mov     [r14+8], rax
0x1800e7ce7  lea     rax, ??_7?$heap_implements@UDedicatedFilterTypePool@@@impl@winrt@@6B@; const winrt::impl::heap_implements<DedicatedFilterTypePool>::`vftable'
0x1800e7cee  mov     [r14+10h], rax
0x1800e7cf2  mov     byte ptr [r14+20h], 1
0x1800e7cf7  lea     rcx, [r14+28h]; lpCriticalSection
0x1800e7cfb  xor     r8d, r8d; Flags
0x1800e7cfe  xor     edx, edx; dwSpinCount
0x1800e7d00  call    cs:__imp_InitializeCriticalSectionEx
0x1800e7d06  nop
0x1800e7d07  lea     rdi, [r14+50h]
0x1800e7d0b  mov     [rsp+1F0h+var_1B8], rdi
0x1800e7d10  xor     r12d, r12d
0x1800e7d13  mov     [rdi], r12d
0x1800e7d16  lea     rbx, [rdi+8]
0x1800e7d1a  mov     [rbx], r12
0x1800e7d1d  mov     [rbx+8], r12
0x1800e7d21  mov     rcx, rbx
0x1800e7d24  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$com_ptr@UIFilterHostProcess@@@winrt@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$com_ptr@UIFilterHostProcess@@@winrt@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring const,winrt::com_ptr<IFilterHostProcess>>>::_Alloc_sentinel_and_proxy(void)
0x1800e7d29  nop
0x1800e7d2a  lea     rcx, [rdi+18h]; void *
0x1800e7d2e  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x1800e7d33  nop
0x1800e7d34  mov     qword ptr [rdi+30h], 7
0x1800e7d3c  mov     qword ptr [rdi+38h], 8
0x1800e7d44  mov     dword ptr [rdi], 3F800000h
0x1800e7d4a  mov     r8, [rbx]
0x1800e7d4d  lea     edx, [r12+10h]
0x1800e7d52  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginAckInfo@PluginResourceManager@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginAckInfo@PluginResourceManager@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,PluginResourceManager::PluginAckInfo>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,PluginResourceManager::PluginAckInfo>>>>)
0x1800e7d57  nop
0x1800e7d58  mov     dword ptr [r14+90h], 1D4C0h
0x1800e7d63  mov     [r14+98h], r12
0x1800e7d6a  mov     [r14+0A0h], r12
0x1800e7d71  mov     [r14+0B0h], r12
0x1800e7d78  mov     [r14+0B8h], r12
0x1800e7d7f  lea     rax, ??_7RestrictedToken@@6B@; const RestrictedToken::`vftable'
0x1800e7d86  mov     [r14+0A8h], rax
0x1800e7d8d  mov     [r14+0F8h], r12
0x1800e7d94  mov     [r14+100h], r12
0x1800e7d9b  mov     qword ptr [r14+108h], 3
0x1800e7da6  mov     eax, 7530h
0x1800e7dab  cmp     esi, eax
0x1800e7dad  cmovnb  eax, esi
0x1800e7db0  mov     [r14+90h], eax
0x1800e7db7  lea     rcx, [r14+0F8h]
0x1800e7dbe  test    r15, r15
0x1800e7dc1  jz      short loc_1800E7DCB
0x1800e7dc3  mov     [rcx], r15
0x1800e7dc6  call    ?InternalAddRef@?$ComPtr@UIFilterHost@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IFilterHost>::InternalAddRef(void)
0x1800e7dcb  lea     rbx, [r14+100h]
0x1800e7dd2  cmp     [rbx], r12
0x1800e7dd5  jz      short loc_1800E7DDF
0x1800e7dd7  mov     rcx, rbx
0x1800e7dda  call    ?unconditional_release_ref@?$com_ptr@UIDatabase@@@winrt@@AEAAXXZ; winrt::com_ptr<IDatabase>::unconditional_release_ref(void)
0x1800e7ddf  mov     rcx, rbx; struct IPluginResourceManager **
0x1800e7de2  call    ?CreatePluginResourceManager@@YAJPEAPEAUIPluginResourceManager@@@Z; CreatePluginResourceManager(IPluginResourceManager * *)
0x1800e7de7  mov     rcx, [rbp+0F8h]; this
0x1800e7dee  test    eax, eax
0x1800e7df0  jns     short loc_1800E7E07
0x1800e7df2  mov     r9d, eax; char *
0x1800e7df5  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e7dfc  mov     edx, 0E1h; void *
0x1800e7e01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e7e07  lea     r15, ??_7UserToken@@6B@; const UserToken::`vftable'
0x1800e7e0e  mov     [rsp+1F0h+var_190], r15
0x1800e7e13  xorps   xmm0, xmm0
0x1800e7e16  movdqu  xmmword ptr [rsp+1F0h+hObject], xmm0
0x1800e7e1c  mov     rbx, [rbp+0F8h]
0x1800e7e23  mov     edx, 8Fh; unsigned int
0x1800e7e28  lea     rcx, [rsp+1F0h+var_190]; this
0x1800e7e2d  call    ?OpenCurrentProcToken@UserToken@@QEAA_NK@Z; UserToken::OpenCurrentProcToken(ulong)
0x1800e7e32  test    al, al
0x1800e7e34  jnz     short loc_1800E7E4B
0x1800e7e36  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e7e3d  mov     edx, 0EAh; void *
0x1800e7e42  mov     rcx, rbx; this
0x1800e7e45  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e7e4b  lea     rcx, [r14+0A8h]; this
0x1800e7e52  lea     rax, [rsp+1F0h+var_190]
0x1800e7e57  mov     [rcx+18h], rax
0x1800e7e5b  mov     [rcx+20h], r12
0x1800e7e5f  mov     [rcx+28h], r12
0x1800e7e63  mov     [rcx+30h], r12
0x1800e7e67  mov     [rcx+38h], r12
0x1800e7e6b  movsd   xmm0, qword ptr cs:?BuiltInSidBase@RestrictedToken@@0U_SID@@A.Revision; _SID RestrictedToken::BuiltInSidBase ...
0x1800e7e73  movsd   qword ptr [rcx+40h], xmm0
0x1800e7e78  mov     eax, cs:?BuiltInSidBase@RestrictedToken@@0U_SID@@A.SubAuthority; _SID RestrictedToken::BuiltInSidBase ...
0x1800e7e7e  mov     [rcx+48h], eax
0x1800e7e81  mov     dword ptr [rcx+4Ch], 221h
0x1800e7e88  mov     rbx, [rbp+0F8h]
0x1800e7e8f  call    ?CreateToken@RestrictedToken@@QEAA_NXZ; RestrictedToken::CreateToken(void)
0x1800e7e94  test    al, al
0x1800e7e96  jnz     short loc_1800E7EAD
0x1800e7e98  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e7e9f  mov     edx, 0EDh; void *
0x1800e7ea4  mov     rcx, rbx; this
0x1800e7ea7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e7ead  call    ?IsWindowStationFeatureAvailable@@YA_NXZ; IsWindowStationFeatureAvailable(void)
0x1800e7eb2  test    al, al
0x1800e7eb4  jz      loc_1800E81A5
0x1800e7eba  mov     [rbp+0F0h+var_138], r12
0x1800e7ebe  mov     [rbp+0F0h+var_130], r12b
0x1800e7ec2  mov     [rbp+0F0h+var_12C], 2
0x1800e7ec9  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x1800e7ed0  mov     [rbp+0F0h+var_140], rax
0x1800e7ed4  xorps   xmm0, xmm0
0x1800e7ed7  movdqu  [rbp+0F0h+var_128], xmm0
0x1800e7edc  mov     [rbp+0F0h+var_118], r12
0x1800e7ee0  mov     [rbp+0F0h+var_110], r12d
0x1800e7ee4  lea     rcx, [rbp+0F0h+var_B0]
0x1800e7ee8  call    ?World@Sids@ATL@@YA?AVCSid@2@XZ; ATL::Sids::World(void)
0x1800e7eed  nop
0x1800e7eee  mov     esi, 11Bh
0x1800e7ef3  mov     r8d, esi; unsigned int
0x1800e7ef6  mov     rdx, rax; struct ATL::CSid *
0x1800e7ef9  lea     rcx, [rbp+0F0h+var_140]; this
0x1800e7efd  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x1800e7f02  nop
0x1800e7f03  lea     rcx, [rbp+0F0h+var_B0]; this
0x1800e7f07  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800e7f0c  mov     [rsp+1F0h+pSid], r12
0x1800e7f11  call    ?ShouldRunFilterHostInAppContainer@FilterHostUtils@@YA_NXZ; FilterHostUtils::ShouldRunFilterHostInAppContainer(void)
0x1800e7f16  test    al, al
0x1800e7f18  jz      loc_1800E7FA5
0x1800e7f1e  mov     rbx, [rsp+1F0h+pSid]
0x1800e7f23  test    rbx, rbx
0x1800e7f26  jz      short loc_1800E7F45
0x1800e7f28  lea     rcx, [rsp+1F0h+var_1B8]; this
0x1800e7f2d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800e7f32  mov     rcx, rbx; pSid
0x1800e7f35  call    cs:__imp_FreeSid
0x1800e7f3b  lea     rcx, [rsp+1F0h+var_1B8]; this
0x1800e7f40  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800e7f45  mov     [rsp+1F0h+pSid], r12
0x1800e7f4a  mov     rbx, [rbp+0F8h]
0x1800e7f51  lea     rdx, [rsp+1F0h+pSid]; Sid
0x1800e7f56  lea     rcx, StringSid; "S-1-15-2-2922806004-2201342939-34023795"...
0x1800e7f5d  call    cs:__imp_ConvertStringSidToSidW
0x1800e7f63  test    eax, eax
0x1800e7f65  jnz     short loc_1800E7F7C
0x1800e7f67  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e7f6e  mov     edx, 0FCh; void *
0x1800e7f73  mov     rcx, rbx; this
0x1800e7f76  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e7f7c  mov     rdx, [rsp+1F0h+pSid]; struct _SID *
0x1800e7f81  lea     rcx, [rbp+0F0h+var_B0]; this
0x1800e7f85  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEB_W@Z; ATL::CSid::CSid(_SID const *,wchar_t const *)
0x1800e7f8a  nop
0x1800e7f8b  mov     r8d, esi; unsigned int
0x1800e7f8e  lea     rdx, [rbp+0F0h+var_B0]; struct ATL::CSid *
0x1800e7f92  lea     rcx, [rbp+0F0h+var_140]; this
0x1800e7f96  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x1800e7f9b  nop
0x1800e7f9c  lea     rcx, [rbp+0F0h+var_B0]; this
0x1800e7fa0  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800e7fa5  lea     rdi, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x1800e7fac  mov     [rsp+1F0h+var_1A0], rdi
0x1800e7fb1  mov     [rsp+1F0h+var_198], r12
0x1800e7fb6  lea     rdx, [rbp+0F0h+var_140]; struct ATL::CDacl *
0x1800e7fba  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1800e7fbf  call    ?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z; ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)
0x1800e7fc4  lea     rdx, [rsp+1F0h+var_1A0]; struct ATL::CSecurityDesc *
0x1800e7fc9  lea     rcx, [rbp+0F0h+sa]; this
0x1800e7fcd  call    ??0CSecurityAttributes@ATL@@QEAA@AEBVCSecurityDesc@1@_N@Z; ATL::CSecurityAttributes::CSecurityAttributes(ATL::CSecurityDesc const &,bool)
0x1800e7fd2  nop
0x1800e7fd3  lea     rbx, [r14+98h]
0x1800e7fda  lea     r9, [rbp+0F0h+sa]; lpsa
0x1800e7fde  mov     r8d, esi; dwDesiredAccess
0x1800e7fe1  xor     edx, edx; dwFlags
0x1800e7fe3  lea     rcx, winsta; "msswindowstation"
0x1800e7fea  call    cs:__imp_CreateWindowStationW
0x1800e7ff0  mov     rdx, rax
0x1800e7ff3  mov     rcx, rbx
0x1800e7ff6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHWINSTA__@@P6AHPEAU1@@Z$1?CloseWindowStation@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHWINSTA__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HWINSTA__ *,int (*)(HWINSTA__ *),&CloseWindowStation(HWINSTA__ *),wistd::integral_constant<unsigned __int64,0>,HWINSTA__ *,HWINSTA__ *,0,std::nullptr_t>>::reset(HWINSTA__ *)
0x1800e7ffb  mov     rcx, [rbx]; hWinSta
0x1800e7ffe  mov     rax, [rbp+0F8h]
0x1800e8005  test    rcx, rcx
0x1800e8008  jnz     short loc_1800E801F
0x1800e800a  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e8011  mov     edx, 110h; void *
0x1800e8016  mov     rcx, rax; this
0x1800e8019  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e801f  mov     rbx, [rbp+0F8h]
0x1800e8026  call    cs:__imp_SetProcessWindowStation
0x1800e802c  test    eax, eax
0x1800e802e  jnz     short loc_1800E8045
0x1800e8030  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e8037  mov     edx, 112h; void *
0x1800e803c  mov     rcx, rbx; this
0x1800e803f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e8045  mov     [rbp+0F0h+var_170], r12
0x1800e8049  mov     [rbp+0F0h+var_168], r12b
0x1800e804d  mov     [rbp+0F0h+var_164], 2
0x1800e8054  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x1800e805b  mov     [rsp+1F0h+var_178], rax
0x1800e8060  xorps   xmm0, xmm0
0x1800e8063  movdqu  [rbp+0F0h+var_160], xmm0
0x1800e8068  mov     [rbp+0F0h+var_150], r12
0x1800e806c  mov     [rbp+0F0h+var_148], r12d
0x1800e8070  lea     rcx, [rbp+0F0h+var_B0]
0x1800e8074  call    ?World@Sids@ATL@@YA?AVCSid@2@XZ; ATL::Sids::World(void)
0x1800e8079  nop
0x1800e807a  mov     ebx, 0C3h
0x1800e807f  mov     r8d, ebx; unsigned int
0x1800e8082  mov     rdx, rax; struct ATL::CSid *
0x1800e8085  lea     rcx, [rsp+1F0h+var_178]; this
0x1800e808a  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x1800e808f  nop
0x1800e8090  lea     rcx, [rbp+0F0h+var_B0]; this
0x1800e8094  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800e8099  call    ?ShouldRunFilterHostInAppContainer@FilterHostUtils@@YA_NXZ; FilterHostUtils::ShouldRunFilterHostInAppContainer(void)
0x1800e809e  test    al, al
0x1800e80a0  jz      short loc_1800E80CC
0x1800e80a2  mov     rdx, [rsp+1F0h+pSid]; struct _SID *
0x1800e80a7  lea     rcx, [rbp+0F0h+var_B0]; this
0x1800e80ab  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEB_W@Z; ATL::CSid::CSid(_SID const *,wchar_t const *)
0x1800e80b0  nop
0x1800e80b1  mov     r8d, ebx; unsigned int
0x1800e80b4  lea     rdx, [rbp+0F0h+var_B0]; struct ATL::CSid *
0x1800e80b8  lea     rcx, [rsp+1F0h+var_178]; this
0x1800e80bd  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x1800e80c2  nop
0x1800e80c3  lea     rcx, [rbp+0F0h+var_B0]; this
0x1800e80c7  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800e80cc  mov     [rsp+1F0h+var_1B0], rdi
0x1800e80d1  mov     [rsp+1F0h+var_1A8], r12
0x1800e80d6  lea     rdx, [rsp+1F0h+var_178]; struct ATL::CDacl *
0x1800e80db  lea     rcx, [rsp+1F0h+var_1B0]; this
0x1800e80e0  call    ?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z; ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)
0x1800e80e5  lea     rdx, [rsp+1F0h+var_1B0]; struct ATL::CSecurityDesc *
0x1800e80ea  lea     rcx, [rbp+0F0h+var_100]; this
0x1800e80ee  call    ??0CSecurityAttributes@ATL@@QEAA@AEBVCSecurityDesc@1@_N@Z; ATL::CSecurityAttributes::CSecurityAttributes(ATL::CSecurityDesc const &,bool)
0x1800e80f3  nop
0x1800e80f4  lea     rbx, [r14+0A0h]
0x1800e80fb  lea     rax, [rbp+0F0h+var_100]
0x1800e80ff  mov     [rsp+1F0h+lpsa], rax; lpsa
0x1800e8104  mov     [rsp+1F0h+dwDesiredAccess], 3; dwDesiredAccess
0x1800e810c  xor     r9d, r9d; dwFlags
0x1800e810f  xor     r8d, r8d; pDevmode
0x1800e8112  xor     edx, edx; lpszDevice
0x1800e8114  lea     rcx, szDesktop; "mssrestricteddesk"
0x1800e811b  call    cs:__imp_CreateDesktopW
0x1800e8121  mov     rdx, rax
0x1800e8124  mov     rcx, rbx
0x1800e8127  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHDESK__@@P6AHPEAU1@@Z$1?CloseDesktop@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHDESK__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>::reset(HDESK__ *)
0x1800e812c  mov     rcx, [rbp+0F8h]; this
0x1800e8133  cmp     [rbx], r12
0x1800e8136  jnz     short loc_1800E814A
0x1800e8138  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e813f  mov     edx, 127h; void *
0x1800e8144  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e814a  mov     [rbp+0F0h+var_E8], rdi
0x1800e814e  lea     rcx, [rbp+0F0h+var_E8]; this
0x1800e8152  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x1800e8157  nop
0x1800e8158  mov     [rsp+1F0h+var_1B0], rdi
0x1800e815d  lea     rcx, [rsp+1F0h+var_1B0]; this
0x1800e8162  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x1800e8167  nop
0x1800e8168  lea     rcx, [rsp+1F0h+var_178]; this
0x1800e816d  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x1800e8172  nop
0x1800e8173  mov     [rbp+0F0h+var_C0], rdi
0x1800e8177  lea     rcx, [rbp+0F0h+var_C0]; this
0x1800e817b  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x1800e8180  nop
0x1800e8181  mov     [rsp+1F0h+var_1A0], rdi
0x1800e8186  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1800e818b  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x1800e8190  nop
0x1800e8191  lea     rcx, [rsp+1F0h+pSid]
0x1800e8196  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800e819b  nop
0x1800e819c  lea     rcx, [rbp+0F0h+var_140]; this
0x1800e81a0  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x1800e81a5  cmp     [r14+0A0h], r12
0x1800e81ac  setnz   al
0x1800e81af  mov     [r14+20h], al
0x1800e81b3  mov     [rsp+1F0h+var_190], r15
  ... truncated ...
```
