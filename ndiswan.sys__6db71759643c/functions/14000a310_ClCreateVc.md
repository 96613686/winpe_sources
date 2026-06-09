# ClCreateVc

- ea: `0x14000a310`
- end: `0x14000a4a4`
- name: `ClCreateVc`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140005930`
- `0x1400059d4`
- `0x14000a290`
- `0x14000a310`
- `0x14000b13c`
- `0x14000b2cc`
- `0x14000b3fc`
- `0x14000bfcc`
- `0x14000c25c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000a3f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a43b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a3f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a43b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a3cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a423`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a3cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a423`

## pseudocode

```c
__int64 __fastcall ClCreateVc(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rbx
  _QWORD *LinkCB; // rax
  _QWORD *v8; // rdi
  int v9; // eax
  char *BundleCB; // rax
  char *v11; // rbp
  KIRQL v12; // al

  v3 = *(_QWORD *)(a1 + 32);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
  }
  LinkCB = NdisWanAllocateLinkCB(v3, 0);
  v8 = LinkCB;
  if ( !LinkCB )
    return 3221225626LL;
  LinkCB[7] = a2;
  LinkCB[8] = a2;
  LinkCB[11] = a1;
  *((_DWORD *)LinkCB + 34) = 3600;
  *((_DWORD *)LinkCB + 42) = 3600;
  v9 = *(_DWORD *)(v3 + 172);
  *((_DWORD *)v8 + 9) |= 4u;
  *((_DWORD *)v8 + 52) = v9;
  BundleCB = NdisWanAllocateBundleCB();
  v11 = BundleCB;
  if ( !BundleCB )
  {
LABEL_15:
    NdisWanFreeLinkCB(v8);
    return 3221225626LL;
  }
  BundleCB[1784] = *(_DWORD *)(v3 + 124) != 13;
  BundleCB[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)BundleCB + 221);
  AddLinkToBundle(v11, v8);
  KeReleaseSpinLock((PKSPIN_LOCK)v11 + 221, v11[1776]);
  if ( !InsertBundleInConnectionTable(v11) || !InsertLinkInConnectionTable(v8) )
  {
    RemoveLinkFromBundle(v11);
    goto LABEL_15;
  }
  *a3 = v8[5];
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 88));
  ++*(_DWORD *)(a1 + 20);
  *(_BYTE *)(a1 + 96) = v12;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 88), v12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14000a310  push    rbx
0x14000a312  push    rbp
0x14000a313  push    rsi
0x14000a314  push    rdi
0x14000a315  push    r12
0x14000a317  push    r14
0x14000a319  sub     rsp, 28h
0x14000a31d  mov     rbx, [rcx+20h]
0x14000a321  mov     r14, r8
0x14000a324  mov     rbp, rdx
0x14000a327  mov     rsi, rcx
0x14000a32a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a331  lea     r12, WPP_GLOBAL_Control
0x14000a338  cmp     rcx, r12
0x14000a33b  jz      short loc_14000A361
0x14000a33d  test    dword ptr [rcx+2Ch], 8000h
0x14000a344  jz      short loc_14000A361
0x14000a346  cmp     byte ptr [rcx+29h], 5
0x14000a34a  jb      short loc_14000A361
0x14000a34c  mov     rcx, [rcx+18h]
0x14000a350  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14000a357  mov     edx, 0Ah
0x14000a35c  call    WPP_SF_
0x14000a361  xor     edx, edx
0x14000a363  mov     rcx, rbx
0x14000a366  call    NdisWanAllocateLinkCB
0x14000a36b  mov     rdi, rax
0x14000a36e  test    rax, rax
0x14000a371  jz      loc_14000A491
0x14000a377  mov     [rax+38h], rbp
0x14000a37b  mov     [rax+40h], rbp
0x14000a37f  mov     [rax+58h], rsi
0x14000a383  mov     eax, 0E10h
0x14000a388  mov     [rdi+88h], eax
0x14000a38e  mov     [rdi+0A8h], eax
0x14000a394  mov     eax, [rbx+0ACh]
0x14000a39a  or      dword ptr [rdi+24h], 4
0x14000a39e  mov     [rdi+0D0h], eax
0x14000a3a4  call    NdisWanAllocateBundleCB
0x14000a3a9  mov     rbp, rax
0x14000a3ac  test    rax, rax
0x14000a3af  jz      loc_14000A489
0x14000a3b5  cmp     dword ptr [rbx+7Ch], 0Dh
0x14000a3b9  lea     rbx, [rbp+6E8h]
0x14000a3c0  mov     rcx, rbx; SpinLock
0x14000a3c3  setnz   al
0x14000a3c6  mov     [rbp+6F8h], al
0x14000a3cc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a3d3  nop     dword ptr [rax+rax+00h]
0x14000a3d8  mov     rdx, rdi
0x14000a3db  mov     rcx, rbp
0x14000a3de  mov     [rbp+6F0h], al
0x14000a3e4  call    AddLinkToBundle
0x14000a3e9  mov     dl, [rbp+6F0h]; NewIrql
0x14000a3ef  mov     rcx, rbx; SpinLock
0x14000a3f2  call    cs:__imp_KeReleaseSpinLock
0x14000a3f9  nop     dword ptr [rax+rax+00h]
0x14000a3fe  mov     rcx, rbp
0x14000a401  call    InsertBundleInConnectionTable
0x14000a406  test    rax, rax
0x14000a409  jz      short loc_14000A47B
0x14000a40b  mov     rcx, rdi
0x14000a40e  call    InsertLinkInConnectionTable
0x14000a413  test    rax, rax
0x14000a416  jz      short loc_14000A47B
0x14000a418  mov     rax, [rdi+28h]
0x14000a41c  lea     rcx, [rsi+58h]; SpinLock
0x14000a420  mov     [r14], rax
0x14000a423  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a42a  nop     dword ptr [rax+rax+00h]
0x14000a42f  inc     dword ptr [rsi+14h]
0x14000a432  lea     rcx, [rsi+58h]; SpinLock
0x14000a436  mov     dl, al; NewIrql
0x14000a438  mov     [rsi+60h], al
0x14000a43b  call    cs:__imp_KeReleaseSpinLock
0x14000a442  nop     dword ptr [rax+rax+00h]
0x14000a447  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a44e  cmp     rcx, r12
0x14000a451  jz      short loc_14000A477
0x14000a453  test    dword ptr [rcx+2Ch], 8000h
0x14000a45a  jz      short loc_14000A477
0x14000a45c  cmp     byte ptr [rcx+29h], 5
0x14000a460  jb      short loc_14000A477
0x14000a462  mov     rcx, [rcx+18h]
0x14000a466  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14000a46d  mov     edx, 0Bh
0x14000a472  call    WPP_SF_
0x14000a477  xor     eax, eax
0x14000a479  jmp     short loc_14000A496
0x14000a47b  xor     r8d, r8d
0x14000a47e  mov     rdx, rdi
0x14000a481  mov     rcx, rbp; Entry
0x14000a484  call    RemoveLinkFromBundle
0x14000a489  mov     rcx, rdi; Entry
0x14000a48c  call    NdisWanFreeLinkCB
0x14000a491  mov     eax, 0C000009Ah
0x14000a496  add     rsp, 28h
0x14000a49a  pop     r14
0x14000a49c  pop     r12
0x14000a49e  pop     rdi
0x14000a49f  pop     rsi
0x14000a4a0  pop     rbp
0x14000a4a1  pop     rbx
0x14000a4a2  retn
```
