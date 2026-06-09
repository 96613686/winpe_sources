# operator delete(void *)

- ea: `0x18001e1b4`
- end: `0x18001e1b9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001e5a0`
- `0x18001e5b0`

## callees

- `0x18001eb24`

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
0x18001e1b4  jmp     free
```
