# ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)

- ea: `0x180020f40`
- end: `0x180020f83`
- name: `?ResetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ`
- size: `67`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001fda0`
- `0x1800209f0`

## callees

- `0x180020f40`

## import_xrefs

- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x180020f56`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x180020f56`

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
0x180020f40  sub     rsp, 28h
0x180020f44  mov     rdx, cs:?sm_hTimer@ALLOC_CACHE_HANDLER@@0PEAXEA; Timer
0x180020f4b  test    rdx, rdx
0x180020f4e  jz      short loc_180020F78
0x180020f50  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180020f54  xor     ecx, ecx; TimerQueue
0x180020f56  call    cs:__imp_DeleteTimerQueueTimer
0x180020f5d  nop     dword ptr [rax+rax+00h]
0x180020f62  xor     ecx, ecx
0x180020f64  mov     cs:?sm_hTimer@ALLOC_CACHE_HANDLER@@0PEAXEA, 0; void * ALLOC_CACHE_HANDLER::sm_hTimer
0x180020f6f  test    eax, eax
0x180020f71  setnz   cl
0x180020f74  mov     eax, ecx
0x180020f76  jmp     short loc_180020F7D
0x180020f78  mov     eax, 1
0x180020f7d  add     rsp, 28h
0x180020f81  retn
```
