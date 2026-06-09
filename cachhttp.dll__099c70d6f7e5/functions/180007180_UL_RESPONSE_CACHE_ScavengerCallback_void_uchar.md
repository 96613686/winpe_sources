# UL_RESPONSE_CACHE::ScavengerCallback(void *,uchar)

- ea: `0x180007180`
- end: `0x1800071b3`
- name: `?ScavengerCallback@UL_RESPONSE_CACHE@@CAXPEAXE@Z`
- size: `51`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000653c`
- `0x180007180`

## pseudocode

```c
void __fastcall UL_RESPONSE_CACHE::ScavengerCallback(CLKRHashTable *a1)
{
  if ( !_InterlockedCompareExchange(&UL_RESPONSE_CACHE::sm_fScavengerFired, 1, 0) )
  {
    CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::DeleteIf(
      a1,
      (__int64)&UL_RESPONSE_CACHE::CacheFlushByTTL,
      0);
    UL_RESPONSE_CACHE::sm_fScavengerFired = 0;
  }
}

```

## disassembly

```asm
0x180007180  sub     rsp, 28h
0x180007184  mov     edx, 1
0x180007189  xor     eax, eax
0x18000718b  lock cmpxchg cs:?sm_fScavengerFired@UL_RESPONSE_CACHE@@0HA, edx; int UL_RESPONSE_CACHE::sm_fScavengerFired
0x180007193  jnz     short loc_1800071AE
0x180007195  xor     r8d, r8d
0x180007198  lea     rdx, ?CacheFlushByTTL@UL_RESPONSE_CACHE@@CA?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z; UL_RESPONSE_CACHE::CacheFlushByTTL(UL_RESPONSE_CACHE_ENTRY *,void *)
0x18000719f  call    ?DeleteIf@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@QEAAKP6A?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z1@Z; CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::DeleteIf(LK_PREDICATE (*)(UL_RESPONSE_CACHE_ENTRY *,void *),void *)
0x1800071a4  mov     cs:?sm_fScavengerFired@UL_RESPONSE_CACHE@@0HA, 0; int UL_RESPONSE_CACHE::sm_fScavengerFired
0x1800071ae  add     rsp, 28h
0x1800071b2  retn
```
