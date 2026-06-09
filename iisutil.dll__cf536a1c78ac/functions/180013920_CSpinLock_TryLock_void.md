# CSpinLock::_TryLock(void)

- ea: `0x180013920`
- end: `0x180013957`
- name: `?_TryLock@CSpinLock@@AEAA_NXZ`
- size: `55`
- prototype: `bool __fastcall(CSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013920`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001392f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001392f`

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
0x180013920  push    rbx
0x180013922  sub     rsp, 20h
0x180013926  mov     eax, [rcx]
0x180013928  mov     rbx, rcx
0x18001392b  test    eax, eax
0x18001392d  jnz     short loc_180013953
0x18001392f  call    cs:__imp_GetCurrentThreadId
0x180013936  nop     dword ptr [rax+rax+00h]
0x18001393b  mov     edx, eax
0x18001393d  and     edx, 0FFFFFFFDh
0x180013940  or      edx, 1
0x180013943  xor     eax, eax
0x180013945  lock cmpxchg [rbx], edx
0x180013949  setz    al
0x18001394c  add     rsp, 20h
0x180013950  pop     rbx
0x180013951  retn
0x180013953  xor     al, al
0x180013955  jmp     short loc_18001394C
```
