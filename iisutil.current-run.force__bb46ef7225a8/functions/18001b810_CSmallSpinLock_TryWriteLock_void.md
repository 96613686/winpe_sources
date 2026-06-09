# CSmallSpinLock::TryWriteLock(void)

- ea: `0x18001b810`
- end: `0x18001b83a`
- name: `?TryWriteLock@CSmallSpinLock@@QEAA_NXZ`
- size: `42`
- prototype: `bool __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001b810`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b81f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b81f`

## pseudocode

```c
bool __fastcall CSmallSpinLock::TryWriteLock(CSmallSpinLock *this)
{
  return !*(_DWORD *)this && _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) == 0;
}

```

## disassembly

```asm
0x18001b810  push    rbx; public: bool CSmallSpinLock::TryReadLock(void)
0x18001b812  sub     rsp, 20h
0x18001b816  mov     eax, [rcx]
0x18001b818  mov     rbx, rcx
0x18001b81b  test    eax, eax
0x18001b81d  jnz     short loc_18001B832
0x18001b81f  call    cs:__imp_GetCurrentThreadId
0x18001b825  mov     edx, eax
0x18001b827  xor     eax, eax
0x18001b829  lock cmpxchg [rbx], edx
0x18001b82d  setz    al
0x18001b830  jmp     short loc_18001B834
0x18001b832  xor     al, al
0x18001b834  add     rsp, 20h
0x18001b838  pop     rbx
0x18001b839  retn
```
