# PplpLazyInitializeLookasideList

- ea: `0x140037eb0`
- end: `0x140037f3e`
- name: `PplpLazyInitializeLookasideList`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400093a0`
- `0x14000e530`
- `0x14000e9c0`
- `0x140014830`
- `0x140017140`
- `0x1400181f0`
- `0x14001ad10`
- `0x14001b480`
- `0x140022950`

## callees

- `0x140037eb0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140037ec3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140037ec3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037f28`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037f28`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140037f11`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140037f11`

## pseudocode

```c
void __fastcall PplpLazyInitializeLookasideList(__int64 a1, __int64 a2)
{
  KIRQL v4; // bp

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
0x140037eb0  push    rbx
0x140037eb2  push    rbp
0x140037eb3  push    rsi
0x140037eb4  push    rdi
0x140037eb5  sub     rsp, 48h
0x140037eb9  mov     rdi, rcx
0x140037ebc  mov     rbx, rdx
0x140037ebf  lea     rcx, [rdx+68h]; SpinLock
0x140037ec3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140037eca  nop     dword ptr [rax+rax+00h]
0x140037ecf  cmp     byte ptr [rbx+70h], 0
0x140037ed3  mov     bpl, al
0x140037ed6  jnz     short loc_140037F21
0x140037ed8  movzx   r8d, word ptr [rdi+24h]
0x140037edd  mov     rcx, rbx; Lookaside
0x140037ee0  mov     edx, [rdi+4]
0x140037ee3  mov     r9d, [rdi+20h]; PoolType
0x140037ee7  mov     [rsp+68h+Depth], r8w; Depth
0x140037eed  mov     r8d, [rdi+8]
0x140037ef1  mov     [rsp+68h+Tag], r8d; Tag
0x140037ef6  mov     r8, [rdi+10h]
0x140037efa  mov     [rsp+68h+Size], r8; Size
0x140037eff  lea     r8, PplpGenericFreeFunction; Free
0x140037f06  mov     [rsp+68h+Flags], edx; Flags
0x140037f0a  lea     rdx, PplpGenericAllocateFunction; Allocate
0x140037f11  call    cs:__imp_ExInitializeLookasideListEx
0x140037f18  nop     dword ptr [rax+rax+00h]
0x140037f1d  mov     byte ptr [rbx+70h], 1
0x140037f21  mov     dl, bpl; NewIrql
0x140037f24  lea     rcx, [rbx+68h]; SpinLock
0x140037f28  call    cs:__imp_KeReleaseSpinLock
0x140037f2f  nop     dword ptr [rax+rax+00h]
0x140037f34  add     rsp, 48h
0x140037f38  pop     rdi
0x140037f39  pop     rsi
0x140037f3a  pop     rbp
0x140037f3b  pop     rbx
0x140037f3c  retn
```
