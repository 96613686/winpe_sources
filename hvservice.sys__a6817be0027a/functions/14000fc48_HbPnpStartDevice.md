# HbPnpStartDevice

- ea: `0x14000fc48`
- end: `0x14000fee2`
- name: `HbPnpStartDevice`
- size: `666`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400140f0`

## callees

- `0x140001600`
- `0x14000e6fc`
- `0x14000fc48`

## import_xrefs

- `ntoskrnl!PoSetPowerState` at `0x14000fe40`
- `ntoskrnl!PoSetPowerState` at `0x14000fe40`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000fd97`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000fd97`
- `ntoskrnl!IofCompleteRequest` at `0x14000fd7e`
- `ntoskrnl!IofCompleteRequest` at `0x14000fd7e`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14000fdc6`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14000fdc6`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000fe02`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000fe02`
- `ntoskrnl!KeInitializeMutex` at `0x14000fca5`
- `ntoskrnl!KeInitializeMutex` at `0x14000fca5`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14000fc64`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14000fc64`
- `ntoskrnl!KeInitializeEvent` at `0x14000fce4`
- `ntoskrnl!KeInitializeEvent` at `0x14000fce4`
- `HAL!KeQueryPerformanceCounter` at `0x14000fe61`
- `HAL!KeQueryPerformanceCounter` at `0x14000fe61`

## string_xrefs

- `0x14000fea9`: `HvService loaded. Version: %s, Loaded in %llu ms`
- `0x14000fd58`: `HvService device start failed with 0x%x. Version: %s`

## pseudocode

```c
__int64 __fastcall HbPnpStartDevice(__int64 a1, IRP *a2)
{
  PDEVICE_OBJECT *v2; // rsi
  int Status; // edi
  int v6; // eax
  struct _IO_REMOVE_LOCK *v7; // rbx
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  LARGE_INTEGER PerformanceCounter; // rax
  LONGLONG v12; // rax

  v2 = *(PDEVICE_OBJECT **)(a1 + 64);
  IoForwardIrpSynchronously(v2[3], a2);
  Status = a2->IoStatus.Status;
  if ( Status < 0 )
  {
    HbpTraceEvent(0, "HbPnpStartDevice", 297, "Lower driver failed START_DEVICE with 0x%x", a2->IoStatus.Status);
    goto LABEL_6;
  }
  KeInitializeMutex((PRKMUTEX)(v2 + 26), 0);
  *((_BYTE *)v2 + 264) = 0;
  *((_DWORD *)v2 + 68) = 1;
  v2[35] = 0;
  *((_DWORD *)v2 + 72) = 0;
  KeInitializeEvent((PRKEVENT)(v2 + 37), SynchronizationEvent, 0);
  v2[41] = (PDEVICE_OBJECT)-1LL;
  v2[22] = (PDEVICE_OBJECT)(v2 + 21);
  v2[21] = (PDEVICE_OBJECT)(v2 + 21);
  *((_DWORD *)v2 + 84) = 1;
  *((_DWORD *)v2 + 46) = 1;
  v6 = HbHvInitializeHypervisor(v2);
  Status = v6;
  if ( v6 < 0 )
  {
    HbpTraceEvent(0, "HbPnpStartDevice", 320, "HbHvInitializeHypervisor failed with 0x%x", v6);
LABEL_5:
    HbpTraceEvent(
      0,
      "HbPnpStartDevice",
      369,
      "HvService device start failed with 0x%x. Version: %s",
      Status,
      "10011.16384.GitEnlistment(RnDcbldB).260520-1434");
    goto LABEL_6;
  }
  v9 = IoRegisterDeviceInterface(v2[2], &GUID_DEVINTERFACE_HVBOOT, 0, (PUNICODE_STRING)v2 + 2);
  Status = v9;
  if ( v9 < 0 )
  {
    HbpTraceEvent(0, "HbPnpStartDevice", 335, "IoRegisterDeviceInterface failed with 0x%x", v9);
    goto LABEL_5;
  }
  v10 = IoSetDeviceInterfaceState((PUNICODE_STRING)v2 + 2, 1u);
  Status = v10;
  if ( v10 < 0 )
  {
    HbpTraceEvent(0, "HbPnpStartDevice", 346, "IoSetDeviceInterfaceState failed with 0x%x", v10);
    goto LABEL_5;
  }
  PoSetPowerState(*v2, DevicePowerState, (POWER_STATE)1);
  if ( !qword_1400091D8[0] )
    goto LABEL_5;
  PerformanceCounter = KeQueryPerformanceCounter(&stru_140009210);
  qword_140009208 = PerformanceCounter.QuadPart;
  if ( qword_1400091D8[0] && PerformanceCounter.QuadPart && stru_140009210.QuadPart )
    v12 = 1000 * (PerformanceCounter.QuadPart - qword_1400091D8[0]) / stru_140009210.QuadPart;
  else
    v12 = 0;
  HbpTraceEvent(
    3,
    "HbRecordPhaseTimestamp",
    151,
    "HvService loaded. Version: %s, Loaded in %llu ms",
    "10011.16384.GitEnlistment(RnDcbldB).260520-1434",
    v12);
  HbDriverLastRecordedLifecyclePhase = 2;
LABEL_6:
  v7 = *(struct _IO_REMOVE_LOCK **)(a1 + 64);
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  IoReleaseRemoveLockEx(v7 + 2, a2, 0x20u);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000fc48  push    rbx
0x14000fc4a  push    rsi
0x14000fc4b  push    rdi
0x14000fc4c  push    r12
0x14000fc4e  push    r14
0x14000fc50  push    r15
0x14000fc52  sub     rsp, 38h
0x14000fc56  mov     rsi, [rcx+40h]
0x14000fc5a  mov     r15, rcx
0x14000fc5d  mov     r14, rdx
0x14000fc60  mov     rcx, [rsi+18h]; DeviceObject
0x14000fc64  call    cs:__imp_IoForwardIrpSynchronously
0x14000fc6b  nop     dword ptr [rax+rax+00h]
0x14000fc70  mov     edi, [r14+30h]
0x14000fc74  test    edi, edi
0x14000fc76  jns     short loc_14000FC9C
0x14000fc78  lea     r9, aLowerDriverFai; "Lower driver failed START_DEVICE with 0"...
0x14000fc7f  mov     dword ptr [rsp+68h+var_48], edi
0x14000fc83  mov     r8d, 129h
0x14000fc89  lea     rdx, aHbpnpstartdevi; "HbPnpStartDevice"
0x14000fc90  xor     ecx, ecx
0x14000fc92  call    HbpTraceEvent
0x14000fc97  jmp     loc_14000FD71
0x14000fc9c  lea     rcx, [rsi+0D0h]; Mutex
0x14000fca3  xor     edx, edx; Level
0x14000fca5  call    cs:__imp_KeInitializeMutex
0x14000fcac  nop     dword ptr [rax+rax+00h]
0x14000fcb1  mov     ebx, 1
0x14000fcb6  mov     byte ptr [rsi+108h], 0
0x14000fcbd  mov     edx, ebx; Type
0x14000fcbf  mov     [rsi+110h], ebx
0x14000fcc5  lea     rcx, [rsi+128h]; Event
0x14000fccc  mov     qword ptr [rsi+118h], 0
0x14000fcd7  xor     r8d, r8d; State
0x14000fcda  mov     dword ptr [rsi+120h], 0
0x14000fce4  call    cs:__imp_KeInitializeEvent
0x14000fceb  nop     dword ptr [rax+rax+00h]
0x14000fcf0  lea     rax, [rsi+0A8h]
0x14000fcf7  mov     qword ptr [rsi+148h], 0FFFFFFFFFFFFFFFFh
0x14000fd02  mov     rcx, rsi; DeferredContext
0x14000fd05  mov     [rax+8], rax
0x14000fd09  mov     [rax], rax
0x14000fd0c  mov     [rsi+150h], ebx
0x14000fd12  mov     [rsi+0B8h], ebx
0x14000fd18  call    HbHvInitializeHypervisor
0x14000fd1d  mov     edi, eax
0x14000fd1f  test    eax, eax
0x14000fd21  jns     loc_14000FDB4
0x14000fd27  lea     r9, aHbhvinitialize; "HbHvInitializeHypervisor failed with 0x"...
0x14000fd2e  mov     dword ptr [rsp+68h+var_48], eax
0x14000fd32  mov     r8d, 140h
0x14000fd38  lea     rdx, aHbpnpstartdevi; "HbPnpStartDevice"
0x14000fd3f  xor     ecx, ecx
0x14000fd41  call    HbpTraceEvent
0x14000fd46  lea     rax, a1001116384Gite; "10011.16384.GitEnlistment(RnDcbldB).260"...
0x14000fd4d  mov     r8d, 171h
0x14000fd53  mov     [rsp+68h+var_40], rax
0x14000fd58  lea     r9, aHvserviceDevic; "HvService device start failed with 0x%x"...
0x14000fd5f  lea     rdx, aHbpnpstartdevi; "HbPnpStartDevice"
0x14000fd66  mov     dword ptr [rsp+68h+var_48], edi
0x14000fd6a  xor     ecx, ecx
0x14000fd6c  call    HbpTraceEvent
0x14000fd71  mov     rbx, [r15+40h]
0x14000fd75  xor     edx, edx; PriorityBoost
0x14000fd77  mov     rcx, r14; Irp
0x14000fd7a  mov     [r14+30h], edi
0x14000fd7e  call    cs:__imp_IofCompleteRequest
0x14000fd85  nop     dword ptr [rax+rax+00h]
0x14000fd8a  lea     rcx, [rbx+40h]; RemoveLock
0x14000fd8e  mov     r8d, 20h ; ' '; RemlockSize
0x14000fd94  mov     rdx, r14; Tag
0x14000fd97  call    cs:__imp_IoReleaseRemoveLockEx
0x14000fd9e  nop     dword ptr [rax+rax+00h]
0x14000fda3  mov     eax, edi
0x14000fda5  add     rsp, 38h
0x14000fda9  pop     r15
0x14000fdab  pop     r14
0x14000fdad  pop     r12
0x14000fdaf  pop     rdi
0x14000fdb0  pop     rsi
0x14000fdb1  pop     rbx
0x14000fdb2  retn
0x14000fdb4  mov     rcx, [rsi+10h]; PhysicalDeviceObject
0x14000fdb8  lea     r9, [rsi+20h]; SymbolicLinkName
0x14000fdbc  xor     r8d, r8d; ReferenceString
0x14000fdbf  lea     rdx, GUID_DEVINTERFACE_HVBOOT; InterfaceClassGuid
0x14000fdc6  call    cs:__imp_IoRegisterDeviceInterface
0x14000fdcd  nop     dword ptr [rax+rax+00h]
0x14000fdd2  mov     edi, eax
0x14000fdd4  test    eax, eax
0x14000fdd6  jns     short loc_14000FDFC
0x14000fdd8  lea     r9, aIoregisterdevi; "IoRegisterDeviceInterface failed with 0"...
0x14000fddf  mov     dword ptr [rsp+68h+var_48], eax
0x14000fde3  mov     r8d, 14Fh
0x14000fde9  lea     rdx, aHbpnpstartdevi; "HbPnpStartDevice"
0x14000fdf0  xor     ecx, ecx
0x14000fdf2  call    HbpTraceEvent
0x14000fdf7  jmp     loc_14000FD46
0x14000fdfc  mov     dl, bl; Enable
0x14000fdfe  lea     rcx, [rsi+20h]; SymbolicLinkName
0x14000fe02  call    cs:__imp_IoSetDeviceInterfaceState
0x14000fe09  nop     dword ptr [rax+rax+00h]
0x14000fe0e  mov     edi, eax
0x14000fe10  test    eax, eax
0x14000fe12  jns     short loc_14000FE38
0x14000fe14  lea     r9, aIosetdeviceint; "IoSetDeviceInterfaceState failed with 0"...
0x14000fe1b  mov     dword ptr [rsp+68h+var_48], eax
0x14000fe1f  mov     r8d, 15Ah
0x14000fe25  lea     rdx, aHbpnpstartdevi; "HbPnpStartDevice"
0x14000fe2c  xor     ecx, ecx
0x14000fe2e  call    HbpTraceEvent
0x14000fe33  jmp     loc_14000FD46
0x14000fe38  mov     rcx, [rsi]; DeviceObject
0x14000fe3b  mov     r8d, ebx; State
0x14000fe3e  mov     edx, ebx; Type
0x14000fe40  call    cs:__imp_PoSetPowerState
0x14000fe47  nop     dword ptr [rax+rax+00h]
0x14000fe4c  cmp     cs:qword_1400091D8, 0
0x14000fe54  jz      loc_14000FD46
0x14000fe5a  lea     rcx, stru_140009210; PerformanceFrequency
0x14000fe61  call    cs:__imp_KeQueryPerformanceCounter
0x14000fe68  nop     dword ptr [rax+rax+00h]
0x14000fe6d  mov     cs:qword_140009208, rax
0x14000fe74  mov     rdx, cs:qword_1400091D8
0x14000fe7b  test    rdx, rdx
0x14000fe7e  jz      short loc_14000FEA2
0x14000fe80  test    rax, rax
0x14000fe83  jz      short loc_14000FEA2
0x14000fe85  mov     rcx, qword ptr cs:stru_140009210
0x14000fe8c  test    rcx, rcx
0x14000fe8f  jz      short loc_14000FEA2
0x14000fe91  sub     rax, rdx
0x14000fe94  imul    rax, 3E8h
0x14000fe9b  cqo
0x14000fe9d  idiv    rcx
0x14000fea0  jmp     short loc_14000FEA4
0x14000fea2  xor     eax, eax
0x14000fea4  mov     [rsp+68h+var_40], rax
0x14000fea9  lea     r9, aHvserviceLoade; "HvService loaded. Version: %s, Loaded i"...
0x14000feb0  lea     rax, a1001116384Gite; "10011.16384.GitEnlistment(RnDcbldB).260"...
0x14000feb7  mov     r8d, 97h
0x14000febd  lea     rdx, aHbrecordphaset; "HbRecordPhaseTimestamp"
0x14000fec4  mov     [rsp+68h+var_48], rax
0x14000fec9  mov     ecx, 3
0x14000fece  call    HbpTraceEvent
0x14000fed3  mov     cs:HbDriverLastRecordedLifecyclePhase, 2
0x14000fedd  jmp     loc_14000FD71
```
