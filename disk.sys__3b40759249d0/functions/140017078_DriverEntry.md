# DriverEntry

- ea: `0x140017078`
- end: `0x14001731f`
- name: `DriverEntry`
- size: `679`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140017010`

## callees

- `0x140003bdc`
- `0x140005bf0`
- `0x140006000`
- `0x14000fcf0`
- `0x14000fd84`
- `0x140010dec`
- `0x140017078`

## import_xrefs

- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1400172ec`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1400172ec`
- `CLASSPNP!ClassInitialize` at `0x140017276`
- `CLASSPNP!ClassInitialize` at `0x140017276`
- `CLASSPNP!ClassInitializeEx` at `0x1400172a7`
- `CLASSPNP!ClassInitializeEx` at `0x1400172ca`
- `CLASSPNP!ClassInitializeEx` at `0x1400172a7`
- `CLASSPNP!ClassInitializeEx` at `0x1400172ca`
- `CLASSPNP!ClassSpinDownPowerHandler` at `0x1400171aa`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  NTSTATUS v8; // ebx
  int v10; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD Data[2]; // [rsp+28h] [rbp-D8h] BYREF
  __int64 (__fastcall *Data_8)(); // [rsp+30h] [rbp-D0h]
  __int64 v13; // [rsp+38h] [rbp-C8h]
  _CLASS_INIT_DATA InitializationData; // [rsp+40h] [rbp-C0h] BYREF
  GUID Guid; // [rsp+1D0h] [rbp+D0h] BYREF
  GUID v16; // [rsp+1E0h] [rbp+E0h] BYREF

  memset(&InitializationData, 0, sizeof(InitializationData));
  Guid.Data1 = 14895889;
  v13 = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_wppCtlGuid;
  Data[1] = 0;
  *(_DWORD *)&Guid.Data2 = 1195713604;
  *(_DWORD *)Guid.Data4 = 23215525;
  *(_DWORD *)&Guid.Data4[4] = -142422784;
  v16.Data1 = 172505409;
  *(_DWORD *)&v16.Data2 = 1333509629;
  *(_DWORD *)v16.Data4 = -489777730;
  *(_DWORD *)&v16.Data4[4] = 201922210;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport(v5, v4, v6, v7);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  InitializationData.InitializationDataSize = 392;
  InitializationData.FdoData.ClassInitDevice = (PCLASS_INIT_DEVICE)DiskInitFdo;
  InitializationData.FdoData.DeviceExtensionSize = 1744;
  InitializationData.FdoData.ClassStartDevice = (PCLASS_START_DEVICE)DiskStartFdo;
  InitializationData.FdoData.ClassStopDevice = (PCLASS_STOP_DEVICE)DiskStopDevice;
  InitializationData.FdoData.ClassRemoveDevice = (PCLASS_REMOVE_DEVICE)DiskRemoveDevice;
  InitializationData.FdoData.ClassPowerDevice = ClassSpinDownPowerHandler;
  InitializationData.FdoData.ClassError = (PCLASS_ERROR)DiskFdoProcessError;
  InitializationData.FdoData.ClassReadWriteVerification = (PCLASS_READ_WRITE)DiskReadWriteVerification;
  InitializationData.FdoData.ClassDeviceControl = (PCLASS_DEVICE_CONTROL)DiskDeviceControl;
  InitializationData.FdoData.ClassShutdownFlush = (PCLASS_SHUTDOWN_FLUSH)DiskShutdownFlush;
  InitializationData.FdoData.ClassWmiInfo.GuidRegInfo = (PGUIDREGINFO)DiskWmiFdoGuidList;
  InitializationData.FdoData.ClassWmiInfo.ClassQueryWmiRegInfo = (PCLASS_QUERY_WMI_REGINFO)DiskFdoQueryWmiRegInfo;
  InitializationData.FdoData.ClassWmiInfo.ClassQueryWmiDataBlock = (PCLASS_QUERY_WMI_DATABLOCK)DiskFdoQueryWmiDataBlock;
  InitializationData.FdoData.ClassWmiInfo.ClassSetWmiDataBlock = (PCLASS_SET_WMI_DATABLOCK)DiskFdoSetWmiDataBlock;
  InitializationData.FdoData.ClassWmiInfo.ClassSetWmiDataItem = (PCLASS_SET_WMI_DATAITEM)DiskFdoSetWmiDataItem;
  InitializationData.FdoData.ClassWmiInfo.ClassExecuteWmiMethod = (PCLASS_EXECUTE_WMI_METHOD)DiskFdoExecuteWmiMethod;
  InitializationData.FdoData.ClassWmiInfo.ClassWmiFunctionControl = (PCLASS_WMI_FUNCTION_CONTROL)DiskWmiFunctionControl;
  InitializationData.ClassAddDevice = (PCLASS_ADD_DEVICE)DiskAddDevice;
  InitializationData.ClassUnload = (PCLASS_UNLOAD)DiskUnload;
  InitializationData.FdoData.DeviceType = 7;
  InitializationData.FdoData.DeviceCharacteristics = 256;
  InitializationData.FdoData.ClassCreateClose = 0;
  InitializationData.FdoData.ClassWmiInfo.GuidCount = 7;
  DiskInitializeReregistration();
  Data[0] = 24;
  v8 = ClassInitialize(DriverObject, RegistryPath, &InitializationData);
  Data_8 = DiskFdoQueryWmiRegInfoEx;
  ClassInitializeEx(DriverObject, &Guid, Data);
  v10 = 3;
  ClassInitializeEx(DriverObject, &v16, &v10);
  McGenEventRegister_EtwRegister();
  if ( v8 >= 0 )
    IoRegisterDriverReinitialization(DriverObject, DiskDriverReinitialization, 0);
  return v8;
}

```

## disassembly

```asm
0x140017078  mov     [rsp-8+arg_10], rbx
0x14001707d  mov     [rsp-8+arg_18], rdi
0x140017082  push    rbp
0x140017083  lea     rbp, [rsp-100h]
0x14001708b  sub     rsp, 200h
0x140017092  mov     rax, cs:__security_cookie
0x140017099  xor     rax, rsp
0x14001709c  mov     [rbp+100h+var_10], rax
0x1400170a3  mov     rbx, rdx
0x1400170a6  mov     rdi, rcx
0x1400170a9  xor     edx, edx; Val
0x1400170ab  lea     rcx, [rsp+200h+InitializationData]; void *
0x1400170b0  mov     r8d, 188h; Size
0x1400170b6  call    memset
0x1400170bb  xor     eax, eax
0x1400170bd  mov     [rbp+100h+Guid.Data1], 0E34B11h
0x1400170c7  mov     [rsp+200h+var_1C8], rax
0x1400170cc  xorps   xmm0, xmm0
0x1400170cf  mov     [rsp+200h+var_1E0], eax
0x1400170d3  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x1400170da  lea     rax, WPP_ThisDir_CTLGUID_wppCtlGuid
0x1400170e1  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400170e8  movups  [rsp+200h+Data], xmm0
0x1400170ed  mov     dword ptr [rbp+100h+Guid.Data2], 47452444h
0x1400170f7  mov     dword ptr [rbp+100h+Guid.Data4], 1623DA5h
0x140017101  mov     dword ptr [rbp+100h+Guid.Data4+4], 0F782CD00h
0x14001710b  mov     [rbp+100h+var_20.Data1], 0A483941h
0x140017115  mov     dword ptr [rbp+100h+var_20.Data2], 4F7BBDFDh
0x14001711f  mov     dword ptr [rbp+100h+var_20.Data4], 0E2CE95BEh
0x140017129  mov     dword ptr [rbp+100h+var_20.Data4+4], 0C0916A2h
0x140017133  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14001713e  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x140017149  mov     cs:WPP_MAIN_CB.Timer, 1
0x140017154  call    WppLoadTracingSupport
0x140017159  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x140017164  call    WppInitKm
0x140017169  lea     rax, DiskInitFdo
0x140017170  mov     [rsp+200h+InitializationData.InitializationDataSize], 188h
0x140017178  mov     [rbp+100h+InitializationData.FdoData.ClassInitDevice], rax
0x14001717c  mov     ecx, 7
0x140017181  lea     rax, DiskStartFdo
0x140017188  mov     [rsp+200h+InitializationData.FdoData.DeviceExtensionSize], 6D0h
0x140017190  mov     [rbp+100h+InitializationData.FdoData.ClassStartDevice], rax
0x140017194  lea     rax, DiskStopDevice
0x14001719b  mov     [rbp+100h+InitializationData.FdoData.ClassStopDevice], rax
0x14001719f  lea     rax, DiskRemoveDevice
0x1400171a6  mov     [rbp+100h+InitializationData.FdoData.ClassRemoveDevice], rax
0x1400171aa  mov     rax, cs:__imp_ClassSpinDownPowerHandler
0x1400171b1  mov     [rbp+100h+InitializationData.FdoData.ClassPowerDevice], rax
0x1400171b5  lea     rax, DiskFdoProcessError
0x1400171bc  mov     [rsp+200h+InitializationData.FdoData.ClassError], rax
0x1400171c1  lea     rax, DiskReadWriteVerification
0x1400171c8  mov     [rsp+200h+InitializationData.FdoData.ClassReadWriteVerification], rax
0x1400171cd  lea     rax, DiskDeviceControl
0x1400171d4  mov     [rsp+200h+InitializationData.FdoData.ClassDeviceControl], rax
0x1400171d9  lea     rax, DiskShutdownFlush
0x1400171e0  mov     [rsp+200h+InitializationData.FdoData.ClassShutdownFlush], rax
0x1400171e5  lea     rax, DiskWmiFdoGuidList
0x1400171ec  mov     [rbp+100h+InitializationData.FdoData.ClassWmiInfo.GuidRegInfo], rax
0x1400171f0  lea     rax, DiskFdoQueryWmiRegInfo
0x1400171f7  mov     [rbp+100h+InitializationData.FdoData.ClassWmiInfo.ClassQueryWmiRegInfo], rax
0x1400171fb  lea     rax, DiskFdoQueryWmiDataBlock
0x140017202  mov     [rbp+100h+InitializationData.FdoData.ClassWmiInfo.ClassQueryWmiDataBlock], rax
0x140017206  lea     rax, DiskFdoSetWmiDataBlock
0x14001720d  mov     [rbp+100h+InitializationData.FdoData.ClassWmiInfo.ClassSetWmiDataBlock], rax
0x140017211  lea     rax, DiskFdoSetWmiDataItem
0x140017218  mov     [rbp+100h+InitializationData.FdoData.ClassWmiInfo.ClassSetWmiDataItem], rax
0x14001721c  lea     rax, DiskFdoExecuteWmiMethod
0x140017223  mov     [rbp+100h+InitializationData.FdoData.ClassWmiInfo.ClassExecuteWmiMethod], rax
0x140017227  lea     rax, DiskWmiFunctionControl
0x14001722e  mov     [rbp+100h+InitializationData.FdoData.ClassWmiInfo.ClassWmiFunctionControl], rax
0x140017232  lea     rax, DiskAddDevice
0x140017239  mov     [rbp+100h+InitializationData.ClassAddDevice], rax
0x140017240  lea     rax, DiskUnload
0x140017247  mov     [rbp+100h+InitializationData.ClassUnload], rax
0x14001724e  mov     [rsp+200h+InitializationData.FdoData.DeviceType], ecx
0x140017252  mov     [rsp+200h+InitializationData.FdoData.DeviceCharacteristics], 100h
0x14001725a  mov     [rsp+200h+InitializationData.FdoData.ClassCreateClose], 0
0x140017263  mov     [rbp+100h+InitializationData.FdoData.ClassWmiInfo.GuidCount], ecx
0x140017266  call    DiskInitializeReregistration
0x14001726b  lea     r8, [rsp+200h+InitializationData]; InitializationData
0x140017270  mov     rdx, rbx; Argument2
0x140017273  mov     rcx, rdi; Argument1
0x140017276  call    cs:__imp_ClassInitialize
0x14001727d  nop     dword ptr [rax+rax+00h]
0x140017282  lea     r8, [rsp+200h+Data]; Data
0x140017287  mov     dword ptr [rsp+200h+Data], 18h
0x14001728f  mov     ebx, eax
0x140017291  lea     rdx, [rbp+100h+Guid]; Guid
0x140017298  lea     rax, DiskFdoQueryWmiRegInfoEx
0x14001729f  mov     rcx, rdi; DriverObject
0x1400172a2  mov     qword ptr [rsp+200h+Data+8], rax
0x1400172a7  call    cs:__imp_ClassInitializeEx
0x1400172ae  nop     dword ptr [rax+rax+00h]
0x1400172b3  lea     r8, [rsp+200h+var_1E0]; Data
0x1400172b8  mov     [rsp+200h+var_1E0], 3
0x1400172c0  lea     rdx, [rbp+100h+var_20]; Guid
0x1400172c7  mov     rcx, rdi; DriverObject
0x1400172ca  call    cs:__imp_ClassInitializeEx
0x1400172d1  nop     dword ptr [rax+rax+00h]
0x1400172d6  call    McGenEventRegister_EtwRegister
0x1400172db  test    ebx, ebx
0x1400172dd  js      short loc_1400172F8
0x1400172df  xor     r8d, r8d; Context
0x1400172e2  lea     rdx, DiskDriverReinitialization; DriverReinitializationRoutine
0x1400172e9  mov     rcx, rdi; DriverObject
0x1400172ec  call    cs:__imp_IoRegisterDriverReinitialization
0x1400172f3  nop     dword ptr [rax+rax+00h]
0x1400172f8  mov     eax, ebx
0x1400172fa  mov     rcx, [rbp+100h+var_10]
0x140017301  xor     rcx, rsp; StackCookie
0x140017304  call    __security_check_cookie
0x140017309  lea     r11, [rsp+200h+var_s0]
0x140017311  mov     rbx, [r11+20h]
0x140017315  mov     rdi, [r11+28h]
0x140017319  mov     rsp, r11
0x14001731c  pop     rbp
0x14001731d  retn
```
