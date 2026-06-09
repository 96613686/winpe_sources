# operator delete(void *)

- ea: `0x140001a20`
- end: `0x140001a25`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001484`
- `0x140001490`

## callees

- `0x140001e1a`

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
0x140001a20  jmp     free
```
