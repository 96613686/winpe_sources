# NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run(void)

- ea: `0x1800b9450`
- end: `0x1800b9a2b`
- name: `?Run@TVerifyWorker@TDriverStore@NPackageInstallLocalspl@@UEAAJXZ`
- size: `1499`
- prototype: `__int64 __fastcall(NPackageInstallLocalspl::TDriverStore::TVerifyWorker *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update`

## callees

- `0x18000d1b8`
- `0x18000edc4`
- `0x180012030`
- `0x180015e28`
- `0x18002315c`
- `0x180029ed0`
- `0x18002f638`
- `0x1800306c4`
- `0x180035ae4`
- `0x18003e984`
- `0x18003ea2c`
- `0x180046650`
- `0x180047330`
- `0x180071eb0`
- `0x1800aba5c`
- `0x1800ad50c`
- `0x1800b93ac`
- `0x1800b9450`
- `0x1800b9bc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b95a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b9664`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b97a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b95a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b9664`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b97a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b95ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b96a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b97fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b95ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b96a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b97fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9985`
- `SPOOLSS!DllFreeSplMem` at `0x1800b9927`
- `SPOOLSS!DllFreeSplMem` at `0x1800b9927`
- `SPOOLSS!DllAllocSplMem` at `0x1800b9542`
- `SPOOLSS!DllAllocSplMem` at `0x1800b9542`

## string_xrefs

- `0x1800b96b1`: `GetDriverPackagePath for '%ws' returned hr: 0x%x`
- `0x1800b96bb`: `NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run`
- `0x1800b9715`: `NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run`
- `0x1800b9821`: `NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run`
- `0x1800b9851`: `NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run`
- `0x1800b99fa`: `NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run`
- `0x1800b9704`: `Regeneration needed for '%ws' because GetDriverPackagePath returned ERROR_FILE_NOT_FOUND`
- `0x1800b984a`: `Regeneration needed for '%ws' because GetDriverPackagePath returned ERROR_NOT_FOUND`
- `0x1800b94af`: `NPackageInstallLocalspl::TDriverStore::RegisterVerifyWorker`
- `0x1800b99d8`: `NPackageInstallLocalspl::TDriverStore::UnregisterVerifyWorker`

## pseudocode

```c
__int64 __fastcall NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run(
        NPackageInstallLocalspl::TDriverStore::TVerifyWorker *this)
{
  __int64 v1; // rax
  NPackageInstallLocalspl::TDriverStore::TVerifyWorker *v2; // r13
  __int64 v3; // rsi
  int v4; // eax
  int v5; // ebx
  unsigned int i; // ebx
  __int64 v7; // r15
  const unsigned __int16 *v8; // r12
  NCoreLibrary *v9; // rcx
  int DriverEnvironment; // edi
  __int64 v11; // rax
  NCoreLibrary *v12; // rcx
  struct _INISPOOLER *v13; // rdx
  NPackageInstallLocalspl::TDriverStore *PrinterDriverStore; // rax
  int v15; // r14d
  NPackageInstallLocalspl::TLinkedDriverEnvironment *v16; // rdi
  unsigned int j; // r13d
  __int64 v18; // rax
  const unsigned __int16 *v19; // rsi
  const unsigned __int16 *v20; // r12
  const unsigned __int16 *v21; // r8
  int DriverPackagePath; // ebx
  int v23; // edx
  unsigned __int16 v24; // si
  NPackageInstallLocalspl::TLinkedDriverEnvironment *v25; // r13
  __int64 v26; // rax
  const unsigned __int16 *v27; // r14
  const unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // rbx
  DWORD LastError; // eax
  DWORD v31; // eax
  int v32; // eax
  int v34; // [rsp+40h] [rbp-C0h]
  unsigned int v35; // [rsp+44h] [rbp-BCh] BYREF
  int LastErrorAsFailHRNoBreak; // [rsp+48h] [rbp-B8h]
  unsigned int v37; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v38; // [rsp+50h] [rbp-B0h]
  unsigned int v39; // [rsp+54h] [rbp-ACh]
  NPackageInstallLocalspl::TLinkedDriverEnvironment *v40; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A0h]
  unsigned int v42; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v44; // [rsp+78h] [rbp-88h]
  NPackageInstallLocalspl::TDriverStore::TVerifyWorker *v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h]
  struct _CORE_PRINTER_DRIVERW v47; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v48[40]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v49[40]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v50[264]; // [rsp+360h] [rbp+260h] BYREF

  v1 = *((_QWORD *)this + 13);
  v2 = this;
  v45 = this;
  v3 = *(_QWORD *)(v1 + 24);
  v46 = v3;
  v4 = NPackageInstallLocalspl::TDriverStore::SetVerifyWorker((struct _INISPOOLER *)v3, 0, this);
  v5 = v4;
  if ( v4 < 0 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::TDriverStore::RegisterVerifyWorker",
      L"Failed hr: 0x%x",
      (unsigned int)v4);
    goto LABEL_57;
  }
  for ( i = 0; ; ++i )
  {
    v39 = i;
    if ( i >= 4 )
      break;
    v7 = 0;
    v43 = 0;
    v35 = 0;
    v37 = 0;
    v8 = (const unsigned __int16 *)(&g_DriverPackageEnvironments)[i];
    v40 = 0;
    v44 = v8;
    if ( !(unsigned int)SplEnumPrinterDrivers(*(_QWORD *)(v3 + 24), (_DWORD)v8, 8, 0, 0, (char)&v35, (char)&v37, v3) )
    {
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v9);
      DriverEnvironment = LastErrorAsFailHRNoBreak;
      if ( (_WORD)LastErrorAsFailHRNoBreak != 122 )
        goto LABEL_10;
      v11 = DllAllocSplMem(v35);
      v43 = v11;
      v7 = v11;
      if ( !v11 )
        goto LABEL_54;
      if ( !(unsigned int)SplEnumPrinterDrivers(
                            *(_QWORD *)(v3 + 24),
                            (_DWORD)v8,
                            8,
                            v11,
                            v35,
                            (char)&v35,
                            (char)&v37,
                            v3) )
      {
        DriverEnvironment = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v12);
        LastErrorAsFailHRNoBreak = DriverEnvironment;
LABEL_10:
        if ( DriverEnvironment < 0 )
          goto LABEL_16;
      }
    }
    EnterCriticalSection(&g_PackageLock);
    PrinterDriverStore = NPackageInstallLocalspl::RetrievePrinterDriverStore((NPackageInstallLocalspl *)v3, v13);
    if ( PrinterDriverStore )
    {
      DriverEnvironment = NPackageInstallLocalspl::TDriverStore::GetDriverEnvironment(PrinterDriverStore, v8, &v40);
      LastErrorAsFailHRNoBreak = DriverEnvironment;
    }
    else
    {
      DriverEnvironment = -2147418113;
      LastErrorAsFailHRNoBreak = -2147418113;
    }
    LeaveCriticalSection(&g_PackageLock);
LABEL_16:
    v34 = 0;
    v15 = 0;
    v38 = 0;
    if ( DriverEnvironment >= 0 )
    {
      v16 = v40;
      for ( j = 0; !v15 && j < v37; v38 = j )
      {
        v18 = 200LL * j;
        v41 = v18;
        v19 = *(const unsigned __int16 **)(v18 + v7 + 160);
        if ( v19 )
        {
          v20 = *(const unsigned __int16 **)(v18 + v7 + 176);
          memset_0(v50, 0, 0x208u);
          EnterCriticalSection(&g_PackageLock);
          DriverPackagePath = NPackageInstallLocalspl::TLinkedDriverEnvironment::GetDriverPackagePath(
                                v16,
                                0,
                                v21,
                                v19,
                                v50,
                                0x104u,
                                &v42,
                                1);
          LeaveCriticalSection(&g_PackageLock);
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run",
            L"GetDriverPackagePath for '%ws' returned hr: 0x%x",
            *(_QWORD *)(v41 + v7 + 8),
            (unsigned int)DriverPackagePath);
          if ( DriverPackagePath < 0 || (unsigned int)FileExists(v19) )
          {
            if ( (_WORD)DriverPackagePath == 2 )
            {
              v15 = 1;
              v34 = 1;
              LocalSpoolerTelemetry::WriteDbgTraceInfo(
                "NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run",
                L"Regeneration needed for '%ws' because GetDriverPackagePath returned ERROR_FILE_NOT_FOUND",
                *(_QWORD *)(v41 + v7 + 8));
            }
          }
          else
          {
            v15 = 1;
            v34 = 1;
            DriverPackagePath = NCoreLibrary::HResultFromWin32((NCoreLibrary *)2, v23);
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run",
              L"Regeneration needed for '%ws' because INF does not exist",
              *(_QWORD *)(v41 + v7 + 8));
          }
          if ( DriverPackagePath < 0 )
            goto LABEL_44;
          if ( !v15 )
          {
            if ( v20 )
            {
              v24 = *v20;
              if ( *v20 )
              {
                v25 = v40;
                while ( v24 )
                {
                  v47.CoreDriverGUID.Data1 = 0;
                  memset_0(&v47.CoreDriverGUID.Data2, 0, 0x224u);
                  v26 = -1;
                  do
                    ++v26;
                  while ( v20[v26] );
                  v27 = &v20[v26];
                  v24 = v27[1];
                  *((_WORD *)v27 + 1) = 0;
                  EnterCriticalSection(&g_PackageLock);
                  DriverPackagePath = NPackageInstallLocalspl::TLinkedDriverEnvironment::GetCorePrinterDriverInfo(
                                        v25,
                                        v20,
                                        1u,
                                        &v47);
                  if ( DriverPackagePath >= 0 )
                    DriverPackagePath = NPackageInstallLocalspl::TLinkedDriverEnvironment::GetDriverPackagePath(
                                          v25,
                                          0,
                                          v28,
                                          v47.szPackageID,
                                          v50,
                                          0x104u,
                                          &v42,
                                          1);
                  LeaveCriticalSection(&g_PackageLock);
                  if ( DriverPackagePath < 0 || (unsigned int)FileExists(v47.szPackageID) )
                  {
                    if ( (_WORD)DriverPackagePath == 1168 )
                    {
                      v34 = 1;
                      LocalSpoolerTelemetry::WriteDbgTraceInfo(
                        "NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run",
                        L"Regeneration needed for '%ws' because GetDriverPackagePath returned ERROR_NOT_FOUND",
                        v47.szPackageID);
                    }
                    *((_WORD *)v27 + 1) = v24;
                    v20 = v27 + 1;
                    if ( DriverPackagePath < 0 )
                      break;
                  }
                  else
                  {
                    v34 = 1;
                    LocalSpoolerTelemetry::WriteDbgTraceInfo(
                      "NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run",
                      L"Regeneration needed for '%ws' because INF does not exist",
                      v47.szPackageID);
                    *((_WORD *)v27 + 1) = v24;
                    v20 = v27 + 1;
                  }
                }
                v7 = v43;
                v15 = v34;
                j = v38;
                v16 = v40;
              }
            }
          }
          if ( DriverPackagePath >= 0 )
          {
            v8 = v44;
          }
          else
          {
LABEL_44:
            memset_0(v48, 0, sizeof(v48));
            StringCchPrintfW(v48, 0x28u, L"%u (0x%x)");
            v29 = *(const unsigned __int16 **)(v41 + v7 + 8);
            LastError = GetLastError();
            v8 = v44;
            SplLogEvent(&MSG_VERIFY_PACKAGE_INFORMATION_FOR_DRIVER_FAILED, LastError, v29, v44, v48, 0);
          }
        }
        ++j;
      }
      DriverEnvironment = LastErrorAsFailHRNoBreak;
      v2 = v45;
      v3 = v46;
      i = v39;
    }
    if ( v7 )
      DllFreeSplMem(v7);
    if ( DriverEnvironment >= 0 )
    {
      if ( v15 )
        DriverEnvironment = NPackageInstallLocalspl::TDriverStore::TRegenerateWorker::Add(
                              (NPackageInstallLocalspl::TDriverStore::TVerifyWorker *)((char *)v2 + 112),
                              v8,
                              (struct _INISPOOLER *)v3);
      if ( DriverEnvironment >= 0 )
        continue;
    }
LABEL_54:
    memset_0(v49, 0, sizeof(v49));
    StringCchPrintfW(v49, 0x28u, L"%u (0x%x)");
    v31 = GetLastError();
    SplLogEvent(&MSG_VERIFY_PACKAGE_INFORMATION_FAILED, v31, v8, v49, 0);
    continue;
  }
  v5 = NPackageInstallLocalspl::TDriverStore::TRegenerateWorker::Run((NPackageInstallLocalspl::TDriverStore::TVerifyWorker *)((char *)v2 + 112));
LABEL_57:
  v32 = NPackageInstallLocalspl::TDriverStore::SetVerifyWorker((struct _INISPOOLER *)v3, v2, 0);
  if ( v32 < 0 )
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::TDriverStore::UnregisterVerifyWorker",
      L"Failed hr: 0x%x",
      (unsigned int)v32);
  NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Shutdown(v2);
  if ( v5 < 0 )
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::TDriverStore::TVerifyWorker::Run",
      L"Failed hr: 0x%x",
      (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b9450  push    rbp
0x1800b9452  push    rbx
0x1800b9453  push    rsi
0x1800b9454  push    rdi
0x1800b9455  push    r12
0x1800b9457  push    r13
0x1800b9459  push    r14
0x1800b945b  push    r15
0x1800b945d  lea     rbp, [rsp-488h]
0x1800b9465  sub     rsp, 588h
0x1800b946c  mov     rax, cs:__security_cookie
0x1800b9473  xor     rax, rsp
0x1800b9476  mov     [rbp+4C0h+var_50], rax
0x1800b947d  mov     rax, [rcx+68h]
0x1800b9481  mov     r13, rcx
0x1800b9484  mov     [rbp+4C0h+var_540], rcx
0x1800b9488  mov     r8, rcx; struct NPackageInstallLocalspl::TDriverStore::TVerifyWorker *
0x1800b948b  xor     edx, edx; struct NPackageInstallLocalspl::TDriverStore::TVerifyWorker *
0x1800b948d  mov     rsi, [rax+18h]
0x1800b9491  mov     rcx, rsi; this
0x1800b9494  mov     [rbp+4C0h+var_538], rsi
0x1800b9498  call    ?SetVerifyWorker@TDriverStore@NPackageInstallLocalspl@@CAJPEAU_INISPOOLER@@PEBVTVerifyWorker@12@PEAV412@@Z; NPackageInstallLocalspl::TDriverStore::SetVerifyWorker(_INISPOOLER *,NPackageInstallLocalspl::TDriverStore::TVerifyWorker const *,NPackageInstallLocalspl::TDriverStore::TVerifyWorker *)
0x1800b949d  xor     ecx, ecx
0x1800b949f  mov     ebx, eax
0x1800b94a1  test    eax, eax
0x1800b94a3  jns     short loc_1800B94C0
0x1800b94a5  mov     r8d, eax
0x1800b94a8  lea     rdx, aFailedHr0xX; "Failed hr: 0x%x"
0x1800b94af  lea     rcx, aNpackageinstal_24; "NPackageInstallLocalspl::TDriverStore::"...
0x1800b94b6  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800b94bb  jmp     loc_1800B99BC
0x1800b94c0  mov     ebx, ecx
0x1800b94c2  mov     [rsp+5C0h+var_56C], ebx
0x1800b94c6  cmp     ebx, 4
0x1800b94c9  jnb     loc_1800B99B1
0x1800b94cf  mov     qword ptr [rsp+5C0h+var_588], rsi
0x1800b94d4  lea     r12, ?g_DriverPackageEnvironments@@3PAPEAGA; ushort * near * g_DriverPackageEnvironments
0x1800b94db  mov     eax, ebx
0x1800b94dd  xor     r9d, r9d
0x1800b94e0  mov     r15, rcx
0x1800b94e3  mov     [rsp+5C0h+var_550], rcx
0x1800b94e8  mov     [rsp+5C0h+var_57C], ecx
0x1800b94ec  mov     [rsp+5C0h+var_574], ecx
0x1800b94f0  mov     r12, [r12+rax*8]
0x1800b94f4  lea     r8d, [r9+8]
0x1800b94f8  lea     rax, [rsp+5C0h+var_574]
0x1800b94fd  mov     [rsp+5C0h+var_568], rcx
0x1800b9502  mov     [rsp+5C0h+var_590], rax
0x1800b9507  mov     rdx, r12
0x1800b950a  lea     rax, [rsp+5C0h+var_57C]
0x1800b950f  mov     [rsp+5C0h+var_548], r12
0x1800b9514  mov     qword ptr [rsp+5C0h+var_598], rax
0x1800b9519  mov     dword ptr [rsp+5C0h+var_5A0], ecx
0x1800b951d  mov     rcx, [rsi+18h]
0x1800b9521  call    SplEnumPrinterDrivers
0x1800b9526  xor     r14d, r14d
0x1800b9529  test    eax, eax
0x1800b952b  jnz     short loc_1800B959E
0x1800b952d  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800b9532  mov     [rsp+5C0h+var_578], eax
0x1800b9536  mov     edi, eax
0x1800b9538  cmp     ax, 7Ah ; 'z'
0x1800b953c  jnz     short loc_1800B9598
0x1800b953e  mov     ecx, [rsp+5C0h+var_57C]
0x1800b9542  call    cs:__imp_DllAllocSplMem
0x1800b9548  mov     [rsp+5C0h+var_550], rax
0x1800b954d  mov     r15, rax
0x1800b9550  test    rax, rax
0x1800b9553  jz      short loc_1800B95D0
0x1800b9555  mov     rcx, [rsi+18h]
0x1800b9559  lea     rax, [rsp+5C0h+var_574]
0x1800b955e  mov     qword ptr [rsp+5C0h+var_588], rsi
0x1800b9563  lea     r8d, [r14+8]
0x1800b9567  mov     [rsp+5C0h+var_590], rax
0x1800b956c  mov     r9, r15
0x1800b956f  lea     rax, [rsp+5C0h+var_57C]
0x1800b9574  mov     rdx, r12
0x1800b9577  mov     qword ptr [rsp+5C0h+var_598], rax
0x1800b957c  mov     eax, [rsp+5C0h+var_57C]
0x1800b9580  mov     dword ptr [rsp+5C0h+var_5A0], eax
0x1800b9584  call    SplEnumPrinterDrivers
0x1800b9589  test    eax, eax
0x1800b958b  jnz     short loc_1800B959E
0x1800b958d  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800b9592  mov     edi, eax
0x1800b9594  mov     [rsp+5C0h+var_578], eax
0x1800b9598  xor     ecx, ecx
0x1800b959a  test    edi, edi
0x1800b959c  js      short loc_1800B95F2
0x1800b959e  lea     rcx, ?g_PackageLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b95a5  call    cs:__imp_EnterCriticalSection
0x1800b95ab  mov     rcx, rsi; this
0x1800b95ae  call    ?RetrievePrinterDriverStore@NPackageInstallLocalspl@@YAPEAVTDriverStore@1@PEAU_INISPOOLER@@@Z; NPackageInstallLocalspl::RetrievePrinterDriverStore(_INISPOOLER *)
0x1800b95b3  test    rax, rax
0x1800b95b6  jz      short loc_1800B95DA
0x1800b95b8  lea     r8, [rsp+5C0h+var_568]; struct NPackageInstallLocalspl::TLinkedDriverEnvironment **
0x1800b95bd  mov     rdx, r12; unsigned __int16 *
0x1800b95c0  mov     rcx, rax; this
0x1800b95c3  call    ?GetDriverEnvironment@TDriverStore@NPackageInstallLocalspl@@QEAAJPEBGPEAPEAVTLinkedDriverEnvironment@2@@Z; NPackageInstallLocalspl::TDriverStore::GetDriverEnvironment(ushort const *,NPackageInstallLocalspl::TLinkedDriverEnvironment * *)
0x1800b95c8  mov     edi, eax
0x1800b95ca  mov     [rsp+5C0h+var_578], eax
0x1800b95ce  jmp     short loc_1800B95E3
0x1800b95d0  mov     edi, 8007000Eh
0x1800b95d5  jmp     loc_1800B9952
0x1800b95da  mov     edi, 8000FFFFh
0x1800b95df  mov     [rsp+5C0h+var_578], edi
0x1800b95e3  lea     rcx, ?g_PackageLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b95ea  call    cs:__imp_LeaveCriticalSection
0x1800b95f0  xor     ecx, ecx
0x1800b95f2  mov     [rsp+5C0h+var_580], ecx
0x1800b95f6  mov     r14d, ecx
0x1800b95f9  mov     [rsp+5C0h+var_570], ecx
0x1800b95fd  test    edi, edi
0x1800b95ff  js      loc_1800B991F
0x1800b9605  mov     rdi, [rsp+5C0h+var_568]
0x1800b960a  mov     r13d, ecx
0x1800b960d  test    r14d, r14d
0x1800b9610  jnz     loc_1800B990F
0x1800b9616  cmp     r13d, [rsp+5C0h+var_574]
0x1800b961b  jnb     loc_1800B990F
0x1800b9621  mov     eax, r13d
0x1800b9624  imul    rax, 0C8h
0x1800b962b  mov     [rsp+5C0h+var_560], rax
0x1800b9630  mov     rsi, [rax+r15+0A0h]
0x1800b9638  test    rsi, rsi
0x1800b963b  jz      loc_1800B9902
0x1800b9641  mov     r12, [rax+r15+0B0h]
0x1800b9649  lea     rcx, [rbp+4C0h+var_260]; void *
0x1800b9650  xor     edx, edx; Val
0x1800b9652  mov     r8d, 208h; Size
0x1800b9658  call    memset_0
0x1800b965d  lea     rcx, ?g_PackageLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b9664  call    cs:__imp_EnterCriticalSection
0x1800b966a  mov     [rsp+5C0h+var_588], 1; int
0x1800b9672  lea     rax, [rsp+5C0h+var_558]
0x1800b9677  mov     [rsp+5C0h+var_590], rax; unsigned int *
0x1800b967c  mov     r9, rsi; unsigned __int16 *
0x1800b967f  lea     rax, [rbp+4C0h+var_260]
0x1800b9686  mov     [rsp+5C0h+var_598], 104h; unsigned int
0x1800b968e  xor     edx, edx; unsigned __int16 *
0x1800b9690  mov     [rsp+5C0h+var_5A0], rax; unsigned __int16 *
0x1800b9695  mov     rcx, rdi; this
0x1800b9698  call    ?GetDriverPackagePath@TLinkedDriverEnvironment@NPackageInstallLocalspl@@QEAAJPEBG00PEAGKPEAKH@Z; NPackageInstallLocalspl::TLinkedDriverEnvironment::GetDriverPackagePath(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *,int)
0x1800b969d  lea     rcx, ?g_PackageLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b96a4  mov     ebx, eax
0x1800b96a6  call    cs:__imp_LeaveCriticalSection
0x1800b96ac  mov     r8, [rsp+5C0h+var_560]
0x1800b96b1  lea     rdx, aGetdriverpacka; "GetDriverPackagePath for '%ws' returned"...
0x1800b96b8  mov     r9d, ebx
0x1800b96bb  lea     rcx, aNpackageinstal_23; "NPackageInstallLocalspl::TDriverStore::"...
0x1800b96c2  mov     r8, [r8+r15+8]
0x1800b96c7  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800b96cc  test    ebx, ebx
0x1800b96ce  js      short loc_1800B96F8
0x1800b96d0  mov     rcx, rsi
0x1800b96d3  call    FileExists
0x1800b96d8  test    eax, eax
0x1800b96da  jnz     short loc_1800B96F8
0x1800b96dc  lea     r14d, [rax+1]
0x1800b96e0  lea     ecx, [rax+2]; this
0x1800b96e3  mov     [rsp+5C0h+var_580], r14d
0x1800b96e8  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x1800b96ed  mov     ebx, eax
0x1800b96ef  lea     rdx, aRegenerationNe; "Regeneration needed for '%ws' because I"...
0x1800b96f6  jmp     short loc_1800B9710
0x1800b96f8  cmp     bx, 2
0x1800b96fc  jnz     short loc_1800B9726
0x1800b96fe  mov     r14d, 1
0x1800b9704  lea     rdx, aRegenerationNe_1; "Regeneration needed for '%ws' because G"...
0x1800b970b  mov     [rsp+5C0h+var_580], r14d
0x1800b9710  mov     rax, [rsp+5C0h+var_560]
0x1800b9715  lea     rcx, aNpackageinstal_23; "NPackageInstallLocalspl::TDriverStore::"...
0x1800b971c  mov     r8, [rax+r15+8]
0x1800b9721  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800b9726  xor     ecx, ecx
0x1800b9728  test    ebx, ebx
0x1800b972a  js      loc_1800B9888
0x1800b9730  test    r14d, r14d
0x1800b9733  jnz     loc_1800B9884
0x1800b9739  test    r12, r12
0x1800b973c  jz      loc_1800B9884
0x1800b9742  movzx   esi, word ptr [r12]
0x1800b9747  test    si, si
0x1800b974a  jz      loc_1800B9884
0x1800b9750  mov     r13, [rsp+5C0h+var_568]
0x1800b9755  lea     edi, [rcx+1]
0x1800b9758  xor     r15d, r15d
0x1800b975b  test    si, si
0x1800b975e  jz      loc_1800B986E
0x1800b9764  xor     edx, edx; Val
0x1800b9766  mov     [rbp+4C0h+var_530.CoreDriverGUID.Data1], r15d
0x1800b976a  mov     r8d, 224h; Size
0x1800b9770  lea     rcx, [rbp+4C0h+var_530.CoreDriverGUID.Data2]; void *
0x1800b9774  call    memset_0
0x1800b9779  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b977d  inc     rax
0x1800b9780  cmp     [r12+rax*2], r15w
0x1800b9785  jnz     short loc_1800B977D
0x1800b9787  lea     r14, [r12+rax*2]
0x1800b978b  movzx   esi, word ptr [r14+2]
0x1800b9790  mov     [r14+2], r15w
0x1800b9795  test    ebx, ebx
0x1800b9797  js      loc_1800B983B
0x1800b979d  lea     rcx, ?g_PackageLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b97a4  call    cs:__imp_EnterCriticalSection
0x1800b97aa  lea     r9, [rbp+4C0h+var_530]; struct _CORE_PRINTER_DRIVERW *
0x1800b97ae  mov     r8d, edi; unsigned int
0x1800b97b1  mov     rdx, r12; unsigned __int16 *
0x1800b97b4  mov     rcx, r13; this
0x1800b97b7  call    ?GetCorePrinterDriverInfo@TLinkedDriverEnvironment@NPackageInstallLocalspl@@QEAAJPEBGKPEAU_CORE_PRINTER_DRIVERW@@@Z; NPackageInstallLocalspl::TLinkedDriverEnvironment::GetCorePrinterDriverInfo(ushort const *,ulong,_CORE_PRINTER_DRIVERW *)
0x1800b97bc  mov     ebx, eax
0x1800b97be  test    eax, eax
0x1800b97c0  js      short loc_1800B97F4
0x1800b97c2  mov     [rsp+5C0h+var_588], edi; int
0x1800b97c6  lea     rax, [rsp+5C0h+var_558]
0x1800b97cb  mov     [rsp+5C0h+var_590], rax; unsigned int *
0x1800b97d0  lea     r9, [rbp+4C0h+var_530.szPackageID]; unsigned __int16 *
0x1800b97d4  lea     rax, [rbp+4C0h+var_260]
0x1800b97db  mov     [rsp+5C0h+var_598], 104h; unsigned int
0x1800b97e3  xor     edx, edx; unsigned __int16 *
0x1800b97e5  mov     [rsp+5C0h+var_5A0], rax; unsigned __int16 *
0x1800b97ea  mov     rcx, r13; this
0x1800b97ed  call    ?GetDriverPackagePath@TLinkedDriverEnvironment@NPackageInstallLocalspl@@QEAAJPEBG00PEAGKPEAKH@Z; NPackageInstallLocalspl::TLinkedDriverEnvironment::GetDriverPackagePath(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *,int)
0x1800b97f2  mov     ebx, eax
0x1800b97f4  lea     rcx, ?g_PackageLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b97fb  call    cs:__imp_LeaveCriticalSection
0x1800b9801  test    ebx, ebx
0x1800b9803  js      short loc_1800B983B
0x1800b9805  lea     rcx, [rbp+4C0h+var_530.szPackageID]
0x1800b9809  call    FileExists
0x1800b980e  test    eax, eax
0x1800b9810  jnz     short loc_1800B983B
0x1800b9812  lea     r8, [rbp+4C0h+var_530.szPackageID]
0x1800b9816  mov     [rsp+5C0h+var_580], edi
0x1800b981a  lea     rdx, aRegenerationNe; "Regeneration needed for '%ws' because I"...
0x1800b9821  lea     rcx, aNpackageinstal_23; "NPackageInstallLocalspl::TDriverStore::"...
0x1800b9828  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800b982d  mov     [r14+2], si
0x1800b9832  lea     r12, [r14+2]
0x1800b9836  jmp     loc_1800B975B
0x1800b983b  cmp     bx, 490h
0x1800b9840  jnz     short loc_1800B985D
0x1800b9842  lea     r8, [rbp+4C0h+var_530.szPackageID]
0x1800b9846  mov     [rsp+5C0h+var_580], edi
0x1800b984a  lea     rdx, aRegenerationNe_0; "Regeneration needed for '%ws' because G"...
0x1800b9851  lea     rcx, aNpackageinstal_23; "NPackageInstallLocalspl::TDriverStore::"...
0x1800b9858  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800b985d  mov     [r14+2], si
0x1800b9862  lea     r12, [r14+2]
0x1800b9866  test    ebx, ebx
0x1800b9868  jns     loc_1800B975B
0x1800b986e  mov     r15, [rsp+5C0h+var_550]
0x1800b9873  xor     ecx, ecx
0x1800b9875  mov     r14d, [rsp+5C0h+var_580]
0x1800b987a  mov     r13d, [rsp+5C0h+var_570]
0x1800b987f  mov     rdi, [rsp+5C0h+var_568]
0x1800b9884  test    ebx, ebx
0x1800b9886  jns     short loc_1800B98FD
0x1800b9888  xor     edx, edx; Val
0x1800b988a  lea     rcx, [rbp+4C0h+var_300]; void *
0x1800b9891  lea     r8d, [rdx+50h]; Size
0x1800b9895  call    memset_0
0x1800b989a  movzx   r9d, bx
0x1800b989e  lea     r8, aU0xX; "%u (0x%x)"
0x1800b98a5  mov     edx, 28h ; '('; unsigned __int64
0x1800b98aa  mov     dword ptr [rsp+5C0h+var_5A0], r9d
0x1800b98af  lea     rcx, [rbp+4C0h+var_300]; unsigned __int16 *
0x1800b98b6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b98bb  mov     rax, [rsp+5C0h+var_560]
0x1800b98c0  mov     rbx, [rax+r15+8]
0x1800b98c5  call    cs:__imp_GetLastError
0x1800b98cb  mov     r12, [rsp+5C0h+var_548]
0x1800b98d0  lea     rcx, [rbp+4C0h+var_300]
0x1800b98d7  mov     qword ptr [rsp+5C0h+var_598], 0
0x1800b98e0  mov     r9, r12
0x1800b98e3  mov     [rsp+5C0h+var_5A0], rcx
0x1800b98e8  mov     r8, rbx; unsigned __int16 *
0x1800b98eb  lea     rcx, MSG_VERIFY_PACKAGE_INFORMATION_FOR_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x1800b98f2  mov     edx, eax; unsigned int
0x1800b98f4  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800b98f9  xor     ecx, ecx
0x1800b98fb  jmp     short loc_1800B9902
0x1800b98fd  mov     r12, [rsp+5C0h+var_548]
0x1800b9902  inc     r13d
0x1800b9905  mov     [rsp+5C0h+var_570], r13d
0x1800b990a  jmp     loc_1800B960D
0x1800b990f  mov     edi, [rsp+5C0h+var_578]
0x1800b9913  mov     r13, [rbp+4C0h+var_540]
0x1800b9917  mov     rsi, [rbp+4C0h+var_538]
0x1800b991b  mov     ebx, [rsp+5C0h+var_56C]
0x1800b991f  test    r15, r15
0x1800b9922  jz      short loc_1800B992F
0x1800b9924  mov     rcx, r15
0x1800b9927  call    cs:__imp_DllFreeSplMem
0x1800b992d  xor     ecx, ecx
0x1800b992f  test    edi, edi
0x1800b9931  js      short loc_1800B994F
0x1800b9933  test    r14d, r14d
0x1800b9936  jz      short loc_1800B994B
0x1800b9938  lea     rcx, [r13+70h]; this
  ... truncated ...
```
