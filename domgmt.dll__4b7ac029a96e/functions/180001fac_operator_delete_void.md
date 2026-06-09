# operator delete(void *)

- ea: `0x180001fac`
- end: `0x180001fb1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001f70`
- `0x180001f80`

## callees

- `0x180002954`

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
0x180001fac  jmp     free
```
