# DXGPROCESS::Destroy(_DXGK_DISPLAY_SCENARIO_CONTEXT *,uchar)

- ea: `0x1403a4064`
- end: `0x1403a4acd`
- name: `?Destroy@DXGPROCESS@@QEAAXPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@E@Z`
- size: `2665`
- prototype: `void __fastcall(DXGPROCESS *__hidden this, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *, unsigned __int8)`
- caller_count: `4`
- callee_count: `59`
- tags: `broker_com_uri`

## callers

- `0x140254990`
- `0x140272b5c`
- `0x1403a3d50`
- `0x140400e34`

## callees

- `0x140012380`
- `0x140015288`
- `0x140015458`
- `0x1400158b0`
- `0x140015970`
- `0x1400159a0`
- `0x140015dbc`
- `0x140016300`
- `0x140017fb8`
- `0x1400180f0`
- `0x14001b63c`
- `0x14001b890`
- `0x14001e3e4`
- `0x140030860`
- `0x140033bd4`
- `0x140034740`
- `0x14003c4d8`
- `0x14003d04c`
- `0x140042a60`
- `0x14004a514`
- `0x14004b398`
- `0x140056c48`
- `0x1400579c4`
- `0x140065bac`
- `0x14006f570`
- `0x1400a0100`
- `0x1401869a4`
- `0x14018f448`
- `0x1401903a8`
- `0x140193a74`
- `0x1401a9fe8`
- `0x1401c0ec8`
- `0x1401c8758`
- `0x1401d6eb4`
- `0x1401dac54`
- `0x140240c80`
- `0x14024ba44`
- `0x140255008`
- `0x140255808`
- `0x140255b34`
- `0x14025658c`
- `0x14025df58`
- `0x14026d208`
- `0x14028e3b0`
- `0x140322090`
- `0x140322e90`
- `0x140323280`
- `0x14036d1b4`
- `0x140374488`
- `0x1403752d4`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403a4205`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403a4232`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403a4205`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1403a4232`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a41f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a4220`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a41f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a4220`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403a438d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403a438d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403a4381`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403a4381`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403a40fa`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403a40fa`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403a40dd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403a40dd`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403a4138`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403a49b2`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403a4138`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403a49b2`
- `ntoskrnl!PsGetProcessExitStatus` at `0x1403a40ec`
- `ntoskrnl!PsGetProcessExitStatus` at `0x1403a40ec`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403a43c8`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403a43c8`
- `watchdog!WdLogSingleEntry0` at `0x1403a4263`
- `watchdog!WdLogSingleEntry0` at `0x1403a444a`
- `watchdog!WdLogSingleEntry0` at `0x1403a45a2`
- `watchdog!WdLogSingleEntry0` at `0x1403a4718`
- `watchdog!WdLogSingleEntry0` at `0x1403a47d3`
- `watchdog!WdLogSingleEntry0` at `0x1403a4874`
- `watchdog!WdLogSingleEntry0` at `0x1403a48dd`
- `watchdog!WdLogSingleEntry0` at `0x1403a4940`
- `watchdog!WdLogSingleEntry0` at `0x1403a4263`
- `watchdog!WdLogSingleEntry0` at `0x1403a444a`
- `watchdog!WdLogSingleEntry0` at `0x1403a45a2`
- `watchdog!WdLogSingleEntry0` at `0x1403a4718`
- `watchdog!WdLogSingleEntry0` at `0x1403a47d3`
- `watchdog!WdLogSingleEntry0` at `0x1403a4874`
- `watchdog!WdLogSingleEntry0` at `0x1403a48dd`
- `watchdog!WdLogSingleEntry0` at `0x1403a4940`

## pseudocode

```c
void __fastcall DXGPROCESS::Destroy(DXGPROCESS *this, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *a2, char a3)
{
  int v3; // eax
  char v4; // r12
  DXGGLOBAL *Global; // rax
  struct DXGSESSIONDATA *SessionData; // rax
  struct _KPROCESS *CurrentProcess; // rax
  unsigned int ProcessExitStatus; // ebx
  unsigned int CurrentProcessSessionId; // eax
  _QWORD *v13; // r14
  __int64 v14; // rbx
  __int64 v15; // r15
  __int64 v16; // rsi
  const char *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rax
  const char *v23; // rdx
  __int64 v24; // rcx
  OUTPUTDUPL_MGR *RemoteOutputDuplMgr; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  _QWORD *v28; // rbx
  bool v29; // r8
  __int64 v30; // rsi
  __int64 v31; // r14
  DXGVIRTUALMACHINE *v32; // rcx
  DXGVIRTUALMACHINE *v33; // rcx
  __int64 v34; // rdx
  unsigned int v35; // ecx
  unsigned int v36; // esi
  int v37; // eax
  int v38; // eax
  struct DXGPROTECTEDSESSION *EntryObject; // rbx
  unsigned int v40; // eax
  unsigned int v41; // ebx
  DXGKEYEDMUTEX *v42; // rcx
  int v43; // r8d
  DXGSYNCOBJECT *v44; // rbx
  unsigned int v45; // r15d
  DXGGLOBAL *v46; // rax
  struct DXGGLOBAL *v47; // rax
  unsigned int i; // esi
  int v49; // eax
  unsigned int v50; // ebx
  DXGSHAREDVMOBJECT *v51; // rax
  struct DXGPROCESS *v52; // rbx
  unsigned int v53; // ebx
  int EntryType; // eax
  DXGK_TRANSPORT_BUFFER *v55; // rax
  unsigned int v56; // eax
  DXGGLOBAL *v57; // rax
  DXGGLOBAL *v58; // rax
  DXGSESSIONDATA *v59; // rax
  int v60; // eax
  struct DXGGLOBAL *v61; // rax
  int v62; // edx
  __int64 v63; // rax
  __int64 v64; // rcx
  struct DXGGLOBAL *v65; // rax
  int v66; // [rsp+20h] [rbp-E0h]
  char v67; // [rsp+50h] [rbp-B0h] BYREF
  char v68; // [rsp+51h] [rbp-AFh]
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v70[160]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = *((_DWORD *)this + 102);
  v4 = 0;
  if ( (v3 & 4) != 0 && (v3 & 0x100) == 0 )
  {
    Global = DXGGLOBAL::GetGlobal();
    SessionData = DXGGLOBAL::GetSessionData(Global);
    if ( SessionData )
      DispBrokerClient::DisconnectDisplayBroker((struct DXGSESSIONDATA *)((char *)SessionData + 18984));
    Interval.QuadPart = 0;
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
    ProcessExitStatus = PsGetProcessExitStatus(CurrentProcess);
    CurrentProcessSessionId = PsGetCurrentProcessSessionId();
    DxgkLogCodePointPacketForSession(115, CurrentProcessSessionId, ProcessExitStatus, 0, 0, 0);
  }
  while ( *((_DWORD *)this + 106) )
  {
    Interval.QuadPart = -100000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  v68 = 0;
  DXGCRITICALREGION::Enter((DXGCRITICALREGION *)&v67);
  if ( (*((_BYTE *)this + 408) & 1) != 0 && (*((_DWORD *)this + 102) & 0x100) == 0 )
    DxgkDestroyCsrssProcess();
  v13 = (_QWORD *)((char *)this + 320);
  if ( (_QWORD *)*v13 != v13 )
  {
    if ( !a3 )
      DXGPROCESS::ReleaseVidPnSourceOwners(this, a2);
    while ( (_QWORD *)*v13 != v13 )
    {
      v14 = (*v13 - 24LL) & ((unsigned __int128)-(__int128)(unsigned __int64)*v13 >> 64);
      v15 = *(_QWORD *)(*(_QWORD *)(v14 + 0x10) + 16LL);
      OutputDuplProcessTerminateForWddm((struct DXGADAPTER *)v15, *(struct DXGADAPTER **)(v14 + 0x768));
      LOBYTE(v66) = 0;
      COREDEVICEACCESS::COREDEVICEACCESS(v70, v14, 2);
      v16 = *(_QWORD *)(v15 + 3240);
      if ( *(_DWORD *)(v14 + 464) == 2 )
      {
        v4 = 1;
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v16 + 48, 0);
        *(_QWORD *)(v16 + 56) = KeGetCurrentThread();
      }
      else
      {
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v16 + 24, 0);
        *(_QWORD *)(v16 + 32) = KeGetCurrentThread();
      }
      COREDEVICEACCESS::AcquireSharedUncheck((COREDEVICEACCESS *)v70, v17);
      if ( !*(_QWORD *)(v15 + 3240) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 2139;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pAdapter->IsRenderAdapter()", 2139, 0, 0, 0, 0);
      }
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 16) + 16LL) + 200LL) == 4 )
      {
        v18 = v14 + 24;
        v19 = -v14;
        v20 = v18 & -(__int64)(v19 != 0);
        v21 = *(_QWORD *)v20;
        if ( *(_QWORD *)(*(_QWORD *)v20 + 8LL) != v20
          || (v22 = *(_QWORD **)((v18 & -(__int64)(v19 != 0)) + 8), *v22 != v20) )
        {
          __fastfail(3u);
        }
        *v22 = v21;
        *(_QWORD *)(v21 + 8) = v22;
      }
      else
      {
        if ( *(_DWORD *)(v14 + 608) == 1 )
        {
          COREDEVICEACCESS::Release((COREDEVICEACCESS *)v70);
          DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(
            (DXGADAPTERSTOPRESETLOCKSHARED *)&Interval,
            (struct DXGADAPTER *)v15,
            1u);
          if ( *(_DWORD *)(v15 + 200) == 1 )
            DXGDEVICE::FlushScheduler(v14, 4, 4294967293LL);
          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)&Interval);
          COREDEVICEACCESS::AcquireSharedUncheck((COREDEVICEACCESS *)v70, v23);
          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)&Interval);
        }
        ADAPTER_RENDER::DestroyDevice(*(ADAPTER_RENDER **)(v15 + 3240), (struct DXGDEVICE *)v14, 0);
      }
      if ( v4 )
      {
        v4 = 0;
        v24 = v16 + 48;
        *(_QWORD *)(v16 + 56) = 0;
      }
      else
      {
        v4 = 0;
        v24 = v16 + 24;
        *(_QWORD *)(v16 + 32) = 0;
      }
      ExReleasePushLockExclusiveEx(v24, 0);
      KeLeaveCriticalRegion();
      COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v70);
    }
  }
  RemoteOutputDuplMgr = FindRemoteOutputDuplMgr();
  if ( RemoteOutputDuplMgr )
  {
    OUTPUTDUPL_MGR::ProcessPendingProcessTerminate(RemoteOutputDuplMgr);
  }
  else
  {
    WdLogNewEntry5_WdTrace(v26);
    WdLogGlobalForLineNumber = 3104;
  }
  OutputDuplProcessTerminateForSession(v27);
  v28 = (_QWORD *)((char *)this + 344);
  if ( (_QWORD *)*v28 != v28 )
  {
    DXGFASTMUTEX::Acquire((DXGPROCESS *)((char *)this + 360));
    while ( (_QWORD *)*v28 != v28 )
    {
      v30 = (*v28 - 24LL) & -(__int64)(*v28 != 0);
      v31 = *(_QWORD *)(*(_QWORD *)(v30 + 0x10) + 16LL);
      COREACCESS::COREACCESS((COREACCESS *)&Interval, (struct DXGADAPTER *const)v31, v29);
      COREACCESS::AcquireShared((COREACCESS *)&Interval, 0);
      if ( !*(_QWORD *)(v31 + 3232) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 2214;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pAdapter->IsDisplayAdapter()", 2214, 0, 0, 0, 0);
      }
      if ( *(_DWORD *)(v31 + 200) == 4 )
        DXGPROCESS::RemoveCopyProtection(this, (struct DXGCOPYPROTECTION *)v30);
      else
        ADAPTER_DISPLAY::DestroyCopyProtection(
          *(ADAPTER_DISPLAY **)(v31 + 3232),
          *(_DWORD *)(v30 + 52),
          *(_DWORD *)(v30 + 48));
      COREACCESS::~COREACCESS((COREACCESS *)&Interval);
    }
    DXGFASTMUTEX::Release((DXGPROCESS *)((char *)this + 360));
  }
  if ( (*((_DWORD *)this + 102) & 0x80u) != 0 )
  {
    v32 = (DXGVIRTUALMACHINE *)*((_QWORD *)this + 75);
    if ( v32 )
      DXGVIRTUALMACHINE::FlushDevicesForTermination(v32);
    v33 = (DXGVIRTUALMACHINE *)*((_QWORD *)this + 75);
    if ( v33 )
      DXGVIRTUALMACHINE::PauseVmBusChannels(v33);
  }
  v34 = *((unsigned int *)this + 75);
  v35 = *((_DWORD *)this + 74);
  if ( (_DWORD)v34 != v35 )
  {
    v36 = 0;
    if ( v35 )
    {
      do
      {
        v37 = HMGRTABLE::GetEntryType((char *)this + 280, v36) - 8;
        if ( v37 )
        {
          v38 = v37 - 1;
          if ( v38 )
          {
            if ( v38 == 5 )
            {
              EntryObject = (struct DXGPROTECTEDSESSION *)HMGRTABLE::GetEntryObject(
                                                            (DXGPROCESS *)((char *)this + 280),
                                                            v36);
              v40 = HMGRTABLE::BuildEntryHandle((DXGPROCESS *)((char *)this + 280), v36);
              DXGPROTECTEDSESSION::DestroyProtectedSession(EntryObject, v40);
            }
          }
          else
          {
            HMGRTABLE::GetEntryObject((DXGPROCESS *)((char *)this + 280), v36);
            v41 = HMGRTABLE::BuildEntryHandle((DXGPROCESS *)((char *)this + 280), v36);
            DXGKEYEDMUTEX::SignalAbandoned(v42, v41, v43);
            if ( !DXGKEYEDMUTEX::DestroyHandle(v41) )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 2297;
              DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"bStatus", 2297, 0, 0, 0, 0);
            }
          }
        }
        else
        {
          v44 = (DXGSYNCOBJECT *)HMGRTABLE::GetEntryObject((DXGPROCESS *)((char *)this + 280), v36);
          v45 = HMGRTABLE::BuildEntryHandle((DXGPROCESS *)((char *)this + 280), v36);
          if ( (*((_DWORD *)this + 102) & 0x80) != 0 )
          {
            v47 = DXGGLOBAL::GetGlobal();
            DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)&Interval, v47, 0);
            DXGSYNCOBJECTLOCK::AcquireExclusive((DXGSYNCOBJECTLOCK *)&Interval);
            DXGSYNCOBJECT::SetVmSyncObject(v44, 0);
            *((_DWORD *)v44 + 20) = 0;
            DXGPROCESS::FreeHandleSafe(this, v45);
            DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)&Interval);
          }
          else
          {
            v46 = DXGGLOBAL::GetGlobal();
            DXGGLOBAL::DestroySyncObject(v46, v44, v45, 0);
          }
        }
        v35 = *((_DWORD *)this + 74);
        ++v36;
      }
      while ( v36 < v35 );
      v34 = *((unsigned int *)this + 75);
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x80u) != 0 && (_DWORD)v34 != v35 )
  {
    for ( i = 0; i < v35; ++i )
    {
      v49 = HMGRTABLE::GetEntryType((char *)this + 280, i) - 12;
      if ( v49 )
      {
        if ( v49 == 1 )
        {
          v50 = HMGRTABLE::BuildEntryHandle((DXGPROCESS *)((char *)this + 280), i);
          v51 = (DXGSHAREDVMOBJECT *)HMGRTABLE::GetEntryObject((DXGPROCESS *)((char *)this + 280), i);
          DXGSHAREDVMOBJECT::ReleaseReference(v51);
          DXGPROCESS::FreeHandleSafe(this, v50);
        }
      }
      else
      {
        v52 = (struct DXGPROCESS *)HMGRTABLE::GetEntryObject((DXGPROCESS *)((char *)this + 280), i);
        if ( (*((_DWORD *)v52 + 102) & 0x100) == 0 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 2336;
          DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pProcess->IsVmProcess()", 2336, 0, 0, 0, 0);
        }
        CEnsureCurrentDxgProcess::CEnsureCurrentDxgProcess((CEnsureCurrentDxgProcess *)&Interval, v52, 1u);
        DXGPROCESS::DestroyDxgProcess(v52);
        CEnsureCurrentDxgProcess::~CEnsureCurrentDxgProcess((CEnsureCurrentDxgProcess *)&Interval);
      }
      v35 = *((_DWORD *)this + 74);
    }
  }
  if ( *((_DWORD *)this + 75) != v35 )
  {
    v53 = 0;
    if ( v35 )
    {
      do
      {
        EntryType = HMGRTABLE::GetEntryType((char *)this + 280, v53);
        v34 = (unsigned int)(EntryType - 1);
        if ( EntryType == 1 )
        {
          v56 = HMGRTABLE::BuildEntryHandle((DXGPROCESS *)((char *)this + 280), v53);
          DXGADAPTER::DestroyHandle(this, v56);
        }
        else if ( EntryType == 20 )
        {
          v55 = (DXGK_TRANSPORT_BUFFER *)HMGRTABLE::GetEntryObject((DXGPROCESS *)((char *)this + 280), v53);
          if ( *((_BYTE *)v55 + 40) )
            DXGK_TRANSPORT_BUFFER::Destroy(v55);
        }
        else if ( EntryType )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 2378;
          DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"EntryType == HMGRENTRY_TYPE_FREE", 2378, 0, 0, 0, 0);
        }
        ++v53;
      }
      while ( v53 < *((_DWORD *)this + 74) );
    }
  }
  if ( *((_QWORD *)this + 72) )
  {
    DXGPROCESS::SetVailObject(this, 0);
    if ( *((_QWORD *)this + 72) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2391;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!IsVailProcess()", 2391, 0, 0, 0, 0);
    }
  }
  if ( *((_BYTE *)this + 584) )
  {
    v57 = DXGGLOBAL::GetGlobal();
    if ( !DXGGLOBAL::GetSessionData(v57) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2399;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"DXGGLOBAL::GetGlobal()->GetSessionData()",
        2399,
        0,
        0,
        0,
        0);
    }
    v58 = DXGGLOBAL::GetGlobal();
    v59 = DXGGLOBAL::GetSessionData(v58);
    if ( (int)DXGSESSIONDATA::VailGuestDisconnect(v59) < 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2401;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(_Status)", 2401, 0, 0, 0, 0);
    }
    *((_BYTE *)this + 584) = 0;
  }
  VidSchTerminateProcessX(this, v34);
  VidMmTerminateProcessX(this);
  while ( *((int *)this + 107) > 0 )
  {
    Interval.QuadPart = -100000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  v60 = *((_DWORD *)this + 102);
  if ( a3 )
  {
    if ( (v60 & 0x80u) != 0 )
      DXGPROCESSVMWP::ResetVirtualMachine(this);
  }
  else if ( (v60 & 0x40) != 0 )
  {
    v61 = DXGGLOBAL::GetGlobal();
    DXGGLOBAL::IterateAdaptersWithCallback(v61, DestroyProcessCallback, this, 2, v66);
  }
  DXGCRITICALREGION::Leave((DXGCRITICALREGION *)&v67);
  v62 = *((_DWORD *)this + 102);
  if ( (v62 & 0x100) != 0 )
  {
    DXGPROCESSVM::DestroyVmProcess(this);
  }
  else if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
  {
    v63 = *((_QWORD *)this + 8);
    if ( v63 )
      v64 = *(_QWORD *)(v63 + 80);
    else
      LODWORD(v64) = 0;
    McTemplateK0pxqt_EtwWriteTransfer(
      v64,
      (unsigned int)EventDestroyDxgProcess,
      *((_DWORD *)this + 122),
      (_DWORD)this,
      v64,
      *((_DWORD *)this + 122),
      v62);
  }
  if ( !a3 )
    *((_DWORD *)this + 10) = 2;
  if ( *((_DWORD *)this + 122) )
  {
    v65 = DXGGLOBAL::GetGlobal();
    DXG_GUEST_GLOBAL_VMBUS::VmBusSendDestroyProcess(*((DXG_GUEST_GLOBAL_VMBUS **)v65 + 212), *((_DWORD *)this + 122));
    *((_DWORD *)this + 122) = 0;
  }
  if ( v68 )
    DXGCRITICALREGION::Leave((DXGCRITICALREGION *)&v67);
}

```

## disassembly

```asm
0x1403a4064  mov     [rsp-8+arg_10], rbx
0x1403a4069  push    rbp
0x1403a406a  push    rsi
0x1403a406b  push    rdi
0x1403a406c  push    r12
0x1403a406e  push    r13
0x1403a4070  push    r14
0x1403a4072  push    r15
0x1403a4074  lea     rbp, [rsp-50h]
0x1403a4079  sub     rsp, 150h
0x1403a4080  mov     rax, cs:__security_cookie
0x1403a4087  xor     rax, rsp
0x1403a408a  mov     [rbp+80h+var_40], rax
0x1403a408e  mov     eax, [rcx+198h]
0x1403a4094  xor     r12d, r12d
0x1403a4097  mov     r13b, r8b
0x1403a409a  mov     rsi, rdx
0x1403a409d  mov     rdi, rcx
0x1403a40a0  mov     r15d, 1
0x1403a40a6  test    al, 4
0x1403a40a8  jz      loc_1403A4144
0x1403a40ae  shr     eax, 8
0x1403a40b1  test    r15b, al
0x1403a40b4  jnz     loc_1403A4144
0x1403a40ba  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1403a40bf  mov     rcx, rax; this
0x1403a40c2  call    ?GetSessionData@DXGGLOBAL@@QEAAPEAVDXGSESSIONDATA@@XZ; DXGGLOBAL::GetSessionData(void)
0x1403a40c7  test    rax, rax
0x1403a40ca  jz      short loc_1403A40D8
0x1403a40cc  lea     rcx, [rax+4A28h]; this
0x1403a40d3  call    ?DisconnectDisplayBroker@DispBrokerClient@@QEAAXXZ; DispBrokerClient::DisconnectDisplayBroker(void)
0x1403a40d8  mov     qword ptr [rsp+180h+Interval], r12
0x1403a40dd  call    cs:__imp_PsGetCurrentProcess
0x1403a40e4  nop     dword ptr [rax+rax+00h]
0x1403a40e9  mov     rcx, rax; Process
0x1403a40ec  call    cs:__imp_PsGetProcessExitStatus
0x1403a40f3  nop     dword ptr [rax+rax+00h]
0x1403a40f8  mov     ebx, eax
0x1403a40fa  call    cs:__imp_PsGetCurrentProcessSessionId
0x1403a4101  nop     dword ptr [rax+rax+00h]
0x1403a4106  mov     rcx, r12
0x1403a4109  xor     r9d, r9d
0x1403a410c  mov     edx, eax
0x1403a410e  mov     r8d, ebx
0x1403a4111  mov     [rsp+180h+var_158], rcx
0x1403a4116  mov     dword ptr [rsp+180h+var_160], r12d
0x1403a411b  lea     ecx, [r9+73h]
0x1403a411f  call    ?DxgkLogCodePointPacketForSession@@YAXW4_DXGK_DIAG_CODE_POINT_TYPE@@_KIIIU_LUID@@@Z; DxgkLogCodePointPacketForSession(_DXGK_DIAG_CODE_POINT_TYPE,unsigned __int64,uint,uint,uint,_LUID)
0x1403a4124  jmp     short loc_1403A4144
0x1403a4126  lea     r8, [rsp+180h+Interval]; Interval
0x1403a412b  mov     qword ptr [rsp+180h+Interval], 0FFFFFFFFFFFE7960h
0x1403a4134  xor     edx, edx; Alertable
0x1403a4136  xor     ecx, ecx; WaitMode
0x1403a4138  call    cs:__imp_KeDelayExecutionThread
0x1403a413f  nop     dword ptr [rax+rax+00h]
0x1403a4144  mov     eax, [rdi+1A8h]
0x1403a414a  test    eax, eax
0x1403a414c  jnz     short loc_1403A4126
0x1403a414e  lea     rcx, [rsp+180h+var_130]; this
0x1403a4153  mov     [rsp+180h+var_12F], r12b
0x1403a4158  call    ?Enter@DXGCRITICALREGION@@QEAAXXZ; DXGCRITICALREGION::Enter(void)
0x1403a415d  test    [rdi+198h], r15b
0x1403a4164  jz      short loc_1403A4179
0x1403a4166  mov     eax, [rdi+198h]
0x1403a416c  shr     eax, 8
0x1403a416f  test    r15b, al
0x1403a4172  jnz     short loc_1403A4179
0x1403a4174  call    DxgkDestroyCsrssProcess
0x1403a4179  lea     r14, [rdi+140h]
0x1403a4180  cmp     [r14], r14
0x1403a4183  jz      loc_1403A43B4
0x1403a4189  test    r13b, r13b
0x1403a418c  jnz     short loc_1403A4199
0x1403a418e  mov     rdx, rsi; struct _DXGK_DISPLAY_SCENARIO_CONTEXT *
0x1403a4191  mov     rcx, rdi; this
0x1403a4194  call    ?ReleaseVidPnSourceOwners@DXGPROCESS@@QEAAXPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; DXGPROCESS::ReleaseVidPnSourceOwners(_DXGK_DISPLAY_SCENARIO_CONTEXT *)
0x1403a4199  mov     rcx, [r14]
0x1403a419c  cmp     rcx, r14
0x1403a419f  jz      loc_1403A43AE
0x1403a41a5  lea     rax, [rcx-18h]
0x1403a41a9  neg     rcx
0x1403a41ac  sbb     rbx, rbx
0x1403a41af  and     rbx, rax
0x1403a41b2  mov     rax, [rbx+10h]
0x1403a41b6  mov     rdx, [rbx+768h]; struct DXGADAPTER *
0x1403a41bd  mov     r15, [rax+10h]
0x1403a41c1  mov     rcx, r15; struct DXGADAPTER *
0x1403a41c4  call    OutputDuplProcessTerminateForWddm
0x1403a41c9  mov     r8d, 2
0x1403a41cf  mov     byte ptr [rsp+180h+var_160], r12b
0x1403a41d4  mov     rdx, rbx
0x1403a41d7  lea     rcx, [rbp+80h+var_E0]
0x1403a41db  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x1403a41e0  cmp     dword ptr [rbx+1D0h], 2
0x1403a41e7  mov     rsi, [r15+0CA8h]
0x1403a41ee  jnz     short loc_1403A4220
0x1403a41f0  mov     r12b, 1
0x1403a41f3  call    cs:__imp_KeEnterCriticalRegion
0x1403a41fa  nop     dword ptr [rax+rax+00h]
0x1403a41ff  lea     rcx, [rsi+30h]
0x1403a4203  xor     edx, edx
0x1403a4205  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1403a420c  nop     dword ptr [rax+rax+00h]
0x1403a4211  mov     rax, gs:188h
0x1403a421a  mov     [rsi+38h], rax
0x1403a421e  jmp     short loc_1403A424B
0x1403a4220  call    cs:__imp_KeEnterCriticalRegion
0x1403a4227  nop     dword ptr [rax+rax+00h]
0x1403a422c  lea     rcx, [rsi+18h]
0x1403a4230  xor     edx, edx
0x1403a4232  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1403a4239  nop     dword ptr [rax+rax+00h]
0x1403a423e  mov     rax, gs:188h
0x1403a4247  mov     [rsi+20h], rax
0x1403a424b  lea     rcx, [rbp+80h+var_E0]; this
0x1403a424f  call    ?AcquireSharedUncheck@COREDEVICEACCESS@@QEAAXPEBD@Z; COREDEVICEACCESS::AcquireSharedUncheck(char const *)
0x1403a4254  cmp     qword ptr [r15+0CA8h], 0
0x1403a425c  jnz     short loc_1403A42AC
0x1403a425e  mov     ecx, 1
0x1403a4263  call    cs:__imp_WdLogSingleEntry0
0x1403a426a  nop     dword ptr [rax+rax+00h]
0x1403a426f  xor     eax, eax
0x1403a4271  lea     r9, aPadapterIsrend; "pAdapter->IsRenderAdapter()"
0x1403a4278  mov     [rsp+180h+var_140], rax
0x1403a427d  mov     ecx, 85Bh
0x1403a4282  mov     [rsp+180h+var_148], rax
0x1403a4287  or      r8d, 0FFFFFFFFh
0x1403a428b  mov     [rsp+180h+var_150], rax
0x1403a4290  mov     edx, 40002h
0x1403a4295  mov     [rsp+180h+var_158], rax
0x1403a429a  mov     [rsp+180h+var_160], rcx
0x1403a429f  mov     cs:WdLogGlobalForLineNumber, ecx
0x1403a42a5  xor     ecx, ecx
0x1403a42a7  call    DxgkLogInternalTriageEvent
0x1403a42ac  mov     rax, [rbx+10h]
0x1403a42b0  mov     rcx, [rax+10h]
0x1403a42b4  mov     eax, [rcx+0C8h]
0x1403a42ba  cmp     eax, 4
0x1403a42bd  jnz     short loc_1403A42EF
0x1403a42bf  lea     rax, [rbx+18h]
0x1403a42c3  neg     rbx
0x1403a42c6  sbb     rcx, rcx
0x1403a42c9  and     rcx, rax
0x1403a42cc  mov     rdx, [rcx]
0x1403a42cf  cmp     [rdx+8], rcx
0x1403a42d3  jnz     loc_1403A43A7
0x1403a42d9  mov     rax, [rcx+8]
0x1403a42dd  cmp     [rax], rcx
0x1403a42e0  jnz     loc_1403A43A7
0x1403a42e6  mov     [rax], rdx
0x1403a42e9  mov     [rdx+8], rax
0x1403a42ed  jmp     short loc_1403A4362
0x1403a42ef  mov     eax, [rbx+260h]
0x1403a42f5  cmp     eax, 1
0x1403a42f8  jnz     short loc_1403A4350
0x1403a42fa  lea     rcx, [rbp+80h+var_E0]; this
0x1403a42fe  call    ?Release@COREDEVICEACCESS@@QEAAXXZ; COREDEVICEACCESS::Release(void)
0x1403a4303  mov     r8b, 1; unsigned __int8
0x1403a4306  lea     rcx, [rsp+180h+Interval]; this
0x1403a430b  mov     rdx, r15; struct DXGADAPTER *
0x1403a430e  call    ??0DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@PEAVDXGADAPTER@@E@Z; DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(DXGADAPTER *,uchar)
0x1403a4313  mov     eax, [r15+0C8h]
0x1403a431a  cmp     eax, 1
0x1403a431d  jnz     short loc_1403A4333
0x1403a431f  xor     r9d, r9d
0x1403a4322  lea     edx, [rax+3]
0x1403a4325  mov     r8d, 0FFFFFFFDh
0x1403a432b  mov     rcx, rbx
0x1403a432e  call    ?FlushScheduler@DXGDEVICE@@QEAAXW4DXGDEVICE_FLUSHSCHEDULER_REASON@@I_N@Z; DXGDEVICE::FlushScheduler(DXGDEVICE_FLUSHSCHEDULER_REASON,uint,bool)
0x1403a4333  lea     rcx, [rsp+180h+Interval]; this
0x1403a4338  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1403a433d  lea     rcx, [rbp+80h+var_E0]; this
0x1403a4341  call    ?AcquireSharedUncheck@COREDEVICEACCESS@@QEAAXPEBD@Z; COREDEVICEACCESS::AcquireSharedUncheck(char const *)
0x1403a4346  lea     rcx, [rsp+180h+Interval]; this
0x1403a434b  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1403a4350  mov     rcx, [r15+0CA8h]; this
0x1403a4357  xor     r8d, r8d; struct COREDEVICEACCESS *
0x1403a435a  mov     rdx, rbx; struct DXGDEVICE *
0x1403a435d  call    ?DestroyDevice@ADAPTER_RENDER@@QEAAXPEAVDXGDEVICE@@PEAVCOREDEVICEACCESS@@@Z; ADAPTER_RENDER::DestroyDevice(DXGDEVICE *,COREDEVICEACCESS *)
0x1403a4362  xor     edx, edx
0x1403a4364  test    r12b, r12b
0x1403a4367  jz      short loc_1403A4376
0x1403a4369  xor     r12d, r12d
0x1403a436c  lea     rcx, [rsi+30h]
0x1403a4370  mov     [rsi+38h], r12
0x1403a4374  jmp     short loc_1403A4381
0x1403a4376  xor     r12d, r12d
0x1403a4379  lea     rcx, [rsi+18h]
0x1403a437d  mov     [rsi+20h], r12
0x1403a4381  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1403a4388  nop     dword ptr [rax+rax+00h]
0x1403a438d  call    cs:__imp_KeLeaveCriticalRegion
0x1403a4394  nop     dword ptr [rax+rax+00h]
0x1403a4399  lea     rcx, [rbp+80h+var_E0]; this
0x1403a439d  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1403a43a2  jmp     loc_1403A4199
0x1403a43a7  mov     ecx, 3
0x1403a43ac  int     29h; Win8: RtlFailFast(ecx)
0x1403a43ae  mov     r15d, 1
0x1403a43b4  call    ?FindRemoteOutputDuplMgr@@YAPEAVOUTPUTDUPL_MGR@@XZ; FindRemoteOutputDuplMgr(void)
0x1403a43b9  test    rax, rax
0x1403a43bc  jz      short loc_1403A43C8
0x1403a43be  mov     rcx, rax; this
0x1403a43c1  call    ?ProcessPendingProcessTerminate@OUTPUTDUPL_MGR@@QEAAXXZ; OUTPUTDUPL_MGR::ProcessPendingProcessTerminate(void)
0x1403a43c6  jmp     short loc_1403A43DE
0x1403a43c8  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1403a43cf  nop     dword ptr [rax+rax+00h]
0x1403a43d4  mov     cs:WdLogGlobalForLineNumber, 0C20h
0x1403a43de  call    OutputDuplProcessTerminateForSession
0x1403a43e3  lea     rbx, [rdi+158h]
0x1403a43ea  cmp     [rbx], rbx
0x1403a43ed  jz      loc_1403A44DA
0x1403a43f3  lea     r15, [rdi+168h]
0x1403a43fa  mov     rcx, r15; this
0x1403a43fd  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1403a4402  mov     rcx, [rbx]
0x1403a4405  cmp     rcx, rbx
0x1403a4408  jz      loc_1403A44CC
0x1403a440e  lea     rax, [rcx-18h]
0x1403a4412  neg     rcx
0x1403a4415  lea     rcx, [rsp+180h+Interval]; this
0x1403a441a  sbb     rsi, rsi
0x1403a441d  and     rsi, rax
0x1403a4420  mov     rax, [rsi+10h]
0x1403a4424  mov     r14, [rax+10h]
0x1403a4428  mov     rdx, r14; struct DXGADAPTER *
0x1403a442b  call    ??0COREACCESS@@QEAA@QEAVDXGADAPTER@@_N@Z; COREACCESS::COREACCESS(DXGADAPTER * const,bool)
0x1403a4430  xor     edx, edx; char *
0x1403a4432  lea     rcx, [rsp+180h+Interval]; this
0x1403a4437  call    ?AcquireShared@COREACCESS@@QEAAXPEBD@Z; COREACCESS::AcquireShared(char const *)
0x1403a443c  cmp     [r14+0CA0h], r12
0x1403a4443  jnz     short loc_1403A4491
0x1403a4445  mov     ecx, 1
0x1403a444a  call    cs:__imp_WdLogSingleEntry0
0x1403a4451  nop     dword ptr [rax+rax+00h]
0x1403a4456  mov     [rsp+180h+var_140], r12
0x1403a445b  lea     r9, aPadapterIsdisp; "pAdapter->IsDisplayAdapter()"
0x1403a4462  mov     [rsp+180h+var_148], r12
0x1403a4467  mov     eax, 8A6h
0x1403a446c  mov     [rsp+180h+var_150], r12
0x1403a4471  or      r8d, 0FFFFFFFFh
0x1403a4475  mov     [rsp+180h+var_158], r12
0x1403a447a  mov     edx, 40002h
0x1403a447f  xor     ecx, ecx
0x1403a4481  mov     [rsp+180h+var_160], rax
0x1403a4486  mov     cs:WdLogGlobalForLineNumber, eax
0x1403a448c  call    DxgkLogInternalTriageEvent
0x1403a4491  mov     eax, [r14+0C8h]
0x1403a4498  cmp     eax, 4
0x1403a449b  jnz     short loc_1403A44AA
0x1403a449d  mov     rdx, rsi; struct DXGCOPYPROTECTION *
0x1403a44a0  mov     rcx, rdi; this
0x1403a44a3  call    ?RemoveCopyProtection@DXGPROCESS@@QEAAXPEAVDXGCOPYPROTECTION@@@Z; DXGPROCESS::RemoveCopyProtection(DXGCOPYPROTECTION *)
0x1403a44a8  jmp     short loc_1403A44BD
0x1403a44aa  mov     r8d, [rsi+30h]; unsigned int
0x1403a44ae  mov     edx, [rsi+34h]; unsigned int
0x1403a44b1  mov     rcx, [r14+0CA0h]; this
0x1403a44b8  call    ?DestroyCopyProtection@ADAPTER_DISPLAY@@QEAAJII@Z; ADAPTER_DISPLAY::DestroyCopyProtection(uint,uint)
0x1403a44bd  lea     rcx, [rsp+180h+Interval]; this
0x1403a44c2  call    ??1COREACCESS@@QEAA@XZ; COREACCESS::~COREACCESS(void)
0x1403a44c7  jmp     loc_1403A4402
0x1403a44cc  mov     rcx, r15; this
0x1403a44cf  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1403a44d4  mov     r15d, 1
0x1403a44da  mov     eax, [rdi+198h]
0x1403a44e0  test    al, al
0x1403a44e2  jns     short loc_1403A4506
0x1403a44e4  mov     rcx, [rdi+258h]; this
0x1403a44eb  test    rcx, rcx
0x1403a44ee  jz      short loc_1403A44F5
0x1403a44f0  call    ?FlushDevicesForTermination@DXGVIRTUALMACHINE@@QEAAXXZ; DXGVIRTUALMACHINE::FlushDevicesForTermination(void)
0x1403a44f5  mov     rcx, [rdi+258h]; this
0x1403a44fc  test    rcx, rcx
0x1403a44ff  jz      short loc_1403A4506
0x1403a4501  call    ?PauseVmBusChannels@DXGVIRTUALMACHINE@@QEAAXXZ; DXGVIRTUALMACHINE::PauseVmBusChannels(void)
0x1403a4506  mov     edx, [rdi+12Ch]
0x1403a450c  mov     ecx, [rdi+128h]
0x1403a4512  cmp     edx, ecx
0x1403a4514  jz      loc_1403A468D
0x1403a451a  mov     esi, r12d
0x1403a451d  test    ecx, ecx
0x1403a451f  jz      loc_1403A468D
0x1403a4525  lea     r14, [rdi+118h]
0x1403a452c  mov     edx, esi
0x1403a452e  mov     rcx, r14
0x1403a4531  call    ?GetEntryType@HMGRTABLE@@QEAA?AW4_HMGRENTRY_TYPE@@I@Z; HMGRTABLE::GetEntryType(uint)
0x1403a4536  sub     eax, 8
0x1403a4539  jz      loc_1403A45EE
0x1403a453f  sub     eax, 1
0x1403a4542  jz      short loc_1403A4573
0x1403a4544  cmp     eax, 5
0x1403a4547  jnz     loc_1403A4676
0x1403a454d  mov     edx, esi; unsigned int
0x1403a454f  mov     rcx, r14; this
0x1403a4552  call    ?GetEntryObject@HMGRTABLE@@QEAAPEAXI@Z; HMGRTABLE::GetEntryObject(uint)
0x1403a4557  mov     edx, esi; unsigned int
0x1403a4559  mov     rcx, r14; this
0x1403a455c  mov     rbx, rax
0x1403a455f  call    ?BuildEntryHandle@HMGRTABLE@@QEAAII@Z; HMGRTABLE::BuildEntryHandle(uint)
0x1403a4564  mov     edx, eax; unsigned int
  ... truncated ...
```
