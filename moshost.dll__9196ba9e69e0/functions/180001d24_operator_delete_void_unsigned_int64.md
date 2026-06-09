# operator delete(void *,unsigned __int64)

- ea: `0x180001d24`
- end: `0x180001d29`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007130`
- `0x180008938`
- `0x180009480`
- `0x180009790`
- `0x18000a2b8`
- `0x18000a348`
- `0x18000a3e4`
- `0x18000bd98`
- `0x18000bed8`
- `0x18000c1b8`

## callees

- `0x180001ce4`

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
0x180001d24  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
