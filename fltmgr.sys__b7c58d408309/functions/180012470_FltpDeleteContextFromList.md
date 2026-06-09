# FltpDeleteContextFromList

- ea: `0x180012470`
- end: `0x180012601`
- name: `FltpDeleteContextFromList`
- size: `401`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800123e0`
- `0x180012610`
- `0x18004f410`

## callees

- `0x180012470`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x180012487`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180012487`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800124df`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001254e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800125ed`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800124df`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001254e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800125ed`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x180012498`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x180012498`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1800124d3`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180012542`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1800125e1`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1800124d3`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180012542`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1800125e1`
- `ntoskrnl!RtlDelete` at `0x18001251d`
- `ntoskrnl!RtlDelete` at `0x18001251d`

## pseudocode

```c
__int64 __fastcall FltpDeleteContextFromList(__int64 a1, __int64 a2, unsigned __int64 a3, unsigned __int64 a4)
{
  __int64 v8; // rbx
  bool v9; // cf
  PRTL_SPLAY_LINKS *v11; // rdi
  signed __int64 v12; // r8
  unsigned int i; // edx
  __int64 v14; // rcx
  signed __int64 v15; // rax
  __int64 v16; // r14

  KeEnterGuardedRegion();
  ExAcquireAutoExpandPushLockExclusive(a2, 0);
  if ( FltpVelocity )
  {
    v12 = a3 | 1;
    for ( i = 0; i < 8; ++i )
    {
      v14 = a1 + 16LL * i;
      do
        v15 = _InterlockedCompareExchange64((volatile signed __int64 *)v14, v12, a3);
      while ( v15 == v12 );
      if ( v15 == a3 )
      {
        v16 = *(_QWORD *)(v14 + 8);
        if ( v16 && (a4 == -1 || a4 == *(_QWORD *)(v16 + 64)) )
        {
          *(_QWORD *)(v14 + 8) = 0;
          _InterlockedAnd64((volatile signed __int64 *)v14, 0);
          *(_DWORD *)(v16 + 72) &= ~0x10000u;
          *(_QWORD *)(v16 + 48) = 0;
          *(_OWORD *)(v16 + 24) = 0;
          *(_QWORD *)(v16 + 40) = 0;
          ExReleaseAutoExpandPushLockExclusive(a2, 0);
          KeLeaveGuardedRegion();
          return v16;
        }
        _InterlockedAnd64((volatile signed __int64 *)v14, 0xFFFFFFFFFFFFFFFEuLL);
      }
    }
  }
  v8 = *(_QWORD *)(a1 + 128);
  if ( !v8 )
  {
LABEL_7:
    ExReleaseAutoExpandPushLockExclusive(a2, 0);
    KeLeaveGuardedRegion();
    return 0;
  }
  while ( 1 )
  {
    v9 = a3 < *(_QWORD *)(v8 + 32);
    if ( a3 == *(_QWORD *)(v8 + 32) )
      break;
LABEL_4:
    if ( v9 )
      v8 = *(_QWORD *)(v8 + 8);
    else
      v8 = *(_QWORD *)(v8 + 16);
    if ( !v8 )
      goto LABEL_7;
  }
  if ( a4 != *(_QWORD *)(v8 + 40) && a4 != -1 )
  {
    v9 = a4 < *(_QWORD *)(v8 + 40);
    goto LABEL_4;
  }
  v11 = *(PRTL_SPLAY_LINKS **)(v8 + 24);
  *v11 = RtlDelete((PRTL_SPLAY_LINKS)v8);
  if ( (*(_DWORD *)(v8 + 48) & 0x10000) != 0 )
    _InterlockedAnd((volatile signed __int32 *)(v8 + 48), 0xFFFEFFFF);
  ExReleaseAutoExpandPushLockExclusive(a2, 0);
  KeLeaveGuardedRegion();
  return v8 - 24;
}

```

## disassembly

```asm
0x180012470  push    rbx
0x180012472  push    rbp
0x180012473  push    rsi
0x180012474  push    rdi
0x180012475  push    r14
0x180012477  sub     rsp, 20h
0x18001247b  mov     rsi, r9
0x18001247e  mov     rdi, r8
0x180012481  mov     rbp, rdx
0x180012484  mov     rbx, rcx
0x180012487  call    cs:__imp_KeEnterGuardedRegion
0x18001248e  nop     dword ptr [rax+rax+00h]
0x180012493  xor     edx, edx
0x180012495  mov     rcx, rbp
0x180012498  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x18001249f  nop     dword ptr [rax+rax+00h]
0x1800124a4  cmp     cs:FltpVelocity, 0
0x1800124ab  jnz     loc_18001256A
0x1800124b1  mov     rbx, [rbx+80h]
0x1800124b8  test    rbx, rbx
0x1800124bb  jz      short loc_1800124CE
0x1800124bd  cmp     rdi, [rbx+20h]
0x1800124c1  jz      short loc_1800124F9
0x1800124c3  jb      short loc_18001250B
0x1800124c5  mov     rbx, [rbx+10h]
0x1800124c9  test    rbx, rbx
0x1800124cc  jnz     short loc_1800124BD
0x1800124ce  xor     edx, edx
0x1800124d0  mov     rcx, rbp
0x1800124d3  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x1800124da  nop     dword ptr [rax+rax+00h]
0x1800124df  call    cs:__imp_KeLeaveGuardedRegion
0x1800124e6  nop     dword ptr [rax+rax+00h]
0x1800124eb  xor     eax, eax
0x1800124ed  add     rsp, 20h
0x1800124f1  pop     r14
0x1800124f3  pop     rdi
0x1800124f4  pop     rsi
0x1800124f5  pop     rbp
0x1800124f6  pop     rbx
0x1800124f7  retn
0x1800124f9  cmp     rsi, [rbx+28h]
0x1800124fd  jz      short loc_180012511
0x1800124ff  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180012503  jz      short loc_180012511
0x180012505  cmp     rsi, [rbx+28h]
0x180012509  jmp     short loc_1800124C3
0x18001250b  mov     rbx, [rbx+8]
0x18001250f  jmp     short loc_1800124C9
0x180012511  test    rbx, rbx
0x180012514  jz      short loc_1800124CE
0x180012516  mov     rdi, [rbx+18h]
0x18001251a  mov     rcx, rbx; Links
0x18001251d  call    cs:__imp_RtlDelete
0x180012524  nop     dword ptr [rax+rax+00h]
0x180012529  mov     [rdi], rax
0x18001252c  mov     eax, [rbx+30h]
0x18001252f  bt      eax, 10h
0x180012533  jnb     short loc_18001253D
0x180012535  lock and dword ptr [rbx+30h], 0FFFEFFFFh
0x18001253d  xor     edx, edx
0x18001253f  mov     rcx, rbp
0x180012542  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x180012549  nop     dword ptr [rax+rax+00h]
0x18001254e  call    cs:__imp_KeLeaveGuardedRegion
0x180012555  nop     dword ptr [rax+rax+00h]
0x18001255a  lea     rax, [rbx-18h]
0x18001255e  add     rsp, 20h
0x180012562  pop     r14
0x180012564  pop     rdi
0x180012565  pop     rsi
0x180012566  pop     rbp
0x180012567  pop     rbx
0x180012568  retn
0x18001256a  mov     r8, rdi
0x18001256d  or      r8, 1
0x180012571  xor     edx, edx
0x180012573  cmp     edx, 8
0x180012576  jnb     loc_1800124B1
0x18001257c  mov     ecx, edx
0x18001257e  shl     rcx, 4
0x180012582  add     rcx, rbx
0x180012585  mov     rax, rdi
0x180012588  lock cmpxchg [rcx], r8
0x18001258d  cmp     rax, r8
0x180012590  jz      short loc_180012585
0x180012592  cmp     rax, rdi
0x180012595  jnz     short loc_1800125B1
0x180012597  mov     r14, [rcx+8]
0x18001259b  test    r14, r14
0x18001259e  jz      short loc_1800125AC
0x1800125a0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800125a4  jz      short loc_1800125B5
0x1800125a6  cmp     rsi, [r14+40h]
0x1800125aa  jz      short loc_1800125B5
0x1800125ac  lock and qword ptr [rcx], 0FFFFFFFFFFFFFFFEh
0x1800125b1  inc     edx
0x1800125b3  jmp     short loc_180012573
0x1800125b5  mov     qword ptr [rcx+8], 0
0x1800125bd  lock and qword ptr [rcx], 0
0x1800125c2  and     dword ptr [r14+48h], 0FFFEFFFFh
0x1800125ca  xor     eax, eax
0x1800125cc  xorps   xmm0, xmm0
0x1800125cf  mov     [r14+30h], rax
0x1800125d3  movups  xmmword ptr [r14+18h], xmm0
0x1800125d8  xor     edx, edx
0x1800125da  mov     [r14+28h], rax
0x1800125de  mov     rcx, rbp
0x1800125e1  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x1800125e8  nop     dword ptr [rax+rax+00h]
0x1800125ed  call    cs:__imp_KeLeaveGuardedRegion
0x1800125f4  nop     dword ptr [rax+rax+00h]
0x1800125f9  mov     rax, r14
0x1800125fc  jmp     loc_1800124ED
```
