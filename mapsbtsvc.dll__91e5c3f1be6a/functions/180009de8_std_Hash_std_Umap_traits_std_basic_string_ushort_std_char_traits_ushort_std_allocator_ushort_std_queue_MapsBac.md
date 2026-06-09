# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>>,0>>::_Erase<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180009de8`
- end: `0x180009e8b`
- name: `??$_Erase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@AEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `163`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f308`

## callees

- `0x180009de8`
- `0x180009f40`
- `0x18000a08c`
- `0x18000b880`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Erase<std::wstring>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // r11
  _QWORD *v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  _BYTE v11[24]; // [rsp+20h] [rbp-18h] BYREF

  v3 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a2);
  v5 = *(_QWORD **)(std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
                      a1,
                      v11,
                      v4,
                      v3)
                  + 8);
  if ( !v5 )
    return 0;
  v6 = a1[3];
  v7 = 2 * (v3 & a1[6]);
  if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6]) + 8) == v5 )
  {
    if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6])) == v5 )
    {
      v8 = a1[1];
      *(_QWORD *)(v6 + 16 * (v3 & a1[6])) = v8;
    }
    else
    {
      v8 = v5[1];
    }
    *(_QWORD *)(v6 + 8 * v7 + 8) = v8;
  }
  else if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6])) == v5 )
  {
    *(_QWORD *)(v6 + 16 * (v3 & a1[6])) = *v5;
  }
  v9 = *v5;
  --a1[2];
  *(_QWORD *)v5[1] = v9;
  *(_QWORD *)(v9 + 8) = v5[1];
  std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>>>();
  return 1;
}

```

## disassembly

```asm
0x180009de8  mov     [rsp+arg_0], rbx
0x180009ded  push    rdi
0x180009dee  sub     rsp, 30h
0x180009df2  mov     rbx, rcx
0x180009df5  mov     r11, rdx
0x180009df8  mov     rcx, rdx
0x180009dfb  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180009e00  mov     r9, rax
0x180009e03  lea     rdx, [rsp+38h+var_18]
0x180009e08  mov     r8, r11
0x180009e0b  mov     rcx, rbx
0x180009e0e  mov     rdi, rax
0x180009e11  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180009e16  mov     rdx, [rax+8]
0x180009e1a  test    rdx, rdx
0x180009e1d  jz      short loc_180009E7E
0x180009e1f  mov     rcx, [rbx+30h]
0x180009e23  mov     r8, [rbx+18h]
0x180009e27  and     rcx, rdi
0x180009e2a  add     rcx, rcx
0x180009e2d  cmp     [r8+rcx*8+8], rdx
0x180009e32  jnz     short loc_180009E4F
0x180009e34  cmp     [r8+rcx*8], rdx
0x180009e38  jnz     short loc_180009E44
0x180009e3a  mov     rax, [rbx+8]
0x180009e3e  mov     [r8+rcx*8], rax
0x180009e42  jmp     short loc_180009E48
0x180009e44  mov     rax, [rdx+8]
0x180009e48  mov     [r8+rcx*8+8], rax
0x180009e4d  jmp     short loc_180009E5C
0x180009e4f  cmp     [r8+rcx*8], rdx
0x180009e53  jnz     short loc_180009E5C
0x180009e55  mov     rax, [rdx]
0x180009e58  mov     [r8+rcx*8], rax
0x180009e5c  mov     rcx, [rdx]
0x180009e5f  dec     qword ptr [rbx+10h]
0x180009e63  mov     rax, [rdx+8]
0x180009e67  mov     [rax], rcx
0x180009e6a  mov     rax, [rdx+8]
0x180009e6e  mov     [rcx+8], rax
0x180009e72  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *>> &,std::_List_node<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>,void *> *)
0x180009e77  mov     eax, 1
0x180009e7c  jmp     short loc_180009E80
0x180009e7e  xor     eax, eax
0x180009e80  mov     rbx, [rsp+38h+arg_0]
0x180009e85  add     rsp, 30h
0x180009e89  pop     rdi
0x180009e8a  retn
```
