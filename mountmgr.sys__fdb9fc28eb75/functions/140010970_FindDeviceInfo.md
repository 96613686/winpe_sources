# FindDeviceInfo

- ea: `0x140010970`
- end: `0x140010cf4`
- name: `FindDeviceInfo`
- size: `900`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c9f8`
- `0x14000cb00`
- `0x14000db54`
- `0x14000e340`
- `0x14000ecbc`
- `0x14000f680`
- `0x140010800`
- `0x1400119a0`

## callees

- `0x140001ae0`
- `0x140010970`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140010b86`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140010b86`
- `ntoskrnl!ObfDereferenceObject` at `0x140010b41`
- `ntoskrnl!ObfDereferenceObject` at `0x140010b55`
- `ntoskrnl!ObfDereferenceObject` at `0x140010ca7`
- `ntoskrnl!ObfDereferenceObject` at `0x140010b41`
- `ntoskrnl!ObfDereferenceObject` at `0x140010b55`
- `ntoskrnl!ObfDereferenceObject` at `0x140010ca7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400109a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400109a3`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140010aa6`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140010aa6`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400109ca`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400109ca`
- `ntoskrnl!ExAllocatePool2` at `0x140010a39`
- `ntoskrnl!ExAllocatePool2` at `0x140010a39`
- `ntoskrnl!IofCallDriver` at `0x140010ad1`
- `ntoskrnl!IofCallDriver` at `0x140010ad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010b2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010ba0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010b2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010ba0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c11`
- `ntoskrnl!KeInitializeEvent` at `0x140010a6b`
- `ntoskrnl!KeInitializeEvent` at `0x140010a6b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010be0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010be0`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140010b15`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140010b15`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400109f3`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400109f3`

## pseudocode

```c
__int64 __fastcall FindDeviceInfo(__int64 a1, struct _UNICODE_STRING *a2, __int64 a3, const UNICODE_STRING **a4)
{
  NTSTATUS DeviceObjectPointer; // ebx
  __int64 v8; // r8
  PDEVICE_OBJECT AttachedDeviceReference; // rax
  PFILE_OBJECT v10; // rsi
  struct _DEVICE_OBJECT *v11; // r12
  USHORT *OutputBuffer; // rdi
  unsigned int v13; // eax
  ULONG OutputBufferLength; // r13d
  PIRP v15; // rax
  const UNICODE_STRING *v16; // rbx
  __int64 *v17; // rdi
  const UNICODE_STRING *i; // rsi
  __int64 v19; // r8
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-49h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+58h] [rbp-41h] BYREF
  UNICODE_STRING StringIn; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-19h] BYREF
  struct _KEVENT Event; // [rsp+90h] [rbp-9h] BYREF
  unsigned int v27; // [rsp+110h] [rbp+77h]

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  DeviceObject = 0;
  FileObject = 0;
  DeviceObjectPointer = IoGetDeviceObjectPointer(a2, 0x80u, &FileObject, &DeviceObject);
  if ( DeviceObjectPointer < 0 )
  {
LABEL_36:
    if ( FileObject )
      ObfDereferenceObject(FileObject);
    goto LABEL_30;
  }
  if ( FileObject->FileName.Length )
  {
    DeviceObjectPointer = -1073741772;
    goto LABEL_36;
  }
  AttachedDeviceReference = IoGetAttachedDeviceReference(FileObject->DeviceObject);
  v10 = FileObject;
  v11 = AttachedDeviceReference;
  FileObject = 0;
  OutputBuffer = 0;
  DeviceObjectPointer = 0;
  v13 = 0;
  StringIn = 0;
  OutputBufferLength = 258;
  while ( 1 )
  {
    v27 = v13;
    if ( v13 >= 2 )
    {
      if ( DeviceObjectPointer >= 0 )
      {
LABEL_12:
        StringIn.Length = *OutputBuffer;
        StringIn.MaximumLength = *OutputBuffer;
        StringIn.Buffer = OutputBuffer + 1;
        DeviceObjectPointer = RtlDuplicateUnicodeString(1u, &StringIn, &DestinationString);
      }
      if ( !OutputBuffer )
        goto LABEL_15;
LABEL_14:
      ExFreePoolWithTag(OutputBuffer, 0);
      goto LABEL_15;
    }
    OutputBuffer = (USHORT *)ExAllocatePool2(258, OutputBufferLength, 1098149453);
    if ( !OutputBuffer )
      break;
    memset(&Event, 0, sizeof(Event));
    IoStatusBlock = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v15 = IoBuildDeviceIoControlRequest(
            0x4D0008u,
            v11,
            0,
            0,
            OutputBuffer,
            OutputBufferLength,
            0,
            &Event,
            &IoStatusBlock);
    if ( !v15 )
    {
      DeviceObjectPointer = -1073741670;
      goto LABEL_14;
    }
    if ( v10 )
      v15->Tail.Overlay.CurrentStackLocation[-1].FileObject = v10;
    DeviceObjectPointer = IofCallDriver(v11, v15);
    if ( DeviceObjectPointer == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      DeviceObjectPointer = IoStatusBlock.Status;
    }
    if ( DeviceObjectPointer >= 0 )
      goto LABEL_12;
    if ( DeviceObjectPointer != -2147483643 )
      goto LABEL_14;
    OutputBufferLength = (*OutputBuffer & 0xFFFE) + 2;
    ExFreePoolWithTag(OutputBuffer, 0);
    v13 = v27 + 1;
  }
  DeviceObjectPointer = -1073741670;
LABEL_15:
  if ( v11 )
    ObfDereferenceObject(v11);
  if ( v10 )
    ObfDereferenceObject(v10);
  if ( DeviceObjectPointer >= 0 )
  {
    v16 = *(const UNICODE_STRING **)(a1 + 16);
    v17 = (__int64 *)(a1 + 16);
    for ( i = 0; v16 != (const UNICODE_STRING *)v17; v16 = *(const UNICODE_STRING **)&v16->Length )
    {
      i = v16;
      if ( RtlEqualUnicodeString(&DestinationString, v16 + 5, 1u) )
        break;
    }
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    if ( v16 == (const UNICODE_STRING *)v17 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L((__int64)WPP_GLOBAL_Control->AttachedDevice, 0x12u, v19, -1073741772);
      return 3221225524LL;
    }
    else
    {
      *a4 = i;
      return 0;
    }
  }
LABEL_30:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_L((__int64)WPP_GLOBAL_Control->AttachedDevice, 0x11u, v8, DeviceObjectPointer);
  }
  return (unsigned int)DeviceObjectPointer;
}

```

## disassembly

```asm
0x140010970  mov     byte ptr [rsp-8+arg_10], r8b
0x140010975  push    rbp
0x140010976  push    rbx
0x140010977  push    rsi
0x140010978  push    rdi
0x140010979  push    r12
0x14001097b  push    r13
0x14001097d  push    r14
0x14001097f  push    r15
0x140010981  lea     rbp, [rsp-1Fh]
0x140010986  sub     rsp, 0B8h
0x14001098d  mov     rbx, rdx
0x140010990  mov     r15, rcx
0x140010993  xorps   xmm0, xmm0
0x140010996  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001099a  xor     edx, edx; SourceString
0x14001099c  mov     r14, r9
0x14001099f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400109a3  call    cs:__imp_RtlInitUnicodeString
0x1400109aa  nop     dword ptr [rax+rax+00h]
0x1400109af  xor     r13d, r13d
0x1400109b2  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x1400109b6  lea     r8, [rbp+57h+FileObject]; FileObject
0x1400109ba  mov     [rbp+57h+DeviceObject], r13
0x1400109be  mov     edx, 80h; DesiredAccess
0x1400109c3  mov     [rbp+57h+FileObject], r13
0x1400109c7  mov     rcx, rbx; ObjectName
0x1400109ca  call    cs:__imp_IoGetDeviceObjectPointer
0x1400109d1  nop     dword ptr [rax+rax+00h]
0x1400109d6  mov     rcx, [rbp+57h+FileObject]; Object
0x1400109da  mov     ebx, eax
0x1400109dc  test    eax, eax
0x1400109de  js      loc_140010CA2
0x1400109e4  cmp     [rcx+58h], r13w
0x1400109e9  jnz     loc_140010C9D
0x1400109ef  mov     rcx, [rcx+8]; DeviceObject
0x1400109f3  call    cs:__imp_IoGetAttachedDeviceReference
0x1400109fa  nop     dword ptr [rax+rax+00h]
0x1400109ff  mov     rsi, [rbp+57h+FileObject]
0x140010a03  mov     r12, rax
0x140010a06  mov     [rbp+57h+FileObject], r13
0x140010a0a  xorps   xmm0, xmm0
0x140010a0d  mov     rdi, r13
0x140010a10  mov     ebx, r13d
0x140010a13  xor     eax, eax
0x140010a15  movups  xmmword ptr [rbp+57h+StringIn.Length], xmm0
0x140010a19  mov     r13d, 102h
0x140010a1f  mov     [rbp+57h+arg_10], eax
0x140010a22  cmp     eax, 2
0x140010a25  jnb     loc_140010CE7
0x140010a2b  mov     edx, r13d
0x140010a2e  mov     ecx, 102h
0x140010a33  mov     r8d, 41746E4Dh
0x140010a39  call    cs:__imp_ExAllocatePool2
0x140010a40  nop     dword ptr [rax+rax+00h]
0x140010a45  mov     rdi, rax
0x140010a48  test    rax, rax
0x140010a4b  jz      loc_140010CC2
0x140010a51  xorps   xmm0, xmm0
0x140010a54  lea     rcx, [rbp+57h+Event]; Event
0x140010a58  xor     eax, eax
0x140010a5a  xor     r8d, r8d; State
0x140010a5d  xor     edx, edx; Type
0x140010a5f  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x140010a63  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x140010a67  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x140010a6b  call    cs:__imp_KeInitializeEvent
0x140010a72  nop     dword ptr [rax+rax+00h]
0x140010a77  lea     rax, [rbp+57h+var_70]
0x140010a7b  xor     r9d, r9d; InputBufferLength
0x140010a7e  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x140010a83  xor     r8d, r8d; InputBuffer
0x140010a86  lea     rax, [rbp+57h+Event]
0x140010a8a  mov     rdx, r12; DeviceObject
0x140010a8d  mov     [rsp+0F0h+var_B8], rax; Event
0x140010a92  mov     ecx, 4D0008h; IoControlCode
0x140010a97  mov     [rsp+0F0h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140010a9c  mov     [rsp+0F0h+OutputBufferLength], r13d; OutputBufferLength
0x140010aa1  mov     [rsp+0F0h+OutputBuffer], rdi; OutputBuffer
0x140010aa6  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140010aad  nop     dword ptr [rax+rax+00h]
0x140010ab2  mov     rdx, rax; Irp
0x140010ab5  test    rax, rax
0x140010ab8  jz      loc_140010CDD
0x140010abe  test    rsi, rsi
0x140010ac1  jz      short loc_140010ACE
0x140010ac3  mov     rax, [rax+0B8h]
0x140010aca  mov     [rax-18h], rsi
0x140010ace  mov     rcx, r12; DeviceObject
0x140010ad1  call    cs:__imp_IofCallDriver
0x140010ad8  nop     dword ptr [rax+rax+00h]
0x140010add  mov     ebx, eax
0x140010adf  cmp     eax, 103h
0x140010ae4  jz      loc_140010BCB
0x140010aea  test    ebx, ebx
0x140010aec  js      loc_140010BF4
0x140010af2  movzx   eax, word ptr [rdi]
0x140010af5  lea     r8, [rbp+57h+DestinationString]; StringOut
0x140010af9  mov     [rbp+57h+StringIn.Length], ax
0x140010afd  lea     rdx, [rbp+57h+StringIn]; StringIn
0x140010b01  movzx   eax, word ptr [rdi]
0x140010b04  mov     ecx, 1; Flags
0x140010b09  mov     [rbp+57h+StringIn.MaximumLength], ax
0x140010b0d  lea     rax, [rdi+2]
0x140010b11  mov     [rbp+57h+StringIn.Buffer], rax
0x140010b15  call    cs:__imp_RtlDuplicateUnicodeString
0x140010b1c  nop     dword ptr [rax+rax+00h]
0x140010b21  mov     ebx, eax
0x140010b23  test    rdi, rdi
0x140010b26  jz      short loc_140010B39
0x140010b28  xor     edx, edx; Tag
0x140010b2a  mov     rcx, rdi; P
0x140010b2d  call    cs:__imp_ExFreePoolWithTag
0x140010b34  nop     dword ptr [rax+rax+00h]
0x140010b39  test    r12, r12
0x140010b3c  jz      short loc_140010B4D
0x140010b3e  mov     rcx, r12; Object
0x140010b41  call    cs:__imp_ObfDereferenceObject
0x140010b48  nop     dword ptr [rax+rax+00h]
0x140010b4d  test    rsi, rsi
0x140010b50  jz      short loc_140010B61
0x140010b52  mov     rcx, rsi; Object
0x140010b55  call    cs:__imp_ObfDereferenceObject
0x140010b5c  nop     dword ptr [rax+rax+00h]
0x140010b61  test    ebx, ebx
0x140010b63  js      loc_140010C4C
0x140010b69  mov     rbx, [r15+10h]
0x140010b6d  lea     rdi, [r15+10h]
0x140010b71  xor     esi, esi
0x140010b73  cmp     rbx, rdi
0x140010b76  jz      short loc_140010B9A
0x140010b78  lea     rdx, [rbx+50h]; String2
0x140010b7c  mov     r8b, 1; CaseInSensitive
0x140010b7f  lea     rcx, [rbp+57h+DestinationString]; String1
0x140010b83  mov     rsi, rbx
0x140010b86  call    cs:__imp_RtlEqualUnicodeString
0x140010b8d  nop     dword ptr [rax+rax+00h]
0x140010b92  test    al, al
0x140010b94  jz      loc_140010CCC
0x140010b9a  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x140010b9e  xor     edx, edx; Tag
0x140010ba0  call    cs:__imp_ExFreePoolWithTag
0x140010ba7  nop     dword ptr [rax+rax+00h]
0x140010bac  cmp     rbx, rdi
0x140010baf  jz      short loc_140010C27
0x140010bb1  mov     [r14], rsi
0x140010bb4  xor     eax, eax
0x140010bb6  add     rsp, 0B8h
0x140010bbd  pop     r15
0x140010bbf  pop     r14
0x140010bc1  pop     r13
0x140010bc3  pop     r12
0x140010bc5  pop     rdi
0x140010bc6  pop     rsi
0x140010bc7  pop     rbx
0x140010bc8  pop     rbp
0x140010bc9  retn
0x140010bcb  xor     r9d, r9d; Alertable
0x140010bce  mov     [rsp+0F0h+OutputBuffer], 0; Timeout
0x140010bd7  xor     r8d, r8d; WaitMode
0x140010bda  lea     rcx, [rbp+57h+Event]; Object
0x140010bde  xor     edx, edx; WaitReason
0x140010be0  call    cs:__imp_KeWaitForSingleObject
0x140010be7  nop     dword ptr [rax+rax+00h]
0x140010bec  mov     ebx, dword ptr [rbp+57h+var_70]
0x140010bef  jmp     loc_140010AEA
0x140010bf4  cmp     ebx, 80000005h
0x140010bfa  jnz     loc_140010B28
0x140010c00  movzx   r13d, word ptr [rdi]
0x140010c04  xor     edx, edx; Tag
0x140010c06  and     r13d, 0FFFFFFFEh
0x140010c0a  mov     rcx, rdi; P
0x140010c0d  add     r13d, 2
0x140010c11  call    cs:__imp_ExFreePoolWithTag
0x140010c18  nop     dword ptr [rax+rax+00h]
0x140010c1d  mov     eax, [rbp+57h+arg_10]
0x140010c20  inc     eax
0x140010c22  jmp     loc_140010A1F
0x140010c27  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c2e  lea     rdx, WPP_GLOBAL_Control
0x140010c35  cmp     rcx, rdx
0x140010c38  jz      short loc_140010C42
0x140010c3a  mov     edx, [rcx+2Ch]
0x140010c3d  test    dl, 1
0x140010c40  jnz     short loc_140010C6E
0x140010c42  mov     eax, 0C0000034h
0x140010c47  jmp     loc_140010BB6
0x140010c4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c53  lea     rdx, WPP_GLOBAL_Control
0x140010c5a  cmp     rcx, rdx
0x140010c5d  jz      short loc_140010C67
0x140010c5f  mov     edx, [rcx+2Ch]
0x140010c62  test    dl, 1
0x140010c65  jnz     short loc_140010C84
0x140010c67  mov     eax, ebx
0x140010c69  jmp     loc_140010BB6
0x140010c6e  mov     rcx, [rcx+18h]
0x140010c72  mov     edx, 12h
0x140010c77  mov     r9d, 0C0000034h
0x140010c7d  call    WPP_SF_L
0x140010c82  jmp     short loc_140010C42
0x140010c84  cmp     byte ptr [rcx+29h], 1
0x140010c88  jb      short loc_140010C67
0x140010c8a  mov     rcx, [rcx+18h]
0x140010c8e  mov     edx, 11h
0x140010c93  mov     r9d, ebx
0x140010c96  call    WPP_SF_L
0x140010c9b  jmp     short loc_140010C67
0x140010c9d  mov     ebx, 0C0000034h
0x140010ca2  test    rcx, rcx
0x140010ca5  jz      short loc_140010C4C
0x140010ca7  call    cs:__imp_ObfDereferenceObject
0x140010cae  nop     dword ptr [rax+rax+00h]
0x140010cb3  test    ebx, ebx
0x140010cb5  js      short loc_140010C4C
0x140010cb7  mov     r12, r13
0x140010cba  mov     rsi, r13
0x140010cbd  jmp     loc_140010A0A
0x140010cc2  mov     ebx, 0C000009Ah
0x140010cc7  jmp     loc_140010B39
0x140010ccc  mov     rbx, [rbx]
0x140010ccf  cmp     rbx, rdi
0x140010cd2  jz      loc_140010B9A
0x140010cd8  jmp     loc_140010B78
0x140010cdd  mov     ebx, 0C000009Ah
0x140010ce2  jmp     loc_140010B28
0x140010ce7  test    ebx, ebx
0x140010ce9  js      loc_140010B23
0x140010cef  jmp     loc_140010AF2
```
