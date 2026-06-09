# WFDDiscoverInvalidateCachedDevices(_ADAPT *)

- ea: `0x140054a3c`
- end: `0x140054adf`
- name: `?WFDDiscoverInvalidateCachedDevices@@YAHPEAU_ADAPT@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(struct _ADAPT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140053e08`
- `0x140086a40`

## callees

- `0x140054a3c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054a83`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054a83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054a94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054a94`
- `ntoskrnl!KeReleaseSpinLock` at `0x140054ac5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140054ac5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140054a53`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140054a53`

## pseudocode

```c
__int64 __fastcall WFDDiscoverInvalidateCachedDevices(struct _ADAPT *a1)
{
  _NDIS_SPIN_LOCK *p_Lock; // rdi
  DOT11_BYTE_ARRAY *pWFDDeviceCache; // rcx
  DOT11_BYTE_ARRAY *v4; // rcx
  KIRQL OldIrql; // dl

  p_Lock = &a1->ScanModule.Lock;
  a1->ScanModule.Lock.OldIrql = KeAcquireSpinLockRaiseToDpc(&a1->ScanModule.Lock.SpinLock);
  pWFDDeviceCache = a1->ScanModule.pWFDDeviceCache;
  if ( pWFDDeviceCache )
  {
    v4 = pWFDDeviceCache - 1;
    if ( *(_QWORD *)&v4->Header.Type )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v4->Header.Type, v4);
    else
      ExFreePoolWithTag(v4, v4->uTotalNumOfBytes);
  }
  OldIrql = a1->ScanModule.Lock.OldIrql;
  a1->ScanModule.uWFDDeviceCacheSize = 0;
  a1->ScanModule.pWFDDeviceCache = 0;
  a1->ScanModule.bWFDDeviceCacheValid = 0;
  KeReleaseSpinLock(&p_Lock->SpinLock, OldIrql);
  return 0;
}

```

## disassembly

```asm
0x140054a3c  mov     [rsp+arg_0], rbx
0x140054a41  push    rdi
0x140054a42  sub     rsp, 20h
0x140054a46  lea     rdi, [rcx+90h]
0x140054a4d  mov     rbx, rcx
0x140054a50  mov     rcx, rdi; SpinLock
0x140054a53  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140054a5a  nop     dword ptr [rax+rax+00h]
0x140054a5f  mov     [rbx+98h], al
0x140054a65  mov     rcx, [rbx+0D8h]
0x140054a6c  test    rcx, rcx
0x140054a6f  jz      short loc_140054AA0
0x140054a71  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140054a75  mov     rax, [rcx]
0x140054a78  test    rax, rax
0x140054a7b  jz      short loc_140054A91
0x140054a7d  mov     rdx, rcx; Entry
0x140054a80  mov     rcx, rax; Lookaside
0x140054a83  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054a8a  nop     dword ptr [rax+rax+00h]
0x140054a8f  jmp     short loc_140054AA0
0x140054a91  mov     edx, [rcx+8]; Tag
0x140054a94  call    cs:__imp_ExFreePoolWithTag
0x140054a9b  nop     dword ptr [rax+rax+00h]
0x140054aa0  mov     dl, [rbx+98h]; NewIrql
0x140054aa6  mov     rcx, rdi; SpinLock
0x140054aa9  mov     dword ptr [rbx+0E0h], 0
0x140054ab3  mov     qword ptr [rbx+0D8h], 0
0x140054abe  mov     byte ptr [rbx+0E4h], 0
0x140054ac5  call    cs:__imp_KeReleaseSpinLock
0x140054acc  nop     dword ptr [rax+rax+00h]
0x140054ad1  mov     rbx, [rsp+28h+arg_0]
0x140054ad6  xor     eax, eax
0x140054ad8  add     rsp, 20h
0x140054adc  pop     rdi
0x140054add  retn
```
