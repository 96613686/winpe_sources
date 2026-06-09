# memset_0

- ea: `0x18000efc8`
- end: `0x18000efce`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x180001880`
- `0x180003680`
- `0x180003980`
- `0x180003b80`
- `0x180004230`
- `0x1800042f0`
- `0x180009ab0`
- `0x18000a1d0`
- `0x18000a900`
- `0x18000aa00`
- `0x18000aaf0`
- `0x18000ae90`
- `0x18000c6fc`
- `0x18000c780`
- `0x18000c7d4`
- `0x18000c890`
- `0x18000cd94`
- `0x18000d780`
- `0x18000f640`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x18000efc8`

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
0x18000efc8  jmp     cs:__imp_memset
```
