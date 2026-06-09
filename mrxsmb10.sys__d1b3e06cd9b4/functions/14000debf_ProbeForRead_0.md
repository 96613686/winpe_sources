# ProbeForRead_0

- ea: `0x14000debf`
- end: `0x14000dec6`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140028538`
- `0x14002859c`
- `0x1400285e4`
- `0x140028628`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000debf`

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
0x14000debf  jmp     cs:__imp_ProbeForRead
```
