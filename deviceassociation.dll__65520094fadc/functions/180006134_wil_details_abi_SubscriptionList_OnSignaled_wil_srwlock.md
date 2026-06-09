# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180006134`
- end: `0x1800061f1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002fb0`
- `0x180002fe0`
- `0x180003090`
- `0x180007f60`

## callees

- `0x180006134`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800061bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800061bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006183`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006183`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006164`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006164`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000614a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000614a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000617a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000617a`

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
0x180006134  push    rbx
0x180006136  push    rbp
0x180006137  push    rsi
0x180006138  push    rdi
0x180006139  push    r14
0x18000613b  push    r15
0x18000613d  sub     rsp, 28h
0x180006141  mov     rsi, rcx
0x180006144  mov     rbp, rdx
0x180006147  mov     rcx, rdx; SRWLock
0x18000614a  call    cs:__imp_AcquireSRWLockShared
0x180006150  mov     rdi, [rsi+30h]
0x180006154  sub     rdi, [rsi+28h]
0x180006158  shr     rdi, 4
0x18000615c  test    rbp, rbp
0x18000615f  jz      short loc_18000616A
0x180006161  mov     rcx, rbp; SRWLock
0x180006164  call    cs:__imp_ReleaseSRWLockShared
0x18000616a  xor     ebx, ebx
0x18000616c  test    rdi, rdi
0x18000616f  jz      short loc_1800061E4
0x180006171  mov     rcx, rsi; lpCriticalSection
0x180006174  xor     r14d, r14d
0x180006177  xor     r15d, r15d
0x18000617a  call    cs:__imp_EnterCriticalSection
0x180006180  mov     rcx, rbp; SRWLock
0x180006183  call    cs:__imp_AcquireSRWLockExclusive
0x180006189  cmp     rbx, rdi
0x18000618c  jnb     short loc_1800061B3
0x18000618e  mov     rdx, [rsi+28h]
0x180006192  lea     rax, [rbx+1]
0x180006196  add     rbx, rbx
0x180006199  lea     rcx, [rdx+rbx*8]
0x18000619d  mov     rbx, rax
0x1800061a0  cmp     [rcx], r14
0x1800061a3  jnz     short loc_1800061AC
0x1800061a5  cmp     rax, rdi
0x1800061a8  jb      short loc_180006192
0x1800061aa  jmp     short loc_1800061B3
0x1800061ac  mov     r14, [rcx]
0x1800061af  mov     r15, [rcx+8]
0x1800061b3  test    rbp, rbp
0x1800061b6  jz      short loc_1800061C1
0x1800061b8  mov     rcx, rbp; SRWLock
0x1800061bb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800061c1  test    r14, r14
0x1800061c4  jz      short loc_1800061D1
0x1800061c6  mov     rcx, r15
0x1800061c9  mov     rax, r14
0x1800061cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d1  test    rsi, rsi
0x1800061d4  jz      short loc_1800061DF
0x1800061d6  mov     rcx, rsi; lpCriticalSection
0x1800061d9  call    cs:__imp_LeaveCriticalSection
0x1800061df  cmp     rbx, rdi
0x1800061e2  jb      short loc_180006171
0x1800061e4  add     rsp, 28h
0x1800061e8  pop     r15
0x1800061ea  pop     r14
0x1800061ec  pop     rdi
0x1800061ed  pop     rsi
0x1800061ee  pop     rbp
0x1800061ef  pop     rbx
0x1800061f0  retn
```
