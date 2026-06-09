# WfpStopTimer

- ea: `0x180049de8`
- end: `0x180049eae`
- name: `WfpStopTimer`
- size: `198`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001125c`
- `0x18003c204`
- `0x180049cb0`

## callees

- `0x180007e38`
- `0x180011500`
- `0x180049de8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049e25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049e25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049dfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049dfd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180049e8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180049e8e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180049e7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180049e7f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180049e6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180049e6d`

## pseudocode

```c
__int64 __fastcall WfpStopTimer(LPCRITICAL_SECTION lpCriticalSection, __int64 a2)
{
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbx

  EnterCriticalSection(lpCriticalSection);
  if ( *(_DWORD *)(a2 + 24) == 3 || *(_DWORD *)(a2 + 24) == 2 )
  {
    v4 = 0;
  }
  else
  {
    v4 = 1;
    *(_DWORD *)(a2 + 24) = 2;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( v4 )
  {
    v7 = 0;
    SetThreadpoolTimer(*(PTP_TIMER *)a2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)a2, 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)a2);
  }
  else
  {
    v6 = WfpReportSysErrorAsNtStatus(v5, "WfpStopTimer", 259);
    v7 = v6;
    if ( v6 )
      WfpReportError(v6, "WfpStopTimer");
  }
  return v7;
}

```

## disassembly

```asm
0x180049de8  mov     [rsp+arg_0], rbx
0x180049ded  mov     [rsp+arg_8], rsi
0x180049df2  push    rdi
0x180049df3  sub     rsp, 20h
0x180049df7  mov     rdi, rdx
0x180049dfa  mov     rsi, rcx
0x180049dfd  call    cs:__imp_EnterCriticalSection
0x180049e04  nop     dword ptr [rax+rax+00h]
0x180049e09  cmp     dword ptr [rdi+18h], 3
0x180049e0d  jz      short loc_180049E15
0x180049e0f  cmp     dword ptr [rdi+18h], 2
0x180049e13  jnz     short loc_180049E19
0x180049e15  xor     bl, bl
0x180049e17  jmp     short loc_180049E22
0x180049e19  mov     bl, 1
0x180049e1b  mov     dword ptr [rdi+18h], 2
0x180049e22  mov     rcx, rsi; lpCriticalSection
0x180049e25  call    cs:__imp_LeaveCriticalSection
0x180049e2c  nop     dword ptr [rax+rax+00h]
0x180049e31  test    bl, bl
0x180049e33  jnz     short loc_180049E60
0x180049e35  mov     r8d, 103h
0x180049e3b  lea     rdx, aWfpstoptimer; "WfpStopTimer"
0x180049e42  call    WfpReportSysErrorAsNtStatus
0x180049e47  mov     rbx, rax
0x180049e4a  test    rax, rax
0x180049e4d  jz      short loc_180049E9A
0x180049e4f  lea     rdx, aWfpstoptimer; "WfpStopTimer"
0x180049e56  mov     rcx, rax
0x180049e59  call    WfpReportError
0x180049e5e  jmp     short loc_180049E9A
0x180049e60  mov     rcx, [rdi]; pti
0x180049e63  xor     r9d, r9d; msWindowLength
0x180049e66  xor     r8d, r8d; msPeriod
0x180049e69  xor     edx, edx; pftDueTime
0x180049e6b  xor     ebx, ebx
0x180049e6d  call    cs:__imp_SetThreadpoolTimer
0x180049e74  nop     dword ptr [rax+rax+00h]
0x180049e79  mov     rcx, [rdi]; pti
0x180049e7c  lea     edx, [rbx+1]; fCancelPendingCallbacks
0x180049e7f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180049e86  nop     dword ptr [rax+rax+00h]
0x180049e8b  mov     rcx, [rdi]; pti
0x180049e8e  call    cs:__imp_CloseThreadpoolTimer
0x180049e95  nop     dword ptr [rax+rax+00h]
0x180049e9a  mov     rsi, [rsp+28h+arg_8]
0x180049e9f  mov     rax, rbx
0x180049ea2  mov     rbx, [rsp+28h+arg_0]
0x180049ea7  add     rsp, 20h
0x180049eab  pop     rdi
0x180049eac  retn
```
