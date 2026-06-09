# InstallBaseNTDS

- ea: `0x180194070`
- end: `0x180196b3e`
- name: `InstallBaseNTDS`
- size: `10958`
- prototype: `__int64 __fastcall(struct _DS_INSTALL_PARAM *)`
- caller_count: `1`
- callee_count: `87`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a504c`

## callees

- `0x180006330`
- `0x180006360`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x180038734`
- `0x18003c780`
- `0x18003c8d8`
- `0x180088850`
- `0x180096480`
- `0x1800ad248`
- `0x1800b14c0`
- `0x1800dcec0`
- `0x1800fae64`
- `0x180103910`
- `0x180167220`
- `0x180169070`
- `0x1801703f0`
- `0x1801705ec`
- `0x180172edc`
- `0x180180c50`
- `0x180181460`
- `0x180181ae0`
- `0x180181bf0`
- `0x180181db0`
- `0x180189d2c`
- `0x18018a6b8`
- `0x18018a888`
- `0x18018afc4`
- `0x18018b52c`
- `0x18018b8b0`
- `0x18018b9a4`
- `0x18018bad4`
- `0x18018bf28`
- `0x18018c600`
- `0x18018c65c`
- `0x18018c728`
- `0x18018c7f4`
- `0x18018ca64`
- `0x18018cce0`
- `0x18018cd44`
- `0x18018d798`
- `0x18018d860`
- `0x18018da18`
- `0x18018ed40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180195fb1`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1801968b1`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180195fb1`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1801968b1`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180195f97`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180196880`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180196897`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180195f97`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180196880`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180196897`
- `ntdsbsrv!InstallBackupServices` at `0x1801969f5`
- `ntdsbsrv!InstallBackupServices` at `0x1801969f5`
- `ntdsbsrv!NtdsbsrvDllInit` at `0x1801969d4`
- `ntdsbsrv!NtdsbsrvDllInit` at `0x1801969d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801949ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180194d00`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180195d6c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801962cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180196347`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180196435`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180196577`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180196615`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801967fd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180196a50`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180462d3c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801949ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180194d00`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180195d6c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801962cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180196347`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180196435`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180196577`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180196615`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801967fd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180196a50`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180462d3c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180194f20`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18019501b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180195152`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1801955ab`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180194f20`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18019501b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180195152`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1801955ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019671a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019671a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180196753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180196753`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18019630f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180196477`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801965b9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18019630f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180196477`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801965b9`
- `ntdll!RtlFreeHeap` at `0x180194f05`
- `ntdll!RtlFreeHeap` at `0x180195005`
- `ntdll!RtlFreeHeap` at `0x180195139`
- `ntdll!RtlFreeHeap` at `0x180195236`
- `ntdll!RtlFreeHeap` at `0x180195275`
- `ntdll!RtlFreeHeap` at `0x1801953af`
- `ntdll!RtlFreeHeap` at `0x1801953c6`
- `ntdll!RtlFreeHeap` at `0x18019556d`
- `ntdll!RtlFreeHeap` at `0x18019558b`
- `ntdll!RtlFreeHeap` at `0x180195741`
- `ntdll!RtlFreeHeap` at `0x18019594a`
- `ntdll!RtlFreeHeap` at `0x1801959d3`
- `ntdll!RtlFreeHeap` at `0x180195a0a`
- `ntdll!RtlFreeHeap` at `0x180195b4a`
- `ntdll!RtlFreeHeap` at `0x180195b61`
- `ntdll!RtlFreeHeap` at `0x180195cc3`
- `ntdll!RtlFreeHeap` at `0x1801963c6`
- `ntdll!RtlFreeHeap` at `0x18019650a`
- `ntdll!RtlFreeHeap` at `0x18019666f`
- `ntdll!RtlFreeHeap` at `0x18019669d`
- `ntdll!RtlFreeHeap` at `0x180196a9e`
- `ntdll!RtlFreeHeap` at `0x180196ab5`
- `ntdll!RtlFreeHeap` at `0x180462d8c`
- `ntdll!RtlFreeHeap` at `0x180462dac`
- `ntdll!RtlFreeHeap` at `0x180194f05`
- `ntdll!RtlFreeHeap` at `0x180195005`
- `ntdll!RtlFreeHeap` at `0x180195139`
- `ntdll!RtlFreeHeap` at `0x180195236`
- `ntdll!RtlFreeHeap` at `0x180195275`
- `ntdll!RtlFreeHeap` at `0x1801953af`
- `ntdll!RtlFreeHeap` at `0x1801953c6`
- `ntdll!RtlFreeHeap` at `0x18019556d`
- `ntdll!RtlFreeHeap` at `0x18019558b`
- `ntdll!RtlFreeHeap` at `0x180195741`
- `ntdll!RtlFreeHeap` at `0x18019594a`
- `ntdll!RtlFreeHeap` at `0x1801959d3`
- `ntdll!RtlFreeHeap` at `0x180195a0a`
- `ntdll!RtlFreeHeap` at `0x180195b4a`
- `ntdll!RtlFreeHeap` at `0x180195b61`
- `ntdll!RtlFreeHeap` at `0x180195cc3`
- `ntdll!RtlFreeHeap` at `0x1801963c6`
- `ntdll!RtlFreeHeap` at `0x18019650a`
- `ntdll!RtlFreeHeap` at `0x18019666f`
- `ntdll!RtlFreeHeap` at `0x18019669d`
- `ntdll!RtlFreeHeap` at `0x180196a9e`
- `ntdll!RtlFreeHeap` at `0x180196ab5`
- `ntdll!RtlFreeHeap` at `0x180462d8c`
- `ntdll!RtlFreeHeap` at `0x180462dac`
- `ntdll!RtlDestroyHeap` at `0x180196ad1`
- `ntdll!RtlDestroyHeap` at `0x180462dd0`
- `ntdll!RtlDestroyHeap` at `0x180196ad1`
- `ntdll!RtlDestroyHeap` at `0x180462dd0`
- `ntdll!RtlNtStatusToDosError` at `0x1801944c7`
- `ntdll!RtlNtStatusToDosError` at `0x18019455f`
- `ntdll!RtlNtStatusToDosError` at `0x1801945aa`
- `ntdll!RtlNtStatusToDosError` at `0x18019463e`
- `ntdll!RtlNtStatusToDosError` at `0x18019480a`
- `ntdll!RtlNtStatusToDosError` at `0x180195789`
- `ntdll!RtlNtStatusToDosError` at `0x180196761`
- `ntdll!RtlNtStatusToDosError` at `0x1801944c7`
- `ntdll!RtlNtStatusToDosError` at `0x18019455f`
- `ntdll!RtlNtStatusToDosError` at `0x1801945aa`
- `ntdll!RtlNtStatusToDosError` at `0x18019463e`
- `ntdll!RtlNtStatusToDosError` at `0x18019480a`
- `ntdll!RtlNtStatusToDosError` at `0x180195789`
- `ntdll!RtlNtStatusToDosError` at `0x180196761`
- `ADVAPI32!ConvertStringSidToSidA` at `0x180196710`
- `ADVAPI32!ConvertStringSidToSidA` at `0x180196710`

## string_xrefs

- `0x180196043`: `CN=Directory Service,CN=Windows NT,CN=Services,`
- `0x1801967e1`: `Service account SID`
- `0x1801966e0`: `Admin SID`

## pseudocode

```c
__int64 __fastcall InstallBaseNTDS(struct _DS_INSTALL_PARAM *a1, void *a2)
{
  __m128i v3; // xmm6
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 result; // rax
  NTSTATUS updated; // r14d
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // r9
  BOOL v14; // ebx
  bool v15; // zf
  int v16; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  LPOVERLAPPED v19; // rsi
  unsigned int v20; // eax
  WCHAR *v21; // rax
  unsigned int ConfigParamLocalWEx; // eax
  NTSTATUS ConfigNCObject; // eax
  PVOID v24; // rbx
  ULONG v25; // eax
  __int64 v26; // rdx
  PVOID v27; // r8
  NTSTATUS DefaultConfigNCDIT; // eax
  NTSTATUS NtdsDsaObject; // eax
  LPOVERLAPPED v30; // rbx
  PVOID v31; // rdx
  int i; // ecx
  DWORD v33; // eax
  __int64 v34; // r15
  LPOVERLAPPED v35; // rbx
  unsigned int inited; // eax
  unsigned int SourceDSInstance; // r15d
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // r8
  __int64 v43; // r9
  BOOL v44; // ebx
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // r8
  __int64 v51; // r9
  BOOL v52; // ebx
  int v53; // eax
  PVOID v54; // rbx
  LPVOID v55; // rax
  unsigned int OwnNtdsaDsaObjectGuid; // eax
  __int64 v57; // rdx
  PCWSTR v58; // r9
  PVOID v59; // r8
  __int64 v60; // rcx
  __int64 v61; // rdx
  struct _DSNAME *v62; // rbx
  void *v63; // rdi
  unsigned int v64; // ebx
  char *v65; // r9
  PVOID v66; // r8
  __int64 v67; // rdx
  __int64 v68; // rdx
  struct _DSNAME *v69; // rsi
  void *v70; // rdi
  __int64 v71; // rbx
  __int64 v72; // rdx
  struct _DSNAME *v73; // rbx
  void *v74; // rdi
  char *v75; // rax
  _DWORD *v76; // rdi
  struct _DS_INSTALL_PARAM *v77; // rbx
  unsigned int v78; // edx
  __int64 v79; // rcx
  _DWORD *v80; // rdi
  unsigned int v81; // eax
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 v86; // r8
  __int64 v87; // r9
  BOOL v88; // ebx
  int v89; // eax
  struct _DS_INSTALL_RESULT *v90; // rdx
  int v91; // eax
  int v92; // eax
  __int64 v93; // rdx
  struct _DSNAME *v94; // rsi
  __int64 v95; // rdx
  struct _CROSS_REF *ExactCrossRef; // rax
  struct _GUID *v97; // rdx
  struct _CROSS_REF *v98; // r8
  struct _GUID *v99; // rcx
  unsigned int v100; // eax
  struct _CROSS_REF *v101; // rbx
  NTSTATUS v102; // eax
  struct _DSNAME *v103; // rcx
  __int64 v104; // rdx
  __int64 v105; // rcx
  __int64 v106; // r8
  __int64 v107; // r9
  __int64 v108; // r8
  __int64 v109; // r9
  BOOL v110; // ebx
  int v111; // eax
  char *v112; // rdi
  unsigned int v113; // edx
  __int64 v114; // rcx
  unsigned int v115; // eax
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // r9
  __int64 v120; // r8
  __int64 v121; // r9
  BOOL v122; // ebx
  int v123; // eax
  __int64 v124; // rdx
  __int64 v125; // rcx
  __int64 v126; // r8
  __int64 v127; // r9
  __int64 v128; // r8
  __int64 v129; // r9
  BOOL v130; // ebx
  int v131; // eax
  unsigned int v132; // eax
  LPVOID v133; // rax
  _QWORD *v134; // rax
  int v135; // ecx
  unsigned int v136; // esi
  struct _DSNAME *v137; // rax
  unsigned int v138; // r10d
  unsigned int v139; // r11d
  struct _DSNAME *v140; // rdi
  __int64 v141; // rdx
  int v142; // ebx
  unsigned int v143; // eax
  int v144; // eax
  struct _DSNAME *v145; // rdx
  struct _THSTATE *v146; // rcx
  __int64 v147; // rdx
  int v148; // ebx
  unsigned int v149; // eax
  int v150; // eax
  __int64 v151; // rcx
  unsigned int v152; // eax
  int v153; // eax
  unsigned int v154; // eax
  int v155; // r8d
  int v156; // r9d
  char *v157; // r9
  DWORD ConfigParamLocal; // eax
  DWORD v159; // ebx
  LPVOID Value; // rax
  LPOVERLAPPED v161; // rbx
  int v162; // ebx
  unsigned int v163; // eax
  int v164; // r8d
  int v165; // r9d
  int v166; // [rsp+9Ch] [rbp-FC4h] BYREF
  DWORD LastError; // [rsp+A0h] [rbp-FC0h]
  _DWORD *v168; // [rsp+A8h] [rbp-FB8h]
  void *v169; // [rsp+B0h] [rbp-FB0h]
  unsigned int v170; // [rsp+B8h] [rbp-FA8h] BYREF
  int v171; // [rsp+BCh] [rbp-FA4h]
  int v172; // [rsp+C0h] [rbp-FA0h] BYREF
  unsigned int v173[2]; // [rsp+C8h] [rbp-F98h]
  struct _DS_INSTALL_PARAM *v174; // [rsp+D0h] [rbp-F90h] BYREF
  LPVOID lpTlsValue; // [rsp+D8h] [rbp-F88h] BYREF
  PVOID P; // [rsp+E0h] [rbp-F80h] BYREF
  int v177; // [rsp+E8h] [rbp-F78h] BYREF
  unsigned __int16 *v178; // [rsp+F0h] [rbp-F70h] BYREF
  unsigned __int16 *v179; // [rsp+F8h] [rbp-F68h] BYREF
  struct _GUID v180; // [rsp+100h] [rbp-F60h] BYREF
  void *v181; // [rsp+110h] [rbp-F50h]
  __int64 v182; // [rsp+118h] [rbp-F48h] BYREF
  int v183; // [rsp+120h] [rbp-F40h]
  __int64 v184; // [rsp+128h] [rbp-F38h] BYREF
  struct _GUID v185; // [rsp+130h] [rbp-F30h] BYREF
  __int64 v186; // [rsp+148h] [rbp-F18h] BYREF
  int v187; // [rsp+150h] [rbp-F10h]
  int Internal; // [rsp+154h] [rbp-F0Ch]
  int v189; // [rsp+158h] [rbp-F08h]
  int v190; // [rsp+160h] [rbp-F00h]
  int v191; // [rsp+164h] [rbp-EFCh]
  __int64 v192; // [rsp+168h] [rbp-EF8h]
  __int64 v193; // [rsp+170h] [rbp-EF0h]
  __int64 v194; // [rsp+178h] [rbp-EE8h]
  __int64 v195; // [rsp+188h] [rbp-ED8h]
  int v196; // [rsp+190h] [rbp-ED0h]
  int *v197; // [rsp+1A0h] [rbp-EC0h]
  __int64 v198; // [rsp+1A8h] [rbp-EB8h] BYREF
  int v199; // [rsp+1B0h] [rbp-EB0h]
  DWORD v200; // [rsp+1B4h] [rbp-EACh]
  int v201; // [rsp+1B8h] [rbp-EA8h]
  int v202; // [rsp+1C0h] [rbp-EA0h]
  int v203; // [rsp+1C4h] [rbp-E9Ch]
  __int64 v204; // [rsp+1C8h] [rbp-E98h]
  __int64 v205; // [rsp+1D0h] [rbp-E90h]
  __int64 v206; // [rsp+1D8h] [rbp-E88h]
  __int64 v207; // [rsp+1E8h] [rbp-E78h]
  int v208; // [rsp+1F0h] [rbp-E70h]
  int *v209; // [rsp+200h] [rbp-E60h]
  __int64 v210; // [rsp+208h] [rbp-E58h] BYREF
  int v211; // [rsp+210h] [rbp-E50h]
  DWORD v212; // [rsp+214h] [rbp-E4Ch]
  int v213; // [rsp+218h] [rbp-E48h]
  __int64 v214; // [rsp+220h] [rbp-E40h]
  int v215; // [rsp+228h] [rbp-E38h]
  int v216; // [rsp+22Ch] [rbp-E34h]
  __int64 v217; // [rsp+230h] [rbp-E30h]
  __int64 v218; // [rsp+238h] [rbp-E28h]
  __int64 v219; // [rsp+248h] [rbp-E18h]
  int v220; // [rsp+250h] [rbp-E10h]
  char *v221; // [rsp+260h] [rbp-E00h]
  __int64 v222; // [rsp+268h] [rbp-DF8h] BYREF
  int v223; // [rsp+270h] [rbp-DF0h]
  DWORD Offset; // [rsp+274h] [rbp-DECh]
  int v225; // [rsp+278h] [rbp-DE8h]
  int v226; // [rsp+280h] [rbp-DE0h]
  int v227; // [rsp+284h] [rbp-DDCh]
  __int64 v228; // [rsp+288h] [rbp-DD8h]
  __int64 v229; // [rsp+290h] [rbp-DD0h]
  __int64 v230; // [rsp+298h] [rbp-DC8h]
  __int64 v231; // [rsp+2A8h] [rbp-DB8h]
  int v232; // [rsp+2B0h] [rbp-DB0h]
  char *v233; // [rsp+2C0h] [rbp-DA0h]
  __int64 v234; // [rsp+2C8h] [rbp-D98h] BYREF
  int v235; // [rsp+2D0h] [rbp-D90h]
  DWORD v236; // [rsp+2D4h] [rbp-D8Ch]
  int v237; // [rsp+2D8h] [rbp-D88h]
  int v238; // [rsp+2E0h] [rbp-D80h]
  int v239; // [rsp+2E4h] [rbp-D7Ch]
  __int64 v240; // [rsp+2E8h] [rbp-D78h]
  __int64 v241; // [rsp+2F0h] [rbp-D70h]
  __int64 v242; // [rsp+2F8h] [rbp-D68h]
  __int64 v243; // [rsp+308h] [rbp-D58h]
  int v244; // [rsp+310h] [rbp-D50h]
  char *v245; // [rsp+320h] [rbp-D40h]
  struct _GUID v246; // [rsp+328h] [rbp-D38h] BYREF
  BYTE Data[32]; // [rsp+338h] [rbp-D28h] BYREF
  _OWORD v248[4]; // [rsp+358h] [rbp-D08h] BYREF
  struct _GUID v249; // [rsp+398h] [rbp-CC8h] BYREF
  _OWORD v250[4]; // [rsp+3A8h] [rbp-CB8h] BYREF
  __int64 v251; // [rsp+3E8h] [rbp-C78h] BYREF
  __m128i v252; // [rsp+3F0h] [rbp-C70h]
  __int64 v253; // [rsp+400h] [rbp-C60h]
  _BYTE v254[28]; // [rsp+408h] [rbp-C58h] BYREF
  _BYTE v255[96]; // [rsp+428h] [rbp-C38h] BYREF
  __int64 v256[4]; // [rsp+488h] [rbp-BD8h] BYREF
  int v257; // [rsp+4A8h] [rbp-BB8h] BYREF
  __int64 *v258; // [rsp+4B0h] [rbp-BB0h]
  __int64 v259; // [rsp+4C0h] [rbp-BA0h] BYREF
  int v260; // [rsp+4C8h] [rbp-B98h]
  __int64 *v261; // [rsp+4D0h] [rbp-B90h]
  __int64 v262; // [rsp+4E0h] [rbp-B80h] BYREF
  int v263; // [rsp+6C8h] [rbp-998h] BYREF
  __int64 *v264; // [rsp+6D0h] [rbp-990h]
  __int64 v265; // [rsp+6E0h] [rbp-980h] BYREF
  char v266; // [rsp+8E8h] [rbp-778h] BYREF
  char v267; // [rsp+B08h] [rbp-558h] BYREF
  char v268; // [rsp+D28h] [rbp-338h] BYREF
  _BYTE v269[24]; // [rsp+F48h] [rbp-118h] BYREF
  _BYTE v270[24]; // [rsp+F60h] [rbp-100h] BYREF
  _BYTE v271[24]; // [rsp+F78h] [rbp-E8h] BYREF
  _BYTE v272[24]; // [rsp+F90h] [rbp-D0h] BYREF
  CHAR v273[32]; // [rsp+FA8h] [rbp-B8h] BYREF
  CHAR StringSid[80]; // [rsp+FC8h] [rbp-98h] BYREF

  lpTlsValue = a2;
  v174 = a1;
  memset(v248, 0, 60);
  memset(v250, 0, 60);
  v166 = 0;
  P = 0;
  v184 = 0;
  v177 = 0;
  v182 = 0;
  v178 = 0;
  v179 = 0;
  v3 = 0;
  v180 = 0;
  gfDoSamChecks = 0;
  *(_DWORD *)gUpdatesEnabled = 1;
  memset_0(&gNames, 0, 0x98u);
  if ( gpfnInstallCancelOk )
  {
    LOBYTE(v5) = 1;
    if ( (unsigned int)gpfnInstallCancelOk(v5) )
    {
      SetInstallErrorMessage(1223, 1073743126, 0, 0);
      return 3221225760LL;
    }
  }
  updated = 0;
  if ( DataSource != 1 )
  {
LABEL_31:
    if ( *(_DWORD *)gfADAM )
    {
      Str = 0;
    }
    else
    {
      v21 = (WCHAR *)DSAllocAux(520, 117508413);
      Str = v21;
      if ( !v21 )
      {
        SetInstallErrorMessage(14, 1073743104, 0, 0);
        return 3221225495LL;
      }
      ConfigParamLocalWEx = GetConfigParamLocalWEx(L"RootDomainDnsName", (LPBYTE)v21, 0x104u, 0);
      if ( ConfigParamLocalWEx )
      {
        SetInstallErrorMessage(ConfigParamLocalWEx, 1073743114, 0, 0);
        return 3221225805LL;
      }
    }
    v168 = 0;
    v19 = 0;
    v169 = 0;
    v170 = 0;
    dword_18052B32C = *((_DWORD *)a1 + 31);
    v20 = InitializeNTDSSetup(a1);
    LastError = v20;
    if ( v20 )
    {
      SetInstallErrorMessage(v20, 1073743104, 0, 0);
      v166 = 1;
LABEL_35:
      updated = -1073741823;
LABEL_438:
      v80 = v168;
      goto LABEL_439;
    }
    if ( qword_180526C70 && *qword_180526C70 || *(_DWORD *)gfADAM && (unsigned int)IsValidDSInstance(qword_180526C80) )
      v170 = 1;
    if ( !(unsigned int)IsValidDSInstance(qword_180526C80) && RecoveryMode != 1 )
    {
      v249 = 0;
      gInstallHasDoneSchemaMove = 0;
      if ( !*(_DWORD *)gfADAM )
      {
        ConfigNCObject = CreateRootDomainObject((unsigned __int16 *)::P, &v249, 0);
        updated = ConfigNCObject;
        if ( ConfigNCObject < 0 )
        {
          v24 = ::P;
LABEL_50:
          v25 = RtlNtStatusToDosError(ConfigNCObject);
          v26 = 1073743100;
LABEL_51:
          v27 = v24;
LABEL_52:
          SetInstallErrorMessage(v25, v26, v27, 0);
LABEL_53:
          v166 = 1;
          goto LABEL_438;
        }
      }
      ConfigNCObject = CreateConfigNCObject((unsigned __int16 *)qword_180526C78);
      updated = ConfigNCObject;
      if ( ConfigNCObject < 0 )
      {
        v24 = qword_180526C78;
        goto LABEL_50;
      }
      ConfigNCObject = CreateSchemaNCObject((unsigned __int16 *)qword_180526C98);
      updated = ConfigNCObject;
      if ( ConfigNCObject < 0 )
      {
        v24 = qword_180526C98;
        goto LABEL_50;
      }
      UpdateCreateNCInstallMessage((unsigned __int16 *)qword_180526C98, 0);
      if ( (unsigned int)DBInitialSetup(qword_180526C98) )
      {
        updated = -1073741823;
        v24 = qword_180526C98;
        v25 = RtlNtStatusToDosError(-1073741823);
        v26 = 3221226871LL;
        goto LABEL_51;
      }
      gInstallHasDoneSchemaMove = 1;
      UpdateCreateNCInstallMessage((unsigned __int16 *)qword_180526C78, 1u);
      DefaultConfigNCDIT = CreateDefaultConfigNCDIT((unsigned __int16 *)qword_180526C78);
      updated = DefaultConfigNCDIT;
      if ( DefaultConfigNCDIT < 0 )
      {
        v24 = qword_180526C78;
LABEL_62:
        v25 = RtlNtStatusToDosError(DefaultConfigNCDIT);
        v26 = 1073743099;
        goto LABEL_51;
      }
      if ( !*(_DWORD *)gfADAM )
      {
        UpdateCreateNCInstallMessage((unsigned __int16 *)::P, 2u);
        DefaultConfigNCDIT = CreateDefaultRootDomainDIT((unsigned __int16 *)::P);
        updated = DefaultConfigNCDIT;
        if ( DefaultConfigNCDIT < 0 )
        {
LABEL_65:
          v24 = ::P;
          goto LABEL_62;
        }
      }
      SetInstallStatusMessage(0x40000540u, 0, 0);
      NtdsDsaObject = CreateNtdsDsaObject(
                        (unsigned __int16 *)qword_180526C90,
                        (__int64)"DEFAULTANYSERVER",
                        (__int64)qword_180526CF0);
      updated = NtdsDsaObject;
      if ( NtdsDsaObject < 0 )
      {
        v24 = qword_180526C90;
        v25 = RtlNtStatusToDosError(NtdsDsaObject);
        v26 = 1073743101;
        goto LABEL_51;
      }
      if ( !*(_DWORD *)gfADAM )
        updated = UpdateSchemaSDsUsingAceTemplates();
      if ( updated >= 0 && !(unsigned int)SetDraReplConsisInstallRegKey() )
      {
        v30 = gpDsEventConfig;
        if ( gpDsEventConfig )
        {
          if ( (gpDsEventConfig[2].OffsetHigh & 0x80000000) != 0
            && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(1793, 0)) )
          {
            if ( !(unsigned int)DoLogMsgOverride(3221227505LL) )
              goto LABEL_425;
            v30 = gpDsEventConfig;
          }
          memset_0(&v222, 0, 0x60u);
          v222 = 0;
          Offset = v30[2].Offset;
          v225 = 0;
          v223 = -1073739791;
          v226 = 0;
          v227 = 1;
          v233 = &v266;
          v230 = 0;
          v229 = 1793;
          v228 = 1;
          v231 = 0;
          v232 = 0;
          DoLogEventAndTrace(&v222);
        }
      }
LABEL_425:
      if ( *(_DWORD *)gfADAM )
      {
LABEL_428:
        memset(Data, 0, 28);
        v170 = 0;
        v159 = GetConfigParamLocalWEx(L"Service account SID", Data, 0x1Cu, 0);
        LastError = v159;
        if ( v159
          || (Value = TlsGetValue(dwTSindex),
              v159 = LookupPrincipalName((__int64)Value, Data, &v182, &v170),
              (LastError = v159) != 0) )
        {
          if ( gpDsEventConfig )
          {
            v256[0] = (__int64)v273;
            v256[1] = (__int64)v272;
            v256[2] = (__int64)v269;
            _o__itow_s(v159, v272, 12);
            _o__itow_s(v159, v273, 12);
            _o__ultow_s(117509981, v269, 9, 16);
            DoLogEventW(1793, gpDsEventConfig[4].Offset, 0, -1073740656, 1, 3u, (__int64)v256, 0, 0);
            v161 = gpDsEventConfig;
            if ( gpDsEventConfig )
            {
              memset_0(&v210, 0, 0x60u);
              v210 = 0;
              v212 = v161[7].Offset;
              v213 = 0;
              v211 = -1073740656;
              v214 = 0;
              v221 = &v268;
              v218 = 0;
              v217 = 1793;
              v215 = 1;
              v216 = 1;
              v219 = 0;
              v220 = 0;
              DoLogEventAndTrace(&v210);
            }
          }
          updated = -1073741823;
          goto LABEL_422;
        }
LABEL_434:
        LastError = NtdsbsrvDllInit(1, *(unsigned int *)gfADAM, gpszServiceName, gpszServiceLongName);
        v19 = 0;
        v169 = 0;
        if ( LastError )
          goto LABEL_438;
        LastError = InstallBackupServices(1, v182);
        v169 = 0;
        if ( LastError )
          goto LABEL_438;
        v172 = 0;
        v174 = 0;
        GarbageCollectionMain(0, &v174, &v172);
        goto LABEL_437;
      }
      goto LABEL_426;
    }
    memset_0(v255, 0, 0x54u);
    v185 = 0;
    v31 = 0;
    v181 = 0;
    v172 = *((_DWORD *)a1 + 31) != 0 ? 272638048 : 268435568;
    for ( i = 0; ; ++i )
    {
      v183 = i;
      if ( i >= 84 )
        break;
      v255[i] = -1;
    }
    giInstallReplAuthenticationMode = *((_DWORD *)a1 + 30);
    if ( DomainName )
    {
      if ( *(_WORD *)DomainName )
        v31 = DomainName;
      v181 = v31;
    }
    gInstallHasDoneSchemaMove = 0;
    if ( DataSource != 1 && (unsigned int)DBInitialSetup(0) )
    {
      updated = -1073741823;
      v25 = RtlNtStatusToDosError(-1073741823);
      v27 = 0;
      v26 = 3221226871LL;
      goto LABEL_52;
    }
    gInstallHasDoneSchemaMove = 1;
    if ( *(_DWORD *)gfADAM )
    {
      v35 = 0;
LABEL_101:
      TlsGetValue(dwTSindex);
      inited = InitDRA();
      SourceDSInstance = inited;
      LastError = inited;
      if ( inited )
      {
        DoLogUnhandledError2(117508715, &word_18049B11A, inited, 1);
        updated = -1073741823;
        SetInstallErrorMessage(3221225473LL, 1073743104, 0, 0);
LABEL_103:
        v166 = 1;
        goto LABEL_438;
      }
      if ( DataSource == 1 )
      {
        if ( RecoveryMode == 1 )
        {
          v173[0] = InstallDisasterRecovery(a1);
          if ( v173[0] )
          {
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
              || (unsigned int)THStateCheckForTraceOverride(v39, v38)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v39, v38)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v39, v38, v40, v41)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16)) )
            {
              v44 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v39, v38)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier(v39, v38, v42, v43)
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16));
              if ( (unsigned int)THStateCheckForTraceOverride(v39, v38)
                || (v15 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16) == 0, v45 = 0, !v15) )
              {
                v45 = 1;
              }
              WPP_SF__ATTRTYP_LOG_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                117508757,
                2,
                16,
                v45,
                v44,
                23,
                (__int64)&WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
            }
            goto LABEL_35;
          }
          v3 = *(__m128i *)((char *)qword_18052B2A8 + 8);
          v180 = (struct _GUID)v3;
        }
        else
        {
          updated = CreateDummyNtdsDsaObject();
          if ( updated < 0 )
            goto LABEL_103;
          updated = CopyDsaAttributes(a1, (struct _DSNAME *)v250, qword_18052B2A8, 0);
          if ( updated < 0 )
            goto LABEL_103;
        }
        LODWORD(v248[0]) = 58;
        *(_OWORD *)((char *)v248 + 8) = *(_OWORD *)((char *)qword_18052B2A8 + 8);
      }
      if ( RecoveryMode != 1 )
      {
        updated = UpdateReplicationEpochAndHiddenDSA(qword_18052B2A8, *((_DWORD *)a1 + 4), 0);
        if ( updated < 0 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v47, v46)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v47, v46)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v47, v46, v48, v49)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16)) )
          {
            v52 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v47, v46)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v47, v46, v50, v51)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16));
            if ( (unsigned int)THStateCheckForTraceOverride(v47, v46)
              || (v15 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16) == 0, v53 = 0, !v15) )
            {
              v53 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              117508799,
              2,
              16,
              v53,
              v52,
              24,
              (__int64)&WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
          }
          goto LABEL_53;
        }
        if ( RecoveryMode != 1 )
        {
          v54 = qword_180526C80;
          v55 = TlsGetValue(dwTSindex);
          OwnNtdsaDsaObjectGuid = I_DRSEnableOptionalFeaturesAtInstall(v55, v54);
          SourceDSInstance = OwnNtdsaDsaObjectGuid;
          LastError = OwnNtdsaDsaObjectGuid;
          v35 = 0;
          if ( OwnNtdsaDsaObjectGuid )
          {
            v57 = 1073744840;
LABEL_150:
            v58 = 0;
            v59 = 0;
LABEL_151:
            v60 = OwnNtdsaDsaObjectGuid;
LABEL_152:
            SetInstallErrorMessage(v60, v57, v59, v58);
            updated = -1073741823;
            goto LABEL_103;
          }
        }
      }
      if ( v170 != (_DWORD)v35 )
      {
        SetInstallStatusMessage(0x400005A1u, (__int64)v35, (__int64)v35);
        if ( *((_DWORD *)a1 + 32) == (_DWORD)v35 && gfIsClone == (_DWORD)v35 )
        {
          SourceDSInstance = CreateRemoteNtdsDsaInfra(&v180);
          LastError = SourceDSInstance;
          if ( SourceDSInstance )
          {
            if ( *((_DWORD *)qword_180526C80 + 3) == (_DWORD)v35 )
              v58 = (PCWSTR)v35;
            else
              v58 = (PCWSTR)((char *)qword_180526C80 + *((unsigned int *)qword_180526C80 + 3));
            v59 = qword_180526C90;
            v57 = 1073743264;
            v60 = SourceDSInstance;
            goto LABEL_152;
          }
          *((_DWORD *)lpTlsValue + 1) |= 1u;
        }
        else
        {
          OwnNtdsaDsaObjectGuid = GetOwnNtdsaDsaObjectGuid(a1, &v180);
          SourceDSInstance = OwnNtdsaDsaObjectGuid;
          LastError = OwnNtdsaDsaObjectGuid;
          if ( OwnNtdsaDsaObjectGuid )
          {
            v58 = qword_180526C70;
            v59 = qword_180526C90;
            v57 = 1073744651;
            goto LABEL_151;
          }
        }
        v3 = (__m128i)v180;
      }
      if ( *((_DWORD *)a1 + 31) != (_DWORD)v35 && *((_DWORD *)a1 + 32) == (_DWORD)v35 )
      {
        OwnNtdsaDsaObjectGuid = CreateRemoteConnectionsObject((void **)a1);
        SourceDSInstance = OwnNtdsaDsaObjectGuid;
        LastError = OwnNtdsaDsaObjectGuid;
        if ( OwnNtdsaDsaObjectGuid )
        {
          v57 = 3221228325LL;
          goto LABEL_150;
        }
      }
      if ( RecoveryMode == 1 )
      {
        v19 = 0;
      }
      else
      {
        SetInstallStatusMessage(0x4000053Au, (__int64)v35, (__int64)v35);
        v61 = -1;
        do
          ++v61;
        while ( *((_WORD *)qword_180526C98 + v61) != (_WORD)v35 );
        v62 = (struct _DSNAME *)XCalloc(1u, 2 * (int)v61 + 58);
        BuildDefDSName(v62, (unsigned __int16 *)qword_180526C98, 0);
        v63 = InstallTHSave();
        v173[0] = DirReplicaAdd((__int64)v62, v181, v255, v172 | 0x80000000);
        RtlFreeHeap(ghInstallHeap, 0, v62);
        v19 = 0;
        v169 = 0;
        free_thread_state();
        TlsSetValue(dwTSindex, v63);
        v64 = v173[0];
        if ( v173[0] )
        {
          if ( *((_DWORD *)qword_180526C80 + 3) )
            v65 = (char *)qword_180526C80 + *((unsigned int *)qword_180526C80 + 3);
          else
            v65 = 0;
          v66 = qword_180526C98;
LABEL_177:
          v67 = 1073743098;
LABEL_178:
          SetInstallErrorMessage(v64, v67, v66, v65);
          updated = DirReplicaErrorToNtStatus(v64);
          goto LABEL_53;
        }
        SetInstallStatusMessage(0x4000070Eu, 0, 0);
        v68 = -1;
        do
          ++v68;
        while ( *((_WORD *)qword_180526C98 + v68) );
        v69 = (struct _DSNAME *)XCalloc(1u, 2 * (int)v68 + 58);
        BuildDefDSName(v69, (unsigned __int16 *)qword_180526C98, 0);
        v70 = InstallTHSave();
        v71 = qword_18052B280;
        qword_18052B280 = (__int64)v69;
        v173[0] = SCUpdateSchema();
        qword_18052B280 = v71;
        RtlFreeHeap(ghInstallHeap, 0, v69);
        v19 = 0;
        v169 = 0;
        TlsSetValue(dwTSindex, v70);
        v64 = v173[0];
        if ( v173[0] )
        {
          if ( *((_DWORD *)qword_180526C80 + 3) )
            v65 = (char *)qword_180526C80 + *((unsigned int *)qword_180526C80 + 3);
          else
            v65 = 0;
          v66 = qword_180526C98;
          v67 = 1073743681;
          goto LABEL_178;
        }
        SetInstallStatusMessage(0x40000742u, 0, 0);
      }
      if ( RecoveryMode == 1 )
        goto LABEL_283;
      SetInstallStatusMessage(0x4000053Cu, 0, 0);
      v72 = -1;
      do
        ++v72;
      while ( *((_WORD *)qword_180526C78 + v72) );
      v73 = (struct _DSNAME *)XCalloc(1u, 2 * (int)v72 + 58);
      BuildDefDSName(v73, (unsigned __int16 *)qword_180526C78, 0);
      v74 = InstallTHSave();
      v173[0] = DirReplicaAdd((__int64)v73, v181, v255, v172);
      RtlFreeHeap(ghInstallHeap, 0, v73);
      v169 = 0;
      free_thread_state();
      TlsSetValue(dwTSindex, v74);
      v64 = v173[0];
      if ( v173[0] )
      {
        if ( *((_DWORD *)qword_180526C80 + 3) )
          v65 = (char *)qword_180526C80 + *((unsigned int *)qword_180526C80 + 3);
        else
          v65 = 0;
        v66 = qword_180526C78;
        goto LABEL_177;
      }
      v19 = 0;
      SetInstallStatusMessage(0x4000070Fu, 0, 0);
      if ( RecoveryMode == 1 || *(_DWORD *)gfADAM )
      {
LABEL_283:
        v77 = v174;
      }
      else if ( qword_180526C70 && *qword_180526C70 )
      {
        v75 = (char *)XCalloc(1u, 0x3Au);
        v76 = v75;
        v168 = v75;
        *(_DWORD *)v75 = 58;
        *(__m128i *)(v75 + 8) = v3;
        v77 = v174;
        if ( DataSource == 1 )
        {
          updated = CopyDsaAttributes(v174, (struct _DSNAME *)v248, (struct _DSNAME *)v75, 1);
          if ( updated < 0 )
          {
            RtlFreeHeap(ghInstallHeap, 0, v76);
LABEL_203:
            v168 = 0;
            v166 = 1;
LABEL_204:
            v80 = 0;
LABEL_205:
            v19 = 0;
LABEL_206:
            v169 = 0;
LABEL_439:
            gfDoSamChecks = 1;
            v162 = v182;
            if ( v182 )
            {
              v163 = (unsigned int)TlsGetValue(dwTSindex);
              THFreeAux(v163, v162, v164, v165, 117510022);
            }
            if ( v178 )
              THFree(v178);
            if ( v179 )
              THFree(v179);
            if ( v19 )
              RtlFreeHeap(ghInstallHeap, 0, v19);
            if ( v80 )
              RtlFreeHeap(ghInstallHeap, 0, v80);
            InstallFreeGlobals();
            CleanupIniCache();
            if ( ghInstallHeap )
            {
              RtlDestroyHeap(ghInstallHeap);
              ghInstallHeap = 0;
            }
            ZapTempRegKeys();
            if ( gpfnInstallCancelOk && (unsigned int)gpfnInstallCancelOk(0) )
            {
              SetInstallErrorMessage(1223, 1073743126, 0, 0);
              updated = -1073741536;
            }
            if ( updated < 0 && !v166 )
              SetInstallErrorMessage(8200, 1073743126, 0, 0);
            return (unsigned int)updated;
          }
          v81 = DeleteDummyNtdsDsaObject(v79, v78);
          if ( v81 )
          {
            LastError = v81;
            RtlFreeHeap(ghInstallHeap, 0, v76);
            v168 = 0;
            goto LABEL_204;
          }
        }
        updated = UpdateReplicationEpochAndHiddenDSA((struct _DSNAME *)v76, *((_DWORD *)v174 + 4), 1);
        if ( updated < 0 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v83, v82)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v83, v82)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v83, v82, v84, v85)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16)) )
          {
            v88 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v83, v82)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v83, v82, v86, v87)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16));
            if ( (unsigned int)THStateCheckForTraceOverride(v83, v82)
              || (v15 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16) == 0, v89 = 0, !v15) )
            {
              v89 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              117509321,
              2,
              16,
              v89,
              v88,
              26,
              (__int64)&WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
          }
LABEL_227:
          RtlFreeHeap(ghInstallHeap, 0, v76);
          goto LABEL_203;
        }
        RtlFreeHeap(ghInstallHeap, 0, v76);
        v80 = 0;
        v168 = 0;
        if ( *((_DWORD *)v174 + 32) || gfIsClone )
          v91 = ConfirmMachineAccount(v174, v90);
        else
          v91 = ConvertMachineAccount(v174, (struct _DS_INSTALL_RESULT *)lpTlsValue);
        if ( v91 )
          goto LABEL_233;
        if ( *((_DWORD *)v174 + 31) )
        {
          if ( *((_DWORD *)v174 + 32) )
          {
            SetInstallStatusMessage(0x40000B08u, 0, 0);
            v92 = DsRODCCheckStateObjects(v174, &v178, &v179);
          }
          else
          {
            SetInstallStatusMessage(0x40000AF4u, 0, 0);
            v92 = DsRODCCreateStateObjects(v174, &v180, &v178, &v179);
          }
          if ( v92 )
            goto LABEL_233;
        }
        SetInstallStatusMessage(0x4000053Eu, 0, 0);
        v93 = -1;
        do
          ++v93;
        while ( *((_WORD *)::P + v93) );
        v94 = (struct _DSNAME *)XCalloc(1u, 2 * (int)v93 + 58);
        v169 = v94;
        BuildDefDSName(v94, (unsigned __int16 *)::P, 0);
        v172 |= 0x400u;
        lpTlsValue = InstallTHSave();
        P = (PVOID)DSInstanceFromNTDSAddrEx(qword_180526C70, XCallocFunc);
        v170 = DirReplicaAdd((__int64)v94, v181, v255, v172);
        if ( P )
        {
          RtlFreeHeap(ghInstallHeap, 0, P);
          P = 0;
        }
        RtlFreeHeap(ghInstallHeap, 0, v94);
        v19 = 0;
        v169 = 0;
        free_thread_state();
        TlsSetValue(dwTSindex, lpTlsValue);
        if ( v170 )
        {
          SetInstallErrorMessage(v170, 1073743098, ::P, qword_180526C70);
          updated = DirReplicaErrorToNtStatus(v170);
          v166 = 1;
          goto LABEL_439;
        }
        SetInstallStatusMessage(0x40000710u, 0, 0);
        if ( DataSource != 1 )
          goto LABEL_312;
        updated = RenameAdditionalMachineAccountsIfAny(&v166);
        if ( updated < 0 )
          goto LABEL_439;
      }
      else
      {
        *(_QWORD *)&v246.Data1 = 0;
        v246.Data4[0] = 0;
        *(_DWORD *)&v246.Data4[1] = 0;
        *(_WORD *)&v246.Data4[5] = 0;
        v246.Data4[7] = 0;
        v95 = -1;
        do
          ++v95;
        while ( *((_WORD *)::P + v95) );
        v19 = (LPOVERLAPPED)XCalloc(1u, 2 * (int)v95 + 58);
        v169 = v19;
        BuildDefDSName((struct _DSNAME *)v19, (unsigned __int16 *)::P, 0);
        ExactCrossRef = (struct _CROSS_REF *)FindExactCrossRef(v19);
        v98 = ExactCrossRef;
        if ( ExactCrossRef && !(unsigned int)fNullUuid(*(_QWORD *)ExactCrossRef + 8LL) )
          v246 = *v99;
        v64 = CreateChildDomainCrossRef((struct _DS_INSTALL_RESULT *)lpTlsValue, v97, v98, &v180);
        if ( v64 )
        {
          v65 = 0;
          v66 = ::P;
          v67 = 1073743102;
          goto LABEL_178;
        }
        v100 = CheckForDuplicateDomainSid();
        if ( v100 )
        {
          SetInstallErrorMessage(v100, 1073743247, 0, 0);
          updated = -1073741823;
          goto LABEL_53;
        }
        v101 = (struct _CROSS_REF *)FindExactCrossRef(v19);
        RtlFreeHeap(ghInstallHeap, 0, v19);
        v19 = 0;
        v169 = 0;
        UpdateCreateNCInstallMessage((unsigned __int16 *)::P, 2u);
        v102 = CreateRootDomainObject((unsigned __int16 *)::P, &v246, v101);
        updated = v102;
        if ( v102 < 0 )
        {
          v24 = ::P;
          v25 = RtlNtStatusToDosError(v102);
          v26 = 1073743102;
          goto LABEL_51;
        }
        DefaultConfigNCDIT = CreateDefaultRootDomainDIT((unsigned __int16 *)::P);
        updated = DefaultConfigNCDIT;
        if ( DefaultConfigNCDIT < 0 )
          goto LABEL_65;
        OwnNtdsaDsaObjectGuid = ForceChangeToDomainCrossRef(v103, (unsigned __int16 *)::P, &v246);
        SourceDSInstance = OwnNtdsaDsaObjectGuid;
        LastError = OwnNtdsaDsaObjectGuid;
        if ( OwnNtdsaDsaObjectGuid )
        {
          v58 = 0;
          v59 = ::P;
          v57 = 1073743099;
          goto LABEL_151;
        }
        v80 = XCalloc(1u, 0x3Au);
        v168 = v80;
        *v80 = 58;
        v3 = (__m128i)v180;
        *(struct _GUID *)(v80 + 2) = v180;
        v77 = v174;
        updated = UpdateReplicationEpochAndHiddenDSA((struct _DSNAME *)v80, *((_DWORD *)v174 + 4), 1);
        if ( updated < 0 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v105, v104)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v105, v104)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v105, v104, v106, v107)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16)) )
          {
            v110 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v105, v104)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v105, v104, v108, v109)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16));
            if ( (unsigned int)THStateCheckForTraceOverride(v105, v104)
              || (v15 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16) == 0, v111 = 0, !v15) )
            {
              v111 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              117509262,
              2,
              16,
              v111,
              v110,
              25,
              (__int64)&WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
          }
          v166 = 1;
          goto LABEL_439;
        }
        RtlFreeHeap(ghInstallHeap, 0, v80);
        v168 = 0;
      }
      if ( DataSource == 1 )
      {
        if ( *(_DWORD *)gfADAM && RecoveryMode != 1 )
        {
          v112 = (char *)XCalloc(1u, 0x3Au);
          v168 = v112;
          *(_DWORD *)v112 = 58;
          *(__m128i *)(v112 + 8) = v3;
          updated = CopyDsaAttributes(v77, (struct _DSNAME *)v248, (struct _DSNAME *)v112, 1);
          v19 = 0;
          if ( updated < 0 )
          {
LABEL_288:
            RtlFreeHeap(ghInstallHeap, 0, v112);
            v80 = 0;
            v168 = 0;
            v166 = 1;
            goto LABEL_206;
          }
          v115 = DeleteDummyNtdsDsaObject(v114, v113);
          if ( v115 )
          {
            LastError = v115;
            RtlFreeHeap(ghInstallHeap, 0, v112);
            v80 = 0;
            v168 = 0;
            goto LABEL_206;
          }
          updated = UpdateReplicationEpochAndHiddenDSA((struct _DSNAME *)v112, *((_DWORD *)v77 + 4), 1);
          if ( updated < 0 )
          {
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
              || (unsigned int)THStateCheckForTraceOverride(v117, v116)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v117, v116)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v117, v116, v118, v119)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16)) )
            {
              v122 = gfTraceToSecondProvider
                  && ((unsigned int)THStateCheckForTraceOverride(v117, v116)
                   || (unsigned int)ThStateCheckIfTraceToSecondProvier(v117, v116, v120, v121)
                   && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16));
              if ( (unsigned int)THStateCheckForTraceOverride(v117, v116)
                || (v15 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16) == 0, v123 = 0, !v15) )
              {
                v123 = 1;
              }
              WPP_SF__ATTRTYP_LOG_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                117509512,
                2,
                16,
                v123,
                v122,
                27,
                (__int64)&WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
            }
            goto LABEL_288;
          }
          RtlFreeHeap(ghInstallHeap, 0, v112);
          v168 = 0;
        }
        v80 = 0;
        v168 = 0;
        goto LABEL_331;
      }
LABEL_312:
      v76 = XCalloc(1u, 0x3Au);
      v168 = v76;
      *v76 = 58;
      *(__m128i *)(v76 + 2) = v3;
      v19 = 0;
      SetInstallStatusMessage(0x4000053Eu, 0, 0);
      updated = UpdateReplicationEpochAndHiddenDSA((struct _DSNAME *)v76, *((_DWORD *)v77 + 4), 1);
      if ( updated < 0 )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v125, v124)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v125, v124)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v125, v124, v126, v127)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16)) )
        {
          v130 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v125, v124)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v125, v124, v128, v129)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 16));
          if ( (unsigned int)THStateCheckForTraceOverride(v125, v124)
            || (v15 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 16) == 0, v131 = 0, !v15) )
          {
            v131 = 1;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            117509548,
            2,
            16,
            v131,
            v130,
            28,
            (__int64)&WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
        }
        goto LABEL_227;
      }
      RtlFreeHeap(ghInstallHeap, 0, v76);
      v80 = 0;
      v168 = 0;
      RebuildAnchor(0, &v184, &v177);
      DeriveConfigurationAndPartitionsDNs();
LABEL_331:
      RebuildAnchor(0, &v184, &v177);
      if ( *((_DWORD *)v77 + 32) || gfIsClone )
      {
        v132 = FixupInvocationIDOnNtdsa();
        SourceDSInstance = v132;
        LastError = v132;
        if ( v132 )
        {
          updated = -1073741823;
          SetInstallErrorMessage(v132, 1073744654, 0, 0);
          goto LABEL_234;
        }
      }
      if ( dword_18052B3E0 < 2 )
      {
        v134 = (_QWORD *)*((_QWORD *)v77 + 14);
        if ( v134 && *v134 || *((_QWORD *)v77 + 8) && !*((_DWORD *)v77 + 19) )
        {
          v19 = gpDsEventConfig;
          if ( gpDsEventConfig )
          {
            if ( (gpDsEventConfig[2].OffsetHigh & 0x80000000) != 0
              && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(1793, 0)) )
            {
              v19 = 0;
              if ( !(unsigned int)DoLogMsgOverride(2147485763LL) )
                goto LABEL_351;
              v19 = gpDsEventConfig;
            }
            memset_0(&v198, 0, 0x60u);
            v198 = 0;
            v200 = v19[2].Offset;
            v19 = 0;
            v201 = 0;
            v199 = -2147481533;
            v202 = 0;
            v203 = 1;
            v209 = &v263;
            v263 = 4;
            v265 = 117509638;
            v264 = &v265;
            v198 = 1;
            v206 = 0;
            v205 = 1793;
            v204 = 1;
            v207 = 0;
            v208 = 0;
            DoLogEventAndTrace(&v198);
          }
        }
LABEL_351:
        if ( gfOptionalFeatureEnabledDuringInstall != (_DWORD)v19 && Src == (struct _DSNAME *)v19 )
        {
          if ( !qword_18052B2F0 )
            goto LABEL_375;
          v135 = *((_DWORD *)qword_18052B2F0 + 13);
          if ( !v135 )
            goto LABEL_375;
          v170 = v135 + 47;
          v136 = 2 * (v135 + 47) + 58;
          v137 = (struct _DSNAME *)DSAllocAux(v136, 117509675);
          Src = v137;
          if ( !v137 )
          {
            if ( gpDsEventConfig )
            {
              *(_QWORD *)&v185.Data1 = v271;
              *(_QWORD *)v185.Data4 = v270;
              _o__itow_s(2 * v170 + 58, v271, 12);
              _o__ultow_s(117509678, v270, 9, 16);
              DoLogEventW(1793, gpDsEventConfig[4].Offset, 0, -1073740655, 1, 2u, (__int64)&v185, 0, 0);
            }
            updated = -1073741823;
            goto LABEL_205;
          }
          memset_0(v137, 0, v136);
          *(_DWORD *)Src = v136;
          v138 = v170;
          *((_DWORD *)Src + 13) = v170;
          StringCchCopyW((unsigned __int16 *)Src + 28, v138 + 1, L"CN=Directory Service,CN=Windows NT,CN=Services,");
          StringCchCatW((unsigned __int16 *)Src + 28, v139, (const unsigned __int16 *)qword_18052B2F0 + 28);
          v19 = 0;
        }
        if ( *((_DWORD *)v77 + 31) == (_DWORD)v19
          || (SetInstallStatusMessage(0x40000AF5u, (__int64)v19, (__int64)v19),
              !DsReplicateInSecrets((const unsigned __int16 *)::P, v178))
          && !DsReplicateInSecrets((const unsigned __int16 *)::P, v179) )
        {
          if ( updated >= 0 && !(unsigned int)SetDraReplConsisInstallRegKey() )
          {
            v19 = gpDsEventConfig;
            if ( gpDsEventConfig )
            {
              if ( (gpDsEventConfig[2].OffsetHigh & 0x80000000) != 0
                && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(1793, 0)) )
              {
                v19 = 0;
                if ( !(unsigned int)DoLogMsgOverride(3221227505LL) )
                  goto LABEL_372;
                v19 = gpDsEventConfig;
              }
              memset_0(&v234, 0, 0x60u);
              v234 = 0;
              v236 = v19[2].Offset;
              v19 = 0;
              v237 = 0;
              v235 = -1073739791;
              v238 = 0;
              v239 = 1;
              v245 = &v267;
              v242 = 0;
              v241 = 1793;
              v240 = 1;
              v243 = 0;
              v244 = 0;
              DoLogEventAndTrace(&v234);
            }
          }
LABEL_372:
          if ( RecoveryMode == 1 )
            goto LABEL_414;
          v253 = 0;
          memset(v254, 0, sizeof(v254));
          v252 = v3;
          v251 = 58;
          *(_QWORD *)v173 = DSInstanceFromNameDNSRoot(&v251, Str, THAllocSizeT);
          if ( !*(_QWORD *)v173 )
          {
            SetInstallErrorMessage(8409, 1073743121, 0, 0);
            updated = -1073741801;
            goto LABEL_234;
          }
          v140 = (struct _DSNAME *)v19;
          if ( !SourceDSInstance )
          {
            v141 = -1;
            do
              ++v141;
            while ( *((_WORD *)qword_180526C98 + v141) != (_WORD)v19 );
            v140 = (struct _DSNAME *)XCalloc(1u, 2 * (int)v141 + 58);
            v169 = v140;
            BuildDefDSName(v140, (unsigned __int16 *)qword_180526C98, 0);
            SourceDSInstance = (unsigned int)v19;
            LastError = (unsigned int)v19;
            if ( *((_DWORD *)v77 + 32) == (_DWORD)v19 )
            {
              v171 = 2;
              do
              {
                v142 = (int)qword_180526C80;
                v143 = (unsigned int)TlsGetValue(dwTSindex);
                SourceDSInstance = I_DRSUpdateRefsEx(v143, v142, (_DWORD)v140, v173[0], (__int64)&v180, 28);
                LastError = SourceDSInstance;
                if ( SourceDSInstance != 8438 )
                  break;
                Sleep(0x3E8u);
                v144 = v171--;
              }
              while ( v144 > 0 );
              v77 = v174;
            }
            if ( SourceDSInstance )
              goto LABEL_397;
            TlsGetValue(dwTSindex);
            SourceDSInstance = GetSourceDSInstance(v146, v145, &v185, (struct _DSA_RPC_INST **)&P);
            LastError = SourceDSInstance;
            if ( SourceDSInstance )
              goto LABEL_397;
            SourceDSInstance = DirReplicaModify((_DWORD)v140, (unsigned int)&v185, 0, (_DWORD)P, 0, 0, 2, 0);
            LastError = SourceDSInstance;
          }
          if ( !SourceDSInstance )
          {
            RtlFreeHeap(ghInstallHeap, 0, v140);
            v169 = 0;
            v147 = -1;
            do
              ++v147;
            while ( *((_WORD *)qword_180526C78 + v147) );
            v140 = (struct _DSNAME *)XCalloc(1u, 2 * (int)v147 + 58);
            v169 = v140;
            BuildDefDSName(v140, (unsigned __int16 *)qword_180526C78, 0);
            SourceDSInstance = 0;
            LastError = 0;
            if ( !*((_DWORD *)v77 + 32) )
            {
              v171 = 2;
              do
              {
                v148 = (int)qword_180526C80;
                v149 = (unsigned int)TlsGetValue(dwTSindex);
                SourceDSInstance = I_DRSUpdateRefsEx(v149, v148, (_DWORD)v140, v173[0], (__int64)&v180, 28);
                LastError = SourceDSInstance;
                if ( SourceDSInstance != 8438 )
                  break;
                Sleep(0x3E8u);
                v150 = v171--;
              }
              while ( v150 > 0 );
              v77 = v174;
            }
            if ( !SourceDSInstance )
            {
              SourceDSInstance = DirReplicaModify((_DWORD)v140, (unsigned int)&v185, 0, (_DWORD)P, 0, 0, 2, 0);
              LastError = SourceDSInstance;
            }
          }
LABEL_397:
          if ( !*(_DWORD *)gfADAM && !SourceDSInstance && *qword_180526C70 )
          {
            RtlFreeHeap(ghInstallHeap, 0, v140);
            v169 = 0;
            v151 = -1;
            do
              ++v151;
            while ( *((_WORD *)::P + v151) );
            v140 = (struct _DSNAME *)XCalloc(1u, 2 * (int)v151 + 58);
            v169 = v140;
            BuildDefDSName(v140, (unsigned __int16 *)::P, 0);
            SourceDSInstance = 0;
            LastError = 0;
            if ( !*((_DWORD *)v77 + 32) )
            {
              v171 = 2;
              do
              {
                v152 = (unsigned int)TlsGetValue(dwTSindex);
                SourceDSInstance = I_DRSUpdateRefsEx(v152, (_DWORD)P, (_DWORD)v140, v173[0], (__int64)&v180, 28);
                LastError = SourceDSInstance;
                if ( SourceDSInstance != 8438 )
                  break;
                Sleep(0x3E8u);
                v153 = v171--;
              }
              while ( v153 > 0 );
            }
            if ( !SourceDSInstance )
            {
              SourceDSInstance = DirReplicaModify((_DWORD)v140, (unsigned int)&v185, 0, (_DWORD)P, 0, 0, 2, 0);
              LastError = SourceDSInstance;
            }
          }
          v154 = (unsigned int)TlsGetValue(dwTSindex);
          THFreeAux(v154, v173[0], v155, v156, 117509899);
          if ( SourceDSInstance )
          {
            if ( *((_DWORD *)qword_180526C80 + 3) )
              v157 = (char *)qword_180526C80 + *((unsigned int *)qword_180526C80 + 3);
            else
              v157 = 0;
            SetInstallErrorMessage(SourceDSInstance, 1073744706, (char *)v140 + 56, v157);
            RtlFreeHeap(ghInstallHeap, 0, v140);
            v19 = 0;
            v169 = 0;
            updated = DirReplicaErrorToNtStatus(SourceDSInstance);
            goto LABEL_103;
          }
          RtlFreeHeap(ghInstallHeap, 0, v140);
          v169 = 0;
LABEL_414:
          if ( !*(_DWORD *)gfADAM )
          {
LABEL_426:
            BYTE6(gdbfDataBaseFlags) = 49;
            if ( !(unsigned int)dbSetHiddenFlags() )
            {
              if ( !*(_DWORD *)gfADAM )
                goto LABEL_434;
              goto LABEL_428;
            }
LABEL_418:
            updated = -1073741823;
LABEL_419:
            v19 = 0;
LABEL_437:
            v169 = 0;
            goto LABEL_438;
          }
          v173[0] = 0;
          ConfigParamLocal = GetConfigParamLocalEx((__int64)"Admin SID", (LPBYTE)StringSid);
          LastError = ConfigParamLocal;
          if ( ConfigParamLocal )
          {
            if ( ConfigParamLocal != 2 )
              goto LABEL_418;
            LastError = 0;
          }
          else
          {
            lpTlsValue = 0;
            if ( !ConvertStringSidToSidA(StringSid, &lpTlsValue) )
            {
              LastError = GetLastError();
              goto LABEL_418;
            }
            updated = ADAMAddAdministratorSid(lpTlsValue);
            LocalFree(lpTlsValue);
            if ( updated < 0 )
            {
              LastError = RtlNtStatusToDosError(updated);
              SetInstallErrorMessage(LastError, 1073743126, 0, 0);
LABEL_422:
              v166 = 1;
              goto LABEL_419;
            }
          }
          goto LABEL_425;
        }
LABEL_375:
        updated = -1073741823;
        goto LABEL_205;
      }
      CatalogRebuild(0, &v184, &v177);
      v133 = TlsGetValue(dwTSindex);
      DsaEnableLinkedValueReplication(v133, 0);
      if ( v3.m128i_i64[0] == *((_QWORD *)qword_18052B2A8 + 1)
        && _mm_srli_si128(v3, 8).m128i_u64[0] == *((_QWORD *)qword_18052B2A8 + 2) )
      {
        UpdateAppNCs(*((unsigned __int16 ***)v77 + 14), *((_DWORD *)v77 + 19));
        goto LABEL_351;
      }
      LastError = 87;
LABEL_233:
      updated = -1073741823;
LABEL_234:
      v166 = 1;
      goto LABEL_205;
    }
    v33 = DRSFlushKerberosTicketCache();
    v34 = v33;
    LastError = v33;
    v35 = 0;
    if ( !v33 )
      goto LABEL_101;
    v35 = gpDsEventConfig;
    if ( gpDsEventConfig )
    {
      if ( SHIDWORD(gpDsEventConfig[11].Internal) >= 1
        || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(1793, 1) )
      {
        goto LABEL_98;
      }
      v35 = 0;
      if ( (unsigned int)DoLogMsgOverride(3221227466LL) )
      {
        v35 = gpDsEventConfig;
LABEL_98:
        memset_0(&v186, 0, 0x60u);
        v186 = 0;
        Internal = v35[11].Internal;
        v189 = 1;
        v187 = -1073739830;
        v35 = 0;
        v190 = 0;
        v191 = 1;
        v197 = &v257;
        v257 = 10;
        v259 = v34;
        v258 = &v259;
        v260 = 5;
        v262 = v34;
        v261 = &v262;
        v186 = 2;
        v194 = 0;
        v193 = 1793;
        v192 = 1;
        v195 = 0;
        v196 = 0;
        DoLogEventAndTrace(&v186);
      }
    }
    LastError = (unsigned int)v35;
    goto LABEL_101;
  }
  if ( (unsigned int)THStateCheckForTraceOverride(v5, v4)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 16)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v9, v8)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v9, v8, v10, v11)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 16)) )
  {
    v14 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v9, v8)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v9, v8, v12, v13)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 16));
    if ( (unsigned int)THStateCheckForTraceOverride(v9, v8)
      || (v15 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 16) == 0, v16 = 0, !v15) )
    {
      v16 = 1;
    }
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      117508357,
      4,
      16,
      v16,
      v14,
      22,
      &WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
  }
  result = ClearNonReplicatedAttributesAndSecrets();
  updated = result;
  if ( (int)result >= 0 )
  {
    if ( RecoveryMode == 1
      || (result = CheckTombstone(), updated = result, (int)result >= 0)
      && (RecoveryMode == 1 || (result = CheckReplicationEpoch(a1), updated = result, (int)result >= 0)) )
    {
      if ( !DcInstallFlavor
        || gfIsClone
        || (result = HandleKeys(*((struct _IFM_SYSTEM_INFO **)a1 + 8), v17, v18), updated = result, (int)result >= 0) )
      {
        LODWORD(v250[0]) = 58;
        *(_OWORD *)((char *)v250 + 8) = *(_OWORD *)((char *)qword_18052B2A8 + 8);
        goto LABEL_31;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180194070  mov     r11, rsp
0x180194073  mov     [r11+18h], rbx
0x180194077  mov     [r11+20h], rsi
0x18019407b  push    rdi
0x18019407c  push    r12
0x18019407e  push    r13
0x180194080  push    r14
0x180194082  push    r15
0x180194084  sub     rsp, 0FF0h
0x18019408b  movaps  xmmword ptr [r11-38h], xmm6
0x180194090  mov     rax, cs:__security_cookie
0x180194097  xor     rax, rsp
0x18019409a  mov     [rsp+1018h+var_48], rax
0x1801940a2  mov     [rsp+1018h+lpTlsValue], rdx
0x1801940aa  mov     rdi, rcx
0x1801940ad  mov     [rsp+1018h+var_F90], rcx
0x1801940b5  xorps   xmm0, xmm0
0x1801940b8  xor     eax, eax
0x1801940ba  movups  [rsp+1018h+var_D08], xmm0
0x1801940c2  movups  [rsp+1018h+var_CF8], xmm0
0x1801940ca  movups  xmmword ptr [rsp+1018h+var_CE8], xmm0
0x1801940d2  movups  xmmword ptr [rsp+1018h+var_CE8+0Ch], xmm0
0x1801940da  xorps   xmm1, xmm1
0x1801940dd  movups  [rsp+1018h+var_CB8], xmm1
0x1801940e5  movups  [rsp+1018h+var_CA8], xmm1
0x1801940ed  movups  xmmword ptr [rsp+1018h+var_C98], xmm1
0x1801940f5  movups  xmmword ptr [rsp+1018h+var_C98+0Ch], xmm1
0x1801940fd  xor     r15d, r15d
0x180194100  mov     [rsp+1018h+var_FC4], r15d
0x180194105  mov     [r11-0F80h], r15
0x18019410c  mov     [r11-0F38h], r15
0x180194113  mov     [r11-0F78h], r15d
0x18019411a  mov     [r11-0F48h], r15
0x180194121  mov     [r11-0F70h], r15
0x180194128  mov     [r11-0F68h], r15
0x18019412f  xorps   xmm6, xmm6
0x180194132  movups  xmmword ptr [rsp+1018h+var_F60.Data1], xmm6
0x18019413a  mov     cs:gfDoSamChecks, r15d
0x180194141  mov     cs:gUpdatesEnabled, 1
0x18019414b  xor     edx, edx; Val
0x18019414d  mov     r8d, 98h; Size
0x180194153  lea     rcx, gNames; void *
0x18019415a  call    memset_0
0x18019415f  mov     rax, cs:gpfnInstallCancelOk
0x180194166  test    rax, rax
0x180194169  jz      short loc_1801941C2
0x18019416b  mov     cl, 1
0x18019416d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180194172  test    eax, eax
0x180194174  jz      short loc_1801941C2
0x180194176  xor     r9d, r9d
0x180194179  xor     r8d, r8d
0x18019417c  mov     edx, 40000516h
0x180194181  mov     ecx, 4C7h
0x180194186  call    SetInstallErrorMessage
0x18019418b  mov     eax, 0C0000120h
0x180194190  mov     rcx, [rsp+1018h+var_48]
0x180194198  xor     rcx, rsp; StackCookie
0x18019419b  call    __security_check_cookie
0x1801941a0  lea     r11, [rsp+1018h+var_28]
0x1801941a8  mov     rbx, [r11+40h]
0x1801941ac  mov     rsi, [r11+48h]
0x1801941b0  movaps  xmm6, xmmword ptr [r11-10h]
0x1801941b5  mov     rsp, r11
0x1801941b8  pop     r15
0x1801941ba  pop     r14
0x1801941bc  pop     r13
0x1801941be  pop     r12
0x1801941c0  pop     rdi
0x1801941c1  retn
0x1801941c2  mov     r14d, r15d
0x1801941c5  cmp     cs:DataSource, 1
0x1801941cc  jnz     loc_18019434D
0x1801941d2  call    THStateCheckForTraceOverride
0x1801941d7  mov     r13d, 10h
0x1801941dd  lea     esi, [r13-0Ch]
0x1801941e1  test    eax, eax
0x1801941e3  jnz     short loc_18019422E
0x1801941e5  mov     r8d, r13d
0x1801941e8  mov     edx, esi
0x1801941ea  xor     ecx, ecx
0x1801941ec  call    CheckWPPLevelFlagsEnabledForProvider
0x1801941f1  test    eax, eax
0x1801941f3  jnz     short loc_18019422E
0x1801941f5  mov     eax, cs:gfTraceToSecondProvider
0x1801941fb  test    eax, eax
0x1801941fd  jz      loc_1801942C1
0x180194203  call    THStateCheckForTraceOverride
0x180194208  test    eax, eax
0x18019420a  jnz     short loc_18019422E
0x18019420c  call    ThStateCheckIfTraceToSecondProvier
0x180194211  test    eax, eax
0x180194213  jz      loc_1801942C1
0x180194219  mov     r8d, r13d
0x18019421c  mov     edx, esi
0x18019421e  lea     ecx, [rsi-3]
0x180194221  call    CheckWPPLevelFlagsEnabledForProvider
0x180194226  test    eax, eax
0x180194228  jz      loc_1801942C1
0x18019422e  mov     eax, cs:gfTraceToSecondProvider
0x180194234  test    eax, eax
0x180194236  jz      short loc_180194264
0x180194238  call    THStateCheckForTraceOverride
0x18019423d  test    eax, eax
0x18019423f  jnz     short loc_18019425D
0x180194241  call    ThStateCheckIfTraceToSecondProvier
0x180194246  test    eax, eax
0x180194248  jz      short loc_180194264
0x18019424a  mov     r8d, r13d
0x18019424d  mov     edx, esi
0x18019424f  mov     ecx, 1
0x180194254  call    CheckWPPLevelFlagsEnabledForProvider
0x180194259  test    eax, eax
0x18019425b  jz      short loc_180194264
0x18019425d  mov     ebx, 1
0x180194262  jmp     short loc_180194267
0x180194264  mov     ebx, r15d
0x180194267  call    THStateCheckForTraceOverride
0x18019426c  test    eax, eax
0x18019426e  jnz     short loc_180194283
0x180194270  mov     r8d, r13d
0x180194273  mov     edx, esi
0x180194275  xor     ecx, ecx
0x180194277  call    CheckWPPLevelFlagsEnabledForProvider
0x18019427c  test    eax, eax
0x18019427e  mov     eax, r15d
0x180194281  jz      short loc_180194288
0x180194283  mov     eax, 1
0x180194288  lea     r15, WPP_917fdaafcb49317f4b06728749c09966_Traceguids
0x18019428f  mov     [rsp+1018h+var_FE0], r15; LPCGUID
0x180194294  mov     [rsp+1018h+var_FE8], 16h; __int16
0x18019429b  mov     dword ptr [rsp+1018h+var_FF0], ebx; int
0x18019429f  mov     dword ptr [rsp+1018h+var_FF8], eax; int
0x1801942a3  mov     r9d, r13d; int
0x1801942a6  mov     r8d, esi; int
0x1801942a9  mov     edx, 7010905h; int
0x1801942ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1801942b5  mov     rcx, [rcx+10h]; int
0x1801942b9  call    WPP_SF_
0x1801942be  xor     r15d, r15d
0x1801942c1  call    ?ClearNonReplicatedAttributesAndSecrets@@YAJXZ; ClearNonReplicatedAttributesAndSecrets(void)
0x1801942c6  mov     r14d, eax
0x1801942c9  test    eax, eax
0x1801942cb  js      loc_180194190
0x1801942d1  cmp     cs:RecoveryMode, 1
0x1801942d8  jz      short loc_180194306
0x1801942da  call    ?CheckTombstone@@YAJXZ; CheckTombstone(void)
0x1801942df  mov     r14d, eax
0x1801942e2  test    eax, eax
0x1801942e4  js      loc_180194190
0x1801942ea  cmp     cs:RecoveryMode, 1
0x1801942f1  jz      short loc_180194306
0x1801942f3  mov     rcx, rdi; struct _DS_INSTALL_PARAM *
0x1801942f6  call    ?CheckReplicationEpoch@@YAJPEAU_DS_INSTALL_PARAM@@@Z; CheckReplicationEpoch(_DS_INSTALL_PARAM *)
0x1801942fb  mov     r14d, eax
0x1801942fe  test    eax, eax
0x180194300  js      loc_180194190
0x180194306  cmp     cs:DcInstallFlavor, r15d
0x18019430d  jz      short loc_18019432C
0x18019430f  cmp     cs:gfIsClone, r15d
0x180194316  jnz     short loc_18019432C
0x180194318  mov     rcx, [rdi+40h]; struct _IFM_SYSTEM_INFO *
0x18019431c  call    ?HandleKeys@@YAJPEAU_IFM_SYSTEM_INFO@@PEAXK@Z; HandleKeys(_IFM_SYSTEM_INFO *,void *,ulong)
0x180194321  mov     r14d, eax
0x180194324  test    eax, eax
0x180194326  js      loc_180194190
0x18019432c  mov     dword ptr [rsp+1018h+var_CB8], 3Ah ; ':'
0x180194337  mov     rax, cs:qword_18052B2A8
0x18019433e  movups  xmm0, xmmword ptr [rax+8]
0x180194342  movdqu  [rsp+1018h+var_CB8+8], xmm0
0x18019434b  jmp     short loc_180194353
0x18019434d  mov     r13d, 10h
0x180194353  cmp     cs:gfADAM, r15d
0x18019435a  jz      short loc_1801943BC
0x18019435c  mov     cs:Str, r15
0x180194363  mov     [rsp+1018h+var_FB8], r15
0x180194368  mov     rsi, r15
0x18019436b  mov     [rsp+1018h+var_FB0], r15
0x180194370  mov     [rsp+1018h+var_FA8], r15d
0x180194375  mov     eax, [rdi+7Ch]
0x180194378  mov     cs:dword_18052B32C, eax
0x18019437e  mov     rcx, rdi; struct _DS_INSTALL_PARAM *
0x180194381  call    ?InitializeNTDSSetup@@YAKPEAU_DS_INSTALL_PARAM@@@Z; InitializeNTDSSetup(_DS_INSTALL_PARAM *)
0x180194386  mov     [rsp+1018h+var_FC0], eax
0x18019438a  test    eax, eax
0x18019438c  jz      loc_18019442D
0x180194392  xor     r9d, r9d
0x180194395  xor     r8d, r8d
0x180194398  mov     edx, 40000500h
0x18019439d  mov     ecx, eax
0x18019439f  call    SetInstallErrorMessage
0x1801943a4  mov     [rsp+1018h+var_FC4], 1
0x1801943ac  mov     r14d, 0C0000001h
0x1801943b2  mov     [rsp+1018h+var_FC8], r14d
0x1801943b7  jmp     loc_180196A2E
0x1801943bc  mov     edx, 701093Dh
0x1801943c1  mov     ecx, 208h
0x1801943c6  call    DSAllocAux
0x1801943cb  mov     cs:Str, rax
0x1801943d2  xor     r9d, r9d
0x1801943d5  test    rax, rax
0x1801943d8  jnz     short loc_1801943F4
0x1801943da  xor     r8d, r8d
0x1801943dd  mov     edx, 40000500h
0x1801943e2  lea     ecx, [rax+0Eh]
0x1801943e5  call    SetInstallErrorMessage
0x1801943ea  mov     eax, 0C0000017h
0x1801943ef  jmp     loc_180194190
0x1801943f4  mov     r8d, 104h
0x1801943fa  mov     rdx, rax; lpData
0x1801943fd  lea     rcx, aRootdomaindnsn_0; "RootDomainDnsName"
0x180194404  call    GetConfigParamLocalWEx
0x180194409  test    eax, eax
0x18019440b  jz      loc_180194363
0x180194411  xor     r9d, r9d
0x180194414  xor     r8d, r8d
0x180194417  mov     edx, 4000050Ah
0x18019441c  mov     ecx, eax
0x18019441e  call    SetInstallErrorMessage
0x180194423  mov     eax, 0C000014Dh
0x180194428  jmp     loc_180194190
0x18019442d  mov     rcx, cs:qword_180526C70
0x180194434  test    rcx, rcx
0x180194437  jz      short loc_18019443F
0x180194439  cmp     r15w, [rcx]
0x18019443d  jnz     short loc_180194458
0x18019443f  cmp     cs:gfADAM, r15d
0x180194446  jz      short loc_180194460
0x180194448  mov     rcx, cs:qword_180526C80
0x18019444f  call    IsValidDSInstance
0x180194454  test    eax, eax
0x180194456  jz      short loc_180194460
0x180194458  mov     [rsp+1018h+var_FA8], 1
0x180194460  mov     rcx, cs:qword_180526C80
0x180194467  call    IsValidDSInstance
0x18019446c  test    eax, eax
0x18019446e  jnz     loc_180194760
0x180194474  cmp     cs:RecoveryMode, 1
0x18019447b  jz      loc_180194760
0x180194481  xorps   xmm0, xmm0
0x180194484  movups  xmmword ptr [rsp+1018h+var_CC8.Data1], xmm0
0x18019448c  mov     cs:?gInstallHasDoneSchemaMove@@3HA, r15d; int gInstallHasDoneSchemaMove
0x180194493  cmp     cs:gfADAM, r15d
0x18019449a  jnz     short loc_1801944EC
0x18019449c  xor     r8d, r8d; struct _CROSS_REF *
0x18019449f  lea     rdx, [rsp+1018h+var_CC8]; struct _GUID *
0x1801944a7  mov     rcx, cs:P; unsigned __int16 *
0x1801944ae  call    ?CreateRootDomainObject@@YAJPEAGPEAU_GUID@@PEAU_CROSS_REF@@@Z; CreateRootDomainObject(ushort *,_GUID *,_CROSS_REF *)
0x1801944b3  mov     r14d, eax
0x1801944b6  mov     [rsp+1018h+var_FC8], eax
0x1801944ba  test    eax, eax
0x1801944bc  jns     short loc_1801944EC
0x1801944be  mov     rbx, cs:P
0x1801944c5  mov     ecx, eax; Status
0x1801944c7  call    cs:__imp_RtlNtStatusToDosError
0x1801944cd  mov     edx, 400004FCh
0x1801944d2  xor     r9d, r9d
0x1801944d5  mov     r8, rbx
0x1801944d8  mov     ecx, eax
0x1801944da  call    SetInstallErrorMessage
0x1801944df  mov     [rsp+1018h+var_FC4], 1
0x1801944e7  jmp     loc_180196A2E
0x1801944ec  mov     rcx, cs:qword_180526C78; unsigned __int16 *
0x1801944f3  call    ?CreateConfigNCObject@@YAJPEAG@Z; CreateConfigNCObject(ushort *)
0x1801944f8  mov     r14d, eax
0x1801944fb  mov     [rsp+1018h+var_FC8], eax
0x1801944ff  test    eax, eax
0x180194501  jns     short loc_18019450C
0x180194503  mov     rbx, cs:qword_180526C78
0x18019450a  jmp     short loc_1801944C5
0x18019450c  mov     rcx, cs:qword_180526C98; unsigned __int16 *
0x180194513  call    ?CreateSchemaNCObject@@YAJPEAG@Z; CreateSchemaNCObject(ushort *)
0x180194518  mov     r14d, eax
0x18019451b  mov     [rsp+1018h+var_FC8], eax
0x18019451f  test    eax, eax
0x180194521  jns     short loc_18019452C
0x180194523  mov     rbx, cs:qword_180526C98
0x18019452a  jmp     short loc_1801944C5
0x18019452c  xor     edx, edx; unsigned int
0x18019452e  mov     rcx, cs:qword_180526C98; unsigned __int16 *
0x180194535  call    ?UpdateCreateNCInstallMessage@@YAXPEAGK@Z; UpdateCreateNCInstallMessage(ushort *,ulong)
0x18019453a  mov     rcx, cs:qword_180526C98
0x180194541  call    DBInitialSetup
0x180194546  test    eax, eax
0x180194548  jz      short loc_18019456F
0x18019454a  mov     r14d, 0C0000001h
0x180194550  mov     [rsp+1018h+var_FC8], r14d
0x180194555  mov     rbx, cs:qword_180526C98
0x18019455c  mov     ecx, r14d; Status
0x18019455f  call    cs:__imp_RtlNtStatusToDosError
0x180194565  mov     edx, 0C0000577h
0x18019456a  jmp     loc_1801944D2
0x18019456f  mov     cs:?gInstallHasDoneSchemaMove@@3HA, 1; int gInstallHasDoneSchemaMove
0x180194579  mov     edx, 1; unsigned int
0x18019457e  mov     rcx, cs:qword_180526C78; unsigned __int16 *
0x180194585  call    ?UpdateCreateNCInstallMessage@@YAXPEAGK@Z; UpdateCreateNCInstallMessage(ushort *,ulong)
0x18019458a  mov     rcx, cs:qword_180526C78; unsigned __int16 *
0x180194591  call    ?CreateDefaultConfigNCDIT@@YAJPEAG@Z; CreateDefaultConfigNCDIT(ushort *)
0x180194596  mov     r14d, eax
0x180194599  mov     [rsp+1018h+var_FC8], eax
  ... truncated ...
```
