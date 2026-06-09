# InvalidateAppModelVersionCache

- ea: `0x1800071c0`
- end: `0x1800071c6`
- name: `InvalidateAppModelVersionCache`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!InvalidateAppModelVersionCache` at `0x1800071c0`

## pseudocode

```c
// attributes: thunk
__int64 InvalidateAppModelVersionCache()
{
  return __imp_InvalidateAppModelVersionCache();
}

```

## disassembly

```asm
0x1800071c0  jmp     cs:__imp_InvalidateAppModelVersionCache
```
