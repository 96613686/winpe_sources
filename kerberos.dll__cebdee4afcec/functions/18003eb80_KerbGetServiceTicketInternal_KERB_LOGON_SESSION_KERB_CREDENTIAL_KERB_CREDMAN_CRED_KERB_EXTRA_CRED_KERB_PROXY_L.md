# KerbGetServiceTicketInternal(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_EXTRA_CRED *,_KERB_PROXY_LOGON_CRED *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,ulong,ulong,ulong,KERB_ERROR *,PKERB_AUTHORIZATION_DATA_s *,KERB_TGT_REPLY *,_KERB_TICKET_CACHE_ENTRY * *,_GUID *,_KERB_ENCRYPTION_KEY *)

- ea: `0x18003eb80`
- end: `0x180040fb1`
- name: `?KerbGetServiceTicketInternal@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_EXTRA_CRED@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@KKKPEAUKERB_ERROR@@PEAUPKERB_AUTHORIZATION_DATA_s@@PEAUKERB_TGT_REPLY@@PEAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_GUID@@PEAU_KERB_ENCRYPTION_KEY@@@Z`
- size: `9265`
- prototype: `int(struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, struct _KERB_CREDMAN_CRED *, struct _KERB_EXTRA_CRED *, struct _KERB_PROXY_LOGON_CRED *, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, unsigned int, unsigned int, unsigned int, struct KERB_ERROR *, struct PKERB_AUTHORIZATION_DATA_s *, struct KERB_TGT_REPLY *, struct _KERB_TICKET_CACHE_ENTRY **, struct _GUID *, struct _KERB_ENCRYPTION_KEY *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f8b0`

## callees

- `0x1800063e8`
- `0x180006920`
- `0x18000b300`
- `0x1800113f0`
- `0x180016550`
- `0x1800190c0`
- `0x1800290c0`
- `0x180032964`
- `0x1800376ec`
- `0x18003d3f0`
- `0x18003e9d8`
- `0x18003eb80`
- `0x180041178`
- `0x180041d18`
- `0x180048390`
- `0x18004ed20`
- `0x18005e9a0`
- `0x180061e4c`
- `0x18006250c`
- `0x18006557c`
- `0x180070680`
- `0x180088040`
- `0x18008a304`
- `0x18008b70c`
- `0x1800b4190`
- `0x1800c0120`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f553`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f553`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ef5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ef5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f03d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f40e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f43e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f690`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fa25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fc0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fd9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fe38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ff22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040423`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040872`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040dc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040df1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040e1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040e4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040e76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040eb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040f3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040f66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f03d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f40e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f43e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f690`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fa25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fc0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fd9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fe38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ff22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040423`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040872`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040dc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040df1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040e1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040e4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040e76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040eb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040f3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040f66`
- `ntdll!RtlEqualUnicodeString` at `0x18003f31a`
- `ntdll!RtlEqualUnicodeString` at `0x18003f32e`
- `ntdll!RtlEqualUnicodeString` at `0x18003f82d`
- `ntdll!RtlEqualUnicodeString` at `0x18003f901`
- `ntdll!RtlEqualUnicodeString` at `0x18003f962`
- `ntdll!RtlEqualUnicodeString` at `0x18003faba`
- `ntdll!RtlEqualUnicodeString` at `0x18003fae0`
- `ntdll!RtlEqualUnicodeString` at `0x18003fd4f`
- `ntdll!RtlEqualUnicodeString` at `0x18004002a`
- `ntdll!RtlEqualUnicodeString` at `0x18003f31a`
- `ntdll!RtlEqualUnicodeString` at `0x18003f32e`
- `ntdll!RtlEqualUnicodeString` at `0x18003f82d`
- `ntdll!RtlEqualUnicodeString` at `0x18003f901`
- `ntdll!RtlEqualUnicodeString` at `0x18003f962`
- `ntdll!RtlEqualUnicodeString` at `0x18003faba`
- `ntdll!RtlEqualUnicodeString` at `0x18003fae0`
- `ntdll!RtlEqualUnicodeString` at `0x18003fd4f`
- `ntdll!RtlEqualUnicodeString` at `0x18004002a`
- `ntdll!EtwEventWriteTransfer` at `0x18003f65e`
- `ntdll!EtwEventWriteTransfer` at `0x18003f65e`
- `ntdll!RtlEnterCriticalSection` at `0x18003ed29`
- `ntdll!RtlEnterCriticalSection` at `0x18003f78f`
- `ntdll!RtlEnterCriticalSection` at `0x18003fa97`
- `ntdll!RtlEnterCriticalSection` at `0x18003fc9e`
- `ntdll!RtlEnterCriticalSection` at `0x18003fd69`
- `ntdll!RtlEnterCriticalSection` at `0x18003ff91`
- `ntdll!RtlEnterCriticalSection` at `0x1800403f3`
- `ntdll!RtlEnterCriticalSection` at `0x1800404cf`
- `ntdll!RtlEnterCriticalSection` at `0x180040699`
- `ntdll!RtlEnterCriticalSection` at `0x180040842`
- `ntdll!RtlEnterCriticalSection` at `0x18004093d`
- `ntdll!RtlEnterCriticalSection` at `0x18003ed29`
- `ntdll!RtlEnterCriticalSection` at `0x18003f78f`
- `ntdll!RtlEnterCriticalSection` at `0x18003fa97`
- `ntdll!RtlEnterCriticalSection` at `0x18003fc9e`
- `ntdll!RtlEnterCriticalSection` at `0x18003fd69`
- `ntdll!RtlEnterCriticalSection` at `0x18003ff91`
- `ntdll!RtlEnterCriticalSection` at `0x1800403f3`
- `ntdll!RtlEnterCriticalSection` at `0x1800404cf`
- `ntdll!RtlEnterCriticalSection` at `0x180040699`
- `ntdll!RtlEnterCriticalSection` at `0x180040842`
- `ntdll!RtlEnterCriticalSection` at `0x18004093d`
- `ntdll!RtlLeaveCriticalSection` at `0x18003f386`
- `ntdll!RtlLeaveCriticalSection` at `0x18003f852`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fb0b`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fc02`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fd1a`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fdbb`
- `ntdll!RtlLeaveCriticalSection` at `0x18004000d`
- `ntdll!RtlLeaveCriticalSection` at `0x18004043d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800405d2`
- `ntdll!RtlLeaveCriticalSection` at `0x18004078b`
- `ntdll!RtlLeaveCriticalSection` at `0x18004088c`
- `ntdll!RtlLeaveCriticalSection` at `0x180040a2f`
- `ntdll!RtlLeaveCriticalSection` at `0x180040e89`
- `ntdll!RtlLeaveCriticalSection` at `0x18003f386`
- `ntdll!RtlLeaveCriticalSection` at `0x18003f852`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fb0b`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fc02`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fd1a`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fdbb`
- `ntdll!RtlLeaveCriticalSection` at `0x18004000d`
- `ntdll!RtlLeaveCriticalSection` at `0x18004043d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800405d2`
- `ntdll!RtlLeaveCriticalSection` at `0x18004078b`
- `ntdll!RtlLeaveCriticalSection` at `0x18004088c`
- `ntdll!RtlLeaveCriticalSection` at `0x180040a2f`
- `ntdll!RtlLeaveCriticalSection` at `0x180040e89`
- `LSASRV!LsaIGetLogonGuid` at `0x180040c17`
- `LSASRV!LsaIGetLogonGuid` at `0x180040c17`

## string_xrefs

- `0x18003ed95`: `KerbGetServiceTicketInternal credman autologon restricted for %#x:%#x\n`
- `0x18003eda2`: `KerbGetServiceTicketInternal`
- `0x18003f079`: `KerbGetServiceTicketInternal`
- `0x18003f0d4`: `KerbGetServiceTicketInternal`
- `0x18003f0f2`: `KerbGetServiceTicketInternal`
- `0x18003f18c`: `KerbGetServiceTicketInternal`
- `0x18003f1ae`: `KerbGetServiceTicketInternal`
- `0x18003f6cd`: `KerbGetServiceTicketInternal`
- `0x18003f749`: `KerbGetServiceTicketInternal`
- `0x18003f8e5`: `KerbGetServiceTicketInternal`
- `0x18003f93f`: `KerbGetServiceTicketInternal`
- `0x18003fa40`: `KerbGetServiceTicketInternal`
- `0x18003fa6b`: `KerbGetServiceTicketInternal`
- `0x18003fc4e`: `KerbGetServiceTicketInternal`
- `0x18003fc80`: `KerbGetServiceTicketInternal`
- `0x18003fdd3`: `KerbGetServiceTicketInternal`
- `0x18003ff5f`: `KerbGetServiceTicketInternal`
- `0x180040069`: `KerbGetServiceTicketInternal`
- `0x1800400bd`: `KerbGetServiceTicketInternal`
- `0x18004016d`: `KerbGetServiceTicketInternal`
- `0x1800401e5`: `KerbGetServiceTicketInternal`
- `0x180040248`: `KerbGetServiceTicketInternal`
- `0x1800402a2`: `KerbGetServiceTicketInternal`
- `0x180040351`: `KerbGetServiceTicketInternal`
- `0x180040452`: `KerbGetServiceTicketInternal`
- `0x180040610`: `KerbGetServiceTicketInternal`
- `0x180040643`: `KerbGetServiceTicketInternal`
- `0x1800407c6`: `KerbGetServiceTicketInternal`
- `0x1800408a1`: `KerbGetServiceTicketInternal`
- `0x180040a6e`: `KerbGetServiceTicketInternal`
- `0x180040af0`: `KerbGetServiceTicketInternal`
- `0x180040b4a`: `KerbGetServiceTicketInternal`
- `0x180040b7c`: `KerbGetServiceTicketInternal`
- `0x180040d0d`: `KerbGetServiceTicketInternal`
- `0x180040b71`: `KerbGetServiceTicketInternal autologon restricted for %#x:%#x\n`
- `0x180040b3d`: `KerbGetServiceTicket trying to crack zero length name.\n`
- `0x18004023c`: `KerbGetServiceTicket found ticket cache entry %p\n`
- `0x180040297`: `KerbGetServiceTicket target Realm: %wZ\n`
- `0x18003f05e`: `Found SPN cache entry - %wZ\n`
- `0x18003f0c3`: `KerbGetSpnCacheStatus failed %x\n`
- `0x18003f165`: `KerbGetSpnCacheStatus failed but SPN Oracle says otherwise: %x\n`
- `0x180040adf`: `Failed to get TGT for service: 0x%x`
- `0x180040632`: `Failed to get TGS ticket for service 0x%x`
- `0x1800407b5`: `Failed to get TGS ticket for service 0x%x`
- `0x180040a5d`: `Failed to get TGS ticket for service 0x%x`
- `0x18003f8d9`: `KerbGetServiceTicket loop RealTargetRealm %wZ\n`
- `0x18003fc74`: `KerbGetServiceTicket updated RealTargetRealm %wZ\n`
- `0x180040058`: `KerbGetServiceTicket Restart referral RealTargetRealm: %wZ\n`
- `0x180040d06`: `KerbGetServiceTicket by process %d, TARGET_UNKNOWN for %wZ\%wZ LogonId %#x:%#x\n`

## pseudocode

```c
__int64 __fastcall KerbGetServiceTicketInternal(
        struct _KERB_LOGON_SESSION *a1,
        struct _KERB_CREDENTIAL *a2,
        struct _KERB_CREDMAN_CRED *a3,
        struct _KERB_EXTRA_CRED *a4,
        struct _KERB_PROXY_LOGON_CRED *a5,
        struct _KERB_INTERNAL_NAME *a6,
        struct _UNICODE_STRING *a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        struct KERB_ERROR *a11,
        struct PKERB_AUTHORIZATION_DATA_s *a12,
        struct KERB_TGT_REPLY *a13,
        struct _KERB_TICKET_CACHE_ENTRY **a14,
        struct _GUID *a15,
        struct _KERB_ENCRYPTION_KEY *a16)
{
  struct _KERB_INTERNAL_NAME *v17; // rsi
  struct _KERB_TICKET_CACHE_ENTRY *v20; // r15
  struct _KERB_TICKET_CACHE_ENTRY *v21; // r13
  PLSA_GET_EXTENDED_CALL_FLAGS GetExtendedCallFlags; // rax
  HLOCAL v23; // r14
  __int64 v24; // rdx
  int TgsTicketWithBranch; // ebx
  struct KERB_ENCRYPTED_KDC_REPLY *v26; // r8
  struct _RTL_CRITICAL_SECTION *v27; // rdi
  struct _KERB_PRIMARY_CREDENTIAL *v28; // rax
  char v29; // di
  char v30; // r12
  bool v31; // di
  struct _KERB_TICKET_CACHE *v32; // rcx
  unsigned int v33; // r9d
  struct _KERB_TICKET_CACHE_ENTRY *TicketCacheEntry; // rdi
  struct _KERB_TICKET_CACHE_ENTRY *v35; // rcx
  unsigned int v36; // edx
  int v37; // ecx
  int v38; // edx
  int v39; // ecx
  int v40; // edx
  int v41; // ecx
  union _LARGE_INTEGER v42; // rsi
  unsigned int v43; // edi
  PCUNICODE_STRING v44; // rbx
  int SpnCacheStatus; // eax
  _QWORD *v46; // rcx
  __int64 v47; // rdx
  int v48; // eax
  int v49; // eax
  HLOCAL *v50; // rax
  int TgtForService; // eax
  const UNICODE_STRING *v52; // rdi
  struct _KERB_ENCRYPTION_KEY *v53; // rbx
  unsigned __int8 v54; // bl
  HLOCAL v55; // rcx
  struct _KERB_INTERNAL_NAME *v56; // rcx
  DWORD CurrentThreadId; // eax
  struct _RTL_CRITICAL_SECTION *v58; // r14
  unsigned __int64 v59; // rcx
  struct _KERB_INTERNAL_NAME *v60; // rdi
  PVOID *v61; // rcx
  struct _KERB_INTERNAL_NAME *v62; // r14
  __int64 *v63; // rdi
  unsigned int v64; // ebx
  struct KERB_TGT_REPLY *v65; // rcx
  int v66; // eax
  struct _RTL_CRITICAL_SECTION *v67; // r14
  unsigned __int64 v68; // rcx
  void *v69; // rcx
  int v70; // eax
  unsigned __int64 v71; // rcx
  const void *v72; // rcx
  int v73; // edi
  const void *v74; // rcx
  int v75; // edi
  const void *v76; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *v77; // rax
  const void *v78; // rcx
  struct _KERB_TICKET_CACHE_ENTRY **v79; // rax
  HLOCAL v80; // r14
  int HubTicketForAuthenticationTicket; // eax
  struct _KERB_TICKET_CACHE_ENTRY *v82; // rdi
  const struct _UNICODE_STRING *v83; // rsi
  struct _RTL_CRITICAL_SECTION *v84; // r14
  struct _UNICODE_STRING *v85; // rdi
  PWSTR Buffer; // rcx
  _QWORD *v87; // rcx
  __int64 v88; // rdx
  struct _KERB_TICKET_CACHE_ENTRY *v89; // rax
  unsigned __int64 v90; // rdx
  int v91; // eax
  unsigned __int64 v92; // rcx
  struct _KERB_TICKET_CACHE *v93; // rax
  bool v94; // cf
  struct _KERB_TICKET_CACHE_ENTRY *v95; // rax
  struct _RTL_CRITICAL_SECTION *v96; // rdi
  unsigned __int64 v97; // rcx
  int v98; // eax
  unsigned __int64 v99; // rdx
  struct _KERB_TICKET_CACHE *v100; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v101; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v102; // rdi
  const struct _UNICODE_STRING *v103; // rsi
  struct _RTL_CRITICAL_SECTION *v104; // r14
  struct _UNICODE_STRING *v105; // rdi
  PWSTR v106; // rcx
  struct _RTL_CRITICAL_SECTION *v107; // rdi
  unsigned __int64 v108; // rcx
  int v109; // eax
  unsigned __int64 v110; // rdx
  struct _KERB_TICKET_CACHE *v111; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v112; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v113; // rcx
  struct _KERB_PRIMARY_CREDENTIAL *v114; // rax
  struct _UNICODE_STRING *v115; // r9
  struct _KERB_PRIMARY_CREDENTIAL *v116; // r12
  _QWORD *v117; // rdx
  void *v118; // rcx
  _QWORD *v119; // rdi
  struct _UNICODE_STRING *v121; // [rsp+20h] [rbp-120h]
  struct _UNICODE_STRING *v122; // [rsp+28h] [rbp-118h]
  struct _KERB_TICKET_CACHE *v123; // [rsp+38h] [rbp-108h]
  union _LARGE_INTEGER v124; // [rsp+40h] [rbp-100h]
  struct KERB_KDC_REQUEST_preauth_data_s **v125; // [rsp+60h] [rbp-E0h]
  struct KERB_TICKET *v126; // [rsp+70h] [rbp-D0h]
  struct _KERB_ENCRYPTION_KEY *v127; // [rsp+78h] [rbp-C8h]
  union _LARGE_INTEGER *v128; // [rsp+80h] [rbp-C0h]
  char v129; // [rsp+C0h] [rbp-80h]
  char v130; // [rsp+C4h] [rbp-7Ch]
  struct _KERB_TICKET_CACHE_ENTRY *v131; // [rsp+C8h] [rbp-78h] BYREF
  unsigned __int8 v132; // [rsp+D0h] [rbp-70h] BYREF
  char v133; // [rsp+D1h] [rbp-6Fh]
  struct _KERB_INTERNAL_NAME *v134; // [rsp+D8h] [rbp-68h]
  HLOCAL v135; // [rsp+E0h] [rbp-60h] BYREF
  char v136; // [rsp+E8h] [rbp-58h]
  unsigned int v137; // [rsp+ECh] [rbp-54h]
  unsigned int v138; // [rsp+F0h] [rbp-50h] BYREF
  struct KERB_ENCRYPTED_KDC_REPLY *v139; // [rsp+F8h] [rbp-48h] BYREF
  char v140; // [rsp+100h] [rbp-40h]
  char v141; // [rsp+101h] [rbp-3Fh]
  struct _KERB_PRIMARY_CREDENTIAL *v142; // [rsp+108h] [rbp-38h]
  unsigned int v143; // [rsp+110h] [rbp-30h] BYREF
  struct KERB_KDC_REPLY *v144; // [rsp+118h] [rbp-28h] BYREF
  HLOCAL hMem[2]; // [rsp+120h] [rbp-20h] BYREF
  PCUNICODE_STRING String1; // [rsp+130h] [rbp-10h]
  int v147; // [rsp+138h] [rbp-8h]
  unsigned int v148; // [rsp+13Ch] [rbp-4h]
  unsigned int v149; // [rsp+140h] [rbp+0h]
  struct _KERB_LOGON_SESSION *v150; // [rsp+148h] [rbp+8h]
  struct KERB_TGT_REPLY *v151; // [rsp+150h] [rbp+10h]
  struct _KERB_TICKET_CACHE_ENTRY *v152; // [rsp+158h] [rbp+18h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY **v153; // [rsp+160h] [rbp+20h]
  HLOCAL v154[2]; // [rsp+168h] [rbp+28h] BYREF
  HLOCAL v155; // [rsp+178h] [rbp+38h] BYREF
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+180h] [rbp+40h]
  int v157; // [rsp+188h] [rbp+48h] BYREF
  unsigned int v158; // [rsp+18Ch] [rbp+4Ch]
  HLOCAL v159[2]; // [rsp+190h] [rbp+50h] BYREF
  HLOCAL v160; // [rsp+1A0h] [rbp+60h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1A8h] [rbp+68h] BYREF
  struct _KERB_EXTRA_CRED *v162; // [rsp+1B0h] [rbp+70h]
  struct _KERB_CREDMAN_CRED *v163; // [rsp+1B8h] [rbp+78h]
  struct _KERB_PROXY_LOGON_CRED *v164; // [rsp+1C0h] [rbp+80h]
  struct _KERB_ENCRYPTION_KEY *v165; // [rsp+1C8h] [rbp+88h]
  union _LARGE_INTEGER v166; // [rsp+1D0h] [rbp+90h] BYREF
  int v167; // [rsp+1D8h] [rbp+98h] BYREF
  DWORD v168; // [rsp+1DCh] [rbp+9Ch] BYREF
  _QWORD *v169; // [rsp+1E0h] [rbp+A0h]
  __int128 v170; // [rsp+1E8h] [rbp+A8h] BYREF
  __int64 v171; // [rsp+1F8h] [rbp+B8h]
  __int64 v172; // [rsp+200h] [rbp+C0h] BYREF
  struct _GUID *v173; // [rsp+208h] [rbp+C8h]
  struct PKERB_AUTHORIZATION_DATA_s *v174; // [rsp+210h] [rbp+D0h]
  struct _GUID v175; // [rsp+218h] [rbp+D8h] BYREF
  char *v176; // [rsp+230h] [rbp+F0h] BYREF
  int v177; // [rsp+238h] [rbp+F8h]
  int v178; // [rsp+23Ch] [rbp+FCh]
  char *v179; // [rsp+240h] [rbp+100h]
  int v180; // [rsp+248h] [rbp+108h]
  int v181; // [rsp+24Ch] [rbp+10Ch]
  __int64 *v182; // [rsp+250h] [rbp+110h]
  __int64 v183; // [rsp+258h] [rbp+118h]
  DWORD *v184; // [rsp+260h] [rbp+120h]
  __int64 v185; // [rsp+268h] [rbp+128h]
  int *v186; // [rsp+270h] [rbp+130h]
  __int64 v187; // [rsp+278h] [rbp+138h]

  v17 = a6;
  v164 = a5;
  String1 = a7;
  v148 = a10;
  v151 = a13;
  v153 = a14;
  v150 = a1;
  v165 = a16;
  v174 = a12;
  v160 = a12;
  v147 = KerbGlobalMaxReferralCount;
  v173 = a15;
  v131 = 0;
  v20 = 0;
  v152 = 0;
  v21 = 0;
  GetExtendedCallFlags = LsaFunctions->GetExtendedCallFlags;
  v23 = 0;
  v166.QuadPart = 0;
  v144 = 0;
  v139 = 0;
  v132 = 0;
  v155 = 0;
  hMem[0] = 0;
  hMem[1] = 0;
  v135 = 0;
  v159[0] = 0;
  v159[1] = 0;
  v158 = 0;
  v143 = 0;
  v140 = 0;
  v141 = 0;
  v138 = 0;
  v157 = 0;
  v162 = a4;
  v163 = a3;
  v134 = a6;
  v133 = 1;
  v175 = 0;
  v136 = 1;
  *(_OWORD *)v154 = 0;
  ((void (__fastcall *)(int *))GetExtendedCallFlags)(&v157);
  v137 = a8;
  v149 = a8 & 0x80000;
  TgsTicketWithBranch = KerbAddAuthzDataForTGS(a2, a3, (struct PKERB_AUTHORIZATION_DATA_s **)&v160);
  v169 = v160;
  if ( TgsTicketWithBranch < 0 )
  {
    v142 = 0;
    v30 = 0;
    goto LABEL_357;
  }
  v27 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 80);
  CriticalSection = v27;
LABEL_3:
  KerbFreeData(74);
  KerbFreeData(76);
  v144 = 0;
  v139 = 0;
  RtlEnterCriticalSection(v27);
  v129 = 1;
  if ( v162 )
  {
    v28 = (struct _KERB_PRIMARY_CREDENTIAL *)*((_QWORD *)v162 + 8);
    v142 = v28;
    v130 = 1;
    goto LABEL_19;
  }
  if ( a2 )
  {
    v28 = (struct _KERB_PRIMARY_CREDENTIAL *)*((_QWORD *)a2 + 9);
    v142 = v28;
    if ( v28 )
    {
      v130 = 1;
      goto LABEL_19;
    }
  }
  if ( v163 )
  {
    v28 = (struct _KERB_PRIMARY_CREDENTIAL *)*((_QWORD *)v163 + 8);
    v142 = v28;
    v130 = 1;
    if ( a2 && (*((_BYTE *)a2 + 64) & 0x10) != 0 || (v157 & 4) != 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetServiceTicketInternal",
        6920,
        "KerbGetServiceTicketInternal credman autologon restricted for %#x:%#x\n",
        *((_DWORD *)v150 + 17),
        *((_DWORD *)v150 + 16));
LABEL_13:
      TgsTicketWithBranch = -2146893042;
      goto LABEL_14;
    }
  }
  else
  {
    v28 = (struct _KERB_LOGON_SESSION *)((char *)v150 + 120);
    v31 = (*((_DWORD *)v150 + 226) & 0x20000) != 0;
    v142 = (struct _KERB_LOGON_SESSION *)((char *)v150 + 120);
    v130 = v31;
    if ( a2 && (*((_BYTE *)a2 + 64) & 0x10) != 0 || (v157 & 4) != 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetServiceTicketInternal",
        6951,
        "KerbGetServiceTicketInternal autologon restricted for %#x:%#x\n",
        *((_DWORD *)v150 + 17),
        *((_DWORD *)v150 + 16));
      v130 = v31;
      goto LABEL_13;
    }
  }
LABEL_19:
  if ( !*((_WORD *)v17 + 1) || !*((_WORD *)v17 + 4) )
  {
    KerbTracerT::Log(
      1,
      "KerbGetServiceTicketInternal",
      6964,
      "KerbGetServiceTicket trying to crack zero length name.\n");
    v29 = 1;
    TgsTicketWithBranch = -2146893053;
    v17 = v134;
    v30 = v130;
    goto LABEL_358;
  }
  if ( v149 )
  {
    v32 = (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v28 + 240);
    v33 = 0;
LABEL_23:
    TicketCacheEntry = KerbLocateTicketCacheEntryEx(v32, v17, (struct _UNICODE_STRING *)String1, v33);
    v131 = TicketCacheEntry;
    goto LABEL_28;
  }
  if ( !v151 && (v137 & 1) == 0 )
  {
    v33 = v148;
    v32 = (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v28 + 160);
    goto LABEL_23;
  }
  TicketCacheEntry = v131;
LABEL_28:
  if ( TicketCacheEntry )
  {
    if ( a11 && *((_DWORD *)a11 + 13) == 41 )
    {
      KerbRemoveTicketCacheEntry(TicketCacheEntry);
      v35 = v131;
    }
    else
    {
      v36 = a9 & 0x40000000 | 0x20000000;
      if ( (a9 & 0x20000000) == 0 )
        v36 = a9 & 0x40000000;
      v37 = v36 | 0x10000000;
      if ( (a9 & 0x10000000) == 0 )
        v37 = v36;
      v38 = v37 | 0x8000000;
      if ( (a9 & 0x8000000) == 0 )
        v38 = v37;
      v39 = v38 | 0x2000000;
      if ( (a9 & 0x2000000) == 0 )
        v39 = v38;
      v40 = v39 | 0x4000000;
      if ( (a9 & 0x4000000) == 0 )
        v40 = v39;
      v41 = v40 | 0x800000;
      if ( (a9 & 0x800000) == 0 )
        v41 = v40;
      if ( (v41 & *((_DWORD *)TicketCacheEntry + 40)) == v41 && (!v148 || *((_DWORD *)TicketCacheEntry + 77) == v148) )
      {
        if ( (v137 & 0x40000) != 0 )
        {
          v42.QuadPart = 10066329000000000LL;
        }
        else if ( (v137 & 4) != 0 )
        {
          v42.QuadPart = 600000000LL * (KerbGlobalTgtRenewalTime / 0x3C);
        }
        else
        {
          v42 = KerbGlobalSkewTime;
        }
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        *(_QWORD *)&SystemTimeAsFileTime += v42.QuadPart + 10000000LL * *((int *)TicketCacheEntry + 86);
        if ( *((_QWORD *)TicketCacheEntry + 32) >= *(__int64 *)&SystemTimeAsFileTime )
        {
          v77 = v131;
          *v153 = v131;
          if ( v77 )
            v78 = (const void *)WORD1(v77);
          else
            v78 = 0;
          KerbTracerT::Log(
            11,
            "KerbGetServiceTicketInternal",
            7065,
            "KerbGetServiceTicket found ticket cache entry %p\n",
            v78);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            WPP_SF__KERB_NAME_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids,
              *((_QWORD *)v131 + 5));
          KerbTracerT::Log(
            11,
            "KerbGetServiceTicketInternal",
            7067,
            "KerbGetServiceTicket target Realm: %wZ\n",
            (char *)v131 + 48);
          v79 = v153;
          v29 = 1;
          v17 = v134;
          v80 = v135;
          v30 = v130;
          v131 = 0;
          goto LABEL_360;
        }
        KerbDereferenceTicketCacheEntry(v131);
        v17 = v134;
        goto LABEL_56;
      }
      v35 = TicketCacheEntry;
    }
    KerbDereferenceTicketCacheEntry(v35);
LABEL_56:
    v131 = 0;
  }
  if ( a9 || v148 )
  {
    v43 = v137;
    if ( (v137 & 0x20) == 0 )
    {
LABEL_66:
      v133 = 0;
      goto LABEL_67;
    }
  }
  else
  {
    v43 = v137;
  }
  if ( (v43 & 1) != 0 || v151 || !a2 && !v149 )
    goto LABEL_66;
LABEL_67:
  v44 = String1;
  if ( (v43 & 0x2000000) == 0 || String1->Buffer )
    goto LABEL_90;
  SpnCacheStatus = KerbGetSpnCacheStatus(v17, v142, (struct _UNICODE_STRING *)v159);
  TgsTicketWithBranch = SpnCacheStatus;
  if ( SpnCacheStatus < 0 )
  {
    if ( SpnCacheStatus == -1073741198 )
    {
      v49 = KerbQuerySpnOracle(v150, v142, &a8, v17, (struct _UNICODE_STRING *)hMem);
      v136 = 0;
      TgsTicketWithBranch = v49;
      if ( (int)(v49 + 0x80000000) >= 0 && v49 != -1073741198 )
        goto LABEL_14;
      v43 = a8;
      v44 = String1;
      v137 = a8;
      goto LABEL_90;
    }
    KerbTracerT::Log(19, "KerbGetServiceTicketInternal", 7122, "KerbGetSpnCacheStatus failed %x\n", SpnCacheStatus);
    KerbTracerT::Log(19, "KerbGetServiceTicketInternal", 7123, "TargetName: \n");
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, v17);
    v48 = KerbQuerySpnOracle(v150, v142, &a8, v17, (struct _UNICODE_STRING *)hMem);
    if ( v48 < 0 )
    {
      v29 = 1;
      v17 = v134;
      v30 = v130;
      v141 = 1;
      goto LABEL_358;
    }
    v43 = a8 & 0xFFFFEFFF;
    v159[0] = 0;
    v159[1] = 0;
    v136 = 0;
    v137 = a8 & 0xFFFFEFFF;
    a8 &= ~0x1000u;
    KerbTracerT::Log(
      19,
      "KerbGetServiceTicketInternal",
      7146,
      "KerbGetSpnCacheStatus failed but SPN Oracle says otherwise: %x\n",
      v48);
    KerbTracerT::Log(19, "KerbGetServiceTicketInternal", 7147, "TargetName: \n");
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      goto LABEL_86;
    v47 = 23;
  }
  else
  {
    if ( hMem[1] )
    {
      if ( KerbGlobalPackageState == 1 )
        ((void (*)(void))LsaFunctions->FreeLsaHeap)();
      else
        LocalFree(hMem[1]);
    }
    *(_OWORD *)hMem = *(_OWORD *)v159;
    v43 |= 0x1000u;
    v159[0] = 0;
    v159[1] = 0;
    v137 = v43;
    a8 = v43;
    KerbTracerT::Log(19, "KerbGetServiceTicketInternal", 7115, "Found SPN cache entry - %wZ\n", hMem);
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      goto LABEL_86;
    v47 = 21;
  }
  WPP_SF__KERB_NAME_(v46[2], v47, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, v17);
LABEL_86:
  v44 = String1;
LABEL_90:
  if ( (v143 & 1) != 0 )
  {
    if ( hMem[1] )
    {
      if ( KerbGlobalPackageState == 1 )
        ((void (*)(void))LsaFunctions->FreeLsaHeap)();
      else
        LocalFree(hMem[1]);
    }
    *(_OWORD *)hMem = 0;
  }
  v50 = hMem;
  if ( !hMem[1] )
    v50 = (HLOCAL *)v44;
  TgtForService = KerbGetTgtForService(v150, a2, v163, v162, v164, 0, (struct _UNICODE_STRING *)v50, v43, &v152, &v132);
  TgsTicketWithBranch = TgtForService;
  if ( TgtForService < 0 )
  {
    KerbTracerT::Log(1, "KerbGetServiceTicketInternal", 7227, "Failed to get TGT for service: 0x%x", TgtForService);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, v17);
    v20 = v152;
    v29 = 1;
    v17 = v134;
    v30 = v130;
    goto LABEL_358;
  }
  v20 = v152;
  if ( v149 )
  {
    if ( (v43 & 0x200000) != 0 && *((char *)v152 + 304) < 0 && HIWORD(*((_DWORD *)v152 + 78)) )
    {
      HubTicketForAuthenticationTicket = KerbGetHubTicketForAuthenticationTicket(
                                           v150,
                                           0,
                                           0,
                                           0,
                                           v164,
                                           0,
                                           v152,
                                           v43 & 0x80000,
                                           (union _LARGE_INTEGER)&v166);
      TgsTicketWithBranch = HubTicketForAuthenticationTicket;
      if ( HubTicketForAuthenticationTicket >= 0 )
      {
        v29 = 1;
        v17 = v134;
        v30 = v130;
        *v153 = (struct _KERB_TICKET_CACHE_ENTRY *)v166.QuadPart;
        v166.QuadPart = 0;
        goto LABEL_358;
      }
      LODWORD(v121) = HubTicketForAuthenticationTicket;
      KerbTracerT::Log(1, "KerbGetServiceTicketInternal", 7251, "Failed to get primary TGT from Hub DC: %#x\n", v121);
      goto LABEL_261;
    }
    v52 = String1;
    if ( RtlEqualUnicodeString(String1, (PCUNICODE_STRING)v152 + 4, 1u) )
    {
      if ( RtlEqualUnicodeString(v52, (PCUNICODE_STRING)v20 + 3, 1u) )
      {
        *v153 = v20;
        v20 = 0;
        KerbTracerT::Log(16, "KerbGetServiceTicketInternal", 7267, "got a probing ticket from the domain %wZ\n", v52);
LABEL_261:
        v29 = 1;
        v17 = v134;
        v30 = v130;
        goto LABEL_358;
      }
    }
  }
  if ( v20 )
  {
    v53 = v165;
    if ( v165 )
    {
      KerbFreeKey(v165);
      if ( (unsigned int)KerbDuplicateKey(v53, (char *)v20 + 208) )
      {
        TgsTicketWithBranch = -1073741670;
        LODWORD(v121) = -1073741670;
        KerbTracerT::Log(1, "KerbGetServiceTicketInternal", 7282, "Failed to duplicate credential key: 0x%x", v121);
        goto LABEL_261;
      }
    }
  }
  v54 = v132;
  v27 = CriticalSection;
  if ( (v143 & 1) != 0 )
    v54 = 1;
  v132 = v54;
  RtlLeaveCriticalSection(CriticalSection);
  while ( 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, v17);
    KerbFreeData(74);
    KerbFreeData(76);
    v55 = v154[1];
    v144 = 0;
    v139 = 0;
    if ( v154[1] )
    {
      if ( KerbGlobalPackageState == 1 )
        ((void (*)(void))LsaFunctions->FreeLsaHeap)();
      else
        LocalFree(v154[1]);
    }
    *(_OWORD *)v154 = 0;
    if ( v23 )
    {
      if ( KerbGlobalPackageState == 1 )
        ((void (__fastcall *)(HLOCAL))LsaFunctions->FreeLsaHeap)(v23);
      else
        LocalFree(v23);
      v23 = 0;
      v155 = 0;
    }
    if ( v54 )
    {
      if ( (v137 & 0x10000000) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v55);
      TgsTicketWithBranch = KerbDuplicateKdcName((struct _KERB_INTERNAL_NAME **)&v155, v17);
      if ( TgsTicketWithBranch < 0 )
        goto LABEL_295;
      v129 = 0;
      if ( !hMem[1] )
      {
        v129 = 0;
        TgsTicketWithBranch = KerbDuplicateStringEx((struct _UNICODE_STRING *)hMem, String1);
        if ( TgsTicketWithBranch < 0 )
          goto LABEL_295;
      }
      goto LABEL_155;
    }
    TgsTicketWithBranch = KerbGetTgsTicketWithBranchEx(
                            v150,
                            a2,
                            v163,
                            v162,
                            v164,
                            v122,
                            v20,
                            v17,
                            v137,
                            a9,
                            v148,
                            (struct PKERB_AUTHORIZATION_DATA_s *)v160,
                            v125,
                            v151,
                            v126,
                            v127,
                            v128,
                            &v144,
                            &v139,
                            &v143,
                            (struct _UNICODE_STRING *)v154,
                            &v138,
                            v165);
    if ( v20 )
    {
      if ( (*((_DWORD *)v20 + 41) & 0x400) != 0 && (unsigned int)dword_180140048 > 5 )
      {
        v56 = (struct _KERB_INTERNAL_NAME *)qword_180140060;
        if ( (qword_180140058 & 0x400000000000LL) != 0 && (qword_180140060 & 0x400000000000LL) == qword_180140060 )
        {
          v167 = TgsTicketWithBranch;
          CurrentThreadId = GetCurrentThreadId();
          v172 = 0x1000000;
          v168 = CurrentThreadId;
          v187 = 4;
          v186 = &v167;
          v185 = 4;
          v184 = &v168;
          v183 = 8;
          v182 = &v172;
          *((_QWORD *)&v170 + 1) = 0x400000000000LL;
          v176 = (char *)off_180140050;
          *(_QWORD *)&v170 = 0x50B000000LL;
          v177 = *(unsigned __int16 *)off_180140050;
          v179 = &byte_18012B77F;
          v178 = 2;
          v180 = 66;
          v181 = 1;
          SystemTimeAsFileTime.dwLowDateTime = (unsigned int)&TraceLoggingMetadataEnd
                                             - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180140068, &v170, 0, 0, 5, &v176);
        }
      }
    }
    if ( TgsTicketWithBranch < 0 )
    {
      if ( (v143 & 2) != 0 && v147 > 0 )
      {
        if ( v20 )
          v72 = (const void *)WORD1(v20);
        else
          v72 = 0;
        KerbTracerT::Log(2, "KerbGetServiceTicketInternal", 7369, "Doing TGT retry 1 - %p\n", v72);
        KerbRemoveTicketCacheEntry(v20);
        KerbDereferenceTicketCacheEntry(v20);
        v20 = 0;
        --v147;
        v152 = 0;
        goto LABEL_3;
      }
      if ( (v143 & 1) == 0 || v140 )
      {
        KerbTracerT::Log(
          2,
          "KerbGetServiceTicketInternal",
          7405,
          "Failed to get TGS ticket for service 0x%x",
          TgsTicketWithBranch);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF__KERB_NAME_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids,
            v17);
          v17 = v134;
          v30 = v130;
          goto LABEL_357;
        }
      }
      else
      {
        TgsTicketWithBranch = KerbMITGetMachineDomain(v56, (struct _UNICODE_STRING *)String1, &v152);
        if ( TgsTicketWithBranch >= 0 )
        {
          v20 = v152;
          v137 &= ~0x1000u;
          a8 = v137;
          v140 = 1;
          goto LABEL_3;
        }
        KerbTracerT::Log(3, "KerbGetServiceTicketInternal", 7396, "Failed Query policy information");
        v20 = v152;
      }
LABEL_295:
      v17 = v134;
      v30 = v130;
LABEL_357:
      v29 = 0;
      goto LABEL_358;
    }
    if ( hMem[1] )
    {
      if ( KerbGlobalPackageState == 1 )
        ((void (*)(void))LsaFunctions->FreeLsaHeap)();
      else
        LocalFree(hMem[1]);
    }
    *(_OWORD *)hMem = 0;
    TgsTicketWithBranch = KerbGetReferralNames(v139, v17, (struct _UNICODE_STRING *)hMem);
    if ( TgsTicketWithBranch < 0 )
      goto LABEL_295;
    KerbTracerT::Log(
      11,
      "KerbGetServiceTicketInternal",
      7428,
      "KerbGetReferralNames returns RealTargetRealm %wZ\n",
      hMem);
    if ( !LOWORD(hMem[0]) )
      break;
    TgsTicketWithBranch = KerbDuplicateKdcName((struct _KERB_INTERNAL_NAME **)&v155, v17);
    if ( TgsTicketWithBranch < 0 )
      goto LABEL_295;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, v17);
    KerbTracerT::Log(11, "KerbGetServiceTicketInternal", 7513, "in realm %wZ\n", hMem);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, v155);
    v58 = CriticalSection;
    RtlEnterCriticalSection(CriticalSection);
    v129 = 1;
    if ( a2 )
      v59 = *((_QWORD *)a2 + 16);
    else
      v59 = 0;
    TgsTicketWithBranch = KerbCreateTicketCacheEntry(
                            v144,
                            v139,
                            *((struct KerbCredIsoApi **)v20 + 21),
                            0,
                            0,
                            v138,
                            *((_DWORD *)v20 + 86),
                            (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v142 + 240),
                            0,
                            (struct _UNICODE_STRING *)v154,
                            0,
                            v59,
                            &v131);
    if ( TgsTicketWithBranch < 0 )
      goto LABEL_14;
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)v20 + 4, (PCUNICODE_STRING)v131 + 4, 1u) )
    {
      v82 = v131;
      if ( *((_WORD *)v17 + 1) < 2u )
        v83 = 0;
      else
        v83 = (const struct _UNICODE_STRING *)((char *)v17 + 24);
      v84 = (struct _RTL_CRITICAL_SECTION *)((char *)v131 + 368);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v131 + 368));
      v85 = (struct _UNICODE_STRING *)((char *)v82 + 80);
      if ( v85 )
      {
        Buffer = v85->Buffer;
        if ( Buffer )
        {
          if ( KerbGlobalPackageState == 1 )
            ((void (*)(void))LsaFunctions->FreeLsaHeap)();
          else
            LocalFree(Buffer);
        }
        *v85 = 0;
      }
      KerbDuplicateStringEx(v85, v83);
      RtlLeaveCriticalSection(v84);
      KerbTracerT::Log(
        11,
        "KerbGetServiceTicketInternal",
        7555,
        "Referral has reached target domain (%wZ) (case 1)\n",
        (char *)v131 + 64);
      v87 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        v17 = v134;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
LABEL_279:
          v89 = v131;
          v29 = v129;
          v30 = v130;
          v131 = 0;
          *v153 = v89;
          goto LABEL_358;
        }
        v88 = 29;
LABEL_277:
        WPP_SF__KERB_NAME_(v87[2], v88, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, v17);
        goto LABEL_279;
      }
LABEL_278:
      v17 = v134;
      goto LABEL_279;
    }
    KerbDereferenceTicketCacheEntry(v20);
    v20 = v131;
    v131 = 0;
    RtlLeaveCriticalSection(v58);
    v129 = 0;
LABEL_155:
    if ( (unsigned int)KerbBuildFullServiceKdcNameWithSid(
                         (unsigned int)hMem,
                         (unsigned int)&KerbGlobalKdcServiceName,
                         (_DWORD)v26,
                         2,
                         (__int64)&v135) )
    {
      v29 = 0;
      TgsTicketWithBranch = -1073741670;
      v17 = v134;
      v30 = v130;
      goto LABEL_358;
    }
    KerbTracerT::Log(11, "KerbGetServiceTicketInternal", 7631, "KerbGetServiceTicket loop RealTargetRealm %wZ\n", hMem);
    if ( !RtlEqualUnicodeString((PCUNICODE_STRING)hMem, (PCUNICODE_STRING)v20 + 4, 1u) )
    {
      v60 = (struct _KERB_INTERNAL_NAME *)v135;
      do
      {
        v122 = (struct _UNICODE_STRING *)((char *)v20 + 64);
        KerbTracerT::Log(
          11,
          "KerbGetServiceTicketInternal",
          7648,
          "got two different names: RealTargetRealm %wZ, TGT TargetDomainName %wZ\n",
          hMem);
        if ( v21 && RtlEqualUnicodeString((PCUNICODE_STRING)v21 + 4, (PCUNICODE_STRING)v20 + 4, 1u) )
        {
          RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v21 + 368));
          if ( v21 != (struct _KERB_TICKET_CACHE_ENTRY *)-80LL )
          {
            v69 = (void *)*((_QWORD *)v21 + 11);
            if ( v69 )
            {
              if ( KerbGlobalPackageState == 1 )
                ((void (*)(void))LsaFunctions->FreeLsaHeap)();
              else
                LocalFree(v69);
            }
            *((_OWORD *)v21 + 5) = 0;
          }
          KerbDuplicateStringEx((struct _UNICODE_STRING *)v21 + 5, (const struct _UNICODE_STRING *)hMem);
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v21 + 368));
          KerbTracerT::Log(
            11,
            "KerbGetServiceTicketInternal",
            7667,
            "Got two TGTs for same realm (%wZ), bailing out of referral loop\n",
            (char *)v21 + 64);
          v17 = v134;
          break;
        }
        v61 = (PVOID *)WPP_GLOBAL_Control;
        v62 = v60;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WPP_SF__KERB_NAME_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids,
              v60);
            v61 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v61 != &WPP_GLOBAL_Control && (*((_DWORD *)v61 + 7) & 0x400) != 0 )
            WPP_SF__KERB_NAME_(v61[2], 31, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, *((_QWORD *)v20 + 4));
        }
        KerbFreeData(74);
        KerbFreeData(76);
        v144 = 0;
        v139 = 0;
        if ( v154[1] )
        {
          if ( KerbGlobalPackageState == 1 )
            ((void (*)(void))LsaFunctions->FreeLsaHeap)();
          else
            LocalFree(v154[1]);
        }
        *(_OWORD *)v154 = 0;
        KerbTracerT::Log(11, "KerbGetServiceTicketInternal", 7684, "TGT TargetDomain %wZ\n", (char *)v20 + 64);
        KerbTracerT::Log(11, "KerbGetServiceTicketInternal", 7685, "TGT Domain %wZ\n", (char *)v20 + 48);
        if ( (v143 & 1) != 0 )
        {
          if ( !*((_WORD *)v20 + 32) )
            goto LABEL_179;
          RtlEnterCriticalSection(&stru_180144D18);
          v63 = (__int64 *)KerbMitRealmList;
          if ( (_UNKNOWN *)KerbMitRealmList == &KerbMitRealmList )
          {
LABEL_178:
            RtlLeaveCriticalSection(&stru_180144D18);
LABEL_179:
            v62 = (struct _KERB_INTERNAL_NAME *)v155;
            goto LABEL_180;
          }
          while ( !RtlEqualUnicodeString((PCUNICODE_STRING)v20 + 4, (PCUNICODE_STRING)(v63 + 5), 1u) )
          {
            v64 = 0;
            if ( *((_DWORD *)v63 + 9) )
            {
              while ( !RtlEqualUnicodeString((PCUNICODE_STRING)v20 + 4, (PCUNICODE_STRING)(v63[7] + 16LL * v64), 1u) )
              {
                if ( ++v64 >= *((_DWORD *)v63 + 9) )
                  goto LABEL_177;
              }
              break;
            }
LABEL_177:
            v63 = (__int64 *)*v63;
            if ( v63 == (__int64 *)&KerbMitRealmList )
              goto LABEL_178;
          }
          RtlLeaveCriticalSection(&stru_180144D18);
        }
LABEL_180:
        v65 = 0;
        if ( v62 == v155 )
          v65 = v151;
        v66 = KerbGetTgsTicketWithBranchEx(
                v150,
                a2,
                v163,
                v162,
                v164,
                v122,
                v20,
                v62,
                v137 & 0x180000,
                a9,
                v148,
                (struct PKERB_AUTHORIZATION_DATA_s *)v160,
                v125,
                v65,
                v126,
                v127,
                v128,
                &v144,
                &v139,
                &v143,
                (struct _UNICODE_STRING *)v154,
                &v138,
                v165);
        TgsTicketWithBranch = v66;
        if ( v66 < 0 )
        {
          if ( (v143 & 2) != 0 )
          {
            v73 = v147;
            if ( v147 > 0 )
            {
              if ( v20 )
                v74 = (const void *)WORD1(v20);
              else
                v74 = 0;
              KerbTracerT::Log(2, "KerbGetServiceTicketInternal", 7735, "Doing TGT retry 2 - %p\n", v74);
              KerbRemoveTicketCacheEntry(v20);
              KerbDereferenceTicketCacheEntry(v20);
              v23 = v155;
              v20 = 0;
              v17 = v134;
              v147 = v73 - 1;
              v27 = CriticalSection;
              v152 = 0;
              goto LABEL_3;
            }
          }
          KerbTracerT::Log(2, "KerbGetServiceTicketInternal", 7749, "Failed to get TGS ticket for service 0x%x", v66);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v80 = v135;
            WPP_SF__KERB_NAME_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids,
              v135);
            v29 = 0;
            v17 = v134;
            v30 = v130;
            goto LABEL_359;
          }
LABEL_14:
          v29 = v129;
LABEL_15:
          v17 = v134;
          v30 = v130;
          goto LABEL_358;
        }
        v60 = (struct _KERB_INTERNAL_NAME *)v135;
        if ( v62 == v135 )
        {
          v17 = v134;
        }
        else
        {
          if ( hMem[1] )
          {
            if ( KerbGlobalPackageState == 1 )
              ((void (*)(void))LsaFunctions->FreeLsaHeap)();
            else
              LocalFree(hMem[1]);
          }
          v17 = v134;
          *(_OWORD *)hMem = 0;
          TgsTicketWithBranch = KerbGetReferralNames(v139, v134, (struct _UNICODE_STRING *)hMem);
          if ( TgsTicketWithBranch < 0 )
            goto LABEL_14;
          KerbTracerT::Log(
            11,
            "KerbGetServiceTicketInternal",
            7785,
            "KerbGetReferralNames returns RealTargetRealm %wZ\n",
            hMem);
          if ( !LOWORD(hMem[0]) )
          {
            v96 = CriticalSection;
            RtlEnterCriticalSection(CriticalSection);
            if ( v149 )
            {
              if ( a2 )
                v97 = *((_QWORD *)a2 + 16);
              else
                v97 = 0;
              v98 = KerbCreateTicketCacheEntry(
                      v144,
                      v139,
                      *((struct KerbCredIsoApi **)v20 + 21),
                      v17,
                      (struct _UNICODE_STRING *)String1,
                      v138,
                      *((_DWORD *)v20 + 86),
                      (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v142 + 240),
                      0,
                      (struct _UNICODE_STRING *)v154,
                      0,
                      v97,
                      &v131);
            }
            else
            {
              if ( a2 )
                v99 = *((_QWORD *)a2 + 16);
              else
                v99 = 0;
              if ( v133 )
                v100 = (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v142 + 160);
              else
                v100 = 0;
              v94 = v151 != 0;
              v151 = (struct KERB_TGT_REPLY *)-(__int64)v151;
              v98 = KerbCreateTicketCacheEntry(
                      v144,
                      v139,
                      *((struct KerbCredIsoApi **)v20 + 21),
                      v17,
                      (struct _UNICODE_STRING *)String1,
                      v138 | (v94 ? 0x10 : 0),
                      *((_DWORD *)v20 + 86),
                      v100,
                      0,
                      (struct _UNICODE_STRING *)v154,
                      0,
                      v99,
                      &v131);
            }
            TgsTicketWithBranch = v98;
            RtlLeaveCriticalSection(v96);
            v29 = 0;
            if ( TgsTicketWithBranch >= 0 )
            {
              v101 = v131;
              v30 = v130;
              v131 = 0;
              *v153 = v101;
              goto LABEL_358;
            }
            goto LABEL_15;
          }
          KerbTracerT::Log(
            11,
            "KerbGetServiceTicketInternal",
            7845,
            "KerbGetServiceTicket updated RealTargetRealm %wZ\n",
            hMem);
        }
        v67 = CriticalSection;
        RtlEnterCriticalSection(CriticalSection);
        if ( a2 )
          v68 = *((_QWORD *)a2 + 16);
        else
          v68 = 0;
        TgsTicketWithBranch = KerbCreateTicketCacheEntry(
                                v144,
                                v139,
                                *((struct KerbCredIsoApi **)v20 + 21),
                                0,
                                0,
                                v138,
                                *((_DWORD *)v20 + 86),
                                (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v142 + 240),
                                0,
                                (struct _UNICODE_STRING *)v154,
                                0,
                                v68,
                                &v131);
        RtlLeaveCriticalSection(v67);
        if ( TgsTicketWithBranch < 0 )
          goto LABEL_14;
        if ( v21 )
          KerbDereferenceTicketCacheEntry(v21);
        v21 = v20;
        v20 = v131;
        v131 = 0;
      }
      while ( !RtlEqualUnicodeString((PCUNICODE_STRING)hMem, (PCUNICODE_STRING)v20 + 4, 1u) );
    }
    KerbFreeData(74);
    KerbFreeData(76);
    v144 = 0;
    v139 = 0;
    if ( v154[1] )
    {
      if ( KerbGlobalPackageState == 1 )
        ((void (*)(void))LsaFunctions->FreeLsaHeap)();
      else
        LocalFree(v154[1]);
    }
    v23 = v155;
    *(_OWORD *)v154 = 0;
    v143 = 0;
    v70 = KerbGetTgsTicketWithBranchEx(
            v150,
            a2,
            v163,
            v162,
            v164,
            v122,
            v20,
            (struct _KERB_INTERNAL_NAME *)v155,
            v137 & 0x180000,
            a9,
            v148,
            (struct PKERB_AUTHORIZATION_DATA_s *)v160,
            v125,
            v151,
            v126,
            v127,
            v128,
            &v144,
            &v139,
            &v143,
            (struct _UNICODE_STRING *)v154,
            &v138,
            v165);
    TgsTicketWithBranch = v70;
    if ( v70 < 0 )
    {
      if ( (v143 & 2) == 0 || (v75 = v147, v147 <= 0) )
      {
        KerbTracerT::Log(2, "KerbGetServiceTicketInternal", 7971, "Failed to get TGS ticket for service 0x%x", v70);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_14;
        WPP_SF__KERB_NAME_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids,
          v23);
        v29 = 0;
        v17 = v134;
        v30 = v130;
        goto LABEL_358;
      }
      if ( v20 )
        v76 = (const void *)WORD1(v20);
      else
        v76 = 0;
      KerbTracerT::Log(2, "KerbGetServiceTicketInternal", 7957, "Doing TGT retry - %p\n", v76);
      KerbRemoveTicketCacheEntry(v20);
      KerbDereferenceTicketCacheEntry(v20);
      v20 = 0;
      v152 = 0;
      v147 = v75 - 1;
      v27 = CriticalSection;
      goto LABEL_3;
    }
    if ( hMem[1] )
    {
      if ( KerbGlobalPackageState == 1 )
        ((void (*)(void))LsaFunctions->FreeLsaHeap)();
      else
        LocalFree(hMem[1]);
    }
    *(_OWORD *)hMem = 0;
    TgsTicketWithBranch = KerbGetReferralNames(v139, (struct _KERB_INTERNAL_NAME *)v23, (struct _UNICODE_STRING *)hMem);
    if ( TgsTicketWithBranch < 0 )
      goto LABEL_14;
    KerbTracerT::Log(
      11,
      "KerbGetServiceTicketInternal",
      7995,
      "KerbGetReferralNames returns RealTargetRealm %wZ\n",
      hMem);
    if ( !LOWORD(hMem[0]) )
    {
      v107 = CriticalSection;
      RtlEnterCriticalSection(CriticalSection);
      if ( v149 )
      {
        if ( a2 )
          v108 = *((_QWORD *)a2 + 16);
        else
          v108 = 0;
        v109 = KerbCreateTicketCacheEntry(
                 v144,
                 v139,
                 *((struct KerbCredIsoApi **)v20 + 21),
                 v17,
                 (struct _UNICODE_STRING *)String1,
                 v138,
                 *((_DWORD *)v20 + 86),
                 (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v142 + 240),
                 0,
                 (struct _UNICODE_STRING *)v154,
                 0,
                 v108,
                 &v131);
      }
      else
      {
        if ( a2 )
          v110 = *((_QWORD *)a2 + 16);
        else
          v110 = 0;
        if ( v133 )
          v111 = (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v142 + 160);
        else
          v111 = 0;
        v94 = v151 != 0;
        v151 = (struct KERB_TGT_REPLY *)-(__int64)v151;
        v109 = KerbCreateTicketCacheEntry(
                 v144,
                 v139,
                 *((struct KerbCredIsoApi **)v20 + 21),
                 v17,
                 (struct _UNICODE_STRING *)String1,
                 v138 | (v94 ? 0x10 : 0),
                 *((_DWORD *)v20 + 86),
                 v111,
                 0,
                 (struct _UNICODE_STRING *)v154,
                 0,
                 v110,
                 &v131);
      }
      TgsTicketWithBranch = v109;
      RtlLeaveCriticalSection(v107);
      v29 = 0;
      if ( TgsTicketWithBranch < 0 )
        goto LABEL_15;
      v112 = v131;
      v17 = v134;
      v30 = v130;
      v131 = 0;
      *v153 = v112;
      goto LABEL_358;
    }
    if ( v158 > KerbGlobalMaxReferralCount )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF__KERB_NAME_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids,
          v23);
      v29 = 0;
      TgsTicketWithBranch = -1073741068;
      v17 = v134;
      v30 = v130;
      goto LABEL_358;
    }
    v27 = CriticalSection;
    RtlEnterCriticalSection(CriticalSection);
    if ( a2 )
      v71 = *((_QWORD *)a2 + 16);
    else
      v71 = 0;
    TgsTicketWithBranch = KerbCreateTicketCacheEntry(
                            v144,
                            v139,
                            *((struct KerbCredIsoApi **)v20 + 21),
                            0,
                            0,
                            v138,
                            *((_DWORD *)v20 + 86),
                            (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v142 + 240),
                            0,
                            (struct _UNICODE_STRING *)v154,
                            0,
                            v71,
                            &v131);
    RtlLeaveCriticalSection(v27);
    if ( TgsTicketWithBranch < 0 )
      goto LABEL_14;
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)v20 + 4, (PCUNICODE_STRING)v131 + 4, 1u) )
    {
      v102 = v131;
      if ( *((_WORD *)v17 + 1) < 2u )
        v103 = 0;
      else
        v103 = (const struct _UNICODE_STRING *)((char *)v17 + 24);
      v104 = (struct _RTL_CRITICAL_SECTION *)((char *)v131 + 368);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v131 + 368));
      v105 = (struct _UNICODE_STRING *)((char *)v102 + 80);
      if ( v105 )
      {
        v106 = v105->Buffer;
        if ( v106 )
        {
          if ( KerbGlobalPackageState == 1 )
            ((void (*)(void))LsaFunctions->FreeLsaHeap)();
          else
            LocalFree(v106);
        }
        *v105 = 0;
      }
      KerbDuplicateStringEx(v105, v103);
      RtlLeaveCriticalSection(v104);
      KerbTracerT::Log(
        11,
        "KerbGetServiceTicketInternal",
        8056,
        "Referral has reached target domain (%wZ) (case 2)\n",
        (char *)v131 + 64);
      v87 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        v17 = v134;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          goto LABEL_279;
        v88 = 35;
        goto LABEL_277;
      }
      goto LABEL_278;
    }
    ++v158;
    if ( v21 )
      KerbDereferenceTicketCacheEntry(v21);
    v54 = 0;
    v21 = v20;
    v132 = 0;
    v20 = v131;
    v152 = v131;
    v131 = 0;
    KerbTracerT::Log(
      11,
      "KerbGetServiceTicketInternal",
      8096,
      "KerbGetServiceTicket Restart referral RealTargetRealm: %wZ\n",
      hMem);
  }
  RtlEnterCriticalSection(v27);
  if ( v149 )
  {
    if ( a2 )
      v90 = *((_QWORD *)a2 + 16);
    else
      v90 = 0;
    v91 = KerbCreateTicketCacheEntry(
            v144,
            v139,
            *((struct KerbCredIsoApi **)v20 + 21),
            v17,
            (struct _UNICODE_STRING *)String1,
            v138,
            *((_DWORD *)v20 + 86),
            (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v142 + 240),
            0,
            (struct _UNICODE_STRING *)v154,
            (struct _UNICODE_STRING *)v20 + 8,
            v90,
            &v131);
  }
  else
  {
    if ( a2 )
      v92 = *((_QWORD *)a2 + 16);
    else
      v92 = 0;
    if ( v133 )
      v93 = (struct _KERB_PRIMARY_CREDENTIAL *)((char *)v142 + 160);
    else
      v93 = 0;
    v94 = v151 != 0;
    v151 = (struct KERB_TGT_REPLY *)-(__int64)v151;
    v91 = KerbCreateTicketCacheEntry(
            v144,
            v139,
            *((struct KerbCredIsoApi **)v20 + 21),
            v17,
            (struct _UNICODE_STRING *)String1,
            v138 | (v94 ? 0x10 : 0),
            *((_DWORD *)v20 + 86),
            v93,
            0,
            (struct _UNICODE_STRING *)v154,
            (struct _UNICODE_STRING *)v20 + 8,
            v92,
            &v131);
  }
  TgsTicketWithBranch = v91;
  RtlLeaveCriticalSection(v27);
  v29 = 0;
  if ( TgsTicketWithBranch < 0 )
    goto LABEL_15;
  v95 = v131;
  v17 = v134;
  v30 = v130;
  v131 = 0;
  *v153 = v95;
LABEL_358:
  v80 = v135;
LABEL_359:
  v79 = v153;
  if ( v153 )
  {
LABEL_360:
    v113 = *v79;
    if ( !*v79 )
      goto LABEL_361;
LABEL_362:
    KerbTelemetry::KerbEncryptionKeyEtype(
      *((unsigned int *)v113 + 55),
      *((unsigned int *)v113 + 54),
      3,
      (unsigned int)TgsTicketWithBranch);
  }
  else
  {
LABEL_361:
    v113 = v131;
    if ( v131 )
      goto LABEL_362;
  }
  if ( TgsTicketWithBranch >= 0 )
  {
    v26 = v139;
    v114 = v142;
    if ( v139 && v142 )
    {
      if ( (int)LsaIGetLogonGuid(v142, (char *)v142 + 16, (char *)v139 + 94, 14, &v175) >= 0 )
      {
        if ( v173 )
          *v173 = v175;
      }
      else
      {
        v175 = 0;
      }
      v114 = v142;
    }
    if ( v30 )
      KerbGenerateAuditForLogonUsingExplicitCreds(v150, v114, &v175, v17);
  }
  if ( *(_WORD *)v17 == 2
    && ((int)(TgsTicketWithBranch + 0x80000000) < 0 || TgsTicketWithBranch == -1073741429)
    && !v141 )
  {
    v115 = 0;
    if ( TgsTicketWithBranch >= 0 )
      v115 = (struct _UNICODE_STRING *)((char *)*v153 + 64);
    v116 = v142;
    if ( v136 )
      KerbUpdateSpnCacheEntry(v17, v142, (TgsTicketWithBranch >> 31) + 2, v115);
    if ( TgsTicketWithBranch == -1073741429 )
    {
      v171 = 0;
      v170 = 0;
      if ( ((unsigned __int8 (__fastcall *)(__int128 *, __int64, struct KERB_ENCRYPTED_KDC_REPLY *, struct _UNICODE_STRING *))LsaFunctions->GetCallInfo)(
             &v170,
             v24,
             v26,
             v115) )
      {
        v124.LowPart = *((_DWORD *)v150 + 16);
        LODWORD(v123) = *((_DWORD *)v150 + 17);
        LODWORD(v121) = v170;
        KerbTracerT::Log(
          2,
          "KerbGetServiceTicketInternal",
          8243,
          "KerbGetServiceTicket by process %d, TARGET_UNKNOWN for %wZ\\%wZ LogonId %#x:%#x\n",
          v121,
          (char *)v116 + 16,
          v116,
          v123,
          v124.QuadPart);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF__KERB_NAME_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids,
            v17);
      }
    }
  }
  if ( v144 )
    KerbFreeData(74);
  if ( v139 )
    KerbFreeData(76);
  if ( v154[1] )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(v154[1]);
  }
  *(_OWORD *)v154 = 0;
  if ( v80 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (__fastcall *)(HLOCAL))LsaFunctions->FreeLsaHeap)(v80);
    else
      LocalFree(v80);
  }
  if ( hMem[1] )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(hMem[1]);
  }
  *(_OWORD *)hMem = 0;
  if ( v159[1] )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(v159[1]);
  }
  if ( v155 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(v155);
  }
  if ( v29 )
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v150 + 2);
  if ( hMem[1] )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(hMem[1]);
  }
  *(_OWORD *)hMem = 0;
  if ( v20 )
  {
    if ( TgsTicketWithBranch == -1073741718 )
      KerbRemoveTicketCacheEntry(v20);
    KerbDereferenceTicketCacheEntry(v20);
  }
  if ( v21 )
    KerbDereferenceTicketCacheEntry(v21);
  if ( v131 )
  {
    KerbRemoveTicketCacheEntry(v131);
    KerbDereferenceTicketCacheEntry(v131);
  }
  if ( !v174 )
  {
    v117 = v160;
    if ( v160 )
    {
      do
      {
        v118 = (void *)v117[3];
        v119 = (_QWORD *)*v117;
        if ( v118 )
        {
          if ( KerbGlobalPackageState == 1 )
            ((void (*)(void))LsaFunctions->FreeLsaHeap)();
          else
            LocalFree(v118);
          v117 = v169;
        }
        if ( KerbGlobalPackageState == 1 )
          ((void (__fastcall *)(_QWORD *))LsaFunctions->FreeLsaHeap)(v117);
        else
          LocalFree(v117);
        v117 = v119;
        v169 = v119;
      }
      while ( v119 );
    }
  }
  if ( v166.QuadPart )
    KerbDereferenceTicketCacheEntry((struct _KERB_TICKET_CACHE_ENTRY *)v166.QuadPart);
  return (unsigned int)TgsTicketWithBranch;
}

```

## disassembly

```asm
0x18003eb80  push    rbp
0x18003eb82  push    rbx
0x18003eb83  push    rsi
0x18003eb84  push    rdi
0x18003eb85  push    r12
0x18003eb87  push    r13
0x18003eb89  push    r14
0x18003eb8b  push    r15
0x18003eb8d  lea     rbp, [rsp-158h]
0x18003eb95  sub     rsp, 298h
0x18003eb9c  mov     rax, cs:__security_cookie
0x18003eba3  xor     rax, rsp
0x18003eba6  mov     [rbp+190h+var_50], rax
0x18003ebad  mov     rax, [rbp+190h+arg_20]
0x18003ebb4  mov     rdi, rcx
0x18003ebb7  mov     rsi, [rbp+190h+arg_28]
0x18003ebbe  mov     rbx, r8
0x18003ebc1  mov     [rbp+190h+var_110], rax
0x18003ebc8  xorps   xmm0, xmm0
0x18003ebcb  mov     rax, [rbp+190h+arg_30]
0x18003ebd2  xorps   xmm1, xmm1
0x18003ebd5  mov     [rbp+190h+String1], rax
0x18003ebd9  mov     r12, rdx
0x18003ebdc  mov     eax, [rbp+190h+arg_48]
0x18003ebe2  mov     [rbp+190h+var_194], eax
0x18003ebe5  mov     rax, [rbp+190h+arg_60]
0x18003ebec  mov     [rbp+190h+var_180], rax
0x18003ebf0  mov     rax, [rbp+190h+arg_68]
0x18003ebf7  mov     [rbp+190h+var_170], rax
0x18003ebfb  mov     rax, [rbp+190h+arg_78]
0x18003ec02  mov     [rbp+190h+var_188], rcx
0x18003ec06  mov     rcx, [rbp+190h+arg_58]
0x18003ec0d  mov     [rbp+190h+var_108], rax
0x18003ec14  mov     eax, cs:?KerbGlobalMaxReferralCount@@3KA; ulong KerbGlobalMaxReferralCount
0x18003ec1a  mov     [rbp+190h+var_C0], rcx
0x18003ec21  mov     [rbp+190h+var_130], rcx
0x18003ec25  mov     rcx, [rbp+190h+arg_70]
0x18003ec2c  mov     [rbp+190h+var_198], eax
0x18003ec2f  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18003ec36  mov     [rbp+190h+var_C8], rcx
0x18003ec3d  xor     ecx, ecx
0x18003ec3f  mov     [rbp+190h+var_208], rcx
0x18003ec43  mov     r15d, ecx
0x18003ec46  mov     [rbp+190h+var_178], rcx
0x18003ec4a  mov     r13d, ecx
0x18003ec4d  mov     rax, [rax+1B0h]
0x18003ec54  mov     r14d, ecx
0x18003ec57  mov     qword ptr [rbp+190h+var_100], rcx
0x18003ec5e  mov     [rbp+190h+var_1B8], rcx
0x18003ec62  mov     [rbp+190h+var_1D8], rcx
0x18003ec66  mov     [rbp+190h+var_200], cl
0x18003ec69  mov     [rbp+190h+var_158], rcx
0x18003ec6d  mov     [rbp+190h+hMem], rcx
0x18003ec71  mov     [rbp+190h+hMem+8], rcx
0x18003ec75  mov     [rbp+190h+var_1F0], rcx
0x18003ec79  mov     [rbp+190h+var_140], rcx
0x18003ec7d  mov     [rbp+190h+var_140+8], rcx
0x18003ec81  mov     [rbp+190h+var_144], ecx
0x18003ec84  mov     [rbp+190h+var_1C0], ecx
0x18003ec87  mov     [rbp+190h+var_1D0], cl
0x18003ec8a  mov     [rbp+190h+var_1CF], cl
0x18003ec8d  mov     [rbp+190h+var_1E0], ecx
0x18003ec90  mov     [rbp+190h+var_148], ecx
0x18003ec93  lea     rcx, [rbp+190h+var_148]
0x18003ec97  mov     [rbp+190h+var_120], r9
0x18003ec9b  mov     [rbp+190h+var_118], rbx
0x18003ec9f  mov     [rbp+190h+var_1F8], rsi
0x18003eca3  mov     [rbp+190h+var_1FF], 1
0x18003eca7  movups  xmmword ptr [rbp+190h+var_B8.Data1], xmm0
0x18003ecae  mov     [rbp+190h+var_1E8], 1
0x18003ecb2  movups  xmmword ptr [rbp+190h+var_168], xmm1
0x18003ecb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecbb  mov     eax, [rbp+190h+arg_38]
0x18003ecc1  lea     r8, [rbp+190h+var_130]; struct PKERB_AUTHORIZATION_DATA_s **
0x18003ecc5  mov     [rbp+190h+var_1E4], eax
0x18003ecc8  mov     rdx, rbx; struct _KERB_CREDMAN_CRED *
0x18003eccb  and     eax, 80000h
0x18003ecd0  mov     rcx, r12; struct _KERB_CREDENTIAL *
0x18003ecd3  mov     [rbp+190h+var_190], eax
0x18003ecd6  call    ?KerbAddAuthzDataForTGS@@YAJPEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAPEAUPKERB_AUTHORIZATION_DATA_s@@@Z; KerbAddAuthzDataForTGS(_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,PKERB_AUTHORIZATION_DATA_s * *)
0x18003ecdb  mov     ebx, eax
0x18003ecdd  mov     rax, [rbp+190h+var_130]
0x18003ece1  mov     [rbp+190h+var_F0], rax
0x18003ece8  test    ebx, ebx
0x18003ecea  js      loc_180040BA2
0x18003ecf0  add     rdi, 50h ; 'P'
0x18003ecf4  mov     [rbp+190h+CriticalSection], rdi
0x18003ecf8  nop     dword ptr [rax+rax+00000000h]
0x18003ed00  mov     rdx, [rbp+190h+var_1B8]
0x18003ed04  mov     ecx, 4Ah ; 'J'
0x18003ed09  call    KerbFreeData
0x18003ed0e  mov     rdx, [rbp+190h+var_1D8]
0x18003ed12  mov     ecx, 4Ch ; 'L'
0x18003ed17  call    KerbFreeData
0x18003ed1c  xor     eax, eax
0x18003ed1e  mov     rcx, rdi; CriticalSection
0x18003ed21  mov     [rbp+190h+var_1B8], rax
0x18003ed25  mov     [rbp+190h+var_1D8], rax
0x18003ed29  call    cs:__imp_RtlEnterCriticalSection
0x18003ed2f  mov     rax, [rbp+190h+var_120]
0x18003ed33  mov     [rbp+190h+var_210], 1
0x18003ed37  test    rax, rax
0x18003ed3a  jz      short loc_18003ED4D
0x18003ed3c  mov     rax, [rax+40h]
0x18003ed40  mov     [rbp+190h+var_1C8], rax
0x18003ed44  mov     byte ptr [rbp+190h+var_20C], 1
0x18003ed48  jmp     loc_18003EE0E
0x18003ed4d  test    r12, r12
0x18003ed50  jz      short loc_18003ED69
0x18003ed52  mov     rax, [r12+48h]
0x18003ed57  mov     [rbp+190h+var_1C8], rax
0x18003ed5b  test    rax, rax
0x18003ed5e  jz      short loc_18003ED69
0x18003ed60  mov     byte ptr [rbp+190h+var_20C], 1
0x18003ed64  jmp     loc_18003EE0E
0x18003ed69  mov     rax, [rbp+190h+var_118]
0x18003ed6d  test    rax, rax
0x18003ed70  jz      short loc_18003EDD7
0x18003ed72  mov     rax, [rax+40h]
0x18003ed76  mov     [rbp+190h+var_1C8], rax
0x18003ed7a  mov     byte ptr [rbp+190h+var_20C], 1
0x18003ed7e  test    r12, r12
0x18003ed81  jz      short loc_18003ED8B
0x18003ed83  test    byte ptr [r12+40h], 10h
0x18003ed89  jnz     short loc_18003ED91
0x18003ed8b  test    byte ptr [rbp+190h+var_148], 4
0x18003ed8f  jz      short loc_18003EE0E
0x18003ed91  mov     rcx, [rbp+190h+var_188]
0x18003ed95  lea     r9, aKerbgetservice_10; "KerbGetServiceTicketInternal credman au"...
0x18003ed9c  mov     r8d, 1B08h
0x18003eda2  lea     rdx, aKerbgetservice_13; "KerbGetServiceTicketInternal"
0x18003eda9  mov     eax, [rcx+40h]
0x18003edac  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x18003edb0  mov     eax, [rcx+44h]
0x18003edb3  mov     ecx, 1
0x18003edb8  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x18003edbc  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003edc1  mov     ebx, 8009030Eh
0x18003edc6  movzx   edi, [rbp+190h+var_210]
0x18003edca  mov     rsi, [rbp+190h+var_1F8]
0x18003edce  mov     r12d, [rbp+190h+var_20C]
0x18003edd2  jmp     loc_180040BAC
0x18003edd7  mov     rcx, [rbp+190h+var_188]
0x18003eddb  mov     edi, [rcx+388h]
0x18003ede1  lea     rax, [rcx+78h]
0x18003ede5  shr     edi, 11h
0x18003ede8  and     dil, 1
0x18003edec  mov     [rbp+190h+var_1C8], rax
0x18003edf0  mov     [rbp+190h+var_20C], edi
0x18003edf3  test    r12, r12
0x18003edf6  jz      short loc_18003EE04
0x18003edf8  test    byte ptr [r12+40h], 10h
0x18003edfe  jnz     loc_180040B6E
0x18003ee04  test    byte ptr [rbp+190h+var_148], 4
0x18003ee08  jnz     loc_180040B6E
0x18003ee0e  cmp     word ptr [rsi+2], 0
0x18003ee13  jz      loc_180040B3D
0x18003ee19  cmp     word ptr [rsi+8], 0
0x18003ee1e  jz      loc_180040B3D
0x18003ee24  cmp     [rbp+190h+var_190], 0
0x18003ee28  jz      short loc_18003EE49
0x18003ee2a  lea     rcx, [rax+0F0h]; struct _KERB_TICKET_CACHE *
0x18003ee31  xor     r9d, r9d; unsigned int
0x18003ee34  mov     r8, [rbp+190h+String1]; struct _UNICODE_STRING *
0x18003ee38  mov     rdx, rsi; struct _KERB_INTERNAL_NAME *
0x18003ee3b  call    ?KerbLocateTicketCacheEntryEx@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryEx(_KERB_TICKET_CACHE *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,ulong)
0x18003ee40  mov     rdi, rax
0x18003ee43  mov     [rbp+190h+var_208], rax
0x18003ee47  jmp     short loc_18003EE67
0x18003ee49  cmp     [rbp+190h+var_180], 0
0x18003ee4e  jnz     short loc_18003EE63
0x18003ee50  test    byte ptr [rbp+190h+var_1E4], 1
0x18003ee54  jnz     short loc_18003EE63
0x18003ee56  mov     r9d, [rbp+190h+var_194]
0x18003ee5a  lea     rcx, [rax+0A0h]
0x18003ee61  jmp     short loc_18003EE34
0x18003ee63  mov     rdi, [rbp+190h+var_208]
0x18003ee67  test    rdi, rdi
0x18003ee6a  jz      loc_18003EFAD
0x18003ee70  mov     rax, [rbp+190h+arg_50]
0x18003ee77  test    rax, rax
0x18003ee7a  jz      short loc_18003EE93
0x18003ee7c  cmp     dword ptr [rax+34h], 29h ; ')'
0x18003ee80  jnz     short loc_18003EE93
0x18003ee82  mov     rcx, rdi; struct _KERB_TICKET_CACHE_ENTRY *
0x18003ee85  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18003ee8a  mov     rcx, [rbp+190h+var_208]
0x18003ee8e  jmp     loc_18003EFA0
0x18003ee93  mov     r8d, [rbp+190h+arg_40]
0x18003ee9a  mov     ecx, r8d
0x18003ee9d  mov     eax, [rdi+0A0h]
0x18003eea3  and     ecx, 40000000h
0x18003eea9  mov     edx, ecx
0x18003eeab  bts     edx, 1Dh
0x18003eeaf  bt      r8d, 1Dh
0x18003eeb4  cmovnb  edx, ecx
0x18003eeb7  mov     ecx, edx
0x18003eeb9  bts     ecx, 1Ch
0x18003eebd  bt      r8d, 1Ch
0x18003eec2  cmovnb  ecx, edx
0x18003eec5  mov     edx, ecx
0x18003eec7  bts     edx, 1Bh
0x18003eecb  bt      r8d, 1Bh
0x18003eed0  cmovnb  edx, ecx
0x18003eed3  mov     ecx, edx
0x18003eed5  bts     ecx, 19h
0x18003eed9  bt      r8d, 19h
0x18003eede  cmovnb  ecx, edx
0x18003eee1  mov     edx, ecx
0x18003eee3  bts     edx, 1Ah
0x18003eee7  bt      r8d, 1Ah
0x18003eeec  cmovnb  edx, ecx
0x18003eeef  mov     ecx, edx
0x18003eef1  bts     ecx, 17h
0x18003eef5  bt      r8d, 17h
0x18003eefa  cmovnb  ecx, edx
0x18003eefd  and     eax, ecx
0x18003eeff  cmp     eax, ecx
0x18003ef01  jnz     loc_18003EF9D
0x18003ef07  mov     eax, [rbp+190h+var_194]
0x18003ef0a  test    eax, eax
0x18003ef0c  jz      short loc_18003EF1A
0x18003ef0e  cmp     [rdi+134h], eax
0x18003ef14  jnz     loc_18003EF9D
0x18003ef1a  mov     eax, [rbp+190h+var_1E4]
0x18003ef1d  bt      eax, 12h
0x18003ef21  jnb     short loc_18003EF2F
0x18003ef23  mov     rsi, 23C345DC3CBA00h
0x18003ef2d  jmp     short loc_18003EF53
0x18003ef2f  test    al, 4
0x18003ef31  jz      short loc_18003EF4C
0x18003ef33  mov     eax, 88888889h
0x18003ef38  mul     cs:?KerbGlobalTgtRenewalTime@@3KA; ulong KerbGlobalTgtRenewalTime
0x18003ef3e  shr     edx, 5
0x18003ef41  mov     eax, edx
0x18003ef43  imul    rsi, rax, 23C34600h
0x18003ef4a  jmp     short loc_18003EF53
0x18003ef4c  mov     rsi, qword ptr cs:?KerbGlobalSkewTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalSkewTime ...
0x18003ef53  lea     rcx, [rbp+190h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003ef57  mov     qword ptr [rbp+190h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003ef5f  call    cs:__imp_GetSystemTimeAsFileTime
0x18003ef65  movsxd  rax, dword ptr [rdi+158h]
0x18003ef6c  imul    rcx, rax, 989680h
0x18003ef73  mov     rax, qword ptr [rbp+190h+SystemTimeAsFileTime.dwLowDateTime]
0x18003ef77  add     rcx, rsi
0x18003ef7a  add     rax, rcx
0x18003ef7d  mov     qword ptr [rbp+190h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003ef81  cmp     [rdi+100h], rax
0x18003ef88  jge     loc_18004021C
0x18003ef8e  mov     rcx, [rbp+190h+var_208]; struct _KERB_TICKET_CACHE_ENTRY *
0x18003ef92  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18003ef97  mov     rsi, [rbp+190h+var_1F8]
0x18003ef9b  jmp     short loc_18003EFA5
0x18003ef9d  mov     rcx, rdi; struct _KERB_TICKET_CACHE_ENTRY *
0x18003efa0  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18003efa5  mov     [rbp+190h+var_208], 0
0x18003efad  cmp     [rbp+190h+arg_40], 0
0x18003efb4  jnz     short loc_18003EFBC
0x18003efb6  cmp     [rbp+190h+var_194], 0
0x18003efba  jz      short loc_18003EFC7
0x18003efbc  mov     edi, [rbp+190h+var_1E4]
0x18003efbf  test    dil, 20h
0x18003efc3  jz      short loc_18003EFE2
0x18003efc5  jmp     short loc_18003EFCA
0x18003efc7  mov     edi, [rbp+190h+var_1E4]
0x18003efca  test    dil, 1
0x18003efce  jnz     short loc_18003EFE2
0x18003efd0  cmp     [rbp+190h+var_180], 0
0x18003efd5  jnz     short loc_18003EFE2
0x18003efd7  test    r12, r12
0x18003efda  jnz     short loc_18003EFE6
0x18003efdc  cmp     [rbp+190h+var_190], r12d
0x18003efe0  jnz     short loc_18003EFE6
0x18003efe2  mov     [rbp+190h+var_1FF], 0
0x18003efe6  mov     rbx, [rbp+190h+String1]
0x18003efea  bt      edi, 19h
0x18003efee  jnb     loc_18003F243
0x18003eff4  cmp     qword ptr [rbx+8], 0
0x18003eff9  jnz     loc_18003F243
0x18003efff  mov     rdx, [rbp+190h+var_1C8]; struct _KERB_PRIMARY_CREDENTIAL *
0x18003f003  lea     r8, [rbp+190h+var_140]; struct _UNICODE_STRING *
0x18003f007  mov     rcx, rsi; struct _KERB_INTERNAL_NAME *
0x18003f00a  call    ?KerbGetSpnCacheStatus@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_KERB_PRIMARY_CREDENTIAL@@PEAU_UNICODE_STRING@@@Z; KerbGetSpnCacheStatus(_KERB_INTERNAL_NAME *,_KERB_PRIMARY_CREDENTIAL *,_UNICODE_STRING *)
0x18003f00f  mov     ebx, eax
0x18003f011  test    eax, eax
0x18003f013  js      loc_18003F0B8
0x18003f019  mov     rcx, [rbp+190h+hMem+8]; hMem
0x18003f01d  test    rcx, rcx
0x18003f020  jz      short loc_18003F043
0x18003f022  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18003f029  jnz     short loc_18003F03D
0x18003f02b  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18003f032  mov     rax, [rax+30h]
0x18003f036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f03b  jmp     short loc_18003F043
0x18003f03d  call    cs:__imp_LocalFree
0x18003f043  movaps  xmm0, xmmword ptr [rbp+190h+var_140]
0x18003f047  lea     rax, [rbp+190h+hMem]
0x18003f04b  xor     ecx, ecx
0x18003f04d  movdqa  xmmword ptr [rbp+190h+hMem], xmm0
  ... truncated ...
```
