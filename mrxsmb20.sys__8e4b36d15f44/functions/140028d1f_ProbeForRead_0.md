# ProbeForRead_0

- ea: `0x140028d1f`
- end: `0x140028d26`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140050280`
- `0x1400502e4`
- `0x14005032c`
- `0x140050370`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140028d1f`

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
0x140028d1f  jmp     cs:__imp_ProbeForRead
```
