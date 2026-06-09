# PmInvalidateSnapshotDataCache(_DEVICE_EXTENSION *)

- ea: `0x14000db5c`
- end: `0x14000dbca`
- name: `?PmInvalidateSnapshotDataCache@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `110`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000dbd0`

## callees

- `0x14000db5c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000db8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db8f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dbad`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dbad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000db72`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000db72`

## pseudocode

```c
void __fastcall PmInvalidateSnapshotDataCache(KSPIN_LOCK *a1)
{
  KIRQL v2; // al
  void *v3; // rcx
  KIRQL v4; // si

  v2 = KeAcquireSpinLockRaiseToDpc(a1 + 14);
  v3 = (void *)a1[142];
  v4 = v2;
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    a1[142] = 0;
  }
  KeReleaseSpinLock(a1 + 14, v4);
}

```

## disassembly

```asm
0x14000db5c  mov     [rsp+arg_0], rbx
0x14000db61  mov     [rsp+arg_8], rsi
0x14000db66  push    rdi
0x14000db67  sub     rsp, 20h
0x14000db6b  mov     rbx, rcx
0x14000db6e  add     rcx, 70h ; 'p'; SpinLock
0x14000db72  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000db79  nop     dword ptr [rax+rax+00h]
0x14000db7e  mov     rcx, [rbx+470h]; P
0x14000db85  mov     sil, al
0x14000db88  test    rcx, rcx
0x14000db8b  jz      short loc_14000DBA6
0x14000db8d  xor     edx, edx; Tag
0x14000db8f  call    cs:__imp_ExFreePoolWithTag
0x14000db96  nop     dword ptr [rax+rax+00h]
0x14000db9b  mov     qword ptr [rbx+470h], 0
0x14000dba6  mov     dl, sil; NewIrql
0x14000dba9  lea     rcx, [rbx+70h]; SpinLock
0x14000dbad  call    cs:__imp_KeReleaseSpinLock
0x14000dbb4  nop     dword ptr [rax+rax+00h]
0x14000dbb9  mov     rbx, [rsp+28h+arg_0]
0x14000dbbe  mov     rsi, [rsp+28h+arg_8]
0x14000dbc3  add     rsp, 20h
0x14000dbc7  pop     rdi
0x14000dbc8  retn
```
