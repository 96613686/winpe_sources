# PmNotificationWorkItem(_DEVICE_OBJECT *,void *)

- ea: `0x1400087c0`
- end: `0x1400096fc`
- name: `?PmNotificationWorkItem@@YAXPEAU_DEVICE_OBJECT@@PEAX@Z`
- size: `3900`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005454`
- `0x1400079fc`
- `0x1400084d0`
- `0x1400087c0`
- `0x14000a3d0`
- `0x14000c688`
- `0x14000e018`
- `0x14000e170`
- `0x14000e5b0`
- `0x14001d894`
- `0x14001e468`
- `0x14001e6f0`
- `0x140022cf0`
- `0x1400242f0`
- `0x140024e38`
- `0x1400252a0`
- `0x140026640`
- `0x140026f44`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140008877`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008877`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140008e53`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140009270`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400095a6`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140008e53`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140009270`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400095a6`
- `ntoskrnl!KeSetEvent` at `0x14000962e`
- `ntoskrnl!KeSetEvent` at `0x14000962e`
- `ntoskrnl!IofCompleteRequest` at `0x140009198`
- `ntoskrnl!IofCompleteRequest` at `0x140009198`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400096d4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400096d4`
- `ntoskrnl!IoReuseIrp` at `0x140008dff`
- `ntoskrnl!IoReuseIrp` at `0x140009219`
- `ntoskrnl!IoReuseIrp` at `0x140009556`
- `ntoskrnl!IoReuseIrp` at `0x140008dff`
- `ntoskrnl!IoReuseIrp` at `0x140009219`
- `ntoskrnl!IoReuseIrp` at `0x140009556`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008de7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008f89`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400090cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000931a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000953e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009641`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008de7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008f89`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400090cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000931a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000953e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009641`
- `ntoskrnl!KeReleaseMutex` at `0x140008c86`
- `ntoskrnl!KeReleaseMutex` at `0x140009653`
- `ntoskrnl!KeReleaseMutex` at `0x140008c86`
- `ntoskrnl!KeReleaseMutex` at `0x140009653`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008886`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008d2a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008f14`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400090b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400092ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009480`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008886`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008d2a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008f14`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400090b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400092ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009480`

## pseudocode

```c
void __fastcall PmNotificationWorkItem(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  char *DeviceExtension; // rsi
  int v3; // r15d
  KSPIN_LOCK *v4; // r13
  int v5; // r12d
  _QWORD **v6; // r14
  int v7; // ebx
  int v8; // edx
  KIRQL v9; // di
  int v10; // r8d
  int v11; // ecx
  int v12; // r9d
  _QWORD *v13; // rax
  _QWORD *i; // r9
  __int64 v15; // rcx
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v17; // rax
  int v18; // r8d
  __int64 **v19; // rdx
  __int64 ***v20; // rcx
  __int64 **v21; // rdx
  __int64 **v22; // rdx
  __int64 ***v23; // rcx
  __int64 v24; // rdx
  _QWORD *v25; // rcx
  _QWORD *v26; // rcx
  __int64 ***v27; // rax
  int v28; // eax
  int v29; // r14d
  int v30; // edx
  int v31; // edi
  __int64 *v32; // rbx
  __int64 *v33; // rax
  KIRQL v34; // dl
  __int64 v35; // rcx
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 *v44; // rax
  __int64 v45; // rax
  IRP *v46; // rdx
  struct _DEVICE_OBJECT *v47; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v49; // eax
  unsigned int v50; // ecx
  __int64 **v51; // rax
  KIRQL v52; // al
  unsigned __int128 **v53; // rcx
  KIRQL v54; // r8
  unsigned __int64 v55; // rdx
  unsigned __int128 **v56; // rax
  _QWORD *v57; // rax
  __int64 v58; // rcx
  struct _IRP *v59; // rbx
  __int64 v60; // rdx
  int v61; // r12d
  unsigned int v62; // eax
  __int64 v63; // r15
  unsigned int v64; // eax
  unsigned int v65; // eax
  int v66; // eax
  unsigned __int8 v67; // dl
  struct _LIST_ENTRY *Flink; // rdi
  KIRQL v69; // al
  struct _LIST_ENTRY *v70; // rbx
  struct _LIST_ENTRY *v71; // r13
  unsigned int v72; // eax
  unsigned int v73; // eax
  struct _LIST_ENTRY *v74; // rdi
  char v75; // r14
  IRP *v76; // rcx
  __int64 v77; // rax
  IRP *v78; // rbx
  struct _DEVICE_OBJECT *v79; // rcx
  struct _IO_STACK_LOCATION *v80; // rax
  KIRQL v81; // al
  unsigned __int128 **v82; // rcx
  KIRQL v83; // r8
  unsigned __int64 v84; // rdx
  unsigned __int128 **v85; // rax
  _QWORD *v86; // rax
  __int64 v87; // rcx
  struct _LIST_ENTRY *v88; // rcx
  __int64 *v89; // rbx
  __int64 *v90; // rax
  KIRQL v91; // dl
  __int64 v92; // rcx
  __int128 v93; // xmm1
  __int128 v94; // xmm0
  __int128 v95; // xmm1
  __int128 v96; // xmm0
  __int128 v97; // xmm1
  __int128 v98; // xmm0
  __int128 v99; // xmm1
  __int128 v100; // xmm0
  __int64 v101; // rax
  IRP *v102; // rdx
  struct _DEVICE_OBJECT *v103; // rcx
  struct _IO_STACK_LOCATION *v104; // rax
  __int64 *v105; // rdx
  __int64 *v106; // rax
  __int64 v107; // rdx
  __int64 v108; // r8
  __int64 *v109; // rcx
  __int64 *v110; // rax
  struct _LIST_ENTRY v111; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v112; // [rsp+40h] [rbp-C0h] BYREF
  __int64 **v113; // [rsp+48h] [rbp-B8h]
  __int64 *v114; // [rsp+50h] [rbp-B0h] BYREF
  __int64 **v115; // [rsp+58h] [rbp-A8h]
  __int64 *v116; // [rsp+60h] [rbp-A0h] BYREF
  __int64 **v117; // [rsp+68h] [rbp-98h]
  unsigned __int128 v118; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int128 v119; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v120; // [rsp+90h] [rbp-70h] BYREF
  __int64 **v121; // [rsp+98h] [rbp-68h]
  int v122; // [rsp+A0h] [rbp-60h]
  __int64 v123; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v124; // [rsp+B0h] [rbp-50h] BYREF
  PVOID P; // [rsp+B8h] [rbp-48h] BYREF
  struct _IRP *v126; // [rsp+C0h] [rbp-40h]
  __int128 v127; // [rsp+C8h] [rbp-38h] BYREF
  __int128 *v128; // [rsp+D8h] [rbp-28h]
  struct _LIST_ENTRY *v129; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v130; // [rsp+E8h] [rbp-18h]
  __int128 v131; // [rsp+F8h] [rbp-8h] BYREF
  __int128 *v132; // [rsp+108h] [rbp+8h]
  __int128 v133; // [rsp+110h] [rbp+10h] BYREF
  __int128 v134; // [rsp+120h] [rbp+20h]
  __int128 v135; // [rsp+130h] [rbp+30h]
  __int128 v136; // [rsp+140h] [rbp+40h]
  __int128 v137; // [rsp+150h] [rbp+50h]
  __int128 v138; // [rsp+160h] [rbp+60h]
  __int128 v139; // [rsp+170h] [rbp+70h]
  __int128 v140; // [rsp+180h] [rbp+80h]
  __int128 v141; // [rsp+190h] [rbp+90h]
  __int128 v142; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v143; // [rsp+1B0h] [rbp+B0h]
  __int128 v144; // [rsp+1C0h] [rbp+C0h]
  __int128 v145; // [rsp+1D0h] [rbp+D0h]
  __int128 v146; // [rsp+1E0h] [rbp+E0h]
  __int128 v147; // [rsp+1F0h] [rbp+F0h]
  __int128 v148; // [rsp+200h] [rbp+100h]
  __int128 v149; // [rsp+210h] [rbp+110h]
  __int128 v150; // [rsp+220h] [rbp+120h]
  unsigned __int8 v151; // [rsp+270h] [rbp+170h] BYREF
  int v152; // [rsp+280h] [rbp+180h]
  int v153; // [rsp+288h] [rbp+188h]

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v111.Blink = &v111;
  v153 = 0;
  v111.Flink = &v111;
  v3 = 0;
  v122 = 0;
  v117 = &v116;
  v4 = (KSPIN_LOCK *)(DeviceExtension + 112);
  P = 0;
  v116 = (__int64 *)&v116;
  v5 = 0;
  v121 = &v120;
  v120 = (__int64 *)&v120;
  v115 = &v114;
  v114 = (__int64 *)&v114;
  v113 = &v112;
  v112 = (__int64 *)&v112;
  while ( 1 )
  {
    v6 = (_QWORD **)(DeviceExtension + 896);
    KeWaitForSingleObject(DeviceExtension + 56, Executive, 0, 0, 0);
    v7 = 0;
    v9 = KeAcquireSpinLockRaiseToDpc(v4);
    if ( (Microsoft_Windows_PartitionEnableBits & 4) != 0 )
    {
      v11 = *((_DWORD *)DeviceExtension + 129);
      ++v5;
      v12 = *((_DWORD *)DeviceExtension + 42);
      v122 = v5;
      McTemplateK0qdq_EtwWriteTransfer(v11, v8, v10, v12, v11, v5);
    }
    v13 = *v6;
    for ( i = (_QWORD *)**v6; v13 != v6; i = (_QWORD *)*i )
    {
      *((_DWORD *)v13 - 2) = 0;
      if ( (*((_DWORD *)DeviceExtension + 129) & 0x20) != 0 || (*(_DWORD *)(v13 - 13) & 4) != 0 )
      {
        *((_DWORD *)DeviceExtension + 129) |= 0x100000u;
        *((_DWORD *)v13 - 26) |= 8u;
        v24 = *v13;
        if ( *(_QWORD **)(*v13 + 8LL) != v13 )
          goto LABEL_161;
        v25 = (_QWORD *)v13[1];
        if ( (_QWORD *)*v25 != v13 )
          goto LABEL_161;
        *v25 = v24;
        *(_QWORD *)(v24 + 8) = v25;
        if ( (*(_DWORD *)(v13 - 13) & 2) != 0 )
        {
          ++v3;
          *((_DWORD *)v13 - 26) &= ~2u;
          v153 = v3;
        }
        v26 = v113;
        if ( *v113 != (__int64 *)&v112 )
          goto LABEL_161;
        v27 = (__int64 ***)(v13 - 3);
        v27[1] = v113;
        *v27 = &v112;
        *v26 = v27;
        v113 = (__int64 **)v27;
      }
      else if ( (*((_DWORD *)DeviceExtension + 129) & 0x10) != 0
             || (*((_DWORD *)DeviceExtension + 129) & 0x200000) != 0
             || (*((_QWORD *)DeviceExtension + 66) & 0x40) != 0
             || (*(_DWORD *)(v13 - 13) & 0x100) != 0 )
      {
        if ( *(v13 - 4) )
        {
          v22 = v113;
          if ( *v113 != (__int64 *)&v112 )
            goto LABEL_161;
          v23 = (__int64 ***)(v13 - 3);
          v23[1] = v113;
          *v23 = &v112;
          *v22 = v13 - 3;
          v113 = (__int64 **)(v13 - 3);
        }
        *((_DWORD *)v13 - 26) &= 0xFFFFFEFE;
        if ( (*(_DWORD *)(v13 - 13) & 2) != 0 )
        {
          ++v3;
          *((_DWORD *)v13 - 26) &= ~2u;
          v153 = v3;
        }
      }
      else if ( (*((_DWORD *)DeviceExtension + 129) & 0x3C00000) != 0 )
      {
        if ( *(v13 - 4) || (v15 = *(v13 - 14)) != 0 && *(_QWORD *)(v15 + 112) )
        {
          Blink = v111.Blink;
          if ( v111.Blink->Flink != &v111 )
            goto LABEL_161;
          v17 = (struct _LIST_ENTRY *)(v13 - 3);
          v17->Blink = v111.Blink;
          v17->Flink = &v111;
          Blink->Flink = v17;
          v111.Blink = v17;
        }
      }
      else
      {
        v18 = *(_DWORD *)(v13 - 13) & 0x30;
        if ( v18 )
        {
          *((_DWORD *)DeviceExtension + 129) |= 0x100000u;
          if ( *(v13 - 4) )
          {
            v19 = v115;
            if ( *v115 != (__int64 *)&v114 )
              goto LABEL_161;
            v20 = (__int64 ***)(v13 - 3);
            v20[1] = v115;
            *v20 = &v114;
            *v19 = v13 - 3;
            v115 = (__int64 **)(v13 - 3);
          }
          *((_DWORD *)v13 - 26) &= ~v18;
          *((_DWORD *)v13 - 2) |= v18;
          v7 |= v18;
        }
        else if ( (*(_DWORD *)(v13 - 13) & 1) == 0 && (*(_DWORD *)(v13 - 13) & 0x40) == 0 )
        {
          *((_DWORD *)DeviceExtension + 129) |= 0x100000u;
          v21 = v117;
          if ( *v117 != (__int64 *)&v116 )
            goto LABEL_161;
          *(v13 - 2) = v117;
          *(v13 - 3) = &v116;
          *v21 = v13 - 3;
          v117 = (__int64 **)(v13 - 3);
          *((_DWORD *)v13 - 26) |= 2u;
          ++*((_DWORD *)DeviceExtension + 220);
          *((_DWORD *)v13 - 26) |= 1u;
        }
      }
      v13 = i;
    }
    v28 = *((_DWORD *)DeviceExtension + 129);
    v29 = 0;
    v152 = 0;
    if ( (v28 & 0x20) != 0
      || (*((_DWORD *)DeviceExtension + 129) & 0x200000) != 0
      || (*((_QWORD *)DeviceExtension + 66) & 0x40) != 0 )
    {
      if ( (*((_DWORD *)DeviceExtension + 129) & 4) == 0 )
        goto LABEL_46;
      v29 = 32;
      *((_DWORD *)DeviceExtension + 129) &= ~4u;
    }
    else
    {
      if ( (*((_DWORD *)DeviceExtension + 129) & 4) != 0 )
        goto LABEL_46;
      v29 = 4;
      *((_DWORD *)DeviceExtension + 129) |= 4u;
      ++v3;
      ++*((_DWORD *)DeviceExtension + 220);
      v153 = v3;
    }
    v152 = v29;
LABEL_46:
    v30 = *((_DWORD *)DeviceExtension + 129) & 0x3F00000;
    if ( v30 )
    {
      v29 |= v30;
      *((_DWORD *)DeviceExtension + 129) &= ~v30;
      v152 = v29;
    }
    if ( v111.Flink == &v111
      && !v29
      && v116 == (__int64 *)&v116
      && !v7
      && v114 == (__int64 *)&v114
      && v112 == (__int64 *)&v112 )
    {
      break;
    }
    KeReleaseSpinLock(v4, v9);
    if ( (v29 & 0x100000) != 0 )
      PmCollectTelemetry((struct _DEVICE_EXTENSION *)DeviceExtension, (struct _DISK_TELEMETRY_INFO **)&P);
    KeReleaseMutex((PRKMUTEX)DeviceExtension + 1, 0);
    v31 = v29 & 0x20;
    while ( 1 )
    {
      v32 = v112;
      if ( v112 == (__int64 *)&v112 )
        break;
      if ( (__int64 **)v112[1] != &v112 )
        goto LABEL_161;
      v33 = (__int64 *)*v112;
      if ( *(__int64 **)(*v112 + 8) != v112 )
        goto LABEL_161;
      v112 = (__int64 *)*v112;
      v33[1] = (__int64)&v112;
      v31 = v29 & 0x20;
      v127 = 0;
      v128 = 0;
      v133 = 0;
      v134 = 0;
      v135 = 0;
      v136 = 0;
      v137 = 0;
      v138 = 0;
      v139 = 0;
      v140 = 0;
      v141 = 0;
      if ( *(v32 - 1) )
      {
        v34 = KeAcquireSpinLockRaiseToDpc(v4);
        v35 = 0;
        v36 = *((_OWORD *)v32 + 4);
        v133 = *((_OWORD *)v32 + 3);
        v37 = *((_OWORD *)v32 + 5);
        v134 = v36;
        v38 = *((_OWORD *)v32 + 6);
        v135 = v37;
        v39 = *((_OWORD *)v32 + 7);
        v136 = v38;
        v40 = *((_OWORD *)v32 + 8);
        v137 = v39;
        v41 = *((_OWORD *)v32 + 9);
        v138 = v40;
        v42 = *((_OWORD *)v32 + 10);
        v139 = v41;
        v43 = *((_OWORD *)v32 + 11);
        v140 = v42;
        v141 = v43;
        if ( (__int64 *)v32[24] != v32 + 24 )
          v35 = *(_QWORD *)(v32[25] + 16) + *(_QWORD *)(v32[25] + 32);
        *(_QWORD *)&v127 = *(v32 - 14);
        *(_QWORD *)&v134 = v35;
        if ( (v29 & 0x20) != 0 )
          *((_QWORD *)&v127 + 1) = 0;
        else
          *((_QWORD *)&v127 + 1) = *((_QWORD *)DeviceExtension + 3);
        v44 = &v133;
        if ( (*(_DWORD *)(v32 - 10) & 8) != 0 )
          v44 = v128;
        v128 = v44;
        KeReleaseSpinLock(v4, v34);
        IoReuseIrp(*((PIRP *)DeviceExtension + 107), -1073741637);
        v45 = *((_QWORD *)DeviceExtension + 107);
        --*(_BYTE *)(v45 + 67);
        *(_QWORD *)(v45 + 184) -= 72LL;
        v46 = (IRP *)*((_QWORD *)DeviceExtension + 107);
        v47 = *(struct _DEVICE_OBJECT **)(*(v32 - 1) + 40);
        CurrentStackLocation = v46->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation->MajorFunction = 15;
        v46->AssociatedIrp.MasterIrp = (struct _IRP *)&v127;
        CurrentStackLocation->Parameters.Read.Length = 0;
        CurrentStackLocation->Parameters.Create.Options = 24;
        CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 7733252;
        IoForwardIrpSynchronously(v47, v46);
        _InterlockedDecrement((volatile signed __int32 *)(*(v32 - 1) + 32));
        *(v32 - 1) = 0;
        if ( *((_DWORD *)v32 - 4) )
        {
          v49 = --*((_DWORD *)DeviceExtension + 163);
          *((_DWORD *)v32 - 4) = 0;
          v50 = (v49 != 0) - 1;
        }
        else
        {
          v50 = -2;
        }
        _InterlockedAdd((volatile signed __int32 *)DeviceExtension + 162, v50);
      }
      if ( (*(_DWORD *)(v32 - 10) & 8) != 0 )
      {
        v51 = v121;
        if ( *v121 != (__int64 *)&v120 )
          goto LABEL_161;
        v32[1] = (__int64)v121;
        *v32 = (__int64)&v120;
        *v51 = v32;
        v121 = (__int64 **)v32;
      }
    }
    if ( v31 )
      PmTakeDisk((struct _DEVICE_EXTENSION *)DeviceExtension);
    if ( (v29 & 0x800000) != 0 )
      PmQueryDepends((struct _DEVICE_EXTENSION *)DeviceExtension, &v111);
    if ( (v29 & 0x1000000) != 0 )
      PmPowerChanged((struct _DEVICE_EXTENSION *)DeviceExtension, &v111);
    if ( (v29 & 0x400000) != 0 )
    {
      v118 = 0;
      v52 = KeAcquireSpinLockRaiseToDpc(v4);
      v53 = (unsigned __int128 **)(DeviceExtension + 656);
      v54 = v52;
      v55 = *((_QWORD *)DeviceExtension + 82);
      if ( *(char **)(v55 + 8) != DeviceExtension + 656 )
        goto LABEL_161;
      v118 = __PAIR128__((unsigned __int64)v53, v55);
      *(_QWORD *)(v55 + 8) = &v118;
      *v53 = &v118;
      if ( *((unsigned __int128 ***)&v118 + 1) != v53 )
        goto LABEL_161;
      v56 = (unsigned __int128 **)*((_QWORD *)DeviceExtension + 83);
      if ( *v56 != (unsigned __int128 *)v53 )
        goto LABEL_161;
      *v56 = &v118;
      *((_QWORD *)DeviceExtension + 83) = v53;
      *v53 = (unsigned __int128 *)v53;
      *((_QWORD *)&v118 + 1) = v56;
      KeReleaseSpinLock(v4, v54);
      while ( 1 )
      {
        v57 = (_QWORD *)v118;
        if ( (unsigned __int128 *)v118 == &v118 )
          break;
        if ( *(unsigned __int128 **)(v118 + 8) != &v118 )
          goto LABEL_161;
        v58 = *(_QWORD *)v118;
        if ( *(_QWORD *)(*(_QWORD *)v118 + 8LL) != (_QWORD)v118 )
          goto LABEL_161;
        *(_QWORD *)&v118 = *(_QWORD *)v118;
        v59 = (struct _IRP *)(v57 - 21);
        v126 = (struct _IRP *)(v57 - 21);
        *(_QWORD *)(v58 + 8) = &v118;
        v57[1] = v57;
        *v57 = v57;
        v60 = v57[2];
        *(v57 - 14) = 0;
        if ( *(_BYTE *)v60 != 3 && *(_BYTE *)v60 != 4 )
        {
          if ( *(_BYTE *)v60 != 14 )
          {
            v61 = -1073741808;
            goto LABEL_117;
          }
          v62 = *(_DWORD *)(v60 + 24);
          v63 = 0;
          v123 = 0;
          v61 = 0;
          v151 = 0;
          v124 = 0;
          if ( v62 > 0x4D030 )
          {
            v67 = 0;
            v72 = v62 - 315460;
            if ( !v72 )
              goto LABEL_100;
            v73 = v72 - 4;
            if ( !v73 )
              goto LABEL_100;
            if ( v73 != 2671548 )
              goto LABEL_103;
            v66 = PmIoctlDsmQuerySectorWrite(v59, &v151, &v123, &v124);
          }
          else
          {
            if ( v62 == 315440 )
              goto LABEL_98;
            v64 = v62 - 315396;
            if ( v64 )
            {
              v65 = v64 - 16;
              if ( v65 )
              {
                if ( v65 == 24 )
                {
LABEL_98:
                  v66 = PmIoctlPassThroughQuerySectorWriteAta(v59, &v151, &v123, &v124);
                  goto LABEL_101;
                }
LABEL_103:
                Flink = v111.Flink;
                if ( v111.Flink == &v111 )
                  goto LABEL_117;
                while ( 2 )
                {
                  v69 = KeAcquireSpinLockRaiseToDpc(v4);
                  v70 = Flink[3].Blink;
                  v71 = Flink[4].Flink;
                  KeReleaseSpinLock((PKSPIN_LOCK)DeviceExtension + 14, v69);
                  if ( (__int64)v70 <= v63 )
                  {
                    if ( v63 - (__int64)v70 < (__int64)v71 )
                      goto LABEL_114;
LABEL_106:
                    v59 = v126;
                  }
                  else
                  {
                    if ( (__int64)v124 <= (__int64)v70 - v63 )
                      goto LABEL_106;
LABEL_114:
                    v59 = v126;
                    v61 = PmPartitionRedirect(
                            (struct _DEVICE_EXTENSION *)DeviceExtension,
                            (struct _PARTITION_EXTENSION *)&Flink[-8].Blink,
                            v126,
                            0,
                            0,
                            0);
                    if ( v61 < 0 )
                    {
LABEL_108:
                      v4 = (KSPIN_LOCK *)(DeviceExtension + 112);
                      goto LABEL_117;
                    }
                  }
                  Flink = Flink->Flink;
                  v4 = (KSPIN_LOCK *)(DeviceExtension + 112);
                  if ( Flink == &v111 )
                    goto LABEL_108;
                  continue;
                }
              }
            }
            v67 = 1;
LABEL_100:
            v66 = PmIoctlPassThroughQuerySectorWriteScsi(v59, v67, &v151, &v123, &v124);
          }
LABEL_101:
          v61 = v66;
          if ( v66 < 0 )
            goto LABEL_117;
          v63 = v123;
          goto LABEL_103;
        }
        v61 = PmSplitAndRedirectIo((struct _DEVICE_EXTENSION *)DeviceExtension, (struct _IRP *)(v57 - 21), &v111);
LABEL_117:
        v59->IoStatus.Status = v61;
        IofCompleteRequest(v59, 1);
      }
      v29 = v152;
      v3 = v153;
      v5 = v122;
    }
    if ( (v29 & 0x2000000) != 0 )
    {
      v74 = v111.Flink;
      v75 = 0;
      v129 = 0;
      v119 = 0;
      v130 = 0;
      if ( v111.Flink != &v111 )
      {
        while ( 1 )
        {
          if ( v74[-1].Blink )
          {
            v76 = (IRP *)*((_QWORD *)DeviceExtension + 107);
            v129 = v74[-7].Flink;
            *(_QWORD *)&v130 = *((_QWORD *)DeviceExtension + 3);
            IoReuseIrp(v76, -1073741637);
            v77 = *((_QWORD *)DeviceExtension + 107);
            --*(_BYTE *)(v77 + 67);
            *(_QWORD *)(v77 + 184) -= 72LL;
            v78 = (IRP *)*((_QWORD *)DeviceExtension + 107);
            v79 = (struct _DEVICE_OBJECT *)v74[-1].Blink[2].Blink;
            v80 = v78->Tail.Overlay.CurrentStackLocation;
            v80->MajorFunction = 15;
            v78->AssociatedIrp.MasterIrp = (struct _IRP *)&v129;
            v80->Parameters.Read.Length = 1;
            v80->Parameters.Create.Options = 24;
            v80->Parameters.Read.ByteOffset.LowPart = 7733304;
            IoForwardIrpSynchronously(v79, v78);
            if ( v78->IoStatus.Status >= 0 )
            {
              if ( (_BYTE)v129 )
                break;
            }
          }
          v74 = v74->Flink;
          if ( v74 == &v111 )
            goto LABEL_127;
        }
        v75 = 1;
      }
LABEL_127:
      v81 = KeAcquireSpinLockRaiseToDpc(v4);
      v82 = (unsigned __int128 **)(DeviceExtension + 688);
      v83 = v81;
      v84 = *((_QWORD *)DeviceExtension + 86);
      if ( *(char **)(v84 + 8) != DeviceExtension + 688
        || (v119 = __PAIR128__((unsigned __int64)v82, v84),
            *(_QWORD *)(v84 + 8) = &v119,
            *v82 = &v119,
            *((unsigned __int128 ***)&v119 + 1) != v82)
        || (v85 = (unsigned __int128 **)*((_QWORD *)DeviceExtension + 87), *v85 != (unsigned __int128 *)v82) )
      {
LABEL_161:
        __fastfail(3u);
      }
      *v85 = &v119;
      *((_QWORD *)DeviceExtension + 87) = v82;
      *v82 = (unsigned __int128 *)v82;
      *((_QWORD *)&v119 + 1) = v85;
      KeReleaseSpinLock(v4, v83);
      while ( 1 )
      {
        v86 = (_QWORD *)v119;
        if ( (unsigned __int128 *)v119 == &v119 )
          break;
        if ( *(unsigned __int128 **)(v119 + 8) != &v119 )
          goto LABEL_161;
        v87 = *(_QWORD *)v119;
        if ( *(_QWORD *)(*(_QWORD *)v119 + 8LL) != (_QWORD)v119 )
          goto LABEL_161;
        *(_QWORD *)&v119 = *(_QWORD *)v119;
        *(_QWORD *)(v87 + 8) = &v119;
        v86[1] = v86;
        *v86 = v86;
        *((_DWORD *)v86 - 30) = v75 != 0 ? 0xC0000001 : 0;
      }
      LOBYTE(v29) = v152;
    }
    if ( P )
    {
      PmSendTelemetry((struct _DISK_TELEMETRY_INFO *)P);
      PmFreeTelemetry(P);
      P = 0;
    }
    while ( v111.Flink != &v111 )
    {
      if ( v111.Flink->Blink != &v111 )
        goto LABEL_161;
      v88 = v111.Flink->Flink;
      if ( v111.Flink->Flink->Blink != v111.Flink )
        goto LABEL_161;
      v111.Flink = v111.Flink->Flink;
      v88->Blink = &v111;
    }
    while ( 1 )
    {
      v89 = v114;
      if ( v114 == (__int64 *)&v114 )
        break;
      if ( (__int64 **)v114[1] != &v114 )
        goto LABEL_161;
      v90 = (__int64 *)*v114;
      if ( *(__int64 **)(*v114 + 8) != v114 )
        goto LABEL_161;
      v114 = (__int64 *)*v114;
      v90[1] = (__int64)&v114;
      if ( (v89[2] & 0x10) != 0 )
      {
        v132 = 0;
        v131 = 0;
        v142 = 0;
        v143 = 0;
        v144 = 0;
        v145 = 0;
        v146 = 0;
        v147 = 0;
        v148 = 0;
        v149 = 0;
        v150 = 0;
        if ( *(v89 - 1) )
        {
          v91 = KeAcquireSpinLockRaiseToDpc(v4);
          v92 = 0;
          v93 = *((_OWORD *)v89 + 4);
          v142 = *((_OWORD *)v89 + 3);
          v94 = *((_OWORD *)v89 + 5);
          v143 = v93;
          v95 = *((_OWORD *)v89 + 6);
          v144 = v94;
          v96 = *((_OWORD *)v89 + 7);
          v145 = v95;
          v97 = *((_OWORD *)v89 + 8);
          v146 = v96;
          v98 = *((_OWORD *)v89 + 9);
          v147 = v97;
          v99 = *((_OWORD *)v89 + 10);
          v148 = v98;
          v100 = *((_OWORD *)v89 + 11);
          v149 = v99;
          v150 = v100;
          if ( (__int64 *)v89[24] != v89 + 24 )
            v92 = *(_QWORD *)(v89[25] + 16) + *(_QWORD *)(v89[25] + 32);
          *(_QWORD *)&v131 = *(v89 - 14);
          *((_QWORD *)&v131 + 1) = *((_QWORD *)DeviceExtension + 3);
          *(_QWORD *)&v143 = v92;
          v132 = &v142;
          KeReleaseSpinLock(v4, v91);
          IoReuseIrp(*((PIRP *)DeviceExtension + 107), -1073741637);
          v101 = *((_QWORD *)DeviceExtension + 107);
          --*(_BYTE *)(v101 + 67);
          *(_QWORD *)(v101 + 184) -= 72LL;
          v102 = (IRP *)*((_QWORD *)DeviceExtension + 107);
          v103 = *(struct _DEVICE_OBJECT **)(*(v89 - 1) + 40);
          v104 = v102->Tail.Overlay.CurrentStackLocation;
          v104->MajorFunction = 15;
          v102->AssociatedIrp.MasterIrp = (struct _IRP *)&v131;
          v104->Parameters.Read.Length = 0;
          v104->Parameters.Create.Options = 24;
          v104->Parameters.Read.ByteOffset.LowPart = 7733280;
          IoForwardIrpSynchronously(v103, v102);
        }
      }
    }
    if ( (v29 & 4) != 0 )
      PmGiveDisk((struct _DEVICE_EXTENSION *)DeviceExtension);
    while ( 1 )
    {
      v105 = v116;
      if ( v116 == (__int64 *)&v116 )
        break;
      if ( (__int64 **)v116[1] != &v116 )
        goto LABEL_161;
      v106 = (__int64 *)*v116;
      if ( *(__int64 **)(*v116 + 8) != v116 )
        goto LABEL_161;
      v116 = (__int64 *)*v116;
      v106[1] = (__int64)&v116;
      PmGivePartition((struct _DEVICE_EXTENSION *)DeviceExtension, (struct _PARTITION_EXTENSION *)(v105 - 15));
    }
  }
  DeviceExtension[816] = 0;
  KeSetEvent((PRKEVENT)(DeviceExtension + 824), 0, 0);
  KeReleaseSpinLock(v4, v9);
  KeReleaseMutex((PRKMUTEX)DeviceExtension + 1, 0);
  PmDecrementPendingPartitionsCount((struct _DEVICE_EXTENSION *)DeviceExtension, v3);
  while ( 1 )
  {
    v109 = v120;
    if ( v120 == (__int64 *)&v120 )
      break;
    if ( (__int64 **)v120[1] != &v120 )
      goto LABEL_161;
    v110 = (__int64 *)*v120;
    if ( *(__int64 **)(*v120 + 8) != v120 )
      goto LABEL_161;
    v120 = (__int64 *)*v120;
    v110[1] = (__int64)&v120;
    PmDeletePartition((struct _PARTITION_EXTENSION *)(v109 - 15));
  }
  if ( (Microsoft_Windows_PartitionEnableBits & 4) != 0 )
    McTemplateK0q_EtwWriteTransfer(v120, v107, v108, *((unsigned int *)DeviceExtension + 42));
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), *((PVOID *)DeviceExtension + 106), 0x20u);
}

```

## disassembly

```asm
0x1400087c0  mov     [rsp-8+arg_8], rbx
0x1400087c5  push    rbp
0x1400087c6  push    rsi
0x1400087c7  push    rdi
0x1400087c8  push    r12
0x1400087ca  push    r13
0x1400087cc  push    r14
0x1400087ce  push    r15
0x1400087d0  lea     rbp, [rsp-130h]
0x1400087d8  sub     rsp, 230h
0x1400087df  mov     rsi, [rcx+40h]
0x1400087e3  lea     rax, [rsp+260h+var_230]
0x1400087e8  mov     [rsp+260h+var_230.Blink], rax
0x1400087ed  xor     edi, edi
0x1400087ef  lea     rax, [rsp+260h+var_230]
0x1400087f4  mov     [rbp+160h+arg_18], edi
0x1400087fa  mov     [rsp+260h+var_230.Flink], rax
0x1400087ff  mov     r15d, edi
0x140008802  lea     rax, [rsp+260h+var_200]
0x140008807  mov     [rbp+160h+var_1C0], edi
0x14000880a  mov     [rsp+260h+var_1F8], rax
0x14000880f  lea     r13, [rsi+70h]
0x140008813  lea     rax, [rsp+260h+var_200]
0x140008818  mov     [rbp+160h+P], rdi
0x14000881c  mov     [rsp+260h+var_200], rax
0x140008821  mov     r12d, edi
0x140008824  lea     rax, [rbp+160h+var_1D0]
0x140008828  mov     [rbp+160h+var_1C8], rax
0x14000882c  lea     rax, [rbp+160h+var_1D0]
0x140008830  mov     [rbp+160h+var_1D0], rax
0x140008834  lea     rax, [rsp+260h+var_210]
0x140008839  mov     [rsp+260h+var_208], rax
0x14000883e  lea     rax, [rsp+260h+var_210]
0x140008843  mov     [rsp+260h+var_210], rax
0x140008848  lea     rax, [rsp+260h+var_220]
0x14000884d  mov     [rsp+260h+var_218], rax
0x140008852  lea     rax, [rsp+260h+var_220]
0x140008857  mov     [rsp+260h+var_220], rax
0x14000885c  lea     rax, [rsi+38h]
0x140008860  mov     [rsp+260h+Timeout], rdi; Timeout
0x140008865  mov     rcx, rax; Object
0x140008868  lea     r14, [rsi+380h]
0x14000886f  xor     r9d, r9d; Alertable
0x140008872  xor     r8d, r8d; WaitMode
0x140008875  xor     edx, edx; WaitReason
0x140008877  call    cs:__imp_KeWaitForSingleObject
0x14000887e  nop     dword ptr [rax+rax+00h]
0x140008883  mov     rcx, r13; SpinLock
0x140008886  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000888d  nop     dword ptr [rax+rax+00h]
0x140008892  xor     ebx, ebx
0x140008894  movzx   edi, al
0x140008897  test    cs:Microsoft_Windows_PartitionEnableBits, 4
0x14000889e  jz      short loc_1400088C2
0x1400088a0  mov     ecx, [rsi+204h]
0x1400088a6  inc     r12d
0x1400088a9  mov     r9d, [rsi+0A8h]
0x1400088b0  mov     [rsp+260h+var_238], r12d
0x1400088b5  mov     dword ptr [rsp+260h+Timeout], ecx
0x1400088b9  mov     [rbp+160h+var_1C0], r12d
0x1400088bd  call    McTemplateK0qdq_EtwWriteTransfer
0x1400088c2  mov     rax, [r14]
0x1400088c5  mov     r9, [rax]
0x1400088c8  cmp     rax, r14
0x1400088cb  jz      loc_140008B69
0x1400088d1  nop     dword ptr [rax+00h]
0x1400088d5  nop     word ptr [rax+rax+00000000h]
0x1400088e0  mov     dword ptr [rax-8], 0
0x1400088e7  mov     ecx, [rsi+204h]
0x1400088ed  test    cl, 20h
0x1400088f0  jnz     loc_140008ADA
0x1400088f6  mov     ecx, [rax-68h]
0x1400088f9  test    cl, 4
0x1400088fc  jnz     loc_140008ADA
0x140008902  mov     ecx, [rsi+204h]
0x140008908  test    cl, 10h
0x14000890b  jnz     loc_140008A78
0x140008911  mov     ecx, [rsi+204h]
0x140008917  bt      ecx, 15h
0x14000891b  jb      loc_140008A78
0x140008921  mov     rcx, [rsi+210h]
0x140008928  test    cl, 40h
0x14000892b  jnz     loc_140008A78
0x140008931  mov     ecx, [rax-68h]
0x140008934  bt      ecx, 8
0x140008938  jb      loc_140008A78
0x14000893e  mov     ecx, [rsi+204h]
0x140008944  test    ecx, 3C00000h
0x14000894a  jz      short loc_14000899B
0x14000894c  cmp     qword ptr [rax-20h], 0
0x140008951  jnz     short loc_14000896B
0x140008953  mov     rcx, [rax-70h]
0x140008957  test    rcx, rcx
0x14000895a  jz      loc_140008B5A
0x140008960  cmp     qword ptr [rcx+70h], 0
0x140008965  jz      loc_140008B5A
0x14000896b  mov     rcx, [rsp+260h+var_230.Blink]
0x140008970  lea     rdx, [rsp+260h+var_230]
0x140008975  cmp     [rcx], rdx
0x140008978  jnz     loc_1400096A7
0x14000897e  add     rax, 0FFFFFFFFFFFFFFE8h
0x140008982  lea     rdx, [rsp+260h+var_230]
0x140008987  mov     [rax+8], rcx
0x14000898b  mov     [rax], rdx
0x14000898e  mov     [rcx], rax
0x140008991  mov     [rsp+260h+var_230.Blink], rax
0x140008996  jmp     loc_140008B5A
0x14000899b  mov     r8d, [rax-68h]
0x14000899f  and     r8d, 30h
0x1400089a3  jz      short loc_140008A00
0x1400089a5  mov     ecx, [rsi+204h]
0x1400089ab  bts     ecx, 14h
0x1400089af  mov     [rsi+204h], ecx
0x1400089b5  cmp     qword ptr [rax-20h], 0
0x1400089ba  jz      short loc_1400089E7
0x1400089bc  mov     rdx, [rsp+260h+var_208]
0x1400089c1  lea     rcx, [rsp+260h+var_210]
0x1400089c6  cmp     [rdx], rcx
0x1400089c9  jnz     loc_1400096A7
0x1400089cf  lea     rcx, [rax-18h]
0x1400089d3  mov     [rcx+8], rdx
0x1400089d7  lea     r10, [rsp+260h+var_210]
0x1400089dc  mov     [rcx], r10
0x1400089df  mov     [rdx], rcx
0x1400089e2  mov     [rsp+260h+var_208], rcx
0x1400089e7  mov     ecx, [rax-68h]
0x1400089ea  mov     edx, r8d
0x1400089ed  not     edx
0x1400089ef  and     edx, ecx
0x1400089f1  mov     [rax-68h], edx
0x1400089f4  or      [rax-8], r8d
0x1400089f8  or      ebx, r8d
0x1400089fb  jmp     loc_140008B5A
0x140008a00  mov     ecx, [rax-68h]
0x140008a03  test    cl, 1
0x140008a06  jnz     loc_140008B5A
0x140008a0c  mov     ecx, [rax-68h]
0x140008a0f  test    cl, 40h
0x140008a12  jnz     loc_140008B5A
0x140008a18  mov     ecx, [rsi+204h]
0x140008a1e  bts     ecx, 14h
0x140008a22  mov     [rsi+204h], ecx
0x140008a28  lea     rcx, [rsp+260h+var_200]
0x140008a2d  mov     rdx, [rsp+260h+var_1F8]
0x140008a32  cmp     [rdx], rcx
0x140008a35  jnz     loc_1400096A7
0x140008a3b  mov     [rax-10h], rdx
0x140008a3f  lea     rcx, [rax-18h]
0x140008a43  lea     r8, [rsp+260h+var_200]
0x140008a48  mov     [rcx], r8
0x140008a4b  mov     [rdx], rcx
0x140008a4e  mov     [rsp+260h+var_1F8], rcx
0x140008a53  mov     ecx, [rax-68h]
0x140008a56  or      ecx, 2
0x140008a59  mov     [rax-68h], ecx
0x140008a5c  mov     ecx, [rsi+370h]
0x140008a62  inc     ecx
0x140008a64  mov     [rsi+370h], ecx
0x140008a6a  mov     ecx, [rax-68h]
0x140008a6d  or      ecx, 1
0x140008a70  mov     [rax-68h], ecx
0x140008a73  jmp     loc_140008B5A
0x140008a78  cmp     qword ptr [rax-20h], 0
0x140008a7d  jz      short loc_140008AAA
0x140008a7f  mov     rdx, [rsp+260h+var_218]
0x140008a84  lea     rcx, [rsp+260h+var_220]
0x140008a89  cmp     [rdx], rcx
0x140008a8c  jnz     loc_1400096A7
0x140008a92  lea     rcx, [rax-18h]
0x140008a96  mov     [rcx+8], rdx
0x140008a9a  lea     r8, [rsp+260h+var_220]
0x140008a9f  mov     [rcx], r8
0x140008aa2  mov     [rdx], rcx
0x140008aa5  mov     [rsp+260h+var_218], rcx
0x140008aaa  mov     ecx, [rax-68h]
0x140008aad  and     ecx, 0FFFFFEFEh
0x140008ab3  mov     [rax-68h], ecx
0x140008ab6  mov     ecx, [rax-68h]
0x140008ab9  test    cl, 2
0x140008abc  jz      loc_140008B5A
0x140008ac2  mov     ecx, [rax-68h]
0x140008ac5  and     ecx, 0FFFFFFFDh
0x140008ac8  inc     r15d
0x140008acb  mov     [rax-68h], ecx
0x140008ace  mov     [rbp+160h+arg_18], r15d
0x140008ad5  jmp     loc_140008B5A
0x140008ada  mov     ecx, [rsi+204h]
0x140008ae0  bts     ecx, 14h
0x140008ae4  mov     [rsi+204h], ecx
0x140008aea  mov     ecx, [rax-68h]
0x140008aed  or      ecx, 8
0x140008af0  mov     [rax-68h], ecx
0x140008af3  mov     rdx, [rax]
0x140008af6  cmp     [rdx+8], rax
0x140008afa  jnz     loc_1400096A7
0x140008b00  mov     rcx, [rax+8]
0x140008b04  cmp     [rcx], rax
0x140008b07  jnz     loc_1400096A7
0x140008b0d  mov     [rcx], rdx
0x140008b10  mov     [rdx+8], rcx
0x140008b14  mov     ecx, [rax-68h]
0x140008b17  test    cl, 2
0x140008b1a  jz      short loc_140008B2F
0x140008b1c  mov     ecx, [rax-68h]
0x140008b1f  and     ecx, 0FFFFFFFDh
0x140008b22  inc     r15d
0x140008b25  mov     [rax-68h], ecx
0x140008b28  mov     [rbp+160h+arg_18], r15d
0x140008b2f  mov     rcx, [rsp+260h+var_218]
0x140008b34  lea     rdx, [rsp+260h+var_220]
0x140008b39  cmp     [rcx], rdx
0x140008b3c  jnz     loc_1400096A7
0x140008b42  add     rax, 0FFFFFFFFFFFFFFE8h
0x140008b46  lea     rdx, [rsp+260h+var_220]
0x140008b4b  mov     [rax+8], rcx
0x140008b4f  mov     [rax], rdx
0x140008b52  mov     [rcx], rax
0x140008b55  mov     [rsp+260h+var_218], rax
0x140008b5a  mov     rax, r9
0x140008b5d  mov     r9, [r9]
0x140008b60  cmp     rax, r14
0x140008b63  jnz     loc_1400088E0
0x140008b69  mov     eax, [rsi+204h]
0x140008b6f  xor     r14d, r14d
0x140008b72  mov     [rbp+160h+arg_10], r14d
0x140008b79  test    al, 20h
0x140008b7b  jnz     short loc_140008BCD
0x140008b7d  mov     eax, [rsi+204h]
0x140008b83  bt      eax, 15h
0x140008b87  jb      short loc_140008BCD
0x140008b89  mov     rax, [rsi+210h]
0x140008b90  test    al, 40h
0x140008b92  jnz     short loc_140008BCD
0x140008b94  mov     eax, [rsi+204h]
0x140008b9a  test    al, 4
0x140008b9c  jnz     short loc_140008BF3
0x140008b9e  mov     eax, [rsi+204h]
0x140008ba4  mov     r14d, 4
0x140008baa  or      eax, 4
0x140008bad  mov     [rsi+204h], eax
0x140008bb3  mov     eax, [rsi+370h]
0x140008bb9  inc     eax
0x140008bbb  inc     r15d
0x140008bbe  mov     [rsi+370h], eax
0x140008bc4  mov     [rbp+160h+arg_18], r15d
0x140008bcb  jmp     short loc_140008BEC
0x140008bcd  mov     eax, [rsi+204h]
0x140008bd3  test    al, 4
0x140008bd5  jz      short loc_140008BF3
0x140008bd7  mov     eax, [rsi+204h]
0x140008bdd  mov     r14d, 20h ; ' '
0x140008be3  and     eax, 0FFFFFFFBh
0x140008be6  mov     [rsi+204h], eax
0x140008bec  mov     [rbp+160h+arg_10], r14d
0x140008bf3  mov     edx, [rsi+204h]
0x140008bf9  and     edx, 3F00000h
0x140008bff  jz      short loc_140008C1D
0x140008c01  mov     eax, [rsi+204h]
0x140008c07  mov     ecx, edx
0x140008c09  not     ecx
0x140008c0b  and     ecx, eax
0x140008c0d  or      r14d, edx
0x140008c10  mov     [rsi+204h], ecx
0x140008c16  mov     [rbp+160h+arg_10], r14d
0x140008c1d  lea     rax, [rsp+260h+var_230]
0x140008c22  cmp     [rsp+260h+var_230.Flink], rax
0x140008c27  jnz     short loc_140008C5A
0x140008c29  test    r14d, r14d
0x140008c2c  jnz     short loc_140008C5A
0x140008c2e  lea     rax, [rsp+260h+var_200]
0x140008c33  cmp     [rsp+260h+var_200], rax
0x140008c38  jnz     short loc_140008C5A
0x140008c3a  test    ebx, ebx
0x140008c3c  jnz     short loc_140008C5A
0x140008c3e  lea     rax, [rsp+260h+var_210]
0x140008c43  cmp     [rsp+260h+var_210], rax
0x140008c48  jnz     short loc_140008C5A
0x140008c4a  lea     rax, [rsp+260h+var_220]
0x140008c4f  cmp     [rsp+260h+var_220], rax
0x140008c54  jz      loc_14000961B
0x140008c5a  movzx   edx, dil; NewIrql
0x140008c5e  mov     rcx, r13; SpinLock
0x140008c61  call    cs:__imp_KeReleaseSpinLock
0x140008c68  nop     dword ptr [rax+rax+00h]
0x140008c6d  bt      r14d, 14h
0x140008c72  jnb     short loc_140008C80
0x140008c74  lea     rdx, [rbp+160h+P]; struct _DISK_TELEMETRY_INFO **
0x140008c78  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x140008c7b  call    ?PmCollectTelemetry@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DISK_TELEMETRY_INFO@@@Z; PmCollectTelemetry(_DEVICE_EXTENSION *,_DISK_TELEMETRY_INFO * *)
0x140008c80  xor     edx, edx; Wait
0x140008c82  lea     rcx, [rsi+38h]; Mutex
0x140008c86  call    cs:__imp_KeReleaseMutex
0x140008c8d  nop     dword ptr [rax+rax+00h]
0x140008c92  mov     edi, r14d
0x140008c95  and     edi, 20h
0x140008c98  nop     dword ptr [rax+rax+00000000h]
0x140008ca0  mov     rbx, [rsp+260h+var_220]
0x140008ca5  lea     rax, [rsp+260h+var_220]
0x140008caa  cmp     rbx, rax
0x140008cad  jz      loc_140008ECA
  ... truncated ...
```
