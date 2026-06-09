# NegpMakeVirtualAccountToken(_SECURITY_LOGON_TYPE,ulong,_LUID *,void * *,ulong *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x18005d528`
- end: `0x18005e050`
- name: `?NegpMakeVirtualAccountToken@@YAJW4_SECURITY_LOGON_TYPE@@KPEAU_LUID@@PEAPEAXPEAKPEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@2PEAPEAU_UNICODE_STRING@@66PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `2856`
- prototype: `int(enum _SECURITY_LOGON_TYPE, unsigned int, struct _LUID *, void **, unsigned int *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009ac50`

## callees

- `0x1800093b0`
- `0x180009410`
- `0x18000c0f0`
- `0x18000c300`
- `0x18000d3b0`
- `0x18000dc70`
- `0x18000dca0`
- `0x18000dd1c`
- `0x18000fee0`
- `0x180011278`
- `0x180011c70`
- `0x180012da4`
- `0x1800162a8`
- `0x180016f70`
- `0x180026580`
- `0x18005c8b4`
- `0x18005d528`
- `0x18005e058`
- `0x18005e150`
- `0x18005e5c0`
- `0x18005e770`
- `0x1800b1f9c`
- `0x1800b212c`
- `0x1800b86d0`
- `0x1800bbbfc`
- `0x1800bd6e0`
- `0x1800f3858`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18005db30`
- `ntdll!RtlCopySid` at `0x18005db6b`
- `ntdll!RtlCopySid` at `0x18005dbde`
- `ntdll!RtlCopySid` at `0x18005dc11`
- `ntdll!RtlCopySid` at `0x18005dc3d`
- `ntdll!RtlCopySid` at `0x18005df84`
- `ntdll!RtlCopySid` at `0x18005db30`
- `ntdll!RtlCopySid` at `0x18005db6b`
- `ntdll!RtlCopySid` at `0x18005dbde`
- `ntdll!RtlCopySid` at `0x18005dc11`
- `ntdll!RtlCopySid` at `0x18005dc3d`
- `ntdll!RtlCopySid` at `0x18005df84`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18005d5f0`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18005d5f0`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005d7b8`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005d819`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005d7b8`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005d819`
- `ntdll!RtlSubAuthoritySid` at `0x18005d7fa`
- `ntdll!RtlSubAuthoritySid` at `0x18005de95`
- `ntdll!RtlSubAuthoritySid` at `0x18005d7fa`
- `ntdll!RtlSubAuthoritySid` at `0x18005de95`
- `ntdll!RtlFreeSid` at `0x18005db89`
- `ntdll!RtlFreeSid` at `0x18005e03f`
- `ntdll!RtlFreeSid` at `0x18005db89`
- `ntdll!RtlFreeSid` at `0x18005e03f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18005d87c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18005d87c`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005d7d0`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005d7d0`
- `ntdll!RtlAddAccessAllowedAce` at `0x18005dc93`
- `ntdll!RtlAddAccessAllowedAce` at `0x18005dcb8`
- `ntdll!RtlAddAccessAllowedAce` at `0x18005dc93`
- `ntdll!RtlAddAccessAllowedAce` at `0x18005dcb8`
- `ntdll!RtlCreateAcl` at `0x18005dc63`
- `ntdll!RtlCreateAcl` at `0x18005dc63`
- `ntdll!RtlTimeFieldsToTime` at `0x18005dad3`
- `ntdll!RtlTimeFieldsToTime` at `0x18005dad3`
- `ntdll!RtlLengthSid` at `0x18005d98a`
- `ntdll!RtlLengthSid` at `0x18005d99c`
- `ntdll!RtlLengthSid` at `0x18005da41`
- `ntdll!RtlLengthSid` at `0x18005da54`
- `ntdll!RtlLengthSid` at `0x18005da65`
- `ntdll!RtlLengthSid` at `0x18005da76`
- `ntdll!RtlLengthSid` at `0x18005da87`
- `ntdll!RtlLengthSid` at `0x18005db0e`
- `ntdll!RtlLengthSid` at `0x18005db53`
- `ntdll!RtlLengthSid` at `0x18005dbc8`
- `ntdll!RtlLengthSid` at `0x18005dbfb`
- `ntdll!RtlLengthSid` at `0x18005dc27`
- `ntdll!RtlLengthSid` at `0x18005df3e`
- `ntdll!RtlLengthSid` at `0x18005df64`
- `ntdll!RtlLengthSid` at `0x18005d98a`
- `ntdll!RtlLengthSid` at `0x18005d99c`
- `ntdll!RtlLengthSid` at `0x18005da41`
- `ntdll!RtlLengthSid` at `0x18005da54`
- `ntdll!RtlLengthSid` at `0x18005da65`
- `ntdll!RtlLengthSid` at `0x18005da76`
- `ntdll!RtlLengthSid` at `0x18005da87`
- `ntdll!RtlLengthSid` at `0x18005db0e`
- `ntdll!RtlLengthSid` at `0x18005db53`
- `ntdll!RtlLengthSid` at `0x18005dbc8`
- `ntdll!RtlLengthSid` at `0x18005dbfb`
- `ntdll!RtlLengthSid` at `0x18005dc27`
- `ntdll!RtlLengthSid` at `0x18005df3e`
- `ntdll!RtlLengthSid` at `0x18005df64`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d90d`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d90d`
- `ntdll!RtlEnterCriticalSection` at `0x18005d8de`
- `ntdll!RtlEnterCriticalSection` at `0x18005d8de`
- `RPCRT4!RpcUserFree` at `0x18005de1a`
- `RPCRT4!RpcUserFree` at `0x18005de37`
- `RPCRT4!RpcUserFree` at `0x18005de1a`
- `RPCRT4!RpcUserFree` at `0x18005de37`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetResourceGroupMembershipsTransitive` at `0x18005da00`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetResourceGroupMembershipsTransitive` at `0x18005da00`

## pseudocode

```c
__int64 __fastcall NegpMakeVirtualAccountToken(
        ULONG a1,
        int a2,
        struct _LUID *a3,
        void **a4,
        unsigned int *a5,
        int *a6,
        enum _LSA_TOKEN_INFORMATION_TYPE *a7,
        void **a8,
        struct _UNICODE_STRING **a9,
        struct _UNICODE_STRING **a10,
        struct _UNICODE_STRING **a11,
        struct _SECPKG_PRIMARY_CRED *a12,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a13)
{
  struct _SECPKG_PRIMARY_CRED *v13; // r12
  struct _RTL_BALANCED_NODE **v15; // r15
  union _LARGE_INTEGER *v16; // r13
  struct _LSAP_LOGON_SESSION *v17; // r14
  struct _UNICODE_STRING *v18; // rax
  unsigned int Length; // esi
  unsigned __int64 v20; // rbx
  struct _RTL_BALANCED_NODE *v21; // rax
  void *v22; // rdx
  struct _RTL_BALANCED_NODE *v23; // rdi
  unsigned __int64 v24; // rbx
  char *v25; // rdi
  struct _LSAP_DB_HANDLE *v26; // rdi
  void *v27; // rdx
  unsigned int v28; // ebx
  NTSTATUS LogonSession; // ebx
  void **v30; // rdx
  struct _RTL_BALANCED_NODE **p_UserSid; // rdi
  struct _RTL_BALANCED_NODE *v32; // rsi
  PSID_IDENTIFIER_AUTHORITY v33; // rax
  int v34; // ecx
  ULONG v35; // r15d
  struct _LUID *v36; // r15
  struct _LSAP_LOGON_SESSION *v37; // rax
  struct _RTL_BALANCED_NODE *v38; // r15
  ULONG v39; // r15d
  ULONG v40; // r13d
  __int64 v41; // rcx
  __int64 v42; // r8
  void *v43; // rbx
  struct _SAMPR_PSID_ARRAY *v44; // rcx
  ULONG v45; // r15d
  int v46; // edi
  __int64 v47; // rbx
  ULONG v48; // ebx
  ULONG v49; // ebx
  ULONG v50; // ebx
  ULONG v51; // ebx
  ULONG v52; // eax
  union _LARGE_INTEGER *v53; // rax
  union _LARGE_INTEGER *v54; // r12
  __int64 v55; // rcx
  union _LARGE_INTEGER *v56; // rdi
  ULONG v57; // eax
  __int64 v58; // r15
  char *v59; // r15
  ULONG v60; // eax
  __int64 v61; // rbx
  char *v62; // r15
  struct _SAMPR_PSID_ARRAY *v63; // rcx
  __int64 v64; // r13
  ULONG v65; // eax
  __int64 v66; // rbx
  char *v67; // r15
  ULONG v68; // eax
  __int64 v69; // rbx
  char *v70; // r15
  ULONG v71; // eax
  __int64 v72; // rdi
  ULONG v73; // edx
  struct _ACL *v74; // rdi
  void **v75; // rax
  struct _RTL_BALANCED_NODE **v77; // rsi
  struct _RTL_BALANCED_NODE **v78; // rdi
  void *v79; // rdx
  unsigned int v80; // r8d
  unsigned int i; // ebx
  unsigned __int8 IsRunning; // al
  ULONG v83; // eax
  ULONG v84; // eax
  __int64 v85; // rdi
  __int64 v86; // rdx
  void *v87; // rdx
  void *v88; // rdx
  void *v89; // rdx
  struct _SAMPR_PSID_ARRAY *v90; // [rsp+68h] [rbp-98h] BYREF
  ULONG AclSize; // [rsp+70h] [rbp-90h]
  PSID SourceSid; // [rsp+78h] [rbp-88h] BYREF
  union _LARGE_INTEGER *v93; // [rsp+80h] [rbp-80h]
  struct _LUID *v94[2]; // [rsp+88h] [rbp-78h] BYREF
  void *pBuffer[2]; // [rsp+98h] [rbp-68h] BYREF
  int v96; // [rsp+A8h] [rbp-58h] BYREF
  int v97; // [rsp+ACh] [rbp-54h]
  struct _SECPKG_PRIMARY_CRED *v98; // [rsp+B0h] [rbp-50h]
  struct _UNICODE_STRING **v99; // [rsp+B8h] [rbp-48h]
  struct _RTL_BALANCED_NODE *v100[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v101; // [rsp+D0h] [rbp-30h] BYREF
  struct _RTL_BALANCED_NODE *v102; // [rsp+D8h] [rbp-28h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v103; // [rsp+E0h] [rbp-20h]
  int *v104; // [rsp+E8h] [rbp-18h]
  void **v105; // [rsp+F0h] [rbp-10h]
  unsigned int *v106; // [rsp+F8h] [rbp-8h]
  enum _LSA_TOKEN_INFORMATION_TYPE *v107; // [rsp+100h] [rbp+0h]
  void **v108; // [rsp+108h] [rbp+8h]
  struct _UNICODE_STRING **v109; // [rsp+110h] [rbp+10h]
  __int128 v110; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v111[4]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v112; // [rsp+138h] [rbp+38h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+140h] [rbp+40h] BYREF
  struct _TIME_FIELDS TimeFields; // [rsp+148h] [rbp+48h] BYREF

  v13 = a12;
  v15 = (struct _RTL_BALANCED_NODE **)a9;
  v106 = a5;
  v104 = a6;
  v107 = a7;
  v108 = a8;
  v109 = a11;
  AclSize = a1;
  v16 = 0;
  SourceSid = 0;
  v93 = 0;
  v17 = 0;
  v102 = 0;
  v90 = 0;
  v105 = a4;
  v94[0] = a3;
  v97 = a2;
  v98 = a12;
  v99 = a10;
  v103 = a13;
  TimeFields = 0;
  v110 = 0;
  NtAllocateLocallyUniqueId(a3);
  a12->LogonId = *a3;
  *a13 = 0;
  v101 = 0;
  v96 = 0;
  v18 = *a9;
  *(_OWORD *)v100 = 0;
  *(_OWORD *)pBuffer = 0;
  Length = v18->Length;
  v20 = (*a10)->Length;
  LOWORD(v100[0]) = Length + v20 + 2;
  WORD1(v100[0]) = Length + v20 + 4;
  v21 = (struct _RTL_BALANCED_NODE *)LsapAllocate(WORD1(v100[0]));
  v100[1] = v21;
  v23 = v21;
  if ( !v21 )
  {
    LogonSession = -1073741801;
    goto LABEL_45;
  }
  memcpy_0(v21, (*v99)->Buffer, (unsigned int)v20);
  v24 = v20 >> 1;
  *((_WORD *)v23->Children + v24) = 92;
  v25 = (char *)v23 + 2 * v24;
  memcpy_0(v25 + 2, (*a9)->Buffer, Length);
  *(_WORD *)&v25[2 * ((unsigned __int64)Length >> 1) + 2] = 0;
  v26 = LsapPolicyHandle;
  *(_DWORD *)IdentifierAuthority.Value = 1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_f0978fc1336a326ebe269f72ca0dc488_Traceguids, 1);
  if ( LsapValidateLsapLookupLevel((enum _LSAP_LOOKUP_LEVEL *)&IdentifierAuthority) )
  {
    v28 = 0;
    while ( LsapValidateUnicodeStringWorker((PCUNICODE_STRING)&v100[2 * v28], 1u, 1u, 0, 0xFFFFu, 0) )
    {
      if ( ++v28 )
      {
        if ( v28 != 1 )
          break;
        v30 = (void **)pBuffer[1];
        if ( pBuffer[1] )
        {
          v80 = (unsigned int)pBuffer[0];
          for ( i = 0; i < v80; ++i )
          {
            if ( v30[3 * i + 1] )
            {
              RpcUserFree(0, v30[3 * i + 1]);
              v30 = (void **)pBuffer[1];
              v80 = (unsigned int)pBuffer[0];
            }
          }
          RpcUserFree(0, v30);
          pBuffer[1] = 0;
          LODWORD(pBuffer[0]) = 0;
        }
        LogonSession = LsapLookupNames(v26, 1, v100, &v101, pBuffer, 1, &v96, 0, 2);
        goto LABEL_11;
      }
    }
  }
  LogonSession = -1073741811;
LABEL_11:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) != 0 )
    WPP_SF_Dl(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      15,
      WPP_f0978fc1336a326ebe269f72ca0dc488_Traceguids,
      1,
      LogonSession);
  LsapSubProv_FreeRoutine(v100[1], v27);
  if ( LogonSession < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
        (unsigned int)LogonSession);
    goto LABEL_45;
  }
  p_UserSid = (struct _RTL_BALANCED_NODE **)&a12->UserSid;
  LogonSession = LsapDuplicateSid(&a12->UserSid, *((_QWORD *)pBuffer[1] + 1));
  LsaIFree_LSAPR_REFERENCED_DOMAIN_LIST(v101);
  _fgs__LSAPR_TRANSLATED_SIDS_EX2((struct _LSAPR_TRANSLATED_SIDS_EX2 *)pBuffer);
  if ( LogonSession >= 0 )
  {
    v32 = *p_UserSid;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    v112 = 0;
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_OWORD *)v111 = 0;
    if ( !*RtlSubAuthorityCountSid(v32) )
      goto LABEL_82;
    v33 = RtlIdentifierAuthoritySid(v32);
    v34 = *(_DWORD *)v33->Value - *(_DWORD *)IdentifierAuthority.Value;
    if ( *(_DWORD *)v33->Value == *(_DWORD *)IdentifierAuthority.Value )
      v34 = *(unsigned __int16 *)&v33->Value[4] - *(unsigned __int16 *)&IdentifierAuthority.Value[4];
    if ( v34 )
    {
LABEL_82:
      LogonSession = -1073741790;
      goto LABEL_45;
    }
    v35 = *RtlSubAuthoritySid(v32, 0);
    if ( v35 - 80 <= 0x1F && (*RtlSubAuthorityCountSid(v32) != 2 || *RtlSubAuthoritySid(v32, 1u)) )
    {
      LsapGetCallInfo(v111);
      LogonSession = LsapCheckVirtualAccountRestriction(v35, v111[0]);
      if ( LogonSession < 0 )
        goto LABEL_44;
      LogonSession = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, v35, 0, 0, 0, 0, 0, 0, 0, &SourceSid);
      if ( LogonSession < 0 )
        goto LABEL_44;
      v36 = v94[0];
      LogonSession = LsapCreateLogonSession(v94[0]);
      if ( LogonSession < 0 )
        goto LABEL_44;
      v37 = LsapLocateLogonSession(v36);
      v17 = v37;
      if ( v37 )
      {
        *((_DWORD *)v37 + 78) |= 0x10000000u;
        if ( v97 == 8217 )
        {
          v38 = *p_UserSid;
          *p_UserSid = 0;
          RtlEnterCriticalSection(&NegComputerNamesLock);
          LogonSession = NegpCopyCredsToBuffer(
                           &NegPrimarySystemCredentials,
                           NegSupplementalSystemCredentials,
                           a12,
                           v103);
          RtlLeaveCriticalSection(&NegComputerNamesLock);
          if ( *p_UserSid )
            LsapSubProv_FreeRoutine(*p_UserSid, v22);
          *p_UserSid = v38;
          if ( LogonSession < 0 )
            goto LABEL_44;
          *((_DWORD *)v17 + 78) |= 0x40000000u;
          v36 = v94[0];
        }
        else
        {
          v94[0] = 0;
          v94[1] = 0;
          LogonSession = LsapDuplicateString(&a12->DomainName, v94);
          if ( LogonSession < 0 )
            goto LABEL_44;
          LogonSession = LsapDuplicateString(&a12->DownlevelName, v94);
          if ( LogonSession < 0 )
            goto LABEL_44;
          LogonSession = LsapDuplicateString(&a12->Password, v94);
          if ( LogonSession < 0 )
            goto LABEL_44;
          *((_DWORD *)v17 + 78) |= 0x20000000u;
        }
        LogonSession = LsapSetLogonSessionAccountInfo(
                         v36,
                         *a9,
                         *v99,
                         0,
                         *p_UserSid,
                         (enum _SECURITY_LOGON_TYPE)AclSize,
                         0,
                         a12);
        if ( LogonSession >= 0 )
        {
          v39 = RtlLengthSid(*((PSID *)WellKnownSids + 90));
          v40 = RtlLengthSid(v32);
          LogonSession = LsapWaitForSamForAwhile();
          if ( LogonSession >= 0 )
          {
            if ( LsapProductType != NtProductLanManNt
              || (IsRunning = LsapSamExtDsIsRunning(), v43 = LsapLocalAccountDomainHandle, IsRunning) )
            {
              v43 = LsapAccountDomainHandle;
            }
            v102 = v32;
            *((_QWORD *)&v110 + 1) = &v102;
            LODWORD(v110) = 1;
            if ( (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v41, v22, v42) )
            {
              LogonSession = SamIGetResourceGroupMembershipsTransitive(v43, &v110, 2, &v90);
              if ( LogonSession >= 0 )
              {
                v44 = v90;
                v45 = v40 + v39 + 24;
                v46 = 0;
                v47 = 0;
                for ( AclSize = v45; (unsigned int)v47 < *(_DWORD *)v90; v46 += v83 )
                {
                  v83 = RtlLengthSid(*(PSID *)(*((_QWORD *)v44 + 1) + 8 * v47));
                  v44 = v90;
                  v47 = (unsigned int)(v47 + 1);
                }
                v48 = RtlLengthSid(*((PSID *)WellKnownSids + 102));
                v49 = RtlLengthSid(SourceSid) + v48;
                v50 = RtlLengthSid(v32) + v49;
                v51 = RtlLengthSid(v32) + v50;
                v52 = RtlLengthSid(v32);
                v53 = (union _LARGE_INTEGER *)LsapAllocate(v46 + v45 + 16 * *(_DWORD *)v90 + 104 + v52 + v51);
                v93 = v53;
                v16 = v53;
                if ( v53 )
                {
                  TimeFields = (struct _TIME_FIELDS)_mm_load_si128((const __m128i *)&_xmm);
                  RtlTimeFieldsToTime(&TimeFields, v53);
                  v54 = v16 + 8;
                  v55 = *(unsigned int *)v90;
                  v16[8].LowPart = v55 + 2;
                  v56 = &v16[2 * v55 + 13];
                  v57 = RtlLengthSid(*((PSID *)WellKnownSids + 102));
                  v58 = v57;
                  RtlCopySid(v57, v56, *((PSID *)WellKnownSids + 102));
                  v16[9].QuadPart = (LONGLONG)v56;
                  v59 = (char *)v56 + v58;
                  v16[10].LowPart = 7;
                  v60 = RtlLengthSid(SourceSid);
                  v61 = v60;
                  RtlCopySid(v60, v59, SourceSid);
                  v16[11].QuadPart = (LONGLONG)v59;
                  v62 = &v59[v61];
                  v16[12].LowPart = 7;
                  RtlFreeSid(SourceSid);
                  v63 = v90;
                  v64 = 0;
                  for ( SourceSid = 0; (unsigned int)v64 < *(_DWORD *)v90; v63 = v90 )
                  {
                    v84 = RtlLengthSid(*(PSID *)(*((_QWORD *)v63 + 1) + 8 * v64));
                    v85 = v84;
                    RtlCopySid(v84, v62, *(PSID *)(*((_QWORD *)v90 + 1) + 8 * v64));
                    v86 = (unsigned int)(v64 + 2);
                    v64 = (unsigned int)(v64 + 1);
                    v86 *= 2;
                    v54[v86 + 1].QuadPart = (LONGLONG)v62;
                    v62 += v85;
                    v54[v86 + 2].LowPart = 536870919;
                  }
                  LsapSamExtFreeSidArray(v63);
                  v16 = v93;
                  v90 = 0;
                  v93[3].QuadPart = (LONGLONG)v54;
                  v65 = RtlLengthSid(v32);
                  v66 = v65;
                  RtlCopySid(v65, v62, v32);
                  v16[1].QuadPart = (LONGLONG)v62;
                  v16[2].LowPart = 0;
                  v67 = &v62[v66];
                  v68 = RtlLengthSid(v32);
                  v69 = v68;
                  RtlCopySid(v68, v67, v32);
                  v16[4].QuadPart = (LONGLONG)v67;
                  v70 = &v67[v69];
                  v71 = RtlLengthSid(v32);
                  v72 = v71;
                  RtlCopySid(v71, v70, v32);
                  v73 = AclSize;
                  v74 = (struct _ACL *)&v70[v72];
                  v16[6].QuadPart = (LONGLONG)v70;
                  v16[5].QuadPart = 0;
                  LogonSession = RtlCreateAcl(v74, v73, 2u);
                  if ( LogonSession >= 0 )
                  {
                    LogonSession = RtlAddAccessAllowedAce(v74, 2u, 0x10000000u, *((PSID *)WellKnownSids + 90));
                    if ( LogonSession >= 0 )
                    {
                      LogonSession = RtlAddAccessAllowedAce(v74, 2u, 0x10000000u, v32);
                      if ( LogonSession >= 0 )
                      {
                        v75 = v105;
                        v16[7].QuadPart = (LONGLONG)v74;
                        *v75 = 0;
                        *v106 = 0;
                        *v107 = LsaTokenInformationV2;
                        *v108 = v16;
                        LsapReleaseLogonSession(v17);
                        *v104 = 0;
                        return 0;
                      }
                    }
                  }
                  v13 = v98;
                }
                else
                {
                  LogonSession = -1073741801;
                }
                goto LABEL_44;
              }
            }
            else
            {
              LogonSession = -1073741637;
            }
          }
          v16 = v93;
        }
      }
      else
      {
        LogonSession = -1073741729;
      }
    }
    else
    {
      LogonSession = -1073741790;
    }
LABEL_44:
    v15 = (struct _RTL_BALANCED_NODE **)a9;
  }
LABEL_45:
  v77 = (struct _RTL_BALANCED_NODE **)v99;
  if ( *v99 )
  {
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)(*v99)->Buffer, v22);
    LsapSubProv_FreeRoutine(*v77, v87);
    *v77 = 0;
  }
  if ( *v15 )
  {
    LsapSubProv_FreeRoutine((*v15)->Children[1], v22);
    LsapSubProv_FreeRoutine(*v15, v88);
    *v15 = 0;
  }
  v78 = (struct _RTL_BALANCED_NODE **)v109;
  if ( *v109 )
  {
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)(*v109)->Buffer, v22);
    LsapSubProv_FreeRoutine(*v78, v89);
    *v78 = 0;
  }
  NegpFreePrimaryCred(v13);
  LsapFreeSupplementalCredentials(v103);
  LsapSamExtFreeSidArray(v90);
  if ( v17 )
    LsapReleaseLogonSession(v17);
  LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v16, v79);
  if ( SourceSid )
    RtlFreeSid(SourceSid);
  *v104 = LogonSession;
  return (unsigned int)LogonSession;
}

```

## disassembly

```asm
0x18005d528  mov     [rsp-8+arg_8], rbx
0x18005d52d  push    rbp
0x18005d52e  push    rsi
0x18005d52f  push    rdi
0x18005d530  push    r12
0x18005d532  push    r13
0x18005d534  push    r14
0x18005d536  push    r15
0x18005d538  lea     rbp, [rsp-60h]
0x18005d53d  sub     rsp, 160h
0x18005d544  mov     rax, cs:__security_cookie
0x18005d54b  xor     rax, rsp
0x18005d54e  mov     [rbp+90h+var_38], rax
0x18005d552  mov     rax, [rbp+90h+arg_20]
0x18005d559  xorps   xmm0, xmm0
0x18005d55c  mov     r12, [rbp+90h+arg_58]
0x18005d563  mov     rbx, r8
0x18005d566  mov     r15, [rbp+90h+arg_40]
0x18005d56d  mov     rdi, [rbp+90h+arg_48]
0x18005d574  mov     rsi, [rbp+90h+arg_60]
0x18005d57b  mov     [rbp+90h+var_98], rax
0x18005d57f  mov     rax, [rbp+90h+arg_28]
0x18005d586  mov     [rbp+90h+var_A8], rax
0x18005d58a  mov     rax, [rbp+90h+arg_30]
0x18005d591  mov     [rbp+90h+var_90], rax
0x18005d595  mov     rax, [rbp+90h+arg_38]
0x18005d59c  mov     [rbp+90h+var_88], rax
0x18005d5a0  mov     rax, [rbp+90h+arg_50]
0x18005d5a7  mov     [rbp+90h+var_80], rax
0x18005d5ab  xor     eax, eax
0x18005d5ad  mov     [rsp+190h+AclSize], ecx
0x18005d5b1  mov     r13d, eax
0x18005d5b4  mov     rcx, r8; LocallyUniqueId
0x18005d5b7  mov     [rsp+190h+SourceSid], rax
0x18005d5bc  mov     [rbp+90h+var_110], rax
0x18005d5c0  mov     r14d, eax
0x18005d5c3  mov     [rbp+90h+var_B8], rax
0x18005d5c7  mov     [rsp+190h+var_128], rax
0x18005d5cc  mov     [rbp+90h+var_A0], r9
0x18005d5d0  mov     [rbp+90h+var_108], rbx
0x18005d5d4  mov     [rbp+90h+var_E4], edx
0x18005d5d7  mov     [rbp+90h+var_E0], r12
0x18005d5db  mov     [rsp+190h+var_130], r15
0x18005d5e0  mov     [rbp+90h+var_D8], rdi
0x18005d5e4  mov     [rbp+90h+var_B0], rsi
0x18005d5e8  movups  xmmword ptr [rbp+90h+TimeFields.Year], xmm0
0x18005d5ec  movups  [rbp+90h+var_78], xmm0
0x18005d5f0  call    cs:__imp_NtAllocateLocallyUniqueId
0x18005d5f7  nop     dword ptr [rax+rax+00h]
0x18005d5fc  mov     rax, [rbx]
0x18005d5ff  lea     ecx, [r14+2]
0x18005d603  mov     [r12], rax
0x18005d607  xorps   xmm0, xmm0
0x18005d60a  xor     eax, eax
0x18005d60c  xorps   xmm1, xmm1
0x18005d60f  mov     [rsi], rax
0x18005d612  mov     [rbp+90h+var_C0], rax
0x18005d616  mov     [rbp+90h+var_E8], eax
0x18005d619  mov     rax, [r15]
0x18005d61c  movups  xmmword ptr [rbp+90h+var_D0], xmm0
0x18005d620  movups  xmmword ptr [rbp+90h+pBuffer], xmm1
0x18005d624  movzx   esi, word ptr [rax]
0x18005d627  mov     rax, [rdi]
0x18005d62a  movzx   ebx, word ptr [rax]
0x18005d62d  lea     eax, [rsi+rbx]
0x18005d630  add     ax, cx
0x18005d633  mov     word ptr [rbp+90h+var_D0], ax
0x18005d637  add     ax, cx
0x18005d63a  movzx   ecx, ax
0x18005d63d  mov     word ptr [rbp+90h+var_D0+2], cx
0x18005d641  call    LsapAllocate
0x18005d646  mov     [rbp+90h+var_D0+8], rax
0x18005d64a  mov     rdi, rax
0x18005d64d  test    rax, rax
0x18005d650  jz      loc_18005DDC6
0x18005d656  mov     rdx, [rbp+90h+var_D8]
0x18005d65a  mov     r8d, ebx; Size
0x18005d65d  mov     rcx, rax; void *
0x18005d660  mov     rdx, [rdx]
0x18005d663  mov     rdx, [rdx+8]; Src
0x18005d667  call    memcpy_0
0x18005d66c  shr     rbx, 1
0x18005d66f  mov     r8d, esi; Size
0x18005d672  mov     word ptr [rdi+rbx*2], 5Ch ; '\'
0x18005d678  lea     rdi, [rdi+rbx*2]
0x18005d67c  mov     rdx, [r15]
0x18005d67f  lea     rcx, [rdi+2]; void *
0x18005d683  mov     ebx, esi
0x18005d685  mov     rdx, [rdx+8]; Src
0x18005d689  call    memcpy_0
0x18005d68e  shr     rbx, 1
0x18005d691  xor     esi, esi
0x18005d693  mov     [rdi+rbx*2+2], si
0x18005d698  mov     rdi, cs:?LsapPolicyHandle@@3PEAXEA; void * LsapPolicyHandle
0x18005d69f  lea     eax, [rsi+1]
0x18005d6a2  mov     dword ptr [rbp+90h+IdentifierAuthority.Value], eax
0x18005d6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d6ac  test    byte ptr [rcx+6Ch], 40h
0x18005d6b0  jnz     loc_18005DDCD
0x18005d6b6  lea     rcx, [rbp+90h+IdentifierAuthority]; enum _LSAP_LOOKUP_LEVEL *
0x18005d6ba  call    ?LsapValidateLsapLookupLevel@@YAEPEAW4_LSAP_LOOKUP_LEVEL@@@Z; LsapValidateLsapLookupLevel(_LSAP_LOOKUP_LEVEL *)
0x18005d6bf  test    al, al
0x18005d6c1  jz      short loc_18005D6F4
0x18005d6c3  mov     ebx, esi
0x18005d6c5  mov     r8b, 1; unsigned __int8
0x18005d6c8  mov     eax, ebx
0x18005d6ca  shl     rax, 4
0x18005d6ce  lea     rcx, [rbp+90h+var_D0]
0x18005d6d2  add     rcx, rax; SearchString
0x18005d6d5  mov     qword ptr [rsp+190h+SubAuthority3], rsi; unsigned __int16 *
0x18005d6da  xor     r9d, r9d; unsigned __int8
0x18005d6dd  mov     word ptr [rsp+190h+SubAuthority2], 0FFFFh; unsigned __int16
0x18005d6e4  mov     dl, r8b; unsigned __int8
0x18005d6e7  call    ?LsapValidateUnicodeStringWorker@@YAEPEAU_UNICODE_STRING@@EEEGPEAG@Z; LsapValidateUnicodeStringWorker(_UNICODE_STRING *,uchar,uchar,uchar,ushort,ushort *)
0x18005d6ec  test    al, al
0x18005d6ee  jnz     loc_18005DDEA
0x18005d6f4  mov     ebx, 0C000000Dh
0x18005d6f9  jmp     short loc_18005D747
0x18005d6fb  jnz     short loc_18005D6F4
0x18005d6fd  mov     rdx, [rbp+90h+pBuffer+8]
0x18005d701  test    rdx, rdx
0x18005d704  jnz     loc_18005DDFA
0x18005d70a  mov     [rsp+190h+SubAuthority6], 2
0x18005d712  lea     rax, [rbp+90h+var_E8]
0x18005d716  mov     [rsp+190h+SubAuthority5], esi
0x18005d71a  lea     r9, [rbp+90h+var_C0]
0x18005d71e  mov     qword ptr [rsp+190h+SubAuthority4], rax
0x18005d723  lea     r8, [rbp+90h+var_D0]
0x18005d727  lea     rax, [rbp+90h+pBuffer]
0x18005d72b  mov     [rsp+190h+SubAuthority3], 1
0x18005d733  mov     edx, 1
0x18005d738  mov     qword ptr [rsp+190h+SubAuthority2], rax
0x18005d73d  mov     rcx, rdi
0x18005d740  call    ?LsapLookupNames@@YAJPEAXKPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@W4_LSAP_LOOKUP_LEVEL@@PEAKKK@Z; LsapLookupNames(void *,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST * *,_LSAPR_TRANSLATED_SIDS_EX2 *,_LSAP_LOOKUP_LEVEL,ulong *,ulong,ulong)
0x18005d745  mov     ebx, eax
0x18005d747  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d74e  test    byte ptr [rcx+6Ch], 40h
0x18005d752  jnz     loc_18005DD27
0x18005d758  mov     rcx, [rbp+90h+var_D0+8]; struct _RTL_BALANCED_NODE *
0x18005d75c  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18005d761  test    ebx, ebx
0x18005d763  js      loc_18005DE4F
0x18005d769  mov     rdx, [rbp+90h+pBuffer+8]
0x18005d76d  lea     rdi, [r12+48h]
0x18005d772  mov     rcx, rdi
0x18005d775  mov     rdx, [rdx+8]
0x18005d779  call    LsapDuplicateSid
0x18005d77e  mov     rcx, [rbp+90h+var_C0]
0x18005d782  mov     ebx, eax
0x18005d784  call    LsaIFree_LSAPR_REFERENCED_DOMAIN_LIST
0x18005d789  lea     rcx, [rbp+90h+pBuffer]; struct _LSAPR_TRANSLATED_SIDS_EX2 *
0x18005d78d  call    ?_fgs__LSAPR_TRANSLATED_SIDS_EX2@@YAXPEAU_LSAPR_TRANSLATED_SIDS_EX2@@@Z; _fgs__LSAPR_TRANSLATED_SIDS_EX2(_LSAPR_TRANSLATED_SIDS_EX2 *)
0x18005d792  test    ebx, ebx
0x18005d794  js      loc_18005DD53
0x18005d79a  mov     rsi, [rdi]
0x18005d79d  xorps   xmm0, xmm0
0x18005d7a0  xor     eax, eax
0x18005d7a2  mov     word ptr [rbp+90h+IdentifierAuthority.Value+4], 500h
0x18005d7a8  xor     ebx, ebx
0x18005d7aa  mov     [rbp+90h+var_58], rax
0x18005d7ae  mov     rcx, rsi; Sid
0x18005d7b1  mov     dword ptr [rbp+90h+IdentifierAuthority.Value], ebx
0x18005d7b4  movups  xmmword ptr [rbp+90h+var_68], xmm0
0x18005d7b8  call    cs:__imp_RtlSubAuthorityCountSid
0x18005d7bf  nop     dword ptr [rax+rax+00h]
0x18005d7c4  cmp     byte ptr [rax], 1
0x18005d7c7  jb      loc_18005DFC8
0x18005d7cd  mov     rcx, rsi; Sid
0x18005d7d0  call    cs:__imp_RtlIdentifierAuthoritySid
0x18005d7d7  nop     dword ptr [rax+rax+00h]
0x18005d7dc  mov     ecx, [rax]
0x18005d7de  sub     ecx, dword ptr [rbp+90h+IdentifierAuthority.Value]
0x18005d7e1  jnz     short loc_18005D7ED
0x18005d7e3  movzx   ecx, word ptr [rax+4]
0x18005d7e7  movzx   eax, word ptr [rbp+90h+IdentifierAuthority.Value+4]
0x18005d7eb  sub     ecx, eax
0x18005d7ed  test    ecx, ecx
0x18005d7ef  jnz     loc_18005DFC8
0x18005d7f5  xor     edx, edx; SubAuthority
0x18005d7f7  mov     rcx, rsi; Sid
0x18005d7fa  call    cs:__imp_RtlSubAuthoritySid
0x18005d801  nop     dword ptr [rax+rax+00h]
0x18005d806  mov     r15d, [rax]
0x18005d809  lea     eax, [r15-50h]
0x18005d80d  cmp     eax, 1Fh
0x18005d810  ja      loc_18005DEA9
0x18005d816  mov     rcx, rsi; Sid
0x18005d819  call    cs:__imp_RtlSubAuthorityCountSid
0x18005d820  nop     dword ptr [rax+rax+00h]
0x18005d825  cmp     byte ptr [rax], 2
0x18005d828  jz      loc_18005DE8D
0x18005d82e  lea     rcx, [rbp+90h+var_68]
0x18005d832  call    LsapGetCallInfo
0x18005d837  mov     edx, [rbp+90h+var_68]; unsigned int
0x18005d83a  mov     ecx, r15d; unsigned int
0x18005d83d  call    ?LsapCheckVirtualAccountRestriction@@YAJKK@Z; LsapCheckVirtualAccountRestriction(ulong,ulong)
0x18005d842  xor     ecx, ecx
0x18005d844  mov     ebx, eax
0x18005d846  test    eax, eax
0x18005d848  js      loc_18005DD4E
0x18005d84e  lea     rax, [rsp+190h+SourceSid]
0x18005d853  xor     r9d, r9d; SubAuthority1
0x18005d856  mov     [rsp+190h+Sid], rax; Sid
0x18005d85b  mov     r8d, r15d; SubAuthority0
0x18005d85e  mov     [rsp+190h+SubAuthority7], ecx; SubAuthority7
0x18005d862  mov     dl, 2; SubAuthorityCount
0x18005d864  mov     [rsp+190h+SubAuthority6], ecx; SubAuthority6
0x18005d868  mov     [rsp+190h+SubAuthority5], ecx; SubAuthority5
0x18005d86c  mov     [rsp+190h+SubAuthority4], ecx; SubAuthority4
0x18005d870  mov     [rsp+190h+SubAuthority3], ecx; SubAuthority3
0x18005d874  mov     [rsp+190h+SubAuthority2], ecx; SubAuthority2
0x18005d878  lea     rcx, [rbp+90h+IdentifierAuthority]; IdentifierAuthority
0x18005d87c  call    cs:__imp_RtlAllocateAndInitializeSid
0x18005d883  nop     dword ptr [rax+rax+00h]
0x18005d888  mov     ebx, eax
0x18005d88a  test    eax, eax
0x18005d88c  js      loc_18005DD4E
0x18005d892  mov     r15, [rbp+90h+var_108]
0x18005d896  mov     rcx, r15; struct _LUID *
0x18005d899  call    ?LsapCreateLogonSession@@YAJPEAU_LUID@@@Z; LsapCreateLogonSession(_LUID *)
0x18005d89e  mov     ebx, eax
0x18005d8a0  test    eax, eax
0x18005d8a2  js      loc_18005DD4E
0x18005d8a8  mov     rcx, r15; struct _LUID *
0x18005d8ab  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x18005d8b0  mov     r14, rax
0x18005d8b3  test    rax, rax
0x18005d8b6  jz      loc_18005DEB3
0x18005d8bc  bts     dword ptr [rax+138h], 1Ch
0x18005d8c4  cmp     [rbp+90h+var_E4], 2019h
0x18005d8cb  jnz     loc_18005DEBD
0x18005d8d1  mov     r15, [rdi]
0x18005d8d4  lea     rcx, ?NegComputerNamesLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18005d8db  mov     [rdi], r13
0x18005d8de  call    cs:__imp_RtlEnterCriticalSection
0x18005d8e5  nop     dword ptr [rax+rax+00h]
0x18005d8ea  mov     r9, [rbp+90h+var_B0]; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x18005d8ee  lea     rcx, ?NegPrimarySystemCredentials@@3U_SECPKG_PRIMARY_CRED@@A; struct _SECPKG_PRIMARY_CRED *
0x18005d8f5  mov     rdx, cs:?NegSupplementalSystemCredentials@@3PEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@EA; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *
0x18005d8fc  mov     r8, r12; struct _SECPKG_PRIMARY_CRED *
0x18005d8ff  call    ?NegpCopyCredsToBuffer@@YAJPEAU_SECPKG_PRIMARY_CRED@@PEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@0PEAPEAU2@@Z; NegpCopyCredsToBuffer(_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x18005d904  lea     rcx, ?NegComputerNamesLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18005d90b  mov     ebx, eax
0x18005d90d  call    cs:__imp_RtlLeaveCriticalSection
0x18005d914  nop     dword ptr [rax+rax+00h]
0x18005d919  mov     rcx, [rdi]; struct _RTL_BALANCED_NODE *
0x18005d91c  test    rcx, rcx
0x18005d91f  jz      short loc_18005D926
0x18005d921  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18005d926  mov     [rdi], r15
0x18005d929  test    ebx, ebx
0x18005d92b  js      loc_18005DD4E
0x18005d931  bts     dword ptr [r14+138h], 1Eh
0x18005d93a  mov     r15, [rbp+90h+var_108]
0x18005d93e  mov     eax, [rsp+190h+AclSize]
0x18005d942  xor     r9d, r9d; struct _UNICODE_STRING *
0x18005d945  mov     rdx, [rsp+190h+var_130]
0x18005d94a  mov     rcx, r15; struct _LUID *
0x18005d94d  mov     qword ptr [rsp+190h+SubAuthority5], r12; struct _SECPKG_PRIMARY_CRED *
0x18005d952  mov     [rsp+190h+SubAuthority4], r13d; int
0x18005d957  mov     [rsp+190h+SubAuthority3], eax; enum _SECURITY_LOGON_TYPE
0x18005d95b  mov     rax, [rdi]
0x18005d95e  mov     rdx, [rdx]; struct _UNICODE_STRING *
0x18005d961  mov     qword ptr [rsp+190h+SubAuthority2], rax; Src
0x18005d966  mov     rax, [rbp+90h+var_D8]
0x18005d96a  mov     r8, [rax]; struct _UNICODE_STRING *
0x18005d96d  call    ?LsapSetLogonSessionAccountInfo@@YAJPEAU_LUID@@PEAU_UNICODE_STRING@@11PEAXW4_SECURITY_LOGON_TYPE@@HPEAU_SECPKG_PRIMARY_CRED@@@Z; LsapSetLogonSessionAccountInfo(_LUID *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_SECURITY_LOGON_TYPE,int,_SECPKG_PRIMARY_CRED *)
0x18005d972  mov     ebx, eax
0x18005d974  test    eax, eax
0x18005d976  js      loc_18005DD4E
0x18005d97c  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005d983  mov     rcx, [rcx+2D0h]; Sid
0x18005d98a  call    cs:__imp_RtlLengthSid
0x18005d991  nop     dword ptr [rax+rax+00h]
0x18005d996  mov     rcx, rsi; Sid
0x18005d999  mov     r15d, eax
0x18005d99c  call    cs:__imp_RtlLengthSid
0x18005d9a3  nop     dword ptr [rax+rax+00h]
0x18005d9a8  mov     r13d, eax
0x18005d9ab  call    ?LsapWaitForSamForAwhile@@YAJXZ; LsapWaitForSamForAwhile(void)
0x18005d9b0  mov     ebx, eax
0x18005d9b2  test    eax, eax
0x18005d9b4  js      loc_18005DFBF
0x18005d9ba  cmp     cs:LsapProductType, 2
0x18005d9c1  jz      loc_18005DF1D
0x18005d9c7  mov     rbx, cs:?LsapAccountDomainHandle@@3PEAXEA; void * LsapAccountDomainHandle
0x18005d9ce  lea     rax, [rbp+90h+var_B8]
0x18005d9d2  mov     [rbp+90h+var_B8], rsi
0x18005d9d6  mov     qword ptr [rbp+90h+var_78+8], rax
0x18005d9da  mov     dword ptr [rbp+90h+var_78], 1
0x18005d9e1  call    IsSamIDecodeClaimsBlobPresent
0x18005d9e6  test    al, al
0x18005d9e8  jz      loc_18005DFBA
0x18005d9ee  lea     r9, [rsp+190h+var_128]
0x18005d9f3  mov     r8d, 2
0x18005d9f9  lea     rdx, [rbp+90h+var_78]
0x18005d9fd  mov     rcx, rbx
0x18005da00  call    cs:__imp_SamIGetResourceGroupMembershipsTransitive
0x18005da07  nop     dword ptr [rax+rax+00h]
0x18005da0c  mov     ebx, eax
  ... truncated ...
```
