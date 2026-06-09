# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)

- ea: `0x1800102a8`
- end: `0x180010341`
- name: `??$_Emplace@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAPEAU?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@1@QEAU21@$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800123fc`
- `0x18001266c`

## callees

- `0x18000183c`
- `0x1800102a8`
- `0x1800111f0`
- `0x180011d0c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800102d1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800102d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
        __int64 a1,
        __int64 a2,
        const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *a3)
{
  _QWORD *v6; // rbx
  _QWORD *v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-38h] BYREF
  _QWORD *v10; // [rsp+28h] [rbp-30h]

  if ( *(_QWORD *)(a1 + 8) == 0x199999999999999LL )
    std::_Xlength_error("list too long");
  v9 = a1;
  v6 = operator new(0xA0u);
  v10 = v6;
  Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
    (Microsoft::Windows::Performance::CCvDDCache::CCvDD *)(v6 + 2),
    a3);
  ++*(_QWORD *)(a1 + 8);
  v7 = *(_QWORD **)(a2 + 8);
  *v6 = a2;
  v6[1] = v7;
  v10 = 0;
  *(_QWORD *)(a2 + 8) = v6;
  *v7 = v6;
  std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(&v9);
  return v6;
}

```

## disassembly

```asm
0x1800102a8  push    rbx
0x1800102aa  push    rbp
0x1800102ab  push    rsi
0x1800102ac  push    rdi
0x1800102ad  sub     rsp, 38h
0x1800102b1  mov     rbp, r8
0x1800102b4  mov     rsi, rdx
0x1800102b7  mov     rdi, rcx
0x1800102ba  mov     rax, 199999999999999h
0x1800102c4  cmp     [rcx+8], rax
0x1800102c8  jnz     short loc_1800102DE
0x1800102ca  lea     rcx, aListTooLong; "list too long"
0x1800102d1  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800102de  mov     [rsp+58h+var_38], rdi
0x1800102e3  mov     [rsp+58h+var_30], 0
0x1800102ec  mov     ecx, 0A0h; Size
0x1800102f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800102f6  mov     rbx, rax
0x1800102f9  mov     [rsp+58h+var_30], rax
0x1800102fe  lea     rcx, [rax+10h]; this
0x180010302  mov     rdx, rbp; struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *
0x180010305  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)
0x18001030a  nop
0x18001030b  inc     qword ptr [rdi+8]
0x18001030f  mov     rcx, [rsi+8]
0x180010313  mov     [rbx], rsi
0x180010316  mov     [rbx+8], rcx
0x18001031a  mov     [rsp+58h+var_30], 0
0x180010323  mov     [rsi+8], rbx
0x180010327  mov     [rcx], rbx
0x18001032a  lea     rcx, [rsp+58h+var_38]
0x18001032f  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)
0x180010334  mov     rax, rbx
0x180010337  add     rsp, 38h
0x18001033b  pop     rdi
0x18001033c  pop     rsi
0x18001033d  pop     rbp
0x18001033e  pop     rbx
0x18001033f  retn
```
