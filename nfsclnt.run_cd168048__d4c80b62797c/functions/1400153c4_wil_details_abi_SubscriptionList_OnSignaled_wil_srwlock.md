# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1400153c4`
- end: `0x140015481`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140012240`
- `0x140012270`
- `0x140012320`
- `0x1400171f0`

## callees

- `0x1400153c4`
- `0x140019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001544b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001544b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140015413`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140015413`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400153f4`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400153f4`
- `KERNEL32!AcquireSRWLockShared` at `0x1400153da`
- `KERNEL32!AcquireSRWLockShared` at `0x1400153da`
- `KERNEL32!EnterCriticalSection` at `0x14001540a`
- `KERNEL32!EnterCriticalSection` at `0x14001540a`
- `KERNEL32!LeaveCriticalSection` at `0x140015469`
- `KERNEL32!LeaveCriticalSection` at `0x140015469`

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
0x1400153c4  push    rbx
0x1400153c6  push    rbp
0x1400153c7  push    rsi
0x1400153c8  push    rdi
0x1400153c9  push    r14
0x1400153cb  push    r15
0x1400153cd  sub     rsp, 28h
0x1400153d1  mov     rsi, rcx
0x1400153d4  mov     rbp, rdx
0x1400153d7  mov     rcx, rdx; SRWLock
0x1400153da  call    cs:__imp_AcquireSRWLockShared
0x1400153e0  mov     rdi, [rsi+30h]
0x1400153e4  sub     rdi, [rsi+28h]
0x1400153e8  shr     rdi, 4
0x1400153ec  test    rbp, rbp
0x1400153ef  jz      short loc_1400153FA
0x1400153f1  mov     rcx, rbp; SRWLock
0x1400153f4  call    cs:__imp_ReleaseSRWLockShared
0x1400153fa  xor     ebx, ebx
0x1400153fc  test    rdi, rdi
0x1400153ff  jz      short loc_140015474
0x140015401  mov     rcx, rsi; lpCriticalSection
0x140015404  xor     r14d, r14d
0x140015407  xor     r15d, r15d
0x14001540a  call    cs:__imp_EnterCriticalSection
0x140015410  mov     rcx, rbp; SRWLock
0x140015413  call    cs:__imp_AcquireSRWLockExclusive
0x140015419  cmp     rbx, rdi
0x14001541c  jnb     short loc_140015443
0x14001541e  mov     rdx, [rsi+28h]
0x140015422  lea     rax, [rbx+1]
0x140015426  add     rbx, rbx
0x140015429  lea     rcx, [rdx+rbx*8]
0x14001542d  mov     rbx, rax
0x140015430  cmp     [rcx], r14
0x140015433  jnz     short loc_14001543C
0x140015435  cmp     rax, rdi
0x140015438  jb      short loc_140015422
0x14001543a  jmp     short loc_140015443
0x14001543c  mov     r14, [rcx]
0x14001543f  mov     r15, [rcx+8]
0x140015443  test    rbp, rbp
0x140015446  jz      short loc_140015451
0x140015448  mov     rcx, rbp; SRWLock
0x14001544b  call    cs:__imp_ReleaseSRWLockExclusive
0x140015451  test    r14, r14
0x140015454  jz      short loc_140015461
0x140015456  mov     rcx, r15
0x140015459  mov     rax, r14
0x14001545c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015461  test    rsi, rsi
0x140015464  jz      short loc_14001546F
0x140015466  mov     rcx, rsi; lpCriticalSection
0x140015469  call    cs:__imp_LeaveCriticalSection
0x14001546f  cmp     rbx, rdi
0x140015472  jb      short loc_140015401
0x140015474  add     rsp, 28h
0x140015478  pop     r15
0x14001547a  pop     r14
0x14001547c  pop     rdi
0x14001547d  pop     rsi
0x14001547e  pop     rbp
0x14001547f  pop     rbx
0x140015480  retn
```
