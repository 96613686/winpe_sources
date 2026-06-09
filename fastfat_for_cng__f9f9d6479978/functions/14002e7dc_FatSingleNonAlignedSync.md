# FatSingleNonAlignedSync

- ea: `0x14002e7dc`
- end: `0x14002e955`
- name: `FatSingleNonAlignedSync`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002e0cc`

## callees

- `0x140001ef8`
- `0x14002e7dc`
- `0x14002e95c`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002e905`
- `ntoskrnl!IoFreeMdl` at `0x14005ce16`
- `ntoskrnl!IoFreeMdl` at `0x14005ce55`
- `ntoskrnl!IoFreeMdl` at `0x14002e905`
- `ntoskrnl!IoFreeMdl` at `0x14005ce16`
- `ntoskrnl!IoFreeMdl` at `0x14005ce55`
- `ntoskrnl!IoAllocateMdl` at `0x14002e832`
- `ntoskrnl!IoAllocateMdl` at `0x14002e832`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x14002e930`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x14002e930`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002e86d`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002e86d`
- `ntoskrnl!MmUnlockPages` at `0x14002e8f6`
- `ntoskrnl!MmUnlockPages` at `0x14005ce45`
- `ntoskrnl!MmUnlockPages` at `0x14002e8f6`
- `ntoskrnl!MmUnlockPages` at `0x14005ce45`
- `ntoskrnl!ExRaiseStatus` at `0x14002e857`
- `ntoskrnl!ExRaiseStatus` at `0x14002e857`

## pseudocode

```c
void __fastcall FatSingleNonAlignedSync(__int64 a1, __int64 a2, void *a3, LARGE_INTEGER a4, ULONG Length, IRP *a6)
{
  struct _MDL *MdlAddress; // r12
  struct _MDL *Mdl; // rax
  struct _MDL *v10; // rsi
  void *v11; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v13; // rcx
  UCHAR v14; // r14
  __int64 v15; // rdx
  ULONG v16; // eax

  MdlAddress = a6->MdlAddress;
  a6->MdlAddress = 0;
  Mdl = IoAllocateMdl(a3, Length, 0, 0, a6);
  v10 = Mdl;
  if ( !Mdl )
  {
    a6->MdlAddress = MdlAddress;
    *(_DWORD *)(a1 + 72) = -1073741670;
    ExRaiseStatus(-1073741670);
  }
  MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
  v11 = *(void **)(a1 + 80);
  CurrentStackLocation = a6->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)FatSingleSyncCompletionRoutine;
  CurrentStackLocation[-1].Context = v11;
  CurrentStackLocation[-1].Control = -32;
  v13 = a6->Tail.Overlay.CurrentStackLocation;
  v14 = *(_BYTE *)(a1 + 64);
  v13[-1].MajorFunction = v14;
  v13[-1].Parameters.Read.Length = Length;
  v13[-1].Parameters.Read.ByteOffset = a4;
  if ( *(struct _KTHREAD **)(a2 + 880) == KeGetCurrentThread() )
    *(_DWORD *)(a1 + 68) |= 0x1000u;
  if ( (*(_DWORD *)(a1 + 68) & 0x1000) != 0 )
    v13[-1].Flags |= 2u;
  FatLowLevelReadWrite(v13, *(_QWORD *)(a2 + 136), a6);
  FatWaitSync(a1);
  MmUnlockPages(v10);
  IoFreeMdl(v10);
  a6->MdlAddress = MdlAddress;
  if ( FatDiskAccountingEnabled )
  {
    v15 = Length;
    v16 = 0;
    if ( v14 != 4 )
    {
      v15 = 0;
      v16 = Length;
    }
    FsRtlUpdateDiskCounters(v16, v15);
  }
}

```

## disassembly

```asm
0x14002e7dc  mov     r11, rsp
0x14002e7df  mov     [r11+8], rbx
0x14002e7e3  mov     [r11+10h], rsi
0x14002e7e7  mov     [r11+20h], r9
0x14002e7eb  push    rdi
0x14002e7ec  push    r12
0x14002e7ee  push    r13
0x14002e7f0  push    r14
0x14002e7f2  push    r15
0x14002e7f4  sub     rsp, 40h
0x14002e7f8  mov     rax, r8
0x14002e7fb  mov     r13, rdx
0x14002e7fe  mov     rbx, rcx
0x14002e801  mov     rdi, [rsp+68h+arg_28]
0x14002e809  mov     r12, [rdi+8]
0x14002e80d  mov     [rsp+68h+var_30], r12
0x14002e812  mov     qword ptr [rdi+8], 0
0x14002e81a  mov     [r11-48h], rdi
0x14002e81e  xor     r9d, r9d; ChargeQuota
0x14002e821  xor     r8d, r8d; SecondaryBuffer
0x14002e824  mov     r15d, [rsp+68h+Length]
0x14002e82c  mov     edx, r15d; Length
0x14002e82f  mov     rcx, rax; VirtualAddress
0x14002e832  call    cs:__imp_IoAllocateMdl
0x14002e839  nop     dword ptr [rax+rax+00h]
0x14002e83e  mov     rsi, rax
0x14002e841  mov     [rsp+68h+var_38], rax
0x14002e846  test    rax, rax
0x14002e849  jnz     short loc_14002E864
0x14002e84b  mov     [rdi+8], r12
0x14002e84f  mov     ecx, 0C000009Ah; Status
0x14002e854  mov     [rbx+48h], ecx
0x14002e857  call    cs:__imp_ExRaiseStatus
0x14002e864  xor     edx, edx; AccessMode
0x14002e866  lea     r8d, [rdx+1]; Operation
0x14002e86a  mov     rcx, rsi; MemoryDescriptorList
0x14002e86d  call    cs:__imp_MmProbeAndLockPages
0x14002e874  nop     dword ptr [rax+rax+00h]
0x14002e879  nop
0x14002e87a  mov     rcx, [rbx+50h]
0x14002e87e  mov     rax, [rdi+0B8h]
0x14002e885  lea     rdx, FatSingleSyncCompletionRoutine
0x14002e88c  mov     [rax-10h], rdx
0x14002e890  mov     [rax-8], rcx
0x14002e894  mov     byte ptr [rax-45h], 0E0h
0x14002e898  mov     rcx, [rdi+0B8h]
0x14002e89f  mov     r14b, [rbx+40h]
0x14002e8a3  mov     [rcx-48h], r14b
0x14002e8a7  mov     [rcx-40h], r15d
0x14002e8ab  mov     rax, [rsp+68h+arg_18]
0x14002e8b3  mov     [rcx-30h], rax
0x14002e8b7  mov     rax, gs:188h
0x14002e8c0  cmp     [r13+370h], rax
0x14002e8c7  jnz     short loc_14002E8CE
0x14002e8c9  bts     dword ptr [rbx+44h], 0Ch
0x14002e8ce  test    dword ptr [rbx+44h], 1000h
0x14002e8d5  jz      short loc_14002E8DB
0x14002e8d7  or      byte ptr [rcx-46h], 2
0x14002e8db  mov     r8, rdi
0x14002e8de  mov     rdx, [r13+88h]
0x14002e8e5  call    FatLowLevelReadWrite
0x14002e8ea  mov     rcx, rbx
0x14002e8ed  call    FatWaitSync
0x14002e8f2  nop
0x14002e8f3  mov     rcx, rsi; MemoryDescriptorList
0x14002e8f6  call    cs:__imp_MmUnlockPages
0x14002e8fd  nop     dword ptr [rax+rax+00h]
0x14002e902  mov     rcx, rsi; Mdl
0x14002e905  call    cs:__imp_IoFreeMdl
0x14002e90c  nop     dword ptr [rax+rax+00h]
0x14002e911  mov     [rdi+8], r12
0x14002e915  cmp     cs:FatDiskAccountingEnabled, 0
0x14002e91c  jz      short loc_14002E93C
0x14002e91e  mov     edx, r15d
0x14002e921  xor     eax, eax
0x14002e923  cmp     r14b, 4
0x14002e927  cmovnz  edx, eax
0x14002e92a  cmovnz  eax, r15d
0x14002e92e  mov     ecx, eax
0x14002e930  call    cs:__imp_FsRtlUpdateDiskCounters
0x14002e937  nop     dword ptr [rax+rax+00h]
0x14002e93c  mov     rbx, [rsp+68h+arg_0]
0x14002e941  mov     rsi, [rsp+68h+arg_8]
0x14002e946  add     rsp, 40h
0x14002e94a  pop     r15
0x14002e94c  pop     r14
0x14002e94e  pop     r13
0x14002e950  pop     r12
0x14002e952  pop     rdi
0x14002e953  retn
0x14005ce05  push    rbp
0x14005ce07  sub     rsp, 30h
0x14005ce0b  mov     rbp, rdx
0x14005ce0e  test    cl, cl
0x14005ce10  jz      short loc_14005CE31
0x14005ce12  mov     rcx, [rbp+30h]; Mdl
0x14005ce16  call    cs:__imp_IoFreeMdl
0x14005ce1d  nop     dword ptr [rax+rax+00h]
0x14005ce22  mov     rcx, [rbp+98h]
0x14005ce29  mov     rax, [rbp+38h]
0x14005ce2d  mov     [rcx+8], rax
0x14005ce31  add     rsp, 30h
0x14005ce35  pop     rbp
0x14005ce36  retn
0x14005ce38  push    rbp
0x14005ce3a  sub     rsp, 30h
0x14005ce3e  mov     rbp, rdx
0x14005ce41  mov     rcx, [rbp+30h]; MemoryDescriptorList
0x14005ce45  call    cs:__imp_MmUnlockPages
0x14005ce4c  nop     dword ptr [rax+rax+00h]
0x14005ce51  mov     rcx, [rbp+30h]; Mdl
0x14005ce55  call    cs:__imp_IoFreeMdl
0x14005ce5c  nop     dword ptr [rax+rax+00h]
0x14005ce61  mov     rcx, [rbp+98h]
0x14005ce68  mov     rax, [rbp+38h]
0x14005ce6c  mov     [rcx+8], rax
0x14005ce70  add     rsp, 30h
0x14005ce74  pop     rbp
0x14005ce75  retn
```
