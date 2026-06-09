# LsapAuApiDispatchLogonUser(_LSAP_CLIENT_REQUEST *,void *,_QUOTA_LIMITS *,uchar,ulong *)

- ea: `0x180056fec`
- end: `0x18005863f`
- name: `?LsapAuApiDispatchLogonUser@@YAJPEAU_LSAP_CLIENT_REQUEST@@PEAXPEAU_QUOTA_LIMITS@@EPEAK@Z`
- size: `5715`
- prototype: `__int64 __fastcall(struct _LSAP_CLIENT_REQUEST *, void *, struct _QUOTA_LIMITS *, unsigned __int8, PULONG)`
- caller_count: `1`
- callee_count: `46`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180028cb0`

## callees

- `0x180004140`
- `0x1800072c8`
- `0x1800093b0`
- `0x180009410`
- `0x18000b7d0`
- `0x18000c300`
- `0x18000dd1c`
- `0x180011278`
- `0x180024750`
- `0x180027010`
- `0x180056d24`
- `0x180056dec`
- `0x180056f84`
- `0x180056fec`
- `0x180058878`
- `0x180058cec`
- `0x180058e54`
- `0x180059260`
- `0x1800592d0`
- `0x180059448`
- `0x18005966c`
- `0x180059a94`
- `0x18005c6fc`
- `0x18007bed8`
- `0x180081fa8`
- `0x180082b70`
- `0x180087b38`
- `0x18008d370`
- `0x18008d590`
- `0x180097ca4`
- `0x1800b24f4`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bc2c4`
- `0x1800d9e54`
- `0x1800f02a4`
- `0x1800f0364`
- `0x1800f0584`
- `0x1800f0960`
- `0x1800f09c4`
- `0x1800f5430`
- `0x18011a300`
- `0x18011a520`
- `0x18012ce58`
- `0x18014a704`
- `0x18014d010`

## import_xrefs

- `LSAADT!__imp_?LsapCrashOnAuditFailState@@3KA` at `0x18005792d`
- `LSAADT!__imp_?LsapAdtSglSidCount@@3KA` at `0x180057ca5`
- `LSAADT!__imp_?LsapAdtGetPrivilegeSetFromToken@@YAJPEAXPEAPEAU_PRIVILEGE_SET@@@Z` at `0x180057df5`
- `LSAADT!__imp_?LsapAdtGetPrivilegeSetFromToken@@YAJPEAXPEAPEAU_PRIVILEGE_SET@@@Z` at `0x180057e74`
- `LSAADT!__imp_?LsapAdtGetPrivilegeSetFromToken@@YAJPEAXPEAPEAU_PRIVILEGE_SET@@@Z` at `0x180057df5`
- `LSAADT!__imp_?LsapAdtGetPrivilegeSetFromToken@@YAJPEAXPEAPEAU_PRIVILEGE_SET@@@Z` at `0x180057e74`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180058129`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180058129`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180057071`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180057103`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180057071`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180057103`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800573d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180057425`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005762a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005788a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800578dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005828e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005835a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800573d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180057425`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005762a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005788a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800578dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005828e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005835a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058523`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058523`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800573b8`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800573b8`
- `ntdll!NtClose` at `0x18005723f`
- `ntdll!NtClose` at `0x180058149`
- `ntdll!NtClose` at `0x180058168`
- `ntdll!NtClose` at `0x18005723f`
- `ntdll!NtClose` at `0x180058149`
- `ntdll!NtClose` at `0x180058168`
- `ntdll!NtOpenProcess` at `0x1800571df`
- `ntdll!NtOpenProcess` at `0x1800571df`
- `ntdll!NtQueryInformationProcess` at `0x18005722d`
- `ntdll!NtQueryInformationProcess` at `0x18005722d`
- `ntdll!RtlFreeSid` at `0x180057a6e`
- `ntdll!RtlFreeSid` at `0x180057ade`
- `ntdll!RtlFreeSid` at `0x180057aee`
- `ntdll!RtlFreeSid` at `0x180057b25`
- `ntdll!RtlFreeSid` at `0x180057b35`
- `ntdll!RtlFreeSid` at `0x180057a6e`
- `ntdll!RtlFreeSid` at `0x180057ade`
- `ntdll!RtlFreeSid` at `0x180057aee`
- `ntdll!RtlFreeSid` at `0x180057b25`
- `ntdll!RtlFreeSid` at `0x180057b35`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800579ec`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180057a58`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800579ec`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180057a58`
- `ntdll!NtSetInformationToken` at `0x180057db4`
- `ntdll!NtSetInformationToken` at `0x180057db4`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800574d2`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800574d2`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800574fa`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800575e4`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800574fa`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800575e4`
- `IPHLPAPI!GetSessionCompartmentId` at `0x1800574e4`
- `IPHLPAPI!GetSessionCompartmentId` at `0x1800574e4`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180057cc3`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180057cc3`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditSpecialPrivileges` at `0x1800583ca`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditSpecialPrivileges` at `0x180058409`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditSpecialPrivileges` at `0x1800583ca`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditSpecialPrivileges` at `0x180058409`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapReportGroupsAtLogonEvent` at `0x180057c99`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapReportGroupsAtLogonEvent` at `0x180057c99`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapReportClaimsAtLogonEvent` at `0x180057d54`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapReportClaimsAtLogonEvent` at `0x180057d54`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtGenerateSpecialGroupsLogonAudit` at `0x180057d0a`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtGenerateSpecialGroupsLogonAudit` at `0x180057d0a`

## pseudocode

```c
__int64 __fastcall LsapAuApiDispatchLogonUser(
        void **a1,
        void *a2,
        struct _QUOTA_LIMITS *a3,
        unsigned __int8 a4,
        PULONG a5)
{
  void *Value; // rax
  char v7; // r13
  NTSTATUS ClientInfo; // ebx
  LsaHandleCache *v9; // rcx
  __int64 v10; // rdx
  ULONG SessionId; // eax
  struct _LSAP_LOGON_USER_ARGS *v12; // r12
  unsigned __int64 v13; // rcx
  struct _LSAP_SECURITY_PACKAGE *v14; // r15
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  int v18; // eax
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r12d
  bool v20; // r13
  unsigned int v21; // r15d
  int v22; // eax
  struct _LSAP_LOGON_USER_ARGS *v23; // rbx
  NET_IF_COMPARTMENT_ID SessionCompartmentId; // eax
  NTSTATUS v25; // eax
  __int64 v26; // r8
  int v27; // eax
  NTSTATUS v28; // eax
  __int64 v29; // r8
  LsaHandleCache *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r9
  struct _LSAP_LOGON_SESSION *v33; // rax
  struct _LSAP_LOGON_SESSION *v34; // rbx
  void *v35; // r13
  struct _LSAP_SECURITY_PACKAGE *v36; // rax
  int SystemAccessAuditInfo; // eax
  int v38; // r15d
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  LsaHandleCache *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r9
  __int64 v45; // rdx
  unsigned __int8 v46; // al
  NTSTATUS v47; // eax
  PSID v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rcx
  int v51; // eax
  struct _RTL_BALANCED_NODE *v52; // r15
  struct _RTL_BALANCED_NODE *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  NTSTATUS PrivilegeSetFromToken; // eax
  struct _SECPKG_PRIMARY_CRED *v58; // rdx
  int v59; // eax
  enum _SECURITY_LOGON_TYPE v60; // r15d
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // r8
  LsaHandleCache *v64; // rcx
  HANDLE v65; // rcx
  struct _LUID *p_AuthenticationId; // r8
  char v67; // al
  struct _LUID *v68; // rdx
  void *v69; // rcx
  enum _SECURITY_LOGON_TYPE v70; // esi
  struct _UNICODE_STRING *v71; // r14
  struct _UNICODE_STRING *v72; // r15
  struct _RTL_BALANCED_NODE *v73; // r13
  unsigned int v74; // esi
  void *v75; // rdx
  __int64 v76; // r8
  struct _RTL_BALANCED_NODE *v77; // rcx
  void *v78; // rdx
  void *v79; // rdx
  void *v80; // rdx
  void *v81; // rdx
  void *v82; // rdx
  void *v83; // rdx
  void *v84; // rdx
  void *v85; // rdx
  struct _RTL_BALANCED_NODE *Buffer; // rcx
  __int64 Length; // rax
  struct _RTL_BALANCED_NODE *v88; // rcx
  __int64 v89; // rax
  struct _RTL_BALANCED_NODE *v90; // rcx
  __int64 v91; // rax
  void *v92; // rdx
  void *v93; // rdx
  struct _RTL_BALANCED_NODE *v94; // rdx
  struct _UNICODE_STRING *ReturnLength; // [rsp+20h] [rbp-F0h]
  _SECPKG_CLIENT_INFO *SubAuthority3; // [rsp+28h] [rbp-E8h]
  struct _UNICODE_STRING *SubAuthority7; // [rsp+48h] [rbp-C8h]
  PSID *Sid; // [rsp+50h] [rbp-C0h]
  _BYTE v100[8]; // [rsp+90h] [rbp-80h] BYREF
  unsigned __int8 v101[8]; // [rsp+98h] [rbp-78h] BYREF
  struct _LSAP_SECURITY_PACKAGE *v102; // [rsp+A0h] [rbp-70h]
  unsigned int v103; // [rsp+A8h] [rbp-68h]
  char v104; // [rsp+ACh] [rbp-64h]
  unsigned __int8 v105; // [rsp+ADh] [rbp-63h] BYREF
  unsigned __int8 v106[2]; // [rsp+AEh] [rbp-62h] BYREF
  struct _LUID AuthenticationId; // [rsp+B0h] [rbp-60h] BYREF
  struct _PROCESS_SESSION_INFORMATION ProcessInformation; // [rsp+B8h] [rbp-58h] BYREF
  PLARGE_INTEGER ExpirationTime; // [rsp+C0h] [rbp-50h] BYREF
  enum _SECURITY_LOGON_TYPE v110; // [rsp+C8h] [rbp-48h]
  _LSA_TOKEN_INFORMATION_TYPE v111; // [rsp+CCh] [rbp-44h] BYREF
  unsigned int v112; // [rsp+D0h] [rbp-40h]
  _LSA_TOKEN_INFORMATION_TYPE v113; // [rsp+D4h] [rbp-3Ch]
  unsigned int v114; // [rsp+D8h] [rbp-38h] BYREF
  struct _RTL_BALANCED_NODE *v115; // [rsp+E0h] [rbp-30h] BYREF
  HANDLE TokenHandle; // [rsp+E8h] [rbp-28h] BYREF
  struct _LUID v117; // [rsp+F0h] [rbp-20h] BYREF
  struct _RTL_BALANCED_NODE *v118; // [rsp+F8h] [rbp-18h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL v119; // [rsp+100h] [rbp-10h]
  PSID v120; // [rsp+108h] [rbp-8h] BYREF
  struct _RTL_BALANCED_NODE *v121; // [rsp+110h] [rbp+0h] BYREF
  struct _UNICODE_STRING *v122; // [rsp+118h] [rbp+8h]
  PSID v123; // [rsp+120h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+128h] [rbp+18h] BYREF
  struct _RTL_BALANCED_NODE *v125; // [rsp+130h] [rbp+20h] BYREF
  struct _RTL_BALANCED_NODE *v126; // [rsp+138h] [rbp+28h] BYREF
  struct _RTL_BALANCED_NODE *v127; // [rsp+140h] [rbp+30h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v128; // [rsp+148h] [rbp+38h] BYREF
  LUID LocallyUniqueId[2]; // [rsp+150h] [rbp+40h] BYREF
  struct _RTL_BALANCED_NODE *v130; // [rsp+160h] [rbp+50h]
  struct _LSA_CALL_INFO *v131; // [rsp+168h] [rbp+58h]
  HLOCAL v132; // [rsp+170h] [rbp+60h] BYREF
  void *ProcessHandle; // [rsp+178h] [rbp+68h] BYREF
  void *v134; // [rsp+180h] [rbp+70h]
  void **v135; // [rsp+188h] [rbp+78h]
  struct _UNICODE_STRING *v136; // [rsp+190h] [rbp+80h]
  struct _LUID v137; // [rsp+198h] [rbp+88h] BYREF
  struct _LSAP_LOGON_SESSION *v138; // [rsp+1A0h] [rbp+90h]
  HLOCAL hMem; // [rsp+1A8h] [rbp+98h] BYREF
  _SECPKG_CLIENT_INFO v140; // [rsp+1B0h] [rbp+A0h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+1D0h] [rbp+C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1E0h] [rbp+D0h] BYREF
  struct _SECPKG_PRIMARY_CRED v143; // [rsp+210h] [rbp+100h] BYREF
  struct _LSAP_LOGON_USER_ARGS *IdentifierAuthority; // [rsp+2F0h] [rbp+1E0h] BYREF

  v135 = a1;
  ExpirationTime = 0;
  v111 = LsaTokenInformationNull;
  TokenHandle = 0;
  Handle = 0;
  v115 = 0;
  v118 = 0;
  v125 = 0;
  v121 = 0;
  AuthenticationId = 0;
  v117 = 0;
  hMem = 0;
  v126 = 0;
  v127 = 0;
  v120 = a3;
  v134 = a2;
  v101[0] = a4;
  Value = TlsGetValue(dwSession);
  v143.LogonId.LowPart = 0;
  v123 = Value;
  memset(&v140, 0, sizeof(v140));
  memset_0(&v143.LogonId.HighPart, 0, 0xDCu);
  v128 = 0;
  ProcessInformation.SessionId = 0;
  ClientId = 0;
  v130 = 0;
  v7 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ProcessHandle = 0;
  v137 = 0;
  v106[0] = 0;
  *(_OWORD *)&LocallyUniqueId[0].LowPart = 0;
  v100[0] = 0;
  v105 = 0;
  v132 = 0;
  v131 = (struct _LSA_CALL_INFO *)TlsGetValue(dwCallInfo);
  ClientInfo = LsapGetClientInfoEx((struct _SECPKG_CLIENT_INFO_EX *)&v140, 0x20u);
  if ( ClientInfo < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 10;
LABEL_302:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, &WPP_5f4735df67a33b644648330a4d5d4709_Traceguids, (unsigned int)ClientInfo);
      return (unsigned int)ClientInfo;
    }
    return (unsigned int)ClientInfo;
  }
  if ( (v140.ClientFlags & 2) != 0 || (v140.ClientFlags & 1) != 0 )
  {
    v9 = WPP_GLOBAL_Control;
    ClientInfo = -1073741790;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 11;
      goto LABEL_302;
    }
    return (unsigned int)ClientInfo;
  }
  if ( a5 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_5f4735df67a33b644648330a4d5d4709_Traceguids, *a5);
    SessionId = *a5;
    ProcessInformation.SessionId = *a5;
    goto LABEL_21;
  }
  ClientId.UniqueProcess = (HANDLE)(int)v140.ProcessID;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ClientId.UniqueThread = 0;
  ClientInfo = NtOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributes, &ClientId);
  if ( ClientInfo >= 0 )
  {
    ClientInfo = NtQueryInformationProcess(ProcessHandle, ProcessSessionInformation, &ProcessInformation, 4u, 0);
    NtClose(ProcessHandle);
    if ( ClientInfo < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 13;
        goto LABEL_302;
      }
      return (unsigned int)ClientInfo;
    }
    SessionId = ProcessInformation.SessionId;
LABEL_21:
    *((_DWORD *)a1 + 2) = SessionId;
    v12 = (struct _LSAP_LOGON_USER_ARGS *)((char *)*a1 + 48);
    IdentifierAuthority = v12;
    *((_QWORD *)v12 + 9) = 0;
    if ( *((_DWORD *)v12 + 8) > 0x100000u )
    {
      v9 = WPP_GLOBAL_Control;
      ClientInfo = -1073741811;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 15;
        goto LABEL_302;
      }
      return (unsigned int)ClientInfo;
    }
    v13 = *((unsigned int *)v12 + 5);
    v112 = 39;
    v102 = SpmpValidRequest(v13, 0x27u);
    v14 = v102;
    if ( !v102 )
    {
      v15 = *((unsigned int *)v12 + 5);
      v112 = 7;
      v102 = SpmpValidRequest(v15, 7u);
      v14 = v102;
      if ( !v102 )
      {
        v16 = *((unsigned int *)v12 + 5);
        v112 = 6;
        v102 = SpmpValidRequest(v16, 6u);
        v14 = v102;
        if ( !v102 )
        {
          v17 = *((unsigned int *)v12 + 5);
          v112 = 1;
          v102 = SpmpValidRequest(v17, 1u);
          v14 = v102;
          if ( !v102 )
          {
            v9 = WPP_GLOBAL_Control;
            ClientInfo = -1073741637;
            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v10 = 16;
              goto LABEL_302;
            }
            return (unsigned int)ClientInfo;
          }
        }
      }
    }
    v113 = LsaTokenInformationNull;
    v119 = SecurityAnonymous;
    v136 = 0;
    v122 = 0;
    v138 = 0;
    LocallyUniqueId[0].LowPart = 1;
    NtAllocateLocallyUniqueId((LUID *)&LocallyUniqueId[0].HighPart);
    LocallyUniqueId[1].HighPart = 0;
    v130 = 0;
    TlsSetValue(dwThreadPackage, *(LPVOID *)v14);
    if ( !*((_QWORD *)v12 + 5) )
    {
      v18 = LsapBuildDefaultTokenGroups(v12);
      ClientInfo = v18;
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            &WPP_5f4735df67a33b644648330a4d5d4709_Traceguids,
            (unsigned int)v18);
        }
        TlsSetValue(dwThreadPackage, (LPVOID)0xFFFFFFFFFFFFFFFFLL);
        goto LABEL_217;
      }
    }
    CurrentThreadCompartmentId = 1;
    v20 = 0;
    v21 = 1;
    v104 = 0;
    if ( *((_WORD *)v102 + 24) == 74 )
    {
      v22 = wcscmp_0(*((const wchar_t **)v102 + 7), L"MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
      v23 = IdentifierAuthority;
      if ( !v22 && *((_DWORD *)IdentifierAuthority + 8) >= 4u )
        v20 = **((_DWORD **)IdentifierAuthority + 3) == 5;
    }
    else
    {
      v23 = IdentifierAuthority;
    }
    v110 = LsapMapLogonType(
             v23,
             *((void **)v23 + 3),
             (struct _Session *)v123,
             &ProcessInformation,
             v131,
             &v137,
             &v105,
             v101);
    if ( v131 )
    {
      if ( *((char *)v131 + 68) < 0 )
      {
        CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
        SessionCompartmentId = GetSessionCompartmentId(ProcessInformation.SessionId);
        v21 = SessionCompartmentId;
        if ( CurrentThreadCompartmentId != SessionCompartmentId )
        {
          v25 = SetCurrentThreadCompartmentId(SessionCompartmentId);
          if ( v25 )
          {
            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v26, CurrentThreadCompartmentId, v21, v25);
            }
          }
          else
          {
            v104 = 1;
          }
        }
      }
    }
    v27 = LsapCallAuthPackagesForPreLogonSurrogate(
            v135,
            v110,
            v134,
            v23,
            (struct _SECPKG_SURROGATE_LOGON *)LocallyUniqueId);
    v103 = 32;
    ClientInfo = v27;
    if ( v27 >= 0 )
      ClientInfo = LsapCallAuthPackageForLogon(
                     v112,
                     v102,
                     v135,
                     v110,
                     v134,
                     IdentifierAuthority,
                     (struct _SECPKG_SURROGATE_LOGON *)LocallyUniqueId,
                     &v111,
                     (void **)&ExpirationTime,
                     (struct _UNICODE_STRING **)&v115,
                     (struct _UNICODE_STRING **)&v118,
                     (struct _UNICODE_STRING **)&v125,
                     &v143,
                     &v128);
    if ( v104 )
    {
      v28 = SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
      if ( v28 )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v29, v21, CurrentThreadCompartmentId, v28);
        }
      }
    }
    TlsSetValue(dwThreadPackage, (LPVOID)0xFFFFFFFFFFFFFFFFLL);
    v12 = IdentifierAuthority;
    AuthenticationId = (struct _LUID)*((_QWORD *)IdentifierAuthority + 11);
    if ( ClientInfo < 0 )
    {
      if ( !v20 )
      {
        LsapClientFree(*((void **)IdentifierAuthority + 9));
        *((_QWORD *)v12 + 9) = 0;
      }
      goto LABEL_61;
    }
    v7 = 33;
    v103 = 33;
    v114 = 33;
    if ( (LsapIsShadowAdminUser(ExpirationTime) || LsapIsShadowAdminUser((LPCWSTR)v115->Children[1]))
      && (!LsapShadowAdminEnabled || !LsapCanLogonShadowAdmin(v140.ClientToken, v140.ProcessID)) )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          &WPP_5f4735df67a33b644648330a4d5d4709_Traceguids,
          v140.ProcessID);
      ClientInfo = -1073741790;
      goto LABEL_216;
    }
    if ( ((v112 - 7) & 0xFFFFFFDF) != 0 )
    {
      v143.LogonId = AuthenticationId;
      v143.DomainName = (UNICODE_STRING)v118->0;
      v143.DownlevelName = (UNICODE_STRING)v115->0;
    }
    if ( LsapGlobalForceSCLogon
      && v105
      && (!v140.HasTcbPrivilege || !v131 || (*((_DWORD *)v131 + 17) & 0x2000) == 0)
      && (v143.Flags & 0x180040) == 0
      && !LsapCheckLapsManagedAccount(ExpirationTime) )
    {
      *((_DWORD *)v12 + 16) = -1073741062;
      ClientInfo = -1073741714;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_216;
      v31 = 21;
      v32 = 3221225582LL;
      goto LABEL_78;
    }
    v33 = LsapLocateLogonSession(&AuthenticationId);
    v138 = v33;
    v34 = v33;
    if ( !v33 )
    {
      ClientInfo = -1073741729;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_216;
      v31 = 22;
      goto LABEL_83;
    }
    if ( v101[0] )
      *((_DWORD *)v33 + 144) |= 0x40000u;
    v14 = v102;
    v35 = *(void **)v102;
    if ( (v143.Flags & 0xFF000000) != 0 )
    {
      v36 = SpmpLookupPackageByRpcId(HIBYTE(v143.Flags));
      if ( v36 )
      {
        *((_QWORD *)v34 + 38) = *(_QWORD *)v36;
        v35 = *(void **)v36;
      }
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned int)LsapAuditingLogonSystemAccessRights() )
      {
        SystemAccessAuditInfo = LsapCreateSystemAccessAuditInfo(v110, (struct _SYSTEM_ACCESS_AUDIT_INFO **)&v132);
        ClientInfo = SystemAccessAuditInfo;
        if ( SystemAccessAuditInfo < 0 )
        {
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              &WPP_5f4735df67a33b644648330a4d5d4709_Traceguids,
              (unsigned int)SystemAccessAuditInfo);
          }
          v7 = v103;
          goto LABEL_217;
        }
      }
    }
    v38 = v143.Flags & 0x10;
    v101[0] = v38 != 0;
    v113 = v111;
    TlsSetValue(dwThreadPackage, v35);
    ClientInfo = LsapAuUserLogonPolicyFilter(
                   v110,
                   &v111,
                   (void **)&ExpirationTime,
                   *((struct _TOKEN_GROUPS **)v12 + 5),
                   (struct _QUOTA_LIMITS *)v120,
                   (struct _PRIVILEGE_SET **)&hMem,
                   0,
                   (struct _SYSTEM_ACCESS_AUDIT_INFO *)v132);
    TlsSetValue(dwThreadPackage, (LPVOID)0xFFFFFFFFFFFFFFFFLL);
    if ( ClientInfo < 0 )
    {
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_61;
      v43 = 24;
      goto LABEL_100;
    }
    if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(v40, v39, v41)
      && LsapCrashOnAuditFailState == 2
      && (unsigned int)(v113 - 1) <= 2
      && (AuthenticationId.LowPart != 997 || AuthenticationId.HighPart)
      && (AuthenticationId.LowPart != 996 || AuthenticationId.HighPart)
      && (AuthenticationId.LowPart != 995 || AuthenticationId.HighPart) )
    {
      v46 = LsapSidPresentInGroups((struct _TOKEN_GROUPS *)ExpirationTime[3].QuadPart, *((void **)WellKnownSids + 96));
      v45 = 0;
      if ( !v46 )
      {
        v120 = 0;
        v123 = 0;
        LODWORD(IdentifierAuthority) = 0;
        WORD2(IdentifierAuthority) = 1280;
        v47 = RtlAllocateAndInitializeSid(
                (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority,
                2u,
                0x5Au,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                &v120);
        ClientInfo = v47;
        if ( v47 < 0 )
        {
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_61;
          }
          v43 = 25;
          v44 = (unsigned int)v47;
          goto LABEL_101;
        }
        ClientInfo = RtlAllocateAndInitializeSid(
                       (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority,
                       2u,
                       0x60u,
                       0,
                       0,
                       0,
                       0,
                       0,
                       0,
                       0,
                       &v123);
        if ( ClientInfo < 0 )
        {
          RtlFreeSid(v120);
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_61;
          }
          v43 = 26;
LABEL_100:
          v44 = (unsigned int)ClientInfo;
LABEL_101:
          WPP_SF_d(*((_QWORD *)v42 + 2), v43, &WPP_5f4735df67a33b644648330a4d5d4709_Traceguids, v44);
LABEL_61:
          v7 = v103;
LABEL_216:
          v14 = v102;
LABEL_217:
          if ( v131 )
          {
            v69 = (void *)*((_QWORD *)v131 + 51);
            if ( v69 )
              SetEvent(v69);
          }
          if ( TokenHandle && (v7 & 0x10) == 0 )
          {
            NtClose(TokenHandle);
            v7 &= ~1u;
            TokenHandle = 0;
          }
          if ( Handle )
          {
            NtClose(Handle);
            v7 &= ~4u;
            if ( (v7 & 0x90) != 0 )
              v7 &= ~1u;
          }
          v70 = *((_DWORD *)v12 + 4);
          if ( ClientInfo >= 0 )
          {
            if ( (v143.Flags & 8) != 0 )
            {
              if ( v70 == Interactive )
              {
                v70 = CachedInteractive;
              }
              else if ( v70 == RemoteInteractive )
              {
                v70 = CachedRemoteInteractive;
              }
            }
            else if ( v70 == CachedRemoteInteractive )
            {
              v70 = RemoteInteractive;
            }
          }
          if ( v138 )
            LsapReleaseLogonSession(v138);
          if ( (v7 & 0x20) != 0 )
          {
            LsapCallAuthPackagesForPostLogonSurrogate(
              v135,
              v70,
              v134,
              v12,
              (struct _SECPKG_SURROGATE_LOGON *)LocallyUniqueId,
              ClientInfo,
              v111,
              ExpirationTime,
              (struct _UNICODE_STRING *)v115,
              (struct _UNICODE_STRING *)v118,
              (struct _UNICODE_STRING *)v125,
              &v143,
              v128);
            v7 &= ~0x20u;
          }
          if ( ClientInfo < 0 )
          {
            if ( (v7 & 1) != 0 )
            {
              (*((void (__fastcall **)(struct _LUID *))v14 + 20))(&AuthenticationId);
              LsapDeleteLogonSession(&AuthenticationId);
              LsapClientFree(*((void **)v12 + 9));
              *((_QWORD *)v12 + 9) = 0;
              LsapFreeTokenInformation(v111, ExpirationTime);
              ExpirationTime = 0;
            }
            if ( (v7 & 4) != 0 )
              LsapDeleteLogonSession(&v117);
          }
          TlsSetValue(dwThreadPackage, *(LPVOID *)v14);
          _InterlockedDecrement((volatile signed __int32 *)v14 + 10);
          if ( v100[0] )
          {
            v71 = v136;
            v72 = v122;
          }
          else if ( ClientInfo < 0 || v113 )
          {
            v71 = (struct _UNICODE_STRING *)v115;
            v72 = (struct _UNICODE_STRING *)v118;
          }
          else
          {
            v71 = (struct _UNICODE_STRING *)((char *)WellKnownSids + 880);
            v72 = (struct _UNICODE_STRING *)((char *)WellKnownSids + 896);
          }
          v73 = v121;
          LsapAuGenerateLogonAudits(
            ClientInfo,
            *((_DWORD *)v12 + 16),
            &v140,
            &AuthenticationId,
            &v117,
            v70,
            v119,
            v71,
            v72,
            v121,
            (struct _UNICODE_STRING *)v125,
            (struct _TOKEN_SOURCE *)v12 + 3,
            (struct _SYSTEM_ACCESS_AUDIT_INFO *)v132);
          v74 = 0;
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::GetImpl'::`2'::impl) )
            LsapFreeSystemAccessAuditInfo(v132);
          TlsSetValue(dwThreadPackage, (LPVOID)0xFFFFFFFFFFFFFFFFLL);
          if ( ClientInfo == -1073741715
            && (*((_DWORD *)v12 + 16) == -1073741718 || *((_DWORD *)v12 + 16) == -1073741724) )
          {
            *((_DWORD *)v12 + 16) = 0;
          }
          v77 = v125;
          if ( v125 )
          {
            LsapSubProv_FreeRoutine(v125->Children[1], v75);
            LsapSubProv_FreeRoutine(v125, v78);
          }
          if ( v126 )
          {
            if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(v77, v75, v76) && ClientInfo >= 0 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))LsapAdtAuditSpecialPrivileges)(
                v126,
                AuthenticationId,
                v73,
                v71,
                v72);
            LsapSubProv_FreeRoutine(v126, v79);
            v126 = 0;
          }
          if ( v127 )
          {
            if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(v77, v75, v76) && ClientInfo >= 0 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))LsapAdtAuditSpecialPrivileges)(
                v127,
                v117,
                v73,
                v71,
                v72);
            LsapSubProv_FreeRoutine(v127, v80);
            v127 = 0;
          }
          if ( ((v112 - 7) & 0xFFFFFFDF) == 0 )
          {
            LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v143.DownlevelName.Buffer, v75);
            LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v143.DomainName.Buffer, v81);
            LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v143.UserSid, v82);
            LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v143.LogonServer.Buffer, v83);
            LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v143.DnsDomainName.Buffer, v84);
            LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v143.Upn.Buffer, v85);
            Buffer = (struct _RTL_BALANCED_NODE *)v143.Password.Buffer;
            if ( v143.Password.Buffer )
            {
              Length = v143.Password.Length;
              if ( v143.Password.Length )
              {
                do
                {
                  LOBYTE(Buffer->Children[0]) = 0;
                  Buffer = (struct _RTL_BALANCED_NODE *)((char *)Buffer + 1);
                  --Length;
                }
                while ( Length );
                Buffer = (struct _RTL_BALANCED_NODE *)v143.Password.Buffer;
              }
              LsapSubProv_FreeRoutine(Buffer, v75);
            }
            v88 = (struct _RTL_BALANCED_NODE *)v143.OldPassword.Buffer;
            if ( v143.OldPassword.Buffer )
            {
              v89 = v143.OldPassword.Length;
              if ( v143.OldPassword.Length )
              {
                do
                {
                  LOBYTE(v88->Children[0]) = 0;
                  v88 = (struct _RTL_BALANCED_NODE *)((char *)v88 + 1);
                  --v89;
                }
                while ( v89 );
                v88 = (struct _RTL_BALANCED_NODE *)v143.OldPassword.Buffer;
              }
              LsapSubProv_FreeRoutine(v88, v75);
            }
            v90 = (struct _RTL_BALANCED_NODE *)v143.Spare1.Buffer;
            if ( v143.Spare1.Buffer )
            {
              v91 = v143.Spare1.Length;
              if ( v143.Spare1.Length )
              {
                do
                {
                  LOBYTE(v90->Children[0]) = 0;
                  v90 = (struct _RTL_BALANCED_NODE *)((char *)v90 + 1);
                  --v91;
                }
                while ( v91 );
                v90 = (struct _RTL_BALANCED_NODE *)v143.Spare1.Buffer;
              }
              LsapSubProv_FreeRoutine(v90, v75);
            }
            if ( v128 )
              LsapFreeSupplementalCredentials(&v128);
            if ( hMem )
              LocalFree(hMem);
          }
          if ( v115 )
          {
            LsapSubProv_FreeRoutine(v115->Children[1], v75);
            LsapSubProv_FreeRoutine(v115, v92);
            v115 = 0;
          }
          if ( v118 )
          {
            LsapSubProv_FreeRoutine(v118->Children[1], v75);
            LsapSubProv_FreeRoutine(v118, v93);
            v118 = 0;
          }
          LsapSubProv_FreeRoutine(v73, v75);
          v94 = v130;
          if ( v130 )
          {
            if ( LocallyUniqueId[1].HighPart )
            {
              do
              {
                LsapZeroAndFree((PVOID)v94[v74].ParentValue);
                v94 = v130;
                ++v74;
              }
              while ( v74 < LocallyUniqueId[1].HighPart );
            }
            LsapSubProv_FreeRoutine(v94, v94);
            LocallyUniqueId[1].HighPart = 0;
            v130 = 0;
          }
          if ( (int)(ClientInfo + 0x80000000) >= 0 && ClientInfo != -1073741043 )
          {
            v114 = 0;
            LsapCheckRestrictedMode(0, (int *)&v114, 0);
            if ( v114 )
            {
              ClientInfo = -1073741043;
              *((_DWORD *)v12 + 16) = 0;
            }
          }
          return (unsigned int)ClientInfo;
        }
        if ( !LsapSidPresentInGroups((struct _TOKEN_GROUPS *)ExpirationTime[3].QuadPart, v120)
          && !LsapSidPresentInGroups((struct _TOKEN_GROUPS *)ExpirationTime[3].QuadPart, v123) )
        {
          v48 = v120;
          ClientInfo = -1073741714;
          *((_DWORD *)v12 + 16) = -1073741712;
          RtlFreeSid(v48);
          RtlFreeSid(v123);
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_61;
          }
          v43 = 27;
          v44 = 3221225582LL;
          goto LABEL_101;
        }
        RtlFreeSid(v120);
        RtlFreeSid(v123);
      }
    }
    v49 = (unsigned int)v111;
    if ( v111 )
    {
      if ( v111 == LsaTokenInformationV1 || (v50 = (unsigned int)(v111 - 2), (unsigned int)v50 <= 1) )
      {
        v51 = LsapBuildAndCreateToken(
                v12,
                ExpirationTime,
                v111,
                &ProcessInformation,
                &v143,
                v110,
                &AuthenticationId,
                (unsigned __int64)v35,
                v101[0],
                SubAuthority7,
                (struct _UNICODE_STRING *)Sid,
                v106,
                (void **)&v121,
                &TokenHandle,
                &Handle,
                &v117,
                &v114);
        v7 = v114;
        ClientInfo = v51;
        v103 = v114;
        v119 = 2 - (v38 != 0);
LABEL_132:
        if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(v50, v45, v49) && ClientInfo >= 0 )
        {
          if ( v113 )
          {
            v52 = v115;
            v53 = v118;
          }
          else
          {
            v52 = (struct _RTL_BALANCED_NODE *)((char *)WellKnownSids + 880);
            v53 = (struct _RTL_BALANCED_NODE *)((char *)WellKnownSids + 896);
          }
          v122 = (struct _UNICODE_STRING *)v53;
          v136 = (struct _UNICODE_STRING *)v52;
          if ( SpmpEventEnabled(&LSA_GROUPS_AT_LOGON) )
          {
            HIDWORD(SubAuthority3) = HIDWORD(v122);
            ReturnLength = (struct _UNICODE_STRING *)v52;
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))LsapReportGroupsAtLogonEvent)(
              &LSA_GROUPS_AT_LOGON,
              (union _LARGE_INTEGER)ExpirationTime[3].QuadPart,
              v121,
              0);
          }
          if ( LsapAdtSglSidCount )
          {
            if ( (int)LsapAdtAuditingEnabledByLogonId(109, &AuthenticationId, 8, v100) >= 0
              && v100[0]
              && (unsigned __int8)IsLsapAdtInitParametersArrayPresent(v55, v54, v56) )
            {
              SubAuthority3 = &v140;
              ReturnLength = (struct _UNICODE_STRING *)v121;
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))LsapAdtGenerateSpecialGroupsLogonAudit)(
                (union _LARGE_INTEGER)ExpirationTime[3].QuadPart,
                &AuthenticationId,
                v52,
                v122);
            }
            else
            {
              v100[0] = 0;
            }
          }
          if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(v55, v54, v56)
            && SpmpEventEnabled(&LSA_CLAIMS_AT_LOGON) )
          {
            ReturnLength = (struct _UNICODE_STRING *)&AuthenticationId;
            LsapReportClaimsAtLogonEvent(TokenHandle, v121, v52, v122);
          }
        }
        LsapFreeTokenInformation(v111, ExpirationTime);
        ExpirationTime = 0;
        if ( ClientInfo < 0 )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_216;
          }
          v31 = 28;
LABEL_83:
          v32 = (unsigned int)ClientInfo;
LABEL_78:
          WPP_SF_d(*((_QWORD *)v30 + 2), v31, &WPP_5f4735df67a33b644648330a4d5d4709_Traceguids, v32);
          goto LABEL_216;
        }
        if ( !v106[0] )
        {
          PrivilegeSetFromToken = NtSetInformationToken(TokenHandle, TokenSessionId, &ProcessInformation, 4u);
          ClientInfo = PrivilegeSetFromToken;
          if ( PrivilegeSetFromToken < 0 )
          {
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_61;
            }
            v31 = 29;
LABEL_157:
            v32 = (unsigned int)PrivilegeSetFromToken;
            goto LABEL_78;
          }
        }
        PrivilegeSetFromToken = LsapAdtGetPrivilegeSetFromToken(TokenHandle, (struct _PRIVILEGE_SET **)&v126);
        ClientInfo = PrivilegeSetFromToken;
        if ( PrivilegeSetFromToken < 0 )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_61;
          }
          v31 = 30;
          goto LABEL_157;
        }
        PrivilegeSetFromToken = LsapSetSessionToken(TokenHandle, &AuthenticationId, &ProcessInformation);
        ClientInfo = PrivilegeSetFromToken;
        if ( PrivilegeSetFromToken < 0 )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_61;
          }
          v31 = 31;
          goto LABEL_157;
        }
        if ( (v7 & 0xD0) != 0 )
        {
          PrivilegeSetFromToken = LsapAdtGetPrivilegeSetFromToken(Handle, (struct _PRIVILEGE_SET **)&v127);
          ClientInfo = PrivilegeSetFromToken;
          if ( PrivilegeSetFromToken < 0 )
          {
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_61;
            }
            v31 = 32;
            goto LABEL_157;
          }
          PrivilegeSetFromToken = LsapSetSessionToken(Handle, &v117, &ProcessInformation);
          ClientInfo = PrivilegeSetFromToken;
          if ( PrivilegeSetFromToken < 0 )
          {
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_61;
            }
            v31 = 33;
            goto LABEL_157;
          }
        }
        if ( (AuthenticationId.LowPart != 999 || AuthenticationId.HighPart)
          && (AuthenticationId.LowPart != 996 || AuthenticationId.HighPart) )
        {
          v58 = &v143;
          v59 = 0;
          if ( ((v112 - 7) & 0xFFFFFFDF) != 0 )
            v58 = 0;
          LOBYTE(v59) = v113 == LsaTokenInformationNull;
          PrivilegeSetFromToken = LsapSetLinkedLogonSessionAccountInfo(
                                    (struct _LUID *)((unsigned __int64)&v117 & -(__int64)((v7 & 0xD0) != 0)),
                                    &AuthenticationId,
                                    (struct _UNICODE_STRING *)v115,
                                    (struct _UNICODE_STRING *)v118,
                                    ReturnLength,
                                    v121,
                                    *((enum _SECURITY_LOGON_TYPE *)v12 + 4),
                                    v59,
                                    v58);
          ClientInfo = PrivilegeSetFromToken;
          if ( PrivilegeSetFromToken < 0 )
          {
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_61;
            }
            v31 = 36;
            goto LABEL_157;
          }
        }
        v60 = v110;
        v61 = LsapCheckAndUpdateRestrictedModeLogon(v110, v121);
        ClientInfo = v61;
        if ( v61 == -1073741043 )
        {
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              37,
              &WPP_5f4735df67a33b644648330a4d5d4709_Traceguids,
              3221226253LL);
            goto LABEL_216;
          }
          goto LABEL_61;
        }
        if ( v61 < 0 )
        {
          v64 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control )
          {
LABEL_197:
            if ( v60 != Network )
              LsapUpdateNamesAndCredentials(v60, &v137, (struct _UNICODE_STRING *)v115, &v143, v128);
            v65 = TokenHandle;
            if ( v7 >= 0 && Handle )
              v65 = Handle;
            ClientInfo = LsapDuplicateHandle(v65, (PHANDLE)v12 + 12);
            if ( ClientInfo >= 0 )
            {
              if ( v117 )
              {
                p_AuthenticationId = &AuthenticationId;
                v67 = 0;
              }
              else
              {
                p_AuthenticationId = &v117;
                v67 = 1;
              }
              v68 = &AuthenticationId;
              if ( !v67 )
                v68 = &v117;
              LsapPostLogonUser(v143.Flags, v68, p_AuthenticationId);
              goto LABEL_216;
            }
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_61;
            }
            v31 = 40;
            goto LABEL_83;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          {
LABEL_194:
            if ( v64 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v64 + 7) & 0x800000) != 0 )
            {
              LODWORD(SubAuthority3) = v60;
              LODWORD(ReturnLength) = v143.LogonId.LowPart;
              WPP_SF_DDd(
                *((_QWORD *)v64 + 2),
                v62,
                v63,
                (unsigned int)v143.LogonId.HighPart,
                ReturnLength,
                SubAuthority3);
            }
            goto LABEL_197;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            &WPP_5f4735df67a33b644648330a4d5d4709_Traceguids,
            (unsigned int)v61);
        }
        v64 = WPP_GLOBAL_Control;
        goto LABEL_194;
      }
    }
    else
    {
      v119 = SecurityImpersonation;
      ClientInfo = LsapCreateNullToken(&AuthenticationId, (PTOKEN_SOURCE)v12 + 3, ExpirationTime, &TokenHandle);
    }
    v7 = v103;
    goto LABEL_132;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 12;
    goto LABEL_302;
  }
  return (unsigned int)ClientInfo;
}

```

## disassembly

```asm
0x180056fec  push    rbp
0x180056fee  push    rbx
0x180056fef  push    rsi
0x180056ff0  push    rdi
0x180056ff1  push    r12
0x180056ff3  push    r13
0x180056ff5  push    r14
0x180056ff7  push    r15
0x180056ff9  lea     rbp, [rsp-1F8h]
0x180057001  sub     rsp, 308h
0x180057008  mov     rax, cs:__security_cookie
0x18005700f  xor     rax, rsp
0x180057012  mov     [rbp+230h+var_48], rax
0x180057019  mov     r15, [rbp+230h+arg_20]
0x180057020  xor     edi, edi
0x180057022  mov     r12, rcx
0x180057025  mov     [rbp+230h+var_1B8], rcx
0x180057029  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x18005702f  mov     [rbp+230h+ExpirationTime], rdi
0x180057033  mov     [rbp+230h+var_274], edi
0x180057036  mov     [rbp+230h+TokenHandle], rdi
0x18005703a  mov     [rbp+230h+Handle], rdi
0x18005703e  mov     [rbp+230h+var_260], rdi
0x180057042  mov     [rbp+230h+var_248], rdi
0x180057046  mov     [rbp+230h+var_210], rdi
0x18005704a  mov     [rbp+230h+var_230], rdi
0x18005704e  mov     qword ptr [rbp+230h+AuthenticationId.LowPart], rdi
0x180057052  mov     qword ptr [rbp+230h+var_250.LowPart], rdi
0x180057056  mov     [rbp+230h+hMem], rdi
0x18005705d  mov     [rbp+230h+var_208], rdi
0x180057061  mov     [rbp+230h+var_200], rdi
0x180057065  mov     [rbp+230h+var_238], r8
0x180057069  mov     [rbp+230h+var_1C0], rdx
0x18005706d  mov     [rbp+230h+var_2A8], r9b
0x180057071  call    cs:__imp_TlsGetValue
0x180057078  nop     dword ptr [rax+rax+00h]
0x18005707d  xorps   xmm0, xmm0
0x180057080  mov     [rbp+230h+var_130.LogonId.LowPart], edi
0x180057086  xor     edx, edx; Val
0x180057088  mov     [rbp+230h+var_220], rax
0x18005708c  mov     r8d, 0DCh; Size
0x180057092  lea     rcx, [rbp+230h+var_130.LogonId.HighPart]; void *
0x180057099  movups  xmmword ptr [rbp+230h+var_190.LogonId.LowPart], xmm0
0x1800570a0  movups  xmmword ptr [rbp+230h+var_190.HasTcbPrivilege], xmm0
0x1800570a7  call    memset_0
0x1800570ac  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x1800570b2  xorps   xmm1, xmm1
0x1800570b5  xorps   xmm0, xmm0
0x1800570b8  mov     [rbp+230h+var_1F8], rdi
0x1800570bc  xor     eax, eax
0x1800570be  mov     [rbp+230h+ProcessInformation], edi
0x1800570c1  movups  xmmword ptr [rbp+230h+ClientId.UniqueProcess], xmm0
0x1800570c8  mov     [rbp+230h+var_1E0], rax
0x1800570cc  mov     r13d, edi
0x1800570cf  movups  xmmword ptr [rbp+230h+ObjectAttributes.Length], xmm1
0x1800570d6  mov     [rbp+230h+ProcessHandle], rdi
0x1800570da  movups  xmmword ptr [rbp+230h+ObjectAttributes.ObjectName], xmm1
0x1800570e1  mov     qword ptr [rbp+230h+var_1A8.LowPart], rdi
0x1800570e8  movups  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800570ef  mov     [rbp+230h+var_292], dil
0x1800570f3  movups  xmmword ptr [rbp+230h+LocallyUniqueId.LowPart], xmm0
0x1800570f7  mov     [rbp+230h+var_2B0], dil
0x1800570fb  mov     [rbp+230h+var_293], dil
0x1800570ff  mov     [rbp+230h+var_1D0], rdi
0x180057103  call    cs:__imp_TlsGetValue
0x18005710a  nop     dword ptr [rax+rax+00h]
0x18005710f  lea     edx, [rdi+20h]; Size
0x180057112  mov     [rbp+230h+var_1D8], rax
0x180057116  lea     rcx, [rbp+230h+var_190]; struct _SECPKG_CLIENT_INFO_EX *
0x18005711d  call    ?LsapGetClientInfoEx@@YAJPEAU_SECPKG_CLIENT_INFO_EX@@K@Z; LsapGetClientInfoEx(_SECPKG_CLIENT_INFO_EX *,ulong)
0x180057122  mov     ebx, eax
0x180057124  test    eax, eax
0x180057126  jns     short loc_180057156
0x180057128  mov     rcx, cs:WPP_GLOBAL_Control
0x18005712f  lea     rsi, WPP_GLOBAL_Control
0x180057136  cmp     rcx, rsi
0x180057139  jz      loc_180058619
0x18005713f  mov     edi, 1
0x180057144  test    [rcx+1Ch], dil
0x180057148  jz      loc_180058619
0x18005714e  lea     edx, [rdi+9]
0x180057151  jmp     loc_180058606
0x180057156  mov     al, [rbp+230h+var_190.ClientFlags]
0x18005715c  mov     edi, 1
0x180057161  test    al, 2
0x180057163  jnz     loc_1800585E3
0x180057169  test    dil, al
0x18005716c  jnz     loc_1800585E3
0x180057172  lea     rsi, WPP_GLOBAL_Control
0x180057179  lea     r14, WPP_5f4735df67a33b644648330a4d5d4709_Traceguids
0x180057180  test    r15, r15
0x180057183  jnz     loc_180057275
0x180057189  movsxd  rax, [rbp+230h+var_190.ProcessID]
0x180057190  lea     r9, [rbp+230h+ClientId]; ClientId
0x180057197  xorps   xmm0, xmm0
0x18005719a  mov     [rbp+230h+ClientId.UniqueProcess], rax
0x1800571a1  lea     r8, [rbp+230h+ObjectAttributes]; ObjectAttributes
0x1800571a8  mov     [rbp+230h+ObjectAttributes.Length], 30h ; '0'
0x1800571b2  mov     edx, 1000h; DesiredAccess
0x1800571b7  mov     [rbp+230h+ObjectAttributes.RootDirectory], r15
0x1800571be  lea     rcx, [rbp+230h+ProcessHandle]; ProcessHandle
0x1800571c2  mov     [rbp+230h+ObjectAttributes.Attributes], r15d
0x1800571c9  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800571d1  mov     [rbp+230h+ObjectAttributes.ObjectName], r15
0x1800571d8  mov     [rbp+230h+ClientId.UniqueThread], r15
0x1800571df  call    cs:__imp_NtOpenProcess
0x1800571e6  nop     dword ptr [rax+rax+00h]
0x1800571eb  mov     ebx, eax
0x1800571ed  test    eax, eax
0x1800571ef  jns     short loc_180057216
0x1800571f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800571f8  cmp     rcx, rsi
0x1800571fb  jz      loc_180058619
0x180057201  test    [rcx+1Ch], dil
0x180057205  jz      loc_180058619
0x18005720b  lea     edx, [rdi+0Bh]
0x18005720e  mov     r8, r14
0x180057211  jmp     loc_18005860D
0x180057216  mov     rcx, [rbp+230h+ProcessHandle]; ProcessHandle
0x18005721a  lea     r8, [rbp+230h+ProcessInformation]; ProcessInformation
0x18005721e  mov     r9d, 4; ProcessInformationLength
0x180057224  mov     [rsp+340h+ReturnLength], r15; ReturnLength
0x180057229  lea     edx, [r9+14h]; ProcessInformationClass
0x18005722d  call    cs:__imp_NtQueryInformationProcess
0x180057234  nop     dword ptr [rax+rax+00h]
0x180057239  mov     rcx, [rbp+230h+ProcessHandle]; Handle
0x18005723d  mov     ebx, eax
0x18005723f  call    cs:__imp_NtClose
0x180057246  nop     dword ptr [rax+rax+00h]
0x18005724b  test    ebx, ebx
0x18005724d  jns     short loc_180057270
0x18005724f  mov     rcx, cs:WPP_GLOBAL_Control
0x180057256  cmp     rcx, rsi
0x180057259  jz      loc_180058619
0x18005725f  test    [rcx+1Ch], dil
0x180057263  jz      loc_180058619
0x180057269  mov     edx, 0Dh
0x18005726e  jmp     short loc_18005720E
0x180057270  mov     eax, [rbp+230h+ProcessInformation]
0x180057273  jmp     short loc_1800572A4
0x180057275  mov     rcx, cs:WPP_GLOBAL_Control
0x18005727c  cmp     rcx, rsi
0x18005727f  jz      short loc_18005729B
0x180057281  test    byte ptr [rcx+1Ch], 4
0x180057285  jz      short loc_18005729B
0x180057287  mov     r9d, [r15]
0x18005728a  mov     edx, 0Eh
0x18005728f  mov     rcx, [rcx+10h]
0x180057293  mov     r8, r14
0x180057296  call    WPP_SF_d
0x18005729b  mov     eax, [r15]
0x18005729e  xor     r15d, r15d
0x1800572a1  mov     [rbp+230h+ProcessInformation], eax
0x1800572a4  mov     [r12+8], eax
0x1800572a9  mov     r12, [r12]
0x1800572ad  add     r12, 30h ; '0'
0x1800572b1  mov     [rbp+230h+IdentifierAuthority], r12
0x1800572b8  mov     [r12+48h], r15
0x1800572bd  cmp     dword ptr [r12+20h], 100000h
0x1800572c6  jbe     short loc_1800572F1
0x1800572c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800572cf  mov     ebx, 0C000000Dh
0x1800572d4  cmp     rcx, rsi
0x1800572d7  jz      loc_180058619
0x1800572dd  test    [rcx+1Ch], dil
0x1800572e1  jz      loc_180058619
0x1800572e7  mov     edx, 0Fh
0x1800572ec  jmp     loc_18005720E
0x1800572f1  mov     ecx, [r12+14h]; unsigned __int64
0x1800572f6  mov     ebx, 27h ; '''
0x1800572fb  mov     edx, ebx; unsigned int
0x1800572fd  mov     [rbp+230h+var_270], ebx
0x180057300  call    ?SpmpValidRequest@@YAPEAU_LSAP_SECURITY_PACKAGE@@_KK@Z; SpmpValidRequest(unsigned __int64,ulong)
0x180057305  xor     ebx, ebx
0x180057307  mov     [rbp+230h+var_2A0], rax
0x18005730b  mov     r15, rax
0x18005730e  test    rax, rax
0x180057311  jnz     loc_180057399
0x180057317  mov     ecx, [r12+14h]; unsigned __int64
0x18005731c  lea     ebx, [rax+7]
0x18005731f  mov     edx, ebx; unsigned int
0x180057321  mov     [rbp+230h+var_270], ebx
0x180057324  call    ?SpmpValidRequest@@YAPEAU_LSAP_SECURITY_PACKAGE@@_KK@Z; SpmpValidRequest(unsigned __int64,ulong)
0x180057329  xor     ebx, ebx
0x18005732b  mov     [rbp+230h+var_2A0], rax
0x18005732f  mov     r15, rax
0x180057332  test    rax, rax
0x180057335  jnz     short loc_180057399
0x180057337  mov     ecx, [r12+14h]; unsigned __int64
0x18005733c  lea     ebx, [rax+6]
0x18005733f  mov     edx, ebx; unsigned int
0x180057341  mov     [rbp+230h+var_270], ebx
0x180057344  call    ?SpmpValidRequest@@YAPEAU_LSAP_SECURITY_PACKAGE@@_KK@Z; SpmpValidRequest(unsigned __int64,ulong)
0x180057349  xor     ebx, ebx
0x18005734b  mov     [rbp+230h+var_2A0], rax
0x18005734f  mov     r15, rax
0x180057352  test    rax, rax
0x180057355  jnz     short loc_180057399
0x180057357  mov     ecx, [r12+14h]; unsigned __int64
0x18005735c  mov     edx, edi; unsigned int
0x18005735e  mov     [rbp+230h+var_270], edi
0x180057361  call    ?SpmpValidRequest@@YAPEAU_LSAP_SECURITY_PACKAGE@@_KK@Z; SpmpValidRequest(unsigned __int64,ulong)
0x180057366  mov     [rbp+230h+var_2A0], rax
0x18005736a  mov     r15, rax
0x18005736d  test    rax, rax
0x180057370  jnz     short loc_180057399
0x180057372  mov     rcx, cs:WPP_GLOBAL_Control
0x180057379  mov     ebx, 0C00000BBh
0x18005737e  cmp     rcx, rsi
0x180057381  jz      loc_180058619
0x180057387  test    [rcx+1Ch], dil
0x18005738b  jz      loc_180058619
0x180057391  lea     edx, [rax+10h]
0x180057394  jmp     loc_18005720E
0x180057399  lea     rcx, [rbp+230h+LocallyUniqueId.HighPart]; LocallyUniqueId
0x18005739d  mov     [rbp+230h+var_26C], ebx
0x1800573a0  mov     [rbp+230h+var_240], ebx
0x1800573a3  mov     [rbp+230h+var_1B0], rbx
0x1800573aa  mov     [rbp+230h+var_228], rbx
0x1800573ae  mov     [rbp+230h+var_1A0], rbx
0x1800573b5  mov     [rbp+230h+LocallyUniqueId.LowPart], edi
0x1800573b8  call    cs:__imp_NtAllocateLocallyUniqueId
0x1800573bf  nop     dword ptr [rax+rax+00h]
0x1800573c4  mov     ecx, cs:?dwThreadPackage@@3KA; dwTlsIndex
0x1800573ca  mov     [rbp+230h+LocallyUniqueId.HighPart+8], ebx
0x1800573cd  mov     [rbp+230h+var_1E0], rbx
0x1800573d1  mov     rdx, [r15]; lpTlsValue
0x1800573d4  call    cs:__imp_TlsSetValue
0x1800573db  nop     dword ptr [rax+rax+00h]
0x1800573e0  cmp     [r12+28h], rbx
0x1800573e5  jnz     short loc_180057438
0x1800573e7  mov     rcx, r12; struct _LSAP_LOGON_USER_ARGS *
0x1800573ea  call    ?LsapBuildDefaultTokenGroups@@YAJPEAU_LSAP_LOGON_USER_ARGS@@@Z; LsapBuildDefaultTokenGroups(_LSAP_LOGON_USER_ARGS *)
0x1800573ef  mov     ebx, eax
0x1800573f1  test    eax, eax
0x1800573f3  jns     short loc_180057436
0x1800573f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800573fc  cmp     rcx, rsi
0x1800573ff  jz      short loc_18005741B
0x180057401  test    [rcx+1Ch], dil
0x180057405  jz      short loc_18005741B
0x180057407  mov     rcx, [rcx+10h]
0x18005740b  mov     edx, 11h
0x180057410  mov     r9d, eax
0x180057413  mov     r8, r14
0x180057416  call    WPP_SF_d
0x18005741b  mov     ecx, cs:?dwThreadPackage@@3KA; dwTlsIndex
0x180057421  or      rdx, 0FFFFFFFFFFFFFFFFh; lpTlsValue
0x180057425  call    cs:__imp_TlsSetValue
0x18005742c  nop     dword ptr [rax+rax+00h]
0x180057431  jmp     loc_180058111
0x180057436  xor     ebx, ebx
0x180057438  mov     rax, [rbp+230h+var_2A0]
0x18005743c  mov     r12d, edi
0x18005743f  movzx   r13d, bl
0x180057443  mov     r15d, edi
0x180057446  mov     [rbp+230h+var_294], bl
0x180057449  cmp     word ptr [rax+30h], 4Ah ; 'J'
0x18005744e  jnz     short loc_18005747E
0x180057450  mov     rcx, [rax+38h]; String1
0x180057454  lea     rdx, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x18005745b  call    wcscmp_0
0x180057460  mov     rbx, [rbp+230h+IdentifierAuthority]
0x180057467  test    eax, eax
0x180057469  jnz     short loc_180057485
0x18005746b  cmp     dword ptr [rbx+20h], 4
0x18005746f  jb      short loc_180057485
0x180057471  mov     rax, [rbx+18h]
0x180057475  cmp     dword ptr [rax], 5
0x180057478  cmovz   r13d, edi
0x18005747c  jmp     short loc_180057485
0x18005747e  mov     rbx, [rbp+230h+IdentifierAuthority]
0x180057485  mov     r8, [rbp+230h+var_220]; struct _Session *
0x180057489  lea     rax, [rbp+230h+var_2A8]
0x18005748d  mov     rdx, [rbx+18h]; void *
0x180057491  lea     r9, [rbp+230h+ProcessInformation]; struct _PROCESS_SESSION_INFORMATION *
0x180057495  mov     qword ptr [rsp+340h+SubAuthority5], rax; unsigned __int8 *
0x18005749a  mov     rcx, rbx; struct _LSAP_LOGON_USER_ARGS *
0x18005749d  lea     rax, [rbp+230h+var_293]
0x1800574a1  mov     qword ptr [rsp+340h+SubAuthority4], rax; unsigned __int8 *
0x1800574a6  lea     rax, [rbp+230h+var_1A8]
0x1800574ad  mov     qword ptr [rsp+340h+SubAuthority3], rax; struct _LUID *
0x1800574b2  mov     rax, [rbp+230h+var_1D8]
0x1800574b6  mov     [rsp+340h+ReturnLength], rax; struct _LSA_CALL_INFO *
0x1800574bb  call    ?LsapMapLogonType@@YA?AW4_SECURITY_LOGON_TYPE@@PEAU_LSAP_LOGON_USER_ARGS@@PEAXPEAU_Session@@PEAU_PROCESS_SESSION_INFORMATION@@PEAU_LSA_CALL_INFO@@PEAU_LUID@@PEAE6@Z; LsapMapLogonType(_LSAP_LOGON_USER_ARGS *,void *,_Session *,_PROCESS_SESSION_INFORMATION *,_LSA_CALL_INFO *,_LUID *,uchar *,uchar *)
0x1800574c0  mov     [rbp+230h+var_278], eax
0x1800574c3  mov     rax, [rbp+230h+var_1D8]
0x1800574c7  test    rax, rax
0x1800574ca  jz      short loc_18005753C
0x1800574cc  test    byte ptr [rax+44h], 80h
0x1800574d0  jz      short loc_18005753C
0x1800574d2  call    cs:__imp_GetCurrentThreadCompartmentId
0x1800574d9  nop     dword ptr [rax+rax+00h]
0x1800574de  mov     ecx, [rbp+230h+ProcessInformation]; SessionId
0x1800574e1  mov     r12d, eax
0x1800574e4  call    cs:__imp_GetSessionCompartmentId
0x1800574eb  nop     dword ptr [rax+rax+00h]
0x1800574f0  mov     r15d, eax
0x1800574f3  cmp     r12d, eax
0x1800574f6  jz      short loc_18005753C
  ... truncated ...
```
