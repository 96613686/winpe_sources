# _std::list_Command_std::allocator_Command___::assign_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch$0

- ea: `0x18000d54c`
- end: `0x18000d56c`
- name: `_std::list_Command_std::allocator_Command___::assign_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800080bc`
- `0x18000cb69`

## pseudocode

```c
void __fastcall __noreturn std::list_Command_std::allocator_Command___::assign_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::list<Command>::clear(*(_QWORD *)(a2 + 80));
  throw;
}

```

## disassembly

```asm
0x18000d54c  mov     [rsp+arg_8], rdx
0x18000d551  push    rbp
0x18000d552  sub     rsp, 20h
0x18000d556  mov     rbp, rdx
0x18000d559  mov     rcx, [rbp+50h]
0x18000d55d  call    ?clear@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ; std::list<Command>::clear(void)
0x18000d562  xor     edx, edx; pThrowInfo
0x18000d564  xor     ecx, ecx; pExceptionObject
0x18000d566  call    _CxxThrowException_0
```
