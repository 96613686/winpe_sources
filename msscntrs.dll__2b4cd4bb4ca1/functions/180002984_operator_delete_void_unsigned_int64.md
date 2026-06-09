# operator delete(void *,unsigned __int64)

- ea: `0x180002984`
- end: `0x180002989`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800046fc`
- `0x180004764`
- `0x180004fb0`
- `0x180004ff0`
- `0x180005030`
- `0x180005070`
- `0x18000b0cc`
- `0x18000b438`
- `0x18000b4d8`
- `0x18000b7f0`
- `0x18000b870`
- `0x18000b8f0`
- `0x18000b940`
- `0x18000b980`
- `0x18000b9c0`
- `0x18000ba20`
- `0x18000ba7c`
- `0x18000c4b4`
- `0x180012480`

## callees

- `0x180002484`

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
0x180002984  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
