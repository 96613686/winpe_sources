# _memmove

- ea: `0x1003bd04`
- end: `0x1003bd0a`
- name: `_memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x10008280`
- `0x10025317`
- `0x1002abaa`
- `0x1002ad94`
- `0x1002bf90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1003bd04`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return _memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x1003bd04  jmp     ds:__imp__memmove
```
