# operator delete(void *,unsigned __int64)

- ea: `0x180001bb4`
- end: `0x180001bb9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `72`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004274`
- `0x180004470`
- `0x1800044a0`
- `0x1800044e0`
- `0x1800081e0`
- `0x180008280`
- `0x180008500`
- `0x1800087d0`
- `0x180008be8`
- `0x1800091c0`
- `0x180009300`
- `0x1800096a0`
- `0x1800096d0`
- `0x180009870`
- `0x1800098b0`
- `0x180009910`
- `0x180009950`
- `0x180009990`
- `0x180009e00`
- `0x180009f30`
- `0x18000a960`
- `0x18000a9c0`
- `0x18000af50`
- `0x18000b854`
- `0x18000ba8c`
- `0x18000bcf8`
- `0x18000bd1c`
- `0x18000bd7c`
- `0x18000bdec`
- `0x18000be5c`
- `0x18000bedc`
- `0x18000bf50`
- `0x18000c1d8`
- `0x18000c404`
- `0x18000c45c`
- `0x18000c4c8`
- `0x18000c574`
- `0x18000c740`
- `0x18000c890`
- `0x18000e670`
- `0x18000e8dc`
- `0x18000e944`
- `0x18000e9a0`
- `0x18000eb84`
- `0x18000eba8`
- `0x18000ebcc`
- `0x18000ebf0`
- `0x18000ec58`
- `0x18000ecc8`
- `0x18000ed3c`

## callees

- `0x180001ba8`

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
0x180001bb4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
