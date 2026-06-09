# PplpLazyInitializeLookasideList

- ea: `0x14001771c`
- end: `0x1400177ac`
- name: `PplpLazyInitializeLookasideList`
- size: `144`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400138e0`
- `0x140015f60`
- `0x140016050`
- `0x140016280`
- `0x140016620`
- `0x140016b10`
- `0x140017210`
- `0x1400174c0`
- `0x140017520`
- `0x140017580`
- `0x140017680`
- `0x1400176d0`
- `0x140017c30`
- `0x140018020`
- `0x14004e7d0`

## callees

- `0x14001771c`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001779a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001779a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001774b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001774b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001772f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001772f`

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
0x14001771c  push    rbx
0x14001771e  push    rbp
0x14001771f  push    rsi
0x140017720  push    rdi
0x140017721  sub     rsp, 48h
0x140017725  mov     rdi, rcx
0x140017728  mov     rbx, rdx
0x14001772b  lea     rcx, [rdx+68h]; SpinLock
0x14001772f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017736  nop     dword ptr [rax+rax+00h]
0x14001773b  cmp     byte ptr [rbx+70h], 0
0x14001773f  mov     bpl, al
0x140017742  jz      short loc_140017761
0x140017744  mov     dl, bpl; NewIrql
0x140017747  lea     rcx, [rbx+68h]; SpinLock
0x14001774b  call    cs:__imp_KeReleaseSpinLock
0x140017752  nop     dword ptr [rax+rax+00h]
0x140017757  add     rsp, 48h
0x14001775b  pop     rdi
0x14001775c  pop     rsi
0x14001775d  pop     rbp
0x14001775e  pop     rbx
0x14001775f  retn
0x140017761  movzx   r8d, word ptr [rdi+24h]
0x140017766  mov     rcx, rbx; Lookaside
0x140017769  mov     edx, [rdi+4]
0x14001776c  mov     r9d, [rdi+20h]; PoolType
0x140017770  mov     [rsp+68h+Depth], r8w; Depth
0x140017776  mov     r8d, [rdi+8]
0x14001777a  mov     [rsp+68h+Tag], r8d; Tag
0x14001777f  mov     r8, [rdi+10h]
0x140017783  mov     [rsp+68h+Size], r8; Size
0x140017788  lea     r8, PplpGenericFreeFunction; Free
0x14001778f  mov     [rsp+68h+Flags], edx; Flags
0x140017793  lea     rdx, PplpGenericAllocateFunction; Allocate
0x14001779a  call    cs:__imp_ExInitializeLookasideListEx
0x1400177a1  nop     dword ptr [rax+rax+00h]
0x1400177a6  mov     byte ptr [rbx+70h], 1
0x1400177aa  jmp     short loc_140017744
```
