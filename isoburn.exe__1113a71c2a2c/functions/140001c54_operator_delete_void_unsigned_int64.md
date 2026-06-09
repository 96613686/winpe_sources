# operator delete(void *,unsigned __int64)

- ea: `0x140001c54`
- end: `0x140001c59`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001fc4`
- `0x140003720`
- `0x140003954`
- `0x140003d50`
- `0x140003d90`
- `0x140003e10`
- `0x140003e70`
- `0x14000a710`
- `0x14000c3c0`
- `0x14000c410`
- `0x14000c44c`
- `0x14000cc84`
- `0x14000e130`

## callees

- `0x140001bfc`

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
0x140001c54  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
