# ProbeForRead_0

- ea: `0x140001044`
- end: `0x14000104b`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010f4`
- `0x14000b008`
- `0x14000b06c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140001044`

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
0x140001044  jmp     cs:__imp_ProbeForRead
```
