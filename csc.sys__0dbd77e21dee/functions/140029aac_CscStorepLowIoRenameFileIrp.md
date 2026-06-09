# CscStorepLowIoRenameFileIrp

- ea: `0x140029aac`
- end: `0x140029ca7`
- name: `CscStorepLowIoRenameFileIrp`
- size: `507`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14008a6bc`

## callees

- `0x1400190ec`
- `0x14001cffc`
- `0x140029aac`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140029ba4`
- `ntoskrnl!KeInitializeEvent` at `0x140029ba4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140029bec`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140029bec`
- `ntoskrnl!IofCallDriver` at `0x140029c0f`
- `ntoskrnl!IofCallDriver` at `0x140029c0f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029c46`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029c46`
- `ntoskrnl!IoFreeIrp` at `0x140029c58`
- `ntoskrnl!IoFreeIrp` at `0x140029c58`
- `ntoskrnl!IoAllocateIrp` at `0x140029b2e`
- `ntoskrnl!IoAllocateIrp` at `0x140029b2e`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140029bd1`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140029bd1`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140029bfd`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140029c20`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140029bfd`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140029c20`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140029b1a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140029b1a`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoRenameFileIrp(PFILE_OBJECT FileObject, LARGE_INTEGER a2, struct _IRP *a3, ULONG a4)
{
  PDEVICE_OBJECT RelatedDeviceObject; // r14
  PIRP Irp; // rax
  IRP *v10; // rsi
  NTSTATUS Status; // edi
  int v12; // ebp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  IRP *TopLevelIrp; // rbx
  struct _KEVENT Event; // [rsp+40h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqqD)(
      WPP_GLOBAL_Control->AttachedDevice,
      30,
      WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
      FileObject,
      (LARGE_INTEGER)a2.QuadPart,
      a3,
      a4);
  RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
  Irp = IoAllocateIrp(RelatedDeviceObject->StackSize, 0);
  v10 = Irp;
  if ( Irp )
  {
    Irp->Tail.Overlay.OriginalFileObject = FileObject;
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    Irp->Tail.Overlay.Thread = KeGetCurrentThread();
    Irp->RequestorMode = 0;
    CurrentStackLocation[-1].MajorFunction = 6;
    CurrentStackLocation[-1].FileObject = FileObject;
    CurrentStackLocation[-1].Flags = 1;
    Irp->Flags |= 0x10u;
    Irp->AssociatedIrp.MasterIrp = a3;
    CurrentStackLocation[-1].Parameters.Read.Length = a4;
    CurrentStackLocation[-1].Parameters.Create.Options = 10;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset = a2;
    CurrentStackLocation[-1].Parameters.SetFile.ReplaceIfExists = a3->Type;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    Status = IoSetCompletionRoutineEx(RelatedDeviceObject, v10, CscStorepLowIoIrpCompletionRoutine, &Event, 1u, 1u, 1u);
    if ( Status >= 0 )
    {
      v12 = 0;
      TopLevelIrp = IoGetTopLevelIrp();
      IoSetTopLevelIrp(0);
      Status = IofCallDriver(RelatedDeviceObject, v10);
      IoSetTopLevelIrp(TopLevelIrp);
      if ( Status == 259 )
      {
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        Status = v10->IoStatus.Status;
      }
    }
    else
    {
      v12 = 2377;
    }
    IoFreeIrp(v10);
  }
  else
  {
    Status = -1073741670;
    v12 = 2319;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      31,
      WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
      (unsigned int)Status,
      v12);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140029aac  push    rbx
0x140029aae  push    rbp
0x140029aaf  push    rsi
0x140029ab0  push    rdi
0x140029ab1  push    r13
0x140029ab3  push    r14
0x140029ab5  push    r15
0x140029ab7  sub     rsp, 60h
0x140029abb  xorps   xmm0, xmm0
0x140029abe  xor     eax, eax
0x140029ac0  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x140029ac5  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x140029aca  mov     ebp, r9d
0x140029acd  mov     rdi, r8
0x140029ad0  mov     r15, rdx
0x140029ad3  mov     rbx, rcx
0x140029ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x140029add  lea     r13, WPP_GLOBAL_Control
0x140029ae4  cmp     rcx, r13
0x140029ae7  jz      short loc_140029B17
0x140029ae9  test    dword ptr [rcx+2Ch], 20000h
0x140029af0  jz      short loc_140029B17
0x140029af2  mov     rcx, [rcx+18h]
0x140029af6  lea     edx, [rax+1Eh]
0x140029af9  mov     dword ptr [rsp+98h+InvokeOnCancel], r9d
0x140029afe  mov     r9, rbx
0x140029b01  mov     qword ptr [rsp+98h+InvokeOnError], r8
0x140029b06  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x140029b0d  mov     qword ptr [rsp+98h+InvokeOnSuccess], r15
0x140029b12  call    WPP_SF_qqqD
0x140029b17  mov     rcx, rbx; FileObject
0x140029b1a  call    cs:__imp_IoGetRelatedDeviceObject
0x140029b21  nop     dword ptr [rax+rax+00h]
0x140029b26  xor     edx, edx; ChargeQuota
0x140029b28  mov     r14, rax
0x140029b2b  mov     cl, [rax+4Ch]; StackSize
0x140029b2e  call    cs:__imp_IoAllocateIrp
0x140029b35  nop     dword ptr [rax+rax+00h]
0x140029b3a  mov     rsi, rax
0x140029b3d  test    rax, rax
0x140029b40  jnz     short loc_140029B51
0x140029b42  mov     edi, 0C000009Ah
0x140029b47  mov     ebp, 90Fh
0x140029b4c  jmp     loc_140029C64
0x140029b51  mov     [rax+0C0h], rbx
0x140029b58  xor     r8d, r8d; State
0x140029b5b  mov     rax, gs:188h
0x140029b64  xor     edx, edx; Type
0x140029b66  mov     rcx, [rsi+0B8h]
0x140029b6d  mov     [rsi+98h], rax
0x140029b74  mov     byte ptr [rsi+40h], 0
0x140029b78  mov     byte ptr [rcx-48h], 6
0x140029b7c  mov     [rcx-18h], rbx
0x140029b80  mov     byte ptr [rcx-46h], 1
0x140029b84  or      dword ptr [rsi+10h], 10h
0x140029b88  mov     [rsi+18h], rdi
0x140029b8c  mov     [rcx-40h], ebp
0x140029b8f  mov     dword ptr [rcx-38h], 0Ah
0x140029b96  mov     [rcx-30h], r15
0x140029b9a  mov     al, [rdi]
0x140029b9c  mov     [rcx-28h], al
0x140029b9f  lea     rcx, [rsp+98h+Event]; Event
0x140029ba4  call    cs:__imp_KeInitializeEvent
0x140029bab  nop     dword ptr [rax+rax+00h]
0x140029bb0  mov     [rsp+98h+InvokeOnCancel], 1; InvokeOnCancel
0x140029bb5  lea     r9, [rsp+98h+Event]; Context
0x140029bba  mov     [rsp+98h+InvokeOnError], 1; InvokeOnError
0x140029bbf  lea     r8, CscStorepLowIoIrpCompletionRoutine; CompletionRoutine
0x140029bc6  mov     rdx, rsi; Irp
0x140029bc9  mov     [rsp+98h+InvokeOnSuccess], 1; InvokeOnSuccess
0x140029bce  mov     rcx, r14; DeviceObject
0x140029bd1  call    cs:__imp_IoSetCompletionRoutineEx
0x140029bd8  nop     dword ptr [rax+rax+00h]
0x140029bdd  mov     edi, eax
0x140029bdf  test    eax, eax
0x140029be1  jns     short loc_140029BEA
0x140029be3  mov     ebp, 949h
0x140029be8  jmp     short loc_140029C55
0x140029bea  xor     ebp, ebp
0x140029bec  call    cs:__imp_IoGetTopLevelIrp
0x140029bf3  nop     dword ptr [rax+rax+00h]
0x140029bf8  xor     ecx, ecx; Irp
0x140029bfa  mov     rbx, rax
0x140029bfd  call    cs:__imp_IoSetTopLevelIrp
0x140029c04  nop     dword ptr [rax+rax+00h]
0x140029c09  mov     rdx, rsi; Irp
0x140029c0c  mov     rcx, r14; DeviceObject
0x140029c0f  call    cs:__imp_IofCallDriver
0x140029c16  nop     dword ptr [rax+rax+00h]
0x140029c1b  mov     rcx, rbx; Irp
0x140029c1e  mov     edi, eax
0x140029c20  call    cs:__imp_IoSetTopLevelIrp
0x140029c27  nop     dword ptr [rax+rax+00h]
0x140029c2c  cmp     edi, 103h
0x140029c32  jnz     short loc_140029C55
0x140029c34  xor     r9d, r9d; Alertable
0x140029c37  mov     qword ptr [rsp+98h+InvokeOnSuccess], rbp; Timeout
0x140029c3c  xor     r8d, r8d; WaitMode
0x140029c3f  lea     rcx, [rsp+98h+Event]; Object
0x140029c44  xor     edx, edx; WaitReason
0x140029c46  call    cs:__imp_KeWaitForSingleObject
0x140029c4d  nop     dword ptr [rax+rax+00h]
0x140029c52  mov     edi, [rsi+30h]
0x140029c55  mov     rcx, rsi; Irp
0x140029c58  call    cs:__imp_IoFreeIrp
0x140029c5f  nop     dword ptr [rax+rax+00h]
0x140029c64  mov     rcx, cs:WPP_GLOBAL_Control
0x140029c6b  cmp     rcx, r13
0x140029c6e  jz      short loc_140029C95
0x140029c70  test    dword ptr [rcx+2Ch], 20000h
0x140029c77  jz      short loc_140029C95
0x140029c79  mov     rcx, [rcx+18h]
0x140029c7d  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x140029c84  mov     edx, 1Fh
0x140029c89  mov     dword ptr [rsp+98h+InvokeOnSuccess], ebp
0x140029c8d  mov     r9d, edi
0x140029c90  call    WPP_SF_Dd
0x140029c95  mov     eax, edi
0x140029c97  add     rsp, 60h
0x140029c9b  pop     r15
0x140029c9d  pop     r14
0x140029c9f  pop     r13
0x140029ca1  pop     rdi
0x140029ca2  pop     rsi
0x140029ca3  pop     rbp
0x140029ca4  pop     rbx
0x140029ca5  retn
```
