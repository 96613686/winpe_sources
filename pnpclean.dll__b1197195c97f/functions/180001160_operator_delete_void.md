# operator delete(void *)

- ea: `0x180001160`
- end: `0x180001165`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800021a8`
- `0x180002260`
- `0x180002ce0`
- `0x180002e60`
- `0x180003790`
- `0x1800038b0`

## callees

- `0x180001921`

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
0x180001160  jmp     free_0
```
