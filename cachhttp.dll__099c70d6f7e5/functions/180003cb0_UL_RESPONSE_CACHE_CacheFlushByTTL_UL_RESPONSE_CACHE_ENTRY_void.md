# UL_RESPONSE_CACHE::CacheFlushByTTL(UL_RESPONSE_CACHE_ENTRY *,void *)

- ea: `0x180003cb0`
- end: `0x180003cc5`
- name: `?CacheFlushByTTL@UL_RESPONSE_CACHE@@CA?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall UL_RESPONSE_CACHE::CacheFlushByTTL(__int64 a1)
{
  return 3 - (unsigned int)(_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 760), 0xFFFFFFFF) != 1);
}

```

## disassembly

```asm
0x180003cb0  or      eax, 0FFFFFFFFh
0x180003cb3  lock xadd [rcx+2F8h], eax
0x180003cbb  dec     eax
0x180003cbd  neg     eax
0x180003cbf  sbb     eax, eax
0x180003cc1  add     eax, 3
0x180003cc4  retn
```
