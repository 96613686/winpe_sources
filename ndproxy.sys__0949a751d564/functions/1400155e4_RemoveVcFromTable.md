# RemoveVcFromTable

- ea: `0x1400155e4`
- end: `0x1400156d2`
- name: `RemoveVcFromTable`
- size: `238`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140013bc0`
- `0x1400156d8`

## callees

- `0x14000757c`
- `0x1400155e4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001569b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001569b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015673`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015673`
- `NDIS!NdisAcquireRWLockWrite` at `0x140015641`
- `NDIS!NdisAcquireRWLockWrite` at `0x140015641`
- `NDIS!NdisReleaseRWLock` at `0x1400156b3`
- `NDIS!NdisReleaseRWLock` at `0x1400156b3`

## pseudocode

```c
void __fastcall RemoveVcFromTable(KSPIN_LOCK *a1, __int64 a2, __int64 a3)
{
  KSPIN_LOCK v4; // rdx
  KSPIN_LOCK **v5; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qP(WPP_GLOBAL_Control->AttachedDevice, 150, a3, a1, a1[35]);
  NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState, 0);
  *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type + 8 * a1[35]) = 0;
  --LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  KeAcquireSpinLockAtDpcLevel(a1 + 64);
  v4 = *a1;
  if ( *(KSPIN_LOCK **)(*a1 + 8) != a1 || (v5 = (KSPIN_LOCK **)a1[1], *v5 != a1) )
    __fastfail(3u);
  *v5 = (KSPIN_LOCK *)v4;
  *(_QWORD *)(v4 + 8) = v5;
  KeReleaseSpinLockFromDpcLevel(a1 + 64);
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState);
}

```

## disassembly

```asm
0x1400155e4  mov     [rsp+arg_8], rbx
0x1400155e9  push    rdi
0x1400155ea  sub     rsp, 30h
0x1400155ee  xor     eax, eax
0x1400155f0  mov     rbx, rcx
0x1400155f3  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x1400155f8  mov     [rsp+38h+LockState.Flags], al
0x1400155fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140015603  lea     rax, WPP_GLOBAL_Control
0x14001560a  cmp     rcx, rax
0x14001560d  jz      short loc_140015632
0x14001560f  cmp     byte ptr [rcx+29h], 4
0x140015613  jb      short loc_140015632
0x140015615  mov     rax, [rbx+118h]
0x14001561c  mov     edx, 96h
0x140015621  mov     rcx, [rcx+18h]
0x140015625  mov     r9, rbx
0x140015628  mov     [rsp+38h+var_18], rax
0x14001562d  call    WPP_SF_qP
0x140015632  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x140015639  lea     rdx, [rsp+38h+LockState]; LockState
0x14001563e  xor     r8d, r8d; Flags
0x140015641  call    cs:__imp_NdisAcquireRWLockWrite
0x140015648  nop     dword ptr [rax+rax+00h]
0x14001564d  mov     rcx, [rbx+118h]
0x140015654  lea     rdi, [rbx+200h]
0x14001565b  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x140015662  mov     qword ptr [rax+rcx*8], 0
0x14001566a  mov     rcx, rdi; SpinLock
0x14001566d  dec     dword ptr cs:WPP_MAIN_CB.Queue+30h
0x140015673  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001567a  nop     dword ptr [rax+rax+00h]
0x14001567f  mov     rdx, [rbx]
0x140015682  cmp     [rdx+8], rbx
0x140015686  jnz     short loc_1400156CB
0x140015688  mov     rax, [rbx+8]
0x14001568c  cmp     [rax], rbx
0x14001568f  jnz     short loc_1400156CB
0x140015691  mov     [rax], rdx
0x140015694  mov     rcx, rdi; SpinLock
0x140015697  mov     [rdx+8], rax
0x14001569b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400156a2  nop     dword ptr [rax+rax+00h]
0x1400156a7  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x1400156ae  lea     rdx, [rsp+38h+LockState]; LockState
0x1400156b3  call    cs:__imp_NdisReleaseRWLock
0x1400156ba  nop     dword ptr [rax+rax+00h]
0x1400156bf  mov     rbx, [rsp+38h+arg_8]
0x1400156c4  add     rsp, 30h
0x1400156c8  pop     rdi
0x1400156c9  retn
0x1400156cb  mov     ecx, 3
0x1400156d0  int     29h; Win8: RtlFailFast(ecx)
```
