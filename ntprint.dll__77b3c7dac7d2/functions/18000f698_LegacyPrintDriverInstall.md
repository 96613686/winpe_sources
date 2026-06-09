# LegacyPrintDriverInstall

- ea: `0x18000f698`
- end: `0x180010b41`
- name: `LegacyPrintDriverInstall`
- size: `5289`
- prototype: `__int64 __usercall@<rax>(HDEVINFO DeviceInfoSet@<rcx>, struct _PSETUP_LOCAL_DATA *@<rdx>, HWND Owner@<r8>, int, LPWSTR pName, __int64, char, int, __int64)`
- caller_count: `2`
- callee_count: `34`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000b7ec`
- `0x18002c0f0`

## callees

- `0x180001ea4`
- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x180009d64`
- `0x18000b150`
- `0x18000c2f4`
- `0x18000c768`
- `0x18000d558`
- `0x18000d7f0`
- `0x18000d904`
- `0x18000f698`
- `0x1800110a0`
- `0x1800173e8`
- `0x18001bcd4`
- `0x18001c208`
- `0x18001d8c8`
- `0x18001ddf4`
- `0x18001f958`
- `0x180020418`
- `0x180020574`
- `0x180020660`
- `0x180020b60`
- `0x1800217e0`
- `0x180026584`
- `0x180026f2c`
- `0x180027570`
- `0x1800281a0`
- `0x1800288a0`
- `0x180029d14`
- `0x180029e44`
- `0x1800348d8`
- `0x180034bec`
- `0x180036470`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f8e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010431`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f8e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010892`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010217`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010a50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010217`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010a50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fb75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fb75`
- `SETUPAPI!SetupScanFileQueueW` at `0x180010262`
- `SETUPAPI!SetupScanFileQueueW` at `0x18001028e`
- `SETUPAPI!SetupScanFileQueueW` at `0x180010262`
- `SETUPAPI!SetupScanFileQueueW` at `0x18001028e`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x18000f9d7`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x18000f9d7`
- `SETUPAPI!SetupOpenFileQueue` at `0x18000fe88`
- `SETUPAPI!SetupOpenFileQueue` at `0x18000fe88`
- `SETUPAPI!SetupFindFirstLineW` at `0x18000f8d1`
- `SETUPAPI!SetupFindFirstLineW` at `0x18000f8d1`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800109e0`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800109e0`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180010a1f`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180010a1f`
- `SETUPAPI!SetupCommitFileQueueW` at `0x1800102a6`
- `SETUPAPI!SetupCommitFileQueueW` at `0x1800102a6`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800109a7`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800109a7`
- `SETUPAPI!SetupCloseFileQueue` at `0x180010a0d`
- `SETUPAPI!SetupCloseFileQueue` at `0x180010a0d`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x18000fab1`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x18000fab1`
- `SETUPAPI!SetupCloseInfFile` at `0x18000fe5b`
- `SETUPAPI!SetupCloseInfFile` at `0x180010957`
- `SETUPAPI!SetupCloseInfFile` at `0x18001096f`
- `SETUPAPI!SetupCloseInfFile` at `0x18000fe5b`
- `SETUPAPI!SetupCloseInfFile` at `0x180010957`
- `SETUPAPI!SetupCloseInfFile` at `0x18001096f`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x18000f9a2`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x18000fe82`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x18000f9a2`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x18000fe82`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x1800103c1`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x1800103c1`
- `WINSPOOL!AddPrintProcessorW` at `0x180010534`
- `WINSPOOL!AddPrintProcessorW` at `0x180010534`

## string_xrefs

- `0x18000ff1a`: `SetupOpenFileQueue failed`
- `0x1800100cd`: `InstallAllInfSections failed`
- `0x180010334`: `SetupCommitFileQueue failed`
- `0x18000f86a`: `LegacyPrintDriverInstall`
- `0x18000f975`: `LegacyPrintDriverInstall`
- `0x18000fa8f`: `LegacyPrintDriverInstall`
- `0x180010340`: `LegacyPrintDriverInstall`
- `0x1800104b2`: `LegacyPrintDriverInstall`
- `0x18001079c`: `LegacyPrintDriverInstall`
- `0x180010832`: `LegacyPrintDriverInstall`
- `0x180010aeb`: `LegacyPrintDriverInstall`
- `0x1800101d1`: `CheckAndEnqueueMonitorDll failed`
- `0x18001083c`: `PSetupInstallICMProfiles failed (profile names in additional info)`

## pseudocode

```c
__int64 __fastcall LegacyPrintDriverInstall(
        HDEVINFO DeviceInfoSet,
        struct _PSETUP_LOCAL_DATA *a2,
        __int64 Owner,
        WINBOOL a4,
        int a5,
        LPWSTR pName,
        const WCHAR *a7,
        int a8,
        int a9,
        unsigned int *a10)
{
  int v13; // eax
  int v14; // edi
  int v15; // ecx
  unsigned int DriverValidationPolicyLevel; // esi
  int v17; // eax
  unsigned int v18; // edi
  const unsigned __int16 *v19; // r8
  unsigned int v20; // r10d
  const unsigned __int16 *v21; // rcx
  int v22; // r9d
  unsigned int v23; // r15d
  const unsigned __int16 *v24; // rax
  const unsigned __int16 *v25; // rdx
  int v26; // r12d
  HINF v27; // rax
  __int64 v28; // rsi
  const unsigned __int16 *v29; // rcx
  int v30; // r9d
  const unsigned __int16 *v31; // rax
  const unsigned __int16 *v32; // rdx
  const unsigned __int16 *v33; // r8
  signed int v34; // eax
  const unsigned __int16 *v35; // r8
  unsigned int v36; // ecx
  const unsigned __int16 *v37; // rdx
  int v38; // r11d
  const unsigned __int16 *v39; // rdi
  const unsigned __int16 *v40; // r9
  const unsigned __int16 *v41; // r10
  signed int LastError; // eax
  const unsigned __int16 *v43; // r8
  unsigned int v44; // ecx
  const unsigned __int16 *v45; // rdx
  int v46; // r11d
  const unsigned __int16 *v47; // rdi
  const unsigned __int16 *v48; // r9
  const unsigned __int16 *v49; // r10
  _QWORD *v50; // rax
  const unsigned __int16 *v51; // rdx
  const unsigned __int16 *v52; // rax
  int v53; // r9d
  const unsigned __int16 *v54; // r10
  const unsigned __int16 *v55; // rcx
  const unsigned __int16 *v56; // r8
  const WCHAR *v57; // rsi
  int v58; // eax
  PVOID v59; // rdx
  const wchar_t *v60; // r11
  wchar_t *v61; // rax
  int v62; // ecx
  __int64 v63; // rax
  signed int v64; // eax
  unsigned int v65; // ecx
  unsigned int v66; // edx
  const unsigned __int16 *v67; // r8
  int v68; // r11d
  const unsigned __int16 *v69; // rax
  const unsigned __int16 *v70; // r9
  const unsigned __int16 *v71; // r10
  int v72; // eax
  _QWORD *v73; // rdx
  void *v74; // rax
  signed int v75; // eax
  unsigned int v76; // ecx
  unsigned int v77; // edx
  const unsigned __int16 *v78; // r8
  int v79; // r11d
  const unsigned __int16 *v80; // rax
  const unsigned __int16 *v81; // r9
  const unsigned __int16 *v82; // r10
  signed int v83; // eax
  unsigned int v84; // ecx
  unsigned int v85; // edx
  const unsigned __int16 *v86; // r8
  int v87; // r11d
  const unsigned __int16 *v88; // rax
  const unsigned __int16 *v89; // r9
  const unsigned __int16 *v90; // r10
  int v91; // eax
  const WCHAR *v92; // rsi
  signed int v93; // eax
  unsigned int v94; // ecx
  unsigned int v95; // edx
  const unsigned __int16 *v96; // r8
  int v97; // r11d
  const unsigned __int16 *v98; // rax
  const unsigned __int16 *v99; // r9
  const unsigned __int16 *v100; // r10
  __int64 v101; // rcx
  __int64 v102; // rax
  signed int v103; // eax
  unsigned int v104; // ecx
  unsigned int v105; // edx
  const unsigned __int16 *v106; // r8
  int v107; // r11d
  const unsigned __int16 *v108; // rax
  const unsigned __int16 *v109; // r9
  const unsigned __int16 *v110; // r10
  int v111; // eax
  void *v112; // rcx
  signed int v113; // eax
  unsigned int v114; // ecx
  unsigned int v115; // edx
  const unsigned __int16 *v116; // r8
  int v117; // r11d
  const unsigned __int16 *v118; // rax
  const unsigned __int16 *v119; // r9
  const unsigned __int16 *v120; // r10
  signed int v121; // esi
  int v122; // eax
  DWORD v123; // ecx
  unsigned int v124; // ecx
  const unsigned __int16 *v125; // rdx
  int v126; // r10d
  const unsigned __int16 *v127; // rax
  const unsigned __int16 *v128; // r8
  const unsigned __int16 *v129; // r9
  WCHAR *v130; // r9
  __int64 v131; // rax
  signed int v132; // eax
  unsigned int v133; // ecx
  unsigned int v134; // edx
  const unsigned __int16 *v135; // r8
  int v136; // r11d
  const unsigned __int16 *v137; // rax
  const unsigned __int16 *v138; // r9
  const unsigned __int16 *v139; // r10
  const wchar_t *v140; // rcx
  __int128 v141; // xmm0
  __int128 v142; // xmm1
  const wchar_t *v143; // rax
  __int64 v144; // rax
  __int128 v145; // xmm0
  __int64 v146; // rax
  __int128 v147; // xmm1
  __int128 v148; // xmm0
  __int128 v149; // xmm1
  __int128 v150; // xmm0
  __int128 v151; // xmm1
  signed int v152; // eax
  unsigned int v153; // edx
  int v154; // r9d
  const unsigned __int16 *v155; // r8
  signed int v156; // edi
  unsigned int v157; // ecx
  int v158; // r8d
  const unsigned __int16 *v159; // rdx
  WCHAR *v160; // rdi
  unsigned __int64 v161; // rdx
  signed int FailureLastError; // edi
  signed int v163; // eax
  unsigned int v164; // ecx
  unsigned int v165; // edx
  const unsigned __int16 *v166; // r8
  int v167; // r11d
  const unsigned __int16 *v168; // rax
  const unsigned __int16 *v169; // r9
  const unsigned __int16 *v170; // r10
  HDEVINFO v171; // r14
  BOOL DeviceInstallParamsW; // eax
  HSPFILEQ v173; // rsi
  unsigned int v174; // edx
  const unsigned __int16 *v175; // r8
  int v176; // r11d
  const unsigned __int16 *v177; // rax
  const unsigned __int16 *v178; // r9
  const unsigned __int16 *v179; // r10
  const struct _EVENT_DESCRIPTOR *v180; // rcx
  unsigned int DeviceInfoData; // [rsp+50h] [rbp-B0h]
  int v183; // [rsp+70h] [rbp-90h]
  WINBOOL IsMember; // [rsp+74h] [rbp-8Ch] BYREF
  HINF InfHandle; // [rsp+78h] [rbp-88h]
  HSPFILEQ FileQueue; // [rsp+80h] [rbp-80h]
  PVOID hMem; // [rsp+88h] [rbp-78h]
  unsigned int v188; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR SourceRootPath; // [rsp+98h] [rbp-68h] BYREF
  int v190; // [rsp+A0h] [rbp-60h]
  HINF v191; // [rsp+A8h] [rbp-58h] BYREF
  HDEVINFO v192; // [rsp+B0h] [rbp-50h]
  PVOID inited; // [rsp+B8h] [rbp-48h]
  DWORD Result; // [rsp+C0h] [rbp-40h] BYREF
  DWORD v195; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned __int16 *v196; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v197; // [rsp+D0h] [rbp-30h]
  __int64 v198[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int *v199; // [rsp+E8h] [rbp-18h]
  struct _INFCONTEXT Context; // [rsp+F0h] [rbp-10h] BYREF
  _DRIVER_INFO_6W v201; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v202; // [rsp+198h] [rbp+98h]
  __int64 v203; // [rsp+1A0h] [rbp+A0h]
  __int64 v204; // [rsp+1A8h] [rbp+A8h]
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+1E0h] [rbp+E0h] BYREF
  _WORD v206[264]; // [rsp+430h] [rbp+330h] BYREF

  SourceRootPath = a7;
  v192 = DeviceInfoSet;
  v199 = a10;
  IsMember = a4;
  v191 = (HINF)-1LL;
  v183 = 0;
  hMem = 0;
  v188 = 0;
  v196 = 0;
  v195 = 0;
  memset_0(v206, 0, 0x208u);
  FileQueue = (HSPFILEQ)-1LL;
  inited = 0;
  v197 = -1;
  *(_OWORD *)v198 = 0;
  DisassociateQueueFromDeviceInfoList(DeviceInfoSet);
  v13 = 1;
  if ( pName && *pName )
    v13 = IsWhistlerOrAbove(pName);
  v14 = a8 | 0x80;
  if ( !v13 )
    v14 = a8;
  v15 = a9 | 0x10;
  if ( !v13 )
    v15 = a9;
  v190 = v15;
  if ( (v14 & 0x40) != 0 )
    *((_DWORD *)a2 + 66) = a5;
  DriverValidationPolicyLevel = GetDriverValidationPolicyLevel();
  if ( !(unsigned int)IsTestSigningEnabled() && DriverValidationPolicyLevel <= 3 )
  {
    v17 = PSetupValidateDriver(DriverValidationPolicyLevel, *(_QWORD *)a2);
    if ( v17 < 0 )
    {
      InfHandle = (HINF)-1LL;
      v18 = WIN32_FROM_HRESULT(v17);
      if ( !a2 || *((_DWORD *)a2 + 43) == (_DWORD)v19 )
      {
        v21 = v19;
        if ( !a2 )
        {
          v22 = (int)v19;
          goto LABEL_19;
        }
      }
      else
      {
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
      }
      v22 = *((_DWORD *)a2 + 43);
LABEL_19:
      v23 = IsMember;
      if ( a2 )
      {
        v24 = *(const unsigned __int16 **)a2;
        v25 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
        v19 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
      }
      else
      {
        v24 = v19;
        v25 = v19;
      }
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"LegacyPrintDriverInstall",
        L"DriverValidation",
        pName,
        v24,
        v25,
        v19,
        (const unsigned __int16 *)PlatformEnv[IsMember],
        v22,
        v21,
        v18,
        v20);
      goto LABEL_23;
    }
  }
  v27 = (HINF)OpenPrinterInfFile(*(unsigned __int16 **)a2);
  InfHandle = v27;
  if ( v27 == (HINF)-1LL )
  {
    v23 = IsMember;
LABEL_23:
    v26 = 0;
LABEL_265:
    FailureLastError = GetFailureLastError();
    goto LABEL_266;
  }
  v28 = IsMember;
  if ( IsMember != MyPlatform )
  {
    memset(&Context, 0, sizeof(Context));
    if ( SetupFindFirstLineW(v27, L"Version", L"LayoutFile", &Context) )
    {
      SetLastError(0x661u);
      if ( a2 && *((_DWORD *)a2 + 43) )
      {
        v29 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
      }
      else
      {
        v29 = 0;
        if ( !a2 )
        {
          v30 = 0;
          goto LABEL_33;
        }
      }
      v30 = *((_DWORD *)a2 + 43);
LABEL_33:
      v23 = IsMember;
      if ( a2 )
      {
        v31 = *(const unsigned __int16 **)a2;
        v32 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
        v33 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
      }
      else
      {
        v31 = 0;
        v32 = 0;
        v33 = 0;
      }
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"LegacyPrintDriverInstall",
        L"SetupFindFirstLine(Version, LayoutFile) failed",
        pName,
        v31,
        v32,
        v33,
        (const unsigned __int16 *)PlatformEnv[IsMember],
        v30,
        v29,
        0x661u,
        0x80070661);
LABEL_37:
      v26 = 0;
      goto LABEL_265;
    }
    v27 = InfHandle;
  }
  SetupOpenAppendInfFileW(0, v27, 0);
  *((_QWORD *)a2 + 35) = PlatformEnv[IsMember];
  if ( (v14 & 0x10) == 0 )
  {
    inited = SetupInitDefaultQueueCallback((HWND)Owner);
    if ( inited )
      goto LABEL_64;
    LastError = GetLastError();
    v43 = 0;
    if ( LastError > 0 )
      v44 = (unsigned __int16)LastError | 0x80070000;
    else
      v44 = LastError;
    if ( a2 && *((_DWORD *)a2 + 43) )
    {
      v45 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    }
    else
    {
      v45 = 0;
      if ( !a2 )
      {
        v47 = (const unsigned __int16 *)PlatformEnv[v28];
        v48 = 0;
        v49 = 0;
        v46 = 0;
        v45 = 0;
        goto LABEL_63;
      }
    }
    v46 = *((_DWORD *)a2 + 43);
    v47 = (const unsigned __int16 *)PlatformEnv[v28];
    v48 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
    v43 = *(const unsigned __int16 **)a2;
    v49 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
LABEL_63:
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"SetupInitDefaultQueueCallback failed",
      pName,
      v43,
      v48,
      v49,
      v47,
      v46,
      v45,
      LastError,
      v44);
    goto LABEL_51;
  }
  inited = SetupInitDefaultQueueCallbackEx((HWND)Owner, HWND_MESSAGE|0x2LL, 0, 0, 0);
  if ( !inited )
  {
    v34 = GetLastError();
    v35 = 0;
    if ( v34 > 0 )
      v36 = (unsigned __int16)v34 | 0x80070000;
    else
      v36 = v34;
    if ( a2 && *((_DWORD *)a2 + 43) )
    {
      v37 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    }
    else
    {
      v37 = 0;
      if ( !a2 )
      {
        v39 = (const unsigned __int16 *)PlatformEnv[v28];
        v40 = 0;
        v41 = 0;
        v38 = 0;
        v37 = 0;
        goto LABEL_50;
      }
    }
    v38 = *((_DWORD *)a2 + 43);
    v39 = (const unsigned __int16 *)PlatformEnv[v28];
    v40 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
    v35 = *(const unsigned __int16 **)a2;
    v41 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
LABEL_50:
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"SetupInitDefaultQueueCallbackEx failed",
      pName,
      v35,
      v40,
      v41,
      v39,
      v38,
      v37,
      v34,
      v36);
LABEL_51:
    v23 = IsMember;
LABEL_52:
    v26 = v183;
    goto LABEL_265;
  }
LABEL_64:
  v50 = LocalAlloc(0x40u, 0x448u);
  v51 = 0;
  hMem = v50;
  if ( !v50 )
  {
    if ( a2 && *((_DWORD *)a2 + 43) )
    {
      v52 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    }
    else
    {
      v52 = 0;
      if ( !a2 )
      {
        v54 = (const unsigned __int16 *)PlatformEnv[v28];
        v55 = 0;
        v56 = 0;
        v53 = 0;
        v52 = 0;
        goto LABEL_71;
      }
    }
    v53 = *((_DWORD *)a2 + 43);
    v54 = (const unsigned __int16 *)PlatformEnv[v28];
    v55 = *(const unsigned __int16 **)a2;
    v51 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
    v56 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
LABEL_71:
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"LocalAlloc(sizeof(FILE_QUEUE_CONTEXT)) failed",
      pName,
      v55,
      v51,
      v56,
      v54,
      v53,
      v52,
      0xEu,
      0x8007000E);
    goto LABEL_51;
  }
  v57 = SourceRootPath;
  *v50 = Owner;
  v50[1] = inited;
  *((_DWORD *)v50 + 7) = v14;
  *((_DWORD *)v50 + 139) = a5;
  v50[2] = (unsigned __int64)v57 & -(__int64)((v14 & 0x21) != 0);
  *((_DWORD *)v50 + 138) = IsMember;
  v58 = IsNTPrintInf(*(_QWORD *)a2, 0);
  v59 = hMem;
  *((_DWORD *)hMem + 140) = v58;
  *((_DWORD *)v59 + 142) = 0;
  if ( *(_QWORD *)a2 )
  {
    StringCchCopyW((unsigned __int16 *)v59 + 16, 0x104u, *(const unsigned __int16 **)a2);
    v61 = wcsrchr(v60, 0x5Cu);
    v59 = hMem;
    if ( v61 )
      *v61 = 0;
  }
  v23 = IsMember;
  if ( (v14 & 8) != 0 || MyPlatform == IsMember )
  {
    v62 = 0;
    v59 = 0;
  }
  else
  {
    v62 = 1;
  }
  v63 = Owner;
  if ( !v62 )
    v63 = -1;
  if ( !(unsigned int)ParseInf(v192, a2, (unsigned int)IsMember, pName, v62, v63, v59, v14, &v191, v198) )
  {
    v64 = GetLastError();
    v65 = v64;
    if ( v64 > 0 )
      v66 = (unsigned __int16)v64 | 0x80070000;
    else
      v66 = v64;
    if ( a2 && *((_DWORD *)a2 + 43) )
    {
      v67 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    }
    else
    {
      v67 = 0;
      if ( !a2 )
      {
        v68 = 0;
        goto LABEL_91;
      }
    }
    v68 = *((_DWORD *)a2 + 43);
LABEL_91:
    if ( a2 )
    {
      v69 = *(const unsigned __int16 **)a2;
      v70 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
      v71 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
    }
    else
    {
      v69 = 0;
      v70 = 0;
      v71 = 0;
    }
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"ParseInf failed",
      pName,
      v69,
      v70,
      v71,
      (const unsigned __int16 *)PlatformEnv[IsMember],
      v68,
      v67,
      v65,
      v66);
    goto LABEL_37;
  }
  v72 = CheckDriverSigning(
          v192,
          a2,
          Owner,
          (unsigned int)IsMember,
          pName,
          v57,
          v14,
          a2,
          (char *)a2 + 168,
          v191,
          hMem,
          MyQueueCallback,
          v206,
          v198);
  v73 = hMem;
  if ( (!*((_DWORD *)hMem + 141) || !*((_WORD *)hMem + 286)) && v206[0] )
  {
    *((_DWORD *)hMem + 7) |= 1u;
    v73[2] = v206;
    *((_DWORD *)v73 + 142) = 1;
  }
  if ( v72 )
  {
    v26 = 0;
    goto LABEL_265;
  }
  SetupCloseInfFile(InfHandle);
  v74 = (void *)OpenPrinterInfFile(*(unsigned __int16 **)a2);
  InfHandle = v74;
  if ( v74 == (void *)-1LL )
    goto LABEL_23;
  SetupOpenAppendInfFileW(0, v74, 0);
  FileQueue = SetupOpenFileQueue();
  if ( FileQueue == (HSPFILEQ)-1LL )
  {
    v75 = GetLastError();
    v76 = v75;
    if ( v75 > 0 )
      v77 = (unsigned __int16)v75 | 0x80070000;
    else
      v77 = v75;
    if ( a2 && *((_DWORD *)a2 + 43) )
    {
      v78 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    }
    else
    {
      v78 = 0;
      if ( !a2 )
      {
        v79 = 0;
        goto LABEL_111;
      }
    }
    v79 = *((_DWORD *)a2 + 43);
LABEL_111:
    if ( a2 )
    {
      v80 = *(const unsigned __int16 **)a2;
      v81 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
      v82 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
    }
    else
    {
      v80 = 0;
      v81 = 0;
      v82 = 0;
    }
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"SetupOpenFileQueue failed",
      pName,
      v80,
      v81,
      v82,
      (const unsigned __int16 *)PlatformEnv[v23],
      v79,
      v78,
      v76,
      v77);
    goto LABEL_37;
  }
  if ( !(unsigned int)SetAltPlatform(v192, pName, 0) )
  {
    v83 = GetLastError();
    v84 = v83;
    if ( v83 > 0 )
      v85 = (unsigned __int16)v83 | 0x80070000;
    else
      v85 = v83;
    if ( a2 && *((_DWORD *)a2 + 43) )
    {
      v86 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    }
    else
    {
      v86 = 0;
      if ( !a2 )
      {
        v87 = 0;
        goto LABEL_125;
      }
    }
    v87 = *((_DWORD *)a2 + 43);
LABEL_125:
    if ( a2 )
    {
      v88 = *(const unsigned __int16 **)a2;
      v89 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
      v90 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
    }
    else
    {
      v88 = 0;
      v89 = 0;
      v90 = 0;
    }
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"SetAltPlatform failed",
      pName,
      v88,
      v89,
      v90,
      (const unsigned __int16 *)PlatformEnv[v23],
      v87,
      v86,
      v84,
      v85);
    goto LABEL_37;
  }
  v91 = InstallAllInfSections(
          a2,
          v57,
          v14,
          InfHandle,
          *((PCWSTR *)a2 + 23),
          (__int64)v191,
          (__int64)v198,
          (__int64)a2 + 400);
  v92 = 0;
  if ( !v91 )
  {
    v93 = GetLastError();
    v94 = v93;
    if ( v93 > 0 )
      v95 = (unsigned __int16)v93 | 0x80070000;
    else
      v95 = v93;
    if ( a2 && *((_DWORD *)a2 + 43) )
    {
      v96 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    }
    else
    {
      v96 = 0;
      if ( !a2 )
      {
        v97 = 0;
        goto LABEL_139;
      }
    }
    v97 = *((_DWORD *)a2 + 43);
LABEL_139:
    if ( a2 )
    {
      v98 = *(const unsigned __int16 **)a2;
      v99 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
      v100 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
    }
    else
    {
      v98 = 0;
      v99 = 0;
      v100 = 0;
    }
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"InstallAllInfSections failed",
      pName,
      v98,
      v99,
      v100,
      (const unsigned __int16 *)PlatformEnv[v23],
      v97,
      v96,
      v94,
      v95);
    goto LABEL_37;
  }
  v101 = *((_QWORD *)a2 + 41);
  if ( !v101 || v23 != MyPlatform || (v14 & 0x24) != 0 || pName )
  {
    v111 = 0;
  }
  else
  {
    v102 = -1;
    do
      ++v102;
    while ( *(_WORD *)(v101 + 2 * v102) );
    v92 = (const WCHAR *)(v101 + 2 + 2 * v102);
    if ( !(unsigned int)CheckAndEnqueueMonitorDll(v92) )
    {
      v103 = GetLastError();
      v104 = v103;
      if ( v103 > 0 )
        v105 = (unsigned __int16)v103 | 0x80070000;
      else
        v105 = v103;
      if ( a2 && *((_DWORD *)a2 + 43) )
      {
        v106 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
      }
      else
      {
        v106 = 0;
        if ( !a2 )
        {
          v107 = 0;
          goto LABEL_159;
        }
      }
      v107 = *((_DWORD *)a2 + 43);
LABEL_159:
      if ( a2 )
      {
        v108 = *(const unsigned __int16 **)a2;
        v109 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
        v110 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
      }
      else
      {
        v108 = 0;
        v109 = 0;
        v110 = 0;
      }
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"LegacyPrintDriverInstall",
        L"CheckAndEnqueueMonitorDll failed",
        0,
        v108,
        v109,
        v110,
        (const unsigned __int16 *)PlatformEnv[v23],
        v107,
        v106,
        v104,
        v105);
      goto LABEL_37;
    }
    v111 = 1;
    v183 = 1;
  }
  if ( (v14 & 0x20) != 0 || !v111 )
  {
    v112 = (void *)*((_QWORD *)a2 + 41);
    if ( v112 )
    {
      LocalFree(v112);
      *((_QWORD *)a2 + 41) = 0;
    }
  }
  IsMember = 0;
  Result = 0;
  if ( !(unsigned int)IsLocalAdmin(&IsMember)
    || !IsMember && !SetupScanFileQueueW(FileQueue, 0x21u, (HWND)Owner, 0, 0, &Result) )
  {
    v163 = GetLastError();
    v164 = v163;
    if ( v163 > 0 )
      v165 = (unsigned __int16)v163 | 0x80070000;
    else
      v165 = v163;
    if ( a2 && *((_DWORD *)a2 + 43) )
    {
      v166 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    }
    else
    {
      v166 = 0;
      if ( !a2 )
      {
        v167 = 0;
        goto LABEL_259;
      }
    }
    v167 = *((_DWORD *)a2 + 43);
LABEL_259:
    if ( a2 )
    {
      v168 = *(const unsigned __int16 **)a2;
      v169 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
      v170 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
    }
    else
    {
      v168 = 0;
      v169 = 0;
      v170 = 0;
    }
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"PruneInvalidFilesIfNotAdmin failed",
      pName,
      v168,
      v169,
      v170,
      (const unsigned __int16 *)PlatformEnv[v23],
      v167,
      v166,
      v164,
      v165);
    goto LABEL_52;
  }
  SetupScanFileQueueW(FileQueue, 0x22u, (HWND)Owner, 0, 0, &v195);
  if ( !SetupCommitFileQueueW((HWND)Owner, FileQueue, MyQueueCallback, hMem) )
  {
    v113 = GetLastError();
    v114 = v113;
    if ( v113 > 0 )
      v115 = (unsigned __int16)v113 | 0x80070000;
    else
      v115 = v113;
    if ( a2 && *((_DWORD *)a2 + 43) )
    {
      v116 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    }
    else
    {
      v116 = 0;
      if ( !a2 )
      {
        v117 = 0;
        goto LABEL_182;
      }
    }
    v117 = *((_DWORD *)a2 + 43);
LABEL_182:
    if ( a2 )
    {
      v118 = *(const unsigned __int16 **)a2;
      v119 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
      v120 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
    }
    else
    {
      v118 = 0;
      v119 = 0;
      v120 = 0;
    }
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"SetupCommitFileQueue failed",
      pName,
      v118,
      v119,
      v120,
      (const unsigned __int16 *)PlatformEnv[v23],
      v117,
      v116,
      v114,
      v115);
    goto LABEL_52;
  }
  if ( !pName && v23 == MyPlatform )
    SetupInstallFromInfSectionW(
      (HWND)Owner,
      InfHandle,
      *((PCWSTR *)a2 + 23),
      0x7EFu,
      0,
      SourceRootPath,
      0,
      0,
      inited,
      v192,
      *((PSP_DEVINFO_DATA *)a2 + 3));
  v26 = v183;
  if ( v183 )
  {
    if ( !(unsigned int)AddPrintMonitor(*((_QWORD *)a2 + 41), v92) )
    {
      v121 = GetLastError();
      v122 = BlockedDriverPrintUpgUI(
               pName,
               (struct _DRIVER_INFO_6W *)((char *)a2 + 264),
               (unsigned __int8)v14 & 0x80,
               &v188);
      v123 = 3014;
      if ( !v122 )
        v123 = v121;
      SetLastError(v123);
      if ( v121 > 0 )
        v124 = (unsigned __int16)v121 | 0x80070000;
      else
        v124 = v121;
      if ( a2 && *((_DWORD *)a2 + 43) )
      {
        v125 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
      }
      else
      {
        v125 = 0;
        if ( !a2 )
        {
          v126 = 0;
          goto LABEL_202;
        }
      }
      v126 = *((_DWORD *)a2 + 43);
LABEL_202:
      if ( a2 )
      {
        v127 = *(const unsigned __int16 **)a2;
        v128 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
        v129 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
      }
      else
      {
        v127 = 0;
        v128 = 0;
        v129 = 0;
      }
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"LegacyPrintDriverInstall",
        L"AddPrintMonitor failed",
        *((const unsigned __int16 **)a2 + 41),
        v127,
        v128,
        v129,
        (const unsigned __int16 *)PlatformEnv[v23],
        v126,
        v125,
        v121,
        v124);
      goto LABEL_265;
    }
    MonitorRedirectEnable(&v196);
  }
  if ( (v14 & 4) == 0 )
  {
    v130 = (WCHAR *)*((_QWORD *)a2 + 25);
    if ( v130 )
    {
      v131 = -1;
      do
        ++v131;
      while ( v130[v131] );
      if ( !AddPrintProcessorW(pName, (LPWSTR)PlatformEnv[v23], &v130[v131 + 1], v130)
        && GetLastError() != 3005
        && GetLastError() != 1805 )
      {
        v132 = GetLastError();
        v133 = v132;
        if ( v132 > 0 )
          v134 = (unsigned __int16)v132 | 0x80070000;
        else
          v134 = v132;
        if ( a2 && *((_DWORD *)a2 + 43) )
        {
          v135 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
        }
        else
        {
          v135 = 0;
          if ( !a2 )
          {
            v136 = 0;
            goto LABEL_223;
          }
        }
        v136 = *((_DWORD *)a2 + 43);
LABEL_223:
        if ( a2 )
        {
          v137 = *(const unsigned __int16 **)a2;
          v138 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
          v139 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
        }
        else
        {
          v137 = 0;
          v138 = 0;
          v139 = 0;
        }
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"LegacyPrintDriverInstall",
          L"AddPrintProcessor failed",
          *((const unsigned __int16 **)a2 + 25),
          v137,
          v138,
          v139,
          (const unsigned __int16 *)PlatformEnv[v23],
          v136,
          v135,
          v133,
          v134);
        goto LABEL_265;
      }
    }
  }
  if ( (unsigned int)IsTheSamePlatform(pName) && (unsigned int)IsWhistlerOrAbove(pName) )
    CheckAndKeepPreviousNames(pName);
  memset_0(&v201, 0, 0xC8u);
  v140 = (const wchar_t *)*((_QWORD *)a2 + 25);
  v141 = *(_OWORD *)((char *)a2 + 264);
  v142 = *(_OWORD *)((char *)a2 + 280);
  v201.pszProvider = (LPWSTR)*((_QWORD *)a2 + 49);
  v143 = L"winprint";
  if ( v140 )
    v143 = v140;
  v202 = v143;
  v144 = *((_QWORD *)a2 + 27);
  *(_OWORD *)&v201.cVersion = v141;
  v203 = v144;
  v145 = *(_OWORD *)((char *)a2 + 296);
  v146 = *((_QWORD *)a2 + 24);
  *(_OWORD *)&v201.pEnvironment = v142;
  v204 = v146;
  v147 = *(_OWORD *)((char *)a2 + 312);
  *(_OWORD *)&v201.pDataFile = v145;
  v148 = *(_OWORD *)((char *)a2 + 328);
  *(_OWORD *)&v201.pHelpFile = v147;
  v149 = *(_OWORD *)((char *)a2 + 344);
  *(_OWORD *)&v201.pMonitorName = v148;
  v150 = *(_OWORD *)((char *)a2 + 360);
  *(_OWORD *)&v201.pszzPreviousNames = v149;
  v151 = *(_OWORD *)((char *)a2 + 376);
  *(_OWORD *)&v201.dwlDriverVersion = v150;
  *(_OWORD *)&v201.pszOEMUrl = v151;
  if ( !(unsigned int)AddPrinterDriverUsingCorrectLevelWithPrintUpgRetry(pName, &v201, (v14 & 0x208) == 0, &v188) )
  {
    v152 = GetLastError();
    if ( v152 > 0 )
      v153 = (unsigned __int16)v152 | 0x80070000;
    else
      v153 = v152;
    v154 = *((_DWORD *)a2 + 43);
    if ( v154 )
      v155 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    else
      v155 = 0;
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"AddPrinterDriverUsingCorrectLevelWithPrintUpgRetry failed",
      pName,
      *(const unsigned __int16 **)a2,
      *((const unsigned __int16 **)a2 + 1),
      *((const unsigned __int16 **)a2 + 23),
      (const unsigned __int16 *)PlatformEnv[v23],
      v154,
      v155,
      v152,
      v153);
    goto LABEL_265;
  }
  if ( !(unsigned int)PSetupInstallICMProfiles(pName, *((unsigned __int16 **)a2 + 24)) )
  {
    SourceRootPath = 0;
    v156 = GetLastError();
    ConvertMultiToSingleSz(*((const unsigned __int16 **)a2 + 24), (unsigned __int16 **)&SourceRootPath);
    if ( v156 > 0 )
      v157 = (unsigned __int16)v156 | 0x80070000;
    else
      v157 = v156;
    v158 = *((_DWORD *)a2 + 43);
    if ( v158 )
      v159 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
    else
      v159 = 0;
    DeviceInfoData = v156;
    v160 = (WCHAR *)SourceRootPath;
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"LegacyPrintDriverInstall",
      L"PSetupInstallICMProfiles failed (profile names in additional info)",
      SourceRootPath,
      *(const unsigned __int16 **)a2,
      *((const unsigned __int16 **)a2 + 1),
      *((const unsigned __int16 **)a2 + 23),
      (const unsigned __int16 *)PlatformEnv[v23],
      v158,
      v159,
      DeviceInfoData,
      v157);
    if ( v160 )
      operator delete(v160, v161);
    goto LABEL_265;
  }
  FailureLastError = 0;
LABEL_266:
  if ( v26 && v196 )
    MonitorRedirectEnable(&v196);
  if ( InfHandle != (HINF)-1LL )
    SetupCloseInfFile(InfHandle);
  FreeInfArray(v198);
  if ( v191 != (HINF)-1LL )
  {
    SetupCloseInfFile(v191);
    v191 = (HINF)-1LL;
  }
  memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
  v171 = v192;
  DeviceInstallParams.cbSize = 584;
  DeviceInstallParamsW = SetupDiGetDeviceInstallParamsW(v192, 0, &DeviceInstallParams);
  v173 = FileQueue;
  if ( DeviceInstallParamsW && DeviceInstallParams.FileQueue == FileQueue )
  {
    DeviceInstallParams.FlagsEx &= ~0x10000000u;
    DeviceInstallParams.Flags &= ~8u;
    DeviceInstallParams.FileQueue = (HSPFILEQ)-1LL;
    SetupDiSetDeviceInstallParamsW(v171, 0, &DeviceInstallParams);
  }
  if ( v206[0] )
    RecursivelyDeleteDirectory(v206, 5);
  if ( v173 != (HSPFILEQ)-1LL )
    SetupCloseFileQueue(v173);
  if ( inited )
    SetupTermDefaultQueueCallback(inited);
  if ( (v190 & 0x10) == 0 )
    CleanupScratchDirectory(pName, v23);
  if ( v199 )
    *v199 = v188;
  if ( hMem )
    LocalFree(hMem);
  if ( v197 != -1 )
    AssociateQueueWithDeviceInfoList(v171);
  if ( FailureLastError > 0 )
    v174 = (unsigned __int16)FailureLastError | 0x80070000;
  else
    v174 = FailureLastError;
  if ( a2 && *((_DWORD *)a2 + 43) )
  {
    v175 = (const unsigned __int16 *)*((_QWORD *)a2 + 28);
LABEL_297:
    v176 = *((_DWORD *)a2 + 43);
    goto LABEL_299;
  }
  v175 = 0;
  if ( a2 )
    goto LABEL_297;
  v176 = 0;
LABEL_299:
  if ( a2 )
  {
    v177 = *(const unsigned __int16 **)a2;
    v178 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
    v179 = (const unsigned __int16 *)*((_QWORD *)a2 + 23);
  }
  else
  {
    v177 = 0;
    v178 = 0;
    v179 = 0;
  }
  v180 = &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED;
  if ( FailureLastError )
    v180 = &SETUP_INSTALL_PRINTER_DRIVER_FAILED;
  SplLogPrinterSetupCoreDriverEvent(
    v180,
    L"LegacyPrintDriverInstall",
    0,
    pName,
    v177,
    v178,
    v179,
    (const unsigned __int16 *)PlatformEnv[v23],
    v176,
    v175,
    FailureLastError,
    v174);
  return (unsigned int)FailureLastError;
}

```

## disassembly

```asm
0x18000f698  push    rbp
0x18000f69a  push    rbx
0x18000f69b  push    rsi
0x18000f69c  push    rdi
0x18000f69d  push    r12
0x18000f69f  push    r13
0x18000f6a1  push    r14
0x18000f6a3  push    r15
0x18000f6a5  lea     rbp, [rsp-558h]
0x18000f6ad  sub     rsp, 658h
0x18000f6b4  mov     rax, cs:__security_cookie
0x18000f6bb  xor     rax, rsp
0x18000f6be  mov     [rbp+590h+var_50], rax
0x18000f6c5  mov     rax, [rbp+590h+arg_30]
0x18000f6cc  xor     esi, esi
0x18000f6ce  mov     r13, [rbp+590h+pName]
0x18000f6d5  mov     r12, r8
0x18000f6d8  mov     [rbp+590h+SourceRootPath], rax
0x18000f6dc  mov     rbx, rdx
0x18000f6df  mov     rax, [rbp+590h+arg_48]
0x18000f6e6  mov     rdi, rcx
0x18000f6e9  mov     [rbp+590h+var_5E0], rcx
0x18000f6ed  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000f6f1  xor     edx, edx; Val
0x18000f6f3  mov     [rbp+590h+var_5A8], rax
0x18000f6f7  mov     r8d, 208h; Size
0x18000f6fd  mov     [rsp+690h+IsMember], r9d
0x18000f702  lea     rcx, [rbp+590h+var_260]; void *
0x18000f709  mov     [rbp+590h+var_5E8], r14
0x18000f70d  mov     [rsp+690h+var_620], esi
0x18000f711  mov     [rbp+590h+hMem], rsi
0x18000f715  mov     [rbp+590h+var_600], esi
0x18000f718  mov     [rbp+590h+var_5C8], rsi
0x18000f71c  mov     [rbp+590h+var_5CC], esi
0x18000f71f  call    memset_0
0x18000f724  xorps   xmm0, xmm0
0x18000f727  mov     [rbp+590h+FileQueue], r14
0x18000f72b  lea     rdx, [rbp+590h+var_5C0]
0x18000f72f  mov     [rbp+590h+var_5D8], rsi
0x18000f733  mov     rcx, rdi; DeviceInfoSet
0x18000f736  mov     [rbp+590h+var_5C0], r14
0x18000f73a  movups  xmmword ptr [rbp+590h+var_5B8], xmm0
0x18000f73e  call    DisassociateQueueFromDeviceInfoList
0x18000f743  lea     r14, [rbx+0A8h]
0x18000f74a  lea     eax, [rsi+1]
0x18000f74d  test    r13, r13
0x18000f750  jz      short loc_18000F761
0x18000f752  cmp     [r13+0], si
0x18000f757  jz      short loc_18000F761
0x18000f759  mov     rcx, r13; pPrinterName
0x18000f75c  call    IsWhistlerOrAbove
0x18000f761  mov     edi, dword ptr [rbp+590h+arg_38]
0x18000f767  mov     ecx, [rbp+590h+arg_40]
0x18000f76d  bts     edi, 7
0x18000f771  mov     r15d, [rbp+590h+arg_20]
0x18000f778  test    eax, eax
0x18000f77a  cmovz   edi, dword ptr [rbp+590h+arg_38]
0x18000f781  or      ecx, 10h
0x18000f784  test    eax, eax
0x18000f786  cmovz   ecx, [rbp+590h+arg_40]
0x18000f78d  mov     [rbp+590h+var_5F0], ecx
0x18000f790  test    dil, 40h
0x18000f794  jz      short loc_18000F79A
0x18000f796  mov     [r14+60h], r15d
0x18000f79a  call    ?GetDriverValidationPolicyLevel@@YA?AW4_DRIVER_VALIDATION_LEVEL@@XZ; GetDriverValidationPolicyLevel(void)
0x18000f79f  mov     esi, eax
0x18000f7a1  call    ?IsTestSigningEnabled@@YAHXZ; IsTestSigningEnabled(void)
0x18000f7a6  test    eax, eax
0x18000f7a8  jnz     loc_18000F885
0x18000f7ae  cmp     esi, 3
0x18000f7b1  ja      loc_18000F885
0x18000f7b7  mov     rdx, [rbx]
0x18000f7ba  mov     ecx, esi
0x18000f7bc  call    PSetupValidateDriver
0x18000f7c1  xor     r8d, r8d
0x18000f7c4  mov     r10d, eax
0x18000f7c7  test    eax, eax
0x18000f7c9  jns     loc_18000F885
0x18000f7cf  mov     ecx, eax; int
0x18000f7d1  mov     [rsp+690h+InfHandle], 0FFFFFFFFFFFFFFFFh
0x18000f7da  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000f7df  mov     edi, eax
0x18000f7e1  test    rbx, rbx
0x18000f7e4  jz      short loc_18000F7F8
0x18000f7e6  cmp     [rbx+0ACh], r8d
0x18000f7ed  jz      short loc_18000F7F8
0x18000f7ef  mov     rcx, [rbx+0E0h]
0x18000f7f6  jmp     short loc_18000F800
0x18000f7f8  mov     rcx, r8
0x18000f7fb  test    rbx, rbx
0x18000f7fe  jz      short loc_18000F809
0x18000f800  mov     r9d, [rbx+0ACh]
0x18000f807  jmp     short loc_18000F80C
0x18000f809  mov     r9d, r8d
0x18000f80c  movsxd  r15, [rsp+690h+IsMember]
0x18000f811  lea     rdx, PlatformEnv
0x18000f818  mov     r11, [rdx+r15*8]
0x18000f81c  test    rbx, rbx
0x18000f81f  jz      short loc_18000F831
0x18000f821  mov     rax, [rbx]
0x18000f824  mov     rdx, [rbx+8]
0x18000f828  mov     r8, [rbx+0B8h]
0x18000f82f  jmp     short loc_18000F837
0x18000f831  mov     rax, r8
0x18000f834  mov     rdx, r8
0x18000f837  mov     [rsp+690h+var_638], r10d; unsigned int
0x18000f83c  mov     dword ptr [rsp+690h+DeviceInfoData], edi; unsigned int
0x18000f840  mov     [rsp+690h+DeviceInfoSet], rcx; unsigned __int16 *
0x18000f845  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000f84c  mov     dword ptr [rsp+690h+var_650], r9d; int
0x18000f851  mov     r9, r13; unsigned __int16 *
0x18000f854  mov     [rsp+690h+MsgHandler], r11; unsigned __int16 *
0x18000f859  mov     qword ptr [rsp+690h+CopyFlags], r8; unsigned __int16 *
0x18000f85e  lea     r8, aDrivervalidati; "DriverValidation"
0x18000f865  mov     [rsp+690h+Result], rdx; unsigned __int16 *
0x18000f86a  lea     rdx, aLegacyprintdri; "LegacyPrintDriverInstall"
0x18000f871  mov     [rsp+690h+Reserved2], rax; unsigned __int16 *
0x18000f876  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000f87b  mov     r12d, [rsp+690h+var_620]
0x18000f880  jmp     loc_180010929
0x18000f885  mov     rcx, [rbx]; unsigned __int16 *
0x18000f888  xor     edx, edx
0x18000f88a  call    OpenPrinterInfFile
0x18000f88f  mov     [rsp+690h+InfHandle], rax
0x18000f894  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f898  jz      loc_18001091C
0x18000f89e  movsxd  rsi, [rsp+690h+IsMember]
0x18000f8a3  cmp     esi, cs:MyPlatform
0x18000f8a9  jz      loc_18000F99A
0x18000f8af  xor     ecx, ecx
0x18000f8b1  lea     r9, [rbp+590h+Context]; Context
0x18000f8b5  mov     qword ptr [rbp+590h+Context.Section], rcx
0x18000f8b9  lea     r8, Key; "LayoutFile"
0x18000f8c0  xorps   xmm0, xmm0
0x18000f8c3  lea     rdx, cszVersion; "Version"
0x18000f8ca  mov     rcx, rax; InfHandle
0x18000f8cd  movups  xmmword ptr [rbp+590h+Context.Inf], xmm0
0x18000f8d1  call    cs:__imp_SetupFindFirstLineW
0x18000f8d7  test    eax, eax
0x18000f8d9  jz      loc_18000F995
0x18000f8df  mov     edi, 661h
0x18000f8e4  mov     ecx, edi; dwErrCode
0x18000f8e6  call    cs:__imp_SetLastError
0x18000f8ec  xor     esi, esi
0x18000f8ee  test    rbx, rbx
0x18000f8f1  jz      short loc_18000F904
0x18000f8f3  cmp     [rbx+0ACh], esi
0x18000f8f9  jz      short loc_18000F904
0x18000f8fb  mov     rcx, [rbx+0E0h]
0x18000f902  jmp     short loc_18000F90C
0x18000f904  mov     rcx, rsi
0x18000f907  test    rbx, rbx
0x18000f90a  jz      short loc_18000F915
0x18000f90c  mov     r9d, [rbx+0ACh]
0x18000f913  jmp     short loc_18000F918
0x18000f915  mov     r9d, esi
0x18000f918  movsxd  r15, [rsp+690h+IsMember]
0x18000f91d  lea     rdx, PlatformEnv
0x18000f924  mov     r10, [rdx+r15*8]
0x18000f928  test    rbx, rbx
0x18000f92b  jz      short loc_18000F93D
0x18000f92d  mov     rax, [rbx]
0x18000f930  mov     rdx, [rbx+8]
0x18000f934  mov     r8, [rbx+0B8h]
0x18000f93b  jmp     short loc_18000F946
0x18000f93d  mov     rax, rsi
0x18000f940  mov     rdx, rsi
0x18000f943  mov     r8, rsi
0x18000f946  mov     [rsp+690h+var_638], 80070661h; unsigned int
0x18000f94e  mov     dword ptr [rsp+690h+DeviceInfoData], edi; unsigned int
0x18000f952  mov     [rsp+690h+DeviceInfoSet], rcx; unsigned __int16 *
0x18000f957  mov     dword ptr [rsp+690h+var_650], r9d; int
0x18000f95c  mov     [rsp+690h+MsgHandler], r10; unsigned __int16 *
0x18000f961  mov     qword ptr [rsp+690h+CopyFlags], r8; unsigned __int16 *
0x18000f966  lea     r8, aSetupfindfirst; "SetupFindFirstLine(Version, LayoutFile)"...
0x18000f96d  mov     [rsp+690h+Result], rdx; unsigned __int16 *
0x18000f972  mov     r9, r13; unsigned __int16 *
0x18000f975  lea     rdx, aLegacyprintdri; "LegacyPrintDriverInstall"
0x18000f97c  mov     [rsp+690h+Reserved2], rax; unsigned __int16 *
0x18000f981  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000f988  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000f98d  mov     r12d, esi
0x18000f990  jmp     loc_18001092B
0x18000f995  mov     rax, [rsp+690h+InfHandle]
0x18000f99a  xor     r8d, r8d; ErrorLine
0x18000f99d  mov     rdx, rax; InfHandle
0x18000f9a0  xor     ecx, ecx; FileName
0x18000f9a2  call    cs:__imp_SetupOpenAppendInfFileW
0x18000f9a8  lea     rax, PlatformEnv
0x18000f9af  mov     rcx, r12; OwnerWindow
0x18000f9b2  mov     rax, [rax+rsi*8]
0x18000f9b6  mov     [r14+70h], rax
0x18000f9ba  test    dil, 10h
0x18000f9be  jz      loc_18000FAB1
0x18000f9c4  xor     r9d, r9d; Reserved1
0x18000f9c7  mov     [rsp+690h+Reserved2], 0; Reserved2
0x18000f9d0  xor     r8d, r8d; ProgressMessage
0x18000f9d3  or      rdx, 0FFFFFFFFFFFFFFFFh; AlternateProgressWindow
0x18000f9d7  call    cs:__imp_SetupInitDefaultQueueCallbackEx
0x18000f9dd  mov     [rbp+590h+var_5D8], rax
0x18000f9e1  test    rax, rax
0x18000f9e4  jnz     loc_18000FB6B
0x18000f9ea  call    cs:__imp_GetLastError
0x18000f9f0  xor     r8d, r8d
0x18000f9f3  test    eax, eax
0x18000f9f5  jg      short loc_18000F9FB
0x18000f9f7  mov     ecx, eax
0x18000f9f9  jmp     short loc_18000FA04
0x18000f9fb  movzx   ecx, ax
0x18000f9fe  or      ecx, 80070000h
0x18000fa04  test    rbx, rbx
0x18000fa07  jz      short loc_18000FA1B
0x18000fa09  cmp     [rbx+0ACh], r8d
0x18000fa10  jz      short loc_18000FA1B
0x18000fa12  mov     rdx, [rbx+0E0h]
0x18000fa19  jmp     short loc_18000FA23
0x18000fa1b  mov     rdx, r8
0x18000fa1e  test    rbx, rbx
0x18000fa21  jz      short loc_18000FA47
0x18000fa23  mov     r11d, [rbx+0ACh]
0x18000fa2a  lea     r9, PlatformEnv
0x18000fa31  mov     rdi, [r9+rsi*8]
0x18000fa35  xor     esi, esi
0x18000fa37  mov     r9, [rbx+8]
0x18000fa3b  mov     r8, [rbx]
0x18000fa3e  mov     r10, [rbx+0B8h]
0x18000fa45  jmp     short loc_18000FA5F
0x18000fa47  lea     rdx, PlatformEnv
0x18000fa4e  mov     rdi, [rdx+rsi*8]
0x18000fa52  xor     esi, esi
0x18000fa54  mov     r9d, esi
0x18000fa57  mov     r10d, esi
0x18000fa5a  mov     r11d, esi
0x18000fa5d  mov     edx, esi
0x18000fa5f  mov     [rsp+690h+var_638], ecx; unsigned int
0x18000fa63  mov     dword ptr [rsp+690h+DeviceInfoData], eax; unsigned int
0x18000fa67  mov     [rsp+690h+DeviceInfoSet], rdx; unsigned __int16 *
0x18000fa6c  mov     dword ptr [rsp+690h+var_650], r11d; int
0x18000fa71  mov     [rsp+690h+MsgHandler], rdi; unsigned __int16 *
0x18000fa76  mov     qword ptr [rsp+690h+CopyFlags], r10; unsigned __int16 *
0x18000fa7b  mov     [rsp+690h+Result], r9; unsigned __int16 *
0x18000fa80  mov     [rsp+690h+Reserved2], r8; unsigned __int16 *
0x18000fa85  lea     r8, aSetupinitdefau_0; "SetupInitDefaultQueueCallbackEx failed"
0x18000fa8c  mov     r9, r13; unsigned __int16 *
0x18000fa8f  lea     rdx, aLegacyprintdri; "LegacyPrintDriverInstall"
0x18000fa96  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000fa9d  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000faa2  mov     r15d, [rsp+690h+IsMember]
0x18000faa7  mov     r12d, [rsp+690h+var_620]
0x18000faac  jmp     loc_18001092B
0x18000fab1  call    cs:__imp_SetupInitDefaultQueueCallback
0x18000fab7  mov     [rbp+590h+var_5D8], rax
0x18000fabb  test    rax, rax
0x18000fabe  jnz     loc_18000FB6B
0x18000fac4  call    cs:__imp_GetLastError
0x18000faca  xor     r8d, r8d
0x18000facd  test    eax, eax
0x18000facf  jg      short loc_18000FAD5
0x18000fad1  mov     ecx, eax
0x18000fad3  jmp     short loc_18000FADE
0x18000fad5  movzx   ecx, ax
0x18000fad8  or      ecx, 80070000h
0x18000fade  test    rbx, rbx
0x18000fae1  jz      short loc_18000FAF5
0x18000fae3  cmp     [rbx+0ACh], r8d
0x18000faea  jz      short loc_18000FAF5
0x18000faec  mov     rdx, [rbx+0E0h]
0x18000faf3  jmp     short loc_18000FAFD
0x18000faf5  mov     rdx, r8
0x18000faf8  test    rbx, rbx
0x18000fafb  jz      short loc_18000FB21
0x18000fafd  mov     r11d, [rbx+0ACh]
0x18000fb04  lea     r9, PlatformEnv
0x18000fb0b  mov     rdi, [r9+rsi*8]
0x18000fb0f  xor     esi, esi
0x18000fb11  mov     r9, [rbx+8]
0x18000fb15  mov     r8, [rbx]
0x18000fb18  mov     r10, [rbx+0B8h]
0x18000fb1f  jmp     short loc_18000FB39
0x18000fb21  lea     rdx, PlatformEnv
0x18000fb28  mov     rdi, [rdx+rsi*8]
0x18000fb2c  xor     esi, esi
0x18000fb2e  mov     r9d, esi
0x18000fb31  mov     r10d, esi
0x18000fb34  mov     r11d, esi
0x18000fb37  mov     edx, esi
0x18000fb39  mov     [rsp+690h+var_638], ecx
0x18000fb3d  mov     dword ptr [rsp+690h+DeviceInfoData], eax
0x18000fb41  mov     [rsp+690h+DeviceInfoSet], rdx
0x18000fb46  mov     dword ptr [rsp+690h+var_650], r11d
0x18000fb4b  mov     [rsp+690h+MsgHandler], rdi
0x18000fb50  mov     qword ptr [rsp+690h+CopyFlags], r10
0x18000fb55  mov     [rsp+690h+Result], r9
0x18000fb5a  mov     [rsp+690h+Reserved2], r8
0x18000fb5f  lea     r8, aSetupinitdefau; "SetupInitDefaultQueueCallback failed"
0x18000fb66  jmp     loc_18000FA8C
0x18000fb6b  mov     edx, 448h; uBytes
0x18000fb70  mov     ecx, 40h ; '@'; uFlags
0x18000fb75  call    cs:__imp_LocalAlloc
0x18000fb7b  xor     edx, edx
  ... truncated ...
```
