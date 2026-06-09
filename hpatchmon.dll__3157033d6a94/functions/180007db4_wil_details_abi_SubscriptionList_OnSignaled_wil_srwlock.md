# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180007db4`
- end: `0x180007e71`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030f0`
- `0x180003120`
- `0x180003220`
- `0x18000c040`

## callees

- `0x180007db4`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007dca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007dca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007dfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007dfa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007de4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007de4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007e03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007e03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007e3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007e3b`

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
0x180007db4  push    rbx
0x180007db6  push    rbp
0x180007db7  push    rsi
0x180007db8  push    rdi
0x180007db9  push    r14
0x180007dbb  push    r15
0x180007dbd  sub     rsp, 28h
0x180007dc1  mov     rbp, rdx
0x180007dc4  mov     rsi, rcx
0x180007dc7  mov     rcx, rdx; SRWLock
0x180007dca  call    cs:__imp_AcquireSRWLockShared
0x180007dd0  mov     rdi, [rsi+30h]
0x180007dd4  sub     rdi, [rsi+28h]
0x180007dd8  shr     rdi, 4
0x180007ddc  test    rbp, rbp
0x180007ddf  jz      short loc_180007DEA
0x180007de1  mov     rcx, rbp; SRWLock
0x180007de4  call    cs:__imp_ReleaseSRWLockShared
0x180007dea  xor     ebx, ebx
0x180007dec  test    rdi, rdi
0x180007def  jz      short loc_180007E64
0x180007df1  xor     r14d, r14d
0x180007df4  xor     r15d, r15d
0x180007df7  mov     rcx, rsi; lpCriticalSection
0x180007dfa  call    cs:__imp_EnterCriticalSection
0x180007e00  mov     rcx, rbp; SRWLock
0x180007e03  call    cs:__imp_AcquireSRWLockExclusive
0x180007e09  cmp     rbx, rdi
0x180007e0c  jnb     short loc_180007E33
0x180007e0e  mov     rdx, [rsi+28h]
0x180007e12  lea     rax, [rbx+1]
0x180007e16  add     rbx, rbx
0x180007e19  lea     rcx, [rdx+rbx*8]
0x180007e1d  mov     rbx, rax
0x180007e20  cmp     [rcx], r14
0x180007e23  jnz     short loc_180007E2C
0x180007e25  cmp     rax, rdi
0x180007e28  jb      short loc_180007E12
0x180007e2a  jmp     short loc_180007E33
0x180007e2c  mov     r14, [rcx]
0x180007e2f  mov     r15, [rcx+8]
0x180007e33  test    rbp, rbp
0x180007e36  jz      short loc_180007E41
0x180007e38  mov     rcx, rbp; SRWLock
0x180007e3b  call    cs:__imp_ReleaseSRWLockExclusive
0x180007e41  test    r14, r14
0x180007e44  jz      short loc_180007E51
0x180007e46  mov     rcx, r15
0x180007e49  mov     rax, r14
0x180007e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e51  test    rsi, rsi
0x180007e54  jz      short loc_180007E5F
0x180007e56  mov     rcx, rsi; lpCriticalSection
0x180007e59  call    cs:__imp_LeaveCriticalSection
0x180007e5f  cmp     rbx, rdi
0x180007e62  jb      short loc_180007DF1
0x180007e64  add     rsp, 28h
0x180007e68  pop     r15
0x180007e6a  pop     r14
0x180007e6c  pop     rdi
0x180007e6d  pop     rsi
0x180007e6e  pop     rbp
0x180007e6f  pop     rbx
0x180007e70  retn
```
