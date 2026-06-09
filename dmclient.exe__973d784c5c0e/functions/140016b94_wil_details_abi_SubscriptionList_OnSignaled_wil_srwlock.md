# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140016b94`
- end: `0x140016c7e`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `234`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400158f0`
- `0x140015920`
- `0x1400159d0`
- `0x140018430`

## callees

- `0x140016b94`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016bf9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016bf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140016bca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140016bca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016bea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016bea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140016c5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140016c5b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140016baa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140016baa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016c37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016c37`

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
0x140016b94  push    rbx
0x140016b96  push    rbp
0x140016b97  push    rsi
0x140016b98  push    rdi
0x140016b99  push    r14
0x140016b9b  push    r15
0x140016b9d  sub     rsp, 28h
0x140016ba1  mov     rbp, rdx
0x140016ba4  mov     rsi, rcx
0x140016ba7  mov     rcx, rdx; SRWLock
0x140016baa  call    cs:__imp_AcquireSRWLockShared
0x140016bb1  nop     dword ptr [rax+rax+00h]
0x140016bb6  mov     rdi, [rsi+30h]
0x140016bba  sub     rdi, [rsi+28h]
0x140016bbe  shr     rdi, 4
0x140016bc2  test    rbp, rbp
0x140016bc5  jz      short loc_140016BD6
0x140016bc7  mov     rcx, rbp; SRWLock
0x140016bca  call    cs:__imp_ReleaseSRWLockShared
0x140016bd1  nop     dword ptr [rax+rax+00h]
0x140016bd6  xor     ebx, ebx
0x140016bd8  test    rdi, rdi
0x140016bdb  jz      loc_140016C70
0x140016be1  xor     r14d, r14d
0x140016be4  xor     r15d, r15d
0x140016be7  mov     rcx, rsi; lpCriticalSection
0x140016bea  call    cs:__imp_EnterCriticalSection
0x140016bf1  nop     dword ptr [rax+rax+00h]
0x140016bf6  mov     rcx, rbp; SRWLock
0x140016bf9  call    cs:__imp_AcquireSRWLockExclusive
0x140016c00  nop     dword ptr [rax+rax+00h]
0x140016c05  cmp     rbx, rdi
0x140016c08  jnb     short loc_140016C2F
0x140016c0a  mov     rdx, [rsi+28h]
0x140016c0e  lea     rax, [rbx+1]
0x140016c12  add     rbx, rbx
0x140016c15  lea     rcx, [rdx+rbx*8]
0x140016c19  mov     rbx, rax
0x140016c1c  cmp     [rcx], r14
0x140016c1f  jnz     short loc_140016C28
0x140016c21  cmp     rax, rdi
0x140016c24  jb      short loc_140016C0E
0x140016c26  jmp     short loc_140016C2F
0x140016c28  mov     r14, [rcx]
0x140016c2b  mov     r15, [rcx+8]
0x140016c2f  test    rbp, rbp
0x140016c32  jz      short loc_140016C43
0x140016c34  mov     rcx, rbp; SRWLock
0x140016c37  call    cs:__imp_ReleaseSRWLockExclusive
0x140016c3e  nop     dword ptr [rax+rax+00h]
0x140016c43  test    r14, r14
0x140016c46  jz      short loc_140016C53
0x140016c48  mov     rcx, r15
0x140016c4b  mov     rax, r14
0x140016c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016c53  test    rsi, rsi
0x140016c56  jz      short loc_140016C67
0x140016c58  mov     rcx, rsi; lpCriticalSection
0x140016c5b  call    cs:__imp_LeaveCriticalSection
0x140016c62  nop     dword ptr [rax+rax+00h]
0x140016c67  cmp     rbx, rdi
0x140016c6a  jb      loc_140016BE1
0x140016c70  add     rsp, 28h
0x140016c74  pop     r15
0x140016c76  pop     r14
0x140016c78  pop     rdi
0x140016c79  pop     rsi
0x140016c7a  pop     rbp
0x140016c7b  pop     rbx
0x140016c7c  retn
```
