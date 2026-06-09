# operator delete(void *,unsigned __int64)

- ea: `0x1800031d4`
- end: `0x1800031d9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `18`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005160`
- `0x1800051a0`
- `0x1800098a8`
- `0x180009a2c`
- `0x180009e58`
- `0x180009ec8`
- `0x180009ff8`
- `0x18000a064`
- `0x18000a720`
- `0x18000a830`
- `0x18000a870`
- `0x18001cf70`
- `0x18001e7b4`
- `0x180020530`
- `0x180020a80`
- `0x180020c74`
- `0x180020df4`
- `0x180023271`

## callees

- `0x180003bc8`

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
0x1800031d4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
