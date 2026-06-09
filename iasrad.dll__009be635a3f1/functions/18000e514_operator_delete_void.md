# operator delete(void *)

- ea: `0x18000e514`
- end: `0x18000e51b`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001530`
- `0x180001bc0`
- `0x180001cec`
- `0x18002e7bd`
- `0x18002e8d3`
- `0x18002f1ac`
- `0x18002f411`
- `0x18002f46b`
- `0x18002f8a1`
- `0x18002f8c5`
- `0x18002faaf`

## import_xrefs

- `msvcrt!free` at `0x18000e514`

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
0x18000e514  jmp     cs:__imp_free
```
