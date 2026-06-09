# operator delete(void *,unsigned __int64)

- ea: `0x140001728`
- end: `0x14000172d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002aa0`
- `0x140002ad0`
- `0x140002b10`
- `0x140004c00`
- `0x140004c60`
- `0x140004cf0`

## callees

- `0x14000113c`

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
0x140001728  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
