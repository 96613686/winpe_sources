# PartitionIoctlBandmgmt(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14002532c`
- end: `0x1400254bf`
- name: `?PartitionIoctlBandmgmt@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003110`

## callees

- `0x1400030a0`
- `0x140005994`
- `0x140005a84`
- `0x14002532c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400253e8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400253e8`
- `ntoskrnl!IofCompleteRequest` at `0x140025457`
- `ntoskrnl!IofCompleteRequest` at `0x140025457`
- `ntoskrnl!KeReleaseMutex` at `0x140025443`
- `ntoskrnl!KeReleaseMutex` at `0x140025496`
- `ntoskrnl!KeReleaseMutex` at `0x140025443`
- `ntoskrnl!KeReleaseMutex` at `0x140025496`

## pseudocode

```c
__int64 __fastcall PartitionIoctlBandmgmt(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *p_AssociatedIrp; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  struct _IRP *MasterIrp; // r9
  _DWORD *v7; // rdi
  unsigned int v8; // eax
  _QWORD *p_Flags; // rbx
  unsigned int v10; // ebx
  struct _PARTITION_EXTENSION *DeviceExtension; // rsi
  __int64 v12; // r9
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // rax
  __int64 v16; // r8

  p_AssociatedIrp = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  switch ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart )
  {
    case 0x2D148Cu:
      p_AssociatedIrp = &MasterIrp->AssociatedIrp;
LABEL_12:
      p_Flags = &MasterIrp->Flags;
      v7 = (_DWORD *)&MasterIrp->MdlAddress + 1;
      goto LABEL_13;
    case 0x2D149Cu:
    case 0x2DD494u:
      v8 = 24;
      v7 = &MasterIrp->Size + 1;
      p_Flags = &MasterIrp->MdlAddress;
      goto LABEL_14;
    case 0x2DD498u:
      v8 = 40;
      v7 = (_DWORD *)&MasterIrp->MdlAddress + 1;
      p_Flags = &MasterIrp->Flags;
      goto LABEL_14;
  }
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 3003552 )
  {
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 3003560 )
    {
      v7 = 0;
      v8 = 0;
      p_Flags = 0;
      goto LABEL_14;
    }
    goto LABEL_12;
  }
  v7 = &MasterIrp->Size + 1;
  p_Flags = &MasterIrp->MdlAddress;
LABEL_13:
  v8 = 32;
LABEL_14:
  if ( CurrentStackLocation->Parameters.Create.Options < v8 )
  {
    v10 = -1073741820;
LABEL_23:
    a2->IoStatus.Status = v10;
    IofCompleteRequest(a2, 0);
    return v10;
  }
  DeviceExtension = (struct _PARTITION_EXTENSION *)a1->DeviceExtension;
  KeWaitForSingleObject((PVOID)(*((_QWORD *)DeviceExtension + 3) + 56LL), Executive, 0, 0, 0);
  if ( PartitionOffset(DeviceExtension, 1u) != *((_QWORD *)DeviceExtension + 22) )
  {
    v10 = -1073741637;
LABEL_22:
    KeReleaseMutex((PRKMUTEX)(*((_QWORD *)DeviceExtension + 3) + 56LL), 0);
    goto LABEL_23;
  }
  v12 = 0x7FFFFFFFFFFFFFFFLL;
  if ( *v7 == -1 && *p_Flags != 0x7FFFFFFFFFFFFFFFLL )
  {
    v13 = PartitionLength(DeviceExtension, 1u);
    if ( v14 >= v13 )
    {
      v10 = -1073741811;
      goto LABEL_22;
    }
    v15 = PartitionOffset(DeviceExtension, 1u);
    *p_Flags = v16 + v15;
  }
  if ( p_AssociatedIrp && p_AssociatedIrp->MasterIrp == (struct _IRP *)v12 )
    p_AssociatedIrp->MasterIrp = (struct _IRP *)PartitionLength(DeviceExtension, 1u);
  KeReleaseMutex((PRKMUTEX)(*((_QWORD *)DeviceExtension + 3) + 56LL), 0);
  return (unsigned int)PartitionPassThrough(a1, a2);
}

```

## disassembly

```asm
0x14002532c  push    rbx
0x14002532e  push    rbp
0x14002532f  push    rsi
0x140025330  push    rdi
0x140025331  push    r14
0x140025333  push    r15
0x140025335  sub     rsp, 38h
0x140025339  mov     rbp, rdx
0x14002533c  xor     r14d, r14d
0x14002533f  mov     rdx, [rdx+0B8h]
0x140025346  mov     r15, rcx
0x140025349  mov     r9, [rbp+18h]
0x14002534d  mov     r8d, [rdx+18h]
0x140025351  sub     r8d, 2D148Ch
0x140025358  jz      short loc_1400253AB
0x14002535a  sub     r8d, 10h
0x14002535e  jz      short loc_14002539C
0x140025360  sub     r8d, 0BFF8h
0x140025367  jz      short loc_14002539C
0x140025369  sub     r8d, 4
0x14002536d  jz      short loc_14002538D
0x14002536f  sub     r8d, 8
0x140025373  jz      short loc_140025383
0x140025375  cmp     r8d, 8
0x140025379  jz      short loc_1400253AF
0x14002537b  xor     edi, edi
0x14002537d  xor     eax, eax
0x14002537f  xor     ebx, ebx
0x140025381  jmp     short loc_1400253BC
0x140025383  lea     rdi, [r9+4]
0x140025387  lea     rbx, [r9+8]
0x14002538b  jmp     short loc_1400253B7
0x14002538d  mov     eax, 28h ; '('
0x140025392  lea     rdi, [r9+0Ch]
0x140025396  lea     rbx, [r9+10h]
0x14002539a  jmp     short loc_1400253BC
0x14002539c  mov     eax, 18h
0x1400253a1  lea     rdi, [r9+4]
0x1400253a5  lea     rbx, [r9+8]
0x1400253a9  jmp     short loc_1400253BC
0x1400253ab  lea     r14, [r9+18h]
0x1400253af  lea     rbx, [r9+10h]
0x1400253b3  lea     rdi, [r9+0Ch]
0x1400253b7  mov     eax, 20h ; ' '
0x1400253bc  cmp     [rdx+10h], eax
0x1400253bf  jnb     short loc_1400253CB
0x1400253c1  mov     ebx, 0C0000004h
0x1400253c6  jmp     loc_14002544F
0x1400253cb  mov     rsi, [rcx+40h]
0x1400253cf  xor     r9d, r9d; Alertable
0x1400253d2  xor     r8d, r8d; WaitMode
0x1400253d5  mov     [rsp+68h+Timeout], 0; Timeout
0x1400253de  xor     edx, edx; WaitReason
0x1400253e0  mov     rcx, [rsi+18h]
0x1400253e4  add     rcx, 38h ; '8'; Object
0x1400253e8  call    cs:__imp_KeWaitForSingleObject
0x1400253ef  nop     dword ptr [rax+rax+00h]
0x1400253f4  mov     dl, 1; unsigned __int8
0x1400253f6  mov     rcx, rsi; struct _PARTITION_EXTENSION *
0x1400253f9  call    ?PartitionOffset@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionOffset(_PARTITION_EXTENSION *,uchar)
0x1400253fe  cmp     rax, [rsi+0B0h]
0x140025405  jz      short loc_14002540E
0x140025407  mov     ebx, 0C00000BBh
0x14002540c  jmp     short loc_140025439
0x14002540e  cmp     dword ptr [rdi], 0FFFFFFFFh
0x140025411  mov     r9, 7FFFFFFFFFFFFFFFh
0x14002541b  jnz     short loc_140025475
0x14002541d  mov     r8, [rbx]
0x140025420  cmp     r8, r9
0x140025423  jz      short loc_140025475
0x140025425  mov     dl, 1; unsigned __int8
0x140025427  mov     rcx, rsi; struct _PARTITION_EXTENSION *
0x14002542a  call    ?PartitionLength@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionLength(_PARTITION_EXTENSION *,uchar)
0x14002542f  cmp     r8, rax
0x140025432  jb      short loc_140025465
0x140025434  mov     ebx, 0C000000Dh
0x140025439  mov     rcx, [rsi+18h]
0x14002543d  xor     edx, edx; Wait
0x14002543f  add     rcx, 38h ; '8'; Mutex
0x140025443  call    cs:__imp_KeReleaseMutex
0x14002544a  nop     dword ptr [rax+rax+00h]
0x14002544f  xor     edx, edx; PriorityBoost
0x140025451  mov     [rbp+30h], ebx
0x140025454  mov     rcx, rbp; Irp
0x140025457  call    cs:__imp_IofCompleteRequest
0x14002545e  nop     dword ptr [rax+rax+00h]
0x140025463  jmp     short loc_1400254AF
0x140025465  mov     dl, 1; unsigned __int8
0x140025467  mov     rcx, rsi; struct _PARTITION_EXTENSION *
0x14002546a  call    ?PartitionOffset@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionOffset(_PARTITION_EXTENSION *,uchar)
0x14002546f  add     rax, r8
0x140025472  mov     [rbx], rax
0x140025475  test    r14, r14
0x140025478  jz      short loc_14002548C
0x14002547a  cmp     [r14], r9
0x14002547d  jnz     short loc_14002548C
0x14002547f  mov     dl, 1; unsigned __int8
0x140025481  mov     rcx, rsi; struct _PARTITION_EXTENSION *
0x140025484  call    ?PartitionLength@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionLength(_PARTITION_EXTENSION *,uchar)
0x140025489  mov     [r14], rax
0x14002548c  mov     rcx, [rsi+18h]
0x140025490  xor     edx, edx; Wait
0x140025492  add     rcx, 38h ; '8'; Mutex
0x140025496  call    cs:__imp_KeReleaseMutex
0x14002549d  nop     dword ptr [rax+rax+00h]
0x1400254a2  mov     rdx, rbp; struct _IRP *
0x1400254a5  mov     rcx, r15; struct _DEVICE_OBJECT *
0x1400254a8  call    ?PartitionPassThrough@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionPassThrough(_DEVICE_OBJECT *,_IRP *)
0x1400254ad  mov     ebx, eax
0x1400254af  mov     eax, ebx
0x1400254b1  add     rsp, 38h
0x1400254b5  pop     r15
0x1400254b7  pop     r14
0x1400254b9  pop     rdi
0x1400254ba  pop     rsi
0x1400254bb  pop     rbp
0x1400254bc  pop     rbx
0x1400254bd  retn
```
