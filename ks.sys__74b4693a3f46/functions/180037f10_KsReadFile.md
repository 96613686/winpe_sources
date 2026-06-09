# KsReadFile

- ea: `0x180037f10`
- end: `0x180038118`
- name: `KsReadFile`
- size: `520`
- prototype: `NTSTATUS __stdcall(PFILE_OBJECT FileObject, PKEVENT Event, PVOID PortContext, PIO_STATUS_BLOCK IoStatusBlock, PVOID Buffer, ULONG Length, ULONG Key, KPROCESSOR_MODE RequestorMode)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180019c60`
- `0x180037f10`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1800380a3`
- `ntoskrnl!ObfReferenceObject` at `0x1800380b2`
- `ntoskrnl!ObfReferenceObject` at `0x1800380a3`
- `ntoskrnl!ObfReferenceObject` at `0x1800380b2`
- `ntoskrnl!IofCallDriver` at `0x1800380c4`
- `ntoskrnl!IofCallDriver` at `0x1800380c4`
- `ntoskrnl!ExGetPreviousMode` at `0x180037fa1`
- `ntoskrnl!ExGetPreviousMode` at `0x180037fa1`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x180038053`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x180038053`
- `ntoskrnl!ProbeForWrite` at `0x180037f68`
- `ntoskrnl!ProbeForWrite` at `0x180037f68`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180037f7e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180037f7e`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800380f8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800380f8`
- `ntoskrnl!KeClearEvent` at `0x180037f37`
- `ntoskrnl!KeClearEvent` at `0x180038021`
- `ntoskrnl!KeClearEvent` at `0x180037f37`
- `ntoskrnl!KeClearEvent` at `0x180038021`

## pseudocode

```c
NTSTATUS __stdcall KsReadFile(
        PFILE_OBJECT FileObject,
        PKEVENT Event,
        PVOID PortContext,
        PIO_STATUS_BLOCK IoStatusBlock,
        PVOID Buffer,
        ULONG Length,
        ULONG Key,
        KPROCESSOR_MODE RequestorMode)
{
  __int64 v12; // r9
  PDEVICE_OBJECT RelatedDeviceObject; // r14
  NTSTATUS result; // eax
  PIRP v15; // rax
  IRP *v16; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx

  if ( Event )
    KeClearEvent(Event);
  if ( Length && RequestorMode )
    ProbeForWrite(Buffer, Length, 1u);
  RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
  if ( !FileObject->PrivateCacheMap
    || !RequestorMode && ExGetPreviousMode()
    || (LOBYTE(v12) = 1,
        !((unsigned __int8 (__fastcall *)(PFILE_OBJECT, LARGE_INTEGER *, _QWORD, __int64, ULONG, PVOID, PIO_STATUS_BLOCK, PDEVICE_OBJECT))RelatedDeviceObject->DriverObject->FastIoDispatch->FastIoRead)(
           FileObject,
           &FileObject->CurrentByteOffset,
           Length,
           v12,
           Key,
           Buffer,
           IoStatusBlock,
           RelatedDeviceObject))
    || (result = IoStatusBlock->Status) != 0 && result != -2147483643 && result != -1073741807 )
  {
    KeClearEvent(&FileObject->Event);
    v15 = IoBuildSynchronousFsdRequest(
            3u,
            RelatedDeviceObject,
            Buffer,
            Length,
            &FileObject->CurrentByteOffset,
            Event,
            IoStatusBlock);
    v16 = v15;
    if ( v15 )
    {
      v15->RequestorMode = RequestorMode;
      v15->Tail.Overlay.OriginalFileObject = FileObject;
      v15->Overlay.AsynchronousParameters.UserApcContext = PortContext;
      CurrentStackLocation = v15->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation[-1].Parameters.Create.Options = Key;
      CurrentStackLocation[-1].FileObject = FileObject;
      if ( Event )
        ObfReferenceObject(Event);
      ObfReferenceObject(FileObject);
      result = IofCallDriver(RelatedDeviceObject, v16);
      if ( result == 259 && (FileObject->Flags & 2) != 0 )
      {
        KeWaitForSingleObject(&FileObject->Event, Executive, RequestorMode, 0, 0);
        return FileObject->FinalStatus;
      }
    }
    else
    {
      return -1073741670;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180037f10  push    rbx
0x180037f12  push    rsi
0x180037f13  push    rdi
0x180037f14  push    r12
0x180037f16  push    r13
0x180037f18  push    r14
0x180037f1a  push    r15
0x180037f1c  sub     rsp, 50h
0x180037f20  mov     r12, r9
0x180037f23  mov     r13, r8
0x180037f26  mov     rsi, rdx
0x180037f29  mov     rbx, rcx
0x180037f2c  xor     r15d, r15d
0x180037f2f  test    rdx, rdx
0x180037f32  jz      short loc_180037F43
0x180037f34  mov     rcx, rdx; Event
0x180037f37  call    cs:__imp_KeClearEvent
0x180037f3e  nop     dword ptr [rax+rax+00h]
0x180037f43  mov     edi, [rsp+88h+Length]
0x180037f4a  test    edi, edi
0x180037f4c  jz      short loc_180037F7B
0x180037f4e  cmp     [rsp+88h+RequestorMode], r15b
0x180037f56  jz      short loc_180037F7B
0x180037f58  mov     edx, edi; Length
0x180037f5a  mov     r8d, 1; Alignment
0x180037f60  mov     rcx, [rsp+88h+Buffer]; Address
0x180037f68  call    cs:__imp_ProbeForWrite
0x180037f6f  nop     dword ptr [rax+rax+00h]
0x180037f74  jmp     short loc_180037F7B
0x180037f76  jmp     loc_180038107
0x180037f7b  mov     rcx, rbx; FileObject
0x180037f7e  call    cs:__imp_IoGetRelatedDeviceObject
0x180037f85  nop     dword ptr [rax+rax+00h]
0x180037f8a  mov     r14, rax
0x180037f8d  cmp     [rbx+30h], r15
0x180037f91  jz      loc_180038017
0x180037f97  cmp     [rsp+88h+RequestorMode], r15b
0x180037f9f  jnz     short loc_180037FB1
0x180037fa1  call    cs:__imp_ExGetPreviousMode
0x180037fa8  nop     dword ptr [rax+rax+00h]
0x180037fad  test    al, al
0x180037faf  jnz     short loc_180038017
0x180037fb1  mov     rcx, [r14+8]
0x180037fb5  mov     r8, [rcx+50h]
0x180037fb9  lea     rdx, [rbx+68h]
0x180037fbd  mov     rax, [r8+10h]
0x180037fc1  mov     [rsp+88h+var_50], r14
0x180037fc6  mov     [rsp+88h+IoStatusBlock], r12
0x180037fcb  mov     rcx, [rsp+88h+Buffer]
0x180037fd3  mov     [rsp+88h+Event], rcx
0x180037fd8  mov     ecx, [rsp+88h+Key]
0x180037fdf  mov     dword ptr [rsp+88h+StartingOffset], ecx
0x180037fe3  mov     r9b, 1
0x180037fe6  mov     r8d, edi
0x180037fe9  mov     rcx, rbx
0x180037fec  call    _guard_dispatch_icall
0x180037ff1  test    al, al
0x180037ff3  jz      short loc_180038017
0x180037ff5  mov     eax, [r12]
0x180037ff9  test    eax, eax
0x180037ffb  jz      loc_180038107
0x180038001  cmp     eax, 80000005h
0x180038006  jz      loc_180038107
0x18003800c  cmp     eax, 0C0000011h
0x180038011  jz      loc_180038107
0x180038017  lea     r15, [rbx+98h]
0x18003801e  mov     rcx, r15; Event
0x180038021  call    cs:__imp_KeClearEvent
0x180038028  nop     dword ptr [rax+rax+00h]
0x18003802d  lea     rax, [rbx+68h]
0x180038031  mov     [rsp+88h+IoStatusBlock], r12; IoStatusBlock
0x180038036  mov     [rsp+88h+Event], rsi; Event
0x18003803b  mov     [rsp+88h+StartingOffset], rax; StartingOffset
0x180038040  mov     r9d, edi; Length
0x180038043  mov     r8, [rsp+88h+Buffer]; Buffer
0x18003804b  mov     rdx, r14; DeviceObject
0x18003804e  mov     ecx, 3; MajorFunction
0x180038053  call    cs:__imp_IoBuildSynchronousFsdRequest
0x18003805a  nop     dword ptr [rax+rax+00h]
0x18003805f  mov     rdi, rax
0x180038062  test    rax, rax
0x180038065  jnz     short loc_180038071
0x180038067  mov     eax, 0C000009Ah
0x18003806c  jmp     loc_180038107
0x180038071  mov     al, [rsp+88h+RequestorMode]
0x180038078  mov     [rdi+40h], al
0x18003807b  mov     [rdi+0C0h], rbx
0x180038082  mov     [rdi+60h], r13
0x180038086  mov     rcx, [rdi+0B8h]
0x18003808d  mov     eax, [rsp+88h+Key]
0x180038094  mov     [rcx-38h], eax
0x180038097  mov     [rcx-18h], rbx
0x18003809b  test    rsi, rsi
0x18003809e  jz      short loc_1800380AF
0x1800380a0  mov     rcx, rsi; Object
0x1800380a3  call    cs:__imp_ObfReferenceObject
0x1800380aa  nop     dword ptr [rax+rax+00h]
0x1800380af  mov     rcx, rbx; Object
0x1800380b2  call    cs:__imp_ObfReferenceObject
0x1800380b9  nop     dword ptr [rax+rax+00h]
0x1800380be  mov     rdx, rdi; Irp
0x1800380c1  mov     rcx, r14; DeviceObject
0x1800380c4  call    cs:__imp_IofCallDriver
0x1800380cb  nop     dword ptr [rax+rax+00h]
0x1800380d0  cmp     eax, 103h
0x1800380d5  jnz     short loc_180038107
0x1800380d7  mov     edx, [rbx+50h]
0x1800380da  test    dl, 2
0x1800380dd  jz      short loc_180038107
0x1800380df  mov     [rsp+88h+StartingOffset], 0; Timeout
0x1800380e8  xor     r9d, r9d; Alertable
0x1800380eb  mov     r8b, [rsp+88h+RequestorMode]; WaitMode
0x1800380f3  xor     edx, edx; WaitReason
0x1800380f5  mov     rcx, r15; Object
0x1800380f8  call    cs:__imp_KeWaitForSingleObject
0x1800380ff  nop     dword ptr [rax+rax+00h]
0x180038104  mov     eax, [rbx+38h]
0x180038107  add     rsp, 50h
0x18003810b  pop     r15
0x18003810d  pop     r14
0x18003810f  pop     r13
0x180038111  pop     r12
0x180038113  pop     rdi
0x180038114  pop     rsi
0x180038115  pop     rbx
0x180038116  retn
```
