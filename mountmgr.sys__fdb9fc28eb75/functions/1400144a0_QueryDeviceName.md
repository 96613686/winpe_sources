# QueryDeviceName

- ea: `0x1400144a0`
- end: `0x140014792`
- name: `QueryDeviceName`
- size: `754`
- prototype: `__int64 __fastcall(PUNICODE_STRING ObjectName, PUNICODE_STRING StringOut)`
- caller_count: `6`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x14000bcac`
- `0x14000db54`
- `0x140013a20`
- `0x140014fc0`
- `0x140017760`
- `0x14001aab0`

## callees

- `0x1400144a0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400146a8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400146bc`
- `ntoskrnl!ObfDereferenceObject` at `0x140014744`
- `ntoskrnl!ObfDereferenceObject` at `0x1400146a8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400146bc`
- `ntoskrnl!ObfDereferenceObject` at `0x140014744`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400144ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400144ba`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400145fa`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400145fa`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400144f1`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400144f1`
- `ntoskrnl!ExAllocatePool2` at `0x140014584`
- `ntoskrnl!ExAllocatePool2` at `0x140014584`
- `ntoskrnl!IofCallDriver` at `0x140014625`
- `ntoskrnl!IofCallDriver` at `0x140014625`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014684`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014726`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014684`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014726`
- `ntoskrnl!KeInitializeEvent` at `0x1400145bd`
- `ntoskrnl!KeInitializeEvent` at `0x1400145bd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400146f4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400146f4`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14001466c`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14001466c`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001451e`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001451e`

## pseudocode

```c
__int64 __fastcall QueryDeviceName(PUNICODE_STRING ObjectName, PUNICODE_STRING StringOut)
{
  NTSTATUS DeviceObjectPointer; // ebx
  PDEVICE_OBJECT AttachedDeviceReference; // rax
  PFILE_OBJECT v6; // rsi
  struct _DEVICE_OBJECT *v7; // rbp
  USHORT *OutputBuffer; // rbx
  NTSTATUS Status; // edi
  unsigned int v10; // r15d
  ULONG OutputBufferLength; // r14d
  PIRP v12; // rax
  UNICODE_STRING StringIn; // [rsp+50h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-68h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp-58h] BYREF
  PFILE_OBJECT FileObject; // [rsp+E0h] [rbp+18h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+E8h] [rbp+20h] BYREF

  RtlInitUnicodeString(StringOut, 0);
  DeviceObject = 0;
  FileObject = 0;
  DeviceObjectPointer = IoGetDeviceObjectPointer(ObjectName, 0x80u, &FileObject, &DeviceObject);
  if ( DeviceObjectPointer < 0 )
    goto LABEL_23;
  if ( FileObject->FileName.Length )
  {
    DeviceObjectPointer = -1073741772;
LABEL_23:
    if ( FileObject )
      ObfDereferenceObject(FileObject);
    return (unsigned int)DeviceObjectPointer;
  }
  AttachedDeviceReference = IoGetAttachedDeviceReference(FileObject->DeviceObject);
  v6 = FileObject;
  v7 = AttachedDeviceReference;
  FileObject = 0;
  OutputBuffer = 0;
  Status = 0;
  v10 = 0;
  OutputBufferLength = 258;
  StringIn = 0;
  while ( 1 )
  {
    if ( v10 >= 2 )
    {
      if ( Status >= 0 )
      {
LABEL_12:
        StringIn.Length = *OutputBuffer;
        StringIn.MaximumLength = *OutputBuffer;
        StringIn.Buffer = OutputBuffer + 1;
        Status = RtlDuplicateUnicodeString(1u, &StringIn, StringOut);
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
    v12 = IoBuildDeviceIoControlRequest(
            0x4D0008u,
            v7,
            0,
            0,
            OutputBuffer,
            OutputBufferLength,
            0,
            &Event,
            &IoStatusBlock);
    if ( !v12 )
    {
      Status = -1073741670;
      goto LABEL_14;
    }
    if ( v6 )
      v12->Tail.Overlay.CurrentStackLocation[-1].FileObject = v6;
    Status = IofCallDriver(v7, v12);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = IoStatusBlock.Status;
    }
    if ( Status >= 0 )
      goto LABEL_12;
    if ( Status != -2147483643 )
      goto LABEL_14;
    OutputBufferLength = (*OutputBuffer & 0xFFFE) + 2;
    ExFreePoolWithTag(OutputBuffer, 0);
    ++v10;
  }
  Status = -1073741670;
LABEL_15:
  if ( v7 )
    ObfDereferenceObject(v7);
  if ( v6 )
    ObfDereferenceObject(v6);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400144a0  push    rbx
0x1400144a2  push    rbp
0x1400144a3  push    rsi
0x1400144a4  push    r12
0x1400144a6  push    r13
0x1400144a8  sub     rsp, 0A0h
0x1400144af  mov     r12, rdx
0x1400144b2  mov     rbx, rcx
0x1400144b5  mov     rcx, r12; DestinationString
0x1400144b8  xor     edx, edx; SourceString
0x1400144ba  call    cs:__imp_RtlInitUnicodeString
0x1400144c1  nop     dword ptr [rax+rax+00h]
0x1400144c6  xor     r13d, r13d
0x1400144c9  lea     r9, [rsp+0C8h+DeviceObject]; DeviceObject
0x1400144d1  lea     r8, [rsp+0C8h+FileObject]; FileObject
0x1400144d9  mov     [rsp+0C8h+DeviceObject], r13
0x1400144e1  mov     edx, 80h; DesiredAccess
0x1400144e6  mov     [rsp+0C8h+FileObject], r13
0x1400144ee  mov     rcx, rbx; ObjectName
0x1400144f1  call    cs:__imp_IoGetDeviceObjectPointer
0x1400144f8  nop     dword ptr [rax+rax+00h]
0x1400144fd  mov     rcx, [rsp+0C8h+FileObject]; Object
0x140014505  mov     ebx, eax
0x140014507  test    eax, eax
0x140014509  js      loc_14001473F
0x14001450f  cmp     [rcx+58h], r13w
0x140014514  jnz     loc_14001473A
0x14001451a  mov     rcx, [rcx+8]; DeviceObject
0x14001451e  call    cs:__imp_IoGetAttachedDeviceReference
0x140014525  nop     dword ptr [rax+rax+00h]
0x14001452a  mov     rsi, [rsp+0C8h+FileObject]
0x140014532  mov     rbp, rax
0x140014535  mov     [rsp+0C8h+FileObject], r13
0x14001453d  mov     [rsp+0C8h+arg_0], rdi
0x140014545  xorps   xmm0, xmm0
0x140014548  mov     [rsp+0C8h+var_30], r14
0x140014550  mov     rbx, r13
0x140014553  mov     [rsp+0C8h+var_38], r15
0x14001455b  mov     edi, r13d
0x14001455e  mov     r15d, r13d
0x140014561  mov     r14d, 102h
0x140014567  movups  xmmword ptr [rsp+0C8h+StringIn.Length], xmm0
0x14001456c  cmp     r15d, 2
0x140014570  jnb     loc_140014785
0x140014576  mov     edx, r14d
0x140014579  mov     ecx, 102h
0x14001457e  mov     r8d, 41746E4Dh
0x140014584  call    cs:__imp_ExAllocatePool2
0x14001458b  nop     dword ptr [rax+rax+00h]
0x140014590  mov     rbx, rax
0x140014593  test    rax, rax
0x140014596  jz      loc_140014771
0x14001459c  xorps   xmm0, xmm0
0x14001459f  lea     rcx, [rsp+0C8h+Event]; Event
0x1400145a4  xor     eax, eax
0x1400145a6  xor     r8d, r8d; State
0x1400145a9  xor     edx, edx; Type
0x1400145ab  mov     [rsp+0C8h+Event.Header.WaitListHead.Blink], rax
0x1400145b3  movups  xmmword ptr [rsp+0C8h+Event.Header], xmm0
0x1400145b8  movups  xmmword ptr [rsp+0C8h+var_68], xmm0
0x1400145bd  call    cs:__imp_KeInitializeEvent
0x1400145c4  nop     dword ptr [rax+rax+00h]
0x1400145c9  lea     rax, [rsp+0C8h+var_68]
0x1400145ce  xor     r9d, r9d; InputBufferLength
0x1400145d1  mov     [rsp+0C8h+IoStatusBlock], rax; IoStatusBlock
0x1400145d6  xor     r8d, r8d; InputBuffer
0x1400145d9  lea     rax, [rsp+0C8h+Event]
0x1400145de  mov     rdx, rbp; DeviceObject
0x1400145e1  mov     [rsp+0C8h+var_90], rax; Event
0x1400145e6  mov     ecx, 4D0008h; IoControlCode
0x1400145eb  mov     [rsp+0C8h+InternalDeviceIoControl], r13b; InternalDeviceIoControl
0x1400145f0  mov     [rsp+0C8h+OutputBufferLength], r14d; OutputBufferLength
0x1400145f5  mov     [rsp+0C8h+OutputBuffer], rbx; OutputBuffer
0x1400145fa  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140014601  nop     dword ptr [rax+rax+00h]
0x140014606  test    rax, rax
0x140014609  jz      loc_14001477B
0x14001460f  test    rsi, rsi
0x140014612  jz      short loc_14001461F
0x140014614  mov     rcx, [rax+0B8h]
0x14001461b  mov     [rcx-18h], rsi
0x14001461f  mov     rdx, rax; Irp
0x140014622  mov     rcx, rbp; DeviceObject
0x140014625  call    cs:__imp_IofCallDriver
0x14001462c  nop     dword ptr [rax+rax+00h]
0x140014631  mov     edi, eax
0x140014633  cmp     eax, 103h
0x140014638  jz      loc_1400146E2
0x14001463e  test    edi, edi
0x140014640  js      loc_140014709
0x140014646  movzx   eax, word ptr [rbx]
0x140014649  lea     rdx, [rsp+0C8h+StringIn]; StringIn
0x14001464e  mov     [rsp+0C8h+StringIn.Length], ax
0x140014653  mov     r8, r12; StringOut
0x140014656  movzx   eax, word ptr [rbx]
0x140014659  mov     ecx, 1; Flags
0x14001465e  mov     [rsp+0C8h+StringIn.MaximumLength], ax
0x140014663  lea     rax, [rbx+2]
0x140014667  mov     [rsp+0C8h+StringIn.Buffer], rax
0x14001466c  call    cs:__imp_RtlDuplicateUnicodeString
0x140014673  nop     dword ptr [rax+rax+00h]
0x140014678  mov     edi, eax
0x14001467a  test    rbx, rbx
0x14001467d  jz      short loc_140014690
0x14001467f  xor     edx, edx; Tag
0x140014681  mov     rcx, rbx; P
0x140014684  call    cs:__imp_ExFreePoolWithTag
0x14001468b  nop     dword ptr [rax+rax+00h]
0x140014690  mov     r15, [rsp+0C8h+var_38]
0x140014698  mov     r14, [rsp+0C8h+var_30]
0x1400146a0  test    rbp, rbp
0x1400146a3  jz      short loc_1400146B4
0x1400146a5  mov     rcx, rbp; Object
0x1400146a8  call    cs:__imp_ObfDereferenceObject
0x1400146af  nop     dword ptr [rax+rax+00h]
0x1400146b4  test    rsi, rsi
0x1400146b7  jz      short loc_1400146C8
0x1400146b9  mov     rcx, rsi; Object
0x1400146bc  call    cs:__imp_ObfDereferenceObject
0x1400146c3  nop     dword ptr [rax+rax+00h]
0x1400146c8  mov     eax, edi
0x1400146ca  mov     rdi, [rsp+0C8h+arg_0]
0x1400146d2  add     rsp, 0A0h
0x1400146d9  pop     r13
0x1400146db  pop     r12
0x1400146dd  pop     rsi
0x1400146de  pop     rbp
0x1400146df  pop     rbx
0x1400146e0  retn
0x1400146e2  xor     r9d, r9d; Alertable
0x1400146e5  mov     [rsp+0C8h+OutputBuffer], r13; Timeout
0x1400146ea  xor     r8d, r8d; WaitMode
0x1400146ed  lea     rcx, [rsp+0C8h+Event]; Object
0x1400146f2  xor     edx, edx; WaitReason
0x1400146f4  call    cs:__imp_KeWaitForSingleObject
0x1400146fb  nop     dword ptr [rax+rax+00h]
0x140014700  mov     edi, dword ptr [rsp+0C8h+var_68]
0x140014704  jmp     loc_14001463E
0x140014709  cmp     edi, 80000005h
0x14001470f  jnz     loc_14001467F
0x140014715  movzx   r14d, word ptr [rbx]
0x140014719  xor     edx, edx; Tag
0x14001471b  and     r14d, 0FFFFFFFEh
0x14001471f  mov     rcx, rbx; P
0x140014722  add     r14d, 2
0x140014726  call    cs:__imp_ExFreePoolWithTag
0x14001472d  nop     dword ptr [rax+rax+00h]
0x140014732  inc     r15d
0x140014735  jmp     loc_14001456C
0x14001473a  mov     ebx, 0C0000034h
0x14001473f  test    rcx, rcx
0x140014742  jz      short loc_14001475F
0x140014744  call    cs:__imp_ObfDereferenceObject
0x14001474b  nop     dword ptr [rax+rax+00h]
0x140014750  test    ebx, ebx
0x140014752  js      short loc_14001475F
0x140014754  mov     rbp, r13
0x140014757  mov     rsi, r13
0x14001475a  jmp     loc_14001453D
0x14001475f  mov     eax, ebx
0x140014761  add     rsp, 0A0h
0x140014768  pop     r13
0x14001476a  pop     r12
0x14001476c  pop     rsi
0x14001476d  pop     rbp
0x14001476e  pop     rbx
0x14001476f  retn
0x140014771  mov     edi, 0C000009Ah
0x140014776  jmp     loc_140014690
0x14001477b  mov     edi, 0C000009Ah
0x140014780  jmp     loc_14001467F
0x140014785  test    edi, edi
0x140014787  js      loc_14001467A
0x14001478d  jmp     loc_140014646
```
