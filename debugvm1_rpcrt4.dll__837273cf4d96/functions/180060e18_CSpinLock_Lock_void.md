# CSpinLock::Lock(void)

- ea: `0x180060e18`
- end: `0x180060e74`
- name: `?Lock@CSpinLock@@QEAAXXZ`
- size: `92`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004d650`
- `0x18005b4c8`
- `0x18005fe3c`
- `0x18006008c`
- `0x1800604f0`
- `0x180060928`
- `0x180060b54`
- `0x180060c20`
- `0x180061108`
- `0x180080400`
- `0x18009c3d0`
- `0x1800a1070`
- `0x1800c6060`
- `0x1800c61a0`
- `0x1800c6370`
- `0x1800c63e0`
- `0x1800c64b0`
- `0x1800c6700`
- `0x1800c6920`
- `0x1800c6a10`

## callees

- `0x180060e18`
- `0x18006220c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060e27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060e41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060e27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060e41`

## pseudocode

```c
void __fastcall CSpinLock::Lock(CSpinLock *this)
{
  if ( *(_DWORD *)this
    || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFF | 0x10000000, 0) )
  {
    if ( (*(_DWORD *)this & 0xFFFFFFF) == (GetCurrentThreadId() & 0xFFFFFFF) )
      _InterlockedExchange((volatile __int32 *)this, *(_DWORD *)this + 0x10000000);
    else
      CSpinLock::_LockSpin(this);
  }
}

```

## disassembly

```asm
0x180060e18  push    rbx
0x180060e1a  sub     rsp, 20h
0x180060e1e  mov     eax, [rcx]
0x180060e20  mov     rbx, rcx
0x180060e23  test    eax, eax
0x180060e25  jnz     short loc_180060E41
0x180060e27  call    cs:__imp_GetCurrentThreadId
0x180060e2d  mov     edx, eax
0x180060e2f  and     edx, 0FFFFFFFh
0x180060e35  bts     edx, 1Ch
0x180060e39  xor     eax, eax
0x180060e3b  lock cmpxchg [rbx], edx
0x180060e3f  jz      short loc_180060E61
0x180060e41  call    cs:__imp_GetCurrentThreadId
0x180060e47  mov     ecx, [rbx]
0x180060e49  and     eax, 0FFFFFFFh
0x180060e4e  and     ecx, 0FFFFFFFh
0x180060e54  cmp     ecx, eax
0x180060e56  jnz     short loc_180060E67
0x180060e58  mov     eax, [rbx]
0x180060e5a  add     eax, 10000000h
0x180060e5f  xchg    eax, [rbx]
0x180060e61  add     rsp, 20h
0x180060e65  pop     rbx
0x180060e66  retn
0x180060e67  mov     rcx, rbx; this
0x180060e6a  add     rsp, 20h
0x180060e6e  pop     rbx
0x180060e6f  jmp     ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
```
