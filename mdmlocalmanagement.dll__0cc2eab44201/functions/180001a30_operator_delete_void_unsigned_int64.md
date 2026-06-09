# operator delete(void *,unsigned __int64)

- ea: `0x180001a30`
- end: `0x180001a35`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002ed0`
- `0x180002f10`

## callees

- `0x180001644`

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
0x180001a30  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
