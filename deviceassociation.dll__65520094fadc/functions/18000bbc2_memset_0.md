# memset_0

- ea: `0x18000bbc2`
- end: `0x18000bbc8`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x180002168`
- `0x180002284`
- `0x180002a54`
- `0x180002ca4`
- `0x1800033d0`
- `0x180003638`
- `0x1800038d4`
- `0x18000410c`
- `0x1800044b0`
- `0x1800052e4`
- `0x180007588`
- `0x180008280`
- `0x1800085a8`
- `0x180008b40`
- `0x180009a00`
- `0x180009aa0`
- `0x18000a430`
- `0x18000ae00`

## import_xrefs

- `msvcrt!memset` at `0x18000bbc2`

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
0x18000bbc2  jmp     cs:__imp_memset
```
