# std::_List_buy<Command,std::allocator<Command>>::_Buynode<Command>(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *,Command &&)

- ea: `0x1400080e0`
- end: `0x14000811a`
- name: `??$_Buynode@UCommand@@@?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@1@PEAU21@0$$QEAUCommand@@@Z`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007e3c`
- `0x1400081a0`

## callees

- `0x140007d20`
- `0x1400082c4`

## pseudocode

```c
_QWORD *__fastcall std::_List_buy<Command>::_Buynode<Command>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        const struct Command *a4)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  __int64 v7; // rcx
  _QWORD *result; // rax
  _QWORD *v9; // [rsp+30h] [rbp+8h]

  v5 = std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(a1, a2, a3);
  v6 = v5;
  v9 = v5;
  try
  {
    Command::Command((Command *)(v5 + 2), a4);
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
0x1400080e0  mov     [rsp+arg_8], rbx
0x1400080e5  mov     [rsp+arg_0], rcx
0x1400080ea  push    rdi
0x1400080eb  sub     rsp, 20h
0x1400080ef  mov     rdi, r9
0x1400080f2  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x1400080f7  mov     rbx, rax
0x1400080fa  mov     [rsp+28h+arg_0], rax
0x1400080ff  lea     rcx, [rax+10h]; this
0x140008103  mov     rdx, rdi; struct Command *
0x140008106  call    ??0Command@@QEAA@AEBU0@@Z; Command::Command(Command const &)
0x14000810b  nop
0x14000810c  mov     rax, rbx
0x14000810f  mov     rbx, [rsp+28h+arg_8]
0x140008114  add     rsp, 20h
0x140008118  pop     rdi
0x140008119  retn
```
