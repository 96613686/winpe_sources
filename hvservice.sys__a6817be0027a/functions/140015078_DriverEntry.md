# DriverEntry

- ea: `0x140015078`
- end: `0x14001526c`
- name: `DriverEntry`
- size: `500`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x140015010`

## callees

- `0x140001600`
- `0x140002824`
- `0x140002ae0`
- `0x14000e600`
- `0x14000e61c`
- `0x140015078`

## import_xrefs

- `ntoskrnl!IoReportRootDevice` at `0x1400151f5`
- `ntoskrnl!IoReportRootDevice` at `0x1400151f5`
- `HAL!KeQueryPerformanceCounter` at `0x1400150a8`
- `HAL!KeQueryPerformanceCounter` at `0x1400150a8`

## string_xrefs

- `0x140015238`: `HvService entry failed with 0x%x, driver will not load. Version: %s`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS v3; // ebx
  __int64 v4; // r11
  PDRIVER_EXTENSION DriverExtension; // rax
  NTSTATUS v6; // eax
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF

  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140009088);
  qword_1400091D8[0] = KeQueryPerformanceCounter(&stru_1400091E0).QuadPart;
  HbpTraceEvent(3, "HbRecordPhaseTimestamp", 177, "Phase %s reached", HbDriverPhaseNames[0]);
  HbDriverLastRecordedLifecyclePhase = 0;
  v8 = 0;
  HviGetHypervisorFeatures(&v8);
  if ( (v8 & 0x100000000LL) != 0 )
  {
    HbpTraceEvent(2, "DriverEntry", 105, "Hypervisor detected and is management partition, initializing driver.");
    v8 = 0;
    HviGetHypervisorFeatures(&v8);
    v4 = v8;
    DriverObject->DriverUnload = (PDRIVER_UNLOAD)HbDriverUnload;
    DriverExtension = DriverObject->DriverExtension;
    HbpIsCpuManagementPartition = (v4 & 0x100000000000LL) != 0;
    DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)HbAddDevice;
    DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)HbPnpDispatch;
    DriverObject->MajorFunction[22] = (PDRIVER_DISPATCH)&HbPowerDispatch;
    DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)&HbSysCtrlDispatch;
    DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&HbIoDispatchCreate;
    DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&HbIoDispatchCleanup;
    DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&HbIoDispatchClose;
    DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)HbIoDispatchIoctl;
    v6 = IoReportRootDevice(DriverObject);
    v3 = v6;
    if ( v6 < 0 )
    {
      HbpTraceEvent(0, "DriverEntry", 128, "IoReportRootDevice failed with 0x%x", v6);
      HbpTraceEvent(
        0,
        "DriverEntry",
        151,
        "HvService entry failed with 0x%x, driver will not load. Version: %s",
        v3,
        "10011.16384.GitEnlistment(RnDcbldB).260520-1434");
      HbpDriverTeardown();
    }
  }
  else
  {
    HbpTraceEvent(1, "DriverEntry", 100, "Hypervisor is not management partition, driver will not load");
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x140015078  push    rbx
0x14001507a  sub     rsp, 50h
0x14001507e  mov     rax, cs:__security_cookie
0x140015085  xor     rax, rsp
0x140015088  mov     [rsp+58h+var_18], rax
0x14001508d  mov     rbx, rcx
0x140015090  xor     r8d, r8d
0x140015093  lea     rcx, dword_140009088; CallbackContext
0x14001509a  xor     edx, edx
0x14001509c  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1400150a1  lea     rcx, stru_1400091E0; PerformanceFrequency
0x1400150a8  call    cs:__imp_KeQueryPerformanceCounter
0x1400150af  nop     dword ptr [rax+rax+00h]
0x1400150b4  mov     cs:qword_1400091D8, rax
0x1400150bb  mov     rax, cs:HbDriverPhaseNames
0x1400150c2  lea     r9, aPhaseSReached; "Phase %s reached"
0x1400150c9  mov     r8d, 0B1h
0x1400150cf  mov     [rsp+58h+var_38], rax
0x1400150d4  lea     rdx, aHbrecordphaset; "HbRecordPhaseTimestamp"
0x1400150db  mov     ecx, 3
0x1400150e0  call    HbpTraceEvent
0x1400150e5  xorps   xmm0, xmm0
0x1400150e8  mov     cs:HbDriverLastRecordedLifecyclePhase, 0
0x1400150f2  lea     rcx, [rsp+58h+var_28]
0x1400150f7  movups  [rsp+58h+var_28], xmm0
0x1400150fc  call    HviGetHypervisorFeatures
0x140015101  mov     rax, 100000000h
0x14001510b  test    qword ptr [rsp+58h+var_28], rax
0x140015110  jnz     short loc_140015136
0x140015112  mov     r8d, 64h ; 'd'
0x140015118  lea     r9, aHypervisorIsNo; "Hypervisor is not management partition,"...
0x14001511f  lea     rdx, aDriverentry; "DriverEntry"
0x140015126  lea     ecx, [r8-63h]
0x14001512a  call    HbpTraceEvent
0x14001512f  xor     ebx, ebx
0x140015131  jmp     loc_140015256
0x140015136  mov     r8d, 69h ; 'i'
0x14001513c  lea     r9, aHypervisorDete; "Hypervisor detected and is management p"...
0x140015143  lea     rdx, aDriverentry; "DriverEntry"
0x14001514a  lea     ecx, [r8-67h]
0x14001514e  call    HbpTraceEvent
0x140015153  xorps   xmm0, xmm0
0x140015156  lea     rcx, [rsp+58h+var_28]
0x14001515b  movups  [rsp+58h+var_28], xmm0
0x140015160  call    HviGetHypervisorFeatures
0x140015165  mov     r11, qword ptr [rsp+58h+var_28]
0x14001516a  lea     rax, HbDriverUnload
0x140015171  mov     [rbx+68h], rax
0x140015175  lea     rcx, HbAddDevice
0x14001517c  mov     rax, [rbx+30h]
0x140015180  shr     r11, 2Ch
0x140015184  and     r11b, 1
0x140015188  mov     cs:HbpIsCpuManagementPartition, r11b
0x14001518f  mov     [rax+8], rcx
0x140015193  lea     rax, HbPnpDispatch
0x14001519a  mov     [rbx+148h], rax
0x1400151a1  mov     rcx, rbx; DriverObject
0x1400151a4  lea     rax, HbPowerDispatch
0x1400151ab  mov     [rbx+120h], rax
0x1400151b2  lea     rax, HbSysCtrlDispatch
0x1400151b9  mov     [rbx+128h], rax
0x1400151c0  lea     rax, HbIoDispatchCreate
0x1400151c7  mov     [rbx+70h], rax
0x1400151cb  lea     rax, HbIoDispatchCleanup
0x1400151d2  mov     [rbx+100h], rax
0x1400151d9  lea     rax, HbIoDispatchClose
0x1400151e0  mov     [rbx+80h], rax
0x1400151e7  lea     rax, HbIoDispatchIoctl
0x1400151ee  mov     [rbx+0E0h], rax
0x1400151f5  call    cs:__imp_IoReportRootDevice
0x1400151fc  nop     dword ptr [rax+rax+00h]
0x140015201  mov     ebx, eax
0x140015203  test    eax, eax
0x140015205  jns     short loc_140015256
0x140015207  lea     r9, aIoreportrootde; "IoReportRootDevice failed with 0x%x"
0x14001520e  mov     dword ptr [rsp+58h+var_38], eax
0x140015212  mov     r8d, 80h
0x140015218  lea     rdx, aDriverentry; "DriverEntry"
0x14001521f  xor     ecx, ecx
0x140015221  call    HbpTraceEvent
0x140015226  lea     rax, a1001116384Gite; "10011.16384.GitEnlistment(RnDcbldB).260"...
0x14001522d  mov     r8d, 97h
0x140015233  mov     [rsp+58h+var_30], rax
0x140015238  lea     r9, aHvserviceEntry; "HvService entry failed with 0x%x, drive"...
0x14001523f  lea     rdx, aDriverentry; "DriverEntry"
0x140015246  mov     dword ptr [rsp+58h+var_38], ebx
0x14001524a  xor     ecx, ecx
0x14001524c  call    HbpTraceEvent
0x140015251  call    HbpDriverTeardown
0x140015256  mov     eax, ebx
0x140015258  mov     rcx, [rsp+58h+var_18]
0x14001525d  xor     rcx, rsp; StackCookie
0x140015260  call    __security_check_cookie
0x140015265  add     rsp, 50h
0x140015269  pop     rbx
0x14001526a  retn
```
