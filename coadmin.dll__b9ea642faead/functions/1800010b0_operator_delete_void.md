# operator delete[](void *)

- ea: `0x1800010b0`
- end: `0x1800010b5`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800063c0`
- `0x1800068d4`
- `0x180007c20`
- `0x180009b4c`
- `0x18000c588`
- `0x18000c5e8`
- `0x18000ca70`
- `0x18000cc5c`
- `0x18000cfd4`
- `0x18000d6a4`

## callees

- `0x1800010a4`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x1800010b0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
