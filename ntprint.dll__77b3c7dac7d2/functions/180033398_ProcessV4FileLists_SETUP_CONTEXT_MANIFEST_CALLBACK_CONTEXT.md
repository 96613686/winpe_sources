# ProcessV4FileLists(_SETUP_CONTEXT *,_MANIFEST_CALLBACK_CONTEXT *)

- ea: `0x180033398`
- end: `0x180033d4d`
- name: `?ProcessV4FileLists@@YAJPEAU_SETUP_CONTEXT@@PEAU_MANIFEST_CALLBACK_CONTEXT@@@Z`
- size: `2485`
- prototype: `__int64 __fastcall(struct _SETUP_CONTEXT *, struct _MANIFEST_CALLBACK_CONTEXT *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800340b4`

## callees

- `0x180002300`
- `0x1800026f0`
- `0x180007944`
- `0x18000b200`
- `0x18000d290`
- `0x18000d57c`
- `0x18000d624`
- `0x180017810`
- `0x18001bc44`
- `0x18001c914`
- `0x180026498`
- `0x180031a74`
- `0x180031e68`
- `0x180032210`
- `0x1800324ac`
- `0x18003325c`
- `0x180033398`
- `0x180033d80`
- `0x180033dc4`
- `0x180033ebc`
- `0x180034a60`
- `0x180035bd4`
- `0x180035cb4`
- `0x180035cf0`
- `0x180039044`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180033983`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003399b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800339e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180033983`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003399b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800339e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033cef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033921`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033a74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033ac3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033921`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033a74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033ac3`
- `SETUPAPI!SetupScanFileQueueW` at `0x180033695`
- `SETUPAPI!SetupScanFileQueueW` at `0x180033c04`
- `SETUPAPI!SetupScanFileQueueW` at `0x180033695`
- `SETUPAPI!SetupScanFileQueueW` at `0x180033c04`
- `SETUPAPI!SetupOpenFileQueue` at `0x180033b7b`
- `SETUPAPI!SetupOpenFileQueue` at `0x180033b7b`
- `SETUPAPI!SetupCommitFileQueueW` at `0x180033c83`
- `SETUPAPI!SetupCommitFileQueueW` at `0x180033c83`
- `SETUPAPI!SetupCloseFileQueue` at `0x180033cc0`
- `SETUPAPI!SetupCloseFileQueue` at `0x180033cc0`
- `SETUPAPI!SetupDefaultQueueCallbackW` at `0x180033c74`
- `mscms!GetColorDirectoryW` at `0x180033620`
- `mscms!GetColorDirectoryW` at `0x180033620`

## string_xrefs

- `0x180033877`: `PrinterExtension`
- `0x1800334c6`: `Could not retrieve filename part of INF path`
- `0x18003364a`: `Error retrieving color directory: %d`
- `0x1800336e3`: `DataFile specified in manifest does not exist in file queue`
- `0x18003397c`: `pscript5.dll`
- `0x180033853`: `Printer extension '%ws' specified in manifest does not exist in file queue`
- `0x180033994`: `unidrv.dll`
- `0x180033b9d`: `Error creating file queue for copying color profiles: %d`
- `0x180033c9f`: `Error while copying color profiles to system color directory: %d`
- `0x1800339d7`: `application/vnd.ms-PrintDeviceCapabilities+xml`

## pseudocode

```c
__int64 __fastcall ProcessV4FileLists(struct _SETUP_CONTEXT *a1, struct _MANIFEST_CALLBACK_CONTEXT *a2)
{
  void *v2; // r13
  struct _MANIFEST_CALLBACK_CONTEXT *v3; // r12
  __int64 v4; // r15
  _DWORD *v5; // rax
  _DWORD *v6; // rsi
  _DWORD *v7; // rax
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rax
  signed int v10; // ecx
  signed int LastErrorAsFailHR; // ebx
  signed int StringFromManifest; // eax
  SplLogType *v13; // rbx
  struct SplLogType *v14; // rax
  __int64 v15; // r10
  __int64 v16; // r11
  struct _FILELIST_CALLBACK_CONTEXT *v17; // rcx
  _DWORD *v18; // r14
  signed int v19; // eax
  NCoreLibrary *v20; // rcx
  DWORD LastError; // eax
  void *CallbackContext; // rax
  NCoreLibrary *v23; // rcx
  SplLogType *v24; // rdi
  SplLogType *v25; // rbx
  struct SplLogType *v26; // rax
  __int64 v27; // r10
  __int64 v28; // r11
  _DWORD *v29; // r13
  __int64 v30; // r14
  NCoreLibrary *v31; // rdi
  NCoreLibrary::TString *v32; // rcx
  SplLogType *v33; // rdi
  SplLogType *v34; // rbx
  struct SplLogType *v35; // rax
  __int64 v36; // r10
  __int64 v37; // r11
  SIZE_T v38; // rbx
  HLOCAL v39; // rax
  NCoreLibrary *v40; // rcx
  __int64 v41; // rcx
  unsigned int v42; // edx
  int v43; // r8d
  unsigned int v44; // eax
  int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // eax
  int v48; // eax
  HLOCAL v49; // rax
  NCoreLibrary *v50; // rcx
  DWORD v51; // eax
  HLOCAL v52; // rax
  NCoreLibrary *v53; // rcx
  DWORD v54; // eax
  HSPFILEQ v55; // rax
  NCoreLibrary *v56; // rcx
  DWORD v57; // eax
  HSPFILEQ v58; // rcx
  NCoreLibrary *v59; // rcx
  HSPFILEQ *v60; // rdx
  NCoreLibrary *v61; // rcx
  DWORD v62; // eax
  void *v63; // rcx
  __int64 v64; // rax
  DWORD v65; // eax
  DWORD Result; // [rsp+40h] [rbp-C0h] BYREF
  struct _MANIFEST_CALLBACK_CONTEXT *v68; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwSize; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v70; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v71; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v72; // [rsp+68h] [rbp-98h]
  int v73; // [rsp+70h] [rbp-90h]
  HSPFILEQ FileQueue; // [rsp+78h] [rbp-88h]
  struct _SETUP_CONTEXT *v75; // [rsp+80h] [rbp-80h]
  _BYTE v76[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v77[24]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v78[24]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v79[24]; // [rsp+D0h] [rbp-30h] BYREF
  char v80[24]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 v81[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR ReturnedString[264]; // [rsp+310h] [rbp+210h] BYREF

  v2 = (void *)*((_QWORD *)a1 + 1);
  v3 = a2;
  v4 = *((_QWORD *)a1 + 4);
  v68 = a2;
  v75 = a1;
  Result = 0;
  FileQueue = v2;
  v5 = operator new(0x890u, (const struct std::nothrow_t *)&NCoreLibrary::nothrow);
  v6 = v5;
  if ( v5 )
  {
    *v5 = 1953721460;
    v7 = v5 + 2;
    v6[10] = 0;
    *(_QWORD *)(v6 + 11) = 0;
    v6[13] = 0;
    *((_QWORD *)v6 + 7) = 0;
    v7[2] = 1802398836;
    *(_QWORD *)v7 = &NCoreLibrary::TLink::`vftable';
    *((_QWORD *)v7 + 2) = v7;
    *((_QWORD *)v7 + 3) = v7;
    *((_QWORD *)v6 + 8) = 0;
    v6[18] = 0;
    *((_QWORD *)v6 + 10) = 0;
    *((_QWORD *)v6 + 11) = 0;
    *((_QWORD *)v6 + 12) = 0;
    *((_QWORD *)v6 + 13) = 0;
    *((_WORD *)v6 + 56) = 0;
    *((_WORD *)v6 + 316) = 0;
    *((_WORD *)v6 + 576) = 0;
    *((_WORD *)v6 + 836) = 0;
  }
  else
  {
    v6 = 0;
  }
  v70 = 0;
  NCoreLibrary::TGenericSP<_FILELIST_CALLBACK_CONTEXT,NCoreLibrary::TAutoPtr<_FILELIST_CALLBACK_CONTEXT>,_FILELIST_CALLBACK_CONTEXT *,0,_FILELIST_CALLBACK_CONTEXT const *>::Reset(&v70);
  v70 = v6;
  if ( v6 )
  {
    *((_QWORD *)v6 + 13) = v4 + 168;
    *((_QWORD *)v6 + 12) = v4;
    v9 = FileNamePart(*(wchar_t **)v4);
    v10 = Result;
  }
  else
  {
    v10 = -2147024882;
    v9 = 0;
    Result = -2147024882;
  }
  if ( v10 >= 0 && v9 )
  {
    *((_QWORD *)v6 + 11) = (v9 - *(_QWORD *)v4) >> 1;
  }
  else
  {
    Result = -2147418113;
    ClassInstallerTelemetry::WriteDbgTraceError("ProcessV4FileLists", L"Could not retrieve filename part of INF path");
  }
  LastErrorAsFailHR = Result;
  if ( (Result & 0x80000000) == 0 )
  {
    StringFromManifest = GetStringFromManifest(L"DataFile", (LPWSTR)v6 + 316, 0x104u, (LPCWSTR)v3 + 1);
    Result = StringFromManifest;
    LastErrorAsFailHR = StringFromManifest;
    if ( StringFromManifest < 0 )
    {
      ClassInstallerTelemetry::WriteDbgTraceError(
        "ProcessV4FileLists",
        L"Error parsing DataFile directive: hr: 0x%x",
        (unsigned int)StringFromManifest);
      if ( Result == -2147024894 )
        Result = -2147021875;
      v72 = 4;
      v71 = L"-";
      v73 = 1;
      v13 = SplLogType::SplLogType((SplLogType *)v76, L"DataFile");
      SplLogType::SplLogType((SplLogType *)v77, *(const unsigned __int16 **)(v4 + 112));
      SplLogType::SplLogType((SplLogType *)v78, *(const unsigned __int16 **)v4);
      v14 = SplLogType::SplLogType((SplLogType *)v79, *(const unsigned __int16 **)(v4 + 8));
      SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_MISSING_DIRECTIVE, v14, v15, v16, v13, &v71, 0);
      LastErrorAsFailHR = Result;
    }
    if ( LastErrorAsFailHR >= 0 )
    {
      v17 = 0;
      if ( v6 )
        v17 = (struct _FILELIST_CALLBACK_CONTEXT *)v6;
      v18 = v6;
      v19 = ParseAppSection(v17, (const unsigned __int16 *)v3 + 1);
      Result = v19;
      LastErrorAsFailHR = v19;
      if ( v19 == -2147024894 )
      {
        Result = 0;
      }
      else if ( v19 < 0 )
      {
        goto LABEL_38;
      }
      pdwSize = 520;
      if ( GetColorDirectoryW(0, (PWSTR)v6 + 56, &pdwSize) )
      {
        v6[11] = (pdwSize - 1) >> 1;
      }
      else
      {
        Result = NCoreLibrary::GetLastErrorAsFailHR(v20);
        LastError = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceError(
          "ProcessV4FileLists",
          L"Error retrieving color directory: %d",
          LastError);
      }
      LastErrorAsFailHR = Result;
      if ( (Result & 0x80000000) == 0 )
      {
        if ( v6 )
          CallbackContext = v6;
        else
          CallbackContext = 0;
        if ( !SetupScanFileQueueW(v2, 9u, 0, BuildDriverDataFromFileQueue, CallbackContext, &Result) )
        {
          LastErrorAsFailHR = Result;
          if ( (Result & 0x80000000) == 0 )
          {
            Result = NCoreLibrary::GetLastErrorAsFailHR(v23);
            LastErrorAsFailHR = Result;
            if ( (Result & 0x80000000) == 0 )
              goto LABEL_34;
          }
          ClassInstallerTelemetry::WriteDbgTraceError(
            "ProcessV4FileLists",
            L"Error while getting data file and sizes from queue: hr: 0x%x",
            (unsigned int)LastErrorAsFailHR);
        }
        LastErrorAsFailHR = Result;
        if ( (Result & 0x80000000) == 0 )
        {
LABEL_34:
          if ( !*((_BYTE *)v6 + 40) )
          {
            Result = -2147024894;
            ClassInstallerTelemetry::WriteDbgTraceError(
              "ProcessV4FileLists",
              L"DataFile specified in manifest does not exist in file queue");
            v24 = SplLogType::SplLogType((SplLogType *)v79, (const unsigned __int16 *)v6 + 316);
            v25 = SplLogType::SplLogType((SplLogType *)v78, L"DataFile");
            SplLogType::SplLogType((SplLogType *)v77, *(const unsigned __int16 **)(v4 + 112));
            SplLogType::SplLogType((SplLogType *)v76, *(const unsigned __int16 **)v4);
            v26 = SplLogType::SplLogType((SplLogType *)&v71, *(const unsigned __int16 **)(v4 + 8));
            SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_MISSING_FILE, v26, v27, v28, v25, v24, 0);
            LastErrorAsFailHR = Result;
          }
          if ( LastErrorAsFailHR >= 0 )
          {
            LastErrorAsFailHR = StringCchCopyNW(
                                  v81,
                                  (unsigned __int64)v8,
                                  *(const unsigned __int16 **)v4,
                                  *((_QWORD *)v6 + 11));
            Result = LastErrorAsFailHR;
          }
        }
      }
LABEL_38:
      v3 = v68;
      goto LABEL_41;
    }
    v3 = v68;
  }
  v18 = v6;
LABEL_41:
  v29 = v18 + 2;
  v30 = 0;
  if ( LastErrorAsFailHR >= 0 )
  {
    LastErrorAsFailHR = v29 == 0 ? 0x80004005 : 0;
    Result = LastErrorAsFailHR;
  }
  LODWORD(v71) = 1920234349;
  v31 = (NCoreLibrary *)&NCoreLibrary::TMultiString::gszzEmpty;
  v72 = (__int64)&NCoreLibrary::TMultiString::gszzEmpty;
  v73 = 0;
  if ( v29 )
    v30 = *((_QWORD *)v29 + 2);
  if ( LastErrorAsFailHR >= 0 )
  {
    if ( v29 )
    {
      do
      {
        if ( (_DWORD *)v30 == v29 )
          break;
        if ( *(_BYTE *)(v30 + 64) )
        {
          v68 = (struct _MANIFEST_CALLBACK_CONTEXT *)&NCoreLibrary::TString::gszNullState;
          Result = TAppRegistration::ToString((TAppRegistration *)v30, v81, (struct TString *)&v68);
          if ( (Result & 0x80000000) == 0 )
            Result = NCoreLibrary::TMultiString::Cat((NCoreLibrary::TMultiString *)&v71, (const unsigned __int16 *)v68);
          NCoreLibrary::TString::vFree(v32, v68);
        }
        else
        {
          Result = -2147024894;
          ClassInstallerTelemetry::WriteDbgTraceError(
            "ProcessV4FileLists",
            L"Printer extension '%ws' specified in manifest does not exist in file queue",
            *(_QWORD *)(v30 + 72));
          v33 = SplLogType::SplLogType((SplLogType *)v79, *(const unsigned __int16 **)(v30 + 72));
          v34 = SplLogType::SplLogType((SplLogType *)v78, L"PrinterExtension");
          SplLogType::SplLogType((SplLogType *)v77, *(const unsigned __int16 **)(v4 + 112));
          SplLogType::SplLogType((SplLogType *)v76, *(const unsigned __int16 **)v4);
          v35 = SplLogType::SplLogType((SplLogType *)v80, *(const unsigned __int16 **)(v4 + 8));
          SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_MISSING_FILE, v35, v36, v37, v34, v33, 0);
        }
        if ( v30 )
          v30 = *(_QWORD *)(v30 + 16);
        LastErrorAsFailHR = Result;
      }
      while ( (Result & 0x80000000) == 0 );
      v31 = (NCoreLibrary *)v72;
    }
    if ( LastErrorAsFailHR >= 0 )
    {
      if ( *(_WORD *)v31 )
      {
        v38 = 2 * NCoreLibrary::MultiSzSize(v31, v8);
        v39 = LocalAlloc(0x40u, v38);
        *(_QWORD *)(v4 + 152) = v39;
        if ( v39 )
        {
          memcpy_0(v39, v31, (unsigned int)v38);
          LastErrorAsFailHR = Result;
        }
        else
        {
          LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v40);
          Result = LastErrorAsFailHR;
        }
      }
      if ( LastErrorAsFailHR >= 0 )
      {
        Result = PopulatePackagePaths((struct _FILELIST_CALLBACK_CONTEXT *)v6);
        LastErrorAsFailHR = Result;
        if ( (Result & 0x80000000) == 0 )
        {
          v41 = *(_QWORD *)(v4 + 288);
          if ( v41 )
          {
            if ( !(unsigned int)_o__wcsicmp(v41, L"pscript5.dll")
              || !(unsigned int)_o__wcsicmp(*(_QWORD *)(v4 + 288), L"unidrv.dll") )
            {
              *((_BYTE *)v6 + 42) = 1;
            }
            LastErrorAsFailHR = Result;
          }
          if ( LastErrorAsFailHR >= 0 )
          {
            if ( (int)GetStringFromManifest(L"DataFileType", ReturnedString, 0x104u, (LPCWSTR)v3 + 1) >= 0
              && !(unsigned int)_o__wcsicmp(ReturnedString, L"application/vnd.ms-PrintDeviceCapabilities+xml") )
            {
              *((_BYTE *)v6 + 43) = 1;
            }
            LastErrorAsFailHR = Result;
            if ( (Result & 0x80000000) == 0 )
            {
              Result = CheckRequiredFilesAndGetSize(v3, (struct _FILELIST_CALLBACK_CONTEXT *)v6);
              LastErrorAsFailHR = Result;
              if ( (Result & 0x80000000) == 0 )
              {
                v42 = v6[13];
                v43 = -1;
                if ( !v42 )
                  goto LABEL_79;
                v44 = v42 + 1;
                v45 = -1;
                if ( v42 + 1 >= v42 )
                  v45 = v42 + 1;
                LastErrorAsFailHR = v44 < v42 ? 0x80070216 : 0;
                v6[13] = v45;
                Result = LastErrorAsFailHR;
                if ( v44 >= v42 )
                {
LABEL_79:
                  v46 = v6[12];
                  v47 = v46 + 1;
                  if ( v46 + 1 >= v46 )
                    v43 = v46 + 1;
                  LastErrorAsFailHR = v47 < v46 ? 0x80070216 : 0;
                  v6[12] = v43;
                  Result = LastErrorAsFailHR;
                  if ( v47 >= v46 )
                  {
                    v48 = v6[13];
                    if ( v48 )
                    {
                      v49 = LocalAlloc(0x40u, (unsigned int)(2 * v48));
                      *(_QWORD *)(v4 + 192) = v49;
                      if ( !v49 )
                      {
                        Result = NCoreLibrary::GetLastErrorAsFailHR(v50);
                        v51 = GetLastError();
                        ClassInstallerTelemetry::WriteDbgTraceError(
                          "ProcessV4FileLists",
                          L"Couldn't allocate %u bytes of memory for pszzICMFiles: %d",
                          2LL * (unsigned int)v6[13],
                          v51);
                      }
                      LastErrorAsFailHR = Result;
                    }
                    if ( LastErrorAsFailHR >= 0 )
                    {
                      v52 = LocalAlloc(0x40u, (unsigned int)(2 * v6[12]));
                      *(_QWORD *)(v4 + 320) = v52;
                      if ( !v52 )
                      {
                        Result = NCoreLibrary::GetLastErrorAsFailHR(v53);
                        v54 = GetLastError();
                        ClassInstallerTelemetry::WriteDbgTraceError(
                          "ProcessV4FileLists",
                          L"Couldn't allocate %u bytes of memory for pDependentFiles: %d",
                          2LL * (unsigned int)v6[13],
                          v54);
                      }
                      LastErrorAsFailHR = Result;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v68 = 0;
  if ( LastErrorAsFailHR >= 0 )
  {
    Result = StringCchLengthW(
               (const unsigned __int16 *)v3 + *((_QWORD *)v6 + 11) + 1,
               0x7FFFFFFFu,
               (unsigned __int64 *)&v68);
    LastErrorAsFailHR = Result;
    if ( (Result & 0x80000000) == 0 )
    {
      Result = StringCchCopyW(
                 *(unsigned __int16 **)(v4 + 320),
                 (unsigned int)v6[12],
                 (const unsigned __int16 *)v3 + *((_QWORD *)v6 + 11) + 1);
      *((_QWORD *)v6 + 8) += (char *)v68 + 1;
      LastErrorAsFailHR = Result;
      if ( (Result & 0x80000000) == 0 )
      {
        if ( v6[13] )
        {
          v55 = SetupOpenFileQueue();
          *((_QWORD *)v6 + 7) = v55;
          if ( v55 == (HSPFILEQ)-1LL )
          {
            Result = NCoreLibrary::GetLastErrorAsFailHR(v56);
            v57 = GetLastError();
            ClassInstallerTelemetry::WriteDbgTraceError(
              "ProcessV4FileLists",
              L"Error creating file queue for copying color profiles: %d",
              v57);
          }
          LastErrorAsFailHR = Result;
        }
        if ( LastErrorAsFailHR >= 0 )
        {
          ClassInstallerTelemetry::WriteDbgTraceInfo(
            "ProcessV4FileLists",
            L"Size of pszzICMFiles: %u, pDependentFiles: %u",
            (unsigned int)v6[13],
            (unsigned int)v6[12]);
          v58 = FileQueue;
          *((_BYTE *)v6 + 40) = 0;
          v6[18] = 1;
          if ( !SetupScanFileQueueW(v58, 9u, 0, BuildDriverDataFromFileQueue, v6, &Result) )
          {
            LastErrorAsFailHR = Result;
            if ( (Result & 0x80000000) == 0 )
            {
              Result = NCoreLibrary::GetLastErrorAsFailHR(v59);
              LastErrorAsFailHR = Result;
              if ( (Result & 0x80000000) == 0 )
              {
LABEL_103:
                v60 = (HSPFILEQ *)v6;
                if ( *((_BYTE *)v6 + 41) )
                {
                  LastErrorAsFailHR = CopyRequiredFilesToList(
                                        v3,
                                        (struct _FILELIST_CALLBACK_CONTEXT *)v6,
                                        *(unsigned __int16 **)(v4 + 320));
                  Result = LastErrorAsFailHR;
                  v60 = (HSPFILEQ *)v6;
                }
                if ( LastErrorAsFailHR >= 0 && v6[13] )
                {
                  if ( !SetupCommitFileQueueW(0, v60[7], SetupDefaultQueueCallbackW, *((PVOID *)v75 + 2)) )
                  {
                    Result = NCoreLibrary::GetLastErrorAsFailHR(v61);
                    v62 = GetLastError();
                    ClassInstallerTelemetry::WriteDbgTraceError(
                      "ProcessV4FileLists",
                      L"Error while copying color profiles to system color directory: %d",
                      v62);
                  }
                  LastErrorAsFailHR = Result;
                }
                goto LABEL_110;
              }
            }
            ClassInstallerTelemetry::WriteDbgTraceError(
              "ProcessV4FileLists",
              L"Error while running second phase of BuildDriverDataFromQueue: hr: 0x%x",
              (unsigned int)LastErrorAsFailHR);
          }
          LastErrorAsFailHR = Result;
          if ( (Result & 0x80000000) != 0 )
            goto LABEL_110;
          goto LABEL_103;
        }
      }
    }
  }
LABEL_110:
  v63 = (void *)*((_QWORD *)v6 + 7);
  if ( v63 != (void *)-1LL )
  {
    SetupCloseFileQueue(v63);
    LastErrorAsFailHR = Result;
  }
  if ( LastErrorAsFailHR >= 0 )
  {
    v64 = AllocStr((unsigned __int16 *)v6 + 316);
    *(_QWORD *)(v4 + 296) = v64;
    if ( !v64 )
    {
      Result = NCoreLibrary::GetLastErrorAsFailHR((NCoreLibrary *)v63);
      v65 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError(
        "ProcessV4FileLists",
        L"Failed to allocate memory for storing DataFile: %d",
        v65);
    }
    LastErrorAsFailHR = Result;
  }
  NCoreLibrary::TMultiString::vFree((NCoreLibrary::TMultiString *)v63, v31);
  NCoreLibrary::TGenericSP<_FILELIST_CALLBACK_CONTEXT,NCoreLibrary::TAutoPtr<_FILELIST_CALLBACK_CONTEXT>,_FILELIST_CALLBACK_CONTEXT *,0,_FILELIST_CALLBACK_CONTEXT const *>::Reset(&v70);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x180033398  mov     [rsp-8+arg_10], rbx
0x18003339d  push    rbp
0x18003339e  push    rsi
0x18003339f  push    rdi
0x1800333a0  push    r12
0x1800333a2  push    r13
0x1800333a4  push    r14
0x1800333a6  push    r15
0x1800333a8  lea     rbp, [rsp-430h]
0x1800333b0  sub     rsp, 530h
0x1800333b7  mov     rax, cs:__security_cookie
0x1800333be  xor     rax, rsp
0x1800333c1  mov     [rbp+460h+var_40], rax
0x1800333c8  mov     r13, [rcx+8]
0x1800333cc  mov     r12, rdx
0x1800333cf  mov     r15, [rcx+20h]
0x1800333d3  xor     r14d, r14d
0x1800333d6  mov     [rsp+560h+var_518], rdx
0x1800333db  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x1800333e2  mov     [rbp+460h+var_4E0], rcx
0x1800333e6  mov     ecx, 890h; unsigned __int64
0x1800333eb  mov     [rsp+560h+var_520], r14d
0x1800333f0  mov     [rsp+560h+FileQueue], r13
0x1800333f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800333fa  mov     rsi, rax
0x1800333fd  test    rax, rax
0x180033400  jz      short loc_18003346C
0x180033402  mov     dword ptr [rax], 74736C74h
0x180033408  lea     rcx, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x18003340f  add     rax, 8
0x180033413  mov     [rsi+28h], r14d
0x180033417  mov     [rsi+2Ch], r14
0x18003341b  mov     [rsi+34h], r14d
0x18003341f  mov     [rsi+38h], r14
0x180033423  mov     dword ptr [rax+8], 6B6E6C74h
0x18003342a  mov     [rax], rcx
0x18003342d  mov     [rax+10h], rax
0x180033431  mov     [rax+18h], rax
0x180033435  mov     [rsi+40h], r14
0x180033439  mov     [rsi+48h], r14d
0x18003343d  mov     [rsi+50h], r14
0x180033441  mov     [rsi+58h], r14
0x180033445  mov     [rsi+60h], r14
0x180033449  mov     [rsi+68h], r14
0x18003344d  mov     [rsi+70h], r14w
0x180033452  mov     [rsi+278h], r14w
0x18003345a  mov     [rsi+480h], r14w
0x180033462  mov     [rsi+688h], r14w
0x18003346a  jmp     short loc_18003346F
0x18003346c  mov     rsi, r14
0x18003346f  lea     rcx, [rsp+560h+var_508]
0x180033474  mov     [rsp+560h+var_508], r14
0x180033479  call    ?Reset@?$TGenericSP@U_FILELIST_CALLBACK_CONTEXT@@V?$TAutoPtr@U_FILELIST_CALLBACK_CONTEXT@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<_FILELIST_CALLBACK_CONTEXT,NCoreLibrary::TAutoPtr<_FILELIST_CALLBACK_CONTEXT>,_FILELIST_CALLBACK_CONTEXT *,0,_FILELIST_CALLBACK_CONTEXT const *>::Reset(void)
0x18003347e  mov     [rsp+560h+var_508], rsi
0x180033483  test    rsi, rsi
0x180033486  jz      short loc_1800334A5
0x180033488  lea     rax, [r15+0A8h]
0x18003348f  mov     [rsi+68h], rax
0x180033493  mov     [rsi+60h], r15
0x180033497  mov     rcx, [r15]; Str
0x18003349a  call    FileNamePart
0x18003349f  mov     ecx, [rsp+560h+var_520]
0x1800334a3  jmp     short loc_1800334B1
0x1800334a5  mov     ecx, 8007000Eh
0x1800334aa  mov     rax, r14
0x1800334ad  mov     [rsp+560h+var_520], ecx
0x1800334b1  test    ecx, ecx
0x1800334b3  js      short loc_1800334C6
0x1800334b5  test    rax, rax
0x1800334b8  jz      short loc_1800334C6
0x1800334ba  sub     rax, [r15]
0x1800334bd  sar     rax, 1
0x1800334c0  mov     [rsi+58h], rax
0x1800334c4  jmp     short loc_1800334E1
0x1800334c6  lea     rdx, aCouldNotRetrie; "Could not retrieve filename part of INF"...
0x1800334cd  mov     [rsp+560h+var_520], 8000FFFFh
0x1800334d5  lea     rcx, aProcessv4filel; "ProcessV4FileLists"
0x1800334dc  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800334e1  mov     ebx, [rsp+560h+var_520]
0x1800334e5  test    ebx, ebx
0x1800334e7  js      loc_18003379F
0x1800334ed  lea     rdi, [r12+2]
0x1800334f2  mov     r8d, 104h; nSize
0x1800334f8  lea     r12, [rsi+278h]
0x1800334ff  mov     r9, rdi; lpFileName
0x180033502  mov     rdx, r12; lpReturnedString
0x180033505  lea     rcx, aDatafile; "DataFile"
0x18003350c  call    ?GetStringFromManifest@@YAJPEBGPEAGK0@Z; GetStringFromManifest(ushort const *,ushort *,ulong,ushort const *)
0x180033511  mov     [rsp+560h+var_520], eax
0x180033515  mov     ebx, eax
0x180033517  test    eax, eax
0x180033519  jns     loc_1800335D0
0x18003351f  mov     r8d, eax
0x180033522  lea     rdx, aErrorParsingDa; "Error parsing DataFile directive: hr: 0"...
0x180033529  lea     rcx, aProcessv4filel; "ProcessV4FileLists"
0x180033530  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180033535  cmp     [rsp+560h+var_520], 80070002h
0x18003353d  jnz     short loc_180033547
0x18003353f  mov     [rsp+560h+var_520], 80070BCDh
0x180033547  lea     rax, asc_180041954; "-"
0x18003354e  mov     [rsp+560h+var_4F8], 4
0x180033557  lea     rdx, aDatafile; "DataFile"
0x18003355e  mov     [rsp+560h+var_500], rax
0x180033563  lea     rcx, [rbp+460h+var_4D8]; this
0x180033567  mov     [rsp+560h+var_4F0], 1
0x18003356f  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180033574  mov     rdx, [r15+70h]; unsigned __int16 *
0x180033578  lea     rcx, [rbp+460h+var_4C0]; this
0x18003357c  mov     rbx, rax
0x18003357f  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180033584  mov     rdx, [r15]; unsigned __int16 *
0x180033587  lea     rcx, [rbp+460h+var_4A8]; this
0x18003358b  mov     r11, rax
0x18003358e  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180033593  mov     rdx, [r15+8]; unsigned __int16 *
0x180033597  lea     rcx, [rbp+460h+var_490]; this
0x18003359b  mov     r10, rax
0x18003359e  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800335a3  lea     rcx, [rsp+560h+var_500]
0x1800335a8  mov     [rsp+560h+var_530], r14
0x1800335ad  mov     [rsp+560h+Result], rcx
0x1800335b2  mov     r9, r11
0x1800335b5  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_MISSING_DIRECTIVE; struct _EVENT_DESCRIPTOR *
0x1800335bc  mov     [rsp+560h+CallbackContext], rbx
0x1800335c1  mov     r8, r10
0x1800335c4  mov     rdx, rax; struct SplLogType *
0x1800335c7  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x1800335cc  mov     ebx, [rsp+560h+var_520]
0x1800335d0  test    ebx, ebx
0x1800335d2  js      loc_18003379A
0x1800335d8  mov     rcx, r14
0x1800335db  test    rsi, rsi
0x1800335de  jz      short loc_1800335E3
0x1800335e0  mov     rcx, rsi; struct _FILELIST_CALLBACK_CONTEXT *
0x1800335e3  mov     rdx, rdi; unsigned __int16 *
0x1800335e6  mov     r14, rsi
0x1800335e9  call    ?ParseAppSection@@YAJPEAU_FILELIST_CALLBACK_CONTEXT@@PEBG@Z; ParseAppSection(_FILELIST_CALLBACK_CONTEXT *,ushort const *)
0x1800335ee  mov     [rsp+560h+var_520], eax
0x1800335f2  mov     ebx, eax
0x1800335f4  cmp     eax, 80070002h
0x1800335f9  jnz     short loc_180033605
0x1800335fb  mov     [rsp+560h+var_520], 0
0x180033603  jmp     short loc_18003360D
0x180033605  test    eax, eax
0x180033607  js      loc_180033793
0x18003360d  lea     rdx, [r14+70h]; pBuffer
0x180033611  mov     [rsp+560h+pdwSize], 208h
0x180033619  lea     r8, [rsp+560h+pdwSize]; pdwSize
0x18003361e  xor     ecx, ecx; pMachineName
0x180033620  call    cs:__imp_GetColorDirectoryW
0x180033626  test    eax, eax
0x180033628  jz      short loc_180033638
0x18003362a  mov     eax, [rsp+560h+pdwSize]
0x18003362e  dec     eax
0x180033630  shr     eax, 1
0x180033632  mov     [r14+2Ch], eax
0x180033636  jmp     short loc_18003365D
0x180033638  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18003363d  mov     [rsp+560h+var_520], eax
0x180033641  call    cs:__imp_GetLastError
0x180033647  mov     r8d, eax
0x18003364a  lea     rdx, aErrorRetrievin_7; "Error retrieving color directory: %d"
0x180033651  lea     rcx, aProcessv4filel; "ProcessV4FileLists"
0x180033658  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003365d  mov     ebx, [rsp+560h+var_520]
0x180033661  test    ebx, ebx
0x180033663  js      loc_180033793
0x180033669  test    r14, r14
0x18003366c  jnz     short loc_180033672
0x18003366e  xor     eax, eax
0x180033670  jmp     short loc_180033675
0x180033672  mov     rax, r14
0x180033675  xor     r8d, r8d; Window
0x180033678  lea     rcx, [rsp+560h+var_520]
0x18003367d  mov     [rsp+560h+Result], rcx; Result
0x180033682  lea     r9, ?BuildDriverDataFromFileQueue@@YAIPEAXI_K1@Z; CallbackRoutine
0x180033689  mov     rcx, r13; FileQueue
0x18003368c  mov     [rsp+560h+CallbackContext], rax; CallbackContext
0x180033691  lea     edx, [r8+9]; Flags
0x180033695  call    cs:__imp_SetupScanFileQueueW
0x18003369b  test    eax, eax
0x18003369d  jnz     short loc_1800336CC
0x18003369f  mov     ebx, [rsp+560h+var_520]
0x1800336a3  test    ebx, ebx
0x1800336a5  js      short loc_1800336B6
0x1800336a7  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800336ac  mov     [rsp+560h+var_520], eax
0x1800336b0  mov     ebx, eax
0x1800336b2  test    eax, eax
0x1800336b4  jns     short loc_1800336D8
0x1800336b6  mov     r8d, ebx
0x1800336b9  lea     rdx, aErrorWhileGett; "Error while getting data file and sizes"...
0x1800336c0  lea     rcx, aProcessv4filel; "ProcessV4FileLists"
0x1800336c7  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800336cc  mov     ebx, [rsp+560h+var_520]
0x1800336d0  test    ebx, ebx
0x1800336d2  js      loc_180033793
0x1800336d8  cmp     byte ptr [r14+28h], 0
0x1800336dd  jnz     loc_180033779
0x1800336e3  lea     rdx, aDatafileSpecif; "DataFile specified in manifest does not"...
0x1800336ea  mov     [rsp+560h+var_520], 80070002h
0x1800336f2  lea     rcx, aProcessv4filel; "ProcessV4FileLists"
0x1800336f9  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800336fe  mov     rdx, r12; unsigned __int16 *
0x180033701  lea     rcx, [rbp+460h+var_490]; this
0x180033705  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18003370a  lea     rdx, aDatafile; "DataFile"
0x180033711  mov     rdi, rax
0x180033714  lea     rcx, [rbp+460h+var_4A8]; this
0x180033718  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18003371d  mov     rdx, [r15+70h]; unsigned __int16 *
0x180033721  lea     rcx, [rbp+460h+var_4C0]; this
0x180033725  mov     rbx, rax
0x180033728  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18003372d  mov     rdx, [r15]; unsigned __int16 *
0x180033730  lea     rcx, [rbp+460h+var_4D8]; this
0x180033734  mov     r11, rax
0x180033737  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18003373c  mov     rdx, [r15+8]; unsigned __int16 *
0x180033740  lea     rcx, [rsp+560h+var_500]; this
0x180033745  mov     r10, rax
0x180033748  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18003374d  mov     [rsp+560h+var_530], 0
0x180033756  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_MISSING_FILE; struct _EVENT_DESCRIPTOR *
0x18003375d  mov     [rsp+560h+Result], rdi
0x180033762  mov     r9, r11
0x180033765  mov     r8, r10
0x180033768  mov     [rsp+560h+CallbackContext], rbx
0x18003376d  mov     rdx, rax; struct SplLogType *
0x180033770  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180033775  mov     ebx, [rsp+560h+var_520]
0x180033779  test    ebx, ebx
0x18003377b  js      short loc_180033793
0x18003377d  mov     r9, [r14+58h]; unsigned __int64
0x180033781  lea     rcx, [rbp+460h+var_460]; unsigned __int16 *
0x180033785  mov     r8, [r15]; unsigned __int16 *
0x180033788  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003378d  mov     ebx, eax
0x18003378f  mov     [rsp+560h+var_520], eax
0x180033793  mov     r12, [rsp+560h+var_518]
0x180033798  jmp     short loc_1800337A2
0x18003379a  mov     r12, [rsp+560h+var_518]
0x18003379f  mov     r14, rsi
0x1800337a2  lea     r13, [r14+8]
0x1800337a6  xor     r14d, r14d
0x1800337a9  test    ebx, ebx
0x1800337ab  js      short loc_1800337C1
0x1800337ad  mov     rax, r13
0x1800337b0  neg     rax
0x1800337b3  sbb     ebx, ebx
0x1800337b5  not     ebx
0x1800337b7  and     ebx, 80004005h
0x1800337bd  mov     [rsp+560h+var_520], ebx
0x1800337c1  mov     dword ptr [rsp+560h+var_500], 7274736Dh
0x1800337c9  lea     rdi, ?gszzEmpty@TMultiString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TMultiString::gszzEmpty
0x1800337d0  mov     [rsp+560h+var_4F8], rdi
0x1800337d5  mov     [rsp+560h+var_4F0], r14d
0x1800337da  test    r13, r13
0x1800337dd  jz      short loc_1800337E3
0x1800337df  mov     r14, [r13+10h]
0x1800337e3  test    ebx, ebx
0x1800337e5  js      loc_180033B07
0x1800337eb  test    r13, r13
0x1800337ee  jz      loc_1800338FB
0x1800337f4  cmp     r14, r13
0x1800337f7  jz      loc_1800338F6
0x1800337fd  cmp     byte ptr [r14+40h], 0
0x180033802  jz      short loc_18003384B
0x180033804  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18003380b  mov     rcx, r14; this
0x18003380e  lea     r8, [rsp+560h+var_518]; struct TString *
0x180033813  mov     [rsp+560h+var_518], rax
0x180033818  lea     rdx, [rbp+460h+var_460]; unsigned __int16 *
0x18003381c  call    ?ToString@TAppRegistration@@QEAAJPEBGAEAVTString@NCoreLibrary@@@Z; TAppRegistration::ToString(ushort const *,NCoreLibrary::TString &)
0x180033821  mov     [rsp+560h+var_520], eax
0x180033825  test    eax, eax
0x180033827  js      short loc_18003383C
0x180033829  mov     rdx, [rsp+560h+var_518]; unsigned __int16 *
0x18003382e  lea     rcx, [rsp+560h+var_500]; this
0x180033833  call    ?Cat@TMultiString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TMultiString::Cat(ushort const *)
0x180033838  mov     [rsp+560h+var_520], eax
0x18003383c  mov     rdx, [rsp+560h+var_518]; void *
0x180033841  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180033846  jmp     loc_1800338E1
0x18003384b  mov     [rsp+560h+var_520], 80070002h
0x180033853  lea     rdx, aPrinterExtensi; "Printer extension '%ws' specified in ma"...
0x18003385a  mov     r8, [r14+48h]
0x18003385e  lea     rcx, aProcessv4filel; "ProcessV4FileLists"
0x180033865  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003386a  mov     rdx, [r14+48h]; unsigned __int16 *
0x18003386e  lea     rcx, [rbp+460h+var_490]; this
0x180033872  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180033877  lea     rdx, aPrinterextensi; "PrinterExtension"
0x18003387e  mov     rdi, rax
0x180033881  lea     rcx, [rbp+460h+var_4A8]; this
0x180033885  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18003388a  mov     rdx, [r15+70h]; unsigned __int16 *
0x18003388e  lea     rcx, [rbp+460h+var_4C0]; this
0x180033892  mov     rbx, rax
0x180033895  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
  ... truncated ...
```
