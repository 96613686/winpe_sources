# FltpDeleteContextNodeFromList

- ea: `0x18000d2c0`
- end: `0x18000d452`
- name: `FltpDeleteContextNodeFromList`
- size: `402`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e5e0`

## callees

- `0x18000d2c0`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x18000d2d8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000d2d8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000d349`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000d37f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000d42a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000d349`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000d37f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000d42a`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000d2e9`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000d2e9`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000d33d`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000d373`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000d41e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000d33d`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000d373`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000d41e`
- `ntoskrnl!RtlDelete` at `0x18000d318`
- `ntoskrnl!RtlDelete` at `0x18000d318`

## pseudocode

```c
__int64 __fastcall FltpDeleteContextNodeFromList(__int64 a1, __int64 a2, __int64 a3)
{
  PRTL_SPLAY_LINKS *v6; // rdi
  __int64 v8; // rax
  _QWORD *v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // rbx

  KeEnterGuardedRegion();
  ExAcquireAutoExpandPushLockExclusive(a2, 0);
  if ( FltpVelocity
    && (*(_QWORD *)(a3 + 48) != 51918 || a3 != *(_QWORD *)(a3 + 40) ? (v8 = 0) : (v8 = *(_QWORD *)(a3 + 24)),
        v8 == a1 && (v9 = *(_QWORD **)(a3 + 32)) != 0) )
  {
    do
    {
      _m_prefetchw(v9);
      v10 = 0;
      if ( (_InterlockedOr64(v9, 1u) & 1) == 0 )
        v10 = v9;
    }
    while ( !v10 );
    v11 = v9[1];
    v9[1] = 0;
    _InterlockedAnd64(v9, 0);
    *(_DWORD *)(v11 + 72) &= ~0x10000u;
    *(_QWORD *)(v11 + 48) = 0;
    *(_OWORD *)(v11 + 24) = 0;
    *(_QWORD *)(v11 + 40) = 0;
    ExReleaseAutoExpandPushLockExclusive(a2, 0);
    KeLeaveGuardedRegion();
    return v11;
  }
  else if ( (*(_DWORD *)(a3 + 72) & 0x10000) != 0 )
  {
    v6 = *(PRTL_SPLAY_LINKS **)(a3 + 48);
    *v6 = RtlDelete((PRTL_SPLAY_LINKS)(a3 + 24));
    if ( (*(_DWORD *)(a3 + 72) & 0x10000) != 0 )
      _InterlockedAnd((volatile signed __int32 *)(a3 + 72), 0xFFFEFFFF);
    ExReleaseAutoExpandPushLockExclusive(a2, 0);
    KeLeaveGuardedRegion();
    return a3;
  }
  else
  {
    ExReleaseAutoExpandPushLockExclusive(a2, 0);
    KeLeaveGuardedRegion();
    return 0;
  }
}

```

## disassembly

```asm
0x18000d2c0  mov     [rsp+arg_8], rbx
0x18000d2c5  mov     [rsp+arg_10], rbp
0x18000d2ca  push    rdi
0x18000d2cb  sub     rsp, 20h
0x18000d2cf  mov     rbx, r8
0x18000d2d2  mov     rbp, rdx
0x18000d2d5  mov     rdi, rcx
0x18000d2d8  call    cs:__imp_KeEnterGuardedRegion
0x18000d2df  nop     dword ptr [rax+rax+00h]
0x18000d2e4  xor     edx, edx
0x18000d2e6  mov     rcx, rbp
0x18000d2e9  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x18000d2f0  nop     dword ptr [rax+rax+00h]
0x18000d2f5  cmp     cs:FltpVelocity, 0
0x18000d2fc  jnz     loc_18000D39E
0x18000d302  test    dword ptr [rbx+48h], 10000h
0x18000d309  jz      short loc_18000D36E
0x18000d30b  mov     rdi, [rbx+30h]
0x18000d30f  lea     rcx, [rbx+18h]; Links
0x18000d313  mov     [rsp+28h+arg_0], rsi
0x18000d318  call    cs:__imp_RtlDelete
0x18000d31f  nop     dword ptr [rax+rax+00h]
0x18000d324  mov     [rdi], rax
0x18000d327  mov     eax, [rbx+48h]
0x18000d32a  bt      eax, 10h
0x18000d32e  jnb     short loc_18000D338
0x18000d330  lock and dword ptr [rbx+48h], 0FFFEFFFFh
0x18000d338  xor     edx, edx
0x18000d33a  mov     rcx, rbp
0x18000d33d  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000d344  nop     dword ptr [rax+rax+00h]
0x18000d349  call    cs:__imp_KeLeaveGuardedRegion
0x18000d350  nop     dword ptr [rax+rax+00h]
0x18000d355  mov     rsi, [rsp+28h+arg_0]
0x18000d35a  mov     rax, rbx
0x18000d35d  mov     rbx, [rsp+28h+arg_8]
0x18000d362  mov     rbp, [rsp+28h+arg_10]
0x18000d367  add     rsp, 20h
0x18000d36b  pop     rdi
0x18000d36c  retn
0x18000d36e  xor     edx, edx
0x18000d370  mov     rcx, rbp
0x18000d373  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000d37a  nop     dword ptr [rax+rax+00h]
0x18000d37f  call    cs:__imp_KeLeaveGuardedRegion
0x18000d386  nop     dword ptr [rax+rax+00h]
0x18000d38b  xor     eax, eax
0x18000d38d  mov     rbx, [rsp+28h+arg_8]
0x18000d392  mov     rbp, [rsp+28h+arg_10]
0x18000d397  add     rsp, 20h
0x18000d39b  pop     rdi
0x18000d39c  retn
0x18000d39e  xor     r8d, r8d
0x18000d3a1  cmp     qword ptr [rbx+30h], 0CACEh
0x18000d3a9  jnz     loc_18000D44A
0x18000d3af  cmp     rbx, [rbx+28h]
0x18000d3b3  jnz     loc_18000D44A
0x18000d3b9  mov     rax, [rbx+18h]
0x18000d3bd  cmp     rax, rdi
0x18000d3c0  jnz     loc_18000D302
0x18000d3c6  mov     rdx, [rbx+20h]
0x18000d3ca  test    rdx, rdx
0x18000d3cd  jz      loc_18000D302
0x18000d3d3  prefetchw byte ptr [rdx]
0x18000d3d6  mov     rax, [rdx]
0x18000d3d9  mov     rcx, rax
0x18000d3dc  or      rcx, 1
0x18000d3e0  lock cmpxchg [rdx], rcx
0x18000d3e5  jnz     short loc_18000D3D9
0x18000d3e7  test    al, 1
0x18000d3e9  mov     rax, r8
0x18000d3ec  cmovz   rax, rdx
0x18000d3f0  test    rax, rax
0x18000d3f3  jz      short loc_18000D3D3
0x18000d3f5  mov     rbx, [rdx+8]
0x18000d3f9  mov     [rdx+8], r8
0x18000d3fd  lock and [rdx], r8
0x18000d401  and     dword ptr [rbx+48h], 0FFFEFFFFh
0x18000d408  xorps   xmm0, xmm0
0x18000d40b  xor     eax, eax
0x18000d40d  mov     [rbx+30h], r8
0x18000d411  movups  xmmword ptr [rbx+18h], xmm0
0x18000d415  xor     edx, edx
0x18000d417  mov     [rbx+28h], rax
0x18000d41b  mov     rcx, rbp
0x18000d41e  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000d425  nop     dword ptr [rax+rax+00h]
0x18000d42a  call    cs:__imp_KeLeaveGuardedRegion
0x18000d431  nop     dword ptr [rax+rax+00h]
0x18000d436  mov     rbp, [rsp+28h+arg_10]
0x18000d43b  mov     rax, rbx
0x18000d43e  mov     rbx, [rsp+28h+arg_8]
0x18000d443  add     rsp, 20h
0x18000d447  pop     rdi
0x18000d448  retn
0x18000d44a  mov     rax, r8
0x18000d44d  jmp     loc_18000D3BD
```
