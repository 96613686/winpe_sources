# memcpy_0

- ea: `0x18000bfe6`
- end: `0x18000bfec`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005620`
- `0x180007200`
- `0x1800086c0`
- `0x1800098ac`
- `0x180009ad8`
- `0x18000a724`
- `0x18000b9c0`

## import_xrefs

- `msvcrt!memcpy` at `0x18000bfe6`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy_0(void *a1, const void *Src, size_t Size)
{
  return memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x18000bfe6  jmp     cs:__imp_memcpy
```
