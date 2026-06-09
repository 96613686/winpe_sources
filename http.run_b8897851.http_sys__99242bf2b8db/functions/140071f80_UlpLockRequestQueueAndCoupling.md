# UlpLockRequestQueueAndCoupling

- ea: `0x140071f80`
- end: `0x140072800`
- name: `UlpLockRequestQueueAndCoupling`
- size: `2176`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400cdc2c`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140049d28`
- `0x14005dff0`
- `0x14005e050`
- `0x1400705f0`
- `0x140071f80`
- `0x14009622c`
- `0x1400a033c`
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

- `ntoskrnl!KeGetCurrentIrql` at `0x14007243a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14007243a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140072563`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140072563`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14007225c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14007225c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400724c2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400724c2`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14007251a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14007251a`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14007279c`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14007279c`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140072462`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140072462`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400724a3`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400724a3`
- `ntoskrnl!KeSetEvent` at `0x140072581`
- `ntoskrnl!KeSetEvent` at `0x140072581`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400724eb`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400724eb`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14007205a`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14007205a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400723f4`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400723f4`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400726e2`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400726e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140072035`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140072189`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400721ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140072429`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400726d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400726f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140072035`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140072189`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400721ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140072429`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400726d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400726f6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140072029`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007217d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400721a2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007241d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400726c4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140072029`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007217d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400721a2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007241d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400726c4`
- `ntoskrnl!IoGetCurrentProcess` at `0x140072320`
- `ntoskrnl!IoGetCurrentProcess` at `0x140072320`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071fed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007207f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400720f6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140072113`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140072287`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071fed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007207f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400720f6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140072113`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140072287`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071fd8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140072045`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007206a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400720dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140072102`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140072275`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071fd8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140072045`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007206a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400720dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140072102`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140072275`

## pseudocode

```c
volatile signed __int32 *__fastcall UlpLockRequestQueueAndCoupling(__int64 a1, _QWORD *a2)
{
  volatile signed __int32 *v4; // rbx
  int v5; // eax
  __int64 v6; // rdi
  int v7; // eax
  __int64 v8; // rdi
  __int64 v9; // rdx
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // r8
  _QWORD *v14; // rdx
  volatile signed __int32 *v15; // rdx
  volatile signed __int32 *v16; // rdx
  int v17; // eax
  __int64 v18; // rdi
  int v19; // esi
  bool v20; // zf
  unsigned __int64 v21; // rdi
  int v23; // eax
  ULONG_PTR v24; // rsi
  struct _KPROCESS *CurrentProcess; // rax
  void *CurrentServerSilo; // rdi
  __int64 v27; // rcx
  __int64 v28; // rdi
  USHORT CurrentNodeNumber; // ax
  char v30; // bp
  __int64 v31; // rax
  __int64 v32; // r14
  ULONG v33; // ebp
  ULONG_PTR v34; // rdx
  int v35; // r13d
  __int64 v36; // rdi
  __int64 v37; // rax
  int v38; // eax
  __int128 v39; // [rsp+30h] [rbp-B8h] BYREF
  _DWORD v40[24]; // [rsp+40h] [rbp-A8h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a1 )
      v37 = *(_QWORD *)(a1 + 64);
    else
      v37 = 0;
    WPP_SF_qqP(1032, 38, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, v37, a2);
  }
  *a2 = 0;
  while ( 1 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 1704, 0);
    v4 = *(volatile signed __int32 **)(a1 + 1712);
    if ( !v4 )
      break;
    v5 = _InterlockedIncrement(v4 + 5);
    if ( UxDebugCheckRefcount && v5 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v4 + 5), 0x21u, v5);
    ExReleasePushLockExclusiveEx(a1 + 1704, 0);
    KeLeaveCriticalRegion();
    v6 = *((_QWORD *)v4 + 8);
    KeEnterCriticalRegion();
    *a2 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v6 + 280), 0);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 1704, 0);
    if ( *(volatile signed __int32 **)(a1 + 1712) == v4 )
    {
      v7 = _InterlockedDecrement(v4 + 5);
      if ( UxDebugCheckRefcount && v7 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v4 + 5), 0x21u, v7);
      if ( v7 )
        goto LABEL_27;
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v4, 0);
      v8 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v4 + 8) + 264LL) + 8LL
                                                                * *(unsigned __int16 *)(*((_QWORD *)v4 + 7) + 56LL));
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(*((_QWORD *)v4 + 7) + 944LL, 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v8, 0);
      v9 = *((_QWORD *)v4 + 3);
      v10 = v4 + 6;
      if ( *(volatile signed __int32 **)(v9 + 8) != v4 + 6 )
        goto LABEL_48;
      v11 = (_QWORD *)*((_QWORD *)v4 + 4);
      if ( (_QWORD *)*v11 != v10
        || (*v11 = v9,
            *(_QWORD *)(v9 + 8) = v11,
            *v10 = 0,
            *((_QWORD *)v4 + 4) = 0,
            v12 = v4 + 10,
            v13 = *((_QWORD *)v4 + 5),
            *(volatile signed __int32 **)(v13 + 8) != v4 + 10)
        || (v14 = (_QWORD *)*((_QWORD *)v4 + 6), (_QWORD *)*v14 != v12) )
      {
LABEL_48:
        __fastfail(3u);
      }
      *v14 = v13;
      *(_QWORD *)(v13 + 8) = v14;
      *v12 = 0;
      *((_QWORD *)v4 + 6) = 0;
      ExReleasePushLockExclusiveEx(v8, 0);
      KeLeaveCriticalRegion();
      ExReleasePushLockExclusiveEx(*((_QWORD *)v4 + 7) + 944LL, 0);
      KeLeaveCriticalRegion();
      v15 = (volatile signed __int32 *)*((_QWORD *)v4 + 11);
      if ( v15 )
      {
        v23 = _InterlockedDecrement(v15);
        if ( UxDebugCheckRefcount && v23 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)v15, 0xEu, v23);
        if ( !v23 )
          UlConsumerCleanupCompletion(*((_QWORD *)v4 + 11));
        *((_QWORD *)v4 + 11) = 0;
      }
      v16 = (volatile signed __int32 *)*((_QWORD *)v4 + 8);
      v17 = _InterlockedDecrement(v16);
      if ( UxDebugCheckRefcount && v17 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v16, 0xEu, v17);
      if ( !v17 )
        UlFreeRequestQueue(*((PVOID *)v4 + 8));
      v18 = *((_QWORD *)v4 + 7);
      *((_QWORD *)v4 + 8) = 0;
      v19 = _InterlockedDecrement((volatile signed __int32 *)(v18 + 40));
      if ( UxDebugCheckRefcount && v19 <= -1 )
        UlBugCheckEx(3u, v18 + 40, 0xEu, v19);
      if ( v19 )
      {
LABEL_20:
        v20 = UxDebugDisableLookaside == 0;
        *((_QWORD *)v4 + 7) = 0;
        *((_DWORD *)v4 + 4) = 1969441909;
        if ( v20 )
        {
          if ( UxCompactMode )
          {
            v28 = qword_1401A0910;
            CurrentNodeNumber = KeGetCurrentNodeNumber();
            PplFreeToLookasideListProcessor(v28, v4, CurrentNodeNumber);
          }
          else
          {
            v21 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*v4 + 1) << 7);
            if ( !*(_BYTE *)(v21 + 176) )
              PplpLazyInitializeLookasideList(qword_1401A0910, v21 + 64);
            ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v21 + 64), (PVOID)v4);
          }
        }
        else
        {
          memset(v40, 0, sizeof(v40));
          v40[10] = dword_1401A0928;
          ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0938)(v4, v40);
        }
        if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
LABEL_27:
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v4 + 18, 0);
        goto LABEL_28;
      }
      v24 = v18 + 64;
      CurrentProcess = IoGetCurrentProcess();
      CurrentServerSilo = *(void **)(v18 + 1088);
      v27 = *(_QWORD *)v24;
      if ( UxSystemProcess != CurrentProcess )
      {
        if ( v27 || *(_QWORD *)(v24 + 16) || *(_QWORD *)(v24 + 32) )
          UlBugCheckEx(1u, v24, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
        UlThreadPoolEnqueueWorkItem(0, v24, UlFreeHttpConnection, 1, CurrentServerSilo, -1);
        goto LABEL_20;
      }
      if ( v27 || *(_QWORD *)(v24 + 16) || *(_QWORD *)(v24 + 32) )
        UlBugCheckEx(1u, v24, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
      if ( KeGetCurrentIrql() )
      {
        v33 = 0;
        if ( (unsigned int)dword_1401A3F48 > 1 )
        {
          v33 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
          if ( byte_1401A3F60 )
            v33 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
        }
        if ( CurrentServerSilo == (void *)-1LL )
          CurrentServerSilo = (void *)PsGetCurrentServerSilo();
        *(_QWORD *)(v24 + 32) = CurrentServerSilo;
        *(_QWORD *)&v39 = 0;
        if ( CurrentServerSilo )
          ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
        PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v39);
        v34 = v39 + 24;
        v35 = _InterlockedIncrement((volatile signed __int32 *)(v39 + 24));
        if ( UxDebugCheckRefcount && v35 <= -1 )
          UlBugCheckEx(3u, v34, 0xDu, v35);
        *(_BYTE *)(v24 + 24) = 1;
        v36 = *(_QWORD *)(qword_1401A3F50 + 8LL * v33);
        *(_QWORD *)(v24 + 16) = UlFreeHttpConnection;
        if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v36 + 16), (PSLIST_ENTRY)v24) )
        {
          KeSetEvent((PRKEVENT)(v36 + 32), 0, 0);
          UlpActivateThreadPoolQueue((PVOID)v36);
        }
        goto LABEL_20;
      }
      v30 = 0;
      v39 = 0;
      if ( CurrentServerSilo != (void *)-1LL )
      {
        v31 = PsAttachSiloToCurrentThread(CurrentServerSilo);
        v32 = v31;
        v30 = 1;
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
        {
          WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v31, CurrentServerSilo);
          UlFreeHttpConnection(v24);
        }
        else
        {
LABEL_56:
          UlFreeHttpConnection(v24);
          if ( !v30 )
            goto LABEL_20;
        }
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v32);
        PsDetachSiloFromCurrentThread(v32);
        goto LABEL_20;
      }
      v32 = *((_QWORD *)&v39 + 1);
      goto LABEL_56;
    }
    ExReleasePushLockExclusiveEx(a1 + 1704, 0);
    KeLeaveCriticalRegion();
    ExReleaseCacheAwarePushLockSharedEx(*a2, 0);
    *a2 = 0;
    KeLeaveCriticalRegion();
    v38 = _InterlockedDecrement(v4 + 5);
    if ( UxDebugCheckRefcount && v38 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v4 + 5), 0x21u, v38);
    if ( !v38 )
      UlpFreeCoupling((PVOID)v4);
  }
  ExReleasePushLockExclusiveEx(a1 + 1704, 0);
  KeLeaveCriticalRegion();
LABEL_28:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 39, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x140071f80  push    rbx
0x140071f82  push    rsi
0x140071f83  push    r12
0x140071f85  push    r13
0x140071f87  push    r14
0x140071f89  push    r15
0x140071f8b  sub     rsp, 0B8h
0x140071f92  mov     rax, cs:__security_cookie
0x140071f99  xor     rax, rsp
0x140071f9c  mov     [rsp+0E8h+var_48], rax
0x140071fa4  mov     r12, rdx
0x140071fa7  mov     r14, rcx
0x140071faa  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140071fb1  jnz     loc_140072686
0x140071fb7  xor     eax, eax
0x140071fb9  mov     [rsp+0E8h+arg_10], rbp
0x140071fc1  mov     [r12], rax
0x140071fc5  mov     esi, 0FFFFFFFFh
0x140071fca  mov     r13d, 1
0x140071fd0  mov     [rsp+0E8h+var_38], rdi
0x140071fd8  call    cs:__imp_KeEnterCriticalRegion
0x140071fdf  nop     dword ptr [rax+rax+00h]
0x140071fe4  xor     edx, edx
0x140071fe6  lea     rcx, [r14+6A8h]
0x140071fed  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140071ff4  nop     dword ptr [rax+rax+00h]
0x140071ff9  mov     rbx, [r14+6B0h]
0x140072000  test    rbx, rbx
0x140072003  jz      loc_140072414
0x140072009  mov     eax, r13d
0x14007200c  lock xadd [rbx+14h], eax
0x140072011  inc     eax
0x140072013  cmp     cs:UxDebugCheckRefcount, 0
0x14007201a  jnz     loc_1400722FC
0x140072020  xor     edx, edx
0x140072022  lea     rcx, [r14+6A8h]
0x140072029  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140072030  nop     dword ptr [rax+rax+00h]
0x140072035  call    cs:__imp_KeLeaveCriticalRegion
0x14007203c  nop     dword ptr [rax+rax+00h]
0x140072041  mov     rdi, [rbx+40h]
0x140072045  call    cs:__imp_KeEnterCriticalRegion
0x14007204c  nop     dword ptr [rax+rax+00h]
0x140072051  mov     rcx, [rdi+118h]
0x140072058  xor     edx, edx
0x14007205a  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x140072061  nop     dword ptr [rax+rax+00h]
0x140072066  mov     [r12], rax
0x14007206a  call    cs:__imp_KeEnterCriticalRegion
0x140072071  nop     dword ptr [rax+rax+00h]
0x140072076  xor     edx, edx
0x140072078  lea     rcx, [r14+6A8h]
0x14007207f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140072086  nop     dword ptr [rax+rax+00h]
0x14007208b  cmp     [r14+6B0h], rbx
0x140072092  jnz     loc_1400726BB
0x140072098  mov     eax, esi
0x14007209a  lock xadd [rbx+14h], eax
0x14007209f  dec     eax
0x1400720a1  cmp     cs:UxDebugCheckRefcount, 0
0x1400720a8  jnz     loc_140072371
0x1400720ae  test    eax, eax
0x1400720b0  jnz     loc_140072275
0x1400720b6  xor     r15d, r15d
0x1400720b9  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400720c0  jnz     loc_1400725E8
0x1400720c6  mov     rax, [rbx+38h]
0x1400720ca  movzx   edx, word ptr [rax+38h]
0x1400720ce  mov     rax, [rbx+40h]
0x1400720d2  mov     rcx, [rax+108h]
0x1400720d9  mov     rdi, [rcx+rdx*8]
0x1400720dd  call    cs:__imp_KeEnterCriticalRegion
0x1400720e4  nop     dword ptr [rax+rax+00h]
0x1400720e9  mov     rcx, [rbx+38h]
0x1400720ed  xor     edx, edx
0x1400720ef  add     rcx, 3B0h
0x1400720f6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400720fd  nop     dword ptr [rax+rax+00h]
0x140072102  call    cs:__imp_KeEnterCriticalRegion
0x140072109  nop     dword ptr [rax+rax+00h]
0x14007210e  xor     edx, edx
0x140072110  mov     rcx, rdi
0x140072113  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14007211a  nop     dword ptr [rax+rax+00h]
0x14007211f  mov     rdx, [rbx+18h]
0x140072123  lea     rax, [rbx+18h]
0x140072127  cmp     [rdx+8], rax
0x14007212b  jnz     loc_1400723CA
0x140072131  mov     rcx, [rax+8]
0x140072135  cmp     [rcx], rax
0x140072138  jnz     loc_1400723CA
0x14007213e  mov     [rcx], rdx
0x140072141  mov     [rdx+8], rcx
0x140072145  mov     [rax], r15
0x140072148  mov     [rax+8], r15
0x14007214c  lea     rax, [rbx+28h]
0x140072150  mov     r8, [rax]
0x140072153  cmp     [r8+8], rax
0x140072157  jnz     loc_1400723CA
0x14007215d  mov     rdx, [rax+8]
0x140072161  cmp     [rdx], rax
0x140072164  jnz     loc_1400723CA
0x14007216a  mov     [rdx], r8
0x14007216d  mov     rcx, rdi
0x140072170  mov     [r8+8], rdx
0x140072174  xor     edx, edx
0x140072176  mov     [rax], r15
0x140072179  mov     [rax+8], r15
0x14007217d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140072184  nop     dword ptr [rax+rax+00h]
0x140072189  call    cs:__imp_KeLeaveCriticalRegion
0x140072190  nop     dword ptr [rax+rax+00h]
0x140072195  mov     rcx, [rbx+38h]
0x140072199  xor     edx, edx
0x14007219b  add     rcx, 3B0h
0x1400721a2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400721a9  nop     dword ptr [rax+rax+00h]
0x1400721ae  call    cs:__imp_KeLeaveCriticalRegion
0x1400721b5  nop     dword ptr [rax+rax+00h]
0x1400721ba  mov     rdx, [rbx+58h]; BugCheckParameter2
0x1400721be  test    rdx, rdx
0x1400721c1  jnz     loc_1400722D6
0x1400721c7  mov     rdx, [rbx+40h]; BugCheckParameter2
0x1400721cb  mov     eax, esi
0x1400721cd  lock xadd [rdx], eax
0x1400721d1  dec     eax
0x1400721d3  cmp     cs:UxDebugCheckRefcount, 0
0x1400721da  jnz     loc_140072391
0x1400721e0  test    eax, eax
0x1400721e2  jz      loc_140072755
0x1400721e8  mov     rdi, [rbx+38h]
0x1400721ec  mov     [rbx+40h], r15
0x1400721f0  lea     rdx, [rdi+28h]; BugCheckParameter2
0x1400721f4  lock xadd [rdx], esi
0x1400721f8  dec     esi
0x1400721fa  cmp     cs:UxDebugCheckRefcount, 0
0x140072201  jnz     loc_1400723AD
0x140072207  test    esi, esi
0x140072209  jz      loc_14007231C
0x14007220f  cmp     cs:UxDebugDisableLookaside, 0
0x140072216  mov     [rbx+38h], r15
0x14007221a  mov     dword ptr [rbx+10h], 75634C75h
0x140072221  jnz     loc_1400727AD
0x140072227  cmp     cs:UxCompactMode, 0
0x14007222e  jnz     loc_1400723ED
0x140072234  mov     edi, [rbx]
0x140072236  mov     rcx, cs:qword_1401A0910
0x14007223d  inc     edi
0x14007223f  shl     rdi, 7
0x140072243  add     rdi, rcx
0x140072246  movzx   eax, byte ptr [rdi+0B0h]
0x14007224d  test    al, al
0x14007224f  jz      loc_140072626
0x140072255  mov     rdx, rbx; Entry
0x140072258  lea     rcx, [rdi+40h]; Lookaside
0x14007225c  call    cs:__imp_ExFreeToLookasideListEx
0x140072263  nop     dword ptr [rax+rax+00h]
0x140072268  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14007226f  jnz     loc_14007260B
0x140072275  call    cs:__imp_KeEnterCriticalRegion
0x14007227c  nop     dword ptr [rax+rax+00h]
0x140072281  lea     rcx, [rbx+48h]
0x140072285  xor     edx, edx
0x140072287  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14007228e  nop     dword ptr [rax+rax+00h]
0x140072293  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14007229a  jnz     loc_1400727E2
0x1400722a0  mov     rdi, [rsp+0E8h+var_38]
0x1400722a8  mov     rax, rbx
0x1400722ab  mov     rbp, [rsp+0E8h+arg_10]
0x1400722b3  mov     rcx, [rsp+0E8h+var_48]
0x1400722bb  xor     rcx, rsp; StackCookie
0x1400722be  call    __security_check_cookie
0x1400722c3  add     rsp, 0B8h
0x1400722ca  pop     r15
0x1400722cc  pop     r14
0x1400722ce  pop     r13
0x1400722d0  pop     r12
0x1400722d2  pop     rsi
0x1400722d3  pop     rbx
0x1400722d4  retn
0x1400722d6  mov     eax, esi
0x1400722d8  lock xadd [rdx], eax
0x1400722dc  dec     eax
0x1400722de  cmp     cs:UxDebugCheckRefcount, 0
0x1400722e5  jnz     loc_1400723D1
0x1400722eb  test    eax, eax
0x1400722ed  jz      loc_140072747
0x1400722f3  mov     [rbx+58h], r15
0x1400722f7  jmp     loc_1400721C7
0x1400722fc  cmp     eax, esi
0x1400722fe  jg      loc_140072020
0x140072304  movsxd  r9, eax; BugCheckParameter4
0x140072307  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14007230b  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140072311  mov     ecx, 3; BugCheckParameter1
0x140072316  call    UlBugCheckEx
0x14007231c  lea     rsi, [rdi+40h]
0x140072320  call    cs:__imp_IoGetCurrentProcess
0x140072327  nop     dword ptr [rax+rax+00h]
0x14007232c  cmp     cs:UxSystemProcess, rax
0x140072333  mov     rdi, [rdi+440h]
0x14007233a  mov     rcx, [rsi]
0x14007233d  jnz     loc_1400725BE
0x140072343  test    rcx, rcx
0x140072346  jnz     short loc_140072358
0x140072348  cmp     [rsi+10h], rcx
0x14007234c  jnz     short loc_140072358
0x14007234e  cmp     [rsi+20h], rcx
0x140072352  jz      loc_14007243A
0x140072358  mov     r9d, 0E1h; BugCheckParameter4
0x14007235e  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140072365  mov     rdx, rsi; BugCheckParameter2
0x140072368  mov     rcx, r13; BugCheckParameter1
0x14007236b  call    UlBugCheckEx
0x140072371  cmp     eax, esi
0x140072373  jg      loc_1400720AE
0x140072379  movsxd  r9, eax; BugCheckParameter4
0x14007237c  lea     rdx, [rbx+14h]; BugCheckParameter2
0x140072380  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140072386  mov     ecx, 3; BugCheckParameter1
0x14007238b  call    UlBugCheckEx
0x140072391  cmp     eax, esi
0x140072393  jg      loc_1400721E0
0x140072399  movsxd  r9, eax; BugCheckParameter4
0x14007239c  mov     ecx, 3; BugCheckParameter1
0x1400723a1  mov     r8d, 0Eh; BugCheckParameter3
0x1400723a7  call    UlBugCheckEx
0x1400723ad  cmp     esi, 0FFFFFFFFh
0x1400723b0  jg      loc_140072207
0x1400723b6  movsxd  r9, esi; BugCheckParameter4
0x1400723b9  mov     ecx, 3; BugCheckParameter1
0x1400723be  mov     r8d, 0Eh; BugCheckParameter3
0x1400723c4  call    UlBugCheckEx
0x1400723ca  mov     ecx, 3
0x1400723cf  int     29h; Win8: RtlFailFast(ecx)
0x1400723d1  cmp     eax, esi
0x1400723d3  jg      loc_1400722EB
0x1400723d9  movsxd  r9, eax; BugCheckParameter4
0x1400723dc  mov     ecx, 3; BugCheckParameter1
0x1400723e1  mov     r8d, 0Eh; BugCheckParameter3
0x1400723e7  call    UlBugCheckEx
0x1400723ed  mov     rdi, cs:qword_1401A0910
0x1400723f4  call    cs:__imp_KeGetCurrentNodeNumber
0x1400723fb  nop     dword ptr [rax+rax+00h]
0x140072400  movzx   r8d, ax
0x140072404  mov     rdx, rbx
0x140072407  mov     rcx, rdi
0x14007240a  call    PplFreeToLookasideListProcessor
0x14007240f  jmp     loc_140072268
0x140072414  xor     edx, edx
0x140072416  lea     rcx, [r14+6A8h]
0x14007241d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140072424  nop     dword ptr [rax+rax+00h]
0x140072429  call    cs:__imp_KeLeaveCriticalRegion
0x140072430  nop     dword ptr [rax+rax+00h]
0x140072435  jmp     loc_140072293
0x14007243a  call    cs:__imp_KeGetCurrentIrql
0x140072441  nop     dword ptr [rax+rax+00h]
0x140072446  test    al, al
0x140072448  jnz     short loc_1400724B4
0x14007244a  xor     bpl, bpl
0x14007244d  xorps   xmm0, xmm0
0x140072450  movups  [rsp+0E8h+var_B8], xmm0
0x140072455  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140072459  jz      loc_1400725B4
0x14007245f  mov     rcx, rdi
0x140072462  call    cs:__imp_PsAttachSiloToCurrentThread
0x140072469  nop     dword ptr [rax+rax+00h]
0x14007246e  mov     r14, rax
0x140072471  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140072478  movzx   ebp, r13b
0x14007247c  jnz     loc_14007265B
0x140072482  mov     rcx, rsi
0x140072485  call    UlFreeHttpConnection
0x14007248a  test    bpl, bpl
0x14007248d  jz      loc_14007220F
0x140072493  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14007249a  jnz     loc_140072763
0x1400724a0  mov     rcx, r14
0x1400724a3  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1400724aa  nop     dword ptr [rax+rax+00h]
0x1400724af  jmp     loc_14007220F
0x1400724b4  cmp     cs:dword_1401A3F48, r13d
0x1400724bb  mov     ebp, r15d
0x1400724be  jbe     short loc_1400724E5
0x1400724c0  xor     ecx, ecx; ProcNumber
0x1400724c2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400724c9  nop     dword ptr [rax+rax+00h]
0x1400724ce  xor     edx, edx
0x1400724d0  div     cs:UxNumberOfProcessors
0x1400724d6  cmp     cs:byte_1401A3F60, 0
0x1400724dd  mov     ebp, edx
0x1400724df  jnz     loc_140072781
0x1400724e5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400724e9  jnz     short loc_1400724FA
0x1400724eb  call    cs:__imp_PsGetCurrentServerSilo
0x1400724f2  nop     dword ptr [rax+rax+00h]
0x1400724f7  mov     rdi, rax
0x1400724fa  mov     [rsi+20h], rdi
  ... truncated ...
```
