# UpgradePrinters(_INIDRIVER *,_INIVERSION *,_INIENVIRONMENT *,_INIPRINTER *,bool)

- ea: `0x1800c27d8`
- end: `0x1800c2d6e`
- name: `?UpgradePrinters@@YAJPEAU_INIDRIVER@@PEAU_INIVERSION@@PEAU_INIENVIRONMENT@@PEAU_INIPRINTER@@_N@Z`
- size: `1430`
- prototype: `__int64 __usercall@<rax>(struct _INIDRIVER *@<rcx>, struct _INIVERSION *@<rdx>, struct _INIENVIRONMENT *@<r8>, struct _INIPRINTER *@<r9>, bool)`
- caller_count: `4`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180057b58`
- `0x18007e088`
- `0x1800bdf84`
- `0x1800c2640`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800085ac`
- `0x1800086e0`
- `0x180008730`
- `0x18000edc4`
- `0x180014448`
- `0x18001fb10`
- `0x180035ae4`
- `0x1800372f8`
- `0x1800391d4`
- `0x180039818`
- `0x18003b010`
- `0x18003e984`
- `0x18003ea2c`
- `0x180042a80`
- `0x180046650`
- `0x180047330`
- `0x18004eb80`
- `0x180054638`
- `0x180073054`
- `0x180073be0`
- `0x18009cce4`
- `0x18009cd1c`
- `0x1800c2260`
- `0x1800c27d8`
- `0x1800ccbd8`
- `0x1800d8058`
- `0x1800d8210`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c29a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2aee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c29a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2aee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2c4b`
- `SPOOLSS!DllFreeSplStr` at `0x1800c2d0c`
- `SPOOLSS!DllFreeSplStr` at `0x1800c2d0c`
- `SPOOLSS!DllFreeSplMem` at `0x1800c2b94`
- `SPOOLSS!DllFreeSplMem` at `0x1800c2c85`
- `SPOOLSS!DllFreeSplMem` at `0x1800c2d03`
- `SPOOLSS!DllFreeSplMem` at `0x1800c2b94`
- `SPOOLSS!DllFreeSplMem` at `0x1800c2c85`
- `SPOOLSS!DllFreeSplMem` at `0x1800c2d03`
- `SPOOLSS!DllAllocSplMem` at `0x1800c2842`
- `SPOOLSS!DllAllocSplMem` at `0x1800c2842`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800c28ac`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800c2cf5`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800c28ac`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800c2cf5`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800c2d1f`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800c2d1f`

## string_xrefs

- `0x1800c2972`: `Failed to load config module during driver upgrade: hr: 0x%x`
- `0x1800c2b59`: `Failed to create DRIVER_UPGRADE_INFO_2 for printer '%ws'`
- `0x1800c2c54`: `UpdatePrinterIni failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UpgradePrinters(
        struct _INIDRIVER *a1,
        struct _INIVERSION *a2,
        struct _INIENVIRONMENT *a3,
        struct _INIPRINTER *a4,
        bool a5)
{
  unsigned int DriverInfoSize; // eax
  __int64 v9; // rbx
  unsigned __int8 *v10; // r13
  unsigned __int8 *v11; // rax
  const unsigned __int16 *ConfigFilePath; // r12
  signed int v13; // esi
  struct _INISPOOLER *i; // rdi
  __int64 v15; // rcx
  int ConfigModule; // eax
  __int64 v17; // rbx
  DWORD v18; // eax
  struct SplLogType *v19; // rax
  __int64 v20; // r14
  struct _INIPRINTER *v21; // rsi
  unsigned __int16 *PrinterName; // rbx
  __int64 v23; // rcx
  unsigned int v24; // r11d
  DWORD LastError; // eax
  DWORD v26; // eax
  DWORD v27; // eax
  struct _devicemodeW *v28; // rdi
  int v29; // ecx
  DWORD v30; // eax
  __int64 v31; // rbx
  const unsigned __int16 *v32; // rdi
  DWORD v33; // eax
  DWORD v34; // eax
  unsigned __int8 *v36; // [rsp+20h] [rbp-E0h]
  signed int v37; // [rsp+40h] [rbp-C0h]
  HANDLE hToken; // [rsp+48h] [rbp-B8h]
  struct _INISPOOLER *v39; // [rsp+50h] [rbp-B0h]
  __int128 v40; // [rsp+58h] [rbp-A8h] BYREF
  struct _INIPRINTER *v41; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v42; // [rsp+70h] [rbp-90h]
  int v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h]
  int v45; // [rsp+88h] [rbp-78h]
  int v46; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h]
  int v48; // [rsp+A0h] [rbp-60h]
  _BYTE v49[24]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 v50[112]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v51[12]; // [rsp+130h] [rbp+30h] BYREF

  v41 = a4;
  DriverInfoSize = GetDriverInfoSize(a1, 4u, 0, (__int64)pLocalIniSpooler);
  v9 = DriverInfoSize;
  v10 = 0;
  if ( !DriverInfoSize
    || (v11 = (unsigned __int8 *)DllAllocSplMem(DriverInfoSize), (v10 = v11) == 0)
    || !CopyIniDriverToDriverInfo((__int64)a3, (__int64)a2, (__int64)a1, 4u, v11, &v11[v9], 0, pLocalIniSpooler) )
  {
    ConfigFilePath = 0;
    goto LABEL_45;
  }
  ConfigFilePath = (const unsigned __int16 *)GetConfigFilePath((__int64)a1, (__int64)pLocalIniSpooler);
  if ( !ConfigFilePath )
  {
LABEL_45:
    v13 = -2147418113;
    hToken = RevertToPrinterSelf();
    goto LABEL_46;
  }
  v13 = 0;
  hToken = RevertToPrinterSelf();
  if ( a1 )
    SafeIncrementReference((unsigned int *)a1 + 4);
  for ( i = pLocalIniSpooler; ; i = (struct _INISPOOLER *)*((_QWORD *)i + 1) )
  {
    v39 = i;
    if ( !i )
      break;
    if ( (*((_DWORD *)i + 42) & 0x20000) != 0 )
    {
      SafeIncrementReference((unsigned int *)i + 4);
      LeaveSplSem(v15);
      v40 = 0;
      ConfigModule = sandbox::DriverConfigModuleAdapter::LoadConfigModule(
                       (sandbox::DriverConfigModuleAdapter *)&v40,
                       *((struct sandbox::SandboxManager **)i + 46),
                       ConfigFilePath,
                       0,
                       *((const unsigned __int16 **)a1 + 3),
                       *((_DWORD *)a1 + 50),
                       0);
      v13 = ConfigModule;
      v37 = ConfigModule;
      if ( ConfigModule > 0 )
      {
        v13 = (unsigned __int16)ConfigModule | 0x80070000;
        v37 = v13;
      }
      EnterSplSem(0);
      if ( *((_DWORD *)i + 4) )
        SafeDecrementReference((unsigned int *)i + 4);
      DeleteSpoolerCheck(i);
      if ( v13 >= 0 )
      {
        v20 = *((_QWORD *)i + 5);
        if ( v20 )
        {
          v21 = v41;
          do
          {
            if ( *(struct _INIDRIVER **)(v20 + 88) == a1 && (!v21 || v21 == (struct _INIPRINTER *)v20) )
            {
              UpdatePrinterStatusEx((struct _INIPRINTER *)v20);
              PrinterName = pszGetPrinterName((struct _INIPRINTER *)v20, 1, L"LocalOnly");
              v42 = PrinterName;
              if ( PrinterName )
              {
                if ( SafeIncrementReference((unsigned int *)(v20 + 16)) > *(_DWORD *)(v20 + 248) )
                {
                  v23 = *(unsigned int *)(v20 + 16);
                  *(_DWORD *)(v20 + 248) = v23;
                }
                LeaveSplSem(v23);
                memset_0(v50, 0, 0x68u);
                if ( (unsigned int)UpdateUpgradeInfoStruct(
                                     v50,
                                     2u,
                                     PrinterName,
                                     (unsigned __int16 *)&qword_1800EBF90,
                                     v10) )
                {
                  if ( !(unsigned int)sandbox::DriverConfigModuleAdapter::DrvUpgradePrinter(
                                        (sandbox::DriverConfigModuleAdapter *)&v40,
                                        v24,
                                        v50) )
                  {
                    LastError = GetLastError();
                    LocalSpoolerTelemetry::WriteDbgTraceWarning(
                      "UpgradePrinters",
                      L"DrvUpgradePrinter for printer '%ws' failed to upgrade: %d",
                      PrinterName,
                      LastError);
                    v26 = GetLastError();
                    StringCchPrintfW(v51, 0xBu, L"%d", v26);
                    v27 = GetLastError();
                    SplLogEvent(&MSG_DRIVER_FAILED_UPGRADE, v27, PrinterName, ConfigFilePath, v51, 0);
                  }
                }
                else
                {
                  LocalSpoolerTelemetry::WriteDbgTraceWarning(
                    "UpgradePrinters",
                    L"Failed to create DRIVER_UPGRADE_INFO_2 for printer '%ws'");
                }
                EnterSplSem(0);
                v28 = ConvertDevModeToSpecifiedVersion(
                        (struct _INIPRINTER *)v20,
                        *(struct _devicemodeW **)(v20 + 104),
                        (__int64)ConfigFilePath,
                        PrinterName,
                        0);
                DllFreeSplMem(*(_QWORD *)(v20 + 104));
                *(_QWORD *)(v20 + 104) = v28;
                if ( v28 )
                {
                  *(_DWORD *)(v20 + 400) &= ~0x200u;
                  v29 = v28->dmSize + v28->dmDriverExtra;
                }
                else
                {
                  LODWORD(v36) = GetLastError();
                  LocalSpoolerTelemetry::WriteDbgTraceWarning(
                    "UpgradePrinters",
                    L"DevMode conversion on upgrade for '%ws' (driver '%ws') failed to upgrade: %d",
                    *(_QWORD *)(v20 + 24),
                    *((_QWORD *)a1 + 3),
                    v36);
                  v30 = GetLastError();
                  StringCchPrintfW(v51, 0xBu, L"%d", v30);
                  v31 = *((_QWORD *)a1 + 3);
                  v32 = *(const unsigned __int16 **)(v20 + 24);
                  v33 = GetLastError();
                  SplLogEvent(&MSG_DRIVER_FAILED_UPGRADE, v33, v32, v31, v51, 0);
                  v29 = 0;
                  PrinterName = v42;
                }
                *(_DWORD *)(v20 + 96) = v29;
                if ( !(unsigned int)UpdatePrinterIni((_INIPRINTER *)v20, 1) )
                {
                  v34 = GetLastError();
                  LocalSpoolerTelemetry::WriteDbgTraceWarning("UpgradePrinters", L"UpdatePrinterIni failed: %d", v34);
                }
                LocalSpoolerTelemetry::WriteDbgTraceInfo(
                  "UpgradePrinters",
                  L"Upgraded print queue '%ws' due to driver upgrade of driver '%ws'",
                  *(_QWORD *)(v20 + 24),
                  *((_QWORD *)a1 + 3));
                DllFreeSplMem(PrinterName);
                if ( a5 )
                  SetDisableWUFiltering((struct _INIPRINTER *)v20, 1);
                if ( *(_DWORD *)(v20 + 16) )
                  SafeDecrementReference((unsigned int *)(v20 + 16));
              }
            }
            v20 = *(_QWORD *)(v20 + 8);
          }
          while ( v20 );
          v13 = v37;
          i = v39;
        }
        sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v40);
      }
      else
      {
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "UpgradePrinters",
          L"Failed to load config module during driver upgrade: hr: 0x%x",
          (unsigned int)v13);
        v17 = WIN32_FROM_HRESULT(v13);
        StringCchPrintfW(v51, 0xBu, L"%d", v17);
        v18 = GetLastError();
        SplLogEvent(&MSG_DRIVER_FAILED_UPGRADE, v18, v51, ConfigFilePath, v51, 0);
        v43 = 100;
        v44 = 4;
        v45 = 0;
        v46 = v17;
        v47 = 4;
        v48 = 0;
        v19 = SplLogType::SplLogType((SplLogType *)v49, ConfigFilePath);
        SplLogEvent2(&LOAD_PLUGIN_FAILED_EVENT, v19, &v46, &v43, 0);
        sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v40);
      }
    }
  }
  if ( a1 && *((_DWORD *)a1 + 4) )
    SafeDecrementReference((unsigned int *)a1 + 4);
LABEL_46:
  DllFreeSplMem(v10);
  DllFreeSplStr(ConfigFilePath);
  if ( hToken )
    ImpersonatePrinterClient(hToken);
  if ( v13 < 0 )
    LocalSpoolerTelemetry::LogV4SupportError(a1, 0, L"UpgradePrinters", a5, v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800c27d8  mov     [rsp-8+arg_18], rbx
0x1800c27dd  push    rbp
0x1800c27de  push    rsi
0x1800c27df  push    rdi
0x1800c27e0  push    r12
0x1800c27e2  push    r13
0x1800c27e4  push    r14
0x1800c27e6  push    r15
0x1800c27e8  lea     rbp, [rsp-50h]
0x1800c27ed  sub     rsp, 150h
0x1800c27f4  mov     rax, cs:__security_cookie
0x1800c27fb  xor     rax, rsp
0x1800c27fe  mov     [rbp+80h+var_38], rax
0x1800c2802  mov     [rsp+180h+var_118], r9
0x1800c2807  mov     rsi, r8
0x1800c280a  mov     rdi, rdx
0x1800c280d  mov     r15, rcx
0x1800c2810  mov     rax, cs:pLocalIniSpooler
0x1800c2817  mov     qword ptr [rsp+180h+var_158], rax; __int64
0x1800c281c  xor     r14d, r14d
0x1800c281f  mov     [rsp+180h+var_160], r14; unsigned __int16 *
0x1800c2824  mov     r9, r8
0x1800c2827  mov     r8, rdx
0x1800c282a  lea     edx, [r14+4]; unsigned int
0x1800c282e  call    GetDriverInfoSize
0x1800c2833  mov     ebx, eax
0x1800c2835  mov     r13d, r14d
0x1800c2838  test    eax, eax
0x1800c283a  jz      loc_1800C2CED
0x1800c2840  mov     ecx, ebx
0x1800c2842  call    cs:__imp_DllAllocSplMem
0x1800c2848  mov     r13, rax
0x1800c284b  test    rax, rax
0x1800c284e  jz      loc_1800C2CED
0x1800c2854  lea     r8, [rbx+rax]
0x1800c2858  mov     rcx, cs:pLocalIniSpooler
0x1800c285f  mov     [rsp+180h+var_148], rcx
0x1800c2864  mov     qword ptr [rsp+180h+var_150], r14
0x1800c2869  mov     qword ptr [rsp+180h+var_158], r8
0x1800c286e  mov     [rsp+180h+var_160], rax
0x1800c2873  lea     r9d, [r14+4]
0x1800c2877  mov     r8, r15
0x1800c287a  mov     rdx, rdi
0x1800c287d  mov     rcx, rsi
0x1800c2880  call    CopyIniDriverToDriverInfo
0x1800c2885  test    rax, rax
0x1800c2888  jz      loc_1800C2CED
0x1800c288e  mov     rdx, cs:pLocalIniSpooler
0x1800c2895  mov     rcx, r15
0x1800c2898  call    GetConfigFilePath
0x1800c289d  mov     r12, rax
0x1800c28a0  test    rax, rax
0x1800c28a3  jz      loc_1800C2CF0
0x1800c28a9  mov     esi, r14d
0x1800c28ac  call    cs:__imp_RevertToPrinterSelf
0x1800c28b2  mov     [rsp+180h+hToken], rax
0x1800c28b7  test    r15, r15
0x1800c28ba  jz      short loc_1800C28C5
0x1800c28bc  lea     rcx, [r15+10h]; unsigned int *
0x1800c28c0  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x1800c28c5  mov     rdi, cs:pLocalIniSpooler
0x1800c28cc  test    rdi, rdi
0x1800c28cf  mov     [rsp+180h+var_130], rdi
0x1800c28d4  jz      loc_1800C2CD8
0x1800c28da  test    dword ptr [rdi+0A8h], 20000h
0x1800c28e4  jz      loc_1800C2CCF
0x1800c28ea  lea     rbx, [rdi+10h]
0x1800c28ee  mov     rcx, rbx; unsigned int *
0x1800c28f1  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x1800c28f6  call    LeaveSplSem
0x1800c28fb  xorps   xmm0, xmm0
0x1800c28fe  movdqu  [rsp+180h+var_128], xmm0
0x1800c2904  mov     [rsp+180h+var_150], r14d; unsigned int
0x1800c2909  mov     eax, [r15+0C8h]
0x1800c2910  mov     [rsp+180h+var_158], eax; unsigned int
0x1800c2914  mov     rax, [r15+18h]
0x1800c2918  mov     [rsp+180h+var_160], rax; unsigned __int16 *
0x1800c291d  xor     r9d, r9d; unsigned __int16 *
0x1800c2920  mov     r8, r12; unsigned __int16 *
0x1800c2923  mov     rdx, [rdi+170h]; struct sandbox::SandboxManager *
0x1800c292a  lea     rcx, [rsp+180h+var_128]; this
0x1800c292f  call    ?LoadConfigModule@DriverConfigModuleAdapter@sandbox@@QEAAKPEAVSandboxManager@2@PEBG11KK@Z; sandbox::DriverConfigModuleAdapter::LoadConfigModule(sandbox::SandboxManager *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800c2934  mov     esi, eax
0x1800c2936  mov     [rsp+180h+var_140], eax
0x1800c293a  test    eax, eax
0x1800c293c  jle     short loc_1800C294B
0x1800c293e  movzx   esi, ax
0x1800c2941  or      esi, 80070000h
0x1800c2947  mov     [rsp+180h+var_140], esi
0x1800c294b  xor     ecx, ecx
0x1800c294d  call    EnterSplSem
0x1800c2952  cmp     [rbx], r14d
0x1800c2955  jz      short loc_1800C295F
0x1800c2957  mov     rcx, rbx; unsigned int *
0x1800c295a  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800c295f  mov     rcx, rdi
0x1800c2962  call    DeleteSpoolerCheck
0x1800c2967  test    esi, esi
0x1800c2969  jns     loc_1800C2A28
0x1800c296f  mov     r8d, esi
0x1800c2972  lea     rdx, aFailedToLoadCo; "Failed to load config module during dri"...
0x1800c2979  lea     rcx, aUpgradeprinter; "UpgradePrinters"
0x1800c2980  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c2985  mov     ecx, esi; int
0x1800c2987  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800c298c  mov     ebx, eax
0x1800c298e  mov     r9d, eax
0x1800c2991  lea     r8, aD; "%d"
0x1800c2998  mov     edx, 0Bh; unsigned __int64
0x1800c299d  lea     rcx, [rbp+80h+var_50]; unsigned __int16 *
0x1800c29a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c29a6  call    cs:__imp_GetLastError
0x1800c29ac  mov     edx, eax; unsigned int
0x1800c29ae  mov     qword ptr [rsp+180h+var_158], r14
0x1800c29b3  lea     rax, [rbp+80h+var_50]
0x1800c29b7  mov     [rsp+180h+var_160], rax
0x1800c29bc  mov     r9, r12
0x1800c29bf  lea     r8, [rbp+80h+var_50]; unsigned __int16 *
0x1800c29c3  lea     rcx, MSG_DRIVER_FAILED_UPGRADE; struct _EVENT_DESCRIPTOR *
0x1800c29ca  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800c29cf  mov     [rsp+180h+var_108], 64h ; 'd'
0x1800c29d7  mov     eax, 4
0x1800c29dc  mov     [rbp+80h+var_100], rax
0x1800c29e0  mov     [rbp+80h+var_F8], r14d
0x1800c29e4  mov     [rbp+80h+var_F0], ebx
0x1800c29e7  mov     [rbp+80h+var_E8], rax
0x1800c29eb  mov     [rbp+80h+var_E0], r14d
0x1800c29ef  mov     rdx, r12; unsigned __int16 *
0x1800c29f2  lea     rcx, [rbp+80h+var_D8]; this
0x1800c29f6  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800c29fb  mov     [rsp+180h+var_160], r14
0x1800c2a00  lea     r9, [rsp+180h+var_108]
0x1800c2a05  lea     r8, [rbp+80h+var_F0]
0x1800c2a09  mov     rdx, rax; struct SplLogType *
0x1800c2a0c  lea     rcx, LOAD_PLUGIN_FAILED_EVENT; struct _EVENT_DESCRIPTOR *
0x1800c2a13  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x1800c2a18  nop
0x1800c2a19  lea     rcx, [rsp+180h+var_128]; this
0x1800c2a1e  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x1800c2a23  jmp     loc_1800C2CCF
0x1800c2a28  mov     r14, [rdi+28h]
0x1800c2a2c  test    r14, r14
0x1800c2a2f  jz      loc_1800C2CC2
0x1800c2a35  mov     rsi, [rsp+180h+var_118]
0x1800c2a3a  cmp     [r14+58h], r15
0x1800c2a3e  jnz     loc_1800C2CAC
0x1800c2a44  test    rsi, rsi
0x1800c2a47  jz      short loc_1800C2A52
0x1800c2a49  cmp     rsi, r14
0x1800c2a4c  jnz     loc_1800C2CAC
0x1800c2a52  mov     rcx, r14; struct _INIPRINTER *
0x1800c2a55  call    ?UpdatePrinterStatusEx@@YAXPEAU_INIPRINTER@@@Z; UpdatePrinterStatusEx(_INIPRINTER *)
0x1800c2a5a  lea     r8, aLocalonly_0; "LocalOnly"
0x1800c2a61  mov     edx, 1; int
0x1800c2a66  mov     rcx, r14; struct _INIPRINTER *
0x1800c2a69  call    ?pszGetPrinterName@@YAPEAGPEAU_INIPRINTER@@HPEBG@Z; pszGetPrinterName(_INIPRINTER *,int,ushort const *)
0x1800c2a6e  mov     rbx, rax
0x1800c2a71  mov     [rsp+180h+var_110], rax
0x1800c2a76  test    rax, rax
0x1800c2a79  jz      loc_1800C2CAC
0x1800c2a7f  lea     rcx, [r14+10h]; unsigned int *
0x1800c2a83  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x1800c2a88  cmp     eax, [r14+0F8h]
0x1800c2a8f  jbe     short loc_1800C2A9C
0x1800c2a91  mov     ecx, [r14+10h]
0x1800c2a95  mov     [r14+0F8h], ecx
0x1800c2a9c  call    LeaveSplSem
0x1800c2aa1  xor     edx, edx; Val
0x1800c2aa3  lea     r8d, [rdx+68h]; Size
0x1800c2aa7  lea     rcx, [rbp+80h+var_C0]; void *
0x1800c2aab  call    memset_0
0x1800c2ab0  mov     [rsp+180h+var_160], r13; unsigned __int8 *
0x1800c2ab5  lea     r9, qword_1800EBF90; unsigned __int16 *
0x1800c2abc  mov     r8, rbx; unsigned __int16 *
0x1800c2abf  mov     r11d, 2
0x1800c2ac5  mov     edx, r11d; unsigned int
0x1800c2ac8  lea     rcx, [rbp+80h+var_C0]; unsigned __int8 *
0x1800c2acc  call    ?UpdateUpgradeInfoStruct@@YAHPEAEKPEAG10@Z; UpdateUpgradeInfoStruct(uchar *,ulong,ushort *,ushort *,uchar *)
0x1800c2ad1  test    eax, eax
0x1800c2ad3  jz      loc_1800C2B59
0x1800c2ad9  lea     r8, [rbp+80h+var_C0]; unsigned __int8 *
0x1800c2add  mov     edx, r11d; unsigned int
0x1800c2ae0  lea     rcx, [rsp+180h+var_128]; this
0x1800c2ae5  call    ?DrvUpgradePrinter@DriverConfigModuleAdapter@sandbox@@QEAAHKPEAE@Z; sandbox::DriverConfigModuleAdapter::DrvUpgradePrinter(ulong,uchar *)
0x1800c2aea  test    eax, eax
0x1800c2aec  jnz     short loc_1800C2B6C
0x1800c2aee  call    cs:__imp_GetLastError
0x1800c2af4  mov     r9d, eax
0x1800c2af7  mov     r8, rbx
0x1800c2afa  lea     rdx, aDrvupgradeprin; "DrvUpgradePrinter for printer '%ws' fai"...
0x1800c2b01  lea     rcx, aUpgradeprinter; "UpgradePrinters"
0x1800c2b08  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800c2b0d  call    cs:__imp_GetLastError
0x1800c2b13  mov     r9d, eax
0x1800c2b16  lea     r8, aD; "%d"
0x1800c2b1d  mov     edx, 0Bh; unsigned __int64
0x1800c2b22  lea     rcx, [rbp+80h+var_50]; unsigned __int16 *
0x1800c2b26  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c2b2b  call    cs:__imp_GetLastError
0x1800c2b31  mov     edx, eax; unsigned int
0x1800c2b33  mov     qword ptr [rsp+180h+var_158], 0
0x1800c2b3c  lea     rax, [rbp+80h+var_50]
0x1800c2b40  mov     [rsp+180h+var_160], rax
0x1800c2b45  mov     r9, r12
0x1800c2b48  mov     r8, rbx; unsigned __int16 *
0x1800c2b4b  lea     rcx, MSG_DRIVER_FAILED_UPGRADE; struct _EVENT_DESCRIPTOR *
0x1800c2b52  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800c2b57  jmp     short loc_1800C2B6C
0x1800c2b59  lea     rdx, aFailedToCreate_3; "Failed to create DRIVER_UPGRADE_INFO_2 "...
0x1800c2b60  lea     rcx, aUpgradeprinter; "UpgradePrinters"
0x1800c2b67  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800c2b6c  xor     ecx, ecx
0x1800c2b6e  call    EnterSplSem
0x1800c2b73  mov     dword ptr [rsp+180h+var_160], 0; int
0x1800c2b7b  mov     r9, rbx
0x1800c2b7e  mov     r8, r12
0x1800c2b81  mov     rdx, [r14+68h]; Src
0x1800c2b85  mov     rcx, r14; struct _INIPRINTER *
0x1800c2b88  call    ConvertDevModeToSpecifiedVersion
0x1800c2b8d  mov     rdi, rax
0x1800c2b90  mov     rcx, [r14+68h]
0x1800c2b94  call    cs:__imp_DllFreeSplMem
0x1800c2b9a  mov     [r14+68h], rdi
0x1800c2b9e  test    rdi, rdi
0x1800c2ba1  jz      short loc_1800C2BB8
0x1800c2ba3  btr     dword ptr [r14+190h], 9
0x1800c2bac  movzx   ecx, word ptr [rdi+46h]
0x1800c2bb0  movzx   eax, word ptr [rdi+44h]
0x1800c2bb4  add     ecx, eax
0x1800c2bb6  jmp     short loc_1800C2C36
0x1800c2bb8  call    cs:__imp_GetLastError
0x1800c2bbe  mov     dword ptr [rsp+180h+var_160], eax
0x1800c2bc2  mov     r9, [r15+18h]
0x1800c2bc6  mov     r8, [r14+18h]
0x1800c2bca  lea     rdx, aDevmodeConvers_0; "DevMode conversion on upgrade for '%ws'"...
0x1800c2bd1  lea     rcx, aUpgradeprinter; "UpgradePrinters"
0x1800c2bd8  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800c2bdd  call    cs:__imp_GetLastError
0x1800c2be3  mov     r9d, eax
0x1800c2be6  lea     r8, aD; "%d"
0x1800c2bed  mov     edx, 0Bh; unsigned __int64
0x1800c2bf2  lea     rcx, [rbp+80h+var_50]; unsigned __int16 *
0x1800c2bf6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c2bfb  mov     rbx, [r15+18h]
0x1800c2bff  mov     rdi, [r14+18h]
0x1800c2c03  call    cs:__imp_GetLastError
0x1800c2c09  mov     qword ptr [rsp+180h+var_158], 0
0x1800c2c12  lea     rcx, [rbp+80h+var_50]
0x1800c2c16  mov     [rsp+180h+var_160], rcx
0x1800c2c1b  mov     r9, rbx
0x1800c2c1e  mov     r8, rdi; unsigned __int16 *
0x1800c2c21  mov     edx, eax; unsigned int
0x1800c2c23  lea     rcx, MSG_DRIVER_FAILED_UPGRADE; struct _EVENT_DESCRIPTOR *
0x1800c2c2a  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800c2c2f  xor     ecx, ecx
0x1800c2c31  mov     rbx, [rsp+180h+var_110]
0x1800c2c36  mov     [r14+60h], ecx
0x1800c2c3a  mov     edx, 1
0x1800c2c3f  mov     rcx, r14; this
0x1800c2c42  call    UpdatePrinterIni
0x1800c2c47  test    eax, eax
0x1800c2c49  jnz     short loc_1800C2C67
0x1800c2c4b  call    cs:__imp_GetLastError
0x1800c2c51  mov     r8d, eax
0x1800c2c54  lea     rdx, aUpdateprinteri_0; "UpdatePrinterIni failed: %d"
0x1800c2c5b  lea     rcx, aUpgradeprinter; "UpgradePrinters"
0x1800c2c62  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800c2c67  mov     r9, [r15+18h]
0x1800c2c6b  mov     r8, [r14+18h]
0x1800c2c6f  lea     rdx, aUpgradedPrintQ; "Upgraded print queue '%ws' due to drive"...
0x1800c2c76  lea     rcx, aUpgradeprinter; "UpgradePrinters"
0x1800c2c7d  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c2c82  mov     rcx, rbx
0x1800c2c85  call    cs:__imp_DllFreeSplMem
0x1800c2c8b  cmp     [rbp+80h+arg_20], 0
0x1800c2c92  jz      short loc_1800C2C9E
0x1800c2c94  mov     dl, 1; bool
0x1800c2c96  mov     rcx, r14; struct _INIPRINTER *
0x1800c2c99  call    ?SetDisableWUFiltering@@YAXPEAU_INIPRINTER@@_N@Z; SetDisableWUFiltering(_INIPRINTER *,bool)
0x1800c2c9e  lea     rcx, [r14+10h]; unsigned int *
0x1800c2ca2  cmp     dword ptr [rcx], 0
0x1800c2ca5  jz      short loc_1800C2CAC
0x1800c2ca7  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800c2cac  mov     r14, [r14+8]
0x1800c2cb0  test    r14, r14
0x1800c2cb3  jnz     loc_1800C2A3A
0x1800c2cb9  mov     esi, [rsp+180h+var_140]
0x1800c2cbd  mov     rdi, [rsp+180h+var_130]
0x1800c2cc2  lea     rcx, [rsp+180h+var_128]; this
0x1800c2cc7  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x1800c2ccc  xor     r14d, r14d
0x1800c2ccf  mov     rdi, [rdi+8]
0x1800c2cd3  jmp     loc_1800C28CC
0x1800c2cd8  test    r15, r15
0x1800c2cdb  jz      short loc_1800C2D00
0x1800c2cdd  lea     rcx, [r15+10h]; unsigned int *
0x1800c2ce1  cmp     [rcx], r14d
0x1800c2ce4  jz      short loc_1800C2D00
0x1800c2ce6  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800c2ceb  jmp     short loc_1800C2D00
  ... truncated ...
```
