# NtDxgkNativeFencePresent

- ea: `0x140256830`
- end: `0x140257740`
- name: `NtDxgkNativeFencePresent`
- size: `3856`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `29`
- tags: `broker_com_uri`

## callees

- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x140015a70`
- `0x140015b30`
- `0x140018054`
- `0x140018190`
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
- `0x140048a5c`
- `0x140049424`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x140256830`
- `0x14032a5c4`
- `0x14038f1bc`
- `0x14038f59c`
- `0x14038f62c`
- `0x14038fb34`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140256e62`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140256e62`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140256e56`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140256e56`
- `ntoskrnl!PsGetCurrentProcess` at `0x140256882`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402568b5`
- `ntoskrnl!PsGetCurrentProcess` at `0x140256882`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402568b5`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x140256910`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x140256910`
- `watchdog!WdLogSingleEntry2` at `0x14025689f`
- `watchdog!WdLogSingleEntry2` at `0x140256b97`
- `watchdog!WdLogSingleEntry2` at `0x140256e82`
- `watchdog!WdLogSingleEntry2` at `0x140256ebd`
- `watchdog!WdLogSingleEntry2` at `0x140256ef8`
- `watchdog!WdLogSingleEntry2` at `0x1402570a2`
- `watchdog!WdLogSingleEntry2` at `0x1402576b7`
- `watchdog!WdLogSingleEntry2` at `0x14025689f`
- `watchdog!WdLogSingleEntry2` at `0x140256b97`
- `watchdog!WdLogSingleEntry2` at `0x140256e82`
- `watchdog!WdLogSingleEntry2` at `0x140256ebd`
- `watchdog!WdLogSingleEntry2` at `0x140256ef8`
- `watchdog!WdLogSingleEntry2` at `0x1402570a2`
- `watchdog!WdLogSingleEntry2` at `0x1402576b7`
- `watchdog!WdLogSingleEntry0` at `0x140256df6`
- `watchdog!WdLogSingleEntry0` at `0x1402573c9`
- `watchdog!WdLogSingleEntry0` at `0x140256df6`
- `watchdog!WdLogSingleEntry0` at `0x1402573c9`
- `watchdog!WdLogSingleEntry1` at `0x1402569e7`
- `watchdog!WdLogSingleEntry1` at `0x140256aee`
- `watchdog!WdLogSingleEntry1` at `0x140256c02`
- `watchdog!WdLogSingleEntry1` at `0x140257164`
- `watchdog!WdLogSingleEntry1` at `0x1402569e7`
- `watchdog!WdLogSingleEntry1` at `0x140256aee`
- `watchdog!WdLogSingleEntry1` at `0x140256c02`
- `watchdog!WdLogSingleEntry1` at `0x140257164`

## string_xrefs

- `0x14025719b`: `Failed to acquire CoreDeviceAccess, returning 0x%I64x`
- `0x1402576f6`: `0x%I64x 0x%I64x encountered exception copying args`
- `0x1402569fd`: `Invalid PresentHistoryToken Model, returning 0x%I64x`

## pseudocode

```c
__int64 __fastcall NtDxgkNativeFencePresent(char *Src)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  struct DXGPROCESS *Current; // rsi
  __int64 CurrentProcess; // rax
  unsigned int v6; // esi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v11; // r8
  char *v12; // rax
  int v13; // eax
  const wchar_t *v14; // r9
  __int64 v15; // rcx
  __int64 v16; // r8
  bool v17; // zf
  int v18; // edx
  __int64 v19; // r12
  struct DXGDEVICE *v20; // r13
  __int64 v21; // r14
  int v22; // edx
  __int64 v23; // rcx
  __int64 v24; // r8
  struct DXGGLOBAL *Global; // rax
  int v27; // r8d
  __int64 v28; // rsi
  __int64 v29; // rsi
  struct DXGDEVICE *v30; // rax
  const wchar_t *v31; // r9
  __int64 v32; // rax
  int v33; // edx
  bool v34; // zf
  int v35; // eax
  unsigned int v36; // ebx
  int v37; // edx
  __int64 v38; // rcx
  __int64 v39; // r8
  bool v40; // zf
  struct VIDSCH_SUBMIT_DATA_BASE *v41; // rcx
  int v42; // edx
  __int64 v43; // rcx
  __int64 v44; // r8
  unsigned int v45; // [rsp+60h] [rbp-788h] BYREF
  __int64 v46; // [rsp+68h] [rbp-780h]
  _DWORD *v47; // [rsp+70h] [rbp-778h]
  int *v48; // [rsp+78h] [rbp-770h]
  char v49; // [rsp+80h] [rbp-768h]
  int v50; // [rsp+88h] [rbp-760h] BYREF
  struct DXGDEVICE *v51; // [rsp+90h] [rbp-758h] BYREF
  _BYTE v52[8]; // [rsp+98h] [rbp-750h] BYREF
  struct VIDSCH_SUBMIT_DATA_BASE *v53[2]; // [rsp+A0h] [rbp-748h] BYREF
  _BYTE v54[24]; // [rsp+B0h] [rbp-738h] BYREF
  void *v55; // [rsp+C8h] [rbp-720h]
  __int128 v56; // [rsp+D0h] [rbp-718h] BYREF
  __int128 v57; // [rsp+E0h] [rbp-708h]
  struct DXGDEVICE *v58; // [rsp+F0h] [rbp-6F8h]
  _DWORD v59[10]; // [rsp+F8h] [rbp-6F0h] BYREF
  _BYTE v60[160]; // [rsp+120h] [rbp-6C8h] BYREF
  _BYTE v61[1520]; // [rsp+1C0h] [rbp-628h] BYREF

  v50 = -1073741823;
  Current = DXGPROCESS::GetCurrent();
  v51 = Current;
  if ( !Current )
  {
    CurrentProcess = PsGetCurrentProcess(v3, v2);
    v6 = -1073741811;
    WdLogSingleEntry2(2, -1073741811, CurrentProcess);
    WdLogGlobalForLineNumber = 1277;
    v9 = PsGetCurrentProcess(v8, v7);
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Presenting from unexpected process 0x%I64x 0x%I64x",
      -1073741811,
      v9,
      0,
      0,
      0);
    return v6;
  }
  memset(v61, 0, sizeof(v61));
  if ( (unsigned __int8)PsGetCurrentThreadPreviousMode() == 1 )
  {
    RtlCopyFromUser(v61, Src, 0x5F0u);
    Src = v61;
  }
  v55 = Src;
  if ( bTracingEnabled )
    v12 = Src + 8;
  else
    v12 = 0;
  v46 = 0;
  v45 = 2239;
  v48 = &v50;
  v49 = 1;
  v47 = v12;
  if ( (qword_1401604F0 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(&v50, EventProfilerEnter, v11, 2239);
  DXGETWPROFILER_BASE::PushProfilerEntry(&v45, 2239);
  v13 = *((_DWORD *)Src + 92);
  if ( v13 != 2 && v13 != 9 )
  {
    v6 = -1073741811;
    WdLogSingleEntry1(2, -1073741811);
    WdLogGlobalForLineNumber = 1312;
    v14 = L"Invalid PresentHistoryToken Model, returning 0x%I64x";
LABEL_25:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v14, -1073741811, 0, 0, 0, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v45);
    if ( v49 )
    {
      if ( v47 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
        McTemplateK0qqxxqq_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v18,
          v16,
          *v47,
          v47[14],
          *((_QWORD *)v47 + 10),
          *((_QWORD *)v47 + 11),
          v47[274],
          *v48);
    }
    else if ( v47 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
    {
      McTemplateK0qpqqqqpp_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v18,
        v16,
        *v47,
        *((_QWORD *)v47 + 1),
        v47[4],
        v47[21],
        v47[22],
        *v48,
        v47[5],
        v47[6]);
    }
    if ( (qword_1401604F0 & 2) == 0 )
      return v6;
    v17 = (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) == 0;
    goto LABEL_69;
  }
  if ( *((_DWORD *)Src + 378) )
  {
    v6 = -1073741811;
    WdLogSingleEntry1(2, -1073741811);
    WdLogGlobalForLineNumber = 1318;
    v14 = L"Reserved bits should not be set, returning 0x%I64x";
    goto LABEL_25;
  }
  v19 = *((unsigned int *)Src + 1);
  v51 = 0;
  DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)v52, *(_DWORD *)Src, Current, &v51);
  v20 = v51;
  if ( !v51 )
  {
    v6 = -1073741811;
    WdLogSingleEntry2(2, *(unsigned int *)Src, -1073741811);
    WdLogGlobalForLineNumber = 1334;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid hDevice (0x%I64x) specified, returning 0x%I64x",
      *(unsigned int *)Src,
      -1073741811,
      0,
      0,
      0);
LABEL_59:
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v52);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v45);
    v34 = v49 == 0;
LABEL_60:
    if ( v34 )
    {
      if ( v47 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
        McTemplateK0qpqqqqpp_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v33,
          v16,
          *v47,
          *((_QWORD *)v47 + 1),
          v47[4],
          v47[21],
          v47[22],
          *v48,
          v47[5],
          v47[6]);
    }
    else if ( v47 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    {
      McTemplateK0qqxxqq_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v33,
        v16,
        *v47,
        v47[14],
        *((_QWORD *)v47 + 10),
        *((_QWORD *)v47 + 11),
        v47[274],
        *v48);
    }
    if ( (qword_1401604F0 & 2) == 0 )
      return v6;
    v17 = (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) == 0;
LABEL_69:
    if ( !v17 )
      McTemplateK0q_EtwWriteTransfer(v15, EventProfilerExit, v16, v45);
    return v6;
  }
  v21 = *(_QWORD *)(*((_QWORD *)v51 + 2) + 16LL);
  if ( (*(_DWORD *)(v21 + 3104) & 8) != 0 )
  {
    WdLogSingleEntry1(2, *(unsigned int *)Src);
    WdLogGlobalForLineNumber = 1341;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Present is not supported on MCDM adapter device 0x%I64x",
      *(unsigned int *)Src,
      0,
      0,
      0,
      0);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v52);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v45);
    if ( v49 )
    {
      if ( v47 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
        McTemplateK0qqxxqq_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v22,
          v24,
          *v47,
          v47[14],
          *((_QWORD *)v47 + 10),
          *((_QWORD *)v47 + 11),
          v47[274],
          *v48);
    }
    else if ( v47 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
    {
      McTemplateK0qpqqqqpp_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v22,
        v24,
        *v47,
        *((_QWORD *)v47 + 1),
        v47[4],
        v47[21],
        v47[22],
        *v48,
        v47[5],
        v47[6]);
    }
    if ( (qword_1401604F0 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v23, EventProfilerExit, v24, v45);
    return (unsigned int)-1073741811;
  }
  Global = DXGGLOBAL::GetGlobal();
  DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v53, Global, 0);
  DXGSYNCOBJECTLOCK::AcquireShared((DXGSYNCOBJECTLOCK *)v53);
  v51 = (struct DXGPROCESS *)((char *)Current + 248);
  DXGPUSHLOCK::AcquireShared((struct DXGPROCESS *)((char *)Current + 248));
  if ( (((unsigned int)v19 >> 6) & 0xFFFFFF) < *((_DWORD *)Current + 74)
    && (v27 = *(_DWORD *)(*((_QWORD *)Current + 35) + 16LL * (((unsigned int)v19 >> 6) & 0xFFFFFF) + 8),
        (((unsigned int)v19 >> 25) & 0x60) == (*(_BYTE *)(*((_QWORD *)Current + 35)
                                                        + 16LL * (((unsigned int)v19 >> 6) & 0xFFFFFF)
                                                        + 8)
                                             & 0x60))
    && (v27 & 0x2000) == 0
    && (v27 & 0x1F) != 0 )
  {
    v29 = *((_QWORD *)Current + 35);
    if ( (*(_BYTE *)(v29 + 16LL * (((unsigned int)v19 >> 6) & 0xFFFFFF) + 8) & 0x1F) == 0xB )
    {
      v28 = *(_QWORD *)(v29 + 16LL * (((unsigned int)v19 >> 6) & 0xFFFFFF));
    }
    else
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 318;
      v28 = 0;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
    }
  }
  else
  {
    v28 = 0;
  }
  v30 = v51;
  _InterlockedDecrement((volatile signed __int32 *)v51 + 4);
  ExReleasePushLockSharedEx(v30, 0);
  KeLeaveCriticalRegion();
  if ( !v28 )
  {
    v6 = -1073741811;
    WdLogSingleEntry2(2, v19, -1073741811);
    WdLogGlobalForLineNumber = 1359;
    v31 = L"Invalid hSyncObj (0x%I64x) specified, returning 0x%I64x";
LABEL_58:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v31, v19, -1073741811, 0, 0, 0);
    DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v53);
    goto LABEL_59;
  }
  v32 = *(_QWORD *)(v28 + 32);
  if ( *(_DWORD *)(v32 + 420) != 7 )
  {
    v6 = -1073741811;
    WdLogSingleEntry2(2, v19, -1073741811);
    WdLogGlobalForLineNumber = 1366;
    v31 = L"hSyncObj (0x%I64x) is not a native fence, returning 0x%I64x";
    goto LABEL_58;
  }
  if ( *(_DWORD *)(v32 + 316) == 1 )
  {
    v6 = -1073741811;
    WdLogSingleEntry2(2, v19, -1073741811);
    WdLogGlobalForLineNumber = 1373;
    v31 = L"hSyncObj (0x%I64x) is INTRA_GPU type which is not allowed, returning 0x%I64x";
    goto LABEL_58;
  }
  DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v53);
  v51 = v20;
  DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(
    (DXGADAPTERSTOPRESETLOCKSHARED *)v54,
    (struct DXGADAPTER *)v21,
    1u);
  if ( *(_DWORD *)(v21 + 200) != 1 )
  {
    v6 = -1073741823;
    WdLogSingleEntry2(2, v21, -1073741823);
    WdLogGlobalForLineNumber = 1386;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"DXGADAPTER: 0x%I64x stopped, returning 0x%I64x",
      v21,
      -1073741823,
      0,
      0,
      0);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v54);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v51);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v52);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v45);
    v34 = v49 == 0;
    goto LABEL_60;
  }
  COREDEVICEACCESS::COREDEVICEACCESS(v60, v20, 2);
  v35 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v60, 0);
  v50 = v35;
  if ( v35 < 0 )
  {
    WdLogSingleEntry1(2, v35);
    WdLogGlobalForLineNumber = 1394;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to acquire CoreDeviceAccess, returning 0x%I64x",
      v50,
      0,
      0,
      0,
      0);
    v36 = v50;
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v60);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v54);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v51);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v52);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v45);
    v40 = v49 == 0;
LABEL_100:
    if ( v40 )
    {
      if ( v47 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
        McTemplateK0qpqqqqpp_EtwWriteTransfer(
          (unsigned int)&DxgkControlGuid_Context,
          v37,
          v39,
          *v47,
          *((_QWORD *)v47 + 1),
          v47[4],
          v47[21],
          v47[22],
          *v48,
          v47[5],
          v47[6]);
    }
    else if ( v47 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    {
      McTemplateK0qqxxqq_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v37,
        v39,
        *v47,
        v47[14],
        *((_QWORD *)v47 + 10),
        *((_QWORD *)v47 + 11),
        v47[274],
        *v48);
    }
    if ( (qword_1401604F0 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v38, EventProfilerExit, v39, v45);
    return v36;
  }
  v6 = SubmitPresentHistoryTokenPreparation(
         (struct DXGADAPTERSTOPRESETLOCKSHARED *)v54,
         (struct COREDEVICEACCESS *)v60,
         (struct DXGADAPTER *)v21,
         (struct _D3DKMT_PRESENTHISTORYTOKEN *)(Src + 368),
         *((void **)Src + 45),
         (*((_DWORD *)Src + 24) & 0x10) != 0);
  v50 = v6;
  if ( (v6 & 0x80000000) != 0 )
  {
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v60);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v54);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v51);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v52);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v45);
    v34 = v49 == 0;
    goto LABEL_60;
  }
  TOKEN_BINDING_GUARD::TOKEN_BINDING_GUARD(
    (TOKEN_BINDING_GUARD *)v59,
    (struct _D3DKMT_PRESENTHISTORYTOKEN *)(Src + 368),
    (struct DXGADAPTERSTOPRESETLOCKSHARED *)v54,
    (struct COREDEVICEACCESS *)v60);
  CVidSchSubmitData::CVidSchSubmitData((CVidSchSubmitData *)v53, *(struct ADAPTER_RENDER **)(v21 + 3256), 1);
  v41 = v53[0];
  if ( v53[0] )
  {
    *(_DWORD *)v53[0] = *(_DWORD *)v53[0] & 0xFFF9FFDF | 0x40020;
    *((_QWORD *)v41 + 59) = *((_QWORD *)Src + 188);
    v56 = 0;
    v57 = 0;
    v58 = 0;
    LODWORD(v56) = v19;
    DWORD1(v56) = *((_DWORD *)Src + 7);
    DWORD2(v56) = *((_DWORD *)Src + 370);
    *(_QWORD *)&v57 = *((_QWORD *)Src + 186);
    *((_QWORD *)&v57 + 1) = v21;
    v58 = v20;
    v36 = SubmitPresentHistoryToken(
            (const struct _D3DKMT_PRESENTHISTORYTOKEN *)(Src + 368),
            (struct COREDEVICEACCESS *)v60,
            (struct DXGADAPTERSTOPRESETLOCKSHARED *)v54,
            0,
            1,
            0,
            0,
            v41,
            0,
            (struct _PRESENT_REDIRECTED_PARAMS *)&v56,
            0);
    v50 = v36;
    v59[0] = v36;
    CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v53);
    TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD((TOKEN_BINDING_GUARD *)v59);
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v60);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v54);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v51);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v52);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v45);
    v40 = v49 == 0;
    goto LABEL_100;
  }
  WdLogSingleEntry0(6);
  WdLogGlobalForLineNumber = 1418;
  DxgkLogInternalTriageEvent(0, 262145, -1, (unsigned int)L"Failed to allocate VidSchSubmitData", 1418, 0, 0, 0, 0);
  CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v53);
  TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD((TOKEN_BINDING_GUARD *)v59);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v60);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v54);
  ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v51);
  ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v52);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v45);
  if ( v49 )
  {
    if ( v47 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
      McTemplateK0qqxxqq_EtwWriteTransfer(
        (unsigned int)&DxgkControlGuid_Context,
        v42,
        v44,
        *v47,
        v47[14],
        *((_QWORD *)v47 + 10),
        *((_QWORD *)v47 + 11),
        v47[274],
        *v48);
  }
  else if ( v47 && (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
  {
    McTemplateK0qpqqqqpp_EtwWriteTransfer(
      (unsigned int)&DxgkControlGuid_Context,
      v42,
      v44,
      *v47,
      *((_QWORD *)v47 + 1),
      v47[4],
      v47[21],
      v47[22],
      *v48,
      v47[5],
      v47[6]);
  }
  if ( (qword_1401604F0 & 2) != 0 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v43, EventProfilerExit, v44, v45);
  return 3221225495LL;
}

```

## disassembly

```asm
0x140256830  mov     [rsp+arg_8], rbx
0x140256835  mov     [rsp+arg_10], rsi
0x14025683a  push    rdi
0x14025683b  push    r12
0x14025683d  push    r13
0x14025683f  push    r14
0x140256841  push    r15
0x140256843  sub     rsp, 7C0h
0x14025684a  mov     rax, cs:__security_cookie
0x140256851  xor     rax, rsp
0x140256854  mov     [rsp+7E8h+var_38], rax
0x14025685c  mov     rbx, rcx
0x14025685f  mov     [rsp+7E8h+var_760], 0C0000001h
0x14025686a  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14025686f  mov     rsi, rax
0x140256872  mov     [rsp+7E8h+var_758], rax
0x14025687a  xor     r14d, r14d
0x14025687d  test    rax, rax
0x140256880  jnz     short loc_1402568F8
0x140256882  call    cs:__imp_PsGetCurrentProcess
0x140256889  nop     dword ptr [rax+rax+00h]
0x14025688e  mov     r8, rax
0x140256891  mov     rsi, 0FFFFFFFFC000000Dh
0x140256898  mov     rdx, rsi
0x14025689b  lea     ecx, [r14+2]
0x14025689f  call    cs:__imp_WdLogSingleEntry2
0x1402568a6  nop     dword ptr [rax+rax+00h]
0x1402568ab  mov     cs:WdLogGlobalForLineNumber, 4FDh
0x1402568b5  call    cs:__imp_PsGetCurrentProcess
0x1402568bc  nop     dword ptr [rax+rax+00h]
0x1402568c1  mov     [rsp+7E8h+var_7A8], r14
0x1402568c6  mov     [rsp+7E8h+var_7B0], r14
0x1402568cb  mov     [rsp+7E8h+var_7B8], r14
0x1402568d0  mov     [rsp+7E8h+var_7C0], rax
0x1402568d5  mov     [rsp+7E8h+var_7C8], rsi
0x1402568da  lea     r9, aPresentingFrom; "Presenting from unexpected process 0x%I"...
0x1402568e1  or      r8d, 0FFFFFFFFh
0x1402568e5  mov     edx, 40000h
0x1402568ea  xor     ecx, ecx
0x1402568ec  call    DxgkLogInternalTriageEvent
0x1402568f1  mov     eax, esi
0x1402568f3  jmp     loc_140257712
0x1402568f8  mov     edi, 5F0h
0x1402568fd  mov     r8d, edi; Size
0x140256900  xor     edx, edx; Val
0x140256902  lea     rcx, [rsp+7E8h+var_628]; void *
0x14025690a  call    memset
0x14025690f  nop
0x140256910  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x140256917  nop     dword ptr [rax+rax+00h]
0x14025691c  mov     r12d, 1
0x140256922  cmp     al, r12b
0x140256925  jnz     short loc_140256942
0x140256927  mov     r8d, edi; Size
0x14025692a  mov     rdx, rbx; Src
0x14025692d  lea     rcx, [rsp+7E8h+var_628]; void *
0x140256935  call    RtlCopyFromUser
0x14025693a  lea     rbx, [rsp+7E8h+var_628]
0x140256942  mov     [rsp+7E8h+var_720], rbx
0x14025694a  cmp     cs:bTracingEnabled, 0
0x140256951  jz      short loc_14025695C
0x140256953  lea     rax, [rbx+8]
0x140256957  mov     r15, rax
0x14025695a  jmp     short loc_140256963
0x14025695c  mov     rax, r14
0x14025695f  lea     r15, [rbx+8]
0x140256963  mov     [rsp+7E8h+var_780], r14
0x140256968  mov     r13d, 8BFh
0x14025696e  mov     [rsp+7E8h+var_788], r13d
0x140256973  lea     rcx, [rsp+7E8h+var_760]
0x14025697b  mov     [rsp+7E8h+var_770], rcx
0x140256980  mov     [rsp+7E8h+var_768], r12b
0x140256988  mov     [rsp+7E8h+var_778], rax
0x14025698d  mov     rax, cs:qword_1401604F0
0x140256994  mov     edi, 2
0x140256999  test    dil, al
0x14025699c  jz      short loc_1402569B6
0x14025699e  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r12b
0x1402569a5  jz      short loc_1402569B6
0x1402569a7  mov     r9d, r13d
0x1402569aa  lea     rdx, EventProfilerEnter
0x1402569b1  call    McTemplateK0q_EtwWriteTransfer
0x1402569b6  mov     edx, r13d
0x1402569b9  lea     rcx, [rsp+7E8h+var_788]
0x1402569be  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1402569c3  mov     eax, [r15+168h]
0x1402569ca  cmp     eax, edi
0x1402569cc  jz      loc_140256AD9
0x1402569d2  cmp     eax, 9
0x1402569d5  jz      loc_140256AD9
0x1402569db  mov     rsi, 0FFFFFFFFC000000Dh
0x1402569e2  mov     rdx, rsi
0x1402569e5  mov     ecx, edi
0x1402569e7  call    cs:__imp_WdLogSingleEntry1
0x1402569ee  nop     dword ptr [rax+rax+00h]
0x1402569f3  mov     cs:WdLogGlobalForLineNumber, 520h
0x1402569fd  lea     r9, aInvalidPresent_0; "Invalid PresentHistoryToken Model, retu"...
0x140256a04  jmp     loc_140256B0B
0x140256a09  test    r9, r9
0x140256a0c  jz      loc_140256ABD
0x140256a12  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, r12b
0x140256a19  jz      loc_140256ABD
0x140256a1f  mov     rax, [rsp+7E8h+var_770]
0x140256a24  mov     ecx, [rax]
0x140256a26  mov     dword ptr [rsp+7E8h+var_7A8], ecx
0x140256a2a  mov     eax, [r9+448h]
0x140256a31  mov     dword ptr [rsp+7E8h+var_7B0], eax
0x140256a35  mov     rax, [r9+58h]
0x140256a39  mov     [rsp+7E8h+var_7B8], rax
0x140256a3e  mov     rax, [r9+50h]
0x140256a42  mov     [rsp+7E8h+var_7C0], rax
0x140256a47  mov     eax, [r9+38h]
0x140256a4b  mov     dword ptr [rsp+7E8h+var_7C8], eax
0x140256a4f  mov     r9d, [r9]
0x140256a52  lea     rcx, DxgkControlGuid_Context
0x140256a59  call    McTemplateK0qqxxqq_EtwWriteTransfer
0x140256a5e  jmp     short loc_140256ABD
0x140256a60  test    r9, r9
0x140256a63  jz      short loc_140256ABD
0x140256a65  mov     rax, cs:Microsoft_Windows_DxgKrnlEnableBits
0x140256a6c  test    al, al
0x140256a6e  jns     short loc_140256ABD
0x140256a70  mov     eax, [r9+18h]
0x140256a74  mov     ecx, [r9+14h]
0x140256a78  mov     [rsp+7E8h+var_798], rax
0x140256a7d  mov     [rsp+7E8h+var_7A0], rcx
0x140256a82  mov     rax, [rsp+7E8h+var_770]
0x140256a87  mov     ecx, [rax]
0x140256a89  mov     dword ptr [rsp+7E8h+var_7A8], ecx
0x140256a8d  mov     eax, [r9+58h]
0x140256a91  mov     dword ptr [rsp+7E8h+var_7B0], eax
0x140256a95  mov     eax, [r9+54h]
0x140256a99  mov     dword ptr [rsp+7E8h+var_7B8], eax
0x140256a9d  mov     eax, [r9+10h]
0x140256aa1  mov     dword ptr [rsp+7E8h+var_7C0], eax
0x140256aa5  mov     rax, [r9+8]
0x140256aa9  mov     [rsp+7E8h+var_7C8], rax
0x140256aae  mov     r9d, [r9]
0x140256ab1  lea     rcx, DxgkControlGuid_Context
0x140256ab8  call    McTemplateK0qpqqqqpp_EtwWriteTransfer
0x140256abd  mov     rax, cs:qword_1401604F0
0x140256ac4  test    dil, al
0x140256ac7  jz      loc_1402568F1
0x140256acd  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r12b
0x140256ad4  jmp     loc_14025703F
0x140256ad9  cmp     [rbx+5E8h], r14d
0x140256ae0  jz      short loc_140256B56
0x140256ae2  mov     rsi, 0FFFFFFFFC000000Dh
0x140256ae9  mov     rdx, rsi
0x140256aec  mov     ecx, edi
0x140256aee  call    cs:__imp_WdLogSingleEntry1
0x140256af5  nop     dword ptr [rax+rax+00h]
0x140256afa  mov     cs:WdLogGlobalForLineNumber, 526h
0x140256b04  lea     r9, aReservedBitsSh; "Reserved bits should not be set, return"...
0x140256b0b  mov     [rsp+7E8h+var_7A8], r14
0x140256b10  mov     [rsp+7E8h+var_7B0], r14
0x140256b15  mov     [rsp+7E8h+var_7B8], r14
0x140256b1a  mov     [rsp+7E8h+var_7C0], r14
0x140256b1f  mov     [rsp+7E8h+var_7C8], rsi
0x140256b24  or      r8d, 0FFFFFFFFh
0x140256b28  mov     edx, 40000h
0x140256b2d  xor     ecx, ecx
0x140256b2f  call    DxgkLogInternalTriageEvent
0x140256b34  lea     rcx, [rsp+7E8h+var_788]; this
0x140256b39  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140256b3e  cmp     [rsp+7E8h+var_768], r14b
0x140256b46  mov     r9, [rsp+7E8h+var_778]
0x140256b4b  jnz     loc_140256A09
0x140256b51  jmp     loc_140256A60
0x140256b56  mov     r12d, [rbx+4]
0x140256b5a  mov     [rsp+7E8h+var_758], r14
0x140256b62  lea     r9, [rsp+7E8h+var_758]; struct DXGDEVICE **
0x140256b6a  mov     r8, rsi; struct DXGPROCESS *
0x140256b6d  mov     edx, [rbx]; unsigned int
0x140256b6f  lea     rcx, [rsp+7E8h+var_750]; this
0x140256b77  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x140256b7c  mov     r13, [rsp+7E8h+var_758]
0x140256b84  test    r13, r13
0x140256b87  jnz     short loc_140256BE4
0x140256b89  mov     edx, [rbx]
0x140256b8b  mov     rsi, 0FFFFFFFFC000000Dh
0x140256b92  mov     r8, rsi
0x140256b95  mov     ecx, edi
0x140256b97  call    cs:__imp_WdLogSingleEntry2
0x140256b9e  nop     dword ptr [rax+rax+00h]
0x140256ba3  mov     cs:WdLogGlobalForLineNumber, 536h
0x140256bad  mov     eax, [rbx]
0x140256baf  mov     [rsp+7E8h+var_7A8], r14
0x140256bb4  mov     [rsp+7E8h+var_7B0], r14
0x140256bb9  mov     [rsp+7E8h+var_7B8], r14
0x140256bbe  mov     [rsp+7E8h+var_7C0], rsi
0x140256bc3  mov     [rsp+7E8h+var_7C8], rax
0x140256bc8  lea     r9, aInvalidHdevice_2; "Invalid hDevice (0x%I64x) specified, re"...
0x140256bcf  or      r8d, 0FFFFFFFFh
0x140256bd3  mov     edx, 40000h
0x140256bd8  xor     ecx, ecx
0x140256bda  call    DxgkLogInternalTriageEvent
0x140256bdf  jmp     loc_140256F4E
0x140256be4  mov     rax, [r13+10h]
0x140256be8  mov     r14, [rax+10h]
0x140256bec  mov     eax, [r14+0C20h]
0x140256bf3  shr     eax, 3
0x140256bf6  test    al, 1
0x140256bf8  jz      loc_140256D57
0x140256bfe  mov     edx, [rbx]
0x140256c00  mov     ecx, edi
0x140256c02  call    cs:__imp_WdLogSingleEntry1
0x140256c09  nop     dword ptr [rax+rax+00h]
0x140256c0e  mov     cs:WdLogGlobalForLineNumber, 53Dh
0x140256c18  mov     eax, [rbx]
0x140256c1a  xor     ebx, ebx
0x140256c1c  mov     [rsp+7E8h+var_7A8], rbx
0x140256c21  mov     [rsp+7E8h+var_7B0], rbx
0x140256c26  mov     [rsp+7E8h+var_7B8], rbx
0x140256c2b  mov     [rsp+7E8h+var_7C0], rbx
0x140256c30  mov     [rsp+7E8h+var_7C8], rax
0x140256c35  lea     r9, aPresentIsNotSu; "Present is not supported on MCDM adapte"...
0x140256c3c  or      r8d, 0FFFFFFFFh
0x140256c40  mov     edx, 40000h
0x140256c45  xor     ecx, ecx
0x140256c47  call    DxgkLogInternalTriageEvent
0x140256c4c  lea     rcx, [rsp+7E8h+var_750]; this
0x140256c54  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x140256c59  lea     rcx, [rsp+7E8h+var_788]; this
0x140256c5e  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140256c63  mov     r9, [rsp+7E8h+var_778]
0x140256c68  cmp     [rsp+7E8h+var_768], bl
0x140256c6f  jz      short loc_140256CC8
0x140256c71  test    r9, r9
0x140256c74  jz      loc_140256D25
0x140256c7a  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x140256c81  jz      loc_140256D25
0x140256c87  mov     rax, [rsp+7E8h+var_770]
0x140256c8c  mov     ecx, [rax]
0x140256c8e  mov     dword ptr [rsp+7E8h+var_7A8], ecx
0x140256c92  mov     eax, [r9+448h]
0x140256c99  mov     dword ptr [rsp+7E8h+var_7B0], eax
0x140256c9d  mov     rax, [r9+58h]
0x140256ca1  mov     [rsp+7E8h+var_7B8], rax
0x140256ca6  mov     rax, [r9+50h]
0x140256caa  mov     [rsp+7E8h+var_7C0], rax
0x140256caf  mov     eax, [r9+38h]
0x140256cb3  mov     dword ptr [rsp+7E8h+var_7C8], eax
0x140256cb7  mov     r9d, [r9]
0x140256cba  lea     rcx, DxgkControlGuid_Context
0x140256cc1  call    McTemplateK0qqxxqq_EtwWriteTransfer
0x140256cc6  jmp     short loc_140256D25
0x140256cc8  test    r9, r9
0x140256ccb  jz      short loc_140256D25
0x140256ccd  mov     rax, cs:Microsoft_Windows_DxgKrnlEnableBits
0x140256cd4  test    al, al
0x140256cd6  jns     short loc_140256D25
0x140256cd8  mov     eax, [r9+18h]
0x140256cdc  mov     ecx, [r9+14h]
0x140256ce0  mov     [rsp+7E8h+var_798], rax
0x140256ce5  mov     [rsp+7E8h+var_7A0], rcx
0x140256cea  mov     rax, [rsp+7E8h+var_770]
0x140256cef  mov     ecx, [rax]
0x140256cf1  mov     dword ptr [rsp+7E8h+var_7A8], ecx
0x140256cf5  mov     eax, [r9+58h]
0x140256cf9  mov     dword ptr [rsp+7E8h+var_7B0], eax
0x140256cfd  mov     eax, [r9+54h]
0x140256d01  mov     dword ptr [rsp+7E8h+var_7B8], eax
0x140256d05  mov     eax, [r9+10h]
0x140256d09  mov     dword ptr [rsp+7E8h+var_7C0], eax
0x140256d0d  mov     rax, [r9+8]
0x140256d11  mov     [rsp+7E8h+var_7C8], rax
0x140256d16  mov     r9d, [r9]
0x140256d19  lea     rcx, DxgkControlGuid_Context
0x140256d20  call    McTemplateK0qpqqqqpp_EtwWriteTransfer
0x140256d25  mov     rax, cs:qword_1401604F0
0x140256d2c  test    dil, al
0x140256d2f  jz      short loc_140256D4B
0x140256d31  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x140256d38  jz      short loc_140256D4B
0x140256d3a  mov     r9d, [rsp+7E8h+var_788]
0x140256d3f  lea     rdx, EventProfilerExit
0x140256d46  call    McTemplateK0q_EtwWriteTransfer
0x140256d4b  mov     rsi, 0FFFFFFFFC000000Dh
0x140256d52  jmp     loc_1402568F1
0x140256d57  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140256d5c  mov     rdx, rax; struct DXGGLOBAL *
0x140256d5f  xor     r8d, r8d; bool
0x140256d62  lea     rcx, [rsp+7E8h+var_748]; this
0x140256d6a  call    ??0DXGSYNCOBJECTLOCK@@QEAA@QEAVDXGGLOBAL@@_N@Z; DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK(DXGGLOBAL * const,bool)
0x140256d6f  lea     rcx, [rsp+7E8h+var_748]; this
0x140256d77  call    ?AcquireShared@DXGSYNCOBJECTLOCK@@QEAAXXZ; DXGSYNCOBJECTLOCK::AcquireShared(void)
0x140256d7c  lea     rcx, [rsi+0F8h]; this
0x140256d83  mov     [rsp+7E8h+var_758], rcx
0x140256d8b  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x140256d90  mov     eax, r12d
0x140256d93  shr     eax, 6
0x140256d96  and     eax, 0FFFFFFh
0x140256d9b  mov     edx, eax
0x140256d9d  add     rdx, rdx
0x140256da0  cmp     eax, [rsi+128h]
0x140256da6  jb      short loc_140256DAC
0x140256da8  xor     al, al
0x140256daa  jmp     short loc_140256DDA
0x140256dac  mov     rax, [rsi+118h]
  ... truncated ...
```
