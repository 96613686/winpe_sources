# VmbusTlStartCancelConnection

- ea: `0x1400073d0`
- end: `0x14000749c`
- name: `VmbusTlStartCancelConnection`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400209c0`

## callees

- `0x1400073d0`
- `0x14000a048`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400073ee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400073ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000747d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000747d`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140007409`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140007409`

## pseudocode

```c
__int64 __fastcall VmbusTlStartCancelConnection(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rdi
  KIRQL v4; // si
  __int64 v5; // rbx
  unsigned int v6; // ebx
  __int64 Buffer; // [rsp+48h] [rbp+10h] BYREF

  Buffer = a2;
  v2 = (KSPIN_LOCK *)(a1 + 72);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  if ( RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 1016), &Buffer) )
  {
    v5 = Buffer;
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlStartCancelConnection",
        762,
        Buffer,
        *(_QWORD *)(Buffer + 304),
        (__int64)"Cancel reference.");
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v5 + 304)) <= 1 )
      __fastfail(0xEu);
    v6 = 0;
  }
  else
  {
    v6 = -1073741275;
  }
  KeReleaseSpinLock(v2, v4);
  return v6;
}

```

## disassembly

```asm
0x1400073d0  mov     [rsp+arg_0], rbx
0x1400073d5  mov     [rsp+arg_10], rsi
0x1400073da  mov     [rsp+Buffer], rdx
0x1400073df  push    rdi
0x1400073e0  sub     rsp, 30h
0x1400073e4  lea     rdi, [rcx+48h]
0x1400073e8  mov     rbx, rcx
0x1400073eb  mov     rcx, rdi; SpinLock
0x1400073ee  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400073f5  nop     dword ptr [rax+rax+00h]
0x1400073fa  lea     rcx, [rbx+3F8h]; Table
0x140007401  mov     sil, al
0x140007404  lea     rdx, [rsp+38h+Buffer]; Buffer
0x140007409  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140007410  nop     dword ptr [rax+rax+00h]
0x140007415  test    al, al
0x140007417  jz      short loc_140007472
0x140007419  mov     ecx, cs:dword_140013058
0x14000741f  mov     rbx, [rsp+38h+Buffer]
0x140007424  cmp     ecx, 5
0x140007427  jbe     short loc_140007450
0x140007429  mov     r9, [rbx+130h]
0x140007430  lea     rax, aCancelReferenc; "Cancel reference."
0x140007437  mov     r8, rbx
0x14000743a  mov     [rsp+38h+var_18], rax
0x14000743f  mov     edx, 2FAh
0x140007444  lea     rcx, aVmbustlstartca; "VmbusTlStartCancelConnection"
0x14000744b  call    HvsocketTraceReferenceCount
0x140007450  mov     eax, 1
0x140007455  lock xadd [rbx+130h], rax
0x14000745e  inc     rax
0x140007461  cmp     rax, 1
0x140007465  jg      short loc_14000746E
0x140007467  mov     ecx, 0Eh
0x14000746c  int     29h; Win8: RtlFailFast(ecx)
0x14000746e  xor     ebx, ebx
0x140007470  jmp     short loc_140007477
0x140007472  mov     ebx, 0C0000225h
0x140007477  mov     dl, sil; NewIrql
0x14000747a  mov     rcx, rdi; SpinLock
0x14000747d  call    cs:__imp_KeReleaseSpinLock
0x140007484  nop     dword ptr [rax+rax+00h]
0x140007489  mov     rsi, [rsp+38h+arg_10]
0x14000748e  mov     eax, ebx
0x140007490  mov     rbx, [rsp+38h+arg_0]
0x140007495  add     rsp, 30h
0x140007499  pop     rdi
0x14000749a  retn
```
