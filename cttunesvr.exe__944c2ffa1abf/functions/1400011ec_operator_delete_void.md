# operator delete[](void *)

- ea: `0x1400011ec`
- end: `0x1400011f1`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002308`
- `0x140002c40`
- `0x140002cc0`

## callees

- `0x1400011e0`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x1400011ec  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
