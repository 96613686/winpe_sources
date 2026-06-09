# KerbCreateTokenFromLogonTicket(_KERB_TICKET_CACHE_ENTRY *,_LUID *,_KERB_INTERACTIVE_LOGON *,_KERB_PLAINTEXT_PASSWORD *,uchar,_SECURITY_LOGON_TYPE,_KERB_ENCRYPTION_KEY *,_KERB_MESSAGE_BUFFER *,_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_LUID *,KerbCredIsoApi *,_KERB_LOGON_SESSION *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,ulong *,void * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *,_NETLOGON_VALIDATION_SAM_INFO4 * *,_KERB_TICKET_LOGON_SUPP_CRED *)

- ea: `0x1800819b0`
- end: `0x180082eec`
- name: `?KerbCreateTokenFromLogonTicket@@YAJPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_LUID@@PEAU_KERB_INTERACTIVE_LOGON@@PEAU_KERB_PLAINTEXT_PASSWORD@@EW4_SECURITY_LOGON_TYPE@@PEAU_KERB_ENCRYPTION_KEY@@PEAU_KERB_MESSAGE_BUFFER@@PEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@71PEAVKerbCredIsoApi@@PEAU_KERB_LOGON_SESSION@@PEAW4_LSA_TOKEN_INFORMATION_TYPE@@PEAPEAXPEAKPEAPEAXPEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_KERB_TICKET_LOGON_SUPP_CRED@@@Z`
- size: `5436`
- prototype: `__int64 __fastcall(struct _KERB_TICKET_CACHE_ENTRY *, struct _LUID *, struct _KERB_INTERACTIVE_LOGON *, struct _KERB_PLAINTEXT_PASSWORD *, char, enum _SECURITY_LOGON_TYPE, struct _KERB_ENCRYPTION_KEY *, struct _KERB_MESSAGE_BUFFER *, struct _UNICODE_STRING *, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, struct _LUID *, struct KerbCredIsoApi *, struct _RTL_CRITICAL_SECTION *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, unsigned int *, void **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **, struct _NETLOGON_VALIDATION_SAM_INFO4 **, struct _KERB_TICKET_LOGON_SUPP_CRED *)`
- caller_count: `1`
- callee_count: `45`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180025680`

## callees

- `0x180004660`
- `0x1800068d0`
- `0x180006920`
- `0x1800069a0`
- `0x1800069e0`
- `0x180006ba0`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x18000b5c0`
- `0x180010e90`
- `0x1800113f0`
- `0x180014d4c`
- `0x180015740`
- `0x180016550`
- `0x180020690`
- `0x18002b678`
- `0x18002b740`
- `0x180032964`
- `0x180032bd4`
- `0x180032d08`
- `0x180033de0`
- `0x180034a98`
- `0x180034e3c`
- `0x180035290`
- `0x18003576c`
- `0x180035e80`
- `0x180036994`
- `0x180037a58`
- `0x18003ca2c`
- `0x18003d360`
- `0x18006178c`
- `0x1800643dc`
- `0x180070680`
- `0x1800819b0`
- `0x1800841e4`
- `0x18008b70c`
- `0x180093694`
- `0x1800b72b4`
- `0x1800b8ef4`
- `0x1800be1c8`
- `0x1800be9bc`
- `0x1800bfc00`
- `0x1800dd840`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180081cea`
- `ntdll!RtlEnterCriticalSection` at `0x180081d8a`
- `ntdll!RtlEnterCriticalSection` at `0x180081f74`
- `ntdll!RtlEnterCriticalSection` at `0x180081fb8`
- `ntdll!RtlEnterCriticalSection` at `0x1800820fa`
- `ntdll!RtlEnterCriticalSection` at `0x180082713`
- `ntdll!RtlEnterCriticalSection` at `0x180082744`
- `ntdll!RtlEnterCriticalSection` at `0x180082b05`
- `ntdll!RtlEnterCriticalSection` at `0x180082b46`
- `ntdll!RtlEnterCriticalSection` at `0x180082bdc`
- `ntdll!RtlEnterCriticalSection` at `0x180081cea`
- `ntdll!RtlEnterCriticalSection` at `0x180081d8a`
- `ntdll!RtlEnterCriticalSection` at `0x180081f74`
- `ntdll!RtlEnterCriticalSection` at `0x180081fb8`
- `ntdll!RtlEnterCriticalSection` at `0x1800820fa`
- `ntdll!RtlEnterCriticalSection` at `0x180082713`
- `ntdll!RtlEnterCriticalSection` at `0x180082744`
- `ntdll!RtlEnterCriticalSection` at `0x180082b05`
- `ntdll!RtlEnterCriticalSection` at `0x180082b46`
- `ntdll!RtlEnterCriticalSection` at `0x180082bdc`
- `ntdll!RtlLeaveCriticalSection` at `0x180081bf6`
- `ntdll!RtlLeaveCriticalSection` at `0x180081f6b`
- `ntdll!RtlLeaveCriticalSection` at `0x180081f84`
- `ntdll!RtlLeaveCriticalSection` at `0x1800820bf`
- `ntdll!RtlLeaveCriticalSection` at `0x180082602`
- `ntdll!RtlLeaveCriticalSection` at `0x180082757`
- `ntdll!RtlLeaveCriticalSection` at `0x180082b24`
- `ntdll!RtlLeaveCriticalSection` at `0x180082b89`
- `ntdll!RtlLeaveCriticalSection` at `0x180082c28`
- `ntdll!RtlLeaveCriticalSection` at `0x180082d1c`
- `ntdll!RtlLeaveCriticalSection` at `0x180081bf6`
- `ntdll!RtlLeaveCriticalSection` at `0x180081f6b`
- `ntdll!RtlLeaveCriticalSection` at `0x180081f84`
- `ntdll!RtlLeaveCriticalSection` at `0x1800820bf`
- `ntdll!RtlLeaveCriticalSection` at `0x180082602`
- `ntdll!RtlLeaveCriticalSection` at `0x180082757`
- `ntdll!RtlLeaveCriticalSection` at `0x180082b24`
- `ntdll!RtlLeaveCriticalSection` at `0x180082b89`
- `ntdll!RtlLeaveCriticalSection` at `0x180082c28`
- `ntdll!RtlLeaveCriticalSection` at `0x180082d1c`
- `CRYPTSP!SystemFunction007` at `0x180082df7`
- `CRYPTSP!SystemFunction007` at `0x180082df7`
- `LSASRV!LsaICheckProtectedUserByTokenInfo` at `0x180082ba7`
- `LSASRV!LsaICheckProtectedUserByTokenInfo` at `0x180082ba7`

## string_xrefs

- `0x1800829d8`: `Failed to make token information v3: 0x%x`
- `0x180081d24`: `KerbCreateTokenFromLogonTicket using LogonTicketKey supplied\n`
- `0x180081b4d`: `KerbCreateTokenFromLogonTicket`
- `0x180081d31`: `KerbCreateTokenFromLogonTicket`
- `0x180081dfa`: `KerbCreateTokenFromLogonTicket`
- `0x180081ecd`: `KerbCreateTokenFromLogonTicket`
- `0x180081f4f`: `KerbCreateTokenFromLogonTicket`
- `0x180081fd7`: `KerbCreateTokenFromLogonTicket`
- `0x18008205d`: `KerbCreateTokenFromLogonTicket`
- `0x1800820a5`: `KerbCreateTokenFromLogonTicket`
- `0x180082123`: `KerbCreateTokenFromLogonTicket`
- `0x1800821d7`: `KerbCreateTokenFromLogonTicket`
- `0x18008221a`: `KerbCreateTokenFromLogonTicket`
- `0x1800822e7`: `KerbCreateTokenFromLogonTicket`
- `0x180082313`: `KerbCreateTokenFromLogonTicket`
- `0x180082361`: `KerbCreateTokenFromLogonTicket`
- `0x1800823a3`: `KerbCreateTokenFromLogonTicket`
- `0x1800823ef`: `KerbCreateTokenFromLogonTicket`
- `0x180082421`: `KerbCreateTokenFromLogonTicket`
- `0x180082486`: `KerbCreateTokenFromLogonTicket`
- `0x18008257e`: `KerbCreateTokenFromLogonTicket`
- `0x1800826a0`: `KerbCreateTokenFromLogonTicket`
- `0x18008277a`: `KerbCreateTokenFromLogonTicket`
- `0x1800827b0`: `KerbCreateTokenFromLogonTicket`
- `0x1800827dc`: `KerbCreateTokenFromLogonTicket`
- `0x180082895`: `KerbCreateTokenFromLogonTicket`
- `0x1800828eb`: `KerbCreateTokenFromLogonTicket`
- `0x18008292c`: `KerbCreateTokenFromLogonTicket`
- `0x180082979`: `KerbCreateTokenFromLogonTicket`
- `0x180082ae9`: `KerbCreateTokenFromLogonTicket`
- `0x180082c4d`: `KerbCreateTokenFromLogonTicket`
- `0x180082ed1`: `KerbCreateTokenFromLogonTicket`
- `0x180081fca`: `KerbCreateTokenFromLogonTicket getting WkstaKey from SystemLogonSession\n`
- `0x18008204c`: `KerbCreateTokenFromLogonTicket attempting to contact the KDC, and retry, for deferred key %d\n`
- `0x180082388`: `KerbCreateTokenFromLogonTicket couldn't find correct key type: 0x%x`
- `0x1800827c0`: `%hs: Error verifying service ticket: %#x\n`
- `0x180082356`: `KerbCreateTokenFromLogonTicket CipherHasAttribute failed %#x for etype %d\n`
- `0x180082098`: `KerbCreateTokenFromLogonTicket trying to normalize the credential for localsystem\n`
- `0x18008223c`: `KerbCreateTokenFromLogonTicket failed to normalize the credential %#x\n`
- `0x180082301`: `Error verifying service ticket: %#x`
- `0x1800823e4`: `KerbCreateTokenFromLogonTicket failed to decrypt workstation ticket from %wZ of etype %d : %#x\n`
- `0x180082410`: `failed to compare client's session key to workstation's session key: 0x%x`
- `0x18008276e`: `Create non-delegatable S4U logon session %#x:%x: ValidationInfo %p\n`
- `0x180082ec4`: `We don't have any information for creating a token!\n`
- `0x180082884`: `Failed to create local pac for client: 0x%x\n`
- `0x180082adc`: `Building identify token\n`
- `0x180082bb3`: `LsaICheckProtectedUserByTokenInfo failed: %#x\n`
- `0x180082cb5`: `KerbFilterAndEncodeCachedCredentialData failed: %#x\n`
- `0x180082e03`: `KerbCreateTokenFromLogonTicket failed to calculate NT OWF %#x\n`

## pseudocode

```c
__int64 __fastcall KerbCreateTokenFromLogonTicket(
        struct _KERB_TICKET_CACHE_ENTRY *a1,
        struct _LUID *a2,
        struct _KERB_INTERACTIVE_LOGON *a3,
        struct _KERB_PLAINTEXT_PASSWORD *a4,
        char a5,
        enum _SECURITY_LOGON_TYPE a6,
        struct _KERB_ENCRYPTION_KEY *a7,
        struct _KERB_MESSAGE_BUFFER *a8,
        struct _UNICODE_STRING *a9,
        struct _KERB_INTERNAL_NAME *a10,
        struct _UNICODE_STRING *a11,
        struct _LUID *a12,
        struct KerbCredIsoApi *a13,
        struct _RTL_CRITICAL_SECTION *a14,
        enum _LSA_TOKEN_INFORMATION_TYPE *a15,
        void **a16,
        unsigned int *a17,
        void **a18,
        struct _SECPKG_PRIMARY_CRED *a19,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a20,
        struct _NETLOGON_VALIDATION_SAM_INFO4 **a21,
        struct _KERB_TICKET_LOGON_SUPP_CRED *a22)
{
  DWORD LowPart; // ebx
  int OurDomainName; // edi
  struct _KERB_LOGON_SESSION *v25; // r12
  LONG HighPart; // esi
  char v27; // r14
  int v28; // eax
  bool v29; // zf
  struct _RTL_CRITICAL_SECTION *LogonSession; // rax
  struct _KERB_INTERACTIVE_PROFILE **v31; // r15
  struct _SECPKG_PRIMARY_CRED *v32; // rbx
  struct _PACTYPE *v33; // rsi
  PSID UserSid; // rcx
  unsigned __int8 v36; // r8
  char v37; // cl
  struct _KERB_ENCRYPTION_KEY *v38; // rdi
  int TicketForCredential; // eax
  const char *v40; // r9
  __int64 v41; // r8
  int v42; // esi
  int v43; // r12d
  struct _KERB_LOGON_SESSION *v44; // r14
  int v45; // eax
  struct _KERB_LOGON_SESSION *v46; // rsi
  struct _RTL_CRITICAL_SECTION *v47; // rbx
  int v48; // esi
  __int64 v49; // rcx
  int HasAttribute; // ecx
  struct _KERB_ENCRYPTION_KEY *v51; // rax
  struct _KERB_ENCRYPTION_KEY *v52; // r14
  struct _KERB_INTERACTIVE_LOGON *v53; // rsi
  WCHAR *v54; // rcx
  int v55; // eax
  struct PKERB_AUTHORIZATION_DATA_s *v56; // rcx
  __int64 v57; // r8
  int PacFromAuthData; // eax
  __int64 v59; // rbx
  unsigned int v60; // edx
  unsigned __int8 v61; // r8
  unsigned __int8 v62; // r8
  const void *v63; // rcx
  unsigned __int8 v64; // cl
  struct _KERB_INTERNAL_NAME *v65; // rbx
  struct _UNICODE_STRING *v66; // rax
  int v67; // ebx
  struct _PAC_INFO_BUFFER *v68; // rax
  struct _UNICODE_STRING *v69; // r8
  int v70; // eax
  int InteractiveProfile; // eax
  unsigned __int8 v72; // r8
  struct _UNICODE_STRING *p_DownlevelName; // rcx
  const struct _UNICODE_STRING *v74; // rdx
  unsigned __int8 v75; // r8
  unsigned __int8 v76; // r8
  struct _KERB_ENCRYPTION_KEY *v77; // rdi
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v78; // r15
  __int64 v79; // rcx
  int v80; // eax
  unsigned __int8 *v81; // rcx
  __int64 v82; // rax
  unsigned __int8 *v83; // rdx
  struct _KERB_INTERACTIVE_LOGON *v84; // rcx
  struct _UNICODE_STRING *p_LogonDomainName; // rdx
  struct _UNICODE_STRING *p_UserName; // rcx
  struct _KERB_INTERACTIVE_LOGON *v87; // rbx
  struct _NETLOGON_VALIDATION_SAM_INFO4 **v88; // rcx
  struct KERB_ENCRYPTED_TICKET *v89; // [rsp+20h] [rbp-E0h]
  struct KERB_ENCRYPTED_TICKET *v90; // [rsp+20h] [rbp-E0h]
  struct KERB_ENCRYPTED_TICKET *v91; // [rsp+20h] [rbp-E0h]
  struct KERB_ENCRYPTED_TICKET *v92; // [rsp+20h] [rbp-E0h]
  size_t v93; // [rsp+28h] [rbp-D8h]
  struct _KERB_INTERACTIVE_LOGON *v94; // [rsp+28h] [rbp-D8h]
  size_t v95; // [rsp+28h] [rbp-D8h]
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v96; // [rsp+30h] [rbp-D0h]
  size_t v97; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v98; // [rsp+70h] [rbp-90h] BYREF
  char v99; // [rsp+71h] [rbp-8Fh]
  struct _PACTYPE *v100; // [rsp+78h] [rbp-88h] BYREF
  struct _SECPKG_PRIMARY_CRED *v101; // [rsp+80h] [rbp-80h]
  struct _KERB_INTERACTIVE_PROFILE **v102; // [rsp+88h] [rbp-78h]
  int v103; // [rsp+90h] [rbp-70h] BYREF
  struct _KERB_LOGON_SESSION *v104; // [rsp+98h] [rbp-68h]
  char v105; // [rsp+A0h] [rbp-60h]
  char v106; // [rsp+A1h] [rbp-5Fh]
  char v107; // [rsp+A2h] [rbp-5Eh] BYREF
  char v108; // [rsp+A3h] [rbp-5Dh]
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v109; // [rsp+A8h] [rbp-58h] BYREF
  bool v110; // [rsp+B0h] [rbp-50h]
  struct KERB_ENCRYPTED_TICKET *v111; // [rsp+B8h] [rbp-48h] BYREF
  struct _KERB_ENCRYPTION_KEY *KeyFromList; // [rsp+C0h] [rbp-40h]
  struct _LSA_TOKEN_INFORMATION_V3 *v113; // [rsp+C8h] [rbp-38h] BYREF
  struct _LUID v114; // [rsp+D0h] [rbp-30h] BYREF
  struct _KERB_INTERACTIVE_LOGON *v115; // [rsp+D8h] [rbp-28h]
  unsigned int v116; // [rsp+E0h] [rbp-20h] BYREF
  _KERB_INTERACTIVE_LOGON v117; // [rsp+E8h] [rbp-18h] BYREF
  int v118; // [rsp+120h] [rbp+20h] BYREF
  struct _KERB_ENCRYPTION_KEY *v119; // [rsp+128h] [rbp+28h]
  unsigned __int8 *v120; // [rsp+130h] [rbp+30h] BYREF
  __int64 v121; // [rsp+138h] [rbp+38h] BYREF
  __int64 v122; // [rsp+140h] [rbp+40h] BYREF
  struct _UNICODE_STRING *v123; // [rsp+148h] [rbp+48h]
  struct _UNICODE_STRING v124; // [rsp+150h] [rbp+50h] BYREF
  struct _LUID *v125; // [rsp+160h] [rbp+60h]
  struct _KERB_PLAINTEXT_PASSWORD *v126; // [rsp+168h] [rbp+68h]
  struct _KERB_MESSAGE_BUFFER *v127; // [rsp+170h] [rbp+70h]
  struct _KERB_TICKET_LOGON_SUPP_CRED *v128; // [rsp+178h] [rbp+78h]
  struct _KERB_INTERNAL_NAME *v129; // [rsp+180h] [rbp+80h]
  void **v130; // [rsp+188h] [rbp+88h]
  enum _LSA_TOKEN_INFORMATION_TYPE *v131; // [rsp+190h] [rbp+90h]
  struct _NETLOGON_VALIDATION_SAM_INFO4 **v132; // [rsp+198h] [rbp+98h]
  struct _UNICODE_STRING *v133; // [rsp+1A0h] [rbp+A0h]
  unsigned int *v134; // [rsp+1A8h] [rbp+A8h]
  struct _UNICODE_STRING v135; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _UNICODE_STRING v136; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _UNICODE_STRING v137; // [rsp+1D0h] [rbp+D0h] BYREF
  struct _UNICODE_STRING v138; // [rsp+1E0h] [rbp+E0h] BYREF
  struct KerbCredIsoApi *v139; // [rsp+1F0h] [rbp+F0h]
  struct _LM_OWF_PASSWORD v140; // [rsp+1F8h] [rbp+F8h] BYREF

  LowPart = 999;
  v127 = a8;
  v101 = a19;
  v119 = a7;
  v123 = a9;
  v129 = a10;
  v133 = a11;
  v139 = a13;
  v131 = a15;
  v134 = a17;
  v125 = a2;
  v140.data[0] = (CYPHER_BLOCK)a20;
  OurDomainName = 0;
  v25 = 0;
  v126 = a4;
  HighPart = 0;
  v27 = 0;
  v111 = 0;
  v100 = 0;
  v122 = 0;
  v121 = 0;
  v109 = 0;
  v113 = 0;
  v108 = 0;
  v103 = 0;
  v118 = 0;
  v116 = 0;
  v120 = 0;
  v107 = 0;
  v128 = a22;
  v115 = a3;
  v130 = a16;
  v102 = (struct _KERB_INTERACTIVE_PROFILE **)a18;
  v132 = a21;
  v114 = (struct _LUID)999LL;
  v135 = 0;
  v124 = 0;
  v136 = 0;
  v137 = 0;
  v138 = 0;
  *(_OWORD *)&v117.MessageType = 0;
  if ( (unsigned int)a6 > RemoteInteractive || (v28 = 1076, v106 = 1, !_bittest(&v28, a6)) )
    v106 = 0;
  if ( (unsigned int)(a6 - 3) <= 2 || (v105 = 0, a6 == NetworkCleartext) )
    v105 = 1;
  v110 = (unsigned int)(a3->MessageType - 10) <= 2;
  *a18 = 0;
  *a16 = 0;
  *a21 = 0;
  if ( a5 )
  {
    v33 = v100;
    goto LABEL_159;
  }
  KeyFromList = 0;
  v29 = a3->MessageType == KerbS4ULogon;
  v99 = 0;
  if ( v29 )
  {
    LogonSession = (struct _RTL_CRITICAL_SECTION *)KerbLocateLogonSession(a12, 0);
    v104 = (struct _KERB_LOGON_SESSION *)LogonSession;
    v25 = (struct _KERB_LOGON_SESSION *)LogonSession;
    if ( !LogonSession )
    {
LABEL_10:
      OurDomainName = -1073741729;
      goto LABEL_11;
    }
    RtlEnterCriticalSection(LogonSession + 2);
    v27 = 1;
    OurDomainName = KerbDuplicateStringEx(&v135, (const struct _UNICODE_STRING *)((char *)v25 + 136), v36);
    if ( OurDomainName < 0 )
      goto LABEL_11;
    if ( a1 && (*((_BYTE *)a1 + 164) & 0x10) != 0 )
    {
      KerbTracerT::Log(
        3,
        "KerbCreateTokenFromLogonTicket",
        4225,
        "KerbCreateTokenFromLogonTicket using LogonTicketKey supplied\n");
      v37 = 1;
      v38 = (struct _KERB_TICKET_CACHE_ENTRY *)((char *)a1 + 208);
      v99 = 1;
      KeyFromList = (struct _KERB_TICKET_CACHE_ENTRY *)((char *)a1 + 208);
    }
    else
    {
      v37 = 0;
      v38 = 0;
    }
  }
  else
  {
    v104 = KerbLocateLogonSession(&v114, 0);
    v25 = v104;
    if ( !v104 )
      goto LABEL_10;
    OurDomainName = KerbGetOurDomainName(&v135);
    if ( OurDomainName < 0 )
      goto LABEL_11;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v104 + 2);
    v38 = KeyFromList;
    v27 = 1;
    HighPart = v114.HighPart;
    v37 = (char)KeyFromList;
    LowPart = v114.LowPart;
  }
  if ( (_BYTE)KerbGlobalRoles
    && (*((_DWORD *)v25 + 16) == LowPart && *((_DWORD *)v25 + 17) == HighPart
     || *((_DWORD *)v25 + 16) == 996 && !*((_DWORD *)v25 + 17))
    && ((*((_DWORD *)a1 + 77) - 1) & 0xFFFFFFFD) == 0 )
  {
    TicketForCredential = -1073741715;
    v40 = "reject DES logon ticket: %#x\n";
    OurDomainName = -1073741715;
    v41 = 4270;
    goto LABEL_51;
  }
  if ( v38 )
  {
    v44 = v104;
    v43 = 0;
    v42 = 0;
    goto LABEL_55;
  }
  v42 = 1;
  v43 = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      KerbTracerT::Log(
        3,
        "KerbCreateTokenFromLogonTicket",
        4286,
        "KerbCreateTokenFromLogonTicket getting WkstaKey from SystemLogonSession\n");
      v44 = v104;
      KeyFromList = (struct _KERB_ENCRYPTION_KEY *)KerbGetKeyFromList(
                                                     *((_QWORD *)v104 + 33),
                                                     *((unsigned int *)a1 + 77),
                                                     1);
      v38 = KeyFromList;
      if ( !KeyFromList )
      {
        OurDomainName = -1073741715;
        if ( (*((_BYTE *)v44 + 904) & 1) == 0
          || !v43
          || !(unsigned __int8)KerberosCryptoPolicy::CipherIsDeferred(*((unsigned int *)a1 + 77)) )
        {
          LODWORD(v89) = *((_DWORD *)a1 + 77);
          KerbTracerT::Log(
            2,
            "KerbCreateTokenFromLogonTicket",
            4309,
            "KerbCreateTokenFromLogonTicket couldn't find correct key type: 0x%x",
            v89);
          goto LABEL_97;
        }
        KerbTracerT::Log(
          2,
          "KerbCreateTokenFromLogonTicket",
          4303,
          "KerbCreateTokenFromLogonTicket attempting to contact the KDC, and retry, for deferred key %d\n",
          *((_DWORD *)a1 + 77));
        goto LABEL_83;
      }
      v37 = v99;
LABEL_55:
      if ( !v37 )
        KerbRevealKey(v38);
      v103 = 0;
      OurDomainName = (*(__int64 (__fastcall **)(_QWORD, char *, struct _KERB_ENCRYPTION_KEY *, _QWORD, struct KERB_ENCRYPTED_TICKET **, int *))(**(_QWORD **)v38 + 56LL))(
                        *(_QWORD *)v38,
                        (char *)a1 + 272,
                        v38,
                        0,
                        &v111,
                        &v103);
      if ( !v99 )
        KerbHideKey(KeyFromList);
      if ( OurDomainName < 0 )
      {
        LODWORD(v93) = OurDomainName;
        KerbTracerT::Log(
          1,
          "KerbCreateTokenFromLogonTicket",
          4341,
          "%hs: Error verifying service ticket: %#x\n",
          "KerbCreateTokenFromLogonTicket",
          v93);
        goto LABEL_97;
      }
      if ( (unsigned int)(v115->MessageType - 10) <= 1 && (*(_BYTE *)(&v115->MessageType + 1) & 1) != 0 )
      {
        v45 = v103;
        if ( !v103 )
        {
          OurDomainName = -1073741811;
          KerbTracerT::Log(
            1,
            "KerbCreateTokenFromLogonTicket",
            4366,
            "Can't allow expired ticket on a non-expired ticket\n");
LABEL_97:
          v27 = 1;
LABEL_98:
          v25 = v104;
          goto LABEL_11;
        }
        if ( v103 == 32 )
        {
          v45 = 0;
          v103 = 0;
        }
      }
      else
      {
        v45 = v103;
      }
      if ( !v45 )
        goto LABEL_73;
      KerbTracerT::Log(2, "KerbCreateTokenFromLogonTicket", 4378, "Failed to decrypt workstation ticket: 0x%x", v45);
      if ( v103 == 41 )
      {
        OurDomainName = -1073741427;
      }
      else
      {
        OurDomainName = KerbMapKerbError(v103);
        if ( OurDomainName != -1073741427 )
          goto LABEL_73;
      }
      if ( !v43 || (*((_BYTE *)v44 + 904) & 1) == 0 )
        break;
LABEL_83:
      v49 = *((unsigned int *)a1 + 77);
      v98 = 0;
      HasAttribute = KerberosCryptoPolicy::CipherHasAttribute(v49, 1, &v98);
      if ( HasAttribute < 0 )
      {
        LODWORD(v93) = *((_DWORD *)a1 + 77);
        LODWORD(v90) = HasAttribute;
        KerbTracerT::Log(
          1,
          "KerbCreateTokenFromLogonTicket",
          4409,
          "KerbCreateTokenFromLogonTicket CipherHasAttribute failed %#x for etype %d\n",
          v90,
          v93);
        goto LABEL_97;
      }
      if ( !v98 )
      {
        if ( OurDomainName != -1073741427 )
          goto LABEL_73;
        break;
      }
      KerbTracerT::Log(
        2,
        "KerbCreateTokenFromLogonTicket",
        4415,
        "KerbCreateTokenFromLogonTicket trying to normalize the credential for localsystem\n");
      v25 = v104;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v104 + 2);
      v27 = 0;
      TicketForCredential = KerbGetTicketForCredential(v25, 0, 0, 0, 0, 0, 0, 0);
      if ( TicketForCredential < 0 )
      {
        v40 = "KerbCreateTokenFromLogonTicket failed to normalize the credential %#x\n";
        v41 = 4438;
        goto LABEL_51;
      }
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v25 + 2);
      v43 = 0;
    }
    if ( !*((_QWORD *)v44 + 34) )
      goto LABEL_73;
    KerbTracerT::Log(2, "KerbCreateTokenFromLogonTicket", 4459, "Current system password failed, trying old password\n");
    v51 = (struct _KERB_ENCRYPTION_KEY *)KerbGetKeyFromList(*((_QWORD *)v44 + 34), *((unsigned int *)a1 + 77), 1);
    KeyFromList = v51;
    v52 = v51;
    if ( !v51 )
    {
      KerbTracerT::Log(
        1,
        "KerbCreateTokenFromLogonTicket",
        4473,
        "Couldn't find correct key type: 0x%x",
        *((_DWORD *)a1 + 77));
      OurDomainName = -1073741427;
      goto LABEL_97;
    }
    KerbRevealKey(v51);
    v103 = 0;
    OurDomainName = (*(__int64 (__fastcall **)(_QWORD, char *, struct _KERB_ENCRYPTION_KEY *, _QWORD, struct KERB_ENCRYPTED_TICKET **, int *))(**(_QWORD **)v52 + 56LL))(
                      *(_QWORD *)v52,
                      (char *)a1 + 272,
                      v52,
                      0,
                      &v111,
                      &v103);
    KerbHideKey(v52);
    if ( OurDomainName < 0 )
    {
      LODWORD(v91) = OurDomainName;
      KerbTracerT::Log(1, "KerbCreateTokenFromLogonTicket", 4491, "Error verifying service ticket: %#x", v91);
      goto LABEL_97;
    }
    if ( !v103 )
    {
      OurDomainName = 0;
      v27 = 1;
      goto LABEL_101;
    }
    KerbTracerT::Log(
      1,
      "KerbCreateTokenFromLogonTicket",
      4496,
      "Failed to decrypt workstation ticket using old password");
    if ( v103 == 41 )
    {
      OurDomainName = -1073741427;
      goto LABEL_74;
    }
    OurDomainName = KerbMapKerbError(v103);
LABEL_73:
    v27 = 1;
    if ( OurDomainName != -1073741427 )
      goto LABEL_111;
LABEL_74:
    v27 = 1;
    if ( (*((_BYTE *)v104 + 528) & 1) == 0 || !v42 )
      goto LABEL_112;
    KerbTracerT::Log(2, "KerbCreateTokenFromLogonTicket", 4521, "Current Gmsa password failed, trying force fetch\n");
    v46 = v104;
    v47 = (struct _RTL_CRITICAL_SECTION *)((char *)v104 + 80);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v104 + 2);
    RtlEnterCriticalSection(v47);
    *((_DWORD *)v46 + 132) |= 2u;
    RtlLeaveCriticalSection(v47);
    KeyFromList = 0;
    v48 = KerbGetTicketForCredential(v46, 0, 0, 0, 0, 0, 0, 0);
    RtlEnterCriticalSection(v47);
    if ( v48 < 0 )
      break;
    v42 = 0;
  }
  KerbTracerT::Log(
    1,
    "KerbCreateTokenFromLogonTicket",
    4552,
    "%hs failed for Gmsa retry %#x\n",
    "KerbCreateTokenFromLogonTicket",
    v48);
LABEL_111:
  if ( OurDomainName < 0 )
  {
LABEL_112:
    LODWORD(v96) = OurDomainName;
    LODWORD(v93) = *((_DWORD *)a1 + 77);
    KerbTracerT::Log(
      1,
      "KerbCreateTokenFromLogonTicket",
      4565,
      "KerbCreateTokenFromLogonTicket failed to decrypt workstation ticket from %wZ of etype %d : %#x\n",
      (char *)a1 + 112,
      v93,
      v96);
    goto LABEL_98;
  }
LABEL_101:
  v53 = v115;
  if ( v115->MessageType != KerbTicketLogon && v115->MessageType != KerbTicketUnlockLogon )
  {
    v54 = (WCHAR *)*((_QWORD *)a1 + 21);
    *(_QWORD *)(&v117.Password.MaximumLength + 1) = 0;
    *(_OWORD *)(&v117.UserName.MaximumLength + 1) = 0;
    v117.LogonDomainName.Buffer = v54;
    v98 = 0;
    HIDWORD(v117.Password.Buffer) = 0;
    *(_DWORD *)&v117.UserName.Length = 1;
    *(_DWORD *)(&v117.UserName.MaximumLength + 1) = *((_DWORD *)v111 + 6);
    LODWORD(v117.UserName.Buffer) = *((_DWORD *)v111 + 8);
    *(_QWORD *)&v117.Password.Length = *((_QWORD *)v111 + 5);
    v55 = (*(__int64 (__fastcall **)(WCHAR *, char *, PWSTR *, unsigned __int8 *))(*(_QWORD *)v54 + 264LL))(
            v54,
            (char *)a1 + 168,
            &v117.LogonDomainName.Buffer,
            &v98);
    OurDomainName = v55;
    if ( v55 < 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbCreateTokenFromLogonTicket",
        4589,
        "failed to compare client's session key to workstation's session key: 0x%x",
        v55);
      goto LABEL_114;
    }
    if ( !v98 )
    {
      KerbTracerT::Log(
        1,
        "KerbCreateTokenFromLogonTicket",
        4593,
        "session key in workstation ticket doesn't match what the client got from the KDC");
LABEL_114:
      OurDomainName = -1073741427;
      goto LABEL_98;
    }
  }
  if ( v53->MessageType == KerbS4ULogon )
  {
    v98 = 0;
    v103 = KerbCompareKdcNameToPrincipalName((struct KERB_ENCRYPTED_TICKET *)((char *)v111 + 56), v129, &v98);
    if ( v103 )
    {
LABEL_117:
      OurDomainName = -1073741670;
      goto LABEL_98;
    }
    if ( !v98 )
    {
      KerbTracerT::Log(1, "KerbCreateTokenFromLogonTicket", 4630, "S4UClient name != ticket CLIENTNAME\n");
LABEL_120:
      OurDomainName = -1073741715;
      goto LABEL_98;
    }
    v103 = KerbCompareUnicodeRealmToKerbRealm((char *)v111 + 48, v133, &v98);
    if ( v103 )
      goto LABEL_117;
    if ( !v98 )
    {
      KerbTracerT::Log(1, "KerbCreateTokenFromLogonTicket", 4653, "S4UClient REALM != ticket REALM\n");
      goto LABEL_120;
    }
  }
  if ( (*(_BYTE *)v111 & 0x10) == 0 )
    goto LABEL_147;
  v56 = (struct PKERB_AUTHORIZATION_DATA_s *)*((_QWORD *)v111 + 20);
  if ( !v56 )
    goto LABEL_147;
  memset(&v117.LogonDomainName.Buffer, 0, 40);
  if ( !KerbVerifyAuthData(v56) )
  {
    KerbTracerT::Log(1, "KerbCreateTokenFromLogonTicket", 4677, "Failed to verify auth data\n");
    goto LABEL_120;
  }
  PacFromAuthData = KerbGetPacFromAuthData(*((_QWORD *)v111 + 20), &v121, v57, &v122);
  v103 = PacFromAuthData;
  if ( PacFromAuthData )
  {
    OurDomainName = KerbMapKerbError(PacFromAuthData);
    goto LABEL_98;
  }
  v59 = v122;
  if ( !v122 )
  {
LABEL_147:
    v25 = v104;
LABEL_148:
    if ( v53->MessageType != KerbS4ULogon )
      goto LABEL_155;
    if ( v109 )
    {
      if ( (*((_DWORD *)v109 + 60) & 0x4000) == 0 )
      {
        RtlEnterCriticalSection(a14 + 2);
        LODWORD(a14[22].LockSemaphore) |= 0x100u;
        RtlLeaveCriticalSection(a14 + 2);
        goto LABEL_155;
      }
      v63 = (const void *)WORD1(v109);
    }
    else
    {
      v63 = 0;
    }
    KerbTracerT::Log(
      21,
      "KerbCreateTokenFromLogonTicket",
      4824,
      "Create non-delegatable S4U logon session %#x:%x: ValidationInfo %p\n",
      HIDWORD(a14[1].LockSemaphore),
      LODWORD(a14[1].LockSemaphore),
      v63);
LABEL_155:
    v33 = v100;
    if ( v100 )
    {
      v64 = 1;
      goto LABEL_176;
    }
LABEL_159:
    v114 = 0;
    v65 = 0;
    KerbTracerT::Log(2, "KerbCreateTokenFromLogonTicket", 4844, "No authorization data in ticket - trying local\n");
    if ( a1 && v111 )
    {
      if ( (unsigned int)KerbConvertRealmToUnicodeString(&v124, (char *)v111 + 48)
        || (unsigned int)KerbConvertPrincipalNameToKdcName(
                           (struct _KERB_INTERNAL_NAME **)&v114,
                           (struct KERB_ENCRYPTED_TICKET *)((char *)v111 + 56)) )
      {
        OurDomainName = -1073741670;
        goto LABEL_134;
      }
      v65 = (struct _KERB_INTERNAL_NAME *)v114;
      v66 = v123;
    }
    else
    {
      v66 = v123;
      if ( !v123 || !v123->Buffer )
      {
        KerbTracerT::Log(
          1,
          "KerbCreateTokenFromLogonTicket",
          4877,
          "We don't have any information for creating a token!\n");
        OurDomainName = -1073741715;
        goto LABEL_134;
      }
    }
    v67 = KerbCreatePacForKerbClient(&v100, v65, &v124, v66);
    KerbFreeKdcName((struct _KERB_INTERNAL_NAME **)&v114);
    if ( v67 < 0 )
    {
      KerbTracerT::Log(1, "KerbCreateTokenFromLogonTicket", 4895, "Failed to create local pac for client: 0x%x\n", v67);
      v33 = v100;
      v31 = v102;
      if ( OurDomainName >= 0 )
        OurDomainName = v67;
      v32 = v101;
      goto LABEL_13;
    }
    v33 = v100;
    v108 = 1;
    v68 = PAC_Find(v100, 1, 0);
    if ( !v68 )
    {
      KerbTracerT::Log(1, "KerbCreateTokenFromLogonTicket", 4922, "Failed to find logon info!");
LABEL_133:
      OurDomainName = -1073741811;
      goto LABEL_134;
    }
    v70 = PAC_UnmarshallAndConvertValidationInfo(&v109, 0, v69, *((unsigned __int8 **)v68 + 1), *((_DWORD *)v68 + 1));
    OurDomainName = v70;
    if ( v70 < 0 )
    {
      KerbTracerT::Log(1, "KerbCreateTokenFromLogonTicket", 4941, "Failed to unmarshall validation info: 0x%x", v70);
      goto LABEL_134;
    }
    v64 = 0;
LABEL_176:
    if ( (*((_DWORD *)v109 + 60) & 0x1C0) == 0 || v105 || ((__int64)a14[22].LockSemaphore & 0x800) != 0 )
    {
      TicketForCredential = KerbMakeTokenInformationV3(
                              v64,
                              v109,
                              0,
                              0,
                              a14[10].DebugInfo != 0,
                              (struct _SAM_CLAIMS_BLOB *)&v117,
                              0,
                              0,
                              &v113);
      OurDomainName = TicketForCredential;
      if ( TicketForCredential >= 0 )
      {
        v31 = v102;
        InteractiveProfile = KerbAllocateInteractiveProfile(
                               v102,
                               v134,
                               v109,
                               (struct _KERB_LOGON_SESSION *)a14,
                               v89,
                               v94);
        v32 = v101;
        OurDomainName = InteractiveProfile;
        if ( InteractiveProfile )
          goto LABEL_12;
        p_DownlevelName = &v101->DownlevelName;
        v74 = (const struct _UNICODE_STRING *)((char *)v109 + 48);
        v101->LogonId = *v125;
        OurDomainName = KerbDuplicateStringEx(p_DownlevelName, v74, v72);
        if ( OurDomainName < 0 )
          goto LABEL_12;
        OurDomainName = KerbDuplicateStringEx(&v32->DomainName, (const struct _UNICODE_STRING *)v109 + 13, v75);
        if ( OurDomainName < 0 )
          goto LABEL_12;
        OurDomainName = KerbDuplicateStringEx(&v32->LogonServer, (const struct _UNICODE_STRING *)v109 + 12, v76);
        if ( OurDomainName < 0 )
          goto LABEL_12;
        OurDomainName = KerbDuplicateSid(&v32->UserSid);
        if ( OurDomainName < 0 )
          goto LABEL_12;
        v29 = !v110;
        v32->Flags = 0;
        if ( !v29 )
        {
          memset(&v117.LogonDomainName.Buffer, 0, 32);
          OurDomainName = ((__int64 (__fastcall *)(PWSTR *))LsaFunctions->GetClientInfo)(&v117.LogonDomainName.Buffer);
          if ( OurDomainName < 0 )
            goto LABEL_12;
          if ( !LOBYTE(v117.UserName.Buffer)
            || v115->MessageType == KerbS4ULogon && (*(_BYTE *)(&v115->MessageType + 1) & 8) != 0 )
          {
            KerbTracerT::Log(3, "KerbCreateTokenFromLogonTicket", 5072, "Building identify token\n");
            v32->Flags |= 0x10u;
          }
        }
        RtlEnterCriticalSection(a14 + 2);
        v77 = v119;
        if ( !a14[10].DebugInfo )
          KerbRevealKey(v119);
        RtlLeaveCriticalSection(a14 + 2);
        v78 = (struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)v140.data[0];
        OurDomainName = KerbExtractCachedCreds(v100, v77, *(struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY ***)v140.data);
        RtlEnterCriticalSection(a14 + 2);
        if ( !a14[10].DebugInfo )
          goto LABEL_199;
        if ( !*v78 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v79);
        if ( !a14[10].DebugInfo )
LABEL_199:
          KerbHideKey(v119);
        if ( OurDomainName >= 0 )
          OurDomainName = KerbUpdateSuppCredsWithNtowf((const struct _KERB_PRIMARY_CREDENTIAL *)&a14[3], v78);
        RtlLeaveCriticalSection(a14 + 2);
        if ( OurDomainName < 0 )
          goto LABEL_11;
        TicketForCredential = LsaICheckProtectedUserByTokenInfo(v113, (unsigned int)a6, &v107);
        OurDomainName = TicketForCredential;
        if ( TicketForCredential >= 0 )
        {
          if ( v106 )
          {
            if ( v107 )
            {
              RtlEnterCriticalSection(a14 + 2);
              LODWORD(v97) = 0;
              KerbCacheLogonInformation(
                (struct _UNICODE_STRING *)v109 + 3,
                (struct _UNICODE_STRING *)v109 + 13,
                0,
                0,
                (struct _KERB_LOGON_SESSION *)a14,
                0x10u,
                0,
                0,
                0,
                0,
                v97,
                0);
              RtlLeaveCriticalSection(a14 + 2);
              if ( a14[10].DebugInfo && ((__int64)a14[22].LockSemaphore & 0x800) == 0 )
              {
                KerbTracerT::Log(
                  8,
                  "KerbCreateTokenFromLogonTicket",
                  5161,
                  "calling LSA to derive credential keys for protected smartcard user.\n");
                v80 = KerbFilterAndEncodeCachedCredentialData(v113, v78, &v120, &v116);
                v81 = v120;
                OurDomainName = v80;
                if ( v120 )
                {
                  v82 = v116;
                  v83 = v120;
                  if ( v116 )
                  {
                    do
                    {
                      *v83++ = 0;
                      --v82;
                    }
                    while ( v82 );
                  }
                  KerbFree(v81);
                }
                if ( OurDomainName < 0 )
                {
                  LODWORD(v92) = OurDomainName;
                  KerbTracerT::Log(
                    1,
                    "KerbCreateTokenFromLogonTicket",
                    5176,
                    "KerbFilterAndEncodeCachedCredentialData failed: %#x\n",
                    v92);
                  goto LABEL_11;
                }
              }
            }
            else
            {
              memset(&v117.LogonDomainName.Buffer, 0, 24);
              if ( !((unsigned __int8 (__fastcall *)(PWSTR *))LsaFunctions->GetCallInfo)(&v117.LogonDomainName.Buffer) )
              {
                OurDomainName = -1073741595;
                goto LABEL_11;
              }
              if ( (v117.UserName.Length & 0x800) != 0 )
                *((_DWORD *)v109 + 42) |= 0x8000u;
              if ( v27 )
              {
                RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v25 + 2);
                v27 = 0;
              }
              if ( !a14[10].DebugInfo || ((__int64)a14[22].LockSemaphore & 0x800) != 0 )
              {
                if ( ((__int64)a14[22].LockSemaphore & 0x8000000) != 0 )
                {
                  LODWORD(v95) = v117.MessageType;
                  KerbCacheFidoLogon(
                    v109,
                    v113,
                    (struct _KERB_LOGON_SESSION *)a14,
                    v78,
                    *(void **)&v117.LogonDomainName.Length,
                    v95);
                }
                else
                {
                  v87 = v115;
                  if ( v115->MessageType == KerbInteractiveLogon || v115->MessageType == KerbWorkstationUnlockLogon )
                  {
                    v140 = 0;
                    if ( v126 )
                    {
                      if ( !*((_DWORD *)v126 + 2) )
                      {
                        TicketForCredential = SystemFunction007((char *)v126 + 16, &v140);
                        OurDomainName = TicketForCredential;
                        if ( TicketForCredential < 0 )
                        {
                          v40 = "KerbCreateTokenFromLogonTicket failed to calculate NT OWF %#x\n";
                          v41 = 5276;
                          goto LABEL_51;
                        }
                        LODWORD(v97) = v117.MessageType;
                        KerbCacheLogonInformation(
                          &v87->UserName,
                          &v87->LogonDomainName,
                          &v140,
                          0,
                          (struct _KERB_LOGON_SESSION *)a14,
                          0,
                          v109,
                          0,
                          0,
                          *(void **)&v117.LogonDomainName.Length,
                          v97,
                          0);
                      }
                    }
                  }
                }
              }
              else
              {
                v84 = v115;
                *((_DWORD *)v109 + 42) |= 0x10000u;
                if ( ((v84->MessageType - 13) & 0xFFFFFFFD) != 0 )
                {
                  p_LogonDomainName = 0;
                  p_UserName = 0;
                }
                else
                {
                  p_LogonDomainName = &v84->LogonDomainName;
                  p_UserName = &v84->UserName;
                }
                KerbCacheSmartCardLogon(
                  p_UserName,
                  p_LogonDomainName,
                  v109,
                  v113,
                  (struct _KERB_LOGON_SESSION *)a14,
                  v78,
                  *(void **)&v117.LogonDomainName.Length,
                  v117.MessageType);
              }
            }
          }
          if ( !v127
            || !*(_DWORD *)v127
            || (OurDomainName = KerbExtractForwardedTgt((struct _KERB_LOGON_SESSION *)a14, v127, v111, v139, v128),
                OurDomainName >= 0) )
          {
            *v130 = v113;
            v88 = v132;
            *v131 = LsaTokenInformationV3;
            *v88 = v109;
            v109 = 0;
          }
          goto LABEL_11;
        }
        v40 = "LsaICheckProtectedUserByTokenInfo failed: %#x\n";
        v41 = 5125;
      }
      else
      {
        v40 = "Failed to make token information v3: 0x%x";
        v41 = 4980;
      }
LABEL_51:
      LODWORD(v89) = TicketForCredential;
      KerbTracerT::Log(1, "KerbCreateTokenFromLogonTicket", v41, v40, v89);
      goto LABEL_11;
    }
    KerbTracerT::Log(
      1,
      "KerbCreateTokenFromLogonTicket",
      4956,
      "Logons to non-user accounts not allowed. UserAccountControl = 0x%x",
      *((_DWORD *)v109 + 60));
    OurDomainName = -1073741477;
LABEL_134:
    v32 = v101;
    v31 = v102;
    goto LABEL_13;
  }
  v33 = *(struct _PACTYPE **)(v122 + 24);
  v60 = *(_DWORD *)(v122 + 16);
  v100 = v33;
  if ( !(unsigned int)PAC_UnMarshal((unsigned __int64)v33, v60) )
  {
    KerbTracerT::Log(1, "KerbCreateTokenFromLogonTicket", 4708, "Failed to unmarshal pac");
    v25 = v104;
    goto LABEL_133;
  }
  v25 = v104;
  OurDomainName = KerbDuplicateStringEx(&v137, (const struct _UNICODE_STRING *)((char *)v104 + 136), v61);
  if ( OurDomainName < 0 )
    goto LABEL_11;
  OurDomainName = KerbDuplicateStringEx(&v138, (const struct _UNICODE_STRING *)((char *)v25 + 120), v62);
  if ( OurDomainName < 0 )
    goto LABEL_11;
  if ( (unsigned int)KerbDuplicateKey(&v117.LogonDomainName.Buffer, KeyFromList) )
    goto LABEL_138;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v25 + 2);
  if ( !v99 )
    KerbRevealKey((struct _KERB_ENCRYPTION_KEY *)&v117.LogonDomainName.Buffer);
  OurDomainName = KerbVerifyPacSignature(
                    &v137,
                    &v138,
                    v100,
                    *(unsigned int *)(v59 + 16),
                    (__int64)&v117.LogonDomainName.Buffer,
                    (__int64)v111,
                    1,
                    (struct _KERB_TICKET_CACHE_ENTRY *)((char *)a1 + 272),
                    0,
                    (__int64)&v109,
                    (__int64)&v117,
                    0,
                    0,
                    0);
  KerbFreeKey(&v117.LogonDomainName.Buffer);
  if ( OurDomainName >= 0 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v25 + 2);
    v53 = v115;
    v27 = 1;
    goto LABEL_148;
  }
  v27 = 0;
  KerbTracerT::Log(2, "KerbCreateTokenFromLogonTicket", 4778, "Pac signature did not verify %x.\n", OurDomainName);
  if ( a1 )
  {
    if ( (unsigned int)KerbConvertPrincipalNameToString(&v136, &v118, (char *)v111 + 56)
      || (unsigned int)KerbConvertRealmToUnicodeString(&v124, (char *)v111 + 48) )
    {
LABEL_138:
      OurDomainName = -1073741670;
    }
    else
    {
      KerbReportPACError(&v136, &v124, OurDomainName);
    }
  }
LABEL_11:
  v31 = v102;
  v32 = v101;
LABEL_12:
  v33 = v100;
LABEL_13:
  KerbFreeString(&v135);
  KerbFreeString(&v136);
  KerbFreeString(&v124);
  KerbFreeString(&v137);
  KerbFreeString(&v138);
  if ( v27 )
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v25 + 2);
  if ( v25 )
    KerbDereferenceLogonSession(v25);
  if ( OurDomainName < 0 )
  {
    if ( v113 )
      KerbFree(v113);
    if ( *v31 )
    {
      ((void (__fastcall *)(_QWORD))LsaFunctions->FreeClientBuffer)(0);
      *v31 = 0;
    }
    KerbFreeString(&v32->DownlevelName);
    KerbFreeString(&v32->DomainName);
    KerbFreeString(&v32->LogonServer);
    UserSid = v32->UserSid;
    if ( UserSid )
    {
      KerbFree(UserSid);
      v32->UserSid = 0;
    }
  }
  if ( v111 )
    KerbFreeData(51);
  if ( v108 && v33 )
    KerbFree(v33);
  if ( v121 )
    KerbFreeData(1);
  if ( v109 )
    KerbFree(v109);
  if ( *(_QWORD *)&v117.LogonDomainName.Length )
    KerbFree(*(_QWORD *)&v117.LogonDomainName.Length);
  return (unsigned int)OurDomainName;
}

```

## disassembly

```asm
0x1800819b0  mov     [rsp-8+arg_8], rbx
0x1800819b5  push    rbp
0x1800819b6  push    rsi
0x1800819b7  push    rdi
0x1800819b8  push    r12
0x1800819ba  push    r13
0x1800819bc  push    r14
0x1800819be  push    r15
0x1800819c0  lea     rbp, [rsp-110h]
0x1800819c8  sub     rsp, 210h
0x1800819cf  mov     rax, cs:__security_cookie
0x1800819d6  xor     rax, rsp
0x1800819d9  mov     [rbp+140h+var_38], rax
0x1800819e0  mov     rax, [rbp+140h+arg_38]
0x1800819e7  xorps   xmm0, xmm0
0x1800819ea  mov     r10, [rbp+140h+arg_78]
0x1800819f1  xorps   xmm1, xmm1
0x1800819f4  mov     r11, [rbp+140h+arg_A0]
0x1800819fb  mov     ebx, 3E7h
0x180081a00  mov     r13, [rbp+140h+arg_68]
0x180081a07  mov     r15, rcx
0x180081a0a  mov     rcx, [rbp+140h+arg_58]; struct _LUID *
0x180081a11  mov     [rbp+140h+var_D0], rax
0x180081a15  mov     rax, [rbp+140h+arg_90]
0x180081a1c  mov     [rbp+140h+var_1C0], rax
0x180081a20  mov     rax, [rbp+140h+arg_30]
0x180081a27  mov     [rbp+140h+var_118], rax
0x180081a2b  mov     rax, [rbp+140h+arg_40]
0x180081a32  mov     [rbp+140h+var_F8], rax
0x180081a36  mov     rax, [rbp+140h+arg_48]
0x180081a3d  mov     [rbp+140h+var_C0], rax
0x180081a44  mov     rax, [rbp+140h+arg_50]
0x180081a4b  mov     [rbp+140h+var_A0], rax
0x180081a52  mov     rax, [rbp+140h+arg_60]
0x180081a59  mov     [rbp+140h+var_50], rax
0x180081a60  mov     rax, [rbp+140h+arg_70]
0x180081a67  mov     [rbp+140h+var_B0], rax
0x180081a6e  mov     rax, [rbp+140h+arg_80]
0x180081a75  mov     [rbp+140h+var_98], rax
0x180081a7c  mov     rax, [rbp+140h+arg_98]
0x180081a83  mov     [rbp+140h+var_E0], rdx
0x180081a87  xor     edx, edx
0x180081a89  mov     qword ptr [rbp+140h+var_48.data.data], rax
0x180081a90  mov     edi, edx
0x180081a92  mov     rax, [rbp+140h+arg_A8]
0x180081a99  mov     r12d, edx
0x180081a9c  mov     [rbp+140h+var_D8], r9
0x180081aa0  mov     esi, edx
0x180081aa2  mov     r9, [rbp+140h+arg_88]
0x180081aa9  mov     r14b, dl
0x180081aac  mov     [rbp+140h+var_188], rdx
0x180081ab0  mov     [rsp+240h+var_1C8], rdx
0x180081ab5  mov     [rbp+140h+var_100], rdx
0x180081ab9  mov     [rbp+140h+var_108], rdx
0x180081abd  mov     [rbp+140h+var_198], rdx
0x180081ac1  mov     [rbp+140h+var_178], rdx
0x180081ac5  mov     [rbp+140h+var_19D], dl
0x180081ac8  mov     [rbp+140h+var_1B0], edx
0x180081acb  mov     [rbp+140h+var_120], edx
0x180081ace  mov     [rbp+140h+var_160], edx
0x180081ad1  mov     [rbp+140h+var_110], rdx
0x180081ad5  mov     [rbp+140h+var_19E], dl
0x180081ad8  mov     edx, [rbp+140h+arg_28]
0x180081ade  mov     [rbp+140h+var_C8], rax
0x180081ae2  mov     [rbp+140h+var_168], r8
0x180081ae6  mov     [rbp+140h+var_B8], r10
0x180081aed  mov     [rbp+140h+var_1B8], r9
0x180081af1  mov     [rbp+140h+var_A8], r11
0x180081af8  mov     qword ptr [rbp+140h+var_170.LowPart], rbx
0x180081afc  movups  xmmword ptr [rbp+140h+var_90.Length], xmm0
0x180081b03  movups  xmmword ptr [rbp+140h+var_F0.Length], xmm1
0x180081b07  movups  xmmword ptr [rbp+140h+var_80.Length], xmm0
0x180081b0e  movups  xmmword ptr [rbp+140h+var_70.Length], xmm1
0x180081b15  movups  xmmword ptr [rbp+140h+var_60.Length], xmm0
0x180081b1c  movups  xmmword ptr [rbp+140h+var_158.MessageType], xmm1
0x180081b20  cmp     edx, 0Ah
0x180081b23  ja      short loc_180081B31
0x180081b25  lea     eax, [rbx+4Dh]
0x180081b28  mov     [rbp+140h+var_19F], 1
0x180081b2c  bt      eax, edx
0x180081b2f  jb      short loc_180081B35
0x180081b31  mov     [rbp+140h+var_19F], sil
0x180081b35  lea     eax, [rdx-3]
0x180081b38  cmp     eax, 2
0x180081b3b  jbe     short loc_180081B46
0x180081b3d  mov     [rbp+140h+var_1A0], sil
0x180081b41  cmp     edx, 8
0x180081b44  jnz     short loc_180081B4A
0x180081b46  mov     [rbp+140h+var_1A0], 1
0x180081b4a  mov     eax, [r8]
0x180081b4d  lea     rdx, aKerbcreatetoke_0; "KerbCreateTokenFromLogonTicket"
0x180081b54  sub     eax, 0Ah
0x180081b57  cmp     eax, 2
0x180081b5a  setbe   [rbp+140h+var_190]
0x180081b5e  xor     eax, eax
0x180081b60  mov     [r9], rax
0x180081b63  mov     [r10], rax
0x180081b66  mov     [r11], rax
0x180081b69  cmp     [rbp+140h+arg_20], al
0x180081b6f  jnz     loc_1800827D5
0x180081b75  xor     edx, edx; unsigned __int8
0x180081b77  mov     [rbp+140h+var_180], rax
0x180081b7b  cmp     dword ptr [r8], 0Ch
0x180081b7f  mov     [rsp+240h+var_1CF], al
0x180081b83  jnz     loc_180081D56
0x180081b89  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x180081b8e  mov     [rbp+140h+var_1A8], rax
0x180081b92  mov     r12, rax
0x180081b95  test    rax, rax
0x180081b98  jnz     loc_180081CE6
0x180081b9e  mov     edi, 0C000005Fh
0x180081ba3  mov     r15, [rbp+140h+var_1B8]
0x180081ba7  mov     rbx, [rbp+140h+var_1C0]
0x180081bab  mov     rsi, [rsp+240h+var_1C8]
0x180081bb0  lea     rcx, [rbp+140h+var_90]
0x180081bb7  call    KerbFreeString
0x180081bbc  lea     rcx, [rbp+140h+var_80]
0x180081bc3  call    KerbFreeString
0x180081bc8  lea     rcx, [rbp+140h+var_F0]
0x180081bcc  call    KerbFreeString
0x180081bd1  lea     rcx, [rbp+140h+var_70]
0x180081bd8  call    KerbFreeString
0x180081bdd  lea     rcx, [rbp+140h+var_60]
0x180081be4  call    KerbFreeString
0x180081be9  xor     r13d, r13d
0x180081bec  test    r14b, r14b
0x180081bef  jz      short loc_180081BFC
0x180081bf1  lea     rcx, [r12+50h]; CriticalSection
0x180081bf6  call    cs:__imp_RtlLeaveCriticalSection
0x180081bfc  test    r12, r12
0x180081bff  jz      short loc_180081C09
0x180081c01  mov     rcx, r12; struct _KERB_LOGON_SESSION *
0x180081c04  call    ?KerbDereferenceLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbDereferenceLogonSession(_KERB_LOGON_SESSION *)
0x180081c09  test    edi, edi
0x180081c0b  jns     short loc_180081C65
0x180081c0d  mov     rcx, [rbp+140h+var_178]
0x180081c11  test    rcx, rcx
0x180081c14  jz      short loc_180081C1B
0x180081c16  call    KerbFree
0x180081c1b  mov     rdx, [r15]
0x180081c1e  test    rdx, rdx
0x180081c21  jz      short loc_180081C38
0x180081c23  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180081c2a  xor     ecx, ecx
0x180081c2c  mov     rax, [rax+40h]
0x180081c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081c35  mov     [r15], r13
0x180081c38  lea     rcx, [rbx+8]
0x180081c3c  call    KerbFreeString
0x180081c41  lea     rcx, [rbx+18h]
0x180081c45  call    KerbFreeString
0x180081c4a  lea     rcx, [rbx+78h]
0x180081c4e  call    KerbFreeString
0x180081c53  mov     rcx, [rbx+48h]
0x180081c57  test    rcx, rcx
0x180081c5a  jz      short loc_180081C65
0x180081c5c  call    KerbFree
0x180081c61  mov     [rbx+48h], r13
0x180081c65  mov     rdx, [rbp+140h+var_188]
0x180081c69  test    rdx, rdx
0x180081c6c  jz      short loc_180081C78
0x180081c6e  mov     ecx, 33h ; '3'
0x180081c73  call    KerbFreeData
0x180081c78  cmp     [rbp+140h+var_19D], r13b
0x180081c7c  jz      short loc_180081C8B
0x180081c7e  test    rsi, rsi
0x180081c81  jz      short loc_180081C8B
0x180081c83  mov     rcx, rsi
0x180081c86  call    KerbFree
0x180081c8b  mov     rdx, [rbp+140h+var_108]
0x180081c8f  test    rdx, rdx
0x180081c92  jz      short loc_180081C9E
0x180081c94  mov     ecx, 1
0x180081c99  call    KerbFreeData
0x180081c9e  mov     rcx, [rbp+140h+var_198]
0x180081ca2  test    rcx, rcx
0x180081ca5  jz      short loc_180081CAC
0x180081ca7  call    KerbFree
0x180081cac  mov     rcx, qword ptr [rbp+140h+var_158.LogonDomainName.Length]
0x180081cb0  test    rcx, rcx
0x180081cb3  jz      short loc_180081CBA
0x180081cb5  call    KerbFree
0x180081cba  mov     eax, edi
0x180081cbc  mov     rcx, [rbp+140h+var_38]
0x180081cc3  xor     rcx, rsp; StackCookie
0x180081cc6  call    __security_check_cookie
0x180081ccb  mov     rbx, [rsp+240h+arg_8]
0x180081cd3  add     rsp, 210h
0x180081cda  pop     r15
0x180081cdc  pop     r14
0x180081cde  pop     r13
0x180081ce0  pop     r12
0x180081ce2  pop     rdi
0x180081ce3  pop     rsi
0x180081ce4  pop     rbp
0x180081ce5  retn
0x180081ce6  lea     rcx, [rax+50h]; CriticalSection
0x180081cea  call    cs:__imp_RtlEnterCriticalSection
0x180081cf0  lea     rdx, [r12+88h]; struct _UNICODE_STRING *
0x180081cf8  mov     r14b, 1
0x180081cfb  lea     rcx, [rbp+140h+var_90]; struct _UNICODE_STRING *
0x180081d02  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180081d07  mov     edi, eax
0x180081d09  test    eax, eax
0x180081d0b  js      loc_180081BA3
0x180081d11  test    r15, r15
0x180081d14  jz      loc_180081DA2
0x180081d1a  test    byte ptr [r15+0A4h], 10h
0x180081d22  jz      short loc_180081DA2
0x180081d24  lea     r9, aKerbcreatetoke_2; "KerbCreateTokenFromLogonTicket using Lo"...
0x180081d2b  mov     r8d, 1081h
0x180081d31  lea     rdx, aKerbcreatetoke_0; "KerbCreateTokenFromLogonTicket"
0x180081d38  mov     ecx, 3
0x180081d3d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180081d42  mov     cl, r14b
0x180081d45  lea     rdi, [r15+0D0h]
0x180081d4c  mov     [rsp+240h+var_1CF], cl
0x180081d50  mov     [rbp+140h+var_180], rdi
0x180081d54  jmp     short loc_180081DA8
0x180081d56  lea     rcx, [rbp+140h+var_170]; struct _LUID *
0x180081d5a  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x180081d5f  mov     [rbp+140h+var_1A8], rax
0x180081d63  mov     r12, rax
0x180081d66  test    rax, rax
0x180081d69  jz      loc_180081B9E
0x180081d6f  lea     rcx, [rbp+140h+var_90]; struct _UNICODE_STRING *
0x180081d76  call    ?KerbGetOurDomainName@@YAJPEAU_UNICODE_STRING@@@Z; KerbGetOurDomainName(_UNICODE_STRING *)
0x180081d7b  mov     edi, eax
0x180081d7d  test    eax, eax
0x180081d7f  js      loc_180081BA3
0x180081d85  lea     rcx, [r12+50h]; CriticalSection
0x180081d8a  call    cs:__imp_RtlEnterCriticalSection
0x180081d90  mov     rdi, [rbp+140h+var_180]
0x180081d94  mov     r14b, 1
0x180081d97  mov     esi, [rbp+140h+var_170.HighPart]
0x180081d9a  mov     cl, dil
0x180081d9d  mov     ebx, [rbp+140h+var_170.LowPart]
0x180081da0  jmp     short loc_180081DA8
0x180081da2  mov     cl, sil
0x180081da5  mov     rdi, rsi
0x180081da8  cmp     byte ptr cs:?KerbGlobalRoles@@3U_KerberosSystemRole@@A, 0; _KerberosSystemRole KerbGlobalRoles
0x180081daf  jz      short loc_180081E10
0x180081db1  cmp     [r12+40h], ebx
0x180081db6  jnz     short loc_180081DBF
0x180081db8  cmp     [r12+44h], esi
0x180081dbd  jz      short loc_180081DD2
0x180081dbf  cmp     dword ptr [r12+40h], 3E4h
0x180081dc8  jnz     short loc_180081E10
0x180081dca  cmp     dword ptr [r12+44h], 0
0x180081dd0  jnz     short loc_180081E10
0x180081dd2  mov     eax, [r15+134h]
0x180081dd9  dec     eax
0x180081ddb  test    eax, 0FFFFFFFDh
0x180081de0  jnz     short loc_180081E10
0x180081de2  mov     eax, 0C000006Dh
0x180081de7  lea     r9, aRejectDesLogon; "reject DES logon ticket: %#x\n"
0x180081dee  mov     edi, eax
0x180081df0  mov     r8d, 10AEh
0x180081df6  mov     dword ptr [rsp+240h+var_220], eax
0x180081dfa  lea     rdx, aKerbcreatetoke_0; "KerbCreateTokenFromLogonTicket"
0x180081e01  mov     ecx, 1
0x180081e06  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180081e0b  jmp     loc_180081BA3
0x180081e10  xor     ebx, ebx
0x180081e12  test    rdi, rdi
0x180081e15  jnz     short loc_180081E22
0x180081e17  lea     esi, [rbx+1]
0x180081e1a  mov     r12d, esi
0x180081e1d  jmp     loc_180081FCA
0x180081e22  mov     r14, [rbp+140h+var_1A8]
0x180081e26  mov     r12d, ebx
0x180081e29  mov     esi, ebx
0x180081e2b  mov     rbx, r15
0x180081e2e  test    cl, cl
0x180081e30  jnz     short loc_180081E3A
0x180081e32  mov     rcx, rdi; struct _KERB_ENCRYPTION_KEY *
0x180081e35  call    ?KerbRevealKey@@YAXPEAU_KERB_ENCRYPTION_KEY@@@Z; KerbRevealKey(_KERB_ENCRYPTION_KEY *)
0x180081e3a  mov     [rbp+140h+var_1B0], 0
0x180081e41  lea     r8, [rbp+140h+var_1B0]
0x180081e45  mov     rcx, [rdi]
0x180081e48  lea     rdx, [rbx+110h]
0x180081e4f  mov     [rsp+240h+var_218], r8
0x180081e54  xor     r9d, r9d
0x180081e57  lea     r8, [rbp+140h+var_188]
0x180081e5b  mov     [rsp+240h+var_220], r8
0x180081e60  mov     r8, rdi
0x180081e63  mov     rax, [rcx]
0x180081e66  mov     rax, [rax+38h]
0x180081e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e6f  xor     ebx, ebx
0x180081e71  mov     edi, eax
0x180081e73  cmp     [rsp+240h+var_1CF], bl
0x180081e77  jnz     short loc_180081E82
0x180081e79  mov     rcx, [rbp+140h+var_180]; struct _KERB_ENCRYPTION_KEY *
0x180081e7d  call    ?KerbHideKey@@YAXPEAU_KERB_ENCRYPTION_KEY@@@Z; KerbHideKey(_KERB_ENCRYPTION_KEY *)
0x180081e82  test    edi, edi
0x180081e84  js      loc_1800827B0
0x180081e8a  mov     rcx, [rbp+140h+var_168]
0x180081e8e  mov     eax, [rcx]
0x180081e90  sub     eax, 0Ah
  ... truncated ...
```
