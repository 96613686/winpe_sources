# std::_List_buy<Command,std::allocator<Command>>::~_List_buy<Command,std::allocator<Command>>(void)

- ea: `0x180009f90`
- end: `0x180009f9a`
- name: `??1?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d3d8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009f93`

## pseudocode

```c
void __fastcall std::_List_buy<Command>::~_List_buy<Command>(void **a1)
{
  operator delete(*a1);
}

```

## disassembly

```asm
0x180009f90  mov     rcx, [rcx]
0x180009f93  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
