# W3_TRACE_CONFIG_LIST_ENTRY::FreeEntry(void)

- ea: `0x18001a550`
- end: `0x18001a576`
- name: `?FreeEntry@W3_TRACE_CONFIG_LIST_ENTRY@@QEAAXXZ`
- size: `38`
- prototype: `void __fastcall(W3_TRACE_CONFIG_LIST_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f2cc`
- `0x180032774`

## callees

- `0x18001a550`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001a564`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001a564`

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
0x18001a550  sub     rsp, 28h
0x18001a554  cmp     byte ptr [rcx+40h], 0
0x18001a558  jz      short loc_18001A570
0x18001a55a  mov     rdx, rcx
0x18001a55d  mov     rcx, cs:?sm_pachTraceConfigListEntries@W3_TRACE_CONFIG_LIST_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries
0x18001a564  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001a56b  nop     dword ptr [rax+rax+00h]
0x18001a570  add     rsp, 28h
0x18001a574  retn
```
