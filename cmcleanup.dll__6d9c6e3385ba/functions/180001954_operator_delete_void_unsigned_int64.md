# operator delete(void *,unsigned __int64)

- ea: `0x180001954`
- end: `0x180001959`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003330`
- `0x180003370`
- `0x1800033d0`
- `0x180003410`
- `0x180003490`
- `0x1800034d0`

## callees

- `0x180001948`

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
0x180001954  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
