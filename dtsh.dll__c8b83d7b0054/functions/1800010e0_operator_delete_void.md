# operator delete(void *)

- ea: `0x1800010e0`
- end: `0x1800010e5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001d60`
- `0x180001f90`
- `0x180002440`
- `0x18000407c`
- `0x180004130`

## callees

- `0x18000161c`

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
0x1800010e0  jmp     free_0
```
