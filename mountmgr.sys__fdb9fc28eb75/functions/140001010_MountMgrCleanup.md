# MountMgrCleanup

- ea: `0x140001010`
- end: `0x1400010e9`
- name: `MountMgrCleanup`
- size: `217`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001010`
- `0x140001b80`

## import_xrefs

- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140001041`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400010d8`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140001041`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400010d8`
- `ntoskrnl!IofCompleteRequest` at `0x14000107d`
- `ntoskrnl!IofCompleteRequest` at `0x14000107d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001064`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001064`

## pseudocode

```c
__int64 __fastcall MountMgrCleanup(__int64 a1, IRP *a2)
{
  __int64 v3; // rdi
  PFILE_OBJECT FileObject; // rbp
  _QWORD *v6; // rdi
  _QWORD *v7; // rdx
  KIRQL Irql; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  Irql = 0;
  IoAcquireCancelSpinLock(&Irql);
  v6 = (_QWORD *)(v3 + 152);
  while ( 1 )
  {
    v7 = (_QWORD *)*v6;
    if ( (_QWORD *)*v6 == v6 )
      break;
    while ( *(PFILE_OBJECT *)(v7[2] + 48LL) != FileObject )
    {
      v7 = (_QWORD *)*v7;
      if ( v7 == v6 )
        goto LABEL_3;
    }
    *((_BYTE *)v7 - 100) = 1;
    *((_BYTE *)v7 - 99) = Irql;
    *(v7 - 8) = 0;
    MountMgrCancel(a1, (IRP *)(v7 - 21));
    IoAcquireCancelSpinLock(&Irql);
  }
LABEL_3:
  IoReleaseCancelSpinLock(Irql);
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140001010  mov     [rsp+arg_8], rbx
0x140001015  mov     [rsp+arg_10], rbp
0x14000101a  push    rsi
0x14000101b  push    rdi
0x14000101c  push    r14
0x14000101e  sub     rsp, 20h
0x140001022  mov     rax, [rdx+0B8h]
0x140001029  mov     rsi, rcx
0x14000102c  mov     rdi, [rcx+40h]
0x140001030  mov     rbx, rdx
0x140001033  lea     rcx, [rsp+38h+Irql]; Irql
0x140001038  mov     rbp, [rax+30h]
0x14000103c  mov     [rsp+38h+Irql], 0
0x140001041  call    cs:__imp_IoAcquireCancelSpinLock
0x140001048  nop     dword ptr [rax+rax+00h]
0x14000104d  add     rdi, 98h
0x140001054  xor     r14d, r14d
0x140001057  mov     rdx, [rdi]
0x14000105a  cmp     rdx, rdi
0x14000105d  jnz     short loc_1400010A0
0x14000105f  movzx   ecx, [rsp+38h+Irql]; Irql
0x140001064  call    cs:__imp_IoReleaseCancelSpinLock
0x14000106b  nop     dword ptr [rax+rax+00h]
0x140001070  xor     edx, edx; PriorityBoost
0x140001072  mov     [rbx+30h], r14d
0x140001076  mov     rcx, rbx; Irp
0x140001079  mov     [rbx+38h], r14
0x14000107d  call    cs:__imp_IofCompleteRequest
0x140001084  nop     dword ptr [rax+rax+00h]
0x140001089  mov     rbx, [rsp+38h+arg_8]
0x14000108e  xor     eax, eax
0x140001090  mov     rbp, [rsp+38h+arg_10]
0x140001095  add     rsp, 20h
0x140001099  pop     r14
0x14000109b  pop     rdi
0x14000109c  pop     rsi
0x14000109d  retn
0x1400010a0  mov     rax, [rdx+10h]
0x1400010a4  cmp     [rax+30h], rbp
0x1400010a8  jz      short loc_1400010B4
0x1400010aa  mov     rdx, [rdx]
0x1400010ad  cmp     rdx, rdi
0x1400010b0  jnz     short loc_1400010A0
0x1400010b2  jmp     short loc_14000105F
0x1400010b4  mov     byte ptr [rdx-64h], 1
0x1400010b8  mov     rcx, rsi
0x1400010bb  movzx   eax, [rsp+38h+Irql]
0x1400010c0  mov     [rdx-63h], al
0x1400010c3  mov     [rdx-40h], r14
0x1400010c7  add     rdx, 0FFFFFFFFFFFFFF58h
0x1400010ce  call    MountMgrCancel
0x1400010d3  lea     rcx, [rsp+38h+Irql]; Irql
0x1400010d8  call    cs:__imp_IoAcquireCancelSpinLock
0x1400010df  nop     dword ptr [rax+rax+00h]
0x1400010e4  jmp     loc_140001057
```
