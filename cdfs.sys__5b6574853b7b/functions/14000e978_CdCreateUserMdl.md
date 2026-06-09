# CdCreateUserMdl

- ea: `0x14000e978`
- end: `0x14000ea4e`
- name: `CdCreateUserMdl`
- size: `214`
- prototype: `__int64 __fastcall(__int64, ULONG)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f27c`
- `0x14000f618`
- `0x14001a9a0`
- `0x14001aa78`

## callees

- `0x140001114`
- `0x14000e978`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14000ea06`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14000ea06`
- `ntoskrnl!IoAllocateMdl` at `0x14000e9a2`
- `ntoskrnl!IoAllocateMdl` at `0x14000e9a2`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000e9c8`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000e9c8`
- `ntoskrnl!IoFreeMdl` at `0x14000e9e7`
- `ntoskrnl!IoFreeMdl` at `0x14000e9e7`

## pseudocode

```c
__int64 __fastcall CdCreateUserMdl(__int64 a1, ULONG a2)
{
  unsigned int v3; // ebx
  struct _MDL *Mdl; // rax

  v3 = -1073741670;
  Mdl = IoAllocateMdl(*(PVOID *)(*(_QWORD *)(a1 + 8) + 112LL), a2, 0, 0, *(PIRP *)(a1 + 8));
  if ( Mdl )
  {
    MmProbeAndLockPages(Mdl, *(_BYTE *)(*(_QWORD *)(a1 + 8) + 64LL), IoWriteAccess);
    v3 = 0;
  }
  if ( v3 )
    CdRaiseStatusEx(a1, v3, 0, 655360, 1323);
  return 0;
}

```

## disassembly

```asm
0x14000e978  mov     [rsp+arg_8], rbx
0x14000e97d  mov     [rsp+arg_0], rcx
0x14000e982  push    rdi
0x14000e983  sub     rsp, 40h
0x14000e987  mov     rdi, rcx
0x14000e98a  mov     ebx, 0C000009Ah
0x14000e98f  mov     rcx, [rcx+8]
0x14000e993  mov     [rsp+48h+Irp], rcx; Irp
0x14000e998  xor     r9d, r9d; ChargeQuota
0x14000e99b  xor     r8d, r8d; SecondaryBuffer
0x14000e99e  mov     rcx, [rcx+70h]; VirtualAddress
0x14000e9a2  call    cs:__imp_IoAllocateMdl
0x14000e9a9  nop     dword ptr [rax+rax+00h]
0x14000e9ae  mov     [rsp+48h+Mdl], rax
0x14000e9b3  test    rax, rax
0x14000e9b6  jz      short loc_14000EA20
0x14000e9b8  mov     rdx, [rdi+8]
0x14000e9bc  mov     r8d, 1; Operation
0x14000e9c2  mov     dl, [rdx+40h]; AccessMode
0x14000e9c5  mov     rcx, rax; MemoryDescriptorList
0x14000e9c8  call    cs:__imp_MmProbeAndLockPages
0x14000e9cf  nop     dword ptr [rax+rax+00h]
0x14000e9d4  xor     ebx, ebx
0x14000e9d6  mov     [rsp+48h+var_18], ebx
0x14000e9da  jmp     short loc_14000EA20
0x14000e9dc  mov     ebx, eax
0x14000e9de  mov     [rsp+48h+var_18], eax
0x14000e9e2  mov     rcx, [rsp+48h+Mdl]; Mdl
0x14000e9e7  call    cs:__imp_IoFreeMdl
0x14000e9ee  nop     dword ptr [rax+rax+00h]
0x14000e9f3  mov     rdi, [rsp+48h+arg_0]
0x14000e9f8  mov     rax, [rdi+8]
0x14000e9fc  mov     qword ptr [rax+8], 0
0x14000ea04  mov     ecx, ebx; Exception
0x14000ea06  call    cs:__imp_FsRtlIsNtstatusExpected
0x14000ea0d  nop     dword ptr [rax+rax+00h]
0x14000ea12  mov     ecx, 0C00000E8h
0x14000ea17  test    al, al
0x14000ea19  cmovz   ebx, ecx
0x14000ea1c  mov     [rsp+48h+var_18], ebx
0x14000ea20  test    ebx, ebx
0x14000ea22  jnz     short loc_14000EA32
0x14000ea24  mov     eax, ebx
0x14000ea26  mov     rbx, [rsp+48h+arg_8]
0x14000ea2b  add     rsp, 40h
0x14000ea2f  pop     rdi
0x14000ea30  retn
0x14000ea32  mov     dword ptr [rsp+48h+Irp], 52Bh
0x14000ea3a  mov     r9d, 0A0000h
0x14000ea40  xor     r8d, r8d
0x14000ea43  mov     edx, ebx
0x14000ea45  mov     rcx, rdi
0x14000ea48  call    CdRaiseStatusEx
```
