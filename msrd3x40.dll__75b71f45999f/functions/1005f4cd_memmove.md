# _memmove

- ea: `0x1005f4cd`
- end: `0x1005f4d3`
- name: `_memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1000bac0`
- `0x10025300`
- `0x10032460`
- `0x10043660`
- `0x10043c60`
- `0x10052790`
- `0x10055260`
- `0x10055bc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1005f4cd`

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
0x1005f4cd  jmp     ds:__imp__memmove
```
