# operator delete(void *)

- ea: `0x1800025f0`
- end: `0x1800025f5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003194`
- `0x1800031f0`
- `0x180003220`
- `0x180003290`
- `0x1800032c0`
- `0x180003510`
- `0x1800049a0`
- `0x180004c90`

## callees

- `0x180002b8d`

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
0x1800025f0  jmp     free_0
```
