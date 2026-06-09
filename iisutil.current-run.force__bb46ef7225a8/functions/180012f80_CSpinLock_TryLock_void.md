# CSpinLock::_TryLock(void)

- ea: `0x180012f80`
- end: `0x180012fb0`
- name: `?_TryLock@CSpinLock@@AEAA_NXZ`
- size: `48`
- prototype: `bool __fastcall(CSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012f80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012f8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012f8f`

## pseudocode

```c
bool __fastcall CSpinLock::_TryLock(CSpinLock *this)
{
  return !*(_DWORD *)this
      && _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFFC | 1, 0) == 0;
}

```

## disassembly

```asm
0x180012f80  push    rbx
0x180012f82  sub     rsp, 20h
0x180012f86  mov     eax, [rcx]
0x180012f88  mov     rbx, rcx
0x180012f8b  test    eax, eax
0x180012f8d  jnz     short loc_180012FAC
0x180012f8f  call    cs:__imp_GetCurrentThreadId
0x180012f95  mov     edx, eax
0x180012f97  and     edx, 0FFFFFFFDh
0x180012f9a  or      edx, 1
0x180012f9d  xor     eax, eax
0x180012f9f  lock cmpxchg [rbx], edx
0x180012fa3  setz    al
0x180012fa6  add     rsp, 20h
0x180012faa  pop     rbx
0x180012fab  retn
0x180012fac  xor     al, al
0x180012fae  jmp     short loc_180012FA6
```
