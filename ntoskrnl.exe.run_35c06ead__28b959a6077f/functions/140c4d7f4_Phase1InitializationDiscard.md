# Phase1InitializationDiscard

- ea: `0x140c4d7f4`
- end: `0x140c4ec42`
- name: `Phase1InitializationDiscard`
- size: `5198`
- prototype: ``
- caller_count: `1`
- callee_count: `98`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140741f40`

## callees

- `0x140309b40`
- `0x14031ae30`
- `0x140332f10`
- `0x1403d8940`
- `0x1403e8070`
- `0x1403f2d50`
- `0x1403fa510`
- `0x1403fc338`
- `0x14040bd20`
- `0x14040de38`
- `0x140421c80`
- `0x1404358c4`
- `0x14049cbe0`
- `0x1405399c0`
- `0x14053a510`
- `0x14053a530`
- `0x14053bd50`
- `0x14053c22c`
- `0x14053c4c0`
- `0x14053c4f0`
- `0x14053c750`
- `0x14057c214`
- `0x14057c464`
- `0x14057c4c0`
- `0x14057c63c`
- `0x1405bc600`
- `0x1405c9000`
- `0x1405ecd58`
- `0x14069d8f0`
- `0x1406c9414`
- `0x1406d9d70`
- `0x1406dd490`
- `0x1406de050`
- `0x1406de4b0`
- `0x1406f4880`
- `0x1406f4fa0`
- `0x1407566f0`
- `0x14077f5e4`
- `0x1407b5e48`
- `0x1407d7e7c`
- `0x1407e1848`
- `0x1407e1a24`
- `0x1407e3730`
- `0x1407e3c6c`
- `0x1407e41b4`
- `0x1407f0bf4`
- `0x140807e50`
- `0x140807e88`
- `0x14082d9e8`
- `0x1409f590c`

## import_xrefs

- `symcryptk!SymCryptEntropyAccumulatorGlobalInitFromRegistry` at `0x140c4eaf5`
- `symcryptk!SymCryptEntropyAccumulatorGlobalInitFromRegistry` at `0x140c4eaf5`
- `ext-ms-win-ntos-tm-l1-1-0!TmInitSystem` at `0x140c4e35a`
- `ext-ms-win-ntos-tm-l1-1-0!TmInitSystem` at `0x140c4e35a`
- `kdcom!KdInitialize` at `0x140c4e8d2`
- `kdcom!KdInitialize` at `0x140c4e8d2`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrInitSystem` at `0x140c4e5f6`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrInitSystem` at `0x140c4e5f6`
- `ext-ms-win-ntos-ucode-l1-1-0!ExpMicrocodeInitialization` at `0x140c4ea90`
- `ext-ms-win-ntos-ucode-l1-1-0!ExpMicrocodeInitialization` at `0x140c4ea90`

## string_xrefs

- `0x140c4e964`: `DSREPAIR`

## pseudocode

```c
bool __fastcall Phase1InitializationDiscard(ULONG_PTR BugCheckParameter3)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  char *Pool2; // r12
  char *v5; // rcx
  char *v6; // rax
  const char *v7; // r14
  char *v8; // rax
  char *v9; // rax
  char *v10; // rax
  char *v11; // rdi
  __int64 v12; // rbx
  char *v13; // rax
  char *v14; // rsi
  unsigned int v15; // eax
  char *v16; // rcx
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  ULONG_PTR v24; // rcx
  __int64 v25; // rcx
  int Message; // eax
  char *v27; // rbx
  int v28; // esi
  NTSTATUS v29; // eax
  size_t v30; // rdi
  char *v31; // rbx
  NTSTATUS v32; // eax
  NTSTATUS v33; // eax
  NTSTATUS v34; // eax
  _OWORD *v35; // rax
  char *v36; // rcx
  __int64 v37; // rdx
  __int128 v38; // xmm1
  char v39; // si
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rcx
  char *v44; // rax
  char *v45; // rax
  __int16 v46; // bx
  __int64 CurrentServerSiloGlobals; // rax
  LARGE_INTEGER v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rax
  char *v52; // rax
  char *v53; // rax
  char *v54; // rax
  char *v55; // rax
  char *v56; // rax
  char *v57; // rax
  char *v58; // rax
  char *v59; // rax
  char *v60; // rax
  char *v61; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  int v63; // eax
  const char *v64; // rbx
  int v65; // r9d
  int v66; // edi
  __int64 v67; // rbx
  _DWORD *v68; // rax
  __int64 i; // rdx
  __int64 v70; // rcx
  const char *v71; // r8
  NTSTATUS v72; // eax
  bool v73; // r12
  int inited; // eax
  int v75; // eax
  int v76; // eax
  int SystemRootLink; // eax
  int v78; // eax
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // r8
  __int64 *v82; // r9
  __int64 DisplayContext; // rax
  ULONG_PTR v84; // rbx
  int v85; // eax
  int v86; // eax
  int v87; // eax
  int v88; // eax
  __int64 v89; // rcx
  __int64 v90; // rdi
  int v91; // ebx
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // rax
  int v95; // esi
  char *v101; // rax
  const char *v102; // rdi
  int v103; // ebx
  int v104; // r9d
  int v105; // ebx
  int v106; // ebx
  __int64 v107; // rbx
  int v108; // eax
  ULONG dwFlags[2]; // [rsp+20h] [rbp-E0h]
  int pszFormat; // [rsp+28h] [rbp-D8h]
  char v112[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v113; // [rsp+48h] [rbp-B8h] BYREF
  LONGLONG v114; // [rsp+50h] [rbp-B0h] BYREF
  char *EndPtr; // [rsp+58h] [rbp-A8h] BYREF
  int v116; // [rsp+60h] [rbp-A0h] BYREF
  int v117; // [rsp+64h] [rbp-9Ch] BYREF
  int v118; // [rsp+68h] [rbp-98h] BYREF
  LARGE_INTEGER v119; // [rsp+70h] [rbp-90h] BYREF
  __int64 v120; // [rsp+78h] [rbp-88h] BYREF
  size_t pcbRemaining; // [rsp+80h] [rbp-80h] BYREF
  __int64 v122; // [rsp+88h] [rbp-78h] BYREF
  __int64 v123; // [rsp+90h] [rbp-70h] BYREF
  __int128 v124; // [rsp+98h] [rbp-68h] BYREF
  STRING v125; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD v127[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 (__fastcall *v128)(); // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v129)(); // [rsp+E0h] [rbp-20h]
  __int64 (__fastcall *v130)(); // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v131)(int, int, int, int, __int64, __int64); // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall *v132)(); // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall *v133)(); // [rsp+100h] [rbp+0h]
  __int64 (__fastcall *v134)(); // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v135)(ULONG_PTR); // [rsp+110h] [rbp+10h]
  __int64 (__fastcall *v136)(); // [rsp+118h] [rbp+18h]
  __int64 (__fastcall *v137)(); // [rsp+120h] [rbp+20h]
  _KWAIT_BLOCK v138; // [rsp+130h] [rbp+30h]
  __int64 v139; // [rsp+160h] [rbp+60h]
  char pszDest[24]; // [rsp+170h] [rbp+70h] BYREF

  v114 = 0;
  v119.QuadPart = 0;
  v122 = 0;
  v113 = 0;
  v123 = 0;
  v125 = 0;
  v118 = 0;
  v124 = 0;
  v116 = 0;
  v117 = 0;
  DestinationString = 0;
  v127[1] = 0;
  memset_0(v127, 0, 0x94u);
  v120 = *(_QWORD *)(PsGetCurrentServerSiloGlobals(v3, v2) + 1232);
  Pool2 = (char *)ExAllocatePool2(64, 512, 1953066569);
  if ( !Pool2 )
    KeBugCheck(0x31u);
  LODWORD(InitializationPhase) = 1;
  KeSetPriorityThread(KeGetCurrentThread(), 31);
  v5 = *(char **)(BugCheckParameter3 + 216);
  if ( v5 )
  {
    v6 = strupr(v5);
    v7 = v6;
    if ( v6 )
    {
      v8 = strstr(v6, " HYPERVISORROOTPROC=");
      if ( v8 )
      {
        v9 = strstr(v8, "=");
        if ( v9 )
          KeRootProcSpecified = atol(v9 + 1);
      }
      v10 = strstr(v7, " HYPERVISORROOTPROCNUMANODES=");
      v11 = v10;
      if ( v10 )
        v11 = strstr(v10, "=");
      while ( v11 && (unsigned int)KeRootProcNumaNodesSpecified < 0x40 )
      {
        ++v11;
        v12 = (unsigned int)KeRootProcNumaNodesSpecified;
        *((_WORD *)&KeRootProcNumaNodes + v12) = atol(v11);
        ++KeRootProcNumaNodesSpecified;
        while ( *v11 != 44 )
        {
          if ( (*v11 & 0xDF) == 0 )
            goto LABEL_17;
          ++v11;
        }
      }
LABEL_17:
      v13 = strstr(v7, " HYPERVISORROOTPROCNUMANODELPS=");
      v14 = v13;
      if ( v13 )
      {
        v14 = strstr(v13, "=");
        KeRootProcNumaNodeLpsSpecified = 1;
        KeRootProcNumaNodesSpecified = 0;
        KeRootProcSpecified = 0;
      }
      while ( v14 )
      {
        ++v14;
        EndPtr = 0;
        v15 = strtoul(v14, &EndPtr, 10);
        v16 = EndPtr;
        v17 = v15;
        if ( v14 == EndPtr || *EndPtr != 95 )
        {
          v19 = 0;
        }
        else
        {
          v14 = EndPtr + 1;
          v18 = strtoul(EndPtr + 1, &EndPtr, 10);
          v16 = EndPtr;
          v19 = v18;
        }
        if ( v14 != v16 && *v16 == 61 && (unsigned int)v17 < 0x40 )
        {
          v20 = 2 * v17;
          v14 = v16 + 1;
          if ( !qword_140FC06F8[v20] )
          {
            v21 = ExAllocatePool2(64, 256, 2048);
            if ( !v21 )
              KeBugCheck(0x31u);
            KeRootProcNumaNodeLps[v20] = 2048;
            qword_140FC06F8[v20] = v21;
          }
          if ( (unsigned int)v19 < 0x20 )
          {
            v22 = qword_140FC06F8[v20];
            *(_QWORD *)(v22 + 8 * v19) = strtoui64(v14, &EndPtr, 16);
          }
        }
        while ( *v14 != 44 )
        {
          if ( (*v14 & 0xDF) == 0 )
            goto LABEL_39;
          ++v14;
        }
      }
    }
  }
  else
  {
    v7 = 0;
  }
LABEL_39:
  v23 = KiSubNodeConfigBlock;
  word_140E4CB38 = 0;
  *(_BYTE *)(KiSubNodeConfigBlock + 5) &= 0xFCu;
  *(_BYTE *)(v23 + 4) = 0;
  KiPerformGroupConfiguration(BugCheckParameter3);
  KiCommitGroupSubNodeAssignments(*(unsigned __int16 *)(KiSubNodeConfigBlock + 6));
  v24 = (unsigned int)InitializationPhase;
  *(_QWORD *)(KiSubNodeConfigBlock + 16) |= 1uLL;
  if ( !(unsigned __int8)HalInitSystem(v24) )
    goto LABEL_226;
  KeInitializeClock((unsigned int)InitializationPhase);
  if ( v7 && strstr(v7, "NOGUIBOOT") )
    goto LABEL_229;
  byte_140E4BFF8 = 0;
  if ( byte_140E4C061 )
  {
    if ( byte_140E4C062 )
    {
      LOBYTE(v25) = 1;
      if ( (int)BgDisplayProgressIndicator(v25) >= 0 )
        byte_140E4C060 = 1;
    }
    if ( byte_140E4C061 )
    {
      if ( byte_140E4C062 )
      {
        LOBYTE(v25) = 1;
        if ( (int)BgDisplayBackgroundUpdate(v25) >= 0 )
          byte_140E4C030 = 1;
      }
    }
  }
  qword_140E4C008 = (__int64)DisplayFilter;
  InbvDriverInitialize(1, BugCheckParameter3, 7);
  DisplayBootBitmap(0);
  if ( v7 )
  {
LABEL_229:
    if ( strstr(v7, "MININT") )
    {
      InitIsWinPEMode = 1;
      if ( strstr(v7, "INRAM") )
        InitWinPEModeType |= 0x80000000;
      else
        InitWinPEModeType |= 1u;
    }
  }
  Message = RtlFindMessage(0x40000000u, 11, 0, 1073741950, (__int64)&v113);
  v27 = Pool2;
  EndPtr = Pool2;
  v28 = Message;
  pcbRemaining = 256;
  if ( CmCSDVersionString.Length )
  {
    v29 = RtlStringCbPrintfExA(Pool2, 0xFFu, &EndPtr, &pcbRemaining, 0, ": %wZ");
    if ( v29 < 0 )
      KeBugCheckEx(0x32u, v29, 7u, 0, 0);
    v27 = EndPtr;
    v30 = pcbRemaining;
  }
  else
  {
    v30 = 255;
  }
  *v27 = 0;
  v31 = v27 + 1;
  v32 = RtlStringCbPrintfA(pszDest, 0x18u, "%u.%u", 10, 0);
  if ( v32 < 0 )
    KeBugCheckEx(0x32u, v32, 7u, 1u, 0);
  if ( v28 < 0 )
  {
    v34 = RtlStringCbCopyA(v31, v30, "MICROSOFT (R) WINDOWS (TM)\n");
    if ( v34 < 0 )
      KeBugCheckEx(0x32u, v34, 7u, 3u, 0);
  }
  else
  {
    pszFormat = (int)Pool2;
    dwFlags[0] = (unsigned __int16)NtBuildNumber;
    v33 = RtlStringCbPrintfA(v31, v30, (NTSTRSAFE_PCSTR)(v113 + 4), pszDest, *(_QWORD *)dwFlags);
    if ( v33 < 0 )
      KeBugCheckEx(0x32u, v33, 7u, 2u, 0);
  }
  pcbRemaining = (size_t)(Pool2 + 256);
  InbvDisplayString(v31);
  v35 = Pool2 + 256;
  v36 = Pool2;
  v37 = 2;
  do
  {
    *v35 = *(_OWORD *)v36;
    v35[1] = *((_OWORD *)v36 + 1);
    v35[2] = *((_OWORD *)v36 + 2);
    v35[3] = *((_OWORD *)v36 + 3);
    v35[4] = *((_OWORD *)v36 + 4);
    v35[5] = *((_OWORD *)v36 + 5);
    v35[6] = *((_OWORD *)v36 + 6);
    v38 = *((_OWORD *)v36 + 7);
    v36 += 128;
    v35[7] = v38;
    v35 += 8;
    --v37;
  }
  while ( v37 );
  if ( !(unsigned __int8)PoInitSystem(0, BugCheckParameter3) )
LABEL_225:
    KeBugCheck(0xA0u);
  v39 = 0;
  if ( !ExpRealTimeIsUniversal )
  {
    v40 = v120;
    v41 = *(_DWORD *)(v120 + 436);
    if ( v41 == -1 )
    {
      v39 = 1;
      *(_DWORD *)(v120 + 436) = *(_DWORD *)&PspActiveProcessLock.ApcStateFill[20];
      v41 = *(_DWORD *)&PspActiveProcessLock.ApcStateFill[20];
    }
    *(_QWORD *)(v40 + 440) = 600000000LL * v41;
    *(_DWORD *)(MmWriteableSharedUserData + 604) = 0;
    ExpWriteTimeZoneBias();
  }
  GetBootSystemTime(*(_QWORD *)(BugCheckParameter3 + 240), &v114);
  if ( v7 )
  {
    v44 = strstr(v7, "YEAR");
    if ( v44 )
    {
      v45 = strstr(v44, "=");
      if ( v45 )
      {
        v46 = atol(v45 + 1);
        RtlpTimeToTimeFields(&v114, &v124);
        LOWORD(v124) = v46;
        RtlpTimeFieldsToTime(&v124, &v114);
      }
    }
  }
  if ( ExpRealTimeIsUniversal )
  {
    v48.QuadPart = v114;
  }
  else
  {
    CurrentServerSiloGlobals = PsGetCurrentServerSiloGlobals(v43, v42);
    v48.QuadPart = v114 - *(_QWORD *)(*(_QWORD *)(CurrentServerSiloGlobals + 1232) + 440LL);
  }
  v119 = v48;
  KeSetSystemTime(&v114, &v122, 4);
  v51 = PsGetCurrentServerSiloGlobals(v50, v49);
  PoNotifySystemTimeSet(
    (unsigned int)&v114,
    (unsigned int)&v122,
    0,
    (unsigned int)&v119,
    *(_DWORD *)(*(_QWORD *)(v51 + 1232) + 436LL),
    pszFormat,
    ExpSystemIsInCmosMode);
  RtlInitUnicodeString(&DestinationString, L"Kernel-RegisteredProcessors");
  if ( (int)ZwQueryLicenseValue(&DestinationString, &v117, &KeRegisteredProcessors, 4, &v116) < 0
    || v116 != 4
    || v117 != 4 )
  {
    KeRegisteredProcessors = 1;
  }
  if ( v7 )
  {
    v52 = strstr(v7, " BOOTPROC=");
    if ( v52 )
    {
      v53 = strstr(v52, "=");
      if ( v53 )
        KeBootprocSpecified = atol(v53 + 1);
    }
    v54 = strstr(v7, " NUMPROC=");
    if ( v54 )
    {
      v55 = strstr(v54, "=");
      if ( v55 )
        KeNumprocSpecified = atol(v55 + 1);
    }
    v56 = strstr(v7, " HYPERVISORNUMPROC=");
    if ( v56 )
    {
      v57 = strstr(v56, "=");
      if ( v57 )
        KeHypervisorNumprocSpecified = atol(v57 + 1);
    }
    if ( !KeRootProcNumaNodeLpsSpecified )
    {
      v58 = strstr(v7, " HYPERVISORROOTPROCPERNODE=");
      if ( v58 )
      {
        v59 = strstr(v58, "=");
        if ( v59 )
          *(_DWORD *)((char *)&Mm64BitPhysicalAddress + 7) = atol(v59 + 1);
      }
      v60 = strstr(v7, " HYPERVISORROOTPROCPERCORE=");
      if ( v60 )
      {
        v61 = strstr(v60, "=");
        if ( v61 )
          *(_DWORD *)((char *)&Mm64BitPhysicalAddress + 3) = atol(v61 + 1);
      }
    }
    if ( strstr(v7, " MAXPROC") )
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
    v63 = ExLookasideMgrsAllocate();
    if ( v63 < 0 )
      KeBugCheckEx(0x32u, v63, 0xFu, 1u, 0);
  }
  v64 = (int)RtlFindMessage(0x40000000u, 11, 0, 1073741961, (__int64)&v123) < 0
      ? "MultiProcessor Kernel\r\n"
      : (const char *)(v123 + 4);
  if ( !(unsigned __int8)HalAllProcessorsStarted() )
LABEL_226:
    KeBugCheck(0x61u);
  RtlInitAnsiString(&v125, v64);
  if ( v125.Length >= 2u )
    v125.Length -= 2;
  v65 = 1073741981;
  if ( (unsigned int)KeNumberProcessors_0 <= 1 )
    v65 = 1073741960;
  v66 = RtlFindMessage(0x40000000u, 11, 0, v65, (__int64)&v113);
  v67 = 0;
  v68 = (_DWORD *)MmReferencePhysicalMemoryBlock();
  for ( i = 0; (unsigned int)i < *v68; v67 += *(_QWORD *)&v68[4 * v70 + 6] )
  {
    v70 = (unsigned int)i;
    i = (unsigned int)(i + 1);
  }
  MmDereferencePhysicalMemoryBlock(v68, i);
  if ( v66 < 0 )
    v71 = "%u System Processor [%u MB Memory] %Z\n";
  else
    v71 = (const char *)(v113 + 4);
  v72 = RtlStringCbPrintfA(
          Pool2,
          0x100u,
          v71,
          (unsigned int)KeNumberProcessors_0,
          (unsigned __int64)(v67 + 255) >> 8,
          &v125);
  if ( v72 < 0 )
    KeBugCheckEx(0x32u, v72, 7u, 4u, 0);
  InbvDisplayString(Pool2);
  ExFreePoolWithTag(Pool2, 0);
  v73 = 0;
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
             &stru_140FBF218.WaitBlockFill11[112],
             &TmEnlistmentObjectType,
             &stru_140FBF218.WaitBlockFill11[104],
             &TmTransactionObjectType);
  if ( (int)(inited + 0x80000000) >= 0 && inited != -1073741637 )
    KeBugCheckEx(0x32u, 0, 0, 0, 0);
  v75 = DbgkInitialize();
  if ( v75 < 0 )
    KeBugCheckEx(0x32u, v75, 0, 0, 0);
  UcInitialize(0);
  BcdInitializeBcdSyncMutant();
  VerifierInitSystem(0);
  if ( !(unsigned __int8)SeInitSystem() )
    KeBugCheck(0x63u);
  LpcLegacyMaxMessageLength = 648;
  if ( (int)AlpcpInitSystem() < 0 )
    KeBugCheck(0x6Au);
  LpcPortObjectType = AlpcPortObjectType;
  v76 = SmInitSystem(0);
  if ( v76 < 0 )
    KeBugCheckEx(0x32u, v76, 0xDu, 0, 0);
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
  v78 = ExInitializeLeapSecondData();
  if ( v78 < 0 )
    KeBugCheckEx(0x32u, v78, 0xCu, 0, 0);
  v112[0] = 0;
  if ( (int)ExIsMultiSessionSku(v112) >= 0 && v112[0] )
    *(_DWORD *)(MmWriteableSharedUserData + 752) |= 0x100u;
  if ( RtlpMultiUsersInSessionSupported )
    *(_DWORD *)(MmWriteableSharedUserData + 752) |= 0x200u;
  if ( HIDWORD(WheapPfaLock.KernelStack) )
    *(_DWORD *)(MmWriteableSharedUserData + 752) |= 0x400u;
  qword_1410058F8 = KeQueryPerformanceCounter(0).QuadPart;
  memset_0(v127, 0, 0x98u);
  v128 = MmMapLockedRestartPages;
  v129 = MmUnmapLockedRestartPages;
  v130 = KeRemoveEnclavePage;
  v131 = KdPullRemoteFileEx;
  v132 = CmSaveKeyToBuffer;
  v133 = KeIsBugCheckActive;
  v134 = CmOpenKeyForBugCheckRecovery;
  v135 = MiPageToNode;
  v136 = MmGetNextNode;
  v137 = MmGetFileObjectForSection;
  v127[0] = 152;
  if ( VslVsmEnabled )
  {
    VslpIumKsrInitContext = (__int64)VslpKsrEnterIumSecureMode;
    v82 = &VslpIumKsrInitContext;
    qword_1410058A0 = (__int64)VslpRegisterKsrCallback;
  }
  else
  {
    v82 = 0;
  }
  DisplayContext = BgGetDisplayContext(v80, v79, v81, v82);
  v84 = (int)KsrInitSystem(BugCheckParameter3, v127, DisplayContext);
  qword_141005900 = KeQueryPerformanceCounter(0).QuadPart;
  if ( (int)(v84 + 0x80000000) >= 0 && (_DWORD)v84 != -1073741637 )
    KeBugCheckEx(0x32u, v84, 0, 1u, 0);
  ExpKeyManipLock.WaitBlock[3] = v138;
  *(_QWORD *)&ExpKeyManipLock.ThreadFlags2 = v139;
  v85 = EmInitSystem(0, BugCheckParameter3);
  if ( v85 < 0 )
    KeBugCheckEx(0x32u, v85, 8u, 0, 0);
  v86 = MfgInitSystem(BugCheckParameter3);
  if ( v86 < 0 )
    KeBugCheckEx(0x32u, v86, 9u, 0, 0);
  PfInitializeSuperfetch();
  v87 = SmInitSystem(1);
  if ( v87 < 0 )
    KeBugCheckEx(0x32u, v87, 0xEu, 0, 0);
  v88 = VmInitSystem(1);
  if ( v88 < 0 )
    KeBugCheckEx(0x32u, v88, 0xAu, 0, 0);
  if ( (*(_BYTE *)(*(_QWORD *)(BugCheckParameter3 + 240) + 2656LL) & 2) == 0 || strstr(v7, "FORCETIMESYNC") )
    ZwUpdateWnfStateData(&WNF_BOOT_INVALID_TIME_SOURCE, 0, 0, 0, 0, 0, 0);
  if ( (HvlpFlags & 0x2000000) != 0 )
    ZwUpdateWnfStateData(&WNF_HVL_CPU_MGMT_PARTITION, 0, 0, 0, 0, 0, 0);
  v118 = 0;
  FsRtlSendModernAppTermination(&v118, 1, 1);
  ExInitializeTimeRefresh();
  ExAcquireTimeRefreshLockExclusive(v89);
  ExInitializeUtcTimeZoneBias(&v119);
  v90 = v120;
  v91 = *(_DWORD *)(v120 + 436);
  ExpRefreshTimeZoneInformation(0);
  ExReleaseTimeRefreshLockExclusive();
  if ( v39 )
  {
    v94 = PsGetCurrentServerSiloGlobals(v93, v92);
    v114 = *(_QWORD *)(*(_QWORD *)(v94 + 1232) + 440LL) + v119.QuadPart;
    KeSetSystemTime(&v114, &v122, 4);
  }
  else if ( v91 != *(_DWORD *)(v90 + 436) )
  {
    ZwSetSystemTime(0, 0);
  }
  if ( !(unsigned __int8)FsRtlInitSystem() )
    KeBugCheck(0x68u);
  ExInitializeNPagedLookasideListInternal(
    (unsigned int)&PspTlsContext.ApcStateFill[32],
    0,
    0,
    512,
    88,
    1667529324,
    0,
    0);
  v95 = 1;
  _RAX = 1;
  __asm { cpuid }
  LODWORD(RtlpBootStatHandleLock.InitialStack) = _RCX & 0x200;
  HIDWORD(RtlpBootStatHandleLock.InitialStack) = (_RDX & 0x4000000) != 0 && (_RCX & 0x100002) == 1048578;
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)&PspTlsContext.StackBase, 0, 0, 0, 0x38u, 0x656C5252u, 0x10u);
  HvlDebuggerSupportInitialize(BugCheckParameter3);
  HalReportResourceUsage(0);
  KdInitialize(1, BugCheckParameter3, &KdpContext);
  if ( !(unsigned __int8)PpInitSystem() )
    KeBugCheck(0x90u);
  if ( v7 )
  {
    v101 = strstr(v7, "SAFEBOOT:");
    if ( v101 )
    {
      v102 = v101 + 9;
      if ( !strncmp(v101 + 9, "MINIMAL", 7u) )
      {
        v103 = 1;
        v102 += 7;
      }
      else if ( !strncmp(v102, "NETWORK", 7u) )
      {
        v103 = 2;
        v102 += 7;
        v95 = 2;
      }
      else if ( !strncmp(v102, "DSREPAIR", 8u) )
      {
        v103 = 3;
        v102 += 8;
        v95 = 3;
      }
      else
      {
        v103 = 0;
        v95 = 0;
      }
      LODWORD(InitSafeBootMode) = v103;
      if ( *v102 )
        v73 = strncmp(v102, "(ALTERNATESHELL)", 0x10u) == 0;
      if ( v95 )
      {
        v120 = 0;
        v104 = 0;
        v105 = v103 - 1;
        if ( v105 )
        {
          v106 = v105 - 1;
          if ( v106 )
          {
            if ( v106 == 1 )
              v104 = 170;
          }
          else
          {
            v104 = 169;
          }
        }
        else
        {
          v104 = 168;
        }
        if ( (int)RtlFindMessage(0x40000000u, 11, 0, v104, (__int64)&v120) >= 0 )
          InbvDisplayString(v120 + 4);
      }
    }
  }
  if ( (*(_DWORD *)(*(_QWORD *)(BugCheckParameter3 + 240) + 132LL) & 0x800) != 0 )
  {
    if ( (int)RtlFindMessage(0x40000000u, 11, 0, 183, (__int64)&v113) >= 0 )
      InbvDisplayString(v113 + 4);
    IopInitializeBootLogging(BugCheckParameter3, pcbRemaining);
  }
  ExpWatchProductTypeInitialization();
  *(_DWORD *)(MmWriteableSharedUserData + 736) = -1;
  BootApplicationPersistentDataProcess(0);
  ExpMicrocodeInitialization(2);
  if ( LODWORD(PspActiveProcessLock.Header.WaitListHead.Blink) > KeMaximumProcessors )
    LODWORD(PspActiveProcessLock.Header.WaitListHead.Blink) = KeMaximumProcessors;
  LODWORD(v113) = 0;
  *(_DWORD *)&WheapConfigTableLock.WaitBlockFill11[24] = 0;
  if ( (int)ExpGetOriginalImageVersionRegistryValue(&v113) >= 0 )
    *(_DWORD *)&WheapConfigTableLock.WaitBlockFill11[24] = v113;
  v107 = MmWriteableSharedUserData;
  *(_WORD *)(v107 + 726) = ExpComputeCyclesPerYield();
  if ( InitIsWinPEMode )
    CreateMiniNtBootKey();
  SymCryptEntropyAccumulatorGlobalInitFromRegistry();
  v108 = SeCodeIntegrityInitializePolicy(BugCheckParameter3);
  if ( v108 < 0 )
    KeBugCheckEx(0x32u, v108, 0x69436553u, 0, 0);
  KdpTimeSlipPending = 0;
  ExSaPageGroupDescriptorArrayLock.SchedulerAssistLastYieldBoostTime = (__int64)&ExSaPageGroupDescriptorArrayLock.SchedulerAssistYieldCounter;
  *(_QWORD *)&ExSaPageGroupDescriptorArrayLock.SchedulerAssistYieldCounter = &ExSaPageGroupDescriptorArrayLock.SchedulerAssistYieldCounter;
  LODWORD(ExSaPageGroupDescriptorArrayLock.Spare32) = 0;
  qword_140EE4C70 = (__int64)&qword_140EE4C68;
  qword_140EE4C68 = (__int64)&qword_140EE4C68;
  qword_140EE4C90 = (__int64)&qword_140EE4C88;
  qword_140EE4C88 = (__int64)&qword_140EE4C88;
  ExSaPageGroupDescriptorArrayLock.KcsanThread = 0;
  ExSaPageGroupDescriptorArrayLock.Padding[0] = 0;
  LOWORD(ExSaPageGroupDescriptorArrayLock.Padding[4]) = 1;
  BYTE2(ExSaPageGroupDescriptorArrayLock.Padding[4]) = 6;
  HIDWORD(ExSaPageGroupDescriptorArrayLock.Padding[4]) = 0;
  LOWORD(word_140EE4C80.Header.Lock) = 1;
  byte_140EE4C82 = 6;
  dword_140EE4C84 = 1;
  if ( !(unsigned __int8)PoInitSystem(1, BugCheckParameter3) )
    goto LABEL_225;
  RtlInitFunctionalityCache();
  if ( _InterlockedCompareExchange8(&ExKdpPool, 1, 0) )
    KeBugCheckEx(0xC2u, 0xA2u, 0, 0, 0);
  MiProtectKernelRoDataSectionsSlat(0);
  MmCompletePhase1Initialization();
  return v73;
}

```

## disassembly

```asm
0x140c4d7f4  push    rbp
0x140c4d7f6  push    rbx
0x140c4d7f7  push    rsi
0x140c4d7f8  push    rdi
0x140c4d7f9  push    r12
0x140c4d7fb  push    r13
0x140c4d7fd  push    r14
0x140c4d7ff  push    r15
0x140c4d801  lea     rbp, [rsp-98h]
0x140c4d809  sub     rsp, 198h
0x140c4d810  mov     rax, cs:__security_cookie
0x140c4d817  xor     rax, rsp
0x140c4d81a  mov     [rbp+0D0h+var_48], rax
0x140c4d821  xor     r13d, r13d
0x140c4d824  xorps   xmm0, xmm0
0x140c4d827  mov     r15, rcx
0x140c4d82a  mov     [rsp+1D0h+var_180], r13
0x140c4d82f  xor     eax, eax
0x140c4d831  mov     qword ptr [rsp+1D0h+var_160], r13
0x140c4d836  lea     rcx, [rbp+0D0h+var_100]; void *
0x140c4d83a  mov     [rbp+0D0h+var_148], r13
0x140c4d83e  xor     edx, edx; Val
0x140c4d840  mov     [rsp+1D0h+var_188], r13
0x140c4d845  mov     r8d, 94h; Size
0x140c4d84b  mov     [rbp+0D0h+var_140], r13
0x140c4d84f  movups  xmmword ptr [rbp+0D0h+var_128.Length], xmm0
0x140c4d853  mov     [rsp+1D0h+var_168], r13d
0x140c4d858  movups  [rbp+0D0h+var_138], xmm0
0x140c4d85c  mov     [rsp+1D0h+var_170], r13d
0x140c4d861  mov     [rsp+1D0h+var_16C], r13d
0x140c4d866  movups  xmmword ptr [rbp+0D0h+DestinationString.Length], xmm0
0x140c4d86a  mov     [rbp+0D0h+var_FC], eax
0x140c4d86d  call    memset_0
0x140c4d872  call    PsGetCurrentServerSiloGlobals
0x140c4d877  mov     edx, 200h
0x140c4d87c  lea     ecx, [r13+40h]
0x140c4d880  mov     r8d, 74696E49h
0x140c4d886  mov     rax, [rax+4D0h]
0x140c4d88d  mov     [rsp+1D0h+var_158], rax
0x140c4d892  call    ExAllocatePool2
0x140c4d897  mov     r12, rax
0x140c4d89a  test    rax, rax
0x140c4d89d  jnz     short loc_140C4D8A8
0x140c4d89f  lea     ecx, [rax+31h]; BugCheckCode
0x140c4d8a2  call    KeBugCheck
0x140c4d8a8  mov     ebx, 1
0x140c4d8ad  mov     cs:InitializationPhase, ebx
0x140c4d8b3  mov     rcx, gs:188h; Thread
0x140c4d8bc  lea     edx, [rbx+1Eh]; Priority
0x140c4d8bf  call    KeSetPriorityThread
0x140c4d8c4  mov     rcx, [r15+0D8h]; String
0x140c4d8cb  lea     rsi, cs:140000000h
0x140c4d8d2  test    rcx, rcx
0x140c4d8d5  jz      loc_140C4DAC6
0x140c4d8db  call    _strupr
0x140c4d8e0  mov     r14, rax
0x140c4d8e3  test    rax, rax
0x140c4d8e6  jz      loc_140C4DAD2
0x140c4d8ec  lea     rdx, aHypervisorroot; " HYPERVISORROOTPROC="
0x140c4d8f3  mov     rcx, rax; Str
0x140c4d8f6  call    strstr
0x140c4d8fb  test    rax, rax
0x140c4d8fe  jz      short loc_140C4D923
0x140c4d900  lea     rdx, asc_140CAA620; "="
0x140c4d907  mov     rcx, rax; Str
0x140c4d90a  call    strstr
0x140c4d90f  test    rax, rax
0x140c4d912  jz      short loc_140C4D923
0x140c4d914  lea     rcx, [rax+1]; Str
0x140c4d918  call    atol
0x140c4d91d  mov     cs:KeRootProcSpecified, eax
0x140c4d923  lea     rdx, aHypervisorroot_3; " HYPERVISORROOTPROCNUMANODES="
0x140c4d92a  mov     rcx, r14; Str
0x140c4d92d  call    strstr
0x140c4d932  mov     rdi, rax
0x140c4d935  test    rax, rax
0x140c4d938  jz      short loc_140C4D94C
0x140c4d93a  lea     rdx, asc_140CAA620; "="
0x140c4d941  mov     rcx, rax; Str
0x140c4d944  call    strstr
0x140c4d949  mov     rdi, rax
0x140c4d94c  test    rdi, rdi
0x140c4d94f  jz      short loc_140C4D98D
0x140c4d951  mov     eax, cs:KeRootProcNumaNodesSpecified
0x140c4d957  cmp     eax, 40h ; '@'
0x140c4d95a  jnb     short loc_140C4D98D
0x140c4d95c  add     rdi, rbx
0x140c4d95f  mov     ebx, eax
0x140c4d961  mov     rcx, rdi; Str
0x140c4d964  call    atol
0x140c4d969  mov     word ptr ds:rva KeRootProcNumaNodes[rsi+rbx*2], ax
0x140c4d971  mov     ebx, 1
0x140c4d976  add     cs:KeRootProcNumaNodesSpecified, ebx
0x140c4d97c  jmp     short loc_140C4D985
0x140c4d97e  test    al, 0DFh
0x140c4d980  jz      short loc_140C4D98D
0x140c4d982  add     rdi, rbx
0x140c4d985  mov     al, [rdi]
0x140c4d987  cmp     al, 2Ch ; ','
0x140c4d989  jnz     short loc_140C4D97E
0x140c4d98b  jmp     short loc_140C4D94C
0x140c4d98d  lea     rdx, aHypervisorroot_1; " HYPERVISORROOTPROCNUMANODELPS="
0x140c4d994  mov     rcx, r14; Str
0x140c4d997  call    strstr
0x140c4d99c  mov     rsi, rax
0x140c4d99f  test    rax, rax
0x140c4d9a2  jz      short loc_140C4D9CA
0x140c4d9a4  lea     rdx, asc_140CAA620; "="
0x140c4d9ab  mov     rcx, rax; Str
0x140c4d9ae  call    strstr
0x140c4d9b3  mov     rsi, rax
0x140c4d9b6  mov     cs:KeRootProcNumaNodeLpsSpecified, bl
0x140c4d9bc  mov     cs:KeRootProcNumaNodesSpecified, r13d
0x140c4d9c3  mov     cs:KeRootProcSpecified, r13d
0x140c4d9ca  test    rsi, rsi
0x140c4d9cd  jz      loc_140C4DACB
0x140c4d9d3  inc     rsi
0x140c4d9d6  mov     [rsp+1D0h+EndPtr], r13
0x140c4d9db  mov     rcx, rsi; Str
0x140c4d9de  lea     rdx, [rsp+1D0h+EndPtr]; EndPtr
0x140c4d9e3  mov     r8d, 0Ah; Radix
0x140c4d9e9  call    strtoul
0x140c4d9ee  mov     rcx, [rsp+1D0h+EndPtr]
0x140c4d9f3  mov     ebx, eax
0x140c4d9f5  cmp     rsi, rcx
0x140c4d9f8  jz      short loc_140C4DA1F
0x140c4d9fa  cmp     byte ptr [rcx], 5Fh ; '_'
0x140c4d9fd  jnz     short loc_140C4DA1F
0x140c4d9ff  lea     rsi, [rcx+1]
0x140c4da03  mov     r8d, 0Ah; Radix
0x140c4da09  mov     rcx, rsi; Str
0x140c4da0c  lea     rdx, [rsp+1D0h+EndPtr]; EndPtr
0x140c4da11  call    strtoul
0x140c4da16  mov     rcx, [rsp+1D0h+EndPtr]
0x140c4da1b  mov     edi, eax
0x140c4da1d  jmp     short loc_140C4DA22
0x140c4da1f  mov     edi, r13d
0x140c4da22  cmp     rsi, rcx
0x140c4da25  jz      short loc_140C4DAA2
0x140c4da27  cmp     byte ptr [rcx], 3Dh ; '='
0x140c4da2a  jnz     short loc_140C4DAA2
0x140c4da2c  cmp     ebx, 40h ; '@'
0x140c4da2f  jnb     short loc_140C4DAA2
0x140c4da31  add     rbx, rbx
0x140c4da34  lea     rsi, [rcx+1]
0x140c4da38  lea     rcx, cs:140000000h
0x140c4da3f  cmp     ds:rva qword_140FC06F8[rcx+rbx*8], r13
0x140c4da47  jnz     short loc_140C4DA7E
0x140c4da49  mov     edx, 100h
0x140c4da4e  mov     ecx, 40h ; '@'
0x140c4da53  mov     r8d, 800h
0x140c4da59  call    ExAllocatePool2
0x140c4da5e  test    rax, rax
0x140c4da61  jz      short loc_140C4DABB
0x140c4da63  lea     rcx, cs:140000000h
0x140c4da6a  mov     ds:rva KeRootProcNumaNodeLps[rcx+rbx*8], 800h
0x140c4da76  mov     ds:rva qword_140FC06F8[rcx+rbx*8], rax
0x140c4da7e  cmp     edi, 20h ; ' '
0x140c4da81  jnb     short loc_140C4DAA2
0x140c4da83  mov     rbx, ds:rva qword_140FC06F8[rcx+rbx*8]
0x140c4da8b  lea     rdx, [rsp+1D0h+EndPtr]; EndPtr
0x140c4da90  mov     rcx, rsi; String
0x140c4da93  mov     r8d, 10h; Radix
0x140c4da99  call    _strtoui64
0x140c4da9e  mov     [rbx+rdi*8], rax
0x140c4daa2  mov     ebx, 1
0x140c4daa7  jmp     short loc_140C4DAB0
0x140c4daa9  test    al, 0DFh
0x140c4daab  jz      short loc_140C4DACB
0x140c4daad  add     rsi, rbx
0x140c4dab0  mov     al, [rsi]
0x140c4dab2  cmp     al, 2Ch ; ','
0x140c4dab4  jnz     short loc_140C4DAA9
0x140c4dab6  jmp     loc_140C4D9CA
0x140c4dabb  mov     ecx, 31h ; '1'; BugCheckCode
0x140c4dac0  call    KeBugCheck
0x140c4dac6  mov     r14, r13
0x140c4dac9  jmp     short loc_140C4DAD2
0x140c4dacb  lea     rsi, cs:140000000h
0x140c4dad2  mov     rax, cs:KiSubNodeConfigBlock
0x140c4dad9  mov     rcx, r15
0x140c4dadc  mov     cs:word_140E4CB38, r13w
0x140c4dae4  and     byte ptr [rax+5], 0FCh
0x140c4dae8  mov     [rax+4], r13b
0x140c4daec  call    KiPerformGroupConfiguration
0x140c4daf1  mov     rcx, cs:KiSubNodeConfigBlock
0x140c4daf8  movzx   ecx, word ptr [rcx+6]
0x140c4dafc  call    KiCommitGroupSubNodeAssignments
0x140c4db01  mov     rax, cs:KiSubNodeConfigBlock
0x140c4db08  mov     rdx, r15
0x140c4db0b  mov     ecx, cs:InitializationPhase; BugCheckParameter3
0x140c4db11  or      [rax+10h], rbx
0x140c4db15  call    HalInitSystem
0x140c4db1a  test    al, al
0x140c4db1c  jz      loc_140C4EC37
0x140c4db22  mov     ecx, cs:InitializationPhase; BugCheckParameter2
0x140c4db28  mov     rdx, r15
0x140c4db2b  call    KeInitializeClock
0x140c4db30  mov     edi, 80000000h
0x140c4db35  test    r14, r14
0x140c4db38  jz      short loc_140C4DB4E
0x140c4db3a  lea     rdx, aNoguiboot; "NOGUIBOOT"
0x140c4db41  mov     rcx, r14; Str
0x140c4db44  call    strstr
0x140c4db49  test    rax, rax
0x140c4db4c  jnz     short loc_140C4DBC5
0x140c4db4e  cmp     cs:byte_140E4C061, r13b
0x140c4db55  mov     cs:byte_140E4BFF8, r13b
0x140c4db5c  jz      short loc_140C4DB9B
0x140c4db5e  cmp     cs:byte_140E4C062, r13b
0x140c4db65  jz      short loc_140C4DB78
0x140c4db67  mov     cl, bl
0x140c4db69  call    BgDisplayProgressIndicator
0x140c4db6e  test    eax, eax
0x140c4db70  js      short loc_140C4DB78
0x140c4db72  mov     cs:byte_140E4C060, bl
0x140c4db78  cmp     cs:byte_140E4C061, r13b
0x140c4db7f  jz      short loc_140C4DB9B
0x140c4db81  cmp     cs:byte_140E4C062, r13b
0x140c4db88  jz      short loc_140C4DB9B
0x140c4db8a  mov     cl, bl
0x140c4db8c  call    BgDisplayBackgroundUpdate
0x140c4db91  test    eax, eax
0x140c4db93  js      short loc_140C4DB9B
0x140c4db95  mov     cs:byte_140E4C030, bl
0x140c4db9b  lea     rax, DisplayFilter
0x140c4dba2  mov     r8d, 7
0x140c4dba8  mov     rdx, r15
0x140c4dbab  mov     cs:qword_140E4C008, rax
0x140c4dbb2  mov     ecx, ebx
0x140c4dbb4  call    InbvDriverInitialize
0x140c4dbb9  xor     ecx, ecx
0x140c4dbbb  call    DisplayBootBitmap
0x140c4dbc0  test    r14, r14
0x140c4dbc3  jz      short loc_140C4DC01
0x140c4dbc5  lea     rdx, aMinint_0; "MININT"
0x140c4dbcc  mov     rcx, r14; Str
0x140c4dbcf  call    strstr
0x140c4dbd4  test    rax, rax
0x140c4dbd7  jz      short loc_140C4DC01
0x140c4dbd9  lea     rdx, aInram; "INRAM"
0x140c4dbe0  mov     cs:InitIsWinPEMode, bl
0x140c4dbe6  mov     rcx, r14; Str
0x140c4dbe9  call    strstr
0x140c4dbee  test    rax, rax
0x140c4dbf1  jz      short loc_140C4DBFB
0x140c4dbf3  or      cs:InitWinPEModeType, edi
0x140c4dbf9  jmp     short loc_140C4DC01
0x140c4dbfb  or      cs:InitWinPEModeType, ebx
0x140c4dc01  xor     r8d, r8d
0x140c4dc04  lea     rax, [rsp+1D0h+var_188]
0x140c4dc09  mov     r9d, 4000007Eh
0x140c4dc0f  mov     qword ptr [rsp+1D0h+dwFlags], rax
0x140c4dc14  mov     rcx, rsi
0x140c4dc17  lea     edx, [r8+0Bh]
0x140c4dc1b  call    RtlFindMessage
0x140c4dc20  cmp     cs:CmCSDVersionString.Length, r13w
0x140c4dc28  mov     rbx, r12
0x140c4dc2b  mov     [rsp+1D0h+EndPtr], rbx
0x140c4dc30  mov     esi, eax
0x140c4dc32  mov     [rbp+0D0h+pcbRemaining], 100h
0x140c4dc3a  jz      short loc_140C4DC97
0x140c4dc3c  lea     rax, CmCSDVersionString
0x140c4dc43  mov     edx, 0FFh; cbDest
0x140c4dc48  mov     qword ptr [rsp+1D0h+Depth], rax
0x140c4dc4d  lea     r9, [rbp+0D0h+pcbRemaining]; pcbRemaining
0x140c4dc51  lea     rax, aWz_1; ": %wZ"
0x140c4dc58  mov     rcx, r12; pszDest
0x140c4dc5b  mov     [rsp+1D0h+pszFormat], rax; pszFormat
0x140c4dc60  lea     r8, [rsp+1D0h+EndPtr]; ppszDestEnd
0x140c4dc65  mov     qword ptr [rsp+1D0h+dwFlags], r13; dwFlags
0x140c4dc6a  call    RtlStringCbPrintfExA
0x140c4dc6f  test    eax, eax
0x140c4dc71  jns     short loc_140C4DC8C
0x140c4dc73  xor     r9d, r9d; BugCheckParameter3
0x140c4dc76  movsxd  rdx, eax; BugCheckParameter1
0x140c4dc79  mov     qword ptr [rsp+1D0h+dwFlags], r13; BugCheckParameter4
0x140c4dc7e  lea     ecx, [r9+32h]; BugCheckCode
0x140c4dc82  lea     r8d, [r9+7]; BugCheckParameter2
0x140c4dc86  call    KeBugCheckEx
0x140c4dc8c  mov     rbx, [rsp+1D0h+EndPtr]
0x140c4dc91  mov     rdi, [rbp+0D0h+pcbRemaining]
0x140c4dc95  jmp     short loc_140C4DC9C
0x140c4dc97  mov     edi, 0FFh
0x140c4dc9c  mov     r9d, 0Ah
0x140c4dca2  mov     [rbx], r13b
0x140c4dca5  lea     r8, aUU; "%u.%u"
0x140c4dcac  mov     qword ptr [rsp+1D0h+dwFlags], r13
0x140c4dcb1  lea     rcx, [rbp+0D0h+pszDest]; pszDest
0x140c4dcb5  inc     rbx
0x140c4dcb8  lea     edx, [r9+0Eh]; cbDest
0x140c4dcbc  call    RtlStringCbPrintfA
0x140c4dcc1  test    eax, eax
0x140c4dcc3  jns     short loc_140C4DCE0
0x140c4dcc5  mov     ecx, 32h ; '2'; BugCheckCode
0x140c4dcca  movsxd  rdx, eax; BugCheckParameter1
0x140c4dccd  mov     qword ptr [rsp+1D0h+dwFlags], r13; BugCheckParameter4
0x140c4dcd2  lea     r9d, [rcx-31h]; BugCheckParameter3
0x140c4dcd6  lea     r8d, [rcx-2Bh]; BugCheckParameter2
0x140c4dcda  call    KeBugCheckEx
  ... truncated ...
```
