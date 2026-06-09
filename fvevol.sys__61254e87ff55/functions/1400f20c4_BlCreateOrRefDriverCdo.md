# BlCreateOrRefDriverCdo

- ea: `0x1400f20c4`
- end: `0x1400f23d8`
- name: `BlCreateOrRefDriverCdo`
- size: `788`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400f23e0`

## callees

- `0x14002da30`
- `0x140052a94`
- `0x1400889e8`
- `0x1400979d0`
- `0x14009c2e8`
- `0x1400f20c4`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x1400f22fd`
- `ntoskrnl!ZwOpenFile` at `0x1400f22fd`
- `ntoskrnl!IoDeleteDevice` at `0x1400f23a9`
- `ntoskrnl!IoDeleteDevice` at `0x1400f23a9`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400f2281`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400f2281`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400f2347`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400f2347`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400f2399`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400f2399`
- `ntoskrnl!ZwClose` at `0x1400f237f`
- `ntoskrnl!ZwClose` at `0x1400f237f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400f2148`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400f215f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400f2176`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400f2148`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400f215f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400f2176`

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
0x1400f20c4  mov     [rsp-8+arg_0], rbx
0x1400f20c9  push    rbp
0x1400f20ca  push    rsi
0x1400f20cb  push    rdi
0x1400f20cc  push    r14
0x1400f20ce  push    r15
0x1400f20d0  lea     rbp, [rsp-2Fh]
0x1400f20d5  sub     rsp, 0F0h
0x1400f20dc  xorps   xmm0, xmm0
0x1400f20df  xor     r15d, r15d
0x1400f20e2  mov     r14, rcx
0x1400f20e5  mov     [rbp+4Fh+arg_10], r15
0x1400f20e9  xor     eax, eax
0x1400f20eb  mov     [rbp+4Fh+OutputBuffer], r15
0x1400f20ef  mov     ecx, r15d; Handle
0x1400f20f2  xorps   xmm1, xmm1
0x1400f20f5  mov     [rbp+4Fh+FileHandle], rcx
0x1400f20f9  mov     rdi, r9
0x1400f20fc  mov     rsi, r8
0x1400f20ff  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1400f2103  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1400f2107  movups  xmmword ptr [rbp+4Fh+var_68.Length], xmm1
0x1400f210b  movups  xmmword ptr [rbp+4Fh+SymbolicLinkName.Length], xmm0
0x1400f210f  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1400f2113  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1400f2117  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x1400f211b  test    r8, r8
0x1400f211e  jz      short loc_1400F2123
0x1400f2120  mov     [r8], r15
0x1400f2123  test    rdi, rdi
0x1400f2126  jz      short loc_1400F212B
0x1400f2128  mov     [r9], r15
0x1400f212b  test    rsi, rsi
0x1400f212e  jz      loc_1400F2375
0x1400f2134  test    rdi, rdi
0x1400f2137  jz      loc_1400F2375
0x1400f213d  lea     rdx, aDeviceBitlocke_0; "\\Device\\BitLocker"
0x1400f2144  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1400f2148  call    cs:__imp_RtlInitUnicodeString
0x1400f214f  nop     dword ptr [rax+rax+00h]
0x1400f2154  lea     rdx, aDPAGaSyAGrgwAu; "D:P(A;;GA;;;SY)(A;;GRGW;;;AU)"
0x1400f215b  lea     rcx, [rbp+4Fh+var_68]; DestinationString
0x1400f215f  call    cs:__imp_RtlInitUnicodeString
0x1400f2166  nop     dword ptr [rax+rax+00h]
0x1400f216b  lea     rdx, aDosdevicesBitl; "\\DosDevices\\BitLocker"
0x1400f2172  lea     rcx, [rbp+4Fh+SymbolicLinkName]; DestinationString
0x1400f2176  call    cs:__imp_RtlInitUnicodeString
0x1400f217d  nop     dword ptr [rax+rax+00h]
0x1400f2182  lea     rax, BlRootDcbFilterCreate
0x1400f2189  mov     dword ptr [rsp+110h+DefaultSDDLString], 30455646h
0x1400f2191  mov     qword ptr [rbp+4Fh+var_48], rax
0x1400f2195  lea     rdx, aBitlocker; "BitLocker"
0x1400f219c  lea     rax, BlRootDcbDtor
0x1400f21a3  xorps   xmm0, xmm0
0x1400f21a6  mov     qword ptr [rsp+110h+Exclusive], rax; Exclusive
0x1400f21ab  lea     rcx, [rbp+4Fh+OutputBuffer]
0x1400f21af  lea     rax, [rbp+4Fh+var_48]
0x1400f21b3  xorps   xmm1, xmm1
0x1400f21b6  mov     r9d, 28h ; '('
0x1400f21bc  mov     qword ptr [rsp+110h+DeviceCharacteristics], rax; DeviceCharacteristics
0x1400f21c1  xor     r8d, r8d
0x1400f21c4  movdqu  [rbp+4Fh+var_40], xmm0
0x1400f21c9  movdqu  [rbp+4Fh+var_30], xmm1
0x1400f21ce  call    BlCreateDcbImpl
0x1400f21d3  mov     ebx, eax
0x1400f21d5  test    eax, eax
0x1400f21d7  js      loc_1400F236F
0x1400f21dd  mov     rax, [rbp+4Fh+OutputBuffer]
0x1400f21e1  lea     rdx, SDDL_DEVOBJ_KERNEL_ONLY
0x1400f21e8  mov     rcx, r14
0x1400f21eb  mov     r8, [rax+0C8h]
0x1400f21f2  lea     rax, BlCreateDcbImpl
0x1400f21f9  mov     [r8+8], rax
0x1400f21fd  lea     rax, BlDcbRefImpl
0x1400f2204  mov     [r8+10h], rax
0x1400f2208  lea     rax, BlDcbDerefImpl
0x1400f220f  mov     [r8+18h], rax
0x1400f2213  mov     dword ptr [r8+20h], 30455646h
0x1400f221b  call    BlAllocateSecurityDescriptor
0x1400f2220  mov     ebx, eax
0x1400f2222  test    eax, eax
0x1400f2224  js      loc_1400F236F
0x1400f222a  lea     rax, [rbp+4Fh+arg_10]
0x1400f222e  mov     edx, 20h ; ' '; DeviceExtensionSize
0x1400f2233  mov     [rsp+110h+DeviceObject], rax; DeviceObject
0x1400f2238  lea     r8, [rbp+4Fh+DestinationString]; DeviceName
0x1400f223c  lea     rax, BTLCKR_CDO_GUID
0x1400f2243  mov     rcx, r14; DriverObject
0x1400f2246  mov     [rsp+110h+DeviceClassGuid], rax; DeviceClassGuid
0x1400f224b  lea     rax, [rbp+4Fh+var_68]
0x1400f224f  mov     [rsp+110h+DefaultSDDLString], rax; DefaultSDDLString
0x1400f2254  call    WdmlibIoCreateDeviceSecure
0x1400f2259  mov     ebx, eax
0x1400f225b  test    eax, eax
0x1400f225d  js      short loc_1400F22A5
0x1400f225f  mov     rax, [rbp+4Fh+arg_10]
0x1400f2263  lea     rdx, [rbp+4Fh+DestinationString]; DeviceName
0x1400f2267  xorps   xmm0, xmm0
0x1400f226a  or      dword ptr [rax+30h], 4
0x1400f226e  mov     rax, [rbp+4Fh+arg_10]
0x1400f2272  mov     rcx, [rax+40h]
0x1400f2276  movups  xmmword ptr [rcx], xmm0
0x1400f2279  movups  xmmword ptr [rcx+10h], xmm0
0x1400f227d  lea     rcx, [rbp+4Fh+SymbolicLinkName]; SymbolicLinkName
0x1400f2281  call    cs:__imp_IoCreateSymbolicLink
0x1400f2288  nop     dword ptr [rax+rax+00h]
0x1400f228d  mov     ebx, eax
0x1400f228f  test    eax, eax
0x1400f2291  js      loc_1400F236F
0x1400f2297  mov     rax, [rbp+4Fh+arg_10]
0x1400f229b  btr     dword ptr [rax+30h], 7
0x1400f22a0  jmp     loc_1400F2359
0x1400f22a5  cmp     eax, 0C0000035h
0x1400f22aa  jnz     loc_1400F236F
0x1400f22b0  mov     rcx, [rbp+4Fh+OutputBuffer]; P
0x1400f22b4  call    BlDcbDerefImpl
0x1400f22b9  lea     rax, [rbp+4Fh+DestinationString]
0x1400f22bd  mov     dword ptr [rsp+110h+Exclusive], 20h ; ' '; OpenOptions
0x1400f22c5  xorps   xmm0, xmm0
0x1400f22c8  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1400f22cc  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1400f22d0  mov     [rbp+4Fh+OutputBuffer], r15
0x1400f22d4  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400f22d8  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1400f22df  mov     edx, 3; DesiredAccess
0x1400f22e4  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r15
0x1400f22e8  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400f22ec  mov     [rbp+4Fh+ObjectAttributes.Attributes], 200h
0x1400f22f3  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400f22f8  mov     [rsp+110h+DeviceCharacteristics], r15d; ShareAccess
0x1400f22fd  call    cs:__imp_ZwOpenFile
0x1400f2304  nop     dword ptr [rax+rax+00h]
0x1400f2309  mov     ebx, eax
0x1400f230b  test    eax, eax
0x1400f230d  js      short loc_1400F236F
0x1400f230f  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400f2313  lea     rax, [rbp+4Fh+OutputBuffer]
0x1400f2317  mov     [rsp+110h+OutputBufferLength], 8; OutputBufferLength
0x1400f231f  xor     r9d, r9d; ApcContext
0x1400f2322  mov     [rsp+110h+DeviceObject], rax; OutputBuffer
0x1400f2327  xor     r8d, r8d; ApcRoutine
0x1400f232a  mov     dword ptr [rsp+110h+DeviceClassGuid], r15d; InputBufferLength
0x1400f232f  lea     rax, [rbp+4Fh+IoStatusBlock]
0x1400f2333  mov     [rsp+110h+DefaultSDDLString], r15; InputBuffer
0x1400f2338  xor     edx, edx; Event
0x1400f233a  mov     dword ptr [rsp+110h+Exclusive], 4C4290D0h; IoControlCode
0x1400f2342  mov     qword ptr [rsp+110h+DeviceCharacteristics], rax; IoStatusBlock
0x1400f2347  call    cs:__imp_ZwDeviceIoControlFile
0x1400f234e  nop     dword ptr [rax+rax+00h]
0x1400f2353  mov     ebx, eax
0x1400f2355  test    eax, eax
0x1400f2357  js      short loc_1400F236F
0x1400f2359  mov     rax, [rbp+4Fh+arg_10]
0x1400f235d  mov     [rsi], rax
0x1400f2360  mov     rax, [rbp+4Fh+OutputBuffer]
0x1400f2364  mov     [rdi], rax
0x1400f2367  mov     [rbp+4Fh+arg_10], r15
0x1400f236b  mov     [rbp+4Fh+OutputBuffer], r15
0x1400f236f  mov     rcx, [rbp+4Fh+FileHandle]
0x1400f2373  jmp     short loc_1400F237A
0x1400f2375  mov     ebx, 0C000000Dh
0x1400f237a  test    rcx, rcx
0x1400f237d  jz      short loc_1400F238F
0x1400f237f  call    cs:__imp_ZwClose
0x1400f2386  nop     dword ptr [rax+rax+00h]
0x1400f238b  mov     [rbp+4Fh+FileHandle], r15
0x1400f238f  cmp     [rbp+4Fh+arg_10], r15
0x1400f2393  jz      short loc_1400F23B5
0x1400f2395  lea     rcx, [rbp+4Fh+SymbolicLinkName]; SymbolicLinkName
0x1400f2399  call    cs:__imp_IoDeleteSymbolicLink
0x1400f23a0  nop     dword ptr [rax+rax+00h]
0x1400f23a5  mov     rcx, [rbp+4Fh+arg_10]; DeviceObject
0x1400f23a9  call    cs:__imp_IoDeleteDevice
0x1400f23b0  nop     dword ptr [rax+rax+00h]
0x1400f23b5  mov     rcx, [rbp+4Fh+OutputBuffer]
0x1400f23b9  call    BlDcbDeref
0x1400f23be  mov     eax, ebx
0x1400f23c0  mov     rbx, [rsp+110h+arg_0]
0x1400f23c8  add     rsp, 0F0h
0x1400f23cf  pop     r15
0x1400f23d1  pop     r14
0x1400f23d3  pop     rdi
0x1400f23d4  pop     rsi
0x1400f23d5  pop     rbp
0x1400f23d6  retn
```
