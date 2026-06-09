# ReturnTimerToFreeQ

- ea: `0x14001a210`
- end: `0x14001a2af`
- name: `ReturnTimerToFreeQ`
- size: `159`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001a0e0`
- `0x140026380`

## callees

- `0x14001a210`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a23c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a23c`
- `ntoskrnl!KeSetEvent` at `0x14001a28a`
- `ntoskrnl!KeSetEvent` at `0x14001a28a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a26e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a26e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a2a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a2a1`

## pseudocode

```c
void __fastcall ReturnTimerToFreeQ(_DWORD *Entry, char a2)
{
  KIRQL v4; // bl

  v4 = -1;
  if ( !a2 )
    v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  Entry[4] = 846031188;
  ExFreeToNPagedLookasideList(&Lookaside, Entry);
  if ( !--dword_1400396A0 )
    KeSetEvent(&Event, 0, 0);
  if ( !a2 )
    KeReleaseSpinLock(&SpinLock, v4);
}

```

## disassembly

```asm
0x14001a210  mov     [rsp+arg_0], rbx
0x14001a215  mov     [rsp+arg_10], rsi
0x14001a21a  push    rdi
0x14001a21b  sub     rsp, 20h
0x14001a21f  mov     dil, dl
0x14001a222  mov     rsi, rcx
0x14001a225  mov     bl, 0FFh
0x14001a227  test    dl, dl
0x14001a229  jz      short loc_14001A267
0x14001a22b  mov     rdx, rsi; Entry
0x14001a22e  mov     dword ptr [rsi+10h], 326D6954h
0x14001a235  lea     rcx, Lookaside; Lookaside
0x14001a23c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001a243  nop     dword ptr [rax+rax+00h]
0x14001a248  sub     cs:dword_1400396A0, 1
0x14001a24f  jz      short loc_14001A27E
0x14001a251  test    dil, dil
0x14001a254  jz      short loc_14001A298
0x14001a256  mov     rbx, [rsp+28h+arg_0]
0x14001a25b  mov     rsi, [rsp+28h+arg_10]
0x14001a260  add     rsp, 20h
0x14001a264  pop     rdi
0x14001a265  retn
0x14001a267  lea     rcx, SpinLock; SpinLock
0x14001a26e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a275  nop     dword ptr [rax+rax+00h]
0x14001a27a  mov     bl, al
0x14001a27c  jmp     short loc_14001A22B
0x14001a27e  xor     r8d, r8d; Wait
0x14001a281  lea     rcx, Event; Event
0x14001a288  xor     edx, edx; Increment
0x14001a28a  call    cs:__imp_KeSetEvent
0x14001a291  nop     dword ptr [rax+rax+00h]
0x14001a296  jmp     short loc_14001A251
0x14001a298  mov     dl, bl; NewIrql
0x14001a29a  lea     rcx, SpinLock; SpinLock
0x14001a2a1  call    cs:__imp_KeReleaseSpinLock
0x14001a2a8  nop     dword ptr [rax+rax+00h]
0x14001a2ad  jmp     short loc_14001A256
```
