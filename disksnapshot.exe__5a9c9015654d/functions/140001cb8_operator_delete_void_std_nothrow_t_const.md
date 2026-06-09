# operator delete(void *,std::nothrow_t const &)

- ea: `0x140001cb8`
- end: `0x140001cbd`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `35`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002d90`
- `0x140002fb8`
- `0x140003040`
- `0x140004dc8`
- `0x140004f34`
- `0x140004f90`
- `0x140004fec`
- `0x1400052b0`
- `0x1400055f4`
- `0x140005618`
- `0x14000563c`
- `0x140005660`
- `0x140005684`
- `0x1400056f4`
- `0x14000574c`
- `0x1400057a4`
- `0x1400057fc`
- `0x1400059b4`
- `0x140005bd0`
- `0x140005e10`
- `0x140006424`
- `0x140006c30`
- `0x1400082d0`
- `0x140008a38`
- `0x14000ae5c`
- `0x14000afe8`
- `0x14000b144`
- `0x14000c310`
- `0x14000c78a`
- `0x14000c7ec`
- `0x14000c811`
- `0x14000c8b9`
- `0x14000c94d`
- `0x14000c987`
- `0x14000c9be`

## callees

- `0x1400025f8`

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
0x140001cb8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
