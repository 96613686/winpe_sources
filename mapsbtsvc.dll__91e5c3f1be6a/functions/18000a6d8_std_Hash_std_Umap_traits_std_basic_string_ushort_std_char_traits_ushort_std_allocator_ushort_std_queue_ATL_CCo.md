# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>>,0>>::_Try_emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000a6d8`
- end: `0x18000a846`
- name: `??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `366`
- prototype: `__int64 __fastcall(float *, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c4dc`
- `0x18000dd10`

## callees

- `0x180003a00`
- `0x180005bf0`
- `0x180009f40`
- `0x18000a6d8`
- `0x18000a928`
- `0x18000b1e4`
- `0x18000b880`
- `0x180010274`
- `0x1800106e4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a743`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a743`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Try_emplace<std::wstring const &,>(
        float *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r14
  _QWORD *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  float v11; // xmm0_4
  __int64 v12; // rcx
  float v13; // xmm1_4
  __int64 v14; // rax
  __int64 v15; // rax
  _QWORD *v17; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v18; // [rsp+38h] [rbp-18h]
  __int128 v19; // [rsp+40h] [rbp-10h] BYREF
  __int64 v20; // [rsp+70h] [rbp+20h] BYREF

  v6 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a3);
  std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
    a1,
    &v19,
    a3,
    v6);
  if ( *((_QWORD *)&v19 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v19 + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *((_QWORD *)a1 + 2) == 0x2E8BA2E8BA2E8BALL )
      std::_Xlength_error("unordered_map/set too long");
    v20 = a3;
    v17 = a1 + 2;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x58u);
    v18 = v7;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>>>::construct<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,std::piecewise_construct_t const &,std::tuple<std::wstring const &>,std::tuple<>>(
      v8,
      v7 + 2,
      v9,
      &v20);
    v10 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v10 < 0 )
      v11 = (float)(v10 & 1 | (unsigned int)((unsigned __int64)v10 >> 1))
          + (float)(v10 & 1 | (unsigned int)((unsigned __int64)v10 >> 1));
    else
      v11 = (float)(int)v10;
    v12 = *((_QWORD *)a1 + 7);
    if ( v12 < 0 )
    {
      v14 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v12 >> 1);
      v13 = (float)(int)v14 + (float)(int)v14;
    }
    else
    {
      v13 = (float)(int)v12;
    }
    if ( (float)(v11 / v13) > *a1 )
    {
      v15 = std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Forced_rehash(
        a1,
        v15);
      v19 = *(_OWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
                         a1,
                         &v19,
                         (__int64)(v7 + 2),
                         v6);
    }
    v18 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      v19,
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>(&v17);
  }
  return a2;
}

```

## disassembly

```asm
0x18000a6d8  mov     [rsp-18h+arg_8], rbx
0x18000a6dd  mov     [rsp-18h+arg_10], rsi
0x18000a6e2  push    rbp
0x18000a6e3  push    rdi
0x18000a6e4  push    r14
0x18000a6e6  mov     rbp, rsp
0x18000a6e9  sub     rsp, 50h
0x18000a6ed  mov     rsi, r8
0x18000a6f0  mov     rbx, rdx
0x18000a6f3  mov     rdi, rcx
0x18000a6f6  mov     rcx, r8
0x18000a6f9  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000a6fe  mov     r14, rax
0x18000a701  mov     r9, rax
0x18000a704  mov     r8, rsi
0x18000a707  lea     rdx, [rbp+var_10]
0x18000a70b  mov     rcx, rdi
0x18000a70e  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000a713  mov     rcx, qword ptr [rbp+var_10+8]
0x18000a717  test    rcx, rcx
0x18000a71a  jz      short loc_18000A728
0x18000a71c  mov     [rbx], rcx
0x18000a71f  mov     byte ptr [rbx+8], 0
0x18000a723  jmp     loc_18000A82E
0x18000a728  lea     rax, [rdi+8]
0x18000a72c  mov     rcx, 2E8BA2E8BA2E8BAh
0x18000a736  cmp     [rax+8], rcx
0x18000a73a  jnz     short loc_18000A74A
0x18000a73c  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000a743  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000a74a  mov     [rbp+arg_0], rsi
0x18000a74e  mov     [rbp+var_20], rax
0x18000a752  mov     [rbp+var_18], 0
0x18000a75a  mov     ecx, 58h ; 'X'
0x18000a75f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a764  mov     rsi, rax
0x18000a767  mov     [rbp+var_18], rax
0x18000a76b  lea     rdx, [rax+10h]
0x18000a76f  lea     r9, [rbp+arg_0]
0x18000a773  call    ??$construct@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>>>::construct<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,std::piecewise_construct_t const &,std::tuple<std::wstring const &>,std::tuple<>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>> &,std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>> * const,std::piecewise_construct_t const &,std::tuple<std::wstring const &> &&,std::tuple<> &&)
0x18000a778  nop
0x18000a779  mov     rdx, [rdi+10h]
0x18000a77d  add     rdx, 1
0x18000a781  xorps   xmm0, xmm0
0x18000a784  js      short loc_18000A78D
0x18000a786  cvtsi2ss xmm0, rdx
0x18000a78b  jmp     short loc_18000A7A5
0x18000a78d  mov     rcx, rdx
0x18000a790  shr     rcx, 1
0x18000a793  mov     rax, rdx
0x18000a796  and     eax, 1
0x18000a799  or      rcx, rax
0x18000a79c  cvtsi2ss xmm0, rcx
0x18000a7a1  addss   xmm0, xmm0
0x18000a7a5  mov     rcx, [rdi+38h]
0x18000a7a9  xorps   xmm1, xmm1
0x18000a7ac  test    rcx, rcx
0x18000a7af  js      short loc_18000A7B8
0x18000a7b1  cvtsi2ss xmm1, rcx
0x18000a7b6  jmp     short loc_18000A7CD
0x18000a7b8  mov     rax, rcx
0x18000a7bb  shr     rax, 1
0x18000a7be  and     ecx, 1
0x18000a7c1  or      rax, rcx
0x18000a7c4  cvtsi2ss xmm1, rax
0x18000a7c9  addss   xmm1, xmm1
0x18000a7cd  divss   xmm0, xmm1
0x18000a7d1  comiss  xmm0, dword ptr [rdi]
0x18000a7d4  jbe     short loc_18000A804
0x18000a7d6  mov     rcx, rdi
0x18000a7d9  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000a7de  mov     rdx, rax
0x18000a7e1  mov     rcx, rdi
0x18000a7e4  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Forced_rehash(unsigned __int64)
0x18000a7e9  lea     r8, [rsi+10h]
0x18000a7ed  mov     r9, r14
0x18000a7f0  lea     rdx, [rbp+var_10]
0x18000a7f4  mov     rcx, rdi
0x18000a7f7  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000a7fc  movups  xmm0, xmmword ptr [rax]
0x18000a7ff  movdqu  [rbp+var_10], xmm0
0x18000a804  mov     [rbp+var_18], 0
0x18000a80c  mov     r9, rsi
0x18000a80f  mov     r8, qword ptr [rbp+var_10]
0x18000a813  mov     rdx, r14
0x18000a816  mov     rcx, rdi
0x18000a819  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *> * const,std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *> * const)
0x18000a81e  mov     [rbx], rax
0x18000a821  mov     byte ptr [rbx+8], 1
0x18000a825  lea     rcx, [rbp+var_20]
0x18000a829  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>(void)
0x18000a82e  mov     rax, rbx
0x18000a831  lea     r11, [rsp+50h+var_s0]
0x18000a836  mov     rbx, [r11+28h]
0x18000a83a  mov     rsi, [r11+30h]
0x18000a83e  mov     rsp, r11
0x18000a841  pop     r14
0x18000a843  pop     rdi
0x18000a844  pop     rbp
0x18000a845  retn
```
