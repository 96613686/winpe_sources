# ScheduleAdjustTime(ulong,ulong)

- ea: `0x180017590`
- end: `0x1800176eb`
- name: `?ScheduleAdjustTime@@YAKKK@Z`
- size: `347`
- prototype: `unsigned int __fastcall(char, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180008000`
- `0x180017590`
- `0x1800176f4`
- `0x180017dac`
- `0x1800211d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017627`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800176b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017627`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800176b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001760a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001760a`

## string_xrefs

- `0x1800175d8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`

## pseudocode

```c
__int64 __fastcall ScheduleAdjustTime(unsigned int a1, DWORD a2)
{
  unsigned int v5; // edi
  struct TIMER *TimerNoLock; // rax
  struct TIMER *v7; // rbx
  _QWORD *v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  void *v11; // r8
  void (*v12)(void *); // rdx
  struct SCHEDULER *v13; // rcx
  int v14; // [rsp+20h] [rbp-28h]
  int v15; // [rsp+28h] [rbp-20h]
  unsigned int v16; // [rsp+30h] [rbp-18h]

  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x2000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\sched.cxx",
      0x1E8u,
      "ScheduleAdjustTime",
      "ScheduleAdjustTime: cookie=%d time=%d\n",
      a1);
  if ( !g_pScheduler )
    return 21;
  EnterCriticalSection(&g_SchedulerCritSec);
  if ( !g_pScheduler )
  {
    LeaveCriticalSection(&g_SchedulerCritSec);
    return 21;
  }
  v5 = 1168;
  TimerNoLock = FindTimerNoLock(a1);
  v7 = TimerNoLock;
  if ( TimerNoLock )
  {
    v8 = (_QWORD *)((char *)TimerNoLock + 64);
    v9 = *v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 || (v10 = (_QWORD *)v8[1], (_QWORD *)*v10 != v8) )
      __fastfail(3u);
    *v10 = v9;
    *(_QWORD *)(v9 + 8) = v10;
    v11 = (void *)*((_QWORD *)v7 + 4);
    v12 = (void (*)(void *))*((_QWORD *)v7 + 3);
    v13 = (struct SCHEDULER *)*((_QWORD *)v7 + 1);
    *v8 = 0;
    v16 = *((_DWORD *)v7 + 4);
    v15 = *((_DWORD *)v7 + 11);
    v14 = *((_DWORD *)v7 + 10);
    *((_QWORD *)v7 + 9) = 0;
    v5 = 8;
    if ( (unsigned int)TIMER::Create(v13, v12, v11, a2, v14, v15, v16) )
      v5 = 0;
  }
  LeaveCriticalSection(&g_SchedulerCritSec);
  if ( !v7 )
    return 1168;
  TIMER::Terminate(v7);
  return v5;
}

```

## disassembly

```asm
0x180017590  mov     [rsp+arg_0], rbx
0x180017595  mov     [rsp+arg_8], rsi
0x18001759a  push    rdi
0x18001759b  sub     rsp, 40h
0x18001759f  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800175a5  mov     esi, edx
0x1800175a7  test    al, 3
0x1800175a9  mov     ebx, ecx
0x1800175ab  setnz   r8b
0x1800175af  bt      eax, 19h
0x1800175b3  setb    al
0x1800175b6  test    al, r8b
0x1800175b9  jz      short loc_1800175EF
0x1800175bb  mov     [rsp+48h+var_18], edx
0x1800175bf  lea     rax, aScheduleadjust_1; "ScheduleAdjustTime: cookie=%d time=%d\n"
0x1800175c6  mov     dword ptr [rsp+48h+var_20], ecx; char
0x1800175ca  lea     r9, aScheduleadjust_0; "ScheduleAdjustTime"
0x1800175d1  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800175d8  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800175df  mov     r8d, 1E8h; unsigned int
0x1800175e5  mov     [rsp+48h+var_28], rax; char *
0x1800175ea  call    PuDbgPrint
0x1800175ef  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x1800175f7  jnz     short loc_180017603
0x1800175f9  mov     eax, 15h
0x1800175fe  jmp     loc_1800176DA
0x180017603  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001760a  call    cs:__imp_EnterCriticalSection
0x180017611  nop     dword ptr [rax+rax+00h]
0x180017616  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x18001761e  jnz     short loc_180017635
0x180017620  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180017627  call    cs:__imp_LeaveCriticalSection
0x18001762e  nop     dword ptr [rax+rax+00h]
0x180017633  jmp     short loc_1800175F9
0x180017635  mov     ecx, ebx; unsigned int
0x180017637  mov     edi, 490h
0x18001763c  call    ?FindTimerNoLock@@YAPEAVTIMER@@K@Z; FindTimerNoLock(ulong)
0x180017641  mov     rbx, rax
0x180017644  test    rax, rax
0x180017647  jz      short loc_1800176AA
0x180017649  add     rax, 40h ; '@'
0x18001764d  mov     rcx, [rax]
0x180017650  cmp     [rcx+8], rax
0x180017654  jnz     short loc_1800176CE
0x180017656  mov     rdx, [rax+8]
0x18001765a  cmp     [rdx], rax
0x18001765d  jnz     short loc_1800176CE
0x18001765f  mov     [rdx], rcx
0x180017662  mov     r9d, esi; unsigned int
0x180017665  mov     [rcx+8], rdx
0x180017669  mov     r8, [rbx+20h]; void *
0x18001766d  mov     rdx, [rbx+18h]; void (*)(void *)
0x180017671  mov     rcx, [rbx+8]; struct SCHEDULER *
0x180017675  mov     qword ptr [rax], 0
0x18001767c  mov     eax, [rbx+10h]
0x18001767f  mov     [rsp+48h+var_18], eax; unsigned int
0x180017683  mov     eax, [rbx+2Ch]
0x180017686  mov     dword ptr [rsp+48h+var_20], eax; int
0x18001768a  mov     eax, [rbx+28h]
0x18001768d  mov     dword ptr [rsp+48h+var_28], eax; int
0x180017691  mov     qword ptr [rbx+48h], 0
0x180017699  call    ?Create@TIMER@@SAKPEAVSCHEDULER@@P6AXPEAX@Z1KHHK@Z; TIMER::Create(SCHEDULER *,void (*)(void *),void *,ulong,int,int,ulong)
0x18001769e  xor     ecx, ecx
0x1800176a0  mov     edi, 8
0x1800176a5  test    eax, eax
0x1800176a7  cmovnz  edi, ecx
0x1800176aa  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800176b1  call    cs:__imp_LeaveCriticalSection
0x1800176b8  nop     dword ptr [rax+rax+00h]
0x1800176bd  test    rbx, rbx
0x1800176c0  jz      short loc_1800176D5
0x1800176c2  mov     rcx, rbx; this
0x1800176c5  call    ?Terminate@TIMER@@QEAAXXZ; TIMER::Terminate(void)
0x1800176ca  mov     eax, edi
0x1800176cc  jmp     short loc_1800176DA
0x1800176ce  mov     ecx, 3
0x1800176d3  int     29h; Win8: RtlFailFast(ecx)
0x1800176d5  mov     eax, 490h
0x1800176da  mov     rbx, [rsp+48h+arg_0]
0x1800176df  mov     rsi, [rsp+48h+arg_8]
0x1800176e4  add     rsp, 40h
0x1800176e8  pop     rdi
0x1800176e9  retn
```
