# DiscpInitiatorArrivalTimerCallback

- ea: `0x180013390`
- end: `0x180013541`
- name: `DiscpInitiatorArrivalTimerCallback`
- size: `433`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180012e28`

## callees

- `0x180013390`
- `0x180013a1c`

## import_xrefs

- `ISCSIUM!DiscpPnpDeviceInterfaceToInstanceName` at `0x18001340b`
- `ISCSIUM!DiscpPnpDeviceInterfaceToInstanceName` at `0x18001340b`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x1800134be`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x1800134be`
- `ISCSIUM!DiscpFreeMemory` at `0x180013490`
- `ISCSIUM!DiscpFreeMemory` at `0x180013490`
- `ISCSIUM!DiscpFreeProcessMemory` at `0x1800134ff`
- `ISCSIUM!DiscpFreeProcessMemory` at `0x1800134ff`
- `ntdll!RtlLeaveCriticalSection` at `0x180013457`
- `ntdll!RtlLeaveCriticalSection` at `0x1800134f6`
- `ntdll!RtlLeaveCriticalSection` at `0x180013457`
- `ntdll!RtlLeaveCriticalSection` at `0x1800134f6`
- `ntdll!RtlEnterCriticalSection` at `0x1800133d3`
- `ntdll!RtlEnterCriticalSection` at `0x1800133d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013470`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001352f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001352f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180013446`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180013446`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800133bf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800133bf`

## pseudocode

```c
void __fastcall DiscpInitiatorArrivalTimerCallback(_QWORD *a1)
{
  void **v1; // rsi
  void *v2; // rdx
  DWORD LastError; // edi
  _QWORD *v6; // rax
  PVOID *v7; // rcx
  ULONG Flags; // [rsp+30h] [rbp-28h]
  __int64 v9; // [rsp+70h] [rbp+18h] BYREF

  v1 = (void **)(a1 + 2);
  v9 = 0;
  v2 = (void *)a1[2];
  if ( v2 )
  {
    DeleteTimerQueueTimer(0, v2, 0);
    *v1 = 0;
  }
  RtlEnterCriticalSection(&DiscpShutdownCritSection);
  if ( (a1[3] & 1) == 0 && !DiscpShutdownInProgress )
  {
    LastError = DiscpPnpDeviceInterfaceToInstanceName(a1 + 4, 0, MSiSCSI_HBAInformation_GUID, &v9);
    if ( LastError )
    {
      if ( (*((_DWORD *)a1 + 7))-- == 1 )
        goto LABEL_12;
      if ( CreateTimerQueueTimer(v1, 0, DiscpInitiatorArrivalTimerCallback, a1, DiscpInitiatorArrivalRetryTime, 0, 8u) )
      {
        RtlLeaveCriticalSection(&DiscpShutdownCritSection);
        return;
      }
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_12;
    }
    LastError = DiscpProcessInitiatorArrival(a1 + 4, v9);
    DiscpFreeMemory(v9);
    if ( LastError )
    {
LABEL_12:
      LOWORD(Flags) = 1;
      DiscpReportEventlogWithStatus(108, 2, 0, LastError, 0, 0, Flags);
    }
  }
  v6 = (_QWORD *)*a1;
  if ( *(_QWORD **)(*a1 + 8LL) != a1 || (v7 = (PVOID *)a1[1], *v7 != a1) )
    __fastfail(3u);
  *v7 = v6;
  v6[1] = v7;
  if ( DiscpInitiatorArrivalTimersActiveCount )
    --DiscpInitiatorArrivalTimersActiveCount;
  RtlLeaveCriticalSection(&DiscpShutdownCritSection);
  DiscpFreeProcessMemory(a1);
  if ( DiscpInitiatorArrivalTimersCleared && DiscpShutdownInProgress && !DiscpInitiatorArrivalTimersActiveCount )
    SetEvent(DiscpInitiatorArrivalTimersCleared);
}

```

## disassembly

```asm
0x180013390  mov     [rsp+arg_8], rbx
0x180013395  mov     [rsp+arg_18], rbp
0x18001339a  push    rsi
0x18001339b  push    rdi
0x18001339c  push    r13
0x18001339e  sub     rsp, 40h
0x1800133a2  lea     rsi, [rcx+10h]
0x1800133a6  mov     [rsp+58h+arg_10], 0
0x1800133af  mov     rdx, [rsi]; Timer
0x1800133b2  mov     rbx, rcx
0x1800133b5  test    rdx, rdx
0x1800133b8  jz      short loc_1800133CC
0x1800133ba  xor     r8d, r8d; CompletionEvent
0x1800133bd  xor     ecx, ecx; TimerQueue
0x1800133bf  call    cs:__imp_DeleteTimerQueueTimer
0x1800133c5  mov     qword ptr [rsi], 0
0x1800133cc  lea     rcx, DiscpShutdownCritSection; CriticalSection
0x1800133d3  call    cs:__imp_RtlEnterCriticalSection
0x1800133d9  mov     r13d, 1
0x1800133df  test    [rbx+18h], r13b
0x1800133e3  jnz     loc_1800134C4
0x1800133e9  cmp     cs:DiscpShutdownInProgress, 0
0x1800133f0  jnz     loc_1800134C4
0x1800133f6  lea     rbp, [rbx+20h]
0x1800133fa  xor     edx, edx
0x1800133fc  mov     rcx, rbp
0x1800133ff  lea     r9, [rsp+58h+arg_10]
0x180013404  lea     r8, MSiSCSI_HBAInformation_GUID
0x18001340b  call    cs:__imp_DiscpPnpDeviceInterfaceToInstanceName
0x180013411  mov     edi, eax
0x180013413  test    eax, eax
0x180013415  jz      short loc_18001347C
0x180013417  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x18001341b  jz      short loc_18001349A
0x18001341d  mov     eax, cs:DiscpInitiatorArrivalRetryTime
0x180013423  lea     r8, DiscpInitiatorArrivalTimerCallback; Callback
0x18001342a  mov     [rsp+58h+Flags], 8; Flags
0x180013432  mov     r9, rbx; Parameter
0x180013435  mov     [rsp+58h+Period], 0; Period
0x18001343d  xor     edx, edx; TimerQueue
0x18001343f  mov     rcx, rsi; phNewTimer
0x180013442  mov     [rsp+58h+DueTime], eax; DueTime
0x180013446  call    cs:__imp_CreateTimerQueueTimer
0x18001344c  test    eax, eax
0x18001344e  jz      short loc_180013470
0x180013450  lea     rcx, DiscpShutdownCritSection; CriticalSection
0x180013457  call    cs:__imp_RtlLeaveCriticalSection
0x18001345d  mov     rbx, [rsp+58h+arg_8]
0x180013462  mov     rbp, [rsp+58h+arg_18]
0x180013467  add     rsp, 40h
0x18001346b  pop     r13
0x18001346d  pop     rdi
0x18001346e  pop     rsi
0x18001346f  retn
0x180013470  call    cs:__imp_GetLastError
0x180013476  mov     edi, eax
0x180013478  test    eax, eax
0x18001347a  jnz     short loc_18001349A
0x18001347c  mov     rdx, [rsp+58h+arg_10]
0x180013481  mov     rcx, rbp
0x180013484  call    DiscpProcessInitiatorArrival
0x180013489  mov     rcx, [rsp+58h+arg_10]
0x18001348e  mov     edi, eax
0x180013490  call    cs:__imp_DiscpFreeMemory
0x180013496  test    edi, edi
0x180013498  jz      short loc_1800134C4
0x18001349a  xor     eax, eax
0x18001349c  mov     [rsp+58h+var_20], rbp
0x1800134a1  mov     word ptr [rsp+58h+Flags], r13w
0x1800134a7  mov     r9d, edi
0x1800134aa  mov     qword ptr [rsp+58h+Period], rax
0x1800134af  movzx   r8d, ax
0x1800134b3  lea     edx, [rax+2]
0x1800134b6  mov     qword ptr [rsp+58h+DueTime], rax
0x1800134bb  lea     ecx, [rax+6Ch]
0x1800134be  call    cs:__imp_DiscpReportEventlogWithStatus
0x1800134c4  mov     rax, [rbx]
0x1800134c7  cmp     [rax+8], rbx
0x1800134cb  jnz     short loc_18001353A
0x1800134cd  mov     rcx, [rbx+8]
0x1800134d1  cmp     [rcx], rbx
0x1800134d4  jnz     short loc_18001353A
0x1800134d6  mov     [rcx], rax
0x1800134d9  mov     [rax+8], rcx
0x1800134dd  mov     eax, cs:DiscpInitiatorArrivalTimersActiveCount
0x1800134e3  test    eax, eax
0x1800134e5  jz      short loc_1800134EF
0x1800134e7  dec     eax
0x1800134e9  mov     cs:DiscpInitiatorArrivalTimersActiveCount, eax
0x1800134ef  lea     rcx, DiscpShutdownCritSection; CriticalSection
0x1800134f6  call    cs:__imp_RtlLeaveCriticalSection
0x1800134fc  mov     rcx, rbx
0x1800134ff  call    cs:__imp_DiscpFreeProcessMemory
0x180013505  mov     rcx, cs:DiscpInitiatorArrivalTimersCleared; hEvent
0x18001350c  test    rcx, rcx
0x18001350f  jz      loc_18001345D
0x180013515  cmp     cs:DiscpShutdownInProgress, 0
0x18001351c  jz      loc_18001345D
0x180013522  cmp     cs:DiscpInitiatorArrivalTimersActiveCount, 0
0x180013529  jnz     loc_18001345D
0x18001352f  call    cs:__imp_SetEvent
0x180013535  jmp     loc_18001345D
0x18001353a  mov     ecx, 3
0x18001353f  int     29h; Win8: RtlFailFast(ecx)
```
