# DXGDEVICE::ScheduleDeferredDestruction(_D3DDDICB_DESTROYALLOCATION2FLAGS,DXGTERMINATIONTRACKER *,COREDEVICEACCESS *)

- ea: `0x140320138`
- end: `0x140320980`
- name: `?ScheduleDeferredDestruction@DXGDEVICE@@QEAAXU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAVDXGTERMINATIONTRACKER@@PEAVCOREDEVICEACCESS@@@Z`
- size: `2120`
- prototype: `void __fastcall(DXGDEVICE *__hidden this, struct _D3DDDICB_DESTROYALLOCATION2FLAGS, struct DXGTERMINATIONTRACKER *, struct COREDEVICEACCESS *)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x14031e088`

## callees

- `0x140012380`
- `0x140015dbc`
- `0x14001a57c`
- `0x14001aadc`
- `0x14001b890`
- `0x14001bd70`
- `0x14001d0e4`
- `0x140021c80`
- `0x140034740`
- `0x1400495f0`
- `0x1400a01e0`
- `0x140310f10`
- `0x14031f190`
- `0x140320138`
- `0x140320988`
- `0x140321260`
- `0x14032152c`
- `0x140321770`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140320378`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140320378`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x140320359`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x140320359`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140320348`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140320348`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140320243`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403202b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403203be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403205b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140320243`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403202b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403203be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403205b0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140320237`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403202a7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403203b2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403205a4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140320237`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403202a7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403203b2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403205a4`
- `ntoskrnl!KeReadStateEvent` at `0x1403204bb`
- `ntoskrnl!KeReadStateEvent` at `0x140320507`
- `ntoskrnl!KeReadStateEvent` at `0x1403204bb`
- `ntoskrnl!KeReadStateEvent` at `0x140320507`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1403203f7`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1403203f7`
- `ntoskrnl!PsGetCurrentProcess` at `0x14032016b`
- `ntoskrnl!PsGetCurrentProcess` at `0x140320305`
- `ntoskrnl!PsGetCurrentProcess` at `0x14032016b`
- `ntoskrnl!PsGetCurrentProcess` at `0x140320305`
- `ntoskrnl!KeClearEvent` at `0x14032058f`
- `ntoskrnl!KeClearEvent` at `0x14032058f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140320273`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140320479`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140320273`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140320479`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140320222`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140320222`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x14032017a`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140320314`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x14032017a`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140320314`
- `ntoskrnl!KeWaitForSingleObject` at `0x140320676`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403206b7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140320676`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403206b7`
- `watchdog!WdLogSingleEntry0` at `0x14032070c`
- `watchdog!WdLogSingleEntry0` at `0x14032075d`
- `watchdog!WdLogSingleEntry0` at `0x1403207ef`
- `watchdog!WdLogSingleEntry0` at `0x140320934`
- `watchdog!WdLogSingleEntry0` at `0x14032070c`
- `watchdog!WdLogSingleEntry0` at `0x14032075d`
- `watchdog!WdLogSingleEntry0` at `0x1403207ef`
- `watchdog!WdLogSingleEntry0` at `0x140320934`
- `watchdog!WdLogSingleEntry5` at `0x140320854`
- `watchdog!WdLogSingleEntry5` at `0x140320888`
- `watchdog!WdLogSingleEntry5` at `0x1403208bc`
- `watchdog!WdLogSingleEntry5` at `0x140320902`
- `watchdog!WdLogSingleEntry5` at `0x140320854`
- `watchdog!WdLogSingleEntry5` at `0x140320888`
- `watchdog!WdLogSingleEntry5` at `0x1403208bc`
- `watchdog!WdLogSingleEntry5` at `0x140320902`

## pseudocode

```c
void __fastcall DXGDEVICE::ScheduleDeferredDestruction(
        PRKEVENT *this,
        struct _D3DDDICB_DESTROYALLOCATION2FLAGS a2,
        struct DXGTERMINATIONTRACKER *a3,
        struct COREDEVICEACCESS *a4)
{
  __int64 v4; // r14
  struct DXGTERMINATIONTRACKER *v6; // r15
  __int64 CurrentProcess; // rax
  __int64 ProcessDxgProcess; // rax
  struct DXGPROCESS *v11; // rsi
  struct DXGPROCESS *v12; // rdi
  DXGPUSHLOCK *v13; // rsi
  HMGRTABLE *v14; // r15
  unsigned int v15; // eax
  int v16; // ecx
  char v17; // di
  const char *v18; // rdx
  unsigned int v19; // edi
  __int64 v20; // r14
  unsigned int v21; // edx
  unsigned int v22; // edx
  __int64 v23; // rax
  __int64 v24; // rax
  struct DXGPROCESS *v25; // rbp
  struct DXGPROCESS *v26; // rsi
  char v27; // si
  __int64 v28; // rcx
  struct _KTHREAD **v29; // rcx
  struct _KTHREAD **v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rsi
  struct DXGTHREAD *Current; // rax
  struct _ETHREAD *CurrentThread; // rdi
  DXGGLOBAL *Global; // rax
  struct DXGTHREAD *v41; // rax
  struct _ETHREAD *v42; // rdi
  DXGGLOBAL *v43; // rax
  char v44; // [rsp+50h] [rbp-58h]

  v4 = *(_QWORD *)a3;
  v44 = 0;
  v6 = a3;
  if ( !*(_QWORD *)a3 )
    goto LABEL_19;
  CurrentProcess = PsGetCurrentProcess();
  ProcessDxgProcess = PsGetProcessDxgProcess(CurrentProcess);
  v11 = (struct DXGPROCESS *)ProcessDxgProcess;
  if ( ProcessDxgProcess && (*(_DWORD *)(ProcessDxgProcess + 408) & 0x80) == 0 )
    goto LABEL_4;
  Current = DXGTHREAD::GetCurrent();
  if ( !Current )
  {
    CurrentThread = KeGetCurrentThread();
    Global = DXGGLOBAL::GetGlobal();
    v12 = DXGGLOBAL::SearchDxgThreadList(Global, CurrentThread);
    if ( v12 )
      goto LABEL_5;
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 3089;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Failed to find DXGPROCESS", 3089, 0, 0, 0, 0);
LABEL_4:
    v12 = v11;
    goto LABEL_5;
  }
  v12 = (struct DXGPROCESS *)*((_QWORD *)Current + 3);
  if ( !v12 )
    goto LABEL_4;
LABEL_5:
  v13 = (struct DXGPROCESS *)((char *)v12 + 248);
  if ( v12 != (struct DXGPROCESS *)-248LL && *((struct _KTHREAD **)v12 + 32) == KeGetCurrentThread() )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1500;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"bAllowAcquireRecursive || pPushLock == NULL || !m_pPushLock->IsExclusiveOwner()",
      1500,
      0,
      0,
      0,
      0);
  }
  DXGPUSHLOCK::AcquireExclusive((struct DXGPROCESS *)((char *)v12 + 248));
  v14 = (struct DXGPROCESS *)((char *)v12 + 280);
  v15 = (*(_DWORD *)(v4 + 16) >> 6) & 0xFFFFFF;
  if ( v15 < *((_DWORD *)v12 + 74) )
  {
    v16 = *(_DWORD *)(*(_QWORD *)v14 + 16LL * v15 + 8);
    if ( ((*(_DWORD *)(v4 + 16) >> 25) & 0x60) == (*(_BYTE *)(*(_QWORD *)v14 + 16LL * v15 + 8) & 0x60)
      && (v16 & 0x2000) == 0
      && (v16 & 0x1F) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)v14 + 16LL * v15 + 8) = v16 | 0x2000;
    }
  }
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v4 + 72));
  *((_QWORD *)v12 + 32) = 0;
  ExReleasePushLockExclusiveEx((char *)v12 + 248, 0);
  KeLeaveCriticalRegion();
  v17 = 0;
  if ( a4 && !DXGADAPTER::IsCoreResourceExclusiveOwner(*((DXGADAPTER **)a4 + 3)) )
  {
    v17 = 1;
    COREDEVICEACCESS::Release(a4);
  }
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v4 + 72));
  if ( v17 )
    COREDEVICEACCESS::AcquireSharedUncheck(a4, v18);
  v19 = *(_DWORD *)(v4 + 16);
  DXGPUSHLOCK::AcquireExclusive(v13);
  HMGRTABLE::FreeHandle(v14, v19);
  *((_QWORD *)v13 + 1) = 0;
  ExReleasePushLockExclusiveEx(v13, 0);
  KeLeaveCriticalRegion();
  v6 = a3;
LABEL_19:
  v20 = *((_QWORD *)v6 + 1);
  if ( v20 )
  {
    do
    {
      v21 = *(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL);
      if ( (v21 & 0x2000) != 0 && *(_QWORD *)(v20 + 24) )
        DXGDEVICE::RemoveDirectFlipAllocationFromRequestedPinnedList(
          (DXGDEVICE *)this,
          (v21 >> 6) & 0xF,
          (struct DXGALLOCATION *)v20);
      v22 = *(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL);
      if ( (v22 & 0x200B) != 0 )
        DXGDEVICE::TestAndSetDisplayedPrimary(
          (DXGDEVICE *)this,
          (v22 >> 6) & 0xF,
          (const struct DXGALLOCATION *)v20,
          a4);
      v23 = PsGetCurrentProcess();
      v24 = PsGetProcessDxgProcess(v23);
      v25 = (struct DXGPROCESS *)v24;
      if ( !v24 || (*(_DWORD *)(v24 + 408) & 0x80) != 0 )
      {
        v41 = DXGTHREAD::GetCurrent();
        if ( v41 )
        {
          v26 = (struct DXGPROCESS *)*((_QWORD *)v41 + 3);
          if ( v26 )
            goto LABEL_26;
        }
        else
        {
          v42 = KeGetCurrentThread();
          v43 = DXGGLOBAL::GetGlobal();
          v26 = DXGGLOBAL::SearchDxgThreadList(v43, v42);
          if ( v26 )
            goto LABEL_26;
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 3089;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Failed to find DXGPROCESS", 3089, 0, 0, 0, 0);
        }
      }
      v26 = v25;
LABEL_26:
      KeEnterCriticalRegion();
      if ( !(unsigned __int8)ExTryAcquirePushLockExclusiveEx((char *)v26 + 248, 0) )
      {
        DXGPUSHLOCK::LogEvent((struct DXGPROCESS *)((char *)v26 + 248));
        ExAcquirePushLockExclusiveEx((char *)v26 + 248, 0);
      }
      *((_QWORD *)v26 + 32) = KeGetCurrentThread();
      HMGRTABLE::FreeHandle((struct DXGPROCESS *)((char *)v26 + 280), *(_DWORD *)(v20 + 16));
      DxgkUnreferenceDxgAllocation((struct DXGALLOCATION *)v20);
      *((_QWORD *)v26 + 32) = 0;
      ExReleasePushLockExclusiveEx((char *)v26 + 248, 0);
      KeLeaveCriticalRegion();
      v27 = 0;
      if ( a4 )
      {
        v28 = *((_QWORD *)a4 + 3);
        if ( KeGetCurrentThread() != *(struct _KTHREAD **)(v28 + 184)
          && !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v28 + 168)) )
        {
          v27 = 1;
          if ( !*((_BYTE *)a4 + 32) )
          {
            WdLogSingleEntry5(0, 275, 4, (char *)a4 + 8, 0, 0);
            WdLogGlobalForLineNumber = 7835;
          }
          v29 = (struct _KTHREAD **)*((_QWORD *)a4 + 3);
          *((_BYTE *)a4 + 32) = 0;
          if ( KeGetCurrentThread() != v29[23] )
            DXGADAPTER::ReleaseCoreResource((DXGADAPTER *)v29, *((const char **)a4 + 5));
          *((_QWORD *)a4 + 5) = 0;
          if ( *((_BYTE *)a4 + 144) )
          {
            if ( !*((_BYTE *)a4 + 96) )
            {
              WdLogSingleEntry5(0, 275, 4, (char *)a4 + 72, 0, 0);
              WdLogGlobalForLineNumber = 7835;
            }
            v30 = (struct _KTHREAD **)*((_QWORD *)a4 + 11);
            *((_BYTE *)a4 + 96) = 0;
            if ( KeGetCurrentThread() != v30[23] )
              DXGADAPTER::ReleaseCoreResource((DXGADAPTER *)v30, *((const char **)a4 + 13));
            *((_QWORD *)a4 + 13) = 0;
          }
        }
      }
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v20 + 88));
      if ( v27 )
      {
        if ( *((_BYTE *)a4 + 144) )
        {
          if ( *((_BYTE *)a4 + 96) )
          {
            WdLogSingleEntry5(0, 275, 4, (char *)a4 + 72, 0, 0);
            WdLogGlobalForLineNumber = 7720;
          }
          v31 = *((_QWORD *)a4 + 11);
          if ( KeGetCurrentThread() != *(struct _KTHREAD **)(v31 + 184) )
          {
            if ( !KeReadStateEvent((PRKEVENT)(v31 + 48)) )
            {
              if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                McTemplateK0q_EtwWriteTransfer(v32, EventBlockThread, v33, 72);
              KeWaitForSingleObject((PVOID)(*((_QWORD *)a4 + 11) + 48LL), Executive, 0, 0, 0);
            }
            DXGADAPTER::AcquireCoreResourceShared(*((DXGADAPTER **)a4 + 11), 0);
          }
          *((_QWORD *)a4 + 13) = 0;
          *((_BYTE *)a4 + 96) = 1;
        }
        if ( *((_BYTE *)a4 + 32) )
        {
          WdLogSingleEntry5(0, 275, 4, (char *)a4 + 8, 0, 0);
          WdLogGlobalForLineNumber = 7720;
        }
        v34 = *((_QWORD *)a4 + 3);
        if ( KeGetCurrentThread() != *(struct _KTHREAD **)(v34 + 184) )
        {
          if ( !KeReadStateEvent((PRKEVENT)(v34 + 48)) )
          {
            if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
              McTemplateK0q_EtwWriteTransfer(v35, EventBlockThread, v36, 72);
            KeWaitForSingleObject((PVOID)(*((_QWORD *)a4 + 3) + 48LL), Executive, 0, 0, 0);
          }
          DXGADAPTER::AcquireCoreResourceShared(*((DXGADAPTER **)a4 + 3), 0);
        }
        *((_QWORD *)a4 + 5) = 0;
        *((_BYTE *)a4 + 32) = 1;
      }
      v37 = *(_QWORD *)(v20 + 64);
      if ( *(_QWORD *)(v20 + 24) )
      {
        if ( !v44 )
        {
          v44 = 1;
          if ( this != (PRKEVENT *)-176LL && this[23] == (PRKEVENT)KeGetCurrentThread() )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 1500;
            DxgkLogInternalTriageEvent(
              0,
              262146,
              -1,
              (unsigned int)L"bAllowAcquireRecursive || pPushLock == NULL || !m_pPushLock->IsExclusiveOwner()",
              1500,
              0,
              0,
              0,
              0);
          }
          DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)(this + 22));
          if ( ++*((_DWORD *)this + 480) == 1 )
            KeClearEvent(this[241]);
          this[23] = 0;
          ExReleasePushLockExclusiveEx(this + 22, 0);
          KeLeaveCriticalRegion();
        }
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, struct DXGTERMINATIONTRACKER *))this[2][31].Header.WaitListHead.Blink->Blink[8].Blink)(
          *(_QWORD *)&this[2][32].Header.Lock,
          *(_QWORD *)(v20 + 24),
          (*(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL) >> 6) & 0xF,
          a2.Value,
          v6);
      }
      v20 = v37;
    }
    while ( v37 );
  }
}

```

## disassembly

```asm
0x140320138  mov     [rsp+arg_10], r8
0x14032013d  push    rbx
0x14032013e  push    rbp
0x14032013f  push    rsi
0x140320140  push    rdi
0x140320141  push    r12
0x140320143  push    r13
0x140320145  push    r14
0x140320147  push    r15
0x140320149  sub     rsp, 68h
0x14032014d  mov     r14, [r8]
0x140320150  xor     ebp, ebp
0x140320152  mov     [rsp+0A8h+var_58], bpl
0x140320157  mov     r13, r9
0x14032015a  mov     r15, r8
0x14032015d  mov     ebx, edx
0x14032015f  mov     r12, rcx
0x140320162  test    r14, r14
0x140320165  jz      loc_1403202C7
0x14032016b  call    cs:__imp_PsGetCurrentProcess
0x140320172  nop     dword ptr [rax+rax+00h]
0x140320177  mov     rcx, rax
0x14032017a  call    cs:__imp_PsGetProcessDxgProcess
0x140320181  nop     dword ptr [rax+rax+00h]
0x140320186  mov     rsi, rax
0x140320189  test    rax, rax
0x14032018c  jz      loc_1403206C8
0x140320192  mov     ecx, [rax+198h]
0x140320198  shr     ecx, 7
0x14032019b  test    cl, 1
0x14032019e  jnz     loc_1403206C8
0x1403201a4  mov     rdi, rsi
0x1403201a7  lea     rsi, [rdi+0F8h]
0x1403201ae  test    rsi, rsi
0x1403201b1  jz      short loc_1403201C9
0x1403201b3  mov     rcx, [rsi+8]
0x1403201b7  mov     rax, gs:188h
0x1403201c0  cmp     rcx, rax
0x1403201c3  jz      loc_140320758
0x1403201c9  mov     rcx, rsi; this
0x1403201cc  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x1403201d1  mov     edx, [r14+10h]
0x1403201d5  lea     r15, [rdi+118h]
0x1403201dc  mov     eax, edx
0x1403201de  shr     eax, 6
0x1403201e1  and     eax, 0FFFFFFh
0x1403201e6  cmp     eax, [r15+10h]
0x1403201ea  jnb     short loc_14032021E
0x1403201ec  mov     r9, [r15]
0x1403201ef  mov     r8d, eax
0x1403201f2  add     r8, r8
0x1403201f5  shr     edx, 19h
0x1403201f8  and     edx, 60h
0x1403201fb  mov     ecx, [r9+r8*8+8]
0x140320200  mov     eax, ecx
0x140320202  and     eax, 60h
0x140320205  cmp     dl, al
0x140320207  jnz     short loc_14032021E
0x140320209  mov     eax, 2000h
0x14032020e  test    eax, ecx
0x140320210  jnz     short loc_14032021E
0x140320212  test    cl, 1Fh
0x140320215  jz      short loc_14032021E
0x140320217  or      ecx, eax
0x140320219  mov     [r9+r8*8+8], ecx
0x14032021e  lea     rcx, [r14+48h]; RunRef
0x140320222  call    cs:__imp_ExReleaseRundownProtection
0x140320229  nop     dword ptr [rax+rax+00h]
0x14032022e  xor     edx, edx
0x140320230  mov     [rsi+8], rbp
0x140320234  mov     rcx, rsi
0x140320237  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14032023e  nop     dword ptr [rax+rax+00h]
0x140320243  call    cs:__imp_KeLeaveCriticalRegion
0x14032024a  nop     dword ptr [rax+rax+00h]
0x14032024f  xor     dil, dil
0x140320252  test    r13, r13
0x140320255  jz      short loc_14032026F
0x140320257  mov     rcx, [r13+18h]; this
0x14032025b  call    ?IsCoreResourceExclusiveOwner@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsCoreResourceExclusiveOwner(void)
0x140320260  test    al, al
0x140320262  jnz     short loc_14032026F
0x140320264  mov     rcx, r13; this
0x140320267  mov     dil, 1
0x14032026a  call    ?Release@COREDEVICEACCESS@@QEAAXXZ; COREDEVICEACCESS::Release(void)
0x14032026f  lea     rcx, [r14+48h]; RunRef
0x140320273  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14032027a  nop     dword ptr [rax+rax+00h]
0x14032027f  test    dil, dil
0x140320282  jnz     loc_140320619
0x140320288  mov     edi, [r14+10h]
0x14032028c  mov     rcx, rsi; this
0x14032028f  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x140320294  mov     edx, edi; unsigned int
0x140320296  mov     rcx, r15; this
0x140320299  call    ?FreeHandle@HMGRTABLE@@QEAAXI@Z; HMGRTABLE::FreeHandle(uint)
0x14032029e  xor     edx, edx
0x1403202a0  mov     [rsi+8], rbp
0x1403202a4  mov     rcx, rsi
0x1403202a7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1403202ae  nop     dword ptr [rax+rax+00h]
0x1403202b3  call    cs:__imp_KeLeaveCriticalRegion
0x1403202ba  nop     dword ptr [rax+rax+00h]
0x1403202bf  mov     r15, [rsp+0A8h+arg_10]
0x1403202c7  mov     r14, [r15+8]
0x1403202cb  test    r14, r14
0x1403202ce  jz      loc_140320607
0x1403202d4  mov     rax, [r14+30h]
0x1403202d8  mov     edx, [rax+4]
0x1403202db  bt      edx, 0Dh
0x1403202df  jb      loc_140320626
0x1403202e5  mov     rax, [r14+30h]
0x1403202e9  mov     edx, [rax+4]
0x1403202ec  test    edx, 200Bh
0x1403202f2  jz      short loc_140320305
0x1403202f4  shr     edx, 6
0x1403202f7  mov     r8, r14; struct DXGALLOCATION *
0x1403202fa  and     edx, 0Fh; unsigned int
0x1403202fd  mov     rcx, r12; this
0x140320300  call    ?TestAndSetDisplayedPrimary@DXGDEVICE@@QEAAXIPEBVDXGALLOCATION@@PEAV2@@Z; DXGDEVICE::TestAndSetDisplayedPrimary(uint,DXGALLOCATION const *,DXGALLOCATION *)
0x140320305  call    cs:__imp_PsGetCurrentProcess
0x14032030c  nop     dword ptr [rax+rax+00h]
0x140320311  mov     rcx, rax
0x140320314  call    cs:__imp_PsGetProcessDxgProcess
0x14032031b  nop     dword ptr [rax+rax+00h]
0x140320320  mov     rbp, rax
0x140320323  test    rax, rax
0x140320326  jz      loc_1403207A9
0x14032032c  mov     ecx, [rax+198h]
0x140320332  shr     ecx, 7
0x140320335  test    cl, 1
0x140320338  jnz     loc_1403207A9
0x14032033e  mov     rsi, rbp
0x140320341  lea     rdi, [rsi+0F8h]
0x140320348  call    cs:__imp_KeEnterCriticalRegion
0x14032034f  nop     dword ptr [rax+rax+00h]
0x140320354  xor     edx, edx
0x140320356  mov     rcx, rdi
0x140320359  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x140320360  nop     dword ptr [rax+rax+00h]
0x140320365  xor     ebp, ebp
0x140320367  test    al, al
0x140320369  jnz     short loc_140320384
0x14032036b  mov     rcx, rdi; this
0x14032036e  call    ?LogEvent@DXGPUSHLOCK@@IEAAXXZ; DXGPUSHLOCK::LogEvent(void)
0x140320373  xor     edx, edx
0x140320375  mov     rcx, rdi
0x140320378  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14032037f  nop     dword ptr [rax+rax+00h]
0x140320384  mov     rax, gs:188h
0x14032038d  lea     rcx, [rsi+118h]; this
0x140320394  mov     [rdi+8], rax
0x140320398  mov     edx, [r14+10h]; unsigned int
0x14032039c  call    ?FreeHandle@HMGRTABLE@@QEAAXI@Z; HMGRTABLE::FreeHandle(uint)
0x1403203a1  mov     rcx, r14; struct DXGALLOCATION *
0x1403203a4  call    ?DxgkUnreferenceDxgAllocation@@YAXPEAVDXGALLOCATION@@@Z; DxgkUnreferenceDxgAllocation(DXGALLOCATION *)
0x1403203a9  xor     edx, edx
0x1403203ab  mov     [rdi+8], rbp
0x1403203af  mov     rcx, rdi
0x1403203b2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1403203b9  nop     dword ptr [rax+rax+00h]
0x1403203be  call    cs:__imp_KeLeaveCriticalRegion
0x1403203c5  nop     dword ptr [rax+rax+00h]
0x1403203ca  mov     sil, bpl
0x1403203cd  test    r13, r13
0x1403203d0  jz      loc_140320475
0x1403203d6  mov     rcx, [r13+18h]
0x1403203da  mov     rax, gs:188h
0x1403203e3  cmp     rax, [rcx+0B8h]
0x1403203ea  jz      loc_140320475
0x1403203f0  mov     rcx, [rcx+0A8h]; Resource
0x1403203f7  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1403203fe  nop     dword ptr [rax+rax+00h]
0x140320403  test    al, al
0x140320405  jnz     short loc_140320475
0x140320407  mov     sil, 1
0x14032040a  cmp     [r13+20h], bpl
0x14032040e  jz      loc_14032083B
0x140320414  mov     rcx, [r13+18h]; this
0x140320418  mov     [r13+20h], bpl
0x14032041c  mov     rax, gs:188h
0x140320425  cmp     rax, [rcx+0B8h]
0x14032042c  jz      short loc_140320437
0x14032042e  mov     rdx, [r13+28h]; char *
0x140320432  call    ?ReleaseCoreResource@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::ReleaseCoreResource(char const *)
0x140320437  mov     [r13+28h], rbp
0x14032043b  cmp     [r13+90h], bpl
0x140320442  jz      short loc_140320475
0x140320444  cmp     [r13+60h], bpl
0x140320448  jz      loc_14032086F
0x14032044e  mov     rcx, [r13+58h]; this
0x140320452  mov     [r13+60h], bpl
0x140320456  mov     rax, gs:188h
0x14032045f  cmp     rax, [rcx+0B8h]
0x140320466  jz      short loc_140320471
0x140320468  mov     rdx, [r13+68h]; char *
0x14032046c  call    ?ReleaseCoreResource@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::ReleaseCoreResource(char const *)
0x140320471  mov     [r13+68h], rbp
0x140320475  lea     rcx, [r14+58h]; RunRef
0x140320479  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140320480  nop     dword ptr [rax+rax+00h]
0x140320485  test    sil, sil
0x140320488  jz      loc_14032052F
0x14032048e  cmp     [r13+90h], bpl
0x140320495  jz      short loc_1403204E3
0x140320497  cmp     [r13+60h], bpl
0x14032049b  jnz     loc_1403208A3
0x1403204a1  mov     rcx, [r13+58h]
0x1403204a5  mov     rax, gs:188h
0x1403204ae  cmp     rax, [rcx+0B8h]
0x1403204b5  jz      short loc_1403204DA
0x1403204b7  add     rcx, 30h ; '0'; Event
0x1403204bb  call    cs:__imp_KeReadStateEvent
0x1403204c2  nop     dword ptr [rax+rax+00h]
0x1403204c7  test    eax, eax
0x1403204c9  jz      loc_1403208D7
0x1403204cf  mov     rcx, [r13+58h]; this
0x1403204d3  xor     edx, edx; char *
0x1403204d5  call    ?AcquireCoreResourceShared@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::AcquireCoreResourceShared(char const *)
0x1403204da  mov     [r13+68h], rbp
0x1403204de  mov     byte ptr [r13+60h], 1
0x1403204e3  cmp     [r13+20h], bpl
0x1403204e7  jnz     loc_1403208E9
0x1403204ed  mov     rcx, [r13+18h]
0x1403204f1  mov     rax, gs:188h
0x1403204fa  cmp     rax, [rcx+0B8h]
0x140320501  jz      short loc_140320526
0x140320503  add     rcx, 30h ; '0'; Event
0x140320507  call    cs:__imp_KeReadStateEvent
0x14032050e  nop     dword ptr [rax+rax+00h]
0x140320513  test    eax, eax
0x140320515  jz      loc_14032091D
0x14032051b  mov     rcx, [r13+18h]; this
0x14032051f  xor     edx, edx; char *
0x140320521  call    ?AcquireCoreResourceShared@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::AcquireCoreResourceShared(char const *)
0x140320526  mov     [r13+28h], rbp
0x14032052a  mov     byte ptr [r13+20h], 1
0x14032052f  mov     rsi, [r14+40h]
0x140320533  cmp     [r14+18h], rbp
0x140320537  jz      loc_1403205FB
0x14032053d  cmp     [rsp+0A8h+var_58], bpl
0x140320542  jnz     short loc_1403205BC
0x140320544  lea     rdi, [r12+0B0h]
0x14032054c  mov     [rsp+0A8h+var_58], 1
0x140320551  test    rdi, rdi
0x140320554  jz      short loc_14032056C
0x140320556  mov     rcx, [rdi+8]
0x14032055a  mov     rax, gs:188h
0x140320563  cmp     rcx, rax
0x140320566  jz      loc_14032092F
0x14032056c  mov     rcx, rdi; this
0x14032056f  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x140320574  inc     dword ptr [r12+780h]
0x14032057c  cmp     dword ptr [r12+780h], 1
0x140320585  jnz     short loc_14032059B
0x140320587  mov     rcx, [r12+788h]; Event
0x14032058f  call    cs:__imp_KeClearEvent
0x140320596  nop     dword ptr [rax+rax+00h]
0x14032059b  xor     edx, edx
0x14032059d  mov     [rdi+8], rbp
0x1403205a1  mov     rcx, rdi
0x1403205a4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1403205ab  nop     dword ptr [rax+rax+00h]
0x1403205b0  call    cs:__imp_KeLeaveCriticalRegion
0x1403205b7  nop     dword ptr [rax+rax+00h]
0x1403205bc  mov     rcx, [r12+10h]
0x1403205c1  mov     r9d, ebx
0x1403205c4  mov     [rsp+0A8h+Timeout], r15
0x1403205c9  mov     rax, [rcx+2F8h]
0x1403205d0  mov     rcx, [rcx+300h]
0x1403205d7  mov     rdx, [rax+8]
0x1403205db  mov     rax, [r14+30h]
0x1403205df  mov     r8d, [rax+4]
0x1403205e3  mov     rax, [rdx+88h]
0x1403205ea  mov     rdx, [r14+18h]
0x1403205ee  shr     r8d, 6
0x1403205f2  and     r8d, 0Fh
0x1403205f6  call    _guard_dispatch_icall
0x1403205fb  mov     r14, rsi
0x1403205fe  test    rsi, rsi
0x140320601  jnz     loc_1403202D4
0x140320607  add     rsp, 68h
0x14032060b  pop     r15
0x14032060d  pop     r14
0x14032060f  pop     r13
0x140320611  pop     r12
0x140320613  pop     rdi
0x140320614  pop     rsi
0x140320615  pop     rbp
0x140320616  pop     rbx
0x140320617  retn
0x140320619  mov     rcx, r13; this
0x14032061c  call    ?AcquireSharedUncheck@COREDEVICEACCESS@@QEAAXPEBD@Z; COREDEVICEACCESS::AcquireSharedUncheck(char const *)
0x140320621  jmp     loc_140320288
0x140320626  cmp     [r14+18h], rbp
0x14032062a  jz      loc_1403202E5
0x140320630  shr     edx, 6
0x140320633  mov     r8, r14; struct DXGALLOCATION *
0x140320636  and     edx, 0Fh; unsigned int
0x140320639  mov     rcx, r12; this
  ... truncated ...
```
