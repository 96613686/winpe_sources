# UxStartDeviceFacet

- ea: `0x1400fb8a0`
- end: `0x1400fbc80`
- name: `UxStartDeviceFacet`
- size: `992`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1400fb8a0`

## import_xrefs

- `ntoskrnl!RtlMapGenericMask` at `0x1400fba4f`
- `ntoskrnl!RtlMapGenericMask` at `0x1400fba62`
- `ntoskrnl!RtlMapGenericMask` at `0x1400fba4f`
- `ntoskrnl!RtlMapGenericMask` at `0x1400fba62`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400fba39`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400fba39`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc13`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc2c`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc45`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc13`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc2c`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc45`
- `ntoskrnl!ZwCreateDirectoryObject` at `0x1400fb960`
- `ntoskrnl!ZwCreateDirectoryObject` at `0x1400fb960`
- `ntoskrnl!IoCreateDevice` at `0x1400fb999`
- `ntoskrnl!IoCreateDevice` at `0x1400fb9d6`
- `ntoskrnl!IoCreateDevice` at `0x1400fba13`
- `ntoskrnl!IoCreateDevice` at `0x1400fb999`
- `ntoskrnl!IoCreateDevice` at `0x1400fb9d6`
- `ntoskrnl!IoCreateDevice` at `0x1400fba13`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbab7`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbb16`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbb71`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbab7`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbb16`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbb71`
- `ntoskrnl!ZwClose` at `0x1400fbbc8`
- `ntoskrnl!ZwClose` at `0x1400fbbe1`
- `ntoskrnl!ZwClose` at `0x1400fbbfa`
- `ntoskrnl!ZwClose` at `0x1400fbc5e`
- `ntoskrnl!ZwClose` at `0x1400fbbc8`
- `ntoskrnl!ZwClose` at `0x1400fbbe1`
- `ntoskrnl!ZwClose` at `0x1400fbbfa`
- `ntoskrnl!ZwClose` at `0x1400fbc5e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fba93`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fbaf2`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fbb51`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fba93`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fbaf2`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fbb51`

## string_xrefs

- `0x1400fb8d5`: `\Device\Http\Communication`

## pseudocode

```c
__int64 __fastcall UxStartDeviceFacet(_QWORD *a1)
{
  NTSTATUS v2; // ebx
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rbx
  PDEVICE_OBJECT v5; // [rsp+40h] [rbp-59h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+48h] [rbp-51h] BYREF
  HANDLE v7; // [rsp+50h] [rbp-49h] BYREF
  void *Handle; // [rsp+58h] [rbp-41h] BYREF
  HANDLE v9; // [rsp+60h] [rbp-39h] BYREF
  void *DirectoryHandle; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v11[2]; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING v13; // [rsp+90h] [rbp-9h] BYREF
  struct _UNICODE_STRING v14; // [rsp+A0h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp+17h] BYREF
  DWORD AccessMask; // [rsp+108h] [rbp+6Fh] BYREF
  DWORD v17; // [rsp+110h] [rbp+77h] BYREF
  PDEVICE_OBJECT v18; // [rsp+118h] [rbp+7Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v11[1] = L"\\Device\\Http";
  v11[0] = 1703960;
  DeviceName.Buffer = (PWSTR)L"\\Device\\Http\\Communication";
  *(_QWORD *)&DeviceName.Length = 3538996;
  v13.Buffer = L"\\Device\\Http\\ReqQueue";
  *(_QWORD *)&v13.Length = 2883626;
  v14.Buffer = L"\\Device\\Http\\ClientSession";
  *(_QWORD *)&v14.Length = 3538996;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
  DirectoryHandle = 0;
  DeviceObject = 0;
  v5 = 0;
  v18 = 0;
  Handle = 0;
  v9 = 0;
  v7 = 0;
  AccessMask = -1073741824;
  v17 = 0x10000000;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwCreateDirectoryObject(&DirectoryHandle, 0xF000Fu, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    v2 = IoCreateDevice((PDRIVER_OBJECT)UxDriverObject, 0, &DeviceName, 0x12u, 0, 0, &DeviceObject);
    if ( v2 >= 0 )
    {
      v2 = IoCreateDevice((PDRIVER_OBJECT)UxDriverObject, 0, &v13, 0x12u, 0x20000u, 0, &v5);
      if ( v2 >= 0 )
      {
        v2 = IoCreateDevice((PDRIVER_OBJECT)UxDriverObject, 0, &v14, 0x12u, 0x20000u, 0, &v18);
        if ( v2 >= 0 )
        {
          v5->StackSize = 4;
          v18->StackSize = 4;
          FileObjectGenericMapping = IoGetFileObjectGenericMapping();
          RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
          RtlMapGenericMask(&v17, FileObjectGenericMapping);
          v2 = ObOpenObjectByPointer(DeviceObject, 0x240u, 0, 0x2000000u, 0, 0, &Handle);
          if ( v2 >= 0 )
          {
            v2 = ZwSetSecurityObject(Handle, 4u, UxDeviceObjectSDBytes);
            if ( v2 >= 0 )
            {
              v2 = ObOpenObjectByPointer(v5, 0x240u, 0, 0x2000000u, 0, 0, &v9);
              if ( v2 >= 0 )
              {
                v2 = ZwSetSecurityObject(v9, 4u, UxDeviceObjectSDBytes);
                if ( v2 >= 0 )
                {
                  v2 = ObOpenObjectByPointer(v18, 0x240u, 0, 0x2000000u, 0, 0, &v7);
                  if ( v2 >= 0 )
                  {
                    v2 = ZwSetSecurityObject(v7, 4u, UxDeviceObjectSDBytes);
                    if ( v2 >= 0 )
                    {
                      a1[517] = v18;
                      a1[516] = v5;
                      a1[515] = DeviceObject;
                      a1[514] = DirectoryHandle;
                      v18 = 0;
                      v5 = 0;
                      DeviceObject = 0;
                      DirectoryHandle = 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v7 )
  {
    ZwClose(v7);
    v7 = 0;
  }
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( v9 )
  {
    ZwClose(v9);
    v9 = 0;
  }
  if ( v18 )
  {
    IoDeleteDevice(v18);
    v18 = 0;
  }
  if ( DeviceObject )
  {
    IoDeleteDevice(DeviceObject);
    DeviceObject = 0;
  }
  if ( v5 )
  {
    IoDeleteDevice(v5);
    v5 = 0;
  }
  if ( DirectoryHandle )
    ZwClose(DirectoryHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400fb8a0  mov     [rsp-8+arg_0], rbx
0x1400fb8a5  push    rbp
0x1400fb8a6  push    rsi
0x1400fb8a7  push    rdi
0x1400fb8a8  lea     rbp, [rsp-47h]
0x1400fb8ad  sub     rsp, 0E0h
0x1400fb8b4  xor     esi, esi
0x1400fb8b6  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400fb8be  lea     rax, aDeviceHttp; "\\Device\\Http"
0x1400fb8c5  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400fb8cd  mov     [rbp+57h+var_78], rax
0x1400fb8d1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400fb8d5  lea     rax, aDeviceHttpComm; "\\Device\\Http\\Communication"
0x1400fb8dc  mov     [rbp+57h+var_80], 1A0018h
0x1400fb8e4  mov     [rbp+57h+DeviceName.Buffer], rax
0x1400fb8e8  mov     rdi, rcx
0x1400fb8eb  lea     rax, aDeviceHttpReqq; "\\Device\\Http\\ReqQueue"
0x1400fb8f2  mov     qword ptr [rbp+57h+DeviceName.Length], 360034h
0x1400fb8fa  mov     [rbp+57h+var_60.Buffer], rax
0x1400fb8fe  lea     rcx, [rbp+57h+DirectoryHandle]; DirectoryHandle
0x1400fb902  lea     rax, aDeviceHttpClie; "\\Device\\Http\\ClientSession"
0x1400fb909  mov     qword ptr [rbp+57h+var_60.Length], 2C002Ah
0x1400fb911  mov     [rbp+57h+var_50.Buffer], rax
0x1400fb915  xorps   xmm0, xmm0
0x1400fb918  lea     rax, [rbp+57h+var_80]
0x1400fb91c  mov     qword ptr [rbp+57h+var_50.Length], 360034h
0x1400fb924  mov     edx, 0F000Fh; DesiredAccess
0x1400fb929  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400fb92d  mov     [rbp+57h+DirectoryHandle], rsi
0x1400fb931  mov     [rbp+57h+var_A8], rsi
0x1400fb935  mov     [rbp+57h+var_B0], rsi
0x1400fb939  mov     [rbp+57h+arg_18], rsi
0x1400fb93d  mov     [rbp+57h+Handle], rsi
0x1400fb941  mov     [rbp+57h+var_90], rsi
0x1400fb945  mov     [rbp+57h+var_A0], rsi
0x1400fb949  mov     [rbp+57h+AccessMask], 0C0000000h
0x1400fb950  mov     [rbp+57h+arg_10], 10000000h
0x1400fb957  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1400fb95b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400fb960  call    cs:__imp_ZwCreateDirectoryObject
0x1400fb967  nop     dword ptr [rax+rax+00h]
0x1400fb96c  mov     ebx, eax
0x1400fb96e  test    eax, eax
0x1400fb970  js      loc_1400FBBBF
0x1400fb976  mov     rcx, cs:UxDriverObject; DriverObject
0x1400fb97d  lea     rax, [rbp+57h+var_A8]
0x1400fb981  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x1400fb986  lea     r9d, [rsi+12h]; DeviceType
0x1400fb98a  mov     [rsp+0F0h+Exclusive], sil; Exclusive
0x1400fb98f  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x1400fb993  xor     edx, edx; DeviceExtensionSize
0x1400fb995  mov     [rsp+0F0h+DeviceCharacteristics], esi; DeviceCharacteristics
0x1400fb999  call    cs:__imp_IoCreateDevice
0x1400fb9a0  nop     dword ptr [rax+rax+00h]
0x1400fb9a5  mov     ebx, eax
0x1400fb9a7  test    eax, eax
0x1400fb9a9  js      loc_1400FBBBF
0x1400fb9af  mov     rcx, cs:UxDriverObject; DriverObject
0x1400fb9b6  lea     rax, [rbp+57h+var_B0]
0x1400fb9ba  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x1400fb9bf  lea     r9d, [rsi+12h]; DeviceType
0x1400fb9c3  mov     [rsp+0F0h+Exclusive], sil; Exclusive
0x1400fb9c8  lea     r8, [rbp+57h+var_60]; DeviceName
0x1400fb9cc  xor     edx, edx; DeviceExtensionSize
0x1400fb9ce  mov     [rsp+0F0h+DeviceCharacteristics], 20000h; DeviceCharacteristics
0x1400fb9d6  call    cs:__imp_IoCreateDevice
0x1400fb9dd  nop     dword ptr [rax+rax+00h]
0x1400fb9e2  mov     ebx, eax
0x1400fb9e4  test    eax, eax
0x1400fb9e6  js      loc_1400FBBBF
0x1400fb9ec  mov     rcx, cs:UxDriverObject; DriverObject
0x1400fb9f3  lea     rax, [rbp+57h+arg_18]
0x1400fb9f7  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x1400fb9fc  lea     r9d, [rsi+12h]; DeviceType
0x1400fba00  mov     [rsp+0F0h+Exclusive], sil; Exclusive
0x1400fba05  lea     r8, [rbp+57h+var_50]; DeviceName
0x1400fba09  xor     edx, edx; DeviceExtensionSize
0x1400fba0b  mov     [rsp+0F0h+DeviceCharacteristics], 20000h; DeviceCharacteristics
0x1400fba13  call    cs:__imp_IoCreateDevice
0x1400fba1a  nop     dword ptr [rax+rax+00h]
0x1400fba1f  mov     ebx, eax
0x1400fba21  test    eax, eax
0x1400fba23  js      loc_1400FBBBF
0x1400fba29  mov     rax, [rbp+57h+var_B0]
0x1400fba2d  mov     byte ptr [rax+4Ch], 4
0x1400fba31  mov     rax, [rbp+57h+arg_18]
0x1400fba35  mov     byte ptr [rax+4Ch], 4
0x1400fba39  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400fba40  nop     dword ptr [rax+rax+00h]
0x1400fba45  mov     rdx, rax; GenericMapping
0x1400fba48  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1400fba4c  mov     rbx, rax
0x1400fba4f  call    cs:__imp_RtlMapGenericMask
0x1400fba56  nop     dword ptr [rax+rax+00h]
0x1400fba5b  mov     rdx, rbx; GenericMapping
0x1400fba5e  lea     rcx, [rbp+57h+arg_10]; AccessMask
0x1400fba62  call    cs:__imp_RtlMapGenericMask
0x1400fba69  nop     dword ptr [rax+rax+00h]
0x1400fba6e  mov     rcx, [rbp+57h+var_A8]; Object
0x1400fba72  lea     rax, [rbp+57h+Handle]
0x1400fba76  mov     [rsp+0F0h+DeviceObject], rax; Handle
0x1400fba7b  mov     r9d, 2000000h; DesiredAccess
0x1400fba81  mov     [rsp+0F0h+Exclusive], sil; AccessMode
0x1400fba86  xor     r8d, r8d; PassedAccessState
0x1400fba89  mov     edx, 240h; HandleAttributes
0x1400fba8e  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rsi; ObjectType
0x1400fba93  call    cs:__imp_ObOpenObjectByPointer
0x1400fba9a  nop     dword ptr [rax+rax+00h]
0x1400fba9f  mov     ebx, eax
0x1400fbaa1  test    eax, eax
0x1400fbaa3  js      loc_1400FBBBF
0x1400fbaa9  mov     rcx, [rbp+57h+Handle]; Handle
0x1400fbaad  lea     r8, UxDeviceObjectSDBytes; SecurityDescriptor
0x1400fbab4  lea     edx, [rsi+4]; SecurityInformation
0x1400fbab7  call    cs:__imp_ZwSetSecurityObject
0x1400fbabe  nop     dword ptr [rax+rax+00h]
0x1400fbac3  mov     ebx, eax
0x1400fbac5  test    eax, eax
0x1400fbac7  js      loc_1400FBBBF
0x1400fbacd  mov     rcx, [rbp+57h+var_B0]; Object
0x1400fbad1  lea     rax, [rbp+57h+var_90]
0x1400fbad5  mov     [rsp+0F0h+DeviceObject], rax; Handle
0x1400fbada  mov     r9d, 2000000h; DesiredAccess
0x1400fbae0  mov     [rsp+0F0h+Exclusive], sil; AccessMode
0x1400fbae5  xor     r8d, r8d; PassedAccessState
0x1400fbae8  mov     edx, 240h; HandleAttributes
0x1400fbaed  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rsi; ObjectType
0x1400fbaf2  call    cs:__imp_ObOpenObjectByPointer
0x1400fbaf9  nop     dword ptr [rax+rax+00h]
0x1400fbafe  mov     ebx, eax
0x1400fbb00  test    eax, eax
0x1400fbb02  js      loc_1400FBBBF
0x1400fbb08  mov     rcx, [rbp+57h+var_90]; Handle
0x1400fbb0c  lea     r8, UxDeviceObjectSDBytes; SecurityDescriptor
0x1400fbb13  lea     edx, [rsi+4]; SecurityInformation
0x1400fbb16  call    cs:__imp_ZwSetSecurityObject
0x1400fbb1d  nop     dword ptr [rax+rax+00h]
0x1400fbb22  mov     ebx, eax
0x1400fbb24  test    eax, eax
0x1400fbb26  js      loc_1400FBBBF
0x1400fbb2c  mov     rcx, [rbp+57h+arg_18]; Object
0x1400fbb30  lea     rax, [rbp+57h+var_A0]
0x1400fbb34  mov     [rsp+0F0h+DeviceObject], rax; Handle
0x1400fbb39  mov     r9d, 2000000h; DesiredAccess
0x1400fbb3f  mov     [rsp+0F0h+Exclusive], sil; AccessMode
0x1400fbb44  xor     r8d, r8d; PassedAccessState
0x1400fbb47  mov     edx, 240h; HandleAttributes
0x1400fbb4c  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rsi; ObjectType
0x1400fbb51  call    cs:__imp_ObOpenObjectByPointer
0x1400fbb58  nop     dword ptr [rax+rax+00h]
0x1400fbb5d  mov     ebx, eax
0x1400fbb5f  test    eax, eax
0x1400fbb61  js      short loc_1400FBBBF
0x1400fbb63  mov     rcx, [rbp+57h+var_A0]; Handle
0x1400fbb67  lea     r8, UxDeviceObjectSDBytes; SecurityDescriptor
0x1400fbb6e  lea     edx, [rsi+4]; SecurityInformation
0x1400fbb71  call    cs:__imp_ZwSetSecurityObject
0x1400fbb78  nop     dword ptr [rax+rax+00h]
0x1400fbb7d  mov     ebx, eax
0x1400fbb7f  test    eax, eax
0x1400fbb81  js      short loc_1400FBBBF
0x1400fbb83  mov     rax, [rbp+57h+arg_18]
0x1400fbb87  mov     [rdi+1028h], rax
0x1400fbb8e  mov     rax, [rbp+57h+var_B0]
0x1400fbb92  mov     [rdi+1020h], rax
0x1400fbb99  mov     rax, [rbp+57h+var_A8]
0x1400fbb9d  mov     [rdi+1018h], rax
0x1400fbba4  mov     rax, [rbp+57h+DirectoryHandle]
0x1400fbba8  mov     [rdi+1010h], rax
0x1400fbbaf  mov     [rbp+57h+arg_18], rsi
0x1400fbbb3  mov     [rbp+57h+var_B0], rsi
0x1400fbbb7  mov     [rbp+57h+var_A8], rsi
0x1400fbbbb  mov     [rbp+57h+DirectoryHandle], rsi
0x1400fbbbf  mov     rcx, [rbp+57h+var_A0]; Handle
0x1400fbbc3  test    rcx, rcx
0x1400fbbc6  jz      short loc_1400FBBD8
0x1400fbbc8  call    cs:__imp_ZwClose
0x1400fbbcf  nop     dword ptr [rax+rax+00h]
0x1400fbbd4  mov     [rbp+57h+var_A0], rsi
0x1400fbbd8  mov     rcx, [rbp+57h+Handle]; Handle
0x1400fbbdc  test    rcx, rcx
0x1400fbbdf  jz      short loc_1400FBBF1
0x1400fbbe1  call    cs:__imp_ZwClose
0x1400fbbe8  nop     dword ptr [rax+rax+00h]
0x1400fbbed  mov     [rbp+57h+Handle], rsi
0x1400fbbf1  mov     rcx, [rbp+57h+var_90]; Handle
0x1400fbbf5  test    rcx, rcx
0x1400fbbf8  jz      short loc_1400FBC0A
0x1400fbbfa  call    cs:__imp_ZwClose
0x1400fbc01  nop     dword ptr [rax+rax+00h]
0x1400fbc06  mov     [rbp+57h+var_90], rsi
0x1400fbc0a  mov     rcx, [rbp+57h+arg_18]; DeviceObject
0x1400fbc0e  test    rcx, rcx
0x1400fbc11  jz      short loc_1400FBC23
0x1400fbc13  call    cs:__imp_IoDeleteDevice
0x1400fbc1a  nop     dword ptr [rax+rax+00h]
0x1400fbc1f  mov     [rbp+57h+arg_18], rsi
0x1400fbc23  mov     rcx, [rbp+57h+var_A8]; DeviceObject
0x1400fbc27  test    rcx, rcx
0x1400fbc2a  jz      short loc_1400FBC3C
0x1400fbc2c  call    cs:__imp_IoDeleteDevice
0x1400fbc33  nop     dword ptr [rax+rax+00h]
0x1400fbc38  mov     [rbp+57h+var_A8], rsi
0x1400fbc3c  mov     rcx, [rbp+57h+var_B0]; DeviceObject
0x1400fbc40  test    rcx, rcx
0x1400fbc43  jz      short loc_1400FBC55
0x1400fbc45  call    cs:__imp_IoDeleteDevice
0x1400fbc4c  nop     dword ptr [rax+rax+00h]
0x1400fbc51  mov     [rbp+57h+var_B0], rsi
0x1400fbc55  mov     rcx, [rbp+57h+DirectoryHandle]; Handle
0x1400fbc59  test    rcx, rcx
0x1400fbc5c  jz      short loc_1400FBC6A
0x1400fbc5e  call    cs:__imp_ZwClose
0x1400fbc65  nop     dword ptr [rax+rax+00h]
0x1400fbc6a  mov     eax, ebx
0x1400fbc6c  mov     rbx, [rsp+0F0h+arg_0]
0x1400fbc74  add     rsp, 0E0h
0x1400fbc7b  pop     rdi
0x1400fbc7c  pop     rsi
0x1400fbc7d  pop     rbp
0x1400fbc7e  retn
```
