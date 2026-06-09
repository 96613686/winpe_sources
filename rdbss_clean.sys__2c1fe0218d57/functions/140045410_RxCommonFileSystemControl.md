# RxCommonFileSystemControl

- ea: `0x140045410`
- end: `0x1400465bf`
- name: `RxCommonFileSystemControl`
- size: `4527`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp)`
- caller_count: `0`
- callee_count: `38`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x140007ca0`
- `0x140008030`
- `0x140008190`
- `0x140009b80`
- `0x140009ea0`
- `0x14000d610`
- `0x14000f130`
- `0x140012030`
- `0x1400146a0`
- `0x140016e20`
- `0x140016fc0`
- `0x140017280`
- `0x140017968`
- `0x140019aac`
- `0x14001a14c`
- `0x14001a834`
- `0x14001aa54`
- `0x14001abb8`
- `0x14001b0f0`
- `0x140024828`
- `0x140025c20`
- `0x140025d00`
- `0x140025d80`
- `0x140026080`
- `0x140045410`
- `0x1400465c8`
- `0x1400466c0`
- `0x14004698c`
- `0x140046c48`
- `0x1400470d4`
- `0x140047438`
- `0x140047558`
- `0x14004aeb4`
- `0x14004b370`
- `0x140057660`
- `0x140069970`
- `0x140071990`
- `0x1400737a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140045af6`
- `ntoskrnl!ExAllocatePool2` at `0x140045af6`
- `ntoskrnl!MmForceSectionClosed` at `0x140046320`
- `ntoskrnl!MmForceSectionClosed` at `0x140046320`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14004643e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14004643e`
- `ntoskrnl!ProbeForRead` at `0x1400455fc`
- `ntoskrnl!ProbeForRead` at `0x140045654`
- `ntoskrnl!ProbeForRead` at `0x1400455fc`
- `ntoskrnl!ProbeForRead` at `0x140045654`
- `ntoskrnl!ProbeForWrite` at `0x140045615`
- `ntoskrnl!ProbeForWrite` at `0x14004566d`
- `ntoskrnl!ProbeForWrite` at `0x140045615`
- `ntoskrnl!ProbeForWrite` at `0x14004566d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140045ab5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140045b94`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140045ba8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140045ab5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140045b94`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140045ba8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045b21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045b21`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004647e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004647e`
- `ntoskrnl!SeTokenIsAdmin` at `0x14004645d`
- `ntoskrnl!SeTokenIsAdmin` at `0x14004645d`
- `ntoskrnl!FsRtlGetNextFileLock` at `0x140046177`
- `ntoskrnl!FsRtlGetNextFileLock` at `0x140046177`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004630d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004630d`

## pseudocode

```c
__int64 __fastcall RxCommonFileSystemControl(PRX_CONTEXT RxContext, PIRP Irp)
{
  PIRP v2; // rbx
  unsigned int LowPart; // edi
  int v5; // esi
  struct _IO_STACK_LOCATION *v6; // r9
  NTSTATUS v8; // esi
  KPROCESSOR_MODE *p_RequestorMode; // r14
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rax
  volatile void *UserBuffer; // rcx
  SIZE_T Options; // rdx
  ULONG v13; // r8d
  ULONG v14; // ebx
  ULONG v15; // ebx
  CHAR *v16; // r9
  struct _IO_STACK_LOCATION *v17; // rcx
  UCHAR v18; // al
  PFCB v19; // r14
  bool v20; // di
  IRP *v21; // rbx
  NTSTATUS v22; // eax
  unsigned int v23; // edi
  unsigned int v24; // edi
  unsigned int v25; // edi
  unsigned int v26; // edi
  unsigned int v27; // edi
  unsigned int v28; // edi
  unsigned int v29; // edi
  unsigned int v30; // edi
  int v31; // eax
  unsigned int v32; // edi
  unsigned int v33; // edi
  unsigned int v34; // edi
  unsigned int v35; // edi
  NTSTATUS DirectAccessOriginalBase; // eax
  unsigned int v37; // edi
  unsigned int v38; // edi
  unsigned int v39; // edi
  unsigned int v40; // edi
  struct _IRP *MasterIrp; // rdi
  unsigned int v42; // r8d
  unsigned int v43; // ecx
  unsigned int v44; // edx
  const WCHAR *v45; // r12
  unsigned __int16 v46; // dx
  unsigned int v47; // r8d
  struct _IRP *Pool2; // r12
  unsigned __int64 v49; // rbx
  NTSTATUS v50; // eax
  __int64 v51; // rdi
  ULONG v52; // r8d
  __int128 v53; // xmm0
  _DWORD *ClientToken; // rcx
  struct _IRP *v55; // r12
  unsigned int v56; // eax
  __int64 v57; // rdi
  ULONG v58; // r8d
  unsigned int v59; // edi
  unsigned int v60; // edi
  unsigned int v61; // edi
  unsigned int v62; // edi
  struct _FCB *v63; // rbx
  __int16 v64; // di
  ULONG v65; // r8d
  const CHAR *v66; // r9
  int v67; // edi
  PSECTION_OBJECT_POINTERS *v68; // r14
  __int64 v69; // r8
  PFOBX v70; // r9
  ULONG v71; // r8d
  PCSTR v72; // r9
  struct _IRP *v73; // rsi
  PFCB v74; // rdi
  int NetRootCachingMode; // eax
  PACCESS_TOKEN PrimaryToken; // rcx
  BOOLEAN IsAdmin; // bl
  ULONG v78; // r8d
  struct _IRP *v79; // r9
  char v80; // cl
  unsigned int v81; // edi
  unsigned int v82; // edi
  unsigned int v83; // edi
  const CHAR *Timeout; // [rsp+20h] [rbp-138h]
  ULONG Timeouta; // [rsp+20h] [rbp-138h]
  ULONG Timeoutb; // [rsp+20h] [rbp-138h]
  ULONG Timeoutc; // [rsp+20h] [rbp-138h]
  ULONG Timeoute; // [rsp+20h] [rbp-138h]
  ULONG Timeoutd; // [rsp+20h] [rbp-138h]
  ULONG MinorFunction; // [rsp+28h] [rbp-130h]
  ULONG Length; // [rsp+40h] [rbp-118h]
  char Lengtha; // [rsp+40h] [rbp-118h]
  PFCB Fcb; // [rsp+48h] [rbp-110h] BYREF
  PIRP Irpa; // [rsp+50h] [rbp-108h]
  int v95; // [rsp+58h] [rbp-100h]
  ULONG v96; // [rsp+5Ch] [rbp-FCh]
  __int64 v97; // [rsp+60h] [rbp-F8h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+68h] [rbp-F0h]
  ULONG v99; // [rsp+70h] [rbp-E8h]
  struct _SECURITY_SUBJECT_CONTEXT UnicodeString; // [rsp+78h] [rbp-E0h] BYREF
  unsigned int v101; // [rsp+98h] [rbp-C0h]
  _DWORD *p_Type; // [rsp+A0h] [rbp-B8h]
  void *Src[2]; // [rsp+A8h] [rbp-B0h] BYREF
  volatile void *v104; // [rsp+B8h] [rbp-A0h]
  KPROCESSOR_MODE *v105; // [rsp+C0h] [rbp-98h]
  volatile void *Address; // [rsp+C8h] [rbp-90h]
  PRX_CONTEXT v107; // [rsp+D0h] [rbp-88h]
  PIRP v108; // [rsp+D8h] [rbp-80h]
  _OWORD v109[4]; // [rsp+E0h] [rbp-78h] BYREF

  v2 = Irp;
  Irpa = Irp;
  v107 = RxContext;
  v108 = Irp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Src[0] = CurrentStackLocation;
  p_Type = &CurrentStackLocation->FileObject->Type;
  UnicodeString.ClientToken = p_Type;
  Fcb = 0;
  v97 = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v101 = LowPart;
  v99 = p_Type[20];
  v96 = v99;
  v5 = (unsigned __int16)RxDecodeFileObject2(p_Type, &Fcb, &v97);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    MinorFunction = v6->MinorFunction;
    Timeout = (const CHAR *)v2;
    WPP_SF_qqDll(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, &WPP_GLOBAL_Control, RxContext);
    v6 = CurrentStackLocation;
  }
  if ( (unsigned __int16)(v5 + 5088) <= 2u )
  {
    v8 = 0;
    p_RequestorMode = &v2->RequestorMode;
    v105 = &v2->RequestorMode;
    if ( v2->RequestorMode == 1 && ((__int64)RxContext->RdbssDbgExtension & 0x200) == 0 )
    {
      if ( (LowPart & 3) == 0 || (LowPart & 3) == 1 || (LowPart & 3) == 2 )
      {
        v8 = 0;
        v95 = 0;
      }
      else if ( (LowPart & 3) == 3 )
      {
        v95 = 0;
        Parameters = v6->Parameters.CreatePipe.Parameters;
        Address = Parameters;
        UserBuffer = v2->UserBuffer;
        v104 = UserBuffer;
        Options = v6->Parameters.Create.Options;
        v13 = v6->Parameters.Read.Length;
        Length = v13;
        if ( Parameters )
        {
          v14 = v6->Parameters.Create.Options;
          ProbeForRead(Parameters, Options, 1u);
          ProbeForWrite(Address, v14, 1u);
          UserBuffer = v104;
          v13 = Length;
        }
        else
        {
          if ( (_DWORD)Options )
            v8 = -1073741592;
          v95 = v8;
        }
        if ( !v8 )
        {
          if ( UserBuffer )
          {
            v15 = v13;
            ProbeForRead(UserBuffer, v13, 1u);
            ProbeForWrite(v104, v15, 1u);
          }
          else if ( v13 )
          {
            v8 = -1073741592;
            v95 = -1073741592;
          }
        }
      }
      v2 = Irpa;
      if ( v8 )
        return (unsigned int)v8;
    }
    Lengtha = 1;
    RxInitializeLowIoContext(RxContext, 6u, (PLOWIO_CONTEXT)((char *)&RxContext->9 + 120));
    v17 = CurrentStackLocation;
    v18 = CurrentStackLocation->MinorFunction;
    if ( v18 && v18 != 4 )
      goto LABEL_31;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 51, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids, LowPart);
      v17 = CurrentStackLocation;
    }
    if ( LowPart <= 0x903A4 )
    {
      if ( LowPart == 590756 )
      {
        if ( Fcb->Header.NodeTypeCode == -5086 && !*p_RequestorMode )
        {
          DirectAccessOriginalBase = RxQueryDirectAccessOriginalBase(v2);
          goto LABEL_80;
        }
        goto LABEL_89;
      }
      if ( LowPart <= 0x90020 )
      {
        if ( LowPart == 589856 )
          goto LABEL_69;
        if ( LowPart <= 0x90008 )
        {
          if ( LowPart != 589832 )
          {
            v23 = LowPart - 393620;
            if ( !v23 || (v24 = v23 - 4) == 0 || (v25 = v24 - 24) == 0 )
            {
              v19 = Fcb;
              if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)&Fcb->1 + 15) + 32LL) + 96LL) & 0x10) == 0 )
                v8 = -1073741203;
              v20 = (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)&Fcb->1 + 15) + 32LL) + 96LL) & 0x10) != 0;
              goto LABEL_33;
            }
            v26 = v25 - 196176;
            if ( v26 )
            {
              if ( v26 != 4 )
                goto LABEL_31;
            }
          }
LABEL_51:
          v8 = -1073741822;
          goto LABEL_52;
        }
        v27 = LowPart - 589836;
        if ( !v27 )
          goto LABEL_51;
        v28 = v27 - 4;
        if ( !v28 )
          goto LABEL_51;
        v29 = v28 - 4;
        if ( !v29 )
          goto LABEL_51;
        v30 = v29 - 4;
        if ( !v30 || v30 == 4 )
        {
LABEL_69:
          Lengtha = 0;
          v31 = -1073741811;
          v19 = Fcb;
          if ( Fcb->Header.NodeTypeCode == -5345 )
            v31 = -1073741822;
          v8 = v31;
          goto LABEL_32;
        }
        goto LABEL_31;
      }
      if ( LowPart <= 0x900C4 )
      {
        if ( LowPart != 590020 )
        {
          v32 = LowPart - 589864;
          if ( !v32 )
            goto LABEL_69;
          v33 = v32 - 8;
          if ( !v33 )
            goto LABEL_69;
          v34 = v33 - 32;
          if ( !v34 )
            goto LABEL_51;
          v35 = v34 - 12;
          if ( !v35 )
            goto LABEL_51;
          if ( v35 != 72 )
          {
LABEL_31:
            v19 = Fcb;
LABEL_32:
            v20 = Lengtha;
LABEL_33:
            v21 = Irpa;
            goto LABEL_34;
          }
          DirectAccessOriginalBase = RxSetReparsePointInformation(RxContext, v2, Fcb);
LABEL_80:
          v8 = DirectAccessOriginalBase;
          goto LABEL_52;
        }
LABEL_182:
        v19 = Fcb;
        v8 = _RxAcquireFcb(Fcb, RxContext, 1u, 0, Timeout, MinorFunction);
        if ( v8 == -1073741739 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
          }
          BYTE3(RxContext->RealDevice) = 1;
        }
        if ( v8 )
          goto LABEL_52;
        *((_DWORD *)&v19->1 + 40) &= 0xFFBFF7FF;
        if ( LowPart == 590020 )
        {
          if ( v19->Header.NodeTypeCode == -5086 )
          {
            *(_DWORD *)&v19->FcbTableEntry.Path.Length |= 0x200u;
            RxDisableLocalBuffering(v19);
          }
          else
          {
            v8 = -1073741637;
          }
        }
LABEL_193:
        _RxReleaseFcb(RxContext, (PMRX_FCB)&v19->Header, v58, v16, Timeoutb);
        goto LABEL_32;
      }
      v37 = LowPart - 590080;
      if ( v37 )
      {
        v38 = v37 - 320;
        if ( !v38 )
        {
          if ( *p_RequestorMode == 1 )
            goto LABEL_51;
          DirectAccessOriginalBase = RxOplockRequest(RxContext, v2);
          goto LABEL_80;
        }
        v39 = v38 - 48;
        if ( !v39 )
        {
          DirectAccessOriginalBase = RxSetPurgeFailureMode(RxContext);
          goto LABEL_80;
        }
        v40 = v39 - 72;
        if ( v40 )
        {
          if ( v40 != 227 )
            goto LABEL_31;
          if ( Fcb->Header.NodeTypeCode == -5086 && !*p_RequestorMode )
          {
            DirectAccessOriginalBase = RxQueryDirectAccessExtents((ULONG_PTR)v2, (ULONG_PTR)Fcb);
            goto LABEL_80;
          }
LABEL_89:
          v8 = -1073741637;
          goto LABEL_52;
        }
LABEL_220:
        v63 = Fcb;
        if ( Fcb->Header.NodeTypeCode == -5086 )
        {
          v8 = _RxAcquireFcb(Fcb, RxContext, 1u, 0, Timeout, MinorFunction);
          if ( v8 == -1073741739 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
            }
            BYTE3(RxContext->RealDevice) = 1;
          }
          if ( !v8 )
          {
            v64 = v99;
            memset(&UnicodeString, 0, sizeof(UnicodeString));
            RxDisableLocalBuffering(v63);
            v67 = v64 & 0x4000;
            v68 = (PSECTION_OBJECT_POINTERS *)p_Type;
            if ( !v67 )
              RxUninitializeCacheMap(RxContext, p_Type, 0, &UnicodeString);
            _RxReleaseFcb(RxContext, (PMRX_FCB)&v63->Header, v65, v66, Timeoutc);
            RxReleaseLViewRundown(RxContext);
            if ( !v67 )
            {
              KeWaitForSingleObject(&UnicodeString.ImpersonationLevel, Executive, 0, 0, 0);
              MmForceSectionClosed(v68[5], 1u);
            }
          }
          goto LABEL_52;
        }
        goto LABEL_89;
      }
      MasterIrp = v2->AssociatedIrp.MasterIrp;
      *(_OWORD *)&UnicodeString.ClientToken = 0;
      *(_OWORD *)Src = 0;
      if ( MasterIrp )
      {
        v42 = v17->Parameters.Create.Options;
        if ( v42 >= 0x10 )
        {
          v43 = *(_DWORD *)&MasterIrp->Type;
          if ( *(_DWORD *)&MasterIrp->Type <= v42 )
          {
            v44 = *(_DWORD *)(&MasterIrp->Size + 1);
            if ( v44 <= v42 && v43 <= 0xFFFF && v44 <= 0xFFFF && v43 >= 4 && v44 >= 4 && v44 + v43 + 12 <= v42 )
            {
              v45 = (const WCHAR *)&MasterIrp->MdlAddress + ((unsigned __int64)v43 >> 1) + 2;
              if ( !*(v45 - 1) && !v45[((unsigned __int64)v44 >> 1) - 1] )
              {
                v19 = Fcb;
                v8 = TranslateSisFsctlName((PCWSTR)&MasterIrp->MdlAddress + 2, (PUNICODE_STRING)&UnicodeString);
                if ( v8 < 0 )
                  goto LABEL_52;
                v8 = TranslateSisFsctlName(v45, (PUNICODE_STRING)Src);
                if ( v8 < 0 )
                {
                  RtlFreeUnicodeString((PUNICODE_STRING)&UnicodeString);
                  goto LABEL_52;
                }
                v46 = WORD1(UnicodeString.ClientToken);
                v47 = WORD1(UnicodeString.ClientToken) + WORD1(Src[0]);
                if ( v47 <= *(_DWORD *)&MasterIrp->Type + *(_DWORD *)(&MasterIrp->Size + 1) )
                {
                  Pool2 = MasterIrp;
                }
                else
                {
                  v96 = v47 + 12;
                  Pool2 = (struct _IRP *)ExAllocatePool2(66, v47 + 12, 1934456914);
                  if ( !Pool2 )
                  {
                    v8 = -1073741670;
                    goto LABEL_52;
                  }
                  LODWORD(Pool2->MdlAddress) = MasterIrp->MdlAddress;
                  ExFreePoolWithTag(MasterIrp, 0);
                  v2->AssociatedIrp.MasterIrp = Pool2;
                  CurrentStackLocation->Parameters.Create.Options = v96;
                  v46 = WORD1(UnicodeString.ClientToken);
                }
                *(_DWORD *)&Pool2->Type = v46;
                *(_DWORD *)(&Pool2->Size + 1) = WORD1(Src[0]);
                v49 = v46;
                memmove((char *)&Pool2->MdlAddress + 4, *(const void **)&UnicodeString.ImpersonationLevel, v46);
                memmove((char *)&Pool2->MdlAddress + 2 * (v49 >> 1) + 4, Src[1], *(unsigned int *)(&Pool2->Size + 1));
                RtlFreeUnicodeString((PUNICODE_STRING)&UnicodeString);
                RtlFreeUnicodeString((PUNICODE_STRING)Src);
                goto LABEL_32;
              }
            }
          }
        }
      }
LABEL_113:
      v8 = -1073741811;
      goto LABEL_52;
    }
    if ( LowPart <= 0x1401D4 )
    {
      if ( LowPart == 1311188 )
      {
        v19 = Fcb;
        if ( Fcb->Header.NodeTypeCode == -5086 && !*(_BYTE *)(*((_QWORD *)&Fcb->1 + 15) + 77LL) )
        {
          v8 = _RxAcquireFcb(Fcb, RxContext, 1u, 0, Timeout, MinorFunction);
          if ( v8 == -1073741739 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
            }
            Lengtha = 0;
            BYTE3(RxContext->RealDevice) = 1;
          }
          if ( v8 < 0 )
            goto LABEL_32;
          if ( v19->ulFileSizeVersion + *(&v19->ulFileSizeVersion + 1) + LODWORD(v19->FileLock.CompleteLockIrpRoutine)
            || !(v19->LastWriteTime.HighPart + v19->LastChangeTime.LowPart + v19->LastChangeTime.HighPart) )
          {
            if ( !FsRtlGetNextFileLock((PFILE_LOCK)&v19->FileLock.LockRequestsInProgress, 1u)
              || LOBYTE(v19->PagingIoResourceFile) == 1 )
            {
              RxDisableLocalBuffering(v19);
              LOBYTE(v19->PagingIoResourceFile) = 1;
            }
            else
            {
              v8 = -1073741808;
              Lengtha = 0;
            }
          }
          if ( v8 >= 0 )
            *(_DWORD *)(*(_QWORD *)(v97 + 32) + 72LL) |= 0x80u;
          goto LABEL_193;
        }
        v8 = -1073741637;
      }
      else
      {
        if ( LowPart <= 0x983E8 )
        {
          if ( LowPart == 623592 )
          {
            DirectAccessOriginalBase = RxDuplicateExtentsEx(RxContext, v2, (PMRX_FCB)&Fcb->Header);
            goto LABEL_80;
          }
          if ( LowPart == 590912 )
          {
            v19 = Fcb;
            v50 = RxRefsStreamSnapshotManagement(RxContext, v2, (PMRX_FCB)&Fcb->Header);
          }
          else if ( LowPart == 606820 )
          {
            v19 = Fcb;
            v50 = RxOffloadRead(RxContext, v2, (PMRX_FCB)&Fcb->Header);
          }
          else
          {
            if ( LowPart != 622792 )
            {
              if ( LowPart == 623208 )
              {
                DirectAccessOriginalBase = RxProcessOffloadWrite(RxContext, v2, (PMRX_FCB)&Fcb->Header);
              }
              else
              {
                if ( LowPart != 623428 )
                  goto LABEL_31;
                DirectAccessOriginalBase = RxDuplicateExtents(RxContext, v2, (PMRX_FCB)&Fcb->Header);
              }
              goto LABEL_80;
            }
            v19 = Fcb;
            v50 = RxSetZeroData(RxContext, v2, (PMRX_FCB)&Fcb->Header);
          }
          v8 = v50;
          v20 = v50 == 0;
          goto LABEL_33;
        }
        switch ( LowPart )
        {
          case 0x9C040u:
            goto LABEL_182;
          case 0x110004u:
            goto LABEL_113;
          case 0x110044u:
            Lengtha = 0;
            v19 = Fcb;
            if ( *(_BYTE *)(*((_QWORD *)&Fcb->1 + 15) + 77LL) == 1 && *(_BYTE *)(v97 + 164) )
            {
              v8 = 0;
              RxContext->InformationToReturn = 0;
              v2->IoStatus.Information = 0;
            }
            else
            {
              v8 = -1073741808;
            }
            goto LABEL_32;
        }
        if ( LowPart != 1130508 )
        {
          if ( LowPart != 1310952 )
            goto LABEL_31;
          Lengtha = 0;
          if ( v17->Parameters.Read.Length >= 0x14 && (UnicodeString.ClientToken = v2->AssociatedIrp.MasterIrp) != 0 )
          {
            v19 = Fcb;
            v51 = *((_QWORD *)&Fcb->1 + 15);
            if ( !*(_BYTE *)(v51 + 77) )
            {
              memset(v109, 0, sizeof(v109));
              RxContext->LowIoContext.ParamsFor.Locks.Flags = 8;
              RxContext->LowIoContext.ParamsFor.ReadWrite.ByteOffset = (RXVBO)v109;
              *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = 64;
              v8 = _RxAcquireFcb(v19, RxContext, 2u, 0, Timeout, MinorFunction);
              if ( v8 == -1073741739 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
                }
                BYTE3(RxContext->RealDevice) = 1;
              }
              if ( !v8 )
              {
                if ( *(_QWORD *)(RxContext->pFcb[2].Header.ValidDataLength.QuadPart + 272) )
                {
                  if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) != 0 )
                  {
                    v8 = -1073741536;
                  }
                  else
                  {
                    *(_OWORD *)&RxContext->MRxContext[2] = 0;
                    *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
                    RxContext->ResumeRoutine = 0;
                    v8 = (*(__int64 (__fastcall **)(PRX_CONTEXT))(RxContext->pFcb[2].Header.ValidDataLength.QuadPart
                                                                + 272))(RxContext);
                  }
                }
                else
                {
                  v8 = -1073741822;
                }
                _RxReleaseFcb(RxContext, (PMRX_FCB)&v19->Header, v52, v16, Timeouta);
                if ( !v8 || v8 == -2147483643 )
                {
                  v53 = v109[0];
                  *(_OWORD *)(v51 + 124) = v109[0];
                  ClientToken = UnicodeString.ClientToken;
                  *(_OWORD *)((char *)UnicodeString.ClientToken + 4) = v53;
                  *ClientToken = (*(_DWORD *)(v51 + 56) >> 1) & 1;
                  v2->IoStatus.Information = 20;
                  v8 = 0;
                }
              }
              goto LABEL_158;
            }
          }
          else
          {
            v19 = Fcb;
          }
          v8 = -1073741811;
LABEL_158:
          v2->IoStatus.Status = v8;
          goto LABEL_32;
        }
        v19 = Fcb;
        if ( *(_BYTE *)(*((_QWORD *)&Fcb->1 + 15) + 77LL) == 1 )
        {
          v55 = v2->AssociatedIrp.MasterIrp;
          if ( v55 )
          {
            v56 = v17->Parameters.Read.Length;
            if ( v56 >= 0x10 )
            {
              memset(v2->AssociatedIrp.MasterIrp, 0, v56);
              v57 = v97;
              if ( RxShouldRequestBeThrottled((PTHROTTLING_STATE)(v97 + 184)) )
              {
                v20 = 0;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
                }
                v2->IoStatus.Information = 16;
                *(_QWORD *)&v55->Type = 3;
                LODWORD(v55->MdlAddress) = -1;
                HIDWORD(v55->MdlAddress) = 0;
                v8 = 0;
                goto LABEL_33;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  58,
                  &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
                  *(unsigned int *)(v57 + 208));
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qqqL(
                  WPP_GLOBAL_Control->AttachedDevice,
                  59,
                  &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
                  RxContext,
                  v57,
                  v57 + 184,
                  *(_DWORD *)(v57 + 208));
              }
              goto LABEL_32;
            }
          }
        }
        v8 = -1073741811;
      }
LABEL_177:
      v20 = 0;
      goto LABEL_33;
    }
    if ( LowPart <= 0x14424C )
    {
      if ( LowPart != 1327692 )
      {
        v59 = LowPart - 1311212;
        if ( !v59 )
        {
          Lengtha = 1;
          v19 = Fcb;
          if ( (unsigned __int16)(Fcb->Header.NodeTypeCode + 5087) <= 1u )
          {
            if ( !*v105 )
              goto LABEL_247;
            memset(&UnicodeString, 0, sizeof(UnicodeString));
            SeCaptureSubjectContext(&UnicodeString);
            PrimaryToken = UnicodeString.PrimaryToken;
            if ( UnicodeString.ClientToken )
              PrimaryToken = UnicodeString.ClientToken;
            IsAdmin = SeTokenIsAdmin(PrimaryToken);
            v8 = IsAdmin == 0 ? 0xC0000022 : 0;
            SeReleaseSubjectContext(&UnicodeString);
            if ( IsAdmin )
            {
LABEL_247:
              v8 = _RxAcquireFcb(v19, RxContext, 2u, 0, Timeout, MinorFunction);
              if ( v8 == -1073741739 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 55, &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids);
                }
                v20 = 0;
                Lengtha = 0;
                BYTE3(RxContext->RealDevice) = 1;
              }
              else
              {
                v20 = 1;
              }
              v21 = Irpa;
              if ( !v8 )
              {
                v79 = Irpa->AssociatedIrp.MasterIrp;
                if ( v79 )
                {
                  v78 = (unsigned int)CurrentStackLocation;
                  if ( CurrentStackLocation->Parameters.Create.Options == 4 )
                  {
                    v8 = RxPopulateDebugInfoForFile(
                           (_DWORD)RxContext,
                           *(_DWORD *)&v79->Type,
                           CurrentStackLocation->Parameters.Read.Length,
                           (_DWORD)v79,
                           (__int64)&Irpa->IoStatus.Information);
                    v80 = Lengtha;
                    if ( v8 != -1073741811 )
                      v80 = 0;
                    v20 = v80;
                  }
                }
                _RxReleaseFcb(RxContext, (PMRX_FCB)&v19->Header, v78, (PCSTR)v79, Timeoutd);
              }
LABEL_34:
              if ( v20 )
              {
                v22 = RxLowIoFsCtlShell(RxContext, v21, v19, (PFOBX)v16);
                goto LABEL_55;
              }
LABEL_52:
              if ( v8 == 259 || !BYTE3(RxContext->RealDevice) )
              {
LABEL_56:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    60,
                    &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
                    (unsigned int)v8);
                }
                return (unsigned int)v8;
              }
              v22 = RxFsdPostRequest(RxContext);
LABEL_55:
              v8 = v22;
              goto LABEL_56;
            }
          }
          goto LABEL_32;
        }
        v60 = v59 - 8;
        if ( !v60 )
        {
          v73 = v2->AssociatedIrp.MasterIrp;
          v2->IoStatus.Information = 0;
          if ( !v73 )
          {
            v8 = -1073741592;
            goto LABEL_52;
          }
          if ( v17->Parameters.Read.Length < 4 )
          {
            v8 = -1073741789;
            goto LABEL_52;
          }
          v74 = Fcb;
          if ( Fcb != &RxDeviceFCB )
          {
            NetRootCachingMode = RxQueryNetRootCachingMode(*((_QWORD *)&Fcb->1 + 15));
            if ( NetRootCachingMode == -1
              || (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v74->1 + 15) + 32LL) + 96LL) & 0x80u) != 0 )
            {
              NetRootCachingMode = 12;
            }
            *(_DWORD *)&v73->Type = 4 * NetRootCachingMode;
            v2->IoStatus.Information = 4;
            v8 = 0;
            goto LABEL_52;
          }
          goto LABEL_113;
        }
        v61 = v60 - 12;
        if ( !v61 )
        {
          LODWORD(RxContext->RdbssDbgExtension) |= 2u;
          v19 = Fcb;
          _RxAcquireFcb(Fcb, RxContext, 1u, 0, Timeout, MinorFunction);
          LOBYTE(v69) = 1;
          RxAcquirePagingIoResource(RxContext, v19, v69);
          v8 = RxLowIoFsCtlShell(RxContext, v2, v19, v70);
          RxReleasePagingIoResource(RxContext, v19);
          _RxReleaseFcb(RxContext, (PMRX_FCB)&v19->Header, v71, v72, Timeoute);
          v20 = 0;
          BYTE3(RxContext->RealDevice) = 0;
          goto LABEL_33;
        }
        v62 = v61 - 400;
        if ( !v62 )
          goto LABEL_220;
        if ( v62 != 15714 )
          goto LABEL_31;
LABEL_219:
        Lengtha = 0;
        v8 = RxProcessCopyChunkIoctlOrFsCtl(RxContext, v2);
        goto LABEL_31;
      }
LABEL_269:
      v19 = Fcb;
      v8 = RxProcessBatchedRead(RxContext, v2, Fcb);
      goto LABEL_177;
    }
    v81 = LowPart - 1327699;
    if ( v81 )
    {
      v82 = v81 - 16031;
      if ( !v82 )
        goto LABEL_219;
      v83 = v82 - 338;
      if ( !v83 )
        goto LABEL_267;
      if ( v83 != 7 )
        goto LABEL_31;
      if ( !*p_RequestorMode )
      {
LABEL_267:
        DirectAccessOriginalBase = RxProcessBatchedWrite(RxContext, v2, (PMRX_FCB)&Fcb->Header);
        goto LABEL_80;
      }
    }
    else if ( !*p_RequestorMode )
    {
      goto LABEL_269;
    }
    v8 = -1073741790;
    goto LABEL_52;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_qqqL(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        &WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
        RxContext,
        v97,
        Fcb,
        v5);
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140045410  mov     [rsp+arg_10], rbx
0x140045415  mov     [rsp+arg_18], rsi
0x14004541a  push    rdi
0x14004541b  push    r12
0x14004541d  push    r13
0x14004541f  push    r14
0x140045421  push    r15
0x140045423  sub     rsp, 130h
0x14004542a  mov     rax, cs:__security_cookie
0x140045431  xor     rax, rsp
0x140045434  mov     [rsp+158h+var_38], rax
0x14004543c  mov     rbx, rdx
0x14004543f  mov     [rsp+158h+Irp], rdx
0x140045444  mov     r13, rcx
0x140045447  mov     [rsp+158h+var_88], rcx
0x14004544f  mov     [rsp+158h+var_80], rdx
0x140045457  mov     r9, [rdx+0B8h]
0x14004545e  mov     [rsp+158h+var_F0], r9
0x140045463  mov     [rsp+158h+Src], r9
0x14004546b  mov     rcx, [r9+30h]
0x14004546f  mov     [rsp+158h+var_B8], rcx
0x140045477  mov     qword ptr [rsp+158h+UnicodeString.Length], rcx
0x14004547c  xor     r15d, r15d
0x14004547f  mov     [rsp+158h+Fcb], r15
0x140045484  mov     [rsp+158h+var_F8], r15
0x140045489  mov     edi, [r9+18h]
0x14004548d  mov     [rsp+158h+var_C0], edi
0x140045494  mov     eax, [rcx+50h]
0x140045497  mov     [rsp+158h+var_E8], eax
0x14004549b  mov     [rsp+158h+var_FC], eax
0x14004549f  lea     r8, [rsp+158h+var_F8]
0x1400454a4  lea     rdx, [rsp+158h+Fcb]
0x1400454a9  call    RxDecodeFileObject2
0x1400454ae  movzx   esi, ax
0x1400454b1  lea     r8, WPP_GLOBAL_Control
0x1400454b8  mov     rdx, cs:WPP_GLOBAL_Control
0x1400454bf  cmp     rdx, r8
0x1400454c2  jz      short loc_140045508
0x1400454c4  mov     ecx, [rdx+2Ch]
0x1400454c7  test    cl, 4
0x1400454ca  lea     ecx, [r15+2]
0x1400454ce  jz      short loc_14004550D
0x1400454d0  cmp     [rdx+29h], cl
0x1400454d3  jb      short loc_14004550D
0x1400454d5  mov     ecx, edi
0x1400454d7  and     ecx, 3
0x1400454da  movzx   eax, byte ptr [r9+1]
0x1400454df  mov     [rsp+158h+var_120], ecx
0x1400454e3  mov     [rsp+158h+var_128], edi
0x1400454e7  mov     dword ptr [rsp+158h+var_130], eax
0x1400454eb  mov     [rsp+158h+Timeout], rbx
0x1400454f0  mov     r9, r13
0x1400454f3  mov     rcx, [rdx+18h]
0x1400454f7  call    WPP_SF_qqDll
0x1400454fc  mov     r9, [rsp+158h+var_F0]
0x140045501  lea     r8, WPP_GLOBAL_Control
0x140045508  mov     ecx, 2
0x14004550d  mov     eax, 13E0h
0x140045512  add     eax, esi
0x140045514  cmp     ax, cx
0x140045517  jbe     short loc_140045573
0x140045519  mov     rcx, cs:WPP_GLOBAL_Control
0x140045520  cmp     rcx, r8
0x140045523  jz      short loc_140045569
0x140045525  mov     eax, [rcx+2Ch]
0x140045528  mov     r12d, 1
0x14004552e  test    r12b, al
0x140045531  jz      short loc_140045569
0x140045533  cmp     [rcx+29h], r12b
0x140045537  jb      short loc_140045569
0x140045539  lea     edx, [r12+31h]
0x14004553e  mov     [rsp+158h+var_128], esi
0x140045542  mov     rax, [rsp+158h+Fcb]
0x140045547  mov     [rsp+158h+var_130], rax
0x14004554c  mov     rax, [rsp+158h+var_F8]
0x140045551  mov     [rsp+158h+Timeout], rax
0x140045556  mov     r9, r13
0x140045559  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x140045560  mov     rcx, [rcx+18h]
0x140045564  call    WPP_SF_qqqL
0x140045569  mov     eax, 0C000000Dh
0x14004556e  jmp     loc_140045842
0x140045573  mov     esi, r15d
0x140045576  lea     r14, [rbx+40h]
0x14004557a  mov     [rsp+158h+var_98], r14
0x140045582  mov     r12d, 1
0x140045588  cmp     [r14], r12b
0x14004558b  jnz     loc_1400456F5
0x140045591  test    dword ptr [r13+78h], 200h
0x140045599  jnz     loc_1400456F5
0x14004559f  mov     eax, edi
0x1400455a1  and     eax, 3
0x1400455a4  jz      loc_140045688
0x1400455aa  sub     eax, r12d
0x1400455ad  jz      loc_140045688
0x1400455b3  sub     eax, r12d
0x1400455b6  jz      loc_140045688
0x1400455bc  cmp     eax, r12d
0x1400455bf  jnz     loc_140045690
0x1400455c5  mov     [rsp+158h+var_100], r15d
0x1400455ca  mov     rax, [r9+20h]
0x1400455ce  mov     [rsp+158h+Address], rax
0x1400455d6  mov     rcx, [rbx+70h]; Address
0x1400455da  mov     [rsp+158h+var_A0], rcx
0x1400455e2  mov     edx, [r9+10h]; Length
0x1400455e6  mov     r8d, [r9+8]
0x1400455ea  mov     dword ptr [rsp+158h+Length], r8d
0x1400455ef  test    rax, rax
0x1400455f2  jz      short loc_140045635
0x1400455f4  mov     ebx, edx
0x1400455f6  mov     r8d, r12d; Alignment
0x1400455f9  mov     rcx, rax; Address
0x1400455fc  call    cs:__imp_ProbeForRead
0x140045603  nop     dword ptr [rax+rax+00h]
0x140045608  mov     r8d, r12d; Alignment
0x14004560b  mov     edx, ebx; Length
0x14004560d  mov     rcx, [rsp+158h+Address]; Address
0x140045615  call    cs:__imp_ProbeForWrite
0x14004561c  nop     dword ptr [rax+rax+00h]
0x140045621  mov     eax, 0C00000E8h
0x140045626  mov     rcx, [rsp+158h+var_A0]
0x14004562e  mov     r8d, dword ptr [rsp+158h+Length]
0x140045633  jmp     short loc_140045643
0x140045635  mov     eax, 0C00000E8h
0x14004563a  test    edx, edx
0x14004563c  cmovnz  esi, eax
0x14004563f  mov     [rsp+158h+var_100], esi
0x140045643  test    esi, esi
0x140045645  jnz     short loc_140045690
0x140045647  test    rcx, rcx
0x14004564a  jz      short loc_14004567B
0x14004564c  mov     ebx, r8d
0x14004564f  mov     r8d, r12d; Alignment
0x140045652  mov     edx, ebx; Length
0x140045654  call    cs:__imp_ProbeForRead
0x14004565b  nop     dword ptr [rax+rax+00h]
0x140045660  mov     r8d, r12d; Alignment
0x140045663  mov     edx, ebx; Length
0x140045665  mov     rcx, [rsp+158h+var_A0]; Address
0x14004566d  call    cs:__imp_ProbeForWrite
0x140045674  nop     dword ptr [rax+rax+00h]
0x140045679  jmp     short loc_140045690
0x14004567b  test    r8d, r8d
0x14004567e  jz      short loc_140045690
0x140045680  mov     esi, eax
0x140045682  mov     [rsp+158h+var_100], eax
0x140045686  jmp     short loc_140045690
0x140045688  mov     esi, r15d
0x14004568b  mov     [rsp+158h+var_100], r15d
0x140045690  mov     rbx, [rsp+158h+Irp]
0x140045695  jmp     short loc_1400456ED
0x140045697  mov     esi, 0C00000E8h
0x14004569c  mov     [rsp+158h+var_100], esi
0x1400456a0  xor     r15d, r15d
0x1400456a3  lea     r12d, [r15+1]
0x1400456a7  mov     r13, [rsp+158h+var_88]
0x1400456af  mov     rbx, [rsp+158h+var_80]
0x1400456b7  mov     [rsp+158h+Irp], rbx
0x1400456bc  mov     r8, [rsp+158h+Src]
0x1400456c4  mov     [rsp+158h+var_F0], r8
0x1400456c9  mov     rax, qword ptr [rsp+158h+UnicodeString.Length]
0x1400456ce  mov     [rsp+158h+var_B8], rax
0x1400456d6  mov     edi, [rsp+158h+var_C0]
0x1400456dd  mov     eax, [rsp+158h+var_FC]
0x1400456e1  mov     [rsp+158h+var_E8], eax
0x1400456e5  mov     r14, [rsp+158h+var_98]
0x1400456ed  test    esi, esi
0x1400456ef  jnz     loc_140045840
0x1400456f5  mov     byte ptr [rsp+158h+Length], r12b
0x1400456fa  lea     r8, [r13+208h]; LowIoContext
0x140045701  mov     edx, 6; Operation
0x140045706  mov     rcx, r13; RxContext
0x140045709  call    RxInitializeLowIoContext
0x14004570e  mov     rcx, [rsp+158h+var_F0]
0x140045713  mov     al, [rcx+1]
0x140045716  test    al, al
0x140045718  jz      short loc_140045748
0x14004571a  cmp     al, 4
0x14004571c  jz      short loc_140045748
0x14004571e  mov     r14, [rsp+158h+Fcb]
0x140045723  mov     edi, dword ptr [rsp+158h+Length]
0x140045727  mov     rbx, [rsp+158h+Irp]
0x14004572c  test    dil, dil
0x14004572f  jz      loc_1400457F0
0x140045735  mov     r8, r14; Fcb
0x140045738  mov     rdx, rbx; Irp
0x14004573b  mov     rcx, r13; RxContext
0x14004573e  call    RxLowIoFsCtlShell
0x140045743  jmp     loc_140045806
0x140045748  mov     r10, cs:WPP_GLOBAL_Control
0x14004574f  lea     rax, WPP_GLOBAL_Control
0x140045756  cmp     r10, rax
0x140045759  jz      short loc_140045787
0x14004575b  mov     eax, [r10+2Ch]
0x14004575f  test    al, 2
0x140045761  jz      short loc_140045787
0x140045763  cmp     byte ptr [r10+29h], 4
0x140045768  jb      short loc_140045787
0x14004576a  mov     edx, 33h ; '3'
0x14004576f  mov     r9d, edi
0x140045772  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x140045779  mov     rcx, [r10+18h]
0x14004577d  call    WPP_SF_d
0x140045782  mov     rcx, [rsp+158h+var_F0]
0x140045787  mov     eax, 903A4h
0x14004578c  cmp     edi, eax
0x14004578e  ja      loc_140045BEC
0x140045794  jz      loc_140045BC3
0x14004579a  mov     eax, 90020h
0x14004579f  cmp     edi, eax
0x1400457a1  ja      loc_1400458E6
0x1400457a7  jz      loc_1400458C1
0x1400457ad  mov     eax, 90008h
0x1400457b2  cmp     edi, eax
0x1400457b4  ja      loc_140045895
0x1400457ba  jz      short loc_1400457EB
0x1400457bc  sub     edi, 60194h
0x1400457c2  jz      loc_140045870
0x1400457c8  sub     edi, 4
0x1400457cb  jz      loc_140045870
0x1400457d1  sub     edi, 18h
0x1400457d4  jz      loc_140045870
0x1400457da  sub     edi, 2FE50h
0x1400457e0  jz      short loc_1400457EB
0x1400457e2  cmp     edi, 4
0x1400457e5  jnz     loc_14004571E
0x1400457eb  mov     esi, 0C0000002h
0x1400457f0  cmp     esi, 103h
0x1400457f6  jz      short loc_140045808
0x1400457f8  cmp     [r13+23h], r15b
0x1400457fc  jz      short loc_140045808
0x1400457fe  mov     rcx, r13; RxContext
0x140045801  call    RxFsdPostRequest
0x140045806  mov     esi, eax
0x140045808  mov     rcx, cs:WPP_GLOBAL_Control
0x14004580f  lea     rax, WPP_GLOBAL_Control
0x140045816  cmp     rcx, rax
0x140045819  jz      short loc_140045840
0x14004581b  mov     eax, [rcx+2Ch]
0x14004581e  test    al, 2
0x140045820  jz      short loc_140045840
0x140045822  cmp     byte ptr [rcx+29h], 2
0x140045826  jb      short loc_140045840
0x140045828  mov     edx, 3Ch ; '<'
0x14004582d  mov     r9d, esi
0x140045830  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x140045837  mov     rcx, [rcx+18h]
0x14004583b  call    WPP_SF_d
0x140045840  mov     eax, esi
0x140045842  mov     rcx, [rsp+158h+var_38]
0x14004584a  xor     rcx, rsp; StackCookie
0x14004584d  call    __security_check_cookie
0x140045852  lea     r11, [rsp+158h+var_28]
0x14004585a  mov     rbx, [r11+40h]
0x14004585e  mov     rsi, [r11+48h]
0x140045862  mov     rsp, r11
0x140045865  pop     r15
0x140045867  pop     r14
0x140045869  pop     r13
0x14004586b  pop     r12
0x14004586d  pop     rdi
0x14004586e  retn
0x140045870  mov     r14, [rsp+158h+Fcb]
0x140045875  mov     rax, [r14+78h]
0x140045879  mov     rcx, [rax+20h]
0x14004587d  mov     eax, [rcx+60h]
0x140045880  bt      eax, 4
0x140045884  mov     ecx, 0C000026Dh
0x140045889  cmovnb  esi, ecx
0x14004588c  setb    dil
0x140045890  jmp     loc_140045727
0x140045895  sub     edi, 9000Ch
0x14004589b  jz      loc_1400457EB
0x1400458a1  sub     edi, 4
0x1400458a4  jz      loc_1400457EB
0x1400458aa  sub     edi, 4
0x1400458ad  jz      loc_1400457EB
0x1400458b3  sub     edi, 4
0x1400458b6  jz      short loc_1400458C1
0x1400458b8  cmp     edi, 4
0x1400458bb  jnz     loc_14004571E
0x1400458c1  mov     byte ptr [rsp+158h+Length], r15b
0x1400458c6  mov     ecx, 0EB1Fh
0x1400458cb  mov     eax, 0C000000Dh
0x1400458d0  lea     esi, [rax-0Bh]
0x1400458d3  mov     r14, [rsp+158h+Fcb]
0x1400458d8  cmp     [r14], cx
0x1400458dc  cmovz   eax, esi
0x1400458df  mov     esi, eax
0x1400458e1  jmp     loc_140045723
0x1400458e6  mov     eax, 900C4h
0x1400458eb  cmp     edi, eax
0x1400458ed  ja      short loc_140045934
0x1400458ef  jz      loc_140046017
0x1400458f5  sub     edi, 90028h
0x1400458fb  jz      short loc_1400458C1
0x1400458fd  sub     edi, 8
0x140045900  jz      short loc_1400458C1
0x140045902  sub     edi, 20h ; ' '
0x140045905  jz      loc_1400457EB
  ... truncated ...
```
