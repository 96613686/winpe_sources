# Phase1InitializationIoReady

- ea: `0x140c4ec48`
- end: `0x140c4ef7a`
- name: `Phase1InitializationIoReady`
- size: `818`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting`

## callers

- `0x140741f40`

## callees

- `0x1402f44c0`
- `0x1403fdab0`
- `0x1404e48cc`
- `0x1404fdbf4`
- `0x140529c5c`
- `0x14053a510`
- `0x14053a530`
- `0x14057c464`
- `0x140633cf8`
- `0x14063a6c8`
- `0x14063b5d0`
- `0x140732ef0`
- `0x1407e3ddc`
- `0x140a14c88`
- `0x140ac955c`
- `0x140aed5c0`
- `0x140afff60`
- `0x140b00288`
- `0x140bc1800`
- `0x140c1e2e8`
- `0x140c1e4dc`
- `0x140c1eb88`
- `0x140c1ee48`
- `0x140c1f3c8`
- `0x140c1f518`
- `0x140c1fbe4`
- `0x140c1fd40`
- `0x140c4d030`
- `0x140c4ec48`
- `0x140c69430`
- `0x140c69b18`
- `0x140c6bb30`
- `0x140c6d334`
- `0x140c6f8c0`
- `0x140c70a9c`
- `0x140ca65b0`
- `0x140ca715c`
- `0x140ca8ed0`
- `0x140ca98c0`
- `0x140ca9c28`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!TmInitSystemPhase2` at `0x140c4ecf7`
- `ext-ms-win-ntos-tm-l1-1-0!TmInitSystemPhase2` at `0x140c4ecf7`
- `ext-ms-win-ntos-stateseparation-l1-1-1!ExpInitializeStateSeparationPhase1` at `0x140c4ecba`
- `ext-ms-win-ntos-stateseparation-l1-1-1!ExpInitializeStateSeparationPhase1` at `0x140c4ecba`

## pseudocode

```c
struct _KTHREAD *__fastcall Phase1InitializationIoReady(__int64 a1, char a2)
{
  int Driver; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  int inited; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  struct _KTHREAD *result; // rax

  RtlpInitializeNonVolatileFlush();
  Driver = IoCreateDriver(ExpInternalDriverObjectName, ExpInternalDriverObjectEntry);
  if ( Driver < 0 )
    KeBugCheckEx(0x32u, Driver, 0xEu, 0, 0);
  if ( (Feature_LookasideDepthManager__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_LookasideDepthManager__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_LookasideDepthManager__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    v6 = ExLookasideMgrsStart();
    if ( v6 < 0 )
      KeBugCheckEx(0x32u, v6, 0xFu, 0, 0);
  }
  v7 = ExInitializeNls();
  if ( v7 < 0 )
    KeBugCheckEx(0x32u, v7, 7u, 0, 0);
  LOBYTE(v8) = HIDWORD(WheapPfaLock.KernelStack) != 0;
  v9 = ExpInitializeStateSeparationPhase1(v8);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -1073741637 )
    KeBugCheckEx(0x32u, 0, 0, 0, 0);
  CmInitSystem2();
  inited = EmInitSystem(1, a1);
  if ( inited < 0 )
    KeBugCheckEx(0x32u, inited, 8u, 1u, 0);
  TmInitSystemPhase2();
  InbvSetProgressBarSubset(0, 100);
  if ( (_DWORD)InitSafeBootMode )
  {
    LOBYTE(v11) = a2;
    InitSafeBoot(v11);
  }
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0A9B8, 0, 0);
  SmInitSystem(3);
  VmInitSystem(2);
  MmInitSystem(2, a1);
  CcInitializeCacheManager(2);
  ObInitSystem(2);
  SaveNodeDistanceInformation();
  if ( !(unsigned __int8)PoInitSystem(3, a1) )
    KeBugCheck(0xA0u);
  KeInitializeClock(2u);
  KiInitializeReservedCpuSets();
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0C900, 0, 0);
  if ( byte_140FCCF00 )
    KasanInitSystem(a1, 2);
  ExLogTimeZoneInformation();
  sub_140A14C88();
  if ( !(unsigned __int8)PsInitSystem(2, a1) )
    goto LABEL_30;
  MmInitSystemDll();
  if ( !(unsigned __int8)SeRmInitPhase1() )
    KeBugCheck(0x6Cu);
  BootApplicationPersistentDataProcess(3);
  if ( !(unsigned __int8)PsInitSystem(3, a1) )
LABEL_30:
    KeBugCheck(0x6Bu);
  TlgRegisterAggregateProvider(&dword_140E0A150);
  StartFirstUserProcess();
  LODWORD(InitializationPhase) = InitializationPhase + 1;
  ExNotifyWithProcessing(stru_140EE4C98.KernelStack, 0, 0, 0);
  if ( ViVerifierEnabled )
  {
    CarInitLogging();
    VfNotifyVerifierOfEvent(5);
  }
  if ( VfClearanceFlag )
    VfClearVerifierSettings();
  v12 = *(unsigned int *)(*(_QWORD *)(a1 + 240) + 132LL);
  if ( (v12 & 2) == 0 && !(_DWORD)InitSafeBootMode )
  {
    LOBYTE(v12) = ViVerifierEnabled == 0;
    CarReportUnusualShutdown(v12);
  }
  ExQueryBootEntropyInformation(0);
  if ( !(unsigned __int8)KeInitSystem(4) )
    KeBugCheckEx(0x32u, 0xFFFFFFFFC0000001uLL, 0, 2u, 0);
  ExInitializePrmContext();
  result = stru_140E3BBD8.WaitBlock[3].Thread;
  if ( stru_140E3BBD8.WaitBlock[3].Thread )
    return (struct _KTHREAD *)KeSetTimer2(&stru_140E3BBD8.WaitBlockFill11[32], -600000000, 0, 0);
  return result;
}

```

## disassembly

```asm
0x140c4ec48  mov     [rsp+arg_8], rbx
0x140c4ec4d  mov     [rsp+arg_10], rsi
0x140c4ec52  push    rdi
0x140c4ec53  sub     rsp, 30h
0x140c4ec57  mov     dil, dl
0x140c4ec5a  mov     rbx, rcx
0x140c4ec5d  call    RtlpInitializeNonVolatileFlush
0x140c4ec62  lea     rdx, ExpInternalDriverObjectEntry
0x140c4ec69  lea     rcx, ExpInternalDriverObjectName; "&("
0x140c4ec70  call    IoCreateDriver
0x140c4ec75  xor     esi, esi
0x140c4ec77  test    eax, eax
0x140c4ec79  js      loc_140C4EECC
0x140c4ec7f  mov     eax, cs:Feature_LookasideDepthManager__private_featureState
0x140c4ec85  test    al, 10h
0x140c4ec87  jz      short loc_140C4EC8E
0x140c4ec89  and     eax, 1
0x140c4ec8c  jmp     short loc_140C4EC93
0x140c4ec8e  call    Feature_LookasideDepthManager__private_IsEnabledDeviceUsageNoInline
0x140c4ec93  test    eax, eax
0x140c4ec95  jz      short loc_140C4ECA4
0x140c4ec97  call    ExLookasideMgrsStart
0x140c4ec9c  test    eax, eax
0x140c4ec9e  js      loc_140C4EEE5
0x140c4eca4  call    ExInitializeNls
0x140c4eca9  test    eax, eax
0x140c4ecab  js      loc_140C4EEFE
0x140c4ecb1  cmp     dword ptr cs:WheapPfaLock.KernelStack+4, esi
0x140c4ecb7  setnz   cl
0x140c4ecba  call    cs:__imp_ExpInitializeStateSeparationPhase1
0x140c4ecc1  nop     dword ptr [rax+rax+00h]
0x140c4ecc6  mov     edx, 80000000h
0x140c4eccb  lea     ecx, [rax+rdx]
0x140c4ecce  test    edx, ecx
0x140c4ecd0  jnz     short loc_140C4ECDD
0x140c4ecd2  cmp     eax, 0C00000BBh
0x140c4ecd7  jnz     loc_140C4EF17
0x140c4ecdd  call    CmInitSystem2
0x140c4ece2  mov     rdx, rbx
0x140c4ece5  mov     ecx, 1
0x140c4ecea  call    EmInitSystem
0x140c4ecef  test    eax, eax
0x140c4ecf1  js      loc_140C4EF2D
0x140c4ecf7  call    cs:__imp_TmInitSystemPhase2
0x140c4ecfe  nop     dword ptr [rax+rax+00h]
0x140c4ed03  mov     edx, 64h ; 'd'
0x140c4ed08  xor     ecx, ecx
0x140c4ed0a  call    InbvSetProgressBarSubset
0x140c4ed0f  cmp     cs:InitSafeBootMode, esi
0x140c4ed15  jz      short loc_140C4ED1F
0x140c4ed17  mov     cl, dil
0x140c4ed1a  call    InitSafeBoot
0x140c4ed1f  xor     r8d, r8d
0x140c4ed22  lea     rcx, dword_140E0A9B8
0x140c4ed29  xor     edx, edx
0x140c4ed2b  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c4ed30  mov     ecx, 3
0x140c4ed35  call    SmInitSystem
0x140c4ed3a  mov     edi, 2
0x140c4ed3f  mov     ecx, edi
0x140c4ed41  call    VmInitSystem
0x140c4ed46  mov     rdx, rbx
0x140c4ed49  mov     ecx, edi
0x140c4ed4b  call    MmInitSystem
0x140c4ed50  mov     ecx, edi
0x140c4ed52  call    CcInitializeCacheManager
0x140c4ed57  mov     ecx, edi
0x140c4ed59  call    ObInitSystem
0x140c4ed5e  call    SaveNodeDistanceInformation
0x140c4ed63  mov     rdx, rbx
0x140c4ed66  lea     ecx, [rdi+1]
0x140c4ed69  call    PoInitSystem
0x140c4ed6e  test    al, al
0x140c4ed70  jz      loc_140C4EF48
0x140c4ed76  mov     rdx, rbx
0x140c4ed79  mov     ecx, edi; BugCheckParameter2
0x140c4ed7b  call    KeInitializeClock
0x140c4ed80  call    KiInitializeReservedCpuSets
0x140c4ed85  xor     r8d, r8d
0x140c4ed88  lea     rcx, dword_140E0C900
0x140c4ed8f  xor     edx, edx
0x140c4ed91  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c4ed96  cmp     cs:byte_140FCCF00, sil
0x140c4ed9d  jz      short loc_140C4EDA9
0x140c4ed9f  mov     edx, edi
0x140c4eda1  mov     rcx, rbx
0x140c4eda4  call    KasanInitSystem
0x140c4eda9  call    ExLogTimeZoneInformation
0x140c4edae  call    sub_140A14C88
0x140c4edb3  mov     rdx, rbx
0x140c4edb6  mov     ecx, edi
0x140c4edb8  call    PsInitSystem
0x140c4edbd  test    al, al
0x140c4edbf  jz      loc_140C4EEC1
0x140c4edc5  call    MmInitSystemDll
0x140c4edca  call    SeRmInitPhase1
0x140c4edcf  test    al, al
0x140c4edd1  jz      loc_140C4EF53
0x140c4edd7  mov     ecx, 3
0x140c4eddc  call    BootApplicationPersistentDataProcess
0x140c4ede1  mov     rdx, rbx
0x140c4ede4  mov     ecx, 3
0x140c4ede9  call    PsInitSystem
0x140c4edee  test    al, al
0x140c4edf0  jz      loc_140C4EEC1
0x140c4edf6  lea     rcx, dword_140E0A150
0x140c4edfd  call    TlgRegisterAggregateProvider
0x140c4ee02  call    StartFirstUserProcess
0x140c4ee07  mov     rcx, cs:stru_140EE4C98.KernelStack
0x140c4ee0e  xor     r9d, r9d
0x140c4ee11  inc     cs:InitializationPhase
0x140c4ee17  xor     r8d, r8d
0x140c4ee1a  xor     edx, edx
0x140c4ee1c  call    ExNotifyWithProcessing
0x140c4ee21  cmp     cs:ViVerifierEnabled, esi
0x140c4ee27  jz      short loc_140C4EE38
0x140c4ee29  call    CarInitLogging
0x140c4ee2e  mov     ecx, 5
0x140c4ee33  call    VfNotifyVerifierOfEvent
0x140c4ee38  cmp     cs:VfClearanceFlag, esi
0x140c4ee3e  jz      short loc_140C4EE45
0x140c4ee40  call    VfClearVerifierSettings
0x140c4ee45  mov     rax, [rbx+0F0h]
0x140c4ee4c  mov     ecx, [rax+84h]
0x140c4ee52  test    dil, cl
0x140c4ee55  jnz     short loc_140C4EE6D
0x140c4ee57  cmp     cs:InitSafeBootMode, esi
0x140c4ee5d  jnz     short loc_140C4EE6D
0x140c4ee5f  cmp     cs:ViVerifierEnabled, esi
0x140c4ee65  setz    cl
0x140c4ee68  call    CarReportUnusualShutdown
0x140c4ee6d  xor     ecx, ecx
0x140c4ee6f  call    ExQueryBootEntropyInformation
0x140c4ee74  mov     ecx, 4
0x140c4ee79  call    KeInitSystem
0x140c4ee7e  test    al, al
0x140c4ee80  jz      loc_140C4EF5E
0x140c4ee86  call    ExInitializePrmContext
0x140c4ee8b  mov     rax, qword ptr cs:stru_140E3BBD8.___u33+0A8h
0x140c4ee92  test    rax, rax
0x140c4ee95  jz      short loc_140C4EEB0
0x140c4ee97  xor     r9d, r9d
0x140c4ee9a  lea     rcx, stru_140E3BBD8.___u33+20h
0x140c4eea1  xor     r8d, r8d
0x140c4eea4  mov     rdx, 0FFFFFFFFDC3CBA00h
0x140c4eeab  call    KeSetTimer2
0x140c4eeb0  mov     rbx, [rsp+38h+arg_8]
0x140c4eeb5  mov     rsi, [rsp+38h+arg_10]
0x140c4eeba  add     rsp, 30h
0x140c4eebe  pop     rdi
0x140c4eebf  retn
0x140c4eec1  mov     ecx, 6Bh ; 'k'; BugCheckCode
0x140c4eec6  call    KeBugCheck
0x140c4eecc  xor     r9d, r9d; BugCheckParameter3
0x140c4eecf  movsxd  rdx, eax; BugCheckParameter1
0x140c4eed2  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c4eed7  lea     ecx, [r9+32h]; BugCheckCode
0x140c4eedb  lea     r8d, [r9+0Eh]; BugCheckParameter2
0x140c4eedf  call    KeBugCheckEx
0x140c4eee5  xor     r9d, r9d; BugCheckParameter3
0x140c4eee8  movsxd  rdx, eax; BugCheckParameter1
0x140c4eeeb  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c4eef0  lea     ecx, [r9+32h]; BugCheckCode
0x140c4eef4  lea     r8d, [r9+0Fh]; BugCheckParameter2
0x140c4eef8  call    KeBugCheckEx
0x140c4eefe  xor     r9d, r9d; BugCheckParameter3
0x140c4ef01  movsxd  rdx, eax; BugCheckParameter1
0x140c4ef04  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c4ef09  lea     ecx, [r9+32h]; BugCheckCode
0x140c4ef0d  lea     r8d, [r9+7]; BugCheckParameter2
0x140c4ef11  call    KeBugCheckEx
0x140c4ef17  xor     edx, edx; BugCheckParameter1
0x140c4ef19  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c4ef1e  xor     r9d, r9d; BugCheckParameter3
0x140c4ef21  xor     r8d, r8d; BugCheckParameter2
0x140c4ef24  lea     ecx, [rdx+32h]; BugCheckCode
0x140c4ef27  call    KeBugCheckEx
0x140c4ef2d  mov     ecx, 32h ; '2'; BugCheckCode
0x140c4ef32  movsxd  rdx, eax; BugCheckParameter1
0x140c4ef35  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c4ef3a  lea     r9d, [rcx-31h]; BugCheckParameter3
0x140c4ef3e  lea     r8d, [rcx-2Ah]; BugCheckParameter2
0x140c4ef42  call    KeBugCheckEx
0x140c4ef48  mov     ecx, 0A0h; BugCheckCode
0x140c4ef4d  call    KeBugCheck
0x140c4ef53  mov     ecx, 6Ch ; 'l'; BugCheckCode
0x140c4ef58  call    KeBugCheck
0x140c4ef5e  xor     r8d, r8d; BugCheckParameter2
0x140c4ef61  mov     [rsp+38h+BugCheckParameter4], rsi; BugCheckParameter4
0x140c4ef66  mov     r9, rdi; BugCheckParameter3
0x140c4ef69  mov     rdx, 0FFFFFFFFC0000001h; BugCheckParameter1
0x140c4ef70  lea     ecx, [r8+32h]; BugCheckCode
0x140c4ef74  call    KeBugCheckEx
```
