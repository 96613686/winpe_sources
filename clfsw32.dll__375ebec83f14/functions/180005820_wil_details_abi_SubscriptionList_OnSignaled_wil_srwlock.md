# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005820`
- end: `0x18000590a`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `234`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002720`
- `0x180002750`
- `0x180002800`
- `0x1800079d0`

## callees

- `0x180005820`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005876`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005876`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005836`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005836`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800058c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800058c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005885`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005885`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005856`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005856`

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
0x180005820  push    rbx
0x180005822  push    rbp
0x180005823  push    rsi
0x180005824  push    rdi
0x180005825  push    r14
0x180005827  push    r15
0x180005829  sub     rsp, 28h
0x18000582d  mov     rsi, rcx
0x180005830  mov     rbp, rdx
0x180005833  mov     rcx, rdx; SRWLock
0x180005836  call    cs:__imp_AcquireSRWLockShared
0x18000583d  nop     dword ptr [rax+rax+00h]
0x180005842  mov     rdi, [rsi+30h]
0x180005846  sub     rdi, [rsi+28h]
0x18000584a  shr     rdi, 4
0x18000584e  test    rbp, rbp
0x180005851  jz      short loc_180005862
0x180005853  mov     rcx, rbp; SRWLock
0x180005856  call    cs:__imp_ReleaseSRWLockShared
0x18000585d  nop     dword ptr [rax+rax+00h]
0x180005862  xor     ebx, ebx
0x180005864  test    rdi, rdi
0x180005867  jz      loc_1800058FC
0x18000586d  mov     rcx, rsi; lpCriticalSection
0x180005870  xor     r14d, r14d
0x180005873  xor     r15d, r15d
0x180005876  call    cs:__imp_EnterCriticalSection
0x18000587d  nop     dword ptr [rax+rax+00h]
0x180005882  mov     rcx, rbp; SRWLock
0x180005885  call    cs:__imp_AcquireSRWLockExclusive
0x18000588c  nop     dword ptr [rax+rax+00h]
0x180005891  cmp     rbx, rdi
0x180005894  jnb     short loc_1800058BB
0x180005896  mov     rdx, [rsi+28h]
0x18000589a  lea     rax, [rbx+1]
0x18000589e  add     rbx, rbx
0x1800058a1  lea     rcx, [rdx+rbx*8]
0x1800058a5  mov     rbx, rax
0x1800058a8  cmp     [rcx], r14
0x1800058ab  jnz     short loc_1800058B4
0x1800058ad  cmp     rax, rdi
0x1800058b0  jb      short loc_18000589A
0x1800058b2  jmp     short loc_1800058BB
0x1800058b4  mov     r14, [rcx]
0x1800058b7  mov     r15, [rcx+8]
0x1800058bb  test    rbp, rbp
0x1800058be  jz      short loc_1800058CF
0x1800058c0  mov     rcx, rbp; SRWLock
0x1800058c3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800058ca  nop     dword ptr [rax+rax+00h]
0x1800058cf  test    r14, r14
0x1800058d2  jz      short loc_1800058DF
0x1800058d4  mov     rcx, r15
0x1800058d7  mov     rax, r14
0x1800058da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058df  test    rsi, rsi
0x1800058e2  jz      short loc_1800058F3
0x1800058e4  mov     rcx, rsi; lpCriticalSection
0x1800058e7  call    cs:__imp_LeaveCriticalSection
0x1800058ee  nop     dword ptr [rax+rax+00h]
0x1800058f3  cmp     rbx, rdi
0x1800058f6  jb      loc_18000586D
0x1800058fc  add     rsp, 28h
0x180005900  pop     r15
0x180005902  pop     r14
0x180005904  pop     rdi
0x180005905  pop     rsi
0x180005906  pop     rbp
0x180005907  pop     rbx
0x180005908  retn
```
