# SpInitLsaModeContext_Old(unsigned __int64,unsigned __int64,_UNICODE_STRING *,ulong,ulong,_SecBufferDesc *,unsigned __int64 *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x180021574`
- end: `0x180023ff7`
- name: `?SpInitLsaModeContext_Old@@YAJ_K0PEAU_UNICODE_STRING@@KKPEAU_SecBufferDesc@@PEA_K2PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `10883`
- prototype: `__int64 __fastcall(struct _KERB_CREDENTIAL *, struct _KERBEROS_LIST_ENTRY *, struct _UNICODE_STRING *, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned __int64 *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `1`
- callee_count: `62`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180021300`

## callees

- `0x1800063e8`
- `0x180006680`
- `0x1800068d0`
- `0x180006920`
- `0x1800069a0`
- `0x1800069e0`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x180010b64`
- `0x180010e90`
- `0x1800113f0`
- `0x180016550`
- `0x180016600`
- `0x180021574`
- `0x180024de0`
- `0x1800290c0`
- `0x180029360`
- `0x18002bd40`
- `0x18002f8b0`
- `0x18002ffa8`
- `0x180034060`
- `0x18003af1c`
- `0x18003dfc0`
- `0x180042470`
- `0x180045970`
- `0x180045cd0`
- `0x180046970`
- `0x180046e70`
- `0x1800484f8`
- `0x180048690`
- `0x180050078`
- `0x1800501e0`
- `0x180050bd0`
- `0x1800548b4`
- `0x1800566a8`
- `0x18005de50`
- `0x18005e550`
- `0x1800621d0`
- `0x180062d28`
- `0x18006557c`
- `0x18006ba94`
- `0x18006d608`
- `0x18006e98c`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x180085c20`
- `0x180087070`
- `0x180088424`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002390a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002390a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023e53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023e53`
- `ntdll!RtlSystemTimeToLocalTime` at `0x180022af8`
- `ntdll!RtlSystemTimeToLocalTime` at `0x180023a0f`
- `ntdll!RtlSystemTimeToLocalTime` at `0x180022af8`
- `ntdll!RtlSystemTimeToLocalTime` at `0x180023a0f`
- `ntdll!EtwLogTraceEvent` at `0x18002178a`
- `ntdll!EtwLogTraceEvent` at `0x180023c69`
- `ntdll!EtwLogTraceEvent` at `0x18002178a`
- `ntdll!EtwLogTraceEvent` at `0x180023c69`
- `ntdll!RtlInitUnicodeString` at `0x180023ae6`
- `ntdll!RtlInitUnicodeString` at `0x180023b0d`
- `ntdll!RtlInitUnicodeString` at `0x180023b33`
- `ntdll!RtlInitUnicodeString` at `0x180023b53`
- `ntdll!RtlInitUnicodeString` at `0x180023b6a`
- `ntdll!RtlInitUnicodeString` at `0x180023ae6`
- `ntdll!RtlInitUnicodeString` at `0x180023b0d`
- `ntdll!RtlInitUnicodeString` at `0x180023b33`
- `ntdll!RtlInitUnicodeString` at `0x180023b53`
- `ntdll!RtlInitUnicodeString` at `0x180023b6a`
- `ntdll!RtlReleaseResource` at `0x180021cb6`
- `ntdll!RtlReleaseResource` at `0x180021cfb`
- `ntdll!RtlReleaseResource` at `0x180021d79`
- `ntdll!RtlReleaseResource` at `0x1800221c2`
- `ntdll!RtlReleaseResource` at `0x1800222b0`
- `ntdll!RtlReleaseResource` at `0x18002237b`
- `ntdll!RtlReleaseResource` at `0x1800225b5`
- `ntdll!RtlReleaseResource` at `0x1800228e1`
- `ntdll!RtlReleaseResource` at `0x180022b0f`
- `ntdll!RtlReleaseResource` at `0x1800232bf`
- `ntdll!RtlReleaseResource` at `0x1800239a8`
- `ntdll!RtlReleaseResource` at `0x1800239ea`
- `ntdll!RtlReleaseResource` at `0x180023d28`
- `ntdll!RtlReleaseResource` at `0x180021cb6`
- `ntdll!RtlReleaseResource` at `0x180021cfb`
- `ntdll!RtlReleaseResource` at `0x180021d79`
- `ntdll!RtlReleaseResource` at `0x1800221c2`
- `ntdll!RtlReleaseResource` at `0x1800222b0`
- `ntdll!RtlReleaseResource` at `0x18002237b`
- `ntdll!RtlReleaseResource` at `0x1800225b5`
- `ntdll!RtlReleaseResource` at `0x1800228e1`
- `ntdll!RtlReleaseResource` at `0x180022b0f`
- `ntdll!RtlReleaseResource` at `0x1800232bf`
- `ntdll!RtlReleaseResource` at `0x1800239a8`
- `ntdll!RtlReleaseResource` at `0x1800239ea`
- `ntdll!RtlReleaseResource` at `0x180023d28`
- `ntdll!RtlAcquireResourceShared` at `0x180021c4a`
- `ntdll!RtlAcquireResourceShared` at `0x18002289e`
- `ntdll!RtlAcquireResourceShared` at `0x180022ade`
- `ntdll!RtlAcquireResourceShared` at `0x180023281`
- `ntdll!RtlAcquireResourceShared` at `0x180021c4a`
- `ntdll!RtlAcquireResourceShared` at `0x18002289e`
- `ntdll!RtlAcquireResourceShared` at `0x180022ade`
- `ntdll!RtlAcquireResourceShared` at `0x180023281`
- `ntdll!RtlAcquireResourceExclusive` at `0x180021d40`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800221b2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022295`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002235c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022598`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002396b`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800239c0`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023cac`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023ccc`
- `ntdll!RtlAcquireResourceExclusive` at `0x180021d40`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800221b2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022295`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002235c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022598`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002396b`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800239c0`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023cac`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023ccc`
- `ntdll!RtlEnterCriticalSection` at `0x180022856`
- `ntdll!RtlEnterCriticalSection` at `0x180022b94`
- `ntdll!RtlEnterCriticalSection` at `0x180022e02`
- `ntdll!RtlEnterCriticalSection` at `0x180022856`
- `ntdll!RtlEnterCriticalSection` at `0x180022b94`
- `ntdll!RtlEnterCriticalSection` at `0x180022e02`
- `ntdll!RtlLeaveCriticalSection` at `0x18002288e`
- `ntdll!RtlLeaveCriticalSection` at `0x180022ba3`
- `ntdll!RtlLeaveCriticalSection` at `0x180022e41`
- `ntdll!RtlLeaveCriticalSection` at `0x18002288e`
- `ntdll!RtlLeaveCriticalSection` at `0x180022ba3`
- `ntdll!RtlLeaveCriticalSection` at `0x180022e41`

## string_xrefs

- `0x18002264f`: `Output token is too small - sent in %d, needed %d`
- `0x180022a58`: `Output token is too small - sent in %d, needed %d`
- `0x18002378c`: `Output token is too small - sent in %d, needed %d`
- `0x18002188e`: `Failed to map output token: 0x%x`
- `0x180021944`: `Failed to map Input token: 0x%x`
- `0x1800219b6`: `Failed to map Mechlist token: 0x%x`
- `0x180021b15`: `Failed to map incoming SECBUFFER_TARGET_HOST. %x`
- `0x180021bd0`: `SpInitLsaModeContext trying to complete a context with no input token!`
- `0x180021e37`: `onecore\ds\security\protocols\kerberos\client2\ctxtapi.cxx`
- `0x180022078`: `onecore\ds\security\protocols\kerberos\client2\ctxtapi.cxx`
- `0x180022772`: `onecore\ds\security\protocols\kerberos\client2\ctxtapi.cxx`
- `0x180022603`: `Output token missing`
- `0x180022919`: `Output token missing.`
- `0x180022979`: `SpInitLsaModeContext does NOT have service ticket\n`
- `0x180022cf2`: `Trying to use local service credentials for outbound authentication\n`
- `0x180023377`: `SpInitLsaModeContext getting service ticket for S4UProxy\n`
- `0x1800233f0`: `SpInitLsaModeContext getting service ticket\n`
- `0x18002349a`: `SpInitLsaModeContext failed to get serviceticket: STATUS_USER2USER_REQUIRED\n`
- `0x1800234f9`: `SpInitLsaModeContext failed to get outbound ticket, KerbGetServiceTicket %s failed with 0x%x\n`
- `0x1800235be`: `Trying to initialize a context with no output token!`
- `0x1800238d4`: `Failed to create client context: 0x%x`
- `0x180023946`: `Failed to create session key entry: 0x%x`

## pseudocode

```c
__int64 __fastcall SpInitLsaModeContext_Old(
        struct _KERB_CREDENTIAL *a1,
        struct _KERBEROS_LIST_ENTRY *a2,
        struct _UNICODE_STRING *a3,
        unsigned int a4,
        unsigned int a5,
        struct _SecBufferDesc *a6,
        unsigned __int64 *a7,
        struct _SecBufferDesc *a8,
        unsigned int *a9,
        union _LARGE_INTEGER *a10,
        unsigned __int8 *a11,
        struct _SecBuffer *a12)
{
  unsigned int v12; // r14d
  struct _FILETIME v14; // rsi
  unsigned int v15; // r13d
  unsigned int v16; // ebx
  struct KERB_ERROR_METHOD_DATA *v17; // rdi
  const void *v18; // rcx
  struct _SecBuffer *v19; // r15
  struct _SecBuffer *v20; // r12
  struct _SecBuffer *v21; // r15
  int v22; // ecx
  PSecBuffer pBuffers; // rdx
  struct _SecBuffer *v24; // r8
  int v25; // ecx
  const char *v26; // r9
  __int64 v27; // r8
  int v28; // r15d
  struct _SecBuffer *v29; // rdi
  struct _SecBufferDesc *v30; // r10
  int v31; // edx
  PSecBuffer v32; // r9
  struct _SecBuffer *v33; // r8
  int v34; // edx
  PSecBuffer v35; // r9
  struct _SecBuffer *v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  __int64 v39; // rcx
  unsigned int v40; // ecx
  PSecBuffer v41; // rdx
  __int64 v42; // rbx
  struct _SecBuffer *v43; // r8
  __int64 v44; // rcx
  struct _KERBEROS_LIST_ENTRY *v45; // rbx
  int updated; // eax
  PSecBuffer v47; // rdx
  unsigned __int64 cbBuffer; // r8
  unsigned __int8 v49; // r8
  int v50; // eax
  int v51; // eax
  int v52; // eax
  struct _KERB_CREDENTIAL *v53; // r9
  unsigned int v54; // ecx
  int v55; // ebx
  int v56; // eax
  struct _KERB_CREDENTIAL *v57; // r9
  unsigned int v58; // ecx
  int v59; // ebx
  int v60; // eax
  unsigned int v61; // edx
  struct _SecBuffer *v62; // rbx
  unsigned int *v63; // r15
  struct _KERB_CREDENTIAL *v64; // r9
  unsigned int v65; // edi
  int v66; // eax
  char v67; // r12
  struct _RTL_CRITICAL_SECTION *v68; // rax
  struct _RTL_CRITICAL_SECTION *v69; // rbx
  struct _SecBuffer *v70; // rdi
  int v71; // eax
  unsigned int v72; // edx
  size_t v73; // rbx
  struct _RTL_CRITICAL_SECTION *v74; // rax
  struct _RTL_CRITICAL_SECTION *v75; // rbx
  struct _RTL_CRITICAL_SECTION *v76; // r14
  int LockSemaphore; // edi
  DWORD LowPart; // ebx
  struct _KERB_INTERNAL_NAME *v79; // rdx
  unsigned int v80; // ecx
  unsigned int v81; // r14d
  const char *v82; // r9
  __int64 v83; // r8
  char v84; // di
  int v85; // eax
  unsigned int v86; // eax
  int v87; // edx
  struct _KERB_TICKET_CACHE_ENTRY *v88; // r15
  int ServiceTicketByS4UProxy; // eax
  int v90; // ecx
  const char *v91; // rax
  struct _SecBuffer *v92; // r15
  unsigned int v93; // edx
  size_t v94; // rdi
  struct _KERB_LOGON_SESSION *v95; // rcx
  unsigned __int8 *v96; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v97; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v98; // rcx
  unsigned int v99; // eax
  struct _KERB_LOGON_SESSION **v100; // rbx
  struct _KERB_LOGON_SESSION **v101; // rcx
  struct _KERB_LOGON_SESSION **v102; // rdx
  struct _KERB_LOGON_SESSION *v103; // r14
  int v104; // eax
  int v105; // ebx
  struct _KERB_LOGON_SESSION *v106; // rbx
  int v107; // eax
  unsigned __int64 v108; // rbx
  struct _KERB_CREDENTIAL *v109; // rcx
  const void *v110; // rcx
  unsigned int v111; // ebx
  struct _UNICODE_STRING *v113; // [rsp+20h] [rbp-E0h]
  int v114; // [rsp+20h] [rbp-E0h]
  int ChannelBindings; // [rsp+80h] [rbp-80h] BYREF
  char v116; // [rsp+84h] [rbp-7Ch] BYREF
  struct _SecBuffer *v117; // [rsp+88h] [rbp-78h]
  unsigned int v118; // [rsp+90h] [rbp-70h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v119; // [rsp+98h] [rbp-68h] BYREF
  struct KERB_ERROR *v120; // [rsp+A0h] [rbp-60h] BYREF
  char v121; // [rsp+A8h] [rbp-58h]
  struct _KERB_CREDENTIAL *v122; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v123; // [rsp+B8h] [rbp-48h]
  struct _KERB_INTERNAL_NAME *v124; // [rsp+C0h] [rbp-40h] BYREF
  size_t v125; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v126; // [rsp+D0h] [rbp-30h] BYREF
  struct _KERB_LOGON_SESSION *v127; // [rsp+D8h] [rbp-28h]
  struct _LUID v128; // [rsp+E0h] [rbp-20h] BYREF
  struct KERB_ERROR_METHOD_DATA *v129; // [rsp+E8h] [rbp-18h] BYREF
  size_t Size; // [rsp+F0h] [rbp-10h] BYREF
  int v131; // [rsp+F8h] [rbp-8h]
  unsigned int *v132; // [rsp+100h] [rbp+0h]
  unsigned __int8 *v133; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v134; // [rsp+110h] [rbp+10h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+118h] [rbp+18h] BYREF
  struct _UNICODE_STRING *v136; // [rsp+120h] [rbp+20h]
  struct _KERB_CREDMAN_CRED *v137; // [rsp+128h] [rbp+28h] BYREF
  unsigned int v138; // [rsp+130h] [rbp+30h]
  unsigned int v139; // [rsp+134h] [rbp+34h] BYREF
  int v140; // [rsp+138h] [rbp+38h]
  UNICODE_STRING String1; // [rsp+140h] [rbp+40h] BYREF
  struct _SecBuffer *v142; // [rsp+150h] [rbp+50h]
  struct _SecBufferDesc *v143; // [rsp+158h] [rbp+58h]
  int v144; // [rsp+160h] [rbp+60h]
  unsigned int v145; // [rsp+164h] [rbp+64h] BYREF
  BOOL v146; // [rsp+168h] [rbp+68h]
  union _LARGE_INTEGER v147; // [rsp+170h] [rbp+70h] BYREF
  HLOCAL hMem; // [rsp+178h] [rbp+78h] BYREF
  struct KERB_TGT_REPLY *v149; // [rsp+180h] [rbp+80h] BYREF
  void *Src; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int64 *v151; // [rsp+190h] [rbp+90h]
  PLARGE_INTEGER LocalTime[2]; // [rsp+198h] [rbp+98h] BYREF
  int v153; // [rsp+1A8h] [rbp+A8h]
  struct _KERB_LOGON_SESSION *v154[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _KERBEROS_LIST_ENTRY *v155; // [rsp+1C0h] [rbp+C0h]
  struct _UNICODE_STRING v156; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v157; // [rsp+1D8h] [rbp+D8h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+1E0h] [rbp+E0h] BYREF
  struct _SecBuffer *v159; // [rsp+1E8h] [rbp+E8h]
  struct _KERB_TICKET_CACHE_ENTRY *v160; // [rsp+1F0h] [rbp+F0h] BYREF
  char v161[8]; // [rsp+1F8h] [rbp+F8h] BYREF
  struct _SecBufferDesc *v162; // [rsp+200h] [rbp+100h]
  unsigned __int8 *v163; // [rsp+208h] [rbp+108h]
  struct _UNICODE_STRING v164; // [rsp+210h] [rbp+110h] BYREF
  __int64 v165; // [rsp+220h] [rbp+120h]
  UNICODE_STRING String; // [rsp+228h] [rbp+128h] BYREF
  UNICODE_STRING v167; // [rsp+238h] [rbp+138h] BYREF
  _OWORD v168[2]; // [rsp+248h] [rbp+148h] BYREF
  __int64 v169; // [rsp+268h] [rbp+168h]
  __int16 v170; // [rsp+270h] [rbp+170h] BYREF
  char v171[2]; // [rsp+272h] [rbp+172h] BYREF
  char v172; // [rsp+274h] [rbp+174h]
  __int128 v173; // [rsp+288h] [rbp+188h]
  int v174; // [rsp+29Ch] [rbp+19Ch]
  int *p_ChannelBindings; // [rsp+2A0h] [rbp+1A0h]
  int v176; // [rsp+2A8h] [rbp+1A8h]
  PLARGE_INTEGER *v177; // [rsp+2B0h] [rbp+1B0h]
  int v178; // [rsp+2B8h] [rbp+1B8h]
  PLARGE_INTEGER v179; // [rsp+2C0h] [rbp+1C0h]
  int v180; // [rsp+2C8h] [rbp+1C8h]
  struct _KERB_LOGON_SESSION **v181; // [rsp+2D0h] [rbp+1D0h]
  int v182; // [rsp+2D8h] [rbp+1D8h]
  struct _KERB_LOGON_SESSION *v183; // [rsp+2E0h] [rbp+1E0h]
  int v184; // [rsp+2E8h] [rbp+1E8h]
  struct _KERB_LOGON_SESSION **v185; // [rsp+2F0h] [rbp+1F0h]
  int v186; // [rsp+2F8h] [rbp+1F8h]
  struct _KERB_LOGON_SESSION *v187; // [rsp+300h] [rbp+200h]
  int v188; // [rsp+308h] [rbp+208h]
  struct _KERB_LOGON_SESSION **v189; // [rsp+310h] [rbp+210h]
  int v190; // [rsp+318h] [rbp+218h]
  struct _KERB_LOGON_SESSION *v191; // [rsp+320h] [rbp+220h]
  int v192; // [rsp+328h] [rbp+228h]

  v12 = a4;
  v138 = a4;
  v136 = a3;
  v155 = a2;
  v159 = a12;
  v143 = a6;
  v151 = a7;
  v162 = a8;
  v132 = a9;
  LocalTime[0] = a10;
  v163 = a11;
  KerbTracerT::KerbTracerT((KerbTracerT *)v161, "SP Init OLD", (unsigned int)a3);
  v127 = 0;
  v154[0] = 0;
  v122 = 0;
  v119 = 0;
  ChannelBindings = 0;
  v133 = 0;
  v125 = 0;
  Src = 0;
  Size = 0;
  v117 = 0;
  String = 0;
  String1 = 0;
  v124 = 0;
  v14 = 0;
  SystemTimeAsFileTime = 0;
  v126 = 0;
  v134 = 0;
  v128.LowPart = 0;
  v15 = 0;
  v118 = 0;
  v16 = 0;
  SystemTime.QuadPart = 0;
  v147.QuadPart = 0;
  LOBYTE(v131) = 0;
  v120 = 0;
  v17 = 0;
  v129 = 0;
  v149 = 0;
  memset(v168, 0, sizeof(v168));
  v169 = 0;
  v140 = 0;
  v137 = 0;
  v157 = 0;
  v160 = 0;
  hMem = 0;
  v145 = 0;
  memset_0(v171, 0, 0xDEu);
  v18 = 0;
  v170 = 0;
  v164 = 0;
  v167 = 0;
  v156 = 0;
  if ( v155 )
    v18 = (const void *)WORD1(v155);
  KerbTracerT::Log(7, "SpInitLsaModeContext_Old", 994, "SpInitLsaModeContext %p called\n", v18);
  if ( KerbEventTraceFlag )
  {
    v173 = KerbInitSCGuid;
    v172 = 1;
    v174 = 0x20000;
    v170 = 48;
    EtwLogTraceEvent(KerbTraceLoggerHandle, &v170);
  }
  *v132 = 0;
  *v151 = 0;
  *a10 = KerbGlobalHasNeverTime;
  *v163 = 0;
  v19 = v159;
  v159->pvBuffer = 0;
  v19->cbBuffer = 0;
  String = 0;
  String1 = 0;
  if ( !KerbGlobalInitialized )
  {
    ChannelBindings = -1073741604;
    v20 = 0;
    goto LABEL_324;
  }
  v146 = 0;
  v21 = 0;
  v142 = 0;
  ((void (__fastcall *)(char *))LsaFunctions->GetExtendedCallFlags)((char *)&Size + 4);
  if ( (Size & 0x400000000LL) != 0 )
    v16 = 0x80000;
  v123 = v16;
  v139 = v16;
  if ( (v12 & 1) != 0 )
  {
    v121 = 1;
    v12 = v12 & 0xFFEFFFFE | 0x100000;
    v138 = v12;
  }
  else
  {
    v121 = 0;
    v146 = (v12 & 0x100000) != 0;
  }
  if ( v162->cBuffers )
  {
    v22 = 0;
    while ( 1 )
    {
      pBuffers = v162->pBuffers;
      v24 = &pBuffers[v22];
      if ( (v24->BufferType & 0xFFFFFFF) == 2 )
        break;
      if ( ++v22 >= v162->cBuffers )
        goto LABEL_16;
    }
    v21 = &pBuffers[v22];
    v142 = v21;
    v25 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))LsaFunctions->MapBuffer)(v24, v21);
    ChannelBindings = v25;
  }
  else
  {
LABEL_16:
    v25 = ChannelBindings;
  }
  if ( v25 >= 0 )
  {
    v29 = 0;
    v30 = v143;
    if ( v143->cBuffers )
    {
      v31 = 0;
      v32 = v143->pBuffers;
      while ( 1 )
      {
        v33 = &v32[v31];
        if ( (v33->BufferType & 0xFFFFFFF) == 2 )
          break;
        if ( ++v31 >= v143->cBuffers )
          goto LABEL_27;
      }
      v29 = &v32[v31];
      v25 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))LsaFunctions->MapBuffer)(v33, v29);
      ChannelBindings = v25;
      v30 = v143;
    }
LABEL_27:
    if ( v25 < 0 )
    {
      v26 = "Failed to map Input token: 0x%x";
      v27 = 1097;
      goto LABEL_19;
    }
    if ( v30->cBuffers )
    {
      v34 = 0;
      v35 = v30->pBuffers;
      while ( 1 )
      {
        v36 = &v35[v34];
        if ( (v36->BufferType & 0xFFFFFFF) == 0xB )
          break;
        if ( ++v34 >= v30->cBuffers )
          goto LABEL_35;
      }
      v117 = &v35[v34];
      v25 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))LsaFunctions->MapBuffer)(v36, v117);
      ChannelBindings = v25;
      v30 = v143;
    }
LABEL_35:
    if ( v25 < 0 )
    {
      LODWORD(v113) = v25;
      v37 = "Failed to map Mechlist token: 0x%x";
      v38 = 1117;
      v28 = 1;
      v39 = 1;
LABEL_37:
      KerbTracerT::Log(v39, "SpInitLsaModeContext_Old", v38, v37, v113);
LABEL_97:
      v20 = v117;
      goto LABEL_98;
    }
    if ( v30->cBuffers )
    {
      v40 = 0;
      while ( 1 )
      {
        v42 = v40;
        v41 = v30->pBuffers;
        v43 = &v41[v40];
        if ( (v43->BufferType & 0xFFFFFFF) == 0x10 )
          break;
        if ( ++v40 >= v30->cBuffers )
          goto LABEL_42;
      }
      updated = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))LsaFunctions->MapBuffer)(
                  v43,
                  &v41[v40]);
      ChannelBindings = updated;
      if ( updated < 0 )
      {
        v37 = "Failed to map incoming SECBUFFER_TARGET_HOST. %x";
        v38 = 1133;
LABEL_49:
        LODWORD(v113) = updated;
        goto LABEL_50;
      }
      v47 = v143->pBuffers;
      v164.Buffer = (PWSTR)v47[v42].pvBuffer;
      cbBuffer = v47[v42].cbBuffer;
      if ( cbBuffer > 65532 - (unsigned __int64)HostTargetSvc.Length || (cbBuffer & 1) != 0 )
      {
        ChannelBindings = -2146893048;
        goto LABEL_57;
      }
      v164.MaximumLength = v47[v42].cbBuffer;
      v164.Length = v164.MaximumLength;
      ChannelBindings = KerbBuildHostTargetSPN(&v164, &v167);
      if ( ChannelBindings < 0 )
        goto LABEL_96;
    }
LABEL_42:
    ChannelBindings = KerbProcessTargetNames(v136, &String, &v167, 0, 1, &v126, &v124, &String1);
    if ( ChannelBindings < 0 )
      goto LABEL_96;
    ChannelBindings = SspGetChannelBindings(v44, v143, &v157);
    if ( ChannelBindings < 0 )
      goto LABEL_96;
    v116 = 0;
    v153 = 9;
    v144 = v12 & 0x20000000;
    v45 = v155;
    if ( !v155 )
      goto LABEL_85;
    KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 1221, "SpInitLsaModeContext: Second call to Initialize\n");
    ChannelBindings = KerbReferenceContext(v45, 0, (struct _KERB_CONTEXT **)&SystemTimeAsFileTime);
    v14 = SystemTimeAsFileTime;
    if ( !*(_QWORD *)&SystemTimeAsFileTime )
    {
      v113 = (struct _UNICODE_STRING *)WORD1(v45);
      v37 = "Failed to reference context %p";
      v38 = 1234;
LABEL_50:
      v28 = 1;
LABEL_51:
      v39 = 1;
      goto LABEL_37;
    }
    if ( !v29 )
    {
      v20 = v117;
      if ( !v117 )
      {
        v28 = 1;
        KerbTracerT::Log(
          1,
          "SpInitLsaModeContext_Old",
          1242,
          "SpInitLsaModeContext trying to complete a context with no input token!");
LABEL_61:
        ChannelBindings = -2146893048;
        goto LABEL_315;
      }
      if ( v21 )
        v21->cbBuffer = 0;
      if ( *(_DWORD *)(*(_QWORD *)&v14 + 216LL) != 5 )
      {
        v28 = 1;
        KerbTracerT::Log(
          1,
          "SpInitLsaModeContext_Old",
          1255,
          "Invalid context state: %d",
          *(_DWORD *)(*(_QWORD *)&v14 + 216LL));
        goto LABEL_61;
      }
      v63 = v132;
LABEL_160:
      ChannelBindings = 0;
      RtlAcquireResourceShared(&KerbContextResource, 1u);
      *v63 |= *(_DWORD *)(*(_QWORD *)&v14 + 192LL);
      RtlSystemTimeToLocalTime((PLARGE_INTEGER)(*(_QWORD *)&v14 + 24LL), LocalTime[0]);
      *v151 = (unsigned __int64)v45;
      RtlReleaseResource(&KerbContextResource);
      v28 = 1;
      goto LABEL_98;
    }
    RtlAcquireResourceShared(&KerbContextResource, 1u);
    v28 = *(_DWORD *)(*(_QWORD *)&v14 + 216LL);
    v153 = v28;
    if ( ((v28 - 1) & 0xFFFFFFF9) != 0 || v28 == 5 )
    {
      v114 = v28;
      v28 = 1;
      KerbTracerT::Log(1, "SpInitLsaModeContext_Old", 1277, "Invalid context state: %d", v114);
      ChannelBindings = -1073741816;
      goto LABEL_70;
    }
    v50 = KerbDuplicateStringEx(&v156, (const struct _UNICODE_STRING *)(*(_QWORD *)&v14 + 312LL), v49);
    ChannelBindings = v50;
    if ( v50 < 0 )
    {
      v28 = 1;
      KerbTracerT::Log(1, "SpInitLsaModeContext_Old", 1287, "Failed to duplicate ServerErrorName: 0x%08X\n", v50);
LABEL_70:
      RtlReleaseResource(&KerbContextResource);
      goto LABEL_97;
    }
    v118 = *(_DWORD *)(*(_QWORD *)&v14 + 192LL);
    v15 = v118;
    v123 = *(_DWORD *)(*(_QWORD *)&v14 + 196LL);
    v139 = v123;
    HIDWORD(v125) = *(_DWORD *)(*(_QWORD *)&v14 + 176LL);
    a1 = *(struct _KERB_CREDENTIAL **)(*(_QWORD *)&v14 + 128LL);
    v140 = *(_DWORD *)(*(_QWORD *)&v14 + 104LL);
    RtlReleaseResource(&KerbContextResource);
    if ( (v118 & 0x400) != 0 )
    {
      if ( v29->cbBuffer )
      {
        ChannelBindings = KerbReceiveErrorMessage(
                            (unsigned __int8 *)v29->pvBuffer,
                            v29->cbBuffer,
                            *(struct _KERB_CONTEXT **)&v14,
                            &v120,
                            &v129,
                            &v156);
        KerbTracerT::Log(
          3,
          "SpInitLsaModeContext_Old",
          1925,
          "SpInitLsaModeContext datagram called KerbReceiveErrorMessage %#x\n",
          ChannelBindings);
        if ( ChannelBindings >= 0 )
        {
          if ( v120 )
            v65 = *((_DWORD *)v120 + 13);
          else
            v65 = 60;
          KerbReportKerbError(
            0,
            0,
            0,
            v64,
            L"onecore\\ds\\security\\protocols\\kerberos\\client2\\ctxtapi.cxx",
            0x792u,
            v120,
            v65,
            0,
            0);
        }
        goto LABEL_96;
      }
      v28 = 1;
      v66 = KerbReferenceCredentialEx(a1, 0x80000002, 0, 0, &v122);
      ChannelBindings = v66;
      v67 = 0;
      if ( v66 < 0 )
      {
        v37 = "SpInitLsaModeContext datagram failed to locate credential: 0x%x\n";
        v38 = 1974;
LABEL_126:
        LODWORD(v113) = v66;
        v39 = 2;
        goto LABEL_37;
      }
      if ( (Size & 0x400000000LL) != 0 && !*((_QWORD *)v122 + 9) )
        goto LABEL_129;
      v128 = *(struct _LUID *)((char *)v122 + 28);
      v68 = (struct _RTL_CRITICAL_SECTION *)KerbLocateLogonSession(&v128, 0);
      v69 = v68;
      v127 = (struct _KERB_LOGON_SESSION *)v68;
      if ( !v68 )
        goto LABEL_131;
      RtlEnterCriticalSection(v68 + 2);
      if ( !*((_QWORD *)v122 + 9) )
      {
        if ( (*((_DWORD *)v122 + 16) & 0x20000000) != 0 || (v12 & 0x40000) != 0 )
        {
          v67 = 1;
          v15 = v118 | 0x40000;
          v118 |= 0x40000u;
        }
        v28 = 1;
      }
      RtlLeaveCriticalSection(v69 + 2);
      RtlAcquireResourceShared(&KerbContextResource, 1u);
      v119 = *(struct _KERB_TICKET_CACHE_ENTRY **)(*(_QWORD *)&v14 + 272LL);
      _InterlockedAdd((volatile signed __int32 *)v119 + 4, 1u);
      if ( *(_QWORD *)(*(_QWORD *)&v14 + 160LL) && (unsigned int)KerbDuplicateKey(v168, *(_QWORD *)&v14 + 136LL) )
        ChannelBindings = -1073741670;
      RtlReleaseResource(&KerbContextResource);
      if ( ChannelBindings < 0 )
        goto LABEL_97;
      KerbTracerT::Log(14, "SpInitLsaModeContext_Old", 2049, "Building AP request for datagram oriented context\n");
      v70 = v142;
      if ( !v142 )
      {
        KerbTracerT::Log(1, "SpInitLsaModeContext_Old", 2053, "Output token missing.");
        goto LABEL_108;
      }
      if ( v67 )
      {
        if ( (Size & 0x400000000LL) != 0 )
        {
          ChannelBindings = -1073741790;
          LODWORD(v113) = -1073741790;
          v37 = "AppContainer trying to use Null session: 0x%x";
          v38 = 2068;
          goto LABEL_51;
        }
        v15 &= 0x40D00u;
        v71 = KerbBuildEmptyApRequest(1u, &v133, (unsigned int *)&v125);
      }
      else
      {
        if ( !v119 )
        {
          KerbTracerT::Log(1, "SpInitLsaModeContext_Old", 2088, "SpInitLsaModeContext does NOT have service ticket\n");
          ChannelBindings = -1073741595;
          goto LABEL_102;
        }
        v113 = (struct _UNICODE_STRING *)v120;
        v71 = KerbBuildApRequest(v127, v122, v137);
        v15 = v118;
      }
      ChannelBindings = v71;
      if ( v71 < 0 )
      {
        LODWORD(v113) = v71;
        v37 = "Failed to build AP request: 0x%x";
        v38 = 2117;
        goto LABEL_51;
      }
      v73 = (unsigned int)v125;
      KerbTelemetry::KerbRecordMaxTokenSize((KerbTelemetry *)(unsigned int)v125, v72);
      if ( (v12 & 0x100) != 0 )
      {
        v70->pvBuffer = v133;
        v63 = v132;
        *v132 |= 0x100u;
        v133 = 0;
      }
      else
      {
        if ( v70->cbBuffer < (unsigned int)v73 )
        {
          KerbTracerT::Log(
            1,
            "SpInitLsaModeContext_Old",
            2132,
            "Output token is too small - sent in %d, needed %d",
            v70->cbBuffer,
            v73);
          KerbReportBufferTooSmallError(v73, v70->cbBuffer, *(struct _KERB_CONTEXT **)&v14, v119);
          v70->cbBuffer = v73;
          goto LABEL_112;
        }
        memcpy_0(v70->pvBuffer, v133, v73);
        v63 = v132;
      }
      v70->cbBuffer = v73;
    }
    else
    {
      if ( v28 == 1 )
      {
        KerbTracerT::Log(25, "SpInitLsaModeContext_Old", 1316, "SpInitLsaModeContext calling KerbUnpackTgtReply\n");
        RtlAcquireResourceExclusive(&KerbContextResource, 1u);
        v51 = *(_DWORD *)(*(_QWORD *)&v14 + 196LL);
        if ( (v51 & 0x10) == 0 )
        {
          *(_DWORD *)(*(_QWORD *)&v14 + 196LL) = v51 | 0x10;
          KerbTracerT::Log(
            2,
            "SpInitLsaModeContext_Old",
            1322,
            "SpInitLsaModeContext * use_sesion_key but USER2USER-OUTBOUND not set, added it now\n");
        }
        RtlReleaseResource(&KerbContextResource);
        v52 = KerbUnpackTgtReply(
                *(struct _KERB_CONTEXT **)&v14,
                (unsigned __int8 *)v29->pvBuffer,
                v29->cbBuffer,
                &v124,
                &String1,
                &v149);
        ChannelBindings = v52;
        if ( v52 < 0 )
        {
          KerbTracerT::Log(
            1,
            "SpInitLsaModeContext_Old",
            1337,
            "SpInitLsaModeContext failed to unpack TGT reply: 0x%x",
            v52);
          ChannelBindings = KerbReceiveErrorMessage(
                              (unsigned __int8 *)v29->pvBuffer,
                              v29->cbBuffer,
                              *(struct _KERB_CONTEXT **)&v14,
                              &v120,
                              &v129,
                              &v156);
          if ( ChannelBindings >= 0 )
          {
            if ( v120 )
              v54 = *((_DWORD *)v120 + 13);
            else
              v54 = 60;
            KerbReportKerbError(
              0,
              0,
              0,
              v53,
              L"onecore\\ds\\security\\protocols\\kerberos\\client2\\ctxtapi.cxx",
              0x552u,
              v120,
              v54,
              0,
              0);
          }
          goto LABEL_97;
        }
LABEL_86:
        KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2196, "SpInitLsaModeContext: First call to Initialize\n");
        v55 = KerbReferenceCredentialEx(a1, 0x80000002, 0, 0, &v122);
        ChannelBindings = v55;
        if ( v55 < 0 )
        {
          v56 = KerbReferenceCredentialEx(a1, 2u, 0, 0, &v122);
          ChannelBindings = v56;
          if ( v56 < 0 || *((_QWORD *)v122 + 9) )
          {
            KerbTracerT::Log(
              2,
              "SpInitLsaModeContext_Old",
              2224,
              "SpInitLsaModeContext failed to locate credential 0x%x, InitialStatus %#x\n",
              v56,
              v55);
            ChannelBindings = v55;
            goto LABEL_97;
          }
        }
        if ( (Size & 0x400000000LL) != 0 && !*((_QWORD *)v122 + 9) )
          goto LABEL_129;
        v128 = *(struct _LUID *)((char *)v122 + 28);
        v74 = (struct _RTL_CRITICAL_SECTION *)KerbLocateLogonSession(&v128, 0);
        v75 = v74;
        v127 = (struct _KERB_LOGON_SESSION *)v74;
        if ( v74 )
        {
          v76 = v74 + 2;
          RtlEnterCriticalSection(v74 + 2);
          LockSemaphore = (int)v75[22].LockSemaphore;
          RtlLeaveCriticalSection(v76);
          LowPart = v128.LowPart;
          if ( *((_QWORD *)v122 + 9) )
            goto LABEL_187;
          if ( (*((_DWORD *)v122 + 16) & 0x20000000) != 0 || (v138 & 0x40000) != 0 )
          {
            v116 = 1;
            v15 |= 0x40000u;
            v118 = v15;
            goto LABEL_187;
          }
          if ( (LockSemaphore & 0xF000) != 0 )
          {
            if ( (LockSemaphore & 0x100) == 0 )
            {
              v28 = 1;
              KerbTracerT::Log(
                1,
                "SpInitLsaModeContext_Old",
                2302,
                "Calling ISC from a nondelegatable S4U ls (%p)\n",
                (const void *)WORD1(v127));
LABEL_129:
              ChannelBindings = -2146893042;
              goto LABEL_102;
            }
            KerbTracerT::Log(
              21,
              "SpInitLsaModeContext_Old",
              2308,
              "Trying S4UProxy for ls %p\n",
              (const void *)WORD1(v127));
            ChannelBindings = KerbGetS4UProxyEvidence(v127, v79, v122, v154, &v160);
            if ( ChannelBindings < 0 )
            {
              v164 = 0;
              v165 = 0;
              ((void (__fastcall *)(struct _UNICODE_STRING *))LsaFunctions->GetCallInfo)(&v164);
              v28 = 1;
              KerbTracerT::Log(
                1,
                "SpInitLsaModeContext_Old",
                2331,
                "Failed to get S4UProxy Evidence ticket %x, caller process id %d for %#x:%#x\n",
                ChannelBindings,
                *(_DWORD *)&v164.Length,
                *((_DWORD *)v127 + 17),
                *((_DWORD *)v127 + 16));
              goto LABEL_129;
            }
            goto LABEL_187;
          }
          if ( v128.LowPart != 997 || v128.HighPart )
          {
            if ( (*((_BYTE *)v122 + 64) & 0x10) != 0 || (Size & 0x400000000LL) != 0 )
            {
              v28 = 1;
              KerbTracerT::Log(
                1,
                "SpInitLsaModeContext_Old",
                2370,
                "SpInitLsaModeContext autologon restricted for %#x:%#x\n",
                *((_DWORD *)v127 + 17),
                *((_DWORD *)v127 + 16));
              goto LABEL_129;
            }
            updated = KerbCheckCredMgrForGivenTarget(
                        v127,
                        v122,
                        v136,
                        v124,
                        (v138 >> 5) & 4,
                        &String1,
                        0,
                        &v137,
                        (unsigned __int8 **)&hMem,
                        &v145);
            ChannelBindings = updated;
            if ( updated < 0 )
            {
              v37 = "SpInitLsaModeContext failed to get outbound ticket, KerbCheckCredMgrForGivenTarget failed with 0x%x\n";
              v38 = 2402;
              goto LABEL_49;
            }
            if ( v137 )
            {
              v126 &= ~0x2000u;
              goto LABEL_187;
            }
            if ( (*((_DWORD *)v122 + 16) & 0x8000000) == 0 )
            {
LABEL_187:
              RtlEnterCriticalSection(v76);
              v113 = (struct _UNICODE_STRING *)((char *)v127 + 136);
              KerbTracerT::Log(
                9,
                "SpInitLsaModeContext_Old",
                2431,
                "SpInitLsaModeContext: Initailizing context for %wZ\\%wZ\n");
              RtlLeaveCriticalSection(v76);
              v81 = v138;
              if ( (v138 & 2) != 0 )
              {
                KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2449, "Client wants mutual auth.\n");
                v15 |= 2u;
                v118 = v15;
              }
              if ( (v81 & 8) != 0 )
              {
                KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2455, "Client wants sequence detect\n");
                v15 |= 0x10008u;
                v118 = v15;
              }
              if ( (v81 & 4) != 0 )
              {
                KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2461, "Client wants replay detect\n");
                v15 |= 0x10004u;
                v118 = v15;
              }
              if ( (v81 & 0x10000) != 0 )
              {
                KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2467, "Client wants integrity\n");
                v15 |= 0x10000u;
                v118 = v15;
              }
              if ( (v81 & 0x10) != 0 )
              {
                KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2473, "Client wants privacy\n");
                v81 &= ~0x40000000u;
                v15 |= 0x1001Cu;
                v118 = v15;
              }
              if ( (v81 & 0x40000000) != 0 )
              {
                if ( (v81 & 8) != 0 )
                {
                  if ( (v81 & 4) == 0 )
                  {
                    ChannelBindings = -2146893054;
                    LODWORD(v113) = -2146893054;
                    v37 = "Client wants confidentiality only and sequence detect w/o replay detect: %#x";
                    v38 = 2508;
                    goto LABEL_50;
                  }
                  KerbTracerT::Log(
                    9,
                    "SpInitLsaModeContext_Old",
                    2497,
                    "Client wants confidentiality only, sequence detect and replay detect\n");
                  v15 |= 0x4001001Cu;
                }
                else
                {
                  if ( (v81 & 4) != 0 )
                  {
                    ChannelBindings = -2146893054;
                    LODWORD(v113) = -2146893054;
                    v37 = "Client wants confidentiality only and replay detect w/o sequence detect: %#x";
                    v38 = 2514;
                    goto LABEL_50;
                  }
                  KerbTracerT::Log(
                    9,
                    "SpInitLsaModeContext_Old",
                    2519,
                    "Client wants confidentiality only, neither sequence detect nor replay detect is assumed\n");
                  v15 |= 0x40010010u;
                }
                v118 = v15;
              }
              if ( (v81 & 0x200) != 0 )
              {
                KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2529, "Client wants DCE style\n");
                v15 |= 0x200u;
                v118 = v15;
              }
              if ( (v81 & 0x4000) != 0 )
              {
                KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2535, "Client wants extended error\n");
                v15 |= 0x4000u;
                v118 = v15;
              }
              if ( (v81 & 0x400) != 0 )
              {
                if ( (v81 & 0x800) != 0 )
                {
                  v82 = "Client wanted both data gram and connection.";
                  v83 = 2543;
LABEL_213:
                  v28 = 1;
                  KerbTracerT::Log(1, "SpInitLsaModeContext_Old", v83, v82);
                  ChannelBindings = -2146893054;
                  goto LABEL_102;
                }
                KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2547, "Client wants Datagram style\n");
                v15 |= 0x400u;
                v118 = v15;
              }
              if ( (v81 & 0x20) != 0 )
              {
                KerbTracerT::Log(
                  25,
                  "SpInitLsaModeContext_Old",
                  2553,
                  "SpInitLsaModeContext Client wants sub-session key\n");
                v84 = v116;
                if ( v116 || (v81 & 0x600) != 0 )
                {
                  KerbTracerT::Log(
                    2,
                    "SpInitLsaModeContext_Old",
                    2579,
                    "SpInitLsaModeContext Client wanted both datagram and session key, dropping session key\n");
                }
                else
                {
                  v85 = (unsigned __int8)v131;
                  if ( ((v153 - 7) & 0xFFFFFFFD) == 0 )
                    v85 = 1;
                  v131 = v85;
                  v15 |= 0x20u;
                  v118 = v15;
                }
              }
              else
              {
                v84 = v116;
              }
              v116 = 0;
              v86 = 1;
              if ( (v81 & 1) != 0 || (v86 = 0x100000, (v81 & 0x100000) != 0) )
              {
                KerbpSetDelegationIfAllowed(v80, v86, &v118, (bool *)&v116);
                if ( v116 )
                {
                  KerbReportUnconstrainedDelegationBlockedByCredGuard(v136, v122);
                  KerbTelemetry::UnconstrainedDelegationRequested((KerbTelemetry *)1, v87);
                }
                v15 = v118;
              }
              if ( (v81 & 0x800) != 0 )
              {
                KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2604, "Client wants Connection style\n");
                v15 |= 0x800u;
                v118 = v15;
              }
              if ( (v81 & 0x20000) != 0 )
              {
                KerbTracerT::Log(9, "SpInitLsaModeContext_Old", 2610, "Client wants Identify level\n");
                v15 |= 0x20000u;
                v118 = v15;
                if ( (v81 & 0x100001) != 0 )
                {
                  KerbTracerT::Log(
                    2,
                    "SpInitLsaModeContext_Old",
                    2615,
                    "Client wants Delegation and Identify, turning off delegation\n");
                  v15 &= 0xFFEFFFFE;
                  v118 = v15;
                }
              }
              if ( (v81 & 0x1000000) != 0 )
              {
                v15 |= 0x1000000u;
                v118 = v15;
              }
              if ( v84 )
              {
                v15 &= 0x40D00u;
                v118 = v15;
LABEL_262:
                if ( (v15 & 0x400) != 0 )
                {
                  if ( KerbAllocateNonce((PUCHAR)&v125 + 4) )
                  {
                    if ( v142 )
                      v142->cbBuffer = 0;
LABEL_291:
                    if ( v14 )
                    {
                      updated = KerbUpdateClientContext(
                                  *(struct _KERB_CONTEXT **)&v14,
                                  v119,
                                  HIDWORD(v125),
                                  &v147,
                                  v134,
                                  v15,
                                  v123,
                                  (struct _KERB_ENCRYPTION_KEY *)v168,
                                  &v156,
                                  &SystemTime);
                    }
                    else
                    {
                      updated = KerbCreateClientContext(
                                  v95,
                                  v122,
                                  v137,
                                  v119,
                                  v136,
                                  HIDWORD(v125),
                                  &v147,
                                  v15,
                                  v123,
                                  (struct _KERB_ENCRYPTION_KEY *)v168,
                                  (struct _KERB_CONTEXT **)&SystemTimeAsFileTime,
                                  &SystemTime);
                      v14 = SystemTimeAsFileTime;
                    }
                    ChannelBindings = updated;
                    if ( updated >= 0 )
                    {
                      if ( (LowPart != 999 || v128.HighPart) && (LowPart != 996 || v128.HighPart)
                        || (SystemTimeAsFileTime = 0,
                            GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
                            *(_QWORD *)&SystemTimeAsFileTime += 2 * KerbGlobalSkewTime.QuadPart,
                            updated = KerbCreateSKeyEntry(
                                        &v128,
                                        (struct _KERB_ENCRYPTION_KEY *)v168,
                                        &SystemTimeAsFileTime,
                                        *((void **)v122 + 13)),
                            ChannelBindings = updated,
                            updated >= 0) )
                      {
                        v28 = 1;
                        RtlAcquireResourceExclusive(&KerbContextResource, 1u);
                        v97 = v119;
                        if ( v119 )
                        {
                          v98 = *(struct _KERB_TICKET_CACHE_ENTRY **)(*(_QWORD *)&v14 + 272LL);
                          if ( v98 )
                          {
                            KerbDereferenceTicketCacheEntry(v98);
                            v97 = v119;
                          }
                          _InterlockedAdd((volatile signed __int32 *)v97 + 4, 1u);
                          *(_QWORD *)(*(_QWORD *)&v14 + 272LL) = v119;
                        }
                        v140 = *(_DWORD *)(*(_QWORD *)&v14 + 104LL);
                        RtlReleaseResource(&KerbContextResource);
                        if ( ChannelBindings >= 0 && hMem )
                        {
                          RtlAcquireResourceExclusive(&KerbContextResource, 1u);
                          if ( !*(_QWORD *)(*(_QWORD *)&v14 + 344LL) )
                          {
                            *(_QWORD *)(*(_QWORD *)&v14 + 344LL) = hMem;
                            *(_DWORD *)(*(_QWORD *)&v14 + 352LL) = v145;
                            hMem = 0;
                          }
                          RtlReleaseResource(&KerbContextResource);
                        }
                        *v151 = (unsigned __int64)v14;
                        *v132 |= v15;
                        RtlSystemTimeToLocalTime(&SystemTime, LocalTime[0]);
                        if ( (v15 & 0x602) != 0 || (_BYTE)v131 )
                          ChannelBindings = 590610;
                        goto LABEL_97;
                      }
                      v37 = "Failed to create session key entry: 0x%x";
                      v38 = 3048;
                    }
                    else
                    {
                      v37 = "Failed to create client context: 0x%x";
                      v38 = 3024;
                    }
                    goto LABEL_49;
                  }
                  goto LABEL_285;
                }
                v92 = v142;
                if ( !v142 )
                {
                  v28 = 1;
                  KerbTracerT::Log(
                    1,
                    "SpInitLsaModeContext_Old",
                    2819,
                    "Trying to initialize a context with no output token!");
                  goto LABEL_108;
                }
                if ( v84 )
                {
                  ChannelBindings = KerbBuildEmptyApRequest(1u, &v133, (unsigned int *)&v125);
LABEL_278:
                  updated = ChannelBindings;
                  if ( ChannelBindings < 0 )
                  {
                    v37 = "Failed to build AP request: 0x%x\n";
                    v38 = 2896;
                    goto LABEL_49;
                  }
                  v94 = (unsigned int)v125;
                  KerbTelemetry::KerbRecordMaxTokenSize((KerbTelemetry *)(unsigned int)v125, v93);
                  if ( (v81 & 0x100) == 0 )
                  {
                    if ( v92->cbBuffer < (unsigned int)v94 )
                    {
                      KerbTracerT::Log(
                        1,
                        "SpInitLsaModeContext_Old",
                        2917,
                        "Output token is too small - sent in %d, needed %d",
                        v92->cbBuffer,
                        v94);
                      KerbReportBufferTooSmallError(v94, v92->cbBuffer, *(struct _KERB_CONTEXT **)&v14, v119);
                      v92->cbBuffer = v94;
                      ChannelBindings = -1073741789;
                      goto LABEL_57;
                    }
                    memcpy_0(v92->pvBuffer, v133, v94);
                    goto LABEL_287;
                  }
                  v96 = v133;
                  v92->pvBuffer = v133;
                  if ( v96 )
                  {
                    *v132 |= 0x100u;
                    v133 = 0;
LABEL_287:
                    v92->cbBuffer = v94;
                    goto LABEL_291;
                  }
LABEL_285:
                  ChannelBindings = -1073741670;
                  goto LABEL_57;
                }
                if ( !(_BYTE)v131 )
                {
                  KerbTracerT::Log(
                    14,
                    "SpInitLsaModeContext_Old",
                    2867,
                    "Building AP request for connection oriented context\n");
                  v113 = (struct _UNICODE_STRING *)v120;
                  ChannelBindings = KerbBuildApRequest(v127, v122, v137);
                  v134 = HIDWORD(v125);
                  v15 = v118;
                  goto LABEL_278;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  WPP_SF__KERB_NAME_(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    13,
                    WPP_4cf819f558c23a34c6140fdc5a6d2e85_Traceguids,
                    v124);
                if ( (v81 & 2) != 0 && (!v136 || !v136->Length) )
                {
                  v82 = "Client wanted mutual auth, but did not supply target name\n";
                  v83 = 2845;
                  goto LABEL_213;
                }
                ChannelBindings = KerbBuildTgtRequest(v124, &String1, &v139, &v133, (unsigned int *)&v125);
                KerbTracerT::Log(
                  25,
                  "SpInitLsaModeContext_Old",
                  2858,
                  "SpInitLsaModeContext built TGT request %#x\n",
                  ChannelBindings);
                if ( ChannelBindings >= 0 )
                {
                  v123 = v139;
                  goto LABEL_278;
                }
LABEL_96:
                v28 = 1;
                goto LABEL_97;
              }
              v113 = v136;
              KerbTracerT::Log(
                9,
                "SpInitLsaModeContext_Old",
                2642,
                "SpInitLsaModeContext: Getting outbound ticket for %wZ (%wZ)\n");
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
                WPP_SF__KERB_NAME_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  11,
                  WPP_4cf819f558c23a34c6140fdc5a6d2e85_Traceguids,
                  v124);
              RtlAcquireResourceShared(&KerbContextResource, 1u);
              if ( v120 && *((_DWORD *)v120 + 13) == 37 && *(_QWORD *)(*(_QWORD *)&v14 + 272LL) )
              {
                v119 = *(struct _KERB_TICKET_CACHE_ENTRY **)(*(_QWORD *)&v14 + 272LL);
                _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)&v14 + 272LL) + 16LL), 1u);
              }
              RtlReleaseResource(&KerbContextResource);
              if ( !v119 )
              {
                if ( (v123 & 0x40000) != 0 )
                {
                  KerbFreeString(&String1);
                  KerbFreeKdcName(&v124);
                  KerbTracerT::Log(2, "SpInitLsaModeContext_Old", 2677, "could not achieve server auth.\n");
                  v28 = 1;
                  v66 = KerbProcessTargetNames(&v156, 0, 0, 0, 1, &v126, &v124, &String1);
                  ChannelBindings = v66;
                  if ( v66 < 0 )
                  {
                    v37 = "SpInitLsaModeContext failed to process name from server error message failed with 0x%x\n";
                    v38 = 2691;
                    goto LABEL_126;
                  }
                }
                v88 = v160;
                if ( v160 )
                {
                  KerbTracerT::Log(
                    3,
                    "SpInitLsaModeContext_Old",
                    2698,
                    "SpInitLsaModeContext getting service ticket for S4UProxy\n");
                  ServiceTicketByS4UProxy = KerbGetServiceTicketByS4UProxy(
                                              (struct _RTL_CRITICAL_SECTION *)v127,
                                              v154[0],
                                              v122,
                                              v88,
                                              v124,
                                              &String1,
                                              v126,
                                              0,
                                              0,
                                              v120,
                                              0,
                                              v149,
                                              &v119,
                                              0);
                }
                else
                {
                  KerbTracerT::Log(3, "SpInitLsaModeContext_Old", 2718, "SpInitLsaModeContext getting service ticket\n");
                  ServiceTicketByS4UProxy = KerbGetServiceTicketEx(
                                              v127,
                                              v122,
                                              v137,
                                              0,
                                              0,
                                              v124,
                                              &String1,
                                              v126 | 4 | (KerbGlobalUseForestSearch != 0 ? 1179648 : 0x100000),
                                              0,
                                              0,
                                              v120,
                                              0,
                                              v149,
                                              &v119,
                                              0,
                                              0);
                }
                v90 = ServiceTicketByS4UProxy;
                ChannelBindings = ServiceTicketByS4UProxy;
                if ( ServiceTicketByS4UProxy == -1073740792 )
                {
                  KerbTracerT::Log(
                    25,
                    "SpInitLsaModeContext_Old",
                    2739,
                    "SpInitLsaModeContext failed to get serviceticket: STATUS_USER2USER_REQUIRED\n");
                  ChannelBindings = 0;
                  v15 |= 0x20u;
                  v118 = v15;
                  v28 = 1;
                  LOBYTE(v131) = 1;
                  goto LABEL_259;
                }
                if ( ServiceTicketByS4UProxy < 0 )
                {
                  v91 = "(proxy)";
                  if ( !v88 )
                    v91 = (const char *)&word_1800FEE0E;
                  KerbTracerT::Log(
                    2,
                    "SpInitLsaModeContext_Old",
                    2766,
                    "SpInitLsaModeContext failed to get outbound ticket, KerbGetServiceTicket %s failed with 0x%x\n",
                    v91,
                    v90);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    WPP_SF__KERB_NAME_(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      12,
                      WPP_4cf819f558c23a34c6140fdc5a6d2e85_Traceguids,
                      v124);
                  goto LABEL_96;
                }
              }
              v28 = 1;
LABEL_259:
              if ( (v15 & 0x420) == 0x420 )
              {
                KerbTracerT::Log(
                  1,
                  "SpInitLsaModeContext_Old",
                  2779,
                  "SpInitLsaModeContext Client needed session key in datagram, dropping session key\n");
                LOWORD(v15) = v15 | 0xFFDF;
                ChannelBindings = -1073741715;
                goto LABEL_102;
              }
              goto LABEL_262;
            }
            KerbTracerT::Log(2, "SpInitLsaModeContext_Old", 2419, "Trying to use a local logon session with Kerberos\n");
          }
          else
          {
            KerbTracerT::Log(
              2,
              "SpInitLsaModeContext_Old",
              2347,
              "Trying to use local service credentials for outbound authentication\n");
          }
          ChannelBindings = -2146893042;
LABEL_57:
          v20 = v117;
          v28 = 1;
          goto LABEL_315;
        }
LABEL_131:
        ChannelBindings = -1073741729;
        goto LABEL_102;
      }
      if ( v28 == 7 )
      {
        updated = KerbReceiveErrorMessage(
                    (unsigned __int8 *)v29->pvBuffer,
                    v29->cbBuffer,
                    *(struct _KERB_CONTEXT **)&v14,
                    &v120,
                    &v129,
                    &v156);
        ChannelBindings = updated;
        if ( updated < 0 )
        {
          v37 = "failed to receive solicited error %#x\n";
          v38 = 1422;
          goto LABEL_49;
        }
        KerbFreeData(6);
        v120 = 0;
LABEL_85:
        v28 = 1;
        goto LABEL_86;
      }
      ChannelBindings = KerbVerifyApReply(
                          *(struct _KERB_CONTEXT **)&v14,
                          (unsigned __int8 *)v29->pvBuffer,
                          v29->cbBuffer,
                          (unsigned int *)&v128);
      if ( ChannelBindings < 0 )
      {
        ChannelBindings = KerbReceiveErrorMessage(
                            (unsigned __int8 *)v29->pvBuffer,
                            v29->cbBuffer,
                            *(struct _KERB_CONTEXT **)&v14,
                            &v120,
                            &v129,
                            &v156);
        KerbTracerT::Log(
          3,
          "SpInitLsaModeContext_Old",
          1473,
          "SpInitLsaModeContext non datagram called KerbReceiveErrorMessage %#x\n",
          ChannelBindings);
        if ( ChannelBindings >= 0 )
        {
          if ( v120 )
            v58 = *((_DWORD *)v120 + 13);
          else
            v58 = 60;
          KerbReportKerbError(
            0,
            0,
            0,
            v57,
            L"onecore\\ds\\security\\protocols\\kerberos\\client2\\ctxtapi.cxx",
            0x5CEu,
            v120,
            v58,
            0,
            0);
        }
        goto LABEL_96;
      }
      v28 = 1;
      RtlAcquireResourceExclusive(&KerbContextResource, 1u);
      v59 = *(_DWORD *)(*(_QWORD *)&v14 + 192LL);
      *(_QWORD *)(*(_QWORD *)&v14 + 184LL) = v128.LowPart;
      RtlReleaseResource(&KerbContextResource);
      if ( (v59 & 0x200) != 0 )
      {
        v60 = KerbBuildThirdLegApReply(
                *(struct _KERB_CONTEXT **)&v14,
                v128.LowPart,
                (unsigned __int8 **)&Src,
                (unsigned int *)&Size);
        ChannelBindings = v60;
        if ( v60 < 0 )
        {
          LODWORD(v113) = v60;
          v37 = "Failed to build AP reply: 0x%x";
          v38 = 1833;
          goto LABEL_51;
        }
        v62 = v142;
        if ( !v142 )
        {
          KerbTracerT::Log(1, "SpInitLsaModeContext_Old", 1839, "Output token missing");
LABEL_108:
          ChannelBindings = -2146893048;
LABEL_102:
          v20 = v117;
          goto LABEL_315;
        }
        KerbTelemetry::KerbRecordMaxTokenSize((KerbTelemetry *)(unsigned int)Size, v61);
        if ( (v12 & 0x100) != 0 )
        {
          v62->pvBuffer = Src;
          Src = 0;
          v63 = v132;
          *v132 |= 0x100u;
        }
        else
        {
          if ( v62->cbBuffer < (unsigned int)Size )
          {
            KerbTracerT::Log(
              1,
              "SpInitLsaModeContext_Old",
              1855,
              "Output token is too small - sent in %d, needed %d",
              v62->cbBuffer,
              Size);
            KerbReportBufferTooSmallError(Size, v62->cbBuffer, *(struct _KERB_CONTEXT **)&v14, v119);
            v62->cbBuffer = Size;
LABEL_112:
            ChannelBindings = -1073741789;
            goto LABEL_102;
          }
          memcpy_0(v62->pvBuffer, Src, (unsigned int)Size);
          v63 = v132;
        }
        v62->cbBuffer = Size;
      }
      else
      {
        v63 = v132;
        if ( v142 )
          v142->cbBuffer = 0;
      }
    }
    *(_DWORD *)(*(_QWORD *)&v14 + 192LL) = v15;
    v45 = v155;
    v20 = v117;
    goto LABEL_160;
  }
  v26 = "Failed to map output token: 0x%x";
  v27 = 1077;
LABEL_19:
  LODWORD(v113) = v25;
  v28 = 1;
  KerbTracerT::Log(1, "SpInitLsaModeContext_Old", v27, v26, v113);
  v20 = 0;
LABEL_98:
  if ( !ChannelBindings || ChannelBindings == 590611 )
  {
    if ( v20 )
      KerbSqmNegoISCIncrement();
    else
      KerbSqmKerbISCIncrement();
  }
LABEL_315:
  if ( v146 && ((unsigned __int8)*v132 & (unsigned __int8)v28) != 0 )
  {
    v99 = *v132 & 0xFFEFFFFE | 0x100000;
LABEL_321:
    *v132 = v99;
    goto LABEL_322;
  }
  if ( v121 && (*v132 & 0x100000) != 0 )
  {
    v99 = v28 | *v132 & 0xFFEFFFFF;
    goto LABEL_321;
  }
LABEL_322:
  v17 = v129;
  v19 = v159;
  if ( ChannelBindings == -1073741718 )
    ChannelBindings = -1073741715;
LABEL_324:
  if ( !KerbEventTraceFlag )
    goto LABEL_339;
  v154[0] = (struct _KERB_LOGON_SESSION *)524296;
  v154[1] = (struct _KERB_LOGON_SESSION *)L"NONE";
  *(_OWORD *)LocalTime = 0;
  v100 = (struct _KERB_LOGON_SESSION **)(*(_QWORD *)&v14 + 296LL);
  if ( v14 )
  {
    if ( *(_QWORD *)(*(_QWORD *)&v14 + 328LL) )
    {
      RtlInitUnicodeString((PUNICODE_STRING)LocalTime, L"CredMan");
      v101 = *(struct _KERB_LOGON_SESSION ***)(*(_QWORD *)(*(_QWORD *)&v14 + 328LL) + 64LL);
      goto LABEL_336;
    }
  }
  else
  {
    v100 = v154;
  }
  if ( v122 && *((_QWORD *)v122 + 9) )
  {
    RtlInitUnicodeString((PUNICODE_STRING)LocalTime, L"Supplied");
    v101 = (struct _KERB_LOGON_SESSION **)*((_QWORD *)v122 + 9);
LABEL_336:
    v102 = v101 + 2;
    goto LABEL_338;
  }
  if ( !*(_QWORD *)&v14 )
  {
    v103 = v127;
    if ( !v127 )
    {
      RtlInitUnicodeString((PUNICODE_STRING)LocalTime, L"None");
      v102 = v154;
      v101 = v154;
      goto LABEL_338;
    }
    RtlInitUnicodeString((PUNICODE_STRING)LocalTime, L"LogonSession");
    v101 = (struct _KERB_LOGON_SESSION **)((char *)v103 + 120);
    goto LABEL_336;
  }
  RtlInitUnicodeString((PUNICODE_STRING)LocalTime, L"Context");
  v102 = (struct _KERB_LOGON_SESSION **)(*(_QWORD *)&v14 + 72LL);
  v101 = (struct _KERB_LOGON_SESSION **)(*(_QWORD *)&v14 + 56LL);
LABEL_338:
  p_ChannelBindings = &ChannelBindings;
  v176 = 4;
  v177 = LocalTime;
  v178 = 2;
  v179 = LocalTime[1];
  v180 = LOWORD(LocalTime[0]);
  v181 = v102;
  v182 = 2;
  v183 = v102[1];
  v184 = *(unsigned __int16 *)v102;
  v185 = v101;
  v186 = 2;
  v187 = v101[1];
  v188 = *(unsigned __int16 *)v101;
  v189 = v100;
  v190 = 2;
  v191 = v100[1];
  v192 = *(unsigned __int16 *)v100;
  v170 = 192;
  v173 = KerbInitSCGuid;
  v172 = 2;
  v174 = 1179648;
  EtwLogTraceEvent(KerbTraceLoggerHandle, &v170);
LABEL_339:
  if ( !*(_QWORD *)&v14 )
    goto LABEL_351;
  if ( ChannelBindings >= 0 )
  {
    RtlAcquireResourceExclusive(&KerbContextResource, 1u);
    if ( ChannelBindings )
    {
      if ( (_BYTE)v131 )
      {
        *(_DWORD *)(*(_QWORD *)&v14 + 216LL) = 1;
        *(_DWORD *)(*(_QWORD *)&v14 + 196LL) |= 0x10u;
        KerbTracerT::Log(
          25,
          "SpInitLsaModeContext_Old",
          3289,
          "SpInitLsaModeContext (TGT in TGT reply) USER2USER-OUTBOUND set\n");
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)&v14 + 216LL) = 3;
      }
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)&v14 + 216LL) = 5;
    }
    goto LABEL_349;
  }
  if ( v155 )
  {
    RtlAcquireResourceExclusive(&KerbContextResource, 1u);
    *(_DWORD *)(*(_QWORD *)&v14 + 216LL) = 9;
LABEL_349:
    RtlReleaseResource(&KerbContextResource);
    goto LABEL_350;
  }
  KerbReferenceContextByPointer(*(struct _KERB_CONTEXT **)&v14, 1u);
  KerbDereferenceContext(*(struct _KERB_CONTEXT **)&v14);
LABEL_350:
  KerbDereferenceContext(*(struct _KERB_CONTEXT **)&v14);
LABEL_351:
  if ( !ChannelBindings )
  {
    if ( (v15 & 0x400) != 0 )
      goto LABEL_359;
    if ( v20 )
    {
      v104 = *(_DWORD *)(*(_QWORD *)&v14 + 196LL);
      if ( (v104 & 0x4000) == 0 )
      {
        *(_DWORD *)(*(_QWORD *)&v14 + 196LL) = v104 | 0x4000;
        *v132 |= 0x2000000u;
      }
    }
    ChannelBindings = KerbGenerateOrVerifyMechlistMIC(*(struct _KERB_CONTEXT **)&v14, v143, v162);
    if ( !ChannelBindings )
      goto LABEL_359;
  }
  if ( ChannelBindings == 590610 && (v15 & 0x400) != 0 )
  {
LABEL_359:
    v105 = KerbMapContext(*(struct _KERB_CONTEXT **)&v14, v163, v19);
    KerbTracerT::Log(
      3,
      "SpInitLsaModeContext_Old",
      3332,
      "SpInitLsaModeContext called KerbMapContext ContextAttributes %#x, %#x\n",
      *(_DWORD *)(*(_QWORD *)&v14 + 196LL),
      v105);
    if ( v105 < 0 )
      ChannelBindings = v105;
    KerbUpdateSkewTime(0);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Enable_tryIPSPN>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_Enable_tryIPSPN>::GetImpl'::`2'::impl)
    && ChannelBindings != 590610
    && v136
    && v136->Length
    && v136->Buffer )
  {
    KerbTelemetry::RecordKerberosServices(
      (KerbTelemetry *)(unsigned int)ChannelBindings,
      (int)v136,
      0,
      (v126 >> 26) & 1,
      (int)v113);
  }
  v106 = v127;
  if ( v137 )
    KerbDereferenceCredmanCred(v137, (struct _KERB_LOGON_SESSION *)((char *)v127 + 8));
  if ( hMem )
    LocalFree(hMem);
  if ( v149 )
    KerbFreeData(59);
  if ( v106 )
    KerbDereferenceLogonSession(v106);
  if ( v122 )
    KerbDereferenceCredential(v122);
  if ( v119 )
    KerbDereferenceTicketCacheEntry(v119);
  KerbFreeData(6);
  if ( v17 )
    KerbFree(v17);
  if ( v133 )
    KerbFree(v133);
  if ( Src )
    KerbFree(Src);
  if ( v160 )
    KerbDereferenceTicketCacheEntry(v160);
  KerbFreeKey(v168);
  KerbFreeString(&String1);
  KerbFreeKdcName(&v124);
  KerbFreeString(&v156);
  KerbFreeString(&v167);
  v107 = ChannelBindings;
  if ( !ChannelBindings )
  {
    v108 = *v151;
    if ( *v151 )
    {
      v109 = *(struct _KERB_CREDENTIAL **)(v108 + 128);
      if ( v109 )
      {
        KerbDereferenceCredential(v109);
        *(_QWORD *)(v108 + 128) = 0;
        v107 = ChannelBindings;
      }
    }
  }
  if ( *v151 )
    v110 = (const void *)*((unsigned __int16 *)v151 + 1);
  else
    v110 = 0;
  KerbTracerT::Log(
    17,
    "SpInitLsaModeContext_Old",
    3438,
    "SpInitLsaModeContext returned 0x%x, Context %p, Pid 0x%x\n",
    v107,
    v110,
    v140);
  KerbTracerT::Log(7, "SpInitLsaModeContext_Old", 3439, "SpInitLsaModeContext returned 0x%x\n", ChannelBindings);
  KerbTracerT::CaptureLastStatus(ChannelBindings);
  v111 = ChannelBindings;
  KerbTracerT::~KerbTracerT((KerbTracerT *)v161);
  return v111;
}

```

## disassembly

```asm
0x180021574  mov     [rsp-8+arg_18], rbx
0x180021579  push    rbp
0x18002157a  push    rsi
0x18002157b  push    rdi
0x18002157c  push    r12
0x18002157e  push    r13
0x180021580  push    r14
0x180021582  push    r15
0x180021584  lea     rbp, [rsp-260h]
0x18002158c  sub     rsp, 360h
0x180021593  mov     rax, cs:__security_cookie
0x18002159a  xor     rax, rsp
0x18002159d  mov     [rbp+290h+var_40], rax
0x1800215a4  mov     r14d, r9d
0x1800215a7  mov     [rbp+290h+var_260], r9d
0x1800215ab  mov     [rbp+290h+var_270], r8
0x1800215af  mov     [rbp+290h+var_1D0], rdx
0x1800215b6  mov     r12, rcx
0x1800215b9  mov     rax, [rbp+290h+arg_58]
0x1800215c0  mov     [rbp+290h+var_1A8], rax
0x1800215c7  mov     rax, [rbp+290h+arg_28]
0x1800215ce  mov     [rbp+290h+var_238], rax
0x1800215d2  mov     rax, [rbp+290h+arg_30]
0x1800215d9  mov     [rbp+290h+var_200], rax
0x1800215e0  mov     rax, [rbp+290h+arg_38]
0x1800215e7  mov     [rbp+290h+var_190], rax
0x1800215ee  mov     r15, [rbp+290h+arg_40]
0x1800215f5  mov     [rbp+290h+var_290], r15
0x1800215f9  mov     r15, [rbp+290h+arg_48]
0x180021600  mov     [rbp+290h+LocalTime], r15
0x180021607  mov     rax, [rbp+290h+arg_50]
0x18002160e  mov     [rbp+290h+var_188], rax
0x180021615  lea     rdx, aSpInitOld; "SP Init OLD"
0x18002161c  lea     rcx, [rbp+290h+var_198]; this
0x180021623  call    ??0KerbTracerT@@QEAA@PEBDK@Z; KerbTracerT::KerbTracerT(char const *,ulong)
0x180021628  nop
0x180021629  xor     ecx, ecx
0x18002162b  mov     [rbp+290h+var_2B8], rcx
0x18002162f  mov     [rbp+290h+var_1E0], rcx
0x180021636  mov     [rbp+290h+var_2E0], rcx
0x18002163a  mov     [rbp+290h+var_2F8], rcx
0x18002163e  mov     dword ptr [rbp+290h+var_310], ecx
0x180021641  mov     [rbp+290h+var_288], rcx
0x180021645  mov     dword ptr [rbp+290h+var_2C8], ecx
0x180021648  mov     [rbp+290h+Src], rcx
0x18002164f  mov     dword ptr [rbp+290h+Size], ecx
0x180021652  mov     [rbp+290h+var_308], rcx
0x180021656  xorps   xmm0, xmm0
0x180021659  movups  xmmword ptr [rbp+290h+String.Length], xmm0
0x180021660  xorps   xmm1, xmm1
0x180021663  movups  xmmword ptr [rbp+290h+var_250.Length], xmm1
0x180021667  mov     [rbp+290h+var_2D0], rcx
0x18002166b  mov     esi, ecx
0x18002166d  mov     qword ptr [rbp+290h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180021671  mov     dword ptr [rbp+290h+var_2C8+4], ecx
0x180021674  mov     [rbp+290h+var_2C0], ecx
0x180021677  mov     [rbp+290h+var_280], ecx
0x18002167a  mov     [rbp+290h+var_2B0.LowPart], ecx
0x18002167d  mov     r13d, ecx
0x180021680  mov     [rbp+290h+var_300], ecx
0x180021683  mov     ebx, ecx
0x180021685  mov     qword ptr [rbp+290h+SystemTime], rcx
0x18002168c  mov     qword ptr [rbp+290h+var_220], rcx
0x180021690  mov     byte ptr [rbp+290h+var_298], cl
0x180021693  mov     [rbp+290h+var_2F0], rcx
0x180021697  mov     edi, ecx
0x180021699  mov     [rbp+290h+var_2A8], rcx
0x18002169d  mov     [rbp+290h+var_210], rcx
0x1800216a4  xor     eax, eax
0x1800216a6  movups  [rbp+290h+var_148], xmm0
0x1800216ad  movups  [rbp+290h+var_138], xmm0
0x1800216b4  mov     [rbp+290h+var_128], rax
0x1800216bb  mov     [rbp+290h+var_258], ecx
0x1800216be  mov     [rbp+290h+var_268], rcx
0x1800216c2  mov     [rbp+290h+var_1B8], rcx
0x1800216c9  mov     [rbp+290h+var_1A0], rcx
0x1800216d0  mov     [rbp+290h+hMem], rcx
0x1800216d4  mov     [rbp+290h+var_22C], ecx
0x1800216d7  xor     edx, edx; Val
0x1800216d9  mov     r8d, 0DEh; Size
0x1800216df  lea     rcx, [rbp+290h+var_11E]; void *
0x1800216e6  call    memset_0
0x1800216eb  xor     ecx, ecx
0x1800216ed  mov     [rbp+290h+var_120], cx
0x1800216f4  xorps   xmm0, xmm0
0x1800216f7  movups  xmmword ptr [rbp+290h+var_180.Length], xmm0
0x1800216fe  xorps   xmm1, xmm1
0x180021701  movups  xmmword ptr [rbp+290h+var_158.Length], xmm1
0x180021708  movups  xmmword ptr [rbp+290h+var_1C8.Length], xmm0
0x18002170f  mov     dword ptr [rbp+290h+Size+4], ecx
0x180021712  mov     rax, [rbp+290h+var_1D0]
0x180021719  test    rax, rax
0x18002171c  jz      short loc_180021725
0x18002171e  shr     rax, 10h
0x180021722  movzx   ecx, ax
0x180021725  mov     [rsp+390h+var_370], rcx
0x18002172a  lea     r9, aSpinitlsamodec_33; "SpInitLsaModeContext %p called\n"
0x180021731  mov     r8d, 3E2h
0x180021737  lea     rdx, aSpinitlsamodec_7; "SpInitLsaModeContext_Old"
0x18002173e  mov     ecx, 7
0x180021743  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180021748  cmp     cs:KerbEventTraceFlag, bl
0x18002174e  jz      short loc_180021790
0x180021750  movups  xmm0, cs:KerbInitSCGuid
0x180021757  movdqu  [rbp+290h+var_108], xmm0
0x18002175f  mov     [rbp+290h+var_11C], 1
0x180021766  mov     [rbp+290h+var_F4], 20000h
0x180021770  mov     eax, 30h ; '0'
0x180021775  mov     [rbp+290h+var_120], ax
0x18002177c  lea     rdx, [rbp+290h+var_120]
0x180021783  mov     rcx, cs:KerbTraceLoggerHandle
0x18002178a  call    cs:__imp_EtwLogTraceEvent
0x180021790  mov     rcx, [rbp+290h+var_290]
0x180021794  mov     [rcx], ebx
0x180021796  mov     rax, [rbp+290h+var_200]
0x18002179d  xor     ecx, ecx
0x18002179f  mov     [rax], rcx
0x1800217a2  mov     rax, cs:?KerbGlobalHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalHasNeverTime
0x1800217a9  mov     [r15], rax
0x1800217ac  mov     rax, [rbp+290h+var_188]
0x1800217b3  mov     [rax], cl
0x1800217b5  mov     r15, [rbp+290h+var_1A8]
0x1800217bc  mov     [r15+8], rcx
0x1800217c0  mov     [r15], ecx
0x1800217c3  xorps   xmm0, xmm0
0x1800217c6  movups  xmmword ptr [rbp+290h+String.Length], xmm0
0x1800217cd  xorps   xmm1, xmm1
0x1800217d0  movups  xmmword ptr [rbp+290h+var_250.Length], xmm1
0x1800217d4  cmp     cs:?KerbGlobalInitialized@@3EA, cl; uchar KerbGlobalInitialized
0x1800217da  jnz     short loc_1800217EB
0x1800217dc  mov     dword ptr [rbp+290h+var_310], 0C00000DCh
0x1800217e3  mov     r12d, ecx
0x1800217e6  jmp     loc_180023A87
0x1800217eb  mov     [rbp+290h+var_228], edi
0x1800217ee  mov     r15, rcx
0x1800217f1  mov     [rbp+290h+var_240], rcx
0x1800217f5  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800217fc  lea     rcx, [rbp+290h+Size+4]
0x180021800  mov     rax, [rax+1B0h]
0x180021807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002180c  test    byte ptr [rbp+290h+Size+4], 4
0x180021810  mov     eax, 80000h
0x180021815  cmovnz  ebx, eax
0x180021818  mov     [rbp+290h+var_2D8], ebx
0x18002181b  mov     [rbp+290h+var_25C], ebx
0x18002181e  mov     ebx, 1
0x180021823  test    bl, r14b
0x180021826  jz      short loc_18002183D
0x180021828  mov     [rbp+290h+var_2E8], bl
0x18002182b  and     r14d, 0FFFFFFFEh
0x18002182f  bts     r14d, 14h
0x180021834  mov     [rbp+290h+var_260], r14d
0x180021838  xor     r11d, r11d
0x18002183b  jmp     short loc_180021853
0x18002183d  xor     r11d, r11d
0x180021840  mov     [rbp+290h+var_2E8], r11b
0x180021844  bt      r14d, 14h
0x180021849  movzx   edi, dil
0x18002184d  cmovb   edi, ebx
0x180021850  mov     [rbp+290h+var_228], edi
0x180021853  mov     r9, [rbp+290h+var_190]
0x18002185a  cmp     [r9+4], r11d
0x18002185e  jbe     short loc_180021887
0x180021860  mov     ecx, r11d
0x180021863  mov     rdx, [r9+8]
0x180021867  mov     r8d, ecx
0x18002186a  shl     r8, 4
0x18002186e  add     r8, rdx
0x180021871  mov     eax, [r8+4]
0x180021875  and     eax, 0FFFFFFFh
0x18002187a  cmp     eax, 2
0x18002187d  jz      short loc_1800218B8
0x18002187f  add     ecx, ebx
0x180021881  cmp     ecx, [r9+4]
0x180021885  jb      short loc_180021867
0x180021887  mov     ecx, dword ptr [rbp+290h+var_310]
0x18002188a  test    ecx, ecx
0x18002188c  jns     short loc_1800218E2
0x18002188e  lea     r9, aFailedToMapOut; "Failed to map output token: 0x%x"
0x180021895  mov     r8d, 435h
0x18002189b  mov     dword ptr [rsp+390h+var_370], ecx
0x18002189f  lea     rdx, aSpinitlsamodec_7; "SpInitLsaModeContext_Old"
0x1800218a6  mov     r15d, ebx
0x1800218a9  mov     ecx, ebx
0x1800218ab  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800218b0  mov     r12, rsi
0x1800218b3  jmp     loc_18002217A
0x1800218b8  mov     r15, r8
0x1800218bb  mov     [rbp+290h+var_240], r8
0x1800218bf  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800218c6  mov     rdx, r8
0x1800218c9  mov     rcx, r8
0x1800218cc  mov     rax, [rax+98h]
0x1800218d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218d8  mov     ecx, eax
0x1800218da  mov     dword ptr [rbp+290h+var_310], eax
0x1800218dd  xor     r11d, r11d
0x1800218e0  jmp     short loc_18002188A
0x1800218e2  mov     rdi, r11
0x1800218e5  mov     r10, [rbp+290h+var_238]
0x1800218e9  cmp     [r10+4], r11d
0x1800218ed  jbe     short loc_180021940
0x1800218ef  mov     edx, r11d
0x1800218f2  mov     r9, [r10+8]
0x1800218f6  mov     r8d, edx
0x1800218f9  shl     r8, 4
0x1800218fd  add     r8, r9
0x180021900  mov     eax, [r8+4]
0x180021904  and     eax, 0FFFFFFFh
0x180021909  cmp     eax, 2
0x18002190c  jz      short loc_180021918
0x18002190e  add     edx, ebx
0x180021910  cmp     edx, [r10+4]
0x180021914  jb      short loc_1800218F6
0x180021916  jmp     short loc_180021940
0x180021918  mov     rdi, r8
0x18002191b  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180021922  mov     rdx, r8
0x180021925  mov     rcx, r8
0x180021928  mov     rax, [rax+98h]
0x18002192f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021934  mov     ecx, eax
0x180021936  mov     dword ptr [rbp+290h+var_310], eax
0x180021939  mov     r10, [rbp+290h+var_238]
0x18002193d  xor     r11d, r11d
0x180021940  test    ecx, ecx
0x180021942  jns     short loc_180021956
0x180021944  lea     r9, aFailedToMapInp; "Failed to map Input token: 0x%x"
0x18002194b  mov     r8d, 449h
0x180021951  jmp     loc_18002189B
0x180021956  cmp     [r10+4], r11d
0x18002195a  jbe     short loc_1800219AE
0x18002195c  mov     edx, r11d
0x18002195f  mov     r9, [r10+8]
0x180021963  mov     r8d, edx
0x180021966  shl     r8, 4
0x18002196a  add     r8, r9
0x18002196d  mov     eax, [r8+4]
0x180021971  and     eax, 0FFFFFFFh
0x180021976  cmp     eax, 0Bh
0x180021979  jz      short loc_180021985
0x18002197b  add     edx, ebx
0x18002197d  cmp     edx, [r10+4]
0x180021981  jb      short loc_180021963
0x180021983  jmp     short loc_1800219AE
0x180021985  mov     [rbp+290h+var_308], r8
0x180021989  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180021990  mov     rdx, r8
0x180021993  mov     rcx, r8
0x180021996  mov     rax, [rax+98h]
0x18002199d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219a2  mov     ecx, eax
0x1800219a4  mov     dword ptr [rbp+290h+var_310], eax
0x1800219a7  mov     r10, [rbp+290h+var_238]
0x1800219ab  xor     r11d, r11d
0x1800219ae  test    ecx, ecx
0x1800219b0  jns     short loc_1800219D9
0x1800219b2  mov     dword ptr [rsp+390h+var_370], ecx
0x1800219b6  lea     r9, aFailedToMapMec; "Failed to map Mechlist token: 0x%x"
0x1800219bd  mov     r8d, 45Dh
0x1800219c3  mov     r15d, ebx
0x1800219c6  mov     ecx, ebx
0x1800219c8  lea     rdx, aSpinitlsamodec_7; "SpInitLsaModeContext_Old"
0x1800219cf  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800219d4  jmp     loc_180022176
0x1800219d9  cmp     [r10+4], r11d
0x1800219dd  jbe     short loc_180021A0E
0x1800219df  mov     ecx, r11d
0x1800219e2  mov     rdx, [r10+8]
0x1800219e6  mov     ebx, ecx
0x1800219e8  add     rbx, rbx
0x1800219eb  lea     r8, [rdx+rbx*8]
0x1800219ef  mov     eax, [r8+4]
0x1800219f3  and     eax, 0FFFFFFFh
0x1800219f8  cmp     eax, 10h
0x1800219fb  jz      loc_180021AF5
0x180021a01  mov     ebx, 1
0x180021a06  add     ecx, ebx
0x180021a08  cmp     ecx, [r10+4]
0x180021a0c  jb      short loc_1800219E6
0x180021a0e  lea     rax, [rbp+290h+var_250]
0x180021a12  mov     [rsp+390h+var_358], rax; struct _UNICODE_STRING *
0x180021a17  lea     rax, [rbp+290h+var_2D0]
0x180021a1b  mov     [rsp+390h+var_360], rax; struct _KERB_INTERNAL_NAME **
0x180021a20  lea     rax, [rbp+290h+var_2C0]
0x180021a24  mov     [rsp+390h+String1], rax; unsigned int *
0x180021a29  mov     byte ptr [rsp+390h+var_370], bl; char
0x180021a2d  xor     r9d, r9d; unsigned int
0x180021a30  lea     r8, [rbp+290h+var_158]; PCUNICODE_STRING
0x180021a37  lea     rdx, [rbp+290h+String]; String
0x180021a3e  mov     rcx, [rbp+290h+var_270]; struct _UNICODE_STRING *
0x180021a42  call    ?KerbProcessTargetNames@@YAJPEBU_UNICODE_STRING@@00KEPEAKPEAPEAU_KERB_INTERNAL_NAME@@PEAU1@@Z; KerbProcessTargetNames(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong,uchar,ulong *,_KERB_INTERNAL_NAME * *,_UNICODE_STRING *)
0x180021a47  mov     dword ptr [rbp+290h+var_310], eax
0x180021a4a  test    eax, eax
0x180021a4c  js      loc_180022170
0x180021a52  lea     r8, [rbp+290h+var_1B8]
0x180021a59  mov     rdx, [rbp+290h+var_238]
0x180021a5d  call    SspGetChannelBindings
0x180021a62  mov     dword ptr [rbp+290h+var_310], eax
0x180021a65  test    eax, eax
  ... truncated ...
```
