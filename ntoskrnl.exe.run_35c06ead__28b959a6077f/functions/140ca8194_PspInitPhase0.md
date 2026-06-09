# PspInitPhase0

- ea: `0x140ca8194`
- end: `0x140ca8dba`
- name: `PspInitPhase0`
- size: `3110`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update`

## callers

- `0x140c1f3c8`

## callees

- `0x1403f2d50`
- `0x140511740`
- `0x14053ea40`
- `0x140542f30`
- `0x1406f4880`
- `0x140732ed0`
- `0x1408a4070`
- `0x1408ecdf0`
- `0x1408eef70`
- `0x14096c4a0`
- `0x1409d5f84`
- `0x140a43a7c`
- `0x140a541c0`
- `0x140ad98f0`
- `0x140af4730`
- `0x140bae410`
- `0x140c7abe4`
- `0x140c7af00`
- `0x140c7b23c`
- `0x140c7b344`
- `0x140c7b398`
- `0x140c7b4c8`
- `0x140ca8194`

## import_xrefs

- `ext-ms-win-ntos-win32k-l1-1-0!Win32kAsyncProcessFreezeThawSupportIsActive` at `0x140ca845d`
- `ext-ms-win-ntos-win32k-l1-1-0!Win32kAsyncProcessFreezeThawSupportIsActive` at `0x140ca845d`

## string_xrefs

- `0x140ca8999`: `ThreadStateChange`
- `0x140ca86c9`: `Thread`

## pseudocode

```c
char __fastcall PspInitPhase0(PVOID StartContext)
{
  __int64 v2; // r9
  unsigned int v3; // eax
  __int64 v4; // rdx
  unsigned __int64 v5; // r8
  __int64 v6; // rdx
  __int64 i; // r8
  int v8; // eax
  size_t v9; // rbx
  __int64 j; // rax
  __int64 v11; // rax
  __int64 k; // rax
  __int64 v13; // rax
  __int64 m; // rax
  __int64 v15; // rax
  _KPROCESS *Process; // rcx
  size_t v17; // rax
  int v18; // eax
  int v19; // eax
  int v20; // ebx
  _QWORD *v21; // rbx
  void *v22; // rcx
  NTSTATUS v23; // eax
  PVOID v24; // rcx
  PEPROCESS v25; // rbx
  __int16 v27; // [rsp+50h] [rbp-B0h] BYREF
  char v28; // [rsp+52h] [rbp-AEh]
  char v29; // [rsp+53h] [rbp-ADh]
  __int64 v30; // [rsp+54h] [rbp-ACh]
  __int128 v31; // [rsp+5Ch] [rbp-A4h]
  int v32; // [rsp+6Ch] [rbp-94h]
  int v33; // [rsp+70h] [rbp-90h]
  int v34; // [rsp+74h] [rbp-8Ch]
  int v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+7Ch] [rbp-84h]
  __int64 (__fastcall *v37)(); // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v38)(); // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v39)(); // [rsp+98h] [rbp-68h]
  int v40; // [rsp+C8h] [rbp-38h]
  UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  void *SchedulingGroup; // [rsp+E0h] [rbp-20h]
  int v43; // [rsp+E8h] [rbp-18h]
  char v44; // [rsp+ECh] [rbp-14h]
  int v45; // [rsp+F0h] [rbp-10h]
  char v46; // [rsp+F4h] [rbp-Ch]
  int v47; // [rsp+F8h] [rbp-8h]
  char v48; // [rsp+FCh] [rbp-4h]
  _OWORD v49[5]; // [rsp+100h] [rbp+0h]
  PVOID Object; // [rsp+168h] [rbp+68h] BYREF
  HANDLE ThreadHandle; // [rsp+170h] [rbp+70h] BYREF

  v49[0] = _mm_load_si128((const __m128i *)&_xmm);
  ThreadHandle = 0;
  *(_DWORD *)&DestinationString.Length = 0;
  LODWORD(DestinationString.Buffer) = 2;
  *((_BYTE *)&DestinationString.MaximumLength + 2) = 1;
  BYTE4(DestinationString.Buffer) = 3;
  LODWORD(SchedulingGroup) = 3;
  v2 = 0;
  BYTE4(SchedulingGroup) = 1;
  v43 = 1;
  v44 = 1;
  v46 = 1;
  v48 = 1;
  v45 = 4;
  v47 = 5;
  v49[1] = _mm_load_si128((const __m128i *)&_xmm);
  *(_QWORD *)&PspActiveProcessLock.WaitBlockFill11[16] = 50;
  *(_QWORD *)&PspActiveProcessLock.WaitBlockFill11[160] = 345;
  PspHardenedMitigationOptionsMap = 0;
  qword_140FBF848 = 0;
  do
  {
    v3 = *((_DWORD *)&DestinationString.Length + 2 * v2);
    v4 = *((unsigned __int8 *)&DestinationString.MaximumLength + 8 * v2++ + 2);
    v3 *= 4;
    v5 = (unsigned __int64)v3 >> 6;
    v6 = *((_QWORD *)&PspHardenedMitigationOptionsMap + v5) & ~(3LL << (v3 & 0x3F)) | (v4 << (v3 & 0x3F));
    *((_QWORD *)&PspHardenedMitigationOptionsMap + v5) = v6;
  }
  while ( v2 != 6 );
  if ( (unsigned int)PspSystemMitigationOptionsLength < 0x18 )
    memset_0(
      (void *)(0x140000000LL + (unsigned int)PspSystemMitigationOptionsLength + 16511600LL),
      0,
      24LL - (unsigned int)PspSystemMitigationOptionsLength);
  LOBYTE(v6) = 1;
  DestinationString = *(UNICODE_STRING *)&stru_140FBF218.KernelStack;
  PspSystemMitigationOptionsLength = 24;
  SchedulingGroup = stru_140FBF218.SchedulingGroup;
  if ( (int)PspValidateMitigationOptions(&DestinationString, v6) < 0 )
  {
    *(_OWORD *)&stru_140FBF218.KernelStack = 0;
    stru_140FBF218.SchedulingGroup = 0;
  }
  for ( i = 0; i != 8; ++i )
  {
    v8 = *((_DWORD *)v49 + i);
    *((_QWORD *)&stru_140FBF218.KernelStack + ((unsigned __int64)(unsigned int)(4 * v8) >> 6)) &= ~(3LL << (4 * (unsigned __int8)v8));
  }
  v9 = (unsigned int)PspSystemMitigationAuditOptionsLength;
  if ( (unsigned int)PspSystemMitigationAuditOptionsLength < 0x18 )
    memset_0(
      &stru_140FBF218.WaitBlockFill11[(unsigned int)PspSystemMitigationAuditOptionsLength + 168],
      0,
      24LL - (unsigned int)PspSystemMitigationAuditOptionsLength);
  DestinationString = *(UNICODE_STRING *)&stru_140FBF218.WaitBlockFill11[168];
  SchedulingGroup = stru_140FBF218.WaitBlock[3].SparePtr;
  if ( (int)PspValidateMitigationAuditOptions(&DestinationString) < 0 )
    memset_0(&stru_140FBF218.WaitBlockFill11[168], 0, v9);
  for ( j = 0; j != 64; j = v11 + 1 )
    CmSiRWLockInitialize((PRTL_RUN_ONCE)&NormalizationListLock.TracingPrivate[j + 1]);
  for ( k = 0; k != 64; k = v13 + 1 )
    CmSiRWLockInitialize((PRTL_RUN_ONCE)&PspCreateProcessNotifyRoutine[k]);
  for ( m = 0; m != 64; m = v15 + 1 )
    CmSiRWLockInitialize(&stru_140EF3C80[m]);
  PsChangeQuantumTable(0, (unsigned int)PsRawPrioritySeparation);
  *(_QWORD *)&PspActiveProcessLock.Header.Lock = 0;
  PsAltSystemCallRegistrationLock.WaitBlock[1].SparePtr = &PsAltSystemCallRegistrationLock.WaitBlockFill11[80];
  PsAltSystemCallRegistrationLock.WaitBlock[1].Object = &PsAltSystemCallRegistrationLock.WaitBlockFill11[80];
  *(_QWORD *)&PsAltSystemCallRegistrationLock.AffinityPrimaryGroup = &PsAltSystemCallRegistrationLock.Affinity;
  PsAltSystemCallRegistrationLock.Affinity = (_KAFFINITY_EX *)&PsAltSystemCallRegistrationLock.Affinity;
  Process = KeGetCurrentThread()->ApcState.Process;
  PsIdleProcess = Process;
  *(_QWORD *)&Process[1].Header.Lock = 0;
  Process[1].ProfileListHead.Blink = 0;
  Process->KernelTime = 0;
  *(_DWORD *)&NormalizationListLock.WaitBlockFill11[88] = 128;
  NormalizationListLock.WaitBlock[2].WaitListEntry.Flink = (struct _LIST_ENTRY *)&NormalizationListLock.WaitBlockFill11[56];
  *(_OWORD *)&NormalizationListLock.WaitBlockFill11[56] = 0;
  NormalizationListLock.WaitBlock[1].Thread = 0;
  if ( (unsigned __int8)Win32kAsyncProcessFreezeThawSupportIsActive() )
  {
    PsAltSystemCallRegistrationLock.SavedApcState.Process = (_KPROCESS *)&PsAltSystemCallRegistrationLock.SavedApcStateFill[24];
    PsAltSystemCallRegistrationLock.SavedApcState.ApcListHead[1].Blink = (struct _LIST_ENTRY *)&PsAltSystemCallRegistrationLock.SavedApcState.ApcListHead[1].Blink;
    PsAltSystemCallRegistrationLock.SchedulerApc.Thread = (struct _KTHREAD *)PspPostFreezeOperationWorker;
    PsAltSystemCallRegistrationLock.SchedulerApc.ApcListEntry.Flink = (struct _LIST_ENTRY *)&PsAltSystemCallRegistrationLock.SavedApcState.ApcListHead[0].Blink;
    *(_QWORD *)&PsAltSystemCallRegistrationLock.SchedulerApc.Type = 0;
    *(_OWORD *)&PsAltSystemCallRegistrationLock.SavedApcStateFill[8] = 0u;
    *(_QWORD *)&PsAltSystemCallRegistrationLock.SavedApcStateFill[40] = 0;
  }
  PsAltSystemCallRegistrationLock.SchedulerApc.SystemArgument1 = PspProcessQosChangeNotificationWorker;
  *(_OWORD *)&PsAltSystemCallRegistrationLock.SchedulerApcFill5[24] = 0u;
  *(_OWORD *)&PsAltSystemCallRegistrationLock.SchedulerApcFill5[32] = 0u;
  *(_OWORD *)&PsAltSystemCallRegistrationLock.SchedulerApcFill5[40] = 0u;
  PsAltSystemCallRegistrationLock.SchedulerApc.SystemArgument2 = 0;
  *(_OWORD *)&PsAltSystemCallRegistrationLock.SchedulerApcFill5[48] = 0u;
  memset_0(&v27, 0, 0x80u);
  v27 = 128;
  DestinationString.Buffer = (wchar_t *)L"Session";
  v34 = 512;
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  v17 = 2 * wcslen(L"Session");
  v36 = 40;
  v32 = 983043;
  v28 = 12;
  if ( v17 >= 0xFFFE )
    LOWORD(v17) = -4;
  DestinationString.Length = v17;
  DestinationString.MaximumLength = v17 + 2;
  v39 = PsSessionObjectDelete;
  v31 = PspSessionMapping;
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &MmSessionObjectType) < 0 )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"Job");
  v28 &= 0x7Bu;
  v39 = PspJobDelete;
  v30 = 2048;
  v38 = PspJobClose;
  v35 = 0;
  v36 = 2392;
  v32 = 2031679;
  v31 = PspJobMapping;
  v40 = 1;
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &PsJobType) < 0 )
    return 0;
  HIDWORD(v30) = 176;
  RtlInitUnicodeString(&DestinationString, L"Process");
  v28 |= 0xC2u;
  v39 = (__int64 (__fastcall *)())PspProcessDelete;
  v37 = (__int64 (__fastcall *)())PspProcessOpen;
  v38 = (__int64 (__fastcall *)())&PspProcessClose;
  LODWORD(v30) = 32;
  v35 = 4096;
  v36 = 2112;
  v32 = 0x1FFFFF;
  v33 = 1052672;
  v31 = PspProcessMapping;
  v40 = 3;
  v18 = (Feature_RcuFreeObject__private_featureState & 2) != 0
      ? Feature_RcuFreeObject__private_featureState & 1
      : Feature_RcuFreeObject__private_IsEnabledNoReportingNoInline();
  v29 = v18 ? v29 | 8 : v29 & 0xF7;
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &PsProcessType) < 0 )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"Thread");
  v28 |= 0x80u;
  v39 = (__int64 (__fastcall *)())PspThreadDelete;
  v37 = (__int64 (__fastcall *)())PspThreadOpen;
  LODWORD(v30) = 4;
  v35 = 0;
  v36 = 1952;
  v38 = 0;
  v32 = 0x1FFFFF;
  v33 = 1054720;
  v31 = PspThreadMapping;
  v40 = 3;
  v19 = (Feature_RcuFreeObject__private_featureState & 2) != 0
      ? Feature_RcuFreeObject__private_featureState & 1
      : Feature_RcuFreeObject__private_IsEnabledNoReportingNoInline();
  v29 = v19 ? v29 | 8 : v29 & 0xF7;
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &PsThreadType) < 0 )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"Partition");
  memset_0(&v27, 0, 0x80u);
  v27 = 128;
  v37 = PspOpenPartitionHandle;
  v28 = 12;
  v38 = PspClosePartitionHandle;
  HIDWORD(v30) = 16;
  v39 = (__int64 (__fastcall *)())PspDeletePartition;
  v32 = 2031619;
  v31 = PspPartitionMapping;
  v34 = 512;
  v36 = 144;
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &PsPartitionType) < 0 )
    return 0;
  memset_0(&v27, 0, 0x80u);
  v28 = 2;
  v20 = 0;
  v27 = 128;
  v31 = PspMemReserveMapping;
  HIDWORD(v30) = 176;
  v34 = 512;
  v32 = 983043;
  while ( v20 < 2 )
  {
    v36 = *((_DWORD *)&ExpPlatformBinaryLock.UserAffinityPrimaryGroup + 2 * v20);
    if ( (int)ObCreateObjectType(
                &PspMemoryReserveObjectNames[2 * v20],
                &v27,
                0,
                &stru_140FBF218.WaitBlockFill11[8 * v20 + 120]) < 0 )
      return 0;
    ++v20;
  }
  RtlInitUnicodeString(&DestinationString, L"ActivityReference");
  memset_0(&v27, 0, 0x80u);
  v27 = 128;
  v34 = 1;
  v35 = 8;
  HIDWORD(v30) = 402;
  v32 = 2031616;
  v31 = PspActivityReferenceMapping;
  v39 = PspDeleteActivityReference;
  v28 = 4;
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &stru_140FBF218.WaitBlockFill11[24]) < 0 )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"ProcessStateChange");
  memset_0(&v27, 0, 0x80u);
  v27 = 128;
  v28 = 6;
  HIDWORD(v30) = 146;
  v32 = 983041;
  v34 = 1;
  v35 = 24;
  v37 = 0;
  v31 = PspProcessStateChangeMapping;
  v38 = 0;
  v39 = PspDeleteProcessStateChange;
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &stru_140FBF218.SystemCallNumber) < 0 )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"ThreadStateChange");
  memset_0(&v27, 0, 0x80u);
  v27 = 128;
  v28 = 6;
  HIDWORD(v30) = 146;
  v32 = 983041;
  v34 = 1;
  v31 = PspThreadStateChangeMapping;
  v35 = 24;
  v37 = 0;
  v38 = 0;
  v39 = PspDeleteThreadStateChange;
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &stru_140FBF218.MiscFlags + 1) < 0 )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"CpuPartition");
  memset_0(&v27, 0, 0x80u);
  v27 = 128;
  v28 = 4;
  HIDWORD(v30) = 128;
  v32 = 983047;
  v34 = 512;
  v36 = 40;
  v31 = PspCpuPartitionMapping;
  v37 = 0;
  v38 = 0;
  v39 = PspDeleteCpuPartition;
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &PsCpuPartitionType) < 0 )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"SchedulerSharedData");
  memset_0(&v27, 0, 0x80u);
  v27 = 128;
  v28 = 6;
  HIDWORD(v30) = 146;
  v32 = 983041;
  v34 = 512;
  v31 = PspSchedulerSharedDataMapping;
  v35 = 248;
  v37 = 0;
  v38 = 0;
  v39 = PspSchedulerSharedDataRegionDelete;
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &PspSchedulerSharedDataType) < 0 )
    return 0;
  if ( !(unsigned __int8)PspInitializeJobStructures() )
    return 0;
  if ( !(unsigned __int8)PspInitializeSiloStructures() )
    return 0;
  *(_QWORD *)&stru_140FBF218.Header.Lock = 0;
  qword_140FBF210 = (__int64)&PspWorkingSetChangeHead;
  PspWorkingSetChangeHead = (__int64)&PspWorkingSetChangeHead;
  PspActiveProcessLock.Timer.Dpc = 0;
  PspCidTable = ExCreateHandleTable(0, 0);
  if ( !PspCidTable )
    return 0;
  CmSiRWLockInitialize((PRTL_RUN_ONCE)&NormalizationListLock.ThreadTimerDelay);
  CmSiRWLockInitialize((PRTL_RUN_ONCE)NormalizationListLock.TracingPrivate);
  *(_BYTE *)(PspCidTable + 44) |= 1u;
  PsAltSystemCallRegistrationLock.WaitBlock[3].WaitListEntry.Flink = (struct _LIST_ENTRY *)PspReaper;
  *(_QWORD *)&PsAltSystemCallRegistrationLock.UserAffinityPrimaryGroup = PspProcessRundownWorker;
  PsAltSystemCallRegistrationLock.Spare18 = (unsigned __int64)PspProcessRundownWorkerSingle;
  PsAltSystemCallRegistrationLock.WaitBlock[2].WaitListEntry.Flink = 0;
  PsAltSystemCallRegistrationLock.WaitBlock[2].Object = 0;
  PsAltSystemCallRegistrationLock.AffinityVersion = 0;
  PsAltSystemCallRegistrationLock.Process = 0;
  PsAltSystemCallRegistrationLock.LastXStateSaveDebugInfo = 0;
  *(_OWORD *)&PsAltSystemCallRegistrationLock.WaitBlockFill11[152] = 0u;
  if ( (int)PspTlsInitialize() < 0 )
    return 0;
  PspBootAccessToken = *((_QWORD *)PsIdleProcess + 73) & 0xFFFFFFFFFFFFFFF0uLL;
  if ( (int)PspInitializeSystemPartitionPhase0() < 0 )
    return 0;
  v21 = PspSystemPartition;
  if ( (int)PspInitializeCpuPartitionsPhase0() < 0 )
    return 0;
  if ( (int)PspCreateProcess(v21 + 16, 0x1FFFFF, 0, 0, 0, 0, 0, 0, 0) < 0 )
    return 0;
  v22 = (void *)v21[16];
  Object = 0;
  v23 = ObReferenceObjectByHandle(v22, 0, (POBJECT_TYPE)PsProcessType, 0, &Object, 0);
  v24 = Object;
  v21[15] = Object;
  if ( v23 < 0 )
    return 0;
  PsInitialSystemProcess = (PEPROCESS)v24;
  _InterlockedOr((volatile signed __int32 *)v24 + 468, 0x40000000u);
  _InterlockedOr((volatile signed __int32 *)&PsInitialSystemProcess[4].ThreadListHead.Flink + 1, 0x2000u);
  _InterlockedOr((volatile signed __int32 *)&PsInitialSystemProcess[3].ActiveGroupsMask.Masks[1] + 1, 0x1000u);
  strcpy_s((char *)PsIdleProcess + 824, 0xFu, "Idle");
  strcpy_s((char *)&PsInitialSystemProcess[1].SecureState, 0xFu, "System");
  v25 = PsInitialSystemProcess;
  v25[1].LastRebalanceQpc = ExAllocatePool2(64, 16, 1632658771);
  if ( !PsInitialSystemProcess[1].LastRebalanceQpc )
    return 0;
  if ( PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, Phase1Initialization, StartContext) < 0 )
    return 0;
  ObCloseHandle(ThreadHandle, 0);
  if ( !(unsigned __int8)PspIumInitialize() )
    return 0;
  PsAltSystemCallRegistrationLock.Timer.Header.WaitListHead.Blink = 0;
  return 1;
}

```

## disassembly

```asm
0x140ca8194  mov     [rsp-8+arg_0], rbx
0x140ca8199  push    rbp
0x140ca819a  push    rsi
0x140ca819b  push    rdi
0x140ca819c  push    r12
0x140ca819e  push    r13
0x140ca81a0  push    r14
0x140ca81a2  push    r15
0x140ca81a4  lea     rbp, [rsp-20h]
0x140ca81a9  sub     rsp, 120h
0x140ca81b0  movdqa  xmm0, cs:__xmm@00000015000000140000001900000007
0x140ca81b8  lea     r12, cs:140000000h
0x140ca81bf  movdqa  xmm1, cs:__xmm@0000001a000000180000001700000016
0x140ca81c7  xor     r14d, r14d
0x140ca81ca  movdqu  [rbp+50h+var_50], xmm0
0x140ca81cf  mov     [rbp+50h+ThreadHandle], r14
0x140ca81d3  xor     eax, eax
0x140ca81d5  xorps   xmm0, xmm0
0x140ca81d8  mov     dword ptr [rbp+50h+DestinationString.Length], r14d
0x140ca81dc  lea     r15d, [r14+1]
0x140ca81e0  mov     dword ptr [rbp+50h+DestinationString.Buffer], 2
0x140ca81e7  lea     ebx, [r14+3]
0x140ca81eb  mov     byte ptr [rbp+50h+DestinationString+4], r15b
0x140ca81ef  mov     byte ptr [rbp+50h+DestinationString.Buffer+4], bl
0x140ca81f2  mov     rsi, rcx
0x140ca81f5  mov     dword ptr [rbp+50h+var_70], ebx
0x140ca81f8  mov     r9d, r14d
0x140ca81fb  mov     byte ptr [rbp+50h+var_70+4], r15b
0x140ca81ff  mov     [rbp+50h+var_68], r15d
0x140ca8203  mov     [rbp+50h+var_64], r15b
0x140ca8207  mov     [rbp+50h+var_5C], r15b
0x140ca820b  mov     [rbp+50h+var_54], r15b
0x140ca820f  mov     [rbp+50h+var_60], 4
0x140ca8216  mov     [rbp+50h+var_58], 5
0x140ca821d  movdqu  [rbp+50h+var_40], xmm1
0x140ca8222  mov     qword ptr cs:PspActiveProcessLock.___u33+10h, 32h ; '2'
0x140ca822d  mov     qword ptr cs:PspActiveProcessLock.___u33+0A0h, 159h
0x140ca8238  movups  cs:PspHardenedMitigationOptionsMap, xmm0
0x140ca823f  mov     cs:qword_140FBF848, rax
0x140ca8246  mov     eax, dword ptr [rbp+r9*8+50h+DestinationString.Length]
0x140ca824b  movzx   edx, byte ptr [rbp+r9*8+50h+DestinationString+4]
0x140ca8251  add     r9, r15
0x140ca8254  shl     eax, 2
0x140ca8257  mov     ecx, eax
0x140ca8259  mov     r8d, eax
0x140ca825c  and     ecx, 3Fh
0x140ca825f  shr     r8, 6
0x140ca8263  shl     rdx, cl
0x140ca8266  mov     rax, rbx
0x140ca8269  shl     rax, cl
0x140ca826c  not     rax
0x140ca826f  and     rax, qword ptr ds:rva PspHardenedMitigationOptionsMap[r12+r8*8]
0x140ca8277  or      rdx, rax
0x140ca827a  mov     qword ptr ds:rva PspHardenedMitigationOptionsMap[r12+r8*8], rdx
0x140ca8282  cmp     r9, 6
0x140ca8286  jnz     short loc_140CA8246
0x140ca8288  mov     eax, cs:PspSystemMitigationOptionsLength
0x140ca828e  lea     r13d, [r9+12h]
0x140ca8292  cmp     eax, r13d
0x140ca8295  jnb     short loc_140CA82AE
0x140ca8297  lea     rcx, [rax+0FBF270h]
0x140ca829e  mov     r8d, r13d
0x140ca82a1  sub     r8, rax; Size
0x140ca82a4  add     rcx, r12; void *
0x140ca82a7  xor     edx, edx; Val
0x140ca82a9  call    memset_0
0x140ca82ae  movups  xmm0, xmmword ptr cs:stru_140FBF218.KernelStack
0x140ca82b5  lea     rcx, [rbp+50h+DestinationString]
0x140ca82b9  mov     dl, r15b
0x140ca82bc  movsd   xmm1, cs:stru_140FBF218.SchedulingGroup
0x140ca82c4  movaps  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x140ca82c8  mov     cs:PspSystemMitigationOptionsLength, r13d
0x140ca82cf  movsd   [rbp+50h+var_70], xmm1
0x140ca82d4  call    PspValidateMitigationOptions
0x140ca82d9  test    eax, eax
0x140ca82db  jns     short loc_140CA82F0
0x140ca82dd  xorps   xmm0, xmm0
0x140ca82e0  xor     eax, eax
0x140ca82e2  movups  xmmword ptr cs:stru_140FBF218.KernelStack, xmm0
0x140ca82e9  mov     cs:stru_140FBF218.SchedulingGroup, rax
0x140ca82f0  mov     r8, r14
0x140ca82f3  mov     eax, dword ptr [rbp+r8*4+50h+var_50]
0x140ca82f8  add     r8, r15
0x140ca82fb  shl     eax, 2
0x140ca82fe  mov     edx, eax
0x140ca8300  mov     ecx, eax
0x140ca8302  mov     rax, rbx
0x140ca8305  shr     rdx, 6
0x140ca8309  shl     rax, cl
0x140ca830c  not     rax
0x140ca830f  and     ds:rva stru_140FBF218.KernelStack[r12+rdx*8], rax
0x140ca8317  cmp     r8, 8
0x140ca831b  jnz     short loc_140CA82F3
0x140ca831d  mov     ebx, cs:PspSystemMitigationAuditOptionsLength
0x140ca8323  lea     rdi, stru_140FBF218.___u33+0A8h
0x140ca832a  cmp     ebx, r13d
0x140ca832d  jnb     short loc_140CA8340
0x140ca832f  mov     r8, r13
0x140ca8332  lea     rcx, [rbx+rdi]; void *
0x140ca8336  sub     r8, rbx; Size
0x140ca8339  xor     edx, edx; Val
0x140ca833b  call    memset_0
0x140ca8340  movups  xmm0, xmmword ptr cs:stru_140FBF218.___u33+0A8h
0x140ca8347  lea     rcx, [rbp+50h+DestinationString]
0x140ca834b  movsd   xmm1, qword ptr cs:stru_140FBF218.___u33+0B8h
0x140ca8353  movaps  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x140ca8357  movsd   [rbp+50h+var_70], xmm1
0x140ca835c  call    PspValidateMitigationAuditOptions
0x140ca8361  test    eax, eax
0x140ca8363  jns     short loc_140CA8372
0x140ca8365  mov     r8, rbx; Size
0x140ca8368  xor     edx, edx; Val
0x140ca836a  mov     rcx, rdi; void *
0x140ca836d  call    memset_0
0x140ca8372  mov     rax, r14
0x140ca8375  lea     rcx, rva NormalizationListLock.SchedulerAssist[r12]
0x140ca837d  lea     rcx, [rcx+rax*8]; RunOnce
0x140ca8381  call    CmSiRWLockInitialize
0x140ca8386  add     rax, r15
0x140ca8389  cmp     rax, 40h ; '@'
0x140ca838d  jnz     short loc_140CA8375
0x140ca838f  mov     rax, r14
0x140ca8392  lea     rcx, rva PspCreateProcessNotifyRoutine[r12]
0x140ca839a  lea     rcx, [rcx+rax*8]; RunOnce
0x140ca839e  call    CmSiRWLockInitialize
0x140ca83a3  add     rax, r15
0x140ca83a6  cmp     rax, 40h ; '@'
0x140ca83aa  jnz     short loc_140CA8392
0x140ca83ac  mov     rax, r14
0x140ca83af  lea     rcx, rva stru_140EF3C80[r12]
0x140ca83b7  lea     rcx, [rcx+rax*8]; RunOnce
0x140ca83bb  call    CmSiRWLockInitialize
0x140ca83c0  add     rax, r15
0x140ca83c3  cmp     rax, 40h ; '@'
0x140ca83c7  jnz     short loc_140CA83AF
0x140ca83c9  mov     edx, cs:PsRawPrioritySeparation
0x140ca83cf  xor     ecx, ecx
0x140ca83d1  call    PsChangeQuantumTable
0x140ca83d6  mov     qword ptr cs:PspActiveProcessLock.Header, r14
0x140ca83dd  lea     rax, PsAltSystemCallRegistrationLock.___u33+50h
0x140ca83e4  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u33+58h, rax
0x140ca83eb  xorps   xmm0, xmm0
0x140ca83ee  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u33+50h, rax
0x140ca83f5  mov     edi, 80h
0x140ca83fa  lea     rax, PsAltSystemCallRegistrationLock.Affinity
0x140ca8401  mov     qword ptr cs:PsAltSystemCallRegistrationLock.AffinityPrimaryGroup, rax
0x140ca8408  mov     cs:PsAltSystemCallRegistrationLock.Affinity, rax
0x140ca840f  mov     rax, gs:188h
0x140ca8418  mov     rcx, [rax+0B8h]
0x140ca841f  lea     rax, NormalizationListLock.___u33+38h
0x140ca8426  mov     cs:PsIdleProcess, rcx
0x140ca842d  mov     [rcx+1C8h], r14
0x140ca8434  mov     [rcx+1E8h], r14
0x140ca843b  mov     [rcx+138h], r14
0x140ca8442  mov     dword ptr cs:NormalizationListLock.___u33+58h, edi
0x140ca8448  mov     qword ptr cs:NormalizationListLock.___u33+60h, rax
0x140ca844f  movups  xmmword ptr cs:NormalizationListLock.___u33+38h, xmm0
0x140ca8456  mov     qword ptr cs:NormalizationListLock.___u33+48h, r14
0x140ca845d  call    cs:__imp_Win32kAsyncProcessFreezeThawSupportIsActive
0x140ca8464  nop     dword ptr [rax+rax+00h]
0x140ca8469  test    al, al
0x140ca846b  jz      short loc_140CA84BA
0x140ca846d  lea     rax, PsAltSystemCallRegistrationLock.___u57+18h
0x140ca8474  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u57+8, r14
0x140ca847b  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u57+20h, rax
0x140ca8482  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u57+18h, rax
0x140ca8489  lea     rax, PspPostFreezeOperationWorker
0x140ca8490  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u58+8, rax
0x140ca8497  lea     rax, PsAltSystemCallRegistrationLock.___u57+8
0x140ca849e  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u58+10h, rax
0x140ca84a5  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u58, r14
0x140ca84ac  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u57+10h, r14
0x140ca84b3  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u57+28h, r14
0x140ca84ba  lea     rax, PspProcessQosChangeNotificationWorker
0x140ca84c1  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u58+18h, r14
0x140ca84c8  mov     r8, rdi; Size
0x140ca84cb  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u58+40h, rax
0x140ca84d2  xor     edx, edx; Val
0x140ca84d4  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u58+38h, r14
0x140ca84db  lea     rcx, [rsp+150h+var_100]; void *
0x140ca84e0  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u58+20h, r14
0x140ca84e7  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u58+28h, r14
0x140ca84ee  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u58+48h, r14
0x140ca84f5  mov     qword ptr cs:PsAltSystemCallRegistrationLock.___u58+30h, r14
0x140ca84fc  call    memset_0
0x140ca8501  lea     rcx, aSession_0; "Session"
0x140ca8508  mov     [rsp+150h+var_100], di
0x140ca850d  mov     [rbp+50h+DestinationString.Buffer], rcx
0x140ca8511  mov     [rsp+150h+var_DC], 200h
0x140ca8519  mov     dword ptr [rbp+50h+DestinationString+4], r14d
0x140ca851d  call    wcslen
0x140ca8522  movups  xmm0, cs:PspSessionMapping
0x140ca8529  add     rax, rax
0x140ca852c  mov     [rsp+150h+var_D4], 28h ; '('
0x140ca8534  cmp     rax, 0FFFEh
0x140ca853a  mov     [rsp+150h+var_E4], 0F0003h
0x140ca8542  mov     ecx, 0FFFCh
0x140ca8547  mov     [rsp+150h+var_FE], 0Ch
0x140ca854c  cmovnb  rax, rcx
0x140ca8550  lea     r9, MmSessionObjectType
0x140ca8557  mov     [rbp+50h+DestinationString.Length], ax
0x140ca855b  lea     rdx, [rsp+150h+var_100]
0x140ca8560  mov     ebx, 2
0x140ca8565  lea     rcx, [rbp+50h+DestinationString]
0x140ca8569  add     ax, bx
0x140ca856c  xor     r8d, r8d
0x140ca856f  mov     [rbp+50h+DestinationString.MaximumLength], ax
0x140ca8573  lea     rax, PsSessionObjectDelete
0x140ca857a  mov     [rbp+50h+var_B8], rax
0x140ca857e  movdqu  [rsp+150h+var_F4], xmm0
0x140ca8584  call    ObCreateObjectType
0x140ca8589  test    eax, eax
0x140ca858b  js      loc_140CA8D9C
0x140ca8591  lea     rdx, aJob; "Job"
0x140ca8598  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140ca859c  call    RtlInitUnicodeString
0x140ca85a1  movups  xmm0, cs:PspJobMapping
0x140ca85a8  and     [rsp+150h+var_FE], 7Bh
0x140ca85ad  lea     rax, PspJobDelete
0x140ca85b4  mov     [rbp+50h+var_B8], rax
0x140ca85b8  lea     r9, PsJobType
0x140ca85bf  lea     rax, PspJobClose
0x140ca85c6  mov     [rsp+150h+var_FC], 800h
0x140ca85cf  xor     r8d, r8d
0x140ca85d2  mov     [rbp+50h+var_C0], rax
0x140ca85d6  lea     rdx, [rsp+150h+var_100]
0x140ca85db  mov     [rsp+150h+var_D8], r14d
0x140ca85e0  lea     rcx, [rbp+50h+DestinationString]
0x140ca85e4  mov     [rsp+150h+var_D4], 958h
0x140ca85ec  mov     [rsp+150h+var_E4], 1F003Fh
0x140ca85f4  movdqu  [rsp+150h+var_F4], xmm0
0x140ca85fa  mov     [rbp+50h+var_88], r15d
0x140ca85fe  call    ObCreateObjectType
0x140ca8603  test    eax, eax
0x140ca8605  js      loc_140CA8D9C
0x140ca860b  lea     rdx, aProcess_0; "Process"
0x140ca8612  mov     dword ptr [rsp+150h+var_FC+4], 0B0h
0x140ca861a  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140ca861e  call    RtlInitUnicodeString
0x140ca8623  movups  xmm0, cs:PspProcessMapping
0x140ca862a  or      [rsp+150h+var_FE], 0C2h
0x140ca862f  lea     rax, PspProcessDelete
0x140ca8636  mov     [rbp+50h+var_B8], rax
0x140ca863a  lea     rax, PspProcessOpen
0x140ca8641  mov     [rbp+50h+var_C8], rax
0x140ca8645  lea     rax, PspProcessClose
0x140ca864c  mov     [rbp+50h+var_C0], rax
0x140ca8650  mov     dword ptr [rsp+150h+var_FC], 20h ; ' '
0x140ca8658  mov     [rsp+150h+var_D8], 1000h
0x140ca8660  mov     [rsp+150h+var_D4], 840h
0x140ca8668  mov     [rsp+150h+var_E4], 1FFFFFh
0x140ca8670  mov     [rsp+150h+var_E0], 101000h
0x140ca8678  movdqu  [rsp+150h+var_F4], xmm0
0x140ca867e  mov     [rbp+50h+var_88], 3
0x140ca8685  mov     eax, cs:Feature_RcuFreeObject__private_featureState
0x140ca868b  test    bl, al
0x140ca868d  jz      short loc_140CA8694
0x140ca868f  and     eax, r15d
0x140ca8692  jmp     short loc_140CA8699
0x140ca8694  call    Feature_RcuFreeObject__private_IsEnabledNoReportingNoInline
0x140ca8699  test    eax, eax
0x140ca869b  jnz     short loc_140CA86A4
0x140ca869d  and     [rsp+150h+var_FD], 0F7h
0x140ca86a2  jmp     short loc_140CA86A9
0x140ca86a4  or      [rsp+150h+var_FD], 8
0x140ca86a9  lea     r9, PsProcessType
0x140ca86b0  xor     r8d, r8d
0x140ca86b3  lea     rdx, [rsp+150h+var_100]
0x140ca86b8  lea     rcx, [rbp+50h+DestinationString]
0x140ca86bc  call    ObCreateObjectType
0x140ca86c1  test    eax, eax
0x140ca86c3  js      loc_140CA8D9C
0x140ca86c9  lea     rdx, aThread_0; "Thread"
0x140ca86d0  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140ca86d4  call    RtlInitUnicodeString
0x140ca86d9  movups  xmm0, cs:PspThreadMapping
0x140ca86e0  or      [rsp+150h+var_FE], dil
0x140ca86e5  lea     rax, PspThreadDelete
0x140ca86ec  mov     [rbp+50h+var_B8], rax
0x140ca86f0  lea     rax, PspThreadOpen
0x140ca86f7  mov     [rbp+50h+var_C8], rax
0x140ca86fb  mov     dword ptr [rsp+150h+var_FC], 4
0x140ca8703  mov     [rsp+150h+var_D8], r14d
0x140ca8708  mov     [rsp+150h+var_D4], 7A0h
0x140ca8710  mov     [rbp+50h+var_C0], r14
0x140ca8714  mov     [rsp+150h+var_E4], 1FFFFFh
0x140ca871c  mov     [rsp+150h+var_E0], 101800h
0x140ca8724  movdqu  [rsp+150h+var_F4], xmm0
0x140ca872a  mov     [rbp+50h+var_88], 3
0x140ca8731  mov     eax, cs:Feature_RcuFreeObject__private_featureState
0x140ca8737  test    bl, al
0x140ca8739  jz      short loc_140CA8740
0x140ca873b  and     eax, r15d
0x140ca873e  jmp     short loc_140CA8745
0x140ca8740  call    Feature_RcuFreeObject__private_IsEnabledNoReportingNoInline
0x140ca8745  test    eax, eax
0x140ca8747  jnz     short loc_140CA8750
0x140ca8749  and     [rsp+150h+var_FD], 0F7h
0x140ca874e  jmp     short loc_140CA8755
0x140ca8750  or      [rsp+150h+var_FD], 8
  ... truncated ...
```
