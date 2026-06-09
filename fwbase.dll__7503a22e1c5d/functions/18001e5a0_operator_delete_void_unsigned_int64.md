# operator delete(void *,unsigned __int64)

- ea: `0x18001e5a0`
- end: `0x18001e5a5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180022b60`
- `0x180022ba0`
- `0x180022be0`
- `0x180022cd0`

## callees

- `0x18001e1b4`

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
0x18001e5a0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
