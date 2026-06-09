# ProbeForRead_0

- ea: `0x140002b06`
- end: `0x140002b0d`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002aa0`
- `0x14000e008`
- `0x14000e06c`
- `0x14000e0a8`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140002b06`

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
0x140002b06  jmp     cs:__imp_ProbeForRead
```
