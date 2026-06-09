# memmove_0

- ea: `0x1800022da`
- end: `0x1800022e0`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x180002844`
- `0x180004c34`
- `0x18000aa88`
- `0x180019270`
- `0x1800195ec`
- `0x18001d430`
- `0x18001df70`
- `0x18001e148`
- `0x18001e1c8`
- `0x18001e440`
- `0x18001e564`
- `0x18001e678`
- `0x18001ea94`
- `0x1800201e0`
- `0x180020368`
- `0x180020a84`
- `0x180020cc0`
- `0x180021144`
- `0x1800211e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800022da`

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
0x1800022da  jmp     cs:__imp_memmove
```
