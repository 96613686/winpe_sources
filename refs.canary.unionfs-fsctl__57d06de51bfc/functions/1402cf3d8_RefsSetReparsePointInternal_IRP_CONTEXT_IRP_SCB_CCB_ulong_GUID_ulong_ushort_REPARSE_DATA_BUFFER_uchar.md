# RefsSetReparsePointInternal(_IRP_CONTEXT *,_IRP *,_SCB *,_CCB *,ulong *,_GUID *,ulong,ushort,_REPARSE_DATA_BUFFER *,uchar *)

- ea: `0x1402cf3d8`
- end: `0x1402d065b`
- name: `?RefsSetReparsePointInternal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_SCB@@PEAU_CCB@@PEAKPEAU_GUID@@KGPEAU_REPARSE_DATA_BUFFER@@PEAE@Z`
- size: `4739`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct _IRP *@<rdx>, struct _SCB *@<r8>, struct _CCB *@<r9>, unsigned int *, struct _GUID *, char, unsigned __int16, struct _REPARSE_DATA_BUFFER *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `28`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140291760`
- `0x1402ce9cc`
- `0x1402cee8c`

## callees

- `0x14000c66c`
- `0x140051400`
- `0x140051eb0`
- `0x140071660`
- `0x140081670`
- `0x14008dbd0`
- `0x14008e360`
- `0x140097090`
- `0x1400a2354`
- `0x1400aef94`
- `0x1400c8024`
- `0x1400ca788`
- `0x1400e1498`
- `0x1400facd4`
- `0x14010e2ac`
- `0x1401e9ce0`
- `0x1402853d4`
- `0x140287bac`
- `0x14028e724`
- `0x14028e95c`
- `0x1402cf3d8`
- `0x1402fec90`
- `0x1403000b0`
- `0x1403021e0`
- `0x140311d00`
- `0x14031c8e0`
- `0x140325110`
- `0x14033034c`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1402cfffe`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1402d023c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1402cfffe`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1402d023c`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1402cf96b`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1402cfa49`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1402cf96b`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1402cfa49`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1402cf472`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1402cf472`
- `ntoskrnl!RtlIsSandboxedToken` at `0x1402cf6f5`
- `ntoskrnl!RtlIsSandboxedToken` at `0x1402cf6f5`
- `ntoskrnl!CcCanIWrite` at `0x1402d0066`
- `ntoskrnl!CcCanIWrite` at `0x1402d0293`
- `ntoskrnl!CcCanIWrite` at `0x1402d0066`
- `ntoskrnl!CcCanIWrite` at `0x1402d0293`
- `ntoskrnl!SePrivilegeCheck` at `0x1402cf6b9`
- `ntoskrnl!SePrivilegeCheck` at `0x1402cf6b9`
- `ntoskrnl!IoComputeRedirectionTrustLevel` at `0x1402cfb9b`
- `ntoskrnl!IoComputeRedirectionTrustLevel` at `0x1402cfb9b`

## string_xrefs

- `0x1402cf4d2`: `MountSup.c`
- `0x1402cf54c`: `MountSup.c`
- `0x1402cf601`: `MountSup.c`
- `0x1402cf7bb`: `MountSup.c`
- `0x1402cf863`: `MountSup.c`
- `0x1402cf8d9`: `MountSup.c`
- `0x1402d0578`: `MountSup.c`
- `0x1402d05f0`: `MountSup.c`
- `0x1402d061b`: `MountSup.c`

## pseudocode

```c
void __fastcall RefsSetReparsePointInternal(
        struct _IRP_CONTEXT *a1,
        struct _IRP *a2,
        struct _FCB *a3,
        struct _CCB *a4,
        unsigned int *a5,
        struct _GUID *a6,
        char a7,
        unsigned __int16 a8,
        PREPARSE_DATA_BUFFER ReparseBuffer,
        unsigned __int8 *a10)
{
  ULONGLONG ActualAllocationLength; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  NTSTATUS v14; // eax
  NTSTATUS v15; // ebx
  ULONG ReparseTag; // r13d
  PIRP v17; // r8
  __int64 v18; // rcx
  struct _SECURITY_SUBJECT_CONTEXT *v19; // rbx
  KPROCESSOR_MODE v20; // al
  __int64 v21; // rdx
  unsigned int v22; // r9d
  int v23; // ebx
  NTSTATUS v24; // edi
  unsigned int v25; // r9d
  NTSTATUS v26; // edi
  unsigned int v27; // r9d
  struct _FCB *v28; // rdx
  __int64 v29; // r9
  char v30; // al
  __int16 NumberOfBufferingStateChangeWaiters; // ax
  __int64 v32; // rax
  __int64 v33; // rdx
  char v34; // al
  struct CmsRowWithBuffer *v35; // r9
  int v36; // ecx
  _QWORD *UntypedAttribute; // r12
  struct _ROLLBACK_STRUCT *v38; // rax
  int v39; // r8d
  struct _ROLLBACK_STRUCT *v40; // rax
  int v41; // edx
  struct _ROLLBACK_STRUCT *v42; // rax
  int v43; // r8d
  unsigned int v44; // r8d
  struct _CCB *v45; // r13
  struct _IO_STACK_LOCATION *v46; // r13
  DWORD LowPart; // eax
  ULONG v48; // r12d
  struct _FCB *v49; // r8
  struct _SCB *v50; // r9
  struct _ROLLBACK_STRUCT *v51; // rax
  int v52; // r8d
  DWORD v53; // eax
  struct _FCB *v54; // r8
  struct _SCB *v55; // r9
  struct _ROLLBACK_STRUCT *v56; // rax
  int v57; // r8d
  struct _ROLLBACK_STRUCT *v58; // rax
  int v59; // edx
  struct _ROLLBACK_STRUCT *v60; // rax
  int v61; // r8d
  NTSTATUS v62; // ebx
  __int64 v63; // rax
  __int64 v64; // r8
  NTSTATUS v65; // eax
  unsigned int v66; // r8d
  NTSTATUS v67; // ebx
  NTSTATUS v68; // eax
  unsigned int v69; // r8d
  int v70; // [rsp+48h] [rbp-2B0h] BYREF
  struct _FCB *v71; // [rsp+50h] [rbp-2A8h]
  PIRP Irp; // [rsp+58h] [rbp-2A0h]
  struct _IO_STACK_LOCATION *v73; // [rsp+60h] [rbp-298h]
  void *v74; // [rsp+68h] [rbp-290h]
  struct _CCB *v75; // [rsp+70h] [rbp-288h]
  unsigned __int8 *v76; // [rsp+78h] [rbp-280h]
  _QWORD v77[3]; // [rsp+80h] [rbp-278h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+98h] [rbp-260h] BYREF
  _BYTE v79[120]; // [rsp+B0h] [rbp-248h] BYREF
  __int16 v80; // [rsp+128h] [rbp-1D0h]
  __int64 v81; // [rsp+2A8h] [rbp-50h]

  v75 = a4;
  v71 = a3;
  Irp = a2;
  v74 = ReparseBuffer;
  v77[2] = a1;
  v76 = a10;
  ActualAllocationLength = a3->ActualAllocationLength;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v73 = CurrentStackLocation;
  v81 = 0;
  v80 = 0;
  RefsAttributeManager::Initialize((RefsAttributeManager *)v79);
  v70 = 0;
  v14 = FsRtlValidateReparsePointBuffer(a8, ReparseBuffer);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
        (unsigned int)v14);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v15, 0, "MountSup.c", 0x2FEu);
    return;
  }
  ReparseTag = ReparseBuffer->ReparseTag;
  if ( ReparseBuffer->ReparseTag == -1610612733 && *((_BYTE *)a4 + 80) != 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids, 3221225731LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741565, 0, "MountSup.c", 0x31Au);
    return;
  }
  if ( a5
    && (int)*a5 > 0
    && (!a6 || *(_QWORD *)&a6->Data1 == *(_QWORD *)P && *(_QWORD *)a6->Data4 == *((_QWORD *)P + 1)) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811, 0, "MountSup.c", 0x32Eu);
    return;
  }
  v17 = Irp;
  v77[0] = Irp->AssociatedIrp.MasterIrp;
  if ( ReparseTag != -1610612724 )
    goto LABEL_53;
  *((_DWORD *)v74 + 4) &= 0xFFFFFFFu;
  if ( !*((_BYTE *)a1 + 40) )
  {
    v18 = *(_QWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 8);
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.Privilege[0].Luid = (LUID)35LL;
    RequiredPrivileges.Privilege[0].Attributes = 0;
    if ( (*(_DWORD *)(v18 + 20) & 0x10102) == 0 || (*(_DWORD *)(v18 + 12) & 4) == 0 )
    {
      v19 = (struct _SECURITY_SUBJECT_CONTEXT *)(v18 + 32);
      v20 = RefsEffectiveMode(v17, v17->Tail.Overlay.CurrentStackLocation);
      if ( !SePrivilegeCheck(&RequiredPrivileges, v19, v20) )
      {
        if ( ((unsigned int)dword_1402612AC & 0x4000000) == 0
          || (LOBYTE(v21) = RefsEffectiveMode(Irp, Irp->Tail.Overlay.CurrentStackLocation),
              (unsigned __int8)RtlIsSandboxedToken(v19, v21)) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              30,
              WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
              3221225569LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
          {
            v22 = 864;
LABEL_51:
            RefsStatusDebug(-1073741727, 0, "MountSup.c", v22);
            return;
          }
          return;
        }
      }
    }
    *((_WORD *)a4 + 44) |= 0x400u;
LABEL_53:
    v23 = 0;
    *((_QWORD *)a1 + 1) |= 1uLL;
    *((_DWORD *)a1 + 158) = *((_DWORD *)a4 + 21);
    v24 = (HIDWORD(v71->PrivateDispatchVector) & 0x4000) != 0 ? 0xC000026E : 0;
    if ( (HIDWORD(v71->PrivateDispatchVector) & 0x4000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
          (unsigned int)v24);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_243;
      v25 = 907;
      goto LABEL_60;
    }
    if ( (*(_BYTE *)(ActualAllocationLength + 8) & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v26 = -1073741533;
      }
      else
      {
        v26 = -1073741533;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids, 3221225763LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_243;
      v27 = 917;
      goto LABEL_69;
    }
    if ( !RefsIsFileOpen((const struct _FCB *)ActualAllocationLength) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v26 = -1073741528;
      }
      else
      {
        v26 = -1073741528;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids, 3221225768LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_243;
      v27 = 923;
      goto LABEL_69;
    }
    v30 = *((_BYTE *)v75 + 80);
    if ( v30 == 3 )
    {
      if ( !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(ReparseTag)
        && !RefsIsFileDeleteable(a1, (struct _FCB *)ActualAllocationLength) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v26 = -1073741567;
        }
        else
        {
          v26 = -1073741567;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            35,
            WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
            3221225729LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_243;
        v27 = 956;
        goto LABEL_69;
      }
    }
    else if ( v30 == 2 )
    {
      NumberOfBufferingStateChangeWaiters = v28->NumberOfBufferingStateChangeWaiters;
      if ( (NumberOfBufferingStateChangeWaiters == 128 || NumberOfBufferingStateChangeWaiters == 176)
        && v28->FcbTableEntry.NodeTypeCode != (_WORD)v29 )
      {
        v32 = *(_QWORD *)(ActualAllocationLength + 88);
        if ( *(_QWORD *)(v32 + 248) == v29 && *(_QWORD *)(v32 + 256) != v29 )
        {
          if ( !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(ReparseTag)
            && !RefsIsFileDeleteable(a1, (struct _FCB *)ActualAllocationLength) )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v26 = -1073741567;
            }
            else
            {
              v26 = -1073741567;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                36,
                WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
                3221225729LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_243;
            v27 = 983;
            goto LABEL_69;
          }
          v28 = v71;
        }
      }
      if ( ReparseTag == -1610612724 )
      {
        if ( (*((_DWORD *)&v28->1 + 38) & 0x20) == 0 )
        {
          RefsUpdateScbFromAttribute(a1, (struct _SCB *)v28, 0);
          v28 = v71;
        }
        if ( v28->Header.FileSize.QuadPart )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v26 = -1073741192;
          }
          else
          {
            v26 = -1073741192;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              37,
              WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
              3221226104LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_243;
          v27 = 1004;
          goto LABEL_69;
        }
      }
    }
    if ( ReparseTag == -1610612733 || ReparseTag == -1610612724 )
    {
      LOBYTE(v33) = RefsEffectiveMode(Irp, v73);
      v24 = IoComputeRedirectionTrustLevel((unsigned int)(ReparseTag != -1610612733) + 1, v33, 0, &v70);
      if ( v24 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            38,
            WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
            (unsigned int)v24);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_243;
        v25 = 1026;
LABEL_60:
        RefsStatusDebug(v24, 0, "MountSup.c", v25);
LABEL_243:
        RefsAttributeManager::Cleanup((RefsAttributeManager *)v79, a1);
        return;
      }
    }
    if ( *(unsigned __int8 *)(ActualAllocationLength + 244) != v70 )
      v23 = 1;
    if ( *((_BYTE *)a1 + 40) )
      RefsPostUsnChange(a1, v71, 0x100000u, 0);
    v34 = RefsAttributeManager::LookupAttribute(v79, a1, ActualAllocationLength, 192, 0);
    v36 = *(_DWORD *)(ActualAllocationLength + 152) & 0x400;
    if ( v34 )
    {
      if ( v36 )
      {
        RefsAttributeManager::CopyFullAttribute(
          (RefsAttributeManager *)v79,
          a1,
          (struct _FCB *)ActualAllocationLength,
          v35);
        LODWORD(v71) = RefsAttributeManager::GetAttributeLength((RefsAttributeManager *)v79);
        UntypedAttribute = RefsAttributeManager::GetUntypedAttribute((RefsAttributeManager *)v79, (unsigned int)v71);
        if ( a5 )
        {
          if ( *a5 != *(_DWORD *)UntypedAttribute )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v26 = -1073741193;
            }
            else
            {
              v26 = -1073741193;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                40,
                WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
                3221226103LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_243;
            v27 = 1112;
            goto LABEL_69;
          }
          if ( (*a5 & 0x80000000) == 0
            && (*(_QWORD *)&a6->Data1 != UntypedAttribute[1] || *(_QWORD *)a6->Data4 != UntypedAttribute[2]) )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v26 = -1073741134;
            }
            else
            {
              v26 = -1073741134;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                41,
                WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
                3221226162LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_243;
            v27 = 1124;
            goto LABEL_69;
          }
        }
        if ( ReparseTag == *(_DWORD *)UntypedAttribute )
        {
          if ( (ReparseTag & 0x80000000) != 0
            || *(_QWORD *)(v77[0] + 8LL) == UntypedAttribute[1] && *(_QWORD *)(v77[0] + 16LL) == UntypedAttribute[2]
            || a5 )
          {
            if ( a1 != *((struct _IRP_CONTEXT **)a1 + 13)
              || !LOBYTE(IoGetTopLevelIrp()->Type)
              || *((_BYTE *)a1 + 40) != 13
              || (v46 = v73, LowPart = v73->Parameters.Read.ByteOffset.LowPart, LowPart != 589988) && LowPart != 590860
              || a8 <= (unsigned int)v71
              || (v48 = a8 - (_DWORD)v71, CcCanIWrite(v73->FileObject, v48, 0, (*((_DWORD *)a1 + 1) & 8) != 0)) )
            {
              v77[0] = 0;
              v77[1] = a8;
              RefsAttributeManager::UpdateAttribute(
                (RefsAttributeManager *)v79,
                a1,
                (struct _FCB *)ActualAllocationLength,
                v74,
                (const struct _RANGE *)v77,
                1);
              RefsAttributeManager::Reinitialize((RefsAttributeManager *)v79, a1);
              if ( v23 )
              {
                v51 = RefsAddStructToRollbackList(a1, 0x823u, (void *)ActualAllocationLength, 1u);
                v52 = *((_DWORD *)v51 + 1);
                if ( (v52 & 0x2000) == 0 )
                {
                  *((_BYTE *)v51 + 68) = *(_BYTE *)(ActualAllocationLength + 244);
                  *((_DWORD *)v51 + 1) = v52 | 0x2000;
                }
                *(_BYTE *)(ActualAllocationLength + 244) = v70;
                RefsUpdateStandardInformation(a1, (struct _FCB *)ActualAllocationLength);
              }
              v45 = v75;
              goto LABEL_228;
            }
            RefsSetReparsePointDeferWrite(a1, Irp, v49, v50, v46, (struct RefsAttributeManager *)v79, v48, v76);
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
            {
              v26 = 259;
            }
            else
            {
              v26 = 259;
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids, 259);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_243;
            v27 = 1280;
          }
          else
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v26 = -1073741134;
            }
            else
            {
              v26 = -1073741134;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                43,
                WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
                3221226162LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_243;
            v27 = 1188;
          }
        }
        else
        {
          if ( a5 )
          {
            v38 = RefsAddStructToRollbackList(a1, 0x823u, (void *)ActualAllocationLength, 1u);
            v39 = ~(unsigned __int16)*((_DWORD *)v38 + 13) & 0x400;
            *((_DWORD *)v38 + 13) |= v39;
            *((_DWORD *)v38 + 12) |= v39 & *(_DWORD *)(ActualAllocationLength + 152);
            *((_DWORD *)v38 + 1) |= 0x10u;
            v40 = RefsAddStructToRollbackList(a1, 0x823u, (void *)ActualAllocationLength, 1u);
            v41 = *((_DWORD *)v40 + 1);
            if ( (v41 & 0x40) == 0 )
            {
              *((_DWORD *)v40 + 16) = *(_DWORD *)(ActualAllocationLength + 156);
              *((_DWORD *)v40 + 1) = v41 | 0x40;
            }
            RefsDeleteReparsePointInternal(
              a1,
              (struct _FCB *)ActualAllocationLength,
              *(_DWORD *)UntypedAttribute,
              0,
              (struct RefsAttributeManager *)v79);
            RefsAttributeManager::Reinitialize((RefsAttributeManager *)v79, a1);
            RefsCreateReparsePointInternal(
              a1,
              (struct _FCB *)ActualAllocationLength,
              v74,
              a8,
              ReparseTag,
              0,
              (struct RefsAttributeManager *)v79);
            RefsAttributeManager::Reinitialize((RefsAttributeManager *)v79, a1);
            if ( v23 )
            {
              v42 = RefsAddStructToRollbackList(a1, 0x823u, (void *)ActualAllocationLength, 1u);
              v43 = *((_DWORD *)v42 + 1);
              if ( (v43 & 0x2000) == 0 )
              {
                *((_BYTE *)v42 + 68) = *(_BYTE *)(ActualAllocationLength + 244);
                *((_DWORD *)v42 + 1) = v43 | 0x2000;
              }
              *(_BYTE *)(ActualAllocationLength + 244) = v70;
            }
            RefsUpdateStandardInformation(a1, (struct _FCB *)ActualAllocationLength);
            *(_DWORD *)(ActualAllocationLength + 172) |= 4u;
            v45 = v75;
            *((_DWORD *)v75 + 1) |= 0x10000u;
LABEL_228:
            if ( !*((_BYTE *)a1 + 40) )
              goto LABEL_243;
            v62 = *(_DWORD *)(*((_QWORD *)a1 + 13) + 16LL);
            if ( v62 >= 0 )
            {
              v62 = 0;
              RefsCheckpointCurrentTransaction(a1);
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( v62 >= 0 )
                goto LABEL_237;
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  48,
                  WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
                  (unsigned int)v62);
            }
            if ( v62 >= 0 )
            {
LABEL_237:
              if ( *((_BYTE *)a1 + 40) )
              {
                v63 = *(_QWORD *)(ActualAllocationLength + 88);
                if ( *(_QWORD *)(v63 + 248) || (v64 = 0, !*(_QWORD *)(v63 + 256)) )
                  v64 = 0x400000;
                RefsUpdateFileTimestampsForChange(ActualAllocationLength, v45, v64, 0);
                if ( *((_BYTE *)a1 + 40) )
                  RefsFlushForWriteThrough(a1, ActualAllocationLength, 0);
              }
              goto LABEL_243;
            }
LABEL_258:
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(v62, a1, "MountSup.c", 0x5B3u);
            RefsRaiseStatusInternal(a1, v62, v44);
            __debugbreak();
            return;
          }
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v26 = -1073741193;
          }
          else
          {
            v26 = -1073741193;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              42,
              WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
              3221226103LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_243;
          v27 = 1159;
        }
LABEL_69:
        RefsStatusDebug(v26, 0, "MountSup.c", v27);
        goto LABEL_243;
      }
      v65 = RefsQueueTriageForDeadFcb(a1, (struct _FCB *)ActualAllocationLength);
      v67 = v65;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qd(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
          ActualAllocationLength,
          v65);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(v67, a1, "MountSup.c", 0x430u);
      RefsRaiseStatusInternal(a1, v67, v66);
    }
    else if ( !v36 )
    {
      if ( a5 && *a5 && (a7 & 1) == 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v26 = -1073741193;
        }
        else
        {
          v26 = -1073741193;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            46,
            WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
            3221226103LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_243;
        v27 = 1341;
      }
      else
      {
        if ( a1 != *((struct _IRP_CONTEXT **)a1 + 13)
          || !LOBYTE(IoGetTopLevelIrp()->Type)
          || *((_BYTE *)a1 + 40) != 13
          || (v53 = v73->Parameters.Read.ByteOffset.LowPart, v53 != 589988) && v53 != 590860
          || CcCanIWrite(v73->FileObject, a8, 0, (*((_DWORD *)a1 + 1) & 8) != 0) )
        {
          RefsAttributeManager::Reinitialize((RefsAttributeManager *)v79, a1);
          v56 = RefsAddStructToRollbackList(a1, 0x823u, (void *)ActualAllocationLength, 1u);
          v57 = ~(unsigned __int16)*((_DWORD *)v56 + 13) & 0x400;
          *((_DWORD *)v56 + 13) |= v57;
          *((_DWORD *)v56 + 12) |= *(_DWORD *)(ActualAllocationLength + 152) & v57;
          *((_DWORD *)v56 + 1) |= 0x10u;
          v58 = RefsAddStructToRollbackList(a1, 0x823u, (void *)ActualAllocationLength, 1u);
          v59 = *((_DWORD *)v58 + 1);
          if ( (v59 & 0x40) == 0 )
          {
            *((_DWORD *)v58 + 16) = *(_DWORD *)(ActualAllocationLength + 156);
            *((_DWORD *)v58 + 1) = v59 | 0x40;
          }
          RefsCreateReparsePointInternal(
            a1,
            (struct _FCB *)ActualAllocationLength,
            v74,
            a8,
            ReparseTag,
            0,
            (struct RefsAttributeManager *)v79);
          RefsAttributeManager::Reinitialize((RefsAttributeManager *)v79, a1);
          v45 = v75;
          *((_DWORD *)v75 + 1) |= 0x10000u;
          if ( v23 )
          {
            if ( *((_BYTE *)a1 + 40) )
            {
              v60 = RefsAddStructToRollbackList(a1, 0x823u, (void *)ActualAllocationLength, 1u);
              v61 = *((_DWORD *)v60 + 1);
              if ( (v61 & 0x2000) == 0 )
              {
                *((_BYTE *)v60 + 68) = *(_BYTE *)(ActualAllocationLength + 244);
                *((_DWORD *)v60 + 1) = v61 | 0x2000;
              }
            }
            *(_BYTE *)(ActualAllocationLength + 244) = v70;
          }
          RefsUpdateStandardInformation(a1, (struct _FCB *)ActualAllocationLength);
          *(_DWORD *)(ActualAllocationLength + 172) |= 4u;
          goto LABEL_228;
        }
        RefsSetReparsePointDeferWrite(a1, Irp, v54, v55, v73, (struct RefsAttributeManager *)v79, a8, v76);
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        {
          v26 = 259;
        }
        else
        {
          v26 = 259;
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids, 259);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_243;
        v27 = 1370;
      }
      goto LABEL_69;
    }
    v68 = RefsQueueTriageForDeadFcb(a1, (struct _FCB *)ActualAllocationLength);
    v62 = v68;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        45,
        WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids,
        ActualAllocationLength,
        v68);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v62, a1, "MountSup.c", 0x530u);
    RefsRaiseStatusInternal(a1, v62, v69);
    goto LABEL_258;
  }
  if ( _bittest16((const signed __int16 *)a4 + 44, 0xAu) )
    goto LABEL_53;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids, 3221225569LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v22 = 875;
    goto LABEL_51;
  }
}

```

## disassembly

```asm
0x1402cf3d8  mov     r11, rsp
0x1402cf3db  push    rbx
0x1402cf3dc  push    rsi
0x1402cf3dd  push    rdi
0x1402cf3de  push    r12
0x1402cf3e0  push    r13
0x1402cf3e2  push    r14
0x1402cf3e4  push    r15
0x1402cf3e6  sub     rsp, 2C0h
0x1402cf3ed  mov     rax, cs:__security_cookie
0x1402cf3f4  xor     rax, rsp
0x1402cf3f7  mov     [rsp+2F8h+var_48], rax
0x1402cf3ff  mov     rdi, r9
0x1402cf402  mov     [rsp+2F8h+var_288], r9
0x1402cf407  mov     [rsp+2F8h+var_2A8], r8
0x1402cf40c  mov     [rsp+2F8h+Irp], rdx
0x1402cf411  mov     rsi, rcx
0x1402cf414  mov     r12, [rsp+2F8h+ReparseBuffer]
0x1402cf41c  mov     [rsp+2F8h+var_290], r12
0x1402cf421  mov     [rsp+2F8h+var_268], rcx
0x1402cf429  mov     rcx, [rsp+2F8h+arg_48]
0x1402cf431  mov     [rsp+2F8h+var_280], rcx
0x1402cf436  mov     r14, [r8+88h]
0x1402cf43d  mov     r15, [rdx+0B8h]
0x1402cf444  mov     [rsp+2F8h+var_298], r15
0x1402cf449  xor     ebx, ebx
0x1402cf44b  mov     [r11-50h], rbx
0x1402cf44f  mov     [rsp+2F8h+var_1D0], bx
0x1402cf457  lea     rcx, [r11-248h]; this
0x1402cf45e  call    ?Initialize@RefsAttributeManager@@AEAAXXZ; RefsAttributeManager::Initialize(void)
0x1402cf463  mov     [rsp+2F8h+var_2B0], ebx
0x1402cf467  movzx   ecx, [rsp+2F8h+arg_38]; BufferLength
0x1402cf46f  mov     rdx, r12; ReparseBuffer
0x1402cf472  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x1402cf479  nop     dword ptr [rax+rax+00h]
0x1402cf47e  mov     ebx, eax
0x1402cf480  xor     r9d, r9d
0x1402cf483  test    eax, eax
0x1402cf485  jns     short loc_1402CF4EA
0x1402cf487  lea     rcx, WPP_GLOBAL_Control
0x1402cf48e  mov     r10, cs:WPP_GLOBAL_Control
0x1402cf495  cmp     r10, rcx
0x1402cf498  jz      short loc_1402CF4C2
0x1402cf49a  test    dword ptr [r10+2Ch], 100h
0x1402cf4a2  jz      short loc_1402CF4C2
0x1402cf4a4  cmp     byte ptr [r10+29h], 4
0x1402cf4a9  jb      short loc_1402CF4C2
0x1402cf4ab  lea     edx, [r9+1Bh]
0x1402cf4af  mov     r9d, eax
0x1402cf4b2  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402cf4b9  mov     rcx, [r10+18h]
0x1402cf4bd  call    WPP_SF_d
0x1402cf4c2  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cf4c8  test    al, al
0x1402cf4ca  jz      short loc_1402CF4E2
0x1402cf4cc  mov     r9d, 2FEh; unsigned int
0x1402cf4d2  lea     r8, aMountsupC; "MountSup.c"
0x1402cf4d9  xor     edx, edx; struct _IRP_CONTEXT *
0x1402cf4db  mov     ecx, ebx; Status
0x1402cf4dd  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402cf4e2  mov     eax, ebx
0x1402cf4e4  jmp     loc_1402D0638
0x1402cf4ea  mov     r13d, [r12]
0x1402cf4ee  cmp     r13d, 0A0000003h
0x1402cf4f5  jnz     short loc_1402CF569
0x1402cf4f7  cmp     byte ptr [rdi+50h], 3
0x1402cf4fb  jz      short loc_1402CF569
0x1402cf4fd  lea     rcx, WPP_GLOBAL_Control
0x1402cf504  mov     r10, cs:WPP_GLOBAL_Control
0x1402cf50b  cmp     r10, rcx
0x1402cf50e  jz      short loc_1402CF53C
0x1402cf510  test    dword ptr [r10+2Ch], 100h
0x1402cf518  jz      short loc_1402CF53C
0x1402cf51a  cmp     byte ptr [r10+29h], 4
0x1402cf51f  jb      short loc_1402CF53C
0x1402cf521  mov     edx, 1Ch
0x1402cf526  mov     r9d, 0C0000103h
0x1402cf52c  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402cf533  mov     rcx, [r10+18h]
0x1402cf537  call    WPP_SF_d
0x1402cf53c  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cf542  test    cl, cl
0x1402cf544  jz      short loc_1402CF55F
0x1402cf546  mov     r9d, 31Ah; unsigned int
0x1402cf54c  lea     r8, aMountsupC; "MountSup.c"
0x1402cf553  xor     edx, edx; struct _IRP_CONTEXT *
0x1402cf555  mov     ecx, 0C0000103h; Status
0x1402cf55a  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402cf55f  mov     eax, 0C0000103h
0x1402cf564  jmp     loc_1402D0638
0x1402cf569  mov     r12, [rsp+2F8h+arg_20]
0x1402cf571  test    r12, r12
0x1402cf574  jz      loc_1402CF61E
0x1402cf57a  mov     eax, [r12]
0x1402cf57e  test    eax, eax
0x1402cf580  jz      loc_1402CF61E
0x1402cf586  js      loc_1402CF61E
0x1402cf58c  mov     rcx, [rsp+2F8h+arg_28]
0x1402cf594  test    rcx, rcx
0x1402cf597  jz      short loc_1402CF5B2
0x1402cf599  mov     rdx, cs:P
0x1402cf5a0  mov     rax, [rcx]
0x1402cf5a3  cmp     rax, [rdx]
0x1402cf5a6  jnz     short loc_1402CF61E
0x1402cf5a8  mov     rax, [rcx+8]
0x1402cf5ac  cmp     rax, [rdx+8]
0x1402cf5b0  jnz     short loc_1402CF61E
0x1402cf5b2  lea     rcx, WPP_GLOBAL_Control
0x1402cf5b9  mov     r10, cs:WPP_GLOBAL_Control
0x1402cf5c0  cmp     r10, rcx
0x1402cf5c3  jz      short loc_1402CF5F1
0x1402cf5c5  test    dword ptr [r10+2Ch], 100h
0x1402cf5cd  jz      short loc_1402CF5F1
0x1402cf5cf  cmp     byte ptr [r10+29h], 4
0x1402cf5d4  jb      short loc_1402CF5F1
0x1402cf5d6  mov     edx, 1Dh
0x1402cf5db  mov     r9d, 0C000000Dh
0x1402cf5e1  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402cf5e8  mov     rcx, [r10+18h]
0x1402cf5ec  call    WPP_SF_d
0x1402cf5f1  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cf5f7  test    cl, cl
0x1402cf5f9  jz      short loc_1402CF614
0x1402cf5fb  mov     r9d, 32Eh; unsigned int
0x1402cf601  lea     r8, aMountsupC; "MountSup.c"
0x1402cf608  xor     edx, edx; struct _IRP_CONTEXT *
0x1402cf60a  mov     ecx, 0C000000Dh; Status
0x1402cf60f  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402cf614  mov     eax, 0C000000Dh
0x1402cf619  jmp     loc_1402D0638
0x1402cf61e  mov     r8, [rsp+2F8h+Irp]
0x1402cf623  mov     rax, [r8+18h]
0x1402cf627  mov     [rsp+2F8h+var_278], rax
0x1402cf62f  cmp     r13d, 0A000000Ch
0x1402cf636  jnz     loc_1402CF7D8
0x1402cf63c  mov     rax, [rsp+2F8h+var_290]
0x1402cf641  and     dword ptr [rax+10h], 0FFFFFFFh
0x1402cf648  cmp     [rsi+28h], r9b
0x1402cf64c  jnz     loc_1402CF764
0x1402cf652  mov     rax, [r15+8]
0x1402cf656  mov     rcx, [rax+8]
0x1402cf65a  mov     r15d, 1
0x1402cf660  mov     [rsp+2F8h+RequiredPrivileges.PrivilegeCount], r15d
0x1402cf668  mov     [rsp+2F8h+RequiredPrivileges.Control], r15d
0x1402cf670  mov     qword ptr [rsp+2F8h+RequiredPrivileges.Privilege.Luid.LowPart], 23h ; '#'
0x1402cf67c  mov     [rsp+2F8h+RequiredPrivileges.Privilege.Attributes], r9d
0x1402cf684  test    dword ptr [rcx+14h], 10102h
0x1402cf68b  jz      short loc_1402CF698
0x1402cf68d  mov     eax, [rcx+0Ch]
0x1402cf690  test    al, 4
0x1402cf692  jnz     loc_1402CF759
0x1402cf698  lea     rbx, [rcx+20h]
0x1402cf69c  mov     rdx, [r8+0B8h]; struct _IO_STACK_LOCATION *
0x1402cf6a3  mov     rcx, r8; struct _IRP *
0x1402cf6a6  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402cf6ab  mov     r8b, al; AccessMode
0x1402cf6ae  mov     rdx, rbx; SubjectSecurityContext
0x1402cf6b1  lea     rcx, [rsp+2F8h+RequiredPrivileges]; RequiredPrivileges
0x1402cf6b9  call    cs:__imp_SePrivilegeCheck
0x1402cf6c0  nop     dword ptr [rax+rax+00h]
0x1402cf6c5  xor     r9d, r9d
0x1402cf6c8  test    al, al
0x1402cf6ca  jnz     loc_1402CF759
0x1402cf6d0  test    cs:dword_1402612AC, 4000000h
0x1402cf6da  jz      short loc_1402CF708
0x1402cf6dc  mov     rax, [rsp+2F8h+Irp]
0x1402cf6e1  mov     rdx, [rax+0B8h]; struct _IO_STACK_LOCATION *
0x1402cf6e8  mov     rcx, rax; struct _IRP *
0x1402cf6eb  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402cf6f0  mov     dl, al
0x1402cf6f2  mov     rcx, rbx
0x1402cf6f5  call    cs:__imp_RtlIsSandboxedToken
0x1402cf6fc  nop     dword ptr [rax+rax+00h]
0x1402cf701  xor     r9d, r9d
0x1402cf704  test    al, al
0x1402cf706  jz      short loc_1402CF759
0x1402cf708  lea     rcx, WPP_GLOBAL_Control
0x1402cf70f  mov     r10, cs:WPP_GLOBAL_Control
0x1402cf716  cmp     r10, rcx
0x1402cf719  jz      short loc_1402CF747
0x1402cf71b  test    dword ptr [r10+2Ch], 100h
0x1402cf723  jz      short loc_1402CF747
0x1402cf725  cmp     byte ptr [r10+29h], 4
0x1402cf72a  jb      short loc_1402CF747
0x1402cf72c  mov     edx, 1Eh
0x1402cf731  mov     r9d, 0C0000061h
0x1402cf737  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402cf73e  mov     rcx, [r10+18h]
0x1402cf742  call    WPP_SF_d
0x1402cf747  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cf74d  test    al, al
0x1402cf74f  jz      short loc_1402CF7CE
0x1402cf751  mov     r9d, 360h
0x1402cf757  jmp     short loc_1402CF7BB
0x1402cf759  mov     ecx, 400h
0x1402cf75e  or      [rdi+58h], cx
0x1402cf762  jmp     short loc_1402CF7DE
0x1402cf764  bt      word ptr [rdi+58h], 0Ah
0x1402cf76a  jb      short loc_1402CF7D8
0x1402cf76c  lea     rcx, WPP_GLOBAL_Control
0x1402cf773  mov     r10, cs:WPP_GLOBAL_Control
0x1402cf77a  cmp     r10, rcx
0x1402cf77d  jz      short loc_1402CF7AB
0x1402cf77f  test    dword ptr [r10+2Ch], 100h
0x1402cf787  jz      short loc_1402CF7AB
0x1402cf789  cmp     byte ptr [r10+29h], 4
0x1402cf78e  jb      short loc_1402CF7AB
0x1402cf790  mov     edx, 1Fh
0x1402cf795  mov     r9d, 0C0000061h
0x1402cf79b  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402cf7a2  mov     rcx, [r10+18h]
0x1402cf7a6  call    WPP_SF_d
0x1402cf7ab  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cf7b1  test    cl, cl
0x1402cf7b3  jz      short loc_1402CF7CE
0x1402cf7b5  mov     r9d, 36Bh; unsigned int
0x1402cf7bb  lea     r8, aMountsupC; "MountSup.c"
0x1402cf7c2  xor     edx, edx; struct _IRP_CONTEXT *
0x1402cf7c4  mov     ecx, 0C0000061h; Status
0x1402cf7c9  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402cf7ce  mov     eax, 0C0000061h
0x1402cf7d3  jmp     loc_1402D0638
0x1402cf7d8  mov     r15d, 1
0x1402cf7de  mov     ebx, r9d
0x1402cf7e1  or      [rsi+8], r15
0x1402cf7e5  mov     eax, [rdi+54h]
0x1402cf7e8  mov     [rsi+278h], eax
0x1402cf7ee  mov     rdx, [rsp+2F8h+var_2A8]
0x1402cf7f3  mov     ecx, [rdx+12Ch]
0x1402cf7f9  and     ecx, 4000h
0x1402cf7ff  mov     eax, ecx
0x1402cf801  neg     eax
0x1402cf803  sbb     edi, edi
0x1402cf805  and     edi, 0C000026Eh
0x1402cf80b  mov     [rsp+2F8h+var_2B8], edi
0x1402cf80f  test    ecx, ecx
0x1402cf811  jz      short loc_1402CF878
0x1402cf813  lea     rcx, WPP_GLOBAL_Control
0x1402cf81a  mov     r10, cs:WPP_GLOBAL_Control
0x1402cf821  cmp     r10, rcx
0x1402cf824  jz      short loc_1402CF84F
0x1402cf826  mov     eax, [r10+2Ch]
0x1402cf82a  bt      eax, 8
0x1402cf82e  jnb     short loc_1402CF84F
0x1402cf830  cmp     byte ptr [r10+29h], 4
0x1402cf835  jb      short loc_1402CF84F
0x1402cf837  mov     edx, 20h ; ' '
0x1402cf83c  mov     r9d, edi
0x1402cf83f  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402cf846  mov     rcx, [r10+18h]
0x1402cf84a  call    WPP_SF_d
0x1402cf84f  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cf855  test    al, al
0x1402cf857  jz      loc_1402D0504
0x1402cf85d  mov     r9d, 38Bh; unsigned int
0x1402cf863  lea     r8, aMountsupC; "MountSup.c"
0x1402cf86a  xor     edx, edx; struct _IRP_CONTEXT *
0x1402cf86c  mov     ecx, edi; Status
0x1402cf86e  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402cf873  jmp     loc_1402D0504
0x1402cf878  mov     al, [r14+8]
0x1402cf87c  test    r15b, al
0x1402cf87f  jz      short loc_1402CF8F2
0x1402cf881  lea     rcx, WPP_GLOBAL_Control
0x1402cf888  mov     r10, cs:WPP_GLOBAL_Control
0x1402cf88f  cmp     r10, rcx
0x1402cf892  jz      short loc_1402CF8C4
0x1402cf894  mov     eax, [r10+2Ch]
0x1402cf898  bt      eax, 8
0x1402cf89c  jnb     short loc_1402CF8C4
0x1402cf89e  cmp     byte ptr [r10+29h], 4
0x1402cf8a3  jb      short loc_1402CF8C4
0x1402cf8a5  mov     edx, 21h ; '!'
0x1402cf8aa  mov     edi, 0C0000123h
0x1402cf8af  mov     r9d, edi
0x1402cf8b2  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402cf8b9  mov     rcx, [r10+18h]
0x1402cf8bd  call    WPP_SF_d
0x1402cf8c2  jmp     short loc_1402CF8C9
0x1402cf8c4  mov     edi, 0C0000123h
0x1402cf8c9  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cf8cf  test    al, al
0x1402cf8d1  jz      short loc_1402CF8E9
0x1402cf8d3  mov     r9d, 395h; unsigned int
0x1402cf8d9  lea     r8, aMountsupC; "MountSup.c"
0x1402cf8e0  xor     edx, edx; struct _IRP_CONTEXT *
0x1402cf8e2  mov     ecx, edi; Status
0x1402cf8e4  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402cf8e9  mov     [rsp+2F8h+var_2B8], edi
0x1402cf8ed  jmp     loc_1402D0504
0x1402cf8f2  mov     rcx, r14; struct _FCB *
0x1402cf8f5  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x1402cf8fa  test    al, al
0x1402cf8fc  jnz     short loc_1402CF958
0x1402cf8fe  lea     rcx, WPP_GLOBAL_Control
0x1402cf905  mov     r10, cs:WPP_GLOBAL_Control
0x1402cf90c  cmp     r10, rcx
0x1402cf90f  jz      short loc_1402CF941
0x1402cf911  mov     eax, [r10+2Ch]
0x1402cf915  bt      eax, 8
  ... truncated ...
```
