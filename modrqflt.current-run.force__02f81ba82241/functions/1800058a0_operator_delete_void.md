# operator delete(void *)

- ea: `0x1800058a0`
- end: `0x1800058a5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800052e0`
- `0x180005520`
- `0x180006190`
- `0x180006ee0`
- `0x1800071d0`

## callees

- `0x180005d76`

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
0x1800058a0  jmp     free_0
```
