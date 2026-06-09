# VidSchiCompleteFlipEntry

- ea: `0x140024d78`
- end: `0x140025b45`
- name: `VidSchiCompleteFlipEntry`
- size: `3533`
- prototype: ``
- caller_count: `11`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400248fc`
- `0x1400249c8`
- `0x140026a78`
- `0x140028938`
- `0x140028c50`
- `0x1400381e4`
- `0x14003e224`
- `0x140043944`
- `0x14004eaf0`
- `0x140056a04`
- `0x1400573cc`

## callees

- `0x14000ddfc`
- `0x14001898c`
- `0x140018c20`
- `0x14001ba84`
- `0x14001bff0`
- `0x14001c360`
- `0x14001ef60`
- `0x140020288`
- `0x140024d78`
- `0x140026130`
- `0x140026310`
- `0x140026334`
- `0x140026360`
- `0x1400265c0`
- `0x1400266d4`
- `0x140026930`
- `0x1400269d4`
- `0x1400269fc`
- `0x14002b0e0`
- `0x14002f530`
- `0x140032d84`
- `0x14003303c`
- `0x1400347a0`
- `0x14003b390`
- `0x14003e138`
- `0x14003efc4`
- `0x1400434e8`
- `0x140043f84`
- `0x140058680`
- `0x140058760`
- `0x140058ac0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400254f4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400254f4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002551a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002551a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400253d1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400253d1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14002546c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14002546c`

## pseudocode

```c
__int64 __fastcall VidSchiCompleteFlipEntry(
        struct HwQueueStagingList *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        unsigned int a7,
        _BYTE *a8)
{
  __int64 v8; // r10
  __int64 v9; // r15
  _BYTE *v10; // r8
  __int64 v13; // r13
  unsigned int v14; // r11d
  __int64 v15; // r12
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rdi
  int v19; // esi
  unsigned int v20; // edx
  unsigned int v21; // r14d
  char v22; // si
  int v23; // r15d
  struct _D3DKMT_FLIPMANAGER_AUXILIARYPRESENTINFO *FlipManagerAuxiliaryPresentInfo; // rax
  __int64 v25; // r8
  struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 **v26; // r12
  unsigned int v27; // r15d
  __int64 v28; // r14
  enum _D3DKMT_FLIPMODEL_INDEPENDENT_FLIP_STAGE v29; // edx
  void *v30; // rcx
  int v31; // eax
  __int64 v32; // r15
  unsigned int v33; // esi
  __int64 i; // rsi
  _DWORD *v35; // rcx
  unsigned int v36; // edx
  __int64 v37; // r8
  int v38; // eax
  __int64 v39; // r9
  bool j; // zf
  char v41; // cl
  int v42; // eax
  unsigned int v43; // esi
  __int64 v44; // rdx
  int v45; // eax
  char v46; // cl
  __int64 v47; // r8
  int v48; // r9d
  unsigned int v49; // r8d
  unsigned int updated; // eax
  struct _D3DKMT_FLIPMANAGER_AUXILIARYPRESENTINFO *v51; // rax
  int v52; // edx
  __int64 v53; // rcx
  __int64 v54; // r8
  int v55; // eax
  char v56; // cl
  char v57; // di
  __int64 v58; // rdx
  int v59; // eax
  __int64 v60; // rsi
  bool v61; // si
  void *v62; // rcx
  int v63; // ecx
  int v64; // eax
  int v65; // eax
  BOOL v66; // r8d
  __int64 v67; // rcx
  __int64 v68; // r9
  __int64 v69; // rcx
  __int64 v70; // rax
  unsigned __int64 v71; // rcx
  unsigned int v72; // edx
  unsigned int v73; // eax
  unsigned int v74; // edx
  char v75; // cl
  unsigned int v76; // r9d
  char v77; // cl
  int v78; // eax
  unsigned int v79; // edx
  __int64 v80; // r8
  unsigned int v81; // r9d
  char v82; // al
  __int64 v83; // rdx
  __int64 v84; // rcx
  unsigned int v85; // ecx
  void (__fastcall *v86)(_QWORD, __int64, __int64, __int64); // rax
  int v87; // [rsp+20h] [rbp-E0h]
  char v88; // [rsp+60h] [rbp-A0h]
  unsigned int v89; // [rsp+64h] [rbp-9Ch]
  unsigned int v90; // [rsp+68h] [rbp-98h]
  unsigned int v92; // [rsp+78h] [rbp-88h]
  char v93; // [rsp+7Ch] [rbp-84h]
  __int64 v94; // [rsp+80h] [rbp-80h]
  __int64 v95; // [rsp+88h] [rbp-78h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v98; // [rsp+B0h] [rbp-50h]
  unsigned int v99; // [rsp+B4h] [rbp-4Ch]
  unsigned int v100; // [rsp+B8h] [rbp-48h]
  int v101; // [rsp+C0h] [rbp-40h]
  int v102; // [rsp+C4h] [rbp-3Ch]
  _BYTE *v103; // [rsp+C8h] [rbp-38h]
  unsigned int v104; // [rsp+D0h] [rbp-30h] BYREF
  int v105; // [rsp+D4h] [rbp-2Ch]
  _QWORD v106[21]; // [rsp+D8h] [rbp-28h] BYREF

  v8 = a3;
  v9 = a4;
  v10 = a8;
  v90 = v8;
  v103 = a8;
  if ( a8 )
    *a8 = 0;
  if ( !*(_DWORD *)(a2 + 948) || !a4 )
    return 0;
  v13 = *(_QWORD *)(a2 + 8 * v8 + 3528);
  v14 = a5;
  v15 = v8;
  v92 = 0;
  v89 = 0;
  v95 = v8;
  while ( 1 )
  {
    v16 = 0;
    v17 = 1400LL * v14;
    v94 = 0;
    v18 = v17 + v9 + 120;
    v19 = 4673;
    v20 = *(_DWORD *)(v17 + v9 + 1172);
    if ( v20 > 0xC || !_bittest(&v19, v20) )
    {
      v16 = *(_QWORD *)(v18 + 1040);
      v94 = v16;
    }
    v21 = a7;
    v22 = 0;
    v88 = 0;
    v93 = 1;
    v23 = 1;
    if ( !a7 )
    {
      if ( v20 - 10 > 1 )
        goto LABEL_180;
LABEL_11:
      if ( DXGADAPTER::IsMockDriverStateEnabled(*(DXGADAPTER **)(a2 + 16))
        && *(_DWORD *)(v18 + 1052) == 11
        && (*(_DWORD *)(v18 + 1152) & 0x1000) == 0
        && !a7 )
      {
        v105 = 0;
        memset(v106, 0, 0xA0u);
        v71 = 0;
        do
        {
          v70 = 2 * v71++;
          LODWORD(v106[v70]) = 0;
          BYTE4(v106[v70]) = 0;
          *(_WORD *)((char *)&v106[v70] + 5) = 0;
          HIBYTE(v106[v70]) = 0;
          v106[v70 + 1] = 0;
        }
        while ( v71 < 0xA );
        v104 = v90;
        LockHandle.LockQueue.Lock = *(volatile PKSPIN_LOCK *)(v18 + 1192);
        LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a2;
        v72 = *(_DWORD *)LockHandle.LockQueue.Lock;
        v73 = *(_DWORD *)LockHandle.LockQueue.Lock & 0x3FF;
        j = *(_BYTE *)(a2 + 164) == 0;
        *(_DWORD *)&LockHandle.OldIrql = v73;
        if ( j )
          v74 = 0;
        else
          v74 = (v72 >> 10) & 0x3FF;
        *((_DWORD *)&LockHandle.OldIrql + 1) = v74;
        j = !_BitScanForward(&v73, v73);
        v98 = 0;
        v75 = -1;
        if ( !j )
          v75 = v73;
        v76 = v75;
        v77 = -1;
        j = !_BitScanForward((unsigned int *)&v78, v74);
        v99 = v76;
        if ( !j )
          v77 = v78;
        v100 = v77;
        if ( !VIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR::end((VIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR *)&LockHandle) )
        {
          while ( 1 )
          {
            if ( v81 < v79 )
            {
              v82 = 1;
            }
            else
            {
              v82 = 0;
              v81 = v79;
            }
            v83 = 2 * v80;
            LODWORD(v106[v83]) = v81;
            BYTE4(v106[v83]) = v82;
            v84 = v82
                ? *(_QWORD *)((v80 << 6)
                            + *(_QWORD *)(v18 + 1192)
                            + *(_DWORD *)(*(_QWORD *)(v18 + 1192) + 4LL)
                            * ((8 * *(_DWORD *)(*(_QWORD *)(v18 + 1192) + 8LL) + 231) & 0xFFFFFFF8)
                            + 32)
                : 0LL;
            v106[2 * v80 + 1] = v84;
            ++v105;
            VIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR::operator++((unsigned int *)&LockHandle);
            if ( VIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR::end((VIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR *)&LockHandle) )
              break;
            v79 = v100;
            v81 = v99;
            v80 = v98;
          }
        }
        DXGADAPTER::SetMockDriverState(*(_QWORD *)(a2 + 16), 0, &v104);
        goto LABEL_16;
      }
      if ( a7 == 9 || a7 == 6 )
      {
        FlipManagerAuxiliaryPresentInfo = GetFlipManagerAuxiliaryPresentInfo(*(struct _D3DKMT_AUXILIARYPRESENTINFO **)(v18 + 1344));
        if ( FlipManagerAuxiliaryPresentInfo )
        {
          *((_DWORD *)FlipManagerAuxiliaryPresentInfo + 13) = 1;
          if ( (byte_140086204 & 0x20) != 0 )
            McTemplateK0dq_EtwWriteTransfer(
              *(unsigned int *)(v18 + 1056),
              EventFlipManagerIFlipPresentCancel,
              v25,
              *((unsigned int *)FlipManagerAuxiliaryPresentInfo + 2),
              *(_DWORD *)(v18 + 1056));
        }
        if ( a7 != 9 )
          goto LABEL_16;
      }
      else
      {
        if ( a7 != 12 )
          goto LABEL_16;
        v51 = GetFlipManagerAuxiliaryPresentInfo(*(struct _D3DKMT_AUXILIARYPRESENTINFO **)(v18 + 1344));
        if ( v51 )
        {
          if ( v22 )
          {
            *((_DWORD *)v51 + 9) = 1;
            *((_DWORD *)v51 + 14) = 1;
            if ( (byte_140086204 & 0x20) != 0 )
              McTemplateK0qqt_EtwWriteTransfer(
                (*(_DWORD *)(v18 + 1152) >> 20) & 1,
                v52,
                v54,
                *((_DWORD *)v51 + 2),
                *(_DWORD *)(v18 + 1056),
                (*(_DWORD *)(v18 + 1152) & 0x100000) != 0);
          }
          else
          {
            *((_DWORD *)v51 + 13) = 1;
            if ( (byte_140086204 & 0x20) != 0 )
              McTemplateK0dq_EtwWriteTransfer(
                v53,
                EventFlipManagerIFlipPresentCancel,
                v54,
                *((unsigned int *)v51 + 2),
                *(_DWORD *)(v18 + 1056));
          }
        }
      }
      if ( v23 )
      {
        v27 = VidSchiDecrementPendingFlipsForFlipEntry(
                (struct _VIDSCH_GLOBAL *)a2,
                (struct _VIDSCH_PRESENT_INFO *)v13,
                (struct _VIDSCH_FLIP_QUEUE_ENTRY *)v18);
        v26 = (struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 **)(v18 + 1192);
        goto LABEL_19;
      }
LABEL_16:
      v26 = (struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 **)(v18 + 1192);
      if ( (*(_DWORD *)(v18 + 1152) & 0x10) != 0 )
        v27 = ((unsigned __int16)*(_DWORD *)*v26 | (unsigned __int16)(*(_DWORD *)*v26 >> 10)) & 0x3FF;
      else
        v27 = (1 << *(_DWORD *)(a2 + 160)) - 1;
      if ( a7 == 9 && *(_DWORD *)(v18 + 1052) == 13 )
        *(_DWORD *)(v13 + 3252) &= ~v27;
LABEL_19:
      if ( *(_QWORD *)(v13 + 120) == v18 )
        *(_QWORD *)(v13 + 120) = 0;
      if ( *(_QWORD *)(a2 + 3880) == v18 )
      {
        *(_QWORD *)(a2 + 3880) = 0;
        VidSchiSignalRegisteredEvent(a2, a2 + 2056);
      }
      *(_DWORD *)(v18 + 1052) = a7;
      v28 = *(_QWORD *)(v18 + 1176);
      if ( v28 )
      {
        v26 = (struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 **)(v18 + 1192);
        v60 = *(_QWORD *)(*(_QWORD *)(v18 + 1192) + 208LL);
        if ( v60 )
        {
          memset(&LockHandle, 0, sizeof(LockHandle));
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v28 + 16), &LockHandle);
          _InterlockedIncrement((volatile signed __int32 *)(v60 + 12));
          v62 = *(void **)(v28 + 8);
          if ( v62 )
            CRefCountedBuffer::RefCountedBufferRelease(v62);
          *(_QWORD *)(v28 + 8) = v60;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        *(_QWORD *)(v18 + 1176) = 0;
      }
      v21 = a7;
      VidSchiSignalRuntimeFenceForCompletedFlipEntry(a2, v18, a7, a1);
      VidSchiReleasePrivateDataReference((struct _VIDSCH_GLOBAL *)a2, *v26);
      VidSchiReleaseFlipFencesReference((struct _VIDSCH_GLOBAL *)a2, *v26);
      v30 = *(void **)(v18 + 1184);
      if ( v30 )
      {
        CRefCountedBuffer::RefCountedBufferRelease(v30);
        *(_QWORD *)(v18 + 1184) = 0;
      }
      if ( !a7 )
      {
        memset(&LockHandle, 0, sizeof(LockHandle));
        KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(a2 + 2104), &LockHandle);
        *(_DWORD *)(v13 + 44400) = *(_DWORD *)(v18 + 1056);
        if ( (*(_DWORD *)(v18 + 1152) & 0x20) == 0 )
        {
          *(_DWORD *)(*(_QWORD *)(v13 + 16) + 4 * v95 + 516) = *(_DWORD *)(v18 + 1056);
          *(_QWORD *)(*(_QWORD *)(v13 + 16) + 8 * v95 + 584) = *(_QWORD *)(v18 + 1128);
          *(_QWORD *)(*(_QWORD *)(v13 + 16) + 8 * v95 + 712) = *(_QWORD *)(v18 + 1112);
          *(_QWORD *)(*(_QWORD *)(v13 + 16) + 8 * v95 + 840) = *(_QWORD *)(v18 + 1144);
          *(_QWORD *)(*(_QWORD *)(v13 + 16) + 8 * v95 + 968) = *(_QWORD *)(v18 + 1136);
          *(_QWORD *)(*(_QWORD *)(v13 + 16) + 8 * v95 + 1096) = *(_QWORD *)(v18 + 1120);
        }
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      }
      v31 = *(_DWORD *)(v18 + 1152);
      if ( (v31 & 0x20) == 0 || !*(_QWORD *)(v18 + 1168) )
      {
LABEL_28:
        if ( bTracingEnabled && a7 )
        {
          j = !_BitScanForward((unsigned int *)&v45, v27);
          v32 = v94;
          v46 = -1;
          if ( !j )
            v46 = v45;
          v101 = v46;
          v102 = *(_DWORD *)(v18 + 1048);
          if ( (byte_140086201 & 1) != 0 )
          {
            if ( v94 )
            {
              v47 = *(_QWORD *)(v94 + 8);
              v48 = *(_DWORD *)(a2 + 2912);
              if ( !v47 )
                LODWORD(v47) = v94;
            }
            else
            {
              LODWORD(v47) = 0;
              LOBYTE(v48) = 0;
            }
            v33 = v90;
            v85 = 8 * *((_DWORD *)*v26 + 1) * (*((_DWORD *)*v26 + 2) + 28);
            McTemplateK0pxqqpqx_EtwWriteTransfer(
              v85,
              (unsigned int)*v26,
              v47,
              *(_QWORD *)(a2 + 16),
              *(_QWORD *)((char *)*v26 + v85 + 48),
              v90,
              *(_DWORD *)(v18 + 1056),
              v47,
              v48,
              v101);
            goto LABEL_31;
          }
        }
        else
        {
          v32 = v94;
        }
        v33 = v90;
LABEL_31:
        if ( (*(_DWORD *)*v26 & 0x3FF) != 0 )
        {
          VidSchiUnreferencePrimaryAllocations(
            a1,
            (struct _VIDSCH_GLOBAL *)a2,
            v33,
            *v26,
            *(_DWORD *)(v18 + 1080),
            *(_DWORD *)(v18 + 1084),
            1,
            a7 != 0,
            (unsigned int *)*v26 + 4);
          if ( v32 )
            VidSchiCheckPendingDeviceCommand(v32);
        }
        for ( i = 0; (unsigned int)i < *(_DWORD *)(v18 + 1092); i = (unsigned int)(i + 1) )
        {
          v35 = *(_DWORD **)(v18 + 8 * i);
          if ( (*(_DWORD *)(v18 + 1152) & 0x4000) != 0 )
          {
            if ( v35 )
            {
              VidSchiReleaseSyncObjectReference(v35);
              *(_QWORD *)(v18 + 8 * i) = 0;
            }
          }
          else if ( v35 )
          {
            --v35[200];
          }
        }
        ++v92;
        _InterlockedDecrement((volatile signed __int32 *)(v32 + 1836));
        DecrementNumberOfQueuedFlipPerSource((struct _VIDSCH_GLOBAL *)a2, v90);
        _InterlockedDecrement((volatile signed __int32 *)(a2 + 880));
        _InterlockedDecrement((volatile signed __int32 *)(v32 + 4 * v95 + 1772));
        if ( (*(_DWORD *)(v18 + 1152) & 0x10) != 0 )
          v36 = ((unsigned __int16)*(_DWORD *)*v26 | (unsigned __int16)(*(_DWORD *)*v26 >> 10)) & 0x3FF;
        else
          v36 = (1 << *(_DWORD *)(a2 + 160)) - 1;
        v15 = v95;
        v37 = 0xFFFFFFFFLL;
        j = !_BitScanForward((unsigned int *)&v38, v36);
        v39 = v36;
        if ( !j )
          v37 = (unsigned __int8)v38;
        for ( j = v36 == 0; !j; j = (_DWORD)v39 == 0 )
        {
          --*(_DWORD *)(304LL * (char)v37 + *(_QWORD *)(a2 + 8 * v95 + 3528) + 196);
          v41 = v37;
          v37 = 0xFFFFFFFFLL;
          v39 = ~(1 << v41) & (unsigned int)v39;
          j = !_BitScanForward((unsigned int *)&v42, v39);
          if ( !j )
            v37 = (unsigned __int8)v42;
        }
        v43 = v36 | v89;
        _InterlockedDecrement((volatile signed __int32 *)(v32 + 4 * v95 + 1708));
        --*(_DWORD *)(v32 + 1840);
        v89 |= v36;
        v44 = *(unsigned int *)(*(_QWORD *)(a2 + 8 * v95 + 3528) + 44488LL);
        if ( (_DWORD)v44 != -1 )
        {
          v86 = *(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(a2 + 3400);
          if ( v86 )
            v86(*(_QWORD *)(a2 + 3448), v44, v37, v39);
        }
        v9 = a4;
        *(_DWORD *)(a4 + 76) = a5;
        VidSchiUpdateFlipQueueHistory((unsigned int)(a7 != 0) + 3, a2, v90, a4, a5);
        LODWORD(v8) = v90;
        v14 = a5;
        v10 = v103;
        goto LABEL_48;
      }
      v61 = 1;
      switch ( a7 )
      {
        case 0u:
          goto LABEL_91;
        case 9u:
          v61 = v93;
          if ( v93 )
          {
LABEL_91:
            if ( !v88 )
              UpdateFlipManagerStatsOnFlipCompletion(a2, v18, v13, v90, a7);
          }
          break;
        case 6u:
          if ( (v31 & 0x100000) == 0 )
          {
            SetIndependentFlipStage((struct _VIDSCH_FLIP_QUEUE_ENTRY *)v18, v29);
            VidSchiPropagatePresentHistoryToken(
              a2,
              *(union _SLIST_HEADER **)(v18 + 1160),
              *(struct _D3DKMT_PRESENTHISTORYTOKEN **)(v18 + 1168),
              1,
              (*(_DWORD *)(v18 + 1152) & 0x40) != 0,
              0,
              0,
              *(_QWORD *)(v18 + 1176),
              (__int64)*v26,
              0,
              (v18 + 1352) & -(__int64)(*(_QWORD *)(v18 + 1352) != 0),
              1);
          }
          goto LABEL_91;
        default:
          v61 = v88 != 0;
          break;
      }
      VidSchiPropagatePresentHistoryToken(
        a2,
        *(union _SLIST_HEADER **)(v18 + 1160),
        *(struct _D3DKMT_PRESENTHISTORYTOKEN **)(v18 + 1168),
        v61,
        (*(_DWORD *)(v18 + 1152) & 0x40) != 0,
        0,
        0,
        *(_QWORD *)(v18 + 1176),
        (__int64)*v26,
        0,
        (v18 + 1352) & -(__int64)(*(_QWORD *)(v18 + 1352) != 0),
        0);
      goto LABEL_28;
    }
    if ( a7 == 9 || a7 == 6 )
    {
      v66 = 1;
      if ( v20 <= 0xC )
      {
        v65 = 4673;
        if ( _bittest(&v65, v20) )
          v66 = 0;
      }
      if ( a7 == 9 )
      {
        if ( v20 == 5 || v20 == 15 )
        {
          v93 = 1;
        }
        else
        {
          v23 = 0;
          v93 = 0;
        }
      }
      else if ( ((v20 - 5) & 0xFFFFFFF5) == 0 && v20 != 7 )
      {
        v66 = 0;
      }
      if ( v20 - 7 <= 1 )
      {
        if ( *(_BYTE *)(v18 + 1077) )
          ++*(_QWORD *)(v16 + 8 * v15 + 384);
        _InterlockedAdd((volatile signed __int32 *)(a2 + 952), 1u);
        _InterlockedAdd((volatile signed __int32 *)(v13 + 3240), 1u);
        if ( *(_DWORD *)(v18 + 1052) == 8 && !*(_BYTE *)(v18 + 1077) )
        {
          _InterlockedAdd((volatile signed __int32 *)(v16 + 4 * v15 + 1708), 1u);
          v67 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 48) + 32LL)
                                      + 8LL * *(unsigned int *)(*(_QWORD *)(v16 + 40) + 4LL))
                          + 8 * v15
                          + 88);
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 8 * v15 + 7584) + 8LL));
          _InterlockedIncrement((volatile signed __int32 *)(v67 + 8));
          _InterlockedIncrement((volatile signed __int32 *)(a2 + 880));
          IncrementNumberOfQueuedFlipPerSource((struct _VIDSCH_GLOBAL *)a2, v8);
          _InterlockedIncrement((volatile signed __int32 *)(v68 + 1836));
          _InterlockedIncrement((volatile signed __int32 *)(v68 + 4 * v15 + 1772));
        }
      }
      if ( !v66 )
      {
        v10 = v103;
LABEL_180:
        v43 = v89;
        v9 = a4;
        goto LABEL_48;
      }
      v69 = 25;
      goto LABEL_124;
    }
    if ( a7 != 12 )
      goto LABEL_180;
    if ( v20 - 2 <= 1 )
    {
LABEL_100:
      v63 = *(_DWORD *)(v18 + 1152);
      v23 = 0;
      v93 = 0;
      if ( *(_BYTE *)(a2 + 67) )
      {
        if ( (v63 & 0x20) == 0 )
          goto LABEL_180;
        if ( (v63 & 0x102000) != 0x102000 )
          goto LABEL_152;
        v22 = 1;
      }
      else if ( (v63 & 0x20) == 0 )
      {
        goto LABEL_180;
      }
      v88 = v22;
LABEL_152:
      v69 = 26;
LABEL_124:
      v87 = ((_BYTE)v14 + 1) & 0x3F;
      *(_DWORD *)(a4 + 64) = v87;
      VidSchiUpdateFlipQueueHistory(v69, a2, (unsigned int)v8, a4, v87);
      goto LABEL_11;
    }
    if ( v20 != 5 )
    {
      if ( v20 == 14 )
        goto LABEL_100;
      if ( v20 != 15 )
        goto LABEL_180;
    }
    v64 = *(_DWORD *)(v18 + 1152);
    if ( (v64 & 0x20) == 0 )
      goto LABEL_180;
    if ( (v64 & 0x2000) != 0 && *(_BYTE *)(a2 + 67) )
    {
      v22 = 1;
      v88 = 1;
      goto LABEL_152;
    }
    v43 = v89;
    v9 = a4;
    if ( v10 )
      *v10 = 1;
LABEL_48:
    if ( v14 == a6 )
      break;
    v14 = ((_BYTE)v14 + 1) & 0x3F;
    a5 = v14;
  }
  v49 = v92;
  if ( v92 )
  {
    j = !_BitScanForward((unsigned int *)&v55, v43);
    v56 = -1;
    if ( !j )
      v56 = v55;
    if ( v43 )
    {
      do
      {
        v57 = v56;
        v58 = *(int *)(304LL * (unsigned int)v56 + *(_QWORD *)(a2 + 8 * v15 + 3528) + 188);
        if ( (int)v58 > -1 && *(_DWORD *)(160 * v58 + *(_QWORD *)(a2 + 3656) + 112) == 1 )
          VidSchiTryEnterIndependentFlip(a1, (struct _VIDSCH_GLOBAL *)a2, v8, v56);
        LODWORD(v8) = v90;
        v56 = -1;
        v43 &= ~(1 << v57);
        j = !_BitScanForward((unsigned int *)&v59, v43);
        if ( !j )
          v56 = v59;
      }
      while ( v43 );
      v21 = a7;
      v49 = v92;
    }
  }
  *(_DWORD *)(a2 + 948) -= v49;
  *(_DWORD *)(v13 + 3236) -= v49;
  _InterlockedAdd((volatile signed __int32 *)(a2 + 952), -v49);
  _InterlockedAdd((volatile signed __int32 *)(v13 + 3240), -v49);
  if ( !v21 )
    VidSchiQueueDeferredVisibilityWorkItem((struct _VIDSCH_PRESENT_INFO *)v13, (struct _VIDSCH_GLOBAL *)a2);
  updated = VidSchiUpdateFlipDeviceStatus(a1, v13);
  VidSchiSignalFlipEvents(v13, updated, 0);
  return v92;
}

```

## disassembly

```asm
0x140024d78  push    rbp
0x140024d7a  push    rbx
0x140024d7b  push    rsi
0x140024d7c  push    rdi
0x140024d7d  push    r12
0x140024d7f  push    r13
0x140024d81  push    r14
0x140024d83  push    r15
0x140024d85  lea     rbp, [rsp-98h]
0x140024d8d  sub     rsp, 198h
0x140024d94  mov     rax, cs:__security_cookie
0x140024d9b  xor     rax, rsp
0x140024d9e  mov     [rbp+0D0h+var_50], rax
0x140024da5  mov     r10d, r8d
0x140024da8  mov     r15, r9
0x140024dab  mov     r8, [rbp+0D0h+arg_38]
0x140024db2  mov     rbx, rdx
0x140024db5  mov     [rsp+1D0h+var_160], r9
0x140024dba  mov     [rsp+1D0h+var_168], r10d
0x140024dbf  mov     [rbp+0D0h+var_140], rcx
0x140024dc3  mov     [rbp+0D0h+var_108], r8
0x140024dc7  test    r8, r8
0x140024dca  jnz     loc_140025827
0x140024dd0  cmp     dword ptr [rdx+3B4h], 0
0x140024dd7  jnz     short loc_140024DFF
0x140024dd9  xor     eax, eax
0x140024ddb  mov     rcx, [rbp+0D0h+var_50]
0x140024de2  xor     rcx, rsp; StackCookie
0x140024de5  call    __security_check_cookie
0x140024dea  add     rsp, 198h
0x140024df1  pop     r15
0x140024df3  pop     r14
0x140024df5  pop     r13
0x140024df7  pop     r12
0x140024df9  pop     rdi
0x140024dfa  pop     rsi
0x140024dfb  pop     rbx
0x140024dfc  pop     rbp
0x140024dfd  retn
0x140024dff  test    r9, r9
0x140024e02  jz      short loc_140024DD9
0x140024e04  mov     r13, [rdx+r10*8+0DC8h]
0x140024e0c  xor     eax, eax
0x140024e0e  mov     r11d, [rbp+0D0h+arg_20]
0x140024e15  mov     r12, r10
0x140024e18  mov     [rsp+1D0h+var_158], eax
0x140024e1c  mov     [rsp+1D0h+var_16C], eax
0x140024e20  mov     [rbp+0D0h+var_148], r10
0x140024e24  xor     r9d, r9d
0x140024e27  mov     eax, r11d
0x140024e2a  imul    rcx, rax, 578h
0x140024e31  lea     rdi, [r15+78h]
0x140024e35  mov     [rbp+0D0h+var_150], r9
0x140024e39  add     rdi, rcx
0x140024e3c  mov     esi, 1241h
0x140024e41  mov     edx, [rcx+r15+494h]
0x140024e49  cmp     edx, 0Ch
0x140024e4c  ja      loc_1400255A8
0x140024e52  bt      esi, edx
0x140024e55  jnb     loc_1400255A8
0x140024e5b  mov     r14d, [rbp+0D0h+arg_30]
0x140024e62  xor     sil, sil
0x140024e65  mov     [rsp+1D0h+var_170], sil
0x140024e6a  mov     ecx, 1
0x140024e6f  mov     [rsp+1D0h+var_154], ecx
0x140024e73  mov     r15d, ecx
0x140024e76  test    r14d, r14d
0x140024e79  jnz     loc_140025830
0x140024e7f  lea     eax, [rdx-0Ah]
0x140024e82  cmp     eax, ecx
0x140024e84  ja      loc_140025B21
0x140024e8a  mov     rcx, [rbx+10h]; this
0x140024e8e  call    ?IsMockDriverStateEnabled@DXGADAPTER@@QEAA_NXZ; DXGADAPTER::IsMockDriverStateEnabled(void)
0x140024e93  test    al, al
0x140024e95  jnz     loc_14002588F
0x140024e9b  cmp     r14d, 9
0x140024e9f  jz      short loc_140024EAB
0x140024ea1  cmp     r14d, 6
0x140024ea5  jnz     loc_14002526D
0x140024eab  mov     rcx, [rdi+540h]; struct _D3DKMT_AUXILIARYPRESENTINFO *
0x140024eb2  call    ?GetFlipManagerAuxiliaryPresentInfo@@YAPEAU_D3DKMT_FLIPMANAGER_AUXILIARYPRESENTINFO@@PEAU_D3DKMT_AUXILIARYPRESENTINFO@@@Z; GetFlipManagerAuxiliaryPresentInfo(_D3DKMT_AUXILIARYPRESENTINFO *)
0x140024eb7  test    rax, rax
0x140024eba  jnz     loc_140025983
0x140024ec0  cmp     r14d, 9
0x140024ec4  jz      loc_1400252CE
0x140024eca  cmp     r14d, 0Ch
0x140024ece  jz      loc_1400252CE
0x140024ed4  mov     eax, [rdi+480h]
0x140024eda  lea     r12, [rdi+4A8h]
0x140024ee1  test    al, 10h
0x140024ee3  jz      loc_140025148
0x140024ee9  mov     rax, [r12]
0x140024eed  mov     ecx, [rax]
0x140024eef  mov     r15d, ecx
0x140024ef2  shr     r15d, 0Ah
0x140024ef6  or      r15d, ecx
0x140024ef9  and     r15d, 3FFh
0x140024f00  cmp     r14d, 9
0x140024f04  jz      loc_1400259B6
0x140024f0a  cmp     [r13+78h], rdi
0x140024f0e  jz      loc_1400259D4
0x140024f14  cmp     [rbx+0F28h], rdi
0x140024f1b  jz      loc_1400259E1
0x140024f21  mov     [rdi+41Ch], r14d
0x140024f28  mov     r14, [rdi+498h]
0x140024f2f  test    r14, r14
0x140024f32  jnz     loc_14002547D
0x140024f38  mov     r14d, [rbp+0D0h+arg_30]
0x140024f3f  mov     rdx, rdi
0x140024f42  mov     r9, [rbp+0D0h+var_140]
0x140024f46  mov     r8d, r14d
0x140024f49  mov     rcx, rbx
0x140024f4c  call    ?VidSchiSignalRuntimeFenceForCompletedFlipEntry@@YAXPEAU_VIDSCH_GLOBAL@@PEAU_VIDSCH_FLIP_QUEUE_ENTRY@@W4_VIDSCH_FLIP_STATUS@@PEAVHwQueueStagingList@@@Z; VidSchiSignalRuntimeFenceForCompletedFlipEntry(_VIDSCH_GLOBAL *,_VIDSCH_FLIP_QUEUE_ENTRY *,_VIDSCH_FLIP_STATUS,HwQueueStagingList *)
0x140024f51  mov     rdx, [r12]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140024f55  mov     rcx, rbx; struct _VIDSCH_GLOBAL *
0x140024f58  call    ?VidSchiReleasePrivateDataReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiReleasePrivateDataReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x140024f5d  mov     rdx, [r12]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140024f61  mov     rcx, rbx; struct _VIDSCH_GLOBAL *
0x140024f64  call    ?VidSchiReleaseFlipFencesReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiReleaseFlipFencesReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x140024f69  mov     rcx, [rdi+4A0h]; Entry
0x140024f70  test    rcx, rcx
0x140024f73  jz      short loc_140024F85
0x140024f75  call    ?RefCountedBufferRelease@CRefCountedBuffer@@QEAAXXZ; CRefCountedBuffer::RefCountedBufferRelease(void)
0x140024f7a  mov     qword ptr [rdi+4A0h], 0
0x140024f85  test    r14d, r14d
0x140024f88  jz      loc_1400253B9
0x140024f8e  mov     eax, [rdi+480h]
0x140024f94  test    al, 20h
0x140024f96  jnz     loc_1400254A4
0x140024f9c  cmp     cs:bTracingEnabled, 0
0x140024fa3  jnz     loc_14002515F
0x140024fa9  mov     r15, [rbp+0D0h+var_150]
0x140024fad  mov     esi, [rsp+1D0h+var_168]
0x140024fb1  mov     r9, [r12]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140024fb5  test    dword ptr [r9], 3FFh
0x140024fbc  jnz     loc_14002521C
0x140024fc2  xor     esi, esi
0x140024fc4  cmp     [rdi+444h], esi
0x140024fca  jbe     short loc_140024FF5
0x140024fcc  test    dword ptr [rdi+480h], 4000h
0x140024fd6  mov     rcx, [rdi+rsi*8]; P
0x140024fda  jnz     loc_14002539E
0x140024fe0  test    rcx, rcx
0x140024fe3  jz      short loc_140024FEB
0x140024fe5  dec     dword ptr [rcx+320h]
0x140024feb  inc     esi
0x140024fed  cmp     esi, [rdi+444h]
0x140024ff3  jb      short loc_140024FCC
0x140024ff5  inc     [rsp+1D0h+var_158]
0x140024ff9  mov     rcx, rbx; struct _VIDSCH_GLOBAL *
0x140024ffc  lock dec dword ptr [r15+72Ch]
0x140025004  mov     edx, [rsp+1D0h+var_168]; unsigned int
0x140025008  call    ?DecrementNumberOfQueuedFlipPerSource@@YAXPEAU_VIDSCH_GLOBAL@@I@Z; DecrementNumberOfQueuedFlipPerSource(_VIDSCH_GLOBAL *,uint)
0x14002500d  lock dec dword ptr [rbx+370h]
0x140025014  mov     rax, [rbp+0D0h+var_148]
0x140025018  lock dec dword ptr [r15+rax*4+6ECh]
0x140025021  mov     eax, [rdi+480h]
0x140025027  test    al, 10h
0x140025029  jz      loc_140025134
0x14002502f  mov     rax, [r12]
0x140025033  mov     ecx, [rax]
0x140025035  mov     edx, ecx
0x140025037  shr     edx, 0Ah
0x14002503a  or      edx, ecx
0x14002503c  and     edx, 3FFh
0x140025042  mov     r12, [rbp+0D0h+var_148]
0x140025046  mov     r8d, 0FFFFFFFFh
0x14002504c  bsf     eax, edx
0x14002504f  mov     r9d, edx
0x140025052  movzx   eax, al
0x140025055  cmovnz  r8d, eax
0x140025059  test    edx, edx
0x14002505b  mov     [rsp+1D0h+var_164], 0
0x140025063  jz      short loc_1400250A4
0x140025065  movsx   rax, r8b
0x140025069  imul    rcx, rax, 130h
0x140025070  mov     rax, [rbx+r12*8+0DC8h]
0x140025078  dec     dword ptr [rcx+rax+0C4h]
0x14002507f  mov     cl, r8b
0x140025082  mov     eax, 1
0x140025087  mov     r8d, 0FFFFFFFFh
0x14002508d  shl     eax, cl
0x14002508f  not     eax
0x140025091  and     r9d, eax
0x140025094  bsf     eax, r9d
0x140025098  movzx   eax, al
0x14002509b  cmovnz  r8d, eax
0x14002509f  test    r9d, r9d
0x1400250a2  jmp     short loc_14002505B
0x1400250a4  mov     esi, [rsp+1D0h+var_16C]
0x1400250a8  or      esi, edx
0x1400250aa  lock dec dword ptr [r15+r12*4+6ACh]
0x1400250b3  dec     dword ptr [r15+730h]
0x1400250ba  mov     rax, [rbx+r12*8+0DC8h]
0x1400250c2  mov     [rsp+1D0h+var_16C], esi
0x1400250c6  mov     edx, [rax+0ADC8h]
0x1400250cc  cmp     edx, 0FFFFFFFFh
0x1400250cf  jnz     loc_140025AFC
0x1400250d5  mov     edx, [rbp+0D0h+arg_20]
0x1400250db  mov     eax, r14d
0x1400250de  mov     r15, [rsp+1D0h+var_160]
0x1400250e3  neg     eax
0x1400250e5  mov     r8d, [rsp+1D0h+var_168]
0x1400250ea  mov     r9, r15
0x1400250ed  sbb     ecx, ecx
0x1400250ef  mov     [rsp+1D0h+var_1B0], edx
0x1400250f3  neg     ecx
0x1400250f5  mov     [r15+4Ch], edx
0x1400250f9  add     ecx, 3
0x1400250fc  mov     rdx, rbx
0x1400250ff  call    ?VidSchiUpdateFlipQueueHistory@@YAXW4_VIDSCH_FLIP_QUEUE_HISTORY_EVENT@@PEAU_VIDSCH_GLOBAL@@IPEAUVIDSCH_FLIP_QUEUE@@K@Z; VidSchiUpdateFlipQueueHistory(_VIDSCH_FLIP_QUEUE_HISTORY_EVENT,_VIDSCH_GLOBAL *,uint,VIDSCH_FLIP_QUEUE *,ulong)
0x140025104  mov     r10d, [rsp+1D0h+var_168]
0x140025109  mov     r11d, [rbp+0D0h+arg_20]
0x140025110  mov     r8, [rbp+0D0h+var_108]
0x140025114  cmp     r11d, [rbp+0D0h+arg_28]
0x14002511b  jz      loc_1400251C1
0x140025121  inc     r11d
0x140025124  and     r11d, 3Fh
0x140025128  mov     [rbp+0D0h+arg_20], r11d
0x14002512f  jmp     loc_140024E24
0x140025134  mov     ecx, [rbx+0A0h]
0x14002513a  mov     edx, 1
0x14002513f  shl     edx, cl
0x140025141  dec     edx
0x140025143  jmp     loc_140025042
0x140025148  mov     ecx, [rbx+0A0h]
0x14002514e  mov     r15d, 1
0x140025154  shl     r15d, cl
0x140025157  dec     r15d
0x14002515a  jmp     loc_140024F00
0x14002515f  test    r14d, r14d
0x140025162  jz      loc_140024FA9
0x140025168  bsf     eax, r15d
0x14002516c  mov     r15, [rbp+0D0h+var_150]
0x140025170  mov     ecx, 0FFFFFFFFh
0x140025175  mov     [rsp+1D0h+var_164], 0
0x14002517d  cmovnz  ecx, eax
0x140025180  test    cs:byte_140086201, 1
0x140025187  movsx   eax, cl
0x14002518a  mov     dword ptr [rbp+0D0h+var_110], eax
0x14002518d  mov     eax, [rdi+418h]
0x140025193  mov     dword ptr [rbp+0D0h+var_110+4], eax
0x140025196  jz      loc_140024FAD
0x14002519c  test    r15, r15
0x14002519f  jz      loc_140025AA8
0x1400251a5  mov     r8, [r15+8]
0x1400251a9  mov     r9d, [rbx+0B60h]
0x1400251b0  test    r8, r8
0x1400251b3  jnz     loc_140025AAE
0x1400251b9  mov     r8, r15
0x1400251bc  jmp     loc_140025AAE
0x1400251c1  mov     r8d, [rsp+1D0h+var_158]
0x1400251c6  test    r8d, r8d
0x1400251c9  jnz     loc_1400252F4
0x1400251cf  sub     [rbx+3B4h], r8d
0x1400251d6  mov     eax, r8d
0x1400251d9  sub     [r13+0CA4h], r8d
0x1400251e0  neg     eax
0x1400251e2  lock add [rbx+3B8h], eax
0x1400251e9  lock add [r13+0CA8h], eax
0x1400251f1  test    r14d, r14d
0x1400251f4  jz      loc_14002538E
0x1400251fa  mov     rcx, [rbp+0D0h+var_140]
0x1400251fe  mov     rdx, r13
0x140025201  call    VidSchiUpdateFlipDeviceStatus
0x140025206  xor     r8d, r8d
0x140025209  mov     edx, eax
0x14002520b  mov     rcx, r13
0x14002520e  call    VidSchiSignalFlipEvents
0x140025213  mov     eax, [rsp+1D0h+var_158]
0x140025217  jmp     loc_140024DDB
0x14002521c  lea     rcx, [r9+10h]
0x140025220  test    r14d, r14d
0x140025223  mov     [rsp+1D0h+var_190], rcx; unsigned int *
0x140025228  mov     r8d, esi; unsigned int
0x14002522b  mov     rcx, [rbp+0D0h+var_140]; struct HwQueueStagingList *
0x14002522f  setnz   al
0x140025232  mov     [rsp+1D0h+var_198], al; bool
0x140025236  mov     rdx, rbx; struct _VIDSCH_GLOBAL *
0x140025239  mov     eax, [rdi+43Ch]
0x14002523f  mov     [rsp+1D0h+var_1A0], 1; bool
0x140025244  mov     [rsp+1D0h+var_1A8], eax; unsigned int
0x140025248  mov     eax, [rdi+438h]
0x14002524e  mov     [rsp+1D0h+var_1B0], eax; unsigned int
0x140025252  call    ?VidSchiUnreferencePrimaryAllocations@@YAXPEAVHwQueueStagingList@@PEAU_VIDSCH_GLOBAL@@IPEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@II_N3PEAI@Z; VidSchiUnreferencePrimaryAllocations(HwQueueStagingList *,_VIDSCH_GLOBAL *,uint,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *,uint,uint,bool,bool,uint *)
0x140025257  test    r15, r15
0x14002525a  jz      loc_140024FC2
0x140025260  mov     rcx, r15
0x140025263  call    VidSchiCheckPendingDeviceCommand
0x140025268  jmp     loc_140024FC2
0x14002526d  cmp     r14d, 0Ch
0x140025271  jnz     loc_140024ED4
0x140025277  mov     rcx, [rdi+540h]; struct _D3DKMT_AUXILIARYPRESENTINFO *
0x14002527e  call    ?GetFlipManagerAuxiliaryPresentInfo@@YAPEAU_D3DKMT_FLIPMANAGER_AUXILIARYPRESENTINFO@@PEAU_D3DKMT_AUXILIARYPRESENTINFO@@@Z; GetFlipManagerAuxiliaryPresentInfo(_D3DKMT_AUXILIARYPRESENTINFO *)
0x140025283  mov     r9, rax
0x140025286  test    rax, rax
0x140025289  jz      short loc_1400252CE
0x14002528b  test    sil, sil
0x14002528e  jz      loc_140025950
0x140025294  mov     dword ptr [rax+24h], 1
  ... truncated ...
```
