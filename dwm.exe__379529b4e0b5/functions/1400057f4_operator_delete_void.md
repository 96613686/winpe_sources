# operator delete(void *)

- ea: `0x1400057f4`
- end: `0x1400057f9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400057c4`
- `0x140005f30`
- `0x140006000`
- `0x14000c654`

## callees

- `0x140006164`

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
0x1400057f4  jmp     free
```
