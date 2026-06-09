# ProbeForRead_0

- ea: `0x140003051`
- end: `0x140003058`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140003064`
- `0x140011bfc`
- `0x140011c60`
- `0x140011c9c`
- `0x140011ce4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140003051`

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
0x140003051  jmp     cs:__imp_ProbeForRead
```
