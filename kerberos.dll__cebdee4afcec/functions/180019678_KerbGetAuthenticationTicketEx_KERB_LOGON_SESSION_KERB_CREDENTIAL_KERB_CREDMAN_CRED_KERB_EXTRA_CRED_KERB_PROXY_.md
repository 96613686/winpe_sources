# KerbGetAuthenticationTicketEx(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_EXTRA_CRED *,_KERB_PROXY_LOGON_CRED *,uchar,ulong,uchar *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_KERB_INTERNAL_NAME *,ulong,ulong,ulong,uchar,_KERB_TICKET_CACHE_ENTRY * *,_KERB_ENCRYPTION_KEY *,_UNICODE_STRING *,int *,_KDC_PROXY_CACHE_ENTRY * *)

- ea: `0x180019678`
- end: `0x18001db8c`
- name: `?KerbGetAuthenticationTicketEx@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_EXTRA_CRED@@PEAU_KERB_PROXY_LOGON_CRED@@EKPEAEPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@6KKKEPEAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_ENCRYPTION_KEY@@7PEAHPEAPEAU_KDC_PROXY_CACHE_ENTRY@@@Z`
- size: `17684`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, struct _KERB_CREDMAN_CRED *, struct _KERB_EXTRA_CRED *, struct _KERB_PROXY_LOGON_CRED *, unsigned __int8, unsigned int, unsigned __int8 *, struct _KERB_INTERNAL_NAME *, PCUNICODE_STRING String1, struct _KERB_INTERNAL_NAME *, unsigned int, unsigned int, unsigned int, char, struct _KERB_TICKET_CACHE_ENTRY **, struct _KERB_ENCRYPTION_KEY *, struct _UNICODE_STRING *, int *, struct _KDC_PROXY_CACHE_ENTRY **)`
- caller_count: `4`
- callee_count: `103`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180018de8`
- `0x180019678`
- `0x1800545ec`
- `0x180058f14`

## callees

- `0x180001754`
- `0x1800017e0`
- `0x1800018e0`
- `0x180001928`
- `0x18000202c`
- `0x180002140`
- `0x180004660`
- `0x180004760`
- `0x180005c90`
- `0x180006350`
- `0x1800063e8`
- `0x1800068d0`
- `0x180006920`
- `0x1800069a0`
- `0x1800069e0`
- `0x1800088c4`
- `0x180008ec0`
- `0x1800093f0`
- `0x180009744`
- `0x180009afc`
- `0x18000a630`
- `0x18000d0d0`
- `0x18000d9e4`
- `0x18000e020`
- `0x18000e298`
- `0x18000efd0`
- `0x180010d70`
- `0x180010e90`
- `0x180011150`
- `0x1800113f0`
- `0x1800120f4`
- `0x180014380`
- `0x180014b40`
- `0x180014c50`
- `0x180014dc0`
- `0x180016550`
- `0x180018cf0`
- `0x180019678`
- `0x18001e268`
- `0x18001e570`
- `0x18001fbc0`
- `0x1800210e0`
- `0x180029360`
- `0x180029c50`
- `0x180029ec8`
- `0x18002b740`
- `0x18002d228`
- `0x1800301ec`
- `0x180030dac`
- `0x180032964`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ba54`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bb2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c0dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c23c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ba54`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bb2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c0dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c23c`
- `ntdll!RtlEqualUnicodeString` at `0x180019a00`
- `ntdll!RtlEqualUnicodeString` at `0x18001b682`
- `ntdll!RtlEqualUnicodeString` at `0x18001b7b8`
- `ntdll!RtlEqualUnicodeString` at `0x180019a00`
- `ntdll!RtlEqualUnicodeString` at `0x18001b682`
- `ntdll!RtlEqualUnicodeString` at `0x18001b7b8`
- `ntdll!RtlInitUnicodeString` at `0x180019980`
- `ntdll!RtlInitUnicodeString` at `0x180019980`
- `ntdll!WinSqmSetDWORD` at `0x18001d31a`
- `ntdll!WinSqmSetDWORD` at `0x18001d331`
- `ntdll!WinSqmSetDWORD` at `0x18001d31a`
- `ntdll!WinSqmSetDWORD` at `0x18001d331`
- `ntdll!RtlEnterCriticalSection` at `0x180019a4e`
- `ntdll!RtlEnterCriticalSection` at `0x180019b68`
- `ntdll!RtlEnterCriticalSection` at `0x18001a5b5`
- `ntdll!RtlEnterCriticalSection` at `0x18001b50a`
- `ntdll!RtlEnterCriticalSection` at `0x18001bb51`
- `ntdll!RtlEnterCriticalSection` at `0x18001d442`
- `ntdll!RtlEnterCriticalSection` at `0x180019a4e`
- `ntdll!RtlEnterCriticalSection` at `0x180019b68`
- `ntdll!RtlEnterCriticalSection` at `0x18001a5b5`
- `ntdll!RtlEnterCriticalSection` at `0x18001b50a`
- `ntdll!RtlEnterCriticalSection` at `0x18001bb51`
- `ntdll!RtlEnterCriticalSection` at `0x18001d442`
- `ntdll!RtlLeaveCriticalSection` at `0x180019a8a`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b533`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c071`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c7b1`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d434`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d521`
- `ntdll!RtlLeaveCriticalSection` at `0x18001da04`
- `ntdll!RtlLeaveCriticalSection` at `0x180019a8a`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b533`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c071`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c7b1`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d434`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d521`
- `ntdll!RtlLeaveCriticalSection` at `0x18001da04`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18001d46f`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18001d496`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18001d945`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18001d957`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18001d46f`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18001d496`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18001d945`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18001d957`
- `KerbClientShared!KerbClientDuplicateStoredCred` at `0x18001c516`
- `KerbClientShared!KerbClientDuplicateStoredCred` at `0x18001c53b`
- `KerbClientShared!KerbClientDuplicateStoredCred` at `0x18001c516`
- `KerbClientShared!KerbClientDuplicateStoredCred` at `0x18001c53b`
- `CRYPT32!CertVerifyTimeValidity` at `0x18001a0b4`
- `CRYPT32!CertVerifyTimeValidity` at `0x18001a0b4`
- `CRYPT32!CertCompareCertificateName` at `0x18001a060`
- `CRYPT32!CertCompareCertificateName` at `0x18001a060`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001a9df`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001a9df`
- `CRYPT32!CertFreeCertificateContext` at `0x18001a46d`
- `CRYPT32!CertFreeCertificateContext` at `0x18001d91f`
- `CRYPT32!CertFreeCertificateContext` at `0x18001a46d`
- `CRYPT32!CertFreeCertificateContext` at `0x18001d91f`

## string_xrefs

- `0x18001d698`: `Failed to create crypto policy`
- `0x18001a3fe`: `AS-REQ to claims capable domain %wZ (domain cache)\n`
- `0x18001a580`: `Failed to create explicit armor ap-req for AS-REQ: %#x, Status %#x\n`
- `0x18001b2a3`: `onecore\ds\security\protocols\kerberos\client2\logonapi.cxx`
- `0x18001c8ea`: `onecore\ds\security\protocols\kerberos\client2\logonapi.cxx`
- `0x18001d12d`: `onecore\ds\security\protocols\kerberos\client2\logonapi.cxx`
- `0x18001cac6`: `Failed to create FAST armored AS-REQ: %#x\n`
- `0x18001cb50`: `Discovered a linked dmsa and successfully acquired a TGT`
- `0x18001cc8f`: `KerbGetAuthenticationTicket for service in realm %wZ\n`
- `0x18001cf83`: `KerbGetAuthenticationTicket for service in realm %wZ\n`
- `0x18001cf07`: `KerbGetAuthenticationTicket no preauth, already retried: %#x\n`
- `0x18001cfc1`: `Couldn't read realm in error message`
- `0x18001c702`: `Requested freshess token but got ticket.  User has smartcard preauth and preauth not required\n`
- `0x18001d602`: `KerbGetAuthenticationTicketEx Failed to compare realm names of ticket and reply: %#x Status %#x\n`
- `0x18001d279`: `failed to cache claims capable for domain %wZ\n`
- `0x18001c783`: `client reprobes claims for domain %wZ (domain cache)\n`
- `0x18001c45f`: `failed to update names in primary credentials: 0x%x`
- `0x18001c6df`: `Retrying AS after trying to cache time invalid ticket\n`

## pseudocode

```c
__int64 __fastcall KerbGetAuthenticationTicketEx(
        struct _KERB_LOGON_SESSION *a1,
        struct _KERB_CREDENTIAL *a2,
        struct _KERB_CREDMAN_CRED *a3,
        struct _KERB_EXTRA_CRED *a4,
        struct _KERB_PROXY_LOGON_CRED *a5,
        unsigned __int8 a6,
        unsigned int a7,
        unsigned __int8 *a8,
        struct _KERB_INTERNAL_NAME *a9,
        PCUNICODE_STRING String1,
        struct _KERB_INTERNAL_NAME *a11,
        unsigned int a12,
        unsigned int a13,
        unsigned int a14,
        char a15,
        struct _KERB_TICKET_CACHE_ENTRY **a16,
        struct _KERB_ENCRYPTION_KEY *a17,
        struct _UNICODE_STRING *a18,
        int *a19,
        struct _KDC_PROXY_CACHE_ENTRY **a20)
{
  struct _KERB_INTERNAL_NAME *v22; // r13
  bool v23; // r14
  _DWORD *v24; // r12
  unsigned __int8 v25; // si
  __int64 v26; // rcx
  int S4UClientRealm; // ebx
  int ExtendedPolicies; // edi
  int v29; // ebx
  int v30; // edi
  unsigned int v31; // ecx
  struct _UNICODE_STRING *v32; // r13
  Ntlmless::Kerberos *v33; // rcx
  __int64 v34; // rdx
  struct _KERB_CREDENTIAL *v35; // rbx
  struct _KERB_PRIMARY_CREDENTIAL *v36; // rcx
  int v37; // r14d
  const char *v38; // r9
  __int64 v39; // r8
  bool v40; // bl
  struct _UNICODE_STRING *v41; // rdi
  bool v42; // r15
  char *v43; // rax
  struct _CRYPTOAPI_BLOB *v44; // rdx
  unsigned __int8 v45; // dl
  unsigned __int8 v46; // al
  char v47; // r12
  unsigned int v48; // r15d
  char v49; // di
  unsigned __int8 v50; // bl
  struct _KERB_TICKET_CACHE_ENTRY *v51; // rax
  int v52; // r8d
  struct _UNICODE_STRING *v53; // rbx
  __int64 v54; // r8
  const char *v55; // r9
  const char *v56; // r9
  __int64 v57; // r8
  int v58; // r8d
  int v59; // eax
  int v60; // eax
  int v61; // r8d
  const char *v62; // r9
  __int64 v63; // r8
  Ntlmless::Kerberos *v64; // rcx
  Ntlmless::Kerberos *v65; // rcx
  __int64 *v66; // rax
  _QWORD *v67; // rbx
  struct KERB_KDC_REQUEST_preauth_data_s *v68; // r8
  struct _KERB_CREDENTIAL *v69; // r9
  const char *v70; // r9
  __int64 v71; // r8
  PWSTR Buffer; // rax
  PWSTR v73; // rax
  const CERT_CONTEXT *v74; // rcx
  _QWORD *v75; // rbx
  _QWORD *v76; // rcx
  _OWORD *v77; // rax
  _QWORD *v78; // rdi
  _QWORD *v79; // rcx
  _OWORD *v80; // rax
  _OWORD *v81; // rbx
  unsigned int v82; // eax
  unsigned int v83; // edi
  void *v84; // rax
  const void *v85; // rax
  HLOCAL v86; // rbx
  int v87; // eax
  struct PKERB_HOST_ADDRESSES_s *v88; // rbx
  __int64 v89; // rdx
  unsigned int v90; // edi
  unsigned __int8 v91; // r15
  int v92; // r8d
  int v93; // eax
  unsigned int v94; // ebx
  int v95; // eax
  struct _KERB_LOGON_SESSION *v96; // r12
  __int64 v97; // r8
  __int64 v98; // rax
  int v99; // eax
  int v100; // eax
  int v101; // ecx
  int v102; // eax
  int v103; // r8d
  unsigned int v104; // r8d
  struct _KERB_CREDENTIAL *v105; // r9
  char v106; // di
  int v107; // eax
  struct _KERB_LOGON_SESSION *v108; // rbx
  int PreAuthDataForRealm; // eax
  struct _KERB_CREDENTIAL *v110; // r9
  struct _UNICODE_STRING *v111; // r8
  int v112; // ecx
  PWSTR *p_Buffer; // rbx
  __int64 v114; // r9
  __int64 v115; // r9
  __int64 v116; // r10
  int v117; // eax
  int v118; // eax
  struct _KERB_STORED_CREDENTIAL **v119; // rbx
  int v120; // eax
  const char *v121; // r9
  __int64 v122; // r8
  __int64 v123; // rdx
  struct _KERB_ENCRYPTION_KEY *KeyFromList; // r15
  int v125; // eax
  int v126; // ebx
  int v127; // edx
  struct _KERB_ENCRYPTION_KEY *v128; // rcx
  UNICODE_STRING *v129; // rax
  PWSTR v130; // rcx
  struct _KERB_ENCRYPTION_KEY *v131; // rax
  int v132; // r8d
  unsigned int v133; // r15d
  int v134; // edx
  struct _KERB_ENCRYPTION_KEY *v135; // rcx
  __int64 v136; // rax
  int v137; // eax
  Ntlmless::Kerberos *v138; // rcx
  int v139; // ebx
  struct KERB_PA_DATA *PreAuthDataEntry; // rax
  struct KERB_ENCRYPTED_KDC_REPLY *v141; // r8
  __int64 v142; // r9
  int v143; // eax
  __int64 v144; // rax
  int v145; // r9d
  struct _UNICODE_STRING *v146; // rbx
  int updated; // eax
  struct _KERB_LOGON_SESSION *v148; // rbx
  int v149; // eax
  unsigned __int8 v150; // dl
  _DWORD *v151; // rcx
  const struct _KERB_STORED_CREDENTIAL *v152; // rcx
  const struct _KERB_STORED_CREDENTIAL *v153; // rcx
  void *v154; // rax
  struct _KERB_TICKET_CACHE *v155; // r8
  int v156; // eax
  int v157; // r8d
  unsigned __int8 v158; // al
  int v159; // eax
  int v160; // r8d
  const char *v161; // r9
  __int64 v162; // r8
  int v163; // r8d
  __int64 v164; // r8
  const UNICODE_STRING *v165; // r15
  const char *v166; // r9
  __int64 v167; // r8
  int v168; // r8d
  struct _KERB_ENCRYPTION_KEY *v169; // rax
  struct _KERB_LOGON_SESSION *v170; // r15
  struct _KERB_LOGON_SESSION *LogonSession; // rax
  struct _KERB_LOGON_SESSION *v172; // r13
  char *v173; // r8
  unsigned int v174; // ebx
  struct _KERB_STORED_CREDENTIAL *v175; // rcx
  struct _KERB_STORED_CREDENTIAL *v176; // rcx
  int v177; // r8d
  __int64 v178; // rdx
  __int64 v179; // rax
  int v180; // r9d
  const char *v181; // r9
  __int64 v182; // r8
  int v183; // r8d
  __int64 v184; // rax
  int v185; // r8d
  __int64 v186; // rax
  int v187; // r8d
  struct PKERB_HOST_ADDRESSES_s *v188; // rsi
  __int64 v189; // rcx
  struct PKERB_HOST_ADDRESSES_s *v190; // rbx
  PEVENT_DATA_DESCRIPTOR v192; // [rsp+20h] [rbp-100h]
  PEVENT_DATA_DESCRIPTOR v193; // [rsp+20h] [rbp-100h]
  struct _UNICODE_STRING *v194; // [rsp+28h] [rbp-F8h]
  UNICODE_STRING *v195; // [rsp+28h] [rbp-F8h]
  struct KERB_TICKET *v196; // [rsp+38h] [rbp-E8h]
  char v197; // [rsp+A0h] [rbp-80h]
  unsigned int v198; // [rsp+B0h] [rbp-70h]
  char v199; // [rsp+B4h] [rbp-6Ch]
  char v200; // [rsp+B5h] [rbp-6Bh]
  unsigned __int8 v201; // [rsp+B6h] [rbp-6Ah]
  int v202; // [rsp+B8h] [rbp-68h] BYREF
  bool v203; // [rsp+BCh] [rbp-64h]
  _DWORD *v204; // [rsp+C0h] [rbp-60h]
  unsigned __int8 v205; // [rsp+C8h] [rbp-58h]
  char v206; // [rsp+C9h] [rbp-57h]
  unsigned __int8 v207; // [rsp+CAh] [rbp-56h] BYREF
  unsigned __int8 IsDomainClaimsCapableFromCache; // [rsp+CBh] [rbp-55h]
  unsigned __int8 v209; // [rsp+CCh] [rbp-54h]
  unsigned __int8 v210; // [rsp+CDh] [rbp-53h] BYREF
  char v211; // [rsp+CEh] [rbp-52h]
  unsigned __int8 v212; // [rsp+CFh] [rbp-51h]
  int v213; // [rsp+D0h] [rbp-50h]
  PCUNICODE_STRING v214; // [rsp+D8h] [rbp-48h]
  struct KERB_ERROR *v215; // [rsp+E0h] [rbp-40h] BYREF
  bool v216; // [rsp+E8h] [rbp-38h]
  unsigned __int8 v217; // [rsp+E9h] [rbp-37h]
  unsigned __int8 v218; // [rsp+EAh] [rbp-36h] BYREF
  unsigned __int8 v219; // [rsp+EBh] [rbp-35h]
  _BYTE v220[20]; // [rsp+ECh] [rbp-34h] BYREF
  int v221; // [rsp+100h] [rbp-20h]
  struct KERB_EXT_ERROR *v222; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v223[8]; // [rsp+110h] [rbp-10h] BYREF
  bool v224; // [rsp+118h] [rbp-8h] BYREF
  struct _UNICODE_STRING *v225; // [rsp+120h] [rbp+0h]
  int v226; // [rsp+128h] [rbp+8h] BYREF
  int v227; // [rsp+12Ch] [rbp+Ch] BYREF
  int v228; // [rsp+130h] [rbp+10h] BYREF
  unsigned int v229; // [rsp+134h] [rbp+14h] BYREF
  UNICODE_STRING String2; // [rsp+138h] [rbp+18h] BYREF
  unsigned int size; // [rsp+148h] [rbp+28h]
  int size_4; // [rsp+14Ch] [rbp+2Ch] BYREF
  unsigned int v233; // [rsp+150h] [rbp+30h] BYREF
  unsigned int v234[2]; // [rsp+158h] [rbp+38h] BYREF
  int v235; // [rsp+160h] [rbp+40h] BYREF
  struct _KERB_LOGON_SESSION *v236; // [rsp+168h] [rbp+48h]
  union _LARGE_INTEGER v237; // [rsp+170h] [rbp+50h] BYREF
  struct KERB_ENCRYPTED_KDC_REPLY *v238; // [rsp+178h] [rbp+58h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v239; // [rsp+180h] [rbp+60h] BYREF
  int v240; // [rsp+188h] [rbp+68h] BYREF
  struct _KERB_INTERNAL_NAME *v241; // [rsp+190h] [rbp+70h]
  _DWORD *v242; // [rsp+198h] [rbp+78h]
  int v243; // [rsp+1A0h] [rbp+80h] BYREF
  unsigned int v244; // [rsp+1A4h] [rbp+84h]
  int v245; // [rsp+1A8h] [rbp+88h]
  struct KERB_KDC_REQUEST_preauth_data_s **v246; // [rsp+1B0h] [rbp+90h]
  __int64 v247; // [rsp+1B8h] [rbp+98h] BYREF
  struct KrbFastResponse *v248; // [rsp+1C0h] [rbp+A0h] BYREF
  union _LARGE_INTEGER Time; // [rsp+1C8h] [rbp+A8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1D0h] [rbp+B0h] BYREF
  struct KERB_KDC_REQUEST_preauth_data_s **v251; // [rsp+1D8h] [rbp+B8h]
  struct KerbKeyAgreement *v252; // [rsp+1E0h] [rbp+C0h] BYREF
  int v253; // [rsp+1E8h] [rbp+C8h] BYREF
  int v254; // [rsp+1ECh] [rbp+CCh]
  unsigned int v255; // [rsp+1F0h] [rbp+D0h] BYREF
  int v256; // [rsp+1F4h] [rbp+D4h]
  struct _KERB_MIT_REALM *v257; // [rsp+1F8h] [rbp+D8h] BYREF
  PUNICODE_STRING DestinationString; // [rsp+200h] [rbp+E0h]
  struct PKERB_HOST_ADDRESSES_s *v259; // [rsp+208h] [rbp+E8h] BYREF
  UNICODE_STRING v260; // [rsp+210h] [rbp+F0h] BYREF
  struct _KERB_CREDENTIAL *v261; // [rsp+220h] [rbp+100h]
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+228h] [rbp+108h]
  KerberosCryptoPolicy *v263; // [rsp+230h] [rbp+110h] BYREF
  struct _KERB_ENCRYPTION_KEY *v264[2]; // [rsp+238h] [rbp+118h] BYREF
  int *v265; // [rsp+248h] [rbp+128h]
  void *Src; // [rsp+250h] [rbp+130h]
  _QWORD *v267; // [rsp+258h] [rbp+138h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+260h] [rbp+140h]
  __int64 v269; // [rsp+268h] [rbp+148h] BYREF
  int v270; // [rsp+270h] [rbp+150h] BYREF
  __int128 v271; // [rsp+278h] [rbp+158h] BYREF
  __int128 v272; // [rsp+288h] [rbp+168h]
  __int64 v273; // [rsp+298h] [rbp+178h]
  __int64 v274; // [rsp+2A0h] [rbp+180h] BYREF
  __int64 v275; // [rsp+2A8h] [rbp+188h] BYREF
  struct _KERB_STORED_CREDENTIAL *v276; // [rsp+2B0h] [rbp+190h] BYREF
  struct _KDC_PROXY_CACHE_ENTRY **v277; // [rsp+2B8h] [rbp+198h]
  void *v278; // [rsp+2C0h] [rbp+1A0h]
  struct _KERB_TICKET_CACHE_ENTRY *v279; // [rsp+2C8h] [rbp+1A8h] BYREF
  struct _KERB_PROXY_LOGON_CRED *v280; // [rsp+2D0h] [rbp+1B0h]
  struct _KERB_EXTRA_CRED *v281; // [rsp+2D8h] [rbp+1B8h]
  struct _KERB_CREDMAN_CRED *v282; // [rsp+2E0h] [rbp+1C0h]
  struct _KERB_TICKET_CACHE_ENTRY **v283; // [rsp+2E8h] [rbp+1C8h]
  struct _KERB_STORED_CREDENTIAL *v284; // [rsp+2F0h] [rbp+1D0h] BYREF
  __int64 v285; // [rsp+2F8h] [rbp+1D8h] BYREF
  __int64 v286; // [rsp+300h] [rbp+1E0h]
  struct _KERB_ENCRYPTION_KEY *v287; // [rsp+308h] [rbp+1E8h]
  union _LARGE_INTEGER v288; // [rsp+310h] [rbp+1F0h] BYREF
  struct PKERB_HOST_ADDRESSES_s *v289; // [rsp+318h] [rbp+1F8h]
  struct _KERB_INTERNAL_NAME *v290; // [rsp+320h] [rbp+200h] BYREF
  UNICODE_STRING v291; // [rsp+328h] [rbp+208h] BYREF
  unsigned int v292[4]; // [rsp+338h] [rbp+218h] BYREF
  unsigned __int8 *v293; // [rsp+348h] [rbp+228h] BYREF
  _QWORD *v294; // [rsp+350h] [rbp+230h]
  unsigned __int64 v295; // [rsp+358h] [rbp+238h] BYREF
  struct _KERB_LOGON_SESSION *v296; // [rsp+360h] [rbp+240h]
  _OWORD v297[2]; // [rsp+368h] [rbp+248h] BYREF
  __int64 v298; // [rsp+388h] [rbp+268h]
  _QWORD v299[2]; // [rsp+390h] [rbp+270h] BYREF
  struct _UNICODE_STRING v300; // [rsp+3A0h] [rbp+280h] BYREF
  UNICODE_STRING *p_String2; // [rsp+3B0h] [rbp+290h] BYREF
  int v302; // [rsp+3B8h] [rbp+298h]
  __int64 v303; // [rsp+3C0h] [rbp+2A0h] BYREF
  int v304; // [rsp+3C8h] [rbp+2A8h]
  struct _UNICODE_STRING v305; // [rsp+3E0h] [rbp+2C0h] BYREF
  __int64 v306; // [rsp+3F0h] [rbp+2D0h] BYREF
  __int128 v307; // [rsp+3F8h] [rbp+2D8h] BYREF
  __int128 v308; // [rsp+408h] [rbp+2E8h]
  __int64 v309; // [rsp+418h] [rbp+2F8h]
  _OWORD v310[2]; // [rsp+420h] [rbp+300h] BYREF
  __int64 v311; // [rsp+440h] [rbp+320h]
  _WORD v312[2]; // [rsp+450h] [rbp+330h] BYREF
  int v313; // [rsp+454h] [rbp+334h]
  int v314; // [rsp+458h] [rbp+338h]
  HLOCAL hMem; // [rsp+460h] [rbp+340h] BYREF
  __int16 v316; // [rsp+468h] [rbp+348h] BYREF
  int v317; // [rsp+470h] [rbp+350h]
  int *v318; // [rsp+478h] [rbp+358h]
  _BYTE v319[16]; // [rsp+480h] [rbp+360h] BYREF
  char v320[8]; // [rsp+490h] [rbp+370h] BYREF
  _BYTE v321[30]; // [rsp+498h] [rbp+378h] BYREF
  char v322[14]; // [rsp+4B6h] [rbp+396h] BYREF
  char v323[16]; // [rsp+4C4h] [rbp+3A4h] BYREF
  UCHAR pbBuffer[4]; // [rsp+4D4h] [rbp+3B4h] BYREF
  _QWORD v325[7]; // [rsp+4D8h] [rbp+3B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v326; // [rsp+510h] [rbp+3F0h] BYREF
  __int64 *v327; // [rsp+530h] [rbp+410h]
  __int64 v328; // [rsp+538h] [rbp+418h]
  unsigned int *v329; // [rsp+540h] [rbp+420h]
  __int64 v330; // [rsp+548h] [rbp+428h]
  unsigned __int8 *v331; // [rsp+550h] [rbp+430h]
  __int64 v332; // [rsp+558h] [rbp+438h]
  bool *v333; // [rsp+560h] [rbp+440h]
  __int64 v334; // [rsp+568h] [rbp+448h]
  _BYTE *v335; // [rsp+570h] [rbp+450h]
  __int64 v336; // [rsp+578h] [rbp+458h]
  unsigned __int8 *v337; // [rsp+580h] [rbp+460h]
  __int64 v338; // [rsp+588h] [rbp+468h]

  v281 = a4;
  v282 = a3;
  v261 = a2;
  v236 = a1;
  v280 = a5;
  v241 = a11;
  size = a7;
  Src = a8;
  v22 = a9;
  v214 = String1;
  v283 = a16;
  v287 = a17;
  DestinationString = a18;
  v265 = a19;
  v277 = a20;
  v23 = 0;
  v226 = 0;
  v202 = 0;
  memset_0(v312, 0, 0xC0u);
  *(_QWORD *)&v220[12] = 0;
  v238 = 0;
  v279 = 0;
  v288.QuadPart = 0;
  v274 = 0;
  v275 = 0;
  v285 = 0;
  v286 = 0;
  v220[5] = 0;
  pCertContext = 0;
  v215 = 0;
  v246 = 0;
  v237.QuadPart = 0;
  v257 = 0;
  v290 = 0;
  v222 = 0;
  v271 = 0;
  v272 = 0;
  v273 = 0;
  v289 = 0;
  v259 = 0;
  v300 = 0;
  v270 = 0;
  v252 = 0;
  v305 = 0;
  v24 = 0;
  v220[4] = 0;
  v295 = 0;
  v239 = 0;
  memset(v310, 0, sizeof(v310));
  v311 = 0;
  memset(v297, 0, sizeof(v297));
  v298 = 0;
  v307 = 0;
  v308 = 0;
  v309 = 0;
  *(_OWORD *)v292 = 0;
  v293 = 0;
  v248 = 0;
  v269 = 0;
  v233 = 0;
  SystemTimeAsFileTime = 0;
  Time.QuadPart = 0;
  v299[0] = a1;
  v299[1] = a2;
  v296 = 0;
  v276 = 0;
  v284 = 0;
  v278 = 0;
  v207 = 0;
  v243 = 0;
  v291 = 0;
  *(_OWORD *)v264 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_158d5f44375531ecadb51b1a2a87ab5b_Traceguids, a11);
  KerbTracerT::Log(3, "KerbGetAuthenticationTicketEx", 2877, "KerbGetAuthenticationTicket in realm %wZ\n", String1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_158d5f44375531ecadb51b1a2a87ab5b_Traceguids, a9);
  v25 = 0;
  v219 = 0;
  v217 = 0;
  v245 = 0;
  v244 = 0;
  if ( v265 )
    *v265 = 0;
  RtlInitUnicodeString(DestinationString, 0);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase2>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_NGCKeyUsagePhase2>::GetImpl'::`2'::impl);
  v229 = a12 & 4;
  if ( (a12 & 4) == 0 && !a15 )
  {
    String2 = 0;
    S4UClientRealm = KerbGetS4UClientRealm(a1, v241, size, (unsigned __int8 *)Src, &String2);
    if ( !S4UClientRealm || (MicrosoftTelemetryAssertTriggeredNoArgs(v26), S4UClientRealm >= 0) )
    {
      if ( String2.Length )
      {
        if ( !RtlEqualUnicodeString(String1, &String2, 1u) )
        {
          v199 = 0;
          *DestinationString = String2;
          ExtendedPolicies = -1073741724;
          goto LABEL_522;
        }
        String2.Buffer = 0;
      }
    }
    KerbFreeString((__int64)&String2);
  }
  v254 = 0;
  v29 = 1082195984;
  RtlEnterCriticalSection(&stru_180144D18);
  if ( KerbLookupMitRealm(String1, &v257, &v218) )
  {
    v30 = *((_DWORD *)v257 + 6);
    v254 = v30;
  }
  else
  {
    LOBYTE(v30) = v254;
  }
  RtlLeaveCriticalSection(&stru_180144D18);
  if ( v257 )
    v29 = ((v30 & 8) << 13) | 0x40800010;
  v31 = v29 & 0xFFFEFFFF;
  if ( (a12 & 2) == 0 )
    v31 = v29;
  v220[0] = HIBYTE(v31);
  v220[1] = BYTE2(v31);
  v220[2] = BYTE1(v31);
  v220[3] = v31;
  v270 = *(_DWORD *)v220;
  v318 = &v270;
  v317 = 32;
  v288 = KerbGlobalWillNeverTime;
  KerbConvertLargeIntToGeneralizedTime(v322, 0, &v288);
  KerbConvertLargeIntToGeneralizedTime(v323, 0, &v288);
  v316 |= 0x10u;
  v253 = 0;
  ((void (__fastcall *)(int *))LsaFunctions->GetExtendedCallFlags)(&v253);
  CriticalSection = (PRTL_CRITICAL_SECTION)((char *)a1 + 80);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a1 + 2);
  v199 = 1;
  if ( v281 )
  {
    v201 = 1;
    v32 = (struct _UNICODE_STRING *)*((_QWORD *)v281 + 8);
    v225 = v32;
    KerbTracerT::Log(
      8,
      "KerbGetAuthenticationTicketEx",
      3041,
      "KerbGetAuthenticationTicket using extra credentials %wZ\\%wZ\n",
      &v32[1],
      v32);
    v33 = (Ntlmless::Kerberos *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v34 = 14;
LABEL_38:
      WPP_SF__KERB_NAME_(*((_QWORD *)v33 + 2), v34, WPP_158d5f44375531ecadb51b1a2a87ab5b_Traceguids, a9);
    }
  }
  else
  {
    v35 = v261;
    if ( !v261 || (v36 = (struct _KERB_PRIMARY_CREDENTIAL *)*((_QWORD *)v261 + 9)) == 0 )
    {
      if ( v282 )
      {
        v32 = (struct _UNICODE_STRING *)*((_QWORD *)v282 + 8);
        v225 = v32;
        KerbTracerT::Log(
          8,
          "KerbGetAuthenticationTicketEx",
          3079,
          "KerbGetAuthenticationTicket using cred manager credentials %wZ\\%wZ\n",
          &v32[1],
          v32);
        v33 = (Ntlmless::Kerberos *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF__KERB_NAME_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            WPP_158d5f44375531ecadb51b1a2a87ab5b_Traceguids,
            a9);
        if ( (!v35 || (*((_BYTE *)v35 + 64) & 0x10) == 0) && (v253 & 4) == 0 )
        {
          v201 = 1;
          goto LABEL_39;
        }
        v38 = "KerbGetAuthenticationTicketEx credman autologon restricted for %#x:%#x\n";
        v39 = 3103;
      }
      else
      {
        v32 = (struct _UNICODE_STRING *)((char *)a1 + 120);
        v225 = (struct _UNICODE_STRING *)((char *)a1 + 120);
        KerbTracerT::Log(
          8,
          "KerbGetAuthenticationTicketEx",
          3115,
          "KerbGetAuthenticationTicketEx using default credentials %wZ\\%wZ\n",
          (char *)a1 + 136,
          (char *)a1 + 120);
        v33 = (Ntlmless::Kerberos *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF__KERB_NAME_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_158d5f44375531ecadb51b1a2a87ab5b_Traceguids,
            a9);
        if ( !v35 || (*((_BYTE *)v35 + 64) & 0x10) == 0 )
        {
          v201 = 0;
          if ( (v253 & 4) == 0 )
            goto LABEL_39;
        }
        v38 = "KerbGetAuthenticationTicketEx autologon restricted for %#x:%#x\n";
        v39 = 3139;
      }
      LODWORD(v194) = *((_DWORD *)a1 + 16);
      LODWORD(v192) = *((_DWORD *)a1 + 17);
      KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", v39, v38, v192, v194);
      ExtendedPolicies = -2146893042;
      v22 = a9;
      goto LABEL_522;
    }
    if ( (*((_DWORD *)v261 + 16) & 0x100000) != 0 && *((_DWORD *)a1 + 16) == 999 && !*((_DWORD *)a1 + 17) )
    {
      ExtendedPolicies = KerbReplacePasswords(v36, (struct _KERB_LOGON_SESSION *)((char *)a1 + 120));
      if ( ExtendedPolicies < 0 )
        goto LABEL_522;
    }
    v201 = 1;
    v32 = (struct _UNICODE_STRING *)*((_QWORD *)v35 + 9);
    v225 = v32;
    KerbTracerT::Log(
      8,
      "KerbGetAuthenticationTicketEx",
      3068,
      "KerbGetAuthenticationTicket using supplied credentials %wZ\\%wZ\n",
      &v32[1],
      v32);
    v33 = (Ntlmless::Kerberos *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v34 = 15;
      goto LABEL_38;
    }
  }
LABEL_39:
  v37 = 0;
  v220[6] = 0;
  v212 = 0;
  v216 = 0;
  if ( *(_DWORD *)&v32[18].Length != 999 || *(_DWORD *)(&v32[18].MaximumLength + 1) )
  {
    v228 = 0;
  }
  else
  {
    v25 = 1;
    v220[6] = 1;
    v216 = KerbDevicePkinitEnabled != 0;
    LOBYTE(v37) = KerbDevicePkinitBehavior != 0;
    v228 = v37;
  }
  v40 = v32[17].Buffer != 0;
  v41 = v32 + 9;
  *(_QWORD *)&String2.Length = v32 + 9;
  v42 = *(_QWORD *)&v32[9].Length != 0;
  if ( Ntlmless::Kerberos::IsEnabled(v33) )
  {
    if ( ((__int64)v32[25].Buffer & 0x1000000) != 0 )
    {
      if ( !v32[3].Buffer && (unsigned int)_KERB_PLAINTEXT_PASSWORD::IsEmpty((_KERB_PLAINTEXT_PASSWORD *)&v32[43]) )
      {
        KerbTracerT::Log(
          1,
          "KerbGetAuthenticationTicketEx",
          3160,
          "Can't get AS ticket with no password for local user");
LABEL_65:
        ExtendedPolicies = -2146893042;
LABEL_515:
        v23 = v40;
        v25 = v42;
        goto LABEL_516;
      }
    }
    else if ( !*(_QWORD *)&v41->Length && !v32[17].Buffer )
    {
      KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", 3168, "Can't get AS ticket with no password");
      goto LABEL_65;
    }
  }
  else if ( !*(_QWORD *)&v41->Length && !v32[17].Buffer )
  {
    KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", 3178, "Can't get AS ticket with no password");
    goto LABEL_65;
  }
  if ( v25 && !v32[17].Buffer && KerbDevicePkinitEnabled && KerbDevicePkinitBehavior == 1 )
  {
    KerbTracerT::Log(
      2,
      "KerbGetAuthenticationTicketEx",
      3189,
      "%hs: PK Creds required, but missing\n",
      "KerbGetAuthenticationTicketEx");
    ExtendedPolicies = -2146893042;
    goto LABEL_518;
  }
  if ( !*((_WORD *)v241 + 1) || !*((_WORD *)v241 + 4) )
  {
    KerbTracerT::Log(
      2,
      "KerbGetAuthenticationTicketEx",
      3196,
      "KerbGetAuthenticationTicketEx not requesting ticket for blank client name\n");
    ExtendedPolicies = -1073741724;
    goto LABEL_515;
  }
  v213 = 0;
  v206 = 0;
  if ( KerbIsFastReady() )
  {
    v43 = (char *)v236 + 904;
    v242 = (_DWORD *)((char *)v236 + 904);
    if ( (*((_DWORD *)v236 + 226) & 0x800) != 0 )
    {
      v203 = v201 || !a6;
      goto LABEL_88;
    }
    v203 = 1;
  }
  else
  {
    v203 = 0;
    v43 = (char *)v236 + 904;
  }
  v242 = v43;
LABEL_88:
  if ( v32[17].Buffer )
  {
    if ( v25 )
    {
      if ( KerbDevicePkinitBehavior == 1 )
      {
        KerbTracerT::Log(
          8,
          "KerbGetAuthenticationTicketEx",
          3231,
          "Machine PKINIT required. Looking for DS 10 or above.\n");
        v213 = 0x800000;
      }
      else if ( *(_QWORD *)&v41->Length )
      {
        KerbTracerT::Log(
          8,
          "KerbGetAuthenticationTicketEx",
          3236,
          "Allow fallback to password credentials if machine PKINIT creds fail.\n");
        v206 = 1;
      }
    }
    else
    {
      ExtendedPolicies = KerbInitializePkCreds((struct _KERB_PRIMARY_CREDENTIAL *)v32, 0);
      v23 = v40;
      v25 = v42;
      if ( ExtendedPolicies < 0 )
      {
        v22 = a9;
        goto LABEL_522;
      }
      v44 = *(struct _CRYPTOAPI_BLOB **)(*((_QWORD *)v32[17].Buffer + 4) + 24LL);
      if ( CertCompareCertificateName(1u, v44 + 3, v44 + 5) )
      {
        KerbTracerT::Log(
          8,
          "KerbGetAuthenticationTicketEx",
          3253,
          "User has a self signed certficate. Looking for DS 10 or above.\n");
        v213 = 0x800000;
        v219 = 1;
      }
      else if ( (*v242 & 0x1000000) != 0
             && CertVerifyTimeValidity(0, *(PCERT_INFO *)(*((_QWORD *)v32[17].Buffer + 4) + 24LL)) )
      {
        KerbTracerT::Log(
          2,
          "KerbGetAuthenticationTicketEx",
          3261,
          "User's certificate is not time valid(potentially expired) for NGC logon!\n");
        v217 = 1;
      }
    }
  }
  v202 = KerbConvertKdcNameToPrincipalName((struct KERB_PRINCIPAL_NAME *)v319, v241);
  if ( v202 || (v316 |= 0x80u, (v202 = KerbConvertKdcNameToPrincipalName((struct KERB_PRINCIPAL_NAME *)v321, a9)) != 0) )
  {
    ExtendedPolicies = -1073741670;
    goto LABEL_515;
  }
  v45 = 1;
  v316 |= 0x40u;
  v46 = KerbGlobalUseClientIpAddresses != 0;
  if ( v257 )
  {
    v45 = 0;
    if ( (*((_BYTE *)v257 + 24) & 1) != 0 )
      v46 = 1;
  }
  ExtendedPolicies = KerbBuildHostAddresses(v46, v45, &v259);
  v23 = v40;
  v25 = v42;
  v289 = v259;
  if ( ExtendedPolicies < 0 )
    goto LABEL_516;
  v47 = 0;
  v221 = 0;
  v48 = 0;
  v198 = 0;
  v49 = a6;
  v256 = a6;
  v240 = 0;
  size_4 = 0;
  v294 = 0;
  v50 = 0;
  v200 = 0;
  v211 = 0;
  v235 = 0;
  v227 = 0;
  if ( v259 )
  {
    v325[1] = v259;
    v316 |= 8u;
  }
  v313 = 5;
  v314 = 10;
  while ( 1 )
  {
    v205 = 1;
    if ( v199 )
      goto LABEL_409;
    while ( 1 )
    {
      v202 = 0;
      v197 = 0;
      IsDomainClaimsCapableFromCache = 0;
      *(_DWORD *)v220 = 0;
      KerbFreeKey(&v271);
      v51 = v239;
      if ( v239 )
      {
        KerbDereferenceTicketCacheEntry(v239);
        v51 = 0;
        v239 = 0;
      }
      if ( v257 )
      {
        if ( v203 )
        {
          if ( (v254 & 0x10) != 0 )
          {
            v52 = v50 << 18;
            v53 = (struct _UNICODE_STRING *)v214;
            ExtendedPolicies = KerbGetExtendedPolicies(
                                 (struct _KERB_PROXY_LOGON_CRED *)v299,
                                 (struct _UNICODE_STRING *)v214,
                                 v52,
                                 &v239);
            if ( ExtendedPolicies < 0 )
            {
              v56 = "Failed to probe extended policies for domain %wZ: %#x\n";
              v57 = 3400;
              goto LABEL_413;
            }
            if ( v239 )
            {
              v47 = 1;
              v197 = 1;
              v54 = 3407;
              v55 = "AS-REQ to Mit realm %wZ using FAST\n";
            }
            else
            {
              v54 = 3411;
              v55 = "AS-REQ to Mit realm %wZ w/o FAST\n";
            }
            v49 = a6;
          }
          else
          {
            v54 = 3416;
            v55 = "AS-REQ to Mit realm %wZ w/o FAST\n";
            v53 = (struct _UNICODE_STRING *)v214;
          }
          KerbTracerT::Log(16, "KerbGetAuthenticationTicketEx", v54, v55, v53);
          if ( KerbGlobalRequireFast && !v47 )
          {
            ExtendedPolicies = -1073741715;
            v56 = "Client requires FAST armored AS-REQ but Mit realm %wZ does not support FAST: %#x\n";
            v57 = 3422;
LABEL_413:
            LODWORD(v194) = ExtendedPolicies;
            KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", v57, v56, v53, v194);
LABEL_414:
            v24 = 0;
            goto LABEL_516;
          }
        }
        else
        {
          v53 = (struct _UNICODE_STRING *)v214;
        }
      }
      else
      {
        if ( v203 )
        {
          v58 = v50 << 18;
          v53 = (struct _UNICODE_STRING *)v214;
          v59 = KerbGetExtendedPolicies(
                  (struct _KERB_PROXY_LOGON_CRED *)v299,
                  (struct _UNICODE_STRING *)v214,
                  v58,
                  &v239);
          ExtendedPolicies = v59;
          if ( v59 < 0 )
          {
            LODWORD(v194) = v59;
            KerbTracerT::Log(
              1,
              "KerbGetAuthenticationTicketEx",
              3440,
              "Failed to probe extended policies for domain %wZ: %#x\n",
              v53,
              v194);
            goto LABEL_414;
          }
          if ( v239 && (*((_DWORD *)v239 + 106) & 0x10000) != 0 )
          {
            v47 = 1;
            v197 = 1;
            KerbTracerT::Log(16, "KerbGetAuthenticationTicketEx", 3446, "AS-REQ to domain %wZ using FAST\n", v53);
          }
          else
          {
            KerbTracerT::Log(16, "KerbGetAuthenticationTicketEx", 3451, "AS-REQ to domain %wZ w/o FAST\n", v53);
          }
          if ( KerbGlobalRequireFast && !v47 )
          {
            ExtendedPolicies = -1073741715;
            v56 = "Client requires FAST armored AS-REQ but domain %wZ does not support FAST: %#x\n";
            v57 = 3457;
            goto LABEL_413;
          }
          v51 = v239;
          v49 = a6;
        }
        else
        {
          v53 = (struct _UNICODE_STRING *)v214;
        }
        if ( v51 )
        {
          if ( (*((_DWORD *)v51 + 106) & 0x40000) != 0 )
          {
            IsDomainClaimsCapableFromCache = 1;
            KerbTracerT::Log(16, "KerbGetAuthenticationTicketEx", 3467, "AS-REQ to claims capable domain %wZ\n", v53);
          }
        }
        else
        {
          IsDomainClaimsCapableFromCache = KerbIsDomainClaimsCapableFromCache(v53);
          if ( IsDomainClaimsCapableFromCache )
            KerbTracerT::Log(
              16,
              "KerbGetAuthenticationTicketEx",
              3476,
              "AS-REQ to claims capable domain %wZ (domain cache)\n",
              v53);
        }
      }
      v209 = 0;
      while ( 1 )
      {
LABEL_142:
        if ( (unsigned int)++size_4 > 0xC )
        {
          KerbTracerT::Log(
            1,
            "KerbGetAuthenticationTicketEx",
            3487,
            "KerbGetAuthenticationTicketEx exceeded max retries\n");
          ExtendedPolicies = -1073741715;
          goto LABEL_414;
        }
        KerbFreePreAuthData(hMem);
        hMem = 0;
        if ( v293 )
          KerbFree(v293);
        *(_OWORD *)v292 = 0;
        v293 = 0;
        if ( pCertContext )
        {
          CertFreeCertificateContext(pCertContext);
          pCertContext = 0;
        }
        KerbFreeKey(v310);
        KerbFreeKey(v297);
        KerbFreeKey(&v307);
        if ( !KerbAllocateNonce(pbBuffer) )
        {
          ExtendedPolicies = -1073741670;
          v24 = 0;
          goto LABEL_516;
        }
        if ( v47 )
        {
          (*(void (__fastcall **)(_QWORD, char *, _OWORD *, _OWORD *))(**((_QWORD **)v239 + 21) + 120LL))(
            *((_QWORD *)v239 + 21),
            (char *)v239 + 168,
            v310,
            v297);
          v292[0] = 1;
          v24 = 0;
          v60 = KerbCreateApRequest(
                  *((struct _KERB_INTERNAL_NAME **)v239 + 18),
                  (struct _UNICODE_STRING *)v239 + 6,
                  (struct _KERB_TICKET_CACHE_ENTRY *)((char *)v239 + 168),
                  (struct _KERB_ENCRYPTION_KEY *)v310,
                  0,
                  0,
                  0,
                  (struct _KERB_TICKET_CACHE_ENTRY *)((char *)v239 + 272),
                  0,
                  0,
                  &v237,
                  0xBu,
                  &v292[2],
                  &v293);
          v202 = v60;
          if ( v60 )
          {
            ExtendedPolicies = KerbMapKerbError(v60);
            LODWORD(v195) = ExtendedPolicies;
            LODWORD(v192) = v61;
            v62 = "Failed to create explicit armor ap-req for AS-REQ: %#x, Status %#x\n";
            v63 = 3551;
LABEL_151:
            KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", v63, v62, v192, v195);
            goto LABEL_516;
          }
        }
        else
        {
          v24 = 0;
        }
        if ( !v199 )
        {
          RtlEnterCriticalSection(CriticalSection);
          v199 = 1;
        }
        if ( v275 )
        {
          KerbFree(v275);
          v275 = 0;
        }
        KerbFreeRealm(v320);
        v202 = KerbConvertUnicodeStringToRealm(v320, v53);
        if ( v202 )
          goto LABEL_168;
        if ( Ntlmless::Kerberos::IsEnabled(v64) && ((__int64)v32[25].Buffer & 0x1000000) != 0 && v291.Length )
        {
          if ( KerbIsDomainLocalMachine(&v291) || KerbIsDomainLocalHostAlias(&v291) )
          {
            ExtendedPolicies = -1073741730;
            KerbTelemetry::ReportInterestingKerbEvent(0, 0);
            v195 = &v291;
            LODWORD(v192) = -1073741730;
            v62 = "GetAuthenticationTicket: Remote unjoined machine (LocalKDC) has the same name as current device : 0x%x, %wZ";
            v63 = 3601;
            goto LABEL_151;
          }
          v53 = &v291;
          v214 = &v291;
        }
        KerbFreeCryptList(v325[0]);
        v325[0] = 0;
        if ( Ntlmless::Kerberos::IsEnabled(v65)
          && ((__int64)v32[25].Buffer & 0x1000000) != 0
          && _KERB_PRIMARY_CREDENTIAL::HasLocalUserGeneratedKeys((_KERB_PRIMARY_CREDENTIAL *)v32, v53) )
        {
          _KERB_PRIMARY_CREDENTIAL::GetLocalUserPasswordKeys((_KERB_PRIMARY_CREDENTIAL *)v32, v53);
          if ( (unsigned int)KerbConvertKeysToCryptList(v325) )
            goto LABEL_168;
        }
        else
        {
          if ( !v32[3].Buffer && *(_QWORD *)&v32[9].Length )
          {
            if ( (unsigned int)KerbConvertKeysToCryptList(v325) )
            {
              ExtendedPolicies = -1073741670;
              goto LABEL_516;
            }
            goto LABEL_185;
          }
          KerberosCryptoPolicy::ForLocalMachine(&v263);
          if ( !v263 )
          {
            KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", 3654, "Failed to create crypto policy");
            ExtendedPolicies = -1073741670;
            goto LABEL_509;
          }
          KerberosCryptoPolicy::GetEncryptionTypes(v263);
          if ( !v267 )
          {
            KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", 3663, "Failed to get supported encryption types");
            ExtendedPolicies = -1073741059;
            goto LABEL_508;
          }
          if ( (unsigned int)KerbConvertArrayToCryptList(v325, *v267, (__int64)(v267[1] - *v267) >> 2) )
          {
            ExtendedPolicies = -1073741670;
LABEL_508:
            utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v267);
LABEL_509:
            utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v263);
            goto LABEL_516;
          }
          v66 = (__int64 *)v325[0];
          if ( v325[0] )
          {
            while ( 1 )
            {
              v67 = v66;
              v294 = v66;
              if ( *((_DWORD *)v66 + 2) == 3 )
                break;
              v66 = (__int64 *)*v66;
              if ( !v66 )
                goto LABEL_181;
            }
          }
          else
          {
            v67 = v294;
LABEL_181:
            if ( v325[0] )
            {
              v24 = MIDL_user_allocate(0x10u);
              if ( !v24 )
              {
                ExtendedPolicies = -1073741801;
                utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v267);
                utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v263);
                goto LABEL_516;
              }
              v24[2] = 3;
              *(_QWORD *)v24 = 0;
              *v67 = v24;
              v24 = 0;
            }
          }
          utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v267);
          utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v263);
        }
LABEL_185:
        v204 = 0;
        if ( !v49 )
          goto LABEL_213;
        v68 = 0;
        if ( v197 )
        {
          if ( v248 )
            v68 = (struct KERB_KDC_REQUEST_preauth_data_s *)*((_QWORD *)v248 + 1);
        }
        else if ( v246 )
        {
          v68 = *v246;
        }
        ExtendedPolicies = KerbGetPreAuthDataForRealm(
                             v236,
                             (struct _KERB_PRIMARY_CREDENTIAL *)v32,
                             (struct _UNICODE_STRING *)v214,
                             a9,
                             (struct _KERB_ENCRYPTION_KEY *)((unsigned __int64)v297 & -(__int64)(v197 != 0)),
                             v68,
                             &v237,
                             (v48 & 4) != 0,
                             v205,
                             v221,
                             v49,
                             &v207,
                             (struct KERB_KDC_REQUEST_preauth_data_s **)&hMem,
                             (struct _KERB_ENCRYPTION_KEY *)&v271,
                             (struct KERB_KDC_REQUEST_BODY *)&v316,
                             (struct _KERB_MESSAGE_BUFFER *)&v274,
                             (struct _UNICODE_STRING *)v220,
                             &v252);
        if ( ExtendedPolicies >= 0 )
          break;
        if ( ExtendedPolicies != -1073741718 )
        {
          if ( ExtendedPolicies == -1073740975 )
            KerbReportKerbError(
              a9,
              (struct _UNICODE_STRING *)v214,
              0,
              v69,
              L"onecore\\ds\\security\\protocols\\kerberos\\client2\\logonapi.cxx",
              0xED9u,
              0,
              0x10u,
              0,
              1u);
          if ( (ExtendedPolicies == -1073741023 || ExtendedPolicies == -1073740927 || ExtendedPolicies == -1073700608)
            && v206 )
          {
            KerbTracerT::Log(
              1,
              "KerbGetAuthenticationTicketEx",
              3812,
              "Failed to build pkinit pre-auth data. Retrying passwords.\n");
            if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                &dword_180140048,
                word_18012C792,
                0);
            KerbFallbackToPasswordCreds(v236, v32);
            v22 = a9;
            ExtendedPolicies = KerbGetAuthenticationTicketEx(
                                 v236,
                                 v261,
                                 v282,
                                 v281,
                                 v280,
                                 a6,
                                 size,
                                 (unsigned __int8 *)Src,
                                 a9,
                                 v214,
                                 v241,
                                 a12,
                                 a13,
                                 a14,
                                 a15,
                                 v283,
                                 v287,
                                 DestinationString,
                                 v265,
                                 v277);
            goto LABEL_517;
          }
LABEL_429:
          LODWORD(v192) = ExtendedPolicies;
          KerbTracerT::Log(
            1,
            "KerbGetAuthenticationTicketEx",
            3848,
            "GetAuthenticationTicket: Failed to build pre-auth data: 0x%x for %wZ\\%wZ",
            v192,
            &v32[1],
            v32);
          goto LABEL_516;
        }
        if ( (v48 & 0x40) != 0 )
        {
          if ( (v48 & 4) != 0 )
            goto LABEL_429;
          v48 = v48 & 0xFFFFFFBB | 4;
          v70 = "KerbGetAuthenticationTicket retry with old password\n";
          v71 = 3786;
        }
        else
        {
          v48 |= 0x40u;
          v70 = "KerbGetAuthenticationTicket retry with new salts\n";
          v71 = 3778;
        }
        v198 = v48;
        KerbTracerT::Log(2, "KerbGetAuthenticationTicketEx", v71, v70);
        v53 = (struct _UNICODE_STRING *)v214;
LABEL_196:
        v49 = a6;
        v47 = v197;
      }
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase2>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_NGCKeyUsagePhase2>::GetImpl'::`2'::impl);
      Buffer = v32[17].Buffer;
      if ( Buffer && !v207 )
        ++v227;
      if ( hMem )
      {
        if ( v256
          && !KerbGlobalSendPreauthForNewerETypes
          && !v257
          && !Buffer
          && (unsigned __int8)KerberosCryptoPolicy::CipherIsDeferred(HIDWORD(v271)) )
        {
          KerbFreePreAuthData(hMem);
          hMem = 0;
          a6 = 0;
          KerbFreeKey(&v271);
          v271 = 0;
          v272 = 0;
          v273 = 0;
          goto LABEL_214;
        }
        a6 = 1;
        v73 = v32[17].Buffer;
        if ( v73 )
        {
          v74 = (const CERT_CONTEXT *)*((_QWORD *)v73 + 4);
          if ( v74 )
            pCertContext = CertDuplicateCertificateContext(v74);
        }
      }
      else
      {
        a6 = 0;
      }
LABEL_213:
      if ( !v257 )
      {
LABEL_214:
        ExtendedPolicies = KerbAddPacRequestPreAuth((struct KERB_KDC_REQUEST_preauth_data_s **)&hMem, a12);
        if ( ExtendedPolicies < 0 )
          goto LABEL_516;
        if ( KerbGlobalEnableCbacAndArmor )
        {
          ExtendedPolicies = KerbAddPacOptionsPreAuth((struct KERB_KDC_REQUEST_preauth_data_s **)&hMem, 0x80000000, 0);
          if ( ExtendedPolicies < 0 )
            goto LABEL_516;
        }
      }
      if ( (*v242 & 0x400) != 0 )
      {
        v75 = hMem;
        if ( hMem )
        {
          v76 = *(_QWORD **)hMem;
          if ( *(_QWORD *)hMem )
          {
            do
            {
              v75 = v76;
              v76 = (_QWORD *)*v76;
            }
            while ( v76 );
          }
          v77 = MIDL_user_allocate(0x20u);
          *v75 = v77;
          if ( v77 )
          {
            *v77 = 0;
            v77[1] = 0;
            *((_DWORD *)v77 + 2) = 131;
            goto LABEL_223;
          }
LABEL_431:
          ExtendedPolicies = -1073741801;
          goto LABEL_516;
        }
LABEL_430:
        hMem = MIDL_user_allocate(0x20u);
        goto LABEL_431;
      }
LABEL_223:
      if ( *(_WORD *)v241 == 6 && size )
      {
        v78 = hMem;
        if ( !hMem )
          goto LABEL_430;
        v79 = *(_QWORD **)hMem;
        if ( *(_QWORD *)hMem )
        {
          do
          {
            v78 = v79;
            v79 = (_QWORD *)*v79;
          }
          while ( v79 );
        }
        v80 = MIDL_user_allocate(0x20u);
        v81 = v80;
        *v78 = v80;
        if ( !v80 )
          goto LABEL_431;
        *v80 = 0;
        v80[1] = 0;
        *((_DWORD *)v80 + 2) = 130;
        v82 = size;
        *((_DWORD *)v81 + 4) = size;
        v83 = v82;
        v84 = MIDL_user_allocate(v82);
        *((_QWORD *)v81 + 3) = v84;
        if ( !v84 )
          goto LABEL_431;
        memcpy_0(v84, Src, v83);
        *(_QWORD *)v81 = 0;
      }
      if ( (a12 & 8) != 0 )
        KerbAddPacOptionsPreAuth((struct KERB_KDC_REQUEST_preauth_data_s **)&hMem, 0x20000000u, 0);
      if ( hMem )
      {
        v312[0] |= 0x80u;
        if ( v32[17].Buffer )
          v85 = (const void *)WORD1(v32[17].Buffer);
        else
          v85 = 0;
        KerbTracerT::Log(
          2,
          "KerbGetAuthenticationTicketEx",
          4030,
          "KerbGetAuthenticationTicket sending preauth enctype %d, length %d, PrimaryCredentials->PublicKeyCreds %p\n",
          HIDWORD(v271),
          (_DWORD)v272,
          v85);
      }
      else
      {
        v312[0] &= ~0x80u;
        KerbTracerT::Log(2, "KerbGetAuthenticationTicketEx", 4035, "KerbGetAuthenticationTicket sending NO preauth\n");
      }
      if ( v197 )
      {
        v86 = hMem;
        v87 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, struct KerbKeyAgreement *, _QWORD, unsigned int *, _OWORD *))(**(_QWORD **)&v297[0] + 152LL))(
                *(_QWORD *)&v297[0],
                v312,
                v252,
                0,
                v292,
                v297);
        ExtendedPolicies = v87;
        if ( v87 < 0 )
        {
          KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", 4052, "Failed to create FAST armored AS-REQ: %#x\n", v87);
          goto LABEL_516;
        }
        KerbFreePreAuthData(v86);
      }
      v223[4] = 0;
      v202 = KerbPackData((__int64)v312, 0x4Eu, &v274, &v275);
      if ( v202 )
      {
LABEL_168:
        ExtendedPolicies = -1073741670;
        goto LABEL_516;
      }
      v88 = (struct PKERB_HOST_ADDRESSES_s *)v299;
      if ( v280 )
        v88 = v280;
      v259 = v88;
LABEL_347:
      RtlLeaveCriticalSection(CriticalSection);
      v199 = 0;
      KerbTracerT::Log(13, "KerbGetAuthenticationTicketEx", 4089, "KerbGetAuthenticationTicket: Calling KDC\n");
      KerbFreeData(31);
      v222 = 0;
      KerbFreeData(3);
      v246 = 0;
      v251 = 0;
      KerbFreeData(71);
      v248 = 0;
      if ( v269 )
      {
        KerbFree(v269);
        v269 = 0;
      }
      v47 = v197;
      if ( v197 || IsDomainClaimsCapableFromCache )
        v90 = v213 | 0x200000;
      else
        v90 = v213 & 0xFFDFFFFF;
      v213 = v90;
      LOBYTE(v89) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_InstantHAADJ>::GetImpl'::`2'::impl,
        v89);
      if ( v261 && (*((_DWORD *)v261 + 16) & 0x400000) != 0 )
      {
        v90 |= 0x2000000u;
        v213 = v90;
      }
      v255 = 0;
      if ( Ntlmless::Kerberos::IsEnabled(0)
        && (a14 & 0x20000000) != 0
        && (*v242 & 0x800) != 0
        && ((__int64)v225[25].Buffer & 0x1000000) == 0 )
      {
        v255 |= 2u;
      }
      v196 = v88;
      v53 = (struct _UNICODE_STRING *)v214;
      ExtendedPolicies = KerbTransferMessage(
                           (struct _KERB_MESSAGE_BUFFER *)&v274,
                           (struct _KERB_MESSAGE_BUFFER *)&v285,
                           (struct _UNICODE_STRING *const)v214,
                           v241,
                           a14,
                           v90,
                           v48,
                           v196,
                           v209,
                           v201,
                           &v295,
                           &v220[5],
                           &v305,
                           v277,
                           v261,
                           &v220[4],
                           &v255);
      if ( ExtendedPolicies < 0 )
      {
        LODWORD(v192) = ExtendedPolicies;
        KerbTracerT::Log(
          13,
          "KerbGetAuthenticationTicketEx",
          4166,
          "KerbTransferMessage failed with status 0x%x\n",
          v192);
        goto LABEL_439;
      }
      v209 = 0;
      KerbFreeData(73);
      *(_QWORD *)&v220[12] = 0;
      v91 = v220[4];
      if ( *(_DWORD *)v220 == 16
        && (unsigned int)dword_180140048 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
      {
        v210 = IsDomainClaimsCapableFromCache;
        v223[0] = v197;
        v224 = v203;
        v218 = v91;
        *(_QWORD *)v234 = (unsigned int)(v92 + 1);
        v247 = 0x1000000;
        v337 = &v210;
        v338 = *(_QWORD *)v234;
        v335 = v223;
        v336 = *(_QWORD *)v234;
        v333 = &v224;
        v334 = *(_QWORD *)v234;
        v331 = &v218;
        v332 = *(_QWORD *)v234;
        v329 = v234;
        v330 = (unsigned int)(v92 + 8);
        v327 = &v247;
        v328 = v330;
        tlgWriteAgg((int)&dword_180140048, (int)&byte_18012C719, v92, v92 + 8, &v326);
      }
      v93 = KerbUnpackData(v286, (unsigned int)v285, 73, &v220[12]);
      v202 = v93;
      if ( v93 )
        break;
      if ( v207 )
      {
        KerbTracerT::Log(
          1,
          "KerbGetAuthenticationTicketEx",
          5078,
          "Requested freshess token but got ticket.  User has smartcard preauth and preauth not required\n");
        v48 = v198;
        goto LABEL_403;
      }
      if ( (v198 & 2) == 0 )
        KerbUpdateSkewTime(0);
      v106 = v197;
      if ( v197 )
      {
        v107 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _BYTE *, _OWORD *, __int128 *, union _LARGE_INTEGER *))(**(_QWORD **)&v297[0] + 168LL))(
                 *(_QWORD *)&v297[0],
                 v312,
                 &v220[12],
                 v297,
                 &v307,
                 &Time);
        ExtendedPolicies = v107;
        if ( v107 < 0 )
        {
          LODWORD(v193) = v107;
          v121 = "Failed to verify FAST armored AS-REP: %#x\n";
          v122 = 5112;
          goto LABEL_447;
        }
        if ( *(_DWORD *)v220 == 138 && !(_DWORD)v308 )
        {
          ExtendedPolicies = -1073741715;
          LODWORD(v193) = -1073741715;
          v121 = "missing strengthen key when encrypted challenge is used: %#x\n";
          v122 = 5121;
          goto LABEL_447;
        }
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v237.QuadPart = Time.QuadPart - *(_QWORD *)&SystemTimeAsFileTime;
        v106 = v197;
      }
      RtlEnterCriticalSection(CriticalSection);
      v199 = 1;
      v32 = v225;
      if ( (char)**(_BYTE **)&v220[12] >= 0 )
      {
        v119 = *(struct _KERB_STORED_CREDENTIAL ***)&String2.Length;
        v111 = 0;
      }
      else
      {
        if ( v225[17].Buffer )
        {
          KerbFreeKey(&v271);
          HIDWORD(v271) = *(_DWORD *)(*(_QWORD *)&v220[12] + 124LL);
        }
        KerbFreePreAuthData(hMem);
        hMem = 0;
        v108 = v236;
        PreAuthDataForRealm = KerbGetPreAuthDataForRealm(
                                v236,
                                (struct _KERB_PRIMARY_CREDENTIAL *)v32,
                                (struct _UNICODE_STRING *)v214,
                                a9,
                                (struct _KERB_ENCRYPTION_KEY *)((unsigned __int64)v297 & -(__int64)(v106 != 0)),
                                *(struct KERB_KDC_REQUEST_preauth_data_s **)(*(_QWORD *)&v220[12] + 16LL),
                                &v237,
                                (v198 & 4) != 0,
                                v205,
                                0,
                                a6,
                                &v207,
                                (struct KERB_KDC_REQUEST_preauth_data_s **)&hMem,
                                (struct _KERB_ENCRYPTION_KEY *)&v271,
                                (struct KERB_KDC_REQUEST_BODY *)&v316,
                                (struct _KERB_MESSAGE_BUFFER *)&v274,
                                (struct _UNICODE_STRING *)v220,
                                &v252);
        ExtendedPolicies = PreAuthDataForRealm;
        v111 = 0;
        if ( PreAuthDataForRealm < 0 )
        {
          v165 = v214;
          if ( PreAuthDataForRealm == -1073740975 )
            KerbReportKerbError(
              a9,
              (struct _UNICODE_STRING *)v214,
              0,
              v110,
              L"onecore\\ds\\security\\protocols\\kerberos\\client2\\logonapi.cxx",
              0x1441u,
              0,
              0x10u,
              0,
              1u);
          KerbTracerT::Log(
            1,
            "KerbGetAuthenticationTicketEx",
            5193,
            "Failed to post process pre-auth data: 0x%x",
            PreAuthDataForRealm);
          if ( v206 )
          {
            v212 = 1;
            KerbFallbackToPasswordCreds(v108, v32);
            v22 = a9;
            ExtendedPolicies = KerbGetAuthenticationTicketEx(
                                 v108,
                                 v261,
                                 v282,
                                 v281,
                                 v280,
                                 a6,
                                 size,
                                 (unsigned __int8 *)Src,
                                 a9,
                                 v165,
                                 v241,
                                 a12,
                                 a13,
                                 a14,
                                 a15,
                                 v283,
                                 v287,
                                 DestinationString,
                                 v265,
                                 v277);
          }
          else
          {
            v22 = a9;
          }
          v24 = v204;
          goto LABEL_517;
        }
        if ( v32[17].Buffer || (v112 = *(_DWORD *)(*(_QWORD *)&v220[12] + 124LL), HIDWORD(v271) == v112) )
        {
          v119 = (struct _KERB_STORED_CREDENTIAL **)&v32[9];
        }
        else
        {
          if ( (v198 & 4) != 0 )
            p_Buffer = &v32[5].Buffer;
          else
            p_Buffer = &v32[3].Buffer;
          KerbTracerT::Log(
            2,
            "KerbGetAuthenticationTicketEx",
            5241,
            "KerbGetAuthenticationTicket rekeying %d -> %d (preauth not required)\n",
            HIDWORD(v271),
            v112);
          v111 = 0;
          if ( !v229
            && *p_Buffer
            && (KerbFindPreAuthDataEntry(19, *(_QWORD *)(*(_QWORD *)&v220[12] + 16LL), 0, v114)
             || KerbFindPreAuthDataEntry(11, v116, v111, v115)) )
          {
            v117 = (int)v111;
            LOBYTE(v117) = (v198 & 4) != 0;
            v118 = KerbRetryCredentialsPassword((_KERB_PRIMARY_CREDENTIAL *)v32, v117, v111);
            ExtendedPolicies = v118;
            v111 = 0;
            if ( v118 < 0 )
            {
              LODWORD(v193) = v118;
              v121 = "KerbRetryCredentialsPassword failed with %#x\n";
              v122 = 5268;
              goto LABEL_447;
            }
          }
          v119 = (struct _KERB_STORED_CREDENTIAL **)&v32[9];
          if ( *((struct _UNICODE_STRING **)&v272 + 1) != v111 )
          {
            v120 = KerbAugumentCredentialsPassword(
                     *v119,
                     (struct _KERB_ENCRYPTION_KEY *)&v271,
                     (struct _KERB_STORED_CREDENTIAL **)&v32[9]);
            ExtendedPolicies = v120;
            v111 = 0;
            if ( v120 < 0 )
            {
              LODWORD(v193) = v120;
              v121 = "KerbAugumentCredentialsPassword failed with %#x\n";
              v122 = 5286;
              goto LABEL_447;
            }
          }
        }
      }
      v123 = *(unsigned int *)(*(_QWORD *)&v220[12] + 124LL);
      if ( HIDWORD(v271) == (_DWORD)v123 )
      {
        KeyFromList = (struct _KERB_ENCRYPTION_KEY *)&v271;
      }
      else
      {
        if ( (struct _UNICODE_STRING *)v32[17].Buffer != v111 )
        {
          v194 = v32;
          v193 = (PEVENT_DATA_DESCRIPTOR)&v32[1];
          v166 = "KerbGetAuthenticationTicket kdc does not support the PKINIT revision for %wZ\\%wZ\n";
          v167 = 5306;
          goto LABEL_461;
        }
        KeyFromList = (struct _KERB_ENCRYPTION_KEY *)KerbGetKeyFromList(*v119, v123, 0);
        v111 = 0;
        if ( !KeyFromList )
        {
          KerbTracerT::Log(
            1,
            "KerbGetAuthenticationTicketEx",
            5322,
            "Kdc returned reply with encryption type we don't support: %d",
            *(_DWORD *)(*(_QWORD *)&v220[12] + 124LL));
          goto LABEL_446;
        }
      }
      if ( (struct _UNICODE_STRING *)v32[17].Buffer == v111 )
        KerbRevealKey(KeyFromList);
      KerbFreeData(76);
      v238 = 0;
      v125 = KerbCredIsoApi::UnpackKdcReplyBody(
               *(KerbCredIsoApi **)KeyFromList,
               (struct KERB_ENCRYPTED_DATA *)(*(_QWORD *)&v220[12] + 120LL),
               KeyFromList,
               (struct _KERB_ENCRYPTION_KEY *)&v307,
               0x4Bu,
               (unsigned int *)&v264[1],
               v264,
               &v202,
               &v238,
               0);
      v126 = v125;
      v245 = *((_DWORD *)KeyFromList + 3);
      v244 = 75;
      if ( v125 < 0 )
        KerbTracerT::Log(
          1,
          "KerbGetAuthenticationTicketEx",
          5366,
          "%hs: Failed to unpack kdc reply body. NT: %#x, KERB: %#x\n",
          "KerbGetAuthenticationTicketEx",
          v125,
          v202);
      v127 = (int)v264[1];
      LODWORD(v264[1]) = 0;
      v128 = v264[0];
      v264[0] = 0;
      v129 = *(UNICODE_STRING **)&v32[19].Length;
      *(_QWORD *)&v32[19].Length = v128;
      p_String2 = v129;
      LODWORD(v129) = v32[19].Buffer;
      LODWORD(v32[19].Buffer) = v127;
      v302 = (int)v129;
      kerb_encryption_keylist::~kerb_encryption_keylist((kerb_encryption_keylist *)&p_String2);
      if ( !v32[17].Buffer )
        KerbHideKey(KeyFromList);
      if ( v202 == 41 )
      {
        v130 = v32[9].Buffer;
        if ( v130 )
        {
          if ( !*((_QWORD *)&v272 + 1) )
          {
            v131 = (struct _KERB_ENCRYPTION_KEY *)KerbGetKeyFromList(
                                                    v130,
                                                    *(unsigned int *)(*(_QWORD *)&v220[12] + 124LL),
                                                    0);
            KeyFromList = v131;
            if ( v131 )
            {
              KerbRevealKey(v131);
              v126 = KerbCredIsoApi::UnpackKdcReplyBody(
                       *(KerbCredIsoApi **)KeyFromList,
                       (struct KERB_ENCRYPTED_DATA *)(*(_QWORD *)&v220[12] + 120LL),
                       KeyFromList,
                       (struct _KERB_ENCRYPTION_KEY *)&v307,
                       0x4Bu,
                       (unsigned int *)&v264[1],
                       v264,
                       &v202,
                       &v238,
                       0);
              v245 = *((_DWORD *)KeyFromList + 3);
              v244 = 75;
              KerbHideKey(KeyFromList);
            }
          }
        }
      }
      if ( v126 < 0 )
      {
        KerbTracerT::Log(
          1,
          "KerbGetAuthenticationTicketEx",
          5420,
          "%hs: Failed to unpack kdc reply body (second try). NT: %#x, KERB: %#x\n",
          "KerbGetAuthenticationTicketEx",
          v126,
          v202);
        if ( (v198 & 0x20) != 0 || v202 != 41 || !KerbGlobalRetryPdc )
        {
          ExtendedPolicies = a6 != 0 ? -1073741715 : -1073741718;
          goto LABEL_435;
        }
        v48 = v198 | 0x20;
        v198 |= 0x20u;
        KerbFreeData(73);
        *(_QWORD *)&v220[12] = 0;
        v286 = 0;
        KerbTracerT::Log(
          8,
          "KerbGetAuthenticationTicketEx",
          5437,
          "KerbGetAuthenticationTicket: Password wrong, trying PDC\n");
        v88 = v259;
        goto LABEL_347;
      }
      v134 = (int)v264[1];
      LODWORD(v264[1]) = 0;
      v135 = v264[0];
      v264[0] = 0;
      v136 = *(_QWORD *)&v32[19].Length;
      *(_QWORD *)&v32[19].Length = v135;
      v303 = v136;
      LODWORD(v136) = v32[19].Buffer;
      LODWORD(v32[19].Buffer) = v134;
      v304 = v136;
      kerb_encryption_keylist::~kerb_encryption_keylist((kerb_encryption_keylist *)&v303);
      if ( *(_DWORD *)pbBuffer != *((_DWORD *)v238 + 10) )
      {
        LODWORD(v194) = *((_DWORD *)v238 + 10);
        LODWORD(v193) = *(_DWORD *)pbBuffer;
        v166 = "AS Nonces don't match: 0x%x vs 0x%x";
        v167 = 5459;
LABEL_461:
        KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", v167, v166, v193, v194);
LABEL_446:
        ExtendedPolicies = -1073741715;
        goto LABEL_435;
      }
      if ( !(unsigned __int8)KerbComparePrincipalNames((char *)v238 + 144, *(_QWORD *)&v220[12] + 64LL) )
      {
        v181 = "KerbGetAuthenticationTicketEx Mismatch between ticket sname and reply sname";
        v182 = 5470;
        goto LABEL_502;
      }
      v210 = 0;
      v137 = KerbCompareRealmNames((char *)v238 + 136, *(_QWORD *)&v220[12] + 56LL, &v210);
      v202 = v137;
      if ( v137 )
      {
        v159 = KerbMapKerbError(v137);
        LODWORD(v194) = v159;
        LODWORD(v193) = v183;
        v161 = "KerbGetAuthenticationTicketEx Failed to compare realm names of ticket and reply: %#x Status %#x\n";
        v162 = 5485;
        goto LABEL_434;
      }
      if ( !v210 )
      {
        v181 = "KerbGetAuthenticationTicketEx Mismatch between ticket realm and reply realm";
        v182 = 5491;
LABEL_502:
        KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", v182, v181);
        goto LABEL_446;
      }
      if ( !KerbGlobalEnableCbacAndArmor || (*(_BYTE *)v238 & 8) == 0 || (v213 & 0x200000) != 0 )
        goto LABEL_566;
      v234[0] = 0;
      v139 = 0;
      PreAuthDataEntry = (struct KERB_PA_DATA *)KerbFindPreAuthDataEntry(167, *((_QWORD *)v238 + 21), v238, 0);
      if ( PreAuthDataEntry )
      {
        v143 = KerbCheckPacOptionsPreAuthData(PreAuthDataEntry, v234);
        v202 = v143;
        if ( v143 )
        {
          v159 = KerbMapKerbError(v143);
          LODWORD(v194) = v159;
          LODWORD(v193) = v168;
          v161 = "Failed to check PacOptions from encrypted_pa_data in AS-REP: %#x, Status %#x\n";
          v162 = 5525;
          goto LABEL_434;
        }
        v141 = v238;
        v142 = v234[0];
      }
      v144 = KerbFindPreAuthDataEntry(165, *((_QWORD *)v141 + 21), v141, v142);
      if ( v144 )
      {
        v138 = *(Ntlmless::Kerberos **)(v144 + 16);
        if ( v138 )
        {
          if ( *(_DWORD *)(v144 + 8) == 4 )
            v139 = *(_DWORD *)v138;
        }
      }
      if ( v145 < 0
        || (v139 & 0x40000) == 0
        || (v146 = (struct _UNICODE_STRING *)v214,
            KerbTracerT::Log(
              16,
              "KerbGetAuthenticationTicketEx",
              5549,
              "downlevel DC returns claims capable for %wZ.\n",
              v214),
            v200) )
      {
LABEL_566:
        if ( Ntlmless::Kerberos::IsEnabled(v138) )
        {
          if ( ((__int64)v32[25].Buffer & 0x1000000) == 0 )
          {
            KerbTracerT::Log(
              10,
              "KerbGetAuthenticationTicketEx",
              5585,
              "Updating primary credentials user/realm names from AS_REP");
            updated = KerbUpdatePrimaryCredentialsNamesFromAsRep(v32, *(struct KERB_KDC_REPLY *const *)&v220[12], &v300);
            ExtendedPolicies = updated;
            if ( updated < 0 )
            {
              v122 = 5590;
              goto LABEL_373;
            }
          }
LABEL_375:
          v148 = v236;
          v149 = KerbHandleDmsaMigrationInProgress(v238, v236);
          ExtendedPolicies = v149;
          if ( v149 >= 0 )
          {
            v150 = v201;
            if ( v201 )
              goto LABEL_389;
            v151 = v242;
            if ( v211 || (*v242 & 0x400000) == 0 || !*(_QWORD *)((char *)v148 + 924) )
              goto LABEL_388;
            v152 = (const struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)v148 + 33);
            if ( !v152 || (ExtendedPolicies = KerbClientDuplicateStoredCred(v152, &v276), ExtendedPolicies >= 0) )
            {
              v153 = (const struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)v148 + 34);
              if ( !v153 || (ExtendedPolicies = KerbClientDuplicateStoredCred(v153, &v284), ExtendedPolicies >= 0) )
              {
                if ( !*((_QWORD *)v148 + 88) )
                  goto LABEL_387;
                v154 = MIDL_user_allocate(*((unsigned int *)v148 + 178));
                v278 = v154;
                if ( v154 )
                {
                  memcpy_0(v154, *((const void **)v148 + 88), *((unsigned int *)v148 + 178));
                  v235 = *((_DWORD *)v148 + 178);
LABEL_387:
                  v211 = 1;
                  v151 = v242;
LABEL_388:
                  *v151 &= ~0x80u;
                  KerbCleanupLogonSessionCredentials(v148);
                  v150 = 0;
LABEL_389:
                  if ( v32[3].Buffer && v150 && ((__int64)v32[25].Buffer & 1) == 0 )
                    KerbFreePlaintextPassword((struct _KERB_PLAINTEXT_PASSWORD *)&v32[2]);
                  if ( !v32[18].Buffer )
                    v32[18].Buffer = (PWSTR)((((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                                            * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64);
                  if ( (a12 & 0xC) != 0 || (v155 = (struct _KERB_TICKET_CACHE *)&v32[15], (a14 & 1) != 0) )
                    v155 = 0;
                  v53 = (struct _UNICODE_STRING *)v214;
                  v156 = KerbCreateTicketCacheEntry(
                           *(struct KERB_KDC_REPLY **)&v220[12],
                           v238,
                           *(struct KerbCredIsoApi **)KeyFromList,
                           a9,
                           (struct _UNICODE_STRING *)v214,
                           a13 | (v197 != 0 ? 0x40 : 0),
                           (signed int)v237.LowPart / 10000000,
                           v155,
                           (struct _KERB_ENCRYPTION_KEY *)&v271,
                           &v305,
                           &v300,
                           v295,
                           &v279);
                  ExtendedPolicies = v156;
                  if ( v156 < 0 )
                  {
                    if ( v156 == -1073741517 && (v198 & 2) == 0 )
                    {
                      v48 = v198 | 2;
                      v198 |= 2u;
                      KerbUpdateSkewTime(1u);
                      KerbTracerT::Log(
                        2,
                        "KerbGetAuthenticationTicketEx",
                        5738,
                        "Retrying AS after trying to cache time invalid ticket\n");
                      goto LABEL_196;
                    }
                    goto LABEL_439;
                  }
                  if ( v283 )
                  {
                    *v283 = v279;
                    v279 = 0;
                  }
                  v169 = v287;
                  if ( v287 )
                  {
                    *(_OWORD *)v287 = v271;
                    *((_OWORD *)v169 + 1) = v272;
                    *((_QWORD *)v169 + 4) = v273;
                    *((_QWORD *)&v272 + 1) = 0;
                  }
                  v170 = v236;
                  if ( (*((_DWORD *)v236 + 16) == 999 || *((_DWORD *)v236 + 16) == 996)
                    && !*((_DWORD *)v236 + 17)
                    && !v201 )
                  {
                    WinSqmSetDWORD(0, 10688);
                  }
                  if ( v211 )
                  {
                    LogonSession = KerbLocateLogonSession((const struct _LUID *)((char *)v170 + 924), 0);
                    v172 = LogonSession;
                    v296 = LogonSession;
                    if ( LogonSession )
                    {
                      if ( (*((_DWORD *)LogonSession + 226) & 0x400001) == 0x400001 && !*((_QWORD *)LogonSession + 88) )
                      {
                        String2 = 0;
                        v173 = (char *)MIDL_user_allocate(40LL * *((unsigned int *)v170 + 108));
                        *(_QWORD *)&String2.Length = v173;
                        if ( !v173 )
                        {
                          ExtendedPolicies = -1073741801;
                          goto LABEL_435;
                        }
                        p_String2 = &String2;
                        LOBYTE(v302) = 1;
                        v174 = 0;
                        if ( *((_DWORD *)v170 + 108) )
                        {
                          while ( !(unsigned int)KerbDuplicateKey(
                                                   &v173[40 * v174],
                                                   *((_QWORD *)v170 + 53) + 40LL * v174) )
                          {
                            ++LODWORD(String2.Buffer);
                            if ( ++v174 >= *((_DWORD *)v170 + 108) )
                              goto LABEL_487;
                            v173 = *(char **)&String2.Length;
                          }
                          ExtendedPolicies = -1073741801;
                          if ( *(_QWORD *)&String2.Length )
                            KerbFreeKeyArray(LODWORD(String2.Buffer));
                          goto LABEL_439;
                        }
LABEL_487:
                        RtlLeaveCriticalSection(CriticalSection);
                        v199 = 0;
                        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v172 + 2);
                        if ( (*((_BYTE *)v172 + 904) & 1) != 0 && !*((_QWORD *)v172 + 88) )
                        {
                          v175 = (struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)v172 + 33);
                          if ( v175 )
                            KerbClientFreeStoredCred(v175);
                          *((_QWORD *)v172 + 33) = v276;
                          v276 = 0;
                          v176 = (struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)v172 + 34);
                          if ( v176 )
                            KerbClientFreeStoredCred(v176);
                          *((_QWORD *)v172 + 34) = v284;
                          v284 = 0;
                          *((_QWORD *)v172 + 88) = v278;
                          v278 = 0;
                          *((_DWORD *)v172 + 178) = v235;
                          v177 = (int)String2.Buffer;
                          LODWORD(String2.Buffer) = 0;
                          v178 = *(_QWORD *)&String2.Length;
                          *(_QWORD *)&String2.Length = 0;
                          v179 = *((_QWORD *)v172 + 53);
                          *((_QWORD *)v172 + 53) = v178;
                          v303 = v179;
                          LODWORD(v179) = *((_DWORD *)v172 + 108);
                          *((_DWORD *)v172 + 108) = v177;
                          v304 = v179;
                          kerb_encryption_keylist::~kerb_encryption_keylist((kerb_encryption_keylist *)&v303);
                          KerbCleanupLogonSessionCredentials(v172);
                        }
                        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v172 + 2);
                        if ( *(_QWORD *)&String2.Length )
                          KerbFreeKeyArray(LODWORD(String2.Buffer));
                      }
                    }
                  }
                  wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase2>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_NGCKeyUsagePhase2>::GetImpl'::`2'::impl);
                  if ( (unsigned int)dword_180140048 > 5
                    && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
                  {
                    v226 = ExtendedPolicies;
                    v229 = v227;
                    *(_QWORD *)&String2.Length = 0x1000000;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                      (unsigned int)&dword_180140048,
                      (unsigned int)&byte_18012C667,
                      0,
                      v180,
                      (__int64)&String2,
                      (__int64)&v229,
                      (__int64)&v226);
                  }
                }
                else
                {
                  ExtendedPolicies = -1073741801;
                }
              }
            }
LABEL_439:
            v24 = v204;
            goto LABEL_516;
          }
          LODWORD(v193) = v149;
          v121 = "KerbHandleDmsaMigration failed: 0x%x";
          v122 = 5611;
        }
        else
        {
          KerbTracerT::Log(
            10,
            "KerbGetAuthenticationTicketEx",
            5597,
            "Updating primary credentials user/realm names from AS_REP");
          updated = KerbUpdatePrimaryCredentialsNamesFromAsRep(v32, *(struct KERB_KDC_REPLY *const *)&v220[12], &v300);
          ExtendedPolicies = updated;
          if ( updated >= 0 )
            goto LABEL_375;
          v122 = 5602;
LABEL_373:
          v121 = "failed to update names in primary credentials: 0x%x";
          LODWORD(v193) = updated;
        }
LABEL_447:
        KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", v122, v121, v193);
        goto LABEL_435;
      }
      if ( v239 )
      {
        KerbTracerT::Log(16, "KerbGetAuthenticationTicketEx", 5555, "client reprobes claims for domain %wZ\n", v146);
        v47 = 0;
      }
      else
      {
        ExtendedPolicies = KerbCacheClaimsCapableDomain(v146);
        v47 = 0;
        v193 = (PEVENT_DATA_DESCRIPTOR)v146;
        if ( ExtendedPolicies < 0 )
        {
          v121 = "failed to cache claims capable for domain %wZ\n";
          v122 = 5563;
          goto LABEL_447;
        }
        KerbTracerT::Log(
          16,
          "KerbGetAuthenticationTicketEx",
          5567,
          "client reprobes claims for domain %wZ (domain cache)\n",
          v146);
      }
      v50 = 1;
      v200 = 1;
      v48 = v198;
      v49 = a6;
LABEL_409:
      RtlLeaveCriticalSection(CriticalSection);
      v199 = 0;
    }
    KerbTracerT::Log(2, "KerbGetAuthenticationTicketEx", 4198, "Failed to unpack KDC reply as AS: 0x%x\n", v93);
    v94 = 0;
    if ( v215 )
    {
      KerbFreeData(6);
      v215 = 0;
    }
    v95 = KerbUnpackData(v286, (unsigned int)v285, 6, &v215);
    v202 = v95;
    if ( v95 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetAuthenticationTicketEx",
        5070,
        "Failed to unpack KDC reply as AS or Error: 0x%x\n",
        v95);
      ExtendedPolicies = -1073741595;
      goto LABEL_435;
    }
    v205 = 1;
    if ( !v197 )
    {
      v96 = v236;
      if ( (*(_BYTE *)v215 & 4) == 0 )
        goto LABEL_286;
      KerbHandleDmsaMigrationComplete(v215, 0, v236, &v243);
      if ( !v243 )
      {
        v202 = KerbUnpackErrorData(v215, &v222);
        if ( !v202 && v222 && (*((_BYTE *)v222 + 8) & 1) != 0 && *(int *)v222 < 0 )
          v94 = *(_DWORD *)v222;
LABEL_286:
        v101 = *((_DWORD *)v215 + 13);
        v221 = v101;
        v102 = v101;
        v202 = v101;
        if ( v101 == 85 )
        {
          ExtendedPolicies = -1073741730;
          KerbTracerT::Log(
            2,
            "KerbGetAuthenticationTicketEx",
            4374,
            "KerbGetAuthenticationTicket IAKerb error translated to 0x%x, 0x%x\n",
            85,
            -1073741730);
        }
        else if ( v101 == 86 )
        {
          ExtendedPolicies = -2146893039;
          KerbTracerT::Log(
            2,
            "KerbGetAuthenticationTicketEx",
            4381,
            "KerbGetAuthenticationTicket IAKerb error translated to 0x%x, 0x%x\n",
            86,
            -2146893039);
        }
        else
        {
          if ( v101 != 7 || v94 != -2147483640 )
          {
            if ( *(_DWORD *)v220 == 16 )
            {
              if ( (unsigned int)dword_180140048 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
              {
                v234[0] = v94;
                LODWORD(v247) = v202;
                v306 = 1;
                *(_QWORD *)&v260.Length = 0x1000000;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  (unsigned int)&dword_180140048,
                  (unsigned int)byte_18012C6BD,
                  v103,
                  (unsigned int)&v260,
                  (__int64)&v306,
                  (__int64)&v247,
                  (__int64)v234);
              }
              v102 = v202;
            }
            if ( v102 != 25 && v265 )
              *v265 = 1;
            KerbTracerT::Log(
              2,
              "KerbGetAuthenticationTicketEx",
              4412,
              "KerbCallKdc failed: error 0x%x, extendedStatus %#x",
              v102,
              v94);
            KerbMapKerbError(v202);
            KerbReportKerbError(
              a9,
              (struct _UNICODE_STRING *)v214,
              v96,
              v105,
              L"onecore\\ds\\security\\protocols\\kerberos\\client2\\logonapi.cxx",
              0x1146u,
              v215,
              v104,
              v222,
              0);
          }
          ExtendedPolicies = -1073741730;
          LODWORD(v193) = -1073741730;
          KerbTracerT::Log(
            13,
            "KerbGetAuthenticationTicketEx",
            4389,
            "We're a local KDC and it returned SPN unknown so converting to 0x%x\n",
            v193);
        }
        goto LABEL_439;
      }
      v164 = 4352;
      goto LABEL_438;
    }
    ExtendedPolicies = (*(__int64 (__fastcall **)(_QWORD, _WORD *, struct KERB_ERROR **, _OWORD *, struct KrbFastResponse **))(**(_QWORD **)&v297[0] + 160LL))(
                         *(_QWORD *)&v297[0],
                         v312,
                         &v215,
                         v297,
                         &v248);
    if ( ExtendedPolicies >= 0 )
      break;
    v132 = *((_DWORD *)v215 + 13);
    v50 = 1;
    if ( (unsigned int)(v132 - 32) > 1 )
    {
      if ( v132 == 37 )
      {
        ExtendedPolicies = KerbMapKerbError(37);
        v133 = v198;
        if ( (v198 & 2) == 0 )
        {
          v48 = v198 | 2;
          v198 |= 2u;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          KerbConvertGeneralizedTimeToLargeInt(&Time);
          v237.QuadPart = Time.QuadPart - *(_QWORD *)&SystemTimeAsFileTime;
          KerbUpdateSkewTime(1u);
          KerbTracerT::Log(
            2,
            "KerbGetAuthenticationTicketEx",
            4266,
            "client recover FAST armor ticket time skew error in AS-REQ: %#x, TimeSkew = %lld seconds\n",
            *((_DWORD *)v215 + 13),
            v237.QuadPart / 10000000);
          v53 = (struct _UNICODE_STRING *)v214;
LABEL_403:
          v32 = v225;
          v49 = a6;
          goto LABEL_142;
        }
      }
      else
      {
        v133 = v198;
      }
      v158 = v200;
LABEL_442:
      KerbTracerT::Log(
        1,
        "KerbGetAuthenticationTicketEx",
        4272,
        "Failed to verify FAST armored KRB-ERROR in response to AS-REQ: %#x, RetriedProbeFast %d, RetryFlags %#x\n",
        ExtendedPolicies,
        v158,
        v133);
      goto LABEL_435;
    }
    ExtendedPolicies = KerbMapKerbError(v132);
    v158 = v200;
    v47 = 0;
    if ( v200 )
    {
      v133 = v198;
      goto LABEL_442;
    }
    KerbTracerT::Log(
      2,
      "KerbGetAuthenticationTicketEx",
      4240,
      "client reprobe FAST in AS-REQ because the armor ticket was either expired or not yet valid: %#x\n",
      v157);
    v200 = 1;
    v32 = v225;
    v48 = v198;
    v49 = a6;
  }
  KerbTracerT::Log(
    16,
    "KerbGetAuthenticationTicketEx",
    4276,
    "Received FAST armored KRB-ERROR in response to AS-REQ: %#x\n",
    *((_DWORD *)v215 + 13));
  v96 = v236;
  KerbHandleDmsaMigrationComplete(v215, v248, v236, &v243);
  if ( v243 )
  {
    v164 = 4288;
LABEL_438:
    KerbTracerT::Log(
      3,
      "KerbGetAuthenticationTicketEx",
      v164,
      "Discovered a linked dmsa and successfully acquired a TGT");
    goto LABEL_439;
  }
  v98 = KerbFindPreAuthDataEntry(3, *((_QWORD *)v248 + 1), v97, 0);
  if ( !v98 )
    goto LABEL_286;
  v99 = KerbPackData(*(_QWORD *)(v98 + 16), 0x1Fu, &v233, &v269);
  v202 = v99;
  if ( v99 )
  {
    v159 = KerbMapKerbError(v99);
    LODWORD(v194) = v159;
    LODWORD(v193) = v163;
    v161 = "Failed to pack extended error: %#x, Status %#x\n";
    v162 = 4309;
  }
  else
  {
    v100 = KerbUnpackData(v269, v233, 31, &v222);
    v202 = v100;
    if ( !v100 )
    {
      if ( v222 && (*((_BYTE *)v222 + 8) & 1) != 0 && *(int *)v222 < 0 )
        v94 = *(_DWORD *)v222;
      goto LABEL_286;
    }
    v159 = KerbMapKerbError(v100);
    LODWORD(v194) = v159;
    LODWORD(v193) = v160;
    v161 = "Failed to unpack extended error: %#x, Status %#x\n";
    v162 = 4323;
  }
LABEL_434:
  ExtendedPolicies = v159;
  KerbTracerT::Log(1, "KerbGetAuthenticationTicketEx", v162, v161, v193, v194);
LABEL_435:
  v24 = v204;
LABEL_516:
  v22 = a9;
LABEL_517:
  if ( !v220[6] )
  {
LABEL_522:
    if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
    {
      v226 = v217;
      v229 = v219;
      v235 = v25;
      v234[0] = v23;
      v233 = v244;
      size_4 = v245;
      v228 = KerbGlobalIsRunningIsolated;
      v186 = _tlgWrapBinary<unsigned short,2>(
               &v303,
               *((_QWORD *)v22 + 2),
               (unsigned __int64)*((unsigned __int16 *)v22 + 4) >> 1);
      v227 = v202;
      v240 = ExtendedPolicies;
      *(_QWORD *)&String2.Length = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&v228,
        (unsigned int)&byte_18012C4EF,
        v187,
        (unsigned int)&String2,
        (__int64)&v240,
        (__int64)&v227,
        v186,
        (__int64)&v228,
        (__int64)&size_4,
        (__int64)&v233,
        (__int64)v234,
        (__int64)&v235,
        (__int64)&v229,
        (__int64)&v226);
    }
    goto LABEL_525;
  }
LABEL_518:
  if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
  {
    v226 = v228;
    v229 = v216;
    v235 = v212;
    v234[0] = v244;
    v233 = v245;
    size_4 = KerbGlobalIsRunningIsolated;
    v184 = _tlgWrapBinary<unsigned short,2>(
             &v303,
             *((_QWORD *)a9 + 2),
             (unsigned __int64)*((unsigned __int16 *)a9 + 4) >> 1);
    v228 = v202;
    v227 = ExtendedPolicies;
    *(_QWORD *)&String2.Length = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&size_4,
      (unsigned int)word_18012C5AA,
      v185,
      (unsigned int)&String2,
      (__int64)&v227,
      (__int64)&v228,
      v184,
      (__int64)&size_4,
      (__int64)&v233,
      (__int64)v234,
      (__int64)&v235,
      (__int64)&v229,
      (__int64)&v226);
  }
LABEL_525:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v296 )
    KerbDereferenceLogonSession(v296);
  if ( v276 )
    KerbClientFreeStoredCred(v276);
  if ( v284 )
    KerbClientFreeStoredCred(v284);
  if ( v278 )
    KerbFree(v278);
  v188 = v289;
  if ( v289 )
  {
    do
    {
      v189 = *((_QWORD *)v188 + 3);
      if ( v189 )
        KerbFree(v189);
      v190 = *(struct PKERB_HOST_ADDRESSES_s **)v188;
      KerbFree(v188);
      v188 = v190;
    }
    while ( v190 );
  }
  if ( v24 )
    KerbFree(v24);
  if ( v215 )
    KerbFreeData(6);
  if ( v269 )
    KerbFree(v269);
  KerbFreeData(71);
  if ( v222 )
    KerbFreeData(31);
  if ( v199 )
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v236 + 2);
  if ( v246 )
    KerbFreeData(3);
  KerbFreePreAuthData(hMem);
  KerbFreeCryptList(v325[0]);
  KerbFreeKdcName(&v290);
  KerbFreeString((__int64)&v300);
  KerbFreePrincipalName(v319);
  KerbFreePrincipalName(v321);
  KerbFreeRealm(v320);
  KerbFreeData(76);
  KerbFreeKey(&v307);
  KerbFreeData(73);
  if ( v279 )
    KerbDereferenceTicketCacheEntry(v279);
  if ( v286 )
    KerbFree(v286);
  if ( v275 )
    KerbFree(v275);
  KerbFreeKey(&v271);
  if ( v252 )
    (**(void (__fastcall ***)(struct KerbKeyAgreement *, __int64))v252)(v252, 1);
  KerbFreeString((__int64)&v305);
  if ( v293 )
    KerbFree(v293);
  KerbFreeKey(v310);
  KerbFreeKey(v297);
  if ( v239 )
    KerbDereferenceTicketCacheEntry(v239);
  v290 = (struct _KERB_INTERNAL_NAME *)&v291;
  *(_QWORD *)&String2.Length = KerbFreeString;
  wistd::invoke<void (*)(KERB_KDC_REQUEST_preauth_data_s *),KERB_KDC_REQUEST_preauth_data_s * &>(&String2, &v290);
  return (unsigned int)ExtendedPolicies;
}

```

## disassembly

```asm
0x180019678  push    rbp
0x18001967a  push    rbx
0x18001967b  push    rsi
0x18001967c  push    rdi
0x18001967d  push    r12
0x18001967f  push    r13
0x180019681  push    r14
0x180019683  push    r15
0x180019685  lea     rbp, [rsp-488h]
0x18001968d  sub     rsp, 5A8h
0x180019694  mov     rax, cs:__security_cookie
0x18001969b  xor     rax, rsp
0x18001969e  mov     [rbp+4C0h+var_50], rax
0x1800196a5  mov     [rbp+4C0h+var_308], r9
0x1800196ac  mov     [rbp+4C0h+var_300], r8
0x1800196b3  mov     rbx, rdx
0x1800196b6  mov     [rbp+4C0h+var_3C0], rdx
0x1800196bd  mov     r15, rcx
0x1800196c0  mov     [rbp+4C0h+var_478], rcx
0x1800196c4  mov     rax, [rbp+4C0h+arg_20]
0x1800196cb  mov     [rbp+4C0h+var_310], rax
0x1800196d2  mov     rsi, [rbp+4C0h+arg_50]
0x1800196d9  mov     [rbp+4C0h+var_450], rsi
0x1800196dd  mov     eax, [rbp+4C0h+arg_30]
0x1800196e3  mov     dword ptr [rbp+4C0h+size], eax
0x1800196e6  mov     rax, [rbp+4C0h+arg_38]
0x1800196ed  mov     [rbp+4C0h+Src], rax
0x1800196f4  mov     r13, [rbp+4C0h+arg_40]
0x1800196fb  mov     [rbp+4C0h+var_538], r13
0x1800196ff  mov     rdi, [rbp+4C0h+String1]
0x180019706  mov     [rbp+4C0h+var_508], rdi
0x18001970a  mov     rax, [rbp+4C0h+arg_78]
0x180019711  mov     [rbp+4C0h+var_2F8], rax
0x180019718  mov     rax, [rbp+4C0h+arg_80]
0x18001971f  mov     [rbp+4C0h+var_2D8], rax
0x180019726  mov     rax, [rbp+4C0h+arg_88]
0x18001972d  mov     [rbp+4C0h+DestinationString], rax
0x180019734  mov     rax, [rbp+4C0h+arg_90]
0x18001973b  mov     [rbp+4C0h+var_398], rax
0x180019742  mov     rax, [rbp+4C0h+arg_98]
0x180019749  mov     [rbp+4C0h+var_328], rax
0x180019750  xor     r14d, r14d
0x180019753  mov     [rbp+4C0h+var_4B8], r14d
0x180019757  mov     dword ptr [rbp+4C0h+var_528], r14d
0x18001975b  xor     edx, edx; Val
0x18001975d  mov     r8d, 0C0h; Size
0x180019763  lea     rcx, [rbp+4C0h+var_190]; void *
0x18001976a  call    memset_0
0x18001976f  mov     qword ptr [rbp+4C0h+var_4F4+0Ch], r14
0x180019773  mov     [rbp+4C0h+var_468], r14
0x180019777  mov     [rbp+4C0h+var_318], r14
0x18001977e  mov     [rbp+4C0h+var_2D0], r14
0x180019785  mov     [rbp+4C0h+var_340], r14
0x18001978c  mov     [rbp+4C0h+var_338], r14
0x180019793  mov     [rbp+4C0h+var_2E8], r14
0x18001979a  mov     [rbp+4C0h+var_2E0], r14
0x1800197a1  mov     [rbp+4C0h+var_4F4+5], r14b
0x1800197a5  mov     [rbp+4C0h+pCertContext], r14
0x1800197ac  mov     [rbp+4C0h+var_500], r14
0x1800197b0  mov     [rbp+4C0h+var_430], r14
0x1800197b7  mov     qword ptr [rbp+4C0h+var_470], r14
0x1800197bb  mov     [rbp+4C0h+var_3E8], r14
0x1800197c2  mov     [rbp+4C0h+var_2C0], r14
0x1800197c9  mov     [rbp+4C0h+var_4D8], r14
0x1800197cd  xorps   xmm0, xmm0
0x1800197d0  xor     eax, eax
0x1800197d2  movups  [rbp+4C0h+var_368], xmm0
0x1800197d9  movups  [rbp+4C0h+var_358], xmm0
0x1800197e0  mov     [rbp+4C0h+var_348], rax
0x1800197e7  mov     [rbp+4C0h+var_2C8], rax
0x1800197ee  mov     [rbp+4C0h+var_3D8], rax
0x1800197f5  movups  xmmword ptr [rbp+4C0h+var_240.Length], xmm0
0x1800197fc  mov     [rbp+4C0h+var_370], r14d
0x180019803  mov     [rbp+4C0h+var_400], r14
0x18001980a  movups  xmmword ptr [rbp+4C0h+var_200.Length], xmm0
0x180019811  mov     r12d, r14d
0x180019814  mov     [rbp+4C0h+var_4F4+4], r14b
0x180019818  mov     [rbp+4C0h+var_288], r14
0x18001981f  mov     [rbp+4C0h+var_460], r14
0x180019823  movups  [rbp+4C0h+var_1C0], xmm0
0x18001982a  movups  [rbp+4C0h+var_1B0], xmm0
0x180019831  mov     [rbp+4C0h+var_1A0], rax
0x180019838  xorps   xmm1, xmm1
0x18001983b  movups  [rbp+4C0h+var_278], xmm1
0x180019842  movups  [rbp+4C0h+var_268], xmm1
0x180019849  mov     [rbp+4C0h+var_258], rax
0x180019850  movups  [rbp+4C0h+var_1E8], xmm0
0x180019857  movups  [rbp+4C0h+var_1D8], xmm0
0x18001985e  mov     [rbp+4C0h+var_1C8], rax
0x180019865  movups  xmmword ptr [rbp+4C0h+var_2A8], xmm0
0x18001986c  mov     [rbp+4C0h+var_298], rax
0x180019873  mov     [rbp+4C0h+var_420], r14
0x18001987a  mov     [rbp+4C0h+var_378], r14
0x180019881  mov     [rbp+4C0h+var_490], r14d
0x180019885  mov     qword ptr [rbp+4C0h+SystemTimeAsFileTime.dwLowDateTime], r14
0x18001988c  mov     qword ptr [rbp+4C0h+Time], r14
0x180019893  mov     [rbp+4C0h+var_250], r15
0x18001989a  mov     [rbp+4C0h+var_248], rbx
0x1800198a1  mov     [rbp+4C0h+var_280], r14
0x1800198a8  mov     [rbp+4C0h+var_330], r14
0x1800198af  mov     [rbp+4C0h+var_2F0], r14
0x1800198b6  mov     [rbp+4C0h+var_320], r14
0x1800198bd  mov     [rbp+4C0h+var_516], r14b
0x1800198c1  mov     [rbp+4C0h+var_440], r14d
0x1800198c8  movups  xmmword ptr [rbp+4C0h+var_2B8.Length], xmm0
0x1800198cf  movups  xmmword ptr [rbp+4C0h+var_3A8], xmm0
0x1800198d6  lea     rbx, WPP_GLOBAL_Control
0x1800198dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198e4  cmp     rcx, rbx
0x1800198e7  jz      short loc_180019905
0x1800198e9  test    byte ptr [rcx+1Ch], 4
0x1800198ed  jz      short loc_180019905
0x1800198ef  lea     edx, [rax+0Ch]
0x1800198f2  mov     r9, rsi
0x1800198f5  lea     r8, WPP_158d5f44375531ecadb51b1a2a87ab5b_Traceguids
0x1800198fc  mov     rcx, [rcx+10h]
0x180019900  call    WPP_SF__KERB_NAME_
0x180019905  mov     [rsp+5E0h+var_5C0], rdi
0x18001990a  lea     r9, aKerbgetauthent_14; "KerbGetAuthenticationTicket in realm %w"...
0x180019911  mov     r8d, 0B3Dh
0x180019917  lea     rdx, aKerbgetauthent_28; "KerbGetAuthenticationTicketEx"
0x18001991e  mov     ecx, 3
0x180019923  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180019928  mov     rcx, cs:WPP_GLOBAL_Control
0x18001992f  cmp     rcx, rbx
0x180019932  jz      short loc_180019952
0x180019934  test    byte ptr [rcx+1Ch], 4
0x180019938  jz      short loc_180019952
0x18001993a  mov     edx, 0Dh
0x18001993f  mov     r9, r13
0x180019942  lea     r8, WPP_158d5f44375531ecadb51b1a2a87ab5b_Traceguids
0x180019949  mov     rcx, [rcx+10h]
0x18001994d  call    WPP_SF__KERB_NAME_
0x180019952  mov     sil, r14b
0x180019955  xor     ecx, ecx
0x180019957  mov     [rbp+4C0h+var_4F5], cl
0x18001995a  mov     [rbp+4C0h+var_4F7], cl
0x18001995d  mov     [rbp+4C0h+var_438], ecx
0x180019963  mov     [rbp+4C0h+var_43C], ecx
0x180019969  mov     rax, [rbp+4C0h+var_398]
0x180019970  test    rax, rax
0x180019973  jz      short loc_180019977
0x180019975  mov     [rax], ecx
0x180019977  xor     edx, edx; SourceString
0x180019979  mov     rcx, [rbp+4C0h+DestinationString]; DestinationString
0x180019980  call    cs:__imp_RtlInitUnicodeString
0x180019986  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NGCKeyUsagePhase2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NGCKeyUsagePhase2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase2> `wil::Feature<__WilFeatureTraits_Feature_NGCKeyUsagePhase2>::GetImpl(void)'::`2'::impl
0x18001998d  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_NGCKeyUsagePhase2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase2>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180019992  mov     eax, [rbp+4C0h+arg_58]
0x180019998  and     eax, 4
0x18001999b  mov     [rbp+4C0h+var_4AC], eax
0x18001999e  jnz     loc_180019A38
0x1800199a4  cmp     [rbp+4C0h+arg_70], r14b
0x1800199ab  jnz     loc_180019A38
0x1800199b1  xorps   xmm0, xmm0
0x1800199b4  movups  xmmword ptr [rbp+4C0h+String2.Length], xmm0
0x1800199b8  lea     rax, [rbp+4C0h+String2]
0x1800199bc  mov     [rsp+5E0h+var_5C0], rax; struct _UNICODE_STRING *
0x1800199c1  mov     r9, [rbp+4C0h+Src]; unsigned __int8 *
0x1800199c8  mov     r8d, dword ptr [rbp+4C0h+size]; unsigned int
0x1800199cc  mov     rdx, [rbp+4C0h+var_450]; struct _KERB_INTERNAL_NAME *
0x1800199d0  mov     rcx, r15; struct _KERB_LOGON_SESSION *
0x1800199d3  call    ?KerbGetS4UClientRealm@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_INTERNAL_NAME@@KPEAEPEAU_UNICODE_STRING@@@Z; KerbGetS4UClientRealm(_KERB_LOGON_SESSION *,_KERB_INTERNAL_NAME *,ulong,uchar *,_UNICODE_STRING *)
0x1800199d8  mov     ebx, eax
0x1800199da  xor     eax, eax
0x1800199dc  test    ebx, ebx
0x1800199de  jz      short loc_1800199EB
0x1800199e0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800199e5  xor     eax, eax
0x1800199e7  test    ebx, ebx
0x1800199e9  js      short loc_180019A2F
0x1800199eb  cmp     [rbp+4C0h+String2.Length], ax
0x1800199ef  jz      short loc_180019A2F
0x1800199f1  mov     ebx, 1
0x1800199f6  mov     r8b, bl; CaseInsensitive
0x1800199f9  lea     rdx, [rbp+4C0h+String2]; String2
0x1800199fd  mov     rcx, rdi; String1
0x180019a00  call    cs:__imp_RtlEqualUnicodeString
0x180019a06  test    al, al
0x180019a08  jnz     short loc_180019A27
0x180019a0a  mov     [rbp+4C0h+var_52C], r14b
0x180019a0e  movups  xmm0, xmmword ptr [rbp+4C0h+String2.Length]
0x180019a12  mov     rax, [rbp+4C0h+DestinationString]
0x180019a19  movdqu  xmmword ptr [rax], xmm0
0x180019a1d  mov     edi, 0C0000064h
0x180019a22  jmp     loc_18001D81E
0x180019a27  mov     [rbp+4C0h+String2.Buffer], 0
0x180019a2f  lea     rcx, [rbp+4C0h+String2]
0x180019a33  call    KerbFreeString
0x180019a38  mov     [rbp+4C0h+var_3F4], 0
0x180019a42  mov     ebx, 40810010h
0x180019a47  lea     rcx, stru_180144D18; CriticalSection
0x180019a4e  call    cs:__imp_RtlEnterCriticalSection
0x180019a54  lea     r8, [rbp+4C0h+var_4F6]; unsigned __int8 *
0x180019a58  lea     rdx, [rbp+4C0h+var_3E8]; struct _KERB_MIT_REALM **
0x180019a5f  mov     rcx, rdi; String1
0x180019a62  call    ?KerbLookupMitRealm@@YAEPEAU_UNICODE_STRING@@PEAPEAU_KERB_MIT_REALM@@PEAE@Z; KerbLookupMitRealm(_UNICODE_STRING *,_KERB_MIT_REALM * *,uchar *)
0x180019a67  test    al, al
0x180019a69  jz      short loc_180019A7D
0x180019a6b  mov     rax, [rbp+4C0h+var_3E8]
0x180019a72  mov     edi, [rax+18h]
0x180019a75  mov     [rbp+4C0h+var_3F4], edi
0x180019a7b  jmp     short loc_180019A83
0x180019a7d  mov     edi, [rbp+4C0h+var_3F4]
0x180019a83  lea     rcx, stru_180144D18; CriticalSection
0x180019a8a  call    cs:__imp_RtlLeaveCriticalSection
0x180019a90  cmp     [rbp+4C0h+var_3E8], 0
0x180019a98  jz      short loc_180019AAA
0x180019a9a  movzx   ebx, dil
0x180019a9e  and     ebx, 8
0x180019aa1  shl     ebx, 0Dh
0x180019aa4  or      ebx, 40800010h
0x180019aaa  mov     ecx, ebx
0x180019aac  btr     ecx, 10h
0x180019ab0  xor     edi, edi
0x180019ab2  test    byte ptr [rbp+4C0h+arg_58], 2
0x180019ab9  cmovz   ecx, ebx
0x180019abc  mov     eax, ecx
0x180019abe  shr     eax, 18h
0x180019ac1  mov     [rbp+4C0h+var_4F4], al
0x180019ac4  mov     eax, ecx
0x180019ac6  shr     eax, 10h
0x180019ac9  mov     [rbp+4C0h+var_4F4+1], al
0x180019acc  mov     eax, ecx
0x180019ace  shr     eax, 8
0x180019ad1  mov     [rbp+4C0h+var_4F4+2], al
0x180019ad4  mov     [rbp+4C0h+var_4F4+3], cl
0x180019ad7  mov     eax, dword ptr [rbp+4C0h+var_4F4]
0x180019ada  mov     [rbp+4C0h+var_370], eax
0x180019ae0  lea     rax, [rbp+4C0h+var_370]
0x180019ae7  mov     [rbp+4C0h+var_168], rax
0x180019aee  mov     [rbp+4C0h+var_170], 20h ; ' '
0x180019af8  mov     rax, cs:?KerbGlobalWillNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalWillNeverTime
0x180019aff  mov     [rbp+4C0h+var_2D0], rax
0x180019b06  lea     r8, [rbp+4C0h+var_2D0]
0x180019b0d  xor     edx, edx
0x180019b0f  lea     rcx, [rbp+4C0h+var_12A]
0x180019b16  call    KerbConvertLargeIntToGeneralizedTime
0x180019b1b  lea     r8, [rbp+4C0h+var_2D0]
0x180019b22  xor     edx, edx
0x180019b24  lea     rcx, [rbp+4C0h+var_11C]
0x180019b2b  call    KerbConvertLargeIntToGeneralizedTime
0x180019b30  lea     eax, [rdi+10h]
0x180019b33  or      [rbp+4C0h+var_178], ax
0x180019b3a  mov     [rbp+4C0h+var_3F8], edi
0x180019b40  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180019b47  lea     rcx, [rbp+4C0h+var_3F8]
0x180019b4e  mov     rax, [rax+1B0h]
0x180019b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b5a  lea     rax, [r15+50h]
0x180019b5e  mov     [rbp+4C0h+CriticalSection], rax
0x180019b65  mov     rcx, rax; CriticalSection
0x180019b68  call    cs:__imp_RtlEnterCriticalSection
0x180019b6e  mov     [rbp+4C0h+var_52C], 1
0x180019b72  mov     rax, [rbp+4C0h+var_308]
0x180019b79  test    rax, rax
0x180019b7c  jz      short loc_180019BDD
0x180019b7e  mov     [rbp+4C0h+var_52A], 1
0x180019b82  mov     r13, [rax+40h]
0x180019b86  mov     [rbp+4C0h+var_4C0], r13
0x180019b8a  lea     rax, [r13+10h]
0x180019b8e  mov     [rsp+5E0h+var_5B8], r13
0x180019b93  mov     [rsp+5E0h+var_5C0], rax
0x180019b98  lea     r9, aKerbgetauthent_6; "KerbGetAuthenticationTicket using extra"...
0x180019b9f  mov     r8d, 0BE1h
0x180019ba5  lea     rdx, aKerbgetauthent_28; "KerbGetAuthenticationTicketEx"
0x180019bac  lea     ecx, [rdi+8]
0x180019baf  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180019bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bbb  lea     rax, WPP_GLOBAL_Control
0x180019bc2  cmp     rcx, rax
0x180019bc5  jz      loc_180019C90
0x180019bcb  test    byte ptr [rcx+1Ch], 80h
0x180019bcf  jz      loc_180019C90
0x180019bd5  lea     edx, [rdi+0Eh]
0x180019bd8  jmp     loc_180019C7C
0x180019bdd  mov     rbx, [rbp+4C0h+var_3C0]
0x180019be4  test    rbx, rbx
0x180019be7  jz      loc_180019CE6
0x180019bed  mov     rcx, [rbx+48h]; struct _KERB_PRIMARY_CREDENTIAL *
0x180019bf1  test    rcx, rcx
0x180019bf4  jz      loc_180019CE6
0x180019bfa  test    dword ptr [rbx+40h], 100000h
0x180019c01  jz      short loc_180019C26
0x180019c03  cmp     dword ptr [r15+40h], 3E7h
0x180019c0b  jnz     short loc_180019C26
0x180019c0d  cmp     [r15+44h], edi
0x180019c11  jnz     short loc_180019C26
0x180019c13  lea     rdx, [r15+78h]; struct _KERB_PRIMARY_CREDENTIAL *
0x180019c17  call    ?KerbReplacePasswords@@YAJPEAU_KERB_PRIMARY_CREDENTIAL@@0@Z; KerbReplacePasswords(_KERB_PRIMARY_CREDENTIAL *,_KERB_PRIMARY_CREDENTIAL *)
0x180019c1c  mov     edi, eax
0x180019c1e  test    eax, eax
0x180019c20  js      loc_18001D819
0x180019c26  mov     [rbp+4C0h+var_52A], 1
0x180019c2a  mov     r13, [rbx+48h]
0x180019c2e  mov     [rbp+4C0h+var_4C0], r13
0x180019c32  lea     rax, [r13+10h]
0x180019c36  mov     [rsp+5E0h+var_5B8], r13
0x180019c3b  mov     [rsp+5E0h+var_5C0], rax
0x180019c40  lea     r9, aKerbgetauthent_15; "KerbGetAuthenticationTicket using suppl"...
  ... truncated ...
```
