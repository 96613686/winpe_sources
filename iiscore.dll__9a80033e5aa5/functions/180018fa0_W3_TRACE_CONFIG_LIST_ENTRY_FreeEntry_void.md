# W3_TRACE_CONFIG_LIST_ENTRY::FreeEntry(void)

- ea: `0x180018fa0`
- end: `0x180018fbf`
- name: `?FreeEntry@W3_TRACE_CONFIG_LIST_ENTRY@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(W3_TRACE_CONFIG_LIST_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e690`
- `0x18002fb14`

## callees

- `0x180018fa0`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180018fb4`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180018fb4`

## pseudocode

```c
void __fastcall W3_TRACE_CONFIG_LIST_ENTRY::FreeEntry(W3_TRACE_CONFIG_LIST_ENTRY *this)
{
  if ( *((_BYTE *)this + 64) )
    ALLOC_CACHE_HANDLER::Free(W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries, this);
}

```

## disassembly

```asm
0x180018fa0  sub     rsp, 28h
0x180018fa4  cmp     byte ptr [rcx+40h], 0
0x180018fa8  jz      short loc_180018FBA
0x180018faa  mov     rdx, rcx
0x180018fad  mov     rcx, cs:?sm_pachTraceConfigListEntries@W3_TRACE_CONFIG_LIST_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries
0x180018fb4  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180018fba  add     rsp, 28h
0x180018fbe  retn
```
