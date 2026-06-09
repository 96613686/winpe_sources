# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::_Try_emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000a460`
- end: `0x18000a55c`
- name: `??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `252`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000dd10`

## callees

- `0x180003a00`
- `0x180009f40`
- `0x18000a460`
- `0x18000a88c`
- `0x18000b184`
- `0x18000b880`
- `0x18000fcec`
- `0x18000fd1c`
- `0x1800106e4`
- `0x18001076c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Try_emplace<std::wstring const &,>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r14
  _QWORD *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // r8
  _QWORD *v11; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v12; // [rsp+38h] [rbp-18h]
  __int128 v13; // [rsp+40h] [rbp-10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+20h] BYREF

  v6 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a3);
  std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
    a1,
    &v13,
    a3,
    v6);
  if ( *((_QWORD *)&v13 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v13 + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Check_max_size(a1);
    v14 = a3;
    v11 = a1 + 1;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x38u);
    v12 = v7;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>::construct<std::pair<std::wstring const,unsigned long>,std::piecewise_construct_t const &,std::tuple<std::wstring const &>,std::tuple<>>(
      v8,
      v7 + 2,
      v9,
      &v14);
    if ( (unsigned __int8)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Rehash_for_1(a1);
      v13 = *(_OWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
                         a1,
                         &v13,
                         (__int64)(v7 + 2),
                         v6);
    }
    v12 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      v13,
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>(&v11);
  }
  return a2;
}

```

## disassembly

```asm
0x18000a460  mov     [rsp-18h+arg_8], rbx
0x18000a465  mov     [rsp-18h+arg_10], rsi
0x18000a46a  push    rbp
0x18000a46b  push    rdi
0x18000a46c  push    r14
0x18000a46e  mov     rbp, rsp
0x18000a471  sub     rsp, 50h
0x18000a475  mov     rsi, r8
0x18000a478  mov     rbx, rdx
0x18000a47b  mov     rdi, rcx
0x18000a47e  mov     rcx, r8
0x18000a481  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000a486  mov     r14, rax
0x18000a489  mov     r9, rax
0x18000a48c  mov     r8, rsi
0x18000a48f  lea     rdx, [rbp+var_10]
0x18000a493  mov     rcx, rdi
0x18000a496  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000a49b  mov     rcx, qword ptr [rbp+var_10+8]
0x18000a49f  test    rcx, rcx
0x18000a4a2  jz      short loc_18000A4B0
0x18000a4a4  mov     [rbx], rcx
0x18000a4a7  mov     byte ptr [rbx+8], 0
0x18000a4ab  jmp     loc_18000A544
0x18000a4b0  mov     rcx, rdi
0x18000a4b3  call    ?_Check_max_size@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBAXXZ; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Check_max_size(void)
0x18000a4b8  mov     [rbp+arg_0], rsi
0x18000a4bc  lea     rax, [rdi+8]
0x18000a4c0  mov     [rbp+var_20], rax
0x18000a4c4  mov     [rbp+var_18], 0
0x18000a4cc  mov     ecx, 38h ; '8'
0x18000a4d1  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a4d6  mov     rsi, rax
0x18000a4d9  mov     [rbp+var_18], rax
0x18000a4dd  lea     rdx, [rax+10h]
0x18000a4e1  lea     r9, [rbp+arg_0]
0x18000a4e5  call    ??$construct@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>::construct<std::pair<std::wstring const,ulong>,std::piecewise_construct_t const &,std::tuple<std::wstring const &>,std::tuple<>>(std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>> &,std::pair<std::wstring const,ulong> * const,std::piecewise_construct_t const &,std::tuple<std::wstring const &> &&,std::tuple<> &&)
0x18000a4ea  nop
0x18000a4eb  mov     rcx, rdi
0x18000a4ee  call    ?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_NXZ; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Check_rehash_required_1(void)
0x18000a4f3  test    al, al
0x18000a4f5  jz      short loc_18000A51A
0x18000a4f7  mov     rcx, rdi
0x18000a4fa  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Rehash_for_1(void)
0x18000a4ff  lea     r8, [rsi+10h]
0x18000a503  mov     r9, r14
0x18000a506  lea     rdx, [rbp+var_10]
0x18000a50a  mov     rcx, rdi
0x18000a50d  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000a512  movups  xmm0, xmmword ptr [rax]
0x18000a515  movdqu  [rbp+var_10], xmm0
0x18000a51a  mov     [rbp+var_18], 0
0x18000a522  mov     r9, rsi
0x18000a525  mov     r8, qword ptr [rbp+var_10]
0x18000a529  mov     rdx, r14
0x18000a52c  mov     rcx, rdi
0x18000a52f  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *> * const,std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *> * const)
0x18000a534  mov     [rbx], rax
0x18000a537  mov     byte ptr [rbx+8], 1
0x18000a53b  lea     rcx, [rbp+var_20]
0x18000a53f  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>(void)
0x18000a544  mov     rax, rbx
0x18000a547  lea     r11, [rsp+50h+var_s0]
0x18000a54c  mov     rbx, [r11+28h]
0x18000a550  mov     rsi, [r11+30h]
0x18000a554  mov     rsp, r11
0x18000a557  pop     r14
0x18000a559  pop     rdi
0x18000a55a  pop     rbp
0x18000a55b  retn
```
