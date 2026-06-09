# _std::_List_buy_CommandSet_std::allocator_CommandSet___::_Buynode_CommandSet__::_1_::dtor$0

- ea: `0x18000da28`
- end: `0x18000da38`
- name: `_std::_List_buy_CommandSet_std::allocator_CommandSet___::_Buynode_CommandSet__::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a490`

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
0x18000da28  mov     rcx, [rdx+48h]
0x18000da2f  add     rcx, 8; void *
0x18000da33  jmp     ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
```
