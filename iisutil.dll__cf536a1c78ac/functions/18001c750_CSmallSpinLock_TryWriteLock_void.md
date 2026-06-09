# CSmallSpinLock::TryWriteLock(void)

- ea: `0x18001c750`
- end: `0x18001c781`
- name: `?TryWriteLock@CSmallSpinLock@@QEAA_NXZ`
- size: `49`
- prototype: `bool __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c75f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c75f`

## pseudocode

```c
bool __fastcall CSmallSpinLock::TryWriteLock(CSmallSpinLock *this)
{
  return !*(_DWORD *)this && _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) == 0;
}

```

## disassembly

```asm
0x18001c750  push    rbx; public: bool CSmallSpinLock::TryReadLock(void)
0x18001c752  sub     rsp, 20h
0x18001c756  mov     eax, [rcx]
0x18001c758  mov     rbx, rcx
0x18001c75b  test    eax, eax
0x18001c75d  jnz     short loc_18001C778
0x18001c75f  call    cs:__imp_GetCurrentThreadId
0x18001c766  nop     dword ptr [rax+rax+00h]
0x18001c76b  mov     edx, eax
0x18001c76d  xor     eax, eax
0x18001c76f  lock cmpxchg [rbx], edx
0x18001c773  setz    al
0x18001c776  jmp     short loc_18001C77A
0x18001c778  xor     al, al
0x18001c77a  add     rsp, 20h
0x18001c77e  pop     rbx
0x18001c77f  retn
```
