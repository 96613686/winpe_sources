# CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::DeleteIf(LK_PREDICATE (*)(UL_RESPONSE_CACHE_ENTRY *,void *),void *)

- ea: `0x18000653c`
- end: `0x180006573`
- name: `?DeleteIf@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@QEAAKP6A?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z1@Z`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d10`
- `0x180003fe0`
- `0x180007180`

## callees

- `0x18000653c`

## import_xrefs

- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180006568`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180006568`

## pseudocode

```c
unsigned int __fastcall CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::DeleteIf(
        CLKRHashTable *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD v4[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( !a2 )
    return 0;
  v4[0] = a2;
  v4[2] = a3;
  v4[1] = 0;
  return CLKRHashTable::DeleteIf(
           a1,
           (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_Pred,
           v4);
}

```

## disassembly

```asm
0x18000653c  sub     rsp, 48h
0x180006540  test    rdx, rdx
0x180006543  jnz     short loc_180006549
0x180006545  xor     eax, eax
0x180006547  jmp     short loc_18000656E
0x180006549  mov     [rsp+48h+var_28], rdx
0x18000654e  lea     rdx, ?_Pred@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_Pred(void const *,void *)
0x180006555  mov     [rsp+48h+var_18], r8
0x18000655a  lea     r8, [rsp+48h+var_28]
0x18000655f  mov     [rsp+48h+var_20], 0
0x180006568  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x18000656e  add     rsp, 48h
0x180006572  retn
```
