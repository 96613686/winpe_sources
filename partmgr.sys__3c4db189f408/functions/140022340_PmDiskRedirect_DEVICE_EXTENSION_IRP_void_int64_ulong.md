# PmDiskRedirect(_DEVICE_EXTENSION *,_IRP *,void *,__int64,ulong)

- ea: `0x140022340`
- end: `0x140022495`
- name: `?PmDiskRedirect@@YAJPEAU_DEVICE_EXTENSION@@PEAU_IRP@@PEAX_JK@Z`
- size: `341`
- prototype: `int(struct _DEVICE_EXTENSION *, struct _IRP *, void *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e170`

## callees

- `0x140022340`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140022477`
- `ntoskrnl!IoFreeIrp` at `0x140022477`
- `ntoskrnl!IoFreeMdl` at `0x140022468`
- `ntoskrnl!IoFreeMdl` at `0x140022468`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002244b`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002244b`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400223c9`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400223c9`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x140022432`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x140022432`
- `ntoskrnl!IoAllocateMdl` at `0x14002239e`
- `ntoskrnl!IoAllocateMdl` at `0x14002239e`
- `ntoskrnl!IoMakeAssociatedIrp` at `0x140022367`
- `ntoskrnl!IoMakeAssociatedIrp` at `0x140022367`

## pseudocode

```c
__int64 __fastcall PmDiskRedirect(
        struct _DEVICE_EXTENSION *a1,
        struct _IRP *a2,
        char *a3,
        LARGE_INTEGER a4,
        ULONG Length)
{
  IRP *Irp; // rax
  IRP *v10; // rdi
  int Status; // ebx
  struct _MDL *Mdl; // rax
  struct _MDL *v13; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v15; // rcx

  Irp = IoMakeAssociatedIrp(a2, *(_BYTE *)(*((_QWORD *)a1 + 2) + 76LL) + 1);
  v10 = Irp;
  if ( Irp )
  {
    Mdl = IoAllocateMdl(a3, Length, 0, 0, Irp);
    v13 = Mdl;
    if ( Mdl )
    {
      IoBuildPartialMdl(a2->MdlAddress, Mdl, a3, Length);
      CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
      v15 = v10->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v15[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
      *(_OWORD *)&v15[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v15[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota + 6);
      v15[-1].FileObject = CurrentStackLocation->FileObject;
      v15[-1].Parameters.Read.Length = Length;
      v15[-1].Parameters.Read.ByteOffset = a4;
      --v10->CurrentLocation;
      --v10->Tail.Overlay.CurrentStackLocation;
      Status = IoPropagateIrpExtensionEx(
                 a2,
                 v10,
                 &a3[-a2->MdlAddress->ByteOffset] - (char *)a2->MdlAddress->StartVa,
                 0xFFFFFFFFLL);
      if ( Status >= 0 )
      {
        IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)a1 + 2), v10);
        Status = v10->IoStatus.Status;
        if ( Status >= 0 )
          _InterlockedAdd((volatile signed __int32 *)&a2->IoStatus.Information, v10->IoStatus.Information);
      }
      IoFreeMdl(v13);
    }
    else
    {
      Status = -1073741670;
    }
    IoFreeIrp(v10);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140022340  push    rbx
0x140022342  push    rbp
0x140022343  push    rsi
0x140022344  push    rdi
0x140022345  push    r12
0x140022347  push    r14
0x140022349  push    r15
0x14002234b  sub     rsp, 30h
0x14002234f  mov     rax, [rcx+10h]
0x140022353  mov     rsi, rdx
0x140022356  mov     r14, rcx
0x140022359  mov     r12, r9
0x14002235c  mov     rcx, rsi; Irp
0x14002235f  mov     rbx, r8
0x140022362  mov     dl, [rax+4Ch]
0x140022365  inc     dl; StackSize
0x140022367  call    cs:__imp_IoMakeAssociatedIrp
0x14002236e  nop     dword ptr [rax+rax+00h]
0x140022373  mov     rdi, rax
0x140022376  test    rax, rax
0x140022379  jnz     short loc_140022385
0x14002237b  mov     ebx, 0C000009Ah
0x140022380  jmp     loc_140022483
0x140022385  mov     r15d, [rsp+68h+Length]
0x14002238d  xor     r9d, r9d; ChargeQuota
0x140022390  mov     edx, r15d; Length
0x140022393  mov     [rsp+68h+Irp], rdi; Irp
0x140022398  xor     r8d, r8d; SecondaryBuffer
0x14002239b  mov     rcx, rbx; VirtualAddress
0x14002239e  call    cs:__imp_IoAllocateMdl
0x1400223a5  nop     dword ptr [rax+rax+00h]
0x1400223aa  mov     rbp, rax
0x1400223ad  test    rax, rax
0x1400223b0  jnz     short loc_1400223BC
0x1400223b2  mov     ebx, 0C000009Ah
0x1400223b7  jmp     loc_140022474
0x1400223bc  mov     rcx, [rsi+8]; SourceMdl
0x1400223c0  mov     r9d, r15d; Length
0x1400223c3  mov     r8, rbx; VirtualAddress
0x1400223c6  mov     rdx, rbp; TargetMdl
0x1400223c9  call    cs:__imp_IoBuildPartialMdl
0x1400223d0  nop     dword ptr [rax+rax+00h]
0x1400223d5  mov     rax, [rsi+0B8h]
0x1400223dc  or      r9d, 0FFFFFFFFh
0x1400223e0  mov     rcx, [rdi+0B8h]
0x1400223e7  mov     rdx, rdi
0x1400223ea  movups  xmm0, xmmword ptr [rax]
0x1400223ed  movups  xmmword ptr [rcx-48h], xmm0
0x1400223f1  movups  xmm1, xmmword ptr [rax+10h]
0x1400223f5  movups  xmmword ptr [rcx-38h], xmm1
0x1400223f9  movups  xmm0, xmmword ptr [rax+20h]
0x1400223fd  movups  xmmword ptr [rcx-28h], xmm0
0x140022401  movsd   xmm1, qword ptr [rax+30h]
0x140022406  movsd   qword ptr [rcx-18h], xmm1
0x14002240b  mov     [rcx-40h], r15d
0x14002240f  mov     [rcx-30h], r12
0x140022413  dec     byte ptr [rdi+43h]
0x140022416  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14002241e  mov     rcx, [rsi+8]
0x140022422  mov     eax, [rcx+2Ch]
0x140022425  sub     rbx, rax
0x140022428  sub     rbx, [rcx+20h]
0x14002242c  mov     rcx, rsi
0x14002242f  mov     r8, rbx
0x140022432  call    cs:__imp_IoPropagateIrpExtensionEx
0x140022439  nop     dword ptr [rax+rax+00h]
0x14002243e  mov     ebx, eax
0x140022440  test    eax, eax
0x140022442  js      short loc_140022465
0x140022444  mov     rcx, [r14+10h]; DeviceObject
0x140022448  mov     rdx, rdi; Irp
0x14002244b  call    cs:__imp_IoForwardIrpSynchronously
0x140022452  nop     dword ptr [rax+rax+00h]
0x140022457  mov     ebx, [rdi+30h]
0x14002245a  test    ebx, ebx
0x14002245c  js      short loc_140022465
0x14002245e  mov     eax, [rdi+38h]
0x140022461  lock add [rsi+38h], eax
0x140022465  mov     rcx, rbp; Mdl
0x140022468  call    cs:__imp_IoFreeMdl
0x14002246f  nop     dword ptr [rax+rax+00h]
0x140022474  mov     rcx, rdi; Irp
0x140022477  call    cs:__imp_IoFreeIrp
0x14002247e  nop     dword ptr [rax+rax+00h]
0x140022483  mov     eax, ebx
0x140022485  add     rsp, 30h
0x140022489  pop     r15
0x14002248b  pop     r14
0x14002248d  pop     r12
0x14002248f  pop     rdi
0x140022490  pop     rsi
0x140022491  pop     rbp
0x140022492  pop     rbx
0x140022493  retn
```
