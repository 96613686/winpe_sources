# ALLOC_CACHE_HANDLER::Cleanup(int)

- ea: `0x1800209f0`
- end: `0x180020a2a`
- name: `?Cleanup@ALLOC_CACHE_HANDLER@@SAHH@Z`
- size: `58`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180014ca0`

## callees

- `0x1800209f0`
- `0x180020f40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020a09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020a09`

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
0x1800209f0  sub     rsp, 28h
0x1800209f4  call    ?ResetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ; ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)
0x1800209f9  cmp     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, 0; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x180020a00  jz      short loc_180020A1F
0x180020a02  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020a09  call    cs:__imp_DeleteCriticalSection
0x180020a10  nop     dword ptr [rax+rax+00h]
0x180020a15  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, 0; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x180020a1f  mov     eax, 1
0x180020a24  add     rsp, 28h
0x180020a28  retn
```
