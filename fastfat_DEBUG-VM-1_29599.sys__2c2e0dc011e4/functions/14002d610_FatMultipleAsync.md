# FatMultipleAsync

- ea: `0x14002d610`
- end: `0x14002d911`
- name: `FatMultipleAsync`
- size: `769`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002d918`
- `0x14004af08`

## callees

- `0x140001ef8`
- `0x14002d610`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14005cd06`
- `ntoskrnl!IoFreeMdl` at `0x14005cd06`
- `ntoskrnl!IoAllocateMdl` at `0x14002d727`
- `ntoskrnl!IoAllocateMdl` at `0x14002d727`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x14002d8f3`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x14002d8f3`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002d76b`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002d76b`
- `ntoskrnl!IoMakeAssociatedIrp` at `0x14002d6d2`
- `ntoskrnl!IoMakeAssociatedIrp` at `0x14002d6d2`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x14002d860`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x14002d879`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x14002d860`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x14002d879`
- `ntoskrnl!IoFreeIrp` at `0x14005cd16`
- `ntoskrnl!IoFreeIrp` at `0x14005cd16`
- `ntoskrnl!KeBugCheckEx` at `0x14005ccd5`
- `ntoskrnl!KeBugCheckEx` at `0x14005ccd5`
- `ntoskrnl!ExRaiseStatus` at `0x14002d6f4`
- `ntoskrnl!ExRaiseStatus` at `0x14002d744`
- `ntoskrnl!ExRaiseStatus` at `0x14002d6f4`
- `ntoskrnl!ExRaiseStatus` at `0x14002d744`

## pseudocode

```c
__int64 __fastcall FatMultipleAsync(__int64 a1, __int64 a2, IRP *a3, unsigned int a4, __int64 a5)
{
  __int64 v7; // r10
  _DWORD *v9; // rbx
  int v10; // r8d
  _DWORD *v11; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _ERESOURCE *v13; // rcx
  unsigned int v14; // r14d
  __int64 v15; // rdx
  int v16; // r9d
  __int64 v17; // r12
  IRP *Irp; // rdx
  struct _MDL *Mdl; // rdx
  struct _IO_STACK_LOCATION *v20; // rcx
  struct _IO_STACK_LOCATION *v21; // rcx
  __int64 (__fastcall *v22)(__int64, __int64, volatile signed __int32 *); // rax
  void *v23; // rdx
  struct _ERESOURCE *v24; // rcx
  __int64 result; // rax
  unsigned int i; // ebx
  ULONG v27; // eax
  ULONG v28; // r12d
  ULONG Length; // [rsp+38h] [rbp-50h]
  struct _ERESOURCE *v30; // [rsp+40h] [rbp-48h]
  IRP *v31; // [rsp+48h] [rbp-40h]
  UCHAR MajorFunction; // [rsp+90h] [rbp+8h]
  int v34; // [rsp+A0h] [rbp+18h]

  v7 = a2;
  v9 = (_DWORD *)(a1 + 68);
  if ( *(struct _KTHREAD **)(a2 + 880) == KeGetCurrentThread() )
    *v9 |= 0x1000u;
  v10 = *v9 & 2;
  v34 = v10;
  v11 = *(_DWORD **)(a1 + 80);
  *((_QWORD *)v11 + 1) = a3;
  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  MajorFunction = CurrentStackLocation->MajorFunction;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v13 = (struct _ERESOURCE *)((char *)a3->MdlAddress->StartVa + a3->MdlAddress->ByteOffset);
  v30 = v13;
  v14 = 0;
  v15 = a5;
  v16 = v10;
  while ( v14 < a4 )
  {
    v17 = 32LL * v14;
    *(_QWORD *)(v17 + v15 + 24) = 0;
    Irp = IoMakeAssociatedIrp(a3, *(_BYTE *)(*(_QWORD *)(v7 + 136) + 76LL) + 1);
    v31 = Irp;
    if ( !Irp )
    {
      *(_DWORD *)(a1 + 72) = -1073741670;
      ExRaiseStatus(-1073741670);
    }
    *(_QWORD *)(v17 + a5 + 24) = Irp;
    Mdl = IoAllocateMdl((char *)v30 + *(unsigned int *)(v17 + a5 + 12), *(_DWORD *)(v17 + a5 + 16), 0, 0, Irp);
    if ( !Mdl )
    {
      *(_DWORD *)(a1 + 72) = -1073741670;
      ExRaiseStatus(-1073741670);
    }
    IoBuildPartialMdl(a3->MdlAddress, Mdl, (char *)v30 + *(unsigned int *)(v17 + a5 + 12), *(_DWORD *)(v17 + a5 + 16));
    --v31->CurrentLocation;
    v20 = --v31->Tail.Overlay.CurrentStackLocation;
    v20->MajorFunction = *(_BYTE *)(a1 + 64);
    v15 = a5;
    v20->Parameters.Read.Length = *(_DWORD *)(v17 + a5 + 16);
    v20->Parameters.Read.ByteOffset.QuadPart = *(unsigned int *)(v17 + a5 + 8);
    v21 = v31->Tail.Overlay.CurrentStackLocation;
    v22 = (__int64 (__fastcall *)(__int64, __int64, volatile signed __int32 *))&FatMultiSyncCompletionRoutine;
    v16 = v34;
    if ( !v34 )
      v22 = FatMultiAsyncCompletionRoutine;
    v21[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)v22;
    v21[-1].Context = v11;
    v21[-1].Control = 0;
    v21[-1].Control = 64;
    v21[-1].Control = -64;
    v21[-1].Control = -32;
    v13 = (struct _ERESOURCE *)v31->Tail.Overlay.CurrentStackLocation;
    LOBYTE(v13[-1].SharedWaiters) = *(_BYTE *)(a1 + 64);
    LODWORD(v13[-1].ExclusiveWaiters) = *(_DWORD *)(v17 + a5 + 16);
    *(_QWORD *)&v13[-1].OwnerEntry.0 = *(_QWORD *)(v17 + a5);
    if ( (*v9 & 4) != 0 )
      BYTE2(v13[-1].SharedWaiters) |= 4u;
    if ( (*v9 & 0x1000) != 0 )
      BYTE2(v13[-1].SharedWaiters) |= 2u;
    ++v14;
    v7 = a2;
  }
  v11[1] = a4;
  a3->AssociatedIrp.IrpCount = a4;
  if ( v16 )
  {
    a3->AssociatedIrp.IrpCount = a4 + 1;
  }
  else
  {
    v23 = (void *)*((_QWORD *)v11 + 5);
    if ( ((unsigned __int8)v23 & 3) != 0 )
    {
      v24 = (struct _ERESOURCE *)*((_QWORD *)v11 + 3);
      if ( v24 )
        ExSetResourceOwnerPointer(v24, v23);
      v13 = (struct _ERESOURCE *)*((_QWORD *)v11 + 4);
      if ( v13 )
        ExSetResourceOwnerPointer(v13, *((PVOID *)v11 + 5));
    }
  }
  result = (unsigned int)*v9;
  *v11 = result;
  for ( i = 0; i < a4; ++i )
    result = FatLowLevelReadWrite(v13, *(_QWORD *)(a2 + 136), *(_QWORD *)(32LL * i + a5 + 24));
  if ( FatDiskAccountingEnabled )
  {
    v27 = 0;
    v28 = Length;
    if ( MajorFunction == 4 )
    {
      v27 = Length;
      v28 = 0;
    }
    return FsRtlUpdateDiskCounters(v28, v27);
  }
  return result;
}

```

## disassembly

```asm
0x14002d610  mov     [rsp+arg_8], rdx
0x14002d615  push    rbx
0x14002d616  push    rsi
0x14002d617  push    rdi
0x14002d618  push    r12
0x14002d61a  push    r13
0x14002d61c  push    r14
0x14002d61e  push    r15
0x14002d620  sub     rsp, 50h
0x14002d624  mov     r13d, r9d
0x14002d627  mov     rsi, r8
0x14002d62a  mov     r10, rdx
0x14002d62d  mov     r15, rcx
0x14002d630  mov     [rsp+88h+var_54], 0
0x14002d638  mov     [rsp+88h+var_58], 1
0x14002d63d  lea     rbx, [rcx+44h]
0x14002d641  mov     rax, gs:188h
0x14002d64a  cmp     [rdx+370h], rax
0x14002d651  jnz     short loc_14002D657
0x14002d653  bts     dword ptr [rbx], 0Ch
0x14002d657  mov     r8d, [rbx]
0x14002d65a  and     r8d, 2
0x14002d65e  mov     [rsp+88h+arg_10], r8d
0x14002d666  mov     rdi, [rcx+50h]
0x14002d66a  mov     [rdi+8], rsi
0x14002d66e  mov     rax, [rsi+0B8h]
0x14002d675  mov     r12b, [rax]
0x14002d678  mov     [rsp+88h+arg_0], r12b
0x14002d680  mov     ecx, [rax+8]
0x14002d683  mov     [rsp+88h+var_50], ecx
0x14002d687  mov     rax, [rsi+8]
0x14002d68b  mov     ecx, [rax+2Ch]
0x14002d68e  add     rcx, [rax+20h]
0x14002d692  mov     [rsp+88h+var_48], rcx
0x14002d697  xor     r14d, r14d
0x14002d69a  mov     [rsp+88h+var_54], r14d
0x14002d69f  mov     rdx, [rsp+88h+arg_20]
0x14002d6a7  mov     r9d, r8d
0x14002d6aa  cmp     r14d, r13d
0x14002d6ad  jnb     loc_14002D833
0x14002d6b3  mov     r12d, r14d
0x14002d6b6  shl     r12, 5
0x14002d6ba  mov     qword ptr [r12+rdx+18h], 0
0x14002d6c3  mov     rax, [r10+88h]
0x14002d6ca  mov     dl, [rax+4Ch]
0x14002d6cd  inc     dl; StackSize
0x14002d6cf  mov     rcx, rsi; Irp
0x14002d6d2  call    cs:__imp_IoMakeAssociatedIrp
0x14002d6d9  nop     dword ptr [rax+rax+00h]
0x14002d6de  mov     rdx, rax
0x14002d6e1  mov     [rsp+88h+var_40], rax
0x14002d6e6  test    rax, rax
0x14002d6e9  jnz     short loc_14002D700
0x14002d6eb  mov     ecx, 0C000009Ah; Status
0x14002d6f0  mov     [r15+48h], ecx
0x14002d6f4  call    cs:__imp_ExRaiseStatus
0x14002d700  mov     rax, [rsp+88h+arg_20]
0x14002d708  mov     [r12+rax+18h], rdx
0x14002d70d  mov     ecx, [r12+rax+0Ch]
0x14002d712  add     rcx, [rsp+88h+var_48]; VirtualAddress
0x14002d717  mov     [rsp+88h+Irp], rdx; Irp
0x14002d71c  xor     r9d, r9d; ChargeQuota
0x14002d71f  xor     r8d, r8d; SecondaryBuffer
0x14002d722  mov     edx, [r12+rax+10h]; Length
0x14002d727  call    cs:__imp_IoAllocateMdl
0x14002d72e  nop     dword ptr [rax+rax+00h]
0x14002d733  mov     rdx, rax; TargetMdl
0x14002d736  test    rax, rax
0x14002d739  jnz     short loc_14002D750
0x14002d73b  mov     ecx, 0C000009Ah; Status
0x14002d740  mov     [r15+48h], ecx
0x14002d744  call    cs:__imp_ExRaiseStatus
0x14002d750  mov     rax, [rsp+88h+arg_20]
0x14002d758  mov     r8d, [r12+rax+0Ch]
0x14002d75d  add     r8, [rsp+88h+var_48]; VirtualAddress
0x14002d762  mov     r9d, [r12+rax+10h]; Length
0x14002d767  mov     rcx, [rsi+8]; SourceMdl
0x14002d76b  call    cs:__imp_IoBuildPartialMdl
0x14002d772  nop     dword ptr [rax+rax+00h]
0x14002d777  mov     r8, [rsp+88h+var_40]
0x14002d77c  dec     byte ptr [r8+43h]
0x14002d780  add     qword ptr [r8+0B8h], 0FFFFFFFFFFFFFFB8h
0x14002d788  mov     rcx, [r8+0B8h]
0x14002d78f  mov     al, [r15+40h]
0x14002d793  mov     [rcx], al
0x14002d795  mov     rdx, [rsp+88h+arg_20]
0x14002d79d  mov     eax, [r12+rdx+10h]
0x14002d7a2  mov     [rcx+8], eax
0x14002d7a5  mov     eax, [r12+rdx+8]
0x14002d7aa  mov     [rcx+18h], rax
0x14002d7ae  mov     rcx, [r8+0B8h]
0x14002d7b5  lea     rax, FatMultiSyncCompletionRoutine
0x14002d7bc  lea     r10, FatMultiAsyncCompletionRoutine
0x14002d7c3  mov     r9d, [rsp+88h+arg_10]
0x14002d7cb  test    r9d, r9d
0x14002d7ce  cmovz   rax, r10
0x14002d7d2  mov     [rcx-10h], rax
0x14002d7d6  mov     [rcx-8], rdi
0x14002d7da  mov     byte ptr [rcx-45h], 0
0x14002d7de  mov     byte ptr [rcx-45h], 40h ; '@'
0x14002d7e2  mov     byte ptr [rcx-45h], 0C0h
0x14002d7e6  mov     byte ptr [rcx-45h], 0E0h
0x14002d7ea  mov     rcx, [r8+0B8h]
0x14002d7f1  mov     al, [r15+40h]
0x14002d7f5  mov     [rcx-48h], al
0x14002d7f8  mov     eax, [r12+rdx+10h]
0x14002d7fd  mov     [rcx-40h], eax
0x14002d800  mov     rax, [r12+rdx]
0x14002d804  mov     [rcx-30h], rax
0x14002d808  mov     eax, [rbx]
0x14002d80a  test    al, 4
0x14002d80c  jz      short loc_14002D812
0x14002d80e  or      byte ptr [rcx-46h], 4
0x14002d812  test    dword ptr [rbx], 1000h
0x14002d818  jz      short loc_14002D81E
0x14002d81a  or      byte ptr [rcx-46h], 2
0x14002d81e  inc     r14d
0x14002d821  mov     [rsp+88h+var_54], r14d
0x14002d826  mov     r10, [rsp+88h+arg_8]
0x14002d82e  jmp     loc_14002D6AA
0x14002d833  mov     [rsp+88h+var_58], 0
0x14002d838  mov     [rdi+4], r13d
0x14002d83c  mov     [rsi+18h], r13d
0x14002d840  test    r9d, r9d
0x14002d843  jz      short loc_14002D84E
0x14002d845  lea     eax, [r13+1]
0x14002d849  mov     [rsi+18h], eax
0x14002d84c  jmp     short loc_14002D885
0x14002d84e  mov     rdx, [rdi+28h]; OwnerPointer
0x14002d852  test    dl, 3
0x14002d855  jz      short loc_14002D885
0x14002d857  mov     rcx, [rdi+18h]; Resource
0x14002d85b  test    rcx, rcx
0x14002d85e  jz      short loc_14002D86C
0x14002d860  call    cs:__imp_ExSetResourceOwnerPointer
0x14002d867  nop     dword ptr [rax+rax+00h]
0x14002d86c  mov     rcx, [rdi+20h]; Resource
0x14002d870  test    rcx, rcx
0x14002d873  jz      short loc_14002D885
0x14002d875  mov     rdx, [rdi+28h]; OwnerPointer
0x14002d879  call    cs:__imp_ExSetResourceOwnerPointer
0x14002d880  nop     dword ptr [rax+rax+00h]
0x14002d885  mov     eax, [rbx]
0x14002d887  mov     [rdi], eax
0x14002d889  xor     ebx, ebx
0x14002d88b  mov     [rsp+88h+var_54], ebx
0x14002d88f  mov     rdi, [rsp+88h+arg_20]
0x14002d897  mov     rsi, [rsp+88h+arg_8]
0x14002d89f  cmp     ebx, r13d
0x14002d8a2  jnb     short loc_14002D8C4
0x14002d8a4  mov     r8d, ebx
0x14002d8a7  shl     r8, 5
0x14002d8ab  mov     r8, [r8+rdi+18h]
0x14002d8b0  mov     rdx, [rsi+88h]
0x14002d8b7  call    FatLowLevelReadWrite
0x14002d8bc  inc     ebx
0x14002d8be  mov     [rsp+88h+var_54], ebx
0x14002d8c2  jmp     short loc_14002D89F
0x14002d8c4  cmp     cs:FatDiskAccountingEnabled, 0
0x14002d8cb  jz      short loc_14002D900
0x14002d8cd  xor     eax, eax
0x14002d8cf  cmp     [rsp+88h+arg_0], 4
0x14002d8d7  mov     r12d, [rsp+88h+var_50]
0x14002d8dc  cmovz   eax, r12d
0x14002d8e0  mov     edx, eax
0x14002d8e2  xor     eax, eax
0x14002d8e4  cmp     [rsp+88h+arg_0], 4
0x14002d8ec  cmovz   r12d, eax
0x14002d8f0  mov     ecx, r12d
0x14002d8f3  call    cs:__imp_FsRtlUpdateDiskCounters
0x14002d8fa  nop     dword ptr [rax+rax+00h]
0x14002d8ff  nop
0x14002d900  add     rsp, 50h
0x14002d904  pop     r15
0x14002d906  pop     r14
0x14002d908  pop     r13
0x14002d90a  pop     r12
0x14002d90c  pop     rdi
0x14002d90d  pop     rsi
0x14002d90e  pop     rbx
0x14002d90f  retn
0x14005cca7  push    rbx
0x14005cca9  push    rbp
0x14005ccaa  push    rsi
0x14005ccab  push    rdi
0x14005ccac  sub     rsp, 38h
0x14005ccb0  mov     rbp, rdx
0x14005ccb3  test    cl, cl
0x14005ccb5  jz      short loc_14005CD2A
0x14005ccb7  cmp     byte ptr [rbp+30h], 0
0x14005ccbb  jnz     short loc_14005CCE2
0x14005ccbd  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x14005ccc6  xor     r9d, r9d; BugCheckParameter3
0x14005ccc9  xor     r8d, r8d; BugCheckParameter2
0x14005cccc  mov     edx, 808D2h; BugCheckParameter1
0x14005ccd1  lea     ecx, [r9+23h]; BugCheckCode
0x14005ccd5  call    cs:__imp_KeBugCheckEx
0x14005cce2  xor     ebx, ebx
0x14005cce4  mov     rsi, [rbp+0B0h]
0x14005cceb  mov     eax, ebx
0x14005cced  shl     rax, 5
0x14005ccf1  mov     rdi, [rax+rsi+18h]
0x14005ccf6  test    rdi, rdi
0x14005ccf9  jz      short loc_14005CD23
0x14005ccfb  cmp     qword ptr [rdi+8], 0
0x14005cd00  jz      short loc_14005CD13
0x14005cd02  mov     rcx, [rdi+8]; Mdl
0x14005cd06  call    cs:__imp_IoFreeMdl
0x14005cd0d  nop     dword ptr [rax+rax+00h]
0x14005cd12  nop
0x14005cd13  mov     rcx, rdi; Irp
0x14005cd16  call    cs:__imp_IoFreeIrp
0x14005cd1d  nop     dword ptr [rax+rax+00h]
0x14005cd22  nop
0x14005cd23  inc     ebx
0x14005cd25  cmp     ebx, [rbp+34h]
0x14005cd28  jbe     short loc_14005CCEB
0x14005cd2a  add     rsp, 38h
0x14005cd2e  pop     rdi
0x14005cd2f  pop     rsi
0x14005cd30  pop     rbp
0x14005cd31  pop     rbx
0x14005cd32  retn
```
