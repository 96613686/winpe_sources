# HbPnpDeleteAllEventLogs

- ea: `0x14000f948`
- end: `0x14000fc3f`
- name: `HbPnpDeleteAllEventLogs`
- size: `759`
- prototype: `LONG __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400140f0`

## callees

- `0x140001600`
- `0x14000f948`
- `0x140010a78`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000fc27`
- `ntoskrnl!KeReleaseMutex` at `0x14000fc27`
- `ntoskrnl!KeCancelTimer` at `0x14000f95a`
- `ntoskrnl!KeCancelTimer` at `0x14000f95a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f981`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f981`
- `HAL!KeQueryPerformanceCounter` at `0x14000f9ac`
- `HAL!KeQueryPerformanceCounter` at `0x14000fa8a`
- `HAL!KeQueryPerformanceCounter` at `0x14000fb5f`
- `HAL!KeQueryPerformanceCounter` at `0x14000f9ac`
- `HAL!KeQueryPerformanceCounter` at `0x14000fa8a`
- `HAL!KeQueryPerformanceCounter` at `0x14000fb5f`

## string_xrefs

- `0x14000fa53`: `HbEvtpDeleteEventLog failed for log type %d with 0x%x`
- `0x14000fb2a`: `HbEvtpDeleteEventLog failed for log type %d with 0x%x`
- `0x14000fbff`: `HbEvtpDeleteEventLog failed for log type %d with 0x%x`
- `0x14000fa69`: `HbPnpDeleteAllEventLogs`
- `0x14000fb3b`: `HbPnpDeleteAllEventLogs`
- `0x14000fc14`: `HbPnpDeleteAllEventLogs`

## pseudocode

```c
LONG __fastcall HbPnpDeleteAllEventLogs(__int64 a1)
{
  int v2; // ebx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v4; // rdx
  LONGLONG v5; // rcx
  int v6; // ebx
  LARGE_INTEGER v7; // rax
  __int64 v8; // rdx
  LONGLONG v9; // rcx
  int v10; // ebx
  LARGE_INTEGER v11; // rax
  __int64 v12; // rdx
  LONGLONG v13; // rcx

  KeCancelTimer((PKTIMER)(a1 + 96));
  KeWaitForSingleObject((PVOID)(a1 + 208), Executive, 0, 0, 0);
  *(_BYTE *)(a1 + 264) = 1;
  v2 = HbEvtpDeleteEventLog(a1, 0);
  PerformanceCounter = KeQueryPerformanceCounter(&stru_140009240);
  qword_140009238 = PerformanceCounter.QuadPart;
  v4 = qword_1400091D8[3 * HbDriverLastRecordedLifecyclePhase];
  if ( v4 && PerformanceCounter.QuadPart && stru_140009240.QuadPart )
    v5 = 1000 * (PerformanceCounter.QuadPart - v4) / stru_140009240.QuadPart;
  else
    v5 = 0;
  HbpTraceEvent(
    3,
    "HbRecordPhaseTimestamp",
    185,
    "Phase %s reached (%llu ms since %s)",
    "Unload.DeleteGlobalLog",
    v5,
    HbDriverPhaseNames[HbDriverLastRecordedLifecyclePhase]);
  HbDriverLastRecordedLifecyclePhase = 4;
  if ( v2 < 0 )
    HbpTraceEvent(1, "HbPnpDeleteAllEventLogs", 418, "HbEvtpDeleteEventLog failed for log type %d with 0x%x", 0, v2);
  v6 = HbEvtpDeleteEventLog(a1, 1u);
  v7 = KeQueryPerformanceCounter(&stru_140009258);
  qword_140009250 = v7.QuadPart;
  v8 = qword_1400091D8[3 * HbDriverLastRecordedLifecyclePhase];
  if ( v8 && v7.QuadPart && stru_140009258.QuadPart )
    v9 = 1000 * (v7.QuadPart - v8) / stru_140009258.QuadPart;
  else
    v9 = 0;
  HbpTraceEvent(
    3,
    "HbRecordPhaseTimestamp",
    185,
    "Phase %s reached (%llu ms since %s)",
    "Unload.DeleteLocalLog",
    v9,
    HbDriverPhaseNames[HbDriverLastRecordedLifecyclePhase]);
  HbDriverLastRecordedLifecyclePhase = 5;
  if ( v6 < 0 )
    HbpTraceEvent(1, "HbPnpDeleteAllEventLogs", 429, "HbEvtpDeleteEventLog failed for log type %d with 0x%x", 1, v6);
  v10 = HbEvtpDeleteEventLog(a1, 2u);
  v11 = KeQueryPerformanceCounter(&stru_140009270);
  qword_140009268 = v11.QuadPart;
  v12 = qword_1400091D8[3 * HbDriverLastRecordedLifecyclePhase];
  if ( v12 && v11.QuadPart && stru_140009270.QuadPart )
    v13 = 1000 * (v11.QuadPart - v12) / stru_140009270.QuadPart;
  else
    v13 = 0;
  HbpTraceEvent(
    3,
    "HbRecordPhaseTimestamp",
    185,
    "Phase %s reached (%llu ms since %s)",
    "Unload.DeleteSysDiagLog",
    v13,
    HbDriverPhaseNames[HbDriverLastRecordedLifecyclePhase]);
  HbDriverLastRecordedLifecyclePhase = 6;
  if ( v10 < 0 )
    HbpTraceEvent(1, "HbPnpDeleteAllEventLogs", 440, "HbEvtpDeleteEventLog failed for log type %d with 0x%x", 2, v10);
  return KeReleaseMutex((PRKMUTEX)(a1 + 208), 0);
}

```

## disassembly

```asm
0x14000f948  push    rbx
0x14000f94a  push    rbp
0x14000f94b  push    rsi
0x14000f94c  push    rdi
0x14000f94d  push    r13
0x14000f94f  sub     rsp, 40h
0x14000f953  mov     rdi, rcx
0x14000f956  add     rcx, 60h ; '`'; PKTIMER
0x14000f95a  call    cs:__imp_KeCancelTimer
0x14000f961  nop     dword ptr [rax+rax+00h]
0x14000f966  lea     rsi, [rdi+0D0h]
0x14000f96d  mov     [rsp+68h+Timeout], 0; Timeout
0x14000f976  mov     rcx, rsi; Object
0x14000f979  xor     r9d, r9d; Alertable
0x14000f97c  xor     r8d, r8d; WaitMode
0x14000f97f  xor     edx, edx; WaitReason
0x14000f981  call    cs:__imp_KeWaitForSingleObject
0x14000f988  nop     dword ptr [rax+rax+00h]
0x14000f98d  mov     ebp, 1
0x14000f992  xor     edx, edx
0x14000f994  mov     rcx, rdi
0x14000f997  mov     [rdi+108h], bpl
0x14000f99e  call    HbEvtpDeleteEventLog
0x14000f9a3  lea     rcx, stru_140009240; PerformanceFrequency
0x14000f9aa  mov     ebx, eax
0x14000f9ac  call    cs:__imp_KeQueryPerformanceCounter
0x14000f9b3  nop     dword ptr [rax+rax+00h]
0x14000f9b8  mov     cs:qword_140009238, rax
0x14000f9bf  movsxd  r8, cs:HbDriverLastRecordedLifecyclePhase
0x14000f9c6  lea     r13, cs:140000000h
0x14000f9cd  lea     rcx, [r8+r8*2]
0x14000f9d1  mov     rdx, rva qword_1400091D8[r13+rcx*8]
0x14000f9d9  test    rdx, rdx
0x14000f9dc  jz      short loc_14000FA03
0x14000f9de  test    rax, rax
0x14000f9e1  jz      short loc_14000FA03
0x14000f9e3  mov     rcx, qword ptr cs:stru_140009240
0x14000f9ea  test    rcx, rcx
0x14000f9ed  jz      short loc_14000FA03
0x14000f9ef  sub     rax, rdx
0x14000f9f2  imul    rax, 3E8h
0x14000f9f9  cqo
0x14000f9fb  idiv    rcx
0x14000f9fe  mov     rcx, rax
0x14000fa01  jmp     short loc_14000FA05
0x14000fa03  xor     ecx, ecx
0x14000fa05  mov     rax, ds:rva HbDriverPhaseNames[r13+r8*8]
0x14000fa0d  lea     r9, aPhaseSReachedL; "Phase %s reached (%llu ms since %s)"
0x14000fa14  mov     [rsp+68h+var_38], rax
0x14000fa19  lea     rdx, aHbrecordphaset; "HbRecordPhaseTimestamp"
0x14000fa20  mov     rax, cs:off_140005020; "Unload.DeleteGlobalLog"
0x14000fa27  mov     r8d, 0B9h
0x14000fa2d  mov     [rsp+68h+var_40], rcx
0x14000fa32  mov     ecx, 3
0x14000fa37  mov     [rsp+68h+Timeout], rax
0x14000fa3c  call    HbpTraceEvent
0x14000fa41  mov     cs:HbDriverLastRecordedLifecyclePhase, 4
0x14000fa4b  test    ebx, ebx
0x14000fa4d  jns     short loc_14000FA77
0x14000fa4f  mov     dword ptr [rsp+68h+var_40], ebx
0x14000fa53  lea     r9, aHbevtpdeleteev_0; "HbEvtpDeleteEventLog failed for log typ"...
0x14000fa5a  mov     r8d, 1A2h
0x14000fa60  mov     [rsp+68h+Timeout], 0
0x14000fa69  lea     rdx, aHbpnpdeleteall; "HbPnpDeleteAllEventLogs"
0x14000fa70  mov     ecx, ebp
0x14000fa72  call    HbpTraceEvent
0x14000fa77  mov     edx, ebp
0x14000fa79  mov     rcx, rdi
0x14000fa7c  call    HbEvtpDeleteEventLog
0x14000fa81  lea     rcx, stru_140009258; PerformanceFrequency
0x14000fa88  mov     ebx, eax
0x14000fa8a  call    cs:__imp_KeQueryPerformanceCounter
0x14000fa91  nop     dword ptr [rax+rax+00h]
0x14000fa96  mov     cs:qword_140009250, rax
0x14000fa9d  movsxd  r8, cs:HbDriverLastRecordedLifecyclePhase
0x14000faa4  lea     rcx, [r8+r8*2]
0x14000faa8  mov     rdx, rva qword_1400091D8[r13+rcx*8]
0x14000fab0  test    rdx, rdx
0x14000fab3  jz      short loc_14000FADA
0x14000fab5  test    rax, rax
0x14000fab8  jz      short loc_14000FADA
0x14000faba  mov     rcx, qword ptr cs:stru_140009258
0x14000fac1  test    rcx, rcx
0x14000fac4  jz      short loc_14000FADA
0x14000fac6  sub     rax, rdx
0x14000fac9  imul    rax, 3E8h
0x14000fad0  cqo
0x14000fad2  idiv    rcx
0x14000fad5  mov     rcx, rax
0x14000fad8  jmp     short loc_14000FADC
0x14000fada  xor     ecx, ecx
0x14000fadc  mov     rax, ds:rva HbDriverPhaseNames[r13+r8*8]
0x14000fae4  lea     r9, aPhaseSReachedL; "Phase %s reached (%llu ms since %s)"
0x14000faeb  mov     [rsp+68h+var_38], rax
0x14000faf0  lea     rdx, aHbrecordphaset; "HbRecordPhaseTimestamp"
0x14000faf7  mov     rax, cs:off_140005028; "Unload.DeleteLocalLog"
0x14000fafe  mov     r8d, 0B9h
0x14000fb04  mov     [rsp+68h+var_40], rcx
0x14000fb09  mov     ecx, 3
0x14000fb0e  mov     [rsp+68h+Timeout], rax
0x14000fb13  call    HbpTraceEvent
0x14000fb18  mov     cs:HbDriverLastRecordedLifecyclePhase, 5
0x14000fb22  test    ebx, ebx
0x14000fb24  jns     short loc_14000FB49
0x14000fb26  mov     dword ptr [rsp+68h+var_40], ebx
0x14000fb2a  lea     r9, aHbevtpdeleteev_0; "HbEvtpDeleteEventLog failed for log typ"...
0x14000fb31  mov     r8d, 1ADh
0x14000fb37  mov     dword ptr [rsp+68h+Timeout], ebp
0x14000fb3b  lea     rdx, aHbpnpdeleteall; "HbPnpDeleteAllEventLogs"
0x14000fb42  mov     ecx, ebp
0x14000fb44  call    HbpTraceEvent
0x14000fb49  mov     edx, 2
0x14000fb4e  mov     rcx, rdi
0x14000fb51  call    HbEvtpDeleteEventLog
0x14000fb56  lea     rcx, stru_140009270; PerformanceFrequency
0x14000fb5d  mov     ebx, eax
0x14000fb5f  call    cs:__imp_KeQueryPerformanceCounter
0x14000fb66  nop     dword ptr [rax+rax+00h]
0x14000fb6b  mov     cs:qword_140009268, rax
0x14000fb72  movsxd  r8, cs:HbDriverLastRecordedLifecyclePhase
0x14000fb79  lea     rcx, [r8+r8*2]
0x14000fb7d  mov     rdx, rva qword_1400091D8[r13+rcx*8]
0x14000fb85  test    rdx, rdx
0x14000fb88  jz      short loc_14000FBAF
0x14000fb8a  test    rax, rax
0x14000fb8d  jz      short loc_14000FBAF
0x14000fb8f  mov     rcx, qword ptr cs:stru_140009270
0x14000fb96  test    rcx, rcx
0x14000fb99  jz      short loc_14000FBAF
0x14000fb9b  sub     rax, rdx
0x14000fb9e  imul    rax, 3E8h
0x14000fba5  cqo
0x14000fba7  idiv    rcx
0x14000fbaa  mov     rcx, rax
0x14000fbad  jmp     short loc_14000FBB1
0x14000fbaf  xor     ecx, ecx
0x14000fbb1  mov     rax, ds:rva HbDriverPhaseNames[r13+r8*8]
0x14000fbb9  lea     r9, aPhaseSReachedL; "Phase %s reached (%llu ms since %s)"
0x14000fbc0  mov     [rsp+68h+var_38], rax
0x14000fbc5  lea     rdx, aHbrecordphaset; "HbRecordPhaseTimestamp"
0x14000fbcc  mov     rax, cs:off_140005030; "Unload.DeleteSysDiagLog"
0x14000fbd3  mov     r8d, 0B9h
0x14000fbd9  mov     [rsp+68h+var_40], rcx
0x14000fbde  mov     ecx, 3
0x14000fbe3  mov     [rsp+68h+Timeout], rax
0x14000fbe8  call    HbpTraceEvent
0x14000fbed  mov     cs:HbDriverLastRecordedLifecyclePhase, 6
0x14000fbf7  test    ebx, ebx
0x14000fbf9  jns     short loc_14000FC22
0x14000fbfb  mov     dword ptr [rsp+68h+var_40], ebx
0x14000fbff  lea     r9, aHbevtpdeleteev_0; "HbEvtpDeleteEventLog failed for log typ"...
0x14000fc06  mov     r8d, 1B8h
0x14000fc0c  mov     dword ptr [rsp+68h+Timeout], 2
0x14000fc14  lea     rdx, aHbpnpdeleteall; "HbPnpDeleteAllEventLogs"
0x14000fc1b  mov     ecx, ebp
0x14000fc1d  call    HbpTraceEvent
0x14000fc22  xor     edx, edx; Wait
0x14000fc24  mov     rcx, rsi; Mutex
0x14000fc27  call    cs:__imp_KeReleaseMutex
0x14000fc2e  nop     dword ptr [rax+rax+00h]
0x14000fc33  add     rsp, 40h
0x14000fc37  pop     r13
0x14000fc39  pop     rdi
0x14000fc3a  pop     rsi
0x14000fc3b  pop     rbp
0x14000fc3c  pop     rbx
0x14000fc3d  retn
```
