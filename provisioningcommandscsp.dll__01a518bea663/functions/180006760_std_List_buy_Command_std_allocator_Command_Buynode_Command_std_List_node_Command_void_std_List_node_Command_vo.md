# std::_List_buy<Command,std::allocator<Command>>::_Buynode<Command>(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *,Command &&)

- ea: `0x180006760`
- end: `0x18000679a`
- name: `??$_Buynode@UCommand@@@?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@1@PEAU21@0$$QEAUCommand@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const struct Command *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800067a0`
- `0x18000a0dc`
- `0x18000a3b0`

## callees

- `0x1800068e4`
- `0x180007698`

## pseudocode

```c
__int64 __fastcall std::_List_buy<Command>::_Buynode<Command>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const struct Command *a4)
{
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 result; // rax
  __int64 v9; // [rsp+30h] [rbp+8h]

  v5 = std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0();
  v6 = v5;
  v9 = v5;
  try
  {
    Command::Command((Command *)(v5 + 16), a4);
    result = v6;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v7, v9);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180006760  mov     [rsp+arg_8], rbx
0x180006765  mov     [rsp+arg_0], rcx
0x18000676a  push    rdi
0x18000676b  sub     rsp, 20h
0x18000676f  mov     rdi, r9
0x180006772  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x180006777  mov     rbx, rax
0x18000677a  mov     [rsp+28h+arg_0], rax
0x18000677f  lea     rcx, [rax+10h]; this
0x180006783  mov     rdx, rdi; struct Command *
0x180006786  call    ??0Command@@QEAA@AEBU0@@Z; Command::Command(Command const &)
0x18000678b  nop
0x18000678c  mov     rax, rbx
0x18000678f  mov     rbx, [rsp+28h+arg_8]
0x180006794  add     rsp, 20h
0x180006798  pop     rdi
0x180006799  retn
```
