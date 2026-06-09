# BlCreateOrRefDriverCdo

- ea: `0x1400ed058`
- end: `0x1400ed36c`
- name: `BlCreateOrRefDriverCdo`
- size: `788`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400ed374`

## callees

- `0x14002ca30`
- `0x140050a94`
- `0x140086948`
- `0x140095920`
- `0x14009a238`
- `0x1400ed058`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x1400ed291`
- `ntoskrnl!ZwOpenFile` at `0x1400ed291`
- `ntoskrnl!IoDeleteDevice` at `0x1400ed33d`
- `ntoskrnl!IoDeleteDevice` at `0x1400ed33d`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400ed215`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400ed215`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400ed2db`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400ed2db`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400ed32d`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400ed32d`
- `ntoskrnl!ZwClose` at `0x1400ed313`
- `ntoskrnl!ZwClose` at `0x1400ed313`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ed0dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ed0f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ed10a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ed0dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ed0f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ed10a`

## pseudocode

```c
__int64 __fastcall BlCreateOrRefDriverCdo(PDRIVER_OBJECT DriverObject, __int64 a2, PDEVICE_OBJECT *a3, _QWORD *a4)
{
  void *v5; // rcx
  int SecurityDescriptor; // ebx
  int v9; // r9d
  __int64 v10; // r8
  ULONG v11; // r9d
  NTSTATUS v12; // eax
  _OWORD *DeviceExtension; // rcx
  void *FileHandle; // [rsp+50h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-69h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+68h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-49h] BYREF
  UNICODE_STRING DefaultSDDLString; // [rsp+A8h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-9h] BYREF
  ULONG v21[2]; // [rsp+C8h] [rbp+7h] BYREF
  __int128 v22; // [rsp+D0h] [rbp+Fh]
  __int128 v23; // [rsp+E0h] [rbp+1Fh]
  PDEVICE_OBJECT DeviceObject; // [rsp+130h] [rbp+6Fh] BYREF
  _QWORD *OutputBuffer; // [rsp+138h] [rbp+77h] BYREF

  DeviceObject = 0;
  OutputBuffer = 0;
  v5 = 0;
  FileHandle = 0;
  DestinationString = 0;
  DefaultSDDLString = 0;
  SymbolicLinkName = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 && a4 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Device\\BitLocker");
    RtlInitUnicodeString(&DefaultSDDLString, L"D:P(A;;GA;;;SY)(A;;GRGW;;;AU)");
    RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\BitLocker");
    *(_QWORD *)v21 = &BlRootDcbFilterCreate;
    v22 = 0;
    v23 = 0;
    SecurityDescriptor = BlCreateDcbImpl(&OutputBuffer, L"BitLocker", 0, 40);
    if ( SecurityDescriptor < 0 )
      goto LABEL_16;
    v10 = OutputBuffer[25];
    *(_QWORD *)(v10 + 8) = BlCreateDcbImpl;
    *(_QWORD *)(v10 + 16) = BlDcbRefImpl;
    *(_QWORD *)(v10 + 24) = BlDcbDerefImpl;
    *(_DWORD *)(v10 + 32) = 809850438;
    SecurityDescriptor = BlAllocateSecurityDescriptor(
                           (__int64)DriverObject,
                           (__int64)&SDDL_DEVOBJ_KERNEL_ONLY,
                           (void **)v10,
                           v9);
    if ( SecurityDescriptor < 0 )
      goto LABEL_16;
    v12 = WdmlibIoCreateDeviceSecure(
            DriverObject,
            0x20u,
            &DestinationString,
            v11,
            (ULONG)v21,
            (BOOLEAN)BlRootDcbDtor,
            &DefaultSDDLString,
            &BTLCKR_CDO_GUID,
            &DeviceObject);
    SecurityDescriptor = v12;
    if ( v12 < 0 )
    {
      if ( v12 != -1073741771 )
        goto LABEL_16;
      BlDcbDerefImpl(OutputBuffer);
      ObjectAttributes.ObjectName = &DestinationString;
      OutputBuffer = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      SecurityDescriptor = ZwOpenFile(&FileHandle, 3u, &ObjectAttributes, &IoStatusBlock, 0, 0x20u);
      if ( SecurityDescriptor < 0 )
        goto LABEL_16;
      SecurityDescriptor = ZwDeviceIoControlFile(
                             FileHandle,
                             0,
                             0,
                             0,
                             &IoStatusBlock,
                             0x4C4290D0u,
                             0,
                             0,
                             &OutputBuffer,
                             8u);
      if ( SecurityDescriptor < 0 )
        goto LABEL_16;
    }
    else
    {
      DeviceObject->Flags |= 4u;
      DeviceExtension = DeviceObject->DeviceExtension;
      *DeviceExtension = 0;
      DeviceExtension[1] = 0;
      SecurityDescriptor = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
      if ( SecurityDescriptor < 0 )
      {
LABEL_16:
        v5 = FileHandle;
        goto LABEL_18;
      }
      DeviceObject->Flags &= ~0x80u;
    }
    *a3 = DeviceObject;
    *a4 = OutputBuffer;
    DeviceObject = 0;
    OutputBuffer = 0;
    goto LABEL_16;
  }
  SecurityDescriptor = -1073741811;
LABEL_18:
  if ( v5 )
  {
    ZwClose(v5);
    FileHandle = 0;
  }
  if ( DeviceObject )
  {
    IoDeleteSymbolicLink(&SymbolicLinkName);
    IoDeleteDevice(DeviceObject);
  }
  BlDcbDeref(OutputBuffer);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x1400ed058  mov     [rsp-8+arg_0], rbx
0x1400ed05d  push    rbp
0x1400ed05e  push    rsi
0x1400ed05f  push    rdi
0x1400ed060  push    r14
0x1400ed062  push    r15
0x1400ed064  lea     rbp, [rsp-2Fh]
0x1400ed069  sub     rsp, 0F0h
0x1400ed070  xorps   xmm0, xmm0
0x1400ed073  xor     r15d, r15d
0x1400ed076  mov     r14, rcx
0x1400ed079  mov     [rbp+4Fh+arg_10], r15
0x1400ed07d  xor     eax, eax
0x1400ed07f  mov     [rbp+4Fh+OutputBuffer], r15
0x1400ed083  mov     ecx, r15d; Handle
0x1400ed086  xorps   xmm1, xmm1
0x1400ed089  mov     [rbp+4Fh+FileHandle], rcx
0x1400ed08d  mov     rdi, r9
0x1400ed090  mov     rsi, r8
0x1400ed093  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1400ed097  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1400ed09b  movups  xmmword ptr [rbp+4Fh+var_68.Length], xmm1
0x1400ed09f  movups  xmmword ptr [rbp+4Fh+SymbolicLinkName.Length], xmm0
0x1400ed0a3  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1400ed0a7  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1400ed0ab  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x1400ed0af  test    r8, r8
0x1400ed0b2  jz      short loc_1400ED0B7
0x1400ed0b4  mov     [r8], r15
0x1400ed0b7  test    rdi, rdi
0x1400ed0ba  jz      short loc_1400ED0BF
0x1400ed0bc  mov     [r9], r15
0x1400ed0bf  test    rsi, rsi
0x1400ed0c2  jz      loc_1400ED309
0x1400ed0c8  test    rdi, rdi
0x1400ed0cb  jz      loc_1400ED309
0x1400ed0d1  lea     rdx, aDeviceBitlocke_0; "\\Device\\BitLocker"
0x1400ed0d8  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1400ed0dc  call    cs:__imp_RtlInitUnicodeString
0x1400ed0e3  nop     dword ptr [rax+rax+00h]
0x1400ed0e8  lea     rdx, aDPAGaSyAGrgwAu; "D:P(A;;GA;;;SY)(A;;GRGW;;;AU)"
0x1400ed0ef  lea     rcx, [rbp+4Fh+var_68]; DestinationString
0x1400ed0f3  call    cs:__imp_RtlInitUnicodeString
0x1400ed0fa  nop     dword ptr [rax+rax+00h]
0x1400ed0ff  lea     rdx, aDosdevicesBitl; "\\DosDevices\\BitLocker"
0x1400ed106  lea     rcx, [rbp+4Fh+SymbolicLinkName]; DestinationString
0x1400ed10a  call    cs:__imp_RtlInitUnicodeString
0x1400ed111  nop     dword ptr [rax+rax+00h]
0x1400ed116  lea     rax, BlRootDcbFilterCreate
0x1400ed11d  mov     dword ptr [rsp+110h+DefaultSDDLString], 30455646h
0x1400ed125  mov     qword ptr [rbp+4Fh+var_48], rax
0x1400ed129  lea     rdx, aBitlocker; "BitLocker"
0x1400ed130  lea     rax, BlRootDcbDtor
0x1400ed137  xorps   xmm0, xmm0
0x1400ed13a  mov     qword ptr [rsp+110h+Exclusive], rax; Exclusive
0x1400ed13f  lea     rcx, [rbp+4Fh+OutputBuffer]
0x1400ed143  lea     rax, [rbp+4Fh+var_48]
0x1400ed147  xorps   xmm1, xmm1
0x1400ed14a  mov     r9d, 28h ; '('
0x1400ed150  mov     qword ptr [rsp+110h+DeviceCharacteristics], rax; DeviceCharacteristics
0x1400ed155  xor     r8d, r8d
0x1400ed158  movdqu  [rbp+4Fh+var_40], xmm0
0x1400ed15d  movdqu  [rbp+4Fh+var_30], xmm1
0x1400ed162  call    BlCreateDcbImpl
0x1400ed167  mov     ebx, eax
0x1400ed169  test    eax, eax
0x1400ed16b  js      loc_1400ED303
0x1400ed171  mov     rax, [rbp+4Fh+OutputBuffer]
0x1400ed175  lea     rdx, SDDL_DEVOBJ_KERNEL_ONLY
0x1400ed17c  mov     rcx, r14
0x1400ed17f  mov     r8, [rax+0C8h]
0x1400ed186  lea     rax, BlCreateDcbImpl
0x1400ed18d  mov     [r8+8], rax
0x1400ed191  lea     rax, BlDcbRefImpl
0x1400ed198  mov     [r8+10h], rax
0x1400ed19c  lea     rax, BlDcbDerefImpl
0x1400ed1a3  mov     [r8+18h], rax
0x1400ed1a7  mov     dword ptr [r8+20h], 30455646h
0x1400ed1af  call    BlAllocateSecurityDescriptor
0x1400ed1b4  mov     ebx, eax
0x1400ed1b6  test    eax, eax
0x1400ed1b8  js      loc_1400ED303
0x1400ed1be  lea     rax, [rbp+4Fh+arg_10]
0x1400ed1c2  mov     edx, 20h ; ' '; DeviceExtensionSize
0x1400ed1c7  mov     [rsp+110h+DeviceObject], rax; DeviceObject
0x1400ed1cc  lea     r8, [rbp+4Fh+DestinationString]; DeviceName
0x1400ed1d0  lea     rax, BTLCKR_CDO_GUID
0x1400ed1d7  mov     rcx, r14; DriverObject
0x1400ed1da  mov     [rsp+110h+DeviceClassGuid], rax; DeviceClassGuid
0x1400ed1df  lea     rax, [rbp+4Fh+var_68]
0x1400ed1e3  mov     [rsp+110h+DefaultSDDLString], rax; DefaultSDDLString
0x1400ed1e8  call    WdmlibIoCreateDeviceSecure
0x1400ed1ed  mov     ebx, eax
0x1400ed1ef  test    eax, eax
0x1400ed1f1  js      short loc_1400ED239
0x1400ed1f3  mov     rax, [rbp+4Fh+arg_10]
0x1400ed1f7  lea     rdx, [rbp+4Fh+DestinationString]; DeviceName
0x1400ed1fb  xorps   xmm0, xmm0
0x1400ed1fe  or      dword ptr [rax+30h], 4
0x1400ed202  mov     rax, [rbp+4Fh+arg_10]
0x1400ed206  mov     rcx, [rax+40h]
0x1400ed20a  movups  xmmword ptr [rcx], xmm0
0x1400ed20d  movups  xmmword ptr [rcx+10h], xmm0
0x1400ed211  lea     rcx, [rbp+4Fh+SymbolicLinkName]; SymbolicLinkName
0x1400ed215  call    cs:__imp_IoCreateSymbolicLink
0x1400ed21c  nop     dword ptr [rax+rax+00h]
0x1400ed221  mov     ebx, eax
0x1400ed223  test    eax, eax
0x1400ed225  js      loc_1400ED303
0x1400ed22b  mov     rax, [rbp+4Fh+arg_10]
0x1400ed22f  btr     dword ptr [rax+30h], 7
0x1400ed234  jmp     loc_1400ED2ED
0x1400ed239  cmp     eax, 0C0000035h
0x1400ed23e  jnz     loc_1400ED303
0x1400ed244  mov     rcx, [rbp+4Fh+OutputBuffer]; P
0x1400ed248  call    BlDcbDerefImpl
0x1400ed24d  lea     rax, [rbp+4Fh+DestinationString]
0x1400ed251  mov     dword ptr [rsp+110h+Exclusive], 20h ; ' '; OpenOptions
0x1400ed259  xorps   xmm0, xmm0
0x1400ed25c  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1400ed260  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1400ed264  mov     [rbp+4Fh+OutputBuffer], r15
0x1400ed268  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400ed26c  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1400ed273  mov     edx, 3; DesiredAccess
0x1400ed278  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r15
0x1400ed27c  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400ed280  mov     [rbp+4Fh+ObjectAttributes.Attributes], 200h
0x1400ed287  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ed28c  mov     [rsp+110h+DeviceCharacteristics], r15d; ShareAccess
0x1400ed291  call    cs:__imp_ZwOpenFile
0x1400ed298  nop     dword ptr [rax+rax+00h]
0x1400ed29d  mov     ebx, eax
0x1400ed29f  test    eax, eax
0x1400ed2a1  js      short loc_1400ED303
0x1400ed2a3  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400ed2a7  lea     rax, [rbp+4Fh+OutputBuffer]
0x1400ed2ab  mov     [rsp+110h+OutputBufferLength], 8; OutputBufferLength
0x1400ed2b3  xor     r9d, r9d; ApcContext
0x1400ed2b6  mov     [rsp+110h+DeviceObject], rax; OutputBuffer
0x1400ed2bb  xor     r8d, r8d; ApcRoutine
0x1400ed2be  mov     dword ptr [rsp+110h+DeviceClassGuid], r15d; InputBufferLength
0x1400ed2c3  lea     rax, [rbp+4Fh+IoStatusBlock]
0x1400ed2c7  mov     [rsp+110h+DefaultSDDLString], r15; InputBuffer
0x1400ed2cc  xor     edx, edx; Event
0x1400ed2ce  mov     dword ptr [rsp+110h+Exclusive], 4C4290D0h; IoControlCode
0x1400ed2d6  mov     qword ptr [rsp+110h+DeviceCharacteristics], rax; IoStatusBlock
0x1400ed2db  call    cs:__imp_ZwDeviceIoControlFile
0x1400ed2e2  nop     dword ptr [rax+rax+00h]
0x1400ed2e7  mov     ebx, eax
0x1400ed2e9  test    eax, eax
0x1400ed2eb  js      short loc_1400ED303
0x1400ed2ed  mov     rax, [rbp+4Fh+arg_10]
0x1400ed2f1  mov     [rsi], rax
0x1400ed2f4  mov     rax, [rbp+4Fh+OutputBuffer]
0x1400ed2f8  mov     [rdi], rax
0x1400ed2fb  mov     [rbp+4Fh+arg_10], r15
0x1400ed2ff  mov     [rbp+4Fh+OutputBuffer], r15
0x1400ed303  mov     rcx, [rbp+4Fh+FileHandle]
0x1400ed307  jmp     short loc_1400ED30E
0x1400ed309  mov     ebx, 0C000000Dh
0x1400ed30e  test    rcx, rcx
0x1400ed311  jz      short loc_1400ED323
0x1400ed313  call    cs:__imp_ZwClose
0x1400ed31a  nop     dword ptr [rax+rax+00h]
0x1400ed31f  mov     [rbp+4Fh+FileHandle], r15
0x1400ed323  cmp     [rbp+4Fh+arg_10], r15
0x1400ed327  jz      short loc_1400ED349
0x1400ed329  lea     rcx, [rbp+4Fh+SymbolicLinkName]; SymbolicLinkName
0x1400ed32d  call    cs:__imp_IoDeleteSymbolicLink
0x1400ed334  nop     dword ptr [rax+rax+00h]
0x1400ed339  mov     rcx, [rbp+4Fh+arg_10]; DeviceObject
0x1400ed33d  call    cs:__imp_IoDeleteDevice
0x1400ed344  nop     dword ptr [rax+rax+00h]
0x1400ed349  mov     rcx, [rbp+4Fh+OutputBuffer]
0x1400ed34d  call    BlDcbDeref
0x1400ed352  mov     eax, ebx
0x1400ed354  mov     rbx, [rsp+110h+arg_0]
0x1400ed35c  add     rsp, 0F0h
0x1400ed363  pop     r15
0x1400ed365  pop     r14
0x1400ed367  pop     rdi
0x1400ed368  pop     rsi
0x1400ed369  pop     rbp
0x1400ed36a  retn
```
