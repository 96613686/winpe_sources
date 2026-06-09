# ProbeForRead_0

- ea: `0x140002546`
- end: `0x14000254d`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140014b8c`
- `0x140014bf0`
- `0x140014c2c`
- `0x140014c8c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140002546`

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
0x140002546  jmp     cs:__imp_ProbeForRead
```
