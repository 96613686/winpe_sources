# UlpDispatchToRequestQueue

- ea: `0x14003cdc0`
- end: `0x14003deaa`
- name: `UlpDispatchToRequestQueue`
- size: `4330`
- prototype: ``
- caller_count: `3`
- callee_count: `35`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002cfc0`
- `0x14002dd70`
- `0x14003cd00`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140013430`
- `0x140022610`
- `0x14003bbdc`
- `0x14003bf00`
- `0x14003c124`
- `0x14003cdc0`
- `0x14003deb0`
- `0x14003e640`
- `0x140049d08`
- `0x14005dfd0`
- `0x14005e030`
- `0x140090ef0`
- `0x14009620c`
- `0x14009c7c4`
- `0x1400a031c`
- `0x1400a7a74`
- `0x1400cf108`
- `0x14013dd68`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
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

- `ntoskrnl!KeGetCurrentIrql` at `0x14003d7f9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003d7f9`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003d92f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003d92f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d204`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d204`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003d885`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003d885`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003d8e2`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003d8e2`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14003de00`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14003de00`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003d821`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003d821`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003d866`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003d866`
- `ntoskrnl!KeSetEvent` at `0x14003d94d`
- `ntoskrnl!KeSetEvent` at `0x14003d94d`
- `ntoskrnl!IofCompleteRequest` at `0x140175adf`
- `ntoskrnl!IofCompleteRequest` at `0x140175adf`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14003d8af`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14003d8af`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14003ce92`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14003ce92`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003d7d9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003d7d9`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003d00e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003d717`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003d00e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003d717`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cfdc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cffd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d01a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d12d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d152`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d6e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d704`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d723`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cfdc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cffd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d01a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d12d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d152`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d6e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d704`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003d723`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003d26e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003d3e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003d26e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003d3e5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003cfd0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003cff1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d121`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d146`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d6d7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d6f8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003cfd0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003cff1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d121`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d146`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d6d7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003d6f8`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003d57b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003d57b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003ced8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003cefb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003d09a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003d0b7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003ced8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003cefb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003d09a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003d0b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003ce7d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003cec3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003cee4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003d081`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003d0a6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003ce7d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003cec3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003cee4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003d081`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003d0a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003d246`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003d3ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003d246`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003d3ad`
- `HAL!KeQueryPerformanceCounter` at `0x14003d400`
- `HAL!KeQueryPerformanceCounter` at `0x14003d400`

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
          WPP_SF_(1032, 237, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids);
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
0x14003cdc0  push    rbp
0x14003cdc2  push    rbx
0x14003cdc3  push    rsi
0x14003cdc4  push    r13
0x14003cdc6  push    r14
0x14003cdc8  push    r15
0x14003cdca  lea     rbp, [rsp-8]
0x14003cdcf  sub     rsp, 108h
0x14003cdd6  mov     rax, cs:__security_cookie
0x14003cddd  xor     rax, rsp
0x14003cde0  mov     [rbp+30h+var_40], rax
0x14003cde4  mov     rsi, rdx
0x14003cde7  movzx   r13d, r8b
0x14003cdeb  mov     rdx, [rbp+30h+arg_20]
0x14003cdef  mov     rbx, r9
0x14003cdf2  mov     qword ptr [rsp+130h+var_B8], rdx
0x14003cdf7  mov     r14, rcx
0x14003cdfa  mov     [rsp+130h+var_C0], rbx
0x14003cdff  mov     [rsp+130h+var_DF], r13b
0x14003ce04  mov     [rsp+130h+var_C8], 0
0x14003ce0d  mov     [rsp+130h+Entry], 0
0x14003ce16  mov     [rsp+130h+var_E0], 0
0x14003ce1b  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003ce22  jnz     loc_14003DB60
0x14003ce28  mov     byte ptr [rbx], 0
0x14003ce2b  mov     byte ptr [rsi+73Ch], 1
0x14003ce32  test    r13b, r13b
0x14003ce35  jnz     short loc_14003CE4C
0x14003ce37  cmp     [rsi+73Bh], r13b
0x14003ce3e  jnz     short loc_14003CE4C
0x14003ce40  lock inc qword ptr [r14+60h]
0x14003ce45  mov     byte ptr [rsi+73Bh], 1
0x14003ce4c  mov     rcx, [rsi+18h]
0x14003ce50  lea     r8, [rsp+130h+Entry]
0x14003ce55  mov     [rsp+130h+arg_10], rdi
0x14003ce5d  mov     rdx, r14
0x14003ce60  mov     [rsp+130h+var_30], r12
0x14003ce68  call    UlpOpenCoupling
0x14003ce6d  mov     r15d, eax
0x14003ce70  mov     ebx, 1
0x14003ce75  test    eax, eax
0x14003ce77  js      loc_14003D026
0x14003ce7d  call    cs:__imp_KeEnterCriticalRegion
0x14003ce84  nop     dword ptr [rax+rax+00h]
0x14003ce89  mov     rcx, [r14+118h]
0x14003ce90  xor     edx, edx
0x14003ce92  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14003ce99  nop     dword ptr [rax+rax+00h]
0x14003ce9e  mov     [rsp+130h+var_D0], rax
0x14003cea3  mov     rdi, rax
0x14003cea6  test    r13b, r13b
0x14003cea9  jnz     loc_14003DC83
0x14003ceaf  mov     ebx, [r14+0F8h]
0x14003ceb6  test    ebx, ebx
0x14003ceb8  jnz     loc_14003D4DE
0x14003cebe  mov     ebx, 1
0x14003cec3  call    cs:__imp_KeEnterCriticalRegion
0x14003ceca  nop     dword ptr [rax+rax+00h]
0x14003cecf  xor     edx, edx
0x14003ced1  lea     rcx, [rsi+6A8h]
0x14003ced8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003cedf  nop     dword ptr [rax+rax+00h]
0x14003cee4  call    cs:__imp_KeEnterCriticalRegion
0x14003ceeb  nop     dword ptr [rax+rax+00h]
0x14003cef0  mov     rcx, [rsp+130h+Entry]
0x14003cef5  xor     edx, edx
0x14003cef7  add     rcx, 48h ; 'H'
0x14003cefb  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003cf02  nop     dword ptr [rax+rax+00h]
0x14003cf07  mov     rax, [rsp+130h+Entry]
0x14003cf0c  cmp     byte ptr [rax+50h], 0
0x14003cf10  jnz     loc_14003CFBF
0x14003cf16  test    r13b, r13b
0x14003cf19  jnz     loc_14003DC99
0x14003cf1f  mov     rax, [rsp+130h+Entry]
0x14003cf24  mov     dword ptr [rsi+6CCh], 2
0x14003cf2e  cmp     byte ptr [rax+51h], 0
0x14003cf32  jnz     loc_14003D441
0x14003cf38  cmp     dword ptr [r14+110h], 0
0x14003cf40  jz      loc_14003D441
0x14003cf46  cmp     qword ptr [rsi+6B0h], 0
0x14003cf4e  jnz     short loc_14003CF75
0x14003cf50  mov     rax, [rsp+130h+Entry]
0x14003cf55  mov     [rsi+6B0h], rax
0x14003cf5c  lea     rdx, [rax+14h]; BugCheckParameter2
0x14003cf60  mov     eax, ebx
0x14003cf62  lock xadd [rdx], eax
0x14003cf66  inc     eax
0x14003cf68  cmp     cs:UxDebugCheckRefcount, 0
0x14003cf6f  jnz     loc_14003D424
0x14003cf75  test    r13b, r13b
0x14003cf78  jnz     loc_14003D9B8
0x14003cf7e  mov     rax, [rsp+130h+Entry]
0x14003cf83  mov     edi, 0C00h
0x14003cf88  mov     r8, [rax+58h]
0x14003cf8c  lea     r9, [rsp+130h+var_C8]
0x14003cf91  mov     rdx, rsi
0x14003cf94  mov     rcx, r14
0x14003cf97  call    UlpSubmitRequest
0x14003cf9c  cmp     eax, 0C00002CAh
0x14003cfa1  jz      loc_14003DD95
0x14003cfa7  test    eax, eax
0x14003cfa9  jz      loc_14003D44F
0x14003cfaf  cmp     eax, 103h
0x14003cfb4  jz      loc_14003D36E
0x14003cfba  mov     rdi, [rsp+130h+var_D0]
0x14003cfbf  mov     r15d, 0C0000184h
0x14003cfc5  mov     rcx, [rsp+130h+Entry]
0x14003cfca  xor     edx, edx
0x14003cfcc  add     rcx, 48h ; 'H'
0x14003cfd0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003cfd7  nop     dword ptr [rax+rax+00h]
0x14003cfdc  call    cs:__imp_KeLeaveCriticalRegion
0x14003cfe3  nop     dword ptr [rax+rax+00h]
0x14003cfe8  xor     edx, edx
0x14003cfea  lea     rcx, [rsi+6A8h]
0x14003cff1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003cff8  nop     dword ptr [rax+rax+00h]
0x14003cffd  call    cs:__imp_KeLeaveCriticalRegion
0x14003d004  nop     dword ptr [rax+rax+00h]
0x14003d009  xor     edx, edx
0x14003d00b  mov     rcx, rdi
0x14003d00e  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14003d015  nop     dword ptr [rax+rax+00h]
0x14003d01a  call    cs:__imp_KeLeaveCriticalRegion
0x14003d021  nop     dword ptr [rax+rax+00h]
0x14003d026  mov     rbx, [rsp+130h+Entry]
0x14003d02b  test    rbx, rbx
0x14003d02e  jz      loc_14003D22C
0x14003d034  mov     edi, 0FFFFFFFFh
0x14003d039  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14003d03d  mov     eax, edi
0x14003d03f  lock xadd [rdx], eax
0x14003d043  dec     eax
0x14003d045  cmp     cs:UxDebugCheckRefcount, 0
0x14003d04c  jnz     loc_14003D5EB
0x14003d052  test    eax, eax
0x14003d054  jnz     loc_14003D21D
0x14003d05a  xor     r13d, r13d
0x14003d05d  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003d064  jnz     loc_14003D9D8
0x14003d06a  mov     rax, [rbx+38h]
0x14003d06e  movzx   edx, word ptr [rax+38h]
0x14003d072  mov     rax, [rbx+40h]
0x14003d076  mov     rcx, [rax+108h]
0x14003d07d  mov     r12, [rcx+rdx*8]
0x14003d081  call    cs:__imp_KeEnterCriticalRegion
0x14003d088  nop     dword ptr [rax+rax+00h]
0x14003d08d  mov     rcx, [rbx+38h]
0x14003d091  xor     edx, edx
0x14003d093  add     rcx, 3B0h
0x14003d09a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003d0a1  nop     dword ptr [rax+rax+00h]
0x14003d0a6  call    cs:__imp_KeEnterCriticalRegion
0x14003d0ad  nop     dword ptr [rax+rax+00h]
0x14003d0b2  xor     edx, edx
0x14003d0b4  mov     rcx, r12
0x14003d0b7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003d0be  nop     dword ptr [rax+rax+00h]
0x14003d0c3  mov     rdx, [rbx+18h]
0x14003d0c7  lea     rax, [rbx+18h]
0x14003d0cb  cmp     [rdx+8], rax
0x14003d0cf  jnz     loc_14003D4D7
0x14003d0d5  mov     rcx, [rax+8]
0x14003d0d9  cmp     [rcx], rax
0x14003d0dc  jnz     loc_14003D4D7
0x14003d0e2  mov     [rcx], rdx
0x14003d0e5  mov     [rdx+8], rcx
0x14003d0e9  mov     [rax], r13
0x14003d0ec  mov     [rax+8], r13
0x14003d0f0  lea     rax, [rbx+28h]
0x14003d0f4  mov     rdx, [rax]
0x14003d0f7  cmp     [rdx+8], rax
0x14003d0fb  jnz     loc_14003D4D7
0x14003d101  mov     rcx, [rax+8]
0x14003d105  cmp     [rcx], rax
0x14003d108  jnz     loc_14003D4D7
0x14003d10e  mov     [rcx], rdx
0x14003d111  mov     [rdx+8], rcx
0x14003d115  xor     edx, edx
0x14003d117  mov     rcx, r12
0x14003d11a  mov     [rax], r13
0x14003d11d  mov     [rax+8], r13
0x14003d121  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003d128  nop     dword ptr [rax+rax+00h]
0x14003d12d  call    cs:__imp_KeLeaveCriticalRegion
0x14003d134  nop     dword ptr [rax+rax+00h]
0x14003d139  mov     rcx, [rbx+38h]
0x14003d13d  xor     edx, edx
0x14003d13f  add     rcx, 3B0h
0x14003d146  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003d14d  nop     dword ptr [rax+rax+00h]
0x14003d152  call    cs:__imp_KeLeaveCriticalRegion
0x14003d159  nop     dword ptr [rax+rax+00h]
0x14003d15e  mov     rdx, [rbx+58h]; BugCheckParameter2
0x14003d162  test    rdx, rdx
0x14003d165  jnz     loc_14003D348
0x14003d16b  mov     rdx, [rbx+40h]; BugCheckParameter2
0x14003d16f  mov     eax, edi
0x14003d171  lock xadd [rdx], eax
0x14003d175  dec     eax
0x14003d177  cmp     cs:UxDebugCheckRefcount, 0
0x14003d17e  jnz     loc_14003D607
0x14003d184  test    eax, eax
0x14003d186  jz      loc_14003DDB8
0x14003d18c  mov     [rbx+40h], r13
0x14003d190  mov     r13, [rbx+38h]
0x14003d194  lea     rdx, [r13+28h]; BugCheckParameter2
0x14003d198  lock xadd [rdx], edi
0x14003d19c  dec     edi
0x14003d19e  cmp     cs:UxDebugCheckRefcount, 0
0x14003d1a5  jnz     loc_14003D623
0x14003d1ab  test    edi, edi
0x14003d1ad  jz      loc_14003D577
0x14003d1b3  cmp     cs:UxDebugDisableLookaside, 0
0x14003d1ba  mov     qword ptr [rbx+38h], 0
0x14003d1c2  mov     dword ptr [rbx+10h], 75634C75h
0x14003d1c9  jnz     loc_14003DE11
0x14003d1cf  cmp     cs:UxCompactMode, 0
0x14003d1d6  jnz     loc_14003D7D2
0x14003d1dc  mov     edi, [rbx]
0x14003d1de  mov     r8, cs:qword_1401A0910
0x14003d1e5  inc     edi
0x14003d1e7  shl     rdi, 7
0x14003d1eb  add     rdi, r8
0x14003d1ee  movzx   eax, byte ptr [rdi+0B0h]
0x14003d1f5  test    al, al
0x14003d1f7  jz      loc_14003DA78
0x14003d1fd  mov     rdx, rbx; Entry
0x14003d200  lea     rcx, [rdi+40h]; Lookaside
0x14003d204  call    cs:__imp_ExFreeToLookasideListEx
0x14003d20b  nop     dword ptr [rax+rax+00h]
0x14003d210  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003d217  jnz     loc_14003D9FB
0x14003d21d  movzx   r13d, [rsp+130h+var_DF]
0x14003d223  mov     [rsp+130h+Entry], 0
0x14003d22c  cmp     [rsp+130h+var_E0], 0
0x14003d231  jz      short loc_14003D290
0x14003d233  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003d23a  jnz     loc_14003DA16
0x14003d240  xor     edi, edi
0x14003d242  lea     rcx, [r14+40h]; SpinLock
0x14003d246  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003d24d  nop     dword ptr [rax+rax+00h]
0x14003d252  movzx   r8d, al
0x14003d256  lea     rcx, [r14+48h]
0x14003d25a  mov     rdx, [rcx]
0x14003d25d  cmp     rdx, rcx
0x14003d260  jnz     loc_14003D2F3
0x14003d266  movzx   edx, r8b; NewIrql
0x14003d26a  lea     rcx, [r14+40h]; SpinLock
0x14003d26e  call    cs:__imp_KeReleaseSpinLock
0x14003d275  nop     dword ptr [rax+rax+00h]
0x14003d27a  test    rdi, rdi
0x14003d27d  jnz     loc_14003DE4A
0x14003d283  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003d28a  jnz     loc_14003DA5D
0x14003d290  test    r15d, r15d
0x14003d293  js      loc_14003DE97
0x14003d299  movzx   ebx, cs:byte_1401A3780
0x14003d2a0  cmp     byte ptr cs:xmmword_1401A2CA0+2, 0
0x14003d2a7  jl      loc_14003DB24
0x14003d2ad  test    bl, bl
0x14003d2af  jnz     loc_14003D9C9
0x14003d2b5  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003d2bc  jnz     loc_14003DA34
0x14003d2c2  mov     r12, [rsp+130h+var_30]
0x14003d2ca  mov     eax, r15d
0x14003d2cd  mov     rdi, [rsp+130h+arg_10]
0x14003d2d5  mov     rcx, [rbp+30h+var_40]
0x14003d2d9  xor     rcx, rsp; StackCookie
0x14003d2dc  call    __security_check_cookie
0x14003d2e1  add     rsp, 108h
0x14003d2e8  pop     r15
0x14003d2ea  pop     r14
0x14003d2ec  pop     r13
0x14003d2ee  pop     rsi
0x14003d2ef  pop     rbx
0x14003d2f0  pop     rbp
0x14003d2f1  retn
0x14003d2f3  cmp     [rdx+8], rcx
0x14003d2f7  jnz     loc_14003D4D7
0x14003d2fd  mov     rax, [rdx]
0x14003d300  cmp     [rax+8], rdx
0x14003d304  jnz     loc_14003D4D7
0x14003d30a  mov     [rcx], rax
0x14003d30d  lea     rdi, [rdx-0A8h]
0x14003d314  mov     [rax+8], rcx
0x14003d318  xor     eax, eax
0x14003d31a  mov     qword ptr [rdx], 0
0x14003d321  mov     qword ptr [rdx+8], 0
0x14003d329  dec     dword ptr [r14+58h]
0x14003d32d  xchg    rax, [rdi+68h]
0x14003d331  test    rax, rax
0x14003d334  jz      loc_14003DE43
0x14003d33a  test    rdi, rdi
0x14003d33d  jz      loc_14003D25A
0x14003d343  jmp     loc_14003D266
0x14003d348  mov     eax, edi
0x14003d34a  lock xadd [rdx], eax
  ... truncated ...
```
