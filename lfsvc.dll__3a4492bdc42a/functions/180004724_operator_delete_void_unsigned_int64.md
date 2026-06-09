# operator delete(void *,unsigned __int64)

- ea: `0x180004724`
- end: `0x180004729`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800058c8`
- `0x180006118`
- `0x180006200`
- `0x180006240`
- `0x180006280`
- `0x1800062c0`

## callees

- `0x1800042f4`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180004724  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
