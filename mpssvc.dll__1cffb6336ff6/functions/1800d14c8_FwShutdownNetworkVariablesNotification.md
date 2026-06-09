# FwShutdownNetworkVariablesNotification

- ea: `0x1800d14c8`
- end: `0x1800d160a`
- name: `FwShutdownNetworkVariablesNotification`
- size: `322`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d1010`
- `0x1800d107c`
- `0x1800dd12c`

## callees

- `0x18006ffc8`
- `0x1800d14c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d157f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d157f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d1591`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d1591`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800d14fb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800d14fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d1508`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d1508`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d14e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d14e9`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d153f`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d1556`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d156d`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d153f`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d1556`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d156d`
- `fwbase!FwCriticalSectionDestroy` at `0x1800d15ea`
- `fwbase!FwCriticalSectionDestroy` at `0x1800d15ea`
- `fwbase!FwCloseHandle` at `0x1800d159b`
- `fwbase!FwCloseHandle` at `0x1800d15a5`
- `fwbase!FwCloseHandle` at `0x1800d15b7`
- `fwbase!FwCloseHandle` at `0x1800d15c8`
- `fwbase!FwCloseHandle` at `0x1800d15d9`
- `fwbase!FwCloseHandle` at `0x1800d159b`
- `fwbase!FwCloseHandle` at `0x1800d15a5`
- `fwbase!FwCloseHandle` at `0x1800d15b7`
- `fwbase!FwCloseHandle` at `0x1800d15c8`
- `fwbase!FwCloseHandle` at `0x1800d15d9`
- `fwbase!FwCriticalSectionEnter` at `0x1800d1520`
- `fwbase!FwCriticalSectionEnter` at `0x1800d1520`
- `fwbase!FwCriticalSectionLeave` at `0x1800d1530`
- `fwbase!FwCriticalSectionLeave` at `0x1800d1530`

## pseudocode

```c
void *__fastcall FwShutdownNetworkVariablesNotification(char *a1)
{
  struct _TP_TIMER *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)a1 + 18);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)a1 + 18), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)a1 + 18));
    *((_QWORD *)a1 + 18) = 0;
  }
  FwCriticalSectionEnter(a1 + 72);
  *((_DWORD *)a1 + 16) = 0;
  FwCriticalSectionLeave(a1 + 72);
  v3 = (void *)*((_QWORD *)a1 + 5);
  if ( v3 )
  {
    CancelMibChangeNotify2(v3);
    *((_QWORD *)a1 + 5) = 0;
  }
  v4 = (void *)*((_QWORD *)a1 + 4);
  if ( v4 )
  {
    CancelMibChangeNotify2(v4);
    *((_QWORD *)a1 + 4) = 0;
  }
  v5 = (void *)*((_QWORD *)a1 + 3);
  if ( v5 )
  {
    CancelMibChangeNotify2(v5);
    *((_QWORD *)a1 + 3) = 0;
  }
  SetEvent(*((HANDLE *)a1 + 1));
  v6 = (void *)*((_QWORD *)a1 + 6);
  if ( v6 )
    WaitForSingleObject(v6, 0xFFFFFFFF);
  FwCloseHandle(*((_QWORD *)a1 + 6));
  FwCloseHandle(*((_QWORD *)a1 + 7));
  v7 = *((_QWORD *)a1 + 2);
  *((_QWORD *)a1 + 7) = 0;
  FwCloseHandle(v7);
  v8 = *(_QWORD *)a1;
  *((_QWORD *)a1 + 2) = 0;
  FwCloseHandle(v8);
  v9 = *((_QWORD *)a1 + 1);
  *(_QWORD *)a1 = 0;
  FwCloseHandle(v9);
  *((_QWORD *)a1 + 1) = 0;
  FwCriticalSectionDestroy(a1 + 72);
  return memset_0(a1, 0, 0xA0u);
}

```

## disassembly

```asm
0x1800d14c8  mov     [rsp+arg_0], rbx
0x1800d14cd  push    rdi
0x1800d14ce  sub     rsp, 20h
0x1800d14d2  mov     rbx, rcx
0x1800d14d5  mov     rcx, [rcx+90h]; pti
0x1800d14dc  test    rcx, rcx
0x1800d14df  jz      short loc_1800D1519
0x1800d14e1  xor     r9d, r9d; msWindowLength
0x1800d14e4  xor     r8d, r8d; msPeriod
0x1800d14e7  xor     edx, edx; pftDueTime
0x1800d14e9  call    cs:__imp_SetThreadpoolTimer
0x1800d14ef  mov     rcx, [rbx+90h]; pti
0x1800d14f6  mov     edx, 1; fCancelPendingCallbacks
0x1800d14fb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800d1501  mov     rcx, [rbx+90h]; pti
0x1800d1508  call    cs:__imp_CloseThreadpoolTimer
0x1800d150e  mov     qword ptr [rbx+90h], 0
0x1800d1519  lea     rdi, [rbx+48h]
0x1800d151d  mov     rcx, rdi
0x1800d1520  call    cs:__imp_FwCriticalSectionEnter
0x1800d1526  mov     rcx, rdi
0x1800d1529  mov     dword ptr [rbx+40h], 0
0x1800d1530  call    cs:__imp_FwCriticalSectionLeave
0x1800d1536  mov     rcx, [rbx+28h]; NotificationHandle
0x1800d153a  test    rcx, rcx
0x1800d153d  jz      short loc_1800D154D
0x1800d153f  call    cs:__imp_CancelMibChangeNotify2
0x1800d1545  mov     qword ptr [rbx+28h], 0
0x1800d154d  mov     rcx, [rbx+20h]; NotificationHandle
0x1800d1551  test    rcx, rcx
0x1800d1554  jz      short loc_1800D1564
0x1800d1556  call    cs:__imp_CancelMibChangeNotify2
0x1800d155c  mov     qword ptr [rbx+20h], 0
0x1800d1564  mov     rcx, [rbx+18h]; NotificationHandle
0x1800d1568  test    rcx, rcx
0x1800d156b  jz      short loc_1800D157B
0x1800d156d  call    cs:__imp_CancelMibChangeNotify2
0x1800d1573  mov     qword ptr [rbx+18h], 0
0x1800d157b  mov     rcx, [rbx+8]; hEvent
0x1800d157f  call    cs:__imp_SetEvent
0x1800d1585  mov     rcx, [rbx+30h]; hHandle
0x1800d1589  test    rcx, rcx
0x1800d158c  jz      short loc_1800D1597
0x1800d158e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800d1591  call    cs:__imp_WaitForSingleObject
0x1800d1597  mov     rcx, [rbx+30h]
0x1800d159b  call    cs:__imp_FwCloseHandle
0x1800d15a1  mov     rcx, [rbx+38h]
0x1800d15a5  call    cs:__imp_FwCloseHandle
0x1800d15ab  mov     rcx, [rbx+10h]
0x1800d15af  mov     qword ptr [rbx+38h], 0
0x1800d15b7  call    cs:__imp_FwCloseHandle
0x1800d15bd  mov     rcx, [rbx]
0x1800d15c0  mov     qword ptr [rbx+10h], 0
0x1800d15c8  call    cs:__imp_FwCloseHandle
0x1800d15ce  mov     rcx, [rbx+8]
0x1800d15d2  mov     qword ptr [rbx], 0
0x1800d15d9  call    cs:__imp_FwCloseHandle
0x1800d15df  mov     rcx, rdi
0x1800d15e2  mov     qword ptr [rbx+8], 0
0x1800d15ea  call    cs:__imp_FwCriticalSectionDestroy
0x1800d15f0  xor     edx, edx; Val
0x1800d15f2  mov     r8d, 0A0h; Size
0x1800d15f8  mov     rcx, rbx; void *
0x1800d15fb  mov     rbx, [rsp+28h+arg_0]
0x1800d1600  add     rsp, 20h
0x1800d1604  pop     rdi
0x1800d1605  jmp     memset_0
```
