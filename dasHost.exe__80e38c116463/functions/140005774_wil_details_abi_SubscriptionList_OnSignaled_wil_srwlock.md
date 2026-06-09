# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140005774`
- end: `0x140005831`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002230`
- `0x140002260`
- `0x140002310`
- `0x140007ed0`

## callees

- `0x140005774`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400057c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400057c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400057a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400057a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400057fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400057fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005819`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400057ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400057ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000578a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000578a`

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
0x140005774  push    rbx
0x140005776  push    rbp
0x140005777  push    rsi
0x140005778  push    rdi
0x140005779  push    r14
0x14000577b  push    r15
0x14000577d  sub     rsp, 28h
0x140005781  mov     rbp, rdx
0x140005784  mov     rsi, rcx
0x140005787  mov     rcx, rdx; SRWLock
0x14000578a  call    cs:__imp_AcquireSRWLockShared
0x140005790  mov     rdi, [rsi+30h]
0x140005794  sub     rdi, [rsi+28h]
0x140005798  shr     rdi, 4
0x14000579c  test    rbp, rbp
0x14000579f  jz      short loc_1400057AA
0x1400057a1  mov     rcx, rbp; SRWLock
0x1400057a4  call    cs:__imp_ReleaseSRWLockShared
0x1400057aa  xor     ebx, ebx
0x1400057ac  test    rdi, rdi
0x1400057af  jz      short loc_140005824
0x1400057b1  xor     r14d, r14d
0x1400057b4  xor     r15d, r15d
0x1400057b7  mov     rcx, rsi; lpCriticalSection
0x1400057ba  call    cs:__imp_EnterCriticalSection
0x1400057c0  mov     rcx, rbp; SRWLock
0x1400057c3  call    cs:__imp_AcquireSRWLockExclusive
0x1400057c9  cmp     rbx, rdi
0x1400057cc  jnb     short loc_1400057F3
0x1400057ce  mov     rdx, [rsi+28h]
0x1400057d2  lea     rax, [rbx+1]
0x1400057d6  add     rbx, rbx
0x1400057d9  lea     rcx, [rdx+rbx*8]
0x1400057dd  mov     rbx, rax
0x1400057e0  cmp     [rcx], r14
0x1400057e3  jnz     short loc_1400057EC
0x1400057e5  cmp     rax, rdi
0x1400057e8  jb      short loc_1400057D2
0x1400057ea  jmp     short loc_1400057F3
0x1400057ec  mov     r14, [rcx]
0x1400057ef  mov     r15, [rcx+8]
0x1400057f3  test    rbp, rbp
0x1400057f6  jz      short loc_140005801
0x1400057f8  mov     rcx, rbp; SRWLock
0x1400057fb  call    cs:__imp_ReleaseSRWLockExclusive
0x140005801  test    r14, r14
0x140005804  jz      short loc_140005811
0x140005806  mov     rcx, r15
0x140005809  mov     rax, r14
0x14000580c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005811  test    rsi, rsi
0x140005814  jz      short loc_14000581F
0x140005816  mov     rcx, rsi; lpCriticalSection
0x140005819  call    cs:__imp_LeaveCriticalSection
0x14000581f  cmp     rbx, rdi
0x140005822  jb      short loc_1400057B1
0x140005824  add     rsp, 28h
0x140005828  pop     r15
0x14000582a  pop     r14
0x14000582c  pop     rdi
0x14000582d  pop     rsi
0x14000582e  pop     rbp
0x14000582f  pop     rbx
0x140005830  retn
```
