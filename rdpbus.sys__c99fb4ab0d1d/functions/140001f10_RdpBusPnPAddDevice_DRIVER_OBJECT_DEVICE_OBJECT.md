# RdpBusPnPAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)

- ea: `0x140001f10`
- end: `0x1400020ac`
- name: `?RdpBusPnPAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140001f10`
- `0x1400020b4`
- `0x1400020e4`
- `0x140002520`
- `0x140009120`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140001f75`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001f8c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001f75`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001f8c`
- `ntoskrnl!IoDeleteDevice` at `0x14000206c`
- `ntoskrnl!IoDeleteDevice` at `0x14000206c`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14000201f`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14000201f`

## pseudocode

```c
__int64 __fastcall RdpBusPnPAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  ULONG v4; // edx
  ULONG v5; // r9d
  NTSTATUS v6; // eax
  unsigned int v7; // edi
  _QWORD *DeviceExtension; // rbx
  PDEVICE_OBJECT v9; // rax
  ULONG v11; // [rsp+20h] [rbp-29h]
  BOOLEAN v12; // [rsp+28h] [rbp-21h]
  PDEVICE_OBJECT SourceDevice; // [rsp+50h] [rbp+7h] BYREF
  UNICODE_STRING DefaultSDDLString; // [rsp+58h] [rbp+Fh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp+1Fh] BYREF
  GUID DeviceClassGuid; // [rsp+78h] [rbp+2Fh] BYREF

  SourceDevice = 0;
  DeviceClassGuid.Data1 = -1545392710;
  *(_DWORD *)&DeviceClassGuid.Data2 = 1326955145;
  *(_DWORD *)DeviceClassGuid.Data4 = 19760771;
  *(_DWORD *)&DeviceClassGuid.Data4[4] = -858457305;
  DestinationString = 0;
  DefaultSDDLString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\RdpBus");
  RtlInitUnicodeString(&DefaultSDDLString, L"D:P(A;;GA;;;SY)");
  v6 = WdmlibIoCreateDeviceSecure(
         DriverObject,
         v4,
         &DestinationString,
         v5,
         v11,
         v12,
         &DefaultSDDLString,
         &DeviceClassGuid,
         &SourceDevice);
  v7 = v6;
  if ( v6 >= 0 )
  {
    SourceDevice->Flags |= 4u;
    DeviceExtension = SourceDevice->DeviceExtension;
    *DeviceExtension = 0;
    v9 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
    *DeviceExtension = v9;
    if ( v9 )
    {
      RDPDYN_PDO = TargetDevice;
      SourceDevice->Flags &= ~0x80u;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
      SourceDevice->Flags &= ~0x80u;
      IoDeleteDevice(SourceDevice);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids, (unsigned int)v6);
  }
  return v7;
}

```

## disassembly

```asm
0x140001f10  mov     [rsp-8+arg_10], rbx
0x140001f15  push    rbp
0x140001f16  push    rsi
0x140001f17  push    rdi
0x140001f18  lea     rbp, [rsp-47h]
0x140001f1d  sub     rsp, 90h
0x140001f24  mov     rax, cs:__security_cookie
0x140001f2b  xor     rax, rsp
0x140001f2e  mov     [rbp+57h+var_18], rax
0x140001f32  mov     rsi, rdx
0x140001f35  mov     [rbp+57h+SourceDevice], 0
0x140001f3d  mov     rbx, rcx
0x140001f40  mov     [rbp+57h+var_28.Data1], 0A3E32DBAh
0x140001f47  xorps   xmm0, xmm0
0x140001f4a  mov     dword ptr [rbp+57h+var_28.Data2], 4F17BA89h
0x140001f51  xorps   xmm1, xmm1
0x140001f54  mov     dword ptr [rbp+57h+var_28.Data4], 12D8683h
0x140001f5b  lea     rdx, aDeviceRdpbus; "\\Device\\RdpBus"
0x140001f62  mov     dword ptr [rbp+57h+var_28.Data4+4], 0CCD4FB27h
0x140001f69  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140001f6d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140001f71  movups  xmmword ptr [rbp+57h+var_48.Length], xmm1
0x140001f75  call    cs:__imp_RtlInitUnicodeString
0x140001f7c  nop     dword ptr [rax+rax+00h]
0x140001f81  lea     rdx, aDPAGaSy; "D:P(A;;GA;;;SY)"
0x140001f88  lea     rcx, [rbp+57h+var_48]; DestinationString
0x140001f8c  call    cs:__imp_RtlInitUnicodeString
0x140001f93  nop     dword ptr [rax+rax+00h]
0x140001f98  lea     rax, [rbp+57h+SourceDevice]
0x140001f9c  mov     rcx, rbx; DriverObject
0x140001f9f  mov     [rsp+0A0h+DeviceObject], rax; DeviceObject
0x140001fa4  lea     r8, [rbp+57h+DestinationString]; DeviceName
0x140001fa8  lea     rax, [rbp+57h+var_28]
0x140001fac  mov     [rsp+0A0h+DeviceClassGuid], rax; DeviceClassGuid
0x140001fb1  lea     rax, [rbp+57h+var_48]
0x140001fb5  mov     [rsp+0A0h+DefaultSDDLString], rax; DefaultSDDLString
0x140001fba  call    WdmlibIoCreateDeviceSecure
0x140001fbf  mov     edi, eax
0x140001fc1  test    eax, eax
0x140001fc3  jns     short loc_140002003
0x140001fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140001fcc  lea     rdx, WPP_GLOBAL_Control
0x140001fd3  cmp     rcx, rdx
0x140001fd6  jz      loc_14000208A
0x140001fdc  cmp     byte ptr [rcx+29h], 2
0x140001fe0  jb      loc_14000208A
0x140001fe6  mov     rcx, [rcx+18h]
0x140001fea  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001ff1  mov     edx, 14h
0x140001ff6  mov     r9d, eax
0x140001ff9  call    WPP_SF_D
0x140001ffe  jmp     loc_14000208A
0x140002003  mov     rax, [rbp+57h+SourceDevice]
0x140002007  mov     rdx, rsi; TargetDevice
0x14000200a  or      dword ptr [rax+30h], 4
0x14000200e  mov     rax, [rbp+57h+SourceDevice]
0x140002012  mov     rbx, [rax+40h]
0x140002016  xor     eax, eax
0x140002018  mov     [rbx], rax
0x14000201b  mov     rcx, [rbp+57h+SourceDevice]; SourceDevice
0x14000201f  call    cs:__imp_IoAttachDeviceToDeviceStack
0x140002026  nop     dword ptr [rax+rax+00h]
0x14000202b  mov     [rbx], rax
0x14000202e  test    rax, rax
0x140002031  jnz     short loc_14000207A
0x140002033  mov     rcx, cs:WPP_GLOBAL_Control
0x14000203a  lea     rdx, WPP_GLOBAL_Control
0x140002041  cmp     rcx, rdx
0x140002044  jz      short loc_14000205F
0x140002046  cmp     byte ptr [rcx+29h], 2
0x14000204a  jb      short loc_14000205F
0x14000204c  mov     rcx, [rcx+18h]
0x140002050  lea     edx, [rax+15h]
0x140002053  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x14000205a  call    WPP_SF_
0x14000205f  mov     rax, [rbp+57h+SourceDevice]
0x140002063  btr     dword ptr [rax+30h], 7
0x140002068  mov     rcx, [rbp+57h+SourceDevice]; DeviceObject
0x14000206c  call    cs:__imp_IoDeleteDevice
0x140002073  nop     dword ptr [rax+rax+00h]
0x140002078  jmp     short loc_14000208A
0x14000207a  mov     rax, [rbp+57h+SourceDevice]
0x14000207e  mov     cs:?RDPDYN_PDO@@3PEAU_DEVICE_OBJECT@@EA, rsi; _DEVICE_OBJECT * RDPDYN_PDO
0x140002085  btr     dword ptr [rax+30h], 7
0x14000208a  mov     eax, edi
0x14000208c  mov     rcx, [rbp+57h+var_18]
0x140002090  xor     rcx, rsp; StackCookie
0x140002093  call    __security_check_cookie
0x140002098  mov     rbx, [rsp+0A0h+arg_10]
0x1400020a0  add     rsp, 90h
0x1400020a7  pop     rdi
0x1400020a8  pop     rsi
0x1400020a9  pop     rbp
0x1400020aa  retn
```
