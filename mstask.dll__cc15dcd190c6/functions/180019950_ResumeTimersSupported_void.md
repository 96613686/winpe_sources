# ResumeTimersSupported(void)

- ea: `0x180019950`
- end: `0x1800199db`
- name: `?ResumeTimersSupported@@YAHXZ`
- size: `139`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180018300`
- `0x1800199e4`
- `0x18001a7e0`

## callees

- `0x180019950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800199c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800199c3`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800199a1`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800199a1`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800199ba`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800199ba`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180019971`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180019971`

## pseudocode

```c
HANDLE ResumeTimersSupported(void)
{
  HANDLE result; // rax
  HANDLE v1; // rdi
  BOOL v2; // ebx
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp+8h] BYREF

  result = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
  v1 = result;
  if ( result )
  {
    v2 = 0;
    DueTime.QuadPart = -1;
    if ( SetWaitableTimer(result, &DueTime, 0, 0, 0, 1) )
      v2 = GetLastError() != 50;
    CancelWaitableTimer(v1);
    CloseHandle(v1);
    return (HANDLE)v2;
  }
  return result;
}

```

## disassembly

```asm
0x180019950  mov     [rsp+arg_8], rbx
0x180019955  mov     [rsp+arg_10], rsi
0x18001995a  push    rdi
0x18001995b  sub     rsp, 30h
0x18001995f  mov     esi, 1
0x180019964  mov     r9d, 1F0003h; dwDesiredAccess
0x18001996a  mov     r8d, esi; dwFlags
0x18001996d  xor     edx, edx; lpTimerName
0x18001996f  xor     ecx, ecx; lpTimerAttributes
0x180019971  call    cs:__imp_CreateWaitableTimerExW
0x180019977  mov     rdi, rax
0x18001997a  test    rax, rax
0x18001997d  jz      short loc_1800199CB
0x18001997f  xor     ebx, ebx
0x180019981  mov     [rsp+38h+fResume], esi; fResume
0x180019985  xor     r9d, r9d; pfnCompletionRoutine
0x180019988  mov     [rsp+38h+lpArgToCompletionRoutine], rbx; lpArgToCompletionRoutine
0x18001998d  xor     r8d, r8d; lPeriod
0x180019990  mov     qword ptr [rsp+38h+DueTime], 0FFFFFFFFFFFFFFFFh
0x180019999  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x18001999e  mov     rcx, rdi; hTimer
0x1800199a1  call    cs:__imp_SetWaitableTimer
0x1800199a7  test    eax, eax
0x1800199a9  jz      short loc_1800199B7
0x1800199ab  call    cs:__imp_GetLastError
0x1800199b1  cmp     eax, 32h ; '2'
0x1800199b4  cmovnz  ebx, esi
0x1800199b7  mov     rcx, rdi; hTimer
0x1800199ba  call    cs:__imp_CancelWaitableTimer
0x1800199c0  mov     rcx, rdi; hObject
0x1800199c3  call    cs:__imp_CloseHandle
0x1800199c9  mov     eax, ebx
0x1800199cb  mov     rbx, [rsp+38h+arg_8]
0x1800199d0  mov     rsi, [rsp+38h+arg_10]
0x1800199d5  add     rsp, 30h
0x1800199d9  pop     rdi
0x1800199da  retn
```
