# WskAcceptCompletion

- ea: `0x14001c4f0`
- end: `0x14001c5b9`
- name: `WskAcceptCompletion`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007710`
- `0x14001c4f0`
- `0x14001c7d0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001c597`
- `ntoskrnl!IoFreeIrp` at `0x14001c597`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c534`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c534`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c516`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c516`

## pseudocode

```c
__int64 __fastcall WskAcceptCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  int Status; // ebx
  KSPIN_LOCK *v6; // rbx
  KIRQL v7; // al

  Status = a2->IoStatus.Status;
  if ( Status >= 0 )
  {
    v6 = (KSPIN_LOCK *)(a3 + 456);
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 456));
    *(_DWORD *)(a3 + 392) |= 0x20u;
    *(_BYTE *)(a3 + 464) = v7;
    KeReleaseSpinLock(v6, v7);
    Status = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(a3 + 32))(
               *(_QWORD *)(*(_QWORD *)(a3 + 504) + 8LL),
               a3 + 472,
               a3,
               a3 + 8);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 512), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64))(a3 + 520))(a3);
  if ( Status < 0 )
    WskCloseSocketContextAndFreeSocketEx(a3, 0, 0);
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001c4f0  mov     [rsp+arg_0], rbx
0x14001c4f5  mov     [rsp+arg_10], rsi
0x14001c4fa  push    rdi
0x14001c4fb  sub     rsp, 30h
0x14001c4ff  mov     ebx, [rdx+30h]
0x14001c502  mov     rdi, r8
0x14001c505  mov     rsi, rdx
0x14001c508  test    ebx, ebx
0x14001c50a  js      short loc_14001C564
0x14001c50c  lea     rbx, [r8+1C8h]
0x14001c513  mov     rcx, rbx; SpinLock
0x14001c516  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001c51d  nop     dword ptr [rax+rax+00h]
0x14001c522  or      dword ptr [rdi+188h], 20h
0x14001c529  mov     rcx, rbx; SpinLock
0x14001c52c  mov     dl, al; NewIrql
0x14001c52e  mov     [rdi+1D0h], al
0x14001c534  call    cs:__imp_KeReleaseSpinLock
0x14001c53b  nop     dword ptr [rax+rax+00h]
0x14001c540  mov     rcx, [rdi+1F8h]
0x14001c547  lea     r9, [rdi+8]
0x14001c54b  mov     rax, [rdi+20h]
0x14001c54f  lea     rdx, [rdi+1D8h]
0x14001c556  mov     r8, rdi
0x14001c559  mov     rcx, [rcx+8]
0x14001c55d  call    _guard_dispatch_icall
0x14001c562  mov     ebx, eax
0x14001c564  or      eax, 0FFFFFFFFh
0x14001c567  lock xadd [rdi+200h], eax
0x14001c56f  cmp     eax, 1
0x14001c572  jnz     short loc_14001C583
0x14001c574  mov     rax, [rdi+208h]
0x14001c57b  mov     rcx, rdi
0x14001c57e  call    _guard_dispatch_icall
0x14001c583  test    ebx, ebx
0x14001c585  jns     short loc_14001C594
0x14001c587  xor     r8d, r8d
0x14001c58a  xor     edx, edx
0x14001c58c  mov     rcx, rdi
0x14001c58f  call    WskCloseSocketContextAndFreeSocketEx
0x14001c594  mov     rcx, rsi; Irp
0x14001c597  call    cs:__imp_IoFreeIrp
0x14001c59e  nop     dword ptr [rax+rax+00h]
0x14001c5a3  mov     rbx, [rsp+38h+arg_0]
0x14001c5a8  mov     eax, 0C0000016h
0x14001c5ad  mov     rsi, [rsp+38h+arg_10]
0x14001c5b2  add     rsp, 30h
0x14001c5b6  pop     rdi
0x14001c5b7  retn
```
