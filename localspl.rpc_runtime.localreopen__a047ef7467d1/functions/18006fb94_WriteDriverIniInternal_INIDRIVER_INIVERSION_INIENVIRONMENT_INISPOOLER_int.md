# WriteDriverIniInternal(_INIDRIVER *,_INIVERSION *,_INIENVIRONMENT *,_INISPOOLER *,int)

- ea: `0x18006fb94`
- end: `0x1800703f8`
- name: `?WriteDriverIniInternal@@YAHPEAU_INIDRIVER@@PEAU_INIVERSION@@PEAU_INIENVIRONMENT@@PEAU_INISPOOLER@@H@Z`
- size: `2148`
- prototype: `int(struct _INIDRIVER *, struct _INIVERSION *, struct _INIENVIRONMENT *, struct _INISPOOLER *, int)`
- caller_count: `4`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006b71c`
- `0x1800705a0`
- `0x18007e088`
- `0x1800bf1e0`

## callees

- `0x180004efc`
- `0x180005cc0`
- `0x180005d40`
- `0x180008520`
- `0x180008560`
- `0x1800085ac`
- `0x1800086e0`
- `0x180008730`
- `0x180025938`
- `0x18002595c`
- `0x180030fcc`
- `0x18003d0a4`
- `0x18003e984`
- `0x1800419cc`
- `0x180041aa0`
- `0x180042644`
- `0x1800443cc`
- `0x180045010`
- `0x18006fb94`
- `0x18009ef20`
- `0x18009f8ec`
- `0x18009fd60`
- `0x18009fe3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fc26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fc26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007036a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007036a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800703d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800703d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070307`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070332`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007033c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070346`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070307`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070332`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007033c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070346`
- `SPOOLSS!DllFreeSplStr` at `0x18006feb5`
- `SPOOLSS!DllFreeSplStr` at `0x18006feee`
- `SPOOLSS!DllFreeSplStr` at `0x180070243`
- `SPOOLSS!DllFreeSplStr` at `0x18007027f`
- `SPOOLSS!DllFreeSplStr` at `0x1800702be`
- `SPOOLSS!DllFreeSplStr` at `0x1800702fd`
- `SPOOLSS!DllFreeSplStr` at `0x18006feb5`
- `SPOOLSS!DllFreeSplStr` at `0x18006feee`
- `SPOOLSS!DllFreeSplStr` at `0x180070243`
- `SPOOLSS!DllFreeSplStr` at `0x18007027f`
- `SPOOLSS!DllFreeSplStr` at `0x1800702be`
- `SPOOLSS!DllFreeSplStr` at `0x1800702fd`
- `SPOOLSS!DllFreeSplMem` at `0x18007037c`
- `SPOOLSS!DllFreeSplMem` at `0x180070386`
- `SPOOLSS!DllFreeSplMem` at `0x18007038f`
- `SPOOLSS!DllFreeSplMem` at `0x18007037c`
- `SPOOLSS!DllFreeSplMem` at `0x180070386`
- `SPOOLSS!DllFreeSplMem` at `0x18007038f`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006fc96`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006fc96`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18007034f`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18007034f`

## string_xrefs

- `0x18006fdef`: `Dup pDependentFiles = %ws, pIni pDependentFiles = %ws, bUpdateDependentFilesOnly = %d`
- `0x18006fdfa`: `WriteDriverIniInternal`
- `0x18006ffff`: `TempDir`
- `0x18006ff08`: `Configuration File`
- `0x1800701d0`: `LastServicedBuild`

## pseudocode

```c
__int64 __fastcall WriteDriverIniInternal(
        struct _INIDRIVER *a1,
        struct _INIVERSION *a2,
        struct _INIENVIRONMENT *a3,
        struct _INISPOOLER *a4,
        int a5)
{
  struct _INISPOOLER *v6; // rbx
  DWORD Key; // edi
  unsigned int v10; // r12d
  int v11; // eax
  __int64 v12; // rcx
  unsigned __int16 *v13; // rsi
  HANDLE v14; // rax
  void *v15; // r13
  int v16; // edi
  unsigned __int16 *v17; // r8
  const unsigned __int16 *v18; // r9
  void *v19; // rdx
  struct _SECURITY_ATTRIBUTES *v21; // [rsp+20h] [rbp-71h]
  void **v22; // [rsp+28h] [rbp-69h]
  HKEY hKey; // [rsp+40h] [rbp-51h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-49h] BYREF
  HKEY v25; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 *v26; // [rsp+58h] [rbp-39h] BYREF
  __int64 v27; // [rsp+60h] [rbp-31h] BYREF
  __int64 v28; // [rsp+68h] [rbp-29h] BYREF
  __int64 v29; // [rsp+70h] [rbp-21h] BYREF
  __int64 v30; // [rsp+78h] [rbp-19h] BYREF
  HKEY v31; // [rsp+80h] [rbp-11h] BYREF
  HKEY v32; // [rsp+88h] [rbp-9h] BYREF
  HKEY v33; // [rsp+90h] [rbp-1h] BYREF
  __int64 v34; // [rsp+98h] [rbp+7h] BYREF
  _QWORD v35[8]; // [rsp+A0h] [rbp+Fh] BYREF
  struct _INISPOOLER *v36; // [rsp+F0h] [rbp+5Fh] BYREF
  struct _INIENVIRONMENT *v37; // [rsp+100h] [rbp+6Fh]
  unsigned int v38; // [rsp+108h] [rbp+77h]

  v37 = a3;
  v33 = 0;
  v6 = 0;
  v36 = 0;
  v32 = 0;
  v31 = 0;
  Key = 0;
  hKey = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v24 = 0;
  v34 = 0;
  v35[0] = 0;
  v29 = 0;
  v30 = 0;
  if ( a4 )
    SafeIncrementReference((unsigned int *)a4 + 4);
  if ( a1 )
    SafeIncrementReference((unsigned int *)a1 + 4);
  v38 = LeaveSplSemAndResetCount();
  EnterCriticalSection(&RegistryLock);
  EnterSplSem(0);
  v10 = 1;
  v11 = CloneIniDriver(a1, &v24, 1);
  v13 = v24;
  if ( !v11 || !(unsigned int)CloneIniVersion(a2, &v34) || !(unsigned int)CloneIniEnvironment(v37, v35) )
    goto LABEL_37;
  if ( !(unsigned int)CloneIniSpooler(a4) )
  {
    v6 = v36;
LABEL_37:
    v10 = 0;
    LeaveSplSem(v12);
    goto LABEL_38;
  }
  LeaveSplSem(v12);
  v14 = RevertToPrinterSelf();
  v6 = v36;
  v15 = v14;
  Key = SplRegCreateKey(
          (void *)0xFFFFFFFF80000002LL,
          *((const unsigned __int16 **)v36 + 14),
          0,
          0x20006u,
          0,
          (void **)&v33,
          0,
          v36);
  if ( !Key )
  {
    Key = SplRegCreateKey(v33, *(const unsigned __int16 **)(v35[0] + 24LL), 0, 0x20006u, 0, (void **)&v32, 0, v6);
    if ( !Key )
    {
      Key = SplRegCreateKey(v32, L"Drivers", 0, 0x20006u, 0, (void **)&v31, 0, v6);
      if ( !Key )
      {
        Key = SplRegCreateKey(v31, *(const unsigned __int16 **)(v34 + 16), 0, 0x20006u, 0, (void **)&v25, 0, v6);
        if ( !Key )
        {
          LODWORD(v36) = SplRegCreateKey(
                           v25,
                           *((const unsigned __int16 **)v13 + 3),
                           0,
                           0x20006u,
                           0,
                           (void **)&hKey,
                           0,
                           v6);
          Key = (unsigned int)v36;
          if ( !(_DWORD)v36 )
          {
            v16 = a5;
            LODWORD(v21) = a5;
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "WriteDriverIniInternal",
              L"Dup pDependentFiles = %ws, pIni pDependentFiles = %ws, bUpdateDependentFilesOnly = %d",
              *((_QWORD *)v13 + 9),
              *((_QWORD *)a1 + 9),
              v21);
            v17 = (unsigned __int16 *)*((_QWORD *)v13 + 9);
            if ( v17 )
            {
              RegSetMultiString(hKey, L"Dependent Files", v17, (__int64)&v36, v6);
            }
            else
            {
              v18 = (const unsigned __int16 *)*((_QWORD *)v13 + 3);
              v24 = 0;
              v26 = 0;
              SplLogGenericEvent(&LOCAL_ADDDRV_SUCCEEDED, L"Value of Dependent Files is NULL", 0, v18);
              SplLogGenericEvent(&LOCAL_ADDDRV_SUCCEEDED, L"Driver File", 0, *((const unsigned __int16 **)v13 + 4));
              if ( (unsigned int)ConvertDriverVersionToLPWSTR(*((_QWORD *)v13 + 15), &v26, &v36) )
              {
                SplLogGenericEvent(&LOCAL_ADDDRV_SUCCEEDED, L"Driver Version", 0, v26);
                DllFreeSplStr(v26);
              }
              if ( (unsigned int)ConvertDriverDateToLPWSTR(*((_QWORD *)v13 + 14), &v24, &v36) )
              {
                SplLogGenericEvent(&LOCAL_ADDDRV_SUCCEEDED, L"Driver Date", 0, v24);
                DllFreeSplStr(v24);
              }
            }
            if ( !v16 )
            {
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetMultiString(hKey, L"Previous Names", *((unsigned __int16 **)v13 + 13), (__int64)&v36, v6);
              RegSetDWord(
                (_DWORD)hKey,
                (unsigned int)L"Version",
                *((_DWORD *)v13 + 59),
                (unsigned int)&v36,
                (__int64)v6);
              RegSetDWord(
                (_DWORD)hKey,
                (unsigned int)L"TempDir",
                *((_DWORD *)v13 + 60),
                (unsigned int)&v36,
                (__int64)v6);
              RegSetDWord(
                (_DWORD)hKey,
                (unsigned int)L"Attributes",
                *((_DWORD *)v13 + 58),
                (unsigned int)&v36,
                (__int64)v6);
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetMultiString(hKey, L"ColorProfiles", *((unsigned __int16 **)v13 + 23), (__int64)&v36, v6);
              RegSetString(hKey, v6);
              RegSetString(hKey, v6);
              RegSetMultiString(hKey, L"App Registration", *((unsigned __int16 **)v13 + 37), (__int64)&v36, v6);
              NPackageInstallLocalspl::RegSetInfPath(
                (NPackageInstallLocalspl *)hKey,
                v19,
                *((const unsigned __int16 **)v13 + 24),
                (const unsigned __int16 *)&v36,
                (unsigned int *)v6,
                (struct _INISPOOLER *)v22);
              RegSetDWord(
                (_DWORD)hKey,
                (unsigned int)L"PrinterDriverAttributes",
                *((_DWORD *)v13 + 50),
                (unsigned int)&v36,
                (__int64)v6);
              RegSetDWord(
                (_DWORD)hKey,
                (unsigned int)L"LastServicedBuild",
                *((_DWORD *)v13 + 76),
                (unsigned int)&v36,
                (__int64)v6);
              RegSetMultiString(hKey, L"CoreDependencies", *((unsigned __int16 **)v13 + 26), (__int64)&v36, v6);
              if ( (unsigned int)ConvertDriverDateToLPWSTR(*((_QWORD *)v13 + 14), &v27, &v36) )
              {
                RegSetString(hKey, v6);
                DllFreeSplStr(v27);
              }
              if ( (unsigned int)ConvertDriverVersionToLPWSTR(*((_QWORD *)v13 + 15), &v28, &v36) )
              {
                RegSetString(hKey, v6);
                DllFreeSplStr(v28);
              }
              if ( (unsigned int)ConvertDriverDateToLPWSTR(*((_QWORD *)v13 + 27), &v29, &v36) )
              {
                RegSetString(hKey, v6);
                DllFreeSplStr(v29);
              }
              if ( (unsigned int)ConvertDriverVersionToLPWSTR(*((_QWORD *)v13 + 28), &v30, &v36) )
              {
                RegSetString(hKey, v6);
                DllFreeSplStr(v30);
              }
            }
            RegCloseKey(hKey);
            Key = (unsigned int)v36;
            if ( (_DWORD)v36 )
              SplRegDeleteKey(v25, *((const unsigned __int16 **)v13 + 3), v6);
          }
          RegCloseKey(v25);
        }
        RegCloseKey(v31);
      }
      RegCloseKey(v32);
    }
    RegCloseKey(v33);
  }
  ImpersonatePrinterClient(v15);
LABEL_38:
  LeaveCriticalSection(&RegistryLock);
  FreeClonedIniPrintProc(v13);
  DllFreeSplMem(v34);
  DllFreeSplMem(v35[0]);
  DllFreeSplMem(v6);
  EnterSplSemAndRestoreCount(v38);
  if ( a4 )
  {
    if ( *((_DWORD *)a4 + 4) )
      SafeDecrementReference((unsigned int *)a4 + 4);
    DeleteSpoolerCheck(a4);
  }
  if ( a1 && *((_DWORD *)a1 + 4) )
    SafeDecrementReference((unsigned int *)a1 + 4);
  if ( Key )
  {
    SetLastError(Key);
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x18006fb94  mov     [rsp-8+arg_8], rbx
0x18006fb99  mov     [rsp-8+arg_10], r8
0x18006fb9e  push    rbp
0x18006fb9f  push    rsi
0x18006fba0  push    rdi
0x18006fba1  push    r12
0x18006fba3  push    r13
0x18006fba5  push    r14
0x18006fba7  push    r15
0x18006fba9  lea     rbp, [rsp-1Fh]
0x18006fbae  sub     rsp, 0B0h
0x18006fbb5  xor     r10d, r10d
0x18006fbb8  mov     r15, r9
0x18006fbbb  mov     [rbp+4Fh+var_50], r10
0x18006fbbf  mov     ebx, r10d
0x18006fbc2  mov     [rbp+4Fh+arg_0], rbx
0x18006fbc6  mov     r13, rdx
0x18006fbc9  mov     [rbp+4Fh+var_58], r10
0x18006fbcd  mov     r14, rcx
0x18006fbd0  mov     [rbp+4Fh+var_60], r10
0x18006fbd4  mov     edi, r10d
0x18006fbd7  mov     [rbp+4Fh+hKey], r10
0x18006fbdb  mov     [rbp+4Fh+var_90], r10
0x18006fbdf  mov     [rbp+4Fh+var_80], r10
0x18006fbe3  mov     [rbp+4Fh+var_78], r10
0x18006fbe7  mov     [rbp+4Fh+var_98], r10
0x18006fbeb  mov     [rbp+4Fh+var_48], r10
0x18006fbef  mov     [rbp+4Fh+var_40], r10
0x18006fbf3  mov     [rbp+4Fh+var_70], r10
0x18006fbf7  mov     [rbp+4Fh+var_68], r10
0x18006fbfb  test    r9, r9
0x18006fbfe  jz      short loc_18006FC09
0x18006fc00  lea     rcx, [r9+10h]; unsigned int *
0x18006fc04  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18006fc09  test    r14, r14
0x18006fc0c  jz      short loc_18006FC17
0x18006fc0e  lea     rcx, [r14+10h]; unsigned int *
0x18006fc12  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18006fc17  call    LeaveSplSemAndResetCount
0x18006fc1c  lea     rcx, RegistryLock; lpCriticalSection
0x18006fc23  mov     [rbp+4Fh+arg_18], eax
0x18006fc26  call    cs:__imp_EnterCriticalSection
0x18006fc2c  xor     ecx, ecx
0x18006fc2e  call    EnterSplSem
0x18006fc33  mov     r12d, 1
0x18006fc39  lea     rdx, [rbp+4Fh+var_98]
0x18006fc3d  mov     r8d, r12d
0x18006fc40  mov     rcx, r14
0x18006fc43  call    CloneIniDriver
0x18006fc48  mov     rsi, [rbp+4Fh+var_98]
0x18006fc4c  test    eax, eax
0x18006fc4e  jz      loc_18007035B
0x18006fc54  lea     rdx, [rbp+4Fh+var_48]
0x18006fc58  mov     rcx, r13
0x18006fc5b  call    CloneIniVersion
0x18006fc60  test    eax, eax
0x18006fc62  jz      loc_18007035B
0x18006fc68  mov     rcx, [rbp+4Fh+arg_10]
0x18006fc6c  lea     rdx, [rbp+4Fh+var_40]
0x18006fc70  call    CloneIniEnvironment
0x18006fc75  test    eax, eax
0x18006fc77  jz      loc_18007035B
0x18006fc7d  lea     rdx, [rbp+4Fh+arg_0]
0x18006fc81  mov     rcx, r15; Src
0x18006fc84  call    CloneIniSpooler
0x18006fc89  test    eax, eax
0x18006fc8b  jz      loc_180070357
0x18006fc91  call    LeaveSplSem
0x18006fc96  call    cs:__imp_RevertToPrinterSelf
0x18006fc9c  mov     rbx, [rbp+4Fh+arg_0]
0x18006fca0  mov     r9d, 20006h; unsigned int
0x18006fca6  mov     [rsp+0E0h+var_A8], rbx; struct _INISPOOLER *
0x18006fcab  mov     r13, rax
0x18006fcae  lea     rax, [rbp+4Fh+var_50]
0x18006fcb2  mov     [rsp+0E0h+var_B0], rdi; unsigned int *
0x18006fcb7  mov     [rsp+0E0h+var_B8], rax; void **
0x18006fcbc  xor     r8d, r8d; unsigned int
0x18006fcbf  mov     rdx, [rbx+70h]; unsigned __int16 *
0x18006fcc3  mov     rcx, 0FFFFFFFF80000002h; void *
0x18006fcca  mov     [rsp+0E0h+var_C0], rdi; struct _SECURITY_ATTRIBUTES *
0x18006fccf  call    ?SplRegCreateKey@@YAJPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAXPEAKPEAU_INISPOOLER@@@Z; SplRegCreateKey(void *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *,ulong *,_INISPOOLER *)
0x18006fcd4  mov     edi, eax
0x18006fcd6  test    eax, eax
0x18006fcd8  jnz     loc_18007034C
0x18006fcde  mov     rdx, [rbp+4Fh+var_40]
0x18006fce2  lea     rax, [rbp+4Fh+var_58]
0x18006fce6  mov     rcx, [rbp+4Fh+var_50]; void *
0x18006fcea  mov     r9d, 20006h; unsigned int
0x18006fcf0  mov     [rsp+0E0h+var_A8], rbx; struct _INISPOOLER *
0x18006fcf5  xor     r8d, r8d; unsigned int
0x18006fcf8  mov     [rsp+0E0h+var_B0], 0; unsigned int *
0x18006fd01  mov     rdx, [rdx+18h]; unsigned __int16 *
0x18006fd05  mov     [rsp+0E0h+var_B8], rax; void **
0x18006fd0a  mov     [rsp+0E0h+var_C0], 0; struct _SECURITY_ATTRIBUTES *
0x18006fd13  call    ?SplRegCreateKey@@YAJPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAXPEAKPEAU_INISPOOLER@@@Z; SplRegCreateKey(void *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *,ulong *,_INISPOOLER *)
0x18006fd18  mov     edi, eax
0x18006fd1a  test    eax, eax
0x18006fd1c  jnz     loc_180070342
0x18006fd22  mov     rcx, [rbp+4Fh+var_58]; void *
0x18006fd26  lea     rax, [rbp+4Fh+var_60]
0x18006fd2a  mov     [rsp+0E0h+var_A8], rbx; struct _INISPOOLER *
0x18006fd2f  lea     rdx, szDriversKey; "Drivers"
0x18006fd36  mov     [rsp+0E0h+var_B0], 0; unsigned int *
0x18006fd3f  mov     r9d, 20006h; unsigned int
0x18006fd45  mov     [rsp+0E0h+var_B8], rax; void **
0x18006fd4a  xor     r8d, r8d; unsigned int
0x18006fd4d  mov     [rsp+0E0h+var_C0], 0; struct _SECURITY_ATTRIBUTES *
0x18006fd56  call    ?SplRegCreateKey@@YAJPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAXPEAKPEAU_INISPOOLER@@@Z; SplRegCreateKey(void *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *,ulong *,_INISPOOLER *)
0x18006fd5b  mov     edi, eax
0x18006fd5d  test    eax, eax
0x18006fd5f  jnz     loc_180070338
0x18006fd65  mov     rdx, [rbp+4Fh+var_48]
0x18006fd69  lea     rax, [rbp+4Fh+var_90]
0x18006fd6d  mov     rcx, [rbp+4Fh+var_60]; void *
0x18006fd71  mov     r9d, 20006h; unsigned int
0x18006fd77  mov     [rsp+0E0h+var_A8], rbx; struct _INISPOOLER *
0x18006fd7c  xor     r8d, r8d; unsigned int
0x18006fd7f  mov     [rsp+0E0h+var_B0], 0; unsigned int *
0x18006fd88  mov     rdx, [rdx+10h]; unsigned __int16 *
0x18006fd8c  mov     [rsp+0E0h+var_B8], rax; void **
0x18006fd91  mov     [rsp+0E0h+var_C0], 0; struct _SECURITY_ATTRIBUTES *
0x18006fd9a  call    ?SplRegCreateKey@@YAJPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAXPEAKPEAU_INISPOOLER@@@Z; SplRegCreateKey(void *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *,ulong *,_INISPOOLER *)
0x18006fd9f  mov     edi, eax
0x18006fda1  test    eax, eax
0x18006fda3  jnz     loc_18007032E
0x18006fda9  mov     rdx, [rsi+18h]; unsigned __int16 *
0x18006fdad  lea     rax, [rbp+4Fh+hKey]
0x18006fdb1  mov     rcx, [rbp+4Fh+var_90]; void *
0x18006fdb5  mov     r9d, 20006h; unsigned int
0x18006fdbb  mov     [rsp+0E0h+var_A8], rbx; struct _INISPOOLER *
0x18006fdc0  xor     r8d, r8d; unsigned int
0x18006fdc3  mov     [rsp+0E0h+var_B0], 0; unsigned int *
0x18006fdcc  mov     [rsp+0E0h+var_B8], rax; void **
0x18006fdd1  mov     [rsp+0E0h+var_C0], 0; struct _SECURITY_ATTRIBUTES *
0x18006fdda  call    ?SplRegCreateKey@@YAJPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAXPEAKPEAU_INISPOOLER@@@Z; SplRegCreateKey(void *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *,ulong *,_INISPOOLER *)
0x18006fddf  mov     dword ptr [rbp+4Fh+arg_0], eax
0x18006fde2  mov     edi, eax
0x18006fde4  test    eax, eax
0x18006fde6  jnz     loc_180070324
0x18006fdec  mov     edi, [rbp+4Fh+arg_20]
0x18006fdef  lea     rdx, aDupPdependentf; "Dup pDependentFiles = %ws, pIni pDepend"...
0x18006fdf6  mov     r9, [r14+48h]
0x18006fdfa  lea     rcx, aWritedriverini; "WriteDriverIniInternal"
0x18006fe01  mov     r8, [rsi+48h]
0x18006fe05  mov     dword ptr [rsp+0E0h+var_C0], edi
0x18006fe09  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18006fe0e  mov     r8, [rsi+48h]; unsigned __int16 *
0x18006fe12  test    r8, r8
0x18006fe15  jz      short loc_18006FE3E
0x18006fe17  mov     r9d, [r14+40h]
0x18006fe1b  lea     rax, [rbp+4Fh+arg_0]
0x18006fe1f  mov     rcx, [rbp+4Fh+hKey]; void *
0x18006fe23  lea     rdx, szDependentFiles; "Dependent Files"
0x18006fe2a  mov     [rsp+0E0h+var_B8], rbx; struct _INISPOOLER *
0x18006fe2f  mov     [rsp+0E0h+var_C0], rax; __int64
0x18006fe34  call    RegSetMultiString
0x18006fe39  jmp     loc_18006FEF4
0x18006fe3e  mov     r9, [rsi+18h]; unsigned __int16 *
0x18006fe42  lea     rdx, aValueOfDepende; "Value of Dependent Files is NULL"
0x18006fe49  xor     r8d, r8d; unsigned int
0x18006fe4c  mov     [rbp+4Fh+var_98], 0
0x18006fe54  lea     rcx, LOCAL_ADDDRV_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x18006fe5b  mov     [rbp+4Fh+var_88], 0
0x18006fe63  call    ?SplLogGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBGK1@Z; SplLogGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ushort const *)
0x18006fe68  mov     r9, [rsi+20h]; unsigned __int16 *
0x18006fe6c  lea     rdx, aDriverFile; "Driver File"
0x18006fe73  xor     r8d, r8d; unsigned int
0x18006fe76  lea     rcx, LOCAL_ADDDRV_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x18006fe7d  call    ?SplLogGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBGK1@Z; SplLogGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ushort const *)
0x18006fe82  mov     rcx, [rsi+78h]
0x18006fe86  lea     r8, [rbp+4Fh+arg_0]
0x18006fe8a  lea     rdx, [rbp+4Fh+var_88]
0x18006fe8e  call    ConvertDriverVersionToLPWSTR
0x18006fe93  test    eax, eax
0x18006fe95  jz      short loc_18006FEBB
0x18006fe97  mov     r9, [rbp+4Fh+var_88]; unsigned __int16 *
0x18006fe9b  lea     rdx, aDriverVersion; "Driver Version"
0x18006fea2  xor     r8d, r8d; unsigned int
0x18006fea5  lea     rcx, LOCAL_ADDDRV_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x18006feac  call    ?SplLogGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBGK1@Z; SplLogGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ushort const *)
0x18006feb1  mov     rcx, [rbp+4Fh+var_88]
0x18006feb5  call    cs:__imp_DllFreeSplStr
0x18006febb  mov     rcx, [rsi+70h]
0x18006febf  lea     r8, [rbp+4Fh+arg_0]
0x18006fec3  lea     rdx, [rbp+4Fh+var_98]
0x18006fec7  call    ConvertDriverDateToLPWSTR
0x18006fecc  test    eax, eax
0x18006fece  jz      short loc_18006FEF4
0x18006fed0  mov     r9, [rbp+4Fh+var_98]; unsigned __int16 *
0x18006fed4  lea     rdx, aDriverDate; "Driver Date"
0x18006fedb  xor     r8d, r8d; unsigned int
0x18006fede  lea     rcx, LOCAL_ADDDRV_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x18006fee5  call    ?SplLogGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBGK1@Z; SplLogGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ushort const *)
0x18006feea  mov     rcx, [rbp+4Fh+var_98]
0x18006feee  call    cs:__imp_DllFreeSplStr
0x18006fef4  test    edi, edi
0x18006fef6  jnz     loc_180070303
0x18006fefc  mov     r8, [rsi+28h]
0x18006ff00  lea     r9, [rbp+4Fh+arg_0]
0x18006ff04  mov     rcx, [rbp+4Fh+hKey]; void *
0x18006ff08  lea     rdx, szConfigurationKey; "Configuration File"
0x18006ff0f  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x18006ff14  call    RegSetString
0x18006ff19  mov     r8, [rsi+30h]
0x18006ff1d  lea     r9, [rbp+4Fh+arg_0]
0x18006ff21  mov     rcx, [rbp+4Fh+hKey]; void *
0x18006ff25  lea     rdx, szDataFileKey; "Data File"
0x18006ff2c  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x18006ff31  call    RegSetString
0x18006ff36  mov     r8, [rsi+20h]
0x18006ff3a  lea     r9, [rbp+4Fh+arg_0]
0x18006ff3e  mov     rcx, [rbp+4Fh+hKey]; void *
0x18006ff42  lea     rdx, szDriverFile; "Driver"
0x18006ff49  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x18006ff4e  call    RegSetString
0x18006ff53  mov     r8, [rsi+38h]
0x18006ff57  lea     r9, [rbp+4Fh+arg_0]
0x18006ff5b  mov     rcx, [rbp+4Fh+hKey]; void *
0x18006ff5f  lea     rdx, szHelpFile
0x18006ff66  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x18006ff6b  call    RegSetString
0x18006ff70  mov     r8, [rsi+50h]
0x18006ff74  lea     r9, [rbp+4Fh+arg_0]
0x18006ff78  mov     rcx, [rbp+4Fh+hKey]; void *
0x18006ff7c  lea     rdx, szMonitor; "Monitor"
0x18006ff83  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x18006ff88  call    RegSetString
0x18006ff8d  mov     r8, [rsi+58h]
0x18006ff91  lea     r9, [rbp+4Fh+arg_0]
0x18006ff95  mov     rcx, [rbp+4Fh+hKey]; void *
0x18006ff99  lea     rdx, szDatatype; "Datatype"
0x18006ffa0  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x18006ffa5  call    RegSetString
0x18006ffaa  mov     r9d, [r14+60h]
0x18006ffae  lea     rax, [rbp+4Fh+arg_0]
0x18006ffb2  mov     r8, [rsi+68h]; unsigned __int16 *
0x18006ffb6  lea     rdx, szPreviousNames; "Previous Names"
0x18006ffbd  mov     rcx, [rbp+4Fh+hKey]; void *
0x18006ffc1  mov     [rsp+0E0h+var_B8], rbx; struct _INISPOOLER *
0x18006ffc6  mov     [rsp+0E0h+var_C0], rax; __int64
0x18006ffcb  call    RegSetMultiString
0x18006ffd0  mov     r8d, [rsi+0ECh]
0x18006ffd7  lea     r9, [rbp+4Fh+arg_0]
0x18006ffdb  mov     rcx, [rbp+4Fh+hKey]
0x18006ffdf  lea     rdx, szDriverVersion; "Version"
0x18006ffe6  mov     [rsp+0E0h+var_C0], rbx
0x18006ffeb  call    RegSetDWord
0x18006fff0  mov     r8d, [rsi+0F0h]
0x18006fff7  lea     r9, [rbp+4Fh+arg_0]
0x18006fffb  mov     rcx, [rbp+4Fh+hKey]
0x18006ffff  lea     rdx, szTempDir; "TempDir"
0x180070006  mov     [rsp+0E0h+var_C0], rbx
0x18007000b  call    RegSetDWord
0x180070010  mov     r8d, [rsi+0E8h]
0x180070017  lea     r9, [rbp+4Fh+arg_0]
0x18007001b  mov     rcx, [rbp+4Fh+hKey]
0x18007001f  lea     rdx, szAttributes; "Attributes"
0x180070026  mov     [rsp+0E0h+var_C0], rbx
0x18007002b  call    RegSetDWord
0x180070030  mov     r8, [rsi+80h]
0x180070037  lea     r9, [rbp+4Fh+arg_0]
0x18007003b  mov     rcx, [rbp+4Fh+hKey]; void *
0x18007003f  lea     rdx, szMfgName; "Manufacturer"
0x180070046  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x18007004b  call    RegSetString
0x180070050  mov     r8, [rsi+88h]
0x180070057  lea     r9, [rbp+4Fh+arg_0]
0x18007005b  mov     rcx, [rbp+4Fh+hKey]; void *
0x18007005f  lea     rdx, szOEMUrl; "OEM URL"
0x180070066  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x18007006b  call    RegSetString
0x180070070  mov     r8, [rsi+90h]
0x180070077  lea     r9, [rbp+4Fh+arg_0]
0x18007007b  mov     rcx, [rbp+4Fh+hKey]; void *
0x18007007f  lea     rdx, szHardwareID; "HardwareID"
0x180070086  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x18007008b  call    RegSetString
0x180070090  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x180070095  mov     r8, [rsi+98h]
0x18007009c  lea     r9, [rbp+4Fh+arg_0]
0x1800700a0  mov     rcx, [rbp+4Fh+hKey]; void *
0x1800700a4  lea     rdx, szProvider; "Provider"
0x1800700ab  call    RegSetString
0x1800700b0  mov     r8, [rsi+0A0h]
0x1800700b7  lea     r9, [rbp+4Fh+arg_0]
0x1800700bb  mov     rcx, [rbp+4Fh+hKey]; void *
0x1800700bf  lea     rdx, szPrintProcessor; "Print Processor"
0x1800700c6  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x1800700cb  call    RegSetString
0x1800700d0  mov     r8, [rsi+0A8h]
0x1800700d7  lea     r9, [rbp+4Fh+arg_0]
0x1800700db  mov     rcx, [rbp+4Fh+hKey]; void *
0x1800700df  lea     rdx, szVendorSetup; "VendorSetup"
0x1800700e6  mov     [rsp+0E0h+var_C0], rbx; struct _INISPOOLER *
0x1800700eb  call    RegSetString
0x1800700f0  mov     r9d, [r14+0B0h]
0x1800700f7  lea     rax, [rbp+4Fh+arg_0]
0x1800700fb  mov     r8, [rsi+0B8h]; unsigned __int16 *
0x180070102  lea     rdx, szColorProfiles; "ColorProfiles"
0x180070109  mov     rcx, [rbp+4Fh+hKey]; void *
  ... truncated ...
```
