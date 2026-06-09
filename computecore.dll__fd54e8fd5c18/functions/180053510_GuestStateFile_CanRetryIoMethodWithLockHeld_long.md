# GuestStateFile::CanRetryIoMethodWithLockHeld(long)

- ea: `0x180053510`
- end: `0x1800535d2`
- name: `?CanRetryIoMethodWithLockHeld@GuestStateFile@@AEBA_NJ@Z`
- size: `194`
- prototype: `bool __fastcall(GuestStateFile *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18009ea76`
- `0x18009eadc`

## callees

- `0x180053510`
- `0x180054730`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800535b5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800535b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800535ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800535ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180053566`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180053566`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005356f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005356f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005353f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053575`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005353f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053575`

## pseudocode

```c
bool __fastcall GuestStateFile::CanRetryIoMethodWithLockHeld(RTL_SRWLOCK *this, int a2)
{
  bool IsErrorRetryable; // r14
  RTL_SRWLOCK *v4; // rbx
  DWORD *v5; // rsi
  int v6; // edi
  int v8; // [rsp+68h] [rbp+20h]

  IsErrorRetryable = GuestStateFile::IsErrorRetryable((GuestStateFile *)this, a2);
  if ( IsErrorRetryable )
  {
    v4 = this + 5;
    v5 = (DWORD *)&this[6];
    if ( GetCurrentThreadId() == LODWORD(this[6].Ptr) )
    {
      v6 = 1;
      v8 = 1;
    }
    else
    {
      v6 = 0;
      v8 = 0;
      ReleaseSRWLockShared(this + 5);
      AcquireSRWLockExclusive(this + 5);
      *v5 = GetCurrentThreadId();
    }
    try
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)this[7].Ptr + 24LL))(this[7].Ptr);
    }
    catch ( ... )
    {
      IsErrorRetryable = 0;
      v6 = v8;
      v4 = this + 5;
      v5 = (DWORD *)&this[6];
    }
    if ( !v6 )
    {
      *v5 = 0;
      ReleaseSRWLockExclusive(v4);
      AcquireSRWLockShared(v4);
    }
  }
  return IsErrorRetryable;
}

```

## disassembly

```asm
0x180053510  mov     [rsp+arg_0], rbx
0x180053515  mov     [rsp+arg_8], rsi
0x18005351a  push    rdi
0x18005351b  push    r14
0x18005351d  push    r15
0x18005351f  sub     rsp, 30h
0x180053523  mov     r15, rcx
0x180053526  call    ?IsErrorRetryable@GuestStateFile@@AEBA_NJ@Z; GuestStateFile::IsErrorRetryable(long)
0x18005352b  mov     r14b, al
0x18005352e  test    al, al
0x180053530  jz      loc_1800535BB
0x180053536  lea     rbx, [r15+28h]
0x18005353a  mov     [rsp+48h+var_28], rbx
0x18005353f  call    cs:__imp_GetCurrentThreadId
0x180053545  lea     rsi, [rbx+8]
0x180053549  mov     [rsp+48h+var_20], rsi
0x18005354e  cmp     eax, [rsi]
0x180053550  jnz     short loc_18005355D
0x180053552  mov     edi, 1
0x180053557  mov     [rsp+48h+arg_18], edi
0x18005355b  jmp     short loc_18005357D
0x18005355d  xor     edi, edi
0x18005355f  mov     [rsp+48h+arg_18], edi
0x180053563  mov     rcx, rbx; SRWLock
0x180053566  call    cs:__imp_ReleaseSRWLockShared
0x18005356c  mov     rcx, rbx; SRWLock
0x18005356f  call    cs:__imp_AcquireSRWLockExclusive
0x180053575  call    cs:__imp_GetCurrentThreadId
0x18005357b  mov     [rsi], eax
0x18005357d  mov     rcx, [r15+38h]
0x180053581  mov     rax, [rcx]
0x180053584  mov     rax, [rax+18h]
0x180053588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005358d  nop
0x18005358e  jmp     short loc_1800535A3
0x180053590  mov     r14b, [rsp+48h+arg_10]
0x180053595  mov     edi, [rsp+48h+arg_18]
0x180053599  mov     rbx, [rsp+48h+var_28]
0x18005359e  mov     rsi, [rsp+48h+var_20]
0x1800535a3  test    edi, edi
0x1800535a5  jnz     short loc_1800535BB
0x1800535a7  mov     [rsi], edi
0x1800535a9  mov     rcx, rbx; SRWLock
0x1800535ac  call    cs:__imp_ReleaseSRWLockExclusive
0x1800535b2  mov     rcx, rbx; SRWLock
0x1800535b5  call    cs:__imp_AcquireSRWLockShared
0x1800535bb  mov     al, r14b
0x1800535be  mov     rbx, [rsp+48h+arg_0]
0x1800535c3  mov     rsi, [rsp+48h+arg_8]
0x1800535c8  add     rsp, 30h
0x1800535cc  pop     r15
0x1800535ce  pop     r14
0x1800535d0  pop     rdi
0x1800535d1  retn
```
