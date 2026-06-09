# operator delete(void *,std::nothrow_t const &)

- ea: `0x180008080`
- end: `0x180008085`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003b40`
- `0x180004f00`
- `0x180007180`

## callees

- `0x180008050`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180008080  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
