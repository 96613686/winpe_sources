# CdpAllocateKernelConnectionIrp

- ea: `0x140008790`
- end: `0x140008883`
- name: `CdpAllocateKernelConnectionIrp`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400083b0`

## callees

- `0x140001600`
- `0x140008790`
- `0x140008a54`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400087ec`
- `ntoskrnl!ExAllocatePool2` at `0x1400087ec`
- `ntoskrnl!IoAllocateIrp` at `0x1400087c2`
- `ntoskrnl!IoAllocateIrp` at `0x1400087c2`

## pseudocode

```c
__int64 __fastcall CdpAllocateKernelConnectionIrp(__int64 a1, __int64 a2, void *a3, PIRP *a4)
{
  const void *v4; // r15
  __int64 v6; // rax
  unsigned int v8; // edi
  PIRP v10; // rbx
  struct _IRP *Pool2; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v13; // rax
  PIRP Irp; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(const void **)(a1 + 24);
  v6 = CdDeviceObject;
  v8 = *(_DWORD *)(a2 + 32);
  *a4 = 0;
  Irp = IoAllocateIrp(*(_BYTE *)(v6 + 76) + 1, 0);
  v10 = Irp;
  if ( Irp )
  {
    Pool2 = (struct _IRP *)ExAllocatePool2(64, v8, 1665360963);
    v10->AssociatedIrp.MasterIrp = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, v4, v8);
      v10->RequestorMode = 0;
      v10->Tail.Overlay.Thread = KeGetCurrentThread();
      CurrentStackLocation = v10->Tail.Overlay.CurrentStackLocation;
      *a4 = v10;
      CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)CdpCompleteServerKernelConnection;
      CurrentStackLocation[-1].Context = a3;
      CurrentStackLocation[-1].Control = -32;
      --v10->Tail.Overlay.CurrentStackLocation;
      --v10->CurrentLocation;
      v13 = v10->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v13->Parameters.Create.SecurityContext = *(_OWORD *)(a2 + 8);
      *(_OWORD *)&v13->Parameters.LockControl.ByteOffset.LowPart = *(_OWORD *)(a2 + 24);
      return 0;
    }
    CdpFreeKernelConnectionIrp(&Irp);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140008790  push    rbx
0x140008792  push    rbp
0x140008793  push    rsi
0x140008794  push    rdi
0x140008795  push    r14
0x140008797  push    r15
0x140008799  sub     rsp, 28h
0x14000879d  mov     r15, [rcx+18h]
0x1400087a1  mov     rsi, rdx
0x1400087a4  mov     rax, cs:CdDeviceObject
0x1400087ab  mov     r14, r9
0x1400087ae  mov     edi, [rdx+20h]
0x1400087b1  mov     rbp, r8
0x1400087b4  xor     edx, edx; ChargeQuota
0x1400087b6  mov     qword ptr [r9], 0
0x1400087bd  mov     cl, [rax+4Ch]
0x1400087c0  inc     cl; StackSize
0x1400087c2  call    cs:__imp_IoAllocateIrp
0x1400087c9  nop     dword ptr [rax+rax+00h]
0x1400087ce  mov     [rsp+58h+arg_0], rax
0x1400087d3  mov     rbx, rax
0x1400087d6  test    rax, rax
0x1400087d9  jz      loc_140008870
0x1400087df  mov     r8d, 63436443h
0x1400087e5  mov     edx, edi
0x1400087e7  mov     ecx, 40h ; '@'
0x1400087ec  call    cs:__imp_ExAllocatePool2
0x1400087f3  nop     dword ptr [rax+rax+00h]
0x1400087f8  mov     [rbx+18h], rax
0x1400087fc  test    rax, rax
0x1400087ff  jz      short loc_140008866
0x140008801  mov     r8d, edi; Size
0x140008804  mov     rdx, r15; Src
0x140008807  mov     rcx, rax; void *
0x14000880a  call    memmove
0x14000880f  mov     byte ptr [rbx+40h], 0
0x140008813  lea     rcx, CdpCompleteServerKernelConnection
0x14000881a  mov     rax, gs:188h
0x140008823  mov     [rbx+98h], rax
0x14000882a  mov     rax, [rbx+0B8h]
0x140008831  mov     [r14], rbx
0x140008834  mov     [rax-10h], rcx
0x140008838  mov     [rax-8], rbp
0x14000883c  mov     byte ptr [rax-45h], 0E0h
0x140008840  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140008848  dec     byte ptr [rbx+43h]
0x14000884b  mov     rax, [rbx+0B8h]
0x140008852  movups  xmm0, xmmword ptr [rsi+8]
0x140008856  movups  xmmword ptr [rax+8], xmm0
0x14000885a  movups  xmm1, xmmword ptr [rsi+18h]
0x14000885e  movups  xmmword ptr [rax+18h], xmm1
0x140008862  xor     eax, eax
0x140008864  jmp     short loc_140008875
0x140008866  lea     rcx, [rsp+58h+arg_0]
0x14000886b  call    CdpFreeKernelConnectionIrp
0x140008870  mov     eax, 0C000009Ah
0x140008875  add     rsp, 28h
0x140008879  pop     r15
0x14000887b  pop     r14
0x14000887d  pop     rdi
0x14000887e  pop     rsi
0x14000887f  pop     rbp
0x140008880  pop     rbx
0x140008881  retn
```
