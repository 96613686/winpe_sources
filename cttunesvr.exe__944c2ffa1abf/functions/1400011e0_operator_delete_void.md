# operator delete(void *)

- ea: `0x1400011e0`
- end: `0x1400011e5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400011ec`
- `0x140002210`
- `0x140002270`
- `0x1400022d0`
- `0x140002ed0`
- `0x140004bb0`
- `0x140005320`
- `0x1400060fc`

## callees

- `0x14000162e`

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
0x1400011e0  jmp     free_0
```
