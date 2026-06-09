# WfpStartTimer

- ea: `0x180049cb0`
- end: `0x180049de1`
- name: `WfpStartTimer`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180040e80`
- `0x180040f9c`

## callees

- `0x1800034e0`
- `0x180007e38`
- `0x180049cb0`
- `0x180049de8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049ce5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049db4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049ce5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049db4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049cce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049d9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049cce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049d9e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180049d2a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180049d2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180049d8f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180049d8f`

## string_xrefs

- `0x180049d4d`: `CreateThreadpoolTimer`

## pseudocode

```c
__int64 __fastcall WfpStartTimer(__int64 a1, __int64 a2, __int64 a3, struct _RTL_CRITICAL_SECTION *a4, PVOID pv)
{
  __int64 v6; // rdi
  _OWORD *v7; // rsi
  int v8; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  DWORD LastError; // eax
  __int64 v11; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+18h] BYREF

  pftDueTime = 0;
  v6 = 0;
  EnterCriticalSection(a4);
  v7 = pv;
  v8 = *((_DWORD *)pv + 6);
  LeaveCriticalSection(a4);
  if ( v8 == 1 )
  {
    v6 = WfpStopTimer(a4, (__int64)v7);
    if ( v6 )
      goto LABEL_7;
  }
  *v7 = 0;
  v7[1] = 0;
  *((_QWORD *)v7 + 4) = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(WfpUserModeTimerInternalCallback, v7, 0);
  *(_QWORD *)v7 = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    *((_QWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 1) = FeCalloutWatchdogTimerCallback;
    *((_QWORD *)v7 + 4) = a4;
    pftDueTime = (struct _FILETIME)-280000000LL;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0x5DCu);
    EnterCriticalSection(a4);
    *((_DWORD *)v7 + 6) = 1;
    LeaveCriticalSection(a4);
  }
  else
  {
    LastError = GetLastError();
    v6 = WfpReportSysErrorAsWinError(v11, "CreateThreadpoolTimer", LastError);
  }
  if ( v6 )
LABEL_7:
    WfpReportError(v6, "WfpStartTimer");
  return v6;
}

```

## disassembly

```asm
0x180049cb0  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r8
0x180049cb5  push    rbx
0x180049cb6  push    rbp
0x180049cb7  push    rsi
0x180049cb8  push    rdi
0x180049cb9  sub     rsp, 28h
0x180049cbd  mov     rcx, r9; lpCriticalSection
0x180049cc0  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0
0x180049cc9  mov     rbp, r9
0x180049ccc  xor     edi, edi
0x180049cce  call    cs:__imp_EnterCriticalSection
0x180049cd5  nop     dword ptr [rax+rax+00h]
0x180049cda  mov     rsi, [rsp+48h+pv]
0x180049cdf  mov     rcx, rbp; lpCriticalSection
0x180049ce2  mov     ebx, [rsi+18h]
0x180049ce5  call    cs:__imp_LeaveCriticalSection
0x180049cec  nop     dword ptr [rax+rax+00h]
0x180049cf1  cmp     ebx, 1
0x180049cf4  jnz     short loc_180049D0D
0x180049cf6  mov     rdx, rsi
0x180049cf9  mov     rcx, rbp; lpCriticalSection
0x180049cfc  call    WfpStopTimer
0x180049d01  mov     rdi, rax
0x180049d04  test    rax, rax
0x180049d07  jnz     loc_180049DC5
0x180049d0d  xorps   xmm0, xmm0
0x180049d10  lea     rcx, WfpUserModeTimerInternalCallback; pfnti
0x180049d17  movups  xmmword ptr [rsi], xmm0
0x180049d1a  xor     eax, eax
0x180049d1c  xor     r8d, r8d; pcbe
0x180049d1f  movups  xmmword ptr [rsi+10h], xmm0
0x180049d23  mov     rdx, rsi; pv
0x180049d26  mov     [rsi+20h], rax
0x180049d2a  call    cs:__imp_CreateThreadpoolTimer
0x180049d31  nop     dword ptr [rax+rax+00h]
0x180049d36  mov     [rsi], rax
0x180049d39  test    rax, rax
0x180049d3c  jnz     short loc_180049D5E
0x180049d3e  call    cs:__imp_GetLastError
0x180049d45  nop     dword ptr [rax+rax+00h]
0x180049d4a  mov     r8d, eax
0x180049d4d  lea     rdx, aCreatethreadpo; "CreateThreadpoolTimer"
0x180049d54  call    WfpReportSysErrorAsWinError
0x180049d59  mov     rdi, rax
0x180049d5c  jmp     short loc_180049DC0
0x180049d5e  lea     rcx, FeCalloutWatchdogTimerCallback
0x180049d65  mov     qword ptr [rsi+10h], 0
0x180049d6d  mov     [rsi+8], rcx
0x180049d71  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180049d76  mov     rcx, rax; pti
0x180049d79  mov     [rsi+20h], rbp
0x180049d7d  mov     r9d, 5DCh; msWindowLength
0x180049d83  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFEF4F8A00h
0x180049d8c  xor     r8d, r8d; msPeriod
0x180049d8f  call    cs:__imp_SetThreadpoolTimer
0x180049d96  nop     dword ptr [rax+rax+00h]
0x180049d9b  mov     rcx, rbp; lpCriticalSection
0x180049d9e  call    cs:__imp_EnterCriticalSection
0x180049da5  nop     dword ptr [rax+rax+00h]
0x180049daa  mov     rcx, rbp; lpCriticalSection
0x180049dad  mov     dword ptr [rsi+18h], 1
0x180049db4  call    cs:__imp_LeaveCriticalSection
0x180049dbb  nop     dword ptr [rax+rax+00h]
0x180049dc0  test    rdi, rdi
0x180049dc3  jz      short loc_180049DD4
0x180049dc5  lea     rdx, aWfpstarttimer; "WfpStartTimer"
0x180049dcc  mov     rcx, rdi
0x180049dcf  call    WfpReportError
0x180049dd4  mov     rax, rdi
0x180049dd7  add     rsp, 28h
0x180049ddb  pop     rdi
0x180049ddc  pop     rsi
0x180049ddd  pop     rbp
0x180049dde  pop     rbx
0x180049ddf  retn
```
