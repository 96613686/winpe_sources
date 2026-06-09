# IP_RESTRICTION_LIST::TimerCallback(void *,uchar)

- ea: `0x1800048c0`
- end: `0x180004904`
- name: `?TimerCallback@IP_RESTRICTION_LIST@@SAXPEAXE@Z`
- size: `68`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800048d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800048d9`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x1800048f9`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x1800048f9`

## pseudocode

```c
void __fastcall IP_RESTRICTION_LIST::TimerCallback(PVOID a1)
{
  _QWORD v1[5]; // [rsp+20h] [rbp-28h] BYREF

  v1[1] = 0;
  v1[0] = &FAST_DNS_LOOKUP_HASH::CacheFlushByTime;
  v1[2] = GetTickCount();
  CLKRHashTable::DeleteIf(
    (CLKRHashTable *)&IP_RESTRICTION_LIST::sm_FastDNSLookupTable,
    (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<FAST_DNS_LOOKUP_HASH,FAST_DNS_LOOKUP_ENTRY,sockaddr *,CLKRHashTable>::_Pred,
    v1);
}

```

## disassembly

```asm
0x1800048c0  sub     rsp, 48h
0x1800048c4  lea     rax, ?CacheFlushByTime@FAST_DNS_LOOKUP_HASH@@SA?AW4LK_PREDICATE@@PEAVFAST_DNS_LOOKUP_ENTRY@@PEAX@Z; FAST_DNS_LOOKUP_HASH::CacheFlushByTime(FAST_DNS_LOOKUP_ENTRY *,void *)
0x1800048cb  mov     [rsp+48h+var_20], 0
0x1800048d4  mov     [rsp+48h+var_28], rax
0x1800048d9  call    cs:__imp_GetTickCount
0x1800048df  mov     eax, eax
0x1800048e1  lea     r8, [rsp+48h+var_28]
0x1800048e6  lea     rdx, ?_Pred@?$CTypedHashTable@VFAST_DNS_LOOKUP_HASH@@VFAST_DNS_LOOKUP_ENTRY@@PEAUsockaddr@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<FAST_DNS_LOOKUP_HASH,FAST_DNS_LOOKUP_ENTRY,sockaddr *,CLKRHashTable>::_Pred(void const *,void *)
0x1800048ed  mov     [rsp+48h+var_18], rax
0x1800048f2  lea     rcx, ?sm_FastDNSLookupTable@IP_RESTRICTION_LIST@@0VFAST_DNS_LOOKUP_HASH@@A; FAST_DNS_LOOKUP_HASH IP_RESTRICTION_LIST::sm_FastDNSLookupTable
0x1800048f9  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x1800048ff  add     rsp, 48h
0x180004903  retn
```
