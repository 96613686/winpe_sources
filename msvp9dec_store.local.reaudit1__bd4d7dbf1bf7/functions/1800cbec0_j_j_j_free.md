# j_j_j_free

- ea: `0x1800cbec0`
- end: `0x1800cbec5`
- name: `j_j_j_free`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x180005eb0`
- `0x180006e40`
- `0x180018290`
- `0x18001b920`
- `0x18001c4a0`
- `0x180021a10`
- `0x180022a60`
- `0x180023b40`
- `0x180025848`
- `0x180025968`
- `0x180026de0`
- `0x1800274c4`
- `0x18002774c`
- `0x1800281a0`
- `0x18002afd0`
- `0x180137e80`
- `0x180137f10`
- `0x1801380a6`
- `0x18013810f`

## callees

- `0x1800cbe04`

## pseudocode

```c
// attributes: thunk
void __cdecl j_j_j_free(void *Block)
{
  j_j_free(Block);
}

```

## disassembly

```asm
0x1800cbec0  jmp     j_j_free
```
