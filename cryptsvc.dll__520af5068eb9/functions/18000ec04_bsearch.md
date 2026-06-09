# bsearch

- ea: `0x18000ec04`
- end: `0x18000ec0a`
- name: `bsearch`
- size: `6`
- prototype: `void *__cdecl(const void *Key, const void *Base, size_t NumOfElements, size_t SizeOfElements, _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001284`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_bsearch` at `0x18000ec04`

## pseudocode

```c
// attributes: thunk
void *__cdecl bsearch(
        const void *Key,
        const void *Base,
        size_t NumOfElements,
        size_t SizeOfElements,
        _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)
{
  return _o_bsearch(Key, Base, NumOfElements, SizeOfElements, CompareFunction);
}

```

## disassembly

```asm
0x18000ec04  jmp     cs:__imp__o_bsearch
```
