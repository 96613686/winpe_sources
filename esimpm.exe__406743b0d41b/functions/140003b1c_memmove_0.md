# memmove_0

- ea: `0x140003b1c`
- end: `0x140003b22`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x140004350`
- `0x140007360`
- `0x140008ef0`
- `0x14000ae00`
- `0x14000bc80`
- `0x14000bde0`
- `0x140011968`
- `0x1400167fc`
- `0x140019e8c`
- `0x14001db40`
- `0x14001df48`
- `0x14001fa90`
- `0x140020860`
- `0x1400240fc`
- `0x140026334`
- `0x140026604`
- `0x140026b74`
- `0x140029040`
- `0x14002a4b8`
- `0x14002f214`
- `0x14003154c`
- `0x140032434`
- `0x14003a530`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x140003b1c`

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
0x140003b1c  jmp     cs:__imp_memmove
```
