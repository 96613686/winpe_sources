# ProbeForRead_0

- ea: `0x140003046`
- end: `0x14000304d`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002fc0`
- `0x14000d0b0`
- `0x14000d114`
- `0x14000d174`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140003046`

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
0x140003046  jmp     cs:__imp_ProbeForRead
```
