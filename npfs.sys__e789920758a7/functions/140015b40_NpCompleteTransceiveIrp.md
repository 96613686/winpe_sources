# NpCompleteTransceiveIrp

- ea: `0x140015b40`
- end: `0x140015b7b`
- name: `NpCompleteTransceiveIrp`
- size: `59`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140015b40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015b54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015b54`
- `ntoskrnl!IoFreeIrp` at `0x140015b63`
- `ntoskrnl!IoFreeIrp` at `0x140015b63`

## pseudocode

```c
__int64 __fastcall NpCompleteTransceiveIrp(__int64 a1, IRP *a2)
{
  struct _IRP *MasterIrp; // rcx

  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( MasterIrp )
    ExFreePoolWithTag(MasterIrp, 0);
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140015b40  push    rbx
0x140015b42  sub     rsp, 20h
0x140015b46  mov     rcx, [rdx+18h]; P
0x140015b4a  mov     rbx, rdx
0x140015b4d  test    rcx, rcx
0x140015b50  jz      short loc_140015B60
0x140015b52  xor     edx, edx; Tag
0x140015b54  call    cs:__imp_ExFreePoolWithTag
0x140015b5b  nop     dword ptr [rax+rax+00h]
0x140015b60  mov     rcx, rbx; Irp
0x140015b63  call    cs:__imp_IoFreeIrp
0x140015b6a  nop     dword ptr [rax+rax+00h]
0x140015b6f  mov     eax, 0C0000016h
0x140015b74  add     rsp, 20h
0x140015b78  pop     rbx
0x140015b79  retn
```
