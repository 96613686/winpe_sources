# memmove_0

- ea: `0x18004d8f0`
- end: `0x18004d8f6`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `34`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f190`
- `0x18001ca04`
- `0x18001ca80`
- `0x1800226a0`
- `0x180027c30`
- `0x180027d5c`
- `0x180031348`
- `0x180033f94`
- `0x180034618`
- `0x1800376ec`
- `0x1800388e8`
- `0x18003d470`
- `0x180042174`
- `0x1800456ac`
- `0x180046b5c`
- `0x18004dea8`
- `0x180050a18`
- `0x180050a54`
- `0x180055ba8`
- `0x180056cd8`
- `0x180063ac4`
- `0x180065080`
- `0x180065518`
- `0x1800656a0`
- `0x1800664dc`
- `0x1800700d4`
- `0x180070ed0`
- `0x1800711d0`
- `0x180071370`
- `0x18007e9b4`
- `0x1800814d4`
- `0x180087038`
- `0x1800870b0`
- `0x180087114`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18004d8f0`

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
0x18004d8f0  jmp     cs:__imp_memmove
```
