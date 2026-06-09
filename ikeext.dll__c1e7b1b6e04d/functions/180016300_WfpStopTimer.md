# WfpStopTimer

- ea: `0x180016300`
- end: `0x1800163a7`
- name: `WfpStopTimer`
- size: `167`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180015af0`
- `0x18003cfa0`
- `0x180064fa0`
- `0x180068088`
- `0x1800ce2d0`

## callees

- `0x180010db0`
- `0x180016300`
- `0x180016534`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016337`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016337`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016315`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016315`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016379`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016379`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001638e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001638e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016385`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016385`

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
0x180016300  mov     [rsp+arg_0], rbx
0x180016305  mov     [rsp+arg_8], rsi
0x18001630a  push    rdi
0x18001630b  sub     rsp, 20h
0x18001630f  mov     rdi, rdx
0x180016312  mov     rsi, rcx
0x180016315  call    cs:__imp_EnterCriticalSection
0x18001631b  cmp     dword ptr [rdi+18h], 3
0x18001631f  jz      short loc_180016327
0x180016321  cmp     dword ptr [rdi+18h], 2
0x180016325  jnz     short loc_18001632B
0x180016327  xor     bl, bl
0x180016329  jmp     short loc_180016334
0x18001632b  mov     bl, 1
0x18001632d  mov     dword ptr [rdi+18h], 2
0x180016334  mov     rcx, rsi; lpCriticalSection
0x180016337  call    cs:__imp_LeaveCriticalSection
0x18001633d  test    bl, bl
0x18001633f  jnz     short loc_18001636C
0x180016341  mov     r8d, 103h
0x180016347  lea     rdx, aWfpstoptimer; "WfpStopTimer"
0x18001634e  call    WfpReportSysErrorAsNtStatus
0x180016353  mov     rbx, rax
0x180016356  test    rax, rax
0x180016359  jz      short loc_180016394
0x18001635b  lea     rdx, aWfpstoptimer; "WfpStopTimer"
0x180016362  mov     rcx, rax
0x180016365  call    WfpReportError
0x18001636a  jmp     short loc_180016394
0x18001636c  mov     rcx, [rdi]; pti
0x18001636f  xor     r9d, r9d; msWindowLength
0x180016372  xor     r8d, r8d; msPeriod
0x180016375  xor     edx, edx; pftDueTime
0x180016377  xor     ebx, ebx
0x180016379  call    cs:__imp_SetThreadpoolTimer
0x18001637f  mov     rcx, [rdi]; pti
0x180016382  lea     edx, [rbx+1]; fCancelPendingCallbacks
0x180016385  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001638b  mov     rcx, [rdi]; pti
0x18001638e  call    cs:__imp_CloseThreadpoolTimer
0x180016394  mov     rsi, [rsp+28h+arg_8]
0x180016399  mov     rax, rbx
0x18001639c  mov     rbx, [rsp+28h+arg_0]
0x1800163a1  add     rsp, 20h
0x1800163a5  pop     rdi
0x1800163a6  retn
```
