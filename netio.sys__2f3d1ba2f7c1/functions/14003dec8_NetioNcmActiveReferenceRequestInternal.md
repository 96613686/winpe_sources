# NetioNcmActiveReferenceRequestInternal

- ea: `0x14003dec8`
- end: `0x14003e207`
- name: `NetioNcmActiveReferenceRequestInternal`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14003dd90`

## callees

- `0x14003dec8`
- `0x140050ea4`
- `0x1400512d8`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003e0ec`
- `ntoskrnl!ObfDereferenceObject` at `0x14003e0ec`
- `ntoskrnl!ZwClose` at `0x14003e109`
- `ntoskrnl!ZwClose` at `0x14003e109`
- `ntoskrnl!KeInitializeEvent` at `0x14003dfed`
- `ntoskrnl!KeInitializeEvent` at `0x14003dfed`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007d353`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007d353`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003e06a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003e06a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14003e0aa`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14003e0aa`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003e016`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003e016`
- `ntoskrnl!IoCreateFile` at `0x14003dfbe`
- `ntoskrnl!IoCreateFile` at `0x14003dfbe`
- `ntoskrnl!IofCallDriver` at `0x14003e0d0`
- `ntoskrnl!IofCallDriver` at `0x14003e0d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003df44`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003df44`

## pseudocode

```c
__int64 __fastcall NetioNcmActiveReferenceRequestInternal(__int64 a1, int a2, char a3, void **a4)
{
  NTSTATUS Status; // edi
  ULONG v9; // r14d
  void *v10; // rcx
  struct _FILE_OBJECT *v12; // rbx
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rdi
  PIRP v14; // rax
  PVOID Object; // [rsp+70h] [rbp-69h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-61h] BYREF
  struct _KEVENT Event; // [rsp+88h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-9h] BYREF
  __int128 InputBuffer; // [rsp+E0h] [rbp+7h] BYREF
  __int64 v21; // [rsp+F0h] [rbp+17h]

  v21 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  InputBuffer = 0;
  DestinationString = 0;
  memset(&Event, 0, sizeof(Event));
  if ( a3 )
  {
    v9 = 1507468;
    if ( !*a4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids);
      }
      Status = -1073741811;
      goto LABEL_11;
    }
  }
  else
  {
    *a4 = 0;
    RtlInitUnicodeString(&DestinationString, L"\\Device\\Ndis");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Status = IoCreateFile(
               a4,
               0x2000000u,
               &ObjectAttributes,
               &IoStatusBlock,
               0,
               0,
               3u,
               1u,
               0,
               0,
               0,
               CreateFileTypeNone,
               0,
               0x101u);
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          48,
          WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids,
          (unsigned int)Status);
      }
      goto LABEL_11;
    }
    v9 = 1507464;
  }
  *((_QWORD *)&InputBuffer + 1) = a1;
  LODWORD(v21) = a2;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v10 = *a4;
  Object = 0;
  Status = ObReferenceObjectByHandle(v10, 0, 0, 0, &Object, 0);
  if ( Status >= 0 )
  {
    v12 = (struct _FILE_OBJECT *)Object;
    RelatedDeviceObject = IoGetRelatedDeviceObject((PFILE_OBJECT)Object);
    v14 = IoBuildDeviceIoControlRequest(v9, RelatedDeviceObject, &InputBuffer, 0x18u, 0, 0, 0, &Event, &IoStatusBlock);
    if ( v14 )
    {
      v14->Tail.Overlay.CurrentStackLocation[-1].FileObject = v12;
      Status = IofCallDriver(RelatedDeviceObject, v14);
      if ( Status == 259 )
      {
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        Status = IoStatusBlock.Status;
        if ( IoStatusBlock.Status < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            51,
            WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids,
            (unsigned int)IoStatusBlock.Status);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids);
      }
      Status = -1073741670;
    }
    ObfDereferenceObject(v12);
  }
  if ( a3 || Status < 0 )
  {
LABEL_11:
    if ( *a4 )
    {
      ZwClose(*a4);
      *a4 = 0;
    }
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14003dec8  mov     [rsp-8+arg_10], rbx
0x14003decd  push    rbp
0x14003dece  push    rsi
0x14003decf  push    rdi
0x14003ded0  push    r12
0x14003ded2  push    r13
0x14003ded4  push    r14
0x14003ded6  push    r15
0x14003ded8  lea     rbp, [rsp-27h]
0x14003dedd  sub     rsp, 100h
0x14003dee4  mov     rax, cs:__security_cookie
0x14003deeb  xor     rax, rsp
0x14003deee  mov     [rbp+57h+var_38], rax
0x14003def2  xorps   xmm0, xmm0
0x14003def5  xor     eax, eax
0x14003def7  xorps   xmm1, xmm1
0x14003defa  mov     [rbp+57h+var_40], rax
0x14003defe  xor     r13d, r13d
0x14003df01  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14003df05  mov     rsi, r9
0x14003df08  mov     r15b, r8b
0x14003df0b  mov     r12d, edx
0x14003df0e  mov     rbx, rcx
0x14003df11  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14003df15  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14003df19  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14003df1d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14003df21  movups  [rbp+57h+InputBuffer], xmm1
0x14003df25  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003df29  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x14003df2d  test    r8b, r8b
0x14003df30  jnz     loc_14003E11D
0x14003df36  lea     rdx, aDeviceNdis_0; "\\Device\\Ndis"
0x14003df3d  mov     [r9], r13
0x14003df40  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003df44  call    cs:__imp_RtlInitUnicodeString
0x14003df4b  nop     dword ptr [rax+rax+00h]
0x14003df50  mov     [rsp+130h+Options], 101h; Options
0x14003df58  lea     rax, [rbp+57h+DestinationString]
0x14003df5c  mov     [rsp+130h+InternalParameters], r13; InternalParameters
0x14003df61  lea     r14d, [r13+30h]
0x14003df65  mov     [rsp+130h+CreateFileType], r13d; CreateFileType
0x14003df6a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14003df6e  mov     [rsp+130h+EaLength], r13d; EaLength
0x14003df73  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14003df77  mov     [rsp+130h+EaBuffer], r13; EaBuffer
0x14003df7c  xorps   xmm0, xmm0
0x14003df7f  mov     [rsp+130h+CreateOptions], r13d; CreateOptions
0x14003df84  mov     edx, 2000000h; DesiredAccess
0x14003df89  mov     [rsp+130h+Disposition], 1; Disposition
0x14003df91  mov     rcx, rsi; FileHandle
0x14003df94  mov     [rsp+130h+ShareAccess], 3; ShareAccess
0x14003df9c  mov     [rsp+130h+FileAttributes], r13d; FileAttributes
0x14003dfa1  mov     [rsp+130h+AllocationSize], r13; AllocationSize
0x14003dfa6  mov     [rbp+57h+ObjectAttributes.Length], r14d
0x14003dfaa  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x14003dfae  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14003dfb5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14003dfb9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003dfbe  call    cs:__imp_IoCreateFile
0x14003dfc5  nop     dword ptr [rax+rax+00h]
0x14003dfca  mov     edi, eax
0x14003dfcc  test    eax, eax
0x14003dfce  js      loc_14003E175
0x14003dfd4  mov     r14d, 170088h
0x14003dfda  xor     r8d, r8d; State
0x14003dfdd  mov     qword ptr [rbp+57h+InputBuffer+8], rbx
0x14003dfe1  lea     rcx, [rbp+57h+Event]; Event
0x14003dfe5  mov     dword ptr [rbp+57h+var_40], r12d
0x14003dfe9  lea     edx, [r8+1]; Type
0x14003dfed  call    cs:__imp_KeInitializeEvent
0x14003dff4  nop     dword ptr [rax+rax+00h]
0x14003dff9  mov     rcx, [rsi]; Handle
0x14003dffc  lea     rax, [rbp+57h+Object]
0x14003e000  mov     qword ptr [rsp+130h+FileAttributes], r13; HandleInformation
0x14003e005  xor     r9d, r9d; AccessMode
0x14003e008  xor     r8d, r8d; ObjectType
0x14003e00b  mov     [rsp+130h+AllocationSize], rax; Object
0x14003e010  xor     edx, edx; DesiredAccess
0x14003e012  mov     [rbp+57h+Object], r13
0x14003e016  call    cs:__imp_ObReferenceObjectByHandle
0x14003e01d  nop     dword ptr [rax+rax+00h]
0x14003e022  mov     edi, eax
0x14003e024  test    eax, eax
0x14003e026  jns     short loc_14003E063
0x14003e028  test    r15b, r15b
0x14003e02b  jnz     loc_14003E0FD
0x14003e031  test    edi, edi
0x14003e033  js      loc_14003E0FD
0x14003e039  mov     eax, edi
0x14003e03b  mov     rcx, [rbp+57h+var_38]
0x14003e03f  xor     rcx, rsp; StackCookie
0x14003e042  call    __security_check_cookie
0x14003e047  mov     rbx, [rsp+130h+arg_10]
0x14003e04f  add     rsp, 100h
0x14003e056  pop     r15
0x14003e058  pop     r14
0x14003e05a  pop     r13
0x14003e05c  pop     r12
0x14003e05e  pop     rdi
0x14003e05f  pop     rsi
0x14003e060  pop     rbp
0x14003e061  retn
0x14003e063  mov     rbx, [rbp+57h+Object]
0x14003e067  mov     rcx, rbx; FileObject
0x14003e06a  call    cs:__imp_IoGetRelatedDeviceObject
0x14003e071  nop     dword ptr [rax+rax+00h]
0x14003e076  mov     r9d, 18h; InputBufferLength
0x14003e07c  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x14003e080  mov     rdi, rax
0x14003e083  mov     ecx, r14d; IoControlCode
0x14003e086  lea     rax, [rbp+57h+IoStatusBlock]
0x14003e08a  mov     rdx, rdi; DeviceObject
0x14003e08d  mov     qword ptr [rsp+130h+CreateOptions], rax; IoStatusBlock
0x14003e092  lea     rax, [rbp+57h+Event]
0x14003e096  mov     qword ptr [rsp+130h+Disposition], rax; Event
0x14003e09b  mov     byte ptr [rsp+130h+ShareAccess], r13b; InternalDeviceIoControl
0x14003e0a0  mov     [rsp+130h+FileAttributes], r13d; OutputBufferLength
0x14003e0a5  mov     [rsp+130h+AllocationSize], r13; OutputBuffer
0x14003e0aa  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14003e0b1  nop     dword ptr [rax+rax+00h]
0x14003e0b6  mov     rdx, rax; Irp
0x14003e0b9  test    rax, rax
0x14003e0bc  jz      loc_14003E1BE
0x14003e0c2  mov     rax, [rax+0B8h]
0x14003e0c9  mov     rcx, rdi; DeviceObject
0x14003e0cc  mov     [rax-18h], rbx
0x14003e0d0  call    cs:__imp_IofCallDriver
0x14003e0d7  nop     dword ptr [rax+rax+00h]
0x14003e0dc  mov     edi, eax
0x14003e0de  cmp     eax, 103h
0x14003e0e3  jz      loc_14007D342
0x14003e0e9  mov     rcx, rbx; Object
0x14003e0ec  call    cs:__imp_ObfDereferenceObject
0x14003e0f3  nop     dword ptr [rax+rax+00h]
0x14003e0f8  jmp     loc_14003E028
0x14003e0fd  mov     rcx, [rsi]; Handle
0x14003e100  test    rcx, rcx
0x14003e103  jz      loc_14003E039
0x14003e109  call    cs:__imp_ZwClose
0x14003e110  nop     dword ptr [rax+rax+00h]
0x14003e115  mov     [rsi], r13
0x14003e118  jmp     loc_14003E039
0x14003e11d  mov     r14d, 17008Ch
0x14003e123  cmp     [r9], r13
0x14003e126  jnz     loc_14003DFDA
0x14003e12c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e133  lea     rax, WPP_GLOBAL_Control
0x14003e13a  cmp     rcx, rax
0x14003e13d  jz      loc_14007D32E
0x14003e143  cmp     byte ptr [rcx+29h], 3
0x14003e147  jb      loc_14007D32E
0x14003e14d  test    dword ptr [rcx+2Ch], 200000h
0x14003e154  jz      loc_14007D32E
0x14003e15a  mov     rcx, [rcx+18h]
0x14003e15e  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14003e165  mov     edx, 31h ; '1'
0x14003e16a  call    WPP_SF_
0x14003e16f  nop
0x14003e170  jmp     loc_14007D32E
0x14003e175  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e17c  lea     rax, WPP_GLOBAL_Control
0x14003e183  cmp     rcx, rax
0x14003e186  jz      loc_14003E0FD
0x14003e18c  cmp     byte ptr [rcx+29h], 3
0x14003e190  jb      loc_14003E0FD
0x14003e196  test    dword ptr [rcx+2Ch], 200000h
0x14003e19d  jz      loc_14003E0FD
0x14003e1a3  mov     rcx, [rcx+18h]
0x14003e1a7  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14003e1ae  mov     edx, r14d
0x14003e1b1  mov     r9d, edi
0x14003e1b4  call    WPP_SF_d
0x14003e1b9  jmp     loc_14003E0FD
0x14003e1be  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e1c5  lea     rax, WPP_GLOBAL_Control
0x14003e1cc  cmp     rcx, rax
0x14003e1cf  jz      loc_14007D338
0x14003e1d5  cmp     byte ptr [rcx+29h], 3
0x14003e1d9  jb      loc_14007D338
0x14003e1df  test    dword ptr [rcx+2Ch], 200000h
0x14003e1e6  jz      loc_14007D338
0x14003e1ec  mov     rcx, [rcx+18h]
0x14003e1f0  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14003e1f7  mov     edx, 32h ; '2'
0x14003e1fc  call    WPP_SF_
0x14003e201  nop
0x14003e202  jmp     loc_14007D338
0x14007d32e  mov     edi, 0C000000Dh
0x14007d333  jmp     loc_14003E0FD
0x14007d338  mov     edi, 0C000009Ah
0x14007d33d  jmp     loc_14003E0E9
0x14007d342  xor     r9d, r9d; Alertable
0x14007d345  mov     [rsp+130h+AllocationSize], r13; Timeout
0x14007d34a  xor     r8d, r8d; WaitMode
0x14007d34d  lea     rcx, [rbp+57h+Event]; Object
0x14007d351  xor     edx, edx; WaitReason
0x14007d353  call    cs:__imp_KeWaitForSingleObject
0x14007d35a  nop     dword ptr [rax+rax+00h]
0x14007d35f  mov     edi, dword ptr [rbp+57h+IoStatusBlock]
0x14007d362  test    edi, edi
0x14007d364  jns     loc_14003E0E9
0x14007d36a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d371  lea     rax, WPP_GLOBAL_Control
0x14007d378  cmp     rcx, rax
0x14007d37b  jz      loc_14003E0E9
0x14007d381  cmp     byte ptr [rcx+29h], 3
0x14007d385  jb      loc_14003E0E9
0x14007d38b  test    dword ptr [rcx+2Ch], 200000h
0x14007d392  jz      loc_14003E0E9
0x14007d398  mov     rcx, [rcx+18h]
0x14007d39c  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14007d3a3  mov     edx, 33h ; '3'
0x14007d3a8  mov     r9d, edi
0x14007d3ab  call    WPP_SF_d
0x14007d3b0  nop
0x14007d3b1  jmp     loc_14003E0E9
```
