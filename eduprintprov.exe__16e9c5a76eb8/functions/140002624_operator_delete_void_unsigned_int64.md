# operator delete(void *,unsigned __int64)

- ea: `0x140002624`
- end: `0x140002629`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `32`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000452c`
- `0x14000466c`
- `0x140004e30`
- `0x140004f24`
- `0x140005630`
- `0x140005670`
- `0x1400056b0`
- `0x1400056f0`
- `0x140005f00`
- `0x14000c318`
- `0x14000c540`
- `0x14000ca68`
- `0x14000ce70`
- `0x14000ced0`
- `0x14000d2a4`
- `0x14000e150`
- `0x14000e7ec`
- `0x14000e810`
- `0x14000e870`
- `0x14000eb20`
- `0x14000eb5c`
- `0x14000ebec`
- `0x14000f330`
- `0x14001011c`
- `0x1400101bc`
- `0x140010300`
- `0x140010f8c`
- `0x140011344`
- `0x1400118a4`
- `0x1400119c0`
- `0x140012f90`
- `0x1400136d9`

## callees

- `0x140002f54`

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
0x140002624  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
