# ProbeForRead_0

- ea: `0x14000113f`
- end: `0x140001146`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140001154`
- `0x1400080c4`
- `0x140008128`
- `0x140008164`
- `0x1400081a0`
- `0x1400081e8`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000113f`

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
0x14000113f  jmp     cs:__imp_ProbeForRead
```
