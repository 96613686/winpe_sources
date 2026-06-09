# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000724c`
- end: `0x180007309`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002160`
- `0x180002190`
- `0x180002240`
- `0x18000aea0`

## callees

- `0x18000724c`
- `0x180019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007292`
- `KERNEL32!EnterCriticalSection` at `0x180007292`
- `KERNEL32!LeaveCriticalSection` at `0x1800072f1`
- `KERNEL32!LeaveCriticalSection` at `0x1800072f1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800072d3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800072d3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000729b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000729b`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000727c`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000727c`
- `KERNEL32!AcquireSRWLockShared` at `0x180007262`
- `KERNEL32!AcquireSRWLockShared` at `0x180007262`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // r14
  __int64 v7; // r15
  unsigned __int64 v8; // rax
  WORD *v9; // rcx

  AcquireSRWLockShared(SRWLock);
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    AcquireSRWLockExclusive(SRWLock);
    if ( v5 < v4 )
    {
      while ( 1 )
      {
        v8 = v5 + 1;
        v9 = &lpCriticalSection[1].DebugInfo->Type + 8 * v5++;
        if ( *(_QWORD *)v9 )
          break;
        if ( v8 >= v4 )
          goto LABEL_9;
      }
      v6 = *(void (__fastcall **)(__int64))v9;
      v7 = *((_QWORD *)v9 + 1);
    }
LABEL_9:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( v6 )
      v6(v7);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x18000724c  push    rbx
0x18000724e  push    rbp
0x18000724f  push    rsi
0x180007250  push    rdi
0x180007251  push    r14
0x180007253  push    r15
0x180007255  sub     rsp, 28h
0x180007259  mov     rsi, rcx
0x18000725c  mov     rbp, rdx
0x18000725f  mov     rcx, rdx; SRWLock
0x180007262  call    cs:__imp_AcquireSRWLockShared
0x180007268  mov     rdi, [rsi+30h]
0x18000726c  sub     rdi, [rsi+28h]
0x180007270  shr     rdi, 4
0x180007274  test    rbp, rbp
0x180007277  jz      short loc_180007282
0x180007279  mov     rcx, rbp; SRWLock
0x18000727c  call    cs:__imp_ReleaseSRWLockShared
0x180007282  xor     ebx, ebx
0x180007284  test    rdi, rdi
0x180007287  jz      short loc_1800072FC
0x180007289  mov     rcx, rsi; lpCriticalSection
0x18000728c  xor     r14d, r14d
0x18000728f  xor     r15d, r15d
0x180007292  call    cs:__imp_EnterCriticalSection
0x180007298  mov     rcx, rbp; SRWLock
0x18000729b  call    cs:__imp_AcquireSRWLockExclusive
0x1800072a1  cmp     rbx, rdi
0x1800072a4  jnb     short loc_1800072CB
0x1800072a6  mov     rdx, [rsi+28h]
0x1800072aa  lea     rax, [rbx+1]
0x1800072ae  add     rbx, rbx
0x1800072b1  lea     rcx, [rdx+rbx*8]
0x1800072b5  mov     rbx, rax
0x1800072b8  cmp     [rcx], r14
0x1800072bb  jnz     short loc_1800072C4
0x1800072bd  cmp     rax, rdi
0x1800072c0  jb      short loc_1800072AA
0x1800072c2  jmp     short loc_1800072CB
0x1800072c4  mov     r14, [rcx]
0x1800072c7  mov     r15, [rcx+8]
0x1800072cb  test    rbp, rbp
0x1800072ce  jz      short loc_1800072D9
0x1800072d0  mov     rcx, rbp; SRWLock
0x1800072d3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800072d9  test    r14, r14
0x1800072dc  jz      short loc_1800072E9
0x1800072de  mov     rcx, r15
0x1800072e1  mov     rax, r14
0x1800072e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e9  test    rsi, rsi
0x1800072ec  jz      short loc_1800072F7
0x1800072ee  mov     rcx, rsi; lpCriticalSection
0x1800072f1  call    cs:__imp_LeaveCriticalSection
0x1800072f7  cmp     rbx, rdi
0x1800072fa  jb      short loc_180007289
0x1800072fc  add     rsp, 28h
0x180007300  pop     r15
0x180007302  pop     r14
0x180007304  pop     rdi
0x180007305  pop     rsi
0x180007306  pop     rbp
0x180007307  pop     rbx
0x180007308  retn
```
