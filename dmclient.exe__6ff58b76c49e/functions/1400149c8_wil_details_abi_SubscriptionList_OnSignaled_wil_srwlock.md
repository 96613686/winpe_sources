# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1400149c8`
- end: `0x140014a85`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140012b90`
- `0x140012bc0`
- `0x140012c70`
- `0x1400167d0`

## callees

- `0x1400149c8`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014a17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014a17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400149de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400149de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014a4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014a4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400149f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400149f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014a6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014a6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140014a0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140014a0e`

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
0x1400149c8  push    rbx
0x1400149ca  push    rbp
0x1400149cb  push    rsi
0x1400149cc  push    rdi
0x1400149cd  push    r14
0x1400149cf  push    r15
0x1400149d1  sub     rsp, 28h
0x1400149d5  mov     rbp, rdx
0x1400149d8  mov     rsi, rcx
0x1400149db  mov     rcx, rdx; SRWLock
0x1400149de  call    cs:__imp_AcquireSRWLockShared
0x1400149e4  mov     rdi, [rsi+30h]
0x1400149e8  sub     rdi, [rsi+28h]
0x1400149ec  shr     rdi, 4
0x1400149f0  test    rbp, rbp
0x1400149f3  jz      short loc_1400149FE
0x1400149f5  mov     rcx, rbp; SRWLock
0x1400149f8  call    cs:__imp_ReleaseSRWLockShared
0x1400149fe  xor     ebx, ebx
0x140014a00  test    rdi, rdi
0x140014a03  jz      short loc_140014A78
0x140014a05  xor     r14d, r14d
0x140014a08  xor     r15d, r15d
0x140014a0b  mov     rcx, rsi; lpCriticalSection
0x140014a0e  call    cs:__imp_EnterCriticalSection
0x140014a14  mov     rcx, rbp; SRWLock
0x140014a17  call    cs:__imp_AcquireSRWLockExclusive
0x140014a1d  cmp     rbx, rdi
0x140014a20  jnb     short loc_140014A47
0x140014a22  mov     rdx, [rsi+28h]
0x140014a26  lea     rax, [rbx+1]
0x140014a2a  add     rbx, rbx
0x140014a2d  lea     rcx, [rdx+rbx*8]
0x140014a31  mov     rbx, rax
0x140014a34  cmp     [rcx], r14
0x140014a37  jnz     short loc_140014A40
0x140014a39  cmp     rax, rdi
0x140014a3c  jb      short loc_140014A26
0x140014a3e  jmp     short loc_140014A47
0x140014a40  mov     r14, [rcx]
0x140014a43  mov     r15, [rcx+8]
0x140014a47  test    rbp, rbp
0x140014a4a  jz      short loc_140014A55
0x140014a4c  mov     rcx, rbp; SRWLock
0x140014a4f  call    cs:__imp_ReleaseSRWLockExclusive
0x140014a55  test    r14, r14
0x140014a58  jz      short loc_140014A65
0x140014a5a  mov     rcx, r15
0x140014a5d  mov     rax, r14
0x140014a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a65  test    rsi, rsi
0x140014a68  jz      short loc_140014A73
0x140014a6a  mov     rcx, rsi; lpCriticalSection
0x140014a6d  call    cs:__imp_LeaveCriticalSection
0x140014a73  cmp     rbx, rdi
0x140014a76  jb      short loc_140014A05
0x140014a78  add     rsp, 28h
0x140014a7c  pop     r15
0x140014a7e  pop     r14
0x140014a80  pop     rdi
0x140014a81  pop     rsi
0x140014a82  pop     rbp
0x140014a83  pop     rbx
0x140014a84  retn
```
