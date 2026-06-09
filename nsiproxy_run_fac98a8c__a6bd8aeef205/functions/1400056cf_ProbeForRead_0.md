# ProbeForRead_0

- ea: `0x1400056cf`
- end: `0x1400056d6`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400056e8`
- `0x14000d08c`
- `0x14000d0f0`
- `0x14000d138`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400056cf`

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
0x1400056cf  jmp     cs:__imp_ProbeForRead
```
