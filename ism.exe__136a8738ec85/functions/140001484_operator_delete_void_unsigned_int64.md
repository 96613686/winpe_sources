# operator delete(void *,unsigned __int64)

- ea: `0x140001484`
- end: `0x140001489`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002df0`
- `0x140002e30`

## callees

- `0x140001a20`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x140001484  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
