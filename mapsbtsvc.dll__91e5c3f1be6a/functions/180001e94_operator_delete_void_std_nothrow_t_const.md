# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001e94`
- end: `0x180001e99`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003c34`
- `0x18000b3a4`
- `0x180014430`

## callees

- `0x180001e54`

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
0x180001e94  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
