# UxStartDeviceFacet

- ea: `0x1c00dbab0`
- end: `0x1c00dbe64`
- name: `UxStartDeviceFacet`
- size: `948`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1c00dbab0`

## import_xrefs

- `ntoskrnl!ZwCreateDirectoryObject` at `0x1c00dbb70`
- `ntoskrnl!ZwCreateDirectoryObject` at `0x1c00dbb70`
- `ntoskrnl!IoCreateDevice` at `0x1c00dbba9`
- `ntoskrnl!IoCreateDevice` at `0x1c00dbbe6`
- `ntoskrnl!IoCreateDevice` at `0x1c00dbc23`
- `ntoskrnl!IoCreateDevice` at `0x1c00dbba9`
- `ntoskrnl!IoCreateDevice` at `0x1c00dbbe6`
- `ntoskrnl!IoCreateDevice` at `0x1c00dbc23`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c00dbc49`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c00dbc49`
- `ntoskrnl!RtlMapGenericMask` at `0x1c00dbc5f`
- `ntoskrnl!RtlMapGenericMask` at `0x1c00dbc72`
- `ntoskrnl!RtlMapGenericMask` at `0x1c00dbc5f`
- `ntoskrnl!RtlMapGenericMask` at `0x1c00dbc72`
- `ntoskrnl!NtSetSecurityObject` at `0x1c00dbcc7`
- `ntoskrnl!NtSetSecurityObject` at `0x1c00dbd26`
- `ntoskrnl!NtSetSecurityObject` at `0x1c00dbd81`
- `ntoskrnl!NtSetSecurityObject` at `0x1c00dbcc7`
- `ntoskrnl!NtSetSecurityObject` at `0x1c00dbd26`
- `ntoskrnl!NtSetSecurityObject` at `0x1c00dbd81`
- `ntoskrnl!IoDeleteDevice` at `0x1c00feb90`
- `ntoskrnl!IoDeleteDevice` at `0x1c00feba5`
- `ntoskrnl!IoDeleteDevice` at `0x1c00febba`
- `ntoskrnl!IoDeleteDevice` at `0x1c00feb90`
- `ntoskrnl!IoDeleteDevice` at `0x1c00feba5`
- `ntoskrnl!IoDeleteDevice` at `0x1c00febba`
- `ntoskrnl!ZwClose` at `0x1c00dbdd8`
- `ntoskrnl!ZwClose` at `0x1c00dbdf1`
- `ntoskrnl!ZwClose` at `0x1c00dbe0a`
- `ntoskrnl!ZwClose` at `0x1c00febcf`
- `ntoskrnl!ZwClose` at `0x1c00dbdd8`
- `ntoskrnl!ZwClose` at `0x1c00dbdf1`
- `ntoskrnl!ZwClose` at `0x1c00dbe0a`
- `ntoskrnl!ZwClose` at `0x1c00febcf`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1c00dbca3`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1c00dbd02`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1c00dbd61`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1c00dbca3`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1c00dbd02`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1c00dbd61`

## string_xrefs

- `0x1c00dbae5`: `\Device\Http\Communication`

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
            v2 = NtSetSecurityObject(Handle, 4u, UxDeviceObjectSDBytes);
            if ( v2 >= 0 )
            {
              v2 = ObOpenObjectByPointer(v5, 0x240u, 0, 0x2000000u, 0, 0, &v9);
              if ( v2 >= 0 )
              {
                v2 = NtSetSecurityObject(v9, 4u, UxDeviceObjectSDBytes);
                if ( v2 >= 0 )
                {
                  v2 = ObOpenObjectByPointer(v18, 0x240u, 0, 0x2000000u, 0, 0, &v7);
                  if ( v2 >= 0 )
                  {
                    v2 = NtSetSecurityObject(v7, 4u, UxDeviceObjectSDBytes);
                    if ( v2 >= 0 )
                    {
                      a1[493] = v18;
                      a1[492] = v5;
                      a1[491] = DeviceObject;
                      a1[490] = DirectoryHandle;
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
0x1c00dbab0  mov     [rsp-8+arg_0], rbx
0x1c00dbab5  push    rbp
0x1c00dbab6  push    rsi
0x1c00dbab7  push    rdi
0x1c00dbab8  lea     rbp, [rsp-47h]
0x1c00dbabd  sub     rsp, 0E0h
0x1c00dbac4  xor     esi, esi
0x1c00dbac6  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1c00dbace  lea     rax, aDeviceHttp; "\\Device\\Http"
0x1c00dbad5  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1c00dbadd  mov     [rbp+57h+var_78], rax
0x1c00dbae1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1c00dbae5  lea     rax, aDeviceHttpComm; "\\Device\\Http\\Communication"
0x1c00dbaec  mov     [rbp+57h+var_80], 1A0018h
0x1c00dbaf4  mov     [rbp+57h+DeviceName.Buffer], rax
0x1c00dbaf8  mov     rdi, rcx
0x1c00dbafb  lea     rax, aDeviceHttpReqq; "\\Device\\Http\\ReqQueue"
0x1c00dbb02  mov     qword ptr [rbp+57h+DeviceName.Length], 360034h
0x1c00dbb0a  mov     [rbp+57h+var_60.Buffer], rax
0x1c00dbb0e  lea     rcx, [rbp+57h+DirectoryHandle]; DirectoryHandle
0x1c00dbb12  lea     rax, aDeviceHttpClie; "\\Device\\Http\\ClientSession"
0x1c00dbb19  mov     qword ptr [rbp+57h+var_60.Length], 2C002Ah
0x1c00dbb21  mov     [rbp+57h+var_50.Buffer], rax
0x1c00dbb25  xorps   xmm0, xmm0
0x1c00dbb28  lea     rax, [rbp+57h+var_80]
0x1c00dbb2c  mov     qword ptr [rbp+57h+var_50.Length], 360034h
0x1c00dbb34  mov     edx, 0F000Fh; DesiredAccess
0x1c00dbb39  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1c00dbb3d  mov     [rbp+57h+DirectoryHandle], rsi
0x1c00dbb41  mov     [rbp+57h+var_A8], rsi
0x1c00dbb45  mov     [rbp+57h+var_B0], rsi
0x1c00dbb49  mov     [rbp+57h+arg_18], rsi
0x1c00dbb4d  mov     [rbp+57h+Handle], rsi
0x1c00dbb51  mov     [rbp+57h+var_90], rsi
0x1c00dbb55  mov     [rbp+57h+var_A0], rsi
0x1c00dbb59  mov     [rbp+57h+AccessMask], 0C0000000h
0x1c00dbb60  mov     [rbp+57h+arg_10], 10000000h
0x1c00dbb67  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1c00dbb6b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00dbb70  call    cs:__imp_ZwCreateDirectoryObject
0x1c00dbb77  nop     dword ptr [rax+rax+00h]
0x1c00dbb7c  mov     ebx, eax
0x1c00dbb7e  test    eax, eax
0x1c00dbb80  js      loc_1C00DBDCF
0x1c00dbb86  mov     rcx, cs:UxDriverObject; DriverObject
0x1c00dbb8d  lea     rax, [rbp+57h+var_A8]
0x1c00dbb91  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x1c00dbb96  lea     r9d, [rsi+12h]; DeviceType
0x1c00dbb9a  mov     [rsp+0F0h+Exclusive], sil; Exclusive
0x1c00dbb9f  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x1c00dbba3  xor     edx, edx; DeviceExtensionSize
0x1c00dbba5  mov     [rsp+0F0h+DeviceCharacteristics], esi; DeviceCharacteristics
0x1c00dbba9  call    cs:__imp_IoCreateDevice
0x1c00dbbb0  nop     dword ptr [rax+rax+00h]
0x1c00dbbb5  mov     ebx, eax
0x1c00dbbb7  test    eax, eax
0x1c00dbbb9  js      loc_1C00DBDCF
0x1c00dbbbf  mov     rcx, cs:UxDriverObject; DriverObject
0x1c00dbbc6  lea     rax, [rbp+57h+var_B0]
0x1c00dbbca  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x1c00dbbcf  lea     r9d, [rsi+12h]; DeviceType
0x1c00dbbd3  mov     [rsp+0F0h+Exclusive], sil; Exclusive
0x1c00dbbd8  lea     r8, [rbp+57h+var_60]; DeviceName
0x1c00dbbdc  xor     edx, edx; DeviceExtensionSize
0x1c00dbbde  mov     [rsp+0F0h+DeviceCharacteristics], 20000h; DeviceCharacteristics
0x1c00dbbe6  call    cs:__imp_IoCreateDevice
0x1c00dbbed  nop     dword ptr [rax+rax+00h]
0x1c00dbbf2  mov     ebx, eax
0x1c00dbbf4  test    eax, eax
0x1c00dbbf6  js      loc_1C00DBDCF
0x1c00dbbfc  mov     rcx, cs:UxDriverObject; DriverObject
0x1c00dbc03  lea     rax, [rbp+57h+arg_18]
0x1c00dbc07  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x1c00dbc0c  lea     r9d, [rsi+12h]; DeviceType
0x1c00dbc10  mov     [rsp+0F0h+Exclusive], sil; Exclusive
0x1c00dbc15  lea     r8, [rbp+57h+var_50]; DeviceName
0x1c00dbc19  xor     edx, edx; DeviceExtensionSize
0x1c00dbc1b  mov     [rsp+0F0h+DeviceCharacteristics], 20000h; DeviceCharacteristics
0x1c00dbc23  call    cs:__imp_IoCreateDevice
0x1c00dbc2a  nop     dword ptr [rax+rax+00h]
0x1c00dbc2f  mov     ebx, eax
0x1c00dbc31  test    eax, eax
0x1c00dbc33  js      loc_1C00DBDCF
0x1c00dbc39  mov     rax, [rbp+57h+var_B0]
0x1c00dbc3d  mov     byte ptr [rax+4Ch], 4
0x1c00dbc41  mov     rax, [rbp+57h+arg_18]
0x1c00dbc45  mov     byte ptr [rax+4Ch], 4
0x1c00dbc49  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c00dbc50  nop     dword ptr [rax+rax+00h]
0x1c00dbc55  mov     rdx, rax; GenericMapping
0x1c00dbc58  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1c00dbc5c  mov     rbx, rax
0x1c00dbc5f  call    cs:__imp_RtlMapGenericMask
0x1c00dbc66  nop     dword ptr [rax+rax+00h]
0x1c00dbc6b  mov     rdx, rbx; GenericMapping
0x1c00dbc6e  lea     rcx, [rbp+57h+arg_10]; AccessMask
0x1c00dbc72  call    cs:__imp_RtlMapGenericMask
0x1c00dbc79  nop     dword ptr [rax+rax+00h]
0x1c00dbc7e  mov     rcx, [rbp+57h+var_A8]; Object
0x1c00dbc82  lea     rax, [rbp+57h+Handle]
0x1c00dbc86  mov     [rsp+0F0h+DeviceObject], rax; Handle
0x1c00dbc8b  mov     r9d, 2000000h; DesiredAccess
0x1c00dbc91  mov     [rsp+0F0h+Exclusive], sil; AccessMode
0x1c00dbc96  xor     r8d, r8d; PassedAccessState
0x1c00dbc99  mov     edx, 240h; HandleAttributes
0x1c00dbc9e  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rsi; ObjectType
0x1c00dbca3  call    cs:__imp_ObOpenObjectByPointer
0x1c00dbcaa  nop     dword ptr [rax+rax+00h]
0x1c00dbcaf  mov     ebx, eax
0x1c00dbcb1  test    eax, eax
0x1c00dbcb3  js      loc_1C00DBDCF
0x1c00dbcb9  mov     rcx, [rbp+57h+Handle]; Handle
0x1c00dbcbd  lea     r8, UxDeviceObjectSDBytes; SecurityDescriptor
0x1c00dbcc4  lea     edx, [rsi+4]; SecurityInformation
0x1c00dbcc7  call    cs:__imp_NtSetSecurityObject
0x1c00dbcce  nop     dword ptr [rax+rax+00h]
0x1c00dbcd3  mov     ebx, eax
0x1c00dbcd5  test    eax, eax
0x1c00dbcd7  js      loc_1C00DBDCF
0x1c00dbcdd  mov     rcx, [rbp+57h+var_B0]; Object
0x1c00dbce1  lea     rax, [rbp+57h+var_90]
0x1c00dbce5  mov     [rsp+0F0h+DeviceObject], rax; Handle
0x1c00dbcea  mov     r9d, 2000000h; DesiredAccess
0x1c00dbcf0  mov     [rsp+0F0h+Exclusive], sil; AccessMode
0x1c00dbcf5  xor     r8d, r8d; PassedAccessState
0x1c00dbcf8  mov     edx, 240h; HandleAttributes
0x1c00dbcfd  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rsi; ObjectType
0x1c00dbd02  call    cs:__imp_ObOpenObjectByPointer
0x1c00dbd09  nop     dword ptr [rax+rax+00h]
0x1c00dbd0e  mov     ebx, eax
0x1c00dbd10  test    eax, eax
0x1c00dbd12  js      loc_1C00DBDCF
0x1c00dbd18  mov     rcx, [rbp+57h+var_90]; Handle
0x1c00dbd1c  lea     r8, UxDeviceObjectSDBytes; SecurityDescriptor
0x1c00dbd23  lea     edx, [rsi+4]; SecurityInformation
0x1c00dbd26  call    cs:__imp_NtSetSecurityObject
0x1c00dbd2d  nop     dword ptr [rax+rax+00h]
0x1c00dbd32  mov     ebx, eax
0x1c00dbd34  test    eax, eax
0x1c00dbd36  js      loc_1C00DBDCF
0x1c00dbd3c  mov     rcx, [rbp+57h+arg_18]; Object
0x1c00dbd40  lea     rax, [rbp+57h+var_A0]
0x1c00dbd44  mov     [rsp+0F0h+DeviceObject], rax; Handle
0x1c00dbd49  mov     r9d, 2000000h; DesiredAccess
0x1c00dbd4f  mov     [rsp+0F0h+Exclusive], sil; AccessMode
0x1c00dbd54  xor     r8d, r8d; PassedAccessState
0x1c00dbd57  mov     edx, 240h; HandleAttributes
0x1c00dbd5c  mov     qword ptr [rsp+0F0h+DeviceCharacteristics], rsi; ObjectType
0x1c00dbd61  call    cs:__imp_ObOpenObjectByPointer
0x1c00dbd68  nop     dword ptr [rax+rax+00h]
0x1c00dbd6d  mov     ebx, eax
0x1c00dbd6f  test    eax, eax
0x1c00dbd71  js      short loc_1C00DBDCF
0x1c00dbd73  mov     rcx, [rbp+57h+var_A0]; Handle
0x1c00dbd77  lea     r8, UxDeviceObjectSDBytes; SecurityDescriptor
0x1c00dbd7e  lea     edx, [rsi+4]; SecurityInformation
0x1c00dbd81  call    cs:__imp_NtSetSecurityObject
0x1c00dbd88  nop     dword ptr [rax+rax+00h]
0x1c00dbd8d  mov     ebx, eax
0x1c00dbd8f  test    eax, eax
0x1c00dbd91  js      short loc_1C00DBDCF
0x1c00dbd93  mov     rax, [rbp+57h+arg_18]
0x1c00dbd97  mov     [rdi+0F68h], rax
0x1c00dbd9e  mov     rax, [rbp+57h+var_B0]
0x1c00dbda2  mov     [rdi+0F60h], rax
0x1c00dbda9  mov     rax, [rbp+57h+var_A8]
0x1c00dbdad  mov     [rdi+0F58h], rax
0x1c00dbdb4  mov     rax, [rbp+57h+DirectoryHandle]
0x1c00dbdb8  mov     [rdi+0F50h], rax
0x1c00dbdbf  mov     [rbp+57h+arg_18], rsi
0x1c00dbdc3  mov     [rbp+57h+var_B0], rsi
0x1c00dbdc7  mov     [rbp+57h+var_A8], rsi
0x1c00dbdcb  mov     [rbp+57h+DirectoryHandle], rsi
0x1c00dbdcf  mov     rcx, [rbp+57h+var_A0]; Handle
0x1c00dbdd3  test    rcx, rcx
0x1c00dbdd6  jz      short loc_1C00DBDE8
0x1c00dbdd8  call    cs:__imp_ZwClose
0x1c00dbddf  nop     dword ptr [rax+rax+00h]
0x1c00dbde4  mov     [rbp+57h+var_A0], rsi
0x1c00dbde8  mov     rcx, [rbp+57h+Handle]; Handle
0x1c00dbdec  test    rcx, rcx
0x1c00dbdef  jz      short loc_1C00DBE01
0x1c00dbdf1  call    cs:__imp_ZwClose
0x1c00dbdf8  nop     dword ptr [rax+rax+00h]
0x1c00dbdfd  mov     [rbp+57h+Handle], rsi
0x1c00dbe01  mov     rcx, [rbp+57h+var_90]; Handle
0x1c00dbe05  test    rcx, rcx
0x1c00dbe08  jz      short loc_1C00DBE1A
0x1c00dbe0a  call    cs:__imp_ZwClose
0x1c00dbe11  nop     dword ptr [rax+rax+00h]
0x1c00dbe16  mov     [rbp+57h+var_90], rsi
0x1c00dbe1a  mov     rcx, [rbp+57h+arg_18]; DeviceObject
0x1c00dbe1e  test    rcx, rcx
0x1c00dbe21  jnz     loc_1C00FEB90
0x1c00dbe27  mov     rcx, [rbp+57h+var_A8]; DeviceObject
0x1c00dbe2b  test    rcx, rcx
0x1c00dbe2e  jnz     loc_1C00FEBA5
0x1c00dbe34  mov     rcx, [rbp+57h+var_B0]; DeviceObject
0x1c00dbe38  test    rcx, rcx
0x1c00dbe3b  jnz     loc_1C00FEBBA
0x1c00dbe41  mov     rcx, [rbp+57h+DirectoryHandle]; Handle
0x1c00dbe45  test    rcx, rcx
0x1c00dbe48  jnz     loc_1C00FEBCF
0x1c00dbe4e  mov     eax, ebx
0x1c00dbe50  mov     rbx, [rsp+0F0h+arg_0]
0x1c00dbe58  add     rsp, 0E0h
0x1c00dbe5f  pop     rdi
0x1c00dbe60  pop     rsi
0x1c00dbe61  pop     rbp
0x1c00dbe62  retn
0x1c00feb90  call    cs:__imp_IoDeleteDevice
0x1c00feb97  nop     dword ptr [rax+rax+00h]
0x1c00feb9c  mov     [rbp+57h+arg_18], rsi
0x1c00feba0  jmp     loc_1C00DBE27
0x1c00feba5  call    cs:__imp_IoDeleteDevice
0x1c00febac  nop     dword ptr [rax+rax+00h]
0x1c00febb1  mov     [rbp+57h+var_A8], rsi
0x1c00febb5  jmp     loc_1C00DBE34
0x1c00febba  call    cs:__imp_IoDeleteDevice
0x1c00febc1  nop     dword ptr [rax+rax+00h]
0x1c00febc6  mov     [rbp+57h+var_B0], rsi
0x1c00febca  jmp     loc_1C00DBE41
0x1c00febcf  call    cs:__imp_ZwClose
0x1c00febd6  nop     dword ptr [rax+rax+00h]
0x1c00febdb  nop
0x1c00febdc  jmp     loc_1C00DBE4E
```
