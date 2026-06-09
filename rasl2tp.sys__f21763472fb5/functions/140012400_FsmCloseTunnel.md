# FsmCloseTunnel

- ea: `0x140012400`
- end: `0x1400124ad`
- name: `FsmCloseTunnel`
- size: `173`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140001850`
- `0x14000fd0c`
- `0x140010998`
- `0x140012400`
- `0x14001c400`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140012497`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012497`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140012423`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140012423`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012433`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012433`

## pseudocode

```c
void __fastcall FsmCloseTunnel(PVOID Entry, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  int v4; // esi
  int v6; // ebp
  KIRQL v7; // al
  bool v8; // cc
  _WORD *v9; // [rsp+28h] [rbp-40h]

  v4 = *a4;
  v6 = a4[4];
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 960LL), Entry);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  v8 = *(_DWORD *)(a2 + 124) <= 1u;
  *(_BYTE *)(a2 + 40) = v7;
  if ( v8 )
  {
    CloseTunnel2(a2);
  }
  else
  {
    SetFlags(a2 + 120, 770);
    ReferenceTunnel(a2, 0);
    *(_DWORD *)(a2 + 124) = 0;
    SendControl(a2, 0, 4u, v4, v6, v9, 16);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), *(_BYTE *)(a2 + 40));
}

```

## disassembly

```asm
0x140012400  push    rbx
0x140012402  push    rbp
0x140012403  push    rsi
0x140012404  push    rdi
0x140012405  sub     rsp, 48h
0x140012409  movzx   esi, word ptr [r9]
0x14001240d  mov     rbx, rdx
0x140012410  movzx   ebp, word ptr [r9+8]
0x140012415  mov     rdx, rcx; Entry
0x140012418  mov     rcx, [rbx+18h]
0x14001241c  add     rcx, 3C0h; Lookaside
0x140012423  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001242a  nop     dword ptr [rax+rax+00h]
0x14001242f  lea     rcx, [rbx+20h]; SpinLock
0x140012433  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001243a  nop     dword ptr [rax+rax+00h]
0x14001243f  cmp     dword ptr [rbx+7Ch], 1
0x140012443  mov     [rbx+28h], al
0x140012446  jbe     short loc_140012488
0x140012448  lea     rcx, [rbx+78h]
0x14001244c  mov     edx, 302h
0x140012451  call    SetFlags
0x140012456  xor     edx, edx
0x140012458  mov     rcx, rbx
0x14001245b  call    ReferenceTunnel
0x140012460  mov     r9d, esi
0x140012463  mov     [rsp+68h+var_38], 10h
0x14001246b  mov     r8d, 4
0x140012471  mov     dword ptr [rbx+7Ch], 0
0x140012478  xor     edx, edx
0x14001247a  mov     [rsp+68h+var_48], ebp
0x14001247e  mov     rcx, rbx
0x140012481  call    SendControl
0x140012486  jmp     short loc_140012490
0x140012488  mov     rcx, rbx
0x14001248b  call    CloseTunnel2
0x140012490  mov     dl, [rbx+28h]; NewIrql
0x140012493  lea     rcx, [rbx+20h]; SpinLock
0x140012497  call    cs:__imp_KeReleaseSpinLock
0x14001249e  nop     dword ptr [rax+rax+00h]
0x1400124a3  add     rsp, 48h
0x1400124a7  pop     rdi
0x1400124a8  pop     rsi
0x1400124a9  pop     rbp
0x1400124aa  pop     rbx
0x1400124ab  retn
```
