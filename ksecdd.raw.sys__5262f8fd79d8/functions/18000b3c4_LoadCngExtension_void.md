# LoadCngExtension(void)

- ea: `0x18000b3c4`
- end: `0x18000b795`
- name: `?LoadCngExtension@@YAJXZ`
- size: `977`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002b078`

## callees

- `0x180007ba8`
- `0x180007bd8`
- `0x18000b3c4`

## import_xrefs

- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18000b426`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18000b426`
- `ntoskrnl!KeInitializeEvent` at `0x18000b46e`
- `ntoskrnl!KeInitializeEvent` at `0x18000b577`
- `ntoskrnl!KeInitializeEvent` at `0x18000b673`
- `ntoskrnl!KeInitializeEvent` at `0x18000b46e`
- `ntoskrnl!KeInitializeEvent` at `0x18000b577`
- `ntoskrnl!KeInitializeEvent` at `0x18000b673`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000b4b4`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000b5bd`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000b6b9`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000b4b4`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000b5bd`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000b6b9`
- `ntoskrnl!IofCallDriver` at `0x18000b505`
- `ntoskrnl!IofCallDriver` at `0x18000b601`
- `ntoskrnl!IofCallDriver` at `0x18000b6fd`
- `ntoskrnl!IofCallDriver` at `0x18000b505`
- `ntoskrnl!IofCallDriver` at `0x18000b601`
- `ntoskrnl!IofCallDriver` at `0x18000b6fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000b52f`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000b62b`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000b727`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000b52f`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000b62b`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000b727`
- `ntoskrnl!ObfDereferenceObject` at `0x18000b775`
- `ntoskrnl!ObfDereferenceObject` at `0x18000b775`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000b409`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000b409`

## pseudocode

```c
__int64 LoadCngExtension(void)
{
  NTSTATUS DeviceObjectPointer; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  IRP *v3; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  IRP *v6; // rax
  IRP *v7; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+17h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp+27h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp+37h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+A0h] [rbp+67h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A8h] [rbp+6Fh] BYREF

  DeviceObject = 0;
  FileObject = 0;
  DestinationString = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\CNG");
  DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0x1F01FFu, &FileObject, &DeviceObject);
  if ( DeviceObjectPointer < 0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    {
      v2 = 10;
LABEL_37:
      WPP_SF_D(v1[3], v2, &WPP_47798432cc4f3443573e38da5669f213_Traceguids);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v3 = IoBuildDeviceIoControlRequest(
         0x390064u,
         DeviceObject,
         0,
         0,
         &WPP_MAIN_CB.SectorSize,
         8u,
         0,
         &Event,
         &IoStatusBlock);
  if ( !v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      goto LABEL_10;
    v5 = 11;
    goto LABEL_9;
  }
  DeviceObjectPointer = IofCallDriver(DeviceObject, v3);
  if ( DeviceObjectPointer == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    DeviceObjectPointer = IoStatusBlock.Status;
  }
  if ( DeviceObjectPointer >= 0 )
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v6 = IoBuildDeviceIoControlRequest(
           0x390044u,
           DeviceObject,
           0,
           0,
           &WPP_MAIN_CB.DeviceLock.Header.WaitListHead,
           8u,
           0,
           &Event,
           &IoStatusBlock);
    if ( v6 )
    {
      DeviceObjectPointer = IofCallDriver(DeviceObject, v6);
      if ( DeviceObjectPointer == 259 )
      {
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        DeviceObjectPointer = IoStatusBlock.Status;
      }
      if ( DeviceObjectPointer < 0 )
      {
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        {
          v2 = 14;
          goto LABEL_37;
        }
        goto LABEL_38;
      }
      KeInitializeEvent(&Event, NotificationEvent, 0);
      v7 = IoBuildDeviceIoControlRequest(
             0x390048u,
             DeviceObject,
             0,
             0,
             &WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink,
             8u,
             0,
             &Event,
             &IoStatusBlock);
      if ( v7 )
      {
        DeviceObjectPointer = IofCallDriver(DeviceObject, v7);
        if ( DeviceObjectPointer == 259 )
        {
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          DeviceObjectPointer = IoStatusBlock.Status;
        }
        if ( DeviceObjectPointer < 0 )
        {
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          {
            v2 = 16;
            goto LABEL_37;
          }
        }
        goto LABEL_38;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      {
LABEL_10:
        DeviceObjectPointer = -1073741823;
        goto LABEL_38;
      }
      v5 = 15;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
        goto LABEL_10;
      v5 = 13;
    }
LABEL_9:
    WPP_SF_(v4[3], v5, &WPP_47798432cc4f3443573e38da5669f213_Traceguids);
    goto LABEL_10;
  }
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
  {
    v2 = 12;
    goto LABEL_37;
  }
LABEL_38:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)DeviceObjectPointer;
}

```

## disassembly

```asm
0x18000b3c4  mov     [rsp-8+arg_10], rbx
0x18000b3c9  push    rbp
0x18000b3ca  lea     rbp, [rsp-57h]
0x18000b3cf  sub     rsp, 90h
0x18000b3d6  xorps   xmm0, xmm0
0x18000b3d9  mov     [rbp+57h+DeviceObject], 0
0x18000b3e1  xorps   xmm1, xmm1
0x18000b3e4  mov     [rbp+57h+FileObject], 0
0x18000b3ec  xor     eax, eax
0x18000b3ee  lea     rdx, SourceString; "\\Device\\CNG"
0x18000b3f5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000b3f9  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x18000b3fd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000b401  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x18000b405  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18000b409  call    cs:__imp_RtlInitUnicodeString
0x18000b410  nop     dword ptr [rax+rax+00h]
0x18000b415  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x18000b419  mov     edx, 1F01FFh; DesiredAccess
0x18000b41e  lea     r8, [rbp+57h+FileObject]; FileObject
0x18000b422  lea     rcx, [rbp+57h+DestinationString]; ObjectName
0x18000b426  call    cs:__imp_IoGetDeviceObjectPointer
0x18000b42d  nop     dword ptr [rax+rax+00h]
0x18000b432  mov     ebx, eax
0x18000b434  test    eax, eax
0x18000b436  jns     short loc_18000B465
0x18000b438  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b43f  lea     rax, WPP_GLOBAL_Control
0x18000b446  cmp     rcx, rax
0x18000b449  jz      loc_18000B76C
0x18000b44f  mov     edx, [rcx+2Ch]
0x18000b452  test    dl, 1
0x18000b455  jz      loc_18000B76C
0x18000b45b  mov     edx, 0Ah
0x18000b460  jmp     loc_18000B759
0x18000b465  xor     r8d, r8d; State
0x18000b468  lea     rcx, [rbp+57h+Event]; Event
0x18000b46c  xor     edx, edx; Type
0x18000b46e  call    cs:__imp_KeInitializeEvent
0x18000b475  nop     dword ptr [rax+rax+00h]
0x18000b47a  mov     rdx, [rbp+57h+DeviceObject]; DeviceObject
0x18000b47e  lea     rax, [rbp+57h+var_40]
0x18000b482  mov     [rsp+90h+IoStatusBlock], rax; IoStatusBlock
0x18000b487  xor     r9d, r9d; InputBufferLength
0x18000b48a  lea     rax, [rbp+57h+Event]
0x18000b48e  xor     r8d, r8d; InputBuffer
0x18000b491  mov     [rsp+90h+var_58], rax; Event
0x18000b496  mov     ecx, 390064h; IoControlCode
0x18000b49b  mov     [rsp+90h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x18000b4a0  lea     rax, WPP_MAIN_CB.SectorSize
0x18000b4a7  mov     [rsp+90h+OutputBufferLength], 8; OutputBufferLength
0x18000b4af  mov     [rsp+90h+OutputBuffer], rax; OutputBuffer
0x18000b4b4  call    cs:__imp_IoBuildDeviceIoControlRequest
0x18000b4bb  nop     dword ptr [rax+rax+00h]
0x18000b4c0  test    rax, rax
0x18000b4c3  jnz     short loc_18000B4FE
0x18000b4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4cc  lea     rax, WPP_GLOBAL_Control
0x18000b4d3  cmp     rcx, rax
0x18000b4d6  jz      short loc_18000B4F4
0x18000b4d8  mov     eax, [rcx+2Ch]
0x18000b4db  test    al, 1
0x18000b4dd  jz      short loc_18000B4F4
0x18000b4df  mov     edx, 0Bh
0x18000b4e4  mov     rcx, [rcx+18h]
0x18000b4e8  lea     r8, WPP_47798432cc4f3443573e38da5669f213_Traceguids
0x18000b4ef  call    WPP_SF_
0x18000b4f4  mov     ebx, 0C0000001h
0x18000b4f9  jmp     loc_18000B76C
0x18000b4fe  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x18000b502  mov     rdx, rax; Irp
0x18000b505  call    cs:__imp_IofCallDriver
0x18000b50c  nop     dword ptr [rax+rax+00h]
0x18000b511  mov     ebx, eax
0x18000b513  cmp     eax, 103h
0x18000b518  jnz     short loc_18000B53E
0x18000b51a  xor     r9d, r9d; Alertable
0x18000b51d  mov     [rsp+90h+OutputBuffer], 0; Timeout
0x18000b526  xor     r8d, r8d; WaitMode
0x18000b529  lea     rcx, [rbp+57h+Event]; Object
0x18000b52d  xor     edx, edx; WaitReason
0x18000b52f  call    cs:__imp_KeWaitForSingleObject
0x18000b536  nop     dword ptr [rax+rax+00h]
0x18000b53b  mov     ebx, dword ptr [rbp+57h+var_40]
0x18000b53e  test    ebx, ebx
0x18000b540  jns     short loc_18000B56E
0x18000b542  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b549  lea     rax, WPP_GLOBAL_Control
0x18000b550  cmp     rcx, rax
0x18000b553  jz      loc_18000B76C
0x18000b559  mov     eax, [rcx+2Ch]
0x18000b55c  test    al, 1
0x18000b55e  jz      loc_18000B76C
0x18000b564  mov     edx, 0Ch
0x18000b569  jmp     loc_18000B759
0x18000b56e  xor     r8d, r8d; State
0x18000b571  lea     rcx, [rbp+57h+Event]; Event
0x18000b575  xor     edx, edx; Type
0x18000b577  call    cs:__imp_KeInitializeEvent
0x18000b57e  nop     dword ptr [rax+rax+00h]
0x18000b583  mov     rdx, [rbp+57h+DeviceObject]; DeviceObject
0x18000b587  lea     rax, [rbp+57h+var_40]
0x18000b58b  mov     [rsp+90h+IoStatusBlock], rax; IoStatusBlock
0x18000b590  xor     r9d, r9d; InputBufferLength
0x18000b593  lea     rax, [rbp+57h+Event]
0x18000b597  xor     r8d, r8d; InputBuffer
0x18000b59a  mov     [rsp+90h+var_58], rax; Event
0x18000b59f  mov     ecx, 390044h; IoControlCode
0x18000b5a4  mov     [rsp+90h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x18000b5a9  lea     rax, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x18000b5b0  mov     [rsp+90h+OutputBufferLength], 8; OutputBufferLength
0x18000b5b8  mov     [rsp+90h+OutputBuffer], rax; OutputBuffer
0x18000b5bd  call    cs:__imp_IoBuildDeviceIoControlRequest
0x18000b5c4  nop     dword ptr [rax+rax+00h]
0x18000b5c9  test    rax, rax
0x18000b5cc  jnz     short loc_18000B5FA
0x18000b5ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5d5  lea     rax, WPP_GLOBAL_Control
0x18000b5dc  cmp     rcx, rax
0x18000b5df  jz      loc_18000B4F4
0x18000b5e5  mov     eax, [rcx+2Ch]
0x18000b5e8  test    al, 1
0x18000b5ea  jz      loc_18000B4F4
0x18000b5f0  mov     edx, 0Dh
0x18000b5f5  jmp     loc_18000B4E4
0x18000b5fa  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x18000b5fe  mov     rdx, rax; Irp
0x18000b601  call    cs:__imp_IofCallDriver
0x18000b608  nop     dword ptr [rax+rax+00h]
0x18000b60d  mov     ebx, eax
0x18000b60f  cmp     eax, 103h
0x18000b614  jnz     short loc_18000B63A
0x18000b616  xor     r9d, r9d; Alertable
0x18000b619  mov     [rsp+90h+OutputBuffer], 0; Timeout
0x18000b622  xor     r8d, r8d; WaitMode
0x18000b625  lea     rcx, [rbp+57h+Event]; Object
0x18000b629  xor     edx, edx; WaitReason
0x18000b62b  call    cs:__imp_KeWaitForSingleObject
0x18000b632  nop     dword ptr [rax+rax+00h]
0x18000b637  mov     ebx, dword ptr [rbp+57h+var_40]
0x18000b63a  test    ebx, ebx
0x18000b63c  jns     short loc_18000B66A
0x18000b63e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b645  lea     rax, WPP_GLOBAL_Control
0x18000b64c  cmp     rcx, rax
0x18000b64f  jz      loc_18000B76C
0x18000b655  mov     eax, [rcx+2Ch]
0x18000b658  test    al, 1
0x18000b65a  jz      loc_18000B76C
0x18000b660  mov     edx, 0Eh
0x18000b665  jmp     loc_18000B759
0x18000b66a  xor     r8d, r8d; State
0x18000b66d  lea     rcx, [rbp+57h+Event]; Event
0x18000b671  xor     edx, edx; Type
0x18000b673  call    cs:__imp_KeInitializeEvent
0x18000b67a  nop     dword ptr [rax+rax+00h]
0x18000b67f  mov     rdx, [rbp+57h+DeviceObject]; DeviceObject
0x18000b683  lea     rax, [rbp+57h+var_40]
0x18000b687  mov     [rsp+90h+IoStatusBlock], rax; IoStatusBlock
0x18000b68c  xor     r9d, r9d; InputBufferLength
0x18000b68f  lea     rax, [rbp+57h+Event]
0x18000b693  xor     r8d, r8d; InputBuffer
0x18000b696  mov     [rsp+90h+var_58], rax; Event
0x18000b69b  mov     ecx, 390048h; IoControlCode
0x18000b6a0  mov     [rsp+90h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x18000b6a5  lea     rax, WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink
0x18000b6ac  mov     [rsp+90h+OutputBufferLength], 8; OutputBufferLength
0x18000b6b4  mov     [rsp+90h+OutputBuffer], rax; OutputBuffer
0x18000b6b9  call    cs:__imp_IoBuildDeviceIoControlRequest
0x18000b6c0  nop     dword ptr [rax+rax+00h]
0x18000b6c5  test    rax, rax
0x18000b6c8  jnz     short loc_18000B6F6
0x18000b6ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6d1  lea     rax, WPP_GLOBAL_Control
0x18000b6d8  cmp     rcx, rax
0x18000b6db  jz      loc_18000B4F4
0x18000b6e1  mov     eax, [rcx+2Ch]
0x18000b6e4  test    al, 1
0x18000b6e6  jz      loc_18000B4F4
0x18000b6ec  mov     edx, 0Fh
0x18000b6f1  jmp     loc_18000B4E4
0x18000b6f6  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x18000b6fa  mov     rdx, rax; Irp
0x18000b6fd  call    cs:__imp_IofCallDriver
0x18000b704  nop     dword ptr [rax+rax+00h]
0x18000b709  mov     ebx, eax
0x18000b70b  cmp     eax, 103h
0x18000b710  jnz     short loc_18000B736
0x18000b712  xor     r9d, r9d; Alertable
0x18000b715  mov     [rsp+90h+OutputBuffer], 0; Timeout
0x18000b71e  xor     r8d, r8d; WaitMode
0x18000b721  lea     rcx, [rbp+57h+Event]; Object
0x18000b725  xor     edx, edx; WaitReason
0x18000b727  call    cs:__imp_KeWaitForSingleObject
0x18000b72e  nop     dword ptr [rax+rax+00h]
0x18000b733  mov     ebx, dword ptr [rbp+57h+var_40]
0x18000b736  test    ebx, ebx
0x18000b738  jns     short loc_18000B76C
0x18000b73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b741  lea     rax, WPP_GLOBAL_Control
0x18000b748  cmp     rcx, rax
0x18000b74b  jz      short loc_18000B76C
0x18000b74d  mov     eax, [rcx+2Ch]
0x18000b750  test    al, 1
0x18000b752  jz      short loc_18000B76C
0x18000b754  mov     edx, 10h
0x18000b759  mov     rcx, [rcx+18h]
0x18000b75d  lea     r8, WPP_47798432cc4f3443573e38da5669f213_Traceguids
0x18000b764  mov     r9d, ebx
0x18000b767  call    WPP_SF_D
0x18000b76c  mov     rcx, [rbp+57h+FileObject]; Object
0x18000b770  test    rcx, rcx
0x18000b773  jz      short loc_18000B781
0x18000b775  call    cs:__imp_ObfDereferenceObject
0x18000b77c  nop     dword ptr [rax+rax+00h]
0x18000b781  mov     eax, ebx
0x18000b783  mov     rbx, [rsp+90h+arg_10]
0x18000b78b  add     rsp, 90h
0x18000b792  pop     rbp
0x18000b793  retn
```
