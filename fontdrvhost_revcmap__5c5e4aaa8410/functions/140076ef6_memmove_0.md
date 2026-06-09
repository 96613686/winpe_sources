# memmove_0

- ea: `0x140076ef6`
- end: `0x140076efc`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `38`
- callee_count: `0`
- tags: ``

## callers

- `0x140031ed8`
- `0x140034688`
- `0x140035de4`
- `0x140038e74`
- `0x1400392dc`
- `0x14003bff8`
- `0x140044cfc`
- `0x14004d7e0`
- `0x140052a4c`
- `0x140059ca8`
- `0x14005a520`
- `0x14005c4c0`
- `0x14005ce34`
- `0x14005dfa8`
- `0x140063ff0`
- `0x140067d40`
- `0x14006b7ac`
- `0x140075778`
- `0x140076a50`
- `0x14007dce0`
- `0x14007e914`
- `0x14007eac4`
- `0x14007f17c`
- `0x14007f6a0`
- `0x14007f6f8`
- `0x140080574`
- `0x140081a78`
- `0x1400823e0`
- `0x140088278`
- `0x14008b87c`
- `0x140092ed0`
- `0x14009381c`
- `0x14009397c`
- `0x140093cb0`
- `0x140094054`
- `0x14009414c`
- `0x140094230`
- `0x1400942dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x140076ef6`

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
0x140076ef6  jmp     cs:__imp_memmove
```
