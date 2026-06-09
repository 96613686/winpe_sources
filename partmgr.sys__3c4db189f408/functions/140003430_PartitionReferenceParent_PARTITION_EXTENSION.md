# PartitionReferenceParent(_PARTITION_EXTENSION *)

- ea: `0x140003430`
- end: `0x140003495`
- name: `?PartitionReferenceParent@@YAPEAU_DEVICE_OBJECT@@PEAU_PARTITION_EXTENSION@@@Z`
- size: `101`
- prototype: `struct _DEVICE_OBJECT *__fastcall(struct _PARTITION_EXTENSION *)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400030c0`
- `0x140003110`
- `0x14001c08c`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14000345f`
- `ntoskrnl!ObfReferenceObject` at `0x14000345f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003475`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003475`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000344a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000344a`

## pseudocode

```c
struct _DEVICE_OBJECT *__fastcall PartitionReferenceParent(struct _PARTITION_EXTENSION *a1)
{
  KIRQL v2; // al
  void *v3; // rdi
  KIRQL v4; // bl

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*((_QWORD *)a1 + 3) + 112LL));
  v3 = (void *)*((_QWORD *)a1 + 2);
  v4 = v2;
  ObfReferenceObject(v3);
  KeReleaseSpinLock((PKSPIN_LOCK)(*((_QWORD *)a1 + 3) + 112LL), v4);
  return (struct _DEVICE_OBJECT *)v3;
}

```

## disassembly

```asm
0x140003430  mov     [rsp+arg_0], rbx
0x140003435  mov     [rsp+arg_8], rsi
0x14000343a  push    rdi
0x14000343b  sub     rsp, 20h
0x14000343f  mov     rsi, rcx
0x140003442  mov     rcx, [rcx+18h]
0x140003446  add     rcx, 70h ; 'p'; SpinLock
0x14000344a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003451  nop     dword ptr [rax+rax+00h]
0x140003456  mov     rdi, [rsi+10h]
0x14000345a  mov     bl, al
0x14000345c  mov     rcx, rdi; Object
0x14000345f  call    cs:__imp_ObfReferenceObject
0x140003466  nop     dword ptr [rax+rax+00h]
0x14000346b  mov     rcx, [rsi+18h]
0x14000346f  mov     dl, bl; NewIrql
0x140003471  add     rcx, 70h ; 'p'; SpinLock
0x140003475  call    cs:__imp_KeReleaseSpinLock
0x14000347c  nop     dword ptr [rax+rax+00h]
0x140003481  mov     rbx, [rsp+28h+arg_0]
0x140003486  mov     rax, rdi
0x140003489  mov     rsi, [rsp+28h+arg_8]
0x14000348e  add     rsp, 20h
0x140003492  pop     rdi
0x140003493  retn
```
