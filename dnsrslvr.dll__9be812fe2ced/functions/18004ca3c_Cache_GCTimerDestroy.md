# Cache_GCTimerDestroy

- ea: `0x18004ca3c`
- end: `0x18004ca9c`
- name: `Cache_GCTimerDestroy`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18003cfc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ca86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ca86`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004ca61`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004ca61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004ca4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004ca4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004ca6e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004ca6e`

## pseudocode

```c
BOOL Cache_GCTimerDestroy()
{
  BOOL result; // eax

  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
  pti = 0;
  result = CloseHandle(g_hCacheGCEvent);
  g_hCacheGCEvent = 0;
  return result;
}

```

## disassembly

```asm
0x18004ca3c  sub     rsp, 28h
0x18004ca40  mov     rcx, cs:pti; pti
0x18004ca47  xor     r9d, r9d; msWindowLength
0x18004ca4a  xor     r8d, r8d; msPeriod
0x18004ca4d  xor     edx, edx; pftDueTime
0x18004ca4f  call    cs:__imp_SetThreadpoolTimer
0x18004ca55  mov     rcx, cs:pti; pti
0x18004ca5c  mov     edx, 1; fCancelPendingCallbacks
0x18004ca61  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004ca67  mov     rcx, cs:pti; pti
0x18004ca6e  call    cs:__imp_CloseThreadpoolTimer
0x18004ca74  mov     rcx, cs:g_hCacheGCEvent; hObject
0x18004ca7b  mov     cs:pti, 0
0x18004ca86  call    cs:__imp_CloseHandle
0x18004ca8c  mov     cs:g_hCacheGCEvent, 0
0x18004ca97  add     rsp, 28h
0x18004ca9b  retn
```
