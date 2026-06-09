# FltpvLinkResourceToFilter

- ea: `0x18007c220`
- end: `0x18007c3ff`
- name: `FltpvLinkResourceToFilter`
- size: `479`
- prototype: ``
- caller_count: `59`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180024440`
- `0x180066990`
- `0x18007d5d0`
- `0x18007d6c0`
- `0x18007d7d0`
- `0x18007d8c0`
- `0x18007d980`
- `0x18007e2a0`
- `0x18007e370`
- `0x18007e440`
- `0x18007e510`
- `0x18007e5e0`
- `0x18007e6b0`
- `0x18007ea70`
- `0x18007eb60`
- `0x18007ede0`
- `0x18007eea0`
- `0x18007f0c0`
- `0x18007f1e0`
- `0x18007f2a0`
- `0x18007f360`
- `0x18007f480`
- `0x18007f550`
- `0x180080840`
- `0x180080e40`
- `0x180080f60`
- `0x180081050`
- `0x180081170`
- `0x180081290`
- `0x1800813b0`
- `0x180082400`
- `0x1800824c0`
- `0x1800825c0`
- `0x1800827a0`
- `0x1800828b0`
- `0x180083060`
- `0x1800832a0`
- `0x180083430`
- `0x1800835f0`
- `0x180083ad0`
- `0x180083ee0`
- `0x180084340`
- `0x1800845a0`
- `0x180084b00`
- `0x180084bf0`
- `0x180084d80`
- `0x180084e90`
- `0x180084f80`
- `0x180085150`
- `0x180085380`

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
void __fastcall FltpvLinkResourceToFilter(_QWORD *a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  __int64 v4; // rsi
  _DWORD *v5; // rdi
  __int64 v8; // r9
  __int64 v9; // rax
  KIRQL v10; // r9
  __int64 v11; // r10
  KIRQL v12; // dl
  volatile signed __int32 *v13; // rcx
  char v14; // bp
  KIRQL v15; // r15
  __int64 v16; // rax

  v4 = a3;
  v5 = a4;
  if ( !a1 )
  {
    _InterlockedIncrement(&dword_180040310);
    return;
  }
  if ( !a4 )
  {
    LOBYTE(v8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1[30] + 1032LL));
    v9 = TreeLookup(a1[30] + 1024LL, a2, 0, v8);
    v12 = v10;
    if ( v9 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 72));
      ++*(_DWORD *)(a1[30] + 4 * v4 + 1040);
LABEL_6:
      KeReleaseSpinLock((PKSPIN_LOCK)(a1[30] + 1032LL), v12);
      return;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 1032), v10);
    v5 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1[30] + 896LL));
    if ( !v5 )
    {
      v13 = (volatile signed __int32 *)a1[30];
      if ( (*v13 & 1) == 0 )
        _InterlockedOr(v13, 1u);
      DbgPrintEx(
        0x2Fu,
        0,
        "FLTMGR!FltpvLinkResourceToFilter: Failed to allocate FLT_VERIFIER_OBJECT for filter (PFLT_FILTER=0x%08p).\n"
        "  Verifier resource tracking will not be accurate.\n",
        a1);
      v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1[30] + 1032LL));
      ++*(_DWORD *)(a1[30] + 1084LL);
      goto LABEL_6;
    }
  }
  v5[12] = 0;
  v14 = 0;
  v5[14] = v4;
  *((_QWORD *)v5 + 8) = a2;
  v5[18] = 1;
  v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1[30] + 1032LL));
  v16 = TreeInsert(a1[30] + 1024LL, v5, a2, 0);
  if ( v5 != (_DWORD *)v16 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 72));
    v14 = 1;
  }
  ++*(_DWORD *)(a1[30] + 4 * v4 + 1040);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1[30] + 1032LL), v15);
  if ( v14 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1[30] + 896LL), v5);
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
0x18007c240  lock inc cs:dword_180040310
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
