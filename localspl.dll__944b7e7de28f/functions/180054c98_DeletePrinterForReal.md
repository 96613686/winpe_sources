# DeletePrinterForReal

- ea: `0x180054c98`
- end: `0x180055090`
- name: `DeletePrinterForReal`
- size: `1016`
- prototype: `__int64 __fastcall(struct _INIPRINTER *, int)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002d388`
- `0x180038d84`

## callees

- `0x1800085ac`
- `0x180008730`
- `0x18000beb4`
- `0x180012c54`
- `0x18001905c`
- `0x180019ff8`
- `0x180025938`
- `0x18002595c`
- `0x18002e420`
- `0x180033734`
- `0x180035ae4`
- `0x18003e984`
- `0x18003ea2c`
- `0x180046a5c`
- `0x18004f574`
- `0x180051fa4`
- `0x180052134`
- `0x180053920`
- `0x180054b3c`
- `0x180054b88`
- `0x180054c98`
- `0x180055098`
- `0x18007df54`
- `0x18009bc10`
- `0x1800cceec`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180054e8b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180054e8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055022`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055022`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055042`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055042`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054e77`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054ec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054ec3`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180054e3e`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180054e3e`
- `SPOOLSS!DllFreeSplStr` at `0x180054d26`
- `SPOOLSS!DllFreeSplStr` at `0x180054d26`
- `SPOOLSS!DllFreeSplMem` at `0x180054faf`
- `SPOOLSS!DllFreeSplMem` at `0x180055078`
- `SPOOLSS!DllFreeSplMem` at `0x180054faf`
- `SPOOLSS!DllFreeSplMem` at `0x180055078`

## string_xrefs

- `0x180054cc8`: `DeletePrinterForReal`
- `0x180054eb1`: `DeletePrinterForReal`
- `0x180054f88`: `DeletePrinterForReal`
- `0x180054eaa`: `Skipped warning event MSG_PRINTER_DELETED for TS printer %ws`
- `0x180054f81`: `Failed to create redirected port cleanup threadpool worker for printer %ws.  Error hr: 0x%x`
- `0x180054fcd`: `DeletePrinterForReal`
- `0x180054e54`: `DestroyPrivateObjectSecurity failed.  Error %d`
- `0x180054e5b`: `DeletePrinterSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeletePrinterForReal(struct _INIPRINTER *a1, int a2)
{
  __int64 v4; // rbp
  __int64 v5; // rdx
  unsigned __int16 *PrinterDeviceInstanceId; // rax
  unsigned __int16 *v7; // rbx
  struct _INIPRINTER **v8; // rcx
  struct _INIPRINTER *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned int i; // esi
  __int64 v13; // rax
  __int64 v14; // rbx
  unsigned int j; // ebx
  __int64 v16; // rcx
  BOOL v17; // eax
  DWORD LastError; // eax
  const wchar_t *v19; // rcx
  wchar_t *v20; // rax
  const unsigned __int16 *v21; // rbx
  DWORD v22; // eax
  __int64 v23; // rax
  NThreadingLibrary::TWorkCrew *v24; // rsi
  RedirectedPortCleanupWorkItem *v25; // rax
  struct NThreadingLibrary::TWorkItem *v26; // rbx
  int v27; // eax
  __int64 v28; // rcx
  unsigned int v29; // ebx
  __int64 v30; // rcx
  unsigned int *v31; // rcx
  struct NThreadingLibrary::TWorkItem *v33; // [rsp+80h] [rbp+8h] BYREF

  v4 = *((_QWORD *)a1 + 35);
  v5 = *((_QWORD *)a1 + 3);
  if ( v5 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "DeletePrinterForReal",
      L"Deleting printer %ws for real",
      *((_QWORD *)a1 + 3));
    v5 = *((_QWORD *)a1 + 3);
  }
  if ( (*((_DWORD *)a1 + 38) & 0x400000) != 0 )
    v5 = *((_QWORD *)a1 + 68);
  CheckAndUpdatePrinterRegAll(v4, v5, 0, 1, 0, *((_DWORD *)a1 + 38) & 0x400000, 0);
  PrinterDeviceInstanceId = GetPrinterDeviceInstanceId(a1);
  v7 = PrinterDeviceInstanceId;
  if ( PrinterDeviceInstanceId )
  {
    DeletePrinterDevNode(PrinterDeviceInstanceId);
    DllFreeSplStr(v7);
  }
  DeletePrinterIni(a1);
  v8 = (struct _INIPRINTER **)(v4 + 40);
  v9 = *(struct _INIPRINTER **)(v4 + 40);
  if ( v9 )
  {
    do
    {
      if ( v9 == a1 )
        break;
      v8 = (struct _INIPRINTER **)((char *)*v8 + 8);
      v9 = *v8;
    }
    while ( *v8 );
    if ( *v8 )
      *v8 = (struct _INIPRINTER *)*((_QWORD *)a1 + 1);
  }
  RemoveFromHashBuckets(v4 + 392, a1, *((unsigned __int16 *)a1 + 16));
  v10 = *((_QWORD *)a1 + 7);
  if ( v10 )
    SafeDecrementReference((unsigned int *)(v10 + 16));
  v11 = *((_QWORD *)a1 + 11);
  if ( v11 && *(_DWORD *)(v11 + 16) )
    SafeDecrementReference((unsigned int *)(v11 + 16));
  for ( i = 0; i < *((_DWORD *)a1 + 77); ++i )
  {
    v13 = *((_QWORD *)a1 + 39);
    v14 = *(_QWORD *)(v13 + 8LL * i);
    if ( a2 && !*(_DWORD *)(v14 + 84) && !*(_QWORD *)(v14 + 96) )
      DeletePortEntry(*(_QWORD *)(v13 + 8LL * i));
    RemovePrinterFromPort(a1, (struct _INIPORT *)v14);
  }
  CloseMonitorsRestartOrphanJobs(a1);
  if ( !a2 )
    CleanupOfflineWSDPorts(a1);
  if ( (*(_DWORD *)(v4 + 168) & 0x4000000) != 0 )
  {
    for ( j = 0; j < *((_DWORD *)a1 + 77); ++j )
    {
      v16 = *(_QWORD *)(*((_QWORD *)a1 + 39) + 8LL * (int)j);
      if ( !*(_DWORD *)(v16 + 84) )
        DeletePortEntry(v16);
    }
  }
  v17 = DestroyPrivateObjectSecurity((PSECURITY_DESCRIPTOR *)a1 + 24);
  *((_QWORD *)a1 + 24) = 0;
  if ( !v17 )
  {
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "DeletePrinterSecurity",
      L"DestroyPrivateObjectSecurity failed.  Error %d",
      LastError);
  }
  if ( *((_DWORD *)a1 + 116) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 424));
  v19 = (const wchar_t *)*((_QWORD *)a1 + 3);
  if ( v19 )
  {
    v20 = wcsrchr(v19, 0x2Cu);
    if ( v20 )
      *v20 = 0;
    if ( (*((_DWORD *)a1 + 38) & 0x8000) != 0 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "DeletePrinterForReal",
        L"Skipped warning event MSG_PRINTER_DELETED for TS printer %ws",
        *((_QWORD *)a1 + 3));
    }
    else
    {
      v21 = (const unsigned __int16 *)*((_QWORD *)a1 + 3);
      v22 = GetLastError();
      SplLogEvent(&MSG_PRINTER_DELETED, v22, v21, 0);
    }
  }
  v23 = *((_QWORD *)a1 + 21);
  if ( v23 && *(_QWORD *)(v23 + 24) )
    DeleteIniNetPort(a1);
  if ( *((_DWORD *)a1 + 134) && *((_DWORD *)a1 + 77) == 1 )
  {
    v24 = g_pWorkCrew;
    v33 = 0;
    v25 = (RedirectedPortCleanupWorkItem *)operator new(0x70u);
    v26 = RedirectedPortCleanupWorkItem::RedirectedPortCleanupWorkItem(
            v25,
            *(const unsigned __int16 **)(**((_QWORD **)a1 + 39) + 24LL));
    NCoreLibrary::TGenericSP<NPackageInstallLocalspl::TDriverStore::TVerifyWorker,NCoreLibrary::TRefPtrCOM<NPackageInstallLocalspl::TDriverStore::TVerifyWorker>,NPackageInstallLocalspl::TDriverStore::TVerifyWorker *,0,NPackageInstallLocalspl::TDriverStore::TVerifyWorker const *>::Reset(&v33);
    v33 = v26;
    if ( (*(int (__fastcall **)(struct NThreadingLibrary::TWorkItem *))(*(_QWORD *)v26 + 16LL))(v26) >= 0 )
    {
      v27 = NThreadingLibrary::TWorkCrew::AddItem(v24, v26);
      if ( v27 < 0 )
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "DeletePrinterForReal",
          L"Failed to create redirected port cleanup threadpool worker for printer %ws.  Error hr: 0x%x",
          *((_QWORD *)a1 + 3),
          (unsigned int)v27);
    }
    NCoreLibrary::TGenericSP<NPackageInstallLocalspl::TDriverStore::TVerifyWorker,NCoreLibrary::TRefPtrCOM<NPackageInstallLocalspl::TDriverStore::TVerifyWorker>,NPackageInstallLocalspl::TDriverStore::TVerifyWorker *,0,NPackageInstallLocalspl::TDriverStore::TVerifyWorker const *>::Reset(&v33);
  }
  v28 = *((_QWORD *)a1 + 59);
  if ( v28 )
  {
    DllFreeSplMem(v28);
    *((_QWORD *)a1 + 59) = 0;
  }
  SplLogPrinterEvent(
    &LOCAL_DELPRN_SUCCEEDED,
    L"DeletePrinterForReal",
    0,
    *((const unsigned __int16 **)a1 + 3),
    *((_DWORD *)a1 + 34));
  DeleteDirectoryRecursively(*((unsigned __int16 **)a1 + 61), 1);
  FreeStructurePointers(a1, 0, IniPrinterOffsets);
  if ( *(_QWORD *)(v4 + 192) && *((_QWORD *)a1 + 37) )
  {
    v29 = LeaveSplSemAndResetCount();
    EnterCriticalSection(&RegistryLock);
    (*(void (__fastcall **)(_QWORD))(v4 + 192))(*((_QWORD *)a1 + 37));
    LeaveCriticalSection(&RegistryLock);
    EnterSplSemAndRestoreCount(v29);
  }
  v30 = *((_QWORD *)a1 + 35);
  if ( v30 )
  {
    v31 = (unsigned int *)(v30 + 16);
    if ( *v31 )
      SafeDecrementReference(v31);
    DeleteSpoolerCheck(*((_QWORD *)a1 + 35));
  }
  DllFreeSplMem(a1);
  return 1;
}

```

## disassembly

```asm
0x180054c98  push    rbx
0x180054c9a  push    rbp
0x180054c9b  push    rsi
0x180054c9c  push    rdi
0x180054c9d  push    r14
0x180054c9f  push    r15
0x180054ca1  sub     rsp, 48h
0x180054ca5  mov     r14d, edx
0x180054ca8  mov     rdi, rcx
0x180054cab  mov     rbp, [rcx+118h]
0x180054cb2  mov     rdx, [rcx+18h]
0x180054cb6  xor     r15d, r15d
0x180054cb9  test    rdx, rdx
0x180054cbc  jz      short loc_180054CD8
0x180054cbe  mov     r8, rdx
0x180054cc1  lea     rdx, aDeletingPrinte; "Deleting printer %ws for real"
0x180054cc8  lea     rcx, aDeleteprinterf; "DeletePrinterForReal"
0x180054ccf  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180054cd4  mov     rdx, [rdi+18h]
0x180054cd8  mov     eax, [rdi+98h]
0x180054cde  and     eax, 400000h
0x180054ce3  jz      short loc_180054CEC
0x180054ce5  mov     rdx, [rdi+220h]
0x180054cec  mov     [rsp+78h+var_48], r15
0x180054cf1  mov     [rsp+78h+var_50], eax
0x180054cf5  mov     qword ptr [rsp+78h+var_58], r15
0x180054cfa  mov     r9d, 1
0x180054d00  xor     r8d, r8d
0x180054d03  mov     rcx, rbp
0x180054d06  call    CheckAndUpdatePrinterRegAll
0x180054d0b  mov     rcx, rdi; struct _INIPRINTER *
0x180054d0e  call    ?GetPrinterDeviceInstanceId@@YAPEAGPEAU_INIPRINTER@@@Z; GetPrinterDeviceInstanceId(_INIPRINTER *)
0x180054d13  mov     rbx, rax
0x180054d16  test    rax, rax
0x180054d19  jz      short loc_180054D2C
0x180054d1b  mov     rcx, rax; unsigned __int16 *
0x180054d1e  call    ?DeletePrinterDevNode@@YAHPEAG@Z; DeletePrinterDevNode(ushort *)
0x180054d23  mov     rcx, rbx
0x180054d26  call    cs:__imp_DllFreeSplStr
0x180054d2c  mov     rcx, rdi
0x180054d2f  call    DeletePrinterIni
0x180054d34  lea     rcx, [rbp+28h]
0x180054d38  mov     rax, [rcx]
0x180054d3b  test    rax, rax
0x180054d3e  jz      short loc_180054D60
0x180054d40  cmp     rax, rdi
0x180054d43  jz      short loc_180054D54
0x180054d45  mov     rcx, [rcx]
0x180054d48  add     rcx, 8
0x180054d4c  mov     rax, [rcx]
0x180054d4f  test    rax, rax
0x180054d52  jnz     short loc_180054D40
0x180054d54  cmp     [rcx], r15
0x180054d57  jz      short loc_180054D60
0x180054d59  mov     rax, [rdi+8]
0x180054d5d  mov     [rcx], rax
0x180054d60  lea     rcx, [rbp+188h]
0x180054d67  movzx   r8d, word ptr [rdi+20h]
0x180054d6c  mov     rdx, rdi
0x180054d6f  call    RemoveFromHashBuckets
0x180054d74  mov     rcx, [rdi+38h]
0x180054d78  test    rcx, rcx
0x180054d7b  jz      short loc_180054D86
0x180054d7d  add     rcx, 10h; unsigned int *
0x180054d81  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180054d86  mov     rax, [rdi+58h]
0x180054d8a  test    rax, rax
0x180054d8d  jz      short loc_180054D9D
0x180054d8f  lea     rcx, [rax+10h]; unsigned int *
0x180054d93  cmp     [rcx], r15d
0x180054d96  jz      short loc_180054D9D
0x180054d98  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180054d9d  mov     esi, r15d
0x180054da0  cmp     [rdi+134h], r15d
0x180054da7  jbe     short loc_180054DE4
0x180054da9  mov     ecx, esi
0x180054dab  mov     rax, [rdi+138h]
0x180054db2  mov     rbx, [rax+rcx*8]
0x180054db6  test    r14d, r14d
0x180054db9  jz      short loc_180054DCF
0x180054dbb  cmp     [rbx+54h], r15d
0x180054dbf  jnz     short loc_180054DCF
0x180054dc1  cmp     [rbx+60h], r15
0x180054dc5  jnz     short loc_180054DCF
0x180054dc7  mov     rcx, rbx
0x180054dca  call    DeletePortEntry
0x180054dcf  mov     rdx, rbx; struct _INIPORT *
0x180054dd2  mov     rcx, rdi; struct _INIPRINTER *
0x180054dd5  call    ?RemovePrinterFromPort@@YAXPEAU_INIPRINTER@@PEAU_INIPORT@@@Z; RemovePrinterFromPort(_INIPRINTER *,_INIPORT *)
0x180054dda  inc     esi
0x180054ddc  cmp     esi, [rdi+134h]
0x180054de2  jb      short loc_180054DA9
0x180054de4  mov     rcx, rdi; struct _INIPRINTER *
0x180054de7  call    ?CloseMonitorsRestartOrphanJobs@@YAXPEAU_INIPRINTER@@@Z; CloseMonitorsRestartOrphanJobs(_INIPRINTER *)
0x180054dec  test    r14d, r14d
0x180054def  jnz     short loc_180054DF9
0x180054df1  mov     rcx, rdi; struct _INIPRINTER *
0x180054df4  call    ?CleanupOfflineWSDPorts@@YAXPEAU_INIPRINTER@@@Z; CleanupOfflineWSDPorts(_INIPRINTER *)
0x180054df9  test    dword ptr [rbp+0A8h], 4000000h
0x180054e03  jz      short loc_180054E34
0x180054e05  mov     ebx, r15d
0x180054e08  cmp     [rdi+134h], r15d
0x180054e0f  jbe     short loc_180054E34
0x180054e11  movsxd  rcx, ebx
0x180054e14  mov     rax, [rdi+138h]
0x180054e1b  mov     rcx, [rax+rcx*8]
0x180054e1f  cmp     [rcx+54h], r15d
0x180054e23  jnz     short loc_180054E2A
0x180054e25  call    DeletePortEntry
0x180054e2a  inc     ebx
0x180054e2c  cmp     ebx, [rdi+134h]
0x180054e32  jb      short loc_180054E11
0x180054e34  lea     rbx, [rdi+0C0h]
0x180054e3b  mov     rcx, rbx; ObjectDescriptor
0x180054e3e  call    cs:__imp_DestroyPrivateObjectSecurity
0x180054e44  mov     [rbx], r15
0x180054e47  test    eax, eax
0x180054e49  jnz     short loc_180054E67
0x180054e4b  call    cs:__imp_GetLastError
0x180054e51  mov     r8d, eax
0x180054e54  lea     rdx, aDestroyprivate; "DestroyPrivateObjectSecurity failed.  E"...
0x180054e5b  lea     rcx, aDeleteprinters; "DeletePrinterSecurity"
0x180054e62  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180054e67  cmp     [rdi+1D0h], r15d
0x180054e6e  jz      short loc_180054E7D
0x180054e70  lea     rcx, [rdi+1A8h]; lpCriticalSection
0x180054e77  call    cs:__imp_DeleteCriticalSection
0x180054e7d  mov     rcx, [rdi+18h]; Str
0x180054e81  test    rcx, rcx
0x180054e84  jz      short loc_180054EDD
0x180054e86  mov     edx, 2Ch ; ','; Ch
0x180054e8b  call    cs:__imp_wcsrchr
0x180054e91  test    rax, rax
0x180054e94  jz      short loc_180054E9A
0x180054e96  mov     [rax], r15w
0x180054e9a  test    dword ptr [rdi+98h], 8000h
0x180054ea4  jz      short loc_180054EBF
0x180054ea6  mov     r8, [rdi+18h]
0x180054eaa  lea     rdx, aSkippedWarning; "Skipped warning event MSG_PRINTER_DELET"...
0x180054eb1  lea     rcx, aDeleteprinterf; "DeletePrinterForReal"
0x180054eb8  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180054ebd  jmp     short loc_180054EDD
0x180054ebf  mov     rbx, [rdi+18h]
0x180054ec3  call    cs:__imp_GetLastError
0x180054ec9  xor     r9d, r9d
0x180054ecc  mov     r8, rbx; unsigned __int16 *
0x180054ecf  mov     edx, eax; unsigned int
0x180054ed1  lea     rcx, MSG_PRINTER_DELETED; struct _EVENT_DESCRIPTOR *
0x180054ed8  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x180054edd  mov     rax, [rdi+0A8h]
0x180054ee4  test    rax, rax
0x180054ee7  jz      short loc_180054EF7
0x180054ee9  cmp     [rax+18h], r15
0x180054eed  jz      short loc_180054EF7
0x180054eef  mov     rcx, rdi
0x180054ef2  call    DeleteIniNetPort
0x180054ef7  cmp     [rdi+218h], r15d
0x180054efe  jz      loc_180054FA3
0x180054f04  cmp     dword ptr [rdi+134h], 1
0x180054f0b  jnz     loc_180054FA3
0x180054f11  mov     rsi, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; NThreadingLibrary::TWorkCrew * g_pWorkCrew
0x180054f18  mov     [rsp+78h+arg_0], r15
0x180054f20  mov     ecx, 70h ; 'p'; Size
0x180054f25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054f2a  mov     rcx, rax; this
0x180054f2d  mov     rax, [rdi+138h]
0x180054f34  mov     rdx, [rax]
0x180054f37  mov     rdx, [rdx+18h]; unsigned __int16 *
0x180054f3b  call    ??0RedirectedPortCleanupWorkItem@@QEAA@PEBG@Z; RedirectedPortCleanupWorkItem::RedirectedPortCleanupWorkItem(ushort const *)
0x180054f40  mov     rbx, rax
0x180054f43  lea     rcx, [rsp+78h+arg_0]
0x180054f4b  call    ?Reset@?$TGenericSP@VTVerifyWorker@TDriverStore@NPackageInstallLocalspl@@V?$TRefPtrCOM@VTVerifyWorker@TDriverStore@NPackageInstallLocalspl@@@NCoreLibrary@@PEAV123@$0A@PEBV123@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPackageInstallLocalspl::TDriverStore::TVerifyWorker,NCoreLibrary::TRefPtrCOM<NPackageInstallLocalspl::TDriverStore::TVerifyWorker>,NPackageInstallLocalspl::TDriverStore::TVerifyWorker *,0,NPackageInstallLocalspl::TDriverStore::TVerifyWorker const *>::Reset(void)
0x180054f50  mov     [rsp+78h+arg_0], rbx
0x180054f58  mov     rax, [rbx]
0x180054f5b  mov     rcx, rbx
0x180054f5e  mov     rax, [rax+10h]
0x180054f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f67  test    eax, eax
0x180054f69  js      short loc_180054F95
0x180054f6b  mov     rdx, rbx; struct NThreadingLibrary::TWorkItem *
0x180054f6e  mov     rcx, rsi; this
0x180054f71  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x180054f76  test    eax, eax
0x180054f78  jns     short loc_180054F95
0x180054f7a  mov     r9d, eax
0x180054f7d  mov     r8, [rdi+18h]
0x180054f81  lea     rdx, aFailedToCreate_5; "Failed to create redirected port cleanu"...
0x180054f88  lea     rcx, aDeleteprinterf; "DeletePrinterForReal"
0x180054f8f  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180054f94  nop
0x180054f95  lea     rcx, [rsp+78h+arg_0]
0x180054f9d  call    ?Reset@?$TGenericSP@VTVerifyWorker@TDriverStore@NPackageInstallLocalspl@@V?$TRefPtrCOM@VTVerifyWorker@TDriverStore@NPackageInstallLocalspl@@@NCoreLibrary@@PEAV123@$0A@PEBV123@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPackageInstallLocalspl::TDriverStore::TVerifyWorker,NCoreLibrary::TRefPtrCOM<NPackageInstallLocalspl::TDriverStore::TVerifyWorker>,NPackageInstallLocalspl::TDriverStore::TVerifyWorker *,0,NPackageInstallLocalspl::TDriverStore::TVerifyWorker const *>::Reset(void)
0x180054fa2  nop
0x180054fa3  mov     rcx, [rdi+1D8h]
0x180054faa  test    rcx, rcx
0x180054fad  jz      short loc_180054FBC
0x180054faf  call    cs:__imp_DllFreeSplMem
0x180054fb5  mov     [rdi+1D8h], r15
0x180054fbc  mov     eax, [rdi+88h]
0x180054fc2  mov     [rsp+78h+var_58], eax; unsigned int
0x180054fc6  mov     r9, [rdi+18h]; unsigned __int16 *
0x180054fca  xor     r8d, r8d; unsigned int
0x180054fcd  lea     rdx, aDeleteprinterf_0; "DeletePrinterForReal"
0x180054fd4  lea     rcx, LOCAL_DELPRN_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x180054fdb  call    ?SplLogPrinterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBGK1K@Z; SplLogPrinterEvent(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ushort const *,ulong)
0x180054fe0  mov     edx, 1
0x180054fe5  mov     rcx, [rdi+1E8h]; unsigned __int16 *
0x180054fec  call    DeleteDirectoryRecursively
0x180054ff1  lea     r8, IniPrinterOffsets
0x180054ff8  xor     edx, edx
0x180054ffa  mov     rcx, rdi
0x180054ffd  call    FreeStructurePointers
0x180055002  cmp     [rbp+0C0h], r15
0x180055009  jz      short loc_18005504F
0x18005500b  cmp     [rdi+128h], r15
0x180055012  jz      short loc_18005504F
0x180055014  call    LeaveSplSemAndResetCount
0x180055019  mov     ebx, eax
0x18005501b  lea     rcx, RegistryLock; lpCriticalSection
0x180055022  call    cs:__imp_EnterCriticalSection
0x180055028  mov     rcx, [rdi+128h]
0x18005502f  mov     rax, [rbp+0C0h]
0x180055036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005503b  lea     rcx, RegistryLock; lpCriticalSection
0x180055042  call    cs:__imp_LeaveCriticalSection
0x180055048  mov     ecx, ebx
0x18005504a  call    EnterSplSemAndRestoreCount
0x18005504f  mov     rcx, [rdi+118h]
0x180055056  test    rcx, rcx
0x180055059  jz      short loc_180055075
0x18005505b  add     rcx, 10h; unsigned int *
0x18005505f  cmp     [rcx], r15d
0x180055062  jz      short loc_180055069
0x180055064  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180055069  mov     rcx, [rdi+118h]
0x180055070  call    DeleteSpoolerCheck
0x180055075  mov     rcx, rdi
0x180055078  call    cs:__imp_DllFreeSplMem
0x18005507e  mov     eax, 1
0x180055083  add     rsp, 48h
0x180055087  pop     r15
0x180055089  pop     r14
0x18005508b  pop     rdi
0x18005508c  pop     rsi
0x18005508d  pop     rbp
0x18005508e  pop     rbx
0x18005508f  retn
```
