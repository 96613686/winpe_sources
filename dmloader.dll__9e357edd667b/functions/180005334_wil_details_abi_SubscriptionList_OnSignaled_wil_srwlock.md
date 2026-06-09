# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005334`
- end: `0x1800053f1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f70`
- `0x180001fa0`
- `0x180002050`
- `0x180007340`

## callees

- `0x180005334`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005383`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005383`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000534a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000534a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000537a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000537a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005364`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005364`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800053bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800053bb`

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
0x180005334  push    rbx
0x180005336  push    rbp
0x180005337  push    rsi
0x180005338  push    rdi
0x180005339  push    r14
0x18000533b  push    r15
0x18000533d  sub     rsp, 28h
0x180005341  mov     rsi, rcx
0x180005344  mov     rbp, rdx
0x180005347  mov     rcx, rdx; SRWLock
0x18000534a  call    cs:__imp_AcquireSRWLockShared
0x180005350  mov     rdi, [rsi+30h]
0x180005354  sub     rdi, [rsi+28h]
0x180005358  shr     rdi, 4
0x18000535c  test    rbp, rbp
0x18000535f  jz      short loc_18000536A
0x180005361  mov     rcx, rbp; SRWLock
0x180005364  call    cs:__imp_ReleaseSRWLockShared
0x18000536a  xor     ebx, ebx
0x18000536c  test    rdi, rdi
0x18000536f  jz      short loc_1800053E4
0x180005371  mov     rcx, rsi; lpCriticalSection
0x180005374  xor     r14d, r14d
0x180005377  xor     r15d, r15d
0x18000537a  call    cs:__imp_EnterCriticalSection
0x180005380  mov     rcx, rbp; SRWLock
0x180005383  call    cs:__imp_AcquireSRWLockExclusive
0x180005389  cmp     rbx, rdi
0x18000538c  jnb     short loc_1800053B3
0x18000538e  mov     rdx, [rsi+28h]
0x180005392  lea     rax, [rbx+1]
0x180005396  add     rbx, rbx
0x180005399  lea     rcx, [rdx+rbx*8]
0x18000539d  mov     rbx, rax
0x1800053a0  cmp     [rcx], r14
0x1800053a3  jnz     short loc_1800053AC
0x1800053a5  cmp     rax, rdi
0x1800053a8  jb      short loc_180005392
0x1800053aa  jmp     short loc_1800053B3
0x1800053ac  mov     r14, [rcx]
0x1800053af  mov     r15, [rcx+8]
0x1800053b3  test    rbp, rbp
0x1800053b6  jz      short loc_1800053C1
0x1800053b8  mov     rcx, rbp; SRWLock
0x1800053bb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800053c1  test    r14, r14
0x1800053c4  jz      short loc_1800053D1
0x1800053c6  mov     rcx, r15
0x1800053c9  mov     rax, r14
0x1800053cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d1  test    rsi, rsi
0x1800053d4  jz      short loc_1800053DF
0x1800053d6  mov     rcx, rsi; lpCriticalSection
0x1800053d9  call    cs:__imp_LeaveCriticalSection
0x1800053df  cmp     rbx, rdi
0x1800053e2  jb      short loc_180005371
0x1800053e4  add     rsp, 28h
0x1800053e8  pop     r15
0x1800053ea  pop     r14
0x1800053ec  pop     rdi
0x1800053ed  pop     rsi
0x1800053ee  pop     rbp
0x1800053ef  pop     rbx
0x1800053f0  retn
```
