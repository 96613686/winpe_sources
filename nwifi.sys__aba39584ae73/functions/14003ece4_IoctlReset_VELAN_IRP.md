# IoctlReset(_VELAN *,_IRP *)

- ea: `0x14003ece4`
- end: `0x14003efd8`
- name: `?IoctlReset@@YAJPEAU_VELAN@@PEAU_IRP@@@Z`
- size: `756`
- prototype: `__int64 __fastcall(struct _VELAN *, struct _IRP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140033a14`

## callees

- `0x14000a81c`
- `0x14000aa5c`
- `0x140020dc0`
- `0x140020f20`
- `0x14003464c`
- `0x14003ece4`
- `0x14003efe0`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14003eeb5`
- `ntoskrnl!IoFreeWorkItem` at `0x14003eeb5`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14003ef40`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14003ef40`
- `ntoskrnl!IoAllocateWorkItem` at `0x14003ee70`
- `ntoskrnl!IoAllocateWorkItem` at `0x14003ee70`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003ee33`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003ee33`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003eee1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003eee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003eef5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003eef5`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003ee90`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003ee90`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003eea6`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003ef50`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003eea6`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003ef50`

## pseudocode

```c
__int64 __fastcall IoctlReset(struct _VELAN *a1, _LIST_ENTRY *a2, int a3)
{
  _IO_STACK_LOCATION *Blink; // rax
  _IRP::<unnamed_type_AssociatedIrp> v6; // rbx
  __int64 v7; // r9
  unsigned int v8; // ebx
  __int64 p_MdlAddress; // rdi
  char MdlAddress; // al
  int v11; // ecx
  __int64 *v12; // rdx
  char *v13; // rax
  _LIST_ENTRY *v14; // rdi
  struct _IO_WORKITEM *WorkItem; // rbx
  int v17; // ecx
  KIRQL Irql; // [rsp+68h] [rbp+10h] BYREF

  Blink = (_IO_STACK_LOCATION *)a2[11].Blink;
  Irql = 0;
  if ( Blink->Parameters.Create.Options < 0x10 )
  {
    v8 = -1073741789;
    goto LABEL_37;
  }
  v6.MasterIrp = (_IRP *)a2[1].Blink;
  if ( !*(_DWORD *)v6.MasterIrp )
  {
    v8 = -1073741790;
    goto LABEL_37;
  }
  if ( *(_DWORD *)&v6.MasterIrp->Type != 1 )
    goto LABEL_6;
  v7 = *(unsigned int *)&v6.MasterIrp->AllocationProcessorNumber;
  if ( *(_DWORD *)&v6.MasterIrp->AllocationProcessorNumber != 1
    && (unsigned int)(*(_DWORD *)&v6.MasterIrp->AllocationProcessorNumber - 2) >= 2 )
  {
    goto LABEL_6;
  }
  if ( (_DWORD)v7 != 1 )
  {
    p_MdlAddress = (__int64)&v6.MasterIrp->MdlAddress;
    MdlAddress = (char)v6.MasterIrp->MdlAddress;
    if ( MdlAddress )
      goto LABEL_14;
    if ( BYTE1(v6.MasterIrp->MdlAddress)
      || BYTE2(v6.MasterIrp->MdlAddress)
      || BYTE3(v6.MasterIrp->MdlAddress)
      || BYTE4(v6.MasterIrp->MdlAddress) )
    {
      goto LABEL_15;
    }
    if ( BYTE5(v6.MasterIrp->MdlAddress) )
    {
LABEL_14:
      if ( (MdlAddress & 1) != 0 )
      {
LABEL_6:
        v8 = -1073741811;
        goto LABEL_37;
      }
LABEL_15:
      v11 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_l_MAC_l(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a2, a3, v7, (__int64)&v6.MasterIrp->MdlAddress);
      if ( byte_1400B2802 < 0 )
      {
        v12 = AdapterResetNewMAC;
LABEL_23:
        McTemplateK0pjub6t_EtwWriteTransfer(
          v11,
          (_DWORD)v12,
          (_DWORD)a1 + 4920,
          (_DWORD)a1,
          (__int64)&a1->gDeviceId,
          v6.MasterIrp->AllocationProcessorNumber,
          p_MdlAddress,
          BYTE6(v6.MasterIrp->MdlAddress));
        goto LABEL_24;
      }
      goto LABEL_24;
    }
  }
  p_MdlAddress = (__int64)&v6.MasterIrp->MdlAddress;
  LODWORD(v6.MasterIrp->MdlAddress) = *(_DWORD *)a1->CurrentAddress;
  WORD2(v6.MasterIrp->MdlAddress) = *(_WORD *)&a1->CurrentAddress[4];
  v11 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_89b7f4b5d0213b18cf155f9488908e89_Traceguids,
      v7,
      BYTE6(v6.MasterIrp->MdlAddress));
  if ( byte_1400B2802 < 0 )
  {
    v12 = AdapterReset;
    goto LABEL_23;
  }
LABEL_24:
  v13 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue);
  if ( v13 )
  {
    *(_QWORD *)v13 = &WPP_MAIN_CB.DeviceQueue;
    v14 = (_LIST_ENTRY *)(v13 + 16);
    *((_DWORD *)v13 + 2) = 812217207;
    *((_QWORD *)v13 + 2) = *(_QWORD *)&v6.MasterIrp->AllocationProcessorNumber;
    *((_DWORD *)v13 + 6) = HIDWORD(v6.MasterIrp->MdlAddress);
    *((_QWORD *)v13 + 4) = a1;
    WorkItem = IoAllocateWorkItem((PDEVICE_OBJECT)WPP_MAIN_CB.Queue.Wcb.DeviceContext);
    if ( WorkItem )
    {
      IoAcquireCancelSpinLock(&Irql);
      if ( !BYTE4(a2[4].Flink) )
      {
        BYTE3(a2[11].Blink->Flink) |= 1u;
        v14[1].Blink = a2;
        a2[7].Blink = v14;
        _InterlockedExchange64((volatile __int64 *)&a2[6].Blink, (__int64)&Dot11CancelIoctlReset);
        NwfBlockIrpProcessing(a1);
        _InterlockedIncrement((volatile signed __int32 *)&a1->RefCount);
        IoQueueWorkItemEx(WorkItem, Dot11DelayedIoctlReset, DelayedWorkQueue, v14);
        IoReleaseCancelSpinLock(Irql);
        return 259;
      }
      IoReleaseCancelSpinLock(Irql);
      IoFreeWorkItem(WorkItem);
      v8 = -1073741536;
    }
    else
    {
      v8 = -1073741670;
    }
    if ( v14 )
    {
      if ( v14[-1].Flink )
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v14[-1].Flink, &v14[-1]);
      else
        ExFreePoolWithTag(&v14[-1], (ULONG)v14[-1].Blink);
    }
  }
  else
  {
    v8 = -1073741670;
  }
LABEL_37:
  v17 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_89b7f4b5d0213b18cf155f9488908e89_Traceguids, v8);
  if ( (byte_1400B2803 & 1) != 0 )
    McTemplateK0pjq_EtwWriteTransfer(
      v17,
      (unsigned int)RejectResetRequest,
      (_DWORD)a1 + 4920,
      (_DWORD)a1,
      (__int64)&a1->gDeviceId,
      v8);
  return v8;
}

```

## disassembly

```asm
0x14003ece4  mov     [rsp+arg_0], rbx
0x14003ece9  mov     [rsp+arg_10], rbp
0x14003ecee  push    rsi
0x14003ecef  push    rdi
0x14003ecf0  push    r12
0x14003ecf2  sub     rsp, 40h
0x14003ecf6  mov     rax, [rdx+0B8h]
0x14003ecfd  lea     r12, WPP_GLOBAL_Control
0x14003ed04  mov     [rsp+58h+Irql], 0
0x14003ed09  mov     rbp, rdx
0x14003ed0c  mov     rsi, rcx
0x14003ed0f  cmp     dword ptr [rax+10h], 10h
0x14003ed13  jb      loc_14003EF71
0x14003ed19  mov     rbx, [rdx+18h]
0x14003ed1d  mov     ecx, [rbx]
0x14003ed1f  test    ecx, ecx
0x14003ed21  jz      loc_14003EF6A
0x14003ed27  cmp     ecx, 1
0x14003ed2a  jnz     short loc_14003ED42
0x14003ed2c  mov     r9d, [rbx+4]
0x14003ed30  mov     ecx, r9d
0x14003ed33  sub     ecx, 1
0x14003ed36  jz      short loc_14003ED4C
0x14003ed38  sub     ecx, 1
0x14003ed3b  jz      short loc_14003ED4C
0x14003ed3d  cmp     ecx, 1
0x14003ed40  jz      short loc_14003ED4C
0x14003ed42  mov     ebx, 0C000000Dh
0x14003ed47  jmp     loc_14003EF76
0x14003ed4c  cmp     r9d, 1
0x14003ed50  jz      short loc_14003EDB1
0x14003ed52  lea     rdi, [rbx+8]
0x14003ed56  mov     al, [rdi]
0x14003ed58  test    al, al
0x14003ed5a  jnz     short loc_14003ED75
0x14003ed5c  cmp     [rbx+9], al
0x14003ed5f  jnz     short loc_14003ED79
0x14003ed61  cmp     [rbx+0Ah], al
0x14003ed64  jnz     short loc_14003ED79
0x14003ed66  cmp     [rbx+0Bh], al
0x14003ed69  jnz     short loc_14003ED79
0x14003ed6b  cmp     [rbx+0Ch], al
0x14003ed6e  jnz     short loc_14003ED79
0x14003ed70  cmp     [rbx+0Dh], al
0x14003ed73  jz      short loc_14003EDB1
0x14003ed75  test    al, 1
0x14003ed77  jnz     short loc_14003ED42
0x14003ed79  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed80  cmp     rcx, r12
0x14003ed83  jz      short loc_14003ED9B
0x14003ed85  movzx   eax, byte ptr [rbx+0Eh]
0x14003ed89  mov     rcx, [rcx+18h]
0x14003ed8d  mov     [rsp+58h+var_30], eax
0x14003ed91  mov     [rsp+58h+var_38], rdi
0x14003ed96  call    WPP_SF_l_MAC_l
0x14003ed9b  cmp     cs:byte_1400B2802, 0
0x14003eda2  jge     loc_14003EE29
0x14003eda8  lea     rdx, AdapterResetNewMAC
0x14003edaf  jmp     short loc_14003EE01
0x14003edb1  mov     eax, [rsi+132Ah]
0x14003edb7  lea     rdi, [rbx+8]
0x14003edbb  mov     [rdi], eax
0x14003edbd  movzx   eax, word ptr [rsi+132Eh]
0x14003edc4  mov     [rdi+4], ax
0x14003edc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003edcf  cmp     rcx, r12
0x14003edd2  jz      short loc_14003EDF1
0x14003edd4  movzx   eax, byte ptr [rbx+0Eh]
0x14003edd8  lea     r8, WPP_89b7f4b5d0213b18cf155f9488908e89_Traceguids
0x14003eddf  mov     rcx, [rcx+18h]
0x14003ede3  mov     edx, 0Dh
0x14003ede8  mov     dword ptr [rsp+58h+var_38], eax
0x14003edec  call    WPP_SF_Dd
0x14003edf1  cmp     cs:byte_1400B2802, 0
0x14003edf8  jge     short loc_14003EE29
0x14003edfa  lea     rdx, AdapterReset
0x14003ee01  movzx   eax, byte ptr [rbx+0Eh]
0x14003ee05  lea     r8, [rsi+1338h]
0x14003ee0c  mov     [rsp+58h+var_20], eax
0x14003ee10  mov     r9, rsi
0x14003ee13  mov     al, [rbx+4]
0x14003ee16  mov     [rsp+58h+var_28], rdi
0x14003ee1b  mov     byte ptr [rsp+58h+var_30], al
0x14003ee1f  mov     [rsp+58h+var_38], r8
0x14003ee24  call    McTemplateK0pjub6t_EtwWriteTransfer
0x14003ee29  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14003ee30  mov     rcx, rdi; Lookaside
0x14003ee33  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003ee3a  nop     dword ptr [rax+rax+00h]
0x14003ee3f  test    rax, rax
0x14003ee42  jz      loc_14003EF63
0x14003ee48  mov     [rax], rdi
0x14003ee4b  lea     rdi, [rax+10h]
0x14003ee4f  mov     dword ptr [rax+8], 30697377h
0x14003ee56  movsd   xmm0, qword ptr [rbx+4]
0x14003ee5b  movsd   qword ptr [rdi], xmm0
0x14003ee5f  mov     eax, [rbx+0Ch]
0x14003ee62  mov     [rdi+8], eax
0x14003ee65  mov     [rdi+10h], rsi
0x14003ee69  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; DeviceObject
0x14003ee70  call    cs:__imp_IoAllocateWorkItem
0x14003ee77  nop     dword ptr [rax+rax+00h]
0x14003ee7c  mov     rbx, rax
0x14003ee7f  test    rax, rax
0x14003ee82  jnz     short loc_14003EE8B
0x14003ee84  mov     ebx, 0C000009Ah
0x14003ee89  jmp     short loc_14003EEC6
0x14003ee8b  lea     rcx, [rsp+58h+Irql]; Irql
0x14003ee90  call    cs:__imp_IoAcquireCancelSpinLock
0x14003ee97  nop     dword ptr [rax+rax+00h]
0x14003ee9c  cmp     byte ptr [rbp+44h], 0
0x14003eea0  jz      short loc_14003EF03
0x14003eea2  mov     cl, [rsp+58h+Irql]; Irql
0x14003eea6  call    cs:__imp_IoReleaseCancelSpinLock
0x14003eead  nop     dword ptr [rax+rax+00h]
0x14003eeb2  mov     rcx, rbx; IoWorkItem
0x14003eeb5  call    cs:__imp_IoFreeWorkItem
0x14003eebc  nop     dword ptr [rax+rax+00h]
0x14003eec1  mov     ebx, 0C0000120h
0x14003eec6  test    rdi, rdi
0x14003eec9  jz      loc_14003EF76
0x14003eecf  lea     rcx, [rdi-10h]; P
0x14003eed3  mov     rax, [rcx]
0x14003eed6  test    rax, rax
0x14003eed9  jz      short loc_14003EEF2
0x14003eedb  mov     rdx, rcx; Entry
0x14003eede  mov     rcx, rax; Lookaside
0x14003eee1  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003eee8  nop     dword ptr [rax+rax+00h]
0x14003eeed  jmp     loc_14003EF76
0x14003eef2  mov     edx, [rcx+8]; Tag
0x14003eef5  call    cs:__imp_ExFreePoolWithTag
0x14003eefc  nop     dword ptr [rax+rax+00h]
0x14003ef01  jmp     short loc_14003EF76
0x14003ef03  mov     rax, [rbp+0B8h]
0x14003ef0a  mov     rcx, rsi; struct _VELAN *
0x14003ef0d  or      byte ptr [rax+3], 1
0x14003ef11  lea     rax, Dot11CancelIoctlReset
0x14003ef18  mov     [rdi+18h], rbp
0x14003ef1c  mov     [rbp+78h], rdi
0x14003ef20  xchg    rax, [rbp+68h]
0x14003ef24  call    ?NwfBlockIrpProcessing@@YAXPEAU_VELAN@@@Z; NwfBlockIrpProcessing(_VELAN *)
0x14003ef29  lock inc dword ptr [rsi+1Ch]
0x14003ef2d  mov     r9, rdi; Context
0x14003ef30  lea     rdx, ?Dot11DelayedIoctlReset@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x14003ef37  mov     r8d, 1; QueueType
0x14003ef3d  mov     rcx, rbx; IoWorkItem
0x14003ef40  call    cs:__imp_IoQueueWorkItemEx
0x14003ef47  nop     dword ptr [rax+rax+00h]
0x14003ef4c  mov     cl, [rsp+58h+Irql]; Irql
0x14003ef50  call    cs:__imp_IoReleaseCancelSpinLock
0x14003ef57  nop     dword ptr [rax+rax+00h]
0x14003ef5c  mov     eax, 103h
0x14003ef61  jmp     short loc_14003EFC4
0x14003ef63  mov     ebx, 0C000009Ah
0x14003ef68  jmp     short loc_14003EF76
0x14003ef6a  mov     ebx, 0C0000022h
0x14003ef6f  jmp     short loc_14003EF76
0x14003ef71  mov     ebx, 0C0000023h
0x14003ef76  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ef7d  cmp     rcx, r12
0x14003ef80  jz      short loc_14003EF9A
0x14003ef82  mov     rcx, [rcx+18h]
0x14003ef86  lea     r8, WPP_89b7f4b5d0213b18cf155f9488908e89_Traceguids
0x14003ef8d  mov     edx, 0Eh
0x14003ef92  mov     r9d, ebx
0x14003ef95  call    WPP_SF_d
0x14003ef9a  test    cs:byte_1400B2803, 1
0x14003efa1  jz      short loc_14003EFC2
0x14003efa3  lea     r8, [rsi+1338h]
0x14003efaa  mov     [rsp+58h+var_30], ebx
0x14003efae  mov     r9, rsi
0x14003efb1  mov     [rsp+58h+var_38], r8
0x14003efb6  lea     rdx, RejectResetRequest
0x14003efbd  call    McTemplateK0pjq_EtwWriteTransfer
0x14003efc2  mov     eax, ebx
0x14003efc4  mov     rbx, [rsp+58h+arg_0]
0x14003efc9  mov     rbp, [rsp+58h+arg_10]
0x14003efce  add     rsp, 40h
0x14003efd2  pop     r12
0x14003efd4  pop     rdi
0x14003efd5  pop     rsi
0x14003efd6  retn
```
