# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140008284`
- end: `0x140008341`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003310`
- `0x140003340`
- `0x140003470`
- `0x14000a9d0`

## callees

- `0x140008284`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000829a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000829a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400082b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400082b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008329`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400082ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400082ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400082d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400082d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000830b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000830b`

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
0x140008284  push    rbx
0x140008286  push    rbp
0x140008287  push    rsi
0x140008288  push    rdi
0x140008289  push    r14
0x14000828b  push    r15
0x14000828d  sub     rsp, 28h
0x140008291  mov     rbp, rdx
0x140008294  mov     rsi, rcx
0x140008297  mov     rcx, rdx; SRWLock
0x14000829a  call    cs:__imp_AcquireSRWLockShared
0x1400082a0  mov     rdi, [rsi+30h]
0x1400082a4  sub     rdi, [rsi+28h]
0x1400082a8  shr     rdi, 4
0x1400082ac  test    rbp, rbp
0x1400082af  jz      short loc_1400082BA
0x1400082b1  mov     rcx, rbp; SRWLock
0x1400082b4  call    cs:__imp_ReleaseSRWLockShared
0x1400082ba  xor     ebx, ebx
0x1400082bc  test    rdi, rdi
0x1400082bf  jz      short loc_140008334
0x1400082c1  xor     r14d, r14d
0x1400082c4  xor     r15d, r15d
0x1400082c7  mov     rcx, rsi; lpCriticalSection
0x1400082ca  call    cs:__imp_EnterCriticalSection
0x1400082d0  mov     rcx, rbp; SRWLock
0x1400082d3  call    cs:__imp_AcquireSRWLockExclusive
0x1400082d9  cmp     rbx, rdi
0x1400082dc  jnb     short loc_140008303
0x1400082de  mov     rdx, [rsi+28h]
0x1400082e2  lea     rax, [rbx+1]
0x1400082e6  add     rbx, rbx
0x1400082e9  lea     rcx, [rdx+rbx*8]
0x1400082ed  mov     rbx, rax
0x1400082f0  cmp     [rcx], r14
0x1400082f3  jnz     short loc_1400082FC
0x1400082f5  cmp     rax, rdi
0x1400082f8  jb      short loc_1400082E2
0x1400082fa  jmp     short loc_140008303
0x1400082fc  mov     r14, [rcx]
0x1400082ff  mov     r15, [rcx+8]
0x140008303  test    rbp, rbp
0x140008306  jz      short loc_140008311
0x140008308  mov     rcx, rbp; SRWLock
0x14000830b  call    cs:__imp_ReleaseSRWLockExclusive
0x140008311  test    r14, r14
0x140008314  jz      short loc_140008321
0x140008316  mov     rcx, r15
0x140008319  mov     rax, r14
0x14000831c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008321  test    rsi, rsi
0x140008324  jz      short loc_14000832F
0x140008326  mov     rcx, rsi; lpCriticalSection
0x140008329  call    cs:__imp_LeaveCriticalSection
0x14000832f  cmp     rbx, rdi
0x140008332  jb      short loc_1400082C1
0x140008334  add     rsp, 28h
0x140008338  pop     r15
0x14000833a  pop     r14
0x14000833c  pop     rdi
0x14000833d  pop     rsi
0x14000833e  pop     rbp
0x14000833f  pop     rbx
0x140008340  retn
```
