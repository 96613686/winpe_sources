# UlpDispatchToRequestQueue

- ea: `0x14003cde0`
- end: `0x14003deca`
- name: `UlpDispatchToRequestQueue`
- size: `4330`
- prototype: ``
- caller_count: `3`
- callee_count: `35`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002cfc0`
- `0x14002dd70`
- `0x14003cd20`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140013430`
- `0x140022610`
- `0x14003bbfc`
- `0x14003bf20`
- `0x14003c144`
- `0x14003cde0`
- `0x14003ded0`
- `0x14003e660`
- `0x140049d28`
- `0x14005dff0`
- `0x14005e050`
- `0x140090f10`
- `0x14009622c`
- `0x14009c7e4`
- `0x1400a033c`
- `0x1400a7a94`
- `0x1400cf1e8`
- `0x14013dc78`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c5068`
- `0x1401c5480`
- `0x1401c6560`
- `0x1401c65ec`
- `0x1401ccf58`
- `0x1401cd174`
- `0x1401d9e44`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14003d819`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003d819`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003d94f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003d94f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d224`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d224`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003d8a5`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003d8a5`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003d902`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003d902`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14003de20`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14003de20`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003d841`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003d841`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003d886`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003d886`
- `ntoskrnl!KeSetEvent` at `0x14003d96d`
- `ntoskrnl!KeSetEvent` at `0x14003d96d`
- `ntoskrnl!IofCompleteRequest` at `0x1401759df`
- `ntoskrnl!IofCompleteRequest` at `0x1401759df`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14003d8cf`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14003d8cf`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14003ceb2`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14003ceb2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003d7f9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003d7f9`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003d02e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003d737`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003d02e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003d737`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cffc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d01d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d03a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d14d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d172`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d703`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d724`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d743`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cffc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d01d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d03a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d14d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d172`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d703`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d724`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d743`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003d28e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003d405`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003d28e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003d405`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003cff0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d011`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d141`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d166`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d6f7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d718`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003cff0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d011`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d141`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d166`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d6f7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d718`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003d59b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003d59b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003cef8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003cf1b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003d0ba`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003d0d7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003cef8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003cf1b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003d0ba`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003d0d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003ce9d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003cee3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003cf04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003d0a1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003d0c6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003ce9d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003cee3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003cf04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003d0a1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003d0c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003d266`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003d3cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003d266`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003d3cd`
- `HAL!KeQueryPerformanceCounter` at `0x14003d420`
- `HAL!KeQueryPerformanceCounter` at `0x14003d420`

## pseudocode

```c
__int64 __fastcall UlpDispatchToRequestQueue(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4, __int64 a5)
{
  char v6; // r13
  int v9; // r15d
  __int64 v10; // rdi
  unsigned int v11; // ebx
  _BYTE *v12; // rax
  volatile signed __int32 *v13; // rax
  ULONG_PTR v14; // rdx
  int v15; // eax
  __int64 v16; // rdi
  __int64 v17; // r8
  int v18; // eax
  int v19; // r8d
  char *v20; // rbx
  char *v21; // rdx
  int v22; // eax
  __int64 v23; // r12
  __int64 v24; // rdx
  _QWORD *v25; // rax
  _QWORD *v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // rdx
  _QWORD *v29; // rcx
  volatile signed __int32 *v30; // rdx
  volatile signed __int32 *v31; // rdx
  int v32; // eax
  __int64 v33; // r13
  int v34; // edi
  bool v35; // zf
  unsigned __int64 v36; // rdi
  IRP *v37; // rdi
  KIRQL v38; // r8
  _QWORD **v39; // rcx
  _QWORD *v40; // rdx
  char v41; // bl
  _QWORD *v43; // rax
  int v44; // eax
  int v45; // eax
  KIRQL v46; // al
  __int64 v47; // r9
  KIRQL v48; // bl
  LARGE_INTEGER PerformanceCounter; // rax
  ULONG_PTR v50; // rdx
  int v51; // eax
  PIRP v52; // rbx
  ULONG_PTR FsContext; // rbx
  __int64 v54; // rdi
  _QWORD *v55; // rdx
  unsigned int v56; // ebx
  const wchar_t *v57; // rcx
  int v58; // r8d
  __int64 v59; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v61; // r9
  void *CurrentServerSilo; // r12
  __int64 v63; // rcx
  int v64; // eax
  int v65; // eax
  __int64 v66; // rdi
  USHORT CurrentNodeNumber; // ax
  char v68; // r13
  __int64 v69; // rax
  __int64 v70; // r12
  ULONG v71; // r13d
  ULONG_PTR v72; // rdx
  int v73; // ecx
  __int64 v74; // r13
  __int64 v75; // rcx
  unsigned int v76; // ebx
  unsigned int v77; // ebx
  __int64 v78; // r8
  char ConsumerFromIrp; // al
  int v80; // r8d
  char v81; // [rsp+50h] [rbp-B0h]
  char v82; // [rsp+51h] [rbp-AFh]
  PVOID Entry; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v84; // [rsp+60h] [rbp-A0h] BYREF
  PIRP v85; // [rsp+68h] [rbp-98h] BYREF
  _BYTE *v86; // [rsp+70h] [rbp-90h]
  __int128 v87; // [rsp+78h] [rbp-88h]
  _DWORD v88[24]; // [rsp+90h] [rbp-70h] BYREF

  v6 = a3;
  *(_QWORD *)&v87 = a5;
  v86 = a4;
  v82 = a3;
  v85 = 0;
  Entry = 0;
  v81 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a2 )
      v75 = *(_QWORD *)(a2 + 64);
    else
      v75 = 0;
    WPP_SF_qqilqq(v75, a5, a3, a1, a2, v75, (unsigned __int8)a3, a4, a5);
  }
  *a4 = 0;
  *(_BYTE *)(a2 + 1852) = 1;
  if ( !v6 && !*(_BYTE *)(a2 + 1851) )
  {
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 96));
    *(_BYTE *)(a2 + 1851) = 1;
  }
  v9 = UlpOpenCoupling(*(_QWORD *)(a2 + 24), a1, &Entry);
  if ( v9 >= 0 )
  {
    KeEnterCriticalRegion();
    v84 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 280), 0);
    v10 = v84;
    if ( v6 )
    {
      if ( !*(_QWORD *)(a1 + 296) )
      {
        v9 = 0;
        goto LABEL_22;
      }
    }
    else
    {
      v11 = *(_DWORD *)(a1 + 248);
      if ( v11 )
      {
        if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          WPP_SF_d(1032, 137, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v11);
        if ( v11 == 4 )
        {
          v56 = 24;
        }
        else if ( v11 == 2 )
        {
          v56 = 22;
        }
        else
        {
          v76 = v11 - 1;
          if ( v76 )
          {
            v77 = v76 - 2;
            if ( v77 )
            {
              if ( v77 == 2 )
                v56 = 26;
              else
                v56 = 20;
            }
            else
            {
              v56 = 23;
            }
          }
          else
          {
            v56 = 25;
          }
        }
        if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        {
          WPP_SF_d(1032, 138, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v56);
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_qiLq(1032, 235, v78, a2, *(_QWORD *)(a2 + 64), v56, a1);
        }
        *(_DWORD *)(a2 + 500) = *(_DWORD *)(a2 + 496);
        *(_DWORD *)(a2 + 496) = 11;
        *(_DWORD *)(a2 + 1868) = v56;
        *(_DWORD *)(a2 + 1968) = *(_DWORD *)(a1 + 252);
        v57 = *(const wchar_t **)(a1 + 168);
        if ( !v57 )
          v57 = L"<<unnamed>>";
        UxCaptureWideStringZ(v57);
        if ( (BYTE9(xmmword_1401A2C90) & 0x40) != 0 )
          WPP_SF_qidsH(
            5 * v56,
            (unsigned int)ErrorTable,
            v58,
            a2,
            *(_QWORD *)(a2 + 64),
            v56,
            *(_QWORD *)&ErrorTable[40 * v56 + 16],
            *(_WORD *)&ErrorTable[40 * v56 + 4]);
        if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          WPP_SF_(1032, 237, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
        v9 = -1073741769;
        goto LABEL_22;
      }
    }
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a2 + 1704, 0);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx((char *)Entry + 72, 0);
    if ( *((_BYTE *)Entry + 80) )
      goto LABEL_20;
    if ( v6 )
    {
      if ( *(_BYTE *)(a2 + 1853) )
      {
        v9 = 0;
        goto LABEL_21;
      }
      *(_DWORD *)(a2 + 1740) = 1;
      UlpToggleRequestQueueTimer(a2, 0);
    }
    else
    {
      v12 = Entry;
      *(_DWORD *)(a2 + 1740) = 2;
      if ( v12[81] || !*(_DWORD *)(a1 + 272) )
      {
        v12[81] = 0;
        v81 = 1;
      }
    }
    if ( !*(_QWORD *)(a2 + 1712) )
    {
      v13 = (volatile signed __int32 *)Entry;
      *(_QWORD *)(a2 + 1712) = Entry;
      v14 = (ULONG_PTR)(v13 + 5);
      v15 = _InterlockedIncrement(v13 + 5);
      if ( UxDebugCheckRefcount )
      {
        if ( v15 <= -1 )
          UlBugCheckEx(3u, v14, 0x26u, v15);
      }
    }
    if ( v6 )
    {
      v17 = *(_QWORD *)(a1 + 296);
      v16 = 3024;
    }
    else
    {
      v16 = 3072;
      v17 = *((_QWORD *)Entry + 11);
    }
    v18 = UlpSubmitRequest(a1, a2, v17, &v85);
    if ( v18 == -1073741110 )
    {
      UlSetErrorCode(a2, 23, a1);
LABEL_19:
      v10 = v84;
LABEL_20:
      v9 = -1073741436;
LABEL_21:
      ExReleasePushLockExclusiveEx((char *)Entry + 72, 0);
      KeLeaveCriticalRegion();
      ExReleasePushLockExclusiveEx(a2 + 1704, 0);
      KeLeaveCriticalRegion();
LABEL_22:
      ExReleaseCacheAwarePushLockSharedEx(v10, 0);
      KeLeaveCriticalRegion();
      goto LABEL_23;
    }
    if ( v18 )
    {
      if ( v18 == 259 )
      {
        *v86 = 1;
        v45 = _InterlockedIncrement((volatile signed __int32 *)(a2 + 48));
        if ( UxDebugCheckRefcount && v45 <= -1 )
          UlBugCheckEx(3u, a2 + 48, 0xCu, v45);
        *(_DWORD *)(a2 + 1736) = 1;
        if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          WPP_SF_qq(1032, 226, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a2, *(_QWORD *)(a2 + 64));
        v46 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a2 + 24) + 640LL));
        LOBYTE(v47) = 1;
        v48 = v46;
        UlSetBundleTimerEx(*(_QWORD *)(a2 + 24) + 648LL, 5, 0, v47);
        KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a2 + 24) + 640LL), v48);
        if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          WPP_SF_(1032, 227, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
        PerformanceCounter = KeQueryPerformanceCounter(0);
        if ( !*(_QWORD *)(a2 + v16) )
          *(LARGE_INTEGER *)(a2 + v16) = PerformanceCounter;
        v10 = v84;
        v9 = 0;
        goto LABEL_21;
      }
      goto LABEL_19;
    }
    v50 = a2 + 48;
    *v86 = 1;
    v51 = _InterlockedIncrement((volatile signed __int32 *)(a2 + 48));
    if ( UxDebugCheckRefcount && v51 <= -1 )
      UlBugCheckEx(3u, v50, 0xCu, v51);
    v52 = v85;
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_q(1032, 132, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v85);
    FsContext = (ULONG_PTR)v52->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_q(1032, 133, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, FsContext);
    v54 = *(_QWORD *)(a2 + 1712);
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_qqqL(1032, 183, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a2, *(_QWORD *)(a2 + 64), FsContext, 0);
    if ( *(_BYTE *)(v54 + 80) && (BYTE10(xmmword_1401A2C90) & 0x40) != 0 )
      WPP_SF_qLLqqZq(
        *(_QWORD *)(FsContext + 8),
        v50,
        v19,
        a2,
        *(_DWORD *)(a2 + 1736),
        *(_DWORD *)(a2 + 1740),
        FsContext,
        *(_QWORD *)(FsContext + 8),
        *(_QWORD *)(FsContext + 8) + 160LL,
        v54);
    *(_DWORD *)(a2 + 1736) = 2;
    v55 = *(_QWORD **)(v54 + 104);
    if ( *v55 != v54 + 96 )
      goto LABEL_91;
    *(_QWORD *)(a2 + 1720) = v54 + 96;
    *(_QWORD *)(a2 + 1728) = v55;
    *v55 = a2 + 1720;
    *(_QWORD *)(v54 + 104) = a2 + 1720;
    if ( *(_DWORD *)(FsContext + 40) == 1 && !*(_QWORD *)(v54 + 88) )
    {
      *(_QWORD *)(v54 + 88) = FsContext;
      v65 = _InterlockedIncrement((volatile signed __int32 *)FsContext);
      if ( UxDebugCheckRefcount )
      {
        if ( v65 <= -1 )
          UlBugCheckEx(3u, FsContext, 0xEu, v65);
      }
    }
    if ( *(_DWORD *)(FsContext + 40) == 4 )
      *(_BYTE *)(a2 + 1853) = 1;
    *(_QWORD *)(a2 + 1744) = FsContext;
    v64 = _InterlockedIncrement((volatile signed __int32 *)FsContext);
    if ( UxDebugCheckRefcount && v64 <= -1 )
      UlBugCheckEx(3u, FsContext, 9u, v64);
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_d(1032, 186, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, 1);
    ExReleasePushLockExclusiveEx((char *)Entry + 72, 0);
    KeLeaveCriticalRegion();
    ExReleasePushLockExclusiveEx(a2 + 1704, 0);
    KeLeaveCriticalRegion();
    ExReleaseCacheAwarePushLockSharedEx(v84, 0);
    KeLeaveCriticalRegion();
    UlCopyRequestToIrp(a2, v85, 1);
    v9 = 0;
    v85 = 0;
  }
LABEL_23:
  v20 = (char *)Entry;
  if ( !Entry )
    goto LABEL_46;
  v21 = (char *)Entry + 20;
  v22 = _InterlockedDecrement((volatile signed __int32 *)Entry + 5);
  if ( UxDebugCheckRefcount && v22 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v21, 0xAu, v22);
  if ( !v22 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v20, 0);
    v23 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 8) + 264LL)
                    + 8LL * *(unsigned __int16 *)(*((_QWORD *)v20 + 7) + 56LL));
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(*((_QWORD *)v20 + 7) + 944LL, 0);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v23, 0);
    v24 = *((_QWORD *)v20 + 3);
    v25 = v20 + 24;
    if ( *(char **)(v24 + 8) == v20 + 24 )
    {
      v26 = (_QWORD *)*((_QWORD *)v20 + 4);
      if ( (_QWORD *)*v26 == v25 )
      {
        *v26 = v24;
        *(_QWORD *)(v24 + 8) = v26;
        *v25 = 0;
        *((_QWORD *)v20 + 4) = 0;
        v27 = v20 + 40;
        v28 = *((_QWORD *)v20 + 5);
        if ( *(char **)(v28 + 8) == v20 + 40 )
        {
          v29 = (_QWORD *)*((_QWORD *)v20 + 6);
          if ( (_QWORD *)*v29 == v27 )
          {
            *v29 = v28;
            *(_QWORD *)(v28 + 8) = v29;
            *v27 = 0;
            *((_QWORD *)v20 + 6) = 0;
            ExReleasePushLockExclusiveEx(v23, 0);
            KeLeaveCriticalRegion();
            ExReleasePushLockExclusiveEx(*((_QWORD *)v20 + 7) + 944LL, 0);
            KeLeaveCriticalRegion();
            v30 = (volatile signed __int32 *)*((_QWORD *)v20 + 11);
            if ( v30 )
            {
              v44 = _InterlockedDecrement(v30);
              if ( UxDebugCheckRefcount && v44 <= -1 )
                UlBugCheckEx(3u, (ULONG_PTR)v30, 0xEu, v44);
              if ( !v44 )
                UlConsumerCleanupCompletion(*((_QWORD *)v20 + 11));
              *((_QWORD *)v20 + 11) = 0;
            }
            v31 = (volatile signed __int32 *)*((_QWORD *)v20 + 8);
            v32 = _InterlockedDecrement(v31);
            if ( UxDebugCheckRefcount && v32 <= -1 )
              UlBugCheckEx(3u, (ULONG_PTR)v31, 0xEu, v32);
            if ( !v32 )
              UlFreeRequestQueue(*((PVOID *)v20 + 8));
            *((_QWORD *)v20 + 8) = 0;
            v33 = *((_QWORD *)v20 + 7);
            v34 = _InterlockedDecrement((volatile signed __int32 *)(v33 + 40));
            if ( UxDebugCheckRefcount && v34 <= -1 )
              UlBugCheckEx(3u, v33 + 40, 0xEu, v34);
            if ( v34 )
              goto LABEL_38;
            v59 = v33 + 64;
            CurrentProcess = IoGetCurrentProcess();
            CurrentServerSilo = *(void **)(v33 + 1088);
            v63 = *(_QWORD *)(v33 + 64);
            if ( UxSystemProcess != CurrentProcess )
            {
              if ( v63 || *(_QWORD *)(v33 + 80) || *(_QWORD *)(v33 + 96) )
                UlBugCheckEx(1u, v33 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
              LOBYTE(v61) = 1;
              UlThreadPoolEnqueueWorkItem(0, v33 + 64, UlFreeHttpConnection, v61, CurrentServerSilo, -1);
              goto LABEL_38;
            }
            if ( v63 || *(_QWORD *)(v33 + 80) || *(_QWORD *)(v33 + 96) )
              UlBugCheckEx(1u, v33 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
            if ( KeGetCurrentIrql() )
            {
              v71 = 0;
              if ( (unsigned int)dword_1401A3F48 > 1 )
              {
                v71 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
                if ( byte_1401A3F60 )
                  v71 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
              }
              if ( CurrentServerSilo == (void *)-1LL )
                CurrentServerSilo = (void *)PsGetCurrentServerSilo();
              *(_QWORD *)(v59 + 32) = CurrentServerSilo;
              v84 = 0;
              if ( CurrentServerSilo )
                ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
              PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v84);
              v72 = v84 + 24;
              v73 = _InterlockedIncrement((volatile signed __int32 *)(v84 + 24));
              if ( UxDebugCheckRefcount && v73 <= -1 )
                UlBugCheckEx(3u, v72, 0xDu, v73);
              *(_BYTE *)(v59 + 24) = 1;
              v74 = *(_QWORD *)(qword_1401A3F50 + 8LL * v71);
              *(_QWORD *)(v59 + 16) = UlFreeHttpConnection;
              if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v74 + 16), (PSLIST_ENTRY)v59) )
              {
                KeSetEvent((PRKEVENT)(v74 + 32), 0, 0);
                UlpActivateThreadPoolQueue((PVOID)v74);
              }
              goto LABEL_38;
            }
            v68 = 0;
            v87 = 0;
            if ( CurrentServerSilo == (void *)-1LL )
            {
              v70 = *((_QWORD *)&v87 + 1);
            }
            else
            {
              v69 = PsAttachSiloToCurrentThread(CurrentServerSilo);
              v84 = v69;
              v68 = 1;
              if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
              {
                WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v69, CurrentServerSilo);
                UlFreeHttpConnection(v59);
                v70 = v84;
                goto LABEL_142;
              }
              v70 = v69;
            }
            UlFreeHttpConnection(v59);
            if ( !v68 )
            {
LABEL_38:
              v35 = UxDebugDisableLookaside == 0;
              *((_QWORD *)v20 + 7) = 0;
              *((_DWORD *)v20 + 4) = 1969441909;
              if ( v35 )
              {
                if ( UxCompactMode )
                {
                  v66 = qword_1401A0910;
                  CurrentNodeNumber = KeGetCurrentNodeNumber();
                  PplFreeToLookasideListProcessor(v66, v20, CurrentNodeNumber);
                }
                else
                {
                  v36 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v20 + 1) << 7);
                  if ( !*(_BYTE *)(v36 + 176) )
                    PplpLazyInitializeLookasideList(qword_1401A0910, v36 + 64);
                  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v36 + 64), v20);
                }
              }
              else
              {
                memset(v88, 0, sizeof(v88));
                v88[10] = dword_1401A0928;
                ((void (__fastcall *)(char *, _DWORD *))off_1401A0938)(v20, v88);
              }
              if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
                WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
              goto LABEL_45;
            }
LABEL_142:
            if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
              WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v70);
            PsDetachSiloFromCurrentThread(v70);
            goto LABEL_38;
          }
        }
      }
    }
LABEL_91:
    __fastfail(3u);
  }
LABEL_45:
  v6 = v82;
  Entry = 0;
LABEL_46:
  if ( v81 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_q(1032, 159, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1);
    v37 = 0;
    v38 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 64));
    v39 = (_QWORD **)(a1 + 72);
    while ( 1 )
    {
      v40 = *v39;
      if ( *v39 == v39 )
        break;
      if ( (_QWORD **)v40[1] != v39 )
        goto LABEL_91;
      v43 = (_QWORD *)*v40;
      if ( *(_QWORD **)(*v40 + 8LL) != v40 )
        goto LABEL_91;
      *v39 = v43;
      v37 = (IRP *)(v40 - 21);
      v43[1] = v39;
      *v40 = 0;
      v40[1] = 0;
      --*(_DWORD *)(a1 + 88);
      if ( _InterlockedExchange64(v40 - 8, 0) )
      {
        if ( v40 != (_QWORD *)168 )
          break;
      }
      else
      {
        v37 = 0;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 64), v38);
    if ( v37 )
    {
      ConsumerFromIrp = UlGetConsumerFromIrp(v37);
      v37->IoStatus.Status = 0;
      v37->IoStatus.Information = 0;
      if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_qqqZ(a1 + 160, 160, v80, (_DWORD)v37, ConsumerFromIrp, a1, a1 + 160);
      IofCompleteRequest(v37, 2);
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 161, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  }
  if ( v9 < 0 )
  {
    if ( !v6 )
      _InterlockedIncrement64((volatile signed __int64 *)(a1 + 104));
    UlpLogRequestQueueOverflowEvents(a1, a2);
  }
  else
  {
    v41 = byte_1401A3780;
    if ( SBYTE2(xmmword_1401A2CA0) < 0 )
      WPP_SF_d(1047, 10, WPP_b6616b8acc683c557a6f97eb9025b7cb_Traceguids, (unsigned __int8)byte_1401A3780);
    if ( v41 )
      UxPktMonTraceHttpReceive(a2, 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_Dd(1032, 192, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, (unsigned __int8)*v86, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14003cde0  push    rbp
0x14003cde2  push    rbx
0x14003cde3  push    rsi
0x14003cde4  push    r13
0x14003cde6  push    r14
0x14003cde8  push    r15
0x14003cdea  lea     rbp, [rsp-8]
0x14003cdef  sub     rsp, 108h
0x14003cdf6  mov     rax, cs:__security_cookie
0x14003cdfd  xor     rax, rsp
0x14003ce00  mov     [rbp+30h+var_40], rax
0x14003ce04  mov     rsi, rdx
0x14003ce07  movzx   r13d, r8b
0x14003ce0b  mov     rdx, [rbp+30h+arg_20]
0x14003ce0f  mov     rbx, r9
0x14003ce12  mov     qword ptr [rsp+130h+var_B8], rdx
0x14003ce17  mov     r14, rcx
0x14003ce1a  mov     [rsp+130h+var_C0], rbx
0x14003ce1f  mov     [rsp+130h+var_DF], r13b
0x14003ce24  mov     [rsp+130h+var_C8], 0
0x14003ce2d  mov     [rsp+130h+Entry], 0
0x14003ce36  mov     [rsp+130h+var_E0], 0
0x14003ce3b  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003ce42  jnz     loc_14003DB80
0x14003ce48  mov     byte ptr [rbx], 0
0x14003ce4b  mov     byte ptr [rsi+73Ch], 1
0x14003ce52  test    r13b, r13b
0x14003ce55  jnz     short loc_14003CE6C
0x14003ce57  cmp     [rsi+73Bh], r13b
0x14003ce5e  jnz     short loc_14003CE6C
0x14003ce60  lock inc qword ptr [r14+60h]
0x14003ce65  mov     byte ptr [rsi+73Bh], 1
0x14003ce6c  mov     rcx, [rsi+18h]
0x14003ce70  lea     r8, [rsp+130h+Entry]
0x14003ce75  mov     [rsp+130h+arg_10], rdi
0x14003ce7d  mov     rdx, r14
0x14003ce80  mov     [rsp+130h+var_30], r12
0x14003ce88  call    UlpOpenCoupling
0x14003ce8d  mov     r15d, eax
0x14003ce90  mov     ebx, 1
0x14003ce95  test    eax, eax
0x14003ce97  js      loc_14003D046
0x14003ce9d  call    cs:__imp_KeEnterCriticalRegion
0x14003cea4  nop     dword ptr [rax+rax+00h]
0x14003cea9  mov     rcx, [r14+118h]
0x14003ceb0  xor     edx, edx
0x14003ceb2  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14003ceb9  nop     dword ptr [rax+rax+00h]
0x14003cebe  mov     [rsp+130h+var_D0], rax
0x14003cec3  mov     rdi, rax
0x14003cec6  test    r13b, r13b
0x14003cec9  jnz     loc_14003DCA3
0x14003cecf  mov     ebx, [r14+0F8h]
0x14003ced6  test    ebx, ebx
0x14003ced8  jnz     loc_14003D4FE
0x14003cede  mov     ebx, 1
0x14003cee3  call    cs:__imp_KeEnterCriticalRegion
0x14003ceea  nop     dword ptr [rax+rax+00h]
0x14003ceef  xor     edx, edx
0x14003cef1  lea     rcx, [rsi+6A8h]
0x14003cef8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003ceff  nop     dword ptr [rax+rax+00h]
0x14003cf04  call    cs:__imp_KeEnterCriticalRegion
0x14003cf0b  nop     dword ptr [rax+rax+00h]
0x14003cf10  mov     rcx, [rsp+130h+Entry]
0x14003cf15  xor     edx, edx
0x14003cf17  add     rcx, 48h ; 'H'
0x14003cf1b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003cf22  nop     dword ptr [rax+rax+00h]
0x14003cf27  mov     rax, [rsp+130h+Entry]
0x14003cf2c  cmp     byte ptr [rax+50h], 0
0x14003cf30  jnz     loc_14003CFDF
0x14003cf36  test    r13b, r13b
0x14003cf39  jnz     loc_14003DCB9
0x14003cf3f  mov     rax, [rsp+130h+Entry]
0x14003cf44  mov     dword ptr [rsi+6CCh], 2
0x14003cf4e  cmp     byte ptr [rax+51h], 0
0x14003cf52  jnz     loc_14003D461
0x14003cf58  cmp     dword ptr [r14+110h], 0
0x14003cf60  jz      loc_14003D461
0x14003cf66  cmp     qword ptr [rsi+6B0h], 0
0x14003cf6e  jnz     short loc_14003CF95
0x14003cf70  mov     rax, [rsp+130h+Entry]
0x14003cf75  mov     [rsi+6B0h], rax
0x14003cf7c  lea     rdx, [rax+14h]; BugCheckParameter2
0x14003cf80  mov     eax, ebx
0x14003cf82  lock xadd [rdx], eax
0x14003cf86  inc     eax
0x14003cf88  cmp     cs:UxDebugCheckRefcount, 0
0x14003cf8f  jnz     loc_14003D444
0x14003cf95  test    r13b, r13b
0x14003cf98  jnz     loc_14003D9D8
0x14003cf9e  mov     rax, [rsp+130h+Entry]
0x14003cfa3  mov     edi, 0C00h
0x14003cfa8  mov     r8, [rax+58h]
0x14003cfac  lea     r9, [rsp+130h+var_C8]
0x14003cfb1  mov     rdx, rsi
0x14003cfb4  mov     rcx, r14
0x14003cfb7  call    UlpSubmitRequest
0x14003cfbc  cmp     eax, 0C00002CAh
0x14003cfc1  jz      loc_14003DDB5
0x14003cfc7  test    eax, eax
0x14003cfc9  jz      loc_14003D46F
0x14003cfcf  cmp     eax, 103h
0x14003cfd4  jz      loc_14003D38E
0x14003cfda  mov     rdi, [rsp+130h+var_D0]
0x14003cfdf  mov     r15d, 0C0000184h
0x14003cfe5  mov     rcx, [rsp+130h+Entry]
0x14003cfea  xor     edx, edx
0x14003cfec  add     rcx, 48h ; 'H'
0x14003cff0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003cff7  nop     dword ptr [rax+rax+00h]
0x14003cffc  call    cs:__imp_KeLeaveCriticalRegion
0x14003d003  nop     dword ptr [rax+rax+00h]
0x14003d008  xor     edx, edx
0x14003d00a  lea     rcx, [rsi+6A8h]
0x14003d011  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003d018  nop     dword ptr [rax+rax+00h]
0x14003d01d  call    cs:__imp_KeLeaveCriticalRegion
0x14003d024  nop     dword ptr [rax+rax+00h]
0x14003d029  xor     edx, edx
0x14003d02b  mov     rcx, rdi
0x14003d02e  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14003d035  nop     dword ptr [rax+rax+00h]
0x14003d03a  call    cs:__imp_KeLeaveCriticalRegion
0x14003d041  nop     dword ptr [rax+rax+00h]
0x14003d046  mov     rbx, [rsp+130h+Entry]
0x14003d04b  test    rbx, rbx
0x14003d04e  jz      loc_14003D24C
0x14003d054  mov     edi, 0FFFFFFFFh
0x14003d059  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14003d05d  mov     eax, edi
0x14003d05f  lock xadd [rdx], eax
0x14003d063  dec     eax
0x14003d065  cmp     cs:UxDebugCheckRefcount, 0
0x14003d06c  jnz     loc_14003D60B
0x14003d072  test    eax, eax
0x14003d074  jnz     loc_14003D23D
0x14003d07a  xor     r13d, r13d
0x14003d07d  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003d084  jnz     loc_14003D9F8
0x14003d08a  mov     rax, [rbx+38h]
0x14003d08e  movzx   edx, word ptr [rax+38h]
0x14003d092  mov     rax, [rbx+40h]
0x14003d096  mov     rcx, [rax+108h]
0x14003d09d  mov     r12, [rcx+rdx*8]
0x14003d0a1  call    cs:__imp_KeEnterCriticalRegion
0x14003d0a8  nop     dword ptr [rax+rax+00h]
0x14003d0ad  mov     rcx, [rbx+38h]
0x14003d0b1  xor     edx, edx
0x14003d0b3  add     rcx, 3B0h
0x14003d0ba  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003d0c1  nop     dword ptr [rax+rax+00h]
0x14003d0c6  call    cs:__imp_KeEnterCriticalRegion
0x14003d0cd  nop     dword ptr [rax+rax+00h]
0x14003d0d2  xor     edx, edx
0x14003d0d4  mov     rcx, r12
0x14003d0d7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003d0de  nop     dword ptr [rax+rax+00h]
0x14003d0e3  mov     rdx, [rbx+18h]
0x14003d0e7  lea     rax, [rbx+18h]
0x14003d0eb  cmp     [rdx+8], rax
0x14003d0ef  jnz     loc_14003D4F7
0x14003d0f5  mov     rcx, [rax+8]
0x14003d0f9  cmp     [rcx], rax
0x14003d0fc  jnz     loc_14003D4F7
0x14003d102  mov     [rcx], rdx
0x14003d105  mov     [rdx+8], rcx
0x14003d109  mov     [rax], r13
0x14003d10c  mov     [rax+8], r13
0x14003d110  lea     rax, [rbx+28h]
0x14003d114  mov     rdx, [rax]
0x14003d117  cmp     [rdx+8], rax
0x14003d11b  jnz     loc_14003D4F7
0x14003d121  mov     rcx, [rax+8]
0x14003d125  cmp     [rcx], rax
0x14003d128  jnz     loc_14003D4F7
0x14003d12e  mov     [rcx], rdx
0x14003d131  mov     [rdx+8], rcx
0x14003d135  xor     edx, edx
0x14003d137  mov     rcx, r12
0x14003d13a  mov     [rax], r13
0x14003d13d  mov     [rax+8], r13
0x14003d141  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003d148  nop     dword ptr [rax+rax+00h]
0x14003d14d  call    cs:__imp_KeLeaveCriticalRegion
0x14003d154  nop     dword ptr [rax+rax+00h]
0x14003d159  mov     rcx, [rbx+38h]
0x14003d15d  xor     edx, edx
0x14003d15f  add     rcx, 3B0h
0x14003d166  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003d16d  nop     dword ptr [rax+rax+00h]
0x14003d172  call    cs:__imp_KeLeaveCriticalRegion
0x14003d179  nop     dword ptr [rax+rax+00h]
0x14003d17e  mov     rdx, [rbx+58h]; BugCheckParameter2
0x14003d182  test    rdx, rdx
0x14003d185  jnz     loc_14003D368
0x14003d18b  mov     rdx, [rbx+40h]; BugCheckParameter2
0x14003d18f  mov     eax, edi
0x14003d191  lock xadd [rdx], eax
0x14003d195  dec     eax
0x14003d197  cmp     cs:UxDebugCheckRefcount, 0
0x14003d19e  jnz     loc_14003D627
0x14003d1a4  test    eax, eax
0x14003d1a6  jz      loc_14003DDD8
0x14003d1ac  mov     [rbx+40h], r13
0x14003d1b0  mov     r13, [rbx+38h]
0x14003d1b4  lea     rdx, [r13+28h]; BugCheckParameter2
0x14003d1b8  lock xadd [rdx], edi
0x14003d1bc  dec     edi
0x14003d1be  cmp     cs:UxDebugCheckRefcount, 0
0x14003d1c5  jnz     loc_14003D643
0x14003d1cb  test    edi, edi
0x14003d1cd  jz      loc_14003D597
0x14003d1d3  cmp     cs:UxDebugDisableLookaside, 0
0x14003d1da  mov     qword ptr [rbx+38h], 0
0x14003d1e2  mov     dword ptr [rbx+10h], 75634C75h
0x14003d1e9  jnz     loc_14003DE31
0x14003d1ef  cmp     cs:UxCompactMode, 0
0x14003d1f6  jnz     loc_14003D7F2
0x14003d1fc  mov     edi, [rbx]
0x14003d1fe  mov     r8, cs:qword_1401A0910
0x14003d205  inc     edi
0x14003d207  shl     rdi, 7
0x14003d20b  add     rdi, r8
0x14003d20e  movzx   eax, byte ptr [rdi+0B0h]
0x14003d215  test    al, al
0x14003d217  jz      loc_14003DA98
0x14003d21d  mov     rdx, rbx; Entry
0x14003d220  lea     rcx, [rdi+40h]; Lookaside
0x14003d224  call    cs:__imp_ExFreeToLookasideListEx
0x14003d22b  nop     dword ptr [rax+rax+00h]
0x14003d230  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003d237  jnz     loc_14003DA1B
0x14003d23d  movzx   r13d, [rsp+130h+var_DF]
0x14003d243  mov     [rsp+130h+Entry], 0
0x14003d24c  cmp     [rsp+130h+var_E0], 0
0x14003d251  jz      short loc_14003D2B0
0x14003d253  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003d25a  jnz     loc_14003DA36
0x14003d260  xor     edi, edi
0x14003d262  lea     rcx, [r14+40h]; SpinLock
0x14003d266  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003d26d  nop     dword ptr [rax+rax+00h]
0x14003d272  movzx   r8d, al
0x14003d276  lea     rcx, [r14+48h]
0x14003d27a  mov     rdx, [rcx]
0x14003d27d  cmp     rdx, rcx
0x14003d280  jnz     loc_14003D313
0x14003d286  movzx   edx, r8b; NewIrql
0x14003d28a  lea     rcx, [r14+40h]; SpinLock
0x14003d28e  call    cs:__imp_KeReleaseSpinLock
0x14003d295  nop     dword ptr [rax+rax+00h]
0x14003d29a  test    rdi, rdi
0x14003d29d  jnz     loc_14003DE6A
0x14003d2a3  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003d2aa  jnz     loc_14003DA7D
0x14003d2b0  test    r15d, r15d
0x14003d2b3  js      loc_14003DEB7
0x14003d2b9  movzx   ebx, cs:byte_1401A3780
0x14003d2c0  cmp     byte ptr cs:xmmword_1401A2CA0+2, 0
0x14003d2c7  jl      loc_14003DB44
0x14003d2cd  test    bl, bl
0x14003d2cf  jnz     loc_14003D9E9
0x14003d2d5  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003d2dc  jnz     loc_14003DA54
0x14003d2e2  mov     r12, [rsp+130h+var_30]
0x14003d2ea  mov     eax, r15d
0x14003d2ed  mov     rdi, [rsp+130h+arg_10]
0x14003d2f5  mov     rcx, [rbp+30h+var_40]
0x14003d2f9  xor     rcx, rsp; StackCookie
0x14003d2fc  call    __security_check_cookie
0x14003d301  add     rsp, 108h
0x14003d308  pop     r15
0x14003d30a  pop     r14
0x14003d30c  pop     r13
0x14003d30e  pop     rsi
0x14003d30f  pop     rbx
0x14003d310  pop     rbp
0x14003d311  retn
0x14003d313  cmp     [rdx+8], rcx
0x14003d317  jnz     loc_14003D4F7
0x14003d31d  mov     rax, [rdx]
0x14003d320  cmp     [rax+8], rdx
0x14003d324  jnz     loc_14003D4F7
0x14003d32a  mov     [rcx], rax
0x14003d32d  lea     rdi, [rdx-0A8h]
0x14003d334  mov     [rax+8], rcx
0x14003d338  xor     eax, eax
0x14003d33a  mov     qword ptr [rdx], 0
0x14003d341  mov     qword ptr [rdx+8], 0
0x14003d349  dec     dword ptr [r14+58h]
0x14003d34d  xchg    rax, [rdi+68h]
0x14003d351  test    rax, rax
0x14003d354  jz      loc_14003DE63
0x14003d35a  test    rdi, rdi
0x14003d35d  jz      loc_14003D27A
0x14003d363  jmp     loc_14003D286
0x14003d368  mov     eax, edi
0x14003d36a  lock xadd [rdx], eax
  ... truncated ...
```
