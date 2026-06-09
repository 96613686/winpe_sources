# memset_0

- ea: `0x18000dce6`
- end: `0x18000dcec`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800028fc`
- `0x18000be1c`
- `0x18000c580`
- `0x18000cbb0`
- `0x18000d990`

## import_xrefs

- `msvcrt!memset` at `0x18000dce6`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18000dce6  jmp     cs:__imp_memset
```
