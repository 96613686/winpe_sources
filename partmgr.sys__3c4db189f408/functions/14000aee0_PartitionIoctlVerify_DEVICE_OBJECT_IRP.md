# PartitionIoctlVerify(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14000aee0`
- end: `0x14000afc3`
- name: `?PartitionIoctlVerify@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140003110`

## callees

- `0x1400030a0`
- `0x140003530`
- `0x14000aee0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000af1a`
- `ntoskrnl!IofCompleteRequest` at `0x14000af1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000af84`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000af84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000af46`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000af46`

## pseudocode

```c
__int64 __fastcall PartitionIoctlVerify(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  NTSTATUS v5; // esi
  char *DeviceExtension; // rdi
  struct _IRP *MasterIrp; // r15
  KIRQL v9; // bl
  __int128 v10; // [rsp+30h] [rbp-58h] BYREF
  __int128 v11; // [rsp+40h] [rbp-48h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v10 = 0;
  v11 = 0;
  if ( CurrentStackLocation->Parameters.Create.Options >= 0x10 )
  {
    DeviceExtension = (char *)a1->DeviceExtension;
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*((_QWORD *)DeviceExtension + 3) + 112LL));
    v5 = PmEnumerateOverlaps(
           (struct _LIST_ENTRY *)(DeviceExtension + 312),
           *(_QWORD *)&MasterIrp->Type,
           LODWORD(MasterIrp->MdlAddress),
           (int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *))PartitionOverlapCount,
           &v10);
    KeReleaseSpinLock((PKSPIN_LOCK)(*((_QWORD *)DeviceExtension + 3) + 112LL), v9);
    if ( v5 >= 0 )
    {
      if ( (_DWORD)v11 == 1 )
      {
        *(_QWORD *)&MasterIrp->Type = *((_QWORD *)&v11 + 1);
        return (unsigned int)PartitionPassThrough(a1, a2);
      }
      v5 = -1073741637;
    }
  }
  else
  {
    v5 = -1073741820;
  }
  a2->IoStatus.Status = v5;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000aee0  push    rbx
0x14000aee2  push    rbp
0x14000aee3  push    rsi
0x14000aee4  push    rdi
0x14000aee5  push    r14
0x14000aee7  push    r15
0x14000aee9  sub     rsp, 58h
0x14000aeed  mov     rax, [rdx+0B8h]
0x14000aef4  xorps   xmm0, xmm0
0x14000aef7  movups  [rsp+88h+var_58], xmm0
0x14000aefc  mov     rbp, rdx
0x14000aeff  mov     r14, rcx
0x14000af02  movups  [rsp+88h+var_48], xmm0
0x14000af07  cmp     dword ptr [rax+10h], 10h
0x14000af0b  jnb     short loc_14000AF36
0x14000af0d  mov     esi, 0C0000004h
0x14000af12  xor     edx, edx; PriorityBoost
0x14000af14  mov     [rbp+30h], esi
0x14000af17  mov     rcx, rbp; Irp
0x14000af1a  call    cs:__imp_IofCompleteRequest
0x14000af21  nop     dword ptr [rax+rax+00h]
0x14000af26  mov     eax, esi
0x14000af28  add     rsp, 58h
0x14000af2c  pop     r15
0x14000af2e  pop     r14
0x14000af30  pop     rdi
0x14000af31  pop     rsi
0x14000af32  pop     rbp
0x14000af33  pop     rbx
0x14000af34  retn
0x14000af36  mov     rdi, [rcx+40h]
0x14000af3a  mov     r15, [rdx+18h]
0x14000af3e  mov     rcx, [rdi+18h]
0x14000af42  add     rcx, 70h ; 'p'; SpinLock
0x14000af46  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000af4d  nop     dword ptr [rax+rax+00h]
0x14000af52  mov     r8d, [r15+8]; unsigned __int64
0x14000af56  lea     rcx, [rdi+138h]; struct _LIST_ENTRY *
0x14000af5d  mov     rdx, [r15]; unsigned __int64
0x14000af60  lea     r9, ?PartitionOverlapCount@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z; int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *)
0x14000af67  mov     bl, al
0x14000af69  lea     rax, [rsp+88h+var_58]
0x14000af6e  mov     [rsp+88h+var_68], rax; void *
0x14000af73  call    ?PmEnumerateOverlaps@@YAJPEAU_LIST_ENTRY@@_K1P6AJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@11PEAX@Z4@Z; PmEnumerateOverlaps(_LIST_ENTRY *,unsigned __int64,unsigned __int64,long (*)(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *),void *)
0x14000af78  mov     rcx, [rdi+18h]
0x14000af7c  mov     dl, bl; NewIrql
0x14000af7e  add     rcx, 70h ; 'p'; SpinLock
0x14000af82  mov     esi, eax
0x14000af84  call    cs:__imp_KeReleaseSpinLock
0x14000af8b  nop     dword ptr [rax+rax+00h]
0x14000af90  test    esi, esi
0x14000af92  js      loc_14000AF12
0x14000af98  cmp     dword ptr [rsp+88h+var_48], 1
0x14000af9d  jz      short loc_14000AFA9
0x14000af9f  mov     esi, 0C00000BBh
0x14000afa4  jmp     loc_14000AF12
0x14000afa9  mov     rax, qword ptr [rsp+88h+var_48+8]
0x14000afae  mov     rdx, rbp; struct _IRP *
0x14000afb1  mov     rcx, r14; struct _DEVICE_OBJECT *
0x14000afb4  mov     [r15], rax
0x14000afb7  call    ?PartitionPassThrough@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionPassThrough(_DEVICE_OBJECT *,_IRP *)
0x14000afbc  mov     esi, eax
0x14000afbe  jmp     loc_14000AF26
```
