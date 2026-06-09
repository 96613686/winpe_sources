# RxCreateNetFcb

- ea: `0x14005cae0`
- end: `0x14005d6c3`
- name: `RxCreateNetFcb`
- size: `3043`
- prototype: `PFCB __stdcall(PRX_CONTEXT RxContext, PIRP Irp, PV_NET_ROOT VNetRoot, PUNICODE_STRING Name)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d7c0`
- `0x140054ca0`
- `0x140055950`

## callees

- `0x140014d10`
- `0x140014e40`
- `0x140017370`
- `0x14001810c`
- `0x14001b178`
- `0x140025d00`
- `0x140025d80`
- `0x14005c6c0`
- `0x14005cae0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005cb25`
- `ntoskrnl!ExAllocatePool2` at `0x14005cb25`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14005ce90`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14005ce90`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005cd88`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005cda6`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005cd88`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005cda6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ced2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d19c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ced2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d19c`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14005cec1`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14005d2aa`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14005cec1`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14005d2aa`
- `ntoskrnl!RtlHashUnicodeString` at `0x14005cde8`
- `ntoskrnl!RtlHashUnicodeString` at `0x14005cde8`
- `ntoskrnl!KeBugCheckEx` at `0x14005d11b`
- `ntoskrnl!KeBugCheckEx` at `0x14005d174`
- `ntoskrnl!KeBugCheckEx` at `0x14005d4eb`
- `ntoskrnl!KeBugCheckEx` at `0x14005d591`
- `ntoskrnl!KeBugCheckEx` at `0x14005d64b`
- `ntoskrnl!KeBugCheckEx` at `0x14005d11b`
- `ntoskrnl!KeBugCheckEx` at `0x14005d174`
- `ntoskrnl!KeBugCheckEx` at `0x14005d4eb`
- `ntoskrnl!KeBugCheckEx` at `0x14005d591`
- `ntoskrnl!KeBugCheckEx` at `0x14005d64b`
- `ntoskrnl!KeReleaseMutex` at `0x14005ccd5`
- `ntoskrnl!KeReleaseMutex` at `0x14005d02b`
- `ntoskrnl!KeReleaseMutex` at `0x14005ccd5`
- `ntoskrnl!KeReleaseMutex` at `0x14005d02b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005d40f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005d449`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005d40f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005d449`

## pseudocode

```c
PFCB __stdcall RxCreateNetFcb(PRX_CONTEXT RxContext, PIRP Irp, PV_NET_ROOT VNetRoot, PUNICODE_STRING Name)
{
  PFCB v8; // rbp
  struct _RDBSS_DEVICE_OBJECT *v9; // rsi
  PFCB result; // rax
  _BYTE *FcbObject; // rax
  ULONG_PTR v12; // rbx
  signed __int64 v13; // rax
  char v14; // r9
  signed __int64 v15; // rsi
  int Length; // edx
  unsigned int v17; // r8d
  wchar_t *v18; // rax
  _DWORD *v19; // r12
  _DWORD *v20; // r12
  PUNICODE_STRING v21; // rsi
  __int64 v22; // rcx
  wchar_t *Buffer; // rax
  ULONG_PTR v24; // rsi
  CSHORT *v25; // r12
  CSHORT NodeTypeCode; // cx
  struct _ERESOURCE *v27; // rcx
  struct _ERESOURCE *v28; // rcx
  unsigned __int64 *v29; // rbp
  __int64 v30; // r8
  unsigned __int8 *v31; // r14
  signed __int64 v32; // rax
  char v33; // r14
  signed __int64 v34; // rsi
  int v35; // edx
  unsigned int v36; // r8d
  _QWORD *Pointer; // rax
  _DWORD *v38; // rbp
  _DWORD *v39; // rbp
  struct _LIST_ENTRY **p_Blink; // rsi
  struct _LIST_ENTRY *v41; // rcx
  struct _LIST_ENTRY ***v42; // rax
  unsigned __int64 DfsContext; // r14
  __int64 (__fastcall *v44)(); // r13
  PDFS_NAME_CONTEXT DfsNameContext; // rax
  int v46; // r12d
  unsigned __int64 v47; // rax
  int AlreadyAllocatedObject; // [rsp+20h] [rbp-38h]
  signed __int64 v49; // [rsp+60h] [rbp+8h]
  char v50; // [rsp+60h] [rbp+8h]
  signed __int64 v51; // [rsp+60h] [rbp+8h]
  __int16 v52; // [rsp+80h] [rbp+28h]
  int v53; // [rsp+88h] [rbp+30h]
  POOL_TYPE PoolType; // [rsp+90h] [rbp+38h]
  NODE_TYPE_CODE v55; // [rsp+98h] [rbp+40h]
  char v56; // [rsp+A0h] [rbp+48h]

  v8 = 0;
  v9 = *(struct _RDBSS_DEVICE_OBJECT **)&RxContext->RealDevice->Flags;
  if ( VNetRoot )
  {
    result = (PFCB)ExAllocatePool2(258, VNetRoot->NodeTypeCode, 1061124178);
    v8 = result;
    if ( !result )
      return result;
    memmove(result, VNetRoot->pNetRoot, VNetRoot->NodeTypeCode);
  }
  FcbObject = RxAllocateFcbObject(v9, v55, PoolType, (unsigned __int16)Irp->Type, 0);
  v12 = (ULONG_PTR)FcbObject;
  if ( !FcbObject )
    return (PFCB)v12;
  FcbObject[257] = BYTE5(RxContext->pRelevantSrvOpen);
  *((_QWORD *)FcbObject + 50) = v9;
  *((_QWORD *)FcbObject + 49) = v9->RDBSSDeviceObject;
  *((_DWORD *)FcbObject + 39) = v53;
  *((_QWORD *)FcbObject + 15) = RxContext;
  *((_QWORD *)FcbObject + 34) = FcbObject + 264;
  *((_QWORD *)FcbObject + 33) = FcbObject + 264;
  *((_QWORD *)FcbObject + 87) = 0;
  *((_QWORD *)FcbObject + 88) = 0;
  if ( !Name )
    goto LABEL_24;
  v13 = *(_QWORD *)&Name->Length;
  v14 = 0;
  v49 = *(_QWORD *)&Name->Length;
  do
  {
    v15 = v13;
    if ( (v13 & 0x1000) != 0 )
    {
      LOWORD(v49) = v13 & 0xEFFF;
      if ( !v14 )
      {
        KeWaitForSingleObject(&RxScavengerMutex, Executive, 0, 0, 0);
        v14 = 1;
      }
    }
    else
    {
      HIDWORD(v49) = HIDWORD(v13) + 1;
    }
    v13 = _InterlockedCompareExchange64((volatile signed __int64 *)Name, v49, v15);
    v49 = v13;
  }
  while ( v15 != v13 );
  v50 = v14;
  if ( (v15 & 0x1000) != 0 )
  {
    Length = Name->Length;
    v17 = Length & 0xEFFF;
    if ( v17 == 60178 )
    {
      v18 = *(wchar_t **)(*(_QWORD *)(*(_QWORD *)&Name[2].Length + 32LL) + 48LL);
LABEL_13:
      v19 = (_DWORD *)*((_QWORD *)v18 + 104);
      switch ( Length & 0xFFFFEFFF )
      {
        case 0xEB12u:
          v20 = v19 + 5;
          break;
        case 0xEB10u:
          v20 = v19 + 3;
          break;
        case 0xEB11u:
          v20 = v19 + 4;
          break;
        case 0xEB13u:
          v20 = v19 + 8;
          break;
        case 0xEB1Cu:
          v20 = v19 + 6;
          break;
        case 0xEC30u:
          v20 = v19 + 7;
          break;
        default:
          KeBugCheckEx(0x27u, 0x1021Cu, (ULONG_PTR)Name, Name->Length, 0);
      }
      v21 = Name + 1;
      if ( *(PUNICODE_STRING *)&v21->Length == v21 )
        KeBugCheckEx(0x27u, 0x10225u, (ULONG_PTR)Name, Name->Length, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        AlreadyAllocatedObject = Name->Length & 0xEFFF;
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_7cd1a4145ac63a5107541aa80a8a6609_Traceguids, Name);
        v14 = v50;
      }
      _InterlockedAnd((volatile signed __int32 *)Name, 0xFFFFEFFF);
      --*v20;
      v22 = *(_QWORD *)&v21->Length;
      if ( *(PUNICODE_STRING *)(*(_QWORD *)&v21->Length + 8LL) != v21 )
        goto LABEL_113;
      Buffer = Name[1].Buffer;
      if ( *(PUNICODE_STRING *)Buffer != v21 )
        goto LABEL_113;
      *(_QWORD *)Buffer = v22;
      *(_QWORD *)(v22 + 8) = Buffer;
      Name[1].Buffer = &Name[1].Length;
      *(_QWORD *)&v21->Length = v21;
      goto LABEL_21;
    }
    if ( v17 <= 0xEB1C )
    {
      switch ( v17 )
      {
        case 0xEB1Cu:
          v18 = *(wchar_t **)(*(_QWORD *)&Name[2].Length + 400LL);
          goto LABEL_13;
        case 0xEB10u:
          v18 = *(wchar_t **)&Name[3].Length;
          goto LABEL_13;
        case 0xEB11u:
          v18 = *(wchar_t **)(*(_QWORD *)&Name[2].Length + 48LL);
          goto LABEL_13;
        case 0xEB13u:
          v18 = *(wchar_t **)&Name[5].Length;
          goto LABEL_13;
      }
    }
    else
    {
      if ( v17 == 60449 || v17 == 60450 )
      {
        v18 = *(wchar_t **)&Name[25].Length;
        goto LABEL_13;
      }
      if ( v17 == 60464 )
      {
        v18 = Name[15].Buffer;
        goto LABEL_13;
      }
    }
    v18 = 0;
    goto LABEL_13;
  }
LABEL_21:
  if ( v14 )
    KeReleaseMutex(&RxScavengerMutex, 0);
  *(_QWORD *)(v12 + 128) = Name;
LABEL_24:
  v24 = v12 + 312;
  *(_BYTE *)(v12 + 355) &= 0xC3u;
  v25 = (CSHORT *)(v12 + 336);
  if ( VNetRoot )
  {
    *(_QWORD *)(v12 + 344) = v8;
    NodeTypeCode = VNetRoot->NodeTypeCode;
    *(_BYTE *)(v12 + 355) |= 2u;
    *v25 = NodeTypeCode;
  }
  else
  {
    *(_QWORD *)(v12 + 344) = *(_QWORD *)(v12 + 368);
    *v25 = Irp->Type;
    NodeTypeCode = Irp->Type;
  }
  *(_WORD *)(v12 + 338) = NodeTypeCode;
  memmove(*(void **)(v12 + 368), Irp->MdlAddress, (unsigned __int16)Irp->Type);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, v12 + 360);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, v12 + 336);
    }
  }
  if ( v52 )
  {
    *(_DWORD *)(v12 + 156) |= 0x400u;
    *(_WORD *)(v12 + 280) = v52;
  }
  v27 = (struct _ERESOURCE *)(*(_QWORD *)(v12 + 304) + 32LL);
  *(_QWORD *)(v12 + 8) = v27;
  ExInitializeResourceLite(v27);
  v28 = (struct _ERESOURCE *)(*(_QWORD *)(v12 + 304) + 136LL);
  *(_QWORD *)(v12 + 16) = v28;
  ExInitializeResourceLite(v28);
  if ( !v56 )
  {
    *(_DWORD *)(v12 + 156) |= 0x10000000u;
    *(_DWORD *)(v12 + 152) = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqZ(
        WPP_GLOBAL_Control->AttachedDevice,
        55,
        (unsigned int)WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
        v12,
        (char)RxContext,
        v12 + 360);
    }
    goto LABEL_44;
  }
  v29 = 0;
  *(_BYTE *)(v12 + 355) = *(_BYTE *)(v12 + 355) & 0xFE | (VNetRoot != 0);
  RtlHashUnicodeString(
    (PCUNICODE_STRING)(v12 + 336),
    *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 32),
    0,
    (PULONG)(v12 + 356));
  v30 = *((_QWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 3);
  if ( v30 )
  {
    v29 = (unsigned __int64 *)(v30
                             + 8
                             * (*(_DWORD *)(v12 + 356)
                              & 3
                              ^ (unsigned __int64)((unsigned __int8)(*(_DWORD *)(v12 + 356)
                                                                   ^ ((unsigned __int64)*(unsigned int *)(v12 + 356) >> 6)
                                                                   ^ ((((unsigned __int64)*(unsigned int *)(v12 + 356) >> 6)
                                                                     ^ ((*(unsigned int *)(v12 + 356)
                                                                       ^ ((unsigned __int64)*(unsigned int *)(v12 + 356) >> 6)) >> 12)) >> 6)) >> 2)));
    if ( (*v29 & 1) != 0 )
    {
      v31 = (unsigned __int8 *)(*v29 & 0xFFFFFFFFFFFFFFFEuLL);
      *v29 = 0;
      if ( !_InterlockedExchangeAdd16((volatile signed __int16 *)(*(_QWORD *)v31 + 40LL), 0xFFFFu) )
        KeBugCheckEx(0x27u, 0xFCB3032A, v12, (ULONG_PTR)v31, 0);
      if ( *((_DWORD *)v31 + 7) == HIDWORD(RxContext->OverflowListEntry.Blink)
        && *(_DWORD *)(v12 + 356) == *((_DWORD *)v31 + 6)
        && RtlEqualUnicodeString(
             (PCUNICODE_STRING)(v12 + 336),
             (PCUNICODE_STRING)(v31 + 8),
             *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 32)) )
      {
        *v29 = v24 & 0xFFFFFFFFFFFFFFFEuLL;
        RtlRbInsertNodeEx(
          &RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory.NotificationBufferLength,
          *(_QWORD *)v31,
          v31[32],
          v12 + 312,
          AlreadyAllocatedObject);
        ExFreePoolWithTag(v31, 0);
        goto LABEL_40;
      }
      ExFreePoolWithTag(v31, 0);
    }
  }
  DfsContext = (unsigned __int64)RxContext->Create.NtCreateParameters.DfsContext;
  v44 = RxpCompareFcbNamesCaseInsensitive;
  if ( !*((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 32) )
    v44 = RxpCompareFcbNamesCaseSensitive;
  DfsNameContext = RxContext->Create.NtCreateParameters.DfsNameContext;
  if ( ((unsigned __int8)DfsNameContext & 1) != 0 )
  {
    if ( !DfsContext )
    {
      LOBYTE(v30) = 0;
      goto LABEL_99;
    }
    DfsContext ^= (unsigned __int64)&RxContext->Create.NtCreateParameters.DfsContext;
  }
  LOBYTE(v30) = 0;
  v46 = (unsigned __int8)DfsNameContext & 1;
  if ( !DfsContext )
    goto LABEL_98;
  while ( 1 )
  {
    if ( ((int (__fastcall *)(ULONG_PTR, unsigned __int64, __int64))v44)(v12 + 336, DfsContext, v30) >= 0 )
    {
      v47 = *(_QWORD *)(DfsContext + 8);
      if ( v46 )
      {
        if ( !v47 )
        {
LABEL_97:
          LOBYTE(v30) = 1;
          goto LABEL_98;
        }
        v47 ^= DfsContext;
      }
      if ( !v47 )
        goto LABEL_97;
      goto LABEL_85;
    }
    v47 = *(_QWORD *)DfsContext;
    if ( v46 )
      break;
LABEL_110:
    if ( !v47 )
      goto LABEL_119;
LABEL_85:
    DfsContext = v47;
  }
  if ( v47 )
  {
    v47 ^= DfsContext;
    goto LABEL_110;
  }
LABEL_119:
  LOBYTE(v30) = 0;
LABEL_98:
  v25 = (CSHORT *)(v12 + 336);
LABEL_99:
  RtlRbInsertNodeEx(
    &RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory.NotificationBufferLength,
    DfsContext,
    v30,
    v12 + 312,
    AlreadyAllocatedObject);
  if ( *((_QWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 3) )
    *v29 = v24 & 0xFFFFFFFFFFFFFFFEuLL;
LABEL_40:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      (unsigned int)WPP_518c92af35303f374eeedacc3593600d_Traceguids,
      v12,
      (__int64)v25);
  }
  ++LODWORD(RxContext->SyncEvent.Header.WaitListHead.Flink);
  *(_DWORD *)(v12 + 156) &= ~0x10000000u;
  _InterlockedIncrement((volatile signed __int32 *)&RxContext->OverflowListEntry.Blink + 1);
  *(_DWORD *)(v12 + 152) = 2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      54,
      (unsigned int)WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
      v12,
      (char)RxContext,
      (__int64)v25);
  }
LABEL_44:
  v32 = *(_QWORD *)&RxContext->NodeTypeCode;
  v33 = 0;
  v51 = *(_QWORD *)&RxContext->NodeTypeCode;
  do
  {
    v34 = v32;
    if ( (v32 & 0x1000) != 0 )
    {
      LOWORD(v51) = v32 & 0xEFFF;
      if ( !v33 )
      {
        KeWaitForSingleObject(&RxScavengerMutex, Executive, 0, 0, 0);
        v33 = 1;
      }
    }
    else
    {
      HIDWORD(v51) = HIDWORD(v32) + 1;
    }
    v32 = _InterlockedCompareExchange64((volatile signed __int64 *)RxContext, v51, v34);
    v51 = v32;
  }
  while ( v34 != v32 );
  if ( (v34 & 0x1000) != 0 )
  {
    v35 = RxContext->NodeTypeCode;
    v36 = v35 & 0xEFFF;
    if ( v36 == 60178 )
    {
      Pointer = RxContext->RealDevice->CurrentIrp->IoStatus.Pointer;
      goto LABEL_51;
    }
    if ( v36 <= 0xEB1C )
    {
      switch ( v36 )
      {
        case 0xEB1Cu:
          Pointer = RxContext->RealDevice[1].DeviceExtension;
          break;
        case 0xEB10u:
          Pointer = &RxContext->CurrentIrpSp->MajorFunction;
          break;
        case 0xEB11u:
          Pointer = *(_QWORD **)&RxContext->RealDevice->Flags;
          break;
        case 0xEB13u:
          Pointer = &RxContext->NonPagedFcb->NodeTypeCode;
          break;
        default:
          goto LABEL_159;
      }
    }
    else if ( v36 == 60449 || v36 == 60450 )
    {
      Pointer = &RxContext->NotifyChangeDirectory.pVNetRoot->0;
    }
    else
    {
      if ( v36 == 60464 )
      {
        Pointer = &RxContext->WorkQueueItem.List.Flink->Flink;
        goto LABEL_51;
      }
LABEL_159:
      Pointer = 0;
    }
LABEL_51:
    v38 = (_DWORD *)Pointer[104];
    switch ( v35 & 0xFFFFEFFF )
    {
      case 0xEB12u:
        v39 = v38 + 5;
        break;
      case 0xEB10u:
        v39 = v38 + 3;
        break;
      case 0xEB11u:
        v39 = v38 + 4;
        break;
      case 0xEB13u:
        v39 = v38 + 8;
        break;
      case 0xEB1Cu:
        v39 = v38 + 6;
        break;
      case 0xEC30u:
        v39 = v38 + 7;
        break;
      default:
        KeBugCheckEx(0x27u, 0x1021Cu, (ULONG_PTR)RxContext, RxContext->NodeTypeCode, 0);
    }
    p_Blink = &RxContext->ContextListEntry.Blink;
    if ( *p_Blink == (struct _LIST_ENTRY *)p_Blink )
      KeBugCheckEx(0x27u, 0x10225u, (ULONG_PTR)RxContext, RxContext->NodeTypeCode, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_7cd1a4145ac63a5107541aa80a8a6609_Traceguids, RxContext);
    }
    _InterlockedAnd((volatile signed __int32 *)RxContext, 0xFFFFEFFF);
    --*v39;
    v41 = *p_Blink;
    if ( (struct _LIST_ENTRY **)(*p_Blink)->Blink == p_Blink )
    {
      v42 = *(struct _LIST_ENTRY ****)&RxContext->MajorFunction;
      if ( *v42 == p_Blink )
      {
        *v42 = &v41->Flink;
        v41->Blink = (struct _LIST_ENTRY *)v42;
        *(_QWORD *)&RxContext->MajorFunction = &RxContext->ContextListEntry.Blink;
        *p_Blink = (struct _LIST_ENTRY *)p_Blink;
        goto LABEL_59;
      }
    }
LABEL_113:
    __fastfail(3u);
  }
LABEL_59:
  if ( v33 )
    KeReleaseMutex(&RxScavengerMutex, 0);
  _InterlockedIncrement((volatile signed __int32 *)&RxContext->pFcb + 1);
  *(_WORD *)(v12 + 282) = 0;
  *(_QWORD *)(v12 + 520) = v12 + 512;
  *(_QWORD *)(v12 + 512) = v12 + 512;
  *(_QWORD *)(v12 + 168) = -1;
  *(_QWORD *)(v12 + 176) = -1;
  *(_QWORD *)(v12 + 528) = v12;
  *(_QWORD *)(v12 + 160) = 175114240;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids);
  }
  return (PFCB)v12;
}

```

## disassembly

```asm
0x14005cae0  mov     [rsp+arg_10], rbp
0x14005cae5  mov     [rsp+arg_18], rsi
0x14005caea  push    rdi
0x14005caeb  push    r12
0x14005caed  push    r13
0x14005caef  push    r14
0x14005caf1  push    r15
0x14005caf3  sub     rsp, 30h
0x14005caf7  mov     rax, [rcx+20h]
0x14005cafb  xor     r12d, r12d
0x14005cafe  mov     r14, r9
0x14005cb01  mov     r15, r8
0x14005cb04  mov     r13, rdx
0x14005cb07  mov     rdi, rcx
0x14005cb0a  mov     ebp, r12d
0x14005cb0d  mov     rsi, [rax+30h]
0x14005cb11  test    r8, r8
0x14005cb14  jz      short loc_14005CB4D
0x14005cb16  movzx   edx, word ptr [r8]
0x14005cb1a  mov     ecx, 102h
0x14005cb1f  mov     r8d, 3F3F7852h
0x14005cb25  call    cs:__imp_ExAllocatePool2
0x14005cb2c  nop     dword ptr [rax+rax+00h]
0x14005cb31  mov     rbp, rax
0x14005cb34  test    rax, rax
0x14005cb37  jz      loc_14005D330
0x14005cb3d  movzx   r8d, word ptr [r15]; Size
0x14005cb41  mov     rcx, rax; void *
0x14005cb44  mov     rdx, [r15+8]; Src
0x14005cb48  call    memmove
0x14005cb4d  movzx   r9d, word ptr [r13+0]; NameSize
0x14005cb52  mov     rcx, rsi; RxDeviceObject
0x14005cb55  mov     r8, qword ptr [rsp+58h+PoolType]; PoolType
0x14005cb5d  movzx   edx, [rsp+58h+arg_38]; NodeType
0x14005cb65  mov     [rsp+58h+arg_8], rbx
0x14005cb6a  mov     [rsp+58h+AlreadyAllocatedObject], r12; AlreadyAllocatedObject
0x14005cb6f  call    RxAllocateFcbObject
0x14005cb74  mov     rbx, rax
0x14005cb77  test    rax, rax
0x14005cb7a  jz      loc_14005D093
0x14005cb80  movzx   eax, byte ptr [rdi+4Dh]
0x14005cb84  mov     edx, 1000h
0x14005cb89  mov     [rbx+101h], al
0x14005cb8f  mov     r8d, 0EFFFh
0x14005cb95  mov     [rbx+190h], rsi
0x14005cb9c  mov     rax, [rsi+160h]
0x14005cba3  mov     [rbx+188h], rax
0x14005cbaa  mov     eax, [rsp+58h+arg_28]
0x14005cbb1  mov     [rbx+9Ch], eax
0x14005cbb7  lea     rax, [rbx+108h]
0x14005cbbe  mov     [rbx+78h], rdi
0x14005cbc2  mov     [rax+8], rax
0x14005cbc6  mov     [rax], rax
0x14005cbc9  mov     [rbx+2B8h], r12
0x14005cbd0  mov     [rbx+2C0h], r12
0x14005cbd7  test    r14, r14
0x14005cbda  jz      loc_14005CCE8
0x14005cbe0  mov     rax, [r14]
0x14005cbe3  xor     r9b, r9b
0x14005cbe6  mov     [rsp+58h+arg_0], rax
0x14005cbeb  mov     rsi, rax
0x14005cbee  movzx   ecx, ax
0x14005cbf1  test    dx, ax
0x14005cbf4  jnz     loc_14005D423
0x14005cbfa  shr     rax, 20h
0x14005cbfe  inc     eax
0x14005cc00  mov     dword ptr [rsp+58h+arg_0+4], eax
0x14005cc04  mov     rcx, [rsp+58h+arg_0]
0x14005cc09  mov     rax, rsi
0x14005cc0c  lock cmpxchg [r14], rcx
0x14005cc11  mov     [rsp+58h+arg_0], rax
0x14005cc16  jnz     short loc_14005CBEB
0x14005cc18  mov     byte ptr [rsp+58h+arg_0], r9b
0x14005cc1d  test    dx, si
0x14005cc20  jz      loc_14005CCC7
0x14005cc26  movzx   edx, word ptr [r14]
0x14005cc2a  mov     r8d, edx
0x14005cc2d  btr     r8d, 0Ch
0x14005cc32  cmp     r8d, 0EB12h
0x14005cc39  jnz     loc_14005D257
0x14005cc3f  mov     rax, [r14+20h]
0x14005cc43  mov     rcx, [rax+20h]
0x14005cc47  mov     rax, [rcx+30h]
0x14005cc4b  mov     r12, [rax+340h]
0x14005cc52  mov     ecx, edx
0x14005cc54  btr     ecx, 0Ch
0x14005cc58  cmp     ecx, 0EB12h
0x14005cc5e  jnz     loc_14005D128
0x14005cc64  add     r12, 14h
0x14005cc68  lea     rsi, [r14+10h]
0x14005cc6c  cmp     [rsi], rsi
0x14005cc6f  jz      loc_14005D4D2
0x14005cc75  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc7c  lea     rax, WPP_GLOBAL_Control
0x14005cc83  cmp     rcx, rax
0x14005cc86  jz      short loc_14005CC93
0x14005cc88  mov     eax, [rcx+2Ch]
0x14005cc8b  test    al, al
0x14005cc8d  js      loc_14005D4F8
0x14005cc93  lock and dword ptr [r14], 0FFFFEFFFh
0x14005cc9b  dec     dword ptr [r12]
0x14005cc9f  mov     rcx, [rsi]
0x14005cca2  cmp     [rcx+8], rsi
0x14005cca6  jnz     loc_14005D335
0x14005ccac  mov     rax, [rsi+8]
0x14005ccb0  cmp     [rax], rsi
0x14005ccb3  jnz     loc_14005D335
0x14005ccb9  mov     [rax], rcx
0x14005ccbc  mov     [rcx+8], rax
0x14005ccc0  mov     [rsi+8], rsi
0x14005ccc4  mov     [rsi], rsi
0x14005ccc7  test    r9b, r9b
0x14005ccca  jz      short loc_14005CCE1
0x14005cccc  xor     edx, edx; Wait
0x14005ccce  lea     rcx, RxScavengerMutex; Mutex
0x14005ccd5  call    cs:__imp_KeReleaseMutex
0x14005ccdc  nop     dword ptr [rax+rax+00h]
0x14005cce1  mov     [rbx+80h], r14
0x14005cce8  lea     rsi, [rbx+138h]
0x14005ccef  and     byte ptr [rsi+2Bh], 0C3h
0x14005ccf3  lea     r12, [rsi+18h]
0x14005ccf7  mov     [rsp+58h+arg_0], r12
0x14005ccfc  test    r15, r15
0x14005ccff  jz      loc_14005D0B4
0x14005cd05  mov     [rsi+20h], rbp
0x14005cd09  movzx   ecx, word ptr [r15]
0x14005cd0d  or      byte ptr [rsi+2Bh], 2
0x14005cd11  mov     [r12], cx
0x14005cd16  mov     [rsi+1Ah], cx
0x14005cd1a  movzx   r8d, word ptr [r13+0]; Size
0x14005cd1f  mov     rdx, [r13+8]; Src
0x14005cd23  mov     rcx, [rbx+170h]; void *
0x14005cd2a  call    memmove
0x14005cd2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cd36  lea     r13, WPP_GLOBAL_Control
0x14005cd3d  cmp     rcx, r13
0x14005cd40  jz      short loc_14005CD68
0x14005cd42  test    dword ptr [rcx+2Ch], 100h
0x14005cd49  jnz     loc_14005D52A
0x14005cd4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cd56  cmp     rcx, r13
0x14005cd59  jz      short loc_14005CD68
0x14005cd5b  test    dword ptr [rcx+2Ch], 100h
0x14005cd62  jnz     loc_14005D555
0x14005cd68  movzx   eax, [rsp+58h+arg_20]
0x14005cd70  test    ax, ax
0x14005cd73  jnz     loc_14005D181
0x14005cd79  mov     rcx, [rbx+130h]
0x14005cd80  add     rcx, 20h ; ' '; Resource
0x14005cd84  mov     [rbx+8], rcx
0x14005cd88  call    cs:__imp_ExInitializeResourceLite
0x14005cd8f  nop     dword ptr [rax+rax+00h]
0x14005cd94  mov     rcx, [rbx+130h]
0x14005cd9b  add     rcx, 88h; Resource
0x14005cda2  mov     [rbx+10h], rcx
0x14005cda6  call    cs:__imp_ExInitializeResourceLite
0x14005cdad  nop     dword ptr [rax+rax+00h]
0x14005cdb2  cmp     [rsp+58h+arg_40], 0
0x14005cdba  jz      loc_14005D33C
0x14005cdc0  movzx   eax, byte ptr [rsi+2Bh]
0x14005cdc4  lea     r9, [rsi+2Ch]; HashValue
0x14005cdc8  xor     r13d, r13d
0x14005cdcb  test    r15, r15
0x14005cdce  mov     ebp, r13d
0x14005cdd1  setnz   cl
0x14005cdd4  and     al, 0FEh
0x14005cdd6  or      cl, al
0x14005cdd8  xor     r8d, r8d; HashAlgorithm
0x14005cddb  mov     [rsi+2Bh], cl
0x14005cdde  mov     rcx, r12; String
0x14005cde1  movzx   edx, byte ptr [rdi+1D8h]; CaseInSensitive
0x14005cde8  call    cs:__imp_RtlHashUnicodeString
0x14005cdef  nop     dword ptr [rax+rax+00h]
0x14005cdf4  mov     r8, [rdi+1D0h]
0x14005cdfb  test    r8, r8
0x14005cdfe  jz      loc_14005D1A8
0x14005ce04  mov     edx, [rsi+2Ch]
0x14005ce07  mov     eax, edx
0x14005ce09  shr     rax, 6
0x14005ce0d  mov     rcx, rax
0x14005ce10  xor     rcx, rdx
0x14005ce13  shr     rcx, 0Ch
0x14005ce17  xor     rcx, rax
0x14005ce1a  shr     rcx, 6
0x14005ce1e  xor     rcx, rax
0x14005ce21  xor     rcx, rdx
0x14005ce24  and     edx, 3
0x14005ce27  shr     rcx, 2
0x14005ce2b  and     ecx, 3Fh
0x14005ce2e  xor     rcx, rdx
0x14005ce31  mov     rax, [r8+rcx*8]
0x14005ce35  lea     rbp, [r8+rcx*8]
0x14005ce39  test    al, 1
0x14005ce3b  jz      loc_14005D1A8
0x14005ce41  mov     r14, [rbp+0]
0x14005ce45  mov     eax, 0FFFFFFFFh
0x14005ce4a  and     r14, 0FFFFFFFFFFFFFFFEh
0x14005ce4e  mov     [rbp+0], r13
0x14005ce52  mov     rcx, [r14]
0x14005ce55  lock xadd [rcx+28h], ax
0x14005ce5b  test    ax, ax
0x14005ce5e  jz      loc_14005D57C
0x14005ce64  mov     eax, [rdi+12Ch]
0x14005ce6a  cmp     [r14+1Ch], eax
0x14005ce6e  jnz     loc_14005D197
0x14005ce74  mov     eax, [r14+18h]
0x14005ce78  cmp     [rsi+2Ch], eax
0x14005ce7b  jnz     loc_14005D197
0x14005ce81  movzx   r8d, byte ptr [rdi+1D8h]; CaseInSensitive
0x14005ce89  lea     rdx, [r14+8]; String2
0x14005ce8d  mov     rcx, r12; String1
0x14005ce90  call    cs:__imp_RtlEqualUnicodeString
0x14005ce97  nop     dword ptr [rax+rax+00h]
0x14005ce9c  test    al, al
0x14005ce9e  jz      loc_14005D197
0x14005cea4  mov     rax, rsi
0x14005cea7  lea     rcx, [rdi+1C0h]
0x14005ceae  and     rax, 0FFFFFFFFFFFFFFFEh
0x14005ceb2  mov     r9, rsi
0x14005ceb5  mov     [rbp+0], rax
0x14005ceb9  movzx   r8d, byte ptr [r14+20h]
0x14005cebe  mov     rdx, [r14]
0x14005cec1  call    cs:__imp_RtlRbInsertNodeEx
0x14005cec8  nop     dword ptr [rax+rax+00h]
0x14005cecd  xor     edx, edx; Tag
0x14005cecf  mov     rcx, r14; P
0x14005ced2  call    cs:__imp_ExFreePoolWithTag
0x14005ced9  nop     dword ptr [rax+rax+00h]
0x14005cede  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cee5  lea     r13, WPP_GLOBAL_Control
0x14005ceec  cmp     rcx, r13
0x14005ceef  jz      short loc_14005CEFE
0x14005cef1  test    dword ptr [rcx+2Ch], 100h
0x14005cef8  jnz     loc_14005D5AE
0x14005cefe  inc     dword ptr [rdi+138h]
0x14005cf04  and     dword ptr [rbx+9Ch], 0EFFFFFFFh
0x14005cf0e  lock inc dword ptr [rdi+12Ch]
0x14005cf15  mov     dword ptr [rbx+98h], 2
0x14005cf1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cf26  cmp     rcx, r13
0x14005cf29  jz      short loc_14005CF38
0x14005cf2b  test    dword ptr [rcx+2Ch], 100h
0x14005cf32  jnz     loc_14005D5DA
0x14005cf38  mov     rax, [rdi]
0x14005cf3b  xor     r14b, r14b
0x14005cf3e  mov     [rsp+58h+arg_0], rax
0x14005cf43  mov     r12d, 0EFFFh
0x14005cf49  bt      ax, 0Ch
0x14005cf4e  mov     rsi, rax
0x14005cf51  movzx   ecx, ax
0x14005cf54  jb      loc_14005D3E6
0x14005cf5a  shr     rax, 20h
0x14005cf5e  inc     eax
0x14005cf60  mov     dword ptr [rsp+58h+arg_0+4], eax
0x14005cf64  xor     r15d, r15d
0x14005cf67  mov     rcx, [rsp+58h+arg_0]
0x14005cf6c  mov     rax, rsi
0x14005cf6f  lock cmpxchg [rdi], rcx
0x14005cf74  mov     [rsp+58h+arg_0], rax
0x14005cf79  jnz     short loc_14005CF49
0x14005cf7b  bt      si, 0Ch
0x14005cf80  jnb     loc_14005D01D
0x14005cf86  movzx   edx, word ptr [rdi]
0x14005cf89  mov     r8d, edx
0x14005cf8c  btr     r8d, 0Ch
0x14005cf91  cmp     r8d, 0EB12h
0x14005cf98  jnz     loc_14005D21E
0x14005cf9e  mov     rax, [rdi+20h]
0x14005cfa2  mov     rcx, [rax+20h]
0x14005cfa6  mov     rax, [rcx+30h]
0x14005cfaa  mov     rbp, [rax+340h]
0x14005cfb1  mov     ecx, edx
0x14005cfb3  btr     ecx, 0Ch
0x14005cfb7  cmp     ecx, 0EB12h
0x14005cfbd  jnz     loc_14005D0D3
0x14005cfc3  add     rbp, 14h
0x14005cfc7  lea     rsi, [rdi+10h]
0x14005cfcb  cmp     [rsi], rsi
0x14005cfce  jz      loc_14005D636
0x14005cfd4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cfdb  cmp     rcx, r13
0x14005cfde  jz      short loc_14005CFEB
0x14005cfe0  mov     eax, [rcx+2Ch]
0x14005cfe3  test    al, al
0x14005cfe5  js      loc_14005D658
0x14005cfeb  lock and dword ptr [rdi], 0FFFFEFFFh
0x14005cff2  dec     dword ptr [rbp+0]
0x14005cff5  mov     rcx, [rsi]
0x14005cff8  cmp     [rcx+8], rsi
0x14005cffc  jnz     loc_14005D335
0x14005d002  mov     rax, [rsi+8]
0x14005d006  cmp     [rax], rsi
0x14005d009  jnz     loc_14005D335
0x14005d00f  mov     [rax], rcx
0x14005d012  mov     [rcx+8], rax
0x14005d016  mov     [rsi+8], rsi
0x14005d01a  mov     [rsi], rsi
0x14005d01d  test    r14b, r14b
0x14005d020  jz      short loc_14005D037
0x14005d022  xor     edx, edx; Wait
  ... truncated ...
```
