# operator delete(void *)

- ea: `0x180001cd4`
- end: `0x180001cd9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001d14`
- `0x180001d20`

## callees

- `0x1800026a4`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180001cd4  jmp     free
```
