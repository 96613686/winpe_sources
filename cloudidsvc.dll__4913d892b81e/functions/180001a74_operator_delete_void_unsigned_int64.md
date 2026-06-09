# operator delete(void *,unsigned __int64)

- ea: `0x180001a74`
- end: `0x180001a79`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002e94`
- `0x1800031f4`
- `0x180004a20`
- `0x180004a60`
- `0x180004aa0`
- `0x180004ae0`
- `0x180004b20`
- `0x180004b60`
- `0x180004ba0`
- `0x180004be0`
- `0x180004c20`
- `0x180004c5c`
- `0x180004c98`
- `0x180004ce0`
- `0x180007b9c`
- `0x180009014`
- `0x18000ac74`
- `0x18000acb0`
- `0x18000acf0`
- `0x18000ad30`
- `0x18000ad70`
- `0x18000df90`
- `0x180010d9c`

## callees

- `0x180002070`

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
0x180001a74  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
