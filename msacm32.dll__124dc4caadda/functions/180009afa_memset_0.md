# memset_0

- ea: `0x180009afa`
- end: `0x180009b00`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `28`
- callee_count: `0`
- tags: ``

## callers

- `0x180002540`
- `0x180002e70`
- `0x180004470`
- `0x1800045b0`
- `0x180005990`
- `0x180005f60`
- `0x180006f00`
- `0x180007790`
- `0x180008160`
- `0x18000ae04`
- `0x18000b7d0`
- `0x18000b8d0`
- `0x18000bba0`
- `0x18000bca0`
- `0x18000c040`
- `0x18000c350`
- `0x18000cdf0`
- `0x18000cef0`
- `0x18000cfe0`
- `0x18000d6c0`
- `0x18000e608`
- `0x18000e7d4`
- `0x18000ec20`
- `0x180010548`
- `0x180011018`
- `0x1800116d0`
- `0x1800119c0`
- `0x180011d40`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180009afa`

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
0x180009afa  jmp     cs:__imp_memset
```
