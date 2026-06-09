# CSmallSpinLock::_TryLock(void)

- ea: `0x180011f40`
- end: `0x180011f6a`
- name: `?_TryLock@CSmallSpinLock@@AEAA_NXZ`
- size: `42`
- prototype: `bool __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011f40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f4f`

## pseudocode

```c
bool __fastcall CSmallSpinLock::_TryLock(CSmallSpinLock *this)
{
  return !*(_DWORD *)this && _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) == 0;
}

```

## disassembly

```asm
0x180011f40  push    rbx
0x180011f42  sub     rsp, 20h
0x180011f46  mov     eax, [rcx]
0x180011f48  mov     rbx, rcx
0x180011f4b  test    eax, eax
0x180011f4d  jnz     short loc_180011F66
0x180011f4f  call    cs:__imp_GetCurrentThreadId
0x180011f55  mov     edx, eax
0x180011f57  xor     eax, eax
0x180011f59  lock cmpxchg [rbx], edx
0x180011f5d  setz    al
0x180011f60  add     rsp, 20h
0x180011f64  pop     rbx
0x180011f65  retn
0x180011f66  xor     al, al
0x180011f68  jmp     short loc_180011F60
```
