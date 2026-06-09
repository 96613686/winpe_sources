# PplpLazyInitializeLookasideList

- ea: `0x140003eb0`
- end: `0x140003f3f`
- name: `PplpLazyInitializeLookasideList`
- size: `143`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400031a0`
- `0x140003410`
- `0x1400037e0`
- `0x140003ae0`

## callees

- `0x140003eb0`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x140003f11`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140003f11`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003f29`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003f29`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003ec3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003ec3`

## pseudocode

```c
void __fastcall PplpLazyInitializeLookasideList(__int64 a1, __int64 a2)
{
  KIRQL v4; // si

  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 104));
  if ( !*(_BYTE *)(a2 + 112) )
  {
    ExInitializeLookasideListEx(
      (PLOOKASIDE_LIST_EX)a2,
      PplpGenericAllocateFunction,
      PplpGenericFreeFunction,
      *(POOL_TYPE *)(a1 + 32),
      *(_DWORD *)(a1 + 4),
      *(_QWORD *)(a1 + 16),
      *(_DWORD *)(a1 + 8),
      *(_WORD *)(a1 + 36));
    *(_BYTE *)(a2 + 112) = 1;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 104), v4);
}

```

## disassembly

```asm
0x140003eb0  push    rbx
0x140003eb2  push    rbp
0x140003eb3  push    rsi
0x140003eb4  push    rdi
0x140003eb5  sub     rsp, 48h
0x140003eb9  mov     rbp, rcx
0x140003ebc  mov     rdi, rdx
0x140003ebf  lea     rcx, [rdx+68h]; SpinLock
0x140003ec3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003eca  nop     dword ptr [rax+rax+00h]
0x140003ecf  cmp     byte ptr [rdi+70h], 0
0x140003ed3  movzx   esi, al
0x140003ed6  jnz     short loc_140003F21
0x140003ed8  movzx   r8d, word ptr [rbp+24h]
0x140003edd  lea     rdx, PplpGenericAllocateFunction; Allocate
0x140003ee4  mov     ecx, [rbp+4]
0x140003ee7  mov     r9d, [rbp+20h]; PoolType
0x140003eeb  mov     [rsp+68h+Depth], r8w; Depth
0x140003ef1  mov     r8d, [rbp+8]
0x140003ef5  mov     [rsp+68h+Tag], r8d; Tag
0x140003efa  mov     r8, [rbp+10h]
0x140003efe  mov     [rsp+68h+Size], r8; Size
0x140003f03  lea     r8, PplpGenericFreeFunction; Free
0x140003f0a  mov     [rsp+68h+Flags], ecx; Flags
0x140003f0e  mov     rcx, rdi; Lookaside
0x140003f11  call    cs:__imp_ExInitializeLookasideListEx
0x140003f18  nop     dword ptr [rax+rax+00h]
0x140003f1d  mov     byte ptr [rdi+70h], 1
0x140003f21  movzx   edx, sil; NewIrql
0x140003f25  lea     rcx, [rdi+68h]; SpinLock
0x140003f29  call    cs:__imp_KeReleaseSpinLock
0x140003f30  nop     dword ptr [rax+rax+00h]
0x140003f35  add     rsp, 48h
0x140003f39  pop     rdi
0x140003f3a  pop     rsi
0x140003f3b  pop     rbp
0x140003f3c  pop     rbx
0x140003f3d  retn
```
