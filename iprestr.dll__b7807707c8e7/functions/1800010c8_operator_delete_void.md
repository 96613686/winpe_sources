# operator delete(void *)

- ea: `0x1800010c8`
- end: `0x1800010cd`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001aa0`
- `0x180002e10`
- `0x180002e78`
- `0x180002f00`
- `0x180004110`
- `0x180004290`
- `0x180004910`

## callees

- `0x180001661`

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
0x1800010c8  jmp     free_0
```
