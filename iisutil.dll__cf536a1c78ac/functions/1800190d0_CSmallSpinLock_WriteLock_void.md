# CSmallSpinLock::WriteLock(void)

- ea: `0x1800190d0`
- end: `0x180019104`
- name: `?WriteLock@CSmallSpinLock@@QEAAXXZ`
- size: `52`
- prototype: `void __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800190d0`
- `0x180019110`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800190df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800190df`

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
0x1800190d0  push    rbx; public: void CSmallSpinLock::ReadLock(void)
0x1800190d2  sub     rsp, 20h
0x1800190d6  mov     eax, [rcx]
0x1800190d8  mov     rbx, rcx
0x1800190db  test    eax, eax
0x1800190dd  jnz     short loc_1800190F5
0x1800190df  call    cs:__imp_GetCurrentThreadId
0x1800190e6  nop     dword ptr [rax+rax+00h]
0x1800190eb  mov     edx, eax
0x1800190ed  xor     eax, eax
0x1800190ef  lock cmpxchg [rbx], edx
0x1800190f3  jz      short loc_1800190FD
0x1800190f5  mov     rcx, rbx; this
0x1800190f8  call    ?_LockSpin@CSmallSpinLock@@AEAAXXZ; CSmallSpinLock::_LockSpin(void)
0x1800190fd  add     rsp, 20h
0x180019101  pop     rbx
0x180019102  retn
```
