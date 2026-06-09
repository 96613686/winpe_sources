# InternalAddPrinterDriverEx

- ea: `0x1800705a0`
- end: `0x1800718da`
- name: `InternalAddPrinterDriverEx`
- size: `4922`
- prototype: `__int64 __fastcall(const WCHAR *, unsigned int, __int64, unsigned int, struct _INISPOOLER *, int, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `50`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180069e20`
- `0x1800b81d0`

## callees

- `0x180007e94`
- `0x180008520`
- `0x180008560`
- `0x180009630`
- `0x18000a100`
- `0x18000a41c`
- `0x18000ba20`
- `0x18000c380`
- `0x18000c5fc`
- `0x18000d40c`
- `0x180011f00`
- `0x1800146e8`
- `0x18001fb10`
- `0x180020690`
- `0x18002db3c`
- `0x18002dc20`
- `0x18002ff50`
- `0x180035644`
- `0x180035ae4`
- `0x1800361c8`
- `0x18003a888`
- `0x18003d0a4`
- `0x18003e984`
- `0x18003ea2c`
- `0x18003fdbc`
- `0x180043740`
- `0x1800444e8`
- `0x180046650`
- `0x180046a20`
- `0x180047330`
- `0x180054638`
- `0x180069f64`
- `0x18006a41c`
- `0x18006c1c0`
- `0x18006c870`
- `0x18006ca34`
- `0x18006d224`
- `0x18006e330`
- `0x18006e520`
- `0x18006ed08`
- `0x18006f624`
- `0x18006fb94`
- `0x180070584`
- `0x1800705a0`
- `0x1800718e0`
- `0x180071b20`
- `0x180072110`
- `0x1800ca578`
- `0x1800ccbd8`
- `0x1800d8a90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180070b97`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007169c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e4d13`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180070b97`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007169c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e4d13`
- `ntdll!RtlPublishWnfStateData` at `0x1800709fe`
- `ntdll!RtlPublishWnfStateData` at `0x1800709fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800707d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800708b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070da8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007117a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007128d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800712a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800712bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800712d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007134c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007137f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800717bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800707d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800708b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070da8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007117a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007128d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800712a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800712bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800712d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007134c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007137f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800717bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4d97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007064f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070d7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800715e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071645`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071740`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800718bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e4c54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e4cbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e4dc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007064f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070d7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800715e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071645`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071740`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800718bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e4c54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e4cbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e4dc0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180070de9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180070de9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180070fba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180070fba`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800709d5`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800709d5`
- `SPOOLSS!AllocSplStr` at `0x180071523`
- `SPOOLSS!AllocSplStr` at `0x180071538`
- `SPOOLSS!AllocSplStr` at `0x180071567`
- `SPOOLSS!AllocSplStr` at `0x18007157c`
- `SPOOLSS!AllocSplStr` at `0x1800715ab`
- `SPOOLSS!AllocSplStr` at `0x1800715bd`
- `SPOOLSS!AllocSplStr` at `0x1800715d2`
- `SPOOLSS!AllocSplStr` at `0x1800e4c01`
- `SPOOLSS!AllocSplStr` at `0x1800e4c0e`
- `SPOOLSS!AllocSplStr` at `0x1800e4c1b`
- `SPOOLSS!AllocSplStr` at `0x1800e4c28`
- `SPOOLSS!AllocSplStr` at `0x1800e4c35`
- `SPOOLSS!AllocSplStr` at `0x1800e4c3f`
- `SPOOLSS!AllocSplStr` at `0x1800e4c4c`
- `SPOOLSS!AllocSplStr` at `0x180071523`
- `SPOOLSS!AllocSplStr` at `0x180071538`
- `SPOOLSS!AllocSplStr` at `0x180071567`
- `SPOOLSS!AllocSplStr` at `0x18007157c`
- `SPOOLSS!AllocSplStr` at `0x1800715ab`
- `SPOOLSS!AllocSplStr` at `0x1800715bd`
- `SPOOLSS!AllocSplStr` at `0x1800715d2`
- `SPOOLSS!AllocSplStr` at `0x1800e4c01`
- `SPOOLSS!AllocSplStr` at `0x1800e4c0e`
- `SPOOLSS!AllocSplStr` at `0x1800e4c1b`
- `SPOOLSS!AllocSplStr` at `0x1800e4c28`
- `SPOOLSS!AllocSplStr` at `0x1800e4c35`
- `SPOOLSS!AllocSplStr` at `0x1800e4c3f`
- `SPOOLSS!AllocSplStr` at `0x1800e4c4c`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180070a28`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180070a28`

## string_xrefs

- `0x180071808`: `Install`
- `0x180070637`: `Trying to install printer driver %ws but installation of printer drivers is not allowed in ContainerOS`
- `0x1800707bf`: `INF install of driver '%ws', inf name '%ws', root '%ws' onto server '%ws' failed.  Error %d`
- `0x18007089b`: `INF install of driver '%ws' onto server '%ws' failed.  Error %d`
- `0x1800707e6`: `InternalINFInstallDriver`
- `0x1800708bd`: `CreateInternalDriverFileArray`
- `0x180070a44`: `Failed to impersonate client after publishing WNF notification for driver '%ws'!`
- `0x180070a58`: `Failed to copy driver information for WNF notification!`
- `0x1800712fc`: `Driver architecture is incompatible with this machine.  Failing install.`
- `0x180070b6b`: `Driver '%ws' is a v4 driver.  Failing install.`
- `0x180070b4a`: `Driver '%ws' is a KM driver.  Failing install.`
- `0x180070bae`: `Installation of driver '%ws' failed, because v3 drivers are not supported on ARM.`
- `0x180070c20`: `Driver '%ws' is blocked from install.  Failing install.`
- `0x180070db4`: `Failed to create version directory for driver '%ws'.  Error %d.`
- `0x180070e03`: `Cannot complete upgrade for driver '%ws' because the replacement driver is older`
- `0x180070d67`: `Cannot complete upgrade for driver '%ws' because class to non-class upgrades are not supported`
- `0x180070efc`: `Driver Installation`
- `0x180071791`: `Driver Installation`
- `0x180070e3e`: `Cannot complete upgrade for driver '%ws' due to sharing`
- `0x180071049`: `Driver '%ws' is already installed, continue installation to associate language monitor '%ws'`
- `0x180070fdf`: `Existing driver '%ws' has a bad INF path: '%ws'`
- `0x1800710f5`: `CheckFileCopyOptions`
- `0x1800710dd`: `CheckFileCopyOptions failed for driver '%ws'.  Error %d.`
- `0x1800710c5`: `CopyFilesToFinalDirectory`
- `0x1800710ad`: `CopyFilesToFinalDirectory failed for driver '%ws'.  Error %d.`
- `0x18007119b`: `SetDependentFilesCommon`
- `0x180071186`: `SetDependentFilesCommon for driver '%ws' failed.  Error %d.`
- `0x1800712b1`: `AddTempDriver`
- `0x180071299`: `AddTempDriver for driver '%ws' failed.  Error %d.`
- `0x18007139c`: `Driver '%ws' could not be moved, and the driver is still loaded.  Failing installation.`
- `0x1800e4a79`: `Driver '%ws' could not be moved, and the driver is still loaded.  Failing installation.`
- `0x18007161b`: `Driver '%ws' installation failed.  Error %d.`
- `0x1800e4c8b`: `Driver '%ws' installation failed.  Error %d.`
- `0x18007172c`: `Could not delete KMPD driver %ws. Error %d`
- `0x1800e4da7`: `Could not delete KMPD driver %ws. Error %d`
- `0x18007170f`: `Deleted driver %ws because it is was KMPD`
- `0x1800e4d82`: `Deleted driver %ws because it is was KMPD`

## pseudocode

```c
__int64 __fastcall InternalAddPrinterDriverEx(
        const WCHAR *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        struct _INISPOOLER *a5,
        int a6,
        int a7,
        unsigned __int16 *a8)
{
  const unsigned __int16 *v9; // rbx
  DWORD IsCompatibleDriver; // edi
  struct _INTERNAL_DRV_FILE *v12; // r13
  struct _INIDRIVER *DriverInEnvironment; // r15
  const unsigned __int16 *v14; // rsi
  unsigned int v15; // ebx
  unsigned int v16; // r14d
  DWORD v17; // eax
  struct _INISPOOLER *v18; // r8
  DWORD v19; // eax
  HANDLE v20; // rbx
  int v21; // eax
  unsigned int v22; // edi
  DWORD LastError; // eax
  const unsigned __int16 *v24; // r9
  const unsigned __int16 *v25; // rdx
  unsigned int v26; // r8d
  int v27; // ebx
  struct _INIENVIRONMENT *v28; // rbx
  struct _INIVERSION *VersionEntry; // rax
  unsigned int v30; // edx
  struct _INIENVIRONMENT *v31; // rcx
  struct SplLogType *v32; // rax
  __int64 v33; // r10
  DWORD v34; // eax
  LONG v35; // eax
  __int64 i; // rcx
  const unsigned __int16 *v37; // rdx
  struct SplLogType *v38; // rax
  __int64 v39; // r10
  __int64 v40; // r11
  struct SplLogType *v41; // rax
  __int64 v42; // r10
  unsigned int v43; // ecx
  struct _INIDRIVER *v44; // r8
  struct _INISPOOLER *v45; // rcx
  unsigned int v46; // ecx
  unsigned int v47; // eax
  int v48; // eax
  _WORD *v49; // r9
  DWORD v50; // eax
  DWORD v51; // eax
  DWORD v52; // eax
  unsigned int v53; // ebx
  DWORD v54; // eax
  DWORD v55; // eax
  DWORD v56; // eax
  struct _INIVERSION *v57; // rbx
  struct _INIDRIVER *DriverEntry; // r13
  __int64 v59; // rcx
  struct _INISPOOLER *v60; // rbx
  unsigned __int16 *v61; // rbx
  DWORD v62; // eax
  DWORD v63; // ebx
  int v64; // eax
  unsigned int v65; // r13d
  unsigned int v66; // eax
  DWORD v67; // eax
  const unsigned __int16 *v68; // rdx
  struct SplLogType *v69; // rax
  __int64 v70; // r10
  DWORD v71; // ebx
  bool v72; // cf
  unsigned int v73; // edx
  unsigned __int64 v74; // r8
  const unsigned __int16 *v75; // rcx
  struct _INIDRIVER *v76; // [rsp+C8h] [rbp-8E8h]
  struct _INIDRIVER *v77; // [rsp+C8h] [rbp-8E8h]
  struct _INIDRIVER *v78; // [rsp+C8h] [rbp-8E8h]
  DWORD v79; // [rsp+D8h] [rbp-8D8h]
  struct _INISPOOLER *v80; // [rsp+D8h] [rbp-8D8h]
  struct _INIVERSION *v81; // [rsp+E0h] [rbp-8D0h]
  unsigned int v82; // [rsp+F0h] [rbp-8C0h]
  unsigned int v83; // [rsp+138h] [rbp-878h] BYREF
  unsigned int v84; // [rsp+13Ch] [rbp-874h] BYREF
  int v85; // [rsp+140h] [rbp-870h] BYREF
  unsigned int v86; // [rsp+144h] [rbp-86Ch]
  int v87; // [rsp+148h] [rbp-868h]
  unsigned int v88; // [rsp+14Ch] [rbp-864h]
  struct _INIENVIRONMENT *IniKey; // [rsp+150h] [rbp-860h]
  __int16 v90; // [rsp+158h] [rbp-858h] BYREF
  struct _INISPOOLER *v91; // [rsp+160h] [rbp-850h]
  int v92; // [rsp+168h] [rbp-848h]
  unsigned int v93; // [rsp+16Ch] [rbp-844h] BYREF
  struct _INIVERSION *v94; // [rsp+170h] [rbp-840h]
  unsigned __int16 *v95; // [rsp+178h] [rbp-838h] BYREF
  struct _INTERNAL_DRV_FILE *v96; // [rsp+180h] [rbp-830h] BYREF
  LPCWSTR lpString1; // [rsp+188h] [rbp-828h]
  const unsigned __int16 *v98; // [rsp+190h] [rbp-820h]
  int v99; // [rsp+198h] [rbp-818h] BYREF
  unsigned __int16 *v100; // [rsp+1A0h] [rbp-810h]
  unsigned int v101; // [rsp+1A8h] [rbp-808h]
  DWORD v102; // [rsp+1B0h] [rbp-800h] BYREF
  __int64 v103; // [rsp+1B8h] [rbp-7F8h]
  int v104; // [rsp+1C0h] [rbp-7F0h]
  struct _INISPOOLER *v105; // [rsp+1C8h] [rbp-7E8h]
  unsigned __int16 *v106; // [rsp+1D8h] [rbp-7D8h] BYREF
  unsigned __int16 *v107; // [rsp+1E0h] [rbp-7D0h]
  unsigned __int64 v108; // [rsp+1E8h] [rbp-7C8h]
  unsigned int v109; // [rsp+1F0h] [rbp-7C0h]
  unsigned __int16 *v110; // [rsp+1F8h] [rbp-7B8h]
  unsigned __int16 *v111; // [rsp+200h] [rbp-7B0h]
  unsigned int v112; // [rsp+208h] [rbp-7A8h]
  struct _FILETIME v113; // [rsp+20Ch] [rbp-7A4h]
  unsigned __int16 *v114; // [rsp+218h] [rbp-798h]
  unsigned __int16 *v115; // [rsp+220h] [rbp-790h]
  unsigned __int16 *v116; // [rsp+228h] [rbp-788h]
  int v117; // [rsp+238h] [rbp-778h]
  __int64 v118; // [rsp+240h] [rbp-770h]
  const WCHAR *v119; // [rsp+248h] [rbp-768h]
  int v120; // [rsp+250h] [rbp-760h] BYREF
  __int64 v121; // [rsp+258h] [rbp-758h]
  int v122; // [rsp+260h] [rbp-750h]
  int v123; // [rsp+268h] [rbp-748h] BYREF
  __int64 v124; // [rsp+270h] [rbp-740h]
  int v125; // [rsp+278h] [rbp-738h]
  unsigned __int16 *v126; // [rsp+280h] [rbp-730h]
  struct _INIDRIVER *v127; // [rsp+288h] [rbp-728h]
  _BYTE v128[24]; // [rsp+290h] [rbp-720h] BYREF
  _BYTE v129[24]; // [rsp+2A8h] [rbp-708h] BYREF
  _BYTE v130[24]; // [rsp+2C0h] [rbp-6F0h] BYREF
  _BYTE v131[24]; // [rsp+2D8h] [rbp-6D8h] BYREF
  _BYTE v132[24]; // [rsp+2F0h] [rbp-6C0h] BYREF
  _BYTE v133[24]; // [rsp+308h] [rbp-6A8h] BYREF
  _BYTE v134[24]; // [rsp+320h] [rbp-690h] BYREF
  _BYTE v135[4]; // [rsp+338h] [rbp-678h] BYREF
  unsigned __int16 v136[260]; // [rsp+33Ch] [rbp-674h] BYREF
  int v137; // [rsp+544h] [rbp-46Ch]
  unsigned __int16 v138[264]; // [rsp+548h] [rbp-468h] BYREF
  unsigned __int16 v139[216]; // [rsp+758h] [rbp-258h] BYREF

  v84 = a4;
  v86 = a2;
  lpString1 = a1;
  v119 = a1;
  v101 = a2;
  v118 = a3;
  v91 = a5;
  v105 = a5;
  if ( (unsigned int)RunningInContainerOS() )
  {
    v9 = *(const unsigned __int16 **)(a3 + 40);
    if ( !(unsigned int)IsDriverAllowedInContainerOS(v9) )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "InternalAddPrinterDriverEx",
        L"Trying to install printer driver %ws but installation of printer drivers is not allowed in ContainerOS",
        v9);
      SetLastError(0x32u);
      return 0;
    }
  }
  IsCompatibleDriver = 0;
  v87 = 0;
  v85 = 0;
  v93 = 0;
  v100 = 0;
  v12 = 0;
  v96 = 0;
  v88 = 0;
  DriverInEnvironment = 0;
  IniKey = 0;
  v94 = 0;
  v14 = 0;
  v98 = 0;
  v99 = 0;
  v15 = 0;
  v83 = 0;
  memset_0(v139, 0, 0x208u);
  LODWORD(v95) = 0;
  v92 = 0;
  memset_0(&v106, 0, 0x58u);
  v90 = -1;
  EnterSplSem(0);
  if ( !(unsigned int)MyName(lpString1) )
  {
    v16 = v86;
    goto LABEL_105;
  }
  v16 = v86;
  if ( !(unsigned int)ValidateDriverInfo((struct _DRIVER_INFO_VERSION *)a3, v86, v84, v91, a8) )
  {
LABEL_105:
    LODWORD(v76) = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"Server name '%ws' is invalid, or driver info (Level %d) failed validation.  Error %d",
      lpString1,
      v16,
      v76);
    LastError = GetLastError();
    v24 = lpString1;
    v25 = L"ValidateDriverInfo";
    goto LABEL_106;
  }
  if ( v86 == 7 )
  {
    ((void (*)(void))LeaveSplSem)();
    v85 = InternalINFInstallDriver(a3);
    if ( !v85 )
    {
      v79 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "InternalAddPrinterDriverEx",
        L"INF install of driver '%ws', inf name '%ws', root '%ws' onto server '%ws' failed.  Error %d",
        *(_QWORD *)(a3 + 8),
        *(_QWORD *)(a3 + 16),
        *(_QWORD *)(a3 + 24),
        lpString1,
        v79);
      v17 = GetLastError();
      SplLogGenericEvent(&LOCAL_ADDDRV_FAILED, L"InternalINFInstallDriver", v17, lpString1);
    }
    EnterSplSem(0);
    goto LABEL_108;
  }
  v14 = *(const unsigned __int16 **)(a3 + 8);
  v98 = v14;
  v100 = *(unsigned __int16 **)(a3 + 16);
  v126 = v100;
  IniKey = (struct _INIENVIRONMENT *)FindIniKey(*((_QWORD *)v91 + 6), v100, 0);
  if ( !(unsigned int)CreateInternalDriverFileArray(v86, (unsigned __int8 *)a3, &v96, &v83, a6, IniKey, 0) )
  {
    LODWORD(v77) = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"INF install of driver '%ws' onto server '%ws' failed.  Error %d",
      v14,
      lpString1,
      v77);
    v19 = GetLastError();
    SplLogGenericEvent(&LOCAL_ADDDRV_FAILED, L"CreateInternalDriverFileArray", v19, v14);
    v12 = v96;
LABEL_12:
    v15 = v83;
    goto LABEL_108;
  }
  if ( (int)GetProcessorArchitectureFromEnvironmentString(szEnvironment, &v90) < 0
    || v90 != 12
    || (unsigned __int8)IsServerSKU() )
  {
    v12 = v96;
LABEL_27:
    v15 = v83;
    goto LABEL_28;
  }
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "InternalAddPrinterDriverEx",
    L"Checking if ARM64 is supported for driver: %ws",
    v14);
  v15 = v83;
  v12 = v96;
  if ( v83 && !(unsigned int)CheckFilePlatform(*(_QWORD *)v96, L"Windows ARM64") )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"ARM64 is not supported by driver: %ws",
      v14);
    memset_0(v135, 0, 0x418u);
    v137 = 2;
    if ( (int)StringCchCopyW(v136, 0x104u, v14) >= 0
      && (int)StringCchCopyW(v138, 0x104u, *(const unsigned __int16 **)v12) >= 0 )
    {
      v20 = RevertToPrinterSelf();
      v21 = RtlPublishWnfStateData(WNF_PNPF_DRIVER_NO_NATIVE_ARCHITECTURE_SUPPORT, 0, v135, 1048, 0) | 0x10000000;
      if ( v21 < 0 )
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "InternalAddPrinterDriverEx",
          L"Failed to publish WNF notification for driver '%ws' with hr: 0x%x!",
          v14,
          (unsigned int)v21);
      if ( v20 && !ImpersonatePrinterClient(v20) )
      {
        IsCompatibleDriver = GetLastError();
        v87 = IsCompatibleDriver;
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "InternalAddPrinterDriverEx",
          L"Failed to impersonate client after publishing WNF notification for driver '%ws'!",
          v14);
        goto LABEL_12;
      }
      goto LABEL_27;
    }
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"Failed to copy driver information for WNF notification!");
  }
LABEL_28:
  if ( a6 || (v84 & 0x10) != 0 )
  {
    if ( !(unsigned int)GetPrintDriverVersion(*(LPCWSTR *)v12) )
    {
      LODWORD(v77) = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "InternalAddPrinterDriverEx",
        L"Version check for driver '%ws' onto server '%ws' failed.  Error %d",
        v14,
        lpString1,
        v77);
      LastError = GetLastError();
      v24 = v14;
      v25 = L"GetPrinterDriverVersion";
LABEL_106:
      v26 = LastError;
      goto LABEL_107;
    }
    v22 = v88;
    *(_DWORD *)a3 = v88;
    if ( !v15
      || !(unsigned int)CheckFilePlatform(*(_QWORD *)v12, v100)
      || v15 <= 1
      || !(unsigned int)CheckFilePlatform(*((_QWORD *)v12 + 4), v100) )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "InternalAddPrinterDriverEx",
        L"Driver architecture is incompatible with this machine.  Failing install.");
      IsCompatibleDriver = 216;
      goto LABEL_103;
    }
  }
  else
  {
    v22 = *(_DWORD *)a3;
    v88 = *(_DWORD *)a3;
  }
  if ( v22 == 2 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"Driver '%ws' is a KM driver.  Failing install.",
      v14);
    IsCompatibleDriver = 1930;
LABEL_103:
    v87 = IsCompatibleDriver;
    goto LABEL_108;
  }
  if ( v22 > 3 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"Driver '%ws' is a v4 driver.  Failing install.",
      v14);
    IsCompatibleDriver = 3014;
    goto LABEL_103;
  }
  if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)IniKey + 3), L"Windows ARM") )
  {
    IsCompatibleDriver = 50;
    v87 = 50;
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"Installation of driver '%ws' failed, because v3 drivers are not supported on ARM.",
      v14);
    v24 = v14;
    v26 = 50;
    v25 = L"InternalAddPrinterDriverEx";
LABEL_107:
    SplLogGenericEvent(&LOCAL_ADDDRV_FAILED, v25, v26, v24);
    goto LABEL_108;
  }
  ((void (*)(void))LeaveSplSem)();
  IsCompatibleDriver = SplIsCompatibleDriver((_DWORD)v14, *(_QWORD *)v12, *(_QWORD *)(a3 + 16), v22, (char)&v99);
  v87 = IsCompatibleDriver;
  EnterSplSem(0);
  v18 = 0;
  if ( IsCompatibleDriver )
    goto LABEL_12;
  if ( (_BYTE)v99 == 1 )
  {
    v27 = 1;
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"Driver '%ws' is blocked from install.  Failing install.",
      v14);
    IsCompatibleDriver = 3014;
    v87 = 3014;
  }
  else
  {
    v27 = 0;
  }
  if ( v27 )
  {
    if ( (v84 & 0x10000) == 0 )
      IsCompatibleDriver = 1797;
    v87 = IsCompatibleDriver;
    SplLogEvent(&MSG_BAD_OEM_DRIVER, IsCompatibleDriver, v14, 0);
    goto LABEL_12;
  }
  v28 = IniKey;
  VersionEntry = (struct _INIVERSION *)FindVersionEntry(IniKey, v88);
  v94 = VersionEntry;
  if ( VersionEntry )
  {
    if ( !(unsigned int)CreateVersionDirectory(VersionEntry, v28, 0, v91) )
    {
      v34 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "InternalAddPrinterDriverEx",
        L"Failed to create version directory for driver '%ws'.  Error %d.",
        v14,
        v34);
      goto LABEL_12;
    }
  }
  else
  {
    v94 = CreateVersionEntry(v31, v30, v91);
    if ( !v94 )
      goto LABEL_12;
  }
  DriverInEnvironment = FindDriverInEnvironment(v14, v28);
  v127 = DriverInEnvironment;
  if ( DriverInEnvironment )
  {
    v120 = 0;
    v121 = 4;
    v122 = 0;
    SplLogType::SplLogType((SplLogType *)v130, v14);
    v32 = SplLogType::SplLogType((SplLogType *)v131, L"Driver Upgrade");
    SplLogEvent2(&SPOOLER_OPERATION_START_EVENT, v32, v33, &v120, 0);
    if ( *((_DWORD *)DriverInEnvironment + 59) > 3u )
    {
      v92 = 1;
      v117 = 1;
      if ( (*((_BYTE *)DriverInEnvironment + 200) & 8) != 0 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "InternalAddPrinterDriverEx",
          L"Cannot complete upgrade for driver '%ws' because class to non-class upgrades are not supported",
          *((_QWORD *)DriverInEnvironment + 3));
LABEL_57:
        SetLastError(0xBC6u);
        goto LABEL_12;
      }
      if ( ((v86 - 6) & 0xFFFFFFFD) == 0 )
      {
        if ( *(_QWORD *)(a3 + 96) )
        {
          v35 = CompareFileTime((const FILETIME *)DriverInEnvironment + 14, (const FILETIME *)(a3 + 88));
          if ( v35 == 1 || !v35 && *((_QWORD *)DriverInEnvironment + 15) >= *(_QWORD *)(a3 + 96) )
          {
            LocalSpoolerTelemetry::WriteDbgTraceWarning(
              "InternalAddPrinterDriverEx",
              L"Cannot complete upgrade for driver '%ws' because the replacement driver is older",
              *((_QWORD *)DriverInEnvironment + 3));
            goto LABEL_57;
          }
        }
      }
      for ( i = *((_QWORD *)pLocalIniSpooler + 5); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(struct _INIDRIVER **)(i + 88) == DriverInEnvironment && (*(_BYTE *)(i + 152) & 8) != 0 )
        {
          LocalSpoolerTelemetry::WriteDbgTraceWarning(
            "InternalAddPrinterDriverEx",
            L"Cannot complete upgrade for driver '%ws' due to sharing",
            *((_QWORD *)DriverInEnvironment + 3));
          v123 = -2147021882;
          v124 = 4;
          v125 = 0;
          SplLogType::SplLogType((SplLogType *)v132, 0);
          SplLogType::SplLogType((SplLogType *)v133, v37);
          v38 = SplLogType::SplLogType((SplLogType *)v134, v14);
          SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_SHARING_BLOCK, v38, v39, v40, &v123, 0);
          goto LABEL_57;
        }
      }
    }
  }
  else
  {
    v102 = 0;
    v103 = 4;
    v104 = 0;
    SplLogType::SplLogType((SplLogType *)v128, v14);
    v41 = SplLogType::SplLogType((SplLogType *)v129, L"Driver Installation");
    SplLogEvent2(&SPOOLER_OPERATION_START_EVENT, v41, v42, &v102, 0);
  }
  v43 = v84 & 0xFFFC7FEF;
  v84 &= 0xFFFC7FEF;
  v44 = DriverInEnvironment;
  if ( v92 )
    v44 = 0;
  v15 = v83;
  if ( !(unsigned int)CheckFileCopyOptions(IniKey, v94, v44, v12, v83, v43, &v85, (int *)&v95) )
  {
    v46 = v86;
    v47 = v84;
    if ( v86 == 8 && v84 == 8 )
    {
      if ( GetFileAttributesW(*((LPCWSTR *)DriverInEnvironment + 24)) == -1
        && (unsigned int)IsInfInDriverStore(*(wchar_t **)(a3 + 160)) )
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "InternalAddPrinterDriverEx",
          L"Existing driver '%ws' has a bad INF path: '%ws'",
          *((_QWORD *)DriverInEnvironment + 3),
          *((_QWORD *)DriverInEnvironment + 24));
        goto LABEL_90;
      }
      v46 = v86;
      v47 = v84;
    }
    if ( !v85
      || v47 != 8
      || *((_QWORD *)DriverInEnvironment + 31)
      || v46 > 8
      || (v48 = 344, !_bittest(&v48, v46))
      || (v49 = *(_WORD **)(a3 + 64)) == 0
      || !*v49 )
    {
      v51 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "InternalAddPrinterDriverEx",
        L"CheckFileCopyOptions failed for driver '%ws'.  Error %d.",
        v14,
        v51);
      LastError = GetLastError();
      v24 = v14;
      v25 = L"CheckFileCopyOptions";
      goto LABEL_106;
    }
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "InternalAddPrinterDriverEx",
      L"Driver '%ws' is already installed, continue installation to associate language monitor '%ws'",
      *((_QWORD *)DriverInEnvironment + 3),
      v49);
  }
LABEL_90:
  if ( !CopyFilesToFinalDirectory(v45, IniKey, v94, v12, v15, v84, a7, (int *)&v93) )
  {
    v50 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"CopyFilesToFinalDirectory failed for driver '%ws'.  Error %d.",
      v14,
      v50);
    LastError = GetLastError();
    v24 = v14;
    v25 = L"CopyFilesToFinalDirectory";
    goto LABEL_106;
  }
  if ( (_DWORD)v95 )
  {
    if ( (unsigned int)SetDependentFilesCommon(
                         v86,
                         (unsigned __int8 *)a3,
                         v12,
                         v15,
                         DriverInEnvironment,
                         IniKey,
                         v80,
                         v81,
                         0,
                         1) )
    {
      v85 = WriteDriverIniInternal(DriverInEnvironment, v94, IniKey, v91, 1);
      goto LABEL_108;
    }
    v52 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"SetDependentFilesCommon for driver '%ws' failed.  Error %d.",
      v14,
      v52);
    v24 = v14;
    v26 = 0;
    v25 = L"SetDependentFilesCommon";
    goto LABEL_107;
  }
  v53 = v93;
  if ( !(unsigned int)WaitRequiredForDriverUnload(v91, IniKey, v94, DriverInEnvironment, v86, a3, v84, v12, v83) || !v85 )
  {
    v55 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"WaitRequiredForDriverUnload for driver '%ws' failed.  Error %d.",
      v14,
      v55);
    v56 = GetLastError();
    SplLogGenericEvent(&LOCAL_ADDDRV_FAILED, L"WaitRequiredForDriverUnload", v56, v14);
    goto LABEL_12;
  }
  v82 = v53;
  v15 = v83;
  v85 = AddTempDriver(v91, IniKey, v94, v86, (unsigned __int8 *)a3, v84, v12, v83, v88, v82, DriverInEnvironment);
  if ( !v85 )
  {
    v54 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"AddTempDriver for driver '%ws' failed.  Error %d.",
      v14,
      v54);
    LastError = GetLastError();
    v24 = v14;
    v25 = L"AddTempDriver";
    goto LABEL_106;
  }
LABEL_108:
  if ( !v85 && !IsCompatibleDriver )
  {
    IsCompatibleDriver = GetLastError();
    if ( !IsCompatibleDriver && !v93 )
    {
      IsCompatibleDriver = 1450;
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "InternalAddPrinterDriverEx",
        L"Driver '%ws' could not be moved, and the driver is still loaded.  Failing installation.",
        v14);
    }
  }
  if ( a6 && v15 )
    SetOldDateOnDriverFilesInScratchDirectory(v12, v15, v18);
  v57 = v94;
  DriverEntry = FindDriverEntry(v94, v14);
  v59 = 0;
  if ( DriverEntry )
  {
    if ( v57 )
    {
      if ( IniKey )
      {
        v78 = v57;
        v60 = v91;
        GetDriverVersionDirectory(
          (unsigned int)v139,
          258,
          (_DWORD)v91,
          (_DWORD)IniKey,
          (__int64)v78,
          (__int64)DriverEntry,
          0);
        StringCchCatW(v139, 0x104u, L"\\");
        StringCchCatW(v139, 0x104u, *((const unsigned __int16 **)DriverEntry + 4));
        if ( (*((_DWORD *)DriverEntry + 50) & 0x800) != 0 )
        {
          v95 = 0;
          v84 = 0;
          sandbox::SandboxManagerUtil::AddDriverToSandboxExclusionList(
            (sandbox::SandboxManagerUtil *)(*((_QWORD *)v60 + 46) + 128LL),
            *((const unsigned __int16 **)DriverEntry + 3),
            &v95,
            &v84);
          v61 = v95;
          if ( v95 )
          {
            v62 = SetPrinterDataServer(v91, L"PrintDriverIsolationGroups", 1, v95, 2 * v84);
            IsCompatibleDriver = v62;
            if ( v62 )
            {
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "InternalAddPrinterDriverEx",
                L"SetPrinterDataServer SPLREG_PRINT_DRIVER_ISOLATION_GROUPS '%ws' failed. Error %d",
                v61,
                v62);
              v85 = 0;
            }
            operator delete(v61, 2u);
          }
        }
      }
    }
  }
  if ( DriverEntry )
  {
    v63 = GetLastError();
    v106 = (unsigned __int16 *)AllocSplStr(*((_QWORD *)DriverEntry + 3));
    v107 = (unsigned __int16 *)AllocSplStr(*((_QWORD *)DriverEntry + 33));
    v108 = *((_QWORD *)DriverEntry + 15);
    v109 = *((_DWORD *)DriverEntry + 59);
    v110 = (unsigned __int16 *)AllocSplStr(*((_QWORD *)DriverEntry + 16));
    v111 = (unsigned __int16 *)AllocSplStr(&qword_1800EBF90);
    v112 = *((_DWORD *)DriverEntry + 50);
    v113 = (struct _FILETIME)*((_QWORD *)DriverEntry + 14);
    v114 = (unsigned __int16 *)AllocSplStr(*((_QWORD *)DriverEntry + 19));
    v115 = (unsigned __int16 *)AllocSplStr(*((_QWORD *)DriverEntry + 11));
    v116 = (unsigned __int16 *)AllocSplStr(*((_QWORD *)DriverEntry + 18));
    SetLastError(v63);
  }
  LeaveSplSem(v59);
  if ( v83 )
    CleanupInternalDriverInfo(v96);
  CleanUpgradeDirectories();
  if ( v85 )
  {
    SplLogGenericEvent(&LOCAL_ADDDRV_SUCCEEDED, L"InternalAddPrinterDriverEx", IsCompatibleDriver, v14);
  }
  else
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalAddPrinterDriverEx",
      L"Driver '%ws' installation failed.  Error %d.",
      v14,
      IsCompatibleDriver);
    SplLogGenericEvent(&LOCAL_ADDDRV_FAILED, L"InternalAddPrinterDriverEx", IsCompatibleDriver, v14);
    SetLastError(IsCompatibleDriver);
  }
  if ( v85 && !IsCompatibleDriver && v88 == 3 )
  {
    v64 = _o__wcsicmp(*((_QWORD *)IniKey + 3), szEnvironment);
    v65 = v86;
    if ( !v64 )
    {
      v66 = PrinterDriverAttributesFromDriverInfo(v86, (unsigned __int8 *)a3);
      if ( (unsigned int)IsKMPD(
                           *((struct sandbox::SandboxManager **)v91 + 46),
                           (struct sandbox::SandboxManager *)v139,
                           v14,
                           (unsigned __int16 *)v66) )
      {
        v85 = 0;
        if ( (unsigned int)LocalDeletePrinterDriverEx((_DWORD)lpString1, (unsigned int)szEnvironment, (_DWORD)v14, 0, 0) )
        {
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "InternalAddPrinterDriverEx",
            L"Deleted driver %ws because it is was KMPD",
            v14);
        }
        else
        {
          v67 = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "InternalAddPrinterDriverEx",
            L"Could not delete KMPD driver %ws. Error %d",
            v14,
            v67);
        }
        SetLastError(0x78Au);
      }
    }
  }
  else
  {
    v65 = v86;
  }
  v102 = IsCompatibleDriver;
  v103 = 4;
  v104 = 0;
  SplLogType::SplLogType((SplLogType *)v129, v14);
  v68 = L"Driver Upgrade";
  if ( !DriverInEnvironment )
    v68 = L"Driver Installation";
  v69 = SplLogType::SplLogType((SplLogType *)v128, v68);
  SplLogEvent2(&SPOOLER_OPERATION_END_EVENT, v69, v70, &v102, 0);
  v71 = GetLastError();
  if ( v85 )
    IsCompatibleDriver = 0;
  if ( DriverInEnvironment )
  {
    v72 = v92 != 0;
    v92 = -v92;
    v73 = v72 + 3;
  }
  else
  {
    v73 = 0;
  }
  if ( DriverInEnvironment )
    v74 = *((_QWORD *)DriverInEnvironment + 15);
  else
    v74 = 0;
  v75 = L"Upgrade";
  if ( !DriverInEnvironment )
    v75 = L"Install";
  LocalSpoolerTelemetry::LogPrinterDriverChanged(
    v75,
    v106,
    v107,
    v108,
    v109,
    v74,
    v73,
    v110,
    v111,
    v112,
    0,
    v113,
    v114,
    v115,
    v65,
    v116,
    v100,
    IsCompatibleDriver);
  SetLastError(v71);
  CleanupTelemetryDriverInfo((struct _TELEMETRY_DRIVER_INFO *)&v106);
  return (unsigned int)v85;
}

```

## disassembly

```asm
0x1800705a0  push    rbx
0x1800705a2  push    rsi
0x1800705a3  push    rdi
0x1800705a4  push    r12
0x1800705a6  push    r13
0x1800705a8  push    r14
0x1800705aa  push    r15
0x1800705ac  sub     rsp, 8D0h
0x1800705b3  mov     rax, cs:__security_cookie
0x1800705ba  xor     rax, rsp
0x1800705bd  mov     [rsp+908h+var_48], rax
0x1800705c5  mov     [rsp+908h+var_874], r9d
0x1800705cd  mov     r12, r8
0x1800705d0  mov     [rsp+908h+var_86C], edx
0x1800705d7  mov     [rsp+908h+lpString1], rcx
0x1800705df  mov     [rsp+908h+var_768], rcx
0x1800705e7  mov     [rsp+908h+var_808], edx
0x1800705ee  mov     [rsp+908h+var_770], r8
0x1800705f6  mov     rax, [rsp+908h+arg_20]
0x1800705fe  mov     [rsp+908h+var_850], rax
0x180070606  mov     [rsp+908h+var_7E8], rax
0x18007060e  mov     r14, [rsp+908h+arg_38]
0x180070616  call    ?RunningInContainerOS@@YAHXZ; RunningInContainerOS(void)
0x18007061b  xor     ecx, ecx
0x18007061d  test    eax, eax
0x18007061f  jz      short loc_18007067A
0x180070621  mov     rbx, [r12+28h]
0x180070626  mov     rcx, rbx; unsigned __int16 *
0x180070629  call    ?IsDriverAllowedInContainerOS@@YAHPEBG@Z; IsDriverAllowedInContainerOS(ushort const *)
0x18007062e  xor     ecx, ecx
0x180070630  test    eax, eax
0x180070632  jnz     short loc_18007067A
0x180070634  mov     r8, rbx
0x180070637  lea     rdx, aTryingToInstal; "Trying to install printer driver %ws bu"...
0x18007063e  lea     rcx, aInternaladdpri_1; "InternalAddPrinterDriverEx"
0x180070645  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18007064a  mov     ecx, 32h ; '2'; dwErrCode
0x18007064f  call    cs:__imp_SetLastError
0x180070655  xor     eax, eax
0x180070657  mov     rcx, [rsp+908h+var_48]
0x18007065f  xor     rcx, rsp; StackCookie
0x180070662  call    __security_check_cookie
0x180070667  add     rsp, 8D0h
0x18007066e  pop     r15
0x180070670  pop     r14
0x180070672  pop     r13
0x180070674  pop     r12
0x180070676  pop     rdi
0x180070677  pop     rsi
0x180070678  pop     rbx
0x180070679  retn
0x18007067a  mov     edi, ecx
0x18007067c  mov     [rsp+908h+var_868], ecx
0x180070683  mov     [rsp+908h+var_870], ecx
0x18007068a  mov     [rsp+908h+var_844], ecx
0x180070691  mov     [rsp+908h+var_810], rcx
0x180070699  mov     r13, rcx
0x18007069c  mov     [rsp+908h+var_830], rcx
0x1800706a4  mov     [rsp+908h+var_864], ecx
0x1800706ab  mov     r15, rcx
0x1800706ae  mov     [rsp+908h+var_860], rcx
0x1800706b6  mov     [rsp+908h+var_840], rcx
0x1800706be  mov     rsi, rcx
0x1800706c1  mov     [rsp+908h+var_820], rcx
0x1800706c9  mov     [rsp+908h+var_818], ecx
0x1800706d0  mov     ebx, ecx
0x1800706d2  mov     [rsp+908h+var_878], ecx
0x1800706d9  xor     edx, edx; Val
0x1800706db  mov     r8d, 208h; Size
0x1800706e1  lea     rcx, [rsp+908h+var_258]; void *
0x1800706e9  call    memset_0
0x1800706ee  xor     eax, eax
0x1800706f0  mov     dword ptr [rsp+908h+var_838], eax
0x1800706f7  mov     [rsp+908h+var_848], eax
0x1800706fe  xor     edx, edx; Val
0x180070700  lea     r8d, [rax+58h]; Size
0x180070704  lea     rcx, [rsp+908h+var_7D8]; void *
0x18007070c  call    memset_0
0x180070711  mov     eax, 0FFFFh
0x180070716  mov     [rsp+908h+var_858], ax
0x18007071e  xor     ecx, ecx
0x180070720  call    EnterSplSem
0x180070725  mov     rdx, [rsp+908h+var_850]
0x18007072d  mov     rcx, [rsp+908h+lpString1]; lpString1
0x180070735  call    MyName
0x18007073a  test    eax, eax
0x18007073c  jz      loc_180071319
0x180070742  mov     [rsp+908h+var_8E8], r14; unsigned __int16 *
0x180070747  mov     r9, [rsp+908h+var_850]; struct _INISPOOLER *
0x18007074f  mov     r8d, [rsp+908h+var_874]; unsigned int
0x180070757  mov     r14d, [rsp+908h+var_86C]
0x18007075f  mov     edx, r14d; unsigned int
0x180070762  mov     rcx, r12; struct _DRIVER_INFO_VERSION *
0x180070765  call    ?ValidateDriverInfo@@YAHPEAEKKPEAU_INISPOOLER@@PEAG@Z; ValidateDriverInfo(uchar *,ulong,ulong,_INISPOOLER *,ushort *)
0x18007076a  test    eax, eax
0x18007076c  jz      loc_180071321
0x180070772  cmp     r14d, 7
0x180070776  jnz     loc_18007080E
0x18007077c  call    LeaveSplSem
0x180070781  mov     rcx, r12
0x180070784  call    InternalINFInstallDriver
0x180070789  mov     [rsp+908h+var_870], eax
0x180070790  test    eax, eax
0x180070792  jnz     short loc_1800707FB
0x180070794  call    cs:__imp_GetLastError
0x18007079a  mov     dword ptr [rsp+908h+var_8D8], eax
0x18007079e  mov     rax, [rsp+908h+lpString1]
0x1800707a6  mov     [rsp+908h+var_8E0], rax
0x1800707ab  mov     rax, [r12+18h]
0x1800707b0  mov     [rsp+908h+var_8E8], rax
0x1800707b5  mov     r9, [r12+10h]
0x1800707ba  mov     r8, [r12+8]
0x1800707bf  lea     rdx, aInfInstallOfDr; "INF install of driver '%ws', inf name '"...
0x1800707c6  lea     r14, aInternaladdpri_1; "InternalAddPrinterDriverEx"
0x1800707cd  mov     rcx, r14; char *
0x1800707d0  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800707d5  call    cs:__imp_GetLastError
0x1800707db  mov     r8d, eax; unsigned int
0x1800707de  mov     r9, [rsp+908h+lpString1]; unsigned __int16 *
0x1800707e6  lea     rdx, aInternalinfins; "InternalINFInstallDriver"
0x1800707ed  lea     rcx, LOCAL_ADDDRV_FAILED; struct _EVENT_DESCRIPTOR *
0x1800707f4  call    ?SplLogGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBGK1@Z; SplLogGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ushort const *)
0x1800707f9  jmp     short loc_180070802
0x1800707fb  lea     r14, aInternaladdpri_1; "InternalAddPrinterDriverEx"
0x180070802  xor     ecx, ecx
0x180070804  call    EnterSplSem
0x180070809  jmp     loc_180071371
0x18007080e  mov     rsi, [r12+8]
0x180070813  mov     [rsp+908h+var_820], rsi
0x18007081b  mov     rax, [r12+10h]
0x180070820  mov     [rsp+908h+var_810], rax
0x180070828  mov     [rsp+908h+var_730], rax
0x180070830  xor     r8d, r8d
0x180070833  mov     rdx, rax
0x180070836  mov     rax, [rsp+908h+var_850]
0x18007083e  mov     rcx, [rax+30h]
0x180070842  call    FindIniKey
0x180070847  mov     [rsp+908h+var_860], rax
0x18007084f  xor     r13d, r13d
0x180070852  mov     dword ptr [rsp+908h+var_8D8], r13d; int
0x180070857  mov     [rsp+908h+var_8E0], rax; struct _INIENVIRONMENT *
0x18007085c  mov     eax, [rsp+908h+arg_28]
0x180070863  mov     dword ptr [rsp+908h+var_8E8], eax; int
0x180070867  lea     r9, [rsp+908h+var_878]; unsigned int *
0x18007086f  lea     r8, [rsp+908h+var_830]; struct _INTERNAL_DRV_FILE **
0x180070877  mov     rdx, r12; unsigned __int8 *
0x18007087a  mov     ecx, r14d; unsigned int
0x18007087d  call    ?CreateInternalDriverFileArray@@YAHKPEAEPEAPEAU_INTERNAL_DRV_FILE@@PEAKHPEAU_INIENVIRONMENT@@H@Z; CreateInternalDriverFileArray(ulong,uchar *,_INTERNAL_DRV_FILE * *,ulong *,int,_INIENVIRONMENT *,int)
0x180070882  test    eax, eax
0x180070884  jnz     short loc_1800708E4
0x180070886  call    cs:__imp_GetLastError
0x18007088c  mov     dword ptr [rsp+908h+var_8E8], eax
0x180070890  mov     r9, [rsp+908h+lpString1]
0x180070898  mov     r8, rsi
0x18007089b  lea     rdx, aInfInstallOfDr_0; "INF install of driver '%ws' onto server"...
0x1800708a2  lea     r14, aInternaladdpri_1; "InternalAddPrinterDriverEx"
0x1800708a9  mov     rcx, r14; char *
0x1800708ac  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800708b1  call    cs:__imp_GetLastError
0x1800708b7  mov     r8d, eax; unsigned int
0x1800708ba  mov     r9, rsi; unsigned __int16 *
0x1800708bd  lea     rdx, aCreateinternal; "CreateInternalDriverFileArray"
0x1800708c4  lea     rcx, LOCAL_ADDDRV_FAILED; struct _EVENT_DESCRIPTOR *
0x1800708cb  call    ?SplLogGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBGK1@Z; SplLogGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ushort const *)
0x1800708d0  mov     r13, [rsp+908h+var_830]
0x1800708d8  mov     ebx, [rsp+908h+var_878]
0x1800708df  jmp     loc_180071371
0x1800708e4  lea     rdx, [rsp+908h+var_858]
0x1800708ec  lea     rcx, szEnvironment; "Windows x64"
0x1800708f3  call    GetProcessorArchitectureFromEnvironmentString
0x1800708f8  test    eax, eax
0x1800708fa  js      loc_180070A69
0x180070900  mov     eax, 0Ch
0x180070905  cmp     ax, [rsp+908h+var_858]
0x18007090d  jnz     loc_180070A69
0x180070913  call    IsServerSKU
0x180070918  test    al, al
0x18007091a  jnz     loc_180070A69
0x180070920  mov     r8, rsi
0x180070923  lea     rdx, aCheckingIfArm6; "Checking if ARM64 is supported for driv"...
0x18007092a  lea     r14, aInternaladdpri_1; "InternalAddPrinterDriverEx"
0x180070931  mov     rcx, r14; char *
0x180070934  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180070939  mov     ebx, [rsp+908h+var_878]
0x180070940  mov     r13, [rsp+908h+var_830]
0x180070948  test    ebx, ebx
0x18007094a  jz      loc_180070A7F
0x180070950  lea     rdx, aWindowsArm64; "Windows ARM64"
0x180070957  mov     rcx, [r13+0]
0x18007095b  call    CheckFilePlatform
0x180070960  test    eax, eax
0x180070962  jnz     loc_180070A7F
0x180070968  mov     r8, rsi
0x18007096b  lea     rdx, aArm64IsNotSupp; "ARM64 is not supported by driver: %ws"
0x180070972  mov     rcx, r14; char *
0x180070975  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18007097a  xor     edx, edx; Val
0x18007097c  mov     r8d, 418h; Size
0x180070982  lea     rcx, [rsp+908h+var_678]; void *
0x18007098a  call    memset_0
0x18007098f  mov     [rsp+908h+var_46C], 2
0x18007099a  mov     r8, rsi; unsigned __int16 *
0x18007099d  mov     edx, 104h; unsigned __int64
0x1800709a2  lea     rcx, [rsp+908h+var_674]; unsigned __int16 *
0x1800709aa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800709af  test    eax, eax
0x1800709b1  js      loc_180070A58
0x1800709b7  mov     r8, [r13+0]; unsigned __int16 *
0x1800709bb  mov     edx, 104h; unsigned __int64
0x1800709c0  lea     rcx, [rsp+908h+var_468]; unsigned __int16 *
0x1800709c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800709cd  test    eax, eax
0x1800709cf  js      loc_180070A58
0x1800709d5  call    cs:__imp_RevertToPrinterSelf
0x1800709db  mov     rbx, rax
0x1800709de  mov     [rsp+908h+var_8E8], 0
0x1800709e7  mov     r9d, 418h
0x1800709ed  lea     r8, [rsp+908h+var_678]
0x1800709f5  xor     edx, edx
0x1800709f7  mov     rcx, cs:WNF_PNPF_DRIVER_NO_NATIVE_ARCHITECTURE_SUPPORT
0x1800709fe  call    cs:__imp_RtlPublishWnfStateData
0x180070a04  or      eax, 10000000h
0x180070a09  jge     short loc_180070A20
0x180070a0b  mov     r9d, eax
0x180070a0e  mov     r8, rsi
0x180070a11  lea     rdx, aFailedToPublis_0; "Failed to publish WNF notification for "...
0x180070a18  mov     rcx, r14; char *
0x180070a1b  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180070a20  test    rbx, rbx
0x180070a23  jz      short loc_180070A78
0x180070a25  mov     rcx, rbx; hToken
0x180070a28  call    cs:__imp_ImpersonatePrinterClient
0x180070a2e  test    eax, eax
0x180070a30  jnz     short loc_180070A78
0x180070a32  call    cs:__imp_GetLastError
0x180070a38  mov     edi, eax
0x180070a3a  mov     [rsp+908h+var_868], eax
0x180070a41  mov     r8, rsi
0x180070a44  lea     rdx, aFailedToImpers; "Failed to impersonate client after publ"...
0x180070a4b  mov     rcx, r14; char *
0x180070a4e  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180070a53  jmp     loc_1800708D8
0x180070a58  lea     rdx, aFailedToCopyDr_1; "Failed to copy driver information for W"...
0x180070a5f  mov     rcx, r14; char *
0x180070a62  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180070a67  jmp     short loc_180070A7F
0x180070a69  lea     r14, aInternaladdpri_1; "InternalAddPrinterDriverEx"
0x180070a70  mov     r13, [rsp+908h+var_830]
0x180070a78  mov     ebx, [rsp+908h+var_878]
0x180070a7f  cmp     [rsp+908h+arg_28], 0
0x180070a87  jnz     short loc_180070AA3
0x180070a89  test    byte ptr [rsp+908h+var_874], 10h
0x180070a91  jnz     short loc_180070AA3
0x180070a93  mov     edi, [r12]
0x180070a97  mov     [rsp+908h+var_864], edi
0x180070a9e  jmp     loc_180070B42
0x180070aa3  xor     r8d, r8d
0x180070aa6  lea     rdx, [rsp+908h+var_864]
0x180070aae  mov     rcx, [r13+0]; lpwstrFilename
0x180070ab2  call    GetPrintDriverVersion
0x180070ab7  test    eax, eax
0x180070ab9  jnz     short loc_180070AF4
0x180070abb  call    cs:__imp_GetLastError
0x180070ac1  mov     dword ptr [rsp+908h+var_8E8], eax
0x180070ac5  mov     r9, [rsp+908h+lpString1]
0x180070acd  mov     r8, rsi
0x180070ad0  lea     rdx, aVersionCheckFo; "Version check for driver '%ws' onto ser"...
0x180070ad7  mov     rcx, r14; char *
0x180070ada  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180070adf  call    cs:__imp_GetLastError
0x180070ae5  mov     r9, rsi
0x180070ae8  lea     rdx, aGetprinterdriv_0; "GetPrinterDriverVersion"
0x180070aef  jmp     loc_180071361
0x180070af4  mov     edi, [rsp+908h+var_864]
0x180070afb  mov     [r12], edi
0x180070aff  test    ebx, ebx
0x180070b01  jz      loc_1800712FC
0x180070b07  mov     rdx, [rsp+908h+var_810]
0x180070b0f  mov     rcx, [r13+0]
0x180070b13  call    CheckFilePlatform
0x180070b18  test    eax, eax
0x180070b1a  jz      loc_1800712FC
0x180070b20  cmp     ebx, 1
0x180070b23  jbe     loc_1800712FC
0x180070b29  mov     rdx, [rsp+908h+var_810]
0x180070b31  mov     rcx, [r13+20h]
0x180070b35  call    CheckFilePlatform
0x180070b3a  test    eax, eax
0x180070b3c  jz      loc_1800712FC
0x180070b42  cmp     edi, 2
0x180070b45  jnz     short loc_180070B63
0x180070b47  mov     r8, rsi
0x180070b4a  lea     rdx, aDriverWsIsAKmD; "Driver '%ws' is a KM driver.  Failing i"...
0x180070b51  mov     rcx, r14; char *
0x180070b54  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180070b59  mov     edi, 78Ah
0x180070b5e  jmp     loc_180071310
0x180070b63  cmp     edi, 3
0x180070b66  jbe     short loc_180070B84
0x180070b68  mov     r8, rsi
  ... truncated ...
```
