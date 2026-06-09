# RemoveWorkItem(ulong)

- ea: `0x18001fee0`
- end: `0x18001ffe7`
- name: `?RemoveWorkItem@@YAHK@Z`
- size: `263`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800202f0`

## callees

- `0x180007300`
- `0x1800170e8`
- `0x18001fe74`
- `0x18001fee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fef7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ffd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fef7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ffd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ff68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ffb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ff68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ffb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ff51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ff51`

## string_xrefs

- `0x18001ff3e`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`
- `0x18001ff21`: `RemoveWorkItem: cookie=%d\n`
- `0x18001ff2c`: `RemoveWorkItem`

## pseudocode

```c
_BOOL8 __fastcall RemoveWorkItem(unsigned int a1)
{
  struct TIMER *TimerNoLock; // rax
  TIMER *v4; // rbx
  _QWORD *v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rdx

  if ( !g_pScheduler )
  {
    SetLastError(0x15u);
    return 0;
  }
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x2000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\sched.cxx",
      0x19Eu,
      "RemoveWorkItem",
      "RemoveWorkItem: cookie=%d\n",
      a1);
  EnterCriticalSection(&g_SchedulerCritSec);
  if ( !g_pScheduler )
  {
    LeaveCriticalSection(&g_SchedulerCritSec);
    return 0;
  }
  TimerNoLock = FindTimerNoLock(a1);
  v4 = TimerNoLock;
  if ( TimerNoLock )
  {
    v5 = (_QWORD *)((char *)TimerNoLock + 64);
    v6 = *v5;
    if ( *(_QWORD **)(*v5 + 8LL) != v5 || (v7 = (_QWORD *)v5[1], (_QWORD *)*v7 != v5) )
      __fastfail(3u);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    *v5 = 0;
    *((_QWORD *)v4 + 9) = 0;
  }
  LeaveCriticalSection(&g_SchedulerCritSec);
  if ( v4 )
    TIMER::Terminate(v4);
  else
    SetLastError(0x490u);
  return v4 != 0;
}

```

## disassembly

```asm
0x18001fee0  push    rbx
0x18001fee2  sub     rsp, 30h
0x18001fee6  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x18001feee  mov     ebx, ecx
0x18001fef0  jnz     short loc_18001FF04
0x18001fef2  mov     ecx, 15h; dwErrCode
0x18001fef7  call    cs:__imp_SetLastError
0x18001fefd  xor     eax, eax
0x18001feff  jmp     loc_18001FFE1
0x18001ff04  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18001ff0a  test    al, 3
0x18001ff0c  setnz   cl
0x18001ff0f  bt      eax, 19h
0x18001ff13  setb    al
0x18001ff16  test    al, cl
0x18001ff18  jz      short loc_18001FF4A
0x18001ff1a  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001ff21  lea     rax, aRemoveworkitem_1; "RemoveWorkItem: cookie=%d\n"
0x18001ff28  mov     dword ptr [rsp+38h+var_10], ebx; char
0x18001ff2c  lea     r9, aRemoveworkitem_0; "RemoveWorkItem"
0x18001ff33  mov     r8d, 19Eh; unsigned int
0x18001ff39  mov     [rsp+38h+var_18], rax; char *
0x18001ff3e  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001ff45  call    PuDbgPrint
0x18001ff4a  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ff51  call    cs:__imp_EnterCriticalSection
0x18001ff57  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x18001ff5f  jnz     short loc_18001FF70
0x18001ff61  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ff68  call    cs:__imp_LeaveCriticalSection
0x18001ff6e  jmp     short loc_18001FEFD
0x18001ff70  mov     ecx, ebx; unsigned int
0x18001ff72  call    ?FindTimerNoLock@@YAPEAVTIMER@@K@Z; FindTimerNoLock(ulong)
0x18001ff77  mov     rbx, rax
0x18001ff7a  test    rax, rax
0x18001ff7d  jz      short loc_18001FFAB
0x18001ff7f  add     rax, 40h ; '@'
0x18001ff83  mov     rcx, [rax]
0x18001ff86  cmp     [rcx+8], rax
0x18001ff8a  jnz     short loc_18001FFC7
0x18001ff8c  mov     rdx, [rax+8]
0x18001ff90  cmp     [rdx], rax
0x18001ff93  jnz     short loc_18001FFC7
0x18001ff95  mov     [rdx], rcx
0x18001ff98  mov     [rcx+8], rdx
0x18001ff9c  mov     qword ptr [rax], 0
0x18001ffa3  mov     qword ptr [rbx+48h], 0
0x18001ffab  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ffb2  call    cs:__imp_LeaveCriticalSection
0x18001ffb8  test    rbx, rbx
0x18001ffbb  jz      short loc_18001FFCE
0x18001ffbd  mov     rcx, rbx; this
0x18001ffc0  call    ?Terminate@TIMER@@QEAAXXZ; TIMER::Terminate(void)
0x18001ffc5  jmp     short loc_18001FFD9
0x18001ffc7  mov     ecx, 3
0x18001ffcc  int     29h; Win8: RtlFailFast(ecx)
0x18001ffce  mov     ecx, 490h; dwErrCode
0x18001ffd3  call    cs:__imp_SetLastError
0x18001ffd9  xor     eax, eax
0x18001ffdb  test    rbx, rbx
0x18001ffde  setnz   al
0x18001ffe1  add     rsp, 30h
0x18001ffe5  pop     rbx
0x18001ffe6  retn
```
