# operator delete(void *,unsigned __int64)

- ea: `0x140001754`
- end: `0x140001759`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000311c`
- `0x1400032b8`
- `0x140003ac8`
- `0x140003ce0`
- `0x140003d20`

## callees

- `0x140001748`

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
0x140001754  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
