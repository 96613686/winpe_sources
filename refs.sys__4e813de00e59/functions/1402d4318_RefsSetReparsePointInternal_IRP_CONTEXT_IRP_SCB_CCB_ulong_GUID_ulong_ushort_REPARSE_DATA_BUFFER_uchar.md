# RefsSetReparsePointInternal(_IRP_CONTEXT *,_IRP *,_SCB *,_CCB *,ulong *,_GUID *,ulong,ushort,_REPARSE_DATA_BUFFER *,uchar *)

- ea: `0x1402d4318`
- end: `0x1402d559b`
- name: `?RefsSetReparsePointInternal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_SCB@@PEAU_CCB@@PEAKPEAU_GUID@@KGPEAU_REPARSE_DATA_BUFFER@@PEAE@Z`
- size: `4739`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct _IRP *@<rdx>, struct _SCB *@<r8>, struct _CCB *@<r9>, unsigned int *, struct _GUID *, char, unsigned __int16, struct _REPARSE_DATA_BUFFER *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `28`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402986f0`
- `0x1402d390c`
- `0x1402d3dcc`

## callees

- `0x140028be0`
- `0x140029a60`
- `0x140037bbc`
- `0x140047e80`
- `0x140076ad0`
- `0x1400862c0`
- `0x140088990`
- `0x1400914e0`
- `0x14009d0c4`
- `0x1400aa8a4`
- `0x1400cea34`
- `0x1400d0fd8`
- `0x1400e6488`
- `0x1400ffb94`
- `0x140112a1c`
- `0x1401f3fc0`
- `0x14028c3d4`
- `0x14028ebac`
- `0x1402956b8`
- `0x1402958f0`
- `0x1402d4318`
- `0x140302e10`
- `0x140304230`
- `0x140306290`
- `0x140315f30`
- `0x14031f9c0`
- `0x140339b3c`
- `0x14033afa0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1402d4f3e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1402d517c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1402d4f3e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1402d517c`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1402d48ab`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1402d4989`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1402d48ab`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1402d4989`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1402d43b2`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1402d43b2`
- `ntoskrnl!RtlIsSandboxedToken` at `0x1402d4635`
- `ntoskrnl!RtlIsSandboxedToken` at `0x1402d4635`
- `ntoskrnl!CcCanIWrite` at `0x1402d4fa6`
- `ntoskrnl!CcCanIWrite` at `0x1402d51d3`
- `ntoskrnl!CcCanIWrite` at `0x1402d4fa6`
- `ntoskrnl!CcCanIWrite` at `0x1402d51d3`
- `ntoskrnl!SePrivilegeCheck` at `0x1402d45f9`
- `ntoskrnl!SePrivilegeCheck` at `0x1402d45f9`
- `ntoskrnl!IoComputeRedirectionTrustLevel` at `0x1402d4adb`
- `ntoskrnl!IoComputeRedirectionTrustLevel` at `0x1402d4adb`

## string_xrefs

- `0x1402d4412`: `MountSup.c`
- `0x1402d448c`: `MountSup.c`
- `0x1402d4541`: `MountSup.c`
- `0x1402d46fb`: `MountSup.c`
- `0x1402d47a3`: `MountSup.c`
- `0x1402d4819`: `MountSup.c`
- `0x1402d54b8`: `MountSup.c`
- `0x1402d5530`: `MountSup.c`
- `0x1402d555b`: `MountSup.c`

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
        if ( ((unsigned int)dword_1402682AC & 0x4000000) == 0
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
0x1402d4318  mov     r11, rsp
0x1402d431b  push    rbx
0x1402d431c  push    rsi
0x1402d431d  push    rdi
0x1402d431e  push    r12
0x1402d4320  push    r13
0x1402d4322  push    r14
0x1402d4324  push    r15
0x1402d4326  sub     rsp, 2C0h
0x1402d432d  mov     rax, cs:__security_cookie
0x1402d4334  xor     rax, rsp
0x1402d4337  mov     [rsp+2F8h+var_48], rax
0x1402d433f  mov     rdi, r9
0x1402d4342  mov     [rsp+2F8h+var_288], r9
0x1402d4347  mov     [rsp+2F8h+var_2A8], r8
0x1402d434c  mov     [rsp+2F8h+Irp], rdx
0x1402d4351  mov     rsi, rcx
0x1402d4354  mov     r12, [rsp+2F8h+ReparseBuffer]
0x1402d435c  mov     [rsp+2F8h+var_290], r12
0x1402d4361  mov     [rsp+2F8h+var_268], rcx
0x1402d4369  mov     rcx, [rsp+2F8h+arg_48]
0x1402d4371  mov     [rsp+2F8h+var_280], rcx
0x1402d4376  mov     r14, [r8+88h]
0x1402d437d  mov     r15, [rdx+0B8h]
0x1402d4384  mov     [rsp+2F8h+var_298], r15
0x1402d4389  xor     ebx, ebx
0x1402d438b  mov     [r11-50h], rbx
0x1402d438f  mov     [rsp+2F8h+var_1D0], bx
0x1402d4397  lea     rcx, [r11-248h]; this
0x1402d439e  call    ?Initialize@RefsAttributeManager@@AEAAXXZ; RefsAttributeManager::Initialize(void)
0x1402d43a3  mov     [rsp+2F8h+var_2B0], ebx
0x1402d43a7  movzx   ecx, [rsp+2F8h+arg_38]; BufferLength
0x1402d43af  mov     rdx, r12; ReparseBuffer
0x1402d43b2  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x1402d43b9  nop     dword ptr [rax+rax+00h]
0x1402d43be  mov     ebx, eax
0x1402d43c0  xor     r9d, r9d
0x1402d43c3  test    eax, eax
0x1402d43c5  jns     short loc_1402D442A
0x1402d43c7  lea     rcx, WPP_GLOBAL_Control
0x1402d43ce  mov     r10, cs:WPP_GLOBAL_Control
0x1402d43d5  cmp     r10, rcx
0x1402d43d8  jz      short loc_1402D4402
0x1402d43da  test    dword ptr [r10+2Ch], 100h
0x1402d43e2  jz      short loc_1402D4402
0x1402d43e4  cmp     byte ptr [r10+29h], 4
0x1402d43e9  jb      short loc_1402D4402
0x1402d43eb  lea     edx, [r9+1Bh]
0x1402d43ef  mov     r9d, eax
0x1402d43f2  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402d43f9  mov     rcx, [r10+18h]
0x1402d43fd  call    WPP_SF_d
0x1402d4402  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402d4408  test    al, al
0x1402d440a  jz      short loc_1402D4422
0x1402d440c  mov     r9d, 2FEh; unsigned int
0x1402d4412  lea     r8, aMountsupC; "MountSup.c"
0x1402d4419  xor     edx, edx; struct _IRP_CONTEXT *
0x1402d441b  mov     ecx, ebx; Status
0x1402d441d  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402d4422  mov     eax, ebx
0x1402d4424  jmp     loc_1402D5578
0x1402d442a  mov     r13d, [r12]
0x1402d442e  cmp     r13d, 0A0000003h
0x1402d4435  jnz     short loc_1402D44A9
0x1402d4437  cmp     byte ptr [rdi+50h], 3
0x1402d443b  jz      short loc_1402D44A9
0x1402d443d  lea     rcx, WPP_GLOBAL_Control
0x1402d4444  mov     r10, cs:WPP_GLOBAL_Control
0x1402d444b  cmp     r10, rcx
0x1402d444e  jz      short loc_1402D447C
0x1402d4450  test    dword ptr [r10+2Ch], 100h
0x1402d4458  jz      short loc_1402D447C
0x1402d445a  cmp     byte ptr [r10+29h], 4
0x1402d445f  jb      short loc_1402D447C
0x1402d4461  mov     edx, 1Ch
0x1402d4466  mov     r9d, 0C0000103h
0x1402d446c  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402d4473  mov     rcx, [r10+18h]
0x1402d4477  call    WPP_SF_d
0x1402d447c  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402d4482  test    cl, cl
0x1402d4484  jz      short loc_1402D449F
0x1402d4486  mov     r9d, 31Ah; unsigned int
0x1402d448c  lea     r8, aMountsupC; "MountSup.c"
0x1402d4493  xor     edx, edx; struct _IRP_CONTEXT *
0x1402d4495  mov     ecx, 0C0000103h; Status
0x1402d449a  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402d449f  mov     eax, 0C0000103h
0x1402d44a4  jmp     loc_1402D5578
0x1402d44a9  mov     r12, [rsp+2F8h+arg_20]
0x1402d44b1  test    r12, r12
0x1402d44b4  jz      loc_1402D455E
0x1402d44ba  mov     eax, [r12]
0x1402d44be  test    eax, eax
0x1402d44c0  jz      loc_1402D455E
0x1402d44c6  js      loc_1402D455E
0x1402d44cc  mov     rcx, [rsp+2F8h+arg_28]
0x1402d44d4  test    rcx, rcx
0x1402d44d7  jz      short loc_1402D44F2
0x1402d44d9  mov     rdx, cs:P
0x1402d44e0  mov     rax, [rcx]
0x1402d44e3  cmp     rax, [rdx]
0x1402d44e6  jnz     short loc_1402D455E
0x1402d44e8  mov     rax, [rcx+8]
0x1402d44ec  cmp     rax, [rdx+8]
0x1402d44f0  jnz     short loc_1402D455E
0x1402d44f2  lea     rcx, WPP_GLOBAL_Control
0x1402d44f9  mov     r10, cs:WPP_GLOBAL_Control
0x1402d4500  cmp     r10, rcx
0x1402d4503  jz      short loc_1402D4531
0x1402d4505  test    dword ptr [r10+2Ch], 100h
0x1402d450d  jz      short loc_1402D4531
0x1402d450f  cmp     byte ptr [r10+29h], 4
0x1402d4514  jb      short loc_1402D4531
0x1402d4516  mov     edx, 1Dh
0x1402d451b  mov     r9d, 0C000000Dh
0x1402d4521  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402d4528  mov     rcx, [r10+18h]
0x1402d452c  call    WPP_SF_d
0x1402d4531  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402d4537  test    cl, cl
0x1402d4539  jz      short loc_1402D4554
0x1402d453b  mov     r9d, 32Eh; unsigned int
0x1402d4541  lea     r8, aMountsupC; "MountSup.c"
0x1402d4548  xor     edx, edx; struct _IRP_CONTEXT *
0x1402d454a  mov     ecx, 0C000000Dh; Status
0x1402d454f  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402d4554  mov     eax, 0C000000Dh
0x1402d4559  jmp     loc_1402D5578
0x1402d455e  mov     r8, [rsp+2F8h+Irp]
0x1402d4563  mov     rax, [r8+18h]
0x1402d4567  mov     [rsp+2F8h+var_278], rax
0x1402d456f  cmp     r13d, 0A000000Ch
0x1402d4576  jnz     loc_1402D4718
0x1402d457c  mov     rax, [rsp+2F8h+var_290]
0x1402d4581  and     dword ptr [rax+10h], 0FFFFFFFh
0x1402d4588  cmp     [rsi+28h], r9b
0x1402d458c  jnz     loc_1402D46A4
0x1402d4592  mov     rax, [r15+8]
0x1402d4596  mov     rcx, [rax+8]
0x1402d459a  mov     r15d, 1
0x1402d45a0  mov     [rsp+2F8h+RequiredPrivileges.PrivilegeCount], r15d
0x1402d45a8  mov     [rsp+2F8h+RequiredPrivileges.Control], r15d
0x1402d45b0  mov     qword ptr [rsp+2F8h+RequiredPrivileges.Privilege.Luid.LowPart], 23h ; '#'
0x1402d45bc  mov     [rsp+2F8h+RequiredPrivileges.Privilege.Attributes], r9d
0x1402d45c4  test    dword ptr [rcx+14h], 10102h
0x1402d45cb  jz      short loc_1402D45D8
0x1402d45cd  mov     eax, [rcx+0Ch]
0x1402d45d0  test    al, 4
0x1402d45d2  jnz     loc_1402D4699
0x1402d45d8  lea     rbx, [rcx+20h]
0x1402d45dc  mov     rdx, [r8+0B8h]; struct _IO_STACK_LOCATION *
0x1402d45e3  mov     rcx, r8; struct _IRP *
0x1402d45e6  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402d45eb  mov     r8b, al; AccessMode
0x1402d45ee  mov     rdx, rbx; SubjectSecurityContext
0x1402d45f1  lea     rcx, [rsp+2F8h+RequiredPrivileges]; RequiredPrivileges
0x1402d45f9  call    cs:__imp_SePrivilegeCheck
0x1402d4600  nop     dword ptr [rax+rax+00h]
0x1402d4605  xor     r9d, r9d
0x1402d4608  test    al, al
0x1402d460a  jnz     loc_1402D4699
0x1402d4610  test    cs:dword_1402682AC, 4000000h
0x1402d461a  jz      short loc_1402D4648
0x1402d461c  mov     rax, [rsp+2F8h+Irp]
0x1402d4621  mov     rdx, [rax+0B8h]; struct _IO_STACK_LOCATION *
0x1402d4628  mov     rcx, rax; struct _IRP *
0x1402d462b  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402d4630  mov     dl, al
0x1402d4632  mov     rcx, rbx
0x1402d4635  call    cs:__imp_RtlIsSandboxedToken
0x1402d463c  nop     dword ptr [rax+rax+00h]
0x1402d4641  xor     r9d, r9d
0x1402d4644  test    al, al
0x1402d4646  jz      short loc_1402D4699
0x1402d4648  lea     rcx, WPP_GLOBAL_Control
0x1402d464f  mov     r10, cs:WPP_GLOBAL_Control
0x1402d4656  cmp     r10, rcx
0x1402d4659  jz      short loc_1402D4687
0x1402d465b  test    dword ptr [r10+2Ch], 100h
0x1402d4663  jz      short loc_1402D4687
0x1402d4665  cmp     byte ptr [r10+29h], 4
0x1402d466a  jb      short loc_1402D4687
0x1402d466c  mov     edx, 1Eh
0x1402d4671  mov     r9d, 0C0000061h
0x1402d4677  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402d467e  mov     rcx, [r10+18h]
0x1402d4682  call    WPP_SF_d
0x1402d4687  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402d468d  test    al, al
0x1402d468f  jz      short loc_1402D470E
0x1402d4691  mov     r9d, 360h
0x1402d4697  jmp     short loc_1402D46FB
0x1402d4699  mov     ecx, 400h
0x1402d469e  or      [rdi+58h], cx
0x1402d46a2  jmp     short loc_1402D471E
0x1402d46a4  bt      word ptr [rdi+58h], 0Ah
0x1402d46aa  jb      short loc_1402D4718
0x1402d46ac  lea     rcx, WPP_GLOBAL_Control
0x1402d46b3  mov     r10, cs:WPP_GLOBAL_Control
0x1402d46ba  cmp     r10, rcx
0x1402d46bd  jz      short loc_1402D46EB
0x1402d46bf  test    dword ptr [r10+2Ch], 100h
0x1402d46c7  jz      short loc_1402D46EB
0x1402d46c9  cmp     byte ptr [r10+29h], 4
0x1402d46ce  jb      short loc_1402D46EB
0x1402d46d0  mov     edx, 1Fh
0x1402d46d5  mov     r9d, 0C0000061h
0x1402d46db  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402d46e2  mov     rcx, [r10+18h]
0x1402d46e6  call    WPP_SF_d
0x1402d46eb  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402d46f1  test    cl, cl
0x1402d46f3  jz      short loc_1402D470E
0x1402d46f5  mov     r9d, 36Bh; unsigned int
0x1402d46fb  lea     r8, aMountsupC; "MountSup.c"
0x1402d4702  xor     edx, edx; struct _IRP_CONTEXT *
0x1402d4704  mov     ecx, 0C0000061h; Status
0x1402d4709  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402d470e  mov     eax, 0C0000061h
0x1402d4713  jmp     loc_1402D5578
0x1402d4718  mov     r15d, 1
0x1402d471e  mov     ebx, r9d
0x1402d4721  or      [rsi+8], r15
0x1402d4725  mov     eax, [rdi+54h]
0x1402d4728  mov     [rsi+278h], eax
0x1402d472e  mov     rdx, [rsp+2F8h+var_2A8]
0x1402d4733  mov     ecx, [rdx+12Ch]
0x1402d4739  and     ecx, 4000h
0x1402d473f  mov     eax, ecx
0x1402d4741  neg     eax
0x1402d4743  sbb     edi, edi
0x1402d4745  and     edi, 0C000026Eh
0x1402d474b  mov     [rsp+2F8h+var_2B8], edi
0x1402d474f  test    ecx, ecx
0x1402d4751  jz      short loc_1402D47B8
0x1402d4753  lea     rcx, WPP_GLOBAL_Control
0x1402d475a  mov     r10, cs:WPP_GLOBAL_Control
0x1402d4761  cmp     r10, rcx
0x1402d4764  jz      short loc_1402D478F
0x1402d4766  mov     eax, [r10+2Ch]
0x1402d476a  bt      eax, 8
0x1402d476e  jnb     short loc_1402D478F
0x1402d4770  cmp     byte ptr [r10+29h], 4
0x1402d4775  jb      short loc_1402D478F
0x1402d4777  mov     edx, 20h ; ' '
0x1402d477c  mov     r9d, edi
0x1402d477f  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402d4786  mov     rcx, [r10+18h]
0x1402d478a  call    WPP_SF_d
0x1402d478f  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402d4795  test    al, al
0x1402d4797  jz      loc_1402D5444
0x1402d479d  mov     r9d, 38Bh; unsigned int
0x1402d47a3  lea     r8, aMountsupC; "MountSup.c"
0x1402d47aa  xor     edx, edx; struct _IRP_CONTEXT *
0x1402d47ac  mov     ecx, edi; Status
0x1402d47ae  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402d47b3  jmp     loc_1402D5444
0x1402d47b8  mov     al, [r14+8]
0x1402d47bc  test    r15b, al
0x1402d47bf  jz      short loc_1402D4832
0x1402d47c1  lea     rcx, WPP_GLOBAL_Control
0x1402d47c8  mov     r10, cs:WPP_GLOBAL_Control
0x1402d47cf  cmp     r10, rcx
0x1402d47d2  jz      short loc_1402D4804
0x1402d47d4  mov     eax, [r10+2Ch]
0x1402d47d8  bt      eax, 8
0x1402d47dc  jnb     short loc_1402D4804
0x1402d47de  cmp     byte ptr [r10+29h], 4
0x1402d47e3  jb      short loc_1402D4804
0x1402d47e5  mov     edx, 21h ; '!'
0x1402d47ea  mov     edi, 0C0000123h
0x1402d47ef  mov     r9d, edi
0x1402d47f2  lea     r8, WPP_63b2e771753a393d18cce4ef8e3066db_Traceguids
0x1402d47f9  mov     rcx, [r10+18h]
0x1402d47fd  call    WPP_SF_d
0x1402d4802  jmp     short loc_1402D4809
0x1402d4804  mov     edi, 0C0000123h
0x1402d4809  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402d480f  test    al, al
0x1402d4811  jz      short loc_1402D4829
0x1402d4813  mov     r9d, 395h; unsigned int
0x1402d4819  lea     r8, aMountsupC; "MountSup.c"
0x1402d4820  xor     edx, edx; struct _IRP_CONTEXT *
0x1402d4822  mov     ecx, edi; Status
0x1402d4824  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402d4829  mov     [rsp+2F8h+var_2B8], edi
0x1402d482d  jmp     loc_1402D5444
0x1402d4832  mov     rcx, r14; struct _FCB *
0x1402d4835  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x1402d483a  test    al, al
0x1402d483c  jnz     short loc_1402D4898
0x1402d483e  lea     rcx, WPP_GLOBAL_Control
0x1402d4845  mov     r10, cs:WPP_GLOBAL_Control
0x1402d484c  cmp     r10, rcx
0x1402d484f  jz      short loc_1402D4881
0x1402d4851  mov     eax, [r10+2Ch]
0x1402d4855  bt      eax, 8
  ... truncated ...
```
