# operator delete(void *)

- ea: `0x140001008`
- end: `0x14000100d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001870`
- `0x140001a80`
- `0x140001c68`
- `0x140001e74`
- `0x140001f30`
- `0x1400023ac`

## callees

- `0x140001366`

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
0x140001008  jmp     free_0
```
