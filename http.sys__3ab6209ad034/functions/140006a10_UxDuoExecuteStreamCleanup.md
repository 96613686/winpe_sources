# UxDuoExecuteStreamCleanup

- ea: `0x140006a10`
- end: `0x1400079aa`
- name: `UxDuoExecuteStreamCleanup`
- size: `3994`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `34`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1400029a0`
- `0x140003ac0`
- `0x1400040d0`
- `0x140005410`
- `0x140005970`
- `0x140005c3c`
- `0x1400068a8`
- `0x1400069d0`
- `0x140006a10`
- `0x1400079b0`
- `0x14000a350`
- `0x140022e90`
- `0x14003bf00`
- `0x140049d08`
- `0x1400589c0`
- `0x14005dfd0`
- `0x140069310`
- `0x14006e4ec`
- `0x140090fb0`
- `0x1400d91d0`
- `0x1400d9e34`
- `0x1400db434`
- `0x1400dd410`
- `0x1400de2a8`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3c4c`
- `0x1401c4510`
- `0x1401c462c`
- `0x1401c4974`
- `0x1401ca2e4`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140006bf8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400071bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140007297`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400073d0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140006bf8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400071bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140007297`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400073d0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007090`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007090`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000705d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000705d`
- `ntoskrnl!IofCompleteRequest` at `0x140007918`
- `ntoskrnl!IofCompleteRequest` at `0x140007918`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140006ecd`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400074f8`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140006ecd`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400074f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c12`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400077eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c12`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400077eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006eae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006eae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070f6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006e7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006ff3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400070c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006e7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006ff3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400070c4`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x140007079`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x140007079`

## pseudocode

```c
void __fastcall UxDuoExecuteStreamCleanup(_QWORD *Entry)
{
  char *v1; // rsi
  __int64 v3; // r15
  __int64 v4; // rcx
  _QWORD *v5; // rax
  _QWORD *v6; // rdx
  LONG v7; // r13d
  _QWORD *v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int v12; // ecx
  __int64 v13; // r8
  __int64 v14; // rcx
  _QWORD *v15; // rbx
  _QWORD *v16; // rcx
  __int64 *v17; // rax
  ULONG_PTR v18; // rdx
  __int64 v19; // r8
  _QWORD **v20; // rbx
  _QWORD *v21; // rax
  _DWORD *v22; // rdi
  bool v23; // zf
  unsigned __int64 v24; // rbx
  void *v25; // rcx
  void *v26; // rcx
  char *v27; // rdi
  __int64 v28; // r10
  __int64 v29; // r9
  unsigned __int64 v30; // rax
  bool v31; // cc
  LONG v32; // ecx
  NTSTATUS Parcel; // ebx
  __int64 v34; // r9
  _QWORD *v35; // rcx
  _QWORD *v36; // rdi
  int v37; // eax
  __int64 v38; // rax
  KIRQL v39; // al
  __int64 v40; // r9
  KIRQL v41; // bl
  __int64 v42; // rbx
  USHORT CurrentNodeNumber; // ax
  unsigned int v44; // edx
  __int64 v45; // rdi
  KIRQL v46; // r15
  unsigned __int16 i; // cx
  __int64 v48; // rdx
  __int64 j; // rax
  __int64 v50; // rcx
  __int64 v51; // r8
  KIRQL v52; // al
  int v53; // eax
  volatile signed __int32 *v54; // rcx
  int v55; // eax
  __int64 v56; // rcx
  unsigned __int64 v57; // rbx
  __int64 v58; // rcx
  int v59; // eax
  volatile signed __int32 *v60; // rcx
  int v61; // r14d
  unsigned __int64 v62; // rbx
  NTSTATUS v63; // eax
  volatile signed __int32 *v64; // rbx
  __int64 v65; // rcx
  int v66; // eax
  unsigned __int64 v67; // rdi
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rbx
  __int64 v71; // r8
  __int64 v72; // rbx
  USHORT v73; // ax
  __int64 *v74; // rdi
  __int64 **v75; // rcx
  int v76; // eax
  int v77; // eax
  int v78; // ecx
  IRP *v79; // rcx
  volatile signed __int32 *v80; // rcx
  unsigned int v81; // edx
  char v82[4]; // [rsp+70h] [rbp-90h] BYREF
  LONG plResult; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v84; // [rsp+78h] [rbp-88h]
  __int64 v85; // [rsp+80h] [rbp-80h] BYREF
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v87[24]; // [rsp+A0h] [rbp-60h] BYREF

  v1 = (char *)Entry[6];
  v3 = *((_QWORD *)v1 + 6);
  if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_DDDL(
      1307,
      13,
      WPP_309922b680ce3405e88e422e035050e4_Traceguids,
      *(unsigned int *)(v3 + 17232),
      *((_DWORD *)v1 + 22),
      *((_DWORD *)v1 + 58),
      *((_DWORD *)v1 + 59));
  v4 = *((_QWORD *)v1 + 7);
  v5 = v1 + 56;
  if ( *(char **)(v4 + 8) != v1 + 56 )
    goto LABEL_79;
  v6 = (_QWORD *)*((_QWORD *)v1 + 8);
  if ( (_QWORD *)*v6 != v5 )
    goto LABEL_79;
  *v6 = v4;
  v7 = 0;
  *(_QWORD *)(v4 + 8) = v6;
  *v5 = 0;
  *((_QWORD *)v1 + 8) = 0;
  v8 = v1 + 72;
  v9 = *((_QWORD *)v1 + 9);
  if ( *(char **)(v9 + 8) != v1 + 72 || (v10 = (_QWORD *)*((_QWORD *)v1 + 10), (_QWORD *)*v10 != v8) )
LABEL_79:
    __fastfail(3u);
  *v10 = v9;
  *(_QWORD *)(v9 + 8) = v10;
  *v8 = 0;
  *((_QWORD *)v1 + 10) = 0;
  if ( !*(_BYTE *)(v3 + 309) && *(_QWORD *)(v3 + 32) == v3 + 32 )
  {
    if ( *(_BYTE *)(v3 + 315) )
      UxDuoUpdateIdleConnectionTimeout(v3);
    if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
      WPP_SF_d(1307, 14, WPP_03a57f2472ee35d9a08fe2d0d8024514_Traceguids, *(unsigned int *)(v3 + 17232));
    v39 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 16936));
    LOBYTE(v40) = 1;
    v41 = v39;
    UlSetBundleTimerEx(v3 + 16808, 14, 0, v40);
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 16936), v41);
  }
  if ( *(_BYTE *)(v3 + 308) )
  {
    v11 = *(unsigned int *)(v3 + 304);
    LODWORD(v11) = v11 | 0x200;
  }
  else if ( v1[246] )
  {
    v11 = 640;
  }
  else if ( *((_DWORD *)v1 + 58) || (v11 = 512, *(_DWORD *)(v3 + 17032)) )
  {
    v11 = 768;
  }
  v12 = *((_DWORD *)v1 + 10);
  v13 = *((_QWORD *)v1 + 4);
  *((_QWORD *)v1 + 4) = 0;
  if ( v12 != 3 )
  {
    v78 = v12 - 1;
    if ( !v78 )
    {
      *((_DWORD *)v1 + 10) = 6;
      goto LABEL_13;
    }
    if ( v78 != 1 )
      goto LABEL_13;
  }
  v14 = *((_QWORD *)v1 + 3);
  *((_DWORD *)v1 + 10) = 4;
  (*(void (__fastcall **)(__int64, __int64))(v13 + 8))(v14, v11);
LABEL_13:
  v15 = v1 + 280;
  while ( 1 )
  {
    v16 = (_QWORD *)*v15;
    if ( (_QWORD *)*v15 == v15 )
      break;
    if ( (_QWORD *)v16[1] != v15 )
      goto LABEL_79;
    v38 = *v16;
    if ( *(_QWORD **)(*v16 + 8LL) != v16 )
      goto LABEL_79;
    *v15 = v38;
    *(_QWORD *)(v38 + 8) = v15;
    *v16 = 0;
    v16[1] = 0;
    if ( *((int *)v16 + 4) >= 0 )
      *((_DWORD *)v16 + 4) = -1073741536;
    ((void (*)(void))UxDuoDecrementParcelPending)();
  }
  v17 = *(__int64 **)(v3 + 16984);
  if ( v17 != (__int64 *)(v3 + 16984) )
  {
    do
    {
      v74 = (__int64 *)*v17;
      if ( (char *)v17[10] == v1 )
      {
        if ( *((int *)v17 + 4) >= 0 )
          *((_DWORD *)v17 + 4) = -1073741536;
        if ( (__int64 *)v74[1] != v17 )
          goto LABEL_79;
        v75 = (__int64 **)v17[1];
        if ( *v75 != v17 )
          goto LABEL_79;
        *v75 = v74;
        v74[1] = (__int64)v75;
        *v17 = 0;
        v17[1] = 0;
        UxDuoDecrementParcelPending(v17);
      }
      v17 = v74;
    }
    while ( v74 != (__int64 *)(v3 + 16984) );
  }
  v18 = *((unsigned int *)v1 + 58);
  if ( (_DWORD)v18 )
  {
    LOBYTE(v16) = 1;
    UlTelemetryHttp2Fault(v16, v18, *((unsigned int *)v1 + 59));
    v19 = *((unsigned int *)v1 + 58);
  }
  else
  {
    v19 = 0;
  }
  if ( !v1[406] )
    UxDuoGenerateHttperr(v3, *((unsigned int *)v1 + 22), v19);
  if ( *((_DWORD *)v1 + 58)
    && !v1[246]
    && !v1[245]
    && !*(_BYTE *)(v3 + 309)
    && (unsigned __int8)UxDuoApplyServerRstDosPrevention(v3, v18, v19)
    && ((*((_DWORD *)v1 + 22) & 1) != 0 || v1[402]) )
  {
    UxDuoSendResetStream(v3, v1);
  }
  v20 = (_QWORD **)(v1 + 360);
  while ( 1 )
  {
    v21 = *v20;
    if ( *v20 == v20 )
      break;
    if ( (_QWORD **)v21[1] != v20 )
      goto LABEL_79;
    v35 = (_QWORD *)*v21;
    if ( *(_QWORD **)(*v21 + 8LL) != v21 )
      goto LABEL_79;
    *v20 = v35;
    v36 = v21 - 3;
    v35[1] = v20;
    *v21 = 0;
    v21[1] = 0;
    if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
      WPP_SF_LLL(
        1307,
        14,
        WPP_309922b680ce3405e88e422e035050e4_Traceguids,
        *(unsigned int *)(v3 + 17232),
        *((_DWORD *)v1 + 22),
        *((_DWORD *)v36 + 15));
    v18 = (ULONG_PTR)v36 + 20;
    v37 = _InterlockedDecrement((volatile signed __int32 *)v36 + 5);
    if ( UxDebugCheckRefcount && v37 <= -1 )
      UlBugCheckEx(3u, v18, 1u, v37);
    if ( !v37 )
      UxDuoFreeDataIndication(v1, v36);
  }
  v22 = (_DWORD *)_InterlockedExchange64((volatile __int64 *)v1 + 33, 0);
  if ( v22 )
  {
    UxDuoCleanupTask(v22, v18, v19);
    v23 = UxDebugDisableLookaside == 0;
    v22[4] = 1769560181;
    if ( v23 )
    {
      if ( UxCompactMode )
      {
        v42 = qword_1401A0790;
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        PplFreeToLookasideListProcessor(v42, v22, CurrentNodeNumber);
      }
      else
      {
        v24 = qword_1401A0790 + ((unsigned __int64)(unsigned int)(*v22 + 1) << 7);
        if ( !*(_BYTE *)(v24 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0790, v24 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v24 + 64), v22);
      }
    }
    else
    {
      memset(v87, 0, sizeof(v87));
      v87[10] = dword_1401A07A8;
      ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A07B8)(v22, v87);
    }
  }
  v25 = (void *)*((_QWORD *)v1 + 43);
  if ( v25 )
  {
    ExFreePoolWithTag(v25, 0);
    *((_OWORD *)v1 + 21) = 0;
  }
  v26 = (void *)*((_QWORD *)v1 + 44);
  if ( v26 )
  {
    ExFreePoolWithTag(v26, 0);
    *((_QWORD *)v1 + 44) = 0;
  }
  if ( *((_QWORD *)v1 + 55) )
  {
    UxpFreeHeaderBufferBlock(27, 1346926677);
    *((_QWORD *)v1 + 55) = 0;
  }
  if ( v1[312] )
  {
    --*(_DWORD *)(v3 + 16980);
    v1[312] = 0;
  }
  if ( (*((_DWORD *)v1 + 22) & 1) != 0 && v1[405] )
  {
    --*(_DWORD *)(*((_QWORD *)v1 + 6) + 17016LL);
    v1[405] = 0;
  }
  v85 = 0;
  if ( !*(_BYTE *)(v3 + 309) )
  {
    v27 = v1;
    v28 = *(int *)(v3 + 17020);
    if ( v1[96] )
      v27 = 0;
    v29 = *(int *)(v3 + 17028) - v28 - *(int *)(v3 + 17024);
    v30 = v29 + 0x80000000LL;
    v31 = *(_DWORD *)(v3 + 17028) < 0x100000;
    v32 = 0;
    plResult = 0;
    if ( !v31 )
    {
      v84 = 0;
      if ( v30 > 0xFFFFFFFF )
      {
        Parcel = -1073741675;
        v34 = 3221225621LL;
LABEL_46:
        UxDuoSetFault(v3, 0, 1062, v34);
LABEL_47:
        if ( !*(_DWORD *)(v3 + 17032) && (!v27 || !*((_DWORD *)v27 + 58)) )
          UxDuoSetFault(v3, 0, 1045, (unsigned int)Parcel);
        goto LABEL_50;
      }
      Parcel = 0;
      if ( v27 && !v27[399] )
      {
        v63 = RtlLongLongToLong(*((int *)v27 + 82) - (__int64)*((int *)v27 + 81) - *((int *)v27 + 80), &plResult);
        Parcel = v63;
        if ( v63 < 0 )
        {
          v34 = (unsigned int)v63;
          goto LABEL_46;
        }
        v32 = plResult;
      }
      v44 = 0;
      if ( (int)v29 >= 0x10000 )
        v44 = v29;
      if ( v32 < 0x10000 )
        v32 = 0;
      if ( v44 || v32 )
      {
        *(_DWORD *)(v3 + 17020) = v44 + v28;
        if ( v27 )
          *((_DWORD *)v27 + 80) += v32;
        v84 = v44;
        v7 = v32;
      }
      if ( Parcel >= 0 )
      {
LABEL_99:
        if ( !v84 && !v7 )
          goto LABEL_101;
        Parcel = UxDuoAllocateParcel(6, (_DWORD)v27, v3, 4, 0, (__int64)&v85);
        if ( Parcel >= 0 )
        {
          v70 = v85;
          v71 = v84;
          *(_DWORD *)(v85 + 244) = v84;
          *(_DWORD *)(v70 + 240) = v7;
          if ( v27 )
          {
            if ( (BYTE3(xmmword_1401A2CA0) & 8) != 0 )
              WPP_SF_DDdddddddd(
                v69,
                v68,
                v71,
                *(unsigned int *)(v3 + 17232),
                *((_DWORD *)v27 + 22),
                v71,
                *(_DWORD *)(v3 + 17020),
                *(_DWORD *)(v3 + 17024),
                *(_DWORD *)(v3 + 17028),
                v7,
                *((_DWORD *)v27 + 80),
                *((_DWORD *)v27 + 81),
                *((_DWORD *)v27 + 82));
          }
          else if ( (BYTE3(xmmword_1401A2CA0) & 8) != 0 )
          {
            WPP_SF_Ddddd(
              1051,
              17,
              v71,
              *(unsigned int *)(v3 + 17232),
              v71,
              *(_DWORD *)(v3 + 17020),
              *(_DWORD *)(v3 + 17024),
              *(_DWORD *)(v3 + 17028));
          }
          UxDuoSubmitParcel(v70);
          Parcel = UxDuoDispatchConnectionSends(v3);
LABEL_101:
          if ( Parcel >= 0 )
            goto LABEL_102;
        }
LABEL_71:
        if ( !*(_DWORD *)(v3 + 17032) && (!v27 || !*((_DWORD *)v27 + 58)) )
          UxDuoSetFault(v3, 0, 1045, (unsigned int)Parcel);
        goto LABEL_102;
      }
      goto LABEL_47;
    }
    if ( v30 > 0xFFFFFFFF )
    {
      Parcel = -1073741675;
LABEL_70:
      UxDuoSetFault(v3, 0, 1030, (unsigned int)Parcel);
      UxDuoVerifyFault(v3, v27, (unsigned int)Parcel);
      goto LABEL_71;
    }
    Parcel = 0;
    if ( v27 && !v27[399] )
    {
      Parcel = RtlLongLongToLong(*((int *)v27 + 82) - (__int64)*((int *)v27 + 81) - *((int *)v27 + 80), &plResult);
      if ( Parcel < 0 )
        goto LABEL_70;
      v32 = plResult;
    }
    v81 = 0;
    if ( (int)v29 >= 0 )
      v81 = v29;
    if ( v32 < 0 )
      v32 = 0;
    if ( v81 || (v84 = 0, v32) )
    {
      *(_DWORD *)(v3 + 17020) = v81 + v28;
      if ( v27 )
        *((_DWORD *)v27 + 80) += v32;
      v84 = v81;
      v7 = v32;
    }
    UxDuoVerifyFault(v3, v27, (unsigned int)Parcel);
LABEL_50:
    if ( Parcel < 0 )
      goto LABEL_71;
    goto LABEL_99;
  }
LABEL_102:
  UxDuoDispatchConnectionSends(v3);
  v45 = *((_QWORD *)v1 + 14);
  v82[0] = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (BYTE2(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_qD(1043, 13, WPP_94ca9e589e4f3da486b24c2e49372186_Traceguids, v1 + 104, *((_DWORD *)v1 + 26));
  v46 = KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)v1 + 15));
  for ( i = 0; i < *((_WORD *)&UlTimersPerBundle + *((int *)v1 + 26)); *(_DWORD *)&v1[4 * v48 + 148] = 0 )
    v48 = i++;
  for ( j = 0; j != 2; ++j )
  {
    *(_QWORD *)&v1[8 * j + 208] = -1;
    *(_DWORD *)&v1[4 * j + 224] = 0;
  }
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v45 + 48), &LockHandle);
  RtlCleanupTimerWheelEntry(*(_QWORD *)(v45 + 56), v1 + 128, v82);
  v1[204] = 0;
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  KeReleaseSpinLock(*((PKSPIN_LOCK *)v1 + 15), v46);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v45 + 64), 0xFFFFFFFF) == 1 )
  {
    v52 = KeAcquireSpinLockRaiseToDpc(&UlHotAddCommitLock);
    if ( !--UlMetronomeCount && UlMetronomeState == 2 )
      UlMetronomeState = 1;
    KeReleaseSpinLock(&UlHotAddCommitLock, v52);
  }
  v53 = _InterlockedDecrement((volatile signed __int32 *)v1 + 5);
  if ( UxDebugCheckRefcount && v53 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v1 + 20), 1u, v53);
  if ( !v53 )
  {
    if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
      WPP_SF_DDq(v50, 19, v51, *(unsigned int *)(*((_QWORD *)v1 + 6) + 17232LL), *((_DWORD *)v1 + 22), v1);
    v54 = (volatile signed __int32 *)*((_QWORD *)v1 + 6);
    *((_DWORD *)v1 + 4) = 1752782965;
    *((_DWORD *)v1 + 10) = 7;
    v55 = _InterlockedDecrement(v54 + 1);
    if ( UxDebugCheckRefcount && v55 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v54 + 1), 6u, v55);
    if ( !v55 )
      UxDuoFreeConnection((PVOID)v54);
    v56 = *((_QWORD *)v1 + 34);
    *((_QWORD *)v1 + 6) = 0;
    if ( v56 )
    {
      v76 = _InterlockedDecrement((volatile signed __int32 *)(v56 + 20));
      if ( UxDebugCheckRefcount && v76 <= -1 )
        UlBugCheckEx(3u, v56 + 20, 3u, v76);
      if ( !v76 )
        UxDuoFreeStream(v56);
      *((_QWORD *)v1 + 34) = 0;
    }
    if ( UxDebugDisableLookaside )
    {
      memset(v87, 0, sizeof(v87));
      v87[10] = dword_1401A0778;
      ((void (__fastcall *)(char *, _DWORD *))off_1401A0788)(v1, v87);
    }
    else if ( UxCompactMode )
    {
      PnlFreeToLookasideList(qword_1401A0760, v1);
    }
    else
    {
      v57 = qword_1401A0760 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v1 + 1) << 7);
      if ( !*(_BYTE *)(v57 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0760, v57 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v57 + 64), v1);
    }
  }
  switch ( *((_DWORD *)Entry + 16) )
  {
    case 9:
      v64 = (volatile signed __int32 *)Entry[9];
      if ( !v64 )
        break;
      v65 = Entry[7];
      v66 = _InterlockedDecrement(v64 + 5);
      if ( UxDebugCheckRefcount && v66 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v64 + 5), 1u, v66);
      if ( v66 )
        goto LABEL_157;
      if ( *((_QWORD *)v64 + 3) )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(v65 + 16) + 128LL))(*(_QWORD *)(v65 + 8));
        *((_QWORD *)v64 + 3) = 0;
      }
      v23 = UxDebugDisableLookaside == 0;
      *((_DWORD *)v64 + 4) = 2021218421;
      if ( !v23 )
      {
        memset(v87, 0, sizeof(v87));
        v87[10] = dword_1401A07D8;
        ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A07E8)(v64, v87);
        goto LABEL_157;
      }
      if ( !UxCompactMode )
      {
        v67 = qword_1401A07C0 + ((unsigned __int64)(unsigned int)(*v64 + 1) << 7);
        if ( !*(_BYTE *)(v67 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A07C0, v67 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v67 + 64), (PVOID)v64);
        goto LABEL_157;
      }
      PnlFreeToLookasideList(qword_1401A07C0, v64);
      Entry[9] = 0;
      break;
    case 0xA:
      v80 = (volatile signed __int32 *)Entry[9];
      if ( v80 )
      {
        v77 = _InterlockedDecrement(v80);
        if ( UxDebugCheckRefcount && v77 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)v80, 0x3Au, v77);
        if ( !v77 )
          UxDuoFreeDeclarePushParameters((PVOID)v80);
        Entry[10] = 0;
        Entry[9] = 0;
      }
      break;
    case 0x11:
      v79 = (IRP *)Entry[9];
      if ( v79 )
      {
        IofCompleteRequest(v79, 0);
LABEL_157:
        Entry[9] = 0;
      }
      break;
  }
  v58 = Entry[6];
  if ( v58 )
  {
    v59 = _InterlockedDecrement((volatile signed __int32 *)(v58 + 20));
    if ( UxDebugCheckRefcount && v59 <= -1 )
      UlBugCheckEx(3u, v58 + 20, 0x2Cu, v59);
    if ( !v59 )
      UxDuoFreeStream(v58);
    Entry[6] = 0;
  }
  v60 = (volatile signed __int32 *)Entry[7];
  if ( v60 )
  {
    v61 = _InterlockedDecrement(v60 + 1);
    if ( UxDebugCheckRefcount && v61 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v60 + 1), 0x2Cu, v61);
    if ( !v61 )
      UxDuoFreeConnection((PVOID)v60);
    Entry[7] = 0;
  }
  v23 = UxDebugDisableLookaside == 0;
  *((_DWORD *)Entry + 4) = 1769560181;
  if ( v23 )
  {
    if ( UxCompactMode )
    {
      v72 = qword_1401A0790;
      v73 = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v72, Entry, v73);
    }
    else
    {
      v62 = qword_1401A0790 + ((unsigned __int64)(unsigned int)(*(_DWORD *)Entry + 1) << 7);
      if ( !*(_BYTE *)(v62 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0790, v62 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v62 + 64), Entry);
    }
  }
  else
  {
    memset(v87, 0, sizeof(v87));
    v87[10] = dword_1401A07A8;
    ((void (__fastcall *)(_QWORD *, _DWORD *))off_1401A07B8)(Entry, v87);
  }
}

```

## disassembly

```asm
0x140006a10  push    rbp
0x140006a12  push    rsi
0x140006a13  push    r12
0x140006a15  push    r15
0x140006a17  lea     rbp, [rsp-18h]
0x140006a1c  sub     rsp, 118h
0x140006a23  mov     rax, cs:__security_cookie
0x140006a2a  xor     rax, rsp
0x140006a2d  mov     [rbp+30h+var_30], rax
0x140006a31  mov     rsi, [rcx+30h]
0x140006a35  mov     r12, rcx
0x140006a38  mov     r15, [rsi+30h]
0x140006a3c  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 8
0x140006a43  jnz     loc_1400075A3
0x140006a49  mov     rcx, [rsi+38h]
0x140006a4d  lea     rax, [rsi+38h]
0x140006a51  mov     [rsp+130h+arg_8], rbx
0x140006a59  mov     [rsp+130h+arg_10], rdi
0x140006a61  mov     [rsp+130h+arg_18], r13
0x140006a69  mov     [rsp+130h+var_20], r14
0x140006a71  cmp     [rcx+8], rax
0x140006a75  jnz     loc_140006EBF
0x140006a7b  mov     rdx, [rax+8]
0x140006a7f  cmp     [rdx], rax
0x140006a82  jnz     loc_140006EBF
0x140006a88  mov     [rdx], rcx
0x140006a8b  xor     r13d, r13d
0x140006a8e  mov     [rcx+8], rdx
0x140006a92  mov     [rax], r13
0x140006a95  mov     [rax+8], r13
0x140006a99  lea     rax, [rsi+48h]
0x140006a9d  mov     rdx, [rax]
0x140006aa0  cmp     [rdx+8], rax
0x140006aa4  jnz     loc_140006EBF
0x140006aaa  mov     rcx, [rax+8]
0x140006aae  cmp     [rcx], rax
0x140006ab1  jnz     loc_140006EBF
0x140006ab7  mov     [rcx], rdx
0x140006aba  mov     [rdx+8], rcx
0x140006abe  mov     [rax], r13
0x140006ac1  mov     [rax+8], r13
0x140006ac5  cmp     [r15+135h], r13b
0x140006acc  jnz     short loc_140006ADB
0x140006ace  lea     rax, [r15+20h]
0x140006ad2  cmp     [rax], rax
0x140006ad5  jz      loc_140006E5D
0x140006adb  cmp     [r15+134h], r13b
0x140006ae2  jz      loc_140006D91
0x140006ae8  mov     edx, [r15+130h]
0x140006aef  bts     edx, 9
0x140006af3  mov     ecx, [rsi+28h]
0x140006af6  mov     r8, [rsi+20h]
0x140006afa  mov     [rsi+20h], r13
0x140006afe  cmp     ecx, 3
0x140006b01  jnz     loc_140007760
0x140006b07  mov     rcx, [rsi+18h]
0x140006b0b  mov     dword ptr [rsi+28h], 4
0x140006b12  mov     rax, [r8+8]
0x140006b16  call    _guard_dispatch_icall
0x140006b1b  lea     rbx, [rsi+118h]
0x140006b22  mov     rcx, [rbx]
0x140006b25  cmp     rcx, rbx
0x140006b28  jnz     loc_140006DC3
0x140006b2e  lea     rbx, [r15+4258h]
0x140006b35  mov     rax, [rbx]
0x140006b38  cmp     rax, rbx
0x140006b3b  jnz     loc_140007562
0x140006b41  mov     edx, [rsi+0E8h]
0x140006b47  test    edx, edx
0x140006b49  jz      loc_140006F65
0x140006b4f  mov     r8d, [rsi+0ECh]
0x140006b56  mov     cl, 1
0x140006b58  call    UlTelemetryHttp2Fault
0x140006b5d  mov     r8d, [rsi+0E8h]
0x140006b64  cmp     [rsi+196h], r13b
0x140006b6b  jz      loc_140007777
0x140006b71  cmp     [rsi+0E8h], r13d
0x140006b78  jnz     loc_140006F0A
0x140006b7e  lea     rbx, [rsi+168h]
0x140006b85  mov     r14, 0FFFFFFFFFFFFFFFFh
0x140006b8c  mov     rax, [rbx]
0x140006b8f  cmp     rax, rbx
0x140006b92  jnz     loc_140006D29
0x140006b98  mov     rdi, r13
0x140006b9b  xchg    rdi, [rsi+108h]
0x140006ba2  test    rdi, rdi
0x140006ba5  jz      short loc_140006C04
0x140006ba7  mov     rcx, rdi
0x140006baa  call    UxDuoCleanupTask
0x140006baf  cmp     cs:UxDebugDisableLookaside, r13b
0x140006bb6  mov     dword ptr [rdi+10h], 69795875h
0x140006bbd  jnz     loc_1400077B7
0x140006bc3  cmp     cs:UxCompactMode, r13b
0x140006bca  jnz     loc_140006EC6
0x140006bd0  mov     ebx, [rdi]
0x140006bd2  mov     r8, cs:qword_1401A0790
0x140006bd9  inc     ebx
0x140006bdb  shl     rbx, 7
0x140006bdf  add     rbx, r8
0x140006be2  movzx   eax, byte ptr [rbx+0B0h]
0x140006be9  test    al, al
0x140006beb  jz      loc_1400075E0
0x140006bf1  mov     rdx, rdi; Entry
0x140006bf4  lea     rcx, [rbx+40h]; Lookaside
0x140006bf8  call    cs:__imp_ExFreeToLookasideListEx
0x140006bff  nop     dword ptr [rax+rax+00h]
0x140006c04  mov     rcx, [rsi+158h]; P
0x140006c0b  test    rcx, rcx
0x140006c0e  jz      short loc_140006C28
0x140006c10  xor     edx, edx; Tag
0x140006c12  call    cs:__imp_ExFreePoolWithTag
0x140006c19  nop     dword ptr [rax+rax+00h]
0x140006c1e  xorps   xmm0, xmm0
0x140006c21  movups  xmmword ptr [rsi+150h], xmm0
0x140006c28  mov     rcx, [rsi+160h]; P
0x140006c2f  test    rcx, rcx
0x140006c32  jnz     loc_1400077E9
0x140006c38  mov     r8, [rsi+1B8h]
0x140006c3f  test    r8, r8
0x140006c42  jnz     loc_140007803
0x140006c48  mov     edx, 0FFFFFFFFh
0x140006c4d  cmp     [rsi+138h], r13b
0x140006c54  jnz     loc_14000781E
0x140006c5a  mov     eax, [rsi+58h]
0x140006c5d  test    al, 1
0x140006c5f  jz      short loc_140006C7B
0x140006c61  cmp     [rsi+195h], r13b
0x140006c68  jz      short loc_140006C7B
0x140006c6a  mov     rax, [rsi+30h]
0x140006c6e  add     [rax+4278h], edx
0x140006c74  mov     [rsi+195h], r13b
0x140006c7b  mov     [rbp+30h+var_B0], r13
0x140006c7f  cmp     [r15+135h], r13b
0x140006c86  jnz     loc_140006FC4
0x140006c8c  movsxd  rcx, dword ptr [r15+4284h]
0x140006c93  mov     rdi, rsi
0x140006c96  cmp     [rsi+60h], r13b
0x140006c9a  mov     r9, rcx
0x140006c9d  movsxd  rax, dword ptr [r15+4280h]
0x140006ca4  movsxd  r10, dword ptr [r15+427Ch]
0x140006cab  cmovnz  rdi, r13
0x140006caf  sub     r9, r10
0x140006cb2  sub     r9, rax
0x140006cb5  mov     eax, 80000000h
0x140006cba  add     rax, r9
0x140006cbd  cmp     ecx, 100000h
0x140006cc3  mov     ecx, r13d
0x140006cc6  mov     [rsp+130h+plResult], ecx
0x140006cca  jl      loc_140006DFF
0x140006cd0  mov     [rsp+130h+var_B8], r13d
0x140006cd5  cmp     rax, rdx
0x140006cd8  jbe     loc_140006F6D
0x140006cde  mov     ebx, 0C0000095h
0x140006ce3  mov     r9d, ebx
0x140006ce6  mov     r8d, 426h
0x140006cec  xor     edx, edx
0x140006cee  mov     rcx, r15
0x140006cf1  call    UxDuoSetFault
0x140006cf6  cmp     dword ptr [r15+4288h], 0
0x140006cfe  jnz     short loc_140006D1C
0x140006d00  test    rdi, rdi
0x140006d03  jnz     loc_14000783C
0x140006d09  mov     r9d, ebx
0x140006d0c  xor     edx, edx
0x140006d0e  mov     r8d, 415h
0x140006d14  mov     rcx, r15
0x140006d17  call    UxDuoSetFault
0x140006d1c  test    ebx, ebx
0x140006d1e  jns     loc_140006FA8
0x140006d24  jmp     loc_140006E2E
0x140006d29  cmp     [rax+8], rbx
0x140006d2d  jnz     loc_140006EBF
0x140006d33  mov     rcx, [rax]
0x140006d36  cmp     [rcx+8], rax
0x140006d3a  jnz     loc_140006EBF
0x140006d40  mov     [rbx], rcx
0x140006d43  lea     rdi, [rax-18h]
0x140006d47  mov     [rcx+8], rbx
0x140006d4b  mov     [rax], r13
0x140006d4e  mov     [rax+8], r13
0x140006d52  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 8
0x140006d59  jnz     loc_140007787
0x140006d5f  lea     rdx, [rdi+14h]; BugCheckParameter2
0x140006d63  mov     eax, r14d
0x140006d66  lock xadd [rdx], eax
0x140006d6a  dec     eax
0x140006d6c  cmp     cs:UxDebugCheckRefcount, r13b
0x140006d73  jnz     loc_140006EED
0x140006d79  test    eax, eax
0x140006d7b  jnz     loc_140006B8C
0x140006d81  mov     rdx, rdi
0x140006d84  mov     rcx, rsi
0x140006d87  call    UxDuoFreeDataIndication
0x140006d8c  jmp     loc_140006B8C
0x140006d91  cmp     [rsi+0F6h], r13b
0x140006d98  jnz     loc_140007756
0x140006d9e  cmp     [rsi+0E8h], r13d
0x140006da5  jnz     short loc_140006DB9
0x140006da7  mov     edx, 200h
0x140006dac  cmp     [r15+4288h], r13d
0x140006db3  jz      loc_140006AF3
0x140006db9  mov     edx, 300h
0x140006dbe  jmp     loc_140006AF3
0x140006dc3  cmp     [rcx+8], rbx
0x140006dc7  jnz     loc_140006EBF
0x140006dcd  mov     rax, [rcx]
0x140006dd0  cmp     [rax+8], rcx
0x140006dd4  jnz     loc_140006EBF
0x140006dda  mov     [rbx], rax
0x140006ddd  mov     [rax+8], rbx
0x140006de1  mov     [rcx], r13
0x140006de4  mov     [rcx+8], r13
0x140006de8  cmp     [rcx+10h], r13d
0x140006dec  jl      short loc_140006DF5
0x140006dee  mov     dword ptr [rcx+10h], 0C0000120h
0x140006df5  call    UxDuoDecrementParcelPending
0x140006dfa  jmp     loc_140006B22
0x140006dff  cmp     rax, rdx
0x140006e02  jbe     loc_14000784E
0x140006e08  mov     ebx, 0C0000095h
0x140006e0d  mov     r9d, ebx
0x140006e10  mov     r8d, 406h
0x140006e16  xor     edx, edx
0x140006e18  mov     rcx, r15
0x140006e1b  call    UxDuoSetFault
0x140006e20  mov     r8d, ebx
0x140006e23  mov     rdx, rdi
0x140006e26  mov     rcx, r15
0x140006e29  call    UxDuoVerifyFault
0x140006e2e  cmp     dword ptr [r15+4288h], 0
0x140006e36  jnz     loc_140006FC4
0x140006e3c  test    rdi, rdi
0x140006e3f  jnz     loc_14000789E
0x140006e45  mov     r9d, ebx
0x140006e48  xor     edx, edx
0x140006e4a  mov     r8d, 415h
0x140006e50  mov     rcx, r15
0x140006e53  call    UxDuoSetFault
0x140006e58  jmp     loc_140006FC4
0x140006e5d  cmp     [r15+13Bh], r13b
0x140006e64  jnz     loc_140007727
0x140006e6a  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 8
0x140006e71  jnz     loc_140007734
0x140006e77  lea     rcx, [r15+4228h]; SpinLock
0x140006e7e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006e85  nop     dword ptr [rax+rax+00h]
0x140006e8a  lea     rcx, [r15+41A8h]
0x140006e91  mov     r9b, 1
0x140006e94  xor     r8d, r8d
0x140006e97  mov     edx, 0Eh
0x140006e9c  movzx   ebx, al
0x140006e9f  call    UlSetBundleTimerEx
0x140006ea4  movzx   edx, bl; NewIrql
0x140006ea7  lea     rcx, [r15+4228h]; SpinLock
0x140006eae  call    cs:__imp_KeReleaseSpinLock
0x140006eb5  nop     dword ptr [rax+rax+00h]
0x140006eba  jmp     loc_140006ADB
0x140006ebf  mov     ecx, 3
0x140006ec4  int     29h; Win8: RtlFailFast(ecx)
0x140006ec6  mov     rbx, cs:qword_1401A0790
0x140006ecd  call    cs:__imp_KeGetCurrentNodeNumber
0x140006ed4  nop     dword ptr [rax+rax+00h]
0x140006ed9  movzx   r8d, ax
0x140006edd  mov     rdx, rdi
0x140006ee0  mov     rcx, rbx
0x140006ee3  call    PplFreeToLookasideListProcessor
0x140006ee8  jmp     loc_140006C04
0x140006eed  cmp     eax, r14d
0x140006ef0  jg      loc_140006D79
0x140006ef6  movsxd  r9, eax; BugCheckParameter4
0x140006ef9  mov     ecx, 3; BugCheckParameter1
0x140006efe  mov     r8d, 1; BugCheckParameter3
0x140006f04  call    UlBugCheckEx
0x140006f0a  cmp     [rsi+0F6h], r13b
0x140006f11  jnz     loc_140006B7E
0x140006f17  cmp     [rsi+0F5h], r13b
0x140006f1e  jnz     loc_140006B7E
0x140006f24  cmp     [r15+135h], r13b
0x140006f2b  jnz     loc_140006B7E
0x140006f31  mov     rcx, r15
0x140006f34  call    UxDuoApplyServerRstDosPrevention
0x140006f39  test    al, al
0x140006f3b  jz      loc_140006B7E
0x140006f41  mov     eax, [rsi+58h]
0x140006f44  test    al, 1
0x140006f46  jnz     short loc_140006F55
0x140006f48  cmp     [rsi+192h], r13b
0x140006f4f  jz      loc_140006B7E
0x140006f55  mov     rdx, rsi
0x140006f58  mov     rcx, r15
0x140006f5b  call    UxDuoSendResetStream
0x140006f60  jmp     loc_140006B7E
0x140006f65  mov     r8d, r13d
0x140006f68  jmp     loc_140006B64
0x140006f6d  xor     ebx, ebx
0x140006f6f  test    rdi, rdi
0x140006f72  jnz     loc_1400072E8
0x140006f78  xor     edx, edx
0x140006f7a  cmp     r9d, 10000h
0x140006f81  cmovge  edx, r9d
  ... truncated ...
```
