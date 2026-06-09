# UlUnlinkHttpRequest

- ea: `0x14005e0f0`
- end: `0x14005f3b0`
- name: `UlUnlinkHttpRequest`
- size: `4800`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400568e0`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x14000c390`
- `0x14000e420`
- `0x140022610`
- `0x140049d28`
- `0x1400517d0`
- `0x14005dff0`
- `0x14005e050`
- `0x14005e0f0`
- `0x1400704c4`
- `0x1400705f0`
- `0x14009622c`
- `0x1400a033c`
- `0x1400ca804`
- `0x1400cfc88`
- `0x1400e2e34`
- `0x14013dc78`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4e4c`
- `0x1401c4eb4`
- `0x1401d9c5c`
- `0x1401d9e44`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005e961`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005ec7b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005e961`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005ec7b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005eac7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005edb0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005eac7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005edb0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005e5b7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005e5b7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005ea20`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005ed0a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005ea20`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005ed0a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005ea76`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005ed64`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005ea76`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005ed64`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005f2a7`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005f35c`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005f2a7`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005f35c`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005e98b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005eca2`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005e98b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005eca2`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005e9c5`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005ece2`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005e9c5`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005ece2`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14005eb40`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14005eb40`
- `ntoskrnl!KeSetEvent` at `0x14005eae5`
- `ntoskrnl!KeSetEvent` at `0x14005edce`
- `ntoskrnl!KeSetEvent` at `0x14005eae5`
- `ntoskrnl!KeSetEvent` at `0x14005edce`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005ea49`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005ed33`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005ea49`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005ed33`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14005e3b7`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14005e3b7`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005ebe6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005ebe6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14005eb23`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14005eb23`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005e709`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005f0d3`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005e709`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005f0d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e2d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e392`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e4e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e505`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e719`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ec17`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f0c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f0e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e2d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e392`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e4e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e505`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e6f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e719`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ec17`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f0c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f0e3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e2c5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e386`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e4d4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e4f9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e6ce`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e6eb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005ec0b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f0b5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e2c5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e386`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e4d4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e4f9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e6ce`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005e6eb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005ec0b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f0b5`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005e8a8`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005e8a8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e2a5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e34f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e3d8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e44d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e46a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e5e2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e2a5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e34f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e3d8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e44d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e46a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005e5e2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e293`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e33e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e3a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e3c7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e434`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e459`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e5d0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e293`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e33e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e3a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e3c7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e434`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e459`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e5d0`

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
    WPP_SF_q(1032, 95, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, v4);
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
    WPP_SF_q(1032, 96, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, v6);
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
0x14005e0f0  mov     [rsp-8+arg_18], rbx
0x14005e0f5  push    rbp
0x14005e0f6  push    rsi
0x14005e0f7  push    rdi
0x14005e0f8  push    r12
0x14005e0fa  push    r15
0x14005e0fc  lea     rbp, [rsp-37h]
0x14005e101  sub     rsp, 0E0h
0x14005e108  mov     rax, cs:__security_cookie
0x14005e10f  xor     rax, rsp
0x14005e112  mov     [rbp+57h+var_30], rax
0x14005e116  mov     rbx, rcx
0x14005e119  xor     r15d, r15d
0x14005e11c  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e123  jnz     loc_14005F04B
0x14005e129  mov     eax, 40h ; '@'
0x14005e12e  lea     r12, [rcx+rax]
0x14005e132  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e139  jnz     loc_14005F07F
0x14005e13f  or      dword ptr [rbx+898h], 200h
0x14005e149  test    dword ptr [rbx+898h], 1000h
0x14005e153  jz      loc_14005EF63
0x14005e159  and     dword ptr [rbx+898h], 0FFFFEFFFh
0x14005e163  mov     rsi, r15
0x14005e166  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e16d  jnz     loc_14005EEF5
0x14005e173  mov     [rsp+100h+arg_8], r13
0x14005e17b  lea     rdi, [rbx+1F8h]
0x14005e182  mov     [rsp+100h+arg_10], r14
0x14005e18a  mov     rax, [rdi]
0x14005e18d  cmp     rax, rdi
0x14005e190  jnz     loc_14005E667
0x14005e196  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e19d  jnz     loc_14005F153
0x14005e1a3  test    rsi, rsi
0x14005e1a6  jnz     loc_14005EE90
0x14005e1ac  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e1b3  jnz     loc_14005EF13
0x14005e1b9  mov     r14d, 0FFFFFFFFh
0x14005e1bf  cmp     [r12], r15
0x14005e1c3  jz      loc_14005E303
0x14005e1c9  mov     rax, [rbx+18h]
0x14005e1cd  mov     rcx, [rax+448h]
0x14005e1d4  cmp     [rcx+4Fh], r15b
0x14005e1d8  jz      short loc_14005E1E8
0x14005e1da  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14005e1e0  test    eax, eax
0x14005e1e2  jnz     loc_14005F171
0x14005e1e8  mov     rdi, [r12]
0x14005e1ec  mov     [rbp+57h+var_C0], 0FFFFFFFFh
0x14005e1f3  mov     dword ptr [rbp+57h+var_B8], r15d
0x14005e1f7  mov     dword ptr [rbp+57h+var_A8], r15d
0x14005e1fb  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14005e202  jnz     loc_14005F184
0x14005e208  shr     rdi, 20h
0x14005e20c  mov     eax, edi
0x14005e20e  mov     [rbp+57h+var_C0], r15d
0x14005e212  and     eax, 0FFFh
0x14005e217  mov     dword ptr [rbp+57h+var_A8], r15d
0x14005e21b  cmp     eax, cs:UxMaximumNumberOfProcessors
0x14005e221  mov     dword ptr [rbp+57h+var_B8], eax
0x14005e224  jnb     loc_14005EE71
0x14005e22a  mov     ecx, eax
0x14005e22c  mov     edx, edi
0x14005e22e  mov     rax, cs:UxOpaqueIdTable
0x14005e235  shr     edx, 0Ch
0x14005e238  and     edx, 0FFFh
0x14005e23e  shl     rcx, 6
0x14005e242  mov     [rbp+57h+var_C0], edx
0x14005e245  cmp     edx, [rcx+rax+28h]
0x14005e249  jnb     loc_14005F1C7
0x14005e24f  shr     edi, 18h
0x14005e252  mov     sil, 1
0x14005e255  mov     dword ptr [rbp+57h+var_A8], edi
0x14005e258  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14005e25f  jnz     loc_14005F1F2
0x14005e265  test    sil, sil
0x14005e268  jz      short loc_14005E2DD
0x14005e26a  mov     rax, cs:UxOpaqueIdTable
0x14005e271  mov     ecx, dword ptr [rbp+57h+var_B8]
0x14005e274  mov     r8d, [rbp+57h+var_C0]
0x14005e278  shl     rcx, 6
0x14005e27c  mov     rdx, [rcx+rax+10h]
0x14005e281  mov     eax, dword ptr [rbp+57h+var_A8]
0x14005e284  mov     rdi, [rdx+r8*8]
0x14005e288  lea     rcx, [rax+rax*2]
0x14005e28c  shl     rcx, 4
0x14005e290  add     rdi, rcx
0x14005e293  call    cs:__imp_KeEnterCriticalRegion
0x14005e29a  nop     dword ptr [rax+rax+00h]
0x14005e29f  xor     edx, edx
0x14005e2a1  lea     rcx, [rdi+20h]
0x14005e2a5  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e2ac  nop     dword ptr [rax+rax+00h]
0x14005e2b1  mov     rax, [rdi]
0x14005e2b4  lea     rcx, [rdi+20h]
0x14005e2b8  xor     edx, edx
0x14005e2ba  and     dword ptr [rax+20h], 0FFFFFFFh
0x14005e2c1  mov     [rax+18h], r15
0x14005e2c5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005e2cc  nop     dword ptr [rax+rax+00h]
0x14005e2d1  call    cs:__imp_KeLeaveCriticalRegion
0x14005e2d8  nop     dword ptr [rax+rax+00h]
0x14005e2dd  mov     [r12], r15
0x14005e2e1  lea     rdx, [rbx+30h]; BugCheckParameter2
0x14005e2e5  mov     eax, r14d
0x14005e2e8  lock xadd [rdx], eax
0x14005e2ec  dec     eax
0x14005e2ee  cmp     cs:UxDebugCheckRefcount, r15b
0x14005e2f5  jnz     loc_14005E887
0x14005e2fb  test    eax, eax
0x14005e2fd  jz      loc_14005F215
0x14005e303  mov     qword ptr [rbp+57h+var_B8], r15
0x14005e307  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e30e  jnz     loc_14005EC54
0x14005e314  mov     edi, 1
0x14005e319  cmp     [rbx+73Ch], r15b
0x14005e320  jz      loc_14005E72E
0x14005e326  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14005e32d  jnz     loc_14005F222
0x14005e333  mov     qword ptr [rbp+57h+var_B8], r15
0x14005e337  lea     r13, [rbx+6A8h]
0x14005e33e  call    cs:__imp_KeEnterCriticalRegion
0x14005e345  nop     dword ptr [rax+rax+00h]
0x14005e34a  xor     edx, edx
0x14005e34c  mov     rcx, r13
0x14005e34f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e356  nop     dword ptr [rax+rax+00h]
0x14005e35b  mov     rsi, [rbx+6B0h]
0x14005e362  test    rsi, rsi
0x14005e365  jz      loc_14005EC06
0x14005e36b  mov     eax, edi
0x14005e36d  lock xadd [rsi+14h], eax
0x14005e372  inc     eax
0x14005e374  cmp     cs:UxDebugCheckRefcount, r15b
0x14005e37b  jnz     loc_14005E848
0x14005e381  xor     edx, edx
0x14005e383  mov     rcx, r13
0x14005e386  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005e38d  nop     dword ptr [rax+rax+00h]
0x14005e392  call    cs:__imp_KeLeaveCriticalRegion
0x14005e399  nop     dword ptr [rax+rax+00h]
0x14005e39e  mov     rdi, [rsi+40h]
0x14005e3a2  call    cs:__imp_KeEnterCriticalRegion
0x14005e3a9  nop     dword ptr [rax+rax+00h]
0x14005e3ae  mov     rcx, [rdi+118h]
0x14005e3b5  xor     edx, edx
0x14005e3b7  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14005e3be  nop     dword ptr [rax+rax+00h]
0x14005e3c3  mov     qword ptr [rbp+57h+var_B8], rax
0x14005e3c7  call    cs:__imp_KeEnterCriticalRegion
0x14005e3ce  nop     dword ptr [rax+rax+00h]
0x14005e3d3  xor     edx, edx
0x14005e3d5  mov     rcx, r13
0x14005e3d8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e3df  nop     dword ptr [rax+rax+00h]
0x14005e3e4  cmp     [rbx+6B0h], rsi
0x14005e3eb  jnz     loc_14005F0B0
0x14005e3f1  mov     eax, r14d
0x14005e3f4  lock xadd [rsi+14h], eax
0x14005e3f9  dec     eax
0x14005e3fb  cmp     cs:UxDebugCheckRefcount, r15b
0x14005e402  jnz     loc_14005E8FB
0x14005e408  test    eax, eax
0x14005e40a  jnz     loc_14005E5D0
0x14005e410  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e417  jnz     loc_14005EEB7
0x14005e41d  mov     rax, [rsi+38h]
0x14005e421  movzx   edx, word ptr [rax+38h]
0x14005e425  mov     rax, [rsi+40h]
0x14005e429  mov     rcx, [rax+108h]
0x14005e430  mov     rdi, [rcx+rdx*8]
0x14005e434  call    cs:__imp_KeEnterCriticalRegion
0x14005e43b  nop     dword ptr [rax+rax+00h]
0x14005e440  mov     rcx, [rsi+38h]
0x14005e444  xor     edx, edx
0x14005e446  add     rcx, 3B0h
0x14005e44d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e454  nop     dword ptr [rax+rax+00h]
0x14005e459  call    cs:__imp_KeEnterCriticalRegion
0x14005e460  nop     dword ptr [rax+rax+00h]
0x14005e465  xor     edx, edx
0x14005e467  mov     rcx, rdi
0x14005e46a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e471  nop     dword ptr [rax+rax+00h]
0x14005e476  mov     rdx, [rsi+18h]
0x14005e47a  lea     rax, [rsi+18h]
0x14005e47e  cmp     [rdx+8], rax
0x14005e482  jnz     loc_14005E660
0x14005e488  mov     rcx, [rax+8]
0x14005e48c  cmp     [rcx], rax
0x14005e48f  jnz     loc_14005E660
0x14005e495  mov     [rcx], rdx
0x14005e498  mov     [rdx+8], rcx
0x14005e49c  mov     [rax], r15
0x14005e49f  mov     [rax+8], r15
0x14005e4a3  lea     rax, [rsi+28h]
0x14005e4a7  mov     r8, [rax]
0x14005e4aa  cmp     [r8+8], rax
0x14005e4ae  jnz     loc_14005E660
0x14005e4b4  mov     rdx, [rax+8]
0x14005e4b8  cmp     [rdx], rax
0x14005e4bb  jnz     loc_14005E660
0x14005e4c1  mov     [rdx], r8
0x14005e4c4  mov     rcx, rdi
0x14005e4c7  mov     [r8+8], rdx
0x14005e4cb  xor     edx, edx
0x14005e4cd  mov     [rax], r15
0x14005e4d0  mov     [rax+8], r15
0x14005e4d4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005e4db  nop     dword ptr [rax+rax+00h]
0x14005e4e0  call    cs:__imp_KeLeaveCriticalRegion
0x14005e4e7  nop     dword ptr [rax+rax+00h]
0x14005e4ec  mov     rcx, [rsi+38h]
0x14005e4f0  xor     edx, edx
0x14005e4f2  add     rcx, 3B0h
0x14005e4f9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005e500  nop     dword ptr [rax+rax+00h]
0x14005e505  call    cs:__imp_KeLeaveCriticalRegion
0x14005e50c  nop     dword ptr [rax+rax+00h]
0x14005e511  mov     rdx, [rsi+58h]; BugCheckParameter2
0x14005e515  test    rdx, rdx
0x14005e518  jnz     loc_14005E821
0x14005e51e  mov     rdx, [rsi+40h]; BugCheckParameter2
0x14005e522  mov     eax, r14d
0x14005e525  lock xadd [rdx], eax
0x14005e529  dec     eax
0x14005e52b  cmp     cs:UxDebugCheckRefcount, 0
0x14005e532  jnz     loc_14005E91C
0x14005e538  test    eax, eax
0x14005e53a  jz      loc_14005F260
0x14005e540  mov     rdi, [rsi+38h]
0x14005e544  mov     eax, r14d
0x14005e547  mov     [rsi+40h], r15
0x14005e54b  lea     rdx, [rdi+28h]; BugCheckParameter2
0x14005e54f  lock xadd [rdx], eax
0x14005e553  dec     eax
0x14005e555  cmp     cs:UxDebugCheckRefcount, 0
0x14005e55c  jnz     loc_14005E939
0x14005e562  test    eax, eax
0x14005e564  jz      loc_14005E8A4
0x14005e56a  cmp     cs:UxDebugDisableLookaside, 0
0x14005e571  mov     [rsi+38h], r15
0x14005e575  mov     dword ptr [rsi+10h], 75634C75h
0x14005e57c  jnz     loc_14005F2B8
0x14005e582  cmp     cs:UxCompactMode, 0
0x14005e589  jnz     loc_14005EBDF
0x14005e58f  mov     edi, [rsi]
0x14005e591  mov     rcx, cs:qword_1401A0910
0x14005e598  inc     edi
0x14005e59a  shl     rdi, 7
0x14005e59e  add     rdi, rcx
0x14005e5a1  movzx   eax, byte ptr [rdi+0B0h]
0x14005e5a8  test    al, al
0x14005e5aa  jz      loc_14005EF55
0x14005e5b0  mov     rdx, rsi; Entry
0x14005e5b3  lea     rcx, [rdi+40h]; Lookaside
0x14005e5b7  call    cs:__imp_ExFreeToLookasideListEx
0x14005e5be  nop     dword ptr [rax+rax+00h]
0x14005e5c3  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e5ca  jnz     loc_14005EEDA
0x14005e5d0  call    cs:__imp_KeEnterCriticalRegion
0x14005e5d7  nop     dword ptr [rax+rax+00h]
0x14005e5dc  lea     rcx, [rsi+48h]
0x14005e5e0  xor     edx, edx
0x14005e5e2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005e5e9  nop     dword ptr [rax+rax+00h]
0x14005e5ee  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005e5f5  jnz     loc_14005F2EA
0x14005e5fb  test    rsi, rsi
0x14005e5fe  jz      loc_14005E72E
0x14005e604  mov     ecx, [rbx+6C8h]
0x14005e60a  xor     dil, dil
0x14005e60d  sub     ecx, 1
0x14005e610  jz      loc_14005F029
0x14005e616  cmp     ecx, 1
0x14005e619  jnz     loc_14005E6C1
0x14005e61f  lea     rax, [rbx+6B8h]
0x14005e626  mov     rcx, [rax]
0x14005e629  cmp     [rcx+8], rax
0x14005e62d  jnz     short loc_14005E660
0x14005e62f  mov     rdx, [rax+8]
0x14005e633  cmp     [rdx], rax
0x14005e636  jnz     short loc_14005E660
0x14005e638  mov     [rdx], rcx
0x14005e63b  mov     dil, 1
0x14005e63e  mov     [rcx+8], rdx
0x14005e642  mov     [rax], r15
0x14005e645  mov     [rax+8], r15
0x14005e649  mov     dword ptr [rbx+6C8h], 3
0x14005e653  mov     rcx, [rsi+78h]
0x14005e657  add     rsi, 70h ; 'p'
0x14005e65b  cmp     [rcx], rsi
0x14005e65e  jz      short loc_14005E6AC
0x14005e660  mov     ecx, 3
0x14005e665  int     29h; Win8: RtlFailFast(ecx)
0x14005e667  test    rsi, rsi
0x14005e66a  jnz     loc_14005E196
0x14005e670  cmp     [rax+8], rdi
0x14005e674  jnz     short loc_14005E660
  ... truncated ...
```
