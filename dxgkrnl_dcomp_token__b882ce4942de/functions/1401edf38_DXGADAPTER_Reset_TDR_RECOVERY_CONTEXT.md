# DXGADAPTER::Reset(_TDR_RECOVERY_CONTEXT *)

- ea: `0x1401edf38`
- end: `0x1401ee69c`
- name: `?Reset@DXGADAPTER@@QEAAJPEAU_TDR_RECOVERY_CONTEXT@@@Z`
- size: `1892`
- prototype: `__int64 __fastcall(DXGADAPTER *__hidden this, struct _TDR_RECOVERY_CONTEXT *)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1402392c0`

## callees

- `0x14001b890`
- `0x14001d6b4`
- `0x14001dc4c`
- `0x14002fdc0`
- `0x1400382d8`
- `0x14004b398`
- `0x14006834c`
- `0x1400a01e0`
- `0x14019a850`
- `0x1401e5dfc`
- `0x1401ec00c`
- `0x1401edf38`
- `0x1401ef150`
- `0x1401f6d28`
- `0x1401fa0f4`
- `0x1402686c4`
- `0x140333e70`
- `0x140333f00`
- `0x1403a84cc`
- `0x1403a9b68`
- `0x1403ecdc8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ee0a4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ee0a4`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1401ee2e5`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1401ee2e5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ee093`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ee2d0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ee093`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ee2d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ee0e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ee2f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ee5fd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ee0e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ee2f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ee5fd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ee0d5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ee5f1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ee0d5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ee5f1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401ee67c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401ee67c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401ee402`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401ee468`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401ee402`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401ee468`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ee645`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ee645`
- `ntoskrnl!KeResetEvent` at `0x1401ee0f6`
- `ntoskrnl!KeResetEvent` at `0x1401ee34d`
- `ntoskrnl!KeResetEvent` at `0x1401ee5b8`
- `ntoskrnl!KeResetEvent` at `0x1401ee0f6`
- `ntoskrnl!KeResetEvent` at `0x1401ee34d`
- `ntoskrnl!KeResetEvent` at `0x1401ee5b8`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401ee32b`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401ee453`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401ee32b`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401ee453`
- `ntoskrnl!KeSetEvent` at `0x1401edfdc`
- `ntoskrnl!KeSetEvent` at `0x1401ee222`
- `ntoskrnl!KeSetEvent` at `0x1401ee65a`
- `ntoskrnl!KeSetEvent` at `0x1401edfdc`
- `ntoskrnl!KeSetEvent` at `0x1401ee222`
- `ntoskrnl!KeSetEvent` at `0x1401ee65a`
- `watchdog!WdLogSingleEntry0` at `0x1401edf68`
- `watchdog!WdLogSingleEntry0` at `0x1401edff7`
- `watchdog!WdLogSingleEntry0` at `0x1401ee10c`
- `watchdog!WdLogSingleEntry0` at `0x1401ee360`
- `watchdog!WdLogSingleEntry0` at `0x1401ee4fa`
- `watchdog!WdLogSingleEntry0` at `0x1401ee55b`
- `watchdog!WdLogSingleEntry0` at `0x1401edf68`
- `watchdog!WdLogSingleEntry0` at `0x1401edff7`
- `watchdog!WdLogSingleEntry0` at `0x1401ee10c`
- `watchdog!WdLogSingleEntry0` at `0x1401ee360`
- `watchdog!WdLogSingleEntry0` at `0x1401ee4fa`
- `watchdog!WdLogSingleEntry0` at `0x1401ee55b`

## string_xrefs

- `0x1401ee11d`: `OldCoreAccess != 0`
- `0x1401ee371`: `OldCoreAccess != 0`

## pseudocode

```c
__int64 __fastcall DXGADAPTER::Reset(DXGADAPTER *this, struct _TDR_RECOVERY_CONTEXT *a2)
{
  struct _TDR_RECOVERY_CONTEXT *v2; // rdi
  struct _KTHREAD *CurrentThread; // r14
  ADAPTER_RENDER **v5; // rsi
  char *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r8
  struct _TDR_RECOVERY_CONTEXT *v9; // rdx
  char *v10; // r14
  struct _KTHREAD *v11; // r14
  __int64 v12; // r8
  BOOLEAN i; // al
  __int64 v14; // r8
  int FirstProfilerInterface; // eax
  ADAPTER_RENDER *v16; // rcx
  ADAPTER_RENDER *v17; // rcx
  struct _TDR_RECOVERY_CONTEXT *v18; // rdx
  ADAPTER_DISPLAY *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  char v23; // [rsp+A0h] [rbp+8h] BYREF
  char v24; // [rsp+A1h] [rbp+9h]
  struct _TDR_RECOVERY_CONTEXT *v25; // [rsp+A8h] [rbp+10h]
  struct _KTHREAD *v26; // [rsp+B0h] [rbp+18h]
  union _LARGE_INTEGER Interval; // [rsp+B8h] [rbp+20h] BYREF

  v25 = a2;
  v2 = a2;
  if ( !a2 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 8920;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pTdrContext", 8920, 0, 0, 0, 0);
  }
  CurrentThread = KeGetCurrentThread();
  v26 = CurrentThread;
  DxgkpAcquireTestLockForStopReset();
  if ( !DXGADAPTER::IsDxgmms2(this) )
    KeSetEvent((PRKEVENT)((char *)this + 3208), 0, 0);
  v5 = (ADAPTER_RENDER **)((char *)this + 3240);
  if ( !*((_QWORD *)this + 405) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 8938;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"this->IsRenderAdapter()", 8938, 0, 0, 0, 0);
  }
  v24 = 0;
  DXGCRITICALREGION::Enter((DXGCRITICALREGION *)&v23);
  if ( !DXGADAPTER::IsDxgmms2(this) )
  {
    while ( 1 )
    {
      KeEnterCriticalRegion();
      if ( (unsigned __int8)ExTryAcquirePushLockExclusiveEx((char *)this + 136, 0) )
        break;
      KeLeaveCriticalRegion();
      ADAPTER_RENDER::FlushScheduler(*v5, 4, 0xFFFFFFFFLL);
      Interval.QuadPart = -100000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    *((_QWORD *)this + 18) = KeGetCurrentThread();
    if ( !KeResetEvent((PRKEVENT)this + 2) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 9070;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"OldCoreAccess != 0", 9070, 0, 0, 0, 0);
    }
    if ( bTracingEnabled
      && (qword_14015C500 & 0x1000000) != 0
      && (qword_14015C500 & 0x2000) == 0
      && (Microsoft_Windows_DxgKrnlEnableBits & 0x200000000000LL) != 0 )
    {
      McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, EventPreAcquireAdapterLock, v12, this, 1);
    }
    for ( i = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 21), 0);
          !i;
          i = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 21), 0) )
    {
      *((_DWORD *)this + 1257) = 2;
      FirstProfilerInterface = DXGGLOBAL::GetFirstProfilerInterface();
      v16 = *v5;
      *((_DWORD *)this + 1258) = FirstProfilerInterface;
      ADAPTER_RENDER::FlushScheduler(v16, 4, 0xFFFFFFFFLL);
      Interval.QuadPart = -100000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    if ( bTracingEnabled
      && (qword_14015C500 & 0x1000000) != 0
      && (qword_14015C500 & 0x2000) == 0
      && (Microsoft_Windows_DxgKrnlEnableBits & 0x200000000000LL) != 0 )
    {
      McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, EventPostAcquireAdapterLock, v14, this, 1);
    }
    *((_DWORD *)this + 44) = 2;
    v11 = v26;
    goto LABEL_48;
  }
  *((_QWORD *)this + 406) = CurrentThread;
  if ( CurrentThread == *((struct _KTHREAD **)v2 + 363) )
  {
    v10 = (char *)this + 3240;
    goto LABEL_27;
  }
  v6 = (char *)this + 136;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx((char *)this + 136, 0);
  *((_QWORD *)this + 18) = KeGetCurrentThread();
  if ( *((_DWORD *)this + 50) != 1 )
  {
    *((_QWORD *)this + 18) = 0;
    ExReleasePushLockExclusiveEx((char *)this + 136, 0);
    KeLeaveCriticalRegion();
    goto LABEL_62;
  }
  if ( !KeResetEvent((PRKEVENT)this + 2) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 8973;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"OldCoreAccess != 0", 8973, 0, 0, 0, 0);
  }
  if ( bTracingEnabled
    && (qword_14015C500 & 0x1000000) != 0
    && (qword_14015C500 & 0x2000) == 0
    && (Microsoft_Windows_DxgKrnlEnableBits & 0x200000000000LL) != 0 )
  {
    McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, EventPreAcquireAdapterLock, v7, this, 1);
  }
  DXGADAPTER::AcquireCoreResourceExclusiveWithTracking(this, 2);
  if ( bTracingEnabled
    && (qword_14015C500 & 0x1000000) != 0
    && (qword_14015C500 & 0x2000) == 0
    && (Microsoft_Windows_DxgKrnlEnableBits & 0x200000000000LL) != 0 )
  {
    McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, EventPostAcquireAdapterLock, v8, this, 1);
  }
  v9 = v25;
  *((_DWORD *)this + 44) = 2;
  if ( !*((_QWORD *)v9 + 363) )
  {
    v10 = (char *)this + 3240;
    v2 = v9;
LABEL_27:
    KeSetEvent((PRKEVENT)((char *)this + 3208), 0, 0);
    VIDSCH_EXPORT::VidSchSetRecoveryThread(
      *(VIDSCH_EXPORT **)(*(_QWORD *)v10 + 736LL),
      *(struct _VIDSCH_GLOBAL **)(*(_QWORD *)v10 + 744LL),
      *((struct _KTHREAD **)this + 406));
    DXGADAPTER::BlockAndDrainIoRingAccess(this);
    DXGADAPTER::PrepareToReset(this, v2);
    ADAPTER_RENDER::FlushScheduler(*v5, 4, 0xFFFFFFFFLL);
    ADAPTER_RENDER::FlushDeferredDestructions(*v5);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(*((_QWORD *)*v5 + 95) + 8LL) + 1104LL))(*((_QWORD *)*v5 + 96));
    v11 = v26;
    if ( v26 != *((struct _KTHREAD **)v2 + 363) )
      ADAPTER_RENDER::SuspendVidMmWorkerThread(*v5, 0, 0);
    ADAPTER_RENDER::FlushScheduler(*v5, 4, 0xFFFFFFFFLL);
LABEL_48:
    ADAPTER_RENDER::FlushScheduler(*v5, 4, 0xFFFFFFFFLL);
    TdrCollectDbgInfoStage2(v2);
    v17 = *v5;
    *((_BYTE *)this + 3165) = 0;
    if ( (int)ADAPTER_RENDER::Reset(v17, v2) < 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 9114;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(Status)", 9114, 0, 0, 0, 0);
    }
    v19 = (ADAPTER_DISPLAY *)*((_QWORD *)this + 404);
    if ( v19 && (int)ADAPTER_DISPLAY::Reset(v19, v18) < 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 9122;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(Status)", 9122, 0, 0, 0, 0);
    }
    DXGADAPTER::UnblockIoRingAccess(this);
    *((_QWORD *)this + 406) = 0;
    KeResetEvent((PRKEVENT)((char *)this + 3208));
    v6 = (char *)this + 136;
    goto LABEL_54;
  }
  v11 = v26;
LABEL_54:
  if ( !DXGADAPTER::IsDxgmms2(this) || *(struct _KTHREAD **)(v20 + 2904) != v11 )
  {
    *((_QWORD *)v6 + 1) = 0;
    ExReleasePushLockExclusiveEx(v6, 0);
    KeLeaveCriticalRegion();
    if ( bTracingEnabled
      && (qword_14015C500 & 0x1000000) != 0
      && (qword_14015C500 & 0x2000) == 0
      && (Microsoft_Windows_DxgKrnlEnableBits & 0x200000000000LL) != 0 )
    {
      McTemplateK0p_EtwWriteTransfer(&DxgkControlGuid_Context, EventReleaseAdapterLock, v21, this);
    }
    ExReleaseResourceLite(*((PERESOURCE *)this + 21));
    KeSetEvent((PRKEVENT)this + 2, 0, 0);
  }
LABEL_62:
  DXGCRITICALREGION::~DXGCRITICALREGION((DXGCRITICALREGION *)&v23);
  ExReleasePushLockSharedEx(&qword_14015E7F0, 0);
  return 0;
}

```

## disassembly

```asm
0x1401edf38  mov     [rsp+arg_8], rdx
0x1401edf3d  push    rbx
0x1401edf3e  push    rbp
0x1401edf3f  push    rsi
0x1401edf40  push    rdi
0x1401edf41  push    r12
0x1401edf43  push    r13
0x1401edf45  push    r14
0x1401edf47  push    r15
0x1401edf49  sub     rsp, 58h
0x1401edf4d  or      r13d, 0FFFFFFFFh
0x1401edf51  xor     r15d, r15d
0x1401edf54  mov     rdi, rdx
0x1401edf57  mov     rbx, rcx
0x1401edf5a  mov     r12d, 1
0x1401edf60  test    rdx, rdx
0x1401edf63  jnz     short loc_1401EDFAE
0x1401edf65  mov     ecx, r12d
0x1401edf68  call    cs:__imp_WdLogSingleEntry0
0x1401edf6f  nop     dword ptr [rax+rax+00h]
0x1401edf74  mov     [rsp+98h+var_58], r15
0x1401edf79  lea     r9, aPtdrcontext; "pTdrContext"
0x1401edf80  mov     [rsp+98h+var_60], r15
0x1401edf85  mov     eax, 22D8h
0x1401edf8a  mov     [rsp+98h+var_68], r15
0x1401edf8f  mov     r8d, r13d
0x1401edf92  mov     [rsp+98h+var_70], r15
0x1401edf97  mov     edx, 40002h
0x1401edf9c  xor     ecx, ecx
0x1401edf9e  mov     [rsp+98h+var_78], rax
0x1401edfa3  mov     cs:WdLogGlobalForLineNumber, eax
0x1401edfa9  call    DxgkLogInternalTriageEvent
0x1401edfae  mov     r14, gs:188h
0x1401edfb7  mov     [rsp+98h+arg_10], r14
0x1401edfbf  call    ?DxgkpAcquireTestLockForStopReset@@YAXXZ; DxgkpAcquireTestLockForStopReset(void)
0x1401edfc4  mov     rcx, rbx; this
0x1401edfc7  call    ?IsDxgmms2@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDxgmms2(void)
0x1401edfcc  test    al, al
0x1401edfce  jnz     short loc_1401EDFE8
0x1401edfd0  lea     rcx, [rbx+0C88h]; Event
0x1401edfd7  xor     r8d, r8d; Wait
0x1401edfda  xor     edx, edx; Increment
0x1401edfdc  call    cs:__imp_KeSetEvent
0x1401edfe3  nop     dword ptr [rax+rax+00h]
0x1401edfe8  lea     rsi, [rbx+0CA8h]
0x1401edfef  cmp     [rsi], r15
0x1401edff2  jnz     short loc_1401EE03D
0x1401edff4  mov     ecx, r12d
0x1401edff7  call    cs:__imp_WdLogSingleEntry0
0x1401edffe  nop     dword ptr [rax+rax+00h]
0x1401ee003  mov     [rsp+98h+var_58], r15
0x1401ee008  lea     r9, aThisIsrenderad; "this->IsRenderAdapter()"
0x1401ee00f  mov     [rsp+98h+var_60], r15
0x1401ee014  mov     eax, 22EAh
0x1401ee019  mov     [rsp+98h+var_68], r15
0x1401ee01e  mov     r8d, r13d
0x1401ee021  mov     [rsp+98h+var_70], r15
0x1401ee026  mov     edx, 40002h
0x1401ee02b  xor     ecx, ecx
0x1401ee02d  mov     [rsp+98h+var_78], rax
0x1401ee032  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ee038  call    DxgkLogInternalTriageEvent
0x1401ee03d  lea     rcx, [rsp+98h+arg_0]; this
0x1401ee045  mov     [rsp+98h+arg_1], r15b
0x1401ee04d  call    ?Enter@DXGCRITICALREGION@@QEAAXXZ; DXGCRITICALREGION::Enter(void)
0x1401ee052  mov     rcx, rbx; this
0x1401ee055  call    ?IsDxgmms2@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDxgmms2(void)
0x1401ee05a  test    al, al
0x1401ee05c  jz      loc_1401EE2D0
0x1401ee062  mov     [rbx+0CB0h], r14
0x1401ee069  lea     r13, DxgkControlGuid_Context
0x1401ee070  mov     r12d, 1000000h
0x1401ee076  mov     r15d, 2000h
0x1401ee07c  mov     bpl, 20h ; ' '
0x1401ee07f  cmp     r14, [rdi+0B58h]
0x1401ee086  jz      loc_1401EE213
0x1401ee08c  lea     rdi, [rbx+88h]
0x1401ee093  call    cs:__imp_KeEnterCriticalRegion
0x1401ee09a  nop     dword ptr [rax+rax+00h]
0x1401ee09f  xor     edx, edx
0x1401ee0a1  mov     rcx, rdi
0x1401ee0a4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401ee0ab  nop     dword ptr [rax+rax+00h]
0x1401ee0b0  mov     rax, gs:188h
0x1401ee0b9  mov     [rdi+8], rax
0x1401ee0bd  mov     eax, [rbx+0C8h]
0x1401ee0c3  cmp     eax, 1
0x1401ee0c6  jz      short loc_1401EE0F2
0x1401ee0c8  xor     edx, edx
0x1401ee0ca  mov     qword ptr [rdi+8], 0
0x1401ee0d2  mov     rcx, rdi
0x1401ee0d5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401ee0dc  nop     dword ptr [rax+rax+00h]
0x1401ee0e1  call    cs:__imp_KeLeaveCriticalRegion
0x1401ee0e8  nop     dword ptr [rax+rax+00h]
0x1401ee0ed  jmp     loc_1401EE666
0x1401ee0f2  lea     rcx, [rbx+30h]; Event
0x1401ee0f6  call    cs:__imp_KeResetEvent
0x1401ee0fd  nop     dword ptr [rax+rax+00h]
0x1401ee102  xor     r14d, r14d
0x1401ee105  test    eax, eax
0x1401ee107  jnz     short loc_1401EE153
0x1401ee109  lea     ecx, [rax+1]
0x1401ee10c  call    cs:__imp_WdLogSingleEntry0
0x1401ee113  nop     dword ptr [rax+rax+00h]
0x1401ee118  mov     [rsp+98h+var_58], r14
0x1401ee11d  lea     r9, aOldcoreaccess0; "OldCoreAccess != 0"
0x1401ee124  mov     [rsp+98h+var_60], r14
0x1401ee129  mov     eax, 230Dh
0x1401ee12e  mov     [rsp+98h+var_68], r14
0x1401ee133  or      r8d, 0FFFFFFFFh
0x1401ee137  mov     [rsp+98h+var_70], r14
0x1401ee13c  mov     edx, 40002h
0x1401ee141  xor     ecx, ecx
0x1401ee143  mov     [rsp+98h+var_78], rax
0x1401ee148  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ee14e  call    DxgkLogInternalTriageEvent
0x1401ee153  cmp     cs:bTracingEnabled, r14b
0x1401ee15a  jz      short loc_1401EE190
0x1401ee15c  mov     rax, cs:qword_14015C500
0x1401ee163  test    r12, rax
0x1401ee166  jz      short loc_1401EE190
0x1401ee168  test    r15, rax
0x1401ee16b  jnz     short loc_1401EE190
0x1401ee16d  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+5, bpl
0x1401ee174  jz      short loc_1401EE190
0x1401ee176  mov     r9, rbx
0x1401ee179  mov     dword ptr [rsp+98h+var_78], 1
0x1401ee181  lea     rdx, EventPreAcquireAdapterLock
0x1401ee188  mov     rcx, r13
0x1401ee18b  call    McTemplateK0pt_EtwWriteTransfer
0x1401ee190  xor     r8d, r8d
0x1401ee193  mov     rcx, rbx
0x1401ee196  lea     r14d, [r8+2]
0x1401ee19a  mov     edx, r14d
0x1401ee19d  call    ?AcquireCoreResourceExclusiveWithTracking@DXGADAPTER@@AEAAXW4DXGADAPTER_EXCLUSIVEACCESS_REASON@@_N@Z; DXGADAPTER::AcquireCoreResourceExclusiveWithTracking(DXGADAPTER_EXCLUSIVEACCESS_REASON,bool)
0x1401ee1a2  cmp     cs:bTracingEnabled, 0
0x1401ee1a9  jz      short loc_1401EE1DF
0x1401ee1ab  mov     rax, cs:qword_14015C500
0x1401ee1b2  test    r12, rax
0x1401ee1b5  jz      short loc_1401EE1DF
0x1401ee1b7  test    r15, rax
0x1401ee1ba  jnz     short loc_1401EE1DF
0x1401ee1bc  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+5, bpl
0x1401ee1c3  jz      short loc_1401EE1DF
0x1401ee1c5  mov     r9, rbx
0x1401ee1c8  mov     dword ptr [rsp+98h+var_78], 1
0x1401ee1d0  lea     rdx, EventPostAcquireAdapterLock
0x1401ee1d7  mov     rcx, r13
0x1401ee1da  call    McTemplateK0pt_EtwWriteTransfer
0x1401ee1df  mov     rdx, [rsp+98h+arg_8]
0x1401ee1e7  mov     [rbx+0B0h], r14d
0x1401ee1ee  cmp     qword ptr [rdx+0B58h], 0
0x1401ee1f6  jnz     short loc_1401EE204
0x1401ee1f8  lea     r14, [rbx+0CA8h]
0x1401ee1ff  mov     rdi, rdx
0x1401ee202  jmp     short loc_1401EE216
0x1401ee204  mov     r14, [rsp+98h+arg_10]
0x1401ee20c  xor     esi, esi
0x1401ee20e  jmp     loc_1401EE5D3
0x1401ee213  mov     r14, rsi
0x1401ee216  lea     rcx, [rbx+0C88h]; Event
0x1401ee21d  xor     r8d, r8d; Wait
0x1401ee220  xor     edx, edx; Increment
0x1401ee222  call    cs:__imp_KeSetEvent
0x1401ee229  nop     dword ptr [rax+rax+00h]
0x1401ee22e  mov     rcx, [r14]
0x1401ee231  mov     r8, [rbx+0CB0h]; struct _KTHREAD *
0x1401ee238  mov     rdx, [rcx+2E8h]; struct _VIDSCH_GLOBAL *
0x1401ee23f  mov     rcx, [rcx+2E0h]; this
0x1401ee246  call    ?VidSchSetRecoveryThread@VIDSCH_EXPORT@@QEAAXPEAU_VIDSCH_GLOBAL@@PEAU_KTHREAD@@@Z; VIDSCH_EXPORT::VidSchSetRecoveryThread(_VIDSCH_GLOBAL *,_KTHREAD *)
0x1401ee24b  mov     rcx, rbx; this
0x1401ee24e  call    ?BlockAndDrainIoRingAccess@DXGADAPTER@@QEAAJXZ; DXGADAPTER::BlockAndDrainIoRingAccess(void)
0x1401ee253  mov     rdx, rdi; struct _TDR_RECOVERY_CONTEXT *
0x1401ee256  mov     rcx, rbx; this
0x1401ee259  call    ?PrepareToReset@DXGADAPTER@@QEAAJPEAU_TDR_RECOVERY_CONTEXT@@@Z; DXGADAPTER::PrepareToReset(_TDR_RECOVERY_CONTEXT *)
0x1401ee25e  mov     rcx, [rsi]
0x1401ee261  xor     r9d, r9d
0x1401ee264  or      r8d, 0FFFFFFFFh
0x1401ee268  lea     edx, [r9+4]
0x1401ee26c  call    ?FlushScheduler@ADAPTER_RENDER@@QEAAJW4DXGADAPTER_FLUSHSCHEDULER_REASON@@IH@Z; ADAPTER_RENDER::FlushScheduler(DXGADAPTER_FLUSHSCHEDULER_REASON,uint,int)
0x1401ee271  mov     rcx, [rsi]; this
0x1401ee274  call    ?FlushDeferredDestructions@ADAPTER_RENDER@@AEAAXXZ; ADAPTER_RENDER::FlushDeferredDestructions(void)
0x1401ee279  mov     rcx, [rsi]
0x1401ee27c  mov     rax, [rcx+2F8h]
0x1401ee283  mov     rcx, [rcx+300h]
0x1401ee28a  mov     rdx, [rax+8]
0x1401ee28e  mov     rax, [rdx+450h]
0x1401ee295  call    _guard_dispatch_icall
0x1401ee29a  mov     r14, [rsp+98h+arg_10]
0x1401ee2a2  cmp     r14, [rdi+0B58h]
0x1401ee2a9  jz      short loc_1401EE2B8
0x1401ee2ab  mov     rcx, [rsi]
0x1401ee2ae  xor     r8d, r8d
0x1401ee2b1  xor     edx, edx
0x1401ee2b3  call    ?SuspendVidMmWorkerThread@ADAPTER_RENDER@@AEAAXW4VIDMM_WORKER_THREAD_SUSPEND_REASON@@E@Z; ADAPTER_RENDER::SuspendVidMmWorkerThread(VIDMM_WORKER_THREAD_SUSPEND_REASON,uchar)
0x1401ee2b8  mov     rcx, [rsi]
0x1401ee2bb  xor     r9d, r9d
0x1401ee2be  or      r8d, 0FFFFFFFFh
0x1401ee2c2  lea     edx, [r9+4]
0x1401ee2c6  call    ?FlushScheduler@ADAPTER_RENDER@@QEAAJW4DXGADAPTER_FLUSHSCHEDULER_REASON@@IH@Z; ADAPTER_RENDER::FlushScheduler(DXGADAPTER_FLUSHSCHEDULER_REASON,uint,int)
0x1401ee2cb  jmp     loc_1401EE4C4
0x1401ee2d0  call    cs:__imp_KeEnterCriticalRegion
0x1401ee2d7  nop     dword ptr [rax+rax+00h]
0x1401ee2dc  xor     edx, edx
0x1401ee2de  lea     rcx, [rbx+88h]
0x1401ee2e5  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x1401ee2ec  nop     dword ptr [rax+rax+00h]
0x1401ee2f1  test    al, al
0x1401ee2f3  jnz     short loc_1401EE339
0x1401ee2f5  call    cs:__imp_KeLeaveCriticalRegion
0x1401ee2fc  nop     dword ptr [rax+rax+00h]
0x1401ee301  mov     rcx, [rsi]
0x1401ee304  xor     r9d, r9d
0x1401ee307  mov     r8d, r13d
0x1401ee30a  lea     edx, [r9+4]
0x1401ee30e  call    ?FlushScheduler@ADAPTER_RENDER@@QEAAJW4DXGADAPTER_FLUSHSCHEDULER_REASON@@IH@Z; ADAPTER_RENDER::FlushScheduler(DXGADAPTER_FLUSHSCHEDULER_REASON,uint,int)
0x1401ee313  lea     r8, [rsp+98h+Interval]; Interval
0x1401ee31b  mov     qword ptr [rsp+98h+Interval], 0FFFFFFFFFFFE7960h
0x1401ee327  xor     edx, edx; Alertable
0x1401ee329  xor     ecx, ecx; WaitMode
0x1401ee32b  call    cs:__imp_KeDelayExecutionThread
0x1401ee332  nop     dword ptr [rax+rax+00h]
0x1401ee337  jmp     short loc_1401EE2D0
0x1401ee339  mov     rax, gs:188h
0x1401ee342  lea     rcx, [rbx+30h]; Event
0x1401ee346  mov     [rbx+90h], rax
0x1401ee34d  call    cs:__imp_KeResetEvent
0x1401ee354  nop     dword ptr [rax+rax+00h]
0x1401ee359  test    eax, eax
0x1401ee35b  jnz     short loc_1401EE3A6
0x1401ee35d  mov     ecx, r12d
0x1401ee360  call    cs:__imp_WdLogSingleEntry0
0x1401ee367  nop     dword ptr [rax+rax+00h]
0x1401ee36c  mov     [rsp+98h+var_58], r15
0x1401ee371  lea     r9, aOldcoreaccess0; "OldCoreAccess != 0"
0x1401ee378  mov     [rsp+98h+var_60], r15
0x1401ee37d  mov     eax, 236Eh
0x1401ee382  mov     [rsp+98h+var_68], r15
0x1401ee387  mov     r8d, r13d
0x1401ee38a  mov     [rsp+98h+var_70], r15
0x1401ee38f  mov     edx, 40002h
0x1401ee394  xor     ecx, ecx
0x1401ee396  mov     [rsp+98h+var_78], rax
0x1401ee39b  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ee3a1  call    DxgkLogInternalTriageEvent
0x1401ee3a6  cmp     cs:bTracingEnabled, 0
0x1401ee3ad  lea     r13, DxgkControlGuid_Context
0x1401ee3b4  mov     r12d, 1000000h
0x1401ee3ba  mov     r15d, 2000h
0x1401ee3c0  mov     bpl, 20h ; ' '
0x1401ee3c3  jz      short loc_1401EE3F9
0x1401ee3c5  mov     rax, cs:qword_14015C500
0x1401ee3cc  test    r12, rax
0x1401ee3cf  jz      short loc_1401EE3F9
0x1401ee3d1  test    r15, rax
0x1401ee3d4  jnz     short loc_1401EE3F9
0x1401ee3d6  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+5, bpl
0x1401ee3dd  jz      short loc_1401EE3F9
0x1401ee3df  mov     r9, rbx
0x1401ee3e2  mov     dword ptr [rsp+98h+var_78], 1
0x1401ee3ea  lea     rdx, EventPreAcquireAdapterLock
0x1401ee3f1  mov     rcx, r13
0x1401ee3f4  call    McTemplateK0pt_EtwWriteTransfer
0x1401ee3f9  mov     rcx, [rbx+0A8h]; Resource
0x1401ee400  xor     edx, edx; Wait
0x1401ee402  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401ee409  nop     dword ptr [rax+rax+00h]
0x1401ee40e  mov     r14d, 2
0x1401ee414  jmp     short loc_1401EE474
0x1401ee416  mov     [rbx+13A4h], r14d
0x1401ee41d  call    ?GetFirstProfilerInterface@DXGGLOBAL@@SA?AW4_DXGKETW_PROFILER_TYPE@@XZ; DXGGLOBAL::GetFirstProfilerInterface(void)
0x1401ee422  mov     rcx, [rsi]
0x1401ee425  xor     r9d, r9d
0x1401ee428  or      r8d, 0FFFFFFFFh
0x1401ee42c  mov     [rbx+13A8h], eax
0x1401ee432  lea     edx, [r9+4]
0x1401ee436  call    ?FlushScheduler@ADAPTER_RENDER@@QEAAJW4DXGADAPTER_FLUSHSCHEDULER_REASON@@IH@Z; ADAPTER_RENDER::FlushScheduler(DXGADAPTER_FLUSHSCHEDULER_REASON,uint,int)
0x1401ee43b  lea     r8, [rsp+98h+Interval]; Interval
0x1401ee443  mov     qword ptr [rsp+98h+Interval], 0FFFFFFFFFFFE7960h
0x1401ee44f  xor     edx, edx; Alertable
0x1401ee451  xor     ecx, ecx; WaitMode
0x1401ee453  call    cs:__imp_KeDelayExecutionThread
0x1401ee45a  nop     dword ptr [rax+rax+00h]
0x1401ee45f  mov     rcx, [rbx+0A8h]; Resource
0x1401ee466  xor     edx, edx; Wait
0x1401ee468  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401ee46f  nop     dword ptr [rax+rax+00h]
0x1401ee474  test    al, al
0x1401ee476  jz      short loc_1401EE416
0x1401ee478  cmp     cs:bTracingEnabled, 0
0x1401ee47f  jz      short loc_1401EE4B5
0x1401ee481  mov     rax, cs:qword_14015C500
0x1401ee488  test    r12, rax
0x1401ee48b  jz      short loc_1401EE4B5
0x1401ee48d  test    r15, rax
0x1401ee490  jnz     short loc_1401EE4B5
0x1401ee492  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+5, bpl
0x1401ee499  jz      short loc_1401EE4B5
0x1401ee49b  mov     r9, rbx
  ... truncated ...
```
