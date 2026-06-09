# TenantRestrictions::UpdateTenantRestrictionsList(void)

- ea: `0x18000b67c`
- end: `0x18000ba50`
- name: `?UpdateTenantRestrictionsList@TenantRestrictions@@QEAAJXZ`
- size: `980`
- prototype: `__int64 __fastcall(TenantRestrictions *__hidden this)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ba60`

## callees

- `0x180001a50`
- `0x180003e84`
- `0x180004518`
- `0x180006d14`
- `0x180008dc4`
- `0x180009514`
- `0x18000983c`
- `0x180009d60`
- `0x180009ff0`
- `0x18000a5b8`
- `0x18000a9b0`
- `0x18000a9e0`
- `0x18000aa50`
- `0x18000aaf4`
- `0x18000adb8`
- `0x18000b67c`
- `0x18000bee0`
- `0x18000bf84`
- `0x18000c338`
- `0x18000c498`
- `0x18000c750`
- `0x18000c784`
- `0x18000ce4c`
- `0x18000e0b0`
- `0x18000e668`
- `0x18000e8e8`
- `0x18000eaf4`
- `0x18000ed90`
- `0x18000f4ac`
- `0x18000f7cc`

## string_xrefs

- `0x18000b835`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`
- `0x18000b6ab`: `TenantRestrictionsListUpdate`

## pseudocode

```c
__int64 __fastcall TenantRestrictions::UpdateTenantRestrictionsList(TenantRestrictions *this)
{
  __int64 O365Guid; // rax
  int *v3; // rsi
  __int64 TenantRestrictionsVersion; // rax
  __int64 v5; // rax
  char v6; // r15
  _QWORD *v7; // rdi
  _QWORD *i; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  _QWORD *j; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  const char *v14; // r9
  __int64 result; // rax
  const struct _WNF_STATE_NAME *v16; // rdx
  wil *v17; // rcx
  __int64 v18; // rax
  __int64 LocalTimeAsString; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  int v23; // [rsp+20h] [rbp-258h]
  _QWORD v24[2]; // [rsp+30h] [rbp-248h] BYREF
  _BYTE v25[16]; // [rsp+40h] [rbp-238h] BYREF
  _BYTE v26[16]; // [rsp+50h] [rbp-228h] BYREF
  _BYTE v27[16]; // [rsp+60h] [rbp-218h] BYREF
  int v28; // [rsp+70h] [rbp-208h] BYREF
  _QWORD *v29; // [rsp+78h] [rbp-200h]
  _QWORD v30[2]; // [rsp+B0h] [rbp-1C8h] BYREF
  _QWORD *v31; // [rsp+C0h] [rbp-1B8h]
  _QWORD *v32; // [rsp+D0h] [rbp-1A8h]
  _BYTE v33[244]; // [rsp+F0h] [rbp-188h] BYREF
  int v34; // [rsp+1E4h] [rbp-94h]
  _QWORD v35[4]; // [rsp+200h] [rbp-78h] BYREF
  _BYTE v36[32]; // [rsp+220h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  TenantRestrictionsLoggers::AutoMeasureLogger::AutoMeasureLogger(
    (TenantRestrictionsLoggers::AutoMeasureLogger *)v33,
    "TenantRestrictionsListUpdate");
  try
  {
    if ( !*((_QWORD *)this + 2) )
    {
      O365Guid = TenantRestrictionsHelpers::GetO365Guid(v35);
      std::wstring::operator=(this, O365Guid);
      std::wstring::_Tidy_deallocate(v35);
    }
    v3 = (int *)((char *)this + 32);
    if ( !*((_QWORD *)this + 6) )
    {
      TenantRestrictionsVersion = TenantRestrictionsHelpers::GetTenantRestrictionsVersion(v30);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::operator=(
        (char *)this + 32,
        TenantRestrictionsVersion);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v30);
    }
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
    TenantRestrictionsHelpers::GetLatestTenantRestrictionsVersion(&v28, v5, *((unsigned int *)this + 24));
    v6 = 0;
    v7 = v29;
    for ( i = (_QWORD *)*v29; i != v7; i = (_QWORD *)*i )
    {
      std::wstring::wstring(v36, i + 2);
      std::wstring::wstring(v35, i + 6);
      if ( !std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::count(
              (char *)this + 32,
              v36) )
      {
        v6 = 1;
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v36);
        break;
      }
      v9 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                       (char *)this + 32,
                       v24,
                       v36);
      v6 |= (int)std::wstring::compare(v35, *v9 + 48LL) > 0;
      std::wstring::_Tidy_deallocate(v35);
      std::wstring::_Tidy_deallocate(v36);
    }
    if ( v6 )
    {
      TenantRestrictionsHelpers::TenantRestrictionsData::TenantRestrictionsData((TenantRestrictionsHelpers::TenantRestrictionsData *)v25);
      v10 = v29;
      for ( j = (_QWORD *)*v29; j != v10; j = (_QWORD *)*j )
      {
        std::wstring::wstring(v36, j + 2);
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
        v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
        TenantRestrictionsHelpers::GetTenantRestrictionsO365ApiData(
          v35,
          (__int64)L"/endpoints",
          v20,
          v21,
          *((_DWORD *)this + 24));
        v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
        TenantRestrictionsHelpers::ParseTenantRestrictionsHostnameAndIPData(v30, v22);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>>(
          v25,
          *(_QWORD *)v30[0],
          v30[0]);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>>(
          v26,
          *v31,
          v31);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>>(
          v27,
          *v32,
          v32);
        TenantRestrictionsHelpers::TenantRestrictionsData::~TenantRestrictionsData((TenantRestrictionsHelpers::TenantRestrictionsData *)v30);
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v36);
      }
      v12 = TenantRestrictions::AddInBoxEndpoints((struct TenantRestrictionsHelpers::TenantRestrictionsData *)v25);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDD,
          (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
          (const char *)(unsigned int)v12,
          v23);
        TenantRestrictionsHelpers::TenantRestrictionsData::~TenantRestrictionsData((TenantRestrictionsHelpers::TenantRestrictionsData *)v25);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v28);
        TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger((TenantRestrictionsLoggers::AutoMeasureLogger *)v33);
        return v13;
      }
      TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry(v25, &v28);
      if ( v3 != &v28 )
      {
        v24[0] = (char *)this + 32;
        *v3 = v28;
        std::list<std::pair<std::wstring const,std::wstring>>::_Assign_cast<std::pair<std::wstring,std::wstring> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>>(
          (char *)this + 40,
          *v29,
          v29);
        v18 = std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Desired_grow_bucket_count(
                (char *)this + 32,
                *((_QWORD *)this + 6));
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
          (char *)this + 32,
          v18);
        v24[0] = 0;
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(v24);
      }
      wil::wnf_publish(v17, v16);
      TenantRestrictionsHelpers::TenantRestrictionsData::~TenantRestrictionsData((TenantRestrictionsHelpers::TenantRestrictionsData *)v25);
    }
    LocalTimeAsString = TenantRestrictionsHelpers::GetLocalTimeAsString(v35);
    std::wstring::operator=((char *)this + 184, LocalTimeAsString);
    std::wstring::_Tidy_deallocate(v35);
    v33[240] = 1;
    v34 = 0;
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v28);
    TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger((TenantRestrictionsLoggers::AutoMeasureLogger *)v33);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xED,
                           (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18000b67c  mov     [rsp+arg_8], rbx
0x18000b681  mov     [rsp+arg_10], rsi
0x18000b686  push    rdi
0x18000b687  push    r12
0x18000b689  push    r13
0x18000b68b  push    r14
0x18000b68d  push    r15
0x18000b68f  sub     rsp, 250h
0x18000b696  mov     rax, cs:__security_cookie
0x18000b69d  xor     rax, rsp
0x18000b6a0  mov     [rsp+278h+var_38], rax
0x18000b6a8  mov     r14, rcx
0x18000b6ab  lea     rdx, aTenantrestrict_0; "TenantRestrictionsListUpdate"
0x18000b6b2  lea     rcx, [rsp+278h+var_188]; this
0x18000b6ba  call    ??0AutoMeasureLogger@TenantRestrictionsLoggers@@QEAA@PEBD@Z; TenantRestrictionsLoggers::AutoMeasureLogger::AutoMeasureLogger(char const *)
0x18000b6bf  nop
0x18000b6c0  cmp     qword ptr [r14+10h], 0
0x18000b6c5  jnz     short loc_18000B6EC
0x18000b6c7  lea     rcx, [rsp+278h+var_78]
0x18000b6cf  call    ?GetO365Guid@TenantRestrictionsHelpers@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; TenantRestrictionsHelpers::GetO365Guid(void)
0x18000b6d4  mov     rdx, rax
0x18000b6d7  mov     rcx, r14
0x18000b6da  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000b6df  lea     rcx, [rsp+278h+var_78]
0x18000b6e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b6ec  lea     rsi, [r14+20h]
0x18000b6f0  cmp     qword ptr [rsi+10h], 0
0x18000b6f5  jnz     short loc_18000B71C
0x18000b6f7  lea     rcx, [rsp+278h+var_1C8]
0x18000b6ff  call    ?GetTenantRestrictionsVersion@TenantRestrictionsHelpers@@YA?AV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ; TenantRestrictionsHelpers::GetTenantRestrictionsVersion(void)
0x18000b704  mov     rdx, rax
0x18000b707  mov     rcx, rsi
0x18000b70a  call    ??4?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::operator=(std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>> &&)
0x18000b70f  lea     rcx, [rsp+278h+var_1C8]
0x18000b717  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000b71c  mov     rcx, r14
0x18000b71f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b724  mov     r8d, [r14+60h]
0x18000b728  mov     rdx, rax
0x18000b72b  lea     rcx, [rsp+278h+var_208]
0x18000b730  call    ?GetLatestTenantRestrictionsVersion@TenantRestrictionsHelpers@@YA?AV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEBGK@Z; TenantRestrictionsHelpers::GetLatestTenantRestrictionsVersion(ushort const *,ulong)
0x18000b735  nop
0x18000b736  xor     r15b, r15b
0x18000b739  mov     rdi, [rsp+278h+var_200]
0x18000b73e  mov     rbx, [rdi]
0x18000b741  cmp     rbx, rdi
0x18000b744  jz      loc_18000B7F5
0x18000b74a  lea     rdx, [rbx+10h]
0x18000b74e  lea     rcx, [rsp+278h+var_58]
0x18000b756  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000b75b  nop
0x18000b75c  lea     rdx, [rbx+30h]
0x18000b760  lea     rcx, [rsp+278h+var_78]
0x18000b768  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000b76d  nop
0x18000b76e  lea     rdx, [rsp+278h+var_58]
0x18000b776  mov     rcx, rsi
0x18000b779  call    ?count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::count(std::wstring const &)
0x18000b77e  test    rax, rax
0x18000b781  jz      short loc_18000B7D7
0x18000b783  lea     r8, [rsp+278h+var_58]
0x18000b78b  lea     rdx, [rsp+278h+var_248]
0x18000b790  mov     rcx, rsi
0x18000b793  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18000b798  mov     rdx, [rax]
0x18000b79b  add     rdx, 30h ; '0'
0x18000b79f  lea     rcx, [rsp+278h+var_78]
0x18000b7a7  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x18000b7ac  test    eax, eax
0x18000b7ae  setnle  al
0x18000b7b1  or      r15b, al
0x18000b7b4  lea     rcx, [rsp+278h+var_78]
0x18000b7bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b7c1  nop
0x18000b7c2  lea     rcx, [rsp+278h+var_58]
0x18000b7ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b7cf  mov     rbx, [rbx]
0x18000b7d2  jmp     loc_18000B741
0x18000b7d7  mov     r15b, 1
0x18000b7da  lea     rcx, [rsp+278h+var_78]
0x18000b7e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b7e7  nop
0x18000b7e8  lea     rcx, [rsp+278h+var_58]
0x18000b7f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b7f5  test    r15b, r15b
0x18000b7f8  jz      loc_18000B8E3
0x18000b7fe  lea     rcx, [rsp+278h+var_238]; this
0x18000b803  call    ??0TenantRestrictionsData@TenantRestrictionsHelpers@@QEAA@XZ; TenantRestrictionsHelpers::TenantRestrictionsData::TenantRestrictionsData(void)
0x18000b808  nop
0x18000b809  mov     rdi, [rsp+278h+var_200]
0x18000b80e  mov     rbx, [rdi]
0x18000b811  cmp     rbx, rdi
0x18000b814  jnz     loc_18000B96C
0x18000b81a  lea     rcx, [rsp+278h+var_238]; struct TenantRestrictionsHelpers::TenantRestrictionsData *
0x18000b81f  call    ?AddInBoxEndpoints@TenantRestrictions@@CAJAEAUTenantRestrictionsData@TenantRestrictionsHelpers@@@Z; TenantRestrictions::AddInBoxEndpoints(TenantRestrictionsHelpers::TenantRestrictionsData &)
0x18000b824  mov     ebx, eax
0x18000b826  test    eax, eax
0x18000b828  jns     short loc_18000B871
0x18000b82a  mov     rcx, [rsp+278h]; this
0x18000b832  mov     r9d, eax; char *
0x18000b835  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000b83c  mov     edx, 0DDh; void *
0x18000b841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b846  nop
0x18000b847  lea     rcx, [rsp+278h+var_238]; this
0x18000b84c  call    ??1TenantRestrictionsData@TenantRestrictionsHelpers@@QEAA@XZ; TenantRestrictionsHelpers::TenantRestrictionsData::~TenantRestrictionsData(void)
0x18000b851  nop
0x18000b852  lea     rcx, [rsp+278h+var_208]
0x18000b857  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000b85c  nop
0x18000b85d  lea     rcx, [rsp+278h+var_188]; this
0x18000b865  call    ??1AutoMeasureLogger@TenantRestrictionsLoggers@@UEAA@XZ; TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger(void)
0x18000b86a  mov     eax, ebx
0x18000b86c  jmp     loc_18000B93F
0x18000b871  lea     rdx, [rsp+278h+var_208]
0x18000b876  lea     rcx, [rsp+278h+var_238]
0x18000b87b  call    ?FlushTenantRestrictionsDataToRegistry@TenantRestrictionsHelpers@@YAXAEAUTenantRestrictionsData@1@AEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry(TenantRestrictionsHelpers::TenantRestrictionsData &,std::unordered_map<std::wstring,std::wstring> &)
0x18000b880  lea     rax, [rsp+278h+var_208]
0x18000b885  cmp     rsi, rax
0x18000b888  jz      short loc_18000B8D3
0x18000b88a  mov     [rsp+278h+var_248], rsi
0x18000b88f  mov     eax, [rsp+278h+var_208]
0x18000b893  mov     [rsi], eax
0x18000b895  mov     rdx, [rsp+278h+var_200]
0x18000b89a  mov     r8, rdx
0x18000b89d  mov     rdx, [rdx]
0x18000b8a0  lea     rcx, [rsi+8]
0x18000b8a4  call    ??$_Assign_cast@AEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<std::pair<std::wstring const,std::wstring>>::_Assign_cast<std::pair<std::wstring,std::wstring> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>)
0x18000b8a9  mov     rdx, [rsi+10h]
0x18000b8ad  mov     rcx, rsi
0x18000b8b0  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000b8b5  mov     rdx, rax
0x18000b8b8  mov     rcx, rsi
0x18000b8bb  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(unsigned __int64)
0x18000b8c0  mov     [rsp+278h+var_248], 0
0x18000b8c9  lea     rcx, [rsp+278h+var_248]
0x18000b8ce  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18000b8d3  call    ?wnf_publish@wil@@YAXAEBU_WNF_STATE_NAME@@@Z; wil::wnf_publish(_WNF_STATE_NAME const &)
0x18000b8d8  nop
0x18000b8d9  lea     rcx, [rsp+278h+var_238]; this
0x18000b8de  call    ??1TenantRestrictionsData@TenantRestrictionsHelpers@@QEAA@XZ; TenantRestrictionsHelpers::TenantRestrictionsData::~TenantRestrictionsData(void)
0x18000b8e3  lea     rcx, [rsp+278h+var_78]
0x18000b8eb  call    ?GetLocalTimeAsString@TenantRestrictionsHelpers@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; TenantRestrictionsHelpers::GetLocalTimeAsString(void)
0x18000b8f0  lea     rcx, [r14+0B8h]
0x18000b8f7  mov     rdx, rax
0x18000b8fa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000b8ff  lea     rcx, [rsp+278h+var_78]
0x18000b907  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b90c  mov     [rsp+278h+var_98], 1
0x18000b914  mov     [rsp+278h+var_94], 0
0x18000b91f  lea     rcx, [rsp+278h+var_208]
0x18000b924  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000b929  nop
0x18000b92a  lea     rcx, [rsp+278h+var_188]; this
0x18000b932  call    ??1AutoMeasureLogger@TenantRestrictionsLoggers@@UEAA@XZ; TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger(void)
0x18000b937  xor     eax, eax
0x18000b939  jmp     short loc_18000B93F
0x18000b93b  mov     eax, dword ptr [rsp+278h+var_248]
0x18000b93f  mov     rcx, [rsp+278h+var_38]
0x18000b947  xor     rcx, rsp; StackCookie
0x18000b94a  call    __security_check_cookie
0x18000b94f  lea     r11, [rsp+278h+var_28]
0x18000b957  mov     rbx, [r11+38h]
0x18000b95b  mov     rsi, [r11+40h]
0x18000b95f  mov     rsp, r11
0x18000b962  pop     r15
0x18000b964  pop     r14
0x18000b966  pop     r13
0x18000b968  pop     r12
0x18000b96a  pop     rdi
0x18000b96b  retn
0x18000b96c  lea     rdx, [rbx+10h]
0x18000b970  lea     rcx, [rsp+278h+var_58]
0x18000b978  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000b97d  nop
0x18000b97e  mov     rcx, r14
0x18000b981  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b986  mov     r9, rax
0x18000b989  lea     rcx, [rsp+278h+var_58]
0x18000b991  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b996  mov     r8, rax
0x18000b999  mov     ecx, [r14+60h]
0x18000b99d  mov     [rsp+278h+var_258], ecx
0x18000b9a1  lea     rdx, aEndpoints; "/endpoints"
0x18000b9a8  lea     rcx, [rsp+278h+var_78]
0x18000b9b0  call    ?GetTenantRestrictionsO365ApiData@TenantRestrictionsHelpers@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00K@Z; TenantRestrictionsHelpers::GetTenantRestrictionsO365ApiData(ushort const *,ushort const *,ushort const *,ulong)
0x18000b9b5  nop
0x18000b9b6  lea     rcx, [rsp+278h+var_78]
0x18000b9be  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b9c3  mov     rdx, rax
0x18000b9c6  lea     rcx, [rsp+278h+var_1C8]
0x18000b9ce  call    ?ParseTenantRestrictionsHostnameAndIPData@TenantRestrictionsHelpers@@YA?AUTenantRestrictionsData@1@PEBG@Z; TenantRestrictionsHelpers::ParseTenantRestrictionsHostnameAndIPData(ushort const *)
0x18000b9d3  nop
0x18000b9d4  mov     rdx, [rsp+278h+var_1C8]
0x18000b9dc  mov     r8, rdx
0x18000b9df  mov     rdx, [rdx]
0x18000b9e2  lea     rcx, [rsp+278h+var_238]
0x18000b9e7  call    ??$_Insert_range_unchecked@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18000b9ec  mov     rdx, [rsp+278h+var_1B8]
0x18000b9f4  mov     r8, rdx
0x18000b9f7  mov     rdx, [rdx]
0x18000b9fa  lea     rcx, [rsp+278h+var_228]
0x18000b9ff  call    ??$_Insert_range_unchecked@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18000ba04  mov     rdx, [rsp+278h+var_1A8]
0x18000ba0c  mov     r8, rdx
0x18000ba0f  mov     rdx, [rdx]
0x18000ba12  lea     rcx, [rsp+278h+var_218]
0x18000ba17  call    ??$_Insert_range_unchecked@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18000ba1c  nop
0x18000ba1d  lea     rcx, [rsp+278h+var_1C8]; this
0x18000ba25  call    ??1TenantRestrictionsData@TenantRestrictionsHelpers@@QEAA@XZ; TenantRestrictionsHelpers::TenantRestrictionsData::~TenantRestrictionsData(void)
0x18000ba2a  nop
0x18000ba2b  lea     rcx, [rsp+278h+var_78]
0x18000ba33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ba38  nop
0x18000ba39  lea     rcx, [rsp+278h+var_58]
0x18000ba41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ba46  mov     rbx, [rbx]
0x18000ba49  jmp     loc_18000B811
```
