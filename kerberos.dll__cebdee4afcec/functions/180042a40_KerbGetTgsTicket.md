# __KerbGetTgsTicket

- ea: `0x180042a40`
- end: `0x1800457e3`
- name: `__KerbGetTgsTicket`
- size: `11683`
- prototype: `__int64 __fastcall(int, int, int, int, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, unsigned int, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `70`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180040fb8`

## callees

- `0x1800019b8`
- `0x180004760`
- `0x180005c90`
- `0x180006350`
- `0x1800063e8`
- `0x1800068d0`
- `0x180006920`
- `0x1800069a0`
- `0x1800069e0`
- `0x180007e80`
- `0x1800088c4`
- `0x180008ec0`
- `0x180009744`
- `0x18000b300`
- `0x18000d9e4`
- `0x18000efd0`
- `0x180010d70`
- `0x180010e90`
- `0x180011150`
- `0x1800113f0`
- `0x180014380`
- `0x180014c50`
- `0x180014dc0`
- `0x1800163a0`
- `0x180018cf0`
- `0x18001e570`
- `0x18001fbc0`
- `0x180020690`
- `0x1800210e0`
- `0x180029360`
- `0x180029c50`
- `0x180029ec8`
- `0x18002a334`
- `0x18002c8a4`
- `0x18002d228`
- `0x180030170`
- `0x1800301ec`
- `0x180030a14`
- `0x180030b98`
- `0x180030ea8`
- `0x180032f94`
- `0x1800336dc`
- `0x180033e1c`
- `0x1800362a8`
- `0x18003aef0`
- `0x18003e170`
- `0x18003e9d8`
- `0x180042a40`
- `0x1800501e0`
- `0x1800621d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800451da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045628`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800451da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045628`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800446e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044c30`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800452be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800446e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044c30`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800452be`
- `ntdll!RtlEqualUnicodeString` at `0x1800437f9`
- `ntdll!RtlEqualUnicodeString` at `0x180043862`
- `ntdll!RtlEqualUnicodeString` at `0x18004387e`
- `ntdll!RtlEqualUnicodeString` at `0x180043897`
- `ntdll!RtlEqualUnicodeString` at `0x180043b12`
- `ntdll!RtlEqualUnicodeString` at `0x180043f63`
- `ntdll!RtlEqualUnicodeString` at `0x1800437f9`
- `ntdll!RtlEqualUnicodeString` at `0x180043862`
- `ntdll!RtlEqualUnicodeString` at `0x18004387e`
- `ntdll!RtlEqualUnicodeString` at `0x180043897`
- `ntdll!RtlEqualUnicodeString` at `0x180043b12`
- `ntdll!RtlEqualUnicodeString` at `0x180043f63`
- `ntdll!EtwEventActivityIdControl` at `0x1800455d8`
- `ntdll!EtwEventActivityIdControl` at `0x1800455d8`
- `ntdll!RtlEnterCriticalSection` at `0x180043281`
- `ntdll!RtlEnterCriticalSection` at `0x180043281`
- `ntdll!RtlLeaveCriticalSection` at `0x1800432be`
- `ntdll!RtlLeaveCriticalSection` at `0x1800432be`

## string_xrefs

- `0x18004364a`: `Failed to create crypto policy`
- `0x1800434cc`: `Forcing KDC proxy for target from SPN oracle`
- `0x180043c34`: `Inconsistent configuration: Hub DC does not support FAST while an RODC does.\n`
- `0x180043cbd`: `No trust allows the machine to get a TGT to %wZ for compound identity\n`
- `0x180043d49`: `TGS-REQ to domain %wZ requesting always compound\n`
- `0x180043f11`: `Failed to create explicit armor ap-req for TGS-REQ: %#x, Status %#x\n`
- `0x180044271`: `Failed to create authenticator: 0x%x`
- `0x1800443d1`: `Failed to create FAST armored TGS-REQ: %#x\n`
- `0x180044ab2`: `onecore\ds\security\protocols\kerberos\client2\kerbtick.cxx`
- `0x180044fff`: `No S4U available due to no A2D2 is configured\n`
- `0x1800454a5`: `Failed to compare realm names of ticket and reply: %#x Status %#x\n`
- `0x180043968`: `domain %wZ supports compound identity\n`
- `0x1800439c0`: `the service supports compound identity\n`
- `0x180043aa0`: `get machine TGT from hub for compounding. Machine TGT BranchID: %#x, User TGT BranchID: %#x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _KerbGetTgsTicket(
        __int64 a1,
        struct _KERB_CREDENTIAL *a2,
        struct _KERB_PROXY_LOGON_CRED *a3,
        __int64 a4,
        struct _KERB_INTERNAL_NAME *a5,
        struct _UNICODE_STRING *a6,
        unsigned int a7,
        unsigned int a8,
        int a9,
        __int64 a10,
        struct KERB_PA_FOR_USER *a11,
        struct PA_S4U_X509_USER *a12,
        struct KERB_KDC_REQUEST_preauth_data_s *a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        struct KERB_KDC_REPLY **a18,
        struct KERB_ENCRYPTED_KDC_REPLY **a19,
        int *a20,
        struct _UNICODE_STRING *a21,
        int *a22,
        struct _DMSA_KEY_PACKAGE *a23)
{
  struct _KERB_INTERNAL_NAME *v24; // rdi
  __int64 v25; // r14
  __int64 v26; // rdx
  struct KERB_KDC_REQUEST_preauth_data_s *v27; // r12
  bool v28; // r13
  struct _KERB_TICKET_CACHE_ENTRY *v29; // rsi
  __int64 v30; // r8
  int *v31; // rdx
  int *v32; // rdx
  __int64 v33; // rsi
  __int64 v34; // r8
  __int64 v35; // rdx
  struct KERB_KDC_REQUEST_preauth_data_s *v36; // rbx
  __int64 v37; // r9
  signed int ReferralNames; // edi
  char v39; // r14
  int v40; // r15d
  unsigned __int64 v41; // rdi
  int *v42; // r8
  unsigned __int64 v43; // rcx
  int v44; // eax
  __int64 v45; // rcx
  unsigned __int64 v46; // rcx
  void *v47; // rsp
  void *v48; // rsp
  int *v49; // rax
  unsigned __int64 i; // rdi
  int v51; // eax
  int v52; // edx
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rbx
  HLOCAL v56; // r12
  unsigned int v57; // ebx
  unsigned int v58; // ebx
  unsigned __int8 v59; // al
  struct _KERB_MIT_REALM *v60; // rdi
  int v61; // esi
  unsigned int v62; // r15d
  unsigned int v63; // edi
  __int64 v64; // rsi
  char v65; // r12
  char v66; // r14
  __int64 v67; // rdi
  int v68; // ebx
  int v69; // ebx
  const char *v70; // r9
  int ExtendedPolicies; // eax
  const char *v72; // r9
  __int64 v73; // r8
  struct _KERB_INTERNAL_NAME *v74; // r12
  char v75; // bl
  __int64 v76; // r9
  int v77; // eax
  unsigned int v78; // esi
  unsigned int v79; // eax
  struct _KERB_INTERNAL_NAME *v80; // rbx
  int v81; // r8d
  char v82; // bl
  __int64 PreAuthDataEntry; // rax
  int v84; // r8d
  _DWORD *v85; // rcx
  int v86; // edx
  int v87; // edx
  __int64 v88; // r8
  __int64 v89; // r8
  int v90; // eax
  const char *v91; // r9
  __int64 v92; // r8
  int v93; // eax
  unsigned int v94; // eax
  int v95; // r8d
  __int64 v96; // rdi
  __int64 v97; // rcx
  _OWORD *v98; // r8
  __int64 v99; // rdx
  int v100; // eax
  union _LARGE_INTEGER *v101; // r8
  struct KERB_PA_FOR_USER *v102; // r9
  struct PA_S4U_X509_USER *v103; // r8
  __int64 v104; // r9
  union _LARGE_INTEGER v105; // rdi
  KerbCredIsoApi **v106; // rsi
  unsigned int v107; // r9d
  struct KERB_KDC_REQUEST_preauth_data_s *v108; // r10
  unsigned int v109; // edx
  int v110; // eax
  int v111; // eax
  __int64 v112; // rdx
  unsigned int v113; // ebx
  __int64 v114; // rax
  struct _KERB_PROXY_LOGON_CRED *v115; // rax
  __int64 v116; // rdx
  signed int v117; // eax
  const char *v118; // r9
  __int64 v119; // r8
  unsigned int v120; // eax
  int v121; // esi
  int v122; // r8d
  unsigned __int8 v123; // al
  LONGLONG v124; // rbx
  int v125; // r8d
  __int64 v126; // r8
  __int64 v127; // r9
  struct KERB_PA_DATA *v128; // rax
  __int64 v129; // r9
  unsigned int v130; // eax
  signed int v131; // eax
  int v132; // r8d
  const char *v133; // r9
  __int64 v134; // r8
  __int64 v135; // rcx
  unsigned int v136; // ebx
  __int64 v137; // r8
  __int64 v138; // r9
  __int64 v139; // rax
  unsigned int v140; // eax
  int v141; // r8d
  unsigned int v142; // eax
  int v143; // r8d
  struct _KERB_CREDENTIAL *v144; // r9
  int v145; // eax
  unsigned __int8 v146; // cl
  _DWORD *v147; // r9
  int v148; // eax
  unsigned int v149; // eax
  int v150; // r8d
  struct _KERB_ENCRYPTION_KEY *v151; // rdx
  bool v152; // zf
  __int64 v153; // r8
  int v154; // edx
  struct _KERB_ENCRYPTION_KEY *v155; // rcx
  __int64 v156; // rax
  int v157; // r9d
  int v158; // eax
  __int64 v160; // [rsp+0h] [rbp-90h] BYREF
  struct PA_S4U_X509_USER *v161; // [rsp+20h] [rbp-70h]
  struct KERB_KDC_REQUEST_preauth_data_s **v162; // [rsp+28h] [rbp-68h]
  union _LARGE_INTEGER *v163; // [rsp+30h] [rbp-60h]
  int v164; // [rsp+90h] [rbp+0h] BYREF
  __int64 v165; // [rsp+98h] [rbp+8h] BYREF
  unsigned __int8 v166; // [rsp+A0h] [rbp+10h]
  int v167; // [rsp+A4h] [rbp+14h]
  unsigned int v168; // [rsp+A8h] [rbp+18h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v169; // [rsp+B0h] [rbp+20h] BYREF
  char v170; // [rsp+B8h] [rbp+28h]
  unsigned __int8 v171; // [rsp+B9h] [rbp+29h] BYREF
  char v172; // [rsp+BAh] [rbp+2Ah]
  char v173; // [rsp+BBh] [rbp+2Bh]
  char v174; // [rsp+BCh] [rbp+2Ch]
  char v175; // [rsp+BDh] [rbp+2Dh]
  char v176; // [rsp+BEh] [rbp+2Eh]
  char v177; // [rsp+BFh] [rbp+2Fh]
  char v178; // [rsp+C0h] [rbp+30h]
  char v179; // [rsp+C1h] [rbp+31h]
  unsigned __int8 v180[2]; // [rsp+C2h] [rbp+32h] BYREF
  unsigned int v181; // [rsp+C4h] [rbp+34h]
  int v182; // [rsp+C8h] [rbp+38h]
  int v183; // [rsp+CCh] [rbp+3Ch] BYREF
  struct KERB_ENCRYPTED_KDC_REPLY *v184; // [rsp+D0h] [rbp+40h] BYREF
  struct KERB_EXT_ERROR *v185; // [rsp+D8h] [rbp+48h] BYREF
  struct KERB_KDC_REQUEST_preauth_data_s *v186; // [rsp+E0h] [rbp+50h] BYREF
  struct KERB_ERROR *v187; // [rsp+E8h] [rbp+58h] BYREF
  struct KERB_KDC_REPLY *v188; // [rsp+F0h] [rbp+60h] BYREF
  UNICODE_STRING String2; // [rsp+F8h] [rbp+68h] BYREF
  struct _KERB_INTERNAL_NAME *v190; // [rsp+108h] [rbp+78h]
  UCHAR pbBuffer[4]; // [rsp+110h] [rbp+80h] BYREF
  unsigned int v192; // [rsp+114h] [rbp+84h] BYREF
  int *v193; // [rsp+118h] [rbp+88h]
  KerberosCryptoPolicy *v194; // [rsp+120h] [rbp+90h] BYREF
  unsigned int v195; // [rsp+128h] [rbp+98h] BYREF
  int v196; // [rsp+12Ch] [rbp+9Ch]
  int v197; // [rsp+130h] [rbp+A0h]
  struct _KERB_MIT_REALM *v198; // [rsp+138h] [rbp+A8h] BYREF
  union _LARGE_INTEGER v199; // [rsp+140h] [rbp+B0h] BYREF
  union _LARGE_INTEGER Time; // [rsp+148h] [rbp+B8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+150h] [rbp+C0h] BYREF
  unsigned int v202; // [rsp+158h] [rbp+C8h] BYREF
  HLOCAL hMem; // [rsp+160h] [rbp+D0h] BYREF
  struct _KERB_CREDENTIAL *v204; // [rsp+168h] [rbp+D8h]
  __int64 v205; // [rsp+170h] [rbp+E0h] BYREF
  union _LARGE_INTEGER v206; // [rsp+178h] [rbp+E8h]
  struct _KERB_ENCRYPTION_KEY *v207[2]; // [rsp+180h] [rbp+F0h] BYREF
  struct KERB_KDC_REQUEST_preauth_data_s *v208; // [rsp+190h] [rbp+100h] BYREF
  __int64 v209; // [rsp+198h] [rbp+108h] BYREF
  struct PA_S4U_X509_USER *v210; // [rsp+1A0h] [rbp+110h]
  struct _KERB_INTERNAL_NAME *v211; // [rsp+1A8h] [rbp+118h] BYREF
  struct KERB_KDC_REQUEST_preauth_data_s *v212; // [rsp+1B0h] [rbp+120h]
  __int128 v213; // [rsp+1B8h] [rbp+128h] BYREF
  UNICODE_STRING String1; // [rsp+1C8h] [rbp+138h] BYREF
  __int128 v215; // [rsp+1D8h] [rbp+148h] BYREF
  struct KERB_KDC_REQUEST_preauth_data_s *v216; // [rsp+1E8h] [rbp+158h]
  __int64 v217; // [rsp+1F0h] [rbp+160h]
  __int64 v218; // [rsp+1F8h] [rbp+168h]
  DWORD CurrentThreadId; // [rsp+200h] [rbp+170h] BYREF
  struct _KERB_PROXY_LOGON_CRED *v220; // [rsp+218h] [rbp+188h]
  struct _DMSA_KEY_PACKAGE *v221; // [rsp+220h] [rbp+190h]
  struct KERB_PA_FOR_USER *v222; // [rsp+228h] [rbp+198h]
  int *v223; // [rsp+230h] [rbp+1A0h]
  struct KERB_KDC_REPLY **v224; // [rsp+238h] [rbp+1A8h]
  struct KERB_ENCRYPTED_KDC_REPLY **v225; // [rsp+240h] [rbp+1B0h]
  int *v226; // [rsp+248h] [rbp+1B8h]
  struct _UNICODE_STRING *v227; // [rsp+250h] [rbp+1C0h]
  __int64 v228; // [rsp+258h] [rbp+1C8h] BYREF
  union _LARGE_INTEGER v229; // [rsp+260h] [rbp+1D0h] BYREF
  unsigned int v230[4]; // [rsp+268h] [rbp+1D8h] BYREF
  unsigned __int8 *v231; // [rsp+278h] [rbp+1E8h] BYREF
  __m256i v232; // [rsp+280h] [rbp+1F0h] BYREF
  __int128 v233; // [rsp+2A0h] [rbp+210h] BYREF
  unsigned __int8 *v234[2]; // [rsp+2B0h] [rbp+220h] BYREF
  struct _UNICODE_STRING v235; // [rsp+2C0h] [rbp+230h] BYREF
  _OWORD v236[2]; // [rsp+2D0h] [rbp+240h] BYREF
  __int64 v237; // [rsp+2F0h] [rbp+260h]
  _OWORD v238[2]; // [rsp+2F8h] [rbp+268h] BYREF
  __int64 v239; // [rsp+318h] [rbp+288h]
  __int128 v240; // [rsp+320h] [rbp+290h] BYREF
  __int64 v241; // [rsp+330h] [rbp+2A0h]
  struct KERB_KDC_REQUEST_preauth_data_s *EndOfPaDataList; // [rsp+338h] [rbp+2A8h]
  __int64 v243; // [rsp+340h] [rbp+2B0h]
  __int64 v244; // [rsp+348h] [rbp+2B8h]
  __int64 v245; // [rsp+350h] [rbp+2C0h]
  _QWORD v246[2]; // [rsp+358h] [rbp+2C8h] BYREF
  __int64 v247; // [rsp+368h] [rbp+2D8h] BYREF
  __int128 v248; // [rsp+370h] [rbp+2E0h] BYREF
  __int64 v249; // [rsp+380h] [rbp+2F0h]
  __int64 v250; // [rsp+388h] [rbp+2F8h] BYREF
  int v251; // [rsp+390h] [rbp+300h]
  _OWORD v252[2]; // [rsp+398h] [rbp+308h] BYREF
  __int64 v253; // [rsp+3B8h] [rbp+328h]
  _OWORD v254[2]; // [rsp+3C0h] [rbp+330h] BYREF
  __int64 v255; // [rsp+3E0h] [rbp+350h]
  _OWORD v256[2]; // [rsp+408h] [rbp+378h] BYREF
  __int64 v257; // [rsp+428h] [rbp+398h]
  __int64 v258; // [rsp+430h] [rbp+3A0h] BYREF
  __int128 v259; // [rsp+438h] [rbp+3A8h]
  __int128 v260; // [rsp+448h] [rbp+3B8h]
  __int128 v261; // [rsp+458h] [rbp+3C8h]
  __int128 v262; // [rsp+468h] [rbp+3D8h]
  _QWORD v263[11]; // [rsp+478h] [rbp+3E8h]
  _WORD v264[2]; // [rsp+4D0h] [rbp+440h] BYREF
  int v265; // [rsp+4D4h] [rbp+444h]
  int v266; // [rsp+4D8h] [rbp+448h]
  struct KERB_KDC_REQUEST_preauth_data_s *v267; // [rsp+4E0h] [rbp+450h] BYREF
  __int16 v268; // [rsp+4E8h] [rbp+458h] BYREF
  int v269; // [rsp+4F0h] [rbp+460h]
  int *v270; // [rsp+4F8h] [rbp+468h]
  CHAR *v271; // [rsp+510h] [rbp+480h] BYREF
  _BYTE v272[30]; // [rsp+518h] [rbp+488h] BYREF
  char v273[14]; // [rsp+536h] [rbp+4A6h] BYREF
  char v274[16]; // [rsp+544h] [rbp+4B4h] BYREF
  int v275; // [rsp+554h] [rbp+4C4h]
  struct _KERB_TICKET_CACHE_ENTRY *v276; // [rsp+558h] [rbp+4C8h] BYREF
  __m256i v277; // [rsp+568h] [rbp+4D8h]
  __int64 *v278; // [rsp+588h] [rbp+4F8h]
  int v279; // [rsp+590h] [rbp+500h] BYREF
  char v280; // [rsp+594h] [rbp+504h]
  _BYTE v281[16]; // [rsp+598h] [rbp+508h] BYREF
  _DWORD v282[4]; // [rsp+5A8h] [rbp+518h] BYREF

  v165 = a4;
  v220 = a3;
  v204 = a2;
  v218 = a1;
  v245 = a17;
  v210 = a12;
  v24 = a5;
  v190 = a5;
  v243 = a10;
  v222 = a11;
  v216 = a13;
  v217 = a14;
  v25 = a15;
  v244 = a16;
  v224 = a18;
  v225 = a19;
  v226 = a20;
  v227 = a21;
  v223 = a22;
  v221 = a23;
  v182 = 0;
  v168 = 0;
  v188 = 0;
  v184 = 0;
  v167 = 0;
  v235 = 0;
  memset_0(v264, 0, 0xC0u);
  v26 = 0;
  v185 = 0;
  *(_DWORD *)pbBuffer = 0;
  v229.QuadPart = 0;
  v233 = 0;
  *(_OWORD *)v234 = 0;
  v215 = 0u;
  v213 = 0u;
  v177 = 0;
  v176 = 0;
  v172 = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  v240 = 0;
  v241 = 0;
  v180[0] = 0;
  v183 = 0;
  v198 = 0;
  v197 = 0;
  v178 = 0;
  v179 = 0;
  v206.QuadPart = 0;
  v199.QuadPart = 0;
  memset(v238, 0, sizeof(v238));
  v239 = 0;
  memset(v254, 0, sizeof(v254));
  v255 = 0;
  memset(v256, 0, sizeof(v256));
  v257 = 0;
  *(_OWORD *)v230 = 0;
  v231 = 0;
  memset(v236, 0, sizeof(v236));
  v237 = 0;
  memset(v252, 0, sizeof(v252));
  v253 = 0;
  v205 = 0;
  v209 = 0;
  v202 = 0;
  v208 = 0;
  hMem = 0;
  v212 = 0;
  v27 = 0;
  v248 = 0;
  v249 = 0;
  v28 = 0;
  v173 = 0;
  v29 = 0;
  v169 = 0;
  v175 = 0;
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = 0;
  LOWORD(v164) = 0;
  LODWORD(v194) = 0;
  memset(&v232, 0, sizeof(v232));
  v171 = 0;
  v187 = 0;
  v174 = 0;
  v166 = 0;
  BYTE2(v164) = 0;
  v170 = 0;
  SystemTimeAsFileTime = 0;
  Time.QuadPart = 0;
  v211 = 0;
  v196 = 0;
  v181 = 0;
  v246[0] = v218;
  v246[1] = v204;
  *(_OWORD *)v207 = 0;
  v279 = 0;
  v280 = 0;
  if ( v25 )
    v30 = WORD1(v25);
  else
    v30 = 0;
  if ( v217 )
    v26 = WORD1(v217);
  LODWORD(v161) = a7;
  KerbTracerT::Log(
    3,
    "__KerbGetTgsTicket",
    4050,
    "KerbGetTgsTicket Flags %#x, Tgt DomainName %wZ, Tgt TargetDomainName %wZ, TgtReply %p, EvidenceTicket %p\n",
    v161,
    a4 + 48,
    a4 + 64,
    v26,
    v30);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, a5);
  *v224 = 0;
  *v225 = 0;
  *v226 = 0;
  *v227 = 0;
  *v223 = 0;
  EndOfPaDataList = KerbGetEndOfPaDataList(v216);
  if ( a9 != (_DWORD)v31 && (a7 & 0x200) != 0 )
  {
    v32 = &a9;
    v193 = &a9;
    LODWORD(v33) = 1;
    goto LABEL_47;
  }
  v193 = v31;
  KerberosCryptoPolicy::ForLocalMachine(&v194);
  if ( !v194 )
  {
    KerbTracerT::Log(1, "__KerbGetTgsTicket", 4089, "Failed to create crypto policy");
    ReferralNames = -1073741670;
    goto LABEL_115;
  }
  KerberosCryptoPolicy::GetEncryptionAlgorithms(v194, (__int64 *)&v186, v34);
  v36 = v186;
  v37 = 0;
  if ( !v186 )
  {
    KerbTracerT::Log(1, "__KerbGetTgsTicket", 4097, "Failed to build cipher list");
    ReferralNames = -1073741670;
    utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v186);
LABEL_115:
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v194);
    goto LABEL_16;
  }
  v33 = (__int64)(*((_QWORD *)v186 + 1) - *(_QWORD *)v186) >> 3;
  if ( (_DWORD)v33 )
  {
    v41 = 4LL * (unsigned int)v33;
    v42 = 0;
    v193 = 0;
    if ( v41 )
    {
      if ( v41 <= g_ulMaxStackAllocSize )
      {
        v43 = v41 + g_ulAdditionalProbeSize + 8;
        if ( v43 >= v41 )
        {
          v44 = VerifyStackAvailable(v43, v35, 0, 0);
          v37 = 0;
          if ( v44 )
          {
            v45 = v41 + 23;
            if ( v41 + 23 <= v41 + 8 )
              v45 = 0xFFFFFFFFFFFFFF0LL;
            v46 = v45 & 0xFFFFFFFFFFFFFFF0uLL;
            v47 = alloca(v46);
            v48 = alloca(v46);
            v42 = &v164;
            v193 = &v164;
            if ( &v160 != (__int64 *)-144LL )
            {
              v164 = 1801679955;
              v42 = (int *)&v165;
              v193 = (int *)&v165;
              if ( &v165 )
              {
LABEL_31:
                if ( v42 )
                {
                  for ( i = 0; i < (__int64)(*((_QWORD *)v36 + 1) - *(_QWORD *)v36) >> 3; ++i )
                  {
                    if ( i >= (__int64)(*((_QWORD *)v36 + 1) - *(_QWORD *)v36) >> 3 )
                      __int2c();
                    v51 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, __int64))(**(_QWORD **)(*(_QWORD *)v36 + 8 * i)
                                                                                     + 216LL))(
                            *(_QWORD *)(*(_QWORD *)v36 + 8 * i),
                            v35,
                            v42,
                            v37);
                    v42 = v193;
                    v193[i] = v51;
                  }
                  v52 = a9;
                  if ( a9 && *v42 != a9 )
                  {
                    v53 = 1;
                    if ( (unsigned int)v33 <= 1 )
                    {
LABEL_41:
                      v53 = (unsigned int)(v33 - 1);
                    }
                    else
                    {
                      while ( v42[v53] != a9 )
                      {
                        v53 = (unsigned int)(v53 + 1);
                        if ( (unsigned int)v53 >= (unsigned int)v33 )
                          goto LABEL_41;
                      }
                    }
                    if ( (_DWORD)v53 )
                    {
                      do
                      {
                        v54 = (unsigned int)(v53 - 1);
                        v42[v53] = v42[v54];
                        v53 = v54;
                      }
                      while ( (_DWORD)v54 );
                      v52 = a9;
                    }
                    *v42 = v52;
                  }
                  utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v186);
                  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v194);
                  v32 = v193;
                  v24 = v190;
LABEL_47:
                  if ( !(unsigned int)KerbConvertArrayToCryptList(&v276, v32, (unsigned int)v33)
                    && !(unsigned int)KerbConvertKdcNameToPrincipalName((struct KERB_PRINCIPAL_NAME *)v272, v24) )
                  {
                    v268 |= 0x40u;
                    ReferralNames = KerbDuplicateStringEx(&String2, a6);
                    if ( ReferralNames < 0 )
                      goto LABEL_49;
                    if ( !(unsigned int)KerbConvertUnicodeStringToRealm(&v271, &String2.Length) )
                    {
                      v57 = a8;
                      if ( !a8 )
                        v57 = KerbGlobalKdcOptions | *(_DWORD *)(v165 + 160) & 0x40810010;
                      v58 = v57 & 0xFFFDFFF7;
                      RtlEnterCriticalSection(&stru_180144D18);
                      v59 = KerbLookupMitRealm(&String2, &v198, (unsigned __int8 *)&v164 + 1);
                      v60 = v198;
                      if ( v59 )
                      {
                        v61 = *((_DWORD *)v198 + 6);
                        v197 = v61;
                      }
                      else
                      {
                        LOBYTE(v61) = v197;
                      }
                      RtlLeaveCriticalSection(&stru_180144D18);
                      v62 = a7;
                      if ( (a7 & 2) == 0 )
                      {
                        if ( !v60 )
                          goto LABEL_84;
                        if ( (v61 & 8) != 0 )
                        {
                          v58 |= 0x10000u;
LABEL_84:
                          v63 = 0;
                          v64 = v217;
                          if ( v217 )
                          {
                            KerbTracerT::Log(
                              25,
                              "__KerbGetTgsTicket",
                              4315,
                              "KerbGetTgsTicket setting KERB_KDC_OPTIONS_enc_tkt_in_skey (index %d)\n",
                              0);
                            v258 = 0;
                            v259 = *(_OWORD *)(v64 + 8);
                            v260 = *(_OWORD *)(v64 + 24);
                            v261 = *(_OWORD *)(v64 + 40);
                            v262 = *(_OWORD *)(v64 + 56);
                            v263[0] = *(_QWORD *)(v64 + 72);
                            v58 |= 8u;
                            v63 = 1;
                          }
                          v29 = 0;
                          if ( v25 )
                          {
                            KerbTracerT::Log(
                              3,
                              "__KerbGetTgsTicket",
                              4341,
                              "KerbGetTgsTicket setting KERB_KDC_OPTIONS_cname_in_addl_tkt (index %d)\n",
                              v63);
                            if ( v63 )
                              *(&v258 + 10 * v63 - 10) = (__int64)(&v258 + 10 * v63);
                            *(&v258 + 10 * v63) = 0;
                            *(&v259 + 5 * v63) = *(_OWORD *)v25;
                            *(&v260 + 5 * v63) = *(_OWORD *)(v25 + 16);
                            *(&v261 + 5 * v63) = *(_OWORD *)(v25 + 32);
                            *(_OWORD *)&v263[10 * v63 - 2] = *(_OWORD *)(v25 + 48);
                            v263[10 * v63] = *(_QWORD *)(v25 + 64);
                            v58 |= 0x20000u;
                          }
                          if ( (v58 & 0x20008) != 0 )
                          {
                            v278 = &v258;
                            v268 |= 2u;
                          }
                          LOBYTE(v183) = HIBYTE(v58);
                          BYTE1(v183) = BYTE2(v58);
                          BYTE2(v183) = BYTE1(v58);
                          HIBYTE(v183) = v58;
                          v269 = 32;
                          v270 = &v183;
                          if ( v220 && KerbCredentialForceProxy(*((struct _KERB_CREDENTIAL **)v220 + 1)) )
                          {
                            KerbTracerT::Log(
                              16,
                              "__KerbGetTgsTicket",
                              4371,
                              "Force kdc proxy using proxy credential to probe domain %wZ (TGS)\n",
                              &String2);
                          }
                          else if ( KerbCredentialForceProxy(v204) )
                          {
                            KerbTracerT::Log(
                              13,
                              "__KerbGetTgsTicket",
                              4376,
                              "KerbGetTgsTicketEx: force kdc proxy by credential\n");
                          }
                          else
                          {
                            if ( (a7 & 0x10000000) == 0 )
                            {
LABEL_100:
                              if ( KerbGlobalForceProxy )
                              {
                                KerbTracerT::Log(
                                  13,
                                  "__KerbGetTgsTicket",
                                  4387,
                                  "KerbGetTgsTicketEx: force kdc proxy globally\n");
                                v171 = 1;
                              }
                              v65 = 0;
                              v66 = 0;
                              goto LABEL_103;
                            }
                            KerbTracerT::Log(
                              3,
                              "__KerbGetTgsTicket",
                              4381,
                              "Forcing KDC proxy for target from SPN oracle");
                          }
                          v171 = 1;
                          goto LABEL_100;
                        }
                        v179 = 1;
                      }
                      v58 &= ~0x10000u;
                      goto LABEL_84;
                    }
                  }
                  ReferralNames = -1073741670;
LABEL_49:
                  v39 = 0;
                  v40 = 0;
                  goto LABEL_50;
                }
                goto LABEL_15;
              }
            }
          }
          else
          {
            v42 = 0;
          }
        }
      }
    }
    if ( v41 + 8 >= v41 )
    {
      v49 = (int *)((__int64 (__fastcall *)(unsigned __int64, __int64, int *, _QWORD))g_pfnAllocate)(
                     v41 + 8,
                     v35,
                     v42,
                     0);
      v42 = v49;
      v193 = v49;
      v37 = 0;
      if ( v49 )
      {
        *v49 = 1885431112;
        v42 = v49 + 2;
        v193 = v49 + 2;
      }
    }
    goto LABEL_31;
  }
LABEL_15:
  ReferralNames = -1073741670;
  utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v186);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v194);
  v29 = v169;
LABEL_16:
  v39 = BYTE1(v164);
LABEL_17:
  v40 = v167;
LABEL_51:
  v55 = v165;
  while ( 1 )
  {
    KerbFreeKey(v252);
    KerbFreeData(31);
    v185 = 0;
    if ( v207[0] )
      KerbFree(v207[0]);
    if ( v209 )
    {
      KerbFree(v209);
      v209 = 0;
    }
    KerbFreeData(71);
    v205 = 0;
    KerbFreeData(6);
    v187 = 0;
    if ( *((_QWORD *)&v213 + 1) )
      KerbFree(*((_QWORD *)&v213 + 1));
    v213 = 0;
    if ( *((_QWORD *)&v215 + 1) )
      KerbFree(*((_QWORD *)&v215 + 1));
    v215 = 0;
    v267 = 0;
    KerbFreePreAuthData(v27);
    if ( v208 )
    {
      KerbRestorePacOptionsPreAuth(&v208, (struct KERB_PA_DATA *)&v248);
      v248 = 0;
      v249 = 0;
      v208 = 0;
    }
    if ( v216 )
      *(_QWORD *)EndOfPaDataList = 0;
    v56 = hMem;
    if ( hMem )
      *(_QWORD *)v212 = 0;
    if ( v234[1] )
      KerbFree(v234[1]);
    v233 = 0;
    *(_OWORD *)v234 = 0;
    if ( v177 )
    {
      v177 = 0;
      goto LABEL_250;
    }
    KerbFree(v241);
    v240 = 0;
    v241 = 0;
    if ( v56 )
    {
      *(_QWORD *)v212 = 0;
      KerbFreePreAuthData(v56);
      hMem = 0;
      v212 = 0;
    }
    if ( v231 )
      KerbFree(v231);
    *(_OWORD *)v230 = 0;
    v231 = 0;
    KerbFreeKey(v238);
    KerbFreeKey(v254);
    KerbFreeKey(v256);
    KerbFreeKey(v236);
    if ( v176 && !v172 )
    {
      v172 = 1;
      v74 = v190;
LABEL_124:
      v75 = v164;
      goto LABEL_125;
    }
    if ( ReferralNames < 0 )
      goto LABEL_145;
    v74 = v190;
    ReferralNames = KerbGetReferralNames(v184, v190, &String1);
    if ( ReferralNames < 0 )
      goto LABEL_145;
    v77 = *(_DWORD *)(v55 + 164) & 0x200;
    v196 = v77;
    if ( !v198 && !v77 )
    {
      v78 = KerbConvertFlagsToUlong((struct KERB_ENCRYPTED_KDC_REPLY *)((char *)v184 + 64));
      if ( String1.Length )
      {
        if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
          goto LABEL_154;
      }
      else
      {
        v79 = KerbConvertPrincipalNameToKdcName(&v211, (struct KERB_ENCRYPTED_KDC_REPLY *)((char *)v184 + 144));
        v168 = v79;
        if ( v79 )
        {
          ReferralNames = KerbMapKerbError(v79);
          KerbTracerT::Log(
            1,
            "__KerbGetTgsTicket",
            5771,
            "Failed to conver from principal name to kdc name: %#x Status %#x\n",
            v81,
            ReferralNames);
          v29 = v169;
LABEL_145:
          v82 = BYTE2(v164);
          goto LABEL_146;
        }
        v80 = v211;
        if ( *((_WORD *)v211 + 1) != 2
          || !RtlEqualUnicodeString(&KerbGlobalKdcServiceName, (PCUNICODE_STRING)((char *)v74 + 8), 0)
          || !RtlEqualUnicodeString(&KerbGlobalKdcServiceName, (PCUNICODE_STRING)((char *)v80 + 8), 0)
          || RtlEqualUnicodeString((PCUNICODE_STRING)((char *)v80 + 24), &String2, 1u) )
        {
          v55 = v165;
          goto LABEL_154;
        }
        v55 = v165;
      }
      if ( (v78 & 0x40000) == 0 )
        v196 = 512;
    }
LABEL_154:
    v29 = v169;
    if ( String1.Length || !v173 || (_BYTE)v164 )
      goto LABEL_145;
    if ( (*((_DWORD *)v169 + 106) & 0x20000) != 0 )
    {
      KerbTracerT::Log(16, "__KerbGetTgsTicket", 5804, "domain %wZ supports compound identity\n", &String2);
    }
    else
    {
      PreAuthDataEntry = KerbFindPreAuthDataEntry(165, *((_QWORD *)v184 + 21), 0x20000, v76);
      if ( !PreAuthDataEntry
        || *(_DWORD *)(PreAuthDataEntry + 8) != 4
        || (v84 & **(_DWORD **)(PreAuthDataEntry + 16)) == 0 )
      {
        goto LABEL_145;
      }
      KerbTracerT::Log(16, "__KerbGetTgsTicket", 5830, "the service supports compound identity\n");
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        WPP_SF__KERB_NAME_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids,
          v74);
    }
    LOBYTE(v164) = 1;
    if ( *((char *)v29 + 304) >= 0 || !HIWORD(*((_DWORD *)v29 + 78)) )
      goto LABEL_124;
    v85 = (_DWORD *)(v55 + 312);
    v86 = (*(_WORD *)(v55 + 304) & 0x80) != 0 ? (unsigned __int16)HIWORD(*v85) : 0;
    if ( (unsigned __int16)HIWORD(*((_DWORD *)v29 + 78)) == v86 )
      goto LABEL_124;
    v87 = (*(_WORD *)(v55 + 304) & 0x80) != 0 ? (unsigned __int16)HIWORD(*v85) : 0;
    KerbTracerT::Log(
      16,
      "__KerbGetTgsTicket",
      5846,
      "get machine TGT from hub for compounding. Machine TGT BranchID: %#x, User TGT BranchID: %#x\n",
      HIWORD(*((_DWORD *)v29 + 78)),
      v87);
    v82 = 1;
    BYTE2(v164) = 1;
LABEL_146:
    if ( v29 )
    {
      if ( !v175 )
        KerbDereferenceTicketCacheEntry(v29);
      v29 = 0;
      v169 = 0;
      v175 = 0;
    }
    if ( !v82 || v170 != (_BYTE)v29 )
      break;
    BYTE2(v164) = (_BYTE)v29;
    v65 = 1;
    v170 = 1;
    v62 = a7;
    v66 = v166;
LABEL_103:
    v28 = (char)v29;
    if ( !KerbIsFastReady() )
      goto LABEL_203;
    v67 = v165;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(v165 + 168) + 16LL))(*(_QWORD *)(v165 + 168)) )
      goto LABEL_203;
    v68 = (v66 != 0 ? 0x40000 : 0) | 0x200000;
    if ( !v65 )
      v68 = v66 != 0 ? 0x40000 : 0;
    if ( v198 != v29 )
    {
      v69 = v197 & 0x10;
      v28 = v69 != 0;
      v70 = "TGS-REQ to Mit realm %wZ using FAST\n";
      if ( (v197 & 0x10) == 0 )
        v70 = "TGS-REQ to Mit realm %wZ w/o FAST\n";
      KerbTracerT::Log(16, "__KerbGetTgsTicket", v69 != 0 ? 4412 : 4416, v70, &String2);
      if ( KerbGlobalRequireFast != (_DWORD)v29 && !v69 )
      {
        ExtendedPolicies = -1073741715;
        ReferralNames = -1073741715;
        v72 = "Client requires FAST armored TGS-REQ but Mit realm %wZ does not support FAST: %#x\n";
        v73 = 4422;
LABEL_113:
        LODWORD(v162) = ExtendedPolicies;
        KerbTracerT::Log(1, "__KerbGetTgsTicket", v73, v72, &String2, v162);
        v27 = v29;
        v39 = (char)v29;
        v29 = v169;
        goto LABEL_17;
      }
LABEL_203:
      v29 = v169;
      goto LABEL_204;
    }
    if ( (v62 & 0x80000) == 0 || !RtlEqualUnicodeString(&String2, (PCUNICODE_STRING)((char *)v190 + 24), 1u) )
    {
      ExtendedPolicies = KerbGetExtendedPolicies((struct _KERB_PROXY_LOGON_CRED *)v246, &String2, v68, &v169);
      ReferralNames = ExtendedPolicies;
      if ( ExtendedPolicies < 0 )
      {
        v72 = "Failed to probe extended policies for domain %wZ: %#x\n";
        v73 = 4471;
        goto LABEL_113;
      }
      v29 = v169;
      v39 = 0;
      if ( !v169 || (*((_DWORD *)v169 + 106) & 0x10000) == 0 )
      {
        v89 = 4482;
        goto LABEL_191;
      }
      v88 = 4477;
      goto LABEL_189;
    }
    v29 = (struct _KERB_TICKET_CACHE_ENTRY *)v67;
    v169 = (struct _KERB_TICKET_CACHE_ENTRY *)v67;
    v175 = 1;
    KerbTracerT::Log(
      16,
      "__KerbGetTgsTicket",
      4440,
      "probe extended policies for domain %wZ from presented TGT: %p\n",
      &String2,
      WORD1(v67));
    if ( !v66 )
    {
      v39 = 0;
      if ( (*(_DWORD *)(v67 + 424) & 0x10000) == 0 )
      {
        v89 = 4456;
LABEL_191:
        v28 = 0;
        KerbTracerT::Log(16, "__KerbGetTgsTicket", v89, "TGS-REQ to domain %wZ w/o FAST\n", &String2);
        goto LABEL_192;
      }
      v88 = 4451;
LABEL_189:
      v28 = 1;
      KerbTracerT::Log(16, "__KerbGetTgsTicket", v88, "TGS-REQ to domain %wZ using FAST\n", &String2);
      goto LABEL_192;
    }
    v28 = 1;
    v39 = 0;
    KerbTracerT::Log(16, "__KerbGetTgsTicket", 4444, "TGS-REQ to domain %wZ using FAST\n", &String2);
LABEL_192:
    if ( v65 && !v28 )
    {
      KerbTracerT::Log(
        2,
        "__KerbGetTgsTicket",
        4488,
        "Inconsistent configuration: Hub DC does not support FAST while an RODC does.\n");
      LOBYTE(v164) = 0;
      v173 = 0;
    }
    if ( KerbGlobalRequireFast )
    {
      if ( !v28 )
      {
        ReferralNames = -1073741715;
        LODWORD(v162) = -1073741715;
        KerbTracerT::Log(
          1,
          "__KerbGetTgsTicket",
          4497,
          "Client requires FAST armored TGS-REQ but domain %wZ does not support FAST: %#x\n",
          &String2,
          v162);
        v27 = 0;
        goto LABEL_17;
      }
    }
    else if ( !v28 )
    {
      goto LABEL_204;
    }
    if ( (v62 & 0x100000) != 0 )
    {
      if ( v29 )
        v173 = 1;
      else
        KerbTracerT::Log(
          16,
          "__KerbGetTgsTicket",
          4513,
          "No trust allows the machine to get a TGT to %wZ for compound identity\n",
          &String2);
    }
LABEL_204:
    v39 = 0;
    if ( v29 && (*((_DWORD *)v29 + 106) & 0x40000) != 0 )
    {
      KerbTracerT::Log(16, "__KerbGetTgsTicket", 4521, "TGS-REQ to domain %wZ requesting claims\n", &String2);
      v39 = 1;
    }
    if ( !v28 || !KerbGlobalSendCompoundFirst || !v29 || (*((_DWORD *)v29 + 106) & 0x20000) == 0 )
    {
      v74 = v190;
      goto LABEL_124;
    }
    KerbTracerT::Log(16, "__KerbGetTgsTicket", 4527, "TGS-REQ to domain %wZ requesting always compound\n", &String2);
    v75 = 1;
    LOBYTE(v164) = 1;
    v74 = v190;
LABEL_125:
    KerbFreeKdcName(&v211);
    KerbFreeString((__int64)&String1);
    if ( v232.m256i_i64[3] )
      KerbFree(v232.m256i_i64[3]);
    memset(&v232, 0, sizeof(v232));
    if ( !KerbAllocateNonce(pbBuffer) )
    {
      ReferralNames = -1073741670;
LABEL_129:
      v27 = 0;
      goto LABEL_17;
    }
    if ( !v28 )
      goto LABEL_225;
    if ( v75 )
    {
      v93 = (*(__int64 (__fastcall **)(_QWORD, __int64, _OWORD *, _OWORD *, _OWORD *, _OWORD *))(**((_QWORD **)v29 + 21)
                                                                                               + 128LL))(
              *((_QWORD *)v29 + 21),
              (__int64)v29 + 168,
              v254,
              v256,
              v238,
              v236);
      ReferralNames = v93;
      if ( v93 < 0 )
      {
        KerbTracerT::Log(1, "__KerbGetTgsTicket", 4576, "Failed to build explicit armor key for ap-req: 0x%x", v93);
        goto LABEL_129;
      }
      v230[0] = 1;
      if ( !v206.QuadPart )
      {
        v206.QuadPart = 10000000LL * *((int *)v29 + 86);
        v199 = v206;
      }
      v94 = KerbCreateApRequest(
              *((struct _KERB_INTERNAL_NAME **)v29 + 18),
              (struct _UNICODE_STRING *)v29 + 6,
              (struct _KERB_TICKET_CACHE_ENTRY *)((char *)v29 + 168),
              (struct _KERB_ENCRYPTION_KEY *)v254,
              0,
              *(unsigned int *)pbBuffer,
              0,
              (struct _KERB_TICKET_CACHE_ENTRY *)((char *)v29 + 272),
              0,
              0,
              &v199,
              0xBu,
              &v230[2],
              &v231);
      v168 = v94;
      if ( v94 )
      {
        ReferralNames = KerbMapKerbError(v94);
        KerbTracerT::Log(
          1,
          "__KerbGetTgsTicket",
          4607,
          "Failed to create explicit armor ap-req for TGS-REQ: %#x, Status %#x\n",
          v95,
          ReferralNames);
        goto LABEL_129;
      }
LABEL_225:
      v55 = v165;
      goto LABEL_226;
    }
    v55 = v165;
    v90 = (*(__int64 (__fastcall **)(_QWORD, __int64, _OWORD *, _OWORD *))(**(_QWORD **)(v165 + 168) + 120LL))(
            *(_QWORD *)(v165 + 168),
            v165 + 168,
            v238,
            v236);
    ReferralNames = v90;
    if ( v90 < 0 )
    {
      v91 = "Failed to build ticket armor key for ap-req: 0x%x";
      v92 = 4563;
LABEL_217:
      LODWORD(v161) = v90;
      KerbTracerT::Log(1, "__KerbGetTgsTicket", v92, v91, v161);
      goto LABEL_218;
    }
LABEL_226:
    v96 = v243;
    if ( !v243
      || !*((_WORD *)v74 + 1)
      || RtlEqualUnicodeString((PCUNICODE_STRING)((char *)v74 + 8), &KerbGlobalKdcServiceName, 1u) )
    {
      goto LABEL_236;
    }
    if ( v28 )
    {
      v97 = *(_QWORD *)&v238[0];
      v161 = (struct PA_S4U_X509_USER *)&v232;
      v98 = v238;
      v99 = 5;
    }
    else
    {
      v98 = (_OWORD *)(v55 + 168);
      v97 = *(_QWORD *)(v55 + 168);
      if ( v244 )
        v98 = (_OWORD *)v244;
      v161 = (struct PA_S4U_X509_USER *)&v232;
      v99 = 4;
    }
    v100 = (*(__int64 (__fastcall **)(__int64, __int64, _OWORD *, __int64, struct PA_S4U_X509_USER *))(*(_QWORD *)v97 + 72LL))(
             v97,
             v99,
             v98,
             v96,
             v161);
    ReferralNames = v100;
    if ( v100 < 0 )
    {
      LODWORD(v161) = v100;
      KerbTracerT::Log(1, "__KerbGetTgsTicket", 4645, "Failed to encrypt auth data: 0x%x\n", v161);
LABEL_218:
      v27 = 0;
      v40 = v167;
    }
    else
    {
LABEL_236:
      if ( v232.m256i_i32[1] )
      {
        v277 = v232;
        v268 |= 4u;
      }
      v101 = &KerbGlobalWillNeverTime;
      if ( v245 )
        v101 = (union _LARGE_INTEGER *)v245;
      KerbConvertLargeIntToGeneralizedTime(v273, 0, v101);
      KerbConvertLargeIntToGeneralizedTime(v274, 0, &KerbGlobalHasNeverTime);
      v102 = v222;
      v103 = v210;
      if ( v222 || v210 )
      {
        *((_DWORD *)v210 + 1) = *(_DWORD *)pbBuffer;
        v90 = KerbSignAndPackS4UPreauthDataNew(
                (struct _KERB_ENCRYPTION_KEY *)(v55 + 168),
                (struct _KERB_ENCRYPTION_KEY *)((unsigned __int64)v238 & -(__int64)v28),
                a7,
                v102,
                v103,
                (struct KERB_KDC_REQUEST_preauth_data_s **)&hMem);
        ReferralNames = v90;
        if ( v90 < 0 )
        {
          v91 = "Failed to sign s4u preauth: %#x\n";
          v92 = 4698;
          goto LABEL_217;
        }
        v212 = KerbGetEndOfPaDataList((struct KERB_KDC_REQUEST_preauth_data_s *)hMem);
      }
      v275 = *(_DWORD *)pbBuffer;
      if ( !v198 || (v104 = *((unsigned int *)v198 + 7), !(_DWORD)v104) )
        v104 = 7;
      ReferralNames = (*(__int64 (__fastcall **)(_QWORD, __int16 *, __int64, __int64, __int128 *))(**(_QWORD **)(v55 + 168)
                                                                                                 + 80LL))(
                        *(_QWORD *)(v55 + 168),
                        &v268,
                        v55 + 168,
                        v104,
                        &v240);
      v27 = 0;
      v40 = v167;
      if ( ReferralNames >= 0 )
      {
        v56 = hMem;
LABEL_250:
        KerbFreeString((__int64)&v235);
        v40 = 0;
        v167 = 0;
        KerbFreeData(76);
        v184 = 0;
        KerbFreeData(74);
        v188 = 0;
        v195 = 0;
        v105.QuadPart = 10000000LL * *(int *)(v55 + 344);
        v206 = v105;
        v199 = v105;
        v106 = (KerbCredIsoApi **)(v55 + 168);
        v168 = KerbCreateApRequest(
                 *(struct _KERB_INTERNAL_NAME **)(v55 + 144),
                 (struct _UNICODE_STRING *)(v55 + 96),
                 (struct _KERB_ENCRYPTION_KEY *)(v55 + 168),
                 (struct _KERB_ENCRYPTION_KEY *)((unsigned __int64)v238 & -(__int64)v28),
                 0,
                 *(unsigned int *)pbBuffer,
                 &v229,
                 (struct KERB_TICKET *)(v55 + 272),
                 0,
                 (struct KERB_CHECKSUM *)&v240,
                 &v199,
                 7u,
                 (unsigned int *)v234,
                 &v234[1]);
        _InterlockedExchange((volatile __int32 *)(v55 + 344), (signed int)v105.LowPart / 10000000);
        if ( v168 )
        {
          KerbTracerT::Log(1, "__KerbGetTgsTicket", 4768, "Failed to create authenticator: 0x%x", v168);
          ReferralNames = -1073741670;
LABEL_252:
          v27 = 0;
          goto LABEL_253;
        }
        *(_QWORD *)&v233 = 0;
        DWORD2(v233) = 1;
        v267 = (struct KERB_KDC_REQUEST_preauth_data_s *)v56;
        v186 = v216;
        KerbConcatenatePaDataList(&v267, &v186);
        if ( (a7 & 0x400000) == 0 && KerbGlobalEnableCbacAndArmor != (_DWORD)v108 )
          v107 = 0x80000000;
        v109 = v107 | 0x10000000;
        if ( (a7 & 0x800000) == 0 )
          v109 = v107;
        if ( v109 )
        {
          v110 = KerbAddPacOptionsPreAuth(&v267, v109, (struct KERB_PA_DATA *)&v248);
          ReferralNames = v110;
          v108 = 0;
          if ( v110 < 0 )
          {
            KerbTracerT::Log(1, "__KerbGetTgsTicket", 4811, "KerbAddPacOptionsPreAuth failed: %#x\n", v110);
            goto LABEL_252;
          }
          v208 = v267;
        }
        v265 = 5;
        v266 = 12;
        v27 = v108;
        if ( v28 )
        {
          v111 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _QWORD, char *, unsigned __int64, _OWORD *))(**(_QWORD **)&v236[0] + 152LL))(
                   *(_QWORD *)&v236[0],
                   v264,
                   0,
                   (char *)&v233 + 8,
                   (unsigned __int64)v230 & -(__int64)((_BYTE)v164 != 0),
                   v236);
          ReferralNames = v111;
          v27 = 0;
          if ( v111 < 0 )
          {
            KerbTracerT::Log(1, "__KerbGetTgsTicket", 4833, "Failed to create FAST armored TGS-REQ: %#x\n", v111);
            goto LABEL_253;
          }
          v27 = v267;
        }
        v186 = (struct KERB_KDC_REQUEST_preauth_data_s *)&v233;
        KerbConcatenatePaDataList(&v186, &v267);
        v267 = v186;
        v264[0] |= 0x80u;
        v168 = KerbPackData((__int64)v264, 0x4Fu, &v215, (_QWORD *)&v215 + 1);
        if ( v168 )
        {
          ReferralNames = -1073741670;
          goto LABEL_253;
        }
        v113 = a7 & 0x8000000;
        if ( (a7 & 0x8000000) != 0 )
        {
          v181 |= 0x1000000u;
        }
        else if ( v28 || v39 || (a7 & 0x1000000) != 0 )
        {
          v181 |= 0x200000u;
          v40 = 16;
          v167 = 16;
        }
        else
        {
          v181 &= 0xFEDFFFFF;
          v167 = 0;
        }
        LOBYTE(v112) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_InstantHAADJ>::GetImpl'::`2'::impl,
          v112);
        if ( v204 && (*((_DWORD *)v204 + 16) & 0x400000) != 0 )
          v181 |= 0x2000000u;
        v192 = 0;
        if ( Ntlmless::Kerberos::IsEnabled(0)
          && (a7 & 0x20000000) != 0
          && (*(_DWORD *)(v218 + 904) & 0x800) != 0
          && (!v204 || (v114 = *((_QWORD *)v204 + 9)) == 0 || (*(_DWORD *)(v114 + 408) & 0x1000000) == 0) )
        {
          v192 |= 2u;
        }
        v115 = (struct _KERB_PROXY_LOGON_CRED *)v246;
        if ( v220 )
          v115 = v220;
        ReferralNames = KerbTransferMessage(
                          (struct _KERB_MESSAGE_BUFFER *)&v215,
                          (struct _KERB_MESSAGE_BUFFER *)&v213,
                          &String2,
                          0,
                          a7,
                          v181,
                          0,
                          v115,
                          0,
                          1u,
                          (unsigned __int64 *)&v186,
                          v180,
                          &v235,
                          0,
                          v204,
                          &v171,
                          &v192);
        LOBYTE(v116) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_InstantHAADJ>::GetImpl'::`2'::impl,
          v116);
        if ( ReferralNames < 0 )
        {
          v117 = v168;
          v118 = "failed to transfer kerberos message: 0x%x";
          v119 = 4948;
LABEL_290:
          LODWORD(v161) = v117;
          KerbTracerT::Log(1, "__KerbGetTgsTicket", v119, v118, v161);
          goto LABEL_50;
        }
        v120 = KerbUnpackData(*((_QWORD *)&v213 + 1), (unsigned int)v213, 74, &v188);
        v168 = v120;
        if ( v120 )
        {
          KerbTracerT::Log(2, "__KerbGetTgsTicket", 4961, "KerbGetTgsTicket failed to unpack KDC reply: 0x%x\n", v120);
          v168 = KerbUnpackData(*((_QWORD *)&v213 + 1), (unsigned int)v213, 6, &v187);
          if ( !v168 )
          {
            v121 = 0;
            if ( v28 )
            {
              ReferralNames = (*(__int64 (__fastcall **)(_QWORD, _WORD *, struct KERB_ERROR **, _OWORD *, __int64 *))(**(_QWORD **)&v236[0] + 160LL))(
                                *(_QWORD *)&v236[0],
                                v264,
                                &v187,
                                v236,
                                &v205);
              if ( ReferralNames < 0 )
              {
                v122 = *((_DWORD *)v187 + 13);
                if ( (unsigned int)(v122 - 32) <= 1 )
                {
                  ReferralNames = KerbMapKerbError(v122);
                  if ( !(_BYTE)v164 )
                  {
                    v40 |= 2u;
                    v167 = v40;
                    LODWORD(v161) = v125;
                    KerbTracerT::Log(
                      2,
                      "__KerbGetTgsTicket",
                      4995,
                      "the implicit armor ticket in TGS-REQ was either expired or not yet valid: %#x, caller retry\n",
                      v161);
                    goto LABEL_50;
                  }
                  if ( !v166 )
                  {
                    KerbTracerT::Log(
                      2,
                      "__KerbGetTgsTicket",
                      5002,
                      "the explicit armor ticket in TGS-REQ was either expired or not yet valid: %#x, reprobe FAST\n",
                      v125);
                    v174 = 1;
                    goto LABEL_50;
                  }
                }
                else if ( v122 == 37 )
                {
                  ReferralNames = KerbMapKerbError(37);
                  v123 = v172;
                  if ( !v172 )
                  {
                    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                    KerbConvertGeneralizedTimeToLargeInt(&Time);
                    v206.QuadPart = Time.QuadPart - *(_QWORD *)&SystemTimeAsFileTime;
                    v199.QuadPart = Time.QuadPart - *(_QWORD *)&SystemTimeAsFileTime;
                    v124 = (Time.QuadPart - *(_QWORD *)&SystemTimeAsFileTime) / 10000000;
                    _InterlockedExchange((volatile __int32 *)(v165 + 344), v124);
                    KerbUpdateSkewTime(1u);
                    KerbTracerT::Log(
                      2,
                      "__KerbGetTgsTicket",
                      5029,
                      "client recover FAST armor ticket time skew error in TGS-REQ: %#x, TimeSkew = %lld seconds\n",
                      *((_DWORD *)v187 + 13),
                      v124);
                    v176 = 1;
                    goto LABEL_50;
                  }
                  goto LABEL_304;
                }
                v123 = v172;
LABEL_304:
                LODWORD(v163) = v123;
                LODWORD(v162) = v166;
                LODWORD(v161) = ReferralNames;
                KerbTracerT::Log(
                  1,
                  "__KerbGetTgsTicket",
                  5036,
                  "Failed to verify FAST armored KRB-ERROR in response to TGS-REQ: %#x, RetriedProbeFast %d, RetriedTimeFailure %d\n",
                  v161,
                  v162,
                  v163);
                goto LABEL_50;
              }
              KerbTracerT::Log(
                16,
                "__KerbGetTgsTicket",
                5040,
                "Received FAST armored KRB-ERROR in response to TGS-REQ: %#x\n",
                *((_DWORD *)v187 + 13));
              v128 = (struct KERB_PA_DATA *)KerbFindPreAuthDataEntry(167, *(_QWORD *)(v205 + 8), v126, v127);
              if ( v128 )
              {
                v130 = KerbCheckPacOptionsPreAuthData(v128, &v195);
                v168 = v130;
                if ( v130 )
                {
                  v131 = KerbMapKerbError(v130);
                  LODWORD(v162) = v131;
                  LODWORD(v161) = v132;
                  v133 = "Failed to check pac options: %#x, Status %#x\n";
                  v134 = 5058;
                  goto LABEL_308;
                }
                v136 = v195;
                KerbTracerT::Log(
                  16,
                  "__KerbGetTgsTicket",
                  5062,
                  "Received PacOptions in KRB-ERROR in response to TGS-REQ: %#x\n",
                  v195);
                if ( (v136 & 0x10000000) != 0 )
                {
                  v40 |= 0x80u;
                  v167 = v40;
                }
              }
              if ( KerbFindPreAuthDataEntry(4294967168LL, *(_QWORD *)(v205 + 8), *(_QWORD *)(v205 + 8), v129) )
              {
                KerbTracerT::Log(
                  2,
                  "__KerbGetTgsTicket",
                  5075,
                  "remap FAST armored error KDC_ERR_S_PRINCIPAL_UNKNOWN to KDC_ERR_MUST_USE_USER2USER\n");
                *((_DWORD *)v187 + 13) = 27;
                goto LABEL_323;
              }
              v139 = KerbFindPreAuthDataEntry(3, v137, v137, v138);
              if ( v139 )
              {
                v140 = KerbPackData(*(_QWORD *)(v139 + 16), 0x1Fu, &v202, &v209);
                v168 = v140;
                if ( v140 )
                {
                  v131 = KerbMapKerbError(v140);
                  LODWORD(v162) = v131;
                  LODWORD(v161) = v141;
                  v133 = "Failed to pack extended error: %#x, Status %#x\n";
                  v134 = 5097;
                  goto LABEL_308;
                }
                v142 = KerbUnpackData(v209, v202, 31, &v185);
                v168 = v142;
                if ( v142 )
                {
                  v131 = KerbMapKerbError(v142);
                  LODWORD(v162) = v131;
                  LODWORD(v161) = v143;
                  v133 = "Failed to unpack extended error: %#x, Status %#x\n";
                  v134 = 5111;
                  goto LABEL_308;
                }
LABEL_321:
                if ( v185 )
                  v121 = *(_DWORD *)v185;
              }
            }
            else if ( (*(_BYTE *)v187 & 4) != 0 )
            {
              KerbUnpackErrorData(v187, &v185);
              goto LABEL_321;
            }
LABEL_323:
            v168 = *((_DWORD *)v187 + 13);
            KerbTracerT::Log(
              2,
              "__KerbGetTgsTicket",
              5140,
              "KerbGetTgsTicket KDC error reply: 0x%x, ExtendedStatus %#x\n",
              v168,
              v121);
            if ( v168 == 85 )
            {
              v145 = -1073741730;
              LODWORD(v162) = -1073741730;
              LODWORD(v161) = 85;
              v134 = 5145;
            }
            else
            {
              if ( v168 != 86 )
              {
                if ( v168 != 7 || !v185 || (v146 = 1, *(_DWORD *)v185 != -1073741771) )
                  v146 = 0;
                KerbReportKerbError(
                  v190,
                  &String2,
                  0,
                  v144,
                  L"onecore\\ds\\security\\protocols\\kerberos\\client2\\kerbtick.cxx",
                  0x142Bu,
                  v187,
                  v168,
                  v185,
                  v146);
              }
              v145 = -2146893039;
              LODWORD(v162) = -2146893039;
              LODWORD(v161) = 86;
              v134 = 5152;
            }
            v133 = "KerbGetTgsTicket IAKerb error translated to 0x%x, 0x%x\n";
            ReferralNames = v145;
            v135 = 2;
LABEL_309:
            KerbTracerT::Log(v135, "__KerbGetTgsTicket", v134, v133, v161, v162);
            goto LABEL_50;
          }
LABEL_353:
          ReferralNames = -1073741715;
LABEL_50:
          v29 = v169;
          goto LABEL_51;
        }
        if ( KerbGlobalKeyListReqSupportOverride )
        {
          if ( v113 )
          {
            _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v279);
            if ( (unsigned int)dword_180140048 > 5 )
            {
              if ( (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
              {
                CurrentThreadId = GetCurrentThreadId();
                v247 = 0x1000000;
                if ( v280 && (v282[0] || v282[1] || v282[2] || v282[3]) )
                  v147 = v282;
                else
                  LODWORD(v147) = 0;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                  (unsigned int)&dword_180140048,
                  (unsigned int)byte_18012B899,
                  (unsigned int)v281,
                  (_DWORD)v147,
                  (__int64)&v247,
                  (__int64)&CurrentThreadId);
              }
            }
          }
        }
        if ( v28 )
        {
          ReferralNames = (*(__int64 (__fastcall **)(_QWORD, _WORD *, struct KERB_KDC_REPLY **, _OWORD *, _OWORD *, _OWORD *, union _LARGE_INTEGER *))(**(_QWORD **)&v236[0] + 136LL))(
                            *(_QWORD *)&v236[0],
                            v264,
                            &v188,
                            v236,
                            v238,
                            v252,
                            &Time);
          if ( ReferralNames < 0 )
            goto LABEL_50;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          _InterlockedExchange(
            (volatile __int32 *)(v165 + 344),
            (signed int)(Time.LowPart - SystemTimeAsFileTime.dwLowDateTime) / 10000000);
          v148 = (*(__int64 (__fastcall **)(_QWORD, char *, _OWORD *, _QWORD, int, int, struct _KERB_ENCRYPTION_KEY **, struct _KERB_ENCRYPTION_KEY **, unsigned int *, struct KERB_ENCRYPTED_KDC_REPLY **, struct _DMSA_KEY_PACKAGE *))(**(_QWORD **)&v252[0] + 112LL))(
                   *(_QWORD *)&v252[0],
                   (char *)v188 + 120,
                   v252,
                   0,
                   76,
                   9,
                   &v207[1],
                   v207,
                   &v168,
                   &v184,
                   v221);
        }
        else
        {
          v148 = KerbCredIsoApi::UnpackKdcReplyBody(
                   *v106,
                   (struct KERB_KDC_REPLY *)((char *)v188 + 120),
                   (struct _KERB_ENCRYPTION_KEY *)v106,
                   0,
                   0x4Cu,
                   (unsigned int *)&v207[1],
                   v207,
                   (int *)&v168,
                   &v184,
                   v221);
        }
        ReferralNames = v148;
        if ( v148 < 0 )
        {
          LODWORD(v163) = v168;
          LODWORD(v162) = v148;
          KerbTracerT::Log(
            1,
            "__KerbGetTgsTicket",
            5510,
            "%hs: Failed to decrypt KDC reply body. NT: %#x, KERB: %#x\n",
            "__KerbGetTgsTicket",
            v162,
            v163);
          goto LABEL_50;
        }
        if ( v275 != *((_DWORD *)v184 + 10) )
        {
          KerbTracerT::Log(
            1,
            "__KerbGetTgsTicket",
            5522,
            "KerbGetTgsTicket AS Nonces don't match: 0x%x vs 0x%x",
            v275,
            *((_DWORD *)v184 + 10));
          goto LABEL_353;
        }
        if ( !(unsigned __int8)KerbComparePrincipalNames((char *)v184 + 144, (char *)v188 + 64) )
        {
          KerbTracerT::Log(
            1,
            "__KerbGetTgsTicket",
            5534,
            "KerbGetTgsTicket Mismatch between ticket sname and reply sname");
          goto LABEL_353;
        }
        BYTE1(v164) = 0;
        v149 = KerbCompareRealmNames((char *)v184 + 136, (char *)v188 + 56, (char *)&v164 + 1);
        v168 = v149;
        if ( v149 )
        {
          v131 = KerbMapKerbError(v149);
          LODWORD(v162) = v131;
          LODWORD(v161) = v150;
          v133 = "Failed to compare realm names of ticket and reply: %#x Status %#x\n";
          v134 = 5549;
LABEL_308:
          ReferralNames = v131;
          v135 = 1;
          goto LABEL_309;
        }
        if ( !BYTE1(v164) )
        {
          KerbTracerT::Log(
            1,
            "__KerbGetTgsTicket",
            5555,
            "KerbGetTgsTicket Mismatch between ticket realm and reply realm");
          goto LABEL_353;
        }
        if ( v222 || v210 )
        {
          v151 = (struct _KERB_ENCRYPTION_KEY *)v238;
          if ( !v28 )
            v151 = (struct _KERB_ENCRYPTION_KEY *)v106;
          v117 = KerbCheckX509S4uReply(*((_DWORD *)v210 + 8), a7, v210, v222, v151, v188, v184);
          ReferralNames = v117;
          if ( v117 < 0 )
          {
            v118 = "KerbGetTgsTicket failed to KerbCheckX509S4uReply: %#x\n";
            v119 = 5576;
            goto LABEL_290;
          }
        }
        v29 = v169;
        if ( !KerbGlobalKeyListReqSupportOverride )
          goto LABEL_51;
        v152 = v113 == 0;
        v55 = v165;
        if ( !v152 )
        {
          v153 = v218;
          if ( v218 )
          {
            v154 = (int)v207[1];
            LODWORD(v207[1]) = 0;
            v155 = v207[0];
            v207[0] = 0;
            v156 = *(_QWORD *)(v218 + 424);
            *(_QWORD *)(v218 + 424) = v155;
            v250 = v156;
            LODWORD(v156) = *(_DWORD *)(v153 + 432);
            *(_DWORD *)(v153 + 432) = v154;
            v251 = v156;
            kerb_encryption_keylist::~kerb_encryption_keylist((kerb_encryption_keylist *)&v250);
            *(_OWORD *)v207 = 0;
          }
          if ( v280 )
            EtwEventActivityIdControl(4, v282);
          v279 = 2;
          v29 = v169;
          if ( (unsigned int)dword_180140048 > 5 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
            {
              v195 = ReferralNames;
              LODWORD(v186) = v207[1];
              LODWORD(v194) = GetCurrentThreadId();
              v228 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180140048,
                (unsigned int)byte_18012B845,
                (unsigned int)v281,
                v157,
                (__int64)&v228,
                (__int64)&v194,
                (__int64)&v186,
                (__int64)&v195);
LABEL_253:
              v29 = v169;
            }
          }
        }
      }
    }
  }
  if ( v174 != (_BYTE)v29 )
  {
    v174 = (char)v29;
    v66 = 1;
    v166 = 1;
    v168 = (unsigned int)v29;
    v173 = (char)v29;
    LOBYTE(v164) = (_BYTE)v29;
    v62 = a7;
    v65 = v170;
    goto LABEL_103;
  }
  KerbFreeKdcName(&v211);
  KerbFreeString((__int64)&String1);
  if ( v232.m256i_i64[3] )
    KerbFree(v232.m256i_i64[3]);
  KerbFreeRealm(&v271);
  KerbFreeString((__int64)&String2);
  KerbFreePrincipalName(v272);
  KerbFreeCryptList(v276);
  v276 = v29;
  if ( v193 && v193 != &a9 && *(v193 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( ReferralNames >= 0 )
  {
    v158 = *v223;
    if ( v28 )
      v158 |= 0x40u;
    if ( (_BYTE)v164 != (_BYTE)v29 )
      v158 |= 0x80u;
    *v223 = v196 | v158;
    *v224 = v188;
    v188 = v29;
    *v225 = v184;
    v184 = v29;
  }
  *v226 = v40;
  *v227 = v235;
  v235 = 0;
  KerbFreeData(76);
  v184 = v29;
  KerbFreeData(74);
  v188 = v29;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v279);
  return (unsigned int)ReferralNames;
}

```

## disassembly

```asm
0x180042a40  push    rbp
0x180042a42  push    rbx
0x180042a43  push    rsi
0x180042a44  push    rdi
0x180042a45  push    r12
0x180042a47  push    r13
0x180042a49  push    r14
0x180042a4b  push    r15
0x180042a4d  sub     rsp, 5C8h
0x180042a54  lea     rbp, [rsp+90h]
0x180042a5c  mov     rax, cs:__security_cookie
0x180042a63  xor     rax, rbp
0x180042a66  mov     [rbp+570h+var_48], rax
0x180042a6d  mov     rbx, r9
0x180042a70  mov     [rbp+570h+var_568], rbx
0x180042a74  mov     [rbp+570h+var_3E8], r8
0x180042a7b  mov     [rbp+570h+var_498], rdx
0x180042a82  mov     [rbp+570h+var_408], rcx
0x180042a89  mov     rax, [rbp+570h+arg_80]
0x180042a90  mov     [rbp+570h+var_2B0], rax
0x180042a97  mov     rax, [rbp+570h+arg_58]
0x180042a9e  mov     [rbp+570h+var_460], rax
0x180042aa5  mov     rdi, [rbp+570h+arg_20]
0x180042aac  mov     [rbp+570h+var_4F8], rdi
0x180042ab0  mov     r15, [rbp+570h+arg_28]
0x180042ab7  mov     rax, [rbp+570h+arg_48]
0x180042abe  mov     [rbp+570h+var_2C0], rax
0x180042ac5  mov     rax, [rbp+570h+arg_50]
0x180042acc  mov     [rbp+570h+var_3D8], rax
0x180042ad3  mov     rax, [rbp+570h+arg_60]
0x180042ada  mov     [rbp+570h+var_418], rax
0x180042ae1  mov     rax, [rbp+570h+arg_68]
0x180042ae8  mov     [rbp+570h+var_410], rax
0x180042aef  mov     r14, [rbp+570h+arg_70]
0x180042af6  mov     rax, [rbp+570h+arg_78]
0x180042afd  mov     [rbp+570h+var_2B8], rax
0x180042b04  mov     rax, [rbp+570h+arg_88]
0x180042b0b  mov     [rbp+570h+var_3C8], rax
0x180042b12  mov     rax, [rbp+570h+arg_90]
0x180042b19  mov     [rbp+570h+var_3C0], rax
0x180042b20  mov     rax, [rbp+570h+arg_98]
0x180042b27  mov     [rbp+570h+var_3B8], rax
0x180042b2e  mov     rax, [rbp+570h+arg_A0]
0x180042b35  mov     [rbp+570h+var_3B0], rax
0x180042b3c  mov     rax, [rbp+570h+arg_A8]
0x180042b43  mov     [rbp+570h+var_3D0], rax
0x180042b4a  mov     rax, [rbp+570h+arg_B0]
0x180042b51  mov     [rbp+570h+var_3E0], rax
0x180042b58  xor     eax, eax
0x180042b5a  mov     [rbp+570h+var_538], eax
0x180042b5d  mov     [rbp+570h+var_558], eax
0x180042b60  mov     [rbp+570h+var_510], rax
0x180042b64  mov     [rbp+570h+var_530], rax
0x180042b68  mov     [rbp+570h+var_55C], eax
0x180042b6b  xorps   xmm0, xmm0
0x180042b6e  movups  xmmword ptr [rbp+570h+var_340.Length], xmm0
0x180042b75  xor     edx, edx; Val
0x180042b77  mov     r8d, 0C0h; Size
0x180042b7d  lea     rcx, [rbp+570h+var_130]; void *
0x180042b84  call    memset_0
0x180042b89  xor     edx, edx
0x180042b8b  mov     [rbp+570h+var_528], rdx
0x180042b8f  mov     dword ptr [rbp+570h+pbBuffer], edx
0x180042b95  mov     qword ptr [rbp+570h+var_3A0], rdx
0x180042b9c  xorps   xmm0, xmm0
0x180042b9f  movups  [rbp+570h+var_360], xmm0
0x180042ba6  movups  xmmword ptr [rbp+570h+var_350], xmm0
0x180042bad  mov     qword ptr [rbp+570h+var_428], rdx
0x180042bb4  mov     qword ptr [rbp+570h+var_428+8], rdx
0x180042bbb  mov     qword ptr [rbp+570h+var_448], rdx
0x180042bc2  mov     qword ptr [rbp+570h+var_448+8], rdx
0x180042bc9  mov     [rbp+570h+var_541], dl
0x180042bcc  mov     [rbp+570h+var_542], dl
0x180042bcf  mov     [rbp+570h+var_546], dl
0x180042bd2  mov     qword ptr [rbp+570h+String2.Length], rdx
0x180042bd6  mov     [rbp+570h+String2.Buffer], rdx
0x180042bda  xor     eax, eax
0x180042bdc  movups  [rbp+570h+var_2E0], xmm0
0x180042be3  mov     [rbp+570h+var_2D0], rax
0x180042bea  mov     [rbp+570h+var_53E], dl
0x180042bed  mov     [rbp+570h+var_534], edx
0x180042bf0  mov     [rbp+570h+var_4C8], rdx
0x180042bf7  mov     [rbp+570h+var_4D0], edx
0x180042bfd  mov     [rbp+570h+var_540], dl
0x180042c00  mov     [rbp+570h+var_53F], dl
0x180042c03  mov     [rbp+570h+var_488], rdx
0x180042c0a  mov     qword ptr [rbp+570h+var_4C0], rdx
0x180042c11  movups  [rbp+570h+var_308], xmm0
0x180042c18  movups  [rbp+570h+var_2F8], xmm0
0x180042c1f  mov     [rbp+570h+var_2E8], rax
0x180042c26  xorps   xmm1, xmm1
0x180042c29  movups  [rbp+570h+var_240], xmm1
0x180042c30  movups  [rbp+570h+var_230], xmm1
0x180042c37  mov     [rbp+570h+var_220], rax
0x180042c3e  movups  [rbp+570h+var_1F8], xmm0
0x180042c45  movups  [rbp+570h+var_1E8], xmm0
0x180042c4c  mov     [rbp+570h+var_1D8], rax
0x180042c53  movups  xmmword ptr [rbp+570h+var_398], xmm0
0x180042c5a  mov     [rbp+570h+var_388], rax
0x180042c61  movups  [rbp+570h+var_330], xmm1
0x180042c68  movups  [rbp+570h+var_320], xmm1
0x180042c6f  mov     [rbp+570h+var_310], rax
0x180042c76  movups  [rbp+570h+var_268], xmm0
0x180042c7d  movups  [rbp+570h+var_258], xmm0
0x180042c84  mov     [rbp+570h+var_248], rax
0x180042c8b  mov     [rbp+570h+var_490], rdx
0x180042c92  mov     [rbp+570h+var_468], rdx
0x180042c99  mov     [rbp+570h+var_4A8], edx
0x180042c9f  mov     [rbp+570h+var_470], rdx
0x180042ca6  mov     [rbp+570h+hMem], rdx
0x180042cad  mov     [rbp+570h+var_450], rdx
0x180042cb4  mov     r12d, edx
0x180042cb7  movups  [rbp+570h+var_290], xmm0
0x180042cbe  mov     [rbp+570h+var_280], rax
0x180042cc5  mov     r13b, dl
0x180042cc8  mov     [rbp+570h+var_56F], dl
0x180042ccb  mov     [rbp+570h+var_545], dl
0x180042cce  mov     esi, edx
0x180042cd0  mov     [rbp+570h+var_550], rdx
0x180042cd4  mov     [rbp+570h+var_543], dl
0x180042cd7  mov     qword ptr [rbp+570h+String1.Length], rdx
0x180042cde  mov     [rbp+570h+String1.Buffer], rdx
0x180042ce5  mov     [rbp+570h+var_570], dl
0x180042ce8  mov     dword ptr [rbp+570h+var_4E0], edx
0x180042cee  movups  [rbp+570h+var_380], xmm0
0x180042cf5  movups  [rbp+570h+var_370], xmm0
0x180042cfc  mov     [rbp+570h+var_547], dl
0x180042cff  mov     [rbp+570h+var_518], rdx
0x180042d03  mov     [rbp+570h+var_544], dl
0x180042d06  mov     [rbp+570h+var_560], dl
0x180042d09  mov     [rbp+570h+var_56E], dl
0x180042d0c  mov     [rbp+570h+var_548], dl
0x180042d0f  mov     qword ptr [rbp+570h+SystemTimeAsFileTime.dwLowDateTime], rdx
0x180042d16  mov     qword ptr [rbp+570h+Time], rdx
0x180042d1d  mov     [rbp+570h+var_458], rdx
0x180042d24  mov     [rbp+570h+var_4D4], edx
0x180042d2a  mov     [rbp+570h+var_53C], edx
0x180042d2d  mov     rcx, [rbp+570h+var_408]
0x180042d34  mov     [rbp+570h+var_2A8], rcx
0x180042d3b  mov     rcx, [rbp+570h+var_498]
0x180042d42  mov     [rbp+570h+var_2A0], rcx
0x180042d49  movups  xmmword ptr [rbp+570h+var_480], xmm0
0x180042d50  mov     [rbp+570h+var_70], edx
0x180042d56  mov     [rbp+570h+var_6C], dl
0x180042d5c  test    r14, r14
0x180042d5f  jz      short loc_180042D6E
0x180042d61  mov     rax, r14
0x180042d64  shr     rax, 10h
0x180042d68  movzx   r8d, ax
0x180042d6c  jmp     short loc_180042D71
0x180042d6e  mov     r8, rdx
0x180042d71  mov     rax, [rbp+570h+var_410]
0x180042d78  test    rax, rax
0x180042d7b  jz      short loc_180042D84
0x180042d7d  shr     rax, 10h
0x180042d81  movzx   edx, ax
0x180042d84  lea     rax, [rbx+40h]
0x180042d88  lea     rcx, [rbx+30h]
0x180042d8c  mov     [rsp+600h+var_5C0], r8
0x180042d91  mov     [rsp+600h+var_5C8], rdx
0x180042d96  mov     [rsp+600h+var_5D0], rax
0x180042d9b  mov     [rsp+600h+var_5D8], rcx
0x180042da0  mov     ebx, [rbp+570h+arg_30]
0x180042da6  mov     dword ptr [rsp+600h+var_5E0], ebx
0x180042daa  lea     r9, aKerbgettgstick_5; "KerbGetTgsTicket Flags %#x, Tgt DomainN"...
0x180042db1  mov     r8d, 0FD2h
0x180042db7  lea     rdx, aKerbgettgstick_0; "__KerbGetTgsTicket"
0x180042dbe  mov     ecx, 3
0x180042dc3  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180042dc8  lea     rax, WPP_GLOBAL_Control
0x180042dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180042dd6  cmp     rcx, rax
0x180042dd9  jz      short loc_180042DF9
0x180042ddb  test    byte ptr [rcx+1Ch], 4
0x180042ddf  jz      short loc_180042DF9
0x180042de1  mov     edx, 0Dh
0x180042de6  mov     r9, rdi
0x180042de9  lea     r8, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids
0x180042df0  mov     rcx, [rcx+10h]
0x180042df4  call    WPP_SF__KERB_NAME_
0x180042df9  mov     rax, [rbp+570h+var_3C8]
0x180042e00  xor     edx, edx
0x180042e02  mov     [rax], rdx
0x180042e05  mov     rax, [rbp+570h+var_3C0]
0x180042e0c  mov     [rax], rdx
0x180042e0f  mov     rax, [rbp+570h+var_3B8]
0x180042e16  mov     [rax], edx
0x180042e18  xorps   xmm0, xmm0
0x180042e1b  mov     rax, [rbp+570h+var_3B0]
0x180042e22  movups  xmmword ptr [rax], xmm0
0x180042e25  mov     rax, [rbp+570h+var_3D0]
0x180042e2c  mov     [rax], edx
0x180042e2e  mov     rcx, [rbp+570h+var_418]; struct KERB_KDC_REQUEST_preauth_data_s *
0x180042e35  call    ?KerbGetEndOfPaDataList@@YAPEAUKERB_KDC_REQUEST_preauth_data_s@@PEAU1@@Z; KerbGetEndOfPaDataList(KERB_KDC_REQUEST_preauth_data_s *)
0x180042e3a  mov     [rbp+570h+var_2C8], rax
0x180042e41  cmp     [rbp+570h+arg_40], edx
0x180042e47  jz      short loc_180042E67
0x180042e49  bt      ebx, 9
0x180042e4d  jnb     short loc_180042E67
0x180042e4f  lea     rdx, [rbp+570h+arg_40]
0x180042e56  mov     [rbp+570h+var_4E8], rdx
0x180042e5d  mov     esi, 1
0x180042e62  jmp     loc_180043075
0x180042e67  mov     [rbp+570h+var_4E8], rdx
0x180042e6e  lea     rcx, [rbp+570h+var_4E0]
0x180042e75  call    ?ForLocalMachine@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::ForLocalMachine(Kerb3961PolicyType)
0x180042e7a  nop
0x180042e7b  mov     rcx, [rbp+570h+var_4E0]; this
0x180042e82  test    rcx, rcx
0x180042e85  jz      loc_18004364A
0x180042e8b  lea     rdx, [rbp+570h+var_520]
0x180042e8f  call    ?GetEncryptionAlgorithms@KerberosCryptoPolicy@@QEBA?AV?$unique_ptr@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@U?$default_delete@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@@2@@utl@@W4KeyUsage@Kerb3961@@@Z; KerberosCryptoPolicy::GetEncryptionAlgorithms(Kerb3961::KeyUsage)
0x180042e94  nop
0x180042e95  mov     rbx, [rbp+570h+var_520]
0x180042e99  xor     r9d, r9d
0x180042e9c  test    rbx, rbx
0x180042e9f  jz      loc_18004360C
0x180042ea5  mov     rsi, [rbx+8]
0x180042ea9  sub     rsi, [rbx]
0x180042eac  sar     rsi, 3
0x180042eb0  test    esi, esi
0x180042eb2  jnz     short loc_180042EE0
0x180042eb4  mov     edi, 0C000009Ah
0x180042eb9  lea     rcx, [rbp+570h+var_520]
0x180042ebd  call    ??1?$unique_ptr@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@U?$default_delete@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@@2@@utl@@QEAA@XZ; utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(void)
0x180042ec2  nop
0x180042ec3  lea     rcx, [rbp+570h+var_4E0]
0x180042eca  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180042ecf  mov     rsi, [rbp+570h+var_550]
0x180042ed3  mov     r14b, [rbp+570h+var_56F]
0x180042ed7  mov     r15d, [rbp+570h+var_55C]
0x180042edb  jmp     loc_18004309D
0x180042ee0  mov     eax, esi
0x180042ee2  lea     rdi, ds:0[rax*4]
0x180042eea  mov     r8, r9
0x180042eed  mov     [rbp+570h+var_4E8], r9
0x180042ef4  test    rdi, rdi
0x180042ef7  jz      short loc_180042F74
0x180042ef9  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180042f00  ja      short loc_180042F74
0x180042f02  mov     rcx, cs:g_ulAdditionalProbeSize
0x180042f09  add     rcx, 8
0x180042f0d  add     rcx, rdi
0x180042f10  cmp     rcx, rdi
0x180042f13  jb      short loc_180042F74
0x180042f15  call    VerifyStackAvailable
0x180042f1a  xor     r9d, r9d
0x180042f1d  test    eax, eax
0x180042f1f  jz      short loc_180042F71
0x180042f21  lea     rax, [rdi+8]
0x180042f25  lea     rcx, [rax+0Fh]
0x180042f29  cmp     rcx, rax
0x180042f2c  ja      short loc_180042F38
0x180042f2e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180042f38  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180042f3c  mov     rax, rcx
0x180042f3f  call    _alloca_probe
0x180042f44  sub     rsp, rcx
0x180042f47  lea     r8, [rsp+600h+var_570]
0x180042f4f  mov     [rbp+570h+var_4E8], r8
0x180042f56  test    r8, r8
0x180042f59  jz      short loc_180042F74
0x180042f5b  mov     dword ptr [r8], 6B637453h
0x180042f62  add     r8, 8
0x180042f66  mov     [rbp+570h+var_4E8], r8
0x180042f6d  jnz     short loc_180042FAC
0x180042f6f  jmp     short loc_180042F74
0x180042f71  mov     r8, r9
0x180042f74  lea     rcx, [rdi+8]
0x180042f78  cmp     rcx, rdi
0x180042f7b  jb      short loc_180042FAC
0x180042f7d  mov     rax, cs:g_pfnAllocate
0x180042f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f89  mov     r8, rax
0x180042f8c  mov     [rbp+570h+var_4E8], rax
0x180042f93  xor     r9d, r9d
0x180042f96  test    rax, rax
0x180042f99  jz      short loc_180042FAC
0x180042f9b  mov     dword ptr [rax], 70616548h
0x180042fa1  add     r8, 8
0x180042fa5  mov     [rbp+570h+var_4E8], r8
0x180042fac  test    r8, r8
0x180042faf  jz      loc_180042EB4
0x180042fb5  mov     rdi, r9
0x180042fb8  mov     rax, [rbx+8]
0x180042fbc  sub     rax, [rbx]
0x180042fbf  sar     rax, 3
0x180042fc3  test    rax, rax
0x180042fc6  jz      short loc_18004300E
0x180042fc8  mov     rcx, [rbx]
0x180042fcb  mov     rax, [rbx+8]
0x180042fcf  sub     rax, rcx
0x180042fd2  sar     rax, 3
0x180042fd6  cmp     rdi, rax
0x180042fd9  jb      short loc_180042FDD
0x180042fdb  int     2Ch; Windows NT - assertion failure
0x180042fdd  mov     rcx, [rcx+rdi*8]
0x180042fe1  mov     rax, [rcx]
0x180042fe4  mov     rax, [rax+0D8h]
0x180042feb  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
