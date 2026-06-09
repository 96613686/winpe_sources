# memcpy_0

- ea: `0x180021ffc`
- end: `0x180022002`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x1800037bc`
- `0x180005c80`
- `0x180005d4c`
- `0x180005e94`
- `0x180006ec4`
- `0x1800177e4`
- `0x180017904`
- `0x180017a34`
- `0x18001a6ac`
- `0x18001cfb8`
- `0x18001d530`
- `0x18001e018`
- `0x18001fb4c`
- `0x18001fc48`
- `0x18001fd80`
- `0x18001fedc`
- `0x1800210d0`
- `0x180021680`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x180021ffc`

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
0x180021ffc  jmp     cs:__imp_memcpy
```
