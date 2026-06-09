# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140008fbc`
- end: `0x140009079`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003230`
- `0x1400033e0`
- `0x1400034f0`
- `0x14000c7c0`

## callees

- `0x140008fbc`
- `0x140011010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000900b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000900b`
- `KERNEL32!AcquireSRWLockShared` at `0x140008fd2`
- `KERNEL32!AcquireSRWLockShared` at `0x140008fd2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009043`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009043`
- `KERNEL32!EnterCriticalSection` at `0x140009002`
- `KERNEL32!EnterCriticalSection` at `0x140009002`
- `KERNEL32!LeaveCriticalSection` at `0x140009061`
- `KERNEL32!LeaveCriticalSection` at `0x140009061`
- `KERNEL32!ReleaseSRWLockShared` at `0x140008fec`
- `KERNEL32!ReleaseSRWLockShared` at `0x140008fec`

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
0x140008fbc  push    rbx
0x140008fbe  push    rbp
0x140008fbf  push    rsi
0x140008fc0  push    rdi
0x140008fc1  push    r14
0x140008fc3  push    r15
0x140008fc5  sub     rsp, 28h
0x140008fc9  mov     rbp, rdx
0x140008fcc  mov     rsi, rcx
0x140008fcf  mov     rcx, rdx; SRWLock
0x140008fd2  call    cs:__imp_AcquireSRWLockShared
0x140008fd8  mov     rdi, [rsi+30h]
0x140008fdc  sub     rdi, [rsi+28h]
0x140008fe0  shr     rdi, 4
0x140008fe4  test    rbp, rbp
0x140008fe7  jz      short loc_140008FF2
0x140008fe9  mov     rcx, rbp; SRWLock
0x140008fec  call    cs:__imp_ReleaseSRWLockShared
0x140008ff2  xor     ebx, ebx
0x140008ff4  test    rdi, rdi
0x140008ff7  jz      short loc_14000906C
0x140008ff9  xor     r14d, r14d
0x140008ffc  xor     r15d, r15d
0x140008fff  mov     rcx, rsi; lpCriticalSection
0x140009002  call    cs:__imp_EnterCriticalSection
0x140009008  mov     rcx, rbp; SRWLock
0x14000900b  call    cs:__imp_AcquireSRWLockExclusive
0x140009011  cmp     rbx, rdi
0x140009014  jnb     short loc_14000903B
0x140009016  mov     rdx, [rsi+28h]
0x14000901a  lea     rax, [rbx+1]
0x14000901e  add     rbx, rbx
0x140009021  lea     rcx, [rdx+rbx*8]
0x140009025  mov     rbx, rax
0x140009028  cmp     [rcx], r14
0x14000902b  jnz     short loc_140009034
0x14000902d  cmp     rax, rdi
0x140009030  jb      short loc_14000901A
0x140009032  jmp     short loc_14000903B
0x140009034  mov     r14, [rcx]
0x140009037  mov     r15, [rcx+8]
0x14000903b  test    rbp, rbp
0x14000903e  jz      short loc_140009049
0x140009040  mov     rcx, rbp; SRWLock
0x140009043  call    cs:__imp_ReleaseSRWLockExclusive
0x140009049  test    r14, r14
0x14000904c  jz      short loc_140009059
0x14000904e  mov     rcx, r15
0x140009051  mov     rax, r14
0x140009054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009059  test    rsi, rsi
0x14000905c  jz      short loc_140009067
0x14000905e  mov     rcx, rsi; lpCriticalSection
0x140009061  call    cs:__imp_LeaveCriticalSection
0x140009067  cmp     rbx, rdi
0x14000906a  jb      short loc_140008FF9
0x14000906c  add     rsp, 28h
0x140009070  pop     r15
0x140009072  pop     r14
0x140009074  pop     rdi
0x140009075  pop     rsi
0x140009076  pop     rbp
0x140009077  pop     rbx
0x140009078  retn
```
