# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180007f74`
- end: `0x180008031`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039e0`
- `0x180003a10`
- `0x180003ac0`
- `0x18000a030`

## callees

- `0x180007f74`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007fa4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007fa4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007f8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007f8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007fba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007fba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007fc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007fc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008019`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008019`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007ffb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007ffb`

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
0x180007f74  push    rbx
0x180007f76  push    rbp
0x180007f77  push    rsi
0x180007f78  push    rdi
0x180007f79  push    r14
0x180007f7b  push    r15
0x180007f7d  sub     rsp, 28h
0x180007f81  mov     rsi, rcx
0x180007f84  mov     rbp, rdx
0x180007f87  mov     rcx, rdx; SRWLock
0x180007f8a  call    cs:__imp_AcquireSRWLockShared
0x180007f90  mov     rdi, [rsi+30h]
0x180007f94  sub     rdi, [rsi+28h]
0x180007f98  shr     rdi, 4
0x180007f9c  test    rbp, rbp
0x180007f9f  jz      short loc_180007FAA
0x180007fa1  mov     rcx, rbp; SRWLock
0x180007fa4  call    cs:__imp_ReleaseSRWLockShared
0x180007faa  xor     ebx, ebx
0x180007fac  test    rdi, rdi
0x180007faf  jz      short loc_180008024
0x180007fb1  mov     rcx, rsi; lpCriticalSection
0x180007fb4  xor     r14d, r14d
0x180007fb7  xor     r15d, r15d
0x180007fba  call    cs:__imp_EnterCriticalSection
0x180007fc0  mov     rcx, rbp; SRWLock
0x180007fc3  call    cs:__imp_AcquireSRWLockExclusive
0x180007fc9  cmp     rbx, rdi
0x180007fcc  jnb     short loc_180007FF3
0x180007fce  mov     rdx, [rsi+28h]
0x180007fd2  lea     rax, [rbx+1]
0x180007fd6  add     rbx, rbx
0x180007fd9  lea     rcx, [rdx+rbx*8]
0x180007fdd  mov     rbx, rax
0x180007fe0  cmp     [rcx], r14
0x180007fe3  jnz     short loc_180007FEC
0x180007fe5  cmp     rax, rdi
0x180007fe8  jb      short loc_180007FD2
0x180007fea  jmp     short loc_180007FF3
0x180007fec  mov     r14, [rcx]
0x180007fef  mov     r15, [rcx+8]
0x180007ff3  test    rbp, rbp
0x180007ff6  jz      short loc_180008001
0x180007ff8  mov     rcx, rbp; SRWLock
0x180007ffb  call    cs:__imp_ReleaseSRWLockExclusive
0x180008001  test    r14, r14
0x180008004  jz      short loc_180008011
0x180008006  mov     rcx, r15
0x180008009  mov     rax, r14
0x18000800c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008011  test    rsi, rsi
0x180008014  jz      short loc_18000801F
0x180008016  mov     rcx, rsi; lpCriticalSection
0x180008019  call    cs:__imp_LeaveCriticalSection
0x18000801f  cmp     rbx, rdi
0x180008022  jb      short loc_180007FB1
0x180008024  add     rsp, 28h
0x180008028  pop     r15
0x18000802a  pop     r14
0x18000802c  pop     rdi
0x18000802d  pop     rsi
0x18000802e  pop     rbp
0x18000802f  pop     rbx
0x180008030  retn
```
