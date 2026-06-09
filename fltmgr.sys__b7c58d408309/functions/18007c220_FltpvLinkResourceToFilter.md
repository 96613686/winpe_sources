# FltpvLinkResourceToFilter

- ea: `0x18007c220`
- end: `0x18007c3ff`
- name: `FltpvLinkResourceToFilter`
- size: `479`
- prototype: `void __fastcall(_QWORD *, unsigned __int64, unsigned int, volatile signed __int32 *)`
- caller_count: `59`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800243e0`
- `0x180066990`
- `0x18007d570`
- `0x18007d660`
- `0x18007d770`
- `0x18007d860`
- `0x18007d920`
- `0x18007e040`
- `0x18007e110`
- `0x18007e1e0`
- `0x18007e2b0`
- `0x18007e380`
- `0x18007e450`
- `0x18007e750`
- `0x18007e840`
- `0x18007e960`
- `0x18007ea20`
- `0x18007eb30`
- `0x18007ebf0`
- `0x18007ecb0`
- `0x18007ed70`
- `0x18007ee90`
- `0x18007ef60`
- `0x180080040`
- `0x180080500`
- `0x180080620`
- `0x180080710`
- `0x180080830`
- `0x180080950`
- `0x180080a70`
- `0x1800823c0`
- `0x180082480`
- `0x180082580`
- `0x180082680`
- `0x180082790`
- `0x180082ae0`
- `0x180082ba0`
- `0x180082d30`
- `0x180082ef0`
- `0x1800831a0`
- `0x180083420`
- `0x1800835f0`
- `0x1800837e0`
- `0x180083bd0`
- `0x180083cc0`
- `0x180083e00`
- `0x180083f10`
- `0x180084000`
- `0x180084100`
- `0x180084230`

## callees

- `0x1800139a0`
- `0x180015890`
- `0x18007c220`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18007c2e3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18007c2e3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18007c3e3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18007c3e3`
- `ntoskrnl!DbgPrintEx` at `0x18007c317`
- `ntoskrnl!DbgPrintEx` at `0x18007c317`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18007c265`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18007c32d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18007c36f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18007c265`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18007c32d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18007c36f`
- `ntoskrnl!KeReleaseSpinLock` at `0x18007c2b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x18007c2c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x18007c3c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x18007c2b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x18007c2c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x18007c3c1`

## string_xrefs

- `0x18007c30a`: `FLTMGR!FltpvLinkResourceToFilter: Failed to allocate FLT_VERIFIER_OBJECT for filter (PFLT_FILTER=0x%08p).\n  Verifier resource tracking will not be accurate.\n`

## pseudocode

```c
void __fastcall FltpvLinkResourceToFilter(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned int a3,
        volatile signed __int32 *a4)
{
  __int64 v4; // rsi
  volatile signed __int32 *v5; // rdi
  volatile signed __int32 *v8; // rax
  KIRQL v9; // r9
  __int64 v10; // r10
  KIRQL v11; // dl
  volatile signed __int32 *v12; // rcx
  char v13; // bp
  KIRQL v14; // r15
  volatile signed __int32 *v15; // rax

  v4 = a3;
  v5 = a4;
  if ( !a1 )
  {
    _InterlockedIncrement(&dword_18003FD90);
    return;
  }
  if ( !a4 )
  {
    KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1[30] + 1032LL));
    v8 = (volatile signed __int32 *)TreeLookup((__int64 *)(a1[30] + 1024LL), a2, 0);
    v11 = v9;
    if ( v8 )
    {
      _InterlockedIncrement(v8 + 18);
      ++*(_DWORD *)(a1[30] + 4 * v4 + 1040);
LABEL_6:
      KeReleaseSpinLock((PKSPIN_LOCK)(a1[30] + 1032LL), v11);
      return;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v10 + 1032), v9);
    v5 = (volatile signed __int32 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1[30] + 896LL));
    if ( !v5 )
    {
      v12 = (volatile signed __int32 *)a1[30];
      if ( (*v12 & 1) == 0 )
        _InterlockedOr(v12, 1u);
      DbgPrintEx(
        0x2Fu,
        0,
        "FLTMGR!FltpvLinkResourceToFilter: Failed to allocate FLT_VERIFIER_OBJECT for filter (PFLT_FILTER=0x%08p).\n"
        "  Verifier resource tracking will not be accurate.\n",
        a1);
      v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1[30] + 1032LL));
      ++*(_DWORD *)(a1[30] + 1084LL);
      goto LABEL_6;
    }
  }
  *((_DWORD *)v5 + 12) = 0;
  v13 = 0;
  *((_DWORD *)v5 + 14) = v4;
  *((_QWORD *)v5 + 8) = a2;
  *((_DWORD *)v5 + 18) = 1;
  v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1[30] + 1032LL));
  v15 = (volatile signed __int32 *)TreeInsert((_QWORD *)(a1[30] + 1024LL), (__int64)v5, a2, 0);
  if ( v5 != v15 )
  {
    _InterlockedIncrement(v15 + 18);
    v13 = 1;
  }
  ++*(_DWORD *)(a1[30] + 4 * v4 + 1040);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1[30] + 1032LL), v14);
  if ( v13 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1[30] + 896LL), (PVOID)v5);
}

```

## disassembly

```asm
0x18007c220  push    rbx
0x18007c222  push    rbp
0x18007c223  push    rsi
0x18007c224  push    rdi
0x18007c225  push    r12
0x18007c227  push    r14
0x18007c229  push    r15
0x18007c22b  sub     rsp, 20h
0x18007c22f  mov     esi, r8d
0x18007c232  mov     rdi, r9
0x18007c235  mov     r14, rdx
0x18007c238  mov     rbx, rcx
0x18007c23b  test    rcx, rcx
0x18007c23e  jnz     short loc_18007C24C
0x18007c240  lock inc cs:dword_18003FD90
0x18007c247  jmp     loc_18007C3EF
0x18007c24c  mov     r12d, 408h
0x18007c252  test    r9, r9
0x18007c255  jnz     loc_18007C34D
0x18007c25b  mov     rcx, [rcx+0F0h]
0x18007c262  add     rcx, r12; SpinLock
0x18007c265  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18007c26c  nop     dword ptr [rax+rax+00h]
0x18007c271  mov     r10, [rbx+0F0h]
0x18007c278  xor     r8d, r8d
0x18007c27b  mov     rdx, r14
0x18007c27e  mov     r9b, al
0x18007c281  lea     rcx, [r10+400h]
0x18007c288  call    TreeLookup
0x18007c28d  mov     dl, r9b; NewIrql
0x18007c290  test    rax, rax
0x18007c293  jz      short loc_18007C2C2
0x18007c295  lock inc dword ptr [rax+48h]
0x18007c299  mov     rax, [rbx+0F0h]
0x18007c2a0  inc     dword ptr [rax+rsi*4+410h]
0x18007c2a7  mov     rcx, [rbx+0F0h]
0x18007c2ae  add     rcx, r12; SpinLock
0x18007c2b1  call    cs:__imp_KeReleaseSpinLock
0x18007c2b8  nop     dword ptr [rax+rax+00h]
0x18007c2bd  jmp     loc_18007C3EF
0x18007c2c2  lea     rcx, [r10+408h]; SpinLock
0x18007c2c9  call    cs:__imp_KeReleaseSpinLock
0x18007c2d0  nop     dword ptr [rax+rax+00h]
0x18007c2d5  mov     rcx, [rbx+0F0h]
0x18007c2dc  add     rcx, 380h; Lookaside
0x18007c2e3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18007c2ea  nop     dword ptr [rax+rax+00h]
0x18007c2ef  mov     rdi, rax
0x18007c2f2  test    rax, rax
0x18007c2f5  jnz     short loc_18007C34D
0x18007c2f7  mov     rcx, [rbx+0F0h]
0x18007c2fe  mov     eax, [rcx]
0x18007c300  test    al, 1
0x18007c302  jnz     short loc_18007C308
0x18007c304  lock or dword ptr [rcx], 1
0x18007c308  xor     edx, edx; Level
0x18007c30a  lea     r8, aFltmgrFltpvlin; "FLTMGR!FltpvLinkResourceToFilter: Faile"...
0x18007c311  mov     r9, rbx
0x18007c314  lea     ecx, [rdx+2Fh]; ComponentId
0x18007c317  call    cs:__imp_DbgPrintEx
0x18007c31e  nop     dword ptr [rax+rax+00h]
0x18007c323  mov     rcx, [rbx+0F0h]
0x18007c32a  add     rcx, r12; SpinLock
0x18007c32d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18007c334  nop     dword ptr [rax+rax+00h]
0x18007c339  mov     rcx, [rbx+0F0h]
0x18007c340  mov     dl, al
0x18007c342  inc     dword ptr [rcx+43Ch]
0x18007c348  jmp     loc_18007C2A7
0x18007c34d  mov     dword ptr [rdi+30h], 0
0x18007c354  xor     bpl, bpl
0x18007c357  mov     [rdi+38h], esi
0x18007c35a  mov     [rdi+40h], r14
0x18007c35e  mov     dword ptr [rdi+48h], 1
0x18007c365  mov     rcx, [rbx+0F0h]
0x18007c36c  add     rcx, r12; SpinLock
0x18007c36f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18007c376  nop     dword ptr [rax+rax+00h]
0x18007c37b  mov     rcx, [rbx+0F0h]
0x18007c382  xor     r9d, r9d
0x18007c385  add     rcx, 400h
0x18007c38c  mov     r8, r14
0x18007c38f  mov     rdx, rdi
0x18007c392  mov     r15b, al
0x18007c395  call    TreeInsert
0x18007c39a  cmp     rdi, rax
0x18007c39d  jz      short loc_18007C3A6
0x18007c39f  lock inc dword ptr [rax+48h]
0x18007c3a3  mov     bpl, 1
0x18007c3a6  mov     rax, [rbx+0F0h]
0x18007c3ad  mov     dl, r15b; NewIrql
0x18007c3b0  inc     dword ptr [rax+rsi*4+410h]
0x18007c3b7  mov     rcx, [rbx+0F0h]
0x18007c3be  add     rcx, r12; SpinLock
0x18007c3c1  call    cs:__imp_KeReleaseSpinLock
0x18007c3c8  nop     dword ptr [rax+rax+00h]
0x18007c3cd  test    bpl, bpl
0x18007c3d0  jz      short loc_18007C3EF
0x18007c3d2  mov     rcx, [rbx+0F0h]
0x18007c3d9  mov     rdx, rdi; Entry
0x18007c3dc  add     rcx, 380h; Lookaside
0x18007c3e3  call    cs:__imp_ExFreeToNPagedLookasideList
0x18007c3ea  nop     dword ptr [rax+rax+00h]
0x18007c3ef  add     rsp, 20h
0x18007c3f3  pop     r15
0x18007c3f5  pop     r14
0x18007c3f7  pop     r12
0x18007c3f9  pop     rdi
0x18007c3fa  pop     rsi
0x18007c3fb  pop     rbp
0x18007c3fc  pop     rbx
0x18007c3fd  retn
```
