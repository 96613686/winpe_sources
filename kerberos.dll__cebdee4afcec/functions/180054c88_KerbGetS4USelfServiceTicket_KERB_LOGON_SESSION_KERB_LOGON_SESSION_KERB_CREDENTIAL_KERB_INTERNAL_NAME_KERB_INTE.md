# KerbGetS4USelfServiceTicket(_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_INTERNAL_NAME * *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_KERB_TICKET_CACHE_ENTRY * *,ulong,ulong,ulong,ulong,uchar *)

- ea: `0x180054c88`
- end: `0x1800564d0`
- name: `?KerbGetS4USelfServiceTicket@@YAJPEAU_KERB_LOGON_SESSION@@0PEAU_KERB_CREDENTIAL@@PEAPEAU_KERB_INTERNAL_NAME@@PEAU3@PEAU_UNICODE_STRING@@PEAPEAU_KERB_TICKET_CACHE_ENTRY@@KKKKPEAE@Z`
- size: `6216`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, struct _KERB_INTERNAL_NAME **, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, struct _KERB_TICKET_CACHE_ENTRY **, unsigned int, char, unsigned __int8, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1800548b4`
- `0x18009eb08`

## callees

- `0x180005c90`
- `0x180006350`
- `0x1800063e8`
- `0x1800068d0`
- `0x180006920`
- `0x1800069a0`
- `0x1800069e0`
- `0x1800093f0`
- `0x18000b300`
- `0x180010e90`
- `0x1800113f0`
- `0x180014dc0`
- `0x180016550`
- `0x1800190c0`
- `0x18001e570`
- `0x180020690`
- `0x1800290c0`
- `0x180029ec8`
- `0x18002a150`
- `0x18002a2bc`
- `0x18003e9d8`
- `0x180040fb8`
- `0x180041178`
- `0x18004ed20`
- `0x180054c88`
- `0x1800564d8`
- `0x180057f58`
- `0x180058380`
- `0x18006557c`
- `0x18007108c`
- `0x180088040`
- `0x18008a304`
- `0x18008b70c`
- `0x180091118`
- `0x18009d63c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180054dcb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180054dcb`
- `ntdll!RtlEqualUnicodeString` at `0x18005517f`
- `ntdll!RtlEqualUnicodeString` at `0x180055786`
- `ntdll!RtlEqualUnicodeString` at `0x180055803`
- `ntdll!RtlEqualUnicodeString` at `0x18005599b`
- `ntdll!RtlEqualUnicodeString` at `0x18005517f`
- `ntdll!RtlEqualUnicodeString` at `0x180055786`
- `ntdll!RtlEqualUnicodeString` at `0x180055803`
- `ntdll!RtlEqualUnicodeString` at `0x18005599b`
- `ntdll!RtlEnterCriticalSection` at `0x180054e60`
- `ntdll!RtlEnterCriticalSection` at `0x18005512d`
- `ntdll!RtlEnterCriticalSection` at `0x1800551a5`
- `ntdll!RtlEnterCriticalSection` at `0x1800553bd`
- `ntdll!RtlEnterCriticalSection` at `0x180055bcf`
- `ntdll!RtlEnterCriticalSection` at `0x180056152`
- `ntdll!RtlEnterCriticalSection` at `0x18005621b`
- `ntdll!RtlEnterCriticalSection` at `0x180054e60`
- `ntdll!RtlEnterCriticalSection` at `0x18005512d`
- `ntdll!RtlEnterCriticalSection` at `0x1800551a5`
- `ntdll!RtlEnterCriticalSection` at `0x1800553bd`
- `ntdll!RtlEnterCriticalSection` at `0x180055bcf`
- `ntdll!RtlEnterCriticalSection` at `0x180056152`
- `ntdll!RtlEnterCriticalSection` at `0x18005621b`
- `ntdll!RtlLeaveCriticalSection` at `0x180054f5b`
- `ntdll!RtlLeaveCriticalSection` at `0x180055158`
- `ntdll!RtlLeaveCriticalSection` at `0x1800551fc`
- `ntdll!RtlLeaveCriticalSection` at `0x180055413`
- `ntdll!RtlLeaveCriticalSection` at `0x180055c26`
- `ntdll!RtlLeaveCriticalSection` at `0x1800562ac`
- `ntdll!RtlLeaveCriticalSection` at `0x18005644e`
- `ntdll!RtlLeaveCriticalSection` at `0x180054f5b`
- `ntdll!RtlLeaveCriticalSection` at `0x180055158`
- `ntdll!RtlLeaveCriticalSection` at `0x1800551fc`
- `ntdll!RtlLeaveCriticalSection` at `0x180055413`
- `ntdll!RtlLeaveCriticalSection` at `0x180055c26`
- `ntdll!RtlLeaveCriticalSection` at `0x1800562ac`
- `ntdll!RtlLeaveCriticalSection` at `0x18005644e`

## string_xrefs

- `0x180056391`: `KerbGetS4UServiceTicket need client realm\n`
- `0x18005503e`: `KerbGetS4USelfServiceTicket`
- `0x180055080`: `KerbGetS4USelfServiceTicket`
- `0x1800552d3`: `KerbGetS4USelfServiceTicket`
- `0x1800554a1`: `KerbGetS4USelfServiceTicket`
- `0x180055577`: `KerbGetS4USelfServiceTicket`
- `0x18005568e`: `KerbGetS4USelfServiceTicket`
- `0x1800557b4`: `KerbGetS4USelfServiceTicket`
- `0x1800557db`: `KerbGetS4USelfServiceTicket`
- `0x180055a59`: `KerbGetS4USelfServiceTicket`
- `0x180055b45`: `KerbGetS4USelfServiceTicket`
- `0x180055ba7`: `KerbGetS4USelfServiceTicket`
- `0x180055cbd`: `KerbGetS4USelfServiceTicket`
- `0x180055ee2`: `KerbGetS4USelfServiceTicket`
- `0x180055f0e`: `KerbGetS4USelfServiceTicket`
- `0x180055fb5`: `KerbGetS4USelfServiceTicket`
- `0x180055fdd`: `KerbGetS4USelfServiceTicket`
- `0x180055fff`: `KerbGetS4USelfServiceTicket`
- `0x180056046`: `KerbGetS4USelfServiceTicket`
- `0x180056087`: `KerbGetS4USelfServiceTicket`
- `0x1800560dd`: `KerbGetS4USelfServiceTicket`
- `0x1800561dd`: `KerbGetS4USelfServiceTicket`
- `0x1800562dc`: `KerbGetS4USelfServiceTicket`
- `0x180056303`: `KerbGetS4USelfServiceTicket`
- `0x180056371`: `KerbGetS4USelfServiceTicket`
- `0x18005639e`: `KerbGetS4USelfServiceTicket`
- `0x180055032`: `KerbGetS4UServiceTicket receives s4u options (network order): %#x\n`
- `0x180055063`: `KerbGetS4UServiceTicket calling KerbGetTgtToS4URealm ClientRealm %wZ\n`
- `0x180056364`: `KerbGetS4UServiceTicket cannot get S4U Tgt - %x\n`
- `0x180056355`: `KerbGetS4UServiceTicket KerbBuildS4UPreauth failed - %x\n`
- `0x180055fa8`: `KerbGetS4UServiceTicket got unexpected cross realm TGT`
- `0x180055ff2`: `KerbGetS4UServiceTicket got unexpected cross realm TGT`
- `0x180055fd1`: `KerbGetS4UServiceTicket failed to get tgt`
- `0x1800552c6`: `KerbGetS4UServiceTicket calling KerbGetTgsTicket (ReferralRestart)`
- `0x180055494`: `KerbGetS4UServiceTicket calling KerbGetTgsTicket`
- `0x18005556c`: `KerbGetS4UServiceTicket failed to get TGS ticket for service vis u2u 0x%x\n`
- `0x180056022`: `KerbGetS4UServiceTicket failed to duplicate u2u key\n`
- `0x180056064`: `KerbGetS4UServiceTicket failed to duplicate reply key\n`
- `0x180056101`: `KerbGetS4UServiceTicket failed to duplicate reply key\n`
- `0x180056034`: `KerbGetS4UServiceTicket failed to convert name: %#x\n`
- `0x1800561cc`: `KerbGetS4UServiceTicket failed to convert name: %#x\n`
- `0x180055f03`: `KerbGetS4UServiceTicket doing TGT retry - %p\n`
- `0x1800562cf`: `KerbGetS4UServiceTicket failed Query policy information`
- `0x180055b34`: `KerbGetS4UServiceTicket failed to get TGS ticket for service 0x%x`
- `0x1800562f2`: `KerbGetS4UServiceTicket failed to get TGS ticket for service 0x%x`
- `0x180055682`: `KerbGetS4UServiceTicket got referral ticket for service in realm %wZ\n`
- `0x1800557a8`: `KerbGetS4UServiceTicket realTargetRealm %wZ\n`
- `0x1800557cf`: `KerbGetS4UServiceTicket TGT %wZ\n`
- `0x180055b95`: `KerbGetS4UServiceTicket got two TGTs for same realm (%wZ), S4U\n`
- `0x180056076`: `KerbGetTgsTicket failed to get TGS ticket for service 0x%x`
- `0x180055a4c`: `KerbGetS4UServiceTicket xForest final calling KerbGetTgsTicket\n`
- `0x1800560d0`: `KerbGetS4UServiceTicket got unexpected cross realm TGT\n`
- `0x180055cb0`: `KerbGetS4UServiceTicket xForest final u2u calling KerbGetTgsTicket\n`
- `0x180055ed1`: `KerbGetS4UServiceTicket restart referral: %wZ`

## pseudocode

```c
__int64 __fastcall KerbGetS4USelfServiceTicket(
        struct _KERB_LOGON_SESSION *a1,
        struct _KERB_LOGON_SESSION *a2,
        struct _KERB_CREDENTIAL *a3,
        struct _KERB_INTERNAL_NAME **a4,
        struct _KERB_INTERNAL_NAME *a5,
        struct _UNICODE_STRING *a6,
        struct _KERB_TICKET_CACHE_ENTRY **a7,
        unsigned int a8,
        char a9,
        unsigned __int8 a10,
        unsigned int a11,
        unsigned __int8 *a12)
{
  struct _KERB_TICKET_CACHE_ENTRY *S4UTicketCacheEntry; // rsi
  struct _KERB_TICKET_CACHE_ENTRY *v14; // rdi
  struct _KERB_TICKET_CACHE_ENTRY *v15; // r13
  HLOCAL v16; // r15
  struct _KERB_TICKET_CACHE_ENTRY *v17; // r14
  struct _RTL_CRITICAL_SECTION *v18; // r12
  struct _KERB_PRIMARY_CREDENTIAL *v19; // rax
  struct _LUID *v20; // rbx
  int S4UTargetName; // ebx
  unsigned int v22; // ecx
  unsigned int v23; // eax
  struct _KERB_TICKET_CACHE_ENTRY *v24; // rcx
  int v25; // eax
  __int16 v26; // cx
  int v27; // ecx
  int v28; // eax
  struct _KERB_CREDENTIAL *v29; // rdx
  int TgtToS4URealm; // eax
  int v31; // eax
  _QWORD *v32; // rax
  struct _KERB_PRIMARY_CREDENTIAL *v33; // rdi
  unsigned __int8 v34; // r8
  _QWORD *v35; // rbx
  struct _KERB_INTERNAL_NAME *v36; // rcx
  __int64 v37; // r8
  int v38; // r15d
  struct _KERB_INTERNAL_NAME *v39; // r15
  int v40; // r8d
  struct _KERB_INTERNAL_NAME *v41; // r12
  struct _KERB_TICKET_CACHE_ENTRY *v42; // r15
  struct _KERB_TICKET_CACHE_ENTRY *v43; // r13
  struct _KERB_TICKET_CACHE_ENTRY *v44; // r15
  char *v45; // r15
  int TgsTicket; // eax
  _QWORD *v47; // rax
  _QWORD *v48; // rcx
  struct _KERB_INTERNAL_NAME *v49; // r9
  __int64 v50; // rdx
  int v51; // eax
  int v52; // ebx
  int v53; // ecx
  __int64 v54; // r8
  int v55; // eax
  const char *v56; // r9
  __int64 v57; // r8
  struct _UNICODE_STRING *v59; // [rsp+28h] [rbp-110h]
  unsigned int v60; // [rsp+30h] [rbp-108h]
  unsigned int v61; // [rsp+38h] [rbp-100h]
  struct KERB_ENCRYPTED_KDC_REPLY *v62; // [rsp+B8h] [rbp-80h] BYREF
  unsigned int v63; // [rsp+C0h] [rbp-78h] BYREF
  struct KERB_KDC_REPLY *v64; // [rsp+C8h] [rbp-70h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v65; // [rsp+D0h] [rbp-68h] BYREF
  unsigned __int8 v66[4]; // [rsp+D8h] [rbp-60h] BYREF
  unsigned int v67; // [rsp+DCh] [rbp-5Ch] BYREF
  int v68; // [rsp+E0h] [rbp-58h]
  struct _KERB_TICKET_CACHE_ENTRY *v69; // [rsp+E8h] [rbp-50h] BYREF
  struct _KERB_INTERNAL_NAME *v70; // [rsp+F0h] [rbp-48h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v71; // [rsp+F8h] [rbp-40h] BYREF
  int v72; // [rsp+100h] [rbp-38h]
  int v73; // [rsp+104h] [rbp-34h]
  int v74; // [rsp+108h] [rbp-30h]
  int v75; // [rsp+10Ch] [rbp-2Ch] BYREF
  unsigned int v76; // [rsp+110h] [rbp-28h]
  UNICODE_STRING v77; // [rsp+118h] [rbp-20h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v78; // [rsp+128h] [rbp-10h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+130h] [rbp-8h] BYREF
  struct _KERB_PRIMARY_CREDENTIAL *v80; // [rsp+138h] [rbp+0h]
  unsigned int v81; // [rsp+140h] [rbp+8h]
  struct _UNICODE_STRING v82; // [rsp+148h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+158h] [rbp+20h]
  struct _KERB_INTERNAL_NAME *v84; // [rsp+160h] [rbp+28h] BYREF
  _QWORD *v85; // [rsp+168h] [rbp+30h]
  struct _LUID *v86; // [rsp+170h] [rbp+38h]
  struct _KERB_INTERNAL_NAME *v87; // [rsp+178h] [rbp+40h] BYREF
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+180h] [rbp+48h]
  unsigned int v89; // [rsp+188h] [rbp+50h]
  UNICODE_STRING String1; // [rsp+190h] [rbp+58h] BYREF
  int v91; // [rsp+1A8h] [rbp+70h] BYREF
  char v92[4]; // [rsp+1ACh] [rbp+74h] BYREF
  _BYTE v93[16]; // [rsp+1B0h] [rbp+78h] BYREF
  char v94[8]; // [rsp+1C0h] [rbp+88h] BYREF
  unsigned int v95; // [rsp+1C8h] [rbp+90h]
  unsigned __int8 *v96; // [rsp+1D0h] [rbp+98h]
  int v97; // [rsp+1D8h] [rbp+A0h]
  int *v98; // [rsp+1E0h] [rbp+A8h]
  __int64 v99; // [rsp+1F8h] [rbp+C0h]
  int v100; // [rsp+208h] [rbp+D0h] BYREF
  int v101; // [rsp+20Ch] [rbp+D4h]
  __int128 v102; // [rsp+210h] [rbp+D8h]
  __int128 v103; // [rsp+220h] [rbp+E8h]
  __int128 v104; // [rsp+230h] [rbp+F8h]
  __int128 v105; // [rsp+240h] [rbp+108h]
  __int64 v106; // [rsp+250h] [rbp+118h]
  _OWORD v107[2]; // [rsp+258h] [rbp+120h] BYREF
  __int64 v108; // [rsp+278h] [rbp+140h]
  struct KerbCredIsoApi *v109[2]; // [rsp+280h] [rbp+148h] BYREF
  __int128 v110; // [rsp+290h] [rbp+158h]
  __int64 v111; // [rsp+2A0h] [rbp+168h]
  struct _UNICODE_STRING v112; // [rsp+2A8h] [rbp+170h] BYREF
  char v113[8]; // [rsp+2B8h] [rbp+180h] BYREF
  _BYTE v114[16]; // [rsp+2C0h] [rbp+188h] BYREF
  _BYTE v115[32]; // [rsp+2D0h] [rbp+198h] BYREF
  const char *v116; // [rsp+2F0h] [rbp+1B8h]
  char v118; // [rsp+360h] [rbp+228h]
  char v119; // [rsp+368h] [rbp+230h]
  char v121; // [rsp+398h] [rbp+260h]

  S4UTicketCacheEntry = 0;
  v65 = 0;
  v14 = 0;
  v69 = 0;
  v15 = 0;
  v78 = 0;
  v16 = 0;
  v64 = 0;
  v62 = 0;
  if ( !a11 || (v68 = 32, (a8 & 0x100) != 0) )
    v68 = 0;
  v108 = 0;
  v111 = 0;
  memset(v107, 0, sizeof(v107));
  *(_OWORD *)v109 = 0;
  v110 = 0;
  memset_0(&v100, 0, 0x50u);
  v76 = KerbGlobalCacheS4UTicket;
  v71 = 0;
  v17 = 0;
  v84 = 0;
  v70 = 0;
  v112 = 0;
  *(_QWORD *)&v77.Length = 0;
  v77.Buffer = 0;
  v87 = 0;
  v66[0] = 0;
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = 0;
  v81 = 0;
  v67 = 0;
  v91 = 0;
  memset_0(v92, 0, 0x54u);
  memset_0(v113, 0, 0x50u);
  v118 = 0;
  v119 = 0;
  v82 = 0;
  SystemTimeAsFileTime = 0;
  v75 = 0;
  v63 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v18 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 80);
  *(_QWORD *)&SystemTimeAsFileTime += KerbGlobalS4UTicketLifetime.QuadPart;
  v19 = (struct _KERB_LOGON_SESSION *)((char *)a1 + 120);
  v20 = (struct _LUID *)((char *)a1 + 64);
  CriticalSection = v18;
  v86 = v20;
  v80 = v19;
LABEL_5:
  KerbFreePrincipalName(v114);
  KerbFreeRealm(v115);
  memset_0(v113, 0, 0x50u);
  KerbFreePrincipalName(v93);
  KerbFreeRealm(v94);
  KerbFree(v99);
  memset_0(&v91, 0, 0x58u);
  KerbFreePreAuthData(v16);
  v16 = 0;
  hMem = 0;
  RtlEnterCriticalSection(v18);
  v121 = 1;
  S4UTargetName = KerbGetS4UTargetName(&v70, a6, v80, v20, v66);
  if ( S4UTargetName < 0 )
    goto LABEL_162;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
    WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids, v70);
  if ( (a8 & 9) != 0 )
  {
    v22 = v76;
    if ( (a8 & 1) != 0 )
      v22 = 0;
    v76 = v22;
  }
  else
  {
    S4UTicketCacheEntry = KerbLocateS4UTicketCacheEntry(
                            (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v80 + 200),
                            v86,
                            *a4,
                            a6,
                            0,
                            0);
    v65 = S4UTicketCacheEntry;
  }
  if ( S4UTicketCacheEntry )
  {
    v23 = KerbConvertKdcOptionsToTicketFlags(0);
    v24 = S4UTicketCacheEntry;
    if ( (v23 & *((_DWORD *)S4UTicketCacheEntry + 40)) == v23 )
    {
      if ( !KerbTicketIsExpiring(S4UTicketCacheEntry, &KerbGlobalSkewTime) )
        goto LABEL_151;
      v24 = S4UTicketCacheEntry;
    }
    KerbDereferenceTicketCacheEntry(v24);
    S4UTicketCacheEntry = 0;
    v65 = 0;
  }
  RtlLeaveCriticalSection(v18);
  v121 = 0;
  if ( *(_WORD *)*a4 != 6 )
  {
    v25 = KerbConvertKdcNameToPrincipalName((struct KERB_PRINCIPAL_NAME *)v93, *a4);
    if ( v25 )
    {
LABEL_121:
      v53 = v25;
LABEL_122:
      S4UTargetName = KerbMapKerbError(v53);
      goto LABEL_162;
    }
    LOWORD(v91) = v91 | 0x80;
  }
  if ( !a6->Length )
  {
    S4UTargetName = -1073741726;
    KerbTracerT::Log(1, "KerbGetS4USelfServiceTicket", 4012, "KerbGetS4UServiceTicket need client realm\n");
    goto LABEL_162;
  }
  v25 = KerbConvertUnicodeStringToRealm(v94, a6);
  if ( v25 )
    goto LABEL_121;
  v26 = v91 | 0x40;
  LOWORD(v91) = v91 | 0x40;
  if ( a11 )
  {
    v95 = a11;
    v96 = a12;
    LOWORD(v91) = v26 | 0x20;
  }
  v72 = 32;
  v27 = 32;
  v28 = 32;
  v75 = 32;
  if ( (a8 & 0x80u) != 0 )
  {
    v73 = 64;
    v28 = 96;
    v27 = 96;
    v75 = 96;
  }
  if ( (a8 & 0x400) != 0 )
  {
    v74 = 16;
    v27 = v28 | 0x10;
    v75 = v28 | 0x10;
  }
  KerbTracerT::Log(
    21,
    "KerbGetS4USelfServiceTicket",
    4035,
    "KerbGetS4UServiceTicket receives s4u options (network order): %#x\n",
    v27);
  v97 = 32;
  LOWORD(v91) = v91 | 0x10;
  v98 = &v75;
  KerbTracerT::Log(
    21,
    "KerbGetS4USelfServiceTicket",
    4046,
    "KerbGetS4UServiceTicket calling KerbGetTgtToS4URealm ClientRealm %wZ\n");
  TgtToS4URealm = KerbGetTgtToS4URealm(a1, v29, a6, &v69, (unsigned int)a6, v60, v61);
  S4UTargetName = TgtToS4URealm;
  if ( TgtToS4URealm < 0 )
  {
    v56 = "KerbGetS4UServiceTicket cannot get S4U Tgt - %x\n";
    v57 = 4060;
    goto LABEL_159;
  }
  v31 = KerbConvertKdcNameToPrincipalName((struct KERB_PRINCIPAL_NAME *)v114, *a4);
  if ( v31 || (v31 = KerbConvertUnicodeStringToRealm(v115, a6)) != 0 )
  {
    TgtToS4URealm = KerbMapKerbError(v31);
    S4UTargetName = TgtToS4URealm;
    v56 = "KerbGetS4UServiceTicket KerbBuildS4UPreauth failed - %x\n";
    v57 = 4078;
LABEL_159:
    LODWORD(v59) = TgtToS4URealm;
    KerbTracerT::Log(1, "KerbGetS4USelfServiceTicket", v57, v56, v59);
    goto LABEL_160;
  }
  v116 = "Kerberos";
  v89 = a8 & 0x40;
  if ( (a8 & 0x40) != 0 )
  {
    v32 = MIDL_user_allocate(0x20u);
    hMem = v32;
    v16 = v32;
    if ( !v32 )
    {
      S4UTargetName = -1073741801;
      goto LABEL_160;
    }
    *((_DWORD *)v32 + 2) = 131;
    v32[3] = 0;
    *((_DWORD *)v32 + 4) = 0;
    *v32 = 0;
  }
  RtlEnterCriticalSection(v18);
  v33 = v80;
  v121 = 1;
  S4UTargetName = KerbDuplicateStringEx(&String1, (const struct _UNICODE_STRING *)v80 + 1, v34);
  if ( S4UTargetName < 0 )
  {
LABEL_160:
    v14 = v69;
    goto LABEL_162;
  }
  RtlLeaveCriticalSection(v18);
  v35 = (_QWORD *)((char *)v33 + 144);
  v121 = 0;
  v14 = v69;
  while ( 1 )
  {
    v85 = v35;
    if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)v14 + 4, 1u) && !*v35 )
    {
      a10 = 0;
      RtlEnterCriticalSection(v18);
      S4UTargetName = KerbGetTgtForService(a1, 0, 0, 0, 0, (struct _UNICODE_STRING *)v80 + 1, &v112, 0, &v71, &a10);
      RtlLeaveCriticalSection(v18);
      if ( S4UTargetName < 0 )
        goto LABEL_125;
      if ( a10 )
      {
        S4UTargetName = -1073741595;
        KerbTracerT::Log(
          1,
          "KerbGetS4USelfServiceTicket",
          4162,
          "KerbGetS4UServiceTicket got unexpected cross realm TGT");
LABEL_125:
        v54 = 4175;
        goto LABEL_126;
      }
      v17 = v71;
      v100 = 5;
      v101 = 17;
      v102 = *((_OWORD *)v71 + 17);
      v103 = *((_OWORD *)v71 + 18);
      v104 = *((_OWORD *)v71 + 19);
      v105 = *((_OWORD *)v71 + 20);
      v106 = *((_QWORD *)v71 + 42);
    }
    KerbFreeData(74);
    KerbFreeData(76);
    v64 = 0;
    v62 = 0;
    KerbFreeString(&v82);
    KerbFreeKey(v107);
    KerbFreeKey(v109);
    KerbTracerT::Log(
      3,
      "KerbGetS4USelfServiceTicket",
      4188,
      "KerbGetS4UServiceTicket calling KerbGetTgsTicket (ReferralRestart)");
    S4UTargetName = KerbGetTgsTicketEx(
                      0,
                      0,
                      0,
                      v14,
                      v70,
                      a8,
                      0,
                      0,
                      0,
                      (struct KERB_PA_FOR_USER *)v113,
                      (struct PA_S4U_X509_USER *)&v91,
                      (struct KERB_KDC_REQUEST_preauth_data_s *)v16,
                      (struct KERB_TGT_REPLY *)((unsigned __int64)&v100 & -(__int64)(v17 != 0)),
                      0,
                      0,
                      (union _LARGE_INTEGER *)&SystemTimeAsFileTime,
                      &v64,
                      &v62,
                      &v67,
                      &v82,
                      &v63,
                      0);
    if ( S4UTargetName == -1073740792 )
    {
      if ( !v17 )
      {
        a10 = 0;
        RtlEnterCriticalSection(v18);
        S4UTargetName = KerbGetTgtForService(a1, 0, 0, 0, 0, (struct _UNICODE_STRING *)v80 + 1, &v112, 0, &v71, &a10);
        RtlLeaveCriticalSection(v18);
        if ( S4UTargetName < 0 )
          goto LABEL_128;
        if ( a10 )
        {
          S4UTargetName = -1073741595;
          KerbTracerT::Log(
            1,
            "KerbGetS4USelfServiceTicket",
            4254,
            "KerbGetS4UServiceTicket got unexpected cross realm TGT");
LABEL_128:
          v54 = 4260;
LABEL_126:
          KerbTracerT::Log(1, "KerbGetS4USelfServiceTicket", v54, "KerbGetS4UServiceTicket failed to get tgt");
          v17 = v71;
          goto LABEL_162;
        }
        v17 = v71;
        v100 = 5;
        v101 = 17;
        v102 = *((_OWORD *)v71 + 17);
        v103 = *((_OWORD *)v71 + 18);
        v104 = *((_OWORD *)v71 + 19);
        v105 = *((_OWORD *)v71 + 20);
        v106 = *((_QWORD *)v71 + 42);
      }
      KerbTracerT::Log(25, "KerbGetS4USelfServiceTicket", 4267, "KerbGetS4UServiceTicket calling KerbGetTgsTicket");
      S4UTargetName = KerbGetTgsTicketEx(
                        0,
                        0,
                        0,
                        v14,
                        v70,
                        a8,
                        0,
                        0,
                        0,
                        (struct KERB_PA_FOR_USER *)v113,
                        (struct PA_S4U_X509_USER *)&v91,
                        (struct KERB_KDC_REQUEST_preauth_data_s *)v16,
                        (struct KERB_TGT_REPLY *)&v100,
                        0,
                        0,
                        (union _LARGE_INTEGER *)&SystemTimeAsFileTime,
                        &v64,
                        &v62,
                        &v67,
                        &v82,
                        &v63,
                        0);
      if ( S4UTargetName < 0 )
      {
        v37 = 4297;
        goto LABEL_50;
      }
    }
    if ( S4UTargetName >= 0 )
    {
      if ( v17 )
      {
        if ( (unsigned int)KerbDuplicateKey(v107, (char *)v17 + 168) )
        {
          S4UTargetName = -1073741801;
          KerbTracerT::Log(
            1,
            "KerbGetS4USelfServiceTicket",
            4313,
            "KerbGetS4UServiceTicket failed to duplicate u2u key\n");
          goto LABEL_162;
        }
        v68 |= 0x10u;
      }
      if ( (unsigned int)KerbDuplicateKey(v109, (char *)v14 + 168) )
      {
        S4UTargetName = -1073741801;
        KerbTracerT::Log(
          1,
          "KerbGetS4USelfServiceTicket",
          4328,
          "KerbGetS4UServiceTicket failed to duplicate reply key\n");
        goto LABEL_162;
      }
      KerbFreeKdcName(a4);
      v38 = KerbConvertPrincipalNameToKdcName(a4, (struct KERB_PRINCIPAL_NAME *)v93);
      if ( v38 )
      {
        KerbTracerT::Log(
          1,
          "KerbGetS4USelfServiceTicket",
          4341,
          "KerbGetS4UServiceTicket failed to convert name: %#x\n",
          v38);
        v53 = v38;
        goto LABEL_122;
      }
      v16 = hMem;
    }
    if ( v14 )
    {
      if ( (v67 & 2) != 0 && !v119 )
      {
        KerbTracerT::Log(
          2,
          "KerbGetS4USelfServiceTicket",
          4360,
          "KerbGetS4UServiceTicket doing TGT retry - %p\n",
          (const void *)WORD1(v14));
        KerbRemoveTicketCacheEntry(v14);
        KerbDereferenceTicketCacheEntry(v14);
        v14 = 0;
        v119 = 1;
        v69 = 0;
LABEL_116:
        v20 = v86;
        goto LABEL_5;
      }
      KerbDereferenceTicketCacheEntry(v14);
      v14 = 0;
      v69 = 0;
    }
    if ( S4UTargetName < 0 )
      break;
    KerbFreeString(&v77);
    v39 = v70;
    S4UTargetName = KerbGetReferralNames(v62, v70, &v77);
    if ( S4UTargetName < 0 )
      goto LABEL_162;
    if ( !v77.Length )
    {
      RtlEnterCriticalSection(v18);
      v55 = KerbCacheS4UTicket(
              a1,
              v64,
              v62,
              v109[0],
              v39,
              a4,
              a5,
              a6,
              v68 | v63,
              (struct _KERB_TICKET_CACHE *)(((unsigned __int64)v80 + 200) & -(__int64)(v76 != 0)),
              &v82,
              &v65,
              (struct _KERB_ENCRYPTION_KEY *)v107);
LABEL_150:
      S4UTargetName = v55;
      RtlLeaveCriticalSection(v18);
      S4UTicketCacheEntry = v65;
      if ( S4UTargetName < 0 )
        goto LABEL_162;
LABEL_151:
      *a7 = S4UTicketCacheEntry;
      S4UTicketCacheEntry = 0;
      goto LABEL_162;
    }
    S4UTargetName = KerbDuplicateKdcName(&v84, v39);
    if ( S4UTargetName < 0 )
      goto LABEL_162;
    KerbTracerT::Log(
      9,
      "KerbGetS4USelfServiceTicket",
      4484,
      "KerbGetS4UServiceTicket got referral ticket for service in realm %wZ\n",
      &v77);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids, v39);
    S4UTicketCacheEntry = 0;
    S4UTargetName = KerbCreateTicketCacheEntry(v64, v62, v109[0], 0, 0, v63, 0, 0, 0, &v82, 0, 0, &v65);
    if ( S4UTargetName < 0 )
    {
LABEL_148:
      S4UTicketCacheEntry = v65;
      goto LABEL_162;
    }
    v14 = v65;
    v65 = 0;
    KerbFreeData(74);
    KerbFreeData(76);
    v64 = 0;
    v62 = 0;
    if ( (unsigned int)KerbBuildFullServiceKdcNameWithSid(
                         (unsigned int)&v77,
                         (unsigned int)&KerbGlobalKdcServiceName,
                         v40,
                         2,
                         (__int64)&v87) )
    {
      S4UTargetName = -1073741670;
      goto LABEL_162;
    }
    if ( !RtlEqualUnicodeString(&v77, (PCUNICODE_STRING)v14 + 4, 1u) )
    {
      v41 = v87;
      v42 = v14;
      v43 = v14;
      while ( 1 )
      {
        KerbTracerT::Log(9, "KerbGetS4USelfServiceTicket", 4558, "KerbGetS4UServiceTicket realTargetRealm %wZ\n", &v77);
        KerbTracerT::Log(9, "KerbGetS4USelfServiceTicket", 4559, "KerbGetS4UServiceTicket TGT %wZ\n", (char *)v42 + 64);
        v44 = v78;
        if ( v78 )
        {
          v45 = (char *)v78 + 64;
          if ( RtlEqualUnicodeString((PCUNICODE_STRING)v78 + 4, (PCUNICODE_STRING)v43 + 4, 1u) )
          {
            v15 = v78;
            KerbSetTicketCacheEntryTarget(&v77, v78);
            KerbTracerT::Log(
              9,
              "KerbGetS4USelfServiceTicket",
              4573,
              "KerbGetS4UServiceTicket got two TGTs for same realm (%wZ), S4U\n",
              v45);
            goto LABEL_85;
          }
          v44 = v78;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF__KERB_NAME_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids,
            v41);
        KerbFreeData(74);
        KerbFreeData(76);
        v64 = 0;
        v62 = 0;
        KerbFreeString(&v82);
        TgsTicket = KerbGetTgsTicketEx(
                      0,
                      0,
                      0,
                      v14,
                      v41,
                      a8,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      (union _LARGE_INTEGER *)&SystemTimeAsFileTime,
                      &v64,
                      &v62,
                      &v67,
                      &v82,
                      &v63,
                      0);
        S4UTargetName = TgsTicket;
        if ( TgsTicket < 0 )
          break;
        S4UTicketCacheEntry = 0;
        S4UTargetName = KerbCreateTicketCacheEntry(
                          v64,
                          v62,
                          *((struct KerbCredIsoApi **)v14 + 21),
                          0,
                          0,
                          v63,
                          0,
                          0,
                          0,
                          &v82,
                          0,
                          0,
                          &v65);
        if ( S4UTargetName < 0 )
          goto LABEL_148;
        if ( v44 )
          KerbDereferenceTicketCacheEntry(v44);
        v14 = v65;
        v78 = v43;
        v42 = v65;
        v65 = 0;
        v43 = v42;
        if ( RtlEqualUnicodeString(&v77, (PCUNICODE_STRING)v42 + 4, 1u) )
        {
          v15 = v78;
LABEL_85:
          v18 = CriticalSection;
          goto LABEL_86;
        }
      }
      KerbTracerT::Log(
        2,
        "KerbGetS4USelfServiceTicket",
        4616,
        "KerbGetTgsTicket failed to get TGS ticket for service 0x%x",
        TgsTicket);
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v50 = 18;
        v49 = v41;
        goto LABEL_156;
      }
      goto LABEL_162;
    }
LABEL_86:
    KerbFreeData(74);
    KerbFreeData(76);
    v64 = 0;
    v62 = 0;
    KerbFreeString(&v82);
    KerbFreeKey(v107);
    KerbFreeKey(v109);
    KerbFreePreAuthData(hMem);
    v16 = 0;
    hMem = 0;
    if ( v89 )
    {
      v47 = MIDL_user_allocate(0x20u);
      hMem = v47;
      v16 = v47;
      if ( !v47 )
      {
        S4UTargetName = -1073741801;
        goto LABEL_162;
      }
      *((_DWORD *)v47 + 2) = 131;
      v47[3] = 0;
      *((_DWORD *)v47 + 4) = 0;
      *v47 = 0;
    }
    if ( *v85
      && (KerbTracerT::Log(
            3,
            "KerbGetS4USelfServiceTicket",
            4707,
            "KerbGetS4UServiceTicket xForest final calling KerbGetTgsTicket\n"),
          S4UTargetName = KerbGetTgsTicketEx(
                            0,
                            0,
                            0,
                            v14,
                            v70,
                            a8,
                            0,
                            0,
                            0,
                            (struct KERB_PA_FOR_USER *)v113,
                            (struct PA_S4U_X509_USER *)&v91,
                            (struct KERB_KDC_REQUEST_preauth_data_s *)v16,
                            0,
                            0,
                            0,
                            (union _LARGE_INTEGER *)&SystemTimeAsFileTime,
                            &v64,
                            &v62,
                            &v67,
                            &v82,
                            &v63,
                            0),
          *v85)
      && S4UTargetName != -1073740792 )
    {
      if ( S4UTargetName < 0 )
      {
        KerbTracerT::Log(
          2,
          "KerbGetS4USelfServiceTicket",
          4832,
          "KerbGetS4UServiceTicket failed to get TGS ticket for service 0x%x",
          S4UTargetName);
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v49 = v84;
          v50 = 19;
          goto LABEL_156;
        }
        goto LABEL_162;
      }
    }
    else
    {
      a10 = 0;
      if ( v17 )
      {
        if ( S4UTargetName < 0 )
          goto LABEL_146;
      }
      else
      {
        RtlEnterCriticalSection(v18);
        S4UTargetName = KerbGetTgtForService(a1, 0, 0, 0, 0, (struct _UNICODE_STRING *)v80 + 1, &v112, 0, &v71, &a10);
        RtlLeaveCriticalSection(v18);
        if ( S4UTargetName < 0 )
          goto LABEL_137;
        if ( a10 )
        {
          S4UTargetName = -1073741595;
          KerbTracerT::Log(
            1,
            "KerbGetS4USelfServiceTicket",
            4764,
            "KerbGetS4UServiceTicket got unexpected cross realm TGT\n");
LABEL_137:
          v17 = v71;
LABEL_146:
          v37 = 4826;
LABEL_50:
          KerbTracerT::Log(
            1,
            "KerbGetS4USelfServiceTicket",
            v37,
            "KerbGetS4UServiceTicket failed to get TGS ticket for service vis u2u 0x%x\n",
            S4UTargetName);
          goto LABEL_162;
        }
        v17 = v71;
        v100 = 5;
        v101 = 17;
        v102 = *((_OWORD *)v71 + 17);
        v103 = *((_OWORD *)v71 + 18);
        v104 = *((_OWORD *)v71 + 19);
        v105 = *((_OWORD *)v71 + 20);
        v106 = *((_QWORD *)v71 + 42);
      }
      KerbTracerT::Log(
        25,
        "KerbGetS4USelfServiceTicket",
        4778,
        "KerbGetS4UServiceTicket xForest final u2u calling KerbGetTgsTicket\n");
      S4UTargetName = KerbGetTgsTicketEx(
                        0,
                        0,
                        0,
                        v14,
                        v70,
                        a8,
                        0,
                        0,
                        0,
                        (struct KERB_PA_FOR_USER *)v113,
                        (struct PA_S4U_X509_USER *)&v91,
                        (struct KERB_KDC_REQUEST_preauth_data_s *)v16,
                        (struct KERB_TGT_REPLY *)&v100,
                        0,
                        0,
                        (union _LARGE_INTEGER *)&SystemTimeAsFileTime,
                        &v64,
                        &v62,
                        &v67,
                        &v82,
                        &v63,
                        0);
      if ( S4UTargetName < 0 )
        goto LABEL_146;
      KerbFreeKey(v107);
      if ( (unsigned int)KerbDuplicateKey(v107, (char *)v17 + 168) )
      {
        S4UTargetName = -1073741801;
        goto LABEL_146;
      }
      v68 |= 0x10u;
    }
    if ( v14 && (unsigned int)KerbDuplicateKey(v109, (char *)v14 + 168) )
    {
      S4UTargetName = -1073741801;
      KerbTracerT::Log(
        1,
        "KerbGetS4USelfServiceTicket",
        4846,
        "KerbGetS4UServiceTicket failed to duplicate reply key\n");
      goto LABEL_162;
    }
    KerbFreeKdcName(a4);
    v51 = KerbConvertPrincipalNameToKdcName(a4, (struct KERB_PRINCIPAL_NAME *)v93);
    v52 = v51;
    if ( v51 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetS4USelfServiceTicket",
        4860,
        "KerbGetS4UServiceTicket failed to convert name: %#x\n",
        v51);
      v53 = v52;
      goto LABEL_122;
    }
    KerbFreeString(&v77);
    S4UTargetName = KerbGetReferralNames(v62, v84, &v77);
    if ( S4UTargetName < 0 )
      goto LABEL_162;
    if ( !v77.Length )
    {
      RtlEnterCriticalSection(v18);
      v55 = KerbCacheS4UTicket(
              a1,
              v64,
              v62,
              v109[0],
              v70,
              a4,
              a5,
              a6,
              v68 | v63,
              (struct _KERB_TICKET_CACHE *)(((unsigned __int64)v80 + 200) & -(__int64)(v76 != 0)),
              &v82,
              &v65,
              (struct _KERB_ENCRYPTION_KEY *)v107);
      goto LABEL_150;
    }
    if ( v81 > KerbGlobalMaxReferralCount )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF__KERB_NAME_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids,
          v84);
      S4UTargetName = -1073741068;
      goto LABEL_162;
    }
    S4UTicketCacheEntry = 0;
    S4UTargetName = KerbCreateTicketCacheEntry(
                      v64,
                      v62,
                      *((struct KerbCredIsoApi **)v14 + 21),
                      0,
                      0,
                      v63,
                      0,
                      0,
                      0,
                      &v82,
                      0,
                      0,
                      &v65);
    KerbFreeData(74);
    KerbFreeData(76);
    v64 = 0;
    v62 = 0;
    if ( S4UTargetName < 0 )
      goto LABEL_148;
    ++v81;
    if ( v15 )
      KerbDereferenceTicketCacheEntry(v15);
    v78 = v14;
    v15 = v14;
    v14 = v65;
    v69 = v65;
    v65 = 0;
    KerbTracerT::Log(9, "KerbGetS4USelfServiceTicket", 4945, "KerbGetS4UServiceTicket restart referral: %wZ", &v77);
    v35 = v85;
  }
  if ( (v67 & 1) != 0 && !v118 )
  {
    S4UTargetName = KerbMITGetMachineDomain(v36, a6, &v69);
    if ( S4UTargetName >= 0 )
    {
      v14 = v69;
      v118 = 1;
      goto LABEL_116;
    }
    KerbTracerT::Log(1, "KerbGetS4USelfServiceTicket", 4395, "KerbGetS4UServiceTicket failed Query policy information");
    goto LABEL_160;
  }
  KerbTracerT::Log(
    2,
    "KerbGetS4USelfServiceTicket",
    4404,
    "KerbGetS4UServiceTicket failed to get TGS ticket for service 0x%x",
    S4UTargetName);
  v48 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v49 = v70;
    v50 = 15;
LABEL_156:
    WPP_SF__KERB_NAME_(v48[2], v50, WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids, v49);
  }
LABEL_162:
  KerbFreeData(74);
  KerbFreeData(76);
  KerbFreeKdcName(&v87);
  KerbFreeString(&v77);
  KerbFreeKdcName(&v84);
  KerbFreeKdcName(&v70);
  KerbFreePrincipalName(v114);
  KerbFreeRealm(v115);
  KerbFreePrincipalName(v93);
  KerbFreeRealm(v94);
  KerbFree(v99);
  KerbFreePreAuthData(hMem);
  if ( v17 )
    KerbDereferenceTicketCacheEntry(v17);
  if ( v121 )
    RtlLeaveCriticalSection(CriticalSection);
  KerbFreeString(&v77);
  if ( v14 )
    KerbDereferenceTicketCacheEntry(v14);
  if ( v78 )
    KerbDereferenceTicketCacheEntry(v78);
  if ( S4UTicketCacheEntry )
  {
    KerbRemoveTicketCacheEntry(S4UTicketCacheEntry);
    KerbDereferenceTicketCacheEntry(S4UTicketCacheEntry);
  }
  KerbFreeString(&String1);
  KerbFreeKey(v107);
  KerbFreeKey(v109);
  KerbFreeString(&v82);
  return (unsigned int)S4UTargetName;
}

```

## disassembly

```asm
0x180054c88  mov     rax, rsp
0x180054c8b  mov     [rax+20h], r9
0x180054c8f  mov     [rax+18h], r8
0x180054c93  mov     [rax+10h], rdx
0x180054c97  mov     [rax+8], rcx
0x180054c9b  push    rbp
0x180054c9c  push    rbx
0x180054c9d  push    rsi
0x180054c9e  push    rdi
0x180054c9f  push    r12
0x180054ca1  push    r13
0x180054ca3  push    r14
0x180054ca5  push    r15
0x180054ca7  lea     rbp, [rax-218h]
0x180054cae  sub     rsp, 308h
0x180054cb5  xor     r12d, r12d
0x180054cb8  mov     rbx, rcx
0x180054cbb  mov     esi, r12d
0x180054cbe  mov     [rbp+210h+var_278], r12
0x180054cc2  mov     edi, r12d
0x180054cc5  mov     [rbp+210h+var_260], r12
0x180054cc9  mov     r13d, r12d
0x180054ccc  mov     [rbp+210h+var_220], r12
0x180054cd0  mov     r15d, r12d
0x180054cd3  mov     [rbp+210h+var_280], r12
0x180054cd7  mov     [rbp+210h+var_290], r12
0x180054cdb  cmp     [rbp+210h+arg_50], r12d
0x180054ce2  jz      short loc_180054CF7
0x180054ce4  test    [rbp+210h+arg_38], 100h
0x180054cee  mov     [rbp+210h+var_268], 20h ; ' '
0x180054cf5  jz      short loc_180054CFB
0x180054cf7  mov     [rbp+210h+var_268], r12d
0x180054cfb  xor     eax, eax
0x180054cfd  lea     rcx, [rbp+210h+var_140]; void *
0x180054d04  xorps   xmm0, xmm0
0x180054d07  mov     [rbp+210h+var_D0], rax
0x180054d0e  xorps   xmm1, xmm1
0x180054d11  mov     [rbp+210h+var_A8], rax
0x180054d18  xor     edx, edx; Val
0x180054d1a  lea     r8d, [rax+50h]; Size
0x180054d1e  movups  [rbp+210h+var_F0], xmm0
0x180054d25  movups  [rbp+210h+var_E0], xmm0
0x180054d2c  movups  xmmword ptr [rbp+210h+var_C8], xmm1
0x180054d33  movups  [rbp+210h+var_B8], xmm1
0x180054d3a  call    memset_0
0x180054d3f  mov     ecx, cs:?KerbGlobalCacheS4UTicket@@3KA; ulong KerbGlobalCacheS4UTicket
0x180054d45  xor     edx, edx; Val
0x180054d47  xorps   xmm0, xmm0
0x180054d4a  mov     [rbp+210h+var_238], ecx
0x180054d4d  lea     rcx, [rbp+210h+var_19C]; void *
0x180054d51  mov     [rbp+210h+var_250], r12
0x180054d55  mov     r14, r12
0x180054d58  mov     [rbp+210h+var_1E8], r12
0x180054d5c  lea     r8d, [rdx+54h]; Size
0x180054d60  mov     [rbp+210h+var_258], r12
0x180054d64  movups  xmmword ptr [rbp+210h+var_A0.Length], xmm0
0x180054d6b  mov     qword ptr [rbp+210h+var_230.Length], r12
0x180054d6f  mov     [rbp+210h+var_230.Buffer], r12
0x180054d73  mov     [rbp+210h+var_1D0], r12
0x180054d77  mov     [rbp+210h+var_270], r12b
0x180054d7b  mov     qword ptr [rbp+210h+String1.Length], r12
0x180054d7f  mov     [rbp+210h+String1.Buffer], r12
0x180054d83  mov     [rbp+210h+var_208], r12d
0x180054d87  mov     [rbp+210h+var_26C], r12d
0x180054d8b  mov     [rbp+210h+var_1A0], r12d
0x180054d8f  call    memset_0
0x180054d94  xor     edx, edx; Val
0x180054d96  lea     rcx, [rbp+210h+var_90]; void *
0x180054d9d  lea     r8d, [rdx+50h]; Size
0x180054da1  call    memset_0
0x180054da6  xorps   xmm0, xmm0
0x180054da9  mov     [rbp+210h+arg_8], r12b
0x180054db0  lea     rcx, [rbp+210h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180054db4  mov     [rbp+210h+arg_10], r12b
0x180054dbb  movups  xmmword ptr [rbp+210h+var_200.Length], xmm0
0x180054dbf  mov     qword ptr [rbp+210h+SystemTimeAsFileTime.dwLowDateTime], r12
0x180054dc3  mov     [rbp+210h+var_23C], r12d
0x180054dc7  mov     [rbp+210h+var_288], r12d
0x180054dcb  call    cs:__imp_GetSystemTimeAsFileTime
0x180054dd1  mov     rax, cs:?KerbGlobalS4UTicketLifetime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalS4UTicketLifetime
0x180054dd8  lea     r12, [rbx+50h]
0x180054ddc  add     qword ptr [rbp+210h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180054de0  lea     rax, [rbx+78h]
0x180054de4  add     rbx, 40h ; '@'
0x180054de8  mov     [rbp+210h+CriticalSection], r12
0x180054dec  mov     [rbp+210h+var_1D8], rbx
0x180054df0  mov     [rbp+210h+var_210], rax
0x180054df4  lea     rcx, [rbp+210h+var_88]
0x180054dfb  call    KerbFreePrincipalName
0x180054e00  lea     rcx, [rbp+210h+var_78]
0x180054e07  call    KerbFreeRealm
0x180054e0c  xor     edx, edx; Val
0x180054e0e  lea     rcx, [rbp+210h+var_90]; void *
0x180054e15  lea     r8d, [rdx+50h]; Size
0x180054e19  call    memset_0
0x180054e1e  lea     rcx, [rbp+210h+var_198]
0x180054e22  call    KerbFreePrincipalName
0x180054e27  lea     rcx, [rbp+210h+var_188]
0x180054e2e  call    KerbFreeRealm
0x180054e33  mov     rcx, [rbp+210h+var_150]
0x180054e3a  call    KerbFree
0x180054e3f  xor     edx, edx; Val
0x180054e41  lea     rcx, [rbp+210h+var_1A0]; void *
0x180054e45  lea     r8d, [rdx+58h]; Size
0x180054e49  call    memset_0
0x180054e4e  mov     rcx, r15; hMem
0x180054e51  call    KerbFreePreAuthData
0x180054e56  xor     r15d, r15d
0x180054e59  mov     rcx, r12; CriticalSection
0x180054e5c  mov     [rbp+210h+hMem], r15
0x180054e60  call    cs:__imp_RtlEnterCriticalSection
0x180054e66  mov     r8, [rbp+210h+var_210]; struct _KERB_PRIMARY_CREDENTIAL *
0x180054e6a  lea     rax, [rbp+210h+var_270]
0x180054e6e  mov     rdx, [rbp+210h+arg_28]; struct _UNICODE_STRING *
0x180054e75  lea     rcx, [rbp+210h+var_258]; struct _KERB_INTERNAL_NAME **
0x180054e79  mov     r9, rbx; struct _LUID *
0x180054e7c  mov     [rsp+340h+var_320], rax; unsigned __int8 *
0x180054e81  mov     [rbp+210h+arg_40], 1
0x180054e88  call    ?KerbGetS4UTargetName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@PEAU_KERB_PRIMARY_CREDENTIAL@@PEAU_LUID@@PEAE@Z; KerbGetS4UTargetName(_KERB_INTERNAL_NAME * *,_UNICODE_STRING *,_KERB_PRIMARY_CREDENTIAL *,_LUID *,uchar *)
0x180054e8d  xor     edx, edx
0x180054e8f  mov     ebx, eax
0x180054e91  test    eax, eax
0x180054e93  js      loc_1800563AF
0x180054e99  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ea0  lea     rax, WPP_GLOBAL_Control
0x180054ea7  cmp     rcx, rax
0x180054eaa  jz      short loc_180054ECF
0x180054eac  test    dword ptr [rcx+1Ch], 100000h
0x180054eb3  jz      short loc_180054ECF
0x180054eb5  mov     r9, [rbp+210h+var_258]
0x180054eb9  lea     edx, [r15+0Eh]
0x180054ebd  mov     rcx, [rcx+10h]
0x180054ec1  lea     r8, WPP_0cd4f8b3ce863effc6e95b4025302777_Traceguids
0x180054ec8  call    WPP_SF__KERB_NAME_
0x180054ecd  xor     edx, edx
0x180054ecf  mov     eax, [rbp+210h+arg_38]
0x180054ed5  test    al, 9
0x180054ed7  jnz     short loc_180054F10
0x180054ed9  mov     r8, [rbp+210h+arg_18]
0x180054ee0  mov     rcx, [rbp+210h+var_210]
0x180054ee4  mov     r9, [rbp+210h+arg_28]; struct _UNICODE_STRING *
0x180054eeb  add     rcx, 0C8h; struct _KERB_TICKET_CACHE *
0x180054ef2  mov     dword ptr [rsp+340h+var_318], edx; unsigned int
0x180054ef6  mov     r8, [r8]; struct _KERB_INTERNAL_NAME *
0x180054ef9  mov     [rsp+340h+var_320], rdx; struct _KERB_INTERNAL_NAME *
0x180054efe  mov     rdx, [rbp+210h+var_1D8]; struct _LUID *
0x180054f02  call    ?KerbLocateS4UTicketCacheEntry@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_LUID@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@2K@Z; KerbLocateS4UTicketCacheEntry(_KERB_TICKET_CACHE *,_LUID *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_KERB_INTERNAL_NAME *,ulong)
0x180054f07  mov     rsi, rax
0x180054f0a  mov     [rbp+210h+var_278], rax
0x180054f0e  jmp     short loc_180054F1B
0x180054f10  mov     ecx, [rbp+210h+var_238]
0x180054f13  test    al, 1
0x180054f15  cmovnz  ecx, edx
0x180054f18  mov     [rbp+210h+var_238], ecx
0x180054f1b  test    rsi, rsi
0x180054f1e  jz      short loc_180054F58
0x180054f20  xor     ecx, ecx; unsigned int
0x180054f22  call    ?KerbConvertKdcOptionsToTicketFlags@@YAKK@Z; KerbConvertKdcOptionsToTicketFlags(ulong)
0x180054f27  mov     ecx, [rsi+0A0h]
0x180054f2d  and     ecx, eax
0x180054f2f  cmp     ecx, eax
0x180054f31  mov     rcx, rsi; struct _KERB_TICKET_CACHE_ENTRY *
0x180054f34  jnz     short loc_180054F4D
0x180054f36  lea     rdx, ?KerbGlobalSkewTime@@3T_LARGE_INTEGER@@A; union _LARGE_INTEGER *
0x180054f3d  call    ?KerbTicketIsExpiring@@YAEPEAU_KERB_TICKET_CACHE_ENTRY@@PEAT_LARGE_INTEGER@@@Z; KerbTicketIsExpiring(_KERB_TICKET_CACHE_ENTRY *,_LARGE_INTEGER *)
0x180054f42  test    al, al
0x180054f44  jz      loc_1800562BE
0x180054f4a  mov     rcx, rsi; struct _KERB_TICKET_CACHE_ENTRY *
0x180054f4d  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180054f52  xor     esi, esi
0x180054f54  mov     [rbp+210h+var_278], rsi
0x180054f58  mov     rcx, r12; CriticalSection
0x180054f5b  call    cs:__imp_RtlLeaveCriticalSection
0x180054f61  mov     rax, [rbp+210h+arg_18]
0x180054f68  mov     [rbp+210h+arg_40], r15b
0x180054f6f  mov     rdx, [rax]; struct _KERB_INTERNAL_NAME *
0x180054f72  cmp     word ptr [rdx], 6
0x180054f76  jz      short loc_180054F92
0x180054f78  lea     rcx, [rbp+210h+var_198]; struct KERB_PRINCIPAL_NAME *
0x180054f7c  call    ?KerbConvertKdcNameToPrincipalName@@YAJPEAUKERB_PRINCIPAL_NAME@@PEAU_KERB_INTERNAL_NAME@@@Z; KerbConvertKdcNameToPrincipalName(KERB_PRINCIPAL_NAME *,_KERB_INTERNAL_NAME *)
0x180054f81  test    eax, eax
0x180054f83  jnz     loc_180055F90
0x180054f89  mov     eax, 80h
0x180054f8e  or      word ptr [rbp+210h+var_1A0], ax
0x180054f92  mov     rbx, [rbp+210h+arg_28]
0x180054f99  xor     eax, eax
0x180054f9b  cmp     [rbx], ax
0x180054f9e  jz      loc_18005638C
0x180054fa4  mov     rdx, rbx
0x180054fa7  lea     rcx, [rbp+210h+var_188]
0x180054fae  call    KerbConvertUnicodeStringToRealm
0x180054fb3  test    eax, eax
0x180054fb5  jnz     loc_180055F90
0x180054fbb  movzx   ecx, word ptr [rbp+210h+var_1A0]
0x180054fbf  lea     r8d, [rax+40h]
0x180054fc3  mov     eax, [rbp+210h+arg_50]
0x180054fc9  or      cx, r8w
0x180054fcd  mov     word ptr [rbp+210h+var_1A0], cx
0x180054fd1  test    eax, eax
0x180054fd3  jz      short loc_180054FF1
0x180054fd5  mov     [rbp+210h+var_180], eax
0x180054fdb  or      cx, 20h
0x180054fdf  mov     rax, [rbp+210h+arg_58]
0x180054fe6  mov     [rbp+210h+var_178], rax
0x180054fed  mov     word ptr [rbp+210h+var_1A0], cx
0x180054ff1  mov     edi, [rbp+210h+arg_38]
0x180054ff7  mov     [rbp+210h+var_248], 20h ; ' '
0x180054ffe  mov     ecx, [rbp+210h+var_248]
0x180055001  mov     eax, ecx
0x180055003  mov     [rbp+210h+var_23C], ecx
0x180055006  test    dil, dil
0x180055009  jns     short loc_180055019
0x18005500b  mov     eax, r8d
0x18005500e  mov     [rbp+210h+var_244], r8d
0x180055012  or      eax, ecx
0x180055014  mov     ecx, eax
0x180055016  mov     [rbp+210h+var_23C], eax
0x180055019  bt      edi, 0Ah
0x18005501d  jnb     short loc_18005502E
0x18005501f  mov     [rbp+210h+var_240], 10h
0x180055026  mov     ecx, [rbp+210h+var_240]
0x180055029  or      ecx, eax
0x18005502b  mov     [rbp+210h+var_23C], ecx
0x18005502e  mov     dword ptr [rsp+340h+var_320], ecx
0x180055032  lea     r9, aKerbgets4userv_11; "KerbGetS4UServiceTicket receives s4u op"...
0x180055039  mov     ecx, 15h
0x18005503e  lea     rdx, aKerbgets4uself; "KerbGetS4USelfServiceTicket"
0x180055045  mov     r8d, 0FC3h
0x18005504b  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180055050  mov     eax, 10h
0x180055055  mov     [rbp+210h+var_170], 20h ; ' '
0x18005505f  or      word ptr [rbp+210h+var_1A0], ax
0x180055063  lea     r9, aKerbgets4userv_12; "KerbGetS4UServiceTicket calling KerbGet"...
0x18005506a  lea     rax, [rbp+210h+var_23C]
0x18005506e  mov     [rsp+340h+var_320], rbx; unsigned int
0x180055073  mov     r8d, 0FCEh
0x180055079  mov     [rbp+210h+var_168], rax
0x180055080  lea     rdx, aKerbgets4uself; "KerbGetS4USelfServiceTicket"
0x180055087  mov     ecx, 15h
0x18005508c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180055091  mov     rcx, [rbp+210h+arg_0]; struct _KERB_LOGON_SESSION *
0x180055098  lea     r9, [rbp+210h+var_260]; struct _KERB_TICKET_CACHE_ENTRY **
0x18005509c  mov     r8, rbx; struct _UNICODE_STRING *
0x18005509f  call    ?KerbGetTgtToS4URealm@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_UNICODE_STRING@@PEAPEAU_KERB_TICKET_CACHE_ENTRY@@KKK@Z; KerbGetTgtToS4URealm(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_UNICODE_STRING *,_KERB_TICKET_CACHE_ENTRY * *,ulong,ulong,ulong)
0x1800550a4  mov     ebx, eax
0x1800550a6  test    eax, eax
0x1800550a8  js      loc_180056364
0x1800550ae  mov     rax, [rbp+210h+arg_18]
0x1800550b5  lea     rcx, [rbp+210h+var_88]; struct KERB_PRINCIPAL_NAME *
0x1800550bc  mov     rdx, [rax]; struct _KERB_INTERNAL_NAME *
0x1800550bf  call    ?KerbConvertKdcNameToPrincipalName@@YAJPEAUKERB_PRINCIPAL_NAME@@PEAU_KERB_INTERNAL_NAME@@@Z; KerbConvertKdcNameToPrincipalName(KERB_PRINCIPAL_NAME *,_KERB_INTERNAL_NAME *)
0x1800550c4  xor     ebx, ebx
0x1800550c6  test    eax, eax
0x1800550c8  jnz     loc_18005634C
0x1800550ce  mov     rdx, [rbp+210h+arg_28]
0x1800550d5  lea     rcx, [rbp+210h+var_78]
0x1800550dc  call    KerbConvertUnicodeStringToRealm
0x1800550e1  test    eax, eax
0x1800550e3  jnz     loc_18005634C
0x1800550e9  lea     rax, aKerberos_4; "Kerberos"
0x1800550f0  mov     [rbp+210h+var_58], rax
0x1800550f7  mov     eax, edi
0x1800550f9  and     eax, 40h
0x1800550fc  mov     [rbp+210h+var_1C0], eax
0x1800550ff  jz      short loc_18005512A
0x180055101  lea     ecx, [rbx+20h]; size
0x180055104  call    MIDL_user_allocate
0x180055109  mov     [rbp+210h+hMem], rax
0x18005510d  mov     r15, rax
0x180055110  test    rax, rax
0x180055113  jz      loc_180055F9E
0x180055119  mov     dword ptr [rax+8], 83h
0x180055120  mov     [rax+18h], rbx
0x180055124  mov     [rax+10h], ebx
0x180055127  mov     [rax], rbx
0x18005512a  mov     rcx, r12; CriticalSection
0x18005512d  call    cs:__imp_RtlEnterCriticalSection
0x180055133  mov     rdi, [rbp+210h+var_210]
0x180055137  lea     rcx, [rbp+210h+String1]; struct _UNICODE_STRING *
0x18005513b  mov     [rbp+210h+arg_40], 1
0x180055142  lea     rdx, [rdi+10h]; struct _UNICODE_STRING *
0x180055146  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18005514b  mov     ebx, eax
0x18005514d  test    eax, eax
0x18005514f  js      loc_180056386
0x180055155  mov     rcx, r12; CriticalSection
0x180055158  call    cs:__imp_RtlLeaveCriticalSection
0x18005515e  lea     rbx, [rdi+90h]
0x180055165  mov     [rbp+210h+arg_40], 0
0x18005516c  mov     rdi, [rbp+210h+var_260]
0x180055170  mov     [rbp+210h+var_1E0], rbx
0x180055174  lea     rdx, [rdi+40h]; String2
0x180055178  mov     r8b, 1; CaseInsensitive
0x18005517b  lea     rcx, [rbp+210h+String1]; String1
0x18005517f  call    cs:__imp_RtlEqualUnicodeString
0x180055185  xor     ecx, ecx
0x180055187  test    al, al
0x180055189  jz      loc_18005527F
0x18005518f  cmp     [rbx], rcx
0x180055192  jnz     loc_18005527F
  ... truncated ...
```
