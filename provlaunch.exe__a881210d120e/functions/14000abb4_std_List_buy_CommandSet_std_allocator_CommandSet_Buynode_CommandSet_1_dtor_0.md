# _std::_List_buy_CommandSet_std::allocator_CommandSet___::_Buynode_CommandSet__::_1_::dtor$0

- ea: `0x14000abb4`
- end: `0x14000abc4`
- name: `_std::_List_buy_CommandSet_std::allocator_CommandSet___::_Buynode_CommandSet__::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007c70`

## pseudocode

```c
void __fastcall std::_List_buy_CommandSet_std::allocator_CommandSet___::_Buynode_CommandSet__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::list<Command>::~list<Command>((void ***)(*(_QWORD *)(a2 + 72) + 8LL));
}

```

## disassembly

```asm
0x14000abb4  mov     rcx, [rdx+48h]
0x14000abbb  add     rcx, 8; void *
0x14000abbf  jmp     ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
```
