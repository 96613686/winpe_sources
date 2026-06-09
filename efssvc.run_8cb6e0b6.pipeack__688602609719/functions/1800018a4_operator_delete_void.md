# operator delete(void *)

- ea: `0x1800018a4`
- end: `0x1800018a9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002cd4`
- `0x1800099b0`

## callees

- `0x180001d8e`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x1800018a4  jmp     free_0
```
