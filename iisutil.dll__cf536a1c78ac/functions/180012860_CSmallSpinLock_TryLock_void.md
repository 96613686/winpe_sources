# CSmallSpinLock::_TryLock(void)

- ea: `0x180012860`
- end: `0x180012891`
- name: `?_TryLock@CSmallSpinLock@@AEAA_NXZ`
- size: `49`
- prototype: `bool __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012860`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001286f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001286f`

## pseudocode

```c
bool __fastcall CSmallSpinLock::_TryLock(CSmallSpinLock *this)
{
  return !*(_DWORD *)this && _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) == 0;
}

```

## disassembly

```asm
0x180012860  push    rbx
0x180012862  sub     rsp, 20h
0x180012866  mov     eax, [rcx]
0x180012868  mov     rbx, rcx
0x18001286b  test    eax, eax
0x18001286d  jnz     short loc_18001288D
0x18001286f  call    cs:__imp_GetCurrentThreadId
0x180012876  nop     dword ptr [rax+rax+00h]
0x18001287b  mov     edx, eax
0x18001287d  xor     eax, eax
0x18001287f  lock cmpxchg [rbx], edx
0x180012883  setz    al
0x180012886  add     rsp, 20h
0x18001288a  pop     rbx
0x18001288b  retn
0x18001288d  xor     al, al
0x18001288f  jmp     short loc_180012886
```
