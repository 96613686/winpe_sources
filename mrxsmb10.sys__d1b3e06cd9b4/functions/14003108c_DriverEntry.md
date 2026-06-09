# DriverEntry

- ea: `0x14003108c`
- end: `0x140031799`
- name: `DriverEntry`
- size: `1805`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140055010`

## callees

- `0x140001008`
- `0x140001040`
- `0x14000dfd8`
- `0x14000ed10`
- `0x14000fa14`
- `0x140016560`
- `0x14003108c`
- `0x1400317a0`
- `0x140031a18`
- `0x140031b98`
- `0x140031d54`
- `0x140032114`
- `0x140032e60`
- `0x1400330b4`
- `0x14003330c`
- `0x140033520`
- `0x140033688`
- `0x14003371c`
- `0x140033b0c`
- `0x140035358`
- `0x14003e8d4`
- `0x140055078`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140031633`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031648`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003165d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031672`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031687`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003169c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400316b1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031633`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031648`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003165d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031672`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031687`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003169c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400316b1`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003132d`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003132d`
- `ntoskrnl!EtwRegister` at `0x1400311d8`
- `ntoskrnl!EtwRegister` at `0x1400311d8`
- `ntoskrnl!DbgPrint` at `0x140031600`
- `ntoskrnl!DbgPrint` at `0x140054401`
- `ntoskrnl!DbgPrint` at `0x140031600`
- `ntoskrnl!DbgPrint` at `0x140054401`
- `ntoskrnl!KeInitializeEvent` at `0x140031253`
- `ntoskrnl!KeInitializeEvent` at `0x140031281`
- `ntoskrnl!KeInitializeEvent` at `0x140031253`
- `ntoskrnl!KeInitializeEvent` at `0x140031281`
- `ntoskrnl!ExAllocatePool2` at `0x1400312c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400312c3`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14003128d`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14003128d`
- `mrxsmb!MRxSmbRegisterSubRedirector` at `0x140031351`
- `mrxsmb!MRxSmbRegisterSubRedirector` at `0x140031351`
- `mrxsmb!MRxSmbRegisterDialect` at `0x1400313a4`
- `mrxsmb!MRxSmbRegisterDialect` at `0x1400313e4`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14003142a`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14003146d`
- `mrxsmb!MRxSmbRegisterDialect` at `0x1400314b0`
- `mrxsmb!MRxSmbRegisterDialect` at `0x1400314f3`
- `mrxsmb!MRxSmbRegisterDialect` at `0x1400313a4`
- `mrxsmb!MRxSmbRegisterDialect` at `0x1400313e4`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14003142a`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14003146d`
- `mrxsmb!MRxSmbRegisterDialect` at `0x1400314b0`
- `mrxsmb!MRxSmbRegisterDialect` at `0x1400314f3`
- `mrxsmb!MRxSmbInitializeRecurrentService` at `0x140031730`
- `mrxsmb!MRxSmbInitializeRecurrentService` at `0x140031730`
- `mrxsmb!MRxSmbActivateRecurrentService` at `0x14003174d`
- `mrxsmb!MRxSmbActivateRecurrentService` at `0x14003174d`
- `mrxsmb!MRxSmbDeviceObject` at `0x140031347`
- `mrxsmb!MRxSmbDeviceObject` at `0x14003139a`
- `mrxsmb!MRxSmbDeviceObject` at `0x1400313da`
- `mrxsmb!MRxSmbDeviceObject` at `0x140031420`
- `mrxsmb!MRxSmbDeviceObject` at `0x140031463`
- `mrxsmb!MRxSmbDeviceObject` at `0x1400314a6`
- `mrxsmb!MRxSmbDeviceObject` at `0x1400314e9`
- `mrxsmb!MRxSmbDeviceObject` at `0x14003170b`
- `mrxsmb!MRxSmbDeviceObject` at `0x140031743`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  unsigned int v3; // edi
  unsigned int v4; // eax
  NTSTATUS v5; // ebx
  struct _MDL *Pool2; // rax
  struct _MDL *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-C8h]
  int v15; // [rsp+20h] [rbp-C8h]
  int v16; // [rsp+20h] [rbp-C8h]
  int v17; // [rsp+20h] [rbp-C8h]
  int v18; // [rsp+20h] [rbp-C8h]
  int v19; // [rsp+20h] [rbp-C8h]
  int v20; // [rsp+28h] [rbp-C0h]
  int v21; // [rsp+28h] [rbp-C0h]
  int v22; // [rsp+28h] [rbp-C0h]
  int v23; // [rsp+28h] [rbp-C0h]
  int v24; // [rsp+28h] [rbp-C0h]
  int v25; // [rsp+38h] [rbp-B0h]
  int v26; // [rsp+38h] [rbp-B0h]
  int v27; // [rsp+38h] [rbp-B0h]
  int v28; // [rsp+38h] [rbp-B0h]
  int v29; // [rsp+38h] [rbp-B0h]
  char v30; // [rsp+40h] [rbp-A8h] BYREF
  char v31; // [rsp+41h] [rbp-A7h] BYREF
  int v32; // [rsp+44h] [rbp-A4h]
  NTSTATUS v33; // [rsp+48h] [rbp-A0h]
  __int64 v34; // [rsp+50h] [rbp-98h] BYREF
  __int64 v35; // [rsp+58h] [rbp-90h] BYREF
  __int64 v36[10]; // [rsp+60h] [rbp-88h] BYREF

  v3 = 0;
  v32 = 0;
  v34 = 0;
  wil_InitializeFeatureStaging(DriverObject, RegistryPath);
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_MupLog;
  WPP_MAIN_CB.NextDevice = (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceExtension;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = WPP_ThisDir_CTLGUID_RFSMon;
  WPP_MAIN_CB.Queue.ListEntry.Flink = 0;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = 0;
  WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = (PDRIVER_CONTROL)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids,
      (_DWORD)DriverObject,
      (__int64)&DriverObject->DriverName);
  v4 = McGenEventRegister_EtwRegister();
  if ( v4
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids, v4);
  }
  v5 = 0;
  if ( !Microsoft_Windows_Networking_CorrelationHandle )
    v5 = EtwRegister(
           &Microsoft_Windows_Networking_CorrelationId,
           Microsoft_Windows_Networking_Correlation_EtwEnableCallback,
           0,
           &Microsoft_Windows_Networking_CorrelationHandle);
  if ( !v5 )
    Microsoft_Windows_Networking_ProviderId = (__int128)REMOTEFS_SMB;
  v33 = v5;
  if ( v5
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids, (unsigned int)v5);
  }
  WPP_MAIN_CB.Queue.Wcb.DeviceObject = DriverObject;
  MRxSmbSerializationMutex.Count = 1;
  MRxSmbSerializationMutex.Owner = 0;
  MRxSmbSerializationMutex.Contention = 0;
  KeInitializeEvent(&MRxSmbSerializationMutex.Event, SynchronizationEvent, 0);
  MRxSmbReadWriteMutex.Count = 1;
  MRxSmbReadWriteMutex.Owner = 0;
  MRxSmbReadWriteMutex.Contention = 0;
  KeInitializeEvent(&MRxSmbReadWriteMutex.Event, SynchronizationEvent, 0);
  RdrConfigurationBlock = MRxSmbGetConfigurationBlock();
  MRxSmbReadMiscellaneousRegistryParameters();
  if ( (unsigned int)IsServerSKU() )
    MRxSmbEnableOpDirCache = 0;
  Pool2 = (struct _MDL *)ExAllocatePool2(64, 88, 1934454099);
  v7 = Pool2;
  MrxSmbCeGlobalPadding = Pool2;
  if ( Pool2 )
  {
    Pool2->Next = 0;
    Pool2->Size = 8 * (((unsigned __int16)((((_WORD)Pool2 + 56) & 0xFFF) + 4127) >> 12) + 6);
    Pool2->MdlFlags = 0;
    Pool2->StartVa = (PVOID)((unsigned __int64)&Pool2[1].Size & 0xFFFFFFFFFFFFF000uLL);
    Pool2->ByteOffset = ((_WORD)Pool2 + 56) & 0xFFF;
    Pool2->ByteCount = 32;
    MmBuildMdlForNonPagedPool(Pool2);
    v5 = MRxSmbRegisterSubRedirector(MRxSmbDeviceObject, &WPP_MAIN_CB.DeviceQueue, &MRxSmb10SubRdrHandle);
    v33 = v5;
    if ( v5 >= 0 )
    {
      LOWORD(v14) = 0;
      MRxSmbRegisterDialect(MRxSmbDeviceObject, MRxSmb10SubRdrHandle, 0, 1, v14, 0, "PC NETWORK PROGRAM 1.0", -1);
      LOWORD(v25) = -1;
      LOWORD(v20) = 0;
      LOWORD(v15) = 1;
      MRxSmbRegisterDialect(MRxSmbDeviceObject, MRxSmb10SubRdrHandle, 1, 1, v15, v20, "LANMAN1.0", v25);
      LOWORD(v26) = -1;
      LOWORD(v21) = 0;
      LOWORD(v16) = 2;
      MRxSmbRegisterDialect(
        MRxSmbDeviceObject,
        MRxSmb10SubRdrHandle,
        2,
        1,
        v16,
        v21,
        "Windows for Workgroups 3.1a",
        v26);
      LOWORD(v27) = -1;
      LOWORD(v22) = 0;
      LOWORD(v17) = 3;
      MRxSmbRegisterDialect(MRxSmbDeviceObject, MRxSmb10SubRdrHandle, 3, 1, v17, v22, "LM1.2X002", v27);
      LOWORD(v28) = -1;
      LOWORD(v23) = 0;
      LOWORD(v18) = 4;
      MRxSmbRegisterDialect(MRxSmbDeviceObject, MRxSmb10SubRdrHandle, 4, 1, v18, v23, "LANMAN2.1", v28);
      LOWORD(v29) = -1;
      LOWORD(v24) = 0;
      LOWORD(v19) = 5;
      MRxSmbRegisterDialect(MRxSmbDeviceObject, MRxSmb10SubRdrHandle, 5, 1, v19, v24, "NT LM 0.12", v29);
      v3 = 1;
      v32 = 1;
      v5 = SmbMmInit();
      v33 = v5;
      if ( v5 >= 0 )
      {
        v3 = 2;
        v32 = 2;
        v5 = SmbCeDbInit();
        v33 = v5;
        if ( v5 >= 0 )
        {
          v5 = 0;
          v33 = 0;
          v3 = 5;
          v32 = 5;
          if ( (unsigned int)dword_14001F0D0 > 5 )
          {
            if ( (unsigned __int8)tlgKeywordOn(v7, v8, v9) )
            {
              v35 = 0x1000000;
              v36[4] = (__int64)&v35;
              v36[5] = 8;
              v30 = MRxSmbSecuritySignaturesEnabled;
              v36[6] = (__int64)&v30;
              v36[7] = 1;
              v31 = MRxSmbSecuritySignaturesRequired;
              v36[8] = (__int64)&v31;
              v36[9] = 1;
              tlgWriteTransfer_EtwWriteTransfer((int)v7, (int)&byte_14001B3D9, v10, v11, 5u, (__int64)v36);
            }
          }
        }
      }
    }
  }
  if ( v5 < 0 )
  {
    DbgPrint("MRxSmb10 failed to load with %08lx %08lx\n", v5, v3);
    MRxSmbInitUnwindSmb(v12, v3);
LABEL_29:
    wil_UninitializeFeatureStaging();
    return v5;
  }
  v5 = MRxSmbInitializeTables(v7);
  if ( v5 < 0 )
    goto LABEL_29;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&SmbCeContext, 0);
  RtlInitUnicodeString(&stru_1400202E0, 0);
  RtlInitUnicodeString(&stru_1400202F0, 0);
  RtlInitUnicodeString(&stru_140020300, 0);
  RtlInitUnicodeString(&stru_140020310, 0);
  RtlInitUnicodeString(&stru_140020320, 0);
  SmbCeGetConfigurationInformation();
  SmbCeGetServersWithExtendedSessTimeout();
  SmbCeGetReconnectableServers();
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)MRxSmbUnload;
  memset64(DriverObject->MajorFunction, (unsigned __int64)&MRxSmbFsdDispatch, 0x1Cu);
  MRxSmb1ObservedInthisPeriod = 0;
  MRxSmb1UnusedCounter = MRxSmbGetSMB1UnusedCounter();
  v34 = 12000000000LL;
  MRxSmbInitializeRecurrentService(
    MRxSmbSMB1UninstallServiceContext,
    MRxSmbSMB1MonitorRoutine,
    0,
    &v34,
    MRxSmbDeviceObject);
  MRxSmbActivateRecurrentService(MRxSmbDeviceObject, MRxSmbSMB1UninstallServiceContext);
  MRxSmbSMB1UninstallServiceInitialized = 1;
  return v5;
}

```

## disassembly

```asm
0x14003108c  mov     [rsp+arg_8], rbx
0x140031091  mov     [rsp+arg_10], rsi
0x140031096  push    rdi
0x140031097  push    r12
0x140031099  push    r13
0x14003109b  push    r14
0x14003109d  push    r15
0x14003109f  sub     rsp, 0C0h
0x1400310a6  mov     rax, cs:__security_cookie
0x1400310ad  xor     rax, rsp
0x1400310b0  mov     [rsp+0E8h+var_38], rax
0x1400310b8  mov     r14, rcx
0x1400310bb  xor     r15d, r15d
0x1400310be  mov     edi, r15d
0x1400310c1  mov     [rsp+0E8h+var_A4], r15d
0x1400310c6  mov     [rsp+0E8h+var_98], r15
0x1400310cb  call    wil_InitializeFeatureStaging
0x1400310d0  mov     qword ptr cs:WPP_MAIN_CB.Type, r15
0x1400310d7  lea     rax, WPP_ThisDir_CTLGUID_MupLog
0x1400310de  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400310e5  lea     rax, WPP_MAIN_CB.DeviceExtension
0x1400310ec  mov     cs:WPP_MAIN_CB.NextDevice, rax
0x1400310f3  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x1400310fa  lea     r12d, [r15+1]
0x1400310fe  mov     cs:WPP_MAIN_CB.Timer, r12
0x140031105  mov     cs:WPP_MAIN_CB.DeviceExtension, r15
0x14003110c  lea     rax, WPP_ThisDir_CTLGUID_RFSMon
0x140031113  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x14003111a  mov     qword ptr cs:WPP_MAIN_CB.Queue, r15
0x140031121  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, r15
0x140031128  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, r12
0x14003112f  call    WppLoadTracingSupport
0x140031134  mov     cs:WPP_MAIN_CB.CurrentIrp, r15; __annotation("TMC:", "51734B23-5B7E-4892-BA8E-45BC110B735C", "RFSMon", "IRPS", "MIGRATION", "OPLOCKBREAKS", "IRPSEXTENDED", "IOCANCEL", "PUBLIC_TMF:")
0x14003113b  call    WppInitKm
0x140031140  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140031145  lea     r13, WPP_GLOBAL_Control; __annotation("TMF:",
0x14003114c  mov     rcx, cs:WPP_GLOBAL_Control
0x140031153  mov     esi, 400h
0x140031158  cmp     rcx, r13
0x14003115b  jz      short loc_140031182
0x14003115d  test    [rcx+2Ch], esi
0x140031160  jz      short loc_140031182
0x140031162  lea     rax, [r14+38h]
0x140031166  lea     edx, [r15+0Ah]
0x14003116a  mov     qword ptr [rsp+0E8h+var_C8], rax
0x14003116f  mov     r9, r14
0x140031172  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x140031179  mov     rcx, [rcx+18h]
0x14003117d  call    WPP_SF_qZ
0x140031182  call    McGenEventRegister_EtwRegister
0x140031187  test    eax, eax
0x140031189  jz      short loc_1400311B4
0x14003118b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140031192  cmp     rcx, r13
0x140031195  jz      short loc_1400311B4
0x140031197  test    [rcx+2Ch], esi
0x14003119a  jz      short loc_1400311B4
0x14003119c  mov     edx, 0Bh
0x1400311a1  mov     r9d, eax
0x1400311a4  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x1400311ab  mov     rcx, [rcx+18h]
0x1400311af  call    WPP_SF_d
0x1400311b4  mov     ebx, r15d
0x1400311b7  cmp     cs:Microsoft_Windows_Networking_CorrelationHandle, rbx
0x1400311be  jnz     short loc_1400311E6
0x1400311c0  lea     r9, Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x1400311c7  xor     r8d, r8d; CallbackContext
0x1400311ca  lea     rdx, Microsoft_Windows_Networking_Correlation_EtwEnableCallback; EnableCallback
0x1400311d1  lea     rcx, Microsoft_Windows_Networking_CorrelationId; ProviderId
0x1400311d8  call    cs:__imp_EtwRegister
0x1400311df  nop     dword ptr [rax+rax+00h]
0x1400311e4  mov     ebx, eax
0x1400311e6  test    ebx, ebx
0x1400311e8  jnz     short loc_1400311F9
0x1400311ea  movups  xmm0, xmmword ptr cs:REMOTEFS_SMB.Data1
0x1400311f1  movdqu  cs:Microsoft_Windows_Networking_ProviderId, xmm0
0x1400311f9  mov     [rsp+0E8h+var_A0], ebx
0x1400311fd  test    ebx, ebx
0x1400311ff  jz      short loc_14003122A
0x140031201  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140031208  cmp     rcx, r13
0x14003120b  jz      short loc_14003122A
0x14003120d  test    [rcx+2Ch], esi
0x140031210  jz      short loc_14003122A
0x140031212  mov     edx, 0Ch
0x140031217  mov     r9d, ebx
0x14003121a  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x140031221  mov     rcx, [rcx+18h]
0x140031225  call    WPP_SF_d
0x14003122a  mov     qword ptr cs:WPP_MAIN_CB.Queue+30h, r14
0x140031231  mov     cs:MRxSmbSerializationMutex.Count, r12d
0x140031238  mov     cs:MRxSmbSerializationMutex.Owner, r15
0x14003123f  mov     cs:MRxSmbSerializationMutex.Contention, r15d
0x140031246  xor     r8d, r8d; State
0x140031249  mov     edx, r12d; Type
0x14003124c  lea     rcx, MRxSmbSerializationMutex.Event; Event
0x140031253  call    cs:__imp_KeInitializeEvent
0x14003125a  nop     dword ptr [rax+rax+00h]
0x14003125f  mov     cs:MRxSmbReadWriteMutex.Count, r12d
0x140031266  mov     cs:MRxSmbReadWriteMutex.Owner, r15
0x14003126d  mov     cs:MRxSmbReadWriteMutex.Contention, r15d
0x140031274  xor     r8d, r8d; State
0x140031277  mov     edx, r12d; Type
0x14003127a  lea     rcx, MRxSmbReadWriteMutex.Event; Event
0x140031281  call    cs:__imp_KeInitializeEvent
0x140031288  nop     dword ptr [rax+rax+00h]
0x14003128d  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140031294  nop     dword ptr [rax+rax+00h]
0x140031299  mov     cs:RdrConfigurationBlock, rax
0x1400312a0  call    MRxSmbReadMiscellaneousRegistryParameters
0x1400312a5  call    IsServerSKU
0x1400312aa  test    eax, eax
0x1400312ac  jz      short loc_1400312B5
0x1400312ae  mov     cs:MRxSmbEnableOpDirCache, r15b
0x1400312b5  mov     edx, 58h ; 'X'
0x1400312ba  lea     ecx, [rdx-18h]
0x1400312bd  mov     r8d, 734D6D53h
0x1400312c3  call    cs:__imp_ExAllocatePool2
0x1400312ca  nop     dword ptr [rax+rax+00h]
0x1400312cf  mov     rcx, rax; MemoryDescriptorList
0x1400312d2  mov     cs:MrxSmbCeGlobalPadding, rax
0x1400312d9  test    rax, rax
0x1400312dc  jz      loc_1400315F0
0x1400312e2  lea     rdx, [rax+38h]
0x1400312e6  mov     [rax], r15
0x1400312e9  movzx   eax, dx
0x1400312ec  mov     r9d, 0FFFh
0x1400312f2  and     ax, r9w
0x1400312f6  lea     r8d, [r9+20h]
0x1400312fa  add     ax, r8w
0x1400312fe  shr     ax, 0Ch
0x140031302  add     ax, 6
0x140031306  shl     ax, 3
0x14003130a  mov     [rcx+8], ax
0x14003130e  mov     [rcx+0Ah], r15w
0x140031313  mov     rax, rdx
0x140031316  and     rax, 0FFFFFFFFFFFFF000h
0x14003131c  mov     [rcx+20h], rax
0x140031320  and     edx, r9d
0x140031323  mov     [rcx+2Ch], edx
0x140031326  mov     dword ptr [rcx+28h], 20h ; ' '
0x14003132d  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140031334  nop     dword ptr [rax+rax+00h]
0x140031339  lea     r8, MRxSmb10SubRdrHandle
0x140031340  lea     rdx, WPP_MAIN_CB.DeviceQueue
0x140031347  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14003134e  mov     rcx, [rcx]
0x140031351  call    cs:__imp_MRxSmbRegisterSubRedirector
0x140031358  nop     dword ptr [rax+rax+00h]
0x14003135d  mov     ebx, eax
0x14003135f  mov     [rsp+0E8h+var_A0], eax
0x140031363  test    eax, eax
0x140031365  js      loc_1400315F0
0x14003136b  mov     edi, 0FFFFh
0x140031370  mov     r9d, r12d
0x140031373  mov     [rsp+0E8h+var_B0], di
0x140031378  lea     rdx, aPcNetworkProgr; "PC NETWORK PROGRAM 1.0"
0x14003137f  mov     [rsp+0E8h+var_B8], rdx
0x140031384  mov     word ptr [rsp+0E8h+var_C0], r15w
0x14003138a  mov     word ptr [rsp+0E8h+var_C8], r15w
0x140031390  xor     r8d, r8d
0x140031393  mov     rdx, cs:MRxSmb10SubRdrHandle
0x14003139a  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x1400313a1  mov     rcx, [rcx]
0x1400313a4  call    cs:__imp_MRxSmbRegisterDialect
0x1400313ab  nop     dword ptr [rax+rax+00h]
0x1400313b0  mov     r9d, r12d
0x1400313b3  mov     [rsp+0E8h+var_B0], di
0x1400313b8  lea     rcx, aLanman10; "LANMAN1.0"
0x1400313bf  mov     [rsp+0E8h+var_B8], rcx
0x1400313c4  mov     word ptr [rsp+0E8h+var_C0], r15w
0x1400313ca  mov     word ptr [rsp+0E8h+var_C8], r12w
0x1400313d0  mov     r8d, r12d
0x1400313d3  mov     rdx, cs:MRxSmb10SubRdrHandle
0x1400313da  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x1400313e1  mov     rcx, [rcx]
0x1400313e4  call    cs:__imp_MRxSmbRegisterDialect
0x1400313eb  nop     dword ptr [rax+rax+00h]
0x1400313f0  mov     r13d, 2
0x1400313f6  mov     r9d, r12d
0x1400313f9  mov     [rsp+0E8h+var_B0], di
0x1400313fe  lea     rcx, aWindowsForWork; "Windows for Workgroups 3.1a"
0x140031405  mov     [rsp+0E8h+var_B8], rcx
0x14003140a  mov     word ptr [rsp+0E8h+var_C0], r15w
0x140031410  mov     word ptr [rsp+0E8h+var_C8], r13w
0x140031416  mov     r8d, r13d
0x140031419  mov     rdx, cs:MRxSmb10SubRdrHandle
0x140031420  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140031427  mov     rcx, [rcx]
0x14003142a  call    cs:__imp_MRxSmbRegisterDialect
0x140031431  nop     dword ptr [rax+rax+00h]
0x140031436  lea     edx, [r13+1]
0x14003143a  mov     r9d, r12d
0x14003143d  mov     [rsp+0E8h+var_B0], di
0x140031442  lea     rcx, aLm12x002; "LM1.2X002"
0x140031449  mov     [rsp+0E8h+var_B8], rcx
0x14003144e  mov     word ptr [rsp+0E8h+var_C0], r15w
0x140031454  mov     word ptr [rsp+0E8h+var_C8], dx
0x140031459  mov     r8d, edx
0x14003145c  mov     rdx, cs:MRxSmb10SubRdrHandle
0x140031463  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14003146a  mov     rcx, [rcx]
0x14003146d  call    cs:__imp_MRxSmbRegisterDialect
0x140031474  nop     dword ptr [rax+rax+00h]
0x140031479  lea     edx, [r13+2]
0x14003147d  mov     r9d, r12d
0x140031480  mov     [rsp+0E8h+var_B0], di
0x140031485  lea     rcx, aLanman21; "LANMAN2.1"
0x14003148c  mov     [rsp+0E8h+var_B8], rcx
0x140031491  mov     word ptr [rsp+0E8h+var_C0], r15w
0x140031497  mov     word ptr [rsp+0E8h+var_C8], dx
0x14003149c  mov     r8d, edx
0x14003149f  mov     rdx, cs:MRxSmb10SubRdrHandle
0x1400314a6  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x1400314ad  mov     rcx, [rcx]
0x1400314b0  call    cs:__imp_MRxSmbRegisterDialect
0x1400314b7  nop     dword ptr [rax+rax+00h]
0x1400314bc  lea     esi, [r13+3]
0x1400314c0  mov     r9d, r12d
0x1400314c3  mov     [rsp+0E8h+var_B0], di
0x1400314c8  lea     rcx, aNtLm012; "NT LM 0.12"
0x1400314cf  mov     [rsp+0E8h+var_B8], rcx
0x1400314d4  mov     word ptr [rsp+0E8h+var_C0], r15w
0x1400314da  mov     word ptr [rsp+0E8h+var_C8], si
0x1400314df  mov     r8d, esi
0x1400314e2  mov     rdx, cs:MRxSmb10SubRdrHandle
0x1400314e9  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x1400314f0  mov     rcx, [rcx]
0x1400314f3  call    cs:__imp_MRxSmbRegisterDialect
0x1400314fa  nop     dword ptr [rax+rax+00h]
0x1400314ff  mov     edi, r12d
0x140031502  mov     [rsp+0E8h+var_A4], r12d
0x140031507  call    SmbMmInit
0x14003150c  mov     ebx, eax
0x14003150e  mov     [rsp+0E8h+var_A0], eax
0x140031512  test    eax, eax
0x140031514  js      loc_1400315F0
0x14003151a  mov     edi, r13d
0x14003151d  mov     [rsp+0E8h+var_A4], r13d
0x140031522  call    SmbCeDbInit
0x140031527  mov     ebx, eax
0x140031529  mov     [rsp+0E8h+var_A0], eax
0x14003152d  test    eax, eax
0x14003152f  js      loc_1400315F0
0x140031535  mov     [rsp+0E8h+var_A4], 3
0x14003153d  mov     ebx, r15d
0x140031540  mov     [rsp+0E8h+var_A0], ebx
0x140031544  mov     [rsp+0E8h+var_A4], 4
0x14003154c  mov     edi, esi
0x14003154e  mov     [rsp+0E8h+var_A4], esi
0x140031552  mov     eax, cs:dword_14001F0D0
0x140031558  cmp     eax, esi
0x14003155a  jbe     loc_1400315F0
0x140031560  call    _tlgKeywordOn
0x140031565  test    al, al
0x140031567  jz      loc_1400315F0
0x14003156d  mov     [rsp+0E8h+var_90], 1000000h
0x140031576  lea     rax, [rsp+0E8h+var_90]
0x14003157b  mov     [rsp+0E8h+var_68], rax
0x140031583  mov     [rsp+0E8h+var_60], 8
0x14003158f  mov     al, cs:MRxSmbSecuritySignaturesEnabled
0x140031595  mov     [rsp+0E8h+var_A8], al
0x140031599  lea     rax, [rsp+0E8h+var_A8]
0x14003159e  mov     [rsp+0E8h+var_58], rax
0x1400315a6  mov     [rsp+0E8h+var_50], 1
0x1400315b2  mov     al, cs:MRxSmbSecuritySignaturesRequired
0x1400315b8  mov     [rsp+0E8h+var_A7], al
0x1400315bc  lea     rax, [rsp+0E8h+var_A7]
0x1400315c1  mov     [rsp+0E8h+var_48], rax
0x1400315c9  mov     [rsp+0E8h+var_40], 1
0x1400315d5  lea     rax, [rsp+0E8h+var_88]
0x1400315da  mov     [rsp+0E8h+var_C0], rax; __int64
0x1400315df  mov     [rsp+0E8h+var_C8], esi; ULONG
0x1400315e3  lea     rdx, byte_14001B3D9; int
0x1400315ea  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400315ef  nop
0x1400315f0  test    ebx, ebx
0x1400315f2  jns     short loc_14003161B
0x1400315f4  mov     r8d, edi
0x1400315f7  mov     edx, ebx
0x1400315f9  lea     rcx, aMrxsmb10Failed; "MRxSmb10 failed to load with %08lx %08l"...
0x140031600  call    cs:__imp_DbgPrint
0x140031607  nop     dword ptr [rax+rax+00h]
0x14003160c  mov     edx, edi
0x14003160e  call    MRxSmbInitUnwindSmb
0x140031613  test    ebx, ebx
0x140031615  js      loc_140031764
0x14003161b  call    MRxSmbInitializeTables
0x140031620  mov     ebx, eax
0x140031622  test    eax, eax
0x140031624  js      loc_140031760
0x14003162a  xor     edx, edx; SourceString
0x14003162c  lea     rcx, DestinationString; DestinationString
0x140031633  call    cs:__imp_RtlInitUnicodeString
0x14003163a  nop     dword ptr [rax+rax+00h]
0x14003163f  xor     edx, edx; SourceString
0x140031641  lea     rcx, SmbCeContext; DestinationString
0x140031648  call    cs:__imp_RtlInitUnicodeString
0x14003164f  nop     dword ptr [rax+rax+00h]
0x140031654  xor     edx, edx; SourceString
  ... truncated ...
```
