# CreateProcessInternalW

- ea: `0x18008e220`
- end: `0x180096e6f`
- name: `CreateProcessInternalW`
- size: `35919`
- prototype: ``
- caller_count: `5`
- callee_count: `63`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18008c8cc`
- `0x18008dba0`
- `0x18008e120`
- `0x18008e1a0`
- `0x18011b248`

## callees

- `0x18000ec14`
- `0x18000f348`
- `0x18000f590`
- `0x1800123e0`
- `0x180019350`
- `0x18004b9d0`
- `0x1800715e0`
- `0x180083140`
- `0x18008e220`
- `0x1800cb390`
- `0x1800cd5ec`
- `0x1800cedf0`
- `0x1800d3300`
- `0x1800e1d50`
- `0x1800e7e40`
- `0x1800e9ac0`
- `0x1800ec3d0`
- `0x1800ed4cc`
- `0x1800ef8f0`
- `0x1800f4da0`
- `0x1800fe470`
- `0x1800fe800`
- `0x180107dec`
- `0x18010a008`
- `0x18010d064`
- `0x180115dfc`
- `0x180117f3c`
- `0x180119c34`
- `0x18011b7f8`
- `0x18012e338`
- `0x18012e970`
- `0x18012f680`
- `0x1801304ac`
- `0x180130ae8`
- `0x180131098`
- `0x180136930`
- `0x1801369c9`
- `0x180139590`
- `0x180139b24`
- `0x180139b78`
- `0x180139bcc`
- `0x180139c20`
- `0x18013a9c0`
- `0x180188b74`
- `0x180188c40`
- `0x18018b84c`
- `0x18018b904`
- `0x18018ba64`
- `0x18018bb84`
- `0x18018bd64`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18008f27d`
- `ntdll!RtlFreeUnicodeString` at `0x180095e2e`
- `ntdll!RtlFreeUnicodeString` at `0x180096744`
- `ntdll!RtlFreeUnicodeString` at `0x180196037`
- `ntdll!RtlFreeUnicodeString` at `0x180196905`
- `ntdll!RtlFreeUnicodeString` at `0x18008f27d`
- `ntdll!RtlFreeUnicodeString` at `0x180095e2e`
- `ntdll!RtlFreeUnicodeString` at `0x180096744`
- `ntdll!RtlFreeUnicodeString` at `0x180196037`
- `ntdll!RtlFreeUnicodeString` at `0x180196905`
- `ntdll!RtlInitUnicodeString` at `0x18008fd01`
- `ntdll!RtlInitUnicodeString` at `0x180092339`
- `ntdll!RtlInitUnicodeString` at `0x18009237b`
- `ntdll!RtlInitUnicodeString` at `0x180092b1d`
- `ntdll!RtlInitUnicodeString` at `0x180092d00`
- `ntdll!RtlInitUnicodeString` at `0x180092d46`
- `ntdll!RtlInitUnicodeString` at `0x180094068`
- `ntdll!RtlInitUnicodeString` at `0x18009409b`
- `ntdll!RtlInitUnicodeString` at `0x1800944c1`
- `ntdll!RtlInitUnicodeString` at `0x18008fd01`
- `ntdll!RtlInitUnicodeString` at `0x180092339`
- `ntdll!RtlInitUnicodeString` at `0x18009237b`
- `ntdll!RtlInitUnicodeString` at `0x180092b1d`
- `ntdll!RtlInitUnicodeString` at `0x180092d00`
- `ntdll!RtlInitUnicodeString` at `0x180092d46`
- `ntdll!RtlInitUnicodeString` at `0x180094068`
- `ntdll!RtlInitUnicodeString` at `0x18009409b`
- `ntdll!RtlInitUnicodeString` at `0x1800944c1`
- `ntdll!wcslen` at `0x18008f831`
- `ntdll!wcslen` at `0x1800929d8`
- `ntdll!wcslen` at `0x1800929ef`
- `ntdll!wcslen` at `0x180092a70`
- `ntdll!wcslen` at `0x180092a86`
- `ntdll!wcslen` at `0x180092a9c`
- `ntdll!wcslen` at `0x180092b38`
- `ntdll!wcslen` at `0x18008f831`
- `ntdll!wcslen` at `0x1800929d8`
- `ntdll!wcslen` at `0x1800929ef`
- `ntdll!wcslen` at `0x180092a70`
- `ntdll!wcslen` at `0x180092a86`
- `ntdll!wcslen` at `0x180092a9c`
- `ntdll!wcslen` at `0x180092b38`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18008f8fa`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18008f8fa`
- `ntdll!_wcsnicmp` at `0x1800924ce`
- `ntdll!_wcsnicmp` at `0x1800924ef`
- `ntdll!_wcsnicmp` at `0x1800924ce`
- `ntdll!_wcsnicmp` at `0x1800924ef`
- `ntdll!RtlSetLastWin32Error` at `0x18008e79f`
- `ntdll!RtlSetLastWin32Error` at `0x18008f056`
- `ntdll!RtlSetLastWin32Error` at `0x18008e79f`
- `ntdll!RtlSetLastWin32Error` at `0x18008f056`
- `ntdll!NtWaitForSingleObject` at `0x18008f3e0`
- `ntdll!NtWaitForSingleObject` at `0x1800966d6`
- `ntdll!NtWaitForSingleObject` at `0x18019689a`
- `ntdll!NtWaitForSingleObject` at `0x18008f3e0`
- `ntdll!NtWaitForSingleObject` at `0x1800966d6`
- `ntdll!NtWaitForSingleObject` at `0x18019689a`
- `ntdll!RtlIsDosDeviceName_U` at `0x180092d89`
- `ntdll!RtlIsDosDeviceName_U` at `0x180092d89`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18008f949`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18008f949`
- `ntdll!NtTerminateProcess` at `0x18008f3c7`
- `ntdll!NtTerminateProcess` at `0x1800966bd`
- `ntdll!NtTerminateProcess` at `0x180196882`
- `ntdll!NtTerminateProcess` at `0x18008f3c7`
- `ntdll!NtTerminateProcess` at `0x1800966bd`
- `ntdll!NtTerminateProcess` at `0x180196882`
- `ntdll!NtQueryInformationToken` at `0x180093452`
- `ntdll!NtQueryInformationToken` at `0x180093452`
- `ntdll!CsrClientCallServer` at `0x180093554`
- `ntdll!CsrClientCallServer` at `0x180093554`
- `ntdll!CsrFreeCaptureBuffer` at `0x18008f4ee`
- `ntdll!CsrFreeCaptureBuffer` at `0x18009680a`
- `ntdll!CsrFreeCaptureBuffer` at `0x1801969c2`
- `ntdll!CsrFreeCaptureBuffer` at `0x18008f4ee`
- `ntdll!CsrFreeCaptureBuffer` at `0x18009680a`
- `ntdll!CsrFreeCaptureBuffer` at `0x1801969c2`
- `ntdll!RtlInitUnicodeStringEx` at `0x18008f924`
- `ntdll!RtlInitUnicodeStringEx` at `0x18008f924`
- `ntdll!NtClose` at `0x18008f2d4`
- `ntdll!NtClose` at `0x18008f2f5`
- `ntdll!NtClose` at `0x18008f378`
- `ntdll!NtClose` at `0x18008f3f4`
- `ntdll!NtClose` at `0x18008f415`
- `ntdll!NtClose` at `0x180091f84`
- `ntdll!NtClose` at `0x1800920e4`
- `ntdll!NtClose` at `0x180092199`
- `ntdll!NtClose` at `0x180092215`
- `ntdll!NtClose` at `0x1800923a2`
- `ntdll!NtClose` at `0x18009448c`
- `ntdll!NtClose` at `0x180095cd4`
- `ntdll!NtClose` at `0x18009643e`
- `ntdll!NtClose` at `0x18009645a`
- `ntdll!NtClose` at `0x180096658`
- `ntdll!NtClose` at `0x180096674`
- `ntdll!NtClose` at `0x1800966ea`
- `ntdll!NtClose` at `0x180096703`
- `ntdll!NtClose` at `0x1800967d8`
- `ntdll!NtClose` at `0x180195f23`
- `ntdll!NtClose` at `0x180195f36`
- `ntdll!NtClose` at `0x18019662b`
- `ntdll!NtClose` at `0x180196644`
- `ntdll!NtClose` at `0x180196825`
- `ntdll!NtClose` at `0x18019683e`
- `ntdll!NtClose` at `0x1801968ad`
- `ntdll!NtClose` at `0x1801968c6`
- `ntdll!NtClose` at `0x180196990`
- `ntdll!NtClose` at `0x18008f2d4`
- `ntdll!NtClose` at `0x18008f2f5`
- `ntdll!NtClose` at `0x18008f378`
- `ntdll!NtClose` at `0x18008f3f4`
- `ntdll!NtClose` at `0x18008f415`
- `ntdll!NtClose` at `0x180091f84`
- `ntdll!NtClose` at `0x1800920e4`
- `ntdll!NtClose` at `0x180092199`
- `ntdll!NtClose` at `0x180092215`
- `ntdll!NtClose` at `0x1800923a2`
- `ntdll!NtClose` at `0x18009448c`
- `ntdll!NtClose` at `0x180095cd4`
- `ntdll!NtClose` at `0x18009643e`
- `ntdll!NtClose` at `0x18009645a`
- `ntdll!NtClose` at `0x180096658`
- `ntdll!NtClose` at `0x180096674`
- `ntdll!NtClose` at `0x1800966ea`
- `ntdll!NtClose` at `0x180096703`
- `ntdll!NtClose` at `0x1800967d8`
- `ntdll!NtClose` at `0x180195f23`
- `ntdll!NtClose` at `0x180195f36`
- `ntdll!NtClose` at `0x18019662b`
- `ntdll!NtClose` at `0x180196644`
- `ntdll!NtClose` at `0x180196825`
- `ntdll!NtClose` at `0x18019683e`
- `ntdll!NtClose` at `0x1801968ad`
- `ntdll!NtClose` at `0x1801968c6`
- `ntdll!NtClose` at `0x180196990`
- `ntdll!NtQueryInformationProcess` at `0x1800930a8`
- `ntdll!NtQueryInformationProcess` at `0x1800930a8`
- `ntdll!RtlFreeHeap` at `0x18008f238`
- `ntdll!RtlFreeHeap` at `0x18008f261`
- `ntdll!RtlFreeHeap` at `0x18008f2b0`
- `ntdll!RtlFreeHeap` at `0x18008fd64`
- `ntdll!RtlFreeHeap` at `0x18009227a`
- `ntdll!RtlFreeHeap` at `0x180095dd8`
- `ntdll!RtlFreeHeap` at `0x180095e1a`
- `ntdll!RtlFreeHeap` at `0x1800965d2`
- `ntdll!RtlFreeHeap` at `0x1800965f3`
- `ntdll!RtlFreeHeap` at `0x18009661b`
- `ntdll!RtlFreeHeap` at `0x18009663c`
- `ntdll!RtlFreeHeap` at `0x180096830`
- `ntdll!RtlFreeHeap` at `0x18009684e`
- `ntdll!RtlFreeHeap` at `0x180195fd1`
- `ntdll!RtlFreeHeap` at `0x180196019`
- `ntdll!RtlFreeHeap` at `0x1801967a8`
- `ntdll!RtlFreeHeap` at `0x1801967c6`
- `ntdll!RtlFreeHeap` at `0x1801967ee`
- `ntdll!RtlFreeHeap` at `0x18019680c`
- `ntdll!RtlFreeHeap` at `0x1801969ea`
- `ntdll!RtlFreeHeap` at `0x180196a08`
- `ntdll!RtlFreeHeap` at `0x18008f238`
- `ntdll!RtlFreeHeap` at `0x18008f261`
- `ntdll!RtlFreeHeap` at `0x18008f2b0`
- `ntdll!RtlFreeHeap` at `0x18008fd64`
- `ntdll!RtlFreeHeap` at `0x18009227a`
- `ntdll!RtlFreeHeap` at `0x180095dd8`
- `ntdll!RtlFreeHeap` at `0x180095e1a`
- `ntdll!RtlFreeHeap` at `0x1800965d2`
- `ntdll!RtlFreeHeap` at `0x1800965f3`
- `ntdll!RtlFreeHeap` at `0x18009661b`
- `ntdll!RtlFreeHeap` at `0x18009663c`
- `ntdll!RtlFreeHeap` at `0x180096830`
- `ntdll!RtlFreeHeap` at `0x18009684e`
- `ntdll!RtlFreeHeap` at `0x180195fd1`
- `ntdll!RtlFreeHeap` at `0x180196019`
- `ntdll!RtlFreeHeap` at `0x1801967a8`
- `ntdll!RtlFreeHeap` at `0x1801967c6`
- `ntdll!RtlFreeHeap` at `0x1801967ee`
- `ntdll!RtlFreeHeap` at `0x18019680c`
- `ntdll!RtlFreeHeap` at `0x1801969ea`
- `ntdll!RtlFreeHeap` at `0x180196a08`
- `ntdll!RtlImageNtHeader` at `0x1800933fc`
- `ntdll!RtlImageNtHeader` at `0x1800933fc`
- `ntdll!RtlDestroyProcessParameters` at `0x1800920fa`
- `ntdll!RtlDestroyProcessParameters` at `0x1800920fa`
- `ntdll!NtOpenProcessToken` at `0x1800943bd`
- `ntdll!NtOpenProcessToken` at `0x1800943bd`
- `ntdll!NtOpenThreadToken` at `0x180091f47`
- `ntdll!NtOpenThreadToken` at `0x180091fe1`
- `ntdll!NtOpenThreadToken` at `0x180091f47`
- `ntdll!NtOpenThreadToken` at `0x180091fe1`
- `ntdll!RtlReleasePath` at `0x18008f688`
- `ntdll!RtlReleasePath` at `0x1800967f1`
- `ntdll!RtlReleasePath` at `0x1801969a9`
- `ntdll!RtlReleasePath` at `0x18008f688`
- `ntdll!RtlReleasePath` at `0x1800967f1`
- `ntdll!RtlReleasePath` at `0x1801969a9`
- `ntdll!NtWriteVirtualMemory` at `0x1800957c9`
- `ntdll!NtWriteVirtualMemory` at `0x180095806`
- `ntdll!NtWriteVirtualMemory` at `0x180095863`
- `ntdll!NtWriteVirtualMemory` at `0x1800957c9`

## string_xrefs

- `0x18008e3f9`: `ntdll.dll`
- `0x180092599`: `\system32\cmd.exe`
- `0x180092556`: `ComSpec`

## pseudocode

```c
__int64 __fastcall CreateProcessInternalW(
        void *a1,
        const WCHAR *a2,
        const wchar_t *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        WCHAR *a8,
        WCHAR *a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v14; // r15
  unsigned int v15; // r14d
  __int64 v16; // rcx
  __int64 v17; // rbx
  PVOID ProcessHeap; // r12
  __int64 v19; // rdx
  HANDLE ThreadDebugObject; // rcx
  char v21; // al
  NTSTATUS v22; // eax
  wchar_t *v23; // r14
  __int64 v24; // rax
  __int64 v25; // r15
  int v26; // eax
  __m128i v27; // xmm2
  __int64 v28; // rcx
  unsigned int ProcessInternalW; // ebx
  _DWORD *v30; // r10
  int ExePath; // eax
  int v32; // edx
  __int64 v33; // rcx
  WCHAR *v34; // rbx
  PVOID Heap; // r15
  NTSTATUS FullPathName_UEx; // eax
  ULONG v37; // ecx
  unsigned int v38; // eax
  const WCHAR *v39; // r15
  const wchar_t *v40; // rcx
  WCHAR *v41; // rdx
  HANDLE v42; // r13
  void *v43; // rbx
  const wchar_t *v44; // r13
  __int64 v45; // rdx
  __int64 v46; // rax
  HANDLE v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // rcx
  char v50; // r15
  char v51; // r13
  ULONG LastErrorValue; // r14d
  const WCHAR *v53; // rax
  STRSAFE_LPCWSTR v54; // rdx
  STRSAFE_LPCWSTR v55; // rbx
  char v56; // r12
  ULONG v57; // eax
  __int64 v58; // rcx
  DWORD FileAttributesW; // eax
  const wchar_t *v60; // rcx
  SIZE_T v61; // rbx
  wchar_t *v62; // rax
  wchar_t *v63; // r13
  int v64; // ebx
  RTL_PATH_TYPE v65; // eax
  struct _PEB *v66; // r14
  __int64 v67; // rdx
  _WORD *v68; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  int v70; // ecx
  __int64 v71; // rax
  WCHAR *v72; // r14
  __int64 v73; // rdx
  HANDLE v74; // rbx
  __int64 v75; // rdx
  __int64 v76; // rcx
  WCHAR *v77; // rax
  int v78; // eax
  DWORD v79; // eax
  unsigned int v80; // eax
  int v81; // ecx
  _WORD *v82; // rcx
  int v83; // r12d
  __int64 v84; // rdx
  __int64 v85; // rcx
  char v86; // r11
  char v87; // r9
  char v88; // r14
  __int64 v89; // rbx
  int v90; // eax
  bool v91; // al
  char v92; // r10
  int v93; // eax
  bool v94; // zf
  char v95; // al
  char v96; // r10
  int v97; // eax
  char v98; // al
  char v99; // r10
  int v100; // eax
  char v101; // al
  char v102; // r10
  int v103; // eax
  char v104; // al
  char v105; // r10
  int v106; // eax
  char v107; // al
  char v108; // r10
  int v109; // eax
  char v110; // al
  char v111; // r10
  int v112; // eax
  char v113; // al
  int v114; // eax
  bool v115; // al
  char v116; // r10
  int v117; // eax
  char v118; // al
  char v119; // r10
  int v120; // eax
  char v121; // al
  char v122; // r10
  int v123; // eax
  char v124; // al
  char v125; // r10
  int v126; // eax
  char v127; // al
  char v128; // r10
  int v129; // eax
  char v130; // al
  char v131; // r10
  int v132; // eax
  char v133; // al
  char v134; // r10
  int v135; // eax
  char v136; // al
  int v137; // eax
  bool v138; // al
  char v139; // cl
  int v140; // eax
  char v141; // al
  char v142; // r9
  char v143; // r14
  char v144; // r8
  char v145; // r10
  __int64 v146; // rax
  unsigned int v147; // eax
  int v148; // eax
  __int16 v149; // ax
  char v150; // cl
  char v151; // dl
  char v152; // dl
  char v153; // dl
  char v154; // dl
  char v155; // dl
  char v156; // dl
  char v157; // dl
  char v158; // cl
  __int64 v159; // r8
  __int64 v160; // rdx
  struct _RTL_USER_PROCESS_PARAMETERS *v161; // r14
  __int64 Length; // rbx
  PVOID v163; // rax
  int v164; // eax
  HANDLE v165; // rcx
  int v166; // eax
  BOOL v167; // eax
  __int64 v168; // rdx
  __int64 v169; // rcx
  __int64 v170; // rcx
  HANDLE v171; // rbx
  _WORD *v172; // r14
  int v173; // eax
  void *v174; // rax
  __int64 v175; // rcx
  WCHAR *v176; // r14
  WCHAR *v177; // rax
  WCHAR *v178; // rbx
  DWORD EnvironmentVariableW; // eax
  char v180; // r14
  char v181; // al
  HANDLE v182; // r14
  __int64 v183; // rdx
  __int64 v184; // rcx
  int v185; // eax
  const wchar_t *v186; // rcx
  int v187; // ebx
  SIZE_T v188; // rbx
  wchar_t *v189; // rax
  wchar_t *v190; // r15
  const wchar_t *v191; // r8
  int v192; // ebx
  int v193; // ebx
  wchar_t *v194; // rax
  SIZE_T v195; // rbx
  wchar_t *v196; // rax
  int AppExecutionAliasInfoForExecutable; // r14d
  int v198; // eax
  void *v199; // rax
  HANDLE v200; // rbx
  int v201; // r12d
  int v202; // eax
  __int64 v203; // rdx
  __int64 v204; // rcx
  int v205; // eax
  __int64 v206; // rdx
  __int64 v207; // rcx
  __int64 v208; // r13
  char v209; // al
  HANDLE v210; // r14
  __int64 v211; // rdx
  __int64 v212; // rcx
  char v213; // al
  __int64 v214; // rdx
  HMODULE ModuleHandleA; // rax
  PIMAGE_NT_HEADERS v216; // rax
  HANDLE v217; // rbx
  unsigned int v218; // eax
  __int64 ConsoleHost; // rcx
  __int64 v220; // rdx
  __int64 v221; // rcx
  __int64 v222; // rdx
  __int64 v223; // rcx
  int v224; // ebx
  int v225; // eax
  __int64 v226; // rcx
  HANDLE v227; // rax
  int EAAumidIfPresent; // ebx
  const WCHAR *v229; // rdx
  __int16 *v230; // rbx
  __int64 v231; // rcx
  LONG PackageActivationTokenForSxS3; // eax
  BOOL v233; // ebx
  LONG PackageFullNameFromToken; // ebx
  WCHAR *v235; // rdx
  char *v236; // rax
  __int16 *v237; // rdx
  WCHAR *v238; // rdx
  char v239; // al
  NTSTATUS v240; // eax
  __int64 v241; // rdx
  unsigned __int64 v242; // rcx
  unsigned __int64 v243; // r14
  HANDLE v244; // r15
  unsigned __int64 i; // rbx
  LONG v246; // ebx
  int v247; // edx
  __int64 v248; // rax
  char *v249; // rdx
  unsigned __int8 v250; // r13
  char v251; // r11
  char v252; // r10
  __int64 v253; // r14
  int v254; // eax
  bool v255; // al
  char v256; // cl
  int v257; // eax
  char v258; // al
  char v259; // cl
  int v260; // eax
  char v261; // al
  char v262; // cl
  int v263; // eax
  char v264; // al
  char v265; // cl
  int v266; // eax
  char v267; // al
  char v268; // cl
  int v269; // eax
  char v270; // al
  char v271; // cl
  int v272; // eax
  char v273; // al
  char v274; // cl
  int v275; // eax
  char v276; // al
  int v277; // eax
  bool v278; // al
  char v279; // r9
  int v280; // eax
  char v281; // al
  char v282; // r9
  int v283; // eax
  char v284; // al
  char v285; // r9
  int v286; // eax
  char v287; // al
  char v288; // r9
  int v289; // eax
  char v290; // al
  char v291; // r9
  int v292; // eax
  char v293; // al
  char v294; // r9
  int v295; // eax
  char v296; // al
  char v297; // r9
  int v298; // eax
  char v299; // al
  int v300; // eax
  bool v301; // al
  char v302; // r9
  int v303; // eax
  char v304; // al
  char v305; // r9
  int v306; // eax
  char v307; // al
  char v308; // r9
  int v309; // eax
  char v310; // al
  char v311; // r9
  int v312; // eax
  char v313; // al
  int v314; // eax
  int v315; // edx
  ULONG v316; // eax
  __int64 v317; // r8
  __int64 v318; // r15
  PVOID v319; // r14
  __int64 v320; // r12
  ULONG v321; // r15d
  __int64 v322; // rdx
  __int64 v323; // rcx
  __int64 v324; // r12
  const WCHAR *v325; // rax
  char *v326; // rax
  char *v327; // rdx
  const WCHAR *v328; // rax
  PVOID v329; // r12
  HANDLE v330; // rcx
  __int64 v331; // rdx
  __int64 v332; // rcx
  __int64 v333; // r12
  const WCHAR *v334; // rax
  char *v335; // rax
  __int16 *v336; // rdx
  const WCHAR *v337; // rax
  __int64 v339; // [rsp+0h] [rbp-2238h] BYREF
  RTL_PATH_TYPE *PathType; // [rsp+30h] [rbp-2208h]
  PSIZE_T LengthNeeded; // [rsp+38h] [rbp-2200h]
  __int64 v342; // [rsp+48h] [rbp-21F0h]
  __int64 v343; // [rsp+50h] [rbp-21E8h]
  int v344; // [rsp+C0h] [rbp-2178h]
  int v345; // [rsp+D0h] [rbp-2168h]
  unsigned int v346; // [rsp+D4h] [rbp-2164h] BYREF
  PVOID HeapHandle; // [rsp+D8h] [rbp-2160h]
  NTSTATUS v348; // [rsp+E0h] [rbp-2158h]
  __int64 v349; // [rsp+E8h] [rbp-2150h]
  unsigned int v350; // [rsp+F0h] [rbp-2148h] BYREF
  int v351; // [rsp+F8h] [rbp-2140h] BYREF
  char v352; // [rsp+FCh] [rbp-213Ch]
  char v353; // [rsp+FDh] [rbp-213Bh]
  char v354; // [rsp+FEh] [rbp-213Ah]
  char v355; // [rsp+FFh] [rbp-2139h]
  char v356; // [rsp+100h] [rbp-2138h]
  HANDLE Process; // [rsp+108h] [rbp-2130h] BYREF
  __int64 v358; // [rsp+110h] [rbp-2128h] BYREF
  char v359; // [rsp+118h] [rbp-2120h]
  __int128 v360; // [rsp+120h] [rbp-2118h]
  __int128 v361; // [rsp+130h] [rbp-2108h]
  __int128 v362; // [rsp+140h] [rbp-20F8h]
  STRSAFE_LPCWSTR pszSrc; // [rsp+150h] [rbp-20E8h] BYREF
  LPCWSTR lpFileName; // [rsp+158h] [rbp-20E0h] BYREF
  bool v365; // [rsp+160h] [rbp-20D8h] BYREF
  char v366; // [rsp+161h] [rbp-20D7h] BYREF
  char v367; // [rsp+162h] [rbp-20D6h] BYREF
  bool v368; // [rsp+163h] [rbp-20D5h] BYREF
  bool v369; // [rsp+164h] [rbp-20D4h] BYREF
  bool v370; // [rsp+165h] [rbp-20D3h] BYREF
  bool v371; // [rsp+166h] [rbp-20D2h] BYREF
  bool v372; // [rsp+167h] [rbp-20D1h] BYREF
  bool v373; // [rsp+168h] [rbp-20D0h] BYREF
  bool v374; // [rsp+169h] [rbp-20CFh] BYREF
  bool v375; // [rsp+16Ah] [rbp-20CEh] BYREF
  char v376; // [rsp+16Bh] [rbp-20CDh] BYREF
  char v377; // [rsp+16Ch] [rbp-20CCh] BYREF
  bool v378; // [rsp+16Dh] [rbp-20CBh] BYREF
  bool v379; // [rsp+16Eh] [rbp-20CAh] BYREF
  bool v380; // [rsp+16Fh] [rbp-20C9h] BYREF
  bool v381; // [rsp+170h] [rbp-20C8h] BYREF
  bool v382; // [rsp+171h] [rbp-20C7h] BYREF
  bool v383; // [rsp+172h] [rbp-20C6h] BYREF
  bool v384; // [rsp+173h] [rbp-20C5h] BYREF
  char v385; // [rsp+174h] [rbp-20C4h] BYREF
  char v386; // [rsp+175h] [rbp-20C3h] BYREF
  bool v387; // [rsp+176h] [rbp-20C2h] BYREF
  bool v388; // [rsp+177h] [rbp-20C1h] BYREF
  bool v389; // [rsp+178h] [rbp-20C0h] BYREF
  bool v390; // [rsp+179h] [rbp-20BFh] BYREF
  bool v391; // [rsp+17Ah] [rbp-20BEh] BYREF
  bool v392; // [rsp+17Bh] [rbp-20BDh] BYREF
  bool v393; // [rsp+17Ch] [rbp-20BCh] BYREF
  char v394; // [rsp+17Dh] [rbp-20BBh] BYREF
  NTSTATUS ExitStatus; // [rsp+180h] [rbp-20B8h]
  char v396; // [rsp+184h] [rbp-20B4h]
  char v397; // [rsp+185h] [rbp-20B3h] BYREF
  char v398; // [rsp+186h] [rbp-20B2h]
  char v399; // [rsp+187h] [rbp-20B1h] BYREF
  char v400; // [rsp+188h] [rbp-20B0h] BYREF
  bool v401; // [rsp+189h] [rbp-20AFh] BYREF
  bool v402; // [rsp+18Ah] [rbp-20AEh] BYREF
  bool v403; // [rsp+18Bh] [rbp-20ADh] BYREF
  bool v404; // [rsp+18Ch] [rbp-20ACh] BYREF
  bool v405; // [rsp+18Dh] [rbp-20ABh] BYREF
  bool v406; // [rsp+18Eh] [rbp-20AAh] BYREF
  unsigned int v407; // [rsp+190h] [rbp-20A8h] BYREF
  int v408; // [rsp+194h] [rbp-20A4h]
  int v409; // [rsp+198h] [rbp-20A0h]
  __int64 v410; // [rsp+1A0h] [rbp-2098h] BYREF
  unsigned int v411; // [rsp+1A8h] [rbp-2090h] BYREF
  PWSTR v412; // [rsp+1B0h] [rbp-2088h] BYREF
  char ProcessInformation; // [rsp+1B8h] [rbp-2080h] BYREF
  char v414; // [rsp+1B9h] [rbp-207Fh]
  char v415; // [rsp+1BAh] [rbp-207Eh]
  wchar_t v416; // [rsp+1BCh] [rbp-207Ch]
  char v417[2]; // [rsp+1BEh] [rbp-207Ah] BYREF
  unsigned int v418; // [rsp+1C0h] [rbp-2078h]
  HANDLE v419; // [rsp+1C8h] [rbp-2070h]
  HANDLE v420; // [rsp+1D0h] [rbp-2068h]
  __int64 v421; // [rsp+1D8h] [rbp-2060h] BYREF
  PWSTR FileName; // [rsp+1E0h] [rbp-2058h]
  STRSAFE_LPCWSTR v423; // [rsp+1E8h] [rbp-2050h]
  __int16 v424[2]; // [rsp+1F0h] [rbp-2048h] BYREF
  _WORD v425[3]; // [rsp+1F4h] [rbp-2044h] BYREF
  char v426; // [rsp+1FAh] [rbp-203Eh]
  __int16 v427; // [rsp+1FBh] [rbp-203Dh]
  char v428; // [rsp+1FDh] [rbp-203Bh]
  __int16 v429; // [rsp+1FEh] [rbp-203Ah]
  char v430; // [rsp+200h] [rbp-2038h]
  int v431; // [rsp+201h] [rbp-2037h]
  __int16 v432; // [rsp+205h] [rbp-2033h]
  char v433; // [rsp+207h] [rbp-2031h]
  __int128 v434; // [rsp+208h] [rbp-2030h]
  __int64 v435; // [rsp+218h] [rbp-2020h]
  __int64 v436; // [rsp+220h] [rbp-2018h]
  __int64 v437; // [rsp+228h] [rbp-2010h]
  HANDLE ThreadHandle[2]; // [rsp+230h] [rbp-2008h] BYREF
  char v439; // [rsp+240h] [rbp-1FF8h]
  int v440; // [rsp+241h] [rbp-1FF7h]
  __int16 v441; // [rsp+245h] [rbp-1FF3h]
  char v442; // [rsp+247h] [rbp-1FF1h]
  __int128 v443; // [rsp+248h] [rbp-1FF0h]
  __int128 v444; // [rsp+258h] [rbp-1FE0h]
  __int64 v445; // [rsp+268h] [rbp-1FD0h]
  __int64 v446; // [rsp+270h] [rbp-1FC8h]
  char v447; // [rsp+278h] [rbp-1FC0h]
  int v448; // [rsp+279h] [rbp-1FBFh]
  __int16 v449; // [rsp+27Dh] [rbp-1FBBh]
  char v450; // [rsp+27Fh] [rbp-1FB9h]
  __int64 v451; // [rsp+280h] [rbp-1FB8h]
  __int64 v452; // [rsp+288h] [rbp-1FB0h]
  __int16 v453; // [rsp+290h] [rbp-1FA8h]
  char v454; // [rsp+292h] [rbp-1FA6h]
  int v455; // [rsp+293h] [rbp-1FA5h]
  char v456; // [rsp+297h] [rbp-1FA1h]
  __int64 v457; // [rsp+298h] [rbp-1FA0h]
  bool v458; // [rsp+2A0h] [rbp-1F98h] BYREF
  bool v459; // [rsp+2A1h] [rbp-1F97h] BYREF
  bool v460; // [rsp+2A2h] [rbp-1F96h] BYREF
  bool v461; // [rsp+2A3h] [rbp-1F95h] BYREF
  char v462; // [rsp+2A4h] [rbp-1F94h]
  bool v463; // [rsp+2A5h] [rbp-1F93h] BYREF
  _BYTE v464[2]; // [rsp+2A6h] [rbp-1F92h] BYREF
  int v465; // [rsp+2A8h] [rbp-1F90h] BYREF
  unsigned int v466; // [rsp+2ACh] [rbp-1F8Ch] BYREF
  bool v467; // [rsp+2B0h] [rbp-1F88h] BYREF
  char v468; // [rsp+2B1h] [rbp-1F87h]
  bool v469; // [rsp+2B2h] [rbp-1F86h] BYREF
  char v470; // [rsp+2B3h] [rbp-1F85h]
  char v471; // [rsp+2B4h] [rbp-1F84h]
  char v472; // [rsp+2B5h] [rbp-1F83h]
  bool v473; // [rsp+2B6h] [rbp-1F82h] BYREF
  bool v474; // [rsp+2B7h] [rbp-1F81h] BYREF
  bool v475; // [rsp+2B8h] [rbp-1F80h] BYREF
  bool v476; // [rsp+2B9h] [rbp-1F7Fh] BYREF
  const wchar_t *v477; // [rsp+2C0h] [rbp-1F78h]
  int v478; // [rsp+2C8h] [rbp-1F70h]
  int v479; // [rsp+2CCh] [rbp-1F6Ch] BYREF
  int v480; // [rsp+2D0h] [rbp-1F68h] BYREF
  unsigned int NumberOfBytesToWrite; // [rsp+2D4h] [rbp-1F64h] BYREF
  unsigned int NumberOfBytesToWrite_4; // [rsp+2D8h] [rbp-1F60h] BYREF
  _DWORD *v483; // [rsp+2E0h] [rbp-1F58h]
  HANDLE Handle; // [rsp+2E8h] [rbp-1F50h]
  int v485; // [rsp+2F0h] [rbp-1F48h]
  LPCWSTR v486; // [rsp+2F8h] [rbp-1F40h]
  PWSTR v487; // [rsp+300h] [rbp-1F38h]
  int v488; // [rsp+308h] [rbp-1F30h]
  int v489; // [rsp+30Ch] [rbp-1F2Ch] BYREF
  __int64 v490; // [rsp+310h] [rbp-1F28h] BYREF
  struct _UNICODE_STRING v491; // [rsp+318h] [rbp-1F20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+330h] [rbp-1F08h] BYREF
  __int64 v493; // [rsp+340h] [rbp-1EF8h]
  int v494; // [rsp+348h] [rbp-1EF0h] BYREF
  int v495; // [rsp+34Ch] [rbp-1EECh] BYREF
  int v496; // [rsp+350h] [rbp-1EE8h] BYREF
  __int64 v497; // [rsp+358h] [rbp-1EE0h]
  HANDLE v498; // [rsp+360h] [rbp-1ED8h] BYREF
  int v499; // [rsp+368h] [rbp-1ED0h]
  int v500; // [rsp+36Ch] [rbp-1ECCh] BYREF
  __int64 v501; // [rsp+370h] [rbp-1EC8h] BYREF
  PWSTR Environment; // [rsp+378h] [rbp-1EC0h] BYREF
  int v503; // [rsp+380h] [rbp-1EB8h]
  HANDLE v504; // [rsp+388h] [rbp-1EB0h]
  PVOID v505; // [rsp+390h] [rbp-1EA8h] BYREF
  _QWORD *v506; // [rsp+398h] [rbp-1EA0h] BYREF
  HANDLE token[2]; // [rsp+3A0h] [rbp-1E98h] BYREF
  __int64 v508; // [rsp+3B0h] [rbp-1E88h] BYREF
  PVOID P; // [rsp+3B8h] [rbp-1E80h]
  PVOID v510; // [rsp+3C0h] [rbp-1E78h]
  PCSR_CAPTURE_BUFFER CaptureBuffer; // [rsp+3C8h] [rbp-1E70h] BYREF
  ULONG ReturnedLength; // [rsp+3D0h] [rbp-1E68h] BYREF
  unsigned int v513; // [rsp+3D4h] [rbp-1E64h]
  int v514; // [rsp+3D8h] [rbp-1E60h]
  int v515; // [rsp+3DCh] [rbp-1E5Ch]
  int v516; // [rsp+3E0h] [rbp-1E58h]
  int v517; // [rsp+3E4h] [rbp-1E54h]
  int v518; // [rsp+3E8h] [rbp-1E50h] BYREF
  ULONG v519; // [rsp+3ECh] [rbp-1E4Ch] BYREF
  unsigned int v520; // [rsp+3F0h] [rbp-1E48h] BYREF
  unsigned int v521; // [rsp+3F4h] [rbp-1E44h] BYREF
  int v522; // [rsp+3F8h] [rbp-1E40h]
  ULONG v523; // [rsp+3FCh] [rbp-1E3Ch] BYREF
  int v524; // [rsp+400h] [rbp-1E38h] BYREF
  ULONG v525; // [rsp+404h] [rbp-1E34h] BYREF
  unsigned int v526; // [rsp+408h] [rbp-1E30h] BYREF
  ULONG v527; // [rsp+40Ch] [rbp-1E2Ch] BYREF
  unsigned int v528; // [rsp+410h] [rbp-1E28h] BYREF
  ULONG v529; // [rsp+414h] [rbp-1E24h] BYREF
  char v530; // [rsp+418h] [rbp-1E20h]
  char v531; // [rsp+419h] [rbp-1E1Fh]
  HANDLE TokenHandle; // [rsp+420h] [rbp-1E18h] BYREF
  HANDLE v533; // [rsp+428h] [rbp-1E10h]
  __int64 v534; // [rsp+430h] [rbp-1E08h] BYREF
  void *v535; // [rsp+438h] [rbp-1E00h]
  void *Src; // [rsp+440h] [rbp-1DF8h]
  PVOID v537; // [rsp+448h] [rbp-1DF0h]
  char v538; // [rsp+450h] [rbp-1DE8h]
  char v539; // [rsp+451h] [rbp-1DE7h]
  char v540; // [rsp+452h] [rbp-1DE6h]
  struct _UNICODE_STRING UnicodeString; // [rsp+458h] [rbp-1DE0h] BYREF
  wchar_t v542; // [rsp+468h] [rbp-1DD0h]
  __int16 v543; // [rsp+46Ch] [rbp-1DCCh] BYREF
  int v544; // [rsp+470h] [rbp-1DC8h] BYREF
  int v545; // [rsp+474h] [rbp-1DC4h] BYREF
  HANDLE ProcessHandle; // [rsp+478h] [rbp-1DC0h] BYREF
  LPCWSTR lpPath; // [rsp+480h] [rbp-1DB8h] BYREF
  struct _PEB *v548; // [rsp+488h] [rbp-1DB0h]
  HANDLE v549; // [rsp+490h] [rbp-1DA8h]
  PVOID v550; // [rsp+498h] [rbp-1DA0h]
  __int64 v551; // [rsp+4A0h] [rbp-1D98h]
  int v552; // [rsp+4A8h] [rbp-1D90h]
  __int64 v553; // [rsp+4B0h] [rbp-1D88h]
  STRSAFE_LPCWSTR v554; // [rsp+4B8h] [rbp-1D80h]
  int v555; // [rsp+4C0h] [rbp-1D78h] BYREF
  int v556; // [rsp+4C4h] [rbp-1D74h]
  int v557; // [rsp+4C8h] [rbp-1D70h] BYREF
  int TokenInformation; // [rsp+4CCh] [rbp-1D6Ch] BYREF
  ULONG ReturnLength; // [rsp+4D0h] [rbp-1D68h] BYREF
  int v560; // [rsp+4D4h] [rbp-1D64h] BYREF
  int v561; // [rsp+4D8h] [rbp-1D60h]
  int v562; // [rsp+4DCh] [rbp-1D5Ch]
  ULONG Response; // [rsp+4E0h] [rbp-1D58h] BYREF
  int v564; // [rsp+4E4h] [rbp-1D54h]
  int v565; // [rsp+4E8h] [rbp-1D50h] BYREF
  int v566; // [rsp+4ECh] [rbp-1D4Ch] BYREF
  int v567; // [rsp+4F0h] [rbp-1D48h] BYREF
  int v568; // [rsp+4F4h] [rbp-1D44h] BYREF
  RTL_PATH_TYPE v569; // [rsp+4F8h] [rbp-1D40h] BYREF
  PVOID BaseAddress; // [rsp+500h] [rbp-1D38h] BYREF
  RTL_PATH_TYPE InputPathType; // [rsp+508h] [rbp-1D30h] BYREF
  BOOL Result; // [rsp+50Ch] [rbp-1D2Ch] BYREF
  int v573; // [rsp+510h] [rbp-1D28h] BYREF
  int v574; // [rsp+514h] [rbp-1D24h] BYREF
  PVOID Buffer; // [rsp+518h] [rbp-1D20h]
  __int64 v576; // [rsp+520h] [rbp-1D18h]
  PVOID v577; // [rsp+528h] [rbp-1D10h]
  HANDLE DebugObject; // [rsp+530h] [rbp-1D08h]
  PVOID v579; // [rsp+538h] [rbp-1D00h]
  PWSTR v580; // [rsp+540h] [rbp-1CF8h] BYREF
  STRSAFE_LPCWSTR v581; // [rsp+548h] [rbp-1CF0h]
  __int64 v582; // [rsp+550h] [rbp-1CE8h] BYREF
  WCHAR *v583; // [rsp+558h] [rbp-1CE0h] BYREF
  __int64 v584; // [rsp+560h] [rbp-1CD8h] BYREF
  __int64 v585; // [rsp+568h] [rbp-1CD0h] BYREF
  struct _UNICODE_STRING v586; // [rsp+570h] [rbp-1CC8h] BYREF
  __int128 v587; // [rsp+580h] [rbp-1CB8h]
  __int64 v588; // [rsp+590h] [rbp-1CA8h]
  struct _UNICODE_STRING v589; // [rsp+598h] [rbp-1CA0h] BYREF
  ULONG v590; // [rsp+5A8h] [rbp-1C90h]
  int v591; // [rsp+5ACh] [rbp-1C8Ch] BYREF
  UINT32 packageFullNameLength; // [rsp+5B0h] [rbp-1C88h] BYREF
  LONG v593; // [rsp+5B4h] [rbp-1C84h] BYREF
  LONG v594; // [rsp+5B8h] [rbp-1C80h] BYREF
  UINT32 v595; // [rsp+5BCh] [rbp-1C7Ch] BYREF
  LONG v596; // [rsp+5C0h] [rbp-1C78h] BYREF
  UINT32 v597; // [rsp+5C4h] [rbp-1C74h] BYREF
  int v598; // [rsp+5C8h] [rbp-1C70h]
  UINT32 applicationUserModelIdLength; // [rsp+5CCh] [rbp-1C6Ch] BYREF
  int v600; // [rsp+5D0h] [rbp-1C68h] BYREF
  unsigned int v601; // [rsp+5D4h] [rbp-1C64h] BYREF
  int v602; // [rsp+5D8h] [rbp-1C60h] BYREF
  __int64 v603; // [rsp+5E0h] [rbp-1C58h]
  PVOID v604; // [rsp+5E8h] [rbp-1C50h]
  __int64 v605; // [rsp+5F0h] [rbp-1C48h] BYREF
  __int16 *v606; // [rsp+5F8h] [rbp-1C40h]
  __int64 v607; // [rsp+600h] [rbp-1C38h]
  PVOID v608; // [rsp+608h] [rbp-1C30h]
  __int64 v609; // [rsp+610h] [rbp-1C28h] BYREF
  __int64 v610; // [rsp+618h] [rbp-1C20h] BYREF
  HANDLE v611; // [rsp+620h] [rbp-1C18h] BYREF
  int v612; // [rsp+628h] [rbp-1C10h]
  LONG v613; // [rsp+62Ch] [rbp-1C0Ch] BYREF
  BOOL v614; // [rsp+630h] [rbp-1C08h]
  unsigned int v615; // [rsp+634h] [rbp-1C04h] BYREF
  int v616; // [rsp+638h] [rbp-1C00h] BYREF
  __int64 v617; // [rsp+640h] [rbp-1BF8h] BYREF
  int v618; // [rsp+648h] [rbp-1BF0h]
  HANDLE KeyHandle; // [rsp+650h] [rbp-1BE8h]
  void *v620; // [rsp+658h] [rbp-1BE0h]
  void *v621; // [rsp+660h] [rbp-1BD8h]
  int v622; // [rsp+674h] [rbp-1BC4h]
  __int64 v623; // [rsp+678h] [rbp-1BC0h]
  unsigned int v624; // [rsp+680h] [rbp-1BB8h]
  unsigned __int64 v625; // [rsp+688h] [rbp-1BB0h]
  int v626; // [rsp+690h] [rbp-1BA8h]
  __int64 v627; // [rsp+6A0h] [rbp-1B98h] BYREF
  __int64 v628; // [rsp+6A8h] [rbp-1B90h]
  struct _UNICODE_STRING DynamicString; // [rsp+6B0h] [rbp-1B88h] BYREF
  __int64 v630; // [rsp+6C0h] [rbp-1B78h] BYREF
  __int64 v631; // [rsp+6C8h] [rbp-1B70h]
  __int64 v632; // [rsp+6D0h] [rbp-1B68h] BYREF
  __int64 v633; // [rsp+6D8h] [rbp-1B60h] BYREF
  __int64 v634; // [rsp+6E0h] [rbp-1B58h]
  _QWORD v635[2]; // [rsp+6E8h] [rbp-1B50h] BYREF
  __m128i v636; // [rsp+6F8h] [rbp-1B40h] BYREF
  unsigned __int64 v637; // [rsp+708h] [rbp-1B30h]
  unsigned __int64 v638; // [rsp+710h] [rbp-1B28h] BYREF
  unsigned __int64 v639; // [rsp+718h] [rbp-1B20h]
  __int64 v640; // [rsp+720h] [rbp-1B18h]
  ULONG_PTR RegionSize; // [rsp+728h] [rbp-1B10h] BYREF
  PVOID v642; // [rsp+730h] [rbp-1B08h]
  __int64 v643; // [rsp+738h] [rbp-1B00h] BYREF
  __int64 v644; // [rsp+740h] [rbp-1AF8h] BYREF
  int v645; // [rsp+748h] [rbp-1AF0h]
  int v646; // [rsp+74Ch] [rbp-1AECh]
  int v647; // [rsp+750h] [rbp-1AE8h]
  int v648; // [rsp+754h] [rbp-1AE4h]
  __int64 v649; // [rsp+758h] [rbp-1AE0h] BYREF
  __int64 v650; // [rsp+760h] [rbp-1AD8h] BYREF
  PWSTR FilePart; // [rsp+768h] [rbp-1AD0h] BYREF
  __int64 v652; // [rsp+770h] [rbp-1AC8h] BYREF
  __int64 v653; // [rsp+778h] [rbp-1AC0h] BYREF
  __int64 v654; // [rsp+780h] [rbp-1AB8h] BYREF
  __int64 v655; // [rsp+788h] [rbp-1AB0h] BYREF
  __int64 v656; // [rsp+790h] [rbp-1AA8h] BYREF
  __int64 v657; // [rsp+798h] [rbp-1AA0h] BYREF
  __m128i Buf1; // [rsp+7A0h] [rbp-1A98h] BYREF
  __int128 v659; // [rsp+7B0h] [rbp-1A88h]
  __int128 v660; // [rsp+7C0h] [rbp-1A78h]
  __int128 v661; // [rsp+7D0h] [rbp-1A68h]
  __int128 v662; // [rsp+7E0h] [rbp-1A58h]
  __int128 v663; // [rsp+7F0h] [rbp-1A48h]
  __int64 v664; // [rsp+800h] [rbp-1A38h]
  __int128 v665; // [rsp+810h] [rbp-1A28h] BYREF
  _BYTE v666[32]; // [rsp+820h] [rbp-1A18h] BYREF
  int v667; // [rsp+840h] [rbp-19F8h]
  unsigned __int16 v668; // [rsp+844h] [rbp-19F4h]
  unsigned __int16 v669; // [rsp+846h] [rbp-19F2h]
  unsigned __int16 v670; // [rsp+84Eh] [rbp-19EAh]
  unsigned __int16 v671; // [rsp+850h] [rbp-19E8h]
  unsigned __int64 Parameters[4]; // [rsp+860h] [rbp-19D8h] BYREF
  __int64 *v673; // [rsp+880h] [rbp-19B8h]
  __int128 v674; // [rsp+888h] [rbp-19B0h] BYREF
  _OWORD v675[3]; // [rsp+898h] [rbp-19A0h] BYREF
  __int64 v676; // [rsp+8C8h] [rbp-1970h]
  _OWORD v677[3]; // [rsp+8D0h] [rbp-1968h] BYREF
  _OWORD v678[3]; // [rsp+900h] [rbp-1938h] BYREF
  int Buf2; // [rsp+930h] [rbp-1908h] BYREF
  char v680[108]; // [rsp+934h] [rbp-1904h] BYREF
  int v681; // [rsp+9A0h] [rbp-1898h] BYREF
  char v682[108]; // [rsp+9A4h] [rbp-1894h] BYREF
  _BYTE v683[96]; // [rsp+A10h] [rbp-1828h] BYREF
  __int128 v684; // [rsp+A70h] [rbp-17C8h] BYREF
  __int128 v685; // [rsp+A80h] [rbp-17B8h]
  __int128 v686; // [rsp+A90h] [rbp-17A8h] BYREF
  __int128 v687; // [rsp+AA0h] [rbp-1798h] BYREF
  __int128 v688; // [rsp+AB0h] [rbp-1788h] BYREF
  __int64 v689; // [rsp+AC0h] [rbp-1778h]
  __int128 v690; // [rsp+AC8h] [rbp-1770h] BYREF
  __int128 v691; // [rsp+AD8h] [rbp-1760h] BYREF
  __int128 v692; // [rsp+AE8h] [rbp-1750h] BYREF
  __int64 v693; // [rsp+AF8h] [rbp-1740h]
  __int128 v694; // [rsp+B00h] [rbp-1738h] BYREF
  __int64 v695; // [rsp+B10h] [rbp-1728h]
  _BYTE ApiMessage[52]; // [rsp+B20h] [rbp-1718h] BYREF
  NTSTATUS v697; // [rsp+B54h] [rbp-16E4h]
  unsigned __int64 v698; // [rsp+B60h] [rbp-16D8h]
  unsigned __int64 v699; // [rsp+B68h] [rbp-16D0h]
  __m128i v700; // [rsp+B70h] [rbp-16C8h]
  unsigned int v701; // [rsp+B80h] [rbp-16B8h]
  unsigned int v702; // [rsp+B84h] [rbp-16B4h]
  unsigned int v703; // [rsp+B88h] [rbp-16B0h]
  __int64 v704; // [rsp+B90h] [rbp-16A8h]
  _BYTE v705[4]; // [rsp+B98h] [rbp-16A0h] BYREF
  int v706; // [rsp+B9Ch] [rbp-169Ch]
  _BYTE v707[12]; // [rsp+C30h] [rbp-1608h] BYREF
  _WORD v708[2]; // [rsp+C3Ch] [rbp-15FCh] BYREF
  _BYTE v709[16]; // [rsp+C40h] [rbp-15F8h] BYREF
  __int64 v710; // [rsp+C50h] [rbp-15E8h] BYREF
  __int16 v711; // [rsp+C58h] [rbp-15E0h] BYREF
  __int64 v712; // [rsp+D60h] [rbp-14D8h]
  __int64 v713; // [rsp+D68h] [rbp-14D0h]
  __int16 v714; // [rsp+D70h] [rbp-14C8h]
  __int64 v715; // [rsp+EE0h] [rbp-1358h] BYREF
  __int64 v716; // [rsp+EE8h] [rbp-1350h]
  __int64 v717; // [rsp+EF0h] [rbp-1348h]
  PWSTR v718; // [rsp+EF8h] [rbp-1340h]
  _QWORD v719[134]; // [rsp+F00h] [rbp-1338h]
  char v720[8]; // [rsp+1330h] [rbp-F08h] BYREF
  __int64 v721; // [rsp+1338h] [rbp-F00h]
  __int64 v722; // [rsp+1340h] [rbp-EF8h]
  struct _UNICODE_STRING *v723; // [rsp+1348h] [rbp-EF0h]
  __int64 v724; // [rsp+1350h] [rbp-EE8h]
  __int64 v725; // [rsp+1358h] [rbp-EE0h]
  __int64 v726; // [rsp+1360h] [rbp-ED8h]
  __int64 *v727; // [rsp+1368h] [rbp-ED0h]
  __int64 v728; // [rsp+1370h] [rbp-EC8h]
  char v729; // [rsp+1780h] [rbp-AB8h] BYREF
  __int64 *v730; // [rsp+17A0h] [rbp-A98h]
  __int64 v731; // [rsp+17A8h] [rbp-A90h]
  char *v732; // [rsp+17B0h] [rbp-A88h]
  __int64 v733; // [rsp+17B8h] [rbp-A80h]
  ULONG *v734; // [rsp+17C0h] [rbp-A78h]
  __int64 v735; // [rsp+17C8h] [rbp-A70h]
  char *v736; // [rsp+17D0h] [rbp-A68h]
  __int64 v737; // [rsp+17D8h] [rbp-A60h]
  char v738[16]; // [rsp+17E0h] [rbp-A58h] BYREF
  char v739[16]; // [rsp+17F0h] [rbp-A48h] BYREF
  bool *v740; // [rsp+1800h] [rbp-A38h]
  __int64 v741; // [rsp+1808h] [rbp-A30h]
  bool *v742; // [rsp+1810h] [rbp-A28h]
  __int64 v743; // [rsp+1818h] [rbp-A20h]
  bool *v744; // [rsp+1820h] [rbp-A18h]
  __int64 v745; // [rsp+1828h] [rbp-A10h]
  bool *v746; // [rsp+1830h] [rbp-A08h]
  __int64 v747; // [rsp+1838h] [rbp-A00h]
  unsigned int *v748; // [rsp+1840h] [rbp-9F8h]
  __int64 v749; // [rsp+1848h] [rbp-9F0h]
  bool *v750; // [rsp+1850h] [rbp-9E8h]
  __int64 v751; // [rsp+1858h] [rbp-9E0h]
  bool *v752; // [rsp+1860h] [rbp-9D8h]
  __int64 v753; // [rsp+1868h] [rbp-9D0h]
  bool *v754; // [rsp+1870h] [rbp-9C8h]
  __int64 v755; // [rsp+1878h] [rbp-9C0h]
  char v756; // [rsp+1880h] [rbp-9B8h] BYREF
  __int64 *v757; // [rsp+18A0h] [rbp-998h]
  __int64 v758; // [rsp+18A8h] [rbp-990h]
  char *v759; // [rsp+18B0h] [rbp-988h]
  __int64 v760; // [rsp+18B8h] [rbp-980h]
  ULONG *v761; // [rsp+18C0h] [rbp-978h]
  __int64 v762; // [rsp+18C8h] [rbp-970h]
  char *v763; // [rsp+18D0h] [rbp-968h]
  __int64 v764; // [rsp+18D8h] [rbp-960h]
  char v765[16]; // [rsp+18E0h] [rbp-958h] BYREF
  char v766[16]; // [rsp+18F0h] [rbp-948h] BYREF
  bool *v767; // [rsp+1900h] [rbp-938h]
  __int64 v768; // [rsp+1908h] [rbp-930h]
  bool *v769; // [rsp+1910h] [rbp-928h]
  __int64 v770; // [rsp+1918h] [rbp-920h]
  bool *v771; // [rsp+1920h] [rbp-918h]
  __int64 v772; // [rsp+1928h] [rbp-910h]
  bool *v773; // [rsp+1930h] [rbp-908h]
  __int64 v774; // [rsp+1938h] [rbp-900h]
  unsigned int *v775; // [rsp+1940h] [rbp-8F8h]
  __int64 v776; // [rsp+1948h] [rbp-8F0h]
  bool *v777; // [rsp+1950h] [rbp-8E8h]
  __int64 v778; // [rsp+1958h] [rbp-8E0h]
  bool *v779; // [rsp+1960h] [rbp-8D8h]
  __int64 v780; // [rsp+1968h] [rbp-8D0h]
  bool *v781; // [rsp+1970h] [rbp-8C8h]
  __int64 v782; // [rsp+1978h] [rbp-8C0h]
  char v783; // [rsp+1980h] [rbp-8B8h] BYREF
  char *v784; // [rsp+19A0h] [rbp-898h]
  __int64 v785; // [rsp+19A8h] [rbp-890h]
  ULONG *v786; // [rsp+19B0h] [rbp-888h]
  __int64 v787; // [rsp+19B8h] [rbp-880h]
  char *v788; // [rsp+19C0h] [rbp-878h]
  __int64 v789; // [rsp+19C8h] [rbp-870h]
  char v790[16]; // [rsp+19D0h] [rbp-868h] BYREF
  char v791[16]; // [rsp+19E0h] [rbp-858h] BYREF
  bool *v792; // [rsp+19F0h] [rbp-848h]
  __int64 v793; // [rsp+19F8h] [rbp-840h]
  bool *v794; // [rsp+1A00h] [rbp-838h]
  __int64 v795; // [rsp+1A08h] [rbp-830h]
  bool *v796; // [rsp+1A10h] [rbp-828h]
  __int64 v797; // [rsp+1A18h] [rbp-820h]
  bool *v798; // [rsp+1A20h] [rbp-818h]
  __int64 v799; // [rsp+1A28h] [rbp-810h]
  unsigned int *v800; // [rsp+1A30h] [rbp-808h]
  __int64 v801; // [rsp+1A38h] [rbp-800h]
  bool *v802; // [rsp+1A40h] [rbp-7F8h]
  __int64 v803; // [rsp+1A48h] [rbp-7F0h]
  bool *v804; // [rsp+1A50h] [rbp-7E8h]
  __int64 v805; // [rsp+1A58h] [rbp-7E0h]
  bool *v806; // [rsp+1A60h] [rbp-7D8h]
  __int64 v807; // [rsp+1A68h] [rbp-7D0h]
  char v808; // [rsp+1A70h] [rbp-7C8h] BYREF
  char *v809; // [rsp+1A90h] [rbp-7A8h]
  __int64 v810; // [rsp+1A98h] [rbp-7A0h]
  ULONG *v811; // [rsp+1AA0h] [rbp-798h]
  __int64 v812; // [rsp+1AA8h] [rbp-790h]
  char *v813; // [rsp+1AB0h] [rbp-788h]
  __int64 v814; // [rsp+1AB8h] [rbp-780h]
  char v815[16]; // [rsp+1AC0h] [rbp-778h] BYREF
  char v816[16]; // [rsp+1AD0h] [rbp-768h] BYREF
  bool *v817; // [rsp+1AE0h] [rbp-758h]
  __int64 v818; // [rsp+1AE8h] [rbp-750h]
  bool *v819; // [rsp+1AF0h] [rbp-748h]
  __int64 v820; // [rsp+1AF8h] [rbp-740h]
  bool *v821; // [rsp+1B00h] [rbp-738h]
  __int64 v822; // [rsp+1B08h] [rbp-730h]
  bool *v823; // [rsp+1B10h] [rbp-728h]
  __int64 v824; // [rsp+1B18h] [rbp-720h]
  unsigned int *v825; // [rsp+1B20h] [rbp-718h]
  __int64 v826; // [rsp+1B28h] [rbp-710h]
  bool *v827; // [rsp+1B30h] [rbp-708h]
  __int64 v828; // [rsp+1B38h] [rbp-700h]
  bool *v829; // [rsp+1B40h] [rbp-6F8h]
  __int64 v830; // [rsp+1B48h] [rbp-6F0h]
  bool *v831; // [rsp+1B50h] [rbp-6E8h]
  __int64 v832; // [rsp+1B58h] [rbp-6E0h]
  char v833[32]; // [rsp+1B60h] [rbp-6D8h] BYREF
  __int64 *v834; // [rsp+1B80h] [rbp-6B8h]
  __int64 v835; // [rsp+1B88h] [rbp-6B0h]
  ULONG *v836; // [rsp+1B90h] [rbp-6A8h]
  __int64 v837; // [rsp+1B98h] [rbp-6A0h]
  char v838[16]; // [rsp+1BA0h] [rbp-698h] BYREF
  bool *v839; // [rsp+1BB0h] [rbp-688h]
  __int64 v840; // [rsp+1BB8h] [rbp-680h]
  int *v841; // [rsp+1BC0h] [rbp-678h]
  __int64 v842; // [rsp+1BC8h] [rbp-670h]
  char v843[32]; // [rsp+1BD0h] [rbp-668h] BYREF
  __int64 *v844; // [rsp+1BF0h] [rbp-648h]
  __int64 v845; // [rsp+1BF8h] [rbp-640h]
  char v846[16]; // [rsp+1C00h] [rbp-638h] BYREF
  _BYTE *v847; // [rsp+1C10h] [rbp-628h]
  __int64 v848; // [rsp+1C18h] [rbp-620h]
  bool *v849; // [rsp+1C20h] [rbp-618h]
  __int64 v850; // [rsp+1C28h] [rbp-610h]
  bool *v851; // [rsp+1C30h] [rbp-608h]
  __int64 v852; // [rsp+1C38h] [rbp-600h]
  unsigned int *v853; // [rsp+1C40h] [rbp-5F8h]
  __int64 v854; // [rsp+1C48h] [rbp-5F0h]
  bool *v855; // [rsp+1C50h] [rbp-5E8h]
  __int64 v856; // [rsp+1C58h] [rbp-5E0h]
  bool *v857; // [rsp+1C60h] [rbp-5D8h]
  __int64 v858; // [rsp+1C68h] [rbp-5D0h]
  char v859[32]; // [rsp+1C70h] [rbp-5C8h] BYREF
  __int64 *v860; // [rsp+1C90h] [rbp-5A8h]
  __int64 v861; // [rsp+1C98h] [rbp-5A0h]
  char v862[16]; // [rsp+1CA0h] [rbp-598h] BYREF
  bool *v863; // [rsp+1CB0h] [rbp-588h]
  __int64 v864; // [rsp+1CB8h] [rbp-580h]
  bool *v865; // [rsp+1CC0h] [rbp-578h]
  __int64 v866; // [rsp+1CC8h] [rbp-570h]
  bool *v867; // [rsp+1CD0h] [rbp-568h]
  __int64 v868; // [rsp+1CD8h] [rbp-560h]
  unsigned int *v869; // [rsp+1CE0h] [rbp-558h]
  __int64 v870; // [rsp+1CE8h] [rbp-550h]
  bool *v871; // [rsp+1CF0h] [rbp-548h]
  __int64 v872; // [rsp+1CF8h] [rbp-540h]
  bool *v873; // [rsp+1D00h] [rbp-538h]
  __int64 v874; // [rsp+1D08h] [rbp-530h]
  char v875[32]; // [rsp+1D10h] [rbp-528h] BYREF
  __int64 *v876; // [rsp+1D30h] [rbp-508h]
  __int64 v877; // [rsp+1D38h] [rbp-500h]
  LONG *v878; // [rsp+1D40h] [rbp-4F8h]
  __int64 v879; // [rsp+1D48h] [rbp-4F0h]
  bool *v880; // [rsp+1D50h] [rbp-4E8h]
  __int64 v881; // [rsp+1D58h] [rbp-4E0h]
  char v882[32]; // [rsp+1D60h] [rbp-4D8h] BYREF
  __int64 *v883; // [rsp+1D80h] [rbp-4B8h]
  __int64 v884; // [rsp+1D88h] [rbp-4B0h]
  LONG *v885; // [rsp+1D90h] [rbp-4A8h]
  __int64 v886; // [rsp+1D98h] [rbp-4A0h]
  bool *v887; // [rsp+1DA0h] [rbp-498h]
  __int64 v888; // [rsp+1DA8h] [rbp-490h]
  char v889[32]; // [rsp+1DB0h] [rbp-488h] BYREF
  __int64 *v890; // [rsp+1DD0h] [rbp-468h]
  __int64 v891; // [rsp+1DD8h] [rbp-460h]
  int *v892; // [rsp+1DE0h] [rbp-458h]
  __int64 v893; // [rsp+1DE8h] [rbp-450h]
  char v894[16]; // [rsp+1DF0h] [rbp-448h] BYREF
  int *v895; // [rsp+1E00h] [rbp-438h]
  __int64 v896; // [rsp+1E08h] [rbp-430h]
  char v897; // [rsp+1E10h] [rbp-428h] BYREF
  __int64 *v898; // [rsp+1E30h] [rbp-408h]
  __int64 v899; // [rsp+1E38h] [rbp-400h]
  LONG *v900; // [rsp+1E40h] [rbp-3F8h]
  __int64 v901; // [rsp+1E48h] [rbp-3F0h]
  char v902[16]; // [rsp+1E50h] [rbp-3E8h] BYREF
  char v903[16]; // [rsp+1E60h] [rbp-3D8h] BYREF
  char v904; // [rsp+1E70h] [rbp-3C8h] BYREF
  __int64 *v905; // [rsp+1E90h] [rbp-3A8h]
  __int64 v906; // [rsp+1E98h] [rbp-3A0h]
  LONG *v907; // [rsp+1EA0h] [rbp-398h]
  __int64 v908; // [rsp+1EA8h] [rbp-390h]
  char v909[16]; // [rsp+1EB0h] [rbp-388h] BYREF
  char v910[16]; // [rsp+1EC0h] [rbp-378h] BYREF
  WCHAR packageFullName[128]; // [rsp+1ED0h] [rbp-368h] BYREF
  _WORD v912[136]; // [rsp+1FD0h] [rbp-268h] BYREF
  WCHAR applicationUserModelId[64]; // [rsp+20E0h] [rbp-158h] BYREF

  v673 = &v339;
  v497 = a4;
  v535 = a1;
  v14 = a11;
  v349 = a11;
  v15 = a7;
  lpFileName = a2;
  pszSrc = a3;
  v553 = a4;
  v493 = a5;
  v551 = a5;
  v350 = a7;
  v412 = a8;
  FileName = a9;
  v634 = a10;
  v607 = a11;
  ReturnLength = 0;
  NumberOfBytesToWrite_4 = 0;
  v407 = 0;
  v411 = 0;
  v627 = 0;
  v630 = 0;
  v580 = 0;
  Buf1.m128i_i32[1] = 0;
  memset_0(&Buf1, 0, 0x64u);
  lpPath = 0;
  memset_0(ApiMessage, 0, 0x3B8u);
  ReturnedLength = 0;
  memset(v677, 0, 44);
  memset(v678, 0, 44);
  v633 = 0;
  v632 = 0;
  UnicodeString = 0;
  DestinationString = 0;
  v684 = 0;
  v685 = 0;
  v360 = 0;
  v361 = 0;
  v362 = 0;
  v635[0] = 1310738;
  v635[1] = L"ntdll.dll";
  memset_0(&v617, 0, 0x58u);
  Result = 0;
  v574 = 0;
  v569 = RtlPathTypeUnknown;
  memset_0(v666, 0, 0x40u);
  DynamicString = 0;
  *(_QWORD *)&v589.Length = 0;
  v394 = 0;
  Response = 0;
  v496 = 0;
  BaseAddress = 0;
  RegionSize = 0;
  memset_0(&v715, 0, 0x448u);
  v346 = 0;
  memset_0(v720, 0, 0x448u);
  v490 = 0;
  v636 = 0;
  v491 = 0;
  v506 = 0;
  Environment = 0;
  v583 = 0;
  v504 = 0;
  v421 = 0;
  v417[0] = 0;
  v465 = 0;
  v358 = 0;
  v410 = 0;
  TokenHandle = 0;
  ProcessInformation = 0;
  v424[0] = 0;
  v543 = 0;
  v425[0] = 0;
  memset(v675, 0, sizeof(v675));
  v676 = 0;
  v674 = 0;
  v650 = 0;
  v566 = 0;
  v545 = 0;
  v687 = 0;
  v686 = 0;
  v690 = 0;
  v691 = 0;
  v573 = 0;
  v638 = 0;
  v567 = 0;
  if ( !a2 && !a3 )
  {
    v16 = 3221225520LL;
LABEL_1279:
    BaseSetLastNTError(v16);
    return 0;
  }
  if ( !v14 || (v17 = v634) == 0 )
  {
    v16 = 3221225485LL;
    goto LABEL_1279;
  }
  v498 = 0;
  Process = 0;
  ThreadHandle[0] = 0;
  CaptureBuffer = 0;
  v602 = 0;
  FilePart = 0;
  v589.Buffer = 0;
  v397 = 0;
  ProcessHandle = 0;
  v584 = 0;
  v505 = 0;
  NumberOfBytesToWrite = 0;
  v508 = 0;
  v489 = 0;
  v501 = 0;
  v480 = 0;
  v466 = 0;
  v560 = 0;
  v534 = 0;
  v500 = 0;
  v585 = 0;
  v518 = 0;
  v351 = 0;
  v495 = 0;
  v628 = 0;
  v631 = 0;
  v665 = 0;
  v688 = 0;
  v689 = 0;
  v694 = 0;
  v695 = 0;
  v582 = 0;
  v591 = 0;
  v565 = 0;
  v479 = 0;
  v692 = 0;
  v693 = 0;
  memset_0(v683, 0, 0x58u);
  v586 = 0;
  v587 = 0;
  v588 = 0;
  *(_OWORD *)token = 0;
  v548 = NtCurrentPeb();
  ProcessHeap = v548->ProcessHeap;
  HeapHandle = ProcessHeap;
  memset_0(packageFullName, 0, sizeof(packageFullName));
  v545 = 1;
  v912[0] = 0;
  if ( (v15 & 0x18) == 0x18 )
  {
LABEL_9:
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  if ( (v15 & 0x800) != 0 )
  {
    if ( (v15 & 0x1000) != 0 )
      goto LABEL_9;
  }
  else if ( (v15 & 0x1000) == 0 && *(_BYTE *)(BaseStaticServerData + 2036) )
  {
    v15 |= 0x800u;
    v350 = v15;
  }
  ThreadDebugObject = 0;
  DebugObject = 0;
  if ( (v15 & 0x40) != 0 )
  {
    v21 = 1;
  }
  else if ( (v15 & 0x4000) != 0 )
  {
    v21 = 5;
  }
  else if ( (v15 & 0x20) != 0 )
  {
    v21 = 2;
  }
  else if ( (v15 & 0x8000) != 0 )
  {
    v21 = 6;
  }
  else if ( (v15 & 0x80u) == 0 )
  {
    if ( (v15 & 0x100) != 0 )
    {
      LOBYTE(v19) = a1 != 0;
      v21 = (BasepIsRealtimeAllowed(0, v19) != 0) + 3;
      ThreadDebugObject = DebugObject;
    }
    else
    {
      v21 = 0;
    }
  }
  else
  {
    v21 = 3;
  }
  v394 = v21;
  v350 &= 0xFFFF3E1F;
  if ( (v350 & 0x40000) != 0 )
    v351 |= 0x40u;
  if ( (v350 & 0x1000000) != 0 )
    v351 |= 1u;
  if ( (v350 & 0x10000) != 0 )
    v351 |= 0x100u;
  if ( (v350 & 4) == 0 )
    v351 |= 0x200u;
  if ( (v350 & 3) != 0 )
  {
    v22 = DbgUiConnectToDbg();
    if ( v22 < 0 )
    {
      v16 = (unsigned int)v22;
      goto LABEL_1279;
    }
    ThreadDebugObject = DbgUiGetThreadDebugObject();
    DebugObject = ThreadDebugObject;
    if ( (v350 & 2) != 0 )
      v351 |= 2u;
  }
  v345 = 0;
  v23 = 0;
  v423 = 0;
  v416 = 0;
  v510 = 0;
  v483 = 0;
  v603 = 0;
  Handle = 0;
  v549 = 0;
  P = 0;
  Buffer = 0;
  v537 = 0;
  v608 = 0;
  v398 = 0;
  v359 = 0;
  v396 = 0;
  v577 = 0;
  ExitStatus = 0;
  v637 = 0;
  v561 = 0;
  v503 = 0;
  v488 = 0;
  v352 = 0;
  v604 = ProcessHeap;
  v353 = 0;
  LOBYTE(v516) = 0;
  v414 = 0;
  v419 = 0;
  v576 = 0;
  v499 = 0;
  v356 = 0;
  v355 = 0;
  v579 = 0;
  v550 = 0;
  v562 = 0;
  v517 = 0;
  v522 = 0;
  v478 = 0;
  Src = 0;
  v606 = 0;
  v716 = 131077;
  v719[0] = 0;
  v719[1] = 65539;
  v719[2] = 16;
  v719[4] = 0;
  v719[3] = &v636;
  v719[5] = 6;
  v719[6] = 64;
  v719[8] = 0;
  v719[7] = v666;
  v346 = 3;
  if ( ThreadDebugObject )
  {
    v719[9] = 393217;
    v719[10] = 8;
    v719[12] = 0;
    v719[11] = ThreadDebugObject;
    v346 = 4;
    v24 = 4;
  }
  else
  {
    v24 = 3;
  }
  if ( v394 )
  {
    *(&v716 + 4 * v24) = 131080;
    *(&v717 + 4 * v346) = 1;
    v719[4 * v346] = 0;
    v719[4 * v346 - 1] = &v394;
    v24 = ++v346;
  }
  if ( (v350 & 0x4000000) != 0 )
  {
    v574 = 1;
    *(&v716 + 4 * v24) = 131081;
    *(&v717 + 4 * v346) = 4;
    v719[4 * v346] = 0;
    v719[4 * v346 - 1] = &v574;
    v24 = ++v346;
  }
  if ( (v350 & 0x400000) != 0 )
  {
    *(&v716 + 4 * v24) = 131090;
    *(&v717 + 4 * v346) = 8;
    v719[4 * v346] = 0;
    v719[4 * v346++ - 1] = &v692;
  }
  v25 = v349;
  *(_OWORD *)v349 = 0;
  *(_QWORD *)(v25 + 16) = 0;
  if ( v412 && (v350 & 0x400) == 0 )
  {
    v26 = RtlCreateEnvironmentEx(v412, &v580, 1);
    v348 = v26;
    if ( v26 < 0 )
    {
      BaseSetLastNTError((unsigned int)v26);
      local_unwind_1(v673, &loc_180096E49);
    }
    v412 = v580;
    v350 |= 0x400u;
  }
  v27 = *(__m128i *)v17;
  Buf1 = *(__m128i *)v17;
  v659 = *(_OWORD *)(v17 + 16);
  v660 = *(_OWORD *)(v17 + 32);
  v661 = *(_OWORD *)(v17 + 48);
  v662 = *(_OWORD *)(v17 + 64);
  v663 = *(_OWORD *)(v17 + 80);
  v664 = *(_QWORD *)(v17 + 96);
  if ( (v350 & 0x80000) != 0 )
  {
    if ( _mm_cvtsi128_si32(v27) != 112 )
    {
LABEL_55:
      v28 = 3221225485LL;
LABEL_56:
      BaseSetLastNTError(v28);
      goto LABEL_57;
    }
    v30 = *(_DWORD **)(v17 + 104);
    v483 = v30;
    if ( v30 )
    {
      v344 = 29;
      ExePath = BasepConvertWin32AttributeList(
                  (_DWORD)v30,
                  0,
                  (unsigned int)&v495,
                  (unsigned int)&v491,
                  (__int64)&v506,
                  (__int64)v417,
                  (__int64)&ProcessHandle,
                  (__int64)&v665,
                  (__int64)&v688,
                  (__int64)&v694,
                  (__int64)&v582,
                  (__int64)&v565,
                  (__int64)&v591,
                  (__int64)&v585,
                  (__int64)&v586,
                  (__int64)&v479,
                  (__int64)&v573,
                  (__int64)v675,
                  (__int64)&v674,
                  (__int64)&v650,
                  (__int64)&v692,
                  (__int64)&v351,
                  (__int64)&v715,
                  (__int64)&v346);
      v348 = ExePath;
      if ( ExePath < 0 )
      {
LABEL_60:
        v28 = (unsigned int)ExePath;
        goto LABEL_56;
      }
      if ( (unsigned int)Feature_Win32alacarteSupport_PROC_THREAD_ATTRIBUTE_JOB_LIST__private_IsEnabledDeviceUsageNoInline()
        && v573
        && (unsigned int)ShouldAvoidInlineJobListAssignment(v548) )
      {
        v603 = ExtractJobListAttribute(&v715, &v346, &v638);
        Parameters[3] = v603;
      }
      if ( (*v483 & 0x100) != 0 )
      {
        v353 = 1;
        v530 = 1;
        if ( v506 )
          goto LABEL_55;
      }
      v32 = v503;
      if ( (*v483 & 0x80000) != 0 )
        v32 = 1;
      v503 = v32;
      v612 = v32;
      if ( (v495 & 4) != 0 )
        v351 |= 0x400u;
      if ( (*v483 & 0x20000000) != 0 )
        v350 |= 0x400000u;
    }
  }
  if ( (v350 & 0x800) == 0 )
  {
    v33 = -1;
    if ( ProcessHandle )
      v33 = (__int64)ProcessHandle;
    if ( IsProcessInJob((HANDLE)v33, 0, &Result) && Result )
      v350 = v350 & 0xFFFFE7FF | 0x800;
  }
  if ( (WORD6(v661) & 0x100) != 0 && (WORD6(v661) & 0x600) != 0 )
    HIDWORD(v661) &= ~0x100u;
  v34 = FileName;
  if ( FileName )
  {
    Heap = RtlAllocateHeap(ProcessHeap, 0, 0x206u);
    v537 = Heap;
    if ( !Heap )
    {
LABEL_84:
      v28 = 3221225495LL;
      goto LABEL_56;
    }
    InputPathType = RtlPathTypeUnknown;
    FullPathName_UEx = RtlGetFullPathName_UEx(v34, 0x206u, (PWSTR)Heap, &FilePart, &InputPathType);
    if ( FullPathName_UEx < 0 )
      BaseSetLastNTError((unsigned int)FullPathName_UEx);
    if ( (unsigned int)InputPathType >> 1 >= 0x104 )
    {
LABEL_88:
      v37 = 267;
      goto LABEL_89;
    }
    if ( !((unsigned int)InputPathType >> 1) )
      goto LABEL_57;
    FileName = (PWSTR)Heap;
    v642 = Heap;
  }
  ExePath = BaseFormatObjectAttributes(v677, v497, 0, &v633);
  v348 = ExePath;
  if ( ExePath < 0 )
    goto LABEL_60;
  ExePath = BaseFormatObjectAttributes(v678, v493, 0, &v632);
  v348 = ExePath;
  if ( ExePath < 0 )
    goto LABEL_60;
  v38 = v346;
  v418 = v346;
  v39 = lpFileName;
  v486 = lpFileName;
  v40 = pszSrc;
  v477 = pszSrc;
  v41 = v412;
  v487 = v412;
  v42 = v419;
  while ( 1 )
  {
    v346 = v38;
    if ( !a6 || (v408 = 1, v417[0]) )
      v408 = 0;
    v420 = v535;
    v533 = v535;
    v412 = v41;
    if ( v410 && *(_DWORD *)(v410 + 548) != 1 )
    {
      v43 = *(void **)(v410 + 552);
LABEL_104:
      v420 = v43;
      v533 = v43;
      goto LABEL_107;
    }
    if ( v358 && *(_DWORD *)(v358 + 32) != 1 )
    {
      v43 = *(void **)(v358 + 16);
      goto LABEL_104;
    }
    if ( v42 )
    {
      lpFileName = v39;
      pszSrc = v40;
      v420 = v42;
      v533 = v42;
    }
LABEL_107:
    if ( (unsigned int)Feature_AlwaysUseAppxExtensionForPackagedProcesses__private_IsEnabledDeviceUsageNoInline()
      && v414 )
    {
      lpFileName = v39;
      v44 = v477;
      pszSrc = v477;
    }
    else
    {
      v44 = v477;
    }
    if ( P )
    {
      if ( lpFileName == P )
        lpFileName = v39;
      RtlFreeHeap(ProcessHeap, 0, P);
      P = 0;
    }
    if ( v510 )
    {
      RtlFreeHeap(ProcessHeap, 0, v510);
      v510 = 0;
    }
    RtlFreeUnicodeString(&UnicodeString);
    if ( v577 )
    {
      if ( pszSrc == v577 )
        pszSrc = v44;
      RtlFreeHeap(ProcessHeap, 0, v577);
      v577 = 0;
    }
    if ( Handle )
    {
      NtClose(Handle);
      Handle = 0;
    }
    if ( v504 )
    {
      NtClose(v504);
      v504 = 0;
    }
    if ( Environment )
    {
      RtlDestroyEnvironment(Environment);
      Environment = 0;
    }
    v46 = v421;
    if ( v421 )
    {
      if ( v576 )
      {
        BasepReleaseAppXContext();
        v46 = v421;
      }
      v576 = v46;
      v421 = 0;
    }
    if ( v549 )
    {
      NtClose(v549);
      v549 = 0;
    }
    if ( ThreadHandle[0] )
    {
      if ( DebugObject )
        NtRemoveProcessDebug(Process, DebugObject);
      NtTerminateProcess(Process, -1073741267);
      NtWaitForSingleObject(Process, 0, 0);
      NtClose(ThreadHandle[0]);
      ThreadHandle[0] = 0;
    }
    v47 = Process;
    if ( Process )
    {
      NtClose(Process);
      Process = 0;
    }
    if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v47, v45) )
    {
      BasepFreeAppCompatData(v505, v508, v501);
      v505 = 0;
      NumberOfBytesToWrite = 0;
      v508 = 0;
      v489 = 0;
      v501 = 0;
      v480 = 0;
    }
    if ( (unsigned __int8)IsBasepFreeAppCompatData2Present() )
    {
      BasepFreeAppCompatData2(v584);
      v584 = 0;
    }
    if ( !v411 && (unsigned __int8)IsBasepProcessInvalidImagePresent(v49, v48) )
    {
      BasepReleaseSxsCreateProcessUtilityStruct(v683);
      memset_0(v683, 0, 0x58u);
    }
    if ( CaptureBuffer )
    {
      CsrFreeCaptureBuffer(CaptureBuffer);
      CaptureBuffer = 0;
    }
    BasepFreeBnoIsolationParameter(&v586);
    v50 = 0;
    v468 = 0;
    v51 = 0;
    v471 = 0;
    v513 = 1;
    if ( !lpFileName )
    {
      P = RtlAllocateHeap(ProcessHeap, 0, 0x208u);
      if ( !P )
        goto LABEL_84;
      LastErrorValue = 0;
      v590 = 0;
      v53 = pszSrc;
      lpFileName = pszSrc;
      v54 = pszSrc;
      v423 = pszSrc;
      v554 = pszSrc;
      v55 = pszSrc;
      v581 = pszSrc;
      if ( *pszSrc == 34 )
      {
        v56 = 0;
        v470 = 0;
        v55 = pszSrc + 1;
        v581 = pszSrc + 1;
        lpFileName = pszSrc + 1;
        while ( 1 )
        {
          if ( !*v55 )
            goto LABEL_164;
          if ( *v55 == 34 )
            break;
          v581 = ++v55;
          v54 = v55;
          v423 = v55;
          v554 = v55;
        }
        v554 = v55;
        v513 = 0;
LABEL_163:
        v423 = v55;
        v54 = v55;
        goto LABEL_164;
      }
      v56 = 1;
      v470 = 1;
      while ( 1 )
      {
        lpFileName = v53;
        while ( *v55 )
        {
          if ( *v55 == 32 || *v55 == 9 )
          {
            v554 = v55;
            goto LABEL_163;
          }
          v581 = ++v55;
          v54 = v55;
          v423 = v55;
          v554 = v55;
        }
LABEL_164:
        v416 = *v54;
        v542 = v416;
        *v54 = 0;
        if ( lpPath )
        {
          RtlReleasePath();
          lpPath = 0;
        }
        ExePath = RtlGetExePath(lpFileName, &lpPath);
        v348 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
        v57 = SearchPathW(lpPath, lpFileName, L".exe", 0x104u, (LPWSTR)P, 0);
        ReturnLength = v57;
        if ( v57 )
        {
          if ( v57 >= 0x104 )
          {
            v58 = 3221225734LL;
LABEL_170:
            BaseSetLastNTError(v58);
            goto LABEL_171;
          }
          FileAttributesW = GetFileAttributesW((LPCWSTR)P);
          if ( FileAttributesW != -1 )
          {
            if ( (FileAttributesW & 0x10) == 0 )
            {
              v23 = (wchar_t *)v423;
              *v423 = v416;
              lpFileName = (LPCWSTR)P;
              v60 = pszSrc;
              ProcessHeap = HeapHandle;
              goto LABEL_184;
            }
            v58 = 3221225658LL;
            goto LABEL_170;
          }
        }
LABEL_171:
        if ( !LastErrorValue )
        {
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
          v590 = LastErrorValue;
        }
        *v423 = v416;
        if ( !*v55 || !v56 )
        {
          v37 = LastErrorValue;
          goto LABEL_89;
        }
        v581 = ++v55;
        v54 = v55;
        v423 = v55;
        v554 = v55;
        v50 = 1;
        v468 = 1;
        v513 = 0;
        v53 = pszSrc;
      }
    }
    v60 = pszSrc;
    if ( !pszSrc || !*pszSrc )
    {
      v51 = 1;
      v471 = 1;
      v60 = lpFileName;
      pszSrc = lpFileName;
    }
LABEL_184:
    if ( v50 || v51 )
    {
      v61 = 2 * wcslen(v60) + 6;
      v62 = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, v61);
      v63 = v62;
      v577 = v62;
      if ( v62 )
      {
        StringCbCopyW(v62, v61, L"\"");
        if ( v50 )
        {
          v416 = *v23;
          v542 = v416;
          *v23 = 0;
        }
        StringCbCatW(v63, v61, pszSrc);
        StringCbCatW(v63, v61, L"\"");
        if ( v50 )
        {
          *v23 = v416;
          StringCbCatW(v63, v61, v23);
        }
        pszSrc = v63;
      }
    }
    if ( !RtlDosPathNameToNtPathName_U(lpFileName, &UnicodeString, 0, 0) )
    {
      v37 = 3;
      goto LABEL_89;
    }
    ExePath = RtlInitUnicodeStringEx(&DestinationString, lpFileName);
    v64 = ExePath;
    v348 = ExePath;
    if ( ExePath < 0 )
      goto LABEL_60;
    v65 = RtlDetermineDosPathNameType_U(lpFileName);
    v569 = v65;
    if ( (unsigned int)(v65 - 1) > 1 && (unsigned int)(v65 - 6) > 1
      || !(unsigned int)BasepAdjustApplicationPath(&DestinationString) )
    {
      *(_QWORD *)&DynamicString.Length = 0;
      DynamicString.Buffer = 0;
      ExePath = RtlGetFullPathName_UstrEx(&DestinationString, 0, &DynamicString, 0, 0, 0, &v569, 0);
      v64 = ExePath;
      v348 = ExePath;
      if ( ExePath < 0 )
        goto LABEL_60;
      DestinationString = DynamicString;
      v510 = (PVOID)_mm_srli_si128((__m128i)DynamicString, 8).m128i_u64[0];
      DynamicString.Buffer = 0;
    }
    if ( (v479 & 3) == 3 )
      goto LABEL_55;
    v66 = v548;
    if ( (v548->BitField & 0x10) != 0 && !v358 && !v410 )
    {
      v544 = 720897;
      if ( (int)AppModelPolicy_GetProcessPolicy_ImplicitPackageBreakaway(-6, &v544) >= 0
        && (v544 == 720896 && (v479 & 6) == 0 || v544 == 720898 && (v479 & 5) == 1) )
      {
        if ( (unsigned __int8)IsCheckAppXPackageBreakawayPresent() )
        {
          v64 = CheckAppXPackageBreakaway(DestinationString.Buffer, &v465);
          v348 = v64;
          if ( v64 < 0 )
            v465 = 0;
        }
        else
        {
          v64 = -1073741823;
          v348 = -1073741823;
        }
      }
      if ( v64 < 0 )
        goto LABEL_214;
      v568 = 2424832;
      v652 = 0;
      v653 = 0;
      if ( (int)AppModelPolicy_GetPolicy_Internal(-6, 37, (unsigned int)&v568, (unsigned int)&v653, (__int64)&v652) < 0 )
      {
        v64 = -1073741823;
        v348 = -1073741823;
      }
      else if ( v568 == 2424833 )
      {
        v517 = 1;
        v645 = 1;
      }
      if ( v64 < 0 )
        goto LABEL_214;
    }
    if ( (unsigned int)Feature_EnableRunningHostedAppsWithAEA__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( v358 )
      {
        if ( !*(_DWORD *)(v358 + 32) )
        {
          v68 = *(_WORD **)(v358 + 56);
          if ( v68 )
          {
            if ( *v68 )
            {
              v567 = 4;
              v721 = 131097;
              v722 = 4;
              v724 = 0;
              v723 = (struct _UNICODE_STRING *)&v567;
              BasepAddToOrUpdateAttributesList(v720, 1, &v715, &v346, 29);
            }
          }
        }
      }
    }
    if ( v465 || !v491.Length && ((v66->BitField & 0x10) == 0 || v517) )
      goto LABEL_250;
    if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v68, v67) )
      ExePath = BasepAppXExtension(v420, &v491, v506, v412, &v421, &Environment);
    else
      ExePath = -1073741823;
    v348 = ExePath;
    if ( ExePath < 0 )
    {
      v421 = 0;
      Environment = 0;
      goto LABEL_60;
    }
    IsEnabledDeviceUsageNoInline = Feature_AlwaysUseAppxExtensionForPackagedProcesses__private_IsEnabledDeviceUsageNoInline();
    v70 = (unsigned __int8)v516;
    if ( IsEnabledDeviceUsageNoInline )
      v70 = 1;
    v516 = v70;
    v531 = v70;
    if ( Environment )
      v412 = Environment;
    if ( !v421 )
    {
      *(_QWORD *)&v491.Length = 0;
      v491.Buffer = 0;
LABEL_250:
      v72 = FileName;
      goto LABEL_251;
    }
    RtlInitUnicodeString(&v491, *(PCWSTR *)(v421 + 24));
    v71 = v421;
    if ( *(_QWORD *)v421 )
      v506 = *(_QWORD **)v421;
    if ( !*(_QWORD *)(v421 + 16) || v358 || v410 && *(_BYTE *)(v410 + 544) )
      goto LABEL_250;
    if ( v537 )
    {
      RtlFreeHeap(ProcessHeap, 0, v537);
      v537 = 0;
      v71 = v421;
    }
    v72 = *(WCHAR **)(v71 + 16);
    FileName = v72;
    v642 = v72;
LABEL_251:
    ExePath = GetEmbeddedImageMitigationPolicy(v675, &v688, &v582, &v566);
    v348 = ExePath;
    if ( v566 )
    {
      if ( ExePath < 0 )
        goto LABEL_60;
      v721 = 131088;
      v722 = 24;
      v724 = 0;
      v723 = (struct _UNICODE_STRING *)&v688;
      v73 = 1;
      v485 = 1;
      if ( HIDWORD(v582) )
      {
        v725 = 131094;
        v726 = 8;
        v728 = 0;
        v727 = &v582;
        v73 = 2;
        v485 = 2;
      }
      BasepAddToOrUpdateAttributesList(v720, v73, &v715, &v346, 29);
    }
    if ( v565 )
    {
      v689 &= 0xFFFFFFFFCFFFFFFFuLL;
      v689 |= 0x10000000uLL;
      v485 = 1;
      v721 = 131088;
      v722 = 24;
      v724 = 0;
      v723 = (struct _UNICODE_STRING *)&v688;
      BasepAddToOrUpdateAttributesList(v720, 1, &v715, &v346, 29);
    }
    v74 = v420;
    if ( v506 )
    {
      ExePath = BasepCreateLowBox(v420);
      v348 = ExePath;
      if ( ExePath < 0
        || ((v583 = 0, !(unsigned __int8)IsBasepProcessInvalidImagePresent(v76, v75))
          ? (ExePath = 0)
          : (ExePath = BasepAppContainerEnvironmentExtension(*v506, v412, &v583)),
            v348 = ExePath,
            ExePath < 0) )
      {
        v504 = 0;
        goto LABEL_60;
      }
      if ( v504 )
        v74 = v504;
      v420 = v74;
      v533 = v74;
      v77 = v583;
      if ( v583 )
      {
        if ( Environment )
        {
          RtlDestroyEnvironment(Environment);
          v77 = v583;
        }
        Environment = v77;
        v412 = v77;
      }
    }
    if ( v488 )
    {
      v721 = 131096;
      v722 = 40;
      v724 = 0;
      v723 = &v586;
      BasepAddToOrUpdateAttributesList(v720, 1, &v715, &v346, 29);
      v78 = 1;
      v503 = 1;
      v612 = 1;
    }
    else
    {
      v78 = v503;
    }
    if ( v78 )
    {
      if ( v506 || (NtCurrentPeb()->BitField & 0x20) != 0 )
      {
        v28 = 3221225659LL;
        goto LABEL_56;
      }
      if ( *((_QWORD *)&v587 + 1) )
        goto LABEL_282;
      if ( !(_BYTE)v588 )
      {
        ExePath = 0;
        goto LABEL_283;
      }
      if ( !v586.Buffer )
LABEL_282:
        ExePath = -1073741811;
      else
        ExePath = BasepCreateBnoIsolationObjectDirectories(v74);
LABEL_283:
      v348 = ExePath;
      if ( ExePath < 0 )
        goto LABEL_60;
    }
    if ( v72 )
    {
      v79 = GetFileAttributesW(v72);
      if ( v79 == -1 || (v79 & 0x10) == 0 )
        goto LABEL_88;
    }
    if ( v74 )
    {
      *(&v716 + 4 * v346) = 393218;
      *(&v717 + 4 * v346) = 8;
      v719[4 * v346] = 0;
      v719[4 * v346++ - 1] = v74;
    }
    if ( v421 && (*(_BYTE *)(v421 + 80) & 1) != 0 )
    {
      if ( (unsigned __int8)IsBasepCheckPplSupportPresent() )
      {
        ExePath = BasepCheckPplSupport(DestinationString.Buffer, &v545);
        v348 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
      }
      if ( v545 )
      {
        *(&v716 + 4 * v346) = 393233;
        *(&v717 + 4 * v346) = 1;
        v719[4 * v346] = 0;
        v719[4 * v346++ - 1] = 129;
        v351 |= 0x40u;
      }
    }
    if ( a6 )
      v351 |= 4u;
    else
      v351 &= ~4u;
    memset_0(&v617, 0, 0x58u);
    v617 = 88;
    v80 = v411;
    v81 = v408;
    if ( !v411 )
    {
      if ( !v408 && (WORD6(v661) & 0x100) == 0 && !ProcessHandle && (v350 & 0x8000018) == 0 )
      {
        HIDWORD(v490) = 3;
        LODWORD(v490) = v490 & 0xFFFFFFE0 | 1;
        *(&v716 + 4 * v346) = 131082;
        *(&v717 + 4 * v346) = 8;
        v719[4 * v346] = 0;
        v719[4 * v346++ - 1] = &v490;
        v80 = v411;
      }
      if ( !v80 && !v81 && (WORD6(v661) & 0x100) != 0 && ProcessHandle )
      {
        HIDWORD(v490) = 3;
        LODWORD(v490) = v490 & 0xFFFFFFE0 | 2;
        *(&v716 + 4 * v346) = 131082;
        *(&v717 + 4 * v346) = 8;
        v719[4 * v346] = 0;
        v719[4 * v346++ - 1] = &v490;
      }
    }
    if ( (v350 & 3) == 0 || v548->ReadImageFileExecOptions )
    {
      if ( v396 )
      {
        v396 = 0;
        v472 = 0;
        LOBYTE(KeyHandle) = (unsigned __int8)KeyHandle | 4;
      }
    }
    else
    {
      LOBYTE(KeyHandle) = (unsigned __int8)KeyHandle | 0xC;
    }
    LOBYTE(KeyHandle) = (unsigned __int8)KeyHandle | 1;
    WORD1(KeyHandle) = 0x2000;
    HIDWORD(KeyHandle) = 129;
    if ( !(_QWORD)v659 )
      *(_QWORD *)&v659 = v548->ProcessParameters->DesktopInfo.Buffer;
    if ( !v421 || (v82 = *(_WORD **)(v421 + 24)) == 0 || !*v82 || (*(_BYTE *)(v421 + 80) & 4) != 0 )
      LOBYTE(KeyHandle) = (unsigned __int8)KeyHandle | 2;
    RtlWow64GetProcessMachines(-1, &v543, v425);
    LOWORD(v360) = 48;
    BYTE2(v360) = 18;
    *(_WORD *)((char *)&v360 + 3) = -11264;
    WORD3(v360) = 40;
    BYTE8(v360) = 18;
    *(_DWORD *)((char *)&v360 + 9) = 0;
    *(_WORD *)((char *)&v360 + 13) = 0;
    HIBYTE(v360) = 0;
    *(_QWORD *)&v361 = 0;
    *((_QWORD *)&v361 + 1) = 0x80000000LL;
    LODWORD(v362) = 0x2000000;
    BYTE4(v362) = 108;
    BYTE5(v362) = BYTE5(v362) & 0xF0 | 3;
    *((_QWORD *)&v362 + 1) = 0;
    v83 = 87;
    v409 = 87;
    if ( v425[0] == 0xAA64 )
    {
      if ( !(unsigned __int8)IsBasepFreeAppCompatData2Present()
        || (v83 = BasepQueryModuleChpeSettings2(
                    &v584,
                    DestinationString.Buffer,
                    v635,
                    v412,
                    &v491,
                    &v501,
                    &v480,
                    &v508,
                    &v489,
                    &v534),
            (v409 = v83) != 0) )
      {
LABEL_496:
        if ( (BYTE9(v362) & 0x40) == 0 && (unsigned __int8)IsBasepProcessInvalidImagePresent(v85, v84) )
        {
          v83 = BasepQueryModuleChpeSettings(
                  &v684,
                  32,
                  DestinationString.Buffer,
                  v635,
                  v412,
                  &v491,
                  &v501,
                  &v480,
                  &v508,
                  &v489,
                  &v534);
          v409 = v83;
          if ( v83 )
          {
            *(_QWORD *)&v684 = 0;
            *((_QWORD *)&v684 + 1) = 0x80000000LL;
            LODWORD(v685) = 0x2000000;
            v142 = 108;
            BYTE4(v685) = 108;
            BYTE5(v685) = BYTE5(v685) & 0xF0 | 3;
            *((_QWORD *)&v685 + 1) = 0;
          }
          else
          {
            v142 = BYTE4(v685);
          }
          if ( (BYTE9(v685) & 0x40) != 0 )
          {
            LOWORD(v360) = 48;
            BYTE2(v360) = 18;
            *(_WORD *)((char *)&v360 + 3) = -11264;
            WORD3(v360) = 40;
            BYTE8(v360) = 18;
            *(_DWORD *)((char *)&v360 + 9) = 0;
            *(_WORD *)((char *)&v360 + 13) = 0;
            HIBYTE(v360) = 0;
            *(_QWORD *)&v361 = 0;
            *((_QWORD *)&v361 + 1) = 0x80000000LL;
            LODWORD(v362) = 0x2000000;
            v143 = 2;
            v144 = 108;
            BYTE4(v362) = 108;
            v145 = BYTE5(v362) & 0xF0 | 3;
            BYTE5(v362) = v145;
            *((_QWORD *)&v362 + 1) = 0;
            v146 = 0;
            if ( (BYTE8(v685) & 1) != 0 )
              v146 = v684;
            *(_QWORD *)&v361 = v146;
            BYTE8(v362) = BYTE8(v685) & 1;
            v147 = 0x80000000;
            if ( (BYTE8(v685) & 2) != 0 )
              v147 = DWORD2(v684);
            DWORD2(v361) = v147;
            BYTE8(v362) = BYTE8(v685) & 3;
            v148 = 0;
            if ( (BYTE8(v685) & 4) != 0 )
              v148 = HIDWORD(v684);
            HIDWORD(v361) = v148;
            BYTE8(v362) = BYTE8(v685) & 7;
            v149 = 0;
            if ( (BYTE8(v685) & 8) != 0 )
              v149 = v685;
            LOWORD(v362) = v149;
            BYTE8(v362) = BYTE8(v685) & 0xF;
            v150 = 0;
            if ( (BYTE8(v685) & 0x10) != 0 )
              v150 = BYTE2(v685);
            BYTE2(v362) = v150;
            BYTE8(v362) = BYTE8(v685) & 0x1F;
            if ( (BYTE8(v685) & 0x20) != 0 )
            {
              v143 = BYTE3(v685) & 0xF;
              BYTE3(v362) = BYTE3(v685) & 0xF;
            }
            BYTE8(v362) = BYTE8(v685) & 0x3F;
            if ( (BYTE8(v685) & 0x40) != 0 )
              BYTE3(v362) = v143 & 0xF | BYTE3(v685) & 0xF0;
            BYTE8(v362) = BYTE8(v685) & 0x7F;
            if ( SBYTE8(v685) < 0 )
            {
              v144 = v142 & 3 | 0x6C;
              BYTE4(v362) = v144;
            }
            BYTE8(v362) = BYTE8(v685);
            if ( (BYTE9(v685) & 1) != 0 )
            {
              v144 = v144 & 0xFB | v142 & 4;
              BYTE4(v362) = v144;
            }
            v151 = BYTE9(v685) & 1 | BYTE9(v362) & 0xFE;
            BYTE9(v362) = v151;
            if ( (BYTE9(v685) & 2) != 0 )
            {
              v144 = v144 & 0xF7 | v142 & 8;
              BYTE4(v362) = v144;
            }
            v152 = BYTE9(v685) & 2 | v151 & 0xFD;
            BYTE9(v362) = v152;
            if ( (BYTE9(v685) & 4) != 0 )
            {
              v144 = v144 & 0xEF | v142 & 0x10;
              BYTE4(v362) = v144;
            }
            v153 = BYTE9(v685) & 4 | v152 & 0xFB;
            BYTE9(v362) = v153;
            if ( (BYTE9(v685) & 8) != 0 )
            {
              v144 = v144 & 0xDF | v142 & 0x20;
              BYTE4(v362) = v144;
            }
            v154 = BYTE9(v685) & 8 | v153 & 0xF7;
            BYTE9(v362) = v154;
            if ( (BYTE9(v685) & 0x10) != 0 )
            {
              v144 = v144 & 0xBF | v142 & 0x40;
              BYTE4(v362) = v144;
            }
            v155 = v154 & 0xEF;
            BYTE9(v362) = v155 | BYTE9(v685) & 0x10;
            if ( (BYTE9(v685) & 0x20) != 0 )
              BYTE4(v362) = v144 & 0x7F | v142 & 0x80;
            v156 = v155 & 0xDF | BYTE9(v685) & 0x10 | BYTE9(v685) & 0x20;
            BYTE9(v362) = v156;
            if ( (BYTE9(v685) & 0x40) != 0 )
            {
              v145 = v145 & 0xFE | BYTE5(v685) & 1;
              BYTE5(v362) = v145;
            }
            v157 = v156 & 0xBF;
            BYTE9(v362) = v157 | BYTE9(v685) & 0x40;
            if ( SBYTE9(v685) < 0 )
            {
              v145 = v145 & 0xFD | BYTE5(v685) & 2;
              BYTE5(v362) = v145;
            }
            BYTE9(v362) = v157 & 0x7F | BYTE9(v685) & 0x40 | BYTE9(v685) & 0x80;
            if ( (BYTE10(v685) & 1) != 0 )
            {
              v145 = v145 & 0xFB | BYTE5(v685) & 4;
              BYTE5(v362) = v145;
            }
            v158 = BYTE10(v685) & 1 | BYTE10(v362) & 0xFE;
            BYTE10(v362) = v158;
            if ( (BYTE10(v685) & 2) != 0 )
              BYTE5(v362) = v145 & 0xF7 | BYTE5(v685) & 8;
            BYTE10(v362) = v158 & 0xFD | BYTE10(v685) & 2;
          }
        }
        if ( !v83 && (v534 & 0x800000000LL) != 0 )
        {
          *(_QWORD *)&v688 = v688 & 0xFFFFFCFFFFFFFFFFuLL | 0x20000000000LL;
          v721 = 131088;
          v722 = 24;
          v724 = 0;
          v723 = (struct _UNICODE_STRING *)&v688;
          v485 = 1;
          BasepAddToOrUpdateAttributesList(v720, 1, &v715, &v346, 29);
        }
        v72 = FileName;
        goto LABEL_543;
      }
      v84 = v584;
      v456 = 0;
      v446 = 0x2800D400120030LL;
      v447 = 18;
      v448 = 0;
      v449 = 0;
      v450 = 0;
      v451 = 0;
      v452 = 0x80000000LL;
      v453 = 0;
      v454 = 0;
      v455 = 224258;
      v457 = 0;
      LOWORD(v360) = 48;
      BYTE2(v360) = 18;
      *(_WORD *)((char *)&v360 + 3) = -11264;
      WORD3(v360) = 40;
      BYTE8(v360) = 18;
      *(_DWORD *)((char *)&v360 + 9) = 0;
      *(_WORD *)((char *)&v360 + 13) = 0;
      HIBYTE(v360) = 0;
      *(_QWORD *)&v361 = 0;
      *((_QWORD *)&v361 + 1) = 0x80000000LL;
      LODWORD(v362) = 0x2000000;
      v86 = 2;
      v87 = 108;
      BYTE4(v362) = 108;
      v88 = BYTE5(v362) & 0xF0 | 3;
      BYTE5(v362) = v88;
      *((_QWORD *)&v362 + 1) = 0;
      LOBYTE(v85) = 1;
      if ( *(_BYTE *)(v584 + 2) >> 4 == 1 )
      {
        LOBYTE(v85) = -44;
        if ( !*(_BYTE *)(v584 + 3) )
        {
          if ( *(_BYTE *)(v584 + 8) != 18 || *(_WORD *)v584 != 48 || *(_BYTE *)(v584 + 4) != 0xD4 )
            goto LABEL_495;
          if ( !*(_BYTE *)(v584 + 3) )
            goto LABEL_332;
        }
        if ( *(_BYTE *)(v584 + 8) != 18 )
        {
LABEL_332:
          v89 = *(unsigned __int16 *)(v584 + 6) - 40LL;
          if ( !*(_BYTE *)(v584 + 8) || (v90 = 1, (*(_BYTE *)(*(unsigned __int16 *)(v584 + 6) + v584) & 1) == 0) )
            v90 = 0;
          if ( v90 )
            *(_QWORD *)&v361 = *(_QWORD *)(v584 + 16);
          v91 = *(_BYTE *)(v584 + 8) && (*(_BYTE *)(v89 + v584 + 40) & 1) != 0;
          v92 = v91 | BYTE8(v362) & 0xFE;
          BYTE8(v362) = v92;
          if ( *(_BYTE *)(v584 + 8) < 2u || (v93 = 1, (*(_BYTE *)(v89 + v584 + 40) & 2) == 0) )
            v93 = 0;
          v94 = v93 == 0;
          v95 = 2;
          if ( !v94 )
          {
            DWORD2(v361) = *(_DWORD *)(v584 + 24);
            v95 = 2;
          }
          if ( *(_BYTE *)(v584 + 8) < 2u || (*(_BYTE *)(v89 + v584 + 40) & 2) == 0 )
            v95 = 0;
          v96 = v95 | v92 & 0xFD;
          BYTE8(v362) = v96;
          if ( *(_BYTE *)(v584 + 8) < 3u || (v97 = 1, (*(_BYTE *)(v89 + v584 + 40) & 4) == 0) )
            v97 = 0;
          if ( v97 )
            HIDWORD(v361) = *(_DWORD *)(v584 + 28);
          if ( *(_BYTE *)(v584 + 8) >= 3u && (*(_BYTE *)(v89 + v584 + 40) & 4) != 0 )
            v98 = 4;
          else
            v98 = 0;
          v99 = v98 | v96 & 0xFB;
          BYTE8(v362) = v99;
          if ( *(_BYTE *)(v584 + 8) < 4u || (v100 = 1, (*(_BYTE *)(v89 + v584 + 40) & 8) == 0) )
            v100 = 0;
          if ( v100 )
            LOWORD(v362) = *(_WORD *)(v584 + 32);
          if ( *(_BYTE *)(v584 + 8) >= 4u && (*(_BYTE *)(v89 + v584 + 40) & 8) != 0 )
            v101 = 8;
          else
            v101 = 0;
          v102 = v101 | v99 & 0xF7;
          BYTE8(v362) = v102;
          if ( *(_BYTE *)(v584 + 8) < 5u || (v103 = 1, (*(_BYTE *)(v89 + v584 + 40) & 0x10) == 0) )
            v103 = 0;
          if ( v103 )
            BYTE2(v362) = *(_BYTE *)(v584 + 34);
          if ( *(_BYTE *)(v584 + 8) >= 5u && (*(_BYTE *)(v89 + v584 + 40) & 0x10) != 0 )
            v104 = 16;
          else
            v104 = 0;
          v105 = v104 | v102 & 0xEF;
          BYTE8(v362) = v105;
          if ( *(_BYTE *)(v584 + 8) < 6u || (v106 = 1, (*(_BYTE *)(v89 + v584 + 40) & 0x20) == 0) )
            v106 = 0;
          if ( v106 )
          {
            v86 = *(_BYTE *)(v584 + 35) & 0xF;
            BYTE3(v362) = v86;
          }
          if ( *(_BYTE *)(v584 + 8) >= 6u && (*(_BYTE *)(v89 + v584 + 40) & 0x20) != 0 )
            v107 = 32;
          else
            v107 = 0;
          v108 = v107 | v105 & 0xDF;
          BYTE8(v362) = v108;
          if ( *(_BYTE *)(v584 + 8) < 7u || (v109 = 1, (*(_BYTE *)(v89 + v584 + 40) & 0x40) == 0) )
            v109 = 0;
          if ( v109 )
            BYTE3(v362) = v86 & 0xF | (16 * (*(_BYTE *)(v584 + 35) >> 4));
          if ( *(_BYTE *)(v584 + 8) >= 7u && (*(_BYTE *)(v89 + v584 + 40) & 0x40) != 0 )
            v110 = 64;
          else
            v110 = 0;
          v111 = v110 | v108 & 0xBF;
          BYTE8(v362) = v111;
          if ( *(_BYTE *)(v584 + 8) < 8u || (v112 = 1, *(char *)(v89 + v584 + 40) >= 0) )
            v112 = 0;
          if ( v112 )
          {
            v87 = *(_BYTE *)(v584 + 36) & 3 | 0x6C;
            BYTE4(v362) = v87;
          }
          if ( *(_BYTE *)(v584 + 8) < 8u || *(char *)(v89 + v584 + 40) >= 0 )
            v113 = 0;
          else
            v113 = 0x80;
          BYTE8(v362) = v113 | v111 & 0x7F;
          if ( *(_BYTE *)(v584 + 8) < 9u || (v114 = 1, (*(_BYTE *)(v89 + v584 + 41) & 1) == 0) )
            v114 = 0;
          if ( v114 )
          {
            v87 = v87 & 0xFB | (4 * ((*(_BYTE *)(v584 + 36) & 4) != 0));
            BYTE4(v362) = v87;
          }
          v115 = *(_BYTE *)(v584 + 8) >= 9u && (*(_BYTE *)(v89 + v584 + 41) & 1) != 0;
          v116 = v115 | BYTE9(v362) & 0xFE;
          BYTE9(v362) = v116;
          if ( *(_BYTE *)(v584 + 8) < 0xAu || (v117 = 1, (*(_BYTE *)(v89 + v584 + 41) & 2) == 0) )
            v117 = 0;
          if ( v117 )
          {
            v87 = v87 & 0xF7 | (8 * ((*(_BYTE *)(v584 + 36) & 8) != 0));
            BYTE4(v362) = v87;
          }
          if ( *(_BYTE *)(v584 + 8) >= 0xAu && (*(_BYTE *)(v89 + v584 + 41) & 2) != 0 )
            v118 = 2;
          else
            v118 = 0;
          v119 = v118 | v116 & 0xFD;
          BYTE9(v362) = v119;
          if ( *(_BYTE *)(v584 + 8) < 0xBu || (v120 = 1, (*(_BYTE *)(v89 + v584 + 41) & 4) == 0) )
            v120 = 0;
          if ( v120 )
          {
            v87 = v87 & 0xEF | (16 * ((*(_BYTE *)(v584 + 36) & 0x10) != 0));
            BYTE4(v362) = v87;
          }
          if ( *(_BYTE *)(v584 + 8) >= 0xBu && (*(_BYTE *)(v89 + v584 + 41) & 4) != 0 )
            v121 = 4;
          else
            v121 = 0;
          v122 = v121 | v119 & 0xFB;
          BYTE9(v362) = v122;
          if ( *(_BYTE *)(v584 + 8) < 0xCu || (v123 = 1, (*(_BYTE *)(v89 + v584 + 41) & 8) == 0) )
            v123 = 0;
          if ( v123 )
          {
            v87 = v87 & 0xDF | (32 * ((*(_BYTE *)(v584 + 36) & 0x20) != 0));
            BYTE4(v362) = v87;
          }
          if ( *(_BYTE *)(v584 + 8) >= 0xCu && (*(_BYTE *)(v89 + v584 + 41) & 8) != 0 )
            v124 = 8;
          else
            v124 = 0;
          v125 = v124 | v122 & 0xF7;
          BYTE9(v362) = v125;
          if ( *(_BYTE *)(v584 + 8) < 0xDu || (v126 = 1, (*(_BYTE *)(v89 + v584 + 41) & 0x10) == 0) )
            v126 = 0;
          if ( v126 )
          {
            v87 = v87 & 0xBF | (((*(_BYTE *)(v584 + 36) & 0x40) != 0) << 6);
            BYTE4(v362) = v87;
          }
          if ( *(_BYTE *)(v584 + 8) >= 0xDu && (*(_BYTE *)(v89 + v584 + 41) & 0x10) != 0 )
            v127 = 16;
          else
            v127 = 0;
          v128 = v127 | v125 & 0xEF;
          BYTE9(v362) = v128;
          if ( *(_BYTE *)(v584 + 8) < 0xEu || (v129 = 1, (*(_BYTE *)(v89 + v584 + 41) & 0x20) == 0) )
            v129 = 0;
          if ( v129 )
            BYTE4(v362) = v87 & 0x7F | (*(_BYTE *)(v584 + 36) >> 7 << 7);
          if ( *(_BYTE *)(v584 + 8) >= 0xEu && (*(_BYTE *)(v89 + v584 + 41) & 0x20) != 0 )
            v130 = 32;
          else
            v130 = 0;
          v131 = v130 | v128 & 0xDF;
          BYTE9(v362) = v131;
          if ( *(_BYTE *)(v584 + 8) < 0xFu || (v132 = 1, (*(_BYTE *)(v89 + v584 + 41) & 0x40) == 0) )
            v132 = 0;
          if ( v132 )
          {
            v88 = *(_BYTE *)(v584 + 37) & 1 | v88 & 0xFE;
            BYTE5(v362) = v88;
          }
          if ( *(_BYTE *)(v584 + 8) >= 0xFu && (*(_BYTE *)(v89 + v584 + 41) & 0x40) != 0 )
            v133 = 64;
          else
            v133 = 0;
          v134 = v133 | v131 & 0xBF;
          BYTE9(v362) = v134;
          if ( *(_BYTE *)(v584 + 8) < 0x10u || (v135 = 1, *(char *)(v89 + v584 + 41) >= 0) )
            v135 = 0;
          if ( v135 )
          {
            v88 = v88 & 0xFD | (2 * ((*(_BYTE *)(v584 + 37) & 2) != 0));
            BYTE5(v362) = v88;
          }
          if ( *(_BYTE *)(v584 + 8) < 0x10u || *(char *)(v89 + v584 + 41) >= 0 )
            v136 = 0;
          else
            v136 = 0x80;
          BYTE9(v362) = v136 | v134 & 0x7F;
          v85 = 0;
          if ( *(_BYTE *)(v584 + 8) < 0x11u || (v137 = 1, (*(_BYTE *)(v89 + v584 + 42) & 1) == 0) )
            v137 = 0;
          if ( v137 )
          {
            v85 = (*(unsigned __int8 *)(v584 + 37) >> 2) & 1;
            v88 = v88 & 0xFB | (4 * ((*(_BYTE *)(v584 + 37) & 4) != 0));
            BYTE5(v362) = v88;
          }
          v138 = *(_BYTE *)(v584 + 8) >= 0x11u && (*(_BYTE *)(v89 + v584 + 42) & 1) != 0;
          v139 = v138 | BYTE10(v362) & 0xFE;
          BYTE10(v362) = v139;
          if ( *(_BYTE *)(v584 + 8) < 0x12u || (v140 = 1, (*(_BYTE *)(v89 + v584 + 42) & 2) == 0) )
            v140 = 0;
          if ( v140 )
            BYTE5(v362) = v88 & 0xF7 | (8 * ((*(_BYTE *)(v584 + 37) & 8) != 0));
          if ( *(_BYTE *)(v584 + 8) >= 0x12u && (*(_BYTE *)(v89 + v584 + 42) & 2) != 0 )
            v141 = 2;
          else
            v141 = 0;
          LOBYTE(v85) = v141 | v139 & 0xFD;
          BYTE10(v362) = v85;
        }
      }
LABEL_495:
      v83 = v409;
      goto LABEL_496;
    }
LABEL_543:
    if ( v421 )
      v159 = *(_QWORD *)(v421 + 88);
    else
      v159 = 0;
    if ( v421 )
      v160 = *(_QWORD *)(v421 + 8);
    else
      v160 = 0;
    LODWORD(v343) = v408;
    LODWORD(v342) = v350;
    LOBYTE(PathType) = v491.Length != 0;
    v161 = (struct _RTL_USER_PROCESS_PARAMETERS *)BasepCreateProcessParameters(
                                                    lpFileName,
                                                    &DestinationString,
                                                    v72,
                                                    pszSrc,
                                                    v160,
                                                    v159,
                                                    PathType,
                                                    v412,
                                                    &Buf1,
                                                    v342,
                                                    v343,
                                                    v351 | (v465 != 0 ? 0x10000 : 0),
                                                    &v665,
                                                    ProcessHandle);
    if ( !v161 )
      goto LABEL_57;
    if ( v421 && (*(_BYTE *)(v421 + 80) & 2) != 0 )
      v161->Flags |= 0x8000000u;
    if ( v358 || v410 && *(_BYTE *)(v410 + 544) )
    {
      ProcessHeap = HeapHandle;
      if ( !FileName )
      {
        Length = v161->CurrentDirectory.DosPath.Length;
        v163 = RtlAllocateHeap(HeapHandle, 0, Length + 2);
        v537 = v163;
        if ( !v163 )
          goto LABEL_84;
        StringCbCopyW((STRSAFE_LPWSTR)v163, Length + 2, v161->CurrentDirectory.DosPath.Buffer);
        FileName = (PWSTR)v537;
        v642 = v537;
      }
    }
    else
    {
      ProcessHeap = HeapHandle;
    }
    *(&v716 + 4 * v346) = 393242;
    *(&v717 + 4 * v346) = 1;
    v719[4 * v346] = 0;
    v164 = QueryChpeConfiguration(&UnicodeString, BYTE5(v362) & 1);
    v719[4 * v346++ - 1] = v164;
    v718 = UnicodeString.Buffer;
    v717 = UnicodeString.Length;
    v715 = 32LL * v346 + 8;
    if ( !v410 || *(_DWORD *)(v410 + 548) == 1 )
    {
      if ( v358 && *(_DWORD *)(v358 + 32) != 1 )
      {
        if ( NtCurrentTeb()->IsImpersonating )
        {
          ExePath = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
          if ( ExePath < 0 )
            goto LABEL_60;
        }
        if ( !ImpersonateLoggedOnUser(*(HANDLE *)(v358 + 16)) )
        {
LABEL_565:
          v165 = TokenHandle;
          if ( !TokenHandle )
            goto LABEL_57;
          goto LABEL_566;
        }
        v499 = 1;
        v564 = 1;
      }
    }
    else
    {
      if ( NtCurrentTeb()->IsImpersonating )
      {
        ExePath = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
        if ( ExePath < 0 )
          goto LABEL_60;
      }
      if ( !ImpersonateLoggedOnUser(*(HANDLE *)(v410 + 552)) )
        goto LABEL_565;
      v499 = 1;
      v564 = 1;
    }
    v166 = v351;
    if ( (v351 & 0x80000) != 0 )
    {
      v161->Flags |= 0x2000000u;
      v166 = v351;
    }
    v64 = NtCreateUserProcess(&Process, ThreadHandle, 0x2000000, 0x2000000, v633, v632, v166, 1, v161, &v617, &v715);
    v348 = v64;
    if ( v499 == 1 )
    {
      v499 = 0;
      v564 = 0;
      if ( TokenHandle )
      {
        v167 = ImpersonateLoggedOnUser(TokenHandle);
        v165 = TokenHandle;
        if ( !v167 )
          goto LABEL_566;
        NtClose(TokenHandle);
      }
      else
      {
        RevertToSelf();
      }
    }
    RtlDestroyProcessParameters(v161);
    if ( v64 >= 0 )
      goto LABEL_705;
    Process = 0;
    ThreadHandle[0] = 0;
    if ( !v618 )
      goto LABEL_214;
    if ( v618 == 1 )
    {
      if ( !v562 && (unsigned __int8)IsBasepGetPackagedAppInfoForFilePresent() )
      {
        v185 = (unsigned int)Feature_UseAEAForUnsupportedPackagedCreateProcessScenario__private_IsEnabledDeviceUsageNoInline()
            && v64 == -1073741191
             ? -1073283070
             : BasepGetPackagedAppInfoForFile(lpFileName, v420, 1, &v410);
        v562 = 1;
        v646 = 1;
        if ( v185 >= 0 )
        {
          if ( v410 )
          {
            lpFileName = *(LPCWSTR *)(v410 + 520);
            if ( *(_DWORD *)(v410 + 548) == 1 )
            {
              v186 = (const wchar_t *)(v410 + 2);
              if ( *(_BYTE *)(v410 + 544) )
              {
                v187 = wcslen(v186);
                v188 = (int)(2 * (v187 + wcslen(pszSrc)) + 4);
                v189 = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, v188);
                v190 = v189;
                v550 = v189;
                if ( !v189 )
                  goto LABEL_680;
                StringCbCopyW(v189, v188, (STRSAFE_LPCWSTR)(v410 + 2));
                v191 = L" ";
              }
              else
              {
                v192 = wcslen(v186);
                v193 = wcslen(L" PackagedDataInfo: ") + v192;
                v188 = (int)(2 * (v193 + wcslen(pszSrc)) + 2);
                v194 = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, v188);
                v190 = v194;
                v550 = v194;
                if ( !v194 )
                  goto LABEL_680;
                StringCbCopyW(v194, v188, (STRSAFE_LPCWSTR)(v410 + 2));
                v191 = L" PackagedDataInfo: ";
              }
              StringCbCatW(v190, v188, v191);
              StringCbCatW(v190, v188, pszSrc);
            }
            else
            {
              v533 = *(HANDLE *)(v410 + 552);
              RtlInitUnicodeString(&v491, (PCWSTR)(v410 + 262));
              v465 = 0;
              v195 = (int)(2 * wcslen(pszSrc) + 2);
              v196 = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, v195);
              v190 = v196;
              v550 = v196;
              if ( !v196 )
                goto LABEL_680;
              StringCbCopyExW(v196, v195, pszSrc, 0, 0, 0x900u);
            }
            pszSrc = v190;
            goto LABEL_680;
          }
        }
      }
      if ( v358 || v64 != -1073741191 && v64 != -1073741790 )
        goto LABEL_703;
      AppExecutionAliasInfoForExecutable = -1073741822;
      v514 = -1073741822;
      if ( v64 == -1073741790 )
      {
        AppExecutionAliasInfoForExecutable = LoadAppExecutionAliasInfoForExecutable(0, (__int64)&v358);
        v514 = AppExecutionAliasInfoForExecutable;
        if ( AppExecutionAliasInfoForExecutable >= 0 && v358 )
        {
          v198 = ValidateAppXAliasFallback(DestinationString.Buffer);
          goto LABEL_691;
        }
      }
      else if ( (unsigned __int8)IsLoadAppExecutionAliasInfoExPresent() )
      {
        v198 = LoadAppExecutionAliasInfoEx(DestinationString.Buffer, v535, &v358);
LABEL_691:
        v514 = v198;
        AppExecutionAliasInfoForExecutable = v198;
      }
      if ( AppExecutionAliasInfoForExecutable < 0 || !v358 )
      {
        if ( AppExecutionAliasInfoForExecutable == -1073267456 )
          v64 = -1073267456;
        v348 = v64;
LABEL_703:
        if ( !RtlIsDosDeviceName_U(lpFileName) )
        {
LABEL_214:
          v28 = (unsigned int)v64;
          goto LABEL_56;
        }
        v37 = 1200;
LABEL_89:
        RtlSetLastWin32Error(v37);
        goto LABEL_57;
      }
      lpFileName = *(LPCWSTR *)(v358 + 8);
      v533 = *(HANDLE *)(v358 + 16);
      v199 = (void *)BuildAppExecutionAliasCommandLine(pszSrc);
      v579 = v199;
      if ( v199 )
        pszSrc = (STRSAFE_LPCWSTR)v199;
      if ( *(_DWORD *)(v358 + 32) != 1 )
      {
        RtlInitUnicodeString(&v491, *(PCWSTR *)v358);
        v465 = 0;
      }
      if ( *(_QWORD *)(v358 + 48) )
      {
        BasepFreeBnoIsolationParameter(&v586);
        RtlInitUnicodeString(&v586, *(PCWSTR *)(v358 + 48));
        LOBYTE(v588) = 1;
        v488 = 1;
        v515 = 1;
      }
      goto LABEL_680;
    }
    v170 = (unsigned int)(v618 - 2);
    if ( v618 == 2 )
    {
      Handle = KeyHandle;
      if ( v64 == -1073741790 )
      {
        v37 = 5;
        goto LABEL_89;
      }
      if ( v359 )
        goto LABEL_214;
      if ( v64 == -1073741521 && UnicodeString.Length >= 8u )
      {
        v176 = &UnicodeString.Buffer[(unsigned __int64)UnicodeString.Length >> 1];
        if ( !_wcsnicmp(v176 - 4, L".bat", 4u) || !_wcsnicmp(v176 - 4, L".cmd", 4u) )
        {
          v398 = 1;
          v538 = 1;
          v177 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x20Eu);
          v178 = v177;
          v608 = v177;
          if ( !v177 )
            goto LABEL_84;
          EnvironmentVariableW = GetEnvironmentVariableW(L"ComSpec", v177, 0x104u);
          if ( EnvironmentVariableW >= 0x104 )
          {
            v28 = 3221225487LL;
            goto LABEL_56;
          }
          if ( !EnvironmentVariableW )
          {
            if ( GetEnvironmentVariableW(L"SystemRoot", v178, 0xF3u) - 1 > 0xF1 )
            {
              v28 = 3221225731LL;
              goto LABEL_56;
            }
            RtlStringCchCatW(v178, 260, L"\\system32\\cmd.exe");
          }
          RtlStringCchCatW(v178, 263, L" /c");
          if ( !(unsigned int)BuildSubSysCommandLine(v513, v178, 0, pszSrc, &v589) )
            goto LABEL_57;
          pszSrc = v589.Buffer;
          lpFileName = 0;
          goto LABEL_630;
        }
      }
      if ( (v350 & 0x2000000) != 0 )
        goto LABEL_647;
      v180 = 1;
      v462 = 1;
      if ( v64 != -1073741541 )
      {
        if ( v64 == -1073741521 )
        {
          if ( !(unsigned __int8)IsBasepProcessInvalidImagePresent(v170, v168)
            || !(unsigned int)BaseIsDosApplication(&UnicodeString, 3221225775LL) )
          {
LABEL_640:
            v180 = 0;
            v462 = 0;
          }
        }
        else if ( (unsigned int)(v64 + 1073741520) > 1 && v64 != -1073741209 )
        {
          goto LABEL_640;
        }
      }
      if ( !v180 )
      {
LABEL_647:
        v182 = v420;
      }
      else
      {
        v181 = IsBasepProcessInvalidImagePresent(v170, v168);
        v182 = v420;
        if ( v181 )
          ExePath = BasepCheckWinSaferRestrictions(v420, lpFileName, Handle, &v491);
        else
          ExePath = 0;
        if ( ExePath < 0 )
          goto LABEL_60;
      }
      if ( v64 == -1073741519 )
      {
        if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v170, v168) )
        {
          ProcessInternalW = NtVdm64CreateProcessInternalW(
                               v182,
                               lpFileName,
                               pszSrc,
                               v497,
                               v493,
                               a6,
                               v350,
                               v412,
                               FileName,
                               v634,
                               v349,
                               0);
          v345 = ProcessInternalW;
        }
        else
        {
          ProcessInternalW = 0;
          v345 = 0;
        }
        if ( !ProcessInternalW
          && NtCurrentTeb()->LastErrorValue == 216
          && (unsigned __int8)IsBasepProcessInvalidImagePresent(v184, v183) )
        {
          RaiseInvalid16BitExeError(&UnicodeString);
        }
        goto LABEL_1173;
      }
      if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v170, v168) )
      {
        ProcessInternalW = BasepProcessInvalidImage(
                             (unsigned int)v64,
                             v182,
                             DestinationString.Buffer,
                             &lpFileName,
                             &pszSrc,
                             FileName,
                             &v350,
                             &a6,
                             &UnicodeString,
                             &v397,
                             &v412,
                             &Buf1,
                             ApiMessage,
                             &NumberOfBytesToWrite_4,
                             &v589,
                             &v627,
                             &v630,
                             &v407,
                             &v411,
                             &v602,
                             &v498);
        v345 = ProcessInternalW;
      }
      else
      {
        ProcessInternalW = 0;
        v345 = 0;
      }
      if ( !ProcessInternalW )
        goto LABEL_1173;
      if ( v498 )
        goto LABEL_1160;
LABEL_630:
      v359 = 1;
      v464[1] = 1;
      goto LABEL_680;
    }
    if ( v618 == 3 )
      goto LABEL_614;
    v169 = (unsigned int)(v618 - 4);
    if ( v618 == 4 )
    {
      if ( v425[0] != 0xAA64 )
      {
        Response = 6;
        Parameters[0] = (unsigned __int64)&UnicodeString;
        NtRaiseHardError(1073741859, 1u, 1u, Parameters, 1u, &Response);
      }
      v37 = 193;
      if ( v548->ImageSubsystemMajorVersion > 3 )
        v37 = 216;
      goto LABEL_89;
    }
    if ( v618 == 5 )
    {
      v171 = KeyHandle;
      v172 = Buffer;
      if ( !Buffer )
      {
        v172 = RtlAllocateHeap(ProcessHeap, 0, 0x20Au);
        Buffer = v172;
        if ( !v172 )
        {
          NtClose(v171);
          v37 = 8;
          goto LABEL_89;
        }
      }
      v348 = LdrQueryImageFileKeyOption(v171, L"Debugger", 1u, v172, 0x208u, &ReturnedLength);
      if ( v348 >= 0 )
      {
        if ( v421 )
          ReturnedLength = 0;
        if ( ReturnedLength >= 2 && *v172 )
        {
          NtClose(v171);
          v172[260] = 0;
          if ( !(unsigned int)BuildSubSysCommandLine(3, v172, 0, pszSrc, &v589) )
            goto LABEL_57;
          pszSrc = v589.Buffer;
          lpFileName = 0;
          goto LABEL_680;
        }
      }
      RtlFreeHeap(ProcessHeap, 0, v172);
      Buffer = 0;
      if ( !v358 )
      {
        v173 = LoadAppExecutionAliasInfoForExecutable(v171, (__int64)&v358);
        v348 = v173;
        if ( v173 >= 0 && v358 )
        {
          lpFileName = *(LPCWSTR *)(v358 + 8);
          v533 = *(HANDLE *)(v358 + 16);
          v174 = (void *)BuildAppExecutionAliasCommandLine(pszSrc);
          v579 = v174;
          if ( v174 )
            pszSrc = (STRSAFE_LPCWSTR)v174;
          v175 = v358;
          if ( *(_DWORD *)(v358 + 32) != 1 )
          {
            RtlInitUnicodeString(&v491, *(PCWSTR *)v358);
            v465 = 0;
            v175 = v358;
          }
          if ( *(_QWORD *)(v175 + 48) )
          {
            BasepFreeBnoIsolationParameter(&v586);
            RtlInitUnicodeString(&v586, *(PCWSTR *)(v358 + 48));
            LOBYTE(v588) = 1;
            v488 = 1;
            v515 = 1;
          }
          goto LABEL_607;
        }
        if ( v173 != -1073267456 )
          goto LABEL_607;
        v165 = v171;
LABEL_566:
        NtClose(v165);
        goto LABEL_57;
      }
LABEL_607:
      NtClose(v171);
      v396 = 1;
      v472 = 1;
LABEL_680:
      v42 = v419;
      goto LABEL_681;
    }
LABEL_705:
    v200 = v620;
    Handle = v620;
    v549 = v621;
    if ( (unsigned int)(v667 - 2) > 1 )
    {
      v37 = 129;
      goto LABEL_89;
    }
    v201 = 10;
    if ( v669 < 3u || (v168 = v668, v669 == 3) && v668 < 0xAu )
    {
      v202 = 0;
    }
    else
    {
      v169 = MEMORY[0x7FFE026C];
      if ( (unsigned int)v669 > MEMORY[0x7FFE026C]
        || v669 == MEMORY[0x7FFE026C] && (unsigned int)v668 > MEMORY[0x7FFE0270] )
      {
LABEL_614:
        v37 = 193;
        goto LABEL_89;
      }
      v202 = 1;
    }
    if ( !v202 )
      goto LABEL_614;
    if ( ((unsigned __int8)KeyHandle & 8) != 0 )
    {
      v637 = v625;
      Parameters[2] = v625;
      v561 = v626;
      v647 = v626;
    }
    if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v169, v168) )
      v205 = BasepCheckWebBladeHashes(v200);
    else
      v205 = 0;
    if ( v205 == -1073741790 )
    {
      v37 = 1277;
      goto LABEL_89;
    }
    if ( v205 < 0 )
    {
      v37 = 1278;
      goto LABEL_89;
    }
    if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v204, v203) )
      ExePath = BasepIsProcessAllowed(lpFileName);
    else
      ExePath = 0;
    v348 = ExePath;
    if ( ExePath < 0 )
      goto LABEL_60;
    if ( !v397 && (v350 & 0x800) != 0 )
      v350 &= ~0x800u;
    if ( v411 )
    {
      v498 = Process;
      if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v207, v206) )
      {
        ProcessInternalW = BaseUpdateVDMEntry(1, &v498, NumberOfBytesToWrite_4, v411);
        v345 = ProcessInternalW;
      }
      else
      {
        ProcessInternalW = 0;
        v345 = 0;
      }
      if ( !ProcessInternalW )
      {
        v498 = 0;
        goto LABEL_1173;
      }
      v407 |= 2u;
      v200 = Handle;
    }
    v208 = v623;
    v640 = v623;
    if ( v359 || (v350 & 0x2000000) != 0 )
    {
      v210 = v420;
    }
    else
    {
      v209 = IsBasepProcessInvalidImagePresent(v207, v206);
      v210 = v420;
      if ( v209 )
        ExePath = BasepCheckWinSaferRestrictions(v420, lpFileName, v200, &v491);
      else
        ExePath = 0;
      if ( ExePath < 0 )
        goto LABEL_60;
    }
    memset_0(v705, 0, 0x1C8u);
    v211 = v671;
    v212 = (unsigned int)v671 - 332;
    if ( v671 == 332 )
    {
      if ( ((unsigned __int8)KeyHandle & 2) != 0 )
        LOWORD(v201) = MEMORY[0x7FFE026A];
    }
    else
    {
      v212 = (unsigned int)v671 - 452;
      if ( v671 == 452 )
      {
        v201 = 5;
      }
      else
      {
        v212 = (unsigned int)v671 - 14948;
        if ( v671 != 14948 )
        {
          v212 = (unsigned int)v671 - 34404;
          if ( v671 == 34404 )
          {
            v201 = 9;
          }
          else if ( v671 == 43620 )
          {
            v201 = 12;
          }
          else
          {
            DbgPrint_0("Kernel32: No mapping for ImageInformation.Machine == %04x\n", v671);
            v201 = 0xFFFF;
          }
        }
      }
    }
    v408 = v201;
    if ( (v350 & 0x400000) != 0 )
      goto LABEL_1158;
    if ( ((unsigned __int8)KeyHandle & 0x10) != 0 && v421 )
    {
      v348 = NtQueryInformationProcess(
               Process,
               ProcessAffinityUpdateMode|ProcessUserModeIOPL,
               &ProcessInformation,
               1u,
               0);
      if ( v348 < 0 )
      {
        v348 = 0;
      }
      else if ( ProcessInformation == -127 )
      {
        v213 = 1;
        v352 = 1;
        v539 = 1;
        goto LABEL_766;
      }
    }
    v213 = v352;
LABEL_766:
    v424[0] = 0;
    if ( ((unsigned __int8)KeyHandle & 1) == 0 || v213 )
    {
      if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v212, v211) )
      {
        BasepQueryAppCompat(
          v666,
          ((unsigned __int8)KeyHandle >> 1) & 1,
          (unsigned __int16)v201,
          v200,
          Process,
          DestinationString.Buffer,
          v412,
          &v491,
          &v501,
          &v480,
          &v508,
          &v489,
          &v560,
          &v534,
          &v500,
          v424,
          &v585,
          &v518);
        v212 = 0x80000;
        if ( (v351 & 0x80000) == 0 && (v534 & 0x1000000000LL) != 0 )
        {
          v351 |= 0x80000u;
LABEL_772:
          ProcessHeap = HeapHandle;
          goto LABEL_680;
        }
      }
    }
    if ( ((unsigned __int8)KeyHandle & 1) == 0 || ((unsigned __int8)KeyHandle & 0x10) != 0 )
    {
      v496 = v622;
      v706 = v622;
      v708[0] = 0;
      v710 = 0;
      if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v212, v211) )
      {
        v214 = !v421 || (*(_BYTE *)(v421 + 80) & 4) != 0 ? 0LL : *(_QWORD *)(v421 + 16);
        LODWORD(v343) = (v670 >> 9) & 1;
        LODWORD(v342) = v489;
        LODWORD(LengthNeeded) = v560;
        LODWORD(PathType) = ((unsigned __int8)KeyHandle >> 2) & 1;
        ExePath = BasepConstructSxsCreateProcessMessage(
                    &UnicodeString,
                    &DestinationString,
                    v200,
                    Process,
                    v549,
                    v210,
                    PathType,
                    LengthNeeded,
                    v508,
                    v342,
                    v343,
                    v214,
                    v208,
                    v637,
                    v561,
                    &v496,
                    v705,
                    v683);
      }
      else
      {
        ExePath = 0;
      }
      v348 = ExePath;
      if ( ExePath < 0 )
        goto LABEL_60;
    }
    v713 = v624;
    v712 = v623;
    v698 = (unsigned __int64)Process;
    v699 = (unsigned __int64)ThreadHandle[0];
    v700 = _mm_loadu_si128(&v636);
    v714 = v201;
    v701 = v350 & 0xFFFFFFFC;
    if ( v667 == 2 || v397 )
    {
      v698 = (unsigned __int64)Process | 2;
      ModuleHandleA = GetModuleHandleA(0);
      v216 = RtlImageNtHeader(ModuleHandleA);
      if ( v216 )
      {
        if ( v216->OptionalHeader.Subsystem == 2 )
          v698 |= 1u;
      }
    }
    v217 = v420;
    if ( v420 )
    {
      TokenInformation = 0;
      ExePath = NtQueryInformationToken(v420, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
      v348 = ExePath;
      if ( ExePath < 0 )
        goto LABEL_60;
      if ( TokenInformation != NtCurrentPeb()->SessionId )
        v699 |= 1u;
    }
    if ( (BYTE12(v661) & 0x40) != 0 )
      v698 |= 1u;
    if ( SBYTE12(v661) < 0 )
      v698 &= ~1uLL;
    if ( (HIDWORD(v661) & 0x10000) != 0 )
      v698 &= 0xFFFFFFFFFFFFFFFCuLL;
    v702 = v411;
    if ( v411 )
    {
      v218 = NumberOfBytesToWrite_4;
      if ( NumberOfBytesToWrite_4 )
      {
        ConsoleHost = 0;
      }
      else
      {
        ConsoleHost = BasepGetConsoleHost();
        v218 = NumberOfBytesToWrite_4;
      }
      v704 = ConsoleHost;
      v703 = v218;
    }
    if ( ((unsigned __int8)KeyHandle & 1) != 0 && ((unsigned __int8)KeyHandle & 0x10) == 0 )
      v699 |= 2u;
    ExePath = BasepCsrCaptureSxsMessage(v705, &CaptureBuffer);
    v348 = ExePath;
    if ( ExePath < 0 )
      goto LABEL_60;
    CsrClientCallServer(ApiMessage, CaptureBuffer, (CSR_API_NUMBER)0x1001D, 0x218u);
    v221 = (unsigned int)v697;
    if ( v697 < 0 )
    {
      BaseSetLastNTError((unsigned int)v697);
      ExitStatus = v697;
      goto LABEL_57;
    }
    if ( ((unsigned __int8)KeyHandle & 1) == 0 )
    {
      v496 = v706;
      if ( v706 != v622 )
      {
        ExePath = BasepUpdateProcessParametersField(Process, 8, 8, (__int64)&v617);
        v348 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
      }
    }
    if ( !v398 && (v495 & 2) == 0 && !v506 )
    {
      v466 |= 1u;
      if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v221, v220) )
      {
        if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
        {
          v557 = 0;
          v224 = BaseCheckElevation(
                   Process,
                   Handle,
                   DestinationString.Buffer,
                   &v466,
                   v534,
                   v707,
                   v709,
                   v500,
                   v217,
                   0,
                   &v557);
          v348 = v224;
          if ( (unsigned int)LUAIsShadowAdminEnabled() )
          {
            if ( v224 < 0 )
              break;
            if ( (unsigned __int8)IsBasepFreeAppCompatData2Present() )
              BaseMarkProcessTokenForInstallers(Process, Handle, lpFileName, v709, v500, v557);
          }
        }
        else
        {
          v224 = BaseCheckElevation(
                   Process,
                   Handle,
                   DestinationString.Buffer,
                   &v466,
                   v534,
                   v707,
                   v709,
                   v500,
                   v217,
                   0,
                   0);
          v348 = v224;
        }
      }
      else
      {
        v224 = 0;
        v348 = 0;
      }
      if ( v224 < 0 )
        break;
    }
    v225 = Feature_AutoGenerateSparsePackages__private_IsEnabledDeviceUsageNoInline();
    LOBYTE(v226) = v353;
    v94 = v225 == 0;
    v227 = v419;
    if ( v94 || v711 || v353 || v358 || v419 )
    {
      EAAumidIfPresent = v478;
    }
    else
    {
      EtwEventActivityIdControl(1, &v690);
      EtwEventActivityIdControl(5, &v691);
      if ( (unsigned int)dword_1803A5020 > 5 )
      {
        v643 = 0x1000000;
        v844 = &v643;
        v845 = 8;
        tlgCreate1Sz_wchar_t(v846, lpFileName);
        v464[0] = v497 != 0;
        v847 = v464;
        v848 = 1;
        v463 = v493 != 0;
        v849 = &v463;
        v850 = 1;
        v461 = a6 == 1;
        v851 = &v461;
        v852 = 1;
        v601 = v350;
        v853 = &v601;
        v854 = 4;
        v460 = v412 != 0;
        v855 = &v460;
        v856 = 1;
        v459 = v483 != 0;
        v857 = &v459;
        v858 = 1;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_1803A5020,
          (unsigned int)&unk_180361458,
          (unsigned int)&v690,
          (unsigned int)&v691,
          10,
          (__int64)v843);
      }
      v912[0] = 0;
      EAAumidIfPresent = GetEAAumidIfPresent(lpFileName, v912, 130);
      v478 = EAAumidIfPresent;
      v648 = EAAumidIfPresent;
      v226 = (unsigned int)dword_1803A5020;
      if ( (unsigned int)dword_1803A5020 > 5 )
      {
        v655 = 0x1000000;
        v890 = &v655;
        v891 = 8;
        v600 = EAAumidIfPresent;
        v892 = &v600;
        v893 = 4;
        v229 = v912;
        if ( !v912[0] )
          v229 = &word_18029DECC;
        tlgCreate1Sz_wchar_t(v894, v229);
        v616 = *(_DWORD *)(v349 + 16);
        v895 = &v616;
        v896 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_1803A5020,
          (unsigned int)byte_18036152B,
          (unsigned int)&v690,
          (unsigned int)&v691,
          6,
          (__int64)v889);
      }
      v227 = v419;
      LOBYTE(v226) = v353;
    }
    if ( !v711 && (EAAumidIfPresent < 0 || !v912[0]) || (_BYTE)v226 || v358 || v227 )
      goto LABEL_888;
    v230 = &v711;
    if ( !v711 )
      v230 = v912;
    Src = v230;
    v606 = v230;
    EtwEventActivityIdControl(5, &v686);
    EtwEventActivityIdControl(1, &v687);
    v522 = 1;
    if ( (unsigned int)dword_1803A5020 > 5 )
    {
      v231 = qword_1803A5038;
      if ( (qword_1803A5030 & 0x400000000000LL) != 0 && (qword_1803A5038 & 0x400000000000LL) == qword_1803A5038 )
      {
        v644 = 0x1000000;
        v860 = &v644;
        v861 = 8;
        tlgCreate1Sz_wchar_t(v862, v230);
        v458 = v497 != 0;
        v863 = &v458;
        v864 = 1;
        v473 = v493 != 0;
        v865 = &v473;
        v866 = 1;
        v474 = a6 == 1;
        v867 = &v474;
        v868 = 1;
        v615 = v350;
        v869 = &v615;
        v870 = 4;
        v475 = v412 != 0;
        v871 = &v475;
        v872 = 1;
        v476 = v483 == 0;
        v873 = &v476;
        v874 = 1;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_1803A5020,
          (unsigned int)word_180360C82,
          (unsigned int)&v687,
          (unsigned int)&v686,
          10,
          (__int64)v859);
      }
    }
    if ( (unsigned int)Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte__private_IsEnabledDeviceUsageNoInline(v231) )
    {
      v233 = 0;
      v614 = 0;
      if ( (v479 & 2) != 0 )
      {
        v556 = 0;
        v348 = CurrentProcessFamilyNameMatches(Src);
        if ( v348 < 0 )
        {
          ExitStatus = -1073741823;
          goto LABEL_57;
        }
        v233 = v556 != 0;
        v614 = v233;
      }
      PackageActivationTokenForSxS3 = BasepGetPackageActivationTokenForSxS3(Src, v535, v233, token);
    }
    else
    {
      PackageActivationTokenForSxS3 = BasepGetPackageActivationTokenForSxS2(v230, v535, token);
    }
    PackageFullNameFromToken = PackageActivationTokenForSxS3;
    if ( (unsigned int)dword_1803A5020 > 5 )
    {
      v226 = qword_1803A5038;
      if ( (qword_1803A5030 & 0x400000000000LL) != 0 && (qword_1803A5038 & 0x400000000000LL) == qword_1803A5038 )
      {
        v656 = 0x1000000;
        v876 = &v656;
        v877 = 8;
        v613 = PackageActivationTokenForSxS3;
        v878 = &v613;
        v879 = 4;
        v467 = token[0] != 0;
        v880 = &v467;
        v881 = 1;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_1803A5020,
          (unsigned int)byte_180360D45,
          (unsigned int)&v687,
          (unsigned int)&v686,
          5,
          (__int64)v875);
      }
    }
    if ( PackageFullNameFromToken )
    {
LABEL_866:
      ExitStatus = -1073741823;
      v37 = PackageFullNameFromToken;
      goto LABEL_89;
    }
    if ( !token[0] )
    {
LABEL_888:
      if ( (unsigned int)Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte__private_IsEnabledDeviceUsageNoInline(v226) )
      {
        if ( !v419 && (v479 & 2) != 0 )
        {
          applicationUserModelIdLength = 130;
          if ( (unsigned int)ShouldRelaunchWithWin32alacarteIdentity(
                               Process,
                               applicationUserModelId,
                               &applicationUserModelIdLength) )
          {
            PackageFullNameFromToken = BasepGetPackageActivationTokenForSxS3(applicationUserModelId, v535, 1, token);
            if ( (unsigned int)dword_1803A5020 > 5
              && (qword_1803A5030 & 0x400000000000LL) != 0
              && (qword_1803A5038 & 0x400000000000LL) == qword_1803A5038 )
            {
              v649 = 0x1000000;
              v883 = &v649;
              v884 = 8;
              v594 = PackageFullNameFromToken;
              v885 = &v594;
              v886 = 4;
              v469 = token[0] != 0;
              v887 = &v469;
              v888 = 1;
              tlgWriteTransfer_EtwEventWriteTransfer(
                (unsigned int)&dword_1803A5020,
                (unsigned int)word_180360E12,
                (unsigned int)&v687,
                (unsigned int)&v686,
                5,
                (__int64)v882);
            }
            if ( PackageFullNameFromToken )
              goto LABEL_866;
            if ( token[0] )
            {
              v42 = token[0];
              v419 = token[0];
              token[0] = 0;
              v595 = 128;
              PackageFullNameFromToken = GetPackageFullNameFromToken(v419, &v595, packageFullName);
              if ( (unsigned int)dword_1803A5020 <= 5
                || (qword_1803A5030 & 0x400000000000LL) == 0
                || (qword_1803A5038 & 0x400000000000LL) != qword_1803A5038 )
              {
                goto LABEL_875;
              }
              v657 = 0x1000000;
              v898 = &v657;
              v899 = 8;
              v596 = PackageFullNameFromToken;
              v900 = &v596;
              v901 = 4;
              tlgCreate1Sz_wchar_t(v902, Src);
              v238 = packageFullName;
              if ( PackageFullNameFromToken )
                v238 = L"NULL";
              tlgCreate1Sz_wchar_t(v903, v238);
              v236 = &v897;
              v237 = word_180360E6A;
              goto LABEL_874;
            }
          }
        }
      }
      if ( (unsigned int)Feature_AlwaysUseAppxExtensionForPackagedProcesses__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( (v548->BitField & 0x10) != 0 || (v239 = 0, v420) )
          v239 = 1;
        if ( !(_BYTE)v516 && v239 && !v517 )
        {
          v611 = 0;
          v240 = NtOpenProcessToken(Process, 8u, &v611);
          if ( v240 >= 0 )
          {
            v597 = 128;
            v246 = GetPackageFullNameFromToken(v611, &v597, packageFullName);
            NtClose(v611);
            if ( !v246 )
            {
              v414 = 1;
              v540 = 1;
              RtlInitUnicodeString(&v491, packageFullName);
              goto LABEL_772;
            }
          }
          else
          {
            BaseSetLastNTError((unsigned int)v240);
          }
        }
      }
      if ( (unsigned int)Feature_Win32alacarteSupport_PROC_THREAD_ATTRIBUTE_JOB_LIST__private_IsEnabledDeviceUsageNoInline() )
      {
        v242 = v603;
        if ( v603 )
        {
          v243 = v638;
          v244 = Process;
          v639 = 0;
          ExePath = 0;
          v598 = 0;
          for ( i = 0; ; ++i )
          {
            v639 = i;
            if ( i >= v243 )
              break;
            ExePath = NtAssignProcessToJobObject(*(HANDLE *)(v242 + 8 * i), v244);
            v598 = ExePath;
            if ( ExePath < 0 )
              break;
            v242 = v603;
          }
          v348 = ExePath;
          if ( ExePath < 0 )
            goto LABEL_60;
        }
      }
      if ( ((unsigned __int8)KeyHandle & 1) != 0 )
      {
        if ( v352 )
        {
          if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v242, v241) )
          {
            if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v242, v241) )
            {
              LODWORD(v342) = v518;
              LOWORD(LengthNeeded) = v424[0];
              BasepGetAppCompatData(
                DestinationString.Buffer,
                v491.Buffer,
                &v466,
                v707,
                v708,
                &v710,
                v666,
                LengthNeeded,
                v585,
                v342,
                &v501,
                &v480,
                &v505,
                &NumberOfBytesToWrite);
              if ( !(unsigned int)BasepInitAppCompatData(Process, v505, NumberOfBytesToWrite) )
              {
                ExePath = -1073741790;
                v348 = -1073741790;
                goto LABEL_60;
              }
            }
          }
        }
      }
      else
      {
        if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v242, v241) )
        {
          LODWORD(v342) = v518;
          LOWORD(LengthNeeded) = v424[0];
          BasepGetAppCompatData(
            DestinationString.Buffer,
            v491.Buffer,
            &v466,
            v707,
            v708,
            &v710,
            v666,
            LengthNeeded,
            v585,
            v342,
            &v501,
            &v480,
            &v505,
            &NumberOfBytesToWrite);
        }
        v242 = (unsigned __int64)v505;
        if ( !v505 )
          goto LABEL_1131;
        if ( v425[0] == 0xAA64 )
        {
          v247 = v351;
          if ( (v351 & 0x800000) == 0 )
          {
            if ( *((_DWORD *)v505 + 130) < 0x11C0u
              || !*((_DWORD *)v505 + 1136)
              || (v248 = *((unsigned int *)v505 + 1137), !(_DWORD)v248) )
            {
              v314 = *((unsigned __int8 *)v505 + 4520) >> 4;
LABEL_1123:
              if ( (v314 & 8) == 0 )
                goto LABEL_1125;
              v351 = v247 | 0x800000;
              goto LABEL_772;
            }
            v552 = 0;
            v249 = (char *)v505 + v248;
            v428 = 0;
            v444 = 0;
            ThreadHandle[1] = (HANDLE)0x3000AB00110038LL;
            v439 = 21;
            v440 = 0;
            v441 = 0;
            v442 = 0;
            v443 = 0u;
            LODWORD(v444) = -65536;
            *(_QWORD *)((char *)&v444 + 4) = 0x1A010003000000LL;
            v354 = 26;
            v445 = 0;
            v425[2] = 56;
            v426 = 17;
            v427 = -21760;
            v429 = 48;
            v430 = 21;
            v431 = 0;
            v432 = 0;
            v433 = 0;
            v434 = 0u;
            v435 = 0x3000000FFFF0000LL;
            v250 = 0;
            v436 = 1704192;
            v251 = 1;
            v252 = 26;
            v415 = 0;
            v437 = 0;
            if ( *((_BYTE *)v505 + v248 + 2) >> 4 == 1 )
            {
              if ( !v249[3] )
              {
                if ( v249[8] != 21 || *(_WORD *)v249 != 56 || v249[4] != -85 )
                  goto LABEL_1118;
                if ( !v249[3] )
                  goto LABEL_929;
              }
              if ( v249[8] != 21 )
              {
LABEL_929:
                v253 = *((unsigned __int16 *)v249 + 3) - 48LL;
                if ( !v249[8] || (v254 = 1, (v249[*((unsigned __int16 *)v249 + 3)] & 1) == 0) )
                  v254 = 0;
                if ( v254 )
                  *(_QWORD *)&v434 = *((_QWORD *)v249 + 2);
                v255 = v249[8] && (v249[v253 + 48] & 1) != 0;
                v256 = v255 | v437 & 0xFE;
                LOBYTE(v437) = v256;
                if ( (unsigned __int8)v249[8] < 2u || (v257 = 1, (v249[v253 + 48] & 2) == 0) )
                  v257 = 0;
                v94 = v257 == 0;
                v258 = 2;
                if ( !v94 )
                {
                  DWORD2(v434) = *((_DWORD *)v249 + 6);
                  v258 = 2;
                }
                if ( (unsigned __int8)v249[8] < 2u || (v249[v253 + 48] & 2) == 0 )
                  v258 = 0;
                v259 = v258 | v256 & 0xFD;
                LOBYTE(v437) = v259;
                if ( (unsigned __int8)v249[8] < 3u || (v260 = 1, (v249[v253 + 48] & 4) == 0) )
                  v260 = 0;
                if ( v260 )
                  HIDWORD(v434) = *((_DWORD *)v249 + 7);
                if ( (unsigned __int8)v249[8] >= 3u && (v249[v253 + 48] & 4) != 0 )
                  v261 = 4;
                else
                  v261 = 0;
                v262 = v261 | v259 & 0xFB;
                LOBYTE(v437) = v262;
                if ( (unsigned __int8)v249[8] < 4u || (v263 = 1, (v249[v253 + 48] & 8) == 0) )
                  v263 = 0;
                if ( v263 )
                  LOWORD(v435) = *((_WORD *)v249 + 16);
                if ( (unsigned __int8)v249[8] >= 4u && (v249[v253 + 48] & 8) != 0 )
                  v264 = 8;
                else
                  v264 = 0;
                v265 = v264 | v262 & 0xF7;
                LOBYTE(v437) = v265;
                if ( (unsigned __int8)v249[8] < 5u || (v266 = 1, (v249[v253 + 48] & 0x10) == 0) )
                  v266 = 0;
                if ( v266 )
                  WORD1(v435) = *((_WORD *)v249 + 17);
                if ( (unsigned __int8)v249[8] >= 5u && (v249[v253 + 48] & 0x10) != 0 )
                  v267 = 16;
                else
                  v267 = 0;
                v268 = v267 | v265 & 0xEF;
                LOBYTE(v437) = v268;
                if ( (unsigned __int8)v249[8] < 6u || (v269 = 1, (v249[v253 + 48] & 0x20) == 0) )
                  v269 = 0;
                if ( v269 )
                  WORD2(v435) = *((_WORD *)v249 + 18);
                if ( (unsigned __int8)v249[8] >= 6u && (v249[v253 + 48] & 0x20) != 0 )
                  v270 = 32;
                else
                  v270 = 0;
                v271 = v270 | v268 & 0xDF;
                LOBYTE(v437) = v271;
                if ( (unsigned __int8)v249[8] < 7u || (v272 = 1, (v249[v253 + 48] & 0x40) == 0) )
                  v272 = 0;
                if ( v272 )
                  BYTE6(v435) = v249[38];
                if ( (unsigned __int8)v249[8] >= 7u && (v249[v253 + 48] & 0x40) != 0 )
                  v273 = 64;
                else
                  v273 = 0;
                v274 = v273 | v271 & 0xBF;
                LOBYTE(v437) = v274;
                if ( (unsigned __int8)v249[8] < 8u || (v275 = 1, v249[v253 + 48] >= 0) )
                  v275 = 0;
                if ( v275 )
                  HIBYTE(v435) = v249[39] & 0x1F;
                if ( (unsigned __int8)v249[8] < 8u || v249[v253 + 48] >= 0 )
                  v276 = 0;
                else
                  v276 = 0x80;
                LOBYTE(v437) = v276 | v274 & 0x7F;
                if ( (unsigned __int8)v249[8] < 9u || (v277 = 1, (v249[v253 + 49] & 1) == 0) )
                  v277 = 0;
                if ( v277 )
                {
                  v250 = v249[40] & 0xF;
                  LOBYTE(v436) = v250;
                }
                v278 = (unsigned __int8)v249[8] >= 9u && (v249[v253 + 49] & 1) != 0;
                v279 = v278 | BYTE1(v437) & 0xFE;
                BYTE1(v437) = v279;
                if ( (unsigned __int8)v249[8] < 0xAu || (v280 = 1, (v249[v253 + 49] & 2) == 0) )
                  v280 = 0;
                if ( v280 )
                {
                  v250 = v250 & 0xF | (16 * ((unsigned __int8)v249[40] >> 4));
                  LOBYTE(v436) = v250;
                }
                if ( (unsigned __int8)v249[8] >= 0xAu && (v249[v253 + 49] & 2) != 0 )
                  v281 = 2;
                else
                  v281 = 0;
                v282 = v281 | v279 & 0xFD;
                BYTE1(v437) = v282;
                if ( (unsigned __int8)v249[8] < 0xBu || (v283 = 1, (v249[v253 + 49] & 4) == 0) )
                  v283 = 0;
                if ( v283 )
                {
                  v251 = v249[41] & 7;
                  BYTE1(v436) = v251;
                }
                if ( (unsigned __int8)v249[8] >= 0xBu && (v249[v253 + 49] & 4) != 0 )
                  v284 = 4;
                else
                  v284 = 0;
                v285 = v284 | v282 & 0xFB;
                BYTE1(v437) = v285;
                if ( (unsigned __int8)v249[8] < 0xCu || (v286 = 1, (v249[v253 + 49] & 8) == 0) )
                  v286 = 0;
                if ( v286 )
                {
                  v251 = v251 & 0xE7 | (8 * (((unsigned __int8)v249[41] >> 3) & 3));
                  BYTE1(v436) = v251;
                }
                if ( (unsigned __int8)v249[8] >= 0xCu && (v249[v253 + 49] & 8) != 0 )
                  v287 = 8;
                else
                  v287 = 0;
                v288 = v287 | v285 & 0xF7;
                BYTE1(v437) = v288;
                if ( (unsigned __int8)v249[8] < 0xDu || (v289 = 1, (v249[v253 + 49] & 0x10) == 0) )
                  v289 = 0;
                if ( v289 )
                  BYTE1(v436) = v251 & 0x9F | (32 * (((unsigned __int8)v249[41] >> 5) & 3));
                if ( (unsigned __int8)v249[8] >= 0xDu && (v249[v253 + 49] & 0x10) != 0 )
                  v290 = 16;
                else
                  v290 = 0;
                v291 = v290 | v288 & 0xEF;
                BYTE1(v437) = v291;
                if ( (unsigned __int8)v249[8] < 0xEu || (v292 = 1, (v249[v253 + 49] & 0x20) == 0) )
                  v292 = 0;
                if ( v292 )
                {
                  v252 = v249[42] & 3 | 0x18;
                  BYTE2(v436) = v252;
                }
                if ( (unsigned __int8)v249[8] >= 0xEu && (v249[v253 + 49] & 0x20) != 0 )
                  v293 = 32;
                else
                  v293 = 0;
                v294 = v293 | v291 & 0xDF;
                BYTE1(v437) = v294;
                if ( (unsigned __int8)v249[8] < 0xFu || (v295 = 1, (v249[v253 + 49] & 0x40) == 0) )
                  v295 = 0;
                if ( v295 )
                {
                  v252 = v252 & 0xFB | (4 * ((v249[42] & 4) != 0));
                  BYTE2(v436) = v252;
                }
                if ( (unsigned __int8)v249[8] >= 0xFu && (v249[v253 + 49] & 0x40) != 0 )
                  v296 = 64;
                else
                  v296 = 0;
                v297 = v296 | v294 & 0xBF;
                BYTE1(v437) = v297;
                if ( (unsigned __int8)v249[8] < 0x10u || (v298 = 1, v249[v253 + 49] >= 0) )
                  v298 = 0;
                if ( v298 )
                {
                  v252 = v252 & 0xF7 | (8 * ((v249[42] & 8) != 0));
                  BYTE2(v436) = v252;
                }
                if ( (unsigned __int8)v249[8] < 0x10u || v249[v253 + 49] >= 0 )
                  v299 = 0;
                else
                  v299 = 0x80;
                BYTE1(v437) = v299 | v297 & 0x7F;
                if ( (unsigned __int8)v249[8] < 0x11u || (v300 = 1, (v249[v253 + 50] & 1) == 0) )
                  v300 = 0;
                if ( v300 )
                {
                  v252 = v252 & 0xEF | (16 * ((v249[42] & 0x10) != 0));
                  BYTE2(v436) = v252;
                }
                v301 = (unsigned __int8)v249[8] >= 0x11u && (v249[v253 + 50] & 1) != 0;
                v302 = v301 | BYTE2(v437) & 0xFE;
                BYTE2(v437) = v302;
                if ( (unsigned __int8)v249[8] < 0x12u || (v303 = 1, (v249[v253 + 50] & 2) == 0) )
                  v303 = 0;
                if ( v303 )
                {
                  v252 = v252 & 0xDF | (32 * ((v249[42] & 0x20) != 0));
                  BYTE2(v436) = v252;
                }
                if ( (unsigned __int8)v249[8] >= 0x12u && (v249[v253 + 50] & 2) != 0 )
                  v304 = 2;
                else
                  v304 = 0;
                v305 = v304 | v302 & 0xFD;
                BYTE2(v437) = v305;
                if ( (unsigned __int8)v249[8] < 0x13u || (v306 = 1, (v249[v253 + 50] & 4) == 0) )
                  v306 = 0;
                if ( v306 )
                {
                  v252 = v252 & 0xBF | (((v249[42] & 0x40) != 0) << 6);
                  BYTE2(v436) = v252;
                }
                if ( (unsigned __int8)v249[8] >= 0x13u && (v249[v253 + 50] & 4) != 0 )
                  v307 = 4;
                else
                  v307 = 0;
                v308 = v307 | v305 & 0xFB;
                BYTE2(v437) = v308;
                if ( (unsigned __int8)v249[8] < 0x14u || (v309 = 1, (v249[v253 + 50] & 8) == 0) )
                  v309 = 0;
                if ( v309 )
                  BYTE2(v436) = v252 & 0x7F | ((unsigned __int8)v249[42] >> 7 << 7);
                if ( (unsigned __int8)v249[8] >= 0x14u && (v249[v253 + 50] & 8) != 0 )
                  v310 = 8;
                else
                  v310 = 0;
                v311 = v310 | v308 & 0xF7;
                BYTE2(v437) = v311;
                if ( (unsigned __int8)v249[8] < 0x15u || (v312 = 1, (v249[v253 + 50] & 0x10) == 0) )
                  v312 = 0;
                if ( v312 )
                  BYTE3(v436) = v249[43] & 1 | v415 & 0xFE;
                if ( (unsigned __int8)v249[8] >= 0x15u && (v249[v253 + 50] & 0x10) != 0 )
                  v313 = 16;
                else
                  v313 = 0;
                BYTE2(v437) = v313 | v311 & 0xEF;
              }
            }
LABEL_1118:
            v247 = v351;
            LOWORD(v201) = v408;
            if ( (v437 & 0x200) != 0 )
              v314 = v250 >> 4;
            else
              LOBYTE(v314) = v552;
            v208 = v640;
            goto LABEL_1123;
          }
        }
LABEL_1125:
        BaseAddress = 0;
        RegionSize = NumberOfBytesToWrite;
        ExePath = NtAllocateVirtualMemory(Process, &BaseAddress, 0, &RegionSize, 0x1000u, 4u);
        v348 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
        ExePath = NtWriteVirtualMemory(Process, BaseAddress, v505, NumberOfBytesToWrite, 0);
        v348 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
        ExePath = NtWriteVirtualMemory(Process, (PVOID)(v208 + 728), &BaseAddress, 8u, 0);
        v348 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
        v242 = v624;
        if ( v624 )
        {
          v555 = (int)BaseAddress;
          ExePath = NtWriteVirtualMemory(Process, (PVOID)(v624 + 488), &v555, 4u, 0);
          v348 = ExePath;
        }
        if ( ExePath < 0 )
          goto LABEL_60;
      }
LABEL_1131:
      if ( !v398 && ((unsigned __int8)KeyHandle & 1) == 0 )
      {
        ExePath = (unsigned __int8)IsBasepProcessInvalidImagePresent(v242, v241)
                ? BaseElevationPostProcessing(v466, (unsigned __int16)v201, Process)
                : 0;
        v348 = ExePath;
        if ( ExePath < 0 )
        {
LABEL_1142:
          ExitStatus = ExePath;
          goto LABEL_60;
        }
      }
      if ( !v421 )
      {
LABEL_1158:
        if ( (v350 & 4) == 0 )
        {
          v224 = NtResumeThread(ThreadHandle[0], 0);
          v348 = v224;
          if ( v224 < 0 )
            goto LABEL_828;
        }
LABEL_1160:
        ProcessInternalW = 1;
        v345 = 1;
        if ( v407 )
          v407 |= 8u;
        if ( v498 )
        {
          if ( v411 == 32 )
          {
            v318 = v349;
            *(_QWORD *)v349 = (unsigned __int64)v498 | 2;
            if ( (v407 & 4) != 0 )
              v636 = 0;
          }
          else
          {
            v318 = v349;
            *(_QWORD *)v349 = (unsigned __int64)v498 | 1;
          }
          if ( Process )
            NtClose(Process);
        }
        else
        {
          v318 = v349;
          *(_QWORD *)v349 = Process;
        }
        *(HANDLE *)(v318 + 8) = ThreadHandle[0];
        *(_DWORD *)(v318 + 16) = v636.m128i_i32[0];
        *(_DWORD *)(v318 + 20) = v636.m128i_i32[2];
        Process = 0;
        ThreadHandle[0] = 0;
        v319 = HeapHandle;
        v320 = v349;
        goto LABEL_1174;
      }
      ExePath = BasepPostSuccessAppXExtension(Process);
      v348 = ExePath;
      if ( ExePath < 0 )
        goto LABEL_1142;
      if ( *(_QWORD *)(v421 + 72) )
      {
        ExePath = BasepUpdateProcessParametersField(Process, 1024, 664, (__int64)&v617);
        v348 = ExePath;
      }
      if ( ExePath < 0 )
        goto LABEL_1142;
      v494 = 0;
      if ( !v410 || (v315 = *(_DWORD *)(v410 + 548), v315 == 1) )
      {
        if ( v358 )
        {
          v317 = *(unsigned int *)(v358 + 32);
          if ( (_DWORD)v317 != 1 )
          {
            v355 = 1;
            ExePath = CompleteAppExecutionAliasProcessCreationEx(
                        Process,
                        ThreadHandle[0],
                        v317,
                        FileName,
                        pszSrc,
                        v420,
                        &v494);
            v348 = ExePath;
            if ( ExePath < 0 )
              goto LABEL_1142;
            goto LABEL_1156;
          }
        }
        if ( !v419 )
        {
LABEL_1156:
          if ( (v494 & 1) != 0 )
            v350 |= 4u;
          goto LABEL_1158;
        }
        v316 = BasepFinishPackageActivationForSxS(Process, ThreadHandle[0], FileName, pszSrc, v420, &v494);
      }
      else
      {
        v356 = 1;
        v316 = CompletePackagedProcessCreationEx(
                 Process,
                 ThreadHandle[0],
                 v315 == 3,
                 v315 == 2,
                 FileName,
                 pszSrc,
                 *(_BYTE *)(v410 + 544) != 0,
                 v420,
                 &v494);
      }
      if ( v316 )
      {
        ExitStatus = -1073741823;
        v37 = v316;
        goto LABEL_89;
      }
      goto LABEL_1156;
    }
    v42 = token[0];
    v419 = token[0];
    token[0] = 0;
    packageFullNameLength = 128;
    PackageFullNameFromToken = GetPackageFullNameFromToken(v419, &packageFullNameLength, packageFullName);
    if ( (unsigned int)dword_1803A5020 <= 5
      || (qword_1803A5030 & 0x400000000000LL) == 0
      || (qword_1803A5038 & 0x400000000000LL) != qword_1803A5038 )
    {
      goto LABEL_875;
    }
    v654 = 0x1000000;
    v905 = &v654;
    v906 = 8;
    v593 = PackageFullNameFromToken;
    v907 = &v593;
    v908 = 4;
    tlgCreate1Sz_wchar_t(v909, Src);
    v235 = packageFullName;
    if ( PackageFullNameFromToken )
      v235 = L"NULL";
    tlgCreate1Sz_wchar_t(v910, v235);
    v236 = &v904;
    v237 = (__int16 *)byte_180360D9D;
LABEL_874:
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_1803A5020,
      (_DWORD)v237,
      (unsigned int)&v687,
      (unsigned int)&v686,
      6,
      (__int64)v236);
LABEL_875:
    if ( PackageFullNameFromToken )
      goto LABEL_866;
    RtlInitUnicodeString(&v491, packageFullName);
    if ( token[1] )
    {
      BasepFreeBnoIsolationParameter(&v586);
      RtlInitUnicodeString(&v586, (PCWSTR)token[1]);
      LOBYTE(v588) = 1;
      v488 = 1;
      v515 = 1;
    }
    ProcessHeap = HeapHandle;
LABEL_681:
    v23 = (wchar_t *)v423;
    v39 = v486;
    v40 = v477;
    v38 = v418;
    v41 = v487;
  }
  if ( v224 == -1073740756 && (v495 & 1) == 0 && (unsigned __int8)IsBasepProcessInvalidImagePresent(v223, v222) )
    BaseWriteErrorElevationRequiredEvent();
LABEL_828:
  BaseSetLastNTError((unsigned int)v224);
  ExitStatus = v224;
LABEL_57:
  ProcessInternalW = 0;
  v345 = 0;
LABEL_1173:
  v320 = v349;
  v319 = HeapHandle;
LABEL_1174:
  v321 = NtCurrentTeb()->LastErrorValue;
  if ( Buffer )
    RtlFreeHeap(v319, 0, Buffer);
  if ( v510 )
  {
    if ( ProcessInternalW == 1 && (unsigned int)Feature_PcaProcessTracking__private_IsEnabledDeviceUsageNoInline() )
      BasepSendPcaEvent(*(unsigned int *)(v320 + 16), v510);
    RtlFreeHeap(v319, 0, v510);
  }
  RtlFreeUnicodeString(&UnicodeString);
  if ( !v411 && (unsigned __int8)IsBasepProcessInvalidImagePresent(v323, v322) )
    BasepReleaseSxsCreateProcessUtilityStruct(v683);
  if ( v580 )
    RtlDestroyEnvironment(v580);
  v324 = v358;
  if ( v358 )
  {
    memset_0(v680, 0, 0x64u);
    Buf2 = 104;
    if ( *(_DWORD *)(v324 + 32) )
    {
      if ( (unsigned int)dword_1803A5020 > 5
        && (qword_1803A5030 & 0x400000000000LL) != 0
        && (qword_1803A5038 & 0x400000000000LL) == qword_1803A5038 )
      {
        v366 = 1;
        v809 = &v366;
        v810 = 1;
        v529 = v321;
        v811 = &v529;
        v812 = 4;
        v367 = v355;
        v813 = &v367;
        v814 = 1;
        tlgCreate1Sz_wchar_t(v815, *(_QWORD *)v358);
        if ( *(_QWORD *)(v358 + 8) )
          v328 = (const WCHAR *)CentennialActivationRemovePIIfromFilePath_Kernel();
        else
          v328 = &word_18029DECC;
        tlgCreate1Sz_wchar_t(v816, v328);
        v368 = ProcessInternalW == 1;
        v817 = &v368;
        v818 = 1;
        v369 = v497 != 0;
        v819 = &v369;
        v820 = 1;
        v370 = v493 != 0;
        v821 = &v370;
        v822 = 1;
        v371 = a6 == 1;
        v823 = &v371;
        v824 = 1;
        v521 = v350;
        v825 = &v521;
        v826 = 4;
        v372 = v412 != 0;
        v827 = &v372;
        v828 = 1;
        v373 = memcmp_0(&Buf1, &Buf2, 0x68u) == 0;
        v829 = &v373;
        v830 = 1;
        v374 = v483 == 0;
        v831 = &v374;
        v832 = 1;
        v326 = &v808;
        v327 = (char *)&unk_180361018;
LABEL_1202:
        tlgWriteTransfer_EtwEventWriteTransfer((unsigned int)&dword_1803A5020, (_DWORD)v327, 0, 0, 15, (__int64)v326);
      }
    }
    else if ( (unsigned int)dword_1803A5020 > 5
           && (qword_1803A5030 & 0x400000000000LL) != 0
           && (qword_1803A5038 & 0x400000000000LL) == qword_1803A5038 )
    {
      v399 = 1;
      v784 = &v399;
      v785 = 1;
      v519 = v321;
      v786 = &v519;
      v787 = 4;
      v400 = v355;
      v788 = &v400;
      v789 = 1;
      tlgCreate1Sz_wchar_t(v790, *(_QWORD *)v358);
      if ( *(_QWORD *)(v358 + 8) )
        v325 = (const WCHAR *)CentennialActivationRemovePIIfromFilePath_Kernel();
      else
        v325 = &word_18029DECC;
      tlgCreate1Sz_wchar_t(v791, v325);
      v401 = ProcessInternalW == 1;
      v792 = &v401;
      v793 = 1;
      v402 = v497 != 0;
      v794 = &v402;
      v795 = 1;
      v403 = v493 != 0;
      v796 = &v403;
      v797 = 1;
      v404 = a6 == 1;
      v798 = &v404;
      v799 = 1;
      v520 = v350;
      v800 = &v520;
      v801 = 4;
      v405 = v412 != 0;
      v802 = &v405;
      v803 = 1;
      v406 = memcmp_0(&Buf1, &Buf2, 0x68u) == 0;
      v804 = &v406;
      v805 = 1;
      v365 = v483 == 0;
      v806 = &v365;
      v807 = 1;
      v326 = &v783;
      v327 = &byte_180360EDF;
      goto LABEL_1202;
    }
    if ( !ProcessInternalW )
      PerformAppxLicenseRundownEx(*(_QWORD *)v358, *(_QWORD *)(v358 + 16));
    FreeAppExecutionAliasInfoEx(v358);
    v358 = 0;
  }
  if ( v421 )
  {
    BasepReleaseAppXContext();
    v421 = 0;
  }
  if ( v576 )
    BasepReleaseAppXContext();
  if ( v504 )
    NtClose(v504);
  if ( v419 )
    NtClose(v419);
  if ( v522 == 1 && (unsigned int)dword_1803A5020 > 5 )
  {
    v322 = 0x400000000000LL;
    if ( (qword_1803A5030 & 0x400000000000LL) != 0 && (qword_1803A5038 & 0x400000000000LL) == qword_1803A5038 )
    {
      v605 = 0x1000000;
      v834 = &v605;
      v835 = 8;
      v523 = v321;
      v836 = &v523;
      v837 = 4;
      tlgCreate1Sz_wchar_t(v838, Src);
      v375 = ProcessInternalW == 1;
      v839 = &v375;
      v840 = 1;
      v524 = *(_DWORD *)(v349 + 16);
      v841 = &v524;
      v842 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_1803A5020,
        (unsigned int)byte_18036114D,
        (unsigned int)&v687,
        (unsigned int)&v686,
        7,
        (__int64)v833);
    }
  }
  if ( Environment )
    RtlDestroyEnvironment(Environment);
  v329 = HeapHandle;
  if ( v577 )
    RtlFreeHeap(HeapHandle, 0, v577);
  if ( P )
    RtlFreeHeap(v329, 0, P);
  if ( v608 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v608);
  if ( v537 )
    RtlFreeHeap(v329, 0, v537);
  if ( Handle )
    NtClose(Handle);
  if ( v549 )
    NtClose(v549);
  if ( ThreadHandle[0] )
  {
    if ( DebugObject )
      NtRemoveProcessDebug(Process, DebugObject);
    NtTerminateProcess(Process, ExitStatus);
    NtWaitForSingleObject(Process, 0, 0);
    NtClose(ThreadHandle[0]);
  }
  v330 = Process;
  if ( Process )
    NtClose(Process);
  if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v330, v322) )
    BasepFreeAppCompatData(v505, v508, v501);
  RtlFreeUnicodeString(&v589);
  if ( (v628 || v631) && (unsigned __int8)IsBasepProcessInvalidImagePresent(v332, v331) )
    BaseDestroyVDMEnvironment(&v627, &v630);
  if ( v407 && (v407 & 8) == 0 )
  {
    if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v332, v331) )
      BaseUpdateVDMEntry(0, &NumberOfBytesToWrite_4, v407, v411);
    if ( v498 )
      NtClose(v498);
  }
  if ( lpPath )
    RtlReleasePath();
  if ( CaptureBuffer )
  {
    CsrFreeCaptureBuffer(CaptureBuffer);
    CaptureBuffer = 0;
  }
  if ( v579 )
    RtlFreeHeap(v329, 0, v579);
  if ( v550 )
    RtlFreeHeap(v329, 0, v550);
  v333 = v410;
  if ( v410 )
  {
    memset_0(v682, 0, 0x64u);
    v681 = 104;
    if ( *(_DWORD *)(v333 + 548) == 4 )
    {
      if ( (unsigned int)dword_1803A5020 > 5
        && (qword_1803A5030 & 0x400000000000LL) != 0
        && (qword_1803A5038 & 0x400000000000LL) == qword_1803A5038 )
      {
        v609 = 0x1000000;
        v757 = &v609;
        v758 = 8;
        v376 = 1;
        v759 = &v376;
        v760 = 1;
        v525 = v321;
        v761 = &v525;
        v762 = 4;
        v377 = v356;
        v763 = &v377;
        v764 = 1;
        tlgCreate1Sz_wchar_t(v765, v410 + 262);
        if ( *(_QWORD *)(v410 + 520) )
          v334 = (const WCHAR *)CentennialActivationRemovePIIfromFilePath_Kernel();
        else
          v334 = &word_18029DECC;
        tlgCreate1Sz_wchar_t(v766, v334);
        v378 = ProcessInternalW == 1;
        v767 = &v378;
        v768 = 1;
        v379 = v497 != 0;
        v769 = &v379;
        v770 = 1;
        v380 = v493 != 0;
        v771 = &v380;
        v772 = 1;
        v381 = a6 == 1;
        v773 = &v381;
        v774 = 1;
        v526 = v350;
        v775 = &v526;
        v776 = 4;
        v382 = v412 != 0;
        v777 = &v382;
        v778 = 1;
        v383 = memcmp_0(&Buf1, &v681, 0x68u) == 0;
        v779 = &v383;
        v780 = 1;
        v384 = v483 == 0;
        v781 = &v384;
        v782 = 1;
        v335 = &v756;
        v336 = word_1803611AA;
        goto LABEL_1275;
      }
    }
    else if ( (unsigned int)dword_1803A5020 > 5
           && (qword_1803A5030 & 0x400000000000LL) != 0
           && (qword_1803A5038 & 0x400000000000LL) == qword_1803A5038 )
    {
      v610 = 0x1000000;
      v730 = &v610;
      v731 = 8;
      v385 = 1;
      v732 = &v385;
      v733 = 1;
      v527 = v321;
      v734 = &v527;
      v735 = 4;
      v386 = v356;
      v736 = &v386;
      v737 = 1;
      tlgCreate1Sz_wchar_t(v738, v410 + 262);
      if ( *(_QWORD *)(v410 + 520) )
        v337 = (const WCHAR *)CentennialActivationRemovePIIfromFilePath_Kernel();
      else
        v337 = &word_18029DECC;
      tlgCreate1Sz_wchar_t(v739, v337);
      v387 = ProcessInternalW == 1;
      v740 = &v387;
      v741 = 1;
      v388 = v497 != 0;
      v742 = &v388;
      v743 = 1;
      v389 = v493 != 0;
      v744 = &v389;
      v745 = 1;
      v390 = a6 == 1;
      v746 = &v390;
      v747 = 1;
      v528 = v350;
      v748 = &v528;
      v749 = 4;
      v391 = v412 != 0;
      v750 = &v391;
      v751 = 1;
      v392 = memcmp_0(&Buf1, &v681, 0x68u) == 0;
      v752 = &v392;
      v753 = 1;
      v393 = v483 == 0;
      v754 = &v393;
      v755 = 1;
      v335 = &v729;
      v336 = (__int16 *)byte_180361303;
LABEL_1275:
      tlgWriteTransfer_EtwEventWriteTransfer((unsigned int)&dword_1803A5020, (_DWORD)v336, 0, 0, 16, (__int64)v335);
    }
    BasepReleasePackagedAppInfo(v410);
    v410 = 0;
  }
  BasepFreeBnoIsolationParameter(&v586);
  BasepFreeActivationTokenInfo(token);
  NtCurrentTeb()->LastErrorValue = v321;
  return ProcessInternalW;
}

```

## disassembly

```asm
0x18008e220  push    rbx
0x18008e222  push    rsi
0x18008e223  push    rdi
0x18008e224  push    r12
0x18008e226  push    r13
0x18008e228  push    r14
0x18008e22a  push    r15
0x18008e22c  mov     eax, 2200h
0x18008e231  call    __chkstk_1
0x18008e236  sub     rsp, rax
0x18008e239  mov     rax, cs:__security_cookie
0x18008e240  xor     rax, rsp
0x18008e243  mov     [rsp+2238h+var_48], rax
0x18008e24b  mov     [rsp+2238h+var_19B8], rsp
0x18008e253  mov     rax, r9
0x18008e256  mov     [rsp+2238h+var_1EE0], rax
0x18008e25e  mov     rsi, r8
0x18008e261  mov     rbx, rdx
0x18008e264  mov     r13, rcx
0x18008e267  mov     [rsp+2238h+var_1E00], rcx
0x18008e26f  mov     r15, [rsp+2238h+arg_50]
0x18008e277  mov     [rsp+2238h+var_2150], r15
0x18008e27f  mov     r14d, [rsp+2238h+arg_30]
0x18008e287  mov     [rsp+2238h+lpFileName], rdx
0x18008e28f  mov     [rsp+2238h+pszSrc], r8
0x18008e297  mov     [rsp+2238h+var_1D88], rax
0x18008e29f  mov     rax, [rsp+2238h+arg_20]
0x18008e2a7  mov     [rsp+2238h+var_1EF8], rax
0x18008e2af  mov     [rsp+2238h+var_1D98], rax
0x18008e2b7  mov     [rsp+2238h+var_2148], r14d
0x18008e2bf  mov     rax, [rsp+2238h+arg_38]
0x18008e2c7  mov     [rsp+2238h+var_2088], rax
0x18008e2cf  mov     rax, [rsp+2238h+arg_40]
0x18008e2d7  mov     [rsp+2238h+FileName], rax
0x18008e2df  mov     rax, [rsp+2238h+arg_48]
0x18008e2e7  mov     [rsp+2238h+var_1B58], rax
0x18008e2ef  mov     [rsp+2238h+var_1C38], r15
0x18008e2f7  xor     edi, edi
0x18008e2f9  mov     [rsp+2238h+ReturnLength], edi
0x18008e300  mov     dword ptr [rsp+2238h+NumberOfBytesToWrite+4], edi
0x18008e307  mov     [rsp+2238h+var_20A8], edi
0x18008e30e  mov     [rsp+2238h+var_2090], edi
0x18008e315  mov     [rsp+2238h+var_1B98], rdi
0x18008e31d  mov     [rsp+2238h+var_1B78], rdi
0x18008e325  mov     [rsp+2238h+var_1CF8], rdi
0x18008e32d  xor     eax, eax
0x18008e32f  mov     dword ptr [rsp+2238h+Buf1+4], eax
0x18008e336  xor     edx, edx; Val
0x18008e338  lea     r8d, [rdi+64h]; Size
0x18008e33c  lea     rcx, [rsp+2238h+Buf1]; void *
0x18008e344  call    memset_0
0x18008e349  mov     [rsp+2238h+lpPath], rdi
0x18008e351  xor     edx, edx; Val
0x18008e353  mov     r8d, 3B8h; Size
0x18008e359  lea     rcx, [rsp+2238h+ApiMessage]; void *
0x18008e361  call    memset_0
0x18008e366  mov     [rsp+2238h+ReturnedLength], edi
0x18008e36d  xor     eax, eax
0x18008e36f  xorps   xmm0, xmm0
0x18008e372  movups  [rsp+2238h+var_1968], xmm0
0x18008e37a  movups  xmmword ptr [rsp+2238h+var_1958], xmm0
0x18008e382  movups  xmmword ptr [rsp+2238h+var_1958+0Ch], xmm0
0x18008e38a  movups  [rsp+2238h+var_1938], xmm0
0x18008e392  movups  xmmword ptr [rsp+2238h+var_1928], xmm0
0x18008e39a  movups  xmmword ptr [rsp+2238h+var_1928+0Ch], xmm0
0x18008e3a2  mov     [rsp+2238h+var_1B60], rdi
0x18008e3aa  mov     [rsp+2238h+var_1B68], rdi
0x18008e3b2  movups  xmmword ptr [rsp+2238h+UnicodeString.Length], xmm0
0x18008e3ba  xorps   xmm1, xmm1
0x18008e3bd  movups  xmmword ptr [rsp+2238h+DestinationString.Length], xmm1
0x18008e3c5  movups  [rsp+2238h+var_17C8], xmm0
0x18008e3cd  movups  [rsp+2238h+var_17B8], xmm0
0x18008e3d5  movups  [rsp+2238h+var_2118], xmm1
0x18008e3dd  movups  [rsp+2238h+var_2108], xmm1
0x18008e3e5  movups  [rsp+2238h+var_20F8], xmm1
0x18008e3ed  mov     [rsp+2238h+var_1B50], 140012h
0x18008e3f9  lea     rax, ModuleName; "ntdll.dll"
0x18008e400  mov     [rsp+2238h+var_1B48], rax
0x18008e408  xor     edx, edx; Val
0x18008e40a  lea     r8d, [rdi+58h]; Size
0x18008e40e  lea     rcx, [rsp+2238h+var_1BF8]; void *
0x18008e416  call    memset_0
0x18008e41b  mov     [rsp+2238h+Result], edi
0x18008e422  mov     [rsp+2238h+var_1D24], edi
0x18008e429  mov     [rsp+2238h+var_1D40], edi
0x18008e430  xor     edx, edx; Val
0x18008e432  lea     r8d, [rdi+40h]; Size
0x18008e436  lea     rcx, [rsp+2238h+var_1A18]; void *
0x18008e43e  call    memset_0
0x18008e443  xorps   xmm0, xmm0
0x18008e446  movups  xmmword ptr [rsp+2238h+DynamicString.Length], xmm0
0x18008e44e  mov     qword ptr [rsp+2238h+var_1CA0.Length], rdi
0x18008e456  mov     [rsp+2238h+var_20BB], dil
0x18008e45e  mov     [rsp+2238h+Response], edi
0x18008e465  mov     [rsp+2238h+var_1EE8], edi
0x18008e46c  mov     [rsp+2238h+BaseAddress], rdi
0x18008e474  mov     [rsp+2238h+RegionSize], rdi
0x18008e47c  mov     r12d, 448h
0x18008e482  mov     r8d, r12d; Size
0x18008e485  xor     edx, edx; Val
0x18008e487  lea     rcx, [rsp+2238h+var_1358]; void *
0x18008e48f  call    memset_0
0x18008e494  mov     [rsp+2238h+var_2164], edi
0x18008e49b  mov     r8d, r12d; Size
0x18008e49e  xor     edx, edx; Val
0x18008e4a0  lea     rcx, [rsp+2238h+var_F08]; void *
0x18008e4a8  call    memset_0
0x18008e4ad  mov     [rsp+2238h+var_1F28], rdi
0x18008e4b5  xorps   xmm0, xmm0
0x18008e4b8  movups  [rsp+2238h+var_1B40], xmm0
0x18008e4c0  xorps   xmm1, xmm1
0x18008e4c3  movups  xmmword ptr [rsp+2238h+var_1F20.Length], xmm1
0x18008e4cb  mov     [rsp+2238h+var_1EA0], rdi
0x18008e4d3  mov     [rsp+2238h+Environment], rdi
0x18008e4db  mov     [rsp+2238h+var_1CE0], rdi
0x18008e4e3  mov     [rsp+2238h+var_1EB0], rdi
0x18008e4eb  mov     [rsp+2238h+var_2060], rdi
0x18008e4f3  mov     [rsp+2238h+var_207A], dil
0x18008e4fb  mov     [rsp+2238h+var_1F90], edi
0x18008e502  mov     [rsp+2238h+var_2128], rdi
0x18008e50a  mov     [rsp+2238h+var_2098], rdi
0x18008e512  mov     [rsp+2238h+TokenHandle], rdi
0x18008e51a  mov     [rsp+2238h+ProcessInformation], dil
0x18008e522  mov     [rsp+2238h+var_2048], di
0x18008e52a  mov     [rsp+2238h+var_1DCC], di
0x18008e532  mov     [rsp+2238h+var_2044], di
0x18008e53a  xor     eax, eax
0x18008e53c  movups  [rsp+2238h+var_19A0], xmm0
0x18008e544  movups  [rsp+2238h+var_1990], xmm0
0x18008e54c  movups  [rsp+2238h+var_1980], xmm0
0x18008e554  mov     [rsp+2238h+var_1970], rax
0x18008e55c  movups  [rsp+2238h+var_19B0], xmm0
0x18008e564  mov     [rsp+2238h+var_1AD8], rdi
0x18008e56c  mov     [rsp+2238h+var_1D4C], edi
0x18008e573  mov     [rsp+2238h+var_1DC4], edi
0x18008e57a  movups  [rsp+2238h+var_1798], xmm0
0x18008e582  movups  [rsp+2238h+var_17A8], xmm1
0x18008e58a  movups  [rsp+2238h+var_1770], xmm0
0x18008e592  movups  [rsp+2238h+var_1760], xmm1
0x18008e59a  mov     [rsp+2238h+var_1D28], edi
0x18008e5a1  mov     [rsp+2238h+var_1B28], rdi
0x18008e5a9  mov     [rsp+2238h+var_1D48], edi
0x18008e5b0  test    rbx, rbx
0x18008e5b3  jnz     short loc_18008E5C4
0x18008e5b5  test    rsi, rsi
0x18008e5b8  jnz     short loc_18008E5C4
0x18008e5ba  mov     ecx, 0C0000030h
0x18008e5bf  jmp     loc_180096E44
0x18008e5c4  test    r15, r15
0x18008e5c7  jz      loc_180096E3F
0x18008e5cd  mov     rbx, [rsp+2238h+var_1B58]
0x18008e5d5  test    rbx, rbx
0x18008e5d8  jz      loc_180096E3F
0x18008e5de  mov     [rsp+2238h+var_1ED8], rdi
0x18008e5e6  mov     [rsp+2238h+Process], rdi
0x18008e5ee  mov     [rsp+2238h+ThreadHandle], rdi
0x18008e5f6  mov     [rsp+2238h+CaptureBuffer], rdi
0x18008e5fe  mov     [rsp+2238h+var_1C60], edi
0x18008e605  mov     [rsp+2238h+FilePart], rdi
0x18008e60d  mov     [rsp+2238h+var_1CA0.Buffer], rdi
0x18008e615  mov     [rsp+2238h+var_20B3], dil
0x18008e61d  mov     [rsp+2238h+ProcessHandle], rdi
0x18008e625  mov     [rsp+2238h+var_1CD8], rdi
0x18008e62d  mov     [rsp+2238h+var_1EA8], rdi
0x18008e635  mov     dword ptr [rsp+2238h+NumberOfBytesToWrite], edi
0x18008e63c  mov     [rsp+2238h+var_1E88], rdi
0x18008e644  mov     [rsp+2238h+var_1F2C], edi
0x18008e64b  mov     [rsp+2238h+var_1EC8], rdi
0x18008e653  mov     [rsp+2238h+var_1F68], edi
0x18008e65a  mov     [rsp+2238h+var_1F8C], edi
0x18008e661  mov     [rsp+2238h+var_1D64], edi
0x18008e668  mov     [rsp+2238h+var_1E08], rdi
0x18008e670  mov     [rsp+2238h+var_1ECC], edi
0x18008e677  mov     [rsp+2238h+var_1CD0], rdi
0x18008e67f  mov     [rsp+2238h+var_1E50], edi
0x18008e686  mov     [rsp+2238h+var_2140], edi
0x18008e68d  mov     [rsp+2238h+var_1EEC], edi
0x18008e694  mov     [rsp+2238h+var_1B90], rdi
0x18008e69c  mov     [rsp+2238h+var_1B70], rdi
0x18008e6a4  movups  [rsp+2238h+var_1A28], xmm0
0x18008e6ac  movups  [rsp+2238h+var_1788], xmm1
0x18008e6b4  mov     [rsp+2238h+var_1778], rax
0x18008e6bc  movups  [rsp+2238h+var_1738], xmm0
0x18008e6c4  mov     [rsp+2238h+var_1728], rax
0x18008e6cc  mov     [rsp+2238h+var_1CE8], rdi
0x18008e6d4  mov     [rsp+2238h+var_1C8C], edi
0x18008e6db  mov     [rsp+2238h+var_1D50], edi
0x18008e6e2  mov     [rsp+2238h+var_1F6C], edi
0x18008e6e9  movups  [rsp+2238h+var_1750], xmm0
0x18008e6f1  mov     [rsp+2238h+var_1740], rax
0x18008e6f9  xor     edx, edx; Val
0x18008e6fb  lea     r8d, [rdx+58h]; Size
0x18008e6ff  lea     rcx, [rsp+2238h+var_1828]; void *
0x18008e707  call    memset_0
0x18008e70c  xorps   xmm0, xmm0
0x18008e70f  xor     eax, eax
0x18008e711  movups  xmmword ptr [rsp+2238h+var_1CC8.Length], xmm0
0x18008e719  movups  [rsp+2238h+var_1CB8], xmm0
0x18008e721  mov     [rsp+2238h+var_1CA8], rax
0x18008e729  movups  xmmword ptr [rsp+2238h+token], xmm0
0x18008e731  mov     rax, gs:60h
0x18008e73a  mov     [rsp+2238h+var_1DB0], rax
0x18008e742  mov     r12, [rax+30h]
0x18008e746  mov     [rsp+2238h+HeapHandle], r12
0x18008e74e  mov     r15d, 100h
0x18008e754  mov     r8d, r15d; Size
0x18008e757  xor     edx, edx; Val
0x18008e759  lea     rcx, [rsp+2238h+packageFullName]; void *
0x18008e761  call    memset_0
0x18008e766  mov     esi, 1
0x18008e76b  mov     [rsp+2238h+var_1DC4], esi
0x18008e772  mov     [rsp+2238h+var_268], di
0x18008e77a  mov     eax, r14d
0x18008e77d  and     eax, 18h
0x18008e780  cmp     al, 18h
0x18008e782  jz      short loc_18008E79A
0x18008e784  mov     eax, r14d
0x18008e787  and     eax, 1000h
0x18008e78c  mov     ecx, 800h
0x18008e791  test    ecx, r14d
0x18008e794  jz      short loc_18008E7B0
0x18008e796  test    eax, eax
0x18008e798  jz      short loc_18008E7CF
0x18008e79a  mov     ecx, 57h ; 'W'; LastError
0x18008e79f  call    cs:__imp_RtlSetLastWin32Error
0x18008e7a6  nop     dword ptr [rax+rax+00h]
0x18008e7ab  jmp     loc_180096E49
0x18008e7b0  test    eax, eax
0x18008e7b2  jnz     short loc_18008E7CF
0x18008e7b4  mov     rax, cs:BaseStaticServerData
0x18008e7bb  cmp     [rax+7F4h], dil
0x18008e7c2  jz      short loc_18008E7CF
0x18008e7c4  or      r14d, ecx
0x18008e7c7  mov     [rsp+2238h+var_2148], r14d
0x18008e7cf  mov     rcx, rdi
0x18008e7d2  mov     [rsp+2238h+DebugObject], rcx
0x18008e7da  test    r14b, 40h
0x18008e7de  jz      short loc_18008E7E5
0x18008e7e0  mov     al, sil
0x18008e7e3  jmp     short loc_18008E83A
0x18008e7e5  bt      r14d, 0Eh
0x18008e7ea  jnb     short loc_18008E7F0
0x18008e7ec  mov     al, 5
0x18008e7ee  jmp     short loc_18008E83A
0x18008e7f0  test    r14b, 20h
0x18008e7f4  jz      short loc_18008E801
0x18008e7f6  mov     r15d, 2
0x18008e7fc  mov     al, r15b
0x18008e7ff  jmp     short loc_18008E840
0x18008e801  bt      r14d, 0Fh
0x18008e806  jnb     short loc_18008E80C
0x18008e808  mov     al, 6
0x18008e80a  jmp     short loc_18008E83A
0x18008e80c  test    r14b, r14b
0x18008e80f  jns     short loc_18008E815
0x18008e811  mov     al, 3
0x18008e813  jmp     short loc_18008E83A
0x18008e815  test    r15d, r14d
0x18008e818  jz      short loc_18008E837
0x18008e81a  test    r13, r13
0x18008e81d  setnz   dl
0x18008e820  call    BasepIsRealtimeAllowed
0x18008e825  test    rax, rax
0x18008e828  setnz   al
0x18008e82b  add     al, 3
0x18008e82d  mov     rcx, [rsp+2238h+DebugObject]
0x18008e835  jmp     short loc_18008E83A
0x18008e837  mov     al, dil
0x18008e83a  mov     r15d, 2
0x18008e840  mov     [rsp+2238h+var_20BB], al
0x18008e847  mov     eax, [rsp+2238h+var_2148]
0x18008e84e  and     eax, 0FFFF3E1Fh
0x18008e853  mov     [rsp+2238h+var_2148], eax
0x18008e85a  bt      eax, 12h
0x18008e85e  jnb     short loc_18008E868
0x18008e860  or      [rsp+2238h+var_2140], 40h
0x18008e868  bt      eax, 18h
0x18008e86c  jnb     short loc_18008E875
0x18008e86e  or      [rsp+2238h+var_2140], esi
0x18008e875  bt      eax, 10h
0x18008e879  jnb     short loc_18008E884
0x18008e87b  bts     [rsp+2238h+var_2140], 8
0x18008e884  test    al, 4
0x18008e886  jnz     short loc_18008E891
0x18008e888  bts     [rsp+2238h+var_2140], 9
0x18008e891  test    al, 3
0x18008e893  jz      short loc_18008E8D5
0x18008e895  call    cs:__imp_DbgUiConnectToDbg
0x18008e89c  nop     dword ptr [rax+rax+00h]
0x18008e8a1  test    eax, eax
0x18008e8a3  jns     short loc_18008E8AC
0x18008e8a5  mov     ecx, eax
0x18008e8a7  jmp     loc_180096E44
0x18008e8ac  call    cs:__imp_DbgUiGetThreadDebugObject
0x18008e8b3  nop     dword ptr [rax+rax+00h]
0x18008e8b8  mov     rcx, rax
0x18008e8bb  mov     [rsp+2238h+DebugObject], rax
0x18008e8c3  test    byte ptr [rsp+2238h+var_2148], r15b
0x18008e8cb  jz      short loc_18008E8D5
0x18008e8cd  or      [rsp+2238h+var_2140], r15d
  ... truncated ...
```
