# HbEvtpDeleteEventLogWorker

- ea: `0x140010c0c`
- end: `0x14001111f`
- name: `HbEvtpDeleteEventLogWorker`
- size: `1299`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140010a78`

## callees

- `0x140001230`
- `0x140001600`
- `0x1400020f8`
- `0x140010c0c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010d37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010eef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001101b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011046`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011065`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010d37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010eef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001101b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011046`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011065`
- `ntoskrnl!MmUnmapLockedPages` at `0x140010cf4`
- `ntoskrnl!MmUnmapLockedPages` at `0x140010ff7`
- `ntoskrnl!MmUnmapLockedPages` at `0x140010cf4`
- `ntoskrnl!MmUnmapLockedPages` at `0x140010ff7`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140010c62`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140010caf`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140010c62`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140010caf`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x1400110cd`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x1400110cd`
- `ntoskrnl!KeClearEvent` at `0x1400110b4`
- `ntoskrnl!KeClearEvent` at `0x1400110b4`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x140010fac`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x140010fd0`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x140010fac`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x140010fd0`
- `HAL!KeQueryPerformanceCounter` at `0x140010c98`
- `HAL!KeQueryPerformanceCounter` at `0x140010d59`
- `HAL!KeQueryPerformanceCounter` at `0x140010c98`
- `HAL!KeQueryPerformanceCounter` at `0x140010d59`
- `winhvr!WinHvWithdrawMemory` at `0x140010e97`
- `winhvr!WinHvWithdrawMemory` at `0x140010e97`
- `winhvr!WinHvFinalizeEventLogBufferGroup` at `0x140010e3b`
- `winhvr!WinHvFinalizeEventLogBufferGroup` at `0x140010e3b`
- `winhvr!WinHvReleaseEventLogBuffer` at `0x140010cc0`
- `winhvr!WinHvReleaseEventLogBuffer` at `0x140010cc0`
- `winhvr!WinHvUnmapEventLogBuffer` at `0x140010cd1`
- `winhvr!WinHvUnmapEventLogBuffer` at `0x140010cd1`
- `winhvr!WinHvDeleteEventLogBuffer` at `0x140010d12`
- `winhvr!WinHvDeleteEventLogBuffer` at `0x140010d12`
- `winhvr!WinHvGetPartitionId` at `0x140010e73`
- `winhvr!WinHvGetPartitionId` at `0x140010e73`

## string_xrefs

- `0x140010dc8`: `HbEvtpDeleteEventLogWorker`
- `0x140010df1`: `HbEvtpDeleteEventLogWorker`
- `0x140010e24`: `HbEvtpDeleteEventLogWorker`
- `0x140010e5e`: `HbEvtpDeleteEventLogWorker`
- `0x140010ed2`: `HbEvtpDeleteEventLogWorker`
- `0x14001108c`: `HbEvtpDeleteEventLogWorker`
- `0x1400110ee`: `HbEvtpDeleteEventLogWorker`
- `0x140010d9a`: `LocalDiagnostics average buffer delete time: %llu ms (%d buffers)`
- `0x140010ec1`: `Freeing event log configuration for type %d`

## pseudocode

```c
void __fastcall HbEvtpDeleteEventLogWorker(__int64 a1, unsigned int a2)
{
  __int64 v3; // r14
  char v4; // bl
  int LogConfiguration; // eax
  struct _EX_RUNDOWN_REF *v6; // rdi
  int v7; // ebp
  __int64 v8; // r13
  unsigned int Count; // r8d
  unsigned int v10; // r14d
  LARGE_INTEGER PerformanceCounter; // rbx
  ULONG_PTR v12; // r15
  int v13; // eax
  __int64 v14; // r12
  int v15; // eax
  void *v16; // rcx
  int v17; // eax
  PVOID Ptr; // rcx
  PVOID v19; // rcx
  PVOID v20; // rcx
  char *v21; // rdx
  void *v22; // rcx
  PVOID *v23; // rcx
  __int64 v24; // [rsp+30h] [rbp-58h] BYREF
  __int64 v25[10]; // [rsp+38h] [rbp-50h] BYREF
  struct _EX_RUNDOWN_REF *v27; // [rsp+A0h] [rbp+18h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+A8h] [rbp+20h] BYREF

  v3 = a1;
  v27 = 0;
  v25[0] = 0;
  v24 = 0;
  v4 = 0;
  PerformanceFrequency.QuadPart = 0;
  LogConfiguration = HbEvtpGetLogConfiguration(a2, &v27);
  v6 = v27;
  v7 = LogConfiguration;
  if ( LogConfiguration >= 0 )
  {
    v8 = 0;
    ExWaitForRundownProtectionRelease(v27 + 3);
    Count = v6[1].Count;
    v4 = 1;
    v10 = 0;
    if ( Count )
    {
      while ( 1 )
      {
        PerformanceCounter.QuadPart = 0;
        v12 = v6[4].Count;
        if ( a2 == 1 )
          PerformanceCounter = KeQueryPerformanceCounter(0);
        ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v6[5].Count + 8LL * v10));
        WinHvReleaseEventLogBuffer(a2, v10);
        v13 = WinHvUnmapEventLogBuffer(a2, v10);
        v7 = v13;
        if ( v13 < 0 )
          break;
        v14 = 112LL * v10;
        MmUnmapLockedPages(*(PVOID *)(v14 + v12), *(PMDL *)(v14 + v12 + 8));
        *(_QWORD *)(v14 + v12) = 0;
        if ( a2 != 2 )
        {
          v15 = WinHvDeleteEventLogBuffer(a2, v10);
          v7 = v15;
          if ( v15 < 0 )
          {
            HbpTraceEvent(0, "HbEvtpDeleteEventLogWorker", 1903, "Error deleting buffer %d: 0x%x", v10, v15);
            goto LABEL_18;
          }
        }
        v16 = *(void **)(v14 + v12 + 8);
        if ( v16 )
        {
          ExFreePoolWithTag(v16, 0x75426248u);
          *(_QWORD *)(v14 + v12 + 8) = 0;
        }
        if ( a2 == 1 )
          v8 += *(_QWORD *)&KeQueryPerformanceCounter(&PerformanceFrequency) - PerformanceCounter.QuadPart;
        Count = v6[1].Count;
        if ( ++v10 >= Count )
        {
          v4 = 1;
          goto LABEL_14;
        }
      }
      HbpTraceEvent(0, "HbEvtpDeleteEventLogWorker", 1887, "Error unmapping buffer %d: 0x%x", v10, v13);
LABEL_18:
      v4 = 1;
      goto LABEL_25;
    }
LABEL_14:
    if ( a2 == 1 )
    {
      if ( Count )
        HbpTraceEvent(
          2,
          "HbEvtpDeleteEventLogWorker",
          1922,
          "LocalDiagnostics average buffer delete time: %llu ms (%d buffers)",
          1000 * (v8 / Count) / PerformanceFrequency.QuadPart,
          Count);
    }
    else if ( a2 == 2 )
    {
      goto LABEL_23;
    }
    v17 = WinHvFinalizeEventLogBufferGroup(a2);
    v7 = v17;
    if ( v17 < 0 )
    {
      HbpTraceEvent(0, "HbEvtpDeleteEventLogWorker", 1930, "Error finalizing event log buffer group: 0x%x", v17);
LABEL_25:
      v3 = a1;
      goto LABEL_26;
    }
LABEL_23:
    if ( (int)WinHvGetPartitionId(&v24) >= 0 )
      WinHvWithdrawMemory(v24, -1, 0x80000000LL, v25);
    goto LABEL_25;
  }
LABEL_26:
  if ( v6 )
  {
    LODWORD(v6[1].Count) = 0;
    LODWORD(v6->Count) = 0;
    HbpTraceEvent(3, "HbEvtpDeleteEventLogWorker", 1951, "Freeing event log configuration for type %d", a2);
    Ptr = v6[4].Ptr;
    if ( Ptr )
    {
      ExFreePoolWithTag(Ptr, 0x75426248u);
      v6[4].Count = 0;
    }
    v19 = v6[5].Ptr;
    if ( v19 )
    {
      ExFreePoolWithTag(v19, 0x75426248u);
      v6[5].Count = 0;
    }
    v20 = v6[17].Ptr;
    if ( v20 )
    {
      ExFreePoolWithTag(v20, 0x75426248u);
      v6[17].Count = 0;
    }
  }
  if ( a2 == 2 )
  {
    if ( P )
    {
      ExFreePoolWithTag(P, 0x75426248u);
      P = 0;
    }
    if ( *(_QWORD *)&MaxDataSize )
    {
      ExFreePoolWithTag(*(PVOID *)&MaxDataSize, 0x75426248u);
      *(_QWORD *)&MaxDataSize = 0;
    }
    v21 = (char *)HbEvtpCrashdumpContext;
    if ( HbEvtpCrashdumpContext )
    {
      if ( *((_BYTE *)HbEvtpCrashdumpContext + 104) )
      {
        KeDeregisterBugCheckReasonCallback((PKBUGCHECK_REASON_CALLBACK_RECORD)((char *)HbEvtpCrashdumpContext + 56));
        v21 = (char *)HbEvtpCrashdumpContext;
        *((_BYTE *)HbEvtpCrashdumpContext + 104) = 0;
      }
      if ( v21[160] )
      {
        KeDeregisterBugCheckReasonCallback((PKBUGCHECK_REASON_CALLBACK_RECORD)(v21 + 112));
        v21 = (char *)HbEvtpCrashdumpContext;
        *((_BYTE *)HbEvtpCrashdumpContext + 160) = 0;
      }
      v22 = (void *)*((_QWORD *)v21 + 1);
      if ( v22 )
        MmUnmapLockedPages(v22, *((PMDL *)v21 + 2));
      v23 = (PVOID *)HbEvtpCrashdumpContext;
      if ( *((_QWORD *)HbEvtpCrashdumpContext + 2) )
      {
        ExFreePoolWithTag(*((PVOID *)HbEvtpCrashdumpContext + 2), 0x75426248u);
        v23 = (PVOID *)HbEvtpCrashdumpContext;
        *((_QWORD *)HbEvtpCrashdumpContext + 2) = 0;
      }
      if ( v23[21] )
      {
        ExFreePoolWithTag(v23[21], 0x75426248u);
        v23 = (PVOID *)HbEvtpCrashdumpContext;
        *((_QWORD *)HbEvtpCrashdumpContext + 21) = 0;
      }
      ExFreePoolWithTag(v23, 0x75426248u);
      HbEvtpCrashdumpContext = 0;
    }
  }
  else if ( a2 == 1 )
  {
    HbpTraceEvent(3, "HbEvtpDeleteEventLogWorker", 1994, "Clearing the LocalDiagnostics logger ID and the async event");
    *(_DWORD *)(v3 + 336) = 1;
    *(_QWORD *)(v3 + 328) = -1;
    KeClearEvent(&HbEvtpCompleteBufferAsyncEvent);
  }
  if ( v4 && v6 )
    ExReInitializeRundownProtection(v6 + 3);
  if ( v7 < 0 )
  {
    HbpTraceEvent(0, "HbEvtpDeleteEventLogWorker", 2013, "Routine failed with 0x%x", v7);
    HbEvtpWriteEventLog(&HV_EVENTLOG_ENABLE_ETW_TRACE_FAILED, 0, 0);
  }
}

```

## disassembly

```asm
0x140010c0c  mov     rax, rsp
0x140010c0f  mov     [rax+8], rcx
0x140010c13  push    rbx
0x140010c14  push    rbp
0x140010c15  push    rsi
0x140010c16  push    rdi
0x140010c17  push    r12
0x140010c19  push    r13
0x140010c1b  push    r14
0x140010c1d  push    r15
0x140010c1f  sub     rsp, 48h
0x140010c23  xor     r15d, r15d
0x140010c26  mov     esi, edx
0x140010c28  mov     r14, rcx
0x140010c2b  mov     [rax+18h], r15
0x140010c2f  mov     ecx, esi
0x140010c31  mov     [rax-50h], r15
0x140010c35  lea     rdx, [rax+18h]
0x140010c39  mov     [rax-58h], r15
0x140010c3d  mov     bl, r15b
0x140010c40  mov     [rax+20h], r15
0x140010c44  call    HbEvtpGetLogConfiguration
0x140010c49  mov     rdi, [rsp+88h+arg_10]
0x140010c51  mov     ebp, eax
0x140010c53  test    eax, eax
0x140010c55  js      loc_140010EAB
0x140010c5b  lea     rcx, [rdi+18h]; RunRef
0x140010c5f  mov     r13d, r15d
0x140010c62  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140010c69  nop     dword ptr [rax+rax+00h]
0x140010c6e  mov     r8d, [rdi+8]
0x140010c72  mov     bl, 1
0x140010c74  mov     [rsp+88h+arg_8], bl
0x140010c7b  mov     r14d, r15d
0x140010c7e  test    r8d, r8d
0x140010c81  jz      loc_140010D85
0x140010c87  mov     r12d, r14d
0x140010c8a  mov     rbx, r15
0x140010c8d  mov     r15, [rdi+20h]
0x140010c91  cmp     esi, 1
0x140010c94  jnz     short loc_140010CA7
0x140010c96  xor     ecx, ecx; PerformanceFrequency
0x140010c98  call    cs:__imp_KeQueryPerformanceCounter
0x140010c9f  nop     dword ptr [rax+rax+00h]
0x140010ca4  mov     rbx, rax
0x140010ca7  mov     rax, [rdi+28h]
0x140010cab  lea     rcx, [rax+r12*8]; RunRef
0x140010caf  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140010cb6  nop     dword ptr [rax+rax+00h]
0x140010cbb  mov     edx, r14d
0x140010cbe  mov     ecx, esi
0x140010cc0  call    cs:__imp_WinHvReleaseEventLogBuffer
0x140010cc7  nop     dword ptr [rax+rax+00h]
0x140010ccc  mov     edx, r14d
0x140010ccf  mov     ecx, esi
0x140010cd1  call    cs:__imp_WinHvUnmapEventLogBuffer
0x140010cd8  nop     dword ptr [rax+rax+00h]
0x140010cdd  mov     ebp, eax
0x140010cdf  test    eax, eax
0x140010ce1  js      loc_140010E0E
0x140010ce7  imul    r12, 70h ; 'p'
0x140010ceb  mov     rdx, [r12+r15+8]; MemoryDescriptorList
0x140010cf0  mov     rcx, [r12+r15]; BaseAddress
0x140010cf4  call    cs:__imp_MmUnmapLockedPages
0x140010cfb  nop     dword ptr [rax+rax+00h]
0x140010d00  mov     qword ptr [r12+r15], 0
0x140010d08  cmp     esi, 2
0x140010d0b  jz      short loc_140010D28
0x140010d0d  mov     edx, r14d
0x140010d10  mov     ecx, esi
0x140010d12  call    cs:__imp_WinHvDeleteEventLogBuffer
0x140010d19  nop     dword ptr [rax+rax+00h]
0x140010d1e  mov     ebp, eax
0x140010d20  test    eax, eax
0x140010d22  js      loc_140010DDB
0x140010d28  mov     rcx, [r12+r15+8]; P
0x140010d2d  test    rcx, rcx
0x140010d30  jz      short loc_140010D4C
0x140010d32  mov     edx, 75426248h; Tag
0x140010d37  call    cs:__imp_ExFreePoolWithTag
0x140010d3e  nop     dword ptr [rax+rax+00h]
0x140010d43  mov     qword ptr [r12+r15+8], 0
0x140010d4c  cmp     esi, 1
0x140010d4f  jnz     short loc_140010D6B
0x140010d51  lea     rcx, [rsp+88h+PerformanceFrequency]; PerformanceFrequency
0x140010d59  call    cs:__imp_KeQueryPerformanceCounter
0x140010d60  nop     dword ptr [rax+rax+00h]
0x140010d65  sub     rax, rbx
0x140010d68  add     r13, rax
0x140010d6b  mov     r8d, [rdi+8]
0x140010d6f  inc     r14d
0x140010d72  xor     r15d, r15d
0x140010d75  cmp     r14d, r8d
0x140010d78  jb      loc_140010C87
0x140010d7e  mov     bl, [rsp+88h+arg_8]
0x140010d85  cmp     esi, 1
0x140010d88  jnz     loc_140010E34
0x140010d8e  test    r8d, r8d
0x140010d91  jz      loc_140010E39
0x140010d97  mov     ecx, r8d
0x140010d9a  lea     r9, aLocaldiagnosti; "LocalDiagnostics average buffer delete "...
0x140010da1  mov     rax, r13
0x140010da4  mov     [rsp+88h+var_60], r8d
0x140010da9  cqo
0x140010dab  mov     r8d, 782h
0x140010db1  idiv    rcx
0x140010db4  lea     ecx, [rsi+1]
0x140010db7  imul    rax, 3E8h
0x140010dbe  cqo
0x140010dc0  idiv    qword ptr [rsp+88h+PerformanceFrequency]
0x140010dc8  lea     rdx, aHbevtpdeleteev_1; "HbEvtpDeleteEventLogWorker"
0x140010dcf  mov     [rsp+88h+var_68], rax
0x140010dd4  call    HbpTraceEvent
0x140010dd9  jmp     short loc_140010E39
0x140010ddb  mov     [rsp+88h+var_60], eax
0x140010ddf  lea     r9, aErrorDeletingB; "Error deleting buffer %d: 0x%x"
0x140010de6  mov     r8d, 76Fh
0x140010dec  mov     dword ptr [rsp+88h+var_68], r14d
0x140010df1  lea     rdx, aHbevtpdeleteev_1; "HbEvtpDeleteEventLogWorker"
0x140010df8  xor     ecx, ecx
0x140010dfa  call    HbpTraceEvent
0x140010dff  mov     bl, [rsp+88h+arg_8]
0x140010e06  xor     r15d, r15d
0x140010e09  jmp     loc_140010EA3
0x140010e0e  mov     [rsp+88h+var_60], eax
0x140010e12  lea     r9, aErrorUnmapping; "Error unmapping buffer %d: 0x%x"
0x140010e19  mov     r8d, 75Fh
0x140010e1f  mov     dword ptr [rsp+88h+var_68], r14d
0x140010e24  lea     rdx, aHbevtpdeleteev_1; "HbEvtpDeleteEventLogWorker"
0x140010e2b  xor     ecx, ecx
0x140010e2d  call    HbpTraceEvent
0x140010e32  jmp     short loc_140010DFF
0x140010e34  cmp     esi, 2
0x140010e37  jz      short loc_140010E6E
0x140010e39  mov     ecx, esi
0x140010e3b  call    cs:__imp_WinHvFinalizeEventLogBufferGroup
0x140010e42  nop     dword ptr [rax+rax+00h]
0x140010e47  mov     ebp, eax
0x140010e49  test    eax, eax
0x140010e4b  jns     short loc_140010E6E
0x140010e4d  lea     r9, aErrorFinalizin; "Error finalizing event log buffer group"...
0x140010e54  mov     dword ptr [rsp+88h+var_68], eax
0x140010e58  mov     r8d, 78Ah
0x140010e5e  lea     rdx, aHbevtpdeleteev_1; "HbEvtpDeleteEventLogWorker"
0x140010e65  xor     ecx, ecx
0x140010e67  call    HbpTraceEvent
0x140010e6c  jmp     short loc_140010EA3
0x140010e6e  lea     rcx, [rsp+88h+var_58]
0x140010e73  call    cs:__imp_WinHvGetPartitionId
0x140010e7a  nop     dword ptr [rax+rax+00h]
0x140010e7f  test    eax, eax
0x140010e81  js      short loc_140010EA3
0x140010e83  mov     rcx, [rsp+88h+var_58]
0x140010e88  lea     r9, [rsp+88h+var_50]
0x140010e8d  mov     r8d, 80000000h
0x140010e93  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140010e97  call    cs:__imp_WinHvWithdrawMemory
0x140010e9e  nop     dword ptr [rax+rax+00h]
0x140010ea3  mov     r14, [rsp+88h+arg_0]
0x140010eab  mov     r12d, 3
0x140010eb1  test    rdi, rdi
0x140010eb4  jz      loc_140010F41
0x140010eba  mov     [rdi+8], r15d
0x140010ebe  mov     [rdi], r15d
0x140010ec1  lea     r9, aFreeingEventLo; "Freeing event log configuration for typ"...
0x140010ec8  mov     dword ptr [rsp+88h+var_68], esi
0x140010ecc  mov     r8d, 79Fh
0x140010ed2  lea     rdx, aHbevtpdeleteev_1; "HbEvtpDeleteEventLogWorker"
0x140010ed9  mov     ecx, r12d
0x140010edc  call    HbpTraceEvent
0x140010ee1  mov     rcx, [rdi+20h]; P
0x140010ee5  test    rcx, rcx
0x140010ee8  jz      short loc_140010EFF
0x140010eea  mov     edx, 75426248h; Tag
0x140010eef  call    cs:__imp_ExFreePoolWithTag
0x140010ef6  nop     dword ptr [rax+rax+00h]
0x140010efb  mov     [rdi+20h], r15
0x140010eff  mov     rcx, [rdi+28h]; P
0x140010f03  test    rcx, rcx
0x140010f06  jz      short loc_140010F1D
0x140010f08  mov     edx, 75426248h; Tag
0x140010f0d  call    cs:__imp_ExFreePoolWithTag
0x140010f14  nop     dword ptr [rax+rax+00h]
0x140010f19  mov     [rdi+28h], r15
0x140010f1d  mov     rcx, [rdi+88h]; P
0x140010f24  test    rcx, rcx
0x140010f27  jz      short loc_140010F41
0x140010f29  mov     edx, 75426248h; Tag
0x140010f2e  call    cs:__imp_ExFreePoolWithTag
0x140010f35  nop     dword ptr [rax+rax+00h]
0x140010f3a  mov     [rdi+88h], r15
0x140010f41  cmp     esi, 2
0x140010f44  jnz     loc_14001107A
0x140010f4a  mov     rcx, cs:P; P
0x140010f51  test    rcx, rcx
0x140010f54  jz      short loc_140010F6E
0x140010f56  mov     edx, 75426248h; Tag
0x140010f5b  call    cs:__imp_ExFreePoolWithTag
0x140010f62  nop     dword ptr [rax+rax+00h]
0x140010f67  mov     cs:P, r15
0x140010f6e  mov     rcx, qword ptr cs:MaxDataSize; P
0x140010f75  test    rcx, rcx
0x140010f78  jz      short loc_140010F92
0x140010f7a  mov     edx, 75426248h; Tag
0x140010f7f  call    cs:__imp_ExFreePoolWithTag
0x140010f86  nop     dword ptr [rax+rax+00h]
0x140010f8b  mov     qword ptr cs:MaxDataSize, r15
0x140010f92  mov     rdx, cs:HbEvtpCrashdumpContext
0x140010f99  test    rdx, rdx
0x140010f9c  jz      loc_1400110C0
0x140010fa2  cmp     [rdx+68h], r15b
0x140010fa6  jz      short loc_140010FC3
0x140010fa8  lea     rcx, [rdx+38h]; CallbackRecord
0x140010fac  call    cs:__imp_KeDeregisterBugCheckReasonCallback
0x140010fb3  nop     dword ptr [rax+rax+00h]
0x140010fb8  mov     rdx, cs:HbEvtpCrashdumpContext
0x140010fbf  mov     [rdx+68h], r15b
0x140010fc3  cmp     [rdx+0A0h], r15b
0x140010fca  jz      short loc_140010FEA
0x140010fcc  lea     rcx, [rdx+70h]; CallbackRecord
0x140010fd0  call    cs:__imp_KeDeregisterBugCheckReasonCallback
0x140010fd7  nop     dword ptr [rax+rax+00h]
0x140010fdc  mov     rdx, cs:HbEvtpCrashdumpContext
0x140010fe3  mov     [rdx+0A0h], r15b
0x140010fea  mov     rcx, [rdx+8]; BaseAddress
0x140010fee  test    rcx, rcx
0x140010ff1  jz      short loc_140011003
0x140010ff3  mov     rdx, [rdx+10h]; MemoryDescriptorList
0x140010ff7  call    cs:__imp_MmUnmapLockedPages
0x140010ffe  nop     dword ptr [rax+rax+00h]
0x140011003  mov     rcx, cs:HbEvtpCrashdumpContext
0x14001100a  mov     rax, [rcx+10h]
0x14001100e  test    rax, rax
0x140011011  jz      short loc_140011032
0x140011013  mov     edx, 75426248h; Tag
0x140011018  mov     rcx, rax; P
0x14001101b  call    cs:__imp_ExFreePoolWithTag
0x140011022  nop     dword ptr [rax+rax+00h]
0x140011027  mov     rcx, cs:HbEvtpCrashdumpContext
0x14001102e  mov     [rcx+10h], r15
0x140011032  mov     rax, [rcx+0A8h]
0x140011039  test    rax, rax
0x14001103c  jz      short loc_140011060
0x14001103e  mov     edx, 75426248h; Tag
0x140011043  mov     rcx, rax; P
0x140011046  call    cs:__imp_ExFreePoolWithTag
0x14001104d  nop     dword ptr [rax+rax+00h]
0x140011052  mov     rcx, cs:HbEvtpCrashdumpContext; P
0x140011059  mov     [rcx+0A8h], r15
0x140011060  mov     edx, 75426248h; Tag
0x140011065  call    cs:__imp_ExFreePoolWithTag
0x14001106c  nop     dword ptr [rax+rax+00h]
0x140011071  mov     cs:HbEvtpCrashdumpContext, r15
0x140011078  jmp     short loc_1400110C0
0x14001107a  cmp     esi, 1
0x14001107d  jnz     short loc_1400110C0
0x14001107f  lea     r9, aClearingTheLoc; "Clearing the LocalDiagnostics logger ID"...
0x140011086  mov     r8d, 7CAh
0x14001108c  lea     rdx, aHbevtpdeleteev_1; "HbEvtpDeleteEventLogWorker"
0x140011093  mov     ecx, r12d
0x140011096  call    HbpTraceEvent
0x14001109b  lea     rcx, HbEvtpCompleteBufferAsyncEvent; Event
0x1400110a2  mov     [r14+150h], esi
0x1400110a9  mov     qword ptr [r14+148h], 0FFFFFFFFFFFFFFFFh
0x1400110b4  call    cs:__imp_KeClearEvent
0x1400110bb  nop     dword ptr [rax+rax+00h]
0x1400110c0  test    bl, bl
0x1400110c2  jz      short loc_1400110D9
0x1400110c4  test    rdi, rdi
0x1400110c7  jz      short loc_1400110D9
0x1400110c9  lea     rcx, [rdi+18h]; RunRef
0x1400110cd  call    cs:__imp_ExReInitializeRundownProtection
0x1400110d4  nop     dword ptr [rax+rax+00h]
0x1400110d9  test    ebp, ebp
0x1400110db  jns     short loc_14001110D
0x1400110dd  lea     r9, aRoutineFailedW; "Routine failed with 0x%x"
0x1400110e4  mov     dword ptr [rsp+88h+var_68], ebp
0x1400110e8  mov     r8d, 7DDh
0x1400110ee  lea     rdx, aHbevtpdeleteev_1; "HbEvtpDeleteEventLogWorker"
0x1400110f5  xor     ecx, ecx
0x1400110f7  call    HbpTraceEvent
0x1400110fc  xor     r8d, r8d; UserData
0x1400110ff  lea     rcx, HV_EVENTLOG_ENABLE_ETW_TRACE_FAILED; EventDescriptor
0x140011106  xor     edx, edx; UserDataCount
0x140011108  call    HbEvtpWriteEventLog
0x14001110d  add     rsp, 48h
0x140011111  pop     r15
0x140011113  pop     r14
0x140011115  pop     r13
0x140011117  pop     r12
0x140011119  pop     rdi
0x14001111a  pop     rsi
0x14001111b  pop     rbp
0x14001111c  pop     rbx
0x14001111d  retn
```
