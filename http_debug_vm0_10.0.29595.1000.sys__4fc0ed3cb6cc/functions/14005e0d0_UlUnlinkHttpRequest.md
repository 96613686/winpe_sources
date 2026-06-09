# UlUnlinkHttpRequest

- ea: `0x14005e0d0`
- end: `0x14005f390`
- name: `UlUnlinkHttpRequest`
- size: `4800`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400568c0`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x14000c390`
- `0x14000e420`
- `0x140022610`
- `0x140049d08`
- `0x1400517b0`
- `0x14005dfd0`
- `0x14005e030`
- `0x14005e0d0`
- `0x1400704a4`
- `0x1400705d0`
- `0x14009620c`
- `0x1400a031c`
- `0x1400ca724`
- `0x1400cfba8`
- `0x1400e2e64`
- `0x14013dd68`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4e4c`
- `0x1401c4eb4`
- `0x1401d9c5c`
- `0x1401d9e44`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005e941`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005ec5b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005e941`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005ec5b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005eaa7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005ed90`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005eaa7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005ed90`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005e597`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005e597`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005ea00`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005ecea`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005ea00`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005ecea`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005ea56`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005ed44`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005ea56`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005ed44`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005f287`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005f33c`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005f287`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005f33c`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005e96b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005ec82`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005e96b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005ec82`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005e9a5`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005ecc2`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005e9a5`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005ecc2`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14005eb20`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14005eb20`
- `ntoskrnl!KeSetEvent` at `0x14005eac5`
- `ntoskrnl!KeSetEvent` at `0x14005edae`
- `ntoskrnl!KeSetEvent` at `0x14005eac5`
- `ntoskrnl!KeSetEvent` at `0x14005edae`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005ea29`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005ed13`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005ea29`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005ed13`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14005e397`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14005e397`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005ebc6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005ebc6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14005eb03`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14005eb03`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005e6e9`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005f0b3`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005e6e9`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005f0b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e2b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e372`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e4c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e4e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ebf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f0a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f0c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e2b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e372`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e4c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e4e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ebf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f0a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f0c3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e2a5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e366`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e4b4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e4d9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e6ae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e6cb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005ebeb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f095`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e2a5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e366`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e4b4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e4d9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e6ae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e6cb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005ebeb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f095`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005e888`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005e888`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e285`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e32f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e3b8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e42d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e44a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e5c2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e285`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e32f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e3b8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e42d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e44a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e5c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e273`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e31e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e382`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e3a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e414`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e439`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e5b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e273`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e31e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e382`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e3a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e414`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e439`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e5b0`

## pseudocode

```c
void __fastcall UlUnlinkHttpRequest(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  unsigned __int64 *v5; // r12
  __int64 v6; // rsi
  _QWORD **v7; // rdi
  _QWORD *v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rdi
  unsigned __int8 v12; // si
  __int64 *v13; // rdi
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // r13
  _DWORD *v17; // rsi
  int v18; // eax
  __int64 v19; // rdi
  int v20; // eax
  __int64 v21; // rdi
  __int64 v22; // rdx
  _QWORD *v23; // rax
  _QWORD *v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // r8
  _QWORD *v27; // rdx
  volatile signed __int32 *v28; // rdx
  volatile signed __int32 *v29; // rdx
  int v30; // eax
  __int64 v31; // rdi
  int v32; // eax
  bool v33; // zf
  unsigned __int64 v34; // rdi
  char v35; // di
  _QWORD *v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rdx
  _QWORD *v39; // rcx
  _DWORD *v40; // rsi
  _QWORD *v41; // rcx
  int v42; // r14d
  __int64 v43; // rdi
  int v44; // eax
  int v45; // eax
  __int64 v46; // r15
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v48; // r9
  void *CurrentServerSilo; // r13
  __int64 v50; // rcx
  void *v51; // rsi
  char v52; // bl
  __int64 v53; // rax
  __int64 v54; // r14
  ULONG v55; // ebx
  ULONG_PTR v56; // rdx
  int v57; // eax
  __int64 v58; // rbx
  ULONG_PTR v59; // rdx
  __int64 v60; // rdi
  USHORT CurrentNodeNumber; // ax
  char v62; // di
  __int64 v63; // rax
  __int64 v64; // r13
  ULONG v65; // edi
  ULONG_PTR v66; // rdx
  int v67; // eax
  __int64 v68; // rdi
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  char v72; // al
  __int64 v73; // rax
  unsigned __int64 v74; // rax
  int v75; // eax
  unsigned int v76; // [rsp+40h] [rbp-69h] BYREF
  __int128 v77; // [rsp+48h] [rbp-61h] BYREF
  __int128 v78; // [rsp+58h] [rbp-51h] BYREF
  _DWORD v79[24]; // [rsp+70h] [rbp-39h] BYREF

  v4 = a1;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a1 )
      v73 = *(_QWORD *)(a1 + 64);
    else
      v73 = 0;
    WPP_SF_qq(1032, 55, WPP_682cf469470432b235cb9a4961616e40_Traceguids, a1, v73);
    a1 = v4;
  }
  v5 = (unsigned __int64 *)(a1 + 64);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( v4 )
      v74 = *v5;
    else
      v74 = 0;
    WPP_SF_qq(1032, 38, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v4, v74);
  }
  *(_DWORD *)(v4 + 2200) |= 0x200u;
  if ( (*(_DWORD *)(v4 + 2200) & 0x1000) == 0 )
  {
    v69 = *(_QWORD *)(v4 + 2512);
    if ( v69 )
    {
      LOBYTE(a2) = 1;
      UlHkeCancelCalloutContext(v69, a2);
    }
    v70 = *(_QWORD *)(v4 + 2520);
    if ( v70 )
    {
      LOBYTE(a2) = 1;
      UlHkeCancelCalloutContext(v70, a2);
    }
    v71 = *(_QWORD *)(v4 + 2528);
    if ( v71 )
    {
      LOBYTE(a2) = 1;
      UlHkeCancelCalloutContext(v71, a2);
    }
  }
  *(_DWORD *)(v4 + 2200) &= ~0x1000u;
  v6 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 95, WPP_ed7456c0382c3120fc23861c64a38256_Traceguids, v4);
  v7 = (_QWORD **)(v4 + 504);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == v7 || v6 )
      break;
    if ( (_QWORD **)v8[1] != v7 )
      goto LABEL_69;
    v41 = (_QWORD *)*v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 )
      goto LABEL_69;
    *v7 = v41;
    v6 = (__int64)(v8 - 21);
    v41[1] = v7;
    v8[1] = v8;
    *v8 = v8;
    if ( _InterlockedExchange64(v8 - 8, 0) )
    {
      if ( *(_BYTE *)(v6 + 68) )
      {
        UlCompleteReceiveEntityBodyIrp(v4, v6, 3221225760LL);
        v6 = 0;
      }
    }
    else
    {
      v6 = 0;
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 96, WPP_ed7456c0382c3120fc23861c64a38256_Traceguids, v6);
  for ( ; v6; v6 = UlDequeueReceiveEntityBodyIrp(v4) )
    UlCompleteReceiveEntityBodyIrp(v4, v6, 3221225760LL);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 39, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
  if ( !*v5 )
    goto LABEL_29;
  v9 = *(_QWORD *)(*(_QWORD *)(v4 + 24) + 1096LL);
  if ( *(_BYTE *)(v9 + 79) && Microsoft_Windows_Networking_CorrelationEnabled )
    UlEtwStopActivity(v4 + 72, 3);
  v10 = *v5;
  v76 = -1;
  LODWORD(v77) = 0;
  LODWORD(v78) = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_iqqq(v9, a2, a3, v10, &v77, &v76, &v78);
  v11 = HIDWORD(v10);
  v76 = 0;
  LODWORD(v78) = 0;
  LODWORD(v77) = v11 & 0xFFF;
  if ( (unsigned int)v77 >= UxMaximumNumberOfProcessors )
  {
    if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
      WPP_SF_(521, 11, WPP_6218f2abddb13899518e42ce65335ae2_Traceguids);
LABEL_183:
    v12 = 0;
    goto LABEL_22;
  }
  a2 = ((unsigned int)v11 >> 12) & 0xFFF;
  v9 = (v11 & 0xFFF) << 6;
  v76 = a2;
  if ( (unsigned int)a2 >= *(_DWORD *)((char *)UxOpaqueIdTable + v9 + 40) )
  {
    if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
    {
      WPP_SF_(521, 12, WPP_6218f2abddb13899518e42ce65335ae2_Traceguids);
      v12 = 0;
      goto LABEL_22;
    }
    goto LABEL_183;
  }
  v12 = 1;
  LODWORD(v78) = BYTE3(v11);
LABEL_22:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_lLLL(v9, a2, a3, v12, v77, v76, v78);
  if ( v12 )
  {
    v13 = (__int64 *)(48LL * (unsigned int)v78
                    + *(_QWORD *)(*((_QWORD *)UxOpaqueIdTable + 8 * (unsigned __int64)(unsigned int)v77 + 2) + 8LL * v76));
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v13 + 4, 0);
    v14 = *v13;
    *(_DWORD *)(v14 + 32) &= 0xFFFFFFFu;
    *(_QWORD *)(v14 + 24) = 0;
    ExReleasePushLockExclusiveEx(v13 + 4, 0);
    KeLeaveCriticalRegion();
  }
  *v5 = 0;
  v15 = _InterlockedDecrement((volatile signed __int32 *)(v4 + 48));
  if ( UxDebugCheckRefcount && v15 <= -1 )
    UlBugCheckEx(3u, v4 + 48, 0x10u, v15);
  if ( !v15 )
    UlpQueueFreeHttpRequest(v4);
LABEL_29:
  *(_QWORD *)&v77 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 235, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v4, *v5);
  if ( *(_BYTE *)(v4 + 1852) )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_qqP(1032, 38, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v4, *v5, &v77);
    *(_QWORD *)&v77 = 0;
    v16 = v4 + 1704;
    while ( 1 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v4 + 1704, 0);
      v17 = *(_DWORD **)(v4 + 1712);
      if ( !v17 )
      {
        ExReleasePushLockExclusiveEx(v4 + 1704, 0);
        KeLeaveCriticalRegion();
        goto LABEL_60;
      }
      v18 = _InterlockedIncrement(v17 + 5);
      if ( UxDebugCheckRefcount && v18 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v17 + 5), 0x21u, v18);
      ExReleasePushLockExclusiveEx(v4 + 1704, 0);
      KeLeaveCriticalRegion();
      v19 = *((_QWORD *)v17 + 8);
      KeEnterCriticalRegion();
      *(_QWORD *)&v77 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v19 + 280), 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v4 + 1704, 0);
      if ( *(_DWORD **)(v4 + 1712) == v17 )
        break;
      ExReleasePushLockExclusiveEx(v4 + 1704, 0);
      KeLeaveCriticalRegion();
      ExReleaseCacheAwarePushLockSharedEx(v77, 0);
      *(_QWORD *)&v77 = 0;
      KeLeaveCriticalRegion();
      v75 = _InterlockedDecrement(v17 + 5);
      if ( UxDebugCheckRefcount && v75 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v17 + 5), 0x21u, v75);
      if ( !v75 )
        UlpFreeCoupling(v17);
    }
    v20 = _InterlockedDecrement(v17 + 5);
    if ( UxDebugCheckRefcount && v20 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v17 + 5), 0x21u, v20);
    if ( !v20 )
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v17, 0);
      v21 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v17 + 8) + 264LL)
                      + 8LL * *(unsigned __int16 *)(*((_QWORD *)v17 + 7) + 56LL));
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(*((_QWORD *)v17 + 7) + 944LL, 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v21, 0);
      v22 = *((_QWORD *)v17 + 3);
      v23 = v17 + 6;
      if ( *(_DWORD **)(v22 + 8) == v17 + 6 )
      {
        v24 = (_QWORD *)*((_QWORD *)v17 + 4);
        if ( (_QWORD *)*v24 == v23 )
        {
          *v24 = v22;
          *(_QWORD *)(v22 + 8) = v24;
          *v23 = 0;
          *((_QWORD *)v17 + 4) = 0;
          v25 = v17 + 10;
          v26 = *((_QWORD *)v17 + 5);
          if ( *(_DWORD **)(v26 + 8) == v17 + 10 )
          {
            v27 = (_QWORD *)*((_QWORD *)v17 + 6);
            if ( (_QWORD *)*v27 == v25 )
            {
              *v27 = v26;
              *(_QWORD *)(v26 + 8) = v27;
              *v25 = 0;
              *((_QWORD *)v17 + 6) = 0;
              ExReleasePushLockExclusiveEx(v21, 0);
              KeLeaveCriticalRegion();
              ExReleasePushLockExclusiveEx(*((_QWORD *)v17 + 7) + 944LL, 0);
              KeLeaveCriticalRegion();
              v28 = (volatile signed __int32 *)*((_QWORD *)v17 + 11);
              if ( v28 )
              {
                v45 = _InterlockedDecrement(v28);
                if ( UxDebugCheckRefcount && v45 <= -1 )
                  UlBugCheckEx(3u, (ULONG_PTR)v28, 0xEu, v45);
                if ( !v45 )
                  UlConsumerCleanupCompletion(*((_QWORD *)v17 + 11));
                *((_QWORD *)v17 + 11) = 0;
              }
              v29 = (volatile signed __int32 *)*((_QWORD *)v17 + 8);
              v30 = _InterlockedDecrement(v29);
              if ( UxDebugCheckRefcount && v30 <= -1 )
                UlBugCheckEx(3u, (ULONG_PTR)v29, 0xEu, v30);
              if ( !v30 )
                UlFreeRequestQueue(*((PVOID *)v17 + 8));
              v31 = *((_QWORD *)v17 + 7);
              *((_QWORD *)v17 + 8) = 0;
              v32 = _InterlockedDecrement((volatile signed __int32 *)(v31 + 40));
              if ( UxDebugCheckRefcount && v32 <= -1 )
                UlBugCheckEx(3u, v31 + 40, 0xEu, v32);
              if ( v32 )
              {
LABEL_52:
                v33 = UxDebugDisableLookaside == 0;
                *((_QWORD *)v17 + 7) = 0;
                v17[4] = 1969441909;
                if ( v33 )
                {
                  if ( UxCompactMode )
                  {
                    v60 = qword_1401A0910;
                    CurrentNodeNumber = KeGetCurrentNodeNumber();
                    PplFreeToLookasideListProcessor(v60, v17, CurrentNodeNumber);
                  }
                  else
                  {
                    v34 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*v17 + 1) << 7);
                    if ( !*(_BYTE *)(v34 + 176) )
                      PplpLazyInitializeLookasideList(qword_1401A0910, v34 + 64);
                    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v34 + 64), v17);
                  }
                }
                else
                {
                  memset(v79, 0, sizeof(v79));
                  v79[10] = dword_1401A0928;
                  ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A0938)(v17, v79);
                }
                if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
                  WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
                goto LABEL_59;
              }
              v46 = v31 + 64;
              CurrentProcess = IoGetCurrentProcess();
              CurrentServerSilo = *(void **)(v31 + 1088);
              v50 = *(_QWORD *)(v31 + 64);
              if ( UxSystemProcess != CurrentProcess )
              {
                if ( v50 || *(_QWORD *)(v31 + 80) || *(_QWORD *)(v31 + 96) )
                  UlBugCheckEx(1u, v31 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
                LOBYTE(v48) = 1;
                UlThreadPoolEnqueueWorkItem(0, v31 + 64, UlFreeHttpConnection, v48, CurrentServerSilo, -1);
                v16 = v4 + 1704;
                goto LABEL_52;
              }
              if ( v50 || *(_QWORD *)(v31 + 80) || *(_QWORD *)(v31 + 96) )
                UlBugCheckEx(1u, v31 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
              if ( KeGetCurrentIrql() )
              {
                v65 = 0;
                if ( (unsigned int)dword_1401A3F48 > 1 )
                {
                  v65 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
                  if ( byte_1401A3F60 )
                    v65 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
                }
                if ( CurrentServerSilo == (void *)-1LL )
                  CurrentServerSilo = (void *)PsGetCurrentServerSilo();
                *(_QWORD *)(v46 + 32) = CurrentServerSilo;
                *(_QWORD *)&v78 = 0;
                if ( CurrentServerSilo )
                  ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
                PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v78);
                v66 = v78 + 24;
                v67 = _InterlockedIncrement((volatile signed __int32 *)(v78 + 24));
                if ( UxDebugCheckRefcount && v67 <= -1 )
                  UlBugCheckEx(3u, v66, 0xDu, v67);
                *(_BYTE *)(v46 + 24) = 1;
                v68 = *(_QWORD *)(qword_1401A3F50 + 8LL * v65);
                *(_QWORD *)(v46 + 16) = UlFreeHttpConnection;
                if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v68 + 16), (PSLIST_ENTRY)v46) )
                {
                  KeSetEvent((PRKEVENT)(v68 + 32), 0, 0);
                  UlpActivateThreadPoolQueue((PVOID)v68);
                  v16 = v4 + 1704;
                  goto LABEL_52;
                }
              }
              else
              {
                v62 = 0;
                v78 = 0;
                if ( CurrentServerSilo == (void *)-1LL )
                {
                  v64 = *((_QWORD *)&v78 + 1);
LABEL_158:
                  UlFreeHttpConnection(v46);
                  if ( v62 )
                    goto LABEL_159;
                }
                else
                {
                  v63 = PsAttachSiloToCurrentThread(CurrentServerSilo);
                  *(_QWORD *)&v78 = v63;
                  v62 = 1;
                  if ( (BYTE11(xmmword_1401A2CA0) & 0x10) == 0 )
                  {
                    v64 = v63;
                    goto LABEL_158;
                  }
                  WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v63, CurrentServerSilo);
                  UlFreeHttpConnection(v46);
                  v64 = v78;
LABEL_159:
                  if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
                    WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v64);
                  PsDetachSiloFromCurrentThread(v64);
                }
              }
              v16 = v4 + 1704;
              goto LABEL_52;
            }
          }
        }
      }
LABEL_69:
      __fastfail(3u);
    }
LABEL_59:
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v17 + 18, 0);
LABEL_60:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_q(1032, 39, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v17);
    if ( v17 )
    {
      v35 = 0;
      if ( *(_DWORD *)(v4 + 1736) == 1 )
      {
        v72 = UlpRemoveRequestFromLane(v4);
        *(_DWORD *)(v4 + 1736) = 3;
        v35 = v72;
        if ( v72 )
        {
LABEL_68:
          v39 = (_QWORD *)*((_QWORD *)v17 + 15);
          v40 = v17 + 28;
          if ( (_DWORD *)*v39 != v40 )
            goto LABEL_69;
          *(_QWORD *)(v4 + 1816) = v40;
          *(_QWORD *)(v4 + 1824) = v39;
          *v39 = v4 + 1816;
          *((_QWORD *)v40 + 1) = v4 + 1816;
        }
      }
      else if ( *(_DWORD *)(v4 + 1736) == 2 )
      {
        v36 = (_QWORD *)(v4 + 1720);
        v37 = *(_QWORD *)(v4 + 1720);
        if ( *(_QWORD *)(v37 + 8) != v4 + 1720 )
          goto LABEL_69;
        v38 = *(_QWORD **)(v4 + 1728);
        if ( (_QWORD *)*v38 != v36 )
          goto LABEL_69;
        *v38 = v37;
        v35 = 1;
        *(_QWORD *)(v37 + 8) = v38;
        *v36 = 0;
        *(_QWORD *)(v4 + 1728) = 0;
        *(_DWORD *)(v4 + 1736) = 3;
        goto LABEL_68;
      }
      ExReleasePushLockExclusiveEx(*(_QWORD *)(v4 + 1712) + 72LL, 0);
      KeLeaveCriticalRegion();
      ExReleasePushLockExclusiveEx(v16, 0);
      KeLeaveCriticalRegion();
      ExReleaseCacheAwarePushLockSharedEx(v77, 0);
      *(_QWORD *)&v77 = 0;
      KeLeaveCriticalRegion();
      if ( v35 )
      {
        v44 = _InterlockedDecrement((volatile signed __int32 *)(v4 + 48));
        if ( UxDebugCheckRefcount && v44 <= -1 )
          UlBugCheckEx(3u, v4 + 48, 0xCu, v44);
        if ( !v44 )
          UlpQueueFreeHttpRequest(v4);
      }
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 236, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  v42 = _InterlockedDecrement((volatile signed __int32 *)(v4 + 48));
  if ( UxDebugCheckRefcount && v42 <= -1 )
    UlBugCheckEx(3u, v4 + 48, 1u, v42);
  if ( v42 )
    goto LABEL_90;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 40, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v4, *v5);
  if ( (*(_DWORD *)(v4 + 2264) & 1) != 0 || *(_QWORD *)(v4 + 2288) || *(_QWORD *)(v4 + 2312) )
  {
    v59 = v4 + 1248;
    if ( *(_QWORD *)(v4 + 1248) || *(_QWORD *)(v4 + 1264) || *(_QWORD *)(v4 + 1280) )
      UlBugCheckEx(1u, v59, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x645u);
    LOBYTE(a4) = 1;
    UlThreadPoolEnqueueWorkItem(0, v59, UlpFreeHttpRequest, a4, *(_QWORD *)(*(_QWORD *)(v4 + 24) + 1088LL), -1);
    goto LABEL_123;
  }
  v43 = v4 + 1248;
  if ( *(_QWORD *)(v4 + 1248) || *(_QWORD *)(v4 + 1264) || *(_QWORD *)(v4 + 1280) )
    UlBugCheckEx(1u, v4 + 1248, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x64Du);
  v51 = *(void **)(*(_QWORD *)(v4 + 24) + 1088LL);
  if ( KeGetCurrentIrql() )
  {
    v55 = 0;
    if ( (unsigned int)dword_1401A3F48 > 1 )
    {
      v55 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
      if ( byte_1401A3F60 )
        v55 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
    }
    if ( v51 == (void *)-1LL )
      v51 = (void *)PsGetCurrentServerSilo();
    *(_QWORD *)(v43 + 32) = v51;
    *(_QWORD *)&v77 = 0;
    if ( v51 )
      ObfReferenceObjectWithTag(v51, 0x49576C55u);
    PsGetPermanentSiloContext(v51, (unsigned int)UxPodMonitorSlot, &v77);
    v56 = v77 + 24;
    v57 = _InterlockedIncrement((volatile signed __int32 *)(v77 + 24));
    if ( UxDebugCheckRefcount && v57 <= -1 )
      UlBugCheckEx(3u, v56, 0xDu, v57);
    *(_BYTE *)(v43 + 24) = 1;
    v58 = *(_QWORD *)(qword_1401A3F50 + 8LL * v55);
    *(_QWORD *)(v43 + 16) = UlpFreeHttpRequest;
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v58 + 16), (PSLIST_ENTRY)v43) )
    {
      KeSetEvent((PRKEVENT)(v58 + 32), 0, 0);
      if ( *(_BYTE *)(*(_QWORD *)v58 + 33LL) )
      {
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v58 + 68), 1, 0) )
        {
          if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_Dd(
              1304,
              18,
              WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids,
              *(unsigned int *)(v58 + 8),
              **(_DWORD **)v58);
          _InterlockedIncrement((volatile signed __int32 *)(v58 + 64));
          ExAcquireRundownProtection(&UlThreadPoolIoWorkItemsRundown);
          IoQueueWorkItemEx(*(PIO_WORKITEM *)(v58 + 56), UlpThreadPoolStarter, DelayedWorkQueue, (PVOID)v58);
        }
      }
    }
    goto LABEL_123;
  }
  v52 = 0;
  v77 = 0;
  if ( v51 == (void *)-1LL )
  {
    v54 = *((_QWORD *)&v77 + 1);
  }
  else
  {
    v53 = PsAttachSiloToCurrentThread(v51);
    v54 = v53;
    v52 = 1;
    if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
    {
      WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v53, v51);
      UlpFreeHttpRequest(v43);
      goto LABEL_120;
    }
  }
  UlpFreeHttpRequest(v43);
  if ( v52 )
  {
LABEL_120:
    if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v54);
    PsDetachSiloFromCurrentThread(v54);
  }
LABEL_123:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) == 0 )
    return;
  WPP_SF_(1032, 41, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
LABEL_90:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 56, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
}

```

## disassembly

```asm
0x14005e0d0  mov     [rsp-8+arg_18], rbx
0x14005e0d5  push    rbp
0x14005e0d6  push    rsi
0x14005e0d7  push    rdi
0x14005e0d8  push    r12
0x14005e0da  push    r15
0x14005e0dc  lea     rbp, [rsp-37h]
0x14005e0e1  sub     rsp, 0E0h
0x14005e0e8  mov     rax, cs:__security_cookie
0x14005e0ef  xor     rax, rsp
0x14005e0f2  mov     [rbp+57h+var_30], rax
0x14005e0f6  mov     rbx, rcx
0x14005e0f9  xor     r15d, r15d
0x14005e0fc  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e103  jnz     loc_14005F02B
0x14005e109  mov     eax, 40h ; '@'
0x14005e10e  lea     r12, [rcx+rax]
0x14005e112  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e119  jnz     loc_14005F05F
0x14005e11f  or      dword ptr [rbx+898h], 200h
0x14005e129  test    dword ptr [rbx+898h], 1000h
0x14005e133  jz      loc_14005EF43
0x14005e139  and     dword ptr [rbx+898h], 0FFFFEFFFh
0x14005e143  mov     rsi, r15
0x14005e146  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e14d  jnz     loc_14005EED5
0x14005e153  mov     [rsp+100h+arg_8], r13
0x14005e15b  lea     rdi, [rbx+1F8h]
0x14005e162  mov     [rsp+100h+arg_10], r14
0x14005e16a  mov     rax, [rdi]
0x14005e16d  cmp     rax, rdi
0x14005e170  jnz     loc_14005E647
0x14005e176  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e17d  jnz     loc_14005F133
0x14005e183  test    rsi, rsi
0x14005e186  jnz     loc_14005EE70
0x14005e18c  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e193  jnz     loc_14005EEF3
0x14005e199  mov     r14d, 0FFFFFFFFh
0x14005e19f  cmp     [r12], r15
0x14005e1a3  jz      loc_14005E2E3
0x14005e1a9  mov     rax, [rbx+18h]
0x14005e1ad  mov     rcx, [rax+448h]
0x14005e1b4  cmp     [rcx+4Fh], r15b
0x14005e1b8  jz      short loc_14005E1C8
0x14005e1ba  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14005e1c0  test    eax, eax
0x14005e1c2  jnz     loc_14005F151
0x14005e1c8  mov     rdi, [r12]
0x14005e1cc  mov     [rbp+57h+var_C0], 0FFFFFFFFh
0x14005e1d3  mov     dword ptr [rbp+57h+var_B8], r15d
0x14005e1d7  mov     dword ptr [rbp+57h+var_A8], r15d
0x14005e1db  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14005e1e2  jnz     loc_14005F164
0x14005e1e8  shr     rdi, 20h
0x14005e1ec  mov     eax, edi
0x14005e1ee  mov     [rbp+57h+var_C0], r15d
0x14005e1f2  and     eax, 0FFFh
0x14005e1f7  mov     dword ptr [rbp+57h+var_A8], r15d
0x14005e1fb  cmp     eax, cs:UxMaximumNumberOfProcessors
0x14005e201  mov     dword ptr [rbp+57h+var_B8], eax
0x14005e204  jnb     loc_14005EE51
0x14005e20a  mov     ecx, eax
0x14005e20c  mov     edx, edi
0x14005e20e  mov     rax, cs:UxOpaqueIdTable
0x14005e215  shr     edx, 0Ch
0x14005e218  and     edx, 0FFFh
0x14005e21e  shl     rcx, 6
0x14005e222  mov     [rbp+57h+var_C0], edx
0x14005e225  cmp     edx, [rcx+rax+28h]
0x14005e229  jnb     loc_14005F1A7
0x14005e22f  shr     edi, 18h
0x14005e232  mov     sil, 1
0x14005e235  mov     dword ptr [rbp+57h+var_A8], edi
0x14005e238  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14005e23f  jnz     loc_14005F1D2
0x14005e245  test    sil, sil
0x14005e248  jz      short loc_14005E2BD
0x14005e24a  mov     rax, cs:UxOpaqueIdTable
0x14005e251  mov     ecx, dword ptr [rbp+57h+var_B8]
0x14005e254  mov     r8d, [rbp+57h+var_C0]
0x14005e258  shl     rcx, 6
0x14005e25c  mov     rdx, [rcx+rax+10h]
0x14005e261  mov     eax, dword ptr [rbp+57h+var_A8]
0x14005e264  mov     rdi, [rdx+r8*8]
0x14005e268  lea     rcx, [rax+rax*2]
0x14005e26c  shl     rcx, 4
0x14005e270  add     rdi, rcx
0x14005e273  call    cs:__imp_KeEnterCriticalRegion
0x14005e27a  nop     dword ptr [rax+rax+00h]
0x14005e27f  xor     edx, edx
0x14005e281  lea     rcx, [rdi+20h]
0x14005e285  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e28c  nop     dword ptr [rax+rax+00h]
0x14005e291  mov     rax, [rdi]
0x14005e294  lea     rcx, [rdi+20h]
0x14005e298  xor     edx, edx
0x14005e29a  and     dword ptr [rax+20h], 0FFFFFFFh
0x14005e2a1  mov     [rax+18h], r15
0x14005e2a5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005e2ac  nop     dword ptr [rax+rax+00h]
0x14005e2b1  call    cs:__imp_KeLeaveCriticalRegion
0x14005e2b8  nop     dword ptr [rax+rax+00h]
0x14005e2bd  mov     [r12], r15
0x14005e2c1  lea     rdx, [rbx+30h]; BugCheckParameter2
0x14005e2c5  mov     eax, r14d
0x14005e2c8  lock xadd [rdx], eax
0x14005e2cc  dec     eax
0x14005e2ce  cmp     cs:UxDebugCheckRefcount, r15b
0x14005e2d5  jnz     loc_14005E867
0x14005e2db  test    eax, eax
0x14005e2dd  jz      loc_14005F1F5
0x14005e2e3  mov     qword ptr [rbp+57h+var_B8], r15
0x14005e2e7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e2ee  jnz     loc_14005EC34
0x14005e2f4  mov     edi, 1
0x14005e2f9  cmp     [rbx+73Ch], r15b
0x14005e300  jz      loc_14005E70E
0x14005e306  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14005e30d  jnz     loc_14005F202
0x14005e313  mov     qword ptr [rbp+57h+var_B8], r15
0x14005e317  lea     r13, [rbx+6A8h]
0x14005e31e  call    cs:__imp_KeEnterCriticalRegion
0x14005e325  nop     dword ptr [rax+rax+00h]
0x14005e32a  xor     edx, edx
0x14005e32c  mov     rcx, r13
0x14005e32f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e336  nop     dword ptr [rax+rax+00h]
0x14005e33b  mov     rsi, [rbx+6B0h]
0x14005e342  test    rsi, rsi
0x14005e345  jz      loc_14005EBE6
0x14005e34b  mov     eax, edi
0x14005e34d  lock xadd [rsi+14h], eax
0x14005e352  inc     eax
0x14005e354  cmp     cs:UxDebugCheckRefcount, r15b
0x14005e35b  jnz     loc_14005E828
0x14005e361  xor     edx, edx
0x14005e363  mov     rcx, r13
0x14005e366  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005e36d  nop     dword ptr [rax+rax+00h]
0x14005e372  call    cs:__imp_KeLeaveCriticalRegion
0x14005e379  nop     dword ptr [rax+rax+00h]
0x14005e37e  mov     rdi, [rsi+40h]
0x14005e382  call    cs:__imp_KeEnterCriticalRegion
0x14005e389  nop     dword ptr [rax+rax+00h]
0x14005e38e  mov     rcx, [rdi+118h]
0x14005e395  xor     edx, edx
0x14005e397  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14005e39e  nop     dword ptr [rax+rax+00h]
0x14005e3a3  mov     qword ptr [rbp+57h+var_B8], rax
0x14005e3a7  call    cs:__imp_KeEnterCriticalRegion
0x14005e3ae  nop     dword ptr [rax+rax+00h]
0x14005e3b3  xor     edx, edx
0x14005e3b5  mov     rcx, r13
0x14005e3b8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e3bf  nop     dword ptr [rax+rax+00h]
0x14005e3c4  cmp     [rbx+6B0h], rsi
0x14005e3cb  jnz     loc_14005F090
0x14005e3d1  mov     eax, r14d
0x14005e3d4  lock xadd [rsi+14h], eax
0x14005e3d9  dec     eax
0x14005e3db  cmp     cs:UxDebugCheckRefcount, r15b
0x14005e3e2  jnz     loc_14005E8DB
0x14005e3e8  test    eax, eax
0x14005e3ea  jnz     loc_14005E5B0
0x14005e3f0  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e3f7  jnz     loc_14005EE97
0x14005e3fd  mov     rax, [rsi+38h]
0x14005e401  movzx   edx, word ptr [rax+38h]
0x14005e405  mov     rax, [rsi+40h]
0x14005e409  mov     rcx, [rax+108h]
0x14005e410  mov     rdi, [rcx+rdx*8]
0x14005e414  call    cs:__imp_KeEnterCriticalRegion
0x14005e41b  nop     dword ptr [rax+rax+00h]
0x14005e420  mov     rcx, [rsi+38h]
0x14005e424  xor     edx, edx
0x14005e426  add     rcx, 3B0h
0x14005e42d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e434  nop     dword ptr [rax+rax+00h]
0x14005e439  call    cs:__imp_KeEnterCriticalRegion
0x14005e440  nop     dword ptr [rax+rax+00h]
0x14005e445  xor     edx, edx
0x14005e447  mov     rcx, rdi
0x14005e44a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e451  nop     dword ptr [rax+rax+00h]
0x14005e456  mov     rdx, [rsi+18h]
0x14005e45a  lea     rax, [rsi+18h]
0x14005e45e  cmp     [rdx+8], rax
0x14005e462  jnz     loc_14005E640
0x14005e468  mov     rcx, [rax+8]
0x14005e46c  cmp     [rcx], rax
0x14005e46f  jnz     loc_14005E640
0x14005e475  mov     [rcx], rdx
0x14005e478  mov     [rdx+8], rcx
0x14005e47c  mov     [rax], r15
0x14005e47f  mov     [rax+8], r15
0x14005e483  lea     rax, [rsi+28h]
0x14005e487  mov     r8, [rax]
0x14005e48a  cmp     [r8+8], rax
0x14005e48e  jnz     loc_14005E640
0x14005e494  mov     rdx, [rax+8]
0x14005e498  cmp     [rdx], rax
0x14005e49b  jnz     loc_14005E640
0x14005e4a1  mov     [rdx], r8
0x14005e4a4  mov     rcx, rdi
0x14005e4a7  mov     [r8+8], rdx
0x14005e4ab  xor     edx, edx
0x14005e4ad  mov     [rax], r15
0x14005e4b0  mov     [rax+8], r15
0x14005e4b4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005e4bb  nop     dword ptr [rax+rax+00h]
0x14005e4c0  call    cs:__imp_KeLeaveCriticalRegion
0x14005e4c7  nop     dword ptr [rax+rax+00h]
0x14005e4cc  mov     rcx, [rsi+38h]
0x14005e4d0  xor     edx, edx
0x14005e4d2  add     rcx, 3B0h
0x14005e4d9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005e4e0  nop     dword ptr [rax+rax+00h]
0x14005e4e5  call    cs:__imp_KeLeaveCriticalRegion
0x14005e4ec  nop     dword ptr [rax+rax+00h]
0x14005e4f1  mov     rdx, [rsi+58h]; BugCheckParameter2
0x14005e4f5  test    rdx, rdx
0x14005e4f8  jnz     loc_14005E801
0x14005e4fe  mov     rdx, [rsi+40h]; BugCheckParameter2
0x14005e502  mov     eax, r14d
0x14005e505  lock xadd [rdx], eax
0x14005e509  dec     eax
0x14005e50b  cmp     cs:UxDebugCheckRefcount, 0
0x14005e512  jnz     loc_14005E8FC
0x14005e518  test    eax, eax
0x14005e51a  jz      loc_14005F240
0x14005e520  mov     rdi, [rsi+38h]
0x14005e524  mov     eax, r14d
0x14005e527  mov     [rsi+40h], r15
0x14005e52b  lea     rdx, [rdi+28h]; BugCheckParameter2
0x14005e52f  lock xadd [rdx], eax
0x14005e533  dec     eax
0x14005e535  cmp     cs:UxDebugCheckRefcount, 0
0x14005e53c  jnz     loc_14005E919
0x14005e542  test    eax, eax
0x14005e544  jz      loc_14005E884
0x14005e54a  cmp     cs:UxDebugDisableLookaside, 0
0x14005e551  mov     [rsi+38h], r15
0x14005e555  mov     dword ptr [rsi+10h], 75634C75h
0x14005e55c  jnz     loc_14005F298
0x14005e562  cmp     cs:UxCompactMode, 0
0x14005e569  jnz     loc_14005EBBF
0x14005e56f  mov     edi, [rsi]
0x14005e571  mov     rcx, cs:qword_1401A0910
0x14005e578  inc     edi
0x14005e57a  shl     rdi, 7
0x14005e57e  add     rdi, rcx
0x14005e581  movzx   eax, byte ptr [rdi+0B0h]
0x14005e588  test    al, al
0x14005e58a  jz      loc_14005EF35
0x14005e590  mov     rdx, rsi; Entry
0x14005e593  lea     rcx, [rdi+40h]; Lookaside
0x14005e597  call    cs:__imp_ExFreeToLookasideListEx
0x14005e59e  nop     dword ptr [rax+rax+00h]
0x14005e5a3  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e5aa  jnz     loc_14005EEBA
0x14005e5b0  call    cs:__imp_KeEnterCriticalRegion
0x14005e5b7  nop     dword ptr [rax+rax+00h]
0x14005e5bc  lea     rcx, [rsi+48h]
0x14005e5c0  xor     edx, edx
0x14005e5c2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e5c9  nop     dword ptr [rax+rax+00h]
0x14005e5ce  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e5d5  jnz     loc_14005F2CA
0x14005e5db  test    rsi, rsi
0x14005e5de  jz      loc_14005E70E
0x14005e5e4  mov     ecx, [rbx+6C8h]
0x14005e5ea  xor     dil, dil
0x14005e5ed  sub     ecx, 1
0x14005e5f0  jz      loc_14005F009
0x14005e5f6  cmp     ecx, 1
0x14005e5f9  jnz     loc_14005E6A1
0x14005e5ff  lea     rax, [rbx+6B8h]
0x14005e606  mov     rcx, [rax]
0x14005e609  cmp     [rcx+8], rax
0x14005e60d  jnz     short loc_14005E640
0x14005e60f  mov     rdx, [rax+8]
0x14005e613  cmp     [rdx], rax
0x14005e616  jnz     short loc_14005E640
0x14005e618  mov     [rdx], rcx
0x14005e61b  mov     dil, 1
0x14005e61e  mov     [rcx+8], rdx
0x14005e622  mov     [rax], r15
0x14005e625  mov     [rax+8], r15
0x14005e629  mov     dword ptr [rbx+6C8h], 3
0x14005e633  mov     rcx, [rsi+78h]
0x14005e637  add     rsi, 70h ; 'p'
0x14005e63b  cmp     [rcx], rsi
0x14005e63e  jz      short loc_14005E68C
0x14005e640  mov     ecx, 3
0x14005e645  int     29h; Win8: RtlFailFast(ecx)
0x14005e647  test    rsi, rsi
0x14005e64a  jnz     loc_14005E176
0x14005e650  cmp     [rax+8], rdi
0x14005e654  jnz     short loc_14005E640
  ... truncated ...
```
