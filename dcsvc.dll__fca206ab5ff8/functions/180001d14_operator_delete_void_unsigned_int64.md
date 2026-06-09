# operator delete(void *,unsigned __int64)

- ea: `0x180001d14`
- end: `0x180001d19`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004310`
- `0x180004350`
- `0x180004390`
- `0x1800043d0`
- `0x18000ed9c`
- `0x18000f4cc`
- `0x18000f528`
- `0x18000f634`
- `0x18000f9a8`
- `0x18000f9cc`
- `0x18000f9f0`
- `0x18000fa4c`
- `0x18000fabc`
- `0x18000fb28`
- `0x18000fb94`
- `0x18000fc84`
- `0x18000fcfc`
- `0x180010af0`
- `0x180010c64`
- `0x180010ea0`

## callees

- `0x180001cd4`

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
0x180001d14  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
