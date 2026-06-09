# NpCreateClientEnd

- ea: `0x1400127f0`
- end: `0x1400131da`
- name: `NpCreateClientEnd`
- size: `2538`
- prototype: `int *__fastcall(int *AccessStatus, __int64, __int64, ACCESS_MASK, struct _ACCESS_STATE *, PACCESS_STATE AccessState, char, KPROCESSOR_MODE AccessMode, PETHREAD Thread, const char *, DWORD GrantedAccess, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140011490`

## callees

- `0x140001de6`
- `0x140010068`
- `0x1400127f0`
- `0x140013ec0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140012c3c`
- `ntoskrnl!ExAllocatePool2` at `0x140012cab`
- `ntoskrnl!ExAllocatePool2` at `0x140012db6`
- `ntoskrnl!ExAllocatePool2` at `0x140012ecb`
- `ntoskrnl!ExAllocatePool2` at `0x140012f9b`
- `ntoskrnl!ExAllocatePool2` at `0x14001305f`
- `ntoskrnl!ExAllocatePool2` at `0x140012c3c`
- `ntoskrnl!ExAllocatePool2` at `0x140012cab`
- `ntoskrnl!ExAllocatePool2` at `0x140012db6`
- `ntoskrnl!ExAllocatePool2` at `0x140012ecb`
- `ntoskrnl!ExAllocatePool2` at `0x140012f9b`
- `ntoskrnl!ExAllocatePool2` at `0x14001305f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012bb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ff7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400130a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012bb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ff7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400130a3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400129da`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400129da`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400130cc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400131b5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400130cc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400131b5`
- `ntoskrnl!SeAppendPrivileges` at `0x1400128c2`
- `ntoskrnl!SeAppendPrivileges` at `0x1400128c2`
- `ntoskrnl!SeFreePrivileges` at `0x1400128d3`
- `ntoskrnl!SeFreePrivileges` at `0x1400128d3`
- `ntoskrnl!SeAccessCheck` at `0x1400128a6`
- `ntoskrnl!SeAccessCheck` at `0x1400128a6`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140012852`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140012852`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x140012938`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x140012938`
- `ntoskrnl!PsGetThreadProcessId` at `0x140012e77`
- `ntoskrnl!PsGetThreadProcessId` at `0x140012e77`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140012948`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140012948`
- `ntoskrnl!PsGetThreadSessionId` at `0x140012f51`
- `ntoskrnl!PsGetThreadSessionId` at `0x140012f51`
- `ntoskrnl!SeLockSubjectContext` at `0x140012846`
- `ntoskrnl!SeLockSubjectContext` at `0x140012846`
- `ntoskrnl!RtlCompareMemory` at `0x140012a93`
- `ntoskrnl!RtlCompareMemory` at `0x140012a93`
- `ntoskrnl!SeCreateClientSecurity` at `0x140013088`
- `ntoskrnl!SeCreateClientSecurity` at `0x140013088`

## string_xrefs

- `0x140012a0b`: `ClientComputerName`
- `0x140012a2e`: `ClientComputerName`
- `0x140012aeb`: `ClientProcessId`
- `0x140012b11`: `ClientProcessId`
- `0x140012d33`: `RestrictedAccess`
- `0x140012d5e`: `RestrictedAccess`

## pseudocode

```c
int *__fastcall NpCreateClientEnd(
        int *AccessStatus,
        __int64 a2,
        __int64 a3,
        ACCESS_MASK a4,
        struct _ACCESS_STATE *a5,
        PACCESS_STATE AccessState,
        char a7,
        KPROCESSOR_MODE AccessMode,
        PETHREAD Thread,
        const char *a10,
        DWORD GrantedAccess,
        __int64 a12)
{
  PACCESS_STATE v12; // rdi
  int v13; // ebp
  int *v14; // r12
  struct _GENERIC_MAPPING *GenericMapping; // rax
  KPROCESSOR_MODE v19; // r14
  BOOLEAN v20; // bl
  DWORD v21; // eax
  void *v22; // r9
  __int64 v23; // r8
  __int64 v24; // r9
  int *result; // rax
  struct _ACCESS_STATE *v26; // rax
  _QWORD *v27; // rcx
  unsigned __int64 v28; // rbp
  const char *v29; // r14
  struct _KTHREAD *v30; // r13
  size_t v31; // rdi
  unsigned int *v32; // r13
  const char *v33; // rbx
  __int64 v34; // rax
  size_t v35; // r8
  const char *v36; // rdi
  unsigned __int64 v37; // rbx
  char *v38; // rsi
  NTSTATUS ClientSecurity; // ebx
  _QWORD **v40; // rdi
  size_t v41; // rsi
  const char *v42; // rbx
  __int64 v43; // rax
  size_t v44; // r8
  char *v45; // r15
  _QWORD *v46; // rbx
  __int64 v47; // rsi
  _QWORD *v48; // rcx
  _QWORD *v49; // rax
  __int64 *v50; // rax
  size_t v51; // rsi
  const char *v52; // rbx
  __int64 v53; // rax
  size_t v54; // r8
  char *v55; // r15
  _QWORD *v56; // rbx
  _QWORD *v57; // rsi
  _QWORD *v58; // rcx
  _QWORD *v59; // rax
  _QWORD *v60; // rax
  size_t v61; // rbx
  __int64 v62; // rax
  size_t v63; // r8
  const char *v64; // r15
  _QWORD *v65; // rbx
  __int64 v66; // rax
  _QWORD *v67; // rsi
  _QWORD *v68; // rcx
  _QWORD *v69; // rax
  _QWORD *v70; // rax
  PACCESS_STATE v71; // rax
  _QWORD **v72; // rdi
  unsigned int ThreadProcessId; // r15d
  _QWORD *v74; // rbx
  __int64 Pool2; // rsi
  _QWORD *v76; // rcx
  _QWORD *v77; // rax
  __int64 *v78; // rax
  int ThreadSessionId; // eax
  _QWORD *v80; // rbx
  int v81; // r15d
  __int64 v82; // rsi
  _QWORD *v83; // rcx
  _QWORD *v84; // rax
  __int64 *v85; // rax
  struct _SECURITY_CLIENT_CONTEXT *v86; // rax
  __int64 v87; // rcx
  _QWORD *v88; // rax
  __int64 v89; // rax
  __int64 **v90; // rdx
  _QWORD *v91; // rcx
  __int64 v92; // r8
  __int64 *v93; // rcx
  __int64 *v94; // rax
  __int64 **v95; // rax
  PPRIVILEGE_SET Privileges; // [rsp+50h] [rbp-58h] BYREF
  _QWORD *v97; // [rsp+58h] [rbp-50h]
  struct _UNICODE_STRING ObjectTypeName; // [rsp+60h] [rbp-48h] BYREF
  __int16 Source2; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v101; // [rsp+C0h] [rbp+18h]

  v101 = a3;
  v12 = AccessState;
  GrantedAccess = 0;
  *(_OWORD *)AccessStatus = 0;
  v13 = *(_DWORD *)(a2 + 256);
  v14 = AccessStatus;
  Privileges = 0;
  Source2 = 0;
  ObjectTypeName = 0;
  SeLockSubjectContext(&v12->SubjectSecurityContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  v19 = AccessMode;
  v20 = SeAccessCheck(
          *(PSECURITY_DESCRIPTOR *)(a2 + 152),
          &v12->SubjectSecurityContext,
          1u,
          a4,
          0,
          &Privileges,
          GenericMapping,
          AccessMode,
          &GrantedAccess,
          v14);
  if ( Privileges )
  {
    SeAppendPrivileges(v12, Privileges);
    SeFreePrivileges(Privileges);
  }
  if ( v20 )
  {
    v21 = GrantedAccess;
    v12->PreviouslyGrantedAccess |= GrantedAccess;
    v12->RemainingDesiredAccess &= ~(v21 | 0x2000000);
  }
  v22 = *(void **)(a2 + 152);
  ObjectTypeName.Buffer = L"NamedPipe";
  *(_DWORD *)&ObjectTypeName.Length = 1310738;
  SeOpenObjectAuditAlarm(&ObjectTypeName, 0, (PUNICODE_STRING)(a3 + 88), v22, v12, 0, v20, v19, &v12->GenerateOnClose);
  SeUnlockSubjectContext(&v12->SubjectSecurityContext);
  if ( !v20 )
    return v14;
  if ( (GrantedAccess & 1) != 0 && !(_WORD)v13 || (GrantedAccess & 2) != 0 && (unsigned __int16)v13 == 1 )
  {
    *v14 = -1073741790;
    return v14;
  }
  v26 = 0;
  if ( (GrantedAccess & 3) != 0 )
    v26 = a5;
  AccessState = v26;
  v27 = *(_QWORD **)(a2 + 312);
  v97 = v27;
  if ( v27 == (_QWORD *)(a2 + 312) )
  {
    *v14 = -1073741652;
    return v14;
  }
  v28 = (unsigned __int64)(v27 - 36);
  ExAcquirePushLockExclusiveEx(v27 - 28, 0, v23, v24);
  v29 = a10;
  v30 = Thread;
  if ( !a10 )
    goto LABEL_92;
  v31 = *((unsigned __int8 *)a10 + 5);
  v32 = (unsigned int *)(a10 + 8);
  v33 = a10;
  if ( strncmp_0(a10 + 8, "ClientComputerName", v31) )
  {
    while ( 1 )
    {
      v34 = *(unsigned int *)v33;
      if ( !(_DWORD)v34 )
        break;
      v33 += v34;
      v35 = *((unsigned __int8 *)v33 + 5);
      v36 = &v33[v35 + 8];
      if ( !strncmp_0(v33 + 8, "ClientComputerName", v35) )
        goto LABEL_22;
    }
    v30 = Thread;
LABEL_92:
    v72 = (_QWORD **)(v28 + 304);
    ThreadProcessId = (unsigned int)PsGetThreadProcessId(v30);
    v74 = *(_QWORD **)(v28 + 304);
    if ( v74 == (_QWORD *)(v28 + 304) )
    {
LABEL_95:
      v74 = 0;
    }
    else
    {
      while ( v74[2] != 3 )
      {
        v74 = (_QWORD *)*v74;
        if ( v74 == v72 )
          goto LABEL_95;
      }
    }
    if ( v28 == -352 )
    {
      Pool2 = ExAllocatePool2(256, 40, 1950445646);
      if ( !Pool2 )
        goto LABEL_54;
    }
    else
    {
      Pool2 = v28 + 352;
    }
    *(_QWORD *)(Pool2 + 16) = 3;
    *(_DWORD *)(Pool2 + 32) = ThreadProcessId;
    *(_QWORD *)(Pool2 + 24) = 4;
    if ( v74 )
    {
      v76 = (_QWORD *)*v74;
      if ( *(_QWORD **)(*v74 + 8LL) != v74 )
        goto LABEL_137;
      v77 = (_QWORD *)v74[1];
      if ( (_QWORD *)*v77 != v74 )
        goto LABEL_137;
      *v77 = v76;
      v76[1] = v77;
      if ( v74 != (_QWORD *)(v28 + 352) )
        ExFreePoolWithTag(v74, 0);
    }
    v78 = *(__int64 **)(v28 + 312);
    if ( (_QWORD **)*v78 != v72 )
      goto LABEL_137;
    *(_QWORD *)Pool2 = v72;
    *(_QWORD *)(Pool2 + 8) = v78;
    *v78 = Pool2;
    *(_QWORD *)(v28 + 312) = Pool2;
    ThreadSessionId = PsGetThreadSessionId(v30);
    v80 = *v72;
    v81 = ThreadSessionId;
    if ( *v72 == v72 )
    {
LABEL_108:
      v80 = 0;
    }
    else
    {
      while ( v80[2] != 4 )
      {
        v80 = (_QWORD *)*v80;
        if ( v80 == v72 )
          goto LABEL_108;
      }
    }
    if ( v28 != -392 )
    {
      v82 = v28 + 392;
LABEL_112:
      *(_QWORD *)(v82 + 16) = 4;
      *(_DWORD *)(v82 + 32) = v81;
      *(_QWORD *)(v82 + 24) = 4;
      if ( v80 )
      {
        v83 = (_QWORD *)*v80;
        if ( *(_QWORD **)(*v80 + 8LL) != v80 )
          goto LABEL_137;
        v84 = (_QWORD *)v80[1];
        if ( (_QWORD *)*v84 != v80 )
          goto LABEL_137;
        *v84 = v83;
        v83[1] = v84;
        if ( v80 != (_QWORD *)(v28 + 392) )
          ExFreePoolWithTag(v80, 0);
      }
      v85 = *(__int64 **)(v28 + 312);
      if ( (_QWORD **)*v85 != v72 )
        goto LABEL_137;
      *(_QWORD *)v82 = v72;
      *(_QWORD *)(v82 + 8) = v85;
      *v85 = v82;
      *(_QWORD *)(v28 + 312) = v82;
      goto LABEL_89;
    }
    v82 = ExAllocatePool2(256, 40, 1950445646);
    if ( v82 )
      goto LABEL_112;
LABEL_54:
    ClientSecurity = -1073741670;
    goto LABEL_125;
  }
  v36 = (char *)v32 + v31;
LABEL_22:
  if ( !a7 )
    goto LABEL_35;
  v37 = *((unsigned __int16 *)v33 + 3);
  if ( (v37 & 1) != 0 )
    goto LABEL_35;
  if ( v37 < 4 )
    goto LABEL_35;
  v38 = (char *)(v36 + 1);
  if ( RtlCompareMemory(&v36[2 * ((unsigned __int64)(unsigned int)v37 >> 1) - 1], &Source2, 2u) != 2 )
    goto LABEL_35;
  if ( *(_DWORD *)(a2 + 264) )
  {
    v40 = (_QWORD **)(v28 + 304);
    ClientSecurity = NpSetAttributeInList(v28 + 304, 0, 6, v38, v37);
    if ( ClientSecurity < 0 )
      goto LABEL_125;
    v41 = *((unsigned __int8 *)v29 + 5);
    v42 = v29;
    if ( !strncmp_0(v29 + 8, "ClientProcessId", v41) )
    {
      v45 = (char *)v32 + v41;
LABEL_34:
      if ( *((_WORD *)v42 + 3) < 4u )
        goto LABEL_35;
      v46 = *v40;
      if ( *v40 == v40 )
      {
LABEL_39:
        v46 = 0;
      }
      else
      {
        while ( v46[2] != 3 )
        {
          v46 = (_QWORD *)*v46;
          if ( v46 == v40 )
            goto LABEL_39;
        }
      }
      if ( v28 == -352 )
      {
        v47 = ExAllocatePool2(256, 40, 1950445646);
        if ( !v47 )
          goto LABEL_54;
      }
      else
      {
        v47 = v28 + 352;
      }
      *(_QWORD *)(v47 + 16) = 3;
      *(_DWORD *)(v47 + 32) = *(_DWORD *)(v45 + 1);
      *(_QWORD *)(v47 + 24) = 4;
      if ( v46 )
      {
        v48 = (_QWORD *)*v46;
        if ( *(_QWORD **)(*v46 + 8LL) != v46 )
          goto LABEL_137;
        v49 = (_QWORD *)v46[1];
        if ( (_QWORD *)*v49 != v46 )
          goto LABEL_137;
        *v49 = v48;
        v48[1] = v49;
        if ( v46 != (_QWORD *)(v28 + 352) )
          ExFreePoolWithTag(v46, 0);
      }
      v50 = *(__int64 **)(v28 + 312);
      if ( (_QWORD **)*v50 != v40 )
        goto LABEL_137;
      *(_QWORD *)v47 = v40;
      *(_QWORD *)(v47 + 8) = v50;
      *v50 = v47;
      *(_QWORD *)(v28 + 312) = v47;
    }
    else
    {
      while ( 1 )
      {
        v43 = *(unsigned int *)v42;
        if ( !(_DWORD)v43 )
          break;
        v42 += v43;
        v44 = *((unsigned __int8 *)v42 + 5);
        v45 = (char *)&v42[v44 + 8];
        if ( !strncmp_0(v42 + 8, "ClientProcessId", v44) )
          goto LABEL_34;
      }
    }
    v51 = *((unsigned __int8 *)v29 + 5);
    v52 = v29;
    if ( !strncmp_0(v29 + 8, "ClientSessionId", v51) )
    {
      v55 = (char *)v32 + v51;
LABEL_56:
      if ( *((_WORD *)v52 + 3) < 8u )
        goto LABEL_35;
      v56 = *v40;
      if ( *v40 == v40 )
      {
LABEL_60:
        v56 = 0;
      }
      else
      {
        while ( v56[2] != 4 )
        {
          v56 = (_QWORD *)*v56;
          if ( v56 == v40 )
            goto LABEL_60;
        }
      }
      if ( v28 == -392 )
      {
        v57 = (_QWORD *)ExAllocatePool2(256, 40, 1950445646);
        if ( !v57 )
          goto LABEL_54;
      }
      else
      {
        v57 = (_QWORD *)(v28 + 392);
      }
      v57[2] = 4;
      v57[4] = *(_QWORD *)(v55 + 1);
      v57[3] = 8;
      if ( v56 )
      {
        v58 = (_QWORD *)*v56;
        if ( *(_QWORD **)(*v56 + 8LL) != v56 )
          goto LABEL_137;
        v59 = (_QWORD *)v56[1];
        if ( (_QWORD *)*v59 != v56 )
          goto LABEL_137;
        *v59 = v58;
        v58[1] = v59;
        if ( v56 != (_QWORD *)(v28 + 392) )
          ExFreePoolWithTag(v56, 0);
      }
      v60 = *(_QWORD **)(v28 + 312);
      if ( (_QWORD **)*v60 != v40 )
        goto LABEL_137;
      *v57 = v40;
      v57[1] = v60;
      *v60 = v57;
      *(_QWORD *)(v28 + 312) = v57;
    }
    else
    {
      while ( 1 )
      {
        v53 = *(unsigned int *)v52;
        if ( !(_DWORD)v53 )
          break;
        v52 += v53;
        v54 = *((unsigned __int8 *)v52 + 5);
        v55 = (char *)&v52[v54 + 8];
        if ( !strncmp_0(v52 + 8, "ClientSessionId", v54) )
          goto LABEL_56;
      }
    }
    v61 = *((unsigned __int8 *)v29 + 5);
    if ( strncmp_0(v29 + 8, "RestrictedAccess", v61) )
    {
      while ( 1 )
      {
        v62 = *(unsigned int *)v29;
        if ( !(_DWORD)v62 )
          goto LABEL_88;
        v29 += v62;
        v63 = *((unsigned __int8 *)v29 + 5);
        v64 = &v29[v63 + 8];
        if ( !strncmp_0(v29 + 8, "RestrictedAccess", v63) )
          goto LABEL_76;
      }
    }
    v64 = (char *)v32 + v61;
LABEL_76:
    if ( *((_WORD *)v29 + 3) >= 4u )
    {
      v65 = *v40;
      if ( *v40 == v40 )
      {
LABEL_80:
        v65 = 0;
      }
      else
      {
        while ( v65[2] != 7 )
        {
          v65 = (_QWORD *)*v65;
          if ( v65 == v40 )
            goto LABEL_80;
        }
      }
      v66 = ExAllocatePool2(256, 40, 1950445646);
      v67 = (_QWORD *)v66;
      if ( !v66 )
        goto LABEL_54;
      *(_QWORD *)(v66 + 16) = 7;
      *(_DWORD *)(v66 + 32) = *(_DWORD *)(v64 + 1);
      *(_QWORD *)(v66 + 24) = 4;
      if ( v65 )
      {
        v68 = (_QWORD *)*v65;
        if ( *(_QWORD **)(*v65 + 8LL) != v65 )
          goto LABEL_137;
        v69 = (_QWORD *)v65[1];
        if ( (_QWORD *)*v69 != v65 )
          goto LABEL_137;
        *v69 = v68;
        v68[1] = v69;
        ExFreePoolWithTag(v65, 0);
      }
      v70 = *(_QWORD **)(v28 + 312);
      if ( (_QWORD **)*v70 != v40 )
        goto LABEL_137;
      *v67 = v40;
      v67[1] = v70;
      *v70 = v67;
      *(_QWORD *)(v28 + 312) = v67;
LABEL_88:
      v30 = Thread;
      v14 = AccessStatus;
LABEL_89:
      v71 = AccessState;
      if ( AccessState )
      {
        *(LUID *)(v28 + 12) = AccessState->OperationID;
        *(_DWORD *)(v28 + 20) = *(_DWORD *)&v71->SecurityEvaluated;
      }
      else
      {
        *(_DWORD *)(v28 + 12) = 12;
        *(_DWORD *)(v28 + 16) = 2;
        *(_WORD *)(v28 + 20) = 257;
      }
      if ( *(_BYTE *)(v28 + 20) || *(_QWORD *)(v28 + 264) == -1 )
      {
LABEL_126:
        v87 = *v97;
        if ( *(_QWORD **)(*v97 + 8LL) == v97 )
        {
          v88 = (_QWORD *)v97[1];
          if ( (_QWORD *)*v88 == v97 )
          {
            *v88 = v87;
            *(_QWORD *)(v87 + 8) = v88;
            *(_BYTE *)(v28 + 9) &= 0xFCu;
            *(_BYTE *)(v28 + 8) = 3;
            _InterlockedIncrement((volatile signed __int32 *)(v28 + 4));
            v89 = *(_QWORD *)(v28 + 40);
            v90 = (__int64 **)(v28 + 272);
            v91 = (_QWORD *)v101;
            v92 = a12;
            *(_DWORD *)(v101 + 80) |= 0x80u;
            v91[3] = v89;
            v91[6] = 1;
            v91[4] = v28 | 1;
            *(_QWORD *)(v28 + 48) = v91;
            while ( 1 )
            {
              v93 = *v90;
              if ( *v90 == (__int64 *)v90 )
                break;
              if ( (__int64 **)v93[1] != v90 )
                goto LABEL_137;
              v94 = (__int64 *)*v93;
              if ( *(__int64 **)(*v93 + 8) != v93 )
                goto LABEL_137;
              *v90 = v94;
              v94[1] = (__int64)v90;
              if ( _InterlockedExchange64(v93 - 8, 0) )
              {
                *((_DWORD *)v93 - 30) = 0;
                v95 = *(__int64 ***)(v92 + 8);
                if ( *v95 != (__int64 *)v92 )
                  goto LABEL_137;
                *v93 = v92;
                v93[1] = (__int64)v95;
                *v95 = v93;
                *(_QWORD *)(v92 + 8) = v93;
              }
              else
              {
                v93[1] = (__int64)v93;
                *v93 = (__int64)v93;
              }
            }
            ExReleasePushLockExclusiveEx(v28 + 64, 0);
            *v14 = 0;
            *((_QWORD *)v14 + 1) = 1;
            return v14;
          }
        }
LABEL_137:
        __fastfail(3u);
      }
      v86 = (struct _SECURITY_CLIENT_CONTEXT *)ExAllocatePool2(257, 72, 1933996110);
      *(_QWORD *)(v28 + 264) = v86;
      if ( v86 )
      {
        ClientSecurity = SeCreateClientSecurity(v30, (PSECURITY_QUALITY_OF_SERVICE)(v28 + 12), 0, v86);
        if ( ClientSecurity < 0 )
        {
          ExFreePoolWithTag(*(PVOID *)(v28 + 264), 0);
          *(_QWORD *)(v28 + 264) = 0;
          goto LABEL_125;
        }
        goto LABEL_126;
      }
      goto LABEL_54;
    }
LABEL_35:
    ClientSecurity = -1073741811;
    goto LABEL_125;
  }
  ClientSecurity = -1073741790;
LABEL_125:
  NpRemoveAllAttributesFromList(v28 + 304);
  ExReleasePushLockExclusiveEx(v28 + 64, 0);
  result = AccessStatus;
  *AccessStatus = ClientSecurity;
  *((_QWORD *)AccessStatus + 1) = 0;
  return result;
}

```

## disassembly

```asm
0x1400127f0  mov     r11, rsp
0x1400127f3  mov     [r11+20h], rbx
0x1400127f7  mov     [r11+18h], r8
0x1400127fb  mov     [r11+8], rcx
0x1400127ff  push    rbp
0x140012800  push    rsi
0x140012801  push    rdi
0x140012802  push    r12
0x140012804  push    r13
0x140012806  push    r14
0x140012808  push    r15
0x14001280a  sub     rsp, 70h
0x14001280e  mov     rdi, [rsp+0A8h+AccessState]
0x140012816  xor     eax, eax
0x140012818  xorps   xmm0, xmm0
0x14001281b  mov     [r11+58h], eax
0x14001281f  movups  xmmword ptr [rcx], xmm0
0x140012822  mov     ebp, [rdx+100h]
0x140012828  mov     r12, rcx
0x14001282b  lea     rcx, [rdi+20h]; SubjectContext
0x14001282f  mov     [r11-58h], rax
0x140012833  mov     ebx, r9d
0x140012836  mov     [r11+10h], ax
0x14001283b  mov     r13, r8
0x14001283e  mov     r15, rdx
0x140012841  movups  xmmword ptr [rsp+0A8h+ObjectTypeName.Length], xmm0
0x140012846  call    cs:__imp_SeLockSubjectContext
0x14001284d  nop     dword ptr [rax+rax+00h]
0x140012852  call    cs:__imp_IoGetFileObjectGenericMapping
0x140012859  nop     dword ptr [rax+rax+00h]
0x14001285e  movzx   r14d, [rsp+0A8h+arg_38]
0x140012867  lea     rcx, [rsp+0A8h+arg_50]
0x14001286f  mov     [rsp+0A8h+AccessStatus], r12; AccessStatus
0x140012874  lea     rdx, [rdi+20h]; SubjectSecurityContext
0x140012878  mov     [rsp+0A8h+GrantedAccess], rcx; GrantedAccess
0x14001287d  mov     r9d, ebx; DesiredAccess
0x140012880  mov     rcx, [r15+98h]; SecurityDescriptor
0x140012887  mov     r8b, 1; SubjectContextLocked
0x14001288a  mov     [rsp+0A8h+AccessMode], r14b; AccessMode
0x14001288f  mov     [rsp+0A8h+GenericMapping], rax; GenericMapping
0x140012894  lea     rax, [rsp+0A8h+var_58]
0x140012899  mov     [rsp+0A8h+Privileges], rax; Privileges
0x14001289e  mov     [rsp+0A8h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1400128a6  call    cs:__imp_SeAccessCheck
0x1400128ad  nop     dword ptr [rax+rax+00h]
0x1400128b2  mov     rdx, [rsp+0A8h+var_58]; Privileges
0x1400128b7  movzx   ebx, al
0x1400128ba  test    rdx, rdx
0x1400128bd  jz      short loc_1400128DF
0x1400128bf  mov     rcx, rdi; AccessState
0x1400128c2  call    cs:__imp_SeAppendPrivileges
0x1400128c9  nop     dword ptr [rax+rax+00h]
0x1400128ce  mov     rcx, [rsp+0A8h+var_58]; Privileges
0x1400128d3  call    cs:__imp_SeFreePrivileges
0x1400128da  nop     dword ptr [rax+rax+00h]
0x1400128df  test    bl, bl
0x1400128e1  jz      short loc_1400128F6
0x1400128e3  mov     eax, [rsp+0A8h+arg_50]
0x1400128ea  or      [rdi+14h], eax
0x1400128ed  bts     eax, 19h
0x1400128f1  not     eax
0x1400128f3  and     [rdi+10h], eax
0x1400128f6  mov     r9, [r15+98h]; SecurityDescriptor
0x1400128fd  lea     rax, aNamedpipe; "NamedPipe"
0x140012904  mov     [rsp+0A8h+ObjectTypeName.Buffer], rax
0x140012909  lea     r8, [r13+58h]; AbsoluteObjectName
0x14001290d  lea     rax, [rdi+0Ah]
0x140012911  mov     dword ptr [rsp+0A8h+ObjectTypeName.Length], 140012h
0x140012919  mov     [rsp+0A8h+GrantedAccess], rax; GenerateOnClose
0x14001291e  lea     rcx, [rsp+0A8h+ObjectTypeName]; ObjectTypeName
0x140012923  mov     [rsp+0A8h+AccessMode], r14b; AccessMode
0x140012928  xor     edx, edx; Object
0x14001292a  mov     byte ptr [rsp+0A8h+GenericMapping], bl; AccessGranted
0x14001292e  mov     byte ptr [rsp+0A8h+Privileges], 0; ObjectCreated
0x140012933  mov     qword ptr [rsp+0A8h+PreviouslyGrantedAccess], rdi; AccessState
0x140012938  call    cs:__imp_SeOpenObjectAuditAlarm
0x14001293f  nop     dword ptr [rax+rax+00h]
0x140012944  lea     rcx, [rdi+20h]; SubjectContext
0x140012948  call    cs:__imp_SeUnlockSubjectContext
0x14001294f  nop     dword ptr [rax+rax+00h]
0x140012954  test    bl, bl
0x140012956  jz      short loc_14001297B
0x140012958  mov     eax, [rsp+0A8h+arg_50]
0x14001295f  movzx   ecx, bp
0x140012962  test    al, 1
0x140012964  jz      short loc_14001296A
0x140012966  test    ecx, ecx
0x140012968  jz      short loc_140012973
0x14001296a  test    al, 2
0x14001296c  jz      short loc_140012997
0x14001296e  cmp     ecx, 1
0x140012971  jnz     short loc_140012997
0x140012973  mov     dword ptr [r12], 0C0000022h
0x14001297b  mov     rax, r12
0x14001297e  mov     rbx, [rsp+0A8h+arg_18]
0x140012986  add     rsp, 70h
0x14001298a  pop     r15
0x14001298c  pop     r14
0x14001298e  pop     r13
0x140012990  pop     r12
0x140012992  pop     rdi
0x140012993  pop     rsi
0x140012994  pop     rbp
0x140012995  retn
0x140012997  test    al, 3
0x140012999  mov     eax, 0
0x14001299e  cmovnz  rax, [rsp+0A8h+arg_20]
0x1400129a7  mov     [rsp+0A8h+AccessState], rax
0x1400129af  lea     rax, [r15+138h]
0x1400129b6  mov     rcx, [rax]
0x1400129b9  mov     [rsp+0A8h+var_50], rcx
0x1400129be  cmp     rcx, rax
0x1400129c1  jnz     short loc_1400129CD
0x1400129c3  mov     dword ptr [r12], 0C00000ACh
0x1400129cb  jmp     short loc_14001297B
0x1400129cd  lea     rbp, [rcx-120h]
0x1400129d4  xor     edx, edx
0x1400129d6  lea     rcx, [rbp+40h]
0x1400129da  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400129e1  nop     dword ptr [rax+rax+00h]
0x1400129e6  mov     r14, [rsp+0A8h+arg_48]
0x1400129ee  mov     r13, [rsp+0A8h+Thread]
0x1400129f6  test    r14, r14
0x1400129f9  jz      loc_140012E74
0x1400129ff  movzx   edi, byte ptr [r14+5]
0x140012a04  lea     r13, [r14+8]
0x140012a08  mov     r8d, edi; MaxCount
0x140012a0b  lea     rdx, Str2; "ClientComputerName"
0x140012a12  mov     rcx, r13; Str1
0x140012a15  mov     rbx, r14
0x140012a18  call    strncmp_0
0x140012a1d  test    eax, eax
0x140012a1f  jz      short loc_140012A4D
0x140012a21  mov     eax, [rbx]
0x140012a23  test    eax, eax
0x140012a25  jz      loc_140012E6C
0x140012a2b  add     rbx, rax
0x140012a2e  lea     rdx, Str2; "ClientComputerName"
0x140012a35  movzx   r8d, byte ptr [rbx+5]; MaxCount
0x140012a3a  lea     rcx, [rbx+8]; Str1
0x140012a3e  lea     rdi, [r8+rcx]
0x140012a42  call    strncmp_0
0x140012a47  test    eax, eax
0x140012a49  jnz     short loc_140012A21
0x140012a4b  jmp     short loc_140012A50
0x140012a4d  add     rdi, r13
0x140012a50  cmp     [rsp+0A8h+arg_30], 0
0x140012a58  jz      loc_140012B3B
0x140012a5e  movzx   ebx, word ptr [rbx+6]
0x140012a62  test    bl, 1
0x140012a65  ja      loc_140012B3B
0x140012a6b  cmp     rbx, 4
0x140012a6f  jb      loc_140012B3B
0x140012a75  mov     eax, ebx
0x140012a77  lea     rsi, [rdi+1]
0x140012a7b  shr     rax, 1
0x140012a7e  lea     rdx, [rsp+0A8h+Source2]; Source2
0x140012a86  dec     rax
0x140012a89  mov     r8d, 2; Length
0x140012a8f  lea     rcx, [rsi+rax*2]; Source1
0x140012a93  call    cs:__imp_RtlCompareMemory
0x140012a9a  nop     dword ptr [rax+rax+00h]
0x140012a9f  cmp     rax, 2
0x140012aa3  jnz     loc_140012B3B
0x140012aa9  cmp     dword ptr [r15+108h], 0
0x140012ab1  jnz     short loc_140012ABD
0x140012ab3  mov     ebx, 0C0000022h
0x140012ab8  jmp     loc_1400130BA
0x140012abd  lea     rdi, [rbp+130h]
0x140012ac4  mov     qword ptr [rsp+0A8h+PreviouslyGrantedAccess], rbx
0x140012ac9  mov     rcx, rdi
0x140012acc  mov     r9, rsi
0x140012acf  xor     edx, edx
0x140012ad1  mov     r8d, 6
0x140012ad7  call    NpSetAttributeInList
0x140012adc  mov     ebx, eax
0x140012ade  test    eax, eax
0x140012ae0  js      loc_1400130BA
0x140012ae6  movzx   esi, byte ptr [r14+5]
0x140012aeb  lea     rdx, aClientprocessi; "ClientProcessId"
0x140012af2  mov     r8d, esi; MaxCount
0x140012af5  mov     rcx, r13; Str1
0x140012af8  mov     rbx, r14
0x140012afb  call    strncmp_0
0x140012b00  test    eax, eax
0x140012b02  jz      short loc_140012B30
0x140012b04  mov     eax, [rbx]
0x140012b06  test    eax, eax
0x140012b08  jz      loc_140012BDF
0x140012b0e  add     rbx, rax
0x140012b11  lea     rdx, aClientprocessi; "ClientProcessId"
0x140012b18  movzx   r8d, byte ptr [rbx+5]; MaxCount
0x140012b1d  lea     rcx, [rbx+8]; Str1
0x140012b21  lea     r15, [r8+rcx]
0x140012b25  call    strncmp_0
0x140012b2a  test    eax, eax
0x140012b2c  jnz     short loc_140012B04
0x140012b2e  jmp     short loc_140012B34
0x140012b30  lea     r15, [rsi+r13]
0x140012b34  cmp     word ptr [rbx+6], 4
0x140012b39  jnb     short loc_140012B45
0x140012b3b  mov     ebx, 0C000000Dh
0x140012b40  jmp     loc_1400130BA
0x140012b45  mov     rbx, [rdi]
0x140012b48  lea     r12, [rbp+160h]
0x140012b4f  cmp     rbx, rdi
0x140012b52  jz      short loc_140012B63
0x140012b54  cmp     qword ptr [rbx+10h], 3
0x140012b59  jz      short loc_140012B65
0x140012b5b  mov     rbx, [rbx]
0x140012b5e  cmp     rbx, rdi
0x140012b61  jnz     short loc_140012B54
0x140012b63  xor     ebx, ebx
0x140012b65  test    r12, r12
0x140012b68  jz      loc_140012C2C
0x140012b6e  mov     rsi, r12
0x140012b71  mov     qword ptr [rsi+10h], 3
0x140012b79  mov     eax, [r15+1]
0x140012b7d  mov     [rsi+20h], eax
0x140012b80  mov     qword ptr [rsi+18h], 4
0x140012b88  test    rbx, rbx
0x140012b8b  jz      short loc_140012BC4
0x140012b8d  mov     rcx, [rbx]
0x140012b90  cmp     [rcx+8], rbx
0x140012b94  jnz     loc_1400131D3
0x140012b9a  mov     rax, [rbx+8]
0x140012b9e  cmp     [rax], rbx
0x140012ba1  jnz     loc_1400131D3
0x140012ba7  mov     [rax], rcx
0x140012baa  mov     [rcx+8], rax
0x140012bae  cmp     rbx, r12
0x140012bb1  jz      short loc_140012BC4
0x140012bb3  xor     edx, edx; Tag
0x140012bb5  mov     rcx, rbx; P
0x140012bb8  call    cs:__imp_ExFreePoolWithTag
0x140012bbf  nop     dword ptr [rax+rax+00h]
0x140012bc4  mov     rax, [rdi+8]
0x140012bc8  cmp     [rax], rdi
0x140012bcb  jnz     loc_1400131D3
0x140012bd1  mov     [rsi], rdi
0x140012bd4  mov     [rsi+8], rax
0x140012bd8  mov     [rax], rsi
0x140012bdb  mov     [rdi+8], rsi
0x140012bdf  movzx   esi, byte ptr [r14+5]
0x140012be4  lea     rdx, aClientsessioni; "ClientSessionId"
0x140012beb  mov     r8d, esi; MaxCount
0x140012bee  mov     rcx, r13; Str1
0x140012bf1  mov     rbx, r14
0x140012bf4  call    strncmp_0
0x140012bf9  test    eax, eax
0x140012bfb  jz      short loc_140012C5E
0x140012bfd  nop     dword ptr [rax]
0x140012c00  mov     eax, [rbx]
0x140012c02  test    eax, eax
0x140012c04  jz      loc_140012D2E
0x140012c0a  add     rbx, rax
0x140012c0d  lea     rdx, aClientsessioni; "ClientSessionId"
0x140012c14  movzx   r8d, byte ptr [rbx+5]; MaxCount
0x140012c19  lea     rcx, [rbx+8]; Str1
0x140012c1d  lea     r15, [r8+rcx]
0x140012c21  call    strncmp_0
0x140012c26  test    eax, eax
0x140012c28  jnz     short loc_140012C00
0x140012c2a  jmp     short loc_140012C62
0x140012c2c  mov     edx, 28h ; '('
0x140012c31  mov     ecx, 100h
0x140012c36  mov     r8d, 7441704Eh
0x140012c3c  call    cs:__imp_ExAllocatePool2
0x140012c43  nop     dword ptr [rax+rax+00h]
0x140012c48  mov     rsi, rax
0x140012c4b  test    rax, rax
0x140012c4e  jnz     loc_140012B71
0x140012c54  mov     ebx, 0C000009Ah
0x140012c59  jmp     loc_1400130BA
0x140012c5e  lea     r15, [rsi+r13]
0x140012c62  cmp     word ptr [rbx+6], 8
0x140012c67  jb      loc_140012B3B
0x140012c6d  mov     rbx, [rdi]
0x140012c70  lea     r12, [rbp+188h]
0x140012c77  cmp     rbx, rdi
0x140012c7a  jz      short loc_140012C8F
0x140012c7c  nop     dword ptr [rax+00h]
0x140012c80  cmp     qword ptr [rbx+10h], 4
0x140012c85  jz      short loc_140012C91
0x140012c87  mov     rbx, [rbx]
0x140012c8a  cmp     rbx, rdi
0x140012c8d  jnz     short loc_140012C80
0x140012c8f  xor     ebx, ebx
0x140012c91  test    r12, r12
0x140012c94  jz      short loc_140012C9B
0x140012c96  mov     rsi, r12
0x140012c99  jmp     short loc_140012CBF
0x140012c9b  mov     edx, 28h ; '('
0x140012ca0  mov     ecx, 100h
0x140012ca5  mov     r8d, 7441704Eh
0x140012cab  call    cs:__imp_ExAllocatePool2
0x140012cb2  nop     dword ptr [rax+rax+00h]
0x140012cb7  mov     rsi, rax
0x140012cba  test    rax, rax
0x140012cbd  jz      short loc_140012C54
  ... truncated ...
```
