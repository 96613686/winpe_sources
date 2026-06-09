# operator delete(void *,unsigned __int64)

- ea: `0x180001624`
- end: `0x180001629`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800020a4`
- `0x1800021e4`
- `0x1800027e4`
- `0x180002850`
- `0x180005e60`
- `0x1800064c0`
- `0x180007434`
- `0x180007450`

## callees

- `0x180001618`

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
0x180001624  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
