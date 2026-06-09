# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800067f4`
- end: `0x1800068b1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d00`
- `0x180002d30`
- `0x180002de0`
- `0x180009bf0`

## callees

- `0x1800067f4`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000687b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000687b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006824`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006824`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006843`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006843`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000680a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000680a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000683a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000683a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006899`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006899`

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
0x1800067f4  push    rbx
0x1800067f6  push    rbp
0x1800067f7  push    rsi
0x1800067f8  push    rdi
0x1800067f9  push    r14
0x1800067fb  push    r15
0x1800067fd  sub     rsp, 28h
0x180006801  mov     rbp, rdx
0x180006804  mov     rsi, rcx
0x180006807  mov     rcx, rdx; SRWLock
0x18000680a  call    cs:__imp_AcquireSRWLockShared
0x180006810  mov     rdi, [rsi+30h]
0x180006814  sub     rdi, [rsi+28h]
0x180006818  shr     rdi, 4
0x18000681c  test    rbp, rbp
0x18000681f  jz      short loc_18000682A
0x180006821  mov     rcx, rbp; SRWLock
0x180006824  call    cs:__imp_ReleaseSRWLockShared
0x18000682a  xor     ebx, ebx
0x18000682c  test    rdi, rdi
0x18000682f  jz      short loc_1800068A4
0x180006831  xor     r14d, r14d
0x180006834  xor     r15d, r15d
0x180006837  mov     rcx, rsi; lpCriticalSection
0x18000683a  call    cs:__imp_EnterCriticalSection
0x180006840  mov     rcx, rbp; SRWLock
0x180006843  call    cs:__imp_AcquireSRWLockExclusive
0x180006849  cmp     rbx, rdi
0x18000684c  jnb     short loc_180006873
0x18000684e  mov     rdx, [rsi+28h]
0x180006852  lea     rax, [rbx+1]
0x180006856  add     rbx, rbx
0x180006859  lea     rcx, [rdx+rbx*8]
0x18000685d  mov     rbx, rax
0x180006860  cmp     [rcx], r14
0x180006863  jnz     short loc_18000686C
0x180006865  cmp     rax, rdi
0x180006868  jb      short loc_180006852
0x18000686a  jmp     short loc_180006873
0x18000686c  mov     r14, [rcx]
0x18000686f  mov     r15, [rcx+8]
0x180006873  test    rbp, rbp
0x180006876  jz      short loc_180006881
0x180006878  mov     rcx, rbp; SRWLock
0x18000687b  call    cs:__imp_ReleaseSRWLockExclusive
0x180006881  test    r14, r14
0x180006884  jz      short loc_180006891
0x180006886  mov     rcx, r15
0x180006889  mov     rax, r14
0x18000688c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006891  test    rsi, rsi
0x180006894  jz      short loc_18000689F
0x180006896  mov     rcx, rsi; lpCriticalSection
0x180006899  call    cs:__imp_LeaveCriticalSection
0x18000689f  cmp     rbx, rdi
0x1800068a2  jb      short loc_180006831
0x1800068a4  add     rsp, 28h
0x1800068a8  pop     r15
0x1800068aa  pop     r14
0x1800068ac  pop     rdi
0x1800068ad  pop     rsi
0x1800068ae  pop     rbp
0x1800068af  pop     rbx
0x1800068b0  retn
```
