# memmove_0

- ea: `0x18000ab22`
- end: `0x18000ab28`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180006600`
- `0x18000739c`
- `0x18000a77c`

## import_xrefs

- `msvcrt!memmove` at `0x18000ab22`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18000ab22  jmp     cs:__imp_memmove
```
