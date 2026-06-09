# operator delete(void *)

- ea: `0x180001644`
- end: `0x180001649`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001a30`
- `0x180001a40`

## callees

- `0x180001fd2`

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
0x180001644  jmp     free
```
