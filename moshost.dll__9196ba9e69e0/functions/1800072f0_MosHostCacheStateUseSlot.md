# MosHostCacheStateUseSlot

- ea: `0x1800072f0`
- end: `0x1800072f6`
- name: `MosHostCacheStateUseSlot`
- size: `6`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 MosHostCacheStateUseSlot()
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800072f0  mov     eax, 80004001h; MosHostCacheStateGetSizes
0x1800072f5  retn
```
