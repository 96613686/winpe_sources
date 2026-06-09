# HyperVRepository::LockExclusiveIfNeeded(void)

- ea: `0x180093e48`
- end: `0x180093edc`
- name: `?LockExclusiveIfNeeded@HyperVRepository@@AEAAHXZ`
- size: `148`
- prototype: `__int64 __fastcall(HyperVRepository *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180093180`
- `0x1800945d0`

## callees

- `0x180093e48`
- `0x180094860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180093ec7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180093ec7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180093e69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180093e69`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180093e89`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180093e89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093e8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093e8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093eb1`

## pseudocode

```c
__int64 __fastcall HyperVRepository::LockExclusiveIfNeeded(HyperVRepository *this)
{
  unsigned int v2; // edi

  if ( HyperVRepository::ThreadHoldsExclusiveLock(this) )
  {
    return 0;
  }
  else
  {
    v2 = 1;
    AcquireSRWLockExclusive((PSRWLOCK)this + 14);
    while ( 1 )
    {
      *((_DWORD *)this + 30) = GetCurrentThreadId();
      if ( !*((_DWORD *)this + 35) )
        break;
      *((_DWORD *)this + 30) = 0;
      SleepConditionVariableSRW((PCONDITION_VARIABLE)this + 16, (PSRWLOCK)this + 14, 0xFFFFFFFF, 0);
    }
    *((_DWORD *)this + 34) = 1;
    *((_DWORD *)this + 35) = -1;
    *((_DWORD *)this + 36) = GetCurrentThreadId();
    *((_DWORD *)this + 30) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 14);
  }
  return v2;
}

```

## disassembly

```asm
0x180093e48  push    rbx
0x180093e4a  push    rbp
0x180093e4b  push    rsi
0x180093e4c  push    rdi
0x180093e4d  sub     rsp, 28h
0x180093e51  mov     rbx, rcx
0x180093e54  call    ?ThreadHoldsExclusiveLock@HyperVRepository@@UEBA_NXZ; HyperVRepository::ThreadHoldsExclusiveLock(void)
0x180093e59  test    al, al
0x180093e5b  jnz     short loc_180093ECF
0x180093e5d  lea     rsi, [rbx+70h]
0x180093e61  mov     edi, 1
0x180093e66  mov     rcx, rsi; SRWLock
0x180093e69  call    cs:__imp_AcquireSRWLockExclusive
0x180093e6f  jmp     short loc_180093E8F
0x180093e71  xor     r9d, r9d; Flags
0x180093e74  mov     dword ptr [rsi+8], 0
0x180093e7b  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180093e7f  lea     rcx, [rbx+80h]; ConditionVariable
0x180093e86  mov     rdx, rsi; SRWLock
0x180093e89  call    cs:__imp_SleepConditionVariableSRW
0x180093e8f  call    cs:__imp_GetCurrentThreadId
0x180093e95  mov     [rsi+8], eax
0x180093e98  cmp     dword ptr [rbx+8Ch], 0
0x180093e9f  jnz     short loc_180093E71
0x180093ea1  mov     [rbx+88h], edi
0x180093ea7  mov     dword ptr [rbx+8Ch], 0FFFFFFFFh
0x180093eb1  call    cs:__imp_GetCurrentThreadId
0x180093eb7  mov     [rbx+90h], eax
0x180093ebd  mov     rcx, rsi; SRWLock
0x180093ec0  mov     dword ptr [rsi+8], 0
0x180093ec7  call    cs:__imp_ReleaseSRWLockExclusive
0x180093ecd  jmp     short loc_180093ED1
0x180093ecf  xor     edi, edi
0x180093ed1  mov     eax, edi
0x180093ed3  add     rsp, 28h
0x180093ed7  pop     rdi
0x180093ed8  pop     rsi
0x180093ed9  pop     rbp
0x180093eda  pop     rbx
0x180093edb  retn
```
