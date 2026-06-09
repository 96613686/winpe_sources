# UxStartDeviceFacet

- ea: `0x1400fb8d0`
- end: `0x1400fbcb0`
- name: `UxStartDeviceFacet`
- size: `992`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1400fb8d0`

## import_xrefs

- `ntoskrnl!RtlMapGenericMask` at `0x1400fba7f`
- `ntoskrnl!RtlMapGenericMask` at `0x1400fba92`
- `ntoskrnl!RtlMapGenericMask` at `0x1400fba7f`
- `ntoskrnl!RtlMapGenericMask` at `0x1400fba92`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400fba69`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400fba69`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc43`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc5c`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc75`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc43`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc5c`
- `ntoskrnl!IoDeleteDevice` at `0x1400fbc75`
- `ntoskrnl!ZwCreateDirectoryObject` at `0x1400fb990`
- `ntoskrnl!ZwCreateDirectoryObject` at `0x1400fb990`
- `ntoskrnl!IoCreateDevice` at `0x1400fb9c9`
- `ntoskrnl!IoCreateDevice` at `0x1400fba06`
- `ntoskrnl!IoCreateDevice` at `0x1400fba43`
- `ntoskrnl!IoCreateDevice` at `0x1400fb9c9`
- `ntoskrnl!IoCreateDevice` at `0x1400fba06`
- `ntoskrnl!IoCreateDevice` at `0x1400fba43`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbae7`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbb46`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbba1`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbae7`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbb46`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400fbba1`
- `ntoskrnl!ZwClose` at `0x1400fbbf8`
- `ntoskrnl!ZwClose` at `0x1400fbc11`
- `ntoskrnl!ZwClose` at `0x1400fbc2a`
- `ntoskrnl!ZwClose` at `0x1400fbc8e`
- `ntoskrnl!ZwClose` at `0x1400fbbf8`
- `ntoskrnl!ZwClose` at `0x1400fbc11`
- `ntoskrnl!ZwClose` at `0x1400fbc2a`
- `ntoskrnl!ZwClose` at `0x1400fbc8e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fbac3`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fbb22`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fbb81`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fbac3`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fbb22`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400fbb81`

## string_xrefs

- `0x1400fb905`: `\Device\Http\Communication`

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
0x1400fb8d0  mov     [rsp-8+arg_0], rbx
0x1400fb8d5  push    rbp
0x1400fb8d6  push    rsi
0x1400fb8d7  push    rdi
0x1400fb8d8  lea     rbp, [rsp-47h]
0x1400fb8dd  sub     rsp, 0E0h
0x1400fb8e4  xor     esi, esi
0x1400fb8e6  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400fb8ee  lea     rax, aDeviceHttp; "\\Device\\Http"
0x1400fb8f5  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400fb8fd  mov     [rbp+57h+var_78], rax
0x1400fb901  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400fb905  lea     rax, aDeviceHttpComm; "\\Device\\Http\\Communication"
0x1400fb90c  mov     [rbp+57h+var_80], 1A0018h
0x1400fb914  mov     [rbp+57h+DeviceName.Buffer], rax
0x1400fb918  mov     rdi, rcx
0x1400fb91b  lea     rax, aDeviceHttpReqq; "\\Device\\Http\\ReqQueue"
0x1400fb922  mov     qword ptr [rbp+57h+DeviceName.Length], 360034h
0x1400fb92a  mov     [rbp+57h+var_60.Buffer], rax
0x1400fb92e  lea     rcx, [rbp+57h+DirectoryHandle]; DirectoryHandle
0x1400fb932  lea     rax, aDeviceHttpClie; "\\Device\\Http\\ClientSession"
0x1400fb939  mov     qword ptr [rbp+57h+var_60.Length], 2C002Ah
0x1400fb941  mov     [rbp+57h+var_50.Buffer], rax
0x1400fb945  xorps   xmm0, xmm0
0x1400fb948  lea     rax, [rbp+57h+var_80]
0x1400fb94c  mov     qword ptr [rbp+57h+var_50.Length], 360034h
0x1400fb954  mov     edx, 0F000Fh; DesiredAccess
0x1400fb959  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400fb95d  mov     [rbp+57h+DirectoryHandle], rsi
0x1400fb961  mov     [rbp+57h+var_A8], rsi
0x1400fb965  mov     [rbp+57h+var_B0], rsi
0x1400fb969  mov     [rbp+57h+arg_18], rsi
0x1400fb96d  mov     [rbp+57h+Handle], rsi
0x1400fb971  mov     [rbp+57h+var_90], rsi
0x1400fb975  mov     [rbp+57h+var_A0], rsi
0x1400fb979  mov     [rbp+57h+AccessMask], 0C0000000h
0x1400fb980  mov     [rbp+57h+arg_10], 10000000h
0x1400fb987  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1400fb98b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400fb990  call    cs:__imp_ZwCreateDirectoryObject
0x1400fb997  nop     dword ptr [rax+rax+00h]
0x1400fb99c  mov     ebx, eax
0x1400fb99e  test    eax, eax
0x1400fb9a0  js      loc_1400FBBEF
0x1400fb9a6  mov     rcx, cs:UxDriverObject; DriverObject
0x1400fb9ad  lea     rax, [rbp+57h+var_A8]
0x1400fb9b1  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x1400fb9b6  lea     r9d, [rsi+12h]; DeviceType
0x1400fb9ba  mov     [rsp+0F0h+Exclusive], sil; Exclusive
0x1400fb9bf  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x1400fb9c3  xor     edx, edx; DeviceExtensionSize
0x1400fb9c5  mov     [rsp+0F0h+DeviceCharacteristics], esi; DeviceCharacteristics
0x1400fb9c9  call    cs:__imp_IoCreateDevice
0x1400fb9d0  nop     dword ptr [rax+rax+00h]
0x1400fb9d5  mov     ebx, eax
0x1400fb9d7  test    eax, eax
0x1400fb9d9  js      loc_1400FBBEF
0x1400fb9df  mov     rcx, cs:UxDriverObject; DriverObject
0x1400fb9e6  lea     rax, [rbp+57h+var_B0]
0x1400fb9ea  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x1400fb9ef  lea     r9d, [rsi+12h]; DeviceType
0x1400fb9f3  mov     [rsp+0F0h+Exclusive], sil; Exclusive
0x1400fb9f8  lea     r8, [rbp+57h+var_60]; DeviceName
0x1400fb9fc  xor     edx, edx; DeviceExtensionSize
0x1400fb9fe  mov     [rsp+0F0h+DeviceCharacteristics], 20000h; DeviceCharacteristics
0x1400fba06  call    cs:__imp_IoCreateDevice
0x1400fba0d  nop     dword ptr [rax+rax+00h]
0x1400fba12  mov     ebx, eax
0x1400fba14  test    eax, eax
0x1400fba16  js      loc_1400FBBEF
0x1400fba1c  mov     rcx, cs:UxDriverObject; DriverObject
0x1400fba23  lea     rax, [rbp+57h+arg_18]
0x1400fba27  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x1400fba2c  lea     r9d, [rsi+12h]; DeviceType
0x1400fba30  mov     [rsp+0F0h+Exclusive], sil; Exclusive
0x1400fba35  lea     r8, [rbp+57h+var_50]; DeviceName
0x1400fba39  xor     edx, edx; DeviceExtensionSize
0x1400fba3b  mov     [rsp+0F0h+DeviceCharacteristics], 20000h; DeviceCharacteristics
0x1400fba43  call    cs:__imp_IoCreateDevice
0x1400fba4a  nop     dword ptr [rax+rax+00h]
0x1400fba4f  mov     ebx, eax
0x1400fba51  test    eax, eax
0x1400fba53  js      loc_1400FBBEF
0x1400fba59  mov     rax, [rbp+57h+var_B0]
0x1400fba5d  mov     byte ptr [rax+4Ch], 4
0x1400fba61  mov     rax, [rbp+57h+arg_18]
0x1400fba65  mov     byte ptr [rax+4Ch], 4
0x1400fba69  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400fba70  nop     dword ptr [rax+rax+00h]
0x1400fba75  mov     rdx, rax; GenericMapping
0x1400fba78  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1400fba7c  mov     rbx, rax
0x1400fba7f  call    cs:__imp_RtlMapGenericMask
0x1400fba86  nop     dword ptr [rax+rax+00h]
0x1400fba8b  mov     rdx, rbx; GenericMapping
0x1400fba8e  lea     rcx, [rbp+57h+arg_10]; AccessMask
0x1400fba92  call    cs:__imp_RtlMapGenericMask
0x1400fba99  nop     dword ptr [rax+rax+00h]
0x1400fba9e  mov     rcx, [rbp+57h+var_A8]; Object
0x1400fbaa2  lea     rax, [rbp+57h+Handle]
0x1400fbaa6  mov     [rsp+0F0h+DeviceObject], rax; Handle
0x1400fbaab  mov     r9d, 2000000h; DesiredAccess
0x1400fbab1  mov     [rsp+0F0h+Exclusive], sil; AccessMode
0x1400fbab6  xor     r8d, r8d; PassedAccessState
0x1400fbab9  mov     edx, 240h; HandleAttributes
0x1400fbabe  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rsi; ObjectType
0x1400fbac3  call    cs:__imp_ObOpenObjectByPointer
0x1400fbaca  nop     dword ptr [rax+rax+00h]
0x1400fbacf  mov     ebx, eax
0x1400fbad1  test    eax, eax
0x1400fbad3  js      loc_1400FBBEF
0x1400fbad9  mov     rcx, [rbp+57h+Handle]; Handle
0x1400fbadd  lea     r8, UxDeviceObjectSDBytes; SecurityDescriptor
0x1400fbae4  lea     edx, [rsi+4]; SecurityInformation
0x1400fbae7  call    cs:__imp_ZwSetSecurityObject
0x1400fbaee  nop     dword ptr [rax+rax+00h]
0x1400fbaf3  mov     ebx, eax
0x1400fbaf5  test    eax, eax
0x1400fbaf7  js      loc_1400FBBEF
0x1400fbafd  mov     rcx, [rbp+57h+var_B0]; Object
0x1400fbb01  lea     rax, [rbp+57h+var_90]
0x1400fbb05  mov     [rsp+0F0h+DeviceObject], rax; Handle
0x1400fbb0a  mov     r9d, 2000000h; DesiredAccess
0x1400fbb10  mov     [rsp+0F0h+Exclusive], sil; AccessMode
0x1400fbb15  xor     r8d, r8d; PassedAccessState
0x1400fbb18  mov     edx, 240h; HandleAttributes
0x1400fbb1d  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rsi; ObjectType
0x1400fbb22  call    cs:__imp_ObOpenObjectByPointer
0x1400fbb29  nop     dword ptr [rax+rax+00h]
0x1400fbb2e  mov     ebx, eax
0x1400fbb30  test    eax, eax
0x1400fbb32  js      loc_1400FBBEF
0x1400fbb38  mov     rcx, [rbp+57h+var_90]; Handle
0x1400fbb3c  lea     r8, UxDeviceObjectSDBytes; SecurityDescriptor
0x1400fbb43  lea     edx, [rsi+4]; SecurityInformation
0x1400fbb46  call    cs:__imp_ZwSetSecurityObject
0x1400fbb4d  nop     dword ptr [rax+rax+00h]
0x1400fbb52  mov     ebx, eax
0x1400fbb54  test    eax, eax
0x1400fbb56  js      loc_1400FBBEF
0x1400fbb5c  mov     rcx, [rbp+57h+arg_18]; Object
0x1400fbb60  lea     rax, [rbp+57h+var_A0]
0x1400fbb64  mov     [rsp+0F0h+DeviceObject], rax; Handle
0x1400fbb69  mov     r9d, 2000000h; DesiredAccess
0x1400fbb6f  mov     [rsp+0F0h+Exclusive], sil; AccessMode
0x1400fbb74  xor     r8d, r8d; PassedAccessState
0x1400fbb77  mov     edx, 240h; HandleAttributes
0x1400fbb7c  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rsi; ObjectType
0x1400fbb81  call    cs:__imp_ObOpenObjectByPointer
0x1400fbb88  nop     dword ptr [rax+rax+00h]
0x1400fbb8d  mov     ebx, eax
0x1400fbb8f  test    eax, eax
0x1400fbb91  js      short loc_1400FBBEF
0x1400fbb93  mov     rcx, [rbp+57h+var_A0]; Handle
0x1400fbb97  lea     r8, UxDeviceObjectSDBytes; SecurityDescriptor
0x1400fbb9e  lea     edx, [rsi+4]; SecurityInformation
0x1400fbba1  call    cs:__imp_ZwSetSecurityObject
0x1400fbba8  nop     dword ptr [rax+rax+00h]
0x1400fbbad  mov     ebx, eax
0x1400fbbaf  test    eax, eax
0x1400fbbb1  js      short loc_1400FBBEF
0x1400fbbb3  mov     rax, [rbp+57h+arg_18]
0x1400fbbb7  mov     [rdi+1028h], rax
0x1400fbbbe  mov     rax, [rbp+57h+var_B0]
0x1400fbbc2  mov     [rdi+1020h], rax
0x1400fbbc9  mov     rax, [rbp+57h+var_A8]
0x1400fbbcd  mov     [rdi+1018h], rax
0x1400fbbd4  mov     rax, [rbp+57h+DirectoryHandle]
0x1400fbbd8  mov     [rdi+1010h], rax
0x1400fbbdf  mov     [rbp+57h+arg_18], rsi
0x1400fbbe3  mov     [rbp+57h+var_B0], rsi
0x1400fbbe7  mov     [rbp+57h+var_A8], rsi
0x1400fbbeb  mov     [rbp+57h+DirectoryHandle], rsi
0x1400fbbef  mov     rcx, [rbp+57h+var_A0]; Handle
0x1400fbbf3  test    rcx, rcx
0x1400fbbf6  jz      short loc_1400FBC08
0x1400fbbf8  call    cs:__imp_ZwClose
0x1400fbbff  nop     dword ptr [rax+rax+00h]
0x1400fbc04  mov     [rbp+57h+var_A0], rsi
0x1400fbc08  mov     rcx, [rbp+57h+Handle]; Handle
0x1400fbc0c  test    rcx, rcx
0x1400fbc0f  jz      short loc_1400FBC21
0x1400fbc11  call    cs:__imp_ZwClose
0x1400fbc18  nop     dword ptr [rax+rax+00h]
0x1400fbc1d  mov     [rbp+57h+Handle], rsi
0x1400fbc21  mov     rcx, [rbp+57h+var_90]; Handle
0x1400fbc25  test    rcx, rcx
0x1400fbc28  jz      short loc_1400FBC3A
0x1400fbc2a  call    cs:__imp_ZwClose
0x1400fbc31  nop     dword ptr [rax+rax+00h]
0x1400fbc36  mov     [rbp+57h+var_90], rsi
0x1400fbc3a  mov     rcx, [rbp+57h+arg_18]; DeviceObject
0x1400fbc3e  test    rcx, rcx
0x1400fbc41  jz      short loc_1400FBC53
0x1400fbc43  call    cs:__imp_IoDeleteDevice
0x1400fbc4a  nop     dword ptr [rax+rax+00h]
0x1400fbc4f  mov     [rbp+57h+arg_18], rsi
0x1400fbc53  mov     rcx, [rbp+57h+var_A8]; DeviceObject
0x1400fbc57  test    rcx, rcx
0x1400fbc5a  jz      short loc_1400FBC6C
0x1400fbc5c  call    cs:__imp_IoDeleteDevice
0x1400fbc63  nop     dword ptr [rax+rax+00h]
0x1400fbc68  mov     [rbp+57h+var_A8], rsi
0x1400fbc6c  mov     rcx, [rbp+57h+var_B0]; DeviceObject
0x1400fbc70  test    rcx, rcx
0x1400fbc73  jz      short loc_1400FBC85
0x1400fbc75  call    cs:__imp_IoDeleteDevice
0x1400fbc7c  nop     dword ptr [rax+rax+00h]
0x1400fbc81  mov     [rbp+57h+var_B0], rsi
0x1400fbc85  mov     rcx, [rbp+57h+DirectoryHandle]; Handle
0x1400fbc89  test    rcx, rcx
0x1400fbc8c  jz      short loc_1400FBC9A
0x1400fbc8e  call    cs:__imp_ZwClose
0x1400fbc95  nop     dword ptr [rax+rax+00h]
0x1400fbc9a  mov     eax, ebx
0x1400fbc9c  mov     rbx, [rsp+0F0h+arg_0]
0x1400fbca4  add     rsp, 0E0h
0x1400fbcab  pop     rdi
0x1400fbcac  pop     rsi
0x1400fbcad  pop     rbp
0x1400fbcae  retn
```
