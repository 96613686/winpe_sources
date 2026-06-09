# CdpCreateMdlChain

- ea: `0x14000a260`
- end: `0x14000a383`
- name: `CdpCreateMdlChain`
- size: `291`
- prototype: `__int64 __fastcall(int, int, int, int, LOCK_OPERATION Operation)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140009760`
- `0x140009af0`

## callees

- `0x14000a260`
- `0x14000bd30`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14000a2e5`
- `ntoskrnl!IoAllocateMdl` at `0x14000a2e5`
- `ntoskrnl!IoFreeMdl` at `0x14000a322`
- `ntoskrnl!IoFreeMdl` at `0x14000a322`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14000a2bb`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14000a2bb`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000a2ac`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000a2ac`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000a30d`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000a30d`

## pseudocode

```c
__int64 __fastcall CdpCreateMdlChain(
        PMDL *a1,
        __int64 a2,
        unsigned int a3,
        KPROCESSOR_MODE a4,
        LOCK_OPERATION Operation)
{
  PMDL *p_Next; // r15
  unsigned int i; // ebx
  ULONG *v11; // rdi
  __int64 CurrentProcess; // rax
  void *v13; // rcx
  struct _MDL *Mdl; // rax
  struct _MDL *v15; // rdi
  PMDL v17[9]; // [rsp+30h] [rbp-48h] BYREF

  v17[0] = 0;
  p_Next = v17;
  for ( i = 0; ; ++i )
  {
    if ( i >= a3 )
    {
      *a1 = v17[0];
      return 0;
    }
    v11 = (ULONG *)(a2 + 16LL * i);
    if ( *v11 )
      break;
LABEL_9:
    ;
  }
  if ( a4 && (CurrentProcess = PsGetCurrentProcess(), PsGetProcessWow64Process(CurrentProcess)) )
    v13 = (void *)v11[2];
  else
    v13 = (void *)*((_QWORD *)v11 + 1);
  Mdl = IoAllocateMdl(v13, *v11, 0, 1u, 0);
  v15 = Mdl;
  v17[1] = Mdl;
  if ( Mdl )
  {
    MmProbeAndLockPages(Mdl, a4, Operation);
    *p_Next = v15;
    p_Next = &v15->Next;
    goto LABEL_9;
  }
  CdFreeMdlChain(v17[0]);
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000a260  push    rbx
0x14000a262  push    rsi
0x14000a263  push    rdi
0x14000a264  push    r12
0x14000a266  push    r13
0x14000a268  push    r14
0x14000a26a  push    r15
0x14000a26c  sub     rsp, 40h
0x14000a270  movzx   r14d, r9b
0x14000a274  mov     esi, r8d
0x14000a277  mov     r13, rdx
0x14000a27a  mov     r12, rcx
0x14000a27d  mov     [rsp+78h+var_48], 0
0x14000a286  lea     r15, [rsp+78h+var_48]
0x14000a28b  xor     ebx, ebx
0x14000a28d  cmp     ebx, esi
0x14000a28f  jnb     loc_14000A33D
0x14000a295  mov     edi, ebx
0x14000a297  shl     rdi, 4
0x14000a29b  add     rdi, r13
0x14000a29e  cmp     dword ptr [rdi], 0
0x14000a2a1  jz      loc_14000A336
0x14000a2a7  test    r14b, r14b
0x14000a2aa  jz      short loc_14000A2D0
0x14000a2ac  call    cs:__imp_PsGetCurrentProcess
0x14000a2b3  nop     dword ptr [rax+rax+00h]
0x14000a2b8  mov     rcx, rax
0x14000a2bb  call    cs:__imp_PsGetProcessWow64Process
0x14000a2c2  nop     dword ptr [rax+rax+00h]
0x14000a2c7  test    rax, rax
0x14000a2ca  jnz     loc_14000A359
0x14000a2d0  mov     rcx, [rdi+8]; VirtualAddress
0x14000a2d4  mov     [rsp+78h+Irp], 0; Irp
0x14000a2dd  mov     r9b, 1; ChargeQuota
0x14000a2e0  xor     r8d, r8d; SecondaryBuffer
0x14000a2e3  mov     edx, [rdi]; Length
0x14000a2e5  call    cs:__imp_IoAllocateMdl
0x14000a2ec  nop     dword ptr [rax+rax+00h]
0x14000a2f1  mov     rdi, rax
0x14000a2f4  mov     [rsp+78h+Mdl], rax
0x14000a2f9  test    rax, rax
0x14000a2fc  jz      short loc_14000A361
0x14000a2fe  mov     r8d, [rsp+78h+Operation]; Operation
0x14000a306  movzx   edx, r14b; AccessMode
0x14000a30a  mov     rcx, rax; MemoryDescriptorList
0x14000a30d  call    cs:__imp_MmProbeAndLockPages
0x14000a314  nop     dword ptr [rax+rax+00h]
0x14000a319  jmp     short loc_14000A330
0x14000a31b  mov     ebx, eax
0x14000a31d  mov     rcx, [rsp+78h+Mdl]; Mdl
0x14000a322  call    cs:__imp_IoFreeMdl
0x14000a329  nop     dword ptr [rax+rax+00h]
0x14000a32e  jmp     short loc_14000A366
0x14000a330  mov     [r15], rdi
0x14000a333  mov     r15, rdi
0x14000a336  inc     ebx
0x14000a338  jmp     loc_14000A28D
0x14000a33d  mov     rax, [rsp+78h+var_48]
0x14000a342  mov     [r12], rax
0x14000a346  xor     eax, eax
0x14000a348  add     rsp, 40h
0x14000a34c  pop     r15
0x14000a34e  pop     r14
0x14000a350  pop     r13
0x14000a352  pop     r12
0x14000a354  pop     rdi
0x14000a355  pop     rsi
0x14000a356  pop     rbx
0x14000a357  retn
0x14000a359  mov     ecx, [rdi+8]
0x14000a35c  jmp     loc_14000A2D4
0x14000a361  mov     ebx, 0C000009Ah
0x14000a366  mov     rcx, [rsp+78h+var_48]; Mdl
0x14000a36b  call    CdFreeMdlChain
0x14000a370  mov     eax, ebx
0x14000a372  add     rsp, 40h
0x14000a376  pop     r15
0x14000a378  pop     r14
0x14000a37a  pop     r13
0x14000a37c  pop     r12
0x14000a37e  pop     rdi
0x14000a37f  pop     rsi
0x14000a380  pop     rbx
0x14000a381  retn
```
