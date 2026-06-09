# DxgkCreateProtectedSession

- ea: `0x140259030`
- end: `0x140259e48`
- name: `DxgkCreateProtectedSession`
- size: `3608`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012380`
- `0x140012b14`
- `0x140013860`
- `0x140015970`
- `0x140017fb8`
- `0x14001b890`
- `0x14001bd70`
- `0x14001cec0`
- `0x14001d070`
- `0x14001d0e4`
- `0x14001f120`
- `0x140030654`
- `0x140030820`
- `0x140030860`
- `0x140033bd4`
- `0x140036cd8`
- `0x14004885c`
- `0x14004fc88`
- `0x1400670a4`
- `0x1400a0100`
- `0x1401c8758`
- `0x1401e5360`
- `0x1402584ac`
- `0x140258b58`
- `0x140259030`
- `0x140322090`
- `0x140323854`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140259761`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140259cc0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140259761`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140259cc0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140259cb4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140259cb4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140259755`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140259755`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14025906f`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14025906f`
- `watchdog!WdLogSingleEntry2` at `0x140259322`
- `watchdog!WdLogSingleEntry2` at `0x1402593ad`
- `watchdog!WdLogSingleEntry2` at `0x14025941c`
- `watchdog!WdLogSingleEntry2` at `0x140259478`
- `watchdog!WdLogSingleEntry2` at `0x1402594e4`
- `watchdog!WdLogSingleEntry2` at `0x1402595f8`
- `watchdog!WdLogSingleEntry2` at `0x140259787`
- `watchdog!WdLogSingleEntry2` at `0x140259878`
- `watchdog!WdLogSingleEntry2` at `0x1402598b4`
- `watchdog!WdLogSingleEntry2` at `0x140259d11`
- `watchdog!WdLogSingleEntry2` at `0x140259322`
- `watchdog!WdLogSingleEntry2` at `0x1402593ad`
- `watchdog!WdLogSingleEntry2` at `0x14025941c`
- `watchdog!WdLogSingleEntry2` at `0x140259478`
- `watchdog!WdLogSingleEntry2` at `0x1402594e4`
- `watchdog!WdLogSingleEntry2` at `0x1402595f8`
- `watchdog!WdLogSingleEntry2` at `0x140259787`
- `watchdog!WdLogSingleEntry2` at `0x140259878`
- `watchdog!WdLogSingleEntry2` at `0x1402598b4`
- `watchdog!WdLogSingleEntry2` at `0x140259d11`
- `watchdog!WdLogSingleEntry3` at `0x1402591fe`
- `watchdog!WdLogSingleEntry3` at `0x140259232`
- `watchdog!WdLogSingleEntry3` at `0x14025927d`
- `watchdog!WdLogSingleEntry3` at `0x1402592ab`
- `watchdog!WdLogSingleEntry3` at `0x1402597fc`
- `watchdog!WdLogSingleEntry3` at `0x1402591fe`
- `watchdog!WdLogSingleEntry3` at `0x140259232`
- `watchdog!WdLogSingleEntry3` at `0x14025927d`
- `watchdog!WdLogSingleEntry3` at `0x1402592ab`
- `watchdog!WdLogSingleEntry3` at `0x1402597fc`
- `watchdog!WdLogSingleEntry0` at `0x140259087`
- `watchdog!WdLogSingleEntry0` at `0x1402596f8`
- `watchdog!WdLogSingleEntry0` at `0x140259967`
- `watchdog!WdLogSingleEntry0` at `0x1402599e7`
- `watchdog!WdLogSingleEntry0` at `0x140259a45`
- `watchdog!WdLogSingleEntry0` at `0x140259a95`
- `watchdog!WdLogSingleEntry0` at `0x140259b0b`
- `watchdog!WdLogSingleEntry0` at `0x140259b5a`
- `watchdog!WdLogSingleEntry0` at `0x140259c5a`
- `watchdog!WdLogSingleEntry0` at `0x140259087`
- `watchdog!WdLogSingleEntry0` at `0x1402596f8`
- `watchdog!WdLogSingleEntry0` at `0x140259967`
- `watchdog!WdLogSingleEntry0` at `0x1402599e7`
- `watchdog!WdLogSingleEntry0` at `0x140259a45`
- `watchdog!WdLogSingleEntry0` at `0x140259a95`
- `watchdog!WdLogSingleEntry0` at `0x140259b0b`
- `watchdog!WdLogSingleEntry0` at `0x140259b5a`
- `watchdog!WdLogSingleEntry0` at `0x140259c5a`
- `watchdog!WdLogSingleEntry1` at `0x14025914d`
- `watchdog!WdLogSingleEntry1` at `0x140259dd4`
- `watchdog!WdLogSingleEntry1` at `0x14025914d`
- `watchdog!WdLogSingleEntry1` at `0x140259dd4`

## string_xrefs

- `0x1402590b7`: `PsGetCurrentThreadPreviousMode() == UserMode`
- `0x1402598e7`: `Not NT shared Monitored/Native Fence: Protected session's sync object 0x%I64x does not use NT security sharing. Returning 0x%I64x.`
- `0x140259b8a`: `KMCreateProtectedSession.hHandle`

## pseudocode

```c
__int64 __fastcall DxgkCreateProtectedSession(char *Src)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  struct DXGPROCESS *Current; // rsi
  unsigned int v5; // eax
  struct DXGDEVICE *v6; // r14
  volatile signed __int32 *v7; // r15
  int v8; // esi
  __int64 v9; // rax
  const wchar_t *v10; // r9
  struct DXGDEVICE *v11; // r13
  __int64 v12; // rcx
  __int64 v13; // r8
  struct DXGGLOBAL *v15; // rax
  unsigned int v16; // esi
  __int64 v17; // rdx
  int v19; // ecx
  __int64 v20; // rsi
  __int64 v21; // rsi
  DXGPUSHLOCK *v22; // rax
  __int64 v23; // rsi
  const wchar_t *v24; // r9
  struct DXGDEVICE *v25; // r8
  unsigned __int64 v26; // rsi
  DXGPUSHLOCK *v27; // r15
  __int64 v28; // rax
  struct DXGPROCESS *v29; // r14
  __int64 v30; // r8
  __int64 v31; // rsi
  __int64 v32; // rcx
  __int64 v33; // r8
  DXGGLOBAL *Global; // rax
  __int64 v35; // rcx
  __int64 v36; // r8
  char v37[8]; // [rsp+50h] [rbp-188h] BYREF
  struct DXGDEVICE *v38; // [rsp+58h] [rbp-180h] BYREF
  unsigned int v39; // [rsp+60h] [rbp-178h] BYREF
  __int64 v40; // [rsp+68h] [rbp-170h]
  char v41; // [rsp+70h] [rbp-168h]
  void *Srca[2]; // [rsp+78h] [rbp-160h] BYREF
  size_t Size[2]; // [rsp+88h] [rbp-150h]
  size_t v44; // [rsp+98h] [rbp-140h] BYREF
  DXGPROTECTEDSESSION *v45; // [rsp+A0h] [rbp-138h] BYREF
  struct DXGPROCESS *v46; // [rsp+A8h] [rbp-130h]
  void *v47; // [rsp+B0h] [rbp-128h] BYREF
  void *v48; // [rsp+B8h] [rbp-120h] BYREF
  _BYTE v49[16]; // [rsp+C0h] [rbp-118h] BYREF
  _BYTE v50[16]; // [rsp+D0h] [rbp-108h] BYREF
  DXGPUSHLOCK *v51; // [rsp+E0h] [rbp-F8h]
  __int64 v52; // [rsp+E8h] [rbp-F0h]
  char *v53; // [rsp+F0h] [rbp-E8h]
  char *v54; // [rsp+F8h] [rbp-E0h]
  _BYTE v55[160]; // [rsp+100h] [rbp-D8h] BYREF

  v53 = Src;
  v54 = Src;
  if ( (unsigned __int8)PsGetCurrentThreadPreviousMode() != 1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 57;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"PsGetCurrentThreadPreviousMode() == UserMode",
      57,
      0,
      0,
      0,
      0);
  }
  v39 = -1;
  v40 = 0;
  if ( (qword_14015C500 & 2) != 0 )
  {
    v41 = 1;
    v39 = 2148;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v2, EventProfilerEnter, v3, 2148);
  }
  else
  {
    v41 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v39, 2148);
  Current = DXGPROCESS::GetCurrent();
  v46 = Current;
  if ( !Current )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 66;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid process context, returning 0x%I64x",
      -1073741811,
      0,
      0,
      0,
      0);
LABEL_34:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v39);
    if ( v41 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v12, EventProfilerExit, v13, v39);
    }
    return 3221225485LL;
  }
  *(_OWORD *)Srca = 0;
  *(_OWORD *)Size = 0;
  v44 = 0;
  RtlCopyFromUser(Srca, Src, 0x28u);
  HIDWORD(v44) = 0;
  if ( !Srca[1] )
  {
    if ( !LODWORD(Size[0]) )
      goto LABEL_14;
LABEL_13:
    WdLogSingleEntry3(3, Srca[1], LODWORD(Size[0]), -1073741811);
    WdLogGlobalForLineNumber = 94;
    goto LABEL_34;
  }
  if ( !LODWORD(Size[0]) )
    goto LABEL_13;
LABEL_14:
  if ( LODWORD(Size[0]) > 0x2000000 )
  {
    WdLogSingleEntry3(3, LODWORD(Size[0]), 0x2000000, -1073741811);
    WdLogGlobalForLineNumber = 103;
    goto LABEL_34;
  }
  v5 = v44;
  if ( !Size[1] )
  {
    if ( !(_DWORD)v44 )
      goto LABEL_21;
LABEL_20:
    WdLogSingleEntry3(3, Size[1], (unsigned int)v44, -1073741811);
    WdLogGlobalForLineNumber = 113;
    goto LABEL_34;
  }
  if ( !(_DWORD)v44 )
    goto LABEL_20;
LABEL_21:
  if ( (unsigned int)v44 > 0x2000000 )
  {
    WdLogSingleEntry3(3, (unsigned int)v44, 0x2000000, -1073741811);
    WdLogGlobalForLineNumber = 122;
    goto LABEL_34;
  }
  v47 = 0;
  v48 = 0;
  v6 = 0;
  v38 = 0;
  v7 = 0;
  v45 = 0;
  if ( LODWORD(Size[0]) )
  {
    v47 = (void *)operator new[](LODWORD(Size[0]), 1265072196, 256);
    if ( !v47 )
    {
      v8 = -1073741801;
      WdLogSingleEntry2(6, LODWORD(Size[0]));
      WdLogGlobalForLineNumber = 144;
      v9 = LODWORD(Size[0]);
      v10 = L"Out of memory allocating 0x%I64x bytes for private driver data, returning 0x%I64x";
LABEL_26:
      DxgkLogInternalTriageEvent(0, 262145, -1, (_DWORD)v10, v9, -1073741801, 0, 0, 0);
LABEL_87:
      if ( v7 )
      {
        DXGPROTECTEDSESSION::DestroyProtectedSession((struct DXGPROTECTEDSESSION *)v7, HIDWORD(v44));
        HIDWORD(v44) = 0;
      }
      if ( v6 )
      {
        Global = DXGGLOBAL::GetGlobal();
        DXGGLOBAL::DestroySyncObject(Global, v6, 0, 0);
      }
      if ( v47 )
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v47);
      if ( v48 )
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v48);
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v39);
      if ( v41 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v35, EventProfilerExit, v36, v39);
      return (unsigned int)v8;
    }
    RtlCopyFromUser(v47, Srca[1], LODWORD(Size[0]));
    v5 = v44;
  }
  if ( v5 )
  {
    v48 = (void *)operator new[](v5, 1265072196, 256);
    if ( !v48 )
    {
      v8 = -1073741801;
      WdLogSingleEntry2(6, (unsigned int)v44);
      WdLogGlobalForLineNumber = 172;
      v9 = (unsigned int)v44;
      v10 = L"Out of memory allocating 0x%I64x bytes for private runtime data, returning 0x%I64x";
      goto LABEL_26;
    }
    RtlCopyFromUser(v48, (void *)Size[1], (unsigned int)v44);
  }
  v38 = 0;
  DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)v37, (unsigned int)Srca[0], Current, &v38);
  v11 = v38;
  if ( !v38 )
  {
    WdLogSingleEntry2(2, LODWORD(Srca[0]));
    WdLogGlobalForLineNumber = 200;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid hDevice (0x%I64x) specified, returning 0x%I64x",
      LODWORD(Srca[0]),
      -1073741811,
      0,
      0,
      0);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v37);
    goto LABEL_34;
  }
  DXGDEVICEACCESSLOCKSHARED::DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)v49, v38);
  COREDEVICEACCESS::COREDEVICEACCESS(v55, v11, 1);
  v8 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v55, 0);
  if ( v8 < 0 )
  {
LABEL_39:
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v55);
    DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)v49);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v37);
    goto LABEL_87;
  }
  v52 = *((_QWORD *)v11 + 237);
  if ( !v52 )
  {
    v8 = -1073741637;
    WdLogSingleEntry2(2, v11);
    WdLogGlobalForLineNumber = 218;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"function is called on a render only device (0x%I64x), returning 0x%I64x.",
      (__int64)v11,
      -1073741637,
      0,
      0,
      0);
    goto LABEL_39;
  }
  v15 = DXGGLOBAL::GetGlobal();
  DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v50, v15, 0);
  DXGSYNCOBJECTLOCK::AcquireShared((DXGSYNCOBJECTLOCK *)v50);
  v16 = HIDWORD(Srca[0]);
  v51 = (struct DXGPROCESS *)((char *)v46 + 248);
  DXGPUSHLOCK::AcquireShared((struct DXGPROCESS *)((char *)v46 + 248));
  v17 = 2LL * ((v16 >> 6) & 0xFFFFFF);
  if ( !(((v16 >> 6) & 0xFFFFFF) < *((_DWORD *)v46 + 74)
      && (v19 = *(_DWORD *)(*((_QWORD *)v46 + 35) + 16LL * ((v16 >> 6) & 0xFFFFFF) + 8),
          ((v16 >> 25) & 0x60) == (*(_BYTE *)(*((_QWORD *)v46 + 35) + 16LL * ((v16 >> 6) & 0xFFFFFF) + 8) & 0x60))
      && (v19 & 0x2000) == 0
      && (v19 & 0x1F) != 0) )
    goto LABEL_48;
  v21 = *((_QWORD *)v46 + 35);
  if ( (*(_BYTE *)(v21 + 8 * v17 + 8) & 0x1F) != 0xB )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 318;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
LABEL_48:
    v20 = 0;
    goto LABEL_52;
  }
  v20 = *(_QWORD *)(v21 + 8 * v17);
LABEL_52:
  v22 = v51;
  _InterlockedDecrement((volatile signed __int32 *)v51 + 4);
  ExReleasePushLockSharedEx(v22, 0);
  KeLeaveCriticalRegion();
  if ( !v20 )
  {
    v23 = (__int64)v46;
    WdLogSingleEntry2(2, v46);
    WdLogGlobalForLineNumber = 240;
    v24 = L"Invalid sync object, process 0x%I64x, handle 0x%I64x";
LABEL_54:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v24, v23, HIDWORD(Srca[0]), 0, 0, 0);
LABEL_55:
    v8 = -1073741811;
    DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v50);
    goto LABEL_39;
  }
  v25 = *(struct DXGDEVICE **)(v20 + 16);
  if ( v25 != v11 )
  {
    WdLogSingleEntry3(2, HIDWORD(Srca[0]), v25, v11);
    WdLogGlobalForLineNumber = 253;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"0x%x object belongs to a different device 0x%p that 0x%p passed.",
      HIDWORD(Srca[0]),
      *(_QWORD *)(v20 + 16),
      (__int64)v11,
      0,
      0);
    goto LABEL_55;
  }
  v6 = *(struct DXGDEVICE **)(v20 + 32);
  v38 = v6;
  DXGSYNCOBJECT::AddReference(v6);
  if ( ((*((_DWORD *)v6 + 105) - 5) & 0xFFFFFFFD) != 0 )
  {
    v23 = (__int64)v46;
    WdLogSingleEntry2(2, v46);
    WdLogGlobalForLineNumber = 278;
    v24 = L"not monitored/native fence object, process 0x%I64x, handle 0x%I64x";
    goto LABEL_54;
  }
  if ( (*((_DWORD *)v6 + 106) & 2) == 0 )
  {
    WdLogSingleEntry2(2, v6);
    WdLogGlobalForLineNumber = 287;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Not NT shared Monitored/Native Fence: Protected session's sync object 0x%I64x does not use NT securi"
                     "ty sharing. Returning 0x%I64x.",
      (__int64)v6,
      -1073741811,
      0,
      0,
      0);
    goto LABEL_55;
  }
  DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v50);
  v8 = ADAPTER_DISPLAY::CreateProtectedSession(*(ADAPTER_DISPLAY **)(v52 + 3232), &v38, &v47, Size[0], &v48, v44, &v45);
  if ( v8 < 0 )
  {
    v7 = (volatile signed __int32 *)v45;
    if ( v45 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 305;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pProtectedSession == NULL", 305, 0, 0, 0, 0);
    }
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v55);
    DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)v49);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v37);
    v6 = v38;
    goto LABEL_87;
  }
  v6 = v38;
  if ( v38 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 312;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pSyncObject == NULL", 312, 0, 0, 0, 0);
  }
  if ( v47 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 313;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pKMPrivateDriverData == NULL", 313, 0, 0, 0, 0);
  }
  if ( v48 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 314;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pKMPrivateRuntimeData == NULL", 314, 0, 0, 0, 0);
  }
  v7 = (volatile signed __int32 *)v45;
  v8 = DXGPROTECTEDSESSION::Open(v45, (unsigned int *)&v44 + 1);
  if ( v8 < 0 )
    goto LABEL_39;
  if ( _InterlockedExchangeAdd(v7 + 20, 0xFFFFFFFF) <= 1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 331;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"c > 0", 331, 0, 0, 0, 0);
  }
  if ( !HIDWORD(v44) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 337;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"KMCreateProtectedSession.hHandle", 337, 0, 0, 0, 0);
  }
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v55);
  DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)v49);
  ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v37);
  RtlCopyToUser(v53 + 36, (char *)&v44 + 4, 4u);
  v26 = HIDWORD(v44);
  v27 = v51;
  DXGPUSHLOCK::AcquireExclusive(v51);
  v28 = ((unsigned int)v26 >> 6) & 0xFFFFFF;
  v29 = v46;
  if ( (unsigned int)v28 < *((_DWORD *)v46 + 74) )
  {
    v30 = *((_QWORD *)v46 + 35);
    if ( (((unsigned int)v26 >> 25) & 0x60) == (*(_BYTE *)(v30 + 16 * v28 + 8) & 0x60)
      && (*(_DWORD *)(v30 + 16 * v28 + 8) & 0x1F) != 0 )
    {
      v31 = 16 * ((v26 >> 6) & 0xFFFFFF);
      if ( (*(_DWORD *)(v31 + v30 + 8) & 0x2000) == 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 224;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"m_pEntryTable[GetIndex(hObject)].Destroyed",
          224,
          0,
          0,
          0,
          0);
      }
      *(_DWORD *)(v31 + *((_QWORD *)v29 + 35) + 8) &= ~0x2000u;
    }
  }
  *((_QWORD *)v27 + 1) = 0;
  ExReleasePushLockExclusiveEx(v27, 0);
  KeLeaveCriticalRegion();
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v39);
  if ( v41 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v32, EventProfilerExit, v33, v39);
  return 0;
}

```

## disassembly

```asm
0x140259030  mov     [rsp+arg_8], rbx
0x140259035  mov     [rsp+arg_10], rsi
0x14025903a  push    rdi
0x14025903b  push    r12
0x14025903d  push    r13
0x14025903f  push    r14
0x140259041  push    r15
0x140259043  sub     rsp, 1B0h
0x14025904a  mov     rax, cs:__security_cookie
0x140259051  xor     rax, rsp
0x140259054  mov     [rsp+1D8h+var_38], rax
0x14025905c  mov     r14, rcx
0x14025905f  mov     [rsp+1D8h+var_E8], rcx
0x140259067  mov     [rsp+1D8h+var_E0], rcx
0x14025906f  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x140259076  nop     dword ptr [rax+rax+00h]
0x14025907b  mov     edi, 1
0x140259080  cmp     al, dil
0x140259083  jz      short loc_1402590D3
0x140259085  mov     ecx, edi
0x140259087  call    cs:__imp_WdLogSingleEntry0
0x14025908e  nop     dword ptr [rax+rax+00h]
0x140259093  lea     eax, [rdi+38h]
0x140259096  mov     cs:WdLogGlobalForLineNumber, eax
0x14025909c  xor     ebx, ebx
0x14025909e  mov     [rsp+1D8h+var_198], rbx
0x1402590a3  mov     [rsp+1D8h+var_1A0], rbx
0x1402590a8  mov     [rsp+1D8h+var_1A8], rbx
0x1402590ad  mov     qword ptr [rsp+1D8h+var_1B0], rbx
0x1402590b2  mov     [rsp+1D8h+var_1B8], rax
0x1402590b7  lea     r9, aPsgetcurrentth; "PsGetCurrentThreadPreviousMode() == Use"...
0x1402590be  or      r12d, 0FFFFFFFFh
0x1402590c2  mov     r8d, r12d
0x1402590c5  mov     edx, 40002h
0x1402590ca  xor     ecx, ecx
0x1402590cc  call    DxgkLogInternalTriageEvent
0x1402590d1  jmp     short loc_1402590D9
0x1402590d3  xor     ebx, ebx
0x1402590d5  or      r12d, 0FFFFFFFFh
0x1402590d9  mov     [rsp+1D8h+var_178], 0FFFFFFFFh
0x1402590e1  mov     [rsp+1D8h+var_170], rbx
0x1402590e6  mov     rax, cs:qword_14015C500
0x1402590ed  test    al, 2
0x1402590ef  jz      short loc_14025911B
0x1402590f1  mov     [rsp+1D8h+var_168], dil
0x1402590f6  mov     [rsp+1D8h+var_178], 864h
0x1402590fe  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x140259105  jz      short loc_14025911F
0x140259107  mov     r9d, 864h
0x14025910d  lea     rdx, EventProfilerEnter
0x140259114  call    McTemplateK0q_EtwWriteTransfer
0x140259119  jmp     short loc_14025911F
0x14025911b  mov     [rsp+1D8h+var_168], bl
0x14025911f  mov     edx, 864h
0x140259124  lea     rcx, [rsp+1D8h+var_178]
0x140259129  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x14025912e  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140259133  mov     rsi, rax
0x140259136  mov     [rsp+1D8h+var_130], rax
0x14025913e  test    rax, rax
0x140259141  jnz     short loc_14025919B
0x140259143  mov     rdx, 0FFFFFFFFC000000Dh
0x14025914a  lea     ecx, [rax+2]
0x14025914d  call    cs:__imp_WdLogSingleEntry1
0x140259154  nop     dword ptr [rax+rax+00h]
0x140259159  mov     cs:WdLogGlobalForLineNumber, 42h ; 'B'
0x140259163  mov     [rsp+1D8h+var_198], rbx
0x140259168  mov     [rsp+1D8h+var_1A0], rbx
0x14025916d  mov     [rsp+1D8h+var_1A8], rbx
0x140259172  mov     qword ptr [rsp+1D8h+var_1B0], rbx
0x140259177  mov     [rsp+1D8h+var_1B8], 0FFFFFFFFC000000Dh
0x140259180  lea     r9, aInvalidProcess_4; "Invalid process context, returning 0x%I"...
0x140259187  mov     r8d, r12d
0x14025918a  mov     edx, 40000h
0x14025918f  xor     ecx, ecx
0x140259191  call    DxgkLogInternalTriageEvent
0x140259196  jmp     loc_14025953B
0x14025919b  xorps   xmm0, xmm0
0x14025919e  xor     eax, eax
0x1402591a0  movups  xmmword ptr [rsp+1D8h+Src], xmm0
0x1402591a5  movups  xmmword ptr [rsp+1D8h+Size], xmm0
0x1402591ad  mov     [rsp+1D8h+var_140], rax
0x1402591b5  lea     r8d, [rax+28h]; Size
0x1402591b9  mov     rdx, r14; Src
0x1402591bc  lea     rcx, [rsp+1D8h+Src]; void *
0x1402591c1  call    RtlCopyFromUser
0x1402591c6  nop
0x1402591c7  mov     dword ptr [rsp+1D8h+var_140+4], ebx
0x1402591ce  mov     rdx, [rsp+1D8h+Src+8]
0x1402591d6  mov     ecx, dword ptr [rsp+1D8h+Size]
0x1402591dd  test    rdx, rdx
0x1402591e0  jz      short loc_1402591EB
0x1402591e2  test    ecx, ecx
0x1402591e4  jz      short loc_1402591EF
0x1402591e6  test    rdx, rdx
0x1402591e9  jnz     short loc_140259219
0x1402591eb  test    ecx, ecx
0x1402591ed  jz      short loc_140259219
0x1402591ef  mov     r8d, ecx
0x1402591f2  mov     ecx, 3
0x1402591f7  mov     r9, 0FFFFFFFFC000000Dh
0x1402591fe  call    cs:__imp_WdLogSingleEntry3
0x140259205  nop     dword ptr [rax+rax+00h]
0x14025920a  mov     cs:WdLogGlobalForLineNumber, 5Eh ; '^'
0x140259214  jmp     loc_14025953B
0x140259219  mov     r8d, 2000000h
0x14025921f  cmp     ecx, r8d
0x140259222  jbe     short loc_14025924D
0x140259224  mov     edx, ecx
0x140259226  mov     ecx, 3
0x14025922b  mov     r9, 0FFFFFFFFC000000Dh
0x140259232  call    cs:__imp_WdLogSingleEntry3
0x140259239  nop     dword ptr [rax+rax+00h]
0x14025923e  mov     cs:WdLogGlobalForLineNumber, 67h ; 'g'
0x140259248  jmp     loc_14025953B
0x14025924d  mov     rdx, [rsp+1D8h+Size+8]
0x140259255  mov     eax, dword ptr [rsp+1D8h+var_140]
0x14025925c  test    rdx, rdx
0x14025925f  jz      short loc_14025926A
0x140259261  test    eax, eax
0x140259263  jz      short loc_14025926E
0x140259265  test    rdx, rdx
0x140259268  jnz     short loc_140259298
0x14025926a  test    eax, eax
0x14025926c  jz      short loc_140259298
0x14025926e  mov     r8d, eax
0x140259271  mov     ecx, 3
0x140259276  mov     r9, 0FFFFFFFFC000000Dh
0x14025927d  call    cs:__imp_WdLogSingleEntry3
0x140259284  nop     dword ptr [rax+rax+00h]
0x140259289  mov     cs:WdLogGlobalForLineNumber, 71h ; 'q'
0x140259293  jmp     loc_14025953B
0x140259298  cmp     eax, r8d
0x14025929b  jbe     short loc_1402592C6
0x14025929d  mov     edx, eax
0x14025929f  mov     ecx, 3
0x1402592a4  mov     r9, 0FFFFFFFFC000000Dh
0x1402592ab  call    cs:__imp_WdLogSingleEntry3
0x1402592b2  nop     dword ptr [rax+rax+00h]
0x1402592b7  mov     cs:WdLogGlobalForLineNumber, 7Ah ; 'z'
0x1402592c1  jmp     loc_14025953B
0x1402592c6  mov     [rsp+1D8h+var_128], rbx
0x1402592ce  mov     [rsp+1D8h+var_120], rbx
0x1402592d6  mov     r14, rbx
0x1402592d9  mov     [rsp+1D8h+var_180], rbx
0x1402592de  mov     r15, rbx
0x1402592e1  mov     [rsp+1D8h+var_138], rbx
0x1402592e9  test    ecx, ecx
0x1402592eb  jz      loc_1402593E1
0x1402592f1  mov     edx, 4B677844h
0x1402592f6  mov     r8d, 100h
0x1402592fc  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140259301  mov     [rsp+1D8h+var_128], rax
0x140259309  test    rax, rax
0x14025930c  jnz     short loc_140259373
0x14025930e  mov     edx, dword ptr [rsp+1D8h+Size]
0x140259315  mov     rsi, 0FFFFFFFFC0000017h
0x14025931c  mov     r8, rsi
0x14025931f  lea     ecx, [rax+6]
0x140259322  call    cs:__imp_WdLogSingleEntry2
0x140259329  nop     dword ptr [rax+rax+00h]
0x14025932e  mov     cs:WdLogGlobalForLineNumber, 90h
0x140259338  mov     eax, dword ptr [rsp+1D8h+Size]
0x14025933f  lea     r9, aOutOfMemoryAll_10; "Out of memory allocating 0x%I64x bytes "...
0x140259346  mov     [rsp+1D8h+var_198], rbx
0x14025934b  mov     [rsp+1D8h+var_1A0], rbx
0x140259350  mov     [rsp+1D8h+var_1A8], rbx
0x140259355  mov     qword ptr [rsp+1D8h+var_1B0], rsi
0x14025935a  mov     [rsp+1D8h+var_1B8], rax
0x14025935f  mov     r8d, r12d
0x140259362  mov     edx, 40001h
0x140259367  xor     ecx, ecx
0x140259369  call    DxgkLogInternalTriageEvent
0x14025936e  jmp     loc_140259D40
0x140259373  mov     r8d, dword ptr [rsp+1D8h+Size]; Size
0x14025937b  mov     rdx, [rsp+1D8h+Src+8]; Src
0x140259383  mov     rcx, [rsp+1D8h+var_128]; void *
0x14025938b  call    RtlCopyFromUser
0x140259390  mov     eax, dword ptr [rsp+1D8h+var_140]
0x140259397  jmp     short loc_1402593E1
0x140259399  mov     r8, 0FFFFFFFFC000000Dh
0x1402593a0  mov     rdx, [rsp+1D8h+Src+8]
0x1402593a8  mov     ecx, 3
0x1402593ad  call    cs:__imp_WdLogSingleEntry2
0x1402593b4  nop     dword ptr [rax+rax+00h]
0x1402593b9  mov     cs:WdLogGlobalForLineNumber, 9Fh
0x1402593c3  mov     esi, 0C000000Dh
0x1402593c8  mov     edi, 1
0x1402593cd  xor     ebx, ebx
0x1402593cf  mov     r14, [rsp+1D8h+var_180]
0x1402593d4  mov     r15, [rsp+1D8h+var_138]
0x1402593dc  jmp     loc_140259D40
0x1402593e1  test    eax, eax
0x1402593e3  jz      loc_1402594AC
0x1402593e9  mov     ecx, eax
0x1402593eb  mov     edx, 4B677844h
0x1402593f0  mov     r8d, 100h
0x1402593f6  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1402593fb  mov     [rsp+1D8h+var_120], rax
0x140259403  test    rax, rax
0x140259406  jnz     short loc_140259445
0x140259408  mov     edx, dword ptr [rsp+1D8h+var_140]
0x14025940f  mov     rsi, 0FFFFFFFFC0000017h
0x140259416  mov     r8, rsi
0x140259419  lea     ecx, [rax+6]
0x14025941c  call    cs:__imp_WdLogSingleEntry2
0x140259423  nop     dword ptr [rax+rax+00h]
0x140259428  mov     cs:WdLogGlobalForLineNumber, 0ACh
0x140259432  mov     eax, dword ptr [rsp+1D8h+var_140]
0x140259439  lea     r9, aOutOfMemoryAll_19; "Out of memory allocating 0x%I64x bytes "...
0x140259440  jmp     loc_140259346
0x140259445  mov     r8d, dword ptr [rsp+1D8h+var_140]; Size
0x14025944d  mov     rdx, [rsp+1D8h+Size+8]; Src
0x140259455  mov     rcx, [rsp+1D8h+var_120]; void *
0x14025945d  call    RtlCopyFromUser
0x140259462  jmp     short loc_1402594AC
0x140259464  mov     r8, 0FFFFFFFFC000000Dh
0x14025946b  mov     rdx, [rsp+1D8h+Size+8]
0x140259473  mov     ecx, 3
0x140259478  call    cs:__imp_WdLogSingleEntry2
0x14025947f  nop     dword ptr [rax+rax+00h]
0x140259484  mov     cs:WdLogGlobalForLineNumber, 0BBh
0x14025948e  mov     esi, 0C000000Dh
0x140259493  mov     edi, 1
0x140259498  xor     ebx, ebx
0x14025949a  mov     r14, [rsp+1D8h+var_180]
0x14025949f  mov     r15, [rsp+1D8h+var_138]
0x1402594a7  jmp     loc_140259D40
0x1402594ac  mov     [rsp+1D8h+var_180], rbx
0x1402594b1  lea     r9, [rsp+1D8h+var_180]; struct DXGDEVICE **
0x1402594b6  mov     r8, rsi; struct DXGPROCESS *
0x1402594b9  mov     edx, dword ptr [rsp+1D8h+Src]; unsigned int
0x1402594bd  lea     rcx, [rsp+1D8h+var_188]; this
0x1402594c2  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x1402594c7  mov     r13, [rsp+1D8h+var_180]
0x1402594cc  test    r13, r13
0x1402594cf  jnz     loc_14025956F
0x1402594d5  mov     edx, dword ptr [rsp+1D8h+Src]
0x1402594d9  lea     ecx, [r13+2]
0x1402594dd  mov     r8, 0FFFFFFFFC000000Dh
0x1402594e4  call    cs:__imp_WdLogSingleEntry2
0x1402594eb  nop     dword ptr [rax+rax+00h]
0x1402594f0  mov     cs:WdLogGlobalForLineNumber, 0C8h
0x1402594fa  mov     eax, dword ptr [rsp+1D8h+Src]
0x1402594fe  mov     [rsp+1D8h+var_198], rbx
0x140259503  mov     [rsp+1D8h+var_1A0], rbx
0x140259508  mov     [rsp+1D8h+var_1A8], rbx
0x14025950d  mov     qword ptr [rsp+1D8h+var_1B0], 0FFFFFFFFC000000Dh
0x140259516  mov     [rsp+1D8h+var_1B8], rax
0x14025951b  lea     r9, aInvalidHdevice_2; "Invalid hDevice (0x%I64x) specified, re"...
0x140259522  mov     r8d, r12d
0x140259525  mov     edx, 40000h
0x14025952a  xor     ecx, ecx
0x14025952c  call    DxgkLogInternalTriageEvent
0x140259531  lea     rcx, [rsp+1D8h+var_188]; this
0x140259536  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x14025953b  lea     rcx, [rsp+1D8h+var_178]; this
0x140259540  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140259545  cmp     [rsp+1D8h+var_168], bl
0x140259549  jz      short loc_140259565
0x14025954b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x140259552  jz      short loc_140259565
0x140259554  mov     r9d, [rsp+1D8h+var_178]
0x140259559  lea     rdx, EventProfilerExit
0x140259560  call    McTemplateK0q_EtwWriteTransfer
0x140259565  mov     eax, 0C000000Dh
0x14025956a  jmp     loc_140259E1A
0x14025956f  mov     rdx, r13; struct DXGDEVICE *
0x140259572  lea     rcx, [rsp+1D8h+var_118]; this
0x14025957a  call    ??0DXGDEVICEACCESSLOCKSHARED@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICEACCESSLOCKSHARED::DXGDEVICEACCESSLOCKSHARED(DXGDEVICE *)
0x14025957f  mov     byte ptr [rsp+1D8h+var_1B8], bl
0x140259583  mov     r8d, edi
0x140259586  mov     rdx, r13
0x140259589  lea     rcx, [rsp+1D8h+var_D8]
0x140259591  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x140259596  xor     edx, edx; char *
0x140259598  lea     rcx, [rsp+1D8h+var_D8]; this
0x1402595a0  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x1402595a5  mov     esi, eax
0x1402595a7  test    eax, eax
0x1402595a9  jns     short loc_1402595D4
0x1402595ab  lea     rcx, [rsp+1D8h+var_D8]; this
0x1402595b3  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1402595b8  lea     rcx, [rsp+1D8h+var_118]; this
0x1402595c0  call    ??1DXGDEVICEACCESSLOCKSHARED@@QEAA@XZ; DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED(void)
0x1402595c5  lea     rcx, [rsp+1D8h+var_188]; this
0x1402595ca  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x1402595cf  jmp     loc_140259D40
0x1402595d4  mov     rax, [r13+768h]
0x1402595db  mov     [rsp+1D8h+var_F0], rax
0x1402595e3  test    rax, rax
0x1402595e6  jnz     short loc_140259642
0x1402595e8  mov     rsi, 0FFFFFFFFC00000BBh
0x1402595ef  mov     r8, rsi
0x1402595f2  mov     rdx, r13
0x1402595f5  lea     ecx, [rax+2]
0x1402595f8  call    cs:__imp_WdLogSingleEntry2
0x1402595ff  nop     dword ptr [rax+rax+00h]
0x140259604  mov     cs:WdLogGlobalForLineNumber, 0DAh
0x14025960e  mov     [rsp+1D8h+var_198], rbx
  ... truncated ...
```
