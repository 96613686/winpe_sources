# KerbGetServiceTicketByS4UProxy(_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_TICKET_CACHE_ENTRY *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,ulong,ulong,ulong,KERB_ERROR *,PKERB_AUTHORIZATION_DATA_s *,KERB_TGT_REPLY *,_KERB_TICKET_CACHE_ENTRY * *,_GUID *)

- ea: `0x1800566a8`
- end: `0x180057f51`
- name: `?KerbGetServiceTicketByS4UProxy@@YAJPEAU_KERB_LOGON_SESSION@@0PEAU_KERB_CREDENTIAL@@PEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@KKKPEAUKERB_ERROR@@PEAUPKERB_AUTHORIZATION_DATA_s@@PEAUKERB_TGT_REPLY@@PEAPEAU3@PEAU_GUID@@@Z`
- size: `6313`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, struct _KERB_TICKET_CACHE_ENTRY *, struct _KERB_INTERNAL_NAME *, UNICODE_STRING *String1, unsigned int, char, unsigned int, struct KERB_ERROR *, struct PKERB_AUTHORIZATION_DATA_s *, struct KERB_TGT_REPLY *, struct _KERB_TICKET_CACHE_ENTRY **, struct _GUID *)`
- caller_count: `2`
- callee_count: `35`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180021574`
- `0x1800cc8a8`

## callees

- `0x180005f38`
- `0x18000623c`
- `0x1800063e8`
- `0x1800068d0`
- `0x1800069e0`
- `0x180007e00`
- `0x18000b300`
- `0x1800113f0`
- `0x1800190c0`
- `0x18002a150`
- `0x18002a2bc`
- `0x18002f8b0`
- `0x180031e60`
- `0x180034d5c`
- `0x1800376ec`
- `0x180037aa0`
- `0x18003d3f0`
- `0x18003e9d8`
- `0x180040fb8`
- `0x18004ed20`
- `0x1800541b0`
- `0x1800566a8`
- `0x180058f14`
- `0x18005e9a0`
- `0x18006557c`
- `0x18006e90c`
- `0x18007108c`
- `0x18008a304`
- `0x18008b70c`
- `0x180091118`
- `0x18009e830`
- `0x18009f728`
- `0x18009f7a4`
- `0x1800b4190`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005677e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005677e`
- `ntdll!RtlEqualUnicodeString` at `0x180056bfb`
- `ntdll!RtlEqualUnicodeString` at `0x18005722b`
- `ntdll!RtlEqualUnicodeString` at `0x180057252`
- `ntdll!RtlEqualUnicodeString` at `0x18005743d`
- `ntdll!RtlEqualUnicodeString` at `0x180056bfb`
- `ntdll!RtlEqualUnicodeString` at `0x18005722b`
- `ntdll!RtlEqualUnicodeString` at `0x180057252`
- `ntdll!RtlEqualUnicodeString` at `0x18005743d`
- `ntdll!RtlEnterCriticalSection` at `0x18005679a`
- `ntdll!RtlEnterCriticalSection` at `0x180056b21`
- `ntdll!RtlEnterCriticalSection` at `0x18005718e`
- `ntdll!RtlEnterCriticalSection` at `0x18005739a`
- `ntdll!RtlEnterCriticalSection` at `0x1800579b3`
- `ntdll!RtlEnterCriticalSection` at `0x180057b91`
- `ntdll!RtlEnterCriticalSection` at `0x180057d09`
- `ntdll!RtlEnterCriticalSection` at `0x18005679a`
- `ntdll!RtlEnterCriticalSection` at `0x180056b21`
- `ntdll!RtlEnterCriticalSection` at `0x18005718e`
- `ntdll!RtlEnterCriticalSection` at `0x18005739a`
- `ntdll!RtlEnterCriticalSection` at `0x1800579b3`
- `ntdll!RtlEnterCriticalSection` at `0x180057b91`
- `ntdll!RtlEnterCriticalSection` at `0x180057d09`
- `ntdll!RtlLeaveCriticalSection` at `0x180056b09`
- `ntdll!RtlLeaveCriticalSection` at `0x180056b44`
- `ntdll!RtlLeaveCriticalSection` at `0x1800571b1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800573fb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800579cd`
- `ntdll!RtlLeaveCriticalSection` at `0x180057c0b`
- `ntdll!RtlLeaveCriticalSection` at `0x180057d95`
- `ntdll!RtlLeaveCriticalSection` at `0x180057ecf`
- `ntdll!RtlLeaveCriticalSection` at `0x180056b09`
- `ntdll!RtlLeaveCriticalSection` at `0x180056b44`
- `ntdll!RtlLeaveCriticalSection` at `0x1800571b1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800573fb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800579cd`
- `ntdll!RtlLeaveCriticalSection` at `0x180057c0b`
- `ntdll!RtlLeaveCriticalSection` at `0x180057d95`
- `ntdll!RtlLeaveCriticalSection` at `0x180057ecf`

## string_xrefs

- `0x180056a59`: `Found SPN cache entry - %wZ\n`
- `0x180057aa4`: `Failed to get TGS ticket for service 0x%x`
- `0x180057dc4`: `Kdc GetServiceTicket: trying to crack zero length name.\n`
- `0x18005681e`: `KerbGetServiceTicketByS4UProxy`
- `0x180057dd1`: `KerbGetServiceTicketByS4UProxy`
- `0x1800567ee`: `Attempting S4U2Proxy: caller logon session %#x:%x, caller process id %d, logon session %#x:%x, client crential %wZ@%wZ\n`
- `0x18005692e`: `caller does not support S4U2Proxy: %#x, cache flags %#x\n`
- `0x180056980`: `caller does not support S4U2Proxy for the target: %#x, cache flags %#x\n`
- `0x180056e35`: `Found S4U ticket cache entry %p\n`
- `0x180056ed4`: `KerbGetSpnCacheStatus failed %#x\n`
- `0x1800577cf`: `KerbGetServiceTicketByS4UProxy xrealm proxy middle tier %wZ, backend %wZ\n`
- `0x180056c0d`: `KerbGetServiceTicketByS4UProxy EvidenceTicketCacheEntry %p\n`
- `0x180057976`: `KerbSetS4U2ProxyCacheEntry failed: %#x\n`
- `0x180057a56`: `KerbSetS4U2ProxyCacheEntry failed: %#x\n`
- `0x180057b15`: `KerbSetS4U2ProxyCacheEntry failed: %#x\n`
- `0x180057a17`: `Failed to get service ticket in identity of middle tier: status 0x%08X\n`
- `0x180057a7e`: `KerbGetServiceTicketByS4UProxy: failed to get referral TGT to destination realm.\n`
- `0x180057c77`: `Failed to get TGS S4U ticket for service 0x%x`

## pseudocode

```c
__int64 __fastcall KerbGetServiceTicketByS4UProxy(
        struct _RTL_CRITICAL_SECTION *a1,
        struct _KERB_LOGON_SESSION *a2,
        struct _KERB_CREDENTIAL *a3,
        struct _KERB_TICKET_CACHE_ENTRY *a4,
        struct _KERB_INTERNAL_NAME *a5,
        UNICODE_STRING *String1,
        unsigned int a7,
        char a8,
        unsigned int a9,
        struct KERB_ERROR *a10,
        struct PKERB_AUTHORIZATION_DATA_s *a11,
        struct KERB_TGT_REPLY *a12,
        struct _KERB_TICKET_CACHE_ENTRY **a13,
        struct _GUID *a14)
{
  struct _KERB_TICKET_CACHE_ENTRY *TicketCacheEntry; // r14
  struct _KERB_TICKET_CACHE_ENTRY *v17; // rsi
  struct _RTL_CRITICAL_SECTION *v18; // r13
  char v20; // di
  struct _RTL_CRITICAL_SECTION *v21; // r13
  int TicketGrantingTicket; // ebx
  int S4UProxyCred; // eax
  unsigned int v24; // eax
  const char *v25; // r9
  __int64 v26; // r8
  unsigned __int8 v27; // r13
  int SpnCacheStatus; // eax
  int v29; // ecx
  struct _KERB_LOGON_SESSION *v30; // rdi
  struct _KERB_PRIMARY_CREDENTIAL *v31; // rsi
  unsigned __int8 v32; // r8
  struct _KERB_TICKET_CACHE_ENTRY *v33; // rdx
  int v34; // esi
  int v35; // r13d
  char v36; // cl
  int v37; // ebx
  unsigned int v38; // edx
  struct _KERB_PRIMARY_CREDENTIAL *v39; // rbx
  const char *v40; // r9
  __int64 v41; // r8
  __int64 v42; // rcx
  unsigned int v43; // eax
  char v44; // dl
  const void *v45; // rcx
  int v46; // edi
  struct _RTL_CRITICAL_SECTION *v47; // rbx
  struct _KERB_PRIMARY_CREDENTIAL *v48; // rsi
  int ServiceTicket; // eax
  int v50; // ebx
  unsigned __int8 v51; // r8
  struct _KERB_TICKET_CACHE_ENTRY *v52; // r14
  int v53; // r8d
  unsigned int v54; // r13d
  struct _KERB_TICKET_CACHE_ENTRY *v55; // rdi
  struct _KERB_INTERNAL_NAME *v56; // r13
  PVOID *v57; // rcx
  int v58; // ebx
  int TgsTicket; // ebx
  unsigned int v60; // edi
  int v61; // edi
  const void *v62; // rcx
  int v63; // edi
  const void *v64; // rcx
  struct _KERB_S4U2PROXY_CACHE *v65; // rcx
  int v66; // eax
  int v67; // eax
  int v68; // eax
  __int64 v69; // r8
  struct _KERB_TICKET_CACHE *v70; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v71; // r14
  const void *v72; // rcx
  struct _KERB_TICKET_CACHE_ENTRY **v73; // rcx
  struct _KERB_TICKET_CACHE *v74; // rax
  struct _UNICODE_STRING *v75; // r9
  struct _UNICODE_STRING *v77; // [rsp+28h] [rbp-110h]
  struct _UNICODE_STRING *v78; // [rsp+28h] [rbp-110h]
  struct _UNICODE_STRING *v79; // [rsp+30h] [rbp-108h]
  struct _UNICODE_STRING *v80; // [rsp+30h] [rbp-108h]
  struct _RTL_CRITICAL_SECTION *CriticalSection; // [rsp+B8h] [rbp-80h]
  struct _KERB_TICKET_CACHE_ENTRY *v82; // [rsp+C0h] [rbp-78h] BYREF
  struct _KERB_PRIMARY_CREDENTIAL *v83; // [rsp+C8h] [rbp-70h] BYREF
  struct KERB_ENCRYPTED_KDC_REPLY *v84; // [rsp+D0h] [rbp-68h] BYREF
  unsigned int v85; // [rsp+D8h] [rbp-60h] BYREF
  struct KERB_KDC_REPLY *v86; // [rsp+E0h] [rbp-58h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *TicketCacheEntryByRealm; // [rsp+E8h] [rbp-50h] BYREF
  UNICODE_STRING v88; // [rsp+F8h] [rbp-40h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v89; // [rsp+108h] [rbp-30h]
  struct _KERB_TICKET_CACHE_ENTRY *v90; // [rsp+110h] [rbp-28h]
  HLOCAL hMem; // [rsp+118h] [rbp-20h] BYREF
  struct _UNICODE_STRING v92; // [rsp+120h] [rbp-18h] BYREF
  int v93; // [rsp+130h] [rbp-8h]
  unsigned int v94; // [rsp+134h] [rbp-4h]
  int v95; // [rsp+138h] [rbp+0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+140h] [rbp+8h] BYREF
  struct _KERB_EXTRA_CRED *v97; // [rsp+148h] [rbp+10h] BYREF
  UNICODE_STRING String2; // [rsp+150h] [rbp+18h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v99; // [rsp+160h] [rbp+28h] BYREF
  struct _KERB_INTERNAL_NAME *v100[2]; // [rsp+168h] [rbp+30h] BYREF
  struct _UNICODE_STRING v101; // [rsp+178h] [rbp+40h] BYREF
  struct _UNICODE_STRING v102; // [rsp+188h] [rbp+50h] BYREF
  PRTL_CRITICAL_SECTION v103; // [rsp+198h] [rbp+60h]
  __int128 v104; // [rsp+1A0h] [rbp+68h] BYREF
  __int64 v105; // [rsp+1B0h] [rbp+78h]
  _BYTE v106[24]; // [rsp+1B8h] [rbp+80h] BYREF
  __int64 v107; // [rsp+1D0h] [rbp+98h]
  int v112; // [rsp+278h] [rbp+140h]
  unsigned int v113; // [rsp+288h] [rbp+150h]

  hMem = 0;
  v82 = 0;
  TicketCacheEntryByRealm = 0;
  v105 = 0;
  v90 = 0;
  v99 = 0;
  v104 = 0;
  TicketCacheEntry = 0;
  v89 = 0;
  v17 = 0;
  v86 = 0;
  v84 = 0;
  memset_0(v106, 0, 0x48u);
  *(_QWORD *)&v88.Length = 0;
  v92 = 0;
  v88.Buffer = 0;
  *(_QWORD *)&v102.Length = 0;
  v102.Buffer = 0;
  *(_QWORD *)&v101.Length = 0;
  v101.Buffer = 0;
  v100[0] = 0;
  v83 = 0;
  v97 = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  LODWORD(a11) = 0;
  SystemTimeAsFileTime = 0;
  LODWORD(a14) = KerbGlobalMaxReferralCount;
  v85 = 0;
  a9 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v18 = a1 + 2;
  *(_QWORD *)&SystemTimeAsFileTime += KerbGlobalS4UTicketLifetime.QuadPart;
  CriticalSection = a1 + 2;
  RtlEnterCriticalSection(a1 + 2);
  v20 = 1;
  if ( !*((_WORD *)a5 + 1) || !*((_WORD *)a5 + 4) )
  {
    KerbTracerT::Log(
      1,
      "KerbGetServiceTicketByS4UProxy",
      5269,
      "Kdc GetServiceTicket: trying to crack zero length name.\n");
    TicketGrantingTicket = -2146893053;
    goto LABEL_196;
  }
  v21 = a1 + 3;
  ((void (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v104);
  KerbTracerT::Log(
    21,
    "KerbGetServiceTicketByS4UProxy",
    5278,
    "Attempting S4U2Proxy: caller logon session %#x:%x, caller process id %d, logon session %#x:%x, client crential %wZ@%wZ\n",
    *((_DWORD *)a2 + 17),
    *((_DWORD *)a2 + 16),
    (_DWORD)v104,
    HIDWORD(a1[1].LockSemaphore),
    LODWORD(a1[1].LockSemaphore),
    &a1[3],
    &a1[3].OwningThread);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
    WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids, a5);
  if ( ((__int64)a1[22].LockSemaphore & 0x100) == 0 )
  {
    TicketGrantingTicket = -2146893042;
    KerbTracerT::Log(
      21,
      "KerbGetServiceTicketByS4UProxy",
      5285,
      "logon session %#x:%x is not OK for delegation: %#x\n",
      HIDWORD(a1[1].LockSemaphore),
      LODWORD(a1[1].LockSemaphore),
      -2146893042);
LABEL_8:
    v18 = CriticalSection;
LABEL_196:
    v44 = 0;
    goto LABEL_197;
  }
  S4UProxyCred = KerbGetS4UProxyCred(
                   (struct _RTL_CRITICAL_SECTION *)a2,
                   *((struct _KERB_INTERNAL_NAME **)a4 + 4),
                   &v83,
                   &v97);
  TicketGrantingTicket = S4UProxyCred;
  if ( S4UProxyCred < 0 )
  {
    KerbTracerT::Log(1, "KerbGetServiceTicketByS4UProxy", 5298, "KerbGetS4UProxyCred failed %#x\n", S4UProxyCred);
    goto LABEL_8;
  }
  KerbAgeS4U2ProxyCache((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488), 0, 1u);
  KerbGetS4U2ProxyCacheFlags((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488), &a9);
  v24 = a9;
  if ( (a9 & 1) != 0 )
  {
    v25 = "caller does not support S4U2Proxy: %#x, cache flags %#x\n";
    v26 = 5317;
LABEL_13:
    LODWORD(v79) = v24;
    TicketGrantingTicket = -2146893042;
    LODWORD(v77) = -2146893042;
    KerbTracerT::Log(21, "KerbGetServiceTicketByS4UProxy", v26, v25, v77, v79);
    goto LABEL_8;
  }
  KerbGetS4U2ProxyCacheEntryFlags((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488), a5, &a9);
  v24 = a9;
  if ( (a9 & 0x10000) != 0 )
  {
    v25 = "caller does not support S4U2Proxy for the target: %#x, cache flags %#x\n";
    v26 = 5330;
    goto LABEL_13;
  }
  if ( a12 || (a7 & 1) != 0 )
  {
    v27 = 0;
  }
  else
  {
    TicketCacheEntry = KerbLocateTicketCacheEntryEx((struct _KERB_TICKET_CACHE *)&v21[4], a5, String1, 0);
    v82 = TicketCacheEntry;
    v27 = 1;
  }
  if ( TicketCacheEntry )
  {
    if ( a10 && *((_DWORD *)a10 + 13) == 41 )
    {
      KerbRemoveTicketCacheEntry(TicketCacheEntry);
    }
    else
    {
      v43 = KerbConvertKdcOptionsToTicketFlags(0);
      if ( (v43 & *((_DWORD *)TicketCacheEntry + 40)) == v43
        && !KerbTicketIsExpiring(TicketCacheEntry, &KerbGlobalSkewTime) )
      {
        *a13 = TicketCacheEntry;
        KerbTracerT::Log(
          21,
          "KerbGetServiceTicketByS4UProxy",
          5407,
          "Found S4U ticket cache entry %p\n",
          (const void *)WORD1(TicketCacheEntry));
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
          WPP_SF__KERB_NAME_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids,
            *((_QWORD *)TicketCacheEntry + 5));
        KerbTracerT::Log(21, "KerbGetServiceTicketByS4UProxy", 5409, "Realm - %wZ\n", (char *)TicketCacheEntry + 48);
        TicketCacheEntry = 0;
LABEL_64:
        v18 = CriticalSection;
        goto LABEL_196;
      }
    }
    KerbDereferenceTicketCacheEntry(TicketCacheEntry);
    TicketCacheEntry = 0;
    v82 = 0;
  }
  if ( (a7 & 0x2000000) != 0 && !String1->Buffer )
  {
    SpnCacheStatus = KerbGetSpnCacheStatus(a5, v83, &v101);
    TicketGrantingTicket = SpnCacheStatus;
    if ( SpnCacheStatus < 0 )
    {
      if ( SpnCacheStatus != -1073741198 )
      {
        KerbTracerT::Log(
          19,
          "KerbGetServiceTicketByS4UProxy",
          5441,
          "KerbGetSpnCacheStatus failed %#x\n",
          SpnCacheStatus);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
          WPP_SF__KERB_NAME_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids,
            a5);
        v18 = CriticalSection;
        v44 = 1;
        goto LABEL_197;
      }
    }
    else
    {
      KerbFreeString(&v88);
      v88 = v101;
      v101 = 0;
      KerbTracerT::Log(19, "KerbGetServiceTicketByS4UProxy", 5436, "Found SPN cache entry - %wZ\n", &v88);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids, a5);
    }
  }
  TicketGrantingTicket = KerbAddAuthzDataForTGS(a3, 0, (struct PKERB_AUTHORIZATION_DATA_s **)&hMem);
  if ( TicketGrantingTicket < 0 )
    goto LABEL_64;
  v29 = v27;
  if ( (a7 & 1) != 0 )
    v29 = 0;
  v94 = 0;
  v95 = v29;
  LOBYTE(a9) = 0;
  v112 = 0;
  v93 = 0;
  v113 = a7 | 0xC00000;
  RtlLeaveCriticalSection(CriticalSection);
  v30 = a2;
  v103 = (PRTL_CRITICAL_SECTION)((char *)a2 + 80);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a2 + 2);
  v31 = v83;
  TicketCacheEntryByRealm = KerbLocateTicketCacheEntryByRealm(
                              (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 240),
                              0,
                              1u);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a2 + 2);
LABEL_35:
  while ( 2 )
  {
    if ( !TicketCacheEntryByRealm )
    {
      TicketGrantingTicket = KerbGetTicketGrantingTicket(v30, 0, 0, v97, 0, 0, 0, &TicketCacheEntryByRealm, 0, 0);
      if ( TicketGrantingTicket < 0 )
      {
        KerbTracerT::Log(1, "KerbGetServiceTicketByS4UProxy", 5531, "Failed to get primary TGT from logon session\n");
        goto LABEL_136;
      }
    }
    if ( !String2.Buffer )
    {
      TicketGrantingTicket = KerbDuplicateStringEx(&String2, (const struct _UNICODE_STRING *)v31 + 1, v32);
      if ( TicketGrantingTicket < 0 )
        goto LABEL_136;
    }
    if ( !v107 && (unsigned int)KerbDuplicateTicket(v106, (char *)a4 + 272) )
    {
      TicketGrantingTicket = -1073741801;
      goto LABEL_136;
    }
    if ( a12 && !RtlEqualUnicodeString(String1, &String2, 1u) )
    {
      KerbTracerT::Log(
        21,
        "KerbGetServiceTicketByS4UProxy",
        5579,
        "KerbGetServiceTicketByS4UProxy xrealm proxy middle tier %wZ, backend %wZ\n",
        &String2,
        String1);
      TicketGrantingTicket = -2146892969;
      goto LABEL_136;
    }
    KerbTracerT::Log(
      21,
      "KerbGetServiceTicketByS4UProxy",
      5590,
      "KerbGetServiceTicketByS4UProxy EvidenceTicketCacheEntry %p\n",
      (const void *)WORD1(a4));
    v33 = a4;
    v34 = v112;
    v35 = v93;
    v36 = a9;
    while ( 1 )
    {
      if ( (*((_DWORD *)v33 + 40) & 0x40000000) == 0 || (v37 = 0, v36) )
        v37 = 0x1000000;
      KerbFreeData(74);
      KerbFreeData(76);
      v86 = 0;
      v84 = 0;
      KerbFreeString(&v92);
      TicketGrantingTicket = KerbGetTgsTicketEx(
                               0,
                               0,
                               0,
                               TicketCacheEntryByRealm,
                               a5,
                               v113 | v37,
                               0,
                               0,
                               (struct PKERB_AUTHORIZATION_DATA_s *)hMem,
                               0,
                               0,
                               0,
                               a12,
                               (struct KERB_TICKET *)v106,
                               (struct _KERB_TICKET_CACHE_ENTRY *)((char *)a4 + 168),
                               (union _LARGE_INTEGER *)&SystemTimeAsFileTime,
                               &v86,
                               &v84,
                               (unsigned int *)&a11,
                               &v92,
                               &v85,
                               0);
      if ( TicketGrantingTicket >= 0 )
        break;
      if ( ((unsigned __int8)a11 & 2) != 0 && (int)a14 > 0 )
      {
        if ( TicketCacheEntryByRealm )
          v45 = (const void *)WORD1(TicketCacheEntryByRealm);
        else
          v45 = 0;
        KerbTracerT::Log(2, "KerbGetServiceTicketByS4UProxy", 5643, "Doing s4u TGT retry 1 - %p\n", v45);
        KerbRemoveTicketCacheEntry(TicketCacheEntryByRealm);
        KerbDereferenceTicketCacheEntry(TicketCacheEntryByRealm);
        LODWORD(a14) = (_DWORD)a14 - 1;
        TicketCacheEntryByRealm = 0;
        goto LABEL_80;
      }
      if ( ((unsigned __int8)a11 & 0x40) != 0 )
      {
        RtlEnterCriticalSection(CriticalSection);
        LODWORD(a1[22].LockSemaphore) &= ~0x100u;
        RtlLeaveCriticalSection(CriticalSection);
        TicketGrantingTicket = -2146893042;
        KerbTracerT::Log(
          21,
          "KerbGetServiceTicketByS4UProxy",
          5674,
          "logon session %#x:%x is not delegatable due to sensitive client: %#x\n",
          HIDWORD(a1[1].LockSemaphore),
          LODWORD(a1[1].LockSemaphore),
          -2146893042);
        goto LABEL_136;
      }
      if ( ((unsigned __int8)a11 & 0x20) != 0 )
      {
        v66 = KerbSetS4U2ProxyCacheEntry(
                (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488),
                a5,
                0x10000u,
                TicketGrantingTicket);
        TicketGrantingTicket = v66;
        if ( v66 >= 0 )
        {
          TicketGrantingTicket = -2146893042;
          LODWORD(v78) = -2146893042;
          KerbTracerT::Log(
            21,
            "KerbGetServiceTicketByS4UProxy",
            5698,
            "caller logon session failed to delegate due to target not found supporting cross domain constraint delegation: %#x\n",
            v78);
        }
        else
        {
          LODWORD(v78) = v66;
          KerbTracerT::Log(1, "KerbGetServiceTicketByS4UProxy", 5693, "KerbSetS4U2ProxyCacheEntry failed: %#x\n", v78);
        }
        goto LABEL_136;
      }
      if ( TicketGrantingTicket == -1073741730 )
      {
        if ( (_BYTE)a9 )
        {
          v34 = v112;
          if ( (v112 & 4) != 0 )
            KerbSetS4U2ProxyCache((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488), v38, v35);
          KerbSetS4U2ProxyCacheEntry((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488), a5, 0, v35);
          v40 = "No Win8 DC found to retry cross domain constraint delegation: %#x, retry flags %#x\n";
          v41 = 5731;
          goto LABEL_56;
        }
        v33 = a4;
        if ( (*((_DWORD *)a4 + 40) & 0x40000000) == 0 )
        {
          v39 = v83;
          KerbSetS4U2ProxyCache((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488), (unsigned int)a4, -1073741730);
          KerbSetS4U2ProxyCacheEntry((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v39 + 488), a5, 0, -1073741730);
          v40 = "No Win8 DC found to handle non-forwardable ticket: %#x, retry flags %#x\n";
          v41 = 5756;
LABEL_56:
          LODWORD(v80) = v34;
          TicketGrantingTicket = -2146893042;
          v42 = 21;
          goto LABEL_57;
        }
      }
      else
      {
        if ( (_BYTE)a9 )
        {
          if ( (v112 & 4) != 0 )
            KerbSetS4U2ProxyCache((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488), v38, v35);
          KerbSetS4U2ProxyCacheEntry((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488), a5, 0, v35);
          LODWORD(v80) = TicketGrantingTicket;
          LODWORD(v78) = v112;
          KerbTracerT::Log(
            21,
            "KerbGetServiceTicketByS4UProxy",
            5787,
            "Fallback on retry flags %#x due to Win8 DC returning %#x\n",
            v78,
            v80);
LABEL_146:
          TicketGrantingTicket = -2146893042;
          goto LABEL_136;
        }
        v33 = a4;
      }
      if ( ((unsigned __int8)a11 & 0x10) != 0 || (char)a11 < 0 )
      {
        v65 = (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488);
        if ( (*((_DWORD *)v33 + 40) & 0x40000000) == 0 )
        {
          KerbSetS4U2ProxyCacheEntry(v65, a5, 0x10000u, TicketGrantingTicket);
          LODWORD(v80) = (_DWORD)a11;
          LODWORD(v78) = TicketGrantingTicket;
          KerbTracerT::Log(
            1,
            "KerbGetServiceTicketByS4UProxy",
            5811,
            "S4U2Proxy failed with Win8 for non-forwardable ticket: %#x, Retry Flags %#x\n",
            v78,
            v80);
          goto LABEL_146;
        }
        KerbSetS4U2ProxyCacheEntry(v65, a5, 0, TicketGrantingTicket);
        v40 = "S4U2Proxy failed with Win8: %#x, Retry Flags %#x\n";
        LODWORD(v80) = (_DWORD)a11;
        v41 = 5823;
        v42 = 1;
LABEL_57:
        LODWORD(v78) = TicketGrantingTicket;
        KerbTracerT::Log(v42, "KerbGetServiceTicketByS4UProxy", v41, v40, v78, v80);
LABEL_136:
        v17 = 0;
        goto LABEL_137;
      }
      if ( ((unsigned __int8)a11 & 0xC) == 0 )
      {
        KerbSetS4U2ProxyCacheEntry((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488), a5, 0, TicketGrantingTicket);
        v40 = "Failed S4Uproxy request %x(%x) \n";
        LODWORD(v80) = (_DWORD)a11;
        v41 = 5851;
        v42 = 2;
        goto LABEL_57;
      }
      v36 = 1;
      v112 = (int)a11;
      LOBYTE(a9) = 1;
      v34 = (int)a11;
      v35 = TicketGrantingTicket;
      v93 = TicketGrantingTicket;
    }
    KerbFreeString(&v102);
    TicketGrantingTicket = KerbGetReferralNames(v84, a5, &v102);
    if ( TicketGrantingTicket < 0 )
      goto LABEL_136;
    if ( v102.Length )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
        WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids, a5);
      KerbTracerT::Log(21, "KerbGetServiceTicketByS4UProxy", 5924, "Got referral ticket in realm %wZ\n", &v88);
      TicketGrantingTicket = KerbCreateTicketCacheEntry(
                               v86,
                               v84,
                               *((struct KerbCredIsoApi **)TicketCacheEntryByRealm + 21),
                               0,
                               0,
                               v85,
                               0,
                               0,
                               0,
                               &v92,
                               0,
                               0,
                               &v82);
      if ( TicketGrantingTicket < 0 )
        goto LABEL_155;
      v46 = (int)a14;
      v47 = v103;
      v48 = v83;
      while ( 1 )
      {
        if ( !v88.Length )
        {
          ServiceTicket = KerbGetServiceTicketEx(
                            a2,
                            0,
                            0,
                            v97,
                            0,
                            a5,
                            String1,
                            v113,
                            0,
                            0,
                            a10,
                            (struct PKERB_AUTHORIZATION_DATA_s *)hMem,
                            a12,
                            &v99,
                            0,
                            0);
          v50 = ServiceTicket;
          if ( ServiceTicket < 0 )
          {
            KerbTracerT::Log(
              21,
              "KerbGetServiceTicketByS4UProxy",
              5985,
              "Failed to get service ticket in identity of middle tier: status 0x%08X\n",
              ServiceTicket);
            v67 = KerbSetS4U2ProxyCacheEntry((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v48 + 488), a5, 0x10000u, v50);
            TicketGrantingTicket = v67;
            if ( v67 >= 0 )
              TicketGrantingTicket = -2146893042;
            else
              KerbTracerT::Log(
                1,
                "KerbGetServiceTicketByS4UProxy",
                6000,
                "KerbSetS4U2ProxyCacheEntry failed: %#x\n",
                v67);
            goto LABEL_155;
          }
          KerbFreeString(&v88);
          TicketGrantingTicket = KerbDuplicateStringEx(&v88, (const struct _UNICODE_STRING *)v99 + 4, v51);
          if ( TicketGrantingTicket < 0 )
            goto LABEL_155;
          v47 = v103;
        }
        RtlEnterCriticalSection(v47);
        v89 = KerbLocateTicketCacheEntryByRealm((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v48 + 240), &v88, 0);
        v52 = v89;
        RtlLeaveCriticalSection(v47);
        if ( v52 )
          break;
        if ( v46 <= 0 )
        {
          TicketGrantingTicket = -2146893053;
          KerbTracerT::Log(
            1,
            "KerbGetServiceTicketByS4UProxy",
            6044,
            "KerbGetServiceTicketByS4UProxy: failed to get referral TGT to destination realm.\n");
LABEL_155:
          v17 = 0;
LABEL_156:
          TicketCacheEntry = v82;
LABEL_137:
          v18 = CriticalSection;
          v20 = 0;
          v44 = 0;
          goto LABEL_197;
        }
        KerbFreeString(&v88);
        LODWORD(a14) = --v46;
      }
      v17 = v82;
      TicketCacheEntry = 0;
      v54 = v113;
      v55 = v90;
      v82 = 0;
      while ( 1 )
      {
        if ( (unsigned int)KerbBuildFullServiceKdcNameWithSid(
                             (unsigned int)&v88,
                             (unsigned int)&KerbGlobalKdcServiceName,
                             v53,
                             2,
                             (__int64)v100) )
        {
          TicketGrantingTicket = -1073741670;
          goto LABEL_137;
        }
        if ( !RtlEqualUnicodeString(&v88, (PCUNICODE_STRING)v17 + 4, 1u) )
          break;
LABEL_115:
        KerbFreeData(74);
        KerbFreeData(76);
        v86 = 0;
        v84 = 0;
        KerbFreeString(&v92);
        LODWORD(a11) = 0;
        TgsTicket = KerbGetTgsTicketEx(
                      0,
                      0,
                      0,
                      v89,
                      a5,
                      v54 | 0x1000000,
                      0,
                      0,
                      (struct PKERB_AUTHORIZATION_DATA_s *)hMem,
                      0,
                      0,
                      0,
                      a12,
                      (struct _KERB_TICKET_CACHE_ENTRY *)((char *)v17 + 272),
                      (struct _KERB_TICKET_CACHE_ENTRY *)((char *)v17 + 168),
                      (union _LARGE_INTEGER *)&SystemTimeAsFileTime,
                      &v86,
                      &v84,
                      (unsigned int *)&a11,
                      &v92,
                      &v85,
                      0);
        if ( TgsTicket < 0 )
        {
          if ( ((unsigned __int8)a11 & 2) != 0 )
          {
            v63 = (int)a14;
            if ( (int)a14 > 0 )
            {
              if ( v17 )
                v64 = (const void *)WORD1(v17);
              else
                v64 = 0;
              KerbTracerT::Log(2, "KerbGetServiceTicketByS4UProxy", 6275, "Doing S4u TGT retry 3 - %p\n", v64);
              KerbRemoveTicketCacheEntry(v17);
              KerbDereferenceTicketCacheEntry(v17);
              KerbRemoveTicketCacheEntry(v89);
              KerbDereferenceTicketCacheEntry(v89);
              v89 = 0;
              LODWORD(a14) = v63 - 1;
LABEL_80:
              v30 = a2;
              v31 = v83;
              goto LABEL_35;
            }
          }
          KerbTracerT::Log(
            2,
            "KerbGetServiceTicketByS4UProxy",
            6292,
            "Failed to get TGS S4U ticket for service 0x%x",
            TgsTicket);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF__KERB_NAME_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids,
              a5);
          v68 = KerbSetS4U2ProxyCacheEntry(
                  (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488),
                  a5,
                  0x10000u,
                  TgsTicket);
          TicketGrantingTicket = v68;
          if ( v68 < 0 )
          {
            v69 = 6308;
LABEL_166:
            KerbTracerT::Log(1, "KerbGetServiceTicketByS4UProxy", v69, "KerbSetS4U2ProxyCacheEntry failed: %#x\n", v68);
            goto LABEL_137;
          }
LABEL_167:
          TicketGrantingTicket = -2146893042;
          goto LABEL_137;
        }
        KerbFreeString(&v88);
        TicketGrantingTicket = KerbGetReferralNames(v84, a5, &v88);
        if ( TicketGrantingTicket < 0 )
          goto LABEL_137;
        if ( !v88.Length )
        {
          v18 = CriticalSection;
          RtlEnterCriticalSection(CriticalSection);
          if ( (_BYTE)v95 )
            v70 = (struct _KERB_TICKET_CACHE *)&a1[7];
          else
            v70 = 0;
          TicketGrantingTicket = KerbCreateTicketCacheEntry(
                                   v86,
                                   v84,
                                   *((struct KerbCredIsoApi **)v17 + 21),
                                   a5,
                                   String1,
                                   v85,
                                   *((_DWORD *)v17 + 86),
                                   v70,
                                   0,
                                   &v92,
                                   0,
                                   0,
                                   &v82);
          RtlLeaveCriticalSection(CriticalSection);
          v20 = 0;
          if ( TicketGrantingTicket >= 0 )
          {
            v71 = v82;
            if ( v82 )
              v72 = (const void *)WORD1(v82);
            else
              v72 = 0;
            KerbTracerT::Log(21, "KerbGetServiceTicketByS4UProxy", 6430, "Got the S4U ticket (%p)\n", v72);
            v73 = a13;
            v44 = 0;
            *a13 = v71;
            TicketCacheEntry = 0;
            goto LABEL_198;
          }
LABEL_182:
          TicketCacheEntry = v82;
LABEL_172:
          v44 = 0;
LABEL_197:
          v73 = a13;
          goto LABEL_198;
        }
        v60 = v94;
        if ( v94 > KerbGlobalMaxReferralCount )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF__KERB_NAME_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids,
              a5);
          v18 = CriticalSection;
          TicketGrantingTicket = -1073741068;
          v20 = 0;
          goto LABEL_172;
        }
        TicketGrantingTicket = KerbCreateTicketCacheEntry(
                                 v86,
                                 v84,
                                 *((struct KerbCredIsoApi **)v89 + 21),
                                 0,
                                 0,
                                 v85,
                                 *((_DWORD *)v17 + 86),
                                 0,
                                 0,
                                 &v92,
                                 0,
                                 0,
                                 &v82);
        KerbFreeData(74);
        KerbFreeData(76);
        v86 = 0;
        v84 = 0;
        if ( TicketGrantingTicket < 0 )
          goto LABEL_156;
        v94 = v60 + 1;
        if ( v90 )
          KerbDereferenceTicketCacheEntry(v90);
        v90 = v17;
        v55 = v17;
        v17 = v82;
        v82 = 0;
        TicketCacheEntry = 0;
        KerbTracerT::Log(21, "KerbGetServiceTicketByS4UProxy", 6395, "Restart referral:%wZ", &v88);
      }
      v56 = v100[0];
      while ( 1 )
      {
        if ( v55 && RtlEqualUnicodeString((PCUNICODE_STRING)v55 + 4, (PCUNICODE_STRING)v17 + 4, 1u) )
        {
          KerbSetTicketCacheEntryTarget(&v88, v55);
          KerbTracerT::Log(
            1,
            "KerbGetServiceTicketByS4UProxy",
            6102,
            "Got two TGTs for same realm (%wZ), bailing out of referral loop\n",
            (char *)v55 + 64);
LABEL_114:
          v54 = v113;
          goto LABEL_115;
        }
        v57 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
          {
            WPP_SF__KERB_NAME_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids,
              v56);
            v57 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v57 != &WPP_GLOBAL_Control && (*((_DWORD *)v57 + 7) & 0x100000) != 0 )
            WPP_SF__KERB_NAME_(v57[2], 28, WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids, *((_QWORD *)v17 + 4));
        }
        KerbFreeData(74);
        KerbFreeData(76);
        v86 = 0;
        v84 = 0;
        KerbFreeString(&v92);
        v58 = KerbGetTgsTicketEx(
                0,
                0,
                0,
                v17,
                v56,
                v113,
                0,
                0,
                (struct PKERB_AUTHORIZATION_DATA_s *)hMem,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                &v86,
                &v84,
                (unsigned int *)&a11,
                &v92,
                &v85,
                0);
        if ( v58 < 0 )
          break;
        RtlEnterCriticalSection(CriticalSection);
        TicketGrantingTicket = KerbCreateTicketCacheEntry(
                                 v86,
                                 v84,
                                 *((struct KerbCredIsoApi **)v17 + 21),
                                 0,
                                 0,
                                 v85,
                                 *((_DWORD *)v17 + 86),
                                 0,
                                 0,
                                 &v92,
                                 0,
                                 0,
                                 &v82);
        RtlLeaveCriticalSection(CriticalSection);
        v20 = 0;
        if ( TicketGrantingTicket < 0 )
        {
          v18 = CriticalSection;
          goto LABEL_182;
        }
        if ( v90 )
          KerbDereferenceTicketCacheEntry(v90);
        v55 = v17;
        v90 = v17;
        v17 = v82;
        v82 = 0;
        TicketCacheEntry = 0;
        if ( RtlEqualUnicodeString(&v88, (PCUNICODE_STRING)v17 + 4, 1u) )
          goto LABEL_114;
      }
      if ( ((unsigned __int8)a11 & 2) != 0 )
      {
        v61 = (int)a14;
        if ( (int)a14 > 0 )
        {
          if ( v17 )
            v62 = (const void *)WORD1(v17);
          else
            v62 = 0;
          KerbTracerT::Log(2, "KerbGetServiceTicketByS4UProxy", 6153, "Doing S4u TGT retry 2 - %p\n", v62);
          KerbRemoveTicketCacheEntry(v17);
          KerbDereferenceTicketCacheEntry(v17);
          v31 = v83;
          LODWORD(a14) = v61 - 1;
          v30 = a2;
          continue;
        }
      }
      KerbTracerT::Log(2, "KerbGetServiceTicketByS4UProxy", 6165, "Failed to get TGS ticket for service 0x%x", v58);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF__KERB_NAME_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids,
          v56);
      v68 = KerbSetS4U2ProxyCacheEntry((struct _KERB_PRIMARY_CREDENTIAL *)((char *)v83 + 488), a5, 0x10000u, v58);
      TicketGrantingTicket = v68;
      if ( v68 < 0 )
      {
        v69 = 6181;
        goto LABEL_166;
      }
      goto LABEL_167;
    }
    break;
  }
  v18 = CriticalSection;
  RtlEnterCriticalSection(CriticalSection);
  if ( (_BYTE)v95 )
    v74 = (struct _KERB_TICKET_CACHE *)&a1[7];
  else
    v74 = 0;
  TicketGrantingTicket = KerbCreateTicketCacheEntry(
                           v86,
                           v84,
                           *((struct KerbCredIsoApi **)TicketCacheEntryByRealm + 21),
                           a5,
                           String1,
                           v85,
                           *((_DWORD *)TicketCacheEntryByRealm + 86),
                           v74,
                           0,
                           &v92,
                           (struct _UNICODE_STRING *)TicketCacheEntryByRealm + 8,
                           0,
                           &v82);
  RtlLeaveCriticalSection(CriticalSection);
  v73 = a13;
  v17 = 0;
  v20 = 0;
  v44 = 0;
  if ( TicketGrantingTicket < 0 )
  {
    TicketCacheEntry = v82;
  }
  else
  {
    TicketCacheEntry = 0;
    *a13 = v82;
  }
LABEL_198:
  if ( *(_WORD *)a5 == 2
    && ((int)(TicketGrantingTicket + 0x80000000) < 0 || TicketGrantingTicket == -1073741429)
    && !v44 )
  {
    v75 = 0;
    if ( TicketGrantingTicket >= 0 )
      v75 = (struct _UNICODE_STRING *)((char *)*v73 + 64);
    KerbUpdateSpnCacheEntry(a5, v83, (TicketGrantingTicket >> 31) + 2, v75);
  }
  if ( TicketCacheEntryByRealm )
    KerbDereferenceTicketCacheEntry(TicketCacheEntryByRealm);
  if ( v99 )
    KerbDereferenceTicketCacheEntry(v99);
  if ( v89 )
    KerbDereferenceTicketCacheEntry(v89);
  KerbFreeData(74);
  KerbFreeData(76);
  KerbFreeKdcName(v100);
  KerbFreeString(&v88);
  KerbFreeString(&v101);
  KerbFreeString(&v102);
  KerbFreeDuplicatedTicket(v106);
  if ( v97 )
    KerbDereferenceExtraCred(v97);
  if ( v20 )
    RtlLeaveCriticalSection(v18);
  if ( v17 )
  {
    if ( TicketGrantingTicket == -1073741718 )
      KerbRemoveTicketCacheEntry(v17);
    KerbDereferenceTicketCacheEntry(v17);
  }
  if ( v90 )
    KerbDereferenceTicketCacheEntry(v90);
  KerbFreeString(&String2);
  if ( TicketCacheEntry )
  {
    KerbRemoveTicketCacheEntry(TicketCacheEntry);
    KerbDereferenceTicketCacheEntry(TicketCacheEntry);
  }
  KerbFreeString(&v92);
  if ( hMem )
    KerbFreeAuthData(hMem);
  return (unsigned int)TicketGrantingTicket;
}

```

## disassembly

```asm
0x1800566a8  mov     rax, rsp
0x1800566ab  mov     [rax+20h], r9
0x1800566af  mov     [rax+18h], r8
0x1800566b3  mov     [rax+10h], rdx
0x1800566b7  mov     [rax+8], rcx
0x1800566bb  push    rbp
0x1800566bc  push    rbx
0x1800566bd  push    rsi
0x1800566be  push    rdi
0x1800566bf  push    r12
0x1800566c1  push    r13
0x1800566c3  push    r14
0x1800566c5  push    r15
0x1800566c7  lea     rbp, [rax-118h]
0x1800566ce  sub     rsp, 208h
0x1800566d5  xor     edi, edi
0x1800566d7  mov     r15, rdx
0x1800566da  mov     rbx, rcx
0x1800566dd  mov     [rbp+110h+hMem], rdi
0x1800566e1  xorps   xmm0, xmm0
0x1800566e4  mov     [rbp+110h+var_188], rdi
0x1800566e8  xor     eax, eax
0x1800566ea  mov     [rbp+110h+var_160], rdi
0x1800566ee  lea     r8d, [rdi+48h]; Size
0x1800566f2  mov     [rbp+110h+var_98], rax
0x1800566f6  xor     edx, edx; Val
0x1800566f8  mov     [rbp+110h+var_138], rdi
0x1800566fc  lea     rcx, [rbp+110h+var_90]; void *
0x180056703  mov     [rbp+110h+var_E8], rdi
0x180056707  movups  [rbp+110h+var_A8], xmm0
0x18005670b  mov     r14d, edi
0x18005670e  mov     [rbp+110h+var_140], rdi
0x180056712  mov     esi, edi
0x180056714  mov     [rbp+110h+var_168], rdi
0x180056718  mov     [rbp+110h+var_178], rdi
0x18005671c  call    memset_0
0x180056721  mov     eax, cs:?KerbGlobalMaxReferralCount@@3KA; ulong KerbGlobalMaxReferralCount
0x180056727  lea     rcx, [rbp+110h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005672b  xorps   xmm0, xmm0
0x18005672e  mov     qword ptr [rbp+110h+var_150.Length], rdi
0x180056732  movups  xmmword ptr [rbp+110h+var_128.Length], xmm0
0x180056736  mov     [rbp+110h+var_150.Buffer], rdi
0x18005673a  mov     qword ptr [rbp+110h+var_C0.Length], rdi
0x18005673e  mov     [rbp+110h+var_C0.Buffer], rdi
0x180056742  mov     qword ptr [rbp+110h+var_D0.Length], rdi
0x180056746  mov     [rbp+110h+var_D0.Buffer], rdi
0x18005674a  mov     [rbp+110h+var_E0], rdi
0x18005674e  mov     [rbp+110h+var_180], rdi
0x180056752  mov     [rbp+110h+var_100], rdi
0x180056756  mov     qword ptr [rbp+110h+String2.Length], rdi
0x18005675a  mov     [rbp+110h+String2.Buffer], rdi
0x18005675e  mov     dword ptr [rbp+110h+arg_50], edi
0x180056764  mov     [rbp+110h+arg_38], dil
0x18005676b  mov     qword ptr [rbp+110h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18005676f  mov     dword ptr [rbp+110h+arg_68], eax
0x180056775  mov     [rbp+110h+var_170], edi
0x180056778  mov     [rbp+110h+arg_40], edi
0x18005677e  call    cs:__imp_GetSystemTimeAsFileTime
0x180056784  mov     rax, cs:?KerbGlobalS4UTicketLifetime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalS4UTicketLifetime
0x18005678b  lea     r13, [rbx+50h]
0x18005678f  add     qword ptr [rbp+110h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180056793  mov     rcx, r13; CriticalSection
0x180056796  mov     [rbp+110h+CriticalSection], r13
0x18005679a  call    cs:__imp_RtlEnterCriticalSection
0x1800567a0  mov     r12, [rbp+110h+arg_20]
0x1800567a7  xor     eax, eax
0x1800567a9  mov     dil, 1
0x1800567ac  cmp     [r12+2], ax
0x1800567b2  jz      loc_180057DC4
0x1800567b8  cmp     [r12+8], ax
0x1800567be  jz      loc_180057DC4
0x1800567c4  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800567cb  lea     rcx, [rbp+110h+var_A8]
0x1800567cf  lea     r13, [rbx+78h]
0x1800567d3  mov     rax, [rax+0C0h]
0x1800567da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800567df  lea     rax, [r13+10h]
0x1800567e3  mov     r8d, 149Eh
0x1800567e9  mov     [rsp+240h+var_1F0], rax
0x1800567ee  lea     r9, aAttemptingS4u2_0; "Attempting S4U2Proxy: caller logon sess"...
0x1800567f5  mov     eax, [rbx+40h]
0x1800567f8  lea     ecx, [rsi+15h]
0x1800567fb  mov     [rsp+240h+var_1F8], r13
0x180056800  mov     dword ptr [rsp+240h+var_200], eax
0x180056804  mov     eax, [rbx+44h]
0x180056807  mov     dword ptr [rsp+240h+var_208], eax
0x18005680b  mov     eax, dword ptr [rbp+110h+var_A8]
0x18005680e  mov     dword ptr [rsp+240h+var_210], eax
0x180056812  mov     eax, [r15+40h]
0x180056816  mov     dword ptr [rsp+240h+var_218], eax
0x18005681a  mov     eax, [r15+44h]
0x18005681e  lea     r15, aKerbgetservice_12; "KerbGetServiceTicketByS4UProxy"
0x180056825  mov     rdx, r15
0x180056828  mov     dword ptr [rsp+240h+var_220], eax
0x18005682c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180056831  mov     rcx, cs:WPP_GLOBAL_Control
0x180056838  lea     rax, WPP_GLOBAL_Control
0x18005683f  cmp     rcx, rax
0x180056842  jz      short loc_180056863
0x180056844  test    dword ptr [rcx+1Ch], 100000h
0x18005684b  jz      short loc_180056863
0x18005684d  mov     rcx, [rcx+10h]
0x180056851  lea     edx, [rsi+16h]
0x180056854  mov     r9, r12
0x180056857  lea     r8, WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids
0x18005685e  call    WPP_SF__KERB_NAME_
0x180056863  test    dword ptr [rbx+388h], 100h
0x18005686d  jnz     short loc_1800568B2
0x18005686f  mov     r13, [rbp+110h+arg_0]
0x180056876  lea     r9, aLogonSessionXX; "logon session %#x:%x is not OK for dele"...
0x18005687d  mov     ebx, 8009030Eh
0x180056882  mov     r8d, 14A5h
0x180056888  mov     dword ptr [rsp+240h+var_210], ebx
0x18005688c  mov     rdx, r15
0x18005688f  mov     ecx, 15h
0x180056894  mov     eax, [r13+40h]
0x180056898  mov     dword ptr [rsp+240h+var_218], eax
0x18005689c  mov     eax, [r13+44h]
0x1800568a0  mov     dword ptr [rsp+240h+var_220], eax
0x1800568a4  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800568a9  mov     r13, [rbp+110h+CriticalSection]
0x1800568ad  jmp     loc_180057DE7
0x1800568b2  mov     rdx, qword ptr [rbp+110h+arg_18]
0x1800568b9  lea     r9, [rbp+110h+var_100]; struct _KERB_EXTRA_CRED **
0x1800568bd  mov     rcx, [rbp+110h+arg_8]; struct _KERB_LOGON_SESSION *
0x1800568c4  lea     r8, [rbp+110h+var_180]; struct _KERB_PRIMARY_CREDENTIAL **
0x1800568c8  mov     rdx, [rdx+20h]; struct _KERB_INTERNAL_NAME *
0x1800568cc  call    ?KerbGetS4UProxyCred@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_INTERNAL_NAME@@PEAPEAU_KERB_PRIMARY_CREDENTIAL@@PEAPEAU_KERB_EXTRA_CRED@@@Z; KerbGetS4UProxyCred(_KERB_LOGON_SESSION *,_KERB_INTERNAL_NAME *,_KERB_PRIMARY_CREDENTIAL * *,_KERB_EXTRA_CRED * *)
0x1800568d1  mov     ebx, eax
0x1800568d3  test    eax, eax
0x1800568d5  jns     short loc_1800568F7
0x1800568d7  lea     r9, aKerbgets4uprox; "KerbGetS4UProxyCred failed %#x\n"
0x1800568de  mov     dword ptr [rsp+240h+var_220], eax
0x1800568e2  mov     r8d, 14B2h
0x1800568e8  mov     rdx, r15
0x1800568eb  mov     ecx, 1
0x1800568f0  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800568f5  jmp     short loc_1800568A9
0x1800568f7  mov     rcx, [rbp+110h+var_180]
0x1800568fb  mov     r8b, dil; unsigned __int8
0x1800568fe  add     rcx, 1E8h; struct _KERB_S4U2PROXY_CACHE *
0x180056905  xor     edx, edx; unsigned __int8
0x180056907  call    ?KerbAgeS4U2ProxyCache@@YAXPEAU_KERB_S4U2PROXY_CACHE@@EE@Z; KerbAgeS4U2ProxyCache(_KERB_S4U2PROXY_CACHE *,uchar,uchar)
0x18005690c  mov     rcx, [rbp+110h+var_180]
0x180056910  lea     rdx, [rbp+110h+arg_40]; unsigned int *
0x180056917  add     rcx, 1E8h; struct _KERB_S4U2PROXY_CACHE *
0x18005691e  call    ?KerbGetS4U2ProxyCacheFlags@@YAXPEAU_KERB_S4U2PROXY_CACHE@@PEAK@Z; KerbGetS4U2ProxyCacheFlags(_KERB_S4U2PROXY_CACHE *,ulong *)
0x180056923  mov     eax, [rbp+110h+arg_40]
0x180056929  test    dil, al
0x18005692c  jz      short loc_18005695A
0x18005692e  lea     r9, aCallerDoesNotS; "caller does not support S4U2Proxy: %#x,"...
0x180056935  mov     r8d, 14C5h
0x18005693b  mov     dword ptr [rsp+240h+var_218], eax
0x18005693f  mov     ebx, 8009030Eh
0x180056944  mov     rdx, r15
0x180056947  mov     dword ptr [rsp+240h+var_220], ebx
0x18005694b  mov     ecx, 15h
0x180056950  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180056955  jmp     loc_1800568A9
0x18005695a  mov     rcx, [rbp+110h+var_180]
0x18005695e  lea     r8, [rbp+110h+arg_40]; unsigned int *
0x180056965  add     rcx, 1E8h; struct _KERB_S4U2PROXY_CACHE *
0x18005696c  mov     rdx, r12; struct _KERB_INTERNAL_NAME *
0x18005696f  call    ?KerbGetS4U2ProxyCacheEntryFlags@@YAXPEAU_KERB_S4U2PROXY_CACHE@@PEAU_KERB_INTERNAL_NAME@@PEAK@Z; KerbGetS4U2ProxyCacheEntryFlags(_KERB_S4U2PROXY_CACHE *,_KERB_INTERNAL_NAME *,ulong *)
0x180056974  mov     eax, [rbp+110h+arg_40]
0x18005697a  bt      eax, 10h
0x18005697e  jnb     short loc_18005698F
0x180056980  lea     r9, aCallerDoesNotS_0; "caller does not support S4U2Proxy for t"...
0x180056987  mov     r8d, 14D2h
0x18005698d  jmp     short loc_18005693B
0x18005698f  xor     ecx, ecx
0x180056991  cmp     [rbp+110h+arg_58], rcx
0x180056998  jnz     short loc_1800569CA
0x18005699a  test    byte ptr [rbp+110h+arg_30], dil
0x1800569a1  jnz     short loc_1800569CA
0x1800569a3  mov     r8, [rbp+110h+String1]; struct _UNICODE_STRING *
0x1800569aa  lea     rcx, [r13+0A0h]; struct _KERB_TICKET_CACHE *
0x1800569b1  xor     r9d, r9d; unsigned int
0x1800569b4  mov     rdx, r12; struct _KERB_INTERNAL_NAME *
0x1800569b7  call    ?KerbLocateTicketCacheEntryEx@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryEx(_KERB_TICKET_CACHE *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,ulong)
0x1800569bc  mov     r14, rax
0x1800569bf  mov     [rbp+110h+var_188], rax
0x1800569c3  xor     ecx, ecx
0x1800569c5  mov     r13b, dil
0x1800569c8  jmp     short loc_1800569CD
0x1800569ca  mov     r13b, cl
0x1800569cd  test    r14, r14
0x1800569d0  jz      short loc_180056A05
0x1800569d2  mov     rax, [rbp+110h+arg_48]
0x1800569d9  test    rax, rax
0x1800569dc  jz      loc_180056DFF
0x1800569e2  cmp     dword ptr [rax+34h], 29h ; ')'
0x1800569e6  jnz     loc_180056DFF
0x1800569ec  mov     rcx, r14; struct _KERB_TICKET_CACHE_ENTRY *
0x1800569ef  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800569f4  mov     rcx, r14; struct _KERB_TICKET_CACHE_ENTRY *
0x1800569f7  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800569fc  xor     ecx, ecx
0x1800569fe  mov     r14d, ecx
0x180056a01  mov     [rbp+110h+var_188], rcx
0x180056a05  test    [rbp+110h+arg_30], 2000000h
0x180056a0f  jz      loc_180056AB0
0x180056a15  mov     rax, [rbp+110h+String1]
0x180056a1c  cmp     [rax+8], rcx
0x180056a20  jnz     loc_180056AB0
0x180056a26  mov     rdx, [rbp+110h+var_180]; struct _KERB_PRIMARY_CREDENTIAL *
0x180056a2a  lea     r8, [rbp+110h+var_D0]; struct _UNICODE_STRING *
0x180056a2e  mov     rcx, r12; struct _KERB_INTERNAL_NAME *
0x180056a31  call    ?KerbGetSpnCacheStatus@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_KERB_PRIMARY_CREDENTIAL@@PEAU_UNICODE_STRING@@@Z; KerbGetSpnCacheStatus(_KERB_INTERNAL_NAME *,_KERB_PRIMARY_CREDENTIAL *,_UNICODE_STRING *)
0x180056a36  mov     ebx, eax
0x180056a38  test    eax, eax
0x180056a3a  js      loc_180056EC9
0x180056a40  lea     rcx, [rbp+110h+var_150]
0x180056a44  call    KerbFreeString
0x180056a49  movaps  xmm0, xmmword ptr [rbp+110h+var_D0.Length]
0x180056a4d  lea     rax, [rbp+110h+var_150]
0x180056a51  xorps   xmm1, xmm1
0x180056a54  movdqa  xmmword ptr [rbp+110h+var_150.Length], xmm0
0x180056a59  lea     r9, aFoundSpnCacheE; "Found SPN cache entry - %wZ\n"
0x180056a60  mov     [rsp+240h+var_220], rax
0x180056a65  mov     r8d, 153Ch
0x180056a6b  mov     rdx, r15
0x180056a6e  mov     ecx, 13h
0x180056a73  movups  xmmword ptr [rbp+110h+var_D0.Length], xmm1
0x180056a77  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180056a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180056a83  lea     rax, WPP_GLOBAL_Control
0x180056a8a  cmp     rcx, rax
0x180056a8d  jz      short loc_180056AB0
0x180056a8f  test    dword ptr [rcx+1Ch], 40000h
0x180056a96  jz      short loc_180056AB0
0x180056a98  mov     rcx, [rcx+10h]
0x180056a9c  lea     r8, WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids
0x180056aa3  mov     edx, 18h
0x180056aa8  mov     r9, r12
0x180056aab  call    WPP_SF__KERB_NAME_
0x180056ab0  mov     rcx, [rbp+110h+arg_10]; struct _KERB_CREDENTIAL *
0x180056ab7  lea     r8, [rbp+110h+hMem]; struct PKERB_AUTHORIZATION_DATA_s **
0x180056abb  xor     edx, edx; struct _KERB_CREDMAN_CRED *
0x180056abd  call    ?KerbAddAuthzDataForTGS@@YAJPEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAPEAUPKERB_AUTHORIZATION_DATA_s@@@Z; KerbAddAuthzDataForTGS(_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,PKERB_AUTHORIZATION_DATA_s * *)
0x180056ac2  xor     r10d, r10d
0x180056ac5  mov     ebx, eax
0x180056ac7  test    eax, eax
0x180056ac9  js      loc_180056EC0
0x180056acf  mov     edx, [rbp+110h+arg_30]
0x180056ad5  test    dil, dl
0x180056ad8  movzx   ecx, r13b
0x180056adc  cmovnz  ecx, r10d
0x180056ae0  mov     [rbp+110h+var_114], r10d
0x180056ae4  mov     [rbp+110h+var_110], ecx
0x180056ae7  or      edx, 0C00000h
0x180056aed  mov     rcx, [rbp+110h+CriticalSection]; CriticalSection
0x180056af1  mov     byte ptr [rbp+110h+arg_40], r10b
0x180056af8  mov     dword ptr [rbp+110h+arg_20], r10d
0x180056aff  mov     [rbp+110h+var_118], r10d
0x180056b03  mov     [rbp+110h+arg_30], edx
0x180056b09  call    cs:__imp_RtlLeaveCriticalSection
0x180056b0f  mov     rdi, [rbp+110h+arg_8]
0x180056b16  lea     rbx, [rdi+50h]
0x180056b1a  mov     rcx, rbx; CriticalSection
0x180056b1d  mov     [rbp+110h+var_B0], rbx
0x180056b21  call    cs:__imp_RtlEnterCriticalSection
0x180056b27  mov     rsi, [rbp+110h+var_180]
0x180056b2b  xor     edx, edx; struct _UNICODE_STRING *
0x180056b2d  lea     r8d, [rdx+1]; unsigned int
0x180056b31  lea     rcx, [rsi+0F0h]; struct _KERB_TICKET_CACHE *
0x180056b38  call    ?KerbLocateTicketCacheEntryByRealm@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryByRealm(_KERB_TICKET_CACHE *,_UNICODE_STRING *,ulong)
0x180056b3d  mov     rcx, rbx; CriticalSection
0x180056b40  mov     [rbp+110h+var_160], rax
0x180056b44  call    cs:__imp_RtlLeaveCriticalSection
0x180056b4a  xor     r10d, r10d
0x180056b4d  cmp     [rbp+110h+var_160], r10
0x180056b51  jnz     short loc_180056B93
0x180056b53  mov     r9, [rbp+110h+var_100]; struct _KERB_EXTRA_CRED *
0x180056b57  lea     rax, [rbp+110h+var_160]
0x180056b5b  mov     byte ptr [rsp+240h+var_1F8], r10b; unsigned __int8
0x180056b60  xor     r8d, r8d; struct _KERB_CREDMAN_CRED *
0x180056b63  mov     [rsp+240h+var_200], r10; struct _KERB_ENCRYPTION_KEY *
0x180056b68  xor     edx, edx; struct _KERB_CREDENTIAL *
0x180056b6a  mov     [rsp+240h+var_208], rax; struct _KERB_TICKET_CACHE_ENTRY **
0x180056b6f  mov     rcx, rdi; struct _KERB_LOGON_SESSION *
0x180056b72  mov     dword ptr [rsp+240h+var_210], r10d; unsigned int
0x180056b77  mov     [rsp+240h+var_218], r10; struct _UNICODE_STRING *
0x180056b7c  mov     [rsp+240h+var_220], r10; struct _KERB_PROXY_LOGON_CRED *
0x180056b81  call    ?KerbGetTicketGrantingTicket@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_EXTRA_CRED@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_UNICODE_STRING@@KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_ENCRYPTION_KEY@@E@Z; KerbGetTicketGrantingTicket(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_EXTRA_CRED *,_KERB_PROXY_LOGON_CRED *,_UNICODE_STRING *,ulong,_KERB_TICKET_CACHE_ENTRY * *,_KERB_ENCRYPTION_KEY *,uchar)
0x180056b86  xor     r10d, r10d
0x180056b89  mov     ebx, eax
0x180056b8b  test    eax, eax
0x180056b8d  js      loc_180057790
0x180056b93  cmp     [rbp+110h+String2.Buffer], r10
0x180056b97  jnz     short loc_180056BB3
0x180056b99  lea     rdx, [rsi+10h]; struct _UNICODE_STRING *
0x180056b9d  lea     rcx, [rbp+110h+String2]; struct _UNICODE_STRING *
0x180056ba1  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180056ba6  xor     r10d, r10d
0x180056ba9  mov     ebx, eax
0x180056bab  test    eax, eax
0x180056bad  js      loc_1800577AD
0x180056bb3  mov     rdi, qword ptr [rbp+110h+arg_18]
0x180056bba  cmp     [rbp+110h+var_78], r10
  ... truncated ...
```
