# memmove_0

- ea: `0x1800139ec`
- end: `0x1800139f2`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180009948`
- `0x180009b60`
- `0x18000a10c`
- `0x180010448`
- `0x180010594`
- `0x180012d30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800139ec`

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
0x1800139ec  jmp     cs:__imp_memmove
```
