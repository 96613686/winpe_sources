# PmSetPartitionAttributesMbr(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,unsigned __int64)

- ea: `0x14000ada0`
- end: `0x14000ae81`
- name: `?PmSetPartitionAttributesMbr@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@_K@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000dbd0`
- `0x14001d370`

## callees

- `0x14000a014`
- `0x14000ada0`
- `0x140010f20`
- `0x14001cde0`
- `0x140023310`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000ae5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ae5a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ae08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ae08`

## string_xrefs

- `0x14000adf5`: `AttributesTableCache`

## pseudocode

```c
__int64 __fastcall PmSetPartitionAttributesMbr(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        __int64 a3,
        unsigned int a4)
{
  int v6; // esi
  KIRQL v7; // al
  __int64 v8; // rcx
  KIRQL v9; // r14
  char *v10; // r8
  char *i; // rdx
  GUID v13; // [rsp+20h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-38h]

  v14 = a3;
  v13 = PARTITION_BASIC_DATA_GUID;
  v6 = PmWritePartitionAttributesMbr(a1, a2, (struct _PARTITION_ATTRIBUTES_TABLE *)&v13, a4);
  if ( v6 >= 0 )
  {
    PmSetDeviceParameterBinary(a1, L"AttributesTableCache", &v13, 0x18u);
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
    v8 = *((_QWORD *)a1 + 141);
    v9 = v7;
    if ( v8 )
      *(_QWORD *)(v8 + 16) = a3;
    v10 = (char *)a1 + 896;
    for ( i = (char *)*((_QWORD *)a1 + 112); i != v10; i = *(char **)i )
      *((_DWORD *)i - 26) |= 0x10u;
    PmQueueNotificationWorkItem(a1, "PmSetPartitionAttributesMbr", (int)v10);
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v9);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000ada0  push    rbx
0x14000ada2  push    rbp
0x14000ada3  push    rsi
0x14000ada4  push    rdi
0x14000ada5  push    r14
0x14000ada7  sub     rsp, 40h
0x14000adab  mov     rax, cs:__security_cookie
0x14000adb2  xor     rax, rsp
0x14000adb5  mov     [rsp+68h+var_30], rax
0x14000adba  movups  xmm1, xmmword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x14000adc1  mov     rbp, r8
0x14000adc4  mov     rbx, rcx
0x14000adc7  xorps   xmm0, xmm0
0x14000adca  movups  [rsp+68h+var_48+4], xmm0
0x14000adcf  mov     [rsp+68h+var_38], r8
0x14000add4  lea     r8, [rsp+68h+var_48]; struct _PARTITION_ATTRIBUTES_TABLE *
0x14000add9  movdqu  [rsp+68h+var_48], xmm1
0x14000addf  call    ?PmWritePartitionAttributesMbr@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAU_PARTITION_ATTRIBUTES_TABLE@@K@Z; PmWritePartitionAttributesMbr(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_PARTITION_ATTRIBUTES_TABLE *,ulong)
0x14000ade4  mov     esi, eax
0x14000ade6  test    eax, eax
0x14000ade8  js      short loc_14000AE66
0x14000adea  mov     r9d, 18h; unsigned int
0x14000adf0  lea     r8, [rsp+68h+var_48]; void *
0x14000adf5  lea     rdx, aAttributestabl; "AttributesTableCache"
0x14000adfc  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14000adff  call    ?PmSetDeviceParameterBinary@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAXK@Z; PmSetDeviceParameterBinary(_DEVICE_EXTENSION *,ushort *,void *,ulong)
0x14000ae04  lea     rcx, [rbx+70h]; SpinLock
0x14000ae08  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ae0f  nop     dword ptr [rax+rax+00h]
0x14000ae14  mov     rcx, [rbx+468h]
0x14000ae1b  mov     r14b, al
0x14000ae1e  test    rcx, rcx
0x14000ae21  jz      short loc_14000AE27
0x14000ae23  mov     [rcx+10h], rbp
0x14000ae27  lea     r8, [rbx+380h]
0x14000ae2e  mov     rdx, [r8]
0x14000ae31  jmp     short loc_14000AE3F
0x14000ae33  mov     eax, [rdx-68h]
0x14000ae36  or      eax, 10h
0x14000ae39  mov     [rdx-68h], eax
0x14000ae3c  mov     rdx, [rdx]
0x14000ae3f  cmp     rdx, r8
0x14000ae42  jnz     short loc_14000AE33
0x14000ae44  lea     rdx, aPmsetpartition; "PmSetPartitionAttributesMbr"
0x14000ae4b  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14000ae4e  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x14000ae53  mov     dl, r14b; NewIrql
0x14000ae56  lea     rcx, [rbx+70h]; SpinLock
0x14000ae5a  call    cs:__imp_KeReleaseSpinLock
0x14000ae61  nop     dword ptr [rax+rax+00h]
0x14000ae66  mov     eax, esi
0x14000ae68  mov     rcx, [rsp+68h+var_30]
0x14000ae6d  xor     rcx, rsp; StackCookie
0x14000ae70  call    __security_check_cookie
0x14000ae75  add     rsp, 40h
0x14000ae79  pop     r14
0x14000ae7b  pop     rdi
0x14000ae7c  pop     rsi
0x14000ae7d  pop     rbp
0x14000ae7e  pop     rbx
0x14000ae7f  retn
```
