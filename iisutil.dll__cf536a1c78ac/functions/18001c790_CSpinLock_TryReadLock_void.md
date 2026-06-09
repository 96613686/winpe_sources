# CSpinLock::TryReadLock(void)

- ea: `0x18001c790`
- end: `0x18001c7c7`
- name: `?TryReadLock@CSpinLock@@QEAA_NXZ`
- size: `55`
- prototype: `bool __fastcall(CSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c790`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c79f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c79f`

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
0x18001c790  push    rbx; public: bool CSpinLock::TryReadLock(void)
0x18001c792  sub     rsp, 20h
0x18001c796  mov     eax, [rcx]
0x18001c798  mov     rbx, rcx
0x18001c79b  test    eax, eax
0x18001c79d  jnz     short loc_18001C7BE
0x18001c79f  call    cs:__imp_GetCurrentThreadId
0x18001c7a6  nop     dword ptr [rax+rax+00h]
0x18001c7ab  mov     edx, eax
0x18001c7ad  and     edx, 0FFFFFFFDh
0x18001c7b0  or      edx, 1
0x18001c7b3  xor     eax, eax
0x18001c7b5  lock cmpxchg [rbx], edx
0x18001c7b9  setz    al
0x18001c7bc  jmp     short loc_18001C7C0
0x18001c7be  xor     al, al
0x18001c7c0  add     rsp, 20h
0x18001c7c4  pop     rbx
0x18001c7c5  retn
```
