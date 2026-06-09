# VARY_BY_CACHE_ENTRY::CleanupStoredContext(void)

- ea: `0x1800076c0`
- end: `0x1800076c5`
- name: `?CleanupStoredContext@VARY_BY_CACHE_ENTRY@@UEAAXXZ`
- size: `5`
- prototype: `void __fastcall(VARY_BY_CACHE_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004744`

## pseudocode

```c
// attributes: thunk
void __fastcall VARY_BY_CACHE_ENTRY::CleanupStoredContext(VARY_BY_CACHE_ENTRY *this)
{
  VARY_BY_CACHE_ENTRY::DereferenceCacheData(this);
}

```

## disassembly

```asm
0x1800076c0  jmp     ?DereferenceCacheData@VARY_BY_CACHE_ENTRY@@QEAAXXZ; VARY_BY_CACHE_ENTRY::DereferenceCacheData(void)
```
