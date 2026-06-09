# _std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor$0

- ea: `0x18000dbc9`
- end: `0x18000dbd5`
- name: `_std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006d20`

## pseudocode

```c
void __fastcall std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::list<CommandSet>::~list<CommandSet>((void ***)(a2 + 48));
}

```

## disassembly

```asm
0x18000dbc9  lea     rcx, [rdx+30h]; void *
0x18000dbd0  jmp     ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
```
