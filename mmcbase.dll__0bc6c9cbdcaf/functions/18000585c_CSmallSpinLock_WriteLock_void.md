# CSmallSpinLock::WriteLock(void)

- ea: `0x18000585c`
- end: `0x180005889`
- name: `?WriteLock@CSmallSpinLock@@QEAAXXZ`
- size: `45`
- prototype: `void __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800057f0`
- `0x18000edf8`
- `0x18000f43c`
- `0x18000f6d8`
- `0x18000f8dc`
- `0x18000f9d8`

## callees

- `0x18000585c`
- `0x18001984c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000586b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000586b`

## pseudocode

```c
void __fastcall CSmallSpinLock::WriteLock(CSmallSpinLock *this)
{
  if ( *(_DWORD *)this || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) )
    CSmallSpinLock::_LockSpin(this);
}

```

## disassembly

```asm
0x18000585c  push    rbx
0x18000585e  sub     rsp, 20h
0x180005862  mov     eax, [rcx]
0x180005864  mov     rbx, rcx
0x180005867  test    eax, eax
0x180005869  jnz     short loc_18000587B
0x18000586b  call    cs:__imp_GetCurrentThreadId
0x180005871  mov     edx, eax
0x180005873  xor     eax, eax
0x180005875  lock cmpxchg [rbx], edx
0x180005879  jz      short loc_180005883
0x18000587b  mov     rcx, rbx; this
0x18000587e  call    ?_LockSpin@CSmallSpinLock@@AEAAXXZ; CSmallSpinLock::_LockSpin(void)
0x180005883  add     rsp, 20h
0x180005887  pop     rbx
0x180005888  retn
```
