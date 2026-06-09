# std::map<_GUID,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,DusmCache::DusmCacheCost,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,DusmCache::DusmCacheCost>>>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,DusmCache::DusmCacheCost,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,DusmCache::DusmCacheCost>>>>>>::_Try_emplace<_GUID const &,>(_GUID const &)

- ea: `0x18001aae4`
- end: `0x18001abf1`
- name: `??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@UGuidCompare@DusmCache@@V?$allocator@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(__int64 *, __int64, const void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001cee0`

## callees

- `0x18000da4c`
- `0x18000dc64`
- `0x180012e18`
- `0x18001a730`
- `0x18001aa4c`
- `0x18001aae4`
- `0x18001ad40`
- `0x18001b038`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001ab41`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001ab41`

## pseudocode

```c
__int64 __fastcall std::map<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>>::_Try_emplace<_GUID const &,>(
        __int64 *a1,
        __int64 a2,
        const void *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v12[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v13; // [rsp+40h] [rbp-30h] BYREF
  const void *v14; // [rsp+50h] [rbp-20h] BYREF
  __int128 v15; // [rsp+58h] [rbp-18h] BYREF
  __int64 v16; // [rsp+68h] [rbp-8h]

  std::_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>::_Find_lower_bound<_GUID>(
    (__int64)a1,
    &v15,
    a3);
  v6 = v16;
  if ( std::_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>::_Lower_bound_duplicate<_GUID>(
         v7,
         v16,
         a3) )
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x3FFFFFFFFFFFFFFLL )
      std::_Xlength_error("map/set too long");
    v14 = a3;
    v12[0] = *a1;
    *(_QWORD *)&v13 = a1;
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(0x40u);
    *((_QWORD *)&v13 + 1) = v8;
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *>>>::construct<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,std::piecewise_construct_t const &,std::tuple<_GUID const &>,std::tuple<>>(
      v9,
      v8 + 4,
      v10,
      &v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(
      v8,
      v12);
    std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(
      v8 + 1,
      v12);
    std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(
      v8 + 2,
      v12);
    *((_WORD *)v8 + 12) = 0;
    *((_QWORD *)&v13 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *>>>(&v13);
    v13 = v15;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DUSM_NETWORK_USAGE>>>::_Insert_node(
                      a1,
                      &v13,
                      v8);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x18001aae4  mov     [rsp-18h+arg_10], rbx
0x18001aae9  mov     [rsp-18h+arg_18], rsi
0x18001aaee  push    rbp
0x18001aaef  push    rdi
0x18001aaf0  push    r14
0x18001aaf2  mov     rbp, rsp
0x18001aaf5  sub     rsp, 70h
0x18001aaf9  mov     r14, r8
0x18001aafc  mov     rdi, rdx
0x18001aaff  mov     rsi, rcx
0x18001ab02  lea     rdx, [rbp+var_18]
0x18001ab06  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@UGuidCompare@DusmCache@@V?$allocator@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18001ab0b  mov     r8, r14
0x18001ab0e  mov     rbx, [rbp+var_8]
0x18001ab12  mov     rdx, rbx
0x18001ab15  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@UGuidCompare@DusmCache@@V?$allocator@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * const,_GUID const &)
0x18001ab1a  test    al, al
0x18001ab1c  jz      short loc_18001AB2A
0x18001ab1e  mov     [rdi], rbx
0x18001ab21  mov     byte ptr [rdi+8], 0
0x18001ab25  jmp     loc_18001ABD9
0x18001ab2a  mov     rax, 3FFFFFFFFFFFFFFh
0x18001ab34  cmp     [rsi+8], rax
0x18001ab38  jnz     short loc_18001AB48
0x18001ab3a  lea     rcx, aMapSetTooLong; "map/set too long"
0x18001ab41  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001ab48  mov     [rbp+var_20], r14
0x18001ab4c  mov     rax, [rsi]
0x18001ab4f  mov     [rbp+var_40], rax
0x18001ab53  mov     qword ptr [rbp+var_30], rsi
0x18001ab57  mov     qword ptr [rbp+var_30+8], 0
0x18001ab5f  mov     ecx, 40h ; '@'
0x18001ab64  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001ab69  mov     rbx, rax
0x18001ab6c  mov     qword ptr [rbp+var_30+8], rax
0x18001ab70  lea     rdx, [rax+20h]
0x18001ab74  lea     r9, [rbp+var_20]
0x18001ab78  call    ??$construct@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBU_GUID@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBU_GUID@@@1@$$QEAV?$tuple@$$V@1@@Z
0x18001ab7d  lea     rdx, [rbp+var_40]
0x18001ab81  mov     rcx, rbx
0x18001ab84  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &)
0x18001ab89  lea     rcx, [rbx+8]
0x18001ab8d  lea     rdx, [rbp+var_40]
0x18001ab91  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &)
0x18001ab96  lea     rcx, [rbx+10h]
0x18001ab9a  lea     rdx, [rbp+var_40]
0x18001ab9e  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &)
0x18001aba3  mov     word ptr [rbx+18h], 0
0x18001aba9  mov     qword ptr [rbp+var_30+8], 0
0x18001abb1  lea     rcx, [rbp+var_30]
0x18001abb5  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *>>>(void)
0x18001abba  movups  xmm0, [rbp+var_18]
0x18001abbe  movdqu  [rbp+var_30], xmm0
0x18001abc3  mov     r8, rbx
0x18001abc6  lea     rdx, [rbp+var_30]
0x18001abca  mov     rcx, rsi
0x18001abcd  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDUSM_NETWORK_USAGE@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDUSM_NETWORK_USAGE@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDUSM_NETWORK_USAGE@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DUSM_NETWORK_USAGE>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,DUSM_NETWORK_USAGE>,void *> *>,std::_Tree_node<std::pair<std::wstring const,DUSM_NETWORK_USAGE>,void *> * const)
0x18001abd2  mov     [rdi], rax
0x18001abd5  mov     byte ptr [rdi+8], 1
0x18001abd9  mov     rax, rdi
0x18001abdc  lea     r11, [rsp+70h+var_s0]
0x18001abe1  mov     rbx, [r11+30h]
0x18001abe5  mov     rsi, [r11+38h]
0x18001abe9  mov     rsp, r11
0x18001abec  pop     r14
0x18001abee  pop     rdi
0x18001abef  pop     rbp
0x18001abf0  retn
```
