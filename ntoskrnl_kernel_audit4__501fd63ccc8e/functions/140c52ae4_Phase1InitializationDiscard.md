# Phase1InitializationDiscard

- ea: `0x140c52ae4`
- end: `0x140c53f32`
- name: `Phase1InitializationDiscard`
- size: `5198`
- prototype: ``
- caller_count: `1`
- callee_count: `98`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140746700`

## callees

- `0x140367c90`
- `0x1403729e0`
- `0x14038d300`
- `0x1403ac6e0`
- `0x1403cd384`
- `0x1403f1040`
- `0x140403380`
- `0x14040edb0`
- `0x140423570`
- `0x140424988`
- `0x140439450`
- `0x14044a554`
- `0x1404aa520`
- `0x140541078`
- `0x140541bd0`
- `0x140541bf0`
- `0x140543410`
- `0x1405438ec`
- `0x140543b80`
- `0x140543bb0`
- `0x140543e10`
- `0x140583804`
- `0x140583a54`
- `0x140583ab0`
- `0x140583c2c`
- `0x1405c32f0`
- `0x1405cfcf0`
- `0x1405f3938`
- `0x1406a29e0`
- `0x1406cc074`
- `0x1406dc8c0`
- `0x1406dffe0`
- `0x1406e0ba0`
- `0x1406e1000`
- `0x1406f7380`
- `0x1406f7aa0`
- `0x14075ab70`
- `0x140783a44`
- `0x1407b8cc8`
- `0x1407dab3c`
- `0x1407e4508`
- `0x1407e46e4`
- `0x1407e63f0`
- `0x1407e692c`
- `0x1407e6e74`
- `0x1407f3a34`
- `0x14080ab18`
- `0x14080ab48`
- `0x14082f958`
- `0x14086a810`

## import_xrefs

- `symcryptk!SymCryptEntropyAccumulatorGlobalInitFromRegistry` at `0x140c53de5`
- `symcryptk!SymCryptEntropyAccumulatorGlobalInitFromRegistry` at `0x140c53de5`
- `ext-ms-win-ntos-tm-l1-1-0!TmInitSystem` at `0x140c5364a`
- `ext-ms-win-ntos-tm-l1-1-0!TmInitSystem` at `0x140c5364a`
- `kdcom!KdInitialize` at `0x140c53bc2`
- `kdcom!KdInitialize` at `0x140c53bc2`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrInitSystem` at `0x140c538e6`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrInitSystem` at `0x140c538e6`
- `ext-ms-win-ntos-ucode-l1-1-0!ExpMicrocodeInitialization` at `0x140c53d80`
- `ext-ms-win-ntos-ucode-l1-1-0!ExpMicrocodeInitialization` at `0x140c53d80`

## string_xrefs

- `0x140c53c54`: `DSREPAIR`

## pseudocode

```c
bool __fastcall Phase1InitializationDiscard(ULONG_PTR BugCheckParameter3)
{
  char *Pool2; // r12
  char *v3; // rcx
  char *v4; // rax
  const char *v5; // r14
  char *v6; // rax
  char *v7; // rax
  char *v8; // rax
  char *v9; // rdi
  __int64 v10; // rbx
  char *v11; // rax
  char *v12; // rsi
  unsigned int v13; // eax
  char *v14; // rcx
  __int64 v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  ULONG_PTR v22; // rcx
  __int64 v23; // rcx
  int Message; // eax
  char *v25; // rbx
  int v26; // esi
  NTSTATUS v27; // eax
  size_t v28; // rdi
  char *v29; // rbx
  NTSTATUS v30; // eax
  NTSTATUS v31; // eax
  NTSTATUS v32; // eax
  _OWORD *v33; // rax
  char *v34; // rcx
  __int64 v35; // rdx
  __int128 v36; // xmm1
  char v37; // si
  __int64 v38; // rcx
  int v39; // eax
  char *v40; // rax
  char *v41; // rax
  __int16 v42; // bx
  LARGE_INTEGER v43; // rax
  __int64 CurrentServerSiloGlobals; // rax
  char *v45; // rax
  char *v46; // rax
  char *v47; // rax
  char *v48; // rax
  char *v49; // rax
  char *v50; // rax
  char *v51; // rax
  char *v52; // rax
  char *v53; // rax
  char *v54; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  int v56; // eax
  const char *v57; // rbx
  int v58; // r9d
  int v59; // edi
  __int64 v60; // rbx
  _DWORD *v61; // rax
  __int64 i; // rdx
  __int64 v63; // rcx
  const char *v64; // r8
  NTSTATUS v65; // eax
  bool v66; // r12
  int inited; // eax
  int v68; // eax
  int v69; // eax
  int SystemRootLink; // eax
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 *v75; // r9
  __int64 DisplayContext; // rax
  ULONG_PTR v77; // rbx
  int v78; // eax
  int v79; // eax
  int v80; // eax
  int v81; // eax
  __int64 v82; // rdi
  int v83; // ebx
  int v84; // esi
  char *v90; // rax
  const char *v91; // rdi
  int v92; // ebx
  int v93; // r9d
  int v94; // ebx
  int v95; // ebx
  __int64 v96; // rbx
  int v97; // eax
  ULONG dwFlags[2]; // [rsp+20h] [rbp-E0h]
  int pszFormat; // [rsp+28h] [rbp-D8h]
  char v101[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v102; // [rsp+48h] [rbp-B8h] BYREF
  LONGLONG v103; // [rsp+50h] [rbp-B0h] BYREF
  char *EndPtr; // [rsp+58h] [rbp-A8h] BYREF
  int v105; // [rsp+60h] [rbp-A0h] BYREF
  int v106; // [rsp+64h] [rbp-9Ch] BYREF
  int v107; // [rsp+68h] [rbp-98h] BYREF
  LARGE_INTEGER v108; // [rsp+70h] [rbp-90h] BYREF
  __int64 v109; // [rsp+78h] [rbp-88h] BYREF
  size_t pcbRemaining; // [rsp+80h] [rbp-80h] BYREF
  __int64 v111; // [rsp+88h] [rbp-78h] BYREF
  __int64 v112; // [rsp+90h] [rbp-70h] BYREF
  __int128 v113; // [rsp+98h] [rbp-68h] BYREF
  STRING v114; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD v116[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 (__fastcall *v117)(); // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v118)(); // [rsp+E0h] [rbp-20h]
  __int64 (__fastcall *v119)(); // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v120)(int, int, int, int, __int64, __int64); // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall *v121)(); // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall *v122)(); // [rsp+100h] [rbp+0h]
  __int64 (__fastcall *v123)(); // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v124)(ULONG_PTR); // [rsp+110h] [rbp+10h]
  __int64 (__fastcall *v125)(); // [rsp+118h] [rbp+18h]
  __int64 (__fastcall *v126)(); // [rsp+120h] [rbp+20h]
  __int128 v127; // [rsp+130h] [rbp+30h]
  __int128 v128; // [rsp+140h] [rbp+40h]
  __int128 v129; // [rsp+150h] [rbp+50h]
  __int64 v130; // [rsp+160h] [rbp+60h]
  char pszDest[24]; // [rsp+170h] [rbp+70h] BYREF

  v103 = 0;
  v108.QuadPart = 0;
  v111 = 0;
  v102 = 0;
  v112 = 0;
  v114 = 0;
  v107 = 0;
  v113 = 0;
  v105 = 0;
  v106 = 0;
  DestinationString = 0;
  v116[1] = 0;
  memset_0(v116, 0, 0x94u);
  v109 = *(_QWORD *)(PsGetCurrentServerSiloGlobals() + 1232);
  Pool2 = (char *)ExAllocatePool2(64, 512, 1953066569);
  if ( !Pool2 )
    KeBugCheck(0x31u);
  LODWORD(InitializationPhase) = 1;
  KeSetPriorityThread(KeGetCurrentThread(), 31);
  v3 = *(char **)(BugCheckParameter3 + 216);
  if ( v3 )
  {
    v4 = strupr(v3);
    v5 = v4;
    if ( v4 )
    {
      v6 = strstr(v4, " HYPERVISORROOTPROC=");
      if ( v6 )
      {
        v7 = strstr(v6, "=");
        if ( v7 )
          KeRootProcSpecified = atol(v7 + 1);
      }
      v8 = strstr(v5, " HYPERVISORROOTPROCNUMANODES=");
      v9 = v8;
      if ( v8 )
        v9 = strstr(v8, "=");
      while ( v9 && (unsigned int)KeRootProcNumaNodesSpecified < 0x40 )
      {
        ++v9;
        v10 = (unsigned int)KeRootProcNumaNodesSpecified;
        *((_WORD *)&KeRootProcNumaNodes + v10) = atol(v9);
        ++KeRootProcNumaNodesSpecified;
        while ( *v9 != 44 )
        {
          if ( (*v9 & 0xDF) == 0 )
            goto LABEL_17;
          ++v9;
        }
      }
LABEL_17:
      v11 = strstr(v5, " HYPERVISORROOTPROCNUMANODELPS=");
      v12 = v11;
      if ( v11 )
      {
        v12 = strstr(v11, "=");
        KeRootProcNumaNodeLpsSpecified = 1;
        KeRootProcNumaNodesSpecified = 0;
        KeRootProcSpecified = 0;
      }
      while ( v12 )
      {
        ++v12;
        EndPtr = 0;
        v13 = strtoul(v12, &EndPtr, 10);
        v14 = EndPtr;
        v15 = v13;
        if ( v12 == EndPtr || *EndPtr != 95 )
        {
          v17 = 0;
        }
        else
        {
          v12 = EndPtr + 1;
          v16 = strtoul(EndPtr + 1, &EndPtr, 10);
          v14 = EndPtr;
          v17 = v16;
        }
        if ( v12 != v14 && *v14 == 61 && (unsigned int)v15 < 0x40 )
        {
          v18 = 2 * v15;
          v12 = v14 + 1;
          if ( !qword_140FC06F8[v18] )
          {
            v19 = ExAllocatePool2(64, 256, 2048);
            if ( !v19 )
              KeBugCheck(0x31u);
            KeRootProcNumaNodeLps[v18] = 2048;
            qword_140FC06F8[v18] = v19;
          }
          if ( (unsigned int)v17 < 0x20 )
          {
            v20 = qword_140FC06F8[v18];
            *(_QWORD *)(v20 + 8 * v17) = strtoui64(v12, &EndPtr, 16);
          }
        }
        while ( *v12 != 44 )
        {
          if ( (*v12 & 0xDF) == 0 )
            goto LABEL_39;
          ++v12;
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
LABEL_39:
  v21 = KiSubNodeConfigBlock;
  word_140E4CAC8 = 0;
  *(_BYTE *)(KiSubNodeConfigBlock + 5) &= 0xFCu;
  *(_BYTE *)(v21 + 4) = 0;
  KiPerformGroupConfiguration(BugCheckParameter3);
  KiCommitGroupSubNodeAssignments(*(unsigned __int16 *)(KiSubNodeConfigBlock + 6));
  v22 = (unsigned int)InitializationPhase;
  *(_QWORD *)(KiSubNodeConfigBlock + 16) |= 1uLL;
  if ( !(unsigned __int8)HalInitSystem(v22) )
    goto LABEL_226;
  KeInitializeClock((unsigned int)InitializationPhase);
  if ( v5 && strstr(v5, "NOGUIBOOT") )
    goto LABEL_229;
  byte_140E4BFB0 = 0;
  if ( byte_140E4C010 )
  {
    if ( byte_140E4C018 )
    {
      LOBYTE(v23) = 1;
      if ( (int)BgDisplayProgressIndicator(v23) >= 0 )
        byte_140E4C011 = 1;
    }
    if ( byte_140E4C010 )
    {
      if ( byte_140E4C018 )
      {
        LOBYTE(v23) = 1;
        if ( (int)BgDisplayBackgroundUpdate(v23) >= 0 )
          byte_140E4BFE1 = 1;
      }
    }
  }
  qword_140E4BFB8 = (__int64)DisplayFilter;
  InbvDriverInitialize(1, BugCheckParameter3, 7);
  DisplayBootBitmap(0);
  if ( v5 )
  {
LABEL_229:
    if ( strstr(v5, "MININT") )
    {
      InitIsWinPEMode = 1;
      if ( strstr(v5, "INRAM") )
        InitWinPEModeType |= 0x80000000;
      else
        InitWinPEModeType |= 1u;
    }
  }
  Message = RtlFindMessage(0x40000000u, 11, 0, 1073741950, (__int64)&v102);
  v25 = Pool2;
  EndPtr = Pool2;
  v26 = Message;
  pcbRemaining = 256;
  if ( CmCSDVersionString.Length )
  {
    v27 = RtlStringCbPrintfExA(Pool2, 0xFFu, &EndPtr, &pcbRemaining, 0, ": %wZ");
    if ( v27 < 0 )
      KeBugCheckEx(0x32u, v27, 7u, 0, 0);
    v25 = EndPtr;
    v28 = pcbRemaining;
  }
  else
  {
    v28 = 255;
  }
  *v25 = 0;
  v29 = v25 + 1;
  v30 = RtlStringCbPrintfA(pszDest, 0x18u, "%u.%u", 10, 0);
  if ( v30 < 0 )
    KeBugCheckEx(0x32u, v30, 7u, 1u, 0);
  if ( v26 < 0 )
  {
    v32 = RtlStringCbCopyA(v29, v28, "MICROSOFT (R) WINDOWS (TM)\n");
    if ( v32 < 0 )
      KeBugCheckEx(0x32u, v32, 7u, 3u, 0);
  }
  else
  {
    pszFormat = (int)Pool2;
    dwFlags[0] = (unsigned __int16)NtBuildNumber;
    v31 = RtlStringCbPrintfA(v29, v28, (NTSTRSAFE_PCSTR)(v102 + 4), pszDest, *(_QWORD *)dwFlags);
    if ( v31 < 0 )
      KeBugCheckEx(0x32u, v31, 7u, 2u, 0);
  }
  pcbRemaining = (size_t)(Pool2 + 256);
  InbvDisplayString(v29);
  v33 = Pool2 + 256;
  v34 = Pool2;
  v35 = 2;
  do
  {
    *v33 = *(_OWORD *)v34;
    v33[1] = *((_OWORD *)v34 + 1);
    v33[2] = *((_OWORD *)v34 + 2);
    v33[3] = *((_OWORD *)v34 + 3);
    v33[4] = *((_OWORD *)v34 + 4);
    v33[5] = *((_OWORD *)v34 + 5);
    v33[6] = *((_OWORD *)v34 + 6);
    v36 = *((_OWORD *)v34 + 7);
    v34 += 128;
    v33[7] = v36;
    v33 += 8;
    --v35;
  }
  while ( v35 );
  if ( !(unsigned __int8)PoInitSystem(0, BugCheckParameter3) )
LABEL_225:
    KeBugCheck(0xA0u);
  v37 = 0;
  if ( !ExpRealTimeIsUniversal )
  {
    v38 = v109;
    v39 = *(_DWORD *)(v109 + 436);
    if ( v39 == -1 )
    {
      v37 = 1;
      *(_DWORD *)(v109 + 436) = ExpAltTimeZoneBias;
      v39 = ExpAltTimeZoneBias;
    }
    *(_QWORD *)(v38 + 440) = 600000000LL * v39;
    *(_DWORD *)(MmWriteableSharedUserData + 604) = 0;
    ExpWriteTimeZoneBias();
  }
  GetBootSystemTime(*(_QWORD *)(BugCheckParameter3 + 240), &v103);
  if ( v5 )
  {
    v40 = strstr(v5, "YEAR");
    if ( v40 )
    {
      v41 = strstr(v40, "=");
      if ( v41 )
      {
        v42 = atol(v41 + 1);
        RtlpTimeToTimeFields(&v103, &v113);
        LOWORD(v113) = v42;
        RtlpTimeFieldsToTime(&v113, &v103);
      }
    }
  }
  if ( ExpRealTimeIsUniversal )
    v43.QuadPart = v103;
  else
    v43.QuadPart = v103 - *(_QWORD *)(*(_QWORD *)(PsGetCurrentServerSiloGlobals() + 1232) + 440LL);
  v108 = v43;
  KeSetSystemTime(&v103, &v111, 4);
  CurrentServerSiloGlobals = PsGetCurrentServerSiloGlobals();
  PoNotifySystemTimeSet(
    (unsigned int)&v103,
    (unsigned int)&v111,
    0,
    (unsigned int)&v108,
    *(_DWORD *)(*(_QWORD *)(CurrentServerSiloGlobals + 1232) + 436LL),
    pszFormat,
    ExpSystemIsInCmosMode);
  RtlInitUnicodeString(&DestinationString, L"Kernel-RegisteredProcessors");
  if ( (int)ZwQueryLicenseValue(&DestinationString, &v106, &KeRegisteredProcessors, 4, &v105) < 0
    || v105 != 4
    || v106 != 4 )
  {
    KeRegisteredProcessors = 1;
  }
  if ( v5 )
  {
    v45 = strstr(v5, " BOOTPROC=");
    if ( v45 )
    {
      v46 = strstr(v45, "=");
      if ( v46 )
        KeBootprocSpecified = atol(v46 + 1);
    }
    v47 = strstr(v5, " NUMPROC=");
    if ( v47 )
    {
      v48 = strstr(v47, "=");
      if ( v48 )
        *(_DWORD *)((char *)&Mm64BitPhysicalAddress + 3) = atol(v48 + 1);
    }
    v49 = strstr(v5, " HYPERVISORNUMPROC=");
    if ( v49 )
    {
      v50 = strstr(v49, "=");
      if ( v50 )
        KeHypervisorNumprocSpecified = atol(v50 + 1);
    }
    if ( !KeRootProcNumaNodeLpsSpecified )
    {
      v51 = strstr(v5, " HYPERVISORROOTPROCPERNODE=");
      if ( v51 )
      {
        v52 = strstr(v51, "=");
        if ( v52 )
          KeRootProcPerNodeSpecified = atol(v52 + 1);
      }
      v53 = strstr(v5, " HYPERVISORROOTPROCPERCORE=");
      if ( v53 )
      {
        v54 = strstr(v53, "=");
        if ( v54 )
          *(_DWORD *)((char *)&Mm64BitPhysicalAddress + 7) = atol(v54 + 1);
      }
    }
    if ( strstr(v5, " MAXPROC") )
      KeMaxprocSpecified = 1;
  }
  qword_141005908 = KeQueryPerformanceCounter(0).QuadPart;
  KeStartAllProcessors();
  qword_141005910 = KeQueryPerformanceCounter(0).QuadPart;
  EtwTimeProfileReset();
  KeSetAffinityProcess(KeGetCurrentThread()->ApcState.Process);
  MakeGdtReadOnly();
  if ( (Feature_LookasideDepthManager__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_LookasideDepthManager__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_LookasideDepthManager__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    v56 = ExLookasideMgrsAllocate();
    if ( v56 < 0 )
      KeBugCheckEx(0x32u, v56, 0xFu, 1u, 0);
  }
  v57 = (int)RtlFindMessage(0x40000000u, 11, 0, 1073741961, (__int64)&v112) < 0
      ? "MultiProcessor Kernel\r\n"
      : (const char *)(v112 + 4);
  if ( !(unsigned __int8)HalAllProcessorsStarted() )
LABEL_226:
    KeBugCheck(0x61u);
  RtlInitAnsiString(&v114, v57);
  if ( v114.Length >= 2u )
    v114.Length -= 2;
  v58 = 1073741981;
  if ( (unsigned int)KeNumberProcessors_0 <= 1 )
    v58 = 1073741960;
  v59 = RtlFindMessage(0x40000000u, 11, 0, v58, (__int64)&v102);
  v60 = 0;
  v61 = (_DWORD *)MmReferencePhysicalMemoryBlock();
  for ( i = 0; (unsigned int)i < *v61; v60 += *(_QWORD *)&v61[4 * v63 + 6] )
  {
    v63 = (unsigned int)i;
    i = (unsigned int)(i + 1);
  }
  MmDereferencePhysicalMemoryBlock(v61, i);
  if ( v59 < 0 )
    v64 = "%u System Processor [%u MB Memory] %Z\n";
  else
    v64 = (const char *)(v102 + 4);
  v65 = RtlStringCbPrintfA(
          Pool2,
          0x100u,
          v64,
          (unsigned int)KeNumberProcessors_0,
          (unsigned __int64)(v60 + 255) >> 8,
          &v114);
  if ( v65 < 0 )
    KeBugCheckEx(0x32u, v65, 7u, 4u, 0);
  InbvDisplayString(Pool2);
  ExFreePoolWithTag(Pool2, 0);
  v66 = 0;
  if ( !(unsigned __int8)ObInitSystem(1) )
    KeBugCheck(0x62u);
  if ( !(unsigned __int8)ExInitSystem(BugCheckParameter3) )
    KeBugCheckEx(0x32u, 0xFFFFFFFFC0000001uLL, 0, 1u, 0);
  HalReportResourceUsage(0xFFFFFFFFLL);
  if ( !(unsigned __int8)IoCreateObjectTypes() )
    KeBugCheckEx(0x32u, 0xFFFFFFFFC0000001uLL, 0, 4u, 0);
  if ( !(unsigned __int8)KeInitSystem(1) )
    KeBugCheckEx(0x32u, 0xFFFFFFFFC0000001uLL, 0, 2u, 0);
  if ( !(unsigned __int8)KdInitSystem((unsigned int)InitializationPhase, 0) )
    KeBugCheckEx(0x32u, 0xFFFFFFFFC0000001uLL, 0, 3u, 0);
  inited = TmInitSystem(
             &TmResourceManagerObjectType,
             &TmEnlistmentObjectType,
             &TmTransactionManagerObjectType,
             &TmTransactionObjectType);
  if ( (int)(inited + 0x80000000) >= 0 && inited != -1073741637 )
    KeBugCheckEx(0x32u, 0, 0, 0, 0);
  v68 = DbgkInitialize();
  if ( v68 < 0 )
    KeBugCheckEx(0x32u, v68, 0, 0, 0);
  UcInitialize(0);
  BcdInitializeBcdSyncMutant();
  VerifierInitSystem(0);
  if ( !(unsigned __int8)SeInitSystem() )
    KeBugCheck(0x63u);
  LpcLegacyMaxMessageLength = 648;
  if ( (int)AlpcpInitSystem() < 0 )
    KeBugCheck(0x6Au);
  LpcPortObjectType = AlpcPortObjectType;
  v69 = SmInitSystem(0);
  if ( v69 < 0 )
    KeBugCheckEx(0x32u, v69, 0xDu, 0, 0);
  PsInitSystem(1, BugCheckParameter3);
  ExInitLicenseCallback();
  SystemRootLink = CreateSystemRootLink(BugCheckParameter3);
  if ( SystemRootLink < 0 )
    KeBugCheckEx(0x64u, SystemRootLink, 0, 0, 0);
  qword_141005928 = KeQueryPerformanceCounter(0).QuadPart;
  MmInitSystem(1, BugCheckParameter3);
  qword_141005930 = KeQueryPerformanceCounter(0).QuadPart;
  if ( !(unsigned __int8)CcInitializeCacheManager(1) )
    KeBugCheck(0x66u);
  if ( !(unsigned __int8)CmInitSystem1(BugCheckParameter3) )
    KeBugCheck(0x67u);
  PsInitializeBootCpuPartitions();
  v71 = ExInitializeLeapSecondData();
  if ( v71 < 0 )
    KeBugCheckEx(0x32u, v71, 0xCu, 0, 0);
  v101[0] = 0;
  if ( (int)ExIsMultiSessionSku(v101) >= 0 && v101[0] )
    *(_DWORD *)(MmWriteableSharedUserData + 752) |= 0x100u;
  if ( RtlpMultiUsersInSessionSupported )
    *(_DWORD *)(MmWriteableSharedUserData + 752) |= 0x200u;
  if ( CmStateSeparationEnabled )
    *(_DWORD *)(MmWriteableSharedUserData + 752) |= 0x400u;
  qword_1410058F8 = KeQueryPerformanceCounter(0).QuadPart;
  memset_0(v116, 0, 0x98u);
  v117 = MmMapLockedRestartPages;
  v118 = MmUnmapLockedRestartPages;
  v119 = KeRemoveEnclavePage;
  v120 = KdPullRemoteFileEx;
  v121 = CmSaveKeyToBuffer;
  v122 = KeIsBugCheckActive;
  v123 = CmOpenKeyForBugCheckRecovery;
  v124 = MiPageToNode;
  v125 = MmGetNextNode;
  v126 = MmGetFileObjectForSection;
  v116[0] = 152;
  if ( VslVsmEnabled )
  {
    VslpIumKsrInitContext = (__int64)VslpKsrEnterIumSecureMode;
    v75 = &VslpIumKsrInitContext;
    qword_1410058A0 = (__int64)VslpRegisterKsrCallback;
  }
  else
  {
    v75 = 0;
  }
  DisplayContext = BgGetDisplayContext(v73, v72, v74, v75);
  v77 = (int)KsrInitSystem(BugCheckParameter3, v116, DisplayContext);
  qword_141005900 = KeQueryPerformanceCounter(0).QuadPart;
  if ( (int)(v77 + 0x80000000) >= 0 && (_DWORD)v77 != -1073741637 )
    KeBugCheckEx(0x32u, v77, 0, 1u, 0);
  ExKsrInterface = v127;
  xmmword_140EECF30 = v128;
  xmmword_140EECF40 = v129;
  qword_140EECF50 = v130;
  v78 = EmInitSystem(0, BugCheckParameter3);
  if ( v78 < 0 )
    KeBugCheckEx(0x32u, v78, 8u, 0, 0);
  v79 = MfgInitSystem(BugCheckParameter3);
  if ( v79 < 0 )
    KeBugCheckEx(0x32u, v79, 9u, 0, 0);
  PfInitializeSuperfetch();
  v80 = SmInitSystem(1);
  if ( v80 < 0 )
    KeBugCheckEx(0x32u, v80, 0xEu, 0, 0);
  v81 = VmInitSystem(1);
  if ( v81 < 0 )
    KeBugCheckEx(0x32u, v81, 0xAu, 0, 0);
  if ( (*(_BYTE *)(*(_QWORD *)(BugCheckParameter3 + 240) + 2656LL) & 2) == 0 || strstr(v5, "FORCETIMESYNC") )
    ZwUpdateWnfStateData(&WNF_BOOT_INVALID_TIME_SOURCE, 0, 0, 0, 0, 0, 0);
  if ( (HvlpFlags & 0x2000000) != 0 )
    ZwUpdateWnfStateData(&WNF_HVL_CPU_MGMT_PARTITION, 0, 0, 0, 0, 0, 0);
  v107 = 0;
  FsRtlSendModernAppTermination(&v107, 1, 1);
  ExInitializeTimeRefresh();
  ExAcquireTimeRefreshLockExclusive();
  ExInitializeUtcTimeZoneBias(&v108);
  v82 = v109;
  v83 = *(_DWORD *)(v109 + 436);
  ExpRefreshTimeZoneInformation(0);
  ExReleaseTimeRefreshLockExclusive();
  if ( v37 )
  {
    v103 = *(_QWORD *)(*(_QWORD *)(PsGetCurrentServerSiloGlobals() + 1232) + 440LL) + v108.QuadPart;
    KeSetSystemTime(&v103, &v111, 4);
  }
  else if ( v83 != *(_DWORD *)(v82 + 436) )
  {
    ZwSetSystemTime(0, 0);
  }
  if ( !(unsigned __int8)FsRtlInitSystem() )
    KeBugCheck(0x68u);
  ExInitializeNPagedLookasideListInternal(
    (unsigned int)&RtlLznt1DecompressChunkLookaside,
    0,
    0,
    512,
    88,
    1667529324,
    0,
    0);
  v84 = 1;
  _RAX = 1;
  __asm { cpuid }
  x86_cpu_enable_ssse3 = _RCX & 0x200;
  x86_cpu_enable_simd = (_RDX & 0x4000000) != 0 && (_RCX & 0x100002) == 1048578;
  ExInitializePagedLookasideList(&RtlpRangeListEntryLookasideList, 0, 0, 0, 0x38u, 0x656C5252u, 0x10u);
  HvlDebuggerSupportInitialize(BugCheckParameter3);
  HalReportResourceUsage(0);
  KdInitialize(1, BugCheckParameter3, &KdpContext);
  if ( !(unsigned __int8)PpInitSystem() )
    KeBugCheck(0x90u);
  if ( v5 )
  {
    v90 = strstr(v5, "SAFEBOOT:");
    if ( v90 )
    {
      v91 = v90 + 9;
      if ( !strncmp(v90 + 9, "MINIMAL", 7u) )
      {
        v92 = 1;
        v91 += 7;
      }
      else if ( !strncmp(v91, "NETWORK", 7u) )
      {
        v92 = 2;
        v91 += 7;
        v84 = 2;
      }
      else if ( !strncmp(v91, "DSREPAIR", 8u) )
      {
        v92 = 3;
        v91 += 8;
        v84 = 3;
      }
      else
      {
        v92 = 0;
        v84 = 0;
      }
      LODWORD(InitSafeBootMode) = v92;
      if ( *v91 )
        v66 = strncmp(v91, "(ALTERNATESHELL)", 0x10u) == 0;
      if ( v84 )
      {
        v109 = 0;
        v93 = 0;
        v94 = v92 - 1;
        if ( v94 )
        {
          v95 = v94 - 1;
          if ( v95 )
          {
            if ( v95 == 1 )
              v93 = 170;
          }
          else
          {
            v93 = 169;
          }
        }
        else
        {
          v93 = 168;
        }
        if ( (int)RtlFindMessage(0x40000000u, 11, 0, v93, (__int64)&v109) >= 0 )
          InbvDisplayString(v109 + 4);
      }
    }
  }
  if ( (*(_DWORD *)(*(_QWORD *)(BugCheckParameter3 + 240) + 132LL) & 0x800) != 0 )
  {
    if ( (int)RtlFindMessage(0x40000000u, 11, 0, 183, (__int64)&v102) >= 0 )
      InbvDisplayString(v102 + 4);
    IopInitializeBootLogging(BugCheckParameter3, pcbRemaining);
  }
  ExpWatchProductTypeInitialization();
  *(_DWORD *)(MmWriteableSharedUserData + 736) = -1;
  BootApplicationPersistentDataProcess(0);
  ExpMicrocodeInitialization(2);
  if ( ExpFreeListCount > (unsigned int)KeMaximumProcessors )
    ExpFreeListCount = KeMaximumProcessors;
  LODWORD(v102) = 0;
  ExpOriginalImageVersion = 0;
  if ( (int)ExpGetOriginalImageVersionRegistryValue(&v102) >= 0 )
    ExpOriginalImageVersion = v102;
  v96 = MmWriteableSharedUserData;
  *(_WORD *)(v96 + 726) = ExpComputeCyclesPerYield();
  if ( InitIsWinPEMode )
    CreateMiniNtBootKey();
  SymCryptEntropyAccumulatorGlobalInitFromRegistry();
  v97 = SeCodeIntegrityInitializePolicy(BugCheckParameter3);
  if ( v97 < 0 )
    KeBugCheckEx(0x32u, v97, 0x69436553u, 0, 0);
  KdpTimeSlipPending = 0;
  qword_140EE4B98 = (__int64)&ExBootDeviceList;
  ExBootDeviceList = (__int64)&ExBootDeviceList;
  ExNumMissingBootDevices = 0;
  ExBootDevicesRemovedEvent.Header.WaitListHead.Blink = &ExBootDevicesRemovedEvent.Header.WaitListHead;
  ExBootDevicesRemovedEvent.Header.WaitListHead.Flink = &ExBootDevicesRemovedEvent.Header.WaitListHead;
  ExExternalBootSupportInitializationEvent.Header.WaitListHead.Blink = &ExExternalBootSupportInitializationEvent.Header.WaitListHead;
  ExExternalBootSupportInitializationEvent.Header.WaitListHead.Flink = &ExExternalBootSupportInitializationEvent.Header.WaitListHead;
  ExBootDeviceRemovalHandler = 0;
  ExBootDeviceListSpinLock = 0;
  LOWORD(ExBootDevicesRemovedEvent.Header.Lock) = 1;
  ExBootDevicesRemovedEvent.Header.Size = 6;
  ExBootDevicesRemovedEvent.Header.SignalState = 0;
  LOWORD(ExExternalBootSupportInitializationEvent.Header.Lock) = 1;
  ExExternalBootSupportInitializationEvent.Header.Size = 6;
  ExExternalBootSupportInitializationEvent.Header.SignalState = 1;
  if ( !(unsigned __int8)PoInitSystem(1, BugCheckParameter3) )
    goto LABEL_225;
  RtlInitFunctionalityCache();
  if ( _InterlockedCompareExchange8(&ExKdpPool, 1, 0) )
    KeBugCheckEx(0xC2u, 0xA2u, 0, 0, 0);
  MiProtectKernelRoDataSectionsSlat(0);
  MmCompletePhase1Initialization();
  return v66;
}

```

## disassembly

```asm
0x140c52ae4  push    rbp
0x140c52ae6  push    rbx
0x140c52ae7  push    rsi
0x140c52ae8  push    rdi
0x140c52ae9  push    r12
0x140c52aeb  push    r13
0x140c52aed  push    r14
0x140c52aef  push    r15
0x140c52af1  lea     rbp, [rsp-98h]
0x140c52af9  sub     rsp, 198h
0x140c52b00  mov     rax, cs:__security_cookie
0x140c52b07  xor     rax, rsp
0x140c52b0a  mov     [rbp+0D0h+var_48], rax
0x140c52b11  xor     r13d, r13d
0x140c52b14  xorps   xmm0, xmm0
0x140c52b17  mov     r15, rcx
0x140c52b1a  mov     [rsp+1D0h+var_180], r13
0x140c52b1f  xor     eax, eax
0x140c52b21  mov     qword ptr [rsp+1D0h+var_160], r13
0x140c52b26  lea     rcx, [rbp+0D0h+var_100]; void *
0x140c52b2a  mov     [rbp+0D0h+var_148], r13
0x140c52b2e  xor     edx, edx; Val
0x140c52b30  mov     [rsp+1D0h+var_188], r13
0x140c52b35  mov     r8d, 94h; Size
0x140c52b3b  mov     [rbp+0D0h+var_140], r13
0x140c52b3f  movups  xmmword ptr [rbp+0D0h+var_128.Length], xmm0
0x140c52b43  mov     [rsp+1D0h+var_168], r13d
0x140c52b48  movups  [rbp+0D0h+var_138], xmm0
0x140c52b4c  mov     [rsp+1D0h+var_170], r13d
0x140c52b51  mov     [rsp+1D0h+var_16C], r13d
0x140c52b56  movups  xmmword ptr [rbp+0D0h+DestinationString.Length], xmm0
0x140c52b5a  mov     [rbp+0D0h+var_FC], eax
0x140c52b5d  call    memset_0
0x140c52b62  call    PsGetCurrentServerSiloGlobals
0x140c52b67  mov     edx, 200h
0x140c52b6c  lea     ecx, [r13+40h]
0x140c52b70  mov     r8d, 74696E49h
0x140c52b76  mov     rax, [rax+4D0h]
0x140c52b7d  mov     [rsp+1D0h+var_158], rax
0x140c52b82  call    ExAllocatePool2
0x140c52b87  mov     r12, rax
0x140c52b8a  test    rax, rax
0x140c52b8d  jnz     short loc_140C52B98
0x140c52b8f  lea     ecx, [rax+31h]; BugCheckCode
0x140c52b92  call    KeBugCheck
0x140c52b98  mov     ebx, 1
0x140c52b9d  mov     cs:InitializationPhase, ebx
0x140c52ba3  mov     rcx, gs:188h; Thread
0x140c52bac  lea     edx, [rbx+1Eh]; Priority
0x140c52baf  call    KeSetPriorityThread
0x140c52bb4  mov     rcx, [r15+0D8h]; String
0x140c52bbb  lea     rsi, cs:140000000h
0x140c52bc2  test    rcx, rcx
0x140c52bc5  jz      loc_140C52DB6
0x140c52bcb  call    _strupr
0x140c52bd0  mov     r14, rax
0x140c52bd3  test    rax, rax
0x140c52bd6  jz      loc_140C52DC2
0x140c52bdc  lea     rdx, aHypervisorroot; " HYPERVISORROOTPROC="
0x140c52be3  mov     rcx, rax; Str
0x140c52be6  call    strstr
0x140c52beb  test    rax, rax
0x140c52bee  jz      short loc_140C52C13
0x140c52bf0  lea     rdx, asc_140CAD170; "="
0x140c52bf7  mov     rcx, rax; Str
0x140c52bfa  call    strstr
0x140c52bff  test    rax, rax
0x140c52c02  jz      short loc_140C52C13
0x140c52c04  lea     rcx, [rax+1]; Str
0x140c52c08  call    atol
0x140c52c0d  mov     cs:KeRootProcSpecified, eax
0x140c52c13  lea     rdx, aHypervisorroot_3; " HYPERVISORROOTPROCNUMANODES="
0x140c52c1a  mov     rcx, r14; Str
0x140c52c1d  call    strstr
0x140c52c22  mov     rdi, rax
0x140c52c25  test    rax, rax
0x140c52c28  jz      short loc_140C52C3C
0x140c52c2a  lea     rdx, asc_140CAD170; "="
0x140c52c31  mov     rcx, rax; Str
0x140c52c34  call    strstr
0x140c52c39  mov     rdi, rax
0x140c52c3c  test    rdi, rdi
0x140c52c3f  jz      short loc_140C52C7D
0x140c52c41  mov     eax, cs:KeRootProcNumaNodesSpecified
0x140c52c47  cmp     eax, 40h ; '@'
0x140c52c4a  jnb     short loc_140C52C7D
0x140c52c4c  add     rdi, rbx
0x140c52c4f  mov     ebx, eax
0x140c52c51  mov     rcx, rdi; Str
0x140c52c54  call    atol
0x140c52c59  mov     word ptr ds:rva KeRootProcNumaNodes[rsi+rbx*2], ax
0x140c52c61  mov     ebx, 1
0x140c52c66  add     cs:KeRootProcNumaNodesSpecified, ebx
0x140c52c6c  jmp     short loc_140C52C75
0x140c52c6e  test    al, 0DFh
0x140c52c70  jz      short loc_140C52C7D
0x140c52c72  add     rdi, rbx
0x140c52c75  mov     al, [rdi]
0x140c52c77  cmp     al, 2Ch ; ','
0x140c52c79  jnz     short loc_140C52C6E
0x140c52c7b  jmp     short loc_140C52C3C
0x140c52c7d  lea     rdx, aHypervisorroot_1; " HYPERVISORROOTPROCNUMANODELPS="
0x140c52c84  mov     rcx, r14; Str
0x140c52c87  call    strstr
0x140c52c8c  mov     rsi, rax
0x140c52c8f  test    rax, rax
0x140c52c92  jz      short loc_140C52CBA
0x140c52c94  lea     rdx, asc_140CAD170; "="
0x140c52c9b  mov     rcx, rax; Str
0x140c52c9e  call    strstr
0x140c52ca3  mov     rsi, rax
0x140c52ca6  mov     cs:KeRootProcNumaNodeLpsSpecified, bl
0x140c52cac  mov     cs:KeRootProcNumaNodesSpecified, r13d
0x140c52cb3  mov     cs:KeRootProcSpecified, r13d
0x140c52cba  test    rsi, rsi
0x140c52cbd  jz      loc_140C52DBB
0x140c52cc3  inc     rsi
0x140c52cc6  mov     [rsp+1D0h+EndPtr], r13
0x140c52ccb  mov     rcx, rsi; Str
0x140c52cce  lea     rdx, [rsp+1D0h+EndPtr]; EndPtr
0x140c52cd3  mov     r8d, 0Ah; Radix
0x140c52cd9  call    strtoul
0x140c52cde  mov     rcx, [rsp+1D0h+EndPtr]
0x140c52ce3  mov     ebx, eax
0x140c52ce5  cmp     rsi, rcx
0x140c52ce8  jz      short loc_140C52D0F
0x140c52cea  cmp     byte ptr [rcx], 5Fh ; '_'
0x140c52ced  jnz     short loc_140C52D0F
0x140c52cef  lea     rsi, [rcx+1]
0x140c52cf3  mov     r8d, 0Ah; Radix
0x140c52cf9  mov     rcx, rsi; Str
0x140c52cfc  lea     rdx, [rsp+1D0h+EndPtr]; EndPtr
0x140c52d01  call    strtoul
0x140c52d06  mov     rcx, [rsp+1D0h+EndPtr]
0x140c52d0b  mov     edi, eax
0x140c52d0d  jmp     short loc_140C52D12
0x140c52d0f  mov     edi, r13d
0x140c52d12  cmp     rsi, rcx
0x140c52d15  jz      short loc_140C52D92
0x140c52d17  cmp     byte ptr [rcx], 3Dh ; '='
0x140c52d1a  jnz     short loc_140C52D92
0x140c52d1c  cmp     ebx, 40h ; '@'
0x140c52d1f  jnb     short loc_140C52D92
0x140c52d21  add     rbx, rbx
0x140c52d24  lea     rsi, [rcx+1]
0x140c52d28  lea     rcx, cs:140000000h
0x140c52d2f  cmp     ds:rva qword_140FC06F8[rcx+rbx*8], r13
0x140c52d37  jnz     short loc_140C52D6E
0x140c52d39  mov     edx, 100h
0x140c52d3e  mov     ecx, 40h ; '@'
0x140c52d43  mov     r8d, 800h
0x140c52d49  call    ExAllocatePool2
0x140c52d4e  test    rax, rax
0x140c52d51  jz      short loc_140C52DAB
0x140c52d53  lea     rcx, cs:140000000h
0x140c52d5a  mov     ds:rva KeRootProcNumaNodeLps[rcx+rbx*8], 800h
0x140c52d66  mov     ds:rva qword_140FC06F8[rcx+rbx*8], rax
0x140c52d6e  cmp     edi, 20h ; ' '
0x140c52d71  jnb     short loc_140C52D92
0x140c52d73  mov     rbx, ds:rva qword_140FC06F8[rcx+rbx*8]
0x140c52d7b  lea     rdx, [rsp+1D0h+EndPtr]; EndPtr
0x140c52d80  mov     rcx, rsi; String
0x140c52d83  mov     r8d, 10h; Radix
0x140c52d89  call    _strtoui64
0x140c52d8e  mov     [rbx+rdi*8], rax
0x140c52d92  mov     ebx, 1
0x140c52d97  jmp     short loc_140C52DA0
0x140c52d99  test    al, 0DFh
0x140c52d9b  jz      short loc_140C52DBB
0x140c52d9d  add     rsi, rbx
0x140c52da0  mov     al, [rsi]
0x140c52da2  cmp     al, 2Ch ; ','
0x140c52da4  jnz     short loc_140C52D99
0x140c52da6  jmp     loc_140C52CBA
0x140c52dab  mov     ecx, 31h ; '1'; BugCheckCode
0x140c52db0  call    KeBugCheck
0x140c52db6  mov     r14, r13
0x140c52db9  jmp     short loc_140C52DC2
0x140c52dbb  lea     rsi, cs:140000000h
0x140c52dc2  mov     rax, cs:KiSubNodeConfigBlock
0x140c52dc9  mov     rcx, r15
0x140c52dcc  mov     cs:word_140E4CAC8, r13w
0x140c52dd4  and     byte ptr [rax+5], 0FCh
0x140c52dd8  mov     [rax+4], r13b
0x140c52ddc  call    KiPerformGroupConfiguration
0x140c52de1  mov     rcx, cs:KiSubNodeConfigBlock
0x140c52de8  movzx   ecx, word ptr [rcx+6]
0x140c52dec  call    KiCommitGroupSubNodeAssignments
0x140c52df1  mov     rax, cs:KiSubNodeConfigBlock
0x140c52df8  mov     rdx, r15
0x140c52dfb  mov     ecx, cs:InitializationPhase; BugCheckParameter3
0x140c52e01  or      [rax+10h], rbx
0x140c52e05  call    HalInitSystem
0x140c52e0a  test    al, al
0x140c52e0c  jz      loc_140C53F27
0x140c52e12  mov     ecx, cs:InitializationPhase; BugCheckParameter2
0x140c52e18  mov     rdx, r15
0x140c52e1b  call    KeInitializeClock
0x140c52e20  mov     edi, 80000000h
0x140c52e25  test    r14, r14
0x140c52e28  jz      short loc_140C52E3E
0x140c52e2a  lea     rdx, aNoguiboot; "NOGUIBOOT"
0x140c52e31  mov     rcx, r14; Str
0x140c52e34  call    strstr
0x140c52e39  test    rax, rax
0x140c52e3c  jnz     short loc_140C52EB5
0x140c52e3e  cmp     cs:byte_140E4C010, r13b
0x140c52e45  mov     cs:byte_140E4BFB0, r13b
0x140c52e4c  jz      short loc_140C52E8B
0x140c52e4e  cmp     cs:byte_140E4C018, r13b
0x140c52e55  jz      short loc_140C52E68
0x140c52e57  mov     cl, bl
0x140c52e59  call    BgDisplayProgressIndicator
0x140c52e5e  test    eax, eax
0x140c52e60  js      short loc_140C52E68
0x140c52e62  mov     cs:byte_140E4C011, bl
0x140c52e68  cmp     cs:byte_140E4C010, r13b
0x140c52e6f  jz      short loc_140C52E8B
0x140c52e71  cmp     cs:byte_140E4C018, r13b
0x140c52e78  jz      short loc_140C52E8B
0x140c52e7a  mov     cl, bl
0x140c52e7c  call    BgDisplayBackgroundUpdate
0x140c52e81  test    eax, eax
0x140c52e83  js      short loc_140C52E8B
0x140c52e85  mov     cs:byte_140E4BFE1, bl
0x140c52e8b  lea     rax, DisplayFilter
0x140c52e92  mov     r8d, 7
0x140c52e98  mov     rdx, r15
0x140c52e9b  mov     cs:qword_140E4BFB8, rax
0x140c52ea2  mov     ecx, ebx
0x140c52ea4  call    InbvDriverInitialize
0x140c52ea9  xor     ecx, ecx
0x140c52eab  call    DisplayBootBitmap
0x140c52eb0  test    r14, r14
0x140c52eb3  jz      short loc_140C52EF1
0x140c52eb5  lea     rdx, aMinint_0; "MININT"
0x140c52ebc  mov     rcx, r14; Str
0x140c52ebf  call    strstr
0x140c52ec4  test    rax, rax
0x140c52ec7  jz      short loc_140C52EF1
0x140c52ec9  lea     rdx, aInram; "INRAM"
0x140c52ed0  mov     cs:InitIsWinPEMode, bl
0x140c52ed6  mov     rcx, r14; Str
0x140c52ed9  call    strstr
0x140c52ede  test    rax, rax
0x140c52ee1  jz      short loc_140C52EEB
0x140c52ee3  or      cs:InitWinPEModeType, edi
0x140c52ee9  jmp     short loc_140C52EF1
0x140c52eeb  or      cs:InitWinPEModeType, ebx
0x140c52ef1  xor     r8d, r8d
0x140c52ef4  lea     rax, [rsp+1D0h+var_188]
0x140c52ef9  mov     r9d, 4000007Eh
0x140c52eff  mov     qword ptr [rsp+1D0h+dwFlags], rax
0x140c52f04  mov     rcx, rsi
0x140c52f07  lea     edx, [r8+0Bh]
0x140c52f0b  call    RtlFindMessage
0x140c52f10  cmp     cs:CmCSDVersionString.Length, r13w
0x140c52f18  mov     rbx, r12
0x140c52f1b  mov     [rsp+1D0h+EndPtr], rbx
0x140c52f20  mov     esi, eax
0x140c52f22  mov     [rbp+0D0h+pcbRemaining], 100h
0x140c52f2a  jz      short loc_140C52F87
0x140c52f2c  lea     rax, CmCSDVersionString
0x140c52f33  mov     edx, 0FFh; cbDest
0x140c52f38  mov     qword ptr [rsp+1D0h+Depth], rax
0x140c52f3d  lea     r9, [rbp+0D0h+pcbRemaining]; pcbRemaining
0x140c52f41  lea     rax, aWz_1; ": %wZ"
0x140c52f48  mov     rcx, r12; pszDest
0x140c52f4b  mov     [rsp+1D0h+pszFormat], rax; pszFormat
0x140c52f50  lea     r8, [rsp+1D0h+EndPtr]; ppszDestEnd
0x140c52f55  mov     qword ptr [rsp+1D0h+dwFlags], r13; dwFlags
0x140c52f5a  call    RtlStringCbPrintfExA
0x140c52f5f  test    eax, eax
0x140c52f61  jns     short loc_140C52F7C
0x140c52f63  xor     r9d, r9d; BugCheckParameter3
0x140c52f66  movsxd  rdx, eax; BugCheckParameter1
0x140c52f69  mov     qword ptr [rsp+1D0h+dwFlags], r13; BugCheckParameter4
0x140c52f6e  lea     ecx, [r9+32h]; BugCheckCode
0x140c52f72  lea     r8d, [r9+7]; BugCheckParameter2
0x140c52f76  call    KeBugCheckEx
0x140c52f7c  mov     rbx, [rsp+1D0h+EndPtr]
0x140c52f81  mov     rdi, [rbp+0D0h+pcbRemaining]
0x140c52f85  jmp     short loc_140C52F8C
0x140c52f87  mov     edi, 0FFh
0x140c52f8c  mov     r9d, 0Ah
0x140c52f92  mov     [rbx], r13b
0x140c52f95  lea     r8, aUU; "%u.%u"
0x140c52f9c  mov     qword ptr [rsp+1D0h+dwFlags], r13
0x140c52fa1  lea     rcx, [rbp+0D0h+pszDest]; pszDest
0x140c52fa5  inc     rbx
0x140c52fa8  lea     edx, [r9+0Eh]; cbDest
0x140c52fac  call    RtlStringCbPrintfA
0x140c52fb1  test    eax, eax
0x140c52fb3  jns     short loc_140C52FD0
0x140c52fb5  mov     ecx, 32h ; '2'; BugCheckCode
0x140c52fba  movsxd  rdx, eax; BugCheckParameter1
0x140c52fbd  mov     qword ptr [rsp+1D0h+dwFlags], r13; BugCheckParameter4
0x140c52fc2  lea     r9d, [rcx-31h]; BugCheckParameter3
0x140c52fc6  lea     r8d, [rcx-2Bh]; BugCheckParameter2
0x140c52fca  call    KeBugCheckEx
  ... truncated ...
```
