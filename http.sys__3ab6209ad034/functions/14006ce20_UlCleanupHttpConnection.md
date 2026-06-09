# UlCleanupHttpConnection

- ea: `0x14006ce20`
- end: `0x14006e4e4`
- name: `UlCleanupHttpConnection`
- size: `5828`
- prototype: `__int64 __fastcall(_QWORD)`
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
- `0x140049d08`
- `0x1400517b0`
- `0x14005dfd0`
- `0x14005e030`
- `0x14006cad0`
- `0x14006ce20`
- `0x14006e4ec`
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

- `ntoskrnl!KeGetCurrentIrql` at `0x14006d6c3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006dc2c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006d6c3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006dc2c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006da0a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006dd61`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006da0a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006dd61`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006d30a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006d8d6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006d30a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006d8d6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006d963`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006dcb8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006d963`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006dcb8`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14006d9b9`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14006dd13`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14006d9b9`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14006dd13`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14006e2bd`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14006e37a`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14006e2bd`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14006e37a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006d6ed`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006dc53`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006d6ed`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006dc53`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006d727`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006dc93`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006d727`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006dc93`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14006da83`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14006da83`
- `ntoskrnl!KeSetEvent` at `0x14006da28`
- `ntoskrnl!KeSetEvent` at `0x14006dd7f`
- `ntoskrnl!KeSetEvent` at `0x14006da28`
- `ntoskrnl!KeSetEvent` at `0x14006dd7f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006d98c`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006dce1`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006d98c`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14006dce1`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14006d100`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14006d100`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006db7a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006db7a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14006da66`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14006da66`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14006d45e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14006e0e5`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14006d45e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14006e0e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d01a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d0db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d22b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d250`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d42f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d44c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d471`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006dbc8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e0d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e0f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d01a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d0db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d22b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d250`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d42f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d44c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d471`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006dbc8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e0d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e0f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dba6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dba6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d00e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d0cf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d21f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d244`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d423`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d440`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006dbbc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006e0c7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d00e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d0cf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d21f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d244`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d423`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d440`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006dbbc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006e0c7`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006d607`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006d607`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006cfee`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d098`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d121`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d196`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d1b3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d335`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006cfee`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d098`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d121`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d196`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d1b3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d335`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006cfdc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d087`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d0eb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d110`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d17d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d1a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d323`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006cfdc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d087`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d0eb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d110`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d17d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d1a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d323`

## pseudocode

```c
void __fastcall UlCleanupHttpConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbx
  unsigned __int64 *v6; // r12
  IRP *v7; // rsi
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
  __int64 v89; // [rsp+28h] [rbp-81h]
  __int64 v90; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v91; // [rsp+48h] [rbp-61h] BYREF
  __int128 v92; // [rsp+50h] [rbp-59h] BYREF
  __int128 v93; // [rsp+60h] [rbp-49h] BYREF
  _DWORD v94[24]; // [rsp+70h] [rbp-39h] BYREF

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
  *(_QWORD *)&v93 = v5 + 64;
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
    WPP_SF_q(1032, 95, WPP_ed7456c0382c3120fc23861c64a38256_Traceguids, v5);
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
    v7 = (IRP *)(v9 - 21);
    v42[1] = v8;
    v9[1] = v9;
    *v9 = v9;
    if ( _InterlockedExchange64(v9 - 8, 0) )
    {
      if ( v7->Cancel )
      {
        UlCompleteReceiveEntityBodyIrp(v5, v7, -1073741536);
        v7 = 0;
      }
    }
    else
    {
      v7 = 0;
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 96, WPP_ed7456c0382c3120fc23861c64a38256_Traceguids, v7);
  for ( ; v7; v7 = (IRP *)UlDequeueReceiveEntityBodyIrp(v5) )
    UlCompleteReceiveEntityBodyIrp(v5, v7, -1073741536);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 39, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
  if ( *v6 )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(v5 + 24) + 1096LL);
    if ( *(_BYTE *)(v10 + 79) && Microsoft_Windows_Networking_CorrelationEnabled )
      UlEtwStopActivity(v5 + 72, 3);
    v11 = *v6;
    v91 = -1;
    LODWORD(v90) = 0;
    LODWORD(v92) = 0;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_iqqq(v10, a2, a3, v11, &v90, &v91, &v92);
    v12 = HIDWORD(v11);
    v91 = 0;
    LODWORD(v92) = 0;
    LODWORD(v90) = v12 & 0xFFF;
    if ( (unsigned int)v90 >= UxMaximumNumberOfProcessors )
    {
      if ( (BYTE1(xmmword_1401A2C90) & 2) != 0 )
        WPP_SF_(521, 11, WPP_6218f2abddb13899518e42ce65335ae2_Traceguids);
    }
    else
    {
      a2 = ((unsigned int)v12 >> 12) & 0xFFF;
      v10 = (v12 & 0xFFF) << 6;
      v91 = a2;
      if ( (unsigned int)a2 < *(_DWORD *)((char *)UxOpaqueIdTable + v10 + 40) )
      {
        v13 = 1;
        LODWORD(v92) = BYTE3(v12);
LABEL_23:
        if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
          WPP_SF_lLLL(v10, a2, a3, v13, v90, v91, v92);
        if ( v13 )
        {
          v14 = (__int64 *)(48LL * (unsigned int)v92
                          + *(_QWORD *)(*((_QWORD *)UxOpaqueIdTable + 8 * (unsigned __int64)(unsigned int)v90 + 2)
                                      + 8LL * v91));
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
  v90 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 235, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v5, *v6);
  if ( *(_BYTE *)(v5 + 1852) )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_qqP(1032, 38, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v5, *v6, &v90);
    v90 = 0;
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
      v90 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v20 + 280), 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v5 + 1704, 0);
      if ( *(_DWORD **)(v5 + 1712) == v18 )
        break;
      ExReleasePushLockExclusiveEx(v5 + 1704, 0);
      KeLeaveCriticalRegion();
      ExReleaseCacheAwarePushLockSharedEx(v90, 0);
      v90 = 0;
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
                  memset(v94, 0, sizeof(v94));
                  v94[10] = dword_1401A0928;
                  ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A0938)(v18, v94);
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
                LODWORD(v89) = -1;
                LOBYTE(v49) = 1;
                UlThreadPoolEnqueueWorkItem(0, v32 + 64, UlFreeHttpConnection, v49, CurrentServerSilo, v89);
                v17 = v5 + 1704;
                goto LABEL_53;
              }
              if ( v51 || *(_QWORD *)(v32 + 80) || *(_QWORD *)(v32 + 96) )
                UlBugCheckEx(1u, v32 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
              if ( KeGetCurrentIrql() )
              {
                v77 = 0;
                if ( (unsigned int)dword_1401A3F08 > 1 )
                {
                  v77 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
                  if ( byte_1401A3F20 )
                    v77 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
                }
                if ( CurrentServerSilo == (void *)-1LL )
                  CurrentServerSilo = (void *)PsGetCurrentServerSilo();
                *(_QWORD *)(v47 + 32) = CurrentServerSilo;
                *(_QWORD *)&v92 = 0;
                if ( CurrentServerSilo )
                  ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
                PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v92);
                v78 = v92 + 24;
                v79 = _InterlockedIncrement((volatile signed __int32 *)(v92 + 24));
                if ( UxDebugCheckRefcount && v79 <= -1 )
                  UlBugCheckEx(3u, v78, 0xDu, v79);
                *(_BYTE *)(v47 + 24) = 1;
                v80 = *(_QWORD *)(qword_1401A3F10 + 8LL * v77);
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
                v92 = 0;
                if ( CurrentServerSilo == (void *)-1LL )
                {
                  v76 = *((_QWORD *)&v92 + 1);
LABEL_204:
                  UlFreeHttpConnection(v47);
                  if ( v74 )
                    goto LABEL_205;
                }
                else
                {
                  v75 = PsAttachSiloToCurrentThread(CurrentServerSilo);
                  *(_QWORD *)&v92 = v75;
                  v74 = 1;
                  if ( (BYTE11(xmmword_1401A2CA0) & 0x10) == 0 )
                  {
                    v76 = v75;
                    goto LABEL_204;
                  }
                  WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v75, CurrentServerSilo);
                  UlFreeHttpConnection(v47);
                  v76 = v92;
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
    ExReleaseCacheAwarePushLockSharedEx(v90, 0);
    v90 = 0;
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
    v6 = (unsigned __int64 *)v93;
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
    LODWORD(v89) = -1;
    LOBYTE(a4) = 1;
    UlThreadPoolEnqueueWorkItem(0, v71, UlpFreeHttpRequest, a4, *(_QWORD *)(*(_QWORD *)(v5 + 24) + 1088LL), v89);
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
      v93 = 0;
      if ( v52 == (void *)-1LL )
      {
        v55 = *((_QWORD *)&v93 + 1);
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
    if ( (unsigned int)dword_1401A3F08 > 1 )
    {
      v67 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
      if ( byte_1401A3F20 )
        v67 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
    }
    if ( v52 == (void *)-1LL )
      v52 = (void *)PsGetCurrentServerSilo();
    *(_QWORD *)(v44 + 32) = v52;
    *(_QWORD *)&v93 = 0;
    if ( v52 )
      ObfReferenceObjectWithTag(v52, 0x49576C55u);
    PsGetPermanentSiloContext(v52, (unsigned int)UxPodMonitorSlot, &v93);
    v68 = v93 + 24;
    v69 = _InterlockedIncrement((volatile signed __int32 *)(v93 + 24));
    if ( UxDebugCheckRefcount && v69 <= -1 )
      UlBugCheckEx(3u, v68, 0xDu, v69);
    *(_BYTE *)(v44 + 24) = 1;
    v70 = *(_QWORD *)(qword_1401A3F10 + 8LL * v67);
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
      v93 = 0;
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
        *((_QWORD *)&v93 + 1) = *((_QWORD *)&UlEtwBasePtrActivityGuid + 1);
        *(_QWORD *)&v93 = v56 - 6;
        UlEtwStopActivity(&v93, 2);
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
              v63 = &funcs_140069427;
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
            memset(v94, 0, sizeof(v94));
            v94[10] = *(_DWORD *)v62;
            ((void (__fastcall *)(_DWORD *, _DWORD *))*v63)(v57, v94);
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
0x14006ce20  mov     [rsp-8+arg_10], rbx
0x14006ce25  mov     [rsp-8+arg_18], rsi
0x14006ce2a  push    rbp
0x14006ce2b  push    rdi
0x14006ce2c  push    r12
0x14006ce2e  push    r13
0x14006ce30  push    r14
0x14006ce32  lea     rbp, [rsp-37h]
0x14006ce37  sub     rsp, 0E0h
0x14006ce3e  mov     rax, cs:__security_cookie
0x14006ce45  xor     rax, rsp
0x14006ce48  mov     [rbp+57h+var_30], rax
0x14006ce4c  mov     r14, rcx
0x14006ce4f  xor     r13d, r13d
0x14006ce52  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ce59  jnz     loc_14006E02F
0x14006ce5f  mov     rbx, [r14+238h]
0x14006ce66  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ce6d  jnz     loc_14006E060
0x14006ce73  mov     eax, 40h ; '@'
0x14006ce78  mov     rcx, rbx
0x14006ce7b  lea     r12, [rbx+rax]
0x14006ce7f  mov     qword ptr [rbp+57h+var_A0], r12
0x14006ce83  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006ce8a  jnz     loc_14006E091
0x14006ce90  or      dword ptr [rbx+898h], 200h
0x14006ce9a  test    dword ptr [rbx+898h], 1000h
0x14006cea4  jz      loc_14006DEFA
0x14006ceaa  and     dword ptr [rbx+898h], 0FFFFEFFFh
0x14006ceb4  mov     rsi, r13
0x14006ceb7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006cebe  jnz     loc_14006DE67
0x14006cec4  lea     rdi, [rbx+1F8h]
0x14006cecb  mov     [rsp+100h+arg_8], r15
0x14006ced3  mov     rax, [rdi]
0x14006ced6  cmp     rax, rdi
0x14006ced9  jnz     loc_14006D3BC
0x14006cedf  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006cee6  jnz     loc_14006E169
0x14006ceec  test    rsi, rsi
0x14006ceef  jnz     loc_14006DE40
0x14006cef5  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006cefc  jnz     loc_14006DF36
0x14006cf02  mov     r15d, 0FFFFFFFFh
0x14006cf08  cmp     [r12], r13
0x14006cf0c  jz      loc_14006D04C
0x14006cf12  mov     rax, [rbx+18h]
0x14006cf16  mov     rcx, [rax+448h]
0x14006cf1d  cmp     [rcx+4Fh], r13b
0x14006cf21  jz      short loc_14006CF31
0x14006cf23  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14006cf29  test    eax, eax
0x14006cf2b  jnz     loc_14006E187
0x14006cf31  mov     rdi, [r12]
0x14006cf35  mov     [rbp+57h+var_B8], 0FFFFFFFFh
0x14006cf3c  mov     dword ptr [rbp+57h+var_C0], r13d
0x14006cf40  mov     dword ptr [rbp+57h+var_B0], r13d
0x14006cf44  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14006cf4b  jnz     loc_14006E19A
0x14006cf51  shr     rdi, 20h
0x14006cf55  mov     eax, edi
0x14006cf57  mov     [rbp+57h+var_B8], r13d
0x14006cf5b  and     eax, 0FFFh
0x14006cf60  mov     dword ptr [rbp+57h+var_B0], r13d
0x14006cf64  cmp     eax, cs:UxMaximumNumberOfProcessors
0x14006cf6a  mov     dword ptr [rbp+57h+var_C0], eax
0x14006cf6d  jnb     loc_14006DE21
0x14006cf73  mov     ecx, eax
0x14006cf75  mov     edx, edi
0x14006cf77  mov     rax, cs:UxOpaqueIdTable
0x14006cf7e  shr     edx, 0Ch
0x14006cf81  and     edx, 0FFFh
0x14006cf87  shl     rcx, 6
0x14006cf8b  mov     [rbp+57h+var_B8], edx
0x14006cf8e  cmp     edx, [rcx+rax+28h]
0x14006cf92  jnb     loc_14006E1DD
0x14006cf98  shr     edi, 18h
0x14006cf9b  mov     sil, 1
0x14006cf9e  mov     dword ptr [rbp+57h+var_B0], edi
0x14006cfa1  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14006cfa8  jnz     loc_14006E208
0x14006cfae  test    sil, sil
0x14006cfb1  jz      short loc_14006D026
0x14006cfb3  mov     rax, cs:UxOpaqueIdTable
0x14006cfba  mov     ecx, dword ptr [rbp+57h+var_C0]
0x14006cfbd  mov     r8d, [rbp+57h+var_B8]
0x14006cfc1  shl     rcx, 6
0x14006cfc5  mov     rdx, [rcx+rax+10h]
0x14006cfca  mov     eax, dword ptr [rbp+57h+var_B0]
0x14006cfcd  mov     rdi, [rdx+r8*8]
0x14006cfd1  lea     rcx, [rax+rax*2]
0x14006cfd5  shl     rcx, 4
0x14006cfd9  add     rdi, rcx
0x14006cfdc  call    cs:__imp_KeEnterCriticalRegion
0x14006cfe3  nop     dword ptr [rax+rax+00h]
0x14006cfe8  xor     edx, edx
0x14006cfea  lea     rcx, [rdi+20h]
0x14006cfee  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006cff5  nop     dword ptr [rax+rax+00h]
0x14006cffa  mov     rax, [rdi]
0x14006cffd  lea     rcx, [rdi+20h]
0x14006d001  xor     edx, edx
0x14006d003  and     dword ptr [rax+20h], 0FFFFFFFh
0x14006d00a  mov     [rax+18h], r13
0x14006d00e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006d015  nop     dword ptr [rax+rax+00h]
0x14006d01a  call    cs:__imp_KeLeaveCriticalRegion
0x14006d021  nop     dword ptr [rax+rax+00h]
0x14006d026  mov     [r12], r13
0x14006d02a  lea     rdx, [rbx+30h]; BugCheckParameter2
0x14006d02e  mov     eax, r15d
0x14006d031  lock xadd [rdx], eax
0x14006d035  dec     eax
0x14006d037  cmp     cs:UxDebugCheckRefcount, r13b
0x14006d03e  jnz     loc_14006D5E6
0x14006d044  test    eax, eax
0x14006d046  jz      loc_14006E22B
0x14006d04c  mov     [rbp+57h+var_C0], r13
0x14006d050  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006d057  jnz     loc_14006DC05
0x14006d05d  mov     edi, 1
0x14006d062  cmp     [rbx+73Ch], r13b
0x14006d069  jz      loc_14006D48A
0x14006d06f  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14006d076  jnz     loc_14006E238
0x14006d07c  mov     [rbp+57h+var_C0], r13
0x14006d080  lea     r13, [rbx+6A8h]
0x14006d087  call    cs:__imp_KeEnterCriticalRegion
0x14006d08e  nop     dword ptr [rax+rax+00h]
0x14006d093  xor     edx, edx
0x14006d095  mov     rcx, r13
0x14006d098  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d09f  nop     dword ptr [rax+rax+00h]
0x14006d0a4  mov     rsi, [rbx+6B0h]
0x14006d0ab  test    rsi, rsi
0x14006d0ae  jz      loc_14006DBB7
0x14006d0b4  mov     eax, edi
0x14006d0b6  lock xadd [rsi+14h], eax
0x14006d0bb  inc     eax
0x14006d0bd  cmp     cs:UxDebugCheckRefcount, 0
0x14006d0c4  jnz     loc_14006D5A8
0x14006d0ca  xor     edx, edx
0x14006d0cc  mov     rcx, r13
0x14006d0cf  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006d0d6  nop     dword ptr [rax+rax+00h]
0x14006d0db  call    cs:__imp_KeLeaveCriticalRegion
0x14006d0e2  nop     dword ptr [rax+rax+00h]
0x14006d0e7  mov     rdi, [rsi+40h]
0x14006d0eb  call    cs:__imp_KeEnterCriticalRegion
0x14006d0f2  nop     dword ptr [rax+rax+00h]
0x14006d0f7  mov     rcx, [rdi+118h]
0x14006d0fe  xor     edx, edx
0x14006d100  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14006d107  nop     dword ptr [rax+rax+00h]
0x14006d10c  mov     [rbp+57h+var_C0], rax
0x14006d110  call    cs:__imp_KeEnterCriticalRegion
0x14006d117  nop     dword ptr [rax+rax+00h]
0x14006d11c  xor     edx, edx
0x14006d11e  mov     rcx, r13
0x14006d121  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d128  nop     dword ptr [rax+rax+00h]
0x14006d12d  cmp     [rbx+6B0h], rsi
0x14006d134  jnz     loc_14006E0C2
0x14006d13a  mov     eax, r15d
0x14006d13d  lock xadd [rsi+14h], eax
0x14006d142  dec     eax
0x14006d144  cmp     cs:UxDebugCheckRefcount, 0
0x14006d14b  jnz     loc_14006D65D
0x14006d151  test    eax, eax
0x14006d153  jnz     loc_14006D323
0x14006d159  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006d160  jnz     loc_14006DE85
0x14006d166  mov     rax, [rsi+38h]
0x14006d16a  movzx   edx, word ptr [rax+38h]
0x14006d16e  mov     rax, [rsi+40h]
0x14006d172  mov     rcx, [rax+108h]
0x14006d179  mov     rdi, [rcx+rdx*8]
0x14006d17d  call    cs:__imp_KeEnterCriticalRegion
0x14006d184  nop     dword ptr [rax+rax+00h]
0x14006d189  mov     rcx, [rsi+38h]
0x14006d18d  xor     edx, edx
0x14006d18f  add     rcx, 3B0h
0x14006d196  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d19d  nop     dword ptr [rax+rax+00h]
0x14006d1a2  call    cs:__imp_KeEnterCriticalRegion
0x14006d1a9  nop     dword ptr [rax+rax+00h]
0x14006d1ae  xor     edx, edx
0x14006d1b0  mov     rcx, rdi
0x14006d1b3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d1ba  nop     dword ptr [rax+rax+00h]
0x14006d1bf  mov     rdx, [rsi+18h]
0x14006d1c3  lea     rax, [rsi+18h]
0x14006d1c7  cmp     [rdx+8], rax
0x14006d1cb  jnz     loc_14006D3B5
0x14006d1d1  mov     rcx, [rax+8]
0x14006d1d5  cmp     [rcx], rax
0x14006d1d8  jnz     loc_14006D3B5
0x14006d1de  mov     [rcx], rdx
0x14006d1e1  mov     [rdx+8], rcx
0x14006d1e5  xor     ecx, ecx
0x14006d1e7  mov     [rax], rcx
0x14006d1ea  mov     [rax+8], rcx
0x14006d1ee  lea     rax, [rsi+28h]
0x14006d1f2  mov     r8, [rax]
0x14006d1f5  cmp     [r8+8], rax
0x14006d1f9  jnz     loc_14006D3B5
0x14006d1ff  mov     rdx, [rax+8]
0x14006d203  cmp     [rdx], rax
0x14006d206  jnz     loc_14006D3B5
0x14006d20c  mov     [rdx], r8
0x14006d20f  mov     [r8+8], rdx
0x14006d213  xor     edx, edx
0x14006d215  mov     [rax], rcx
0x14006d218  mov     [rax+8], rcx
0x14006d21c  mov     rcx, rdi
0x14006d21f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006d226  nop     dword ptr [rax+rax+00h]
0x14006d22b  call    cs:__imp_KeLeaveCriticalRegion
0x14006d232  nop     dword ptr [rax+rax+00h]
0x14006d237  mov     rcx, [rsi+38h]
0x14006d23b  xor     edx, edx
0x14006d23d  add     rcx, 3B0h
0x14006d244  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006d24b  nop     dword ptr [rax+rax+00h]
0x14006d250  call    cs:__imp_KeLeaveCriticalRegion
0x14006d257  nop     dword ptr [rax+rax+00h]
0x14006d25c  mov     rdx, [rsi+58h]; BugCheckParameter2
0x14006d260  test    rdx, rdx
0x14006d263  jnz     loc_14006D57D
0x14006d269  mov     rdx, [rsi+40h]; BugCheckParameter2
0x14006d26d  mov     eax, r15d
0x14006d270  lock xadd [rdx], eax
0x14006d274  dec     eax
0x14006d276  cmp     cs:UxDebugCheckRefcount, 0
0x14006d27d  jnz     loc_14006D67E
0x14006d283  test    eax, eax
0x14006d285  jz      loc_14006E276
0x14006d28b  mov     rdi, [rsi+38h]
0x14006d28f  mov     eax, r15d
0x14006d292  mov     qword ptr [rsi+40h], 0
0x14006d29a  lea     rdx, [rdi+28h]; BugCheckParameter2
0x14006d29e  lock xadd [rdx], eax
0x14006d2a2  dec     eax
0x14006d2a4  cmp     cs:UxDebugCheckRefcount, 0
0x14006d2ab  jnz     loc_14006D69B
0x14006d2b1  test    eax, eax
0x14006d2b3  jz      loc_14006D603
0x14006d2b9  cmp     cs:UxDebugDisableLookaside, 0
0x14006d2c0  mov     qword ptr [rsi+38h], 0
0x14006d2c8  mov     dword ptr [rsi+10h], 75634C75h
0x14006d2cf  jnz     loc_14006E2CE
0x14006d2d5  cmp     cs:UxCompactMode, 0
0x14006d2dc  jnz     loc_14006DB73
0x14006d2e2  mov     edi, [rsi]
0x14006d2e4  mov     rcx, cs:qword_1401A0910
0x14006d2eb  inc     edi
0x14006d2ed  shl     rdi, 7
0x14006d2f1  add     rdi, rcx
0x14006d2f4  movzx   eax, byte ptr [rdi+0B0h]
0x14006d2fb  test    al, al
0x14006d2fd  jz      loc_14006DFAD
0x14006d303  mov     rdx, rsi; Entry
0x14006d306  lea     rcx, [rdi+40h]; Lookaside
0x14006d30a  call    cs:__imp_ExFreeToLookasideListEx
0x14006d311  nop     dword ptr [rax+rax+00h]
0x14006d316  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006d31d  jnz     loc_14006DEAB
0x14006d323  call    cs:__imp_KeEnterCriticalRegion
0x14006d32a  nop     dword ptr [rax+rax+00h]
0x14006d32f  lea     rcx, [rsi+48h]
0x14006d333  xor     edx, edx
0x14006d335  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006d33c  nop     dword ptr [rax+rax+00h]
0x14006d341  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14006d348  jnz     loc_14006E300
0x14006d34e  test    rsi, rsi
0x14006d351  jz      loc_14006E31E
0x14006d357  mov     ecx, [rbx+6C8h]
0x14006d35d  xor     dil, dil
0x14006d360  sub     ecx, 1
0x14006d363  jz      loc_14006E00D
0x14006d369  cmp     ecx, 1
0x14006d36c  jnz     loc_14006D416
0x14006d372  lea     rax, [rbx+6B8h]
0x14006d379  mov     rcx, [rax]
0x14006d37c  cmp     [rcx+8], rax
0x14006d380  jnz     short loc_14006D3B5
0x14006d382  mov     rdx, [rax+8]
0x14006d386  cmp     [rdx], rax
0x14006d389  jnz     short loc_14006D3B5
0x14006d38b  mov     [rdx], rcx
0x14006d38e  mov     dil, 1
0x14006d391  mov     [rcx+8], rdx
0x14006d395  xor     ecx, ecx
0x14006d397  mov     [rax], rcx
0x14006d39a  mov     [rax+8], rcx
0x14006d39e  mov     dword ptr [rbx+6C8h], 3
0x14006d3a8  mov     r8, [rsi+78h]
0x14006d3ac  add     rsi, 70h ; 'p'
0x14006d3b0  cmp     [r8], rsi
  ... truncated ...
```
