# memcpy_0

- ea: `0x18001d0ac`
- end: `0x18001d0b2`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180004dd0`
- `0x1800064e0`
- `0x1800078d0`
- `0x180008e74`
- `0x1800092f8`
- `0x1800097d4`
- `0x18000bb90`
- `0x18000dfe0`
- `0x18000f100`
- `0x180011594`
- `0x180019bec`
- `0x18001ac80`
- `0x18001af80`
- `0x18001b91c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18001d0ac`

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
0x18001d0ac  jmp     cs:__imp_memcpy
```
