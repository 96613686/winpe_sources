# CscStorepLowIoSetEndOfFileInformationFileIrp

- ea: `0x14008a210`
- end: `0x14008a4a4`
- name: `CscStorepLowIoSetEndOfFileInformationFileIrp`
- size: `660`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010880`
- `0x140010be0`

## callees

- `0x1400190ec`
- `0x140020028`
- `0x14008a210`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14008a36d`
- `ntoskrnl!KeInitializeEvent` at `0x14008a36d`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14008a3b8`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14008a3b8`
- `ntoskrnl!IofCallDriver` at `0x14008a3db`
- `ntoskrnl!IofCallDriver` at `0x14008a3db`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008a412`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008a412`
- `ntoskrnl!IoFreeIrp` at `0x14008a457`
- `ntoskrnl!IoFreeIrp` at `0x14008a457`
- `ntoskrnl!IoAllocateIrp` at `0x14008a2df`
- `ntoskrnl!IoAllocateIrp` at `0x14008a2df`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14008a39a`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14008a39a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14008a3c9`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14008a3ec`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14008a3c9`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14008a3ec`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14008a2cb`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14008a2cb`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoSetEndOfFileInformationFileIrp(PFILE_OBJECT FileObject, __int64 a2, ULONG a3, int a4)
{
  unsigned int Status; // edi
  int v9; // ebp
  PDEVICE_OBJECT RelatedDeviceObject; // r14
  PIRP Irp; // rax
  IRP *v12; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  IRP *TopLevelIrp; // rbx
  struct _KEVENT Event; // [rsp+40h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qDqd(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      (unsigned int)WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
      (_DWORD)FileObject,
      a3,
      a2,
      a4);
  if ( FileObject )
  {
    if ( a3 )
    {
      if ( a2 )
      {
        if ( a4 == 20 )
        {
          RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
          Irp = IoAllocateIrp(RelatedDeviceObject->StackSize, 0);
          v12 = Irp;
          if ( Irp )
          {
            Irp->Tail.Overlay.OriginalFileObject = FileObject;
            Irp->Tail.Overlay.Thread = KeGetCurrentThread();
            Irp->RequestorMode = 0;
            Irp->MdlAddress = 0;
            Irp->Overlay.AllocationSize.QuadPart = 0;
            Irp->AssociatedIrp.MasterIrp = (struct _IRP *)a2;
            if ( *(int *)(a2 + 4) >= 0 )
            {
              CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
              v12->Flags |= 0x10u;
              CurrentStackLocation[-1].MajorFunction = 6;
              CurrentStackLocation[-1].FileObject = FileObject;
              CurrentStackLocation[-1].Parameters.Read.Length = a3;
              CurrentStackLocation[-1].Parameters.Create.Options = 20;
              KeInitializeEvent(&Event, NotificationEvent, 0);
              Status = IoSetCompletionRoutineEx(
                         RelatedDeviceObject,
                         v12,
                         CscStorepLowIoIrpCompletionRoutine,
                         &Event,
                         1u,
                         1u,
                         1u);
              if ( (Status & 0x80000000) == 0 )
              {
                v9 = 0;
                TopLevelIrp = IoGetTopLevelIrp();
                IoSetTopLevelIrp(0);
                Status = IofCallDriver(RelatedDeviceObject, v12);
                IoSetTopLevelIrp(TopLevelIrp);
                if ( Status == 259 )
                {
                  KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
                  Status = v12->IoStatus.Status;
                }
                else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
                {
                  WPP_SF_Dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    27,
                    WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
                    Status,
                    0);
                }
              }
              else
              {
                v9 = 2038;
              }
            }
            else
            {
              Status = -1073741811;
              v9 = 2006;
            }
            IoFreeIrp(v12);
          }
          else
          {
            Status = -1073741670;
            v9 = 1989;
          }
        }
        else
        {
          Status = -1073741811;
          v9 = 1979;
        }
      }
      else
      {
        Status = -1073741811;
        v9 = 1972;
      }
    }
    else
    {
      Status = -1073741811;
      v9 = 1965;
    }
  }
  else
  {
    Status = -1073741811;
    v9 = 1958;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_0d06f681978d342119bb40210e69c50f_Traceguids, Status, v9);
  return Status;
}

```

## disassembly

```asm
0x14008a210  push    rbx
0x14008a212  push    rbp
0x14008a213  push    rsi
0x14008a214  push    rdi
0x14008a215  push    r12
0x14008a217  push    r14
0x14008a219  sub     rsp, 68h
0x14008a21d  xorps   xmm0, xmm0
0x14008a220  xor     eax, eax
0x14008a222  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x14008a227  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x14008a22c  mov     esi, r9d
0x14008a22f  mov     ebp, r8d
0x14008a232  mov     rdi, rdx
0x14008a235  mov     rbx, rcx
0x14008a238  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a23f  lea     r12, WPP_GLOBAL_Control
0x14008a246  cmp     rcx, r12
0x14008a249  jz      short loc_14008A279
0x14008a24b  test    dword ptr [rcx+2Ch], 40000h
0x14008a252  jz      short loc_14008A279
0x14008a254  mov     rcx, [rcx+18h]
0x14008a258  lea     edx, [rax+1Ah]
0x14008a25b  mov     dword ptr [rsp+98h+InvokeOnCancel], r9d
0x14008a260  mov     r9, rbx
0x14008a263  mov     qword ptr [rsp+98h+InvokeOnError], rdi
0x14008a268  mov     dword ptr [rsp+98h+InvokeOnSuccess], r8d
0x14008a26d  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14008a274  call    WPP_SF_qDqd
0x14008a279  test    rbx, rbx
0x14008a27c  jnz     short loc_14008A28D
0x14008a27e  mov     edi, 0C000000Dh
0x14008a283  mov     ebp, 7A6h
0x14008a288  jmp     loc_14008A463
0x14008a28d  test    ebp, ebp
0x14008a28f  jnz     short loc_14008A2A0
0x14008a291  mov     edi, 0C000000Dh
0x14008a296  mov     ebp, 7ADh
0x14008a29b  jmp     loc_14008A463
0x14008a2a0  test    rdi, rdi
0x14008a2a3  jnz     short loc_14008A2B4
0x14008a2a5  mov     edi, 0C000000Dh
0x14008a2aa  mov     ebp, 7B4h
0x14008a2af  jmp     loc_14008A463
0x14008a2b4  cmp     esi, 14h
0x14008a2b7  jz      short loc_14008A2C8
0x14008a2b9  mov     edi, 0C000000Dh
0x14008a2be  mov     ebp, 7BBh
0x14008a2c3  jmp     loc_14008A463
0x14008a2c8  mov     rcx, rbx; FileObject
0x14008a2cb  call    cs:__imp_IoGetRelatedDeviceObject
0x14008a2d2  nop     dword ptr [rax+rax+00h]
0x14008a2d7  xor     edx, edx; ChargeQuota
0x14008a2d9  mov     r14, rax
0x14008a2dc  mov     cl, [rax+4Ch]; StackSize
0x14008a2df  call    cs:__imp_IoAllocateIrp
0x14008a2e6  nop     dword ptr [rax+rax+00h]
0x14008a2eb  mov     rsi, rax
0x14008a2ee  test    rax, rax
0x14008a2f1  jnz     short loc_14008A302
0x14008a2f3  mov     edi, 0C000009Ah
0x14008a2f8  mov     ebp, 7C5h
0x14008a2fd  jmp     loc_14008A463
0x14008a302  mov     [rax+0C0h], rbx
0x14008a309  mov     rax, gs:188h
0x14008a312  mov     [rsi+98h], rax
0x14008a319  mov     byte ptr [rsi+40h], 0
0x14008a31d  mov     qword ptr [rsi+8], 0
0x14008a325  mov     qword ptr [rsi+58h], 0
0x14008a32d  mov     [rsi+18h], rdi
0x14008a331  cmp     dword ptr [rdi+4], 0
0x14008a335  jge     short loc_14008A346
0x14008a337  mov     edi, 0C000000Dh
0x14008a33c  mov     ebp, 7D6h
0x14008a341  jmp     loc_14008A454
0x14008a346  mov     rax, [rsi+0B8h]
0x14008a34d  lea     rcx, [rsp+98h+Event]; Event
0x14008a352  or      dword ptr [rsi+10h], 10h
0x14008a356  xor     r8d, r8d; State
0x14008a359  xor     edx, edx; Type
0x14008a35b  mov     byte ptr [rax-48h], 6
0x14008a35f  mov     [rax-18h], rbx
0x14008a363  mov     [rax-40h], ebp
0x14008a366  mov     dword ptr [rax-38h], 14h
0x14008a36d  call    cs:__imp_KeInitializeEvent
0x14008a374  nop     dword ptr [rax+rax+00h]
0x14008a379  mov     [rsp+98h+InvokeOnCancel], 1; InvokeOnCancel
0x14008a37e  lea     r9, [rsp+98h+Event]; Context
0x14008a383  mov     [rsp+98h+InvokeOnError], 1; InvokeOnError
0x14008a388  lea     r8, CscStorepLowIoIrpCompletionRoutine; CompletionRoutine
0x14008a38f  mov     rdx, rsi; Irp
0x14008a392  mov     [rsp+98h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14008a397  mov     rcx, r14; DeviceObject
0x14008a39a  call    cs:__imp_IoSetCompletionRoutineEx
0x14008a3a1  nop     dword ptr [rax+rax+00h]
0x14008a3a6  mov     edi, eax
0x14008a3a8  test    eax, eax
0x14008a3aa  jns     short loc_14008A3B6
0x14008a3ac  mov     ebp, 7F6h
0x14008a3b1  jmp     loc_14008A454
0x14008a3b6  xor     ebp, ebp
0x14008a3b8  call    cs:__imp_IoGetTopLevelIrp
0x14008a3bf  nop     dword ptr [rax+rax+00h]
0x14008a3c4  xor     ecx, ecx; Irp
0x14008a3c6  mov     rbx, rax
0x14008a3c9  call    cs:__imp_IoSetTopLevelIrp
0x14008a3d0  nop     dword ptr [rax+rax+00h]
0x14008a3d5  mov     rdx, rsi; Irp
0x14008a3d8  mov     rcx, r14; DeviceObject
0x14008a3db  call    cs:__imp_IofCallDriver
0x14008a3e2  nop     dword ptr [rax+rax+00h]
0x14008a3e7  mov     rcx, rbx; Irp
0x14008a3ea  mov     edi, eax
0x14008a3ec  call    cs:__imp_IoSetTopLevelIrp
0x14008a3f3  nop     dword ptr [rax+rax+00h]
0x14008a3f8  cmp     edi, 103h
0x14008a3fe  jnz     short loc_14008A423
0x14008a400  xor     r9d, r9d; Alertable
0x14008a403  mov     qword ptr [rsp+98h+InvokeOnSuccess], rbp; Timeout
0x14008a408  xor     r8d, r8d; WaitMode
0x14008a40b  lea     rcx, [rsp+98h+Event]; Object
0x14008a410  xor     edx, edx; WaitReason
0x14008a412  call    cs:__imp_KeWaitForSingleObject
0x14008a419  nop     dword ptr [rax+rax+00h]
0x14008a41e  mov     edi, [rsi+30h]
0x14008a421  jmp     short loc_14008A454
0x14008a423  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a42a  cmp     rcx, r12
0x14008a42d  jz      short loc_14008A454
0x14008a42f  test    dword ptr [rcx+2Ch], 20000h
0x14008a436  jz      short loc_14008A454
0x14008a438  mov     rcx, [rcx+18h]
0x14008a43c  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14008a443  mov     edx, 1Bh
0x14008a448  mov     dword ptr [rsp+98h+InvokeOnSuccess], ebp
0x14008a44c  mov     r9d, edi
0x14008a44f  call    WPP_SF_Dd
0x14008a454  mov     rcx, rsi; Irp
0x14008a457  call    cs:__imp_IoFreeIrp
0x14008a45e  nop     dword ptr [rax+rax+00h]
0x14008a463  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a46a  cmp     rcx, r12
0x14008a46d  jz      short loc_14008A494
0x14008a46f  test    dword ptr [rcx+2Ch], 40000h
0x14008a476  jz      short loc_14008A494
0x14008a478  mov     rcx, [rcx+18h]
0x14008a47c  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14008a483  mov     edx, 1Ch
0x14008a488  mov     dword ptr [rsp+98h+InvokeOnSuccess], ebp
0x14008a48c  mov     r9d, edi
0x14008a48f  call    WPP_SF_Dd
0x14008a494  mov     eax, edi
0x14008a496  add     rsp, 68h
0x14008a49a  pop     r14
0x14008a49c  pop     r12
0x14008a49e  pop     rdi
0x14008a49f  pop     rsi
0x14008a4a0  pop     rbp
0x14008a4a1  pop     rbx
0x14008a4a2  retn
```
