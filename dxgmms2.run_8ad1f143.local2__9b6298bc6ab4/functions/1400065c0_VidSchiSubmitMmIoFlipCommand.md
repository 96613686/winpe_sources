# VidSchiSubmitMmIoFlipCommand

- ea: `0x1400065c0`
- end: `0x1400072cb`
- name: `VidSchiSubmitMmIoFlipCommand`
- size: `3339`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400dd5f0`
- `0x1400dd830`

## callees

- `0x1400065c0`
- `0x1400072d4`
- `0x1400073a4`
- `0x1400074a0`
- `0x1400074e4`
- `0x1400075b0`
- `0x14000880c`
- `0x14000eda0`
- `0x140016b74`
- `0x140018e90`
- `0x14001978c`
- `0x14001ca80`
- `0x14001ef60`
- `0x140026360`
- `0x140026930`
- `0x140026a78`
- `0x1400281b0`
- `0x1400333d0`
- `0x1400381e4`
- `0x14003d638`
- `0x140043944`
- `0x140058760`
- `0x1400587c0`
- `0x140058ac0`
- `0x1400f8aa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14000666e`
- `ntoskrnl!KfRaiseIrql` at `0x14000666e`
- `ntoskrnl!KeLowerIrql` at `0x140006bc9`
- `ntoskrnl!KeLowerIrql` at `0x140006cd3`
- `ntoskrnl!KeLowerIrql` at `0x140007016`
- `ntoskrnl!KeLowerIrql` at `0x140006bc9`
- `ntoskrnl!KeLowerIrql` at `0x140006cd3`
- `ntoskrnl!KeLowerIrql` at `0x140007016`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140006695`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140006695`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140006bb2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140006cc4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007007`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140006bb2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140006cc4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007007`
- `watchdog!WdLogSingleEntry5` at `0x1400071d9`
- `watchdog!WdLogSingleEntry5` at `0x1400071d9`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400071b5`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VidSchiSubmitMmIoFlipCommand(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // r13
  __int64 v4; // rsi
  __int64 v5; // r12
  __int64 v6; // r14
  unsigned int v7; // ebx
  __int64 v8; // rbx
  __int64 v9; // r14
  int v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdi
  bool v15; // zf
  unsigned __int16 v16; // r8
  unsigned int v17; // r8d
  int v18; // eax
  char v19; // cl
  _DWORD *v20; // rbx
  __int64 v21; // rcx
  int *v22; // rbx
  int v23; // edx
  int v24; // edx
  int v25; // ecx
  struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *v26; // r10
  int *v27; // rdx
  char v28; // cl
  int v29; // ecx
  int v30; // eax
  int v31; // ecx
  __int64 v32; // rax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // ecx
  bool v37; // cl
  unsigned int **v38; // r10
  int v39; // eax
  char v40; // r9
  unsigned int *v41; // rax
  unsigned int v42; // edx
  unsigned int v43; // r8d
  unsigned int v44; // edx
  int v45; // eax
  char v46; // cl
  int v47; // eax
  unsigned int v48; // r10d
  unsigned int v49; // eax
  __int64 v50; // rcx
  unsigned int v51; // eax
  int v52; // r10d
  unsigned int v53; // r9d
  int v54; // r11d
  unsigned int v55; // edx
  unsigned __int64 v56; // r10
  unsigned __int64 v57; // rdx
  struct VIDMM_ALLOC *v58; // rcx
  void (__fastcall *v59)(_QWORD, _QWORD); // rax
  __int64 v60; // rax
  int v61; // edx
  int v62; // ecx
  __int64 v63; // rcx
  int v64; // eax
  char v65; // di
  __int64 v66; // rax
  void (__fastcall *v67)(_QWORD, _QWORD); // rax
  int v68; // eax
  unsigned int v69; // eax
  __int64 v70; // rcx
  __int64 v71; // [rsp+20h] [rbp-99h]
  __int64 v72; // [rsp+28h] [rbp-91h]
  int v73; // [rsp+40h] [rbp-79h]
  unsigned int **v74; // [rsp+48h] [rbp-71h]
  struct _VIDSCH_PRESENT_INFO *v75; // [rsp+50h] [rbp-69h]
  int v76; // [rsp+58h] [rbp-61h]
  __int64 v77; // [rsp+60h] [rbp-59h]
  __int64 v78; // [rsp+68h] [rbp-51h] BYREF
  _QWORD v79[2]; // [rsp+70h] [rbp-49h] BYREF
  char v80; // [rsp+80h] [rbp-39h]
  int v81; // [rsp+84h] [rbp-35h]
  __int64 v82; // [rsp+88h] [rbp-31h]
  _QWORD v83[2]; // [rsp+90h] [rbp-29h] BYREF
  unsigned int v84; // [rsp+A0h] [rbp-19h]
  unsigned int v85; // [rsp+A4h] [rbp-15h]
  int v86; // [rsp+A8h] [rbp-11h]
  unsigned int v87; // [rsp+ACh] [rbp-Dh]
  unsigned int v88; // [rsp+B0h] [rbp-9h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B8h] [rbp-1h] BYREF
  unsigned int v90; // [rsp+120h] [rbp+67h] BYREF
  char v91; // [rsp+128h] [rbp+6Fh] BYREF
  KIRQL NewIrql; // [rsp+130h] [rbp+77h]
  BOOL v93; // [rsp+138h] [rbp+7Fh]

  v1 = *(_QWORD *)(a1 + 88);
  v82 = v1;
  v3 = *(_QWORD *)(v1 + 104);
  v77 = v3;
  v4 = *(_QWORD *)(v3 + 40);
  if ( (*(_BYTE *)(v4 + 3364) & 1) == 0 && !*(_DWORD *)(v4 + 3340) && !*(_BYTE *)(v3 + 212) )
  {
    v5 = *(unsigned int *)(a1 + 168);
    v6 = *(_QWORD *)(v4 + 8 * v5 + 3528);
    v75 = (struct _VIDSCH_PRESENT_INFO *)v6;
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v3 + 208), 0, 0) )
    {
      if ( (*(_DWORD *)(v3 + 56) & 2) != 0 || *(int *)(a1 + 400) >= 4 || *(_BYTE *)(v4 + 164) )
        VidSchIsVSyncEnabled((struct _VIDSCH_GLOBAL *)v4, v5);
      v7 = *(_DWORD *)(*(_QWORD *)(v4 + 8 * v5 + 3528) + 44488LL);
      if ( v7 != -1 )
      {
        v67 = *(void (__fastcall **)(_QWORD, _QWORD))(v4 + 3384);
        if ( v67 )
          v67(*(_QWORD *)(v4 + 3448), v7);
      }
      NewIrql = KfRaiseIrql(2u);
      memset(&LockHandle, 0, sizeof(LockHandle));
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 2096), &LockHandle);
      v78 = v4;
      v81 = 2;
      v80 = 0;
      v79[1] = v79;
      v79[0] = v79;
      if ( (*(_DWORD *)(a1 + 64) & 0x20) != 0 )
      {
        HwQueueStagingList::ProcessHwQueues((HwQueueStagingList *)&v78, 0);
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        KeLowerIrql(NewIrql);
        VidSchiProcessCompletedQueuePacket((struct _VIDSCH_QUEUE_PACKET *)a1);
      }
      else
      {
        if ( *(_QWORD *)(a1 + 408) - *(_QWORD *)(v3 + 8 * v5 + 384) <= (unsigned __int64)(unsigned int)(64 - *(_DWORD *)(v6 + 3236)) )
        {
          v8 = v6;
          v91 = 0;
          v93 = *(_DWORD *)(v6 + 4) == 3 || !*(_DWORD *)(a1 + 404) && (*(_DWORD *)(a1 + 280) & 0x10000000) != 0;
          v9 = *(_QWORD *)(v6 + 32);
          VidSchiValidateDwmReferencedPlanes(
            (struct _VIDSCH_GLOBAL *)v4,
            v5,
            (*(_DWORD *)(a1 + 72) & 0x800000) != 0,
            (const struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)(a1 + 880));
          if ( *(_BYTE *)(*(_QWORD *)(v3 + 48) + 2632LL) )
            VidSchiUpdateVSyncMultiplier(
              (struct _VIDSCH_GLOBAL *)v4,
              v5,
              (struct _VIDSCH_PRESENT_INFO *)v8,
              (struct VIDSCH_SUBMIT_DATA2 *)(a1 + 280));
          v10 = *(_DWORD *)(a1 + 408) - *(_DWORD *)(v3 + 8 * v5 + 384);
          v11 = v82;
          LODWORD(v3) = ((_BYTE)v10 + (unsigned __int8)*(_DWORD *)(v9 + 56)) & 0x3F;
          v76 = v10;
          v12 = *(_QWORD *)(v4 + 776);
          v13 = *(unsigned int *)(v82 + 88);
          v14 = v9 + 1400LL * (unsigned int)v3 + 120;
          if ( (unsigned int)v13 < *(_DWORD *)(v4 + 848) )
            v12 += 8 * v13;
          v15 = *(_DWORD *)(v14 + 1052) == 8;
          v16 = *(_WORD *)(*(_QWORD *)v12 + 6LL);
          v90 = v16;
          if ( v15 )
          {
            v22 = (int *)(v14 + 1152);
            *(_QWORD *)(v14 + 8LL * *(unsigned int *)(v14 + 1092)) = v82;
            *(_QWORD *)(v14 + 8LL * *(unsigned int *)(v14 + 1092) + 520) = *(_QWORD *)(v11 + 160);
            v66 = *(_QWORD *)(v11 + 104);
            ++*(_DWORD *)(v14 + 1092);
            *(_QWORD *)(v14 + 1040) = v66;
            ++*(_DWORD *)(v11 + 800);
            *(_DWORD *)(v14 + 1084) |= 1 << v16;
          }
          else
          {
            ++*(_DWORD *)(v4 + 948);
            ++*(_DWORD *)(v77 + 1840);
            ++*(_DWORD *)(v11 + 800);
            ++*(_DWORD *)(v8 + 3236);
            if ( (*(_DWORD *)(a1 + 280) & 0x800000) != 0 )
              v17 = ((unsigned __int16)*(_DWORD *)(a1 + 880) | (unsigned __int16)(*(_DWORD *)(a1 + 880) >> 10)) & 0x3FF;
            else
              v17 = (1 << *(_DWORD *)(v4 + 160)) - 1;
            while ( 1 )
            {
              v15 = !_BitScanForward((unsigned int *)&v18, v17);
              v19 = -1;
              if ( !v15 )
                v19 = v18;
              if ( !v17 )
                break;
              ++*(_DWORD *)(304LL * v19 + *(_QWORD *)(v4 + 8 * v5 + 3528) + 196);
              v17 &= ~(1 << v19);
            }
            v20 = *(_DWORD **)(v14 + 1192);
            v74 = (unsigned int **)(v14 + 1192);
            memset((void *)(v9 + 1400LL * (unsigned int)v3 + 120), 0, 0x578u);
            *(_QWORD *)(v14 + 1192) = v20;
            memset(v20 + 6, 0, (unsigned int)(v20[1] * (72 * v20[2] + 224)));
            v21 = v82;
            v22 = (int *)(v14 + 1152);
            *(_QWORD *)v14 = v82;
            *(_QWORD *)(v14 + 1040) = *(_QWORD *)(v21 + 104);
            *(_DWORD *)(v14 + 1048) = *(_DWORD *)(a1 + 112);
            *(_DWORD *)(v14 + 1056) = *(_DWORD *)(a1 + 392);
            *(_QWORD *)(v14 + 520) = *(_QWORD *)(v21 + 160);
            *(_BYTE *)(v14 + 1076) = (*(_DWORD *)(a1 + 280) & 0x10) != 0;
            LODWORD(v21) = *(_DWORD *)(v14 + 1152)
                         ^ ((unsigned __int8)*(_DWORD *)(v14 + 1152)
                          ^ (unsigned __int8)(*(_DWORD *)(a1 + 72) >> 19))
                         & 0x10;
            *(_DWORD *)(v14 + 1152) = v21;
            v23 = v21 ^ (v21 ^ (*(_DWORD *)(a1 + 280) >> 20)) & 0x400;
            *(_DWORD *)(v14 + 1152) = v23;
            *(_DWORD *)(v14 + 1152) = v23 ^ (v23 ^ (*(_DWORD *)(a1 + 280) >> 20)) & 0x800;
            if ( !v76 )
              *(_QWORD *)(v14 + 1064) = ++*(_QWORD *)(v9 + 88);
            v24 = *v22;
            v25 = *(_DWORD *)(a1 + 640);
            *(_DWORD *)(v14 + 1200) = v25;
            if ( (v24 & 0x400) != 0 )
            {
              v62 = v25 - 1;
              if ( v62 )
              {
                if ( v62 == 1 )
                {
                  *(_OWORD *)(v14 + 1204) = *(_OWORD *)(a1 + 644);
                  *(_OWORD *)(v14 + 1220) = *(_OWORD *)(a1 + 660);
                  *(_OWORD *)(v14 + 1236) = *(_OWORD *)(a1 + 676);
                  *(_OWORD *)(v14 + 1252) = *(_OWORD *)(a1 + 692);
                  *(_QWORD *)(v14 + 1268) = *(_QWORD *)(a1 + 708);
                }
              }
              else
              {
                *(_OWORD *)(v14 + 1204) = *(_OWORD *)(a1 + 644);
                *(_OWORD *)(v14 + 1216) = *(_OWORD *)(a1 + 656);
              }
            }
            if ( (v24 & 0x800) != 0 )
            {
              *(_OWORD *)(v14 + 1276) = *(_OWORD *)(a1 + 716);
              *(_OWORD *)(v14 + 1292) = *(_OWORD *)(a1 + 732);
            }
            _VIDSCH_FLIP_QUEUE_ENTRY::FillVmState(
              (_VIDSCH_FLIP_QUEUE_ENTRY *)(v9 + 1400LL * (unsigned int)v3 + 120),
              (struct VIDSCH_SUBMIT_DATA2 *)(a1 + 280));
            memmove(*(void **)(v14 + 1192), (const void *)(a1 + 880), *(unsigned int *)(a1 + 892));
            *(_DWORD *)(a1 + 896) = 0;
            VidSchiAcquirePrivateDataReference(
              (struct _VIDSCH_GLOBAL *)v4,
              *(struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 **)(v14 + 1192));
            VidSchiReleasePrivateDataReference((struct _VIDSCH_GLOBAL *)v4, v26);
            VidSchiAcquireFlipFencesReference(
              (struct _VIDSCH_GLOBAL *)v4,
              *(struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 **)(v14 + 1192));
            v27 = (int *)(a1 + 280);
            v28 = v90;
            *(_DWORD *)(v14 + 1080) = *(_DWORD *)(a1 + 416);
            *(_DWORD *)(v14 + 1084) = 1 << v28;
            v29 = *v22 ^ (*v22 ^ (*(_DWORD *)(a1 + 280) >> 19)) & 1;
            *v22 = v29;
            v30 = v29 ^ ((unsigned __int8)v29 ^ (unsigned __int8)(*(_DWORD *)(a1 + 280) >> 19)) & 2;
            *v22 = v30;
            v31 = v30 ^ ((unsigned __int8)v30 ^ (unsigned __int8)(*(_DWORD *)(a1 + 280) >> 19)) & 4;
            *v22 = v31;
            *v22 = v31 ^ ((unsigned __int8)v31 ^ (unsigned __int8)(*(_DWORD *)(a1 + 280) >> 19)) & 8;
            *(_QWORD *)(v14 + 1176) = *(_QWORD *)(a1 + 304);
            v32 = *(_QWORD *)(a1 + 312);
            *(_QWORD *)(v14 + 1184) = v32;
            if ( v32 )
              _InterlockedAdd((volatile signed __int32 *)(v32 + 12), 1u);
            v33 = *v27;
            *(_DWORD *)(v14 + 1092) = 1;
            if ( (v33 & 0x400) != 0 )
            {
              *(_DWORD *)(v14 + 1088) = *(_DWORD *)(a1 + 420);
              v34 = *(_DWORD *)(a1 + 420);
            }
            else
            {
              *(_DWORD *)(v14 + 1088) = 1;
              v34 = 1;
            }
            *(_DWORD *)(v14 + 1096) = v34;
            if ( *(_BYTE *)(v14 + 1076) || v93 )
            {
              v35 = *v22;
              *(_DWORD *)(v14 + 1072) = 0;
              v36 = v35 ^ ((unsigned __int8)v35 ^ (unsigned __int8)((unsigned int)*v27 >> 21)) & 0x80;
              *v22 = v36;
              *v22 = v36 ^ ((unsigned __int16)v36 ^ ((unsigned int)*v27 >> 20)) & 0x100;
            }
            else
            {
              v68 = *(_DWORD *)(a1 + 404);
              if ( !v68 )
              {
                v69 = *v22 & 0xFFFFFEFF;
                *(_DWORD *)(v14 + 1072) = 0;
                *v22 = v69 | 0x80;
LABEL_35:
                VidSchiVirtualizeFlipInterval(v75, v9 + 1400LL * (unsigned int)v3 + 120);
                v37 = 0;
                if ( (*((_DWORD *)v75 + 20777) & 1) != 0
                  && ((v60 = *(_QWORD *)(v77 + 48), *(_BYTE *)(v60 + 2632)) || *(_BYTE *)(*(_QWORD *)(v60 + 16) + 137LL))
                  && ((v61 = *v22, (*v22 & 0x80) != 0) || v93) )
                {
                  v38 = v74;
                  v37 = (**v74 & 0x3FF) != 0;
                  if ( (*v22 & 0x80) != 0 && (v61 & 0x100) == 0 )
                    *v22 = v61 | 0x200;
                }
                else
                {
                  v38 = v74;
                }
                v39 = *(_DWORD *)(a1 + 424);
                if ( !v39 )
                {
                  if ( v37 )
                  {
                    v40 = -1;
                    v39 = -1;
LABEL_39:
                    *(_DWORD *)(v14 + 1156) = v39;
                    if ( (*(_DWORD *)(a1 + 280) & 0x800) != 0 )
                      *(_BYTE *)(v14 + 1077) = 1;
                    v41 = *v38;
                    v83[0] = v4;
                    v83[1] = v41;
                    v42 = *v41;
                    v43 = *v41 & 0x3FF;
                    v15 = *(_BYTE *)(v4 + 164) == 0;
                    v84 = v43;
                    if ( v15 )
                      v44 = 0;
                    else
                      v44 = (v42 >> 10) & 0x3FF;
                    v15 = !_BitScanForward((unsigned int *)&v45, v43);
                    v46 = -1;
                    v85 = v44;
                    if ( !v15 )
                      v46 = v45;
                    v86 = 0;
                    v15 = !_BitScanForward((unsigned int *)&v47, v44);
                    v48 = v46;
                    v87 = v46;
                    if ( !v15 )
                      v40 = v47;
                    v49 = v40;
                    v88 = v40;
                    while ( v43 || v44 )
                    {
                      if ( v48 < v49 )
                      {
                        v51 = v90;
                        v52 = 0;
                        v73 = 0;
                        v53 = 0;
                        v54 = 1;
                        while ( v53 <= v51 )
                        {
                          if ( (v54 & *(_DWORD *)(v14 + 1080)) != 0 )
                          {
                            v55 = (*v74)[1];
                            v56 = (unsigned __int64)(v86 + v55 * v52) << 6;
                            v57 = (unsigned __int64)*v74 + v55 * ((8 * (*v74)[2] + 231) & 0xFFFFFFF8);
                            v58 = *(struct VIDMM_ALLOC **)(v56 + v57 + 56);
                            if ( ((*((_DWORD *)v58 + 8) >> 2) & 0x3F) == v90 )
                            {
                              VidMmReferencePrimaryAllocationForFlipping(
                                v58,
                                v57,
                                (unsigned __int64 *)(v56 + v57 + 72),
                                (unsigned __int64 *)(v56 + v57 + 80));
                              break;
                            }
                            v51 = v90;
                            v52 = ++v73;
                          }
                          ++v53;
                          v54 *= 2;
                        }
                      }
                      VIDSCH_FLIP_MULTIPLANE_OVERLAY_ITERATOR::operator++(v83);
                      v49 = v88;
                      v44 = v85;
                      v43 = v84;
                      v48 = v87;
                    }
                    if ( *(_DWORD *)(v14 + 1088) > *(_DWORD *)(v14 + 1092) )
                    {
                      *(_DWORD *)(v14 + 1052) = 8;
                      v50 = 8;
                      goto LABEL_52;
                    }
                    if ( v76 )
                    {
                      *(_DWORD *)(v14 + 1052) = 7;
                      v50 = 9;
LABEL_52:
                      VidSchiUpdateFlipQueueHistory(v50, v4, (unsigned int)v5, v9, v3);
LABEL_53:
                      *(_DWORD *)(a1 + 64) |= 2u;
                      if ( v91 )
                        VidSchiCompletePendingFlipOnPlane((unsigned int)&v78, v4, v5, v9, 9);
                      HwQueueStagingList::ProcessHwQueues((HwQueueStagingList *)&v78, 0);
                      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
                      VidSchiProcessCompletedQueuePacket((struct _VIDSCH_QUEUE_PACKET *)a1);
                      KeLowerIrql(NewIrql);
                      goto LABEL_56;
                    }
                    while ( 1 )
                    {
                      *(_DWORD *)(v9 + 56) = ((_BYTE)v3 + 1) & 0x3F;
                      ++*(_QWORD *)(v77 + 8 * v5 + 384);
                      _InterlockedIncrement((volatile signed __int32 *)(v4 + 952));
                      _InterlockedIncrement((volatile signed __int32 *)v75 + 810);
                      if ( *(_DWORD *)(v14 + 1052) == 7 )
                        *(_QWORD *)(v14 + 1064) = ++*(_QWORD *)(v9 + 88);
                      if ( !(unsigned int)VidSchiIsHardwareCompletedDependingCommandForFlip(v14)
                        || *((_BYTE *)v75 + 78948) )
                      {
                        *(_DWORD *)(v14 + 1052) = 1;
                        v63 = 11;
                        goto LABEL_90;
                      }
                      v15 = !v93;
                      *(_DWORD *)(v14 + 1052) = 2;
                      v64 = *(_DWORD *)(v9 + 64);
                      LOBYTE(v90) = 1;
                      if ( v15 )
                        break;
                      if ( (_DWORD)v3 == v64 )
                      {
                        if ( !*(_BYTE *)(v4 + 164)
                          || !VidSchiCheckPendingFlipsForThisEntry(
                                (struct _VIDSCH_GLOBAL *)v4,
                                v75,
                                (struct _VIDSCH_FLIP_QUEUE_ENTRY *)v14,
                                (struct VIDSCH_FLIP_QUEUE *)v9) )
                        {
                          v70 = 12;
                          goto LABEL_138;
                        }
                        if ( !*(_BYTE *)(v4 + 67) )
                          *(_QWORD *)(v14 + 1104) = MEMORY[0xFFFFF78000000320];
                      }
LABEL_102:
                      v65 = v90;
LABEL_103:
                      if ( *(_DWORD *)(1400LL * *(unsigned int *)(v9 + 60) + v9 + 1172) != 1 )
                        *(_DWORD *)(v9 + 60) = *(_DWORD *)(v9 + 56);
                      if ( !v65 )
                        goto LABEL_91;
                      v63 = 10;
LABEL_90:
                      VidSchiUpdateFlipQueueHistory(v63, v4, (unsigned int)v5, v9, v3);
LABEL_91:
                      v3 = *(unsigned int *)(v9 + 56);
                      v14 = v9 + 1400 * v3 + 120;
                      if ( *(_DWORD *)(v14 + 1052) != 7 )
                        goto LABEL_53;
                    }
                    if ( (_DWORD)v3 == v64 || *(_BYTE *)(v14 + 1076) )
                    {
                      if ( *(_BYTE *)(v4 + 67) )
                        goto LABEL_97;
                    }
                    else
                    {
                      if ( (*(_DWORD *)(1400LL * (((_BYTE)v3 - 1) & 0x3F) + v9 + 1272) & 0x20) == 0 )
                        goto LABEL_102;
                      g_DxgMmsBugcheckExportIndex = 1;
                      v72 = v4;
                      HIDWORD(v71) = HIDWORD(v9);
                      WdLogSingleEntry5(0, 281, 0x100000);
                      WdLogGlobalForLineNumber = 921;
                    }
                    *(_QWORD *)(v14 + 1104) = MEMORY[0xFFFFF78000000320];
LABEL_97:
                    if ( !VidSchiCheckPendingFlipsForThisEntry(
                            (struct _VIDSCH_GLOBAL *)v4,
                            v75,
                            (struct _VIDSCH_FLIP_QUEUE_ENTRY *)v14,
                            (struct VIDSCH_FLIP_QUEUE *)v9) )
                    {
                      if ( *(_BYTE *)(v14 + 1076) )
                      {
                        LODWORD(v71) = v3;
                        VidSchiRestartQueuedFlip(&v78, v77, (unsigned int)v5, v9, v71, v72);
                      }
                      if ( !*(_DWORD *)(v9 + 112) )
                      {
                        v70 = 13;
LABEL_138:
                        *(_DWORD *)(v14 + 1052) = 4;
                        v65 = 0;
                        LOBYTE(v90) = 0;
                        VidSchiUpdateFlipQueueHistory(v70, v4, (unsigned int)v5, v9, v3);
                        VidSchiExecuteMmIoFlip(&v78, v4, (unsigned int)v5, v9, v3, &v91, &v90);
                        if ( (_BYTE)v90 )
                          VidSchiExecuteMmIoFlip(&v78, v4, (unsigned int)v5, v9, v3, &v91, &v90);
                        goto LABEL_103;
                      }
                      *(_DWORD *)(v14 + 1052) = 3;
                    }
                    goto LABEL_102;
                  }
                  v39 = *((_DWORD *)v75 + 20774);
                }
                v40 = -1;
                goto LABEL_39;
              }
              *(_DWORD *)(v14 + 1072) = v68;
            }
          }
          v74 = (unsigned int **)(v14 + 1192);
          goto LABEL_35;
        }
        VidSchiRewindPacket(a1, 1, 1, 1);
        VidSchiUpdateContextStatus(v1, 3, 3350);
        HwQueueStagingList::ProcessHwQueues((HwQueueStagingList *)&v78, 0);
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        KeLowerIrql(NewIrql);
      }
      if ( v7 != -1 )
      {
        v59 = *(void (__fastcall **)(_QWORD, _QWORD))(v4 + 3400);
        if ( v59 )
          v59(*(_QWORD *)(v4 + 3448), v7);
      }
LABEL_56:
      HwQueueStagingList::~HwQueueStagingList((HwQueueStagingList *)&v78);
      return;
    }
  }
  VidSchiProcessCompletedQueuePacket((struct _VIDSCH_QUEUE_PACKET *)a1);
}

```

## disassembly

```asm
0x1400065c0  push    rbp
0x1400065c2  push    rbx
0x1400065c3  push    rsi
0x1400065c4  push    rdi
0x1400065c5  push    r12
0x1400065c7  push    r13
0x1400065c9  push    r14
0x1400065cb  push    r15
0x1400065cd  lea     rbp, [rsp-1Fh]
0x1400065d2  sub     rsp, 0D8h
0x1400065d9  mov     rdi, [rcx+58h]
0x1400065dd  mov     r15, rcx
0x1400065e0  mov     [rbp+57h+var_88], rdi
0x1400065e4  mov     r13, [rdi+68h]
0x1400065e8  mov     [rbp+57h+var_B0], r13
0x1400065ec  mov     rsi, [r13+28h]
0x1400065f0  test    byte ptr [rsi+0D24h], 1
0x1400065f7  jnz     loc_140006D30
0x1400065fd  cmp     dword ptr [rsi+0D0Ch], 0
0x140006604  jnz     loc_140006D30
0x14000660a  cmp     byte ptr [r13+0D4h], 0
0x140006612  jnz     loc_140006D30
0x140006618  mov     r12d, [rcx+0A8h]
0x14000661f  xor     ecx, ecx
0x140006621  xor     eax, eax
0x140006623  mov     r14, [rsi+r12*8+0DC8h]
0x14000662b  mov     [rbp+57h+var_C0], r14
0x14000662f  lock cmpxchg [r13+0D0h], ecx
0x140006638  jnz     loc_140006D30
0x14000663e  mov     eax, [r13+38h]
0x140006642  test    al, 2
0x140006644  jz      loc_140006F90
0x14000664a  mov     edx, r12d; unsigned int
0x14000664d  mov     rcx, rsi; struct _VIDSCH_GLOBAL *
0x140006650  call    VidSchIsVSyncEnabled
0x140006655  mov     rax, [rsi+r12*8+0DC8h]
0x14000665d  mov     ebx, [rax+0ADC8h]
0x140006663  cmp     ebx, 0FFFFFFFFh
0x140006666  jnz     loc_140006FAF
0x14000666c  mov     cl, 2; NewIrql
0x14000666e  call    cs:__imp_KfRaiseIrql
0x140006675  nop     dword ptr [rax+rax+00h]
0x14000667a  mov     [rbp+57h+NewIrql], al
0x14000667d  xorps   xmm0, xmm0
0x140006680  xor     eax, eax
0x140006682  lea     rcx, [rsi+830h]; SpinLock
0x140006689  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14000668d  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140006691  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140006695  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14000669c  nop     dword ptr [rax+rax+00h]
0x1400066a1  lea     rax, [rbp+57h+var_A0]
0x1400066a5  mov     [rbp+57h+var_A8], rsi
0x1400066a9  xor     edx, edx; struct _KLOCK_QUEUE_HANDLE *
0x1400066ab  mov     [rbp+57h+var_8C], 2
0x1400066b2  xorps   xmm0, xmm0
0x1400066b5  mov     [rbp+57h+var_90], dl
0x1400066b8  movups  [rbp+57h+var_A0], xmm0
0x1400066bc  mov     qword ptr [rbp+57h+var_A0+8], rax
0x1400066c0  lea     rax, [rbp+57h+var_A0]
0x1400066c4  mov     qword ptr [rbp+57h+var_A0], rax
0x1400066c8  mov     eax, [r15+40h]
0x1400066cc  test    al, 20h
0x1400066ce  jnz     loc_140006CB7
0x1400066d4  mov     r8, [r15+198h]
0x1400066db  lea     eax, [rdx+40h]
0x1400066de  sub     r8, [r13+r12*8+180h]
0x1400066e6  sub     eax, [r14+0CA4h]
0x1400066ed  cmp     r8, rax
0x1400066f0  ja      loc_140006FD2
0x1400066f6  mov     rbx, r14
0x1400066f9  mov     [rbp+57h+arg_8], dl
0x1400066fc  cmp     dword ptr [rbx+4], 3
0x140006700  jnz     loc_140006D97
0x140006706  mov     [rbp+57h+arg_18], 1
0x14000670d  mov     r8d, [r15+48h]
0x140006711  lea     r9, [r15+370h]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140006718  mov     r14, [rbx+20h]
0x14000671c  mov     edx, r12d; unsigned int
0x14000671f  shr     r8d, 17h
0x140006723  mov     rcx, rsi; struct _VIDSCH_GLOBAL *
0x140006726  and     r8b, 1; bool
0x14000672a  call    ?VidSchiValidateDwmReferencedPlanes@@YAXPEAU_VIDSCH_GLOBAL@@I_NAEBUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiValidateDwmReferencedPlanes(_VIDSCH_GLOBAL *,uint,bool,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 const &)
0x14000672f  mov     rax, [r13+30h]
0x140006733  cmp     byte ptr [rax+0A48h], 0
0x14000673a  jnz     loc_14000703D
0x140006740  mov     ecx, [r15+198h]
0x140006747  mov     r10, r12
0x14000674a  sub     ecx, [r13+r12*8+180h]
0x140006752  mov     r13d, [r14+38h]
0x140006756  mov     rdx, [rbp+57h+var_88]
0x14000675a  add     r13d, ecx
0x14000675d  and     r13d, 3Fh
0x140006761  mov     [rbp+57h+var_B8], ecx
0x140006764  mov     rcx, [rsi+308h]
0x14000676b  mov     eax, r13d
0x14000676e  imul    rdi, rax, 578h
0x140006775  mov     eax, [rdx+58h]
0x140006778  add     rdi, 78h ; 'x'
0x14000677c  add     rdi, r14
0x14000677f  cmp     eax, [rsi+350h]
0x140006785  jnb     short loc_14000678B
0x140006787  lea     rcx, [rcx+rax*8]
0x14000678b  cmp     dword ptr [rdi+41Ch], 8
0x140006792  mov     rax, [rcx]
0x140006795  movzx   r8d, word ptr [rax+6]
0x14000679a  mov     [rbp+57h+arg_0], r8d
0x14000679e  jz      loc_140006F3E
0x1400067a4  mov     rax, [rbp+57h+var_B0]
0x1400067a8  mov     r11d, 1
0x1400067ae  add     [rsi+3B4h], r11d
0x1400067b5  add     [rax+730h], r11d
0x1400067bc  add     [rdx+320h], r11d
0x1400067c3  add     [rbx+0CA4h], r11d
0x1400067ca  test    dword ptr [r15+118h], 800000h
0x1400067d5  jz      loc_140006BF3
0x1400067db  mov     eax, [r15+370h]
0x1400067e2  mov     r8d, eax
0x1400067e5  shr     r8d, 0Ah
0x1400067e9  or      r8d, eax
0x1400067ec  and     r8d, 3FFh
0x1400067f3  mov     r9d, 0FFFFFFFFh
0x1400067f9  jmp     short loc_140006820
0x1400067fb  movsx   rax, cl
0x1400067ff  imul    rdx, rax, 130h
0x140006806  mov     rax, [rsi+r10*8+0DC8h]
0x14000680e  add     [rdx+rax+0C4h], r11d
0x140006816  mov     eax, r11d
0x140006819  shl     eax, cl
0x14000681b  not     eax
0x14000681d  and     r8d, eax
0x140006820  bsf     eax, r8d
0x140006824  mov     ecx, r9d
0x140006827  mov     [rbp+57h+var_D0], 0
0x14000682e  movzx   eax, al
0x140006831  cmovnz  ecx, eax
0x140006834  test    r8d, r8d
0x140006837  jnz     short loc_1400067FB
0x140006839  lea     rax, [rdi+4A8h]
0x140006840  xor     edx, edx; Val
0x140006842  mov     rbx, [rax]
0x140006845  mov     r8d, 578h; Size
0x14000684b  mov     rcx, rdi; void *
0x14000684e  mov     [rbp+57h+var_C8], rax
0x140006852  call    memset
0x140006857  mov     [rdi+4A8h], rbx
0x14000685e  xor     edx, edx; Val
0x140006860  mov     eax, [rbx+8]
0x140006863  lea     ecx, [rax+rax*8]
0x140006866  lea     r8d, ds:0E0h[rcx*8]
0x14000686e  imul    r8d, [rbx+4]; Size
0x140006873  lea     rcx, [rbx+18h]; void *
0x140006877  call    memset
0x14000687c  mov     rcx, [rbp+57h+var_88]
0x140006880  lea     rbx, [rdi+480h]
0x140006887  mov     [rdi], rcx
0x14000688a  lea     r8, [r15+118h]
0x140006891  mov     r9d, 400h
0x140006897  mov     r10d, 800h
0x14000689d  mov     rax, [rcx+68h]
0x1400068a1  mov     [rdi+410h], rax
0x1400068a8  mov     eax, [r15+70h]
0x1400068ac  mov     [rdi+418h], eax
0x1400068b2  mov     eax, [r15+188h]
0x1400068b9  mov     [rdi+420h], eax
0x1400068bf  mov     rax, [rcx+0A0h]
0x1400068c6  mov     [rdi+208h], rax
0x1400068cd  mov     eax, [r8]
0x1400068d0  shr     eax, 4
0x1400068d3  and     al, 1
0x1400068d5  mov     [rdi+434h], al
0x1400068db  mov     eax, [rbx]
0x1400068dd  mov     ecx, [r15+48h]
0x1400068e1  shr     ecx, 13h
0x1400068e4  xor     ecx, eax
0x1400068e6  and     ecx, 10h
0x1400068e9  xor     ecx, eax
0x1400068eb  mov     [rbx], ecx
0x1400068ed  mov     edx, [r8]
0x1400068f0  shr     edx, 14h
0x1400068f3  xor     edx, ecx
0x1400068f5  and     edx, r9d
0x1400068f8  xor     edx, ecx
0x1400068fa  mov     [rbx], edx
0x1400068fc  mov     eax, [r8]
0x1400068ff  shr     eax, 14h
0x140006902  xor     eax, edx
0x140006904  and     eax, r10d
0x140006907  xor     eax, edx
0x140006909  cmp     [rbp+57h+var_B8], 0
0x14000690d  mov     [rbx], eax
0x14000690f  jnz     short loc_140006920
0x140006911  inc     qword ptr [r14+58h]
0x140006915  mov     rax, [r14+58h]
0x140006919  mov     [rdi+428h], rax
0x140006920  mov     edx, [rbx]
0x140006922  mov     ecx, [r15+280h]
0x140006929  mov     [rdi+4B0h], ecx
0x14000692f  test    r9d, edx
0x140006932  jnz     loc_140006DAC
0x140006938  test    r10d, edx
0x14000693b  jnz     loc_14000707A
0x140006941  mov     rdx, r8; struct VIDSCH_SUBMIT_DATA2 *
0x140006944  mov     rcx, rdi; this
0x140006947  call    ?FillVmState@_VIDSCH_FLIP_QUEUE_ENTRY@@QEAAXAEAUVIDSCH_SUBMIT_DATA2@@@Z; _VIDSCH_FLIP_QUEUE_ENTRY::FillVmState(VIDSCH_SUBMIT_DATA2 &)
0x14000694c  mov     rcx, [rdi+4A8h]; void *
0x140006953  lea     rax, [r15+370h]
0x14000695a  mov     r8d, [rax+0Ch]; Size
0x14000695e  mov     rdx, rax; Src
0x140006961  call    memmove
0x140006966  lea     r10, [r15+370h]
0x14000696d  mov     rcx, rsi; struct _VIDSCH_GLOBAL *
0x140006970  mov     dword ptr [r10+10h], 0
0x140006978  mov     rdx, [rdi+4A8h]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x14000697f  call    ?VidSchiAcquirePrivateDataReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiAcquirePrivateDataReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x140006984  mov     rdx, r10; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140006987  mov     rcx, rsi; struct _VIDSCH_GLOBAL *
0x14000698a  call    ?VidSchiReleasePrivateDataReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiReleasePrivateDataReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x14000698f  mov     rdx, [rdi+4A8h]; struct VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *
0x140006996  mov     rcx, rsi; struct _VIDSCH_GLOBAL *
0x140006999  call    ?VidSchiAcquireFlipFencesReference@@YAXPEAU_VIDSCH_GLOBAL@@PEAUVIDSCH_FLIP_MULTIPLANE_OVERLAY2@@@Z; VidSchiAcquireFlipFencesReference(_VIDSCH_GLOBAL *,VIDSCH_FLIP_MULTIPLANE_OVERLAY2 *)
0x14000699e  mov     eax, [r15+1A0h]
0x1400069a5  lea     rdx, [r15+118h]
0x1400069ac  mov     ecx, [rbp+57h+arg_0]
0x1400069af  mov     r8d, 1
0x1400069b5  mov     [rdi+438h], eax
0x1400069bb  mov     eax, r8d
0x1400069be  shl     eax, cl
0x1400069c0  mov     [rdi+43Ch], eax
0x1400069c6  mov     ecx, [rdx]
0x1400069c8  mov     eax, [rbx]
0x1400069ca  shr     ecx, 13h
0x1400069cd  xor     ecx, eax
0x1400069cf  and     ecx, r8d
0x1400069d2  xor     ecx, eax
0x1400069d4  mov     [rbx], ecx
0x1400069d6  mov     eax, [rdx]
0x1400069d8  shr     eax, 13h
0x1400069db  xor     eax, ecx
0x1400069dd  and     eax, 2
0x1400069e0  xor     eax, ecx
0x1400069e2  mov     [rbx], eax
0x1400069e4  mov     ecx, [rdx]
0x1400069e6  shr     ecx, 13h
0x1400069e9  xor     ecx, eax
0x1400069eb  and     ecx, 4
0x1400069ee  xor     ecx, eax
0x1400069f0  mov     [rbx], ecx
0x1400069f2  mov     eax, [rdx]
0x1400069f4  shr     eax, 13h
0x1400069f7  xor     eax, ecx
0x1400069f9  and     eax, 8
0x1400069fc  xor     eax, ecx
0x1400069fe  xor     ecx, ecx
0x140006a00  mov     [rbx], eax
0x140006a02  mov     rax, [r15+130h]
0x140006a09  mov     [rdi+498h], rax
0x140006a10  mov     rax, [r15+138h]
0x140006a17  mov     [rdi+4A0h], rax
0x140006a1e  test    rax, rax
0x140006a21  jnz     loc_14000709F
0x140006a27  mov     eax, [rdx]
0x140006a29  mov     [rdi+444h], r8d
0x140006a30  and     eax, 400h
0x140006a35  jz      loc_140006C07
0x140006a3b  mov     eax, [r15+1A4h]
0x140006a42  mov     [rdi+440h], eax
0x140006a48  mov     eax, [r15+1A4h]
0x140006a4f  mov     [rdi+448h], eax
0x140006a55  cmp     [rdi+434h], cl
0x140006a5b  jz      loc_1400070A9
0x140006a61  mov     eax, [rbx]
0x140006a63  mov     [rdi+430h], ecx
0x140006a69  mov     ecx, [rdx]
0x140006a6b  shr     ecx, 15h
0x140006a6e  xor     ecx, eax
0x140006a70  and     ecx, 80h
0x140006a76  xor     ecx, eax
0x140006a78  mov     [rbx], ecx
0x140006a7a  mov     eax, [rdx]
0x140006a7c  shr     eax, 14h
0x140006a7f  xor     eax, ecx
0x140006a81  and     eax, 100h
0x140006a86  xor     eax, ecx
0x140006a88  mov     [rbx], eax
0x140006a8a  lea     rax, [rdi+4A8h]
0x140006a91  mov     [rbp+57h+var_C8], rax
0x140006a95  mov     rcx, [rbp+57h+var_C0]
0x140006a99  mov     rdx, rdi
0x140006a9c  call    VidSchiVirtualizeFlipInterval
0x140006aa1  mov     rax, [rbp+57h+var_C0]
0x140006aa5  xor     cl, cl
0x140006aa7  mov     eax, [rax+144A4h]
0x140006aad  test    al, 1
0x140006aaf  jnz     loc_140006D3D
0x140006ab5  mov     r10, [rbp+57h+var_C8]
0x140006ab9  mov     eax, [r15+1A8h]
0x140006ac0  mov     rbx, [rbp+57h+var_C0]
0x140006ac4  test    eax, eax
0x140006ac6  jz      loc_1400070F4
  ... truncated ...
```
