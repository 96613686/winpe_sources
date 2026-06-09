# PartitionChildIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14000b400`
- end: `0x14000b489`
- name: `?PartitionChildIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `137`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b400`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000b46c`
- `ntoskrnl!IoFreeIrp` at `0x14000b46c`
- `ntoskrnl!IoFreeMdl` at `0x14000b45d`
- `ntoskrnl!IoFreeMdl` at `0x14000b45d`
- `ntoskrnl!IofCompleteRequest` at `0x14000b44d`
- `ntoskrnl!IofCompleteRequest` at `0x14000b44d`
- `ntoskrnl!IoSetMasterIrpStatus` at `0x14000b42f`
- `ntoskrnl!IoSetMasterIrpStatus` at `0x14000b42f`

## pseudocode

```c
__int64 __fastcall PartitionChildIoCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, volatile signed __int32 *a3)
{
  if ( a2->PendingReturned )
    a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  _InterlockedAdd(a3 + 14, a2->IoStatus.Information);
  IoSetMasterIrpStatus(a3, (unsigned int)a2->IoStatus.Status);
  if ( _InterlockedExchangeAdd(a3 + 30, 0xFFFFFFFF) == 1 )
    IofCompleteRequest((PIRP)a3, 1);
  IoFreeMdl(a2->MdlAddress);
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000b400  mov     [rsp+arg_0], rbx
0x14000b405  push    rdi
0x14000b406  sub     rsp, 20h
0x14000b40a  cmp     byte ptr [rdx+41h], 0
0x14000b40e  mov     rdi, r8
0x14000b411  mov     rbx, rdx
0x14000b414  jz      short loc_14000B421
0x14000b416  mov     rax, [rdx+0B8h]
0x14000b41d  or      byte ptr [rax+3], 1
0x14000b421  mov     eax, [rdx+38h]
0x14000b424  lock add [r8+38h], eax
0x14000b429  mov     edx, [rdx+30h]
0x14000b42c  mov     rcx, rdi
0x14000b42f  call    cs:__imp_IoSetMasterIrpStatus
0x14000b436  nop     dword ptr [rax+rax+00h]
0x14000b43b  or      eax, 0FFFFFFFFh
0x14000b43e  lock xadd [rdi+78h], eax
0x14000b443  cmp     eax, 1
0x14000b446  jnz     short loc_14000B459
0x14000b448  mov     dl, al; PriorityBoost
0x14000b44a  mov     rcx, rdi; Irp
0x14000b44d  call    cs:__imp_IofCompleteRequest
0x14000b454  nop     dword ptr [rax+rax+00h]
0x14000b459  mov     rcx, [rbx+8]; Mdl
0x14000b45d  call    cs:__imp_IoFreeMdl
0x14000b464  nop     dword ptr [rax+rax+00h]
0x14000b469  mov     rcx, rbx; Irp
0x14000b46c  call    cs:__imp_IoFreeIrp
0x14000b473  nop     dword ptr [rax+rax+00h]
0x14000b478  mov     rbx, [rsp+28h+arg_0]
0x14000b47d  mov     eax, 0C0000016h
0x14000b482  add     rsp, 20h
0x14000b486  pop     rdi
0x14000b487  retn
```
