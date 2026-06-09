# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000edc4`
- end: `0x18000ee81`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006f90`
- `0x180006fc0`
- `0x1800070c0`
- `0x180011810`

## callees

- `0x18000edc4`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ee4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ee4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ee13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ee13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000edda`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000edda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000edf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000edf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee69`

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
0x18000edc4  push    rbx
0x18000edc6  push    rbp
0x18000edc7  push    rsi
0x18000edc8  push    rdi
0x18000edc9  push    r14
0x18000edcb  push    r15
0x18000edcd  sub     rsp, 28h
0x18000edd1  mov     rbp, rdx
0x18000edd4  mov     rsi, rcx
0x18000edd7  mov     rcx, rdx; SRWLock
0x18000edda  call    cs:__imp_AcquireSRWLockShared
0x18000ede0  mov     rdi, [rsi+30h]
0x18000ede4  sub     rdi, [rsi+28h]
0x18000ede8  shr     rdi, 4
0x18000edec  test    rbp, rbp
0x18000edef  jz      short loc_18000EDFA
0x18000edf1  mov     rcx, rbp; SRWLock
0x18000edf4  call    cs:__imp_ReleaseSRWLockShared
0x18000edfa  xor     ebx, ebx
0x18000edfc  test    rdi, rdi
0x18000edff  jz      short loc_18000EE74
0x18000ee01  xor     r14d, r14d
0x18000ee04  xor     r15d, r15d
0x18000ee07  mov     rcx, rsi; lpCriticalSection
0x18000ee0a  call    cs:__imp_EnterCriticalSection
0x18000ee10  mov     rcx, rbp; SRWLock
0x18000ee13  call    cs:__imp_AcquireSRWLockExclusive
0x18000ee19  cmp     rbx, rdi
0x18000ee1c  jnb     short loc_18000EE43
0x18000ee1e  mov     rdx, [rsi+28h]
0x18000ee22  lea     rax, [rbx+1]
0x18000ee26  add     rbx, rbx
0x18000ee29  lea     rcx, [rdx+rbx*8]
0x18000ee2d  mov     rbx, rax
0x18000ee30  cmp     [rcx], r14
0x18000ee33  jnz     short loc_18000EE3C
0x18000ee35  cmp     rax, rdi
0x18000ee38  jb      short loc_18000EE22
0x18000ee3a  jmp     short loc_18000EE43
0x18000ee3c  mov     r14, [rcx]
0x18000ee3f  mov     r15, [rcx+8]
0x18000ee43  test    rbp, rbp
0x18000ee46  jz      short loc_18000EE51
0x18000ee48  mov     rcx, rbp; SRWLock
0x18000ee4b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ee51  test    r14, r14
0x18000ee54  jz      short loc_18000EE61
0x18000ee56  mov     rcx, r15
0x18000ee59  mov     rax, r14
0x18000ee5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee61  test    rsi, rsi
0x18000ee64  jz      short loc_18000EE6F
0x18000ee66  mov     rcx, rsi; lpCriticalSection
0x18000ee69  call    cs:__imp_LeaveCriticalSection
0x18000ee6f  cmp     rbx, rdi
0x18000ee72  jb      short loc_18000EE01
0x18000ee74  add     rsp, 28h
0x18000ee78  pop     r15
0x18000ee7a  pop     r14
0x18000ee7c  pop     rdi
0x18000ee7d  pop     rsi
0x18000ee7e  pop     rbp
0x18000ee7f  pop     rbx
0x18000ee80  retn
```
