# RemoveWorkItem(ulong)

- ea: `0x180021240`
- end: `0x180021366`
- name: `?RemoveWorkItem@@YAHK@Z`
- size: `294`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800216c0`

## callees

- `0x180008000`
- `0x180017dac`
- `0x1800211d8`
- `0x180021240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021257`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002134b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021257`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002134b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800212d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800212d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021324`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800212b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800212b7`

## string_xrefs

- `0x1800212a4`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`
- `0x180021287`: `RemoveWorkItem: cookie=%d\n`
- `0x180021292`: `RemoveWorkItem`

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
0x180021240  push    rbx
0x180021242  sub     rsp, 30h
0x180021246  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x18002124e  mov     ebx, ecx
0x180021250  jnz     short loc_18002126A
0x180021252  mov     ecx, 15h; dwErrCode
0x180021257  call    cs:__imp_SetLastError
0x18002125e  nop     dword ptr [rax+rax+00h]
0x180021263  xor     eax, eax
0x180021265  jmp     loc_18002135F
0x18002126a  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180021270  test    al, 3
0x180021272  setnz   cl
0x180021275  bt      eax, 19h
0x180021279  setb    al
0x18002127c  test    al, cl
0x18002127e  jz      short loc_1800212B0
0x180021280  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180021287  lea     rax, aRemoveworkitem_1; "RemoveWorkItem: cookie=%d\n"
0x18002128e  mov     dword ptr [rsp+38h+var_10], ebx; char
0x180021292  lea     r9, aRemoveworkitem_0; "RemoveWorkItem"
0x180021299  mov     r8d, 19Eh; unsigned int
0x18002129f  mov     [rsp+38h+var_18], rax; char *
0x1800212a4  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800212ab  call    PuDbgPrint
0x1800212b0  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800212b7  call    cs:__imp_EnterCriticalSection
0x1800212be  nop     dword ptr [rax+rax+00h]
0x1800212c3  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x1800212cb  jnz     short loc_1800212E2
0x1800212cd  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800212d4  call    cs:__imp_LeaveCriticalSection
0x1800212db  nop     dword ptr [rax+rax+00h]
0x1800212e0  jmp     short loc_180021263
0x1800212e2  mov     ecx, ebx; unsigned int
0x1800212e4  call    ?FindTimerNoLock@@YAPEAVTIMER@@K@Z; FindTimerNoLock(ulong)
0x1800212e9  mov     rbx, rax
0x1800212ec  test    rax, rax
0x1800212ef  jz      short loc_18002131D
0x1800212f1  add     rax, 40h ; '@'
0x1800212f5  mov     rcx, [rax]
0x1800212f8  cmp     [rcx+8], rax
0x1800212fc  jnz     short loc_18002133F
0x1800212fe  mov     rdx, [rax+8]
0x180021302  cmp     [rdx], rax
0x180021305  jnz     short loc_18002133F
0x180021307  mov     [rdx], rcx
0x18002130a  mov     [rcx+8], rdx
0x18002130e  mov     qword ptr [rax], 0
0x180021315  mov     qword ptr [rbx+48h], 0
0x18002131d  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021324  call    cs:__imp_LeaveCriticalSection
0x18002132b  nop     dword ptr [rax+rax+00h]
0x180021330  test    rbx, rbx
0x180021333  jz      short loc_180021346
0x180021335  mov     rcx, rbx; this
0x180021338  call    ?Terminate@TIMER@@QEAAXXZ; TIMER::Terminate(void)
0x18002133d  jmp     short loc_180021357
0x18002133f  mov     ecx, 3
0x180021344  int     29h; Win8: RtlFailFast(ecx)
0x180021346  mov     ecx, 490h; dwErrCode
0x18002134b  call    cs:__imp_SetLastError
0x180021352  nop     dword ptr [rax+rax+00h]
0x180021357  xor     eax, eax
0x180021359  test    rbx, rbx
0x18002135c  setnz   al
0x18002135f  add     rsp, 30h
0x180021363  pop     rbx
0x180021364  retn
```
