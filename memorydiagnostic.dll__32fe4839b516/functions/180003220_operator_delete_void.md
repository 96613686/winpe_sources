# operator delete(void *)

- ea: `0x180003220`
- end: `0x180003225`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002b0c`
- `0x180002b20`

## callees

- `0x180003344`

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
0x180003220  jmp     free
```
