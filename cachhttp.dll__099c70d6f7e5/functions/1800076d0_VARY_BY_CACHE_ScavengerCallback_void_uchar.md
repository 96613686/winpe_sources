# VARY_BY_CACHE::ScavengerCallback(void *,uchar)

- ea: `0x1800076d0`
- end: `0x180007704`
- name: `?ScavengerCallback@VARY_BY_CACHE@@CAXPEAXE@Z`
- size: `52`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800076d0`

## import_xrefs

- `iisutil!?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z` at `0x1800076ef`
- `iisutil!?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z` at `0x1800076ef`

## pseudocode

```c
void __fastcall VARY_BY_CACHE::ScavengerCallback(TREE_HASH_TABLE *a1)
{
  if ( !_InterlockedCompareExchange(&VARY_BY_CACHE::sm_fScavengerFired, 1, 0) )
  {
    TREE_HASH_TABLE::DeleteIf(a1, (int (*)(void *, void *))VARY_BY_CACHE::CacheFlushByTTL, 0);
    VARY_BY_CACHE::sm_fScavengerFired = 0;
  }
}

```

## disassembly

```asm
0x1800076d0  sub     rsp, 28h
0x1800076d4  mov     edx, 1
0x1800076d9  xor     eax, eax
0x1800076db  lock cmpxchg cs:?sm_fScavengerFired@VARY_BY_CACHE@@0HA, edx; int VARY_BY_CACHE::sm_fScavengerFired
0x1800076e3  jnz     short loc_1800076FF
0x1800076e5  xor     r8d, r8d
0x1800076e8  lea     rdx, ?CacheFlushByTTL@VARY_BY_CACHE@@CAHPEAX0@Z; VARY_BY_CACHE::CacheFlushByTTL(void *,void *)
0x1800076ef  call    cs:__imp_?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z; TREE_HASH_TABLE::DeleteIf(int (*)(void *,void *),void *)
0x1800076f5  mov     cs:?sm_fScavengerFired@VARY_BY_CACHE@@0HA, 0; int VARY_BY_CACHE::sm_fScavengerFired
0x1800076ff  add     rsp, 28h
0x180007703  retn
```
