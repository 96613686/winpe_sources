# PmInvalidatePartitionTableCache(_DEVICE_EXTENSION *)

- ea: `0x14000cb34`
- end: `0x14000cc81`
- name: `?PmInvalidatePartitionTableCache@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `333`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `15`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000bbe0`
- `0x14000bc88`
- `0x14000c730`
- `0x14000dbd0`
- `0x14001c3d8`
- `0x14001d25c`
- `0x14001f5c4`
- `0x14001f650`
- `0x1400208c8`
- `0x140020afc`
- `0x140020ba8`
- `0x14002470c`
- `0x140024b3c`
- `0x140024d04`
- `0x140025ab8`

## callees

- `0x14000cb34`
- `0x140010f20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000cb8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cb8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbd4`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14000cc57`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14000cc57`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cc16`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cc16`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cb6d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cb6d`

## pseudocode

```c
void __fastcall PmInvalidatePartitionTableCache(KSPIN_LOCK *a1)
{
  KIRQL v2; // al
  void *v3; // rcx
  KIRQL v4; // si
  void *v5; // rcx
  void *v6; // rcx
  struct _DEVICE_OBJECT *v7; // rcx
  _OWORD NotificationStructure[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+40h] [rbp-18h]

  memset(NotificationStructure, 0, sizeof(NotificationStructure));
  v9 = 0;
  v2 = KeAcquireSpinLockRaiseToDpc(a1 + 14);
  v3 = (void *)a1[142];
  v4 = v2;
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    a1[142] = 0;
  }
  v5 = (void *)a1[141];
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0);
    a1[141] = 0;
  }
  v6 = (void *)a1[138];
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    a1[138] = 0;
    *((_DWORD *)a1 + 129) &= ~8u;
  }
  *((_DWORD *)a1 + 278) = 0;
  a1[140] = 0;
  KeReleaseSpinLock(a1 + 14, v4);
  v7 = (struct _DEVICE_OBJECT *)a1[3];
  LODWORD(NotificationStructure[0]) = 2359297;
  *((_QWORD *)&NotificationStructure[1] + 1) = 0;
  *(GUID *)((char *)NotificationStructure + 4) = GUID_IO_DISK_LAYOUT_CHANGE;
  LODWORD(v9) = -1;
  IoReportTargetDeviceChangeAsynchronous(v7, NotificationStructure, 0, 0);
}

```

## disassembly

```asm
0x14000cb34  mov     [rsp+arg_8], rbx
0x14000cb39  mov     [rsp+arg_10], rsi
0x14000cb3e  push    rdi
0x14000cb3f  sub     rsp, 50h
0x14000cb43  mov     rax, cs:__security_cookie
0x14000cb4a  xor     rax, rsp
0x14000cb4d  mov     [rsp+58h+var_10], rax
0x14000cb52  xorps   xmm0, xmm0
0x14000cb55  mov     rbx, rcx
0x14000cb58  xor     eax, eax
0x14000cb5a  add     rcx, 70h ; 'p'; SpinLock
0x14000cb5e  movups  [rsp+58h+NotificationStructure], xmm0
0x14000cb63  mov     [rsp+58h+var_18], rax
0x14000cb68  movups  [rsp+58h+var_28], xmm0
0x14000cb6d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cb74  nop     dword ptr [rax+rax+00h]
0x14000cb79  mov     rcx, [rbx+470h]; P
0x14000cb80  mov     sil, al
0x14000cb83  test    rcx, rcx
0x14000cb86  jz      short loc_14000CBA1
0x14000cb88  xor     edx, edx; Tag
0x14000cb8a  call    cs:__imp_ExFreePoolWithTag
0x14000cb91  nop     dword ptr [rax+rax+00h]
0x14000cb96  mov     qword ptr [rbx+470h], 0
0x14000cba1  mov     rcx, [rbx+468h]; P
0x14000cba8  test    rcx, rcx
0x14000cbab  jz      short loc_14000CBC6
0x14000cbad  xor     edx, edx; Tag
0x14000cbaf  call    cs:__imp_ExFreePoolWithTag
0x14000cbb6  nop     dword ptr [rax+rax+00h]
0x14000cbbb  mov     qword ptr [rbx+468h], 0
0x14000cbc6  mov     rcx, [rbx+450h]; P
0x14000cbcd  test    rcx, rcx
0x14000cbd0  jz      short loc_14000CBFA
0x14000cbd2  xor     edx, edx; Tag
0x14000cbd4  call    cs:__imp_ExFreePoolWithTag
0x14000cbdb  nop     dword ptr [rax+rax+00h]
0x14000cbe0  mov     qword ptr [rbx+450h], 0
0x14000cbeb  mov     eax, [rbx+204h]
0x14000cbf1  and     eax, 0FFFFFFF7h
0x14000cbf4  mov     [rbx+204h], eax
0x14000cbfa  mov     dl, sil; NewIrql
0x14000cbfd  mov     dword ptr [rbx+458h], 0
0x14000cc07  lea     rcx, [rbx+70h]; SpinLock
0x14000cc0b  mov     qword ptr [rbx+460h], 0
0x14000cc16  call    cs:__imp_KeReleaseSpinLock
0x14000cc1d  nop     dword ptr [rax+rax+00h]
0x14000cc22  movups  xmm0, xmmword ptr cs:GUID_IO_DISK_LAYOUT_CHANGE.Data1
0x14000cc29  mov     rcx, [rbx+18h]; PhysicalDeviceObject
0x14000cc2d  lea     rdx, [rsp+58h+NotificationStructure]; NotificationStructure
0x14000cc32  xor     r9d, r9d; Context
0x14000cc35  mov     dword ptr [rsp+58h+NotificationStructure], 240001h
0x14000cc3d  xor     r8d, r8d; Callback
0x14000cc40  mov     qword ptr [rsp+58h+var_28+8], 0
0x14000cc49  movdqu  [rsp+58h+NotificationStructure+4], xmm0
0x14000cc4f  mov     dword ptr [rsp+58h+var_18], 0FFFFFFFFh
0x14000cc57  call    cs:__imp_IoReportTargetDeviceChangeAsynchronous
0x14000cc5e  nop     dword ptr [rax+rax+00h]
0x14000cc63  mov     rcx, [rsp+58h+var_10]
0x14000cc68  xor     rcx, rsp; StackCookie
0x14000cc6b  call    __security_check_cookie
0x14000cc70  mov     rbx, [rsp+58h+arg_8]
0x14000cc75  mov     rsi, [rsp+58h+arg_10]
0x14000cc7a  add     rsp, 50h
0x14000cc7e  pop     rdi
0x14000cc7f  retn
```
