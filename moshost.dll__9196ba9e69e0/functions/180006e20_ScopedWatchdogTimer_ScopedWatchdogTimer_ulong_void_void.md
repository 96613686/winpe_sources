# ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))

- ea: `0x180006e20`
- end: `0x180006f16`
- name: `??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z`
- size: `246`
- prototype: `ScopedWatchdogTimer *__fastcall(PVOID Context, int, void (*)(void))`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180007350`
- `0x180007460`
- `0x180007680`
- `0x180007aa0`
- `0x1800082d0`
- `0x180008800`
- `0x180008ce0`
- `0x180008ed0`
- `0x180009250`
- `0x1800093a0`
- `0x18000b38c`

## callees

- `0x180006e20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006e67`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ed5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e32`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006e4e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006e4e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180006ecb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180006ecb`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180006ea6`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180006ea6`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180006f02`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180006f02`

## pseudocode

```c
ScopedWatchdogTimer *__fastcall ScopedWatchdogTimer::ScopedWatchdogTimer(PVOID Context, int a2, void (*a3)(void))
{
  HANDLE EventW; // rax
  signed int v6; // eax
  signed int LastError; // eax

  *(_QWORD *)Context = a3;
  *((_DWORD *)Context + 2) = GetCurrentThreadId();
  *((_DWORD *)Context + 3) = a2;
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
      v6 = GetLastError();
      if ( v6 )
      {
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
      }
      else
      {
        v6 = -2143748092;
      }
      ZTraceReportOrigination(v6, "ScopedWatchdogTimer::ScopedWatchdogTimer", 40, Context);
    }
  }
  return (ScopedWatchdogTimer *)Context;
}

```

## disassembly

```asm
0x180006e20  mov     [rsp+arg_0], rbx
0x180006e25  push    rdi
0x180006e26  sub     rsp, 30h
0x180006e2a  mov     ebx, edx
0x180006e2c  mov     [rcx], r8
0x180006e2f  mov     rdi, rcx
0x180006e32  call    cs:__imp_GetCurrentThreadId
0x180006e38  mov     [rdi+8], eax
0x180006e3b  mov     [rdi+0Ch], ebx
0x180006e3e  mov     qword ptr [rdi+10h], 0
0x180006e46  mov     qword ptr [rdi+18h], 0
0x180006e4e  call    cs:__imp_IsDebuggerPresent
0x180006e54  test    eax, eax
0x180006e56  jnz     loc_180006F08
0x180006e5c  xor     r9d, r9d; lpName
0x180006e5f  lea     edx, [rax+1]; bManualReset
0x180006e62  xor     r8d, r8d; bInitialState
0x180006e65  xor     ecx, ecx; lpEventAttributes
0x180006e67  call    cs:__imp_CreateEventW
0x180006e6d  mov     [rdi+18h], rax
0x180006e71  mov     rdx, rax; hObject
0x180006e74  test    rax, rax
0x180006e77  jnz     short loc_180006EAE
0x180006e79  call    cs:__imp_GetLastError
0x180006e7f  test    eax, eax
0x180006e81  jz      short loc_180006E8F
0x180006e83  jle     short loc_180006E94
0x180006e85  movzx   eax, ax
0x180006e88  or      eax, 80070000h
0x180006e8d  jmp     short loc_180006E94
0x180006e8f  mov     eax, 80390004h
0x180006e94  mov     r9, rdi
0x180006e97  lea     rdx, aScopedwatchdog; "ScopedWatchdogTimer::ScopedWatchdogTime"...
0x180006e9e  mov     r8d, 28h ; '('
0x180006ea4  mov     ecx, eax
0x180006ea6  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180006eac  jmp     short loc_180006F08
0x180006eae  mov     eax, [rdi+0Ch]
0x180006eb1  lea     r8, ?WaitCallback@ScopedWatchdogTimer@@SAXPEAXE@Z; Callback
0x180006eb8  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180006ec0  lea     rcx, [rdi+10h]; phNewWaitObject
0x180006ec4  mov     r9, rdi; Context
0x180006ec7  mov     [rsp+38h+dwMilliseconds], eax; dwMilliseconds
0x180006ecb  call    cs:__imp_RegisterWaitForSingleObject
0x180006ed1  test    eax, eax
0x180006ed3  jnz     short loc_180006F08
0x180006ed5  call    cs:__imp_GetLastError
0x180006edb  test    eax, eax
0x180006edd  jz      short loc_180006EEB
0x180006edf  jle     short loc_180006EF0
0x180006ee1  movzx   eax, ax
0x180006ee4  or      eax, 80070000h
0x180006ee9  jmp     short loc_180006EF0
0x180006eeb  mov     eax, 80390004h
0x180006ef0  mov     r9, rdi
0x180006ef3  lea     rdx, aScopedwatchdog; "ScopedWatchdogTimer::ScopedWatchdogTime"...
0x180006efa  mov     r8d, 31h ; '1'
0x180006f00  mov     ecx, eax
0x180006f02  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180006f08  mov     rbx, [rsp+38h+arg_0]
0x180006f0d  mov     rax, rdi
0x180006f10  add     rsp, 30h
0x180006f14  pop     rdi
0x180006f15  retn
```
