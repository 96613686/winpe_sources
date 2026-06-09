# CSmallSpinLock::WriteLock(void)

- ea: `0x1800182b0`
- end: `0x1800182dd`
- name: `?WriteLock@CSmallSpinLock@@QEAAXXZ`
- size: `45`
- prototype: `void __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800182b0`
- `0x1800182f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800182bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800182bf`

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
0x1800182b0  push    rbx; public: void CSmallSpinLock::ReadLock(void)
0x1800182b2  sub     rsp, 20h
0x1800182b6  mov     eax, [rcx]
0x1800182b8  mov     rbx, rcx
0x1800182bb  test    eax, eax
0x1800182bd  jnz     short loc_1800182CF
0x1800182bf  call    cs:__imp_GetCurrentThreadId
0x1800182c5  mov     edx, eax
0x1800182c7  xor     eax, eax
0x1800182c9  lock cmpxchg [rbx], edx
0x1800182cd  jz      short loc_1800182D7
0x1800182cf  mov     rcx, rbx; this
0x1800182d2  call    ?_LockSpin@CSmallSpinLock@@AEAAXXZ; CSmallSpinLock::_LockSpin(void)
0x1800182d7  add     rsp, 20h
0x1800182db  pop     rbx
0x1800182dc  retn
```
