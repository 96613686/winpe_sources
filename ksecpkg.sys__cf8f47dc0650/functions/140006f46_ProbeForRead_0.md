# ProbeForRead_0

- ea: `0x140006f46`
- end: `0x140006f4d`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140020110`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140006f46`

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
0x140006f46  jmp     cs:__imp_ProbeForRead
```
