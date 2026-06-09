# AddAccessDeniedObjectACEToSecurityDescriptor

- ea: `0x18011bdd0`
- end: `0x18011cbf7`
- name: `AddAccessDeniedObjectACEToSecurityDescriptor`
- size: `3623`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180160c6c`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x180030af8`
- `0x18011bdd0`
- `0x18011db10`
- `0x180120480`
- `0x180120ecc`
- `0x180123ad4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011c29d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011c397`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011c29d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011c397`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011c180`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011c8dd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011c180`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011c8dd`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18011c9cb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18011c9cb`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18011c6d9`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18011c6d9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18011c4c0`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18011c4c0`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18011c703`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18011c703`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedObjectAce` at `0x18011c5c5`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedObjectAce` at `0x18011c5c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c24e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c24e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c695`

## pseudocode

```c
__int64 __fastcall AddAccessDeniedObjectACEToSecurityDescriptor(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        GUID *a5,
        __int64 a6,
        LPVOID pAce)
{
  _QWORD *v7; // r12
  __int64 v8; // rbx
  struct _ACL *v11; // r13
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  GUID *ObjectTypeGuid; // r15
  int v16; // esi
  int v17; // ebx
  bool v18; // zf
  int v19; // eax
  unsigned int SecurityDescriptorDacl; // r14d
  __int64 v21; // rdx
  __int64 v22; // rcx
  BOOL v23; // ebx
  __int64 v24; // rbx
  int v25; // r8d
  int v26; // r9d
  unsigned int AbsoluteSDHelper; // eax
  int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // r15d
  __int64 v35; // rbx
  int v36; // edx
  __int64 v37; // rcx
  int AclSize; // ebx
  __int64 v39; // rdx
  __int64 v40; // rcx
  BOOL v41; // ebx
  WORD v42; // bx
  unsigned __int16 v43; // ax
  unsigned __int16 v44; // cx
  DWORD v45; // ebx
  struct _ACL *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  BOOL v49; // ebx
  __int64 v50; // rdx
  __int64 v51; // rcx
  BOOL v52; // ebx
  BOOL v53; // eax
  __int64 v54; // rdx
  __int64 v55; // rcx
  DWORD i; // ebx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rcx
  BOOL v63; // ebx
  __int64 v64; // rdx
  __int64 v65; // rcx
  BOOL v66; // ebx
  __int64 v67; // rdx
  __int64 v68; // rcx
  BOOL v69; // ebx
  __int16 pSid; // [rsp+30h] [rbp-50h]
  int v71; // [rsp+38h] [rbp-48h]
  int v72; // [rsp+48h] [rbp-38h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+60h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+68h] [rbp-18h] BYREF
  __int64 v75; // [rsp+70h] [rbp-10h] BYREF
  PACL v76; // [rsp+78h] [rbp-8h] BYREF
  WINBOOL bDaclPresent; // [rsp+C8h] [rbp+48h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+D8h] [rbp+58h] BYREF

  v7 = pAce;
  v8 = a1;
  pDacl = 0;
  v76 = 0;
  v11 = 0;
  *(_QWORD *)pAce = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pSecurityDescriptor = 0;
  a6 = 0;
  v75 = 0;
  v12 = THStateCheckForTraceOverride(0, a2);
  ObjectTypeGuid = a5;
  v16 = 1;
  if ( v12
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v14, v13)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
  {
    v17 = 0;
    if ( gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v14, v13)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
    {
      v17 = 1;
    }
    if ( (unsigned int)THStateCheckForTraceOverride(v14, v13)
      || (v18 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v19 = 0, !v18) )
    {
      v19 = 1;
    }
    WPP_SF__sid_D_guid__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52565323,
      v19,
      v17,
      47,
      v71,
      a3,
      v72,
      (__int64)ObjectTypeGuid);
    v8 = a1;
  }
  if ( *(__int16 *)(a2 + 2) >= 0 )
  {
    SecurityDescriptorDacl = 0;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v22, v21)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v22, v21)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v23 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v22, v21)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v22, v21)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v16 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565330,
        2,
        3,
        v16,
        v23,
        48,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_34;
  }
  AbsoluteSDHelper = MakeAbsoluteSDHelper(v8, a2, &pSecurityDescriptor);
  v29 = 0;
  SecurityDescriptorDacl = AbsoluteSDHelper;
  if ( !AbsoluteSDHelper )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v31, v30)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, SecurityDescriptorDacl + 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v31, v30)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, SecurityDescriptorDacl + 3)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v31, v30)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v29 = 1;
      }
      if ( !(unsigned int)THStateCheckForTraceOverride(v31, v30)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v16 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565341,
        2,
        3,
        v16,
        v29,
        49,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_34;
  }
  SecurityDescriptorDacl = GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted);
  if ( !SecurityDescriptorDacl )
  {
    v34 = 0;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v33, v32)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, SecurityDescriptorDacl + 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v33, v32)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, SecurityDescriptorDacl + 3)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v33, v32)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v34 = 1;
      }
      if ( !(unsigned int)THStateCheckForTraceOverride(v33, v32)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v16 = 0;
      }
      v35 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      GetLastError();
      v36 = 52565353;
      pSid = 50;
      goto LABEL_76;
    }
    goto LABEL_34;
  }
  AclSize = pDacl->AclSize;
  if ( GetLengthSid(a3) + AclSize + 44 > 0xFFFF )
  {
    SecurityDescriptorDacl = 0;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v40, v39)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v40, v39)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v41 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v40, v39)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v40, v39)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v16 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565368,
        2,
        3,
        v16,
        v41,
        51,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_34;
  }
  v42 = pDacl->AclSize;
  v43 = v42 + 12 + GetLengthSid(a3);
  SecurityDescriptorDacl = 0;
  v44 = v43 + 16;
  if ( !ObjectTypeGuid )
    v44 = v43;
  v45 = v44;
  v46 = (struct _ACL *)THAlloc_(a1, 1, v44, 1, 0, 52565384);
  v11 = v46;
  if ( !v46 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v48, v47)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v48, v47)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v49 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v48, v47)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v48, v47)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v16 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565387,
        2,
        3,
        v16,
        v49,
        52,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_34;
  }
  SecurityDescriptorDacl = InitializeAcl(v46, v45, 4u);
  if ( !SecurityDescriptorDacl )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v51, v50)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v51, v50)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v52 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v51, v50)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v51, v50)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v16 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565393,
        2,
        3,
        v16,
        v52,
        53,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_34;
  }
  v53 = AddAccessDeniedObjectAce(v11, 4u, 1u, 0x20u, ObjectTypeGuid, 0, a3);
  v34 = 0;
  SecurityDescriptorDacl = v53;
  if ( !v53 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v55, v54)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, SecurityDescriptorDacl + 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v55, v54)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, SecurityDescriptorDacl + 3)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v55, v54)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v34 = 1;
      }
      if ( !(unsigned int)THStateCheckForTraceOverride(v55, v54)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v16 = 0;
      }
      v35 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      GetLastError();
      v36 = 52565410;
      pSid = 54;
LABEL_76:
      LODWORD(v37) = v35;
LABEL_77:
      WPP_SF__ATTRTYP_LOG_(v37, v36, 2, 3, v16, v34, pSid, (__int64)&WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
LABEL_34:
    v24 = a6;
    goto LABEL_35;
  }
  for ( i = 0; i < pDacl->AceCount; ++i )
  {
    pAce = 0;
    SecurityDescriptorDacl = GetAce(pDacl, i, &pAce);
    if ( !SecurityDescriptorDacl )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v60, v59)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v60, v59)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        if ( gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v60, v59)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v34 = 1;
        }
        if ( !(unsigned int)THStateCheckForTraceOverride(v60, v59)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        {
          v16 = 0;
        }
        v36 = 52565420;
        pSid = 55;
        goto LABEL_172;
      }
      goto LABEL_34;
    }
    SecurityDescriptorDacl = AddAce(v11, 4u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1));
    if ( !SecurityDescriptorDacl )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v58, v57)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v58, v57)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        if ( gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v58, v57)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v34 = 1;
        }
        if ( !(unsigned int)THStateCheckForTraceOverride(v58, v57)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        {
          v16 = 0;
        }
        v36 = 52565426;
        pSid = 56;
LABEL_172:
        v37 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        goto LABEL_77;
      }
      goto LABEL_34;
    }
  }
  SecurityDescriptorDacl = GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &v76, &bDaclDefaulted);
  if ( !SecurityDescriptorDacl )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v62, v61)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, SecurityDescriptorDacl + 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v62, v61)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, SecurityDescriptorDacl + 3)) )
    {
      v63 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v62, v61)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v62, v61)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v16 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565437,
        2,
        3,
        v16,
        v63,
        57,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_34;
  }
  SecurityDescriptorDacl = SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v11, 0);
  if ( !SecurityDescriptorDacl )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v65, v64)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, SecurityDescriptorDacl + 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v65, v64)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, SecurityDescriptorDacl + 3)) )
    {
      v66 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v65, v64)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v65, v64)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v16 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565448,
        2,
        3,
        v16,
        v66,
        58,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    v76 = 0;
    goto LABEL_34;
  }
  v11 = 0;
  SecurityDescriptorDacl = MakeSelfRelativeSDHelper(a1, pSecurityDescriptor, &v75);
  if ( SecurityDescriptorDacl )
  {
    v24 = 0;
    *v7 = v75;
  }
  else
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v68, v67)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, SecurityDescriptorDacl + 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v68, v67)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, SecurityDescriptorDacl + 3)) )
    {
      v69 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v68, v67)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v68, v67)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v16 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565462,
        2,
        3,
        v16,
        v69,
        59,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    v24 = v75;
  }
LABEL_35:
  FreeAbsoluteSDHelper(a1, pSecurityDescriptor);
  if ( v24 )
    THFreeAux(a1, v24, v25, v26, 52565474);
  if ( v76 )
    THFreeAux(a1, (_DWORD)v76, v25, v26, 52565475);
  v76 = 0;
  if ( v11 )
    THFreeAux(a1, (_DWORD)v11, v25, v26, 52565476);
  return SecurityDescriptorDacl;
}

```

## disassembly

```asm
0x18011bdd0  mov     [rsp-38h+arg_10], rbx
0x18011bdd5  mov     [rsp-38h+bDaclDefaulted], r9d
0x18011bdda  mov     [rsp-38h+arg_0], rcx
0x18011bddf  push    rbp
0x18011bde0  push    rsi
0x18011bde1  push    rdi
0x18011bde2  push    r12
0x18011bde4  push    r13
0x18011bde6  push    r14
0x18011bde8  push    r15
0x18011bdea  mov     rbp, rsp
0x18011bded  sub     rsp, 80h
0x18011bdf4  mov     r12, [rbp+pAce]
0x18011bdf8  mov     rbx, rcx
0x18011bdfb  xor     ecx, ecx
0x18011bdfd  mov     rdi, r8
0x18011be00  mov     r14, rdx
0x18011be03  mov     [rbp+pDacl], rcx
0x18011be07  mov     [rbp+var_8], rcx
0x18011be0b  mov     r13d, ecx
0x18011be0e  mov     [r12], rcx
0x18011be12  mov     [rbp+bDaclPresent], ecx
0x18011be15  mov     [rbp+bDaclDefaulted], ecx
0x18011be18  mov     [rbp+pSecurityDescriptor], rcx
0x18011be1c  mov     [rbp+arg_28], rcx
0x18011be20  mov     [rbp+var_10], rcx
0x18011be24  call    THStateCheckForTraceOverride
0x18011be29  mov     r15, [rbp+arg_20]
0x18011be2d  lea     esi, [r13+1]
0x18011be31  test    eax, eax
0x18011be33  jnz     short loc_18011BE81
0x18011be35  lea     edx, [rsi+3]
0x18011be38  xor     ecx, ecx
0x18011be3a  lea     r8d, [r13+3]
0x18011be3e  call    CheckWPPLevelFlagsEnabledForProvider
0x18011be43  test    eax, eax
0x18011be45  jnz     short loc_18011BE81
0x18011be47  mov     eax, cs:gfTraceToSecondProvider
0x18011be4d  test    eax, eax
0x18011be4f  jz      loc_18011BF06
0x18011be55  call    THStateCheckForTraceOverride
0x18011be5a  test    eax, eax
0x18011be5c  jnz     short loc_18011BE81
0x18011be5e  call    ThStateCheckIfTraceToSecondProvier
0x18011be63  test    eax, eax
0x18011be65  jz      loc_18011BF06
0x18011be6b  lea     edx, [rsi+3]
0x18011be6e  mov     ecx, esi
0x18011be70  lea     r8d, [r13+3]
0x18011be74  call    CheckWPPLevelFlagsEnabledForProvider
0x18011be79  test    eax, eax
0x18011be7b  jz      loc_18011BF06
0x18011be81  mov     eax, cs:gfTraceToSecondProvider
0x18011be87  xor     ebx, ebx
0x18011be89  test    eax, eax
0x18011be8b  jz      short loc_18011BEB3
0x18011be8d  call    THStateCheckForTraceOverride
0x18011be92  test    eax, eax
0x18011be94  jnz     short loc_18011BEB1
0x18011be96  call    ThStateCheckIfTraceToSecondProvier
0x18011be9b  test    eax, eax
0x18011be9d  jz      short loc_18011BEB3
0x18011be9f  lea     edx, [rbx+4]
0x18011bea2  mov     ecx, esi
0x18011bea4  lea     r8d, [rbx+3]
0x18011bea8  call    CheckWPPLevelFlagsEnabledForProvider
0x18011bead  test    eax, eax
0x18011beaf  jz      short loc_18011BEB3
0x18011beb1  mov     ebx, esi
0x18011beb3  call    THStateCheckForTraceOverride
0x18011beb8  xor     ecx, ecx
0x18011beba  test    eax, eax
0x18011bebc  jnz     short loc_18011BED2
0x18011bebe  lea     edx, [rcx+4]
0x18011bec1  lea     r8d, [rcx+3]
0x18011bec5  call    CheckWPPLevelFlagsEnabledForProvider
0x18011beca  xor     ecx, ecx
0x18011becc  test    eax, eax
0x18011bece  mov     eax, ecx
0x18011bed0  jz      short loc_18011BED4
0x18011bed2  mov     eax, esi
0x18011bed4  mov     rcx, cs:WPP_GLOBAL_Control
0x18011bedb  mov     edx, 322154Bh; int
0x18011bee0  mov     [rsp+80h+var_30], r15; __int64
0x18011bee5  mov     [rsp+80h+var_40], rdi; pSid
0x18011beea  mov     word ptr [rsp+80h+pSid], 2Fh ; '/'; __int16
0x18011bef1  mov     rcx, [rcx+10h]; int
0x18011bef5  mov     dword ptr [rsp+80h+InheritedObjectTypeGuid], ebx; int
0x18011bef9  mov     dword ptr [rsp+80h+ObjectTypeGuid], eax; int
0x18011befd  call    WPP_SF__sid_D_guid__guid_
0x18011bf02  mov     rbx, [rbp+arg_0]
0x18011bf06  xor     eax, eax
0x18011bf08  cmp     [r14+2], ax
0x18011bf0d  jl      loc_18011C085
0x18011bf13  xor     r15d, r15d
0x18011bf16  mov     r14d, r15d
0x18011bf19  lea     edi, [rax+2]
0x18011bf1c  mov     ecx, edi
0x18011bf1e  call    IncrementWPPPerfCountersForLevel
0x18011bf23  test    eax, eax
0x18011bf25  jnz     short loc_18011BF7A
0x18011bf27  call    THStateCheckForTraceOverride
0x18011bf2c  test    eax, eax
0x18011bf2e  jnz     short loc_18011BF7A
0x18011bf30  lea     r8d, [r15+3]
0x18011bf34  mov     edx, edi
0x18011bf36  xor     ecx, ecx
0x18011bf38  call    CheckWPPLevelFlagsEnabledForProvider
0x18011bf3d  test    eax, eax
0x18011bf3f  jnz     short loc_18011BF7A
0x18011bf41  mov     eax, cs:gfTraceToSecondProvider
0x18011bf47  test    eax, eax
0x18011bf49  jz      loc_18011C006
0x18011bf4f  call    THStateCheckForTraceOverride
0x18011bf54  test    eax, eax
0x18011bf56  jnz     short loc_18011BF7A
0x18011bf58  call    ThStateCheckIfTraceToSecondProvier
0x18011bf5d  test    eax, eax
0x18011bf5f  jz      loc_18011C006
0x18011bf65  lea     r8d, [r15+3]
0x18011bf69  mov     edx, edi
0x18011bf6b  mov     ecx, esi
0x18011bf6d  call    CheckWPPLevelFlagsEnabledForProvider
0x18011bf72  test    eax, eax
0x18011bf74  jz      loc_18011C006
0x18011bf7a  mov     eax, cs:gfTraceToSecondProvider
0x18011bf80  test    eax, eax
0x18011bf82  jz      short loc_18011BFAD
0x18011bf84  call    THStateCheckForTraceOverride
0x18011bf89  test    eax, eax
0x18011bf8b  jnz     short loc_18011BFA9
0x18011bf8d  call    ThStateCheckIfTraceToSecondProvier
0x18011bf92  test    eax, eax
0x18011bf94  jz      short loc_18011BFAD
0x18011bf96  mov     r8d, 3
0x18011bf9c  mov     edx, edi
0x18011bf9e  mov     ecx, esi
0x18011bfa0  call    CheckWPPLevelFlagsEnabledForProvider
0x18011bfa5  test    eax, eax
0x18011bfa7  jz      short loc_18011BFAD
0x18011bfa9  mov     ebx, esi
0x18011bfab  jmp     short loc_18011BFB0
0x18011bfad  mov     ebx, r15d
0x18011bfb0  call    THStateCheckForTraceOverride
0x18011bfb5  test    eax, eax
0x18011bfb7  jnz     short loc_18011BFCD
0x18011bfb9  lea     r8d, [rax+3]
0x18011bfbd  mov     edx, edi
0x18011bfbf  xor     ecx, ecx
0x18011bfc1  call    CheckWPPLevelFlagsEnabledForProvider
0x18011bfc6  test    eax, eax
0x18011bfc8  jnz     short loc_18011BFCD
0x18011bfca  mov     esi, r15d
0x18011bfcd  lea     rax, WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids
0x18011bfd4  mov     edx, 3221552h; int
0x18011bfd9  mov     [rsp+80h+var_48], rax; LPCGUID
0x18011bfde  mov     word ptr [rsp+80h+pSid], 30h ; '0'; __int16
0x18011bfe5  mov     rcx, cs:WPP_GLOBAL_Control
0x18011bfec  mov     r8d, edi; int
0x18011bfef  mov     dword ptr [rsp+80h+InheritedObjectTypeGuid], ebx; int
0x18011bff3  mov     r9d, 3; int
0x18011bff9  mov     dword ptr [rsp+80h+ObjectTypeGuid], esi; int
0x18011bffd  mov     rcx, [rcx+10h]; int
0x18011c001  call    WPP_SF_
0x18011c006  mov     rbx, [rbp+arg_28]
0x18011c00a  mov     rsi, [rbp+arg_0]
0x18011c00e  mov     rdx, [rbp+pSecurityDescriptor]
0x18011c012  mov     rcx, rsi
0x18011c015  call    FreeAbsoluteSDHelper
0x18011c01a  test    rbx, rbx
0x18011c01d  jz      short loc_18011C032
0x18011c01f  mov     rdx, rbx
0x18011c022  mov     dword ptr [rsp+80h+ObjectTypeGuid], 32215E2h
0x18011c02a  mov     rcx, rsi
0x18011c02d  call    THFreeAux
0x18011c032  mov     rdx, [rbp+var_8]
0x18011c036  test    rdx, rdx
0x18011c039  jz      short loc_18011C04B
0x18011c03b  mov     rcx, rsi
0x18011c03e  mov     dword ptr [rsp+80h+ObjectTypeGuid], 32215E3h
0x18011c046  call    THFreeAux
0x18011c04b  mov     [rbp+var_8], r15
0x18011c04f  test    r13, r13
0x18011c052  jz      short loc_18011C067
0x18011c054  mov     rdx, r13
0x18011c057  mov     dword ptr [rsp+80h+ObjectTypeGuid], 32215E4h
0x18011c05f  mov     rcx, rsi
0x18011c062  call    THFreeAux
0x18011c067  mov     rbx, [rsp+80h+arg_10]
0x18011c06f  mov     eax, r14d
0x18011c072  add     rsp, 80h
0x18011c079  pop     r15
0x18011c07b  pop     r14
0x18011c07d  pop     r13
0x18011c07f  pop     r12
0x18011c081  pop     rdi
0x18011c082  pop     rsi
0x18011c083  pop     rbp
0x18011c084  retn
0x18011c085  lea     r8, [rbp+pSecurityDescriptor]
0x18011c089  mov     rdx, r14
0x18011c08c  mov     rcx, rbx
0x18011c08f  call    MakeAbsoluteSDHelper
0x18011c094  xor     ebx, ebx
0x18011c096  mov     r14d, eax
0x18011c099  test    eax, eax
0x18011c09b  jnz     loc_18011C170
0x18011c0a1  lea     edi, [rax+2]
0x18011c0a4  mov     ecx, edi
0x18011c0a6  call    IncrementWPPPerfCountersForLevel
0x18011c0ab  xor     r15d, r15d
0x18011c0ae  test    eax, eax
0x18011c0b0  jnz     short loc_18011C105
0x18011c0b2  call    THStateCheckForTraceOverride
0x18011c0b7  test    eax, eax
0x18011c0b9  jnz     short loc_18011C105
0x18011c0bb  lea     r8d, [r14+3]
0x18011c0bf  mov     edx, edi
0x18011c0c1  xor     ecx, ecx
0x18011c0c3  call    CheckWPPLevelFlagsEnabledForProvider
0x18011c0c8  test    eax, eax
0x18011c0ca  jnz     short loc_18011C105
0x18011c0cc  mov     eax, cs:gfTraceToSecondProvider
0x18011c0d2  test    eax, eax
0x18011c0d4  jz      loc_18011C006
0x18011c0da  call    THStateCheckForTraceOverride
0x18011c0df  test    eax, eax
0x18011c0e1  jnz     short loc_18011C105
0x18011c0e3  call    ThStateCheckIfTraceToSecondProvier
0x18011c0e8  test    eax, eax
0x18011c0ea  jz      loc_18011C006
0x18011c0f0  lea     r8d, [r14+3]
0x18011c0f4  mov     edx, edi
0x18011c0f6  mov     ecx, esi
0x18011c0f8  call    CheckWPPLevelFlagsEnabledForProvider
0x18011c0fd  test    eax, eax
0x18011c0ff  jz      loc_18011C006
0x18011c105  mov     eax, cs:gfTraceToSecondProvider
0x18011c10b  test    eax, eax
0x18011c10d  jz      short loc_18011C136
0x18011c10f  call    THStateCheckForTraceOverride
0x18011c114  test    eax, eax
0x18011c116  jnz     short loc_18011C134
0x18011c118  call    ThStateCheckIfTraceToSecondProvier
0x18011c11d  test    eax, eax
0x18011c11f  jz      short loc_18011C136
0x18011c121  mov     r8d, 3
0x18011c127  mov     edx, edi
0x18011c129  mov     ecx, esi
0x18011c12b  call    CheckWPPLevelFlagsEnabledForProvider
0x18011c130  test    eax, eax
0x18011c132  jz      short loc_18011C136
0x18011c134  mov     ebx, esi
0x18011c136  call    THStateCheckForTraceOverride
0x18011c13b  test    eax, eax
0x18011c13d  jnz     short loc_18011C153
0x18011c13f  lea     r8d, [rax+3]
0x18011c143  mov     edx, edi
0x18011c145  xor     ecx, ecx
0x18011c147  call    CheckWPPLevelFlagsEnabledForProvider
0x18011c14c  test    eax, eax
0x18011c14e  jnz     short loc_18011C153
0x18011c150  mov     esi, r15d
0x18011c153  lea     rax, WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids
0x18011c15a  mov     edx, 322155Dh
0x18011c15f  mov     [rsp+80h+var_48], rax
0x18011c164  mov     word ptr [rsp+80h+pSid], 31h ; '1'
0x18011c16b  jmp     loc_18011BFE5
0x18011c170  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18011c174  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18011c178  lea     r8, [rbp+pDacl]; pDacl
0x18011c17c  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18011c180  call    cs:__imp_GetSecurityDescriptorDacl
0x18011c186  mov     r14d, eax
0x18011c189  test    eax, eax
0x18011c18b  jnz     loc_18011C292
0x18011c191  lea     edi, [rax+2]
0x18011c194  mov     ecx, edi
0x18011c196  call    IncrementWPPPerfCountersForLevel
0x18011c19b  xor     r15d, r15d
0x18011c19e  test    eax, eax
0x18011c1a0  jnz     short loc_18011C1F5
0x18011c1a2  call    THStateCheckForTraceOverride
0x18011c1a7  test    eax, eax
0x18011c1a9  jnz     short loc_18011C1F5
0x18011c1ab  lea     r8d, [r14+3]
0x18011c1af  mov     edx, edi
0x18011c1b1  xor     ecx, ecx
0x18011c1b3  call    CheckWPPLevelFlagsEnabledForProvider
0x18011c1b8  test    eax, eax
0x18011c1ba  jnz     short loc_18011C1F5
0x18011c1bc  mov     eax, cs:gfTraceToSecondProvider
0x18011c1c2  test    eax, eax
0x18011c1c4  jz      loc_18011C006
0x18011c1ca  call    THStateCheckForTraceOverride
0x18011c1cf  test    eax, eax
0x18011c1d1  jnz     short loc_18011C1F5
0x18011c1d3  call    ThStateCheckIfTraceToSecondProvier
0x18011c1d8  test    eax, eax
0x18011c1da  jz      loc_18011C006
  ... truncated ...
```
