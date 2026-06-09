# operator delete(void *,std::nothrow_t const &)

- ea: `0x140003244`
- end: `0x140003249`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `141`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004180`
- `0x1400041b0`
- `0x1400043e0`
- `0x140004670`
- `0x140004ae0`
- `0x140005060`
- `0x1400052c0`
- `0x140005450`
- `0x1400055e0`
- `0x1400057b0`
- `0x140005960`
- `0x1400066e0`
- `0x140006ad0`
- `0x140006b20`
- `0x140006b60`
- `0x140006ba0`
- `0x140006be0`
- `0x140006c30`
- `0x140006c80`
- `0x140006db0`
- `0x140006e90`
- `0x140006f70`
- `0x140008020`
- `0x140008630`
- `0x140008af0`
- `0x140008ef0`
- `0x140009d30`
- `0x140009f80`
- `0x14000a7b0`
- `0x14000a940`
- `0x14000bf50`
- `0x14000c280`
- `0x14000c390`
- `0x14000ea50`
- `0x14000ea90`
- `0x14000ead0`
- `0x14000eb10`
- `0x140013df8`
- `0x1400148e8`
- `0x140014998`
- `0x1400149bc`
- `0x140014a38`
- `0x140014a74`
- `0x140014abc`
- `0x140014c00`
- `0x140014c30`
- `0x140014c70`
- `0x140014cb0`
- `0x140014cf0`
- `0x140014d30`

## callees

- `0x140003238`

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
0x140003244  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
