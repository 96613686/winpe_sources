# CFveApi::FveQueryWcosSecurityInfoImpl(_FVE_WCOS_SEQURITY_INFO_REQUEST *,_FVE_WCOS_SEQURITY_INFO_RESPONSE *)

- ea: `0x1800c2744`
- end: `0x1800c4463`
- name: `?FveQueryWcosSecurityInfoImpl@CFveApi@@SAJPEAU_FVE_WCOS_SEQURITY_INFO_REQUEST@@PEAU_FVE_WCOS_SEQURITY_INFO_RESPONSE@@@Z`
- size: `7455`
- prototype: `static int(struct _FVE_WCOS_SEQURITY_INFO_REQUEST *, struct _FVE_WCOS_SEQURITY_INFO_RESPONSE *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c25f8`

## callees

- `0x180006cc0`
- `0x180007780`
- `0x180007980`
- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x180009468`
- `0x18000ba30`
- `0x180019128`
- `0x1800205f0`
- `0x1800311dc`
- `0x180037edc`
- `0x180042448`
- `0x180045824`
- `0x180045ea0`
- `0x18004b050`
- `0x18005e368`
- `0x1800677f0`
- `0x180098cf8`
- `0x1800ab2f8`
- `0x1800c2744`
- `0x1800c8bec`
- `0x1800c8db0`
- `0x1800d19c0`
- `0x18011efc2`
- `0x18011efce`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800c3974`
- `msvcrt!_wcsicmp` at `0x1800c3974`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800c3673`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800c43dd`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180127035`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800c3673`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800c43dd`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180127035`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800c3324`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800c3324`
- `ntdll!NtQueryWnfStateData` at `0x1800c3128`
- `ntdll!NtQueryWnfStateData` at `0x1800c3493`
- `ntdll!NtQueryWnfStateData` at `0x1800c3128`
- `ntdll!NtQueryWnfStateData` at `0x1800c3493`
- `ntdll!NtQuerySystemInformation` at `0x1800c2c90`
- `ntdll!NtQuerySystemInformation` at `0x1800c2d8d`
- `ntdll!NtQuerySystemInformation` at `0x1800c2c90`
- `ntdll!NtQuerySystemInformation` at `0x1800c2d8d`
- `ntdll!RtlNtStatusToDosError` at `0x1800c2cd9`
- `ntdll!RtlNtStatusToDosError` at `0x1800c2e58`
- `ntdll!RtlNtStatusToDosError` at `0x1800c316f`
- `ntdll!RtlNtStatusToDosError` at `0x1800c336b`
- `ntdll!RtlNtStatusToDosError` at `0x1800c34de`
- `ntdll!RtlNtStatusToDosError` at `0x1800c2cd9`
- `ntdll!RtlNtStatusToDosError` at `0x1800c2e58`
- `ntdll!RtlNtStatusToDosError` at `0x1800c316f`
- `ntdll!RtlNtStatusToDosError` at `0x1800c336b`
- `ntdll!RtlNtStatusToDosError` at `0x1800c34de`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c33ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c33ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c3291`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c3291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c32a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c341e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c37d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c388a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c32a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c341e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c37d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c388a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4048`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c371c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180126fcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180127055`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c371c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180126fcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180127055`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800c4234`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800c4234`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c2bdb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c41c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c4280`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c2bdb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c41c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c4280`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800c36a8`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800c36a8`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800c4026`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800c4026`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800c43bd`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180127012`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800c43bd`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180127012`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c37a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c37a3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c3861`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c3861`

## string_xrefs

- `0x1800c29b3`: `DeviceEncryption-WindowsCore-PreInstalled`
- `0x1800c29a4`: `PREINSTALLED`

## pseudocode

```c
__int64 __fastcall CFveApi::FveQueryWcosSecurityInfoImpl(
        struct _FVE_WCOS_SEQURITY_INFO_REQUEST *a1,
        struct _FVE_WCOS_SEQURITY_INFO_RESPONSE *a2)
{
  int v4; // r12d
  __int64 v5; // rbx
  __int64 v6; // rcx
  PVOID *v7; // r10
  int v8; // esi
  unsigned __int64 v9; // rbx
  struct _FILETIME v10; // rdi
  NTSTATUS v11; // eax
  NTSTATUS v12; // esi
  signed int v13; // eax
  __int64 v14; // rdx
  NTSTATUS v15; // eax
  NTSTATUS v16; // esi
  PVOID *v17; // rcx
  signed int v18; // eax
  int SecureBootBindingState; // eax
  unsigned int v20; // r12d
  const WCHAR *v21; // r13
  __int64 v22; // rdx
  int v23; // eax
  NTSTATUS v24; // r12d
  signed int v25; // eax
  HANDLE EventW; // rax
  signed int v27; // eax
  int v28; // eax
  NTSTATUS v29; // r12d
  signed int v30; // eax
  _DWORD *v31; // r13
  DWORD v32; // edx
  void *v33; // r13
  DWORD v34; // eax
  signed int v35; // eax
  int v36; // eax
  NTSTATUS v37; // r12d
  signed int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rdx
  int v41; // r13d
  char *FirstVolumeW; // rcx
  BOOL k; // eax
  __int64 v44; // rax
  unsigned __int64 v45; // rcx
  HANDLE FileW; // rsi
  char LastError; // al
  int v48; // edx
  unsigned int v49; // esi
  _QWORD *v50; // rcx
  __int64 v51; // rdx
  int v52; // r12d
  __int64 v53; // rsi
  int LockObjectFromHandleImpl; // eax
  _QWORD *v55; // rcx
  int v56; // edx
  CFveApiBase *v57; // r13
  int v58; // eax
  _QWORD *v59; // rcx
  int v60; // edx
  PVOID *v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rdx
  __int64 v64; // rdx
  PVOID *v65; // r8
  __int64 v66; // rdx
  int v67; // eax
  __int64 v68; // rdx
  __int64 v69; // rdx
  int v70; // esi
  int v71; // eax
  _QWORD *v72; // rcx
  int v73; // edx
  __int64 v74; // r8
  signed int v75; // eax
  PVOID *v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // rdx
  bool v80; // [rsp+40h] [rbp-5F8h]
  HANDLE hHandle; // [rsp+48h] [rbp-5F0h]
  char v82; // [rsp+50h] [rbp-5E8h]
  int j; // [rsp+54h] [rbp-5E4h]
  __int64 hObject; // [rsp+58h] [rbp-5E0h]
  unsigned int v85; // [rsp+64h] [rbp-5D4h]
  struct _FILETIME v86; // [rsp+68h] [rbp-5D0h]
  unsigned __int64 v87; // [rsp+68h] [rbp-5D0h]
  unsigned int v88; // [rsp+70h] [rbp-5C8h]
  DWORD pdwValue; // [rsp+74h] [rbp-5C4h] BYREF
  unsigned int i; // [rsp+78h] [rbp-5C0h]
  struct _FILETIME v91; // [rsp+80h] [rbp-5B8h]
  void *lpMem; // [rsp+88h] [rbp-5B0h] BYREF
  unsigned __int64 v93; // [rsp+90h] [rbp-5A8h] BYREF
  CFveApiBase *v94; // [rsp+98h] [rbp-5A0h] BYREF
  __int64 v95; // [rsp+A0h] [rbp-598h] BYREF
  HANDLE hFindVolume; // [rsp+A8h] [rbp-590h]
  unsigned __int64 v97; // [rsp+B0h] [rbp-588h] BYREF
  int v98; // [rsp+B8h] [rbp-580h]
  __int64 v99; // [rsp+C0h] [rbp-578h] BYREF
  int v100; // [rsp+C8h] [rbp-570h] BYREF
  unsigned int v101; // [rsp+CCh] [rbp-56Ch] BYREF
  unsigned int v102; // [rsp+D0h] [rbp-568h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+D8h] [rbp-560h] BYREF
  unsigned int v104; // [rsp+E0h] [rbp-558h] BYREF
  int v105; // [rsp+E4h] [rbp-554h] BYREF
  ULONG ReturnLength; // [rsp+E8h] [rbp-550h] BYREF
  _DWORD SystemInformation[8]; // [rsp+F0h] [rbp-548h] BYREF
  int v108; // [rsp+110h] [rbp-528h] BYREF
  __int128 v109; // [rsp+114h] [rbp-524h]
  unsigned int v110; // [rsp+124h] [rbp-514h]
  char OutBuffer[32]; // [rsp+130h] [rbp-508h] BYREF
  _BYTE Buf1[40]; // [rsp+150h] [rbp-4E8h] BYREF
  wchar_t String1[36]; // [rsp+178h] [rbp-4C0h] BYREF
  int v114; // [rsp+1C0h] [rbp-478h]
  GUID v115; // [rsp+1C4h] [rbp-474h] BYREF
  wchar_t *String2; // [rsp+1D8h] [rbp-460h]
  PCWSTR pwszValueName[2]; // [rsp+1E0h] [rbp-458h]
  _DWORD v118[3]; // [rsp+1F0h] [rbp-448h]
  GUID v119; // [rsp+1FCh] [rbp-43Ch]
  const wchar_t *v120; // [rsp+210h] [rbp-428h]
  const wchar_t *v121; // [rsp+218h] [rbp-420h]
  __int64 v122; // [rsp+220h] [rbp-418h]
  int v123; // [rsp+228h] [rbp-410h]
  int v124; // [rsp+230h] [rbp-408h]
  GUID v125; // [rsp+234h] [rbp-404h]
  const wchar_t *v126; // [rsp+248h] [rbp-3F0h]
  const wchar_t *v127; // [rsp+250h] [rbp-3E8h]
  __int64 v128; // [rsp+258h] [rbp-3E0h]
  int v129; // [rsp+260h] [rbp-3D8h]
  int v130; // [rsp+268h] [rbp-3D0h]
  GUID v131; // [rsp+26Ch] [rbp-3CCh]
  const wchar_t *v132; // [rsp+280h] [rbp-3B8h]
  const wchar_t *v133; // [rsp+288h] [rbp-3B0h]
  int v134; // [rsp+290h] [rbp-3A8h]
  __int64 v135; // [rsp+294h] [rbp-3A4h]
  int v136; // [rsp+2A0h] [rbp-398h]
  GUID v137; // [rsp+2A4h] [rbp-394h]
  const wchar_t *v138; // [rsp+2B8h] [rbp-380h]
  const wchar_t *v139; // [rsp+2C0h] [rbp-378h]
  __int64 v140; // [rsp+2C8h] [rbp-370h]
  int v141; // [rsp+2D0h] [rbp-368h]
  int v142; // [rsp+2D8h] [rbp-360h]
  GUID v143; // [rsp+2DCh] [rbp-35Ch]
  const wchar_t *v144; // [rsp+2F0h] [rbp-348h]
  const wchar_t *v145; // [rsp+2F8h] [rbp-340h]
  int v146; // [rsp+300h] [rbp-338h]
  __int64 v147; // [rsp+304h] [rbp-334h]
  int v148; // [rsp+310h] [rbp-328h]
  GUID v149; // [rsp+314h] [rbp-324h]
  const wchar_t *v150; // [rsp+328h] [rbp-310h]
  const wchar_t *v151; // [rsp+330h] [rbp-308h]
  __int64 v152; // [rsp+338h] [rbp-300h]
  int v153; // [rsp+340h] [rbp-2F8h]
  int v154; // [rsp+348h] [rbp-2F0h]
  __int128 v155; // [rsp+34Ch] [rbp-2ECh]
  const wchar_t *v156; // [rsp+360h] [rbp-2D8h]
  const wchar_t *v157; // [rsp+368h] [rbp-2D0h]
  __int64 v158; // [rsp+370h] [rbp-2C8h]
  int v159; // [rsp+378h] [rbp-2C0h]
  int v160; // [rsp+380h] [rbp-2B8h]
  __int128 v161; // [rsp+384h] [rbp-2B4h]
  const wchar_t *v162; // [rsp+398h] [rbp-2A0h]
  const wchar_t *v163; // [rsp+3A0h] [rbp-298h]
  __int64 v164; // [rsp+3A8h] [rbp-290h]
  int v165; // [rsp+3B0h] [rbp-288h]
  int v166; // [rsp+3B8h] [rbp-280h]
  __int128 v167; // [rsp+3BCh] [rbp-27Ch]
  const wchar_t *v168; // [rsp+3D0h] [rbp-268h]
  const wchar_t *v169; // [rsp+3D8h] [rbp-260h]
  __int64 v170; // [rsp+3E0h] [rbp-258h]
  int v171; // [rsp+3E8h] [rbp-250h]
  WCHAR szVolumeName[264]; // [rsp+3F0h] [rbp-248h] BYREF

  lpMem = a1;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v108 = 0;
  v109 = 0;
  v110 = 0;
  ReturnLength = 24;
  v4 = 0;
  v104 = -1;
  pdwValue = 0;
  hHandle = 0;
  v100 = -1;
  v105 = 4;
  v102 = 0;
  v99 = 0;
  hFindVolume = (HANDLE)-1LL;
  v5 = -1;
  hObject = -1;
  v95 = 0;
  v94 = 0;
  v101 = 0;
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(OutBuffer, 0, 0x90u);
  v80 = 0;
  v82 = 0;
  SystemTimeAsFileTime = 0;
  v91 = 0;
  v93 = 0;
  v88 = 0;
  v114 = 0;
  v115 = PARTITION_MAIN_OS_GUID;
  String2 = L"MAINOS";
  pwszValueName[0] = L"DeviceEncryption-WindowsCore-OSMain";
  pwszValueName[1] = (PCWSTR)1;
  v118[0] = 0;
  v118[2] = 1;
  v119 = PARTITION_BSP_GUID;
  v120 = L"BSP";
  v121 = L"DeviceEncryption-WindowsCore-BSP";
  v122 = 0;
  v123 = 0;
  v124 = 2;
  v125 = PARTITION_WINDOWS_SYSTEM_GUID;
  v126 = L"WSP";
  v127 = L"DeviceEncryption-WindowsCore-WSP";
  v128 = 0;
  v129 = 0;
  v130 = 3;
  v131 = PARTITION_OS_DATA_GUID;
  v132 = L"OSDATA";
  v133 = L"DeviceEncryption-WindowsCore-OSData";
  v134 = 0;
  v135 = 1;
  v136 = 4;
  v137 = PARTITION_PRE_INSTALLED_GUID;
  v138 = L"PREINSTALLED";
  v139 = L"DeviceEncryption-WindowsCore-PreInstalled";
  v140 = 0;
  v141 = 0;
  v142 = 5;
  v143 = PARTITION_BASIC_DATA_GUID;
  v144 = L"DATA";
  v145 = L"DeviceEncryption-WindowsCore-UserData";
  v146 = 0;
  v147 = 1;
  v148 = 6;
  v149 = PARTITION_DPP_GUID;
  v150 = L"DPP";
  v151 = L"DeviceEncryption-WindowsCore-DPP";
  v152 = 0;
  v153 = 0;
  v154 = 7;
  v155 = PARTITION_SERVICING_METADATA_GUID;
  v156 = L"SERVICING_METADATA";
  v157 = L"DeviceEncryption-WindowsCore-ServicingMetadata";
  v158 = 0;
  v159 = 0;
  v160 = 8;
  v161 = PARTITION_SERVICING_FILES_GUID;
  v162 = L"SERVICING_FILES";
  v163 = L"DeviceEncryption-WindowsCore-ServicingFiles";
  v164 = 0;
  v165 = 0;
  v166 = 9;
  v167 = PARTITION_SERVICING_RESERVE_GUID;
  v168 = L"RESERVE";
  v169 = L"DeviceEncryption-WindowsCore-ServicingReserve";
  v170 = 0;
  v171 = 0;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v8 = -2147024809;
    goto LABEL_383;
  }
  if ( !a2 )
  {
    v8 = -2147467261;
    goto LABEL_383;
  }
  memset_0(a2, 0, 0x40u);
  *((_WORD *)a2 + 1) = 64;
  if ( *(_WORD *)a1 >= 2u )
  {
    v80 = *((_BYTE *)a1 + 8) != 0;
    if ( *((_BYTE *)a1 + 9) )
    {
      v82 = 1;
    }
    else
    {
      v82 = 0;
      v80 = *((_BYTE *)a1 + 8) != 0;
    }
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v86 = SystemTimeAsFileTime;
  if ( *((_DWORD *)a1 + 1) == -1 )
  {
    v9 = -1;
    v93 = -1;
    v10 = SystemTimeAsFileTime;
  }
  else
  {
    v8 = ULongLongMult(*((unsigned int *)a1 + 1), 0x2710u, &v93);
    if ( v8 < 0
      || ((v10 = v86, v9 = v93 + *(_QWORD *)&v86, v93 + *(_QWORD *)&v86 < *(_QWORD *)&v86)
        ? (v9 = -1, v8 = -2147024362)
        : (v8 = 0),
          v93 = v9,
          v8 < 0) )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      v5 = -1;
      goto LABEL_383;
    }
  }
  v11 = NtQuerySystemInformation(SystemBootEnvironmentInformation, SystemInformation, 0x20u, 0);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        168,
        &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
        (unsigned int)v11);
    v13 = RtlNtStatusToDosError(v12);
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_381;
    v14 = 169;
LABEL_28:
    WPP_SF_d(v7[2], v14, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, (unsigned int)v8);
    v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_29:
    v5 = hObject;
    goto LABEL_383;
  }
  if ( SystemInformation[4] != 2
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      170,
      &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
      SystemInformation[4]);
  }
  v15 = NtQuerySystemInformation(SystemNonPagedPoolInformation|0x80, &v108, 0x18u, &ReturnLength);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( v15 == -2143092730 )
    {
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      v16 = 0;
      goto LABEL_46;
    }
LABEL_45:
    v17 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( (v110 & 0x10) == 0 )
  {
    v4 = 1;
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v110);
    goto LABEL_45;
  }
LABEL_46:
  if ( v16 < 0 )
  {
    if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 2) != 0 )
      WPP_SF_d(v17[2], 173, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, (unsigned int)v16);
    v18 = RtlNtStatusToDosError(v16);
    v8 = v18;
    if ( v18 > 0 )
      v8 = (unsigned __int16)v18 | 0x80070000;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_381;
    v14 = 174;
    goto LABEL_28;
  }
  SecureBootBindingState = FveGetSecureBootBindingState(&v104);
  v8 = SecureBootBindingState;
  if ( SecureBootBindingState < 0 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_381;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      175,
      &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
      (unsigned int)SecureBootBindingState);
    goto LABEL_59;
  }
  v6 = v104;
  if ( v104 - 2 <= 1 )
    goto LABEL_64;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v104);
    v6 = v104;
LABEL_64:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( SystemInformation[4] != 2 )
    goto LABEL_381;
  if ( v4 && (unsigned int)(v6 - 2) <= 1 )
  {
    *((_BYTE *)a2 + 5) = 1;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( SystemInformation[4] != 2 )
    goto LABEL_381;
  v20 = 0;
  for ( i = 0; ; i = v20 )
  {
    if ( v20 >= 0xA )
    {
      if ( !*((_QWORD *)a2 + 1) && !*((_QWORD *)a2 + 6) )
      {
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
        {
          WPP_SF_(v7[2], 179, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        v8 = 1;
        goto LABEL_29;
      }
      v23 = NtQueryWnfStateData(&WNF_FVE_DETASK_SYNC_PROVISIONING_COMPLETE, 0, 0, &v102, &v100, &v105);
      v24 = v23;
      if ( v23 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            180,
            &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
            (unsigned int)v23);
        v25 = RtlNtStatusToDosError(v24);
        v8 = v25;
        if ( v25 > 0 )
          v8 = (unsigned __int16)v25 | 0x80070000;
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_381;
        v14 = 181;
        goto LABEL_28;
      }
      if ( !v102 )
      {
        v100 = -1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
      }
      if ( !v100 )
      {
        *((_BYTE *)a2 + 6) = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
      }
      if ( v100 == 1 )
      {
        *((_BYTE *)a2 + 6) = 1;
        if ( !v80 )
          *((_BYTE *)a2 + 7) = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
LABEL_183:
        v41 = 0;
        for ( j = 0; ; j = v41 )
        {
          v85 = 0;
          FirstVolumeW = (char *)FindFirstVolumeW(szVolumeName, 0x104u);
          hFindVolume = FirstVolumeW;
          for ( k = FirstVolumeW + 1 != 0; k; k = FindNextVolumeW(hFindVolume, szVolumeName, 0x104u) )
          {
            if ( v94 )
            {
              CFveApiHandle::ReleaseLockedObjectImpl(FirstVolumeW, v94);
              v94 = 0;
            }
            if ( v95 )
            {
              FveCloseHandle(v95);
              v95 = 0;
            }
            if ( hObject != -1 )
              CloseHandle((HANDLE)hObject);
            while ( 1 )
            {
              v44 = -1;
              do
                ++v44;
              while ( szVolumeName[v44] );
              if ( !v44 || szVolumeName[v44 - 1] != 92 && szVolumeName[v44 - 1] != 47 )
                break;
              v45 = 2 * v44 - 2;
              if ( v45 >= 0x208 )
                _report_rangecheckfailure();
              *(WCHAR *)((char *)szVolumeName + v45) = 0;
            }
            FileW = CreateFileW(szVolumeName, 0, 3u, 0, 3u, 0, 0);
            hObject = (__int64)FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                continue;
              LastError = GetLastError();
              v48 = 197;
              goto LABEL_204;
            }
            memset_0(OutBuffer, 0, 0x90u);
            if ( !DeviceIoControl(FileW, 0x70048u, 0, 0, OutBuffer, 0x90u, &ReturnLength, 0) )
            {
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                continue;
              LastError = GetLastError();
              v48 = 198;
LABEL_204:
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v48,
                (unsigned int)&WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
                (unsigned int)szVolumeName,
                LastError);
              continue;
            }
            if ( *(_DWORD *)OutBuffer != 1 )
            {
              if ( !v41 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_SD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  199,
                  (unsigned int)&WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
                  (unsigned int)szVolumeName,
                  OutBuffer[0]);
              continue;
            }
            v49 = 0;
            i = 0;
            while ( v49 < 0xA )
            {
              if ( memcmp_0(Buf1, &PARTITION_BASIC_DATA_GUID, 0x10u) && !memcmp_0(Buf1, (char *)&v115 + 56 * v49, 0x10u)
                || !_wcsicmp(String1, pwszValueName[7 * v49 - 1]) )
              {
                v87 = 56LL * v49;
                v52 = *(int *)((char *)&v114 + v87);
                v53 = 1LL << v52;
                if ( ((1LL << v52) & *((_QWORD *)a2 + 1)) == 0 && (v53 & *((_QWORD *)a2 + 6)) == 0 )
                {
                  if ( !v41 )
                  {
                    v50 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      v51 = 201;
                      goto LABEL_227;
                    }
                  }
                  goto LABEL_341;
                }
                LockObjectFromHandleImpl = FveOpenVolumeByHandle((HANDLE)hObject, 1, (__int64)&v95);
                if ( LockObjectFromHandleImpl < 0 )
                {
                  v55 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                    goto LABEL_341;
                  v56 = 202;
                  goto LABEL_238;
                }
                LockObjectFromHandleImpl = CFveApiHandle::GetLockObjectFromHandleImpl(2, v95, &v94);
                if ( LockObjectFromHandleImpl < 0 )
                {
                  v55 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                    goto LABEL_341;
                  v56 = 203;
LABEL_238:
                  WPP_SF_Sd(
                    v55[2],
                    v56,
                    (unsigned int)&WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
                    (unsigned int)szVolumeName,
                    LockObjectFromHandleImpl);
                  goto LABEL_341;
                }
                v57 = v94;
                CFveApiBase::ResolveVolumeMountName(v94);
                v101 = 0;
                v97 = 0;
                v58 = CFveApiBase::SetFlagsBasedOnState(v57, &v101);
                if ( v58 < 0 )
                {
                  v59 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v60 = 204;
                    goto LABEL_248;
                  }
                  goto LABEL_340;
                }
                v58 = CFveApiBase::SetExtendedFlagsBasedOnState(v57, v101, &v97);
                if ( v58 < 0 )
                {
                  v59 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v60 = 205;
LABEL_248:
                    WPP_SF_Sd(
                      v59[2],
                      v60,
                      (unsigned int)&WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
                      (unsigned int)szVolumeName,
                      v58);
                  }
                  goto LABEL_340;
                }
                if ( (v53 & *((_QWORD *)a2 + 7)) == 0 && (v53 & *((_QWORD *)a2 + 6)) != 0 )
                {
                  v61 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    WPP_SF_S(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      206,
                      &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
                      *((_QWORD *)v57 + 49));
                    v61 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( (*((_BYTE *)v57 + 108) & 8) != 0 )
                  {
                    *((_QWORD *)a2 + 7) |= 1LL << v52;
                    v61 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      v62 = 207;
                      goto LABEL_263;
                    }
LABEL_265:
                    if ( (v53 & *((_QWORD *)a2 + 1)) == 0 )
                      goto LABEL_340;
                    if ( (v53 & *((_QWORD *)a2 + 2)) == 0 )
                    {
                      if ( v61 != &WPP_GLOBAL_Control && (*((_BYTE *)v61 + 28) & 8) != 0 )
                      {
                        WPP_SF_S(v61[2], 209, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, *((_QWORD *)v57 + 49));
                        v61 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( (v101 & 1) != 0 )
                      {
                        *((_QWORD *)a2 + 2) |= 1LL << v52;
                        v61 = (PVOID *)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                        {
                          v63 = 210;
                          goto LABEL_282;
                        }
                      }
                      else if ( !j && v61 != &WPP_GLOBAL_Control && (*((_BYTE *)v61 + 28) & 4) != 0 )
                      {
                        v63 = 211;
LABEL_282:
                        WPP_SF_S(v61[2], v63, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, *((_QWORD *)v57 + 49));
                        v61 = (PVOID *)WPP_GLOBAL_Control;
                      }
                    }
                    if ( (v53 & *((_QWORD *)a2 + 3)) != 0 )
                    {
                      ++v85;
                    }
                    else if ( (v101 & 8) != 0 || !v80 && (v97 & 0x40) != 0 )
                    {
                      if ( v61 != &WPP_GLOBAL_Control && (*((_BYTE *)v61 + 28) & 8) != 0 )
                        WPP_SF_S(v61[2], 212, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, *((_QWORD *)v57 + 49));
                      ++v85;
                      *((_QWORD *)a2 + 3) |= 1LL << v52;
LABEL_294:
                      v61 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    else if ( v61 != &WPP_GLOBAL_Control && (*((_BYTE *)v61 + 28) & 4) != 0 )
                    {
                      WPP_SF_S(v61[2], 213, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, *((_QWORD *)v57 + 49));
                      goto LABEL_294;
                    }
                    v64 = *((_QWORD *)a2 + 4);
                    if ( (v53 & v64) != 0 )
                      goto LABEL_302;
                    if ( (v101 & 0x401) == 1 )
                    {
                      *((_QWORD *)a2 + 4) = v64 | (1LL << v52);
                      v61 = (PVOID *)WPP_GLOBAL_Control;
                      v65 = &WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      {
                        v66 = 214;
                        goto LABEL_301;
                      }
                      v67 = j;
LABEL_304:
                      v68 = *((_QWORD *)a2 + 5);
                      if ( (v53 & v68) == 0 )
                      {
                        if ( (v101 & 0x40000) != 0 )
                        {
                          if ( !v67 && v61 != &WPP_GLOBAL_Control && (*((_BYTE *)v61 + 28) & 4) != 0 )
                          {
                            v69 = 217;
LABEL_318:
                            WPP_SF_S(
                              v61[2],
                              v69,
                              &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
                              *((_QWORD *)v57 + 49));
                            v61 = (PVOID *)WPP_GLOBAL_Control;
                          }
                        }
                        else
                        {
                          *((_QWORD *)a2 + 5) = v68 | (1LL << v52);
                          v61 = (PVOID *)WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                          {
                            v69 = 216;
                            goto LABEL_318;
                          }
                        }
                      }
                      if ( (v53 & *((_QWORD *)a2 + 1)) == 0 || v82 != 1 || v118[v87 / 4] )
                        goto LABEL_340;
                      v70 = 0;
                      if ( !*((_BYTE *)v57 + 1158) )
                      {
                        lpMem = 0;
                        v70 = CFveApi::ReopenWritable(v57, (unsigned __int16 **)&lpMem);
                        if ( lpMem )
                        {
                          CFveApiBase::FastFree(lpMem);
                          lpMem = 0;
                        }
                        v61 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v70 < 0 )
                      {
                        if ( v61 != &WPP_GLOBAL_Control && (*((_BYTE *)v61 + 28) & 4) != 0 )
                          WPP_SF_Sd(
                            (unsigned int)v61[2],
                            218,
                            (unsigned int)&WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
                            (unsigned int)pwszValueName[v87 / 8 - 1],
                            v70);
                        goto LABEL_340;
                      }
                      v71 = (*(__int64 (__fastcall **)(CFveApiBase *, _QWORD, PVOID *))(*(_QWORD *)v57 + 264LL))(
                              v57,
                              0,
                              v65);
                      if ( v71 >= 0 )
                      {
                        v71 = CFveApi::ConversionEncryptEx(v57, 0x21u);
                        if ( v71 >= 0 )
                        {
                          v118[v87 / 4] = 1;
                          goto LABEL_340;
                        }
                        v72 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                          goto LABEL_340;
                        v73 = 220;
                      }
                      else
                      {
                        v72 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                          goto LABEL_340;
                        v73 = 219;
                      }
                      WPP_SF_Sd(
                        v72[2],
                        v73,
                        (unsigned int)&WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
                        (unsigned int)pwszValueName[v87 / 8 - 1],
                        v71);
LABEL_340:
                      v41 = j;
                      goto LABEL_341;
                    }
                    v67 = j;
                    if ( !j )
                    {
                      v65 = &WPP_GLOBAL_Control;
                      if ( v61 == &WPP_GLOBAL_Control || (*((_BYTE *)v61 + 28) & 4) == 0 )
                        goto LABEL_304;
                      v66 = 215;
LABEL_301:
                      WPP_SF_S(v61[2], v66, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, *((_QWORD *)v57 + 49));
                      v61 = (PVOID *)WPP_GLOBAL_Control;
LABEL_302:
                      v67 = j;
                    }
                    v65 = &WPP_GLOBAL_Control;
                    goto LABEL_304;
                  }
                  if ( j || v61 == &WPP_GLOBAL_Control || (*((_BYTE *)v61 + 28) & 4) == 0 )
                    goto LABEL_265;
                  v62 = 208;
LABEL_263:
                  WPP_SF_S(v61[2], v62, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, *((_QWORD *)v57 + 49));
                }
                v61 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_265;
              }
              i = ++v49;
            }
            if ( !v41 )
            {
              v50 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v51 = 200;
LABEL_227:
                WPP_SF_S(v50[2], v51, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, szVolumeName);
                continue;
              }
            }
LABEL_341:
            ;
          }
          if ( GetLastError() != 18 )
          {
            v75 = GetLastError();
            v8 = v75;
            if ( v75 > 0 )
              v8 = (unsigned __int16)v75 | 0x80070000;
            v7 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v14 = 221;
              goto LABEL_28;
            }
            goto LABEL_381;
          }
          if ( !v80 )
          {
            v76 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_358;
          }
          if ( v85 > v88 )
            break;
          if ( v85 == v88 )
          {
            *((_BYTE *)a2 + 7) = 1;
            v76 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v85);
              goto LABEL_357;
            }
            goto LABEL_358;
          }
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          v91 = SystemTimeAsFileTime;
          if ( *(_QWORD *)&SystemTimeAsFileTime > v9 )
          {
            v76 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                224,
                &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
                v85,
                v88);
LABEL_357:
              v76 = (PVOID *)WPP_GLOBAL_Control;
            }
LABEL_358:
            if ( *((_BYTE *)a2 + 5)
              && (v77 = *((_QWORD *)a2 + 1), v77 == (v77 & *((_QWORD *)a2 + 2)))
              && v77 == (v77 & *((_QWORD *)a2 + 3))
              && v77 == (v77 & *((_QWORD *)a2 + 4))
              && v77 == (v77 & *((_QWORD *)a2 + 5))
              && *((_QWORD *)a2 + 6) == (*((_QWORD *)a2 + 6) & *((_QWORD *)a2 + 7)) )
            {
              *((_BYTE *)a2 + 4) = 1;
              v76 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v78 = 225;
                goto LABEL_376;
              }
            }
            else if ( v76 != &WPP_GLOBAL_Control && (*((_BYTE *)v76 + 28) & 8) != 0 )
            {
              v78 = 226;
LABEL_376:
              WPP_SF_(v76[2], v78, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
            }
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            v91 = SystemTimeAsFileTime;
            v7 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_II(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                227,
                &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
                (*(_QWORD *)&v91 - *(_QWORD *)&v10) / 0x989680uLL);
              v7 = (PVOID *)WPP_GLOBAL_Control;
            }
            v8 = 0;
            v5 = hObject;
            goto LABEL_383;
          }
          Sleep(0x1F4u);
          ++v41;
        }
        v8 = -2147418113;
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_LLd(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, v74, v85, v88, -2147418113);
          goto LABEL_59;
        }
LABEL_381:
        v33 = hHandle;
        goto LABEL_155;
      }
      EventW = CreateEventW(0, 1, 0, 0);
      hHandle = EventW;
      if ( !EventW )
      {
        v27 = GetLastError();
        v8 = v27;
        if ( v27 > 0 )
          v8 = (unsigned __int16)v27 | 0x80070000;
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_381;
        v14 = 185;
        goto LABEL_28;
      }
      v28 = RtlSubscribeWnfStateChangeNotification(
              &v99,
              WNF_FVE_DETASK_SYNC_PROVISIONING_COMPLETE,
              v102,
              CFveApiBase::FveDeSyncCompletionChangeCallback,
              EventW,
              0,
              0,
              0);
      v29 = v28;
      if ( v28 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            186,
            &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
            (unsigned int)v28);
        v30 = RtlNtStatusToDosError(v29);
        v8 = v30;
        if ( v30 > 0 )
          v8 = (unsigned __int16)v30 | 0x80070000;
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_381;
        v14 = 187;
        goto LABEL_28;
      }
      v31 = lpMem;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          188,
          &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
          *((unsigned int *)lpMem + 1));
      v32 = v31[1];
      v33 = hHandle;
      v34 = WaitForSingleObject(hHandle, v32);
      if ( !v34 )
      {
        *((_BYTE *)a2 + 6) = 1;
        if ( !v80 )
          *((_BYTE *)a2 + 7) = 1;
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_178;
        v40 = 189;
LABEL_176:
        WPP_SF_(v7[2], v40, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
LABEL_177:
        v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_178:
        if ( v8 >= 0 )
        {
          RtlUnsubscribeWnfStateChangeNotification(v99);
          v99 = 0;
          goto LABEL_183;
        }
        if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 2) == 0 )
        {
LABEL_155:
          v5 = hObject;
          goto LABEL_384;
        }
        v39 = 196;
LABEL_154:
        WPP_SF_d(v7[2], v39, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, (unsigned int)v8);
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_155;
      }
      if ( v34 != 258 )
      {
        if ( v34 == -1 )
        {
          v35 = GetLastError();
          v8 = v35;
          if ( v35 > 0 )
            v8 = (unsigned __int16)v35 | 0x80070000;
        }
        else
        {
          v8 = -2147418113;
        }
        goto LABEL_177;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
      v36 = NtQueryWnfStateData(&WNF_FVE_DETASK_SYNC_PROVISIONING_COMPLETE, 0, 0, &v102, &v100, &v105);
      v37 = v36;
      if ( v36 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            191,
            &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
            (unsigned int)v36);
        v38 = RtlNtStatusToDosError(v37);
        v8 = v38;
        if ( v38 > 0 )
          v8 = (unsigned __int16)v38 | 0x80070000;
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_155;
        v39 = 192;
        goto LABEL_154;
      }
      if ( !v102 )
      {
        v100 = -1;
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_161;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_161:
      if ( !v100 )
      {
        *((_BYTE *)a2 + 6) = 1;
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      if ( v100 != 1 )
        goto LABEL_178;
      *((_BYTE *)a2 + 6) = 1;
      if ( !v80 )
        *((_BYTE *)a2 + 7) = 1;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_178;
      v40 = 195;
      goto LABEL_176;
    }
    v21 = pwszValueName[7 * v20];
    v8 = SLGetWindowsInformationDWORD(v21, &pdwValue);
    if ( ((v8 + 1073418222) & 0xFFFFFFFB) != 0 )
      break;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        177,
        (unsigned int)&WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
        (_DWORD)v21,
        v8);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = 0;
LABEL_87:
    ++v20;
  }
  if ( v8 >= 0 )
  {
    if ( (pdwValue & 1) != 0 )
    {
      v98 = ++v88;
      v22 = 56LL * v20;
      v6 = *((_QWORD *)a2 + 1);
      _bittestandset64(&v6, *(unsigned int *)((char *)&v114 + v22));
      *((_QWORD *)a2 + 1) = v6;
    }
    else
    {
      v22 = 56LL * v20;
    }
    if ( (pdwValue & 2) != 0 )
    {
      v6 = *((_QWORD *)a2 + 6);
      _bittestandset64(&v6, *(unsigned int *)((char *)&v114 + v22));
      *((_QWORD *)a2 + 6) = v6;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_87;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    goto LABEL_381;
  WPP_SF_Sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    178,
    (unsigned int)&WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
    (_DWORD)v21,
    v8);
LABEL_59:
  v7 = (PVOID *)WPP_GLOBAL_Control;
  v5 = hObject;
LABEL_383:
  v33 = hHandle;
LABEL_384:
  if ( v5 != -1 )
  {
    CloseHandle((HANDLE)v5);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v94 )
  {
    CFveApiHandle::ReleaseLockedObjectImpl(v6, v94);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v95 )
  {
    FveCloseHandle(v95);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hFindVolume != (HANDLE)-1LL )
  {
    FindVolumeClose(hFindVolume);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v99 )
  {
    RtlUnsubscribeWnfStateChangeNotification(v99);
    v99 = 0;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v33 )
  {
    CloseHandle(v33);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_d(v7[2], 228, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c2744  mov     r11, rsp
0x1800c2747  mov     [r11+18h], rbx
0x1800c274b  mov     [r11+20h], rsi
0x1800c274f  push    rdi
0x1800c2750  push    r12
0x1800c2752  push    r13
0x1800c2754  push    r14
0x1800c2756  push    r15
0x1800c2758  sub     rsp, 610h
0x1800c275f  mov     rax, cs:__security_cookie
0x1800c2766  xor     rax, rsp
0x1800c2769  mov     [rsp+638h+var_38], rax
0x1800c2771  mov     r15, rdx
0x1800c2774  mov     r13, rcx
0x1800c2777  mov     [rsp+638h+lpMem], rcx
0x1800c277f  xor     edi, edi
0x1800c2781  mov     [rsp+638h+SystemInformation], edi
0x1800c2788  xorps   xmm0, xmm0
0x1800c278b  xor     eax, eax
0x1800c278d  movups  xmmword ptr [rsp+638h+var_544], xmm0
0x1800c2795  movups  xmmword ptr [rsp+638h+var_544+0Ch], xmm0
0x1800c279d  mov     [rsp+638h+var_528], edi
0x1800c27a4  movups  [rsp+638h+var_524], xmm0
0x1800c27ac  mov     [rsp+638h+var_514], eax
0x1800c27b3  mov     [rsp+638h+ReturnLength], 18h
0x1800c27be  mov     r12d, edi
0x1800c27c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c27c5  mov     [rsp+638h+var_558], eax
0x1800c27cc  mov     [rsp+638h+pdwValue], edi
0x1800c27d0  mov     [rsp+638h+hHandle], rdi
0x1800c27d5  mov     [rsp+638h+var_570], 0FFFFFFFFh
0x1800c27e0  lea     r14d, [rdi+4]
0x1800c27e4  mov     [r11-554h], r14d
0x1800c27eb  mov     [rsp+638h+var_568], edi
0x1800c27f2  mov     [r11-578h], rdi
0x1800c27f9  mov     [r11-590h], rax
0x1800c2800  mov     rbx, rax
0x1800c2803  mov     [rsp+638h+hObject], rax
0x1800c2808  mov     [r11-598h], rdi
0x1800c280f  mov     [r11-5A0h], rdi
0x1800c2816  mov     [rsp+638h+var_56C], edi
0x1800c281d  xor     edx, edx; Val
0x1800c281f  mov     r8d, 208h; Size
0x1800c2825  lea     rcx, [r11-248h]; void *
0x1800c282c  call    memset_0
0x1800c2831  xor     edx, edx; Val
0x1800c2833  mov     r8d, 90h; Size
0x1800c2839  lea     rcx, [rsp+638h+OutBuffer]; void *
0x1800c2841  call    memset_0
0x1800c2846  mov     [rsp+638h+var_5F8], dil
0x1800c284b  mov     [rsp+638h+var_5E8], dil
0x1800c2850  mov     qword ptr [rsp+638h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800c2858  mov     [rsp+638h+var_5B8], rdi
0x1800c2860  mov     [rsp+638h+var_5D0], rdi
0x1800c2865  mov     [rsp+638h+var_5A8], rdi
0x1800c286d  mov     [rsp+638h+var_5C8], edi
0x1800c2871  mov     [rsp+638h+var_478], edi
0x1800c2878  movups  xmm0, xmmword ptr cs:PARTITION_MAIN_OS_GUID.Data1
0x1800c287f  movdqu  [rsp+638h+var_474], xmm0
0x1800c2888  lea     rax, aMainos; "MAINOS"
0x1800c288f  mov     [rsp+638h+String2], rax
0x1800c2897  lea     rax, aDeviceencrypti_6; "DeviceEncryption-WindowsCore-OSMain"
0x1800c289e  mov     [rsp+638h+pwszValueName], rax
0x1800c28a6  lea     esi, [rdi+1]
0x1800c28a9  mov     [rsp+638h+var_450], rsi
0x1800c28b1  mov     [rsp+638h+var_448], edi
0x1800c28b8  mov     [rsp+638h+var_440], esi
0x1800c28bf  movups  xmm0, xmmword ptr cs:PARTITION_BSP_GUID.Data1
0x1800c28c6  movdqu  [rsp+638h+var_43C], xmm0
0x1800c28cf  lea     rax, aBsp; "BSP"
0x1800c28d6  mov     [rsp+638h+var_428], rax
0x1800c28de  lea     rax, aDeviceencrypti_3; "DeviceEncryption-WindowsCore-BSP"
0x1800c28e5  mov     [rsp+638h+var_420], rax
0x1800c28ed  mov     [rsp+638h+var_418], rdi
0x1800c28f5  mov     [rsp+638h+var_410], edi
0x1800c28fc  mov     [rsp+638h+var_408], 2
0x1800c2907  movups  xmm0, xmmword ptr cs:PARTITION_WINDOWS_SYSTEM_GUID.Data1
0x1800c290e  movdqu  [rsp+638h+var_404], xmm0
0x1800c2917  lea     rax, aWsp; "WSP"
0x1800c291e  mov     [rsp+638h+var_3F0], rax
0x1800c2926  lea     rax, aDeviceencrypti_1; "DeviceEncryption-WindowsCore-WSP"
0x1800c292d  mov     [rsp+638h+var_3E8], rax
0x1800c2935  mov     [rsp+638h+var_3E0], rdi
0x1800c293d  mov     [rsp+638h+var_3D8], edi
0x1800c2944  mov     [rsp+638h+var_3D0], 3
0x1800c294f  movups  xmm0, xmmword ptr cs:PARTITION_OS_DATA_GUID.Data1
0x1800c2956  movdqu  [rsp+638h+var_3CC], xmm0
0x1800c295f  lea     rax, aOsdata; "OSDATA"
0x1800c2966  mov     [rsp+638h+var_3B8], rax
0x1800c296e  lea     rax, aDeviceencrypti; "DeviceEncryption-WindowsCore-OSData"
0x1800c2975  mov     [rsp+638h+var_3B0], rax
0x1800c297d  mov     [rsp+638h+var_3A8], edi
0x1800c2984  mov     [rsp+638h+var_3A4], rsi
0x1800c298c  mov     [rsp+638h+var_398], r14d
0x1800c2994  movups  xmm0, xmmword ptr cs:PARTITION_PRE_INSTALLED_GUID.Data1
0x1800c299b  movdqu  [rsp+638h+var_394], xmm0
0x1800c29a4  lea     rax, aPreinstalled; "PREINSTALLED"
0x1800c29ab  mov     [rsp+638h+var_380], rax
0x1800c29b3  lea     rax, aDeviceencrypti_4; "DeviceEncryption-WindowsCore-PreInstall"...
0x1800c29ba  mov     [rsp+638h+var_378], rax
0x1800c29c2  mov     [rsp+638h+var_370], rdi
0x1800c29ca  mov     [rsp+638h+var_368], edi
0x1800c29d1  mov     [rsp+638h+var_360], 5
0x1800c29dc  movups  xmm0, xmmword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x1800c29e3  movdqu  [rsp+638h+var_35C], xmm0
0x1800c29ec  lea     rax, aData; "DATA"
0x1800c29f3  mov     [rsp+638h+var_348], rax
0x1800c29fb  lea     rax, aDeviceencrypti_8; "DeviceEncryption-WindowsCore-UserData"
0x1800c2a02  mov     [rsp+638h+var_340], rax
0x1800c2a0a  mov     [rsp+638h+var_338], edi
0x1800c2a11  mov     [rsp+638h+var_334], rsi
0x1800c2a19  mov     [rsp+638h+var_328], 6
0x1800c2a24  movups  xmm0, xmmword ptr cs:PARTITION_DPP_GUID.Data1
0x1800c2a2b  movdqu  [rsp+638h+var_324], xmm0
0x1800c2a34  lea     rax, aDpp; "DPP"
0x1800c2a3b  mov     [rsp+638h+var_310], rax
0x1800c2a43  lea     rax, aDeviceencrypti_5; "DeviceEncryption-WindowsCore-DPP"
0x1800c2a4a  mov     [rsp+638h+var_308], rax
0x1800c2a52  mov     [rsp+638h+var_300], rdi
0x1800c2a5a  mov     [rsp+638h+var_2F8], edi
0x1800c2a61  mov     [rsp+638h+var_2F0], 7
0x1800c2a6c  movups  xmm0, cs:PARTITION_SERVICING_METADATA_GUID
0x1800c2a73  movdqu  [rsp+638h+var_2EC], xmm0
0x1800c2a7c  lea     rax, aServicingMetad; "SERVICING_METADATA"
0x1800c2a83  mov     [rsp+638h+var_2D8], rax
0x1800c2a8b  lea     rax, aDeviceencrypti_7; "DeviceEncryption-WindowsCore-ServicingM"...
0x1800c2a92  mov     [rsp+638h+var_2D0], rax
0x1800c2a9a  mov     [rsp+638h+var_2C8], rdi
0x1800c2aa2  mov     [rsp+638h+var_2C0], edi
0x1800c2aa9  mov     [rsp+638h+var_2B8], 8
0x1800c2ab4  movups  xmm0, cs:PARTITION_SERVICING_FILES_GUID
0x1800c2abb  movdqu  [rsp+638h+var_2B4], xmm0
0x1800c2ac4  lea     rax, aServicingFiles; "SERVICING_FILES"
0x1800c2acb  mov     [rsp+638h+var_2A0], rax
0x1800c2ad3  lea     rax, aDeviceencrypti_0; "DeviceEncryption-WindowsCore-ServicingF"...
0x1800c2ada  mov     [rsp+638h+var_298], rax
0x1800c2ae2  mov     [rsp+638h+var_290], rdi
0x1800c2aea  mov     [rsp+638h+var_288], edi
0x1800c2af1  mov     [rsp+638h+var_280], 9
0x1800c2afc  movups  xmm0, cs:PARTITION_SERVICING_RESERVE_GUID
0x1800c2b03  movdqu  [rsp+638h+var_27C], xmm0
0x1800c2b0c  lea     rax, aReserve; "RESERVE"
0x1800c2b13  mov     [rsp+638h+var_268], rax
0x1800c2b1b  lea     rax, aDeviceencrypti_2; "DeviceEncryption-WindowsCore-ServicingR"...
0x1800c2b22  mov     [rsp+638h+var_260], rax
0x1800c2b2a  mov     [rsp+638h+var_258], rdi
0x1800c2b32  mov     [rsp+638h+var_250], edi
0x1800c2b39  lea     rax, WPP_GLOBAL_Control
0x1800c2b40  mov     r10, cs:WPP_GLOBAL_Control
0x1800c2b47  lea     r14, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c2b4e  cmp     r10, rax
0x1800c2b51  jz      short loc_1800C2B72
0x1800c2b53  test    byte ptr [r10+1Ch], 20h
0x1800c2b58  jz      short loc_1800C2B72
0x1800c2b5a  mov     edx, 0A7h
0x1800c2b5f  mov     r8, r14
0x1800c2b62  mov     rcx, [r10+10h]
0x1800c2b66  call    WPP_SF_
0x1800c2b6b  mov     r10, cs:WPP_GLOBAL_Control
0x1800c2b72  test    r13, r13
0x1800c2b75  jnz     short loc_1800C2B85
0x1800c2b77  mov     esi, 80070057h
0x1800c2b7c  mov     [rsp+638h+var_5F4], esi
0x1800c2b80  jmp     loc_1800C434C
0x1800c2b85  test    r15, r15
0x1800c2b88  jnz     short loc_1800C2B91
0x1800c2b8a  mov     esi, 80004003h
0x1800c2b8f  jmp     short loc_1800C2B7C
0x1800c2b91  mov     ebx, 40h ; '@'
0x1800c2b96  mov     r8d, ebx; Size
0x1800c2b99  xor     edx, edx; Val
0x1800c2b9b  mov     rcx, r15; void *
0x1800c2b9e  call    memset_0
0x1800c2ba3  mov     [r15+2], bx
0x1800c2ba8  lea     eax, [rbx-3Eh]
0x1800c2bab  cmp     [r13+0], ax
0x1800c2bb0  jb      short loc_1800C2BD3
0x1800c2bb2  cmp     [r13+8], dil
0x1800c2bb6  setnz   bl
0x1800c2bb9  mov     [rsp+638h+var_5F8], bl
0x1800c2bbd  cmp     [r13+9], dil
0x1800c2bc1  jz      short loc_1800C2BCA
0x1800c2bc3  mov     [rsp+638h+var_5E8], sil
0x1800c2bc8  jmp     short loc_1800C2BD3
0x1800c2bca  mov     [rsp+638h+var_5E8], dil
0x1800c2bcf  mov     [rsp+638h+var_5F8], bl
0x1800c2bd3  lea     rcx, [rsp+638h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800c2bdb  call    cs:__imp_GetSystemTimeAsFileTime
0x1800c2be2  nop     dword ptr [rax+rax+00h]
0x1800c2be7  mov     eax, [rsp+638h+SystemTimeAsFileTime.dwHighDateTime]
0x1800c2bee  mov     dword ptr [rsp+638h+var_5D0+4], eax
0x1800c2bf2  mov     rax, qword ptr [rsp+638h+SystemTimeAsFileTime.dwLowDateTime]
0x1800c2bfa  mov     dword ptr [rsp+638h+var_5D0], eax
0x1800c2bfe  cmp     dword ptr [r13+4], 0FFFFFFFFh
0x1800c2c03  jnz     short loc_1800C2C1B
0x1800c2c05  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800c2c09  mov     [rsp+638h+var_5A8], rbx
0x1800c2c11  mov     rdi, [rsp+638h+var_5D0]
0x1800c2c16  xor     r13d, r13d
0x1800c2c19  jmp     short loc_1800C2C7D
0x1800c2c1b  mov     ecx, [r13+4]; unsigned __int64
0x1800c2c1f  lea     r8, [rsp+638h+var_5A8]; unsigned __int64 *
0x1800c2c27  mov     edx, 2710h; unsigned __int64
0x1800c2c2c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800c2c31  mov     esi, eax
0x1800c2c33  mov     [rsp+638h+var_5F4], eax
0x1800c2c37  test    eax, eax
0x1800c2c39  js      loc_1800C4340
0x1800c2c3f  mov     rax, [rsp+638h+var_5A8]
0x1800c2c47  mov     rdi, [rsp+638h+var_5D0]
0x1800c2c4c  lea     rbx, [rax+rdi]
0x1800c2c50  cmp     rbx, rdi
0x1800c2c53  jb      short loc_1800C2C5D
0x1800c2c55  xor     r13d, r13d
0x1800c2c58  mov     esi, r13d
0x1800c2c5b  jmp     short loc_1800C2C69
0x1800c2c5d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800c2c61  mov     esi, 80070216h
0x1800c2c66  xor     r13d, r13d
0x1800c2c69  mov     [rsp+638h+var_5A8], rbx
0x1800c2c71  mov     [rsp+638h+var_5F4], esi
0x1800c2c75  test    esi, esi
0x1800c2c77  js      loc_1800C4340
0x1800c2c7d  xor     r9d, r9d; ReturnLength
0x1800c2c80  lea     r8d, [r9+20h]; SystemInformationLength
0x1800c2c84  lea     rdx, [rsp+638h+SystemInformation]; SystemInformation
0x1800c2c8c  lea     ecx, [r9+5Ah]; SystemInformationClass
0x1800c2c90  call    cs:__imp_NtQuerySystemInformation
0x1800c2c97  nop     dword ptr [rax+rax+00h]
0x1800c2c9c  mov     esi, eax
0x1800c2c9e  mov     [rsp+638h+var_5D8], eax
0x1800c2ca2  test    eax, eax
0x1800c2ca4  jns     loc_1800C2D3B
0x1800c2caa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2cb1  lea     rdi, WPP_GLOBAL_Control
0x1800c2cb8  cmp     rcx, rdi
0x1800c2cbb  jz      short loc_1800C2CD7
0x1800c2cbd  test    byte ptr [rcx+1Ch], 2
0x1800c2cc1  jz      short loc_1800C2CD7
0x1800c2cc3  mov     edx, 0A8h
0x1800c2cc8  mov     r9d, eax
0x1800c2ccb  mov     r8, r14
0x1800c2cce  mov     rcx, [rcx+10h]
0x1800c2cd2  call    WPP_SF_d
0x1800c2cd7  mov     ecx, esi; Status
0x1800c2cd9  call    cs:__imp_RtlNtStatusToDosError
0x1800c2ce0  nop     dword ptr [rax+rax+00h]
0x1800c2ce5  mov     esi, eax
0x1800c2ce7  xor     r12d, r12d
0x1800c2cea  test    eax, eax
0x1800c2cec  jle     short loc_1800C2CF7
0x1800c2cee  movzx   esi, ax
0x1800c2cf1  or      esi, 80070000h
0x1800c2cf7  mov     [rsp+638h+var_5F4], esi
0x1800c2cfb  mov     r10, cs:WPP_GLOBAL_Control
0x1800c2d02  cmp     r10, rdi
0x1800c2d05  jz      loc_1800C4336
0x1800c2d0b  test    byte ptr [r10+1Ch], 2
0x1800c2d10  jz      loc_1800C4336
0x1800c2d16  mov     edx, 0A9h
0x1800c2d1b  mov     r9d, esi
0x1800c2d1e  mov     r8, r14
0x1800c2d21  mov     rcx, [r10+10h]
0x1800c2d25  call    WPP_SF_d
0x1800c2d2a  mov     r10, cs:WPP_GLOBAL_Control
0x1800c2d31  mov     rbx, [rsp+638h+hObject]
0x1800c2d36  jmp     loc_1800C4356
0x1800c2d3b  mov     r9d, dword ptr [rsp+638h+var_544+0Ch]
0x1800c2d43  cmp     r9d, 2
0x1800c2d47  jz      short loc_1800C2D73
0x1800c2d49  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2d50  lea     rax, WPP_GLOBAL_Control
0x1800c2d57  cmp     rcx, rax
0x1800c2d5a  jz      short loc_1800C2D73
0x1800c2d5c  test    byte ptr [rcx+1Ch], 4
0x1800c2d60  jz      short loc_1800C2D73
0x1800c2d62  mov     edx, 0AAh
0x1800c2d67  mov     r8, r14
0x1800c2d6a  mov     rcx, [rcx+10h]
0x1800c2d6e  call    WPP_SF_D
0x1800c2d73  lea     r9, [rsp+638h+ReturnLength]; ReturnLength
0x1800c2d7b  mov     r8d, 18h; SystemInformationLength
0x1800c2d81  lea     rdx, [rsp+638h+var_528]; SystemInformation
0x1800c2d89  lea     ecx, [r8+77h]; SystemInformationClass
0x1800c2d8d  call    cs:__imp_NtQuerySystemInformation
0x1800c2d94  nop     dword ptr [rax+rax+00h]
0x1800c2d99  mov     esi, eax
0x1800c2d9b  mov     [rsp+638h+var_5D8], eax
0x1800c2d9f  test    eax, eax
0x1800c2da1  jns     short loc_1800C2DE5
0x1800c2da3  cmp     eax, 80430006h
0x1800c2da8  jnz     short loc_1800C2E25
0x1800c2daa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2db1  lea     rax, WPP_GLOBAL_Control
0x1800c2db8  cmp     rcx, rax
0x1800c2dbb  jz      short loc_1800C2DDB
0x1800c2dbd  test    byte ptr [rcx+1Ch], 4
0x1800c2dc1  jz      short loc_1800C2DDB
0x1800c2dc3  mov     edx, 0ABh
0x1800c2dc8  mov     r8, r14
  ... truncated ...
```
