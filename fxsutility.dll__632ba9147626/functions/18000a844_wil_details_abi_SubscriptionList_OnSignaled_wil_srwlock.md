# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000a844`
- end: `0x18000a901`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007370`
- `0x1800073a0`
- `0x180007450`
- `0x18000ca10`

## callees

- `0x18000a844`
- `0x180017010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a8cb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a8cb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a893`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a893`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000a874`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000a874`
- `KERNEL32!AcquireSRWLockShared` at `0x18000a85a`
- `KERNEL32!AcquireSRWLockShared` at `0x18000a85a`
- `KERNEL32!LeaveCriticalSection` at `0x18000a8e9`
- `KERNEL32!LeaveCriticalSection` at `0x18000a8e9`
- `KERNEL32!EnterCriticalSection` at `0x18000a88a`
- `KERNEL32!EnterCriticalSection` at `0x18000a88a`

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
0x18000a844  push    rbx
0x18000a846  push    rbp
0x18000a847  push    rsi
0x18000a848  push    rdi
0x18000a849  push    r14
0x18000a84b  push    r15
0x18000a84d  sub     rsp, 28h
0x18000a851  mov     rbp, rdx
0x18000a854  mov     rsi, rcx
0x18000a857  mov     rcx, rdx; SRWLock
0x18000a85a  call    cs:__imp_AcquireSRWLockShared
0x18000a860  mov     rdi, [rsi+30h]
0x18000a864  sub     rdi, [rsi+28h]
0x18000a868  shr     rdi, 4
0x18000a86c  test    rbp, rbp
0x18000a86f  jz      short loc_18000A87A
0x18000a871  mov     rcx, rbp; SRWLock
0x18000a874  call    cs:__imp_ReleaseSRWLockShared
0x18000a87a  xor     ebx, ebx
0x18000a87c  test    rdi, rdi
0x18000a87f  jz      short loc_18000A8F4
0x18000a881  xor     r14d, r14d
0x18000a884  xor     r15d, r15d
0x18000a887  mov     rcx, rsi; lpCriticalSection
0x18000a88a  call    cs:__imp_EnterCriticalSection
0x18000a890  mov     rcx, rbp; SRWLock
0x18000a893  call    cs:__imp_AcquireSRWLockExclusive
0x18000a899  cmp     rbx, rdi
0x18000a89c  jnb     short loc_18000A8C3
0x18000a89e  mov     rdx, [rsi+28h]
0x18000a8a2  lea     rax, [rbx+1]
0x18000a8a6  add     rbx, rbx
0x18000a8a9  lea     rcx, [rdx+rbx*8]
0x18000a8ad  mov     rbx, rax
0x18000a8b0  cmp     [rcx], r14
0x18000a8b3  jnz     short loc_18000A8BC
0x18000a8b5  cmp     rax, rdi
0x18000a8b8  jb      short loc_18000A8A2
0x18000a8ba  jmp     short loc_18000A8C3
0x18000a8bc  mov     r14, [rcx]
0x18000a8bf  mov     r15, [rcx+8]
0x18000a8c3  test    rbp, rbp
0x18000a8c6  jz      short loc_18000A8D1
0x18000a8c8  mov     rcx, rbp; SRWLock
0x18000a8cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a8d1  test    r14, r14
0x18000a8d4  jz      short loc_18000A8E1
0x18000a8d6  mov     rcx, r15
0x18000a8d9  mov     rax, r14
0x18000a8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8e1  test    rsi, rsi
0x18000a8e4  jz      short loc_18000A8EF
0x18000a8e6  mov     rcx, rsi; lpCriticalSection
0x18000a8e9  call    cs:__imp_LeaveCriticalSection
0x18000a8ef  cmp     rbx, rdi
0x18000a8f2  jb      short loc_18000A881
0x18000a8f4  add     rsp, 28h
0x18000a8f8  pop     r15
0x18000a8fa  pop     r14
0x18000a8fc  pop     rdi
0x18000a8fd  pop     rsi
0x18000a8fe  pop     rbp
0x18000a8ff  pop     rbx
0x18000a900  retn
```
