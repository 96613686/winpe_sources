# PcpRemoveFilter

- ea: `0x14000e91c`
- end: `0x14000e9f5`
- name: `PcpRemoveFilter`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001d708`

## callees

- `0x140007e10`
- `0x14000e91c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000e9d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e9d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e94d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e94d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000e9b5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000e9b5`

## pseudocode

```c
__int64 __fastcall PcpRemoveFilter(__int64 *a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rsi
  __int64 **v4; // r14
  unsigned int v5; // edi
  KIRQL v6; // al
  __int64 *v7; // rbx
  KIRQL v8; // r15
  __int64 *v9; // rbp
  __int64 *v10; // rdx
  __int64 *v11; // rcx
  __int64 *v12; // rax
  __int64 **v13; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-58h] BYREF

  v2 = (KSPIN_LOCK *)(a2 + 32);
  v4 = (__int64 **)(a2 + 16);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = -1073741275;
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  v7 = *v4;
  v8 = v6;
  while ( v7 != (__int64 *)v4 )
  {
    v9 = (__int64 *)*v7;
    RtlAcquireWriteLockAtDpcLevel((__int64)(v7 + 10), &LockHandle);
    v10 = (__int64 *)v7[69];
    while ( v10 != v7 + 69 )
    {
      v11 = (__int64 *)*v10;
      v12 = v10;
      v10 = (__int64 *)*v10;
      if ( v12 == a1 )
      {
        if ( (__int64 *)v11[1] != v12 || (v13 = (__int64 **)v12[1], *v13 != v12) )
          __fastfail(3u);
        *v13 = v11;
        v11[1] = (__int64)v13;
        --*((_DWORD *)v7 + 142);
        v5 = 0;
        break;
      }
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    if ( !v5 )
      break;
    v7 = v9;
  }
  KeReleaseSpinLock(v2, v8);
  return v5;
}

```

## disassembly

```asm
0x14000e91c  push    rbx
0x14000e91e  push    rbp
0x14000e91f  push    rsi
0x14000e920  push    rdi
0x14000e921  push    r12
0x14000e923  push    r14
0x14000e925  push    r15
0x14000e927  sub     rsp, 40h
0x14000e92b  lea     rsi, [rdx+20h]
0x14000e92f  mov     r12, rcx
0x14000e932  xorps   xmm0, xmm0
0x14000e935  lea     r14, [rdx+10h]
0x14000e939  xor     eax, eax
0x14000e93b  mov     rcx, rsi; SpinLock
0x14000e93e  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14000e943  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14000e948  mov     edi, 0C0000225h
0x14000e94d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e954  nop     dword ptr [rax+rax+00h]
0x14000e959  mov     rbx, [r14]
0x14000e95c  mov     r15b, al
0x14000e95f  cmp     rbx, r14
0x14000e962  jz      short loc_14000E9D1
0x14000e964  mov     rbp, [rbx]
0x14000e967  lea     rcx, [rbx+50h]
0x14000e96b  lea     rdx, [rsp+78h+LockHandle]
0x14000e970  call    RtlAcquireWriteLockAtDpcLevel
0x14000e975  lea     r8, [rbx+228h]
0x14000e97c  mov     rdx, [r8]
0x14000e97f  cmp     rdx, r8
0x14000e982  jz      short loc_14000E9B0
0x14000e984  mov     rcx, [rdx]
0x14000e987  mov     rax, rdx
0x14000e98a  mov     rdx, rcx
0x14000e98d  cmp     rax, r12
0x14000e990  jnz     short loc_14000E97F
0x14000e992  cmp     [rcx+8], rax
0x14000e996  jnz     short loc_14000E9CA
0x14000e998  mov     rdx, [rax+8]
0x14000e99c  cmp     [rdx], rax
0x14000e99f  jnz     short loc_14000E9CA
0x14000e9a1  mov     [rdx], rcx
0x14000e9a4  mov     [rcx+8], rdx
0x14000e9a8  dec     dword ptr [rbx+238h]
0x14000e9ae  xor     edi, edi
0x14000e9b0  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000e9b5  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000e9bc  nop     dword ptr [rax+rax+00h]
0x14000e9c1  test    edi, edi
0x14000e9c3  jz      short loc_14000E9D1
0x14000e9c5  mov     rbx, rbp
0x14000e9c8  jmp     short loc_14000E95F
0x14000e9ca  mov     ecx, 3
0x14000e9cf  int     29h; Win8: RtlFailFast(ecx)
0x14000e9d1  mov     dl, r15b; NewIrql
0x14000e9d4  mov     rcx, rsi; SpinLock
0x14000e9d7  call    cs:__imp_KeReleaseSpinLock
0x14000e9de  nop     dword ptr [rax+rax+00h]
0x14000e9e3  mov     eax, edi
0x14000e9e5  add     rsp, 40h
0x14000e9e9  pop     r15
0x14000e9eb  pop     r14
0x14000e9ed  pop     r12
0x14000e9ef  pop     rdi
0x14000e9f0  pop     rsi
0x14000e9f1  pop     rbp
0x14000e9f2  pop     rbx
0x14000e9f3  retn
```
