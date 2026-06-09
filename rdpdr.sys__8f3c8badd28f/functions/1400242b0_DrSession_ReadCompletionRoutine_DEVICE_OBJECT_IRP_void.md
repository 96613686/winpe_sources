# DrSession::ReadCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x1400242b0`
- end: `0x140024355`
- name: `?ReadCompletionRoutine@DrSession@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `165`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, DrSession *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001660`
- `0x1400065c0`
- `0x1400242b0`
- `0x140024360`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002433f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002433f`
- `ntoskrnl!IoFreeIrp` at `0x1400242fa`
- `ntoskrnl!IoFreeIrp` at `0x1400242fa`

## pseudocode

```c
__int64 __fastcall DrSession::ReadCompletionRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2, DrSession *a3)
{
  NTSTATUS Status; // ecx
  struct _IRP *MasterIrp; // rdx
  struct _IRP *v8; // rcx

  Status = a2->IoStatus.Status;
  if ( (int)(Status + 0x80000000) < 0 || Status == -2147483643 )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    if ( MasterIrp )
      memmove(a2->UserBuffer, MasterIrp, a2->IoStatus.Information);
  }
  DrSession::ReadCompletion(a3, &a2->IoStatus);
  RefCount::Release(a3);
  if ( (a2->Flags & 0x20) != 0 )
  {
    v8 = a2->AssociatedIrp.MasterIrp;
    if ( v8 )
    {
      ExFreePoolWithTag(v8, 0);
      a2->AssociatedIrp.MasterIrp = 0;
    }
  }
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400242b0  mov     [rsp+arg_0], rbx
0x1400242b5  mov     [rsp+arg_8], rsi
0x1400242ba  push    rdi
0x1400242bb  sub     rsp, 20h
0x1400242bf  mov     ecx, [rdx+30h]
0x1400242c2  mov     rbx, rdx
0x1400242c5  mov     edx, 80000000h
0x1400242ca  mov     rdi, r8
0x1400242cd  lea     eax, [rcx+rdx]
0x1400242d0  test    edx, eax
0x1400242d2  jnz     short loc_14002431C
0x1400242d4  cmp     ecx, 80000005h
0x1400242da  jz      short loc_14002431C
0x1400242dc  lea     rdx, [rbx+30h]; struct _IO_STATUS_BLOCK *
0x1400242e0  mov     rcx, rdi; this
0x1400242e3  call    ?ReadCompletion@DrSession@@AEAAXPEAU_IO_STATUS_BLOCK@@@Z; DrSession::ReadCompletion(_IO_STATUS_BLOCK *)
0x1400242e8  mov     rcx, rdi; this
0x1400242eb  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x1400242f0  mov     eax, [rbx+10h]
0x1400242f3  test    al, 20h
0x1400242f5  jnz     short loc_140024334
0x1400242f7  mov     rcx, rbx; Irp
0x1400242fa  call    cs:__imp_IoFreeIrp
0x140024301  nop     dword ptr [rax+rax+00h]
0x140024306  mov     rbx, [rsp+28h+arg_0]
0x14002430b  mov     eax, 0C0000016h
0x140024310  mov     rsi, [rsp+28h+arg_8]
0x140024315  add     rsp, 20h
0x140024319  pop     rdi
0x14002431a  retn
0x14002431c  mov     rdx, [rbx+18h]; Src
0x140024320  test    rdx, rdx
0x140024323  jz      short loc_1400242DC
0x140024325  mov     r8, [rbx+38h]; Size
0x140024329  mov     rcx, [rbx+70h]; void *
0x14002432d  call    memmove
0x140024332  jmp     short loc_1400242DC
0x140024334  mov     rcx, [rbx+18h]; P
0x140024338  test    rcx, rcx
0x14002433b  jz      short loc_1400242F7
0x14002433d  xor     edx, edx; Tag
0x14002433f  call    cs:__imp_ExFreePoolWithTag
0x140024346  nop     dword ptr [rax+rax+00h]
0x14002434b  mov     qword ptr [rbx+18h], 0
0x140024353  jmp     short loc_1400242F7
```
