# std::_Tree_buy<std::pair<ulong const,CounterHelper *>,std::allocator<std::pair<ulong const,CounterHelper *>>>::_Freenode0(std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *)

- ea: `0x180008f28`
- end: `0x180008f32`
- name: `?_Freenode0@?$_Tree_buy@U?$pair@$$CBKPEAVCounterHelper@@@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@2@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@2@@Z`
- size: `10`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180004220`
- `0x180009d96`
- `0x180009dbc`
- `0x180009de2`
- `0x18000a1da`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008f2b`

## pseudocode

```c
void __fastcall std::_Tree_buy<std::pair<unsigned long const,CounterHelper *>>::_Freenode0(__int64 a1, void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x180008f28  mov     rcx, rdx
0x180008f2b  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
