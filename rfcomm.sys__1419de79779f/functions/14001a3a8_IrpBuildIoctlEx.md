# IrpBuildIoctlEx

- ea: `0x14001a3a8`
- end: `0x14001a493`
- name: `IrpBuildIoctlEx`
- size: `235`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003330`
- `0x14001aa18`
- `0x14001ab9c`
- `0x14001ad08`
- `0x14001ade8`
- `0x14001af54`

## callees

- `0x14001a3a8`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x14001a3c1`
- `ntoskrnl!IoAllocateIrp` at `0x14001a3c1`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14001a43e`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14001a43e`

## pseudocode

```c
PIRP __fastcall IrpBuildIoctlEx(
        __int64 a1,
        struct _DEVICE_OBJECT *a2,
        IRP *a3,
        __int64 a4,
        unsigned int a5,
        _IRP *a6,
        unsigned int a7,
        unsigned int a8,
        IO_COMPLETION_ROUTINE *CompletionRoutine,
        PVOID Context)
{
  PIRP Irp; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  _IO_STACK_LOCATION *v13; // rax
  _IO_STACK_LOCATION *v14; // rcx

  Irp = a3;
  if ( a3 || (Irp = IoAllocateIrp(*(_BYTE *)(a1 + 76), 0)) != 0 )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Parameters.Read.Length = a8;
    CurrentStackLocation[-1].Parameters.Create.Options = a7;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = a5;
    CurrentStackLocation[-1].MajorFunction = 14;
    Irp->AssociatedIrp.MasterIrp = a6;
    if ( a2 )
    {
      if ( IoSetCompletionRoutineEx(a2, Irp, CompletionRoutine, Context, 1u, 1u, 1u) < 0 )
      {
        v13 = Irp->Tail.Overlay.CurrentStackLocation;
        v13[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))CompletionRoutine;
        v13[-1].Context = Context;
        v13[-1].Control = -32;
      }
    }
    else
    {
      v14 = Irp->Tail.Overlay.CurrentStackLocation;
      v14[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))CompletionRoutine;
      v14[-1].Context = Context;
      v14[-1].Control = -32;
    }
  }
  return Irp;
}

```

## disassembly

```asm
0x14001a3a8  push    rbx
0x14001a3aa  push    rbp
0x14001a3ab  push    rsi
0x14001a3ac  push    rdi
0x14001a3ad  sub     rsp, 48h
0x14001a3b1  mov     rbx, r8
0x14001a3b4  mov     rdi, rdx
0x14001a3b7  test    r8, r8
0x14001a3ba  jnz     short loc_14001A3D9
0x14001a3bc  mov     cl, [rcx+4Ch]; StackSize
0x14001a3bf  xor     edx, edx; ChargeQuota
0x14001a3c1  call    cs:__imp_IoAllocateIrp
0x14001a3c8  nop     dword ptr [rax+rax+00h]
0x14001a3cd  mov     rbx, rax
0x14001a3d0  test    rax, rax
0x14001a3d3  jz      loc_14001A486
0x14001a3d9  mov     rcx, [rbx+0B8h]
0x14001a3e0  mov     eax, [rsp+68h+arg_38]
0x14001a3e7  mov     [rcx-40h], eax
0x14001a3ea  mov     eax, [rsp+68h+arg_30]
0x14001a3f1  mov     [rcx-38h], eax
0x14001a3f4  mov     eax, [rsp+68h+arg_20]
0x14001a3fb  mov     [rcx-30h], eax
0x14001a3fe  mov     rax, [rsp+68h+arg_28]
0x14001a406  mov     byte ptr [rcx-48h], 0Eh
0x14001a40a  mov     [rbx+18h], rax
0x14001a40e  test    rdi, rdi
0x14001a411  jz      short loc_14001A463
0x14001a413  mov     rsi, [rsp+68h+Context]
0x14001a41b  mov     rdx, rbx; Irp
0x14001a41e  mov     rbp, [rsp+68h+CompletionRoutine]
0x14001a426  mov     r9, rsi; Context
0x14001a429  mov     [rsp+68h+InvokeOnCancel], 1; InvokeOnCancel
0x14001a42e  mov     r8, rbp; CompletionRoutine
0x14001a431  mov     [rsp+68h+InvokeOnError], 1; InvokeOnError
0x14001a436  mov     rcx, rdi; DeviceObject
0x14001a439  mov     [rsp+68h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14001a43e  call    cs:__imp_IoSetCompletionRoutineEx
0x14001a445  nop     dword ptr [rax+rax+00h]
0x14001a44a  test    eax, eax
0x14001a44c  jns     short loc_14001A486
0x14001a44e  mov     rax, [rbx+0B8h]
0x14001a455  mov     [rax-10h], rbp
0x14001a459  mov     [rax-8], rsi
0x14001a45d  mov     byte ptr [rax-45h], 0E0h
0x14001a461  jmp     short loc_14001A486
0x14001a463  mov     rcx, [rbx+0B8h]
0x14001a46a  mov     rax, [rsp+68h+CompletionRoutine]
0x14001a472  mov     [rcx-10h], rax
0x14001a476  mov     rax, [rsp+68h+Context]
0x14001a47e  mov     [rcx-8], rax
0x14001a482  mov     byte ptr [rcx-45h], 0E0h
0x14001a486  mov     rax, rbx
0x14001a489  add     rsp, 48h
0x14001a48d  pop     rdi
0x14001a48e  pop     rsi
0x14001a48f  pop     rbp
0x14001a490  pop     rbx
0x14001a491  retn
```
