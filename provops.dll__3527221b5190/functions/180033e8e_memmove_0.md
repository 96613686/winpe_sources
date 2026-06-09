# memmove_0

- ea: `0x180033e8e`
- end: `0x180033e94`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b980`
- `0x18000bb14`
- `0x18000cbe4`
- `0x18000e850`
- `0x18000e8f4`
- `0x18001f2c4`
- `0x180020260`
- `0x1800202e4`
- `0x180020384`
- `0x18002144c`
- `0x180021740`
- `0x18002187c`
- `0x180021be4`
- `0x180022da4`
- `0x1800260e4`
- `0x1800278d0`
- `0x180027a30`
- `0x18002af7c`
- `0x18002f5dc`
- `0x18002fb20`
- `0x180032018`

## import_xrefs

- `msvcrt!memmove` at `0x180033e8e`

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
0x180033e8e  jmp     cs:__imp_memmove
```
