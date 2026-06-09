# operator delete(void *,unsigned __int64)

- ea: `0x18000a8f0`
- end: `0x18000a8f5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004880`
- `0x180006c1c`
- `0x18000c820`
- `0x18000c860`
- `0x18000c8a0`
- `0x18000c8e0`
- `0x18000f280`
- `0x180010ac0`
- `0x180012b60`
- `0x18001845c`
- `0x180018978`
- `0x180019320`
- `0x18001b214`
- `0x18001b8a0`
- `0x18001c284`
- `0x18001c50c`
- `0x18001c64c`
- `0x18001cc24`
- `0x18001d500`

## callees

- `0x18000ad9c`

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
0x18000a8f0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
