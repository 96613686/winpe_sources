# ProbeForRead_0

- ea: `0x180007a4f`
- end: `0x180007a56`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180007a64`
- `0x18001f520`
- `0x18001f584`
- `0x18001f5c0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x180007a4f`

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
0x180007a4f  jmp     cs:__imp_ProbeForRead
```
