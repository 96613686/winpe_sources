# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001f1c`
- end: `0x180001f21`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001cee4`
- `0x18001cf31`
- `0x18001cf7e`
- `0x18001d02b`
- `0x18001d157`
- `0x18001d9a1`
- `0x18001deeb`

## callees

- `0x1800014d0`

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
0x180001f1c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
