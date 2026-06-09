# RxCommonSetInformation

- ea: `0x14006f9e0`
- end: `0x140070416`
- name: `RxCommonSetInformation`
- size: `2614`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140007ca0`
- `0x140009b80`
- `0x1400120c0`
- `0x140016d40`
- `0x140016e20`
- `0x140016e70`
- `0x140017280`
- `0x140017a8c`
- `0x140019838`
- `0x140019a28`
- `0x140044010`
- `0x140044c78`
- `0x140057660`
- `0x140058540`
- `0x14005b620`
- `0x140069a20`
- `0x14006a2b0`
- `0x14006f9e0`
- `0x140070420`
- `0x1400705d0`
- `0x140070750`
- `0x1400708e0`
- `0x140074810`
- `0x140074a00`
- `0x140078280`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14006ffe6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006ffe6`
- `ntoskrnl!FsRtlCheckOplock` at `0x14006fb9e`
- `ntoskrnl!FsRtlCheckOplock` at `0x14006fb9e`
- `ntoskrnl!DbgPrint` at `0x14006fd5f`
- `ntoskrnl!DbgPrint` at `0x14006fd5f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006fdd2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006fdd2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400703ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007b40a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400703ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007b40a`
- `ntoskrnl!MmFlushImageSection` at `0x140070203`
- `ntoskrnl!MmFlushImageSection` at `0x140070203`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14007026a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14007026a`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1400701c7`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1400701c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400700ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400700ec`

## string_xrefs

- `0x14006fd58`: `SetFile, Illegal TypeOfOpen = %08lx\n`
- `0x14007b3d2`: `RxCommonSetInformation`

## pseudocode

```c
__int64 __fastcall RxCommonSetInformation(PRX_CONTEXT RxContext, __int64 Irp)
{
  PIRP v2; // r10
  struct _IO_STACK_LOCATION *v4; // rdi
  ULONG Options; // r14d
  int v6; // r12d
  BOOLEAN v7; // r11
  char v8; // r13
  PFILE_OBJECT FileObject; // rax
  UNICODE_STRING *FsContext; // rbx
  __int64 FsContext2; // r15
  ULONG Length; // edx
  __int64 v13; // r8
  wchar_t *Buffer; // r9
  char v15; // r15
  NTSTATUS v16; // eax
  int v17; // edi
  __int64 v18; // rcx
  int v19; // eax
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  struct _FCB *i; // rax
  struct _FCB *v23; // rdi
  ULONG v24; // r8d
  const CHAR *v25; // r9
  int v26; // eax
  struct _FCB *j; // rax
  __int64 v28; // r8
  const CHAR *v29; // r9
  ULONG v31; // r8d
  const CHAR *v32; // r9
  PFCB *PostIrpRoutine; // [rsp+20h] [rbp-D8h]
  ULONG PostIrpRoutinea; // [rsp+20h] [rbp-D8h]
  UNICODE_STRING *v35; // [rsp+28h] [rbp-D0h]
  wchar_t *v36; // [rsp+48h] [rbp-B0h]
  PFCB Fcb; // [rsp+50h] [rbp-A8h] BYREF
  PFCB ThisFcb; // [rsp+58h] [rbp-A0h]
  __int64 v39; // [rsp+60h] [rbp-98h]
  UNICODE_STRING *v40; // [rsp+68h] [rbp-90h]
  UNICODE_STRING String2; // [rsp+70h] [rbp-88h] BYREF
  wchar_t *v42; // [rsp+80h] [rbp-78h]
  _OWORD v43[7]; // [rsp+88h] [rbp-70h] BYREF
  bool v45; // [rsp+110h] [rbp+18h] BYREF
  LARGE_INTEGER NewFileSize; // [rsp+118h] [rbp+20h] BYREF

  v2 = (PIRP)Irp;
  v4 = *(struct _IO_STACK_LOCATION **)(Irp + 184);
  Options = v4->Parameters.Create.Options;
  v6 = (__int64)RxContext->RdbssDbgExtension & 2;
  v7 = v6 != 0;
  v45 = v6 != 0;
  v8 = 0;
  Fcb = 0;
  FileObject = v4->FileObject;
  if ( FileObject )
  {
    FsContext = (UNICODE_STRING *)FileObject->FsContext;
    v40 = FsContext;
    FsContext2 = (__int64)FileObject->FsContext2;
    v39 = FsContext2;
    if ( FsContext->Length == 0xEC23 && FsContext2 )
    {
      Length = 60456;
      v13 = 60448;
    }
    else
    {
      Length = FsContext->Length;
      v13 = 60448;
    }
  }
  else
  {
    FsContext = 0;
    v40 = 0;
    FsContext2 = 0;
    v39 = 0;
    v13 = 60448;
    Length = 60448;
  }
  NewFileSize.LowPart = Length;
  Buffer = FsContext[7].Buffer;
  v36 = Buffer;
  v42 = Buffer;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v35 = FsContext;
    PostIrpRoutine = (PFCB *)FsContext2;
    WPP_SF_qqqld(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, RxContext);
    LOWORD(Length) = NewFileSize.LowPart;
    v2 = (PIRP)Irp;
    v13 = 60448;
    Buffer = v36;
    v7 = v45;
  }
  v15 = 0;
  if ( (unsigned __int16)Length != 60455
    && (unsigned __int16)Length != 60448
    && (unsigned __int16)Length != 60449
    && (unsigned __int16)Length != 60450 )
  {
    if ( (unsigned __int16)Length == 60454 )
    {
      v17 = -1073741822;
    }
    else
    {
      DbgPrint("SetFile, Illegal TypeOfOpen = %08lx\n", (unsigned __int16)Length);
LABEL_48:
      v17 = -1073741811;
    }
    goto LABEL_117;
  }
  if ( Options == 20 && v4->Parameters.SetFile.AdvanceOnly )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, RxContext);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, RxContext);
    }
    v17 = 0;
    goto LABEL_117;
  }
  if ( Options - 10 <= 1 || Options == 31 )
  {
    if ( !ExAcquireResourceExclusiveLite((PERESOURCE)(Buffer + 172), v7) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_59;
      }
      v21 = 17;
      goto LABEL_58;
    }
    v8 = 1;
    v2 = (PIRP)Irp;
    Buffer = v36;
  }
  if ( Options == 10 )
  {
    memset(v43, 0, 48);
    String2 = 0;
    v45 = 0;
    if ( v2->AssociatedIrp.MasterIrp->Flags > 0xFFFE )
    {
      v17 = -1073741562;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, 3221225734LL);
      }
      goto LABEL_117;
    }
    NewFileSize.QuadPart = (LONGLONG)(Buffer + 148);
    LOBYTE(v13) = 1;
    for ( i = (struct _FCB *)RxFcbTableLookupFirstFcb(Buffer + 148, &FsContext[21], v13, v43);
          ;
          i = (struct _FCB *)RxFcbTableLookupNextFcb(v43) )
    {
      v23 = i;
      if ( !i )
        break;
      _RxAcquireFcb(i, 0, 1u, 0, (PCSTR)PostIrpRoutine, (ULONG)v35);
      RxPurgeConflictingSrvOpensEx((ULONG_PTR)v23, 0, 0, 0);
      if ( !RxpDereferenceAndFinalizeNetFcb(v23, 0, 0, 0) )
        _RxReleaseFcb(0, (PMRX_FCB)&v23->Header, v24, v25, (ULONG)PostIrpRoutine);
    }
    RxFcbTableEndLookup(v43);
    v26 = RxpBuildTargetFcbTableNameForRename(RxContext, Irp, &String2, &v45);
    v17 = v26;
    if ( v26 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
          (unsigned int)v26);
      }
      goto LABEL_117;
    }
    if ( !RtlEqualUnicodeString(FsContext + 21, &String2, *((_BYTE *)v36 + 472)) )
    {
      LOBYTE(v13) = 1;
      for ( j = (struct _FCB *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RxFcbTableLookupFirstFcb)(
                                 (LARGE_INTEGER)NewFileSize.QuadPart,
                                 &String2,
                                 v13,
                                 v43); ; j = (struct _FCB *)RxFcbTableLookupNextFcb(v43) )
      {
        ThisFcb = j;
        if ( !j )
          break;
        _RxAcquireFcb(j, 0, 1u, 0, (PCSTR)PostIrpRoutine, (ULONG)v35);
        RxPurgeConflictingSrvOpensEx((ULONG_PTR)ThisFcb, 0, 0, 0);
        NewFileSize.LowPart = (ULONG)ThisFcb->ScavengerFinalizationList.Flink;
        if ( !RxpDereferenceAndFinalizeNetFcb(ThisFcb, 0, 0, 0) )
          _RxReleaseFcb(0, (PMRX_FCB)&ThisFcb->Header, v28, v29, (ULONG)PostIrpRoutine);
        if ( NewFileSize.LowPart )
        {
          v17 = -1073741790;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            LODWORD(v35) = -1073741790;
            LODWORD(PostIrpRoutine) = NewFileSize.LowPart;
            WPP_SF_qdD(WPP_GLOBAL_Control->AttachedDevice, NewFileSize.LowPart, v28, ThisFcb);
          }
          break;
        }
      }
      RxFcbTableEndLookup(v43);
    }
    if ( v45 )
    {
      ExFreePoolWithTag(String2.Buffer, 0);
      String2.Buffer = 0;
    }
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        LODWORD(v35) = v17;
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
          RxContext,
          FsContext,
          v35);
      }
      goto LABEL_117;
    }
    v2 = (PIRP)Irp;
    Buffer = v36;
  }
  if ( (HIDWORD(FsContext[9].Buffer) & 4) == 0 )
  {
    v16 = _RxAcquireFcb((PFCB)FsContext, RxContext, 1u, 0, (PCSTR)PostIrpRoutine, (ULONG)v35);
    v17 = v16;
    if ( v16 != -1073741739 )
    {
      if ( v16 )
        goto LABEL_117;
      v15 = 1;
      v2 = (PIRP)Irp;
      Buffer = v36;
      goto LABEL_15;
    }
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
LABEL_59:
      v17 = -1069481981;
      BYTE3(RxContext->RealDevice) = 1;
      goto LABEL_117;
    }
    v21 = 22;
LABEL_58:
    WPP_SF_(v20->AttachedDevice, v21, &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids);
    goto LABEL_59;
  }
LABEL_15:
  if ( (HIDWORD(FsContext[9].Buffer) & 0x80u) != 0 )
  {
    v17 = -1073741528;
    goto LABEL_117;
  }
  v17 = 0;
  v18 = Options - 10;
  if ( Options == 10 || (v18 = Options - 11, Options == 11) )
  {
    if ( *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 38) )
      goto LABEL_20;
    SeCaptureSubjectContext((PSECURITY_SUBJECT_CONTEXT)((char *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory
                                                      + 40));
    *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 38) = 1;
    goto LABEL_111;
  }
  v18 = Options - 13;
  if ( Options == 13 )
  {
    if ( !v2->AssociatedIrp.MasterIrp->Type )
      goto LABEL_20;
    if ( !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)&FsContext[19].Length + 8LL), MmFlushForDelete) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids);
      }
      v17 = -1073741535;
      goto LABEL_117;
    }
LABEL_111:
    v2 = (PIRP)Irp;
    Buffer = v36;
    goto LABEL_20;
  }
  if ( Options == 39 )
  {
    NewFileSize.QuadPart = 0;
    if ( !MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)&FsContext[19].Length + 8LL), &NewFileSize) )
      v17 = -1073741245;
    goto LABEL_111;
  }
LABEL_20:
  if ( v17 >= 0 )
  {
    if ( *((_BYTE *)Buffer + 77)
      || (v17 = FsRtlCheckOplock(
                  (POPLOCK)&FsContext[5].Buffer,
                  v2,
                  RxContext,
                  RxUpperOplockBreakCompleteAsync,
                  RxPrePostIrp),
          v17 != 259) )
    {
      switch ( Options )
      {
        case 0x19u:
LABEL_27:
          v19 = RxSetPipeInfo(RxContext, Irp, FsContext, v39);
          break;
        case 0xEu:
          v17 = RxSetPositionInfo(v18, Irp, v13);
          goto LABEL_117;
        case 4u:
          v17 = RxSetBasicInfo(RxContext, Irp, FsContext, v39);
          goto LABEL_117;
        case 0x27u:
LABEL_32:
          v17 = RxSetSimpleInfo(RxContext, Irp, v13);
          goto LABEL_117;
        default:
          switch ( Options )
          {
            case 0xAu:
            case 0xBu:
            case 0x1Fu:
              if ( !v6 )
              {
                BYTE3(RxContext->RealDevice) = 1;
                v17 = -1069481981;
                goto LABEL_117;
              }
              PostIrpRoutine = &Fcb;
              v19 = RxSetRenameLinkClusterInfo(RxContext, Irp, FsContext, v39);
              break;
            case 0xDu:
              v19 = RxSetDispositionInfo(RxContext, Irp, FsContext);
              goto LABEL_28;
            case 0x13u:
              v19 = RxSetAllocationInfo((__int64)RxContext, Irp, (__int64)FsContext);
              goto LABEL_28;
            case 0x14u:
              v17 = RxSetEndOfFileInfo((__int64)RxContext, Irp, (struct _CC_FILE_SIZES *)FsContext, v39);
              goto LABEL_117;
            case 0x17u:
            case 0x18u:
              goto LABEL_27;
            case 0x1Du:
            case 0x28u:
              goto LABEL_32;
            default:
              goto LABEL_48;
          }
          break;
      }
LABEL_28:
      v17 = v19;
    }
  }
LABEL_117:
  if ( v15 )
    _RxReleaseFcb(RxContext, (PMRX_FCB)FsContext, v13, (PCSTR)Buffer, (ULONG)PostIrpRoutine);
  if ( v8 )
    ExReleaseResourceLite((PERESOURCE)(v36 + 172));
  if ( Fcb )
  {
    _RxAcquireFcb(Fcb, 0, 1u, 0, (PCSTR)PostIrpRoutine, (ULONG)v35);
    if ( !RxpDereferenceAndFinalizeNetFcb(Fcb, 0, 0, 0) )
      _RxReleaseFcb(0, (PMRX_FCB)&Fcb->Header, v31, v32, PostIrpRoutinea);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      24,
      &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
      (unsigned int)v17);
  }
  if ( v17 != 259 && BYTE3(RxContext->RealDevice) )
    return (unsigned int)RxFsdPostRequest(RxContext);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14006f9e0  mov     [rsp+arg_8], rdx
0x14006f9e5  mov     [rsp+arg_0], rcx
0x14006f9ea  push    rbx
0x14006f9eb  push    rsi
0x14006f9ec  push    rdi
0x14006f9ed  push    r12
0x14006f9ef  push    r13
0x14006f9f1  push    r14
0x14006f9f3  push    r15
0x14006f9f5  sub     rsp, 0C0h
0x14006f9fc  mov     r10, rdx
0x14006f9ff  mov     rsi, rcx
0x14006fa02  mov     rdi, [rdx+0B8h]
0x14006fa09  mov     r14d, [rdi+10h]
0x14006fa0d  mov     r12d, [rcx+78h]
0x14006fa11  and     r12d, 2
0x14006fa15  setnz   r11b
0x14006fa19  mov     [rsp+0F8h+arg_10], r11b
0x14006fa21  xor     r13b, r13b
0x14006fa24  mov     [rsp+0F8h+var_B3], r13b
0x14006fa29  mov     [rsp+0F8h+Fcb], 0
0x14006fa32  mov     rax, [rdi+30h]
0x14006fa36  test    rax, rax
0x14006fa39  jz      loc_1400703A0
0x14006fa3f  mov     rbx, [rax+18h]
0x14006fa43  mov     [rsp+0F8h+var_90], rbx
0x14006fa48  mov     r15, [rax+20h]
0x14006fa4c  mov     [rsp+0F8h+var_98], r15
0x14006fa51  movzx   eax, word ptr [rbx]
0x14006fa54  mov     ecx, 0EC23h
0x14006fa59  cmp     ax, cx
0x14006fa5c  jz      loc_140070387
0x14006fa62  movzx   edx, ax
0x14006fa65  mov     r8d, 0EC20h
0x14006fa6b  mov     dword ptr [rsp+0F8h+NewFileSize], edx
0x14006fa72  mov     r9, [rbx+78h]
0x14006fa76  mov     [rsp+0F8h+var_B0], r9
0x14006fa7b  mov     [rsp+0F8h+var_78], r9
0x14006fa83  lea     rax, WPP_GLOBAL_Control
0x14006fa8a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fa91  cmp     rcx, rax
0x14006fa94  jz      short loc_14006FAA1
0x14006fa96  mov     eax, [rcx+2Ch]
0x14006fa99  test    al, 20h
0x14006fa9b  jnz     loc_14007F3FE
0x14006faa1  xor     r15b, r15b
0x14006faa4  mov     [rsp+0F8h+var_B4], r15b
0x14006faa9  mov     [rsp+0F8h+var_B8], 0
0x14006fab1  movzx   edx, dx
0x14006fab4  cmp     edx, 0EC27h
0x14006faba  jnz     loc_14006FD21
0x14006fac0  cmp     r14d, 14h
0x14006fac4  jz      loc_14006FC68
0x14006faca  lea     eax, [r14-0Ah]
0x14006face  cmp     eax, 1
0x14006fad1  jbe     loc_14006FDC7
0x14006fad7  cmp     r14d, 1Fh
0x14006fadb  jz      loc_14006FDC7
0x14006fae1  cmp     r14d, 0Ah
0x14006fae5  jz      loc_14006FE4A
0x14006faeb  mov     eax, [rbx+9Ch]
0x14006faf1  test    al, 4
0x14006faf3  jnz     short loc_14006FB37
0x14006faf5  xor     r9d, r9d; LineNumber
0x14006faf8  mov     r8d, 1; Mode
0x14006fafe  mov     rdx, rsi; RxContext
0x14006fb01  mov     rcx, rbx; Fcb
0x14006fb04  call    __RxAcquireFcb
0x14006fb09  mov     edi, eax
0x14006fb0b  mov     [rsp+0F8h+var_B8], eax
0x14006fb0f  cmp     eax, 0C0000055h
0x14006fb14  jz      loc_14007017B
0x14006fb1a  test    eax, eax
0x14006fb1c  jnz     loc_14006FC11
0x14006fb22  mov     r15b, 1
0x14006fb25  mov     [rsp+0F8h+var_B4], r15b
0x14006fb2a  mov     r10, [rsp+0F8h+arg_8]
0x14006fb32  mov     r9, [rsp+0F8h+var_B0]
0x14006fb37  mov     eax, [rbx+9Ch]
0x14006fb3d  test    al, al
0x14006fb3f  js      loc_14006FCB2
0x14006fb45  xor     edi, edi
0x14006fb47  mov     [rsp+0F8h+var_B8], edi
0x14006fb4b  mov     ecx, r14d
0x14006fb4e  sub     ecx, 0Ah
0x14006fb51  jz      loc_140070256
0x14006fb57  sub     ecx, 1
0x14006fb5a  jz      loc_140070256
0x14006fb60  sub     ecx, 2
0x14006fb63  jz      loc_1400701E9
0x14006fb69  cmp     ecx, 1Ah
0x14006fb6c  jz      loc_1400701AC
0x14006fb72  test    edi, edi
0x14006fb74  js      loc_14006FC11
0x14006fb7a  cmp     byte ptr [r9+4Dh], 0
0x14006fb7f  jnz     short loc_14006FBB7
0x14006fb81  lea     rcx, [rbx+58h]; Oplock
0x14006fb85  lea     rax, RxPrePostIrp
0x14006fb8c  mov     [rsp+0F8h+PostIrpRoutine], rax; SerialNumber
0x14006fb91  lea     r9, RxUpperOplockBreakCompleteAsync; CompletionRoutine
0x14006fb98  mov     r8, rsi; Context
0x14006fb9b  mov     rdx, r10; Irp
0x14006fb9e  call    cs:__imp_FsRtlCheckOplock
0x14006fba5  nop     dword ptr [rax+rax+00h]
0x14006fbaa  mov     edi, eax
0x14006fbac  mov     [rsp+0F8h+var_B8], eax
0x14006fbb0  cmp     eax, 103h
0x14006fbb5  jz      short loc_14006FC11
0x14006fbb7  cmp     r14d, 19h
0x14006fbbb  jz      short loc_14006FBF3; jumptable 000000014006FCF1 cases 23,24
0x14006fbbd  cmp     r14d, 0Eh
0x14006fbc1  jz      short loc_14006FC1D
0x14006fbc3  cmp     r14d, 4
0x14006fbc7  jnz     short loc_14006FC3C
0x14006fbc9  mov     r9, [rsp+0F8h+var_98]
0x14006fbce  mov     r8, rbx
0x14006fbd1  mov     rdx, [rsp+0F8h+arg_8]
0x14006fbd9  mov     rcx, rsi
0x14006fbdc  call    RxSetBasicInfo
0x14006fbe1  mov     [rsp+0F8h+var_B8], eax
0x14006fbe5  mov     edi, eax
0x14006fbe7  lea     r14, WPP_GLOBAL_Control
0x14006fbee  jmp     loc_1400702FD
0x14006fbf3  mov     r9, [rsp+0F8h+var_98]; jumptable 000000014006FCF1 cases 23,24
0x14006fbf8  mov     r8, rbx
0x14006fbfb  mov     rdx, [rsp+0F8h+arg_8]
0x14006fc03  mov     rcx, rsi
0x14006fc06  call    RxSetPipeInfo
0x14006fc0b  mov     [rsp+0F8h+var_B8], eax
0x14006fc0f  mov     edi, eax
0x14006fc11  lea     r14, WPP_GLOBAL_Control
0x14006fc18  jmp     loc_1400702FD
0x14006fc1d  mov     rdx, [rsp+0F8h+arg_8]
0x14006fc25  call    RxSetPositionInfo
0x14006fc2a  mov     [rsp+0F8h+var_B8], eax
0x14006fc2e  mov     edi, eax
0x14006fc30  lea     r14, WPP_GLOBAL_Control
0x14006fc37  jmp     loc_1400702FD
0x14006fc3c  cmp     r14d, 27h ; '''
0x14006fc40  jnz     loc_14006FCC7
0x14006fc46  mov     rdx, [rsp+0F8h+arg_8]; jumptable 000000014006FCF1 cases 29,40
0x14006fc4e  mov     rcx, rsi
0x14006fc51  call    RxSetSimpleInfo
0x14006fc56  mov     [rsp+0F8h+var_B8], eax
0x14006fc5a  mov     edi, eax
0x14006fc5c  lea     r14, WPP_GLOBAL_Control
0x14006fc63  jmp     loc_1400702FD
0x14006fc68  cmp     byte ptr [rdi+21h], 0
0x14006fc6c  jz      loc_14006FACA
0x14006fc72  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fc79  lea     r14, WPP_GLOBAL_Control
0x14006fc80  cmp     rcx, r14
0x14006fc83  jz      short loc_14006FC90
0x14006fc85  mov     eax, [rcx+2Ch]
0x14006fc88  test    al, 20h
0x14006fc8a  jnz     loc_14006FD79
0x14006fc90  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fc97  cmp     rcx, r14
0x14006fc9a  jz      short loc_14006FCA7
0x14006fc9c  mov     eax, [rcx+2Ch]
0x14006fc9f  test    al, 20h
0x14006fca1  jnz     loc_14006FDA0
0x14006fca7  xor     edi, edi
0x14006fca9  mov     [rsp+0F8h+var_B8], edi
0x14006fcad  jmp     loc_1400702FD
0x14006fcb2  mov     edi, 0C0000128h
0x14006fcb7  mov     [rsp+0F8h+var_B8], edi
0x14006fcbb  lea     r14, WPP_GLOBAL_Control
0x14006fcc2  jmp     loc_1400702FD
0x14006fcc7  add     r14d, 0FFFFFFF6h; switch 31 cases
0x14006fccb  cmp     r14d, 1Eh
0x14006fccf  ja      def_14006FCF1; jumptable 000000014006FCF1 default case, cases 12,14-18,21,22,25-28,30,32-39
0x14006fcd5  movsxd  rax, r14d
0x14006fcd8  lea     rdx, cs:140000000h
0x14006fcdf  movzx   eax, ds:(byte_14002AD38 - 140000000h)[rdx+rax]
0x14006fce7  mov     ecx, ds:(jpt_14006FCF1 - 140000000h)[rdx+rax*4]
0x14006fcee  add     rcx, rdx
0x14006fcf1  jmp     rcx; switch jump
0x14006fcf7  mov     r9, [rsp+0F8h+var_98]; jumptable 000000014006FCF1 case 20
0x14006fcfc  mov     r8, rbx
0x14006fcff  mov     rdx, [rsp+0F8h+arg_8]
0x14006fd07  mov     rcx, rsi
0x14006fd0a  call    RxSetEndOfFileInfo
0x14006fd0f  mov     [rsp+0F8h+var_B8], eax
0x14006fd13  mov     edi, eax
0x14006fd15  lea     r14, WPP_GLOBAL_Control
0x14006fd1c  jmp     loc_1400702FD
0x14006fd21  mov     ecx, edx
0x14006fd23  sub     ecx, r8d
0x14006fd26  jz      loc_14006FAC0
0x14006fd2c  sub     ecx, 1
0x14006fd2f  jz      loc_14006FAC0
0x14006fd35  sub     ecx, 1
0x14006fd38  jz      loc_14006FAC0
0x14006fd3e  cmp     ecx, 4
0x14006fd41  jnz     short loc_14006FD58
0x14006fd43  mov     edi, 0C0000002h
0x14006fd48  mov     [rsp+0F8h+var_B8], edi
0x14006fd4c  lea     r14, WPP_GLOBAL_Control
0x14006fd53  jmp     loc_1400702FD
0x14006fd58  lea     rcx, aSetfileIllegal; "SetFile, Illegal TypeOfOpen = %08lx\n"
0x14006fd5f  call    cs:__imp_DbgPrint
0x14006fd66  nop     dword ptr [rax+rax+00h]
0x14006fd6b  mov     edi, 0C000000Dh; jumptable 000000014006FCF1 default case, cases 12,14-18,21,22,25-28,30,32-39
0x14006fd70  mov     [rsp+0F8h+var_B8], edi
0x14006fd74  jmp     loc_14006FC11
0x14006fd79  cmp     byte ptr [rcx+29h], 4
0x14006fd7d  jb      loc_14006FC90
0x14006fd83  mov     edx, 0Fh
0x14006fd88  mov     r9, rsi
0x14006fd8b  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x14006fd92  mov     rcx, [rcx+18h]
0x14006fd96  call    WPP_SF_q
0x14006fd9b  jmp     loc_14006FC90
0x14006fda0  cmp     byte ptr [rcx+29h], 2
0x14006fda4  jb      loc_14006FCA7
0x14006fdaa  mov     edx, 10h
0x14006fdaf  mov     r9, rsi
0x14006fdb2  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x14006fdb9  mov     rcx, [rcx+18h]
0x14006fdbd  call    WPP_SF_q
0x14006fdc2  jmp     loc_14006FCA7
0x14006fdc7  lea     rcx, [r9+158h]; Resource
0x14006fdce  movzx   edx, r11b; Wait
0x14006fdd2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14006fdd9  nop     dword ptr [rax+rax+00h]
0x14006fdde  test    al, al
0x14006fde0  jnz     short loc_14006FE30
0x14006fde2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fde9  lea     r14, WPP_GLOBAL_Control
0x14006fdf0  cmp     rcx, r14
0x14006fdf3  jz      short loc_14006FE1E
0x14006fdf5  mov     eax, [rcx+2Ch]
0x14006fdf8  test    al, 20h
0x14006fdfa  jz      short loc_14006FE1E
0x14006fdfc  cmp     byte ptr [rcx+29h], 4
0x14006fe00  jb      short loc_14006FE1E
0x14006fe02  mov     edx, 11h
0x14006fe07  jmp     short loc_14006FE0E
0x14006fe09  mov     edx, 16h
0x14006fe0e  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x14006fe15  mov     rcx, [rcx+18h]
0x14006fe19  call    WPP_SF_
0x14006fe1e  mov     edi, 0C0410003h
0x14006fe23  mov     [rsp+0F8h+var_B8], edi
0x14006fe27  mov     byte ptr [rsi+23h], 1
0x14006fe2b  jmp     loc_1400702FD
0x14006fe30  mov     r13b, 1
0x14006fe33  mov     [rsp+0F8h+var_B3], r13b
0x14006fe38  mov     r10, [rsp+0F8h+arg_8]
0x14006fe40  mov     r9, [rsp+0F8h+var_B0]
0x14006fe45  jmp     loc_14006FAE1
0x14006fe4a  xorps   xmm0, xmm0
0x14006fe4d  movups  [rsp+0F8h+var_70], xmm0
0x14006fe55  movups  [rsp+0F8h+var_60], xmm0
0x14006fe5d  movups  [rsp+0F8h+var_50], xmm0
0x14006fe65  movups  xmmword ptr [rsp+0F8h+String2.Length], xmm0
0x14006fe6a  mov     [rsp+0F8h+arg_10], 0
0x14006fe72  mov     rax, [r10+18h]
0x14006fe76  cmp     dword ptr [rax+10h], 0FFFEh
0x14006fe7d  jbe     short loc_14006FED1
0x14006fe7f  mov     edi, 0C0000106h
0x14006fe84  mov     [rsp+0F8h+var_B8], edi
0x14006fe88  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fe8f  lea     r14, WPP_GLOBAL_Control
0x14006fe96  cmp     rcx, r14
0x14006fe99  jz      loc_1400702FD
0x14006fe9f  mov     eax, [rcx+2Ch]
0x14006fea2  test    al, 1
0x14006fea4  jz      loc_1400702FD
0x14006feaa  cmp     byte ptr [rcx+29h], 1
0x14006feae  jb      loc_1400702FD
0x14006feb4  mov     edx, 12h
0x14006feb9  mov     r9d, edi
0x14006febc  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x14006fec3  mov     rcx, [rcx+18h]
0x14006fec7  call    WPP_SF_d
0x14006fecc  jmp     loc_1400702FD
0x14006fed1  lea     rdx, [rbx+150h]
0x14006fed8  lea     rcx, [r9+128h]
0x14006fedf  mov     qword ptr [rsp+0F8h+NewFileSize], rcx
0x14006fee7  lea     r9, [rsp+0F8h+var_70]
0x14006feef  mov     r8b, 1
0x14006fef2  call    RxFcbTableLookupFirstFcb
0x14006fef7  mov     rdi, rax
0x14006fefa  test    rax, rax
0x14006fefd  jz      short loc_14006FF4F
0x14006feff  xor     r9d, r9d; LineNumber
0x14006ff02  xor     edx, edx; RxContext
0x14006ff04  mov     r8d, 1; Mode
0x14006ff0a  mov     rcx, rax; Fcb
0x14006ff0d  call    __RxAcquireFcb
0x14006ff12  xor     r9d, r9d
0x14006ff15  xor     r8d, r8d
0x14006ff18  xor     edx, edx
0x14006ff1a  mov     rcx, rdi; BugCheckParameter2
0x14006ff1d  call    RxPurgeConflictingSrvOpensEx
0x14006ff22  xor     r9d, r9d; ForceFinalize
0x14006ff25  xor     r8d, r8d; RecursiveFinalize
0x14006ff28  xor     edx, edx; RxContext
  ... truncated ...
```
