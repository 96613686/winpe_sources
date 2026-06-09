# ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))

- ea: `0x18000420c`
- end: `0x180004304`
- name: `??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z`
- size: `248`
- prototype: `ScopedWatchdogTimer *__fastcall(PVOID Context, __int64, void (*)(void))`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005820`
- `0x180011ad0`

## callees

- `0x18000420c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004255`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000421c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000421c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000423c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000423c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800042b9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800042b9`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800042f0`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800042f0`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180004294`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180004294`

## pseudocode

```c
ScopedWatchdogTimer *__fastcall ScopedWatchdogTimer::ScopedWatchdogTimer(PVOID Context, __int64 a2, void (*a3)(void))
{
  HANDLE EventW; // rax
  signed int v5; // eax
  signed int LastError; // eax

  *(_QWORD *)Context = a3;
  *((_DWORD *)Context + 2) = GetCurrentThreadId();
  *((_DWORD *)Context + 3) = 30000;
  *((_QWORD *)Context + 2) = 0;
  *((_QWORD *)Context + 3) = 0;
  if ( !IsDebuggerPresent() )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)Context + 3) = EventW;
    if ( EventW )
    {
      if ( !RegisterWaitForSingleObject(
              (PHANDLE)Context + 2,
              EventW,
              ScopedWatchdogTimer::WaitCallback,
              Context,
              *((_DWORD *)Context + 3),
              0) )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          LastError = -2143748092;
        }
        ZTraceReportIgnore(LastError, "ScopedWatchdogTimer::ScopedWatchdogTimer", 49, Context);
      }
    }
    else
    {
      v5 = GetLastError();
      if ( v5 )
      {
        if ( v5 > 0 )
          v5 = (unsigned __int16)v5 | 0x80070000;
      }
      else
      {
        v5 = -2143748092;
      }
      ZTraceReportOrigination(v5, "ScopedWatchdogTimer::ScopedWatchdogTimer", 40, Context);
    }
  }
  return (ScopedWatchdogTimer *)Context;
}

```

## disassembly

```asm
0x18000420c  mov     [rsp+arg_0], rbx
0x180004211  push    rdi
0x180004212  sub     rsp, 30h
0x180004216  mov     rbx, rcx
0x180004219  mov     [rcx], r8
0x18000421c  call    cs:__imp_GetCurrentThreadId
0x180004222  mov     [rbx+8], eax
0x180004225  mov     dword ptr [rbx+0Ch], 7530h
0x18000422c  mov     qword ptr [rbx+10h], 0
0x180004234  mov     qword ptr [rbx+18h], 0
0x18000423c  call    cs:__imp_IsDebuggerPresent
0x180004242  test    eax, eax
0x180004244  jnz     loc_1800042F6
0x18000424a  xor     r9d, r9d; lpName
0x18000424d  lea     edx, [rax+1]; bManualReset
0x180004250  xor     r8d, r8d; bInitialState
0x180004253  xor     ecx, ecx; lpEventAttributes
0x180004255  call    cs:__imp_CreateEventW
0x18000425b  mov     [rbx+18h], rax
0x18000425f  mov     rdx, rax; hObject
0x180004262  test    rax, rax
0x180004265  jnz     short loc_18000429C
0x180004267  call    cs:__imp_GetLastError
0x18000426d  test    eax, eax
0x18000426f  jz      short loc_18000427D
0x180004271  jle     short loc_180004282
0x180004273  movzx   eax, ax
0x180004276  or      eax, 80070000h
0x18000427b  jmp     short loc_180004282
0x18000427d  mov     eax, 80390004h
0x180004282  mov     r9, rbx
0x180004285  lea     rdx, aScopedwatchdog; "ScopedWatchdogTimer::ScopedWatchdogTime"...
0x18000428c  mov     r8d, 28h ; '('
0x180004292  mov     ecx, eax
0x180004294  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000429a  jmp     short loc_1800042F6
0x18000429c  mov     eax, [rbx+0Ch]
0x18000429f  lea     r8, ?WaitCallback@ScopedWatchdogTimer@@SAXPEAXE@Z; Callback
0x1800042a6  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800042ae  lea     rcx, [rbx+10h]; phNewWaitObject
0x1800042b2  mov     r9, rbx; Context
0x1800042b5  mov     [rsp+38h+dwMilliseconds], eax; dwMilliseconds
0x1800042b9  call    cs:__imp_RegisterWaitForSingleObject
0x1800042bf  test    eax, eax
0x1800042c1  jnz     short loc_1800042F6
0x1800042c3  call    cs:__imp_GetLastError
0x1800042c9  test    eax, eax
0x1800042cb  jz      short loc_1800042D9
0x1800042cd  jle     short loc_1800042DE
0x1800042cf  movzx   eax, ax
0x1800042d2  or      eax, 80070000h
0x1800042d7  jmp     short loc_1800042DE
0x1800042d9  mov     eax, 80390004h
0x1800042de  mov     r9, rbx
0x1800042e1  lea     rdx, aScopedwatchdog; "ScopedWatchdogTimer::ScopedWatchdogTime"...
0x1800042e8  mov     r8d, 31h ; '1'
0x1800042ee  mov     ecx, eax
0x1800042f0  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800042f6  mov     rax, rbx
0x1800042f9  mov     rbx, [rsp+38h+arg_0]
0x1800042fe  add     rsp, 30h
0x180004302  pop     rdi
0x180004303  retn
```
