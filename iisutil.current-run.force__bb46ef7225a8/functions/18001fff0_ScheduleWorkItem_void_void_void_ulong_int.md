# ScheduleWorkItem(void (*)(void *),void *,ulong,int)

- ea: `0x18001fff0`
- end: `0x1800200cf`
- name: `?ScheduleWorkItem@@YAKP6AXPEAX@Z0KH@Z`
- size: `223`
- prototype: `unsigned int __fastcall(void (*)(void *), void *, unsigned int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007300`
- `0x180016a90`
- `0x18001fff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800200be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800200be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002007c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002007c`

## string_xrefs

- `0x180020050`: `servercommon\inetsrv\iis\iisrearc\core\common\util\sched.cxx`
- `0x180020036`: `ScheduleWorkItem: callback=%p context=%p time=%d periodic=%d Com=%d\n`

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
0x18001fff0  push    rbx
0x18001fff2  push    rbp
0x18001fff3  push    rsi
0x18001fff4  push    rdi
0x18001fff5  sub     rsp, 58h
0x18001fff9  cmp     cs:?g_pScheduler@@3PEAVSCHEDULER@@EA, 0; SCHEDULER * g_pScheduler
0x180020001  mov     ebx, r9d
0x180020004  mov     edi, r8d
0x180020007  mov     rsi, rdx
0x18002000a  mov     rbp, rcx
0x18002000d  jnz     short loc_180020019
0x18002000f  mov     eax, 15h
0x180020014  jmp     loc_1800200C6
0x180020019  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002001f  test    al, 3
0x180020021  setnz   cl
0x180020024  bt      eax, 19h
0x180020028  setb    al
0x18002002b  test    al, cl
0x18002002d  jz      short loc_180020075
0x18002002f  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180020036  lea     rax, aScheduleworkit_0; "ScheduleWorkItem: callback=%p context=%"...
0x18002003d  mov     [rsp+78h+var_30], 1
0x180020045  lea     r9, aScheduleworkit_1; "ScheduleWorkItem"
0x18002004c  mov     [rsp+78h+var_38], ebx
0x180020050  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180020057  mov     [rsp+78h+var_40], edi
0x18002005b  mov     r8d, 0CCh; unsigned int
0x180020061  mov     qword ptr [rsp+78h+var_48], rsi
0x180020066  mov     qword ptr [rsp+78h+var_50], rbp; char
0x18002006b  mov     [rsp+78h+var_58], rax; char *
0x180020070  call    PuDbgPrint
0x180020075  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002007c  call    cs:__imp_EnterCriticalSection
0x180020082  mov     rcx, cs:?g_pScheduler@@3PEAVSCHEDULER@@EA; struct SCHEDULER *
0x180020089  test    rcx, rcx
0x18002008c  jnz     short loc_180020093
0x18002008e  lea     ebx, [rcx+15h]
0x180020091  jmp     short loc_1800200B7
0x180020093  mov     [rsp+78h+var_48], 0; unsigned int
0x18002009b  mov     r9d, edi; unsigned int
0x18002009e  mov     dword ptr [rsp+78h+var_50], 1; int
0x1800200a6  mov     r8, rsi; void *
0x1800200a9  mov     rdx, rbp; void (*)(void *)
0x1800200ac  mov     dword ptr [rsp+78h+var_58], ebx; int
0x1800200b0  call    ?Create@TIMER@@SAKPEAVSCHEDULER@@P6AXPEAX@Z1KHHK@Z; TIMER::Create(SCHEDULER *,void (*)(void *),void *,ulong,int,int,ulong)
0x1800200b5  mov     ebx, eax
0x1800200b7  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800200be  call    cs:__imp_LeaveCriticalSection
0x1800200c4  mov     eax, ebx
0x1800200c6  add     rsp, 58h
0x1800200ca  pop     rdi
0x1800200cb  pop     rsi
0x1800200cc  pop     rbp
0x1800200cd  pop     rbx
0x1800200ce  retn
```
