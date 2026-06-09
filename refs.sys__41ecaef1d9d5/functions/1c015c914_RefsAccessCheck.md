# RefsAccessCheck

- ea: `0x1c015c914`
- end: `0x1c015d63e`
- name: `RefsAccessCheck`
- size: `3370`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0154d5c`
- `0x1c015eb64`
- `0x1c016752c`
- `0x1c0179bd4`

## callees

- `0x1c00032fc`
- `0x1c0003334`
- `0x1c000f770`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c014fc14`
- `0x1c015c5ec`
- `0x1c015c914`
- `0x1c015d78c`
- `0x1c016aad0`
- `0x1c01c07a8`
- `0x1c01c563c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c015d4c7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c015d4c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017ea28`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017ea43`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c018392d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0183941`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017ea28`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017ea43`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c018392d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0183941`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c015cde6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c015d0b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017e9fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c015cde6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c015d0b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017e9fd`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c015d26c`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c015d26c`
- `ntoskrnl!IoFileObjectType` at `0x1c015ca06`
- `ntoskrnl!IoFileObjectType` at `0x1c015cbd5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c015d4eb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c015d4eb`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1c015d519`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1c015d55d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1c015d519`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1c015d55d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c015caea`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c015ce77`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c015cf82`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c015d104`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c015caea`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c015ce77`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c015cf82`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c015d104`
- `ntoskrnl!SeLockSubjectContext` at `0x1c015ca98`
- `ntoskrnl!SeLockSubjectContext` at `0x1c015ce01`
- `ntoskrnl!SeLockSubjectContext` at `0x1c015d352`
- `ntoskrnl!SeLockSubjectContext` at `0x1c015ca98`
- `ntoskrnl!SeLockSubjectContext` at `0x1c015ce01`
- `ntoskrnl!SeLockSubjectContext` at `0x1c015d352`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c015cc4b`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c015ccf9`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c015d286`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c015d300`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c015d605`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c017ea61`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c015cc4b`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c015ccf9`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c015d286`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c015d300`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c015d605`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c017ea61`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x1c015ca10`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x1c015ca10`
- `ntoskrnl!SeAuditingAnyFileEventsWithContextEx` at `0x1c015ca85`
- `ntoskrnl!SeAuditingAnyFileEventsWithContextEx` at `0x1c015ca85`
- `ntoskrnl!SeAppendPrivileges` at `0x1c015cd50`
- `ntoskrnl!SeAppendPrivileges` at `0x1c015d18b`
- `ntoskrnl!SeAppendPrivileges` at `0x1c015cd50`
- `ntoskrnl!SeAppendPrivileges` at `0x1c015d18b`
- `ntoskrnl!SeFreePrivileges` at `0x1c015cd64`
- `ntoskrnl!SeFreePrivileges` at `0x1c015ceee`
- `ntoskrnl!SeFreePrivileges` at `0x1c015cffc`
- `ntoskrnl!SeFreePrivileges` at `0x1c015d19f`
- `ntoskrnl!SeFreePrivileges` at `0x1c015cd64`
- `ntoskrnl!SeFreePrivileges` at `0x1c015ceee`
- `ntoskrnl!SeFreePrivileges` at `0x1c015cffc`
- `ntoskrnl!SeFreePrivileges` at `0x1c015d19f`
- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x1c015cbdf`
- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x1c015cbdf`
- `ntoskrnl!SeAuditingFileEventsWithContextEx` at `0x1c015d377`
- `ntoskrnl!SeAuditingFileEventsWithContextEx` at `0x1c015d377`
- `ntoskrnl!SeOpenObjectForDeleteAuditAlarm` at `0x1c015d5b7`
- `ntoskrnl!SeOpenObjectForDeleteAuditAlarm` at `0x1c015d5b7`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x1c015d5c5`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x1c015d5c5`

## pseudocode

```c
void __fastcall RefsAccessCheck(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        char a7,
        char a8,
        char a9)
{
  int v9; // r12d
  struct _ACCESS_STATE *AccessState; // rsi
  __int64 v14; // rdx
  int v15; // r14d
  BOOLEAN AccessGranted; // r15
  __int64 v17; // r8
  __int16 v18; // r9
  struct _ACCESS_STATE *v19; // rdi
  __int64 v20; // rbx
  PGENERIC_MAPPING FileObjectGenericMapping; // rax
  int *v22; // rcx
  __int64 v23; // rdi
  int v24; // r9d
  int v25; // ebx
  int v26; // eax
  char v27; // al
  char v28; // r12
  char v29; // dl
  __int64 v30; // r13
  __int64 v31; // rcx
  UNICODE_STRING *v32; // rbx
  bool v33; // di
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectSecurityContext; // r12
  char v35; // r14
  __int64 v36; // r13
  char v37; // di
  __int64 v38; // r8
  __int64 v39; // rcx
  struct _ERESOURCE *v40; // rcx
  bool v41; // zf
  int v42; // eax
  __int64 v43; // r8
  __int64 v44; // rcx
  PPRIVILEGE_SET v45; // rcx
  int v46; // eax
  __int64 v47; // rdi
  PGENERIC_MAPPING v48; // rax
  unsigned int *v49; // rcx
  int v50; // r9d
  char v51; // bl
  void *v52; // rdi
  PGENERIC_MAPPING v53; // rax
  unsigned int *v54; // rcx
  int v55; // r9d
  char v56; // bl
  int v57; // r8d
  struct _ERESOURCE *v58; // rcx
  __int64 v59; // rdi
  __int64 v60; // rbx
  PGENERIC_MAPPING v61; // rax
  int *v62; // rcx
  int v63; // r9d
  unsigned int v64; // ecx
  __int64 v65; // rcx
  __int64 v66; // rax
  BOOLEAN IsResourceAcquiredExclusiveLite; // al
  struct _SECURITY_SUBJECT_CONTEXT *v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  const UNICODE_STRING *v71; // r12
  int Length; // edx
  int v73; // r8d
  USHORT v74; // dx
  char v75; // r14
  __int64 v76; // rcx
  PCUNICODE_STRING v77; // rax
  char v78; // cl
  PCUNICODE_STRING v79; // r14
  void *v80; // r9
  unsigned __int8 *GenerateOnClose; // [rsp+40h] [rbp-1A8h]
  __int64 v82; // [rsp+68h] [rbp-180h]
  __int64 v83; // [rsp+68h] [rbp-180h]
  char v84; // [rsp+70h] [rbp-178h]
  char v85; // [rsp+71h] [rbp-177h]
  KPROCESSOR_MODE AccessMode; // [rsp+72h] [rbp-176h]
  char v87; // [rsp+74h] [rbp-174h]
  char v88; // [rsp+76h] [rbp-172h]
  NTSTATUS v89; // [rsp+78h] [rbp-170h] BYREF
  unsigned int v90; // [rsp+7Ch] [rbp-16Ch] BYREF
  int v91; // [rsp+80h] [rbp-168h] BYREF
  char v92; // [rsp+84h] [rbp-164h]
  char v93; // [rsp+85h] [rbp-163h]
  NTSTATUS Status; // [rsp+88h] [rbp-160h]
  unsigned int v95; // [rsp+8Ch] [rbp-15Ch] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+90h] [rbp-158h] BYREF
  int v97; // [rsp+98h] [rbp-150h]
  __int64 v98; // [rsp+A0h] [rbp-148h]
  int v99; // [rsp+A8h] [rbp-140h]
  char v100; // [rsp+ACh] [rbp-13Ch]
  char v101; // [rsp+ADh] [rbp-13Bh]
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-138h] BYREF
  __int64 v103; // [rsp+C0h] [rbp-128h]
  int v104; // [rsp+C8h] [rbp-120h]
  int v105; // [rsp+CCh] [rbp-11Ch]
  UNICODE_STRING v106; // [rsp+D0h] [rbp-118h] BYREF
  int v107; // [rsp+E0h] [rbp-108h]
  __int64 v108; // [rsp+E8h] [rbp-100h]
  PCUNICODE_STRING Source; // [rsp+F0h] [rbp-F8h]
  UNICODE_STRING *v110; // [rsp+F8h] [rbp-F0h]
  __int64 v111; // [rsp+100h] [rbp-E8h]
  PSECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+108h] [rbp-E0h]
  struct _ACCESS_STATE *v113; // [rsp+110h] [rbp-D8h]
  __int64 v114; // [rsp+118h] [rbp-D0h]
  _BYTE v115[128]; // [rsp+120h] [rbp-C8h] BYREF

  v98 = a3;
  v103 = a1;
  v111 = a4;
  v89 = 0;
  Status = 0;
  v91 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  v88 = 0;
  memset(v115, 0, sizeof(v115));
  v108 = *(_QWORD *)(a5 + 184);
  AccessState = *(struct _ACCESS_STATE **)(*(_QWORD *)(v108 + 8) + 8LL);
  v113 = AccessState;
  v14 = *(_QWORD *)(a3 + 184);
  if ( !v14 )
  {
    RefsLoadSecurityDescriptor(a1, a3);
    v14 = *(_QWORD *)(a3 + 184);
  }
  Privileges = 0;
  Source = 0;
  LOBYTE(v9) = 0;
  v104 = v9;
  LOBYTE(v99) = 0;
  DestinationString.Buffer = 0;
  v106 = 0;
  SeAdjustAccessStateForAccessConstraints(IoFileObjectType, v14 + 20, AccessState);
  v15 = a6 & ~AccessState->PreviouslyGrantedAccess;
  AccessGranted = v15 == 0;
  v97 = v15 & 0x2000000;
  v107 = *(_DWORD *)(*(_QWORD *)(v108 + 8) + 20LL) & 0x1000;
  AccessMode = RefsEffectiveMode(a5, v108, v17);
  SubjectContext = &AccessState->SubjectSecurityContext;
  v85 = SeAuditingAnyFileEventsWithContextEx(*(_QWORD *)(a3 + 184) + 20LL, &AccessState->SubjectSecurityContext, 0);
  SeLockSubjectContext(&AccessState->SubjectSecurityContext);
  v84 = 1;
  v18 = 0;
  if ( !v15 )
    goto LABEL_15;
  v19 = 0;
  if ( !a9 )
    v19 = AccessState;
  if ( v85 )
    v20 = (__int64)AccessState->AuxData + 88;
  else
    v20 = 0;
  v92 = a8 != 0;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  v82 = (__int64)v19;
  v22 = &v91;
  LOBYTE(v22) = AccessMode;
  v23 = v98;
  AccessGranted = AccessCheck(
                    (_DWORD)v22,
                    v98,
                    (int)AccessState + 32,
                    v24,
                    a8 != 0,
                    v15,
                    AccessState->PreviouslyGrantedAccess,
                    (__int64)&Privileges,
                    (__int64)FileObjectGenericMapping,
                    AccessMode,
                    (__int64)&v91,
                    v20,
                    (__int64)&v89,
                    v82);
  if ( Privileges )
  {
    SeAppendPrivileges(AccessState, Privileges);
    SeFreePrivileges(Privileges);
    Privileges = 0;
  }
  if ( AccessGranted )
  {
    v15 &= ~(v91 | 0x2000000);
    v25 = v97;
    if ( !a7 )
    {
      v26 = v91 | AccessState->PreviouslyGrantedAccess;
      AccessState->PreviouslyGrantedAccess = v26;
      if ( v25 )
      {
        LOBYTE(v9) = (v26 & 0x10000) != 0;
        v104 = (unsigned __int8)v9;
        v100 = v9;
        v41 = (v26 & 0x80u) == 0;
        v42 = (unsigned __int8)v99;
        if ( !v41 )
          v42 = 1;
        v99 = v42;
      }
      AccessState->RemainingDesiredAccess &= ~(v91 | 0x2000000);
    }
  }
  else
  {
    Status = v89;
    v25 = v97;
  }
  if ( (v27 = SeShouldCheckForAccessRightsFromParent(IoFileObjectType, *(_QWORD *)(v23 + 184) + 20LL, AccessState),
        v18 = 0,
        !a4)
    || !v27
    || (AccessGranted || (v15 & 0x10080) == 0) && (!v25 || (_BYTE)v9 && (_BYTE)v99) )
  {
LABEL_15:
    v28 = 1;
    goto LABEL_16;
  }
  v87 = 0;
  v37 = 0;
  v105 = 0;
  v90 = 0;
  v95 = 0;
  SeUnlockSubjectContext(&AccessState->SubjectSecurityContext);
  LOBYTE(v38) = 1;
  RefsAcquireResourceShared(v39, a4, v38);
  if ( !*(_QWORD *)(a4 + 184) )
  {
    if ( *(_WORD *)a4 == 2050 )
      v40 = (struct _ERESOURCE *)(*(_QWORD *)(a4 + 96) + 64LL);
    else
      v40 = *(struct _ERESOURCE **)(a4 + 8);
    ExReleaseResourceLite(v40);
    LOBYTE(v43) = 1;
    RefsAcquireResourceExclusive(v44, a4, v43);
  }
  SeLockSubjectContext(&AccessState->SubjectSecurityContext);
  v28 = 1;
  v84 = 1;
  v45 = 0;
  if ( !*(_QWORD *)(a4 + 184) )
  {
    RefsLoadSecurityDescriptor(v103, a4);
    v45 = 0;
  }
  if ( (v15 & 0x10000) != 0 || (v46 = v97) != 0 && !(_BYTE)v104 )
  {
    v47 = 0;
    if ( !a9 )
      v47 = (__int64)AccessState;
    v48 = IoGetFileObjectGenericMapping();
    v49 = &v90;
    LOBYTE(v49) = AccessMode;
    v51 = AccessCheck(
            (_DWORD)v49,
            a4,
            (int)AccessState + 32,
            v50,
            1,
            64,
            0,
            (__int64)&Privileges,
            (__int64)v48,
            AccessMode,
            (__int64)&v90,
            (unsigned __int64)v115 & -(__int64)(v85 != 0),
            (__int64)&v89,
            v47);
    v87 = 1;
    v45 = Privileges;
    if ( Privileges )
    {
      SeFreePrivileges(Privileges);
      v45 = 0;
      Privileges = 0;
    }
    if ( v51 )
    {
      v90 = v90 & 0xFFFEFFBF | 0x10000;
      v15 &= ~0x10000u;
    }
    else
    {
      Status = v89;
    }
    v46 = v97;
    v37 = 0;
  }
  if ( (v15 & 0x80u) != 0 || v46 && (_BYTE)v99 == (_BYTE)v45 )
  {
    v52 = v45;
    if ( a9 == (_BYTE)v45 )
      v52 = AccessState;
    v53 = IoGetFileObjectGenericMapping();
    v83 = (__int64)v52;
    v54 = &v95;
    LOBYTE(v54) = AccessMode;
    v37 = 1;
    v56 = AccessCheck(
            (_DWORD)v54,
            a4,
            (int)AccessState + 32,
            v55,
            1,
            1,
            0,
            (__int64)&Privileges,
            (__int64)v53,
            AccessMode,
            (__int64)&v95,
            (unsigned __int64)v115 & -(__int64)(v85 != 0),
            (__int64)&v89,
            v83);
    LODWORD(v45) = (_DWORD)Privileges;
    if ( Privileges )
    {
      SeFreePrivileges(Privileges);
      LODWORD(v45) = 0;
      Privileges = 0;
    }
    if ( v56 )
    {
      v95 = v95 & 0xFFFFFF7E | 0x80;
      v15 &= ~0x80u;
    }
    else
    {
      Status = v89;
    }
  }
  if ( v85 && (v37 || v87) )
  {
    v57 = (int)v45;
    if ( v37 )
      v57 = 128;
    v105 = v57;
    if ( v87 )
      v105 = v57 | 0x10000;
    RefsUpdateAccessReasonSourceToParentSD(AccessState, v115);
  }
  if ( *(_WORD *)a4 == 2050 )
    v58 = (struct _ERESOURCE *)(*(_QWORD *)(a4 + 96) + 64LL);
  else
    v58 = *(struct _ERESOURCE **)(a4 + 8);
  ExReleaseResourceLite(v58);
  v18 = 0;
  if ( v15 )
  {
    v59 = 0;
    if ( !a9 )
      v59 = (__int64)AccessState;
    if ( v85 )
      v60 = (__int64)AccessState->AuxData + 88;
    else
      v60 = 0;
    v61 = IoGetFileObjectGenericMapping();
    v62 = &v91;
    LOBYTE(v62) = AccessMode;
    AccessGranted = AccessCheck(
                      (_DWORD)v62,
                      v98,
                      (int)AccessState + 32,
                      v63,
                      v92,
                      v15,
                      0,
                      (__int64)&Privileges,
                      (__int64)v61,
                      AccessMode,
                      (__int64)&v91,
                      v60,
                      (__int64)&v89,
                      v59);
    v18 = 0;
    if ( Privileges )
    {
      SeAppendPrivileges(AccessState, Privileges);
      SeFreePrivileges(Privileges);
      v18 = 0;
      Privileges = 0;
    }
    if ( AccessGranted )
      goto LABEL_88;
    Status = v89;
    if ( v15 != 0x2000000 || !v95 && !v90 )
      goto LABEL_88;
    v91 = 0;
    goto LABEL_87;
  }
  if ( v95 || v90 )
LABEL_87:
    AccessGranted = 1;
LABEL_88:
  if ( !a7 && AccessGranted )
  {
    v64 = v95;
    AccessState->PreviouslyGrantedAccess |= v91 | v90 | v95;
    AccessState->RemainingDesiredAccess &= ~(v91 | v90 | v64 | 0x2000000);
  }
LABEL_16:
  v29 = v85;
  if ( v85 )
  {
    v30 = v108;
    v31 = *(_QWORD *)(v108 + 48);
    v32 = (UNICODE_STRING *)(v31 + 88);
    v110 = (UNICODE_STRING *)(v31 + 88);
    v33 = *(_WORD *)(v31 + 88) != 0;
    if ( *(_WORD *)(v31 + 88) || (*(_DWORD *)(v108 + 16) & 0x2000) == 0 )
    {
      v65 = *(_QWORD *)(v31 + 64);
      if ( v65 && (v66 = *(_QWORD *)(v65 + 32)) != 0 && (*(_DWORD *)(v66 + 4) & 8) != 0 )
      {
        IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v65 + 24) + 120LL) + 96LL)
                                                                                       + 64LL));
        v35 = 0;
        p_SubjectSecurityContext = &AccessState->SubjectSecurityContext;
        v68 = &AccessState->SubjectSecurityContext;
        if ( IsResourceAcquiredExclusiveLite )
        {
          SeUnlockSubjectContext(v68);
          v84 = 0;
          RefsBuildNormalizedNameImplementation(
            v103,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v30 + 48) + 64LL) + 24LL) + 120LL),
            0,
            &v106);
          v18 = 0;
          if ( v33 )
          {
            RefsAppendNameToParent(v69, &v106, v32, 0);
            v18 = 0;
          }
          v36 = v98;
        }
        else
        {
          SeUnlockSubjectContext(v68);
          v84 = 0;
          v36 = v98;
          RefsBuildNormalizedNameImplementation(v103, v98, 0, &v106);
          v18 = 0;
        }
        v33 = 1;
        v32 = &v106;
        v110 = &v106;
        v29 = v85;
      }
      else
      {
        v35 = 1;
        v36 = v98;
        p_SubjectSecurityContext = &AccessState->SubjectSecurityContext;
      }
    }
    else
    {
      p_SubjectSecurityContext = &AccessState->SubjectSecurityContext;
      SeUnlockSubjectContext(&AccessState->SubjectSecurityContext);
      v35 = 0;
      v84 = 0;
      v36 = v98;
      RefsBuildNormalizedNameImplementation(v103, v98, 0, &v106);
      v33 = 1;
      v32 = &v106;
      v110 = &v106;
      v29 = v85;
      v18 = 0;
    }
    if ( !v35 )
    {
      SeLockSubjectContext(p_SubjectSecurityContext);
      v84 = 1;
      LOBYTE(v70) = AccessGranted;
      v29 = SeAuditingFileEventsWithContextEx(v70, *(_QWORD *)(v36 + 184) + 20LL, p_SubjectSecurityContext, 0);
      v18 = 0;
    }
    if ( v29 )
    {
      v71 = *(const UNICODE_STRING **)(v36 + 88);
      Length = v71[43].Length;
      v73 = v32->Length;
      if ( ((v73 + Length + 4) & 0xFFFF0000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_838d735f45793e0c3968f803c105c9c3_Traceguids,
            3221225523LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741773);
        RefsRaiseStatusInternal(v103, 3221225523LL);
      }
      v74 = v73 + Length + 4;
      DestinationString.MaximumLength = v74;
      if ( v33 && *v32->Buffer == 92 )
      {
        v75 = 1;
        v93 = 1;
      }
      else
      {
        v75 = v18;
        v93 = v18;
        v76 = *(_QWORD *)(*(_QWORD *)(v108 + 48) + 64LL);
        if ( v76 )
        {
          v77 = (PCUNICODE_STRING)(v76 + 88);
          Source = (PCUNICODE_STRING)(v76 + 88);
          v114 = v76 + 88;
        }
        else
        {
          v77 = Source;
        }
        if ( !v77 || (v78 = 1, v77->Length == v18) )
          v78 = v18;
        v88 = v78;
        v101 = v78;
        if ( v78 )
        {
          v74 += v77->Length;
          DestinationString.MaximumLength = v74;
        }
      }
      DestinationString.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)17, v74, 0x53466552u);
      RtlCopyUnicodeString(&DestinationString, v71 + 43);
      if ( !v75 )
      {
        if ( v88 )
        {
          v79 = Source;
          RtlAppendUnicodeStringToString(&DestinationString, Source);
          if ( v79->Length != 2 )
          {
            DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 92;
            DestinationString.Length += 2;
          }
        }
      }
      if ( v33 )
        RtlAppendUnicodeStringToString(&DestinationString, v32);
      v80 = (void *)(*(_QWORD *)(v98 + 184) + 20LL);
      GenerateOnClose = &AccessState->GenerateOnClose;
      if ( v107 )
        SeOpenObjectForDeleteAuditAlarm(
          (PUNICODE_STRING)&FileString,
          0,
          &DestinationString,
          v80,
          AccessState,
          0,
          AccessGranted,
          AccessMode,
          GenerateOnClose);
      else
        SeOpenObjectAuditAlarm(
          (PUNICODE_STRING)&FileString,
          0,
          &DestinationString,
          v80,
          AccessState,
          0,
          AccessGranted,
          AccessMode,
          GenerateOnClose);
    }
    v28 = v84;
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( v106.Buffer )
    ExFreePoolWithTag(v106.Buffer, 0);
  if ( v28 )
    SeUnlockSubjectContext(SubjectContext);
  if ( !AccessGranted )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_838d735f45793e0c3968f803c105c9c3_Traceguids,
        (unsigned int)Status);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsRaiseStatusInternal(v103, (unsigned int)Status);
    JUMPOUT(0x1C01839CALL);
  }
}

```

## disassembly

```asm
0x1c015c914  mov     r11, rsp
0x1c015c917  push    rbx
0x1c015c918  push    rsi
0x1c015c919  push    rdi
0x1c015c91a  push    r12
0x1c015c91c  push    r13
0x1c015c91e  push    r14
0x1c015c920  push    r15
0x1c015c922  sub     rsp, 1B0h
0x1c015c929  mov     rax, cs:__security_cookie
0x1c015c930  xor     rax, rsp
0x1c015c933  mov     [rsp+1E8h+var_48], rax
0x1c015c93b  mov     r13, r9
0x1c015c93e  mov     rdi, r8
0x1c015c941  mov     [rsp+1E8h+var_148], r8
0x1c015c949  mov     r14, rcx
0x1c015c94c  mov     [rsp+1E8h+var_128], rcx
0x1c015c954  mov     [rsp+1E8h+var_E8], r9
0x1c015c95c  mov     rbx, [rsp+1E8h+arg_20]
0x1c015c964  xor     r15d, r15d
0x1c015c967  mov     [rsp+1E8h+var_170], r15d
0x1c015c96c  mov     [r11-160h], r15d
0x1c015c973  mov     [r11-168h], r15d
0x1c015c97a  mov     [r11-138h], r15
0x1c015c981  mov     [rsp+1E8h+var_172], r15b
0x1c015c986  xor     edx, edx; Val
0x1c015c988  mov     r8d, 80h; Size
0x1c015c98e  lea     rcx, [r11-0C8h]; void *
0x1c015c995  call    memset
0x1c015c99a  mov     rax, [rbx+0B8h]
0x1c015c9a1  mov     [rsp+1E8h+var_100], rax
0x1c015c9a9  mov     rax, [rax+8]
0x1c015c9ad  mov     rsi, [rax+8]
0x1c015c9b1  mov     [rsp+1E8h+var_D8], rsi
0x1c015c9b9  mov     rdx, [rdi+0B8h]
0x1c015c9c0  test    rdx, rdx
0x1c015c9c3  jz      loc_1C0183914
0x1c015c9c9  mov     [rsp+1E8h+Privileges], r15
0x1c015c9d1  mov     [rsp+1E8h+Source], r15
0x1c015c9d9  mov     r12b, r15b
0x1c015c9dc  mov     [rsp+1E8h+var_120], r12d
0x1c015c9e4  mov     byte ptr [rsp+1E8h+var_140], r15b
0x1c015c9ec  mov     [rsp+1E8h+DestinationString.Buffer], r15
0x1c015c9f4  xorps   xmm0, xmm0
0x1c015c9f7  movups  xmmword ptr [rsp+1E8h+var_118.Length], xmm0
0x1c015c9ff  add     rdx, 14h
0x1c015ca03  mov     r8, rsi
0x1c015ca06  mov     rcx, cs:__imp_IoFileObjectType
0x1c015ca0d  mov     rcx, [rcx]
0x1c015ca10  call    cs:__imp_SeAdjustAccessStateForAccessConstraints
0x1c015ca17  nop     dword ptr [rax+rax+00h]
0x1c015ca1c  mov     r14d, [rsi+14h]
0x1c015ca20  not     r14d
0x1c015ca23  and     r14d, [rsp+1E8h+arg_28]
0x1c015ca2b  setz    r15b
0x1c015ca2f  mov     eax, r14d
0x1c015ca32  and     eax, 2000000h
0x1c015ca37  mov     [rsp+1E8h+var_150], eax
0x1c015ca3e  mov     rcx, [rsp+1E8h+var_100]
0x1c015ca46  mov     rax, [rcx+8]
0x1c015ca4a  mov     eax, [rax+14h]
0x1c015ca4d  and     eax, 1000h
0x1c015ca52  mov     [rsp+1E8h+var_108], eax
0x1c015ca59  mov     rdx, rcx
0x1c015ca5c  mov     rcx, rbx
0x1c015ca5f  call    RefsEffectiveMode
0x1c015ca64  mov     [rsp+1E8h+var_176], al
0x1c015ca68  lea     rbx, [rsi+20h]
0x1c015ca6c  mov     [rsp+1E8h+SubjectContext], rbx
0x1c015ca74  mov     rcx, [rdi+0B8h]
0x1c015ca7b  add     rcx, 14h
0x1c015ca7f  xor     r8d, r8d
0x1c015ca82  mov     rdx, rbx
0x1c015ca85  call    cs:__imp_SeAuditingAnyFileEventsWithContextEx
0x1c015ca8c  nop     dword ptr [rax+rax+00h]
0x1c015ca91  mov     [rsp+1E8h+var_177], al
0x1c015ca95  mov     rcx, rbx; SubjectContext
0x1c015ca98  call    cs:__imp_SeLockSubjectContext
0x1c015ca9f  nop     dword ptr [rax+rax+00h]
0x1c015caa4  mov     eax, 1
0x1c015caa9  mov     [rsp+1E8h+var_178], al
0x1c015caad  xor     r9d, r9d
0x1c015cab0  test    r14d, r14d
0x1c015cab3  jz      loc_1C015CBF7
0x1c015cab9  mov     edi, r9d
0x1c015cabc  cmp     [rsp+1E8h+arg_40], r9b
0x1c015cac4  cmovz   rdi, rsi
0x1c015cac8  cmp     [rsp+1E8h+var_177], r9b
0x1c015cacd  jnz     loc_1C015CD40
0x1c015cad3  mov     ebx, r9d
0x1c015cad6  cmp     [rsp+1E8h+arg_38], r9b
0x1c015cade  setnz   r15b
0x1c015cae2  mov     [rsp+1E8h+var_164], r15b
0x1c015caea  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c015caf1  nop     dword ptr [rax+rax+00h]
0x1c015caf6  mov     [rsp+1E8h+var_180], rdi
0x1c015cafb  lea     rcx, [rsp+1E8h+var_170]
0x1c015cb00  mov     [rsp+1E8h+var_188], rcx
0x1c015cb05  mov     [rsp+1E8h+var_190], rbx
0x1c015cb0a  lea     rcx, [rsp+1E8h+var_168]
0x1c015cb12  mov     [rsp+1E8h+var_198], rcx
0x1c015cb17  mov     cl, [rsp+1E8h+var_176]
0x1c015cb1b  mov     [rsp+1E8h+var_1A0], cl
0x1c015cb1f  mov     [rsp+1E8h+GenerateOnClose], rax
0x1c015cb24  lea     rax, [rsp+1E8h+Privileges]
0x1c015cb2c  mov     qword ptr [rsp+1E8h+AccessMode], rax
0x1c015cb31  mov     eax, [rsi+14h]
0x1c015cb34  mov     dword ptr [rsp+1E8h+AccessGranted], eax
0x1c015cb38  mov     dword ptr [rsp+1E8h+ObjectCreated], r14d
0x1c015cb3d  mov     byte ptr [rsp+1E8h+AccessState], r15b
0x1c015cb42  lea     r8, [rsi+20h]
0x1c015cb46  mov     rdi, [rsp+1E8h+var_148]
0x1c015cb4e  mov     rdx, rdi
0x1c015cb51  call    AccessCheck
0x1c015cb56  mov     r15b, al
0x1c015cb59  mov     [rsp+1E8h+var_173], al
0x1c015cb5d  mov     rdx, [rsp+1E8h+Privileges]; Privileges
0x1c015cb65  xor     ebx, ebx
0x1c015cb67  test    rdx, rdx
0x1c015cb6a  jnz     loc_1C015CD4D
0x1c015cb70  test    r15b, r15b
0x1c015cb73  jz      loc_1C015CDB9
0x1c015cb79  mov     eax, [rsp+1E8h+var_168]
0x1c015cb80  mov     edx, 2000000h
0x1c015cb85  or      eax, edx
0x1c015cb87  not     eax
0x1c015cb89  and     r14d, eax
0x1c015cb8c  mov     [rsp+1E8h+arg_28], r14d
0x1c015cb94  cmp     [rsp+1E8h+arg_30], bl
0x1c015cb9b  mov     ebx, [rsp+1E8h+var_150]
0x1c015cba2  jnz     short loc_1C015CBC7
0x1c015cba4  mov     eax, [rsi+14h]
0x1c015cba7  or      eax, [rsp+1E8h+var_168]
0x1c015cbae  mov     [rsi+14h], eax
0x1c015cbb1  test    ebx, ebx
0x1c015cbb3  jnz     loc_1C015CD7D
0x1c015cbb9  mov     eax, [rsp+1E8h+var_168]
0x1c015cbc0  or      eax, edx
0x1c015cbc2  not     eax
0x1c015cbc4  and     [rsi+10h], eax
0x1c015cbc7  mov     rdx, [rdi+0B8h]
0x1c015cbce  add     rdx, 14h
0x1c015cbd2  mov     r8, rsi
0x1c015cbd5  mov     rcx, cs:__imp_IoFileObjectType
0x1c015cbdc  mov     rcx, [rcx]
0x1c015cbdf  call    cs:__imp_SeShouldCheckForAccessRightsFromParent
0x1c015cbe6  nop     dword ptr [rax+rax+00h]
0x1c015cbeb  xor     r9d, r9d
0x1c015cbee  test    r13, r13
0x1c015cbf1  jnz     loc_1C015CCA7
0x1c015cbf7  mov     r12b, [rsp+1E8h+var_178]
0x1c015cbfc  mov     dl, [rsp+1E8h+var_177]
0x1c015cc00  test    dl, dl
0x1c015cc02  jz      loc_1C015D5D6
0x1c015cc08  mov     r13, [rsp+1E8h+var_100]
0x1c015cc10  mov     rcx, [r13+30h]
0x1c015cc14  lea     rbx, [rcx+58h]
0x1c015cc18  mov     [rsp+1E8h+var_F0], rbx
0x1c015cc20  cmp     [rbx], r9w
0x1c015cc24  setnz   dil
0x1c015cc28  mov     [rsp+1E8h+var_171], dil
0x1c015cc2d  test    dil, dil
0x1c015cc30  jnz     loc_1C015D237
0x1c015cc36  test    dword ptr [r13+10h], 2000h
0x1c015cc3e  jz      loc_1C015D237
0x1c015cc44  lea     r12, [rsi+20h]
0x1c015cc48  mov     rcx, r12; SubjectContext
0x1c015cc4b  call    cs:__imp_SeUnlockSubjectContext
0x1c015cc52  nop     dword ptr [rax+rax+00h]
0x1c015cc57  xor     eax, eax
0x1c015cc59  mov     r14b, al
0x1c015cc5c  mov     [rsp+1E8h+var_178], al
0x1c015cc60  lea     r9, [rsp+1E8h+var_118]
0x1c015cc68  xor     r8d, r8d
0x1c015cc6b  mov     r13, [rsp+1E8h+var_148]
0x1c015cc73  mov     rdx, r13
0x1c015cc76  mov     rcx, [rsp+1E8h+var_128]
0x1c015cc7e  call    RefsBuildNormalizedNameImplementation
0x1c015cc83  mov     dil, 1
0x1c015cc86  mov     [rsp+1E8h+var_171], dil
0x1c015cc8b  lea     rbx, [rsp+1E8h+var_118]
0x1c015cc93  mov     [rsp+1E8h+var_F0], rbx
0x1c015cc9b  mov     dl, [rsp+1E8h+var_177]
0x1c015cc9f  xor     r9d, r9d
0x1c015cca2  jmp     loc_1C015D34A
0x1c015cca7  test    al, al
0x1c015cca9  jz      loc_1C015CBF7
0x1c015ccaf  test    r15b, r15b
0x1c015ccb2  jz      loc_1C015CDD0
0x1c015ccb8  test    ebx, ebx
0x1c015ccba  jz      loc_1C015CBF7
0x1c015ccc0  test    r12b, r12b
0x1c015ccc3  jz      short loc_1C015CCD3
0x1c015ccc5  cmp     byte ptr [rsp+1E8h+var_140], r9b
0x1c015cccd  jnz     loc_1C015CBF7
0x1c015ccd3  mov     [rsp+1E8h+var_174], r9b
0x1c015ccd8  mov     dil, r9b
0x1c015ccdb  mov     [rsp+1E8h+var_175], r9b
0x1c015cce0  mov     [rsp+1E8h+var_11C], r9d
0x1c015cce8  mov     [rsp+1E8h+var_16C], r9d
0x1c015cced  mov     [rsp+1E8h+var_15C], r9d
0x1c015ccf5  lea     rcx, [rsi+20h]; SubjectContext
0x1c015ccf9  call    cs:__imp_SeUnlockSubjectContext
0x1c015cd00  nop     dword ptr [rax+rax+00h]
0x1c015cd05  xor     ebx, ebx
0x1c015cd07  mov     [rsp+1E8h+var_178], bl
0x1c015cd0b  mov     r8b, 1
0x1c015cd0e  mov     rdx, r13
0x1c015cd11  call    RefsAcquireResourceShared
0x1c015cd16  cmp     [r13+0B8h], rbx
0x1c015cd1d  jnz     loc_1C015CDFD
0x1c015cd23  mov     ebx, 802h
0x1c015cd28  cmp     bx, [r13+0]
0x1c015cd2d  jnz     loc_1C015CDE2
0x1c015cd33  mov     rcx, [r13+60h]
0x1c015cd37  add     rcx, 40h ; '@'
0x1c015cd3b  jmp     loc_1C015CDE6
0x1c015cd40  mov     rbx, [rsi+48h]
0x1c015cd44  add     rbx, 58h ; 'X'
0x1c015cd48  jmp     loc_1C015CAD6
0x1c015cd4d  mov     rcx, rsi; AccessState
0x1c015cd50  call    cs:__imp_SeAppendPrivileges
0x1c015cd57  nop     dword ptr [rax+rax+00h]
0x1c015cd5c  mov     rcx, [rsp+1E8h+Privileges]; Privileges
0x1c015cd64  call    cs:__imp_SeFreePrivileges
0x1c015cd6b  nop     dword ptr [rax+rax+00h]
0x1c015cd70  mov     [rsp+1E8h+Privileges], rbx
0x1c015cd78  jmp     loc_1C015CB70
0x1c015cd7d  bt      eax, 10h
0x1c015cd81  movzx   r12d, r12b
0x1c015cd85  mov     ecx, 1
0x1c015cd8a  cmovb   r12d, ecx
0x1c015cd8e  mov     [rsp+1E8h+var_120], r12d
0x1c015cd96  mov     [rsp+1E8h+var_13C], r12b
0x1c015cd9e  test    al, 80h
0x1c015cda0  mov     eax, [rsp+1E8h+var_140]
0x1c015cda7  movzx   eax, al
0x1c015cdaa  cmovnz  eax, ecx
0x1c015cdad  mov     [rsp+1E8h+var_140], eax
0x1c015cdb4  jmp     loc_1C015CBB9
0x1c015cdb9  mov     eax, [rsp+1E8h+var_170]
0x1c015cdbd  mov     [rsp+1E8h+Status], eax
0x1c015cdc4  mov     ebx, [rsp+1E8h+var_150]
0x1c015cdcb  jmp     loc_1C015CBC7
0x1c015cdd0  test    r14d, 10080h
0x1c015cdd7  jnz     loc_1C015CCD3
0x1c015cddd  jmp     loc_1C015CCB8
0x1c015cde2  mov     rcx, [r13+8]; Resource
0x1c015cde6  call    cs:__imp_ExReleaseResourceLite
0x1c015cded  nop     dword ptr [rax+rax+00h]
0x1c015cdf2  mov     r8b, 1
0x1c015cdf5  mov     rdx, r13
0x1c015cdf8  call    RefsAcquireResourceExclusive
0x1c015cdfd  lea     rcx, [rsi+20h]; SubjectContext
0x1c015ce01  call    cs:__imp_SeLockSubjectContext
0x1c015ce08  nop     dword ptr [rax+rax+00h]
0x1c015ce0d  mov     r12b, 1
0x1c015ce10  mov     [rsp+1E8h+var_178], r12b
0x1c015ce15  xor     ecx, ecx
0x1c015ce17  cmp     [r13+0B8h], rcx
0x1c015ce1e  jnz     short loc_1C015CE32
0x1c015ce20  mov     rdx, r13
0x1c015ce23  mov     rcx, [rsp+1E8h+var_128]
0x1c015ce2b  call    RefsLoadSecurityDescriptor
0x1c015ce30  xor     ecx, ecx
0x1c015ce32  bt      r14d, 10h
0x1c015ce37  jb      short loc_1C015CE55
0x1c015ce39  mov     eax, [rsp+1E8h+var_150]
0x1c015ce40  test    eax, eax
0x1c015ce42  jz      loc_1C015CF41
0x1c015ce48  cmp     byte ptr [rsp+1E8h+var_120], cl
0x1c015ce4f  jnz     loc_1C015CF41
0x1c015ce55  mov     rdi, rcx
0x1c015ce58  cmp     [rsp+1E8h+arg_40], cl
0x1c015ce5f  cmovz   rdi, rsi
0x1c015ce63  mov     al, [rsp+1E8h+var_177]
0x1c015ce67  neg     al
0x1c015ce69  sbb     rbx, rbx
0x1c015ce6c  lea     rax, [rsp+1E8h+var_C8]
0x1c015ce74  and     rbx, rax
0x1c015ce77  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c015ce7e  nop     dword ptr [rax+rax+00h]
0x1c015ce83  mov     [rsp+1E8h+var_180], rdi
0x1c015ce88  lea     rcx, [rsp+1E8h+var_170]
0x1c015ce8d  mov     [rsp+1E8h+var_188], rcx
0x1c015ce92  mov     [rsp+1E8h+var_190], rbx
0x1c015ce97  lea     rcx, [rsp+1E8h+var_16C]
0x1c015ce9c  mov     [rsp+1E8h+var_198], rcx
0x1c015cea1  mov     cl, [rsp+1E8h+var_176]
0x1c015cea5  mov     [rsp+1E8h+var_1A0], cl
0x1c015cea9  mov     [rsp+1E8h+GenerateOnClose], rax
0x1c015ceae  lea     rax, [rsp+1E8h+Privileges]
0x1c015ceb6  mov     qword ptr [rsp+1E8h+AccessMode], rax
0x1c015cebb  xor     edi, edi
0x1c015cebd  mov     dword ptr [rsp+1E8h+AccessGranted], edi
0x1c015cec1  mov     dword ptr [rsp+1E8h+ObjectCreated], 40h ; '@'
0x1c015cec9  mov     byte ptr [rsp+1E8h+AccessState], 1
0x1c015cece  lea     r8, [rsi+20h]
0x1c015ced2  mov     rdx, r13
0x1c015ced5  call    AccessCheck
  ... truncated ...
```
