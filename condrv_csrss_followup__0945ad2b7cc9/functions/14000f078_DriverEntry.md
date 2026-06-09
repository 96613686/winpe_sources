# DriverEntry

- ea: `0x14000f078`
- end: `0x14000f1c6`
- name: `DriverEntry`
- size: `334`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000f010`

## callees

- `0x14000f078`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x14000f18a`
- `ntoskrnl!IoCreateDevice` at `0x14000f18a`
- `ntoskrnl!RtlRunOnceInitialize` at `0x14000f0c6`
- `ntoskrnl!RtlRunOnceInitialize` at `0x14000f0c6`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING DeviceName; // [rsp+40h] [rbp-18h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+60h] [rbp+8h] BYREF

  DeviceObject = 0;
  DeviceName.Buffer = L"\\Device\\ConDrv";
  *(_QWORD *)&DeviceName.Length = 1966108;
  qword_140005188 = (__int64)&CdpServerList;
  CdpServerList = (__int64)&CdpServerList;
  CdpServerListLock = 0;
  RtlRunOnceInitialize(&CdpDisplayInitialized);
  DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)CdpFastIoDispatchTable;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)CdpUnload;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)CdpDispatchCreate;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)CdpDispatchWrite;
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)CdpDispatchRead;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)CdpDispatchCleanup;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)CdpDispatchClose;
  DriverObject->MajorFunction[21] = (PDRIVER_DISPATCH)CdpDispatchSetSecurity;
  DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)CdpDispatchFlushBuffers;
  DriverObject->MajorFunction[20] = (PDRIVER_DISPATCH)CdpDispatchQuerySecurity;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)CdpDispatchDeviceControl;
  result = IoCreateDevice(DriverObject, 0, &DeviceName, 0x50u, 0x20000u, 0, &DeviceObject);
  if ( result >= 0 )
  {
    CdDeviceObject = (__int64)DeviceObject;
    DeviceObject->StackSize = 2;
    DeviceObject->Flags |= 0x10u;
    DeviceObject->Flags &= ~0x80u;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000f078  push    rbx
0x14000f07a  sub     rsp, 50h
0x14000f07e  lea     rax, aDeviceCondrv; "\\Device\\ConDrv"
0x14000f085  mov     [rsp+58h+arg_0], 0
0x14000f08e  mov     [rsp+58h+DeviceName.Buffer], rax
0x14000f093  mov     rbx, rcx
0x14000f096  lea     rax, CdpServerList
0x14000f09d  mov     qword ptr [rsp+58h+DeviceName.Length], 1E001Ch
0x14000f0a6  lea     rcx, CdpDisplayInitialized; RunOnce
0x14000f0ad  mov     cs:qword_140005188, rax
0x14000f0b4  mov     cs:CdpServerList, rax
0x14000f0bb  mov     cs:CdpServerListLock, 0
0x14000f0c6  call    cs:__imp_RtlRunOnceInitialize
0x14000f0cd  nop     dword ptr [rax+rax+00h]
0x14000f0d2  lea     rax, CdpFastIoDispatchTable
0x14000f0d9  mov     r9d, 50h ; 'P'; DeviceType
0x14000f0df  mov     [rbx+50h], rax
0x14000f0e3  lea     r8, [rsp+58h+DeviceName]; DeviceName
0x14000f0e8  lea     rax, CdpUnload
0x14000f0ef  xor     edx, edx; DeviceExtensionSize
0x14000f0f1  mov     [rbx+68h], rax
0x14000f0f5  mov     rcx, rbx; DriverObject
0x14000f0f8  lea     rax, CdpDispatchCreate
0x14000f0ff  mov     [rbx+70h], rax
0x14000f103  lea     rax, CdpDispatchWrite
0x14000f10a  mov     [rbx+90h], rax
0x14000f111  lea     rax, CdpDispatchRead
0x14000f118  mov     [rbx+88h], rax
0x14000f11f  lea     rax, CdpDispatchCleanup
0x14000f126  mov     [rbx+100h], rax
0x14000f12d  lea     rax, CdpDispatchClose
0x14000f134  mov     [rbx+80h], rax
0x14000f13b  lea     rax, CdpDispatchSetSecurity
0x14000f142  mov     [rbx+118h], rax
0x14000f149  lea     rax, CdpDispatchFlushBuffers
0x14000f150  mov     [rbx+0B8h], rax
0x14000f157  lea     rax, CdpDispatchQuerySecurity
0x14000f15e  mov     [rbx+110h], rax
0x14000f165  lea     rax, CdpDispatchDeviceControl
0x14000f16c  mov     [rbx+0E0h], rax
0x14000f173  lea     rax, [rsp+58h+arg_0]
0x14000f178  mov     [rsp+58h+DeviceObject], rax; DeviceObject
0x14000f17d  mov     [rsp+58h+Exclusive], 0; Exclusive
0x14000f182  mov     [rsp+58h+DeviceCharacteristics], 20000h; DeviceCharacteristics
0x14000f18a  call    cs:__imp_IoCreateDevice
0x14000f191  nop     dword ptr [rax+rax+00h]
0x14000f196  test    eax, eax
0x14000f198  js      short loc_14000F1BF
0x14000f19a  mov     rax, [rsp+58h+arg_0]
0x14000f19f  mov     cs:CdDeviceObject, rax
0x14000f1a6  mov     byte ptr [rax+4Ch], 2
0x14000f1aa  mov     rax, [rsp+58h+arg_0]
0x14000f1af  or      dword ptr [rax+30h], 10h
0x14000f1b3  mov     rax, [rsp+58h+arg_0]
0x14000f1b8  btr     dword ptr [rax+30h], 7
0x14000f1bd  xor     eax, eax
0x14000f1bf  add     rsp, 50h
0x14000f1c3  pop     rbx
0x14000f1c4  retn
```
