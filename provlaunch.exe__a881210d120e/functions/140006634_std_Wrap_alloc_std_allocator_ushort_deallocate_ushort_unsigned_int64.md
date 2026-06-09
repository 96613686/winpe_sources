# std::_Wrap_alloc<std::allocator<ushort>>::deallocate(ushort *,unsigned __int64)

- ea: `0x140006634`
- end: `0x14000663e`
- name: `?deallocate@?$_Wrap_alloc@V?$allocator@G@std@@@std@@QEAAXPEAG_K@Z`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x14000aa56`
- `0x14000ab44`
- `0x14000ab6a`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140006637`

## pseudocode

```c
void __fastcall std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(__int64 a1, void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x140006634  mov     rcx, rdx
0x140006637  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
