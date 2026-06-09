# RefsAccessCheck(_IRP_CONTEXT *,_CREATE_CONTEXT *,_FCB *,_FCB *,_IRP *,ulong,uchar,uchar,uchar)

- ea: `0x140307140`
- end: `0x14030806d`
- name: `?RefsAccessCheck@@YAXPEAU_IRP_CONTEXT@@PEAU_CREATE_CONTEXT@@PEAU_FCB@@2PEAU_IRP@@KEEE@Z`
- size: `3885`
- prototype: `void(struct _IRP_CONTEXT *, struct _CREATE_CONTEXT *, struct _FCB *, struct _FCB *, struct _IRP *, unsigned int, unsigned __int8, unsigned __int8, unsigned __int8)`
- caller_count: `4`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140291760`
- `0x140306dd0`
- `0x140308620`
- `0x14030a1a0`

## callees

- `0x14000a370`
- `0x14007c580`
- `0x140081670`
- `0x14008dbd0`
- `0x14008ed90`
- `0x1400ca788`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x140285008`
- `0x1402c77f8`
- `0x1402d2fec`
- `0x140307140`
- `0x140308080`
- `0x140324c10`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x140307270`
- `ntoskrnl!IoFileObjectType` at `0x140307439`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140307340`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1403077c1`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030790c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140307ac8`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140307340`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1403077c1`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030790c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140307ac8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14030758c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14030758c`
- `ntoskrnl!SeLockSubjectContext` at `0x14030730a`
- `ntoskrnl!SeLockSubjectContext` at `0x14030773d`
- `ntoskrnl!SeLockSubjectContext` at `0x140307d89`
- `ntoskrnl!SeLockSubjectContext` at `0x14030730a`
- `ntoskrnl!SeLockSubjectContext` at `0x14030773d`
- `ntoskrnl!SeLockSubjectContext` at `0x140307d89`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1403076d8`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140307c30`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140307ccf`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140307d2d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140307f60`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14033f4ab`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1403076d8`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140307c30`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140307ccf`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140307d2d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140307f60`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14033f4ab`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x14030727a`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x14030727a`
- `ntoskrnl!SeAuditingAnyFileEventsWithContextEx` at `0x1403072f3`
- `ntoskrnl!SeAuditingAnyFileEventsWithContextEx` at `0x1403072f3`
- `ntoskrnl!SeAppendPrivileges` at `0x140307616`
- `ntoskrnl!SeAppendPrivileges` at `0x140307b5b`
- `ntoskrnl!SeAppendPrivileges` at `0x140307616`
- `ntoskrnl!SeAppendPrivileges` at `0x140307b5b`
- `ntoskrnl!SeFreePrivileges` at `0x14030762a`
- `ntoskrnl!SeFreePrivileges` at `0x140307853`
- `ntoskrnl!SeFreePrivileges` at `0x14030799b`
- `ntoskrnl!SeFreePrivileges` at `0x140307b6f`
- `ntoskrnl!SeFreePrivileges` at `0x14030762a`
- `ntoskrnl!SeFreePrivileges` at `0x140307853`
- `ntoskrnl!SeFreePrivileges` at `0x14030799b`
- `ntoskrnl!SeFreePrivileges` at `0x140307b6f`
- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x140307443`
- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x140307443`
- `ntoskrnl!SeAuditingFileEventsWithContextEx` at `0x140307db3`
- `ntoskrnl!SeAuditingFileEventsWithContextEx` at `0x140307db3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140307ed4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140307f24`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140307ed4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140307f24`
- `ntoskrnl!SeOpenObjectForDeleteAuditAlarm` at `0x1403075f1`
- `ntoskrnl!SeOpenObjectForDeleteAuditAlarm` at `0x1403075f1`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x140307602`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x140307602`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140307cbb`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140307cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140307ff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140308009`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f472`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f48d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140307ff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140308009`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f472`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f48d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140307568`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140307568`

## pseudocode

```c
void __fastcall RefsAccessCheck(
        struct _IRP_CONTEXT *a1,
        struct _CREATE_CONTEXT *a2,
        struct _FCB *a3,
        struct _FCB *a4,
        struct _IRP *a5,
        unsigned int a6,
        unsigned __int8 a7,
        unsigned __int8 a8,
        unsigned __int8 a9)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _ACCESS_STATE *v11; // rbx
  unsigned int v12; // r14d
  BOOLEAN AccessGranted; // r12
  struct _IO_STACK_LOCATION *v14; // rcx
  UCHAR MajorFunction; // al
  char v16; // si
  unsigned int v17; // r8d
  struct _ACCESS_STATE *v18; // rdi
  struct _ACCESS_REASONS *v19; // r12
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  ACCESS_MASK PreviouslyGrantedAccess; // eax
  char v22; // al
  struct _FCB *v23; // rdi
  PFILE_OBJECT FileObject; // rcx
  unsigned __int16 *p_Length; // rdx
  USHORT Length; // ax
  struct _FILE_OBJECT *RelatedFileObject; // r9
  char v28; // r14
  int v29; // ecx
  int v30; // r9d
  USHORT v31; // cx
  char v32; // si
  bool v33; // di
  char *v34; // r9
  int v35; // edx
  int v36; // eax
  __int64 v37; // r8
  __int64 v38; // r8
  __int64 v39; // rcx
  int v40; // eax
  struct _ACCESS_STATE *v41; // rsi
  _ACCESS_REASONS *v42; // rdi
  struct _GENERIC_MAPPING *v43; // rax
  unsigned __int8 v44; // si
  char v45; // dl
  struct _ACCESS_STATE *v46; // rsi
  _ACCESS_REASONS *v47; // rdi
  struct _GENERIC_MAPPING *v48; // rax
  unsigned __int8 v49; // si
  char v50; // al
  bool v51; // zf
  unsigned int v52; // eax
  struct _FCB *v53; // rdx
  struct _IRP_CONTEXT *v54; // rdi
  unsigned int v55; // edx
  struct _ACCESS_STATE *v56; // rcx
  struct _ACCESS_REASONS *v57; // r12
  struct _GENERIC_MAPPING *v58; // rax
  _DWORD *FsContext2; // rax
  char IsFastResourceHeldExclusive; // al
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectSecurityContext; // rcx
  struct _UNICODE_STRING *v62; // rcx
  struct _FILE_OBJECT *v63; // rdx
  PCUNICODE_STRING v64; // rax
  PCUNICODE_STRING v65; // rdi
  unsigned int v66; // r8d
  char RequestorMode; // al
  ULONG Options; // edx
  unsigned __int64 v69; // rax
  __int64 v70; // r8
  NTSTATUS v71; // ebx
  struct _SCB *AccessState; // [rsp+20h] [rbp-208h]
  unsigned __int8 *GenerateOnClose; // [rsp+40h] [rbp-1E8h]
  struct _ACCESS_REASONS *v74; // [rsp+58h] [rbp-1D0h]
  struct _ACCESS_REASONS *v75; // [rsp+58h] [rbp-1D0h]
  char AccessMode; // [rsp+70h] [rbp-1B8h]
  char v77; // [rsp+72h] [rbp-1B6h]
  char v78; // [rsp+73h] [rbp-1B5h]
  char v79; // [rsp+74h] [rbp-1B4h]
  bool v80; // [rsp+75h] [rbp-1B3h]
  int v81; // [rsp+78h] [rbp-1B0h] BYREF
  unsigned int v82; // [rsp+7Ch] [rbp-1ACh] BYREF
  NTSTATUS Status; // [rsp+80h] [rbp-1A8h]
  char v84; // [rsp+84h] [rbp-1A4h]
  char v85; // [rsp+85h] [rbp-1A3h]
  unsigned int v86; // [rsp+88h] [rbp-1A0h] BYREF
  unsigned int v87; // [rsp+8Ch] [rbp-19Ch] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+90h] [rbp-198h] BYREF
  struct _IRP_CONTEXT *v89; // [rsp+98h] [rbp-190h]
  int v90; // [rsp+A0h] [rbp-188h]
  int v91; // [rsp+A4h] [rbp-184h]
  int v92; // [rsp+A8h] [rbp-180h]
  unsigned int v93; // [rsp+ACh] [rbp-17Ch]
  int v94; // [rsp+B0h] [rbp-178h]
  char v95; // [rsp+B4h] [rbp-174h]
  bool v96; // [rsp+B5h] [rbp-173h]
  struct _IO_STACK_LOCATION *v97; // [rsp+B8h] [rbp-170h]
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-168h] BYREF
  PCUNICODE_STRING p_FileName; // [rsp+D0h] [rbp-158h]
  PVOID P[2]; // [rsp+E0h] [rbp-148h] BYREF
  PCUNICODE_STRING Source; // [rsp+F0h] [rbp-138h]
  int v102; // [rsp+F8h] [rbp-130h]
  struct _UNICODE_STRING v103; // [rsp+100h] [rbp-128h] BYREF
  struct _UNICODE_STRING SourceString; // [rsp+110h] [rbp-118h] BYREF
  struct _FCB *v105; // [rsp+120h] [rbp-108h]
  struct _ACCESS_STATE *v106; // [rsp+128h] [rbp-100h]
  struct _UNICODE_STRING v107; // [rsp+130h] [rbp-F8h] BYREF
  struct _FCB *v108; // [rsp+140h] [rbp-E8h]
  struct _FCB *v109; // [rsp+148h] [rbp-E0h]
  struct _FCB *v110; // [rsp+150h] [rbp-D8h]
  UNICODE_STRING *v111; // [rsp+158h] [rbp-D0h]
  _ACCESS_REASONS v112; // [rsp+160h] [rbp-C8h] BYREF

  *(_QWORD *)&v103.Length = a4;
  v89 = a1;
  *(_QWORD *)&SourceString.Length = a1;
  *(_QWORD *)&v107.Length = a4;
  v81 = 0;
  Status = -1073741811;
  v87 = 0;
  Privileges = 0;
  DestinationString = 0;
  *(_OWORD *)P = 0;
  memset(&v112, 0, sizeof(v112));
  CurrentStackLocation = a5->Tail.Overlay.CurrentStackLocation;
  v97 = CurrentStackLocation;
  v11 = *(struct _ACCESS_STATE **)(CurrentStackLocation->Parameters.WMI.ProviderId + 8);
  v106 = v11;
  if ( !a3->ScavengerFinalizationList.Flink )
    RefsLoadSecurityDescriptor(a1, a3);
  Privileges = 0;
  Source = 0;
  LOBYTE(v91) = 0;
  LOBYTE(v92) = 0;
  DestinationString.Buffer = 0;
  *(_OWORD *)P = 0;
  SeAdjustAccessStateForAccessConstraints(
    IoFileObjectType,
    (char *)&a3->ScavengerFinalizationList.Flink[1].Flink + 4,
    v11);
  v12 = a6 & ~v11->PreviouslyGrantedAccess;
  AccessGranted = v12 == 0;
  v90 = v12 & 0x2000000;
  v102 = *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 20) & 0x1000;
  if ( CurrentStackLocation )
    v14 = CurrentStackLocation;
  else
    v14 = a5->Tail.Overlay.CurrentStackLocation;
  MajorFunction = v14->MajorFunction;
  if ( !v14->MajorFunction )
  {
    if ( (v14->Flags & 1) != 0 )
    {
      AccessMode = 1;
      goto LABEL_8;
    }
    goto LABEL_147;
  }
  if ( MajorFunction == 6 )
  {
    Options = v14->Parameters.Create.Options;
    v69 = Options - 10;
    if ( (unsigned int)v69 <= 0x3E )
    {
      v70 = 0x4080000000000003LL;
      if ( _bittest64(&v70, v69) )
      {
        RequestorMode = (v14->Flags & 1) == 0;
        goto LABEL_148;
      }
    }
    if ( Options == 71 && (v14->Flags & 1) != 0 )
    {
      AccessMode = 1;
      goto LABEL_8;
    }
LABEL_147:
    RequestorMode = a5->RequestorMode;
LABEL_148:
    AccessMode = RequestorMode;
    goto LABEL_8;
  }
  if ( MajorFunction != 5 || v14->Parameters.Create.Options != 71 || (v14->Flags & 1) == 0 )
    goto LABEL_147;
  AccessMode = 1;
LABEL_8:
  v16 = SeAuditingAnyFileEventsWithContextEx(
          (char *)&a3->ScavengerFinalizationList.Flink[1].Flink + 4,
          &v11->SubjectSecurityContext,
          0);
  v77 = v16;
  SeLockSubjectContext(&v11->SubjectSecurityContext);
  if ( !v12 )
    goto LABEL_24;
  v18 = v11;
  if ( a9 )
    v18 = 0;
  if ( v16 )
    v19 = (struct _ACCESS_REASONS *)((char *)v11->AuxData + 88);
  else
    v19 = 0;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  v84 = a8 != 0;
  AccessGranted = RefsSeAccessCheck(
                    v89,
                    a3,
                    &v11->SubjectSecurityContext,
                    1u,
                    a8 != 0,
                    v12,
                    v11->PreviouslyGrantedAccess,
                    &Privileges,
                    FileObjectGenericMapping,
                    AccessMode,
                    &v87,
                    v19,
                    &v81,
                    v18);
  if ( Privileges )
  {
    SeAppendPrivileges(v11, Privileges);
    SeFreePrivileges(Privileges);
    Privileges = 0;
  }
  if ( AccessGranted )
  {
    v12 &= ~(v87 | 0x2000000);
    if ( !a7 )
    {
      v11->PreviouslyGrantedAccess |= v87;
      PreviouslyGrantedAccess = v11->PreviouslyGrantedAccess;
      if ( v90 )
      {
        v35 = (unsigned __int8)v91;
        if ( (PreviouslyGrantedAccess & 0x10000) != 0 )
          v35 = 1;
        v91 = v35;
        v95 = v35;
        v51 = (PreviouslyGrantedAccess & 0x80u) == 0;
        v36 = (unsigned __int8)v92;
        if ( !v51 )
          v36 = 1;
        v92 = v36;
      }
      v11->RemainingDesiredAccess &= ~(v87 | 0x2000000);
    }
  }
  else
  {
    Status = v81;
    v94 = v81;
  }
  v22 = SeShouldCheckForAccessRightsFromParent(
          IoFileObjectType,
          (char *)&a3->ScavengerFinalizationList.Flink[1].Flink + 4,
          v11);
  v23 = *(struct _FCB **)&v103.Length;
  if ( !*(_QWORD *)&v103.Length || !v22 || (AccessGranted || (v12 & 0x10080) == 0) && (!v90 || (_BYTE)v91 && (_BYTE)v92) )
  {
LABEL_23:
    CurrentStackLocation = v97;
    goto LABEL_24;
  }
  v78 = 0;
  v79 = 0;
  v93 = 0;
  v86 = 0;
  v82 = 0;
  SeUnlockSubjectContext(&v11->SubjectSecurityContext);
  v108 = v23;
  LOBYTE(v37) = 1;
  RefsAcquireResourceShared(v89, v23, v37);
  if ( !v23->ScavengerFinalizationList.Flink )
  {
    v109 = v23;
    RefsReleaseResource(v89, v23);
    v110 = v23;
    LOBYTE(v38) = 1;
    RefsAcquireResourceExclusive(v39, v23, v38);
  }
  SeLockSubjectContext(&v11->SubjectSecurityContext);
  if ( !v23->ScavengerFinalizationList.Flink )
    RefsLoadSecurityDescriptor(v89, v23);
  memset(&v112, 0, sizeof(v112));
  if ( (v12 & 0x10000) != 0 || (v40 = v90) != 0 && !(_BYTE)v91 )
  {
    v41 = v11;
    if ( a9 )
      v41 = 0;
    v42 = &v112;
    if ( !v77 )
      v42 = 0;
    v43 = IoGetFileObjectGenericMapping();
    v74 = v42;
    v23 = *(struct _FCB **)&v103.Length;
    v44 = RefsSeAccessCheck(
            v89,
            *(struct _FCB **)&v103.Length,
            &v11->SubjectSecurityContext,
            1u,
            1,
            0x40u,
            0,
            &Privileges,
            v43,
            AccessMode,
            &v86,
            v74,
            &v81,
            v41);
    v45 = 1;
    v78 = 1;
    if ( Privileges )
    {
      SeFreePrivileges(Privileges);
      Privileges = 0;
      v45 = 1;
    }
    if ( v44 )
    {
      v86 = v86 & 0xFFFEFFBF | 0x10000;
      v12 &= ~0x10000u;
    }
    else
    {
      Status = v81;
      v94 = v81;
    }
    v16 = v77;
    v40 = v90;
  }
  else
  {
    v45 = 0;
  }
  if ( (v12 & 0x80u) != 0 || v40 && !(_BYTE)v92 )
  {
    v46 = v11;
    if ( a9 )
      v46 = 0;
    v47 = &v112;
    if ( !v77 )
      v47 = 0;
    v48 = IoGetFileObjectGenericMapping();
    v75 = v47;
    v23 = *(struct _FCB **)&v103.Length;
    v49 = RefsSeAccessCheck(
            v89,
            *(struct _FCB **)&v103.Length,
            &v11->SubjectSecurityContext,
            1u,
            1,
            1u,
            0,
            &Privileges,
            v48,
            AccessMode,
            &v82,
            v75,
            &v81,
            v46);
    v50 = 1;
    v79 = 1;
    if ( Privileges )
    {
      SeFreePrivileges(Privileges);
      Privileges = 0;
      v50 = 1;
    }
    if ( !v49 )
    {
      Status = v81;
      v94 = v81;
      v16 = v77;
      v45 = v78;
      goto LABEL_84;
    }
    v82 = v82 & 0xFFFFFF7E | 0x80;
    v12 &= ~0x80u;
    v16 = v77;
    v45 = v78;
  }
  v50 = v79;
LABEL_84:
  if ( !v16 )
    goto LABEL_93;
  v51 = v50 == 0;
  if ( !v50 )
  {
    if ( !v45 )
      goto LABEL_93;
    v51 = 1;
  }
  v52 = v93;
  if ( !v51 )
    v52 = 128;
  v93 = v52;
  if ( v45 )
  {
    v52 |= 0x10000u;
    v93 = v52;
  }
  RefsUpdateAccessReasonSourceToParentSD(v11, &v112, v52);
LABEL_93:
  v105 = v23;
  v53 = v23;
  v54 = v89;
  RefsReleaseResource(v89, v53);
  if ( v12 )
  {
    v56 = v11;
    if ( a9 )
      v56 = 0;
    *(_QWORD *)&v103.Length = v56;
    if ( v16 )
      v57 = (struct _ACCESS_REASONS *)((char *)v11->AuxData + 88);
    else
      v57 = 0;
    v58 = IoGetFileObjectGenericMapping();
    AccessGranted = RefsSeAccessCheck(
                      v54,
                      a3,
                      &v11->SubjectSecurityContext,
                      1u,
                      v84,
                      v12,
                      0,
                      &Privileges,
                      v58,
                      AccessMode,
                      &v87,
                      v57,
                      &v81,
                      *(struct _ACCESS_STATE **)&v103.Length);
    if ( Privileges )
    {
      SeAppendPrivileges(v11, Privileges);
      SeFreePrivileges(Privileges);
      Privileges = 0;
    }
    if ( AccessGranted )
    {
      v55 = v82;
    }
    else
    {
      Status = v81;
      v94 = v81;
      v55 = v82;
      if ( v12 == 0x2000000 && (v82 || v86) )
      {
        v87 = 0;
        AccessGranted = 1;
      }
    }
  }
  else
  {
    v55 = v82;
    if ( v82 || v86 )
      AccessGranted = 1;
  }
  if ( a7 )
    goto LABEL_23;
  CurrentStackLocation = v97;
  if ( AccessGranted )
  {
    v11->PreviouslyGrantedAccess |= v87 | v86 | v55;
    v11->RemainingDesiredAccess &= ~(v87 | v86 | v55 | 0x2000000);
  }
LABEL_24:
  if ( v16 )
  {
    FileObject = CurrentStackLocation->FileObject;
    p_Length = &FileObject->FileName.Length;
    p_FileName = &FileObject->FileName;
    Length = FileObject->FileName.Length;
    LOBYTE(v17) = Length != 0;
    v80 = Length != 0;
    if ( Length || (CurrentStackLocation->Parameters.Create.Options & 0x2000) == 0 )
    {
      RelatedFileObject = FileObject->RelatedFileObject;
      if ( RelatedFileObject && (FsContext2 = RelatedFileObject->FsContext2) != 0 && (FsContext2[1] & 8) != 0 )
      {
        *(_QWORD *)&SourceString.Length = *((_QWORD *)RelatedFileObject->FsContext + 17);
        IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(*(_QWORD *)(*(_QWORD *)&SourceString.Length + 88LL) + 64LL);
        p_SubjectSecurityContext = &v11->SubjectSecurityContext;
        if ( IsFastResourceHeldExclusive )
        {
          SeUnlockSubjectContext(p_SubjectSecurityContext);
          v28 = 0;
          *(struct _UNICODE_STRING *)P = *RefsBuildNormalizedName(
                                            &v107,
                                            v89,
                                            *(struct _FCB **)&SourceString.Length,
                                            0,
                                            AccessState);
          if ( v80 )
            RefsAppendNameToParent(v62, (struct _UNICODE_STRING *)P, (struct _UNICODE_STRING *)p_FileName);
        }
        else
        {
          SeUnlockSubjectContext(p_SubjectSecurityContext);
          v28 = 0;
          *(struct _UNICODE_STRING *)P = *RefsBuildNormalizedName(&v103, v89, a3, 0, AccessState);
        }
        LOBYTE(v17) = 1;
        v80 = 1;
        p_Length = (unsigned __int16 *)P;
        p_FileName = (PCUNICODE_STRING)P;
      }
      else
      {
        v28 = 1;
      }
    }
    else
    {
      SeUnlockSubjectContext(&v11->SubjectSecurityContext);
      v28 = 0;
      *(struct _UNICODE_STRING *)P = *RefsBuildNormalizedName(&SourceString, v89, a3, 0, AccessState);
      LOBYTE(v17) = 1;
      v80 = 1;
      p_Length = (unsigned __int16 *)P;
      p_FileName = (PCUNICODE_STRING)P;
    }
    if ( !v28 )
    {
      SeLockSubjectContext(&v11->SubjectSecurityContext);
      v16 = SeAuditingFileEventsWithContextEx(
              AccessGranted,
              (char *)&a3->ScavengerFinalizationList.Flink[1].Flink + 4,
              &v11->SubjectSecurityContext,
              0);
      p_Length = &p_FileName->Length;
      v17 = v80;
    }
    if ( v16 )
    {
      *(_QWORD *)&SourceString.Length = a3->Header.FileContextSupportPointer + 102;
      v29 = **(unsigned __int16 **)&SourceString.Length;
      v30 = *p_Length;
      if ( ((v30 + v29 + 4) & 0xFFFF0000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids,
            3221225523LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741773, v89, "SecurSup.c", 0x7D9u);
        RefsRaiseStatusInternal(v89, -1073741773, v17);
      }
      else
      {
        v31 = v30 + v29 + 4;
        DestinationString.MaximumLength = v31;
        if ( (_BYTE)v17 && **((_WORD **)p_Length + 1) == 92 )
        {
          v32 = 1;
          v85 = 1;
          v33 = 0;
LABEL_38:
          DestinationString.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v31, 0x53466552u);
          RtlCopyUnicodeString(&DestinationString, *(PCUNICODE_STRING *)&SourceString.Length);
          if ( !v32 && v33 )
          {
            v65 = Source;
            RtlAppendUnicodeStringToString(&DestinationString, Source);
            if ( v65->Length != 2 )
            {
              DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 92;
              DestinationString.Length += 2;
            }
          }
          if ( v80 )
            RtlAppendUnicodeStringToString(&DestinationString, p_FileName);
          v34 = (char *)&a3->ScavengerFinalizationList.Flink[1].Flink + 4;
          GenerateOnClose = &v11->GenerateOnClose;
          if ( v102 )
            SeOpenObjectForDeleteAuditAlarm(
              (PUNICODE_STRING)&ObjectTypeName,
              0,
              &DestinationString,
              v34,
              v11,
              0,
              AccessGranted,
              AccessMode,
              GenerateOnClose);
          else
            SeOpenObjectAuditAlarm(
              (PUNICODE_STRING)&ObjectTypeName,
              0,
              &DestinationString,
              v34,
              v11,
              0,
              AccessGranted,
              AccessMode,
              GenerateOnClose);
          goto LABEL_141;
        }
      }
      v32 = 0;
      v85 = 0;
      v63 = CurrentStackLocation->FileObject->RelatedFileObject;
      if ( v63 )
      {
        v64 = &v63->FileName;
        Source = &v63->FileName;
        v111 = &v63->FileName;
      }
      else
      {
        v64 = Source;
      }
      v33 = v64 && v64->Length;
      v96 = v33;
      if ( v33 )
      {
        v31 += v64->Length;
        DestinationString.MaximumLength = v31;
      }
      goto LABEL_38;
    }
  }
LABEL_141:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  SeUnlockSubjectContext(&v11->SubjectSecurityContext);
  if ( !AccessGranted )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
      v71 = Status;
    }
    else
    {
      v71 = Status;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids,
          (unsigned int)Status);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v71, v89, "SecurSup.c", 0x85Du);
    RefsRaiseStatusInternal(v89, v71, v66);
    JUMPOUT(0x140349C77LL);
  }
}

```

## disassembly

```asm
0x140307140  mov     r11, rsp
0x140307143  push    rbx
0x140307144  push    rsi
0x140307145  push    rdi
0x140307146  push    r12
0x140307148  push    r13
0x14030714a  push    r14
0x14030714c  push    r15
0x14030714e  sub     rsp, 1F0h
0x140307155  mov     rax, cs:__security_cookie
0x14030715c  xor     rax, rsp
0x14030715f  mov     [rsp+228h+var_48], rax
0x140307167  mov     rax, r9
0x14030716a  mov     qword ptr [rsp+228h+var_128.Length], rax
0x140307172  mov     r13, r8
0x140307175  mov     [rsp+228h+var_190], rcx
0x14030717d  mov     qword ptr [rsp+228h+SourceString], rcx
0x140307185  mov     qword ptr [rsp+228h+var_F8.Length], rax
0x14030718d  mov     rsi, [rsp+228h+arg_20]
0x140307195  xor     r14d, r14d
0x140307198  mov     [rsp+228h+var_1B0], r14d
0x14030719d  mov     [rsp+228h+Status], 0C000000Dh
0x1403071a8  mov     [r11-19Ch], r14d
0x1403071af  mov     [r11-198h], r14
0x1403071b6  xorps   xmm0, xmm0
0x1403071b9  movups  xmmword ptr [rsp+228h+DestinationString.Length], xmm0
0x1403071c1  xorps   xmm1, xmm1
0x1403071c4  movups  xmmword ptr [rsp+228h+P], xmm1
0x1403071cc  movups  xmmword ptr [rsp+228h+var_C8.Data], xmm0
0x1403071d4  movups  xmmword ptr [rsp+228h+var_C8.Data+10h], xmm0
0x1403071dc  movups  xmmword ptr [rsp+228h+var_C8.Data+20h], xmm0
0x1403071e4  movups  xmmword ptr [rsp+228h+var_C8.Data+30h], xmm0
0x1403071ec  movups  xmmword ptr [rsp+228h+var_C8.Data+40h], xmm0
0x1403071f4  movups  xmmword ptr [r11-78h], xmm0
0x1403071f9  movups  xmmword ptr [r11-68h], xmm0
0x1403071fe  movups  xmmword ptr [r11-58h], xmm0
0x140307203  mov     rdi, [rsi+0B8h]
0x14030720a  mov     [rsp+228h+var_170], rdi
0x140307212  mov     rbx, [rdi+8]
0x140307216  mov     rbx, [rbx+8]
0x14030721a  mov     [rsp+228h+var_100], rbx
0x140307222  cmp     [r8+0C0h], r14
0x140307229  jz      loc_140307FA6
0x14030722f  mov     [rsp+228h+Privileges], r14
0x140307237  mov     [rsp+228h+Source], r14
0x14030723f  mov     byte ptr [rsp+228h+var_184], r14b
0x140307247  mov     byte ptr [rsp+228h+var_180], r14b
0x14030724f  mov     [rsp+228h+DestinationString.Buffer], r14
0x140307257  xorps   xmm0, xmm0
0x14030725a  movups  xmmword ptr [rsp+228h+P], xmm0
0x140307262  mov     rdx, [r13+0C0h]
0x140307269  add     rdx, 14h
0x14030726d  mov     r8, rbx
0x140307270  mov     rcx, cs:__imp_IoFileObjectType
0x140307277  mov     rcx, [rcx]
0x14030727a  call    cs:__imp_SeAdjustAccessStateForAccessConstraints
0x140307281  nop     dword ptr [rax+rax+00h]
0x140307286  mov     r14d, [rbx+14h]
0x14030728a  not     r14d
0x14030728d  and     r14d, [rsp+228h+arg_28]
0x140307295  setz    r12b
0x140307299  mov     eax, r14d
0x14030729c  and     eax, 2000000h
0x1403072a1  mov     [rsp+228h+var_188], eax
0x1403072a8  mov     rax, [rdi+8]
0x1403072ac  mov     eax, [rax+14h]
0x1403072af  and     eax, 1000h
0x1403072b4  mov     [rsp+228h+var_130], eax
0x1403072bb  test    rdi, rdi
0x1403072be  jz      loc_140307FB3
0x1403072c4  mov     rcx, rdi
0x1403072c7  movzx   eax, byte ptr [rcx]
0x1403072ca  test    al, al
0x1403072cc  jnz     loc_140307FBF
0x1403072d2  test    byte ptr [rcx+2], 1
0x1403072d6  jz      loc_140307F99
0x1403072dc  mov     [rsp+228h+var_1B8], 1
0x1403072e1  mov     rcx, [r13+0C0h]
0x1403072e8  add     rcx, 14h
0x1403072ec  xor     r8d, r8d
0x1403072ef  lea     rdx, [rbx+20h]
0x1403072f3  call    cs:__imp_SeAuditingAnyFileEventsWithContextEx
0x1403072fa  nop     dword ptr [rax+rax+00h]
0x1403072ff  movzx   esi, al
0x140307302  mov     [rsp+228h+var_1B6], al
0x140307306  lea     rcx, [rbx+20h]; SubjectContext
0x14030730a  call    cs:__imp_SeLockSubjectContext
0x140307311  nop     dword ptr [rax+rax+00h]
0x140307316  mov     [rsp+228h+var_1B7], 1
0x14030731b  test    r14d, r14d
0x14030731e  jz      loc_14030747F
0x140307324  mov     rdi, rbx
0x140307327  xor     ecx, ecx
0x140307329  cmp     [rsp+228h+arg_40], cl
0x140307330  cmovnz  rdi, rcx
0x140307334  test    sil, sil
0x140307337  jnz     loc_1403074A0
0x14030733d  xor     r12d, r12d
0x140307340  call    cs:__imp_IoGetFileObjectGenericMapping
0x140307347  nop     dword ptr [rax+rax+00h]
0x14030734c  cmp     [rsp+228h+arg_38], 0
0x140307354  setnz   cl
0x140307357  mov     [rsp+228h+var_1A4], cl
0x14030735e  mov     [rsp+228h+var_1C0], rdi; struct _ACCESS_STATE *
0x140307363  lea     rdx, [rsp+228h+var_1B0]
0x140307368  mov     [rsp+228h+var_1C8], rdx; int *
0x14030736d  mov     [rsp+228h+var_1D0], r12; struct _ACCESS_REASONS *
0x140307372  lea     rdx, [rsp+228h+var_19C]
0x14030737a  mov     [rsp+228h+var_1D8], rdx; unsigned int *
0x14030737f  movzx   edx, [rsp+228h+var_1B8]
0x140307384  mov     [rsp+228h+var_1E0], dl; char
0x140307388  mov     [rsp+228h+GenerateOnClose], rax; struct _GENERIC_MAPPING *
0x14030738d  lea     rax, [rsp+228h+Privileges]
0x140307395  mov     qword ptr [rsp+228h+AccessMode], rax; struct _PRIVILEGE_SET **
0x14030739a  mov     eax, [rbx+14h]
0x14030739d  mov     dword ptr [rsp+228h+AccessGranted], eax; unsigned int
0x1403073a1  mov     dword ptr [rsp+228h+ObjectCreated], r14d; unsigned int
0x1403073a6  mov     byte ptr [rsp+228h+AccessState], cl; struct _SCB *
0x1403073aa  mov     r9b, 1; unsigned __int8
0x1403073ad  lea     r8, [rbx+20h]; struct _SECURITY_SUBJECT_CONTEXT *
0x1403073b1  mov     rdx, r13; struct _FCB *
0x1403073b4  mov     rcx, [rsp+228h+var_190]; struct _IRP_CONTEXT *
0x1403073bc  call    ?RefsSeAccessCheck@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SECURITY_SUBJECT_CONTEXT@@EEKKPEAPEAU_PRIVILEGE_SET@@PEAU_GENERIC_MAPPING@@DPEAKPEAU_ACCESS_REASONS@@PEAJPEAU_ACCESS_STATE@@@Z; RefsSeAccessCheck(_IRP_CONTEXT *,_FCB *,_SECURITY_SUBJECT_CONTEXT *,uchar,uchar,ulong,ulong,_PRIVILEGE_SET * *,_GENERIC_MAPPING *,char,ulong *,_ACCESS_REASONS *,long *,_ACCESS_STATE *)
0x1403073c1  movzx   r12d, al
0x1403073c5  mov     [rsp+228h+var_1B2], al
0x1403073c9  mov     rdx, [rsp+228h+Privileges]; Privileges
0x1403073d1  test    rdx, rdx
0x1403073d4  jnz     loc_140307613
0x1403073da  test    r12b, r12b
0x1403073dd  jz      loc_14030748C
0x1403073e3  mov     ecx, [rsp+228h+var_19C]
0x1403073ea  mov     eax, ecx
0x1403073ec  bts     eax, 19h
0x1403073f0  not     eax
0x1403073f2  and     r14d, eax
0x1403073f5  mov     [rsp+228h+arg_28], r14d
0x1403073fd  cmp     [rsp+228h+arg_30], 0
0x140307405  jnz     short loc_14030742B
0x140307407  or      [rbx+14h], ecx
0x14030740a  mov     eax, [rbx+14h]
0x14030740d  cmp     [rsp+228h+var_188], 0
0x140307415  jnz     loc_140307647
0x14030741b  mov     eax, [rsp+228h+var_19C]
0x140307422  bts     eax, 19h
0x140307426  not     eax
0x140307428  and     [rbx+10h], eax
0x14030742b  mov     rdx, [r13+0C0h]
0x140307432  add     rdx, 14h
0x140307436  mov     r8, rbx
0x140307439  mov     rcx, cs:__imp_IoFileObjectType
0x140307440  mov     rcx, [rcx]
0x140307443  call    cs:__imp_SeShouldCheckForAccessRightsFromParent
0x14030744a  nop     dword ptr [rax+rax+00h]
0x14030744f  mov     rdi, qword ptr [rsp+228h+var_128.Length]
0x140307457  test    rdi, rdi
0x14030745a  jz      short loc_140307477
0x14030745c  test    al, al
0x14030745e  jz      short loc_140307477
0x140307460  test    r12b, r12b
0x140307463  jz      loc_140307686
0x140307469  cmp     [rsp+228h+var_188], 0
0x140307471  jnz     loc_140307694
0x140307477  mov     rdi, [rsp+228h+var_170]
0x14030747f  test    sil, sil
0x140307482  jnz     short loc_1403074AD
0x140307484  mov     r14b, 1
0x140307487  jmp     loc_140307F35
0x14030748c  mov     eax, [rsp+228h+var_1B0]
0x140307490  mov     [rsp+228h+Status], eax
0x140307497  mov     [rsp+228h+var_178], eax
0x14030749e  jmp     short loc_14030742B
0x1403074a0  mov     r12, [rbx+48h]
0x1403074a4  add     r12, 58h ; 'X'
0x1403074a8  jmp     loc_140307340
0x1403074ad  mov     rcx, [rdi+30h]
0x1403074b1  lea     rdx, [rcx+58h]
0x1403074b5  mov     [rsp+228h+var_158], rdx
0x1403074bd  movzx   eax, word ptr [rdx]
0x1403074c0  test    ax, ax
0x1403074c3  setnz   r8b
0x1403074c7  mov     [rsp+228h+var_1B3], r8b
0x1403074cc  test    ax, ax
0x1403074cf  jz      loc_140307C1F
0x1403074d5  mov     r9, [rcx+40h]
0x1403074d9  test    r9, r9
0x1403074dc  jnz     loc_140307C88
0x1403074e2  mov     r14b, 1
0x1403074e5  test    r14b, r14b
0x1403074e8  jz      loc_140307D85
0x1403074ee  test    sil, sil
0x1403074f1  jz      loc_140307F35
0x1403074f7  mov     rax, [r13+50h]
0x1403074fb  add     rax, 330h
0x140307501  mov     qword ptr [rsp+228h+SourceString], rax
0x140307509  movzx   ecx, word ptr [rax]
0x14030750c  movzx   r9d, word ptr [rdx]
0x140307510  lea     eax, [rcx+4]
0x140307513  add     eax, r9d
0x140307516  test    eax, 0FFFF0000h
0x14030751b  jnz     loc_140307DD5
0x140307521  add     cx, 4
0x140307525  add     cx, r9w
0x140307529  mov     [rsp+228h+DestinationString.MaximumLength], cx
0x140307531  test    r8b, r8b
0x140307534  jz      loc_140307E4E
0x14030753a  mov     rax, [rdx+8]
0x14030753e  cmp     word ptr [rax], 5Ch ; '\'
0x140307542  jnz     loc_140307E4E
0x140307548  mov     sil, 1
0x14030754b  mov     [rsp+228h+var_1A3], sil
0x140307553  xor     dil, dil
0x140307556  movzx   edx, cx; NumberOfBytes
0x140307559  mov     ecx, cs:PoolType
0x14030755f  or      ecx, 10h; PoolType
0x140307562  mov     r8d, 53466552h; Tag
0x140307568  call    cs:__imp_ExAllocatePoolWithTag
0x14030756f  nop     dword ptr [rax+rax+00h]
0x140307574  mov     [rsp+228h+DestinationString.Buffer], rax
0x14030757c  mov     rdx, qword ptr [rsp+228h+SourceString]; SourceString
0x140307584  lea     rcx, [rsp+228h+DestinationString]; DestinationString
0x14030758c  call    cs:__imp_RtlCopyUnicodeString
0x140307593  nop     dword ptr [rax+rax+00h]
0x140307598  test    sil, sil
0x14030759b  jz      loc_140307EB8
0x1403075a1  cmp     [rsp+228h+var_1B3], 0
0x1403075a6  jnz     loc_140307F14
0x1403075ac  lea     rcx, [rbx+0Ah]
0x1403075b0  mov     r9, [r13+0C0h]
0x1403075b7  add     r9, 14h; SecurityDescriptor
0x1403075bb  mov     [rsp+228h+GenerateOnClose], rcx; GenerateOnClose
0x1403075c0  movzx   eax, [rsp+228h+var_1B8]
0x1403075c5  lea     r8, [rsp+228h+DestinationString]; AbsoluteObjectName
0x1403075cd  xor     edx, edx; Object
0x1403075cf  lea     rcx, ObjectTypeName; ObjectTypeName
0x1403075d6  mov     [rsp+228h+AccessMode], al; AccessMode
0x1403075da  mov     [rsp+228h+AccessGranted], r12b; AccessGranted
0x1403075df  mov     [rsp+228h+ObjectCreated], dl; ObjectCreated
0x1403075e3  mov     [rsp+228h+AccessState], rbx; AccessState
0x1403075e8  cmp     [rsp+228h+var_130], edx
0x1403075ef  jz      short loc_140307602
0x1403075f1  call    cs:__imp_SeOpenObjectForDeleteAuditAlarm
0x1403075f8  nop     dword ptr [rax+rax+00h]
0x1403075fd  jmp     loc_140307F35
0x140307602  call    cs:__imp_SeOpenObjectAuditAlarm
0x140307609  nop     dword ptr [rax+rax+00h]
0x14030760e  jmp     loc_140307F35
0x140307613  mov     rcx, rbx; AccessState
0x140307616  call    cs:__imp_SeAppendPrivileges
0x14030761d  nop     dword ptr [rax+rax+00h]
0x140307622  mov     rcx, [rsp+228h+Privileges]; Privileges
0x14030762a  call    cs:__imp_SeFreePrivileges
0x140307631  nop     dword ptr [rax+rax+00h]
0x140307636  mov     [rsp+228h+Privileges], 0
0x140307642  jmp     loc_1403073DA
0x140307647  bt      eax, 10h
0x14030764b  mov     edx, [rsp+228h+var_184]
0x140307652  movzx   edx, dl
0x140307655  mov     ecx, 1
0x14030765a  cmovb   edx, ecx
0x14030765d  mov     [rsp+228h+var_184], edx
0x140307664  mov     [rsp+228h+var_174], dl
0x14030766b  test    al, 80h
0x14030766d  mov     eax, [rsp+228h+var_180]
0x140307674  movzx   eax, al
0x140307677  cmovnz  eax, ecx
0x14030767a  mov     [rsp+228h+var_180], eax
0x140307681  jmp     loc_14030741B
0x140307686  test    r14d, 10080h
0x14030768d  jnz     short loc_1403076AC
0x14030768f  jmp     loc_140307469
0x140307694  cmp     byte ptr [rsp+228h+var_184], 0
0x14030769c  jz      short loc_1403076AC
0x14030769e  cmp     byte ptr [rsp+228h+var_180], 0
0x1403076a6  jnz     loc_140307477
0x1403076ac  mov     [rsp+228h+var_1B5], 0
0x1403076b1  mov     [rsp+228h+var_1B4], 0
0x1403076b6  mov     [rsp+228h+var_17C], 0
0x1403076c1  mov     [rsp+228h+var_1A0], 0
0x1403076cc  mov     [rsp+228h+var_1AC], 0
0x1403076d4  lea     rcx, [rbx+20h]; SubjectContext
0x1403076d8  call    cs:__imp_SeUnlockSubjectContext
0x1403076df  nop     dword ptr [rax+rax+00h]
0x1403076e4  mov     [rsp+228h+var_1B7], 0
0x1403076e9  mov     [rsp+228h+var_E8], rdi
0x1403076f1  mov     r8b, 1
0x1403076f4  mov     rdx, rdi
0x1403076f7  mov     rcx, [rsp+228h+var_190]
0x1403076ff  call    ?RefsAcquireResourceShared@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquireResourceShared(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x140307704  cmp     qword ptr [rdi+0C0h], 0
0x14030770c  jnz     short loc_140307739
0x14030770e  mov     [rsp+228h+var_E0], rdi
0x140307716  mov     rdx, rdi
0x140307719  mov     rcx, [rsp+228h+var_190]
0x140307721  call    ?RefsReleaseResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleaseResource(_IRP_CONTEXT *,PFCBOrSCB)
0x140307726  mov     [rsp+228h+var_D8], rdi
0x14030772e  mov     r8b, 1
0x140307731  mov     rdx, rdi
0x140307734  call    ?RefsAcquireResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquireResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x140307739  lea     rcx, [rbx+20h]; SubjectContext
0x14030773d  call    cs:__imp_SeLockSubjectContext
  ... truncated ...
```
