# UlUnlinkRequestFromRequestQueue

- ea: `0x14005f3a0`
- end: `0x14005fe22`
- name: `UlUnlinkRequestFromRequestQueue`
- size: `2690`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400b0db4`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x14000e420`
- `0x140022610`
- `0x140049d08`
- `0x14005dfd0`
- `0x14005e030`
- `0x14005f3a0`
- `0x1400705d0`
- `0x14009620c`
- `0x1400a031c`
- `0x1400cfba8`
- `0x14013dd68`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9c5c`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005fa17`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005fa17`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005fb41`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005fb41`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005f6bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005f6bb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005fa9a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005fa9a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005faf7`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005faf7`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005fda3`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005fda3`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005fa3f`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005fa3f`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005fa7b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005fa7b`
- `ntoskrnl!KeSetEvent` at `0x14005fb5f`
- `ntoskrnl!KeSetEvent` at `0x14005fb5f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005fac4`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005fac4`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14005f4ba`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14005f4ba`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005f9a6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005f9a6`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005f7c5`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005fcb8`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005f7c5`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005fcb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f495`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f5e4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f609`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f795`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f9d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005fca5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005fcc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f495`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f5e4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f609`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f795`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f9d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005fca5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005fcc9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f489`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f5d8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f5fd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f789`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f7a6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f9cb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005fc99`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f489`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f5d8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f5fd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f789`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f7a6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f9cb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005fc99`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005f8b7`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005f8b7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f451`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f4dc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f551`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f56e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f6e6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f451`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f4dc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f551`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f56e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f6e6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f440`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f4a5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f4cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f538`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f55d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f6d4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f440`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f4a5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f4cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f538`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f55d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f6d4`

## pseudocode

```c
void __fastcall UlUnlinkRequestFromRequestQueue(__int64 a1)
{
  ULONG v1; // r13d
  _DWORD *v3; // rbx
  int v4; // eax
  __int64 v5; // rdi
  int v6; // eax
  __int64 v7; // rdi
  __int64 v8; // rdx
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  volatile signed __int32 *v14; // rdx
  volatile signed __int32 *v15; // rdx
  int v16; // eax
  __int64 v17; // rdi
  int v18; // eax
  bool v19; // zf
  unsigned __int64 v20; // rdi
  char v21; // di
  _QWORD *v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rdx
  _QWORD *v25; // rcx
  _DWORD *v26; // rbx
  int v27; // r14d
  int v28; // eax
  ULONG_PTR v29; // rbp
  struct _KPROCESS *CurrentProcess; // rax
  void *CurrentServerSilo; // rdi
  __int64 v32; // rcx
  __int64 v33; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v35; // rax
  char v36; // r12
  __int64 v37; // rax
  __int64 v38; // r13
  ULONG_PTR v39; // rdx
  int v40; // r12d
  __int64 v41; // rdi
  char v42; // al
  int v43; // eax
  __int64 v44; // [rsp+28h] [rbp-C0h]
  __int64 v45; // [rsp+30h] [rbp-B8h] BYREF
  __int128 v46; // [rsp+38h] [rbp-B0h] BYREF
  _DWORD v47[24]; // [rsp+50h] [rbp-98h] BYREF

  v1 = 0;
  v45 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a1 )
      v35 = *(_QWORD *)(a1 + 64);
    else
      v35 = 0;
    WPP_SF_qq(1032, 235, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, v35);
  }
  if ( *(_BYTE *)(a1 + 1852) )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_qqP(1032, 38, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, *(_QWORD *)(a1 + 64), &v45);
    v45 = 0;
    while ( 1 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(a1 + 1704, 0);
      v3 = *(_DWORD **)(a1 + 1712);
      if ( !v3 )
      {
        ExReleasePushLockExclusiveEx(a1 + 1704, 0);
        KeLeaveCriticalRegion();
        goto LABEL_31;
      }
      v4 = _InterlockedIncrement(v3 + 5);
      if ( UxDebugCheckRefcount && v4 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v3 + 5), 0x21u, v4);
      ExReleasePushLockExclusiveEx(a1 + 1704, 0);
      KeLeaveCriticalRegion();
      v5 = *((_QWORD *)v3 + 8);
      KeEnterCriticalRegion();
      v45 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v5 + 280), 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(a1 + 1704, 0);
      if ( *(_DWORD **)(a1 + 1712) == v3 )
        break;
      ExReleasePushLockExclusiveEx(a1 + 1704, 0);
      KeLeaveCriticalRegion();
      ExReleaseCacheAwarePushLockSharedEx(v45, 0);
      v45 = 0;
      KeLeaveCriticalRegion();
      v43 = _InterlockedDecrement(v3 + 5);
      if ( UxDebugCheckRefcount && v43 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v3 + 5), 0x21u, v43);
      if ( !v43 )
        UlpFreeCoupling(v3);
    }
    v6 = _InterlockedDecrement(v3 + 5);
    if ( UxDebugCheckRefcount && v6 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v3 + 5), 0x21u, v6);
    if ( !v6 )
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v3, 0);
      v7 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 8) + 264LL) + 8LL
                                                                * *(unsigned __int16 *)(*((_QWORD *)v3 + 7) + 56LL));
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(*((_QWORD *)v3 + 7) + 944LL, 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v7, 0);
      v8 = *((_QWORD *)v3 + 3);
      v9 = v3 + 6;
      if ( *(_DWORD **)(v8 + 8) == v3 + 6 )
      {
        v10 = (_QWORD *)*((_QWORD *)v3 + 4);
        if ( (_QWORD *)*v10 == v9 )
        {
          *v10 = v8;
          *(_QWORD *)(v8 + 8) = v10;
          *v9 = 0;
          *((_QWORD *)v3 + 4) = 0;
          v11 = v3 + 10;
          v12 = *((_QWORD *)v3 + 5);
          if ( *(_DWORD **)(v12 + 8) == v3 + 10 )
          {
            v13 = (_QWORD *)*((_QWORD *)v3 + 6);
            if ( (_QWORD *)*v13 == v11 )
            {
              *v13 = v12;
              *(_QWORD *)(v12 + 8) = v13;
              *v11 = 0;
              *((_QWORD *)v3 + 6) = 0;
              ExReleasePushLockExclusiveEx(v7, 0);
              KeLeaveCriticalRegion();
              ExReleasePushLockExclusiveEx(*((_QWORD *)v3 + 7) + 944LL, 0);
              KeLeaveCriticalRegion();
              v14 = (volatile signed __int32 *)*((_QWORD *)v3 + 11);
              if ( v14 )
              {
                v28 = _InterlockedDecrement(v14);
                if ( UxDebugCheckRefcount && v28 <= -1 )
                  UlBugCheckEx(3u, (ULONG_PTR)v14, 0xEu, v28);
                if ( !v28 )
                  UlConsumerCleanupCompletion(*((_QWORD *)v3 + 11));
                *((_QWORD *)v3 + 11) = 0;
              }
              v15 = (volatile signed __int32 *)*((_QWORD *)v3 + 8);
              v16 = _InterlockedDecrement(v15);
              if ( UxDebugCheckRefcount && v16 <= -1 )
                UlBugCheckEx(3u, (ULONG_PTR)v15, 0xEu, v16);
              if ( !v16 )
                UlFreeRequestQueue(*((PVOID *)v3 + 8));
              v17 = *((_QWORD *)v3 + 7);
              *((_QWORD *)v3 + 8) = 0;
              v18 = _InterlockedDecrement((volatile signed __int32 *)(v17 + 40));
              if ( UxDebugCheckRefcount && v18 <= -1 )
                UlBugCheckEx(3u, v17 + 40, 0xEu, v18);
              if ( v18 )
              {
LABEL_23:
                v19 = UxDebugDisableLookaside == 0;
                *((_QWORD *)v3 + 7) = 0;
                v3[4] = 1969441909;
                if ( v19 )
                {
                  if ( UxCompactMode )
                  {
                    v33 = qword_1401A0910;
                    CurrentNodeNumber = KeGetCurrentNodeNumber();
                    PplFreeToLookasideListProcessor(v33, v3, CurrentNodeNumber);
                  }
                  else
                  {
                    v20 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*v3 + 1) << 7);
                    if ( !*(_BYTE *)(v20 + 176) )
                      PplpLazyInitializeLookasideList(qword_1401A0910, v20 + 64);
                    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v20 + 64), v3);
                  }
                }
                else
                {
                  memset(v47, 0, sizeof(v47));
                  v47[10] = dword_1401A0928;
                  ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A0938)(v3, v47);
                }
                if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
                  WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
                goto LABEL_30;
              }
              v29 = v17 + 64;
              CurrentProcess = IoGetCurrentProcess();
              CurrentServerSilo = *(void **)(v17 + 1088);
              v32 = *(_QWORD *)v29;
              if ( UxSystemProcess != CurrentProcess )
              {
                if ( v32 || *(_QWORD *)(v29 + 16) || *(_QWORD *)(v29 + 32) )
                  UlBugCheckEx(1u, v29, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
                LODWORD(v44) = -1;
                UlThreadPoolEnqueueWorkItem(0, v29, UlFreeHttpConnection, 1, CurrentServerSilo, v44);
                goto LABEL_23;
              }
              if ( v32 || *(_QWORD *)(v29 + 16) || *(_QWORD *)(v29 + 32) )
                UlBugCheckEx(1u, v29, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
              if ( KeGetCurrentIrql() )
              {
                if ( (unsigned int)dword_1401A3F08 > 1 )
                {
                  v1 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
                  if ( byte_1401A3F20 )
                    v1 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
                }
                if ( CurrentServerSilo == (void *)-1LL )
                  CurrentServerSilo = (void *)PsGetCurrentServerSilo();
                *(_QWORD *)(v29 + 32) = CurrentServerSilo;
                *(_QWORD *)&v46 = 0;
                if ( CurrentServerSilo )
                  ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
                PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v46);
                v39 = v46 + 24;
                v40 = _InterlockedIncrement((volatile signed __int32 *)(v46 + 24));
                if ( UxDebugCheckRefcount && v40 <= -1 )
                  UlBugCheckEx(3u, v39, 0xDu, v40);
                *(_BYTE *)(v29 + 24) = 1;
                v41 = *(_QWORD *)(qword_1401A3F10 + 8LL * v1);
                *(_QWORD *)(v29 + 16) = UlFreeHttpConnection;
                if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v41 + 16), (PSLIST_ENTRY)v29) )
                {
                  KeSetEvent((PRKEVENT)(v41 + 32), 0, 0);
                  UlpActivateThreadPoolQueue((PVOID)v41);
                }
                goto LABEL_23;
              }
              v36 = 0;
              v46 = 0;
              if ( CurrentServerSilo != (void *)-1LL )
              {
                v37 = PsAttachSiloToCurrentThread(CurrentServerSilo);
                v38 = v37;
                v36 = 1;
                if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
                {
                  WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v37, CurrentServerSilo);
                  UlFreeHttpConnection(v29);
                }
                else
                {
LABEL_78:
                  UlFreeHttpConnection(v29);
                  if ( !v36 )
                    goto LABEL_23;
                }
                if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
                  WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v38);
                PsDetachSiloFromCurrentThread(v38);
                goto LABEL_23;
              }
              v38 = *((_QWORD *)&v46 + 1);
              goto LABEL_78;
            }
          }
        }
      }
LABEL_40:
      __fastfail(3u);
    }
LABEL_30:
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v3 + 18, 0);
LABEL_31:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_q(1032, 39, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v3);
    if ( v3 )
    {
      v21 = 0;
      if ( *(_DWORD *)(a1 + 1736) == 1 )
      {
        v42 = UlpRemoveRequestFromLane(a1);
        *(_DWORD *)(a1 + 1736) = 3;
        v21 = v42;
        if ( v42 )
        {
LABEL_39:
          v25 = (_QWORD *)*((_QWORD *)v3 + 15);
          v26 = v3 + 28;
          if ( (_DWORD *)*v25 != v26 )
            goto LABEL_40;
          *(_QWORD *)(a1 + 1816) = v26;
          *(_QWORD *)(a1 + 1824) = v25;
          *v25 = a1 + 1816;
          *((_QWORD *)v26 + 1) = a1 + 1816;
        }
      }
      else if ( *(_DWORD *)(a1 + 1736) == 2 )
      {
        v22 = (_QWORD *)(a1 + 1720);
        v23 = *(_QWORD *)(a1 + 1720);
        if ( *(_QWORD *)(v23 + 8) != a1 + 1720 )
          goto LABEL_40;
        v24 = *(_QWORD **)(a1 + 1728);
        if ( (_QWORD *)*v24 != v22 )
          goto LABEL_40;
        *v24 = v23;
        v21 = 1;
        *(_QWORD *)(v23 + 8) = v24;
        *v22 = 0;
        *(_QWORD *)(a1 + 1728) = 0;
        *(_DWORD *)(a1 + 1736) = 3;
        goto LABEL_39;
      }
      ExReleasePushLockExclusiveEx(*(_QWORD *)(a1 + 1712) + 72LL, 0);
      KeLeaveCriticalRegion();
      ExReleasePushLockExclusiveEx(a1 + 1704, 0);
      KeLeaveCriticalRegion();
      ExReleaseCacheAwarePushLockSharedEx(v45, 0);
      v45 = 0;
      KeLeaveCriticalRegion();
      if ( v21 )
      {
        v27 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 48));
        if ( UxDebugCheckRefcount && v27 <= -1 )
          UlBugCheckEx(3u, a1 + 48, 0xCu, v27);
        if ( !v27 )
          UlpQueueFreeHttpRequest(a1);
      }
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 236, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
}

```

## disassembly

```asm
0x14005f3a0  push    rsi
0x14005f3a2  push    r13
0x14005f3a4  sub     rsp, 0D8h
0x14005f3ab  mov     rax, cs:__security_cookie
0x14005f3b2  xor     rax, rsp
0x14005f3b5  mov     [rsp+0E8h+var_38], rax
0x14005f3bd  xor     r13d, r13d
0x14005f3c0  mov     rsi, rcx
0x14005f3c3  mov     [rsp+0E8h+var_B8], r13
0x14005f3c8  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005f3cf  jnz     loc_14005F9E8
0x14005f3d5  mov     r8d, 40h ; '@'
0x14005f3db  mov     [rsp+0E8h+arg_8], rbx
0x14005f3e3  mov     r9, rsi
0x14005f3e6  mov     [rsp+0E8h+arg_10], rbp
0x14005f3ee  mov     [rsp+0E8h+arg_18], rdi
0x14005f3f6  mov     [rsp+0E8h+var_18], r12
0x14005f3fe  mov     [rsp+0E8h+var_20], r14
0x14005f406  mov     [rsp+0E8h+var_28], r15
0x14005f40e  cmp     [rsi+73Ch], r13b
0x14005f415  jz      loc_14005F7E7
0x14005f41b  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005f422  jnz     loc_14005FD1C
0x14005f428  mov     [rsp+0E8h+var_B8], r13
0x14005f42d  lea     r15, [rsi+6A8h]
0x14005f434  mov     r12d, 1
0x14005f43a  mov     r14d, 0FFFFFFFFh
0x14005f440  call    cs:__imp_KeEnterCriticalRegion
0x14005f447  nop     dword ptr [rax+rax+00h]
0x14005f44c  xor     edx, edx
0x14005f44e  mov     rcx, r15
0x14005f451  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005f458  nop     dword ptr [rax+rax+00h]
0x14005f45d  mov     rbx, [rsi+6B0h]
0x14005f464  test    rbx, rbx
0x14005f467  jz      loc_14005F9C6
0x14005f46d  mov     eax, r12d
0x14005f470  lock xadd [rbx+14h], eax
0x14005f475  inc     eax
0x14005f477  cmp     cs:UxDebugCheckRefcount, r13b
0x14005f47e  jnz     loc_14005F892
0x14005f484  xor     edx, edx
0x14005f486  mov     rcx, r15
0x14005f489  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005f490  nop     dword ptr [rax+rax+00h]
0x14005f495  call    cs:__imp_KeLeaveCriticalRegion
0x14005f49c  nop     dword ptr [rax+rax+00h]
0x14005f4a1  mov     rdi, [rbx+40h]
0x14005f4a5  call    cs:__imp_KeEnterCriticalRegion
0x14005f4ac  nop     dword ptr [rax+rax+00h]
0x14005f4b1  mov     rcx, [rdi+118h]
0x14005f4b8  xor     edx, edx
0x14005f4ba  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14005f4c1  nop     dword ptr [rax+rax+00h]
0x14005f4c6  mov     [rsp+0E8h+var_B8], rax
0x14005f4cb  call    cs:__imp_KeEnterCriticalRegion
0x14005f4d2  nop     dword ptr [rax+rax+00h]
0x14005f4d7  xor     edx, edx
0x14005f4d9  mov     rcx, r15
0x14005f4dc  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005f4e3  nop     dword ptr [rax+rax+00h]
0x14005f4e8  cmp     [rsi+6B0h], rbx
0x14005f4ef  jnz     loc_14005FC94
0x14005f4f5  mov     eax, r14d
0x14005f4f8  lock xadd [rbx+14h], eax
0x14005f4fd  dec     eax
0x14005f4ff  cmp     cs:UxDebugCheckRefcount, r13b
0x14005f506  jnz     loc_14005F909
0x14005f50c  test    eax, eax
0x14005f50e  jnz     loc_14005F6D4
0x14005f514  test    byte ptr cs:xmmword_1401A2CA0+1, r12b
0x14005f51b  jnz     loc_14005FBD1
0x14005f521  mov     rax, [rbx+38h]
0x14005f525  movzx   edx, word ptr [rax+38h]
0x14005f529  mov     rax, [rbx+40h]
0x14005f52d  mov     rcx, [rax+108h]
0x14005f534  mov     rdi, [rcx+rdx*8]
0x14005f538  call    cs:__imp_KeEnterCriticalRegion
0x14005f53f  nop     dword ptr [rax+rax+00h]
0x14005f544  mov     rcx, [rbx+38h]
0x14005f548  xor     edx, edx
0x14005f54a  add     rcx, 3B0h
0x14005f551  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005f558  nop     dword ptr [rax+rax+00h]
0x14005f55d  call    cs:__imp_KeEnterCriticalRegion
0x14005f564  nop     dword ptr [rax+rax+00h]
0x14005f569  xor     edx, edx
0x14005f56b  mov     rcx, rdi
0x14005f56e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005f575  nop     dword ptr [rax+rax+00h]
0x14005f57a  mov     rdx, [rbx+18h]
0x14005f57e  lea     rax, [rbx+18h]
0x14005f582  cmp     [rdx+8], rax
0x14005f586  jnz     loc_14005F760
0x14005f58c  mov     rcx, [rax+8]
0x14005f590  cmp     [rcx], rax
0x14005f593  jnz     loc_14005F760
0x14005f599  mov     [rcx], rdx
0x14005f59c  mov     [rdx+8], rcx
0x14005f5a0  mov     [rax], r13
0x14005f5a3  mov     [rax+8], r13
0x14005f5a7  lea     rax, [rbx+28h]
0x14005f5ab  mov     rdx, [rax]
0x14005f5ae  cmp     [rdx+8], rax
0x14005f5b2  jnz     loc_14005F760
0x14005f5b8  mov     rcx, [rax+8]
0x14005f5bc  cmp     [rcx], rax
0x14005f5bf  jnz     loc_14005F760
0x14005f5c5  mov     [rcx], rdx
0x14005f5c8  mov     [rdx+8], rcx
0x14005f5cc  xor     edx, edx
0x14005f5ce  mov     rcx, rdi
0x14005f5d1  mov     [rax], r13
0x14005f5d4  mov     [rax+8], r13
0x14005f5d8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005f5df  nop     dword ptr [rax+rax+00h]
0x14005f5e4  call    cs:__imp_KeLeaveCriticalRegion
0x14005f5eb  nop     dword ptr [rax+rax+00h]
0x14005f5f0  mov     rcx, [rbx+38h]
0x14005f5f4  xor     edx, edx
0x14005f5f6  add     rcx, 3B0h
0x14005f5fd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005f604  nop     dword ptr [rax+rax+00h]
0x14005f609  call    cs:__imp_KeLeaveCriticalRegion
0x14005f610  nop     dword ptr [rax+rax+00h]
0x14005f615  mov     rdx, [rbx+58h]; BugCheckParameter2
0x14005f619  test    rdx, rdx
0x14005f61c  jnz     loc_14005F86B
0x14005f622  mov     rdx, [rbx+40h]; BugCheckParameter2
0x14005f626  mov     eax, r14d
0x14005f629  lock xadd [rdx], eax
0x14005f62d  dec     eax
0x14005f62f  cmp     cs:UxDebugCheckRefcount, r13b
0x14005f636  jnz     loc_14005F92A
0x14005f63c  test    eax, eax
0x14005f63e  jz      loc_14005FD5B
0x14005f644  mov     rdi, [rbx+38h]
0x14005f648  mov     eax, r14d
0x14005f64b  mov     [rbx+40h], r13
0x14005f64f  lea     rdx, [rdi+28h]; BugCheckParameter2
0x14005f653  lock xadd [rdx], eax
0x14005f657  dec     eax
0x14005f659  cmp     cs:UxDebugCheckRefcount, r13b
0x14005f660  jnz     loc_14005F947
0x14005f666  test    eax, eax
0x14005f668  jz      loc_14005F8B3
0x14005f66e  cmp     cs:UxDebugDisableLookaside, 0
0x14005f675  mov     [rbx+38h], r13
0x14005f679  mov     dword ptr [rbx+10h], 75634C75h
0x14005f680  jnz     loc_14005FDB4
0x14005f686  cmp     cs:UxCompactMode, 0
0x14005f68d  jnz     loc_14005F99F
0x14005f693  mov     edi, [rbx]
0x14005f695  mov     r8, cs:qword_1401A0910
0x14005f69c  inc     edi
0x14005f69e  shl     rdi, 7
0x14005f6a2  add     rdi, r8
0x14005f6a5  movzx   eax, byte ptr [rdi+0B0h]
0x14005f6ac  test    al, al
0x14005f6ae  jz      loc_14005FC0F
0x14005f6b4  mov     rdx, rbx; Entry
0x14005f6b7  lea     rcx, [rdi+40h]; Lookaside
0x14005f6bb  call    cs:__imp_ExFreeToLookasideListEx
0x14005f6c2  nop     dword ptr [rax+rax+00h]
0x14005f6c7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005f6ce  jnz     loc_14005FBF4
0x14005f6d4  call    cs:__imp_KeEnterCriticalRegion
0x14005f6db  nop     dword ptr [rax+rax+00h]
0x14005f6e0  lea     rcx, [rbx+48h]
0x14005f6e4  xor     edx, edx
0x14005f6e6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005f6ed  nop     dword ptr [rax+rax+00h]
0x14005f6f2  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005f6f9  jnz     loc_14005FDE9
0x14005f6ff  test    rbx, rbx
0x14005f702  jz      loc_14005F7E7
0x14005f708  mov     ecx, [rsi+6C8h]
0x14005f70e  xor     dil, dil
0x14005f711  sub     ecx, 1
0x14005f714  jz      loc_14005FC72
0x14005f71a  cmp     ecx, 1
0x14005f71d  jnz     short loc_14005F77C
0x14005f71f  lea     rax, [rsi+6B8h]
0x14005f726  mov     rcx, [rax]
0x14005f729  cmp     [rcx+8], rax
0x14005f72d  jnz     short loc_14005F760
0x14005f72f  mov     rdx, [rax+8]
0x14005f733  cmp     [rdx], rax
0x14005f736  jnz     short loc_14005F760
0x14005f738  mov     [rdx], rcx
0x14005f73b  mov     dil, 1
0x14005f73e  mov     [rcx+8], rdx
0x14005f742  mov     [rax], r13
0x14005f745  mov     [rax+8], r13
0x14005f749  mov     dword ptr [rsi+6C8h], 3
0x14005f753  mov     rcx, [rbx+78h]
0x14005f757  add     rbx, 70h ; 'p'
0x14005f75b  cmp     [rcx], rbx
0x14005f75e  jz      short loc_14005F767
0x14005f760  mov     ecx, 3
0x14005f765  int     29h; Win8: RtlFailFast(ecx)
0x14005f767  lea     rax, [rsi+718h]
0x14005f76e  mov     [rax], rbx
0x14005f771  mov     [rax+8], rcx
0x14005f775  mov     [rcx], rax
0x14005f778  mov     [rbx+8], rax
0x14005f77c  mov     rcx, [rsi+6B0h]
0x14005f783  xor     edx, edx
0x14005f785  add     rcx, 48h ; 'H'
0x14005f789  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005f790  nop     dword ptr [rax+rax+00h]
0x14005f795  call    cs:__imp_KeLeaveCriticalRegion
0x14005f79c  nop     dword ptr [rax+rax+00h]
0x14005f7a1  xor     edx, edx
0x14005f7a3  mov     rcx, r15
0x14005f7a6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005f7ad  nop     dword ptr [rax+rax+00h]
0x14005f7b2  call    cs:__imp_KeLeaveCriticalRegion
0x14005f7b9  nop     dword ptr [rax+rax+00h]
0x14005f7be  mov     rcx, [rsp+0E8h+var_B8]
0x14005f7c3  xor     edx, edx
0x14005f7c5  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14005f7cc  nop     dword ptr [rax+rax+00h]
0x14005f7d1  mov     [rsp+0E8h+var_B8], r13
0x14005f7d6  call    cs:__imp_KeLeaveCriticalRegion
0x14005f7dd  nop     dword ptr [rax+rax+00h]
0x14005f7e2  test    dil, dil
0x14005f7e5  jnz     short loc_14005F840
0x14005f7e7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005f7ee  jnz     loc_14005FE07
0x14005f7f4  mov     r15, [rsp+0E8h+var_28]
0x14005f7fc  mov     r14, [rsp+0E8h+var_20]
0x14005f804  mov     r12, [rsp+0E8h+var_18]
0x14005f80c  mov     rdi, [rsp+0E8h+arg_18]
0x14005f814  mov     rbp, [rsp+0E8h+arg_10]
0x14005f81c  mov     rbx, [rsp+0E8h+arg_8]
0x14005f824  mov     rcx, [rsp+0E8h+var_38]
0x14005f82c  xor     rcx, rsp; StackCookie
0x14005f82f  call    __security_check_cookie
0x14005f834  add     rsp, 0D8h
0x14005f83b  pop     r13
0x14005f83d  pop     rsi
0x14005f83e  retn
0x14005f840  lea     rdx, [rsi+30h]; BugCheckParameter2
0x14005f844  lock xadd [rdx], r14d
0x14005f849  dec     r14d
0x14005f84c  cmp     cs:UxDebugCheckRefcount, 0
0x14005f853  jnz     loc_14005F964
0x14005f859  test    r14d, r14d
0x14005f85c  jnz     short loc_14005F7E7
0x14005f85e  mov     rcx, rsi
0x14005f861  call    UlpQueueFreeHttpRequest
0x14005f866  jmp     loc_14005F7E7
0x14005f86b  mov     eax, r14d
0x14005f86e  lock xadd [rdx], eax
0x14005f872  dec     eax
0x14005f874  cmp     cs:UxDebugCheckRefcount, r13b
0x14005f87b  jnz     loc_14005F982
0x14005f881  test    eax, eax
0x14005f883  jz      loc_14005FD4D
0x14005f889  mov     [rbx+58h], r13
0x14005f88d  jmp     loc_14005F622
0x14005f892  cmp     eax, r14d
0x14005f895  jg      loc_14005F484
0x14005f89b  movsxd  r9, eax; BugCheckParameter4
0x14005f89e  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14005f8a2  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14005f8a8  mov     ecx, 3; BugCheckParameter1
0x14005f8ad  call    UlBugCheckEx
0x14005f8b3  lea     rbp, [rdi+40h]
0x14005f8b7  call    cs:__imp_IoGetCurrentProcess
0x14005f8be  nop     dword ptr [rax+rax+00h]
0x14005f8c3  cmp     cs:UxSystemProcess, rax
0x14005f8ca  mov     rdi, [rdi+440h]
0x14005f8d1  mov     rcx, [rbp+0]
0x14005f8d5  jnz     loc_14005FBA7
0x14005f8db  test    rcx, rcx
0x14005f8de  jnz     short loc_14005F8F0
0x14005f8e0  cmp     [rbp+10h], r13
0x14005f8e4  jnz     short loc_14005F8F0
0x14005f8e6  cmp     [rbp+20h], r13
0x14005f8ea  jz      loc_14005FA17
0x14005f8f0  mov     r9d, 0E1h; BugCheckParameter4
0x14005f8f6  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14005f8fd  mov     rdx, rbp; BugCheckParameter2
0x14005f900  mov     rcx, r12; BugCheckParameter1
0x14005f903  call    UlBugCheckEx
0x14005f909  cmp     eax, r14d
0x14005f90c  jg      loc_14005F50C
0x14005f912  movsxd  r9, eax; BugCheckParameter4
0x14005f915  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14005f919  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14005f91f  mov     ecx, 3; BugCheckParameter1
0x14005f924  call    UlBugCheckEx
0x14005f92a  cmp     eax, r14d
0x14005f92d  jg      loc_14005F63C
0x14005f933  movsxd  r9, eax; BugCheckParameter4
0x14005f936  mov     ecx, 3; BugCheckParameter1
0x14005f93b  mov     r8d, 0Eh; BugCheckParameter3
0x14005f941  call    UlBugCheckEx
  ... truncated ...
```
