# SchedulerTerminate(void)

- ea: `0x180021550`
- end: `0x1800215ed`
- name: `?SchedulerTerminate@@YAXXZ`
- size: `157`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fda0`

## callees

- `0x180008000`
- `0x180021550`
- `0x1800215f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800215e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215b1`

## string_xrefs

- `0x18002157e`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`

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
0x180021550  sub     rsp, 48h
0x180021554  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002155a  test    al, 3
0x18002155c  setnz   cl
0x18002155f  bt      eax, 19h
0x180021563  setb    al
0x180021566  test    al, cl
0x180021568  jz      short loc_1800215AA
0x18002156a  mov     eax, cs:?cSchedUninits@@3KA; ulong cSchedUninits
0x180021570  lea     r9, aSchedulertermi_0; "SchedulerTerminate"
0x180021577  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002157e  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180021585  mov     [rsp+48h+var_18], eax
0x180021589  mov     r8d, 8Bh; unsigned int
0x18002158f  mov     eax, cs:?cSchedInits@@3KA; ulong cSchedInits
0x180021595  mov     dword ptr [rsp+48h+var_20], eax; char
0x180021599  lea     rax, aSchedulertermi_1; "SchedulerTerminate: inits=%d, uninits=%"...
0x1800215a0  mov     [rsp+48h+var_28], rax; char *
0x1800215a5  call    PuDbgPrint
0x1800215aa  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800215b1  call    cs:__imp_EnterCriticalSection
0x1800215b8  nop     dword ptr [rax+rax+00h]
0x1800215bd  xor     ecx, ecx
0x1800215bf  xchg    rcx, cs:?g_pScheduler@@3PEAVSCHEDULER@@EA; this
0x1800215c6  inc     cs:?cSchedUninits@@3KA; ulong cSchedUninits
0x1800215cc  test    rcx, rcx
0x1800215cf  jz      short loc_1800215D6
0x1800215d1  call    ?Terminate@SCHEDULER@@QEAAXXZ; SCHEDULER::Terminate(void)
0x1800215d6  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_SchedulerCritSec
0x1800215dd  add     rsp, 48h
0x1800215e1  jmp     cs:__imp_LeaveCriticalSection
```
