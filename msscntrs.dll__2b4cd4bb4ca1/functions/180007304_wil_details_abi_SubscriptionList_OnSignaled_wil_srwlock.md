# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180007304`
- end: `0x1800073c1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003580`
- `0x1800035b0`
- `0x180003660`
- `0x180009e80`

## callees

- `0x180007304`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000734a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000734a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000731a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000731a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007334`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007334`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007353`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007353`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000738b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000738b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073a9`

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
0x180007304  push    rbx
0x180007306  push    rbp
0x180007307  push    rsi
0x180007308  push    rdi
0x180007309  push    r14
0x18000730b  push    r15
0x18000730d  sub     rsp, 28h
0x180007311  mov     rbp, rdx
0x180007314  mov     rsi, rcx
0x180007317  mov     rcx, rdx; SRWLock
0x18000731a  call    cs:__imp_AcquireSRWLockShared
0x180007320  mov     rdi, [rsi+30h]
0x180007324  sub     rdi, [rsi+28h]
0x180007328  shr     rdi, 4
0x18000732c  test    rbp, rbp
0x18000732f  jz      short loc_18000733A
0x180007331  mov     rcx, rbp; SRWLock
0x180007334  call    cs:__imp_ReleaseSRWLockShared
0x18000733a  xor     ebx, ebx
0x18000733c  test    rdi, rdi
0x18000733f  jz      short loc_1800073B4
0x180007341  xor     r14d, r14d
0x180007344  xor     r15d, r15d
0x180007347  mov     rcx, rsi; lpCriticalSection
0x18000734a  call    cs:__imp_EnterCriticalSection
0x180007350  mov     rcx, rbp; SRWLock
0x180007353  call    cs:__imp_AcquireSRWLockExclusive
0x180007359  cmp     rbx, rdi
0x18000735c  jnb     short loc_180007383
0x18000735e  mov     rdx, [rsi+28h]
0x180007362  lea     rax, [rbx+1]
0x180007366  add     rbx, rbx
0x180007369  lea     rcx, [rdx+rbx*8]
0x18000736d  mov     rbx, rax
0x180007370  cmp     [rcx], r14
0x180007373  jnz     short loc_18000737C
0x180007375  cmp     rax, rdi
0x180007378  jb      short loc_180007362
0x18000737a  jmp     short loc_180007383
0x18000737c  mov     r14, [rcx]
0x18000737f  mov     r15, [rcx+8]
0x180007383  test    rbp, rbp
0x180007386  jz      short loc_180007391
0x180007388  mov     rcx, rbp; SRWLock
0x18000738b  call    cs:__imp_ReleaseSRWLockExclusive
0x180007391  test    r14, r14
0x180007394  jz      short loc_1800073A1
0x180007396  mov     rcx, r15
0x180007399  mov     rax, r14
0x18000739c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a1  test    rsi, rsi
0x1800073a4  jz      short loc_1800073AF
0x1800073a6  mov     rcx, rsi; lpCriticalSection
0x1800073a9  call    cs:__imp_LeaveCriticalSection
0x1800073af  cmp     rbx, rdi
0x1800073b2  jb      short loc_180007341
0x1800073b4  add     rsp, 28h
0x1800073b8  pop     r15
0x1800073ba  pop     r14
0x1800073bc  pop     rdi
0x1800073bd  pop     rsi
0x1800073be  pop     rbp
0x1800073bf  pop     rbx
0x1800073c0  retn
```
