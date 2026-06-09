# operator delete(void *)

- ea: `0x140001054`
- end: `0x140001059`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001008`
- `0x140001aa4`
- `0x140001b98`
- `0x140001cb0`
- `0x140002820`
- `0x1400028d0`
- `0x140002960`
- `0x140003550`
- `0x140003674`
- `0x140003cd8`
- `0x140003fec`
- `0x1400048b0`

## callees

- `0x14000138e`

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
0x140001054  jmp     free_0
```
