# CSpinLock::WriteLock(void)

- ea: `0x18000f300`
- end: `0x18000f333`
- name: `?WriteLock@CSpinLock@@QEAAXXZ`
- size: `51`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f210`
- `0x18000f340`
- `0x18000f3a0`
- `0x180015cc0`
- `0x18001abe0`
- `0x18001b090`
- `0x18001b0f0`
- `0x18001b1a0`
- `0x18001b240`
- `0x18001b2b0`
- `0x18001b320`

## callees

- `0x18000f300`
- `0x18000f950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f30f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f30f`

## pseudocode

```c
void __fastcall CSpinLock::WriteLock(CSpinLock *this)
{
  if ( *(_DWORD *)this
    || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFFC | 1, 0) )
  {
    CSpinLock::_Lock(this);
  }
}

```

## disassembly

```asm
0x18000f300  push    rbx; public: void CSpinLock::ReadLock(void)
0x18000f302  sub     rsp, 20h
0x18000f306  mov     eax, [rcx]
0x18000f308  mov     rbx, rcx
0x18000f30b  test    eax, eax
0x18000f30d  jnz     short loc_18000F325
0x18000f30f  call    cs:__imp_GetCurrentThreadId
0x18000f315  mov     edx, eax
0x18000f317  and     edx, 0FFFFFFFDh
0x18000f31a  or      edx, 1
0x18000f31d  xor     eax, eax
0x18000f31f  lock cmpxchg [rbx], edx
0x18000f323  jz      short loc_18000F32D
0x18000f325  mov     rcx, rbx; this
0x18000f328  call    ?_Lock@CSpinLock@@AEAAXXZ; CSpinLock::_Lock(void)
0x18000f32d  add     rsp, 20h
0x18000f331  pop     rbx
0x18000f332  retn
```
