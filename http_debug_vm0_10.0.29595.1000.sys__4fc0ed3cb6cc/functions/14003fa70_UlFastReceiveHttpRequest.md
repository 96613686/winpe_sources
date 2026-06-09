# UlFastReceiveHttpRequest

- ea: `0x14003fa70`
- end: `0x14004069a`
- name: `UlFastReceiveHttpRequest`
- size: `3114`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x140041440`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x14001a360`
- `0x14003ea90`
- `0x14003fa70`
- `0x1400406a0`
- `0x140041320`
- `0x1401c3008`
- `0x1401c3184`
- `0x1401c3f58`
- `0x1401c5068`
- `0x1401c5480`
- `0x1401d9c5c`
- `0x1401d9e44`
- `0x1401da310`
- `0x1401da4fc`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003fd4d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004052d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003fd4d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004052d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003fc11`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003fc11`
- `ntoskrnl!KfRaiseIrql` at `0x14003fb94`
- `ntoskrnl!KfRaiseIrql` at `0x14003fb94`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14003fb59`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14003fb59`
- `ntoskrnl!ZwYieldExecution` at `0x14003ff31`
- `ntoskrnl!ZwYieldExecution` at `0x14003ff31`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003fafd`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003fbbd`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003fafd`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14003fbbd`
- `ntoskrnl!KeLowerIrql` at `0x14003fdda`
- `ntoskrnl!KeLowerIrql` at `0x14003fdda`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003fd6d`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140040016`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14003fd6d`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x140040016`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fd79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ffdf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040004`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040022`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040389`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400403ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fd79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ffdf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040004`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040022`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040389`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400403ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fee6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fee6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003ffd3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003fff8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004037d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400403a2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003ffd3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14003fff8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004037d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400403a2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003fe18`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003fe41`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003fe18`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003fe41`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003fb44`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003fdff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003fe24`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003fb44`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003fdff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003fe24`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003fe96`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003fe96`

## pseudocode

```c
__int64 __fastcall UlFastReceiveHttpRequest(__int64 a1, int a2, ULONG_PTR a3, __int64 a4, int a5, __int64 a6)
{
  ULONG_PTR v6; // r14
  unsigned int *v11; // rsi
  unsigned __int8 v12; // cl
  USHORT CurrentNodeNumber; // di
  _QWORD *v14; // r15
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  __int64 v17; // rax
  bool v18; // zf
  USHORT v19; // si
  __int64 v20; // rcx
  __int64 v21; // r13
  _QWORD *v22; // rsi
  __int64 v23; // r12
  _QWORD *v24; // r15
  int v25; // r8d
  __int64 v26; // r14
  __int64 v27; // rdx
  __int64 v28; // rax
  _QWORD *v29; // rsi
  _QWORD *v30; // rax
  __int64 v31; // rdx
  _QWORD *v32; // rcx
  _QWORD *v33; // rax
  __int64 v34; // rdx
  _QWORD *v35; // rcx
  __int64 v36; // r9
  int v37; // esi
  int v39; // edx
  int v40; // r8d
  __int64 v41; // rsi
  __int64 v42; // r15
  int v43; // edx
  KIRQL v44; // al
  __int64 v45; // r14
  KIRQL v46; // r12
  _QWORD *v47; // rdx
  int v48; // eax
  unsigned __int8 v49; // r14
  ULONG_PTR v50; // rdx
  int v51; // edi
  ULONG_PTR v52; // rdx
  int v53; // eax
  int v54; // eax
  __int64 v55; // rax
  __int64 RequestFromId; // rax
  int v57; // eax
  __int64 v58; // rax
  __int64 v59; // rax
  ULONG_PTR v60; // rdx
  int v61; // eax
  KIRQL v62; // [rsp+50h] [rbp-29h]
  int v63; // [rsp+54h] [rbp-25h]
  __int64 v64; // [rsp+58h] [rbp-21h] BYREF
  _QWORD *v65; // [rsp+60h] [rbp-19h]
  ULONG_PTR BugCheckParameter2; // [rsp+68h] [rbp-11h]
  __int64 v67; // [rsp+70h] [rbp-9h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+78h] [rbp-1h] BYREF
  char v69; // [rsp+D8h] [rbp+5Fh]
  unsigned __int8 v70; // [rsp+E0h] [rbp+67h]

  v69 = a2;
  v6 = *(_QWORD *)(a3 + 8);
  BugCheckParameter2 = v6;
  v64 = 0;
  v11 = (unsigned int *)a6;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_iLqqLq(a1, 0, a3, a1, a2, a3, a4, a5, a6);
  v12 = 0;
  *(_DWORD *)a6 = 0;
  *(_QWORD *)(a6 + 8) = 0;
  v70 = 0;
  if ( *(_DWORD *)(a3 + 40) != 4 || !a2 )
  {
    if ( !a1 )
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_(1032, 16, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
      if ( (unsigned __int16)UlNumberOfLanes <= 1u )
        CurrentNodeNumber = 0;
      else
        CurrentNodeNumber = KeGetCurrentNodeNumber();
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_d(1032, 17, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, CurrentNodeNumber);
      v14 = (_QWORD *)(v6 + 288);
      v65 = (_QWORD *)(v6 + 288);
      v15 = 8LL * CurrentNodeNumber;
      v16 = (_QWORD *)(*(_QWORD *)(v15 + *(_QWORD *)(a3 + 16)) + 16LL);
      if ( (_QWORD *)*v16 == v16 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v15 + *v14) + 88LL) == *(_QWORD *)(v15 + *v14) + 88LL )
          ZwYieldExecution();
        else
          v65 = (_QWORD *)(v6 + 288);
      }
      KeEnterCriticalRegion();
      v17 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v6 + 280), 0);
      v18 = *(_BYTE *)(a3 + 4) == 0;
      v67 = v17;
      if ( v18 )
      {
        while ( 1 )
        {
          memset(&LockHandle, 0, sizeof(LockHandle));
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_qqP(1032, 176, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v6, a3, &v64);
          v62 = KfRaiseIrql(2u);
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_(1032, 16, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
          if ( (unsigned __int16)UlNumberOfLanes <= 1u )
            v19 = 0;
          else
            v19 = KeGetCurrentNodeNumber();
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_d(1032, 17, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v19);
          v20 = 8LL * v19;
          v21 = *(_QWORD *)(v20 + *v14);
          v22 = (_QWORD *)(v21 + 88);
          v23 = *(_QWORD *)(v20 + *(_QWORD *)(a3 + 16));
          v24 = (_QWORD *)(v23 + 16);
          if ( (_QWORD *)*v24 == v24 && (_QWORD *)*v22 == v22 )
          {
            v37 = -1073741275;
            v26 = 0;
            goto LABEL_57;
          }
          KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v21, &LockHandle);
          v25 = *(_DWORD *)(a3 + 40);
          v63 = v25;
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          {
            WPP_SF_qqD(1032, 174, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v21, v23, v25);
            v25 = v63;
          }
          v26 = 0;
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          {
            WPP_SF_qqD(1032, 172, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v21, v23, v25);
            v25 = v63;
          }
          v27 = 0;
          if ( (_QWORD *)*v24 != v24 )
            v27 = *v24 - 1752LL;
          if ( (_QWORD *)*v22 != v22 && v25 == 1 )
            v26 = *v22 - 1752LL;
          if ( v27 )
          {
            if ( v26 )
            {
              if ( *(_QWORD *)(v27 + 1832) < *(_QWORD *)(v26 + 1832) )
                v26 = v27;
            }
            else
            {
              v26 = v27;
            }
          }
          else
          {
            v28 = 0;
            if ( v26 )
              v28 = v26;
            v26 = v28;
          }
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          {
            if ( v26 )
              v58 = *(_QWORD *)(v26 + 64);
            else
              v58 = 0;
            WPP_SF_qq(1032, 173, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v26, v58);
          }
          v29 = (_QWORD *)(v26 + 64);
          if ( !v26 )
            goto LABEL_116;
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_qqP(1032, 83, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v21, v26, *v29);
          if ( *(_DWORD *)(v26 + 1856) == 1 )
          {
            --*(_DWORD *)(v21 + 80);
          }
          else
          {
            if ( *(_DWORD *)(v26 + 1856) != 2 )
            {
              v36 = 0;
              goto LABEL_47;
            }
            --*(_DWORD *)(v21 + 84);
          }
          v30 = (_QWORD *)(v26 + 1752);
          v31 = *(_QWORD *)(v26 + 1752);
          if ( *(_QWORD *)(v31 + 8) != v26 + 1752 )
            goto LABEL_75;
          v32 = *(_QWORD **)(v26 + 1760);
          if ( (_QWORD *)*v32 != v30 )
            goto LABEL_75;
          *v32 = v31;
          *(_QWORD *)(v31 + 8) = v32;
          *v30 = 0;
          *(_QWORD *)(v26 + 1760) = 0;
          v33 = (_QWORD *)(v26 + 1768);
          v34 = *(_QWORD *)(v26 + 1768);
          if ( *(_QWORD *)(v34 + 8) != v26 + 1768 )
            goto LABEL_75;
          v35 = *(_QWORD **)(v26 + 1776);
          if ( (_QWORD *)*v35 != v33 )
            goto LABEL_75;
          *v35 = v34;
          v36 = 1;
          *(_QWORD *)(v34 + 8) = v35;
          *v33 = 0;
          *(_QWORD *)(v26 + 1776) = 0;
          *(_DWORD *)(v26 + 1856) = 0;
LABEL_47:
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          {
            WPP_SF_d(1032, 84, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v36);
LABEL_116:
            if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
            {
              if ( v26 )
                v55 = *v29;
              else
                v55 = 0;
              WPP_SF_qq(1032, 175, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v26, v55);
            }
          }
          if ( v26 )
          {
            v37 = 0;
            KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
          }
          else
          {
            KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
            v37 = -1073741275;
          }
LABEL_57:
          if ( (unsigned __int16)UlNumberOfLanes > 1u )
            UlpSynchronizeLanes(BugCheckParameter2);
          KeLowerIrql(v62);
          v64 = v26;
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          {
            if ( v26 )
              v59 = *(_QWORD *)(v26 + 64);
            else
              v59 = 0;
            WPP_SF_qqD(1032, 177, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v26, v59, v37);
          }
          if ( v37 < 0 )
          {
            v11 = (unsigned int *)a6;
            v17 = v67;
            break;
          }
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(v64 + 1704, 0);
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(*(_QWORD *)(v64 + 1712) + 72LL, 0);
          v41 = v64;
          v42 = *(_QWORD *)(v64 + 1712);
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_qqqL(1032, 183, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v64, *(_QWORD *)(v64 + 64), a3, 1);
          if ( *(_BYTE *)(v42 + 80) && (BYTE10(xmmword_1401A2C90) & 0x40) != 0 )
            WPP_SF_qLLqqZq(
              *(_QWORD *)(a3 + 8),
              v39,
              v40,
              v41,
              *(_DWORD *)(v41 + 1736),
              *(_DWORD *)(v41 + 1740),
              a3,
              *(_QWORD *)(a3 + 8),
              *(_QWORD *)(a3 + 8) + 160LL,
              v42);
          v43 = *(_DWORD *)(v41 + 1736);
          if ( v43 == 1 )
          {
            if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
              WPP_SF_qq(1032, 228, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v41, *(_QWORD *)(v41 + 64));
            v44 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(v41 + 24) + 640LL));
            v45 = *(_QWORD *)(v41 + 24);
            v46 = v44;
            if ( *(_BYTE *)(v45 + 748) && (*(_DWORD *)(v45 + 744) & 0x20) != 0 )
            {
              if ( (BYTE2(xmmword_1401A2CA0) & 8) != 0 )
                WPP_SF_qLd(
                  1043,
                  16,
                  WPP_94ca9e589e4f3da486b24c2e49372186_Traceguids,
                  v45 + 648,
                  *(_DWORD *)(v45 + 648),
                  5);
              *(_DWORD *)(v45 + 712) = 0;
            }
            KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v41 + 24) + 640LL), v46);
            if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
              WPP_SF_(1032, 229, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
            *(_DWORD *)(v41 + 1736) = 2;
            v47 = *(_QWORD **)(v42 + 104);
            if ( *v47 != v42 + 96 )
LABEL_75:
              __fastfail(3u);
            *(_QWORD *)(v41 + 1720) = v42 + 96;
            *(_QWORD *)(v41 + 1728) = v47;
            *v47 = v41 + 1720;
            *(_QWORD *)(v42 + 104) = v41 + 1720;
            if ( *(_DWORD *)(a3 + 40) == 1 && !*(_QWORD *)(v42 + 88) )
            {
              *(_QWORD *)(v42 + 88) = a3;
              v54 = _InterlockedIncrement((volatile signed __int32 *)a3);
              if ( UxDebugCheckRefcount )
              {
                if ( v54 <= -1 )
                  UlBugCheckEx(3u, a3, 0xEu, v54);
              }
            }
            if ( *(_DWORD *)(a3 + 40) == 4 )
              *(_BYTE *)(v41 + 1853) = 1;
            *(_QWORD *)(v41 + 1744) = a3;
            v48 = _InterlockedIncrement((volatile signed __int32 *)a3);
            if ( UxDebugCheckRefcount && v48 <= -1 )
              UlBugCheckEx(3u, a3, 9u, v48);
            v49 = 1;
          }
          else
          {
            v49 = 0;
            if ( (BYTE10(xmmword_1401A2C90) & 0x40) != 0 )
              WPP_SF_qqqZqL(
                *(_QWORD *)(a3 + 8),
                v43,
                v40,
                v41,
                a3,
                *(_QWORD *)(a3 + 8),
                *(_QWORD *)(a3 + 8) + 160LL,
                v42,
                *(_DWORD *)(v41 + 1736));
          }
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_d(1032, 186, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v49);
          if ( v49 )
          {
            v50 = v64 + 48;
            v51 = _InterlockedIncrement((volatile signed __int32 *)(v64 + 48));
            if ( UxDebugCheckRefcount && v51 <= -1 )
              UlBugCheckEx(3u, v50, 0x27u, v51);
            ExReleasePushLockExclusiveEx(*(_QWORD *)(v64 + 1712) + 72LL, 0);
            KeLeaveCriticalRegion();
            ExReleasePushLockExclusiveEx(v64 + 1704, 0);
            KeLeaveCriticalRegion();
            ExReleaseCacheAwarePushLockSharedEx(v67, 0);
            KeLeaveCriticalRegion();
            v11 = (unsigned int *)a6;
            UlCopyRequestToBuffer(v64, a4, v69, a6);
            v52 = v64 + 48;
            v53 = _InterlockedDecrement((volatile signed __int32 *)(v64 + 48));
            if ( UxDebugCheckRefcount && v53 <= -1 )
              UlBugCheckEx(3u, v52, 0x27u, v53);
            v12 = 1;
            v70 = 1;
            if ( !v53 )
            {
              UlpQueueFreeHttpRequest(v64);
              v12 = 1;
            }
            if ( *(_DWORD *)(a3 + 40) == 1 )
            {
              *(_QWORD *)(*(_QWORD *)(a3 + 8) + 352LL) = MEMORY[0xFFFFF78000000014];
              v12 = 1;
            }
            goto LABEL_53;
          }
          ExReleasePushLockExclusiveEx(*(_QWORD *)(v64 + 1712) + 72LL, 0);
          KeLeaveCriticalRegion();
          ExReleasePushLockExclusiveEx(v64 + 1704, 0);
          KeLeaveCriticalRegion();
          v60 = v64 + 48;
          v61 = _InterlockedDecrement((volatile signed __int32 *)(v64 + 48));
          if ( UxDebugCheckRefcount && v61 <= -1 )
            UlBugCheckEx(3u, v60, 0xCu, v61);
          v6 = BugCheckParameter2;
          v14 = v65;
          if ( !v61 )
            UlpQueueFreeHttpRequest(v64);
        }
      }
      ExReleaseCacheAwarePushLockSharedEx(v17, 0);
      KeLeaveCriticalRegion();
LABEL_52:
      v12 = 0;
      goto LABEL_53;
    }
    RequestFromId = UlGetRequestFromId(a1, a3);
    v64 = RequestFromId;
    if ( !RequestFromId )
      goto LABEL_52;
    UlStopRequestQueueTimer(RequestFromId);
    UlCopyRequestToBuffer(v64, a4, a2, a6);
    v57 = _InterlockedDecrement((volatile signed __int32 *)(v64 + 48));
    if ( UxDebugCheckRefcount && v57 <= -1 )
      UlBugCheckEx(3u, v64 + 48, 0xBu, v57);
    v12 = 1;
    v70 = 1;
    if ( !v57 )
    {
      UlpQueueFreeHttpRequest(v64);
      v12 = 1;
    }
  }
LABEL_53:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_Dd(1032, 194, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, *v11, v12);
    return v70;
  }
  return v12;
}

```

## disassembly

```asm
0x14003fa70  mov     [rsp-8+arg_0], rbx
0x14003fa75  mov     [rsp-8+arg_18], r9
0x14003fa7a  mov     [rsp-8+arg_8], edx
0x14003fa7e  push    rbp
0x14003fa7f  push    rsi
0x14003fa80  push    rdi
0x14003fa81  push    r12
0x14003fa83  push    r13
0x14003fa85  push    r14
0x14003fa87  push    r15
0x14003fa89  lea     rbp, [rsp-17h]
0x14003fa8e  sub     rsp, 90h
0x14003fa95  mov     r14, [r8+8]
0x14003fa99  mov     r15d, edx
0x14003fa9c  xor     edx, edx
0x14003fa9e  mov     [rbp+47h+BugCheckParameter2], r14
0x14003faa2  mov     [rbp+47h+var_68], rdx
0x14003faa6  mov     r12, r9
0x14003faa9  mov     rbx, r8
0x14003faac  mov     rdi, rcx
0x14003faaf  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003fab6  mov     rsi, [rbp+47h+arg_28]
0x14003faba  mov     r13d, [rbp+47h+arg_20]
0x14003fabe  jnz     loc_14004028D
0x14003fac4  xor     cl, cl
0x14003fac6  mov     [rsi], edx
0x14003fac8  mov     [rsi+8], rdx
0x14003facc  cmp     dword ptr [rbx+28h], 4
0x14003fad0  mov     [rbp+47h+arg_10], cl
0x14003fad3  jz      loc_1400401AA
0x14003fad9  test    rdi, rdi
0x14003fadc  jnz     loc_140040212
0x14003fae2  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003fae9  jnz     loc_14004040D
0x14003faef  cmp     cs:UlNumberOfLanes, 1
0x14003faf7  jbe     loc_1400401B8
0x14003fafd  call    cs:__imp_KeGetCurrentNodeNumber
0x14003fb04  nop     dword ptr [rax+rax+00h]
0x14003fb09  movzx   edi, ax
0x14003fb0c  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003fb13  jnz     loc_14004042A
0x14003fb19  movzx   eax, di
0x14003fb1c  lea     r15, [r14+120h]
0x14003fb23  mov     [rbp+47h+var_60], r15
0x14003fb27  lea     rdx, ds:0[rax*8]
0x14003fb2f  mov     rax, [rbx+10h]
0x14003fb33  mov     rcx, [rdx+rax]
0x14003fb37  add     rcx, 10h
0x14003fb3b  cmp     [rcx], rcx
0x14003fb3e  jz      loc_14003FF1D
0x14003fb44  call    cs:__imp_KeEnterCriticalRegion
0x14003fb4b  nop     dword ptr [rax+rax+00h]
0x14003fb50  mov     rcx, [r14+118h]
0x14003fb57  xor     edx, edx
0x14003fb59  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14003fb60  nop     dword ptr [rax+rax+00h]
0x14003fb65  cmp     byte ptr [rbx+4], 0
0x14003fb69  mov     [rbp+47h+var_50], rax
0x14003fb6d  jnz     loc_14003FD68
0x14003fb73  mov     edi, 1
0x14003fb78  xorps   xmm0, xmm0
0x14003fb7b  xor     eax, eax
0x14003fb7d  movups  xmmword ptr [rbp+47h+LockHandle.LockQueue.Next], xmm0
0x14003fb81  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x14003fb85  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fb8c  jnz     loc_140040449
0x14003fb92  mov     cl, 2; NewIrql
0x14003fb94  call    cs:__imp_KfRaiseIrql
0x14003fb9b  nop     dword ptr [rax+rax+00h]
0x14003fba0  mov     [rbp+47h+var_70], al
0x14003fba3  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fbaa  jnz     loc_140040475
0x14003fbb0  cmp     cs:UlNumberOfLanes, di
0x14003fbb7  jbe     loc_1400401BF
0x14003fbbd  call    cs:__imp_KeGetCurrentNodeNumber
0x14003fbc4  nop     dword ptr [rax+rax+00h]
0x14003fbc9  movzx   esi, ax
0x14003fbcc  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fbd3  jnz     loc_140040490
0x14003fbd9  movzx   eax, si
0x14003fbdc  lea     rcx, ds:0[rax*8]
0x14003fbe4  mov     rax, [r15]
0x14003fbe7  mov     r13, [rcx+rax]
0x14003fbeb  mov     rax, [rbx+10h]
0x14003fbef  lea     rsi, [r13+58h]
0x14003fbf3  mov     r12, [rcx+rax]
0x14003fbf7  lea     r15, [r12+10h]
0x14003fbfc  cmp     [r15], r15
0x14003fbff  jnz     short loc_14003FC0A
0x14003fc01  cmp     [rsi], rsi
0x14003fc04  jz      loc_14003FDB3
0x14003fc0a  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x14003fc0e  mov     rcx, r13; SpinLock
0x14003fc11  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14003fc18  nop     dword ptr [rax+rax+00h]
0x14003fc1d  mov     r8d, [rbx+28h]
0x14003fc21  mov     [rbp+47h+var_6C], r8d
0x14003fc25  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fc2c  jnz     loc_1400402E1
0x14003fc32  xor     r14d, r14d
0x14003fc35  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fc3c  jnz     loc_1400404AF
0x14003fc42  mov     rcx, [r15]
0x14003fc45  xor     r12d, r12d
0x14003fc48  cmp     rcx, r15
0x14003fc4b  mov     edx, r12d
0x14003fc4e  lea     rax, [rcx-6D8h]
0x14003fc55  cmovnz  rdx, rax
0x14003fc59  mov     rax, [rsi]
0x14003fc5c  cmp     rax, rsi
0x14003fc5f  jz      short loc_14003FC6D
0x14003fc61  cmp     r8d, edi
0x14003fc64  jnz     short loc_14003FC6D
0x14003fc66  lea     r14, [rax-6D8h]
0x14003fc6d  test    rdx, rdx
0x14003fc70  jnz     loc_140040129
0x14003fc76  test    r14, r14
0x14003fc79  mov     rax, r12
0x14003fc7c  cmovnz  rax, r14
0x14003fc80  mov     r14, rax
0x14003fc83  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fc8a  jnz     loc_1400402B5
0x14003fc90  mov     ecx, 40h ; '@'
0x14003fc95  mov     rax, r14
0x14003fc98  lea     rsi, [rcx+rax]
0x14003fc9c  test    r14, r14
0x14003fc9f  jz      loc_1400401D6
0x14003fca5  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fcac  jnz     loc_1400404DB
0x14003fcb2  mov     ecx, [r14+740h]
0x14003fcb9  sub     ecx, edi
0x14003fcbb  jnz     loc_1400401C6
0x14003fcc1  dec     dword ptr [r13+50h]
0x14003fcc5  lea     rax, [r14+6D8h]
0x14003fccc  mov     rdx, [rax]
0x14003fccf  cmp     [rdx+8], rax
0x14003fcd3  jnz     loc_14003FF16
0x14003fcd9  mov     rcx, [r14+6E0h]
0x14003fce0  cmp     [rcx], rax
0x14003fce3  jnz     loc_14003FF16
0x14003fce9  mov     [rcx], rdx
0x14003fcec  mov     [rdx+8], rcx
0x14003fcf0  mov     [rax], r12
0x14003fcf3  mov     [rax+8], r12
0x14003fcf7  lea     rax, [r14+6E8h]
0x14003fcfe  mov     rdx, [rax]
0x14003fd01  cmp     [rdx+8], rax
0x14003fd05  jnz     loc_14003FF16
0x14003fd0b  mov     rcx, [r14+6F0h]
0x14003fd12  cmp     [rcx], rax
0x14003fd15  jnz     loc_14003FF16
0x14003fd1b  mov     [rcx], rdx
0x14003fd1e  mov     r9d, edi
0x14003fd21  mov     [rdx+8], rcx
0x14003fd25  mov     [rax], r12
0x14003fd28  mov     [rax+8], r12
0x14003fd2c  mov     [r14+740h], r12d
0x14003fd33  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fd3a  jnz     loc_14004050F
0x14003fd40  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x14003fd44  test    r14, r14
0x14003fd47  jnz     loc_14004052A
0x14003fd4d  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14003fd54  nop     dword ptr [rax+rax+00h]
0x14003fd59  mov     esi, 0C0000225h
0x14003fd5e  jmp     short loc_14003FDBE
0x14003fd60  mov     rsi, [rbp+47h+arg_28]
0x14003fd64  mov     rax, [rbp+47h+var_50]
0x14003fd68  xor     edx, edx
0x14003fd6a  mov     rcx, rax
0x14003fd6d  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14003fd74  nop     dword ptr [rax+rax+00h]
0x14003fd79  call    cs:__imp_KeLeaveCriticalRegion
0x14003fd80  nop     dword ptr [rax+rax+00h]
0x14003fd85  xor     cl, cl
0x14003fd87  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003fd8e  jnz     loc_14004066F
0x14003fd94  mov     rbx, [rsp+0C0h+arg_0]
0x14003fd9c  movzx   eax, cl
0x14003fd9f  add     rsp, 90h
0x14003fda6  pop     r15
0x14003fda8  pop     r14
0x14003fdaa  pop     r13
0x14003fdac  pop     r12
0x14003fdae  pop     rdi
0x14003fdaf  pop     rsi
0x14003fdb0  pop     rbp
0x14003fdb1  retn
0x14003fdb3  xor     r12d, r12d
0x14003fdb6  mov     esi, 0C0000225h
0x14003fdbb  mov     r14d, r12d
0x14003fdbe  cmp     cs:UlNumberOfLanes, di
0x14003fdc5  jbe     short loc_14003FDD6
0x14003fdc7  mov     rcx, [rbp+47h+BugCheckParameter2]; BugCheckParameter2
0x14003fdcb  xor     r8d, r8d
0x14003fdce  mov     rdx, r13
0x14003fdd1  call    UlpSynchronizeLanes
0x14003fdd6  movzx   ecx, [rbp+47h+var_70]; NewIrql
0x14003fdda  call    cs:__imp_KeLowerIrql
0x14003fde1  nop     dword ptr [rax+rax+00h]
0x14003fde6  mov     [rbp+47h+var_68], r14
0x14003fdea  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fdf1  jnz     loc_140040337
0x14003fdf7  test    esi, esi
0x14003fdf9  js      loc_14003FD60
0x14003fdff  call    cs:__imp_KeEnterCriticalRegion
0x14003fe06  nop     dword ptr [rax+rax+00h]
0x14003fe0b  mov     rcx, [rbp+47h+var_68]
0x14003fe0f  xor     edx, edx
0x14003fe11  add     rcx, 6A8h
0x14003fe18  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003fe1f  nop     dword ptr [rax+rax+00h]
0x14003fe24  call    cs:__imp_KeEnterCriticalRegion
0x14003fe2b  nop     dword ptr [rax+rax+00h]
0x14003fe30  mov     rax, [rbp+47h+var_68]
0x14003fe34  xor     edx, edx
0x14003fe36  mov     rcx, [rax+6B0h]
0x14003fe3d  add     rcx, 48h ; 'H'
0x14003fe41  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003fe48  nop     dword ptr [rax+rax+00h]
0x14003fe4d  mov     rsi, [rbp+47h+var_68]
0x14003fe51  mov     r15, [rsi+6B0h]
0x14003fe58  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fe5f  jnz     loc_14004053E
0x14003fe65  cmp     byte ptr [r15+50h], 0
0x14003fe6a  jnz     loc_14004056E
0x14003fe70  mov     edx, [rsi+6C8h]
0x14003fe76  cmp     edx, edi
0x14003fe78  jnz     loc_14004016A
0x14003fe7e  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fe85  jnz     loc_1400405BB
0x14003fe8b  mov     rcx, [rsi+18h]
0x14003fe8f  add     rcx, 280h; SpinLock
0x14003fe96  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003fe9d  nop     dword ptr [rax+rax+00h]
0x14003fea2  mov     r14, [rsi+18h]
0x14003fea6  movzx   r12d, al
0x14003feaa  cmp     byte ptr [r14+2ECh], 0
0x14003feb2  jz      short loc_14003FED7
0x14003feb4  mov     eax, [r14+2E8h]
0x14003febb  test    al, 20h
0x14003febd  jz      short loc_14003FED7
0x14003febf  test    byte ptr cs:xmmword_1401A2CA0+2, 8
0x14003fec6  jnz     loc_1400405E2
0x14003fecc  mov     dword ptr [r14+2C8h], 0
0x14003fed7  mov     rcx, [rsi+18h]
0x14003fedb  movzx   edx, r12b; NewIrql
0x14003fedf  add     rcx, 280h; SpinLock
0x14003fee6  call    cs:__imp_KeReleaseSpinLock
0x14003feed  nop     dword ptr [rax+rax+00h]
0x14003fef2  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003fef9  jnz     loc_140040617
0x14003feff  lea     rcx, [r15+60h]
0x14003ff03  mov     dword ptr [rsi+6C8h], 2
0x14003ff0d  mov     rdx, [rcx+8]
0x14003ff11  cmp     [rdx], rcx
0x14003ff14  jz      short loc_14003FF42
0x14003ff16  mov     ecx, 3
0x14003ff1b  int     29h; Win8: RtlFailFast(ecx)
0x14003ff1d  mov     rax, [r15]
0x14003ff20  mov     rcx, [rdx+rax]
0x14003ff24  add     rcx, 58h ; 'X'
0x14003ff28  cmp     [rcx], rcx
0x14003ff2b  jnz     loc_140040120
0x14003ff31  call    cs:__imp_ZwYieldExecution
0x14003ff38  nop     dword ptr [rax+rax+00h]
0x14003ff3d  jmp     loc_14003FB44
0x14003ff42  lea     rax, [rsi+6B8h]
0x14003ff49  mov     [rax], rcx
0x14003ff4c  mov     [rax+8], rdx
0x14003ff50  mov     [rdx], rax
0x14003ff53  mov     [rcx+8], rax
0x14003ff57  cmp     [rbx+28h], edi
0x14003ff5a  jnz     short loc_14003FF67
0x14003ff5c  cmp     qword ptr [r15+58h], 0
0x14003ff61  jz      loc_1400400E7
0x14003ff67  cmp     dword ptr [rbx+28h], 4
0x14003ff6b  jz      loc_140040632
0x14003ff71  mov     [rsi+6D0h], rbx
0x14003ff78  mov     eax, edi
0x14003ff7a  lock xadd [rbx], eax
0x14003ff7e  inc     eax
0x14003ff80  cmp     cs:UxDebugCheckRefcount, 0
0x14003ff87  jnz     loc_1400400C7
0x14003ff8d  movzx   r14d, dil
0x14003ff91  test    byte ptr cs:xmmword_1401A2CA0+1, dil
0x14003ff98  jnz     loc_14004063E
0x14003ff9e  test    r14b, r14b
0x14003ffa1  jz      loc_14004036C
0x14003ffa7  mov     rdx, [rbp+47h+var_68]
0x14003ffab  add     rdx, 30h ; '0'; BugCheckParameter2
0x14003ffaf  lock xadd [rdx], edi
0x14003ffb3  inc     edi
0x14003ffb5  cmp     cs:UxDebugCheckRefcount, 0
0x14003ffbc  jnz     loc_1400400AA
0x14003ffc2  mov     rax, [rbp+47h+var_68]
0x14003ffc6  xor     edx, edx
0x14003ffc8  mov     rcx, [rax+6B0h]
0x14003ffcf  add     rcx, 48h ; 'H'
0x14003ffd3  call    cs:__imp_ExReleasePushLockExclusiveEx
  ... truncated ...
```
