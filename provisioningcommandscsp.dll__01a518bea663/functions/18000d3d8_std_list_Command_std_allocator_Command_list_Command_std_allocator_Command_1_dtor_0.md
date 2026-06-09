# _std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::dtor$0

- ea: `0x18000d3d8`
- end: `0x18000d3e4`
- name: `_std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009f90`

## pseudocode

```c
void __fastcall std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::_List_buy<Command>::~_List_buy<Command>(*(void ***)(a2 + 64));
}

```

## disassembly

```asm
0x18000d3d8  mov     rcx, [rdx+40h]
0x18000d3df  jmp     ??1?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::_List_buy<Command>::~_List_buy<Command>(void)
```
