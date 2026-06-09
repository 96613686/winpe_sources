# operator delete(void *)

- ea: `0x180001ff4`
- end: `0x180001ff9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002000`
- `0x180003640`
- `0x180003680`
- `0x1800036f0`
- `0x180003750`
- `0x180003790`

## callees

- `0x1800025ee`

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
0x180001ff4  jmp     free
```
