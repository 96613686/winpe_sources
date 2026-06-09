# _std::list_Command_std::allocator_Command___::sort_::_1_::dtor$0

- ea: `0x14000ae6d`
- end: `0x14000ae79`
- name: `_std::list_Command_std::allocator_Command___::sort_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007c70`

## pseudocode

```c
void __fastcall std::list_Command_std::allocator_Command___::sort_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::list<Command>::~list<Command>((void ***)(a2 + 48));
}

```

## disassembly

```asm
0x14000ae6d  lea     rcx, [rdx+30h]; void *
0x14000ae74  jmp     ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
```
