# ScheduleAdjustTime(ulong,ulong)

- ea: `0x180016940`
- end: `0x180016a88`
- name: `?ScheduleAdjustTime@@YAKKK@Z`
- size: `328`
- prototype: `unsigned int __fastcall(char, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180007300`
- `0x180016940`
- `0x180016a90`
- `0x1800170e8`
- `0x18001fe74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800169d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016a55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800169d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016a55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800169ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800169ba`

## string_xrefs

- `0x180016988`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`

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
0x180016940  mov     [rsp+arg_0], rbx
0x180016945  mov     [rsp+arg_8], rsi
0x18001694a  push    rdi
0x18001694b  sub     rsp, 40h
0x18001694f  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180016955  mov     esi, edx
0x180016957  test    al, 3
0x180016959  mov     ebx, ecx
0x18001695b  setnz   r8b
0x18001695f  bt      eax, 19h
0x180016963  setb    al
0x180016966  test    al, r8b
0x180016969  jz      short loc_18001699F
0x18001696b  mov     [rsp+48h+var_18], edx
0x18001696f  lea     rax, aScheduleadjust_1; "ScheduleAdjustTime: cookie=%d time=%d\n"
0x180016976  mov     dword ptr [rsp+48h+var_20], ecx; char
0x18001697a  lea     r9, aScheduleadjust_0; "ScheduleAdjustTime"
0x180016981  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180016988  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001698f  mov     r8d, 1E8h; unsigned int
0x180016995  mov     [rsp+48h+var_28], rax; char *
0x18001699a  call    PuDbgPrint
0x18001699f  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x1800169a7  jnz     short loc_1800169B3
0x1800169a9  mov     eax, 15h
0x1800169ae  jmp     loc_180016A78
0x1800169b3  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800169ba  call    cs:__imp_EnterCriticalSection
0x1800169c0  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x1800169c8  jnz     short loc_1800169D9
0x1800169ca  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800169d1  call    cs:__imp_LeaveCriticalSection
0x1800169d7  jmp     short loc_1800169A9
0x1800169d9  mov     ecx, ebx; unsigned int
0x1800169db  mov     edi, 490h
0x1800169e0  call    ?FindTimerNoLock@@YAPEAVTIMER@@K@Z; FindTimerNoLock(ulong)
0x1800169e5  mov     rbx, rax
0x1800169e8  test    rax, rax
0x1800169eb  jz      short loc_180016A4E
0x1800169ed  add     rax, 40h ; '@'
0x1800169f1  mov     rcx, [rax]
0x1800169f4  cmp     [rcx+8], rax
0x1800169f8  jnz     short loc_180016A6C
0x1800169fa  mov     rdx, [rax+8]
0x1800169fe  cmp     [rdx], rax
0x180016a01  jnz     short loc_180016A6C
0x180016a03  mov     [rdx], rcx
0x180016a06  mov     r9d, esi; unsigned int
0x180016a09  mov     [rcx+8], rdx
0x180016a0d  mov     r8, [rbx+20h]; void *
0x180016a11  mov     rdx, [rbx+18h]; void (*)(void *)
0x180016a15  mov     rcx, [rbx+8]; struct SCHEDULER *
0x180016a19  mov     qword ptr [rax], 0
0x180016a20  mov     eax, [rbx+10h]
0x180016a23  mov     [rsp+48h+var_18], eax; unsigned int
0x180016a27  mov     eax, [rbx+2Ch]
0x180016a2a  mov     dword ptr [rsp+48h+var_20], eax; int
0x180016a2e  mov     eax, [rbx+28h]
0x180016a31  mov     dword ptr [rsp+48h+var_28], eax; int
0x180016a35  mov     qword ptr [rbx+48h], 0
0x180016a3d  call    ?Create@TIMER@@SAKPEAVSCHEDULER@@P6AXPEAX@Z1KHHK@Z; TIMER::Create(SCHEDULER *,void (*)(void *),void *,ulong,int,int,ulong)
0x180016a42  xor     ecx, ecx
0x180016a44  mov     edi, 8
0x180016a49  test    eax, eax
0x180016a4b  cmovnz  edi, ecx
0x180016a4e  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180016a55  call    cs:__imp_LeaveCriticalSection
0x180016a5b  test    rbx, rbx
0x180016a5e  jz      short loc_180016A73
0x180016a60  mov     rcx, rbx; this
0x180016a63  call    ?Terminate@TIMER@@QEAAXXZ; TIMER::Terminate(void)
0x180016a68  mov     eax, edi
0x180016a6a  jmp     short loc_180016A78
0x180016a6c  mov     ecx, 3
0x180016a71  int     29h; Win8: RtlFailFast(ecx)
0x180016a73  mov     eax, 490h
0x180016a78  mov     rbx, [rsp+48h+arg_0]
0x180016a7d  mov     rsi, [rsp+48h+arg_8]
0x180016a82  add     rsp, 40h
0x180016a86  pop     rdi
0x180016a87  retn
```
