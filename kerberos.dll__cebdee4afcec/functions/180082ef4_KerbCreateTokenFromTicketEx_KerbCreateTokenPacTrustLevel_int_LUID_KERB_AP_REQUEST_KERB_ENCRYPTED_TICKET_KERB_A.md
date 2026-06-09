# KerbCreateTokenFromTicketEx(KerbCreateTokenPacTrustLevel,int,_LUID *,KERB_AP_REQUEST *,KERB_ENCRYPTED_TICKET *,KERB_AUTHENTICATOR *,ulong,_KERB_ENCRYPTION_KEY *,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_ENCRYPTION_KEY *,_KERB_CONTEXT *,_LUID *,void * *,void * *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_S4U_DELEGATION_INFO * *,_LARGE_INTEGER *)

- ea: `0x180082ef4`
- end: `0x180083f77`
- name: `?KerbCreateTokenFromTicketEx@@YAJW4KerbCreateTokenPacTrustLevel@@HPEAU_LUID@@PEAUKERB_AP_REQUEST@@PEAUKERB_ENCRYPTED_TICKET@@PEAUKERB_AUTHENTICATOR@@KPEAU_KERB_ENCRYPTION_KEY@@PEAU_UNICODE_STRING@@65PEAU_KERB_CONTEXT@@1PEAPEAX8666PEAPEAU_S4U_DELEGATION_INFO@@PEAT_LARGE_INTEGER@@@Z`
- size: `4227`
- prototype: `__int64 __fastcall(ULONG, ULONG, struct _UNICODE_STRING **, struct KERB_AP_REQUEST *, __int64, __int64, int, __int64, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _KERB_ENCRYPTION_KEY *, __int64, LUID *, PSID *, HANDLE *, const UNICODE_STRING *, const UNICODE_STRING *, struct _UNICODE_STRING *, __int64, union _LARGE_INTEGER *)`
- caller_count: `4`
- callee_count: `44`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002db10`
- `0x180085080`
- `0x1800ce9ac`
- `0x1800cf66c`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069a0`
- `0x1800069e0`
- `0x180006ba0`
- `0x1800093f0`
- `0x18000b300`
- `0x180010e90`
- `0x180011064`
- `0x1800113f0`
- `0x180015740`
- `0x180016600`
- `0x180020690`
- `0x18002b678`
- `0x180030ea8`
- `0x180032d08`
- `0x180034a98`
- `0x180035e80`
- `0x18003c830`
- `0x18003d360`
- `0x180046818`
- `0x180048f6c`
- `0x18006178c`
- `0x1800643dc`
- `0x18006a90c`
- `0x18006ba6c`
- `0x18006c9a4`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x1800783b0`
- `0x18007a670`
- `0x1800816e0`
- `0x180082ef4`
- `0x180083f80`
- `0x180084020`
- `0x1800841e4`
- `0x180084b74`
- `0x180085014`
- `0x18008b70c`
- `0x180090040`
- `0x180093694`
- `0x1800be1c8`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083e45`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x18008366e`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x18008366e`
- `ntdll!RtlEqualUnicodeString` at `0x18008356b`
- `ntdll!RtlEqualUnicodeString` at `0x18008356b`
- `ntdll!NtClose` at `0x18008333c`
- `ntdll!NtClose` at `0x18008333c`
- `ntdll!RtlReleaseResource` at `0x180083199`
- `ntdll!RtlReleaseResource` at `0x180083469`
- `ntdll!RtlReleaseResource` at `0x180083199`
- `ntdll!RtlReleaseResource` at `0x180083469`
- `ntdll!RtlAcquireResourceShared` at `0x18008317d`
- `ntdll!RtlAcquireResourceShared` at `0x18008344b`
- `ntdll!RtlAcquireResourceShared` at `0x18008317d`
- `ntdll!RtlAcquireResourceShared` at `0x18008344b`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180083a91`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180083a91`
- `ntdll!RtlEqualSid` at `0x180083a72`
- `ntdll!RtlEqualSid` at `0x180083a72`
- `ntdll!NtQueryInformationToken` at `0x1800836a6`
- `ntdll!NtQueryInformationToken` at `0x1800836f2`
- `ntdll!NtQueryInformationToken` at `0x180083a54`
- `ntdll!NtQueryInformationToken` at `0x180083dd9`
- `ntdll!NtQueryInformationToken` at `0x1800836a6`
- `ntdll!NtQueryInformationToken` at `0x1800836f2`
- `ntdll!NtQueryInformationToken` at `0x180083a54`
- `ntdll!NtQueryInformationToken` at `0x180083dd9`
- `LSASRV!LsaIAddNamesToLogonSession` at `0x180083b1e`
- `LSASRV!LsaIAddNamesToLogonSession` at `0x180083b1e`

## string_xrefs

- `0x180083143`: `KerbCreateTokenFromTicketEx`
- `0x180083273`: `KerbCreateTokenFromTicketEx`
- `0x1800833f0`: `KerbCreateTokenFromTicketEx`
- `0x180083417`: `KerbCreateTokenFromTicketEx`
- `0x1800834a0`: `KerbCreateTokenFromTicketEx`
- `0x1800835b9`: `KerbCreateTokenFromTicketEx`
- `0x18008360c`: `KerbCreateTokenFromTicketEx`
- `0x18008363b`: `KerbCreateTokenFromTicketEx`
- `0x1800837dc`: `KerbCreateTokenFromTicketEx`
- `0x180083824`: `KerbCreateTokenFromTicketEx`
- `0x180083b4b`: `KerbCreateTokenFromTicketEx`
- `0x180083c1b`: `KerbCreateTokenFromTicketEx`
- `0x180083d76`: `KerbCreateTokenFromTicketEx`
- `0x1800833dc`: `Failed to create local pac for client : 0x%x\n`
- `0x180083406`: `Failed to create local pac for client : 0x%x\n`
- `0x1800835fb`: `KerbCreateTokenFromTicket, KerbDoesSKeyExist Status %#x, IsLocalSystem? %s\n`
- `0x180083634`: `KerbCreateTokenFromTicket, KerbDoesSKeyExist Status %#x, IsLocalSystem? %s\n`
- `0x180083761`: `Failed to make token information v3: 0x%x`
- `0x1800837cf`: `CreateToken : ClientName - %wZ\n`
- `0x180083812`: `CreateToken : ClientSamDomain - %wZ\n`
- `0x180083ab4`: `Failed to create logon session: 0x%x`
- `0x180083b36`: `KerbCreateTokenFromTicket for %wZ\%wZ, %wZ\n`
- `0x180083bf1`: `Failed to create token: 0x%x`
- `0x180083c0a`: `Failed to create token, substatus = 0x%x`
- `0x180083c5b`: `Failed to create delgation logon session: 0x%x`
- `0x180083cb2`: `Failed to create ASC logon session %x`
- `0x180083d7f`: `KerbCreateTokenFromTicket LOOPBACK using client token\n`
- `0x180083e23`: `KerbCreateTokenFromTicket could not duplicate client token %#x\n`
- `0x180083e4b`: `KerbCreateTokenFromTicket could not enable all prilileges %#x\n`

## pseudocode

```c
__int64 __fastcall KerbCreateTokenFromTicketEx(
        ULONG a1,
        ULONG a2,
        struct _UNICODE_STRING **a3,
        struct KERB_AP_REQUEST *a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        struct _UNICODE_STRING *a9,
        struct _UNICODE_STRING *a10,
        struct _KERB_ENCRYPTION_KEY *a11,
        __int64 a12,
        LUID *a13,
        PSID *a14,
        HANDLE *a15,
        const UNICODE_STRING *a16,
        const UNICODE_STRING *a17,
        struct _UNICODE_STRING *a18,
        __int64 a19,
        union _LARGE_INTEGER *a20)
{
  struct _UNICODE_STRING *v20; // rbx
  struct KERB_AP_REQUEST *v21; // rdx
  NTSTATUS AuthDataFromMultipleIfReleventContainers; // edi
  int v23; // eax
  struct PKERB_AUTHORIZATION_DATA_s *v24; // rcx
  __int64 v25; // r8
  int PacFromAuthData; // eax
  __int64 v27; // rsi
  struct _PACTYPE *v28; // rdi
  unsigned int v29; // edx
  ULONG v30; // r13d
  int v31; // eax
  __int64 v32; // rcx
  char v33; // r14
  Ntlmless::Kerberos *v34; // rcx
  char v35; // r12
  UNICODE_STRING *v36; // r15
  int v37; // esi
  const char *v38; // r9
  __int64 v39; // r8
  unsigned __int8 ShouldLogonSessionEnforceSidFiltering; // si
  unsigned __int8 v41; // r8
  struct _PAC_INFO_BUFFER *v42; // rax
  struct _UNICODE_STRING *v43; // r8
  int v44; // eax
  bool IsEnabled; // al
  unsigned __int8 v46; // r8
  PCUNICODE_STRING v47; // r13
  int DoesSKeyExist; // eax
  HANDLE v49; // r15
  unsigned __int64 v50; // rbx
  void *v51; // rcx
  void *v52; // rbx
  void *v53; // rax
  PSID *v54; // rsi
  unsigned __int8 v55; // r8
  int TokenInformationV3; // eax
  __int64 v57; // rcx
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v58; // rdx
  struct _UNICODE_STRING *v59; // rbx
  unsigned __int8 v60; // r8
  struct _KERB_INTERNAL_NAME *v61; // r13
  int v62; // r14d
  union _LARGE_INTEGER *v63; // rax
  struct _KERB_INTERNAL_NAME *v64; // rbx
  _SECURITY_IMPERSONATION_LEVEL v65; // ebx
  PCUNICODE_STRING v66; // rdi
  WCHAR *v67; // rax
  size_t Length; // r8
  PWSTR Buffer; // rdx
  struct _UNICODE_STRING *v70; // rdi
  void *v71; // rax
  size_t v72; // r8
  PWSTR v73; // rdx
  UNICODE_STRING *v74; // r12
  int v75; // eax
  struct KERB_ENCRYPTED_TICKET *v76; // rsi
  struct PKERB_AUTHORIZATION_DATA_s *v77; // rcx
  int v78; // eax
  void *v79; // rcx
  int v80; // eax
  __int64 v81; // rdx
  __int64 v82; // rax
  char *v83; // rax
  int v84; // eax
  __int64 v85; // rbx
  int v86; // eax
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v87; // rcx
  int v88; // eax
  struct PKERB_AUTHORIZATION_DATA_s *v89; // rcx
  unsigned int v90; // edx
  struct PKERB_AUTHORIZATION_DATA_s *v91; // rcx
  enum _SECURITY_IMPERSONATION_LEVEL v92; // edx
  int v93; // eax
  DWORD LastError; // eax
  PSID *v95; // rbx
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengthb; // [rsp+20h] [rbp-E0h]
  struct _SAM_CLAIMS_BLOB *v100; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v101; // [rsp+70h] [rbp-90h]
  unsigned __int8 v102; // [rsp+72h] [rbp-8Eh]
  unsigned __int8 v103; // [rsp+73h] [rbp-8Dh] BYREF
  char v104; // [rsp+74h] [rbp-8Ch]
  ULONG TokenInformationLength; // [rsp+78h] [rbp-88h] BYREF
  ULONG v106[2]; // [rsp+80h] [rbp-80h] BYREF
  LUID LocallyUniqueId; // [rsp+88h] [rbp-78h] BYREF
  HANDLE v108; // [rsp+90h] [rbp-70h]
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v109; // [rsp+98h] [rbp-68h] BYREF
  struct _PACTYPE *v110; // [rsp+A0h] [rbp-60h] BYREF
  int v111; // [rsp+A8h] [rbp-58h] BYREF
  ULONG v112; // [rsp+ACh] [rbp-54h] BYREF
  PCUNICODE_STRING v113; // [rsp+B0h] [rbp-50h]
  HANDLE Handle; // [rsp+B8h] [rbp-48h] BYREF
  PSID *v115; // [rsp+C0h] [rbp-40h]
  struct KERB_ENCRYPTED_TICKET *v116; // [rsp+C8h] [rbp-38h]
  PCUNICODE_STRING String1; // [rsp+D0h] [rbp-30h]
  struct PKERB_AUTHORIZATION_DATA_s *v118; // [rsp+D8h] [rbp-28h] BYREF
  struct PKERB_AUTHORIZATION_DATA_s **v119; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v120; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v121; // [rsp+F0h] [rbp-10h]
  struct _KERB_CREDENTIAL *v122; // [rsp+F8h] [rbp-8h] BYREF
  struct _LSA_TOKEN_INFORMATION_V3 *v123; // [rsp+100h] [rbp+0h] BYREF
  struct KERB_AP_REQUEST *v124; // [rsp+108h] [rbp+8h]
  LUID *v125; // [rsp+110h] [rbp+10h]
  struct _KERB_TICKET_CACHE_ENTRY *v126; // [rsp+118h] [rbp+18h]
  union _LARGE_INTEGER *v127; // [rsp+120h] [rbp+20h]
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v128; // [rsp+128h] [rbp+28h] BYREF
  struct _LUID v129; // [rsp+130h] [rbp+30h] BYREF
  struct _UNICODE_STRING *v130; // [rsp+138h] [rbp+38h] BYREF
  struct _UNICODE_STRING *v131; // [rsp+140h] [rbp+40h]
  struct _PAC_INFO_BUFFER *v132; // [rsp+148h] [rbp+48h]
  struct _KERB_ENCRYPTION_KEY *v133; // [rsp+150h] [rbp+50h]
  __int64 v134; // [rsp+158h] [rbp+58h] BYREF
  HANDLE TokenHandle; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v136[2]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v137; // [rsp+178h] [rbp+78h]
  struct _LUID v138; // [rsp+180h] [rbp+80h] BYREF
  HANDLE *v139; // [rsp+188h] [rbp+88h]
  __int128 v140; // [rsp+190h] [rbp+90h] BYREF
  __int128 v141; // [rsp+1A0h] [rbp+A0h] BYREF
  int v142; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v143[3]; // [rsp+1B8h] [rbp+B8h]
  char v144[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  struct _UNICODE_STRING v145; // [rsp+1D8h] [rbp+D8h] BYREF
  _WORD v146[4]; // [rsp+1E8h] [rbp+E8h] BYREF
  void *v147; // [rsp+1F0h] [rbp+F0h]
  __int64 v148; // [rsp+218h] [rbp+118h]
  char v149[24]; // [rsp+238h] [rbp+138h] BYREF
  __int64 v150; // [rsp+250h] [rbp+150h]
  __int64 v151; // [rsp+2A0h] [rbp+1A0h]
  int v152; // [rsp+2A8h] [rbp+1A8h]
  __int128 v153; // [rsp+2B0h] [rbp+1B0h] BYREF
  _SECURITY_IMPERSONATION_LEVEL v154[4]; // [rsp+2C0h] [rbp+1C0h]
  __int128 v155; // [rsp+2D0h] [rbp+1D0h]
  __int64 v156; // [rsp+2E0h] [rbp+1E0h]
  PSID TokenInformation[12]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v20 = *a3;
  v113 = a17;
  v121 = a6;
  v131 = a18;
  String1 = a16;
  v130 = a10;
  v133 = a11;
  v125 = a13;
  TokenInformationLength = a1;
  v139 = a15;
  v112 = a2;
  v110 = 0;
  v120 = 0;
  v118 = 0;
  v134 = 0;
  v119 = 0;
  v132 = 0;
  v109 = 0;
  v128 = 0;
  v123 = 0;
  v106[0] = 0;
  v103 = 0;
  v129 = 0;
  v136[0] = 0;
  v136[1] = 0;
  v101 = 0;
  v102 = 0;
  v111 = 0;
  Handle = 0;
  v104 = 0;
  v108 = 0;
  TokenHandle = 0;
  v122 = 0;
  v126 = 0;
  v137 = a19;
  v124 = a4;
  v116 = (struct KERB_ENCRYPTED_TICKET *)a5;
  v151 = (__int64)a20;
  v115 = a14;
  v138 = (struct _LUID)v20;
  v140 = 0;
  v141 = 0;
  memset_0(v144, 0, 0xC8u);
  *a14 = 0;
  LocallyUniqueId = 0;
  *a13 = 0;
  if ( a20 )
    *a20 = KerbGlobalWillNeverTime;
  if ( !a5 )
  {
    v49 = v108;
    v54 = v115;
    goto LABEL_103;
  }
  v127 = 0;
  if ( (unsigned int)KerbConvertPrincipalNameToString(String1, v106, a5 + 56)
    || (v23 = KerbConvertRealmToUnicodeString(v113, a5 + 48), v21 = 0, v23) )
  {
    AuthDataFromMultipleIfReleventContainers = -1073741670;
    goto LABEL_27;
  }
  AuthDataFromMultipleIfReleventContainers = 0;
  if ( (*(_BYTE *)a5 & 0x10) == 0 || (v24 = *(struct PKERB_AUTHORIZATION_DATA_s **)(a5 + 160)) == 0 )
  {
    v35 = 0;
LABEL_47:
    v30 = TokenInformationLength;
    v33 = 0;
    v34 = v110;
LABEL_48:
    if ( v34 )
    {
      v36 = (UNICODE_STRING *)v113;
      ShouldLogonSessionEnforceSidFiltering = 1;
    }
    else
    {
      *(_QWORD *)v106 = 0;
      if ( (unsigned int)KerbConvertPrincipalNameToKdcName(
                           (struct _KERB_INTERNAL_NAME **)v106,
                           (struct KERB_PRINCIPAL_NAME *)(a5 + 56)) )
      {
LABEL_50:
        AuthDataFromMultipleIfReleventContainers = -1073741670;
        goto LABEL_23;
      }
      v36 = (UNICODE_STRING *)v113;
      v37 = KerbCreatePacForKerbClient(&v110, *(struct _KERB_INTERNAL_NAME **)v106, (struct _UNICODE_STRING *)v113, 0);
      KerbFreeKdcName((struct _KERB_INTERNAL_NAME **)v106);
      if ( v37 >= 0 )
      {
        v104 = 1;
        KerbFreeString(v36);
        RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
        AuthDataFromMultipleIfReleventContainers = KerbDuplicateStringEx(v36, &KerbGlobalMachineName, v41);
        RtlReleaseResource(&KerberosGlobalResource);
        if ( AuthDataFromMultipleIfReleventContainers < 0 )
          goto LABEL_23;
        v42 = PAC_Find(v110, 1, 0);
        v132 = v42;
        if ( !v42 )
        {
          KerbTracerT::Log(1, "KerbCreateTokenFromTicketEx", 2535, "Failed to find logon info!");
          AuthDataFromMultipleIfReleventContainers = -1073741811;
          goto LABEL_23;
        }
        v44 = PAC_UnmarshallAndConvertValidationInfo(
                &v109,
                0,
                v43,
                *((unsigned __int8 **)v42 + 1),
                *((_DWORD *)v42 + 1));
        AuthDataFromMultipleIfReleventContainers = v44;
        if ( v44 < 0 )
        {
          LODWORD(ReturnLength) = v44;
          v38 = "Failed to unmarshall validation info: 0x%x";
          v39 = 2553;
LABEL_57:
          KerbTracerT::Log(1, "KerbCreateTokenFromTicketEx", v39, v38, ReturnLength);
          goto LABEL_23;
        }
        ShouldLogonSessionEnforceSidFiltering = 0;
      }
      else
      {
        if ( v37 != -1073741724 && v37 != -1073741727 )
        {
          v38 = "Failed to create local pac for client : 0x%x\n";
          v39 = 2495;
          if ( AuthDataFromMultipleIfReleventContainers >= 0 )
            AuthDataFromMultipleIfReleventContainers = v37;
          LODWORD(ReturnLength) = AuthDataFromMultipleIfReleventContainers;
          goto LABEL_57;
        }
        KerbTracerT::Log(3, "KerbCreateTokenFromTicketEx", 2485, "Failed to create local pac for client : 0x%x\n", v37);
        v33 = 1;
        ShouldLogonSessionEnforceSidFiltering = 0;
      }
    }
    *(_QWORD *)v106 = 0;
    IsEnabled = Ntlmless::Kerberos::IsEnabled(v34);
    if ( ShouldLogonSessionEnforceSidFiltering )
    {
      if ( IsEnabled )
      {
        ShouldLogonSessionEnforceSidFiltering = KerbShouldLogonSessionEnforceSidFiltering(v20, v30);
      }
      else if ( KerbGlobalKerbKdcCallInfo )
      {
        v130 = v20;
        KerbLocateLogonSessionUnique(&v120, &v130);
        ShouldLogonSessionEnforceSidFiltering = 1;
        if ( v120 )
          ShouldLogonSessionEnforceSidFiltering = *(_BYTE *)(v120 + 936);
        wil::details::unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>(&v120);
      }
    }
    if ( v33 )
    {
      v49 = v108;
      v54 = v115;
      goto LABEL_100;
    }
    v47 = String1;
    if ( RtlEqualUnicodeString(String1, &KerbGlobalMachineServiceName, 1u) && KerbIsThisOurDomain(v36) )
    {
      DoesSKeyExist = KerbDoesSKeyExist(v133, &v103, &v129, &TokenHandle);
      v49 = 0;
      AuthDataFromMultipleIfReleventContainers = DoesSKeyExist;
      if ( DoesSKeyExist < 0 )
      {
        LODWORD(ReturnLength) = DoesSKeyExist;
        KerbTracerT::Log(1, "KerbCreateTokenFromTicketEx", 2602, "Failed to detect local loopback: 0x%x", ReturnLength);
        goto LABEL_23;
      }
      if ( v103 )
      {
        KerbSqmLoopbackIncrement();
        if ( v129.LowPart == 999 && !v129.HighPart )
        {
          v101 = 1;
          KerbTracerT::Log(
            23,
            "KerbCreateTokenFromTicketEx",
            2625,
            "KerbCreateTokenFromTicket, KerbDoesSKeyExist Status %#x, IsLocalSystem? %s\n",
            AuthDataFromMultipleIfReleventContainers,
            "true");
LABEL_91:
          TokenInformationV3 = KerbMakeTokenInformationV3(
                                 ShouldLogonSessionEnforceSidFiltering,
                                 v109,
                                 v101,
                                 v102,
                                 v35,
                                 (struct _SAM_CLAIMS_BLOB *)&v140,
                                 v128,
                                 (struct _SAM_CLAIMS_BLOB *)&v141,
                                 &v123);
          AuthDataFromMultipleIfReleventContainers = TokenInformationV3;
          if ( TokenInformationV3 < 0 )
          {
            LODWORD(ReturnLengtha) = TokenInformationV3;
            KerbTracerT::Log(
              1,
              "KerbCreateTokenFromTicketEx",
              2673,
              "Failed to make token information v3: 0x%x",
              ReturnLengtha);
            goto LABEL_23;
          }
          v54 = v115;
          *(_QWORD *)v106 = v123;
          AuthDataFromMultipleIfReleventContainers = KerbDuplicateSid(v115);
          if ( AuthDataFromMultipleIfReleventContainers < 0 )
            goto LABEL_23;
LABEL_94:
          v57 = v151;
          v58 = v109;
          if ( v151 )
          {
            *(_DWORD *)v151 = *((_DWORD *)v109 + 2);
            *(_DWORD *)(v57 + 4) = *((_DWORD *)v58 + 3);
          }
          AuthDataFromMultipleIfReleventContainers = KerbDuplicateStringEx(
                                                       &v145,
                                                       (const struct _UNICODE_STRING *)v58 + 3,
                                                       v55);
          if ( AuthDataFromMultipleIfReleventContainers < 0 )
            goto LABEL_23;
          KerbTracerT::Log(12, "KerbCreateTokenFromTicketEx", 2749, "CreateToken : ClientName - %wZ\n", v47);
          v59 = v131;
          AuthDataFromMultipleIfReleventContainers = KerbDuplicateStringEx(
                                                       v131,
                                                       (const struct _UNICODE_STRING *)v109 + 13,
                                                       v60);
          if ( AuthDataFromMultipleIfReleventContainers < 0 )
            goto LABEL_23;
          KerbTracerT::Log(12, "KerbCreateTokenFromTicketEx", 2761, "CreateToken : ClientSamDomain - %wZ\n", v59);
LABEL_100:
          if ( !v33 )
          {
            v61 = *(struct _KERB_INTERNAL_NAME **)v106;
            v62 = 3;
LABEL_106:
            if ( (a7 & 0x20000) != 0 )
            {
              v65 = SecurityIdentification;
            }
            else
            {
              v65 = SecurityImpersonation;
              if ( (a7 & 1) != 0 )
                v65 = SecurityDelegation;
            }
            v66 = String1;
            if ( String1->Length && String1->Buffer && !v145.Buffer )
            {
              v67 = (WCHAR *)MIDL_user_allocate(String1->Length);
              v145.Buffer = v67;
              if ( !v67 )
                goto LABEL_87;
              Length = v66->Length;
              Buffer = v66->Buffer;
              v145.MaximumLength = Length;
              v145.Length = Length;
              memcpy_0(v67, Buffer, Length);
            }
            v70 = v131;
            if ( !v131->Length || !v131->Buffer )
            {
              v74 = (UNICODE_STRING *)v113;
              v75 = KerbDuplicateStringEx(v131, v113, v46);
              v21 = 0;
              AuthDataFromMultipleIfReleventContainers = v75;
              if ( v75 < 0 )
                goto LABEL_23;
LABEL_120:
              v76 = v116;
              if ( v112 )
              {
                if ( !v102 && !v101 )
                {
                  if ( v116 )
                  {
                    if ( (*(_BYTE *)v116 & 0x10) != 0 )
                    {
                      v77 = (struct PKERB_AUTHORIZATION_DATA_s *)*((_QWORD *)v116 + 20);
                      if ( v77 )
                      {
                        v106[0] = 0;
                        if ( v121 && (*(_BYTE *)v121 & 0x10) != 0 )
                          v21 = *(struct KERB_AP_REQUEST **)(v121 + 120);
                        v78 = KerbProcessLoopback(v77, v21, (int *)v106, &v122);
                        v21 = 0;
                        AuthDataFromMultipleIfReleventContainers = v78;
                        if ( v78 < 0 )
                          goto LABEL_23;
                        if ( v122 )
                        {
                          v79 = (void *)*((_QWORD *)v122 + 13);
                          if ( v79 )
                          {
                            v112 = 84;
                            AuthDataFromMultipleIfReleventContainers = NtQueryInformationToken(
                                                                         v79,
                                                                         TokenUser,
                                                                         TokenInformation,
                                                                         0x54u,
                                                                         &v112);
                            if ( AuthDataFromMultipleIfReleventContainers < 0 )
                              goto LABEL_23;
                            if ( RtlEqualSid(*v115, TokenInformation[0]) )
                              v49 = (HANDLE)*((_QWORD *)v122 + 13);
                          }
                        }
                        else if ( v106[0] )
                        {
                          AuthDataFromMultipleIfReleventContainers = 280;
                          goto LABEL_23;
                        }
                      }
                    }
                  }
                }
              }
              if ( v49 )
              {
                v156 = 0;
                v106[0] = 0;
                v153 = 0;
                *(_OWORD *)v154 = 0;
                v155 = 0;
                KerbTracerT::Log(
                  2,
                  "KerbCreateTokenFromTicketEx",
                  3132,
                  "KerbCreateTokenFromTicket LOOPBACK using client token\n");
                AuthDataFromMultipleIfReleventContainers = NtQueryInformationToken(
                                                             v49,
                                                             TokenStatistics,
                                                             &v153,
                                                             0x38u,
                                                             v106);
                if ( AuthDataFromMultipleIfReleventContainers < 0 )
                  goto LABEL_23;
                v92 = SecurityImpersonation;
                if ( v154[3] < v65 )
                  v65 = v154[3];
                *v125 = *(LUID *)((char *)&v153 + 8);
                if ( v65 < SecurityImpersonation )
                  v92 = v65;
                v93 = KerbDuplicateToken(v49, v92, &Handle);
                AuthDataFromMultipleIfReleventContainers = v93;
                if ( v93 < 0 )
                {
                  LODWORD(ReturnLengthb) = v93;
                  KerbTracerT::Log(
                    1,
                    "KerbCreateTokenFromTicketEx",
                    3171,
                    "KerbCreateTokenFromTicket could not duplicate client token %#x\n",
                    ReturnLengthb);
                  goto LABEL_23;
                }
                if ( !(unsigned int)KerbEnableAllPrivilegesToken(Handle) )
                {
                  LastError = GetLastError();
                  KerbTracerT::Log(
                    2,
                    "KerbCreateTokenFromTicketEx",
                    3185,
                    "KerbCreateTokenFromTicket could not enable all prilileges %#x\n",
                    LastError);
                }
              }
              else
              {
                NtAllocateLocallyUniqueId(&LocallyUniqueId);
                v80 = ((__int64 (__fastcall *)(LUID *))LsaFunctions->CreateLogonSession)(&LocallyUniqueId);
                AuthDataFromMultipleIfReleventContainers = v80;
                if ( v80 < 0 )
                {
                  LODWORD(ReturnLength) = v80;
                  KerbTracerT::Log(
                    1,
                    "KerbCreateTokenFromTicketEx",
                    2942,
                    "Failed to create logon session: 0x%x",
                    ReturnLength);
                  goto LABEL_23;
                }
                v81 = 0;
                if ( v109 )
                {
                  v142 = 3;
                  v143[0] = (char *)v109 + 64;
                  v81 = 1;
                }
                if ( v74->Length && v74->Buffer )
                {
                  v82 = 2LL * (unsigned int)v81;
                  v81 = (unsigned int)(v81 + 1);
                  LODWORD(v143[v82]) = 12;
                  v143[v82] = v74;
                }
                LsaIAddNamesToLogonSession(&LocallyUniqueId, v81, &v142);
                KerbTracerT::Log(
                  3,
                  "KerbCreateTokenFromTicketEx",
                  2968,
                  "KerbCreateTokenFromTicket for %wZ\\%wZ, %wZ\n",
                  v146,
                  &v145,
                  v149);
                if ( v109 )
                  v83 = (char *)v109 + 96;
                else
                  v83 = 0;
                v84 = ((__int64 (__fastcall *)(LUID *, struct _TOKEN_SOURCE *, __int64, _QWORD, int, struct _KERB_INTERNAL_NAME *, _QWORD, _QWORD *, char *, char *, _DWORD, HANDLE *, int *))LsaFunctions->CreateTokenEx)(
                        &LocallyUniqueId,
                        &KerberosSource,
                        3,
                        (unsigned int)v65,
                        v62,
                        v61,
                        0,
                        v136,
                        v83,
                        v144,
                        0,
                        &Handle,
                        &v111);
                AuthDataFromMultipleIfReleventContainers = v84;
                v123 = 0;
                v127 = 0;
                if ( v84 < 0 )
                {
                  LODWORD(ReturnLength) = v84;
                  v38 = "Failed to create token: 0x%x";
                  v39 = 2996;
                  goto LABEL_57;
                }
                if ( v111 < 0 )
                {
                  KerbTracerT::Log(
                    1,
                    "KerbCreateTokenFromTicketEx",
                    3002,
                    "Failed to create token, substatus = 0x%x",
                    v111);
                  AuthDataFromMultipleIfReleventContainers = v111;
                  goto LABEL_23;
                }
                if ( (a7 & 1) != 0 )
                {
                  v85 = v121;
                  v86 = KerbCreateDelegationLogonSession(
                          &LocallyUniqueId,
                          v76,
                          *(struct _KERB_GSS_CHECKSUM **)(v121 + 48));
                  AuthDataFromMultipleIfReleventContainers = v86;
                  if ( v86 < 0 )
                  {
                    LODWORD(ReturnLength) = v86;
                    v38 = "Failed to create delgation logon session: 0x%x";
                    v39 = 3029;
                    goto LABEL_57;
                  }
                }
                else
                {
                  v21 = v124;
                  if ( v124 )
                  {
                    v87 = v109;
                    if ( v132 )
                      v87 = 0;
                    v88 = KerbCreateLogonSessionFromTicket(
                            &LocallyUniqueId,
                            &v138,
                            (struct _UNICODE_STRING *)String1,
                            v74,
                            v124,
                            v76,
                            v87);
                    AuthDataFromMultipleIfReleventContainers = v88;
                    if ( v88 < 0 )
                    {
                      LODWORD(ReturnLength) = v88;
                      v38 = "Failed to create ASC logon session %x";
                      v39 = 3047;
                      goto LABEL_57;
                    }
                  }
                  v85 = v121;
                }
                if ( v76 )
                {
                  if ( (*(_BYTE *)v76 & 0x10) != 0 )
                  {
                    v89 = (struct PKERB_AUTHORIZATION_DATA_s *)*((_QWORD *)v76 + 20);
                    if ( v89 )
                    {
                      AuthDataFromMultipleIfReleventContainers = KerbFindAuthDataFromMultipleIfReleventContainers(
                                                                   v89,
                                                                   (unsigned int)v21,
                                                                   &v119,
                                                                   &v118);
                      if ( AuthDataFromMultipleIfReleventContainers < 0 )
                        goto LABEL_23;
                      v21 = v118;
                      if ( v118 )
                        goto LABEL_173;
                    }
                  }
                }
                if ( v85 && (*(_BYTE *)v85 & 0x10) != 0 && *(_QWORD *)(v85 + 120) )
                {
                  v90 = (unsigned int)v119;
                  if ( v119 )
                  {
                    KerbFreeData(1);
                    v119 = 0;
                  }
                  v91 = *(struct PKERB_AUTHORIZATION_DATA_s **)(v85 + 120);
                  v118 = 0;
                  AuthDataFromMultipleIfReleventContainers = KerbFindAuthDataFromMultipleIfReleventContainers(
                                                               v91,
                                                               v90,
                                                               &v119,
                                                               &v118);
                  if ( AuthDataFromMultipleIfReleventContainers < 0 )
                    goto LABEL_23;
                  v21 = v118;
                  if ( v118 )
                  {
LABEL_173:
                    AuthDataFromMultipleIfReleventContainers = KerbApplyAuthDataRestrictions(&Handle, v21, 0);
                    if ( AuthDataFromMultipleIfReleventContainers < 0 )
                      goto LABEL_23;
                  }
                }
                *v125 = LocallyUniqueId;
              }
              *v139 = Handle;
              goto LABEL_23;
            }
            v71 = MIDL_user_allocate(v131->Length);
            v147 = v71;
            if ( v71 )
            {
              v72 = v70->Length;
              v73 = v70->Buffer;
              v146[1] = v72;
              v146[0] = v72;
              memcpy_0(v71, v73, v72);
              v74 = (UNICODE_STRING *)v113;
              v21 = 0;
              goto LABEL_120;
            }
LABEL_87:
            AuthDataFromMultipleIfReleventContainers = -1073741670;
            goto LABEL_23;
          }
LABEL_103:
          v62 = 0;
          v151 = 0x500000000000101LL;
          v152 = 7;
          v63 = (union _LARGE_INTEGER *)MIDL_user_allocate(0x10u);
          v127 = v63;
          v64 = (struct _KERB_INTERNAL_NAME *)v63;
          if ( !v63 )
            goto LABEL_50;
          v63[1].QuadPart = 0;
          *v63 = KerbGlobalWillNeverTime;
          AuthDataFromMultipleIfReleventContainers = KerbDuplicateSid(v54);
          if ( AuthDataFromMultipleIfReleventContainers < 0 )
            goto LABEL_23;
          v61 = v64;
          goto LABEL_106;
        }
        KerbTracerT::Log(
          23,
          "KerbCreateTokenFromTicketEx",
          2634,
          "KerbCreateTokenFromTicket, KerbDoesSKeyExist Status %#x, IsLocalSystem? %s\n",
          AuthDataFromMultipleIfReleventContainers,
          "false");
        v102 = 1;
      }
      v50 = (unsigned __int64)TokenHandle;
      v101 = 0;
      v108 = TokenHandle;
      if ( TokenHandle )
      {
        v51 = (void *)(v50 & -(__int64)IsTokenRestricted(TokenHandle));
        v52 = v51;
        v108 = v51;
        if ( v51 )
        {
          TokenInformationLength = 0;
          AuthDataFromMultipleIfReleventContainers = NtQueryInformationToken(
                                                       v51,
                                                       TokenUser,
                                                       0,
                                                       0,
                                                       &TokenInformationLength);
          if ( AuthDataFromMultipleIfReleventContainers != -1073741789 )
            goto LABEL_23;
          v53 = MIDL_user_allocate(TokenInformationLength);
          v54 = v115;
          *v115 = v53;
          if ( !v53 )
            goto LABEL_87;
          AuthDataFromMultipleIfReleventContainers = NtQueryInformationToken(
                                                       v52,
                                                       TokenUser,
                                                       v53,
                                                       TokenInformationLength,
                                                       &TokenInformationLength);
          if ( AuthDataFromMultipleIfReleventContainers < 0 )
            goto LABEL_23;
          v49 = v108;
          goto LABEL_94;
        }
      }
    }
    v49 = v108;
    goto LABEL_91;
  }
  if ( !KerbVerifyAuthData(v24) )
  {
    AuthDataFromMultipleIfReleventContainers = -1073741715;
    goto LABEL_27;
  }
  PacFromAuthData = KerbGetPacFromAuthData(*(_QWORD *)(a5 + 160), &v134, v25, &v120);
  if ( PacFromAuthData )
  {
    AuthDataFromMultipleIfReleventContainers = KerbMapKerbError(PacFromAuthData);
    goto LABEL_27;
  }
  v27 = v120;
  if ( !v120 )
  {
    v35 = 0;
    goto LABEL_47;
  }
  v28 = *(struct _PACTYPE **)(v120 + 24);
  v29 = *(_DWORD *)(v120 + 16);
  v110 = v28;
  if ( !(unsigned int)PAC_UnMarshal((unsigned __int64)v28, v29) )
  {
    KerbTracerT::Log(1, "KerbCreateTokenFromTicketEx", 2385, "Failed to unmarshal pac");
    AuthDataFromMultipleIfReleventContainers = -1073741811;
    goto LABEL_27;
  }
  if ( v124 && (KerbConvertFlagsToUlong((struct KERB_AP_REQUEST *)((char *)v124 + 8)) & 0x40000000) != 0 )
  {
    RtlAcquireResourceShared(&KerbContextResource, 1u);
    v126 = *(struct _KERB_TICKET_CACHE_ENTRY **)(a12 + 272);
    _InterlockedIncrement((volatile signed __int32 *)v126 + 4);
    RtlReleaseResource(&KerbContextResource);
  }
  v30 = 2;
  if ( (a7 & 0x20000) == 0 )
    v30 = TokenInformationLength;
  v31 = KerbVerifyPacSignature(
          a9,
          v130,
          v28,
          *(unsigned int *)(v27 + 16),
          a8,
          (__int64)v116,
          v30,
          (struct KERB_TICKET *)(((unsigned __int64)v124 + 24) & -(__int64)(v124 != 0)),
          (struct KERB_TICKET *)(((unsigned __int64)v126 + 272) & -(__int64)(v126 != 0)),
          (__int64)&v109,
          (__int64)&v140,
          (__int64)&v128,
          (__int64)&v141,
          v137);
  AuthDataFromMultipleIfReleventContainers = v31;
  if ( v31 >= 0 )
  {
    v33 = 0;
    v35 = PAC_Find(v110, 2, 0) != 0;
    goto LABEL_48;
  }
  KerbReportPACError((struct _UNICODE_STRING *)String1, (struct _UNICODE_STRING *)v113, v31);
  LODWORD(v100) = AuthDataFromMultipleIfReleventContainers;
  KerbTracerT::Log(
    1,
    "KerbCreateTokenFromTicketEx",
    2434,
    "Pac signature did not verify: domain %wZ, status %x\n",
    a9,
    v100);
LABEL_23:
  if ( v126 )
    KerbDereferenceTicketCacheEntry(v126);
  if ( v122 )
    KerbDereferenceCredential(v122);
LABEL_27:
  if ( v145.Buffer )
    KerbFree(v145.Buffer);
  if ( v147 )
    KerbFree(v147);
  v32 = v150;
  if ( v150 )
  {
    KerbFree(v150);
    v32 = v150;
  }
  if ( v148 )
  {
    KerbFree(v148);
    v32 = v150;
  }
  if ( v32 )
    KerbFree(v32);
  if ( v123 )
    KerbFree(v123);
  if ( v127 )
    KerbFree(v127);
  if ( AuthDataFromMultipleIfReleventContainers < 0 )
  {
    if ( Handle )
    {
      NtClose(Handle);
    }
    else if ( (LocallyUniqueId.LowPart || LocallyUniqueId.HighPart)
           && (LocallyUniqueId.LowPart != 999 || LocallyUniqueId.HighPart) )
    {
      ((void (__fastcall *)(LUID *, struct KERB_AP_REQUEST *))LsaFunctions->DeleteLogonSession)(&LocallyUniqueId, v21);
    }
    v95 = v115;
    if ( *v115 )
    {
      KerbFree(*v115);
      *v95 = 0;
    }
  }
  if ( v103 )
    KerbDeleteSKeyEntry(v133);
  if ( v104 && v110 )
    KerbFree(v110);
  if ( v109 )
    KerbFree(v109);
  if ( v128 )
    KerbFree(v128);
  if ( *((_QWORD *)&v140 + 1) )
    KerbFree(*((_QWORD *)&v140 + 1));
  if ( *((_QWORD *)&v141 + 1) )
    KerbFree(*((_QWORD *)&v141 + 1));
  if ( v134 )
    KerbFreeData(1);
  if ( v119 )
    KerbFreeData(1);
  return (unsigned int)AuthDataFromMultipleIfReleventContainers;
}

```

## disassembly

```asm
0x180082ef4  mov     [rsp-8+arg_8], rbx
0x180082ef9  push    rbp
0x180082efa  push    rsi
0x180082efb  push    rdi
0x180082efc  push    r12
0x180082efe  push    r13
0x180082f00  push    r14
0x180082f02  push    r15
0x180082f04  lea     rbp, [rsp-260h]
0x180082f0c  sub     rsp, 360h
0x180082f13  mov     rax, cs:__security_cookie
0x180082f1a  xor     rax, rsp
0x180082f1d  mov     [rbp+290h+var_40], rax
0x180082f24  mov     rbx, [r8]
0x180082f27  xorps   xmm0, xmm0
0x180082f2a  mov     rax, [rbp+290h+arg_80]
0x180082f31  xorps   xmm1, xmm1
0x180082f34  mov     rsi, [rbp+290h+arg_20]
0x180082f3b  mov     r8d, 0C8h; Size
0x180082f41  mov     rdi, [rbp+290h+arg_98]
0x180082f48  mov     r15, [rbp+290h+arg_68]
0x180082f4f  mov     r12, [rbp+290h+arg_38]
0x180082f56  mov     r14, [rbp+290h+arg_40]
0x180082f5d  mov     r13, [rbp+290h+arg_58]
0x180082f64  mov     [rbp+290h+var_2E0], rax
0x180082f68  mov     rax, [rbp+290h+arg_28]
0x180082f6f  mov     [rbp+290h+var_2A0], rax
0x180082f73  mov     rax, [rbp+290h+arg_88]
0x180082f7a  mov     [rbp+290h+var_250], rax
0x180082f7e  mov     rax, [rbp+290h+arg_78]
0x180082f85  mov     [rbp+290h+String1], rax
0x180082f89  mov     rax, [rbp+290h+arg_48]
0x180082f90  mov     [rbp+290h+var_258], rax
0x180082f94  mov     rax, [rbp+290h+arg_50]
0x180082f9b  mov     [rbp+290h+var_240], rax
0x180082f9f  mov     rax, [rbp+290h+arg_60]
0x180082fa6  mov     [rbp+290h+var_280], rax
0x180082faa  mov     rax, [rbp+290h+arg_70]
0x180082fb1  mov     [rsp+390h+TokenInformationLength], ecx
0x180082fb5  xor     ecx, ecx
0x180082fb7  mov     [rbp+290h+var_208], rax
0x180082fbe  mov     rax, [rbp+290h+arg_90]
0x180082fc5  mov     [rbp+290h+var_2E4], edx
0x180082fc8  xor     edx, edx; Val
0x180082fca  mov     [rbp+290h+var_2F0], rcx
0x180082fce  mov     [rbp+290h+var_2A8], rcx
0x180082fd2  mov     [rbp+290h+var_2B8], rcx
0x180082fd6  mov     [rbp+290h+var_238], rcx
0x180082fda  mov     [rbp+290h+var_2B0], rcx
0x180082fde  mov     [rbp+290h+var_248], rcx
0x180082fe2  mov     [rbp+290h+var_2F8], rcx
0x180082fe6  mov     [rbp+290h+var_268], rcx
0x180082fea  mov     [rbp+290h+var_290], rcx
0x180082fee  mov     [rbp+290h+var_310], ecx
0x180082ff1  mov     [rsp+390h+var_31D], cl
0x180082ff5  mov     qword ptr [rbp+290h+var_260.LowPart], rcx
0x180082ff9  mov     [rbp+290h+var_228], rcx
0x180082ffd  mov     [rbp+290h+var_220], rcx
0x180083001  mov     [rsp+390h+var_320], cl
0x180083005  mov     [rsp+390h+var_31E], cl
0x180083009  mov     [rbp+290h+var_2E8], ecx
0x18008300c  mov     [rbp+290h+Handle], rcx
0x180083010  mov     [rsp+390h+var_31C], cl
0x180083014  mov     [rbp+290h+var_300], rcx
0x180083018  mov     [rbp+290h+TokenHandle], rcx
0x18008301c  mov     [rbp+290h+var_298], rcx
0x180083020  mov     [rbp+290h+var_278], rcx
0x180083024  lea     rcx, [rbp+290h+var_1C0]; void *
0x18008302b  mov     [rbp+290h+var_218], rax
0x18008302f  mov     [rbp+290h+var_288], r9
0x180083033  mov     [rbp+290h+var_2C8], rsi
0x180083037  mov     [rbp+290h+var_F0], rdi
0x18008303e  mov     [rbp+290h+var_2D0], r15
0x180083042  mov     qword ptr [rbp+290h+var_210.LowPart], rbx
0x180083049  movups  [rbp+290h+var_200], xmm0
0x180083050  movups  [rbp+290h+var_1F0], xmm1
0x180083057  call    memset_0
0x18008305c  mov     rcx, [rbp+290h+var_280]
0x180083060  xor     edx, edx
0x180083062  mov     [r15], rdx
0x180083065  mov     eax, edx
0x180083067  mov     qword ptr [rbp+290h+LocallyUniqueId.LowPart], rdx
0x18008306b  mov     [rcx], rdx
0x18008306e  test    rdi, rdi
0x180083071  jz      short loc_18008307D
0x180083073  mov     rax, cs:?KerbGlobalWillNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalWillNeverTime
0x18008307a  mov     [rdi], rax
0x18008307d  test    rsi, rsi
0x180083080  jz      loc_180083853
0x180083086  mov     rcx, [rbp+290h+String1]
0x18008308a  lea     r15, [rsi+38h]
0x18008308e  mov     [rbp+290h+var_270], rdx
0x180083092  mov     r8, r15
0x180083095  lea     rdx, [rbp+290h+var_310]
0x180083099  call    KerbConvertPrincipalNameToString
0x18008309e  test    eax, eax
0x1800830a0  jz      short loc_1800830AF
0x1800830a2  mov     edi, 0C000009Ah
0x1800830a7  xor     r14d, r14d
0x1800830aa  jmp     loc_1800832A9
0x1800830af  mov     rcx, [rbp+290h+var_2E0]
0x1800830b3  lea     rdx, [rsi+30h]
0x1800830b7  call    KerbConvertRealmToUnicodeString
0x1800830bc  xor     edx, edx
0x1800830be  test    eax, eax
0x1800830c0  jnz     short loc_1800830A2
0x1800830c2  test    byte ptr [rsi], 10h
0x1800830c5  mov     edi, edx
0x1800830c7  jz      loc_180083369
0x1800830cd  mov     rcx, [rsi+0A0h]; struct PKERB_AUTHORIZATION_DATA_s *
0x1800830d4  test    rcx, rcx
0x1800830d7  jz      loc_180083369
0x1800830dd  call    ?KerbVerifyAuthData@@YAEPEAUPKERB_AUTHORIZATION_DATA_s@@@Z; KerbVerifyAuthData(PKERB_AUTHORIZATION_DATA_s *)
0x1800830e2  test    al, al
0x1800830e4  jnz     short loc_1800830ED
0x1800830e6  mov     edi, 0C000006Dh
0x1800830eb  jmp     short loc_1800830A7
0x1800830ed  mov     rcx, [rsi+0A0h]
0x1800830f4  lea     r9, [rbp+290h+var_2A8]
0x1800830f8  lea     rdx, [rbp+290h+var_238]
0x1800830fc  call    KerbGetPacFromAuthData
0x180083101  xor     ecx, ecx
0x180083103  test    eax, eax
0x180083105  jz      short loc_180083112
0x180083107  mov     ecx, eax; int
0x180083109  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x18008310e  mov     edi, eax
0x180083110  jmp     short loc_1800830A7
0x180083112  mov     rsi, [rbp+290h+var_2A8]
0x180083116  test    rsi, rsi
0x180083119  jz      loc_18008336E
0x18008311f  mov     rdi, [rsi+18h]
0x180083123  mov     edx, [rsi+10h]; unsigned int
0x180083126  mov     rcx, rdi; struct _PACTYPE *
0x180083129  mov     [rbp+290h+var_2F0], rdi
0x18008312d  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x180083132  test    eax, eax
0x180083134  jnz     short loc_18008315C
0x180083136  lea     r9, aFailedToUnmars_2; "Failed to unmarshal pac"
0x18008313d  mov     r8d, 951h
0x180083143  lea     rdx, aKerbcreatetoke_13; "KerbCreateTokenFromTicketEx"
0x18008314a  lea     ecx, [rax+1]
0x18008314d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180083152  mov     edi, 0C000000Dh
0x180083157  jmp     loc_1800830A7
0x18008315c  mov     rax, [rbp+290h+var_288]
0x180083160  test    rax, rax
0x180083163  jz      short loc_18008319F
0x180083165  lea     rcx, [rax+8]; struct tagASN1bitstring_t *
0x180083169  call    ?KerbConvertFlagsToUlong@@YAKPEBUtagASN1bitstring_t@@@Z; KerbConvertFlagsToUlong(tagASN1bitstring_t const *)
0x18008316e  bt      eax, 1Eh
0x180083172  jnb     short loc_18008319F
0x180083174  mov     dl, 1; Wait
0x180083176  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18008317d  call    cs:__imp_RtlAcquireResourceShared
0x180083183  mov     rax, [r13+110h]
0x18008318a  mov     [rbp+290h+var_278], rax
0x18008318e  lock inc dword ptr [rax+10h]
0x180083192  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x180083199  call    cs:__imp_RtlReleaseResource
0x18008319f  test    [rbp+290h+arg_30], 20000h
0x1800831a9  mov     r13d, 2
0x1800831af  mov     rcx, [rbp+290h+var_278]
0x1800831b3  cmovz   r13d, [rsp+390h+TokenInformationLength]
0x1800831b9  mov     rax, rcx
0x1800831bc  mov     rdx, [rbp+290h+var_258]
0x1800831c0  add     rcx, 110h
0x1800831c7  neg     rax
0x1800831ca  sbb     r9, r9
0x1800831cd  and     r9, rcx
0x1800831d0  mov     rcx, [rbp+290h+var_288]
0x1800831d4  mov     rax, rcx
0x1800831d7  add     rcx, 18h
0x1800831db  neg     rax
0x1800831de  mov     rax, [rbp+290h+var_218]
0x1800831e2  mov     [rsp+390h+var_328], rax
0x1800831e7  sbb     r8, r8
0x1800831ea  and     r8, rcx
0x1800831ed  lea     rax, [rbp+290h+var_1F0]
0x1800831f4  mov     [rsp+390h+var_330], rax
0x1800831f9  mov     rcx, r14
0x1800831fc  lea     rax, [rbp+290h+var_268]
0x180083200  mov     [rsp+390h+var_338], rax
0x180083205  lea     rax, [rbp+290h+var_200]
0x18008320c  mov     [rsp+390h+var_340], rax
0x180083211  lea     rax, [rbp+290h+var_2F8]
0x180083215  mov     [rsp+390h+var_348], rax
0x18008321a  mov     rax, [rbp+290h+var_2C8]
0x18008321e  mov     [rsp+390h+var_350], r9
0x180083223  mov     r9d, [rsi+10h]
0x180083227  mov     [rsp+390h+var_358], r8
0x18008322c  mov     r8, rdi
0x18008322f  mov     dword ptr [rsp+390h+var_360], r13d
0x180083234  mov     [rsp+390h+var_368], rax
0x180083239  mov     [rsp+390h+ReturnLength], r12
0x18008323e  call    ?KerbVerifyPacSignature@@YAJPEAU_UNICODE_STRING@@0PEAU_PACTYPE@@KPEAU_KERB_ENCRYPTION_KEY@@PEAUKERB_ENCRYPTED_TICKET@@W4KerbCreateTokenPacTrustLevel@@PEAUKERB_TICKET@@5PEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAM_CLAIMS_BLOB@@67PEAPEAU_S4U_DELEGATION_INFO@@@Z; KerbVerifyPacSignature(_UNICODE_STRING *,_UNICODE_STRING *,_PACTYPE *,ulong,_KERB_ENCRYPTION_KEY *,KERB_ENCRYPTED_TICKET *,KerbCreateTokenPacTrustLevel,KERB_TICKET *,KERB_TICKET *,_NETLOGON_VALIDATION_SAM_INFO4 * *,_SAM_CLAIMS_BLOB *,_NETLOGON_VALIDATION_SAM_INFO4 * *,_SAM_CLAIMS_BLOB *,_S4U_DELEGATION_INFO * *)
0x180083243  mov     edi, eax
0x180083245  test    eax, eax
0x180083247  jns     loc_180083347
0x18008324d  mov     rdx, [rbp+290h+var_2E0]; struct _UNICODE_STRING *
0x180083251  mov     r8d, eax; int
0x180083254  mov     rcx, [rbp+290h+String1]; struct _UNICODE_STRING *
0x180083258  call    ?KerbReportPACError@@YAXPEAU_UNICODE_STRING@@0J@Z; KerbReportPACError(_UNICODE_STRING *,_UNICODE_STRING *,long)
0x18008325d  lea     r9, aPacSignatureDi; "Pac signature did not verify: domain %w"...
0x180083264  mov     dword ptr [rsp+390h+var_368], edi
0x180083268  mov     r8d, 982h
0x18008326e  mov     [rsp+390h+ReturnLength], r14
0x180083273  lea     rdx, aKerbcreatetoke_13; "KerbCreateTokenFromTicketEx"
0x18008327a  mov     ecx, 1
0x18008327f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180083284  xor     r14d, r14d
0x180083287  mov     rax, [rbp+290h+var_278]
0x18008328b  test    rax, rax
0x18008328e  jz      short loc_180083298
0x180083290  mov     rcx, rax; struct _KERB_TICKET_CACHE_ENTRY *
0x180083293  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180083298  mov     rax, [rbp+290h+var_298]
0x18008329c  test    rax, rax
0x18008329f  jz      short loc_1800832A9
0x1800832a1  mov     rcx, rax; struct _KERB_CREDENTIAL *
0x1800832a4  call    ?KerbDereferenceCredential@@YAXPEAU_KERB_CREDENTIAL@@@Z; KerbDereferenceCredential(_KERB_CREDENTIAL *)
0x1800832a9  mov     rcx, [rbp+290h+var_1B8.Buffer]
0x1800832b0  test    rcx, rcx
0x1800832b3  jz      short loc_1800832BA
0x1800832b5  call    KerbFree
0x1800832ba  mov     rcx, [rbp+290h+var_1A0]
0x1800832c1  test    rcx, rcx
0x1800832c4  jz      short loc_1800832CB
0x1800832c6  call    KerbFree
0x1800832cb  mov     rcx, [rbp+290h+var_140]
0x1800832d2  test    rcx, rcx
0x1800832d5  jz      short loc_1800832E3
0x1800832d7  call    KerbFree
0x1800832dc  mov     rcx, [rbp+290h+var_140]
0x1800832e3  mov     rax, [rbp+290h+var_178]
0x1800832ea  test    rax, rax
0x1800832ed  jz      short loc_1800832FE
0x1800832ef  mov     rcx, rax
0x1800832f2  call    KerbFree
0x1800832f7  mov     rcx, [rbp+290h+var_140]
0x1800832fe  test    rcx, rcx
0x180083301  jz      short loc_180083308
0x180083303  call    KerbFree
0x180083308  mov     rcx, [rbp+290h+var_290]
0x18008330c  test    rcx, rcx
0x18008330f  jz      short loc_180083316
0x180083311  call    KerbFree
0x180083316  mov     rax, [rbp+290h+var_270]
0x18008331a  test    rax, rax
0x18008331d  jz      short loc_180083327
0x18008331f  mov     rcx, rax
0x180083322  call    KerbFree
0x180083327  test    edi, edi
0x180083329  jns     loc_180083EBC
0x18008332f  mov     rcx, [rbp+290h+Handle]; Handle
0x180083333  test    rcx, rcx
0x180083336  jz      loc_180083E7A
0x18008333c  call    cs:__imp_NtClose
0x180083342  jmp     loc_180083EA8
0x180083347  mov     rcx, [rbp+290h+var_2F0]; struct _PACTYPE *
0x18008334b  xor     r8d, r8d; struct _PAC_INFO_BUFFER *
0x18008334e  lea     edx, [r8+2]; unsigned int
0x180083352  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x180083357  xor     r14d, r14d
0x18008335a  test    rax, rax
0x18008335d  jz      short loc_180083364
0x18008335f  mov     r12b, 1
0x180083362  jmp     short loc_18008337D
0x180083364  mov     r12b, r14b
0x180083367  jmp     short loc_18008337D
0x180083369  mov     r12b, dl
0x18008336c  jmp     short loc_180083371
0x18008336e  mov     r12b, cl
0x180083371  mov     r13d, [rsp+390h+TokenInformationLength]
0x180083376  xor     r14d, r14d
0x180083379  mov     rcx, [rbp+290h+var_2F0]; this
0x18008337d  test    rcx, rcx
0x180083380  jnz     loc_1800834F0
0x180083386  mov     rdx, r15; struct KERB_PRINCIPAL_NAME *
0x180083389  mov     qword ptr [rbp+290h+var_310], r14
0x18008338d  lea     rcx, [rbp+290h+var_310]; struct _KERB_INTERNAL_NAME **
0x180083391  call    ?KerbConvertPrincipalNameToKdcName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToKdcName(_KERB_INTERNAL_NAME * *,KERB_PRINCIPAL_NAME *)
0x180083396  test    eax, eax
0x180083398  jz      short loc_1800833A4
0x18008339a  mov     edi, 0C000009Ah
0x18008339f  jmp     loc_180083287
0x1800833a4  mov     r15, [rbp+290h+var_2E0]
0x1800833a8  lea     rcx, [rbp+290h+var_2F0]; struct _PACTYPE **
0x1800833ac  mov     rdx, qword ptr [rbp+290h+var_310]; struct _KERB_INTERNAL_NAME *
0x1800833b0  mov     r8, r15; struct _UNICODE_STRING *
0x1800833b3  xor     r9d, r9d; struct _UNICODE_STRING *
0x1800833b6  call    ?KerbCreatePacForKerbClient@@YAJPEAPEAU_PACTYPE@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@2@Z; KerbCreatePacForKerbClient(_PACTYPE * *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_UNICODE_STRING *)
0x1800833bb  lea     rcx, [rbp+290h+var_310]; struct _KERB_INTERNAL_NAME **
0x1800833bf  mov     esi, eax
0x1800833c1  call    ?KerbFreeKdcName@@YAXPEAPEAU_KERB_INTERNAL_NAME@@@Z; KerbFreeKdcName(_KERB_INTERNAL_NAME * *)
0x1800833c6  test    esi, esi
0x1800833c8  jns     short loc_180083435
0x1800833ca  cmp     esi, 0C0000064h
0x1800833d0  jz      short loc_180083406
0x1800833d2  cmp     esi, 0C0000061h
  ... truncated ...
```
