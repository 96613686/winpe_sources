# DXGADAPTER::Reset(_TDR_RECOVERY_CONTEXT *)

- ea: `0x1401f0308`
- end: `0x1401f0a6e`
- name: `?Reset@DXGADAPTER@@QEAAJPEAU_TDR_RECOVERY_CONTEXT@@@Z`
- size: `1894`
- prototype: `__int64 __fastcall(DXGADAPTER *__hidden this, struct _TDR_RECOVERY_CONTEXT *)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x14023be20`

## callees

- `0x14001b9c0`
- `0x14001d884`
- `0x14001de1c`
- `0x14002ff90`
- `0x140038538`
- `0x14004b598`
- `0x14006881c`
- `0x1400a0cb0`
- `0x14019e850`
- `0x1401e817c`
- `0x1401ee3dc`
- `0x1401f0308`
- `0x1401f1520`
- `0x1401f9108`
- `0x1401fc4d4`
- `0x14026dc84`
- `0x14033a890`
- `0x14033a920`
- `0x1403a92ac`
- `0x1403aa948`
- `0x1403ed288`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401f0474`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401f0474`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1401f06b7`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1401f06b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f0463`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f06a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f0463`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f06a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f04b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f06c7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f09cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f04b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f06c7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f09cf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401f04a5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401f09c3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401f04a5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401f09c3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401f0a4e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401f0a4e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401f07d4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401f083a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401f07d4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401f083a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401f0a17`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401f0a17`
- `ntoskrnl!KeResetEvent` at `0x1401f04c6`
- `ntoskrnl!KeResetEvent` at `0x1401f071f`
- `ntoskrnl!KeResetEvent` at `0x1401f098a`
- `ntoskrnl!KeResetEvent` at `0x1401f04c6`
- `ntoskrnl!KeResetEvent` at `0x1401f071f`
- `ntoskrnl!KeResetEvent` at `0x1401f098a`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401f06fd`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401f0825`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401f06fd`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401f0825`
- `ntoskrnl!KeSetEvent` at `0x1401f03ac`
- `ntoskrnl!KeSetEvent` at `0x1401f05f2`
- `ntoskrnl!KeSetEvent` at `0x1401f0a2c`
- `ntoskrnl!KeSetEvent` at `0x1401f03ac`
- `ntoskrnl!KeSetEvent` at `0x1401f05f2`
- `ntoskrnl!KeSetEvent` at `0x1401f0a2c`
- `watchdog!WdLogSingleEntry0` at `0x1401f0338`
- `watchdog!WdLogSingleEntry0` at `0x1401f03c7`
- `watchdog!WdLogSingleEntry0` at `0x1401f04dc`
- `watchdog!WdLogSingleEntry0` at `0x1401f0732`
- `watchdog!WdLogSingleEntry0` at `0x1401f08cc`
- `watchdog!WdLogSingleEntry0` at `0x1401f092d`
- `watchdog!WdLogSingleEntry0` at `0x1401f0338`
- `watchdog!WdLogSingleEntry0` at `0x1401f03c7`
- `watchdog!WdLogSingleEntry0` at `0x1401f04dc`
- `watchdog!WdLogSingleEntry0` at `0x1401f0732`
- `watchdog!WdLogSingleEntry0` at `0x1401f08cc`
- `watchdog!WdLogSingleEntry0` at `0x1401f092d`

## string_xrefs

- `0x1401f04ed`: `OldCoreAccess != 0`
- `0x1401f0743`: `OldCoreAccess != 0`

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
  __int64 v14; // rcx
  __int64 v15; // r8
  int FirstProfilerInterface; // eax
  ADAPTER_RENDER *v17; // rcx
  ADAPTER_RENDER *v18; // rcx
  struct _TDR_RECOVERY_CONTEXT *v19; // rdx
  ADAPTER_DISPLAY *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  char v24; // [rsp+A0h] [rbp+8h] BYREF
  char v25; // [rsp+A1h] [rbp+9h]
  struct _TDR_RECOVERY_CONTEXT *v26; // [rsp+A8h] [rbp+10h]
  struct _KTHREAD *v27; // [rsp+B0h] [rbp+18h]
  union _LARGE_INTEGER Interval; // [rsp+B8h] [rbp+20h] BYREF

  v26 = a2;
  v2 = a2;
  if ( !a2 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 8920;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pTdrContext", 8920, 0, 0, 0, 0);
  }
  CurrentThread = KeGetCurrentThread();
  v27 = CurrentThread;
  DxgkpAcquireTestLockForStopReset();
  if ( !DXGADAPTER::IsDxgmms2(this) )
    KeSetEvent((PRKEVENT)((char *)this + 3224), 0, 0);
  v5 = (ADAPTER_RENDER **)((char *)this + 3256);
  if ( !*((_QWORD *)this + 407) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 8938;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"this->IsRenderAdapter()", 8938, 0, 0, 0, 0);
  }
  v25 = 0;
  DXGCRITICALREGION::Enter((DXGCRITICALREGION *)&v24);
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
      && (qword_1401604F0 & 0x1000000) != 0
      && (qword_1401604F0 & 0x2000) == 0
      && (Microsoft_Windows_DxgKrnlEnableBits & 0x200000000000LL) != 0 )
    {
      McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, EventPreAcquireAdapterLock, v12, this);
    }
    for ( i = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 21), 0);
          !i;
          i = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 21), 0) )
    {
      *((_DWORD *)this + 1261) = 2;
      FirstProfilerInterface = DXGGLOBAL::GetFirstProfilerInterface(v14);
      v17 = *v5;
      *((_DWORD *)this + 1262) = FirstProfilerInterface;
      ADAPTER_RENDER::FlushScheduler(v17, 4, 0xFFFFFFFFLL);
      Interval.QuadPart = -100000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    if ( bTracingEnabled
      && (qword_1401604F0 & 0x1000000) != 0
      && (qword_1401604F0 & 0x2000) == 0
      && (Microsoft_Windows_DxgKrnlEnableBits & 0x200000000000LL) != 0 )
    {
      McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, EventPostAcquireAdapterLock, v15, this);
    }
    *((_DWORD *)this + 44) = 2;
    v11 = v27;
    goto LABEL_48;
  }
  *((_QWORD *)this + 408) = CurrentThread;
  if ( CurrentThread == *((struct _KTHREAD **)v2 + 363) )
  {
    v10 = (char *)this + 3256;
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
    && (qword_1401604F0 & 0x1000000) != 0
    && (qword_1401604F0 & 0x2000) == 0
    && (Microsoft_Windows_DxgKrnlEnableBits & 0x200000000000LL) != 0 )
  {
    McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, EventPreAcquireAdapterLock, v7, this);
  }
  DXGADAPTER::AcquireCoreResourceExclusiveWithTracking(this, 2);
  if ( bTracingEnabled
    && (qword_1401604F0 & 0x1000000) != 0
    && (qword_1401604F0 & 0x2000) == 0
    && (Microsoft_Windows_DxgKrnlEnableBits & 0x200000000000LL) != 0 )
  {
    McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, EventPostAcquireAdapterLock, v8, this);
  }
  v9 = v26;
  *((_DWORD *)this + 44) = 2;
  if ( !*((_QWORD *)v9 + 363) )
  {
    v10 = (char *)this + 3256;
    v2 = v9;
LABEL_27:
    KeSetEvent((PRKEVENT)((char *)this + 3224), 0, 0);
    VIDSCH_EXPORT::VidSchSetRecoveryThread(
      *(VIDSCH_EXPORT **)(*(_QWORD *)v10 + 736LL),
      *(struct _VIDSCH_GLOBAL **)(*(_QWORD *)v10 + 744LL),
      *((struct _KTHREAD **)this + 408));
    DXGADAPTER::BlockAndDrainIoRingAccess(this, 0);
    DXGADAPTER::PrepareToReset(this, v2);
    ADAPTER_RENDER::FlushScheduler(*v5, 4, 0xFFFFFFFFLL);
    ADAPTER_RENDER::FlushDeferredDestructions(*v5);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(*((_QWORD *)*v5 + 95) + 8LL) + 1104LL))(*((_QWORD *)*v5 + 96));
    v11 = v27;
    if ( v27 != *((struct _KTHREAD **)v2 + 363) )
      ADAPTER_RENDER::SuspendVidMmWorkerThread(*v5, 0, 0);
    ADAPTER_RENDER::FlushScheduler(*v5, 4, 0xFFFFFFFFLL);
LABEL_48:
    ADAPTER_RENDER::FlushScheduler(*v5, 4, 0xFFFFFFFFLL);
    TdrCollectDbgInfoStage2(v2);
    v18 = *v5;
    *((_BYTE *)this + 3181) = 0;
    if ( (int)ADAPTER_RENDER::Reset(v18, v2) < 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 9114;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(Status)", 9114, 0, 0, 0, 0);
    }
    v20 = (ADAPTER_DISPLAY *)*((_QWORD *)this + 406);
    if ( v20 && (int)ADAPTER_DISPLAY::Reset(v20, v19) < 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 9122;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(Status)", 9122, 0, 0, 0, 0);
    }
    DXGADAPTER::UnblockIoRingAccess(this);
    *((_QWORD *)this + 408) = 0;
    KeResetEvent((PRKEVENT)((char *)this + 3224));
    v6 = (char *)this + 136;
    goto LABEL_54;
  }
  v11 = v27;
LABEL_54:
  if ( !DXGADAPTER::IsDxgmms2(this) || *(struct _KTHREAD **)(v21 + 2904) != v11 )
  {
    *((_QWORD *)v6 + 1) = 0;
    ExReleasePushLockExclusiveEx(v6, 0);
    KeLeaveCriticalRegion();
    if ( bTracingEnabled
      && (qword_1401604F0 & 0x1000000) != 0
      && (qword_1401604F0 & 0x2000) == 0
      && (Microsoft_Windows_DxgKrnlEnableBits & 0x200000000000LL) != 0 )
    {
      McTemplateK0p_EtwWriteTransfer(&DxgkControlGuid_Context, EventReleaseAdapterLock, v22, this);
    }
    ExReleaseResourceLite(*((PERESOURCE *)this + 21));
    KeSetEvent((PRKEVENT)this + 2, 0, 0);
  }
LABEL_62:
  DXGCRITICALREGION::~DXGCRITICALREGION((DXGCRITICALREGION *)&v24);
  ExReleasePushLockSharedEx(&qword_140162870, 0);
  return 0;
}

```

## disassembly

```asm
0x1401f0308  mov     [rsp+arg_8], rdx
0x1401f030d  push    rbx
0x1401f030e  push    rbp
0x1401f030f  push    rsi
0x1401f0310  push    rdi
0x1401f0311  push    r12
0x1401f0313  push    r13
0x1401f0315  push    r14
0x1401f0317  push    r15
0x1401f0319  sub     rsp, 58h
0x1401f031d  or      r13d, 0FFFFFFFFh
0x1401f0321  xor     r15d, r15d
0x1401f0324  mov     rdi, rdx
0x1401f0327  mov     rbx, rcx
0x1401f032a  mov     r12d, 1
0x1401f0330  test    rdx, rdx
0x1401f0333  jnz     short loc_1401F037E
0x1401f0335  mov     ecx, r12d
0x1401f0338  call    cs:__imp_WdLogSingleEntry0
0x1401f033f  nop     dword ptr [rax+rax+00h]
0x1401f0344  mov     [rsp+98h+var_58], r15
0x1401f0349  lea     r9, aPtdrcontext; "pTdrContext"
0x1401f0350  mov     [rsp+98h+var_60], r15
0x1401f0355  mov     eax, 22D8h
0x1401f035a  mov     [rsp+98h+var_68], r15
0x1401f035f  mov     r8d, r13d
0x1401f0362  mov     [rsp+98h+var_70], r15
0x1401f0367  mov     edx, 40002h
0x1401f036c  xor     ecx, ecx
0x1401f036e  mov     [rsp+98h+var_78], rax
0x1401f0373  mov     cs:WdLogGlobalForLineNumber, eax
0x1401f0379  call    DxgkLogInternalTriageEvent
0x1401f037e  mov     r14, gs:188h
0x1401f0387  mov     [rsp+98h+arg_10], r14
0x1401f038f  call    ?DxgkpAcquireTestLockForStopReset@@YAXXZ; DxgkpAcquireTestLockForStopReset(void)
0x1401f0394  mov     rcx, rbx; this
0x1401f0397  call    ?IsDxgmms2@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDxgmms2(void)
0x1401f039c  test    al, al
0x1401f039e  jnz     short loc_1401F03B8
0x1401f03a0  lea     rcx, [rbx+0C98h]; Event
0x1401f03a7  xor     r8d, r8d; Wait
0x1401f03aa  xor     edx, edx; Increment
0x1401f03ac  call    cs:__imp_KeSetEvent
0x1401f03b3  nop     dword ptr [rax+rax+00h]
0x1401f03b8  lea     rsi, [rbx+0CB8h]
0x1401f03bf  cmp     [rsi], r15
0x1401f03c2  jnz     short loc_1401F040D
0x1401f03c4  mov     ecx, r12d
0x1401f03c7  call    cs:__imp_WdLogSingleEntry0
0x1401f03ce  nop     dword ptr [rax+rax+00h]
0x1401f03d3  mov     [rsp+98h+var_58], r15
0x1401f03d8  lea     r9, aThisIsrenderad; "this->IsRenderAdapter()"
0x1401f03df  mov     [rsp+98h+var_60], r15
0x1401f03e4  mov     eax, 22EAh
0x1401f03e9  mov     [rsp+98h+var_68], r15
0x1401f03ee  mov     r8d, r13d
0x1401f03f1  mov     [rsp+98h+var_70], r15
0x1401f03f6  mov     edx, 40002h
0x1401f03fb  xor     ecx, ecx
0x1401f03fd  mov     [rsp+98h+var_78], rax
0x1401f0402  mov     cs:WdLogGlobalForLineNumber, eax
0x1401f0408  call    DxgkLogInternalTriageEvent
0x1401f040d  lea     rcx, [rsp+98h+arg_0]; this
0x1401f0415  mov     [rsp+98h+arg_1], r15b
0x1401f041d  call    ?Enter@DXGCRITICALREGION@@QEAAXXZ; DXGCRITICALREGION::Enter(void)
0x1401f0422  mov     rcx, rbx; this
0x1401f0425  call    ?IsDxgmms2@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDxgmms2(void)
0x1401f042a  test    al, al
0x1401f042c  jz      loc_1401F06A2
0x1401f0432  mov     [rbx+0CC0h], r14
0x1401f0439  lea     r13, DxgkControlGuid_Context
0x1401f0440  mov     r12d, 1000000h
0x1401f0446  mov     r15d, 2000h
0x1401f044c  mov     bpl, 20h ; ' '
0x1401f044f  cmp     r14, [rdi+0B58h]
0x1401f0456  jz      loc_1401F05E3
0x1401f045c  lea     rdi, [rbx+88h]
0x1401f0463  call    cs:__imp_KeEnterCriticalRegion
0x1401f046a  nop     dword ptr [rax+rax+00h]
0x1401f046f  xor     edx, edx
0x1401f0471  mov     rcx, rdi
0x1401f0474  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401f047b  nop     dword ptr [rax+rax+00h]
0x1401f0480  mov     rax, gs:188h
0x1401f0489  mov     [rdi+8], rax
0x1401f048d  mov     eax, [rbx+0C8h]
0x1401f0493  cmp     eax, 1
0x1401f0496  jz      short loc_1401F04C2
0x1401f0498  xor     edx, edx
0x1401f049a  mov     qword ptr [rdi+8], 0
0x1401f04a2  mov     rcx, rdi
0x1401f04a5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401f04ac  nop     dword ptr [rax+rax+00h]
0x1401f04b1  call    cs:__imp_KeLeaveCriticalRegion
0x1401f04b8  nop     dword ptr [rax+rax+00h]
0x1401f04bd  jmp     loc_1401F0A38
0x1401f04c2  lea     rcx, [rbx+30h]; Event
0x1401f04c6  call    cs:__imp_KeResetEvent
0x1401f04cd  nop     dword ptr [rax+rax+00h]
0x1401f04d2  xor     r14d, r14d
0x1401f04d5  test    eax, eax
0x1401f04d7  jnz     short loc_1401F0523
0x1401f04d9  lea     ecx, [rax+1]
0x1401f04dc  call    cs:__imp_WdLogSingleEntry0
0x1401f04e3  nop     dword ptr [rax+rax+00h]
0x1401f04e8  mov     [rsp+98h+var_58], r14
0x1401f04ed  lea     r9, aOldcoreaccess0; "OldCoreAccess != 0"
0x1401f04f4  mov     [rsp+98h+var_60], r14
0x1401f04f9  mov     eax, 230Dh
0x1401f04fe  mov     [rsp+98h+var_68], r14
0x1401f0503  or      r8d, 0FFFFFFFFh
0x1401f0507  mov     [rsp+98h+var_70], r14
0x1401f050c  mov     edx, 40002h
0x1401f0511  xor     ecx, ecx
0x1401f0513  mov     [rsp+98h+var_78], rax
0x1401f0518  mov     cs:WdLogGlobalForLineNumber, eax
0x1401f051e  call    DxgkLogInternalTriageEvent
0x1401f0523  cmp     cs:bTracingEnabled, r14b
0x1401f052a  jz      short loc_1401F0560
0x1401f052c  mov     rax, cs:qword_1401604F0
0x1401f0533  test    r12, rax
0x1401f0536  jz      short loc_1401F0560
0x1401f0538  test    r15, rax
0x1401f053b  jnz     short loc_1401F0560
0x1401f053d  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+5, bpl
0x1401f0544  jz      short loc_1401F0560
0x1401f0546  mov     r9, rbx
0x1401f0549  mov     dword ptr [rsp+98h+var_78], 1
0x1401f0551  lea     rdx, EventPreAcquireAdapterLock
0x1401f0558  mov     rcx, r13
0x1401f055b  call    McTemplateK0pt_EtwWriteTransfer
0x1401f0560  xor     r8d, r8d
0x1401f0563  mov     rcx, rbx
0x1401f0566  lea     r14d, [r8+2]
0x1401f056a  mov     edx, r14d
0x1401f056d  call    ?AcquireCoreResourceExclusiveWithTracking@DXGADAPTER@@AEAAXW4DXGADAPTER_EXCLUSIVEACCESS_REASON@@_N@Z; DXGADAPTER::AcquireCoreResourceExclusiveWithTracking(DXGADAPTER_EXCLUSIVEACCESS_REASON,bool)
0x1401f0572  cmp     cs:bTracingEnabled, 0
0x1401f0579  jz      short loc_1401F05AF
0x1401f057b  mov     rax, cs:qword_1401604F0
0x1401f0582  test    r12, rax
0x1401f0585  jz      short loc_1401F05AF
0x1401f0587  test    r15, rax
0x1401f058a  jnz     short loc_1401F05AF
0x1401f058c  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+5, bpl
0x1401f0593  jz      short loc_1401F05AF
0x1401f0595  mov     r9, rbx
0x1401f0598  mov     dword ptr [rsp+98h+var_78], 1
0x1401f05a0  lea     rdx, EventPostAcquireAdapterLock
0x1401f05a7  mov     rcx, r13
0x1401f05aa  call    McTemplateK0pt_EtwWriteTransfer
0x1401f05af  mov     rdx, [rsp+98h+arg_8]
0x1401f05b7  mov     [rbx+0B0h], r14d
0x1401f05be  cmp     qword ptr [rdx+0B58h], 0
0x1401f05c6  jnz     short loc_1401F05D4
0x1401f05c8  lea     r14, [rbx+0CB8h]
0x1401f05cf  mov     rdi, rdx
0x1401f05d2  jmp     short loc_1401F05E6
0x1401f05d4  mov     r14, [rsp+98h+arg_10]
0x1401f05dc  xor     esi, esi
0x1401f05de  jmp     loc_1401F09A5
0x1401f05e3  mov     r14, rsi
0x1401f05e6  lea     rcx, [rbx+0C98h]; Event
0x1401f05ed  xor     r8d, r8d; Wait
0x1401f05f0  xor     edx, edx; Increment
0x1401f05f2  call    cs:__imp_KeSetEvent
0x1401f05f9  nop     dword ptr [rax+rax+00h]
0x1401f05fe  mov     rcx, [r14]
0x1401f0601  mov     r8, [rbx+0CC0h]; struct _KTHREAD *
0x1401f0608  mov     rdx, [rcx+2E8h]; struct _VIDSCH_GLOBAL *
0x1401f060f  mov     rcx, [rcx+2E0h]; this
0x1401f0616  call    ?VidSchSetRecoveryThread@VIDSCH_EXPORT@@QEAAXPEAU_VIDSCH_GLOBAL@@PEAU_KTHREAD@@@Z; VIDSCH_EXPORT::VidSchSetRecoveryThread(_VIDSCH_GLOBAL *,_KTHREAD *)
0x1401f061b  xor     edx, edx; struct DXGCROSSADAPTERLOCK *
0x1401f061d  mov     rcx, rbx; this
0x1401f0620  call    ?BlockAndDrainIoRingAccess@DXGADAPTER@@QEAAJPEAVDXGCROSSADAPTERLOCK@@@Z; DXGADAPTER::BlockAndDrainIoRingAccess(DXGCROSSADAPTERLOCK *)
0x1401f0625  mov     rdx, rdi; struct _TDR_RECOVERY_CONTEXT *
0x1401f0628  mov     rcx, rbx; this
0x1401f062b  call    ?PrepareToReset@DXGADAPTER@@QEAAJPEAU_TDR_RECOVERY_CONTEXT@@@Z; DXGADAPTER::PrepareToReset(_TDR_RECOVERY_CONTEXT *)
0x1401f0630  mov     rcx, [rsi]
0x1401f0633  xor     r9d, r9d
0x1401f0636  or      r8d, 0FFFFFFFFh
0x1401f063a  lea     edx, [r9+4]
0x1401f063e  call    ?FlushScheduler@ADAPTER_RENDER@@QEAAJW4DXGADAPTER_FLUSHSCHEDULER_REASON@@IH@Z; ADAPTER_RENDER::FlushScheduler(DXGADAPTER_FLUSHSCHEDULER_REASON,uint,int)
0x1401f0643  mov     rcx, [rsi]; this
0x1401f0646  call    ?FlushDeferredDestructions@ADAPTER_RENDER@@AEAAXXZ; ADAPTER_RENDER::FlushDeferredDestructions(void)
0x1401f064b  mov     rcx, [rsi]
0x1401f064e  mov     rax, [rcx+2F8h]
0x1401f0655  mov     rcx, [rcx+300h]
0x1401f065c  mov     rdx, [rax+8]
0x1401f0660  mov     rax, [rdx+450h]
0x1401f0667  call    _guard_dispatch_icall
0x1401f066c  mov     r14, [rsp+98h+arg_10]
0x1401f0674  cmp     r14, [rdi+0B58h]
0x1401f067b  jz      short loc_1401F068A
0x1401f067d  mov     rcx, [rsi]
0x1401f0680  xor     r8d, r8d
0x1401f0683  xor     edx, edx
0x1401f0685  call    ?SuspendVidMmWorkerThread@ADAPTER_RENDER@@AEAAXW4VIDMM_WORKER_THREAD_SUSPEND_REASON@@E@Z; ADAPTER_RENDER::SuspendVidMmWorkerThread(VIDMM_WORKER_THREAD_SUSPEND_REASON,uchar)
0x1401f068a  mov     rcx, [rsi]
0x1401f068d  xor     r9d, r9d
0x1401f0690  or      r8d, 0FFFFFFFFh
0x1401f0694  lea     edx, [r9+4]
0x1401f0698  call    ?FlushScheduler@ADAPTER_RENDER@@QEAAJW4DXGADAPTER_FLUSHSCHEDULER_REASON@@IH@Z; ADAPTER_RENDER::FlushScheduler(DXGADAPTER_FLUSHSCHEDULER_REASON,uint,int)
0x1401f069d  jmp     loc_1401F0896
0x1401f06a2  call    cs:__imp_KeEnterCriticalRegion
0x1401f06a9  nop     dword ptr [rax+rax+00h]
0x1401f06ae  xor     edx, edx
0x1401f06b0  lea     rcx, [rbx+88h]
0x1401f06b7  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x1401f06be  nop     dword ptr [rax+rax+00h]
0x1401f06c3  test    al, al
0x1401f06c5  jnz     short loc_1401F070B
0x1401f06c7  call    cs:__imp_KeLeaveCriticalRegion
0x1401f06ce  nop     dword ptr [rax+rax+00h]
0x1401f06d3  mov     rcx, [rsi]
0x1401f06d6  xor     r9d, r9d
0x1401f06d9  mov     r8d, r13d
0x1401f06dc  lea     edx, [r9+4]
0x1401f06e0  call    ?FlushScheduler@ADAPTER_RENDER@@QEAAJW4DXGADAPTER_FLUSHSCHEDULER_REASON@@IH@Z; ADAPTER_RENDER::FlushScheduler(DXGADAPTER_FLUSHSCHEDULER_REASON,uint,int)
0x1401f06e5  lea     r8, [rsp+98h+Interval]; Interval
0x1401f06ed  mov     qword ptr [rsp+98h+Interval], 0FFFFFFFFFFFE7960h
0x1401f06f9  xor     edx, edx; Alertable
0x1401f06fb  xor     ecx, ecx; WaitMode
0x1401f06fd  call    cs:__imp_KeDelayExecutionThread
0x1401f0704  nop     dword ptr [rax+rax+00h]
0x1401f0709  jmp     short loc_1401F06A2
0x1401f070b  mov     rax, gs:188h
0x1401f0714  lea     rcx, [rbx+30h]; Event
0x1401f0718  mov     [rbx+90h], rax
0x1401f071f  call    cs:__imp_KeResetEvent
0x1401f0726  nop     dword ptr [rax+rax+00h]
0x1401f072b  test    eax, eax
0x1401f072d  jnz     short loc_1401F0778
0x1401f072f  mov     ecx, r12d
0x1401f0732  call    cs:__imp_WdLogSingleEntry0
0x1401f0739  nop     dword ptr [rax+rax+00h]
0x1401f073e  mov     [rsp+98h+var_58], r15
0x1401f0743  lea     r9, aOldcoreaccess0; "OldCoreAccess != 0"
0x1401f074a  mov     [rsp+98h+var_60], r15
0x1401f074f  mov     eax, 236Eh
0x1401f0754  mov     [rsp+98h+var_68], r15
0x1401f0759  mov     r8d, r13d
0x1401f075c  mov     [rsp+98h+var_70], r15
0x1401f0761  mov     edx, 40002h
0x1401f0766  xor     ecx, ecx
0x1401f0768  mov     [rsp+98h+var_78], rax
0x1401f076d  mov     cs:WdLogGlobalForLineNumber, eax
0x1401f0773  call    DxgkLogInternalTriageEvent
0x1401f0778  cmp     cs:bTracingEnabled, 0
0x1401f077f  lea     r13, DxgkControlGuid_Context
0x1401f0786  mov     r12d, 1000000h
0x1401f078c  mov     r15d, 2000h
0x1401f0792  mov     bpl, 20h ; ' '
0x1401f0795  jz      short loc_1401F07CB
0x1401f0797  mov     rax, cs:qword_1401604F0
0x1401f079e  test    r12, rax
0x1401f07a1  jz      short loc_1401F07CB
0x1401f07a3  test    r15, rax
0x1401f07a6  jnz     short loc_1401F07CB
0x1401f07a8  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+5, bpl
0x1401f07af  jz      short loc_1401F07CB
0x1401f07b1  mov     r9, rbx
0x1401f07b4  mov     dword ptr [rsp+98h+var_78], 1
0x1401f07bc  lea     rdx, EventPreAcquireAdapterLock
0x1401f07c3  mov     rcx, r13
0x1401f07c6  call    McTemplateK0pt_EtwWriteTransfer
0x1401f07cb  mov     rcx, [rbx+0A8h]; Resource
0x1401f07d2  xor     edx, edx; Wait
0x1401f07d4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401f07db  nop     dword ptr [rax+rax+00h]
0x1401f07e0  mov     r14d, 2
0x1401f07e6  jmp     short loc_1401F0846
0x1401f07e8  mov     [rbx+13B4h], r14d
0x1401f07ef  call    ?GetFirstProfilerInterface@DXGGLOBAL@@SA?AW4_DXGKETW_PROFILER_TYPE@@XZ; DXGGLOBAL::GetFirstProfilerInterface(void)
0x1401f07f4  mov     rcx, [rsi]
0x1401f07f7  xor     r9d, r9d
0x1401f07fa  or      r8d, 0FFFFFFFFh
0x1401f07fe  mov     [rbx+13B8h], eax
0x1401f0804  lea     edx, [r9+4]
0x1401f0808  call    ?FlushScheduler@ADAPTER_RENDER@@QEAAJW4DXGADAPTER_FLUSHSCHEDULER_REASON@@IH@Z; ADAPTER_RENDER::FlushScheduler(DXGADAPTER_FLUSHSCHEDULER_REASON,uint,int)
0x1401f080d  lea     r8, [rsp+98h+Interval]; Interval
0x1401f0815  mov     qword ptr [rsp+98h+Interval], 0FFFFFFFFFFFE7960h
0x1401f0821  xor     edx, edx; Alertable
0x1401f0823  xor     ecx, ecx; WaitMode
0x1401f0825  call    cs:__imp_KeDelayExecutionThread
0x1401f082c  nop     dword ptr [rax+rax+00h]
0x1401f0831  mov     rcx, [rbx+0A8h]; Resource
0x1401f0838  xor     edx, edx; Wait
0x1401f083a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401f0841  nop     dword ptr [rax+rax+00h]
0x1401f0846  test    al, al
0x1401f0848  jz      short loc_1401F07E8
0x1401f084a  cmp     cs:bTracingEnabled, 0
0x1401f0851  jz      short loc_1401F0887
0x1401f0853  mov     rax, cs:qword_1401604F0
0x1401f085a  test    r12, rax
0x1401f085d  jz      short loc_1401F0887
0x1401f085f  test    r15, rax
0x1401f0862  jnz     short loc_1401F0887
0x1401f0864  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+5, bpl
0x1401f086b  jz      short loc_1401F0887
  ... truncated ...
```
