# LdrpInitializeProcess

- ea: `0x1800d6508`
- end: `0x1800d82eb`
- name: `LdrpInitializeProcess`
- size: `7651`
- prototype: ``
- caller_count: `1`
- callee_count: `112`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d5d68`

## callees

- `0x180003850`
- `0x180017e90`
- `0x1800183a0`
- `0x18001861c`
- `0x18001a0d0`
- `0x18001a420`
- `0x18001b984`
- `0x18001eb80`
- `0x18001f070`
- `0x1800254e0`
- `0x1800259fc`
- `0x180025a50`
- `0x180025acc`
- `0x180025d90`
- `0x180025fc4`
- `0x18002631c`
- `0x180026658`
- `0x180029b70`
- `0x18002ad90`
- `0x18002b2a0`
- `0x18002c6f0`
- `0x1800349b0`
- `0x180036e70`
- `0x180040dd4`
- `0x180040eb0`
- `0x18004250c`
- `0x1800469b8`
- `0x18004c620`
- `0x18004c8f0`
- `0x18004cd50`
- `0x180050fa0`
- `0x180051314`
- `0x180051900`
- `0x180053990`
- `0x18005a9f0`
- `0x18005b470`
- `0x18005ede4`
- `0x180066020`
- `0x1800668e0`
- `0x180066d14`
- `0x180066da0`
- `0x180067210`
- `0x1800682dc`
- `0x180068f24`
- `0x1800693a8`
- `0x180069d84`
- `0x18007248c`
- `0x180073210`
- `0x18007324c`
- `0x180074b1c`

## string_xrefs

- `0x1800d65bf`: `\KnownDlls`
- `0x1800d6fa3`: `NTDLL!`
- `0x1800d73be`: `Allocating a buffer to hold the current working directory failed\n`
- `0x1800d731a`: `Querying the known DLL directory link object failed with status 0x%08lx\n`
- `0x1800d7230`: `Failed to open %wZ with status 0x%08lx\n`
- `0x1800d7a80`: `Allocating a data table entry for the application verifier DLL failed\n`
- `0x1800d7a33`: `Initializing the current directory to "%wZ" failed with status 0x%08lx\n`
- `0x1800d7985`: `Beginning execution of %wZ (%wZ)\n	Current directory: %wZ\n	Package directories: %wZ\n`
- `0x1800d7e21`: `DllMain of MSCOREE (or its dependents) failed with status 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall LdrpInitializeProcess(__int64 a1, __int64 a2)
{
  struct _TEB *v3; // r13
  _PEB *ProcessEnvironmentBlock; // rdi
  int v5; // r15d
  bool v6; // cc
  _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rcx
  wchar_t *Buffer; // rdx
  __int16 v9; // bx
  __int64 v10; // r12
  char v11; // bl
  __int64 result; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // ebx
  char v16; // al
  char *Format; // rax
  int v18; // edx
  int v19; // ebx
  __int64 v20; // rdx
  int WowTebOffset; // ecx
  __int64 v22; // rax
  __int64 v23; // r13
  _DWORD *Config; // r15
  __int64 *v25; // rbx
  _BYTE *v26; // rbx
  char v27; // al
  unsigned __int64 v28; // rbx
  char *v29; // rax
  int v30; // edx
  void *ProcessHeap; // r12
  int v32; // ebx
  _RTL_USER_PROCESS_PARAMETERS *v33; // r15
  __int64 NtSystemRoot; // rax
  __int16 v35; // bx
  __int64 Heap_0; // rax
  __int64 v37; // rbx
  int v38; // eax
  __int64 v39; // rax
  __int64 v40; // r15
  int v41; // r13d
  UNICODE_STRING DosPath; // xmm1
  _WORD *v43; // xmm0_8
  wchar_t *v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdx
  char v48; // r12
  unsigned __int64 v49; // rbx
  unsigned __int64 v50; // r15
  __int16 v51; // dx
  __int64 v52; // rcx
  __int64 v53; // rdx
  unsigned __int64 v54; // rcx
  _WORD *v55; // rax
  _WORD *v56; // r8
  __int16 v57; // cx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rax
  int inited; // eax
  __int64 v62; // rax
  __int64 v63; // rcx
  char v64; // r12
  void *ImageBaseAddress; // rcx
  __int64 v66; // rbx
  __int64 v67; // rcx
  __int64 ModuleEntry; // rax
  _QWORD *v69; // rbx
  struct _TEB *v70; // r15
  int v71; // eax
  int v72; // eax
  int v73; // eax
  int v74; // eax
  _DWORD *v75; // r13
  _RTL_USER_PROCESS_PARAMETERS *v76; // rax
  int v77; // eax
  __int64 v78; // rcx
  void (*PostProcessInitRoutine)(void); // rax
  int v85; // eax
  unsigned __int8 IsProcessorFeaturePresent; // al
  const char *i; // rcx
  char ArgList; // [rsp+28h] [rbp-350h]
  __int64 *ArgLista; // [rsp+28h] [rbp-350h]
  char ArgListb; // [rsp+28h] [rbp-350h]
  int ApplicationKeyOption; // [rsp+50h] [rbp-328h] BYREF
  _BYTE v97[4]; // [rsp+54h] [rbp-324h] BYREF
  _RTL_USER_PROCESS_PARAMETERS *v98; // [rsp+58h] [rbp-320h] BYREF
  __int64 v99; // [rsp+60h] [rbp-318h] BYREF
  int v100; // [rsp+68h] [rbp-310h]
  __int64 v101; // [rsp+70h] [rbp-308h] BYREF
  struct _TEB *v102; // [rsp+78h] [rbp-300h] BYREF
  __m128i v103; // [rsp+80h] [rbp-2F8h] BYREF
  HANDLE v104[2]; // [rsp+90h] [rbp-2E8h] BYREF
  __m128i ImagePathName; // [rsp+A0h] [rbp-2D8h] BYREF
  UNICODE_STRING v106; // [rsp+B0h] [rbp-2C8h] BYREF
  __int64 v107; // [rsp+C0h] [rbp-2B8h] BYREF
  HANDLE v108; // [rsp+C8h] [rbp-2B0h] BYREF
  _WORD v109[2]; // [rsp+D0h] [rbp-2A8h] BYREF
  int v110; // [rsp+D4h] [rbp-2A4h]
  __int64 v111; // [rsp+D8h] [rbp-2A0h]
  __int128 v112; // [rsp+E0h] [rbp-298h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+F0h] [rbp-288h] BYREF
  __int64 v114; // [rsp+100h] [rbp-278h]
  HANDLE Handle; // [rsp+108h] [rbp-270h] BYREF
  __int64 v116; // [rsp+110h] [rbp-268h]
  __m128i v117; // [rsp+120h] [rbp-258h] BYREF
  __int128 v118; // [rsp+130h] [rbp-248h] BYREF
  unsigned __int64 v119; // [rsp+140h] [rbp-238h]
  __int64 SystemInformation; // [rsp+148h] [rbp-230h] BYREF
  __int64 v121; // [rsp+150h] [rbp-228h] BYREF
  _DWORD *pShimData; // [rsp+158h] [rbp-220h]
  _QWORD v123[2]; // [rsp+160h] [rbp-218h] BYREF
  _BYTE v124[48]; // [rsp+170h] [rbp-208h] BYREF
  _QWORD v125[2]; // [rsp+1A0h] [rbp-1D8h] BYREF
  __int128 v126; // [rsp+1B0h] [rbp-1C8h]
  __int128 v127; // [rsp+1C0h] [rbp-1B8h]
  __int128 v128; // [rsp+1D0h] [rbp-1A8h]
  __int64 v129; // [rsp+1E0h] [rbp-198h]
  __m128i v130; // [rsp+1F0h] [rbp-188h] BYREF
  _BYTE *v131; // [rsp+200h] [rbp-178h]
  int v132; // [rsp+210h] [rbp-168h]
  int *p_ApplicationKeyOption; // [rsp+218h] [rbp-160h]
  _BYTE v134[128]; // [rsp+2C0h] [rbp-B8h] BYREF

  v114 = a2;
  v116 = a1;
  ApplicationKeyOption = 0;
  UnicodeString = 0;
  ImagePathName = 0;
  v117 = 0;
  v110 = 0;
  v107 = 0;
  v106 = 0;
  v112 = 0;
  v121 = 0;
  Handle = 0;
  memset(v124, 0, 44);
  v123[0] = 1441812;
  v123[1] = L"\\KnownDlls";
  v108 = 0;
  v104[0] = 0;
  v101 = 0;
  memset_thunk_772440563353939046(&v130, 0, 0xD0u);
  v103 = 0;
  memset_thunk_772440563353939046(v134, 0, 0x80u);
  SystemInformation = 0;
  RtlpUnhandledExceptionFilter = RtlEncodePointer(0);
  v3 = NtCurrentTeb();
  v102 = v3;
  ProcessEnvironmentBlock = v3->ProcessEnvironmentBlock;
  LdrpInitializeTeb(v3);
  PebLdr = 88;
  v5 = 1;
  byte_1801CA8C4 = 1;
  qword_1801CA8D8 = (__int64)&qword_1801CA8D0;
  qword_1801CA8D0 = (__int64)&qword_1801CA8D0;
  qword_1801CA8E8 = (__int64)&qword_1801CA8E0;
  qword_1801CA8E0 = (__int64)&qword_1801CA8E0;
  qword_1801CA8F8 = (__int64)&qword_1801CA8F0;
  qword_1801CA8F0 = (__int64)&qword_1801CA8F0;
  byte_1801CA908 = 0;
  qword_1801CA910 = 0;
  ProcessEnvironmentBlock->Ldr = (_PEB_LDR_DATA *)&PebLdr;
  LdrpInitializeNlsInfo(ProcessEnvironmentBlock);
  SRWLockSpinCycleCount = 0;
  v6 = ProcessEnvironmentBlock->NumberOfProcessors <= 1;
  if ( ProcessEnvironmentBlock->NumberOfProcessors > 1 )
    SRWLockSpinCycleCount = 10240;
  ConditionVariableSpinCycleCount = 0;
  if ( !v6 )
    ConditionVariableSpinCycleCount = 10240;
  RtlpWaitOnAddressSpinCycleCount = 0;
  if ( !v6 )
    RtlpWaitOnAddressSpinCycleCount = 10240;
  RtlpInitFeatureConfiguration(1);
  RtlpSrwLockAllowImplicitUpgrade = Feature_Servicing_DisallowSharedLockImplicitUpgrade__private_IsEnabledNoReportingNoInline() == 0;
  RtlpInitializeNonVolatileFlush();
  ProcessParameters = ProcessEnvironmentBlock->ProcessParameters;
  Buffer = (wchar_t *)((char *)ProcessParameters->ImagePathName.Buffer + (unsigned __int64)ProcessParameters);
  if ( (ProcessParameters->Flags & 1) != 0 )
    Buffer = ProcessParameters->ImagePathName.Buffer;
  *((_QWORD *)&v112 + 1) = Buffer;
  LOWORD(v112) = ProcessParameters->ImagePathName.Length;
  v9 = v112;
  WORD1(v112) = v112 + 2;
  if ( (unsigned __int16)v112 >= 8u && *Buffer == 92 && Buffer[1] == 63 && Buffer[2] == 63 && Buffer[3] == 92 )
  {
    LOWORD(v112) = v112 - 8;
    WORD1(v112) = v9 - 6;
    *((_QWORD *)&v112 + 1) = Buffer + 4;
    ProcessParameters->ImagePathName.Length -= 8;
    ProcessParameters->ImagePathName.MaximumLength -= 8;
    ProcessParameters->ImagePathName.Buffer += 4;
  }
  UseCOR = 0;
  LODWORD(v99) = 0;
  RtlImageNtHeaderEx(3, ProcessEnvironmentBlock->ImageBaseAddress, 0, &v107);
  v10 = v107;
  LdrpAppHeaders = v107;
  v11 = LdrpIsSecureProcess;
  if ( LdrpIsSecureProcess && (*(_BYTE *)(v107 + 22) & 0x20) == 0 )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      5912,
      (int)"LdrpInitializeProcess",
      0,
      "Secure processes must be large address aware\n",
      ArgList);
    return 3221225659LL;
  }
  v13 = 0;
  v14 = 0;
  do
  {
    LdrpHashTable[v14 + 1] = (__int64)&LdrpHashTable[v14];
    LdrpHashTable[v14] = (__int64)&LdrpHashTable[v14];
    ++v13;
    v14 += 2;
  }
  while ( v13 != 32 );
  if ( v11
    || (result = LdrpHandleUserCopyAttributeList(v14 * 8, 32, LdrpHashTable),
        ApplicationKeyOption = result,
        (int)result >= 0) )
  {
    v98 = 0;
    RtlImageNtHeaderEx(3, a2, 0, &v98);
    v15 = *(_DWORD *)&v98->DllPath.Length;
    RtlInsertInvertedFunctionTable(a2, v15);
    v118 = 0;
    v119 = 0;
    RtlpxLookupFunctionTable(a2, &v118);
    LdrProtectMrdata(0);
    xmmword_1801E0450 = v118;
    HIDWORD(qword_1801E0460) = HIDWORD(v119);
    LODWORD(qword_1801E0460) = v15;
    RtlRemoveInvertedFunctionTable(a2);
    LdrProtectMrdata(1);
    LdrpCaptureCriticalThunks();
    LdrProtectMrdata(1);
    if ( (unsigned int)LdrControlFlowGuardEnforcedWithExportSuppression() == 1 )
      LdrpSuppressedExportOverrideListPtr = (__int64)&LdrpSuppressedExportOverrideList;
    v16 = ((unsigned __int8)qword_1801E3508 >> 4) & 3;
    LdrpEnforceIntegrityContinuity = v16 == 1;
    LdrpAuditIntegrityContinuity = ((v16 - 1) & 0xFD) == 0;
    ApplicationKeyOption = LdrpInitializeExecutionOptions(
                             (unsigned int)&v112,
                             (_DWORD)ProcessEnvironmentBlock,
                             a2,
                             (unsigned int)&v108,
                             (__int64)v104,
                             (__int64)&v101);
    if ( ApplicationKeyOption < 0 )
    {
      LODWORD(ArgLista) = v3->ClientId.UniqueProcess;
      Format = "Initializing the execution options for the process %lx failed with status 0x%08lx\n";
      v18 = 6077;
LABEL_26:
      LdrpLogInternal((int)"minkernel\\ldr\\ldrinit.c", v18, (int)"LdrpInitializeProcess", 0, Format, (char)ArgLista);
      return (unsigned int)ApplicationKeyOption;
    }
    LOBYTE(v5) = 0;
    v100 = v5;
    v19 = 0;
    if ( LdrpImageExpansionMitigation == 2 )
      LdrpIsHotPatchingEnabled = 0;
    if ( (ProcessEnvironmentBlock->NtGlobalFlag & 2) != 0 )
      LdrpDebugFlags |= 1u;
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      6135,
      (int)"LdrpInitializeProcess",
      2,
      "Initializing process 0x%p\n",
      (char)v3->ClientId.UniqueProcess);
    WowTebOffset = v3->WowTebOffset;
    UseWOW64 = WowTebOffset > 0;
    if ( v10 && *(_WORD *)(v10 + 24) == 267 && WowTebOffset <= 0 )
    {
      UseCOR = 1;
      result = LdrpCorFixupImage(ProcessEnvironmentBlock->ImageBaseAddress);
      ApplicationKeyOption = result;
      if ( (int)result < 0 )
        return result;
      v19 = 1;
      LOBYTE(v5) = 1;
      v100 = v5;
    }
    pShimData = 0;
    if ( !UseWOW64 && !UseCOR )
    {
      LOBYTE(v20) = 1;
      v22 = RtlImageDirectoryEntryToData(ProcessEnvironmentBlock->ImageBaseAddress, v20, 14, &v98);
      if ( v22 )
      {
        UseCOR = 1;
        v5 = (unsigned __int8)v5;
        if ( (*(_BYTE *)(v22 + 16) & 1) != 0 )
          v5 = 1;
        v100 = v5;
      }
    }
    LdrpSystemDllBase = v114;
    if ( !UseWOW64 )
      pShimData = ProcessEnvironmentBlock->pShimData;
    RtlpTimeout = ProcessEnvironmentBlock->CriticalSectionTimeout;
    v23 = RtlNormalizeProcessParams(ProcessEnvironmentBlock->ProcessParameters);
    ImagePathName = *(__m128i *)(v23 + 96);
    if ( UseWOW64 || UseCOR && v19 )
      Config = 0;
    else
      Config = (_DWORD *)LdrImageDirectoryEntryToLoadConfigEx(ProcessEnvironmentBlock->ImageBaseAddress);
    if ( Config )
    {
      if ( *Config >= 0x10u )
        ProcessEnvironmentBlock->NtGlobalFlag &= ~Config[3];
      if ( *Config >= 0x14u )
        ProcessEnvironmentBlock->NtGlobalFlag |= Config[4];
      if ( *Config >= 0x18u && Config[5] )
        RtlpTimeout.QuadPart = -10000LL * (int)Config[5];
    }
    if ( (ProcessEnvironmentBlock->NtGlobalFlag & 2) != 0 )
      LdrpDebugFlags |= 1u;
    if ( RtlpTimeout.QuadPart < -36000000000LL )
      RtlpTimeoutDisable = 1;
    RtlFailedCriticalDebugAllocations = 0;
    if ( ((unsigned __int8)&RtlCriticalSectionDebugSList & 0xF) != 0 )
      goto LABEL_284;
    RtlCriticalSectionDebugSList = 0;
    v25 = RtlpStaticDebugInfo;
    do
    {
      *v25 = (__int64)(v25 + 6);
      v25 += 6;
    }
    while ( v25 <= qword_1801CC280 );
    *v25 = 0;
    InterlockedPushListSList(&RtlCriticalSectionDebugSList, RtlpStaticDebugInfo, qword_1801CC2B0, 8);
    ApplicationKeyOption = 0;
    dword_1801C6220 = 64;
    qword_1801C6228 = ProcessEnvironmentBlock->TlsBitmapBits;
    dword_1801C6210 = 1024;
    qword_1801C6218 = (__int64)ProcessEnvironmentBlock->TlsExpansionBitmapBits;
    ProcessEnvironmentBlock->TlsBitmap = (_RTL_BITMAP *)&dword_1801C6220;
    ProcessEnvironmentBlock->TlsExpansionBitmap = (_RTL_BITMAP *)&dword_1801C6210;
    *(_BYTE *)qword_1801C6228 |= 1u;
    memset_thunk_772440563353939046(&RtlpFlsContext, 0, 0x60u);
    xmmword_1801C5E38 = 0;
    xmmword_1801C5E48 = 0;
    xmmword_1801C5E58 = 0;
    xmmword_1801C5E68 = 0;
    qword_1801C5E80 = (__int64)&qword_1801C5E78;
    qword_1801C5E78 = (__int64)&qword_1801C5E78;
    if ( UseWOW64 )
    {
      v26 = qword_1801C6228;
      RtlSetVolatileMemory(qword_1801C6228, 255, 2u);
      v26[2] |= 7u;
    }
    *((_BYTE *)qword_1801C6228 + 2) |= 1u;
    if ( (ProcessEnvironmentBlock->NtGlobalFlag & 0x1000) != 0 || (v27 = LdrpShouldCreateStackTraceDb) != 0 )
    {
      LODWORD(v98) = 24;
      if ( (int)LdrQueryImageFileExecutionOptions(
                  (unsigned int)&v112,
                  (unsigned int)L"StackTraceDatabaseSizeInMb",
                  4,
                  (unsigned int)&v98,
                  4,
                  0) < 0
        || (unsigned int)v98 < 0x18 )
      {
        v28 = 25165824;
      }
      else if ( (unsigned int)v98 <= 0x80 )
      {
        v28 = (unsigned int)((_DWORD)v98 << 20);
      }
      else
      {
        v28 = 0x8000000;
      }
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        6384,
        (int)"LdrpInitializeProcess",
        2,
        "Stack trace database size is %Id Mb\n",
        v28 >> 20);
      v118 = 0u;
      v119 = v28;
      ApplicationKeyOption = RtlControlStackTraceDataBase(0, 24, &v118);
      v27 = LdrpShouldCreateStackTraceDb;
      v10 = v107;
    }
    if ( (ProcessEnvironmentBlock->NtGlobalFlag & 0x1000) != 0 || v27 )
      RtlpForceCSDebugInfoCreation = 1;
    if ( (NtCurrentPeb()->AppCompatFlags.LowPart & 0x400000) != 0 )
    {
      RtlpForceCSDebugInfoCreation = 1;
      RtlpForceCSToUseEvents = 1;
    }
    result = RtlInitializeCriticalSectionEx(&FastPebLock, 0, 0);
    ApplicationKeyOption = result;
    if ( (int)result < 0 )
      return result;
    ProcessEnvironmentBlock->FastPebLock = (_RTL_CRITICAL_SECTION *)&FastPebLock;
    result = RtlInitializeHeapManager(&v112);
    ApplicationKeyOption = result;
    if ( (int)result < 0 )
      return result;
    if ( (((unsigned __int64)qword_1801E3500 >> 12) & 3) == 1 )
      RtlSetHeapInformation(0, 1, 0, 0);
    ApplicationKeyOption = LdrpInitializeProcessHeap(Config, v10, v23, &ProcessEnvironmentBlock->ProcessHeap);
    if ( ApplicationKeyOption < 0 )
    {
      v29 = "Creating the process heap failed\n";
      v30 = 6457;
LABEL_87:
      LdrpLogInternal((int)"minkernel\\ldr\\ldrinit.c", v30, (int)"LdrpInitializeProcess", 0, v29, ArgListb);
      return 3221225495LL;
    }
    ProcessHeap = ProcessEnvironmentBlock->ProcessHeap;
    RtlpInitFeatureConfiguration(2);
    if ( (unsigned int)Feature_Servicing_LoaderSnapsBuffer__private_IsEnabledDeviceUsageNoInline() )
      LdrpInitializeSnapsBuffer();
    RtlInitializeCriticalSectionEx(LdrpEnclaveListLock, 0, 0);
    qword_1801CC368 = (__int64)&LdrpEnclaveList;
    LdrpEnclaveList = (__int64)&LdrpEnclaveList;
    if ( (ProcessEnvironmentBlock->NtGlobalFlag & 0x800000) != 0 )
      RtlInitializeExceptionLog();
    RtlpInitializeThreadActivationContextStack(v102);
    LdrpHeap = (__int64)ProcessHeap;
    if ( ((unsigned __int8)&EtwpFreeRegistrationList & 0xF) != 0 )
LABEL_284:
      RtlRaiseStatus(2147483650LL);
    EtwpFreeRegistrationList = 0;
    PrivateLoggerNotificationEntry = 0;
    if ( NtQuerySystemInformation(SystemHypervisorSharedPageInformation, &SystemInformation, 8u, 0) >= 0 )
      RtlpHypervisorSharedUserVa = SystemInformation;
    NtdllBaseTag = RtlCreateTagHeap(ProcessHeap);
    result = TpInitializePackage();
    ApplicationKeyOption = result;
    if ( (int)result >= 0 )
    {
      if ( *(_DWORD *)(v23 + 1080) )
        TpSetDefaultPoolCpuSets(*(void **)(v23 + 1072));
      v32 = *(_DWORD *)(v23 + 1084);
      if ( v32 )
      {
        RtlAcquireSRWLockExclusive(&TppPoolpGlobalPoolLock);
        TppPoolpGlobalPoolMaxThreadsOverride = v32;
        RtlReleaseSRWLockExclusive(&TppPoolpGlobalPoolLock);
      }
      if ( !UseWOW64 && !LdrpIsSecureProcess )
        LdrpEnableUMGLTracingStateSync();
      TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation(&dword_1801C4700);
      EtwEventRegister((int)&PrivateLoggerNotificationGuid, 0, 0, (__int64)&g_hPrivLoggerNotificationProvider);
      EtwEventRegister(
        (int)UserDiagnosticGuid,
        (__int64)UserDiagnosticProviderCallback,
        0,
        (__int64)&g_hUserDiagnosticProvider);
      RtlInitializeHeapLogging();
      result = RtlpInitEnvironmentBlock();
      ApplicationKeyOption = result;
      if ( (int)result >= 0 )
      {
        result = RtlpInitParameterBlock();
        ApplicationKeyOption = result;
        if ( (int)result >= 0 )
        {
          v33 = ProcessEnvironmentBlock->ProcessParameters;
          v98 = v33;
          ImagePathName = (__m128i)v33->ImagePathName;
          *((_QWORD *)&v112 + 1) = _mm_srli_si128(ImagePathName, 8).m128i_u64[0];
          if ( v108 || v104[0] )
          {
            ApplicationKeyOption = RtlQueryApplicationKeyOption(
                                     v104[0],
                                     (_DWORD)v108,
                                     (unsigned int)L"DebugProcessHeapOnly",
                                     4,
                                     (__int64)&v99,
                                     4);
            if ( ApplicationKeyOption >= 0 && dword_1801C4588 && (_DWORD)v99 )
            {
              dword_1801C4588 = 0;
              *(_DWORD *)RtlpDebugPageHeapTable &= ~0x400u;
            }
          }
          NtSystemRoot = RtlGetNtSystemRoot();
          RtlInitUnicodeStringEx(&v106, NtSystemRoot);
          v35 = v106.Length + 40;
          Heap_0 = RtlAllocateHeap_0(ProcessHeap, 0, (unsigned int)v106.Length + 38 + 2LL);
          if ( !Heap_0 )
            return 3221225495LL;
          v109[0] = 0;
          v109[1] = v35;
          v111 = Heap_0;
          RtlAppendUnicodeStringToString(v109, &v106);
          RtlAppendUnicodeStringToString(v109, &SlashSystem32SlashString);
          if ( (ProcessEnvironmentBlock->BitField & 2) == 0 )
          {
            LODWORD(v99) = 0;
            v37 = 48;
            *(_DWORD *)v124 = 48;
            *(_QWORD *)&v124[8] = 0;
            *(_DWORD *)&v124[24] = 64;
            *(_QWORD *)&v124[16] = v123;
            *(_OWORD *)&v124[32] = 0;
            LdrProtectMrdata(0);
            ApplicationKeyOption = ZwOpenDirectoryObject(&LdrpKnownDllDirectoryHandle, 3, v124);
            LdrProtectMrdata(1);
            if ( ApplicationKeyOption < 0 )
            {
              ArgLista = v123;
              v18 = 6752;
LABEL_117:
              Format = "Failed to open %wZ with status 0x%08lx\n";
              goto LABEL_26;
            }
            *(_DWORD *)v124 = 48;
            *(_QWORD *)&v124[8] = LdrpKnownDllDirectoryHandle;
            *(_DWORD *)&v124[24] = 64;
            *(_QWORD *)&v124[16] = &qword_180171DC0;
            *(_OWORD *)&v124[32] = 0;
            ApplicationKeyOption = ZwOpenSymbolicLinkObject(&Handle, 1, v124);
            if ( ApplicationKeyOption < 0 )
            {
              ArgLista = &qword_180171DC0;
              v18 = 6775;
              goto LABEL_117;
            }
            while ( 1 )
            {
              v39 = RtlAllocateHeap_0(ProcessHeap, 0, v37);
              v40 = v39;
              if ( !v39 )
                return 3221225495LL;
              LdrpKnownDllPath = 0;
              word_1801CA7B2 = v37;
              qword_1801CA7B8 = v39;
              v38 = NtQuerySymbolicLinkObject(Handle, &LdrpKnownDllPath, &v99);
              ApplicationKeyOption = v38;
              if ( v38 >= 0 )
                break;
              if ( v38 != -1073741789 )
              {
                LdrpLogInternal(
                  (int)"minkernel\\ldr\\ldrinit.c",
                  6810,
                  (int)"LdrpInitializeProcess",
                  0,
                  "Querying the known DLL directory link object failed with status 0x%08lx\n",
                  v38);
                return (unsigned int)ApplicationKeyOption;
              }
              RtlFreeHeap_0(ProcessHeap, 0, v40);
              v37 = (unsigned int)v99;
            }
            NtClose(Handle);
            v33 = v98;
          }
          v41 = 1;
          if ( UseWOW64 || LdrpIsSecureProcess )
          {
            UnicodeString = v106;
          }
          else
          {
            DosPath = v33->CurrentDirectory.DosPath;
            UnicodeString = DosPath;
            v43 = (_WORD *)_mm_srli_si128((__m128i)DosPath, 8).m128i_u64[0];
            if ( !v43 || !(unsigned __int16)_mm_cvtsi128_si32((__m128i)DosPath) || !*v43 )
            {
              v44 = (wchar_t *)RtlAllocateHeap_0(ProcessHeap, 0, 8);
              UnicodeString.Buffer = v44;
              if ( !v44 )
              {
                v29 = "Allocating a buffer to hold the current working directory failed\n";
                v30 = 6862;
                goto LABEL_87;
              }
              v41 = 0;
              v45 = RtlGetNtSystemRoot();
              *(_DWORD *)v44 = *(_DWORD *)v45;
              v44[2] = *(_WORD *)(v45 + 4);
              UnicodeString.Buffer[3] = 0;
              *(_DWORD *)&UnicodeString.Length = 524294;
            }
          }
          LdrpInitializePolicy();
          if ( (ProcessEnvironmentBlock->ProcessParameters->Flags & 0x20000000) != 0 )
          {
            v48 = LdrpIncludeAlternateForwarders(v46, v109[0]);
            v49 = 2 * v47 + 22;
            if ( v48 )
              v49 = v47 + 2 * v47 + 52;
          }
          else
          {
            v48 = 0;
            v49 = v109[0];
          }
          if ( (LdrpPolicyBits & 1) != 0 )
          {
            v50 = v49;
          }
          else
          {
            v50 = v49 + 2 * (v106.Length + 9LL);
            if ( (ProcessEnvironmentBlock->BitField & 2) != 0 )
              v98->DllPath.Length = 0;
          }
          v103.m128i_i64[1] = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, v50);
          if ( !v103.m128i_i64[1] )
          {
            v29 = "Failed to allocate the system dirs string!\n";
            v30 = 6955;
            goto LABEL_87;
          }
          v103.m128i_i16[0] = 0;
          v103.m128i_i16[1] = v50;
          RtlAppendUnicodeStringToString(&v103, v109);
          v51 = v103.m128i_i16[0];
          v52 = v103.m128i_i64[1];
          *(_WORD *)(v103.m128i_i64[1] + 2 * ((unsigned __int64)v103.m128i_u16[0] >> 1) - 2) = 59;
          RtlpSystem32Dirs = (__int128)v103;
          word_1801CA9D2 = _mm_extract_epi16(v103, 1);
          dword_1801CA9D4 = v103.m128i_i32[1];
          qword_1801CA9D8 = v52;
          LdrpSystem32 = v51 - 2;
          if ( (ProcessEnvironmentBlock->ProcessParameters->Flags & 0x20000000) != 0 )
          {
            if ( v48 )
            {
              RtlAppendUnicodeStringToString(&v103, v109);
              RtlAppendUnicodeToString(&v103, L"forwarders\\alt;");
            }
            RtlAppendUnicodeStringToString(&v103, v109);
            RtlAppendUnicodeToString(&v103, L"forwarders;");
          }
          if ( v50 > v49 )
          {
            RtlAppendUnicodeStringToString(&v103, &v106);
            RtlAppendUnicodeToString(&v103, L"\\system;");
            RtlAppendUnicodeStringToString(&v103, &v106);
            RtlAppendUnicodeToString(&v103, L";");
            RtlpSystemDirs = (__int128)v103;
          }
          if ( (unsigned int)(LdrpIllegalCWDDevices - 1) <= 0xFFFFFFFD )
            LdrpCheckAppDirType(&ImagePathName);
          result = LdrpInitializeNtdllDataTableEntry(v114, &LdrpNtDllDataTableEntry, 0, v109);
          ApplicationKeyOption = result;
          if ( (int)result >= 0 )
          {
            v53 = 0;
            v54 = ImagePathName.m128i_u16[0] + ImagePathName.m128i_i64[1];
            v55 = (_WORD *)v54;
            if ( v54 && v54 > ImagePathName.m128i_i64[1] )
            {
              while ( 1 )
              {
                v56 = v55--;
                if ( *v55 == 92 )
                  break;
                if ( (unsigned __int64)v55 <= ImagePathName.m128i_i64[1] )
                  goto LABEL_161;
              }
              v53 = (__int64)v56;
            }
LABEL_161:
            if ( v53 )
            {
              v57 = v54 - v53;
              v117.m128i_i16[0] = v57;
              if ( ImagePathName.m128i_u16[1] - (unsigned __int64)ImagePathName.m128i_u16[0] >= 2 )
                v57 += 2;
              v117.m128i_i16[1] = v57;
              v117.m128i_i64[1] = v53;
            }
            else
            {
              v117 = ImagePathName;
            }
            if ( *(int *)(LdrpNtdllHotPatchContext + 8) < 0 && LdrpIsHotPatchingEnabled )
              __fastfail(0x45u);
            v99 = 0;
            if ( !*(_QWORD *)LdrpNtdllHotPatchContext
              || (result = LdrpInitializeNtdllDataTableEntry(
                             *(_QWORD *)LdrpNtdllHotPatchContext,
                             &v99,
                             LdrpNtDllDataTableEntry,
                             0),
                  ApplicationKeyOption = result,
                  (int)result >= 0) )
            {
              RtlInitializeHistoryTable();
              v58 = qword_1801CA8F0;
              if ( *(__int64 **)(qword_1801CA8F0 + 8) == &qword_1801CA8F0 )
              {
                v59 = LdrpNtDllDataTableEntry + 32;
                *(_QWORD *)(LdrpNtDllDataTableEntry + 32) = qword_1801CA8F0;
                *(_QWORD *)(v59 + 8) = &qword_1801CA8F0;
                *(_QWORD *)(v58 + 8) = v59;
                qword_1801CA8F0 = v59;
                if ( !v99 )
                  goto LABEL_175;
                if ( *(__int64 **)(v59 + 8) == &qword_1801CA8F0 )
                {
                  v60 = v99 + 32;
                  *(_QWORD *)(v99 + 32) = v59;
                  *(_QWORD *)(v60 + 8) = &qword_1801CA8F0;
                  *(_QWORD *)(v59 + 8) = v60;
                  qword_1801CA8F0 = v60;
LABEL_175:
                  inited = LdrpInitParallelLoadingSupport();
                  ApplicationKeyOption = inited;
                  if ( inited < 0 )
                  {
                    LdrpLogInternal(
                      (int)"minkernel\\ldr\\ldrinit.c",
                      7186,
                      (int)"LdrpInitializeProcess",
                      0,
                      "Failed to initialize Parallel loader, st = 0x%x\n",
                      inited);
                    return (unsigned int)ApplicationKeyOption;
                  }
                  LdrpDrainWorkQueue(0);
                  LdrpInitializeDllPath(0, 0, v134);
                  memset_thunk_772440563353939046(&v130, 0, 0xD0u);
                  v131 = v134;
                  v132 = 512;
                  v130 = ImagePathName;
                  p_ApplicationKeyOption = &ApplicationKeyOption;
                  v62 = LdrpAllocateModuleEntry(&v130);
                  if ( !v62 )
                  {
                    v29 = "Allocating a data table entry for the executable failed\n";
                    v30 = 7207;
                    goto LABEL_87;
                  }
                  LdrpImageEntry = v62;
                  *(_DWORD *)(*(_QWORD *)(v62 + 152) + 24LL) = -1;
                  *(_DWORD *)(*(_QWORD *)(v62 + 152) + 24LL) = -1;
                  *(_WORD *)(**(_QWORD **)(LdrpImageEntry + 152) - 52LL) = -1;
                  v63 = LdrpImageEntry;
                  *(__m128i *)(LdrpImageEntry + 72) = ImagePathName;
                  *(_DWORD *)(v63 + 104) |= 4u;
                  if ( (ProcessEnvironmentBlock->BitField & 0x10) != 0 )
                    *(_DWORD *)(LdrpImageEntry + 104) |= 1u;
                  v64 = v100;
                  if ( UseCOR )
                  {
                    *(_DWORD *)(LdrpImageEntry + 104) |= 0x400000u;
                    if ( v64 )
                      *(_DWORD *)(LdrpImageEntry + 104) |= 0x1000000u;
                  }
                  if ( (ProcessEnvironmentBlock->BitField & 4) != 0 )
                    *(_QWORD *)(LdrpImageEntry + 248) = 0;
                  *(__m128i *)(LdrpImageEntry + 88) = v117;
                  ImageBaseAddress = ProcessEnvironmentBlock->ImageBaseAddress;
                  v66 = v107;
                  if ( *(void **)(v107 + 48) != ImageBaseAddress && !v64 && !UseWOW64 )
                  {
                    result = LdrpProtectAndRelocateImage((char)ImageBaseAddress);
                    ApplicationKeyOption = result;
                    if ( (int)result < 0 )
                      return result;
                  }
                  v67 = LdrpImageEntry;
                  *(_QWORD *)(LdrpImageEntry + 48) = ProcessEnvironmentBlock->ImageBaseAddress;
                  LdrpInsertDataTableEntry(v67);
                  LdrpLogInternal(
                    (int)"minkernel\\ldr\\ldrinit.c",
                    7299,
                    (int)"LdrpInitializeProcess",
                    2,
                    "Beginning execution of %wZ (%wZ)\n\tCurrent directory: %wZ\n\tPackage directories: %wZ\n",
                    LdrpImageEntry + 88);
                  LdrpLogDllState(*(_QWORD *)(LdrpImageEntry + 48), LdrpImageEntry + 72, 5285);
                  LdrpInsertModuleToIndex(LdrpImageEntry, v66);
                  result = LdrpProcessMappedModule(LdrpImageEntry, 0, UseWOW64 == 0);
                  ApplicationKeyOption = result;
                  if ( (int)result < 0 )
                    return result;
                  *(_DWORD *)(*(_QWORD *)(LdrpImageEntry + 152) + 56LL) = 9;
                  ApplicationKeyOption = RtlpInitCurrentDir(&UnicodeString);
                  if ( ApplicationKeyOption < 0 )
                    LdrpLogInternal(
                      (int)"minkernel\\ldr\\ldrinit.c",
                      7336,
                      (int)"LdrpInitializeProcess",
                      0,
                      "Initializing the current directory to \"%wZ\" failed with status 0x%08lx\n",
                      (char)&UnicodeString);
                  if ( !v41 )
                    RtlFreeAnsiString(&UnicodeString);
                  if ( AvrfAppVerifierMode )
                  {
                    ModuleEntry = LdrpAllocateModuleEntry(0);
                    v69 = (_QWORD *)ModuleEntry;
                    if ( !ModuleEntry )
                    {
                      v29 = "Allocating a data table entry for the application verifier DLL failed\n";
                      v30 = 7361;
                      goto LABEL_87;
                    }
                    *(_DWORD *)(*(_QWORD *)(ModuleEntry + 152) + 24LL) = -1;
                    *(_WORD *)(**(_QWORD **)(ModuleEntry + 152) - 52LL) = -1;
                    *(_DWORD *)(ModuleEntry + 104) |= *(_DWORD *)(v101 + 104);
                    *(_QWORD *)(ModuleEntry + 248) = *(_QWORD *)(v101 + 248);
                    *(_WORD *)(ModuleEntry + 110) = 0;
                    *(_OWORD *)(ModuleEntry + 72) = *(_OWORD *)(v101 + 72);
                    *(_OWORD *)(ModuleEntry + 88) = *(_OWORD *)(v101 + 88);
                    *(_DWORD *)(ModuleEntry + 128) = *(_DWORD *)(v101 + 128);
                    *(_DWORD *)(ModuleEntry + 288) = *(_DWORD *)(v101 + 288);
                    *(_QWORD *)(ModuleEntry + 48) = *(_QWORD *)(v101 + 48);
                    LdrpInsertDataTableEntry(ModuleEntry);
                    LdrpLogDllState(v69[6], v69 + 9, 5285);
                    result = RtlImageNtHeaderEx(3, v69[6], 0, &v121);
                    ApplicationKeyOption = result;
                    if ( (int)result < 0 )
                      return result;
                    LdrpInsertModuleToIndex(v69, v121);
                    result = LdrpProcessMappedModule(v69, 0, 1);
                    ApplicationKeyOption = result;
                    if ( (int)result < 0 )
                      return result;
                    v69[7] = *(_QWORD *)(v101 + 56);
                    LdrpLogDllState(v69[6], v69 + 9, 5293);
                    *(_DWORD *)(v69[19] + 56LL) = 7;
                    if ( (ProcessEnvironmentBlock->NtGlobalFlag & 0x100) != 0 || (AvrfAppVerifierMode & 2) != 0 )
                    {
                      result = AVrfInitializeVerifier(0, 0, 0, 1, v114, 0);
                      ApplicationKeyOption = result;
                      if ( (int)result < 0 )
                        return result;
                      if ( (AvrfAppVerifierMode & 2) != 0 )
                      {
                        *(_DWORD *)(v69[19] + 56LL) = 9;
                        result = (unsigned int)ApplicationKeyOption;
                      }
                    }
                    else
                    {
                      v97[0] = 0;
                      result = LdrpInitializeGraphRecurse(v69[19], 0, v97);
                      ApplicationKeyOption = result;
                    }
                    if ( (int)result < 0 )
                      return result;
                    v66 = v107;
                  }
                  LdrpDropLastInProgressCount();
                  if ( UseWOW64 )
                  {
                    if ( v108 )
                    {
                      NtClose(v108);
                      v108 = 0;
                      if ( LdrpLargePageDllKeyHandle )
                      {
                        NtClose(LdrpLargePageDllKeyHandle);
                        LdrpLargePageDllKeyHandle = 0;
                      }
                    }
                    if ( v104[0] )
                    {
                      NtClose(v104[0]);
                      v104[0] = 0;
                    }
                    result = LdrpLoadWow64(v109);
                    ApplicationKeyOption = result;
                    if ( (int)result >= 0 )
                    {
                      if ( ProcessEnvironmentBlock->BeingDebugged )
                        LdrpDoDebuggerBreak();
                      LdrInitState = 3;
                      _interlockedbittestandreset((volatile signed __int32 *)&ProcessEnvironmentBlock->80, 1u);
                      g_LdrpWow64LdrpInitialize(v116);
LABEL_261:
                      if ( v108 )
                        NtClose(v108);
                      if ( v104[0] )
                        NtClose(v104[0]);
                      _RAX = 1;
                      __asm { cpuid }
                      x86_cpu_enable_ssse3 = _RCX & 0x200;
                      if ( (_RDX & 0x4000000) == 0 || (_RCX & 0x100000) == 0 || (v85 = 1, (_RCX & 2) == 0) )
                        v85 = 0;
                      x86_cpu_enable_simd = v85;
                      IsProcessorFeaturePresent = RtlIsProcessorFeaturePresent(41);
                      _RCX = IsProcessorFeaturePresent;
                      x86_cpu_enable_avx512 = IsProcessorFeaturePresent;
                      if ( IsProcessorFeaturePresent )
                      {
                        if ( x86_cpu_enable_simd )
                        {
                          _RAX = 7;
                          __asm { cpuid }
                          if ( (_RCX & 0x400) == 0 )
                            x86_cpu_enable_avx512 = 0;
                        }
                      }
                      if ( (g_SymCryptFlags & 1) == 0 )
                      {
                        SymCryptDetectCpuFeaturesByCpuid(_RCX, _RDX);
                        _InterlockedOr(&g_SymCryptFlags, 1u);
                        LODWORD(v99) = 6815744;
                        for ( i = "v104.0.0__2026-04-28T21:40:22+00:00_9319fe3_2026-04-28T22:01:17"; *i; ++i )
                          LOBYTE(v99) = *i;
                        g_SymCryptCpuFeaturesPresentCheck = ~g_SymCryptCpuFeaturesNotPresent;
                      }
                      return 0;
                    }
                    return result;
                  }
                  LdrpInitializeCfgScpHelpers();
                  LdrpSchedulerSharedDataListHeadLock = 0;
                  qword_1801CA988 = (__int64)&LdrpSchedulerSharedDataListHead;
                  LdrpSchedulerSharedDataListHead = (__int64)&LdrpSchedulerSharedDataListHead;
                  LdrpAllocateSchedulerSharedData();
                  v70 = v102;
                  LdrpAcquireSchedulerSharedDataSlot(v102);
                  v102 = 0;
                  if ( UseCOR )
                  {
                    result = LdrpCorInitialize(&v102);
                    ApplicationKeyOption = result;
                    if ( (int)result < 0 )
                      return result;
                    if ( v64 )
                    {
                      result = LdrpCorValidateImage(ProcessEnvironmentBlock->ImageBaseAddress);
                      ApplicationKeyOption = result;
                      if ( (int)result < 0 )
                        return result;
                    }
                    if ( (v70->SameTebFlags & 0x400) != 0 )
                      *(_QWORD *)(v116 + 128) = __ROR8__(LdrpCorExeMainRoutine, 64 - (MEMORY[0x7FFE0330] & 0x3Fu))
                                              ^ MEMORY[0x7FFE0330];
                  }
                  v71 = LdrpInitializeTls();
                  ApplicationKeyOption = v71;
                  if ( v71 < 0 )
                  {
                    LdrpLogInternal(
                      (int)"minkernel\\ldr\\ldrinit.c",
                      7627,
                      (int)"LdrpInitializeProcess",
                      0,
                      "Initializing TLS slots failed with status 0x%08lx\n",
                      v71);
                    return (unsigned int)ApplicationKeyOption;
                  }
                  if ( *(_BYTE *)(LdrpNtdllHotPatchContext + 12) )
                    LdrpLogEtwHotPatchStatus(
                      (unsigned int)&v117,
                      LdrpNtDllDataTableEntry,
                      0,
                      *(_DWORD *)(LdrpNtdllHotPatchContext + 8),
                      0);
                  if ( v102 )
                  {
                    v97[0] = 0;
                    v72 = LdrpInitializeGraphRecurse(*(_QWORD *)&v102->User32Reserved[6], 0, v97);
                    ApplicationKeyOption = v72;
                    if ( v72 < 0 )
                    {
                      LdrpLogInternal(
                        (int)"minkernel\\ldr\\ldrinit.c",
                        7664,
                        (int)"LdrpInitializeProcess",
                        0,
                        "DllMain of MSCOREE (or its dependents) failed with status 0x%08lx\n",
                        v72);
                      return (unsigned int)ApplicationKeyOption;
                    }
                  }
                  v73 = LdrpInitializeImportRedirection();
                  ApplicationKeyOption = v73;
                  if ( v73 < 0 )
                  {
                    LdrpLogInternal(
                      (int)"minkernel\\ldr\\ldrinit.c",
                      7680,
                      (int)"LdrpInitializeProcess",
                      0,
                      "Loading of import redirection module failed with status 0x%08x\n",
                      v73);
                    return (unsigned int)ApplicationKeyOption;
                  }
                  v102 = 0;
                  if ( (unsigned __int16)(*(_WORD *)(v66 + 92) - 2) <= 1u )
                  {
                    v74 = LdrpInitializeKernel32Functions(&v102);
                    ApplicationKeyOption = v74;
                    if ( v74 < 0 )
                    {
                      LdrpLogInternal(
                        (int)"minkernel\\ldr\\ldrinit.c",
                        7702,
                        (int)"LdrpInitializeProcess",
                        0,
                        "Calling LdrpInitializeKernel32Functions failed with status 0x%08lx\n",
                        v74);
                      return (unsigned int)ApplicationKeyOption;
                    }
                  }
                  LdrpDrainWorkQueue(0);
                  SbObtainTraceHandle(0);
                  v75 = pShimData;
                  if ( pShimData && pShimData[132] )
                  {
                    ProcessEnvironmentBlock->AppCompatInfo = 0;
                    LdrpInitShimEngine(v75);
                  }
                  if ( (NtCurrentPeb()->AppCompatFlags.LowPart & 0x400000) != 0 )
                    RtlpForceCSDebugInfoCreation = 1;
                  v76 = v98;
                  if ( (NtCurrentPeb()->AppCompatFlags.LowPart & 0x10000000) != 0 )
                    v98->LoaderThreads = 1;
                  LdrpEnableParallelLoading(v76->LoaderThreads);
                  LdrInitState = 1;
                  *(_DWORD *)(*(_QWORD *)(LdrpImageEntry + 152) + 56LL) = 2;
                  *p_ApplicationKeyOption = 0;
                  if ( v64 )
                  {
                    v77 = LdrpCorProcessImports(LdrpImageEntry);
                  }
                  else
                  {
                    LdrpThreadTokenSetMainThreadToken();
                    v132 |= 1u;
                    LdrpMapAndSnapDependency(&v130);
                    LdrpDrainWorkQueue(1);
                    if ( LdrpMainThreadToken )
                      LdrpThreadTokenUnsetMainThreadToken();
                    LOBYTE(v77) = ApplicationKeyOption;
                    if ( ApplicationKeyOption < 0 )
                      goto LABEL_279;
                    v77 = LdrpPrepareModuleForExecution(LdrpImageEntry, p_ApplicationKeyOption);
                  }
                  ApplicationKeyOption = v77;
                  if ( v77 >= 0 )
                  {
                    LdrInitState = 2;
                    result = LdrpInitializePatchData();
                    ApplicationKeyOption = result;
                    if ( (int)result < 0 )
                      return result;
                    if ( ProcessEnvironmentBlock->BeingDebugged )
                      LdrpDoDebuggerBreak();
                    LdrpDropLastInProgressCount();
                    if ( Kernel32ThreadInitThunkFunction )
                    {
                      result = Kernel32ThreadInitThunkFunction(1, 0, 0);
                      ApplicationKeyOption = result;
                      if ( (int)result < 0 )
                        return result;
                      result = LdrpInitializePerUserWindowsDirectory(v102);
                      ApplicationKeyOption = result;
                      if ( (int)result < 0 )
                        return result;
                    }
                    LdrpProcessInitContextRecord = v116;
                    LdrpDrainWorkQueue(0);
                    LdrpAcquireLoaderLock();
                    v97[0] = 0;
                    ApplicationKeyOption = LdrpInitializeGraphRecurse(
                                             *(_QWORD *)(LdrpImageEntry + 152),
                                             p_ApplicationKeyOption,
                                             v97);
                    LdrpReleaseLoaderLock(v78, 9, (unsigned int)ApplicationKeyOption);
                    LdrpFreeLoadContextOfNode(*(_QWORD *)(LdrpImageEntry + 152), p_ApplicationKeyOption);
                    LdrpDropLastInProgressCount();
                    LdrpProcessInitContextRecord = 0;
                    LdrpReleaseDllPath(v134);
                    if ( ApplicationKeyOption >= 0 )
                    {
                      LdrpInitializeSmtDelayedSleep();
                      if ( *(_WORD *)(LdrpImageEntry + 110) )
                      {
                        v125[0] = 72;
                        v125[1] = 1;
                        v126 = 0;
                        v127 = 0;
                        v128 = 0;
                        v129 = 0;
                        RtlActivateActivationContextUnsafeFast(v125, *(_QWORD *)(LdrpImageEntry + 136));
                        LdrpCallTlsInitializers(1, LdrpImageEntry);
                        RtlDeactivateActivationContextUnsafeFast(v125);
                      }
                      if ( g_ShimsEnabled
                        && !((unsigned __int8 (__fastcall *)(__int128 *, _DWORD *))(__ROR8__(
                                                                                      g_pfnSE_InstallAfterInit,
                                                                                      64 - (MEMORY[0x7FFE0330] & 0x3Fu))
                                                                                  ^ MEMORY[0x7FFE0330]))(
                              &v112,
                              v75) )
                      {
                        Feature_Arm64VcRedistRedirect__private_IsEnabledDeviceUsageNoInline();
                        g_ShimsEnabled = 0;
                        LdrUnloadDll(g_pShimEngineModule);
                        g_pShimEngineModule = 0;
                      }
                      PostProcessInitRoutine = ProcessEnvironmentBlock->PostProcessInitRoutine;
                      if ( PostProcessInitRoutine )
                        PostProcessInitRoutine();
                      goto LABEL_261;
                    }
                    LdrpLogInternal(
                      (int)"minkernel\\ldr\\ldrinit.c",
                      8089,
                      (int)"LdrpInitializeProcess",
                      0,
                      "Running the init routines of the executable's static imports failed with status 0x%08lx\n",
                      ApplicationKeyOption);
                    return (unsigned int)ApplicationKeyOption;
                  }
LABEL_279:
                  LdrpLogInternal(
                    (int)"minkernel\\ldr\\ldrinit.c",
                    7941,
                    (int)"LdrpInitializeProcess",
                    0,
                    "Walking the import tables of the executable and its static imports failed with status 0x%08lx\n",
                    v77);
                  return (unsigned int)ApplicationKeyOption;
                }
              }
              __fastfail(3u);
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800d6508  mov     r11, rsp
0x1800d650b  mov     [r11+18h], rbx
0x1800d650f  mov     [r11+20h], rsi
0x1800d6513  push    rdi
0x1800d6514  push    r12
0x1800d6516  push    r13
0x1800d6518  push    r14
0x1800d651a  push    r15
0x1800d651c  sub     rsp, 350h
0x1800d6523  mov     rax, cs:__security_cookie
0x1800d652a  xor     rax, rsp
0x1800d652d  mov     [rsp+378h+var_38], rax
0x1800d6535  mov     rsi, rdx
0x1800d6538  mov     [rsp+378h+var_278], rdx
0x1800d6540  mov     [rsp+378h+var_268], rcx
0x1800d6548  xor     r14d, r14d
0x1800d654b  mov     [rsp+378h+var_328], r14d
0x1800d6550  xorps   xmm0, xmm0
0x1800d6553  movups  xmmword ptr [rsp+378h+UnicodeString.Length], xmm0
0x1800d655b  xorps   xmm1, xmm1
0x1800d655e  movups  [rsp+378h+var_2D8], xmm1
0x1800d6566  movups  [rsp+378h+var_258], xmm0
0x1800d656e  mov     [r11-2A4h], r14d
0x1800d6575  mov     [r11-2B8h], r14
0x1800d657c  movups  [rsp+378h+var_2C8], xmm0
0x1800d6584  movups  [rsp+378h+var_298], xmm1
0x1800d658c  mov     [r11-228h], r14
0x1800d6593  mov     [r11-270h], r14
0x1800d659a  xor     eax, eax
0x1800d659c  movups  [rsp+378h+var_208], xmm0
0x1800d65a4  movups  [rsp+378h+var_1F8], xmm0
0x1800d65ac  movups  [rsp+378h+var_1F8+0Ch], xmm0
0x1800d65b4  mov     qword ptr [r11-218h], 160014h
0x1800d65bf  lea     rax, aKnowndlls; "\\KnownDlls"
0x1800d65c6  mov     [r11-210h], rax
0x1800d65cd  mov     [r11-2B0h], r14
0x1800d65d4  mov     [r11-2E8h], r14
0x1800d65db  mov     [rsp+378h+var_308], r14
0x1800d65e0  xor     edx, edx; Val
0x1800d65e2  mov     r8d, 0D0h; Size
0x1800d65e8  lea     rcx, [r11-188h]; void *
0x1800d65ef  call    memset$thunk$772440563353939046
0x1800d65f4  xorps   xmm0, xmm0
0x1800d65f7  movups  [rsp+378h+var_2F8], xmm0
0x1800d65ff  xor     edx, edx; Val
0x1800d6601  mov     r8d, 80h; Size
0x1800d6607  lea     rcx, [rsp+378h+var_B8]; void *
0x1800d660f  call    memset$thunk$772440563353939046
0x1800d6614  mov     [rsp+378h+SystemInformation], r14
0x1800d661c  xor     ecx, ecx
0x1800d661e  call    RtlEncodePointer
0x1800d6623  mov     cs:RtlpUnhandledExceptionFilter, rax
0x1800d662a  mov     r13, gs:30h
0x1800d6633  mov     [rsp+378h+var_300], r13
0x1800d6638  mov     rdi, [r13+60h]
0x1800d663c  mov     rcx, r13
0x1800d663f  call    LdrpInitializeTeb
0x1800d6644  mov     cs:PebLdr, 58h ; 'X'
0x1800d664e  lea     r15d, [r14+1]
0x1800d6652  mov     cs:byte_1801CA8C4, r15b
0x1800d6659  lea     rax, qword_1801CA8D0
0x1800d6660  mov     cs:qword_1801CA8D8, rax
0x1800d6667  mov     cs:qword_1801CA8D0, rax
0x1800d666e  lea     rax, qword_1801CA8E0
0x1800d6675  mov     cs:qword_1801CA8E8, rax
0x1800d667c  mov     cs:qword_1801CA8E0, rax
0x1800d6683  lea     rax, qword_1801CA8F0
0x1800d668a  mov     cs:qword_1801CA8F8, rax
0x1800d6691  mov     cs:qword_1801CA8F0, rax
0x1800d6698  mov     cs:byte_1801CA908, r14b
0x1800d669f  mov     cs:qword_1801CA910, r14
0x1800d66a6  lea     rax, PebLdr
0x1800d66ad  mov     [rdi+18h], rax
0x1800d66b1  mov     rcx, rdi
0x1800d66b4  call    LdrpInitializeNlsInfo
0x1800d66b9  mov     cs:SRWLockSpinCycleCount, r14d
0x1800d66c0  cmp     [rdi+0B8h], r15d
0x1800d66c7  jbe     short loc_1800D66D3
0x1800d66c9  mov     cs:SRWLockSpinCycleCount, 2800h
0x1800d66d3  mov     cs:ConditionVariableSpinCycleCount, r14d
0x1800d66da  jbe     short loc_1800D66E6
0x1800d66dc  mov     cs:ConditionVariableSpinCycleCount, 2800h
0x1800d66e6  mov     cs:RtlpWaitOnAddressSpinCycleCount, r14d
0x1800d66ed  jbe     short loc_1800D66F9
0x1800d66ef  mov     cs:RtlpWaitOnAddressSpinCycleCount, 2800h
0x1800d66f9  mov     ecx, r15d
0x1800d66fc  call    RtlpInitFeatureConfiguration
0x1800d6701  call    Feature_Servicing_DisallowSharedLockImplicitUpgrade__private_IsEnabledNoReportingNoInline
0x1800d6706  mov     ecx, r14d
0x1800d6709  test    eax, eax
0x1800d670b  setz    cl
0x1800d670e  mov     cs:RtlpSrwLockAllowImplicitUpgrade, ecx
0x1800d6714  call    RtlpInitializeNonVolatileFlush
0x1800d6719  mov     rcx, [rdi+20h]
0x1800d671d  mov     rax, [rcx+68h]
0x1800d6721  test    [rcx+8], r15b
0x1800d6725  lea     rdx, [rax+rcx]
0x1800d6729  cmovnz  rdx, rax
0x1800d672d  mov     qword ptr [rsp+378h+var_298+8], rdx
0x1800d6735  movzx   ebx, word ptr [rcx+60h]
0x1800d6739  mov     word ptr [rsp+378h+var_298], bx
0x1800d6741  mov     eax, 2
0x1800d6746  add     eax, ebx
0x1800d6748  mov     word ptr [rsp+378h+var_298+2], ax
0x1800d6750  mov     r8d, 8
0x1800d6756  cmp     bx, r8w
0x1800d675a  jb      short loc_1800D67B6
0x1800d675c  cmp     word ptr [rdx], 5Ch ; '\'
0x1800d6760  jnz     short loc_1800D67B6
0x1800d6762  lea     r14d, [r8+37h]
0x1800d6766  cmp     [rdx+2], r14w
0x1800d676b  jnz     short loc_1800D67B3
0x1800d676d  cmp     [rdx+4], r14w
0x1800d6772  jnz     short loc_1800D67B3
0x1800d6774  cmp     word ptr [rdx+6], 5Ch ; '\'
0x1800d6779  jnz     short loc_1800D67B3
0x1800d677b  movzx   eax, bx
0x1800d677e  sub     ax, r8w
0x1800d6782  mov     word ptr [rsp+378h+var_298], ax
0x1800d678a  sub     bx, 6
0x1800d678e  mov     word ptr [rsp+378h+var_298+2], bx
0x1800d6796  lea     rax, [rdx+8]
0x1800d679a  mov     qword ptr [rsp+378h+var_298+8], rax
0x1800d67a2  mov     eax, 0FFF8h
0x1800d67a7  add     [rcx+60h], ax
0x1800d67ab  add     [rcx+62h], ax
0x1800d67af  add     [rcx+68h], r8
0x1800d67b3  xor     r14d, r14d
0x1800d67b6  mov     cs:UseCOR, r14b
0x1800d67bd  mov     dword ptr [rsp+378h+var_318], r14d
0x1800d67c2  lea     r9, [rsp+378h+var_2B8]
0x1800d67ca  xor     r8d, r8d
0x1800d67cd  mov     rdx, [rdi+10h]
0x1800d67d1  lea     ecx, [r8+3]
0x1800d67d5  call    RtlImageNtHeaderEx
0x1800d67da  mov     r12, [rsp+378h+var_2B8]
0x1800d67e2  mov     cs:LdrpAppHeaders, r12
0x1800d67e9  mov     bl, cs:LdrpIsSecureProcess
0x1800d67ef  test    bl, bl
0x1800d67f1  jz      short loc_1800D682C
0x1800d67f3  test    byte ptr [r12+16h], 20h
0x1800d67f9  jnz     short loc_1800D682C
0x1800d67fb  lea     rax, aSecureProcesse; "Secure processes must be large address "...
0x1800d6802  mov     [rsp+378h+Format], rax; Format
0x1800d6807  xor     r9d, r9d; int
0x1800d680a  lea     r8, aLdrpinitialize_3; "LdrpInitializeProcess"
0x1800d6811  mov     edx, 1718h; int
0x1800d6816  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800d681d  call    LdrpLogInternal
0x1800d6822  mov     eax, 0C00000BBh
0x1800d6827  jmp     loc_1800D6EB5
0x1800d682c  mov     rdx, r14
0x1800d682f  mov     rcx, r14
0x1800d6832  lea     r8, LdrpHashTable
0x1800d6839  lea     rax, [rcx+r8]
0x1800d683d  mov     [rcx+r8+8], rax
0x1800d6842  mov     [rax], rax
0x1800d6845  add     rdx, r15
0x1800d6848  lea     rcx, [rcx+10h]
0x1800d684c  cmp     rdx, 20h ; ' '
0x1800d6850  jnz     short loc_1800D6839
0x1800d6852  test    bl, bl
0x1800d6854  jnz     short loc_1800D6867
0x1800d6856  call    LdrpHandleUserCopyAttributeList
0x1800d685b  mov     [rsp+378h+var_328], eax
0x1800d685f  test    eax, eax
0x1800d6861  js      loc_1800D6EB5
0x1800d6867  mov     [rsp+378h+var_320], r14
0x1800d686c  lea     r9, [rsp+378h+var_320]
0x1800d6871  xor     r8d, r8d
0x1800d6874  mov     rdx, rsi
0x1800d6877  lea     ecx, [r8+3]
0x1800d687b  call    RtlImageNtHeaderEx
0x1800d6880  mov     rax, [rsp+378h+var_320]
0x1800d6885  mov     ebx, [rax+50h]
0x1800d6888  mov     edx, ebx
0x1800d688a  mov     rcx, rsi
0x1800d688d  call    RtlInsertInvertedFunctionTable
0x1800d6892  xorps   xmm0, xmm0
0x1800d6895  xor     eax, eax
0x1800d6897  movups  [rsp+378h+var_248], xmm0
0x1800d689f  mov     [rsp+378h+var_238], rax
0x1800d68a7  lea     rdx, [rsp+378h+var_248]
0x1800d68af  mov     rcx, rsi
0x1800d68b2  call    RtlpxLookupFunctionTable
0x1800d68b7  xor     ecx, ecx
0x1800d68b9  call    LdrProtectMrdata
0x1800d68be  movups  xmm0, [rsp+378h+var_248]
0x1800d68c6  movdqu  cs:xmmword_1801E0450, xmm0
0x1800d68ce  mov     rax, [rsp+378h+var_238]
0x1800d68d6  mov     dword ptr cs:qword_1801E0460, eax
0x1800d68dc  mov     eax, dword ptr [rsp+378h+var_238+4]
0x1800d68e3  mov     dword ptr cs:qword_1801E0460+4, eax
0x1800d68e9  nop
0x1800d68ea  mov     dword ptr cs:qword_1801E0460, ebx
0x1800d68f0  mov     rcx, rsi
0x1800d68f3  call    RtlRemoveInvertedFunctionTable
0x1800d68f8  mov     ecx, r15d
0x1800d68fb  call    LdrProtectMrdata
0x1800d6900  call    LdrpCaptureCriticalThunks
0x1800d6905  mov     ecx, r15d
0x1800d6908  call    LdrProtectMrdata
0x1800d690d  call    LdrControlFlowGuardEnforcedWithExportSuppression
0x1800d6912  cmp     eax, r15d
0x1800d6915  jnz     short loc_1800D6925
0x1800d6917  lea     rax, LdrpSuppressedExportOverrideList
0x1800d691e  mov     cs:LdrpSuppressedExportOverrideListPtr, rax
0x1800d6925  mov     rax, cs:qword_1801E3508
0x1800d692c  shr     al, 4
0x1800d692f  and     al, 3
0x1800d6931  cmp     al, r15b
0x1800d6934  setz    cs:LdrpEnforceIntegrityContinuity
0x1800d693b  sub     al, r15b
0x1800d693e  test    al, 0FDh
0x1800d6940  setz    cs:LdrpAuditIntegrityContinuity
0x1800d6947  lea     rax, [rsp+378h+var_308]
0x1800d694c  mov     qword ptr [rsp+378h+ArgList], rax
0x1800d6951  lea     rax, [rsp+378h+var_2E8]
0x1800d6959  mov     [rsp+378h+Format], rax
0x1800d695e  lea     r9, [rsp+378h+var_2B0]
0x1800d6966  mov     r8, rsi
0x1800d6969  mov     rdx, rdi
0x1800d696c  lea     rcx, [rsp+378h+var_298]
0x1800d6974  call    LdrpInitializeExecutionOptions
0x1800d6979  mov     [rsp+378h+var_328], eax
0x1800d697d  test    eax, eax
0x1800d697f  jns     short loc_1800D69BD
0x1800d6981  mov     dword ptr [rsp+378h+var_348], eax
0x1800d6985  mov     eax, [r13+40h]
0x1800d6989  mov     dword ptr [rsp+378h+ArgList], eax; ArgList
0x1800d698d  lea     rax, aInitializingTh; "Initializing the execution options for "...
0x1800d6994  lea     r8, aLdrpinitialize_3; "LdrpInitializeProcess"
0x1800d699b  mov     edx, 17BDh; int
0x1800d69a0  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800d69a7  xor     r9d, r9d; int
0x1800d69aa  mov     [rsp+378h+Format], rax; Format
0x1800d69af  call    LdrpLogInternal
0x1800d69b4  mov     eax, [rsp+378h+var_328]
0x1800d69b8  jmp     loc_1800D6EB5
0x1800d69bd  mov     r15b, r14b
0x1800d69c0  mov     [rsp+378h+var_310], r15d
0x1800d69c5  mov     ebx, r14d
0x1800d69c8  mov     ecx, 2
0x1800d69cd  cmp     cs:LdrpImageExpansionMitigation, ecx
0x1800d69d3  jnz     short loc_1800D69DC
0x1800d69d5  mov     cs:LdrpIsHotPatchingEnabled, r14b
0x1800d69dc  test    [rdi+0BCh], cl
0x1800d69e2  jz      short loc_1800D69EB
0x1800d69e4  or      cs:LdrpDebugFlags, 1
0x1800d69eb  mov     rax, [r13+40h]
0x1800d69ef  mov     qword ptr [rsp+378h+ArgList], rax; ArgList
0x1800d69f4  lea     rax, aInitializingPr; "Initializing process 0x%p\n"
0x1800d69fb  mov     [rsp+378h+Format], rax; Format
0x1800d6a00  mov     r9d, ecx; int
0x1800d6a03  lea     rsi, aLdrpinitialize_3; "LdrpInitializeProcess"
0x1800d6a0a  mov     r8, rsi; int
0x1800d6a0d  mov     edx, 17F7h; int
0x1800d6a12  lea     r14, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800d6a19  mov     rcx, r14; int
0x1800d6a1c  call    LdrpLogInternal
0x1800d6a21  mov     ecx, [r13+180Ch]
0x1800d6a28  xor     r13d, r13d
0x1800d6a2b  mov     eax, r13d
0x1800d6a2e  test    ecx, ecx
0x1800d6a30  setnle  al
0x1800d6a33  mov     cs:UseWOW64, eax
0x1800d6a39  test    r12, r12
0x1800d6a3c  jz      short loc_1800D6A77
0x1800d6a3e  mov     eax, 10Bh
0x1800d6a43  cmp     [r12+18h], ax
0x1800d6a49  jnz     short loc_1800D6A77
0x1800d6a4b  test    ecx, ecx
0x1800d6a4d  jg      short loc_1800D6A77
0x1800d6a4f  mov     cs:UseCOR, 1
0x1800d6a56  mov     rcx, [rdi+10h]
0x1800d6a5a  call    LdrpCorFixupImage
0x1800d6a5f  mov     [rsp+378h+var_328], eax
0x1800d6a63  test    eax, eax
0x1800d6a65  js      loc_1800D6EB5
0x1800d6a6b  lea     ebx, [r13+1]
0x1800d6a6f  mov     r15b, bl
0x1800d6a72  mov     [rsp+378h+var_310], r15d
0x1800d6a77  mov     [rsp+378h+var_220], r13
0x1800d6a7f  cmp     cs:UseWOW64, r13d
0x1800d6a86  jnz     short loc_1800D6AC7
0x1800d6a88  cmp     cs:UseCOR, r13b
0x1800d6a8f  jnz     short loc_1800D6AC7
0x1800d6a91  mov     r8d, 0Eh
0x1800d6a97  lea     r9, [rsp+378h+var_320]
0x1800d6a9c  mov     dl, 1
0x1800d6a9e  mov     rcx, [rdi+10h]
0x1800d6aa2  call    RtlImageDirectoryEntryToData
0x1800d6aa7  test    rax, rax
0x1800d6aaa  jz      short loc_1800D6AC7
0x1800d6aac  mov     ecx, 1
0x1800d6ab1  mov     cs:UseCOR, cl
0x1800d6ab7  test    [rax+10h], cl
0x1800d6aba  movzx   r15d, r15b
0x1800d6abe  cmovnz  r15d, ecx
0x1800d6ac2  mov     [rsp+378h+var_310], r15d
  ... truncated ...
```
