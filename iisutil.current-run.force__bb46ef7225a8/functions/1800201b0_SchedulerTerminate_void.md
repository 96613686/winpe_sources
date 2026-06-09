# SchedulerTerminate(void)

- ea: `0x1800201b0`
- end: `0x180020242`
- name: `?SchedulerTerminate@@YAXXZ`
- size: `146`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001eba0`

## callees

- `0x180007300`
- `0x1800201b0`
- `0x180020248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002023b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020211`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020211`

## string_xrefs

- `0x1800201de`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`

## pseudocode

```c
void SchedulerTerminate(void)
{
  SCHEDULER *v0; // rcx

  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x2000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\sched.cxx",
      0x8Bu,
      "SchedulerTerminate",
      "SchedulerTerminate: inits=%d, uninits=%d\n",
      cSchedInits[0]);
  EnterCriticalSection(&g_SchedulerCritSec);
  v0 = (SCHEDULER *)_InterlockedExchange64((volatile __int64 *)&g_pScheduler, 0);
  ++cSchedUninits;
  if ( v0 )
    SCHEDULER::Terminate(v0);
  LeaveCriticalSection(&g_SchedulerCritSec);
}

```

## disassembly

```asm
0x1800201b0  sub     rsp, 48h
0x1800201b4  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800201ba  test    al, 3
0x1800201bc  setnz   cl
0x1800201bf  bt      eax, 19h
0x1800201c3  setb    al
0x1800201c6  test    al, cl
0x1800201c8  jz      short loc_18002020A
0x1800201ca  mov     eax, cs:?cSchedUninits@@3KA; ulong cSchedUninits
0x1800201d0  lea     r9, aSchedulertermi_0; "SchedulerTerminate"
0x1800201d7  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800201de  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800201e5  mov     [rsp+48h+var_18], eax
0x1800201e9  mov     r8d, 8Bh; unsigned int
0x1800201ef  mov     eax, cs:?cSchedInits@@3KA; ulong cSchedInits
0x1800201f5  mov     dword ptr [rsp+48h+var_20], eax; char
0x1800201f9  lea     rax, aSchedulertermi_1; "SchedulerTerminate: inits=%d, uninits=%"...
0x180020200  mov     [rsp+48h+var_28], rax; char *
0x180020205  call    PuDbgPrint
0x18002020a  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020211  call    cs:__imp_EnterCriticalSection
0x180020217  xor     ecx, ecx
0x180020219  xchg    rcx, cs:?g_pScheduler@@3PEAVSCHEDULER@@EA; this
0x180020220  inc     cs:?cSchedUninits@@3KA; ulong cSchedUninits
0x180020226  test    rcx, rcx
0x180020229  jz      short loc_180020230
0x18002022b  call    ?Terminate@SCHEDULER@@QEAAXXZ; SCHEDULER::Terminate(void)
0x180020230  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_SchedulerCritSec
0x180020237  add     rsp, 48h
0x18002023b  jmp     cs:__imp_LeaveCriticalSection
```
