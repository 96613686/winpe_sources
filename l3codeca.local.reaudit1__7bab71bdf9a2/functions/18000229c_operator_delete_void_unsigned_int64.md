# operator delete(void *,unsigned __int64)

- ea: `0x18000229c`
- end: `0x1800022a1`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800036c0`
- `0x180003980`
- `0x180003c00`
- `0x180003c90`
- `0x1800044e0`
- `0x180004570`
- `0x180005420`
- `0x180005700`
- `0x18000b830`
- `0x18000f5c0`
- `0x180010de0`

## callees

- `0x1800022a8`

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
0x18000229c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
