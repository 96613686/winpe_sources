# ShutdownHttpServer

- ea: `0x18006770c`
- end: `0x1800677c4`
- name: `ShutdownHttpServer`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180042800`

## callees

- `0x18006770c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067720`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067720`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180067733`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180067733`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180067751`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180067751`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180067794`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180067794`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800677a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800677a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006777c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006777c`

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
0x18006770c  sub     rsp, 28h
0x180067710  cmp     cs:byte_1800CC2F8, 0
0x180067717  jz      short loc_180067768
0x180067719  lea     rcx, stru_1800CC2D0; lpCriticalSection
0x180067720  call    cs:__imp_DeleteCriticalSection
0x180067727  nop     dword ptr [rax+rax+00h]
0x18006772c  mov     rcx, qword ptr cs:ptpp+8; ptpcg
0x180067733  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18006773a  nop     dword ptr [rax+rax+00h]
0x18006773f  mov     rcx, qword ptr cs:ptpp; ptpp
0x180067746  mov     qword ptr cs:ptpp+8, 0
0x180067751  call    cs:__imp_CloseThreadpool
0x180067758  nop     dword ptr [rax+rax+00h]
0x18006775d  mov     qword ptr cs:ptpp, 0
0x180067768  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x18006776f  test    rcx, rcx
0x180067772  jz      short loc_1800677BE
0x180067774  xor     r9d, r9d; msWindowLength
0x180067777  xor     r8d, r8d; msPeriod
0x18006777a  xor     edx, edx; pftDueTime
0x18006777c  call    cs:__imp_SetThreadpoolTimer
0x180067783  nop     dword ptr [rax+rax+00h]
0x180067788  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x18006778f  mov     edx, 1; fCancelPendingCallbacks
0x180067794  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006779b  nop     dword ptr [rax+rax+00h]
0x1800677a0  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x1800677a7  call    cs:__imp_CloseThreadpoolTimer
0x1800677ae  nop     dword ptr [rax+rax+00h]
0x1800677b3  mov     cs:g_IpTlsSqmServerTimer, 0
0x1800677be  add     rsp, 28h
0x1800677c2  retn
```
