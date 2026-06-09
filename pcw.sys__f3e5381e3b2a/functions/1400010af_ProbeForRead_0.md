# ProbeForRead_0

- ea: `0x1400010af`
- end: `0x1400010b6`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010c4`
- `0x140008008`
- `0x14000806c`
- `0x1400080b4`
- `0x1400080fc`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400010af`

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
0x1400010af  jmp     cs:__imp_ProbeForRead
```
