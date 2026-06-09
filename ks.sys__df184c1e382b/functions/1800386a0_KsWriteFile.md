# KsWriteFile

- ea: `0x1800386a0`
- end: `0x18003888e`
- name: `KsWriteFile`
- size: `494`
- prototype: `NTSTATUS __stdcall(PFILE_OBJECT FileObject, PKEVENT Event, PVOID PortContext, PIO_STATUS_BLOCK IoStatusBlock, PVOID Buffer, ULONG Length, ULONG Key, KPROCESSOR_MODE RequestorMode)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180019cb0`
- `0x1800386a0`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x180038819`
- `ntoskrnl!ObfReferenceObject` at `0x180038828`
- `ntoskrnl!ObfReferenceObject` at `0x180038819`
- `ntoskrnl!ObfReferenceObject` at `0x180038828`
- `ntoskrnl!IofCallDriver` at `0x18003883a`
- `ntoskrnl!IofCallDriver` at `0x18003883a`
- `ntoskrnl!ExGetPreviousMode` at `0x18003872d`
- `ntoskrnl!ExGetPreviousMode` at `0x18003872d`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1800387c9`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1800387c9`
- `ntoskrnl!ProbeForRead` at `0x1800386f8`
- `ntoskrnl!ProbeForRead` at `0x1800386f8`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18003870e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18003870e`
- `ntoskrnl!KeClearEvent` at `0x1800386c7`
- `ntoskrnl!KeClearEvent` at `0x180038797`
- `ntoskrnl!KeClearEvent` at `0x1800386c7`
- `ntoskrnl!KeClearEvent` at `0x180038797`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003886e`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003886e`

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
0x1800386a0  push    rbx
0x1800386a2  push    rsi
0x1800386a3  push    rdi
0x1800386a4  push    r12
0x1800386a6  push    r13
0x1800386a8  push    r14
0x1800386aa  push    r15
0x1800386ac  sub     rsp, 50h
0x1800386b0  mov     r15, r9
0x1800386b3  mov     r13, r8
0x1800386b6  mov     rsi, rdx
0x1800386b9  mov     rbx, rcx
0x1800386bc  xor     r12d, r12d
0x1800386bf  test    rdx, rdx
0x1800386c2  jz      short loc_1800386D3
0x1800386c4  mov     rcx, rdx; Event
0x1800386c7  call    cs:__imp_KeClearEvent
0x1800386ce  nop     dword ptr [rax+rax+00h]
0x1800386d3  mov     edi, [rsp+88h+Length]
0x1800386da  test    edi, edi
0x1800386dc  jz      short loc_18003870B
0x1800386de  cmp     [rsp+88h+RequestorMode], r12b
0x1800386e6  jz      short loc_18003870B
0x1800386e8  mov     edx, edi; Length
0x1800386ea  mov     r8d, 1; Alignment
0x1800386f0  mov     rcx, [rsp+88h+Buffer]; Address
0x1800386f8  call    cs:__imp_ProbeForRead
0x1800386ff  nop     dword ptr [rax+rax+00h]
0x180038704  jmp     short loc_18003870B
0x180038706  jmp     loc_18003887D
0x18003870b  mov     rcx, rbx; FileObject
0x18003870e  call    cs:__imp_IoGetRelatedDeviceObject
0x180038715  nop     dword ptr [rax+rax+00h]
0x18003871a  mov     r14, rax
0x18003871d  cmp     [rbx+30h], r12
0x180038721  jz      short loc_18003878D
0x180038723  cmp     [rsp+88h+RequestorMode], r12b
0x18003872b  jnz     short loc_18003873D
0x18003872d  call    cs:__imp_ExGetPreviousMode
0x180038734  nop     dword ptr [rax+rax+00h]
0x180038739  test    al, al
0x18003873b  jnz     short loc_18003878D
0x18003873d  mov     rcx, [r14+8]
0x180038741  mov     r8, [rcx+50h]
0x180038745  lea     rdx, [rbx+68h]
0x180038749  mov     rax, [r8+18h]
0x18003874d  mov     [rsp+88h+var_50], r14
0x180038752  mov     [rsp+88h+IoStatusBlock], r15
0x180038757  mov     rcx, [rsp+88h+Buffer]
0x18003875f  mov     [rsp+88h+Event], rcx
0x180038764  mov     ecx, [rsp+88h+Key]
0x18003876b  mov     dword ptr [rsp+88h+StartingOffset], ecx
0x18003876f  mov     r9b, 1
0x180038772  mov     r8d, edi
0x180038775  mov     rcx, rbx
0x180038778  call    _guard_dispatch_icall
0x18003877d  test    al, al
0x18003877f  jz      short loc_18003878D
0x180038781  cmp     [r15], r12d
0x180038784  jnz     short loc_18003878D
0x180038786  xor     eax, eax
0x180038788  jmp     loc_18003887D
0x18003878d  lea     r12, [rbx+98h]
0x180038794  mov     rcx, r12; Event
0x180038797  call    cs:__imp_KeClearEvent
0x18003879e  nop     dword ptr [rax+rax+00h]
0x1800387a3  lea     rax, [rbx+68h]
0x1800387a7  mov     [rsp+88h+IoStatusBlock], r15; IoStatusBlock
0x1800387ac  mov     [rsp+88h+Event], rsi; Event
0x1800387b1  mov     [rsp+88h+StartingOffset], rax; StartingOffset
0x1800387b6  mov     r9d, edi; Length
0x1800387b9  mov     r8, [rsp+88h+Buffer]; Buffer
0x1800387c1  mov     rdx, r14; DeviceObject
0x1800387c4  mov     ecx, 4; MajorFunction
0x1800387c9  call    cs:__imp_IoBuildSynchronousFsdRequest
0x1800387d0  nop     dword ptr [rax+rax+00h]
0x1800387d5  mov     rdi, rax
0x1800387d8  test    rax, rax
0x1800387db  jnz     short loc_1800387E7
0x1800387dd  mov     eax, 0C000009Ah
0x1800387e2  jmp     loc_18003887D
0x1800387e7  mov     al, [rsp+88h+RequestorMode]
0x1800387ee  mov     [rdi+40h], al
0x1800387f1  mov     [rdi+0C0h], rbx
0x1800387f8  mov     [rdi+60h], r13
0x1800387fc  mov     rcx, [rdi+0B8h]
0x180038803  mov     eax, [rsp+88h+Key]
0x18003880a  mov     [rcx-38h], eax
0x18003880d  mov     [rcx-18h], rbx
0x180038811  test    rsi, rsi
0x180038814  jz      short loc_180038825
0x180038816  mov     rcx, rsi; Object
0x180038819  call    cs:__imp_ObfReferenceObject
0x180038820  nop     dword ptr [rax+rax+00h]
0x180038825  mov     rcx, rbx; Object
0x180038828  call    cs:__imp_ObfReferenceObject
0x18003882f  nop     dword ptr [rax+rax+00h]
0x180038834  mov     rdx, rdi; Irp
0x180038837  mov     rcx, r14; DeviceObject
0x18003883a  call    cs:__imp_IofCallDriver
0x180038841  nop     dword ptr [rax+rax+00h]
0x180038846  cmp     eax, 103h
0x18003884b  jnz     short loc_18003887D
0x18003884d  mov     edx, [rbx+50h]
0x180038850  test    dl, 2
0x180038853  jz      short loc_18003887D
0x180038855  mov     [rsp+88h+StartingOffset], 0; Timeout
0x18003885e  xor     r9d, r9d; Alertable
0x180038861  mov     r8b, [rsp+88h+RequestorMode]; WaitMode
0x180038869  xor     edx, edx; WaitReason
0x18003886b  mov     rcx, r12; Object
0x18003886e  call    cs:__imp_KeWaitForSingleObject
0x180038875  nop     dword ptr [rax+rax+00h]
0x18003887a  mov     eax, [rbx+38h]
0x18003887d  add     rsp, 50h
0x180038881  pop     r15
0x180038883  pop     r14
0x180038885  pop     r13
0x180038887  pop     r12
0x180038889  pop     rdi
0x18003888a  pop     rsi
0x18003888b  pop     rbx
0x18003888c  retn
```
