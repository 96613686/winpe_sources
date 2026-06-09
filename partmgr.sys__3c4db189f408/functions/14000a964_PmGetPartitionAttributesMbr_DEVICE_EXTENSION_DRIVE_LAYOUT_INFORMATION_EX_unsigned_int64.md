# PmGetPartitionAttributesMbr(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,unsigned __int64 *)

- ea: `0x14000a964`
- end: `0x14000aa58`
- name: `?PmGetPartitionAttributesMbr@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEA_K@Z`
- size: `244`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000dbd0`
- `0x14002470c`

## callees

- `0x14000a964`
- `0x14001c764`
- `0x140023310`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa38`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa38`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a9b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aa22`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a9b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aa22`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a991`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aa08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a991`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aa08`

## string_xrefs

- `0x14000a9ec`: `AttributesTableCache`

## pseudocode

```c
__int64 __fastcall PmGetPartitionAttributesMbr(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        unsigned __int64 *a3)
{
  KSPIN_LOCK *v3; // rbp
  unsigned int v5; // esi
  KIRQL v8; // al
  _QWORD *v9; // rbx
  int v10; // eax
  KIRQL v11; // al
  unsigned int v13; // [rsp+50h] [rbp+8h] BYREF
  PVOID P; // [rsp+60h] [rbp+18h] BYREF

  v3 = (KSPIN_LOCK *)((char *)a1 + 112);
  v13 = 0;
  v5 = 0;
  *a3 = 0;
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
  P = (PVOID)*((_QWORD *)a1 + 141);
  v9 = P;
  *((_QWORD *)a1 + 141) = 0;
  KeReleaseSpinLock(v3, v8);
  if ( !v9 )
  {
    v10 = PmReadPartitionAttributesMbr(a1, a2, (struct _PARTITION_ATTRIBUTES_TABLE **)&P, &v13);
    v9 = P;
    v5 = v10;
    if ( v10 < 0 )
      goto LABEL_5;
    PmSetDeviceParameterBinary(a1, L"AttributesTableCache", P, 0x18u);
  }
  *a3 = v9[2];
  v11 = KeAcquireSpinLockRaiseToDpc(v3);
  *((_QWORD *)a1 + 141) = v9;
  v9 = 0;
  KeReleaseSpinLock(v3, v11);
LABEL_5:
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  return v5;
}

```

## disassembly

```asm
0x14000a964  mov     [rsp+arg_8], rbx
0x14000a969  push    rbp
0x14000a96a  push    rsi
0x14000a96b  push    rdi
0x14000a96c  push    r14
0x14000a96e  push    r15
0x14000a970  sub     rsp, 20h
0x14000a974  lea     rbp, [rcx+70h]
0x14000a978  mov     [rsp+48h+arg_0], 0
0x14000a980  mov     rdi, rcx
0x14000a983  xor     esi, esi
0x14000a985  mov     rcx, rbp; SpinLock
0x14000a988  mov     [r8], rsi
0x14000a98b  mov     r14, r8
0x14000a98e  mov     r15, rdx
0x14000a991  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a998  nop     dword ptr [rax+rax+00h]
0x14000a99d  mov     rbx, [rdi+468h]
0x14000a9a4  mov     rcx, rbp; SpinLock
0x14000a9a7  mov     dl, al; NewIrql
0x14000a9a9  mov     [rsp+48h+P], rbx
0x14000a9ae  mov     [rdi+468h], rsi
0x14000a9b5  call    cs:__imp_KeReleaseSpinLock
0x14000a9bc  nop     dword ptr [rax+rax+00h]
0x14000a9c1  test    rbx, rbx
0x14000a9c4  jnz     short loc_14000A9FE
0x14000a9c6  lea     r9, [rsp+48h+arg_0]; unsigned int *
0x14000a9cb  mov     rdx, r15; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14000a9ce  lea     r8, [rsp+48h+P]; struct _PARTITION_ATTRIBUTES_TABLE **
0x14000a9d3  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14000a9d6  call    ?PmReadPartitionAttributesMbr@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU_PARTITION_ATTRIBUTES_TABLE@@PEAK@Z; PmReadPartitionAttributesMbr(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_PARTITION_ATTRIBUTES_TABLE * *,ulong *)
0x14000a9db  mov     rbx, [rsp+48h+P]
0x14000a9e0  mov     esi, eax
0x14000a9e2  test    eax, eax
0x14000a9e4  js      short loc_14000AA2E
0x14000a9e6  mov     r9d, 18h; unsigned int
0x14000a9ec  lea     rdx, aAttributestabl; "AttributesTableCache"
0x14000a9f3  mov     r8, rbx; void *
0x14000a9f6  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14000a9f9  call    ?PmSetDeviceParameterBinary@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAXK@Z; PmSetDeviceParameterBinary(_DEVICE_EXTENSION *,ushort *,void *,ulong)
0x14000a9fe  mov     rax, [rbx+10h]
0x14000aa02  mov     rcx, rbp; SpinLock
0x14000aa05  mov     [r14], rax
0x14000aa08  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000aa0f  nop     dword ptr [rax+rax+00h]
0x14000aa14  mov     [rdi+468h], rbx
0x14000aa1b  mov     rcx, rbp; SpinLock
0x14000aa1e  mov     dl, al; NewIrql
0x14000aa20  xor     ebx, ebx
0x14000aa22  call    cs:__imp_KeReleaseSpinLock
0x14000aa29  nop     dword ptr [rax+rax+00h]
0x14000aa2e  test    rbx, rbx
0x14000aa31  jz      short loc_14000AA44
0x14000aa33  xor     edx, edx; Tag
0x14000aa35  mov     rcx, rbx; P
0x14000aa38  call    cs:__imp_ExFreePoolWithTag
0x14000aa3f  nop     dword ptr [rax+rax+00h]
0x14000aa44  mov     rbx, [rsp+48h+arg_8]
0x14000aa49  mov     eax, esi
0x14000aa4b  add     rsp, 20h
0x14000aa4f  pop     r15
0x14000aa51  pop     r14
0x14000aa53  pop     rdi
0x14000aa54  pop     rsi
0x14000aa55  pop     rbp
0x14000aa56  retn
```
