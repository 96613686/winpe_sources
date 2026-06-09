# std::_List_buy<CommandSet,std::allocator<CommandSet>>::_Buynode<CommandSet>(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *,CommandSet &&)

- ea: `0x18000a330`
- end: `0x18000a3a8`
- name: `??$_Buynode@UCommandSet@@@?$_List_buy@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@1@PEAU21@0$$QEAUCommandSet@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b7dc`

## callees

- `0x180007b08`
- `0x18000a444`
- `0x18000ba18`

## pseudocode

```c
__int64 __fastcall std::_List_buy<CommandSet>::_Buynode<CommandSet>(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 result; // rax
  __int64 v10; // [rsp+30h] [rbp+8h]

  v5 = std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(a1, a2, a3);
  v6 = v5;
  v10 = v5;
  v7 = v5 + 16;
  *(_DWORD *)(v5 + 16) = *a4;
  try
  {
    std::list<Command>::list<Command>();
    *(_QWORD *)(v7 + 48) = 7;
    *(_QWORD *)(v7 + 40) = 0;
    *(_WORD *)(v7 + 24) = 0;
    std::wstring::assign((void *)(v7 + 24));
    result = v6;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v8, v10);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000a330  mov     [rsp+arg_8], rbx
0x18000a335  mov     [rsp+arg_10], rsi
0x18000a33a  mov     [rsp+arg_0], rcx
0x18000a33f  push    rdi
0x18000a340  sub     rsp, 20h
0x18000a344  mov     rsi, r9
0x18000a347  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x18000a34c  mov     rdi, rax
0x18000a34f  mov     [rsp+28h+arg_0], rax
0x18000a354  lea     rbx, [rax+10h]
0x18000a358  mov     [rsp+28h+arg_18], rbx
0x18000a35d  mov     ecx, [rsi]
0x18000a35f  mov     [rbx], ecx
0x18000a361  lea     rdx, [rsi+8]
0x18000a365  lea     rcx, [rbx+8]
0x18000a369  call    ??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@AEBV01@@Z; std::list<Command>::list<Command>(std::list<Command> const &)
0x18000a36e  nop
0x18000a36f  lea     rcx, [rbx+18h]; void *
0x18000a373  mov     qword ptr [rcx+18h], 7
0x18000a37b  xor     eax, eax
0x18000a37d  mov     [rcx+10h], rax
0x18000a381  mov     [rcx], ax
0x18000a384  lea     rdx, [rsi+18h]
0x18000a388  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000a38c  xor     r8d, r8d
0x18000a38f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000a394  nop
0x18000a395  mov     rax, rdi
0x18000a398  mov     rbx, [rsp+28h+arg_8]
0x18000a39d  mov     rsi, [rsp+28h+arg_10]
0x18000a3a2  add     rsp, 20h
0x18000a3a6  pop     rdi
0x18000a3a7  retn
```
