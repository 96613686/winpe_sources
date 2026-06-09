# operator delete(void *)

- ea: `0x180003b04`
- end: `0x180003b09`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003b10`
- `0x180003b20`
- `0x180023910`
- `0x180023940`
- `0x18002397c`
- `0x180023fd0`
- `0x180026da4`
- `0x180027710`
- `0x1800280e0`

## callees

- `0x180004130`

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
0x180003b04  jmp     free
```
