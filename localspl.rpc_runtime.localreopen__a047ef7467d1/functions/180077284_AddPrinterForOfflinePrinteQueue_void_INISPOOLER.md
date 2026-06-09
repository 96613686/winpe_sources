# AddPrinterForOfflinePrinteQueue(void *,_INISPOOLER *)

- ea: `0x180077284`
- end: `0x18007797e`
- name: `?AddPrinterForOfflinePrinteQueue@@YAKPEAXPEAU_INISPOOLER@@@Z`
- size: `1786`
- prototype: `unsigned int __fastcall(void *, struct _INISPOOLER *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180077c0c`

## callees

- `0x1800081c0`
- `0x180011f00`
- `0x180015e28`
- `0x180016fb0`
- `0x1800170a0`
- `0x180038300`
- `0x18003e984`
- `0x18003ea2c`
- `0x18004486c`
- `0x180046650`
- `0x180047330`
- `0x1800547e0`
- `0x180055b20`
- `0x180055bd0`
- `0x180071b20`
- `0x180077284`
- `0x1800baec4`
- `0x1800bb038`
- `0x1800c7dc4`
- `0x1800ca0fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077698`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800778a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800778a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077610`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077610`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180077640`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180077640`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18007773f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180077774`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18007773f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180077774`
- `SPOOLSS!DllFreeSplStr` at `0x1800778f4`
- `SPOOLSS!DllFreeSplStr` at `0x1800778ff`
- `SPOOLSS!DllFreeSplStr` at `0x18007790a`
- `SPOOLSS!DllFreeSplStr` at `0x180077914`
- `SPOOLSS!DllFreeSplStr` at `0x18007791e`
- `SPOOLSS!DllFreeSplStr` at `0x180077928`
- `SPOOLSS!DllFreeSplStr` at `0x180077932`
- `SPOOLSS!DllFreeSplStr` at `0x18007793c`
- `SPOOLSS!DllFreeSplStr` at `0x180077946`
- `SPOOLSS!DllFreeSplStr` at `0x180077950`
- `SPOOLSS!DllFreeSplStr` at `0x1800778f4`
- `SPOOLSS!DllFreeSplStr` at `0x1800778ff`
- `SPOOLSS!DllFreeSplStr` at `0x18007790a`
- `SPOOLSS!DllFreeSplStr` at `0x180077914`
- `SPOOLSS!DllFreeSplStr` at `0x18007791e`
- `SPOOLSS!DllFreeSplStr` at `0x180077928`
- `SPOOLSS!DllFreeSplStr` at `0x180077932`
- `SPOOLSS!DllFreeSplStr` at `0x18007793c`
- `SPOOLSS!DllFreeSplStr` at `0x180077946`
- `SPOOLSS!DllFreeSplStr` at `0x180077950`

## string_xrefs

- `0x180077765`: `Microsoft XPS Document Writer`
- `0x180077809`: `Microsoft XPS Document Writer`
- `0x180077830`: `Microsoft XPS Document Writer`
- `0x180077405`: `pComment`
- `0x180077606`: `InfPath`
- `0x1800773d9`: `pShareName`
- `0x1800778d9`: `Failed to get required fields (pPrinterName, pPortName, pDriverName, pPrintProcessor) for offline printer queue installation from registry.`
- `0x180077816`: `Could not delete driver %ws. Error %d`
- `0x18007783a`: `Deleted driver %ws successfully`
- `0x180077846`: `Attempt to add the printer`
- `0x1800778c0`: `All the required fields (pPrinterName, pPortName, pDriverName, pPrintProcessor) for offline printer queue installation not found.`
- `0x180077738`: `Microsoft XPS Document Writer v4`

## pseudocode

```c
__int64 __fastcall AddPrinterForOfflinePrinteQueue(HKEY a1, struct _INISPOOLER *a2)
{
  NCoreLibrary *v4; // rcx
  int LastErrorAsFailHRNoBreak; // eax
  __int64 v6; // rdi
  _QWORD *v7; // rsi
  _QWORD *v8; // r14
  const WCHAR *v9; // rcx
  DWORD LastError; // eax
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v14; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v15; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h]
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v19[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v20; // [rsp+78h] [rbp-88h]
  LPCWSTR lpString1; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  __int64 v23; // [rsp+90h] [rbp-70h]
  __int64 v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+A8h] [rbp-58h]
  __int64 v26; // [rsp+B0h] [rbp-50h]
  __int64 v27; // [rsp+B8h] [rbp-48h]
  unsigned __int8 v28[4]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 v29[4]; // [rsp+CCh] [rbp-34h] BYREF
  unsigned __int8 v30[4]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 v31[4]; // [rsp+D4h] [rbp-2Ch] BYREF
  unsigned __int8 v32[24]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v33; // [rsp+F0h] [rbp-10h]
  __int64 v34; // [rsp+100h] [rbp+0h]
  WCHAR Dst[264]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v36[264]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR Data[264]; // [rsp+530h] [rbp+430h] BYREF

  v14 = 0;
  v12 = 0;
  v15 = 0;
  v16 = 0;
  memset_0(v19, 0, 0x80u);
  cbData = 0;
  v18 = 0;
  if ( !(unsigned int)RegGetString(a1, L"pPrinterName", (__int64)&cbData, 1, a2)
    || !(unsigned int)RegGetString(a1, L"pPortName", (__int64)&cbData, 1, a2)
    || !(unsigned int)RegGetString(a1, L"pDriverName", (__int64)&cbData, 1, a2)
    || !(unsigned int)RegGetString(a1, L"pPrintProcessor", (__int64)&cbData, 1, a2) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "AddPrinterForOfflinePrinteQueue",
      L"Failed to get required fields (pPrinterName, pPortName, pDriverName, pPrintProcessor) for offline printer queue in"
       "stallation from registry.");
    LODWORD(v6) = -1;
    goto LABEL_38;
  }
  RegGetString(a1, L"pShareName", (__int64)&cbData, 0, a2);
  RegGetString(a1, L"pComment", (__int64)&cbData, 0, a2);
  RegGetString(a1, L"pLocation", (__int64)&cbData, 0, a2);
  RegGetString(a1, L"pSepFile", (__int64)&cbData, 0, a2);
  RegGetString(a1, L"pDatatype", (__int64)&cbData, 0, a2);
  RegGetString(a1, L"pParameters", (__int64)&cbData, 0, a2);
  v14 = 4;
  SplRegQueryValue(a1, L"Attributes", &v15, v28, &v14, a2);
  v14 = 4;
  SplRegQueryValue(a1, L"Priority", &v15, v29, &v14, a2);
  v14 = 4;
  SplRegQueryValue(a1, L"Default Priority", &v15, v30, &v14, a2);
  v14 = 4;
  SplRegQueryValue(a1, L"StartTime", &v15, v31, &v14, a2);
  v14 = 4;
  SplRegQueryValue(a1, L"UntilTime", &v15, v32, &v14, a2);
  if ( !v19[0] || !v20 || !lpString1 || !v25 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "AddPrinterForOfflinePrinteQueue",
      L"All the required fields (pPrinterName, pPortName, pDriverName, pPrintProcessor) for offline printer queue installation not found.");
    LODWORD(v6) = cbData;
    goto LABEL_38;
  }
  memset_0(Data, 0, 0x208u);
  Type = 0;
  cbData = 520;
  if ( !RegQueryValueExW(a1, L"InfPath", 0, &Type, (LPBYTE)Data, &cbData) )
  {
    memset_0(Dst, 0, 0x208u);
    if ( ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
    {
      if ( !(unsigned int)IsInInfDir(Dst) )
      {
        memset_0(v36, 0, 0x208u);
        v12 = 260;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl)
          && !(unsigned int)_o__wcsicmp(L"Microsoft Print To PDF", v19[0])
          && (unsigned int)IsWindowsProtectedPrintEnabled() )
        {
          LastErrorAsFailHRNoBreak = InstallPrintToPDFDriverViaBroker(v36, &v12);
        }
        else
        {
          LastErrorAsFailHRNoBreak = SplUploadPrinterDriverPackage(
                                       0,
                                       Dst,
                                       L"Windows x64",
                                       v36,
                                       (__int64)&v12,
                                       (__int64)a2);
        }
        if ( LastErrorAsFailHRNoBreak < 0 )
          goto LABEL_22;
        LastErrorAsFailHRNoBreak = StringCchCopyW(Dst, 0x104u, v36);
        if ( LastErrorAsFailHRNoBreak < 0 )
          goto LABEL_22;
      }
      LastErrorAsFailHRNoBreak = SplInstallPrinterDriverFromPackage(
                                   0,
                                   Dst,
                                   (unsigned __int16 *)lpString1,
                                   L"Windows x64",
                                   0,
                                   (unsigned int)a2);
    }
    else
    {
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v4);
    }
    if ( LastErrorAsFailHRNoBreak < 0 )
    {
LABEL_22:
      LODWORD(v6) = (unsigned __int16)LastErrorAsFailHRNoBreak;
      goto LABEL_38;
    }
  }
  if ( !lstrcmpW(lpString1, L"Microsoft XPS Document Writer v4") )
  {
    v7 = (_QWORD *)*((_QWORD *)a2 + 5);
    if ( v7 )
    {
      do
      {
        v8 = (_QWORD *)v7[1];
        if ( !lstrcmpW(*(LPCWSTR *)(v7[11] + 24LL), L"Microsoft XPS Document Writer") )
        {
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "AddPrinterForOfflinePrinteQueue",
            L"Found print queue %ws using  MXDW V3 driver",
            v7[3]);
          v9 = (const WCHAR *)v7[3];
          v34 = 983052;
          v33 = 0;
          if ( (unsigned int)LocalOpenPrinterEx(v9, 0) )
          {
            SplDeletePrinter(v16);
            SplClosePrinter(v16);
          }
          if ( (unsigned int)LocalDeletePrinterDriverEx(
                               *(_QWORD *)(v7[35] + 24LL),
                               *(_QWORD *)(*(_QWORD *)(v7[35] + 48LL) + 24LL),
                               *(_QWORD *)(v7[11] + 24LL),
                               0,
                               0) )
          {
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "AddPrinterForOfflinePrinteQueue",
              L"Deleted driver %ws successfully",
              L"Microsoft XPS Document Writer");
            break;
          }
          LastError = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "AddPrinterForOfflinePrinteQueue",
            L"Could not delete driver %ws. Error %d",
            L"Microsoft XPS Document Writer",
            LastError);
        }
        v7 = v8;
      }
      while ( v8 );
    }
  }
  LocalSpoolerTelemetry::WriteDbgTraceInfo("AddPrinterForOfflinePrinteQueue", L"Attempt to add the printer");
  v16 = SplAddPrinter(0, 2, (unsigned int)&v18, (_DWORD)a2, 0, 0, 0);
  if ( (unsigned __int64)(v16 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v6 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "AddPrinterForOfflinePrinteQueue",
      L"SplAddPrinter returns an invalid printer handle with ERROR: %d",
      v6);
  }
  else
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "AddPrinterForOfflinePrinteQueue",
      L"SplAddPrinter returns a valid printer handle and close this printer handle.");
    SplClosePrinter(v16);
    LODWORD(v6) = 0;
  }
LABEL_38:
  DllFreeSplStr(v19[0]);
  DllFreeSplStr(v19[1]);
  DllFreeSplStr(v20);
  DllFreeSplStr(lpString1);
  DllFreeSplStr(v22);
  DllFreeSplStr(v23);
  DllFreeSplStr(v24);
  DllFreeSplStr(v25);
  DllFreeSplStr(v26);
  DllFreeSplStr(v27);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180077284  mov     [rsp-8+arg_10], rbx
0x180077289  push    rbp
0x18007728a  push    rsi
0x18007728b  push    rdi
0x18007728c  push    r14
0x18007728e  push    r15
0x180077290  lea     rbp, [rsp-650h]
0x180077298  sub     rsp, 750h
0x18007729f  mov     rax, cs:__security_cookie
0x1800772a6  xor     rax, rsp
0x1800772a9  mov     [rbp+670h+var_30], rax
0x1800772b0  xor     r15d, r15d
0x1800772b3  mov     rdi, rdx
0x1800772b6  mov     rbx, rcx
0x1800772b9  mov     [rsp+770h+var_728], r15d
0x1800772be  xor     edx, edx; Val
0x1800772c0  mov     [rsp+770h+var_730], r15d
0x1800772c5  lea     rcx, [rsp+770h+var_708]; void *
0x1800772ca  mov     [rsp+770h+var_724], r15d
0x1800772cf  mov     r8d, 80h; Size
0x1800772d5  mov     [rsp+770h+var_720], r15
0x1800772da  call    memset_0
0x1800772df  lea     rax, [rsp+770h+cbData]
0x1800772e4  mov     [rsp+770h+var_740], rdi; struct _INISPOOLER *
0x1800772e9  lea     esi, [r15+1]
0x1800772ed  mov     [rsp+770h+cbData], r15d
0x1800772f2  mov     dword ptr [rsp+770h+lpcbData], esi; int
0x1800772f6  lea     r9, [rsp+770h+var_730]
0x1800772fb  lea     r8, [rsp+770h+var_708]
0x180077300  mov     [rsp+770h+lpData], rax; __int64
0x180077305  lea     rdx, aPprintername; "pPrinterName"
0x18007730c  mov     [rsp+770h+var_710], r15
0x180077311  mov     rcx, rbx; void *
0x180077314  call    RegGetString
0x180077319  test    eax, eax
0x18007731b  jz      loc_1800778D9
0x180077321  mov     [rsp+770h+var_740], rdi; struct _INISPOOLER *
0x180077326  lea     rax, [rsp+770h+cbData]
0x18007732b  mov     dword ptr [rsp+770h+lpcbData], esi; int
0x18007732f  lea     r9, [rsp+770h+var_730]
0x180077334  lea     r8, [rsp+770h+var_6F8]
0x180077339  mov     [rsp+770h+lpData], rax; __int64
0x18007733e  lea     rdx, aPportname; "pPortName"
0x180077345  mov     rcx, rbx; void *
0x180077348  call    RegGetString
0x18007734d  test    eax, eax
0x18007734f  jz      loc_1800778D9
0x180077355  mov     [rsp+770h+var_740], rdi; struct _INISPOOLER *
0x18007735a  lea     rax, [rsp+770h+cbData]
0x18007735f  mov     dword ptr [rsp+770h+lpcbData], esi; int
0x180077363  lea     r9, [rsp+770h+var_730]
0x180077368  lea     r8, [rbp+670h+lpString1]
0x18007736c  mov     [rsp+770h+lpData], rax; __int64
0x180077371  lea     rdx, aPdrivername; "pDriverName"
0x180077378  mov     rcx, rbx; void *
0x18007737b  call    RegGetString
0x180077380  test    eax, eax
0x180077382  jz      loc_1800778D9
0x180077388  mov     [rsp+770h+var_740], rdi; struct _INISPOOLER *
0x18007738d  lea     rax, [rsp+770h+cbData]
0x180077392  mov     dword ptr [rsp+770h+lpcbData], esi; int
0x180077396  lea     r9, [rsp+770h+var_730]
0x18007739b  lea     r8, [rbp+670h+var_6C8]
0x18007739f  mov     [rsp+770h+lpData], rax; __int64
0x1800773a4  lea     rdx, aPprintprocesso; "pPrintProcessor"
0x1800773ab  mov     rcx, rbx; void *
0x1800773ae  call    RegGetString
0x1800773b3  test    eax, eax
0x1800773b5  jz      loc_1800778D9
0x1800773bb  mov     [rsp+770h+var_740], rdi; struct _INISPOOLER *
0x1800773c0  lea     rax, [rsp+770h+cbData]
0x1800773c5  mov     dword ptr [rsp+770h+lpcbData], r15d; int
0x1800773ca  lea     r9, [rsp+770h+var_730]
0x1800773cf  lea     r8, [rsp+770h+var_700]
0x1800773d4  mov     [rsp+770h+lpData], rax; __int64
0x1800773d9  lea     rdx, aPsharename; "pShareName"
0x1800773e0  mov     rcx, rbx; void *
0x1800773e3  call    RegGetString
0x1800773e8  lea     rax, [rsp+770h+cbData]
0x1800773ed  mov     [rsp+770h+var_740], rdi; struct _INISPOOLER *
0x1800773f2  mov     dword ptr [rsp+770h+lpcbData], r15d; int
0x1800773f7  lea     r9, [rsp+770h+var_730]
0x1800773fc  lea     r8, [rbp+670h+var_6E8]
0x180077400  mov     [rsp+770h+lpData], rax; __int64
0x180077405  lea     rdx, aPcomment; "pComment"
0x18007740c  mov     rcx, rbx; void *
0x18007740f  call    RegGetString
0x180077414  lea     rax, [rsp+770h+cbData]
0x180077419  mov     [rsp+770h+var_740], rdi; struct _INISPOOLER *
0x18007741e  mov     dword ptr [rsp+770h+lpcbData], r15d; int
0x180077423  lea     r9, [rsp+770h+var_730]
0x180077428  lea     r8, [rbp+670h+var_6E0]
0x18007742c  mov     [rsp+770h+lpData], rax; __int64
0x180077431  lea     rdx, aPlocation; "pLocation"
0x180077438  mov     rcx, rbx; void *
0x18007743b  call    RegGetString
0x180077440  lea     rax, [rsp+770h+cbData]
0x180077445  mov     [rsp+770h+var_740], rdi; struct _INISPOOLER *
0x18007744a  mov     dword ptr [rsp+770h+lpcbData], r15d; int
0x18007744f  lea     r9, [rsp+770h+var_730]
0x180077454  lea     r8, [rbp+670h+var_6D0]
0x180077458  mov     [rsp+770h+lpData], rax; __int64
0x18007745d  lea     rdx, aPsepfile; "pSepFile"
0x180077464  mov     rcx, rbx; void *
0x180077467  call    RegGetString
0x18007746c  lea     rax, [rsp+770h+cbData]
0x180077471  mov     [rsp+770h+var_740], rdi; struct _INISPOOLER *
0x180077476  mov     dword ptr [rsp+770h+lpcbData], r15d; int
0x18007747b  lea     r9, [rsp+770h+var_730]
0x180077480  lea     r8, [rbp+670h+var_6C0]
0x180077484  mov     [rsp+770h+lpData], rax; __int64
0x180077489  lea     rdx, aPdatatype; "pDatatype"
0x180077490  mov     rcx, rbx; void *
0x180077493  call    RegGetString
0x180077498  lea     rax, [rsp+770h+cbData]
0x18007749d  mov     [rsp+770h+var_740], rdi; struct _INISPOOLER *
0x1800774a2  mov     dword ptr [rsp+770h+lpcbData], r15d; int
0x1800774a7  lea     r9, [rsp+770h+var_730]
0x1800774ac  lea     r8, [rbp+670h+var_6B8]
0x1800774b0  mov     [rsp+770h+lpData], rax; __int64
0x1800774b5  lea     rdx, aPparameters; "pParameters"
0x1800774bc  mov     rcx, rbx; void *
0x1800774bf  call    RegGetString
0x1800774c4  lea     rax, [rsp+770h+var_728]
0x1800774c9  mov     [rsp+770h+lpcbData], rdi; struct _INISPOOLER *
0x1800774ce  lea     esi, [r15+4]
0x1800774d2  mov     [rsp+770h+lpData], rax; unsigned int *
0x1800774d7  lea     r9, [rbp+670h+var_6A8]; unsigned __int8 *
0x1800774db  mov     [rsp+770h+var_728], esi
0x1800774df  lea     r8, [rsp+770h+var_724]; unsigned int *
0x1800774e4  mov     rcx, rbx; void *
0x1800774e7  lea     rdx, szAttributes; "Attributes"
0x1800774ee  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x1800774f3  lea     rax, [rsp+770h+var_728]
0x1800774f8  mov     [rsp+770h+lpcbData], rdi; struct _INISPOOLER *
0x1800774fd  lea     r9, [rbp+670h+var_6A4]; unsigned __int8 *
0x180077501  mov     [rsp+770h+lpData], rax; unsigned int *
0x180077506  lea     r8, [rsp+770h+var_724]; unsigned int *
0x18007750b  mov     [rsp+770h+var_728], esi
0x18007750f  lea     rdx, szPriority; "Priority"
0x180077516  mov     rcx, rbx; void *
0x180077519  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18007751e  lea     rax, [rsp+770h+var_728]
0x180077523  mov     [rsp+770h+lpcbData], rdi; struct _INISPOOLER *
0x180077528  mov     [rsp+770h+lpData], rax; unsigned int *
0x18007752d  lea     r9, [rbp+670h+var_6A0]; unsigned __int8 *
0x180077531  mov     [rsp+770h+var_728], esi
0x180077535  lea     r8, [rsp+770h+var_724]; unsigned int *
0x18007753a  lea     rdx, szDefaultPriority; "Default Priority"
0x180077541  mov     rcx, rbx; void *
0x180077544  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x180077549  lea     rax, [rsp+770h+var_728]
0x18007754e  mov     [rsp+770h+lpcbData], rdi; struct _INISPOOLER *
0x180077553  lea     r9, [rbp+670h+var_69C]; unsigned __int8 *
0x180077557  mov     [rsp+770h+lpData], rax; unsigned int *
0x18007755c  lea     r8, [rsp+770h+var_724]; unsigned int *
0x180077561  mov     [rsp+770h+var_728], esi
0x180077565  lea     rdx, szStartTime; "StartTime"
0x18007756c  mov     rcx, rbx; void *
0x18007756f  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x180077574  lea     rax, [rsp+770h+var_728]
0x180077579  mov     [rsp+770h+lpcbData], rdi; struct _INISPOOLER *
0x18007757e  lea     r9, [rbp+670h+var_698]; unsigned __int8 *
0x180077582  mov     [rsp+770h+lpData], rax; unsigned int *
0x180077587  lea     r8, [rsp+770h+var_724]; unsigned int *
0x18007758c  mov     [rsp+770h+var_728], esi
0x180077590  lea     rdx, szUntilTime; "UntilTime"
0x180077597  mov     rcx, rbx; void *
0x18007759a  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18007759f  cmp     [rsp+770h+var_708], r15
0x1800775a4  jz      loc_1800778C0
0x1800775aa  cmp     [rsp+770h+var_6F8], r15
0x1800775af  jz      loc_1800778C0
0x1800775b5  cmp     [rbp+670h+lpString1], r15
0x1800775b9  jz      loc_1800778C0
0x1800775bf  cmp     [rbp+670h+var_6C8], r15
0x1800775c3  jz      loc_1800778C0
0x1800775c9  mov     esi, 208h
0x1800775ce  lea     rcx, [rbp+670h+Data]; void *
0x1800775d5  mov     r8d, esi; Size
0x1800775d8  xor     edx, edx; Val
0x1800775da  call    memset_0
0x1800775df  lea     rax, [rsp+770h+cbData]
0x1800775e4  mov     [rsp+770h+Type], r15d
0x1800775e9  mov     [rsp+770h+lpcbData], rax; lpcbData
0x1800775ee  lea     r9, [rsp+770h+Type]; lpType
0x1800775f3  lea     rax, [rbp+670h+Data]
0x1800775fa  mov     [rsp+770h+cbData], esi
0x1800775fe  xor     r8d, r8d; lpReserved
0x180077601  mov     [rsp+770h+lpData], rax; lpData
0x180077606  lea     rdx, aInfpath_0; "InfPath"
0x18007760d  mov     rcx, rbx; hKey
0x180077610  call    cs:__imp_RegQueryValueExW
0x180077616  test    eax, eax
0x180077618  jnz     loc_180077734
0x18007761e  mov     r8d, esi; Size
0x180077621  lea     rcx, [rbp+670h+Dst]; void *
0x180077625  xor     edx, edx; Val
0x180077627  call    memset_0
0x18007762c  mov     r14d, 104h
0x180077632  lea     rdx, [rbp+670h+Dst]; lpDst
0x180077636  mov     r8d, r14d; nSize
0x180077639  lea     rcx, [rbp+670h+Data]; lpSrc
0x180077640  call    cs:__imp_ExpandEnvironmentStringsW
0x180077646  test    eax, eax
0x180077648  jz      loc_180077723
0x18007764e  lea     rcx, [rbp+670h+Dst]
0x180077652  call    IsInInfDir
0x180077657  lea     rbx, aWindowsX64_0; "Windows x64"
0x18007765e  test    eax, eax
0x180077660  jnz     loc_180077705
0x180077666  mov     r8d, esi; Size
0x180077669  lea     rcx, [rbp+670h+var_450]; void *
0x180077670  xor     edx, edx; Val
0x180077672  call    memset_0
0x180077677  mov     [rsp+770h+var_730], r14d
0x18007767c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180077683  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180077688  test    al, al
0x18007768a  jz      short loc_1800776BE
0x18007768c  mov     rdx, [rsp+770h+var_708]
0x180077691  lea     rcx, g_szMpdw; "Microsoft Print To PDF"
0x180077698  call    cs:__imp__o__wcsicmp
0x18007769e  test    eax, eax
0x1800776a0  jnz     short loc_1800776BE
0x1800776a2  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x1800776a7  test    eax, eax
0x1800776a9  jz      short loc_1800776BE
0x1800776ab  lea     rdx, [rsp+770h+var_730]; unsigned int *
0x1800776b0  lea     rcx, [rbp+670h+var_450]; unsigned __int16 *
0x1800776b7  call    ?InstallPrintToPDFDriverViaBroker@@YAJPEAGPEAK@Z; InstallPrintToPDFDriverViaBroker(ushort *,ulong *)
0x1800776bc  jmp     short loc_1800776EA
0x1800776be  lea     rax, [rsp+770h+var_730]
0x1800776c3  mov     [rsp+770h+var_740], rdi; __int64
0x1800776c8  mov     [rsp+770h+lpcbData], rax; __int64
0x1800776cd  lea     rdx, [rbp+670h+Dst]; unsigned __int16 *
0x1800776d1  lea     rax, [rbp+670h+var_450]
0x1800776d8  xor     r9d, r9d
0x1800776db  mov     r8, rbx; unsigned __int16 *
0x1800776de  mov     [rsp+770h+lpData], rax; unsigned __int16 *
0x1800776e3  xor     ecx, ecx; unsigned __int16 *
0x1800776e5  call    SplUploadPrinterDriverPackage
0x1800776ea  test    eax, eax
0x1800776ec  js      short loc_18007772C
0x1800776ee  lea     r8, [rbp+670h+var_450]; unsigned __int16 *
0x1800776f5  mov     rdx, r14; unsigned __int64
0x1800776f8  lea     rcx, [rbp+670h+Dst]; unsigned __int16 *
0x1800776fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180077701  test    eax, eax
0x180077703  js      short loc_18007772C
0x180077705  mov     r8, [rbp+670h+lpString1]; unsigned __int16 *
0x180077709  lea     rdx, [rbp+670h+Dst]; unsigned __int16 *
0x18007770d  mov     [rsp+770h+lpcbData], rdi; unsigned int
0x180077712  mov     r9, rbx; unsigned __int16 *
0x180077715  xor     ecx, ecx; this
0x180077717  mov     dword ptr [rsp+770h+lpData], r15d; int
0x18007771c  call    SplInstallPrinterDriverFromPackage
0x180077721  jmp     short loc_180077728
0x180077723  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x180077728  test    eax, eax
0x18007772a  jns     short loc_180077734
0x18007772c  movzx   edi, ax
0x18007772f  jmp     loc_1800778EF
0x180077734  mov     rcx, [rbp+670h+lpString1]; lpString1
0x180077738  lea     rdx, g_szMxdw; "Microsoft XPS Document Writer v4"
0x18007773f  call    cs:__imp_lstrcmpW
0x180077745  lea     rbx, aAddprinterforo; "AddPrinterForOfflinePrinteQueue"
0x18007774c  test    eax, eax
0x18007774e  jnz     loc_180077846
0x180077754  mov     rsi, [rdi+28h]
0x180077758  test    rsi, rsi
0x18007775b  jz      loc_180077846
0x180077761  mov     rcx, [rsi+58h]
0x180077765  lea     rdx, g_szMxdwV3; "Microsoft XPS Document Writer"
0x18007776c  mov     r14, [rsi+8]
0x180077770  mov     rcx, [rcx+18h]; lpString1
0x180077774  call    cs:__imp_lstrcmpW
0x18007777a  test    eax, eax
0x18007777c  jnz     loc_180077822
0x180077782  mov     r8, [rsi+18h]
0x180077786  lea     rdx, aFoundPrintQueu; "Found print queue %ws using  MXDW V3 dr"...
0x18007778d  mov     rcx, rbx; char *
0x180077790  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180077795  mov     rcx, [rsi+18h]; lpString1
0x180077799  lea     r8, [rbp+670h+var_680]
0x18007779d  xorps   xmm0, xmm0
0x1800777a0  mov     [rbp+670h+var_670], 0F000Ch
0x1800777a8  xor     r9d, r9d
0x1800777ab  mov     dword ptr [rsp+770h+lpData], r15d; int
0x1800777b0  lea     rdx, [rsp+770h+var_720]
0x1800777b5  movdqu  [rbp+670h+var_680], xmm0
0x1800777ba  call    LocalOpenPrinterEx
0x1800777bf  test    eax, eax
0x1800777c1  jz      short loc_1800777D7
0x1800777c3  mov     rcx, [rsp+770h+var_720]
0x1800777c8  call    SplDeletePrinter
0x1800777cd  mov     rcx, [rsp+770h+var_720]
0x1800777d2  call    SplClosePrinter
0x1800777d7  mov     rcx, [rsi+118h]
0x1800777de  xor     r9d, r9d
  ... truncated ...
```
