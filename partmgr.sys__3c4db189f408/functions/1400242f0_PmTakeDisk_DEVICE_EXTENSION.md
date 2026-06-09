# PmTakeDisk(_DEVICE_EXTENSION *)

- ea: `0x1400242f0`
- end: `0x1400243aa`
- name: `?PmTakeDisk@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `186`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400087c0`

## callees

- `0x1400242f0`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x140024385`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140024385`
- `ntoskrnl!IoReuseIrp` at `0x140024334`
- `ntoskrnl!IoReuseIrp` at `0x140024334`

## pseudocode

```c
void __fastcall PmTakeDisk(struct _DEVICE_EXTENSION *a1)
{
  _QWORD *v2; // rbx
  _QWORD *i; // rdi
  IRP *v4; // rcx
  __int64 v5; // rax
  IRP *v6; // rdx
  struct _DEVICE_OBJECT *v7; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  v2 = (char *)PmControlObject->DeviceExtension + 72;
  for ( i = (_QWORD *)*v2; i != v2; i = (_QWORD *)*i )
  {
    v4 = (IRP *)*((_QWORD *)a1 + 107);
    v9 = *((_QWORD *)a1 + 3);
    IoReuseIrp(v4, -1073741637);
    v5 = *((_QWORD *)a1 + 107);
    --*(_BYTE *)(v5 + 67);
    *(_QWORD *)(v5 + 184) -= 72LL;
    v6 = (IRP *)*((_QWORD *)a1 + 107);
    v7 = (struct _DEVICE_OBJECT *)i[5];
    CurrentStackLocation = v6->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation->MajorFunction = 15;
    v6->AssociatedIrp.MasterIrp = (struct _IRP *)&v9;
    CurrentStackLocation->Parameters.Read.Length = 0;
    CurrentStackLocation->Parameters.Create.Options = 8;
    CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 7733256;
    IoForwardIrpSynchronously(v7, v6);
  }
}

```

## disassembly

```asm
0x1400242f0  mov     [rsp+arg_0], rbx
0x1400242f5  mov     [rsp+arg_10], rsi
0x1400242fa  push    rdi
0x1400242fb  sub     rsp, 20h
0x1400242ff  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x140024306  mov     rsi, rcx
0x140024309  mov     [rsp+28h+arg_8], 0
0x140024312  mov     rbx, [rax+40h]
0x140024316  add     rbx, 48h ; 'H'
0x14002431a  mov     rdi, [rbx]
0x14002431d  jmp     short loc_140024394
0x14002431f  mov     rax, [rsi+18h]
0x140024323  mov     edx, 0C00000BBh; Iostatus
0x140024328  mov     rcx, [rsi+358h]; Irp
0x14002432f  mov     [rsp+28h+arg_8], rax
0x140024334  call    cs:__imp_IoReuseIrp
0x14002433b  nop     dword ptr [rax+rax+00h]
0x140024340  mov     rax, [rsi+358h]
0x140024347  lea     r8, [rsp+28h+arg_8]
0x14002434c  dec     byte ptr [rax+43h]
0x14002434f  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140024357  mov     rdx, [rsi+358h]; Irp
0x14002435e  mov     rcx, [rdi+28h]; DeviceObject
0x140024362  mov     rax, [rdx+0B8h]
0x140024369  mov     byte ptr [rax], 0Fh
0x14002436c  mov     [rdx+18h], r8
0x140024370  mov     dword ptr [rax+8], 0
0x140024377  mov     dword ptr [rax+10h], 8
0x14002437e  mov     dword ptr [rax+18h], 760008h
0x140024385  call    cs:__imp_IoForwardIrpSynchronously
0x14002438c  nop     dword ptr [rax+rax+00h]
0x140024391  mov     rdi, [rdi]
0x140024394  cmp     rdi, rbx
0x140024397  jnz     short loc_14002431F
0x140024399  mov     rbx, [rsp+28h+arg_0]
0x14002439e  mov     rsi, [rsp+28h+arg_10]
0x1400243a3  add     rsp, 20h
0x1400243a7  pop     rdi
0x1400243a8  retn
```
