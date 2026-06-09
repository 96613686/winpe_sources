# NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage(_SETUP_CONTEXT *,_INISPOOLER *)

- ea: `0x1800b81d0`
- end: `0x1800b889c`
- name: `?LegacyInstallPrinterDriverFromPackage@NPackageInstallLocalspl@@YAJPEAU_SETUP_CONTEXT@@PEAU_INISPOOLER@@@Z`
- size: `1740`
- prototype: `__int64 __fastcall(unsigned __int16 **this, struct _SETUP_CONTEXT *, struct _INISPOOLER *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800adb34`

## callees

- `0x18000ea40`
- `0x180012510`
- `0x180015e28`
- `0x180035ae4`
- `0x18003d0a4`
- `0x18003e984`
- `0x18003ea2c`
- `0x180047330`
- `0x18006b2a4`
- `0x1800705a0`
- `0x180072110`
- `0x180092640`
- `0x1800abd54`
- `0x1800abe08`
- `0x1800b81d0`
- `0x1800c8948`
- `0x1800cd2ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b845e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b850e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b86a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b845e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b850e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b86a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8808`
- `SPOOLSS!DllFreeSplMem` at `0x1800b87df`
- `SPOOLSS!DllFreeSplMem` at `0x1800b87df`

## string_xrefs

- `0x1800b82ef`: `Printer driver details pDependentFiles = %ws, pDriverPath = %ws,  pDataFile = %ws, pConfigFile = %ws, pHelpFile = %ws.`
- `0x1800b83e3`: `Driver is blocked (blockingStatus = 0x%x), aborting installation`
- `0x1800b8593`: `SplIsCompatibleDriver failed`
- `0x1800b8428`: `InternalInstallPrinterDriverFromPackage`
- `0x1800b85b0`: `InternalInstallPrinterDriverFromPackage`
- `0x1800b8861`: `InternalInstallPrinterDriverFromPackage`
- `0x1800b824a`: `Installing %ws printer driver with pszServer = %ws, pszInfPath = %ws, pszEnvironment = %ws.`
- `0x1800b82be`: `NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage`
- `0x1800b82fa`: `NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage`
- `0x1800b83ea`: `NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage`
- `0x1800b8502`: `NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage`
- `0x1800b8699`: `NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage`
- `0x1800b875a`: `NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage`
- `0x1800b87f8`: `NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage`

## pseudocode

```c
__int64 __fastcall NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage(
        unsigned __int16 **this,
        struct _SETUP_CONTEXT *a2,
        struct _INISPOOLER *a3)
{
  NPackageInstallLocalspl *v3; // rbx
  unsigned __int16 *v4; // rdi
  const unsigned __int16 *v5; // r14
  const unsigned __int16 *v6; // r13
  const unsigned __int16 *v7; // r12
  const unsigned __int16 *v8; // rsi
  const wchar_t *v9; // rax
  BOOL v10; // eax
  int v11; // ecx
  int v12; // eax
  int IsCompatibleDriver; // eax
  int v14; // ebx
  struct _INISPOOLER *v15; // r8
  const struct _EVENT_DESCRIPTOR *v16; // r15
  int v17; // ecx
  const unsigned __int16 *v18; // rax
  DWORD v19; // eax
  DWORD v20; // eax
  unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // r9
  const struct _EVENT_DESCRIPTOR *v24; // rcx
  DWORD LastError; // eax
  unsigned __int16 *v26; // rcx
  _WORD *v27; // rsi
  struct _SETUP_CONTEXT *v28; // rbx
  const unsigned __int16 *v29; // r14
  NCoreLibrary *v30; // rcx
  int LastErrorAsFailHRNoBreak; // eax
  int v32; // edx
  DWORD v33; // eax
  int v34; // edx
  const unsigned __int16 *v35; // rcx
  const unsigned __int16 *v36; // r9
  const unsigned __int16 *v37; // r8
  NPackageInstallLocalspl *v38; // rsi
  __int64 v39; // rcx
  unsigned __int16 near **v40; // rbx
  unsigned __int16 *CatalogPathFromFilePath; // rsi
  NCoreLibrary *v42; // rcx
  __int64 v44; // [rsp+20h] [rbp-E0h]
  __int64 v45; // [rsp+20h] [rbp-E0h]
  __int64 v46; // [rsp+20h] [rbp-E0h]
  struct _INISPOOLER *v47; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v48; // [rsp+30h] [rbp-D0h]
  int v49; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v50; // [rsp+48h] [rbp-B8h]
  unsigned int v51; // [rsp+50h] [rbp-B0h]
  unsigned int v52; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v53; // [rsp+60h] [rbp-A0h] BYREF
  NPackageInstallLocalspl *v54; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v55; // [rsp+70h] [rbp-90h]
  __int128 v56; // [rsp+80h] [rbp-80h] BYREF
  __int128 v57; // [rsp+90h] [rbp-70h]
  __int128 v58; // [rsp+A0h] [rbp-60h]
  __int128 v59; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v60[2]; // [rsp+C0h] [rbp-40h]
  __int128 v61; // [rsp+D0h] [rbp-30h]
  __int128 v62; // [rsp+E0h] [rbp-20h]
  __int128 v63; // [rsp+F0h] [rbp-10h]
  __int64 v64; // [rsp+100h] [rbp+0h]
  const wchar_t *v65; // [rsp+108h] [rbp+8h]
  __int64 v66; // [rsp+110h] [rbp+10h]
  __int64 v67; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v68; // [rsp+120h] [rbp+20h]
  int v69; // [rsp+128h] [rbp+28h]
  __int64 v70; // [rsp+130h] [rbp+30h]
  __int64 v71; // [rsp+138h] [rbp+38h]
  __int64 v72; // [rsp+140h] [rbp+40h]
  NPackageInstallLocalspl *v73; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _SETUP_CONTEXT *v74; // [rsp+1A8h] [rbp+A8h]
  unsigned int v75; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned int v76; // [rsp+1B8h] [rbp+B8h]

  v74 = a2;
  v73 = (NPackageInstallLocalspl *)this;
  v3 = (NPackageInstallLocalspl *)this[3];
  v4 = this[4];
  v76 = *((_DWORD *)this + 11);
  v6 = this[7];
  v7 = this[8];
  v55 = this[6];
  v5 = v55;
  v54 = v3;
  memset_0(&v56, 0, 0xC8u);
  v8 = 0;
  v56 = *(_OWORD *)(v4 + 132);
  v57 = *(_OWORD *)(v4 + 140);
  v58 = *(_OWORD *)(v4 + 148);
  v59 = *(_OWORD *)(v4 + 156);
  *(_OWORD *)v60 = *(_OWORD *)(v4 + 164);
  v61 = *(_OWORD *)(v4 + 172);
  v62 = *(_OWORD *)(v4 + 180);
  v63 = *(_OWORD *)(v4 + 188);
  v64 = *((_QWORD *)v4 + 49);
  v9 = L"winprint";
  if ( *((_QWORD *)v4 + 25) )
    v9 = (const wchar_t *)*((_QWORD *)v4 + 25);
  v65 = v9;
  v66 = *((_QWORD *)v4 + 27);
  v67 = *((_QWORD *)v4 + 24);
  v68 = *(unsigned __int16 **)v4;
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage",
    L"Installing %ws printer driver with pszServer = %ws, pszInfPath = %ws, pszEnvironment = %ws.",
    v6,
    v3,
    v55,
    v7);
  HIDWORD(v48) = DWORD1(v59);
  v47 = (struct _INISPOOLER *)*((_QWORD *)&v58 + 1);
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage",
    L"Printer driver details pDependentFiles = %ws, pDriverPath = %ws,  pDataFile = %ws, pConfigFile = %ws, pHelpFile = %ws.",
    *((_QWORD *)&v59 + 1),
    *((_QWORD *)&v57 + 1),
    (_QWORD)v58);
  if ( !v55 )
  {
    v5 = *(const unsigned __int16 **)v4;
    v55 = *(unsigned __int16 **)v4;
  }
  v10 = *((_DWORD *)v4 + 43) != 0;
  v69 = v10;
  v11 = *((_DWORD *)v4 + 44);
  if ( v11 == 2 )
  {
    v12 = v10 | 4;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v12 = v10 | 0x800;
  }
  v69 = v12;
LABEL_10:
  if ( *((_DWORD *)v4 + 43) )
    v70 = *((_QWORD *)v4 + 28);
  else
    v70 = 0;
  v71 = *((_QWORD *)v4 + 30);
  v72 = *((_QWORD *)v4 + 31);
  v75 = 0;
  IsCompatibleDriver = SplIsCompatibleDriver((_DWORD)v6, DWORD2(v57), (_DWORD)v7, dwMajorVersion, (char)&v75);
  v14 = IsCompatibleDriver;
  if ( IsCompatibleDriver )
  {
    if ( IsCompatibleDriver > 0 )
      v14 = (unsigned __int16)IsCompatibleDriver | 0x80070000;
    if ( v14 < 0 )
    {
      LastError = GetLastError();
      if ( *((_DWORD *)v4 + 43) )
        v26 = (unsigned __int16 *)*((_QWORD *)v4 + 28);
      else
        v26 = 0;
      v52 = v14;
      v16 = &SETUP_INSTALL_PRINTER_DRIVER_FAILED;
      v51 = LastError;
      v22 = L"SplIsCompatibleDriver failed";
      v50 = v26;
      v23 = 0;
      v49 = *((_DWORD *)v4 + 43);
      v24 = &SETUP_INSTALL_PRINTER_DRIVER_FAILED;
LABEL_41:
      SplLogPrinterSetupCoreDriverEvent(
        v24,
        L"InternalInstallPrinterDriverFromPackage",
        v22,
        v23,
        v5,
        v6,
        *((const unsigned __int16 **)v4 + 23),
        v7,
        v49,
        v50,
        v51,
        v52);
      goto LABEL_42;
    }
  }
  else
  {
    v14 = 0;
  }
  v15 = (struct _INISPOOLER *)v75;
  v16 = &SETUP_INSTALL_PRINTER_DRIVER_FAILED;
  if ( (_BYTE)v75 == 1 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage",
      L"Driver is blocked (blockingStatus = 0x%x), aborting installation");
    v17 = *((_DWORD *)v4 + 43);
    v14 = -2147021882;
    if ( v17 )
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 28);
    else
      v18 = 0;
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InternalInstallPrinterDriverFromPackage",
      L"Driver is blocked",
      0,
      v5,
      v6,
      *((const unsigned __int16 **)v4 + 23),
      v7,
      v17,
      v18,
      0xBC6u,
      0x80070BC6);
    v19 = GetLastError();
    SplLogEvent(&MSG_BAD_OEM_DRIVER, v19, v6, 0);
  }
  if ( v14 >= 0 && !(unsigned int)FastStrcmpi(v7) && v60[0] )
  {
    v53 = 0;
    v14 = StringCchLengthW(v60[0], 0x7FFFFFFFu, &v53);
    if ( v14 < 0
      || (v8 = &v60[0][v53 + 1],
          v14 = NPackageInstallLocalspl::AddLangMonitor(v54, v60[0], v7, v8, (const unsigned __int16 *)v74, v47),
          v14 < 0) )
    {
      LODWORD(v44) = v14;
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage",
        L"Failed adding language monitor %ws(%ws), hr: 0x%x.",
        v60[0],
        v8,
        v44);
    }
    v20 = GetLastError();
    if ( *((_DWORD *)v4 + 43) )
      v21 = (unsigned __int16 *)*((_QWORD *)v4 + 28);
    else
      v21 = 0;
    v52 = v14;
    v51 = v20;
    v22 = L"AddLangMonitor failed (monitor name in additional info)";
    v50 = v21;
    if ( v14 >= 0 )
      v22 = L"AddLangMonitor succeeded (monitor name in additional info)";
    v49 = *((_DWORD *)v4 + 43);
    v23 = v60[0];
    v24 = &SETUP_INSTALL_PRINTER_DRIVER_FAILED;
    if ( v14 >= 0 )
      v24 = &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED;
    goto LABEL_41;
  }
LABEL_42:
  v53 = 0;
  if ( v14 >= 0 )
  {
    v27 = (_WORD *)*((_QWORD *)v4 + 25);
    if ( !v27 || !*v27 )
      goto LABEL_58;
    v14 = StringCchLengthW(*((const unsigned __int16 **)v4 + 25), 0x7FFFFFFFu, &v53);
    if ( v14 < 0 )
      return (unsigned int)v14;
    if ( *v27 )
    {
      v28 = v74;
      v29 = &v27[v53 + 1];
      if ( v29
        && *v29
        && !(unsigned int)SplAddPrintProcessor((_DWORD)v54, (_DWORD)v7, (_DWORD)v29, (_DWORD)v27, (char)v74) )
      {
        LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v30);
        v15 = 0;
        v32 = 0;
        v14 = 0;
        if ( (_WORD)LastErrorAsFailHRNoBreak != 3005 )
          v32 = LastErrorAsFailHRNoBreak;
        if ( (_WORD)v32 != 1805 )
          v14 = v32;
        if ( v14 < 0 )
        {
          LODWORD(v45) = v14;
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage",
            L"Failed adding print processor %ws(%ws), hr: 0x%x.",
            v29,
            v27,
            v45);
          v33 = GetLastError();
          v34 = *((_DWORD *)v4 + 43);
          v35 = 0;
          if ( v34 )
            v35 = (const unsigned __int16 *)*((_QWORD *)v4 + 28);
          v36 = v29;
          v37 = L"SplAddPrintProcessor failed (print processor name in additional info)";
LABEL_80:
          SplLogPrinterSetupCoreDriverEvent(
            v16,
            L"InternalInstallPrinterDriverFromPackage",
            v37,
            v36,
            v55,
            v6,
            *((const unsigned __int16 **)v4 + 23),
            v7,
            v34,
            v35,
            v33,
            v14);
          return (unsigned int)v14;
        }
        v28 = v74;
      }
    }
    else
    {
LABEL_58:
      v28 = v74;
    }
    v38 = v73;
    if ( !*((_DWORD *)v4 + 43) || (v14 = NPackageInstallLocalspl::AddPackageInfoToRegistry(v73, v28, v15), v14 >= 0) )
    {
      v39 = *((_QWORD *)v38 + 4);
      LODWORD(v73) = 0;
      v14 = ConvertDriverCategoryToPrinterDriverAttribute(*(unsigned int *)(v39 + 148), &v73);
      if ( v14 >= 0 )
      {
        v69 |= (unsigned int)v73;
        v40 = &g_szzEmptyMultiString;
        CatalogPathFromFilePath = GetCatalogPathFromFilePath(v68, 0);
        if ( !*((_QWORD *)&v59 + 1) )
        {
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage",
            L"Dependent Files being set to NULL for pszDriverName=%ws.",
            v6);
          SplLogGenericEvent(&LOCAL_ADDDRV_SUCCEEDED, L"Dependent Files is set to NULL", 0, v6);
          *((_QWORD *)&v59 + 1) = &g_szzEmptyMultiString;
        }
        if ( (_QWORD)v61 )
          v40 = (unsigned __int16 near **)v61;
        LODWORD(v48) = 0;
        LODWORD(v47) = 0;
        *(_QWORD *)&v61 = v40;
        if ( (unsigned int)InternalAddPrinterDriverEx(v54, 8, &v56, v76, v74, v47, v48, CatalogPathFromFilePath) )
          v14 = 0;
        else
          v14 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v42);
        if ( CatalogPathFromFilePath )
          DllFreeSplMem(CatalogPathFromFilePath);
        if ( v14 < 0 )
        {
          LODWORD(v46) = v14;
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage",
            L"Error adding printer driver keys for %ws(%ws), hr: 0x%x",
            *((_QWORD *)&v56 + 1),
            v68,
            v46);
        }
        v33 = GetLastError();
        v34 = *((_DWORD *)v4 + 43);
        if ( v34 )
          v35 = (const unsigned __int16 *)*((_QWORD *)v4 + 28);
        else
          v35 = 0;
        v37 = L"InternalAddPrinterDriverEx failed";
        if ( v14 >= 0 )
        {
          v37 = L"InternalAddPrinterDriverEx succeeded";
          v16 = &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED;
        }
        v36 = 0;
        goto LABEL_80;
      }
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800b81d0  mov     [rsp-8+arg_8], rdx
0x1800b81d5  mov     [rsp-8+arg_0], rcx
0x1800b81da  push    rbp
0x1800b81db  push    rbx
0x1800b81dc  push    rsi
0x1800b81dd  push    rdi
0x1800b81de  push    r12
0x1800b81e0  push    r13
0x1800b81e2  push    r14
0x1800b81e4  push    r15
0x1800b81e6  lea     rbp, [rsp-58h]
0x1800b81eb  sub     rsp, 158h
0x1800b81f2  mov     rbx, [rcx+18h]
0x1800b81f6  mov     rax, rcx
0x1800b81f9  mov     rdi, [rcx+20h]
0x1800b81fd  xor     edx, edx; Val
0x1800b81ff  mov     ecx, [rcx+2Ch]
0x1800b8202  mov     r8d, 0C8h; Size
0x1800b8208  mov     [rbp+90h+arg_18], ecx
0x1800b820e  lea     rcx, [rbp+90h+var_110]; void *
0x1800b8212  mov     r14, [rax+30h]
0x1800b8216  mov     r13, [rax+38h]
0x1800b821a  mov     r12, [rax+40h]
0x1800b821e  mov     [rsp+190h+var_120], r14
0x1800b8223  mov     [rsp+190h+var_128], rbx
0x1800b8228  call    memset_0
0x1800b822d  movups  xmm0, xmmword ptr [rdi+108h]
0x1800b8234  xor     esi, esi
0x1800b8236  mov     qword ptr [rsp+190h+var_170+8], r12
0x1800b823b  mov     r9, rbx
0x1800b823e  mov     qword ptr [rsp+190h+var_170], r14
0x1800b8243  movups  [rbp+90h+var_110], xmm0
0x1800b8247  mov     r8, r13
0x1800b824a  lea     rdx, aInstallingWsPr_0; "Installing %ws printer driver with pszS"...
0x1800b8251  movups  xmm1, xmmword ptr [rdi+118h]
0x1800b8258  movups  [rbp+90h+var_100], xmm1
0x1800b825c  movups  xmm0, xmmword ptr [rdi+128h]
0x1800b8263  movups  [rbp+90h+var_F0], xmm0
0x1800b8267  movups  xmm1, xmmword ptr [rdi+138h]
0x1800b826e  movups  [rbp+90h+var_E0], xmm1
0x1800b8272  movups  xmm0, xmmword ptr [rdi+148h]
0x1800b8279  movups  xmmword ptr [rbp+90h+var_D0], xmm0
0x1800b827d  movups  xmm1, xmmword ptr [rdi+158h]
0x1800b8284  movups  [rbp+90h+var_C0], xmm1
0x1800b8288  movups  xmm0, xmmword ptr [rdi+168h]
0x1800b828f  movups  [rbp+90h+var_B0], xmm0
0x1800b8293  movups  xmm1, xmmword ptr [rdi+178h]
0x1800b829a  movups  [rbp+90h+var_A0], xmm1
0x1800b829e  mov     rax, [rdi+188h]
0x1800b82a5  mov     [rbp+90h+var_90], rax
0x1800b82a9  lea     rax, szDefaultPrintProc; "winprint"
0x1800b82b0  mov     rcx, [rdi+0C8h]
0x1800b82b7  test    rcx, rcx
0x1800b82ba  cmovnz  rax, rcx
0x1800b82be  lea     rcx, aNpackageinstal; "NPackageInstallLocalspl::LegacyInstallP"...
0x1800b82c5  mov     [rbp+90h+var_88], rax
0x1800b82c9  mov     rax, [rdi+0D8h]
0x1800b82d0  mov     [rbp+90h+var_80], rax
0x1800b82d4  mov     rax, [rdi+0C0h]
0x1800b82db  mov     [rbp+90h+var_78], rax
0x1800b82df  mov     rax, [rdi]
0x1800b82e2  mov     [rbp+90h+var_70], rax
0x1800b82e6  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800b82eb  mov     rax, qword ptr [rbp+90h+var_E0]
0x1800b82ef  lea     rdx, aPrinterDriverD; "Printer driver details pDependentFiles "...
0x1800b82f6  mov     r9, qword ptr [rbp+90h+var_100+8]
0x1800b82fa  lea     rcx, aNpackageinstal; "NPackageInstallLocalspl::LegacyInstallP"...
0x1800b8301  mov     r8, qword ptr [rbp+90h+var_E0+8]
0x1800b8305  mov     [rsp+190h+var_160], rax
0x1800b830a  mov     rax, qword ptr [rbp+90h+var_F0+8]
0x1800b830e  mov     qword ptr [rsp+190h+var_170+8], rax
0x1800b8313  mov     rax, qword ptr [rbp+90h+var_F0]
0x1800b8317  mov     qword ptr [rsp+190h+var_170], rax
0x1800b831c  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800b8321  test    r14, r14
0x1800b8324  jnz     short loc_1800B832E
0x1800b8326  mov     r14, [rdi]
0x1800b8329  mov     [rsp+190h+var_120], r14
0x1800b832e  cmp     [rdi+0ACh], esi
0x1800b8334  mov     eax, esi
0x1800b8336  setnz   al
0x1800b8339  mov     [rbp+90h+var_68], eax
0x1800b833c  mov     ecx, [rdi+0B0h]
0x1800b8342  cmp     ecx, 2
0x1800b8345  jnz     short loc_1800B834C
0x1800b8347  or      eax, 4
0x1800b834a  jmp     short loc_1800B8354
0x1800b834c  test    ecx, ecx
0x1800b834e  jnz     short loc_1800B8357
0x1800b8350  bts     eax, 0Bh
0x1800b8354  mov     [rbp+90h+var_68], eax
0x1800b8357  cmp     [rdi+0ACh], esi
0x1800b835d  jz      short loc_1800B836C
0x1800b835f  mov     rax, [rdi+0E0h]
0x1800b8366  mov     [rbp+90h+var_60], rax
0x1800b836a  jmp     short loc_1800B8370
0x1800b836c  mov     [rbp+90h+var_60], rsi
0x1800b8370  mov     rax, [rdi+0F0h]
0x1800b8377  mov     r8, r12
0x1800b837a  mov     r9d, cs:dwMajorVersion
0x1800b8381  mov     rcx, r13
0x1800b8384  mov     rdx, qword ptr [rbp+90h+var_100+8]
0x1800b8388  mov     [rbp+90h+var_58], rax
0x1800b838c  mov     rax, [rdi+0F8h]
0x1800b8393  mov     [rbp+90h+var_50], rax
0x1800b8397  lea     rax, [rbp+90h+arg_10]
0x1800b839e  mov     qword ptr [rsp+190h+var_170], rax
0x1800b83a3  mov     [rbp+90h+arg_10], esi
0x1800b83a9  call    SplIsCompatibleDriver
0x1800b83ae  mov     ebx, eax
0x1800b83b0  test    eax, eax
0x1800b83b2  jnz     short loc_1800B83B8
0x1800b83b4  mov     ebx, esi
0x1800b83b6  jmp     short loc_1800B83CB
0x1800b83b8  jle     short loc_1800B83C3
0x1800b83ba  movzx   ebx, ax
0x1800b83bd  or      ebx, 80070000h
0x1800b83c3  test    ebx, ebx
0x1800b83c5  js      loc_1800B8568
0x1800b83cb  mov     r8d, [rbp+90h+arg_10]
0x1800b83d2  lea     r15, SETUP_INSTALL_PRINTER_DRIVER_FAILED
0x1800b83d9  cmp     r8b, 1
0x1800b83dd  jnz     loc_1800B8478
0x1800b83e3  lea     rdx, aDriverIsBlocke_0; "Driver is blocked (blockingStatus = 0x%"...
0x1800b83ea  lea     rcx, aNpackageinstal; "NPackageInstallLocalspl::LegacyInstallP"...
0x1800b83f1  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800b83f6  mov     ecx, [rdi+0ACh]
0x1800b83fc  mov     ebx, 80070BC6h
0x1800b8401  test    ecx, ecx
0x1800b8403  jz      short loc_1800B840E
0x1800b8405  mov     rax, [rdi+0E0h]
0x1800b840c  jmp     short loc_1800B8411
0x1800b840e  mov     rax, rsi
0x1800b8411  mov     [rsp+190h+var_138], 80070BC6h; unsigned int
0x1800b8419  lea     r8, aDriverIsBlocke; "Driver is blocked"
0x1800b8420  mov     [rsp+190h+var_140], 0BC6h; unsigned int
0x1800b8428  lea     rdx, aInternalinstal; "InternalInstallPrinterDriverFromPackage"
0x1800b842f  mov     [rsp+190h+var_148], rax; unsigned __int16 *
0x1800b8434  xor     r9d, r9d; unsigned __int16 *
0x1800b8437  mov     rax, [rdi+0B8h]
0x1800b843e  mov     [rsp+190h+var_150], ecx; int
0x1800b8442  mov     rcx, r15; struct _EVENT_DESCRIPTOR *
0x1800b8445  mov     [rsp+190h+var_158], r12; unsigned __int16 *
0x1800b844a  mov     [rsp+190h+var_160], rax; unsigned __int16 *
0x1800b844f  mov     qword ptr [rsp+190h+var_170+8], r13; struct _INISPOOLER *
0x1800b8454  mov     qword ptr [rsp+190h+var_170], r14; unsigned __int16 *
0x1800b8459  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x1800b845e  call    cs:__imp_GetLastError
0x1800b8464  xor     r9d, r9d
0x1800b8467  lea     rcx, MSG_BAD_OEM_DRIVER; struct _EVENT_DESCRIPTOR *
0x1800b846e  mov     edx, eax; unsigned int
0x1800b8470  mov     r8, r13; unsigned __int16 *
0x1800b8473  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800b8478  test    ebx, ebx
0x1800b847a  js      loc_1800B85D0
0x1800b8480  lea     rdx, szEnvironment; "Windows x64"
0x1800b8487  mov     rcx, r12; lpString1
0x1800b848a  call    FastStrcmpi
0x1800b848f  test    eax, eax
0x1800b8491  jnz     loc_1800B85D0
0x1800b8497  mov     rcx, [rbp+90h+var_D0]; unsigned __int16 *
0x1800b849b  test    rcx, rcx
0x1800b849e  jz      loc_1800B85D0
0x1800b84a4  lea     r8, [rsp+190h+var_130]; unsigned __int64 *
0x1800b84a9  mov     [rsp+190h+var_130], rsi
0x1800b84ae  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800b84b3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800b84b8  mov     ebx, eax
0x1800b84ba  test    eax, eax
0x1800b84bc  js      short loc_1800B84F0
0x1800b84be  mov     rdx, [rbp+90h+var_D0]; unsigned __int16 *
0x1800b84c2  mov     r8, r12; unsigned __int16 *
0x1800b84c5  mov     rax, [rsp+190h+var_130]
0x1800b84ca  mov     rcx, [rsp+190h+var_128]; this
0x1800b84cf  inc     rax
0x1800b84d2  lea     rsi, [rdx+rax*2]
0x1800b84d6  mov     rax, [rbp+90h+arg_8]
0x1800b84dd  mov     r9, rsi; unsigned __int16 *
0x1800b84e0  mov     qword ptr [rsp+190h+var_170], rax; unsigned __int16 *
0x1800b84e5  call    ?AddLangMonitor@NPackageInstallLocalspl@@YAJPEBG000PEAU_INISPOOLER@@@Z; NPackageInstallLocalspl::AddLangMonitor(ushort const *,ushort const *,ushort const *,ushort const *,_INISPOOLER *)
0x1800b84ea  mov     ebx, eax
0x1800b84ec  test    eax, eax
0x1800b84ee  jns     short loc_1800B850E
0x1800b84f0  mov     r8, [rbp+90h+var_D0]
0x1800b84f4  lea     rdx, aFailedAddingLa; "Failed adding language monitor %ws(%ws)"...
0x1800b84fb  mov     r9, rsi
0x1800b84fe  mov     dword ptr [rsp+190h+var_170], ebx
0x1800b8502  lea     rcx, aNpackageinstal; "NPackageInstallLocalspl::LegacyInstallP"...
0x1800b8509  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800b850e  call    cs:__imp_GetLastError
0x1800b8514  mov     r9d, [rdi+0ACh]
0x1800b851b  xor     esi, esi
0x1800b851d  test    r9d, r9d
0x1800b8520  jz      short loc_1800B852B
0x1800b8522  mov     rdx, [rdi+0E0h]
0x1800b8529  jmp     short loc_1800B852E
0x1800b852b  mov     rdx, rsi
0x1800b852e  mov     [rsp+190h+var_138], ebx
0x1800b8532  lea     rcx, aAddlangmonitor_0; "AddLangMonitor succeeded (monitor name "...
0x1800b8539  test    ebx, ebx
0x1800b853b  mov     [rsp+190h+var_140], eax
0x1800b853f  lea     r8, aAddlangmonitor; "AddLangMonitor failed (monitor name in "...
0x1800b8546  mov     [rsp+190h+var_148], rdx
0x1800b854b  cmovns  r8, rcx
0x1800b854f  mov     [rsp+190h+var_150], r9d
0x1800b8554  mov     r9, [rbp+90h+var_D0]
0x1800b8558  lea     r10, SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED
0x1800b855f  mov     rcx, r15
0x1800b8562  cmovns  rcx, r10
0x1800b8566  jmp     short loc_1800B85A9
0x1800b8568  call    cs:__imp_GetLastError
0x1800b856e  mov     edx, [rdi+0ACh]
0x1800b8574  test    edx, edx
0x1800b8576  jz      short loc_1800B8581
0x1800b8578  mov     rcx, [rdi+0E0h]
0x1800b857f  jmp     short loc_1800B8584
0x1800b8581  mov     rcx, rsi
0x1800b8584  mov     [rsp+190h+var_138], ebx; unsigned int
0x1800b8588  lea     r15, SETUP_INSTALL_PRINTER_DRIVER_FAILED
0x1800b858f  mov     [rsp+190h+var_140], eax; unsigned int
0x1800b8593  lea     r8, aSpliscompatibl_1; "SplIsCompatibleDriver failed"
0x1800b859a  mov     [rsp+190h+var_148], rcx; unsigned __int16 *
0x1800b859f  xor     r9d, r9d; unsigned __int16 *
0x1800b85a2  mov     [rsp+190h+var_150], edx; int
0x1800b85a6  mov     rcx, r15; struct _EVENT_DESCRIPTOR *
0x1800b85a9  mov     rax, [rdi+0B8h]
0x1800b85b0  lea     rdx, aInternalinstal; "InternalInstallPrinterDriverFromPackage"
0x1800b85b7  mov     [rsp+190h+var_158], r12; unsigned __int16 *
0x1800b85bc  mov     [rsp+190h+var_160], rax; unsigned __int16 *
0x1800b85c1  mov     qword ptr [rsp+190h+var_170+8], r13; unsigned __int16 *
0x1800b85c6  mov     qword ptr [rsp+190h+var_170], r14; unsigned __int16 *
0x1800b85cb  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x1800b85d0  mov     rax, rsi
0x1800b85d3  mov     [rsp+190h+var_130], rax
0x1800b85d8  test    ebx, ebx
0x1800b85da  js      loc_1800B8886
0x1800b85e0  mov     rsi, [rdi+0C8h]
0x1800b85e7  xor     r14d, r14d
0x1800b85ea  test    rsi, rsi
0x1800b85ed  jz      loc_1800B86CD
0x1800b85f3  cmp     [rsi], r14w
0x1800b85f7  jz      loc_1800B86CD
0x1800b85fd  lea     r8, [rsp+190h+var_130]; unsigned __int64 *
0x1800b8602  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800b8607  mov     rcx, rsi; unsigned __int16 *
0x1800b860a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800b860f  mov     ebx, eax
0x1800b8611  test    eax, eax
0x1800b8613  js      loc_1800B8886
0x1800b8619  mov     rax, [rsp+190h+var_130]
0x1800b861e  cmp     [rsi], r14w
0x1800b8622  jz      loc_1800B86CD
0x1800b8628  mov     rbx, [rbp+90h+arg_8]
0x1800b862f  inc     rax
0x1800b8632  lea     r14, [rsi+rax*2]
0x1800b8636  xor     eax, eax
0x1800b8638  test    r14, r14
0x1800b863b  jz      loc_1800B86DD
0x1800b8641  cmp     [r14], ax
0x1800b8645  jz      loc_1800B86DD
0x1800b864b  mov     rcx, [rsp+190h+var_128]
0x1800b8650  mov     r9, rsi
0x1800b8653  mov     r8, r14
0x1800b8656  mov     qword ptr [rsp+190h+var_170], rbx
0x1800b865b  mov     rdx, r12
0x1800b865e  call    SplAddPrintProcessor
0x1800b8663  test    eax, eax
0x1800b8665  jnz     short loc_1800B86DD
0x1800b8667  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800b866c  xor     r8d, r8d; struct _INISPOOLER *
0x1800b866f  cmp     ax, 0BBDh
0x1800b8673  mov     edx, r8d
0x1800b8676  mov     ebx, r8d
0x1800b8679  cmovnz  edx, eax
0x1800b867c  cmp     dx, 70Dh
0x1800b8681  cmovnz  ebx, edx
0x1800b8684  test    ebx, ebx
0x1800b8686  jns     short loc_1800B86D6
0x1800b8688  mov     r9, rsi
0x1800b868b  mov     dword ptr [rsp+190h+var_170], ebx
0x1800b868f  mov     r8, r14
0x1800b8692  lea     rdx, aFailedAddingPr; "Failed adding print processor %ws(%ws),"...
0x1800b8699  lea     rcx, aNpackageinstal; "NPackageInstallLocalspl::LegacyInstallP"...
0x1800b86a0  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800b86a5  call    cs:__imp_GetLastError
0x1800b86ab  mov     edx, [rdi+0ACh]
0x1800b86b1  xor     ecx, ecx
0x1800b86b3  test    edx, edx
0x1800b86b5  jz      short loc_1800B86BE
0x1800b86b7  mov     rcx, [rdi+0E0h]
0x1800b86be  mov     r9, r14
0x1800b86c1  lea     r8, aSpladdprintpro_2; "SplAddPrintProcessor failed (print proc"...
0x1800b86c8  jmp     loc_1800B8846
0x1800b86cd  mov     rbx, [rbp+90h+arg_8]
0x1800b86d4  jmp     short loc_1800B86E0
0x1800b86d6  mov     rbx, [rbp+90h+arg_8]
0x1800b86dd  xor     r14d, r14d
0x1800b86e0  mov     rsi, [rbp+90h+arg_0]
0x1800b86e7  cmp     [rdi+0ACh], r14d
0x1800b86ee  jz      short loc_1800B8705
  ... truncated ...
```
