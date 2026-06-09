# ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)

- ea: `0x18001fc10`
- end: `0x18001fc4c`
- name: `?ResetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ`
- size: `60`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001eba0`
- `0x18001f710`

## callees

- `0x18001fc10`

## import_xrefs

- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x18001fc26`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x18001fc26`

## pseudocode

```c
_BOOL8 ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)
{
  BOOL v0; // eax

  if ( !ALLOC_CACHE_HANDLER::sm_hTimer )
    return 1;
  v0 = DeleteTimerQueueTimer(0, ALLOC_CACHE_HANDLER::sm_hTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  ALLOC_CACHE_HANDLER::sm_hTimer = 0;
  return v0;
}

```

## disassembly

```asm
0x18001fc10  sub     rsp, 28h
0x18001fc14  mov     rdx, cs:?sm_hTimer@ALLOC_CACHE_HANDLER@@0PEAXEA; Timer
0x18001fc1b  test    rdx, rdx
0x18001fc1e  jz      short loc_18001FC42
0x18001fc20  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001fc24  xor     ecx, ecx; TimerQueue
0x18001fc26  call    cs:__imp_DeleteTimerQueueTimer
0x18001fc2c  xor     ecx, ecx
0x18001fc2e  mov     cs:?sm_hTimer@ALLOC_CACHE_HANDLER@@0PEAXEA, 0; void * ALLOC_CACHE_HANDLER::sm_hTimer
0x18001fc39  test    eax, eax
0x18001fc3b  setnz   cl
0x18001fc3e  mov     eax, ecx
0x18001fc40  jmp     short loc_18001FC47
0x18001fc42  mov     eax, 1
0x18001fc47  add     rsp, 28h
0x18001fc4b  retn
```
