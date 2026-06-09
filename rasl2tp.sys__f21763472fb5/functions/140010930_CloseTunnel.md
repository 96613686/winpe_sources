# CloseTunnel

- ea: `0x140010930`
- end: `0x140010991`
- name: `CloseTunnel`
- size: `97`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140010998`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140010979`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010979`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001094b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001094b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001095b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001095b`

## pseudocode

```c
void __fastcall CloseTunnel(PVOID Entry, __int64 a2)
{
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 960LL), Entry);
  *(_BYTE *)(a2 + 40) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  CloseTunnel2(a2);
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), *(_BYTE *)(a2 + 40));
}

```

## disassembly

```asm
0x140010930  mov     [rsp+arg_0], rbx
0x140010935  push    rdi
0x140010936  sub     rsp, 20h
0x14001093a  mov     rdi, rdx
0x14001093d  mov     rdx, rcx; Entry
0x140010940  mov     rcx, [rdi+18h]
0x140010944  add     rcx, 3C0h; Lookaside
0x14001094b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140010952  nop     dword ptr [rax+rax+00h]
0x140010957  lea     rcx, [rdi+20h]; SpinLock
0x14001095b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010962  nop     dword ptr [rax+rax+00h]
0x140010967  mov     rcx, rdi
0x14001096a  mov     [rdi+28h], al
0x14001096d  call    CloseTunnel2
0x140010972  mov     dl, [rdi+28h]; NewIrql
0x140010975  lea     rcx, [rdi+20h]; SpinLock
0x140010979  call    cs:__imp_KeReleaseSpinLock
0x140010980  nop     dword ptr [rax+rax+00h]
0x140010985  mov     rbx, [rsp+28h+arg_0]
0x14001098a  add     rsp, 20h
0x14001098e  pop     rdi
0x14001098f  retn
```
