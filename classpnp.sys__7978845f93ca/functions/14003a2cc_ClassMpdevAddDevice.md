# ClassMpdevAddDevice

- ea: `0x14003a2cc`
- end: `0x14003a624`
- name: `ClassMpdevAddDevice`
- size: `856`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x140055a60`

## callees

- `0x14001fbf4`
- `0x14001fc38`
- `0x14001feac`
- `0x14002001c`
- `0x140022614`
- `0x14003a2cc`
- `0x14003e940`
- `0x140055ae0`
- `0x14005ce5c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003a397`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a480`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a572`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a397`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a480`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a572`
- `ntoskrnl!IoDetachDevice` at `0x14003a585`
- `ntoskrnl!IoDetachDevice` at `0x14003a585`
- `ntoskrnl!IoDeleteDevice` at `0x14003a490`
- `ntoskrnl!IoDeleteDevice` at `0x14003a595`
- `ntoskrnl!IoDeleteDevice` at `0x14003a490`
- `ntoskrnl!IoDeleteDevice` at `0x14003a595`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14003a311`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14003a311`
- `ntoskrnl!IoCreateDevice` at `0x14003a348`
- `ntoskrnl!IoCreateDevice` at `0x14003a348`
- `ntoskrnl!IoGetConfigurationInformation` at `0x14003a5f5`
- `ntoskrnl!IoGetConfigurationInformation` at `0x14003a5f5`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14003a434`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14003a434`

## pseudocode

```c
__int64 __fastcall ClassMpdevAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  __int64 result; // rax
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  PDEVICE_OBJECT *DeviceExtension; // rbx
  struct _DEVICE_OBJECT *v8; // r13
  PDEVICE_OBJECT v9; // rax
  NTSTATUS v10; // eax
  unsigned int v11; // r15d
  PCONFIGURATION_INFORMATION ConfigurationInformation; // rax
  volatile signed __int32 *DriverObjectExtension; // [rsp+40h] [rbp-10h]
  PDEVICE_OBJECT SourceDevice; // [rsp+90h] [rbp+40h] BYREF
  PVOID Object; // [rsp+98h] [rbp+48h] BYREF

  SourceDevice = 0;
  Object = 0;
  result = ClasspMpdevSupportedDevice(DriverObject, TargetDevice, &Object);
  if ( (int)result >= 0 )
  {
    DriverObjectExtension = (volatile signed __int32 *)IoGetDriverObjectExtension(DriverObject, ClassInitialize);
    v5 = IoCreateDevice(DriverObject, 0x490u, 0, 7u, 0x100u, 0, &SourceDevice);
    v6 = v5;
    if ( v5 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids, SourceDevice);
      }
      DeviceExtension = (PDEVICE_OBJECT *)SourceDevice->DeviceExtension;
      memset(DeviceExtension, 0, 0x280u);
      v8 = (struct _DEVICE_OBJECT *)Object;
      DeviceExtension[1] = SourceDevice;
      DeviceExtension[71] = v8;
      DeviceExtension[56] = (PDEVICE_OBJECT)(DriverObjectExtension + 166);
      DeviceExtension[64] = (PDEVICE_OBJECT)DriverObject;
      DeviceExtension[66] = TargetDevice;
      v9 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
      DeviceExtension[65] = v9;
      if ( v9 )
      {
        DeviceExtension[71] = v8;
        DeviceExtension[12] = (PDEVICE_OBJECT)(DeviceExtension + 80);
        SourceDevice->Flags |= v9->Flags & 0x6014;
        SourceDevice->DeviceType = DeviceExtension[65]->DeviceType;
        SourceDevice->Characteristics = DeviceExtension[65]->Characteristics;
        v10 = ClassClaimDevice(SourceDevice, 0);
        v11 = v10;
        if ( v10 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              22,
              WPP_a63e98891b663a71e40facba1bb231b0_Traceguids,
              DeviceExtension[65]);
          }
          SourceDevice->Flags &= ~0x80u;
          *((_WORD *)DeviceExtension + 290) = -1;
          _InterlockedIncrement(DriverObjectExtension + 102);
          ConfigurationInformation = IoGetConfigurationInformation();
          *((_DWORD *)DeviceExtension + 144) = ConfigurationInformation->DiskCount++;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_a63e98891b663a71e40facba1bb231b0_Traceguids,
                DeviceExtension[65],
                v10);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF_Dq(
                WPP_GLOBAL_Control->AttachedDevice,
                21,
                WPP_a63e98891b663a71e40facba1bb231b0_Traceguids,
                v11,
                TargetDevice);
            }
          }
          ObfDereferenceObject(v8);
          IoDetachDevice(DeviceExtension[65]);
          IoDeleteDevice(SourceDevice);
        }
        return v11;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids);
        }
        ObfDereferenceObject(v8);
        IoDeleteDevice(SourceDevice);
        return 3221225486LL;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_a63e98891b663a71e40facba1bb231b0_Traceguids,
            (unsigned int)v5);
      }
      ObfDereferenceObject(Object);
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003a2cc  mov     [rsp-28h+arg_0], rbx
0x14003a2d1  push    rbp
0x14003a2d2  push    rsi
0x14003a2d3  push    r12
0x14003a2d5  push    r13
0x14003a2d7  push    r15
0x14003a2d9  mov     rbp, rsp
0x14003a2dc  sub     rsp, 50h
0x14003a2e0  lea     r8, [rbp+Object]
0x14003a2e4  mov     [rbp+SourceDevice], 0
0x14003a2ec  mov     r12, rdx
0x14003a2ef  mov     [rbp+Object], 0
0x14003a2f7  mov     r15, rcx
0x14003a2fa  call    ClasspMpdevSupportedDevice
0x14003a2ff  test    eax, eax
0x14003a301  js      loc_14003A60E
0x14003a307  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x14003a30e  mov     rcx, r15; DriverObject
0x14003a311  call    cs:__imp_IoGetDriverObjectExtension
0x14003a318  nop     dword ptr [rax+rax+00h]
0x14003a31d  mov     [rbp+var_10], rax
0x14003a321  mov     r9d, 7; DeviceType
0x14003a327  lea     rax, [rbp+SourceDevice]
0x14003a32b  xor     r8d, r8d; DeviceName
0x14003a32e  mov     [rsp+50h+DeviceObject], rax; DeviceObject
0x14003a333  mov     edx, 490h; DeviceExtensionSize
0x14003a338  mov     [rsp+50h+Exclusive], 0; Exclusive
0x14003a33d  mov     rcx, r15; DriverObject
0x14003a340  mov     [rsp+50h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14003a348  call    cs:__imp_IoCreateDevice
0x14003a34f  nop     dword ptr [rax+rax+00h]
0x14003a354  mov     ebx, eax
0x14003a356  test    eax, eax
0x14003a358  jns     short loc_14003A3AA
0x14003a35a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a361  lea     rsi, WPP_GLOBAL_Control
0x14003a368  cmp     rcx, rsi
0x14003a36b  jz      short loc_14003A393
0x14003a36d  mov     edx, [rcx+2Ch]
0x14003a370  test    dl, 2
0x14003a373  jz      short loc_14003A393
0x14003a375  cmp     byte ptr [rcx+29h], 1
0x14003a379  jb      short loc_14003A393
0x14003a37b  mov     rcx, [rcx+18h]
0x14003a37f  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a386  mov     edx, 11h
0x14003a38b  mov     r9d, eax
0x14003a38e  call    WPP_SF_d
0x14003a393  mov     rcx, [rbp+Object]; Object
0x14003a397  call    cs:__imp_ObfDereferenceObject
0x14003a39e  nop     dword ptr [rax+rax+00h]
0x14003a3a3  mov     eax, ebx
0x14003a3a5  jmp     loc_14003A60E
0x14003a3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a3b1  lea     rsi, WPP_GLOBAL_Control
0x14003a3b8  cmp     rcx, rsi
0x14003a3bb  jz      short loc_14003A3E3
0x14003a3bd  mov     eax, [rcx+2Ch]
0x14003a3c0  test    al, 2
0x14003a3c2  jz      short loc_14003A3E3
0x14003a3c4  cmp     byte ptr [rcx+29h], 4
0x14003a3c8  jb      short loc_14003A3E3
0x14003a3ca  mov     r9, [rbp+SourceDevice]
0x14003a3ce  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a3d5  mov     rcx, [rcx+18h]
0x14003a3d9  mov     edx, 12h
0x14003a3de  call    WPP_SF_q
0x14003a3e3  mov     rax, [rbp+SourceDevice]
0x14003a3e7  xor     edx, edx; Val
0x14003a3e9  mov     r8d, 280h; Size
0x14003a3ef  mov     rbx, [rax+40h]
0x14003a3f3  mov     rcx, rbx; void *
0x14003a3f6  call    memset
0x14003a3fb  mov     rax, [rbp+SourceDevice]
0x14003a3ff  mov     rdx, r12; TargetDevice
0x14003a402  mov     r13, [rbp+Object]
0x14003a406  mov     [rbx+8], rax
0x14003a40a  mov     rax, [rbp+var_10]
0x14003a40e  mov     [rbx+238h], r13
0x14003a415  add     rax, 298h
0x14003a41b  mov     [rbx+1C0h], rax
0x14003a422  mov     [rbx+200h], r15
0x14003a429  mov     [rbx+210h], r12
0x14003a430  mov     rcx, [rbp+SourceDevice]; SourceDevice
0x14003a434  call    cs:__imp_IoAttachDeviceToDeviceStack
0x14003a43b  nop     dword ptr [rax+rax+00h]
0x14003a440  mov     [rbx+208h], rax
0x14003a447  mov     rdx, rax
0x14003a44a  test    rax, rax
0x14003a44d  jnz     short loc_14003A4A6
0x14003a44f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a456  cmp     rcx, rsi
0x14003a459  jz      short loc_14003A47D
0x14003a45b  mov     eax, [rcx+2Ch]
0x14003a45e  test    al, 2
0x14003a460  jz      short loc_14003A47D
0x14003a462  cmp     byte ptr [rcx+29h], 1
0x14003a466  jb      short loc_14003A47D
0x14003a468  mov     rcx, [rcx+18h]
0x14003a46c  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a473  mov     edx, 13h
0x14003a478  call    WPP_SF_
0x14003a47d  mov     rcx, r13; Object
0x14003a480  call    cs:__imp_ObfDereferenceObject
0x14003a487  nop     dword ptr [rax+rax+00h]
0x14003a48c  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x14003a490  call    cs:__imp_IoDeleteDevice
0x14003a497  nop     dword ptr [rax+rax+00h]
0x14003a49c  mov     eax, 0C000000Eh
0x14003a4a1  jmp     loc_14003A60E
0x14003a4a6  mov     [rbx+238h], r13
0x14003a4ad  lea     rax, [rbx+280h]
0x14003a4b4  mov     [rbx+60h], rax
0x14003a4b8  mov     eax, [rdx+30h]
0x14003a4bb  xor     edx, edx; Release
0x14003a4bd  mov     rcx, [rbp+SourceDevice]
0x14003a4c1  and     eax, 6014h
0x14003a4c6  or      [rcx+30h], eax
0x14003a4c9  mov     rax, [rbx+208h]
0x14003a4d0  mov     ecx, [rax+48h]
0x14003a4d3  mov     rax, [rbp+SourceDevice]
0x14003a4d7  mov     [rax+48h], ecx
0x14003a4da  mov     rax, [rbx+208h]
0x14003a4e1  mov     ecx, [rax+34h]
0x14003a4e4  mov     rax, [rbp+SourceDevice]
0x14003a4e8  mov     [rax+34h], ecx
0x14003a4eb  mov     rcx, [rbp+SourceDevice]; LowerDeviceObject
0x14003a4ef  call    ClassClaimDevice
0x14003a4f4  mov     r15d, eax
0x14003a4f7  test    eax, eax
0x14003a4f9  jns     loc_14003A5A3
0x14003a4ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a506  cmp     rcx, rsi
0x14003a509  jz      short loc_14003A56F
0x14003a50b  mov     edx, [rcx+2Ch]
0x14003a50e  test    dl, 2
0x14003a511  jz      short loc_14003A539
0x14003a513  cmp     byte ptr [rcx+29h], 3
0x14003a517  jb      short loc_14003A539
0x14003a519  mov     r9, [rbx+208h]
0x14003a520  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a527  mov     rcx, [rcx+18h]
0x14003a52b  mov     edx, 14h
0x14003a530  mov     [rsp+50h+DeviceCharacteristics], eax
0x14003a534  call    WPP_SF_qD
0x14003a539  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a540  cmp     rcx, rsi
0x14003a543  jz      short loc_14003A56F
0x14003a545  mov     eax, [rcx+2Ch]
0x14003a548  test    al, 2
0x14003a54a  jz      short loc_14003A56F
0x14003a54c  cmp     byte ptr [rcx+29h], 3
0x14003a550  jb      short loc_14003A56F
0x14003a552  mov     rcx, [rcx+18h]
0x14003a556  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a55d  mov     edx, 15h
0x14003a562  mov     qword ptr [rsp+50h+DeviceCharacteristics], r12
0x14003a567  mov     r9d, r15d
0x14003a56a  call    WPP_SF_Dq
0x14003a56f  mov     rcx, r13; Object
0x14003a572  call    cs:__imp_ObfDereferenceObject
0x14003a579  nop     dword ptr [rax+rax+00h]
0x14003a57e  mov     rcx, [rbx+208h]; TargetDevice
0x14003a585  call    cs:__imp_IoDetachDevice
0x14003a58c  nop     dword ptr [rax+rax+00h]
0x14003a591  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x14003a595  call    cs:__imp_IoDeleteDevice
0x14003a59c  nop     dword ptr [rax+rax+00h]
0x14003a5a1  jmp     short loc_14003A60B
0x14003a5a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a5aa  cmp     rcx, rsi
0x14003a5ad  jz      short loc_14003A5D8
0x14003a5af  mov     eax, [rcx+2Ch]
0x14003a5b2  test    al, 2
0x14003a5b4  jz      short loc_14003A5D8
0x14003a5b6  cmp     byte ptr [rcx+29h], 4
0x14003a5ba  jb      short loc_14003A5D8
0x14003a5bc  mov     r9, [rbx+208h]
0x14003a5c3  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003a5ca  mov     rcx, [rcx+18h]
0x14003a5ce  mov     edx, 16h
0x14003a5d3  call    WPP_SF_q
0x14003a5d8  mov     rax, [rbp+SourceDevice]
0x14003a5dc  btr     dword ptr [rax+30h], 7
0x14003a5e1  mov     rax, [rbp+var_10]
0x14003a5e5  mov     word ptr [rbx+244h], 0FFFFh
0x14003a5ee  lock inc dword ptr [rax+198h]
0x14003a5f5  call    cs:__imp_IoGetConfigurationInformation
0x14003a5fc  nop     dword ptr [rax+rax+00h]
0x14003a601  mov     ecx, [rax]
0x14003a603  mov     [rbx+240h], ecx
0x14003a609  inc     dword ptr [rax]
0x14003a60b  mov     eax, r15d
0x14003a60e  mov     rbx, [rsp+50h+arg_0]
0x14003a616  add     rsp, 50h
0x14003a61a  pop     r15
0x14003a61c  pop     r13
0x14003a61e  pop     r12
0x14003a620  pop     rsi
0x14003a621  pop     rbp
0x14003a622  retn
```
