# DxgkCreateProtectedSession

- ea: `0x14025d680`
- end: `0x14025e498`
- name: `DxgkCreateProtectedSession`
- size: `3608`
- prototype: `__int64 __fastcall(char *Src)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x140015b30`
- `0x140018054`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001cff0`
- `0x14001d1a0`
- `0x14001d214`
- `0x14001f2f0`
- `0x140030824`
- `0x1400309f0`
- `0x140030a30`
- `0x140033da4`
- `0x140036ea8`
- `0x140048a5c`
- `0x14004fe88`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1401cb358`
- `0x1401e76e0`
- `0x14025cafc`
- `0x14025d1a8`
- `0x14025d680`
- `0x140328e00`
- `0x14032a5c4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025ddb1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025e310`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025ddb1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025e310`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14025e304`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14025e304`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14025dda5`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14025dda5`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14025d6bf`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14025d6bf`
- `watchdog!WdLogSingleEntry2` at `0x14025d972`
- `watchdog!WdLogSingleEntry2` at `0x14025d9fd`
- `watchdog!WdLogSingleEntry2` at `0x14025da6c`
- `watchdog!WdLogSingleEntry2` at `0x14025dac8`
- `watchdog!WdLogSingleEntry2` at `0x14025db34`
- `watchdog!WdLogSingleEntry2` at `0x14025dc48`
- `watchdog!WdLogSingleEntry2` at `0x14025ddd7`
- `watchdog!WdLogSingleEntry2` at `0x14025dec8`
- `watchdog!WdLogSingleEntry2` at `0x14025df04`
- `watchdog!WdLogSingleEntry2` at `0x14025e361`
- `watchdog!WdLogSingleEntry2` at `0x14025d972`
- `watchdog!WdLogSingleEntry2` at `0x14025d9fd`
- `watchdog!WdLogSingleEntry2` at `0x14025da6c`
- `watchdog!WdLogSingleEntry2` at `0x14025dac8`
- `watchdog!WdLogSingleEntry2` at `0x14025db34`
- `watchdog!WdLogSingleEntry2` at `0x14025dc48`
- `watchdog!WdLogSingleEntry2` at `0x14025ddd7`
- `watchdog!WdLogSingleEntry2` at `0x14025dec8`
- `watchdog!WdLogSingleEntry2` at `0x14025df04`
- `watchdog!WdLogSingleEntry2` at `0x14025e361`
- `watchdog!WdLogSingleEntry3` at `0x14025d84e`
- `watchdog!WdLogSingleEntry3` at `0x14025d882`
- `watchdog!WdLogSingleEntry3` at `0x14025d8cd`
- `watchdog!WdLogSingleEntry3` at `0x14025d8fb`
- `watchdog!WdLogSingleEntry3` at `0x14025de4c`
- `watchdog!WdLogSingleEntry3` at `0x14025d84e`
- `watchdog!WdLogSingleEntry3` at `0x14025d882`
- `watchdog!WdLogSingleEntry3` at `0x14025d8cd`
- `watchdog!WdLogSingleEntry3` at `0x14025d8fb`
- `watchdog!WdLogSingleEntry3` at `0x14025de4c`
- `watchdog!WdLogSingleEntry0` at `0x14025d6d7`
- `watchdog!WdLogSingleEntry0` at `0x14025dd48`
- `watchdog!WdLogSingleEntry0` at `0x14025dfb7`
- `watchdog!WdLogSingleEntry0` at `0x14025e037`
- `watchdog!WdLogSingleEntry0` at `0x14025e095`
- `watchdog!WdLogSingleEntry0` at `0x14025e0e5`
- `watchdog!WdLogSingleEntry0` at `0x14025e15b`
- `watchdog!WdLogSingleEntry0` at `0x14025e1aa`
- `watchdog!WdLogSingleEntry0` at `0x14025e2aa`
- `watchdog!WdLogSingleEntry0` at `0x14025d6d7`
- `watchdog!WdLogSingleEntry0` at `0x14025dd48`
- `watchdog!WdLogSingleEntry0` at `0x14025dfb7`
- `watchdog!WdLogSingleEntry0` at `0x14025e037`
- `watchdog!WdLogSingleEntry0` at `0x14025e095`
- `watchdog!WdLogSingleEntry0` at `0x14025e0e5`
- `watchdog!WdLogSingleEntry0` at `0x14025e15b`
- `watchdog!WdLogSingleEntry0` at `0x14025e1aa`
- `watchdog!WdLogSingleEntry0` at `0x14025e2aa`
- `watchdog!WdLogSingleEntry1` at `0x14025d79d`
- `watchdog!WdLogSingleEntry1` at `0x14025e424`
- `watchdog!WdLogSingleEntry1` at `0x14025d79d`
- `watchdog!WdLogSingleEntry1` at `0x14025e424`

## string_xrefs

- `0x14025d707`: `PsGetCurrentThreadPreviousMode() == UserMode`
- `0x14025df37`: `Not NT shared Monitored/Native Fence: Protected session's sync object 0x%I64x does not use NT security sharing. Returning 0x%I64x.`
- `0x14025e1da`: `KMCreateProtectedSession.hHandle`

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
  if ( (qword_1401604F0 & 2) != 0 )
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
    WdLogSingleEntry1(2, -1073741811);
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
      WdLogSingleEntry2(6, LODWORD(Size[0]), -1073741801);
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
      WdLogSingleEntry2(6, (unsigned int)v44, -1073741801);
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
    WdLogSingleEntry2(2, LODWORD(Srca[0]), -1073741811);
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
    WdLogSingleEntry2(2, v11, -1073741637);
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
    WdLogSingleEntry2(2, v46, HIDWORD(Srca[0]));
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
    WdLogSingleEntry2(2, v46, HIDWORD(Srca[0]));
    WdLogGlobalForLineNumber = 278;
    v24 = L"not monitored/native fence object, process 0x%I64x, handle 0x%I64x";
    goto LABEL_54;
  }
  if ( (*((_DWORD *)v6 + 106) & 2) == 0 )
  {
    WdLogSingleEntry2(2, v6, -1073741811);
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
  v8 = ADAPTER_DISPLAY::CreateProtectedSession(*(ADAPTER_DISPLAY **)(v52 + 3248), &v38, &v47, Size[0], &v48, v44, &v45);
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
0x14025d680  mov     [rsp+arg_8], rbx
0x14025d685  mov     [rsp+arg_10], rsi
0x14025d68a  push    rdi
0x14025d68b  push    r12
0x14025d68d  push    r13
0x14025d68f  push    r14
0x14025d691  push    r15
0x14025d693  sub     rsp, 1B0h
0x14025d69a  mov     rax, cs:__security_cookie
0x14025d6a1  xor     rax, rsp
0x14025d6a4  mov     [rsp+1D8h+var_38], rax
0x14025d6ac  mov     r14, rcx
0x14025d6af  mov     [rsp+1D8h+var_E8], rcx
0x14025d6b7  mov     [rsp+1D8h+var_E0], rcx
0x14025d6bf  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x14025d6c6  nop     dword ptr [rax+rax+00h]
0x14025d6cb  mov     edi, 1
0x14025d6d0  cmp     al, dil
0x14025d6d3  jz      short loc_14025D723
0x14025d6d5  mov     ecx, edi
0x14025d6d7  call    cs:__imp_WdLogSingleEntry0
0x14025d6de  nop     dword ptr [rax+rax+00h]
0x14025d6e3  lea     eax, [rdi+38h]
0x14025d6e6  mov     cs:WdLogGlobalForLineNumber, eax
0x14025d6ec  xor     ebx, ebx
0x14025d6ee  mov     [rsp+1D8h+var_198], rbx
0x14025d6f3  mov     [rsp+1D8h+var_1A0], rbx
0x14025d6f8  mov     [rsp+1D8h+var_1A8], rbx
0x14025d6fd  mov     qword ptr [rsp+1D8h+var_1B0], rbx
0x14025d702  mov     [rsp+1D8h+var_1B8], rax
0x14025d707  lea     r9, aPsgetcurrentth; "PsGetCurrentThreadPreviousMode() == Use"...
0x14025d70e  or      r12d, 0FFFFFFFFh
0x14025d712  mov     r8d, r12d
0x14025d715  mov     edx, 40002h
0x14025d71a  xor     ecx, ecx
0x14025d71c  call    DxgkLogInternalTriageEvent
0x14025d721  jmp     short loc_14025D729
0x14025d723  xor     ebx, ebx
0x14025d725  or      r12d, 0FFFFFFFFh
0x14025d729  mov     [rsp+1D8h+var_178], 0FFFFFFFFh
0x14025d731  mov     [rsp+1D8h+var_170], rbx
0x14025d736  mov     rax, cs:qword_1401604F0
0x14025d73d  test    al, 2
0x14025d73f  jz      short loc_14025D76B
0x14025d741  mov     [rsp+1D8h+var_168], dil
0x14025d746  mov     [rsp+1D8h+var_178], 864h
0x14025d74e  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x14025d755  jz      short loc_14025D76F
0x14025d757  mov     r9d, 864h
0x14025d75d  lea     rdx, EventProfilerEnter
0x14025d764  call    McTemplateK0q_EtwWriteTransfer
0x14025d769  jmp     short loc_14025D76F
0x14025d76b  mov     [rsp+1D8h+var_168], bl
0x14025d76f  mov     edx, 864h
0x14025d774  lea     rcx, [rsp+1D8h+var_178]
0x14025d779  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x14025d77e  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14025d783  mov     rsi, rax
0x14025d786  mov     [rsp+1D8h+var_130], rax
0x14025d78e  test    rax, rax
0x14025d791  jnz     short loc_14025D7EB
0x14025d793  mov     rdx, 0FFFFFFFFC000000Dh
0x14025d79a  lea     ecx, [rax+2]
0x14025d79d  call    cs:__imp_WdLogSingleEntry1
0x14025d7a4  nop     dword ptr [rax+rax+00h]
0x14025d7a9  mov     cs:WdLogGlobalForLineNumber, 42h ; 'B'
0x14025d7b3  mov     [rsp+1D8h+var_198], rbx
0x14025d7b8  mov     [rsp+1D8h+var_1A0], rbx
0x14025d7bd  mov     [rsp+1D8h+var_1A8], rbx
0x14025d7c2  mov     qword ptr [rsp+1D8h+var_1B0], rbx
0x14025d7c7  mov     [rsp+1D8h+var_1B8], 0FFFFFFFFC000000Dh
0x14025d7d0  lea     r9, aInvalidProcess_4; "Invalid process context, returning 0x%I"...
0x14025d7d7  mov     r8d, r12d
0x14025d7da  mov     edx, 40000h
0x14025d7df  xor     ecx, ecx
0x14025d7e1  call    DxgkLogInternalTriageEvent
0x14025d7e6  jmp     loc_14025DB8B
0x14025d7eb  xorps   xmm0, xmm0
0x14025d7ee  xor     eax, eax
0x14025d7f0  movups  xmmword ptr [rsp+1D8h+Src], xmm0
0x14025d7f5  movups  xmmword ptr [rsp+1D8h+Size], xmm0
0x14025d7fd  mov     [rsp+1D8h+var_140], rax
0x14025d805  lea     r8d, [rax+28h]; Size
0x14025d809  mov     rdx, r14; Src
0x14025d80c  lea     rcx, [rsp+1D8h+Src]; void *
0x14025d811  call    RtlCopyFromUser
0x14025d816  nop
0x14025d817  mov     dword ptr [rsp+1D8h+var_140+4], ebx
0x14025d81e  mov     rdx, [rsp+1D8h+Src+8]
0x14025d826  mov     ecx, dword ptr [rsp+1D8h+Size]
0x14025d82d  test    rdx, rdx
0x14025d830  jz      short loc_14025D83B
0x14025d832  test    ecx, ecx
0x14025d834  jz      short loc_14025D83F
0x14025d836  test    rdx, rdx
0x14025d839  jnz     short loc_14025D869
0x14025d83b  test    ecx, ecx
0x14025d83d  jz      short loc_14025D869
0x14025d83f  mov     r8d, ecx
0x14025d842  mov     ecx, 3
0x14025d847  mov     r9, 0FFFFFFFFC000000Dh
0x14025d84e  call    cs:__imp_WdLogSingleEntry3
0x14025d855  nop     dword ptr [rax+rax+00h]
0x14025d85a  mov     cs:WdLogGlobalForLineNumber, 5Eh ; '^'
0x14025d864  jmp     loc_14025DB8B
0x14025d869  mov     r8d, 2000000h
0x14025d86f  cmp     ecx, r8d
0x14025d872  jbe     short loc_14025D89D
0x14025d874  mov     edx, ecx
0x14025d876  mov     ecx, 3
0x14025d87b  mov     r9, 0FFFFFFFFC000000Dh
0x14025d882  call    cs:__imp_WdLogSingleEntry3
0x14025d889  nop     dword ptr [rax+rax+00h]
0x14025d88e  mov     cs:WdLogGlobalForLineNumber, 67h ; 'g'
0x14025d898  jmp     loc_14025DB8B
0x14025d89d  mov     rdx, [rsp+1D8h+Size+8]
0x14025d8a5  mov     eax, dword ptr [rsp+1D8h+var_140]
0x14025d8ac  test    rdx, rdx
0x14025d8af  jz      short loc_14025D8BA
0x14025d8b1  test    eax, eax
0x14025d8b3  jz      short loc_14025D8BE
0x14025d8b5  test    rdx, rdx
0x14025d8b8  jnz     short loc_14025D8E8
0x14025d8ba  test    eax, eax
0x14025d8bc  jz      short loc_14025D8E8
0x14025d8be  mov     r8d, eax
0x14025d8c1  mov     ecx, 3
0x14025d8c6  mov     r9, 0FFFFFFFFC000000Dh
0x14025d8cd  call    cs:__imp_WdLogSingleEntry3
0x14025d8d4  nop     dword ptr [rax+rax+00h]
0x14025d8d9  mov     cs:WdLogGlobalForLineNumber, 71h ; 'q'
0x14025d8e3  jmp     loc_14025DB8B
0x14025d8e8  cmp     eax, r8d
0x14025d8eb  jbe     short loc_14025D916
0x14025d8ed  mov     edx, eax
0x14025d8ef  mov     ecx, 3
0x14025d8f4  mov     r9, 0FFFFFFFFC000000Dh
0x14025d8fb  call    cs:__imp_WdLogSingleEntry3
0x14025d902  nop     dword ptr [rax+rax+00h]
0x14025d907  mov     cs:WdLogGlobalForLineNumber, 7Ah ; 'z'
0x14025d911  jmp     loc_14025DB8B
0x14025d916  mov     [rsp+1D8h+var_128], rbx
0x14025d91e  mov     [rsp+1D8h+var_120], rbx
0x14025d926  mov     r14, rbx
0x14025d929  mov     [rsp+1D8h+var_180], rbx
0x14025d92e  mov     r15, rbx
0x14025d931  mov     [rsp+1D8h+var_138], rbx
0x14025d939  test    ecx, ecx
0x14025d93b  jz      loc_14025DA31
0x14025d941  mov     edx, 4B677844h
0x14025d946  mov     r8d, 100h
0x14025d94c  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14025d951  mov     [rsp+1D8h+var_128], rax
0x14025d959  test    rax, rax
0x14025d95c  jnz     short loc_14025D9C3
0x14025d95e  mov     edx, dword ptr [rsp+1D8h+Size]
0x14025d965  mov     rsi, 0FFFFFFFFC0000017h
0x14025d96c  mov     r8, rsi
0x14025d96f  lea     ecx, [rax+6]
0x14025d972  call    cs:__imp_WdLogSingleEntry2
0x14025d979  nop     dword ptr [rax+rax+00h]
0x14025d97e  mov     cs:WdLogGlobalForLineNumber, 90h
0x14025d988  mov     eax, dword ptr [rsp+1D8h+Size]
0x14025d98f  lea     r9, aOutOfMemoryAll_10; "Out of memory allocating 0x%I64x bytes "...
0x14025d996  mov     [rsp+1D8h+var_198], rbx
0x14025d99b  mov     [rsp+1D8h+var_1A0], rbx
0x14025d9a0  mov     [rsp+1D8h+var_1A8], rbx
0x14025d9a5  mov     qword ptr [rsp+1D8h+var_1B0], rsi
0x14025d9aa  mov     [rsp+1D8h+var_1B8], rax
0x14025d9af  mov     r8d, r12d
0x14025d9b2  mov     edx, 40001h
0x14025d9b7  xor     ecx, ecx
0x14025d9b9  call    DxgkLogInternalTriageEvent
0x14025d9be  jmp     loc_14025E390
0x14025d9c3  mov     r8d, dword ptr [rsp+1D8h+Size]; Size
0x14025d9cb  mov     rdx, [rsp+1D8h+Src+8]; Src
0x14025d9d3  mov     rcx, [rsp+1D8h+var_128]; void *
0x14025d9db  call    RtlCopyFromUser
0x14025d9e0  mov     eax, dword ptr [rsp+1D8h+var_140]
0x14025d9e7  jmp     short loc_14025DA31
0x14025d9e9  mov     r8, 0FFFFFFFFC000000Dh
0x14025d9f0  mov     rdx, [rsp+1D8h+Src+8]
0x14025d9f8  mov     ecx, 3
0x14025d9fd  call    cs:__imp_WdLogSingleEntry2
0x14025da04  nop     dword ptr [rax+rax+00h]
0x14025da09  mov     cs:WdLogGlobalForLineNumber, 9Fh
0x14025da13  mov     esi, 0C000000Dh
0x14025da18  mov     edi, 1
0x14025da1d  xor     ebx, ebx
0x14025da1f  mov     r14, [rsp+1D8h+var_180]
0x14025da24  mov     r15, [rsp+1D8h+var_138]
0x14025da2c  jmp     loc_14025E390
0x14025da31  test    eax, eax
0x14025da33  jz      loc_14025DAFC
0x14025da39  mov     ecx, eax
0x14025da3b  mov     edx, 4B677844h
0x14025da40  mov     r8d, 100h
0x14025da46  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14025da4b  mov     [rsp+1D8h+var_120], rax
0x14025da53  test    rax, rax
0x14025da56  jnz     short loc_14025DA95
0x14025da58  mov     edx, dword ptr [rsp+1D8h+var_140]
0x14025da5f  mov     rsi, 0FFFFFFFFC0000017h
0x14025da66  mov     r8, rsi
0x14025da69  lea     ecx, [rax+6]
0x14025da6c  call    cs:__imp_WdLogSingleEntry2
0x14025da73  nop     dword ptr [rax+rax+00h]
0x14025da78  mov     cs:WdLogGlobalForLineNumber, 0ACh
0x14025da82  mov     eax, dword ptr [rsp+1D8h+var_140]
0x14025da89  lea     r9, aOutOfMemoryAll_19; "Out of memory allocating 0x%I64x bytes "...
0x14025da90  jmp     loc_14025D996
0x14025da95  mov     r8d, dword ptr [rsp+1D8h+var_140]; Size
0x14025da9d  mov     rdx, [rsp+1D8h+Size+8]; Src
0x14025daa5  mov     rcx, [rsp+1D8h+var_120]; void *
0x14025daad  call    RtlCopyFromUser
0x14025dab2  jmp     short loc_14025DAFC
0x14025dab4  mov     r8, 0FFFFFFFFC000000Dh
0x14025dabb  mov     rdx, [rsp+1D8h+Size+8]
0x14025dac3  mov     ecx, 3
0x14025dac8  call    cs:__imp_WdLogSingleEntry2
0x14025dacf  nop     dword ptr [rax+rax+00h]
0x14025dad4  mov     cs:WdLogGlobalForLineNumber, 0BBh
0x14025dade  mov     esi, 0C000000Dh
0x14025dae3  mov     edi, 1
0x14025dae8  xor     ebx, ebx
0x14025daea  mov     r14, [rsp+1D8h+var_180]
0x14025daef  mov     r15, [rsp+1D8h+var_138]
0x14025daf7  jmp     loc_14025E390
0x14025dafc  mov     [rsp+1D8h+var_180], rbx
0x14025db01  lea     r9, [rsp+1D8h+var_180]; struct DXGDEVICE **
0x14025db06  mov     r8, rsi; struct DXGPROCESS *
0x14025db09  mov     edx, dword ptr [rsp+1D8h+Src]; unsigned int
0x14025db0d  lea     rcx, [rsp+1D8h+var_188]; this
0x14025db12  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x14025db17  mov     r13, [rsp+1D8h+var_180]
0x14025db1c  test    r13, r13
0x14025db1f  jnz     loc_14025DBBF
0x14025db25  mov     edx, dword ptr [rsp+1D8h+Src]
0x14025db29  lea     ecx, [r13+2]
0x14025db2d  mov     r8, 0FFFFFFFFC000000Dh
0x14025db34  call    cs:__imp_WdLogSingleEntry2
0x14025db3b  nop     dword ptr [rax+rax+00h]
0x14025db40  mov     cs:WdLogGlobalForLineNumber, 0C8h
0x14025db4a  mov     eax, dword ptr [rsp+1D8h+Src]
0x14025db4e  mov     [rsp+1D8h+var_198], rbx
0x14025db53  mov     [rsp+1D8h+var_1A0], rbx
0x14025db58  mov     [rsp+1D8h+var_1A8], rbx
0x14025db5d  mov     qword ptr [rsp+1D8h+var_1B0], 0FFFFFFFFC000000Dh
0x14025db66  mov     [rsp+1D8h+var_1B8], rax
0x14025db6b  lea     r9, aInvalidHdevice_2; "Invalid hDevice (0x%I64x) specified, re"...
0x14025db72  mov     r8d, r12d
0x14025db75  mov     edx, 40000h
0x14025db7a  xor     ecx, ecx
0x14025db7c  call    DxgkLogInternalTriageEvent
0x14025db81  lea     rcx, [rsp+1D8h+var_188]; this
0x14025db86  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x14025db8b  lea     rcx, [rsp+1D8h+var_178]; this
0x14025db90  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14025db95  cmp     [rsp+1D8h+var_168], bl
0x14025db99  jz      short loc_14025DBB5
0x14025db9b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x14025dba2  jz      short loc_14025DBB5
0x14025dba4  mov     r9d, [rsp+1D8h+var_178]
0x14025dba9  lea     rdx, EventProfilerExit
0x14025dbb0  call    McTemplateK0q_EtwWriteTransfer
0x14025dbb5  mov     eax, 0C000000Dh
0x14025dbba  jmp     loc_14025E46A
0x14025dbbf  mov     rdx, r13; struct DXGDEVICE *
0x14025dbc2  lea     rcx, [rsp+1D8h+var_118]; this
0x14025dbca  call    ??0DXGDEVICEACCESSLOCKSHARED@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICEACCESSLOCKSHARED::DXGDEVICEACCESSLOCKSHARED(DXGDEVICE *)
0x14025dbcf  mov     byte ptr [rsp+1D8h+var_1B8], bl
0x14025dbd3  mov     r8d, edi
0x14025dbd6  mov     rdx, r13
0x14025dbd9  lea     rcx, [rsp+1D8h+var_D8]
0x14025dbe1  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x14025dbe6  xor     edx, edx; char *
0x14025dbe8  lea     rcx, [rsp+1D8h+var_D8]; this
0x14025dbf0  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x14025dbf5  mov     esi, eax
0x14025dbf7  test    eax, eax
0x14025dbf9  jns     short loc_14025DC24
0x14025dbfb  lea     rcx, [rsp+1D8h+var_D8]; this
0x14025dc03  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x14025dc08  lea     rcx, [rsp+1D8h+var_118]; this
0x14025dc10  call    ??1DXGDEVICEACCESSLOCKSHARED@@QEAA@XZ; DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED(void)
0x14025dc15  lea     rcx, [rsp+1D8h+var_188]; this
0x14025dc1a  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x14025dc1f  jmp     loc_14025E390
0x14025dc24  mov     rax, [r13+768h]
0x14025dc2b  mov     [rsp+1D8h+var_F0], rax
0x14025dc33  test    rax, rax
0x14025dc36  jnz     short loc_14025DC92
0x14025dc38  mov     rsi, 0FFFFFFFFC00000BBh
0x14025dc3f  mov     r8, rsi
0x14025dc42  mov     rdx, r13
0x14025dc45  lea     ecx, [rax+2]
0x14025dc48  call    cs:__imp_WdLogSingleEntry2
0x14025dc4f  nop     dword ptr [rax+rax+00h]
0x14025dc54  mov     cs:WdLogGlobalForLineNumber, 0DAh
0x14025dc5e  mov     [rsp+1D8h+var_198], rbx
  ... truncated ...
```
