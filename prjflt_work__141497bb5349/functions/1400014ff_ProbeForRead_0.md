# ProbeForRead_0

- ea: `0x1400014ff`
- end: `0x140001506`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140001514`
- `0x140021008`
- `0x14002106c`
- `0x1400210a8`
- `0x140021108`
- `0x140021150`
- `0x140021198`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400014ff`

## pseudocode

```c
// attributes: thunk
void __stdcall ProbeForRead_0(volatile void *Address, SIZE_T Length, ULONG Alignment)
{
  ProbeForRead(Address, Length, Alignment);
}

```

## disassembly

```asm
0x1400014ff  jmp     cs:__imp_ProbeForRead
```
