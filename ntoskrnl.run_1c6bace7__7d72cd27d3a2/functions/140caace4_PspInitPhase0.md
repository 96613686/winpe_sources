# PspInitPhase0

- ea: `0x140caace4`
- end: `0x140cab90a`
- name: `PspInitPhase0`
- size: `3110`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update`

## callers

- `0x140c223cc`

## callees

- `0x140403380`
- `0x140517920`
- `0x140546100`
- `0x14054a5f0`
- `0x1406f7380`
- `0x140737690`
- `0x1408d9170`
- `0x140948f20`
- `0x14094b0a0`
- `0x1409d4e50`
- `0x140a4d44c`
- `0x140a52d08`
- `0x140a5b630`
- `0x140adf570`
- `0x140afb1b0`
- `0x140bb1410`
- `0x140c7da48`
- `0x140c7dd64`
- `0x140c7e0a0`
- `0x140c7e1a8`
- `0x140c7e1fc`
- `0x140c7e32c`
- `0x140caace4`

## import_xrefs

- `ext-ms-win-ntos-win32k-l1-1-0!Win32kAsyncProcessFreezeThawSupportIsActive` at `0x140caafad`
- `ext-ms-win-ntos-win32k-l1-1-0!Win32kAsyncProcessFreezeThawSupportIsActive` at `0x140caafad`

## string_xrefs

- `0x140cab219`: `Thread`
- `0x140cab4e9`: `ThreadStateChange`

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
  __int64 v42; // [rsp+E0h] [rbp-20h]
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
  LODWORD(v42) = 3;
  v2 = 0;
  BYTE4(v42) = 1;
  v43 = 1;
  v44 = 1;
  v46 = 1;
  v48 = 1;
  v45 = 4;
  v47 = 5;
  v49[1] = _mm_load_si128((const __m128i *)&_xmm);
  PspMinimumWorkingSet = 50;
  PspMaximumWorkingSet = 345;
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
  DestinationString = (UNICODE_STRING)PspSystemMitigationOptions;
  PspSystemMitigationOptionsLength = 24;
  v42 = qword_140FBF280;
  if ( (int)PspValidateMitigationOptions(&DestinationString, v6) < 0 )
  {
    PspSystemMitigationOptions = 0;
    qword_140FBF280 = 0;
  }
  for ( i = 0; i != 8; ++i )
  {
    v8 = *((_DWORD *)v49 + i);
    *((_QWORD *)&PspSystemMitigationOptions + ((unsigned __int64)(unsigned int)(4 * v8) >> 6)) &= ~(3LL << (4 * (unsigned __int8)v8));
  }
  v9 = (unsigned int)PspSystemMitigationAuditOptionsLength;
  if ( (unsigned int)PspSystemMitigationAuditOptionsLength < 0x18 )
    memset_0(
      (char *)&PspSystemMitigationAuditOptions + (unsigned int)PspSystemMitigationAuditOptionsLength,
      0,
      24LL - (unsigned int)PspSystemMitigationAuditOptionsLength);
  DestinationString = (UNICODE_STRING)PspSystemMitigationAuditOptions;
  v42 = qword_140FBF410;
  if ( (int)PspValidateMitigationAuditOptions(&DestinationString) < 0 )
    memset_0(&PspSystemMitigationAuditOptions, 0, v9);
  for ( j = 0; j != 64; j = v11 + 1 )
    CmSiRWLockInitialize((PRTL_RUN_ONCE)&PspCreateThreadNotifyRoutine[j]);
  for ( k = 0; k != 64; k = v13 + 1 )
    CmSiRWLockInitialize((PRTL_RUN_ONCE)&PspCreateProcessNotifyRoutine[k]);
  for ( m = 0; m != 64; m = v15 + 1 )
    CmSiRWLockInitialize((PRTL_RUN_ONCE)&PspLoadImageNotifyRoutine[m]);
  PsChangeQuantumTable(0, (unsigned int)PsRawPrioritySeparation);
  PspActiveProcessLock = 0;
  qword_140EF4078 = (__int64)&PsActiveProcessHead;
  PsActiveProcessHead = (__int64)&PsActiveProcessHead;
  qword_140EF4088 = (__int64)&PsActiveSessionHead;
  PsActiveSessionHead = (__int64)&PsActiveSessionHead;
  Process = KeGetCurrentThread()->ApcState.Process;
  PsIdleProcess = Process;
  *(_QWORD *)&Process[1].Header.Lock = 0;
  Process[1].ProfileListHead.Blink = 0;
  Process->KernelTime = 0;
  PspSessionIdBitmap.SizeOfBitMap = 128;
  PspSessionIdBitmap.Buffer = (unsigned int *)&PspSessionIdBuffer;
  PspSessionIdBuffer = 0;
  PspSessionIdNodes = 0;
  if ( (unsigned __int8)Win32kAsyncProcessFreezeThawSupportIsActive() )
  {
    PsFreezeWorkGlobals = 0;
    qword_140EF4158 = (__int64)&qword_140EF4150;
    qword_140EF4150 = (__int64)&qword_140EF4150;
    stru_140EF4160.WorkerRoutine = (void (__fastcall *)(void *))PspPostFreezeOperationWorker;
    stru_140EF4160.Parameter = &PsFreezeWorkGlobals;
    stru_140EF4160.List.Blink = 0;
    qword_140EF4148 = 0;
    stru_140EF4160.List.Flink = 0;
  }
  PspQosChangeNotifyWorkGlobals = 0;
  stru_140EF4118.WorkerRoutine = (void (__fastcall *)(void *))PspProcessQosChangeNotificationWorker;
  stru_140EF4118.List.Blink = 0;
  qword_140EF4108 = 0;
  qword_140EF4110 = 0;
  stru_140EF4118.Parameter = 0;
  stru_140EF4118.List.Flink = 0;
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
    v36 = PspMemoryReserveObjectSizes[v20];
    if ( (int)ObCreateObjectType(&PspMemoryReserveObjectNames[2 * v20], &v27, 0, &PspMemoryReserveObjectTypes + v20) < 0 )
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
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &PspActivityReferenceObjectType) < 0 )
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
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &PspProcessStateChangeType) < 0 )
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
  if ( (int)ObCreateObjectType(&DestinationString, &v27, 0, &PspThreadStateChangeType) < 0 )
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
  qword_140FBF218 = 0;
  qword_140FBF210 = (__int64)&PspWorkingSetChangeHead;
  PspWorkingSetChangeHead = (__int64)&PspWorkingSetChangeHead;
  PspAffinityUpdateLock = 0;
  PspCidTable = ExCreateHandleTable(0, 0);
  if ( !PspCidTable )
    return 0;
  CmSiRWLockInitialize(&PsWin32CallBack);
  CmSiRWLockInitialize(&PsWin32NullCallBack);
  *(_BYTE *)(PspCidTable + 44) |= 1u;
  qword_140EF4050 = (__int64)PspReaper;
  qword_140EF40B0 = (__int64)PspProcessRundownWorker;
  PspProcessRundownCacheWorkItem.WorkerRoutine = (void (__fastcall *)(void *))PspProcessRundownWorkerSingle;
  PsReaperListHead = 0;
  qword_140EF4058 = 0;
  PsReaperWorkItem = 0;
  qword_140EF40B8 = 0;
  PspProcessRundownWorkItem = 0;
  PspProcessRundownCacheWorkItem.Parameter = 0;
  PspProcessRundownCacheWorkItem.List.Flink = 0;
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
  v25[1].LastRebalanceQpc = ExAllocatePool2(64, 16, 0x61506553u);
  if ( !PsInitialSystemProcess[1].LastRebalanceQpc )
    return 0;
  if ( PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, Phase1Initialization, StartContext) < 0 )
    return 0;
  ObCloseHandle(ThreadHandle, 0);
  if ( !(unsigned __int8)PspIumInitialize() )
    return 0;
  PsVmProcessorHostTransitionEvent = 0;
  return 1;
}

```

## disassembly

```asm
0x140caace4  mov     [rsp-8+arg_0], rbx
0x140caace9  push    rbp
0x140caacea  push    rsi
0x140caaceb  push    rdi
0x140caacec  push    r12
0x140caacee  push    r13
0x140caacf0  push    r14
0x140caacf2  push    r15
0x140caacf4  lea     rbp, [rsp-20h]
0x140caacf9  sub     rsp, 120h
0x140caad00  movdqa  xmm0, cs:__xmm@00000015000000140000001900000007
0x140caad08  lea     r12, cs:140000000h
0x140caad0f  movdqa  xmm1, cs:__xmm@0000001a000000180000001700000016
0x140caad17  xor     r14d, r14d
0x140caad1a  movdqu  [rbp+50h+var_50], xmm0
0x140caad1f  mov     [rbp+50h+ThreadHandle], r14
0x140caad23  xor     eax, eax
0x140caad25  xorps   xmm0, xmm0
0x140caad28  mov     dword ptr [rbp+50h+DestinationString.Length], r14d
0x140caad2c  lea     r15d, [r14+1]
0x140caad30  mov     dword ptr [rbp+50h+DestinationString.Buffer], 2
0x140caad37  lea     ebx, [r14+3]
0x140caad3b  mov     byte ptr [rbp+50h+DestinationString+4], r15b
0x140caad3f  mov     byte ptr [rbp+50h+DestinationString.Buffer+4], bl
0x140caad42  mov     rsi, rcx
0x140caad45  mov     dword ptr [rbp+50h+var_70], ebx
0x140caad48  mov     r9d, r14d
0x140caad4b  mov     byte ptr [rbp+50h+var_70+4], r15b
0x140caad4f  mov     [rbp+50h+var_68], r15d
0x140caad53  mov     [rbp+50h+var_64], r15b
0x140caad57  mov     [rbp+50h+var_5C], r15b
0x140caad5b  mov     [rbp+50h+var_54], r15b
0x140caad5f  mov     [rbp+50h+var_60], 4
0x140caad66  mov     [rbp+50h+var_58], 5
0x140caad6d  movdqu  [rbp+50h+var_40], xmm1
0x140caad72  mov     cs:PspMinimumWorkingSet, 32h ; '2'
0x140caad7d  mov     cs:PspMaximumWorkingSet, 159h
0x140caad88  movups  cs:PspHardenedMitigationOptionsMap, xmm0
0x140caad8f  mov     cs:qword_140FBF848, rax
0x140caad96  mov     eax, dword ptr [rbp+r9*8+50h+DestinationString.Length]
0x140caad9b  movzx   edx, byte ptr [rbp+r9*8+50h+DestinationString+4]
0x140caada1  add     r9, r15
0x140caada4  shl     eax, 2
0x140caada7  mov     ecx, eax
0x140caada9  mov     r8d, eax
0x140caadac  and     ecx, 3Fh
0x140caadaf  shr     r8, 6
0x140caadb3  shl     rdx, cl
0x140caadb6  mov     rax, rbx
0x140caadb9  shl     rax, cl
0x140caadbc  not     rax
0x140caadbf  and     rax, qword ptr ds:rva PspHardenedMitigationOptionsMap[r12+r8*8]
0x140caadc7  or      rdx, rax
0x140caadca  mov     qword ptr ds:rva PspHardenedMitigationOptionsMap[r12+r8*8], rdx
0x140caadd2  cmp     r9, 6
0x140caadd6  jnz     short loc_140CAAD96
0x140caadd8  mov     eax, cs:PspSystemMitigationOptionsLength
0x140caadde  lea     r13d, [r9+12h]
0x140caade2  cmp     eax, r13d
0x140caade5  jnb     short loc_140CAADFE
0x140caade7  lea     rcx, [rax+0FBF270h]
0x140caadee  mov     r8d, r13d
0x140caadf1  sub     r8, rax; Size
0x140caadf4  add     rcx, r12; void *
0x140caadf7  xor     edx, edx; Val
0x140caadf9  call    memset_0
0x140caadfe  movups  xmm0, cs:PspSystemMitigationOptions
0x140caae05  lea     rcx, [rbp+50h+DestinationString]
0x140caae09  mov     dl, r15b
0x140caae0c  movsd   xmm1, cs:qword_140FBF280
0x140caae14  movaps  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x140caae18  mov     cs:PspSystemMitigationOptionsLength, r13d
0x140caae1f  movsd   [rbp+50h+var_70], xmm1
0x140caae24  call    PspValidateMitigationOptions
0x140caae29  test    eax, eax
0x140caae2b  jns     short loc_140CAAE40
0x140caae2d  xorps   xmm0, xmm0
0x140caae30  xor     eax, eax
0x140caae32  movups  cs:PspSystemMitigationOptions, xmm0
0x140caae39  mov     cs:qword_140FBF280, rax
0x140caae40  mov     r8, r14
0x140caae43  mov     eax, dword ptr [rbp+r8*4+50h+var_50]
0x140caae48  add     r8, r15
0x140caae4b  shl     eax, 2
0x140caae4e  mov     edx, eax
0x140caae50  mov     ecx, eax
0x140caae52  mov     rax, rbx
0x140caae55  shr     rdx, 6
0x140caae59  shl     rax, cl
0x140caae5c  not     rax
0x140caae5f  and     qword ptr ds:rva PspSystemMitigationOptions[r12+rdx*8], rax
0x140caae67  cmp     r8, 8
0x140caae6b  jnz     short loc_140CAAE43
0x140caae6d  mov     ebx, cs:PspSystemMitigationAuditOptionsLength
0x140caae73  lea     rdi, PspSystemMitigationAuditOptions
0x140caae7a  cmp     ebx, r13d
0x140caae7d  jnb     short loc_140CAAE90
0x140caae7f  mov     r8, r13
0x140caae82  lea     rcx, [rbx+rdi]; void *
0x140caae86  sub     r8, rbx; Size
0x140caae89  xor     edx, edx; Val
0x140caae8b  call    memset_0
0x140caae90  movups  xmm0, cs:PspSystemMitigationAuditOptions
0x140caae97  lea     rcx, [rbp+50h+DestinationString]
0x140caae9b  movsd   xmm1, cs:qword_140FBF410
0x140caaea3  movaps  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x140caaea7  movsd   [rbp+50h+var_70], xmm1
0x140caaeac  call    PspValidateMitigationAuditOptions
0x140caaeb1  test    eax, eax
0x140caaeb3  jns     short loc_140CAAEC2
0x140caaeb5  mov     r8, rbx; Size
0x140caaeb8  xor     edx, edx; Val
0x140caaeba  mov     rcx, rdi; void *
0x140caaebd  call    memset_0
0x140caaec2  mov     rax, r14
0x140caaec5  lea     rcx, rva PspCreateThreadNotifyRoutine[r12]
0x140caaecd  lea     rcx, [rcx+rax*8]; RunOnce
0x140caaed1  call    CmSiRWLockInitialize
0x140caaed6  add     rax, r15
0x140caaed9  cmp     rax, 40h ; '@'
0x140caaedd  jnz     short loc_140CAAEC5
0x140caaedf  mov     rax, r14
0x140caaee2  lea     rcx, rva PspCreateProcessNotifyRoutine[r12]
0x140caaeea  lea     rcx, [rcx+rax*8]; RunOnce
0x140caaeee  call    CmSiRWLockInitialize
0x140caaef3  add     rax, r15
0x140caaef6  cmp     rax, 40h ; '@'
0x140caaefa  jnz     short loc_140CAAEE2
0x140caaefc  mov     rax, r14
0x140caaeff  lea     rcx, rva PspLoadImageNotifyRoutine[r12]
0x140caaf07  lea     rcx, [rcx+rax*8]; RunOnce
0x140caaf0b  call    CmSiRWLockInitialize
0x140caaf10  add     rax, r15
0x140caaf13  cmp     rax, 40h ; '@'
0x140caaf17  jnz     short loc_140CAAEFF
0x140caaf19  mov     edx, cs:PsRawPrioritySeparation
0x140caaf1f  xor     ecx, ecx
0x140caaf21  call    PsChangeQuantumTable
0x140caaf26  mov     cs:PspActiveProcessLock, r14
0x140caaf2d  lea     rax, PsActiveProcessHead
0x140caaf34  mov     cs:qword_140EF4078, rax
0x140caaf3b  xorps   xmm0, xmm0
0x140caaf3e  mov     cs:PsActiveProcessHead, rax
0x140caaf45  mov     edi, 80h
0x140caaf4a  lea     rax, PsActiveSessionHead
0x140caaf51  mov     cs:qword_140EF4088, rax
0x140caaf58  mov     cs:PsActiveSessionHead, rax
0x140caaf5f  mov     rax, gs:188h
0x140caaf68  mov     rcx, [rax+0B8h]
0x140caaf6f  lea     rax, PspSessionIdBuffer
0x140caaf76  mov     cs:PsIdleProcess, rcx
0x140caaf7d  mov     [rcx+1C8h], r14
0x140caaf84  mov     [rcx+1E8h], r14
0x140caaf8b  mov     [rcx+138h], r14
0x140caaf92  mov     cs:PspSessionIdBitmap.SizeOfBitMap, edi
0x140caaf98  mov     cs:PspSessionIdBitmap.Buffer, rax
0x140caaf9f  movups  cs:PspSessionIdBuffer, xmm0
0x140caafa6  mov     cs:PspSessionIdNodes, r14
0x140caafad  call    cs:__imp_Win32kAsyncProcessFreezeThawSupportIsActive
0x140caafb4  nop     dword ptr [rax+rax+00h]
0x140caafb9  test    al, al
0x140caafbb  jz      short loc_140CAB00A
0x140caafbd  lea     rax, qword_140EF4150
0x140caafc4  mov     cs:PsFreezeWorkGlobals, r14
0x140caafcb  mov     cs:qword_140EF4158, rax
0x140caafd2  mov     cs:qword_140EF4150, rax
0x140caafd9  lea     rax, PspPostFreezeOperationWorker
0x140caafe0  mov     cs:stru_140EF4160.WorkerRoutine, rax
0x140caafe7  lea     rax, PsFreezeWorkGlobals
0x140caafee  mov     cs:stru_140EF4160.Parameter, rax
0x140caaff5  mov     cs:stru_140EF4160.List.Blink, r14
0x140caaffc  mov     cs:qword_140EF4148, r14
0x140cab003  mov     cs:stru_140EF4160.List.Flink, r14
0x140cab00a  lea     rax, PspProcessQosChangeNotificationWorker
0x140cab011  mov     cs:PspQosChangeNotifyWorkGlobals, r14
0x140cab018  mov     r8, rdi; Size
0x140cab01b  mov     cs:stru_140EF4118.WorkerRoutine, rax
0x140cab022  xor     edx, edx; Val
0x140cab024  mov     cs:stru_140EF4118.List.Blink, r14
0x140cab02b  lea     rcx, [rsp+150h+var_100]; void *
0x140cab030  mov     cs:qword_140EF4108, r14
0x140cab037  mov     cs:qword_140EF4110, r14
0x140cab03e  mov     cs:stru_140EF4118.Parameter, r14
0x140cab045  mov     cs:stru_140EF4118.List.Flink, r14
0x140cab04c  call    memset_0
0x140cab051  lea     rcx, aSession_0; "Session"
0x140cab058  mov     [rsp+150h+var_100], di
0x140cab05d  mov     [rbp+50h+DestinationString.Buffer], rcx
0x140cab061  mov     [rsp+150h+var_DC], 200h
0x140cab069  mov     dword ptr [rbp+50h+DestinationString+4], r14d
0x140cab06d  call    wcslen
0x140cab072  movups  xmm0, cs:PspSessionMapping
0x140cab079  add     rax, rax
0x140cab07c  mov     [rsp+150h+var_D4], 28h ; '('
0x140cab084  cmp     rax, 0FFFEh
0x140cab08a  mov     [rsp+150h+var_E4], 0F0003h
0x140cab092  mov     ecx, 0FFFCh
0x140cab097  mov     [rsp+150h+var_FE], 0Ch
0x140cab09c  cmovnb  rax, rcx
0x140cab0a0  lea     r9, MmSessionObjectType
0x140cab0a7  mov     [rbp+50h+DestinationString.Length], ax
0x140cab0ab  lea     rdx, [rsp+150h+var_100]
0x140cab0b0  mov     ebx, 2
0x140cab0b5  lea     rcx, [rbp+50h+DestinationString]
0x140cab0b9  add     ax, bx
0x140cab0bc  xor     r8d, r8d
0x140cab0bf  mov     [rbp+50h+DestinationString.MaximumLength], ax
0x140cab0c3  lea     rax, PsSessionObjectDelete
0x140cab0ca  mov     [rbp+50h+var_B8], rax
0x140cab0ce  movdqu  [rsp+150h+var_F4], xmm0
0x140cab0d4  call    ObCreateObjectType
0x140cab0d9  test    eax, eax
0x140cab0db  js      loc_140CAB8EC
0x140cab0e1  lea     rdx, aJob; "Job"
0x140cab0e8  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140cab0ec  call    RtlInitUnicodeString
0x140cab0f1  movups  xmm0, cs:PspJobMapping
0x140cab0f8  and     [rsp+150h+var_FE], 7Bh
0x140cab0fd  lea     rax, PspJobDelete
0x140cab104  mov     [rbp+50h+var_B8], rax
0x140cab108  lea     r9, PsJobType
0x140cab10f  lea     rax, PspJobClose
0x140cab116  mov     [rsp+150h+var_FC], 800h
0x140cab11f  xor     r8d, r8d
0x140cab122  mov     [rbp+50h+var_C0], rax
0x140cab126  lea     rdx, [rsp+150h+var_100]
0x140cab12b  mov     [rsp+150h+var_D8], r14d
0x140cab130  lea     rcx, [rbp+50h+DestinationString]
0x140cab134  mov     [rsp+150h+var_D4], 958h
0x140cab13c  mov     [rsp+150h+var_E4], 1F003Fh
0x140cab144  movdqu  [rsp+150h+var_F4], xmm0
0x140cab14a  mov     [rbp+50h+var_88], r15d
0x140cab14e  call    ObCreateObjectType
0x140cab153  test    eax, eax
0x140cab155  js      loc_140CAB8EC
0x140cab15b  lea     rdx, aProcess_0; "Process"
0x140cab162  mov     dword ptr [rsp+150h+var_FC+4], 0B0h
0x140cab16a  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140cab16e  call    RtlInitUnicodeString
0x140cab173  movups  xmm0, cs:PspProcessMapping
0x140cab17a  or      [rsp+150h+var_FE], 0C2h
0x140cab17f  lea     rax, PspProcessDelete
0x140cab186  mov     [rbp+50h+var_B8], rax
0x140cab18a  lea     rax, PspProcessOpen
0x140cab191  mov     [rbp+50h+var_C8], rax
0x140cab195  lea     rax, PspProcessClose
0x140cab19c  mov     [rbp+50h+var_C0], rax
0x140cab1a0  mov     dword ptr [rsp+150h+var_FC], 20h ; ' '
0x140cab1a8  mov     [rsp+150h+var_D8], 1000h
0x140cab1b0  mov     [rsp+150h+var_D4], 840h
0x140cab1b8  mov     [rsp+150h+var_E4], 1FFFFFh
0x140cab1c0  mov     [rsp+150h+var_E0], 101000h
0x140cab1c8  movdqu  [rsp+150h+var_F4], xmm0
0x140cab1ce  mov     [rbp+50h+var_88], 3
0x140cab1d5  mov     eax, cs:Feature_RcuFreeObject__private_featureState
0x140cab1db  test    bl, al
0x140cab1dd  jz      short loc_140CAB1E4
0x140cab1df  and     eax, r15d
0x140cab1e2  jmp     short loc_140CAB1E9
0x140cab1e4  call    Feature_RcuFreeObject__private_IsEnabledNoReportingNoInline
0x140cab1e9  test    eax, eax
0x140cab1eb  jnz     short loc_140CAB1F4
0x140cab1ed  and     [rsp+150h+var_FD], 0F7h
0x140cab1f2  jmp     short loc_140CAB1F9
0x140cab1f4  or      [rsp+150h+var_FD], 8
0x140cab1f9  lea     r9, PsProcessType
0x140cab200  xor     r8d, r8d
0x140cab203  lea     rdx, [rsp+150h+var_100]
0x140cab208  lea     rcx, [rbp+50h+DestinationString]
0x140cab20c  call    ObCreateObjectType
0x140cab211  test    eax, eax
0x140cab213  js      loc_140CAB8EC
0x140cab219  lea     rdx, aThread_0; "Thread"
0x140cab220  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140cab224  call    RtlInitUnicodeString
0x140cab229  movups  xmm0, cs:PspThreadMapping
0x140cab230  or      [rsp+150h+var_FE], dil
0x140cab235  lea     rax, PspThreadDelete
0x140cab23c  mov     [rbp+50h+var_B8], rax
0x140cab240  lea     rax, PspThreadOpen
0x140cab247  mov     [rbp+50h+var_C8], rax
0x140cab24b  mov     dword ptr [rsp+150h+var_FC], 4
0x140cab253  mov     [rsp+150h+var_D8], r14d
0x140cab258  mov     [rsp+150h+var_D4], 7A0h
0x140cab260  mov     [rbp+50h+var_C0], r14
0x140cab264  mov     [rsp+150h+var_E4], 1FFFFFh
0x140cab26c  mov     [rsp+150h+var_E0], 101800h
0x140cab274  movdqu  [rsp+150h+var_F4], xmm0
0x140cab27a  mov     [rbp+50h+var_88], 3
0x140cab281  mov     eax, cs:Feature_RcuFreeObject__private_featureState
0x140cab287  test    bl, al
0x140cab289  jz      short loc_140CAB290
0x140cab28b  and     eax, r15d
0x140cab28e  jmp     short loc_140CAB295
0x140cab290  call    Feature_RcuFreeObject__private_IsEnabledNoReportingNoInline
0x140cab295  test    eax, eax
0x140cab297  jnz     short loc_140CAB2A0
0x140cab299  and     [rsp+150h+var_FD], 0F7h
0x140cab29e  jmp     short loc_140CAB2A5
0x140cab2a0  or      [rsp+150h+var_FD], 8
  ... truncated ...
```
