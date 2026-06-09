# DXGPROCESS::Destroy(_DXGK_DISPLAY_SCENARIO_CONTEXT *,uchar)

- ea: `0x1403a4e44`
- end: `0x1403a58ad`
- name: `?Destroy@DXGPROCESS@@QEAAXPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@E@Z`
- size: `2665`
- prototype: `void __fastcall(DXGPROCESS *__hidden this, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *, unsigned __int8)`
- caller_count: `4`
- callee_count: `59`
- tags: `broker_com_uri`

## callers

- `0x140258fe0`
- `0x14027811c`
- `0x1403a4b30`
- `0x1403fe894`

## callees

- `0x140012540`
- `0x140015448`
- `0x140015618`
- `0x140015a70`
- `0x140015b30`
- `0x140015b60`
- `0x140015f7c`
- `0x1400164c0`
- `0x140018054`
- `0x140018190`
- `0x14001b76c`
- `0x14001b9c0`
- `0x14001e5b4`
- `0x140030a30`
- `0x140033da4`
- `0x140034910`
- `0x14003c738`
- `0x14003d2ac`
- `0x140042cc0`
- `0x14004a714`
- `0x14004b598`
- `0x140056eb8`
- `0x140057c34`
- `0x140065fcc`
- `0x14006fb20`
- `0x1400a0bd0`
- `0x14018a9a4`
- `0x140193448`
- `0x1401943a8`
- `0x140197a74`
- `0x1401adef8`
- `0x1401c3ac8`
- `0x1401cb358`
- `0x1401d9ab4`
- `0x1401dcfc4`
- `0x1402437e0`
- `0x14024f024`
- `0x140259658`
- `0x140259e58`
- `0x14025a184`
- `0x14025abdc`
- `0x14026261c`
- `0x1402727c8`
- `0x140294d10`
- `0x140328e00`
- `0x140329c00`
- `0x140329ff0`
- `0x14036d1f4`
- `0x1403744c8`
- `0x140375314`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403a4fe5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403a5012`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403a4fe5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403a5012`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a4fd3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a5000`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a4fd3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a5000`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403a516d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403a516d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403a5161`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403a5161`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403a4eda`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403a4eda`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403a4ebd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403a4ebd`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403a4f18`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403a5792`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403a4f18`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403a5792`
- `ntoskrnl!PsGetProcessExitStatus` at `0x1403a4ecc`
- `ntoskrnl!PsGetProcessExitStatus` at `0x1403a4ecc`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403a51a8`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403a51a8`
- `watchdog!WdLogSingleEntry0` at `0x1403a5043`
- `watchdog!WdLogSingleEntry0` at `0x1403a522a`
- `watchdog!WdLogSingleEntry0` at `0x1403a5382`
- `watchdog!WdLogSingleEntry0` at `0x1403a54f8`
- `watchdog!WdLogSingleEntry0` at `0x1403a55b3`
- `watchdog!WdLogSingleEntry0` at `0x1403a5654`
- `watchdog!WdLogSingleEntry0` at `0x1403a56bd`
- `watchdog!WdLogSingleEntry0` at `0x1403a5720`
- `watchdog!WdLogSingleEntry0` at `0x1403a5043`
- `watchdog!WdLogSingleEntry0` at `0x1403a522a`
- `watchdog!WdLogSingleEntry0` at `0x1403a5382`
- `watchdog!WdLogSingleEntry0` at `0x1403a54f8`
- `watchdog!WdLogSingleEntry0` at `0x1403a55b3`
- `watchdog!WdLogSingleEntry0` at `0x1403a5654`
- `watchdog!WdLogSingleEntry0` at `0x1403a56bd`
- `watchdog!WdLogSingleEntry0` at `0x1403a5720`

## pseudocode

```c
void __fastcall DXGPROCESS::Destroy(DXGPROCESS *this, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *a2, char a3)
{
  int v3; // eax
  char v4; // r12
  DXGGLOBAL *Global; // rax
  struct DXGSESSIONDATA *SessionData; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  struct _KPROCESS *CurrentProcess; // rax
  unsigned int ProcessExitStatus; // ebx
  unsigned int CurrentProcessSessionId; // eax
  _QWORD *v15; // r14
  __int64 v16; // rbx
  __int64 v17; // r15
  __int64 v18; // rsi
  const char *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rdx
  _QWORD *v24; // rax
  const char *v25; // rdx
  __int64 v26; // rcx
  OUTPUTDUPL_MGR *RemoteOutputDuplMgr; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  _QWORD *v30; // rbx
  bool v31; // r8
  __int64 v32; // rsi
  __int64 v33; // r14
  DXGVIRTUALMACHINE *v34; // rcx
  DXGVIRTUALMACHINE *v35; // rcx
  __int64 v36; // rdx
  unsigned int v37; // ecx
  unsigned int v38; // esi
  int v39; // eax
  int v40; // eax
  struct DXGPROTECTEDSESSION *EntryObject; // rbx
  unsigned int v42; // eax
  unsigned int v43; // ebx
  DXGKEYEDMUTEX *v44; // rcx
  int v45; // r8d
  DXGSYNCOBJECT *v46; // rbx
  unsigned int v47; // r15d
  DXGGLOBAL *v48; // rax
  struct DXGGLOBAL *v49; // rax
  unsigned int i; // esi
  int v51; // eax
  unsigned int v52; // ebx
  DXGSHAREDVMOBJECT *v53; // rax
  struct DXGPROCESS *v54; // rbx
  unsigned int v55; // ebx
  int EntryType; // eax
  DXGK_TRANSPORT_BUFFER *v57; // rax
  unsigned int v58; // eax
  DXGGLOBAL *v59; // rax
  DXGGLOBAL *v60; // rax
  DXGSESSIONDATA *v61; // rax
  int v62; // eax
  struct DXGGLOBAL *v63; // rax
  int v64; // edx
  __int64 v65; // rax
  __int64 v66; // rcx
  struct DXGGLOBAL *v67; // rax
  char v68; // [rsp+50h] [rbp-B0h] BYREF
  char v69; // [rsp+51h] [rbp-AFh]
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v71[160]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = *((_DWORD *)this + 102);
  v4 = 0;
  if ( (v3 & 4) != 0 && (v3 & 0x100) == 0 )
  {
    Global = DXGGLOBAL::GetGlobal();
    SessionData = DXGGLOBAL::GetSessionData(Global);
    if ( SessionData )
      DispBrokerClient::DisconnectDisplayBroker((struct DXGSESSIONDATA *)((char *)SessionData + 18984));
    Interval.QuadPart = 0;
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v11, v10);
    ProcessExitStatus = PsGetProcessExitStatus(CurrentProcess);
    CurrentProcessSessionId = PsGetCurrentProcessSessionId();
    DxgkLogCodePointPacketForSession(115, CurrentProcessSessionId, ProcessExitStatus, 0, 0, 0);
  }
  while ( *((_DWORD *)this + 106) )
  {
    Interval.QuadPart = -100000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  v69 = 0;
  DXGCRITICALREGION::Enter((DXGCRITICALREGION *)&v68);
  if ( (*((_BYTE *)this + 408) & 1) != 0 && (*((_DWORD *)this + 102) & 0x100) == 0 )
    DxgkDestroyCsrssProcess();
  v15 = (_QWORD *)((char *)this + 320);
  if ( (_QWORD *)*v15 != v15 )
  {
    if ( !a3 )
      DXGPROCESS::ReleaseVidPnSourceOwners(this, a2);
    while ( (_QWORD *)*v15 != v15 )
    {
      v16 = (*v15 - 24LL) & ((unsigned __int128)-(__int128)(unsigned __int64)*v15 >> 64);
      v17 = *(_QWORD *)(*(_QWORD *)(v16 + 0x10) + 16LL);
      OutputDuplProcessTerminateForWddm((struct DXGADAPTER *)v17, *(struct DXGADAPTER **)(v16 + 0x768));
      COREDEVICEACCESS::COREDEVICEACCESS(v71, v16, 2);
      v18 = *(_QWORD *)(v17 + 3256);
      if ( *(_DWORD *)(v16 + 464) == 2 )
      {
        v4 = 1;
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v18 + 48, 0);
        *(_QWORD *)(v18 + 56) = KeGetCurrentThread();
      }
      else
      {
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v18 + 24, 0);
        *(_QWORD *)(v18 + 32) = KeGetCurrentThread();
      }
      COREDEVICEACCESS::AcquireSharedUncheck((COREDEVICEACCESS *)v71, v19);
      if ( !*(_QWORD *)(v17 + 3256) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 2159;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pAdapter->IsRenderAdapter()", 2159, 0, 0, 0, 0);
      }
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 16) + 16LL) + 200LL) == 4 )
      {
        v20 = v16 + 24;
        v21 = -v16;
        v22 = v20 & -(__int64)(v21 != 0);
        v23 = *(_QWORD *)v22;
        if ( *(_QWORD *)(*(_QWORD *)v22 + 8LL) != v22
          || (v24 = *(_QWORD **)((v20 & -(__int64)(v21 != 0)) + 8), *v24 != v22) )
        {
          __fastfail(3u);
        }
        *v24 = v23;
        *(_QWORD *)(v23 + 8) = v24;
      }
      else
      {
        if ( *(_DWORD *)(v16 + 608) == 1 )
        {
          COREDEVICEACCESS::Release((COREDEVICEACCESS *)v71);
          DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(
            (DXGADAPTERSTOPRESETLOCKSHARED *)&Interval,
            (struct DXGADAPTER *)v17,
            1u);
          if ( *(_DWORD *)(v17 + 200) == 1 )
            DXGDEVICE::FlushScheduler(v16, 4, 4294967293LL);
          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)&Interval);
          COREDEVICEACCESS::AcquireSharedUncheck((COREDEVICEACCESS *)v71, v25);
          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)&Interval);
        }
        ADAPTER_RENDER::DestroyDevice(*(ADAPTER_RENDER **)(v17 + 3256), (struct DXGDEVICE *)v16, 0);
      }
      if ( v4 )
      {
        v4 = 0;
        v26 = v18 + 48;
        *(_QWORD *)(v18 + 56) = 0;
      }
      else
      {
        v4 = 0;
        v26 = v18 + 24;
        *(_QWORD *)(v18 + 32) = 0;
      }
      ExReleasePushLockExclusiveEx(v26, 0);
      KeLeaveCriticalRegion();
      COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v71);
    }
  }
  RemoteOutputDuplMgr = FindRemoteOutputDuplMgr();
  if ( RemoteOutputDuplMgr )
  {
    OUTPUTDUPL_MGR::ProcessPendingProcessTerminate(RemoteOutputDuplMgr);
  }
  else
  {
    WdLogNewEntry5_WdTrace(v28);
    WdLogGlobalForLineNumber = 3104;
  }
  OutputDuplProcessTerminateForSession(v29);
  v30 = (_QWORD *)((char *)this + 344);
  if ( (_QWORD *)*v30 != v30 )
  {
    DXGFASTMUTEX::Acquire((DXGPROCESS *)((char *)this + 360));
    while ( (_QWORD *)*v30 != v30 )
    {
      v32 = (*v30 - 24LL) & -(__int64)(*v30 != 0);
      v33 = *(_QWORD *)(*(_QWORD *)(v32 + 0x10) + 16LL);
      COREACCESS::COREACCESS((COREACCESS *)&Interval, (struct DXGADAPTER *const)v33, v31);
      COREACCESS::AcquireShared((COREACCESS *)&Interval, 0);
      if ( !*(_QWORD *)(v33 + 3248) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 2234;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pAdapter->IsDisplayAdapter()", 2234, 0, 0, 0, 0);
      }
      if ( *(_DWORD *)(v33 + 200) == 4 )
        DXGPROCESS::RemoveCopyProtection(this, (struct DXGCOPYPROTECTION *)v32);
      else
        ADAPTER_DISPLAY::DestroyCopyProtection(
          *(ADAPTER_DISPLAY **)(v33 + 3248),
          *(_DWORD *)(v32 + 52),
          *(_DWORD *)(v32 + 48));
      COREACCESS::~COREACCESS((COREACCESS *)&Interval);
    }
    DXGFASTMUTEX::Release((DXGPROCESS *)((char *)this + 360));
  }
  if ( (*((_DWORD *)this + 102) & 0x80u) != 0 )
  {
    v34 = (DXGVIRTUALMACHINE *)*((_QWORD *)this + 75);
    if ( v34 )
      DXGVIRTUALMACHINE::FlushDevicesForTermination(v34);
    v35 = (DXGVIRTUALMACHINE *)*((_QWORD *)this + 75);
    if ( v35 )
      DXGVIRTUALMACHINE::PauseVmBusChannels(v35);
  }
  v36 = *((unsigned int *)this + 75);
  v37 = *((_DWORD *)this + 74);
  if ( (_DWORD)v36 != v37 )
  {
    v38 = 0;
    if ( v37 )
    {
      do
      {
        v39 = HMGRTABLE::GetEntryType((char *)this + 280) - 8;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( v40 )
          {
            if ( v40 == 5 )
            {
              EntryObject = (struct DXGPROTECTEDSESSION *)HMGRTABLE::GetEntryObject(
                                                            (DXGPROCESS *)((char *)this + 280),
                                                            v38);
              v42 = HMGRTABLE::BuildEntryHandle((DXGPROCESS *)((char *)this + 280), v38);
              DXGPROTECTEDSESSION::DestroyProtectedSession(EntryObject, v42);
            }
          }
          else
          {
            HMGRTABLE::GetEntryObject((DXGPROCESS *)((char *)this + 280), v38);
            v43 = HMGRTABLE::BuildEntryHandle((DXGPROCESS *)((char *)this + 280), v38);
            DXGKEYEDMUTEX::SignalAbandoned(v44, v43, v45);
            if ( !DXGKEYEDMUTEX::DestroyHandle(v43) )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 2317;
              DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"bStatus", 2317, 0, 0, 0, 0);
            }
          }
        }
        else
        {
          v46 = (DXGSYNCOBJECT *)HMGRTABLE::GetEntryObject((DXGPROCESS *)((char *)this + 280), v38);
          v47 = HMGRTABLE::BuildEntryHandle((DXGPROCESS *)((char *)this + 280), v38);
          if ( (*((_DWORD *)this + 102) & 0x80) != 0 )
          {
            v49 = DXGGLOBAL::GetGlobal();
            DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)&Interval, v49, 0);
            DXGSYNCOBJECTLOCK::AcquireExclusive((DXGSYNCOBJECTLOCK *)&Interval);
            DXGSYNCOBJECT::SetVmSyncObject(v46, 0);
            *((_DWORD *)v46 + 20) = 0;
            DXGPROCESS::FreeHandleSafe(this, v47);
            DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)&Interval);
          }
          else
          {
            v48 = DXGGLOBAL::GetGlobal();
            DXGGLOBAL::DestroySyncObject(v48, v46, v47, 0);
          }
        }
        v37 = *((_DWORD *)this + 74);
        ++v38;
      }
      while ( v38 < v37 );
      v36 = *((unsigned int *)this + 75);
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x80u) != 0 && (_DWORD)v36 != v37 )
  {
    for ( i = 0; i < v37; ++i )
    {
      v51 = HMGRTABLE::GetEntryType((char *)this + 280) - 12;
      if ( v51 )
      {
        if ( v51 == 1 )
        {
          v52 = HMGRTABLE::BuildEntryHandle((DXGPROCESS *)((char *)this + 280), i);
          v53 = (DXGSHAREDVMOBJECT *)HMGRTABLE::GetEntryObject((DXGPROCESS *)((char *)this + 280), i);
          DXGSHAREDVMOBJECT::ReleaseReference(v53);
          DXGPROCESS::FreeHandleSafe(this, v52);
        }
      }
      else
      {
        v54 = (struct DXGPROCESS *)HMGRTABLE::GetEntryObject((DXGPROCESS *)((char *)this + 280), i);
        if ( (*((_DWORD *)v54 + 102) & 0x100) == 0 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 2356;
          DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pProcess->IsVmProcess()", 2356, 0, 0, 0, 0);
        }
        CEnsureCurrentDxgProcess::CEnsureCurrentDxgProcess((CEnsureCurrentDxgProcess *)&Interval, v54, 1u);
        DXGPROCESS::DestroyDxgProcess(v54);
        CEnsureCurrentDxgProcess::~CEnsureCurrentDxgProcess((CEnsureCurrentDxgProcess *)&Interval);
      }
      v37 = *((_DWORD *)this + 74);
    }
  }
  if ( *((_DWORD *)this + 75) != v37 )
  {
    v55 = 0;
    if ( v37 )
    {
      do
      {
        EntryType = HMGRTABLE::GetEntryType((char *)this + 280);
        v36 = (unsigned int)(EntryType - 1);
        if ( EntryType == 1 )
        {
          v58 = HMGRTABLE::BuildEntryHandle((DXGPROCESS *)((char *)this + 280), v55);
          DXGADAPTER::DestroyHandle(this, v58);
        }
        else if ( EntryType == 20 )
        {
          v57 = (DXGK_TRANSPORT_BUFFER *)HMGRTABLE::GetEntryObject((DXGPROCESS *)((char *)this + 280), v55);
          if ( *((_BYTE *)v57 + 40) )
            DXGK_TRANSPORT_BUFFER::Destroy(v57);
        }
        else if ( EntryType )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 2398;
          DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"EntryType == HMGRENTRY_TYPE_FREE", 2398, 0, 0, 0, 0);
        }
        ++v55;
      }
      while ( v55 < *((_DWORD *)this + 74) );
    }
  }
  if ( *((_QWORD *)this + 72) )
  {
    DXGPROCESS::SetVailObject(this, 0);
    if ( *((_QWORD *)this + 72) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2411;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!IsVailProcess()", 2411, 0, 0, 0, 0);
    }
  }
  if ( *((_BYTE *)this + 584) )
  {
    v59 = DXGGLOBAL::GetGlobal();
    if ( !DXGGLOBAL::GetSessionData(v59) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2419;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"DXGGLOBAL::GetGlobal()->GetSessionData()",
        2419,
        0,
        0,
        0,
        0);
    }
    v60 = DXGGLOBAL::GetGlobal();
    v61 = DXGGLOBAL::GetSessionData(v60);
    if ( (int)DXGSESSIONDATA::VailGuestDisconnect(v61) < 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2421;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(_Status)", 2421, 0, 0, 0, 0);
    }
    *((_BYTE *)this + 584) = 0;
  }
  VidSchTerminateProcessX(this, v36);
  VidMmTerminateProcessX(this);
  while ( *((int *)this + 107) > 0 )
  {
    Interval.QuadPart = -100000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  v62 = *((_DWORD *)this + 102);
  if ( a3 )
  {
    if ( (v62 & 0x80u) != 0 )
      DXGPROCESSVMWP::ResetVirtualMachine(this);
  }
  else if ( (v62 & 0x40) != 0 )
  {
    v63 = DXGGLOBAL::GetGlobal();
    DXGGLOBAL::IterateAdaptersWithCallback(v63, DestroyProcessCallback, this, 2);
  }
  DXGCRITICALREGION::Leave((DXGCRITICALREGION *)&v68);
  v64 = *((_DWORD *)this + 102);
  if ( (v64 & 0x100) != 0 )
  {
    DXGPROCESSVM::DestroyVmProcess(this);
  }
  else if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
  {
    v65 = *((_QWORD *)this + 8);
    if ( v65 )
      v66 = *(_QWORD *)(v65 + 80);
    else
      LODWORD(v66) = 0;
    McTemplateK0pxqt_EtwWriteTransfer(
      v66,
      (unsigned int)EventDestroyDxgProcess,
      *((_DWORD *)this + 122),
      (_DWORD)this,
      v66,
      *((_DWORD *)this + 122),
      v64);
  }
  if ( !a3 )
    *((_DWORD *)this + 10) = 2;
  if ( *((_DWORD *)this + 122) )
  {
    v67 = DXGGLOBAL::GetGlobal();
    DXG_GUEST_GLOBAL_VMBUS::VmBusSendDestroyProcess(*((DXG_GUEST_GLOBAL_VMBUS **)v67 + 212), *((_DWORD *)this + 122));
    *((_DWORD *)this + 122) = 0;
  }
  if ( v69 )
    DXGCRITICALREGION::Leave((DXGCRITICALREGION *)&v68);
}

```

## disassembly

```asm
0x1403a4e44  mov     [rsp-8+arg_10], rbx
0x1403a4e49  push    rbp
0x1403a4e4a  push    rsi
0x1403a4e4b  push    rdi
0x1403a4e4c  push    r12
0x1403a4e4e  push    r13
0x1403a4e50  push    r14
0x1403a4e52  push    r15
0x1403a4e54  lea     rbp, [rsp-50h]
0x1403a4e59  sub     rsp, 150h
0x1403a4e60  mov     rax, cs:__security_cookie
0x1403a4e67  xor     rax, rsp
0x1403a4e6a  mov     [rbp+80h+var_40], rax
0x1403a4e6e  mov     eax, [rcx+198h]
0x1403a4e74  xor     r12d, r12d
0x1403a4e77  mov     r13b, r8b
0x1403a4e7a  mov     rsi, rdx
0x1403a4e7d  mov     rdi, rcx
0x1403a4e80  mov     r15d, 1
0x1403a4e86  test    al, 4
0x1403a4e88  jz      loc_1403A4F24
0x1403a4e8e  shr     eax, 8
0x1403a4e91  test    r15b, al
0x1403a4e94  jnz     loc_1403A4F24
0x1403a4e9a  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1403a4e9f  mov     rcx, rax; this
0x1403a4ea2  call    ?GetSessionData@DXGGLOBAL@@QEAAPEAVDXGSESSIONDATA@@XZ; DXGGLOBAL::GetSessionData(void)
0x1403a4ea7  test    rax, rax
0x1403a4eaa  jz      short loc_1403A4EB8
0x1403a4eac  lea     rcx, [rax+4A28h]; this
0x1403a4eb3  call    ?DisconnectDisplayBroker@DispBrokerClient@@QEAAXXZ; DispBrokerClient::DisconnectDisplayBroker(void)
0x1403a4eb8  mov     qword ptr [rsp+180h+Interval], r12
0x1403a4ebd  call    cs:__imp_PsGetCurrentProcess
0x1403a4ec4  nop     dword ptr [rax+rax+00h]
0x1403a4ec9  mov     rcx, rax; Process
0x1403a4ecc  call    cs:__imp_PsGetProcessExitStatus
0x1403a4ed3  nop     dword ptr [rax+rax+00h]
0x1403a4ed8  mov     ebx, eax
0x1403a4eda  call    cs:__imp_PsGetCurrentProcessSessionId
0x1403a4ee1  nop     dword ptr [rax+rax+00h]
0x1403a4ee6  mov     rcx, r12
0x1403a4ee9  xor     r9d, r9d
0x1403a4eec  mov     edx, eax
0x1403a4eee  mov     r8d, ebx
0x1403a4ef1  mov     [rsp+180h+var_158], rcx
0x1403a4ef6  mov     dword ptr [rsp+180h+var_160], r12d
0x1403a4efb  lea     ecx, [r9+73h]
0x1403a4eff  call    ?DxgkLogCodePointPacketForSession@@YAXW4_DXGK_DIAG_CODE_POINT_TYPE@@_KIIIU_LUID@@@Z; DxgkLogCodePointPacketForSession(_DXGK_DIAG_CODE_POINT_TYPE,unsigned __int64,uint,uint,uint,_LUID)
0x1403a4f04  jmp     short loc_1403A4F24
0x1403a4f06  lea     r8, [rsp+180h+Interval]; Interval
0x1403a4f0b  mov     qword ptr [rsp+180h+Interval], 0FFFFFFFFFFFE7960h
0x1403a4f14  xor     edx, edx; Alertable
0x1403a4f16  xor     ecx, ecx; WaitMode
0x1403a4f18  call    cs:__imp_KeDelayExecutionThread
0x1403a4f1f  nop     dword ptr [rax+rax+00h]
0x1403a4f24  mov     eax, [rdi+1A8h]
0x1403a4f2a  test    eax, eax
0x1403a4f2c  jnz     short loc_1403A4F06
0x1403a4f2e  lea     rcx, [rsp+180h+var_130]; this
0x1403a4f33  mov     [rsp+180h+var_12F], r12b
0x1403a4f38  call    ?Enter@DXGCRITICALREGION@@QEAAXXZ; DXGCRITICALREGION::Enter(void)
0x1403a4f3d  test    [rdi+198h], r15b
0x1403a4f44  jz      short loc_1403A4F59
0x1403a4f46  mov     eax, [rdi+198h]
0x1403a4f4c  shr     eax, 8
0x1403a4f4f  test    r15b, al
0x1403a4f52  jnz     short loc_1403A4F59
0x1403a4f54  call    DxgkDestroyCsrssProcess
0x1403a4f59  lea     r14, [rdi+140h]
0x1403a4f60  cmp     [r14], r14
0x1403a4f63  jz      loc_1403A5194
0x1403a4f69  test    r13b, r13b
0x1403a4f6c  jnz     short loc_1403A4F79
0x1403a4f6e  mov     rdx, rsi; struct _DXGK_DISPLAY_SCENARIO_CONTEXT *
0x1403a4f71  mov     rcx, rdi; this
0x1403a4f74  call    ?ReleaseVidPnSourceOwners@DXGPROCESS@@QEAAXPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; DXGPROCESS::ReleaseVidPnSourceOwners(_DXGK_DISPLAY_SCENARIO_CONTEXT *)
0x1403a4f79  mov     rcx, [r14]
0x1403a4f7c  cmp     rcx, r14
0x1403a4f7f  jz      loc_1403A518E
0x1403a4f85  lea     rax, [rcx-18h]
0x1403a4f89  neg     rcx
0x1403a4f8c  sbb     rbx, rbx
0x1403a4f8f  and     rbx, rax
0x1403a4f92  mov     rax, [rbx+10h]
0x1403a4f96  mov     rdx, [rbx+768h]; struct DXGADAPTER *
0x1403a4f9d  mov     r15, [rax+10h]
0x1403a4fa1  mov     rcx, r15; struct DXGADAPTER *
0x1403a4fa4  call    OutputDuplProcessTerminateForWddm
0x1403a4fa9  mov     r8d, 2
0x1403a4faf  mov     byte ptr [rsp+180h+var_160], r12b
0x1403a4fb4  mov     rdx, rbx
0x1403a4fb7  lea     rcx, [rbp+80h+var_E0]
0x1403a4fbb  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x1403a4fc0  cmp     dword ptr [rbx+1D0h], 2
0x1403a4fc7  mov     rsi, [r15+0CB8h]
0x1403a4fce  jnz     short loc_1403A5000
0x1403a4fd0  mov     r12b, 1
0x1403a4fd3  call    cs:__imp_KeEnterCriticalRegion
0x1403a4fda  nop     dword ptr [rax+rax+00h]
0x1403a4fdf  lea     rcx, [rsi+30h]
0x1403a4fe3  xor     edx, edx
0x1403a4fe5  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1403a4fec  nop     dword ptr [rax+rax+00h]
0x1403a4ff1  mov     rax, gs:188h
0x1403a4ffa  mov     [rsi+38h], rax
0x1403a4ffe  jmp     short loc_1403A502B
0x1403a5000  call    cs:__imp_KeEnterCriticalRegion
0x1403a5007  nop     dword ptr [rax+rax+00h]
0x1403a500c  lea     rcx, [rsi+18h]
0x1403a5010  xor     edx, edx
0x1403a5012  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1403a5019  nop     dword ptr [rax+rax+00h]
0x1403a501e  mov     rax, gs:188h
0x1403a5027  mov     [rsi+20h], rax
0x1403a502b  lea     rcx, [rbp+80h+var_E0]; this
0x1403a502f  call    ?AcquireSharedUncheck@COREDEVICEACCESS@@QEAAXPEBD@Z; COREDEVICEACCESS::AcquireSharedUncheck(char const *)
0x1403a5034  cmp     qword ptr [r15+0CB8h], 0
0x1403a503c  jnz     short loc_1403A508C
0x1403a503e  mov     ecx, 1
0x1403a5043  call    cs:__imp_WdLogSingleEntry0
0x1403a504a  nop     dword ptr [rax+rax+00h]
0x1403a504f  xor     eax, eax
0x1403a5051  lea     r9, aPadapterIsrend; "pAdapter->IsRenderAdapter()"
0x1403a5058  mov     [rsp+180h+var_140], rax
0x1403a505d  mov     ecx, 86Fh
0x1403a5062  mov     [rsp+180h+var_148], rax
0x1403a5067  or      r8d, 0FFFFFFFFh
0x1403a506b  mov     [rsp+180h+var_150], rax
0x1403a5070  mov     edx, 40002h
0x1403a5075  mov     [rsp+180h+var_158], rax
0x1403a507a  mov     [rsp+180h+var_160], rcx
0x1403a507f  mov     cs:WdLogGlobalForLineNumber, ecx
0x1403a5085  xor     ecx, ecx
0x1403a5087  call    DxgkLogInternalTriageEvent
0x1403a508c  mov     rax, [rbx+10h]
0x1403a5090  mov     rcx, [rax+10h]
0x1403a5094  mov     eax, [rcx+0C8h]
0x1403a509a  cmp     eax, 4
0x1403a509d  jnz     short loc_1403A50CF
0x1403a509f  lea     rax, [rbx+18h]
0x1403a50a3  neg     rbx
0x1403a50a6  sbb     rcx, rcx
0x1403a50a9  and     rcx, rax
0x1403a50ac  mov     rdx, [rcx]
0x1403a50af  cmp     [rdx+8], rcx
0x1403a50b3  jnz     loc_1403A5187
0x1403a50b9  mov     rax, [rcx+8]
0x1403a50bd  cmp     [rax], rcx
0x1403a50c0  jnz     loc_1403A5187
0x1403a50c6  mov     [rax], rdx
0x1403a50c9  mov     [rdx+8], rax
0x1403a50cd  jmp     short loc_1403A5142
0x1403a50cf  mov     eax, [rbx+260h]
0x1403a50d5  cmp     eax, 1
0x1403a50d8  jnz     short loc_1403A5130
0x1403a50da  lea     rcx, [rbp+80h+var_E0]; this
0x1403a50de  call    ?Release@COREDEVICEACCESS@@QEAAXXZ; COREDEVICEACCESS::Release(void)
0x1403a50e3  mov     r8b, 1; unsigned __int8
0x1403a50e6  lea     rcx, [rsp+180h+Interval]; this
0x1403a50eb  mov     rdx, r15; struct DXGADAPTER *
0x1403a50ee  call    ??0DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@PEAVDXGADAPTER@@E@Z; DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(DXGADAPTER *,uchar)
0x1403a50f3  mov     eax, [r15+0C8h]
0x1403a50fa  cmp     eax, 1
0x1403a50fd  jnz     short loc_1403A5113
0x1403a50ff  xor     r9d, r9d
0x1403a5102  lea     edx, [rax+3]
0x1403a5105  mov     r8d, 0FFFFFFFDh
0x1403a510b  mov     rcx, rbx
0x1403a510e  call    ?FlushScheduler@DXGDEVICE@@QEAAXW4DXGDEVICE_FLUSHSCHEDULER_REASON@@I_N@Z; DXGDEVICE::FlushScheduler(DXGDEVICE_FLUSHSCHEDULER_REASON,uint,bool)
0x1403a5113  lea     rcx, [rsp+180h+Interval]; this
0x1403a5118  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1403a511d  lea     rcx, [rbp+80h+var_E0]; this
0x1403a5121  call    ?AcquireSharedUncheck@COREDEVICEACCESS@@QEAAXPEBD@Z; COREDEVICEACCESS::AcquireSharedUncheck(char const *)
0x1403a5126  lea     rcx, [rsp+180h+Interval]; this
0x1403a512b  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1403a5130  mov     rcx, [r15+0CB8h]; this
0x1403a5137  xor     r8d, r8d; struct COREDEVICEACCESS *
0x1403a513a  mov     rdx, rbx; struct DXGDEVICE *
0x1403a513d  call    ?DestroyDevice@ADAPTER_RENDER@@QEAAXPEAVDXGDEVICE@@PEAVCOREDEVICEACCESS@@@Z; ADAPTER_RENDER::DestroyDevice(DXGDEVICE *,COREDEVICEACCESS *)
0x1403a5142  xor     edx, edx
0x1403a5144  test    r12b, r12b
0x1403a5147  jz      short loc_1403A5156
0x1403a5149  xor     r12d, r12d
0x1403a514c  lea     rcx, [rsi+30h]
0x1403a5150  mov     [rsi+38h], r12
0x1403a5154  jmp     short loc_1403A5161
0x1403a5156  xor     r12d, r12d
0x1403a5159  lea     rcx, [rsi+18h]
0x1403a515d  mov     [rsi+20h], r12
0x1403a5161  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1403a5168  nop     dword ptr [rax+rax+00h]
0x1403a516d  call    cs:__imp_KeLeaveCriticalRegion
0x1403a5174  nop     dword ptr [rax+rax+00h]
0x1403a5179  lea     rcx, [rbp+80h+var_E0]; this
0x1403a517d  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1403a5182  jmp     loc_1403A4F79
0x1403a5187  mov     ecx, 3
0x1403a518c  int     29h; Win8: RtlFailFast(ecx)
0x1403a518e  mov     r15d, 1
0x1403a5194  call    ?FindRemoteOutputDuplMgr@@YAPEAVOUTPUTDUPL_MGR@@XZ; FindRemoteOutputDuplMgr(void)
0x1403a5199  test    rax, rax
0x1403a519c  jz      short loc_1403A51A8
0x1403a519e  mov     rcx, rax; this
0x1403a51a1  call    ?ProcessPendingProcessTerminate@OUTPUTDUPL_MGR@@QEAAXXZ; OUTPUTDUPL_MGR::ProcessPendingProcessTerminate(void)
0x1403a51a6  jmp     short loc_1403A51BE
0x1403a51a8  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1403a51af  nop     dword ptr [rax+rax+00h]
0x1403a51b4  mov     cs:WdLogGlobalForLineNumber, 0C20h
0x1403a51be  call    OutputDuplProcessTerminateForSession
0x1403a51c3  lea     rbx, [rdi+158h]
0x1403a51ca  cmp     [rbx], rbx
0x1403a51cd  jz      loc_1403A52BA
0x1403a51d3  lea     r15, [rdi+168h]
0x1403a51da  mov     rcx, r15; this
0x1403a51dd  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1403a51e2  mov     rcx, [rbx]
0x1403a51e5  cmp     rcx, rbx
0x1403a51e8  jz      loc_1403A52AC
0x1403a51ee  lea     rax, [rcx-18h]
0x1403a51f2  neg     rcx
0x1403a51f5  lea     rcx, [rsp+180h+Interval]; this
0x1403a51fa  sbb     rsi, rsi
0x1403a51fd  and     rsi, rax
0x1403a5200  mov     rax, [rsi+10h]
0x1403a5204  mov     r14, [rax+10h]
0x1403a5208  mov     rdx, r14; struct DXGADAPTER *
0x1403a520b  call    ??0COREACCESS@@QEAA@QEAVDXGADAPTER@@_N@Z; COREACCESS::COREACCESS(DXGADAPTER * const,bool)
0x1403a5210  xor     edx, edx; char *
0x1403a5212  lea     rcx, [rsp+180h+Interval]; this
0x1403a5217  call    ?AcquireShared@COREACCESS@@QEAAXPEBD@Z; COREACCESS::AcquireShared(char const *)
0x1403a521c  cmp     [r14+0CB0h], r12
0x1403a5223  jnz     short loc_1403A5271
0x1403a5225  mov     ecx, 1
0x1403a522a  call    cs:__imp_WdLogSingleEntry0
0x1403a5231  nop     dword ptr [rax+rax+00h]
0x1403a5236  mov     [rsp+180h+var_140], r12
0x1403a523b  lea     r9, aPadapterIsdisp; "pAdapter->IsDisplayAdapter()"
0x1403a5242  mov     [rsp+180h+var_148], r12
0x1403a5247  mov     eax, 8BAh
0x1403a524c  mov     [rsp+180h+var_150], r12
0x1403a5251  or      r8d, 0FFFFFFFFh
0x1403a5255  mov     [rsp+180h+var_158], r12
0x1403a525a  mov     edx, 40002h
0x1403a525f  xor     ecx, ecx
0x1403a5261  mov     [rsp+180h+var_160], rax
0x1403a5266  mov     cs:WdLogGlobalForLineNumber, eax
0x1403a526c  call    DxgkLogInternalTriageEvent
0x1403a5271  mov     eax, [r14+0C8h]
0x1403a5278  cmp     eax, 4
0x1403a527b  jnz     short loc_1403A528A
0x1403a527d  mov     rdx, rsi; struct DXGCOPYPROTECTION *
0x1403a5280  mov     rcx, rdi; this
0x1403a5283  call    ?RemoveCopyProtection@DXGPROCESS@@QEAAXPEAVDXGCOPYPROTECTION@@@Z; DXGPROCESS::RemoveCopyProtection(DXGCOPYPROTECTION *)
0x1403a5288  jmp     short loc_1403A529D
0x1403a528a  mov     r8d, [rsi+30h]; unsigned int
0x1403a528e  mov     edx, [rsi+34h]; unsigned int
0x1403a5291  mov     rcx, [r14+0CB0h]; this
0x1403a5298  call    ?DestroyCopyProtection@ADAPTER_DISPLAY@@QEAAJII@Z; ADAPTER_DISPLAY::DestroyCopyProtection(uint,uint)
0x1403a529d  lea     rcx, [rsp+180h+Interval]; this
0x1403a52a2  call    ??1COREACCESS@@QEAA@XZ; COREACCESS::~COREACCESS(void)
0x1403a52a7  jmp     loc_1403A51E2
0x1403a52ac  mov     rcx, r15; this
0x1403a52af  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1403a52b4  mov     r15d, 1
0x1403a52ba  mov     eax, [rdi+198h]
0x1403a52c0  test    al, al
0x1403a52c2  jns     short loc_1403A52E6
0x1403a52c4  mov     rcx, [rdi+258h]; this
0x1403a52cb  test    rcx, rcx
0x1403a52ce  jz      short loc_1403A52D5
0x1403a52d0  call    ?FlushDevicesForTermination@DXGVIRTUALMACHINE@@QEAAXXZ; DXGVIRTUALMACHINE::FlushDevicesForTermination(void)
0x1403a52d5  mov     rcx, [rdi+258h]; this
0x1403a52dc  test    rcx, rcx
0x1403a52df  jz      short loc_1403A52E6
0x1403a52e1  call    ?PauseVmBusChannels@DXGVIRTUALMACHINE@@QEAAXXZ; DXGVIRTUALMACHINE::PauseVmBusChannels(void)
0x1403a52e6  mov     edx, [rdi+12Ch]
0x1403a52ec  mov     ecx, [rdi+128h]
0x1403a52f2  cmp     edx, ecx
0x1403a52f4  jz      loc_1403A546D
0x1403a52fa  mov     esi, r12d
0x1403a52fd  test    ecx, ecx
0x1403a52ff  jz      loc_1403A546D
0x1403a5305  lea     r14, [rdi+118h]
0x1403a530c  mov     edx, esi
0x1403a530e  mov     rcx, r14
0x1403a5311  call    ?GetEntryType@HMGRTABLE@@QEAA?AW4_HMGRENTRY_TYPE@@I@Z; HMGRTABLE::GetEntryType(uint)
0x1403a5316  sub     eax, 8
0x1403a5319  jz      loc_1403A53CE
0x1403a531f  sub     eax, 1
0x1403a5322  jz      short loc_1403A5353
0x1403a5324  cmp     eax, 5
0x1403a5327  jnz     loc_1403A5456
0x1403a532d  mov     edx, esi; unsigned int
0x1403a532f  mov     rcx, r14; this
0x1403a5332  call    ?GetEntryObject@HMGRTABLE@@QEAAPEAXI@Z; HMGRTABLE::GetEntryObject(uint)
0x1403a5337  mov     edx, esi; unsigned int
0x1403a5339  mov     rcx, r14; this
0x1403a533c  mov     rbx, rax
0x1403a533f  call    ?BuildEntryHandle@HMGRTABLE@@QEAAII@Z; HMGRTABLE::BuildEntryHandle(uint)
0x1403a5344  mov     edx, eax; unsigned int
  ... truncated ...
```
