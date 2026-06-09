# IoctlReset(_VELAN *,_IRP *)

- ea: `0x14003eac4`
- end: `0x14003edb8`
- name: `?IoctlReset@@YAJPEAU_VELAN@@PEAU_IRP@@@Z`
- size: `756`
- prototype: `__int64 __fastcall(struct _VELAN *, struct _IRP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400337f4`

## callees

- `0x14000a82c`
- `0x14000aa6c`
- `0x140020dc0`
- `0x140020f20`
- `0x14003442c`
- `0x14003eac4`
- `0x14003edc0`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14003ec95`
- `ntoskrnl!IoFreeWorkItem` at `0x14003ec95`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14003ed20`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14003ed20`
- `ntoskrnl!IoAllocateWorkItem` at `0x14003ec50`
- `ntoskrnl!IoAllocateWorkItem` at `0x14003ec50`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003ec13`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003ec13`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ecc1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ecc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ecd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ecd5`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003ec70`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003ec70`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003ec86`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003ed30`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003ec86`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003ed30`

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
  __int64 v18; // [rsp+28h] [rbp-30h]
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
      if ( byte_1400AF802 < 0 )
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
  if ( byte_1400AF802 < 0 )
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
  if ( (byte_1400AF803 & 1) != 0 )
  {
    LODWORD(v18) = v8;
    McTemplateK0pjq_EtwWriteTransfer(
      v17,
      (unsigned int)RejectResetRequest,
      (_DWORD)a1 + 4920,
      (_DWORD)a1,
      (__int64)&a1->gDeviceId,
      v18);
  }
  return v8;
}

```

## disassembly

```asm
0x14003eac4  mov     [rsp+arg_0], rbx
0x14003eac9  mov     [rsp+arg_10], rbp
0x14003eace  push    rsi
0x14003eacf  push    rdi
0x14003ead0  push    r12
0x14003ead2  sub     rsp, 40h
0x14003ead6  mov     rax, [rdx+0B8h]
0x14003eadd  lea     r12, WPP_GLOBAL_Control
0x14003eae4  mov     [rsp+58h+Irql], 0
0x14003eae9  mov     rbp, rdx
0x14003eaec  mov     rsi, rcx
0x14003eaef  cmp     dword ptr [rax+10h], 10h
0x14003eaf3  jb      loc_14003ED51
0x14003eaf9  mov     rbx, [rdx+18h]
0x14003eafd  mov     ecx, [rbx]
0x14003eaff  test    ecx, ecx
0x14003eb01  jz      loc_14003ED4A
0x14003eb07  cmp     ecx, 1
0x14003eb0a  jnz     short loc_14003EB22
0x14003eb0c  mov     r9d, [rbx+4]
0x14003eb10  mov     ecx, r9d
0x14003eb13  sub     ecx, 1
0x14003eb16  jz      short loc_14003EB2C
0x14003eb18  sub     ecx, 1
0x14003eb1b  jz      short loc_14003EB2C
0x14003eb1d  cmp     ecx, 1
0x14003eb20  jz      short loc_14003EB2C
0x14003eb22  mov     ebx, 0C000000Dh
0x14003eb27  jmp     loc_14003ED56
0x14003eb2c  cmp     r9d, 1
0x14003eb30  jz      short loc_14003EB91
0x14003eb32  lea     rdi, [rbx+8]
0x14003eb36  mov     al, [rdi]
0x14003eb38  test    al, al
0x14003eb3a  jnz     short loc_14003EB55
0x14003eb3c  cmp     [rbx+9], al
0x14003eb3f  jnz     short loc_14003EB59
0x14003eb41  cmp     [rbx+0Ah], al
0x14003eb44  jnz     short loc_14003EB59
0x14003eb46  cmp     [rbx+0Bh], al
0x14003eb49  jnz     short loc_14003EB59
0x14003eb4b  cmp     [rbx+0Ch], al
0x14003eb4e  jnz     short loc_14003EB59
0x14003eb50  cmp     [rbx+0Dh], al
0x14003eb53  jz      short loc_14003EB91
0x14003eb55  test    al, 1
0x14003eb57  jnz     short loc_14003EB22
0x14003eb59  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eb60  cmp     rcx, r12
0x14003eb63  jz      short loc_14003EB7B
0x14003eb65  movzx   eax, byte ptr [rbx+0Eh]
0x14003eb69  mov     rcx, [rcx+18h]
0x14003eb6d  mov     dword ptr [rsp+58h+var_30], eax
0x14003eb71  mov     [rsp+58h+var_38], rdi
0x14003eb76  call    WPP_SF_l_MAC_l
0x14003eb7b  cmp     cs:byte_1400AF802, 0
0x14003eb82  jge     loc_14003EC09
0x14003eb88  lea     rdx, AdapterResetNewMAC
0x14003eb8f  jmp     short loc_14003EBE1
0x14003eb91  mov     eax, [rsi+132Ah]
0x14003eb97  lea     rdi, [rbx+8]
0x14003eb9b  mov     [rdi], eax
0x14003eb9d  movzx   eax, word ptr [rsi+132Eh]
0x14003eba4  mov     [rdi+4], ax
0x14003eba8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ebaf  cmp     rcx, r12
0x14003ebb2  jz      short loc_14003EBD1
0x14003ebb4  movzx   eax, byte ptr [rbx+0Eh]
0x14003ebb8  lea     r8, WPP_89b7f4b5d0213b18cf155f9488908e89_Traceguids
0x14003ebbf  mov     rcx, [rcx+18h]
0x14003ebc3  mov     edx, 0Dh
0x14003ebc8  mov     dword ptr [rsp+58h+var_38], eax
0x14003ebcc  call    WPP_SF_Dd
0x14003ebd1  cmp     cs:byte_1400AF802, 0
0x14003ebd8  jge     short loc_14003EC09
0x14003ebda  lea     rdx, AdapterReset
0x14003ebe1  movzx   eax, byte ptr [rbx+0Eh]
0x14003ebe5  lea     r8, [rsi+1338h]
0x14003ebec  mov     [rsp+58h+var_20], eax
0x14003ebf0  mov     r9, rsi
0x14003ebf3  mov     al, [rbx+4]
0x14003ebf6  mov     [rsp+58h+var_28], rdi
0x14003ebfb  mov     byte ptr [rsp+58h+var_30], al
0x14003ebff  mov     [rsp+58h+var_38], r8
0x14003ec04  call    McTemplateK0pjub6t_EtwWriteTransfer
0x14003ec09  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14003ec10  mov     rcx, rdi; Lookaside
0x14003ec13  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003ec1a  nop     dword ptr [rax+rax+00h]
0x14003ec1f  test    rax, rax
0x14003ec22  jz      loc_14003ED43
0x14003ec28  mov     [rax], rdi
0x14003ec2b  lea     rdi, [rax+10h]
0x14003ec2f  mov     dword ptr [rax+8], 30697377h
0x14003ec36  movsd   xmm0, qword ptr [rbx+4]
0x14003ec3b  movsd   qword ptr [rdi], xmm0
0x14003ec3f  mov     eax, [rbx+0Ch]
0x14003ec42  mov     [rdi+8], eax
0x14003ec45  mov     [rdi+10h], rsi
0x14003ec49  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; DeviceObject
0x14003ec50  call    cs:__imp_IoAllocateWorkItem
0x14003ec57  nop     dword ptr [rax+rax+00h]
0x14003ec5c  mov     rbx, rax
0x14003ec5f  test    rax, rax
0x14003ec62  jnz     short loc_14003EC6B
0x14003ec64  mov     ebx, 0C000009Ah
0x14003ec69  jmp     short loc_14003ECA6
0x14003ec6b  lea     rcx, [rsp+58h+Irql]; Irql
0x14003ec70  call    cs:__imp_IoAcquireCancelSpinLock
0x14003ec77  nop     dword ptr [rax+rax+00h]
0x14003ec7c  cmp     byte ptr [rbp+44h], 0
0x14003ec80  jz      short loc_14003ECE3
0x14003ec82  mov     cl, [rsp+58h+Irql]; Irql
0x14003ec86  call    cs:__imp_IoReleaseCancelSpinLock
0x14003ec8d  nop     dword ptr [rax+rax+00h]
0x14003ec92  mov     rcx, rbx; IoWorkItem
0x14003ec95  call    cs:__imp_IoFreeWorkItem
0x14003ec9c  nop     dword ptr [rax+rax+00h]
0x14003eca1  mov     ebx, 0C0000120h
0x14003eca6  test    rdi, rdi
0x14003eca9  jz      loc_14003ED56
0x14003ecaf  lea     rcx, [rdi-10h]; P
0x14003ecb3  mov     rax, [rcx]
0x14003ecb6  test    rax, rax
0x14003ecb9  jz      short loc_14003ECD2
0x14003ecbb  mov     rdx, rcx; Entry
0x14003ecbe  mov     rcx, rax; Lookaside
0x14003ecc1  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003ecc8  nop     dword ptr [rax+rax+00h]
0x14003eccd  jmp     loc_14003ED56
0x14003ecd2  mov     edx, [rcx+8]; Tag
0x14003ecd5  call    cs:__imp_ExFreePoolWithTag
0x14003ecdc  nop     dword ptr [rax+rax+00h]
0x14003ece1  jmp     short loc_14003ED56
0x14003ece3  mov     rax, [rbp+0B8h]
0x14003ecea  mov     rcx, rsi; struct _VELAN *
0x14003eced  or      byte ptr [rax+3], 1
0x14003ecf1  lea     rax, Dot11CancelIoctlReset
0x14003ecf8  mov     [rdi+18h], rbp
0x14003ecfc  mov     [rbp+78h], rdi
0x14003ed00  xchg    rax, [rbp+68h]
0x14003ed04  call    ?NwfBlockIrpProcessing@@YAXPEAU_VELAN@@@Z; NwfBlockIrpProcessing(_VELAN *)
0x14003ed09  lock inc dword ptr [rsi+1Ch]
0x14003ed0d  mov     r9, rdi; Context
0x14003ed10  lea     rdx, ?Dot11DelayedIoctlReset@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x14003ed17  mov     r8d, 1; QueueType
0x14003ed1d  mov     rcx, rbx; IoWorkItem
0x14003ed20  call    cs:__imp_IoQueueWorkItemEx
0x14003ed27  nop     dword ptr [rax+rax+00h]
0x14003ed2c  mov     cl, [rsp+58h+Irql]; Irql
0x14003ed30  call    cs:__imp_IoReleaseCancelSpinLock
0x14003ed37  nop     dword ptr [rax+rax+00h]
0x14003ed3c  mov     eax, 103h
0x14003ed41  jmp     short loc_14003EDA4
0x14003ed43  mov     ebx, 0C000009Ah
0x14003ed48  jmp     short loc_14003ED56
0x14003ed4a  mov     ebx, 0C0000022h
0x14003ed4f  jmp     short loc_14003ED56
0x14003ed51  mov     ebx, 0C0000023h
0x14003ed56  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed5d  cmp     rcx, r12
0x14003ed60  jz      short loc_14003ED7A
0x14003ed62  mov     rcx, [rcx+18h]
0x14003ed66  lea     r8, WPP_89b7f4b5d0213b18cf155f9488908e89_Traceguids
0x14003ed6d  mov     edx, 0Eh
0x14003ed72  mov     r9d, ebx
0x14003ed75  call    WPP_SF_d
0x14003ed7a  test    cs:byte_1400AF803, 1
0x14003ed81  jz      short loc_14003EDA2
0x14003ed83  lea     r8, [rsi+1338h]
0x14003ed8a  mov     dword ptr [rsp+58h+var_30], ebx
0x14003ed8e  mov     r9, rsi
0x14003ed91  mov     [rsp+58h+var_38], r8
0x14003ed96  lea     rdx, RejectResetRequest
0x14003ed9d  call    McTemplateK0pjq_EtwWriteTransfer
0x14003eda2  mov     eax, ebx
0x14003eda4  mov     rbx, [rsp+58h+arg_0]
0x14003eda9  mov     rbp, [rsp+58h+arg_10]
0x14003edae  add     rsp, 40h
0x14003edb2  pop     r12
0x14003edb4  pop     rdi
0x14003edb5  pop     rsi
0x14003edb6  retn
```
