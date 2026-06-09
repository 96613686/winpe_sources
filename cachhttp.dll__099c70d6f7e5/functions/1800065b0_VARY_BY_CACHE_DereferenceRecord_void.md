# VARY_BY_CACHE::DereferenceRecord(void *)

- ea: `0x1800065b0`
- end: `0x1800065c2`
- name: `?DereferenceRecord@VARY_BY_CACHE@@UEAAXPEAX@Z`
- size: `18`
- prototype: `void(VARY_BY_CACHE *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004744`

## pseudocode

```c
void __fastcall VARY_BY_CACHE::DereferenceRecord(VARY_BY_CACHE *this, VARY_BY_CACHE_ENTRY *a2)
{
  *((_DWORD *)a2 + 332) = 1;
  VARY_BY_CACHE_ENTRY::DereferenceCacheData(a2);
}

```

## disassembly

```asm
0x1800065b0  mov     rcx, rdx; this
0x1800065b3  mov     dword ptr [rdx+530h], 1
0x1800065bd  jmp     ?DereferenceCacheData@VARY_BY_CACHE_ENTRY@@QEAAXXZ; VARY_BY_CACHE_ENTRY::DereferenceCacheData(void)
```
