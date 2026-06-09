# std::_List_buy<Command,std::allocator<Command>>::~_List_buy<Command,std::allocator<Command>>(void)

- ea: `0x18000a474`
- end: `0x18000a47e`
- name: `??1?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000daa4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a477`

## pseudocode

```c
void __fastcall std::_List_buy<Command>::~_List_buy<Command>(void **a1)
{
  operator delete(*a1);
}

```

## disassembly

```asm
0x18000a474  mov     rcx, [rcx]
0x18000a477  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
