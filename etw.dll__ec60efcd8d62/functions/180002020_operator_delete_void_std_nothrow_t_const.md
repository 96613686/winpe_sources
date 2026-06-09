# operator delete(void *,std::nothrow_t const &)

- ea: `0x180002020`
- end: `0x180002025`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000293c`
- `0x180003fa8`
- `0x18000416c`
- `0x180004da0`
- `0x1800061f4`
- `0x180006348`
- `0x180006480`
- `0x180007500`
- `0x180008f30`
- `0x1800099c0`
- `0x18000a300`
- `0x18000c4a0`
- `0x18000cca0`
- `0x18000d780`
- `0x18000ece4`
- `0x18000f90c`
- `0x18000ff6c`
- `0x180010634`
- `0x180010db8`
- `0x180015b60`

## callees

- `0x180002014`

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
0x180002020  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
