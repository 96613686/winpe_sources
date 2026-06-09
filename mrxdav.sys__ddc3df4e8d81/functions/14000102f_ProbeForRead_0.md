# ProbeForRead_0

- ea: `0x14000102f`
- end: `0x140001036`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001044`
- `0x14000f008`
- `0x14000f06c`
- `0x14000f0cc`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000102f`

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
0x14000102f  jmp     cs:__imp_ProbeForRead
```
