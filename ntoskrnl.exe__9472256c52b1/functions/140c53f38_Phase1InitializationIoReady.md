# Phase1InitializationIoReady

- ea: `0x140c53f38`
- end: `0x140c5426a`
- name: `Phase1InitializationIoReady`
- size: `818`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140746700`

## callees

- `0x140352370`
- `0x1403cd190`
- `0x1404f3ce4`
- `0x14050aeb4`
- `0x140530d7c`
- `0x140541bd0`
- `0x140541bf0`
- `0x140583a54`
- `0x1406397e8`
- `0x1406401b8`
- `0x1406410c0`
- `0x1407376b0`
- `0x1407e6a9c`
- `0x140979f10`
- `0x140a1cea8`
- `0x140af3760`
- `0x140b06a00`
- `0x140b06d28`
- `0x140bc4800`
- `0x140c212e8`
- `0x140c214dc`
- `0x140c21b88`
- `0x140c21e4c`
- `0x140c223cc`
- `0x140c22518`
- `0x140c22be4`
- `0x140c22d40`
- `0x140c2464c`
- `0x140c52320`
- `0x140c53f38`
- `0x140c6e700`
- `0x140c6edc8`
- `0x140c70de0`
- `0x140c725e4`
- `0x140c74b70`
- `0x140ca9100`
- `0x140ca9cac`
- `0x140caba20`
- `0x140cac720`
- `0x140caca88`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!TmInitSystemPhase2` at `0x140c53fe7`
- `ext-ms-win-ntos-tm-l1-1-0!TmInitSystemPhase2` at `0x140c53fe7`
- `ext-ms-win-ntos-stateseparation-l1-1-1!ExpInitializeStateSeparationPhase1` at `0x140c53faa`
- `ext-ms-win-ntos-stateseparation-l1-1-1!ExpInitializeStateSeparationPhase1` at `0x140c53faa`

## pseudocode

```c
PVOID __fastcall Phase1InitializationIoReady(__int64 a1, char a2)
{
  int Driver; // eax
  __int64 v5; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  int inited; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  PVOID result; // rax
  ULONG_PTR BugCheckParameter4; // [rsp+20h] [rbp-18h]

  RtlpInitializeNonVolatileFlush();
  Driver = IoCreateDriver(ExpInternalDriverObjectName, (__int64)ExpInternalDriverObjectEntry);
  if ( Driver < 0 )
    KeBugCheckEx(0x32u, Driver, 0xEu, 0, 0);
  if ( (Feature_LookasideDepthManager__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_LookasideDepthManager__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_LookasideDepthManager__private_IsEnabledDeviceUsageNoInline(v5);
  if ( IsEnabledDeviceUsageNoInline )
  {
    v7 = ExLookasideMgrsStart();
    if ( v7 < 0 )
      KeBugCheckEx(0x32u, v7, 0xFu, 0, 0);
  }
  v8 = ExInitializeNls();
  if ( v8 < 0 )
    KeBugCheckEx(0x32u, v8, 7u, 0, 0);
  LOBYTE(v9) = CmStateSeparationEnabled != 0;
  v10 = ExpInitializeStateSeparationPhase1(v9);
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -1073741637 )
    KeBugCheckEx(0x32u, 0, 0, 0, 0);
  CmInitSystem2();
  inited = EmInitSystem(1, a1);
  if ( inited < 0 )
    KeBugCheckEx(0x32u, inited, 8u, 1u, 0);
  TmInitSystemPhase2();
  InbvSetProgressBarSubset(0, 100);
  if ( (_DWORD)InitSafeBootMode )
  {
    LOBYTE(v12) = a2;
    InitSafeBoot(v12);
  }
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0A9B8, 0, 0);
  SmInitSystem(3);
  VmInitSystem(2);
  MmInitSystem(2, a1);
  CcInitializeCacheManager(2);
  ObInitSystem(2);
  SaveNodeDistanceInformation();
  if ( !PoInitSystem(3, a1) )
    KeBugCheck(0xA0u);
  KeInitializeClock(2u);
  KiInitializeReservedCpuSets();
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0C908, 0, 0);
  if ( byte_140FCC730 )
    KasanInitSystem(a1, 2);
  ExLogTimeZoneInformation();
  sub_140A1CEA8();
  if ( !(unsigned __int8)PsInitSystem(2, a1) )
    goto LABEL_30;
  MmInitSystemDll();
  if ( !SeRmInitPhase1() )
    KeBugCheck(0x6Cu);
  BootApplicationPersistentDataProcess(3);
  if ( !(unsigned __int8)PsInitSystem(3, a1) )
LABEL_30:
    KeBugCheck(0x6Bu);
  TlgRegisterAggregateProvider(&dword_140E0A150);
  StartFirstUserProcess();
  LODWORD(InitializationPhase) = InitializationPhase + 1;
  ExNotifyWithProcessing(ExCbPhase1InitComplete, 0, 0, 0);
  if ( ViVerifierEnabled )
  {
    CarInitLogging();
    VfNotifyVerifierOfEvent(5);
  }
  if ( VfClearanceFlag )
    VfClearVerifierSettings();
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 240) + 132LL) & 2) == 0 && !(_DWORD)InitSafeBootMode )
    CarReportUnusualShutdown(ViVerifierEnabled == 0);
  ExQueryBootEntropyInformation(0, v13);
  if ( !KeInitSystem(4) )
    KeBugCheckEx(0x32u, 0xFFFFFFFFC0000001uLL, 0, 2u, 0);
  ExInitializePrmContext();
  result = qword_140E3BD70;
  if ( qword_140E3BD70 )
    return (PVOID)KeSetTimer2(byte_140E3BCE8, -600000000, 0, 0, BugCheckParameter4);
  return result;
}

```

## disassembly

```asm
0x140c53f38  mov     [rsp+arg_8], rbx
0x140c53f3d  mov     [rsp+arg_10], rsi
0x140c53f42  push    rdi
0x140c53f43  sub     rsp, 30h
0x140c53f47  mov     dil, dl
0x140c53f4a  mov     rbx, rcx
0x140c53f4d  call    RtlpInitializeNonVolatileFlush
0x140c53f52  lea     rdx, ExpInternalDriverObjectEntry
0x140c53f59  lea     rcx, ExpInternalDriverObjectName; "&("
0x140c53f60  call    IoCreateDriver
0x140c53f65  xor     esi, esi
0x140c53f67  test    eax, eax
0x140c53f69  js      loc_140C541BC
0x140c53f6f  mov     eax, cs:Feature_LookasideDepthManager__private_featureState
0x140c53f75  test    al, 10h
0x140c53f77  jz      short loc_140C53F7E
0x140c53f79  and     eax, 1
0x140c53f7c  jmp     short loc_140C53F83
0x140c53f7e  call    Feature_LookasideDepthManager__private_IsEnabledDeviceUsageNoInline
0x140c53f83  test    eax, eax
0x140c53f85  jz      short loc_140C53F94
0x140c53f87  call    ExLookasideMgrsStart
0x140c53f8c  test    eax, eax
0x140c53f8e  js      loc_140C541D5
0x140c53f94  call    ExInitializeNls
0x140c53f99  test    eax, eax
0x140c53f9b  js      loc_140C541EE
0x140c53fa1  cmp     cs:CmStateSeparationEnabled, esi
0x140c53fa7  setnz   cl
0x140c53faa  call    cs:__imp_ExpInitializeStateSeparationPhase1
0x140c53fb1  nop     dword ptr [rax+rax+00h]
0x140c53fb6  mov     edx, 80000000h
0x140c53fbb  lea     ecx, [rax+rdx]
0x140c53fbe  test    edx, ecx
0x140c53fc0  jnz     short loc_140C53FCD
0x140c53fc2  cmp     eax, 0C00000BBh
0x140c53fc7  jnz     loc_140C54207
0x140c53fcd  call    CmInitSystem2
0x140c53fd2  mov     rdx, rbx
0x140c53fd5  mov     ecx, 1
0x140c53fda  call    EmInitSystem
0x140c53fdf  test    eax, eax
0x140c53fe1  js      loc_140C5421D
0x140c53fe7  call    cs:__imp_TmInitSystemPhase2
0x140c53fee  nop     dword ptr [rax+rax+00h]
0x140c53ff3  mov     edx, 64h ; 'd'
0x140c53ff8  xor     ecx, ecx
0x140c53ffa  call    InbvSetProgressBarSubset
0x140c53fff  cmp     cs:InitSafeBootMode, esi
0x140c54005  jz      short loc_140C5400F
0x140c54007  mov     cl, dil
0x140c5400a  call    InitSafeBoot
0x140c5400f  xor     r8d, r8d
0x140c54012  lea     rcx, dword_140E0A9B8
0x140c54019  xor     edx, edx
0x140c5401b  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c54020  mov     ecx, 3
0x140c54025  call    SmInitSystem
0x140c5402a  mov     edi, 2
0x140c5402f  mov     ecx, edi
0x140c54031  call    VmInitSystem
0x140c54036  mov     rdx, rbx
0x140c54039  mov     ecx, edi
0x140c5403b  call    MmInitSystem
0x140c54040  mov     ecx, edi
0x140c54042  call    CcInitializeCacheManager
0x140c54047  mov     ecx, edi
0x140c54049  call    ObInitSystem
0x140c5404e  call    SaveNodeDistanceInformation
0x140c54053  mov     rdx, rbx
0x140c54056  lea     ecx, [rdi+1]
0x140c54059  call    PoInitSystem
0x140c5405e  test    al, al
0x140c54060  jz      loc_140C54238
0x140c54066  mov     rdx, rbx
0x140c54069  mov     ecx, edi; BugCheckParameter2
0x140c5406b  call    KeInitializeClock
0x140c54070  call    KiInitializeReservedCpuSets
0x140c54075  xor     r8d, r8d
0x140c54078  lea     rcx, dword_140E0C908
0x140c5407f  xor     edx, edx
0x140c54081  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c54086  cmp     cs:byte_140FCC730, sil
0x140c5408d  jz      short loc_140C54099
0x140c5408f  mov     edx, edi
0x140c54091  mov     rcx, rbx
0x140c54094  call    KasanInitSystem
0x140c54099  call    ExLogTimeZoneInformation
0x140c5409e  call    sub_140A1CEA8
0x140c540a3  mov     rdx, rbx
0x140c540a6  mov     ecx, edi
0x140c540a8  call    PsInitSystem
0x140c540ad  test    al, al
0x140c540af  jz      loc_140C541B1
0x140c540b5  call    MmInitSystemDll
0x140c540ba  call    SeRmInitPhase1
0x140c540bf  test    al, al
0x140c540c1  jz      loc_140C54243
0x140c540c7  mov     ecx, 3
0x140c540cc  call    BootApplicationPersistentDataProcess
0x140c540d1  mov     rdx, rbx
0x140c540d4  mov     ecx, 3
0x140c540d9  call    PsInitSystem
0x140c540de  test    al, al
0x140c540e0  jz      loc_140C541B1
0x140c540e6  lea     rcx, dword_140E0A150
0x140c540ed  call    TlgRegisterAggregateProvider
0x140c540f2  call    StartFirstUserProcess
0x140c540f7  mov     rcx, cs:ExCbPhase1InitComplete
0x140c540fe  xor     r9d, r9d
0x140c54101  inc     cs:InitializationPhase
0x140c54107  xor     r8d, r8d
0x140c5410a  xor     edx, edx
0x140c5410c  call    ExNotifyWithProcessing
0x140c54111  cmp     cs:ViVerifierEnabled, esi
0x140c54117  jz      short loc_140C54128
0x140c54119  call    CarInitLogging
0x140c5411e  mov     ecx, 5
0x140c54123  call    VfNotifyVerifierOfEvent
0x140c54128  cmp     cs:VfClearanceFlag, esi
0x140c5412e  jz      short loc_140C54135
0x140c54130  call    VfClearVerifierSettings
0x140c54135  mov     rax, [rbx+0F0h]
0x140c5413c  mov     ecx, [rax+84h]
0x140c54142  test    dil, cl
0x140c54145  jnz     short loc_140C5415D
0x140c54147  cmp     cs:InitSafeBootMode, esi
0x140c5414d  jnz     short loc_140C5415D
0x140c5414f  cmp     cs:ViVerifierEnabled, esi
0x140c54155  setz    cl
0x140c54158  call    CarReportUnusualShutdown
0x140c5415d  xor     ecx, ecx
0x140c5415f  call    ExQueryBootEntropyInformation
0x140c54164  mov     ecx, 4
0x140c54169  call    KeInitSystem
0x140c5416e  test    al, al
0x140c54170  jz      loc_140C5424E
0x140c54176  call    ExInitializePrmContext
0x140c5417b  mov     rax, cs:qword_140E3BD70
0x140c54182  test    rax, rax
0x140c54185  jz      short loc_140C541A0
0x140c54187  xor     r9d, r9d
0x140c5418a  lea     rcx, byte_140E3BCE8
0x140c54191  xor     r8d, r8d
0x140c54194  mov     rdx, 0FFFFFFFFDC3CBA00h
0x140c5419b  call    KeSetTimer2
0x140c541a0  mov     rbx, [rsp+38h+arg_8]
0x140c541a5  mov     rsi, [rsp+38h+arg_10]
0x140c541aa  add     rsp, 30h
0x140c541ae  pop     rdi
0x140c541af  retn
0x140c541b1  mov     ecx, 6Bh ; 'k'; BugCheckCode
0x140c541b6  call    KeBugCheck
0x140c541bc  xor     r9d, r9d; BugCheckParameter3
0x140c541bf  movsxd  rdx, eax; BugCheckParameter1
0x140c541c2  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c541c7  lea     ecx, [r9+32h]; BugCheckCode
0x140c541cb  lea     r8d, [r9+0Eh]; BugCheckParameter2
0x140c541cf  call    KeBugCheckEx
0x140c541d5  xor     r9d, r9d; BugCheckParameter3
0x140c541d8  movsxd  rdx, eax; BugCheckParameter1
0x140c541db  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c541e0  lea     ecx, [r9+32h]; BugCheckCode
0x140c541e4  lea     r8d, [r9+0Fh]; BugCheckParameter2
0x140c541e8  call    KeBugCheckEx
0x140c541ee  xor     r9d, r9d; BugCheckParameter3
0x140c541f1  movsxd  rdx, eax; BugCheckParameter1
0x140c541f4  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c541f9  lea     ecx, [r9+32h]; BugCheckCode
0x140c541fd  lea     r8d, [r9+7]; BugCheckParameter2
0x140c54201  call    KeBugCheckEx
0x140c54207  xor     edx, edx; BugCheckParameter1
0x140c54209  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c5420e  xor     r9d, r9d; BugCheckParameter3
0x140c54211  xor     r8d, r8d; BugCheckParameter2
0x140c54214  lea     ecx, [rdx+32h]; BugCheckCode
0x140c54217  call    KeBugCheckEx
0x140c5421d  mov     ecx, 32h ; '2'; BugCheckCode
0x140c54222  movsxd  rdx, eax; BugCheckParameter1
0x140c54225  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c5422a  lea     r9d, [rcx-31h]; BugCheckParameter3
0x140c5422e  lea     r8d, [rcx-2Ah]; BugCheckParameter2
0x140c54232  call    KeBugCheckEx
0x140c54238  mov     ecx, 0A0h; BugCheckCode
0x140c5423d  call    KeBugCheck
0x140c54243  mov     ecx, 6Ch ; 'l'; BugCheckCode
0x140c54248  call    KeBugCheck
0x140c5424e  xor     r8d, r8d; BugCheckParameter2
0x140c54251  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c54256  mov     r9, rdi; BugCheckParameter3
0x140c54259  mov     rdx, 0FFFFFFFFC0000001h; BugCheckParameter1
0x140c54260  lea     ecx, [r8+32h]; BugCheckCode
0x140c54264  call    KeBugCheckEx
```
