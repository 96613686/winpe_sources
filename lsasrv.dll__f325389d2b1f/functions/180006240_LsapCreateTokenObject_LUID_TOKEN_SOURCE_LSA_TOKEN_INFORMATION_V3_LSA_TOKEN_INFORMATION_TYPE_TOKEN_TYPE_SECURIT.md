# LsapCreateTokenObject(_LUID *,_TOKEN_SOURCE *,_LSA_TOKEN_INFORMATION_V3 *,_LSA_TOKEN_INFORMATION_TYPE,_TOKEN_TYPE,_SECURITY_IMPERSONATION_LEVEL,uchar,uchar *,uchar *,uchar *,void * *)

- ea: `0x180006240`
- end: `0x180006bc6`
- name: `?LsapCreateTokenObject@@YAJPEAU_LUID@@PEAU_TOKEN_SOURCE@@PEAU_LSA_TOKEN_INFORMATION_V3@@W4_LSA_TOKEN_INFORMATION_TYPE@@W4_TOKEN_TYPE@@W4_SECURITY_IMPERSONATION_LEVEL@@EPEAE66PEAPEAX@Z`
- size: `2438`
- prototype: `__int64 __fastcall(struct _LUID *, struct _TOKEN_SOURCE *, struct _LSA_TOKEN_INFORMATION_V3 *, enum _LSA_TOKEN_INFORMATION_TYPE, enum _TOKEN_TYPE, enum _SECURITY_IMPERSONATION_LEVEL, char, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, void **)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005966c`
- `0x18005af80`
- `0x1800d0d04`
- `0x1800f05e4`

## callees

- `0x180006240`
- `0x180006bcc`
- `0x180006f58`
- `0x180007880`
- `0x18000c300`
- `0x180016f70`
- `0x180086c2c`
- `0x1800b1a84`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bbbfc`
- `0x1800bc2c4`

## import_xrefs

- `ntdll!NtCreateTokenEx` at `0x180006625`
- `ntdll!NtCreateTokenEx` at `0x180006625`
- `ntdll!RtlFreeHeap` at `0x180006657`
- `ntdll!RtlFreeHeap` at `0x18000667a`
- `ntdll!RtlFreeHeap` at `0x180006657`
- `ntdll!RtlFreeHeap` at `0x18000667a`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000670b`
- `ntdll!RtlSubAuthorityCountSid` at `0x180006723`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000670b`
- `ntdll!RtlSubAuthorityCountSid` at `0x180006723`
- `ntdll!RtlSubAuthoritySid` at `0x180006737`
- `ntdll!RtlSubAuthoritySid` at `0x180006737`
- `ntdll!NtClose` at `0x18000681c`
- `ntdll!NtClose` at `0x18000681c`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000691f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006951`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006981`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000691f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006951`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006981`
- `ntdll!RtlCreateAcl` at `0x1800068f7`
- `ntdll!RtlCreateAcl` at `0x1800068f7`
- `ntdll!RtlLengthSid` at `0x1800068a8`
- `ntdll!RtlLengthSid` at `0x1800068ba`
- `ntdll!RtlLengthSid` at `0x1800069e6`
- `ntdll!RtlLengthSid` at `0x1800068a8`
- `ntdll!RtlLengthSid` at `0x1800068ba`
- `ntdll!RtlLengthSid` at `0x1800069e6`
- `ntdll!RtlEqualSid` at `0x18000643b`
- `ntdll!RtlEqualSid` at `0x180006461`
- `ntdll!RtlEqualSid` at `0x1800064c7`
- `ntdll!RtlEqualSid` at `0x1800064ec`
- `ntdll!RtlEqualSid` at `0x180006b16`
- `ntdll!RtlEqualSid` at `0x18000643b`
- `ntdll!RtlEqualSid` at `0x180006461`
- `ntdll!RtlEqualSid` at `0x1800064c7`
- `ntdll!RtlEqualSid` at `0x1800064ec`
- `ntdll!RtlEqualSid` at `0x180006b16`
- `ntdll!NtSetInformationToken` at `0x180006777`
- `ntdll!NtSetInformationToken` at `0x180006a5b`
- `ntdll!NtSetInformationToken` at `0x180006777`
- `ntdll!NtSetInformationToken` at `0x180006a5b`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeSecurityAttributesInfo` at `0x180006b93`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeSecurityAttributesInfo` at `0x180006bb5`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeSecurityAttributesInfo` at `0x180006b93`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeSecurityAttributesInfo` at `0x180006bb5`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIDecodeClaimsBlob` at `0x18000685d`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIDecodeClaimsBlob` at `0x18000685d`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtLogonPerUserAuditing` at `0x180006802`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtLogonPerUserAuditing` at `0x180006802`

## pseudocode

```c
__int64 __fastcall LsapCreateTokenObject(
        struct _LUID *a1,
        struct _TOKEN_SOURCE *a2,
        struct _LSA_TOKEN_INFORMATION_V3 *a3,
        enum _LSA_TOKEN_INFORMATION_TYPE a4,
        enum _TOKEN_TYPE a5,
        enum _SECURITY_IMPERSONATION_LEVEL a6,
        unsigned __int8 a7,
        unsigned __int8 *a8,
        unsigned __int8 *a9,
        unsigned __int8 *a10,
        void **a11)
{
  struct _LSA_TOKEN_INFORMATION_V3 *v11; // r13
  __int128 *v12; // r14
  __int128 *v13; // rsi
  struct _TOKEN_OWNER *p_DefaultDacl; // rdx
  struct _TOKEN_PRIVILEGES *Privileges; // rax
  TOKEN_OWNER *p_Owner; // rcx
  bool v17; // zf
  struct _TOKEN_PRIVILEGES *v18; // r15
  struct _TOKEN_USER *v19; // rcx
  struct _RTL_BALANCED_NODE *v20; // r12
  int TokenDacl; // eax
  void *v22; // rdx
  __int64 GroupCount; // rcx
  __int64 v24; // r8
  PVOID v25; // rdi
  NTSTATUS Acl; // ebx
  unsigned int v27; // eax
  unsigned int v28; // eax
  _DWORD *p_GroupCount; // rax
  PSID v30; // rbx
  BOOL v31; // eax
  unsigned int v32; // ebx
  _DWORD *v33; // rax
  unsigned int v34; // r14d
  _DWORD *v35; // r15
  unsigned int v36; // r13d
  __int128 v37; // xmm0
  __int64 v38; // rax
  unsigned int v39; // r15d
  unsigned int v40; // edi
  unsigned int v41; // r13d
  PSID *v42; // rsi
  PSID v43; // r14
  __int64 v44; // rax
  PACL *v45; // r15
  PTOKEN_GROUPS DeviceGroups; // rdi
  char v47; // cl
  _DWORD *v48; // rbx
  PSID *p_Sid; // rdi
  HANDLE *v50; // r13
  PUCHAR v52; // rax
  ULONG v53; // eax
  unsigned __int8 v54; // al
  unsigned __int8 v55; // dl
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  PCLAIMS_BLOB UserClaims; // rbx
  PSID v60; // rsi
  PSID v61; // rdi
  unsigned int i; // ecx
  _DWORD *v63; // rax
  ULONG v64; // ebx
  ULONG v65; // ebx
  __int64 v66; // rax
  __int64 v67; // rdx
  HANDLE v68; // rcx
  int v69; // r14d
  struct _SAM_CLAIMS_BLOB *DeviceClaims; // rdx
  struct _SID_AND_ATTRIBUTES *v71; // [rsp+28h] [rbp-E8h]
  TOKEN_USER *p_User; // [rsp+30h] [rbp-E0h]
  PTOKEN_GROUPS v73; // [rsp+58h] [rbp-B8h]
  TOKEN_PRIMARY_GROUP *p_PrimaryGroup; // [rsp+70h] [rbp-A0h]
  unsigned __int8 v75; // [rsp+90h] [rbp-80h] BYREF
  bool v76; // [rsp+91h] [rbp-7Fh]
  unsigned __int8 v77[6]; // [rsp+92h] [rbp-7Eh] BYREF
  PVOID v78; // [rsp+98h] [rbp-78h] BYREF
  unsigned int v79; // [rsp+A0h] [rbp-70h]
  __int128 *v80; // [rsp+A8h] [rbp-68h]
  __int128 *v81; // [rsp+B0h] [rbp-60h]
  PVOID P; // [rsp+B8h] [rbp-58h]
  BOOL v83; // [rsp+C0h] [rbp-50h]
  enum _LSA_TOKEN_INFORMATION_TYPE v84; // [rsp+C4h] [rbp-4Ch]
  int TokenInformation; // [rsp+C8h] [rbp-48h] BYREF
  struct _LSA_TOKEN_INFORMATION_V3 *v86; // [rsp+D0h] [rbp-40h]
  struct _LUID *v87; // [rsp+D8h] [rbp-38h]
  PSID Sid[2]; // [rsp+E0h] [rbp-30h] BYREF
  __int128 v89; // [rsp+F0h] [rbp-20h] BYREF
  __int128 v90; // [rsp+100h] [rbp-10h]
  __int128 v91; // [rsp+110h] [rbp+0h]
  struct _TOKEN_SOURCE *v92; // [rsp+120h] [rbp+10h]
  TOKEN_OWNER *v93; // [rsp+128h] [rbp+18h]
  struct _TOKEN_PRIVILEGES *v94; // [rsp+130h] [rbp+20h]
  void **v95; // [rsp+138h] [rbp+28h]
  unsigned __int8 *v96; // [rsp+140h] [rbp+30h]
  unsigned __int8 *v97; // [rsp+148h] [rbp+38h]
  unsigned __int8 *v98; // [rsp+150h] [rbp+40h]
  TOKEN_DEFAULT_DACL *v99; // [rsp+158h] [rbp+48h]
  __int128 v100; // [rsp+160h] [rbp+50h] BYREF
  __int128 v101; // [rsp+170h] [rbp+60h] BYREF
  __int64 v102; // [rsp+180h] [rbp+70h] BYREF
  int v103; // [rsp+188h] [rbp+78h]
  __int128 v104; // [rsp+190h] [rbp+80h] BYREF
  PSID v105[22]; // [rsp+1A0h] [rbp+90h] BYREF
  _RTL_BALANCED_NODE v106; // [rsp+250h] [rbp+140h] BYREF

  v96 = a8;
  v11 = a3;
  v97 = a9;
  v12 = 0;
  v13 = 0;
  v98 = a10;
  v86 = a3;
  v92 = a2;
  v87 = a1;
  v102 = 0;
  v103 = 0;
  v84 = a4;
  v95 = a11;
  v104 = 0;
  v81 = 0;
  v100 = 0;
  v80 = 0;
  v101 = 0;
  v78 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  memset_0(v105, 0, 0xA8u);
  p_DefaultDacl = (struct _TOKEN_OWNER *)&v11->DefaultDacl;
  Privileges = v11->Privileges;
  p_Owner = &v11->Owner;
  if ( !v11->Owner.Owner )
    p_Owner = 0;
  v75 = 0;
  v17 = p_DefaultDacl->Owner == 0;
  v18 = (struct _TOKEN_PRIVILEGES *)&v104;
  v93 = p_Owner;
  v19 = (struct _TOKEN_USER *)&v11->DefaultDacl;
  v77[0] = 0;
  if ( v17 )
    v19 = 0;
  TokenInformation = 3;
  v99 = &v11->DefaultDacl;
  P = v19;
  if ( Privileges )
    v18 = Privileges;
  *a11 = 0;
  v94 = v18;
  v20 = &v106;
  TokenDacl = LsapCreateTokenDacl(v19, p_DefaultDacl, &v11->User, v105, (struct _ACL **)&v78);
  v25 = v78;
  Acl = TokenDacl;
  if ( TokenDacl < 0 )
    goto LABEL_97;
  Acl = LsapIntegrityLevelFromUserAndGroupSids(
          a7,
          &v11->User.User,
          v11->Groups->Groups,
          v11->Groups->GroupCount,
          v18,
          (struct _SID_AND_ATTRIBUTES *)Sid);
  if ( Acl < 0 )
    goto LABEL_97;
  GroupCount = v11->Groups->GroupCount;
  v27 = GroupCount + 1;
  if ( (int)GroupCount + 1 < (unsigned int)GroupCount )
  {
    Acl = -1073741801;
LABEL_97:
    v45 = (PACL *)P;
    goto LABEL_38;
  }
  if ( v27 > 0xFFFFFFF )
  {
    v45 = (PACL *)P;
    Acl = -1073741801;
  }
  else
  {
    v28 = 16 * v27;
    GroupCount = v28 + 24;
    if ( (unsigned int)GroupCount >= v28 )
    {
      if ( (unsigned int)GroupCount > 0x80 )
      {
        v20 = (struct _RTL_BALANCED_NODE *)LsapAllocate(GroupCount);
        if ( !v20 )
        {
          v45 = (PACL *)P;
          Acl = -1073741801;
          goto LABEL_38;
        }
      }
      p_GroupCount = &v11->Groups->GroupCount;
      v30 = Sid[0];
      v76 = 0;
      LODWORD(v20->Children[0]) = *p_GroupCount;
      if ( v30 )
      {
        if ( *RtlSubAuthorityCountSid(v30) )
        {
          v52 = RtlSubAuthorityCountSid(v30);
          v53 = *RtlSubAuthoritySid(v30, (unsigned int)*v52 - 1);
          ++LODWORD(v20->Children[0]);
          v76 = v53 == 0x2000;
        }
        else
        {
          ++LODWORD(v20->Children[0]);
          v76 = 0;
        }
      }
      v31 = v30 != 0;
      v32 = 0;
      v83 = v31;
      v33 = &v11->Groups->GroupCount;
      v79 = 0;
      v34 = *v33;
      v35 = v33 + 2;
      if ( *v33 )
      {
        v36 = 0;
        do
        {
          if ( RtlEqualSid(*(PSID *)&v35[4 * (_QWORD)v13], *((PSID *)WellKnownSids + 354)) )
          {
            v36 |= 1u;
          }
          else if ( RtlEqualSid(*(PSID *)&v35[4 * (_QWORD)v13], *((PSID *)WellKnownSids + 360)) )
          {
            v36 |= 2u;
          }
          v37 = *(_OWORD *)&v35[4 * (_QWORD)v13];
          v13 = (__int128 *)((char *)v13 + 1);
          v38 = 2LL * v32++;
          *(_OWORD *)(&v20->Right + v38) = v37;
        }
        while ( v32 < v34 );
        v79 = v36;
        v11 = v86;
      }
      v39 = v83;
      v40 = 0;
      if ( v83 )
      {
        v41 = v79;
        do
        {
          v42 = &Sid[2 * v40];
          v43 = *v42;
          if ( RtlEqualSid(*v42, *((PSID *)WellKnownSids + 354)) )
          {
            v41 |= 1u;
          }
          else if ( RtlEqualSid(v43, *((PSID *)WellKnownSids + 360)) )
          {
            v41 |= 2u;
          }
          ++v40;
          v44 = 2LL * v32++;
          *(_OWORD *)(&v20->Right + v44) = *(_OWORD *)v42;
        }
        while ( v40 < v39 );
        v79 = v41;
        v11 = v86;
      }
      LODWORD(v20->Children[0]) = v32;
      if ( a7 )
      {
        if ( P )
        {
          v61 = 0;
          for ( i = 0; ; ++i )
          {
            v63 = &v11->Groups->GroupCount;
            if ( i >= *v63 )
              break;
            v67 = 16LL * i;
            v17 = (v63[(unsigned __int64)v67 / 4 + 4] & 0xC0000000) == 0;
            v63[(unsigned __int64)v67 / 4 + 4] &= 0xC0000000;
            if ( !v17 )
            {
              _mm_lfence();
              v61 = v11->Groups->Groups[(unsigned __int64)v67 / 0x10].Sid;
              break;
            }
          }
          v64 = RtlLengthSid(*((PSID *)WellKnownSids + 90));
          v65 = RtlLengthSid(v11->User.User.Sid) + v64 + 32;
          if ( v61 )
            v65 += RtlLengthSid(v61) + 8;
          v66 = LsapAllocate(v65);
          v45 = (PACL *)v66;
          if ( !v66 )
          {
            Acl = -1073741801;
            goto LABEL_72;
          }
          *(_QWORD *)v66 = v66 + 8;
          Acl = RtlCreateAcl((PACL)(v66 + 8), v65 - 8, 2u);
          if ( Acl < 0 )
            goto LABEL_72;
          Acl = RtlAddAccessAllowedAce(*v45, 2u, 0x10000000u, v11->User.User.Sid);
          if ( Acl < 0 )
            goto LABEL_72;
          Acl = RtlAddAccessAllowedAce(*v45, 2u, 0x10000000u, *((PSID *)WellKnownSids + 90));
          if ( Acl < 0 )
            goto LABEL_72;
          if ( v61 )
          {
            Acl = RtlAddAccessAllowedAce(*v45, 2u, 0xA0000000, v61);
            if ( Acl < 0 )
              goto LABEL_72;
          }
        }
        else
        {
          v45 = 0;
        }
      }
      else
      {
        v45 = (PACL *)P;
      }
      DeviceGroups = 0;
      if ( v84 != LsaTokenInformationV3 )
        goto LABEL_33;
      v47 = v79;
      if ( (v79 & 1) != 0 )
      {
        UserClaims = v11->UserClaims.UserClaims;
        if ( UserClaims )
        {
          v60 = v11->User.User.Sid;
          if ( !(unsigned __int8)IsSamIDecodeClaimsBlobPresent(v79, v22, v24) )
          {
            Acl = -1073741637;
            goto LABEL_72;
          }
          Acl = SamIDecodeClaimsBlob(v60, UserClaims, &v100);
          if ( Acl < 0 )
          {
LABEL_72:
            v13 = v80;
            v12 = v80;
            goto LABEL_37;
          }
          v47 = v79;
          v81 = &v100;
        }
      }
      v48 = &v11->DeviceGroups->GroupCount;
      if ( v48 && (v47 & 2) != 0 )
      {
        v69 = *v48;
        v13 = 0;
        DeviceGroups = v11->DeviceGroups;
        if ( *v48 )
        {
          do
          {
            if ( RtlEqualSid(*(PSID *)&v48[4 * --v69 + 2], *((PSID *)WellKnownSids + 354)) )
              LODWORD(v13) = 1;
          }
          while ( v69 );
          v11 = v86;
          if ( (_DWORD)v13 && (DeviceClaims = (struct _SAM_CLAIMS_BLOB *)v86->DeviceClaims.DeviceClaims) != 0 )
          {
            Acl = LsapSamExtDecodeClaimsBlob(
                    v86->User.User.Sid,
                    DeviceClaims,
                    (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)&v101);
            if ( Acl < 0 )
            {
              v13 = v80;
              v12 = v81;
              goto LABEL_37;
            }
            v13 = &v101;
          }
          else
          {
            v13 = v80;
          }
        }
      }
      else
      {
LABEL_33:
        v13 = 0;
      }
      LODWORD(v89) = 48;
      *((_QWORD *)&v89 + 1) = 0;
      DWORD2(v90) = 0;
      *(_QWORD *)&v90 = 0;
      if ( v78 )
        *(_QWORD *)&v91 = v105;
      else
        *(_QWORD *)&v91 = 0;
      v12 = v81;
      HIDWORD(v102) = a6;
      *((_QWORD *)&v91 + 1) = &v102;
      p_PrimaryGroup = &v11->PrimaryGroup;
      v73 = DeviceGroups;
      p_Sid = &v11->User.User.Sid;
      p_User = &v11->User;
      v71 = (struct _SID_AND_ATTRIBUTES *)v11;
      v50 = v95;
      LOWORD(v103) = 1;
      LODWORD(v102) = 12;
      Acl = NtCreateTokenEx(
              v95,
              983551,
              &v89,
              (unsigned int)a5,
              v87,
              v71,
              p_User,
              v20,
              v94,
              v81,
              v13,
              v73,
              0,
              v93,
              p_PrimaryGroup,
              v45,
              v92);
      if ( Acl < 0 )
        goto LABEL_37;
      Acl = NtSetInformationToken(*v50, TokenMandatoryPolicy, &TokenInformation, 4u);
      if ( Acl >= 0 )
      {
        v54 = v76;
        if ( !v76 || a7 )
        {
          v55 = v75;
LABEL_57:
          if ( v96 && !a7 )
          {
            *v96 = v54;
            if ( v97 && v54 )
              *v97 = v55;
            if ( v98 && v54 )
              *v98 = v77[0];
          }
          Acl = LsapAdjustTokenObjectIntegrity(*v50);
          if ( Acl >= 0 )
          {
            if ( !(unsigned __int8)IsLsapAdtInitParametersArrayPresent(v57, v56, v58) )
              goto LABEL_37;
            Acl = LsapAdtLogonPerUserAuditing(*p_Sid, v87, *v50);
            if ( Acl >= 0 )
              goto LABEL_37;
          }
          goto LABEL_68;
        }
        Acl = LsapShouldSplitToken(*p_Sid, *v50, &v75, v77);
        if ( Acl >= 0 )
        {
          v55 = v75;
          if ( !v75 )
          {
LABEL_95:
            v54 = v76;
            goto LABEL_57;
          }
          v68 = *v50;
          *(_OWORD *)Sid = *(_OWORD *)&MandatoryMediumPlusSa.Revision;
          Acl = NtSetInformationToken(v68, TokenIntegrityLevel, Sid, 0x10u);
          if ( Acl >= 0 )
          {
            v55 = v75;
            goto LABEL_95;
          }
        }
      }
LABEL_68:
      NtClose(*v50);
      *v50 = 0;
LABEL_37:
      v25 = v78;
      goto LABEL_38;
    }
    v45 = (PACL *)P;
    Acl = -1073741801;
  }
LABEL_38:
  if ( v45 != (PACL *)v99 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v45);
  if ( v25 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v25);
  if ( v20 && v20 != &v106 )
    LsapSubProv_FreeRoutine(v20, v22);
  if ( v12 && (unsigned __int8)IsSamIDecodeClaimsBlobPresent(GroupCount, v22, v24) )
    SamIFreeSecurityAttributesInfo(&v100);
  if ( v13 && (unsigned __int8)IsSamIDecodeClaimsBlobPresent(GroupCount, v22, v24) )
    SamIFreeSecurityAttributesInfo(&v101);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x180006240  mov     [rsp-8+arg_18], rbx
0x180006245  push    rbp
0x180006246  push    rsi
0x180006247  push    rdi
0x180006248  push    r12
0x18000624a  push    r13
0x18000624c  push    r14
0x18000624e  push    r15
0x180006250  lea     rbp, [rsp-1D0h]
0x180006258  sub     rsp, 2E0h
0x18000625f  mov     rax, cs:__security_cookie
0x180006266  xor     rax, rsp
0x180006269  mov     [rbp+200h+var_40], rax
0x180006270  mov     rax, [rbp+200h+arg_38]
0x180006277  xorps   xmm1, xmm1
0x18000627a  mov     rbx, [rbp+200h+arg_50]
0x180006281  xor     edi, edi
0x180006283  mov     [rbp+200h+var_1D0], rax
0x180006287  xorps   xmm0, xmm0
0x18000628a  mov     rax, [rbp+200h+arg_40]
0x180006291  mov     r13, r8
0x180006294  mov     [rbp+200h+var_1C8], rax
0x180006298  mov     r14d, edi
0x18000629b  mov     rax, [rbp+200h+arg_48]
0x1800062a2  mov     esi, edi
0x1800062a4  mov     [rbp+200h+var_1C0], rax
0x1800062a8  xor     eax, eax
0x1800062aa  mov     [rbp+200h+var_240], r8
0x1800062ae  mov     r8d, 0A8h; Size
0x1800062b4  mov     [rbp+200h+var_1F0], rdx
0x1800062b8  xor     edx, edx; Val
0x1800062ba  mov     [rbp+200h+var_238], rcx
0x1800062be  lea     rcx, [rbp+200h+var_170]; void *
0x1800062c5  mov     [rbp+200h+var_190], rax
0x1800062c9  mov     [rbp+200h+var_188], eax
0x1800062cc  mov     [rbp+200h+var_24C], r9d
0x1800062d0  mov     [rbp+200h+var_1D8], rbx
0x1800062d4  movups  [rbp+200h+var_180], xmm0
0x1800062db  mov     [rbp+200h+var_260], rdi
0x1800062df  movups  [rbp+200h+var_1B0], xmm1
0x1800062e3  mov     [rbp+200h+var_268], rdi
0x1800062e7  movups  [rbp+200h+var_1A0], xmm0
0x1800062eb  mov     [rbp+200h+var_278], rdi
0x1800062ef  movups  [rbp+200h+var_220], xmm1
0x1800062f3  movups  [rbp+200h+var_210], xmm1
0x1800062f7  movups  [rbp+200h+var_200], xmm1
0x1800062fb  call    memset_0
0x180006300  cmp     [r13+30h], rdi
0x180006304  lea     rdx, [r13+38h]; struct _TOKEN_OWNER *
0x180006308  mov     rax, [r13+28h]
0x18000630c  lea     rcx, [r13+30h]
0x180006310  cmovz   rcx, rdi
0x180006314  mov     [rbp+200h+var_280], sil
0x180006318  cmp     [rdx], rdi
0x18000631b  lea     r15, [rbp+200h+var_180]
0x180006322  mov     [rbp+200h+var_1E8], rcx
0x180006326  lea     r8, [r13+8]; struct _TOKEN_USER *
0x18000632a  mov     rcx, rdx
0x18000632d  mov     [rbp+200h+var_27E], sil
0x180006331  cmovz   rcx, rdi; struct _TOKEN_USER *
0x180006335  mov     [rbp+200h+TokenInformation], 3
0x18000633c  test    rax, rax
0x18000633f  mov     [rbp+200h+var_1B8], rdx
0x180006343  lea     r9, [rbp+200h+var_170]; void *
0x18000634a  mov     [rbp+200h+P], rcx
0x18000634e  cmovnz  r15, rax
0x180006352  mov     [rbx], rdi
0x180006355  lea     rax, [rbp+200h+var_278]
0x180006359  mov     [rbp+200h+var_1E0], r15
0x18000635d  mov     [rsp+310h+var_2F0], rax; struct _ACL **
0x180006362  lea     r12, [rbp+200h+var_C0]
0x180006369  call    ?LsapCreateTokenDacl@@YAJPEAU_TOKEN_USER@@PEAU_TOKEN_OWNER@@0PEAXPEAPEAU_ACL@@@Z; LsapCreateTokenDacl(_TOKEN_USER *,_TOKEN_OWNER *,_TOKEN_USER *,void *,_ACL * *)
0x18000636e  mov     rdi, [rbp+200h+var_278]
0x180006372  mov     ebx, eax
0x180006374  test    eax, eax
0x180006376  js      loc_180006A83
0x18000637c  mov     r9, [r13+18h]
0x180006380  lea     rax, [rbp+200h+Sid]
0x180006384  movzx   ecx, [rbp+200h+arg_30]; int
0x18000638b  lea     rdx, [r13+8]; struct _SID_AND_ATTRIBUTES *
0x18000638f  mov     [rsp+310h+var_2E8], rax; struct _SID_AND_ATTRIBUTES *
0x180006394  mov     [rsp+310h+var_2F0], r15; struct _TOKEN_PRIVILEGES *
0x180006399  lea     r8, [r9+8]; struct _SID_AND_ATTRIBUTES *
0x18000639d  mov     r9d, [r9]; unsigned int
0x1800063a0  call    ?LsapIntegrityLevelFromUserAndGroupSids@@YAJHPEAU_SID_AND_ATTRIBUTES@@0KPEAU_TOKEN_PRIVILEGES@@0@Z; LsapIntegrityLevelFromUserAndGroupSids(int,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,ulong,_TOKEN_PRIVILEGES *,_SID_AND_ATTRIBUTES *)
0x1800063a5  mov     ebx, eax
0x1800063a7  test    eax, eax
0x1800063a9  js      loc_180006A83
0x1800063af  mov     rax, [r13+18h]
0x1800063b3  mov     ecx, [rax]
0x1800063b5  lea     eax, [rcx+1]
0x1800063b8  cmp     eax, ecx
0x1800063ba  jb      loc_180006A7E
0x1800063c0  cmp     eax, 0FFFFFFFh
0x1800063c5  ja      loc_1800069C1
0x1800063cb  shl     eax, 4
0x1800063ce  lea     ecx, [rax+18h]
0x1800063d1  cmp     ecx, eax
0x1800063d3  jb      loc_1800069FC
0x1800063d9  cmp     ecx, 80h
0x1800063df  ja      loc_1800066D3
0x1800063e5  mov     rax, [r13+18h]
0x1800063e9  mov     rbx, [rbp+200h+Sid]
0x1800063ed  mov     [rbp+200h+var_27F], sil
0x1800063f1  mov     ecx, [rax]
0x1800063f3  mov     [r12], ecx
0x1800063f7  test    rbx, rbx
0x1800063fa  jnz     loc_180006708
0x180006400  xor     eax, eax
0x180006402  test    rbx, rbx
0x180006405  setnz   al
0x180006408  xor     ebx, ebx
0x18000640a  mov     [rbp+200h+var_250], eax
0x18000640d  mov     rax, [r13+18h]
0x180006411  mov     [rbp+200h+var_270], ebx
0x180006414  mov     r14d, [rax]
0x180006417  lea     r15, [rax+8]
0x18000641b  test    r14d, r14d
0x18000641e  jz      short loc_180006497
0x180006420  mov     r13d, ebx
0x180006423  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18000642a  mov     rdi, rsi
0x18000642d  add     rdi, rdi
0x180006430  mov     rdx, [rdx+0B10h]; Sid2
0x180006437  mov     rcx, [r15+rdi*8]; Sid1
0x18000643b  call    cs:__imp_RtlEqualSid
0x180006442  nop     dword ptr [rax+rax+00h]
0x180006447  test    al, al
0x180006449  jnz     loc_180006A8C
0x18000644f  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180006456  mov     rcx, [r15+rdi*8]; Sid1
0x18000645a  mov     rdx, [rdx+0B40h]; Sid2
0x180006461  call    cs:__imp_RtlEqualSid
0x180006468  nop     dword ptr [rax+rax+00h]
0x18000646d  test    al, al
0x18000646f  jnz     loc_180006A95
0x180006475  movups  xmm0, xmmword ptr [r15+rdi*8]
0x18000647a  mov     eax, ebx
0x18000647c  inc     rsi
0x18000647f  add     rax, rax
0x180006482  inc     ebx
0x180006484  movups  xmmword ptr [r12+rax*8+8], xmm0
0x18000648a  cmp     ebx, r14d
0x18000648d  jb      short loc_180006423
0x18000648f  mov     [rbp+200h+var_270], r13d
0x180006493  mov     r13, [rbp+200h+var_240]
0x180006497  mov     r15d, [rbp+200h+var_250]
0x18000649b  xor     edi, edi
0x18000649d  test    r15d, r15d
0x1800064a0  jz      short loc_18000651F
0x1800064a2  mov     r13d, [rbp+200h+var_270]
0x1800064a6  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800064ad  lea     rsi, [rbp+200h+Sid]
0x1800064b1  mov     eax, edi
0x1800064b3  shl     rax, 4
0x1800064b7  add     rsi, rax
0x1800064ba  mov     rdx, [rdx+0B10h]; Sid2
0x1800064c1  mov     r14, [rsi]
0x1800064c4  mov     rcx, r14; Sid1
0x1800064c7  call    cs:__imp_RtlEqualSid
0x1800064ce  nop     dword ptr [rax+rax+00h]
0x1800064d3  test    al, al
0x1800064d5  jnz     loc_1800066CA
0x1800064db  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800064e2  mov     rcx, r14; Sid1
0x1800064e5  mov     rdx, [rdx+0B40h]; Sid2
0x1800064ec  call    cs:__imp_RtlEqualSid
0x1800064f3  nop     dword ptr [rax+rax+00h]
0x1800064f8  test    al, al
0x1800064fa  jnz     loc_180006A9E
0x180006500  movups  xmm0, xmmword ptr [rsi]
0x180006503  mov     eax, ebx
0x180006505  inc     edi
0x180006507  add     rax, rax
0x18000650a  inc     ebx
0x18000650c  movups  xmmword ptr [r12+rax*8+8], xmm0
0x180006512  cmp     edi, r15d
0x180006515  jb      short loc_1800064A6
0x180006517  mov     [rbp+200h+var_270], r13d
0x18000651b  mov     r13, [rbp+200h+var_240]
0x18000651f  cmp     [rbp+200h+arg_30], 0
0x180006526  mov     [r12], ebx
0x18000652a  jnz     loc_18000687F
0x180006530  mov     r15, [rbp+200h+P]
0x180006534  xor     edi, edi
0x180006536  cmp     [rbp+200h+var_24C], 3
0x18000653a  jnz     short loc_180006555
0x18000653c  mov     ecx, [rbp+200h+var_270]
0x18000653f  test    cl, 1
0x180006542  jnz     loc_180006835
0x180006548  mov     rbx, [r13+50h]
0x18000654c  test    rbx, rbx
0x18000654f  jnz     loc_180006ADA
0x180006555  mov     rsi, rdi
0x180006558  cmp     [rbp+200h+var_278], 0
0x18000655d  mov     dword ptr [rbp+200h+var_220], 30h ; '0'
0x180006564  mov     qword ptr [rbp+200h+var_220+8], 0
0x18000656c  mov     dword ptr [rbp+200h+var_210+8], 0
0x180006573  mov     qword ptr [rbp+200h+var_210], 0
0x18000657b  jz      loc_180006757
0x180006581  lea     rax, [rbp+200h+var_170]
0x180006588  mov     qword ptr [rbp+200h+var_200], rax
0x18000658c  mov     eax, [rbp+200h+arg_28]
0x180006592  lea     r8, [rbp+200h+var_220]
0x180006596  mov     rcx, [rbp+200h+var_1F0]
0x18000659a  mov     edx, 0F01FFh
0x18000659f  mov     r14, [rbp+200h+var_260]
0x1800065a3  mov     r9d, [rbp+200h+arg_20]
0x1800065aa  mov     [rsp+310h+var_290], rcx
0x1800065b2  mov     [rsp+310h+var_298], r15
0x1800065b7  mov     dword ptr [rbp+200h+var_190+4], eax
0x1800065ba  lea     rax, [rbp+200h+var_190]
0x1800065be  mov     qword ptr [rbp+200h+var_200+8], rax
0x1800065c2  lea     rax, [r13+20h]
0x1800065c6  mov     [rsp+310h+var_2A0], rax
0x1800065cb  mov     rax, [rbp+200h+var_1E8]
0x1800065cf  mov     [rsp+310h+var_2A8], rax
0x1800065d4  mov     rax, [rbp+200h+var_1E0]
0x1800065d8  mov     [rsp+310h+var_2B0], 0
0x1800065e1  mov     [rsp+310h+var_2B8], rdi
0x1800065e6  lea     rdi, [r13+8]
0x1800065ea  mov     [rsp+310h+var_2C0], rsi
0x1800065ef  mov     [rsp+310h+var_2C8], r14
0x1800065f4  mov     [rsp+310h+var_2D0], rax
0x1800065f9  mov     rax, [rbp+200h+var_238]
0x1800065fd  mov     [rsp+310h+var_2D8], r12
0x180006602  mov     [rsp+310h+var_2E0], rdi
0x180006607  mov     [rsp+310h+var_2E8], r13
0x18000660c  mov     r13, [rbp+200h+var_1D8]
0x180006610  mov     rcx, r13
0x180006613  mov     word ptr [rbp+200h+var_188], 1
0x180006619  mov     dword ptr [rbp+200h+var_190], 0Ch
0x180006620  mov     [rsp+310h+var_2F0], rax
0x180006625  call    cs:__imp_NtCreateTokenEx
0x18000662c  nop     dword ptr [rax+rax+00h]
0x180006631  mov     ebx, eax
0x180006633  test    eax, eax
0x180006635  jns     loc_180006764
0x18000663b  mov     rdi, [rbp+200h+var_278]
0x18000663f  cmp     r15, [rbp+200h+var_1B8]
0x180006643  jz      short loc_180006663
0x180006645  mov     rcx, gs:60h
0x18000664e  mov     r8, r15; P
0x180006651  xor     edx, edx; Flags
0x180006653  mov     rcx, [rcx+30h]; HeapHandle
0x180006657  call    cs:__imp_RtlFreeHeap
0x18000665e  nop     dword ptr [rax+rax+00h]
0x180006663  test    rdi, rdi
0x180006666  jz      short loc_180006686
0x180006668  mov     rcx, gs:60h
0x180006671  mov     r8, rdi; P
0x180006674  xor     edx, edx; Flags
0x180006676  mov     rcx, [rcx+30h]; HeapHandle
0x18000667a  call    cs:__imp_RtlFreeHeap
0x180006681  nop     dword ptr [rax+rax+00h]
0x180006686  test    r12, r12
0x180006689  jnz     short loc_1800066F2
0x18000668b  test    r14, r14
0x18000668e  jnz     loc_180006B82
0x180006694  test    rsi, rsi
0x180006697  jnz     loc_180006BA4
0x18000669d  mov     eax, ebx
0x18000669f  mov     rcx, [rbp+200h+var_40]
0x1800066a6  xor     rcx, rsp; StackCookie
0x1800066a9  call    __security_check_cookie
0x1800066ae  mov     rbx, [rsp+310h+arg_18]
0x1800066b6  add     rsp, 2E0h
0x1800066bd  pop     r15
0x1800066bf  pop     r14
0x1800066c1  pop     r13
0x1800066c3  pop     r12
0x1800066c5  pop     rdi
0x1800066c6  pop     rsi
0x1800066c7  pop     rbp
0x1800066c8  retn
0x1800066ca  or      r13d, 1
0x1800066ce  jmp     loc_180006500
0x1800066d3  call    LsapAllocate
0x1800066d8  mov     r12, rax
0x1800066db  test    rax, rax
0x1800066de  jnz     loc_1800063E5
0x1800066e4  mov     r15, [rbp+200h+P]
0x1800066e8  mov     ebx, 0C0000017h
0x1800066ed  jmp     loc_18000663F
0x1800066f2  lea     rax, [rbp+200h+var_C0]
0x1800066f9  cmp     r12, rax
0x1800066fc  jz      short loc_18000668B
0x1800066fe  mov     rcx, r12; struct _RTL_BALANCED_NODE *
0x180006701  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180006706  jmp     short loc_18000668B
0x180006708  mov     rcx, rbx; Sid
0x18000670b  call    cs:__imp_RtlSubAuthorityCountSid
0x180006712  nop     dword ptr [rax+rax+00h]
0x180006717  cmp     [rax], sil
0x18000671a  jz      loc_1800069CF
0x180006720  mov     rcx, rbx; Sid
0x180006723  call    cs:__imp_RtlSubAuthorityCountSid
0x18000672a  nop     dword ptr [rax+rax+00h]
0x18000672f  mov     rcx, rbx; Sid
0x180006732  movzx   edx, byte ptr [rax]
  ... truncated ...
```
