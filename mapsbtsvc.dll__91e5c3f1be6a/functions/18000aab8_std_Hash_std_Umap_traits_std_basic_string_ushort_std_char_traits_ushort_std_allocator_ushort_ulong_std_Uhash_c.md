# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::emplace<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong>>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong> &&)

- ea: `0x18000aab8`
- end: `0x18000aba5`
- name: `??$emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@1@@Z`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000dd10`

## callees

- `0x180003a00`
- `0x180009f40`
- `0x18000a8e8`
- `0x18000aab8`
- `0x18000b184`
- `0x18000b880`
- `0x18000fcec`
- `0x18000fd1c`
- `0x1800106e4`
- `0x18001076c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::emplace<std::pair<std::wstring,unsigned long>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbp
  _QWORD *v7; // rsi
  __int64 v8; // rcx
  _QWORD *v10; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v11; // [rsp+28h] [rbp-40h]
  _OWORD v12[3]; // [rsp+30h] [rbp-38h] BYREF

  v6 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a3);
  std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
    a1,
    v12,
    a3,
    v6);
  if ( *((_QWORD *)&v12[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v12[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Check_max_size(a1);
    v10 = a1 + 1;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x38u);
    v11 = v7;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>::construct<std::pair<std::wstring const,unsigned long>,std::pair<std::wstring,unsigned long>>(
      v8,
      v7 + 2,
      a3);
    if ( (unsigned __int8)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Rehash_for_1(a1);
      v12[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
                            a1,
                            v12,
                            (__int64)(v7 + 2),
                            v6);
    }
    v11 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      *(_QWORD *)&v12[0],
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>(&v10);
  }
  return a2;
}

```

## disassembly

```asm
0x18000aab8  push    rbx
0x18000aaba  push    rbp
0x18000aabb  push    rsi
0x18000aabc  push    rdi
0x18000aabd  push    r14
0x18000aabf  sub     rsp, 40h
0x18000aac3  mov     r14, r8
0x18000aac6  mov     rbx, rdx
0x18000aac9  mov     rdi, rcx
0x18000aacc  mov     rcx, r8
0x18000aacf  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000aad4  mov     rbp, rax
0x18000aad7  mov     r9, rax
0x18000aada  mov     r8, r14
0x18000aadd  lea     rdx, [rsp+68h+var_38]
0x18000aae2  mov     rcx, rdi
0x18000aae5  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000aaea  mov     rcx, qword ptr [rsp+68h+var_38+8]
0x18000aaef  test    rcx, rcx
0x18000aaf2  jz      short loc_18000AB00
0x18000aaf4  mov     [rbx], rcx
0x18000aaf7  mov     byte ptr [rbx+8], 0
0x18000aafb  jmp     loc_18000AB97
0x18000ab00  mov     rcx, rdi
0x18000ab03  call    ?_Check_max_size@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBAXXZ; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Check_max_size(void)
0x18000ab08  lea     rax, [rdi+8]
0x18000ab0c  mov     [rsp+68h+var_48], rax
0x18000ab11  mov     [rsp+68h+var_40], 0
0x18000ab1a  mov     ecx, 38h ; '8'
0x18000ab1f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000ab24  mov     rsi, rax
0x18000ab27  mov     [rsp+68h+var_40], rax
0x18000ab2c  lea     rdx, [rax+10h]
0x18000ab30  mov     r8, r14
0x18000ab33  call    ??$construct@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>::construct<std::pair<std::wstring const,ulong>,std::pair<std::wstring,ulong>>(std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>> &,std::pair<std::wstring const,ulong> * const,std::pair<std::wstring,ulong> &&)
0x18000ab38  nop
0x18000ab39  mov     rcx, rdi
0x18000ab3c  call    ?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_NXZ; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Check_rehash_required_1(void)
0x18000ab41  test    al, al
0x18000ab43  jz      short loc_18000AB6A
0x18000ab45  mov     rcx, rdi
0x18000ab48  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Rehash_for_1(void)
0x18000ab4d  lea     r8, [rsi+10h]
0x18000ab51  mov     r9, rbp
0x18000ab54  lea     rdx, [rsp+68h+var_38]
0x18000ab59  mov     rcx, rdi
0x18000ab5c  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000ab61  movups  xmm0, xmmword ptr [rax]
0x18000ab64  movdqu  [rsp+68h+var_38], xmm0
0x18000ab6a  mov     [rsp+68h+var_40], 0
0x18000ab73  mov     r9, rsi
0x18000ab76  mov     r8, qword ptr [rsp+68h+var_38]
0x18000ab7b  mov     rdx, rbp
0x18000ab7e  mov     rcx, rdi
0x18000ab81  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *> * const,std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *> * const)
0x18000ab86  mov     [rbx], rax
0x18000ab89  mov     byte ptr [rbx+8], 1
0x18000ab8d  lea     rcx, [rsp+68h+var_48]
0x18000ab92  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>(void)
0x18000ab97  mov     rax, rbx
0x18000ab9a  add     rsp, 40h
0x18000ab9e  pop     r14
0x18000aba0  pop     rdi
0x18000aba1  pop     rsi
0x18000aba2  pop     rbp
0x18000aba3  pop     rbx
0x18000aba4  retn
```
