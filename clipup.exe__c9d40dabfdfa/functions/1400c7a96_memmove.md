# memmove

- ea: `0x1400c7a96`
- end: `0x1400c7a9c`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x14000f028`
- `0x1400239ec`
- `0x140023ab8`
- `0x140031d04`
- `0x140031e50`
- `0x140031f60`
- `0x140032090`
- `0x1400321a0`
- `0x1400322d4`
- `0x140032428`
- `0x140032528`
- `0x14003263c`
- `0x14003278c`
- `0x1400328a8`
- `0x1400371a0`
- `0x14003d9b8`
- `0x140091030`
- `0x14009b6f4`
- `0x14009b7dc`
- `0x14009b8c4`
- `0x14009b9fc`
- `0x14009bae4`
- `0x14009bbcc`
- `0x1400a41dc`
- `0x1400a5198`

## import_xrefs

- `msvcrt!memmove` at `0x1400c7a96`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x1400c7a96  jmp     cs:__imp_memmove
```
