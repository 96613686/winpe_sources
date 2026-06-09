# CSpinLock::TryReadLock(void)

- ea: `0x18001b840`
- end: `0x18001b870`
- name: `?TryReadLock@CSpinLock@@QEAA_NXZ`
- size: `48`
- prototype: `bool __fastcall(CSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001b840`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b84f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b84f`

## pseudocode

```c
bool __fastcall CSpinLock::TryReadLock(CSpinLock *this)
{
  return !*(_DWORD *)this
      && _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFFC | 1, 0) == 0;
}

```

## disassembly

```asm
0x18001b840  push    rbx; public: bool CSpinLock::TryReadLock(void)
0x18001b842  sub     rsp, 20h
0x18001b846  mov     eax, [rcx]
0x18001b848  mov     rbx, rcx
0x18001b84b  test    eax, eax
0x18001b84d  jnz     short loc_18001B868
0x18001b84f  call    cs:__imp_GetCurrentThreadId
0x18001b855  mov     edx, eax
0x18001b857  and     edx, 0FFFFFFFDh
0x18001b85a  or      edx, 1
0x18001b85d  xor     eax, eax
0x18001b85f  lock cmpxchg [rbx], edx
0x18001b863  setz    al
0x18001b866  jmp     short loc_18001B86A
0x18001b868  xor     al, al
0x18001b86a  add     rsp, 20h
0x18001b86e  pop     rbx
0x18001b86f  retn
```
