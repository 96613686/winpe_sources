# UlCleanupHttpConnection

- ea: `0x14006ce40`
- end: `0x14006e504`
- name: `UlCleanupHttpConnection`
- size: `5828`
- prototype: ``
- caller_count: `2`
- callee_count: `31`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a520`
- `0x14000f480`

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
- `0x14006caf0`
- `0x14006ce40`
- `0x14006e50c`
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

- `ntoskrnl!KeGetCurrentIrql` at `0x14006d6e3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006dc4c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006d6e3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006dc4c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006da2a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006dd81`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006da2a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006dd81`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006d32a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006d8f6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006d32a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006d8f6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006d983`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006dcd8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006d983`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006dcd8`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14006d9d9`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14006dd33`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14006d9d9`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14006dd33`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14006e2dd`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14006e39a`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14006e2dd`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14006e39a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006d70d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006dc73`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006d70d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006dc73`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006d747`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006dcb3`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006d747`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006dcb3`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14006daa3`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14006daa3`
- `ntoskrnl!KeSetEvent` at `0x14006da48`
- `ntoskrnl!KeSetEvent` at `0x14006dd9f`
- `ntoskrnl!KeSetEvent` at `0x14006da48`
- `ntoskrnl!KeSetEvent` at `0x14006dd9f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006d9ac`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006dd01`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006d9ac`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006dd01`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14006d120`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14006d120`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006db9a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006db9a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14006da86`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14006da86`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14006d47e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14006e105`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14006d47e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14006e105`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d03a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d0fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d24b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d270`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d44f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d46c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d491`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006dbe8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e0f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e119`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d03a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d0fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d24b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d270`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d44f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d46c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d491`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006dbe8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e0f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e119`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dbc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dbc6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d02e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d0ef`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d23f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d264`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d443`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d460`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006dbdc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006e0e7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d02e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d0ef`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d23f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d264`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d443`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d460`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006dbdc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006e0e7`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006d627`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006d627`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d00e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d0b8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d141`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d1b6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d1d3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d355`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d00e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d0b8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d141`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d1b6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d1d3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d355`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006cffc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d0a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d10b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d130`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d19d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d1c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d343`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006cffc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d0a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d10b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d130`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d19d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d1c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d343`

## pseudocode

```c
void __fastcall UlCleanupHttpConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbx
  unsigned __int64 *v6; // r12
  __int64 v7; // rsi
  _QWORD **v8; // rdi
  _QWORD *v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rdi
  unsigned __int8 v13; // si
  __int64 *v14; // rdi
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // r13
  _DWORD *v18; // rsi
  int v19; // eax
  __int64 v20; // rdi
  int v21; // eax
  __int64 v22; // rdi
  __int64 v23; // rdx
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // r8
  _QWORD *v28; // rdx
  volatile signed __int32 *v29; // rdx
  volatile signed __int32 *v30; // rdx
  int v31; // eax
  __int64 v32; // rdi
  int v33; // eax
  bool v34; // zf
  unsigned __int64 v35; // rdi
  char v36; // di
  _QWORD *v37; // rax
  __int64 v38; // rcx
  _QWORD *v39; // rdx
  _QWORD *v40; // r8
  _DWORD *v41; // rsi
  _QWORD *v42; // rcx
  int v43; // eax
  __int64 v44; // rdi
  int v45; // eax
  int v46; // eax
  __int64 v47; // r12
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v49; // r9
  void *CurrentServerSilo; // r13
  __int64 v51; // rcx
  void *v52; // rsi
  char v53; // bl
  __int64 v54; // rax
  __int64 v55; // r12
  _QWORD *v56; // rdi
  _DWORD *v57; // rbx
  _QWORD *v58; // rax
  _QWORD *v59; // rcx
  int v60; // r15d
  int v61; // eax
  char *v62; // rdi
  __int64 (__fastcall **v63)(); // rsi
  __int64 *v64; // r8
  __int64 v65; // r8
  unsigned __int64 v66; // rdi
  ULONG v67; // ebx
  ULONG_PTR v68; // rdx
  int v69; // eax
  __int64 v70; // rbx
  ULONG_PTR v71; // rdx
  __int64 v72; // rdi
  USHORT CurrentNodeNumber; // ax
  char v74; // di
  __int64 v75; // rax
  __int64 v76; // r13
  ULONG v77; // edi
  ULONG_PTR v78; // rdx
  int v79; // eax
  __int64 v80; // rdi
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  char v84; // al
  __int64 v85; // rax
  __int64 v86; // rax
  unsigned __int64 v87; // rax
  int v88; // eax
  __int64 v89; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v90; // [rsp+48h] [rbp-61h] BYREF
  __int128 v91; // [rsp+50h] [rbp-59h] BYREF
  __int128 v92; // [rsp+60h] [rbp-49h] BYREF
  _DWORD v93[24]; // [rsp+70h] [rbp-39h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a1 )
      v85 = *(_QWORD *)(a1 + 48);
    else
      v85 = 0;
    WPP_SF_qq(1032, 27, WPP_682cf469470432b235cb9a4961616e40_Traceguids, a1, v85);
  }
  v5 = *(_QWORD *)(a1 + 568);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( v5 )
      v86 = *(_QWORD *)(v5 + 64);
    else
      v86 = 0;
    WPP_SF_qq(1032, 55, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v5, v86);
  }
  v6 = (unsigned __int64 *)(v5 + 64);
  *(_QWORD *)&v92 = v5 + 64;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( v5 )
      v87 = *v6;
    else
      v87 = 0;
    WPP_SF_qq(1032, 38, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v5, v87);
  }
  *(_DWORD *)(v5 + 2200) |= 0x200u;
  if ( (*(_DWORD *)(v5 + 2200) & 0x1000) == 0 )
  {
    v81 = *(_QWORD *)(v5 + 2512);
    if ( v81 )
    {
      LOBYTE(a2) = 1;
      UlHkeCancelCalloutContext(v81, a2);
    }
    v82 = *(_QWORD *)(v5 + 2520);
    if ( v82 )
    {
      LOBYTE(a2) = 1;
      UlHkeCancelCalloutContext(v82, a2);
    }
    v83 = *(_QWORD *)(v5 + 2528);
    if ( v83 )
    {
      LOBYTE(a2) = 1;
      UlHkeCancelCalloutContext(v83, a2);
    }
  }
  *(_DWORD *)(v5 + 2200) &= ~0x1000u;
  v7 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 95, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, v5);
  v8 = (_QWORD **)(v5 + 504);
  while ( 1 )
  {
    v9 = *v8;
    if ( *v8 == v8 || v7 )
      break;
    if ( (_QWORD **)v9[1] != v8 )
      goto LABEL_70;
    v42 = (_QWORD *)*v9;
    if ( *(_QWORD **)(*v9 + 8LL) != v9 )
      goto LABEL_70;
    *v8 = v42;
    v7 = (__int64)(v9 - 21);
    v42[1] = v8;
    v9[1] = v9;
    *v9 = v9;
    if ( _InterlockedExchange64(v9 - 8, 0) )
    {
      if ( *(_BYTE *)(v7 + 68) )
      {
        UlCompleteReceiveEntityBodyIrp(v5, v7, 3221225760LL);
        v7 = 0;
      }
    }
    else
    {
      v7 = 0;
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 96, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, v7);
  for ( ; v7; v7 = UlDequeueReceiveEntityBodyIrp(v5) )
    UlCompleteReceiveEntityBodyIrp(v5, v7, 3221225760LL);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 39, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
  if ( *v6 )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(v5 + 24) + 1096LL);
    if ( *(_BYTE *)(v10 + 79) && Microsoft_Windows_Networking_CorrelationEnabled )
      UlEtwStopActivity(v5 + 72, 3);
    v11 = *v6;
    v90 = -1;
    LODWORD(v89) = 0;
    LODWORD(v91) = 0;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_iqqq(v10, a2, a3, v11, &v89, &v90, &v91);
    v12 = HIDWORD(v11);
    v90 = 0;
    LODWORD(v91) = 0;
    LODWORD(v89) = v12 & 0xFFF;
    if ( (unsigned int)v89 >= UxMaximumNumberOfProcessors )
    {
      if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
        WPP_SF_(521, 11, WPP_6218f2abddb13899518e42ce65335ae2_Traceguids);
    }
    else
    {
      a2 = ((unsigned int)v12 >> 12) & 0xFFF;
      v10 = (v12 & 0xFFF) << 6;
      v90 = a2;
      if ( (unsigned int)a2 < *(_DWORD *)((char *)UxOpaqueIdTable + v10 + 40) )
      {
        v13 = 1;
        LODWORD(v91) = BYTE3(v12);
LABEL_23:
        if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
          WPP_SF_lLLL(v10, a2, a3, v13, v89, v90, v91);
        if ( v13 )
        {
          v14 = (__int64 *)(48LL * (unsigned int)v91
                          + *(_QWORD *)(*((_QWORD *)UxOpaqueIdTable + 8 * (unsigned __int64)(unsigned int)v89 + 2)
                                      + 8LL * v90));
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(v14 + 4, 0);
          v15 = *v14;
          *(_DWORD *)(v15 + 32) &= 0xFFFFFFFu;
          *(_QWORD *)(v15 + 24) = 0;
          ExReleasePushLockExclusiveEx(v14 + 4, 0);
          KeLeaveCriticalRegion();
        }
        *v6 = 0;
        v16 = _InterlockedDecrement((volatile signed __int32 *)(v5 + 48));
        if ( UxDebugCheckRefcount && v16 <= -1 )
          UlBugCheckEx(3u, v5 + 48, 0x10u, v16);
        if ( !v16 )
          UlpQueueFreeHttpRequest(v5);
        goto LABEL_30;
      }
      if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
      {
        WPP_SF_(521, 12, WPP_6218f2abddb13899518e42ce65335ae2_Traceguids);
        v13 = 0;
        goto LABEL_23;
      }
    }
    v13 = 0;
    goto LABEL_23;
  }
LABEL_30:
  v89 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 235, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v5, *v6);
  if ( *(_BYTE *)(v5 + 1852) )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_qqP(1032, 38, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v5, *v6, &v89);
    v89 = 0;
    v17 = v5 + 1704;
    while ( 1 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v5 + 1704, 0);
      v18 = *(_DWORD **)(v5 + 1712);
      if ( !v18 )
      {
        ExReleasePushLockExclusiveEx(v5 + 1704, 0);
        KeLeaveCriticalRegion();
        goto LABEL_61;
      }
      v19 = _InterlockedIncrement(v18 + 5);
      if ( UxDebugCheckRefcount && v19 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v18 + 5), 0x21u, v19);
      ExReleasePushLockExclusiveEx(v5 + 1704, 0);
      KeLeaveCriticalRegion();
      v20 = *((_QWORD *)v18 + 8);
      KeEnterCriticalRegion();
      v89 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v20 + 280), 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v5 + 1704, 0);
      if ( *(_DWORD **)(v5 + 1712) == v18 )
        break;
      ExReleasePushLockExclusiveEx(v5 + 1704, 0);
      KeLeaveCriticalRegion();
      ExReleaseCacheAwarePushLockSharedEx(v89, 0);
      v89 = 0;
      KeLeaveCriticalRegion();
      v88 = _InterlockedDecrement(v18 + 5);
      if ( UxDebugCheckRefcount && v88 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v18 + 5), 0x21u, v88);
      if ( !v88 )
        UlpFreeCoupling(v18);
    }
    v21 = _InterlockedDecrement(v18 + 5);
    if ( UxDebugCheckRefcount && v21 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v18 + 5), 0x21u, v21);
    if ( !v21 )
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v18, 0);
      v22 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v18 + 8) + 264LL)
                      + 8LL * *(unsigned __int16 *)(*((_QWORD *)v18 + 7) + 56LL));
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(*((_QWORD *)v18 + 7) + 944LL, 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v22, 0);
      v23 = *((_QWORD *)v18 + 3);
      v24 = v18 + 6;
      if ( *(_DWORD **)(v23 + 8) == v18 + 6 )
      {
        v25 = (_QWORD *)*((_QWORD *)v18 + 4);
        if ( (_QWORD *)*v25 == v24 )
        {
          *v25 = v23;
          *(_QWORD *)(v23 + 8) = v25;
          *v24 = 0;
          *((_QWORD *)v18 + 4) = 0;
          v26 = v18 + 10;
          v27 = *((_QWORD *)v18 + 5);
          if ( *(_DWORD **)(v27 + 8) == v18 + 10 )
          {
            v28 = (_QWORD *)*((_QWORD *)v18 + 6);
            if ( (_QWORD *)*v28 == v26 )
            {
              *v28 = v27;
              *(_QWORD *)(v27 + 8) = v28;
              *v26 = 0;
              *((_QWORD *)v18 + 6) = 0;
              ExReleasePushLockExclusiveEx(v22, 0);
              KeLeaveCriticalRegion();
              ExReleasePushLockExclusiveEx(*((_QWORD *)v18 + 7) + 944LL, 0);
              KeLeaveCriticalRegion();
              v29 = (volatile signed __int32 *)*((_QWORD *)v18 + 11);
              if ( v29 )
              {
                v46 = _InterlockedDecrement(v29);
                if ( UxDebugCheckRefcount && v46 <= -1 )
                  UlBugCheckEx(3u, (ULONG_PTR)v29, 0xEu, v46);
                if ( !v46 )
                  UlConsumerCleanupCompletion(*((_QWORD *)v18 + 11));
                *((_QWORD *)v18 + 11) = 0;
              }
              v30 = (volatile signed __int32 *)*((_QWORD *)v18 + 8);
              v31 = _InterlockedDecrement(v30);
              if ( UxDebugCheckRefcount && v31 <= -1 )
                UlBugCheckEx(3u, (ULONG_PTR)v30, 0xEu, v31);
              if ( !v31 )
                UlFreeRequestQueue(*((PVOID *)v18 + 8));
              v32 = *((_QWORD *)v18 + 7);
              *((_QWORD *)v18 + 8) = 0;
              v33 = _InterlockedDecrement((volatile signed __int32 *)(v32 + 40));
              if ( UxDebugCheckRefcount && v33 <= -1 )
                UlBugCheckEx(3u, v32 + 40, 0xEu, v33);
              if ( v33 )
              {
LABEL_53:
                v34 = UxDebugDisableLookaside == 0;
                *((_QWORD *)v18 + 7) = 0;
                v18[4] = 1969441909;
                if ( v34 )
                {
                  if ( UxCompactMode )
                  {
                    v72 = qword_1401A0910;
                    CurrentNodeNumber = KeGetCurrentNodeNumber();
                    PplFreeToLookasideListProcessor(v72, v18, CurrentNodeNumber);
                  }
                  else
                  {
                    v35 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*v18 + 1) << 7);
                    if ( !*(_BYTE *)(v35 + 176) )
                      PplpLazyInitializeLookasideList(qword_1401A0910, v35 + 64);
                    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v35 + 64), v18);
                  }
                }
                else
                {
                  memset(v93, 0, sizeof(v93));
                  v93[10] = dword_1401A0928;
                  ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A0938)(v18, v93);
                }
                if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
                  WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
                goto LABEL_60;
              }
              v47 = v32 + 64;
              CurrentProcess = IoGetCurrentProcess();
              CurrentServerSilo = *(void **)(v32 + 1088);
              v51 = *(_QWORD *)(v32 + 64);
              if ( UxSystemProcess != CurrentProcess )
              {
                if ( v51 || *(_QWORD *)(v32 + 80) || *(_QWORD *)(v32 + 96) )
                  UlBugCheckEx(1u, v32 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
                LOBYTE(v49) = 1;
                UlThreadPoolEnqueueWorkItem(0, v32 + 64, UlFreeHttpConnection, v49, CurrentServerSilo, -1);
                v17 = v5 + 1704;
                goto LABEL_53;
              }
              if ( v51 || *(_QWORD *)(v32 + 80) || *(_QWORD *)(v32 + 96) )
                UlBugCheckEx(1u, v32 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
              if ( KeGetCurrentIrql() )
              {
                v77 = 0;
                if ( (unsigned int)dword_1401A3F48 > 1 )
                {
                  v77 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
                  if ( byte_1401A3F60 )
                    v77 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
                }
                if ( CurrentServerSilo == (void *)-1LL )
                  CurrentServerSilo = (void *)PsGetCurrentServerSilo();
                *(_QWORD *)(v47 + 32) = CurrentServerSilo;
                *(_QWORD *)&v91 = 0;
                if ( CurrentServerSilo )
                  ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
                PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v91);
                v78 = v91 + 24;
                v79 = _InterlockedIncrement((volatile signed __int32 *)(v91 + 24));
                if ( UxDebugCheckRefcount && v79 <= -1 )
                  UlBugCheckEx(3u, v78, 0xDu, v79);
                *(_BYTE *)(v47 + 24) = 1;
                v80 = *(_QWORD *)(qword_1401A3F50 + 8LL * v77);
                *(_QWORD *)(v47 + 16) = UlFreeHttpConnection;
                if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v80 + 16), (PSLIST_ENTRY)v47) )
                {
                  KeSetEvent((PRKEVENT)(v80 + 32), 0, 0);
                  UlpActivateThreadPoolQueue((PVOID)v80);
                  v17 = v5 + 1704;
                  goto LABEL_53;
                }
              }
              else
              {
                v74 = 0;
                v91 = 0;
                if ( CurrentServerSilo == (void *)-1LL )
                {
                  v76 = *((_QWORD *)&v91 + 1);
LABEL_204:
                  UlFreeHttpConnection(v47);
                  if ( v74 )
                    goto LABEL_205;
                }
                else
                {
                  v75 = PsAttachSiloToCurrentThread(CurrentServerSilo);
                  *(_QWORD *)&v91 = v75;
                  v74 = 1;
                  if ( (BYTE11(xmmword_1401A2CA0) & 0x10) == 0 )
                  {
                    v76 = v75;
                    goto LABEL_204;
                  }
                  WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v75, CurrentServerSilo);
                  UlFreeHttpConnection(v47);
                  v76 = v91;
LABEL_205:
                  if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
                    WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v76);
                  PsDetachSiloFromCurrentThread(v76);
                }
              }
              v17 = v5 + 1704;
              goto LABEL_53;
            }
          }
        }
      }
LABEL_70:
      __fastfail(3u);
    }
LABEL_60:
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v18 + 18, 0);
LABEL_61:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_q(1032, 39, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v18);
    if ( !v18 )
      goto LABEL_78;
    v36 = 0;
    if ( *(_DWORD *)(v5 + 1736) == 1 )
    {
      v84 = UlpRemoveRequestFromLane(v5);
      *(_DWORD *)(v5 + 1736) = 3;
      v36 = v84;
      if ( v84 )
      {
LABEL_69:
        v40 = (_QWORD *)*((_QWORD *)v18 + 15);
        v41 = v18 + 28;
        if ( (_DWORD *)*v40 != v41 )
          goto LABEL_70;
        *(_QWORD *)(v5 + 1816) = v41;
        *(_QWORD *)(v5 + 1824) = v40;
        *v40 = v5 + 1816;
        *((_QWORD *)v41 + 1) = v5 + 1816;
      }
    }
    else if ( *(_DWORD *)(v5 + 1736) == 2 )
    {
      v37 = (_QWORD *)(v5 + 1720);
      v38 = *(_QWORD *)(v5 + 1720);
      if ( *(_QWORD *)(v38 + 8) != v5 + 1720 )
        goto LABEL_70;
      v39 = *(_QWORD **)(v5 + 1728);
      if ( (_QWORD *)*v39 != v37 )
        goto LABEL_70;
      *v39 = v38;
      v36 = 1;
      *(_QWORD *)(v38 + 8) = v39;
      *v37 = 0;
      *(_QWORD *)(v5 + 1728) = 0;
      *(_DWORD *)(v5 + 1736) = 3;
      goto LABEL_69;
    }
    ExReleasePushLockExclusiveEx(*(_QWORD *)(v5 + 1712) + 72LL, 0);
    KeLeaveCriticalRegion();
    ExReleasePushLockExclusiveEx(v17, 0);
    KeLeaveCriticalRegion();
    ExReleaseCacheAwarePushLockSharedEx(v89, 0);
    v89 = 0;
    KeLeaveCriticalRegion();
    if ( v36 )
    {
      v45 = _InterlockedDecrement((volatile signed __int32 *)(v5 + 48));
      if ( UxDebugCheckRefcount && v45 <= -1 )
        UlBugCheckEx(3u, v5 + 48, 0xCu, v45);
      if ( !v45 )
        UlpQueueFreeHttpRequest(v5);
    }
LABEL_78:
    v6 = (unsigned __int64 *)v92;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 236, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  v43 = _InterlockedDecrement((volatile signed __int32 *)(v5 + 48));
  if ( UxDebugCheckRefcount && v43 <= -1 )
    UlBugCheckEx(3u, v5 + 48, 1u, v43);
  if ( v43 )
    goto LABEL_92;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 40, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v5, *v6);
  if ( (*(_DWORD *)(v5 + 2264) & 1) != 0 || *(_QWORD *)(v5 + 2288) || *(_QWORD *)(v5 + 2312) )
  {
    v71 = v5 + 1248;
    if ( *(_QWORD *)(v5 + 1248) || *(_QWORD *)(v5 + 1264) || *(_QWORD *)(v5 + 1280) )
      UlBugCheckEx(1u, v71, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x645u);
    LOBYTE(a4) = 1;
    UlThreadPoolEnqueueWorkItem(0, v71, UlpFreeHttpRequest, a4, *(_QWORD *)(*(_QWORD *)(v5 + 24) + 1088LL), -1);
  }
  else
  {
    v44 = v5 + 1248;
    if ( *(_QWORD *)(v5 + 1248) || *(_QWORD *)(v5 + 1264) || *(_QWORD *)(v5 + 1280) )
      UlBugCheckEx(1u, v5 + 1248, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x64Du);
    v52 = *(void **)(*(_QWORD *)(v5 + 24) + 1088LL);
    if ( !KeGetCurrentIrql() )
    {
      v53 = 0;
      v92 = 0;
      if ( v52 == (void *)-1LL )
      {
        v55 = *((_QWORD *)&v92 + 1);
      }
      else
      {
        v54 = PsAttachSiloToCurrentThread(v52);
        v55 = v54;
        v53 = 1;
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
        {
          WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v54, v52);
          UlpFreeHttpRequest(v44);
LABEL_122:
          if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v55);
          PsDetachSiloFromCurrentThread(v55);
          goto LABEL_125;
        }
      }
      UlpFreeHttpRequest(v44);
      if ( !v53 )
        goto LABEL_125;
      goto LABEL_122;
    }
    v67 = 0;
    if ( (unsigned int)dword_1401A3F48 > 1 )
    {
      v67 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
      if ( byte_1401A3F60 )
        v67 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
    }
    if ( v52 == (void *)-1LL )
      v52 = (void *)PsGetCurrentServerSilo();
    *(_QWORD *)(v44 + 32) = v52;
    *(_QWORD *)&v92 = 0;
    if ( v52 )
      ObfReferenceObjectWithTag(v52, 0x49576C55u);
    PsGetPermanentSiloContext(v52, (unsigned int)UxPodMonitorSlot, &v92);
    v68 = v92 + 24;
    v69 = _InterlockedIncrement((volatile signed __int32 *)(v92 + 24));
    if ( UxDebugCheckRefcount && v69 <= -1 )
      UlBugCheckEx(3u, v68, 0xDu, v69);
    *(_BYTE *)(v44 + 24) = 1;
    v70 = *(_QWORD *)(qword_1401A3F50 + 8LL * v67);
    *(_QWORD *)(v44 + 16) = UlpFreeHttpRequest;
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v70 + 16), (PSLIST_ENTRY)v44) )
    {
      KeSetEvent((PRKEVENT)(v70 + 32), 0, 0);
      if ( *(_BYTE *)(*(_QWORD *)v70 + 33LL) )
      {
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v70 + 68), 1, 0) )
        {
          if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_Dd(
              1304,
              18,
              WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids,
              *(unsigned int *)(v70 + 8),
              **(_DWORD **)v70);
          _InterlockedIncrement((volatile signed __int32 *)(v70 + 64));
          ExAcquireRundownProtection(&UlThreadPoolIoWorkItemsRundown);
          IoQueueWorkItemEx(*(PIO_WORKITEM *)(v70 + 56), UlpThreadPoolStarter, DelayedWorkQueue, (PVOID)v70);
        }
      }
    }
  }
LABEL_125:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_(1032, 41, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
LABEL_92:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 56, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
  }
  *(_DWORD *)(a1 + 632) &= ~4u;
  *(_QWORD *)(a1 + 568) = 0;
  if ( (BYTE9(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_q(1294, 28, WPP_682cf469470432b235cb9a4961616e40_Traceguids, a1);
  if ( *(_QWORD *)(a1 + 600) )
  {
    v56 = *(_QWORD **)(a1 + 584);
    while ( 1 )
    {
      if ( v56 == (_QWORD *)(a1 + 584) )
        goto LABEL_160;
      v57 = v56 - 6;
      if ( v56 - 6 == *(_QWORD **)(a1 + 600) )
        break;
      v56 = (_QWORD *)*v56;
      UlReleaseRequestBuffer(a1, v57);
    }
    if ( v57[32] == v57[34] )
    {
      v92 = 0;
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_qq(1032, 50, WPP_682cf469470432b235cb9a4961616e40_Traceguids, a1, v56 - 6);
      if ( (BYTE9(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_q(1288, 51, WPP_682cf469470432b235cb9a4961616e40_Traceguids, *((_QWORD *)v57 + 18));
      v58 = (_QWORD *)*v56;
      if ( *v56 )
      {
        if ( (_QWORD *)v58[1] != v56 )
          goto LABEL_70;
        v59 = (_QWORD *)v56[1];
        if ( (_QWORD *)*v59 != v56 )
          goto LABEL_70;
        *v59 = v58;
        v58[1] = v59;
        *v56 = 0;
        *((_QWORD *)v57 + 7) = 0;
      }
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 1096) + 79LL) && Microsoft_Windows_Networking_CorrelationEnabled )
      {
        *((_QWORD *)&v92 + 1) = *((_QWORD *)&UlEtwBasePtrActivityGuid + 1);
        *(_QWORD *)&v92 = v56 - 6;
        UlEtwStopActivity(&v92, 2);
      }
      v60 = _InterlockedDecrement(v57 + 8);
      if ( UxDebugCheckRefcount && v60 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v57 + 8), 1u, v60);
      if ( !v60 )
      {
        if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          WPP_SF_q(1032, 53, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v56 - 6);
        if ( *((_QWORD *)v57 + 19) )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 504) + 128LL))(*(_QWORD *)(a1 + 496));
          *((_QWORD *)v57 + 19) = 0;
        }
        v61 = v57[35];
        if ( v61 == 4 )
        {
          v57[4] = 1886538869;
          ExFreePoolWithTag(v56 - 6, 0);
        }
        else
        {
          if ( v61 )
          {
            if ( v61 == 1 )
            {
              v62 = aUlrp_0;
              v63 = &off_1401A0128;
              v64 = &qword_1401A0100;
            }
            else if ( v61 == 2 )
            {
              v62 = aUlrp_1;
              v63 = &off_1401A00F8;
              v64 = &qword_1401A00D0;
            }
            else
            {
              v62 = aUlrp_2;
              v63 = &funcs_140069447;
              v64 = &UlLookaside;
            }
          }
          else
          {
            v62 = aUlrp;
            v63 = &off_1401A0158;
            v64 = &qword_1401A0130;
          }
          v34 = UxDebugDisableLookaside == 0;
          v57[4] = 1347570805;
          if ( v34 )
          {
            v65 = *v64;
            if ( UxCompactMode )
            {
              PnlFreeToLookasideList(v65, v57);
            }
            else
            {
              v66 = v65 + ((unsigned __int64)(unsigned int)(*v57 + 1) << 7);
              if ( !*(_BYTE *)(v66 + 176) )
                PplpLazyInitializeLookasideList(v65, v66 + 64);
              ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v66 + 64), v57);
            }
          }
          else
          {
            memset(v93, 0, sizeof(v93));
            v93[10] = *(_DWORD *)v62;
            ((void (__fastcall *)(_DWORD *, _DWORD *))*v63)(v57, v93);
          }
        }
        if ( (BYTE1(xmmword_1401A2CA0) & 1) == 0 )
          goto LABEL_159;
        WPP_SF_(1032, 54, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
      }
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_(1032, 52, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
LABEL_159:
      *(_QWORD *)(a1 + 600) = 0;
    }
  }
LABEL_160:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 29, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
}

```

## disassembly

```asm
0x14006ce40  mov     [rsp-8+arg_10], rbx
0x14006ce45  mov     [rsp-8+arg_18], rsi
0x14006ce4a  push    rbp
0x14006ce4b  push    rdi
0x14006ce4c  push    r12
0x14006ce4e  push    r13
0x14006ce50  push    r14
0x14006ce52  lea     rbp, [rsp-37h]
0x14006ce57  sub     rsp, 0E0h
0x14006ce5e  mov     rax, cs:__security_cookie
0x14006ce65  xor     rax, rsp
0x14006ce68  mov     [rbp+57h+var_30], rax
0x14006ce6c  mov     r14, rcx
0x14006ce6f  xor     r13d, r13d
0x14006ce72  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ce79  jnz     loc_14006E04F
0x14006ce7f  mov     rbx, [r14+238h]
0x14006ce86  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ce8d  jnz     loc_14006E080
0x14006ce93  mov     eax, 40h ; '@'
0x14006ce98  mov     rcx, rbx
0x14006ce9b  lea     r12, [rbx+rax]
0x14006ce9f  mov     qword ptr [rbp+57h+var_A0], r12
0x14006cea3  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ceaa  jnz     loc_14006E0B1
0x14006ceb0  or      dword ptr [rbx+898h], 200h
0x14006ceba  test    dword ptr [rbx+898h], 1000h
0x14006cec4  jz      loc_14006DF1A
0x14006ceca  and     dword ptr [rbx+898h], 0FFFFEFFFh
0x14006ced4  mov     rsi, r13
0x14006ced7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006cede  jnz     loc_14006DE87
0x14006cee4  lea     rdi, [rbx+1F8h]
0x14006ceeb  mov     [rsp+100h+arg_8], r15
0x14006cef3  mov     rax, [rdi]
0x14006cef6  cmp     rax, rdi
0x14006cef9  jnz     loc_14006D3DC
0x14006ceff  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006cf06  jnz     loc_14006E189
0x14006cf0c  test    rsi, rsi
0x14006cf0f  jnz     loc_14006DE60
0x14006cf15  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006cf1c  jnz     loc_14006DF56
0x14006cf22  mov     r15d, 0FFFFFFFFh
0x14006cf28  cmp     [r12], r13
0x14006cf2c  jz      loc_14006D06C
0x14006cf32  mov     rax, [rbx+18h]
0x14006cf36  mov     rcx, [rax+448h]
0x14006cf3d  cmp     [rcx+4Fh], r13b
0x14006cf41  jz      short loc_14006CF51
0x14006cf43  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14006cf49  test    eax, eax
0x14006cf4b  jnz     loc_14006E1A7
0x14006cf51  mov     rdi, [r12]
0x14006cf55  mov     [rbp+57h+var_B8], 0FFFFFFFFh
0x14006cf5c  mov     dword ptr [rbp+57h+var_C0], r13d
0x14006cf60  mov     dword ptr [rbp+57h+var_B0], r13d
0x14006cf64  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14006cf6b  jnz     loc_14006E1BA
0x14006cf71  shr     rdi, 20h
0x14006cf75  mov     eax, edi
0x14006cf77  mov     [rbp+57h+var_B8], r13d
0x14006cf7b  and     eax, 0FFFh
0x14006cf80  mov     dword ptr [rbp+57h+var_B0], r13d
0x14006cf84  cmp     eax, cs:UxMaximumNumberOfProcessors
0x14006cf8a  mov     dword ptr [rbp+57h+var_C0], eax
0x14006cf8d  jnb     loc_14006DE41
0x14006cf93  mov     ecx, eax
0x14006cf95  mov     edx, edi
0x14006cf97  mov     rax, cs:UxOpaqueIdTable
0x14006cf9e  shr     edx, 0Ch
0x14006cfa1  and     edx, 0FFFh
0x14006cfa7  shl     rcx, 6
0x14006cfab  mov     [rbp+57h+var_B8], edx
0x14006cfae  cmp     edx, [rcx+rax+28h]
0x14006cfb2  jnb     loc_14006E1FD
0x14006cfb8  shr     edi, 18h
0x14006cfbb  mov     sil, 1
0x14006cfbe  mov     dword ptr [rbp+57h+var_B0], edi
0x14006cfc1  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14006cfc8  jnz     loc_14006E228
0x14006cfce  test    sil, sil
0x14006cfd1  jz      short loc_14006D046
0x14006cfd3  mov     rax, cs:UxOpaqueIdTable
0x14006cfda  mov     ecx, dword ptr [rbp+57h+var_C0]
0x14006cfdd  mov     r8d, [rbp+57h+var_B8]
0x14006cfe1  shl     rcx, 6
0x14006cfe5  mov     rdx, [rcx+rax+10h]
0x14006cfea  mov     eax, dword ptr [rbp+57h+var_B0]
0x14006cfed  mov     rdi, [rdx+r8*8]
0x14006cff1  lea     rcx, [rax+rax*2]
0x14006cff5  shl     rcx, 4
0x14006cff9  add     rdi, rcx
0x14006cffc  call    cs:__imp_KeEnterCriticalRegion
0x14006d003  nop     dword ptr [rax+rax+00h]
0x14006d008  xor     edx, edx
0x14006d00a  lea     rcx, [rdi+20h]
0x14006d00e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d015  nop     dword ptr [rax+rax+00h]
0x14006d01a  mov     rax, [rdi]
0x14006d01d  lea     rcx, [rdi+20h]
0x14006d021  xor     edx, edx
0x14006d023  and     dword ptr [rax+20h], 0FFFFFFFh
0x14006d02a  mov     [rax+18h], r13
0x14006d02e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006d035  nop     dword ptr [rax+rax+00h]
0x14006d03a  call    cs:__imp_KeLeaveCriticalRegion
0x14006d041  nop     dword ptr [rax+rax+00h]
0x14006d046  mov     [r12], r13
0x14006d04a  lea     rdx, [rbx+30h]; BugCheckParameter2
0x14006d04e  mov     eax, r15d
0x14006d051  lock xadd [rdx], eax
0x14006d055  dec     eax
0x14006d057  cmp     cs:UxDebugCheckRefcount, r13b
0x14006d05e  jnz     loc_14006D606
0x14006d064  test    eax, eax
0x14006d066  jz      loc_14006E24B
0x14006d06c  mov     [rbp+57h+var_C0], r13
0x14006d070  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006d077  jnz     loc_14006DC25
0x14006d07d  mov     edi, 1
0x14006d082  cmp     [rbx+73Ch], r13b
0x14006d089  jz      loc_14006D4AA
0x14006d08f  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14006d096  jnz     loc_14006E258
0x14006d09c  mov     [rbp+57h+var_C0], r13
0x14006d0a0  lea     r13, [rbx+6A8h]
0x14006d0a7  call    cs:__imp_KeEnterCriticalRegion
0x14006d0ae  nop     dword ptr [rax+rax+00h]
0x14006d0b3  xor     edx, edx
0x14006d0b5  mov     rcx, r13
0x14006d0b8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d0bf  nop     dword ptr [rax+rax+00h]
0x14006d0c4  mov     rsi, [rbx+6B0h]
0x14006d0cb  test    rsi, rsi
0x14006d0ce  jz      loc_14006DBD7
0x14006d0d4  mov     eax, edi
0x14006d0d6  lock xadd [rsi+14h], eax
0x14006d0db  inc     eax
0x14006d0dd  cmp     cs:UxDebugCheckRefcount, 0
0x14006d0e4  jnz     loc_14006D5C8
0x14006d0ea  xor     edx, edx
0x14006d0ec  mov     rcx, r13
0x14006d0ef  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006d0f6  nop     dword ptr [rax+rax+00h]
0x14006d0fb  call    cs:__imp_KeLeaveCriticalRegion
0x14006d102  nop     dword ptr [rax+rax+00h]
0x14006d107  mov     rdi, [rsi+40h]
0x14006d10b  call    cs:__imp_KeEnterCriticalRegion
0x14006d112  nop     dword ptr [rax+rax+00h]
0x14006d117  mov     rcx, [rdi+118h]
0x14006d11e  xor     edx, edx
0x14006d120  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14006d127  nop     dword ptr [rax+rax+00h]
0x14006d12c  mov     [rbp+57h+var_C0], rax
0x14006d130  call    cs:__imp_KeEnterCriticalRegion
0x14006d137  nop     dword ptr [rax+rax+00h]
0x14006d13c  xor     edx, edx
0x14006d13e  mov     rcx, r13
0x14006d141  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d148  nop     dword ptr [rax+rax+00h]
0x14006d14d  cmp     [rbx+6B0h], rsi
0x14006d154  jnz     loc_14006E0E2
0x14006d15a  mov     eax, r15d
0x14006d15d  lock xadd [rsi+14h], eax
0x14006d162  dec     eax
0x14006d164  cmp     cs:UxDebugCheckRefcount, 0
0x14006d16b  jnz     loc_14006D67D
0x14006d171  test    eax, eax
0x14006d173  jnz     loc_14006D343
0x14006d179  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006d180  jnz     loc_14006DEA5
0x14006d186  mov     rax, [rsi+38h]
0x14006d18a  movzx   edx, word ptr [rax+38h]
0x14006d18e  mov     rax, [rsi+40h]
0x14006d192  mov     rcx, [rax+108h]
0x14006d199  mov     rdi, [rcx+rdx*8]
0x14006d19d  call    cs:__imp_KeEnterCriticalRegion
0x14006d1a4  nop     dword ptr [rax+rax+00h]
0x14006d1a9  mov     rcx, [rsi+38h]
0x14006d1ad  xor     edx, edx
0x14006d1af  add     rcx, 3B0h
0x14006d1b6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d1bd  nop     dword ptr [rax+rax+00h]
0x14006d1c2  call    cs:__imp_KeEnterCriticalRegion
0x14006d1c9  nop     dword ptr [rax+rax+00h]
0x14006d1ce  xor     edx, edx
0x14006d1d0  mov     rcx, rdi
0x14006d1d3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d1da  nop     dword ptr [rax+rax+00h]
0x14006d1df  mov     rdx, [rsi+18h]
0x14006d1e3  lea     rax, [rsi+18h]
0x14006d1e7  cmp     [rdx+8], rax
0x14006d1eb  jnz     loc_14006D3D5
0x14006d1f1  mov     rcx, [rax+8]
0x14006d1f5  cmp     [rcx], rax
0x14006d1f8  jnz     loc_14006D3D5
0x14006d1fe  mov     [rcx], rdx
0x14006d201  mov     [rdx+8], rcx
0x14006d205  xor     ecx, ecx
0x14006d207  mov     [rax], rcx
0x14006d20a  mov     [rax+8], rcx
0x14006d20e  lea     rax, [rsi+28h]
0x14006d212  mov     r8, [rax]
0x14006d215  cmp     [r8+8], rax
0x14006d219  jnz     loc_14006D3D5
0x14006d21f  mov     rdx, [rax+8]
0x14006d223  cmp     [rdx], rax
0x14006d226  jnz     loc_14006D3D5
0x14006d22c  mov     [rdx], r8
0x14006d22f  mov     [r8+8], rdx
0x14006d233  xor     edx, edx
0x14006d235  mov     [rax], rcx
0x14006d238  mov     [rax+8], rcx
0x14006d23c  mov     rcx, rdi
0x14006d23f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006d246  nop     dword ptr [rax+rax+00h]
0x14006d24b  call    cs:__imp_KeLeaveCriticalRegion
0x14006d252  nop     dword ptr [rax+rax+00h]
0x14006d257  mov     rcx, [rsi+38h]
0x14006d25b  xor     edx, edx
0x14006d25d  add     rcx, 3B0h
0x14006d264  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006d26b  nop     dword ptr [rax+rax+00h]
0x14006d270  call    cs:__imp_KeLeaveCriticalRegion
0x14006d277  nop     dword ptr [rax+rax+00h]
0x14006d27c  mov     rdx, [rsi+58h]; BugCheckParameter2
0x14006d280  test    rdx, rdx
0x14006d283  jnz     loc_14006D59D
0x14006d289  mov     rdx, [rsi+40h]; BugCheckParameter2
0x14006d28d  mov     eax, r15d
0x14006d290  lock xadd [rdx], eax
0x14006d294  dec     eax
0x14006d296  cmp     cs:UxDebugCheckRefcount, 0
0x14006d29d  jnz     loc_14006D69E
0x14006d2a3  test    eax, eax
0x14006d2a5  jz      loc_14006E296
0x14006d2ab  mov     rdi, [rsi+38h]
0x14006d2af  mov     eax, r15d
0x14006d2b2  mov     qword ptr [rsi+40h], 0
0x14006d2ba  lea     rdx, [rdi+28h]; BugCheckParameter2
0x14006d2be  lock xadd [rdx], eax
0x14006d2c2  dec     eax
0x14006d2c4  cmp     cs:UxDebugCheckRefcount, 0
0x14006d2cb  jnz     loc_14006D6BB
0x14006d2d1  test    eax, eax
0x14006d2d3  jz      loc_14006D623
0x14006d2d9  cmp     cs:UxDebugDisableLookaside, 0
0x14006d2e0  mov     qword ptr [rsi+38h], 0
0x14006d2e8  mov     dword ptr [rsi+10h], 75634C75h
0x14006d2ef  jnz     loc_14006E2EE
0x14006d2f5  cmp     cs:UxCompactMode, 0
0x14006d2fc  jnz     loc_14006DB93
0x14006d302  mov     edi, [rsi]
0x14006d304  mov     rcx, cs:qword_1401A0910
0x14006d30b  inc     edi
0x14006d30d  shl     rdi, 7
0x14006d311  add     rdi, rcx
0x14006d314  movzx   eax, byte ptr [rdi+0B0h]
0x14006d31b  test    al, al
0x14006d31d  jz      loc_14006DFCD
0x14006d323  mov     rdx, rsi; Entry
0x14006d326  lea     rcx, [rdi+40h]; Lookaside
0x14006d32a  call    cs:__imp_ExFreeToLookasideListEx
0x14006d331  nop     dword ptr [rax+rax+00h]
0x14006d336  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006d33d  jnz     loc_14006DECB
0x14006d343  call    cs:__imp_KeEnterCriticalRegion
0x14006d34a  nop     dword ptr [rax+rax+00h]
0x14006d34f  lea     rcx, [rsi+48h]
0x14006d353  xor     edx, edx
0x14006d355  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d35c  nop     dword ptr [rax+rax+00h]
0x14006d361  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006d368  jnz     loc_14006E320
0x14006d36e  test    rsi, rsi
0x14006d371  jz      loc_14006E33E
0x14006d377  mov     ecx, [rbx+6C8h]
0x14006d37d  xor     dil, dil
0x14006d380  sub     ecx, 1
0x14006d383  jz      loc_14006E02D
0x14006d389  cmp     ecx, 1
0x14006d38c  jnz     loc_14006D436
0x14006d392  lea     rax, [rbx+6B8h]
0x14006d399  mov     rcx, [rax]
0x14006d39c  cmp     [rcx+8], rax
0x14006d3a0  jnz     short loc_14006D3D5
0x14006d3a2  mov     rdx, [rax+8]
0x14006d3a6  cmp     [rdx], rax
0x14006d3a9  jnz     short loc_14006D3D5
0x14006d3ab  mov     [rdx], rcx
0x14006d3ae  mov     dil, 1
0x14006d3b1  mov     [rcx+8], rdx
0x14006d3b5  xor     ecx, ecx
0x14006d3b7  mov     [rax], rcx
0x14006d3ba  mov     [rax+8], rcx
0x14006d3be  mov     dword ptr [rbx+6C8h], 3
0x14006d3c8  mov     r8, [rsi+78h]
0x14006d3cc  add     rsi, 70h ; 'p'
0x14006d3d0  cmp     [r8], rsi
  ... truncated ...
```
