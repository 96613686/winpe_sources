# _std::list_Command_std::allocator_Command___::assign_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch$0

- ea: `0x18000ce86`
- end: `0x18000cea6`
- name: `_std::list_Command_std::allocator_Command___::assign_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch$0`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007d24`
- `0x18000c4b0`

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
0x18000ce86  mov     [rsp+arg_8], rdx
0x18000ce8b  push    rbp
0x18000ce8c  sub     rsp, 20h
0x18000ce90  mov     rbp, rdx
0x18000ce93  mov     rcx, [rbp+50h]
0x18000ce97  call    ?clear@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ; std::list<Command>::clear(void)
0x18000ce9c  xor     edx, edx; pThrowInfo
0x18000ce9e  xor     ecx, ecx; pExceptionObject
0x18000cea0  call    _CxxThrowException_0
```
