# _LsaApLogonUserEx2(void * *,_SECURITY_LOGON_TYPE,void *,void *,ulong,void * *,ulong *,_LUID *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED_EX *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x180011960`
- end: `0x180014a90`
- name: `?_LsaApLogonUserEx2@@YAJPEAPEAXW4_SECURITY_LOGON_TYPE@@PEAX2K0PEAKPEAU_LUID@@PEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@0PEAPEAU_UNICODE_STRING@@77PEAU_SECPKG_PRIMARY_CRED_EX@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `12592`
- prototype: `__int64 __fastcall(void **, enum _SECURITY_LOGON_TYPE, struct _KERB_CERTIFICATE_LOGON *, void *, unsigned int, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED_EX *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `63`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800118b0`

## callees

- `0x1800046f4`
- `0x180007ef0`
- `0x180007fc0`
- `0x18000a600`
- `0x18000ce50`
- `0x18000db68`
- `0x18000e1ec`
- `0x18000f100`
- `0x18000fd50`
- `0x180010320`
- `0x180010460`
- `0x1800104c0`
- `0x180011960`
- `0x1800161dc`
- `0x180016410`
- `0x180016470`
- `0x1800164d0`
- `0x1800165f0`
- `0x1800167d0`
- `0x180016870`
- `0x180018a20`
- `0x18001d010`
- `0x18001d6c0`
- `0x180022f80`
- `0x1800238e4`
- `0x1800243d0`
- `0x180026b10`
- `0x180027a10`
- `0x1800281c0`
- `0x180029650`
- `0x18002b28c`
- `0x18002b350`
- `0x18002be90`
- `0x18002c130`
- `0x18002c3f0`
- `0x18002cc60`
- `0x18002d0a4`
- `0x18002e7d0`
- `0x18002eff0`
- `0x18002f080`
- `0x18002fdec`
- `0x1800322e4`
- `0x180032884`
- `0x180032998`
- `0x180034e20`
- `0x180038dbc`
- `0x180039090`
- `0x180039620`
- `0x180041770`
- `0x180042410`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011fa5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011fa5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001276f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001284d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014984`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001276f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001284d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014984`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014951`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800128f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012926`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800128f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012926`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800128e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012918`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800128e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012918`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800122ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800123da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800122ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800123da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800135c1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800135c1`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001479b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001479b`
- `ntdll!RtlReleaseResource` at `0x1800120c9`
- `ntdll!RtlReleaseResource` at `0x18001210d`
- `ntdll!RtlReleaseResource` at `0x180012284`
- `ntdll!RtlReleaseResource` at `0x180012291`
- `ntdll!RtlReleaseResource` at `0x1800143c7`
- `ntdll!RtlReleaseResource` at `0x1800147dd`
- `ntdll!RtlReleaseResource` at `0x1800148a2`
- `ntdll!RtlReleaseResource` at `0x1800120c9`
- `ntdll!RtlReleaseResource` at `0x18001210d`
- `ntdll!RtlReleaseResource` at `0x180012284`
- `ntdll!RtlReleaseResource` at `0x180012291`
- `ntdll!RtlReleaseResource` at `0x1800143c7`
- `ntdll!RtlReleaseResource` at `0x1800147dd`
- `ntdll!RtlReleaseResource` at `0x1800148a2`
- `ntdll!RtlInitUnicodeString` at `0x180011ffc`
- `ntdll!RtlInitUnicodeString` at `0x18001200c`
- `ntdll!RtlInitUnicodeString` at `0x180011ffc`
- `ntdll!RtlInitUnicodeString` at `0x18001200c`
- `ntdll!RtlAcquireResourceShared` at `0x180011f39`
- `ntdll!RtlAcquireResourceShared` at `0x180011fca`
- `ntdll!RtlAcquireResourceShared` at `0x180011fea`
- `ntdll!RtlAcquireResourceShared` at `0x180012047`
- `ntdll!RtlAcquireResourceShared` at `0x180011f39`
- `ntdll!RtlAcquireResourceShared` at `0x180011fca`
- `ntdll!RtlAcquireResourceShared` at `0x180011fea`
- `ntdll!RtlAcquireResourceShared` at `0x180012047`
- `ntdll!RtlEnterCriticalSection` at `0x180012a70`
- `ntdll!RtlEnterCriticalSection` at `0x180012a70`
- `ntdll!RtlLeaveCriticalSection` at `0x180012b00`
- `ntdll!RtlLeaveCriticalSection` at `0x180012b00`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18001307e`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18001307e`
- `ntdll!NtClose` at `0x180014740`
- `ntdll!NtClose` at `0x180014740`
- `ntdll!RtlCompareUnicodeString` at `0x180012023`
- `ntdll!RtlCompareUnicodeString` at `0x180012023`
- `LSASRV!LsaINotifyNewPassword` at `0x1800140c3`
- `LSASRV!LsaINotifyNewPassword` at `0x1800140c3`
- `LSASRV!LsaISetLogonInfo` at `0x180013487`
- `LSASRV!LsaISetLogonInfo` at `0x180013487`

## string_xrefs

- `0x1800135f2`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180011e28`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180011ea8`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180012143`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001236a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800123b3`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180012992`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180012a33`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180012b0a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800143e6`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001444f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180012a47`: `CreateOrAcquireUserCacheEntry`
- `0x1800141ce`: `SaveCaches`
- `0x18001328e`: `CreateLogonSession`
- `0x1800123c7`: `GetUnlockBufferForDPAPICache`
- `0x180014137`: `EnableCacheNodeFlags`
- `0x180013744`: `RtlStringCchCopyW`
- `0x1800139d4`: `RtlStringCchCopyW`
- `0x180013c62`: `RtlStringCchCopyW`
- `0x180012161`: `Surrogate Plugins not allowed for LsaApLogonUserEx2`
- `0x180012e3e`: `UpdateSAMNames`
- `0x180012efe`: `SetMappedAadAccountSidMap`
- `0x18001306e`: `MakeTokenInformationV2`
- `0x180013317`: `UpdateLogonSessionData(LSDT_LogonUserFlags)`
- `0x1800133ae`: `UpdateLogonSessionData(LSDT_DsNamesFlags)`
- `0x18001341e`: `UpdateLSALogonSessionNames`
- `0x180013e2e`: `GetTokenIfProfileIsLoaded`

## pseudocode

```c
__int64 __fastcall _LsaApLogonUserEx2(
        void **a1,
        enum _SECURITY_LOGON_TYPE a2,
        struct _KERB_CERTIFICATE_LOGON *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7,
        struct _LUID *a8,
        int *a9,
        enum _LSA_TOKEN_INFORMATION_TYPE *a10,
        void **a11,
        struct _UNICODE_STRING **a12,
        struct _UNICODE_STRING **a13,
        struct _UNICODE_STRING **a14,
        struct _SECPKG_PRIMARY_CRED_EX *a15,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a16)
{
  bool v18; // r15
  struct _ApPluginPkg *v19; // r14
  const char *v20; // r12
  unsigned int *v21; // rcx
  LUID *v22; // rdx
  enum _LSA_TOKEN_INFORMATION_TYPE *v23; // r8
  void **v24; // r9
  struct _UNICODE_STRING **v25; // r10
  struct _UNICODE_STRING **v26; // r11
  int LogonCredsFromAuthBuffer; // edi
  const char *v28; // rax
  int v29; // r8d
  bool v30; // al
  const char *v31; // rax
  const char *v32; // rbx
  unsigned int v33; // r14d
  const char *v34; // rax
  __int64 v35; // r10
  const char *v36; // r11
  int v37; // ecx
  WCHAR *v38; // r14
  struct _ApPluginPkg *v39; // rcx
  unsigned int v40; // r15d
  __int64 v41; // rsi
  const WCHAR *v42; // rbx
  LONG v43; // eax
  PRTL_RESOURCE *v44; // rdi
  char *v45; // rbx
  char *v46; // r14
  struct _RTL_BALANCED_NODE *v47; // rbx
  int v48; // eax
  struct _RTL_BALANCED_NODE *v49; // rbx
  int v50; // eax
  struct _ApPluginPkg *v51; // rax
  const char *v52; // rax
  int v53; // eax
  int *v54; // r15
  char v55; // si
  struct _USER_CACHE_ENTRY *v56; // rbx
  _BYTE *v57; // rax
  __int64 v58; // rcx
  int v59; // ebx
  BOOL v60; // edi
  BOOL v61; // esi
  BOOL v62; // r14d
  BOOL v63; // r15d
  BOOL v64; // r12d
  DWORD v65; // eax
  unsigned int v66; // ebx
  PCWSTR v67; // rdi
  const unsigned __int16 *v68; // r8
  unsigned int v69; // eax
  unsigned int UnlockBufferForDPAPICache; // eax
  DWORD CurrentThreadId; // eax
  char *v72; // rax
  int *v73; // rax
  char v74; // bl
  void *v75; // rbx
  char v76; // bl
  void *v77; // rbx
  void *v78; // rbx
  HANDLE ProcessHeap; // rax
  void *v80; // rbx
  HANDLE v81; // rax
  struct CloudAPProvider *v82; // rax
  const char *v83; // rax
  int v84; // r15d
  BOOL v85; // esi
  unsigned int v86; // eax
  struct _USER_CACHE_ENTRY *v87; // rbx
  __int64 v88; // rcx
  __int64 v89; // rax
  __int64 v90; // rax
  int v91; // ebx
  const char *v92; // rax
  PSRWLOCK v93; // rdx
  __int64 v94; // rcx
  PSRWLOCK v95; // rax
  const char *v96; // rdx
  bool v97; // zf
  bool v98; // cl
  struct _ApPluginPkg *v99; // rbx
  unsigned int v100; // eax
  HKEY v101; // rsi
  int v102; // eax
  unsigned int updated; // eax
  unsigned int v104; // eax
  unsigned int v105; // eax
  int v106; // ecx
  int v107; // ebx
  unsigned int v108; // eax
  int v109; // ebx
  const char *v110; // r9
  const char *v111; // rcx
  bool v112; // zf
  unsigned int TokenInformationV2; // eax
  const unsigned __int16 *v114; // r14
  int PrimaryCredentials; // eax
  struct _ApPluginPkg *v116; // rdi
  unsigned int SupplementalCredentials; // eax
  const char *v118; // r9
  const char *v119; // rdx
  bool v120; // zf
  int v121; // ebx
  char v122; // r9
  unsigned int v123; // eax
  unsigned int v124; // eax
  unsigned int v125; // eax
  const char *v126; // r9
  const char *v127; // rdx
  bool v128; // zf
  unsigned int v129; // eax
  int v130; // eax
  unsigned int v131; // eax
  __int64 v132; // rdx
  __int64 v133; // rcx
  const unsigned __int16 *v134; // rdi
  __int64 v135; // r14
  const UCHAR *v136; // rbx
  const UCHAR *v137; // rcx
  __int64 v138; // rdx
  __int64 v139; // r8
  __int64 v140; // rax
  unsigned __int64 v141; // rcx
  unsigned __int16 v142; // ax
  unsigned __int16 *v143; // rax
  const UCHAR *v144; // r9
  const UCHAR *v145; // rcx
  bool v146; // zf
  int v147; // eax
  const char *v148; // r11
  unsigned int v149; // eax
  union _LARGE_INTEGER *v150; // r15
  const char *v151; // rdx
  __int64 v152; // r14
  const UCHAR *v153; // rcx
  bool v154; // zf
  const unsigned __int16 *v155; // rdi
  __int64 v156; // rax
  unsigned __int64 v157; // rcx
  unsigned __int16 *v158; // rax
  const UCHAR *v159; // r9
  const UCHAR *v160; // rcx
  __int64 v161; // r8
  bool v162; // zf
  int v163; // eax
  const char *v164; // r11
  unsigned int v165; // eax
  union _LARGE_INTEGER *v166; // r15
  const char *v167; // rdx
  __int64 v168; // r15
  const UCHAR *v169; // rcx
  bool v170; // zf
  __int64 v171; // rax
  unsigned __int64 v172; // rax
  unsigned __int16 *v173; // rax
  const UCHAR *v174; // rcx
  unsigned int v175; // r11d
  bool v176; // zf
  const char *v177; // r9
  int v178; // eax
  unsigned int v179; // eax
  const char *v180; // rdx
  int v181; // eax
  unsigned int IsLoaded; // eax
  unsigned int v183; // eax
  int v184; // eax
  const char *v185; // r9
  const char *v186; // rcx
  bool v187; // zf
  const char *v188; // rdx
  unsigned int v189; // eax
  const char *v190; // rdx
  unsigned int v191; // ebx
  unsigned int v192; // eax
  const char *v193; // r9
  const char *v194; // rdx
  bool v195; // zf
  unsigned int v196; // eax
  struct _SECPKG_PRIMARY_CRED_EX *v197; // rax
  const WCHAR *v198; // rdx
  const char *v199; // r9
  const char *v200; // rcx
  bool v201; // zf
  const char *v202; // r9
  const char *v203; // rcx
  bool v204; // zf
  _BYTE *v205; // rcx
  __int64 v206; // rax
  _BYTE *v207; // rcx
  __int64 v208; // rax
  struct _UNICODE_STRING *v209; // rdi
  struct _UNICODE_STRING *v210; // rdi
  __int64 v211; // rdi
  unsigned __int8 *v212; // rax
  unsigned __int64 i; // rcx
  struct _LOGON_SESSION *v214; // rdi
  const char *v215; // r9
  const char *v216; // rcx
  bool v217; // zf
  const char *v218; // rcx
  bool v219; // zf
  struct _LOGON_SESSION *v220; // rax
  struct _LOGON_SESSION **v221; // rdx
  struct _USER_CACHE_ENTRY *v222; // rax
  RTL_SRWLOCK *v223; // rdi
  char v224; // si
  int *v225; // rcx
  int v226; // eax
  __int64 v227; // rdx
  int v228; // eax
  ULONG UserDataCount[2]; // [rsp+20h] [rbp-110h]
  ULONG UserDataCounta[2]; // [rsp+20h] [rbp-110h]
  ULONG UserDataCountb[2]; // [rsp+20h] [rbp-110h]
  ULONG UserDataCountc[2]; // [rsp+20h] [rbp-110h]
  const char *UserData; // [rsp+28h] [rbp-108h]
  int v235; // [rsp+58h] [rbp-D8h]
  int v236; // [rsp+68h] [rbp-C8h]
  unsigned __int8 v237; // [rsp+B0h] [rbp-80h]
  int v238; // [rsp+B4h] [rbp-7Ch]
  bool v239; // [rsp+B8h] [rbp-78h] BYREF
  char v240; // [rsp+B9h] [rbp-77h]
  bool v241; // [rsp+BAh] [rbp-76h] BYREF
  char v242; // [rsp+BBh] [rbp-75h]
  bool v243; // [rsp+BCh] [rbp-74h] BYREF
  bool v244; // [rsp+BDh] [rbp-73h] BYREF
  bool v245; // [rsp+BEh] [rbp-72h] BYREF
  bool v246; // [rsp+BFh] [rbp-71h] BYREF
  struct _USER_CACHE_ENTRY *v247; // [rsp+C0h] [rbp-70h] BYREF
  bool v248; // [rsp+C8h] [rbp-68h] BYREF
  bool v249; // [rsp+C9h] [rbp-67h] BYREF
  bool v250; // [rsp+CAh] [rbp-66h] BYREF
  bool v251; // [rsp+CBh] [rbp-65h]
  char v252; // [rsp+CCh] [rbp-64h]
  char v253; // [rsp+CDh] [rbp-63h]
  struct _ApPluginPkg *v254; // [rsp+D0h] [rbp-60h]
  LUID LocallyUniqueId; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v256; // [rsp+E0h] [rbp-50h] BYREF
  struct _APPLUGIN_USER_INFO *v257; // [rsp+E8h] [rbp-48h] BYREF
  void *Buf1[2]; // [rsp+F0h] [rbp-40h] BYREF
  enum _SECURITY_LOGON_TYPE v259; // [rsp+100h] [rbp-30h]
  PSRWLOCK SRWLock; // [rsp+108h] [rbp-28h] BYREF
  PCWSTR SourceString; // [rsp+110h] [rbp-20h] BYREF
  PCWSTR v262; // [rsp+118h] [rbp-18h]
  HLOCAL hMem; // [rsp+120h] [rbp-10h] BYREF
  unsigned int v264; // [rsp+128h] [rbp-8h] BYREF
  union _LARGE_INTEGER *v265; // [rsp+130h] [rbp+0h]
  int v266; // [rsp+138h] [rbp+8h] BYREF
  int *v267; // [rsp+140h] [rbp+10h]
  struct _UNICODE_STRING *v268; // [rsp+148h] [rbp+18h]
  struct _UNICODE_STRING *v269; // [rsp+150h] [rbp+20h]
  __int64 v270; // [rsp+158h] [rbp+28h]
  void *v271; // [rsp+160h] [rbp+30h] BYREF
  unsigned __int8 *v272; // [rsp+168h] [rbp+38h] BYREF
  struct _SCARD_PIN *v273; // [rsp+170h] [rbp+40h] BYREF
  struct _LSA_TOKEN_INFORMATION_V1 *v274; // [rsp+178h] [rbp+48h] BYREF
  __int128 v275; // [rsp+180h] [rbp+50h] BYREF
  unsigned __int16 *v276[2]; // [rsp+190h] [rbp+60h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v277; // [rsp+1A0h] [rbp+70h]
  HANDLE TokenHandle; // [rsp+1A8h] [rbp+78h] BYREF
  struct _UNICODE_STRING **v279; // [rsp+1B0h] [rbp+80h]
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v280; // [rsp+1B8h] [rbp+88h]
  struct _LOGON_SESSION *v281; // [rsp+1C0h] [rbp+90h] BYREF
  struct _ApPluginSubPkg *v282; // [rsp+1C8h] [rbp+98h] BYREF
  void **v283; // [rsp+1D0h] [rbp+A0h]
  HANDLE Handle; // [rsp+1D8h] [rbp+A8h]
  unsigned __int16 *v285; // [rsp+1E0h] [rbp+B0h] BYREF
  int v286; // [rsp+1E8h] [rbp+B8h] BYREF
  __int128 v287; // [rsp+1F0h] [rbp+C0h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v288; // [rsp+200h] [rbp+D0h]
  LUID *v289; // [rsp+208h] [rbp+D8h]
  enum _LSA_TOKEN_INFORMATION_TYPE *v290; // [rsp+210h] [rbp+E0h]
  void **v291; // [rsp+218h] [rbp+E8h]
  struct _UNICODE_STRING **v292; // [rsp+220h] [rbp+F0h]
  struct _UNICODE_STRING **v293; // [rsp+228h] [rbp+F8h]
  void **v294; // [rsp+230h] [rbp+100h]
  unsigned int *v295; // [rsp+238h] [rbp+108h]
  unsigned __int64 v296; // [rsp+240h] [rbp+110h] BYREF
  __int128 v297; // [rsp+248h] [rbp+118h] BYREF
  __int128 v298; // [rsp+258h] [rbp+128h] BYREF
  struct _SECPKG_PRIMARY_CRED_EX *v299; // [rsp+268h] [rbp+138h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+270h] [rbp+140h] BYREF
  __int128 v301; // [rsp+280h] [rbp+150h] BYREF
  __int64 v302; // [rsp+290h] [rbp+160h]
  UNICODE_STRING String2; // [rsp+298h] [rbp+168h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+2A8h] [rbp+178h] BYREF
  _BYTE v305[208]; // [rsp+2C0h] [rbp+190h] BYREF
  __int128 v306; // [rsp+390h] [rbp+260h]
  __int128 v307; // [rsp+3A0h] [rbp+270h] BYREF
  __int128 v308; // [rsp+3B0h] [rbp+280h] BYREF
  __int128 v309; // [rsp+3C0h] [rbp+290h]
  __int128 v310; // [rsp+3D0h] [rbp+2A0h] BYREF
  LPVOID v311[2]; // [rsp+3E0h] [rbp+2B0h]
  _BYTE v312[152]; // [rsp+3F0h] [rbp+2C0h] BYREF
  __int64 v313; // [rsp+488h] [rbp+358h]
  LPVOID lpMem[2]; // [rsp+490h] [rbp+360h]
  int v315; // [rsp+4A0h] [rbp+370h]
  __int64 v316; // [rsp+4A8h] [rbp+378h]
  _DWORD *v317; // [rsp+4B0h] [rbp+380h]
  void *v318; // [rsp+4B8h] [rbp+388h] BYREF
  _QWORD v319[3]; // [rsp+4C0h] [rbp+390h] BYREF
  int v320; // [rsp+4D8h] [rbp+3A8h]
  __int128 *v321; // [rsp+4E0h] [rbp+3B0h]
  char v322; // [rsp+4E8h] [rbp+3B8h]
  void **v323; // [rsp+4F0h] [rbp+3C0h] BYREF
  int v324; // [rsp+4F8h] [rbp+3C8h] BYREF
  char v325; // [rsp+4FCh] [rbp+3CCh]
  __int128 v326; // [rsp+500h] [rbp+3D0h]
  __int128 v327; // [rsp+510h] [rbp+3E0h]
  int v328; // [rsp+520h] [rbp+3F0h] BYREF
  const char *v329; // [rsp+528h] [rbp+3F8h]
  LPVOID v330; // [rsp+530h] [rbp+400h]
  char v331; // [rsp+538h] [rbp+408h]
  int v332; // [rsp+540h] [rbp+410h]
  __int128 v333; // [rsp+548h] [rbp+418h]
  __int128 v334; // [rsp+558h] [rbp+428h]
  __int128 v335; // [rsp+568h] [rbp+438h]
  __int128 v336; // [rsp+578h] [rbp+448h]
  __int128 v337; // [rsp+588h] [rbp+458h]
  __int128 v338; // [rsp+598h] [rbp+468h]
  __int128 v339; // [rsp+5A8h] [rbp+478h]
  __int128 v340; // [rsp+5B8h] [rbp+488h]
  __int128 v341; // [rsp+5C8h] [rbp+498h]
  __int64 v342; // [rsp+5D8h] [rbp+4A8h]
  __int128 v343; // [rsp+5E0h] [rbp+4B0h] BYREF
  int v344; // [rsp+5F0h] [rbp+4C0h]
  __int64 v345; // [rsp+5F8h] [rbp+4C8h]
  int *v346; // [rsp+600h] [rbp+4D0h]
  RTL_SRWLOCK *v347; // [rsp+608h] [rbp+4D8h] BYREF
  _QWORD v348[3]; // [rsp+610h] [rbp+4E0h] BYREF
  int v349; // [rsp+628h] [rbp+4F8h]
  int *v350; // [rsp+630h] [rbp+500h]
  char v351; // [rsp+638h] [rbp+508h]
  void **v352; // [rsp+640h] [rbp+510h] BYREF
  char v353[264]; // [rsp+648h] [rbp+518h] BYREF
  _DWORD *v354; // [rsp+750h] [rbp+620h]
  void *v355; // [rsp+758h] [rbp+628h] BYREF
  char v356[24]; // [rsp+760h] [rbp+630h] BYREF
  int v357; // [rsp+778h] [rbp+648h]
  struct _EVENT_DATA_DESCRIPTOR v358; // [rsp+790h] [rbp+660h] BYREF
  __int16 *v359; // [rsp+7A0h] [rbp+670h]
  int v360; // [rsp+7A8h] [rbp+678h]
  int v361; // [rsp+7ACh] [rbp+67Ch]
  __int64 *v362; // [rsp+7B0h] [rbp+680h]
  __int64 v363; // [rsp+7B8h] [rbp+688h]

  v259 = a2;
  v283 = a1;
  v294 = a6;
  v295 = a7;
  v289 = a8;
  v267 = a9;
  v290 = a10;
  v291 = a11;
  v292 = a12;
  v293 = a13;
  v279 = a14;
  v299 = a15;
  v280 = a16;
  v242 = 0;
  v239 = 0;
  v252 = 0;
  v253 = 0;
  v18 = 0;
  v237 = 0;
  LocallyUniqueId = 0;
  v301 = 0;
  v302 = 0;
  v298 = 0;
  v241 = 0;
  v243 = 0;
  v246 = 0;
  v245 = 0;
  v244 = 0;
  v264 = 0;
  v286 = 0x8000;
  v266 = 1;
  v296 = 0;
  v250 = 0;
  v249 = 0;
  v275 = 0;
  v297 = 0;
  v287 = 0;
  v288 = 0;
  *(_OWORD *)v276 = 0;
  v277 = 0;
  *(_OWORD *)Buf1 = 0;
  v262 = 0;
  SourceString = 0;
  v19 = 0;
  v254 = 0;
  v282 = 0;
  v247 = 0;
  v257 = 0;
  hMem = 0;
  v274 = 0;
  *(_DWORD *)v305 = 0;
  memset_0(&v305[4], 0, 0xDCu);
  v268 = 0;
  v269 = 0;
  v270 = 0;
  v271 = 0;
  v265 = 0;
  v256 = 0;
  Handle = 0;
  TokenHandle = 0;
  v281 = 0;
  v272 = 0;
  v285 = 0;
  v273 = 0;
  v324 = 0;
  v325 = 0;
  v331 = 0;
  v328 = 0;
  v329 = "CloudApLogonUser";
  v330 = 0;
  v332 = 0;
  v343 = 0;
  v333 = 0;
  v334 = 0;
  v335 = 0;
  v336 = 0;
  v337 = 0;
  v338 = 0;
  v339 = 0;
  v340 = 0;
  v341 = 0;
  v342 = 0;
  v344 = 1;
  v345 = 0;
  v346 = &v324;
  v347 = 0;
  v348[0] = 0;
  v348[1] = &v323;
  v348[2] = 0;
  v349 = 0;
  v350 = &v328;
  v351 = 0;
  v323 = &CloudAPProvider::CloudApLogonUser::`vftable';
  v20 = "";
  if ( !a3
    || !a5
    || !v294
    || (v21 = v295) == 0
    || (v22 = v289) == 0
    || !v267
    || (v23 = v290) == 0
    || (v24 = v291) == 0
    || (v25 = v292) == 0
    || (v26 = v293) == 0
    || !v279
    || !a15
    || !v280 )
  {
    LogonCredsFromAuthBuffer = -1073741811;
    v238 = -1073741811;
    v202 = "";
    do
    {
      v203 = v202--;
      v204 = *v202 == 92;
      if ( *v202 == 92 )
        goto LABEL_516;
    }
    while ( v202 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
    v204 = *v202 == 92;
LABEL_516:
    if ( v204 )
      v202 = v203;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v202, 7074, "Invalid Arg(s)", &Class);
LABEL_65:
    v53 = LogonCredsFromAuthBuffer;
    goto LABEL_66;
  }
  *v294 = 0;
  *v21 = 0;
  *v22 = 0;
  *v267 = 0;
  *v23 = LsaTokenInformationNull;
  *v24 = 0;
  *v25 = 0;
  *v26 = 0;
  *v279 = 0;
  memset_0(&v307, 0, 0xE0u);
  *(_OWORD *)&a15->LogonId.LowPart = v307;
  *(_OWORD *)&a15->DownlevelName.Buffer = v308;
  *(_OWORD *)&a15->DomainName.Buffer = v309;
  *(_OWORD *)&a15->Password.Buffer = v310;
  *(_OWORD *)&a15->OldPassword.Buffer = *(_OWORD *)v311;
  *(_OWORD *)&a15->Flags = *(_OWORD *)v312;
  *(_OWORD *)&a15->DnsDomainName.Buffer = *(_OWORD *)&v312[16];
  *(_OWORD *)&a15->Upn.Buffer = *(_OWORD *)&v312[32];
  *(_OWORD *)&a15->LogonServer.Buffer = *(_OWORD *)&v312[48];
  *(_OWORD *)&a15->Spare1.Buffer = *(_OWORD *)&v312[64];
  *(_OWORD *)&a15->Spare2.Buffer = *(_OWORD *)&v312[80];
  *(_OWORD *)&a15->Spare3.Buffer = *(_OWORD *)&v312[96];
  *(_OWORD *)&a15->Spare4.Buffer = *(_OWORD *)&v312[112];
  *(_OWORD *)&a15->PrevLogonId.LowPart = *(_OWORD *)&v312[128];
  *v280 = 0;
  if ( v259 == NetworkCleartext )
  {
LABEL_19:
    v240 = 1;
    v30 = 0;
  }
  else
  {
    if ( v259 != CachedUnlock )
    {
      switch ( v259 )
      {
        case Interactive:
        case Network:
        case Batch:
        case Service:
        case RemoteInteractive:
          goto LABEL_19;
        case CachedInteractive:
        case CachedRemoteInteractive:
          break;
        default:
          LogonCredsFromAuthBuffer = -1073741557;
          v238 = -1073741557;
          v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", -1073741557, v28, 7109, "Unsupported Logon Type", v29);
          goto LABEL_65;
      }
    }
    v240 = 0;
    v30 = 1;
  }
  v251 = 0;
  v239 = v30;
  LogonCredsFromAuthBuffer = GetLogonCredsFromAuthBuffer(
                               a3,
                               a5,
                               a4,
                               (struct _DECRYPTED_AUTH_DATA *)&v287,
                               (unsigned __int16 **)&SourceString);
  v238 = LogonCredsFromAuthBuffer;
  if ( LogonCredsFromAuthBuffer < 0 )
  {
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v32 = "GetLogonCredsFromAuthBuffer";
    UserDataCounta[0] = 7121;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      (unsigned int)LogonCredsFromAuthBuffer,
      v31,
      *(_QWORD *)UserDataCounta,
      "GetLogonCredsFromAuthBuffer",
      &Class);
    if ( LogonCredsFromAuthBuffer != -1073741801 )
    {
      if ( LogonCredsFromAuthBuffer != -1073741670 )
        LogonCredsFromAuthBuffer = -1073741811;
      v238 = LogonCredsFromAuthBuffer;
    }
    v33 = LogonCredsFromAuthBuffer;
    v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v37 = 7128;
    v262 = SourceString;
    goto LABEL_497;
  }
  RtlAcquireResourceShared(&g_PackageListLock, 1u);
  v38 = (WCHAR *)SourceString;
  v262 = SourceString;
  v39 = g_pPlugins;
  if ( !g_pPlugins || (v40 = 0, !g_cPlugins) )
  {
LABEL_503:
    v254 = 0;
    RtlReleaseResource(&g_PackageListLock);
    LogonCredsFromAuthBuffer = -2146893039;
    v238 = -2146893039;
    v198 = &Class;
    if ( v38 )
      v198 = v38;
    v199 = "";
    while ( 1 )
    {
      v200 = v199--;
      v201 = *v199 == 92;
      if ( *v199 == 92 )
        break;
      if ( v199 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v201 = *v199 == 92;
        break;
      }
    }
    if ( v201 )
      v199 = v200;
    UserDataCounta[0] = 7133;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      2148074257LL,
      v199,
      *(_QWORD *)UserDataCounta,
      "RefPackageByProvName",
      v198);
    goto LABEL_64;
  }
  while ( 1 )
  {
    v41 = 392LL * v40;
    v42 = (const WCHAR *)((char *)v39 + v41 + 24);
    DestinationString = 0;
    String2 = 0;
    if ( (g_ulTestFlags & 2) != 0 )
    {
      v43 = _o__wcsicmp(v38, (char *)v39 + v41 + 24);
      goto LABEL_36;
    }
    if ( !v38 )
    {
      if ( !v42 )
        goto LABEL_61;
      v44 = (PRTL_RESOURCE *)((char *)v39 + v41 + 360);
      RtlAcquireResourceShared(*v44, 1u);
      goto LABEL_54;
    }
    if ( !v42 )
      break;
    RtlInitUnicodeString(&DestinationString, v38);
    RtlInitUnicodeString(&String2, v42);
    v43 = RtlCompareUnicodeString(&DestinationString, &String2, 1u);
LABEL_36:
    if ( !v43 )
    {
      v39 = g_pPlugins;
LABEL_61:
      v51 = (struct _ApPluginPkg *)((char *)v39 + v41);
      goto LABEL_62;
    }
    v45 = (char *)g_pPlugins + v41;
    v44 = (PRTL_RESOURCE *)((char *)g_pPlugins + v41 + 360);
    RtlAcquireResourceShared(*v44, 1u);
    if ( v38 )
      goto LABEL_38;
LABEL_54:
    RtlReleaseResource(*v44);
    if ( ++v40 >= g_cPlugins )
      goto LABEL_503;
    v39 = g_pPlugins;
  }
  v45 = (char *)v39 + v41;
  v44 = (PRTL_RESOURCE *)((char *)v39 + v41 + 360);
  RtlAcquireResourceShared(*v44, 1u);
LABEL_38:
  v46 = v45;
  v47 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)v45 + 47);
  if ( !v47 )
  {
LABEL_46:
    v49 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)v46 + 48);
    v38 = (WCHAR *)v262;
    if ( v49 )
    {
      while ( 1 )
      {
        v50 = SubPkgTable_CompareDnsNames(v38, v49);
        if ( v50 >= 0 )
        {
          if ( v50 <= 0 )
          {
            if ( v49 != (struct _RTL_BALANCED_NODE *)24 )
              goto LABEL_57;
            goto LABEL_59;
          }
          v49 = v49->Children[1];
        }
        else
        {
          v49 = v49->Children[0];
        }
        if ( !v49 )
          goto LABEL_54;
      }
    }
    goto LABEL_54;
  }
  while ( 1 )
  {
    v48 = SubPkgTable_CompareNames(v262, v47);
    if ( v48 >= 0 )
      break;
    v47 = v47->Children[0];
LABEL_43:
    if ( !v47 )
      goto LABEL_46;
  }
  if ( v48 > 0 )
  {
    v47 = v47->Children[1];
    goto LABEL_43;
  }
  v38 = (WCHAR *)v262;
LABEL_57:
  if ( (struct _ApPluginPkg *)((char *)g_pPlugins + v41) )
    RtlReleaseResource(*(PRTL_RESOURCE *)((char *)g_pPlugins + v41 + 360));
LABEL_59:
  v51 = (struct _ApPluginPkg *)((char *)g_pPlugins + v41);
LABEL_62:
  v254 = v51;
  if ( (*((_BYTE *)v51 + 160) & 4) != 0 )
  {
    LogonCredsFromAuthBuffer = -2146893039;
    v238 = -2146893039;
    v52 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    UserDataCounta[0] = 7138;
    WPPTraceLogA(
      2,
      "0x%08x %s:%u : %s:%ws",
      2148074257LL,
      v52,
      *(_QWORD *)UserDataCounta,
      "Surrogate Plugins not allowed for LsaApLogonUserEx2",
      &Class);
    goto LABEL_64;
  }
  v68 = v38;
  v19 = v254;
  v69 = ConvertAuthDataToAuthDataInt(
          1,
          v254,
          v68,
          (struct _DECRYPTED_AUTH_DATA *)&v287,
          (struct _DECRYPTED_AUTH_DATA *)v276,
          &v285,
          &v273);
  LogonCredsFromAuthBuffer = v69;
  v238 = v69;
  if ( v69 )
  {
    v33 = v69;
    v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v37 = 7153;
    v32 = "ConvertAuthDataToAuthDataInt";
    v18 = 0;
    goto LABEL_497;
  }
  UnlockBufferForDPAPICache = GetUnlockBufferForDPAPICache(
                                v254,
                                (struct _DECRYPTED_AUTH_DATA *)v276,
                                (struct _DPAPI_DECODED_AUTH_DATA *)Buf1);
  LogonCredsFromAuthBuffer = UnlockBufferForDPAPICache;
  v238 = UnlockBufferForDPAPICache;
  if ( UnlockBufferForDPAPICache )
  {
    v33 = UnlockBufferForDPAPICache;
    v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v37 = 7159;
    v32 = "GetUnlockBufferForDPAPICache";
    v18 = 0;
    goto LABEL_497;
  }
  v242 = 1;
  CurrentThreadId = GetCurrentThreadId();
  DWORD2(v307) = 0;
  BYTE12(v307) = 0;
  LOBYTE(v311[1]) = 0;
  LODWORD(v310) = 0;
  *((_QWORD *)&v310 + 1) = "CloudApLogonUser";
  v311[0] = 0;
  *(_DWORD *)v312 = 0;
  *(_OWORD *)lpMem = 0;
  memset(&v312[8], 0, 144);
  v313 = 0;
  v315 = 1;
  v316 = 0;
  v317 = (_DWORD *)&v307 + 2;
  v318 = 0;
  v319[0] = 0;
  v319[1] = &v307;
  v319[2] = 0;
  v320 = 0;
  v321 = &v310;
  v322 = 0;
  *(_QWORD *)&v307 = &CloudAPProvider::CloudApLogonUser::`vftable';
  CloudAPProvider::CloudApLogonUser::StartActivity((CloudAPProvider::CloudApLogonUser *)&v307, CurrentThreadId, v259);
  wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v352,
    &v323);
  v352 = &CloudAPProvider::CloudApLogonUser::`vftable';
  v324 = DWORD2(v307);
  v325 = BYTE12(v307);
  v326 = v308;
  v327 = v309;
  DWORD2(v307) = 0;
  BYTE12(v307) = 0;
  v328 = v310;
  v329 = (const char *)*((_QWORD *)&v310 + 1);
  wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)&v328);
  v330 = v311[0];
  v311[0] = 0;
  v331 = (char)v311[1];
  LOBYTE(v311[1]) = 0;
  v332 = *(_DWORD *)v312;
  v333 = *(_OWORD *)&v312[8];
  v334 = *(_OWORD *)&v312[24];
  v335 = *(_OWORD *)&v312[40];
  v336 = *(_OWORD *)&v312[56];
  v337 = *(_OWORD *)&v312[72];
  v338 = *(_OWORD *)&v312[88];
  v339 = *(_OWORD *)&v312[104];
  v340 = *(_OWORD *)&v312[120];
  v341 = *(_OWORD *)&v312[136];
  v342 = v313;
  wil::details::shared_buffer::reset((wil::details::shared_buffer *)&v343);
  v343 = *(_OWORD *)lpMem;
  *(_OWORD *)lpMem = 0;
  v344 = v315;
  wil::details::shared_object<wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v347);
  v72 = (char *)v318;
  v347 = (RTL_SRWLOCK *)v318;
  v318 = 0;
  if ( v347 )
    v73 = (int *)(v72 + 8);
  else
    v73 = &v324;
  v346 = v73;
  v350 = v73 + 10;
  if ( v320 )
  {
    if ( !v349 )
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v348);
  }
  else if ( v349 )
  {
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v348);
  }
  v317 = (_DWORD *)&v307 + 2;
  if ( v320 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v319);
  v352 = &CloudAPProvider::CloudApLogonUser::`vftable';
  if ( !v355 )
    goto LABEL_109;
  wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &v352,
    &SRWLock);
  if ( v355 && *(_DWORD *)v355 == 1 )
  {
    v74 = 1;
  }
  else
  {
    v74 = 0;
    wil::details::shared_object<wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v355);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v74 )
  {
LABEL_109:
    if ( *v354 == 1 )
    {
      wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException();
      wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v352);
    }
  }
  if ( v357 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v356);
  if ( v355 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v355, 0xFFFFFFFF) == 1 )
    {
      v75 = v355;
      if ( v355 )
      {
        wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>((char *)v355 + 8);
        operator delete(v75, (const struct std::nothrow_t *)0x110);
      }
    }
    v355 = 0;
  }
  wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>(v353);
  *(_QWORD *)&v307 = &CloudAPProvider::CloudApLogonUser::`vftable';
  if ( !v318 )
    goto LABEL_126;
  wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &v307,
    &SRWLock);
  if ( v318 && *(_DWORD *)v318 == 1 )
  {
    v76 = 1;
  }
  else
  {
    v76 = 0;
    wil::details::shared_object<wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v318);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v76 )
  {
LABEL_126:
    if ( *v317 == 1 )
    {
      wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException();
      wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v307);
    }
  }
  if ( v320 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v319);
  if ( v318 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v318, 0xFFFFFFFF) == 1 )
    {
      v77 = v318;
      if ( v318 )
      {
        wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>((char *)v318 + 8);
        operator delete(v77, (const struct std::nothrow_t *)0x110);
      }
    }
    v318 = 0;
  }
  if ( lpMem[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem[0], 0xFFFFFFFF) == 1 )
    {
      v78 = lpMem[0];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v78);
    }
    *(_OWORD *)lpMem = 0;
  }
  if ( LOBYTE(v311[1]) )
  {
    v80 = v311[0];
    v81 = GetProcessHeap();
    HeapFree(v81, 0, v80);
    LOBYTE(v311[1]) = 0;
  }
  v311[0] = 0;
  if ( DWORD2(v307) == 1 )
  {
    DWORD2(v307) = 2;
    v82 = CloudAPProvider::Instance();
    _tlgWriteActivityAutoStop<70368744177664,5>(*((unsigned int **)v82 + 1), (__int64)&v308);
  }
  DWORD2(v307) = 3;
  if ( !((unsigned __int8 (__fastcall *)(__int128 *))g_pLsaFunctionTable->GetCallInfo)(&v301) )
  {
    LogonCredsFromAuthBuffer = -1073741595;
    v238 = -1073741595;
    v83 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    UserDataCount[0] = 7171;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v83, *(_QWORD *)UserDataCount, "GetCallInfo", &Class);
    goto LABEL_65;
  }
  v84 = WORD4(v301) & 0x800;
  v237 = v84 != 0;
  v85 = (DWORD2(v301) & 0x41800) != 0;
  v86 = _CreateOrAcquireUserCacheEntry(v85, (struct _GUID *)((char *)v254 + 68), v285, 0, &v247);
  LogonCredsFromAuthBuffer = v86;
  v238 = v86;
  if ( v86 )
  {
    v33 = v86;
    v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v37 = 7190;
    v32 = "CreateOrAcquireUserCacheEntry";
    v18 = v84 != 0;
    goto LABEL_497;
  }
  v237 = v84 != 0;
  v87 = v247;
  SCLockAcquireResourceExclusive((PRTL_RESOURCE)(*((_QWORD *)v247 + 3) + 24LL));
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v87 + 32));
  if ( !*((_DWORD *)v87 + 19) )
  {
    v88 = *((_QWORD *)v87 + 36);
    if ( v88 )
      ((void (__fastcall *)(__int64, _QWORD))g_pLsaFunctionTable->LsaUnprotectMemory)(v88, *((unsigned int *)v87 + 70));
    v89 = *((_QWORD *)v87 + 33);
    if ( v89 && *(_DWORD *)(v89 + 12) )
      ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaUnprotectMemory)(v89 + *(unsigned int *)(v89 + 8));
    v90 = *((_QWORD *)v87 + 34);
    if ( v90 && *(_DWORD *)(v90 + 12) )
      ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaUnprotectMemory)(v90 + *(unsigned int *)(v90 + 8));
  }
  ++*((_DWORD *)v87 + 19);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v87 + 32));
  v252 = 1;
  if ( (WORD4(v301) & 0x200) == 0 )
    goto LABEL_174;
  LODWORD(SourceString) = 0;
  SRWLock = 0;
  v91 = (int)Buf1[0];
  if ( Buf1[0] != (void *)0x5800000001LL || memcmp_0(Buf1[1], L"_TBAL_{68EDDCF5-0AEB-4C28-A770-AF5302ECA3C9}", 0x58u) )
  {
LABEL_175:
    v98 = 0;
    v251 = v91 == 3;
    if ( v259 != Service )
      goto LABEL_182;
    if ( (*((_BYTE *)v254 + 160) & 1) != 0 )
    {
      v240 = 0;
      v98 = 1;
    }
    else
    {
      if ( v91 != 3 || !g_bAutoProvisionTBAL )
      {
LABEL_182:
        v99 = v254;
        v100 = LogonCloudUser(
                 v259,
                 v254,
                 v85,
                 &v247,
                 (struct _DECRYPTED_AUTH_DATA *)v276,
                 Buf1,
                 v98,
                 v273,
                 0,
                 &v239,
                 (struct _CloudAPCache **)&hMem,
                 &v241,
                 &v243,
                 &v246,
                 &v245,
                 &v244,
                 &v249,
                 &v257,
                 &v282,
                 (struct _AP_BLOB *)&v275,
                 (struct _tagCacheNodeIdentifier *)&v297,
                 0);
        LogonCredsFromAuthBuffer = v100;
        v238 = v100;
        if ( v100 )
        {
          v33 = v100;
          v34 = "";
          do
            v96 = v34--;
          while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
          v35 = 0;
          v97 = *v34 == 92;
          v37 = 7250;
          v32 = "LogonCloudUser";
          goto LABEL_493;
        }
        if ( v282 )
        {
          SRWLock = (PSRWLOCK)((char *)v282 + 48);
          v101 = (HKEY)*((_QWORD *)v282 + 74);
        }
        else
        {
          SRWLock = (PSRWLOCK)((char *)v99 + 24);
          v101 = (HKEY)*((_QWORD *)v99 + 44);
        }
        v102 = *((_DWORD *)v99 + 40);
        if ( (v102 & 1) != 0 )
        {
          v19 = v99;
          updated = UpdateSAMNames(v99, v247, v257);
          LogonCredsFromAuthBuffer = updated;
          v238 = updated;
          if ( updated )
          {
            v33 = updated;
            v34 = "";
            do
              v96 = v34--;
            while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
            v35 = 0;
            v97 = *v34 == 92;
            v37 = 7279;
            v32 = "UpdateSAMNames";
            goto LABEL_493;
          }
          v104 = PostLogonProcessingForShadowAccounts(v99, v247, v257, (struct _DPAPI_DECODED_AUTH_DATA *)Buf1, v239);
          LogonCredsFromAuthBuffer = v104;
          v238 = v104;
          if ( v104 )
          {
            v33 = v104;
            v34 = "";
            do
              v96 = v34--;
            while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
            v35 = 0;
            v97 = *v34 == 92;
            v37 = 7288;
            v32 = "PostLogonProcessingForShadowAccounts";
            goto LABEL_493;
          }
        }
        else
        {
          if ( (v102 & 0x80u) != 0 )
          {
            v105 = SetMappedAadAccountSidMap(
                     (struct _GUID *)((char *)v19 + 68),
                     *((const unsigned __int16 **)v257 + 8),
                     *((PSID *)v247 + 30));
            LogonCredsFromAuthBuffer = v105;
            v238 = v105;
            if ( v105 )
            {
              v33 = v105;
              v34 = "";
              do
                v96 = v34--;
              while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
              v35 = 0;
              v97 = *v34 == 92;
              v37 = 7296;
              v32 = "SetMappedAadAccountSidMap";
              goto LABEL_493;
            }
          }
          v19 = v99;
        }
        if ( (unsigned int)v259 <= CachedUnlock )
        {
          v106 = 10372;
          if ( _bittest(&v106, v259) )
          {
            if ( LODWORD(Buf1[0]) == 1 && HIDWORD(Buf1[0]) )
            {
              v107 = *((_DWORD *)v19 + 40);
              v248 = 0;
              v108 = IsPasswordNotAllowed(v19, v247, v257, &v248);
              LogonCredsFromAuthBuffer = v108;
              v238 = v108;
              v109 = v107 & 8;
              if ( v109 && v108 )
              {
                v33 = v108;
                v34 = "";
                do
                  v96 = v34--;
                while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                v35 = 0;
                v97 = *v34 == 92;
                v37 = 7314;
                v32 = "IsPasswordNotAllowed";
                goto LABEL_493;
              }
              if ( v248 )
              {
                CloudAPProvider::CloudApLogonUser::PasswordAuthBufferUsed((CloudAPProvider::CloudApLogonUser *)&v323);
                if ( v109 )
                {
                  v55 = 1;
                  v238 = -1073741477;
                  v242 = 0;
                  v54 = v267;
                  *v267 = 0;
                  v110 = "";
                  while ( 1 )
                  {
                    v111 = v110--;
                    v112 = *v110 == 92;
                    if ( *v110 == 92 )
                      break;
                    if ( v110 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
                    {
                      v112 = *v110 == 92;
                      break;
                    }
                  }
                  if ( v112 )
                    v110 = v111;
                  UserDataCount[0] = 7329;
                  WPPTraceLogA(
                    0,
                    "0x%08x %s:%u : %s:%ws",
                    3221225819LL,
                    v110,
                    *(_QWORD *)UserDataCount,
                    "PasswordNotAllowed",
                    &Class);
                  ReleaseLogonSession(v281);
                  goto LABEL_67;
                }
              }
            }
          }
        }
        TokenInformationV2 = MakeTokenInformationV2(v257, &v274);
        LogonCredsFromAuthBuffer = TokenInformationV2;
        v238 = TokenInformationV2;
        if ( TokenInformationV2 )
        {
          v33 = TokenInformationV2;
          v34 = "";
          do
            v96 = v34--;
          while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
          v35 = 0;
          v97 = *v34 == 92;
          v37 = 7335;
          v32 = "MakeTokenInformationV2";
          goto LABEL_493;
        }
        NtAllocateLocallyUniqueId(&LocallyUniqueId);
        v114 = (const unsigned __int16 *)SRWLock;
        PrimaryCredentials = MakePrimaryCredentials(
                               &LocallyUniqueId,
                               v240 == 0,
                               v257,
                               v276[1],
                               v254,
                               (const unsigned __int16 *)SRWLock,
                               v288,
                               (struct _DPAPI_DECODED_AUTH_DATA *)Buf1,
                               (struct _SECPKG_PRIMARY_CRED_EX *)v305);
        LogonCredsFromAuthBuffer = PrimaryCredentials;
        v238 = PrimaryCredentials;
        if ( PrimaryCredentials )
        {
          v33 = PrimaryCredentials;
          v34 = "";
          do
            v96 = v34--;
          while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
          v35 = 0;
          v97 = *v34 == 92;
          v37 = 7350;
          v32 = "MakePrimaryCredentials";
          goto LABEL_493;
        }
        v116 = v254;
        SupplementalCredentials = MakeSupplementalCredentials(
                                    v254,
                                    v247,
                                    (struct _DPAPI_DECODED_AUTH_DATA *)Buf1,
                                    v244,
                                    &v296,
                                    &v272);
        if ( SupplementalCredentials )
        {
          v118 = "";
          while ( 1 )
          {
            v119 = v118--;
            v120 = *v118 == 92;
            if ( *v118 == 92 )
              break;
            if ( v118 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
            {
              v120 = *v118 == 92;
              break;
            }
          }
          if ( v120 )
            v118 = v119;
          UserDataCountb[0] = 7359;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            SupplementalCredentials,
            v118,
            *(_QWORD *)UserDataCountb,
            "MakeSupplementalCredentials",
            &Class);
        }
        v121 = BYTE8(v301) & 0x40;
        v122 = v243 || v245;
        if ( (BYTE8(v301) & 0x40) != 0 )
          v123 = AllocateInteractiveProfileHelper<_KERB_INTERACTIVE_PROFILE_WOW64>(
                   (__int64)v283,
                   v237,
                   v239,
                   v122,
                   (__int64)v257,
                   (__int64)v116,
                   (__int64)v247,
                   &v271,
                   (union _LARGE_INTEGER **)&v256,
                   &v264);
        else
          v123 = AllocateInteractiveProfileHelper<_KERB_INTERACTIVE_PROFILE>(
                   (__int64)v283,
                   v237,
                   v239,
                   v122,
                   (__int64)v257,
                   (__int64)v116,
                   (__int64)v247,
                   &v271,
                   &v256,
                   &v264);
        LogonCredsFromAuthBuffer = v123;
        v238 = v123;
        if ( v123 )
        {
          v33 = v123;
          v34 = "";
          do
            v96 = v34--;
          while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
          v35 = 0;
          v97 = *v34 == 92;
          v37 = 7376;
          v32 = "AllocateInteractiveProfile";
          v265 = (union _LARGE_INTEGER *)v256;
          goto LABEL_493;
        }
        v124 = ((__int64 (__fastcall *)(LUID *))g_pLsaFunctionTable->CreateLogonSession)(&LocallyUniqueId);
        LogonCredsFromAuthBuffer = v124;
        v238 = v124;
        if ( v124 )
        {
          v33 = v124;
          v34 = "";
          do
            v96 = v34--;
          while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
          v35 = 0;
          v97 = *v34 == 92;
          v37 = 7381;
          v32 = "CreateLogonSession";
          v265 = (union _LARGE_INTEGER *)v256;
          goto LABEL_493;
        }
        v253 = 1;
        if ( v84 )
        {
          UserDataCount[0] = 4;
          v125 = ((__int64 (__fastcall *)(LUID *, unsigned __int64, _QWORD, int *))g_pLsaFunctionTable->DummyFunction7)(
                   &LocallyUniqueId,
                   g_ulpCloudAPPackageId,
                   0,
                   &v286);
          if ( v125 )
          {
            v126 = "";
            while ( 1 )
            {
              v127 = v126--;
              v128 = *v126 == 92;
              if ( *v126 == 92 )
                break;
              if ( v126 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
              {
                v128 = *v126 == 92;
                break;
              }
            }
            if ( v128 )
              v126 = v127;
            UserDataCount[0] = 7393;
            WPPTraceLogA(
              0,
              "0x%08x %s:%u : %s:%ws",
              v125,
              v126,
              *(_QWORD *)UserDataCount,
              "UpdateLogonSessionData(LSDT_LogonUserFlags)",
              &Class);
          }
        }
        if ( (*((_BYTE *)v254 + 160) & 1) == 0 )
        {
          v129 = ((__int64 (__fastcall *)(LUID *, unsigned __int64, __int64, int *, int))g_pLsaFunctionTable->DummyFunction7)(
                   &LocallyUniqueId,
                   g_ulpCloudAPPackageId,
                   2,
                   &v266,
                   4);
          LogonCredsFromAuthBuffer = v129;
          v238 = v129;
          if ( v129 )
          {
            v33 = v129;
            v34 = "";
            do
              v96 = v34--;
            while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
            v35 = 0;
            v97 = *v34 == 92;
            v37 = 7405;
            v32 = "UpdateLogonSessionData(LSDT_DsNamesFlags)";
            v265 = (union _LARGE_INTEGER *)v256;
            goto LABEL_493;
          }
          v130 = UpdateLSALogonSessionNames(v305[82] & 1, v114, v101, &LocallyUniqueId, v247, v257);
          LogonCredsFromAuthBuffer = v130;
          v238 = v130;
          if ( v130 )
          {
            v33 = v130;
            v34 = "";
            do
              v96 = v34--;
            while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
            v35 = 0;
            v97 = *v34 == 92;
            v37 = 7415;
            v32 = "UpdateLSALogonSessionNames";
            v265 = (union _LARGE_INTEGER *)v256;
            goto LABEL_493;
          }
        }
        v265 = (union _LARGE_INTEGER *)v256;
        if ( !v121 )
        {
          *(_QWORD *)UserDataCount = 0;
          v131 = LsaISetLogonInfo(&LocallyUniqueId, 0, 0, 0);
          LogonCredsFromAuthBuffer = v131;
          v238 = v131;
          if ( v131 )
          {
            v33 = v131;
            v34 = "";
            do
              v96 = v34--;
            while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
            v35 = 0;
            v97 = *v34 == 92;
            v37 = 7435;
            v32 = "LsaISetLogonInfo";
            goto LABEL_493;
          }
        }
        v133 = *((_QWORD *)CloudAPProvider::Instance() + 1);
        if ( *(_DWORD *)v133 > 5u )
        {
          v132 = *(_QWORD *)(v133 + 24);
          if ( (*(_QWORD *)(v133 + 16) & 0x400000000000LL) != 0 && (v132 & 0x400000000000LL) == v132 )
          {
            v256 = 0x2000000;
            v362 = &v256;
            v363 = 8;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            *(_DWORD *)&EventDescriptor.Level = 5;
            EventDescriptor.Keyword = 0x400000000000LL;
            v358.Ptr = *(_QWORD *)(v133 + 8);
            v358.Size = *(unsigned __int16 *)v358.Ptr;
            v358.Reserved = 2;
            v359 = &word_18008FBF6;
            v360 = 58;
            v361 = 1;
            LODWORD(SourceString) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(*(_QWORD *)(v133 + 32), &EventDescriptor, 0, 0, 3u, &v358);
          }
        }
        v134 = v276[1];
        v268 = 0;
        v135 = ((__int64 (__fastcall *)(__int64, __int64))g_pLsaFunctionTable->AllocateLsaHeap)(16, v132);
        v256 = v135;
        v136 = "";
        if ( !v135 )
        {
          LogonCredsFromAuthBuffer = -1073741801;
          v238 = -1073741801;
          do
            v137 = v136--;
          while ( *v136 != 92 && v136 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
          if ( *v136 == 92 )
            v136 = v137;
          UserDataCount[0] = 198;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            3221225495LL,
            v136,
            *(_QWORD *)UserDataCount,
            "AllocateLsaHeap",
            &Class);
          v33 = -1073741801;
LABEL_328:
          v34 = "";
          do
            v151 = v34--;
          while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
          v18 = v237;
          v35 = 0;
          v36 = "0x%08x %s:%u : %s:%ws";
          if ( *v34 == 92 )
            v34 = v151;
          v37 = 7442;
          v32 = "DuplicateUnicodeString";
          goto LABEL_497;
        }
        v138 = 0xFFFFFFFFLL;
        v139 = 3221225621LL;
        if ( !v134 )
          goto LABEL_334;
        v140 = -1;
        do
          ++v140;
        while ( v134[v140] );
        v141 = 2LL * (unsigned int)v140;
        if ( v141 > 0xFFFFFFFF )
        {
          LogonCredsFromAuthBuffer = -1073741675;
          v238 = -1073741675;
          v144 = "";
          do
            v145 = v144--;
          while ( *v144 != 92 && v144 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
          v148 = "RtlDWordMult";
          v146 = *v144 == 92;
          v147 = 206;
        }
        else
        {
          *(_WORD *)v135 = v141;
          v142 = v141 + 2;
          if ( (int)v141 + 2 >= (unsigned int)v141 )
          {
            *(_WORD *)(v135 + 2) = v142;
            v143 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD, __int64, __int64))g_pLsaFunctionTable->AllocateLsaHeap)(
                                         v142,
                                         0xFFFFFFFFLL,
                                         3221225621LL);
            *(_QWORD *)(v135 + 8) = v143;
            if ( !v143 )
            {
              LogonCredsFromAuthBuffer = -1073741801;
              v238 = -1073741801;
              v144 = "";
              do
                v145 = v144--;
              while ( *v144 != 92 && v144 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
              v33 = -1073741801;
              v139 = 3221225495LL;
              v146 = *v144 == 92;
              v147 = 219;
              v148 = "AllocateLsaHeap";
              goto LABEL_323;
            }
            v149 = RtlStringCchCopyW(v143, (unsigned __int64)*(unsigned __int16 *)(v135 + 2) >> 1, v134);
            LogonCredsFromAuthBuffer = v149;
            v238 = v149;
            if ( v149 )
            {
              v33 = v149;
              v144 = "";
              do
                v145 = v144--;
              while ( *v144 != 92 && v144 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
              v148 = "RtlStringCchCopyW";
              v139 = v149;
              v146 = *v144 == 92;
              v147 = 223;
LABEL_323:
              if ( v146 )
                v144 = v145;
              UserDataCount[0] = v147;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v139, v144, *(_QWORD *)UserDataCount, v148, &Class);
              v150 = (union _LARGE_INTEGER *)v256;
              if ( *(_QWORD *)(v256 + 8) )
                ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
              ((void (__fastcall *)(union _LARGE_INTEGER *))g_pLsaFunctionTable->FreeLsaHeap)(v150);
              if ( LogonCredsFromAuthBuffer )
                goto LABEL_328;
LABEL_335:
              v269 = 0;
              v152 = ((__int64 (__fastcall *)(__int64, __int64, __int64))g_pLsaFunctionTable->AllocateLsaHeap)(
                       16,
                       v138,
                       v139);
              v256 = v152;
              if ( !v152 )
              {
                LogonCredsFromAuthBuffer = -1073741801;
                v238 = -1073741801;
                while ( 1 )
                {
                  v153 = v136--;
                  v154 = *v136 == 92;
                  if ( *v136 == 92 )
                    break;
                  if ( v136 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
                  {
                    v154 = *v136 == 92;
                    break;
                  }
                }
                if ( v154 )
                  v136 = v153;
                UserDataCount[0] = 198;
                WPPTraceLogA(
                  0,
                  "0x%08x %s:%u : %s:%ws",
                  3221225495LL,
                  v136,
                  *(_QWORD *)UserDataCount,
                  "AllocateLsaHeap",
                  &Class);
                v33 = -1073741801;
                goto LABEL_372;
              }
              v155 = (const unsigned __int16 *)SRWLock;
              if ( !SRWLock )
                goto LABEL_378;
              v156 = -1;
              do
                ++v156;
              while ( *((_WORD *)&SRWLock->Ptr + v156) );
              v157 = 2LL * (unsigned int)v156;
              if ( v157 > 0xFFFFFFFF )
              {
                v161 = 3221225621LL;
                LogonCredsFromAuthBuffer = -1073741675;
                v238 = -1073741675;
                v159 = "";
                do
                  v160 = v159--;
                while ( *v159 != 92 && v159 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                v164 = "RtlDWordMult";
                v162 = *v159 == 92;
                v163 = 206;
              }
              else
              {
                *(_WORD *)v152 = v157;
                if ( (int)v157 + 2 >= (unsigned int)v157 )
                {
                  *(_WORD *)(v152 + 2) = v157 + 2;
                  v158 = (unsigned __int16 *)((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
                  *(_QWORD *)(v152 + 8) = v158;
                  if ( !v158 )
                  {
                    LogonCredsFromAuthBuffer = -1073741801;
                    v238 = -1073741801;
                    v159 = "";
                    do
                      v160 = v159--;
                    while ( *v159 != 92 && v159 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                    v33 = -1073741801;
                    v161 = 3221225495LL;
                    v162 = *v159 == 92;
                    v163 = 219;
                    v164 = "AllocateLsaHeap";
                    goto LABEL_367;
                  }
                  v165 = RtlStringCchCopyW(v158, (unsigned __int64)*(unsigned __int16 *)(v152 + 2) >> 1, v155);
                  LogonCredsFromAuthBuffer = v165;
                  v238 = v165;
                  if ( v165 )
                  {
                    v33 = v165;
                    v159 = "";
                    do
                      v160 = v159--;
                    while ( *v159 != 92 && v159 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                    v164 = "RtlStringCchCopyW";
                    v161 = v165;
                    v162 = *v159 == 92;
                    v163 = 223;
LABEL_367:
                    if ( v162 )
                      v159 = v160;
                    UserDataCount[0] = v163;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v161, v159, *(_QWORD *)UserDataCount, v164, &Class);
                    v166 = (union _LARGE_INTEGER *)v256;
                    if ( *(_QWORD *)(v256 + 8) )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    ((void (__fastcall *)(union _LARGE_INTEGER *))g_pLsaFunctionTable->FreeLsaHeap)(v166);
                    if ( LogonCredsFromAuthBuffer )
                    {
LABEL_372:
                      v34 = "";
                      do
                        v167 = v34--;
                      while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                      v18 = v237;
                      v35 = 0;
                      v36 = "0x%08x %s:%u : %s:%ws";
                      if ( *v34 == 92 )
                        v34 = v167;
                      v37 = 7445;
                      v32 = "DuplicateUnicodeString";
                      goto LABEL_497;
                    }
LABEL_379:
                    v270 = 0;
                    v168 = ((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(16);
                    if ( !v168 )
                    {
                      LogonCredsFromAuthBuffer = -1073741801;
                      v238 = -1073741801;
                      while ( 1 )
                      {
                        v169 = v136--;
                        v170 = *v136 == 92;
                        if ( *v136 == 92 )
                          break;
                        if ( v136 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
                        {
                          v170 = *v136 == 92;
                          break;
                        }
                      }
                      if ( v170 )
                        v136 = v169;
                      UserDataCount[0] = 198;
                      WPPTraceLogA(
                        0,
                        "0x%08x %s:%u : %s:%ws",
                        3221225495LL,
                        v136,
                        *(_QWORD *)UserDataCount,
                        "AllocateLsaHeap",
                        &Class);
                      v33 = -1073741801;
                      goto LABEL_416;
                    }
                    v171 = -1;
                    do
                      ++v171;
                    while ( *(&g_awchComputerName + v171) );
                    v172 = 2LL * (unsigned int)v171;
                    if ( v172 > 0xFFFFFFFF )
                    {
                      v175 = -1073741675;
                      LogonCredsFromAuthBuffer = -1073741675;
                      v238 = -1073741675;
                      do
                        v174 = v136--;
                      while ( *v136 != 92 && v136 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                      v177 = "RtlDWordMult";
                      v176 = *v136 == 92;
                      v178 = 206;
                    }
                    else
                    {
                      *(_WORD *)v168 = v172;
                      if ( (int)v172 + 2 >= (unsigned int)v172 )
                      {
                        *(_WORD *)(v168 + 2) = v172 + 2;
                        v173 = (unsigned __int16 *)((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
                        *(_QWORD *)(v168 + 8) = v173;
                        if ( v173 )
                        {
                          v179 = RtlStringCchCopyW(
                                   v173,
                                   (unsigned __int64)*(unsigned __int16 *)(v168 + 2) >> 1,
                                   &g_awchComputerName);
                          LogonCredsFromAuthBuffer = v179;
                          v238 = v179;
                          if ( !v179 )
                          {
                            v270 = v168;
                            goto LABEL_423;
                          }
                          v33 = v179;
                          do
                            v174 = v136--;
                          while ( *v136 != 92 && v136 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                          v177 = "RtlStringCchCopyW";
                          v175 = v179;
                          v176 = *v136 == 92;
                          v178 = 223;
                        }
                        else
                        {
                          LogonCredsFromAuthBuffer = -1073741801;
                          v238 = -1073741801;
                          do
                            v174 = v136--;
                          while ( *v136 != 92 && v136 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                          v33 = -1073741801;
                          v175 = -1073741801;
                          v176 = *v136 == 92;
                          v177 = "AllocateLsaHeap";
                          v178 = 219;
                        }
LABEL_411:
                        if ( v176 )
                          v136 = v174;
                        UserDataCount[0] = v178;
                        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v175, v136, *(_QWORD *)UserDataCount, v177, &Class);
                        if ( *(_QWORD *)(v168 + 8) )
                          ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                        ((void (__fastcall *)(__int64))g_pLsaFunctionTable->FreeLsaHeap)(v168);
                        if ( LogonCredsFromAuthBuffer )
                        {
LABEL_416:
                          v34 = "";
                          do
                            v180 = v34--;
                          while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                          v18 = v237;
                          v35 = 0;
                          v36 = "0x%08x %s:%u : %s:%ws";
                          if ( *v34 == 92 )
                            v34 = v180;
                          v37 = 7448;
                          v32 = "DuplicateUnicodeString";
                          goto LABEL_497;
                        }
                        v168 = v270;
LABEL_423:
                        v181 = CreateLogonSession(&LocallyUniqueId, v247, v273, &v281);
                        LogonCredsFromAuthBuffer = v181;
                        v238 = v181;
                        if ( v181 )
                        {
                          v33 = v181;
                          v34 = "";
                          do
                            v96 = v34--;
                          while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                          v35 = 0;
                          v97 = *v34 == 92;
                          v37 = 7455;
                          v32 = "AddLogonSession";
                        }
                        else
                        {
                          IsLoaded = GetTokenIfProfileIsLoaded(v247, &TokenHandle);
                          LogonCredsFromAuthBuffer = IsLoaded;
                          v238 = IsLoaded;
                          if ( IsLoaded )
                          {
                            v33 = IsLoaded;
                            v34 = "";
                            do
                              v96 = v34--;
                            while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                            v35 = 0;
                            v97 = *v34 == 92;
                            v37 = 7460;
                            v32 = "GetTokenIfProfileIsLoaded";
                            Handle = TokenHandle;
                          }
                          else
                          {
                            Handle = TokenHandle;
                            v19 = v254;
                            if ( TokenHandle
                              && (v183 = SyncDpapiKey(
                                           TokenHandle,
                                           v240,
                                           v254,
                                           v247,
                                           v249,
                                           0,
                                           (struct _CloudAPCache *)hMem,
                                           &v241),
                                  LogonCredsFromAuthBuffer = v183,
                                  (v238 = v183) != 0) )
                            {
                              v33 = v183;
                              v34 = "";
                              do
                                v96 = v34--;
                              while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                              v35 = 0;
                              v97 = *v34 == 92;
                              v37 = 7475;
                              v32 = "SyncDpapiKey";
                            }
                            else
                            {
                              if ( g_bAutoProvisionTBAL )
                              {
                                if ( LODWORD(Buf1[0]) != 3 )
                                {
                                  LogonCredsFromAuthBuffer = CheckTBALProvisioned(
                                                               v247,
                                                               (struct _CloudAPCache *)hMem,
                                                               &v250);
                                  v238 = LogonCredsFromAuthBuffer;
                                  if ( LogonCredsFromAuthBuffer < 0 || !v250 )
                                  {
                                    if ( LogonCredsFromAuthBuffer )
                                    {
                                      v185 = "";
                                      while ( 1 )
                                      {
                                        v186 = v185--;
                                        v187 = *v185 == 92;
                                        if ( *v185 == 92 )
                                          break;
                                        if ( v185 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
                                        {
                                          v187 = *v185 == 92;
                                          break;
                                        }
                                      }
                                      if ( v187 )
                                        v185 = v186;
                                      v32 = "CheckTBALProvisioned";
                                      UserDataCount[0] = 7501;
                                      WPPTraceLogA(
                                        0,
                                        "0x%08x %s:%u : %s:%ws",
                                        (unsigned int)LogonCredsFromAuthBuffer,
                                        v185,
                                        *(_QWORD *)UserDataCount,
                                        "CheckTBALProvisioned",
                                        &Class);
                                      if ( LogonCredsFromAuthBuffer == -1073741801
                                        || LogonCredsFromAuthBuffer == -1073741670 )
                                      {
                                        v33 = LogonCredsFromAuthBuffer;
                                        v34 = "";
                                        do
                                          v188 = v34--;
                                        while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                                        v18 = v237;
                                        v35 = 0;
                                        v36 = "0x%08x %s:%u : %s:%ws";
                                        if ( *v34 == 92 )
                                          v34 = v188;
                                        v37 = 7505;
                                        goto LABEL_497;
                                      }
                                    }
                                    v189 = ProvisionTBAL(v247, (struct _CloudAPCache *)hMem, 0, 0);
                                    LogonCredsFromAuthBuffer = v189;
                                    v238 = v189;
                                    if ( v189 )
                                    {
                                      v33 = v189;
                                      v34 = "";
                                      do
                                        v190 = v34--;
                                      while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                                      v18 = v237;
                                      v35 = 0;
                                      v36 = "0x%08x %s:%u : %s:%ws";
                                      if ( *v34 == 92 )
                                        v34 = v190;
                                      v37 = 7509;
                                      v32 = "ProvisionTBAL";
                                      goto LABEL_497;
                                    }
                                    v241 = 1;
                                  }
                                }
                              }
                              else
                              {
                                v184 = UnprovisionTBAL(v247, (struct _CloudAPCache *)hMem, &v241);
                                LogonCredsFromAuthBuffer = v184;
                                v238 = v184;
                                if ( v184 )
                                {
                                  v33 = v184;
                                  v34 = "";
                                  do
                                    v96 = v34--;
                                  while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                                  v35 = 0;
                                  v97 = *v34 == 92;
                                  v37 = 7489;
                                  v32 = "UnprovisionTBAL";
                                  goto LABEL_493;
                                }
                              }
                              v191 = 0;
                              if ( !v239 && LODWORD(Buf1[0]) == 1 && HIDWORD(Buf1[0]) )
                              {
                                WORD1(v298) = WORD2(Buf1[0]);
                                LOWORD(v298) = WORD2(Buf1[0]);
                                *((void **)&v298 + 1) = Buf1[1];
                                LsaINotifyNewPassword(*((_QWORD *)v257 + 2), &v298);
                              }
                              if ( v243 )
                                v191 = 2;
                              if ( v246 )
                                v191 |= 4u;
                              if ( v191 )
                              {
                                v192 = UpdateCacheNodeFlags(
                                         (struct _CloudAPCache *)hMem,
                                         (struct _USER_CACHE_ENTRY *)((char *)v247 + 296),
                                         *((struct _CREDENTIAL_KEY **)v247 + 33),
                                         v191,
                                         UserDataCount[0]);
                                if ( v192 )
                                {
                                  v193 = "";
                                  while ( 1 )
                                  {
                                    v194 = v193--;
                                    v195 = *v193 == 92;
                                    if ( *v193 == 92 )
                                      break;
                                    if ( v193 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
                                    {
                                      v195 = *v193 == 92;
                                      break;
                                    }
                                  }
                                  if ( v195 )
                                    v193 = v194;
                                  UserDataCountc[0] = 7557;
                                  WPPTraceLogA(
                                    0,
                                    "0x%08x %s:%u : %s:%ws",
                                    v192,
                                    v193,
                                    *(_QWORD *)UserDataCountc,
                                    "EnableCacheNodeFlags",
                                    &Class);
                                }
                              }
                              v196 = SaveCaches(
                                       (const unsigned __int16 **)v19,
                                       v241,
                                       !v239,
                                       (struct _CloudAPCache *)hMem,
                                       v247,
                                       v257,
                                       (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)((char *)v277
                                                                                   + *((unsigned int *)v277 + 5)),
                                       0,
                                       0);
                              LogonCredsFromAuthBuffer = v196;
                              v238 = v196;
                              if ( !v196 )
                              {
                                *((_DWORD *)v247 + 86) = *((_DWORD *)v247 + 74);
                                *v289 = LocallyUniqueId;
                                *v290 = LsaTokenInformationV2;
                                *v291 = v274;
                                v274 = 0;
                                v197 = v299;
                                *(_OWORD *)&v299->LogonId.LowPart = *(_OWORD *)v305;
                                *(_OWORD *)&v197->DownlevelName.Buffer = *(_OWORD *)&v305[16];
                                *(_OWORD *)&v197->DomainName.Buffer = *(_OWORD *)&v305[32];
                                *(_OWORD *)&v197->Password.Buffer = *(_OWORD *)&v305[48];
                                *(_OWORD *)&v197->OldPassword.Buffer = *(_OWORD *)&v305[64];
                                *(_OWORD *)&v197->Flags = *(_OWORD *)&v305[80];
                                *(_OWORD *)&v197->DnsDomainName.Buffer = *(_OWORD *)&v305[96];
                                *(_OWORD *)&v197->Upn.Buffer = *(_OWORD *)&v305[112];
                                *(_OWORD *)&v197->LogonServer.Buffer = *(_OWORD *)&v305[128];
                                *(_OWORD *)&v197->Spare1.Buffer = *(_OWORD *)&v305[144];
                                *(_OWORD *)&v197->Spare2.Buffer = *(_OWORD *)&v305[160];
                                *(_OWORD *)&v197->Spare3.Buffer = *(_OWORD *)&v305[176];
                                *(_OWORD *)&v197->Spare4.Buffer = *(_OWORD *)&v305[192];
                                *(_OWORD *)&v197->PrevLogonId.LowPart = v306;
                                memset_0(v305, 0, 0xE0u);
                                *v292 = v268;
                                v268 = 0;
                                *v293 = v269;
                                v269 = 0;
                                *v279 = (struct _UNICODE_STRING *)v168;
                                v270 = 0;
                                *v294 = v271;
                                *v295 = v264;
                                v271 = 0;
                                *v280 = (struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *)v272;
                                v272 = 0;
                                WriteCredKeyEventLog(v247, 0);
                                LogonCredsFromAuthBuffer = 0;
                                v238 = 0;
                                v18 = v237;
                                goto LABEL_500;
                              }
                              v33 = v196;
                              v34 = "";
                              do
                                v96 = v34--;
                              while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                              v35 = 0;
                              v97 = *v34 == 92;
                              v37 = 7572;
                              v32 = "SaveCaches";
                            }
                          }
                        }
LABEL_493:
                        v18 = v237;
                        goto LABEL_494;
                      }
                      v175 = -1073741675;
                      LogonCredsFromAuthBuffer = -1073741675;
                      v238 = -1073741675;
                      do
                        v174 = v136--;
                      while ( *v136 != 92 && v136 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                      v177 = "RtlDWordAdd";
                      v176 = *v136 == 92;
                      v178 = 211;
                    }
                    v33 = -1073741675;
                    goto LABEL_411;
                  }
LABEL_378:
                  v269 = (struct _UNICODE_STRING *)v152;
                  goto LABEL_379;
                }
                v161 = 3221225621LL;
                LogonCredsFromAuthBuffer = -1073741675;
                v238 = -1073741675;
                v159 = "";
                do
                  v160 = v159--;
                while ( *v159 != 92 && v159 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                v164 = "RtlDWordAdd";
                v162 = *v159 == 92;
                v163 = 211;
              }
              v33 = -1073741675;
              goto LABEL_367;
            }
LABEL_334:
            v268 = (struct _UNICODE_STRING *)v135;
            goto LABEL_335;
          }
          LogonCredsFromAuthBuffer = -1073741675;
          v238 = -1073741675;
          v144 = "";
          do
            v145 = v144--;
          while ( *v144 != 92 && v144 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
          v148 = "RtlDWordAdd";
          v146 = *v144 == 92;
          v147 = 211;
        }
        v33 = -1073741675;
        goto LABEL_323;
      }
      v240 = 0;
    }
    v239 = 1;
    goto LABEL_182;
  }
  LogonCredsFromAuthBuffer = GetTBALPwd(v247, (unsigned __int8 **)&SRWLock, (unsigned int *)&SourceString);
  v238 = LogonCredsFromAuthBuffer;
  if ( LogonCredsFromAuthBuffer >= 0 )
  {
    ((void (__fastcall *)(void *))g_pLsaFunctionTable->FreeLsaHeap)(Buf1[1]);
    Buf1[1] = SRWLock;
    HIDWORD(Buf1[0]) = (_DWORD)SourceString;
    v91 = 3;
    LODWORD(Buf1[0]) = 3;
    goto LABEL_175;
  }
  v92 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  UserDataCount[0] = 6880;
  WPPTraceLogA(
    0,
    "0x%08x %s:%u : %s:%ws",
    (unsigned int)LogonCredsFromAuthBuffer,
    v92,
    *(_QWORD *)UserDataCount,
    "GetTBALPwd",
    &Class);
  if ( LogonCredsFromAuthBuffer != -1073741801 )
  {
    if ( LogonCredsFromAuthBuffer != -1073741670 )
      LogonCredsFromAuthBuffer = 0;
    v238 = LogonCredsFromAuthBuffer;
  }
  v93 = SRWLock;
  if ( SRWLock )
  {
    v94 = (unsigned int)SourceString;
    v95 = SRWLock;
    if ( (_DWORD)SourceString )
    {
      do
      {
        LOBYTE(v95->Ptr) = 0;
        v95 = (PSRWLOCK)((char *)v95 + 1);
        --v94;
      }
      while ( v94 );
    }
    ((void (__fastcall *)(PSRWLOCK))g_pLsaFunctionTable->FreeLsaHeap)(v93);
  }
  if ( !LogonCredsFromAuthBuffer )
  {
LABEL_174:
    v91 = (int)Buf1[0];
    goto LABEL_175;
  }
  v33 = LogonCredsFromAuthBuffer;
  v34 = "";
  do
    v96 = v34--;
  while ( *v34 != 92 && v34 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
  v35 = 0;
  v97 = *v34 == 92;
  v37 = 7201;
  v32 = "RetrieveTBALPwd";
  v18 = v84 != 0;
LABEL_494:
  if ( v97 )
    v34 = v96;
  v36 = "0x%08x %s:%u : %s:%ws";
LABEL_497:
  UserDataCount[0] = v37;
  WPPTraceLogA(v35, v36, v33, v34, *(_QWORD *)UserDataCount, v32, &Class);
  if ( LogonCredsFromAuthBuffer < 0 )
  {
LABEL_64:
    v19 = v254;
    goto LABEL_65;
  }
  v19 = v254;
LABEL_500:
  if ( !v251 || !v18 )
    goto LABEL_65;
  v53 = -1073741232;
LABEL_66:
  v54 = v267;
  v55 = v242;
  *v267 = v53;
  ReleaseLogonSession(v281);
  if ( LogonCredsFromAuthBuffer < 0 )
  {
LABEL_67:
    v56 = v247;
    if ( v247 )
    {
      if ( (_DWORD)v275 && *((_QWORD *)&v275 + 1) )
      {
        v57 = (_BYTE *)*((_QWORD *)v247 + 36);
        if ( v57 )
        {
          v58 = *((unsigned int *)v247 + 70);
          if ( *((_DWORD *)v247 + 70) )
          {
            do
            {
              *v57++ = 0;
              --v58;
            }
            while ( v58 );
          }
          ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*((_QWORD *)v56 + 36));
        }
        *(_OWORD *)((char *)v56 + 280) = v275;
        v275 = 0;
      }
      if ( (_DWORD)v297 )
      {
        if ( *((_QWORD *)v56 + 38) )
          ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
        *(_OWORD *)((char *)v56 + 296) = v297;
        v297 = 0;
      }
    }
  }
  if ( v252 )
    UnlockAndProtectUserCacheEntry(v247);
  _ReleaseUserCacheEntry(0, v247);
  if ( v19 )
  {
    if ( v282 )
      RtlReleaseResource(*((PRTL_RESOURCE *)v19 + 45));
    RtlReleaseResource(&g_PackageListLock);
  }
  if ( v55 )
  {
    v59 = *v54;
    v60 = v244;
    v61 = v245;
    v62 = v246;
    v63 = v243;
    v64 = v239;
    v65 = GetCurrentThreadId();
    v236 = v59;
    v66 = v238;
    v235 = v60;
    v67 = v262;
    CloudAPProvider::CloudApLogonUser::Stop(
      (CloudAPProvider::CloudApLogonUser *)&v323,
      LocallyUniqueId,
      v65,
      v262,
      v259,
      (unsigned int)Buf1[0],
      v237,
      v64,
      v63,
      v62,
      v61,
      v235,
      v238,
      v236);
    v20 = "";
  }
  else
  {
    v66 = v238;
    v67 = v262;
  }
  v205 = (_BYTE *)*((_QWORD *)&v275 + 1);
  if ( *((_QWORD *)&v275 + 1) )
  {
    v206 = (unsigned int)v275;
    if ( (_DWORD)v275 )
    {
      do
      {
        *v205++ = 0;
        --v206;
      }
      while ( v206 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  if ( *((_QWORD *)&v297 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v207 = Buf1[1];
  if ( Buf1[1] )
  {
    v208 = HIDWORD(Buf1[0]);
    if ( HIDWORD(Buf1[0]) )
    {
      do
      {
        *v207++ = 0;
        --v208;
      }
      while ( v208 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  FreePackedCreds(v288);
  if ( (_QWORD)v287 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( *((_QWORD *)&v287 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v287 = 0;
  v288 = 0;
  FreePackedCreds(v277);
  if ( v276[0] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v276[1] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  *(_OWORD *)v276 = 0;
  v277 = 0;
  if ( v67 )
    ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v67);
  FreeUserInfo(v257);
  FreeCloudAPCache(hMem);
  if ( v274 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  FreePrimaryCred((struct _SECPKG_PRIMARY_CRED *)v305);
  v209 = v268;
  if ( v268 )
  {
    if ( v268->Buffer )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    ((void (__fastcall *)(struct _UNICODE_STRING *))g_pLsaFunctionTable->FreeLsaHeap)(v209);
  }
  v210 = v269;
  if ( v269 )
  {
    if ( v269->Buffer )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    ((void (__fastcall *)(struct _UNICODE_STRING *))g_pLsaFunctionTable->FreeLsaHeap)(v210);
  }
  v211 = v270;
  if ( v270 )
  {
    if ( *(_QWORD *)(v270 + 8) )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    ((void (__fastcall *)(__int64))g_pLsaFunctionTable->FreeLsaHeap)(v211);
  }
  if ( v271 )
    ((void (__fastcall *)(void **))g_pLsaFunctionTable->FreeClientBuffer)(v283);
  if ( v265 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v212 = v272;
  if ( v272 )
  {
    for ( i = v296; i; --i )
      *v212++ = 0;
    ((void (__fastcall *)(unsigned __int8 *))g_pLsaFunctionTable->FreeLsaHeap)(v272);
  }
  if ( Handle )
    NtClose(Handle);
  if ( v285 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v273 )
    FreeScardPin(v273);
  if ( (v66 & 0x80000000) == 0 )
  {
    while ( 1 )
    {
      v218 = v20--;
      v219 = *v20 == 92;
      if ( *v20 == 92 )
        break;
      if ( v20 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v219 = *v20 == 92;
        break;
      }
    }
    UserData = "LsapApLogonUserEx2 success";
    UserDataCount[0] = 7739;
LABEL_598:
    if ( v219 )
      v20 = v218;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v66, v20, *(_QWORD *)UserDataCount, UserData, &Class);
  }
  else
  {
    if ( v253 )
      ((void (__fastcall *)(LUID *))g_pLsaFunctionTable->DeleteLogonSession)(&LocallyUniqueId);
    RtlAcquireResourceExclusive(&g_LogonSessionListLock, 1u);
    v214 = g_LogonSessionList;
    if ( g_LogonSessionList == (struct _LOGON_SESSION *)&g_LogonSessionList )
      goto LABEL_575;
    while ( *((_DWORD *)v214 + 7) != LocallyUniqueId.LowPart || *((_DWORD *)v214 + 8) != LocallyUniqueId.HighPart )
    {
      v214 = *(struct _LOGON_SESSION **)v214;
      if ( v214 == (struct _LOGON_SESSION *)&g_LogonSessionList )
        goto LABEL_575;
    }
    _InterlockedDecrement((volatile signed __int32 *)v214 + 4);
    if ( *((_DWORD *)v214 + 4) )
    {
LABEL_575:
      RtlReleaseResource(&g_LogonSessionListLock);
    }
    else
    {
      v220 = *(struct _LOGON_SESSION **)v214;
      if ( *(struct _LOGON_SESSION **)(*(_QWORD *)v214 + 8LL) != v214
        || (v221 = (struct _LOGON_SESSION **)*((_QWORD *)v214 + 1), *v221 != v214) )
      {
        __fastfail(3u);
      }
      *v221 = v220;
      *((_QWORD *)v220 + 1) = v221;
      RtlReleaseResource(&g_LogonSessionListLock);
      v222 = _FreeLogonSession(v214);
      if ( v222 )
        _ReleaseUserCacheEntry(&LocallyUniqueId, v222);
    }
    if ( v242 )
    {
      v215 = "";
      while ( 1 )
      {
        v216 = v215--;
        v217 = *v215 == 92;
        if ( *v215 == 92 )
          break;
        if ( v215 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v217 = *v215 == 92;
          break;
        }
      }
      if ( v217 )
        v215 = v216;
      UserDataCount[0] = 7732;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        v66,
        v215,
        *(_QWORD *)UserDataCount,
        "LsaApLogonUserEx2 ApiSubStatus",
        &Class);
      v66 = -1073741715;
      while ( 1 )
      {
        v218 = v20--;
        v219 = *v20 == 92;
        if ( *v20 == 92 )
          break;
        if ( v20 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v219 = *v20 == 92;
          break;
        }
      }
      UserData = "LsapApLogonUserEx2 return value";
      UserDataCount[0] = 7734;
      goto LABEL_598;
    }
  }
  v323 = &CloudAPProvider::CloudApLogonUser::`vftable';
  if ( !v347 )
    goto LABEL_609;
  v223 = v347 + 33;
  AcquireSRWLockExclusive(v347 + 33);
  if ( v347 && LODWORD(v347->Ptr) == 1 )
  {
    v224 = 1;
  }
  else
  {
    v224 = 0;
    wil::details::shared_object<wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v347);
  }
  if ( v223 )
    ReleaseSRWLockExclusive(v223);
  if ( v224 )
  {
LABEL_609:
    v225 = v346;
    if ( *v346 == 1 )
    {
      v226 = v346[22];
      v227 = 2147942974LL;
      if ( v226 < 0 )
        v227 = (unsigned int)v226;
      v228 = v346[62];
      if ( v228 < 1 )
      {
        memset(v305, 0, 152);
        wil::details::WilFailFast((wil::details *)v305, (const struct wil::FailureInfo *)v227);
      }
      if ( v346[18] >= 0 )
        v346[18] = v227;
      v225[62] = v228 - 1;
      ((void (__fastcall *)(void ***, __int64))v323[1])(&v323, v227);
    }
  }
  wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v323);
  return v66;
}

```

## disassembly

```asm
0x180011960  push    rbp
0x180011962  push    rbx
0x180011963  push    rsi
0x180011964  push    rdi
0x180011965  push    r12
0x180011967  push    r13
0x180011969  push    r14
0x18001196b  push    r15
0x18001196d  lea     rbp, [rsp-6A8h]
0x180011975  sub     rsp, 7D8h
0x18001197c  mov     rax, cs:__security_cookie
0x180011983  xor     rax, rsp
0x180011986  mov     [rbp+6E0h+var_50], rax
0x18001198d  mov     rsi, r9
0x180011990  mov     rdi, r8
0x180011993  mov     [rbp+6E0h+var_710], edx
0x180011996  mov     [rbp+6E0h+var_640], rcx
0x18001199d  mov     rcx, [rbp+6E0h+arg_28]
0x1800119a4  mov     [rbp+6E0h+var_5E0], rcx
0x1800119ab  mov     rax, [rbp+6E0h+arg_30]
0x1800119b2  mov     [rbp+6E0h+var_5D8], rax
0x1800119b9  mov     rax, [rbp+6E0h+arg_38]
0x1800119c0  mov     [rbp+6E0h+var_608], rax
0x1800119c7  mov     rax, [rbp+6E0h+arg_40]
0x1800119ce  mov     [rbp+6E0h+var_6D0], rax
0x1800119d2  mov     rax, [rbp+6E0h+arg_48]
0x1800119d9  mov     [rbp+6E0h+var_600], rax
0x1800119e0  mov     rax, [rbp+6E0h+arg_50]
0x1800119e7  mov     [rbp+6E0h+var_5F8], rax
0x1800119ee  mov     rax, [rbp+6E0h+arg_58]
0x1800119f5  mov     [rbp+6E0h+var_5F0], rax
0x1800119fc  mov     rax, [rbp+6E0h+arg_60]
0x180011a03  mov     [rbp+6E0h+var_5E8], rax
0x180011a0a  mov     rax, [rbp+6E0h+arg_68]
0x180011a11  mov     [rbp+6E0h+var_660], rax
0x180011a18  mov     r13, [rbp+6E0h+arg_70]
0x180011a1f  mov     [rbp+6E0h+var_5A8], r13
0x180011a26  mov     rax, [rbp+6E0h+arg_78]
0x180011a2d  mov     [rbp+6E0h+var_658], rax
0x180011a34  xor     ebx, ebx
0x180011a36  mov     [rbp+6E0h+var_755], bl
0x180011a39  mov     [rbp+6E0h+var_758], bl
0x180011a3c  mov     [rbp+6E0h+var_744], bl
0x180011a3f  mov     [rbp+6E0h+var_743], bl
0x180011a42  xor     r15b, r15b
0x180011a45  mov     [rbp+6E0h+var_760], r15b
0x180011a49  mov     qword ptr [rbp+6E0h+LocallyUniqueId.LowPart], rbx
0x180011a4d  xorps   xmm0, xmm0
0x180011a50  xor     eax, eax
0x180011a52  movups  [rbp+6E0h+var_590], xmm0
0x180011a59  mov     [rbp+6E0h+var_580], rax
0x180011a60  movups  [rbp+6E0h+var_5B8], xmm0
0x180011a67  mov     [rbp+6E0h+var_756], al
0x180011a6a  mov     [rbp+6E0h+var_754], al
0x180011a6d  mov     [rbp+6E0h+var_751], al
0x180011a70  mov     [rbp+6E0h+var_752], al
0x180011a73  mov     [rbp+6E0h+var_753], al
0x180011a76  mov     [rbp+6E0h+var_6E8], ebx
0x180011a79  mov     [rbp+6E0h+var_628], 8000h
0x180011a83  mov     [rbp+6E0h+var_6D8], 1
0x180011a8a  mov     [rbp+6E0h+var_5D0], rbx
0x180011a91  mov     [rbp+6E0h+var_746], al
0x180011a94  mov     [rbp+6E0h+var_747], al
0x180011a97  movups  [rbp+6E0h+var_690], xmm0
0x180011a9b  xorps   xmm1, xmm1
0x180011a9e  movups  [rbp+6E0h+var_5C8], xmm1
0x180011aa5  movups  [rbp+6E0h+var_620], xmm0
0x180011aac  mov     [rbp+6E0h+var_610], rax
0x180011ab3  movups  xmmword ptr [rbp+6E0h+var_680], xmm1
0x180011ab7  mov     [rbp+6E0h+var_670], rax
0x180011abb  movups  xmmword ptr [rbp+6E0h+Buf1], xmm0
0x180011abf  mov     [rbp+6E0h+var_6F8], rbx
0x180011ac3  mov     [rbp+6E0h+SourceString], rbx
0x180011ac7  mov     r14d, ebx
0x180011aca  mov     [rbp+6E0h+var_740], rbx
0x180011ace  mov     [rbp+6E0h+var_648], rbx
0x180011ad5  mov     [rbp+6E0h+var_750], rbx
0x180011ad9  mov     [rbp+6E0h+var_728], rbx
0x180011add  mov     [rbp+6E0h+hMem], rbx
0x180011ae1  mov     [rbp+6E0h+var_698], rbx
0x180011ae5  mov     dword ptr [rbp+6E0h+var_550], ebx
0x180011aeb  xor     edx, edx; Val
0x180011aed  mov     r8d, 0DCh; Size
0x180011af3  lea     rcx, [rbp+6E0h+var_550+4]; void *
0x180011afa  call    memset_0
0x180011aff  mov     [rbp+6E0h+var_6C8], rbx
0x180011b03  mov     [rbp+6E0h+var_6C0], rbx
0x180011b07  mov     [rbp+6E0h+var_6B8], rbx
0x180011b0b  mov     [rbp+6E0h+var_6B0], rbx
0x180011b0f  mov     [rbp+6E0h+var_6E0], rbx
0x180011b13  mov     [rbp+6E0h+var_730], rbx
0x180011b17  mov     [rbp+6E0h+Handle], rbx
0x180011b1e  mov     [rbp+6E0h+TokenHandle], rbx
0x180011b22  mov     [rbp+6E0h+var_650], rbx
0x180011b29  mov     [rbp+6E0h+var_6A8], rbx
0x180011b2d  mov     [rbp+6E0h+var_630], rbx
0x180011b34  mov     [rbp+6E0h+var_6A0], rbx
0x180011b38  mov     [rbp+6E0h+var_318], ebx
0x180011b3e  mov     [rbp+6E0h+var_314], bl
0x180011b44  mov     [rbp+6E0h+var_2D8], bl
0x180011b4a  mov     [rbp+6E0h+var_2F0], ebx
0x180011b50  lea     rax, aCloudaplogonus; "CloudApLogonUser"
0x180011b57  mov     [rbp+6E0h+var_2E8], rax
0x180011b5e  mov     [rbp+6E0h+var_2E0], rbx
0x180011b65  mov     [rbp+6E0h+var_2D0], ebx
0x180011b6b  xorps   xmm0, xmm0
0x180011b6e  movdqa  [rbp+6E0h+var_230], xmm0
0x180011b76  xorps   xmm1, xmm1
0x180011b79  xor     eax, eax
0x180011b7b  movups  [rbp+6E0h+var_2C8], xmm1
0x180011b82  movups  [rbp+6E0h+var_2B8], xmm1
0x180011b89  movups  [rbp+6E0h+var_2A8], xmm1
0x180011b90  movups  [rbp+6E0h+var_298], xmm1
0x180011b97  movups  [rbp+6E0h+var_288], xmm1
0x180011b9e  movups  [rbp+6E0h+var_278], xmm1
0x180011ba5  movups  [rbp+6E0h+var_268], xmm1
0x180011bac  movups  [rbp+6E0h+var_258], xmm1
0x180011bb3  movups  [rbp+6E0h+var_248], xmm1
0x180011bba  mov     [rbp+6E0h+var_238], rax
0x180011bc1  mov     [rbp+6E0h+var_220], 1
0x180011bcb  mov     [rbp+6E0h+var_218], rax
0x180011bd2  lea     rax, [rbp+6E0h+var_318]
0x180011bd9  mov     [rbp+6E0h+var_210], rax
0x180011be0  mov     [rbp+6E0h+var_208], rbx
0x180011be7  mov     [rbp+6E0h+var_200], rbx
0x180011bee  lea     rax, [rbp+6E0h+var_320]
0x180011bf5  mov     [rbp+6E0h+var_1F8], rax
0x180011bfc  mov     [rbp+6E0h+var_1F0], rbx
0x180011c03  mov     [rbp+6E0h+var_1E8], ebx
0x180011c09  lea     rax, [rbp+6E0h+var_2F0]
0x180011c10  mov     [rbp+6E0h+var_1E0], rax
0x180011c17  mov     [rbp+6E0h+var_1D8], r15b
0x180011c1e  lea     rax, ??_7CloudApLogonUser@CloudAPProvider@@6B@; const CloudAPProvider::CloudApLogonUser::`vftable'
0x180011c25  mov     [rbp+6E0h+var_320], rax
0x180011c2c  lea     rdx, Class
0x180011c33  lea     r12, aOnecoreDsExtCl_6+27h; ""
0x180011c3a  test    rdi, rdi
0x180011c3d  jz      loc_18001443F
0x180011c43  mov     ebx, [rbp+6E0h+arg_20]
0x180011c49  test    ebx, ebx
0x180011c4b  jz      loc_18001443F
0x180011c51  mov     rax, [rbp+6E0h+var_5E0]
0x180011c58  test    rax, rax
0x180011c5b  jz      loc_18001443F
0x180011c61  mov     rcx, [rbp+6E0h+var_5D8]
0x180011c68  test    rcx, rcx
0x180011c6b  jz      loc_18001443F
0x180011c71  mov     rdx, [rbp+6E0h+var_608]
0x180011c78  test    rdx, rdx
0x180011c7b  jz      loc_180014438
0x180011c81  cmp     [rbp+6E0h+var_6D0], r14
0x180011c85  jz      loc_180014438
0x180011c8b  mov     r8, [rbp+6E0h+var_600]
0x180011c92  test    r8, r8
0x180011c95  jz      loc_180014438
0x180011c9b  mov     r9, [rbp+6E0h+var_5F8]
0x180011ca2  test    r9, r9
0x180011ca5  jz      loc_180014438
0x180011cab  mov     r10, [rbp+6E0h+var_5F0]
0x180011cb2  test    r10, r10
0x180011cb5  jz      loc_180014438
0x180011cbb  mov     r11, [rbp+6E0h+var_5E8]
0x180011cc2  test    r11, r11
0x180011cc5  jz      loc_180014438
0x180011ccb  cmp     [rbp+6E0h+var_660], r14
0x180011cd2  jz      loc_180014438
0x180011cd8  test    r13, r13
0x180011cdb  jz      loc_180014438
0x180011ce1  cmp     [rbp+6E0h+var_658], r14
0x180011ce8  jz      loc_180014438
0x180011cee  mov     [rax], r14
0x180011cf1  mov     [rcx], r14d
0x180011cf4  xor     eax, eax
0x180011cf6  mov     [rdx], rax
0x180011cf9  mov     rax, [rbp+6E0h+var_6D0]
0x180011cfd  xor     ecx, ecx
0x180011cff  mov     [rax], ecx
0x180011d01  mov     [r8], ecx
0x180011d04  mov     [r9], rcx
0x180011d07  mov     [r10], rcx
0x180011d0a  mov     [r11], rcx
0x180011d0d  mov     rax, [rbp+6E0h+var_660]
0x180011d14  mov     [rax], rcx
0x180011d17  xor     edx, edx; Val
0x180011d19  mov     r8d, 0E0h; Size
0x180011d1f  lea     rcx, [rbp+6E0h+var_470]; void *
0x180011d26  call    memset_0
0x180011d2b  movups  xmm0, [rbp+6E0h+var_470]
0x180011d32  movups  xmmword ptr [r13+0], xmm0
0x180011d37  movups  xmm1, [rbp+6E0h+var_460]
0x180011d3e  movups  xmmword ptr [r13+10h], xmm1
0x180011d43  movups  xmm0, [rbp+6E0h+var_450]
0x180011d4a  movups  xmmword ptr [r13+20h], xmm0
0x180011d4f  movups  xmm1, [rbp+6E0h+var_440]
0x180011d56  movups  xmmword ptr [r13+30h], xmm1
0x180011d5b  movups  xmm0, xmmword ptr [rbp+6E0h+var_430]
0x180011d62  movups  xmmword ptr [r13+40h], xmm0
0x180011d67  movups  xmm1, [rbp+6E0h+var_420]
0x180011d6e  movups  xmmword ptr [r13+50h], xmm1
0x180011d73  movups  xmm0, [rbp+6E0h+var_410]
0x180011d7a  movups  xmmword ptr [r13+60h], xmm0
0x180011d7f  movups  xmm1, [rbp+6E0h+var_400]
0x180011d86  movups  xmmword ptr [r13+70h], xmm1
0x180011d8b  movups  xmm0, [rbp+6E0h+var_3F0]
0x180011d92  movups  xmmword ptr [r13+80h], xmm0
0x180011d9a  movups  xmm1, [rbp+6E0h+var_3E0]
0x180011da1  movups  xmmword ptr [r13+90h], xmm1
0x180011da9  movups  xmm0, [rbp+6E0h+var_3D0]
0x180011db0  movups  xmmword ptr [r13+0A0h], xmm0
0x180011db8  movups  xmm1, [rbp+6E0h+var_3C0]
0x180011dbf  movups  xmmword ptr [r13+0B0h], xmm1
0x180011dc7  movups  xmm0, [rbp+6E0h+var_3B0]
0x180011dce  movups  xmmword ptr [r13+0C0h], xmm0
0x180011dd6  movups  xmm1, [rbp+6E0h+var_3A0]
0x180011ddd  movups  xmmword ptr [r13+0D0h], xmm1
0x180011de5  mov     rax, [rbp+6E0h+var_658]
0x180011dec  xor     r13d, r13d
0x180011def  mov     [rax], r13
0x180011df2  mov     r8d, [rbp+6E0h+var_710]
0x180011df6  cmp     r8d, 8
0x180011dfa  jz      short loc_180011E71; jumptable 0000000180011E1E cases 2-5,10
0x180011dfc  cmp     r8d, 0Dh
0x180011e00  jz      short loc_180011E69; jumptable 0000000180011E1E cases 11,12
0x180011e02  lea     eax, [r8-2]; switch 11 cases
0x180011e06  cmp     eax, 0Ah
0x180011e09  ja      short def_180011E1E; jumptable 0000000180011E1E default case, cases 6-9
0x180011e0b  cdqe
0x180011e0d  lea     rdx, __ImageBase
0x180011e14  mov     ecx, ds:(jpt_180011E1E - 180000000h)[rdx+rax*4]
0x180011e1b  add     rcx, rdx
0x180011e1e  jmp     rcx; switch jump
0x180011e20  mov     edi, 0C000010Bh; jumptable 0000000180011E1E default case, cases 6-9
0x180011e25  mov     [rbp+6E0h+var_75C], edi
0x180011e28  lea     r13, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180011e2f  mov     rcx, r13; char *
0x180011e32  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011e37  mov     r9, rax
0x180011e3a  mov     dword ptr [rsp+810h+var_7E0], r8d
0x180011e3f  lea     rax, aUnsupportedLog; "Unsupported Logon Type"
0x180011e46  mov     [rsp+810h+UserData], rax
0x180011e4b  mov     [rsp+810h+UserDataCount], 1BC5h
0x180011e53  mov     r8d, edi
0x180011e56  lea     rdx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x180011e5d  xor     ecx, ecx
0x180011e5f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180011e64  jmp     loc_18001218D
0x180011e69  mov     [rbp+6E0h+var_757], r13b; jumptable 0000000180011E1E cases 11,12
0x180011e6d  mov     al, 1
0x180011e6f  jmp     short loc_180011E77
0x180011e71  mov     [rbp+6E0h+var_757], 1; jumptable 0000000180011E1E cases 2-5,10
0x180011e75  xor     al, al
0x180011e77  mov     [rbp+6E0h+var_745], r13b
0x180011e7b  mov     [rbp+6E0h+var_758], al
0x180011e7e  lea     rax, [rbp+6E0h+SourceString]
0x180011e82  mov     qword ptr [rsp+810h+UserDataCount], rax; unsigned __int16 **
0x180011e87  lea     r9, [rbp+6E0h+var_620]; struct _DECRYPTED_AUTH_DATA *
0x180011e8e  mov     r8, rsi; void *
0x180011e91  mov     edx, ebx; unsigned int
0x180011e93  mov     rcx, rdi; struct _KERB_CERTIFICATE_LOGON *
0x180011e96  call    ?GetLogonCredsFromAuthBuffer@@YAJPEAXK0PEAU_DECRYPTED_AUTH_DATA@@PEAPEAG@Z; GetLogonCredsFromAuthBuffer(void *,ulong,void *,_DECRYPTED_AUTH_DATA *,ushort * *)
0x180011e9b  mov     edi, eax
0x180011e9d  mov     [rbp+6E0h+var_75C], eax
0x180011ea0  test    eax, eax
0x180011ea2  jns     loc_180011F30
0x180011ea8  lea     r13, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180011eaf  mov     rcx, r13; char *
0x180011eb2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011eb7  mov     r9, rax
0x180011eba  lea     rsi, Class
0x180011ec1  mov     [rsp+810h+var_7E0], rsi
0x180011ec6  lea     rbx, aGetlogoncredsf; "GetLogonCredsFromAuthBuffer"
0x180011ecd  mov     [rsp+810h+UserData], rbx
0x180011ed2  mov     [rsp+810h+UserDataCount], 1BD1h
0x180011eda  mov     r8d, edi
0x180011edd  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180011ee4  xor     ecx, ecx
0x180011ee6  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180011eeb  cmp     edi, 0C0000017h
0x180011ef1  jz      short loc_180011F06
0x180011ef3  mov     r8d, 0C000000Dh
0x180011ef9  cmp     edi, 0C000009Ah
0x180011eff  cmovnz  edi, r8d
0x180011f03  mov     [rbp+6E0h+var_75C], edi
0x180011f06  xor     r10d, r10d
0x180011f09  lea     r11, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180011f10  mov     r14d, edi
0x180011f13  mov     rcx, r13; char *
0x180011f16  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011f1b  mov     ecx, 1BD8h
0x180011f20  mov     rdx, rsi
0x180011f23  mov     r8, [rbp+6E0h+SourceString]
0x180011f27  mov     [rbp+6E0h+var_6F8], r8
0x180011f2b  jmp     loc_1800141F0
0x180011f30  mov     dl, 1; Wait
0x180011f32  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x180011f39  call    cs:__imp_RtlAcquireResourceShared
0x180011f3f  mov     r14, [rbp+6E0h+SourceString]
0x180011f43  mov     [rbp+6E0h+var_6F8], r14
0x180011f47  mov     rcx, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x180011f4e  test    rcx, rcx
  ... truncated ...
```
