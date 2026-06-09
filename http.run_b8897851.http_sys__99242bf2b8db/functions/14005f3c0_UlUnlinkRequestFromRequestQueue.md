# UlUnlinkRequestFromRequestQueue

- ea: `0x14005f3c0`
- end: `0x14005fe42`
- name: `UlUnlinkRequestFromRequestQueue`
- size: `2690`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400b0e94`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x14000e420`
- `0x140022610`
- `0x140049d28`
- `0x14005dff0`
- `0x14005e050`
- `0x14005f3c0`
- `0x1400705f0`
- `0x14009622c`
- `0x1400a033c`
- `0x1400cfc88`
- `0x14013dc78`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9c5c`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005fa37`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005fa37`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005fb61`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005fb61`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005f6db`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005f6db`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005faba`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005faba`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005fb17`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005fb17`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005fdc3`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14005fdc3`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005fa5f`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005fa5f`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005fa9b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14005fa9b`
- `ntoskrnl!KeSetEvent` at `0x14005fb7f`
- `ntoskrnl!KeSetEvent` at `0x14005fb7f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005fae4`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005fae4`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14005f4da`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14005f4da`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005f9c6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14005f9c6`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005f7e5`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005fcd8`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005f7e5`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14005fcd8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f4b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f604`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f629`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7d2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f9f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005fcc5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005fce9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f4b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f604`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f629`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7d2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f9f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005fcc5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005fce9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f4a9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f5f8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f61d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f7a9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f7c6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f9eb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005fcb9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f4a9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f5f8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f61d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f7a9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f7c6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005f9eb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005fcb9`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005f8d7`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005f8d7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f471`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f4fc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f571`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f58e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f706`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f471`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f4fc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f571`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f58e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005f706`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f460`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f4c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f4eb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f558`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f57d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f6f4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f460`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f4c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f4eb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f558`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f57d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005f6f4`

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
  __int64 v44; // [rsp+30h] [rbp-B8h] BYREF
  __int128 v45; // [rsp+38h] [rbp-B0h] BYREF
  _DWORD v46[24]; // [rsp+50h] [rbp-98h] BYREF

  v1 = 0;
  v44 = 0;
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
      WPP_SF_qqP(1032, 38, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, *(_QWORD *)(a1 + 64), &v44);
    v44 = 0;
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
      v44 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v5 + 280), 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(a1 + 1704, 0);
      if ( *(_DWORD **)(a1 + 1712) == v3 )
        break;
      ExReleasePushLockExclusiveEx(a1 + 1704, 0);
      KeLeaveCriticalRegion();
      ExReleaseCacheAwarePushLockSharedEx(v44, 0);
      v44 = 0;
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
                  memset(v46, 0, sizeof(v46));
                  v46[10] = dword_1401A0928;
                  ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A0938)(v3, v46);
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
                UlThreadPoolEnqueueWorkItem(0, v29, UlFreeHttpConnection, 1, CurrentServerSilo, -1);
                goto LABEL_23;
              }
              if ( v32 || *(_QWORD *)(v29 + 16) || *(_QWORD *)(v29 + 32) )
                UlBugCheckEx(1u, v29, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
              if ( KeGetCurrentIrql() )
              {
                if ( (unsigned int)dword_1401A3F48 > 1 )
                {
                  v1 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
                  if ( byte_1401A3F60 )
                    v1 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
                }
                if ( CurrentServerSilo == (void *)-1LL )
                  CurrentServerSilo = (void *)PsGetCurrentServerSilo();
                *(_QWORD *)(v29 + 32) = CurrentServerSilo;
                *(_QWORD *)&v45 = 0;
                if ( CurrentServerSilo )
                  ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
                PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v45);
                v39 = v45 + 24;
                v40 = _InterlockedIncrement((volatile signed __int32 *)(v45 + 24));
                if ( UxDebugCheckRefcount && v40 <= -1 )
                  UlBugCheckEx(3u, v39, 0xDu, v40);
                *(_BYTE *)(v29 + 24) = 1;
                v41 = *(_QWORD *)(qword_1401A3F50 + 8LL * v1);
                *(_QWORD *)(v29 + 16) = UlFreeHttpConnection;
                if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v41 + 16), (PSLIST_ENTRY)v29) )
                {
                  KeSetEvent((PRKEVENT)(v41 + 32), 0, 0);
                  UlpActivateThreadPoolQueue((PVOID)v41);
                }
                goto LABEL_23;
              }
              v36 = 0;
              v45 = 0;
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
              v38 = *((_QWORD *)&v45 + 1);
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
      ExReleaseCacheAwarePushLockSharedEx(v44, 0);
      v44 = 0;
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
0x14005f3c0  push    rsi
0x14005f3c2  push    r13
0x14005f3c4  sub     rsp, 0D8h
0x14005f3cb  mov     rax, cs:__security_cookie
0x14005f3d2  xor     rax, rsp
0x14005f3d5  mov     [rsp+0E8h+var_38], rax
0x14005f3dd  xor     r13d, r13d
0x14005f3e0  mov     rsi, rcx
0x14005f3e3  mov     [rsp+0E8h+var_B8], r13
0x14005f3e8  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005f3ef  jnz     loc_14005FA08
0x14005f3f5  mov     r8d, 40h ; '@'
0x14005f3fb  mov     [rsp+0E8h+arg_8], rbx
0x14005f403  mov     r9, rsi
0x14005f406  mov     [rsp+0E8h+arg_10], rbp
0x14005f40e  mov     [rsp+0E8h+arg_18], rdi
0x14005f416  mov     [rsp+0E8h+var_18], r12
0x14005f41e  mov     [rsp+0E8h+var_20], r14
0x14005f426  mov     [rsp+0E8h+var_28], r15
0x14005f42e  cmp     [rsi+73Ch], r13b
0x14005f435  jz      loc_14005F807
0x14005f43b  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005f442  jnz     loc_14005FD3C
0x14005f448  mov     [rsp+0E8h+var_B8], r13
0x14005f44d  lea     r15, [rsi+6A8h]
0x14005f454  mov     r12d, 1
0x14005f45a  mov     r14d, 0FFFFFFFFh
0x14005f460  call    cs:__imp_KeEnterCriticalRegion
0x14005f467  nop     dword ptr [rax+rax+00h]
0x14005f46c  xor     edx, edx
0x14005f46e  mov     rcx, r15
0x14005f471  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005f478  nop     dword ptr [rax+rax+00h]
0x14005f47d  mov     rbx, [rsi+6B0h]
0x14005f484  test    rbx, rbx
0x14005f487  jz      loc_14005F9E6
0x14005f48d  mov     eax, r12d
0x14005f490  lock xadd [rbx+14h], eax
0x14005f495  inc     eax
0x14005f497  cmp     cs:UxDebugCheckRefcount, r13b
0x14005f49e  jnz     loc_14005F8B2
0x14005f4a4  xor     edx, edx
0x14005f4a6  mov     rcx, r15
0x14005f4a9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005f4b0  nop     dword ptr [rax+rax+00h]
0x14005f4b5  call    cs:__imp_KeLeaveCriticalRegion
0x14005f4bc  nop     dword ptr [rax+rax+00h]
0x14005f4c1  mov     rdi, [rbx+40h]
0x14005f4c5  call    cs:__imp_KeEnterCriticalRegion
0x14005f4cc  nop     dword ptr [rax+rax+00h]
0x14005f4d1  mov     rcx, [rdi+118h]
0x14005f4d8  xor     edx, edx
0x14005f4da  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14005f4e1  nop     dword ptr [rax+rax+00h]
0x14005f4e6  mov     [rsp+0E8h+var_B8], rax
0x14005f4eb  call    cs:__imp_KeEnterCriticalRegion
0x14005f4f2  nop     dword ptr [rax+rax+00h]
0x14005f4f7  xor     edx, edx
0x14005f4f9  mov     rcx, r15
0x14005f4fc  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005f503  nop     dword ptr [rax+rax+00h]
0x14005f508  cmp     [rsi+6B0h], rbx
0x14005f50f  jnz     loc_14005FCB4
0x14005f515  mov     eax, r14d
0x14005f518  lock xadd [rbx+14h], eax
0x14005f51d  dec     eax
0x14005f51f  cmp     cs:UxDebugCheckRefcount, r13b
0x14005f526  jnz     loc_14005F929
0x14005f52c  test    eax, eax
0x14005f52e  jnz     loc_14005F6F4
0x14005f534  test    byte ptr cs:xmmword_1401A2CA0+1, r12b
0x14005f53b  jnz     loc_14005FBF1
0x14005f541  mov     rax, [rbx+38h]
0x14005f545  movzx   edx, word ptr [rax+38h]
0x14005f549  mov     rax, [rbx+40h]
0x14005f54d  mov     rcx, [rax+108h]
0x14005f554  mov     rdi, [rcx+rdx*8]
0x14005f558  call    cs:__imp_KeEnterCriticalRegion
0x14005f55f  nop     dword ptr [rax+rax+00h]
0x14005f564  mov     rcx, [rbx+38h]
0x14005f568  xor     edx, edx
0x14005f56a  add     rcx, 3B0h
0x14005f571  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005f578  nop     dword ptr [rax+rax+00h]
0x14005f57d  call    cs:__imp_KeEnterCriticalRegion
0x14005f584  nop     dword ptr [rax+rax+00h]
0x14005f589  xor     edx, edx
0x14005f58b  mov     rcx, rdi
0x14005f58e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005f595  nop     dword ptr [rax+rax+00h]
0x14005f59a  mov     rdx, [rbx+18h]
0x14005f59e  lea     rax, [rbx+18h]
0x14005f5a2  cmp     [rdx+8], rax
0x14005f5a6  jnz     loc_14005F780
0x14005f5ac  mov     rcx, [rax+8]
0x14005f5b0  cmp     [rcx], rax
0x14005f5b3  jnz     loc_14005F780
0x14005f5b9  mov     [rcx], rdx
0x14005f5bc  mov     [rdx+8], rcx
0x14005f5c0  mov     [rax], r13
0x14005f5c3  mov     [rax+8], r13
0x14005f5c7  lea     rax, [rbx+28h]
0x14005f5cb  mov     rdx, [rax]
0x14005f5ce  cmp     [rdx+8], rax
0x14005f5d2  jnz     loc_14005F780
0x14005f5d8  mov     rcx, [rax+8]
0x14005f5dc  cmp     [rcx], rax
0x14005f5df  jnz     loc_14005F780
0x14005f5e5  mov     [rcx], rdx
0x14005f5e8  mov     [rdx+8], rcx
0x14005f5ec  xor     edx, edx
0x14005f5ee  mov     rcx, rdi
0x14005f5f1  mov     [rax], r13
0x14005f5f4  mov     [rax+8], r13
0x14005f5f8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005f5ff  nop     dword ptr [rax+rax+00h]
0x14005f604  call    cs:__imp_KeLeaveCriticalRegion
0x14005f60b  nop     dword ptr [rax+rax+00h]
0x14005f610  mov     rcx, [rbx+38h]
0x14005f614  xor     edx, edx
0x14005f616  add     rcx, 3B0h
0x14005f61d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005f624  nop     dword ptr [rax+rax+00h]
0x14005f629  call    cs:__imp_KeLeaveCriticalRegion
0x14005f630  nop     dword ptr [rax+rax+00h]
0x14005f635  mov     rdx, [rbx+58h]; BugCheckParameter2
0x14005f639  test    rdx, rdx
0x14005f63c  jnz     loc_14005F88B
0x14005f642  mov     rdx, [rbx+40h]; BugCheckParameter2
0x14005f646  mov     eax, r14d
0x14005f649  lock xadd [rdx], eax
0x14005f64d  dec     eax
0x14005f64f  cmp     cs:UxDebugCheckRefcount, r13b
0x14005f656  jnz     loc_14005F94A
0x14005f65c  test    eax, eax
0x14005f65e  jz      loc_14005FD7B
0x14005f664  mov     rdi, [rbx+38h]
0x14005f668  mov     eax, r14d
0x14005f66b  mov     [rbx+40h], r13
0x14005f66f  lea     rdx, [rdi+28h]; BugCheckParameter2
0x14005f673  lock xadd [rdx], eax
0x14005f677  dec     eax
0x14005f679  cmp     cs:UxDebugCheckRefcount, r13b
0x14005f680  jnz     loc_14005F967
0x14005f686  test    eax, eax
0x14005f688  jz      loc_14005F8D3
0x14005f68e  cmp     cs:UxDebugDisableLookaside, 0
0x14005f695  mov     [rbx+38h], r13
0x14005f699  mov     dword ptr [rbx+10h], 75634C75h
0x14005f6a0  jnz     loc_14005FDD4
0x14005f6a6  cmp     cs:UxCompactMode, 0
0x14005f6ad  jnz     loc_14005F9BF
0x14005f6b3  mov     edi, [rbx]
0x14005f6b5  mov     r8, cs:qword_1401A0910
0x14005f6bc  inc     edi
0x14005f6be  shl     rdi, 7
0x14005f6c2  add     rdi, r8
0x14005f6c5  movzx   eax, byte ptr [rdi+0B0h]
0x14005f6cc  test    al, al
0x14005f6ce  jz      loc_14005FC2F
0x14005f6d4  mov     rdx, rbx; Entry
0x14005f6d7  lea     rcx, [rdi+40h]; Lookaside
0x14005f6db  call    cs:__imp_ExFreeToLookasideListEx
0x14005f6e2  nop     dword ptr [rax+rax+00h]
0x14005f6e7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005f6ee  jnz     loc_14005FC14
0x14005f6f4  call    cs:__imp_KeEnterCriticalRegion
0x14005f6fb  nop     dword ptr [rax+rax+00h]
0x14005f700  lea     rcx, [rbx+48h]
0x14005f704  xor     edx, edx
0x14005f706  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005f70d  nop     dword ptr [rax+rax+00h]
0x14005f712  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005f719  jnz     loc_14005FE09
0x14005f71f  test    rbx, rbx
0x14005f722  jz      loc_14005F807
0x14005f728  mov     ecx, [rsi+6C8h]
0x14005f72e  xor     dil, dil
0x14005f731  sub     ecx, 1
0x14005f734  jz      loc_14005FC92
0x14005f73a  cmp     ecx, 1
0x14005f73d  jnz     short loc_14005F79C
0x14005f73f  lea     rax, [rsi+6B8h]
0x14005f746  mov     rcx, [rax]
0x14005f749  cmp     [rcx+8], rax
0x14005f74d  jnz     short loc_14005F780
0x14005f74f  mov     rdx, [rax+8]
0x14005f753  cmp     [rdx], rax
0x14005f756  jnz     short loc_14005F780
0x14005f758  mov     [rdx], rcx
0x14005f75b  mov     dil, 1
0x14005f75e  mov     [rcx+8], rdx
0x14005f762  mov     [rax], r13
0x14005f765  mov     [rax+8], r13
0x14005f769  mov     dword ptr [rsi+6C8h], 3
0x14005f773  mov     rcx, [rbx+78h]
0x14005f777  add     rbx, 70h ; 'p'
0x14005f77b  cmp     [rcx], rbx
0x14005f77e  jz      short loc_14005F787
0x14005f780  mov     ecx, 3
0x14005f785  int     29h; Win8: RtlFailFast(ecx)
0x14005f787  lea     rax, [rsi+718h]
0x14005f78e  mov     [rax], rbx
0x14005f791  mov     [rax+8], rcx
0x14005f795  mov     [rcx], rax
0x14005f798  mov     [rbx+8], rax
0x14005f79c  mov     rcx, [rsi+6B0h]
0x14005f7a3  xor     edx, edx
0x14005f7a5  add     rcx, 48h ; 'H'
0x14005f7a9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005f7b0  nop     dword ptr [rax+rax+00h]
0x14005f7b5  call    cs:__imp_KeLeaveCriticalRegion
0x14005f7bc  nop     dword ptr [rax+rax+00h]
0x14005f7c1  xor     edx, edx
0x14005f7c3  mov     rcx, r15
0x14005f7c6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005f7cd  nop     dword ptr [rax+rax+00h]
0x14005f7d2  call    cs:__imp_KeLeaveCriticalRegion
0x14005f7d9  nop     dword ptr [rax+rax+00h]
0x14005f7de  mov     rcx, [rsp+0E8h+var_B8]
0x14005f7e3  xor     edx, edx
0x14005f7e5  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14005f7ec  nop     dword ptr [rax+rax+00h]
0x14005f7f1  mov     [rsp+0E8h+var_B8], r13
0x14005f7f6  call    cs:__imp_KeLeaveCriticalRegion
0x14005f7fd  nop     dword ptr [rax+rax+00h]
0x14005f802  test    dil, dil
0x14005f805  jnz     short loc_14005F860
0x14005f807  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14005f80e  jnz     loc_14005FE27
0x14005f814  mov     r15, [rsp+0E8h+var_28]
0x14005f81c  mov     r14, [rsp+0E8h+var_20]
0x14005f824  mov     r12, [rsp+0E8h+var_18]
0x14005f82c  mov     rdi, [rsp+0E8h+arg_18]
0x14005f834  mov     rbp, [rsp+0E8h+arg_10]
0x14005f83c  mov     rbx, [rsp+0E8h+arg_8]
0x14005f844  mov     rcx, [rsp+0E8h+var_38]
0x14005f84c  xor     rcx, rsp; StackCookie
0x14005f84f  call    __security_check_cookie
0x14005f854  add     rsp, 0D8h
0x14005f85b  pop     r13
0x14005f85d  pop     rsi
0x14005f85e  retn
0x14005f860  lea     rdx, [rsi+30h]; BugCheckParameter2
0x14005f864  lock xadd [rdx], r14d
0x14005f869  dec     r14d
0x14005f86c  cmp     cs:UxDebugCheckRefcount, 0
0x14005f873  jnz     loc_14005F984
0x14005f879  test    r14d, r14d
0x14005f87c  jnz     short loc_14005F807
0x14005f87e  mov     rcx, rsi
0x14005f881  call    UlpQueueFreeHttpRequest
0x14005f886  jmp     loc_14005F807
0x14005f88b  mov     eax, r14d
0x14005f88e  lock xadd [rdx], eax
0x14005f892  dec     eax
0x14005f894  cmp     cs:UxDebugCheckRefcount, r13b
0x14005f89b  jnz     loc_14005F9A2
0x14005f8a1  test    eax, eax
0x14005f8a3  jz      loc_14005FD6D
0x14005f8a9  mov     [rbx+58h], r13
0x14005f8ad  jmp     loc_14005F642
0x14005f8b2  cmp     eax, r14d
0x14005f8b5  jg      loc_14005F4A4
0x14005f8bb  movsxd  r9, eax; BugCheckParameter4
0x14005f8be  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14005f8c2  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14005f8c8  mov     ecx, 3; BugCheckParameter1
0x14005f8cd  call    UlBugCheckEx
0x14005f8d3  lea     rbp, [rdi+40h]
0x14005f8d7  call    cs:__imp_IoGetCurrentProcess
0x14005f8de  nop     dword ptr [rax+rax+00h]
0x14005f8e3  cmp     cs:UxSystemProcess, rax
0x14005f8ea  mov     rdi, [rdi+440h]
0x14005f8f1  mov     rcx, [rbp+0]
0x14005f8f5  jnz     loc_14005FBC7
0x14005f8fb  test    rcx, rcx
0x14005f8fe  jnz     short loc_14005F910
0x14005f900  cmp     [rbp+10h], r13
0x14005f904  jnz     short loc_14005F910
0x14005f906  cmp     [rbp+20h], r13
0x14005f90a  jz      loc_14005FA37
0x14005f910  mov     r9d, 0E1h; BugCheckParameter4
0x14005f916  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14005f91d  mov     rdx, rbp; BugCheckParameter2
0x14005f920  mov     rcx, r12; BugCheckParameter1
0x14005f923  call    UlBugCheckEx
0x14005f929  cmp     eax, r14d
0x14005f92c  jg      loc_14005F52C
0x14005f932  movsxd  r9, eax; BugCheckParameter4
0x14005f935  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14005f939  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14005f93f  mov     ecx, 3; BugCheckParameter1
0x14005f944  call    UlBugCheckEx
0x14005f94a  cmp     eax, r14d
0x14005f94d  jg      loc_14005F65C
0x14005f953  movsxd  r9, eax; BugCheckParameter4
0x14005f956  mov     ecx, 3; BugCheckParameter1
0x14005f95b  mov     r8d, 0Eh; BugCheckParameter3
0x14005f961  call    UlBugCheckEx
  ... truncated ...
```
