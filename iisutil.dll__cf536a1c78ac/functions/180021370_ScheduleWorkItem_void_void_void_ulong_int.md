# ScheduleWorkItem(void (*)(void *),void *,ulong,int)

- ea: `0x180021370`
- end: `0x18002145c`
- name: `?ScheduleWorkItem@@YAKP6AXPEAX@Z0KH@Z`
- size: `236`
- prototype: `unsigned int __fastcall(void (*)(void *), void *, unsigned int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008000`
- `0x1800176f4`
- `0x180021370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021444`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800213fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800213fc`

## string_xrefs

- `0x1800213d0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`
- `0x1800213b6`: `ScheduleWorkItem: callback=%p context=%p time=%d periodic=%d Com=%d\n`

## pseudocode

```c
__int64 __fastcall ScheduleWorkItem(void (*a1)(void *), void *a2, DWORD a3, int a4)
{
  unsigned int v9; // ebx

  if ( !g_pScheduler )
    return 21;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x2000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\sched.cxx",
      0xCCu,
      "ScheduleWorkItem",
      "ScheduleWorkItem: callback=%p context=%p time=%d periodic=%d Com=%d\n",
      (char)a1);
  EnterCriticalSection(&g_SchedulerCritSec);
  if ( g_pScheduler )
    v9 = TIMER::Create(g_pScheduler, a1, a2, a3, a4, 1, 0);
  else
    v9 = 21;
  LeaveCriticalSection(&g_SchedulerCritSec);
  return v9;
}

```

## disassembly

```asm
0x180021370  push    rbx
0x180021372  push    rbp
0x180021373  push    rsi
0x180021374  push    rdi
0x180021375  sub     rsp, 58h
0x180021379  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x180021381  mov     ebx, r9d
0x180021384  mov     edi, r8d
0x180021387  mov     rsi, rdx
0x18002138a  mov     rbp, rcx
0x18002138d  jnz     short loc_180021399
0x18002138f  mov     eax, 15h
0x180021394  jmp     loc_180021452
0x180021399  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002139f  test    al, 3
0x1800213a1  setnz   cl
0x1800213a4  bt      eax, 19h
0x1800213a8  setb    al
0x1800213ab  test    al, cl
0x1800213ad  jz      short loc_1800213F5
0x1800213af  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800213b6  lea     rax, aScheduleworkit_0; "ScheduleWorkItem: callback=%p context=%"...
0x1800213bd  mov     [rsp+78h+var_30], 1
0x1800213c5  lea     r9, aScheduleworkit_1; "ScheduleWorkItem"
0x1800213cc  mov     [rsp+78h+var_38], ebx
0x1800213d0  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800213d7  mov     [rsp+78h+var_40], edi
0x1800213db  mov     r8d, 0CCh; unsigned int
0x1800213e1  mov     qword ptr [rsp+78h+var_48], rsi
0x1800213e6  mov     qword ptr [rsp+78h+var_50], rbp; char
0x1800213eb  mov     [rsp+78h+var_58], rax; char *
0x1800213f0  call    PuDbgPrint
0x1800213f5  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800213fc  call    cs:__imp_EnterCriticalSection
0x180021403  nop     dword ptr [rax+rax+00h]
0x180021408  mov     rcx, cs:?g_pScheduler@@3PEAVSCHEDULER@@EA; struct SCHEDULER *
0x18002140f  test    rcx, rcx
0x180021412  jnz     short loc_180021419
0x180021414  lea     ebx, [rcx+15h]
0x180021417  jmp     short loc_18002143D
0x180021419  mov     [rsp+78h+var_48], 0; unsigned int
0x180021421  mov     r9d, edi; unsigned int
0x180021424  mov     dword ptr [rsp+78h+var_50], 1; int
0x18002142c  mov     r8, rsi; void *
0x18002142f  mov     rdx, rbp; void (*)(void *)
0x180021432  mov     dword ptr [rsp+78h+var_58], ebx; int
0x180021436  call    ?Create@TIMER@@SAKPEAVSCHEDULER@@P6AXPEAX@Z1KHHK@Z; TIMER::Create(SCHEDULER *,void (*)(void *),void *,ulong,int,int,ulong)
0x18002143b  mov     ebx, eax
0x18002143d  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021444  call    cs:__imp_LeaveCriticalSection
0x18002144b  nop     dword ptr [rax+rax+00h]
0x180021450  mov     eax, ebx
0x180021452  add     rsp, 58h
0x180021456  pop     rdi
0x180021457  pop     rsi
0x180021458  pop     rbp
0x180021459  pop     rbx
0x18002145a  retn
```
