# AddAccessAllowedACEToSecurityDescriptor

- ea: `0x18011a4ac`
- end: `0x18011b499`
- name: `AddAccessAllowedACEToSecurityDescriptor`
- size: `4077`
- prototype: ``
- caller_count: `6`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b954c`
- `0x1800be2d0`
- `0x180160c6c`
- `0x18023f1c8`
- `0x1803d1420`
- `0x1803d2070`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x180030af8`
- `0x18011a4ac`
- `0x18011db10`
- `0x180120480`
- `0x180120ecc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011a622`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011a622`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011a68b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011b19c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011a68b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011b19c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18011b282`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18011b282`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18011aa64`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18011aa64`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18011a676`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18011a676`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18011a793`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18011a793`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18011a96f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18011af9e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18011a96f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18011af9e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18011aa8b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18011ace1`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18011b090`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18011aa8b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18011ace1`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18011b090`

## pseudocode

```c
__int64 __fastcall AddAccessAllowedACEToSecurityDescriptor(__int64 a1, __int16 *a2, void *a3, int a4, _QWORD *a5)
{
  int v5; // r13d
  unsigned int SecurityDescriptorDacl; // r12d
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // esi
  BOOL v13; // r14d
  DWORD LengthSid; // edi
  int v15; // esi
  __int64 v16; // rax
  unsigned __int16 *v17; // r13
  int v18; // r14d
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  DWORD v23; // r12d
  struct _ACL *v24; // rax
  struct _ACL *v25; // r14
  __int64 v26; // rdx
  __int64 v27; // rcx
  BOOL v28; // r14d
  __int64 v29; // rdx
  __int64 v30; // rcx
  BOOL v31; // r14d
  DWORD i; // r12d
  __int64 v33; // rdx
  __int64 v34; // rcx
  BOOL v35; // r14d
  __int64 v36; // rbx
  int v37; // edi
  int v38; // r8d
  int v39; // r9d
  __int64 v41; // rdx
  __int64 v42; // rcx
  BOOL v43; // r14d
  __int64 v44; // rdx
  __int64 v45; // rcx
  BOOL v46; // r14d
  __int64 v47; // rdx
  __int64 v48; // rcx
  int v49; // eax
  DWORD v50; // r12d
  struct _ACL *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rcx
  BOOL v54; // r14d
  __int64 v55; // rdx
  __int64 v56; // rcx
  BOOL v57; // r14d
  __int64 v58; // r15
  __int64 v59; // rdx
  __int64 v60; // rcx
  BOOL v61; // r14d
  __int64 v62; // rdx
  __int64 v63; // rcx
  BOOL v64; // r14d
  __int64 v65; // rdx
  __int64 v66; // rcx
  BOOL v67; // r14d
  __int64 v68; // rdx
  __int64 v69; // rcx
  BOOL v70; // r14d
  WINBOOL bDaclDefaulted; // [rsp+5Ch] [rbp-45h] BYREF
  WINBOOL bDaclPresent; // [rsp+60h] [rbp-41h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+68h] [rbp-39h] BYREF
  __int64 v74; // [rsp+70h] [rbp-31h] BYREF
  __int64 v75; // [rsp+78h] [rbp-29h]
  PACL pDacl; // [rsp+80h] [rbp-21h] BYREF
  PACL v77; // [rsp+88h] [rbp-19h] BYREF
  LPVOID pAce; // [rsp+90h] [rbp-11h] BYREF
  __int16 *v79; // [rsp+98h] [rbp-9h]
  _QWORD *v80; // [rsp+A0h] [rbp-1h]
  __int64 pAclInformation; // [rsp+A8h] [rbp+7h] BYREF
  int v82; // [rsp+B0h] [rbp+Fh]

  v5 = a1;
  v75 = a1;
  v79 = a2;
  v80 = a5;
  *a5 = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  v77 = 0;
  pAce = 0;
  pSecurityDescriptor = 0;
  v74 = 0;
  pAclInformation = 0;
  v82 = 0;
  if ( a2[1] >= 0 )
  {
    SecurityDescriptorDacl = 0;
    v12 = 1;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v11, v10)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v11, v10)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v13 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v11, v10)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v11, v10)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v12 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52564886,
        2,
        3,
        v12,
        v13,
        24,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_116;
  }
  LengthSid = GetLengthSid(a3);
  v15 = 1;
  v16 = THAlloc_(v5, 1, LengthSid + 8, 1, 0, 52564895);
  v17 = (unsigned __int16 *)v16;
  if ( !v16 )
  {
    SecurityDescriptorDacl = 0;
    goto LABEL_116;
  }
  *(_WORD *)v16 = 0;
  *(_WORD *)(v16 + 2) = LengthSid + 8;
  *(_DWORD *)(v16 + 4) = a4;
  CopySid(LengthSid, (PSID)(v16 + 8), a3);
  v18 = 0;
  SecurityDescriptorDacl = GetSecurityDescriptorDacl(a2, &bDaclPresent, &pDacl, &bDaclDefaulted);
  if ( !SecurityDescriptorDacl )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v20, v19)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v20, v19)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v20, v19)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v18 = 1;
      }
      if ( !(unsigned int)THStateCheckForTraceOverride(v20, v19)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52564912,
        2,
        3,
        v15,
        v18,
        25,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_116;
  }
  if ( pDacl )
  {
    SecurityDescriptorDacl = GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation);
    if ( !SecurityDescriptorDacl )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v22, v21)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v22, v21)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        if ( gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v22, v21)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v18 = 1;
        }
        if ( !(unsigned int)THStateCheckForTraceOverride(v22, v21)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        {
          v15 = 0;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52564924,
          2,
          3,
          v15,
          v18,
          26,
          &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
      }
      goto LABEL_116;
    }
    v23 = HIDWORD(pAclInformation) + v17[1];
    v24 = (struct _ACL *)THAlloc_(v75, 1, v23, 1, 0, 52564929);
    v25 = v24;
    if ( !v24 )
    {
      SecurityDescriptorDacl = 0;
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v27, v26)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v27, v26)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v28 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v27, v26)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride(v27, v26)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        {
          v15 = 0;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52564932,
          2,
          3,
          v15,
          v28,
          27,
          &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
      }
      goto LABEL_116;
    }
    SecurityDescriptorDacl = InitializeAcl(v24, v23, 4u);
    if ( !SecurityDescriptorDacl )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v30, v29)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v31 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride(v30, v29)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        {
          v15 = 0;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52564938,
          2,
          3,
          v15,
          v31,
          28,
          &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
      }
      goto LABEL_116;
    }
    for ( i = 0; i < (unsigned int)pAclInformation; ++i )
    {
      if ( !GetAce(pDacl, i, &pAce) )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v42, v41)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v42, v41)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v43 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v42, v41)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
          if ( !(unsigned int)THStateCheckForTraceOverride(v42, v41)
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
          {
            v15 = 0;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52564947,
            2,
            3,
            v15,
            v43,
            29,
            (__int64)&WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
        }
        goto LABEL_115;
      }
      if ( !AddAce(v25, 4u, i, pAce, *((unsigned __int16 *)pAce + 1)) )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v34, v33)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v34, v33)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v35 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v34, v33)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
          if ( !(unsigned int)THStateCheckForTraceOverride(v34, v33)
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
          {
            v15 = 0;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52564953,
            2,
            3,
            v15,
            v35,
            30,
            (__int64)&WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
        }
LABEL_115:
        SecurityDescriptorDacl = 0;
        goto LABEL_116;
      }
    }
    SecurityDescriptorDacl = AddAce(v25, 4u, i, v17, v17[1]);
    if ( !SecurityDescriptorDacl )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v45, v44)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v45, v44)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v46 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v45, v44)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride(v45, v44)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        {
          v15 = 0;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52564961,
          2,
          3,
          v15,
          v46,
          31,
          &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
      }
      goto LABEL_116;
    }
  }
  else
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
      || (unsigned int)THStateCheckForTraceOverride(v48, v47)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v48, v47)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v48, v47)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
      {
        v18 = 1;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v48, v47)
        || (v49 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
      {
        v49 = 1;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52564970,
        3,
        3,
        v49,
        v18,
        32,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    v50 = v17[1] + 8;
    v51 = (struct _ACL *)THAlloc_(v75, 1, v50, 1, 0, 52564973);
    v25 = v51;
    if ( !v51 )
    {
      SecurityDescriptorDacl = 0;
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v53, v52)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v53, v52)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v54 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v53, v52)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride(v53, v52)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        {
          v15 = 0;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52564976,
          2,
          3,
          v15,
          v54,
          33,
          &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
      }
      goto LABEL_116;
    }
    SecurityDescriptorDacl = InitializeAcl(v51, v50, 4u);
    if ( !SecurityDescriptorDacl )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v56, v55)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v56, v55)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v57 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v56, v55)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride(v56, v55)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        {
          v15 = 0;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52564982,
          2,
          3,
          v15,
          v57,
          34,
          &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
      }
      goto LABEL_116;
    }
    SecurityDescriptorDacl = AddAce(v25, 4u, 0, v17, v17[1]);
    if ( !SecurityDescriptorDacl )
    {
LABEL_116:
      v36 = 0;
      goto LABEL_117;
    }
  }
  v58 = v75;
  SecurityDescriptorDacl = MakeAbsoluteSDHelper(v75, v79, &pSecurityDescriptor);
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
      v61 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v60, v59)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v60, v59)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52564999,
        2,
        3,
        v15,
        v61,
        35,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_116;
  }
  SecurityDescriptorDacl = GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &v77, &bDaclDefaulted);
  if ( !SecurityDescriptorDacl )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v63, v62)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v63, v62)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v64 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v63, v62)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v63, v62)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565010,
        2,
        3,
        v15,
        v64,
        36,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_116;
  }
  SecurityDescriptorDacl = SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v25, 0);
  if ( !SecurityDescriptorDacl )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v66, v65)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v66, v65)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v67 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v66, v65)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v66, v65)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565021,
        2,
        3,
        v15,
        v67,
        37,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    v77 = 0;
    goto LABEL_116;
  }
  SecurityDescriptorDacl = MakeSelfRelativeSDHelper(v58, pSecurityDescriptor, &v74);
  if ( SecurityDescriptorDacl )
  {
    v36 = 0;
    *v80 = v74;
  }
  else
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v69, v68)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v69, v68)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v70 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v69, v68)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v69, v68)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565035,
        2,
        3,
        v15,
        v70,
        38,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    v36 = v74;
  }
LABEL_117:
  v37 = v75;
  FreeAbsoluteSDHelper(v75, pSecurityDescriptor);
  if ( v36 )
    THFreeAux(v37, v36, v38, v39, 52565047);
  if ( v77 )
    THFreeAux(v37, (_DWORD)v77, v38, v39, 52565049);
  return SecurityDescriptorDacl;
}

```

## disassembly

```asm
0x18011a4ac  mov     [rsp-8+arg_18], rbx
0x18011a4b1  push    rbp
0x18011a4b2  push    rsi
0x18011a4b3  push    rdi
0x18011a4b4  push    r12
0x18011a4b6  push    r13
0x18011a4b8  push    r14
0x18011a4ba  push    r15
0x18011a4bc  lea     rbp, [rsp-1Fh]
0x18011a4c1  sub     rsp, 0C0h
0x18011a4c8  mov     rax, cs:__security_cookie
0x18011a4cf  xor     rax, rsp
0x18011a4d2  mov     [rbp+4Fh+var_38], rax
0x18011a4d6  mov     rax, [rbp+4Fh+arg_20]
0x18011a4da  xor     esi, esi
0x18011a4dc  mov     r13, rcx
0x18011a4df  mov     [rbp+4Fh+var_78], rcx
0x18011a4e3  mov     ecx, esi
0x18011a4e5  mov     [rbp+4Fh+var_58], rdx
0x18011a4e9  mov     r15d, r9d
0x18011a4ec  mov     [rbp+4Fh+var_50], rax
0x18011a4f0  mov     [rax], rsi
0x18011a4f3  mov     rbx, r8
0x18011a4f6  mov     r12, rdx
0x18011a4f9  mov     [rbp+4Fh+bDaclPresent], esi
0x18011a4fc  mov     [rbp+4Fh+bDaclDefaulted], esi
0x18011a4ff  mov     [rbp+4Fh+pDacl], rsi
0x18011a503  mov     [rbp+4Fh+var_68], rsi
0x18011a507  mov     [rbp+4Fh+pAce], rsi
0x18011a50b  mov     [rbp+4Fh+pSecurityDescriptor], rsi
0x18011a50f  mov     [rbp+4Fh+var_A0], rcx
0x18011a513  mov     [rbp+4Fh+var_80], rcx
0x18011a517  mov     [rbp+4Fh+pAclInformation], rcx
0x18011a51b  mov     [rbp+4Fh+var_40], ecx
0x18011a51e  cmp     [rdx+2], si
0x18011a522  jl      loc_18011A61F
0x18011a528  xor     r13d, r13d
0x18011a52b  mov     r12d, r13d
0x18011a52e  lea     ebx, [rsi+2]
0x18011a531  mov     ecx, ebx
0x18011a533  call    IncrementWPPPerfCountersForLevel
0x18011a538  lea     edi, [rsi+3]
0x18011a53b  lea     esi, [rbx-1]
0x18011a53e  test    eax, eax
0x18011a540  jnz     short loc_18011A593
0x18011a542  call    THStateCheckForTraceOverride
0x18011a547  test    eax, eax
0x18011a549  jnz     short loc_18011A593
0x18011a54b  mov     r8d, edi
0x18011a54e  mov     edx, ebx
0x18011a550  xor     ecx, ecx
0x18011a552  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a557  test    eax, eax
0x18011a559  jnz     short loc_18011A593
0x18011a55b  mov     eax, cs:gfTraceToSecondProvider
0x18011a561  test    eax, eax
0x18011a563  jz      loc_18011AB8C
0x18011a569  call    THStateCheckForTraceOverride
0x18011a56e  test    eax, eax
0x18011a570  jnz     short loc_18011A593
0x18011a572  call    ThStateCheckIfTraceToSecondProvier
0x18011a577  test    eax, eax
0x18011a579  jz      loc_18011AB8C
0x18011a57f  mov     r8d, edi
0x18011a582  mov     edx, ebx
0x18011a584  mov     ecx, esi
0x18011a586  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a58b  test    eax, eax
0x18011a58d  jz      loc_18011AB8C
0x18011a593  mov     eax, cs:gfTraceToSecondProvider
0x18011a599  test    eax, eax
0x18011a59b  jz      short loc_18011A5C4
0x18011a59d  call    THStateCheckForTraceOverride
0x18011a5a2  test    eax, eax
0x18011a5a4  jnz     short loc_18011A5BF
0x18011a5a6  call    ThStateCheckIfTraceToSecondProvier
0x18011a5ab  test    eax, eax
0x18011a5ad  jz      short loc_18011A5C4
0x18011a5af  mov     r8d, edi
0x18011a5b2  mov     edx, ebx
0x18011a5b4  mov     ecx, esi
0x18011a5b6  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a5bb  test    eax, eax
0x18011a5bd  jz      short loc_18011A5C4
0x18011a5bf  mov     r14d, esi
0x18011a5c2  jmp     short loc_18011A5C7
0x18011a5c4  mov     r14d, r13d
0x18011a5c7  call    THStateCheckForTraceOverride
0x18011a5cc  test    eax, eax
0x18011a5ce  jnz     short loc_18011A5E3
0x18011a5d0  mov     r8d, edi
0x18011a5d3  mov     edx, ebx
0x18011a5d5  xor     ecx, ecx
0x18011a5d7  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a5dc  test    eax, eax
0x18011a5de  jnz     short loc_18011A5E3
0x18011a5e0  mov     esi, r13d
0x18011a5e3  lea     rax, WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids
0x18011a5ea  mov     edx, 3221396h; int
0x18011a5ef  mov     [rsp+0F0h+var_B8], rax; LPCGUID
0x18011a5f4  mov     [rsp+0F0h+var_C0], 18h; __int16
0x18011a5fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18011a602  mov     r8d, ebx; int
0x18011a605  mov     [rsp+0F0h+var_C8], r14d; int
0x18011a60a  mov     r9d, edi; int
0x18011a60d  mov     [rsp+0F0h+nAceListLength], esi; int
0x18011a611  mov     rcx, [rcx+10h]; int
0x18011a615  call    WPP_SF_
0x18011a61a  jmp     loc_18011AB8C
0x18011a61f  mov     rcx, rbx; pSid
0x18011a622  call    cs:__imp_GetLengthSid
0x18011a628  mov     [rsp+0F0h+var_C8], 322139Fh
0x18011a630  mov     rcx, r13
0x18011a633  mov     [rsp+0F0h+nAceListLength], esi
0x18011a637  mov     edi, eax
0x18011a639  mov     esi, 1
0x18011a63e  lea     r14d, [rax+8]
0x18011a642  mov     r9d, esi
0x18011a645  mov     r8d, r14d
0x18011a648  mov     edx, esi
0x18011a64a  call    THAlloc_
0x18011a64f  mov     r13, rax
0x18011a652  test    rax, rax
0x18011a655  jnz     short loc_18011A65F
0x18011a657  mov     r12d, r13d
0x18011a65a  jmp     loc_18011AB8C
0x18011a65f  lea     rdx, [rax+8]; pDestinationSid
0x18011a663  mov     word ptr [rax], 0
0x18011a668  mov     r8, rbx; pSourceSid
0x18011a66b  mov     [rax+2], r14w
0x18011a670  mov     ecx, edi; nDestinationSidLength
0x18011a672  mov     [rax+4], r15d
0x18011a676  call    cs:__imp_CopySid
0x18011a67c  lea     r9, [rbp+4Fh+bDaclDefaulted]; lpbDaclDefaulted
0x18011a680  mov     rcx, r12; pSecurityDescriptor
0x18011a683  lea     r8, [rbp+4Fh+pDacl]; pDacl
0x18011a687  lea     rdx, [rbp+4Fh+bDaclPresent]; lpbDaclPresent
0x18011a68b  call    cs:__imp_GetSecurityDescriptorDacl
0x18011a691  xor     r14d, r14d
0x18011a694  mov     r12d, eax
0x18011a697  test    eax, eax
0x18011a699  jnz     loc_18011A76C
0x18011a69f  lea     ebx, [rax+2]
0x18011a6a2  mov     ecx, ebx
0x18011a6a4  call    IncrementWPPPerfCountersForLevel
0x18011a6a9  xor     r13d, r13d
0x18011a6ac  lea     edi, [rbx+1]
0x18011a6af  test    eax, eax
0x18011a6b1  jnz     short loc_18011A704
0x18011a6b3  call    THStateCheckForTraceOverride
0x18011a6b8  test    eax, eax
0x18011a6ba  jnz     short loc_18011A704
0x18011a6bc  mov     r8d, edi
0x18011a6bf  mov     edx, ebx
0x18011a6c1  xor     ecx, ecx
0x18011a6c3  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a6c8  test    eax, eax
0x18011a6ca  jnz     short loc_18011A704
0x18011a6cc  mov     eax, cs:gfTraceToSecondProvider
0x18011a6d2  test    eax, eax
0x18011a6d4  jz      loc_18011AB8C
0x18011a6da  call    THStateCheckForTraceOverride
0x18011a6df  test    eax, eax
0x18011a6e1  jnz     short loc_18011A704
0x18011a6e3  call    ThStateCheckIfTraceToSecondProvier
0x18011a6e8  test    eax, eax
0x18011a6ea  jz      loc_18011AB8C
0x18011a6f0  mov     r8d, edi
0x18011a6f3  mov     edx, ebx
0x18011a6f5  mov     ecx, esi
0x18011a6f7  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a6fc  test    eax, eax
0x18011a6fe  jz      loc_18011AB8C
0x18011a704  mov     eax, cs:gfTraceToSecondProvider
0x18011a70a  test    eax, eax
0x18011a70c  jz      short loc_18011A733
0x18011a70e  call    THStateCheckForTraceOverride
0x18011a713  test    eax, eax
0x18011a715  jnz     short loc_18011A730
0x18011a717  call    ThStateCheckIfTraceToSecondProvier
0x18011a71c  test    eax, eax
0x18011a71e  jz      short loc_18011A733
0x18011a720  mov     r8d, edi
0x18011a723  mov     edx, ebx
0x18011a725  mov     ecx, esi
0x18011a727  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a72c  test    eax, eax
0x18011a72e  jz      short loc_18011A733
0x18011a730  mov     r14d, esi
0x18011a733  call    THStateCheckForTraceOverride
0x18011a738  test    eax, eax
0x18011a73a  jnz     short loc_18011A74F
0x18011a73c  mov     r8d, edi
0x18011a73f  mov     edx, ebx
0x18011a741  xor     ecx, ecx
0x18011a743  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a748  test    eax, eax
0x18011a74a  jnz     short loc_18011A74F
0x18011a74c  mov     esi, r13d
0x18011a74f  lea     rax, WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids
0x18011a756  mov     edx, 32213B0h
0x18011a75b  mov     [rsp+0F0h+var_B8], rax
0x18011a760  mov     [rsp+0F0h+var_C0], 19h
0x18011a767  jmp     loc_18011A5FB
0x18011a76c  mov     rcx, [rbp+4Fh+pDacl]; pAcl
0x18011a770  lea     r15, WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids
0x18011a777  mov     edi, 3
0x18011a77c  lea     ebx, [rdi-1]
0x18011a77f  test    rcx, rcx
0x18011a782  jz      loc_18011ADBE
0x18011a788  mov     r9d, ebx; dwAclInformationClass
0x18011a78b  lea     r8d, [rdi+9]; nAclInformationLength
0x18011a78f  lea     rdx, [rbp+4Fh+pAclInformation]; pAclInformation
0x18011a793  call    cs:__imp_GetAclInformation
0x18011a799  mov     r12d, eax
0x18011a79c  test    eax, eax
0x18011a79e  jnz     loc_18011A864
0x18011a7a4  mov     ecx, ebx
0x18011a7a6  call    IncrementWPPPerfCountersForLevel
0x18011a7ab  xor     r13d, r13d
0x18011a7ae  test    eax, eax
0x18011a7b0  jnz     short loc_18011A803
0x18011a7b2  call    THStateCheckForTraceOverride
0x18011a7b7  test    eax, eax
0x18011a7b9  jnz     short loc_18011A803
0x18011a7bb  mov     r8d, edi
0x18011a7be  mov     edx, ebx
0x18011a7c0  xor     ecx, ecx
0x18011a7c2  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a7c7  test    eax, eax
0x18011a7c9  jnz     short loc_18011A803
0x18011a7cb  mov     eax, cs:gfTraceToSecondProvider
0x18011a7d1  test    eax, eax
0x18011a7d3  jz      loc_18011AB8C
0x18011a7d9  call    THStateCheckForTraceOverride
0x18011a7de  test    eax, eax
0x18011a7e0  jnz     short loc_18011A803
0x18011a7e2  call    ThStateCheckIfTraceToSecondProvier
0x18011a7e7  test    eax, eax
0x18011a7e9  jz      loc_18011AB8C
0x18011a7ef  mov     r8d, edi
0x18011a7f2  mov     edx, ebx
0x18011a7f4  mov     ecx, esi
0x18011a7f6  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a7fb  test    eax, eax
0x18011a7fd  jz      loc_18011AB8C
0x18011a803  mov     eax, cs:gfTraceToSecondProvider
0x18011a809  test    eax, eax
0x18011a80b  jz      short loc_18011A832
0x18011a80d  call    THStateCheckForTraceOverride
0x18011a812  test    eax, eax
0x18011a814  jnz     short loc_18011A82F
0x18011a816  call    ThStateCheckIfTraceToSecondProvier
0x18011a81b  test    eax, eax
0x18011a81d  jz      short loc_18011A832
0x18011a81f  mov     r8d, edi
0x18011a822  mov     edx, ebx
0x18011a824  mov     ecx, esi
0x18011a826  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a82b  test    eax, eax
0x18011a82d  jz      short loc_18011A832
0x18011a82f  mov     r14d, esi
0x18011a832  call    THStateCheckForTraceOverride
0x18011a837  test    eax, eax
0x18011a839  jnz     short loc_18011A84E
0x18011a83b  mov     r8d, edi
0x18011a83e  mov     edx, ebx
0x18011a840  xor     ecx, ecx
0x18011a842  call    CheckWPPLevelFlagsEnabledForProvider
0x18011a847  test    eax, eax
0x18011a849  jnz     short loc_18011A84E
0x18011a84b  mov     esi, r13d
0x18011a84e  mov     [rsp+0F0h+var_B8], r15
0x18011a853  mov     edx, 32213BCh
0x18011a858  mov     [rsp+0F0h+var_C0], 1Ah
0x18011a85f  jmp     loc_18011A5FB
0x18011a864  movzx   r12d, word ptr [r13+2]
0x18011a869  mov     r9d, esi
0x18011a86c  add     r12d, dword ptr [rbp+4Fh+pAclInformation+4]
0x18011a870  mov     rdx, rsi
0x18011a873  mov     rcx, [rbp+4Fh+var_78]
0x18011a877  mov     r8d, r12d
0x18011a87a  mov     [rsp+0F0h+var_C8], 32213C1h
0x18011a882  mov     [rsp+0F0h+nAceListLength], r14d
0x18011a887  call    THAlloc_
0x18011a88c  mov     r14, rax
0x18011a88f  test    rax, rax
0x18011a892  jnz     loc_18011A960
0x18011a898  xor     r13d, r13d
0x18011a89b  mov     r12d, r13d
0x18011a89e  mov     ecx, ebx
0x18011a8a0  call    IncrementWPPPerfCountersForLevel
0x18011a8a5  test    eax, eax
0x18011a8a7  jnz     short loc_18011A8FA
0x18011a8a9  call    THStateCheckForTraceOverride
0x18011a8ae  test    eax, eax
0x18011a8b0  jnz     short loc_18011A8FA
0x18011a8b2  mov     r8d, edi
0x18011a8b5  mov     edx, ebx
0x18011a8b7  xor     ecx, ecx
  ... truncated ...
```
