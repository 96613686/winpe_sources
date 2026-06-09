# operator delete(void *,unsigned __int64)

- ea: `0x140001794`
- end: `0x140001799`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003000`
- `0x140003040`
- `0x140005ac0`
- `0x140005b3c`
- `0x140005d10`
- `0x140005d80`
- `0x140005dc0`
- `0x140005e10`
- `0x140005e4c`
- `0x140006968`
- `0x140008c70`

## callees

- `0x1400014e8`

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
0x140001794  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
