# DusmCache::QueryCostCache(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA *,int *)

- ea: `0x18001c9f8`
- end: `0x18001cc2f`
- name: `?QueryCostCache@DusmCache@@AEAAHAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_CONNECTION_COST_DATA@@PEAH@Z`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c508`

## callees

- `0x18000e7e0`
- `0x18000e828`
- `0x18000f094`
- `0x180013114`
- `0x18001a730`
- `0x18001a7b8`
- `0x18001aa4c`
- `0x18001aa80`
- `0x18001bf4c`
- `0x18001c154`
- `0x18001c9f8`
- `0x18001d87c`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001ca97`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001cb1c`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001ca97`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001cb1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca5a`

## string_xrefs

- `0x18001cc0a`: `DusmCache::QueryCostCache::source`
- `0x18001cc1c`: `onecoreuap\net\dusm\lib\dusmcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DusmCache::QueryCostCache(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4, const wchar_t *a5)
{
  _QWORD *v5; // r13
  int v8; // r15d
  unsigned int v9; // r12d
  __int64 v10; // rbx
  const WCHAR *v11; // rdi
  __int64 v12; // rcx
  bool v13; // al
  __int64 v14; // rdi
  int v15; // r14d
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 v18; // rcx
  unsigned int v19; // esi
  unsigned int v20; // esi
  __int64 v21; // rcx
  wchar_t *v22; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // [rsp+0h] [rbp-118h] BYREF
  const char *v29; // [rsp+28h] [rbp-F0h]
  int v30; // [rsp+40h] [rbp-D8h]
  __int64 v31; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+50h] [rbp-C8h]
  const WCHAR *v33; // [rsp+58h] [rbp-C0h] BYREF
  wchar_t *v34; // [rsp+60h] [rbp-B8h] BYREF
  const WCHAR *v35; // [rsp+68h] [rbp-B0h] BYREF
  wchar_t *v36; // [rsp+70h] [rbp-A8h]
  _QWORD *v37; // [rsp+78h] [rbp-A0h]
  _QWORD v38[2]; // [rsp+80h] [rbp-98h] BYREF
  __int64 v39; // [rsp+90h] [rbp-88h]
  _BYTE v40[32]; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v41[96]; // [rsp+B8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v5 = a4;
  v31 = a1;
  v35 = (const WCHAR *)a2;
  v37 = a4;
  v34 = (wchar_t *)a5;
  v36 = (wchar_t *)a5;
  v30 = 0;
  v8 = 0;
  v9 = 0;
  v10 = UNKNOWN_COST_DATA;
  v32 = UNKNOWN_COST_DATA;
  v11 = (const WCHAR *)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v33 = v11;
  std::_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>::_Find_lower_bound<_GUID>(
    v31,
    v38,
    (const void *)(a2 + 32));
  v13 = std::_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>::_Lower_bound_duplicate<_GUID>(
          v12,
          v39,
          (const void *)(a2 + 32));
  try
  {
    if ( !v13 )
      std::_Xout_of_range("invalid map<K, T> key");
    if ( *(_DWORD *)(a2 + 16) == 1 )
    {
      v14 = std::wstring::wstring((__int64)v41, (__int64)"*");
      v15 = 1;
    }
    else
    {
      v14 = std::wstring::wstring((__int64)v40, a2 + 48);
      v15 = 2;
    }
    v30 = v15;
    std::_Tree<std::_Tmap_traits<std::wstring,DusmCache::DusmCacheCost,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DusmCache::DusmCacheCost>>,0>>::_Find_lower_bound<std::wstring>(
      v39 + 48,
      v38,
      v14);
    v16 = v14;
    v17 = v39;
    if ( !std::_Tree<std::_Tmap_traits<std::wstring,DusmCache::DusmCacheCost,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DusmCache::DusmCacheCost>>,0>>::_Lower_bound_duplicate<std::wstring>(
            v18,
            v39,
            v16) )
      std::_Xout_of_range("invalid map<K, T> key");
    if ( (v15 & 2) != 0 )
    {
      LOBYTE(v15) = v15 & 0xFD;
      std::wstring::_Tidy_deallocate(v40);
    }
    if ( (v15 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v41);
    v19 = a3 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        if ( v20 != 1 )
          wil::details::in1diag3::Throw_Win32Msg(
            retaddr,
            (void *)0x104,
            (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
            (const char *)0x57,
            (unsigned int)"DusmCache::QueryCostCache::source",
            v29);
        if ( !*(_DWORD *)(v17 + 96) )
          goto LABEL_23;
        v8 = *(_DWORD *)(v17 + 96);
        v9 = *(_DWORD *)(v17 + 100);
        v10 = *(_QWORD *)(v17 + 104);
        goto LABEL_22;
      }
      if ( *(_DWORD *)(v17 + 80) )
      {
        v8 = *(_DWORD *)(v17 + 80);
        v9 = *(_DWORD *)(v17 + 84);
        v10 = *(_QWORD *)(v17 + 88);
LABEL_22:
        v32 = v10;
      }
    }
    else if ( *(_DWORD *)(v17 + 64) )
    {
      v8 = *(_DWORD *)(v17 + 64);
      v9 = *(_DWORD *)(v17 + 68);
      v10 = *(_QWORD *)(v17 + 72);
      goto LABEL_22;
    }
LABEL_23:
    if ( (unsigned int)IsCostCacheFlushReady(*(_QWORD *)(v31 + 8), v31 + 56) )
      DusmCache::FlushCostCache();
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
    v22 = v34;
  }
  catch ( std::out_of_range )
  {
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v21, &v28) + 8) > 5u )
    {
      v34 = (wchar_t *)EnumToString(a3);
      v35 = (const WCHAR *)DusmMediaTypeToSz(*((unsigned int *)v35 + 4));
      v33 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v24 + 48);
      v31 = v25 + 32;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        v26,
        (int)&word_1800571CA,
        v26,
        v27,
        &v31,
        &v33,
        &v35,
        (const wchar_t **)&v34);
    }
    v8 = 0;
    v9 = 0;
    v10 = v32;
    v22 = v36;
    v5 = v37;
  }
  *(_DWORD *)v22 = v8;
  *v5 = v10;
  return v9;
}

```

## disassembly

```asm
0x18001c9f8  mov     [rsp+arg_10], r8d
0x18001c9fd  push    rbx
0x18001c9fe  push    rsi
0x18001c9ff  push    rdi
0x18001ca00  push    r12
0x18001ca02  push    r13
0x18001ca04  push    r14
0x18001ca06  push    r15
0x18001ca08  sub     rsp, 0E0h
0x18001ca0f  mov     r13, r9
0x18001ca12  mov     esi, r8d
0x18001ca15  mov     r14, rdx
0x18001ca18  mov     [rsp+118h+var_D0], rcx
0x18001ca1d  mov     [rsp+118h+var_B0], rdx
0x18001ca22  mov     [rsp+118h+var_A0], r9
0x18001ca27  mov     rax, [rsp+118h+arg_20]
0x18001ca2f  mov     [rsp+118h+var_B8], rax
0x18001ca34  mov     [rsp+118h+var_A8], rax
0x18001ca39  mov     [rsp+118h+var_D8], 0
0x18001ca41  xor     r15d, r15d
0x18001ca44  xor     r12d, r12d
0x18001ca47  mov     rbx, cs:?UNKNOWN_COST_DATA@@3U_DUSM_CONNECTION_COST_DATA@@B; _DUSM_CONNECTION_COST_DATA const UNKNOWN_COST_DATA
0x18001ca4e  mov     [rsp+118h+var_C8], rbx
0x18001ca53  lea     rdi, [rcx+10h]
0x18001ca57  mov     rcx, rdi; lpCriticalSection
0x18001ca5a  call    cs:__imp_EnterCriticalSection
0x18001ca60  mov     [rsp+118h+var_C0], rdi
0x18001ca65  lea     r8, [r14+20h]
0x18001ca69  lea     rdx, [rsp+118h+var_98]
0x18001ca71  mov     rcx, [rsp+118h+var_D0]
0x18001ca76  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@UGuidCompare@DusmCache@@V?$allocator@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18001ca7b  lea     r8, [r14+20h]
0x18001ca7f  mov     rdx, [rsp+118h+var_88]
0x18001ca87  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@UGuidCompare@DusmCache@@V?$allocator@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * const,_GUID const &)
0x18001ca8c  test    al, al
0x18001ca8e  jnz     short loc_18001CA9D
0x18001ca90  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18001ca97  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18001ca9d  cmp     dword ptr [r14+10h], 1
0x18001caa2  jnz     short loc_18001CAC3
0x18001caa4  lea     rdx, asc_180050F74; "*"
0x18001caab  lea     rcx, [rsp+118h+var_60]
0x18001cab3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001cab8  mov     rdi, rax
0x18001cabb  mov     r14d, 1
0x18001cac1  jmp     short loc_18001CADD
0x18001cac3  lea     rdx, [r14+30h]
0x18001cac7  lea     rcx, [rsp+118h+var_80]
0x18001cacf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001cad4  mov     rdi, rax
0x18001cad7  mov     r14d, 2
0x18001cadd  mov     [rsp+118h+var_D8], r14d
0x18001cae2  mov     rcx, [rsp+118h+var_88]
0x18001caea  add     rcx, 30h ; '0'
0x18001caee  mov     r8, rdi
0x18001caf1  lea     rdx, [rsp+118h+var_98]
0x18001caf9  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,DusmCache::DusmCacheCost,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DusmCache::DusmCacheCost>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001cafe  mov     r8, rdi
0x18001cb01  mov     rdi, [rsp+118h+var_88]
0x18001cb09  mov     rdx, rdi
0x18001cb0c  call    ??$_Lower_bound_duplicate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,DusmCache::DusmCacheCost,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DusmCache::DusmCacheCost>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,DusmCache::DusmCacheCost>,void *> * const,std::wstring const &)
0x18001cb11  test    al, al
0x18001cb13  jnz     short loc_18001CB23
0x18001cb15  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18001cb1c  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18001cb22  nop
0x18001cb23  test    r14b, 2
0x18001cb27  jz      short loc_18001CB3B
0x18001cb29  and     r14d, 0FFFFFFFDh
0x18001cb2d  lea     rcx, [rsp+118h+var_80]
0x18001cb35  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cb3a  nop
0x18001cb3b  test    r14b, 1
0x18001cb3f  jz      short loc_18001CB4E
0x18001cb41  lea     rcx, [rsp+118h+var_60]
0x18001cb49  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cb4e  sub     esi, 1
0x18001cb51  jz      short loc_18001CB89
0x18001cb53  sub     esi, 1
0x18001cb56  jz      short loc_18001CB75
0x18001cb58  cmp     esi, 1
0x18001cb5b  jnz     loc_18001CC02
0x18001cb61  cmp     dword ptr [rdi+60h], 0
0x18001cb65  jz      short loc_18001CBA0
0x18001cb67  mov     r15d, [rdi+60h]
0x18001cb6b  mov     r12d, [rdi+64h]
0x18001cb6f  mov     rbx, [rdi+68h]
0x18001cb73  jmp     short loc_18001CB9B
0x18001cb75  cmp     dword ptr [rdi+50h], 0
0x18001cb79  jz      short loc_18001CBA0
0x18001cb7b  mov     r15d, [rdi+50h]
0x18001cb7f  mov     r12d, [rdi+54h]
0x18001cb83  mov     rbx, [rdi+58h]
0x18001cb87  jmp     short loc_18001CB9B
0x18001cb89  cmp     dword ptr [rdi+40h], 0
0x18001cb8d  jz      short loc_18001CBA0
0x18001cb8f  mov     r15d, [rdi+40h]
0x18001cb93  mov     r12d, [rdi+44h]
0x18001cb97  mov     rbx, [rdi+48h]
0x18001cb9b  mov     [rsp+118h+var_C8], rbx
0x18001cba0  mov     rax, [rsp+118h+var_D0]
0x18001cba5  lea     rdx, [rax+38h]
0x18001cba9  mov     rcx, [rax+8]
0x18001cbad  call    IsCostCacheFlushReady
0x18001cbb2  test    eax, eax
0x18001cbb4  jz      short loc_18001CBBC
0x18001cbb6  call    ?FlushCostCache@DusmCache@@SAXXZ; DusmCache::FlushCostCache(void)
0x18001cbbb  nop
0x18001cbbc  lea     rcx, [rsp+118h+var_C0]
0x18001cbc1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001cbc6  nop
0x18001cbc7  mov     rax, [rsp+118h+var_B8]
0x18001cbcc  jmp     short loc_18001CBE5
0x18001cbce  mov     r15d, [rsp+118h+var_D8]
0x18001cbd3  mov     r12d, r15d
0x18001cbd6  mov     rbx, [rsp+118h+var_C8]
0x18001cbdb  mov     rax, [rsp+118h+var_A8]
0x18001cbe0  mov     r13, [rsp+118h+var_A0]
0x18001cbe5  mov     [rax], r15d
0x18001cbe8  mov     [r13+0], rbx
0x18001cbec  mov     eax, r12d
0x18001cbef  add     rsp, 0E0h
0x18001cbf6  pop     r15
0x18001cbf8  pop     r14
0x18001cbfa  pop     r13
0x18001cbfc  pop     r12
0x18001cbfe  pop     rdi
0x18001cbff  pop     rsi
0x18001cc00  pop     rbx
0x18001cc01  retn
0x18001cc02  mov     rcx, [rsp+118h]; this
0x18001cc0a  lea     rax, aDusmcacheQuery_0; "DusmCache::QueryCostCache::source"
0x18001cc11  mov     qword ptr [rsp+118h+var_F8], rax; unsigned int
0x18001cc16  mov     r9d, 57h ; 'W'; char *
0x18001cc1c  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001cc23  mov     edx, 104h; void *
0x18001cc28  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
