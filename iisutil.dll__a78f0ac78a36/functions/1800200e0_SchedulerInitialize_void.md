# SchedulerInitialize(void)

- ea: `0x1800200e0`
- end: `0x1800201a0`
- name: `?SchedulerInitialize@@YAHXZ`
- size: `192`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ea00`

## callees

- `0x180007300`
- `0x18001fda4`
- `0x1800200e0`
- `0x180020248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002017d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002017d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002015a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002015a`

## string_xrefs

- `0x180020114`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`

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
0x1800200e0  mov     [rsp+arg_0], rbx
0x1800200e5  push    rdi
0x1800200e6  sub     rsp, 40h
0x1800200ea  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800200f0  test    al, 3
0x1800200f2  setnz   cl
0x1800200f5  bt      eax, 19h
0x1800200f9  setb    al
0x1800200fc  test    al, cl
0x1800200fe  jz      short loc_180020140
0x180020100  mov     eax, cs:?cSchedUninits@@3KA; ulong cSchedUninits
0x180020106  lea     r9, aScheduleriniti_1; "SchedulerInitialize"
0x18002010d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180020114  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002011b  mov     [rsp+48h+var_18], eax
0x18002011f  mov     r8d, 58h ; 'X'; unsigned int
0x180020125  mov     eax, cs:?cSchedInits@@3KA; ulong cSchedInits
0x18002012b  mov     dword ptr [rsp+48h+var_20], eax; char
0x18002012f  lea     rax, aScheduleriniti_0; "SchedulerInitialize: inits=%d, uninits="...
0x180020136  mov     [rsp+48h+var_28], rax; char *
0x18002013b  call    PuDbgPrint
0x180020140  inc     cs:?cSchedInits@@3KA; ulong cSchedInits
0x180020146  call    ?CreateScheduler@SCHEDULER@@SAPEAV1@XZ; SCHEDULER::CreateScheduler(void)
0x18002014b  mov     rdi, rax
0x18002014e  test    rax, rax
0x180020151  jz      short loc_180020195
0x180020153  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002015a  call    cs:__imp_EnterCriticalSection
0x180020160  xor     eax, eax
0x180020162  lock cmpxchg cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, rdi; SCHEDULER * g_pScheduler
0x18002016b  xor     edx, edx
0x18002016d  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020174  xchg    edx, cs:?sm_lLastCookie@TIMER@@0JA; long TIMER::sm_lLastCookie
0x18002017a  mov     rbx, rax
0x18002017d  call    cs:__imp_LeaveCriticalSection
0x180020183  test    rbx, rbx
0x180020186  jz      short loc_180020190
0x180020188  mov     rcx, rdi; this
0x18002018b  call    ?Terminate@SCHEDULER@@QEAAXXZ; SCHEDULER::Terminate(void)
0x180020190  mov     eax, 1
0x180020195  mov     rbx, [rsp+48h+arg_0]
0x18002019a  add     rsp, 40h
0x18002019e  pop     rdi
0x18002019f  retn
```
