# DxgkPresentRedirected

- ea: `0x14038efe0`
- end: `0x1403900ac`
- name: `DxgkPresentRedirected`
- size: `4300`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `30`
- tags: `broker_com_uri`

## callees

- `0x140012380`
- `0x140012b14`
- `0x140013860`
- `0x1400158b0`
- `0x140015970`
- `0x140016830`
- `0x140017fb8`
- `0x14001b890`
- `0x14001cec0`
- `0x14001d070`
- `0x14001d0e4`
- `0x14001db74`
- `0x14001e9ac`
- `0x14001f120`
- `0x14002da40`
- `0x140030820`
- `0x140030860`
- `0x140033bd4`
- `0x140047790`
- `0x14004885c`
- `0x140049224`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a0540`
- `0x140323854`
- `0x140323d38`
- `0x14038efe0`
- `0x1403900b4`
- `0x140390524`
- `0x140390a24`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038f52a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038f645`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038f52a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038f645`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14038f51e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14038f639`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14038f51e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14038f639`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038f032`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038f065`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038f032`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038f065`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14038f0c0`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14038f0c0`
- `watchdog!WdLogSingleEntry2` at `0x14038f04f`
- `watchdog!WdLogSingleEntry2` at `0x14038f23b`
- `watchdog!WdLogSingleEntry2` at `0x14038f557`
- `watchdog!WdLogSingleEntry2` at `0x14038f672`
- `watchdog!WdLogSingleEntry2` at `0x14038f828`
- `watchdog!WdLogSingleEntry2` at `0x140390023`
- `watchdog!WdLogSingleEntry2` at `0x14038f04f`
- `watchdog!WdLogSingleEntry2` at `0x14038f23b`
- `watchdog!WdLogSingleEntry2` at `0x14038f557`
- `watchdog!WdLogSingleEntry2` at `0x14038f672`
- `watchdog!WdLogSingleEntry2` at `0x14038f828`
- `watchdog!WdLogSingleEntry2` at `0x140390023`
- `watchdog!WdLogSingleEntry0` at `0x14038f4bd`
- `watchdog!WdLogSingleEntry0` at `0x14038f5d8`
- `watchdog!WdLogSingleEntry0` at `0x14038fc75`
- `watchdog!WdLogSingleEntry0` at `0x14038fce9`
- `watchdog!WdLogSingleEntry0` at `0x14038f4bd`
- `watchdog!WdLogSingleEntry0` at `0x14038f5d8`
- `watchdog!WdLogSingleEntry0` at `0x14038fc75`
- `watchdog!WdLogSingleEntry0` at `0x14038fce9`
- `watchdog!WdLogSingleEntry1` at `0x14038f171`
- `watchdog!WdLogSingleEntry1` at `0x14038f1d1`
- `watchdog!WdLogSingleEntry1` at `0x14038f2aa`
- `watchdog!WdLogSingleEntry1` at `0x14038f9d6`
- `watchdog!WdLogSingleEntry1` at `0x14038f171`
- `watchdog!WdLogSingleEntry1` at `0x14038f1d1`
- `watchdog!WdLogSingleEntry1` at `0x14038f2aa`
- `watchdog!WdLogSingleEntry1` at `0x14038f9d6`

## string_xrefs

- `0x14038fa0d`: `Failed to acquire CoreDeviceAccess, returning 0x%I64x`
- `0x14038f187`: `Invalid PresentHistoryToken Mode, returning 0x%I64x`
- `0x140390062`: `0x%I64x 0x%I64x encountered exception copying args`
- `0x14038fca5`: `pToken`

## pseudocode

```c
__int64 __fastcall DxgkPresentRedirected(unsigned __int64 Src)
{
  __int64 v2; // rcx
  struct DXGPROCESS *Current; // r15
  __int64 v4; // rcx
  __int64 CurrentProcess; // rax
  __int64 v7; // r8
  const wchar_t *v8; // r9
  unsigned int v9; // ebx
  struct DXGDEVICE *v10; // rsi
  __int64 v11; // r13
  int v12; // edx
  __int64 v13; // rcx
  __int64 v14; // r8
  struct DXGGLOBAL *Global; // rax
  volatile signed __int32 *v16; // r12
  __int64 v17; // rbx
  DXGPUSHLOCK *v18; // rcx
  int v20; // edx
  __int64 v21; // r15
  __int64 v22; // r15
  __int64 v23; // rbx
  int v25; // edx
  __int64 v26; // r15
  __int64 v27; // r15
  int v28; // edx
  __int64 v29; // rcx
  __int64 v30; // r8
  int v31; // r15d
  int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // r8
  bool v35; // zf
  unsigned int v36; // r14d
  ADAPTER_RENDER **v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // r8
  struct DXGDEVICE *v40; // rcx
  ADAPTER_RENDER **v41; // rcx
  int v42; // edx
  __int64 v43; // rcx
  __int64 v44; // r8
  ADAPTER_RENDER **v45; // rcx
  int v46; // edx
  unsigned int v47; // [rsp+60h] [rbp-5F8h] BYREF
  __int64 v48; // [rsp+68h] [rbp-5F0h]
  _DWORD *v49; // [rsp+70h] [rbp-5E8h]
  int *v50; // [rsp+78h] [rbp-5E0h]
  char v51; // [rsp+80h] [rbp-5D8h]
  int v52; // [rsp+88h] [rbp-5D0h] BYREF
  unsigned int v53; // [rsp+8Ch] [rbp-5CCh]
  struct DXGDEVICE *v54[2]; // [rsp+90h] [rbp-5C8h] BYREF
  struct DXGDEVICE *v55; // [rsp+A0h] [rbp-5B8h] BYREF
  char v56[8]; // [rsp+A8h] [rbp-5B0h] BYREF
  char v57; // [rsp+B0h] [rbp-5A8h]
  char v58[8]; // [rsp+B8h] [rbp-5A0h] BYREF
  __int64 v59; // [rsp+C0h] [rbp-598h]
  char v60; // [rsp+C8h] [rbp-590h]
  unsigned __int64 v61; // [rsp+D0h] [rbp-588h]
  int v62; // [rsp+D8h] [rbp-580h] BYREF
  char *v63; // [rsp+E0h] [rbp-578h]
  char *v64; // [rsp+E8h] [rbp-570h]
  _BYTE *v65; // [rsp+F0h] [rbp-568h]
  unsigned __int64 v66; // [rsp+F8h] [rbp-560h] BYREF
  unsigned int v67; // [rsp+100h] [rbp-558h]
  int v68; // [rsp+104h] [rbp-554h]
  __int64 v69; // [rsp+108h] [rbp-550h]
  struct DXGDEVICE *v70; // [rsp+110h] [rbp-548h]
  _BYTE v71[160]; // [rsp+120h] [rbp-538h] BYREF
  _BYTE v72[1120]; // [rsp+1C0h] [rbp-498h] BYREF

  v52 = -1073741823;
  Current = DXGPROCESS::GetCurrent();
  v54[0] = Current;
  if ( !Current )
  {
    PsGetCurrentProcess(v2);
    WdLogSingleEntry2(2, -1073741811);
    WdLogGlobalForLineNumber = 1073;
    CurrentProcess = PsGetCurrentProcess(v4);
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Presenting from unexpected process 0x%I64x 0x%I64x",
      -1073741811,
      CurrentProcess,
      0,
      0,
      0);
    return 3221225485LL;
  }
  memset(v72, 0, sizeof(v72));
  if ( (unsigned __int8)PsGetCurrentThreadPreviousMode() == 1 )
  {
    RtlCopyFromUser(v72, (void *)Src, 0x460u);
    Src = (unsigned __int64)v72;
  }
  v61 = Src;
  v48 = 0;
  v47 = 2147;
  v50 = &v52;
  v51 = 1;
  v49 = (_DWORD *)(Src & -(__int64)(bTracingEnabled != 0));
  if ( (qword_14015C500 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(Src & -(__int64)(bTracingEnabled != 0), EventProfilerEnter, v7, 2147);
  DXGETWPROFILER_BASE::PushProfilerEntry(&v47, 2147);
  if ( *(_DWORD *)(Src + 16) != 9 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 1105;
    v8 = L"Invalid PresentHistoryToken Mode, returning 0x%I64x";
LABEL_11:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v8, -1073741811, 0, 0, 0, 0);
LABEL_57:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v47);
    if ( v51 )
    {
      if ( v49 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
        McTemplateK0qqxxqq_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v28,
          v30,
          *v49,
          v49[14],
          *((_QWORD *)v49 + 10),
          *((_QWORD *)v49 + 11),
          v49[274],
          *v50);
    }
    else if ( v49 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
    {
      McTemplateK0qpqqqqpp_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v28,
        v30,
        *v49,
        *((_QWORD *)v49 + 1),
        v49[4],
        v49[21],
        v49[22],
        *v50,
        v49[5],
        v49[6]);
    }
    if ( (qword_14015C500 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v29, EventProfilerExit, v30, v47);
    return 3221225485LL;
  }
  if ( *(_DWORD *)(Src + 1096) )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 1112;
    v8 = L"Reserved bits should not be set, returning 0x%I64x";
    goto LABEL_11;
  }
  v9 = *(_DWORD *)Src;
  v53 = *(_DWORD *)Src;
  v54[0] = 0;
  DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)&v55, *(_DWORD *)(Src + 4), Current, v54);
  v10 = v54[0];
  if ( !v54[0] )
  {
    WdLogSingleEntry2(2, *(unsigned int *)(Src + 4));
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
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v55);
    goto LABEL_57;
  }
  v11 = *(_QWORD *)(*((_QWORD *)v54[0] + 2) + 16LL);
  if ( (*(_DWORD *)(v11 + 3088) & 8) != 0 )
  {
    WdLogSingleEntry1(2);
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
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v55);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v47);
    if ( v51 )
    {
      if ( v49 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
        McTemplateK0qqxxqq_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v12,
          v14,
          *v49,
          v49[14],
          *((_QWORD *)v49 + 10),
          *((_QWORD *)v49 + 11),
          v49[274],
          *v50);
    }
    else if ( v49 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
    {
      McTemplateK0qpqqqqpp_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v12,
        v14,
        *v49,
        *((_QWORD *)v49 + 1),
        v49[4],
        v49[21],
        v49[22],
        *v50,
        v49[5],
        v49[6]);
    }
    if ( (qword_14015C500 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v13, EventProfilerExit, v14, v47);
    return 3221225485LL;
  }
  Global = DXGGLOBAL::GetGlobal();
  DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v56, Global, 0);
  DXGSYNCOBJECTLOCK::AcquireShared((DXGSYNCOBJECTLOCK *)v56);
  v16 = (volatile signed __int32 *)((char *)Current + 248);
  v54[0] = (struct DXGDEVICE *)((v9 >> 6) & 0xFFFFFF);
  v17 = 2 * (__int64)v54[0];
  v18 = (struct DXGPROCESS *)((char *)Current + 248);
  if ( *(int *)(v11 + 3116) < 2000 )
  {
    DXGPUSHLOCK::AcquireShared(v18);
    if ( LODWORD(v54[0]) < *((_DWORD *)Current + 74)
      && (v25 = *(_DWORD *)(*((_QWORD *)Current + 35) + 8 * v17 + 8),
          ((v53 >> 25) & 0x60) == (*(_BYTE *)(*((_QWORD *)Current + 35) + 8 * v17 + 8) & 0x60))
      && (v25 & 0x2000) == 0
      && (v25 & 0x1F) != 0 )
    {
      v27 = *((_QWORD *)Current + 35);
      if ( (*(_BYTE *)(v27 + 8 * v17 + 8) & 0x1F) == 8 )
      {
        v26 = *(_QWORD *)(v27 + 8 * v17);
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v26 = 0;
      }
    }
    else
    {
      v26 = 0;
    }
    _InterlockedAdd(v16 + 4, 0xFFFFFFFF);
    ExReleasePushLockSharedEx(v16, 0);
    KeLeaveCriticalRegion();
    if ( !v26 )
    {
      v23 = v53;
      WdLogSingleEntry2(2, v53);
      WdLogGlobalForLineNumber = 1166;
      goto LABEL_55;
    }
  }
  else
  {
    DXGPUSHLOCK::AcquireShared(v18);
    if ( LODWORD(v54[0]) < *((_DWORD *)Current + 74)
      && (v20 = *(_DWORD *)(*((_QWORD *)Current + 35) + 8 * v17 + 8),
          ((v53 >> 25) & 0x60) == (*(_BYTE *)(*((_QWORD *)Current + 35) + 8 * v17 + 8) & 0x60))
      && (v20 & 0x2000) == 0
      && (v20 & 0x1F) != 0 )
    {
      v22 = *((_QWORD *)Current + 35);
      if ( (*(_BYTE *)(v22 + 8 * v17 + 8) & 0x1F) == 0xB )
      {
        v21 = *(_QWORD *)(v22 + 8 * v17);
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v21 = 0;
      }
    }
    else
    {
      v21 = 0;
    }
    _InterlockedAdd(v16 + 4, 0xFFFFFFFF);
    ExReleasePushLockSharedEx(v16, 0);
    KeLeaveCriticalRegion();
    if ( !v21 )
    {
      v23 = v53;
      WdLogSingleEntry2(2, v53);
      WdLogGlobalForLineNumber = 1156;
LABEL_55:
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Invalid hSyncObj (0x%I64x) specified, returning 0x%I64x",
        v23,
        -1073741811,
        0,
        0,
        0);
      DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v56);
      goto LABEL_56;
    }
  }
  _InterlockedIncrement64((volatile signed __int64 *)v10 + 8);
  v54[0] = v10;
  DXGSYNCOBJECTLOCK::Release((DXGSYNCOBJECTLOCK *)v56);
  v59 = v11;
  v60 = 0;
  DXGADAPTERSTOPRESETLOCKSHARED::Acquire((DXGADAPTERSTOPRESETLOCKSHARED *)v58);
  if ( *(_DWORD *)(v11 + 200) != 1 )
  {
    v31 = -1073741823;
    WdLogSingleEntry2(2, v11);
    WdLogGlobalForLineNumber = 1186;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"DXGADAPTER: 0x%I64x stopped, returning 0x%I64x",
      v11,
      -1073741823,
      0,
      0,
      0);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v58);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v54);
    DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v56);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v55);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v47);
    v35 = v51 == 0;
LABEL_100:
    if ( v35 )
    {
      if ( v49 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
        McTemplateK0qpqqqqpp_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v32,
          v34,
          *v49,
          *((_QWORD *)v49 + 1),
          v49[4],
          v49[21],
          v49[22],
          *v50,
          v49[5],
          v49[6]);
    }
    else if ( v49 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    {
      McTemplateK0qqxxqq_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v32,
        v34,
        *v49,
        v49[14],
        *((_QWORD *)v49 + 10),
        *((_QWORD *)v49 + 11),
        v49[274],
        *v50);
    }
    if ( (qword_14015C500 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v33, EventProfilerExit, v34, v47);
    return (unsigned int)v31;
  }
  COREDEVICEACCESS::COREDEVICEACCESS(v71, v10, 2);
  v52 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v71, 0);
  if ( v52 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 1194;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to acquire CoreDeviceAccess, returning 0x%I64x",
      v52,
      0,
      0,
      0,
      0);
    v36 = v52;
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v71);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v58);
    if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v10 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      ADAPTER_RENDER::DestroyDeviceNoLocks(*((ADAPTER_RENDER **)v10 + 2), v10);
    if ( v57 )
      DXGSYNCOBJECTLOCK::Release((DXGSYNCOBJECTLOCK *)v56);
    v37 = (ADAPTER_RENDER **)v55;
    if ( v55 && _InterlockedExchangeAdd64((volatile signed __int64 *)v55 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      ADAPTER_RENDER::DestroyDeviceNoLocks(v37[2], (struct DXGDEVICE *)v37);
LABEL_131:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v47);
    if ( v51 )
    {
      if ( v49 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
        McTemplateK0qqxxqq_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v46,
          v39,
          *v49,
          v49[14],
          *((_QWORD *)v49 + 10),
          *((_QWORD *)v49 + 11),
          v49[274],
          *v50);
    }
    else if ( v49 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
    {
      McTemplateK0qpqqqqpp_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v46,
        v39,
        *v49,
        *((_QWORD *)v49 + 1),
        v49[4],
        v49[21],
        v49[22],
        *v50,
        v49[5],
        v49[6]);
    }
    if ( (qword_14015C500 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v38, EventProfilerExit, v39, v47);
    return v36;
  }
  v31 = SubmitPresentHistoryTokenPreparation(
          (struct DXGADAPTERSTOPRESETLOCKSHARED *)v58,
          (struct COREDEVICEACCESS *)v71,
          (struct DXGADAPTER *)v11,
          (struct _D3DKMT_PRESENTHISTORYTOKEN *)(Src + 16),
          0,
          0);
  v52 = v31;
  if ( v31 < 0 )
  {
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v71);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v58);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v54);
    DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v56);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v55);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v47);
    v35 = v51 == 0;
    goto LABEL_100;
  }
  v62 = -1073741823;
  v63 = (char *)(Src + 16);
  v64 = v58;
  v65 = v71;
  if ( Src == -16 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 122;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pToken", 122, 0, 0, 0, 0);
  }
  CVidSchSubmitData::CVidSchSubmitData((CVidSchSubmitData *)v54, *(struct ADAPTER_RENDER **)(v11 + 3240), 1);
  v40 = v54[0];
  if ( v54[0] )
  {
    *(_DWORD *)v54[0] = *(_DWORD *)v54[0] & 0xFFFCFEDF | 0x10120;
    *((_QWORD *)v40 + 59) = *(_QWORD *)(Src + 8);
    v68 = 0;
    v66 = Src;
    v67 = v53;
    v69 = v11;
    v70 = v10;
    v36 = SubmitPresentHistoryToken(
            (const struct _D3DKMT_PRESENTHISTORYTOKEN *)(Src + 16),
            (struct COREDEVICEACCESS *)v71,
            (struct DXGADAPTERSTOPRESETLOCKSHARED *)v58,
            0,
            1,
            0,
            0,
            v40,
            0,
            (struct _PRESENT_REDIRECTED_PARAMS *)&v66,
            0);
    v52 = v36;
    v62 = v36;
    CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v54);
    TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD((TOKEN_BINDING_GUARD *)&v62);
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v71);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v58);
    if ( v10 && _InterlockedExchangeAdd64((volatile signed __int64 *)v10 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      ADAPTER_RENDER::DestroyDeviceNoLocks(*((ADAPTER_RENDER **)v10 + 2), v10);
    if ( v57 )
      DXGSYNCOBJECTLOCK::Release((DXGSYNCOBJECTLOCK *)v56);
    v45 = (ADAPTER_RENDER **)v55;
    if ( v55 && _InterlockedExchangeAdd64((volatile signed __int64 *)v55 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      ADAPTER_RENDER::DestroyDeviceNoLocks(v45[2], (struct DXGDEVICE *)v45);
    goto LABEL_131;
  }
  WdLogSingleEntry0(6);
  WdLogGlobalForLineNumber = 1218;
  DxgkLogInternalTriageEvent(0, 262145, -1, (unsigned int)L"Failed to allocate VidSchSubmitData", 1218, 0, 0, 0, 0);
  CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v54);
  TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD((TOKEN_BINDING_GUARD *)&v62);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v71);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v58);
  if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v10 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    ADAPTER_RENDER::DestroyDeviceNoLocks(*((ADAPTER_RENDER **)v10 + 2), v10);
  if ( v57 )
    DXGSYNCOBJECTLOCK::Release((DXGSYNCOBJECTLOCK *)v56);
  v41 = (ADAPTER_RENDER **)v55;
  if ( v55 && _InterlockedExchangeAdd64((volatile signed __int64 *)v55 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    ADAPTER_RENDER::DestroyDeviceNoLocks(v41[2], (struct DXGDEVICE *)v41);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v47);
  if ( v51 )
  {
    if ( v49 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
      McTemplateK0qqxxqq_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v42,
        v44,
        *v49,
        v49[14],
        *((_QWORD *)v49 + 10),
        *((_QWORD *)v49 + 11),
        v49[274],
        *v50);
  }
  else if ( v49 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
  {
    McTemplateK0qpqqqqpp_EtwWriteTransfer(
      (unsigned int)&DxgkControlGuid_Context,
      v42,
      v44,
      *v49,
      *((_QWORD *)v49 + 1),
      v49[4],
      v49[21],
      v49[22],
      *v50,
      v49[5],
      v49[6]);
  }
  if ( (qword_14015C500 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v43, EventProfilerExit, v44, v47);
  return 3221225495LL;
}

```

## disassembly

```asm
0x14038efe0  mov     [rsp+arg_8], rbx
0x14038efe5  mov     [rsp+arg_10], rsi
0x14038efea  push    rdi
0x14038efeb  push    r12
0x14038efed  push    r13
0x14038efef  push    r14
0x14038eff1  push    r15
0x14038eff3  sub     rsp, 630h
0x14038effa  mov     rax, cs:__security_cookie
0x14038f001  xor     rax, rsp
0x14038f004  mov     [rsp+658h+var_38], rax
0x14038f00c  mov     r14, rcx
0x14038f00f  mov     [rsp+658h+var_5D0], 0C0000001h
0x14038f01a  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14038f01f  mov     r15, rax
0x14038f022  mov     [rsp+658h+var_5C8], rax
0x14038f02a  xor     r12d, r12d
0x14038f02d  test    rax, rax
0x14038f030  jnz     short loc_14038F0A8
0x14038f032  call    cs:__imp_PsGetCurrentProcess
0x14038f039  nop     dword ptr [rax+rax+00h]
0x14038f03e  mov     r8, rax
0x14038f041  mov     rsi, 0FFFFFFFFC000000Dh
0x14038f048  mov     rdx, rsi
0x14038f04b  lea     ecx, [r15+2]
0x14038f04f  call    cs:__imp_WdLogSingleEntry2
0x14038f056  nop     dword ptr [rax+rax+00h]
0x14038f05b  mov     cs:WdLogGlobalForLineNumber, 431h
0x14038f065  call    cs:__imp_PsGetCurrentProcess
0x14038f06c  nop     dword ptr [rax+rax+00h]
0x14038f071  mov     [rsp+658h+var_618], r12
0x14038f076  mov     [rsp+658h+var_620], r12
0x14038f07b  mov     [rsp+658h+var_628], r12
0x14038f080  mov     [rsp+658h+var_630], rax
0x14038f085  mov     [rsp+658h+var_638], rsi
0x14038f08a  lea     r9, aPresentingFrom; "Presenting from unexpected process 0x%I"...
0x14038f091  or      r8d, 0FFFFFFFFh
0x14038f095  mov     edx, 40000h
0x14038f09a  xor     ecx, ecx
0x14038f09c  call    DxgkLogInternalTriageEvent
0x14038f0a1  mov     eax, esi
0x14038f0a3  jmp     loc_14039007E
0x14038f0a8  mov     ebx, 460h
0x14038f0ad  mov     r8d, ebx; Size
0x14038f0b0  xor     edx, edx; Val
0x14038f0b2  lea     rcx, [rsp+658h+var_498]; void *
0x14038f0ba  call    memset
0x14038f0bf  nop
0x14038f0c0  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x14038f0c7  nop     dword ptr [rax+rax+00h]
0x14038f0cc  cmp     al, 1
0x14038f0ce  jnz     short loc_14038F0EB
0x14038f0d0  mov     r8d, ebx; Size
0x14038f0d3  mov     rdx, r14; Src
0x14038f0d6  lea     rcx, [rsp+658h+var_498]; void *
0x14038f0de  call    RtlCopyFromUser
0x14038f0e3  lea     r14, [rsp+658h+var_498]
0x14038f0eb  mov     [rsp+658h+var_588], r14
0x14038f0f3  mov     al, cs:bTracingEnabled
0x14038f0f9  neg     al
0x14038f0fb  sbb     rcx, rcx
0x14038f0fe  and     rcx, r14
0x14038f101  mov     [rsp+658h+var_5F0], r12
0x14038f106  mov     ebx, 863h
0x14038f10b  mov     [rsp+658h+var_5F8], ebx
0x14038f10f  lea     rax, [rsp+658h+var_5D0]
0x14038f117  mov     [rsp+658h+var_5E0], rax
0x14038f11c  mov     [rsp+658h+var_5D8], 1
0x14038f124  mov     [rsp+658h+var_5E8], rcx
0x14038f129  mov     rax, cs:qword_14015C500
0x14038f130  mov     edi, 2
0x14038f135  test    dil, al
0x14038f138  jz      short loc_14038F152
0x14038f13a  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14038f141  jz      short loc_14038F152
0x14038f143  mov     r9d, ebx
0x14038f146  lea     rdx, EventProfilerEnter
0x14038f14d  call    McTemplateK0q_EtwWriteTransfer
0x14038f152  mov     edx, ebx
0x14038f154  lea     rcx, [rsp+658h+var_5F8]
0x14038f159  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x14038f15e  cmp     dword ptr [r14+10h], 9
0x14038f163  jz      short loc_14038F1BC
0x14038f165  mov     rsi, 0FFFFFFFFC000000Dh
0x14038f16c  mov     rdx, rsi
0x14038f16f  mov     ecx, edi
0x14038f171  call    cs:__imp_WdLogSingleEntry1
0x14038f178  nop     dword ptr [rax+rax+00h]
0x14038f17d  mov     cs:WdLogGlobalForLineNumber, 451h
0x14038f187  lea     r9, aInvalidPresent_0; "Invalid PresentHistoryToken Mode, retur"...
0x14038f18e  mov     [rsp+658h+var_618], r12
0x14038f193  mov     [rsp+658h+var_620], r12
0x14038f198  mov     [rsp+658h+var_628], r12
0x14038f19d  mov     [rsp+658h+var_630], r12
0x14038f1a2  mov     [rsp+658h+var_638], rsi
0x14038f1a7  or      r8d, 0FFFFFFFFh
0x14038f1ab  mov     edx, 40000h
0x14038f1b0  xor     ecx, ecx
0x14038f1b2  call    DxgkLogInternalTriageEvent
0x14038f1b7  jmp     loc_14038F6D2
0x14038f1bc  cmp     [r14+448h], r12d
0x14038f1c3  jz      short loc_14038F1F0
0x14038f1c5  mov     rsi, 0FFFFFFFFC000000Dh
0x14038f1cc  mov     rdx, rsi
0x14038f1cf  mov     ecx, edi
0x14038f1d1  call    cs:__imp_WdLogSingleEntry1
0x14038f1d8  nop     dword ptr [rax+rax+00h]
0x14038f1dd  mov     cs:WdLogGlobalForLineNumber, 458h
0x14038f1e7  lea     r9, aReservedBitsSh; "Reserved bits should not be set, return"...
0x14038f1ee  jmp     short loc_14038F18E
0x14038f1f0  mov     ebx, [r14]
0x14038f1f3  mov     [rsp+658h+var_5CC], ebx
0x14038f1fa  mov     [rsp+658h+var_5C8], r12
0x14038f202  lea     r9, [rsp+658h+var_5C8]; struct DXGDEVICE **
0x14038f20a  mov     r8, r15; struct DXGPROCESS *
0x14038f20d  mov     edx, [r14+4]; unsigned int
0x14038f211  lea     rcx, [rsp+658h+var_5B8]; this
0x14038f219  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x14038f21e  mov     rsi, [rsp+658h+var_5C8]
0x14038f226  test    rsi, rsi
0x14038f229  jnz     short loc_14038F28A
0x14038f22b  mov     edx, [r14+4]
0x14038f22f  mov     rsi, 0FFFFFFFFC000000Dh
0x14038f236  mov     r8, rsi
0x14038f239  mov     ecx, edi
0x14038f23b  call    cs:__imp_WdLogSingleEntry2
0x14038f242  nop     dword ptr [rax+rax+00h]
0x14038f247  mov     cs:WdLogGlobalForLineNumber, 469h
0x14038f251  mov     eax, [r14+4]
0x14038f255  mov     [rsp+658h+var_618], r12
0x14038f25a  mov     [rsp+658h+var_620], r12
0x14038f25f  mov     [rsp+658h+var_628], r12
0x14038f264  mov     [rsp+658h+var_630], rsi
0x14038f269  mov     [rsp+658h+var_638], rax
0x14038f26e  lea     r9, aInvalidHdevice_2; "Invalid hDevice (0x%I64x) specified, re"...
0x14038f275  or      r8d, 0FFFFFFFFh
0x14038f279  mov     edx, 40000h
0x14038f27e  xor     ecx, ecx
0x14038f280  call    DxgkLogInternalTriageEvent
0x14038f285  jmp     loc_14038F6C5
0x14038f28a  mov     rax, [rsi+10h]
0x14038f28e  mov     r13, [rax+10h]
0x14038f292  mov     eax, [r13+0C10h]
0x14038f299  shr     eax, 3
0x14038f29c  test    al, 1
0x14038f29e  jz      loc_14038F400
0x14038f2a4  mov     edx, [r14+4]
0x14038f2a8  mov     ecx, edi
0x14038f2aa  call    cs:__imp_WdLogSingleEntry1
0x14038f2b1  nop     dword ptr [rax+rax+00h]
0x14038f2b6  mov     cs:WdLogGlobalForLineNumber, 471h
0x14038f2c0  mov     eax, [r14+4]
0x14038f2c4  mov     [rsp+658h+var_618], r12
0x14038f2c9  mov     [rsp+658h+var_620], r12
0x14038f2ce  mov     [rsp+658h+var_628], r12
0x14038f2d3  mov     [rsp+658h+var_630], r12
0x14038f2d8  mov     [rsp+658h+var_638], rax
0x14038f2dd  lea     r9, aPresentIsNotSu; "Present is not supported on MCDM adapte"...
0x14038f2e4  or      r8d, 0FFFFFFFFh
0x14038f2e8  mov     edx, 40000h
0x14038f2ed  xor     ecx, ecx
0x14038f2ef  call    DxgkLogInternalTriageEvent
0x14038f2f4  lea     rcx, [rsp+658h+var_5B8]; this
0x14038f2fc  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x14038f301  lea     rcx, [rsp+658h+var_5F8]; this
0x14038f306  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14038f30b  mov     r9, [rsp+658h+var_5E8]
0x14038f310  cmp     [rsp+658h+var_5D8], r12b
0x14038f318  jz      short loc_14038F371
0x14038f31a  test    r9, r9
0x14038f31d  jz      loc_14038F3CE
0x14038f323  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x14038f32a  jz      loc_14038F3CE
0x14038f330  mov     rax, [rsp+658h+var_5E0]
0x14038f335  mov     ecx, [rax]
0x14038f337  mov     dword ptr [rsp+658h+var_618], ecx
0x14038f33b  mov     eax, [r9+448h]
0x14038f342  mov     dword ptr [rsp+658h+var_620], eax
0x14038f346  mov     rax, [r9+58h]
0x14038f34a  mov     [rsp+658h+var_628], rax
0x14038f34f  mov     rax, [r9+50h]
0x14038f353  mov     [rsp+658h+var_630], rax
0x14038f358  mov     eax, [r9+38h]
0x14038f35c  mov     dword ptr [rsp+658h+var_638], eax
0x14038f360  mov     r9d, [r9]
0x14038f363  lea     rcx, DxgkControlGuid_Context
0x14038f36a  call    McTemplateK0qqxxqq_EtwWriteTransfer
0x14038f36f  jmp     short loc_14038F3CE
0x14038f371  test    r9, r9
0x14038f374  jz      short loc_14038F3CE
0x14038f376  mov     rax, cs:Microsoft_Windows_DxgKrnlEnableBits
0x14038f37d  test    al, al
0x14038f37f  jns     short loc_14038F3CE
0x14038f381  mov     eax, [r9+18h]
0x14038f385  mov     ecx, [r9+14h]
0x14038f389  mov     [rsp+658h+var_608], rax
0x14038f38e  mov     [rsp+658h+var_610], rcx
0x14038f393  mov     rax, [rsp+658h+var_5E0]
0x14038f398  mov     ecx, [rax]
0x14038f39a  mov     dword ptr [rsp+658h+var_618], ecx
0x14038f39e  mov     eax, [r9+58h]
0x14038f3a2  mov     dword ptr [rsp+658h+var_620], eax
0x14038f3a6  mov     eax, [r9+54h]
0x14038f3aa  mov     dword ptr [rsp+658h+var_628], eax
0x14038f3ae  mov     eax, [r9+10h]
0x14038f3b2  mov     dword ptr [rsp+658h+var_630], eax
0x14038f3b6  mov     rax, [r9+8]
0x14038f3ba  mov     [rsp+658h+var_638], rax
0x14038f3bf  mov     r9d, [r9]
0x14038f3c2  lea     rcx, DxgkControlGuid_Context
0x14038f3c9  call    McTemplateK0qpqqqqpp_EtwWriteTransfer
0x14038f3ce  mov     rax, cs:qword_14015C500
0x14038f3d5  test    dil, al
0x14038f3d8  jz      short loc_14038F3F4
0x14038f3da  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14038f3e1  jz      short loc_14038F3F4
0x14038f3e3  mov     r9d, [rsp+658h+var_5F8]
0x14038f3e8  lea     rdx, EventProfilerExit
0x14038f3ef  call    McTemplateK0q_EtwWriteTransfer
0x14038f3f4  mov     rsi, 0FFFFFFFFC000000Dh
0x14038f3fb  jmp     loc_14038F0A1
0x14038f400  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14038f405  mov     rdx, rax; struct DXGGLOBAL *
0x14038f408  xor     r8d, r8d; bool
0x14038f40b  lea     rcx, [rsp+658h+var_5B0]; this
0x14038f413  call    ??0DXGSYNCOBJECTLOCK@@QEAA@QEAVDXGGLOBAL@@_N@Z; DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK(DXGGLOBAL * const,bool)
0x14038f418  lea     rcx, [rsp+658h+var_5B0]; this
0x14038f420  call    ?AcquireShared@DXGSYNCOBJECTLOCK@@QEAAXXZ; DXGSYNCOBJECTLOCK::AcquireShared(void)
0x14038f425  lea     r12, [r15+0F8h]
0x14038f42c  mov     eax, ebx
0x14038f42e  shr     eax, 6
0x14038f431  and     eax, 0FFFFFFh
0x14038f436  mov     [rsp+658h+var_5C8], rax
0x14038f43e  mov     ebx, eax
0x14038f440  add     rbx, rbx
0x14038f443  mov     rcx, r12; this
0x14038f446  cmp     dword ptr [r13+0C2Ch], 7D0h
0x14038f451  jl      loc_14038F572
0x14038f457  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x14038f45c  mov     rax, [rsp+658h+var_5C8]
0x14038f464  cmp     eax, [r15+128h]
0x14038f46b  jb      short loc_14038F471
0x14038f46d  xor     al, al
0x14038f46f  jmp     short loc_14038F49F
0x14038f471  mov     rax, [r15+118h]
0x14038f478  mov     edx, [rax+rbx*8+8]
0x14038f47c  mov     ecx, [rsp+658h+var_5CC]
0x14038f483  shr     ecx, 19h
0x14038f486  and     ecx, 60h
0x14038f489  mov     eax, edx
0x14038f48b  and     eax, 60h
0x14038f48e  cmp     cl, al
0x14038f490  jnz     short loc_14038F46D
0x14038f492  bt      edx, 0Dh
0x14038f496  jb      short loc_14038F46D
0x14038f498  test    dl, 1Fh
0x14038f49b  jz      short loc_14038F46D
0x14038f49d  mov     al, 1
0x14038f49f  test    al, al
0x14038f4a1  jnz     short loc_14038F4A8
0x14038f4a3  xor     r15d, r15d
0x14038f4a6  jmp     short loc_14038F50F
0x14038f4a8  mov     r15, [r15+118h]
0x14038f4af  mov     eax, [r15+rbx*8+8]
0x14038f4b4  and     eax, 1Fh
0x14038f4b7  cmp     al, 0Bh
0x14038f4b9  jz      short loc_14038F50B
0x14038f4bb  mov     ecx, edi
0x14038f4bd  call    cs:__imp_WdLogSingleEntry0
0x14038f4c4  nop     dword ptr [rax+rax+00h]
0x14038f4c9  mov     eax, 13Eh
0x14038f4ce  mov     cs:WdLogGlobalForLineNumber, eax
0x14038f4d4  xor     ebx, ebx
0x14038f4d6  mov     [rsp+658h+var_618], rbx
0x14038f4db  mov     [rsp+658h+var_620], rbx
0x14038f4e0  mov     [rsp+658h+var_628], rbx
0x14038f4e5  mov     [rsp+658h+var_630], rbx
0x14038f4ea  mov     [rsp+658h+var_638], rax
0x14038f4ef  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x14038f4f6  or      r8d, 0FFFFFFFFh
0x14038f4fa  mov     edx, 40000h
0x14038f4ff  xor     ecx, ecx
0x14038f501  call    DxgkLogInternalTriageEvent
0x14038f506  mov     r15d, ebx
0x14038f509  jmp     short loc_14038F50F
0x14038f50b  mov     r15, [r15+rbx*8]
0x14038f50f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14038f513  lock add [r12+10h], ebx
0x14038f519  xor     edx, edx
0x14038f51b  mov     rcx, r12
0x14038f51e  call    cs:__imp_ExReleasePushLockSharedEx
0x14038f525  nop     dword ptr [rax+rax+00h]
0x14038f52a  call    cs:__imp_KeLeaveCriticalRegion
0x14038f531  nop     dword ptr [rax+rax+00h]
0x14038f536  xor     r12d, r12d
0x14038f539  test    r15, r15
0x14038f53c  jnz     loc_14038F7D2
0x14038f542  mov     ebx, [rsp+658h+var_5CC]
0x14038f549  mov     rsi, 0FFFFFFFFC000000Dh
0x14038f550  mov     r8, rsi
  ... truncated ...
```
