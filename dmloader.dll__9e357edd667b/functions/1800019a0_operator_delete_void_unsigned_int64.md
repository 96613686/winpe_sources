# operator delete(void *,unsigned __int64)

- ea: `0x1800019a0`
- end: `0x1800019a5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `29`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800030a0`
- `0x1800030e0`
- `0x180003bd0`
- `0x180006740`
- `0x180006780`
- `0x180007fcc`
- `0x180008e90`
- `0x1800094c0`
- `0x1800096c0`
- `0x18000a10c`
- `0x18000a178`
- `0x18000a310`
- `0x18000a484`
- `0x18000a810`
- `0x18000aa70`
- `0x18000b9b0`
- `0x18000c018`
- `0x18000c14c`
- `0x18000c290`
- `0x18000c494`
- `0x18000c5d8`
- `0x18000db40`
- `0x18000dba0`
- `0x18000dc00`
- `0x18000dc50`
- `0x18000e038`
- `0x18000e0f0`
- `0x18000e9e4`
- `0x18000f640`

## callees

- `0x18000dfc4`

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
0x1800019a0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
