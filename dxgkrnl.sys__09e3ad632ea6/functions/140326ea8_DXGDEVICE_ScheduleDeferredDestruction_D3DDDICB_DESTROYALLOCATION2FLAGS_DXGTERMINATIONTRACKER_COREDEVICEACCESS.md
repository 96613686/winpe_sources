# DXGDEVICE::ScheduleDeferredDestruction(_D3DDDICB_DESTROYALLOCATION2FLAGS,DXGTERMINATIONTRACKER *,COREDEVICEACCESS *)

- ea: `0x140326ea8`
- end: `0x1403276f0`
- name: `?ScheduleDeferredDestruction@DXGDEVICE@@QEAAXU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAVDXGTERMINATIONTRACKER@@PEAVCOREDEVICEACCESS@@@Z`
- size: `2120`
- prototype: `void __fastcall(DXGDEVICE *__hidden this, struct _D3DDDICB_DESTROYALLOCATION2FLAGS, struct DXGTERMINATIONTRACKER *, struct COREDEVICEACCESS *)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x140324df8`

## callees

- `0x140012540`
- `0x140015f7c`
- `0x14001a61c`
- `0x14001ac0c`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001d214`
- `0x140021e50`
- `0x140034910`
- `0x1400497f0`
- `0x1400a0cb0`
- `0x140317c80`
- `0x140325f00`
- `0x140326ea8`
- `0x1403276f8`
- `0x140327fd0`
- `0x14032829c`
- `0x1403284e0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403270e8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403270e8`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1403270c9`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1403270c9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403270b8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403270b8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140326fb3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140327023`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032712e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140327320`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140326fb3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140327023`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032712e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140327320`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140326fa7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140327017`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140327122`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140327314`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140326fa7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140327017`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140327122`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140327314`
- `ntoskrnl!KeReadStateEvent` at `0x14032722b`
- `ntoskrnl!KeReadStateEvent` at `0x140327277`
- `ntoskrnl!KeReadStateEvent` at `0x14032722b`
- `ntoskrnl!KeReadStateEvent` at `0x140327277`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140327167`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140327167`
- `ntoskrnl!PsGetCurrentProcess` at `0x140326edb`
- `ntoskrnl!PsGetCurrentProcess` at `0x140327075`
- `ntoskrnl!PsGetCurrentProcess` at `0x140326edb`
- `ntoskrnl!PsGetCurrentProcess` at `0x140327075`
- `ntoskrnl!KeClearEvent` at `0x1403272ff`
- `ntoskrnl!KeClearEvent` at `0x1403272ff`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140326fe3`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1403271e9`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140326fe3`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1403271e9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140326f92`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140326f92`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140326eea`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140327084`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140326eea`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140327084`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403273e6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140327427`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403273e6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140327427`
- `watchdog!WdLogSingleEntry0` at `0x14032747c`
- `watchdog!WdLogSingleEntry0` at `0x1403274cd`
- `watchdog!WdLogSingleEntry0` at `0x14032755f`
- `watchdog!WdLogSingleEntry0` at `0x1403276a4`
- `watchdog!WdLogSingleEntry0` at `0x14032747c`
- `watchdog!WdLogSingleEntry0` at `0x1403274cd`
- `watchdog!WdLogSingleEntry0` at `0x14032755f`
- `watchdog!WdLogSingleEntry0` at `0x1403276a4`
- `watchdog!WdLogSingleEntry5` at `0x1403275c4`
- `watchdog!WdLogSingleEntry5` at `0x1403275f8`
- `watchdog!WdLogSingleEntry5` at `0x14032762c`
- `watchdog!WdLogSingleEntry5` at `0x140327672`
- `watchdog!WdLogSingleEntry5` at `0x1403275c4`
- `watchdog!WdLogSingleEntry5` at `0x1403275f8`
- `watchdog!WdLogSingleEntry5` at `0x14032762c`
- `watchdog!WdLogSingleEntry5` at `0x140327672`

## pseudocode

```c
void __fastcall DXGDEVICE::ScheduleDeferredDestruction(
        struct _KEVENT *this,
        struct _D3DDDICB_DESTROYALLOCATION2FLAGS a2,
        struct DXGTERMINATIONTRACKER *a3,
        struct COREDEVICEACCESS *a4)
{
  __int64 v4; // r14
  struct DXGTERMINATIONTRACKER *v6; // r15
  struct _KEVENT *v8; // r12
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
  __int64 v35; // r8
  __int64 v36; // rsi
  struct DXGTHREAD *Current; // rax
  struct _ETHREAD *CurrentThread; // rdi
  DXGGLOBAL *Global; // rax
  struct DXGTHREAD *v40; // rax
  struct _ETHREAD *v41; // rdi
  DXGGLOBAL *v42; // rax
  char v43; // [rsp+50h] [rbp-58h]

  v4 = *(_QWORD *)a3;
  v43 = 0;
  v6 = a3;
  v8 = this;
  if ( !*(_QWORD *)a3 )
    goto LABEL_19;
  CurrentProcess = PsGetCurrentProcess(this);
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
    WdLogGlobalForLineNumber = 3109;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Failed to find DXGPROCESS", 3109, 0, 0, 0, 0);
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
          (DXGDEVICE *)v8,
          (v21 >> 6) & 0xF,
          (struct DXGALLOCATION *)v20);
      v22 = *(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL);
      if ( (v22 & 0x200B) != 0 )
        DXGDEVICE::TestAndSetDisplayedPrimary((DXGDEVICE *)v8, (v22 >> 6) & 0xF, (const struct DXGALLOCATION *)v20, a4);
      v23 = PsGetCurrentProcess(this);
      v24 = PsGetProcessDxgProcess(v23);
      v25 = (struct DXGPROCESS *)v24;
      if ( !v24 || (*(_DWORD *)(v24 + 408) & 0x80) != 0 )
      {
        v40 = DXGTHREAD::GetCurrent();
        if ( v40 )
        {
          v26 = (struct DXGPROCESS *)*((_QWORD *)v40 + 3);
          if ( v26 )
            goto LABEL_26;
        }
        else
        {
          v41 = KeGetCurrentThread();
          v42 = DXGGLOBAL::GetGlobal();
          v26 = DXGGLOBAL::SearchDxgThreadList(v42, v41);
          if ( v26 )
            goto LABEL_26;
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 3109;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Failed to find DXGPROCESS", 3109, 0, 0, 0, 0);
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
            WdLogGlobalForLineNumber = 7839;
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
              WdLogGlobalForLineNumber = 7839;
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
            WdLogGlobalForLineNumber = 7724;
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
          WdLogGlobalForLineNumber = 7724;
        }
        this = (struct _KEVENT *)*((_QWORD *)a4 + 3);
        if ( KeGetCurrentThread() != (struct _KTHREAD *)this[7].Header.WaitListHead.Blink )
        {
          if ( !KeReadStateEvent(this + 2) )
          {
            if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
              McTemplateK0q_EtwWriteTransfer(v34, EventBlockThread, v35, 72);
            KeWaitForSingleObject((PVOID)(*((_QWORD *)a4 + 3) + 48LL), Executive, 0, 0, 0);
          }
          DXGADAPTER::AcquireCoreResourceShared(*((DXGADAPTER **)a4 + 3), 0);
        }
        *((_QWORD *)a4 + 5) = 0;
        *((_BYTE *)a4 + 32) = 1;
      }
      v36 = *(_QWORD *)(v20 + 64);
      if ( *(_QWORD *)(v20 + 24) )
      {
        if ( !v43 )
        {
          v43 = 1;
          if ( v8 != (struct _KEVENT *)-176LL
            && (struct _KTHREAD *)v8[7].Header.WaitListHead.Blink == KeGetCurrentThread() )
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
          DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)&v8[7].Header.WaitListHead);
          if ( ++v8[80].Header.LockNV == 1 )
            KeClearEvent((PRKEVENT)v8[80].Header.WaitListHead.Flink);
          v8[7].Header.WaitListHead.Blink = 0;
          ExReleasePushLockExclusiveEx(&v8[7].Header.WaitListHead, 0);
          KeLeaveCriticalRegion();
        }
        ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD, _QWORD, struct DXGTERMINATIONTRACKER *))v8->Header.WaitListHead.Blink[47].Blink->Blink[8].Blink)(
          v8->Header.WaitListHead.Blink[48].Flink,
          *(_QWORD *)(v20 + 24),
          (*(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL) >> 6) & 0xF,
          a2.Value,
          v6);
      }
      v20 = v36;
    }
    while ( v36 );
  }
}

```

## disassembly

```asm
0x140326ea8  mov     [rsp+arg_10], r8
0x140326ead  push    rbx
0x140326eae  push    rbp
0x140326eaf  push    rsi
0x140326eb0  push    rdi
0x140326eb1  push    r12
0x140326eb3  push    r13
0x140326eb5  push    r14
0x140326eb7  push    r15
0x140326eb9  sub     rsp, 68h
0x140326ebd  mov     r14, [r8]
0x140326ec0  xor     ebp, ebp
0x140326ec2  mov     [rsp+0A8h+var_58], bpl
0x140326ec7  mov     r13, r9
0x140326eca  mov     r15, r8
0x140326ecd  mov     ebx, edx
0x140326ecf  mov     r12, rcx
0x140326ed2  test    r14, r14
0x140326ed5  jz      loc_140327037
0x140326edb  call    cs:__imp_PsGetCurrentProcess
0x140326ee2  nop     dword ptr [rax+rax+00h]
0x140326ee7  mov     rcx, rax
0x140326eea  call    cs:__imp_PsGetProcessDxgProcess
0x140326ef1  nop     dword ptr [rax+rax+00h]
0x140326ef6  mov     rsi, rax
0x140326ef9  test    rax, rax
0x140326efc  jz      loc_140327438
0x140326f02  mov     ecx, [rax+198h]
0x140326f08  shr     ecx, 7
0x140326f0b  test    cl, 1
0x140326f0e  jnz     loc_140327438
0x140326f14  mov     rdi, rsi
0x140326f17  lea     rsi, [rdi+0F8h]
0x140326f1e  test    rsi, rsi
0x140326f21  jz      short loc_140326F39
0x140326f23  mov     rcx, [rsi+8]
0x140326f27  mov     rax, gs:188h
0x140326f30  cmp     rcx, rax
0x140326f33  jz      loc_1403274C8
0x140326f39  mov     rcx, rsi; this
0x140326f3c  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x140326f41  mov     edx, [r14+10h]
0x140326f45  lea     r15, [rdi+118h]
0x140326f4c  mov     eax, edx
0x140326f4e  shr     eax, 6
0x140326f51  and     eax, 0FFFFFFh
0x140326f56  cmp     eax, [r15+10h]
0x140326f5a  jnb     short loc_140326F8E
0x140326f5c  mov     r9, [r15]
0x140326f5f  mov     r8d, eax
0x140326f62  add     r8, r8
0x140326f65  shr     edx, 19h
0x140326f68  and     edx, 60h
0x140326f6b  mov     ecx, [r9+r8*8+8]
0x140326f70  mov     eax, ecx
0x140326f72  and     eax, 60h
0x140326f75  cmp     dl, al
0x140326f77  jnz     short loc_140326F8E
0x140326f79  mov     eax, 2000h
0x140326f7e  test    eax, ecx
0x140326f80  jnz     short loc_140326F8E
0x140326f82  test    cl, 1Fh
0x140326f85  jz      short loc_140326F8E
0x140326f87  or      ecx, eax
0x140326f89  mov     [r9+r8*8+8], ecx
0x140326f8e  lea     rcx, [r14+48h]; RunRef
0x140326f92  call    cs:__imp_ExReleaseRundownProtection
0x140326f99  nop     dword ptr [rax+rax+00h]
0x140326f9e  xor     edx, edx
0x140326fa0  mov     [rsi+8], rbp
0x140326fa4  mov     rcx, rsi
0x140326fa7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140326fae  nop     dword ptr [rax+rax+00h]
0x140326fb3  call    cs:__imp_KeLeaveCriticalRegion
0x140326fba  nop     dword ptr [rax+rax+00h]
0x140326fbf  xor     dil, dil
0x140326fc2  test    r13, r13
0x140326fc5  jz      short loc_140326FDF
0x140326fc7  mov     rcx, [r13+18h]; this
0x140326fcb  call    ?IsCoreResourceExclusiveOwner@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsCoreResourceExclusiveOwner(void)
0x140326fd0  test    al, al
0x140326fd2  jnz     short loc_140326FDF
0x140326fd4  mov     rcx, r13; this
0x140326fd7  mov     dil, 1
0x140326fda  call    ?Release@COREDEVICEACCESS@@QEAAXXZ; COREDEVICEACCESS::Release(void)
0x140326fdf  lea     rcx, [r14+48h]; RunRef
0x140326fe3  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140326fea  nop     dword ptr [rax+rax+00h]
0x140326fef  test    dil, dil
0x140326ff2  jnz     loc_140327389
0x140326ff8  mov     edi, [r14+10h]
0x140326ffc  mov     rcx, rsi; this
0x140326fff  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x140327004  mov     edx, edi; unsigned int
0x140327006  mov     rcx, r15; this
0x140327009  call    ?FreeHandle@HMGRTABLE@@QEAAXI@Z; HMGRTABLE::FreeHandle(uint)
0x14032700e  xor     edx, edx
0x140327010  mov     [rsi+8], rbp
0x140327014  mov     rcx, rsi
0x140327017  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14032701e  nop     dword ptr [rax+rax+00h]
0x140327023  call    cs:__imp_KeLeaveCriticalRegion
0x14032702a  nop     dword ptr [rax+rax+00h]
0x14032702f  mov     r15, [rsp+0A8h+arg_10]
0x140327037  mov     r14, [r15+8]
0x14032703b  test    r14, r14
0x14032703e  jz      loc_140327377
0x140327044  mov     rax, [r14+30h]
0x140327048  mov     edx, [rax+4]
0x14032704b  bt      edx, 0Dh
0x14032704f  jb      loc_140327396
0x140327055  mov     rax, [r14+30h]
0x140327059  mov     edx, [rax+4]
0x14032705c  test    edx, 200Bh
0x140327062  jz      short loc_140327075
0x140327064  shr     edx, 6
0x140327067  mov     r8, r14; struct DXGALLOCATION *
0x14032706a  and     edx, 0Fh; unsigned int
0x14032706d  mov     rcx, r12; this
0x140327070  call    ?TestAndSetDisplayedPrimary@DXGDEVICE@@QEAAXIPEBVDXGALLOCATION@@PEAV2@@Z; DXGDEVICE::TestAndSetDisplayedPrimary(uint,DXGALLOCATION const *,DXGALLOCATION *)
0x140327075  call    cs:__imp_PsGetCurrentProcess
0x14032707c  nop     dword ptr [rax+rax+00h]
0x140327081  mov     rcx, rax
0x140327084  call    cs:__imp_PsGetProcessDxgProcess
0x14032708b  nop     dword ptr [rax+rax+00h]
0x140327090  mov     rbp, rax
0x140327093  test    rax, rax
0x140327096  jz      loc_140327519
0x14032709c  mov     ecx, [rax+198h]
0x1403270a2  shr     ecx, 7
0x1403270a5  test    cl, 1
0x1403270a8  jnz     loc_140327519
0x1403270ae  mov     rsi, rbp
0x1403270b1  lea     rdi, [rsi+0F8h]
0x1403270b8  call    cs:__imp_KeEnterCriticalRegion
0x1403270bf  nop     dword ptr [rax+rax+00h]
0x1403270c4  xor     edx, edx
0x1403270c6  mov     rcx, rdi
0x1403270c9  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x1403270d0  nop     dword ptr [rax+rax+00h]
0x1403270d5  xor     ebp, ebp
0x1403270d7  test    al, al
0x1403270d9  jnz     short loc_1403270F4
0x1403270db  mov     rcx, rdi; this
0x1403270de  call    ?LogEvent@DXGPUSHLOCK@@IEAAXXZ; DXGPUSHLOCK::LogEvent(void)
0x1403270e3  xor     edx, edx
0x1403270e5  mov     rcx, rdi
0x1403270e8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1403270ef  nop     dword ptr [rax+rax+00h]
0x1403270f4  mov     rax, gs:188h
0x1403270fd  lea     rcx, [rsi+118h]; this
0x140327104  mov     [rdi+8], rax
0x140327108  mov     edx, [r14+10h]; unsigned int
0x14032710c  call    ?FreeHandle@HMGRTABLE@@QEAAXI@Z; HMGRTABLE::FreeHandle(uint)
0x140327111  mov     rcx, r14; struct DXGALLOCATION *
0x140327114  call    ?DxgkUnreferenceDxgAllocation@@YAXPEAVDXGALLOCATION@@@Z; DxgkUnreferenceDxgAllocation(DXGALLOCATION *)
0x140327119  xor     edx, edx
0x14032711b  mov     [rdi+8], rbp
0x14032711f  mov     rcx, rdi
0x140327122  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140327129  nop     dword ptr [rax+rax+00h]
0x14032712e  call    cs:__imp_KeLeaveCriticalRegion
0x140327135  nop     dword ptr [rax+rax+00h]
0x14032713a  mov     sil, bpl
0x14032713d  test    r13, r13
0x140327140  jz      loc_1403271E5
0x140327146  mov     rcx, [r13+18h]
0x14032714a  mov     rax, gs:188h
0x140327153  cmp     rax, [rcx+0B8h]
0x14032715a  jz      loc_1403271E5
0x140327160  mov     rcx, [rcx+0A8h]; Resource
0x140327167  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14032716e  nop     dword ptr [rax+rax+00h]
0x140327173  test    al, al
0x140327175  jnz     short loc_1403271E5
0x140327177  mov     sil, 1
0x14032717a  cmp     [r13+20h], bpl
0x14032717e  jz      loc_1403275AB
0x140327184  mov     rcx, [r13+18h]; this
0x140327188  mov     [r13+20h], bpl
0x14032718c  mov     rax, gs:188h
0x140327195  cmp     rax, [rcx+0B8h]
0x14032719c  jz      short loc_1403271A7
0x14032719e  mov     rdx, [r13+28h]; char *
0x1403271a2  call    ?ReleaseCoreResource@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::ReleaseCoreResource(char const *)
0x1403271a7  mov     [r13+28h], rbp
0x1403271ab  cmp     [r13+90h], bpl
0x1403271b2  jz      short loc_1403271E5
0x1403271b4  cmp     [r13+60h], bpl
0x1403271b8  jz      loc_1403275DF
0x1403271be  mov     rcx, [r13+58h]; this
0x1403271c2  mov     [r13+60h], bpl
0x1403271c6  mov     rax, gs:188h
0x1403271cf  cmp     rax, [rcx+0B8h]
0x1403271d6  jz      short loc_1403271E1
0x1403271d8  mov     rdx, [r13+68h]; char *
0x1403271dc  call    ?ReleaseCoreResource@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::ReleaseCoreResource(char const *)
0x1403271e1  mov     [r13+68h], rbp
0x1403271e5  lea     rcx, [r14+58h]; RunRef
0x1403271e9  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1403271f0  nop     dword ptr [rax+rax+00h]
0x1403271f5  test    sil, sil
0x1403271f8  jz      loc_14032729F
0x1403271fe  cmp     [r13+90h], bpl
0x140327205  jz      short loc_140327253
0x140327207  cmp     [r13+60h], bpl
0x14032720b  jnz     loc_140327613
0x140327211  mov     rcx, [r13+58h]
0x140327215  mov     rax, gs:188h
0x14032721e  cmp     rax, [rcx+0B8h]
0x140327225  jz      short loc_14032724A
0x140327227  add     rcx, 30h ; '0'; Event
0x14032722b  call    cs:__imp_KeReadStateEvent
0x140327232  nop     dword ptr [rax+rax+00h]
0x140327237  test    eax, eax
0x140327239  jz      loc_140327647
0x14032723f  mov     rcx, [r13+58h]; this
0x140327243  xor     edx, edx; char *
0x140327245  call    ?AcquireCoreResourceShared@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::AcquireCoreResourceShared(char const *)
0x14032724a  mov     [r13+68h], rbp
0x14032724e  mov     byte ptr [r13+60h], 1
0x140327253  cmp     [r13+20h], bpl
0x140327257  jnz     loc_140327659
0x14032725d  mov     rcx, [r13+18h]
0x140327261  mov     rax, gs:188h
0x14032726a  cmp     rax, [rcx+0B8h]
0x140327271  jz      short loc_140327296
0x140327273  add     rcx, 30h ; '0'; Event
0x140327277  call    cs:__imp_KeReadStateEvent
0x14032727e  nop     dword ptr [rax+rax+00h]
0x140327283  test    eax, eax
0x140327285  jz      loc_14032768D
0x14032728b  mov     rcx, [r13+18h]; this
0x14032728f  xor     edx, edx; char *
0x140327291  call    ?AcquireCoreResourceShared@DXGADAPTER@@AEAAXPEBD@Z; DXGADAPTER::AcquireCoreResourceShared(char const *)
0x140327296  mov     [r13+28h], rbp
0x14032729a  mov     byte ptr [r13+20h], 1
0x14032729f  mov     rsi, [r14+40h]
0x1403272a3  cmp     [r14+18h], rbp
0x1403272a7  jz      loc_14032736B
0x1403272ad  cmp     [rsp+0A8h+var_58], bpl
0x1403272b2  jnz     short loc_14032732C
0x1403272b4  lea     rdi, [r12+0B0h]
0x1403272bc  mov     [rsp+0A8h+var_58], 1
0x1403272c1  test    rdi, rdi
0x1403272c4  jz      short loc_1403272DC
0x1403272c6  mov     rcx, [rdi+8]
0x1403272ca  mov     rax, gs:188h
0x1403272d3  cmp     rcx, rax
0x1403272d6  jz      loc_14032769F
0x1403272dc  mov     rcx, rdi; this
0x1403272df  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x1403272e4  inc     dword ptr [r12+780h]
0x1403272ec  cmp     dword ptr [r12+780h], 1
0x1403272f5  jnz     short loc_14032730B
0x1403272f7  mov     rcx, [r12+788h]; Event
0x1403272ff  call    cs:__imp_KeClearEvent
0x140327306  nop     dword ptr [rax+rax+00h]
0x14032730b  xor     edx, edx
0x14032730d  mov     [rdi+8], rbp
0x140327311  mov     rcx, rdi
0x140327314  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14032731b  nop     dword ptr [rax+rax+00h]
0x140327320  call    cs:__imp_KeLeaveCriticalRegion
0x140327327  nop     dword ptr [rax+rax+00h]
0x14032732c  mov     rcx, [r12+10h]
0x140327331  mov     r9d, ebx
0x140327334  mov     [rsp+0A8h+Timeout], r15
0x140327339  mov     rax, [rcx+2F8h]
0x140327340  mov     rcx, [rcx+300h]
0x140327347  mov     rdx, [rax+8]
0x14032734b  mov     rax, [r14+30h]
0x14032734f  mov     r8d, [rax+4]
0x140327353  mov     rax, [rdx+88h]
0x14032735a  mov     rdx, [r14+18h]
0x14032735e  shr     r8d, 6
0x140327362  and     r8d, 0Fh
0x140327366  call    _guard_dispatch_icall
0x14032736b  mov     r14, rsi
0x14032736e  test    rsi, rsi
0x140327371  jnz     loc_140327044
0x140327377  add     rsp, 68h
0x14032737b  pop     r15
0x14032737d  pop     r14
0x14032737f  pop     r13
0x140327381  pop     r12
0x140327383  pop     rdi
0x140327384  pop     rsi
0x140327385  pop     rbp
0x140327386  pop     rbx
0x140327387  retn
0x140327389  mov     rcx, r13; this
0x14032738c  call    ?AcquireSharedUncheck@COREDEVICEACCESS@@QEAAXPEBD@Z; COREDEVICEACCESS::AcquireSharedUncheck(char const *)
0x140327391  jmp     loc_140326FF8
0x140327396  cmp     [r14+18h], rbp
0x14032739a  jz      loc_140327055
0x1403273a0  shr     edx, 6
0x1403273a3  mov     r8, r14; struct DXGALLOCATION *
0x1403273a6  and     edx, 0Fh; unsigned int
0x1403273a9  mov     rcx, r12; this
  ... truncated ...
```
