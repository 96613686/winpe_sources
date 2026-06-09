# CdpFreeKernelConnectionIrp

- ea: `0x140008a54`
- end: `0x140008a96`
- name: `CdpFreeKernelConnectionIrp`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400083b0`
- `0x140008790`
- `0x140008890`

## callees

- `0x140008a54`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008a74`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008a74`
- `ntoskrnl!IoFreeIrp` at `0x140008a83`
- `ntoskrnl!IoFreeIrp` at `0x140008a83`

## pseudocode

```c
void __fastcall CdpFreeKernelConnectionIrp(IRP **a1)
{
  IRP *v1; // rbx
  struct _IRP *MasterIrp; // rcx

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    MasterIrp = v1->AssociatedIrp.MasterIrp;
    if ( MasterIrp )
      ExFreePoolWithTag(MasterIrp, 0);
    IoFreeIrp(v1);
  }
}

```

## disassembly

```asm
0x140008a54  push    rbx
0x140008a56  sub     rsp, 20h
0x140008a5a  mov     rbx, [rcx]
0x140008a5d  mov     qword ptr [rcx], 0
0x140008a64  test    rbx, rbx
0x140008a67  jz      short loc_140008A8F
0x140008a69  mov     rcx, [rbx+18h]; P
0x140008a6d  test    rcx, rcx
0x140008a70  jz      short loc_140008A80
0x140008a72  xor     edx, edx; Tag
0x140008a74  call    cs:__imp_ExFreePoolWithTag
0x140008a7b  nop     dword ptr [rax+rax+00h]
0x140008a80  mov     rcx, rbx; Irp
0x140008a83  call    cs:__imp_IoFreeIrp
0x140008a8a  nop     dword ptr [rax+rax+00h]
0x140008a8f  add     rsp, 20h
0x140008a93  pop     rbx
0x140008a94  retn
```
