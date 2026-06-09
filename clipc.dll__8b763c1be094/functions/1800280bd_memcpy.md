# memcpy

- ea: `0x1800280bd`
- end: `0x1800280c3`
- name: `memcpy`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b5c`
- `0x1800047f0`
- `0x180004d2c`
- `0x180006640`
- `0x180006ad0`
- `0x180006f34`
- `0x180007054`
- `0x18000717c`
- `0x180007410`
- `0x18001003c`
- `0x18001a1f0`
- `0x18001a478`
- `0x18001a8f0`
- `0x18001aa58`
- `0x18001ab44`
- `0x18001aca8`
- `0x18001ae1c`
- `0x18001bca0`
- `0x18001f910`
- `0x1800251f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x1800280bd`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy(void *a1, const void *Src, size_t Size)
{
  return __imp_memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x1800280bd  jmp     cs:__imp_memcpy
```
