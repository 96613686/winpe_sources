# RxFsdCommonDispatch

- ea: `0x140015290`
- end: `0x14001663c`
- name: `RxFsdCommonDispatch`
- size: `5036`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140069190`

## callees

- `0x1400027b0`
- `0x140003ae0`
- `0x140007ca0`
- `0x140008f60`
- `0x14000b950`
- `0x14000f130`
- `0x140012260`
- `0x140013760`
- `0x140014540`
- `0x140014600`
- `0x140014ad0`
- `0x140014dc0`
- `0x1400151d0`
- `0x140015230`
- `0x140015290`
- `0x140016e20`
- `0x140017280`
- `0x140017310`
- `0x14001bea8`
- `0x14001c448`
- `0x140025d00`
- `0x140048874`
- `0x1400694e0`
- `0x14006e340`
- `0x140078160`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140016199`
- `ntoskrnl!DbgPrint` at `0x140016199`
- `ntoskrnl!KeSetEvent` at `0x140016579`
- `ntoskrnl!KeSetEvent` at `0x140016579`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001613a`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001613a`
- `ntoskrnl!IofCompleteRequest` at `0x1400156a7`
- `ntoskrnl!IofCompleteRequest` at `0x140015a6f`
- `ntoskrnl!IofCompleteRequest` at `0x1400156a7`
- `ntoskrnl!IofCompleteRequest` at `0x140015a6f`
- `ntoskrnl!KeAreApcsDisabled` at `0x14001531c`
- `ntoskrnl!KeAreApcsDisabled` at `0x1400165b3`
- `ntoskrnl!KeAreApcsDisabled` at `0x14001531c`
- `ntoskrnl!KeAreApcsDisabled` at `0x1400165b3`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400153cf`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400153fe`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400153cf`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400153fe`
- `ntoskrnl!IoGetStackLimits` at `0x140015fde`
- `ntoskrnl!IoGetStackLimits` at `0x140015fde`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e85`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015eee`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e85`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015eee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015e0c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015e0c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400165a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400165a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001534b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001534b`

## pseudocode

```c
__int64 __fastcall RxFsdCommonDispatch(__int64 a1, __int64 a2, __int64 a3, struct _RDBSS_DEVICE_OBJECT *a4)
{
  int v6; // esi
  NTSTATUS v7; // edi
  char *v8; // r14
  char v9; // r12
  int v10; // ebx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // kr00_8
  unsigned __int64 v13; // rdx
  char v14; // r10
  __int64 v15; // r8
  char v16; // r9
  int v17; // ebx
  int v18; // ebx
  __int64 v19; // rdx
  unsigned __int64 v20; // rtt
  char v21; // al
  char v22; // cl
  signed __int64 v23; // rax
  signed __int64 v24; // rtt
  int v25; // ecx
  char v26; // al
  struct _RDBSS_DEVICE_OBJECT *v27; // rbx
  char *v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rbx
  PDEVICE_OBJECT v31; // rcx
  int v32; // edx
  __int64 v33; // rdx
  unsigned __int64 v34; // rtt
  char v35; // al
  char v36; // cl
  signed __int64 v37; // rax
  signed __int64 v38; // rtt
  __int64 v39; // r9
  ULONG v40; // r8d
  __int64 v41; // rdx
  PRX_CONTEXT v42; // rbx
  __int64 v43; // r8
  int v44; // eax
  PRX_CONTEXT v45; // rax
  PMRX_FCB pFcb; // rdx
  int Flink_high; // ecx
  bool v48; // al
  PMRX_FOBX pFobx; // rcx
  _DWORD *Context2; // rdx
  PMRX_FCB v51; // rcx
  __int64 v52; // rdx
  KIRQL v53; // r8
  void (__stdcall *v54)(PDEVICE_OBJECT, PIRP); // rax
  unsigned __int64 v55; // rtt
  __int64 v56; // rdx
  unsigned __int64 v57; // rtt
  __int64 v58; // rdx
  char *v59; // r15
  __int64 v60; // rdx
  NTSTATUS (__stdcall *v61)(PRX_CONTEXT, PIRP); // r14
  char v62; // al
  char v63; // cl
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *Flink; // rax
  __int64 LowPart; // r9
  PIRP CurrentIrp; // rax
  char v68; // bl
  __int64 v69; // r8
  unsigned __int64 v70; // rax
  unsigned __int64 v71; // rtt
  unsigned __int64 v72; // rdx
  bool v73; // zf
  signed __int64 v74; // rax
  unsigned __int64 v75; // rdx
  unsigned __int64 v76; // rax
  __int64 v77; // r8
  unsigned __int64 v78; // rax
  unsigned __int64 v79; // rtt
  unsigned __int64 v80; // rdx
  signed __int64 v81; // rax
  unsigned __int64 v82; // rax
  struct _LIST_ENTRY *v83; // r9
  signed __int64 *v84; // r8
  unsigned __int64 v85; // rtt
  signed __int64 i; // rdx
  signed __int64 v87; // rax
  signed __int64 *v88; // rdx
  unsigned __int64 v89; // rax
  __int64 v90; // rdx
  __int64 v91; // r8
  int v93; // [rsp+28h] [rbp-190h]
  BOOLEAN IsOperationSynchronous; // [rsp+60h] [rbp-158h]
  char v95; // [rsp+61h] [rbp-157h]
  char v96; // [rsp+62h] [rbp-156h]
  char v97; // [rsp+63h] [rbp-155h]
  char v98; // [rsp+68h] [rbp-150h] BYREF
  BOOLEAN v99; // [rsp+69h] [rbp-14Fh]
  int v100; // [rsp+6Ch] [rbp-14Ch]
  char v101; // [rsp+70h] [rbp-148h]
  char v102; // [rsp+71h] [rbp-147h]
  char v103; // [rsp+72h] [rbp-146h]
  char v104; // [rsp+73h] [rbp-145h]
  bool v105; // [rsp+74h] [rbp-144h]
  char v106; // [rsp+75h] [rbp-143h]
  char v107; // [rsp+76h] [rbp-142h]
  BOOLEAN v108; // [rsp+77h] [rbp-141h]
  int v109; // [rsp+78h] [rbp-140h]
  int v110; // [rsp+7Ch] [rbp-13Ch]
  unsigned __int16 v111; // [rsp+80h] [rbp-138h]
  int v112; // [rsp+84h] [rbp-134h]
  char v113; // [rsp+88h] [rbp-130h]
  char v114; // [rsp+89h] [rbp-12Fh]
  char v115; // [rsp+8Ah] [rbp-12Eh]
  char v116; // [rsp+8Bh] [rbp-12Dh]
  __int64 v117; // [rsp+90h] [rbp-128h] BYREF
  char *v118; // [rsp+98h] [rbp-120h]
  unsigned __int64 LowLimit; // [rsp+A0h] [rbp-118h] BYREF
  int v120; // [rsp+A8h] [rbp-110h]
  int v121; // [rsp+ACh] [rbp-10Ch]
  int v122; // [rsp+B0h] [rbp-108h]
  LARGE_INTEGER Interval; // [rsp+B8h] [rbp-100h] BYREF
  PRX_CONTEXT RxContext; // [rsp+C0h] [rbp-F8h]
  int v125; // [rsp+C8h] [rbp-F0h]
  signed __int64 v126; // [rsp+D0h] [rbp-E8h]
  signed __int64 v127; // [rsp+D8h] [rbp-E0h]
  NTSTATUS (__stdcall *v128)(PRX_CONTEXT, PIRP); // [rsp+E0h] [rbp-D8h]
  unsigned __int64 HighLimit; // [rsp+E8h] [rbp-D0h] BYREF
  int v130; // [rsp+F0h] [rbp-C8h]
  ULONG v131; // [rsp+F4h] [rbp-C4h]
  int v132; // [rsp+F8h] [rbp-C0h]
  int v133; // [rsp+FCh] [rbp-BCh]
  int v134; // [rsp+100h] [rbp-B8h]
  void (__stdcall *v135)(PDEVICE_OBJECT, PIRP); // [rsp+108h] [rbp-B0h]
  PRX_CONTEXT v136; // [rsp+110h] [rbp-A8h]
  char *v137; // [rsp+118h] [rbp-A0h]
  __int64 v138; // [rsp+120h] [rbp-98h]
  __int64 v139; // [rsp+128h] [rbp-90h]
  struct _RX_TOPLEVELIRP_CONTEXT TopLevelContext; // [rsp+130h] [rbp-88h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = *(char **)(a2 + 184);
  v118 = v8;
  v137 = v8;
  v106 = *v8;
  v107 = v106;
  RxContext = 0;
  memset(&TopLevelContext, 0, 40);
  v100 = 0;
  v9 = 0;
  v97 = 0;
  v95 = 0;
  v108 = KeAreApcsDisabled();
  v10 = 0;
  v110 = 0;
  v112 = 0;
  v117 = 0;
  LowLimit = 0;
  KeEnterCriticalRegion();
  v99 = RxTryToBecomeTheTopLevelIrp(&TopLevelContext, (PIRP)a2, a4, 0);
  IsOperationSynchronous = 1;
  v96 = 1;
  v135 = RxCancelRoutine;
  v12 = v11;
  v13 = 0x140000000uLL;
  switch ( *v8 )
  {
    case 2:
    case 18:
      v96 = 0;
      v9 = 1;
      v97 = 1;
      v114 = 1;
      goto LABEL_9;
    case 3:
    case 4:
    case 5:
    case 6:
    case 7:
    case 8:
    case 9:
    case 10:
    case 11:
    case 12:
    case 14:
    case 17:
    case 20:
    case 21:
      IsOperationSynchronous = IoIsOperationSynchronous((PIRP)a2);
      goto LABEL_9;
    case 13:
      if ( a3 )
        IsOperationSynchronous = IoIsOperationSynchronous((PIRP)a2);
      else
        IsOperationSynchronous = 1;
      if ( *((_DWORD *)v8 + 6) != 1311244 )
        goto LABEL_9;
      v14 = 1;
      v95 = 1;
      v113 = 1;
      break;
    default:
      v13 = v12;
LABEL_9:
      v14 = 0;
      break;
  }
  v130 = 1;
  if ( !a4->RDBSSDeviceObject )
    goto LABEL_11;
  if ( *v8 )
  {
    v111 = RxDecodeFileObject2(*((_QWORD *)v8 + 6), &LowLimit, &v117);
    v13 = 60451;
    if ( v111 == 60451 )
    {
      if ( (v16 != 13 || *((_DWORD *)v8 + 6) != 1311648)
        && ((unsigned __int8)(v16 - 14) > 1u || *((_DWORD *)v8 + 6) != 1311123) )
      {
        goto LABEL_28;
      }
      v10 = 1;
LABEL_27:
      v109 = v10;
LABEL_28:
      v15 = 2;
      goto LABEL_29;
    }
    if ( v111 != 60452 )
    {
      if ( v111 != 60454 )
      {
        if ( v111 != 60456 )
        {
          v15 = 2;
          v10 = 2;
          v109 = 2;
          goto LABEL_29;
        }
        if ( v16 == 18 )
          goto LABEL_28;
      }
      v10 = 3;
      goto LABEL_27;
    }
LABEL_11:
    v10 = 0;
    goto LABEL_27;
  }
  v111 = RxClassifyCreate(v8);
  v13 = 60451;
  v15 = 2;
  if ( v111 != 0xEC23 )
  {
    v10 = 1;
    v109 = 1;
  }
LABEL_29:
  if ( !v10 )
  {
LABEL_44:
    v26 = 1;
LABEL_45:
    v27 = a4;
    goto LABEL_46;
  }
  v17 = v10 - 1;
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( v18 )
    {
      if ( v18 != 1 )
      {
        __int2c();
        goto LABEL_44;
      }
      v19 = *(_QWORD *)(*(_QWORD *)(v117 + 32) + 40LL);
      _m_prefetchw((const void *)(v19 + 440));
      v138 = *(_QWORD *)(v19 + 440);
      v20 = v138 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v20 == _InterlockedCompareExchange64(
                    (volatile signed __int64 *)(v19 + 440),
                    (v138 & 0xFFFFFFFFFFFFFFFEuLL) + 2,
                    v138 & 0xFFFFFFFFFFFFFFFEuLL) )
      {
        v121 = 1;
        v21 = 1;
        v22 = 1;
      }
      else
      {
        v121 = 0;
        v126 = 0;
        v23 = *(_QWORD *)(v19 + 440);
        TopLevelContext.Irp = (PIRP)v23;
        v126 = v23;
        if ( (v23 & 1) != 0 )
        {
LABEL_39:
          v21 = 0;
          v22 = 0;
        }
        else
        {
          while ( 1 )
          {
            v24 = v23;
            v23 = _InterlockedCompareExchange64((volatile signed __int64 *)(v19 + 440), v23 + 2, v23);
            if ( v24 == v23 )
              break;
            v126 = v23;
            v122 = 0;
            if ( (v23 & 1) != 0 )
              goto LABEL_39;
          }
          v122 = 1;
          v21 = 1;
          v22 = 1;
        }
        v101 = v21;
      }
      v102 = v21;
      v115 = v21;
      if ( v22 )
      {
        v25 = 3;
LABEL_43:
        v110 = v25;
        v112 = v25;
        goto LABEL_44;
      }
      if ( v9 )
      {
        v29 = *((_QWORD *)v8 + 6);
        if ( v29 )
          v30 = *(_QWORD *)(v29 + 24);
        else
          v30 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qllqq(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            (unsigned __int8)*v8,
            a2,
            (unsigned __int8)*v8,
            (unsigned __int8)v8[1],
            v29,
            v30);
        }
        if ( !v30 )
          goto LABEL_44;
        if ( (FCB *)v30 == &RxDeviceFCB )
          goto LABEL_44;
        if ( (*(_WORD *)v30 & 0xFFF0) != 0xEC20 )
          goto LABEL_44;
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_44;
        }
        v32 = 15;
        goto LABEL_70;
      }
    }
    else
    {
      v33 = *(_QWORD *)(v117 + 104);
      _m_prefetchw((const void *)(v33 + 8));
      v139 = *(_QWORD *)(v33 + 8);
      v34 = v139 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v34 == _InterlockedCompareExchange64(
                    (volatile signed __int64 *)(v33 + 8),
                    (v139 & 0xFFFFFFFFFFFFFFFEuLL) + 2,
                    v139 & 0xFFFFFFFFFFFFFFFEuLL) )
      {
        v125 = 1;
        v35 = 1;
        v36 = 1;
      }
      else
      {
        v125 = 0;
        v127 = 0;
        v37 = *(_QWORD *)(v33 + 8);
        *(_QWORD *)&TopLevelContext.Flags = v37;
        v127 = v37;
        if ( (v37 & 1) != 0 )
        {
LABEL_76:
          v35 = 0;
          v36 = 0;
        }
        else
        {
          while ( 1 )
          {
            v38 = v37;
            v37 = _InterlockedCompareExchange64((volatile signed __int64 *)(v33 + 8), v37 + 2, v37);
            if ( v38 == v37 )
              break;
            v127 = v37;
            v120 = 0;
            if ( (v37 & 1) != 0 )
              goto LABEL_76;
          }
          v120 = 1;
          v35 = 1;
          v36 = 1;
        }
        v103 = v35;
      }
      v104 = v35;
      v116 = v35;
      if ( v36 )
      {
        v25 = 2;
        goto LABEL_43;
      }
      if ( v9 )
      {
        v39 = *((_QWORD *)v8 + 6);
        if ( v39 )
          v30 = *(_QWORD *)(v39 + 24);
        else
          v30 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qllqq(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            (unsigned __int8)*v8,
            a2,
            (unsigned __int8)*v8,
            (unsigned __int8)v8[1],
            v39,
            v30);
        }
        if ( !v30 )
          goto LABEL_44;
        if ( (FCB *)v30 == &RxDeviceFCB )
          goto LABEL_44;
        if ( (*(_WORD *)v30 & 0xFFF0) != 0xEC20 )
          goto LABEL_44;
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_44;
        }
        v32 = 17;
LABEL_70:
        WPP_SF_llZ(v31->AttachedDevice, v32, v15, *(_DWORD *)(v30 + 192), *(_DWORD *)(v30 + 184), v30 + 336);
        goto LABEL_44;
      }
      if ( v14 )
        goto LABEL_44;
    }
    v26 = 0;
    v7 = -1073741628;
    goto LABEL_45;
  }
  v27 = a4;
  if ( (unsigned __int8)RfsAcquireRundownProtectionCacheAware(
                          a4->RxNetNameTableInDeviceObject.HashBuckets[30].Flink,
                          v13,
                          2) )
  {
    v110 = 1;
    v112 = 1;
    v26 = 1;
  }
  else
  {
    v26 = 0;
    v7 = -1073741573;
  }
LABEL_46:
  if ( !v26 )
  {
    v28 = v118;
    if ( *v118 == 12 && v118[1] == 2 )
    {
      v100 = 874;
      *(_DWORD *)(a2 + 48) = v7;
      *(_QWORD *)(a2 + 56) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        LOWORD(v93) = (unsigned __int8)*v28;
        WPP_SF_qqhDD(WPP_GLOBAL_Control->AttachedDevice, 20, v15, v27, a2, v93, v7);
      }
      IofCompleteRequest((PIRP)a2, 0);
    }
    else
    {
      if ( v7 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, v118, v15, 0, v7);
        v28 = v118;
      }
      v100 = 847;
      *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
      *(_DWORD *)(a2 + 48) = v7;
      *(_QWORD *)(a2 + 56) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        LOWORD(v93) = (unsigned __int8)*v28;
        WPP_SF_qqhDD(WPP_GLOBAL_Control->AttachedDevice, 19, v15, v27, a2, v93, v7);
      }
      IofCompleteRequest((PIRP)a2, 0);
      v7 = 259;
    }
    goto LABEL_215;
  }
  v40 = 0;
  if ( IsOperationSynchronous )
    v40 = 2;
  v131 = v40;
  v42 = RxCreateRxContextEx((PIRP)a2, v27, v40, 0);
  TopLevelContext.Previous = v42;
  RxContext = v42;
  if ( !v42 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      LOWORD(v93) = (unsigned __int8)*v118;
      WPP_SF_qqhq(WPP_GLOBAL_Control->AttachedDevice, v41, v43, a4, a2, v93, 0);
    }
    v7 = -1073741670;
    v100 = 907;
    RxCompleteRequestEx(0, (PIRP)a2);
    goto LABEL_215;
  }
  v44 = v110;
  v42->TrackerHistory[9].Flags = v110;
  if ( v44 == 2 )
  {
    *(_QWORD *)&v42->TrackerHistory[10].AcquireRelease = *(_QWORD *)(v117 + 104) + 8LL;
  }
  else if ( v44 == 3 )
  {
    v42->TrackerHistory[10].FileName = (PSZ)(*(_QWORD *)(*(_QWORD *)(v117 + 32) + 40LL) + 440LL);
  }
  v110 = 0;
  v112 = 0;
  v136 = v42;
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 2) != 0 )
    McTemplateK0ppppphzr5h_EtwWriteTransfer(
      *(_WORD *)(a3 + 88) >> 1,
      a3,
      (_DWORD)v42 + 412,
      a2,
      (char)v42,
      *(_QWORD *)(a3 + 24),
      *(_QWORD *)(a3 + 32),
      a3,
      *(_WORD *)(a3 + 88) >> 1,
      *(_QWORD *)(a3 + 96),
      *v118);
  v45 = *(PRX_CONTEXT *)&TopLevelContext.Signature;
  if ( v99 )
    v45 = v42;
  *(_QWORD *)&TopLevelContext.Signature = v45;
  pFcb = v42->pFcb;
  if ( pFcb
    && (pFcb->Header.NodeTypeCode & 0xFFF0) == 0xEC20
    && pFcb->Header.NodeTypeCode != -5084
    && *(_QWORD *)&pFcb->OpenCount
    && LOBYTE(v42->RealDevice)
    && ((__int64)v42->RdbssDbgExtension & 0x20) == 0 )
  {
    v98 = 0;
    if ( !(unsigned __int8)RxWaitForStableLViewOnFcbAndAcquireRundown((PRX_BLOCK_CONDITION)v42, pFcb, (__int64)&v98)
      && !v98 )
    {
      v7 = -1073741740;
      v100 = 1004;
      RxCompleteRequestEx(v42, v42->CurrentIrp);
      goto LABEL_215;
    }
    if ( !v97 && !v95 )
    {
      Flink_high = HIDWORD(v42->pFcb->SrvOpenList.Flink);
      v48 = (Flink_high & 0x80) != 0;
      v105 = v48;
      if ( (Flink_high & 0x80) == 0 )
      {
        pFobx = v42->pFobx;
        if ( pFobx )
        {
          Context2 = pFobx->Context2;
          if ( Context2 )
          {
            v48 = (Context2[18] & 0x400) != 0;
            v105 = v48;
          }
        }
      }
      if ( v48 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, &WPP_5c53749fd3ed399097fde467b06e4f03_Traceguids);
        }
        v7 = -1073741628;
        v100 = 1031;
        RxCompleteRequestEx(v42, v42->CurrentIrp);
        goto LABEL_215;
      }
    }
    v51 = v42->pFcb;
    if ( (HIDWORD(v51->SrvOpenList.Flink) & 0x80u) == 0
      && v42->LockManagerContext
      && v42->NonPagedFcb != *(PNON_PAGED_FCB *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v51->OpenCount + 32LL) + 32LL)
                                               + 48LL) )
    {
      v7 = -1073741802;
      v100 = 1066;
      RxCompleteRequestEx(v42, v42->CurrentIrp);
      goto LABEL_215;
    }
  }
  if ( *(_BYTE *)(a2 + 68) )
  {
    v7 = -1073741536;
    v100 = 1079;
    RxCompleteRequestEx(v42, v42->CurrentIrp);
    goto LABEL_215;
  }
  v52 = ((_BYTE)RxActiveContextNodeBucketSize * (unsigned __int8)LOWORD(v42->LowIoContext.ParamsFor.ReadWrite.Flags)
       + (unsigned __int8)(WORD1(v42->LowIoContext.ParamsFor.Locks.Length) % (unsigned int)RxActiveContextNodeBucketSize))
      & 0x3F;
  v132 = ((_BYTE)RxActiveContextNodeBucketSize * (unsigned __int8)LOWORD(v42->LowIoContext.ParamsFor.ReadWrite.Flags)
        + (unsigned __int8)(WORD1(v42->LowIoContext.ParamsFor.Locks.Length) % (unsigned int)RxActiveContextNodeBucketSize))
       & 0x3F;
  v53 = KeAcquireSpinLockRaiseToDpc(&SpinLock[24 * v52]);
  v54 = 0;
  if ( v96 )
    v54 = RxCancelRoutine;
  _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)v54);
  if ( *(_BYTE *)(a2 + 68) )
  {
    _InterlockedExchange64((volatile __int64 *)(a2 + 104), 0);
    _InterlockedExchange64((volatile __int64 *)(a2 + 120), 0);
    v55 = WORD1(v42->LowIoContext.ParamsFor.Locks.Length);
    v56 = ((_BYTE)RxActiveContextNodeBucketSize * (unsigned __int8)LOWORD(v42->LowIoContext.ParamsFor.ReadWrite.Flags)
         + (unsigned __int8)(v55 % (unsigned int)RxActiveContextNodeBucketSize))
        & 0x3F;
    v133 = ((_BYTE)RxActiveContextNodeBucketSize * (unsigned __int8)LOWORD(v42->LowIoContext.ParamsFor.ReadWrite.Flags)
          + (unsigned __int8)((unsigned int)v55 % RxActiveContextNodeBucketSize))
         & 0x3F;
    KeReleaseSpinLock(&SpinLock[24 * v56], v53);
    v7 = -1073741536;
    v100 = 1108;
    RxCompleteRequestEx(v42, v42->CurrentIrp);
    goto LABEL_215;
  }
  v57 = WORD1(v42->LowIoContext.ParamsFor.Locks.Length);
  v58 = ((_BYTE)RxActiveContextNodeBucketSize * (unsigned __int8)LOWORD(v42->LowIoContext.ParamsFor.ReadWrite.Flags)
       + (unsigned __int8)(v57 % (unsigned int)RxActiveContextNodeBucketSize))
      & 0x3F;
  v134 = ((_BYTE)RxActiveContextNodeBucketSize * (unsigned __int8)LOWORD(v42->LowIoContext.ParamsFor.ReadWrite.Flags)
        + (unsigned __int8)((unsigned int)v57 % RxActiveContextNodeBucketSize))
       & 0x3F;
  KeReleaseSpinLock(&SpinLock[24 * v58], v53);
  *(_QWORD *)(a2 + 56) = 0;
  *(_DWORD *)(a2 + 48) = 0;
  v59 = v118;
  v60 = (unsigned __int8)*v118;
  v61 = *(NTSTATUS (__stdcall **)(PRX_CONTEXT, PIRP))(a1 + 16 * v60);
  v128 = v61;
  if ( (_DWORD)v60 != 3 && (_DWORD)v60 != 4 )
    goto LABEL_162;
  v62 = v118[1];
  if ( (v62 & 4) != 0 )
  {
    v61 = RxCompleteMdl;
    v128 = RxCompleteMdl;
    goto LABEL_162;
  }
  if ( (v62 & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_5c53749fd3ed399097fde467b06e4f03_Traceguids);
    }
    v63 = 1;
    goto LABEL_163;
  }
  if ( (_BYTE)v60 != 3
    || (HighLimit = 0,
        LowLimit = 0,
        IoGetStackLimits(&LowLimit, &HighLimit),
        TopLevelContext.Thread = (PETHREAD)((char *)&HighLimit - LowLimit),
        (unsigned __int64)&HighLimit - LowLimit >= 0xE00) )
  {
LABEL_162:
    v63 = 0;
LABEL_163:
    v42->OverflowListEntry.Blink = (struct _LIST_ENTRY *)v61;
    if ( v61 )
    {
      BYTE2(v42->RealDevice) = 1;
      if ( v63 )
      {
        v7 = RxFsdPostRequest(v42);
      }
      else
      {
        do
        {
          v42->StoredStatus = 0;
          Blink = v42->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
          if ( Blink )
          {
            Flink = Blink[42].Flink;
            if ( Flink )
            {
              LOBYTE(v60) = 1;
              ((void (__fastcall *)(PRX_CONTEXT, __int64))Flink)(v42, v60);
            }
          }
          v7 = ((__int64 (__fastcall *)(PRX_CONTEXT, __int64))v61)(v42, a2);
          if ( v7 == -1069481983 )
          {
            LowPart = v42->Create.NtCreateParameters.AllocationSize.LowPart;
            if ( (_DWORD)LowPart )
            {
              Interval.QuadPart = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  25,
                  &WPP_5c53749fd3ed399097fde467b06e4f03_Traceguids,
                  LowPart);
              }
              Interval.QuadPart = -10000;
              Interval.QuadPart = -10000LL * v42->Create.NtCreateParameters.AllocationSize.LowPart;
              KeDelayExecutionThread(0, 0, &Interval);
              v42->Create.NtCreateParameters.AllocationSize.LowPart = 0;
            }
          }
        }
        while ( v7 == -1069481983 );
        if ( v7 != 259 )
        {
          CurrentIrp = v42->CurrentIrp;
          if ( !CurrentIrp
            || CurrentIrp != (PIRP)a2
            || (char *)v42->CurrentIrpSp != v59
            || LOBYTE(v42->RealDevice) != *v59
            || BYTE1(v42->RealDevice) != v59[1] )
          {
            DbgPrint("RXCONTEXT CONTAMINATED!!!!  (RxContext = %p)\n", v42);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                26,
                &WPP_5c53749fd3ed399097fde467b06e4f03_Traceguids,
                a2,
                v42->CurrentIrp);
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                27,
                &WPP_5c53749fd3ed399097fde467b06e4f03_Traceguids,
                v59,
                v42->CurrentIrpSp);
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_Dd(
                WPP_GLOBAL_Control->AttachedDevice,
                28,
                &WPP_5c53749fd3ed399097fde467b06e4f03_Traceguids,
                (unsigned __int8)*v59,
                LOBYTE(v42->RealDevice));
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_Dd(
                WPP_GLOBAL_Control->AttachedDevice,
                29,
                &WPP_5c53749fd3ed399097fde467b06e4f03_Traceguids,
                (unsigned __int8)v59[1],
                BYTE1(v42->RealDevice));
            }
          }
          BYTE2(v42->RealDevice) = 0;
          RxCompleteRequestEx(v42, v42->CurrentIrp);
          LODWORD(v118) = v7;
        }
      }
    }
    else
    {
      v7 = -1073741822;
    }
    goto LABEL_215;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_5c53749fd3ed399097fde467b06e4f03_Traceguids);
  }
  BYTE2(v42->RealDevice) = 1;
  v7 = RxPostStackOverflowRead(v42, *(PFCB *)(*((_QWORD *)v59 + 6) + 24LL));
  if ( v7 != 259 )
  {
    BYTE2(v42->RealDevice) = 0;
    RxCompleteRequestEx(v42, v42->CurrentIrp);
  }
LABEL_215:
  v68 = v106;
  if ( !v110 )
    goto LABEL_267;
  if ( v110 == 1 )
  {
    v83 = a4->RxNetNameTableInDeviceObject.HashBuckets[30].Flink;
    v84 = (signed __int64 *)((char *)v83->Flink
                           + (unsigned int)(HIDWORD(v83[1].Flink)
                                          * (HIDWORD(KeGetPcr()[1].LockArray) % LODWORD(v83[1].Blink))));
    _m_prefetchw(v84);
    v85 = *v84 & 0xFFFFFFFFFFFFFFFEuLL;
    if ( v85 == _InterlockedCompareExchange64(v84, v85 - 2, v85) )
      goto LABEL_267;
    for ( i = *v84; ; i = *v88 )
    {
      while ( (i & 1) == 0 )
      {
        v87 = _InterlockedCompareExchange64(v84, i - 2, i);
        v73 = i == v87;
        i = v87;
        if ( v73 )
          goto LABEL_267;
      }
      if ( i != 1 )
        break;
      v88 = (signed __int64 *)v83->Flink;
      if ( v84 == (signed __int64 *)v83->Flink )
        __int2c();
      v84 = (signed __int64 *)v83->Flink;
      _m_prefetchw(v88);
    }
    v75 = i & 0xFFFFFFFFFFFFFFFEuLL;
    v89 = _InterlockedExchangeAdd64((volatile signed __int64 *)v75, 0xFFFFFFFFFFFFFFFEuLL);
    if ( v89 == 3 )
    {
      if ( (*(_DWORD *)(v75 + 32) & 1) != 0 )
        goto LABEL_262;
      goto LABEL_263;
    }
    if ( (v89 & 1) == 0 || v89 > 3 )
      goto LABEL_267;
    goto LABEL_266;
  }
  if ( v110 != 2 )
  {
    if ( v110 == 3 )
    {
      v69 = *(_QWORD *)(*(_QWORD *)(v117 + 32) + 40LL);
      _m_prefetchw((const void *)(v69 + 440));
      v70 = *(_QWORD *)(v69 + 440) & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v70 >= 2 )
      {
        v71 = *(_QWORD *)(v69 + 440) & 0xFFFFFFFFFFFFFFFEuLL;
        LOBYTE(v6) = v71 == _InterlockedCompareExchange64((volatile signed __int64 *)(v69 + 440), v70 - 2, v70);
      }
      if ( v6 )
        goto LABEL_267;
      _m_prefetchw((const void *)(v69 + 440));
      v72 = *(_QWORD *)(v69 + 440);
      if ( (v72 & 1) == 0 )
      {
        do
        {
          if ( v72 < 2 )
            __int2c();
          v74 = _InterlockedCompareExchange64((volatile signed __int64 *)(v69 + 440), v72 - 2, v72);
          v73 = v72 == v74;
          v72 = v74;
          if ( v73 )
            goto LABEL_267;
        }
        while ( (v74 & 1) == 0 );
      }
      v75 = v72 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( !v75 )
        __int2c();
      v76 = _InterlockedExchangeAdd64((volatile signed __int64 *)v75, 0xFFFFFFFFFFFFFFFEuLL);
      if ( v76 == 3 )
      {
        if ( (*(_DWORD *)(v75 + 32) & 1) != 0 )
          goto LABEL_262;
        goto LABEL_263;
      }
      if ( (v76 & 1) == 0 || v76 > 3 )
        goto LABEL_267;
    }
    goto LABEL_266;
  }
  v77 = *(_QWORD *)(v117 + 104);
  _m_prefetchw((const void *)(v77 + 8));
  v78 = *(_QWORD *)(v77 + 8) & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v78 >= 2 )
  {
    v79 = *(_QWORD *)(v77 + 8) & 0xFFFFFFFFFFFFFFFEuLL;
    LOBYTE(v6) = v79 == _InterlockedCompareExchange64((volatile signed __int64 *)(v77 + 8), v78 - 2, v78);
  }
  if ( v6 )
    goto LABEL_267;
  _m_prefetchw((const void *)(v77 + 8));
  v80 = *(_QWORD *)(v77 + 8);
  if ( (v80 & 1) != 0 )
  {
LABEL_243:
    v75 = v80 & 0xFFFFFFFFFFFFFFFEuLL;
    if ( !v75 )
      __int2c();
    v82 = _InterlockedExchangeAdd64((volatile signed __int64 *)v75, 0xFFFFFFFFFFFFFFFEuLL);
    if ( v82 == 3 )
    {
      if ( (*(_DWORD *)(v75 + 32) & 1) != 0 )
      {
LABEL_262:
        _m_prefetchw((const void *)(v75 + 32));
        if ( (_InterlockedAnd((volatile signed __int32 *)(v75 + 32), 0xFFFFFFFE) & 1) != 0 )
          goto LABEL_267;
      }
LABEL_263:
      KeSetEvent((PRKEVENT)(v75 + 8), 0, 0);
      goto LABEL_267;
    }
    if ( (v82 & 1) == 0 || v82 > 3 )
      goto LABEL_267;
LABEL_266:
    __int2c();
    goto LABEL_267;
  }
  while ( 1 )
  {
    if ( v80 < 2 )
      __int2c();
    v81 = _InterlockedCompareExchange64((volatile signed __int64 *)(v77 + 8), v80 - 2, v80);
    v73 = v80 == v81;
    v80 = v81;
    if ( v73 )
      break;
    if ( (v81 & 1) != 0 )
      goto LABEL_243;
  }
LABEL_267:
  if ( v99 )
    RxUnwindTopLevelIrp(&TopLevelContext);
  KeLeaveCriticalRegion();
  if ( KeAreApcsDisabled() != v108 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, &WPP_5c53749fd3ed399097fde467b06e4f03_Traceguids);
    }
    __debugbreak();
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_hLd(WPP_GLOBAL_Control->AttachedDevice, v90, v91, (unsigned int)v68, v7, v100);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140015290  mov     r11, rsp
0x140015293  mov     [r11+20h], r9
0x140015297  mov     [r11+18h], r8
0x14001529b  mov     [r11+8], rcx
0x14001529f  push    rbx
0x1400152a0  push    rsi
0x1400152a1  push    rdi
0x1400152a2  push    r12
0x1400152a4  push    r13
0x1400152a6  push    r14
0x1400152a8  push    r15
0x1400152aa  sub     rsp, 180h
0x1400152b1  mov     r15, r8
0x1400152b4  mov     r13, rdx
0x1400152b7  xor     esi, esi
0x1400152b9  mov     edi, esi
0x1400152bb  mov     r14, [rdx+0B8h]
0x1400152c2  mov     [rsp+1B8h+var_120], r14
0x1400152ca  mov     [rsp+1B8h+var_A0], r14
0x1400152d2  movzx   eax, byte ptr [r14]
0x1400152d6  mov     [rsp+1B8h+var_143], al
0x1400152da  mov     [rsp+1B8h+var_142], al
0x1400152de  mov     [r11-0F8h], rsi
0x1400152e5  xorps   xmm0, xmm0
0x1400152e8  xor     eax, eax
0x1400152ea  movups  xmmword ptr [rsp+1B8h+TopLevelContext], xmm0
0x1400152f2  movups  xmmword ptr [r11-78h], xmm0
0x1400152f7  mov     [r11-68h], rax
0x1400152fb  mov     dword ptr [rsp+1B8h+var_150+4], esi
0x1400152ff  mov     [rsp+1B8h+var_157], al
0x140015303  mov     [rsp+1B8h+var_158], al
0x140015307  mov     [rsp+1B8h+var_156], al
0x14001530b  xor     r12b, r12b
0x14001530e  mov     [rsp+1B8h+var_155], r12b
0x140015313  mov     [rsp+1B8h+var_157], al
0x140015317  mov     byte ptr [r11+10h], 1
0x14001531c  call    cs:__imp_KeAreApcsDisabled
0x140015323  nop     dword ptr [rax+rax+00h]
0x140015328  mov     [rsp+1B8h+var_141], al
0x14001532c  mov     ebx, esi
0x14001532e  mov     eax, esi
0x140015330  mov     [rsp+1B8h+var_13C], eax
0x140015334  mov     [rsp+1B8h+var_134], eax
0x14001533b  mov     [rsp+1B8h+var_128], rsi
0x140015343  mov     [rsp+1B8h+LowLimit], rsi
0x14001534b  call    cs:__imp_KeEnterCriticalRegion
0x140015352  nop     dword ptr [rax+rax+00h]
0x140015357  xor     r9d, r9d; ForceTopLevel
0x14001535a  mov     r8, [rsp+1B8h+RxDeviceObject]; RxDeviceObject
0x140015362  mov     rdx, r13; Irp
0x140015365  lea     rcx, [rsp+1B8h+TopLevelContext]; TopLevelContext
0x14001536d  call    RxTryToBecomeTheTopLevelIrp
0x140015372  mov     byte ptr [rsp+1B8h+var_150+1], al
0x140015376  mov     [rsp+1B8h+var_158], 1
0x14001537b  mov     [rsp+1B8h+var_156], 1
0x140015380  lea     rax, RxCancelRoutine
0x140015387  mov     [rsp+1B8h+var_B0], rax
0x14001538f  movzx   eax, byte ptr [r14]
0x140015393  add     eax, 0FFFFFFFEh; switch 20 cases
0x140015396  cmp     eax, 13h
0x140015399  ja      def_1400153BA; jumptable 00000001400153BA default case, cases 15,16,19
0x14001539f  cdqe
0x1400153a1  lea     rdx, cs:140000000h
0x1400153a8  movzx   eax, ds:(byte_14002AC88 - 140000000h)[rdx+rax]
0x1400153b0  mov     ecx, ds:(jpt_1400153BA - 140000000h)[rdx+rax*4]
0x1400153b7  add     rcx, rdx
0x1400153ba  jmp     rcx; switch jump
0x1400153c0  test    r15, r15; jumptable 00000001400153BA case 13
0x1400153c3  jnz     short loc_1400153CC
0x1400153c5  mov     [rsp+1B8h+var_158], 1
0x1400153ca  jmp     short loc_1400153DF
0x1400153cc  mov     rcx, r13; Irp
0x1400153cf  call    cs:__imp_IoIsOperationSynchronous
0x1400153d6  nop     dword ptr [rax+rax+00h]
0x1400153db  mov     [rsp+1B8h+var_158], al
0x1400153df  cmp     dword ptr [r14+18h], 14020Ch
0x1400153e7  jnz     short def_1400153BA; jumptable 00000001400153BA default case, cases 15,16,19
0x1400153e9  mov     r10b, 1
0x1400153ec  mov     [rsp+1B8h+var_157], r10b
0x1400153f1  mov     [rsp+1B8h+var_130], r10b
0x1400153f9  jmp     short loc_140015428
0x1400153fb  mov     rcx, r13; jumptable 00000001400153BA cases 3-12,14,17,20,21
0x1400153fe  call    cs:__imp_IoIsOperationSynchronous
0x140015405  nop     dword ptr [rax+rax+00h]
0x14001540a  mov     [rsp+1B8h+var_158], al
0x14001540e  jmp     short def_1400153BA; jumptable 00000001400153BA default case, cases 15,16,19
0x140015410  mov     [rsp+1B8h+var_156], 0; jumptable 00000001400153BA cases 2,18
0x140015415  mov     r12b, 1
0x140015418  mov     [rsp+1B8h+var_155], r12b
0x14001541d  mov     [rsp+1B8h+var_12F], r12b
0x140015425  xor     r10b, r10b; jumptable 00000001400153BA default case, cases 15,16,19
0x140015428  mov     [rsp+1B8h+arg_8], 1
0x140015430  mov     [rsp+1B8h+var_C8], 1
0x14001543b  mov     rax, [rsp+1B8h+RxDeviceObject]
0x140015443  cmp     qword ptr [rax+160h], 0
0x14001544b  jnz     short loc_140015454
0x14001544d  mov     ebx, esi
0x14001544f  jmp     loc_140015510
0x140015454  movzx   r9d, byte ptr [r14]
0x140015458  test    r9b, r9b
0x14001545b  jnz     short loc_14001548F
0x14001545d  mov     rcx, r14
0x140015460  call    RxClassifyCreate
0x140015465  mov     [rsp+1B8h+var_138], ax
0x14001546d  mov     edx, 0EC23h
0x140015472  mov     r8d, 2
0x140015478  cmp     ax, dx
0x14001547b  jz      loc_14001551A
0x140015481  mov     ebx, 1
0x140015486  mov     [rsp+1B8h+var_140], ebx
0x14001548a  jmp     loc_14001551A
0x14001548f  lea     r8, [rsp+1B8h+var_128]
0x140015497  lea     rdx, [rsp+1B8h+LowLimit]
0x14001549f  mov     rcx, [r14+30h]
0x1400154a3  call    RxDecodeFileObject2
0x1400154a8  movzx   ecx, ax
0x1400154ab  mov     [rsp+1B8h+var_138], cx
0x1400154b3  mov     edx, 0EC23h
0x1400154b8  sub     ecx, edx
0x1400154ba  jz      short loc_1400154E7
0x1400154bc  sub     ecx, 1
0x1400154bf  jz      short loc_14001544D
0x1400154c1  sub     ecx, 2
0x1400154c4  jz      short loc_1400154E0
0x1400154c6  cmp     ecx, 2
0x1400154c9  jz      short loc_1400154DA
0x1400154cb  mov     r8d, 2
0x1400154d1  mov     ebx, r8d
0x1400154d4  mov     [rsp+1B8h+var_140], ebx
0x1400154d8  jmp     short loc_14001551A
0x1400154da  cmp     r9b, 12h
0x1400154de  jz      short loc_140015514
0x1400154e0  mov     ebx, 3
0x1400154e5  jmp     short loc_140015510
0x1400154e7  cmp     r9b, 0Dh
0x1400154eb  jnz     short loc_1400154F7
0x1400154ed  cmp     dword ptr [r14+18h], 1403A0h
0x1400154f5  jz      short loc_14001550B
0x1400154f7  sub     r9b, 0Eh
0x1400154fb  cmp     r9b, 1
0x1400154ff  ja      short loc_140015514
0x140015501  cmp     dword ptr [r14+18h], 140193h
0x140015509  jnz     short loc_140015514
0x14001550b  mov     ebx, 1
0x140015510  mov     [rsp+1B8h+var_140], ebx
0x140015514  mov     r8d, 2
0x14001551a  test    ebx, ebx
0x14001551c  jz      loc_140015611
0x140015522  sub     ebx, 1
0x140015525  jz      loc_140015980
0x14001552b  sub     ebx, 1
0x14001552e  jz      loc_1400157C0
0x140015534  cmp     ebx, 1
0x140015537  jz      short loc_140015540
0x140015539  int     2Ch; Windows NT - assertion failure
0x14001553b  jmp     loc_140015611
0x140015540  mov     rax, [rsp+1B8h+var_128]
0x140015548  mov     rcx, [rax+20h]
0x14001554c  mov     rdx, [rcx+28h]
0x140015550  prefetchw byte ptr [rdx+1B8h]
0x140015557  mov     rax, [rdx+1B8h]
0x14001555e  mov     [rsp+1B8h+var_98], rax
0x140015566  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001556a  lea     rcx, [rax+2]
0x14001556e  lock cmpxchg [rdx+1B8h], rcx
0x140015577  jnz     short loc_14001558B
0x140015579  mov     [rsp+1B8h+var_10C], 1
0x140015584  mov     al, 1
0x140015586  movzx   ecx, al
0x140015589  jmp     short loc_1400155EE
0x14001558b  mov     [rsp+1B8h+var_10C], esi
0x140015592  mov     [rsp+1B8h+var_E8], rsi
0x14001559a  mov     rax, [rdx+1B8h]
0x1400155a1  mov     [rsp+1B8h+TopLevelContext.Irp], rax
0x1400155a9  mov     [rsp+1B8h+var_E8], rax
0x1400155b1  test    al, 1
0x1400155b3  jnz     short loc_1400155E6
0x1400155b5  nop     word ptr [rax+rax+00000000h]
0x1400155c0  lea     rcx, [rax+2]
0x1400155c4  lock cmpxchg [rdx+1B8h], rcx
0x1400155cd  jz      loc_1400156B8
0x1400155d3  mov     [rsp+1B8h+var_E8], rax
0x1400155db  mov     [rsp+1B8h+var_108], esi
0x1400155e2  test    al, 1
0x1400155e4  jz      short loc_1400155C0
0x1400155e6  xor     al, al
0x1400155e8  xor     cl, cl
0x1400155ea  mov     [rsp+1B8h+var_148], al
0x1400155ee  mov     [rsp+1B8h+var_147], al
0x1400155f2  mov     [rsp+1B8h+var_12E], al
0x1400155f9  test    cl, cl
0x1400155fb  jz      loc_1400156CD
0x140015601  mov     ecx, 3
0x140015606  mov     [rsp+1B8h+var_13C], ecx
0x14001560a  mov     [rsp+1B8h+var_134], ecx
0x140015611  lea     r12, WPP_GLOBAL_Control
0x140015618  mov     r15d, 0EC20h
0x14001561e  mov     r14d, 0FFF0h
0x140015624  movzx   eax, [rsp+1B8h+arg_8]
0x14001562c  mov     rbx, [rsp+1B8h+RxDeviceObject]
0x140015634  test    al, al
0x140015636  jnz     loc_140015A85
0x14001563c  mov     rdx, [rsp+1B8h+var_120]
0x140015644  cmp     byte ptr [rdx], 0Ch
0x140015647  jnz     loc_1400159DF
0x14001564d  cmp     byte ptr [rdx+1], 2
0x140015651  jnz     loc_1400159DF
0x140015657  mov     dword ptr [rsp+1B8h+var_150+4], 36Ah
0x14001565f  mov     [r13+30h], edi
0x140015663  mov     [r13+38h], rsi
0x140015667  mov     rcx, cs:WPP_GLOBAL_Control
0x14001566e  cmp     rcx, r12
0x140015671  jz      short loc_1400156A2
0x140015673  mov     eax, [rcx+2Ch]
0x140015676  test    al, 4
0x140015678  jz      short loc_1400156A2
0x14001567a  cmp     byte ptr [rcx+29h], 2
0x14001567e  jb      short loc_1400156A2
0x140015680  movzx   eax, byte ptr [rdx]
0x140015683  mov     edx, 14h
0x140015688  mov     dword ptr [rsp+1B8h+var_188], edi
0x14001568c  mov     word ptr [rsp+1B8h+var_190], ax
0x140015691  mov     [rsp+1B8h+var_198], r13
0x140015696  mov     r9, rbx
0x140015699  mov     rcx, [rcx+18h]
0x14001569d  call    WPP_SF_qqhDD
0x1400156a2  xor     edx, edx; PriorityBoost
0x1400156a4  mov     rcx, r13; Irp
0x1400156a7  call    cs:__imp_IofCompleteRequest
0x1400156ae  nop     dword ptr [rax+rax+00h]
0x1400156b3  jmp     loc_1400162B3
0x1400156b8  mov     [rsp+1B8h+var_108], 1
0x1400156c3  mov     al, 1
0x1400156c5  movzx   ecx, al
0x1400156c8  jmp     loc_1400155EA
0x1400156cd  test    r12b, r12b
0x1400156d0  jz      loc_140015956
0x1400156d6  mov     r9, [r14+30h]
0x1400156da  test    r9, r9
0x1400156dd  jz      short loc_1400156E5
0x1400156df  mov     rbx, [r9+18h]
0x1400156e3  jmp     short loc_1400156E8
0x1400156e5  mov     rbx, rsi
0x1400156e8  lea     r12, WPP_GLOBAL_Control
0x1400156ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156f6  cmp     rcx, r12
0x1400156f9  jz      short loc_140015735
0x1400156fb  mov     eax, [rcx+2Ch]
0x1400156fe  test    al, 1
0x140015700  jz      short loc_140015735
0x140015702  cmp     byte ptr [rcx+29h], 1
0x140015706  jb      short loc_140015735
0x140015708  movzx   eax, byte ptr [r14+1]
0x14001570d  movzx   r8d, byte ptr [r14]
0x140015711  mov     edx, 0Eh
0x140015716  mov     [rsp+1B8h+var_180], rbx
0x14001571b  mov     [rsp+1B8h+var_188], r9
0x140015720  mov     dword ptr [rsp+1B8h+var_190], eax
0x140015724  mov     dword ptr [rsp+1B8h+var_198], r8d
0x140015729  mov     r9, r13
0x14001572c  mov     rcx, [rcx+18h]
0x140015730  call    WPP_SF_qllqq
0x140015735  test    rbx, rbx
0x140015738  jz      loc_140015618
0x14001573e  lea     rax, RxDeviceFCB
0x140015745  cmp     rbx, rax
0x140015748  jz      loc_140015618
0x14001574e  movzx   eax, word ptr [rbx]
0x140015751  mov     r14d, 0FFF0h
0x140015757  and     ax, r14w
0x14001575b  mov     r15d, 0EC20h
0x140015761  cmp     ax, r15w
0x140015765  jnz     loc_140015624
0x14001576b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015772  cmp     rcx, r12
0x140015775  jz      loc_140015624
0x14001577b  mov     eax, [rcx+2Ch]
0x14001577e  test    al, 1
0x140015780  jz      loc_140015624
0x140015786  cmp     byte ptr [rcx+29h], 1
0x14001578a  jb      loc_140015624
0x140015790  mov     edx, 0Fh
0x140015795  lea     rax, [rbx+150h]
0x14001579c  mov     [rsp+1B8h+var_190], rax
0x1400157a1  mov     eax, [rbx+0B8h]
0x1400157a7  mov     dword ptr [rsp+1B8h+var_198], eax
0x1400157ab  mov     r9d, [rbx+0C0h]
0x1400157b2  mov     rcx, [rcx+18h]
0x1400157b6  call    WPP_SF_llZ
0x1400157bb  jmp     loc_140015624
0x1400157c0  mov     rax, [rsp+1B8h+var_128]
0x1400157c8  mov     rdx, [rax+68h]
0x1400157cc  prefetchw byte ptr [rdx+8]
0x1400157d0  mov     rax, [rdx+8]
0x1400157d4  mov     [rsp+1B8h+var_90], rax
0x1400157dc  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400157e0  lea     rcx, [rax+2]
0x1400157e4  lock cmpxchg [rdx+8], rcx
0x1400157ea  jnz     short loc_1400157FE
0x1400157ec  mov     [rsp+1B8h+var_F0], 1
  ... truncated ...
```
