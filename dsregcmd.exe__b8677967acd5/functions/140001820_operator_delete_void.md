# operator delete(void *)

- ea: `0x140001820`
- end: `0x140001825`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400028ac`
- `0x1400028e0`
- `0x140003bc0`
- `0x140008c34`
- `0x140008e50`
- `0x140008f78`
- `0x140018d98`
- `0x140018ed8`
- `0x1400193b4`
- `0x14001b8d4`
- `0x14002bc20`
- `0x14002bc50`
- `0x14002c633`

## callees

- `0x1400027c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x140001820  jmp     free
```
