# operator delete(void *,unsigned __int64)

- ea: `0x1800030a4`
- end: `0x1800030a9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800039e0`
- `0x180003a10`
- `0x180003a50`

## callees

- `0x1800028b0`

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
0x1800030a4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
