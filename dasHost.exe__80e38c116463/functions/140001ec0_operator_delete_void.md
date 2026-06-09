# operator delete(void *)

- ea: `0x140001ec0`
- end: `0x140001ec5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400018d4`
- `0x1400018e0`

## callees

- `0x140002094`

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
0x140001ec0  jmp     free
```
