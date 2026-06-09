# KsWriteFile

- ea: `0x180038590`
- end: `0x18003877e`
- name: `KsWriteFile`
- size: `494`
- prototype: `NTSTATUS __stdcall(PFILE_OBJECT FileObject, PKEVENT Event, PVOID PortContext, PIO_STATUS_BLOCK IoStatusBlock, PVOID Buffer, ULONG Length, ULONG Key, KPROCESSOR_MODE RequestorMode)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180019c60`
- `0x180038590`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x180038709`
- `ntoskrnl!ObfReferenceObject` at `0x180038718`
- `ntoskrnl!ObfReferenceObject` at `0x180038709`
- `ntoskrnl!ObfReferenceObject` at `0x180038718`
- `ntoskrnl!IofCallDriver` at `0x18003872a`
- `ntoskrnl!IofCallDriver` at `0x18003872a`
- `ntoskrnl!ExGetPreviousMode` at `0x18003861d`
- `ntoskrnl!ExGetPreviousMode` at `0x18003861d`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1800386b9`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1800386b9`
- `ntoskrnl!ProbeForRead` at `0x1800385e8`
- `ntoskrnl!ProbeForRead` at `0x1800385e8`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1800385fe`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1800385fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003875e`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003875e`
- `ntoskrnl!KeClearEvent` at `0x1800385b7`
- `ntoskrnl!KeClearEvent` at `0x180038687`
- `ntoskrnl!KeClearEvent` at `0x1800385b7`
- `ntoskrnl!KeClearEvent` at `0x180038687`

## pseudocode

```c
NTSTATUS __stdcall KsWriteFile(
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
    ProbeForRead(Buffer, Length, 1u);
  RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
  if ( FileObject->PrivateCacheMap && (RequestorMode || !ExGetPreviousMode()) )
  {
    LOBYTE(v12) = 1;
    if ( ((unsigned __int8 (__fastcall *)(PFILE_OBJECT, LARGE_INTEGER *, _QWORD, __int64, ULONG, PVOID, PIO_STATUS_BLOCK, PDEVICE_OBJECT))RelatedDeviceObject->DriverObject->FastIoDispatch->FastIoWrite)(
           FileObject,
           &FileObject->CurrentByteOffset,
           Length,
           v12,
           Key,
           Buffer,
           IoStatusBlock,
           RelatedDeviceObject) )
    {
      if ( !IoStatusBlock->Status )
        return 0;
    }
  }
  KeClearEvent(&FileObject->Event);
  v15 = IoBuildSynchronousFsdRequest(
          4u,
          RelatedDeviceObject,
          Buffer,
          Length,
          &FileObject->CurrentByteOffset,
          Event,
          IoStatusBlock);
  v16 = v15;
  if ( !v15 )
    return -1073741670;
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
  return result;
}

```

## disassembly

```asm
0x180038590  push    rbx
0x180038592  push    rsi
0x180038593  push    rdi
0x180038594  push    r12
0x180038596  push    r13
0x180038598  push    r14
0x18003859a  push    r15
0x18003859c  sub     rsp, 50h
0x1800385a0  mov     r15, r9
0x1800385a3  mov     r13, r8
0x1800385a6  mov     rsi, rdx
0x1800385a9  mov     rbx, rcx
0x1800385ac  xor     r12d, r12d
0x1800385af  test    rdx, rdx
0x1800385b2  jz      short loc_1800385C3
0x1800385b4  mov     rcx, rdx; Event
0x1800385b7  call    cs:__imp_KeClearEvent
0x1800385be  nop     dword ptr [rax+rax+00h]
0x1800385c3  mov     edi, [rsp+88h+Length]
0x1800385ca  test    edi, edi
0x1800385cc  jz      short loc_1800385FB
0x1800385ce  cmp     [rsp+88h+RequestorMode], r12b
0x1800385d6  jz      short loc_1800385FB
0x1800385d8  mov     edx, edi; Length
0x1800385da  mov     r8d, 1; Alignment
0x1800385e0  mov     rcx, [rsp+88h+Buffer]; Address
0x1800385e8  call    cs:__imp_ProbeForRead
0x1800385ef  nop     dword ptr [rax+rax+00h]
0x1800385f4  jmp     short loc_1800385FB
0x1800385f6  jmp     loc_18003876D
0x1800385fb  mov     rcx, rbx; FileObject
0x1800385fe  call    cs:__imp_IoGetRelatedDeviceObject
0x180038605  nop     dword ptr [rax+rax+00h]
0x18003860a  mov     r14, rax
0x18003860d  cmp     [rbx+30h], r12
0x180038611  jz      short loc_18003867D
0x180038613  cmp     [rsp+88h+RequestorMode], r12b
0x18003861b  jnz     short loc_18003862D
0x18003861d  call    cs:__imp_ExGetPreviousMode
0x180038624  nop     dword ptr [rax+rax+00h]
0x180038629  test    al, al
0x18003862b  jnz     short loc_18003867D
0x18003862d  mov     rcx, [r14+8]
0x180038631  mov     r8, [rcx+50h]
0x180038635  lea     rdx, [rbx+68h]
0x180038639  mov     rax, [r8+18h]
0x18003863d  mov     [rsp+88h+var_50], r14
0x180038642  mov     [rsp+88h+IoStatusBlock], r15
0x180038647  mov     rcx, [rsp+88h+Buffer]
0x18003864f  mov     [rsp+88h+Event], rcx
0x180038654  mov     ecx, [rsp+88h+Key]
0x18003865b  mov     dword ptr [rsp+88h+StartingOffset], ecx
0x18003865f  mov     r9b, 1
0x180038662  mov     r8d, edi
0x180038665  mov     rcx, rbx
0x180038668  call    _guard_dispatch_icall
0x18003866d  test    al, al
0x18003866f  jz      short loc_18003867D
0x180038671  cmp     [r15], r12d
0x180038674  jnz     short loc_18003867D
0x180038676  xor     eax, eax
0x180038678  jmp     loc_18003876D
0x18003867d  lea     r12, [rbx+98h]
0x180038684  mov     rcx, r12; Event
0x180038687  call    cs:__imp_KeClearEvent
0x18003868e  nop     dword ptr [rax+rax+00h]
0x180038693  lea     rax, [rbx+68h]
0x180038697  mov     [rsp+88h+IoStatusBlock], r15; IoStatusBlock
0x18003869c  mov     [rsp+88h+Event], rsi; Event
0x1800386a1  mov     [rsp+88h+StartingOffset], rax; StartingOffset
0x1800386a6  mov     r9d, edi; Length
0x1800386a9  mov     r8, [rsp+88h+Buffer]; Buffer
0x1800386b1  mov     rdx, r14; DeviceObject
0x1800386b4  mov     ecx, 4; MajorFunction
0x1800386b9  call    cs:__imp_IoBuildSynchronousFsdRequest
0x1800386c0  nop     dword ptr [rax+rax+00h]
0x1800386c5  mov     rdi, rax
0x1800386c8  test    rax, rax
0x1800386cb  jnz     short loc_1800386D7
0x1800386cd  mov     eax, 0C000009Ah
0x1800386d2  jmp     loc_18003876D
0x1800386d7  mov     al, [rsp+88h+RequestorMode]
0x1800386de  mov     [rdi+40h], al
0x1800386e1  mov     [rdi+0C0h], rbx
0x1800386e8  mov     [rdi+60h], r13
0x1800386ec  mov     rcx, [rdi+0B8h]
0x1800386f3  mov     eax, [rsp+88h+Key]
0x1800386fa  mov     [rcx-38h], eax
0x1800386fd  mov     [rcx-18h], rbx
0x180038701  test    rsi, rsi
0x180038704  jz      short loc_180038715
0x180038706  mov     rcx, rsi; Object
0x180038709  call    cs:__imp_ObfReferenceObject
0x180038710  nop     dword ptr [rax+rax+00h]
0x180038715  mov     rcx, rbx; Object
0x180038718  call    cs:__imp_ObfReferenceObject
0x18003871f  nop     dword ptr [rax+rax+00h]
0x180038724  mov     rdx, rdi; Irp
0x180038727  mov     rcx, r14; DeviceObject
0x18003872a  call    cs:__imp_IofCallDriver
0x180038731  nop     dword ptr [rax+rax+00h]
0x180038736  cmp     eax, 103h
0x18003873b  jnz     short loc_18003876D
0x18003873d  mov     edx, [rbx+50h]
0x180038740  test    dl, 2
0x180038743  jz      short loc_18003876D
0x180038745  mov     [rsp+88h+StartingOffset], 0; Timeout
0x18003874e  xor     r9d, r9d; Alertable
0x180038751  mov     r8b, [rsp+88h+RequestorMode]; WaitMode
0x180038759  xor     edx, edx; WaitReason
0x18003875b  mov     rcx, r12; Object
0x18003875e  call    cs:__imp_KeWaitForSingleObject
0x180038765  nop     dword ptr [rax+rax+00h]
0x18003876a  mov     eax, [rbx+38h]
0x18003876d  add     rsp, 50h
0x180038771  pop     r15
0x180038773  pop     r14
0x180038775  pop     r13
0x180038777  pop     r12
0x180038779  pop     rdi
0x18003877a  pop     rsi
0x18003877b  pop     rbx
0x18003877c  retn
```
