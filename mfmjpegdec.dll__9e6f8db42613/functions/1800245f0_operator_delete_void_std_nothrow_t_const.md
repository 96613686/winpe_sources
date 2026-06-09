# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800245f0`
- end: `0x1800245f5`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `62`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180024de0`
- `0x18003e3c0`
- `0x18003ef90`
- `0x18003fa30`
- `0x18003fa70`
- `0x18003fac0`
- `0x18003fb00`
- `0x18003fb40`
- `0x18003fb80`
- `0x18003fbc0`
- `0x18003fc00`
- `0x18003fc40`
- `0x18003fc80`
- `0x18003fcc0`
- `0x18003fd00`
- `0x18003fd40`
- `0x18003fd90`
- `0x180043114`
- `0x180043170`
- `0x1800431f4`
- `0x1800432d8`
- `0x180046670`
- `0x1800466b0`
- `0x180048ac4`
- `0x18004b1b0`
- `0x18004b30c`
- `0x18004b340`
- `0x18004b390`
- `0x18004bca8`
- `0x18004bd00`
- `0x18004c424`
- `0x18004ee50`
- `0x180052990`
- `0x180056b84`
- `0x180056bb0`
- `0x180058ea0`
- `0x180058eec`
- `0x180058f2c`
- `0x180058f58`
- `0x180058f94`
- `0x180058fc0`
- `0x180059120`
- `0x18005af70`
- `0x18005d000`
- `0x18005f660`
- `0x18005fc8c`
- `0x180060220`
- `0x180065690`
- `0x1800656d0`
- `0x1800658d0`

## callees

- `0x180024a7c`

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
0x1800245f0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
