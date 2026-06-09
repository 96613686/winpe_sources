# MountMgrSiloArrival

- ea: `0x140001ebc`
- end: `0x140002138`
- name: `MountMgrSiloArrival`
- size: `636`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x1400147a0`

## callees

- `0x140001b30`
- `0x140001bec`
- `0x140001d04`
- `0x140001ebc`
- `0x140018da0`

## import_xrefs

- `ntoskrnl!PsGetJobSilo` at `0x140001f5b`
- `ntoskrnl!PsGetJobSilo` at `0x140001f5b`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140001f8d`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140001f8d`
- `ntoskrnl!PsJobType` at `0x140001f10`
- `ntoskrnl!ObfDereferenceObject` at `0x14000211e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000211e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002023`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002023`
- `ntoskrnl!IoDeleteDevice` at `0x1400020f6`
- `ntoskrnl!IoDeleteDevice` at `0x1400020f6`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140001f75`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140001f75`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140001f3a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140001f3a`
- `ntoskrnl!PsCreateSiloContext` at `0x14000206f`
- `ntoskrnl!PsCreateSiloContext` at `0x14000206f`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14000209a`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14000209a`
- `ntoskrnl!IoCreateDevice` at `0x140001fcc`
- `ntoskrnl!IoCreateDevice` at `0x140001fcc`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000210a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000210a`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400020bd`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400020bd`

## string_xrefs

- `0x140001f81`: `\Registry\Machine\System\MountedDevices`
- `0x140002013`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall MountMgrSiloArrival(struct _DEVICE_OBJECT *a1, __int64 a2)
{
  __int64 v2; // rax
  NTSTATUS JobSilo; // ebx
  void *v4; // rcx
  KPROCESSOR_MODE v5; // r9
  __int64 v6; // r14
  char v7; // si
  NTSTATUS v8; // eax
  PVOID v9; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp+30h] BYREF
  __int64 v13; // [rsp+88h] [rbp+38h] BYREF
  PDEVICE_OBJECT *v14; // [rsp+90h] [rbp+40h] BYREF
  PVOID Object; // [rsp+98h] [rbp+48h] BYREF

  DeviceObject = a1;
  v2 = *(_QWORD *)(a2 + 184);
  v13 = 0;
  DeviceObject = 0;
  v14 = 0;
  DestinationString = 0;
  if ( *(_DWORD *)(v2 + 16) < 8u || (v4 = **(void ***)(a2 + 24)) == 0 )
    return (unsigned int)-1073741811;
  v5 = *(_BYTE *)(a2 + 64);
  v6 = 0;
  v7 = 0;
  Object = 0;
  v8 = ObReferenceObjectByHandle(v4, 2u, (POBJECT_TYPE)PsJobType, v5, &Object, 0);
  v9 = Object;
  JobSilo = v8;
  if ( v8 < 0 || (JobSilo = PsGetJobSilo(Object, &v13), JobSilo < 0) )
  {
LABEL_15:
    if ( DeviceObject )
    {
      MountMgrFreeSiloDeviceExtension(DeviceObject->DeviceExtension);
      IoDeleteDevice(DeviceObject);
    }
    if ( !v7 )
      goto LABEL_19;
    goto LABEL_18;
  }
  v6 = PsAttachSiloToCurrentThread(v13);
  RtlCreateRegistryKey(0, (PWSTR)L"\\Registry\\Machine\\System\\MountedDevices");
  JobSilo = IoCreateDevice(gDeviceObject->DriverObject, 0x178u, &DeviceName, 0x12u, 0x100u, 0, &DeviceObject);
  if ( JobSilo >= 0 )
  {
    v7 = 1;
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\MountedDevices");
    JobSilo = MountMgrInitSiloDeviceExtension(gDeviceObject->DriverObject, DeviceObject, v13, &DestinationString);
    if ( JobSilo >= 0 )
    {
      JobSilo = PsCreateSiloContext(v13, 8, 1, MountMgrSiloContextCleanupCallback, &v14);
      if ( JobSilo >= 0 )
      {
        *v14 = DeviceObject;
        JobSilo = PsInsertPermanentSiloContext(v13, (unsigned int)gSiloSlot, v14);
        DeviceObject->Flags &= ~0x80u;
        DeviceObject = 0;
        PsDereferenceSiloContext(v14);
        if ( JobSilo >= 0 )
          GlobalCreateSymbolicLink((const UNICODE_STRING *)asc_140007068, (__int128 *)&DeviceName);
      }
    }
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 360);
  DeviceObject = 0;
LABEL_18:
  PsDetachSiloFromCurrentThread(v6);
LABEL_19:
  if ( v9 )
    ObfDereferenceObject(v9);
  return (unsigned int)JobSilo;
}

```

## disassembly

```asm
0x140001ebc  mov     [rsp-28h+arg_0], rcx
0x140001ec1  push    rbp
0x140001ec2  push    rbx
0x140001ec3  push    rsi
0x140001ec4  push    rdi
0x140001ec5  push    r14
0x140001ec7  mov     rbp, rsp
0x140001eca  sub     rsp, 50h
0x140001ece  mov     rax, [rdx+0B8h]
0x140001ed5  xorps   xmm0, xmm0
0x140001ed8  mov     [rbp+arg_8], 0
0x140001ee0  mov     [rbp+arg_0], 0
0x140001ee8  mov     [rbp+arg_10], 0
0x140001ef0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140001ef4  cmp     dword ptr [rax+10h], 8
0x140001ef8  jnb     short loc_140001F04
0x140001efa  mov     ebx, 0C000000Dh
0x140001eff  jmp     loc_14000212A
0x140001f04  mov     rax, [rdx+18h]
0x140001f08  mov     rcx, [rax]; Handle
0x140001f0b  test    rcx, rcx
0x140001f0e  jz      short loc_140001EFA
0x140001f10  mov     r8, cs:PsJobType
0x140001f17  lea     rax, [rbp+arg_18]
0x140001f1b  mov     r9b, [rdx+40h]; AccessMode
0x140001f1f  xor     r14d, r14d
0x140001f22  mov     [rsp+50h+HandleInformation], r14; HandleInformation
0x140001f27  xor     sil, sil
0x140001f2a  mov     [rbp+arg_18], r14
0x140001f2e  mov     r8, [r8]; ObjectType
0x140001f31  lea     edx, [r14+2]; DesiredAccess
0x140001f35  mov     [rsp+50h+Object], rax; Object
0x140001f3a  call    cs:__imp_ObReferenceObjectByHandle
0x140001f41  nop     dword ptr [rax+rax+00h]
0x140001f46  mov     rdi, [rbp+arg_18]
0x140001f4a  mov     ebx, eax
0x140001f4c  test    eax, eax
0x140001f4e  js      loc_1400020E0
0x140001f54  lea     rdx, [rbp+arg_8]
0x140001f58  mov     rcx, rdi
0x140001f5b  call    cs:__imp_PsGetJobSilo
0x140001f62  nop     dword ptr [rax+rax+00h]
0x140001f67  mov     ebx, eax
0x140001f69  test    eax, eax
0x140001f6b  js      loc_1400020E0
0x140001f71  mov     rcx, [rbp+arg_8]
0x140001f75  call    cs:__imp_PsAttachSiloToCurrentThread
0x140001f7c  nop     dword ptr [rax+rax+00h]
0x140001f81  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x140001f88  xor     ecx, ecx; RelativeTo
0x140001f8a  mov     r14, rax
0x140001f8d  call    cs:__imp_RtlCreateRegistryKey
0x140001f94  nop     dword ptr [rax+rax+00h]
0x140001f99  mov     rcx, cs:gDeviceObject
0x140001fa0  lea     rax, [rbp+arg_0]
0x140001fa4  mov     [rsp+50h+DeviceObject], rax; DeviceObject
0x140001fa9  lea     r8, DeviceName; DeviceName
0x140001fb0  mov     byte ptr [rsp+50h+HandleInformation], sil; Exclusive
0x140001fb5  mov     r9d, 12h; DeviceType
0x140001fbb  mov     edx, 178h; DeviceExtensionSize
0x140001fc0  mov     dword ptr [rsp+50h+Object], 100h; DeviceCharacteristics
0x140001fc8  mov     rcx, [rcx+8]; DriverObject
0x140001fcc  call    cs:__imp_IoCreateDevice
0x140001fd3  nop     dword ptr [rax+rax+00h]
0x140001fd8  mov     ebx, eax
0x140001fda  test    eax, eax
0x140001fdc  jns     short loc_140002013
0x140001fde  mov     rcx, cs:WPP_GLOBAL_Control
0x140001fe5  lea     rax, WPP_GLOBAL_Control
0x140001fec  cmp     rcx, rax
0x140001fef  jz      short loc_140002006
0x140001ff1  mov     eax, [rcx+2Ch]
0x140001ff4  test    al, 4
0x140001ff6  jz      short loc_140002006
0x140001ff8  mov     rcx, [rcx+18h]
0x140001ffc  mov     edx, 168h
0x140002001  call    WPP_SF_
0x140002006  mov     [rbp+arg_0], 0
0x14000200e  jmp     loc_140002107
0x140002013  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000201a  mov     esi, 1
0x14000201f  lea     rcx, [rbp+DestinationString]; DestinationString
0x140002023  call    cs:__imp_RtlInitUnicodeString
0x14000202a  nop     dword ptr [rax+rax+00h]
0x14000202f  mov     rcx, cs:gDeviceObject
0x140002036  lea     r9, [rbp+DestinationString]
0x14000203a  mov     r8, [rbp+arg_8]
0x14000203e  mov     rdx, [rbp+arg_0]
0x140002042  mov     rcx, [rcx+8]
0x140002046  call    MountMgrInitSiloDeviceExtension
0x14000204b  mov     ebx, eax
0x14000204d  test    eax, eax
0x14000204f  js      loc_1400020E0
0x140002055  mov     rcx, [rbp+arg_8]
0x140002059  lea     rax, [rbp+arg_10]
0x14000205d  lea     r9, MountMgrSiloContextCleanupCallback
0x140002064  mov     [rsp+50h+Object], rax
0x140002069  mov     r8d, esi
0x14000206c  lea     edx, [rsi+7]
0x14000206f  call    cs:__imp_PsCreateSiloContext
0x140002076  nop     dword ptr [rax+rax+00h]
0x14000207b  mov     ebx, eax
0x14000207d  test    eax, eax
0x14000207f  js      short loc_1400020E0
0x140002081  mov     rcx, [rbp+arg_0]
0x140002085  mov     rax, [rbp+arg_10]
0x140002089  mov     [rax], rcx
0x14000208c  mov     r8, [rbp+arg_10]
0x140002090  mov     edx, cs:gSiloSlot
0x140002096  mov     rcx, [rbp+arg_8]
0x14000209a  call    cs:__imp_PsInsertPermanentSiloContext
0x1400020a1  nop     dword ptr [rax+rax+00h]
0x1400020a6  mov     ebx, eax
0x1400020a8  mov     rax, [rbp+arg_0]
0x1400020ac  btr     dword ptr [rax+30h], 7
0x1400020b1  mov     rcx, [rbp+arg_10]
0x1400020b5  mov     [rbp+arg_0], 0
0x1400020bd  call    cs:__imp_PsDereferenceSiloContext
0x1400020c4  nop     dword ptr [rax+rax+00h]
0x1400020c9  test    ebx, ebx
0x1400020cb  js      short loc_1400020E0
0x1400020cd  lea     rdx, DeviceName
0x1400020d4  lea     rcx, asc_140007068; ":<"
0x1400020db  call    GlobalCreateSymbolicLink
0x1400020e0  mov     rcx, [rbp+arg_0]
0x1400020e4  test    rcx, rcx
0x1400020e7  jz      short loc_140002102
0x1400020e9  mov     rcx, [rcx+40h]
0x1400020ed  call    MountMgrFreeSiloDeviceExtension
0x1400020f2  mov     rcx, [rbp+arg_0]; DeviceObject
0x1400020f6  call    cs:__imp_IoDeleteDevice
0x1400020fd  nop     dword ptr [rax+rax+00h]
0x140002102  test    sil, sil
0x140002105  jz      short loc_140002116
0x140002107  mov     rcx, r14
0x14000210a  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140002111  nop     dword ptr [rax+rax+00h]
0x140002116  test    rdi, rdi
0x140002119  jz      short loc_14000212A
0x14000211b  mov     rcx, rdi; Object
0x14000211e  call    cs:__imp_ObfDereferenceObject
0x140002125  nop     dword ptr [rax+rax+00h]
0x14000212a  mov     eax, ebx
0x14000212c  add     rsp, 50h
0x140002130  pop     r14
0x140002132  pop     rdi
0x140002133  pop     rsi
0x140002134  pop     rbx
0x140002135  pop     rbp
0x140002136  retn
```
