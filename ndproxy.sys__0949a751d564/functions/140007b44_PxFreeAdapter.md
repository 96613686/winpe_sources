# PxFreeAdapter

- ea: `0x140007b44`
- end: `0x140007bf1`
- name: `PxFreeAdapter`
- size: `173`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001030`
- `0x140001e40`
- `0x140002670`
- `0x140002fd0`
- `0x140003940`

## callees

- `0x140001bc8`
- `0x140007b44`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b90`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b90`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007bd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007bd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007bc6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007bc6`

## pseudocode

```c
void __fastcall PxFreeAdapter(PVOID **P)
{
  KSPIN_LOCK *v2; // rcx
  KIRQL v3; // al
  PKDEFERRED_ROUTINE DeferredRoutine; // rdx
  PVOID *v5; // rcx
  PVOID *v6; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xBu,
      (__int64)WPP_a6cada0c64e03ec47d691a112a859896_Traceguids,
      P);
  v2 = (KSPIN_LOCK *)((char *)WPP_MAIN_CB.Dpc.DeferredRoutine + 88);
  *((_DWORD *)P + 5) = 0;
  v3 = KeAcquireSpinLockRaiseToDpc(v2);
  DeferredRoutine = WPP_MAIN_CB.Dpc.DeferredRoutine;
  *((_BYTE *)WPP_MAIN_CB.Dpc.DeferredRoutine + 96) = v3;
  v5 = *P;
  if ( (*P)[1] != P || (v6 = P[1], *v6 != P) )
    __fastfail(3u);
  *v6 = v5;
  v5[1] = v6;
  KeReleaseSpinLock((PKSPIN_LOCK)DeferredRoutine + 11, *((_BYTE *)DeferredRoutine + 96));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140007b44  push    rbx
0x140007b46  sub     rsp, 20h
0x140007b4a  mov     rbx, rcx
0x140007b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b54  lea     rax, WPP_GLOBAL_Control
0x140007b5b  cmp     rcx, rax
0x140007b5e  jz      short loc_140007B7E
0x140007b60  cmp     byte ptr [rcx+29h], 5
0x140007b64  jb      short loc_140007B7E
0x140007b66  mov     rcx, [rcx+18h]
0x140007b6a  lea     r8, WPP_a6cada0c64e03ec47d691a112a859896_Traceguids
0x140007b71  mov     edx, 0Bh
0x140007b76  mov     r9, rbx
0x140007b79  call    WPP_SF_q
0x140007b7e  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140007b85  add     rcx, 58h ; 'X'; SpinLock
0x140007b89  mov     dword ptr [rbx+14h], 0
0x140007b90  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007b97  nop     dword ptr [rax+rax+00h]
0x140007b9c  mov     rdx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140007ba3  mov     [rdx+60h], al
0x140007ba6  mov     rcx, [rbx]
0x140007ba9  cmp     [rcx+8], rbx
0x140007bad  jnz     short loc_140007BEA
0x140007baf  mov     rax, [rbx+8]
0x140007bb3  cmp     [rax], rbx
0x140007bb6  jnz     short loc_140007BEA
0x140007bb8  mov     [rax], rcx
0x140007bbb  mov     [rcx+8], rax
0x140007bbf  lea     rcx, [rdx+58h]; SpinLock
0x140007bc3  mov     dl, [rdx+60h]; NewIrql
0x140007bc6  call    cs:__imp_KeReleaseSpinLock
0x140007bcd  nop     dword ptr [rax+rax+00h]
0x140007bd2  xor     edx, edx; Tag
0x140007bd4  mov     rcx, rbx; P
0x140007bd7  call    cs:__imp_ExFreePoolWithTag
0x140007bde  nop     dword ptr [rax+rax+00h]
0x140007be3  add     rsp, 20h
0x140007be7  pop     rbx
0x140007be8  retn
0x140007bea  mov     ecx, 3
0x140007bef  int     29h; Win8: RtlFailFast(ecx)
```
