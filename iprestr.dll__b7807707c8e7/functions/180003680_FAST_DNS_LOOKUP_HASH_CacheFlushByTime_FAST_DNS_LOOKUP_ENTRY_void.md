# FAST_DNS_LOOKUP_HASH::CacheFlushByTime(FAST_DNS_LOOKUP_ENTRY *,void *)

- ea: `0x180003680`
- end: `0x180003695`
- name: `?CacheFlushByTime@FAST_DNS_LOOKUP_HASH@@SA?AW4LK_PREDICATE@@PEAVFAST_DNS_LOOKUP_ENTRY@@PEAX@Z`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall FAST_DNS_LOOKUP_HASH::CacheFlushByTime(__int64 a1, int a2)
{
  return (unsigned int)((unsigned int)(*(_DWORD *)(a1 + 220) - a2) < 0x493E0) + 2;
}

```

## disassembly

```asm
0x180003680  mov     eax, [rcx+0DCh]
0x180003686  sub     eax, edx
0x180003688  cmp     eax, 493E0h
0x18000368d  sbb     eax, eax
0x18000368f  neg     eax
0x180003691  add     eax, 2
0x180003694  retn
```
