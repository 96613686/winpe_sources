# PopDiagInitialize

- ea: `0x140c73dd8`
- end: `0x140c7406f`
- name: `PopDiagInitialize`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140c70a9c`

## callees

- `0x140307510`
- `0x1403fe220`
- `0x1404a3604`
- `0x1404e7c00`
- `0x140604084`
- `0x1406040c4`
- `0x140605fbc`
- `0x1406d9d70`
- `0x14078fe7c`
- `0x1407938d4`
- `0x1407d8db0`
- `0x140950b80`
- `0x140ac955c`
- `0x140c73dd8`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRegister` at `0x140c73f6c`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRegister` at `0x140c73f6c`

## pseudocode

```c
__int64 PopDiagInitialize()
{
  __int64 v0; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v3; // [rsp+30h] [rbp-39h] BYREF
  int v4; // [rsp+38h] [rbp-31h] BYREF
  __int64 v5; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v6[32]; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v7; // [rsp+70h] [rbp+7h]
  __int64 v8; // [rsp+78h] [rbp+Fh]
  char *v9; // [rsp+80h] [rbp+17h]
  __int64 v10; // [rsp+88h] [rbp+1Fh]
  int *v11; // [rsp+90h] [rbp+27h]
  __int64 v12; // [rsp+98h] [rbp+2Fh]
  __int64 *v13; // [rsp+A0h] [rbp+37h]
  __int64 v14; // [rsp+A8h] [rbp+3Fh]

  if ( EtwRegister(&POP_ETW_PROVIDER, PopDiagTraceControlCallback, &PopDiagHandle, &PopDiagHandle) >= 0 )
  {
    PopDiagHandleRegistered = 1;
    EtwSetInformation(
      PopDiagHandle,
      EventProviderSetTraits,
      &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
      (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
  }
  PopDiagDeviceRundownWorkItem.Parameter = 0;
  PopDiagDeviceRundownWorkItem.WorkerRoutine = (void (__fastcall *)(void *))PopDiagDeviceRundownWorker;
  PopDiagDeviceRundownWorkItem.List.Flink = 0;
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0B718, PopDiagTraceControlCallback, &dword_140E0B718);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0B6A8, 0, 0);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0B670, 0, 0);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0B6E0, 0, 0);
  if ( EtwRegister(&POP_TRIGGER_ETW_PROVIDER, 0, 0, &PopTriggerDiagHandle) >= 0 )
    PopTriggerDiagHandleRegistered = 1;
  if ( PopTriggerDiagHandleRegistered )
    PopThermalDeferedTraceThermalZoneEnumeration();
  PopDiagSleepStudyInitialize();
  if ( (int)TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0B938, 0, 0) >= 0 )
    PotsPowerTransitionsHandleRegistered = 1;
  qword_140EF98C8 = 0;
  PopTelemetryOsState = 0;
  LOBYTE(v0) = 1;
  qword_140EF98D8 = MEMORY[0xFFFFF78000000014];
  qword_140EF98E0 = MEMORY[0xFFFFF78000000008];
  qword_140EF98E8 = KiQueryUnbiasedInterruptTime(v0);
  byte_140EF990C = 1;
  PopTransitionTelemetryOsState(1);
  PdcTaskClientRegister(68, &PopSleepStudyTaskClientActivator);
  if ( (unsigned int)dword_140E0B718 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140E0B718, 0x400000000000LL) )
  {
    if ( (Feature_AusterityModeEnabled__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_AusterityModeEnabled__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_AusterityModeEnabled__private_IsEnabledDeviceUsageNoInline();
    v8 = 4;
    v7 = &v3;
    LODWORD(v3) = IsEnabledDeviceUsageNoInline != 0;
    HIDWORD(v3) = Feature_AusterityModeEnabled__private_GetVariant();
    v10 = 4;
    v9 = (char *)&v3 + 4;
    v4 = (unsigned __int64)wil_details_FeatureStateCache_GetCachedVariantState(
                             &Feature_AusterityModeEnabled__private_featureState,
                             &Feature_AusterityModeEnabled__private_descriptor) >> 32;
    v12 = 4;
    v11 = &v4;
    v5 = 0x1000000;
    v13 = &v5;
    v14 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140E0B718, word_14004C472, 0, 0, 6, v6, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x140c73dd8  push    rbp
0x140c73dda  lea     rbp, [rsp-57h]
0x140c73ddf  sub     rsp, 0C0h
0x140c73de6  mov     rax, cs:__security_cookie
0x140c73ded  xor     rax, rsp
0x140c73df0  mov     [rbp+57h+var_10], rax
0x140c73df4  lea     r8, PopDiagHandle; CallbackContext
0x140c73dfb  mov     r9, r8; RegHandle
0x140c73dfe  lea     rdx, PopDiagTraceControlCallback; EnableCallback
0x140c73e05  lea     rcx, POP_ETW_PROVIDER; ProviderId
0x140c73e0c  call    EtwRegister
0x140c73e11  test    eax, eax
0x140c73e13  js      short loc_140C73E3C
0x140c73e15  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@9@9; InformationLength
0x140c73e1d  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@9@9; EventInformation
0x140c73e24  mov     rcx, cs:PopDiagHandle; RegHandle
0x140c73e2b  mov     edx, 2; InformationClass
0x140c73e30  mov     cs:PopDiagHandleRegistered, 1
0x140c73e37  call    EtwSetInformation
0x140c73e3c  lea     rax, PopDiagDeviceRundownWorker
0x140c73e43  mov     cs:PopDiagDeviceRundownWorkItem.Parameter, 0
0x140c73e4e  lea     r8, dword_140E0B718
0x140c73e55  mov     cs:PopDiagDeviceRundownWorkItem.WorkerRoutine, rax
0x140c73e5c  lea     rdx, PopDiagTraceControlCallback
0x140c73e63  mov     cs:PopDiagDeviceRundownWorkItem.List.Flink, 0
0x140c73e6e  lea     rcx, dword_140E0B718
0x140c73e75  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c73e7a  xor     r8d, r8d
0x140c73e7d  lea     rcx, dword_140E0B6A8
0x140c73e84  xor     edx, edx
0x140c73e86  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c73e8b  xor     r8d, r8d
0x140c73e8e  lea     rcx, dword_140E0B670
0x140c73e95  xor     edx, edx
0x140c73e97  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c73e9c  xor     r8d, r8d
0x140c73e9f  lea     rcx, dword_140E0B6E0
0x140c73ea6  xor     edx, edx
0x140c73ea8  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c73ead  lea     r9, PopTriggerDiagHandle; RegHandle
0x140c73eb4  xor     r8d, r8d; CallbackContext
0x140c73eb7  xor     edx, edx; EnableCallback
0x140c73eb9  lea     rcx, POP_TRIGGER_ETW_PROVIDER; ProviderId
0x140c73ec0  call    EtwRegister
0x140c73ec5  test    eax, eax
0x140c73ec7  js      short loc_140C73ED0
0x140c73ec9  mov     cs:PopTriggerDiagHandleRegistered, 1
0x140c73ed0  cmp     cs:PopTriggerDiagHandleRegistered, 0
0x140c73ed7  jz      short loc_140C73EDE
0x140c73ed9  call    PopThermalDeferedTraceThermalZoneEnumeration
0x140c73ede  call    PopDiagSleepStudyInitialize
0x140c73ee3  xor     r8d, r8d
0x140c73ee6  lea     rcx, dword_140E0B938
0x140c73eed  xor     edx, edx
0x140c73eef  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c73ef4  test    eax, eax
0x140c73ef6  js      short loc_140C73EFF
0x140c73ef8  mov     cs:PotsPowerTransitionsHandleRegistered, 1
0x140c73eff  mov     cs:qword_140EF98C8, 0
0x140c73f0a  mov     rax, 0FFFFF78000000014h
0x140c73f14  mov     cs:PopTelemetryOsState, 0
0x140c73f1f  mov     cl, 1
0x140c73f21  mov     rax, [rax]
0x140c73f24  mov     cs:qword_140EF98D8, rax
0x140c73f2b  mov     rax, 0FFFFF78000000008h
0x140c73f35  mov     rax, [rax]
0x140c73f38  mov     cs:qword_140EF98E0, rax
0x140c73f3f  call    KiQueryUnbiasedInterruptTime
0x140c73f44  xor     r8d, r8d
0x140c73f47  mov     cs:qword_140EF98E8, rax
0x140c73f4e  mov     cs:byte_140EF990C, 1
0x140c73f55  lea     edx, [r8+1]
0x140c73f59  mov     ecx, edx
0x140c73f5b  call    PopTransitionTelemetryOsState
0x140c73f60  lea     rdx, PopSleepStudyTaskClientActivator
0x140c73f67  mov     ecx, 44h ; 'D'
0x140c73f6c  call    cs:__imp_PdcTaskClientRegister
0x140c73f73  nop     dword ptr [rax+rax+00h]
0x140c73f78  mov     eax, cs:dword_140E0B718
0x140c73f7e  cmp     eax, 5
0x140c73f81  jbe     loc_140C74057
0x140c73f87  mov     rdx, 400000000000h
0x140c73f91  lea     rcx, dword_140E0B718
0x140c73f98  call    _tlgKeywordOn
0x140c73f9d  test    al, al
0x140c73f9f  jz      loc_140C74057
0x140c73fa5  mov     eax, cs:Feature_AusterityModeEnabled__private_featureState
0x140c73fab  test    al, 10h
0x140c73fad  jz      short loc_140C73FB4
0x140c73faf  and     eax, 1
0x140c73fb2  jmp     short loc_140C73FB9
0x140c73fb4  call    Feature_AusterityModeEnabled__private_IsEnabledDeviceUsageNoInline
0x140c73fb9  xor     ecx, ecx
0x140c73fbb  mov     [rbp+57h+var_48], 4
0x140c73fc3  test    eax, eax
0x140c73fc5  lea     rax, [rbp+57h+var_90]
0x140c73fc9  mov     [rbp+57h+var_50], rax
0x140c73fcd  setnz   cl
0x140c73fd0  mov     [rbp+57h+var_90], ecx
0x140c73fd3  call    Feature_AusterityModeEnabled__private_GetVariant
0x140c73fd8  mov     [rbp+57h+var_8C], eax
0x140c73fdb  lea     rdx, Feature_AusterityModeEnabled__private_descriptor
0x140c73fe2  lea     rax, [rbp+57h+var_8C]
0x140c73fe6  mov     [rbp+57h+var_38], 4
0x140c73fee  lea     rcx, Feature_AusterityModeEnabled__private_featureState
0x140c73ff5  mov     [rbp+57h+var_40], rax
0x140c73ff9  call    wil_details_FeatureStateCache_GetCachedVariantState
0x140c73ffe  shr     rax, 20h
0x140c74002  lea     rdx, word_14004C472
0x140c74009  mov     [rbp+57h+var_88], eax
0x140c7400c  lea     rcx, dword_140E0B718
0x140c74013  lea     rax, [rbp+57h+var_88]
0x140c74017  mov     [rbp+57h+var_28], 4
0x140c7401f  mov     [rbp+57h+var_30], rax
0x140c74023  xor     r9d, r9d
0x140c74026  lea     rax, [rbp+57h+var_80]
0x140c7402a  mov     [rbp+57h+var_80], 1000000h
0x140c74032  mov     [rbp+57h+var_20], rax
0x140c74036  xor     r8d, r8d
0x140c74039  lea     rax, [rbp+57h+var_70]
0x140c7403d  mov     [rbp+57h+var_18], 8
0x140c74045  mov     [rsp+0C0h+var_98], rax
0x140c7404a  mov     [rsp+0C0h+var_A0], 6
0x140c74052  call    _tlgWriteTransfer_EtwWriteTransfer
0x140c74057  xor     eax, eax
0x140c74059  mov     rcx, [rbp+57h+var_10]
0x140c7405d  xor     rcx, rsp; StackCookie
0x140c74060  call    __security_check_cookie
0x140c74065  add     rsp, 0C0h
0x140c7406c  pop     rbp
0x140c7406d  retn
```
