# SchedulerInitialize(void)

- ea: `0x180021470`
- end: `0x18002153d`
- name: `?SchedulerInitialize@@YAHXZ`
- size: `205`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001fbd0`

## callees

- `0x180008000`
- `0x1800210f8`
- `0x180021470`
- `0x1800215f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021513`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021513`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800214ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800214ea`

## string_xrefs

- `0x1800214a4`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`

## pseudocode

```c
SCHEDULER *SchedulerInitialize(void)
{
  SCHEDULER *result; // rax
  SCHEDULER *v1; // rdi
  signed __int64 v2; // rbx

  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x2000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\sched.cxx",
      0x58u,
      "SchedulerInitialize",
      "SchedulerInitialize: inits=%d, uninits=%d\n",
      cSchedInits[0]);
  ++*(_DWORD *)cSchedInits;
  result = SCHEDULER::CreateScheduler();
  v1 = result;
  if ( result )
  {
    EnterCriticalSection(&g_SchedulerCritSec);
    _InterlockedExchange(&TIMER::sm_lLastCookie, 0);
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)&g_pScheduler, (signed __int64)v1, 0);
    LeaveCriticalSection(&g_SchedulerCritSec);
    if ( v2 )
      SCHEDULER::Terminate(v1);
    return (SCHEDULER *)1;
  }
  return result;
}

```

## disassembly

```asm
0x180021470  mov     [rsp+arg_0], rbx
0x180021475  push    rdi
0x180021476  sub     rsp, 40h
0x18002147a  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180021480  test    al, 3
0x180021482  setnz   cl
0x180021485  bt      eax, 19h
0x180021489  setb    al
0x18002148c  test    al, cl
0x18002148e  jz      short loc_1800214D0
0x180021490  mov     eax, cs:?cSchedUninits@@3KA; ulong cSchedUninits
0x180021496  lea     r9, aScheduleriniti_1; "SchedulerInitialize"
0x18002149d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800214a4  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800214ab  mov     [rsp+48h+var_18], eax
0x1800214af  mov     r8d, 58h ; 'X'; unsigned int
0x1800214b5  mov     eax, cs:?cSchedInits@@3KA; ulong cSchedInits
0x1800214bb  mov     dword ptr [rsp+48h+var_20], eax; char
0x1800214bf  lea     rax, aScheduleriniti_0; "SchedulerInitialize: inits=%d, uninits="...
0x1800214c6  mov     [rsp+48h+var_28], rax; char *
0x1800214cb  call    PuDbgPrint
0x1800214d0  inc     cs:?cSchedInits@@3KA; ulong cSchedInits
0x1800214d6  call    ?CreateScheduler@SCHEDULER@@SAPEAV1@XZ; SCHEDULER::CreateScheduler(void)
0x1800214db  mov     rdi, rax
0x1800214de  test    rax, rax
0x1800214e1  jz      short loc_180021531
0x1800214e3  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800214ea  call    cs:__imp_EnterCriticalSection
0x1800214f1  nop     dword ptr [rax+rax+00h]
0x1800214f6  xor     eax, eax
0x1800214f8  lock cmpxchg cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, rdi; SCHEDULER * g_pScheduler
0x180021501  xor     edx, edx
0x180021503  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002150a  xchg    edx, cs:?sm_lLastCookie@TIMER@@0JA; long TIMER::sm_lLastCookie
0x180021510  mov     rbx, rax
0x180021513  call    cs:__imp_LeaveCriticalSection
0x18002151a  nop     dword ptr [rax+rax+00h]
0x18002151f  test    rbx, rbx
0x180021522  jz      short loc_18002152C
0x180021524  mov     rcx, rdi; this
0x180021527  call    ?Terminate@SCHEDULER@@QEAAXXZ; SCHEDULER::Terminate(void)
0x18002152c  mov     eax, 1
0x180021531  mov     rbx, [rsp+48h+arg_0]
0x180021536  add     rsp, 40h
0x18002153a  pop     rdi
0x18002153b  retn
```
