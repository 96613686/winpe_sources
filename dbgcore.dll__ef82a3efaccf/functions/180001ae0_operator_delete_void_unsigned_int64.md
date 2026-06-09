# operator delete(void *,unsigned __int64)

- ea: `0x180001ae0`
- end: `0x180001ae5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `40`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004414`
- `0x18000449c`
- `0x18000450c`
- `0x180004b60`
- `0x180004ba0`
- `0x180004be0`
- `0x180004c20`
- `0x18000d6f4`
- `0x180011370`
- `0x18001d100`
- `0x18001d290`
- `0x18001d638`
- `0x18001d7e8`
- `0x18001d818`
- `0x18001d888`
- `0x18001d8f8`
- `0x18001da90`
- `0x18001e114`
- `0x18001e8f0`
- `0x18001efac`
- `0x18001f04c`
- `0x180027c08`
- `0x180027d98`
- `0x180027ee4`
- `0x180027f54`
- `0x180027fd0`
- `0x18002803c`
- `0x1800280a8`
- `0x18002849c`
- `0x180028b48`
- `0x1800290c8`
- `0x180029260`
- `0x1800292a0`
- `0x180029548`
- `0x18002a404`
- `0x18002aab4`
- `0x18002ab20`
- `0x18002ab50`
- `0x18002b4d2`
- `0x18002b5d2`

## callees

- `0x180001b80`

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
0x180001ae0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
