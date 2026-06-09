# TOKEN_CACHE::ScavengerCallback(void *,uchar)

- ea: `0x180002430`
- end: `0x180002468`
- name: `?ScavengerCallback@TOKEN_CACHE@@CAXPEAXE@Z`
- size: `56`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18000245d`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18000245d`

## pseudocode

```c
void __fastcall TOKEN_CACHE::ScavengerCallback(CLKRHashTable *a1)
{
  _QWORD v1[5]; // [rsp+20h] [rbp-28h] BYREF

  v1[1] = 0;
  v1[0] = &TOKEN_CACHE::CacheFlushByTTL;
  v1[2] = 0;
  CLKRHashTable::DeleteIf(
    a1,
    (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_Pred,
    v1);
}

```

## disassembly

```asm
0x180002430  mov     r11, rsp
0x180002433  sub     rsp, 48h
0x180002437  lea     rax, ?CacheFlushByTTL@TOKEN_CACHE@@CA?AW4LK_PREDICATE@@PEAVTOKEN_ENTRY@@PEAX@Z; TOKEN_CACHE::CacheFlushByTTL(TOKEN_ENTRY *,void *)
0x18000243e  mov     qword ptr [r11-20h], 0
0x180002446  lea     r8, [r11-28h]
0x18000244a  mov     [r11-28h], rax
0x18000244e  lea     rdx, ?_Pred@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_ENTRY@@PEAVIHttpCacheKey@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_Pred(void const *,void *)
0x180002455  mov     qword ptr [r11-18h], 0
0x18000245d  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x180002463  add     rsp, 48h
0x180002467  retn
```
