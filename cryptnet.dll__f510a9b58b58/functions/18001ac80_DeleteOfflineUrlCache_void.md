# DeleteOfflineUrlCache(void)

- ea: `0x18001ac80`
- end: `0x18001acac`
- name: `?DeleteOfflineUrlCache@@YAXXZ`
- size: `44`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016770`

## callees

- `0x18001ac80`
- `0x180020108`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001aca5`

## pseudocode

```c
void DeleteOfflineUrlCache(void)
{
  while ( pOfflineUrlCacheHead )
    RemoveAndFreeOfflineUrlCacheEntry(pOfflineUrlCacheHead);
  DeleteCriticalSection(&OfflineUrlCacheCriticalSection);
}

```

## disassembly

```asm
0x18001ac80  sub     rsp, 28h
0x18001ac84  jmp     short loc_18001AC8E
0x18001ac86  mov     rcx, rax; struct _OFFLINE_URL_CACHE_ENTRY *
0x18001ac89  call    ?RemoveAndFreeOfflineUrlCacheEntry@@YAXPEAU_OFFLINE_URL_CACHE_ENTRY@@@Z; RemoveAndFreeOfflineUrlCacheEntry(_OFFLINE_URL_CACHE_ENTRY *)
0x18001ac8e  mov     rax, cs:?pOfflineUrlCacheHead@@3PEAU_OFFLINE_URL_CACHE_ENTRY@@EA; _OFFLINE_URL_CACHE_ENTRY * pOfflineUrlCacheHead
0x18001ac95  test    rax, rax
0x18001ac98  jnz     short loc_18001AC86
0x18001ac9a  lea     rcx, ?OfflineUrlCacheCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION OfflineUrlCacheCriticalSection
0x18001aca1  add     rsp, 28h
0x18001aca5  jmp     cs:__imp_DeleteCriticalSection
```
