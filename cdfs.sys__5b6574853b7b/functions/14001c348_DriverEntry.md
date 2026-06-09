# DriverEntry

- ea: `0x14001c348`
- end: `0x14001c4f8`
- name: `DriverEntry`
- size: `432`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14001c010`

## callees

- `0x140003300`
- `0x14001c078`
- `0x14001c348`
- `0x14001c500`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001c38f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001c38f`
- `ntoskrnl!IoCreateDevice` at `0x14001c3be`
- `ntoskrnl!IoCreateDevice` at `0x14001c3be`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x14001c466`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x14001c466`
- `ntoskrnl!IoDeleteDevice` at `0x14001c47c`
- `ntoskrnl!IoDeleteDevice` at `0x14001c4a2`
- `ntoskrnl!IoDeleteDevice` at `0x14001c47c`
- `ntoskrnl!IoDeleteDevice` at `0x14001c4a2`
- `ntoskrnl!IoRegisterFileSystem` at `0x14001c4bf`
- `ntoskrnl!IoRegisterFileSystem` at `0x14001c4bf`
- `ntoskrnl!ObfReferenceObject` at `0x14001c4cf`
- `ntoskrnl!ObfReferenceObject` at `0x14001c4cf`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  int v4; // edi
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-39h] BYREF
  _FS_FILTER_CALLBACKS Callbacks; // [rsp+50h] [rbp-29h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+F0h] [rbp+77h] BYREF

  DeviceObject = 0;
  DestinationString = 0;
  memset(&Callbacks, 0, sizeof(Callbacks));
  RtlInitUnicodeString(&DestinationString, L"\\Cdfs");
  result = IoCreateDevice(DriverObject, 0, &DestinationString, 3u, 0, 0, &DeviceObject);
  if ( result >= 0 )
  {
    DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[17] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[13] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[12] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[6] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&CdFsdDispatch;
    DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)&CdFastIoDispatch;
    memset(&Callbacks, 0, sizeof(Callbacks));
    Callbacks.SizeOfFsFilterCallbacks = 120;
    Callbacks.PreAcquireForSectionSynchronization = (PFS_FILTER_CALLBACK)CdFilterCallbackAcquireForCreateSection;
    v4 = FsRtlRegisterFileSystemFilterCallbacks(DriverObject, &Callbacks);
    if ( v4 >= 0 )
    {
      v5 = CdInitializeGlobalData(DriverObject, DeviceObject);
      if ( v5 >= 0 )
      {
        DeviceObject->Flags |= 0x10000u;
        IoRegisterFileSystem(DeviceObject);
        ObfReferenceObject(DeviceObject);
        CdInitializeTelemetry();
        return 0;
      }
      else
      {
        IoDeleteDevice(DeviceObject);
        return v5;
      }
    }
    else
    {
      IoDeleteDevice(DeviceObject);
      return v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001c348  mov     [rsp-8+arg_0], rbx
0x14001c34d  mov     [rsp-8+arg_8], rdi
0x14001c352  push    rbp
0x14001c353  lea     rbp, [rsp-57h]
0x14001c358  sub     rsp, 0D0h
0x14001c35f  mov     rbx, rcx
0x14001c362  mov     [rbp+57h+arg_10], 0
0x14001c36a  xorps   xmm0, xmm0
0x14001c36d  lea     rcx, [rbp+57h+Callbacks]; void *
0x14001c371  mov     edi, 78h ; 'x'
0x14001c376  xor     edx, edx; Val
0x14001c378  mov     r8d, edi; Size
0x14001c37b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001c37f  call    memset
0x14001c384  lea     rdx, SourceString; "\\Cdfs"
0x14001c38b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001c38f  call    cs:__imp_RtlInitUnicodeString
0x14001c396  nop     dword ptr [rax+rax+00h]
0x14001c39b  lea     rax, [rbp+57h+arg_10]
0x14001c39f  xor     edx, edx; DeviceExtensionSize
0x14001c3a1  mov     [rsp+0D0h+DeviceObject], rax; DeviceObject
0x14001c3a6  lea     r9d, [rdi-75h]; DeviceType
0x14001c3aa  mov     [rsp+0D0h+Exclusive], 0; Exclusive
0x14001c3af  lea     r8, [rbp+57h+DestinationString]; DeviceName
0x14001c3b3  mov     rcx, rbx; DriverObject
0x14001c3b6  mov     [rsp+0D0h+DeviceCharacteristics], 0; DeviceCharacteristics
0x14001c3be  call    cs:__imp_IoCreateDevice
0x14001c3c5  nop     dword ptr [rax+rax+00h]
0x14001c3ca  test    eax, eax
0x14001c3cc  js      loc_14001C4E2
0x14001c3d2  lea     rax, CdFsdDispatch
0x14001c3d9  mov     r8d, edi; Size
0x14001c3dc  mov     [rbx+0F0h], rax
0x14001c3e3  lea     rcx, [rbp+57h+Callbacks]; void *
0x14001c3e7  mov     [rbx+148h], rax
0x14001c3ee  xor     edx, edx; Val
0x14001c3f0  mov     [rbx+100h], rax
0x14001c3f7  mov     [rbx+0F8h], rax
0x14001c3fe  mov     [rbx+0E0h], rax
0x14001c405  mov     [rbx+0D8h], rax
0x14001c40c  mov     [rbx+0D0h], rax
0x14001c413  mov     [rbx+0C0h], rax
0x14001c41a  mov     [rbx+0A0h], rax
0x14001c421  mov     [rbx+98h], rax
0x14001c428  mov     [rbx+90h], rax
0x14001c42f  mov     [rbx+88h], rax
0x14001c436  mov     [rbx+80h], rax
0x14001c43d  mov     [rbx+70h], rax
0x14001c441  lea     rax, CdFastIoDispatch
0x14001c448  mov     [rbx+50h], rax
0x14001c44c  call    memset
0x14001c451  lea     rax, CdFilterCallbackAcquireForCreateSection
0x14001c458  mov     [rbp+57h+Callbacks.SizeOfFsFilterCallbacks], edi
0x14001c45b  lea     rdx, [rbp+57h+Callbacks]; Callbacks
0x14001c45f  mov     [rbp+57h+Callbacks.PreAcquireForSectionSynchronization], rax
0x14001c463  mov     rcx, rbx; FilterDriverObject
0x14001c466  call    cs:__imp_FsRtlRegisterFileSystemFilterCallbacks
0x14001c46d  nop     dword ptr [rax+rax+00h]
0x14001c472  mov     edi, eax
0x14001c474  test    eax, eax
0x14001c476  jns     short loc_14001C48C
0x14001c478  mov     rcx, [rbp+57h+arg_10]; DeviceObject
0x14001c47c  call    cs:__imp_IoDeleteDevice
0x14001c483  nop     dword ptr [rax+rax+00h]
0x14001c488  mov     eax, edi
0x14001c48a  jmp     short loc_14001C4E2
0x14001c48c  mov     rdx, [rbp+57h+arg_10]
0x14001c490  mov     rcx, rbx
0x14001c493  call    CdInitializeGlobalData
0x14001c498  mov     ebx, eax
0x14001c49a  test    eax, eax
0x14001c49c  jns     short loc_14001C4B2
0x14001c49e  mov     rcx, [rbp+57h+arg_10]; DeviceObject
0x14001c4a2  call    cs:__imp_IoDeleteDevice
0x14001c4a9  nop     dword ptr [rax+rax+00h]
0x14001c4ae  mov     eax, ebx
0x14001c4b0  jmp     short loc_14001C4E2
0x14001c4b2  mov     rax, [rbp+57h+arg_10]
0x14001c4b6  bts     dword ptr [rax+30h], 10h
0x14001c4bb  mov     rcx, [rbp+57h+arg_10]; DeviceObject
0x14001c4bf  call    cs:__imp_IoRegisterFileSystem
0x14001c4c6  nop     dword ptr [rax+rax+00h]
0x14001c4cb  mov     rcx, [rbp+57h+arg_10]; Object
0x14001c4cf  call    cs:__imp_ObfReferenceObject
0x14001c4d6  nop     dword ptr [rax+rax+00h]
0x14001c4db  call    CdInitializeTelemetry
0x14001c4e0  xor     eax, eax
0x14001c4e2  lea     r11, [rsp+0D0h+var_s0]
0x14001c4ea  mov     rbx, [r11+10h]
0x14001c4ee  mov     rdi, [r11+18h]
0x14001c4f2  mov     rsp, r11
0x14001c4f5  pop     rbp
0x14001c4f6  retn
```
