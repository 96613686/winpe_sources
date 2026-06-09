# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000677c`
- end: `0x180006839`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b10`
- `0x180002b40`
- `0x180002c50`
- `0x180009510`

## callees

- `0x18000677c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006792`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006792`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800067ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800067ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006821`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006821`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800067cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800067cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006803`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006803`

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
0x18000677c  push    rbx
0x18000677e  push    rbp
0x18000677f  push    rsi
0x180006780  push    rdi
0x180006781  push    r14
0x180006783  push    r15
0x180006785  sub     rsp, 28h
0x180006789  mov     rbp, rdx
0x18000678c  mov     rsi, rcx
0x18000678f  mov     rcx, rdx; SRWLock
0x180006792  call    cs:__imp_AcquireSRWLockShared
0x180006798  mov     rdi, [rsi+30h]
0x18000679c  sub     rdi, [rsi+28h]
0x1800067a0  shr     rdi, 4
0x1800067a4  test    rbp, rbp
0x1800067a7  jz      short loc_1800067B2
0x1800067a9  mov     rcx, rbp; SRWLock
0x1800067ac  call    cs:__imp_ReleaseSRWLockShared
0x1800067b2  xor     ebx, ebx
0x1800067b4  test    rdi, rdi
0x1800067b7  jz      short loc_18000682C
0x1800067b9  xor     r14d, r14d
0x1800067bc  xor     r15d, r15d
0x1800067bf  mov     rcx, rsi; lpCriticalSection
0x1800067c2  call    cs:__imp_EnterCriticalSection
0x1800067c8  mov     rcx, rbp; SRWLock
0x1800067cb  call    cs:__imp_AcquireSRWLockExclusive
0x1800067d1  cmp     rbx, rdi
0x1800067d4  jnb     short loc_1800067FB
0x1800067d6  mov     rdx, [rsi+28h]
0x1800067da  lea     rax, [rbx+1]
0x1800067de  add     rbx, rbx
0x1800067e1  lea     rcx, [rdx+rbx*8]
0x1800067e5  mov     rbx, rax
0x1800067e8  cmp     [rcx], r14
0x1800067eb  jnz     short loc_1800067F4
0x1800067ed  cmp     rax, rdi
0x1800067f0  jb      short loc_1800067DA
0x1800067f2  jmp     short loc_1800067FB
0x1800067f4  mov     r14, [rcx]
0x1800067f7  mov     r15, [rcx+8]
0x1800067fb  test    rbp, rbp
0x1800067fe  jz      short loc_180006809
0x180006800  mov     rcx, rbp; SRWLock
0x180006803  call    cs:__imp_ReleaseSRWLockExclusive
0x180006809  test    r14, r14
0x18000680c  jz      short loc_180006819
0x18000680e  mov     rcx, r15
0x180006811  mov     rax, r14
0x180006814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006819  test    rsi, rsi
0x18000681c  jz      short loc_180006827
0x18000681e  mov     rcx, rsi; lpCriticalSection
0x180006821  call    cs:__imp_LeaveCriticalSection
0x180006827  cmp     rbx, rdi
0x18000682a  jb      short loc_1800067B9
0x18000682c  add     rsp, 28h
0x180006830  pop     r15
0x180006832  pop     r14
0x180006834  pop     rdi
0x180006835  pop     rsi
0x180006836  pop     rbp
0x180006837  pop     rbx
0x180006838  retn
```
