# ALLOC_CACHE_HANDLER::Cleanup(int)

- ea: `0x18001f710`
- end: `0x18001f743`
- name: `?Cleanup@ALLOC_CACHE_HANDLER@@SAHH@Z`
- size: `51`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180014240`

## callees

- `0x18001f710`
- `0x18001fc10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f729`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f729`

## pseudocode

```c
__int64 __fastcall ALLOC_CACHE_HANDLER::Cleanup()
{
  ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval();
  if ( ALLOC_CACHE_HANDLER::sm_fInitCsItems )
  {
    DeleteCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
    ALLOC_CACHE_HANDLER::sm_fInitCsItems = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001f710  sub     rsp, 28h
0x18001f714  call    ?ResetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ; ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)
0x18001f719  cmp     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, 0; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x18001f720  jz      short loc_18001F739
0x18001f722  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f729  call    cs:__imp_DeleteCriticalSection
0x18001f72f  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, 0; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x18001f739  mov     eax, 1
0x18001f73e  add     rsp, 28h
0x18001f742  retn
```
