# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800146e4`
- end: `0x1800146e9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `47`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003730`
- `0x180003b10`
- `0x180004b00`
- `0x1800060a0`
- `0x1800070a0`
- `0x180007e80`
- `0x18000a760`
- `0x18000b560`
- `0x18000c600`
- `0x18000d510`
- `0x180010ae8`
- `0x18001106c`
- `0x180011980`
- `0x180011ec4`
- `0x1800126d0`
- `0x180012710`
- `0x180014354`
- `0x180015d80`
- `0x180018600`
- `0x180018b70`
- `0x180018bc0`
- `0x180018c00`
- `0x180018c40`
- `0x180018c80`
- `0x180018cc0`
- `0x18001e6c4`
- `0x18001e7d0`
- `0x18001e810`
- `0x18001e850`
- `0x18001e890`
- `0x18001e8d0`
- `0x18001e90c`
- `0x1800216cc`
- `0x180022340`
- `0x180022380`
- `0x180022980`
- `0x1800229c0`
- `0x1800258d0`
- `0x180025e40`
- `0x1800278c0`
- `0x1800289d0`
- `0x18002bd20`
- `0x18002bee8`
- `0x18002e194`
- `0x18002e9ab`
- `0x18002f122`
- `0x18002fb2e`

## callees

- `0x180014ca4`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1800146e4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
