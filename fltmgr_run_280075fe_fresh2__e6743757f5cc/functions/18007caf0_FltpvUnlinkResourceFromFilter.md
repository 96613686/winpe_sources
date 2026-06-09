# FltpvUnlinkResourceFromFilter

- ea: `0x18007caf0`
- end: `0x18007cc5d`
- name: `FltpvUnlinkResourceFromFilter`
- size: `365`
- prototype: ``
- caller_count: `14`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800185f0`
- `0x1800243a0`
- `0x18007e5d0`
- `0x18007e650`
- `0x18007e6d0`
- `0x180080080`
- `0x1800800c0`
- `0x180080210`
- `0x180082930`
- `0x1800829c0`
- `0x180082a60`
- `0x180083a00`
- `0x1800858c0`
- `0x180085940`

## callees

- `0x18000d270`
- `0x1800139a0`
- `0x18007c010`
- `0x18007caf0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18007cc43`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18007cc43`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18007cb28`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18007cb28`
- `ntoskrnl!KeReleaseSpinLock` at `0x18007cc21`
- `ntoskrnl!KeReleaseSpinLock` at `0x18007cc21`

## pseudocode

```c
void __fastcall FltpvUnlinkResourceFromFilter(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rsi
  char v6; // r14
  KIRQL v7; // r15
  __int64 v8; // rax
  __int64 v9; // r9
  void *v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+20h] [rbp-48h]
  int v16; // [rsp+20h] [rbp-48h]

  v3 = a3;
  if ( a1 )
  {
    v6 = 0;
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 240) + 1032LL));
    v8 = TreeLookup(*(_QWORD *)(a1 + 240) + 1024LL, a2, 0, *(_QWORD *)(a1 + 240));
    v10 = (void *)v8;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 72), 0xFFFFFFFF) == 1 )
      {
        TreeUnlink(v8);
        v6 = 1;
      }
      --*(_DWORD *)(*(_QWORD *)(a1 + 240) + 4 * v3 + 1040);
    }
    else
    {
      ++*(_DWORD *)(v9 + 1088);
      v11 = *(_QWORD *)(a1 + 240);
      if ( (*(_DWORD *)v11 & 1) != 0 )
      {
        FltpvPrintErrors(42, a1, *(_QWORD *)(v11 + 872), *(unsigned int *)(v11 + 1084), *(_DWORD *)(v11 + 1088));
        FltpvPrintErrors(43, v12, v13, v14, v16);
      }
      if ( dword_18003FD90 > 0 )
        FltpvPrintErrors(44, (unsigned int)dword_18003FD90, (unsigned int)dword_18003FD94, v9, v15);
      FltpvPrintErrors(41, a1, *(_QWORD *)(*(_QWORD *)(a1 + 240) + 872LL), VerifierObjectTypeNames[v3], a2);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 240) + 1032LL), v7);
    if ( v6 )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 240) + 896LL), v10);
  }
  else
  {
    _InterlockedIncrement(&dword_18003FD94);
  }
}

```

## disassembly

```asm
0x18007caf0  push    rbx
0x18007caf2  push    rbp
0x18007caf3  push    rsi
0x18007caf4  push    rdi
0x18007caf5  push    r14
0x18007caf7  push    r15
0x18007caf9  sub     rsp, 38h
0x18007cafd  mov     esi, r8d
0x18007cb00  mov     rbp, rdx
0x18007cb03  mov     rbx, rcx
0x18007cb06  test    rcx, rcx
0x18007cb09  jnz     short loc_18007CB17
0x18007cb0b  lock inc cs:dword_18003FD94
0x18007cb12  jmp     loc_18007CC4F
0x18007cb17  mov     rcx, [rcx+0F0h]
0x18007cb1e  xor     r14b, r14b
0x18007cb21  add     rcx, 408h; SpinLock
0x18007cb28  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18007cb2f  nop     dword ptr [rax+rax+00h]
0x18007cb34  mov     r9, [rbx+0F0h]
0x18007cb3b  xor     r8d, r8d
0x18007cb3e  mov     rdx, rbp
0x18007cb41  mov     r15b, al
0x18007cb44  lea     rcx, [r9+400h]
0x18007cb4b  call    TreeLookup
0x18007cb50  mov     rdi, rax
0x18007cb53  test    rax, rax
0x18007cb56  jnz     loc_18007CBEA
0x18007cb5c  inc     dword ptr [r9+440h]
0x18007cb63  mov     r8, [rbx+0F0h]
0x18007cb6a  mov     eax, [r8]
0x18007cb6d  test    al, 1
0x18007cb6f  jz      short loc_18007CB9D
0x18007cb71  mov     eax, [r8+440h]
0x18007cb78  lea     ecx, [rdi+2Ah]
0x18007cb7b  mov     r9d, [r8+43Ch]
0x18007cb82  mov     rdx, rbx
0x18007cb85  mov     r8, [r8+368h]
0x18007cb8c  mov     dword ptr [rsp+68h+var_48], eax
0x18007cb90  call    FltpvPrintErrors
0x18007cb95  lea     ecx, [rdi+2Bh]
0x18007cb98  call    FltpvPrintErrors
0x18007cb9d  mov     edx, cs:dword_18003FD90
0x18007cba3  test    edx, edx
0x18007cba5  jle     short loc_18007CBB8
0x18007cba7  mov     r8d, cs:dword_18003FD94
0x18007cbae  mov     ecx, 2Ch ; ','
0x18007cbb3  call    FltpvPrintErrors
0x18007cbb8  mov     r8, [rbx+0F0h]
0x18007cbbf  lea     rax, VerifierObjectTypeNames
0x18007cbc6  mov     r9, [rax+rsi*8]
0x18007cbca  mov     rdx, rbx
0x18007cbcd  mov     [rsp+68h+var_40], rbx
0x18007cbd2  mov     ecx, 29h ; ')'
0x18007cbd7  mov     [rsp+68h+var_48], rbp
0x18007cbdc  mov     r8, [r8+368h]
0x18007cbe3  call    FltpvPrintErrors
0x18007cbe8  jmp     short loc_18007CC10
0x18007cbea  or      eax, 0FFFFFFFFh
0x18007cbed  lock xadd [rdi+48h], eax
0x18007cbf2  cmp     eax, 1
0x18007cbf5  jnz     short loc_18007CC02
0x18007cbf7  mov     rcx, rdi
0x18007cbfa  call    TreeUnlink
0x18007cbff  mov     r14b, 1
0x18007cc02  mov     rax, [rbx+0F0h]
0x18007cc09  dec     dword ptr [rax+rsi*4+410h]
0x18007cc10  mov     rcx, [rbx+0F0h]
0x18007cc17  mov     dl, r15b; NewIrql
0x18007cc1a  add     rcx, 408h; SpinLock
0x18007cc21  call    cs:__imp_KeReleaseSpinLock
0x18007cc28  nop     dword ptr [rax+rax+00h]
0x18007cc2d  test    r14b, r14b
0x18007cc30  jz      short loc_18007CC4F
0x18007cc32  mov     rcx, [rbx+0F0h]
0x18007cc39  mov     rdx, rdi; Entry
0x18007cc3c  add     rcx, 380h; Lookaside
0x18007cc43  call    cs:__imp_ExFreeToNPagedLookasideList
0x18007cc4a  nop     dword ptr [rax+rax+00h]
0x18007cc4f  add     rsp, 38h
0x18007cc53  pop     r15
0x18007cc55  pop     r14
0x18007cc57  pop     rdi
0x18007cc58  pop     rsi
0x18007cc59  pop     rbp
0x18007cc5a  pop     rbx
0x18007cc5b  retn
```
