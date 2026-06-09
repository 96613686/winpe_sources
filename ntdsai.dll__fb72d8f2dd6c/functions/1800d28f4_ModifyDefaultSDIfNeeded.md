# ModifyDefaultSDIfNeeded

- ea: `0x1800d28f4`
- end: `0x1800d3442`
- name: `ModifyDefaultSDIfNeeded`
- size: `2894`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d94b4`

## callees

- `0x1800067d0`
- `0x18001e090`
- `0x180021aa3`
- `0x1800d28f4`
- `0x180161d38`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800d2ae9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800d2e40`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800d2ae9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800d2e40`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800d2ba9`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800d2ca3`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800d2ba9`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800d2ca3`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x1800d2e89`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x1800d2e89`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedObjectAce` at `0x1800d30e1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedObjectAce` at `0x1800d30e1`
- `api-ms-win-security-base-l1-1-0!FindFirstFreeAce` at `0x1800d314e`
- `api-ms-win-security-base-l1-1-0!FindFirstFreeAce` at `0x1800d314e`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800d3172`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800d31a8`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800d3172`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800d31a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d30eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d31b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d30eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d31b2`
- `ntdll!RtlFreeSid` at `0x1800d3412`
- `ntdll!RtlFreeSid` at `0x1800d3412`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d2ffa`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d2ffa`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800d2d4b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800d2d4b`
- `ntdll!RtlAddAce` at `0x1800d2d28`
- `ntdll!RtlAddAce` at `0x1800d2d28`
- `ntdll!RtlGetAcesBufferSize` at `0x1800d2d05`
- `ntdll!RtlGetAcesBufferSize` at `0x1800d2d05`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800d2b34`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800d2b34`
- `ntdll!RtlNtStatusToDosError` at `0x1800d2b42`
- `ntdll!RtlNtStatusToDosError` at `0x1800d300a`
- `ntdll!RtlNtStatusToDosError` at `0x1800d2b42`
- `ntdll!RtlNtStatusToDosError` at `0x1800d300a`
- `ntdll!RtlCreateAcl` at `0x1800d2cee`
- `ntdll!RtlCreateAcl` at `0x1800d2cee`

## pseudocode

```c
signed int __fastcall ModifyDefaultSDIfNeeded(
        int a1,
        int a2,
        __int64 a3,
        int a4,
        void *a5,
        _QWORD *a6,
        void **a7,
        signed int *a8)
{
  signed int result; // eax
  __int64 LastError; // rsi
  struct _ACL *pSacl; // rbx
  struct _ACL *v12; // rdx
  unsigned int v13; // edi
  int v14; // r11d
  int v15; // r14d
  int v16; // r15d
  int v17; // r10d
  __int64 v18; // rax
  __int64 p_AceCount; // rax
  __int64 v20; // rax
  int ControlSecurityDescriptor; // eax
  signed int *v22; // r15
  void *pOwner; // rdi
  void *pPrimaryGroup; // r15
  struct _ACL *v25; // r14
  BOOL AbsoluteSD; // eax
  ULONG v27; // ebx
  struct _ACL *v28; // rdi
  struct _ACL *v29; // rdx
  DWORD v30; // r13d
  DWORD v31; // r15d
  DWORD v32; // r14d
  int v33; // r11d
  int v34; // r15d
  int v35; // r12d
  int v36; // r10d
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // edi
  _QWORD *v41; // r14
  int v42; // ecx
  NTSTATUS v43; // eax
  int v44; // ecx
  void *v45; // rbx
  void **v46; // rdi
  unsigned int v47; // ebx
  __int64 v48; // rax
  void *v49; // rdx
  int v50; // ecx
  signed int Size; // [rsp+60h] [rbp-A0h]
  int v52; // [rsp+68h] [rbp-98h]
  WORD Control[2]; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwDaclSize; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD dwBufferLength; // [rsp+88h] [rbp-78h] BYREF
  LPVOID pAce; // [rsp+90h] [rbp-70h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+98h] [rbp-68h] BYREF
  DWORD dwOwnerSize; // [rsp+9Ch] [rbp-64h] BYREF
  DWORD dwSaclSize[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-50h] BYREF
  int v61; // [rsp+B8h] [rbp-48h]
  int Internal; // [rsp+BCh] [rbp-44h]
  __int64 v63; // [rsp+C0h] [rbp-40h]
  int v64; // [rsp+C8h] [rbp-38h]
  int v65; // [rsp+CCh] [rbp-34h]
  __int64 v66; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  struct _ACL *v68; // [rsp+E0h] [rbp-20h]
  __int64 v69; // [rsp+E8h] [rbp-18h]
  struct _ACL *v70; // [rsp+F0h] [rbp-10h]
  int v71; // [rsp+F8h] [rbp-8h]
  __int64 v72; // [rsp+FCh] [rbp-4h]
  int v73; // [rsp+104h] [rbp+4h]
  int *v74; // [rsp+108h] [rbp+8h]
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+110h] [rbp+10h] BYREF
  ULONG AceListLength; // [rsp+114h] [rbp+14h] BYREF
  ULONG Revision; // [rsp+118h] [rbp+18h] BYREF
  PSID Sid; // [rsp+120h] [rbp+20h] BYREF
  void *Src; // [rsp+128h] [rbp+28h]
  _OWORD pAbsoluteSecurityDescriptor[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v81; // [rsp+150h] [rbp+50h]
  __int64 v82; // [rsp+160h] [rbp+60h] BYREF
  int v83; // [rsp+168h] [rbp+68h]
  int v84; // [rsp+16Ch] [rbp+6Ch]
  __int64 v85; // [rsp+170h] [rbp+70h]
  int v86; // [rsp+178h] [rbp+78h]
  int v87; // [rsp+17Ch] [rbp+7Ch]
  __int64 v88; // [rsp+180h] [rbp+80h]
  __int64 v89; // [rsp+188h] [rbp+88h]
  struct _ACL *v90; // [rsp+190h] [rbp+90h]
  __int64 v91; // [rsp+198h] [rbp+98h]
  struct _ACL *v92; // [rsp+1A0h] [rbp+A0h]
  int v93; // [rsp+1A8h] [rbp+A8h]
  __int64 v94; // [rsp+1ACh] [rbp+ACh]
  int v95; // [rsp+1B4h] [rbp+B4h]
  int *v96; // [rsp+1B8h] [rbp+B8h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+1C0h] [rbp+C0h] BYREF
  _OWORD pSid2[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  int v99; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 *v100; // [rsp+1F8h] [rbp+F8h]
  __int64 v101; // [rsp+208h] [rbp+108h] BYREF
  int v102; // [rsp+210h] [rbp+110h]
  __int64 *v103; // [rsp+218h] [rbp+118h]
  __int64 v104; // [rsp+228h] [rbp+128h] BYREF
  int v105; // [rsp+230h] [rbp+130h]
  _QWORD *v106; // [rsp+238h] [rbp+138h]

  result = 0;
  Src = (void *)a3;
  LODWORD(LastError) = 0;
  *a7 = 0;
  pSacl = 0;
  Size = a4;
  v52 = a1;
  pAce = 0;
  Revision = 0;
  Control[0] = 0;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v81 = 0;
  dwAbsoluteSecurityDescriptorSize = 40;
  AceListLength = 0;
  dwDaclSize = 0;
  dwSaclSize[0] = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  dwBufferLength = 0;
  *a8 = 0;
  memset(pSid2, 0, 28);
  memset(pAbsoluteSecurityDescriptor, 0, sizeof(pAbsoluteSecurityDescriptor));
  if ( !a2 || *(_DWORD *)gfADAM )
  {
LABEL_101:
    v22 = a8;
    goto LABEL_102;
  }
  if ( (*(_BYTE *)(a3 + 2) & 4) == 0 )
    goto LABEL_95;
  if ( *(__int16 *)(a3 + 2) >= 0 )
  {
    pSacl = *(struct _ACL **)(a3 + 32);
  }
  else
  {
    if ( !*(_DWORD *)(a3 + 16) )
      goto LABEL_95;
    pSacl = (struct _ACL *)(a3 + *(unsigned int *)(a3 + 16));
  }
  if ( !pSacl )
  {
LABEL_95:
    result = (int)gpDsEventConfig;
    if ( gpDsEventConfig )
    {
      if ( SHIDWORD(gpDsEventConfig[12].Internal) >= (int)pSacl
        || HIDWORD(gpDsEventConfig->Internal) != (_DWORD)pSacl && (unsigned int)DoLogOverride(791, 0)
        || (result = DoLogMsgOverride(2147485628LL)) != 0 )
      {
        v60 = (__int64)pSacl;
        v63 = 0;
        v69 = 0;
        v72 = 0;
        v73 = 0;
        v61 = -2147481668;
        v64 = (int)pSacl;
        v65 = 1;
        Internal = gpDsEventConfig[12].Internal;
        v74 = &v99;
        v68 = pSacl;
        v67 = 791;
        v66 = 1;
        v70 = pSacl;
        v71 = (int)pSacl;
        result = DoLogEventAndTrace(&v60);
      }
      goto LABEL_31;
    }
    goto LABEL_101;
  }
  result = SampBuildNT4FullSid(a5);
  if ( result < 0 || (v12 = pSacl + 1, v13 = 0, result = 0, pAce = &pSacl[1], !pSacl->AceCount) )
  {
LABEL_27:
    pSacl = 0;
    goto LABEL_31;
  }
  v14 = *(_DWORD *)&RIGHT_DS_REPL_GET_CHANGES_ALL.Data4[4];
  v15 = *(_DWORD *)RIGHT_DS_REPL_GET_CHANGES_ALL.Data4;
  v16 = *(_DWORD *)&RIGHT_DS_REPL_GET_CHANGES_ALL.Data2;
  while ( 1 )
  {
    if ( v12->AclRevision != 5 )
      goto LABEL_26;
    v17 = *(_DWORD *)&v12[1].AclRevision;
    if ( ((unsigned __int64)&v12[1].AceCount & -(__int64)((v17 & 1) != 0)) == 0
      || *(_DWORD *)((unsigned __int64)&v12[1].AceCount & -(__int64)((*(_DWORD *)&v12[1].AclRevision & 1) != 0)) != 288487085 )
    {
      goto LABEL_26;
    }
    v18 = (__int64)&v12[2];
    if ( (v17 & 1) == 0 )
      v18 = 4;
    if ( *(_DWORD *)v18 != v16 )
      goto LABEL_26;
    p_AceCount = (__int64)&v12[2].AceCount;
    if ( (v17 & 1) == 0 )
      p_AceCount = 8;
    if ( *(_DWORD *)p_AceCount != v15 )
      goto LABEL_26;
    v20 = (__int64)&v12[3];
    if ( (v17 & 1) == 0 )
      v20 = 12;
    if ( *(_DWORD *)v20 != v14 )
      goto LABEL_26;
    if ( EqualSid(&v12[2 * (v17 & 1) + 1 + (v17 & 2)].AceCount, pSid2) )
      break;
    v12 = (struct _ACL *)pAce;
    v14 = *(_DWORD *)&RIGHT_DS_REPL_GET_CHANGES_ALL.Data4[4];
    v15 = *(_DWORD *)RIGHT_DS_REPL_GET_CHANGES_ALL.Data4;
    v16 = *(_DWORD *)&RIGHT_DS_REPL_GET_CHANGES_ALL.Data2;
LABEL_26:
    ++v13;
    v12 = (struct _ACL *)((char *)v12 + v12->AclSize);
    pAce = v12;
    result = pSacl->AceCount;
    if ( v13 >= result )
      goto LABEL_27;
  }
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor((PSECURITY_DESCRIPTOR)a3, Control, &Revision);
  pSacl = 0;
  if ( ControlSecurityDescriptor < 0 )
    goto LABEL_29;
  pOwner = 0;
  pPrimaryGroup = 0;
  v25 = 0;
  MakeAbsoluteSD(
    (PSECURITY_DESCRIPTOR)a3,
    pAbsoluteSecurityDescriptor,
    &dwAbsoluteSecurityDescriptorSize,
    0,
    &dwDaclSize,
    0,
    dwSaclSize,
    0,
    &dwOwnerSize,
    0,
    &dwPrimaryGroupSize);
  if ( dwDaclSize )
    v25 = (struct _ACL *)THAlloc_(v52, 1, dwDaclSize, 1, 0, 51843099);
  if ( dwSaclSize[0] )
    pSacl = (struct _ACL *)THAlloc_(v52, 1, dwSaclSize[0], 1, 0, 51843102);
  if ( dwOwnerSize )
    pOwner = (void *)THAlloc_(v52, 1, dwOwnerSize, 1, 0, 51843105);
  if ( dwPrimaryGroupSize )
    pPrimaryGroup = (void *)THAlloc_(v52, 1, dwPrimaryGroupSize, 1, 0, 51843108);
  AbsoluteSD = MakeAbsoluteSD(
                 (PSECURITY_DESCRIPTOR)a3,
                 pAbsoluteSecurityDescriptor,
                 &dwAbsoluteSecurityDescriptorSize,
                 v25,
                 &dwDaclSize,
                 pSacl,
                 dwSaclSize,
                 pOwner,
                 &dwOwnerSize,
                 pPrimaryGroup,
                 &dwPrimaryGroupSize);
  pSacl = 0;
  if ( !AbsoluteSD )
  {
    result = GetLastError();
    goto LABEL_30;
  }
  v27 = dwDaclSize;
  v28 = (struct _ACL *)THAlloc_(v52, 1, dwDaclSize, 1, 0, 51843126);
  ControlSecurityDescriptor = RtlCreateAcl(v28, v27, v25->AclRevision);
  pSacl = 0;
  if ( ControlSecurityDescriptor < 0
    || (ControlSecurityDescriptor = RtlGetAcesBufferSize(v25, &AceListLength), ControlSecurityDescriptor < 0)
    || (ControlSecurityDescriptor = RtlAddAce(v28, v25->AclRevision, 0, &v25[1], AceListLength),
        ControlSecurityDescriptor < 0)
    || (ControlSecurityDescriptor = RtlSetDaclSecurityDescriptor(
                                      pAbsoluteSecurityDescriptor,
                                      1u,
                                      v28,
                                      (Control[0] & 8) != 0),
        ControlSecurityDescriptor < 0) )
  {
LABEL_29:
    result = RtlNtStatusToDosError(ControlSecurityDescriptor);
LABEL_30:
    LODWORD(LastError) = result;
    goto LABEL_31;
  }
  result = SampBuildNT4FullSid(a5);
  if ( result < 0 )
    goto LABEL_31;
  v29 = v28 + 1;
  pAce = &v28[1];
  v30 = 0;
  v31 = 0;
  v32 = 0;
  if ( !v28->AceCount )
    goto LABEL_65;
  v33 = *(_DWORD *)&RIGHT_DS_REPL_GET_CHANGES_ALL.Data4[4];
  v34 = *(_DWORD *)RIGHT_DS_REPL_GET_CHANGES_ALL.Data4;
  v35 = *(_DWORD *)&RIGHT_DS_REPL_GET_CHANGES_ALL.Data2;
  while ( 2 )
  {
    if ( v29->AclRevision != 5 )
      goto LABEL_63;
    v36 = *(_DWORD *)&v29[1].AclRevision;
    if ( (-(__int64)((v36 & 1) != 0) & (unsigned __int64)&v29[1].AceCount) == 0
      || *(_DWORD *)((unsigned __int64)&v29[1].AceCount & -(__int64)((v36 & 1) != 0)) != 288487085 )
    {
      goto LABEL_63;
    }
    v37 = (__int64)&v29[2];
    if ( (v36 & 1) == 0 )
      v37 = 4;
    if ( *(_DWORD *)v37 != v35 )
      goto LABEL_63;
    v38 = (__int64)&v29[2].AceCount;
    if ( (v36 & 1) == 0 )
      v38 = 8;
    if ( *(_DWORD *)v38 != v34 )
      goto LABEL_63;
    v39 = (__int64)&v29[3];
    if ( (v36 & 1) == 0 )
      v39 = 12;
    if ( *(_DWORD *)v39 != v33 )
    {
LABEL_63:
      LODWORD(pSacl) = (_DWORD)pSacl + 1;
      v29 = (struct _ACL *)((char *)v29 + v29->AclSize);
      pAce = v29;
      if ( (unsigned int)pSacl >= v28->AceCount )
      {
        v31 = 0;
        goto LABEL_65;
      }
      continue;
    }
    break;
  }
  if ( !EqualSid(&v29[2 * (v36 & 1) + 1 + (v36 & 2)].AceCount, pSid2) )
  {
    v29 = (struct _ACL *)pAce;
    v33 = *(_DWORD *)&RIGHT_DS_REPL_GET_CHANGES_ALL.Data4[4];
    v34 = *(_DWORD *)RIGHT_DS_REPL_GET_CHANGES_ALL.Data4;
    v35 = *(_DWORD *)&RIGHT_DS_REPL_GET_CHANGES_ALL.Data2;
    goto LABEL_63;
  }
  v32 = (unsigned int)pSacl;
  v30 = *((_DWORD *)pAce + 1);
  v31 = *((unsigned __int8 *)pAce + 1);
LABEL_65:
  pSacl = 0;
  if ( DeleteAce(v28, v32) )
  {
    v43 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 9u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( v43 )
    {
      LastError = RtlNtStatusToDosError(v43);
      result = (int)gpDsEventConfig;
      if ( !gpDsEventConfig )
        goto LABEL_31;
      v40 = -1073739843;
      if ( (gpDsEventConfig[12].Internal & 0x8000000000000000uLL) != 0LL
        && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(791, 0)) )
      {
        result = DoLogMsgOverride(3221227453LL);
        if ( !result )
          goto LABEL_31;
      }
      v63 = 0;
    }
    else
    {
      if ( AddAccessAllowedObjectAce(v28, 4u, v31, v30, (GUID *)&RIGHT_DS_REPL_GET_CHANGES_ALL, 0, Sid) )
      {
        if ( FindFirstFreeAce(v28, &pAce) && pAce )
          v28->AclSize = (_WORD)pAce - (_WORD)v28;
        MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength);
        v45 = (void *)THAlloc_(v52, 1, dwBufferLength, 1, 0, 51843255);
        if ( !MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v45, &dwBufferLength) )
        {
          result = GetLastError();
          a1 = v52;
          pSacl = 0;
          v22 = a8;
          LODWORD(LastError) = result;
          a4 = Size;
          goto LABEL_102;
        }
        v46 = a7;
        v22 = a8;
        result = dwBufferLength;
        a1 = v52;
        v41 = a6;
        a4 = Size;
        *a7 = v45;
        pSacl = 0;
        *a8 = result;
        goto LABEL_104;
      }
      LastError = GetLastError();
      result = (int)gpDsEventConfig;
      if ( !gpDsEventConfig )
        goto LABEL_31;
      v40 = -1073739841;
      if ( SHIDWORD(gpDsEventConfig[12].Internal) < 1
        && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(791, 1)) )
      {
        result = DoLogMsgOverride(3221227455LL);
        if ( !result )
          goto LABEL_31;
      }
      v63 = 1;
    }
    v41 = a6;
    v69 = 0;
    v72 = 0;
    v73 = 0;
    v101 = LastError;
    v102 = 6;
    v103 = a6;
    v44 = gpDsEventConfig[12].Internal;
    v74 = &v99;
    v100 = &v101;
    Internal = v44;
    v60 = 2;
LABEL_72:
    v99 = 10;
    v65 = 1;
    v64 = 0;
    v61 = v40;
    v68 = 0;
    v67 = 791;
    v66 = 1;
    v70 = 0;
    v71 = 0;
    result = DoLogEventAndTrace(&v60);
    a1 = v52;
    a4 = Size;
    v22 = a8;
    goto LABEL_103;
  }
  LastError = GetLastError();
  result = (int)gpDsEventConfig;
  if ( gpDsEventConfig )
  {
    if ( (v40 = -1073739842, (gpDsEventConfig[12].Internal & 0x8000000000000000uLL) == 0LL)
      || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(791, 0)
      || (result = DoLogMsgOverride(3221227454LL)) != 0 )
    {
      v41 = a6;
      v63 = 0;
      v69 = 0;
      v72 = 0;
      v73 = 0;
      v102 = 5;
      v105 = 6;
      v106 = a6;
      v42 = gpDsEventConfig[12].Internal;
      v74 = &v99;
      v101 = LastError;
      v104 = LastError;
      Internal = v42;
      v103 = &v104;
      v100 = &v101;
      v60 = 3;
      goto LABEL_72;
    }
  }
LABEL_31:
  a1 = v52;
  v22 = a8;
  a4 = Size;
LABEL_102:
  v41 = a6;
LABEL_103:
  v46 = a7;
LABEL_104:
  if ( *v46 == pSacl )
  {
    v47 = a4;
    v48 = THAlloc_(a1, 1, a4, 1, 0, 51843270);
    v49 = Src;
    *v46 = (void *)v48;
    *v22 = Size;
    result = (unsigned int)memcpy_0(*v46, v49, v47);
    pSacl = 0;
  }
  if ( (_DWORD)LastError )
  {
    result = (int)gpDsEventConfig;
    if ( gpDsEventConfig )
    {
      if ( SHIDWORD(gpDsEventConfig[12].Internal) >= (int)pSacl
        || HIDWORD(gpDsEventConfig->Internal) != (_DWORD)pSacl && (unsigned int)DoLogOverride(791, 0)
        || (result = DoLogMsgOverride(3221227451LL)) != 0 )
      {
        v83 = -1073739845;
        v85 = 0;
        v91 = 0;
        v94 = 0;
        v95 = 0;
        v86 = (int)pSacl;
        v87 = 1;
        v82 = 3;
        v50 = gpDsEventConfig[12].Internal;
        v96 = &v99;
        v84 = v50;
        v101 = (unsigned int)LastError;
        v104 = (unsigned int)LastError;
        v100 = &v101;
        v103 = &v104;
        v99 = 10;
        v102 = 5;
        v105 = 6;
        v106 = v41;
        v90 = pSacl;
        v89 = 791;
        v88 = 1;
        v92 = pSacl;
        v93 = (int)pSacl;
        result = DoLogEventAndTrace(&v82);
      }
    }
  }
  if ( Sid )
    return (unsigned int)RtlFreeSid(Sid);
  return result;
}

```

## disassembly

```asm
0x1800d28f4  mov     [rsp-8+arg_8], rbx
0x1800d28f9  push    rbp
0x1800d28fa  push    rsi
0x1800d28fb  push    rdi
0x1800d28fc  push    r12
0x1800d28fe  push    r13
0x1800d2900  push    r14
0x1800d2902  push    r15
0x1800d2904  lea     rbp, [rsp-320h]
0x1800d290c  sub     rsp, 420h
0x1800d2913  mov     rax, cs:__security_cookie
0x1800d291a  xor     rax, rsp
0x1800d291d  mov     [rbp+350h+var_40], rax
0x1800d2924  mov     rbx, [rbp+350h+arg_30]
0x1800d292b  xor     r10d, r10d
0x1800d292e  mov     r12, [rbp+350h+arg_20]
0x1800d2935  xorps   xmm0, xmm0
0x1800d2938  xor     eax, eax
0x1800d293a  mov     [rbp+350h+Src], r8
0x1800d293e  mov     r13, r8
0x1800d2941  mov     [rsp+450h+var_3E0], rbx
0x1800d2946  mov     r8, [rbp+350h+arg_38]
0x1800d294d  mov     esi, r10d
0x1800d2950  mov     [rbx], r10
0x1800d2953  mov     r14d, 317h
0x1800d2959  xor     ebx, ebx
0x1800d295b  mov     dword ptr [rsp+450h+Size], r9d
0x1800d2960  mov     [rsp+450h+var_3E8], rcx
0x1800d2965  mov     [rsp+450h+var_3D8], r8
0x1800d296a  mov     [rbp+350h+pAce], r10
0x1800d296e  mov     [rbp+350h+Revision], r10d
0x1800d2972  mov     [rbp+350h+Control], r10w
0x1800d2977  mov     [rbp+350h+Sid], r10
0x1800d297b  mov     dword ptr [rbp+350h+IdentifierAuthority.Value], r10d
0x1800d2982  mov     word ptr [rbp+350h+IdentifierAuthority.Value+4], 500h
0x1800d298b  mov     [rbp+350h+var_300], rax
0x1800d298f  mov     [rbp+350h+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x1800d2996  mov     [rbp+350h+AceListLength], r10d
0x1800d299a  mov     [rbp+350h+dwDaclSize], r10d
0x1800d299e  mov     [rbp+350h+dwSaclSize], r10d
0x1800d29a2  mov     [rbp+350h+dwOwnerSize], r10d
0x1800d29a6  mov     [rbp+350h+dwPrimaryGroupSize], r10d
0x1800d29aa  mov     [rbp+350h+dwBufferLength], r10d
0x1800d29ae  mov     [r8], ebx
0x1800d29b1  movups  [rbp+350h+pSid2], xmm0
0x1800d29b8  movups  [rbp+350h+pAbsoluteSecurityDescriptor], xmm0
0x1800d29bc  movups  [rbp+350h+var_310], xmm0
0x1800d29c0  movups  [rbp+350h+pSid2+0Ch], xmm0
0x1800d29c7  test    edx, edx
0x1800d29c9  jz      loc_1800D329C
0x1800d29cf  cmp     cs:gfADAM, ebx
0x1800d29d5  jnz     loc_1800D329C
0x1800d29db  test    byte ptr [r13+2], 4
0x1800d29e0  jz      loc_1800D31FB
0x1800d29e6  cmp     [r13+2], bx
0x1800d29eb  jge     short loc_1800D2A00
0x1800d29ed  cmp     [r13+10h], ebx
0x1800d29f1  jz      loc_1800D31FB
0x1800d29f7  mov     ebx, [r13+10h]
0x1800d29fb  add     rbx, r13
0x1800d29fe  jmp     short loc_1800D2A04
0x1800d2a00  mov     rbx, [r13+20h]
0x1800d2a04  test    rbx, rbx
0x1800d2a07  jz      loc_1800D31FB
0x1800d2a0d  lea     r8, [rbp+350h+pSid2]
0x1800d2a14  mov     edx, 204h
0x1800d2a19  mov     rcx, r12; Src
0x1800d2a1c  call    SampBuildNT4FullSid
0x1800d2a21  test    eax, eax
0x1800d2a23  js      loc_1800D2B25
0x1800d2a29  lea     rdx, [rbx+8]
0x1800d2a2d  xor     edi, edi
0x1800d2a2f  xor     eax, eax
0x1800d2a31  mov     [rbp+350h+pAce], rdx
0x1800d2a35  cmp     ax, [rbx+4]
0x1800d2a39  jnb     loc_1800D2B25
0x1800d2a3f  mov     r11d, dword ptr cs:RIGHT_DS_REPL_GET_CHANGES_ALL.Data4+4
0x1800d2a46  mov     r14d, dword ptr cs:RIGHT_DS_REPL_GET_CHANGES_ALL.Data4
0x1800d2a4d  mov     r15d, dword ptr cs:RIGHT_DS_REPL_GET_CHANGES_ALL.Data2
0x1800d2a54  cmp     byte ptr [rdx], 5
0x1800d2a57  jnz     loc_1800D2B0C
0x1800d2a5d  mov     r10d, [rdx+8]
0x1800d2a61  lea     rcx, [rdx+0Ch]
0x1800d2a65  mov     r8d, r10d
0x1800d2a68  and     r8d, 1
0x1800d2a6c  mov     eax, r8d
0x1800d2a6f  neg     eax
0x1800d2a71  sbb     r9, r9
0x1800d2a74  and     r9, rcx
0x1800d2a77  jz      loc_1800D2B0C
0x1800d2a7d  cmp     dword ptr [r9], 1131F6ADh
0x1800d2a84  jnz     loc_1800D2B0C
0x1800d2a8a  test    r8d, r8d
0x1800d2a8d  lea     rax, [rdx+10h]
0x1800d2a91  mov     ecx, 4
0x1800d2a96  cmovz   rax, rcx
0x1800d2a9a  cmp     [rax], r15d
0x1800d2a9d  jnz     short loc_1800D2B0C
0x1800d2a9f  test    r8d, r8d
0x1800d2aa2  lea     rax, [rdx+14h]
0x1800d2aa6  mov     ecx, 8
0x1800d2aab  cmovz   rax, rcx
0x1800d2aaf  cmp     [rax], r14d
0x1800d2ab2  jnz     short loc_1800D2B0C
0x1800d2ab4  test    r8d, r8d
0x1800d2ab7  lea     rax, [rdx+18h]
0x1800d2abb  mov     ecx, 0Ch
0x1800d2ac0  cmovz   rax, rcx
0x1800d2ac4  cmp     [rax], r11d
0x1800d2ac7  jnz     short loc_1800D2B0C
0x1800d2ac9  and     r10d, 2
0x1800d2acd  mov     eax, r8d
0x1800d2ad0  shl     rax, 4
0x1800d2ad4  add     rax, rdx
0x1800d2ad7  lea     rdx, [rbp+350h+pSid2]; pSid2
0x1800d2ade  lea     rcx, ds:0Ch[r10*8]
0x1800d2ae6  add     rcx, rax; pSid1
0x1800d2ae9  call    cs:__imp_EqualSid
0x1800d2aef  test    eax, eax
0x1800d2af1  jnz     short loc_1800D2B29
0x1800d2af3  mov     rdx, [rbp+350h+pAce]
0x1800d2af7  mov     r11d, dword ptr cs:RIGHT_DS_REPL_GET_CHANGES_ALL.Data4+4
0x1800d2afe  mov     r14d, dword ptr cs:RIGHT_DS_REPL_GET_CHANGES_ALL.Data4
0x1800d2b05  mov     r15d, dword ptr cs:RIGHT_DS_REPL_GET_CHANGES_ALL.Data2
0x1800d2b0c  movzx   eax, word ptr [rdx+2]
0x1800d2b10  inc     edi
0x1800d2b12  add     rdx, rax
0x1800d2b15  mov     [rbp+350h+pAce], rdx
0x1800d2b19  movzx   eax, word ptr [rbx+4]
0x1800d2b1d  cmp     edi, eax
0x1800d2b1f  jb      loc_1800D2A54
0x1800d2b25  xor     ebx, ebx
0x1800d2b27  jmp     short loc_1800D2B4A
0x1800d2b29  lea     r8, [rbp+350h+Revision]; Revision
0x1800d2b2d  mov     rcx, r13; SecurityDescriptor
0x1800d2b30  lea     rdx, [rbp+350h+Control]; Control
0x1800d2b34  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1800d2b3a  xor     ebx, ebx
0x1800d2b3c  test    eax, eax
0x1800d2b3e  jns     short loc_1800D2B5E
0x1800d2b40  mov     ecx, eax; Status
0x1800d2b42  call    cs:__imp_RtlNtStatusToDosError
0x1800d2b48  mov     esi, eax
0x1800d2b4a  mov     rcx, [rsp+450h+var_3E8]
0x1800d2b4f  mov     r15, [rsp+450h+var_3D8]
0x1800d2b54  mov     r9d, dword ptr [rsp+450h+Size]
0x1800d2b59  jmp     loc_1800D329F
0x1800d2b5e  xor     ecx, ecx
0x1800d2b60  lea     rax, [rbp+350h+dwPrimaryGroupSize]
0x1800d2b64  mov     [rsp+450h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1800d2b69  lea     r8, [rbp+350h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800d2b6d  mov     [rsp+450h+pPrimaryGroup], rcx; pPrimaryGroup
0x1800d2b72  lea     rax, [rbp+350h+dwOwnerSize]
0x1800d2b76  mov     [rsp+450h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800d2b7b  lea     rdx, [rbp+350h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800d2b7f  mov     [rsp+450h+pOwner], rcx; pOwner
0x1800d2b84  lea     rax, [rbp+350h+dwSaclSize]
0x1800d2b88  mov     [rsp+450h+lpdwSaclSize], rax; lpdwSaclSize
0x1800d2b8d  mov     edi, ecx
0x1800d2b8f  mov     [rsp+450h+pSacl], rcx; pSacl
0x1800d2b94  lea     rax, [rbp+350h+dwDaclSize]
0x1800d2b98  mov     r15d, ecx
0x1800d2b9b  mov     [rsp+450h+lpdwDaclSize], rax; lpdwDaclSize
0x1800d2ba0  mov     rcx, r13; pSelfRelativeSecurityDescriptor
0x1800d2ba3  xor     r9d, r9d; pDacl
0x1800d2ba6  mov     r14, rbx
0x1800d2ba9  call    cs:__imp_MakeAbsoluteSD
0x1800d2baf  mov     eax, [rbp+350h+dwDaclSize]
0x1800d2bb2  test    eax, eax
0x1800d2bb4  jz      short loc_1800D2BDB
0x1800d2bb6  mov     rcx, [rsp+450h+var_3E8]
0x1800d2bbb  mov     r8d, eax
0x1800d2bbe  lea     eax, [r15+1]
0x1800d2bc2  mov     dword ptr [rsp+450h+pSacl], 317101Bh
0x1800d2bca  mov     r9d, eax
0x1800d2bcd  mov     dword ptr [rsp+450h+lpdwDaclSize], ebx
0x1800d2bd1  mov     edx, eax
0x1800d2bd3  call    THAlloc_
0x1800d2bd8  mov     r14, rax
0x1800d2bdb  mov     ecx, [rbp+350h+dwSaclSize]
0x1800d2bde  test    ecx, ecx
0x1800d2be0  jz      short loc_1800D2C08
0x1800d2be2  mov     eax, 1
0x1800d2be7  mov     dword ptr [rsp+450h+pSacl], 317101Eh
0x1800d2bef  mov     r8d, ecx
0x1800d2bf2  mov     dword ptr [rsp+450h+lpdwDaclSize], ebx
0x1800d2bf6  mov     rcx, [rsp+450h+var_3E8]
0x1800d2bfb  mov     r9d, eax
0x1800d2bfe  mov     edx, eax
0x1800d2c00  call    THAlloc_
0x1800d2c05  mov     rbx, rax
0x1800d2c08  mov     ecx, [rbp+350h+dwOwnerSize]
0x1800d2c0b  test    ecx, ecx
0x1800d2c0d  jz      short loc_1800D2C35
0x1800d2c0f  mov     eax, 1
0x1800d2c14  mov     dword ptr [rsp+450h+pSacl], 3171021h
0x1800d2c1c  mov     r8d, ecx
0x1800d2c1f  mov     dword ptr [rsp+450h+lpdwDaclSize], esi
0x1800d2c23  mov     rcx, [rsp+450h+var_3E8]
0x1800d2c28  mov     r9d, eax
0x1800d2c2b  mov     edx, eax
0x1800d2c2d  call    THAlloc_
0x1800d2c32  mov     rdi, rax
0x1800d2c35  mov     ecx, [rbp+350h+dwPrimaryGroupSize]
0x1800d2c38  test    ecx, ecx
0x1800d2c3a  jz      short loc_1800D2C62
0x1800d2c3c  mov     eax, 1
0x1800d2c41  mov     dword ptr [rsp+450h+pSacl], 3171024h
0x1800d2c49  mov     r8d, ecx
0x1800d2c4c  mov     dword ptr [rsp+450h+lpdwDaclSize], esi
0x1800d2c50  mov     rcx, [rsp+450h+var_3E8]
0x1800d2c55  mov     r9d, eax
0x1800d2c58  mov     edx, eax
0x1800d2c5a  call    THAlloc_
0x1800d2c5f  mov     r15, rax
0x1800d2c62  lea     rax, [rbp+350h+dwPrimaryGroupSize]
0x1800d2c66  mov     r9, r14; pDacl
0x1800d2c69  mov     [rsp+450h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1800d2c6e  lea     r8, [rbp+350h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800d2c72  mov     [rsp+450h+pPrimaryGroup], r15; pPrimaryGroup
0x1800d2c77  lea     rax, [rbp+350h+dwOwnerSize]
0x1800d2c7b  mov     [rsp+450h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800d2c80  lea     rdx, [rbp+350h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800d2c84  mov     [rsp+450h+pOwner], rdi; pOwner
0x1800d2c89  lea     rax, [rbp+350h+dwSaclSize]
0x1800d2c8d  mov     [rsp+450h+lpdwSaclSize], rax; lpdwSaclSize
0x1800d2c92  mov     rcx, r13; pSelfRelativeSecurityDescriptor
0x1800d2c95  lea     rax, [rbp+350h+dwDaclSize]
0x1800d2c99  mov     [rsp+450h+pSacl], rbx; pSacl
0x1800d2c9e  mov     [rsp+450h+lpdwDaclSize], rax; lpdwDaclSize
0x1800d2ca3  call    cs:__imp_MakeAbsoluteSD
0x1800d2ca9  xor     ebx, ebx
0x1800d2cab  test    eax, eax
0x1800d2cad  jnz     short loc_1800D2CBA
0x1800d2caf  call    cs:__imp_GetLastError
0x1800d2cb5  jmp     loc_1800D2B48
0x1800d2cba  mov     ebx, [rbp+350h+dwDaclSize]
0x1800d2cbd  mov     r15d, 1
0x1800d2cc3  mov     rcx, [rsp+450h+var_3E8]
0x1800d2cc8  mov     r8d, ebx
0x1800d2ccb  mov     r9d, r15d
0x1800d2cce  mov     dword ptr [rsp+450h+pSacl], 3171036h
0x1800d2cd6  mov     edx, r15d
0x1800d2cd9  mov     dword ptr [rsp+450h+lpdwDaclSize], esi
0x1800d2cdd  call    THAlloc_
0x1800d2ce2  movzx   r8d, byte ptr [r14]; AclRevision
0x1800d2ce6  mov     edx, ebx; AclSize
0x1800d2ce8  mov     rcx, rax; Acl
0x1800d2ceb  mov     rdi, rax
0x1800d2cee  call    cs:__imp_RtlCreateAcl
0x1800d2cf4  xor     ebx, ebx
0x1800d2cf6  test    eax, eax
0x1800d2cf8  js      loc_1800D2B40
0x1800d2cfe  lea     rdx, [rbp+350h+AceListLength]
0x1800d2d02  mov     rcx, r14
0x1800d2d05  call    cs:__imp_RtlGetAcesBufferSize
0x1800d2d0b  test    eax, eax
0x1800d2d0d  js      loc_1800D2B40
0x1800d2d13  mov     eax, [rbp+350h+AceListLength]
0x1800d2d16  lea     r9, [r14+8]; AceList
0x1800d2d1a  movzx   edx, byte ptr [r14]; AceRevision
0x1800d2d1e  xor     r8d, r8d; StartingAceIndex
0x1800d2d21  mov     rcx, rdi; Acl
0x1800d2d24  mov     dword ptr [rsp+450h+lpdwDaclSize], eax; AceListLength
0x1800d2d28  call    cs:__imp_RtlAddAce
0x1800d2d2e  test    eax, eax
0x1800d2d30  js      loc_1800D2B40
0x1800d2d36  mov     r9b, byte ptr [rbp+350h+Control]
0x1800d2d3a  lea     rcx, [rbp+350h+pAbsoluteSecurityDescriptor]; SecurityDescriptor
0x1800d2d3e  shr     r9b, 3
0x1800d2d42  mov     r8, rdi; Dacl
0x1800d2d45  and     r9b, r15b; DaclDefaulted
0x1800d2d48  mov     dl, r15b; DaclPresent
0x1800d2d4b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800d2d51  test    eax, eax
0x1800d2d53  js      loc_1800D2B40
0x1800d2d59  lea     r8, [rbp+350h+pSid2]
0x1800d2d60  mov     edx, 204h
0x1800d2d65  mov     rcx, r12; Src
0x1800d2d68  call    SampBuildNT4FullSid
0x1800d2d6d  test    eax, eax
0x1800d2d6f  js      loc_1800D2B4A
0x1800d2d75  lea     rdx, [rdi+8]
0x1800d2d79  xor     eax, eax
0x1800d2d7b  mov     [rbp+350h+pAce], rdx
0x1800d2d7f  mov     r13d, ebx
0x1800d2d82  mov     r15d, ebx
0x1800d2d85  mov     r14d, ebx
0x1800d2d88  cmp     ax, [rdi+4]
0x1800d2d8c  jnb     loc_1800D2E83
0x1800d2d92  mov     r11d, dword ptr cs:RIGHT_DS_REPL_GET_CHANGES_ALL.Data4+4
0x1800d2d99  mov     r15d, dword ptr cs:RIGHT_DS_REPL_GET_CHANGES_ALL.Data4
0x1800d2da0  mov     r12d, dword ptr cs:RIGHT_DS_REPL_GET_CHANGES_ALL.Data2
0x1800d2da7  cmp     byte ptr [rdx], 5
0x1800d2daa  jnz     loc_1800D2E67
0x1800d2db0  mov     r10d, [rdx+8]
0x1800d2db4  lea     r9, [rdx+0Ch]
0x1800d2db8  mov     r8d, r10d
0x1800d2dbb  and     r8d, 1
0x1800d2dbf  mov     eax, r8d
  ... truncated ...
```
