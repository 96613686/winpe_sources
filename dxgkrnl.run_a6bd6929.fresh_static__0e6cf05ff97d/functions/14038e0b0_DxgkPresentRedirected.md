# DxgkPresentRedirected

- ea: `0x14038e0b0`
- end: `0x14038f1b4`
- name: `DxgkPresentRedirected`
- size: `4356`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `30`
- tags: `broker_com_uri`

## callees

- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x140015a70`
- `0x140015b30`
- `0x1400169f0`
- `0x140018054`
- `0x14001b9c0`
- `0x14001cff0`
- `0x14001d1a0`
- `0x14001d214`
- `0x14001dd44`
- `0x14001eb7c`
- `0x14001f2f0`
- `0x14002dc10`
- `0x1400309f0`
- `0x140030a30`
- `0x140033da4`
- `0x140047990`
- `0x140048a5c`
- `0x140049424`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x14032a5c4`
- `0x14032aaa8`
- `0x14038e0b0`
- `0x14038f1bc`
- `0x14038f62c`
- `0x14038fb34`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038e5fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038e715`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038e5fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038e715`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14038e5ee`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14038e709`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14038e5ee`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14038e709`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038e102`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038e135`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038e102`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038e135`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14038e190`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14038e190`
- `watchdog!WdLogSingleEntry2` at `0x14038e11f`
- `watchdog!WdLogSingleEntry2` at `0x14038e30b`
- `watchdog!WdLogSingleEntry2` at `0x14038e627`
- `watchdog!WdLogSingleEntry2` at `0x14038e742`
- `watchdog!WdLogSingleEntry2` at `0x14038e8f8`
- `watchdog!WdLogSingleEntry2` at `0x14038f12b`
- `watchdog!WdLogSingleEntry2` at `0x14038e11f`
- `watchdog!WdLogSingleEntry2` at `0x14038e30b`
- `watchdog!WdLogSingleEntry2` at `0x14038e627`
- `watchdog!WdLogSingleEntry2` at `0x14038e742`
- `watchdog!WdLogSingleEntry2` at `0x14038e8f8`
- `watchdog!WdLogSingleEntry2` at `0x14038f12b`
- `watchdog!WdLogSingleEntry0` at `0x14038e58d`
- `watchdog!WdLogSingleEntry0` at `0x14038e6a8`
- `watchdog!WdLogSingleEntry0` at `0x14038ed45`
- `watchdog!WdLogSingleEntry0` at `0x14038edb9`
- `watchdog!WdLogSingleEntry0` at `0x14038e58d`
- `watchdog!WdLogSingleEntry0` at `0x14038e6a8`
- `watchdog!WdLogSingleEntry0` at `0x14038ed45`
- `watchdog!WdLogSingleEntry0` at `0x14038edb9`
- `watchdog!WdLogSingleEntry1` at `0x14038e241`
- `watchdog!WdLogSingleEntry1` at `0x14038e2a1`
- `watchdog!WdLogSingleEntry1` at `0x14038e37a`
- `watchdog!WdLogSingleEntry1` at `0x14038eaa6`
- `watchdog!WdLogSingleEntry1` at `0x14038e241`
- `watchdog!WdLogSingleEntry1` at `0x14038e2a1`
- `watchdog!WdLogSingleEntry1` at `0x14038e37a`
- `watchdog!WdLogSingleEntry1` at `0x14038eaa6`

## string_xrefs

- `0x14038eadd`: `Failed to acquire CoreDeviceAccess, returning 0x%I64x`
- `0x14038e257`: `Invalid PresentHistoryToken Mode, returning 0x%I64x`
- `0x14038f16a`: `0x%I64x 0x%I64x encountered exception copying args`
- `0x14038ed75`: `pToken`

## pseudocode

```c
__int64 __fastcall DxgkPresentRedirected(unsigned __int64 Src)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  struct DXGPROCESS *Current; // r15
  __int64 CurrentProcess; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v10; // r8
  const wchar_t *v11; // r9
  unsigned int v12; // ebx
  struct DXGDEVICE *v13; // rsi
  __int64 v14; // r13
  int v15; // edx
  __int64 v16; // rcx
  __int64 v17; // r8
  struct DXGGLOBAL *Global; // rax
  volatile signed __int32 *v19; // r12
  __int64 v20; // rbx
  DXGPUSHLOCK *v21; // rcx
  int v23; // edx
  __int64 v24; // r15
  __int64 v25; // r15
  __int64 v26; // rbx
  int v28; // edx
  __int64 v29; // r15
  __int64 v30; // r15
  int v31; // edx
  __int64 v32; // rcx
  __int64 v33; // r8
  int v34; // r15d
  int v35; // edx
  __int64 v36; // rcx
  __int64 v37; // r8
  bool v38; // zf
  int v39; // eax
  unsigned int v40; // r14d
  ADAPTER_RENDER **v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // r8
  struct DXGDEVICE *v44; // rcx
  ADAPTER_RENDER **v45; // rcx
  int v46; // edx
  __int64 v47; // rcx
  __int64 v48; // r8
  ADAPTER_RENDER **v49; // rcx
  int v50; // edx
  unsigned int v51; // [rsp+60h] [rbp-5F8h] BYREF
  __int64 v52; // [rsp+68h] [rbp-5F0h]
  _DWORD *v53; // [rsp+70h] [rbp-5E8h]
  int *v54; // [rsp+78h] [rbp-5E0h]
  char v55; // [rsp+80h] [rbp-5D8h]
  int v56; // [rsp+88h] [rbp-5D0h] BYREF
  unsigned int v57; // [rsp+8Ch] [rbp-5CCh]
  struct DXGDEVICE *v58[2]; // [rsp+90h] [rbp-5C8h] BYREF
  struct DXGDEVICE *v59; // [rsp+A0h] [rbp-5B8h] BYREF
  char v60[8]; // [rsp+A8h] [rbp-5B0h] BYREF
  char v61; // [rsp+B0h] [rbp-5A8h]
  char v62[8]; // [rsp+B8h] [rbp-5A0h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-598h]
  char v64; // [rsp+C8h] [rbp-590h]
  unsigned __int64 v65; // [rsp+D0h] [rbp-588h]
  __int128 v66; // [rsp+D8h] [rbp-580h] BYREF
  __int128 v67; // [rsp+E8h] [rbp-570h]
  struct DXGDEVICE *v68; // [rsp+F8h] [rbp-560h]
  int v69; // [rsp+100h] [rbp-558h] BYREF
  char *v70; // [rsp+108h] [rbp-550h]
  char *v71; // [rsp+110h] [rbp-548h]
  _BYTE *v72; // [rsp+118h] [rbp-540h]
  _BYTE v73[160]; // [rsp+120h] [rbp-538h] BYREF
  _BYTE v74[1120]; // [rsp+1C0h] [rbp-498h] BYREF

  v56 = -1073741823;
  Current = DXGPROCESS::GetCurrent();
  v58[0] = Current;
  if ( !Current )
  {
    CurrentProcess = PsGetCurrentProcess(v3, v2);
    WdLogSingleEntry2(2, -1073741811, CurrentProcess);
    WdLogGlobalForLineNumber = 1073;
    v8 = PsGetCurrentProcess(v7, v6);
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Presenting from unexpected process 0x%I64x 0x%I64x",
      -1073741811,
      v8,
      0,
      0,
      0);
    return 3221225485LL;
  }
  memset(v74, 0, sizeof(v74));
  if ( (unsigned __int8)PsGetCurrentThreadPreviousMode() == 1 )
  {
    RtlCopyFromUser(v74, (void *)Src, 0x460u);
    Src = (unsigned __int64)v74;
  }
  v65 = Src;
  v52 = 0;
  v51 = 2147;
  v54 = &v56;
  v55 = 1;
  v53 = (_DWORD *)(Src & -(__int64)(bTracingEnabled != 0));
  if ( (qword_1401604F0 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(Src & -(__int64)(bTracingEnabled != 0), EventProfilerEnter, v10, 2147);
  DXGETWPROFILER_BASE::PushProfilerEntry(&v51, 2147);
  if ( *(_DWORD *)(Src + 16) != 9 )
  {
    WdLogSingleEntry1(2, -1073741811);
    WdLogGlobalForLineNumber = 1105;
    v11 = L"Invalid PresentHistoryToken Mode, returning 0x%I64x";
LABEL_11:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v11, -1073741811, 0, 0, 0, 0);
LABEL_57:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v51);
    if ( v55 )
    {
      if ( v53 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
        McTemplateK0qqxxqq_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v31,
          v33,
          *v53,
          v53[14],
          *((_QWORD *)v53 + 10),
          *((_QWORD *)v53 + 11),
          v53[274],
          *v54);
    }
    else if ( v53 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
    {
      McTemplateK0qpqqqqpp_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v31,
        v33,
        *v53,
        *((_QWORD *)v53 + 1),
        v53[4],
        v53[21],
        v53[22],
        *v54,
        v53[5],
        v53[6]);
    }
    if ( (qword_1401604F0 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v32, EventProfilerExit, v33, v51);
    return 3221225485LL;
  }
  if ( *(_DWORD *)(Src + 1096) )
  {
    WdLogSingleEntry1(2, -1073741811);
    WdLogGlobalForLineNumber = 1112;
    v11 = L"Reserved bits should not be set, returning 0x%I64x";
    goto LABEL_11;
  }
  v12 = *(_DWORD *)Src;
  v57 = *(_DWORD *)Src;
  v58[0] = 0;
  DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)&v59, *(_DWORD *)(Src + 4), Current, v58);
  v13 = v58[0];
  if ( !v58[0] )
  {
    WdLogSingleEntry2(2, *(unsigned int *)(Src + 4), -1073741811);
    WdLogGlobalForLineNumber = 1129;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid hDevice (0x%I64x) specified, returning 0x%I64x",
      *(unsigned int *)(Src + 4),
      -1073741811,
      0,
      0,
      0);
LABEL_56:
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v59);
    goto LABEL_57;
  }
  v14 = *(_QWORD *)(*((_QWORD *)v58[0] + 2) + 16LL);
  if ( (*(_DWORD *)(v14 + 3104) & 8) != 0 )
  {
    WdLogSingleEntry1(2, *(unsigned int *)(Src + 4));
    WdLogGlobalForLineNumber = 1137;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Present is not supported on MCDM adapter device 0x%I64x",
      *(unsigned int *)(Src + 4),
      0,
      0,
      0,
      0);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v59);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v51);
    if ( v55 )
    {
      if ( v53 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
        McTemplateK0qqxxqq_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v15,
          v17,
          *v53,
          v53[14],
          *((_QWORD *)v53 + 10),
          *((_QWORD *)v53 + 11),
          v53[274],
          *v54);
    }
    else if ( v53 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
    {
      McTemplateK0qpqqqqpp_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v15,
        v17,
        *v53,
        *((_QWORD *)v53 + 1),
        v53[4],
        v53[21],
        v53[22],
        *v54,
        v53[5],
        v53[6]);
    }
    if ( (qword_1401604F0 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v16, EventProfilerExit, v17, v51);
    return 3221225485LL;
  }
  Global = DXGGLOBAL::GetGlobal();
  DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v60, Global, 0);
  DXGSYNCOBJECTLOCK::AcquireShared((DXGSYNCOBJECTLOCK *)v60);
  v19 = (volatile signed __int32 *)((char *)Current + 248);
  v58[0] = (struct DXGDEVICE *)((v12 >> 6) & 0xFFFFFF);
  v20 = 2 * (__int64)v58[0];
  v21 = (struct DXGPROCESS *)((char *)Current + 248);
  if ( *(int *)(v14 + 3132) < 2000 )
  {
    DXGPUSHLOCK::AcquireShared(v21);
    if ( LODWORD(v58[0]) < *((_DWORD *)Current + 74)
      && (v28 = *(_DWORD *)(*((_QWORD *)Current + 35) + 8 * v20 + 8),
          ((v57 >> 25) & 0x60) == (*(_BYTE *)(*((_QWORD *)Current + 35) + 8 * v20 + 8) & 0x60))
      && (v28 & 0x2000) == 0
      && (v28 & 0x1F) != 0 )
    {
      v30 = *((_QWORD *)Current + 35);
      if ( (*(_BYTE *)(v30 + 8 * v20 + 8) & 0x1F) == 8 )
      {
        v29 = *(_QWORD *)(v30 + 8 * v20);
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v29 = 0;
      }
    }
    else
    {
      v29 = 0;
    }
    _InterlockedAdd(v19 + 4, 0xFFFFFFFF);
    ExReleasePushLockSharedEx(v19, 0);
    KeLeaveCriticalRegion();
    if ( !v29 )
    {
      v26 = v57;
      WdLogSingleEntry2(2, v57, -1073741811);
      WdLogGlobalForLineNumber = 1166;
      goto LABEL_55;
    }
  }
  else
  {
    DXGPUSHLOCK::AcquireShared(v21);
    if ( LODWORD(v58[0]) < *((_DWORD *)Current + 74)
      && (v23 = *(_DWORD *)(*((_QWORD *)Current + 35) + 8 * v20 + 8),
          ((v57 >> 25) & 0x60) == (*(_BYTE *)(*((_QWORD *)Current + 35) + 8 * v20 + 8) & 0x60))
      && (v23 & 0x2000) == 0
      && (v23 & 0x1F) != 0 )
    {
      v25 = *((_QWORD *)Current + 35);
      if ( (*(_BYTE *)(v25 + 8 * v20 + 8) & 0x1F) == 0xB )
      {
        v24 = *(_QWORD *)(v25 + 8 * v20);
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v24 = 0;
      }
    }
    else
    {
      v24 = 0;
    }
    _InterlockedAdd(v19 + 4, 0xFFFFFFFF);
    ExReleasePushLockSharedEx(v19, 0);
    KeLeaveCriticalRegion();
    if ( !v24 )
    {
      v26 = v57;
      WdLogSingleEntry2(2, v57, -1073741811);
      WdLogGlobalForLineNumber = 1156;
LABEL_55:
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Invalid hSyncObj (0x%I64x) specified, returning 0x%I64x",
        v26,
        -1073741811,
        0,
        0,
        0);
      DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v60);
      goto LABEL_56;
    }
  }
  _InterlockedIncrement64((volatile signed __int64 *)v13 + 8);
  v58[0] = v13;
  DXGSYNCOBJECTLOCK::Release((DXGSYNCOBJECTLOCK *)v60);
  v63 = v14;
  v64 = 0;
  DXGADAPTERSTOPRESETLOCKSHARED::Acquire((DXGADAPTERSTOPRESETLOCKSHARED *)v62);
  if ( *(_DWORD *)(v14 + 200) != 1 )
  {
    v34 = -1073741823;
    WdLogSingleEntry2(2, v14, -1073741823);
    WdLogGlobalForLineNumber = 1186;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"DXGADAPTER: 0x%I64x stopped, returning 0x%I64x",
      v14,
      -1073741823,
      0,
      0,
      0);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v62);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v58);
    DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v60);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v59);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v51);
    v38 = v55 == 0;
LABEL_100:
    if ( v38 )
    {
      if ( v53 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
        McTemplateK0qpqqqqpp_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v35,
          v37,
          *v53,
          *((_QWORD *)v53 + 1),
          v53[4],
          v53[21],
          v53[22],
          *v54,
          v53[5],
          v53[6]);
    }
    else if ( v53 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    {
      McTemplateK0qqxxqq_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v35,
        v37,
        *v53,
        v53[14],
        *((_QWORD *)v53 + 10),
        *((_QWORD *)v53 + 11),
        v53[274],
        *v54);
    }
    if ( (qword_1401604F0 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v36, EventProfilerExit, v37, v51);
    return (unsigned int)v34;
  }
  COREDEVICEACCESS::COREDEVICEACCESS(v73, v13, 2);
  v39 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v73, 0);
  v56 = v39;
  if ( v39 < 0 )
  {
    WdLogSingleEntry1(2, v39);
    WdLogGlobalForLineNumber = 1194;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to acquire CoreDeviceAccess, returning 0x%I64x",
      v56,
      0,
      0,
      0,
      0);
    v40 = v56;
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v73);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v62);
    if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v13 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      ADAPTER_RENDER::DestroyDeviceNoLocks(*((ADAPTER_RENDER **)v13 + 2), v13);
    if ( v61 )
      DXGSYNCOBJECTLOCK::Release((DXGSYNCOBJECTLOCK *)v60);
    v41 = (ADAPTER_RENDER **)v59;
    if ( v59 && _InterlockedExchangeAdd64((volatile signed __int64 *)v59 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      ADAPTER_RENDER::DestroyDeviceNoLocks(v41[2], (struct DXGDEVICE *)v41);
LABEL_131:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v51);
    if ( v55 )
    {
      if ( v53 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
        McTemplateK0qqxxqq_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v50,
          v43,
          *v53,
          v53[14],
          *((_QWORD *)v53 + 10),
          *((_QWORD *)v53 + 11),
          v53[274],
          *v54);
    }
    else if ( v53 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
    {
      McTemplateK0qpqqqqpp_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v50,
        v43,
        *v53,
        *((_QWORD *)v53 + 1),
        v53[4],
        v53[21],
        v53[22],
        *v54,
        v53[5],
        v53[6]);
    }
    if ( (qword_1401604F0 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v42, EventProfilerExit, v43, v51);
    return v40;
  }
  v34 = SubmitPresentHistoryTokenPreparation(
          (struct DXGADAPTERSTOPRESETLOCKSHARED *)v62,
          (struct COREDEVICEACCESS *)v73,
          (struct DXGADAPTER *)v14,
          (struct _D3DKMT_PRESENTHISTORYTOKEN *)(Src + 16),
          0,
          0);
  v56 = v34;
  if ( v34 < 0 )
  {
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v73);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v62);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v58);
    DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v60);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v59);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v51);
    v38 = v55 == 0;
    goto LABEL_100;
  }
  v69 = -1073741823;
  v70 = (char *)(Src + 16);
  v71 = v62;
  v72 = v73;
  if ( Src == -16 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 122;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pToken", 122, 0, 0, 0, 0);
  }
  CVidSchSubmitData::CVidSchSubmitData((CVidSchSubmitData *)v58, *(struct ADAPTER_RENDER **)(v14 + 3256), 1);
  v44 = v58[0];
  if ( v58[0] )
  {
    *(_DWORD *)v58[0] = *(_DWORD *)v58[0] & 0xFFFCFEDF | 0x10120;
    *((_QWORD *)v44 + 59) = *(_QWORD *)(Src + 8);
    v66 = 0;
    v67 = 0;
    v68 = 0;
    LODWORD(v66) = v57;
    *(_QWORD *)((char *)&v66 + 4) = *(_QWORD *)(Src + 1100);
    *(_QWORD *)&v67 = *(_QWORD *)(Src + 1112);
    *((_QWORD *)&v67 + 1) = v14;
    v68 = v13;
    v40 = SubmitPresentHistoryToken(
            (const struct _D3DKMT_PRESENTHISTORYTOKEN *)(Src + 16),
            (struct COREDEVICEACCESS *)v73,
            (struct DXGADAPTERSTOPRESETLOCKSHARED *)v62,
            0,
            1,
            0,
            0,
            v44,
            0,
            (struct _PRESENT_REDIRECTED_PARAMS *)&v66,
            0);
    v56 = v40;
    v69 = v40;
    CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v58);
    TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD((TOKEN_BINDING_GUARD *)&v69);
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v73);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v62);
    if ( v13 && _InterlockedExchangeAdd64((volatile signed __int64 *)v13 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      ADAPTER_RENDER::DestroyDeviceNoLocks(*((ADAPTER_RENDER **)v13 + 2), v13);
    if ( v61 )
      DXGSYNCOBJECTLOCK::Release((DXGSYNCOBJECTLOCK *)v60);
    v49 = (ADAPTER_RENDER **)v59;
    if ( v59 && _InterlockedExchangeAdd64((volatile signed __int64 *)v59 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      ADAPTER_RENDER::DestroyDeviceNoLocks(v49[2], (struct DXGDEVICE *)v49);
    goto LABEL_131;
  }
  WdLogSingleEntry0(6);
  WdLogGlobalForLineNumber = 1218;
  DxgkLogInternalTriageEvent(0, 262145, -1, (unsigned int)L"Failed to allocate VidSchSubmitData", 1218, 0, 0, 0, 0);
  CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v58);
  TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD((TOKEN_BINDING_GUARD *)&v69);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v73);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v62);
  if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v13 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    ADAPTER_RENDER::DestroyDeviceNoLocks(*((ADAPTER_RENDER **)v13 + 2), v13);
  if ( v61 )
    DXGSYNCOBJECTLOCK::Release((DXGSYNCOBJECTLOCK *)v60);
  v45 = (ADAPTER_RENDER **)v59;
  if ( v59 && _InterlockedExchangeAdd64((volatile signed __int64 *)v59 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    ADAPTER_RENDER::DestroyDeviceNoLocks(v45[2], (struct DXGDEVICE *)v45);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v51);
  if ( v55 )
  {
    if ( v53 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
      McTemplateK0qqxxqq_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v46,
        v48,
        *v53,
        v53[14],
        *((_QWORD *)v53 + 10),
        *((_QWORD *)v53 + 11),
        v53[274],
        *v54);
  }
  else if ( v53 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
  {
    McTemplateK0qpqqqqpp_EtwWriteTransfer(
      (unsigned int)&DxgkControlGuid_Context,
      v46,
      v48,
      *v53,
      *((_QWORD *)v53 + 1),
      v53[4],
      v53[21],
      v53[22],
      *v54,
      v53[5],
      v53[6]);
  }
  if ( (qword_1401604F0 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v47, EventProfilerExit, v48, v51);
  return 3221225495LL;
}

```

## disassembly

```asm
0x14038e0b0  mov     [rsp+arg_8], rbx
0x14038e0b5  mov     [rsp+arg_10], rsi
0x14038e0ba  push    rdi
0x14038e0bb  push    r12
0x14038e0bd  push    r13
0x14038e0bf  push    r14
0x14038e0c1  push    r15
0x14038e0c3  sub     rsp, 630h
0x14038e0ca  mov     rax, cs:__security_cookie
0x14038e0d1  xor     rax, rsp
0x14038e0d4  mov     [rsp+658h+var_38], rax
0x14038e0dc  mov     r14, rcx
0x14038e0df  mov     [rsp+658h+var_5D0], 0C0000001h
0x14038e0ea  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14038e0ef  mov     r15, rax
0x14038e0f2  mov     [rsp+658h+var_5C8], rax
0x14038e0fa  xor     r12d, r12d
0x14038e0fd  test    rax, rax
0x14038e100  jnz     short loc_14038E178
0x14038e102  call    cs:__imp_PsGetCurrentProcess
0x14038e109  nop     dword ptr [rax+rax+00h]
0x14038e10e  mov     r8, rax
0x14038e111  mov     rsi, 0FFFFFFFFC000000Dh
0x14038e118  mov     rdx, rsi
0x14038e11b  lea     ecx, [r15+2]
0x14038e11f  call    cs:__imp_WdLogSingleEntry2
0x14038e126  nop     dword ptr [rax+rax+00h]
0x14038e12b  mov     cs:WdLogGlobalForLineNumber, 431h
0x14038e135  call    cs:__imp_PsGetCurrentProcess
0x14038e13c  nop     dword ptr [rax+rax+00h]
0x14038e141  mov     [rsp+658h+var_618], r12
0x14038e146  mov     [rsp+658h+var_620], r12
0x14038e14b  mov     [rsp+658h+var_628], r12
0x14038e150  mov     [rsp+658h+var_630], rax
0x14038e155  mov     [rsp+658h+var_638], rsi
0x14038e15a  lea     r9, aPresentingFrom; "Presenting from unexpected process 0x%I"...
0x14038e161  or      r8d, 0FFFFFFFFh
0x14038e165  mov     edx, 40000h
0x14038e16a  xor     ecx, ecx
0x14038e16c  call    DxgkLogInternalTriageEvent
0x14038e171  mov     eax, esi
0x14038e173  jmp     loc_14038F186
0x14038e178  mov     ebx, 460h
0x14038e17d  mov     r8d, ebx; Size
0x14038e180  xor     edx, edx; Val
0x14038e182  lea     rcx, [rsp+658h+var_498]; void *
0x14038e18a  call    memset
0x14038e18f  nop
0x14038e190  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x14038e197  nop     dword ptr [rax+rax+00h]
0x14038e19c  cmp     al, 1
0x14038e19e  jnz     short loc_14038E1BB
0x14038e1a0  mov     r8d, ebx; Size
0x14038e1a3  mov     rdx, r14; Src
0x14038e1a6  lea     rcx, [rsp+658h+var_498]; void *
0x14038e1ae  call    RtlCopyFromUser
0x14038e1b3  lea     r14, [rsp+658h+var_498]
0x14038e1bb  mov     [rsp+658h+var_588], r14
0x14038e1c3  mov     al, cs:bTracingEnabled
0x14038e1c9  neg     al
0x14038e1cb  sbb     rcx, rcx
0x14038e1ce  and     rcx, r14
0x14038e1d1  mov     [rsp+658h+var_5F0], r12
0x14038e1d6  mov     ebx, 863h
0x14038e1db  mov     [rsp+658h+var_5F8], ebx
0x14038e1df  lea     rax, [rsp+658h+var_5D0]
0x14038e1e7  mov     [rsp+658h+var_5E0], rax
0x14038e1ec  mov     [rsp+658h+var_5D8], 1
0x14038e1f4  mov     [rsp+658h+var_5E8], rcx
0x14038e1f9  mov     rax, cs:qword_1401604F0
0x14038e200  mov     edi, 2
0x14038e205  test    dil, al
0x14038e208  jz      short loc_14038E222
0x14038e20a  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14038e211  jz      short loc_14038E222
0x14038e213  mov     r9d, ebx
0x14038e216  lea     rdx, EventProfilerEnter
0x14038e21d  call    McTemplateK0q_EtwWriteTransfer
0x14038e222  mov     edx, ebx
0x14038e224  lea     rcx, [rsp+658h+var_5F8]
0x14038e229  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x14038e22e  cmp     dword ptr [r14+10h], 9
0x14038e233  jz      short loc_14038E28C
0x14038e235  mov     rsi, 0FFFFFFFFC000000Dh
0x14038e23c  mov     rdx, rsi
0x14038e23f  mov     ecx, edi
0x14038e241  call    cs:__imp_WdLogSingleEntry1
0x14038e248  nop     dword ptr [rax+rax+00h]
0x14038e24d  mov     cs:WdLogGlobalForLineNumber, 451h
0x14038e257  lea     r9, aInvalidPresent_1; "Invalid PresentHistoryToken Mode, retur"...
0x14038e25e  mov     [rsp+658h+var_618], r12
0x14038e263  mov     [rsp+658h+var_620], r12
0x14038e268  mov     [rsp+658h+var_628], r12
0x14038e26d  mov     [rsp+658h+var_630], r12
0x14038e272  mov     [rsp+658h+var_638], rsi
0x14038e277  or      r8d, 0FFFFFFFFh
0x14038e27b  mov     edx, 40000h
0x14038e280  xor     ecx, ecx
0x14038e282  call    DxgkLogInternalTriageEvent
0x14038e287  jmp     loc_14038E7A2
0x14038e28c  cmp     [r14+448h], r12d
0x14038e293  jz      short loc_14038E2C0
0x14038e295  mov     rsi, 0FFFFFFFFC000000Dh
0x14038e29c  mov     rdx, rsi
0x14038e29f  mov     ecx, edi
0x14038e2a1  call    cs:__imp_WdLogSingleEntry1
0x14038e2a8  nop     dword ptr [rax+rax+00h]
0x14038e2ad  mov     cs:WdLogGlobalForLineNumber, 458h
0x14038e2b7  lea     r9, aReservedBitsSh; "Reserved bits should not be set, return"...
0x14038e2be  jmp     short loc_14038E25E
0x14038e2c0  mov     ebx, [r14]
0x14038e2c3  mov     [rsp+658h+var_5CC], ebx
0x14038e2ca  mov     [rsp+658h+var_5C8], r12
0x14038e2d2  lea     r9, [rsp+658h+var_5C8]; struct DXGDEVICE **
0x14038e2da  mov     r8, r15; struct DXGPROCESS *
0x14038e2dd  mov     edx, [r14+4]; unsigned int
0x14038e2e1  lea     rcx, [rsp+658h+var_5B8]; this
0x14038e2e9  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x14038e2ee  mov     rsi, [rsp+658h+var_5C8]
0x14038e2f6  test    rsi, rsi
0x14038e2f9  jnz     short loc_14038E35A
0x14038e2fb  mov     edx, [r14+4]
0x14038e2ff  mov     rsi, 0FFFFFFFFC000000Dh
0x14038e306  mov     r8, rsi
0x14038e309  mov     ecx, edi
0x14038e30b  call    cs:__imp_WdLogSingleEntry2
0x14038e312  nop     dword ptr [rax+rax+00h]
0x14038e317  mov     cs:WdLogGlobalForLineNumber, 469h
0x14038e321  mov     eax, [r14+4]
0x14038e325  mov     [rsp+658h+var_618], r12
0x14038e32a  mov     [rsp+658h+var_620], r12
0x14038e32f  mov     [rsp+658h+var_628], r12
0x14038e334  mov     [rsp+658h+var_630], rsi
0x14038e339  mov     [rsp+658h+var_638], rax
0x14038e33e  lea     r9, aInvalidHdevice_2; "Invalid hDevice (0x%I64x) specified, re"...
0x14038e345  or      r8d, 0FFFFFFFFh
0x14038e349  mov     edx, 40000h
0x14038e34e  xor     ecx, ecx
0x14038e350  call    DxgkLogInternalTriageEvent
0x14038e355  jmp     loc_14038E795
0x14038e35a  mov     rax, [rsi+10h]
0x14038e35e  mov     r13, [rax+10h]
0x14038e362  mov     eax, [r13+0C20h]
0x14038e369  shr     eax, 3
0x14038e36c  test    al, 1
0x14038e36e  jz      loc_14038E4D0
0x14038e374  mov     edx, [r14+4]
0x14038e378  mov     ecx, edi
0x14038e37a  call    cs:__imp_WdLogSingleEntry1
0x14038e381  nop     dword ptr [rax+rax+00h]
0x14038e386  mov     cs:WdLogGlobalForLineNumber, 471h
0x14038e390  mov     eax, [r14+4]
0x14038e394  mov     [rsp+658h+var_618], r12
0x14038e399  mov     [rsp+658h+var_620], r12
0x14038e39e  mov     [rsp+658h+var_628], r12
0x14038e3a3  mov     [rsp+658h+var_630], r12
0x14038e3a8  mov     [rsp+658h+var_638], rax
0x14038e3ad  lea     r9, aPresentIsNotSu; "Present is not supported on MCDM adapte"...
0x14038e3b4  or      r8d, 0FFFFFFFFh
0x14038e3b8  mov     edx, 40000h
0x14038e3bd  xor     ecx, ecx
0x14038e3bf  call    DxgkLogInternalTriageEvent
0x14038e3c4  lea     rcx, [rsp+658h+var_5B8]; this
0x14038e3cc  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x14038e3d1  lea     rcx, [rsp+658h+var_5F8]; this
0x14038e3d6  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14038e3db  mov     r9, [rsp+658h+var_5E8]
0x14038e3e0  cmp     [rsp+658h+var_5D8], r12b
0x14038e3e8  jz      short loc_14038E441
0x14038e3ea  test    r9, r9
0x14038e3ed  jz      loc_14038E49E
0x14038e3f3  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x14038e3fa  jz      loc_14038E49E
0x14038e400  mov     rax, [rsp+658h+var_5E0]
0x14038e405  mov     ecx, [rax]
0x14038e407  mov     dword ptr [rsp+658h+var_618], ecx
0x14038e40b  mov     eax, [r9+448h]
0x14038e412  mov     dword ptr [rsp+658h+var_620], eax
0x14038e416  mov     rax, [r9+58h]
0x14038e41a  mov     [rsp+658h+var_628], rax
0x14038e41f  mov     rax, [r9+50h]
0x14038e423  mov     [rsp+658h+var_630], rax
0x14038e428  mov     eax, [r9+38h]
0x14038e42c  mov     dword ptr [rsp+658h+var_638], eax
0x14038e430  mov     r9d, [r9]
0x14038e433  lea     rcx, DxgkControlGuid_Context
0x14038e43a  call    McTemplateK0qqxxqq_EtwWriteTransfer
0x14038e43f  jmp     short loc_14038E49E
0x14038e441  test    r9, r9
0x14038e444  jz      short loc_14038E49E
0x14038e446  mov     rax, cs:Microsoft_Windows_DxgKrnlEnableBits
0x14038e44d  test    al, al
0x14038e44f  jns     short loc_14038E49E
0x14038e451  mov     eax, [r9+18h]
0x14038e455  mov     ecx, [r9+14h]
0x14038e459  mov     [rsp+658h+var_608], rax
0x14038e45e  mov     [rsp+658h+var_610], rcx
0x14038e463  mov     rax, [rsp+658h+var_5E0]
0x14038e468  mov     ecx, [rax]
0x14038e46a  mov     dword ptr [rsp+658h+var_618], ecx
0x14038e46e  mov     eax, [r9+58h]
0x14038e472  mov     dword ptr [rsp+658h+var_620], eax
0x14038e476  mov     eax, [r9+54h]
0x14038e47a  mov     dword ptr [rsp+658h+var_628], eax
0x14038e47e  mov     eax, [r9+10h]
0x14038e482  mov     dword ptr [rsp+658h+var_630], eax
0x14038e486  mov     rax, [r9+8]
0x14038e48a  mov     [rsp+658h+var_638], rax
0x14038e48f  mov     r9d, [r9]
0x14038e492  lea     rcx, DxgkControlGuid_Context
0x14038e499  call    McTemplateK0qpqqqqpp_EtwWriteTransfer
0x14038e49e  mov     rax, cs:qword_1401604F0
0x14038e4a5  test    dil, al
0x14038e4a8  jz      short loc_14038E4C4
0x14038e4aa  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14038e4b1  jz      short loc_14038E4C4
0x14038e4b3  mov     r9d, [rsp+658h+var_5F8]
0x14038e4b8  lea     rdx, EventProfilerExit
0x14038e4bf  call    McTemplateK0q_EtwWriteTransfer
0x14038e4c4  mov     rsi, 0FFFFFFFFC000000Dh
0x14038e4cb  jmp     loc_14038E171
0x14038e4d0  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14038e4d5  mov     rdx, rax; struct DXGGLOBAL *
0x14038e4d8  xor     r8d, r8d; bool
0x14038e4db  lea     rcx, [rsp+658h+var_5B0]; this
0x14038e4e3  call    ??0DXGSYNCOBJECTLOCK@@QEAA@QEAVDXGGLOBAL@@_N@Z; DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK(DXGGLOBAL * const,bool)
0x14038e4e8  lea     rcx, [rsp+658h+var_5B0]; this
0x14038e4f0  call    ?AcquireShared@DXGSYNCOBJECTLOCK@@QEAAXXZ; DXGSYNCOBJECTLOCK::AcquireShared(void)
0x14038e4f5  lea     r12, [r15+0F8h]
0x14038e4fc  mov     eax, ebx
0x14038e4fe  shr     eax, 6
0x14038e501  and     eax, 0FFFFFFh
0x14038e506  mov     [rsp+658h+var_5C8], rax
0x14038e50e  mov     ebx, eax
0x14038e510  add     rbx, rbx
0x14038e513  mov     rcx, r12; this
0x14038e516  cmp     dword ptr [r13+0C3Ch], 7D0h
0x14038e521  jl      loc_14038E642
0x14038e527  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x14038e52c  mov     rax, [rsp+658h+var_5C8]
0x14038e534  cmp     eax, [r15+128h]
0x14038e53b  jb      short loc_14038E541
0x14038e53d  xor     al, al
0x14038e53f  jmp     short loc_14038E56F
0x14038e541  mov     rax, [r15+118h]
0x14038e548  mov     edx, [rax+rbx*8+8]
0x14038e54c  mov     ecx, [rsp+658h+var_5CC]
0x14038e553  shr     ecx, 19h
0x14038e556  and     ecx, 60h
0x14038e559  mov     eax, edx
0x14038e55b  and     eax, 60h
0x14038e55e  cmp     cl, al
0x14038e560  jnz     short loc_14038E53D
0x14038e562  bt      edx, 0Dh
0x14038e566  jb      short loc_14038E53D
0x14038e568  test    dl, 1Fh
0x14038e56b  jz      short loc_14038E53D
0x14038e56d  mov     al, 1
0x14038e56f  test    al, al
0x14038e571  jnz     short loc_14038E578
0x14038e573  xor     r15d, r15d
0x14038e576  jmp     short loc_14038E5DF
0x14038e578  mov     r15, [r15+118h]
0x14038e57f  mov     eax, [r15+rbx*8+8]
0x14038e584  and     eax, 1Fh
0x14038e587  cmp     al, 0Bh
0x14038e589  jz      short loc_14038E5DB
0x14038e58b  mov     ecx, edi
0x14038e58d  call    cs:__imp_WdLogSingleEntry0
0x14038e594  nop     dword ptr [rax+rax+00h]
0x14038e599  mov     eax, 13Eh
0x14038e59e  mov     cs:WdLogGlobalForLineNumber, eax
0x14038e5a4  xor     ebx, ebx
0x14038e5a6  mov     [rsp+658h+var_618], rbx
0x14038e5ab  mov     [rsp+658h+var_620], rbx
0x14038e5b0  mov     [rsp+658h+var_628], rbx
0x14038e5b5  mov     [rsp+658h+var_630], rbx
0x14038e5ba  mov     [rsp+658h+var_638], rax
0x14038e5bf  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x14038e5c6  or      r8d, 0FFFFFFFFh
0x14038e5ca  mov     edx, 40000h
0x14038e5cf  xor     ecx, ecx
0x14038e5d1  call    DxgkLogInternalTriageEvent
0x14038e5d6  mov     r15d, ebx
0x14038e5d9  jmp     short loc_14038E5DF
0x14038e5db  mov     r15, [r15+rbx*8]
0x14038e5df  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14038e5e3  lock add [r12+10h], ebx
0x14038e5e9  xor     edx, edx
0x14038e5eb  mov     rcx, r12
0x14038e5ee  call    cs:__imp_ExReleasePushLockSharedEx
0x14038e5f5  nop     dword ptr [rax+rax+00h]
0x14038e5fa  call    cs:__imp_KeLeaveCriticalRegion
0x14038e601  nop     dword ptr [rax+rax+00h]
0x14038e606  xor     r12d, r12d
0x14038e609  test    r15, r15
0x14038e60c  jnz     loc_14038E8A2
0x14038e612  mov     ebx, [rsp+658h+var_5CC]
0x14038e619  mov     rsi, 0FFFFFFFFC000000Dh
0x14038e620  mov     r8, rsi
  ... truncated ...
```
