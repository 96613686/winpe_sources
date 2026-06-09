# BuildPrinterInfo

- ea: `0x18007bd7c`
- end: `0x18007d724`
- name: `BuildPrinterInfo`
- size: `6568`
- prototype: `__int64 __fastcall(struct _INISPOOLER *, int)`
- caller_count: `1`
- callee_count: `54`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180075f58`

## callees

- `0x180004fb8`
- `0x180005d90`
- `0x1800085ac`
- `0x1800086e0`
- `0x180008730`
- `0x180009630`
- `0x18000bc30`
- `0x18000d39c`
- `0x18000e890`
- `0x18000edc4`
- `0x180010630`
- `0x1800170a0`
- `0x18001d8e0`
- `0x18001fb10`
- `0x1800247f0`
- `0x180024824`
- `0x180024858`
- `0x180025270`
- `0x1800252c0`
- `0x180028060`
- `0x18002c780`
- `0x18002d388`
- `0x18002ee28`
- `0x180031348`
- `0x180033734`
- `0x180035a44`
- `0x180035ae4`
- `0x180037264`
- `0x1800372f8`
- `0x18003a888`
- `0x18003cf80`
- `0x18003e984`
- `0x18003ea2c`
- `0x180045010`
- `0x180046650`
- `0x180051ccc`
- `0x1800532c0`
- `0x180054638`
- `0x1800547e0`
- `0x180054aa8`
- `0x18006263c`
- `0x180073674`
- `0x1800740f4`
- `0x1800746a4`
- `0x18007a200`
- `0x18007bd7c`
- `0x1800978dc`
- `0x180097f10`
- `0x180098ccc`
- `0x18009ef60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007d6b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007d6b9`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18007c3cf`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18007c3cf`
- `ntdll!NtCreateFile` at `0x18007c42e`
- `ntdll!NtCreateFile` at `0x18007c42e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bf03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bf5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c6dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c75a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bf03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bf5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c6dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c75a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c4a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c4a4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18007c395`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18007c395`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007bef2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007bf51`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007bef2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007bf51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c916`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d583`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c916`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d583`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c8d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c8d6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18007d023`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18007d160`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18007d023`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18007d160`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18007d08e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18007d19a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18007d08e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18007d19a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bfa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007cf97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d523`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bfa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007cf97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d523`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007cf4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007cf4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007c0ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007c0ed`
- `SPOOLSS!DllFreeSplStr` at `0x18007bebf`
- `SPOOLSS!DllFreeSplStr` at `0x18007bf1b`
- `SPOOLSS!DllFreeSplStr` at `0x18007bf8a`
- `SPOOLSS!DllFreeSplStr` at `0x18007bebf`
- `SPOOLSS!DllFreeSplStr` at `0x18007bf1b`
- `SPOOLSS!DllFreeSplStr` at `0x18007bf8a`
- `SPOOLSS!DllFreeSplMem` at `0x18007c660`
- `SPOOLSS!DllFreeSplMem` at `0x18007d562`
- `SPOOLSS!DllFreeSplMem` at `0x18007c660`
- `SPOOLSS!DllFreeSplMem` at `0x18007d562`
- `SPOOLSS!DllAllocSplMem` at `0x18007c0c5`
- `SPOOLSS!DllAllocSplMem` at `0x18007c56c`
- `SPOOLSS!DllAllocSplMem` at `0x18007c64b`
- `SPOOLSS!DllAllocSplMem` at `0x18007ce35`
- `SPOOLSS!DllAllocSplMem` at `0x18007ce96`
- `SPOOLSS!DllAllocSplMem` at `0x18007c0c5`
- `SPOOLSS!DllAllocSplMem` at `0x18007c56c`
- `SPOOLSS!DllAllocSplMem` at `0x18007c64b`
- `SPOOLSS!DllAllocSplMem` at `0x18007ce35`
- `SPOOLSS!DllAllocSplMem` at `0x18007ce96`
- `SPOOLSS!AllocSplStr` at `0x18007be4f`
- `SPOOLSS!AllocSplStr` at `0x18007c144`
- `SPOOLSS!AllocSplStr` at `0x18007c196`
- `SPOOLSS!AllocSplStr` at `0x18007c1e8`
- `SPOOLSS!AllocSplStr` at `0x18007c23a`
- `SPOOLSS!AllocSplStr` at `0x18007c513`
- `SPOOLSS!AllocSplStr` at `0x18007c737`
- `SPOOLSS!AllocSplStr` at `0x18007c7e3`
- `SPOOLSS!AllocSplStr` at `0x18007c82b`
- `SPOOLSS!AllocSplStr` at `0x18007c89f`
- `SPOOLSS!AllocSplStr` at `0x18007c961`
- `SPOOLSS!AllocSplStr` at `0x18007c9b3`
- `SPOOLSS!AllocSplStr` at `0x18007c9fe`
- `SPOOLSS!AllocSplStr` at `0x18007ca46`
- `SPOOLSS!AllocSplStr` at `0x18007be4f`
- `SPOOLSS!AllocSplStr` at `0x18007c144`
- `SPOOLSS!AllocSplStr` at `0x18007c196`
- `SPOOLSS!AllocSplStr` at `0x18007c1e8`
- `SPOOLSS!AllocSplStr` at `0x18007c23a`
- `SPOOLSS!AllocSplStr` at `0x18007c513`
- `SPOOLSS!AllocSplStr` at `0x18007c737`
- `SPOOLSS!AllocSplStr` at `0x18007c7e3`
- `SPOOLSS!AllocSplStr` at `0x18007c82b`
- `SPOOLSS!AllocSplStr` at `0x18007c89f`
- `SPOOLSS!AllocSplStr` at `0x18007c961`
- `SPOOLSS!AllocSplStr` at `0x18007c9b3`
- `SPOOLSS!AllocSplStr` at `0x18007c9fe`
- `SPOOLSS!AllocSplStr` at `0x18007ca46`
- `SPOOLSS!ReallocSplMem` at `0x18007d30a`
- `SPOOLSS!ReallocSplMem` at `0x18007d30a`

## string_xrefs

- `0x18007c852`: `PrintQueueV4DriverDirectory`
- `0x18007bdf0`: `DefaultSpoolDirectory`
- `0x18007bfc8`: `DefaultSpoolDirectory`
- `0x18007c36c`: `Using spool directory: %ws (vs default: %ws)`
- `0x18007bf74`: `Failed to create DefaultSpoolDirectory %ws. Error %d`
- `0x18007c480`: `User specified spool directory %ws can't be opened, revert back to default.`
- `0x18007c444`: `Open spool directory %ws returns: status %u, IoStatus %u, handle %p`
- `0x18007c4bb`: `User specified spool directory %ws can't be resolved, revert back to default.`
- `0x18007cb8b`: `Queue '%ws' will be deleted because it is using a v4 driver with a third-party port monitor`
- `0x18007d4f4`: `Failed to create print queue %ws on %ws`
- `0x18007d66a`: `CreateFilePool: GetPrinterDirectory Failed`
- `0x18007c1c0`: `SpoolDirectory`
- `0x18007ce7e`: `CreatorSid`
- `0x18007ceb7`: `CreatorSid`
- `0x18007c2a0`: `DsKeyUpdateForeground`
- `0x18007cf1a`: `Security`
- `0x18007cf77`: `Security`
- `0x18007d0a1`: `Security`
- `0x18007d1ad`: `Security`
- `0x18007c267`: `DsKeyUpdate`

## pseudocode

```c
__int64 __fastcall BuildPrinterInfo(struct _INISPOOLER *a1, int a2)
{
  __int64 v2; // r8
  void *v5; // rcx
  int v6; // r15d
  __int64 *v7; // rbx
  unsigned int v8; // r12d
  __int64 v9; // rax
  int v11; // edi
  unsigned __int64 v12; // rax
  DWORD v13; // eax
  __int64 v14; // r9
  __int64 v15; // rax
  void *v16; // rcx
  unsigned int v17; // ebx
  int i; // eax
  __int64 v19; // rdi
  int v20; // ecx
  __int64 v21; // rax
  int *v22; // rbx
  int v23; // eax
  int v24; // eax
  __int64 v25; // r10
  unsigned __int16 *v26; // rax
  int v27; // ecx
  int v28; // edx
  __int64 v29; // rbx
  void *v30; // rcx
  __int64 v31; // rax
  int v32; // ebx
  unsigned __int8 *v33; // r14
  __int64 TokenList; // r13
  __int64 v35; // rcx
  const unsigned __int16 *v36; // rbx
  DWORD LastError; // eax
  __int64 IniKey; // rax
  const unsigned __int16 *v39; // rbx
  DWORD v40; // eax
  __int64 v41; // rcx
  __int64 LocalDriver; // rax
  const unsigned __int16 *v43; // rbx
  DWORD v44; // eax
  char v45; // r14
  __int64 v46; // rax
  unsigned int v47; // edx
  int v48; // eax
  unsigned __int32 v49; // r8d
  int v50; // ebx
  __int64 v51; // rax
  struct SplLogType *v52; // rax
  __int64 v53; // r10
  int *v54; // r15
  int v55; // eax
  int v56; // ecx
  int v57; // eax
  int v58; // edx
  __int64 v59; // rcx
  __int64 v60; // rcx
  unsigned __int8 *v61; // rax
  unsigned __int8 *v62; // rax
  __int64 v63; // rcx
  __int64 (__fastcall *v64)(HKEY); // rax
  int Value; // eax
  PSECURITY_DESCRIPTOR *v66; // rbx
  unsigned __int8 *v67; // rax
  int v68; // edx
  unsigned int v69; // r8d
  __int64 v70; // rcx
  DWORD SecurityDescriptorLength; // eax
  int v72; // eax
  DWORD v73; // eax
  __int64 v74; // r8
  __int64 v75; // rcx
  unsigned int v76; // r11d
  __int64 v77; // rcx
  unsigned int v78; // eax
  unsigned int v79; // r14d
  __int64 v80; // rax
  __int64 v81; // rbx
  __int64 v82; // r11
  __int64 v83; // rax
  __int64 v84; // rcx
  int v85; // edx
  bool v86; // zf
  int v87; // eax
  int v88; // r14d
  _WORD *v89; // r8
  unsigned __int64 v90; // rax
  _WORD *v91; // rdx
  unsigned __int64 v92; // rax
  __int64 v93; // rcx
  __int64 v94; // rax
  void (*v95)(void); // rax
  void *v96; // rcx
  void *v97; // rcx
  const unsigned __int16 *v98; // r8
  const unsigned __int16 *v99; // r9
  int FilePool; // eax
  __int64 j; // rbx
  __int64 v102; // rdx
  const unsigned __int16 *AllocationSize; // [rsp+20h] [rbp-E0h]
  unsigned int FileAttributes; // [rsp+28h] [rbp-D8h]
  unsigned int ShareAccess; // [rsp+30h] [rbp-D0h]
  unsigned int v106; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v107; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WORD pControl[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v110[4]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v111; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v112; // [rsp+7Ch] [rbp-84h] BYREF
  int v113; // [rsp+80h] [rbp-80h]
  int v114; // [rsp+84h] [rbp-7Ch] BYREF
  SIZE_T uBytes; // [rsp+88h] [rbp-78h] BYREF
  DWORD dwRevision; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v117[4]; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned __int8 v118[4]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 v119[4]; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned __int8 v120[4]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v121[4]; // [rsp+A4h] [rbp-5Ch] BYREF
  int v122; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v123; // [rsp+ACh] [rbp-54h]
  void *FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  HKEY phkResult; // [rsp+B8h] [rbp-48h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+C0h] [rbp-40h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-28h] BYREF
  void *v128[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v129; // [rsp+100h] [rbp+0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+110h] [rbp+10h] BYREF
  char v131[32]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int8 v132[2]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR PathName[264]; // [rsp+370h] [rbp+270h] BYREF
  unsigned __int8 v134[2]; // [rsp+580h] [rbp+480h] BYREF
  unsigned __int16 v135[264]; // [rsp+790h] [rbp+690h] BYREF
  WCHAR Buffer[272]; // [rsp+9A0h] [rbp+8A0h] BYREF

  v2 = *((_QWORD *)a1 + 3);
  *(_DWORD *)v117 = a2;
  LocalSpoolerTelemetry::WriteDbgTraceInfo("BuildPrinterInfo", L"Entering %ws", v2);
  v5 = (void *)*((_QWORD *)a1 + 30);
  FileHandle = (void *)-1LL;
  v6 = 0;
  v114 = 0;
  v7 = (__int64 *)((char *)a1 + 96);
  uBytes = 0;
  v107 = 0;
  hKey = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v106 = 520;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *(_WORD *)v132 = 0;
  IoStatusBlock = 0;
  v129 = 0;
  v8 = 1;
  if ( SplRegQueryValue(v5, L"DefaultSpoolDirectory", 0, v132, &v106, a1) )
  {
    v11 = 1;
  }
  else
  {
    v9 = AllocSplStr(v132);
    *v7 = v9;
    if ( !v9 )
    {
LABEL_3:
      LocalSpoolerTelemetry::WriteDbgTraceInfo("BuildPrinterInfo", L"Leaving %ws", *((_QWORD *)a1 + 3));
      return 0;
    }
    v11 = 0;
  }
  GetPrinterDirectory(0, 0, PathName, 0x104u, (__int64)a1);
  if ( !*v7 )
    goto LABEL_3;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = CreateEverybodySecurityDescriptor();
  SecurityAttributes.bInheritHandle = 0;
  if ( !SecurityAttributes.lpSecurityDescriptor )
  {
    DllFreeSplStr(*v7);
    *v7 = 0;
    goto LABEL_3;
  }
  v12 = -1;
  do
    ++v12;
  while ( PathName[v12] );
  if ( v12 <= 0xF8 && CreateDirectoryW(PathName, &SecurityAttributes) )
    goto LABEL_19;
  v11 = 1;
  if ( GetLastError() == 183 )
    goto LABEL_19;
  DllFreeSplStr(*v7);
  *v7 = 0;
  GetPrinterDirectory(0, 0, PathName, 0x104u, (__int64)a1);
  if ( !*v7 )
    goto LABEL_3;
  if ( CreateDirectoryW(PathName, &SecurityAttributes) || (v13 = GetLastError()) == 0 || v13 == 183 )
  {
LABEL_19:
    v113 = a2;
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
    if ( v11 )
    {
      v14 = *v7;
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      SetPrinterDataServer(a1, L"DefaultSpoolDirectory", 1, v14, 2 * v15 + 2);
    }
    if ( removeMXDW )
      RemoveOfflinePrinter(a1, 0);
    if ( removeMPDW )
      RemoveOfflinePrinter(a1, 1);
    v16 = (void *)*((_QWORD *)a1 + 30);
    v17 = 0;
    v123 = 0;
    v106 = 260;
    for ( i = SplRegEnumKey(v16, 0, v135, &v106, 0, a1); ; i = SplRegEnumKey(v96, v17, v135, &v106, 0, a1) )
    {
      if ( i )
      {
        if ( dwGMTAdjustedForDSTFlag == 1 )
        {
          v97 = (void *)*((_QWORD *)a1 + 29);
          *(_DWORD *)v117 = 1;
          SplRegSetValue(v97, L"GMTAdjustedForDST", 4u, v117, 4u, a1);
          dwGMTAdjustedForDSTFlag = 0;
        }
        if ( (*((_DWORD *)a1 + 42) & 0x1000000) != 0 )
        {
          *(_WORD *)v134 = 0;
          if ( *((_QWORD *)a1 + 38) == -1 )
          {
            if ( (unsigned int)GetPrinterDirectory(0, 0, (unsigned __int16 *)v134, 0x104u, (__int64)a1) )
            {
              FilePool = CreateFilePool(
                           (void **)a1 + 38,
                           (const unsigned __int16 *)v134,
                           v98,
                           v99,
                           AllocationSize,
                           FileAttributes,
                           ShareAccess);
              if ( FilePool < 0 )
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "BuildPrinterInfo",
                  L"Initialization of FilePool failed. Error %d",
                  (unsigned int)FilePool);
            }
            else
            {
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "BuildPrinterInfo",
                L"CreateFilePool: GetPrinterDirectory Failed");
            }
          }
          ProcessShadowJobs(0, a1);
          if ( (unsigned int)GetPrinterDirectory(0, 0, (unsigned __int16 *)v132, 0x104u, (__int64)a1) )
          {
            for ( j = *((_QWORD *)a1 + 5); j; j = *(_QWORD *)(j + 8) )
            {
              v102 = *(_QWORD *)(j + 208);
              if ( v102 )
              {
                if ( (unsigned int)_o__wcsicmp(v132, v102) )
                  ProcessShadowJobs(j, a1);
              }
            }
          }
        }
        UpdateReferencesToChainedJobs(a1);
        CleanupDeletedPrinters(a1);
        goto LABEL_265;
      }
      if ( !(unsigned int)SplRegCreateKey(*((void **)a1 + 30), v135, 0, 0x2001Fu, 0, (void **)&hKey, 0, a1) )
        break;
LABEL_247:
      v96 = (void *)*((_QWORD *)a1 + 30);
      v123 = ++v17;
      v106 = 260;
    }
    v106 = 520;
    *(_WORD *)v134 = 0;
    if ( SplRegQueryValue(hKey, L"Printer Driver", &v107, v134, &v106, a1) || (v19 = DllAllocSplMem(600)) == 0 )
    {
LABEL_245:
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_247;
    }
    SafeIncrementReference((unsigned int *)a1 + 4);
    *(_DWORD *)v19 = 18769;
    GetSystemTime((LPSYSTEMTIME)(v19 + 232));
    v20 = dwUniquePrinterSessionID;
    *(_DWORD *)(v19 + 380) = dwUniquePrinterSessionID;
    v106 = 520;
    *(_WORD *)v132 = 0;
    dwUniquePrinterSessionID = v20 + 1;
    if ( !SplRegQueryValue(hKey, (const unsigned __int16 *)szName, 0, v132, &v106, a1) )
    {
      v21 = AllocSplStr(v132);
      *(_QWORD *)(v19 + 24) = v21;
      *(_WORD *)(v19 + 32) = HashName(v21);
    }
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"PerUserName", 0, v132, &v106, a1) )
      *(_QWORD *)(v19 + 544) = AllocSplStr(v132);
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"SpoolDirectory", &v107, v132, &v106, a1) && *(_WORD *)v132 )
      *(_QWORD *)(v19 + 208) = AllocSplStr(v132);
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"ObjectGUID", &v107, v132, &v106, a1) && *(_WORD *)v132 )
      *(_QWORD *)(v19 + 336) = AllocSplStr(v132);
    v106 = 4;
    SplRegQueryValue(hKey, L"DsKeyUpdate", &v107, (unsigned __int8 *)(v19 + 344), &v106, a1);
    v22 = (int *)(v19 + 388);
    v106 = 4;
    SplRegQueryValue(hKey, L"DsKeyUpdateForeground", &v107, (unsigned __int8 *)(v19 + 388), &v106, a1);
    if ( (*((_DWORD *)a1 + 42) & 0x4000000) != 0 )
    {
      v106 = 4;
      SplRegQueryValue(hKey, L"Action", &v107, (unsigned __int8 *)(v19 + 372), &v106, a1);
    }
    else
    {
      v23 = *v22;
      if ( (*v22 & 0xE0000000) != 0 )
      {
        if ( (v23 & 0x40000000) != 0 )
        {
          *(_DWORD *)(v19 + 372) |= 1u;
        }
        else if ( v23 >= 0 )
        {
          if ( (v23 & 0x20000000) != 0 )
            *(_DWORD *)(v19 + 372) |= 4u;
        }
        else
        {
          *(_DWORD *)(v19 + 372) |= 8u;
        }
        v24 = v23 & 0x1FFFFFFF;
      }
      else
      {
        v24 = 0;
      }
      *v22 = v24;
    }
    v25 = *(_QWORD *)(v19 + 208);
    if ( v25 )
    {
      v26 = *(unsigned __int16 **)(v19 + 208);
      do
      {
        v27 = *(unsigned __int16 *)((char *)PathName + (_QWORD)v26 - v25);
        v28 = *v26 - v27;
        if ( v28 )
          break;
        ++v26;
      }
      while ( v27 );
      if ( v28 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "BuildPrinterInfo",
          L"Using spool directory: %ws (vs default: %ws)",
          *(_QWORD *)(v19 + 208),
          PathName);
        if ( GetFullPathNameW(*(LPCWSTR *)(v19 + 208), 0x109u, Buffer, 0)
          && (unsigned int)IsSpecialTypeFullPathName(*(unsigned __int16 **)(v19 + 208)) )
        {
          IoStatusBlock = 0;
          RtlDosPathNameToRelativeNtPathName_U_WithStatus(Buffer, &v129, 0, 0);
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 64;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&v129;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v29 = (unsigned int)NtCreateFile(
                                &FileHandle,
                                0x100000u,
                                &ObjectAttributes,
                                &IoStatusBlock,
                                0,
                                0x80u,
                                1u,
                                1u,
                                1u,
                                0,
                                0);
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "BuildPrinterInfo",
            L"Open spool directory %ws returns: status %u, IoStatus %u, handle %p",
            Buffer,
            v29,
            IoStatusBlock.Information,
            FileHandle);
          if ( !(_DWORD)v29 && IoStatusBlock.Information == 1 && (v30 = FileHandle, FileHandle != (void *)-1LL)
            || (LocalSpoolerTelemetry::WriteDbgTraceError(
                  "BuildPrinterInfo",
                  L"User specified spool directory %ws can't be opened, revert back to default.",
                  Buffer),
                *(_QWORD *)(v19 + 208) = 0,
                v30 = FileHandle,
                FileHandle != (void *)-1LL) )
          {
            CloseHandle(v30);
            FileHandle = (void *)-1LL;
          }
        }
        else
        {
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "BuildPrinterInfo",
            L"User specified spool directory %ws can't be resolved, revert back to default.",
            *(_QWORD *)(v19 + 208));
          *(_QWORD *)(v19 + 208) = 0;
        }
      }
    }
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"Share Name", &v107, v132, &v106, a1) )
    {
      v31 = AllocSplStr(v132);
      *(_QWORD *)(v19 + 40) = v31;
      *(_WORD *)(v19 + 48) = HashName(v31);
    }
    v106 = 520;
    *(_WORD *)v132 = 0;
    v32 = SplRegQueryValue(hKey, L"Port", &v107, v132, &v106, a1);
    if ( v32 == 234 && (v33 = (unsigned __int8 *)DllAllocSplMem(v106)) != 0 )
    {
      v6 = 1;
      v32 = SplRegQueryValue(hKey, L"Port", &v107, v33, &v106, a1);
    }
    else
    {
      v33 = v132;
    }
    TokenList = 0;
    v111 = 1;
    if ( !v32 )
    {
      TokenList = CreateTokenList((unsigned __int16 *)v33);
      if ( TokenList )
      {
        if ( (unsigned int)ValidatePortTokenList(TokenList, (_DWORD)a1, 1, (unsigned int)&v114, (__int64)&v111) )
        {
          HIDWORD(uBytes) = v114;
          if ( v114 && *(_DWORD *)(TokenList + 4) > 1u )
          {
            v36 = *(const unsigned __int16 **)(v19 + 24);
            LastError = GetLastError();
            SplLogEvent(&MSG_NO_PORT_FOUND_FOR_PRINTER, LastError, v36, v33, 0);
          }
          *(_QWORD *)(v19 + 312) = DllAllocSplMem((unsigned int)(8 * *(_DWORD *)(TokenList + 4)));
        }
        else
        {
          LogFatalPortError(v35, *(_QWORD *)(v19 + 24));
          FreePortTokenList(TokenList);
          TokenList = 0;
          HIDWORD(uBytes) = v114;
        }
      }
    }
    if ( v6 )
      DllFreeSplMem(v33);
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"Print Processor", &v107, v132, &v106, a1) )
    {
      IniKey = FindIniKey(*((_QWORD *)a1 + 6), szEnvironment, 0);
      if ( IniKey )
        *(_QWORD *)(v19 + 56) = FindIniKey(*(_QWORD *)(IniKey + 56), v132, 0);
      if ( !*(_QWORD *)(v19 + 56) )
      {
        v39 = *(const unsigned __int16 **)(v19 + 24);
        v40 = GetLastError();
        SplLogEvent(&MSG_NO_PRINT_PROC_FOUND_FOR_PRINTER, v40, v39, v132, 0);
      }
    }
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"Datatype", &v107, v132, &v106, a1) )
      *(_QWORD *)(v19 + 64) = AllocSplStr(v132);
    LocalDriver = FindLocalDriver(v41, v134);
    *(_QWORD *)(v19 + 88) = LocalDriver;
    if ( LocalDriver )
    {
      if ( (*((_DWORD *)a1 + 42) & 0x4000000) != 0 && (*(_DWORD *)(LocalDriver + 260) || dwSPUpgradeFlag) )
      {
        *(_DWORD *)(LocalDriver + 260) = 0;
        *(_QWORD *)(v19 + 88) = 0;
      }
    }
    else
    {
      v43 = *(const unsigned __int16 **)(v19 + 24);
      v44 = GetLastError();
      SplLogEvent(&MSG_NO_DRIVER_FOUND_FOR_PRINTER, v44, v43, v134, 0);
    }
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"Location", &v107, v132, &v106, a1) )
      *(_QWORD *)(v19 + 144) = AllocSplStr(v132);
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, (const unsigned __int16 *)&szName[16], &v107, v132, &v106, a1) )
      *(_QWORD *)(v19 + 80) = AllocSplStr(v132);
    v106 = 520;
    v45 = 1;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"PrintQueueV4DriverDirectory", &v107, v132, &v106, a1) )
    {
      if ( StringCchPrintfW(v135, 0x104u, L"%s\\V4Dirs\\%s", *((_QWORD *)a1 + 4), v132) < 0
        || (v46 = AllocSplStr(v135), (*(_QWORD *)(v19 + 488) = v46) == 0) )
      {
        v45 = 0;
      }
    }
    phkResult = 0;
    if ( !RegOpenKeyExW(hKey, L"PrinterDriverData", 0, 0x20019u, &phkResult) )
    {
      v106 = 4;
      SplRegQueryValue(phkResult, L"EnableBranchOfficePrinting", 0, (unsigned __int8 *)(v19 + 528), &v106, a1);
      RegCloseKey(phkResult);
    }
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"QueueInstanceId", &v107, v132, &v106, a1) && *(_WORD *)v132 )
      *(_QWORD *)(v19 + 504) = AllocSplStr(v132);
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"DeviceInterfaceId", &v107, v132, &v106, a1) && *(_WORD *)v132 )
      *(_QWORD *)(v19 + 512) = AllocSplStr(v132);
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"Parameters", &v107, v132, &v106, a1) )
      *(_QWORD *)(v19 + 72) = AllocSplStr(v132);
    v106 = 520;
    *(_WORD *)v132 = 0;
    if ( !SplRegQueryValue(hKey, L"Separator File", &v107, v132, &v106, a1) )
      *(_QWORD *)(v19 + 128) = AllocSplStr(v132);
    *(_DWORD *)v118 = 0;
    v106 = 4;
    if ( SplRegQueryValue(hKey, L"Attributes", 0, v118, &v106, a1) )
      v47 = 0;
    else
      v47 = *(_DWORD *)v118;
    _INIPRINTER::SetAttributes((_INIPRINTER *)v19, v47);
    *(_DWORD *)v119 = 0;
    v106 = 4;
    v48 = SplRegQueryValue(hKey, L"StatusExt", &v107, v119, &v106, a1);
    v49 = *(_DWORD *)v119;
    if ( v48 )
      v49 = 0;
    _INIPRINTER::LogPrinterStatusExtChange(
      (_INIPRINTER *)v19,
      _InterlockedExchange((volatile __int32 *)(v19 + 140), v49),
      v49);
    *(_DWORD *)v120 = 0;
    v106 = 4;
    v50 = SplRegQueryValue(hKey, L"Status", &v107, v120, &v106, a1);
    _INIPRINTER::LogPrinterStatusChange(
      (_INIPRINTER *)v19,
      _InterlockedExchange((volatile __int32 *)(v19 + 136), *(_DWORD *)v120 | 0x100),
      *(_DWORD *)v120 | 0x100);
    if ( v50 )
      _INIPRINTER::AddPrinterStatusFlags((_INIPRINTER *)v19, 0x40u);
    else
      _INIPRINTER::MaskPrinterStatusFlags((_INIPRINTER *)v19, 0x1F1u);
    if ( (*(_BYTE *)(v19 + 136) & 0x40) != 0 )
      _INIPRINTER::AddPrinterStatusFlags((_INIPRINTER *)v19, 0x10u);
    if ( !g_bTestMode )
    {
      v51 = *(_QWORD *)(v19 + 88);
      if ( v51 )
      {
        if ( *(_DWORD *)(v51 + 236) >= 4u && !v111 )
        {
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "BuildPrinterInfo",
            L"Queue '%ws' will be deleted because it is using a v4 driver with a third-party port monitor",
            *(_QWORD *)(v19 + 24));
          _INIPRINTER::AddPrinterStatusFlags((_INIPRINTER *)v19, 0x10u);
          SplLogType::SplLogType((SplLogType *)v128, *(const unsigned __int16 **)(*(_QWORD *)(v19 + 88) + 24LL));
          v52 = SplLogType::SplLogType((SplLogType *)v131, *(const unsigned __int16 **)(v19 + 24));
          SplLogEvent2(&SETUP_PRINTER_UNSUPPORTED_PORT_MONITOR, v52, v53, 0);
        }
      }
    }
    *(_DWORD *)(v19 + 420) = MapToPrinterQueueStatus(v19, 0);
    v54 = (int *)(v19 + 112);
    v106 = 4;
    SplRegQueryValue(hKey, L"Priority", &v107, (unsigned __int8 *)(v19 + 112), &v106, a1);
    v106 = 4;
    SplRegQueryValue(hKey, L"Default Priority", &v107, (unsigned __int8 *)(v19 + 116), &v106, a1);
    v106 = 4;
    SplRegQueryValue(hKey, L"UntilTime", &v107, (unsigned __int8 *)(v19 + 124), &v106, a1);
    v106 = 4;
    SplRegQueryValue(hKey, L"StartTime", &v107, (unsigned __int8 *)(v19 + 120), &v106, a1);
    v106 = 4;
    SplRegQueryValue(hKey, L"Redirected", &v107, (unsigned __int8 *)(v19 + 536), &v106, a1);
    if ( dwGMTAdjustedForDSTFlag == 1 )
    {
      AdjustGMTIfDST(v19);
      v113 = 1;
    }
    v106 = 4;
    if ( SplRegQueryValue(hKey, L"dnsTimeout", &v107, (unsigned __int8 *)(v19 + 324), &v106, a1) )
      *(_DWORD *)(v19 + 324) = 15000;
    v106 = 4;
    if ( SplRegQueryValue(hKey, L"txTimeout", &v107, (unsigned __int8 *)(v19 + 328), &v106, a1) )
      *(_DWORD *)(v19 + 328) = 45000;
    v106 = 4;
    v55 = SplRegQueryValue(hKey, L"ChangeID", &v107, (unsigned __int8 *)(v19 + 304), &v106, a1);
    v56 = v113;
    *(_DWORD *)v121 = 0;
    v106 = 4;
    if ( v55 )
      v56 = 1;
    v113 = v56;
    v57 = SplRegQueryValue(hKey, L"ContainerTsSessionId", &v107, v121, &v106, a1);
    v58 = *(_DWORD *)v121;
    v59 = *(_QWORD *)(v19 + 24);
    if ( v57 )
      v58 = 0;
    *(_DWORD *)(v19 + 532) = v58;
    LPatchDefaultDevmode(v59);
    *(_DWORD *)(v19 + 384) = 0;
    *(_QWORD *)(v19 + 104) = 0;
    *(_DWORD *)(v19 + 96) = 0;
    if ( !SplRegQueryValue(hKey, L"Default DevMode", &v107, 0, (unsigned int *)(v19 + 96), a1) )
    {
      v60 = *(unsigned int *)(v19 + 96);
      if ( (_DWORD)v60 )
      {
        v61 = (unsigned __int8 *)DllAllocSplMem(v60);
        *(_QWORD *)(v19 + 104) = v61;
        SplRegQueryValue(hKey, L"Default DevMode", &v107, v61, (unsigned int *)(v19 + 96), a1);
      }
    }
    if ( !SplRegQueryValue(hKey, L"CreatorSid", &v107, 0, &v106, a1) && v106 )
    {
      v62 = (unsigned __int8 *)DllAllocSplMem(v106);
      *(_QWORD *)(v19 + 472) = v62;
      SplRegQueryValue(hKey, L"CreatorSid", &v107, v62, &v106, a1);
    }
    v63 = *(_QWORD *)(v19 + 88);
    if ( v63 && *(_DWORD *)(v63 + 236) >= 4u )
      *(_DWORD *)(v19 + 552) = PrintCore::IppSelection::GetModernPrinterType(*(_QWORD *)(v63 + 144));
    v64 = (__int64 (__fastcall *)(HKEY))*((_QWORD *)a1 + 22);
    if ( v64 )
      *(_QWORD *)(v19 + 296) = v64(hKey);
    Value = SplRegQueryValue(hKey, L"Security", 0, 0, (unsigned int *)&uBytes, a1);
    if ( Value == 234 || !Value )
    {
      v67 = (unsigned __int8 *)LocalAlloc(0, (unsigned int)uBytes);
      v66 = (PSECURITY_DESCRIPTOR *)(v19 + 192);
      *(_QWORD *)(v19 + 192) = v67;
      if ( !v67 )
        goto LABEL_181;
      if ( !SplRegQueryValue(hKey, L"Security", 0, v67, (unsigned int *)&uBytes, a1) )
      {
        *(_DWORD *)v110 = 0;
        v111 = 4;
        if ( SplRegQueryValue(hKey, L"ModernPrintingVerified", 0, v110, &v111, a1) || *(_DWORD *)v110 != 2 )
        {
          v122 = 0;
          v112 = 0;
          if ( !ContainsAccessEntriesForAppContainer(*v66, &v122, (int *)&v112) )
          {
            pControl[0] = 0;
            dwRevision = 0;
            if ( GetSecurityDescriptorControl(*v66, pControl, &dwRevision) )
              v68 = pControl[0] & 8;
            else
              v68 = 1;
            v69 = 0;
            *(_OWORD *)v128 = 0;
            if ( !v122 )
            {
              v69 = 1;
              v128[0] = gAppContainerAllAppsSid;
            }
            if ( !v112 )
            {
              v70 = v69++;
              v128[v70] = gLPACCapabilitySid;
            }
            if ( !FixPrinterSecurityDescriptor((void **)(v19 + 192), v128, v69, 0x20008u, v68) )
            {
              SecurityDescriptorLength = GetSecurityDescriptorLength(*v66);
              RegSetBinaryData(hKey, L"Security", *v66, SecurityDescriptorLength, &v112, a1);
            }
          }
          *(_DWORD *)v110 = 2;
          v111 = 4;
          SplRegSetValue(hKey, L"ModernPrintingVerified", 4u, v110, 4u, a1);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl)
          && (SplRegQueryValue(hKey, L"WindowsProtectedPrintSupportVerified", 0, v110, &v111, a1) || *(_DWORD *)v110 != 1) )
        {
          if ( !ContainsAccessEntriesForRestrictedSpoolerWorker(*v66) )
          {
            dwRevision = 0;
            pControl[0] = 0;
            v72 = GetSecurityDescriptorControl(*v66, pControl, &dwRevision) ? pControl[0] & 8 : 1;
            if ( !FixPrinterSecurityDescriptor((void **)(v19 + 192), &gRestrictedSpoolerServiceSid, 1u, 0xF000Cu, v72) )
            {
              v73 = GetSecurityDescriptorLength(*v66);
              RegSetBinaryData(hKey, L"Security", *v66, v73, &v112, a1);
            }
          }
          *(_DWORD *)v110 = 1;
          v111 = 4;
          SplRegSetValue(hKey, L"WindowsProtectedPrintSupportVerified", 4u, v110, 4u, a1);
        }
        goto LABEL_181;
      }
      LocalFree(*v66);
    }
    else
    {
      v66 = (PSECURITY_DESCRIPTOR *)(v19 + 192);
    }
    *v66 = 0;
LABEL_181:
    v74 = *(_QWORD *)(v19 + 24);
    *(_QWORD *)(v19 + 412) = 0;
    *(_QWORD *)(v19 + 404) = 0;
    *(_DWORD *)(v19 + 400) = -1;
    *(_DWORD *)(v19 + 464) = 0;
    if ( v74
      && *(_QWORD *)(v19 + 40)
      && TokenList
      && *(_QWORD *)(v19 + 312)
      && (v75 = *(_QWORD *)(v19 + 56)) != 0
      && *(_QWORD *)(v19 + 88)
      && *(_QWORD *)(v19 + 144)
      && *(_QWORD *)(v19 + 80)
      && (v66 = (PSECURITY_DESCRIPTOR *)(v19 + 192), *(_QWORD *)(v19 + 192))
      && v45 )
    {
      *(_QWORD *)(v19 + 184) = 0;
      *(_QWORD *)(v19 + 176) = 0;
      SafeIncrementReference((unsigned int *)(v75 + 16));
      v77 = *(_QWORD *)(v19 + 88);
      if ( v77 )
        SafeIncrementReference((unsigned int *)(v77 + 16));
      v78 = *(_DWORD *)(TokenList + 4);
      v79 = v76;
      if ( v78 )
      {
        while ( 1 )
        {
          v80 = *(_QWORD *)(v19 + 312);
          v112 = v76;
          v81 = *(_QWORD *)(TokenList + 8LL * v79 + 8);
          *(_QWORD *)(v80 + 8LL * v79) = v81;
          if ( (int)ULongLongToULong(8LL * *(unsigned int *)(v81 + 84), &v112) < 0 || v112 + 8 < v112 )
            break;
          v83 = ReallocSplMem(*(_QWORD *)(v81 + 88));
          v76 = 0;
          if ( !v83 )
            goto LABEL_199;
          v84 = *(unsigned int *)(v81 + 84);
          *(_QWORD *)(v81 + 88) = v83;
          *(_QWORD *)(v83 + 8 * v84) = v19;
LABEL_200:
          v85 = *(_DWORD *)(v81 + 84);
          *(_DWORD *)(v81 + 84) = v85 + 1;
          if ( !v85 )
          {
            CreateRedirectionThread(v81);
            v76 = 0;
          }
          v78 = *(_DWORD *)(TokenList + 4);
          if ( ++v79 >= v78 )
            goto LABEL_203;
        }
        *(_QWORD *)(v81 + 88) = v82;
LABEL_199:
        LocalSpoolerTelemetry::WriteDbgTraceWarning("BuildPrinterInfo", L"Failed to allocate memory for printer info.");
        v76 = 0;
        goto LABEL_200;
      }
LABEL_203:
      v86 = *v54 == v76;
      *(_DWORD *)(v19 + 308) = v78;
      v87 = 1;
      if ( !v86 )
        v87 = *v54;
      *v54 = v87;
      if ( (*(_BYTE *)(v19 + 152) & 3) == 3 )
        _INIPRINTER::ClearAttributesFlags((_INIPRINTER *)v19, 2u);
      if ( (*(_BYTE *)(*(_QWORD *)(v19 + 88) + 200LL) & 2) != 0 )
        _INIPRINTER::ClearAttributesFlags((_INIPRINTER *)v19, 0x1002u);
      v88 = *(_DWORD *)v117;
      v6 = 0;
      if ( *(_DWORD *)v117 )
      {
        v89 = *(_WORD **)(v19 + 24);
        v90 = -1;
        do
          ++v90;
        while ( v89[v90] );
        if ( v90 > 2 )
        {
          if ( *(_DWORD *)(v19 + 308) )
          {
            v91 = *(_WORD **)(**(_QWORD **)(v19 + 312) + 24LL);
            if ( v91 )
            {
              v92 = -1;
              do
                ++v92;
              while ( v91[v92] );
              if ( v92 > 2
                && (*((_DWORD *)a1 + 42) & 0x1000000) != 0
                && *v89 == 92
                && v89[1] == 92
                && *v91 == 92
                && v91[1] == 92
                && (*(_BYTE *)(v19 + 152) & 0x50) == 0 )
              {
                _INIPRINTER::AddAttributesFlags((_INIPRINTER *)v19, 0x50u);
              }
            }
          }
        }
      }
      else if ( HIDWORD(uBytes) && (*(_BYTE *)(v19 + 152) & 0x10) == 0 )
      {
        _INIPRINTER::AddPrinterStatusFlags((_INIPRINTER *)v19, 0x80u);
      }
      v93 = *(unsigned __int16 *)(v19 + 32);
      v94 = *((_QWORD *)a1 + v93 + 49);
      if ( v94 )
      {
        *(_QWORD *)(v19 + 8) = *(_QWORD *)(v94 + 8);
        *(_QWORD *)(*((_QWORD *)a1 + v93 + 49) + 8LL) = v19;
      }
      else
      {
        *(_QWORD *)(v19 + 8) = *((_QWORD *)a1 + 5);
        *((_QWORD *)a1 + 5) = v19;
        *((_QWORD *)a1 + *(unsigned __int16 *)(v19 + 32) + 49) = v19;
      }
      *(_QWORD *)(v19 + 280) = a1;
      if ( v113 )
      {
        UpdatePrinterIni((_INIPRINTER *)v19);
        v113 = v88;
      }
      if ( (*((_DWORD *)a1 + 42) & 0x4000000) != 0 && (*(_BYTE *)(v19 + 136) & 0x30) == 0 )
        SchedulePrintQueueDevnodeCreation((struct _INIPRINTER *)v19, 0);
    }
    else
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "BuildPrinterInfo",
        L"Failed to create print queue %ws on %ws",
        v74,
        *((_QWORD *)a1 + 3));
      FreeStructurePointers(v19, 0, IniPrinterOffsets);
      v6 = 0;
      if ( *v66 )
      {
        LocalFree(*v66);
        *v66 = 0;
      }
      v95 = (void (*)(void))*((_QWORD *)a1 + 24);
      if ( v95 && *(_QWORD *)(v19 + 296) )
        v95();
      if ( *((_DWORD *)a1 + 4) )
        SafeDecrementReference((unsigned int *)a1 + 4);
      DeleteSpoolerCheck(a1);
      DllFreeSplMem(v19);
    }
    FreePortTokenList(TokenList);
    v17 = v123;
    goto LABEL_245;
  }
  LocalSpoolerTelemetry::WriteDbgTraceError(
    "BuildPrinterInfo",
    L"Failed to create DefaultSpoolDirectory %ws. Error %d",
    PathName,
    v13);
  DllFreeSplStr(*v7);
  *v7 = 0;
  v8 = 0;
LABEL_265:
  LocalSpoolerTelemetry::WriteDbgTraceInfo("BuildPrinterInfo", L"Leaving %ws", *((_QWORD *)a1 + 3));
  return v8;
}

```

## disassembly

```asm
0x18007bd7c  push    rbp
0x18007bd7e  push    rbx
0x18007bd7f  push    rsi
0x18007bd80  push    rdi
0x18007bd81  push    r12
0x18007bd83  push    r13
0x18007bd85  push    r14
0x18007bd87  push    r15
0x18007bd89  lea     rbp, [rsp-0AD8h]
0x18007bd91  sub     rsp, 0BD8h
0x18007bd98  mov     rax, cs:__security_cookie
0x18007bd9f  xor     rax, rsp
0x18007bda2  mov     [rbp+0B10h+var_50], rax
0x18007bda9  mov     r8, [rcx+18h]
0x18007bdad  mov     r14d, edx
0x18007bdb0  mov     dword ptr [rbp+0B10h+var_B7C], edx
0x18007bdb3  mov     rsi, rcx
0x18007bdb6  lea     rdx, aEnteringWs; "Entering %ws"
0x18007bdbd  lea     rcx, aBuildprinterin; "BuildPrinterInfo"
0x18007bdc4  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007bdc9  mov     rcx, [rsi+0F0h]; void *
0x18007bdd0  lea     r9, [rbp+0B10h+var_AB0]; unsigned __int8 *
0x18007bdd4  xorps   xmm0, xmm0
0x18007bdd7  mov     qword ptr [rsp+0C10h+FileAttributes], rsi; struct _INISPOOLER *
0x18007bddc  xor     eax, eax
0x18007bdde  mov     [rbp+0B10h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18007bde6  xor     r15d, r15d
0x18007bde9  mov     qword ptr [rbp+0B10h+SecurityAttributes.bInheritHandle], rax
0x18007bded  mov     dword ptr [rbp+0B10h+uBytes+4], eax
0x18007bdf0  lea     rdx, aDefaultspooldi; "DefaultSpoolDirectory"
0x18007bdf7  mov     [rbp+0B10h+var_B8C], eax
0x18007bdfa  lea     rbx, [rsi+60h]
0x18007bdfe  lea     rax, [rsp+0C10h+var_BB0]
0x18007be03  mov     dword ptr [rbp+0B10h+uBytes], r15d
0x18007be07  xor     r8d, r8d; unsigned int *
0x18007be0a  mov     [rsp+0C10h+AllocationSize], rax; unsigned int *
0x18007be0f  mov     [rsp+0C10h+var_BAC], r15d
0x18007be14  mov     [rsp+0C10h+hKey], r15
0x18007be19  movups  xmmword ptr [rbp+0B10h+SecurityAttributes.nLength], xmm0
0x18007be1d  mov     [rsp+0C10h+var_BB0], 208h
0x18007be25  movups  xmmword ptr [rbp+0B10h+ObjectAttributes.Length], xmm0
0x18007be29  mov     word ptr [rbp+0B10h+var_AB0], r15w
0x18007be2e  movups  xmmword ptr [rbp+0B10h+ObjectAttributes.ObjectName], xmm0
0x18007be32  movups  xmmword ptr [rbp+0B10h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007be36  movups  xmmword ptr [rbp+0B10h+IoStatusBlock], xmm0
0x18007be3a  movups  [rbp+0B10h+var_B10], xmm0
0x18007be3e  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18007be43  lea     r12d, [r15+1]
0x18007be47  test    eax, eax
0x18007be49  jnz     short loc_18007BE80
0x18007be4b  lea     rcx, [rbp+0B10h+var_AB0]
0x18007be4f  call    cs:__imp_AllocSplStr
0x18007be55  mov     [rbx], rax
0x18007be58  test    rax, rax
0x18007be5b  jnz     short loc_18007BE7B
0x18007be5d  mov     r8, [rsi+18h]
0x18007be61  lea     rdx, aLeavingWs; "Leaving %ws"
0x18007be68  lea     rcx, aBuildprinterin; "BuildPrinterInfo"
0x18007be6f  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007be74  xor     eax, eax
0x18007be76  jmp     loc_18007D701
0x18007be7b  mov     edi, r15d
0x18007be7e  jmp     short loc_18007BE83
0x18007be80  mov     edi, r12d
0x18007be83  mov     r9d, 104h
0x18007be89  mov     [rsp+0C10h+AllocationSize], rsi
0x18007be8e  lea     r8, [rbp+0B10h+PathName]
0x18007be95  xor     edx, edx
0x18007be97  xor     ecx, ecx
0x18007be99  call    GetPrinterDirectory
0x18007be9e  cmp     [rbx], r15
0x18007bea1  jz      short loc_18007BE5D
0x18007bea3  mov     [rbp+0B10h+SecurityAttributes.nLength], 18h
0x18007beaa  call    ?CreateEverybodySecurityDescriptor@@YAPEAXXZ; CreateEverybodySecurityDescriptor(void)
0x18007beaf  mov     [rbp+0B10h+SecurityAttributes.lpSecurityDescriptor], rax
0x18007beb3  mov     [rbp+0B10h+SecurityAttributes.bInheritHandle], r15d
0x18007beb7  test    rax, rax
0x18007beba  jnz     short loc_18007BECA
0x18007bebc  mov     rcx, [rbx]
0x18007bebf  call    cs:__imp_DllFreeSplStr
0x18007bec5  mov     [rbx], r15
0x18007bec8  jmp     short loc_18007BE5D
0x18007beca  lea     rcx, [rbp+0B10h+PathName]
0x18007bed1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007bed5  inc     rax
0x18007bed8  cmp     [rcx+rax*2], r15w
0x18007bedd  jnz     short loc_18007BED5
0x18007bedf  cmp     rax, 0F8h
0x18007bee5  ja      short loc_18007BF00
0x18007bee7  lea     rdx, [rbp+0B10h+SecurityAttributes]; lpSecurityAttributes
0x18007beeb  lea     rcx, [rbp+0B10h+PathName]; lpPathName
0x18007bef2  call    cs:__imp_CreateDirectoryW
0x18007bef8  test    eax, eax
0x18007befa  jnz     loc_18007BF9B
0x18007bf00  mov     edi, r12d
0x18007bf03  call    cs:__imp_GetLastError
0x18007bf09  mov     r13d, 0B7h
0x18007bf0f  cmp     eax, r13d
0x18007bf12  jz      loc_18007BF9B
0x18007bf18  mov     rcx, [rbx]
0x18007bf1b  call    cs:__imp_DllFreeSplStr
0x18007bf21  lea     r9d, [r13+4Dh]
0x18007bf25  mov     [rbx], r15
0x18007bf28  lea     r8, [rbp+0B10h+PathName]
0x18007bf2f  mov     [rsp+0C10h+AllocationSize], rsi
0x18007bf34  xor     edx, edx
0x18007bf36  xor     ecx, ecx
0x18007bf38  call    GetPrinterDirectory
0x18007bf3d  cmp     [rbx], r15
0x18007bf40  jz      loc_18007BE5D
0x18007bf46  lea     rdx, [rbp+0B10h+SecurityAttributes]; lpSecurityAttributes
0x18007bf4a  lea     rcx, [rbp+0B10h+PathName]; lpPathName
0x18007bf51  call    cs:__imp_CreateDirectoryW
0x18007bf57  test    eax, eax
0x18007bf59  jnz     short loc_18007BF9B
0x18007bf5b  call    cs:__imp_GetLastError
0x18007bf61  test    eax, eax
0x18007bf63  jz      short loc_18007BF9B
0x18007bf65  cmp     eax, r13d
0x18007bf68  jz      short loc_18007BF9B
0x18007bf6a  mov     r9d, eax
0x18007bf6d  lea     r8, [rbp+0B10h+PathName]
0x18007bf74  lea     rdx, aFailedToCreate_2; "Failed to create DefaultSpoolDirectory "...
0x18007bf7b  lea     rcx, aBuildprinterin; "BuildPrinterInfo"
0x18007bf82  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18007bf87  mov     rcx, [rbx]
0x18007bf8a  call    cs:__imp_DllFreeSplStr
0x18007bf90  mov     [rbx], r15
0x18007bf93  mov     r12d, r15d
0x18007bf96  jmp     loc_18007D6E7
0x18007bf9b  mov     rcx, [rbp+0B10h+SecurityAttributes.lpSecurityDescriptor]; hMem
0x18007bf9f  mov     [rbp+0B10h+var_B90], r14d
0x18007bfa3  call    cs:__imp_LocalFree
0x18007bfa9  test    edi, edi
0x18007bfab  jz      short loc_18007BFDB
0x18007bfad  mov     r9, [rbx]
0x18007bfb0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007bfb4  inc     rax
0x18007bfb7  cmp     [r9+rax*2], r15w
0x18007bfbc  jnz     short loc_18007BFB4
0x18007bfbe  lea     eax, ds:2[rax*2]
0x18007bfc5  mov     r8d, r12d
0x18007bfc8  lea     rdx, aDefaultspooldi; "DefaultSpoolDirectory"
0x18007bfcf  mov     dword ptr [rsp+0C10h+AllocationSize], eax
0x18007bfd3  mov     rcx, rsi
0x18007bfd6  call    SetPrinterDataServer
0x18007bfdb  cmp     cs:removeMXDW, r15d
0x18007bfe2  jz      short loc_18007BFEE
0x18007bfe4  xor     edx, edx
0x18007bfe6  mov     rcx, rsi
0x18007bfe9  call    ?RemoveOfflinePrinter@@YAXPEAU_INISPOOLER@@W4RemoveOfflinePrinterType@@@Z; RemoveOfflinePrinter(_INISPOOLER *,RemoveOfflinePrinterType)
0x18007bfee  cmp     cs:removeMPDW, r15d
0x18007bff5  jz      short loc_18007C002
0x18007bff7  mov     edx, r12d
0x18007bffa  mov     rcx, rsi
0x18007bffd  call    ?RemoveOfflinePrinter@@YAXPEAU_INISPOOLER@@W4RemoveOfflinePrinterType@@@Z; RemoveOfflinePrinter(_INISPOOLER *,RemoveOfflinePrinterType)
0x18007c002  mov     rcx, [rsi+0F0h]; void *
0x18007c009  lea     r9, [rsp+0C10h+var_BB0]; unsigned int *
0x18007c00e  mov     ebx, r15d
0x18007c011  mov     qword ptr [rsp+0C10h+FileAttributes], rsi; struct _INISPOOLER *
0x18007c016  lea     r8, [rbp+0B10h+var_480]; unsigned __int16 *
0x18007c01d  mov     [rbp+0B10h+var_B64], ebx
0x18007c020  xor     edx, edx; unsigned int
0x18007c022  mov     [rsp+0C10h+var_BB0], 104h
0x18007c02a  mov     [rsp+0C10h+AllocationSize], r15; struct _FILETIME *
0x18007c02f  call    ?SplRegEnumKey@@YAJPEAXKPEAGPEAKPEAU_FILETIME@@PEAU_INISPOOLER@@@Z; SplRegEnumKey(void *,ulong,ushort *,ulong *,_FILETIME *,_INISPOOLER *)
0x18007c034  mov     r14d, 4
0x18007c03a  jmp     loc_18007D5BB
0x18007c03f  mov     rcx, [rsi+0F0h]; void *
0x18007c046  lea     rax, [rsp+0C10h+hKey]
0x18007c04b  mov     qword ptr [rsp+0C10h+CreateDisposition], rsi; struct _INISPOOLER *
0x18007c050  lea     rdx, [rbp+0B10h+var_480]; unsigned __int16 *
0x18007c057  mov     qword ptr [rsp+0C10h+ShareAccess], r15; unsigned int
0x18007c05c  mov     r9d, 2001Fh; unsigned int
0x18007c062  mov     qword ptr [rsp+0C10h+FileAttributes], rax; void **
0x18007c067  xor     r8d, r8d; unsigned int
0x18007c06a  mov     [rsp+0C10h+AllocationSize], r15; struct _SECURITY_ATTRIBUTES *
0x18007c06f  call    ?SplRegCreateKey@@YAJPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAXPEAKPEAU_INISPOOLER@@@Z; SplRegCreateKey(void *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *,ulong *,_INISPOOLER *)
0x18007c074  test    eax, eax
0x18007c076  jnz     loc_18007D589
0x18007c07c  mov     rcx, [rsp+0C10h+hKey]; void *
0x18007c081  lea     rax, [rsp+0C10h+var_BB0]
0x18007c086  mov     qword ptr [rsp+0C10h+FileAttributes], rsi; struct _INISPOOLER *
0x18007c08b  lea     r9, [rbp+0B10h+var_690]; unsigned __int8 *
0x18007c092  lea     r8, [rsp+0C10h+var_BAC]; unsigned int *
0x18007c097  mov     [rsp+0C10h+AllocationSize], rax; unsigned int *
0x18007c09c  lea     rdx, szDriver; "Printer Driver"
0x18007c0a3  mov     [rsp+0C10h+var_BB0], 208h
0x18007c0ab  mov     word ptr [rbp+0B10h+var_690], r15w
0x18007c0b3  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18007c0b8  test    eax, eax
0x18007c0ba  jnz     loc_18007D579
0x18007c0c0  mov     ecx, 258h
0x18007c0c5  call    cs:__imp_DllAllocSplMem
0x18007c0cb  mov     rdi, rax
0x18007c0ce  test    rax, rax
0x18007c0d1  jz      loc_18007D579
0x18007c0d7  lea     rcx, [rsi+10h]; unsigned int *
0x18007c0db  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18007c0e0  lea     rcx, [rdi+0E8h]; lpSystemTime
0x18007c0e7  mov     dword ptr [rdi], 4951h
0x18007c0ed  call    cs:__imp_GetSystemTime
0x18007c0f3  mov     ecx, cs:dwUniquePrinterSessionID
0x18007c0f9  lea     r9, [rbp+0B10h+var_AB0]; unsigned __int8 *
0x18007c0fd  mov     [rdi+17Ch], ecx
0x18007c103  lea     rdx, szName; unsigned __int16 *
0x18007c10a  mov     qword ptr [rsp+0C10h+FileAttributes], rsi; struct _INISPOOLER *
0x18007c10f  xor     r8d, r8d; unsigned int *
0x18007c112  mov     [rsp+0C10h+var_BB0], 208h
0x18007c11a  lea     eax, [rcx+1]
0x18007c11d  mov     word ptr [rbp+0B10h+var_AB0], r15w
0x18007c122  mov     rcx, [rsp+0C10h+hKey]; void *
0x18007c127  mov     cs:dwUniquePrinterSessionID, eax
0x18007c12d  lea     rax, [rsp+0C10h+var_BB0]
0x18007c132  mov     [rsp+0C10h+AllocationSize], rax; unsigned int *
0x18007c137  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18007c13c  test    eax, eax
0x18007c13e  jnz     short loc_18007C15A
0x18007c140  lea     rcx, [rbp+0B10h+var_AB0]
0x18007c144  call    cs:__imp_AllocSplStr
0x18007c14a  mov     rcx, rax
0x18007c14d  mov     [rdi+18h], rax
0x18007c151  call    HashName
0x18007c156  mov     [rdi+20h], ax
0x18007c15a  mov     rcx, [rsp+0C10h+hKey]; void *
0x18007c15f  lea     rax, [rsp+0C10h+var_BB0]
0x18007c164  mov     qword ptr [rsp+0C10h+FileAttributes], rsi; struct _INISPOOLER *
0x18007c169  lea     r9, [rbp+0B10h+var_AB0]; unsigned __int8 *
0x18007c16d  xor     r8d, r8d; unsigned int *
0x18007c170  mov     [rsp+0C10h+AllocationSize], rax; unsigned int *
0x18007c175  lea     rdx, szPerUserName; "PerUserName"
0x18007c17c  mov     [rsp+0C10h+var_BB0], 208h
0x18007c184  mov     word ptr [rbp+0B10h+var_AB0], r15w
0x18007c189  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18007c18e  test    eax, eax
0x18007c190  jnz     short loc_18007C1A3
0x18007c192  lea     rcx, [rbp+0B10h+var_AB0]
0x18007c196  call    cs:__imp_AllocSplStr
0x18007c19c  mov     [rdi+220h], rax
0x18007c1a3  mov     rcx, [rsp+0C10h+hKey]; void *
0x18007c1a8  lea     rax, [rsp+0C10h+var_BB0]
0x18007c1ad  mov     qword ptr [rsp+0C10h+FileAttributes], rsi; struct _INISPOOLER *
0x18007c1b2  lea     r9, [rbp+0B10h+var_AB0]; unsigned __int8 *
0x18007c1b6  lea     r8, [rsp+0C10h+var_BAC]; unsigned int *
0x18007c1bb  mov     [rsp+0C10h+AllocationSize], rax; unsigned int *
0x18007c1c0  lea     rdx, szSpoolDir; "SpoolDirectory"
0x18007c1c7  mov     [rsp+0C10h+var_BB0], 208h
0x18007c1cf  mov     word ptr [rbp+0B10h+var_AB0], r15w
0x18007c1d4  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18007c1d9  test    eax, eax
0x18007c1db  jnz     short loc_18007C1F5
0x18007c1dd  cmp     word ptr [rbp+0B10h+var_AB0], r15w
0x18007c1e2  jz      short loc_18007C1F5
0x18007c1e4  lea     rcx, [rbp+0B10h+var_AB0]
0x18007c1e8  call    cs:__imp_AllocSplStr
0x18007c1ee  mov     [rdi+0D0h], rax
0x18007c1f5  mov     rcx, [rsp+0C10h+hKey]; void *
0x18007c1fa  lea     rax, [rsp+0C10h+var_BB0]
0x18007c1ff  mov     qword ptr [rsp+0C10h+FileAttributes], rsi; struct _INISPOOLER *
0x18007c204  lea     r9, [rbp+0B10h+var_AB0]; unsigned __int8 *
0x18007c208  lea     r8, [rsp+0C10h+var_BAC]; unsigned int *
0x18007c20d  mov     [rsp+0C10h+AllocationSize], rax; unsigned int *
0x18007c212  lea     rdx, szObjectGUID; "ObjectGUID"
0x18007c219  mov     [rsp+0C10h+var_BB0], 208h
0x18007c221  mov     word ptr [rbp+0B10h+var_AB0], r15w
0x18007c226  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18007c22b  test    eax, eax
0x18007c22d  jnz     short loc_18007C247
0x18007c22f  cmp     word ptr [rbp+0B10h+var_AB0], r15w
0x18007c234  jz      short loc_18007C247
0x18007c236  lea     rcx, [rbp+0B10h+var_AB0]
0x18007c23a  call    cs:__imp_AllocSplStr
0x18007c240  mov     [rdi+150h], rax
0x18007c247  mov     rcx, [rsp+0C10h+hKey]; void *
0x18007c24c  lea     rax, [rsp+0C10h+var_BB0]
0x18007c251  lea     r9, [rdi+158h]; unsigned __int8 *
0x18007c258  mov     qword ptr [rsp+0C10h+FileAttributes], rsi; struct _INISPOOLER *
0x18007c25d  lea     r8, [rsp+0C10h+var_BAC]; unsigned int *
0x18007c262  mov     [rsp+0C10h+AllocationSize], rax; unsigned int *
0x18007c267  lea     rdx, szDsKeyUpdate; "DsKeyUpdate"
0x18007c26e  mov     [rsp+0C10h+var_BB0], r14d
0x18007c273  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18007c278  mov     rcx, [rsp+0C10h+hKey]; void *
0x18007c27d  lea     rax, [rsp+0C10h+var_BB0]
0x18007c282  lea     rbx, [rdi+184h]
0x18007c289  mov     qword ptr [rsp+0C10h+FileAttributes], rsi; struct _INISPOOLER *
0x18007c28e  mov     r9, rbx; unsigned __int8 *
0x18007c291  mov     [rsp+0C10h+AllocationSize], rax; unsigned int *
0x18007c296  lea     r8, [rsp+0C10h+var_BAC]; unsigned int *
0x18007c29b  mov     [rsp+0C10h+var_BB0], r14d
0x18007c2a0  lea     rdx, szDsKeyUpdateForeground; "DsKeyUpdateForeground"
0x18007c2a7  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18007c2ac  test    dword ptr [rsi+0A8h], 4000000h
0x18007c2b6  jnz     short loc_18007C2F8
0x18007c2b8  mov     eax, [rbx]
0x18007c2ba  test    eax, 0E0000000h
0x18007c2bf  jz      short loc_18007C2F1
0x18007c2c1  bt      eax, 1Eh
0x18007c2c5  jnb     short loc_18007C2D0
0x18007c2c7  or      [rdi+174h], r12d
  ... truncated ...
```
