# memcpy_0

- ea: `0x18000aadd`
- end: `0x18000aae3`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800026b0`
- `0x180002c20`
- `0x180003be0`
- `0x180004030`
- `0x1800044d0`
- `0x180004a60`
- `0x180004ee0`
- `0x180005300`
- `0x180006c50`
- `0x180006e80`
- `0x1800070f0`
- `0x1800072a0`
- `0x180007310`
- `0x1800074e0`
- `0x1800075e0`
- `0x1800077b0`
- `0x180007ac0`
- `0x180008c50`
- `0x180008dd4`
- `0x180009c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18000aadd`

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
0x18000aadd  jmp     cs:__imp_memcpy
```
