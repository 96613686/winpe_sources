# QueryPointsFromMemory

- ea: `0x140016dc0`
- end: `0x14001753a`
- name: `QueryPointsFromMemory`
- size: `1914`
- prototype: `__int64 __fastcall(__int64, _QWORD *, const UNICODE_STRING *, unsigned __int16 *, PUNICODE_STRING ObjectName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400168b0`

## callees

- `0x140001ae0`
- `0x140002f80`
- `0x140003280`
- `0x140016dc0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140017011`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140017211`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001740b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400174a8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140017011`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140017211`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001740b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400174a8`
- `ntoskrnl!ObfDereferenceObject` at `0x140016faa`
- `ntoskrnl!ObfDereferenceObject` at `0x140016fbe`
- `ntoskrnl!ObfDereferenceObject` at `0x1400174d3`
- `ntoskrnl!ObfDereferenceObject` at `0x140016faa`
- `ntoskrnl!ObfDereferenceObject` at `0x140016fbe`
- `ntoskrnl!ObfDereferenceObject` at `0x1400174d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016e0f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016e0f`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140016f0f`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140016f0f`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140016e33`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140016e33`
- `ntoskrnl!ExAllocatePool2` at `0x140016ea2`
- `ntoskrnl!ExAllocatePool2` at `0x140016ea2`
- `ntoskrnl!IofCallDriver` at `0x140016f3a`
- `ntoskrnl!IofCallDriver` at `0x140016f3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017058`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001717e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017330`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400173b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017441`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017058`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001717e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017330`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400173b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017441`
- `ntoskrnl!KeInitializeEvent` at `0x140016ed4`
- `ntoskrnl!KeInitializeEvent` at `0x140016ed4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017386`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017386`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140016f7e`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140016f7e`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140016e5c`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140016e5c`
- `ntoskrnl!RtlCompareMemory` at `0x1400170a7`
- `ntoskrnl!RtlCompareMemory` at `0x140017488`
- `ntoskrnl!RtlCompareMemory` at `0x1400170a7`
- `ntoskrnl!RtlCompareMemory` at `0x140017488`

## pseudocode

```c
__int64 __fastcall QueryPointsFromMemory(
        __int64 a1,
        _QWORD *a2,
        const UNICODE_STRING *a3,
        unsigned __int16 *a4,
        PUNICODE_STRING ObjectName)
{
  PUNICODE_STRING v5; // rbx
  unsigned __int16 *v6; // r15
  __int64 v7; // rax
  NTSTATUS DeviceObjectPointer; // edi
  __int64 v9; // r8
  PDEVICE_OBJECT AttachedDeviceReference; // rax
  PFILE_OBJECT v11; // r14
  struct _DEVICE_OBJECT *v12; // r12
  USHORT *OutputBuffer; // rsi
  unsigned int v14; // eax
  ULONG OutputBufferLength; // r13d
  PIRP v16; // rax
  const UNICODE_STRING *v17; // rsi
  __int64 v18; // r8
  int v19; // r12d
  PDEVICE_OBJECT v20; // r13
  _WORD *v21; // rdx
  SIZE_T v23; // rdi
  __int64 *v24; // rdi
  unsigned int *v25; // r12
  __int64 v26; // rdx
  unsigned int v27; // ecx
  const UNICODE_STRING *v28; // rsi
  unsigned int v29; // r14d
  unsigned __int16 *v30; // rdx
  unsigned int Length; // edi
  char *v32; // rcx
  size_t v33; // r8
  __int64 *v34; // rdi
  unsigned int v35; // ebx
  const UNICODE_STRING *v36; // rdx
  __int64 v37; // rcx
  unsigned int v38; // eax
  __int16 v39; // r8
  unsigned int v40; // eax
  _WORD *v41; // rdx
  BOOLEAN v42; // al
  SIZE_T v43; // rdi
  unsigned int v44; // [rsp+50h] [rbp-61h]
  unsigned int v45; // [rsp+50h] [rbp-61h]
  __int16 v46; // [rsp+50h] [rbp-61h]
  int v47; // [rsp+54h] [rbp-5Dh]
  __int16 v48; // [rsp+54h] [rbp-5Dh]
  PFILE_OBJECT FileObject; // [rsp+58h] [rbp-59h] BYREF
  unsigned int v50; // [rsp+60h] [rbp-51h]
  UNICODE_STRING StringIn; // [rsp+68h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-39h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+88h] [rbp-29h] BYREF
  struct _KEVENT Event; // [rsp+90h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-9h] BYREF

  v5 = ObjectName;
  v6 = a4;
  v7 = a1;
  DestinationString = 0;
  if ( !ObjectName )
    goto LABEL_22;
  RtlInitUnicodeString(&DestinationString, 0);
  DeviceObject = 0;
  FileObject = 0;
  DeviceObjectPointer = IoGetDeviceObjectPointer(ObjectName, 0x80u, &FileObject, &DeviceObject);
  if ( DeviceObjectPointer < 0 )
    goto LABEL_96;
  if ( FileObject->FileName.Length )
  {
    DeviceObjectPointer = -1073741772;
LABEL_96:
    if ( FileObject )
      ObfDereferenceObject(FileObject);
    goto LABEL_78;
  }
  AttachedDeviceReference = IoGetAttachedDeviceReference(FileObject->DeviceObject);
  v11 = FileObject;
  v12 = AttachedDeviceReference;
  FileObject = 0;
  OutputBuffer = 0;
  DeviceObjectPointer = 0;
  v14 = 0;
  StringIn = 0;
  OutputBufferLength = 258;
  while ( 1 )
  {
    v44 = v14;
    if ( v14 >= 2 )
    {
      if ( DeviceObjectPointer >= 0 )
      {
LABEL_13:
        StringIn.Length = *OutputBuffer;
        StringIn.MaximumLength = *OutputBuffer;
        StringIn.Buffer = OutputBuffer + 1;
        DeviceObjectPointer = RtlDuplicateUnicodeString(1u, &StringIn, &DestinationString);
      }
      if ( !OutputBuffer )
        goto LABEL_16;
LABEL_15:
      ExFreePoolWithTag(OutputBuffer, 0);
      goto LABEL_16;
    }
    OutputBuffer = (USHORT *)ExAllocatePool2(258, OutputBufferLength, 1098149453);
    if ( !OutputBuffer )
      break;
    memset(&Event, 0, sizeof(Event));
    IoStatusBlock = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v16 = IoBuildDeviceIoControlRequest(
            0x4D0008u,
            v12,
            0,
            0,
            OutputBuffer,
            OutputBufferLength,
            0,
            &Event,
            &IoStatusBlock);
    if ( !v16 )
    {
      DeviceObjectPointer = -1073741670;
      goto LABEL_15;
    }
    if ( v11 )
      v16->Tail.Overlay.CurrentStackLocation[-1].FileObject = v11;
    DeviceObjectPointer = IofCallDriver(v12, v16);
    if ( DeviceObjectPointer == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      DeviceObjectPointer = IoStatusBlock.Status;
    }
    if ( DeviceObjectPointer >= 0 )
      goto LABEL_13;
    if ( DeviceObjectPointer != -2147483643 )
      goto LABEL_15;
    OutputBufferLength = (*OutputBuffer & 0xFFFE) + 2;
    ExFreePoolWithTag(OutputBuffer, 0);
    v14 = v44 + 1;
  }
  DeviceObjectPointer = -1073741670;
LABEL_16:
  if ( v12 )
    ObfDereferenceObject(v12);
  if ( v11 )
    ObfDereferenceObject(v11);
  if ( DeviceObjectPointer < 0 )
  {
LABEL_78:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 206, v9, (unsigned int)DeviceObjectPointer);
    return (unsigned int)DeviceObjectPointer;
  }
  v7 = a1;
LABEL_22:
  v17 = *(const UNICODE_STRING **)(v7 + 16);
  v18 = 0;
  v45 = 0;
  v19 = 0;
  v47 = 0;
  v20 = (PDEVICE_OBJECT)(v7 + 16);
  for ( DeviceObject = (PDEVICE_OBJECT)(v7 + 16); v17 != (const UNICODE_STRING *)v20; v18 = v45 )
  {
    if ( v6 )
    {
      v21 = *(_WORD **)&v17[6].Length;
      if ( *v6 != *v21 )
        goto LABEL_28;
      v23 = *v6;
      if ( RtlCompareMemory(v6 + 1, v21 + 1, v23) != v23 )
        goto LABEL_28;
    }
    else
    {
      if ( !ObjectName )
        goto LABEL_39;
      if ( !RtlEqualUnicodeString(&DestinationString, v17 + 5, 1u) )
        goto LABEL_28;
    }
    v18 = v45;
LABEL_39:
    v24 = *(__int64 **)&v17[1].Length;
    v19 += **(unsigned __int16 **)&v17[6].Length + v17[5].Length;
    v47 = v19;
    if ( v24 != (__int64 *)&v17[1] )
    {
      do
      {
        if ( !a3 || (v42 = RtlEqualUnicodeString(a3, (PCUNICODE_STRING)(v24 + 3), 1u), v18 = v45, v42) )
        {
          v18 = (unsigned int)(v18 + 1);
          v45 = v18;
          v19 += *((unsigned __int16 *)v24 + 12);
        }
        v24 = (__int64 *)*v24;
      }
      while ( v24 != (__int64 *)&v17[1] );
      v20 = DeviceObject;
      v47 = v19;
    }
    if ( v6 || ObjectName )
      goto LABEL_46;
LABEL_28:
    v17 = *(const UNICODE_STRING **)&v17->Length;
  }
  if ( v6 )
  {
LABEL_30:
    if ( ObjectName && DestinationString.Buffer )
    {
      ExFreePoolWithTag(DestinationString.Buffer, 0);
      DestinationString.Buffer = 0;
      *(_DWORD *)&DestinationString.Length = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 207, v18, 3221225485LL);
    return 3221225485LL;
  }
  if ( ObjectName )
  {
LABEL_46:
    if ( v17 == (const UNICODE_STRING *)v20 )
      goto LABEL_30;
    if ( a3 && !(_DWORD)v18 )
    {
      if ( ObjectName && DestinationString.Buffer )
        ExFreePoolWithTag(DestinationString.Buffer, 0);
      return 3221225524LL;
    }
  }
  v25 = (unsigned int *)a2[3];
  v26 = a2[23];
  v27 = v47 + 8 * (v18 + 2 * v18 + 1);
  *v25 = v27;
  v25[1] = v18;
  a2[7] = v27;
  if ( *v25 > *(_DWORD *)(v26 + 8) )
  {
    a2[7] = 8;
    if ( ObjectName )
      ExFreePoolWithTag(DestinationString.Buffer, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 208, v18, 2147483653LL);
    }
    return 2147483653LL;
  }
  memset((void *)(a2[3] + 8LL), 0, 24LL * (unsigned int)v18);
  v28 = *(const UNICODE_STRING **)&v20->Type;
  v29 = *v25 - v47;
  *(_DWORD *)&StringIn.Length = 0;
  if ( v28 == (const UNICODE_STRING *)v20 )
    goto LABEL_73;
  do
  {
    if ( v6 )
    {
      v41 = *(_WORD **)&v28[6].Length;
      if ( *v6 != *v41 )
        goto LABEL_72;
      v43 = *v6;
      if ( RtlCompareMemory(v6 + 1, v41 + 1, v43) != v43 )
        goto LABEL_72;
    }
    else if ( v5 && !RtlEqualUnicodeString(&DestinationString, v28 + 5, 1u) )
    {
      goto LABEL_72;
    }
    v30 = *(unsigned __int16 **)&v28[6].Length;
    Length = v28[5].Length;
    LODWORD(FileObject) = v29;
    v32 = (char *)v25 + v29;
    v33 = *v30;
    v48 = *v30;
    v46 = Length;
    v50 = v33 + v29;
    v29 += v33 + Length;
    memmove(v32, v30 + 1, v33);
    memmove((char *)v25 + v50, v28[5].Buffer, Length);
    v34 = *(__int64 **)&v28[1].Length;
    if ( v34 == (__int64 *)&v28[1] )
      goto LABEL_67;
    v35 = *(_DWORD *)&StringIn.Length;
    do
    {
      v36 = (const UNICODE_STRING *)(v34 + 3);
      *(_QWORD *)&StringIn.Length = v34 + 3;
      if ( a3 )
      {
        if ( !RtlEqualUnicodeString(a3, v36, 1u) )
          goto LABEL_65;
        v36 = *(const UNICODE_STRING **)&StringIn.Length;
      }
      else
      {
        *(_QWORD *)&StringIn.Length = v34 + 3;
      }
      v37 = 3LL * v35;
      v25[2 * v37 + 2] = v29;
      LOWORD(v25[2 * v37 + 3]) = v36->Length;
      if ( *((_BYTE *)v34 + 16) )
      {
        v38 = (unsigned int)FileObject;
        v39 = v48;
      }
      else
      {
        v39 = 0;
        v38 = 0;
      }
      v25[6 * v35 + 4] = v38;
      v40 = v50;
      LOWORD(v25[6 * v35 + 5]) = v39;
      v25[6 * v35 + 6] = v40;
      LOWORD(v25[6 * v35 + 7]) = v46;
      memmove((char *)v25 + v29, (const void *)v34[4], v36->Length);
      v29 += **(unsigned __int16 **)&StringIn.Length;
      ++v35;
LABEL_65:
      v34 = (__int64 *)*v34;
    }
    while ( v34 != (__int64 *)&v28[1] );
    v6 = a4;
    v20 = DeviceObject;
    *(_DWORD *)&StringIn.Length = v35;
    v5 = ObjectName;
LABEL_67:
    if ( v6 )
      break;
    if ( v5 )
      goto LABEL_69;
LABEL_72:
    v28 = *(const UNICODE_STRING **)&v28->Length;
  }
  while ( v28 != (const UNICODE_STRING *)v20 );
LABEL_73:
  if ( v5 )
LABEL_69:
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  return 0;
}

```

## disassembly

```asm
0x140016dc0  mov     [rsp-8+arg_18], r9
0x140016dc5  mov     [rsp-8+String1], r8
0x140016dca  mov     [rsp-8+arg_8], rdx
0x140016dcf  mov     [rsp-8+arg_0], rcx
0x140016dd4  push    rbp
0x140016dd5  push    rbx
0x140016dd6  push    rsi
0x140016dd7  push    rdi
0x140016dd8  push    r12
0x140016dda  push    r13
0x140016ddc  push    r14
0x140016dde  push    r15
0x140016de0  lea     rbp, [rsp-17h]
0x140016de5  sub     rsp, 0C8h
0x140016dec  mov     rbx, [rbp+4Fh+ObjectName]
0x140016df0  xor     r13d, r13d
0x140016df3  xorps   xmm0, xmm0
0x140016df6  mov     r15, r9
0x140016df9  mov     rax, rcx
0x140016dfc  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x140016e00  test    rbx, rbx
0x140016e03  jz      loc_140016FD9
0x140016e09  xor     edx, edx; SourceString
0x140016e0b  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x140016e0f  call    cs:__imp_RtlInitUnicodeString
0x140016e16  nop     dword ptr [rax+rax+00h]
0x140016e1b  lea     r9, [rbp+4Fh+DeviceObject]; DeviceObject
0x140016e1f  mov     [rbp+4Fh+DeviceObject], r13
0x140016e23  lea     r8, [rbp+4Fh+FileObject]; FileObject
0x140016e27  mov     [rbp+4Fh+FileObject], r13
0x140016e2b  mov     edx, 80h; DesiredAccess
0x140016e30  mov     rcx, rbx; ObjectName
0x140016e33  call    cs:__imp_IoGetDeviceObjectPointer
0x140016e3a  nop     dword ptr [rax+rax+00h]
0x140016e3f  mov     rcx, [rbp+4Fh+FileObject]; Object
0x140016e43  mov     edi, eax
0x140016e45  test    eax, eax
0x140016e47  js      loc_1400174CA
0x140016e4d  cmp     [rcx+58h], r13w
0x140016e52  jnz     loc_1400174C5
0x140016e58  mov     rcx, [rcx+8]; DeviceObject
0x140016e5c  call    cs:__imp_IoGetAttachedDeviceReference
0x140016e63  nop     dword ptr [rax+rax+00h]
0x140016e68  mov     r14, [rbp+4Fh+FileObject]
0x140016e6c  mov     r12, rax
0x140016e6f  mov     [rbp+4Fh+FileObject], r13
0x140016e73  xorps   xmm0, xmm0
0x140016e76  mov     rsi, r13
0x140016e79  mov     edi, r13d
0x140016e7c  xor     eax, eax
0x140016e7e  movups  xmmword ptr [rbp+4Fh+StringIn.Length], xmm0
0x140016e82  mov     r13d, 102h
0x140016e88  mov     [rbp+4Fh+var_B0], eax
0x140016e8b  cmp     eax, 2
0x140016e8e  jnb     loc_140017514
0x140016e94  mov     edx, r13d
0x140016e97  mov     ecx, 102h
0x140016e9c  mov     r8d, 41746E4Dh
0x140016ea2  call    cs:__imp_ExAllocatePool2
0x140016ea9  nop     dword ptr [rax+rax+00h]
0x140016eae  mov     rsi, rax
0x140016eb1  test    rax, rax
0x140016eb4  jz      loc_1400174F2
0x140016eba  xorps   xmm0, xmm0
0x140016ebd  lea     rcx, [rbp+4Fh+Event]; Event
0x140016ec1  xor     eax, eax
0x140016ec3  xor     r8d, r8d; State
0x140016ec6  xor     edx, edx; Type
0x140016ec8  mov     [rbp+4Fh+Event.Header.WaitListHead.Blink], rax
0x140016ecc  movups  xmmword ptr [rbp+4Fh+Event.Header], xmm0
0x140016ed0  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x140016ed4  call    cs:__imp_KeInitializeEvent
0x140016edb  nop     dword ptr [rax+rax+00h]
0x140016ee0  lea     rax, [rbp+4Fh+var_58]
0x140016ee4  xor     r9d, r9d; InputBufferLength
0x140016ee7  mov     [rsp+100h+IoStatusBlock], rax; IoStatusBlock
0x140016eec  xor     r8d, r8d; InputBuffer
0x140016eef  lea     rax, [rbp+4Fh+Event]
0x140016ef3  mov     rdx, r12; DeviceObject
0x140016ef6  mov     [rsp+100h+var_C8], rax; Event
0x140016efb  mov     ecx, 4D0008h; IoControlCode
0x140016f00  mov     [rsp+100h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140016f05  mov     [rsp+100h+OutputBufferLength], r13d; OutputBufferLength
0x140016f0a  mov     [rsp+100h+OutputBuffer], rsi; OutputBuffer
0x140016f0f  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140016f16  nop     dword ptr [rax+rax+00h]
0x140016f1b  mov     rdx, rax; Irp
0x140016f1e  test    rax, rax
0x140016f21  jz      loc_14001750A
0x140016f27  test    r14, r14
0x140016f2a  jz      short loc_140016F37
0x140016f2c  mov     rax, [rax+0B8h]
0x140016f33  mov     [rax-18h], r14
0x140016f37  mov     rcx, r12; DeviceObject
0x140016f3a  call    cs:__imp_IofCallDriver
0x140016f41  nop     dword ptr [rax+rax+00h]
0x140016f46  mov     edi, eax
0x140016f48  cmp     eax, 103h
0x140016f4d  jz      loc_140017371
0x140016f53  test    edi, edi
0x140016f55  js      loc_14001739A
0x140016f5b  movzx   eax, word ptr [rsi]
0x140016f5e  lea     r8, [rbp+4Fh+DestinationString]; StringOut
0x140016f62  mov     [rbp+4Fh+StringIn.Length], ax
0x140016f66  lea     rdx, [rbp+4Fh+StringIn]; StringIn
0x140016f6a  movzx   eax, word ptr [rsi]
0x140016f6d  mov     ecx, 1; Flags
0x140016f72  mov     [rbp+4Fh+StringIn.MaximumLength], ax
0x140016f76  lea     rax, [rsi+2]
0x140016f7a  mov     [rbp+4Fh+StringIn.Buffer], rax
0x140016f7e  call    cs:__imp_RtlDuplicateUnicodeString
0x140016f85  nop     dword ptr [rax+rax+00h]
0x140016f8a  mov     edi, eax
0x140016f8c  test    rsi, rsi
0x140016f8f  jz      short loc_140016FA2
0x140016f91  xor     edx, edx; Tag
0x140016f93  mov     rcx, rsi; P
0x140016f96  call    cs:__imp_ExFreePoolWithTag
0x140016f9d  nop     dword ptr [rax+rax+00h]
0x140016fa2  test    r12, r12
0x140016fa5  jz      short loc_140016FB6
0x140016fa7  mov     rcx, r12; Object
0x140016faa  call    cs:__imp_ObfDereferenceObject
0x140016fb1  nop     dword ptr [rax+rax+00h]
0x140016fb6  test    r14, r14
0x140016fb9  jz      short loc_140016FCA
0x140016fbb  mov     rcx, r14; Object
0x140016fbe  call    cs:__imp_ObfDereferenceObject
0x140016fc5  nop     dword ptr [rax+rax+00h]
0x140016fca  test    edi, edi
0x140016fcc  js      loc_1400173CD
0x140016fd2  mov     rax, [rbp+4Fh+arg_0]
0x140016fd6  xor     r13d, r13d
0x140016fd9  mov     rsi, [rax+10h]
0x140016fdd  mov     r8d, r13d
0x140016fe0  mov     [rbp+4Fh+var_B0], r13d
0x140016fe4  mov     r12d, r13d
0x140016fe7  mov     [rbp+4Fh+var_AC], r13d
0x140016feb  lea     r13, [rax+10h]
0x140016fef  mov     [rbp+4Fh+DeviceObject], r13
0x140016ff3  cmp     rsi, r13
0x140016ff6  jz      short loc_14001703F
0x140016ff8  test    r15, r15
0x140016ffb  jnz     short loc_140017026
0x140016ffd  test    rbx, rbx
0x140017000  jz      loc_1400170C0
0x140017006  lea     rdx, [rsi+50h]; String2
0x14001700a  mov     r8b, 1; CaseInSensitive
0x14001700d  lea     rcx, [rbp+4Fh+DestinationString]; String1
0x140017011  call    cs:__imp_RtlEqualUnicodeString
0x140017018  nop     dword ptr [rax+rax+00h]
0x14001701d  test    al, al
0x14001701f  jz      short loc_140017033
0x140017021  jmp     loc_1400170BC
0x140017026  mov     rdx, [rsi+60h]
0x14001702a  movzx   eax, word ptr [r15]
0x14001702e  cmp     ax, [rdx]
0x140017031  jz      short loc_140017099
0x140017033  mov     rsi, [rsi]
0x140017036  mov     r8d, [rbp+4Fh+var_B0]
0x14001703a  cmp     rsi, r13
0x14001703d  jnz     short loc_140016FF8
0x14001703f  test    r15, r15
0x140017042  jz      loc_1400174FC
0x140017048  test    rbx, rbx
0x14001704b  jz      short loc_140017071
0x14001704d  mov     rcx, [rbp+4Fh+DestinationString.Buffer]; P
0x140017051  test    rcx, rcx
0x140017054  jz      short loc_140017071
0x140017056  xor     edx, edx; Tag
0x140017058  call    cs:__imp_ExFreePoolWithTag
0x14001705f  nop     dword ptr [rax+rax+00h]
0x140017064  xor     eax, eax
0x140017066  mov     [rbp+4Fh+DestinationString.Buffer], 0
0x14001706e  mov     dword ptr [rbp+4Fh+DestinationString.Length], eax
0x140017071  mov     rcx, cs:WPP_GLOBAL_Control
0x140017078  lea     rax, WPP_GLOBAL_Control
0x14001707f  cmp     rcx, rax
0x140017082  jz      short loc_14001708F
0x140017084  mov     eax, [rcx+2Ch]
0x140017087  test    al, 1
0x140017089  jnz     loc_140017521
0x14001708f  mov     eax, 0C000000Dh
0x140017094  jmp     loc_1400171AE
0x140017099  add     rdx, 2; Source2
0x14001709d  lea     rcx, [r15+2]; Source1
0x1400170a1  mov     r8, rax; Length
0x1400170a4  mov     rdi, rax
0x1400170a7  call    cs:__imp_RtlCompareMemory
0x1400170ae  nop     dword ptr [rax+rax+00h]
0x1400170b3  cmp     rax, rdi
0x1400170b6  jnz     loc_140017033
0x1400170bc  mov     r8d, [rbp+4Fh+var_B0]
0x1400170c0  mov     rax, [rsi+60h]
0x1400170c4  mov     rdi, [rsi+10h]
0x1400170c8  movzx   ecx, word ptr [rax]
0x1400170cb  movzx   eax, word ptr [rsi+50h]
0x1400170cf  add     r12d, eax
0x1400170d2  lea     rax, [rsi+10h]
0x1400170d6  add     r12d, ecx
0x1400170d9  mov     [rbp+4Fh+var_AC], r12d
0x1400170dd  cmp     rdi, rax
0x1400170e0  jz      short loc_140017111
0x1400170e2  mov     r13, [rbp+4Fh+String1]
0x1400170e6  test    r13, r13
0x1400170e9  jnz     loc_140017401
0x1400170ef  movzx   eax, word ptr [rdi+18h]
0x1400170f3  inc     r8d
0x1400170f6  mov     [rbp+4Fh+var_B0], r8d
0x1400170fa  add     r12d, eax
0x1400170fd  mov     rdi, [rdi]
0x140017100  lea     rax, [rsi+10h]
0x140017104  cmp     rdi, rax
0x140017107  jnz     short loc_1400170E6
0x140017109  mov     r13, [rbp+4Fh+DeviceObject]
0x14001710d  mov     [rbp+4Fh+var_AC], r12d
0x140017111  test    r15, r15
0x140017114  jnz     short loc_14001711F
0x140017116  test    rbx, rbx
0x140017119  jz      loc_140017033
0x14001711f  cmp     rsi, r13
0x140017122  jz      loc_140017048
0x140017128  cmp     [rbp+4Fh+String1], 0
0x14001712d  jnz     loc_140017428
0x140017133  mov     r9, [rbp+4Fh+arg_8]
0x140017137  lea     eax, ds:1[r8*2]
0x14001713f  mov     edi, [rbp+4Fh+var_AC]
0x140017142  add     eax, r8d
0x140017145  mov     r12, [r9+18h]
0x140017149  mov     rdx, [r9+0B8h]
0x140017150  lea     ecx, [rdi+rax*8]
0x140017153  mov     eax, ecx
0x140017155  mov     [r12], ecx
0x140017159  mov     [r12+4], r8d
0x14001715e  mov     [r9+38h], rax
0x140017162  mov     eax, [rdx+8]
0x140017165  cmp     [r12], eax
0x140017169  jbe     short loc_1400171C3
0x14001716b  mov     qword ptr [r9+38h], 8
0x140017173  test    rbx, rbx
0x140017176  jz      short loc_14001718A
0x140017178  mov     rcx, [rbp+4Fh+DestinationString.Buffer]; P
0x14001717c  xor     edx, edx; Tag
0x14001717e  call    cs:__imp_ExFreePoolWithTag
0x140017185  nop     dword ptr [rax+rax+00h]
0x14001718a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017191  lea     rax, WPP_GLOBAL_Control
0x140017198  cmp     rcx, rax
0x14001719b  jz      short loc_1400171A9
0x14001719d  mov     edx, [rcx+2Ch]
0x1400171a0  test    dl, 1
0x1400171a3  jnz     loc_140017457
0x1400171a9  mov     eax, 80000005h
0x1400171ae  add     rsp, 0C8h
0x1400171b5  pop     r15
0x1400171b7  pop     r14
0x1400171b9  pop     r13
0x1400171bb  pop     r12
0x1400171bd  pop     rdi
0x1400171be  pop     rsi
0x1400171bf  pop     rbx
0x1400171c0  pop     rbp
0x1400171c1  retn
0x1400171c3  mov     rcx, [r9+18h]
0x1400171c7  xor     edx, edx; Val
0x1400171c9  mov     eax, r8d
0x1400171cc  add     rcx, 8; void *
0x1400171d0  lea     r8, [rax+rax*2]
0x1400171d4  shl     r8, 3; Size
0x1400171d8  call    memset
0x1400171dd  mov     r14d, [r12]
0x1400171e1  mov     rsi, [r13+0]
0x1400171e5  sub     r14d, edi
0x1400171e8  mov     dword ptr [rbp+4Fh+StringIn.Length], 0
0x1400171ef  cmp     rsi, r13
0x1400171f2  jz      loc_140017360
0x1400171f8  test    r15, r15
0x1400171fb  jnz     loc_140017343
0x140017201  test    rbx, rbx
0x140017204  jz      short loc_140017225
0x140017206  lea     rdx, [rsi+50h]; String2
0x14001720a  mov     r8b, 1; CaseInSensitive
0x14001720d  lea     rcx, [rbp+4Fh+DestinationString]; String1
0x140017211  call    cs:__imp_RtlEqualUnicodeString
0x140017218  nop     dword ptr [rax+rax+00h]
0x14001721d  test    al, al
0x14001721f  jz      loc_140017354
0x140017225  mov     rdx, [rsi+60h]
0x140017229  movzx   edi, word ptr [rsi+50h]
0x14001722d  mov     ecx, r14d
0x140017230  mov     dword ptr [rbp+4Fh+FileObject], r14d
0x140017234  add     rcx, r12; void *
0x140017237  movzx   r8d, word ptr [rdx]; Size
0x14001723b  add     rdx, 2; Src
0x14001723f  mov     word ptr [rbp+4Fh+var_AC], r8w
0x140017244  mov     word ptr [rbp+4Fh+var_B0], di
0x140017248  lea     eax, [r8+r14]
0x14001724c  mov     [rbp+4Fh+var_A0], eax
0x14001724f  lea     eax, [r8+rdi]
0x140017253  add     r14d, eax
  ... truncated ...
```
