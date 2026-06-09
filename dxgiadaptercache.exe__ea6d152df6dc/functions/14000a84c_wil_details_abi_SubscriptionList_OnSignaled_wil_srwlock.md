# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000a84c`
- end: `0x14000a909`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400031c0`
- `0x1400031f0`
- `0x1400033c0`
- `0x14000f6f0`

## callees

- `0x14000a84c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000a87c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000a87c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a89b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a89b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000a862`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000a862`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000a892`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000a892`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000a8f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000a8f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a8d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a8d3`

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
0x14000a84c  push    rbx
0x14000a84e  push    rbp
0x14000a84f  push    rsi
0x14000a850  push    rdi
0x14000a851  push    r14
0x14000a853  push    r15
0x14000a855  sub     rsp, 28h
0x14000a859  mov     rbp, rdx
0x14000a85c  mov     rsi, rcx
0x14000a85f  mov     rcx, rdx; SRWLock
0x14000a862  call    cs:__imp_AcquireSRWLockShared
0x14000a868  mov     rdi, [rsi+30h]
0x14000a86c  sub     rdi, [rsi+28h]
0x14000a870  shr     rdi, 4
0x14000a874  test    rbp, rbp
0x14000a877  jz      short loc_14000A882
0x14000a879  mov     rcx, rbp; SRWLock
0x14000a87c  call    cs:__imp_ReleaseSRWLockShared
0x14000a882  xor     ebx, ebx
0x14000a884  test    rdi, rdi
0x14000a887  jz      short loc_14000A8FC
0x14000a889  xor     r14d, r14d
0x14000a88c  xor     r15d, r15d
0x14000a88f  mov     rcx, rsi; lpCriticalSection
0x14000a892  call    cs:__imp_EnterCriticalSection
0x14000a898  mov     rcx, rbp; SRWLock
0x14000a89b  call    cs:__imp_AcquireSRWLockExclusive
0x14000a8a1  cmp     rbx, rdi
0x14000a8a4  jnb     short loc_14000A8CB
0x14000a8a6  mov     rdx, [rsi+28h]
0x14000a8aa  lea     rax, [rbx+1]
0x14000a8ae  add     rbx, rbx
0x14000a8b1  lea     rcx, [rdx+rbx*8]
0x14000a8b5  mov     rbx, rax
0x14000a8b8  cmp     [rcx], r14
0x14000a8bb  jnz     short loc_14000A8C4
0x14000a8bd  cmp     rax, rdi
0x14000a8c0  jb      short loc_14000A8AA
0x14000a8c2  jmp     short loc_14000A8CB
0x14000a8c4  mov     r14, [rcx]
0x14000a8c7  mov     r15, [rcx+8]
0x14000a8cb  test    rbp, rbp
0x14000a8ce  jz      short loc_14000A8D9
0x14000a8d0  mov     rcx, rbp; SRWLock
0x14000a8d3  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a8d9  test    r14, r14
0x14000a8dc  jz      short loc_14000A8E9
0x14000a8de  mov     rcx, r15
0x14000a8e1  mov     rax, r14
0x14000a8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8e9  test    rsi, rsi
0x14000a8ec  jz      short loc_14000A8F7
0x14000a8ee  mov     rcx, rsi; lpCriticalSection
0x14000a8f1  call    cs:__imp_LeaveCriticalSection
0x14000a8f7  cmp     rbx, rdi
0x14000a8fa  jb      short loc_14000A889
0x14000a8fc  add     rsp, 28h
0x14000a900  pop     r15
0x14000a902  pop     r14
0x14000a904  pop     rdi
0x14000a905  pop     rsi
0x14000a906  pop     rbp
0x14000a907  pop     rbx
0x14000a908  retn
```
