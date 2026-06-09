# InsertVcInTable

- ea: `0x140010f64`
- end: `0x14001118d`
- name: `InsertVcInTable`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f490`
- `0x140013bc0`

## callees

- `0x140001bc8`
- `0x14000757c`
- `0x1400081c0`
- `0x140010f64`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400110f3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400110f3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140011087`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140011087`
- `ntoskrnl!ExAllocatePool2` at `0x140010fc9`
- `ntoskrnl!ExAllocatePool2` at `0x140010fc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001101f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001101f`
- `NDIS!NdisAcquireRWLockWrite` at `0x140010f93`
- `NDIS!NdisAcquireRWLockWrite` at `0x140010f93`
- `NDIS!NdisReleaseRWLock` at `0x140010fe9`
- `NDIS!NdisReleaseRWLock` at `0x14001113a`
- `NDIS!NdisReleaseRWLock` at `0x140010fe9`
- `NDIS!NdisReleaseRWLock` at `0x14001113a`

## pseudocode

```c
bool __fastcall InsertVcInTable(__int64 a1)
{
  unsigned int DeviceObject_high; // r8d
  void *Pool2; // rax
  void *v4; // rdi
  __int64 CurrentIrp_low; // rdx
  __int64 v7; // rsi
  unsigned int v8; // edi
  _QWORD *v9; // rax
  __int64 v10; // r8
  bool v11; // zf
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState, 0);
  DeviceObject_high = HIDWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) == HIDWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) )
  {
    Pool2 = (void *)ExAllocatePool2(
                      64,
                      (unsigned int)(8
                                   * (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject)
                                    + (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) >> 1))),
                      3299408);
    v4 = Pool2;
    if ( !Pool2 )
    {
      NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState);
      return 0;
    }
    memmove(Pool2, *(const void **)&WPP_MAIN_CB.DeviceQueue.Type, 8LL * HIDWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject));
    ExFreePoolWithTag(*(PVOID *)&WPP_MAIN_CB.DeviceQueue.Type, 0);
    DeviceObject_high = (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) >> 1) + HIDWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject);
    *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = v4;
    HIDWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) = DeviceObject_high;
  }
  CurrentIrp_low = LODWORD(WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
  v7 = LODWORD(WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
  v8 = DeviceObject_high;
  while ( *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type + 8 * CurrentIrp_low) )
  {
    if ( !--v8 )
      goto LABEL_14;
    CurrentIrp_low = ((int)CurrentIrp_low + 1) % DeviceObject_high;
    v7 = (unsigned int)CurrentIrp_low;
  }
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 512));
  *(_QWORD *)(a1 + 280) = v7;
  *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type + 8 * v7) = a1;
  v9 = *(_QWORD **)&WPP_MAIN_CB.AlignmentRequirement;
  if ( **(struct _DEVICE_OBJECT ***)&WPP_MAIN_CB.AlignmentRequirement != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
    __fastfail(3u);
  *(_QWORD *)a1 = &WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
  *(_QWORD *)(a1 + 8) = v9;
  *v9 = a1;
  ++LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement = a1;
  LODWORD(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) = (unsigned int)(LODWORD(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) + 1)
                                            % HIDWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  *(_DWORD *)(a1 + 32) |= 2u;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 512));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qP(WPP_GLOBAL_Control->AttachedDevice, 148, v10, a1, *(_QWORD *)(a1 + 280));
LABEL_14:
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState);
  v11 = v8 == 0;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 149, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids, a1);
    v11 = 1;
  }
  return !v11;
}

```

## disassembly

```asm
0x140010f64  mov     [rsp+arg_0], rbx
0x140010f69  mov     [rsp+arg_10], rbp
0x140010f6e  push    rsi
0x140010f6f  push    rdi
0x140010f70  push    r14
0x140010f72  sub     rsp, 30h
0x140010f76  xor     eax, eax
0x140010f78  lea     rdx, [rsp+48h+LockState]; LockState
0x140010f7d  mov     rbx, rcx
0x140010f80  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140010f85  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x140010f8c  xor     r8d, r8d; Flags
0x140010f8f  mov     [rsp+48h+LockState.Flags], al
0x140010f93  call    cs:__imp_NdisAcquireRWLockWrite
0x140010f9a  nop     dword ptr [rax+rax+00h]
0x140010f9f  mov     r8d, dword ptr cs:WPP_MAIN_CB.Queue+34h
0x140010fa6  cmp     dword ptr cs:WPP_MAIN_CB.Queue+30h, r8d
0x140010fad  jnz     loc_140011048
0x140010fb3  mov     edx, r8d
0x140010fb6  mov     ecx, 40h ; '@'
0x140010fbb  shr     edx, 1
0x140010fbd  add     edx, r8d
0x140010fc0  mov     r8d, 325850h
0x140010fc6  shl     edx, 3
0x140010fc9  call    cs:__imp_ExAllocatePool2
0x140010fd0  nop     dword ptr [rax+rax+00h]
0x140010fd5  mov     rdi, rax
0x140010fd8  test    rax, rax
0x140010fdb  jnz     short loc_140010FFC
0x140010fdd  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x140010fe4  lea     rdx, [rsp+48h+LockState]; LockState
0x140010fe9  call    cs:__imp_NdisReleaseRWLock
0x140010ff0  nop     dword ptr [rax+rax+00h]
0x140010ff5  xor     al, al
0x140010ff7  jmp     loc_140011179
0x140010ffc  mov     r8d, dword ptr cs:WPP_MAIN_CB.Queue+34h
0x140011003  mov     rcx, rdi; void *
0x140011006  mov     rdx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type; Src
0x14001100d  shl     r8, 3; Size
0x140011011  call    memmove
0x140011016  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type; P
0x14001101d  xor     edx, edx; Tag
0x14001101f  call    cs:__imp_ExFreePoolWithTag
0x140011026  nop     dword ptr [rax+rax+00h]
0x14001102b  mov     r8d, dword ptr cs:WPP_MAIN_CB.Queue+34h
0x140011032  mov     eax, r8d
0x140011035  shr     eax, 1
0x140011037  add     r8d, eax
0x14001103a  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, rdi
0x140011041  mov     dword ptr cs:WPP_MAIN_CB.Queue+34h, r8d
0x140011048  mov     edx, dword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001104e  lea     r14, WPP_GLOBAL_Control
0x140011055  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x14001105c  mov     esi, edx
0x14001105e  mov     edi, r8d
0x140011061  jmp     short loc_140011076
0x140011063  add     edi, 0FFFFFFFFh
0x140011066  jz      loc_14001112E
0x14001106c  lea     eax, [rdx+1]
0x14001106f  xor     edx, edx
0x140011071  div     r8d
0x140011074  mov     esi, edx
0x140011076  cmp     qword ptr [rcx+rdx*8], 0
0x14001107b  jnz     short loc_140011063
0x14001107d  lea     rbp, [rbx+200h]
0x140011084  mov     rcx, rbp; SpinLock
0x140011087  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001108e  nop     dword ptr [rax+rax+00h]
0x140011093  mov     [rbx+118h], rsi
0x14001109a  lea     rcx, WPP_MAIN_CB.Queue+40h
0x1400110a1  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x1400110a8  mov     [rax+rsi*8], rbx
0x1400110ac  mov     rax, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x1400110b3  cmp     [rax], rcx
0x1400110b6  jz      short loc_1400110BF
0x1400110b8  mov     ecx, 3
0x1400110bd  int     29h; Win8: RtlFailFast(ecx)
0x1400110bf  mov     [rbx], rcx
0x1400110c2  xor     edx, edx
0x1400110c4  mov     [rbx+8], rax
0x1400110c8  mov     rcx, rbp; SpinLock
0x1400110cb  mov     [rax], rbx
0x1400110ce  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400110d4  inc     dword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400110da  inc     eax
0x1400110dc  mov     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, rbx
0x1400110e3  div     dword ptr cs:WPP_MAIN_CB.Queue+34h
0x1400110e9  mov     dword ptr cs:WPP_MAIN_CB.Queue+38h, edx
0x1400110ef  or      dword ptr [rbx+20h], 2
0x1400110f3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400110fa  nop     dword ptr [rax+rax+00h]
0x1400110ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140011106  cmp     rcx, r14
0x140011109  jz      short loc_14001112E
0x14001110b  cmp     byte ptr [rcx+29h], 4
0x14001110f  jb      short loc_14001112E
0x140011111  mov     rax, [rbx+118h]
0x140011118  mov     edx, 94h
0x14001111d  mov     rcx, [rcx+18h]
0x140011121  mov     r9, rbx
0x140011124  mov     [rsp+48h+var_28], rax
0x140011129  call    WPP_SF_qP
0x14001112e  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x140011135  lea     rdx, [rsp+48h+LockState]; LockState
0x14001113a  call    cs:__imp_NdisReleaseRWLock
0x140011141  nop     dword ptr [rax+rax+00h]
0x140011146  test    edi, edi
0x140011148  jnz     short loc_140011176
0x14001114a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011151  cmp     rcx, r14
0x140011154  jz      short loc_140011174
0x140011156  cmp     byte ptr [rcx+29h], 4
0x14001115a  jb      short loc_140011174
0x14001115c  mov     rcx, [rcx+18h]
0x140011160  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140011167  mov     edx, 95h
0x14001116c  mov     r9, rbx
0x14001116f  call    WPP_SF_q
0x140011174  test    edi, edi
0x140011176  setnz   al
0x140011179  mov     rbx, [rsp+48h+arg_0]
0x14001117e  mov     rbp, [rsp+48h+arg_10]
0x140011183  add     rsp, 30h
0x140011187  pop     r14
0x140011189  pop     rdi
0x14001118a  pop     rsi
0x14001118b  retn
```
