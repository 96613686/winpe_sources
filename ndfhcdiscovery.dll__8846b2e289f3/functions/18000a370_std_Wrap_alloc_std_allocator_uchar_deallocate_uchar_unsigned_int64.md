# std::_Wrap_alloc<std::allocator<uchar>>::deallocate(uchar *,unsigned __int64)

- ea: `0x18000a370`
- end: `0x18000a37a`
- name: `?deallocate@?$_Wrap_alloc@V?$allocator@E@std@@@std@@QEAAXPEAE_K@Z`
- size: `10`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000bf6c`
- `0x180013b3e`
- `0x180013e87`
- `0x180013fb9`
- `0x18001431a`
- `0x180014340`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a373`

## pseudocode

```c
void __fastcall std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(__int64 a1, void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x18000a370  mov     rcx, rdx
0x18000a373  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
