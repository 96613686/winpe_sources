# PartitionIoctlDsm(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140022df0`
- end: `0x1400232ad`
- name: `?PartitionIoctlDsm@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1213`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140003110`

## callees

- `0x1400030c0`
- `0x140003530`
- `0x140005994`
- `0x140011140`
- `0x140022df0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400230f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400230f1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140022eae`
- `ntoskrnl!KeWaitForSingleObject` at `0x140022eae`
- `ntoskrnl!IofCompleteRequest` at `0x1400230db`
- `ntoskrnl!IofCompleteRequest` at `0x1400231b1`
- `ntoskrnl!IofCompleteRequest` at `0x1400231e7`
- `ntoskrnl!IofCompleteRequest` at `0x1400230db`
- `ntoskrnl!IofCompleteRequest` at `0x1400231b1`
- `ntoskrnl!IofCompleteRequest` at `0x1400231e7`
- `ntoskrnl!ExAllocatePool2` at `0x140022f47`
- `ntoskrnl!ExAllocatePool2` at `0x140022f47`
- `ntoskrnl!KeReleaseMutex` at `0x14002300d`
- `ntoskrnl!KeReleaseMutex` at `0x1400230c6`
- `ntoskrnl!KeReleaseMutex` at `0x14002300d`
- `ntoskrnl!KeReleaseMutex` at `0x1400230c6`

## pseudocode

```c
__int64 __fastcall PartitionIoctlDsm(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  unsigned int Options; // r8d
  struct _DEVICE_OBJECT *v4; // r10
  struct _IRP *MasterIrp; // r14
  unsigned int v6; // r15d
  ULONG Flags; // ecx
  unsigned int *v8; // rdi
  LONG IrpCount; // edx
  unsigned int v10; // r9d
  char *DeviceExtension; // rbp
  unsigned __int64 v12; // rax
  NTSTATUS v13; // esi
  int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  ULONG Length; // eax
  ULONG v18; // r15d
  struct _IRP *Pool2; // rax
  struct _IRP *v20; // r12
  size_t v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // eax
  LONG v24; // eax
  unsigned int v25; // edi
  unsigned __int64 *i; // rbx
  struct _IO_STACK_LOCATION *v27; // rax
  struct _IO_STACK_LOCATION *v28; // rax
  struct _IRP *v29; // rcx
  struct _IO_STACK_LOCATION *v30; // rax
  unsigned __int64 v32; // rax
  unsigned int v33; // edi
  unsigned __int64 *v34; // rbx
  unsigned int v35; // r10d
  unsigned int v36; // eax
  unsigned int MdlAddress_high; // ecx
  __int128 v38; // [rsp+30h] [rbp-68h] BYREF
  __int128 v39; // [rsp+40h] [rbp-58h]
  char *v41; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int *v42; // [rsp+B0h] [rbp+18h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+B8h] [rbp+20h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v38 = 0;
  v41 = 0;
  v39 = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  v4 = a1;
  if ( Options < 0x1C )
  {
    v13 = -1073741811;
    a2->IoStatus.Status = -1073741811;
    IofCompleteRequest(a2, 0);
    return (unsigned int)v13;
  }
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v6 = 0;
  Flags = MasterIrp->Flags;
  v8 = (unsigned int *)&MasterIrp->MdlAddress + 1;
  v42 = (unsigned int *)&MasterIrp->MdlAddress + 1;
  if ( Flags )
  {
    v6 = *v8 + Flags;
    if ( v6 < *v8 )
    {
      v13 = -1073741675;
      a2->IoStatus.Status = -1073741675;
LABEL_34:
      IofCompleteRequest(a2, 0);
      return (unsigned int)v13;
    }
    if ( *v8 < 0x1C || Options < v6 )
    {
      v13 = -1073741811;
      a2->IoStatus.Status = -1073741811;
      goto LABEL_34;
    }
  }
  else
  {
    v42 = (unsigned int *)&MasterIrp->MdlAddress + 1;
  }
  IrpCount = MasterIrp->AssociatedIrp.IrpCount;
  v10 = 0;
  if ( IrpCount )
  {
    if ( ((__int64)MasterIrp->MdlAddress & 1) != 0 )
      goto LABEL_57;
    v35 = *(&MasterIrp->Flags + 1);
    v10 = v35 + IrpCount;
    if ( v35 + IrpCount < v35 )
    {
      v13 = -1073741675;
LABEL_37:
      a2->IoStatus.Status = v13;
      goto LABEL_34;
    }
    if ( !v35 || (IrpCount & 0xF) != 0 || v35 < 0x1C || Options < v10 || (((_BYTE)MasterIrp + (_BYTE)v35) & 7) != 0 )
      goto LABEL_57;
    v4 = a1;
  }
  if ( !Flags || !IrpCount )
    goto LABEL_6;
  v36 = *(&MasterIrp->Flags + 1);
  MdlAddress_high = HIDWORD(MasterIrp->MdlAddress);
  if ( MdlAddress_high >= v36 )
  {
    if ( v10 <= MdlAddress_high )
      goto LABEL_6;
LABEL_57:
    v13 = -1073741811;
    goto LABEL_37;
  }
  if ( v6 > v36 )
    goto LABEL_57;
LABEL_6:
  DeviceExtension = (char *)v4->DeviceExtension;
  KeWaitForSingleObject((PVOID)(*((_QWORD *)DeviceExtension + 3) + 56LL), Executive, 0, 0, 0);
  if ( ((__int64)MasterIrp->MdlAddress & 1) != 0 )
  {
    v12 = PartitionLength((struct _PARTITION_EXTENSION *)DeviceExtension, 1u);
    v13 = PmEnumerateOverlaps(
            (struct _LIST_ENTRY *)(DeviceExtension + 312),
            0,
            v12,
            (int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *))&PartitionOverlapCount,
            &v38);
    if ( v13 < 0 )
    {
LABEL_23:
      KeReleaseMutex((PRKMUTEX)(*((_QWORD *)DeviceExtension + 3) + 56LL), 0);
      a2->IoStatus.Status = v13;
      IofCompleteRequest(a2, 0);
      return (unsigned int)v13;
    }
  }
  else
  {
    v33 = MasterIrp->AssociatedIrp.IrpCount;
    v34 = (unsigned __int64 *)((char *)MasterIrp + *(&MasterIrp->Flags + 1));
    while ( v33 >= 0x10 )
    {
      v13 = PmEnumerateOverlaps(
              (struct _LIST_ENTRY *)(DeviceExtension + 312),
              *v34,
              v34[1],
              (int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *))&PartitionOverlapCount,
              &v38);
      if ( v13 < 0 )
        goto LABEL_23;
      v33 -= 16;
      v34 += 2;
    }
    v8 = v42;
  }
  if ( !(_DWORD)v39 )
  {
    v13 = -1073741811;
    goto LABEL_23;
  }
  if ( MasterIrp->Flags )
  {
    v14 = v6 + 7;
    if ( v6 + 7 < v6 )
      goto LABEL_22;
  }
  else
  {
    v14 = 35;
  }
  v15 = v14 & 0xFFFFFFF8;
  v16 = v15 + 16 * v39;
  if ( v16 < v15 )
  {
LABEL_22:
    v13 = -1073741675;
    goto LABEL_23;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( v16 >= Length )
    Length = v15 + 16 * v39;
  v18 = Length;
  Pool2 = (struct _IRP *)ExAllocatePool2(74, Length, 1112108368);
  v20 = Pool2;
  if ( !Pool2 )
  {
    v13 = -1073741670;
    goto LABEL_23;
  }
  v21 = MasterIrp->Flags;
  v22 = *v8;
  *(_DWORD *)&Pool2->Type = 28;
  *(_DWORD *)(&Pool2->Size + 1) = *(_DWORD *)(&MasterIrp->Size + 1);
  v23 = (__int64)MasterIrp->MdlAddress & 0xFFFFFFFE;
  HIDWORD(v20->MdlAddress) = v22;
  LODWORD(v20->MdlAddress) = v23;
  v24 = 16 * v39;
  v20->Flags = v21;
  *(&v20->Flags + 1) = v15;
  v20->AssociatedIrp.IrpCount = v24;
  if ( (_DWORD)v21 )
    memmove((char *)v20 + v22, (char *)MasterIrp + v22, v21);
  v41 = (char *)v20 + *(&v20->Flags + 1);
  if ( ((__int64)MasterIrp->MdlAddress & 1) != 0 )
  {
    v32 = PartitionLength((struct _PARTITION_EXTENSION *)DeviceExtension, 1u);
    PmEnumerateOverlaps(
      (struct _LIST_ENTRY *)(DeviceExtension + 312),
      0,
      v32,
      (int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *))&PartitionOverlapDsm,
      &v41);
  }
  else
  {
    v25 = MasterIrp->AssociatedIrp.IrpCount;
    for ( i = (unsigned __int64 *)((char *)MasterIrp + *(&MasterIrp->Flags + 1)); v25 >= 0x10; i += 2 )
    {
      PmEnumerateOverlaps(
        (struct _LIST_ENTRY *)(DeviceExtension + 312),
        *i,
        i[1],
        (int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *))&PartitionOverlapDsm,
        &v41);
      v25 -= 16;
    }
  }
  KeReleaseMutex((PRKMUTEX)(*((_QWORD *)DeviceExtension + 3) + 56LL), 0);
  v27 = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v27[-1].MajorFunction = *(_OWORD *)&v27->MajorFunction;
  *(_OWORD *)&v27[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v27->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v27[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v27->Parameters.SetQuota + 6);
  v27[-1].FileObject = v27->FileObject;
  v27[-1].Control = 0;
  v28 = a2->Tail.Overlay.CurrentStackLocation;
  v28[-1].Flags |= 0x12u;
  v28[-1].Parameters.Create.Options = v18;
  v29 = a2->AssociatedIrp.MasterIrp;
  v30 = a2->Tail.Overlay.CurrentStackLocation;
  a2->AssociatedIrp.MasterIrp = v20;
  v30[-1].CompletionRoutine = PartitionIoctlDsmCompletion;
  v30[-1].Context = v29;
  v30[-1].Control = -32;
  return (unsigned int)PartitionSendRequest(a1, a2);
}

```

## disassembly

```asm
0x140022df0  mov     rax, rsp
0x140022df3  mov     [rax+8], rcx
0x140022df7  push    rsi
0x140022df8  push    r13
0x140022dfa  sub     rsp, 88h
0x140022e01  mov     rsi, [rdx+0B8h]
0x140022e08  xorps   xmm0, xmm0
0x140022e0b  xor     r11d, r11d
0x140022e0e  mov     [rsp+98h+arg_18], rsi
0x140022e16  movups  xmmword ptr [rax-68h], xmm0
0x140022e1a  mov     [rax+10h], r11
0x140022e1e  mov     r13, rdx
0x140022e21  movups  xmmword ptr [rax-58h], xmm0
0x140022e25  mov     r8d, [rsi+10h]
0x140022e29  mov     r10, rcx
0x140022e2c  cmp     r8d, 1Ch
0x140022e30  jb      loc_1400231DA
0x140022e36  mov     [rax-28h], rdi
0x140022e3a  mov     [rax-38h], r14
0x140022e3e  mov     r14, [rdx+18h]
0x140022e42  mov     [rax-40h], r15
0x140022e46  mov     r15d, r11d
0x140022e49  mov     ecx, [r14+10h]
0x140022e4d  lea     rdi, [r14+0Ch]
0x140022e51  mov     [rsp+98h+arg_10], rdi
0x140022e59  test    ecx, ecx
0x140022e5b  jnz     loc_140023199
0x140022e61  mov     [rsp+98h+arg_10], rdi
0x140022e69  mov     edx, [r14+18h]
0x140022e6d  mov     r9d, r11d
0x140022e70  test    edx, edx
0x140022e72  jnz     loc_14002320F
0x140022e78  test    ecx, ecx
0x140022e7a  jnz     loc_14002325C
0x140022e80  mov     [rsp+98h+var_18], rbx
0x140022e88  xor     r9d, r9d; Alertable
0x140022e8b  mov     [rsp+98h+var_20], rbp
0x140022e90  xor     r8d, r8d; WaitMode
0x140022e93  mov     rbp, [r10+40h]
0x140022e97  xor     edx, edx; WaitReason
0x140022e99  mov     [rsp+98h+var_30], r12
0x140022e9e  mov     r12, r11
0x140022ea1  mov     [rsp+98h+Timeout], r11; Timeout
0x140022ea6  mov     rcx, [rbp+18h]
0x140022eaa  add     rcx, 38h ; '8'; Object
0x140022eae  call    cs:__imp_KeWaitForSingleObject
0x140022eb5  nop     dword ptr [rax+rax+00h]
0x140022eba  mov     eax, [r14+8]
0x140022ebe  test    al, 1
0x140022ec0  jz      loc_140023142
0x140022ec6  mov     dl, 1; unsigned __int8
0x140022ec8  mov     rcx, rbp; struct _PARTITION_EXTENSION *
0x140022ecb  call    ?PartitionLength@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionLength(_PARTITION_EXTENSION *,uchar)
0x140022ed0  mov     r8, rax; unsigned __int64
0x140022ed3  lea     rcx, [rbp+138h]; struct _LIST_ENTRY *
0x140022eda  lea     rax, [rsp+98h+var_68]
0x140022edf  xor     edx, edx; unsigned __int64
0x140022ee1  lea     r9, ?PartitionOverlapCount@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z; int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *)
0x140022ee8  mov     [rsp+98h+Timeout], rax; void *
0x140022eed  call    ?PmEnumerateOverlaps@@YAJPEAU_LIST_ENTRY@@_K1P6AJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@11PEAX@Z4@Z; PmEnumerateOverlaps(_LIST_ENTRY *,unsigned __int64,unsigned __int64,long (*)(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *),void *)
0x140022ef2  mov     esi, eax
0x140022ef4  test    eax, eax
0x140022ef6  js      loc_1400230BC
0x140022efc  mov     eax, dword ptr [rsp+98h+var_58]
0x140022f00  test    eax, eax
0x140022f02  jz      loc_140023282
0x140022f08  cmp     [r14+10h], r12d
0x140022f0c  jnz     loc_1400230FF
0x140022f12  mov     ebx, 23h ; '#'
0x140022f17  and     ebx, 0FFFFFFF8h
0x140022f1a  add     eax, eax
0x140022f1c  lea     ecx, [rbx+rax*8]
0x140022f1f  cmp     ecx, ebx
0x140022f21  jb      loc_1400230B7
0x140022f27  mov     rax, [rsp+98h+arg_18]
0x140022f2f  mov     r8d, 42496D50h
0x140022f35  mov     eax, [rax+8]
0x140022f38  cmp     ecx, eax
0x140022f3a  cmovnb  eax, ecx
0x140022f3d  mov     ecx, 4Ah ; 'J'
0x140022f42  mov     edx, eax
0x140022f44  mov     r15d, eax
0x140022f47  call    cs:__imp_ExAllocatePool2
0x140022f4e  nop     dword ptr [rax+rax+00h]
0x140022f53  mov     r12, rax
0x140022f56  test    rax, rax
0x140022f59  jz      loc_14002328C
0x140022f5f  mov     ecx, [r14+10h]
0x140022f63  mov     edx, [rdi]
0x140022f65  mov     dword ptr [rax], 1Ch
0x140022f6b  mov     eax, [r14+4]
0x140022f6f  mov     [r12+4], eax
0x140022f74  mov     eax, [r14+8]
0x140022f78  and     eax, 0FFFFFFFEh
0x140022f7b  mov     [r12+0Ch], edx
0x140022f80  mov     [r12+8], eax
0x140022f85  mov     eax, dword ptr [rsp+98h+var_58]
0x140022f89  shl     eax, 4
0x140022f8c  mov     [r12+10h], ecx
0x140022f91  mov     [r12+14h], ebx
0x140022f96  mov     [r12+18h], eax
0x140022f9b  test    ecx, ecx
0x140022f9d  jnz     loc_140023296
0x140022fa3  mov     eax, [r12+14h]
0x140022fa8  add     rax, r12
0x140022fab  mov     [rsp+98h+arg_8], rax
0x140022fb3  mov     eax, [r14+8]
0x140022fb7  test    al, 1
0x140022fb9  jnz     loc_14002310E
0x140022fbf  mov     ebx, [r14+14h]
0x140022fc3  mov     edi, [r14+18h]
0x140022fc7  add     rbx, r14
0x140022fca  cmp     edi, 10h
0x140022fcd  jb      short loc_140023003
0x140022fcf  nop
0x140022fd0  mov     r8, [rbx+8]; unsigned __int64
0x140022fd4  lea     rax, [rsp+98h+arg_8]
0x140022fdc  mov     rdx, [rbx]; unsigned __int64
0x140022fdf  lea     r9, ?PartitionOverlapDsm@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z; int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *)
0x140022fe6  lea     rcx, [rbp+138h]; struct _LIST_ENTRY *
0x140022fed  mov     [rsp+98h+Timeout], rax; void *
0x140022ff2  call    ?PmEnumerateOverlaps@@YAJPEAU_LIST_ENTRY@@_K1P6AJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@11PEAX@Z4@Z; PmEnumerateOverlaps(_LIST_ENTRY *,unsigned __int64,unsigned __int64,long (*)(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *),void *)
0x140022ff7  add     edi, 0FFFFFFF0h
0x140022ffa  lea     rbx, [rbx+10h]
0x140022ffe  cmp     edi, 10h
0x140023001  jnb     short loc_140022FD0
0x140023003  mov     rcx, [rbp+18h]
0x140023007  xor     edx, edx; Wait
0x140023009  add     rcx, 38h ; '8'; Mutex
0x14002300d  call    cs:__imp_KeReleaseMutex
0x140023014  nop     dword ptr [rax+rax+00h]
0x140023019  mov     rax, [r13+0B8h]
0x140023020  lea     rdx, ?PartitionIoctlDsmCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; PartitionIoctlDsmCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x140023027  movups  xmm0, xmmword ptr [rax]
0x14002302a  movups  xmmword ptr [rax-48h], xmm0
0x14002302e  movups  xmm1, xmmword ptr [rax+10h]
0x140023032  movups  xmmword ptr [rax-38h], xmm1
0x140023036  movups  xmm0, xmmword ptr [rax+20h]
0x14002303a  movups  xmmword ptr [rax-28h], xmm0
0x14002303e  movsd   xmm1, qword ptr [rax+30h]
0x140023043  movsd   qword ptr [rax-18h], xmm1
0x140023048  mov     byte ptr [rax-45h], 0
0x14002304c  mov     rax, [r13+0B8h]
0x140023053  or      byte ptr [rax-46h], 12h
0x140023057  mov     [rax-38h], r15d
0x14002305b  mov     rcx, [r13+18h]
0x14002305f  mov     rax, [r13+0B8h]
0x140023066  mov     [r13+18h], r12
0x14002306a  mov     [rax-10h], rdx
0x14002306e  mov     rdx, r13; struct _IRP *
0x140023071  mov     [rax-8], rcx
0x140023075  mov     rcx, [rsp+98h+arg_0]; struct _DEVICE_OBJECT *
0x14002307d  mov     byte ptr [rax-45h], 0E0h
0x140023081  call    ?PartitionSendRequest@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionSendRequest(_DEVICE_OBJECT *,_IRP *)
0x140023086  mov     esi, eax
0x140023088  mov     rbp, [rsp+98h+var_20]
0x14002308d  mov     r12, [rsp+98h+var_30]
0x140023092  mov     rbx, [rsp+98h+var_18]
0x14002309a  mov     rdi, [rsp+98h+var_28]
0x14002309f  mov     r14, [rsp+98h+var_38]
0x1400230a4  mov     r15, [rsp+98h+var_40]
0x1400230a9  mov     eax, esi
0x1400230ab  add     rsp, 88h
0x1400230b2  pop     r13
0x1400230b4  pop     rsi
0x1400230b5  retn
0x1400230b7  mov     esi, 0C0000095h
0x1400230bc  mov     rcx, [rbp+18h]
0x1400230c0  xor     edx, edx; Wait
0x1400230c2  add     rcx, 38h ; '8'; Mutex
0x1400230c6  call    cs:__imp_KeReleaseMutex
0x1400230cd  nop     dword ptr [rax+rax+00h]
0x1400230d2  xor     edx, edx; PriorityBoost
0x1400230d4  mov     [r13+30h], esi
0x1400230d8  mov     rcx, r13; Irp
0x1400230db  call    cs:__imp_IofCompleteRequest
0x1400230e2  nop     dword ptr [rax+rax+00h]
0x1400230e7  test    r12, r12
0x1400230ea  jz      short loc_140023088
0x1400230ec  xor     edx, edx; Tag
0x1400230ee  mov     rcx, r12; P
0x1400230f1  call    cs:__imp_ExFreePoolWithTag
0x1400230f8  nop     dword ptr [rax+rax+00h]
0x1400230fd  jmp     short loc_140023088
0x1400230ff  lea     ebx, [r15+7]
0x140023103  cmp     ebx, r15d
0x140023106  jnb     loc_140022F17
0x14002310c  jmp     short loc_1400230B7
0x14002310e  mov     dl, 1; unsigned __int8
0x140023110  mov     rcx, rbp; struct _PARTITION_EXTENSION *
0x140023113  call    ?PartitionLength@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionLength(_PARTITION_EXTENSION *,uchar)
0x140023118  mov     r8, rax; unsigned __int64
0x14002311b  lea     rcx, [rbp+138h]; struct _LIST_ENTRY *
0x140023122  lea     rax, [rsp+98h+arg_8]
0x14002312a  xor     edx, edx; unsigned __int64
0x14002312c  lea     r9, ?PartitionOverlapDsm@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z; int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *)
0x140023133  mov     [rsp+98h+Timeout], rax; void *
0x140023138  call    ?PmEnumerateOverlaps@@YAJPEAU_LIST_ENTRY@@_K1P6AJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@11PEAX@Z4@Z; PmEnumerateOverlaps(_LIST_ENTRY *,unsigned __int64,unsigned __int64,long (*)(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *),void *)
0x14002313d  jmp     loc_140023003
0x140023142  mov     ebx, [r14+14h]
0x140023146  mov     edi, [r14+18h]
0x14002314a  add     rbx, r14
0x14002314d  nop     dword ptr [rax]
0x140023150  cmp     edi, 10h
0x140023153  jb      short loc_14002318C
0x140023155  mov     r8, [rbx+8]; unsigned __int64
0x140023159  lea     rax, [rsp+98h+var_68]
0x14002315e  mov     rdx, [rbx]; unsigned __int64
0x140023161  lea     rcx, [rbp+138h]; struct _LIST_ENTRY *
0x140023168  lea     r9, ?PartitionOverlapCount@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z; int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *)
0x14002316f  mov     [rsp+98h+Timeout], rax; void *
0x140023174  call    ?PmEnumerateOverlaps@@YAJPEAU_LIST_ENTRY@@_K1P6AJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@11PEAX@Z4@Z; PmEnumerateOverlaps(_LIST_ENTRY *,unsigned __int64,unsigned __int64,long (*)(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *),void *)
0x140023179  mov     esi, eax
0x14002317b  test    eax, eax
0x14002317d  js      loc_1400230BC
0x140023183  add     edi, 0FFFFFFF0h
0x140023186  add     rbx, 10h
0x14002318a  jmp     short loc_140023150
0x14002318c  mov     rdi, [rsp+98h+arg_10]
0x140023194  jmp     loc_140022EFC
0x140023199  mov     eax, [rdi]
0x14002319b  lea     r15d, [rax+rcx]
0x14002319f  cmp     r15d, eax
0x1400231a2  jnb     short loc_1400231F8
0x1400231a4  mov     esi, 0C0000095h
0x1400231a9  mov     [rdx+30h], esi
0x1400231ac  xor     edx, edx; PriorityBoost
0x1400231ae  mov     rcx, r13; Irp
0x1400231b1  call    cs:__imp_IofCompleteRequest
0x1400231b8  nop     dword ptr [rax+rax+00h]
0x1400231bd  jmp     loc_14002309A
0x1400231c2  mov     r10d, [r14+14h]
0x1400231c6  lea     r9d, [r10+rdx]
0x1400231ca  cmp     r9d, r10d
0x1400231cd  jnb     short loc_14002321D
0x1400231cf  mov     esi, 0C0000095h
0x1400231d4  mov     [r13+30h], esi
0x1400231d8  jmp     short loc_1400231AC
0x1400231da  mov     esi, 0C000000Dh
0x1400231df  mov     rcx, r13; Irp
0x1400231e2  mov     [rdx+30h], esi
0x1400231e5  xor     edx, edx; PriorityBoost
0x1400231e7  call    cs:__imp_IofCompleteRequest
0x1400231ee  nop     dword ptr [rax+rax+00h]
0x1400231f3  jmp     loc_1400230A9
0x1400231f8  cmp     eax, 1Ch
0x1400231fb  jb      loc_140028168
0x140023201  cmp     r8d, r15d
0x140023204  jnb     loc_140022E69
0x14002320a  jmp     loc_140028168
0x14002320f  mov     eax, [r14+8]
0x140023213  test    al, 1
0x140023215  jnz     loc_140028175
0x14002321b  jmp     short loc_1400231C2
0x14002321d  test    r10d, r10d
0x140023220  jz      loc_140028175
0x140023226  test    dl, 0Fh
0x140023229  jnz     loc_140028175
0x14002322f  cmp     r10d, 1Ch
0x140023233  jb      loc_140028175
0x140023239  cmp     r8d, r9d
0x14002323c  jb      loc_140028175
0x140023242  add     r10b, r14b
0x140023245  test    r10b, 7
0x140023249  jnz     loc_140028175
0x14002324f  mov     r10, [rsp+98h+arg_0]
0x140023257  jmp     loc_140022E78
0x14002325c  test    edx, edx
0x14002325e  jz      loc_140022E80
0x140023264  mov     eax, [r14+14h]
0x140023268  mov     ecx, [r14+0Ch]
0x14002326c  cmp     ecx, eax
0x14002326e  jnb     loc_14002817F
0x140023274  cmp     r15d, eax
0x140023277  jbe     loc_140022E80
0x14002327d  jmp     loc_140028175
0x140023282  mov     esi, 0C000000Dh
0x140023287  jmp     loc_1400230BC
0x14002328c  mov     esi, 0C000009Ah
0x140023291  jmp     loc_1400230BC
0x140023296  mov     rax, rdx
0x140023299  mov     r8, rcx; Size
0x14002329c  add     rdx, r14; Src
0x14002329f  lea     rcx, [rax+r12]; void *
0x1400232a3  call    memmove
0x1400232a8  jmp     loc_140022FA3
0x140028168  mov     esi, 0C000000Dh
0x14002816d  mov     [rdx+30h], esi
0x140028170  jmp     loc_1400231AC
0x140028175  mov     esi, 0C000000Dh
0x14002817a  jmp     loc_1400231D4
0x14002817f  cmp     r9d, ecx
0x140028182  ja      short loc_140028175
0x140028184  jmp     loc_140022E80
```
