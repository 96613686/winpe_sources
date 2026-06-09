# PcpRemoveFilterByHandle32

- ea: `0x14000e9fc`
- end: `0x14000eae4`
- name: `PcpRemoveFilterByHandle32`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001d7cc`

## callees

- `0x140007e10`
- `0x14000e9fc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000eac4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eac4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ea35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ea35`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000eaa2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000eaa2`

## pseudocode

```c
__int64 __fastcall PcpRemoveFilterByHandle32(int a1, __int64 a2, __int64 **a3)
{
  KSPIN_LOCK *v3; // rsi
  __int64 **v5; // r14
  unsigned int v7; // edi
  KIRQL v8; // al
  __int64 *v9; // rbx
  KIRQL v10; // r15
  __int64 *v11; // rbp
  __int64 *v12; // rdx
  __int64 *v13; // rcx
  __int64 *v14; // rax
  __int64 **v15; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-68h] BYREF

  v3 = (KSPIN_LOCK *)(a2 + 32);
  *(_QWORD *)&LockHandle.OldIrql = 0;
  *a3 = 0;
  v5 = (__int64 **)(a2 + 16);
  v7 = -1073741275;
  LockHandle.LockQueue = 0;
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  v9 = *v5;
  v10 = v8;
  while ( v9 != (__int64 *)v5 )
  {
    v11 = (__int64 *)*v9;
    RtlAcquireWriteLockAtDpcLevel((__int64)(v9 + 10), &LockHandle);
    v12 = (__int64 *)v9[69];
    while ( v12 != v9 + 69 )
    {
      v13 = (__int64 *)*v12;
      v14 = v12;
      v12 = (__int64 *)*v12;
      if ( *((_DWORD *)v14 + 10) == a1 )
      {
        if ( (__int64 *)v13[1] != v14 || (v15 = (__int64 **)v14[1], *v15 != v14) )
          __fastfail(3u);
        *v15 = v13;
        v13[1] = (__int64)v15;
        --*((_DWORD *)v9 + 142);
        v7 = 0;
        *a3 = v14;
        break;
      }
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    if ( !v7 )
      break;
    v9 = v11;
  }
  KeReleaseSpinLock(v3, v10);
  return v7;
}

```

## disassembly

```asm
0x14000e9fc  push    rbx
0x14000e9fe  push    rbp
0x14000e9ff  push    rsi
0x14000ea00  push    rdi
0x14000ea01  push    r12
0x14000ea03  push    r13
0x14000ea05  push    r14
0x14000ea07  push    r15
0x14000ea09  sub     rsp, 48h
0x14000ea0d  xor     eax, eax
0x14000ea0f  lea     rsi, [rdx+20h]
0x14000ea13  mov     r13d, ecx
0x14000ea16  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14000ea1b  xorps   xmm0, xmm0
0x14000ea1e  mov     [r8], rax
0x14000ea21  mov     rcx, rsi; SpinLock
0x14000ea24  lea     r14, [rdx+10h]
0x14000ea28  mov     r12, r8
0x14000ea2b  mov     edi, 0C0000225h
0x14000ea30  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14000ea35  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ea3c  nop     dword ptr [rax+rax+00h]
0x14000ea41  mov     rbx, [r14]
0x14000ea44  mov     r15b, al
0x14000ea47  cmp     rbx, r14
0x14000ea4a  jz      short loc_14000EABE
0x14000ea4c  mov     rbp, [rbx]
0x14000ea4f  lea     rcx, [rbx+50h]
0x14000ea53  lea     rdx, [rsp+88h+LockHandle]
0x14000ea58  call    RtlAcquireWriteLockAtDpcLevel
0x14000ea5d  lea     r8, [rbx+228h]
0x14000ea64  mov     rdx, [r8]
0x14000ea67  cmp     rdx, r8
0x14000ea6a  jz      short loc_14000EA9D
0x14000ea6c  mov     rcx, [rdx]
0x14000ea6f  mov     rax, rdx
0x14000ea72  mov     rdx, rcx
0x14000ea75  cmp     [rax+28h], r13d
0x14000ea79  jnz     short loc_14000EA67
0x14000ea7b  cmp     [rcx+8], rax
0x14000ea7f  jnz     short loc_14000EAB7
0x14000ea81  mov     rdx, [rax+8]
0x14000ea85  cmp     [rdx], rax
0x14000ea88  jnz     short loc_14000EAB7
0x14000ea8a  mov     [rdx], rcx
0x14000ea8d  mov     [rcx+8], rdx
0x14000ea91  dec     dword ptr [rbx+238h]
0x14000ea97  xor     edi, edi
0x14000ea99  mov     [r12], rax
0x14000ea9d  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14000eaa2  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000eaa9  nop     dword ptr [rax+rax+00h]
0x14000eaae  test    edi, edi
0x14000eab0  jz      short loc_14000EABE
0x14000eab2  mov     rbx, rbp
0x14000eab5  jmp     short loc_14000EA47
0x14000eab7  mov     ecx, 3
0x14000eabc  int     29h; Win8: RtlFailFast(ecx)
0x14000eabe  mov     dl, r15b; NewIrql
0x14000eac1  mov     rcx, rsi; SpinLock
0x14000eac4  call    cs:__imp_KeReleaseSpinLock
0x14000eacb  nop     dword ptr [rax+rax+00h]
0x14000ead0  mov     eax, edi
0x14000ead2  add     rsp, 48h
0x14000ead6  pop     r15
0x14000ead8  pop     r14
0x14000eada  pop     r13
0x14000eadc  pop     r12
0x14000eade  pop     rdi
0x14000eadf  pop     rsi
0x14000eae0  pop     rbp
0x14000eae1  pop     rbx
0x14000eae2  retn
```
