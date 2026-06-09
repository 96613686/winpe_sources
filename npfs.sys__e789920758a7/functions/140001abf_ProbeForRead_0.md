# ProbeForRead_0

- ea: `0x140001abf`
- end: `0x140001ac6`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001ad4`
- `0x14000b054`
- `0x14000b0b8`
- `0x14000b118`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140001abf`

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
0x140001abf  jmp     cs:__imp_ProbeForRead
```
