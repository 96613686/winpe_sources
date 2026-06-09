# operator delete(void *)

- ea: `0x180014114`
- end: `0x180014119`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180014544`
- `0x180014550`

## callees

- `0x180014f9c`

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
0x180014114  jmp     free
```
