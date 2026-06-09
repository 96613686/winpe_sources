# RxCommonRead

- ea: `0x140066390`
- end: `0x1400679b3`
- name: `RxCommonRead`
- size: `5667`
- prototype: `__int64 __usercall@<rax>(PRX_CONTEXT RxContext@<rcx>, PIRP Irp@<rdx>, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `32`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004a4e0`

## callees

- `0x140004180`
- `0x1400079b0`
- `0x140007ca0`
- `0x140008030`
- `0x140008190`
- `0x140008220`
- `0x140009b80`
- `0x140010570`
- `0x1400108f0`
- `0x140011130`
- `0x140012320`
- `0x140015230`
- `0x140016d40`
- `0x140016e20`
- `0x140016e70`
- `0x140016ec0`
- `0x140017040`
- `0x140017220`
- `0x140017280`
- `0x140017370`
- `0x14001d35c`
- `0x14001d4a8`
- `0x14001d50c`
- `0x14001d658`
- `0x140025c20`
- `0x140025d00`
- `0x140026080`
- `0x140057660`
- `0x140065e40`
- `0x140066390`
- `0x140067ad0`
- `0x1400764b0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140066617`
- `ntoskrnl!KeInitializeEvent` at `0x140066617`
- `ntoskrnl!CcInitializeCacheMap` at `0x14006694b`
- `ntoskrnl!CcInitializeCacheMap` at `0x14006694b`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140067109`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140067109`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140067554`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140067554`
- `ntoskrnl!MmIsFileSectionActive` at `0x14006709c`
- `ntoskrnl!MmIsFileSectionActive` at `0x14006709c`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x140066a0f`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x140066c68`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x140067582`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x140066a0f`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x140066c68`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x140067582`
- `ntoskrnl!CcCopyRead` at `0x140066b2d`
- `ntoskrnl!CcCopyRead` at `0x140066b2d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400666b7`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400666b7`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x140066ecb`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x140066ecb`
- `ntoskrnl!CcSetReadAheadGranularityEx` at `0x140066a70`
- `ntoskrnl!CcSetReadAheadGranularityEx` at `0x140066a70`

## string_xrefs

- `0x14007b1a3`: `RxCommonRead`

## pseudocode

```c
__int64 __fastcall RxCommonRead(PRX_CONTEXT RxContext, PIRP Irp)
{
  PIRP v2; // r13
  PRX_CONTEXT v3; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _FILE_OBJECT *v5; // rax
  PNON_PAGED_FCB NonPagedFcb; // r15
  ULONG_PTR FsContext; // rbx
  _DWORD *FsContext2; // r9
  __int64 v9; // rdx
  char v10; // r8
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *Flink; // rax
  ULONG Flags; // ecx
  char v14; // r14
  bool v15; // r10
  int v16; // r11d
  int v17; // ecx
  LARGE_INTEGER ByteOffset; // rdx
  unsigned __int64 v19; // r11
  __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  PIRP CurrentIrp; // rdi
  __int64 v24; // rdx
  __int64 v25; // r8
  struct _IO_STACK_LOCATION *v26; // rax
  bool v27; // r8
  _DWORD *v28; // rdx
  PFILE_OBJECT v29; // r15
  _DWORD *v30; // rdi
  struct _FILE_OBJECT *v31; // rdx
  _DWORD *v32; // rcx
  _BOOL8 v33; // r9
  signed __int64 v34; // r8
  const char *v35; // r10
  int v36; // edx
  __int64 v37; // r11
  ULONG v38; // edi
  bool v39; // al
  __int64 v40; // r8
  NTSTATUS Status; // edi
  struct _CC_FILE_SIZES *v42; // rdx
  __int64 v43; // r8
  int v44; // eax
  _BYTE *v45; // rcx
  unsigned __int8 v46; // dl
  __int64 (__fastcall *v47)(PRX_CONTEXT, PMRX_SRV_OPEN); // rax
  BOOLEAN v48; // r9
  __int64 v49; // rcx
  int v50; // eax
  PFILE_OBJECT v51; // rcx
  _DWORD *v52; // rdx
  _QWORD *p_DataSectionObject; // rax
  NTSTATUS v54; // eax
  char v55; // r11
  _QWORD *v56; // rax
  PDEVICE_OBJECT v57; // rcx
  __int64 v58; // rdx
  NTSTATUS v59; // eax
  PDEVICE_OBJECT v60; // rcx
  __int64 v61; // rdx
  LARGE_INTEGER *p_FileOffset; // rdx
  __int64 v63; // rcx
  ULONG v64; // r8d
  PCSTR v65; // r9
  NTSTATUS v66; // eax
  NTSTATUS v67; // eax
  __int64 v68; // r8
  PDEVICE_OBJECT v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 (__fastcall *v72)(PRX_CONTEXT, PMRX_SRV_OPEN); // rax
  int v73; // eax
  PDEVICE_OBJECT v74; // rcx
  __int64 v75; // rdx
  __int64 v76; // rcx
  NTSTATUS v77; // eax
  PVOID v78; // rax
  int v80; // eax
  const char *v81; // rax
  const char *v82; // r8
  const char *v83; // r10
  const char *v84; // r11
  const CHAR *LazyWriteContext; // [rsp+20h] [rbp-138h]
  ULONG LazyWriteContexta; // [rsp+20h] [rbp-138h]
  ULONG LazyWriteContextb; // [rsp+20h] [rbp-138h]
  ULONG IoStatus; // [rsp+28h] [rbp-130h]
  bool v89; // [rsp+70h] [rbp-E8h]
  unsigned __int8 v90; // [rsp+71h] [rbp-E7h]
  char v91; // [rsp+78h] [rbp-E0h]
  char v92; // [rsp+79h] [rbp-DFh]
  char v93; // [rsp+7Bh] [rbp-DDh]
  char v94; // [rsp+7Ch] [rbp-DCh]
  ULONG Length; // [rsp+80h] [rbp-D8h]
  _DWORD *v96; // [rsp+88h] [rbp-D0h] BYREF
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-C8h]
  _DWORD *v98; // [rsp+98h] [rbp-C0h]
  signed __int64 QuadPart; // [rsp+A0h] [rbp-B8h]
  int v100; // [rsp+A8h] [rbp-B0h]
  _BYTE *v101; // [rsp+B0h] [rbp-A8h]
  PRX_CONTEXT v102; // [rsp+B8h] [rbp-A0h]
  ULONG LineNumber[2]; // [rsp+C0h] [rbp-98h]
  int v104; // [rsp+C8h] [rbp-90h]
  LARGE_INTEGER FileOffset; // [rsp+D0h] [rbp-88h] BYREF
  const char *v106; // [rsp+D8h] [rbp-80h]
  int v107; // [rsp+E0h] [rbp-78h]
  ULONG_PTR v108; // [rsp+E8h] [rbp-70h]
  _DWORD *v109; // [rsp+F0h] [rbp-68h]
  struct _FILE_OBJECT *v110; // [rsp+F8h] [rbp-60h]
  _BYTE *v111; // [rsp+100h] [rbp-58h]
  PIRP v112; // [rsp+108h] [rbp-50h]
  LARGE_INTEGER v113; // [rsp+110h] [rbp-48h]
  __int64 v114; // [rsp+118h] [rbp-40h] BYREF
  int v115; // [rsp+120h] [rbp-38h]
  int v116; // [rsp+124h] [rbp-34h]

  v2 = Irp;
  v3 = RxContext;
  v102 = RxContext;
  v112 = Irp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v5 = CurrentStackLocation->FileObject;
  FileObject = v5;
  v110 = v5;
  NonPagedFcb = RxContext->NonPagedFcb;
  if ( !v5 )
  {
    v9 = 0;
    FsContext = 0;
    v108 = 0;
    FsContext2 = 0;
    v98 = 0;
    v109 = 0;
    v80 = 60448;
    goto LABEL_309;
  }
  FsContext = (ULONG_PTR)v5->FsContext;
  v108 = FsContext;
  FsContext2 = v5->FsContext2;
  v98 = FsContext2;
  v109 = FsContext2;
  if ( *(_WORD *)FsContext == 0xEC23 && FsContext2 )
  {
    v80 = 60456;
    v9 = 0;
LABEL_309:
    LODWORD(v96) = v80;
    goto LABEL_4;
  }
  LOWORD(v96) = *(_WORD *)FsContext;
  v9 = 0;
LABEL_4:
  FileOffset.QuadPart = 0;
  v10 = 0;
  v93 = 0;
  v114 = 0;
  v115 = 0;
  LOWORD(v116) = 0;
  Blink = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
  if ( Blink )
  {
    Flink = Blink[42].Flink;
    if ( Flink )
    {
      LOBYTE(v9) = 3;
      ((void (__fastcall *)(PRX_CONTEXT, __int64))Flink)(RxContext, v9);
      v10 = 0;
      FsContext2 = v98;
      LODWORD(v9) = 0;
    }
  }
  v101 = *(_BYTE **)(FsContext + 120);
  Flags = v2->Flags;
  if ( (Flags & 2) != 0 )
  {
    v14 = 1;
  }
  else
  {
    v14 = 0;
    v90 = 0;
    if ( ((__int64)v3->RdbssDbgExtension & 2) == 0 )
      goto LABEL_10;
  }
  v90 = 1;
LABEL_10:
  v15 = (Flags & 1) != 0 || FsContext2 && (FsContext2[18] & 0x40000000) != 0;
  v89 = v15;
  v16 = (__int64)v3->RdbssDbgExtension & 0x1000;
  v100 = v16;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v81 = "Sy";
    if ( v16 )
      v81 = "--";
    v106 = "---";
    v82 = "Nc-";
    if ( !v15 )
      v82 = "---";
    v83 = "Pg-";
    if ( !v14 )
      v83 = "---";
    v84 = "Wt-";
    if ( !v90 )
      v84 = v106;
    if ( FsContext2 )
      LODWORD(v9) = FsContext2[18];
    WPP_SF_qqqDLissss(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      (_DWORD)v82,
      (_DWORD)v3,
      FsContext,
      (char)FsContext2,
      v9,
      CurrentStackLocation->Parameters.Read.Length,
      CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart,
      (__int64)v84,
      (__int64)v83,
      (__int64)v82,
      (__int64)v81);
    v10 = 0;
    FsContext2 = v98;
    v15 = v89;
  }
  v17 = (unsigned __int8)v101[77];
  if ( v17 == 4 || (v92 = 0, !v101[77]) )
  {
    v92 = 1;
  }
  else if ( v17 == 1 )
  {
    v10 = 1;
    v93 = 1;
  }
  v2->IoStatus.Information = 0;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  QuadPart = ByteOffset.QuadPart;
  FileOffset = ByteOffset;
  v19 = CurrentStackLocation->Parameters.Read.Length;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( ((__int64)v3->RdbssDbgExtension & 0x200) == 0 && !*(_BYTE *)(FsContext + 257) )
  {
    v20 = *(_QWORD *)&NonPagedFcb[2].AdvancedFcbHeaderMutex.Contention;
    if ( v20 )
    {
      v21 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8;
      _InterlockedIncrement((volatile signed __int32 *)(v21 + v20 + 104));
      if ( QuadPart != *((_QWORD *)FsContext2 + 19) )
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&NonPagedFcb[2].AdvancedFcbHeaderMutex.Contention
                                                        + v21
                                                        + 108));
      *((_QWORD *)FsContext2 + 19) = v19 + QuadPart;
      v22 = *(_QWORD *)&NonPagedFcb[2].AdvancedFcbHeaderMutex.Contention;
      if ( v14 )
      {
        _InterlockedAdd64((volatile signed __int64 *)(v22 + v21 + 16), v19);
      }
      else if ( v15 )
      {
        _InterlockedAdd64((volatile signed __int64 *)(v22 + v21 + 24), v19);
      }
      else
      {
        _InterlockedAdd64((volatile signed __int64 *)(v22 + v21 + 32), v19);
      }
    }
    ByteOffset.QuadPart = QuadPart;
  }
  if ( v10 && v14 )
    return 3221225488LL;
  if ( !(_DWORD)v19 )
    return 0;
  if ( (_WORD)v96 != 0xEC22 && (_WORD)v96 != 0xEB1F )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids,
        (unsigned __int16)v96);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids, 3221225488LL);
    }
    return 3221225488LL;
  }
  v111 = v101;
  v107 = v100;
  v104 = v19;
  v91 = 0;
  v113 = ByteOffset;
  CurrentIrp = v3->CurrentIrp;
  KeInitializeEvent((PRKEVENT)&v3->PrefixClaim.NetRootType, NotificationEvent, 0);
  *((_WORD *)&v3->9 + 60) = 0;
  v26 = CurrentIrp->Tail.Overlay.CurrentStackLocation;
  *((_WORD *)&v3->9 + 88) = 0;
  *((_QWORD *)&v3->9 + 23) = 0;
  *((_DWORD *)&v3->9 + 43) = v26->Parameters.Create.Options;
  v3->Create.PipeCompletionMode = (CurrentIrp->Flags >> 1) & 1;
  *((_QWORD *)&v3->9 + 19) = *(_QWORD *)&v3->pFcb[1].OpenCount;
  if ( v93 )
    return RxIssuePipeRead(v3, Length);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    IoStatus = *(_DWORD *)(FsContext + 160);
    LODWORD(LazyWriteContext) = *(_DWORD *)(FsContext + 164);
    WPP_SF_LDD(WPP_GLOBAL_Control->AttachedDevice, v24, v25, *(unsigned int *)(FsContext + 156));
  }
  v27 = v89;
  if ( v89 || (*(_DWORD *)(FsContext + 164) & 1) == 0 )
  {
    v28 = v98;
  }
  else
  {
    v28 = v98;
    if ( (*(_DWORD *)(FsContext + 160) & 0x2000000) != 0 && (*(_DWORD *)(*((_QWORD *)v98 + 4) + 72LL) & 1) == 0 )
    {
      v29 = FileObject;
      goto LABEL_117;
    }
  }
  v29 = FileObject;
  if ( v14 )
  {
LABEL_33:
    if ( !(unsigned __int8)ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(FsContext + 16))
      && !(unsigned __int8)RxAcquirePagingIoResourceShared(v3, FsContext, v90) )
    {
      v57 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v58 = 23;
LABEL_190:
        WPP_SF_q(v57->AttachedDevice, v58, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids, FsContext);
      }
      goto LABEL_165;
    }
    v30 = (_DWORD *)(FsContext + 164);
    v31 = (struct _FILE_OBJECT *)(FsContext + 160);
    v32 = v98 + 8;
LABEL_35:
    v96 = v32;
    FileObject = v31;
LABEL_36:
    v33 = v89;
    if ( (!v89
       && (*v30 & 1) != 0
       && (*(_DWORD *)&v31->Type & 0x2000000) != 0
       && (*(_DWORD *)(*(_QWORD *)v32 + 72LL) & 1) == 0
       || v14)
      && *(_DWORD *)(FsContext + 636) )
    {
      *(_DWORD *)(FsContext + 636) = 0;
    }
    v34 = *(_QWORD *)(FsContext + 32);
    *(_QWORD *)LineNumber = v34;
    v35 = *(const char **)(FsContext + 40);
    v106 = v35;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_iiDD(WPP_GLOBAL_Control->AttachedDevice, v31, v34, v34, v35, *v30, *(_DWORD *)&v31->Type);
      v34 = *(_QWORD *)LineNumber;
      v33 = v89;
      v35 = v106;
    }
    if ( !v14 )
    {
      if ( !FsRtlCheckLockForReadAccess((PFILE_LOCK)(FsContext + 536), v2) )
      {
        Status = -1073741740;
        goto LABEL_62;
      }
      v34 = *(_QWORD *)LineNumber;
      v33 = v89;
      v35 = v106;
    }
    v36 = *v30 & 1;
    if ( !v36 || (v33 || v14) && (*(_DWORD *)(FsContext + 156) & 0x10000) != 0 )
    {
      v37 = QuadPart;
      v38 = Length;
    }
    else
    {
      v37 = QuadPart;
      if ( QuadPart >= v34 )
      {
        v72 = *(__int64 (__fastcall **)(PRX_CONTEXT, PMRX_SRV_OPEN))(*(_QWORD *)(FsContext + 392) + 592LL);
        if ( v72 )
        {
          v73 = v72(v3, v3->pRelevantSrvOpen);
          Status = v73;
          if ( v73 != -1073741822 )
          {
            if ( v73 == -1069481981 )
              goto LABEL_165;
            if ( v73 < 0 )
            {
              v74 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || !BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                goto LABEL_62;
              }
              v75 = 30;
              goto LABEL_243;
            }
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids);
        }
        Status = -1073741807;
        goto LABEL_62;
      }
      v38 = Length;
      if ( Length > v34 - QuadPart )
      {
        v38 = v34 - QuadPart;
        Length = v34 - QuadPart;
        v104 = v34 - QuadPart;
      }
    }
    v39 = !v36 || (*(_DWORD *)&FileObject->Type & 0x2000000) == 0 || (*(_DWORD *)(*(_QWORD *)v96 + 72LL) & 1) != 0;
    if ( !v92 || v14 || v33 || v39 )
    {
      if ( !*(_BYTE *)(FsContext + 257) && v36 && (*(_DWORD *)(FsContext + 160) & 0x2000000) != 0 && v37 >= (__int64)v35 )
      {
        if ( v37 < v34 )
        {
          if ( v37 + v38 > v34 )
            v38 = v34 - v37;
          v78 = RxMapUserBuffer(v3, v2);
          memset(v78, 0, v38);
        }
        else
        {
          v38 = 0;
        }
        v2->IoStatus.Information = v38;
        Status = 0;
      }
      else
      {
        *((_DWORD *)&v3->9 + 42) = v38;
        v3->Create.TransportName.Buffer = (wchar_t *)v37;
        if ( v100 )
        {
          *((_QWORD *)&v3->9 + 23) = (__int64)v3->RxDeviceObject | 3;
          if ( LOBYTE(v3->Flags) )
          {
            RxSetFcbMainOwnerPointer(FsContext);
            *((_BYTE *)&v3->9 + 176) = 1;
          }
          if ( BYTE1(v3->Flags) )
          {
            RxSetFcbPagingOwnerPointer(FsContext, *((_QWORD *)&v3->9 + 23), v34, v33);
            *((_BYTE *)&v3->9 + 177) = 1;
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids, v3);
        }
        if ( !*(_BYTE *)(FsContext + 257) )
        {
          v40 = *(_QWORD *)&v3->NonPagedFcb[2].AdvancedFcbHeaderMutex.Contention;
          if ( v40 )
            _InterlockedAdd64(
              (volatile signed __int64 *)(((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8) + v40 + 40),
              *((unsigned int *)&v3->9 + 42));
          if ( (v3->Create.PipeCompletionMode & 1) == 0 && !v3->LockManagerContext )
            *((_WORD *)&v3->9 + 61) |= 8u;
        }
        Status = RxLowIoSubmit(v3, v2, (PFCB)FsContext, RxLowIoReadShellCompletion);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 44, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids, v3);
        }
        if ( Status == 259 )
        {
          v3 = 0;
          v102 = 0;
          v2 = 0;
        }
      }
      goto LABEL_62;
    }
    if ( v29->PrivateCacheMap )
    {
      v50 = *(_DWORD *)(FsContext + 156);
      if ( (v50 & 0x100) != 0 && (v50 & 0x8000000) == 0 && v37 >= 4096 )
      {
        CcSetAdditionalCacheAttributes(v29, 0, 0);
        *(_DWORD *)(FsContext + 156) &= ~0x100u;
      }
    }
    else
    {
      if ( (v29->Flags & 0x4000) != 0 )
      {
        Status = -1073741528;
        goto LABEL_62;
      }
      v42 = (struct _CC_FILE_SIZES *)(FsContext + 24);
      v43 = *(_QWORD *)(FsContext + 32);
      if ( v43 > *(_QWORD *)(FsContext + 24) )
      {
        v76 = *(unsigned int *)(*(_QWORD *)(FsContext + 120) + 104LL);
        v42->AllocationSize.QuadPart = ~(v76 - 1) & (v76 + v43);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids,
          v29,
          FsContext);
        v42 = (struct _CC_FILE_SIZES *)(FsContext + 24);
      }
      CcInitializeCacheMap(v29, v42, 0, &Callbacks, (PVOID)FsContext);
      if ( v91 )
      {
        RxSelectAndSwitchPagingFileObject(FsContext);
        ExConvertExclusiveToSharedLite(*(PERESOURCE *)(FsContext + 8));
      }
      if ( (*(_DWORD *)(*(_QWORD *)(FsContext + 392) + 8LL) & 0x1000) == 0
        || (*(_DWORD *)(FsContext + 156) & 0x8000000) != 0 )
      {
        CcSetAdditionalCacheAttributes(v29, 1u, 0);
        v44 = *(_DWORD *)(FsContext + 156);
        if ( (v44 & 0x8000000) == 0 )
          *(_DWORD *)(FsContext + 156) = v44 | 0x100;
      }
      else
      {
        CcSetAdditionalCacheAttributes(v29, 0, 0);
      }
      LOWORD(v114) = 16;
      HIDWORD(v114) = *((_DWORD *)v101 + 27);
      v115 = *((_DWORD *)v101 + 28);
      v116 = 0;
      CcSetReadAheadGranularityEx(v29, &v114);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids);
    }
    if ( (BYTE1(v3->RealDevice) & 2) != 0 )
    {
      Status = -1073741637;
      goto LABEL_62;
    }
    v45 = RxMapUserBuffer(v3, v2);
    v101 = v45;
    if ( !v45 )
    {
      Status = -1073741670;
      goto LABEL_62;
    }
    v46 = v90;
    if ( v90 && (*(_DWORD *)(FsContext + 156) & 0x2000000) != 0 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))RxInlineReadAhead)(v29, (LARGE_INTEGER)FileOffset.QuadPart, Length);
      v45 = v101;
      v46 = v90;
    }
    v47 = *(__int64 (__fastcall **)(PRX_CONTEXT, PMRX_SRV_OPEN))(*(_QWORD *)(FsContext + 392) + 592LL);
    if ( !v47 )
    {
LABEL_90:
      if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
      {
        McTemplateK0pp_EtwWriteTransfer(v45, &CcReadRequest, &v3->LowIoContext.Flags + 1, v3, v29);
        v45 = v101;
        v46 = v90;
      }
      v48 = (v98[18] & 8) != 0 || v46;
      if ( CcCopyRead(v29, &FileOffset, Length, v48, v45, &v2->IoStatus) )
      {
        Status = v2->IoStatus.Status;
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) == 0 )
          goto LABEL_62;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids);
        }
        v77 = RxAsyncCachedRead(v3, Length);
        Status = v77;
        if ( v77 == 259 )
        {
          v3 = 0;
          v102 = 0;
          v2 = 0;
          goto LABEL_62;
        }
        if ( v77 == -1069481981 )
          goto LABEL_165;
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) == 0 )
          goto LABEL_62;
      }
      McTemplateK0ppq_EtwWriteTransfer(v49, &CcReadCompletion, &v3->LowIoContext.Flags + 1, v3);
      goto LABEL_62;
    }
    Status = v47(v3, v3->pRelevantSrvOpen);
    if ( Status == -1073741822 )
    {
      v45 = v101;
      v46 = v90;
      goto LABEL_90;
    }
    if ( Status != -1069481981 )
    {
      if ( Status >= 0 )
      {
        v45 = v101;
        v46 = v90;
        goto LABEL_90;
      }
      v74 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_62;
      }
      v75 = 34;
LABEL_243:
      WPP_SF_qD(v74->AttachedDevice, v75, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids, v3->pRelevantSrvOpen);
      goto LABEL_62;
    }
LABEL_165:
    RxReleaseReadWriteResources(v3, FsContext);
    Status = RxFsdPostRequest(v3);
    v3 = 0;
    v102 = 0;
    goto LABEL_281;
  }
  if ( FileObject->SectionObjectPointer->DataSectionObject && (*(_BYTE *)(FsContext + 256) & 5) != 0 )
  {
    v94 = 0;
    v67 = _RxAcquireFcb((PFCB)FsContext, v3, 1u, 0, LazyWriteContext, IoStatus);
    Status = v67;
    if ( v67 < 0 )
    {
      if ( v67 != -1073741739 )
      {
        v69 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v70 = 22;
LABEL_205:
          WPP_SF_d(v69->AttachedDevice, v70, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids, (unsigned int)Status);
        }
        goto LABEL_62;
      }
      v60 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v61 = 21;
LABEL_164:
        WPP_SF_(v60->AttachedDevice, v61, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids);
      }
      goto LABEL_165;
    }
    LOBYTE(v68) = 1;
    RxAcquirePagingIoResource(v3, FsContext, v68);
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
      McTemplateK0p_EtwWriteTransfer(v71, &CcFlushRequest, &v3->LowIoContext.Flags + 1, FsContext);
    if ( ++*(_DWORD *)(FsContext + 636) > 0x10u )
    {
      LODWORD(v96) = 0;
      MmIsFileSectionActive(*(_QWORD *)(FsContext + 304) + 8LL, 7, &v96);
      if ( !(_DWORD)v96
        && (*(_DWORD *)(FsContext + 184) == *(_DWORD *)(FsContext + 188)
         || (*(_DWORD *)(FsContext + 164) & 1) == 0
         || (*(_DWORD *)(FsContext + 160) & 0x2000000) == 0) )
      {
        v94 = 1;
        *(_DWORD *)(FsContext + 636) = 0;
      }
    }
    p_FileOffset = &FileOffset;
    if ( v94 )
      p_FileOffset = 0;
    CcCoherencyFlushAndPurgeCache(v29->SectionObjectPointer, p_FileOffset, Length, &v2->IoStatus, 3u);
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
      McTemplateK0p_EtwWriteTransfer(v63, &CcFlushCompletion, &v3->LowIoContext.Flags + 1, FsContext);
    RxReleasePagingIoResource(v3, FsContext);
    _RxReleaseFcb(v3, (PMRX_FCB)FsContext, v64, v65, LazyWriteContextb);
    v2->IoStatus.Information = 0;
    Status = v2->IoStatus.Status;
    if ( Status < 0 )
      goto LABEL_62;
    v28 = v98;
    v27 = v89;
  }
LABEL_117:
  if ( v14 )
    goto LABEL_33;
  v30 = (_DWORD *)(FsContext + 164);
  *(_QWORD *)LineNumber = FsContext + 164;
  v51 = (PFILE_OBJECT)(FsContext + 160);
  FileObject = (PFILE_OBJECT)(FsContext + 160);
  v52 = v28 + 8;
  v96 = v52;
  while ( v92 && !v27 && (*v30 & 1) != 0 && (*(_DWORD *)&v51->Type & 0x2000000) != 0 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)v52 + 72LL) & 1) != 0
      || (p_DataSectionObject = &v29->SectionObjectPointer->DataSectionObject, *p_DataSectionObject)
      && p_DataSectionObject[1]
      && v29->PrivateCacheMap )
    {
      v51 = FileObject;
      break;
    }
    v54 = _RxAcquireFcb((PFCB)FsContext, v3, 1u, 0, LazyWriteContext, IoStatus);
    Status = v54;
    if ( v54 < 0 )
    {
      if ( v54 != -1073741739 )
        goto LABEL_62;
      v60 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v61 = 24;
        goto LABEL_164;
      }
      goto LABEL_165;
    }
    v55 = 1;
    v91 = 1;
LABEL_128:
    v30 = *(_DWORD **)LineNumber;
    v31 = FileObject;
    v32 = v96;
    if ( !v92 || v89 )
      goto LABEL_36;
    if ( (**(_DWORD **)LineNumber & 1) == 0
      || (*(_DWORD *)&FileObject->Type & 0x2000000) == 0
      || (*(_DWORD *)(*(_QWORD *)v96 + 72LL) & 1) != 0 )
    {
      v32 = v96;
      goto LABEL_35;
    }
    v56 = &v29->SectionObjectPointer->DataSectionObject;
    if ( *v56 )
    {
      if ( v56[1] )
      {
        v32 = v96;
        if ( v29->PrivateCacheMap )
          goto LABEL_36;
      }
    }
    v30 = *(_DWORD **)LineNumber;
    v31 = FileObject;
    v32 = v96;
    if ( v55 )
      goto LABEL_36;
    _RxReleaseFcb(v3, (PMRX_FCB)FsContext, LineNumber[0], (PCSTR)FileObject, LazyWriteContexta);
    v51 = FileObject;
    v52 = v96;
    v27 = 0;
  }
  if ( v90
    || !v27
    && (*v30 & 1) != 0
    && (*(_DWORD *)&v51->Type & 0x2000000) != 0
    && (*(_DWORD *)(*(_QWORD *)v52 + 72LL) & 1) == 0 )
  {
    v66 = _RxAcquireFcb((PFCB)FsContext, v3, 2u, 0, LazyWriteContext, IoStatus);
    Status = v66;
    if ( v66 < 0 )
    {
      if ( v66 != -1073741739 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids, FsContext);
        }
        goto LABEL_62;
      }
      v57 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v58 = 27;
        goto LABEL_190;
      }
      goto LABEL_165;
    }
    goto LABEL_226;
  }
  v59 = _RxAcquireFcb((PFCB)FsContext, v3, 3u, 0, LazyWriteContext, IoStatus);
  Status = v59;
  if ( v59 >= 0 )
  {
LABEL_226:
    v55 = v91;
    goto LABEL_128;
  }
  if ( v59 == -1073741739 )
  {
    v60 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v61 = 25;
      goto LABEL_164;
    }
    goto LABEL_165;
  }
  v69 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v70 = 26;
    goto LABEL_205;
  }
LABEL_62:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      36,
      &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids,
      (unsigned int)Status);
  }
  if ( !v14 && !v100 && (v29->Flags & 2) != 0 )
    v29->CurrentByteOffset.QuadPart = v2->IoStatus.Information + QuadPart;
LABEL_281:
  if ( Status >= 0 )
  {
    if ( Status != 259 )
    {
      if ( !v14 )
        v29->Flags |= 0x80000u;
      goto LABEL_282;
    }
  }
  else
  {
LABEL_282:
    RxReleaseReadWriteResources(v3, FsContext);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      37,
      &WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids,
      (unsigned int)Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140066390  mov     r11, rsp
0x140066393  mov     [r11+18h], rbx
0x140066397  mov     [r11+20h], rsi
0x14006639b  push    rdi
0x14006639c  push    r12
0x14006639e  push    r13
0x1400663a0  push    r14
0x1400663a2  push    r15
0x1400663a4  sub     rsp, 130h
0x1400663ab  mov     rax, cs:__security_cookie
0x1400663b2  xor     rax, rsp
0x1400663b5  mov     [rsp+158h+var_30], rax
0x1400663bd  mov     r13, rdx
0x1400663c0  mov     rsi, rcx
0x1400663c3  mov     [r11-0A0h], rcx
0x1400663ca  mov     [r11-50h], rdx
0x1400663ce  mov     rdi, [rdx+0B8h]
0x1400663d5  mov     rax, [rdi+30h]
0x1400663d9  mov     [rsp+158h+FileObject], rax
0x1400663e1  mov     [rsp+158h+var_60], rax
0x1400663e9  mov     r15, [rcx+50h]
0x1400663ed  test    rax, rax
0x1400663f0  jz      loc_140067905
0x1400663f6  mov     rbx, [rax+18h]
0x1400663fa  mov     [rsp+158h+var_70], rbx
0x140066402  mov     r9, [rax+20h]
0x140066406  mov     [rsp+158h+var_C0], r9
0x14006640e  mov     [rsp+158h+var_68], r9
0x140066416  movzx   eax, word ptr [rbx]
0x140066419  mov     ecx, 0EC23h
0x14006641e  cmp     ax, cx
0x140066421  jz      loc_1400678F0
0x140066427  mov     word ptr [rsp+158h+var_D0], ax
0x14006642f  xor     edx, edx
0x140066431  mov     qword ptr [rsp+158h+FileOffset], rdx
0x140066439  xor     r8b, r8b
0x14006643c  mov     [rsp+158h+var_DD], r8b
0x140066441  xor     eax, eax
0x140066443  mov     [rsp+158h+var_40], rax
0x14006644b  mov     [rsp+158h+var_38], eax
0x140066452  mov     word ptr [rsp+158h+var_34], ax
0x14006645a  mov     rax, [rsi+50h]
0x14006645e  mov     rax, [rax+160h]
0x140066465  test    rax, rax
0x140066468  jz      short loc_14006648D
0x14006646a  mov     rax, [rax+2A0h]
0x140066471  test    rax, rax
0x140066474  jz      short loc_14006648D
0x140066476  mov     dl, 3
0x140066478  mov     rcx, rsi
0x14006647b  call    _guard_dispatch_icall
0x140066480  xor     r8b, r8b
0x140066483  mov     r9, [rsp+158h+var_C0]
0x14006648b  xor     edx, edx
0x14006648d  mov     rax, [rbx+78h]
0x140066491  mov     [rsp+158h+var_A8], rax
0x140066499  mov     ecx, [r13+10h]
0x14006649d  test    cl, 2
0x1400664a0  jz      loc_1400678C3
0x1400664a6  mov     r14b, 1
0x1400664a9  mov     [rsp+158h+var_DE], r14b
0x1400664ae  mov     [rsp+158h+var_E7], 1
0x1400664b3  test    cl, 1
0x1400664b6  jz      loc_140067867
0x1400664bc  mov     r10b, 1
0x1400664bf  mov     [rsp+158h+var_E8], r10b
0x1400664c4  mov     r11d, [rsi+78h]
0x1400664c8  and     r11d, 1000h
0x1400664cf  mov     [rsp+158h+var_B0], r11d
0x1400664d7  lea     r12, WPP_GLOBAL_Control
0x1400664de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400664e5  cmp     rcx, r12
0x1400664e8  jz      short loc_1400664F5
0x1400664ea  mov     eax, [rcx+2Ch]
0x1400664ed  test    al, 4
0x1400664ef  jnz     loc_14007E5AE
0x1400664f5  mov     rax, [rsp+158h+var_A8]
0x1400664fd  movzx   ecx, byte ptr [rax+4Dh]
0x140066501  cmp     ecx, 4
0x140066504  jnz     loc_1400678A0
0x14006650a  mov     [rsp+158h+var_DF], 1
0x14006650f  mov     [r13+38h], rdx
0x140066513  mov     rdx, [rdi+18h]
0x140066517  mov     [rsp+158h+var_B8], rdx
0x14006651f  mov     qword ptr [rsp+158h+FileOffset], rdx
0x140066527  mov     r11d, [rdi+8]
0x14006652b  mov     [rsp+158h+Length], r11d
0x140066533  test    dword ptr [rsi+78h], 200h
0x14006653a  jnz     short loc_1400665A5
0x14006653c  cmp     byte ptr [rbx+101h], 0
0x140066543  jnz     short loc_1400665A5
0x140066545  mov     rdx, [r15+4F8h]
0x14006654c  test    rdx, rdx
0x14006654f  jz      short loc_14006659D
0x140066551  mov     eax, gs:1A4h
0x140066559  mov     ecx, eax
0x14006655b  shl     rcx, 8
0x14006655f  lock inc dword ptr [rcx+rdx+68h]
0x140066564  mov     rdi, [rsp+158h+var_B8]
0x14006656c  cmp     rdi, [r9+98h]
0x140066573  jnz     loc_14006792E
0x140066579  mov     rdx, r11
0x14006657c  lea     rax, [r11+rdi]
0x140066580  mov     [r9+98h], rax
0x140066587  mov     rax, [r15+4F8h]
0x14006658e  test    r14b, r14b
0x140066591  jz      loc_1400678E0
0x140066597  lock add [rax+rcx+10h], rdx
0x14006659d  mov     rdx, [rsp+158h+var_B8]
0x1400665a5  test    r8b, r8b
0x1400665a8  jnz     loc_14006794A
0x1400665ae  test    r11d, r11d
0x1400665b1  jz      loc_140067958
0x1400665b7  mov     eax, 0EC22h
0x1400665bc  mov     ecx, dword ptr [rsp+158h+var_D0]
0x1400665c3  cmp     cx, ax
0x1400665c6  jnz     loc_14007E66C
0x1400665cc  mov     rax, [rsp+158h+var_A8]
0x1400665d4  mov     [rsp+158h+var_58], rax
0x1400665dc  mov     eax, [rsp+158h+var_B0]
0x1400665e3  mov     [rsp+158h+var_78], eax
0x1400665ea  mov     [rsp+158h+var_90], r11d
0x1400665f2  mov     [rsp+158h+var_E4], 0C000000Dh
0x1400665fa  mov     [rsp+158h+var_E0], 0
0x1400665ff  mov     [rsp+158h+var_48], rdx
0x140066607  mov     rdi, [rsi+28h]
0x14006660b  lea     rcx, [rsi+180h]; Event
0x140066612  xor     r8d, r8d; State
0x140066615  xor     edx, edx; Type
0x140066617  call    cs:__imp_KeInitializeEvent
0x14006661e  nop     dword ptr [rax+rax+00h]
0x140066623  xor     ecx, ecx
0x140066625  mov     [rsi+208h], cx
0x14006662c  mov     rax, [rdi+0B8h]
0x140066633  mov     [rsi+240h], cx
0x14006663a  mov     [rsi+248h], rcx
0x140066641  mov     eax, [rax+10h]
0x140066644  mov     [rsi+23Ch], eax
0x14006664a  mov     eax, [rdi+10h]
0x14006664d  shr     eax, 1
0x14006664f  and     eax, 1
0x140066652  mov     [rsi+218h], eax
0x140066658  mov     rax, [rsi+38h]
0x14006665c  mov     r10, [rax+130h]
0x140066663  mov     [rsi+228h], r10
0x14006666a  cmp     [rsp+158h+var_DD], cl
0x14006666e  jnz     loc_14006795F
0x140066674  mov     rcx, cs:WPP_GLOBAL_Control
0x14006667b  cmp     rcx, r12
0x14006667e  jz      short loc_14006668B
0x140066680  mov     eax, [rcx+2Ch]
0x140066683  test    al, 10h
0x140066685  jnz     loc_1400671FB
0x14006668b  movzx   r8d, [rsp+158h+var_E8]
0x140066691  test    r8b, r8b
0x140066694  jz      loc_140066C83
0x14006669a  mov     rdx, [rsp+158h+var_C0]
0x1400666a2  mov     r15, [rsp+158h+FileObject]
0x1400666aa  test    r14b, r14b
0x1400666ad  jz      loc_14006722E
0x1400666b3  mov     rcx, [rbx+10h]; Resource
0x1400666b7  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1400666be  nop     dword ptr [rax+rax+00h]
0x1400666c3  test    al, al
0x1400666c5  jz      loc_140066E79
0x1400666cb  lea     rdi, [rbx+0A4h]
0x1400666d2  lea     rdx, [rbx+0A0h]
0x1400666d9  mov     rcx, [rsp+158h+var_C0]
0x1400666e1  add     rcx, 20h ; ' '
0x1400666e5  mov     [rsp+158h+var_D0], rcx
0x1400666ed  mov     [rsp+158h+FileObject], rdx
0x1400666f5  movzx   r9d, [rsp+158h+var_E8]
0x1400666fb  test    r9b, r9b
0x1400666fe  jz      loc_140066F48
0x140066704  test    r14b, r14b
0x140066707  jnz     loc_140066F6D
0x14006670d  mov     r8, [rbx+20h]
0x140066711  mov     qword ptr [rsp+158h+LineNumber], r8
0x140066719  mov     r10, [rbx+28h]
0x14006671d  mov     [rsp+158h+var_80], r10
0x140066725  mov     rcx, cs:WPP_GLOBAL_Control
0x14006672c  cmp     rcx, r12
0x14006672f  jnz     loc_140067028
0x140066735  test    r14b, r14b
0x140066738  jz      loc_140066EC1
0x14006673e  mov     edx, [rdi]
0x140066740  and     edx, 1
0x140066743  jnz     loc_140066EFA
0x140066749  mov     r11, [rsp+158h+var_B8]
0x140066751  mov     edi, [rsp+158h+Length]
0x140066758  test    edx, edx
0x14006675a  jz      short loc_140066783
0x14006675c  mov     rax, [rsp+158h+FileObject]
0x140066764  test    dword ptr [rax], 2000000h
0x14006676a  jz      short loc_140066783
0x14006676c  mov     rax, [rsp+158h+var_D0]
0x140066774  mov     rax, [rax]
0x140066777  mov     ecx, [rax+48h]
0x14006677a  test    cl, 1
0x14006677d  jnz     short loc_140066783
0x14006677f  xor     al, al
0x140066781  jmp     short loc_140066785
0x140066783  mov     al, 1
0x140066785  cmp     [rsp+158h+var_DF], 0
0x14006678a  jnz     loc_1400668B3
0x140066790  cmp     byte ptr [rbx+101h], 0
0x140066797  jz      loc_140066BBC
0x14006679d  mov     [rsi+238h], edi
0x1400667a3  mov     [rsi+230h], r11
0x1400667aa  cmp     [rsp+158h+var_B0], 0
0x1400667b2  jnz     loc_140066B7C
0x1400667b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400667bf  cmp     rcx, r12
0x1400667c2  jz      short loc_1400667CF
0x1400667c4  mov     eax, [rcx+2Ch]
0x1400667c7  test    al, 10h
0x1400667c9  jnz     loc_140067790
0x1400667cf  cmp     byte ptr [rbx+101h], 0
0x1400667d6  jnz     short loc_14006681B
0x1400667d8  mov     rax, [rsi+50h]
0x1400667dc  mov     r8, [rax+4F8h]
0x1400667e3  test    r8, r8
0x1400667e6  jz      short loc_140066802
0x1400667e8  mov     eax, gs:1A4h
0x1400667f0  mov     edx, [rsi+238h]
0x1400667f6  mov     ecx, eax
0x1400667f8  shl     rcx, 8
0x1400667fc  lock add [rcx+r8+28h], rdx
0x140066802  mov     eax, [rsi+218h]
0x140066808  test    al, 1
0x14006680a  jnz     short loc_14006681B
0x14006680c  cmp     qword ptr [rsi+70h], 0
0x140066811  jnz     short loc_14006681B
0x140066813  or      word ptr [rsi+20Ah], 8
0x14006681b  lea     r9, RxLowIoReadShellCompletion; CompletionRoutine
0x140066822  mov     r8, rbx; Fcb
0x140066825  mov     rdx, r13; Irp
0x140066828  mov     rcx, rsi; RxContext
0x14006682b  call    RxLowIoSubmit
0x140066830  mov     edi, eax
0x140066832  mov     rcx, cs:WPP_GLOBAL_Control
0x140066839  cmp     rcx, r12
0x14006683c  jz      short loc_140066849
0x14006683e  mov     eax, [rcx+2Ch]
0x140066841  test    al, 10h
0x140066843  jnz     loc_1400677B7
0x140066849  mov     [rsp+158h+var_E4], edi
0x14006684d  cmp     edi, 103h
0x140066853  jnz     short loc_140066864
0x140066855  xor     eax, eax
0x140066857  mov     esi, eax
0x140066859  mov     [rsp+158h+var_A0], rax
0x140066861  mov     r13d, eax
0x140066864  mov     rcx, cs:WPP_GLOBAL_Control
0x14006686b  cmp     rcx, r12
0x14006686e  jz      short loc_14006687B
0x140066870  mov     eax, [rcx+2Ch]
0x140066873  test    al, 10h
0x140066875  jnz     loc_1400677E2
0x14006687b  test    r14b, r14b
0x14006687e  jnz     loc_140067809
0x140066884  cmp     [rsp+158h+var_B0], 0
0x14006688c  jnz     loc_140067809
0x140066892  mov     eax, [r15+50h]
0x140066896  test    al, 2
0x140066898  jz      loc_140067809
0x14006689e  mov     rcx, [rsp+158h+var_B8]
0x1400668a6  add     rcx, [r13+38h]
0x1400668aa  mov     [r15+68h], rcx
0x1400668ae  jmp     loc_140067809
0x1400668b3  test    r14b, r14b
0x1400668b6  jnz     loc_140066790
0x1400668bc  test    r9b, r9b
0x1400668bf  jnz     loc_140066790
0x1400668c5  test    al, al
0x1400668c7  jnz     loc_140066790
0x1400668cd  cmp     qword ptr [r15+30h], 0
0x1400668d2  jnz     loc_140066C39
0x1400668d8  test    dword ptr [r15+50h], 4000h
0x1400668e0  jnz     loc_1400674FE
0x1400668e6  lea     rdx, [rbx+18h]
0x1400668ea  mov     r8, [rbx+20h]
0x1400668ee  cmp     r8, [rdx]
0x1400668f1  jg      loc_14006750C
0x1400668f7  xor     edi, edi
0x1400668f9  mov     [rsp+158h+var_E4], edi
0x1400668fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140066904  cmp     rcx, r12
0x140066907  jz      short loc_140066939
0x140066909  test    dword ptr [rcx+2Ch], 200h
0x140066910  jz      short loc_140066939
0x140066912  cmp     byte ptr [rcx+29h], 2
0x140066916  jb      short loc_140066939
0x140066918  mov     edx, 20h ; ' '
0x14006691d  mov     [rsp+158h+LazyWriteContext], rbx
0x140066922  mov     r9, r15
0x140066925  lea     r8, WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids
0x14006692c  mov     rcx, [rcx+18h]
0x140066930  call    WPP_SF_qq
0x140066935  lea     rdx, [rbx+18h]; FileSizes
  ... truncated ...
```
