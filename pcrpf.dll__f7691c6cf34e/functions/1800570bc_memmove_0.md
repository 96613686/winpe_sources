# memmove_0

- ea: `0x1800570bc`
- end: `0x1800570c2`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180008c24`
- `0x18000f8cc`
- `0x18003b044`
- `0x180042f7c`
- `0x180043764`
- `0x18005087c`
- `0x180051ca0`
- `0x180054460`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800570bc`

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
0x1800570bc  jmp     cs:__imp_memmove
```
