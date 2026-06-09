# ShutdownHttpServer

- ea: `0x1800676ec`
- end: `0x1800677a4`
- name: `ShutdownHttpServer`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180042840`

## callees

- `0x1800676ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067700`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067700`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180067713`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180067713`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180067731`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180067731`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180067774`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180067774`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180067787`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180067787`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006775c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006775c`

## pseudocode

```c
void ShutdownHttpServer()
{
  if ( byte_1800CC2F8 )
  {
    DeleteCriticalSection(&stru_1800CC2D0);
    CloseThreadpoolCleanupGroup(*(&ptpp + 1));
    *(&ptpp + 1) = 0;
    CloseThreadpool(ptpp);
    ptpp = 0;
  }
  if ( g_IpTlsSqmServerTimer )
  {
    SetThreadpoolTimer(g_IpTlsSqmServerTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(g_IpTlsSqmServerTimer, 1);
    CloseThreadpoolTimer(g_IpTlsSqmServerTimer);
    g_IpTlsSqmServerTimer = 0;
  }
}

```

## disassembly

```asm
0x1800676ec  sub     rsp, 28h
0x1800676f0  cmp     cs:byte_1800CC2F8, 0
0x1800676f7  jz      short loc_180067748
0x1800676f9  lea     rcx, stru_1800CC2D0; lpCriticalSection
0x180067700  call    cs:__imp_DeleteCriticalSection
0x180067707  nop     dword ptr [rax+rax+00h]
0x18006770c  mov     rcx, qword ptr cs:ptpp+8; ptpcg
0x180067713  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18006771a  nop     dword ptr [rax+rax+00h]
0x18006771f  mov     rcx, qword ptr cs:ptpp; ptpp
0x180067726  mov     qword ptr cs:ptpp+8, 0
0x180067731  call    cs:__imp_CloseThreadpool
0x180067738  nop     dword ptr [rax+rax+00h]
0x18006773d  mov     qword ptr cs:ptpp, 0
0x180067748  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x18006774f  test    rcx, rcx
0x180067752  jz      short loc_18006779E
0x180067754  xor     r9d, r9d; msWindowLength
0x180067757  xor     r8d, r8d; msPeriod
0x18006775a  xor     edx, edx; pftDueTime
0x18006775c  call    cs:__imp_SetThreadpoolTimer
0x180067763  nop     dword ptr [rax+rax+00h]
0x180067768  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x18006776f  mov     edx, 1; fCancelPendingCallbacks
0x180067774  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006777b  nop     dword ptr [rax+rax+00h]
0x180067780  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x180067787  call    cs:__imp_CloseThreadpoolTimer
0x18006778e  nop     dword ptr [rax+rax+00h]
0x180067793  mov     cs:g_IpTlsSqmServerTimer, 0
0x18006779e  add     rsp, 28h
0x1800677a2  retn
```
