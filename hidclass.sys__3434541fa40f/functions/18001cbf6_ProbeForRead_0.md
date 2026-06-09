# ProbeForRead_0

- ea: `0x18001cbf6`
- end: `0x18001cbfd`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18003802c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x18001cbf6`

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
0x18001cbf6  jmp     cs:__imp_ProbeForRead
```
