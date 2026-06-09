# LdrpInitializeProcess

- ea: `0x180050718`
- end: `0x1800526d2`
- name: `LdrpInitializeProcess`
- size: `8122`
- prototype: ``
- caller_count: `1`
- callee_count: `108`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004ff78`

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
- `0x1800254d0`
- `0x1800259ec`
- `0x180025a40`
- `0x180025abc`
- `0x180025d80`
- `0x180025fb4`
- `0x18002630c`
- `0x180026648`
- `0x180029a60`
- `0x18002a5b0`
- `0x18002b9f0`
- `0x180033f10`
- `0x180035ab0`
- `0x180035fd0`
- `0x180036fa0`
- `0x18004e6b4`
- `0x18004e790`
- `0x18004f700`
- `0x18004f828`
- `0x18004f8e4`
- `0x180050308`
- `0x180050718`
- `0x180052700`
- `0x18005276c`
- `0x180052804`
- `0x180052c24`
- `0x180052ce4`
- `0x18005363c`
- `0x180053670`
- `0x1800536f0`
- `0x1800539a4`
- `0x180058fb0`
- `0x180059930`
- `0x18005f0fc`
- `0x1800635b8`
- `0x180069220`
- `0x1800694f0`
- `0x180069950`
- `0x18006d980`
- `0x18006dcf4`
- `0x180070370`

## string_xrefs

- `0x1800507cf`: `\KnownDlls`
- `0x180050fab`: `NTDLL!`
- `0x1800516b6`: `Beginning execution of %wZ (%wZ)\n	Current directory: %wZ\n	Package directories: %wZ\n`
- `0x1800520be`: `Allocating a buffer to hold the current working directory failed\n`
- `0x18005204d`: `Querying the known DLL directory link object failed with status 0x%08lx\n`
- `0x180051d67`: `Failed to open %wZ with status 0x%08lx\n`
- `0x180051f3a`: `Allocating a data table entry for the application verifier DLL failed\n`
- `0x1800522f5`: `Initializing the current directory to "%wZ" failed with status 0x%08lx\n`
- `0x180052611`: `DllMain of MSCOREE (or its dependents) failed with status 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall LdrpInitializeProcess(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  struct _TEB *v3; // r13
  _PEB *ProcessEnvironmentBlock; // rdi
  int v5; // r15d
  bool v6; // cc
  _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rcx
  wchar_t *Buffer; // rdx
  __int16 v9; // bx
  __int64 v10; // r12
  __int64 v11; // rdx
  __int64 v12; // rcx
  char v13; // al
  int v14; // ebx
  __int64 v15; // rdx
  int WowTebOffset; // ecx
  __int64 v17; // r13
  _DWORD *Config; // r15
  __int64 result; // rax
  char v20; // al
  void *ProcessHeap; // r12
  __int64 v22; // rax
  int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // eax
  _RTL_USER_PROCESS_PARAMETERS *v26; // r15
  __int64 NtSystemRoot; // rax
  __int16 v28; // bx
  __int64 Heap_0; // rax
  int v30; // r13d
  __int64 v31; // rcx
  char v32; // r12
  unsigned __int64 v33; // rbx
  unsigned __int64 v34; // r15
  __int16 v35; // dx
  __int64 v36; // rcx
  unsigned __int64 v37; // rdx
  __int64 v38; // rcx
  _WORD *v39; // rbx
  __int64 v40; // rdx
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 v43; // r15
  int v44; // eax
  unsigned __int64 v45; // rax
  __int64 v46; // rcx
  int inited; // eax
  __int64 v48; // rax
  __int64 v49; // rcx
  char v50; // r12
  void *ImageBaseAddress; // rcx
  __int64 v52; // rbx
  __int64 v53; // rcx
  struct _TEB *v54; // r15
  int v55; // eax
  int v56; // eax
  int v57; // eax
  _DWORD *v58; // r13
  _RTL_USER_PROCESS_PARAMETERS *v59; // rax
  int v60; // eax
  __int64 v61; // rcx
  void (*PostProcessInitRoutine)(void); // rax
  int v68; // eax
  const char *i; // rcx
  __int64 v74; // rax
  int v75; // edx
  _BYTE *v76; // rbx
  unsigned __int64 v77; // rbx
  char *Format; // rax
  int v79; // edx
  UNICODE_STRING DosPath; // xmm1
  _WORD *v81; // xmm0_8
  wchar_t *v82; // rbx
  __int64 v83; // rax
  __int64 v84; // rdx
  __int16 v85; // cx
  __int64 ModuleEntry; // rax
  _QWORD *v87; // rbx
  int v88; // eax
  char ArgList; // [rsp+28h] [rbp-350h]
  char ArgLista; // [rsp+28h] [rbp-350h]
  __int64 *ArgListb; // [rsp+28h] [rbp-350h]
  int ApplicationKeyOption; // [rsp+50h] [rbp-328h] BYREF
  _BYTE v93[4]; // [rsp+54h] [rbp-324h] BYREF
  __int64 v94; // [rsp+58h] [rbp-320h] BYREF
  int v95; // [rsp+60h] [rbp-318h]
  __int64 v96; // [rsp+68h] [rbp-310h] BYREF
  _RTL_USER_PROCESS_PARAMETERS *v97; // [rsp+70h] [rbp-308h] BYREF
  struct _TEB *v98; // [rsp+78h] [rbp-300h] BYREF
  __m128i v99; // [rsp+80h] [rbp-2F8h] BYREF
  HANDLE v100[2]; // [rsp+90h] [rbp-2E8h] BYREF
  __m128i ImagePathName; // [rsp+A0h] [rbp-2D8h] BYREF
  UNICODE_STRING v102; // [rsp+B0h] [rbp-2C8h] BYREF
  __int64 v103; // [rsp+C0h] [rbp-2B8h]
  __int64 v104; // [rsp+C8h] [rbp-2B0h] BYREF
  HANDLE v105; // [rsp+D0h] [rbp-2A8h] BYREF
  _WORD v106[2]; // [rsp+D8h] [rbp-2A0h] BYREF
  int v107; // [rsp+DCh] [rbp-29Ch]
  __int64 v108; // [rsp+E0h] [rbp-298h]
  __int128 v109; // [rsp+E8h] [rbp-290h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+100h] [rbp-278h] BYREF
  HANDLE Handle; // [rsp+110h] [rbp-268h] BYREF
  __int64 v112; // [rsp+118h] [rbp-260h]
  __m128i v113; // [rsp+120h] [rbp-258h] BYREF
  __int64 SystemInformation; // [rsp+130h] [rbp-248h] BYREF
  __int64 v115; // [rsp+138h] [rbp-240h] BYREF
  _DWORD *pShimData; // [rsp+140h] [rbp-238h]
  _QWORD v117[2]; // [rsp+148h] [rbp-230h] BYREF
  _BYTE v118[48]; // [rsp+158h] [rbp-220h] BYREF
  _QWORD v119[3]; // [rsp+188h] [rbp-1F0h] BYREF
  _QWORD v120[2]; // [rsp+1A0h] [rbp-1D8h] BYREF
  __int128 v121; // [rsp+1B0h] [rbp-1C8h]
  __int128 v122; // [rsp+1C0h] [rbp-1B8h]
  __int128 v123; // [rsp+1D0h] [rbp-1A8h]
  __int64 v124; // [rsp+1E0h] [rbp-198h]
  __m128i v125; // [rsp+1F0h] [rbp-188h] BYREF
  _BYTE *v126; // [rsp+200h] [rbp-178h]
  int v127; // [rsp+210h] [rbp-168h]
  int *p_ApplicationKeyOption; // [rsp+218h] [rbp-160h]
  _BYTE v129[128]; // [rsp+2C0h] [rbp-B8h] BYREF

  v2 = a2;
  v103 = a2;
  v112 = a1;
  ApplicationKeyOption = 0;
  UnicodeString = 0;
  ImagePathName = 0;
  v113 = 0;
  v107 = 0;
  v104 = 0;
  v102 = 0;
  v109 = 0;
  v115 = 0;
  Handle = 0;
  memset(v118, 0, 44);
  v117[0] = 1441812;
  v117[1] = L"\\KnownDlls";
  v105 = 0;
  v100[0] = 0;
  v96 = 0;
  memset_thunk_772440563353939046(&v125, 0, 0xD0u);
  v99 = 0;
  memset_thunk_772440563353939046(v129, 0, 0x80u);
  SystemInformation = 0;
  RtlpUnhandledExceptionFilter = RtlEncodePointer(0);
  v3 = NtCurrentTeb();
  v98 = v3;
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
  *((_QWORD *)&v109 + 1) = Buffer;
  LOWORD(v109) = ProcessParameters->ImagePathName.Length;
  v9 = v109;
  WORD1(v109) = v109 + 2;
  if ( (unsigned __int16)v109 >= 8u && *Buffer == 92 )
  {
    if ( Buffer[1] == 63 && Buffer[2] == 63 && Buffer[3] == 92 )
    {
      LOWORD(v109) = v109 - 8;
      WORD1(v109) = v9 - 6;
      *((_QWORD *)&v109 + 1) = Buffer + 4;
      ProcessParameters->ImagePathName.Length -= 8;
      ProcessParameters->ImagePathName.MaximumLength -= 8;
      ProcessParameters->ImagePathName.Buffer += 4;
    }
    v2 = v103;
  }
  UseCOR = 0;
  LODWORD(v94) = 0;
  RtlImageNtHeaderEx(3, ProcessEnvironmentBlock->ImageBaseAddress, 0, &v104);
  v10 = v104;
  LdrpAppHeaders = v104;
  if ( LdrpIsSecureProcess && (*(_BYTE *)(v104 + 22) & 0x20) == 0 )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      5784,
      (int)"LdrpInitializeProcess",
      0,
      "Secure processes must be large address aware\n",
      ArgList);
    return 3221225659LL;
  }
  v11 = 0;
  v12 = 0;
  do
  {
    LdrpHashTable[v12 + 1] = (__int64)&LdrpHashTable[v12];
    LdrpHashTable[v12] = (__int64)&LdrpHashTable[v12];
    ++v11;
    v12 += 2;
  }
  while ( v11 != 32 );
  LdrpInitializeExceptionTable(v2);
  LdrpCaptureCriticalThunks();
  LdrProtectMrdata(1);
  if ( (unsigned int)LdrControlFlowGuardEnforcedWithExportSuppression() == 1 )
    LdrpSuppressedExportOverrideListPtr = (__int64)&LdrpSuppressedExportOverrideList;
  v13 = ((unsigned __int8)qword_1801E3508 >> 4) & 3;
  LdrpEnforceIntegrityContinuity = v13 == 1;
  LdrpAuditIntegrityContinuity = ((v13 - 1) & 0xFD) == 0;
  ApplicationKeyOption = LdrpInitializeExecutionOptions(
                           (unsigned int)&v109,
                           (_DWORD)ProcessEnvironmentBlock,
                           v2,
                           (unsigned int)&v105,
                           (__int64)v100,
                           (__int64)&v96);
  if ( ApplicationKeyOption < 0 )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      5933,
      (int)"LdrpInitializeProcess",
      0,
      "Initializing the execution options for the process %lx failed with status 0x%08lx\n",
      (char)v3->ClientId.UniqueProcess);
    return (unsigned int)ApplicationKeyOption;
  }
  LOBYTE(v5) = 0;
  v95 = v5;
  v14 = 0;
  if ( LdrpImageExpansionMitigation == 2 )
    LdrpIsHotPatchingEnabled = 0;
  if ( (ProcessEnvironmentBlock->NtGlobalFlag & 2) != 0 )
    LdrpDebugFlags |= 1u;
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrinit.c",
    5991,
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
    v14 = 1;
    LOBYTE(v5) = 1;
    v95 = v5;
  }
  pShimData = 0;
  if ( !UseWOW64 && !UseCOR )
  {
    LOBYTE(v15) = 1;
    v22 = RtlImageDirectoryEntryToData(ProcessEnvironmentBlock->ImageBaseAddress, v15, 14, &v97);
    if ( v22 )
    {
      UseCOR = 1;
      v5 = (unsigned __int8)v5;
      if ( (*(_BYTE *)(v22 + 16) & 1) != 0 )
        v5 = 1;
      v95 = v5;
    }
  }
  LdrpSystemDllBase = v103;
  if ( !UseWOW64 )
    pShimData = ProcessEnvironmentBlock->pShimData;
  RtlpTimeout = ProcessEnvironmentBlock->CriticalSectionTimeout;
  v17 = RtlNormalizeProcessParams(ProcessEnvironmentBlock->ProcessParameters);
  ImagePathName = *(__m128i *)(v17 + 96);
  if ( UseWOW64 || UseCOR && v14 )
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
  result = RtlpInitDeferredCriticalSection();
  ApplicationKeyOption = result;
  if ( (int)result < 0 )
    return result;
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
    v76 = qword_1801C6228;
    RtlSetVolatileMemory(qword_1801C6228, 255, 2u);
    v76[2] |= 7u;
  }
  *((_BYTE *)qword_1801C6228 + 2) |= 1u;
  if ( (ProcessEnvironmentBlock->NtGlobalFlag & 0x1000) != 0 || (v20 = LdrpShouldCreateStackTraceDb) != 0 )
  {
    LODWORD(v97) = 24;
    if ( (int)LdrQueryImageFileExecutionOptions(
                (unsigned int)&v109,
                (unsigned int)L"StackTraceDatabaseSizeInMb",
                4,
                (unsigned int)&v97,
                4,
                0) < 0
      || (unsigned int)v97 < 0x18 )
    {
      v77 = 25165824;
    }
    else if ( (unsigned int)v97 <= 0x80 )
    {
      v77 = (unsigned int)((_DWORD)v97 << 20);
    }
    else
    {
      v77 = 0x8000000;
    }
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      6240,
      (int)"LdrpInitializeProcess",
      2,
      "Stack trace database size is %Id Mb\n",
      v77 >> 20);
    v119[0] = 0;
    v119[1] = 0;
    v119[2] = v77;
    ApplicationKeyOption = RtlControlStackTraceDataBase(0, 24, v119);
    v20 = LdrpShouldCreateStackTraceDb;
    v10 = v104;
  }
  if ( (ProcessEnvironmentBlock->NtGlobalFlag & 0x1000) != 0 || v20 )
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
  result = RtlInitializeHeapManager(&v109);
  ApplicationKeyOption = result;
  if ( (int)result < 0 )
    return result;
  if ( (((unsigned __int64)qword_1801E3500 >> 12) & 3) == 1 )
    RtlSetHeapInformation(0, 1, 0, 0);
  ApplicationKeyOption = LdrpInitializeProcessHeap(Config, v10, v17, &ProcessEnvironmentBlock->ProcessHeap);
  if ( ApplicationKeyOption < 0 )
  {
    Format = "Creating the process heap failed\n";
    v79 = 6313;
LABEL_227:
    LdrpLogInternal((int)"minkernel\\ldr\\ldrinit.c", v79, (int)"LdrpInitializeProcess", 0, Format, ArgLista);
    return 3221225495LL;
  }
  ProcessHeap = ProcessEnvironmentBlock->ProcessHeap;
  dword_1801CBE98 = 2;
  if ( (unsigned int)Feature_Servicing_LoaderSnapsBuffer__private_IsEnabledDeviceUsageNoInline() )
    LdrpInitializeSnapsBuffer();
  RtlInitializeCriticalSectionEx(LdrpEnclaveListLock, 0, 0);
  qword_1801CC368 = (__int64)&LdrpEnclaveList;
  LdrpEnclaveList = (__int64)&LdrpEnclaveList;
  if ( (ProcessEnvironmentBlock->NtGlobalFlag & 0x800000) != 0 )
    RtlInitializeExceptionLog();
  RtlpInitializeThreadActivationContextStack(v98);
  LdrpHeap = (__int64)ProcessHeap;
  if ( ((unsigned __int8)&EtwpFreeRegistrationList & 0xF) != 0 )
    RtlRaiseStatus(2147483650LL);
  EtwpFreeRegistrationList = 0;
  PrivateLoggerNotificationEntry = 0;
  if ( NtQuerySystemInformation(SystemHypervisorSharedPageInformation, &SystemInformation, 8u, 0) >= 0 )
    RtlpHypervisorSharedUserVa = SystemInformation;
  NtdllBaseTag = RtlCreateTagHeap(ProcessHeap);
  result = TpInitializePackage();
  ApplicationKeyOption = result;
  if ( (int)result < 0 )
    return result;
  if ( *(_DWORD *)(v17 + 1080) )
    TpSetDefaultPoolCpuSets(*(void **)(v17 + 1072));
  v23 = *(_DWORD *)(v17 + 1084);
  if ( v23 )
  {
    RtlAcquireSRWLockExclusive(&TppPoolpGlobalPoolLock);
    TppPoolpGlobalPoolMaxThreadsOverride = v23;
    RtlReleaseSRWLockExclusive(&TppPoolpGlobalPoolLock);
  }
  if ( !UseWOW64 && !LdrpIsSecureProcess )
    LdrpEnableUMGLTracingStateSync();
  TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation(&dword_1801C4700);
  v24 = EtwNotificationRegister(
          (unsigned int)&PrivateLoggerNotificationGuid,
          3,
          0,
          0,
          (__int64)&g_hPrivLoggerNotificationProvider);
  if ( v24 )
    RtlSetLastWin32Error(v24);
  v25 = EtwNotificationRegister(
          (unsigned int)UserDiagnosticGuid,
          3,
          (unsigned int)UserDiagnosticProviderCallback,
          0,
          (__int64)&g_hUserDiagnosticProvider);
  if ( v25 )
    RtlSetLastWin32Error(v25);
  RtlInitializeHeapLogging();
  result = RtlpInitEnvironmentBlock();
  ApplicationKeyOption = result;
  if ( (int)result < 0 )
    return result;
  result = RtlpInitParameterBlock();
  ApplicationKeyOption = result;
  if ( (int)result < 0 )
    return result;
  v26 = ProcessEnvironmentBlock->ProcessParameters;
  v97 = v26;
  ImagePathName = (__m128i)v26->ImagePathName;
  *((_QWORD *)&v109 + 1) = _mm_srli_si128(ImagePathName, 8).m128i_u64[0];
  if ( v105 || v100[0] )
  {
    ApplicationKeyOption = RtlQueryApplicationKeyOption(
                             v100[0],
                             (_DWORD)v105,
                             (unsigned int)L"DebugProcessHeapOnly",
                             4,
                             (__int64)&v94,
                             4);
    if ( ApplicationKeyOption >= 0 && dword_1801C4588 && (_DWORD)v94 )
    {
      dword_1801C4588 = 0;
      *(_DWORD *)RtlpDebugPageHeapTable &= ~0x400u;
    }
  }
  NtSystemRoot = RtlGetNtSystemRoot();
  RtlInitUnicodeStringEx(&v102, NtSystemRoot);
  v28 = v102.Length + 40;
  Heap_0 = RtlAllocateHeap_0(ProcessHeap, 0, (unsigned int)v102.Length + 38 + 2LL);
  if ( !Heap_0 )
    return 3221225495LL;
  v106[0] = 0;
  v106[1] = v28;
  v108 = Heap_0;
  RtlAppendUnicodeStringToString(v106, &v102);
  RtlAppendUnicodeStringToString(v106, &SlashSystem32SlashString);
  if ( (ProcessEnvironmentBlock->BitField & 2) == 0 )
  {
    LODWORD(v94) = 0;
    v41 = 48;
    *(_DWORD *)v118 = 48;
    *(_QWORD *)&v118[8] = 0;
    *(_DWORD *)&v118[24] = 64;
    *(_QWORD *)&v118[16] = v117;
    *(_OWORD *)&v118[32] = 0;
    LdrProtectMrdata(0);
    ApplicationKeyOption = ZwOpenDirectoryObject(&LdrpKnownDllDirectoryHandle, 3, v118);
    LdrProtectMrdata(1);
    if ( ApplicationKeyOption < 0 )
    {
      ArgListb = v117;
      v75 = 6608;
    }
    else
    {
      *(_DWORD *)v118 = 48;
      *(_QWORD *)&v118[8] = LdrpKnownDllDirectoryHandle;
      *(_DWORD *)&v118[24] = 64;
      *(_QWORD *)&v118[16] = &qword_1801707D0;
      *(_OWORD *)&v118[32] = 0;
      ApplicationKeyOption = ZwOpenSymbolicLinkObject(&Handle, 1, v118);
      if ( ApplicationKeyOption >= 0 )
      {
        while ( 1 )
        {
          v42 = RtlAllocateHeap_0(ProcessHeap, 0, v41);
          v43 = v42;
          if ( !v42 )
            return 3221225495LL;
          LdrpKnownDllPath = 0;
          word_1801CA852 = v41;
          qword_1801CA858 = v42;
          v44 = NtQuerySymbolicLinkObject(Handle, &LdrpKnownDllPath, &v94);
          ApplicationKeyOption = v44;
          if ( v44 >= 0 )
            break;
          if ( v44 != -1073741789 )
          {
            LdrpLogInternal(
              (int)"minkernel\\ldr\\ldrinit.c",
              6666,
              (int)"LdrpInitializeProcess",
              0,
              "Querying the known DLL directory link object failed with status 0x%08lx\n",
              v44);
            return (unsigned int)ApplicationKeyOption;
          }
          RtlFreeHeap_0(ProcessHeap, 0, v43);
          v41 = (unsigned int)v94;
        }
        NtClose(Handle);
        v26 = v97;
        goto LABEL_96;
      }
      ArgListb = &qword_1801707D0;
      v75 = 6631;
    }
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      v75,
      (int)"LdrpInitializeProcess",
      0,
      "Failed to open %wZ with status 0x%08lx\n",
      (char)ArgListb);
    return (unsigned int)ApplicationKeyOption;
  }
LABEL_96:
  v30 = 1;
  if ( UseWOW64 || LdrpIsSecureProcess )
  {
    UnicodeString = v102;
  }
  else
  {
    DosPath = v26->CurrentDirectory.DosPath;
    UnicodeString = DosPath;
    v81 = (_WORD *)_mm_srli_si128((__m128i)DosPath, 8).m128i_u64[0];
    if ( !v81 || !(unsigned __int16)_mm_cvtsi128_si32((__m128i)DosPath) || !*v81 )
    {
      v82 = (wchar_t *)RtlAllocateHeap_0(ProcessHeap, 0, 8);
      UnicodeString.Buffer = v82;
      if ( !v82 )
      {
        Format = "Allocating a buffer to hold the current working directory failed\n";
        v79 = 6718;
        goto LABEL_227;
      }
      v30 = 0;
      v83 = RtlGetNtSystemRoot();
      *(_DWORD *)v82 = *(_DWORD *)v83;
      v82[2] = *(_WORD *)(v83 + 4);
      UnicodeString.Buffer[3] = 0;
      *(_DWORD *)&UnicodeString.Length = 524294;
    }
  }
  LdrpInitializePolicy();
  if ( (ProcessEnvironmentBlock->ProcessParameters->Flags & 0x20000000) != 0 )
  {
    v32 = LdrpIncludeAlternateForwarders(v31, v106[0]);
    v33 = 2 * v84 + 22;
    if ( v32 )
      v33 = v84 + 2 * v84 + 52;
  }
  else
  {
    v32 = 0;
    v33 = v106[0];
  }
  if ( (LdrpPolicyBits & 1) != 0 )
  {
    v34 = v33;
  }
  else
  {
    v34 = v33 + 2 * (v102.Length + 9LL);
    if ( (ProcessEnvironmentBlock->BitField & 2) != 0 )
      v97->DllPath.Length = 0;
  }
  v99.m128i_i64[1] = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, v34);
  if ( !v99.m128i_i64[1] )
  {
    Format = "Failed to allocate the system dirs string!\n";
    v79 = 6811;
    goto LABEL_227;
  }
  v99.m128i_i16[0] = 0;
  v99.m128i_i16[1] = v34;
  RtlAppendUnicodeStringToString(&v99, v106);
  v35 = v99.m128i_i16[0];
  v36 = v99.m128i_i64[1];
  *(_WORD *)(v99.m128i_i64[1] + 2 * ((unsigned __int64)v99.m128i_u16[0] >> 1) - 2) = 59;
  RtlpSystem32Dirs = (__int128)v99;
  word_1801CA942 = _mm_extract_epi16(v99, 1);
  dword_1801CA944 = v99.m128i_i32[1];
  qword_1801CA948 = v36;
  LdrpSystem32 = v35 - 2;
  if ( (ProcessEnvironmentBlock->ProcessParameters->Flags & 0x20000000) != 0 )
  {
    if ( v32 )
    {
      RtlAppendUnicodeStringToString(&v99, v106);
      RtlAppendUnicodeToString(&v99, L"forwarders\\alt;");
    }
    RtlAppendUnicodeStringToString(&v99, v106);
    RtlAppendUnicodeToString(&v99, L"forwarders;");
  }
  if ( v34 > v33 )
  {
    RtlAppendUnicodeStringToString(&v99, &v102);
    RtlAppendUnicodeToString(&v99, L"\\system;");
    RtlAppendUnicodeStringToString(&v99, &v102);
    RtlAppendUnicodeToString(&v99, L";");
    RtlpSystemDirs = (__int128)v99;
  }
  if ( (unsigned int)(LdrpIllegalCWDDevices - 1) <= 0xFFFFFFFD )
    LdrpCheckAppDirType(&ImagePathName);
  result = LdrpInitializeNtdllDataTableEntry(v103, &LdrpNtDllDataTableEntry, 0, v106);
  ApplicationKeyOption = result;
  if ( (int)result < 0 )
    return result;
  v37 = 0;
  v38 = ImagePathName.m128i_u16[0] + ImagePathName.m128i_i64[1];
  v39 = (_WORD *)v38;
  if ( v38 )
  {
    while ( 1 )
    {
      v45 = (unsigned __int64)v39--;
      if ( v45 <= ImagePathName.m128i_i64[1] )
        break;
      if ( *v39 == 92 )
      {
        v37 = v45;
        break;
      }
    }
  }
  if ( v37 )
  {
    v85 = v38 - v37;
    v113.m128i_i16[0] = v85;
    if ( ImagePathName.m128i_u16[1] - (unsigned __int64)ImagePathName.m128i_u16[0] >= 2 )
      v85 += 2;
    v113.m128i_i16[1] = v85;
    v113.m128i_i64[1] = v37;
  }
  else
  {
    v113 = ImagePathName;
  }
  if ( *(int *)(LdrpNtdllHotPatchContext + 8) < 0 && LdrpIsHotPatchingEnabled )
    __fastfail(0x45u);
  v94 = 0;
  if ( *(_QWORD *)LdrpNtdllHotPatchContext )
  {
    result = LdrpInitializeNtdllDataTableEntry(*(_QWORD *)LdrpNtdllHotPatchContext, &v94, LdrpNtDllDataTableEntry, 0);
    ApplicationKeyOption = result;
    if ( (int)result < 0 )
      return result;
  }
  RtlInitializeHistoryTable();
  v40 = qword_1801CA8F0;
  if ( *(__int64 **)(qword_1801CA8F0 + 8) != &qword_1801CA8F0 )
    goto LABEL_115;
  v46 = LdrpNtDllDataTableEntry + 32;
  *(_QWORD *)(LdrpNtDllDataTableEntry + 32) = qword_1801CA8F0;
  *(_QWORD *)(v46 + 8) = &qword_1801CA8F0;
  *(_QWORD *)(v40 + 8) = v46;
  qword_1801CA8F0 = v46;
  if ( v94 )
  {
    if ( *(__int64 **)(v46 + 8) != &qword_1801CA8F0 )
LABEL_115:
      __fastfail(3u);
    v74 = v94 + 32;
    *(_QWORD *)(v94 + 32) = v46;
    *(_QWORD *)(v74 + 8) = &qword_1801CA8F0;
    *(_QWORD *)(v46 + 8) = v74;
    qword_1801CA8F0 = v74;
  }
  inited = LdrpInitParallelLoadingSupport();
  ApplicationKeyOption = inited;
  if ( inited < 0 )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      7042,
      (int)"LdrpInitializeProcess",
      0,
      "Failed to initialize Parallel loader, st = 0x%x\n",
      inited);
    return (unsigned int)ApplicationKeyOption;
  }
  LdrpDrainWorkQueue(0);
  memset_thunk_772440563353939046(v129, 0, 0x80u);
  memset_thunk_772440563353939046(&v125, 0, 0xD0u);
  v126 = v129;
  v127 = 512;
  v125 = ImagePathName;
  p_ApplicationKeyOption = &ApplicationKeyOption;
  v48 = LdrpAllocateModuleEntry(&v125);
  if ( !v48 )
  {
    Format = "Allocating a data table entry for the executable failed\n";
    v79 = 7063;
    goto LABEL_227;
  }
  LdrpImageEntry = v48;
  *(_DWORD *)(*(_QWORD *)(v48 + 152) + 24LL) = -1;
  *(_DWORD *)(*(_QWORD *)(v48 + 152) + 24LL) = -1;
  *(_WORD *)(**(_QWORD **)(LdrpImageEntry + 152) - 52LL) = -1;
  v49 = LdrpImageEntry;
  *(__m128i *)(LdrpImageEntry + 72) = ImagePathName;
  *(_DWORD *)(v49 + 104) |= 4u;
  if ( (ProcessEnvironmentBlock->BitField & 0x10) != 0 )
    *(_DWORD *)(LdrpImageEntry + 104) |= 1u;
  v50 = v95;
  if ( UseCOR )
  {
    *(_DWORD *)(LdrpImageEntry + 104) |= 0x400000u;
    if ( v50 )
      *(_DWORD *)(LdrpImageEntry + 104) |= 0x1000000u;
  }
  if ( (ProcessEnvironmentBlock->BitField & 4) != 0 )
    *(_QWORD *)(LdrpImageEntry + 248) = 0;
  *(__m128i *)(LdrpImageEntry + 88) = v113;
  ImageBaseAddress = ProcessEnvironmentBlock->ImageBaseAddress;
  v52 = v104;
  if ( *(void **)(v104 + 48) != ImageBaseAddress && !v50 && !UseWOW64 )
  {
    result = LdrpProtectAndRelocateImage((char)ImageBaseAddress);
    ApplicationKeyOption = result;
    if ( (int)result < 0 )
      return result;
  }
  v53 = LdrpImageEntry;
  *(_QWORD *)(LdrpImageEntry + 48) = ProcessEnvironmentBlock->ImageBaseAddress;
  LdrpInsertDataTableEntry(v53);
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrinit.c",
    7155,
    (int)"LdrpInitializeProcess",
    2,
    "Beginning execution of %wZ (%wZ)\n\tCurrent directory: %wZ\n\tPackage directories: %wZ\n",
    LdrpImageEntry + 88);
  LdrpLogDllState(*(_QWORD *)(LdrpImageEntry + 48), LdrpImageEntry + 72, 5285);
  LdrpInsertModuleToIndex(LdrpImageEntry, v52);
  result = LdrpProcessMappedModule(LdrpImageEntry, 0, UseWOW64 == 0);
  ApplicationKeyOption = result;
  if ( (int)result < 0 )
    return result;
  *(_DWORD *)(*(_QWORD *)(LdrpImageEntry + 152) + 56LL) = 9;
  ApplicationKeyOption = RtlpInitCurrentDir(&UnicodeString);
  if ( ApplicationKeyOption < 0 )
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      7192,
      (int)"LdrpInitializeProcess",
      0,
      "Initializing the current directory to \"%wZ\" failed with status 0x%08lx\n",
      (char)&UnicodeString);
  if ( !v30 )
    RtlFreeAnsiString(&UnicodeString);
  if ( !AvrfAppVerifierMode )
    goto LABEL_143;
  ModuleEntry = LdrpAllocateModuleEntry(0);
  v87 = (_QWORD *)ModuleEntry;
  if ( !ModuleEntry )
  {
    Format = "Allocating a data table entry for the application verifier DLL failed\n";
    v79 = 7217;
    goto LABEL_227;
  }
  *(_DWORD *)(*(_QWORD *)(ModuleEntry + 152) + 24LL) = -1;
  *(_WORD *)(**(_QWORD **)(ModuleEntry + 152) - 52LL) = -1;
  *(_DWORD *)(ModuleEntry + 104) |= *(_DWORD *)(v96 + 104);
  *(_QWORD *)(ModuleEntry + 248) = *(_QWORD *)(v96 + 248);
  *(_WORD *)(ModuleEntry + 110) = 0;
  *(_OWORD *)(ModuleEntry + 72) = *(_OWORD *)(v96 + 72);
  *(_OWORD *)(ModuleEntry + 88) = *(_OWORD *)(v96 + 88);
  *(_DWORD *)(ModuleEntry + 128) = *(_DWORD *)(v96 + 128);
  *(_DWORD *)(ModuleEntry + 288) = *(_DWORD *)(v96 + 288);
  *(_QWORD *)(ModuleEntry + 48) = *(_QWORD *)(v96 + 48);
  LdrpInsertDataTableEntry(ModuleEntry);
  LdrpLogDllState(v87[6], v87 + 9, 5285);
  result = RtlImageNtHeaderEx(3, v87[6], 0, &v115);
  ApplicationKeyOption = result;
  if ( (int)result < 0 )
    return result;
  LdrpInsertModuleToIndex(v87, v115);
  result = LdrpProcessMappedModule(v87, 0, 1);
  ApplicationKeyOption = result;
  if ( (int)result < 0 )
    return result;
  v87[7] = *(_QWORD *)(v96 + 56);
  LdrpLogDllState(v87[6], v87 + 9, 5293);
  *(_DWORD *)(v87[19] + 56LL) = 7;
  if ( (ProcessEnvironmentBlock->NtGlobalFlag & 0x100) == 0 && (AvrfAppVerifierMode & 2) == 0 )
  {
    v93[0] = 0;
    result = LdrpInitializeGraphRecurse(v87[19], 0, v93);
    ApplicationKeyOption = result;
  }
  else
  {
    result = AVrfInitializeVerifier(0, 0, 0, 1, v103, 0);
    ApplicationKeyOption = result;
    if ( (int)result < 0 )
      return result;
    if ( (AvrfAppVerifierMode & 2) != 0 )
    {
      *(_DWORD *)(v87[19] + 56LL) = 9;
      result = (unsigned int)ApplicationKeyOption;
    }
  }
  if ( (int)result < 0 )
    return result;
  v52 = v104;
LABEL_143:
  LdrpDropLastInProgressCount();
  if ( !UseWOW64 )
  {
    LdrpInitializeCfgScpHelpers();
    LdrpSchedulerSharedDataListHeadLock = 0;
    qword_1801CA998 = (__int64)&LdrpSchedulerSharedDataListHead;
    LdrpSchedulerSharedDataListHead = (__int64)&LdrpSchedulerSharedDataListHead;
    LdrpAllocateSchedulerSharedData();
    v54 = v98;
    LdrpAcquireSchedulerSharedDataSlot(v98);
    v98 = 0;
    if ( UseCOR )
    {
      result = LdrpCorInitialize(&v98);
      ApplicationKeyOption = result;
      if ( (int)result < 0 )
        return result;
      if ( v50 )
      {
        result = LdrpCorValidateImage(ProcessEnvironmentBlock->ImageBaseAddress);
        ApplicationKeyOption = result;
        if ( (int)result < 0 )
          return result;
      }
      if ( (v54->SameTebFlags & 0x400) != 0 )
        *(_QWORD *)(v112 + 128) = __ROR8__(LdrpCorExeMainRoutine, 64 - (MEMORY[0x7FFE0330] & 0x3Fu))
                                ^ MEMORY[0x7FFE0330];
    }
    v55 = LdrpInitializeTls();
    ApplicationKeyOption = v55;
    if ( v55 < 0 )
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        7483,
        (int)"LdrpInitializeProcess",
        0,
        "Initializing TLS slots failed with status 0x%08lx\n",
        v55);
      return (unsigned int)ApplicationKeyOption;
    }
    if ( *(_BYTE *)(LdrpNtdllHotPatchContext + 12) )
      LdrpLogEtwHotPatchStatus(
        (unsigned int)&v113,
        LdrpNtDllDataTableEntry,
        0,
        *(_DWORD *)(LdrpNtdllHotPatchContext + 8),
        0);
    if ( v98 )
    {
      v93[0] = 0;
      v88 = LdrpInitializeGraphRecurse(*(_QWORD *)&v98->User32Reserved[6], 0, v93);
      ApplicationKeyOption = v88;
      if ( v88 < 0 )
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrinit.c",
          7520,
          (int)"LdrpInitializeProcess",
          0,
          "DllMain of MSCOREE (or its dependents) failed with status 0x%08lx\n",
          v88);
        return (unsigned int)ApplicationKeyOption;
      }
    }
    v56 = LdrpInitializeImportRedirection();
    ApplicationKeyOption = v56;
    if ( v56 < 0 )
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        7536,
        (int)"LdrpInitializeProcess",
        0,
        "Loading of import redirection module failed with status 0x%08x\n",
        v56);
      return (unsigned int)ApplicationKeyOption;
    }
    v98 = 0;
    if ( (unsigned __int16)(*(_WORD *)(v52 + 92) - 2) <= 1u )
    {
      v57 = LdrpInitializeKernel32Functions(&v98);
      ApplicationKeyOption = v57;
      if ( v57 < 0 )
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrinit.c",
          7558,
          (int)"LdrpInitializeProcess",
          0,
          "Calling LdrpInitializeKernel32Functions failed with status 0x%08lx\n",
          v57);
        return (unsigned int)ApplicationKeyOption;
      }
    }
    LdrpDrainWorkQueue(0);
    SbObtainTraceHandle(0);
    v58 = pShimData;
    if ( pShimData && pShimData[132] )
    {
      ProcessEnvironmentBlock->AppCompatInfo = 0;
      LdrpInitShimEngine(v58);
    }
    if ( (NtCurrentPeb()->AppCompatFlags.LowPart & 0x400000) != 0 )
      RtlpForceCSDebugInfoCreation = 1;
    v59 = v97;
    if ( (NtCurrentPeb()->AppCompatFlags.LowPart & 0x10000000) != 0 )
      v97->LoaderThreads = 1;
    LdrpEnableParallelLoading(v59->LoaderThreads);
    LdrInitState = 1;
    *(_DWORD *)(*(_QWORD *)(LdrpImageEntry + 152) + 56LL) = 2;
    *p_ApplicationKeyOption = 0;
    if ( v50 )
    {
      v60 = LdrpCorProcessImports(LdrpImageEntry);
    }
    else
    {
      LdrpThreadTokenSetMainThreadToken();
      v127 |= 1u;
      LdrpMapAndSnapDependency(&v125);
      LdrpDrainWorkQueue(1);
      if ( LdrpMainThreadToken )
        LdrpThreadTokenUnsetMainThreadToken();
      LOBYTE(v60) = ApplicationKeyOption;
      if ( ApplicationKeyOption < 0 )
        goto LABEL_188;
      v60 = LdrpPrepareModuleForExecution(LdrpImageEntry, p_ApplicationKeyOption);
    }
    ApplicationKeyOption = v60;
    if ( v60 >= 0 )
    {
      LdrInitState = 2;
      result = LdrpInitializePatchData();
      ApplicationKeyOption = result;
      if ( (int)result >= 0 )
      {
        if ( ProcessEnvironmentBlock->BeingDebugged )
          LdrpDoDebuggerBreak();
        LdrpDropLastInProgressCount();
        if ( !Kernel32ThreadInitThunkFunction
          || (result = Kernel32ThreadInitThunkFunction(1, 0, 0), ApplicationKeyOption = result, (int)result >= 0)
          && (result = LdrpInitializePerUserWindowsDirectory(v98), ApplicationKeyOption = result, (int)result >= 0) )
        {
          LdrpProcessInitContextRecord = v112;
          LdrpDrainWorkQueue(0);
          LdrpAcquireLoaderLock();
          v93[0] = 0;
          ApplicationKeyOption = LdrpInitializeGraphRecurse(
                                   *(_QWORD *)(LdrpImageEntry + 152),
                                   p_ApplicationKeyOption,
                                   v93);
          LdrpReleaseLoaderLock(v61, 9, (unsigned int)ApplicationKeyOption);
          LdrpFreeLoadContextOfNode(*(_QWORD *)(LdrpImageEntry + 152), p_ApplicationKeyOption);
          LdrpDropLastInProgressCount();
          LdrpProcessInitContextRecord = 0;
          LdrpReleaseDllPath(v129);
          if ( ApplicationKeyOption < 0 )
          {
            LdrpLogInternal(
              (int)"minkernel\\ldr\\ldrinit.c",
              7945,
              (int)"LdrpInitializeProcess",
              0,
              "Running the init routines of the executable's static imports failed with status 0x%08lx\n",
              ApplicationKeyOption);
            return (unsigned int)ApplicationKeyOption;
          }
          LdrpInitializeSmtDelayedSleep();
          if ( *(_WORD *)(LdrpImageEntry + 110) )
          {
            v120[0] = 72;
            v120[1] = 1;
            v121 = 0;
            v122 = 0;
            v123 = 0;
            v124 = 0;
            RtlActivateActivationContextUnsafeFast(v120, *(_QWORD *)(LdrpImageEntry + 136));
            LdrpCallTlsInitializers(1, LdrpImageEntry);
            RtlDeactivateActivationContextUnsafeFast(v120);
          }
          if ( g_ShimsEnabled
            && !((unsigned __int8 (__fastcall *)(__int128 *, _DWORD *))(__ROR8__(
                                                                          g_pfnSE_InstallAfterInit,
                                                                          64 - (MEMORY[0x7FFE0330] & 0x3Fu))
                                                                      ^ MEMORY[0x7FFE0330]))(
                  &v109,
                  v58) )
          {
            Feature_Arm64VcRedistRedirect__private_IsEnabledDeviceUsageNoInline();
            g_ShimsEnabled = 0;
            LdrUnloadDll(g_pShimEngineModule);
            g_pShimEngineModule = 0;
          }
          PostProcessInitRoutine = ProcessEnvironmentBlock->PostProcessInitRoutine;
          if ( PostProcessInitRoutine )
            PostProcessInitRoutine();
          goto LABEL_173;
        }
      }
      return result;
    }
LABEL_188:
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      7797,
      (int)"LdrpInitializeProcess",
      0,
      "Walking the import tables of the executable and its static imports failed with status 0x%08lx\n",
      v60);
    return (unsigned int)ApplicationKeyOption;
  }
  if ( v105 )
  {
    NtClose(v105);
    v105 = 0;
    if ( LdrpLargePageDllKeyHandle )
    {
      NtClose(LdrpLargePageDllKeyHandle);
      LdrpLargePageDllKeyHandle = 0;
    }
  }
  if ( v100[0] )
  {
    NtClose(v100[0]);
    v100[0] = 0;
  }
  result = LdrpLoadWow64(v106);
  ApplicationKeyOption = result;
  if ( (int)result >= 0 )
  {
    if ( ProcessEnvironmentBlock->BeingDebugged )
      LdrpDoDebuggerBreak();
    LdrInitState = 3;
    _interlockedbittestandreset((volatile signed __int32 *)&ProcessEnvironmentBlock->80, 1u);
    g_LdrpWow64LdrpInitialize(v112);
LABEL_173:
    if ( v105 )
      NtClose(v105);
    if ( v100[0] )
      NtClose(v100[0]);
    _RAX = 1;
    __asm { cpuid }
    x86_cpu_enable_ssse3 = _RCX & 0x200;
    if ( (_RDX & 0x4000000) == 0 || (_RCX & 0x100000) == 0 || (v68 = 1, (_RCX & 2) == 0) )
      v68 = 0;
    x86_cpu_enable_simd = v68;
    _RCX = MEMORY[0x7FFE029D];
    x86_cpu_enable_avx512 = MEMORY[0x7FFE029D];
    if ( MEMORY[0x7FFE029D] )
    {
      if ( v68 )
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
      LODWORD(v94) = 6815744;
      for ( i = "v104.0.0__2026-03-28T02:17:10+00:00_df5eaa1_2026-03-30T17:48:52"; *i; ++i )
        LOBYTE(v94) = *i;
      g_SymCryptCpuFeaturesPresentCheck = ~g_SymCryptCpuFeaturesNotPresent;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180050718  mov     r11, rsp
0x18005071b  mov     [r11+18h], rbx
0x18005071f  mov     [r11+20h], rsi
0x180050723  push    rdi
0x180050724  push    r12
0x180050726  push    r13
0x180050728  push    r14
0x18005072a  push    r15
0x18005072c  sub     rsp, 350h
0x180050733  mov     rax, cs:__security_cookie
0x18005073a  xor     rax, rsp
0x18005073d  mov     [rsp+378h+var_38], rax
0x180050745  mov     rsi, rdx
0x180050748  mov     [rsp+378h+var_2B8], rdx
0x180050750  mov     [rsp+378h+var_260], rcx
0x180050758  xor     r14d, r14d
0x18005075b  mov     [rsp+378h+var_328], r14d
0x180050760  xorps   xmm0, xmm0
0x180050763  movups  xmmword ptr [rsp+378h+UnicodeString.Length], xmm0
0x18005076b  xorps   xmm1, xmm1
0x18005076e  movups  [rsp+378h+var_2D8], xmm1
0x180050776  movups  [rsp+378h+var_258], xmm0
0x18005077e  mov     [r11-29Ch], r14d
0x180050785  mov     [r11-2B0h], r14
0x18005078c  movups  [rsp+378h+var_2C8], xmm0
0x180050794  movups  [rsp+378h+var_290], xmm1
0x18005079c  mov     [r11-240h], r14
0x1800507a3  mov     [r11-268h], r14
0x1800507aa  xor     eax, eax
0x1800507ac  movups  [rsp+378h+var_220], xmm0
0x1800507b4  movups  [rsp+378h+var_210], xmm0
0x1800507bc  movups  [rsp+378h+var_210+0Ch], xmm0
0x1800507c4  mov     qword ptr [r11-230h], 160014h
0x1800507cf  lea     rax, aKnowndlls; "\\KnownDlls"
0x1800507d6  mov     [r11-228h], rax
0x1800507dd  mov     [r11-2A8h], r14
0x1800507e4  mov     [r11-2E8h], r14
0x1800507eb  mov     [rsp+378h+var_310], r14
0x1800507f0  xor     edx, edx; Val
0x1800507f2  mov     r8d, 0D0h; Size
0x1800507f8  lea     rcx, [r11-188h]; void *
0x1800507ff  call    memset$thunk$772440563353939046
0x180050804  xorps   xmm0, xmm0
0x180050807  movups  [rsp+378h+var_2F8], xmm0
0x18005080f  xor     edx, edx; Val
0x180050811  mov     r8d, 80h; Size
0x180050817  lea     rcx, [rsp+378h+var_B8]; void *
0x18005081f  call    memset$thunk$772440563353939046
0x180050824  mov     [rsp+378h+SystemInformation], r14
0x18005082c  xor     ecx, ecx
0x18005082e  call    RtlEncodePointer
0x180050833  mov     cs:RtlpUnhandledExceptionFilter, rax
0x18005083a  mov     r13, gs:30h
0x180050843  mov     [rsp+378h+var_300], r13
0x180050848  mov     rdi, [r13+60h]
0x18005084c  mov     rcx, r13
0x18005084f  call    LdrpInitializeTeb
0x180050854  mov     cs:PebLdr, 58h ; 'X'
0x18005085e  lea     r15d, [r14+1]
0x180050862  mov     cs:byte_1801CA8C4, r15b
0x180050869  lea     rax, qword_1801CA8D0
0x180050870  mov     cs:qword_1801CA8D8, rax
0x180050877  mov     cs:qword_1801CA8D0, rax
0x18005087e  lea     rax, qword_1801CA8E0
0x180050885  mov     cs:qword_1801CA8E8, rax
0x18005088c  mov     cs:qword_1801CA8E0, rax
0x180050893  lea     rax, qword_1801CA8F0
0x18005089a  mov     cs:qword_1801CA8F8, rax
0x1800508a1  mov     cs:qword_1801CA8F0, rax
0x1800508a8  mov     cs:byte_1801CA908, r14b
0x1800508af  mov     cs:qword_1801CA910, r14
0x1800508b6  lea     rax, PebLdr
0x1800508bd  mov     [rdi+18h], rax
0x1800508c1  mov     rcx, rdi
0x1800508c4  call    LdrpInitializeNlsInfo
0x1800508c9  mov     cs:SRWLockSpinCycleCount, r14d
0x1800508d0  cmp     [rdi+0B8h], r15d
0x1800508d7  jbe     short loc_1800508E3
0x1800508d9  mov     cs:SRWLockSpinCycleCount, 2800h
0x1800508e3  mov     cs:ConditionVariableSpinCycleCount, r14d
0x1800508ea  jbe     short loc_1800508F6
0x1800508ec  mov     cs:ConditionVariableSpinCycleCount, 2800h
0x1800508f6  mov     cs:RtlpWaitOnAddressSpinCycleCount, r14d
0x1800508fd  jbe     short loc_180050909
0x1800508ff  mov     cs:RtlpWaitOnAddressSpinCycleCount, 2800h
0x180050909  mov     ecx, r15d
0x18005090c  call    RtlpInitFeatureConfiguration
0x180050911  call    Feature_Servicing_DisallowSharedLockImplicitUpgrade__private_IsEnabledNoReportingNoInline
0x180050916  mov     ecx, r14d
0x180050919  test    eax, eax
0x18005091b  setz    cl
0x18005091e  mov     cs:RtlpSrwLockAllowImplicitUpgrade, ecx
0x180050924  call    RtlpInitializeNonVolatileFlush
0x180050929  mov     rcx, [rdi+20h]
0x18005092d  mov     rax, [rcx+68h]
0x180050931  test    [rcx+8], r15b
0x180050935  lea     rdx, [rax+rcx]
0x180050939  cmovnz  rdx, rax
0x18005093d  mov     qword ptr [rsp+378h+var_290+8], rdx
0x180050945  movzx   ebx, word ptr [rcx+60h]
0x180050949  mov     word ptr [rsp+378h+var_290], bx
0x180050951  mov     eax, 2
0x180050956  add     eax, ebx
0x180050958  mov     word ptr [rsp+378h+var_290+2], ax
0x180050960  mov     r8d, 8
0x180050966  cmp     bx, r8w
0x18005096a  jnb     loc_180050D86
0x180050970  mov     cs:UseCOR, r14b
0x180050977  mov     dword ptr [rsp+378h+var_320], r14d
0x18005097c  lea     r9, [rsp+378h+var_2B0]
0x180050984  xor     r8d, r8d
0x180050987  mov     rdx, [rdi+10h]
0x18005098b  lea     ecx, [r8+3]
0x18005098f  call    RtlImageNtHeaderEx
0x180050994  mov     r12, [rsp+378h+var_2B0]
0x18005099c  mov     cs:LdrpAppHeaders, r12
0x1800509a3  cmp     cs:LdrpIsSecureProcess, r14b
0x1800509aa  jnz     loc_180050E30
0x1800509b0  mov     rdx, r14
0x1800509b3  mov     rcx, r14
0x1800509b6  lea     rbx, LdrpHashTable
0x1800509bd  lea     rax, [rcx+rbx]
0x1800509c1  mov     [rcx+rbx+8], rax
0x1800509c6  mov     [rax], rax
0x1800509c9  add     rdx, r15
0x1800509cc  lea     rcx, [rcx+10h]
0x1800509d0  cmp     rdx, 20h ; ' '
0x1800509d4  jnz     short loc_1800509BD
0x1800509d6  mov     rcx, rsi
0x1800509d9  call    LdrpInitializeExceptionTable
0x1800509de  call    LdrpCaptureCriticalThunks
0x1800509e3  mov     ecx, r15d
0x1800509e6  call    LdrProtectMrdata
0x1800509eb  call    LdrControlFlowGuardEnforcedWithExportSuppression
0x1800509f0  cmp     eax, r15d
0x1800509f3  jz      loc_180050F0A
0x1800509f9  mov     rax, cs:qword_1801E3508
0x180050a00  shr     al, 4
0x180050a03  and     al, 3
0x180050a05  cmp     al, r15b
0x180050a08  setz    cs:LdrpEnforceIntegrityContinuity
0x180050a0f  sub     al, r15b
0x180050a12  test    al, 0FDh
0x180050a14  setz    cs:LdrpAuditIntegrityContinuity
0x180050a1b  lea     rax, [rsp+378h+var_310]
0x180050a20  mov     qword ptr [rsp+378h+ArgList], rax
0x180050a25  lea     rax, [rsp+378h+var_2E8]
0x180050a2d  mov     [rsp+378h+Format], rax
0x180050a32  lea     r9, [rsp+378h+var_2A8]
0x180050a3a  mov     r8, rsi
0x180050a3d  mov     rdx, rdi
0x180050a40  lea     rcx, [rsp+378h+var_290]
0x180050a48  call    LdrpInitializeExecutionOptions
0x180050a4d  mov     [rsp+378h+var_328], eax
0x180050a51  test    eax, eax
0x180050a53  js      loc_180051D29
0x180050a59  mov     r15b, r14b
0x180050a5c  mov     [rsp+378h+var_318], r15d
0x180050a61  mov     ebx, r14d
0x180050a64  mov     ecx, 2
0x180050a69  cmp     cs:LdrpImageExpansionMitigation, ecx
0x180050a6f  jz      loc_180051D86
0x180050a75  test    [rdi+0BCh], cl
0x180050a7b  jnz     loc_180051D92
0x180050a81  mov     rax, [r13+40h]
0x180050a85  mov     qword ptr [rsp+378h+ArgList], rax; ArgList
0x180050a8a  lea     rax, aInitializingPr; "Initializing process 0x%p\n"
0x180050a91  mov     [rsp+378h+Format], rax; Format
0x180050a96  mov     r9d, ecx; int
0x180050a99  lea     rsi, aLdrpinitialize_3; "LdrpInitializeProcess"
0x180050aa0  mov     r8, rsi; int
0x180050aa3  mov     edx, 1767h; int
0x180050aa8  lea     r14, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x180050aaf  mov     rcx, r14; int
0x180050ab2  call    LdrpLogInternal
0x180050ab7  mov     ecx, [r13+180Ch]
0x180050abe  xor     r13d, r13d
0x180050ac1  mov     eax, r13d
0x180050ac4  test    ecx, ecx
0x180050ac6  setnle  al
0x180050ac9  mov     cs:UseWOW64, eax
0x180050acf  test    r12, r12
0x180050ad2  jnz     loc_180050DED
0x180050ad8  mov     [rsp+378h+var_238], r13
0x180050ae0  cmp     cs:UseWOW64, r13d
0x180050ae7  jz      loc_180050F1D
0x180050aed  mov     rax, [rsp+378h+var_2B8]
0x180050af5  mov     cs:LdrpSystemDllBase, rax
0x180050afc  cmp     cs:UseWOW64, r13d
0x180050b03  jz      loc_180051D9E
0x180050b09  mov     rax, [rdi+0C0h]
0x180050b10  mov     qword ptr cs:RtlpTimeout, rax
0x180050b17  mov     rcx, [rdi+20h]
0x180050b1b  call    RtlNormalizeProcessParams
0x180050b20  mov     r13, rax
0x180050b23  movups  xmm0, xmmword ptr [rax+60h]
0x180050b27  movdqu  [rsp+378h+var_2D8], xmm0
0x180050b30  xor     eax, eax
0x180050b32  cmp     cs:UseWOW64, eax
0x180050b38  jz      loc_180051DB2
0x180050b3e  xor     ebx, ebx
0x180050b40  mov     r15d, ebx
0x180050b43  test    r15, r15
0x180050b46  jnz     loc_180050EBF
0x180050b4c  test    byte ptr [rdi+0BCh], 2
0x180050b53  jnz     loc_180051DE6
0x180050b59  mov     rax, 0FFFFFFF79E3B9800h
0x180050b63  cmp     qword ptr cs:RtlpTimeout, rax
0x180050b6a  jl      loc_180051DF2
0x180050b70  call    RtlpInitDeferredCriticalSection
0x180050b75  mov     [rsp+378h+var_328], eax
0x180050b79  test    eax, eax
0x180050b7b  js      loc_180050E91
0x180050b81  mov     cs:dword_1801C6220, 40h ; '@'
0x180050b8b  lea     rax, [rdi+80h]
0x180050b92  mov     cs:qword_1801C6228, rax
0x180050b99  mov     cs:dword_1801C6210, 400h
0x180050ba3  lea     rax, [rdi+240h]
0x180050baa  mov     cs:qword_1801C6218, rax
0x180050bb1  lea     rax, dword_1801C6220
0x180050bb8  mov     [rdi+78h], rax
0x180050bbc  lea     rax, dword_1801C6210
0x180050bc3  mov     [rdi+238h], rax
0x180050bca  mov     rcx, cs:qword_1801C6228
0x180050bd1  mov     al, [rcx]
0x180050bd3  or      al, 1
0x180050bd5  mov     [rcx], al
0x180050bd7  xor     edx, edx; Val
0x180050bd9  lea     r8d, [rdx+60h]; Size
0x180050bdd  lea     rcx, RtlpFlsContext; void *
0x180050be4  call    memset$thunk$772440563353939046
0x180050be9  xorps   xmm0, xmm0
0x180050bec  movups  cs:xmmword_1801C5E38, xmm0
0x180050bf3  movups  cs:xmmword_1801C5E48, xmm0
0x180050bfa  movups  cs:xmmword_1801C5E58, xmm0
0x180050c01  movups  cs:xmmword_1801C5E68, xmm0
0x180050c08  lea     rax, qword_1801C5E78
0x180050c0f  mov     cs:qword_1801C5E80, rax
0x180050c16  mov     cs:qword_1801C5E78, rax
0x180050c1d  cmp     cs:UseWOW64, ebx
0x180050c23  jnz     loc_180051DFE
0x180050c29  mov     rcx, cs:qword_1801C6228
0x180050c30  mov     al, [rcx+2]
0x180050c33  mov     edx, 1
0x180050c38  or      al, dl
0x180050c3a  mov     [rcx+2], al
0x180050c3d  test    dword ptr [rdi+0BCh], 1000h
0x180050c47  jnz     loc_180051E27
0x180050c4d  mov     al, cs:LdrpShouldCreateStackTraceDb
0x180050c53  test    al, al
0x180050c55  jnz     loc_180051E27
0x180050c5b  test    dword ptr [rdi+0BCh], 1000h
0x180050c65  jnz     loc_180051EFC
0x180050c6b  test    al, al
0x180050c6d  jnz     loc_180051EFC
0x180050c73  mov     rax, gs:60h
0x180050c7c  mov     ecx, [rax+2C8h]
0x180050c82  bt      rcx, 16h
0x180050c87  jb      loc_180051F07
0x180050c8d  xor     r8d, r8d
0x180050c90  xor     edx, edx
0x180050c92  lea     rcx, FastPebLock
0x180050c99  call    RtlInitializeCriticalSectionEx
0x180050c9e  mov     [rsp+378h+var_328], eax
0x180050ca2  test    eax, eax
0x180050ca4  js      loc_180050E91
0x180050caa  lea     rax, FastPebLock
0x180050cb1  mov     [rdi+38h], rax
0x180050cb5  lea     rcx, [rsp+378h+var_290]
0x180050cbd  call    RtlInitializeHeapManager
0x180050cc2  mov     [rsp+378h+var_328], eax
0x180050cc6  test    eax, eax
0x180050cc8  js      loc_180050E91
0x180050cce  mov     rax, cs:qword_1801E3500
0x180050cd5  shr     rax, 0Ch
0x180050cd9  and     al, 3
0x180050cdb  mov     ecx, 1
0x180050ce0  cmp     al, cl
0x180050ce2  jz      loc_180051F18
0x180050ce8  lea     r9, [rdi+30h]
0x180050cec  mov     r8, r13
0x180050cef  mov     rdx, r12
0x180050cf2  mov     rcx, r15
0x180050cf5  call    LdrpInitializeProcessHeap
0x180050cfa  mov     [rsp+378h+var_328], eax
0x180050cfe  xor     r15d, r15d
0x180050d01  test    eax, eax
0x180050d03  js      loc_180051F2C
0x180050d09  mov     r12, [rdi+30h]
0x180050d0d  mov     cs:dword_1801CBE98, 2
0x180050d17  call    Feature_Servicing_LoaderSnapsBuffer__private_IsEnabledDeviceUsageNoInline
0x180050d1c  test    eax, eax
0x180050d1e  jz      short loc_180050D25
0x180050d20  call    LdrpInitializeSnapsBuffer
0x180050d25  xor     r8d, r8d
0x180050d28  xor     edx, edx
0x180050d2a  lea     rcx, LdrpEnclaveListLock
0x180050d31  call    RtlInitializeCriticalSectionEx
0x180050d36  lea     rax, LdrpEnclaveList
0x180050d3d  mov     cs:qword_1801CC368, rax
  ... truncated ...
```
