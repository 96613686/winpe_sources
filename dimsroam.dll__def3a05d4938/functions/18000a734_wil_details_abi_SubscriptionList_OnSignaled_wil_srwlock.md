# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000a734`
- end: `0x18000a7f1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075b0`
- `0x1800075e0`
- `0x180007690`
- `0x18000c560`

## callees

- `0x18000a734`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a764`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a764`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a74a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a74a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a7bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a7bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a783`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a783`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a77a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a77a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7d9`

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
0x18000a734  push    rbx
0x18000a736  push    rbp
0x18000a737  push    rsi
0x18000a738  push    rdi
0x18000a739  push    r14
0x18000a73b  push    r15
0x18000a73d  sub     rsp, 28h
0x18000a741  mov     rsi, rcx
0x18000a744  mov     rbp, rdx
0x18000a747  mov     rcx, rdx; SRWLock
0x18000a74a  call    cs:__imp_AcquireSRWLockShared
0x18000a750  mov     rdi, [rsi+30h]
0x18000a754  sub     rdi, [rsi+28h]
0x18000a758  shr     rdi, 4
0x18000a75c  test    rbp, rbp
0x18000a75f  jz      short loc_18000A76A
0x18000a761  mov     rcx, rbp; SRWLock
0x18000a764  call    cs:__imp_ReleaseSRWLockShared
0x18000a76a  xor     ebx, ebx
0x18000a76c  test    rdi, rdi
0x18000a76f  jz      short loc_18000A7E4
0x18000a771  mov     rcx, rsi; lpCriticalSection
0x18000a774  xor     r14d, r14d
0x18000a777  xor     r15d, r15d
0x18000a77a  call    cs:__imp_EnterCriticalSection
0x18000a780  mov     rcx, rbp; SRWLock
0x18000a783  call    cs:__imp_AcquireSRWLockExclusive
0x18000a789  cmp     rbx, rdi
0x18000a78c  jnb     short loc_18000A7B3
0x18000a78e  mov     rdx, [rsi+28h]
0x18000a792  lea     rax, [rbx+1]
0x18000a796  add     rbx, rbx
0x18000a799  lea     rcx, [rdx+rbx*8]
0x18000a79d  mov     rbx, rax
0x18000a7a0  cmp     [rcx], r14
0x18000a7a3  jnz     short loc_18000A7AC
0x18000a7a5  cmp     rax, rdi
0x18000a7a8  jb      short loc_18000A792
0x18000a7aa  jmp     short loc_18000A7B3
0x18000a7ac  mov     r14, [rcx]
0x18000a7af  mov     r15, [rcx+8]
0x18000a7b3  test    rbp, rbp
0x18000a7b6  jz      short loc_18000A7C1
0x18000a7b8  mov     rcx, rbp; SRWLock
0x18000a7bb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a7c1  test    r14, r14
0x18000a7c4  jz      short loc_18000A7D1
0x18000a7c6  mov     rcx, r15
0x18000a7c9  mov     rax, r14
0x18000a7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d1  test    rsi, rsi
0x18000a7d4  jz      short loc_18000A7DF
0x18000a7d6  mov     rcx, rsi; lpCriticalSection
0x18000a7d9  call    cs:__imp_LeaveCriticalSection
0x18000a7df  cmp     rbx, rdi
0x18000a7e2  jb      short loc_18000A771
0x18000a7e4  add     rsp, 28h
0x18000a7e8  pop     r15
0x18000a7ea  pop     r14
0x18000a7ec  pop     rdi
0x18000a7ed  pop     rsi
0x18000a7ee  pop     rbp
0x18000a7ef  pop     rbx
0x18000a7f0  retn
```
