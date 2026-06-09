# FwShutdownNetworkVariablesNotification

- ea: `0x1800d8e78`
- end: `0x1800d901a`
- name: `FwShutdownNetworkVariablesNotification`
- size: `418`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d8940`
- `0x1800d89b0`
- `0x1800e3274`

## callees

- `0x180073488`
- `0x1800d8e78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d8f5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d8f5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d8f77`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d8f77`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800d8eb1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800d8eb1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d8ec4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d8ec4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d8e99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d8e99`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d8f0d`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d8f2a`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d8f47`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d8f0d`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d8f2a`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800d8f47`
- `fwbase!FwCriticalSectionDestroy` at `0x1800d8ff4`
- `fwbase!FwCriticalSectionDestroy` at `0x1800d8ff4`
- `fwbase!FwCloseHandle` at `0x1800d8f87`
- `fwbase!FwCloseHandle` at `0x1800d8f97`
- `fwbase!FwCloseHandle` at `0x1800d8faf`
- `fwbase!FwCloseHandle` at `0x1800d8fc6`
- `fwbase!FwCloseHandle` at `0x1800d8fdd`
- `fwbase!FwCloseHandle` at `0x1800d8f87`
- `fwbase!FwCloseHandle` at `0x1800d8f97`
- `fwbase!FwCloseHandle` at `0x1800d8faf`
- `fwbase!FwCloseHandle` at `0x1800d8fc6`
- `fwbase!FwCloseHandle` at `0x1800d8fdd`
- `fwbase!FwCriticalSectionEnter` at `0x1800d8ee2`
- `fwbase!FwCriticalSectionEnter` at `0x1800d8ee2`
- `fwbase!FwCriticalSectionLeave` at `0x1800d8ef8`
- `fwbase!FwCriticalSectionLeave` at `0x1800d8ef8`

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
0x1800d8e78  mov     [rsp+arg_0], rbx
0x1800d8e7d  push    rdi
0x1800d8e7e  sub     rsp, 20h
0x1800d8e82  mov     rbx, rcx
0x1800d8e85  mov     rcx, [rcx+90h]; pti
0x1800d8e8c  test    rcx, rcx
0x1800d8e8f  jz      short loc_1800D8EDB
0x1800d8e91  xor     r9d, r9d; msWindowLength
0x1800d8e94  xor     r8d, r8d; msPeriod
0x1800d8e97  xor     edx, edx; pftDueTime
0x1800d8e99  call    cs:__imp_SetThreadpoolTimer
0x1800d8ea0  nop     dword ptr [rax+rax+00h]
0x1800d8ea5  mov     rcx, [rbx+90h]; pti
0x1800d8eac  mov     edx, 1; fCancelPendingCallbacks
0x1800d8eb1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800d8eb8  nop     dword ptr [rax+rax+00h]
0x1800d8ebd  mov     rcx, [rbx+90h]; pti
0x1800d8ec4  call    cs:__imp_CloseThreadpoolTimer
0x1800d8ecb  nop     dword ptr [rax+rax+00h]
0x1800d8ed0  mov     qword ptr [rbx+90h], 0
0x1800d8edb  lea     rdi, [rbx+48h]
0x1800d8edf  mov     rcx, rdi
0x1800d8ee2  call    cs:__imp_FwCriticalSectionEnter
0x1800d8ee9  nop     dword ptr [rax+rax+00h]
0x1800d8eee  mov     rcx, rdi
0x1800d8ef1  mov     dword ptr [rbx+40h], 0
0x1800d8ef8  call    cs:__imp_FwCriticalSectionLeave
0x1800d8eff  nop     dword ptr [rax+rax+00h]
0x1800d8f04  mov     rcx, [rbx+28h]; NotificationHandle
0x1800d8f08  test    rcx, rcx
0x1800d8f0b  jz      short loc_1800D8F21
0x1800d8f0d  call    cs:__imp_CancelMibChangeNotify2
0x1800d8f14  nop     dword ptr [rax+rax+00h]
0x1800d8f19  mov     qword ptr [rbx+28h], 0
0x1800d8f21  mov     rcx, [rbx+20h]; NotificationHandle
0x1800d8f25  test    rcx, rcx
0x1800d8f28  jz      short loc_1800D8F3E
0x1800d8f2a  call    cs:__imp_CancelMibChangeNotify2
0x1800d8f31  nop     dword ptr [rax+rax+00h]
0x1800d8f36  mov     qword ptr [rbx+20h], 0
0x1800d8f3e  mov     rcx, [rbx+18h]; NotificationHandle
0x1800d8f42  test    rcx, rcx
0x1800d8f45  jz      short loc_1800D8F5B
0x1800d8f47  call    cs:__imp_CancelMibChangeNotify2
0x1800d8f4e  nop     dword ptr [rax+rax+00h]
0x1800d8f53  mov     qword ptr [rbx+18h], 0
0x1800d8f5b  mov     rcx, [rbx+8]; hEvent
0x1800d8f5f  call    cs:__imp_SetEvent
0x1800d8f66  nop     dword ptr [rax+rax+00h]
0x1800d8f6b  mov     rcx, [rbx+30h]; hHandle
0x1800d8f6f  test    rcx, rcx
0x1800d8f72  jz      short loc_1800D8F83
0x1800d8f74  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800d8f77  call    cs:__imp_WaitForSingleObject
0x1800d8f7e  nop     dword ptr [rax+rax+00h]
0x1800d8f83  mov     rcx, [rbx+30h]
0x1800d8f87  call    cs:__imp_FwCloseHandle
0x1800d8f8e  nop     dword ptr [rax+rax+00h]
0x1800d8f93  mov     rcx, [rbx+38h]
0x1800d8f97  call    cs:__imp_FwCloseHandle
0x1800d8f9e  nop     dword ptr [rax+rax+00h]
0x1800d8fa3  mov     rcx, [rbx+10h]
0x1800d8fa7  mov     qword ptr [rbx+38h], 0
0x1800d8faf  call    cs:__imp_FwCloseHandle
0x1800d8fb6  nop     dword ptr [rax+rax+00h]
0x1800d8fbb  mov     rcx, [rbx]
0x1800d8fbe  mov     qword ptr [rbx+10h], 0
0x1800d8fc6  call    cs:__imp_FwCloseHandle
0x1800d8fcd  nop     dword ptr [rax+rax+00h]
0x1800d8fd2  mov     rcx, [rbx+8]
0x1800d8fd6  mov     qword ptr [rbx], 0
0x1800d8fdd  call    cs:__imp_FwCloseHandle
0x1800d8fe4  nop     dword ptr [rax+rax+00h]
0x1800d8fe9  mov     rcx, rdi
0x1800d8fec  mov     qword ptr [rbx+8], 0
0x1800d8ff4  call    cs:__imp_FwCriticalSectionDestroy
0x1800d8ffb  nop     dword ptr [rax+rax+00h]
0x1800d9000  xor     edx, edx; Val
0x1800d9002  mov     r8d, 0A0h; Size
0x1800d9008  mov     rcx, rbx; void *
0x1800d900b  mov     rbx, [rsp+28h+arg_0]
0x1800d9010  add     rsp, 20h
0x1800d9014  pop     rdi
0x1800d9015  jmp     memset_0
```
