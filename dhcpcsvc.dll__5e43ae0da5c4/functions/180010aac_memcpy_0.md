# memcpy_0

- ea: `0x180010aac`
- end: `0x180010ab2`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x180001490`
- `0x180005a20`
- `0x180006e10`
- `0x180007010`
- `0x180007200`
- `0x1800075d0`
- `0x180007aa0`
- `0x180008700`
- `0x1800088d0`
- `0x18000a950`
- `0x18000ac50`
- `0x18000c7d0`
- `0x18000c990`
- `0x18000cc10`
- `0x18000cfe0`
- `0x18000d5c8`
- `0x18000da80`
- `0x18000e8b0`
- `0x18000f020`
- `0x18000f528`
- `0x18000fdc4`
- `0x180010198`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x180010aac`

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
0x180010aac  jmp     cs:__imp_memcpy
```
