# InstallV4Driver

- ea: `0x1800340b4`
- end: `0x1800344a8`
- name: `InstallV4Driver`
- size: `1012`
- prototype: `__int64 __fastcall(struct _SETUP_CONTEXT *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180011c70`
- `0x180021020`
- `0x1800344b0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000b200`
- `0x18000d57c`
- `0x180017810`
- `0x180020b60`
- `0x180032a34`
- `0x180033398`
- `0x1800340b4`
- `0x180034a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003417b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003423a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003428a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003417b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003423a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003428a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800341af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800341af`
- `SETUPAPI!SetupScanFileQueueW` at `0x1800342ea`
- `SETUPAPI!SetupScanFileQueueW` at `0x1800342ea`
- `SETUPAPI!SetupDiGetActualSectionToInstallExW` at `0x180034168`
- `SETUPAPI!SetupDiGetActualSectionToInstallExW` at `0x180034227`
- `SETUPAPI!SetupDiGetActualSectionToInstallExW` at `0x180034168`
- `SETUPAPI!SetupDiGetActualSectionToInstallExW` at `0x180034227`
- `SETUPAPI!SetupInstallFilesFromInfSectionW` at `0x180034277`
- `SETUPAPI!SetupInstallFilesFromInfSectionW` at `0x180034277`
- `SETUPAPI!SetupCloseInfFile` at `0x180034479`
- `SETUPAPI!SetupCloseInfFile` at `0x180034479`

## string_xrefs

- `0x1800340f9`: `InstallV4Driver`
- `0x18003411f`: `Error opening INF: %d`
- `0x1800341d0`: `Couldn't allocate memory for pszInstallSection: %d`
- `0x180034185`: `Error retrieving size of install section name (pszDriverSection='%ws'): %d`
- `0x180034297`: `Error building file queue (pszInstallSection='%ws'): %d`
- `0x180034244`: `Error retrieving install section name (pszDriverSection='%ws'): %d`
- `0x180034321`: `Driver contains multiple manifests`
- `0x1800343bd`: `Driver does not contain a manifest`

## pseudocode

```c
__int64 __fastcall InstallV4Driver(struct _SETUP_CONTEXT *a1)
{
  __int64 v1; // rdi
  void *v3; // r15
  int v4; // ebx
  NCoreLibrary *v5; // rcx
  void *v6; // rsi
  DWORD LastError; // eax
  NCoreLibrary *v8; // rcx
  DWORD v9; // eax
  HLOCAL v10; // rax
  NCoreLibrary *v11; // rcx
  DWORD v12; // eax
  WCHAR *v13; // r9
  const WCHAR *v14; // rdx
  NCoreLibrary *v15; // rcx
  DWORD v16; // eax
  NCoreLibrary *v17; // rcx
  DWORD v18; // eax
  NCoreLibrary *v19; // rcx
  const unsigned __int16 *v20; // rdx
  struct SplLogType *v21; // rax
  __int64 v22; // r10
  const unsigned __int16 *v23; // rdx
  struct SplLogType *v24; // rax
  __int64 v25; // r10
  DWORD Result; // [rsp+40h] [rbp-C0h] BYREF
  DWORD RequiredSize; // [rsp+44h] [rbp-BCh] BYREF
  int v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h]
  int v34; // [rsp+70h] [rbp-90h]
  _BYTE v35[24]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v36[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE CallbackContext[528]; // [rsp+B0h] [rbp-50h] BYREF

  v1 = *((_QWORD *)a1 + 4);
  v3 = (void *)*((_QWORD *)a1 + 1);
  v4 = 0;
  v6 = (void *)OpenPrinterInfFile(*(unsigned __int16 **)v1);
  Result = 0;
  if ( v6 == (void *)-1LL )
  {
    Result = NCoreLibrary::GetLastErrorAsFailHR(v5);
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError("InstallV4Driver", L"Error opening INF: %d", LastError);
    v4 = Result;
  }
  RequiredSize = 0;
  if ( v4 >= 0 )
  {
    if ( !SetupDiGetActualSectionToInstallExW(v6, *(PCWSTR *)(v1 + 16), 0, 0, 0, &RequiredSize, 0, 0) )
    {
      Result = NCoreLibrary::GetLastErrorAsFailHR(v8);
      v9 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError(
        "InstallV4Driver",
        L"Error retrieving size of install section name (pszDriverSection='%ws'): %d",
        *(_QWORD *)(v1 + 16),
        v9);
    }
    v4 = Result;
    if ( (Result & 0x80000000) == 0 )
    {
      v10 = LocalAlloc(0x40u, 2 * RequiredSize);
      *(_QWORD *)(v1 + 184) = v10;
      if ( !v10 )
      {
        Result = NCoreLibrary::GetLastErrorAsFailHR(v11);
        v12 = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceError(
          "InstallV4Driver",
          L"Couldn't allocate memory for pszInstallSection: %d",
          v12);
      }
      v4 = Result;
      if ( (Result & 0x80000000) == 0 )
      {
        *(_DWORD *)(v1 + 164) |= 1u;
        v13 = *(WCHAR **)(v1 + 184);
        v14 = *(const WCHAR **)(v1 + 16);
        *(_DWORD *)(v1 + 172) = 1;
        if ( !SetupDiGetActualSectionToInstallExW(v6, v14, 0, v13, RequiredSize, 0, 0, 0) )
        {
          Result = NCoreLibrary::GetLastErrorAsFailHR(v15);
          v16 = GetLastError();
          ClassInstallerTelemetry::WriteDbgTraceError(
            "InstallV4Driver",
            L"Error retrieving install section name (pszDriverSection='%ws'): %d",
            *(_QWORD *)(v1 + 16),
            v16);
        }
        v4 = Result;
        if ( (Result & 0x80000000) == 0 )
        {
          if ( !SetupInstallFilesFromInfSectionW(v6, 0, v3, *(PCWSTR *)(v1 + 184), 0, 0) )
          {
            Result = NCoreLibrary::GetLastErrorAsFailHR(v17);
            v18 = GetLastError();
            ClassInstallerTelemetry::WriteDbgTraceError(
              "InstallV4Driver",
              L"Error building file queue (pszInstallSection='%ws'): %d",
              *(_QWORD *)(v1 + 184),
              v18);
          }
          v4 = Result;
        }
      }
    }
  }
  memset_0(CallbackContext, 0, 0x20Au);
  if ( v4 >= 0 )
  {
    if ( !SetupScanFileQueueW(v3, 9u, 0, CheckAndRetrieveManifest, CallbackContext, &Result) )
    {
      v4 = Result;
      if ( (Result & 0x80000000) == 0 )
      {
        Result = NCoreLibrary::GetLastErrorAsFailHR(v19);
        v4 = Result;
        if ( (Result & 0x80000000) == 0 )
        {
LABEL_24:
          if ( !CallbackContext[0] )
          {
            Result = -2147021875;
            ClassInstallerTelemetry::WriteDbgTraceError("InstallV4Driver", L"Driver does not contain a manifest");
            v23 = *(const unsigned __int16 **)v1;
            v32 = 0;
            v33 = 4;
            v30 = 4;
            v34 = 0;
            v29 = 1;
            v31 = 0;
            SplLogType::SplLogType((SplLogType *)v36, v23);
            v24 = SplLogType::SplLogType((SplLogType *)v35, *(const unsigned __int16 **)(v1 + 8));
            SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_INVALID_MANIFEST_COUNT, v24, v25, &v29, &v32, 0);
            v4 = Result;
          }
          if ( v4 >= 0 )
          {
            Result = ParseManifestDirectives(
                       (struct _PSETUP_LOCAL_DATA *)v1,
                       (struct _MANIFEST_CALLBACK_CONTEXT *)CallbackContext);
            v4 = Result;
            if ( (Result & 0x80000000) == 0 && !*((_BYTE *)a1 + 72) )
            {
              v4 = ProcessV4FileLists(a1, (struct _MANIFEST_CALLBACK_CONTEXT *)CallbackContext);
              Result = v4;
            }
          }
          goto LABEL_30;
        }
      }
      if ( v4 == -2147021875 )
      {
        ClassInstallerTelemetry::WriteDbgTraceError("InstallV4Driver", L"Driver contains multiple manifests");
        v20 = *(const unsigned __int16 **)v1;
        v29 = 1;
        v30 = 4;
        v33 = 4;
        v31 = 0;
        v32 = 0;
        v34 = 0;
        SplLogType::SplLogType((SplLogType *)v35, v20);
        v21 = SplLogType::SplLogType((SplLogType *)v36, *(const unsigned __int16 **)(v1 + 8));
        SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_INVALID_MANIFEST_COUNT, v21, v22, &v32, &v29, 0);
      }
      else
      {
        ClassInstallerTelemetry::WriteDbgTraceError(
          "InstallV4Driver",
          L"Error scanning file queue: hr: 0x%x",
          (unsigned int)v4);
      }
    }
    v4 = Result;
    if ( (Result & 0x80000000) != 0 )
      goto LABEL_30;
    goto LABEL_24;
  }
LABEL_30:
  if ( v6 != (void *)-1LL )
  {
    SetupCloseInfFile(v6);
    return Result;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800340b4  push    rbp
0x1800340b6  push    rbx
0x1800340b7  push    rsi
0x1800340b8  push    rdi
0x1800340b9  push    r12
0x1800340bb  push    r13
0x1800340bd  push    r14
0x1800340bf  push    r15
0x1800340c1  lea     rbp, [rsp-1D8h]
0x1800340c9  sub     rsp, 2D8h
0x1800340d0  mov     rax, cs:__security_cookie
0x1800340d7  xor     rax, rsp
0x1800340da  mov     [rbp+210h+var_50], rax
0x1800340e1  mov     rdi, [rcx+20h]
0x1800340e5  mov     r14, rcx
0x1800340e8  mov     r15, [rcx+8]
0x1800340ec  xor     edx, edx
0x1800340ee  mov     rcx, [rdi]; unsigned __int16 *
0x1800340f1  call    OpenPrinterInfFile
0x1800340f6  xor     r12d, r12d
0x1800340f9  lea     r13, aInstallv4drive; "InstallV4Driver"
0x180034100  mov     ebx, r12d
0x180034103  mov     rsi, rax
0x180034106  mov     [rsp+310h+Result], ebx
0x18003410a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003410e  jnz     short loc_180034135
0x180034110  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180034115  mov     [rsp+310h+Result], eax
0x180034119  call    cs:__imp_GetLastError
0x18003411f  lea     rdx, aErrorOpeningIn_0; "Error opening INF: %d"
0x180034126  mov     rcx, r13; char *
0x180034129  mov     r8d, eax
0x18003412c  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180034131  mov     ebx, [rsp+310h+Result]
0x180034135  mov     [rsp+310h+var_2CC], r12d
0x18003413a  test    ebx, ebx
0x18003413c  js      loc_1800342AD
0x180034142  mov     rdx, [rdi+10h]; InfSectionName
0x180034146  lea     rax, [rsp+310h+var_2CC]
0x18003414b  mov     [rsp+310h+Reserved], r12; Reserved
0x180034150  xor     r9d, r9d; InfSectionWithExt
0x180034153  mov     [rsp+310h+Extension], r12; Extension
0x180034158  xor     r8d, r8d; AlternatePlatformInfo
0x18003415b  mov     [rsp+310h+RequiredSize], rax; RequiredSize
0x180034160  mov     rcx, rsi; InfHandle
0x180034163  mov     [rsp+310h+InfSectionWithExtSize], r12d; InfSectionWithExtSize
0x180034168  call    cs:__imp_SetupDiGetActualSectionToInstallExW
0x18003416e  test    eax, eax
0x180034170  jnz     short loc_180034197
0x180034172  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180034177  mov     [rsp+310h+Result], eax
0x18003417b  call    cs:__imp_GetLastError
0x180034181  mov     r8, [rdi+10h]
0x180034185  lea     rdx, aErrorRetrievin_10; "Error retrieving size of install sectio"...
0x18003418c  mov     r9d, eax
0x18003418f  mov     rcx, r13; char *
0x180034192  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180034197  mov     ebx, [rsp+310h+Result]
0x18003419b  test    ebx, ebx
0x18003419d  js      loc_1800342AD
0x1800341a3  mov     eax, [rsp+310h+var_2CC]
0x1800341a7  mov     ecx, 40h ; '@'; uFlags
0x1800341ac  lea     edx, [rax+rax]; uBytes
0x1800341af  call    cs:__imp_LocalAlloc
0x1800341b5  mov     [rdi+0B8h], rax
0x1800341bc  test    rax, rax
0x1800341bf  jnz     short loc_1800341E2
0x1800341c1  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800341c6  mov     [rsp+310h+Result], eax
0x1800341ca  call    cs:__imp_GetLastError
0x1800341d0  lea     rdx, aCouldnTAllocat; "Couldn't allocate memory for pszInstall"...
0x1800341d7  mov     rcx, r13; char *
0x1800341da  mov     r8d, eax
0x1800341dd  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800341e2  mov     ebx, [rsp+310h+Result]
0x1800341e6  test    ebx, ebx
0x1800341e8  js      loc_1800342AD
0x1800341ee  or      dword ptr [rdi+0A4h], 1
0x1800341f5  xor     r8d, r8d; AlternatePlatformInfo
0x1800341f8  mov     r9, [rdi+0B8h]; InfSectionWithExt
0x1800341ff  mov     rcx, rsi; InfHandle
0x180034202  mov     rdx, [rdi+10h]; InfSectionName
0x180034206  mov     [rsp+310h+Reserved], r12; Reserved
0x18003420b  mov     [rsp+310h+Extension], r12; Extension
0x180034210  mov     dword ptr [rdi+0ACh], 1
0x18003421a  mov     eax, [rsp+310h+var_2CC]
0x18003421e  mov     [rsp+310h+RequiredSize], r12; RequiredSize
0x180034223  mov     [rsp+310h+InfSectionWithExtSize], eax; InfSectionWithExtSize
0x180034227  call    cs:__imp_SetupDiGetActualSectionToInstallExW
0x18003422d  test    eax, eax
0x18003422f  jnz     short loc_180034256
0x180034231  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180034236  mov     [rsp+310h+Result], eax
0x18003423a  call    cs:__imp_GetLastError
0x180034240  mov     r8, [rdi+10h]
0x180034244  lea     rdx, aErrorRetrievin_1; "Error retrieving install section name ("...
0x18003424b  mov     r9d, eax
0x18003424e  mov     rcx, r13; char *
0x180034251  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180034256  mov     ebx, [rsp+310h+Result]
0x18003425a  test    ebx, ebx
0x18003425c  js      short loc_1800342AD
0x18003425e  mov     r9, [rdi+0B8h]; SectionName
0x180034265  mov     r8, r15; FileQueue
0x180034268  mov     dword ptr [rsp+310h+RequiredSize], r12d; CopyFlags
0x18003426d  xor     edx, edx; LayoutInfHandle
0x18003426f  mov     rcx, rsi; InfHandle
0x180034272  mov     qword ptr [rsp+310h+InfSectionWithExtSize], r12; SourceRootPath
0x180034277  call    cs:__imp_SetupInstallFilesFromInfSectionW
0x18003427d  test    eax, eax
0x18003427f  jnz     short loc_1800342A9
0x180034281  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180034286  mov     [rsp+310h+Result], eax
0x18003428a  call    cs:__imp_GetLastError
0x180034290  mov     r8, [rdi+0B8h]
0x180034297  lea     rdx, aErrorBuildingF; "Error building file queue (pszInstallSe"...
0x18003429e  mov     r9d, eax
0x1800342a1  mov     rcx, r13; char *
0x1800342a4  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800342a9  mov     ebx, [rsp+310h+Result]
0x1800342ad  xor     edx, edx; Val
0x1800342af  lea     rcx, [rbp+210h+CallbackContext]; void *
0x1800342b3  mov     r8d, 20Ah; Size
0x1800342b9  call    memset_0
0x1800342be  test    ebx, ebx
0x1800342c0  js      loc_180034470
0x1800342c6  xor     r8d, r8d; Window
0x1800342c9  lea     rax, [rsp+310h+Result]
0x1800342ce  mov     [rsp+310h+RequiredSize], rax; Result
0x1800342d3  lea     r9, ?CheckAndRetrieveManifest@@YAIPEAXI_K1@Z; CallbackRoutine
0x1800342da  lea     rax, [rbp+210h+CallbackContext]
0x1800342de  mov     rcx, r15; FileQueue
0x1800342e1  mov     qword ptr [rsp+310h+InfSectionWithExtSize], rax; CallbackContext
0x1800342e6  lea     edx, [r8+9]; Flags
0x1800342ea  call    cs:__imp_SetupScanFileQueueW
0x1800342f0  mov     r15d, 80070BCDh
0x1800342f6  test    eax, eax
0x1800342f8  jnz     loc_1800343A7
0x1800342fe  mov     ebx, [rsp+310h+Result]
0x180034302  test    ebx, ebx
0x180034304  js      short loc_180034319
0x180034306  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18003430b  mov     [rsp+310h+Result], eax
0x18003430f  mov     ebx, eax
0x180034311  test    eax, eax
0x180034313  jns     loc_1800343B3
0x180034319  mov     rcx, r13; char *
0x18003431c  cmp     ebx, r15d
0x18003431f  jnz     short loc_180034398
0x180034321  lea     rdx, aDriverContains; "Driver contains multiple manifests"
0x180034328  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003432d  mov     rdx, [rdi]; unsigned __int16 *
0x180034330  lea     rcx, [rsp+310h+var_298]; this
0x180034335  mov     eax, 4
0x18003433a  mov     [rsp+310h+var_2C8], 1
0x180034342  mov     [rsp+310h+var_2C0], rax
0x180034347  mov     [rsp+310h+var_2A8], rax
0x18003434c  mov     [rsp+310h+var_2B8], r12d
0x180034351  mov     [rsp+310h+var_2B0], r12d
0x180034356  mov     [rsp+310h+var_2A0], r12d
0x18003435b  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180034360  mov     rdx, [rdi+8]; unsigned __int16 *
0x180034364  lea     rcx, [rbp+210h+var_280]; this
0x180034368  mov     r10, rax
0x18003436b  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180034370  lea     rcx, [rsp+310h+var_2C8]
0x180034375  mov     [rsp+310h+RequiredSize], r12
0x18003437a  mov     qword ptr [rsp+310h+InfSectionWithExtSize], rcx
0x18003437f  lea     r9, [rsp+310h+var_2B0]
0x180034384  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_INVALID_MANIFEST_COUNT; struct _EVENT_DESCRIPTOR *
0x18003438b  mov     r8, r10
0x18003438e  mov     rdx, rax; struct SplLogType *
0x180034391  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180034396  jmp     short loc_1800343A7
0x180034398  mov     r8d, ebx
0x18003439b  lea     rdx, aErrorScanningF; "Error scanning file queue: hr: 0x%x"
0x1800343a2  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800343a7  mov     ebx, [rsp+310h+Result]
0x1800343ab  test    ebx, ebx
0x1800343ad  js      loc_180034470
0x1800343b3  cmp     [rbp+210h+CallbackContext], r12b
0x1800343b7  jnz     loc_18003443E
0x1800343bd  lea     rdx, aDriverDoesNotC; "Driver does not contain a manifest"
0x1800343c4  mov     [rsp+310h+Result], r15d
0x1800343c9  mov     rcx, r13; char *
0x1800343cc  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800343d1  mov     rdx, [rdi]; unsigned __int16 *
0x1800343d4  lea     rcx, [rbp+210h+var_280]; this
0x1800343d8  mov     eax, 4
0x1800343dd  mov     [rsp+310h+var_2B0], r12d
0x1800343e2  mov     [rsp+310h+var_2A8], rax
0x1800343e7  mov     [rsp+310h+var_2C0], rax
0x1800343ec  mov     [rsp+310h+var_2A0], r12d
0x1800343f1  mov     [rsp+310h+var_2C8], 1
0x1800343f9  mov     [rsp+310h+var_2B8], r12d
0x1800343fe  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180034403  mov     rdx, [rdi+8]; unsigned __int16 *
0x180034407  lea     rcx, [rsp+310h+var_298]; this
0x18003440c  mov     r10, rax
0x18003440f  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180034414  lea     rdx, [rsp+310h+var_2B0]
0x180034419  mov     [rsp+310h+RequiredSize], r12
0x18003441e  mov     qword ptr [rsp+310h+InfSectionWithExtSize], rdx
0x180034423  lea     r9, [rsp+310h+var_2C8]
0x180034428  mov     rdx, rax; struct SplLogType *
0x18003442b  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_INVALID_MANIFEST_COUNT; struct _EVENT_DESCRIPTOR *
0x180034432  mov     r8, r10
0x180034435  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x18003443a  mov     ebx, [rsp+310h+Result]
0x18003443e  test    ebx, ebx
0x180034440  js      short loc_180034470
0x180034442  lea     rdx, [rbp+210h+CallbackContext]; struct _MANIFEST_CALLBACK_CONTEXT *
0x180034446  mov     rcx, rdi; struct _PSETUP_LOCAL_DATA *
0x180034449  call    ?ParseManifestDirectives@@YAJPEAU_PSETUP_LOCAL_DATA@@PEAU_MANIFEST_CALLBACK_CONTEXT@@@Z; ParseManifestDirectives(_PSETUP_LOCAL_DATA *,_MANIFEST_CALLBACK_CONTEXT *)
0x18003444e  mov     [rsp+310h+Result], eax
0x180034452  mov     ebx, eax
0x180034454  test    eax, eax
0x180034456  js      short loc_180034470
0x180034458  cmp     [r14+48h], r12b
0x18003445c  jnz     short loc_180034470
0x18003445e  lea     rdx, [rbp+210h+CallbackContext]; struct _MANIFEST_CALLBACK_CONTEXT *
0x180034462  mov     rcx, r14; struct _SETUP_CONTEXT *
0x180034465  call    ?ProcessV4FileLists@@YAJPEAU_SETUP_CONTEXT@@PEAU_MANIFEST_CALLBACK_CONTEXT@@@Z; ProcessV4FileLists(_SETUP_CONTEXT *,_MANIFEST_CALLBACK_CONTEXT *)
0x18003446a  mov     ebx, eax
0x18003446c  mov     [rsp+310h+Result], eax
0x180034470  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180034474  jz      short loc_180034483
0x180034476  mov     rcx, rsi; InfHandle
0x180034479  call    cs:__imp_SetupCloseInfFile
0x18003447f  mov     ebx, [rsp+310h+Result]
0x180034483  mov     eax, ebx
0x180034485  mov     rcx, [rbp+210h+var_50]
0x18003448c  xor     rcx, rsp; StackCookie
0x18003448f  call    __security_check_cookie
0x180034494  add     rsp, 2D8h
0x18003449b  pop     r15
0x18003449d  pop     r14
0x18003449f  pop     r13
0x1800344a1  pop     r12
0x1800344a3  pop     rdi
0x1800344a4  pop     rsi
0x1800344a5  pop     rbx
0x1800344a6  pop     rbp
0x1800344a7  retn
```
