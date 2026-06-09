# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140006670`
- end: `0x14000675a`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `234`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002be0`
- `0x140002c10`
- `0x140002d20`
- `0x140009880`

## callees

- `0x140006670`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400066d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400066d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006713`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006713`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400066c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400066c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140006686`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140006686`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400066a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400066a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006737`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006737`

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
0x140006670  push    rbx
0x140006672  push    rbp
0x140006673  push    rsi
0x140006674  push    rdi
0x140006675  push    r14
0x140006677  push    r15
0x140006679  sub     rsp, 28h
0x14000667d  mov     rbp, rdx
0x140006680  mov     rsi, rcx
0x140006683  mov     rcx, rdx; SRWLock
0x140006686  call    cs:__imp_AcquireSRWLockShared
0x14000668d  nop     dword ptr [rax+rax+00h]
0x140006692  mov     rdi, [rsi+30h]
0x140006696  sub     rdi, [rsi+28h]
0x14000669a  shr     rdi, 4
0x14000669e  test    rbp, rbp
0x1400066a1  jz      short loc_1400066B2
0x1400066a3  mov     rcx, rbp; SRWLock
0x1400066a6  call    cs:__imp_ReleaseSRWLockShared
0x1400066ad  nop     dword ptr [rax+rax+00h]
0x1400066b2  xor     ebx, ebx
0x1400066b4  test    rdi, rdi
0x1400066b7  jz      loc_14000674C
0x1400066bd  xor     r14d, r14d
0x1400066c0  xor     r15d, r15d
0x1400066c3  mov     rcx, rsi; lpCriticalSection
0x1400066c6  call    cs:__imp_EnterCriticalSection
0x1400066cd  nop     dword ptr [rax+rax+00h]
0x1400066d2  mov     rcx, rbp; SRWLock
0x1400066d5  call    cs:__imp_AcquireSRWLockExclusive
0x1400066dc  nop     dword ptr [rax+rax+00h]
0x1400066e1  cmp     rbx, rdi
0x1400066e4  jnb     short loc_14000670B
0x1400066e6  mov     rdx, [rsi+28h]
0x1400066ea  lea     rax, [rbx+1]
0x1400066ee  add     rbx, rbx
0x1400066f1  lea     rcx, [rdx+rbx*8]
0x1400066f5  mov     rbx, rax
0x1400066f8  cmp     [rcx], r14
0x1400066fb  jnz     short loc_140006704
0x1400066fd  cmp     rax, rdi
0x140006700  jb      short loc_1400066EA
0x140006702  jmp     short loc_14000670B
0x140006704  mov     r14, [rcx]
0x140006707  mov     r15, [rcx+8]
0x14000670b  test    rbp, rbp
0x14000670e  jz      short loc_14000671F
0x140006710  mov     rcx, rbp; SRWLock
0x140006713  call    cs:__imp_ReleaseSRWLockExclusive
0x14000671a  nop     dword ptr [rax+rax+00h]
0x14000671f  test    r14, r14
0x140006722  jz      short loc_14000672F
0x140006724  mov     rcx, r15
0x140006727  mov     rax, r14
0x14000672a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000672f  test    rsi, rsi
0x140006732  jz      short loc_140006743
0x140006734  mov     rcx, rsi; lpCriticalSection
0x140006737  call    cs:__imp_LeaveCriticalSection
0x14000673e  nop     dword ptr [rax+rax+00h]
0x140006743  cmp     rbx, rdi
0x140006746  jb      loc_1400066BD
0x14000674c  add     rsp, 28h
0x140006750  pop     r15
0x140006752  pop     r14
0x140006754  pop     rdi
0x140006755  pop     rsi
0x140006756  pop     rbp
0x140006757  pop     rbx
0x140006758  retn
```
