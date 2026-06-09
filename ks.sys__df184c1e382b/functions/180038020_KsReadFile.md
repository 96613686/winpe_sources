# KsReadFile

- ea: `0x180038020`
- end: `0x180038228`
- name: `KsReadFile`
- size: `520`
- prototype: `NTSTATUS __stdcall(PFILE_OBJECT FileObject, PKEVENT Event, PVOID PortContext, PIO_STATUS_BLOCK IoStatusBlock, PVOID Buffer, ULONG Length, ULONG Key, KPROCESSOR_MODE RequestorMode)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180019cb0`
- `0x180038020`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1800381b3`
- `ntoskrnl!ObfReferenceObject` at `0x1800381c2`
- `ntoskrnl!ObfReferenceObject` at `0x1800381b3`
- `ntoskrnl!ObfReferenceObject` at `0x1800381c2`
- `ntoskrnl!IofCallDriver` at `0x1800381d4`
- `ntoskrnl!IofCallDriver` at `0x1800381d4`
- `ntoskrnl!ExGetPreviousMode` at `0x1800380b1`
- `ntoskrnl!ExGetPreviousMode` at `0x1800380b1`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x180038163`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x180038163`
- `ntoskrnl!ProbeForWrite` at `0x180038078`
- `ntoskrnl!ProbeForWrite` at `0x180038078`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18003808e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18003808e`
- `ntoskrnl!KeClearEvent` at `0x180038047`
- `ntoskrnl!KeClearEvent` at `0x180038131`
- `ntoskrnl!KeClearEvent` at `0x180038047`
- `ntoskrnl!KeClearEvent` at `0x180038131`
- `ntoskrnl!KeWaitForSingleObject` at `0x180038208`
- `ntoskrnl!KeWaitForSingleObject` at `0x180038208`

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
0x180038020  push    rbx
0x180038022  push    rsi
0x180038023  push    rdi
0x180038024  push    r12
0x180038026  push    r13
0x180038028  push    r14
0x18003802a  push    r15
0x18003802c  sub     rsp, 50h
0x180038030  mov     r12, r9
0x180038033  mov     r13, r8
0x180038036  mov     rsi, rdx
0x180038039  mov     rbx, rcx
0x18003803c  xor     r15d, r15d
0x18003803f  test    rdx, rdx
0x180038042  jz      short loc_180038053
0x180038044  mov     rcx, rdx; Event
0x180038047  call    cs:__imp_KeClearEvent
0x18003804e  nop     dword ptr [rax+rax+00h]
0x180038053  mov     edi, [rsp+88h+Length]
0x18003805a  test    edi, edi
0x18003805c  jz      short loc_18003808B
0x18003805e  cmp     [rsp+88h+RequestorMode], r15b
0x180038066  jz      short loc_18003808B
0x180038068  mov     edx, edi; Length
0x18003806a  mov     r8d, 1; Alignment
0x180038070  mov     rcx, [rsp+88h+Buffer]; Address
0x180038078  call    cs:__imp_ProbeForWrite
0x18003807f  nop     dword ptr [rax+rax+00h]
0x180038084  jmp     short loc_18003808B
0x180038086  jmp     loc_180038217
0x18003808b  mov     rcx, rbx; FileObject
0x18003808e  call    cs:__imp_IoGetRelatedDeviceObject
0x180038095  nop     dword ptr [rax+rax+00h]
0x18003809a  mov     r14, rax
0x18003809d  cmp     [rbx+30h], r15
0x1800380a1  jz      loc_180038127
0x1800380a7  cmp     [rsp+88h+RequestorMode], r15b
0x1800380af  jnz     short loc_1800380C1
0x1800380b1  call    cs:__imp_ExGetPreviousMode
0x1800380b8  nop     dword ptr [rax+rax+00h]
0x1800380bd  test    al, al
0x1800380bf  jnz     short loc_180038127
0x1800380c1  mov     rcx, [r14+8]
0x1800380c5  mov     r8, [rcx+50h]
0x1800380c9  lea     rdx, [rbx+68h]
0x1800380cd  mov     rax, [r8+10h]
0x1800380d1  mov     [rsp+88h+var_50], r14
0x1800380d6  mov     [rsp+88h+IoStatusBlock], r12
0x1800380db  mov     rcx, [rsp+88h+Buffer]
0x1800380e3  mov     [rsp+88h+Event], rcx
0x1800380e8  mov     ecx, [rsp+88h+Key]
0x1800380ef  mov     dword ptr [rsp+88h+StartingOffset], ecx
0x1800380f3  mov     r9b, 1
0x1800380f6  mov     r8d, edi
0x1800380f9  mov     rcx, rbx
0x1800380fc  call    _guard_dispatch_icall
0x180038101  test    al, al
0x180038103  jz      short loc_180038127
0x180038105  mov     eax, [r12]
0x180038109  test    eax, eax
0x18003810b  jz      loc_180038217
0x180038111  cmp     eax, 80000005h
0x180038116  jz      loc_180038217
0x18003811c  cmp     eax, 0C0000011h
0x180038121  jz      loc_180038217
0x180038127  lea     r15, [rbx+98h]
0x18003812e  mov     rcx, r15; Event
0x180038131  call    cs:__imp_KeClearEvent
0x180038138  nop     dword ptr [rax+rax+00h]
0x18003813d  lea     rax, [rbx+68h]
0x180038141  mov     [rsp+88h+IoStatusBlock], r12; IoStatusBlock
0x180038146  mov     [rsp+88h+Event], rsi; Event
0x18003814b  mov     [rsp+88h+StartingOffset], rax; StartingOffset
0x180038150  mov     r9d, edi; Length
0x180038153  mov     r8, [rsp+88h+Buffer]; Buffer
0x18003815b  mov     rdx, r14; DeviceObject
0x18003815e  mov     ecx, 3; MajorFunction
0x180038163  call    cs:__imp_IoBuildSynchronousFsdRequest
0x18003816a  nop     dword ptr [rax+rax+00h]
0x18003816f  mov     rdi, rax
0x180038172  test    rax, rax
0x180038175  jnz     short loc_180038181
0x180038177  mov     eax, 0C000009Ah
0x18003817c  jmp     loc_180038217
0x180038181  mov     al, [rsp+88h+RequestorMode]
0x180038188  mov     [rdi+40h], al
0x18003818b  mov     [rdi+0C0h], rbx
0x180038192  mov     [rdi+60h], r13
0x180038196  mov     rcx, [rdi+0B8h]
0x18003819d  mov     eax, [rsp+88h+Key]
0x1800381a4  mov     [rcx-38h], eax
0x1800381a7  mov     [rcx-18h], rbx
0x1800381ab  test    rsi, rsi
0x1800381ae  jz      short loc_1800381BF
0x1800381b0  mov     rcx, rsi; Object
0x1800381b3  call    cs:__imp_ObfReferenceObject
0x1800381ba  nop     dword ptr [rax+rax+00h]
0x1800381bf  mov     rcx, rbx; Object
0x1800381c2  call    cs:__imp_ObfReferenceObject
0x1800381c9  nop     dword ptr [rax+rax+00h]
0x1800381ce  mov     rdx, rdi; Irp
0x1800381d1  mov     rcx, r14; DeviceObject
0x1800381d4  call    cs:__imp_IofCallDriver
0x1800381db  nop     dword ptr [rax+rax+00h]
0x1800381e0  cmp     eax, 103h
0x1800381e5  jnz     short loc_180038217
0x1800381e7  mov     edx, [rbx+50h]
0x1800381ea  test    dl, 2
0x1800381ed  jz      short loc_180038217
0x1800381ef  mov     [rsp+88h+StartingOffset], 0; Timeout
0x1800381f8  xor     r9d, r9d; Alertable
0x1800381fb  mov     r8b, [rsp+88h+RequestorMode]; WaitMode
0x180038203  xor     edx, edx; WaitReason
0x180038205  mov     rcx, r15; Object
0x180038208  call    cs:__imp_KeWaitForSingleObject
0x18003820f  nop     dword ptr [rax+rax+00h]
0x180038214  mov     eax, [rbx+38h]
0x180038217  add     rsp, 50h
0x18003821b  pop     r15
0x18003821d  pop     r14
0x18003821f  pop     r13
0x180038221  pop     r12
0x180038223  pop     rdi
0x180038224  pop     rsi
0x180038225  pop     rbx
0x180038226  retn
```
