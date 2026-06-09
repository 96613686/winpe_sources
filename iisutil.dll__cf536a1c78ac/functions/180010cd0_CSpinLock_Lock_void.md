# CSpinLock::_Lock(void)

- ea: `0x180010cd0`
- end: `0x180010d08`
- name: `?_Lock@CSpinLock@@AEAAXXZ`
- size: `56`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010640`

## callees

- `0x180010cd0`
- `0x180010d10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010cd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010cd9`

## pseudocode

```c
void __fastcall CSpinLock::_Lock(CSpinLock *this)
{
  if ( (*(_DWORD *)this & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
    _InterlockedIncrement((volatile signed __int32 *)this);
  else
    CSpinLock::_LockSpin(this);
}

```

## disassembly

```asm
0x180010cd0  push    rbx
0x180010cd2  sub     rsp, 20h
0x180010cd6  mov     rbx, rcx
0x180010cd9  call    cs:__imp_GetCurrentThreadId
0x180010ce0  nop     dword ptr [rax+rax+00h]
0x180010ce5  mov     edx, [rbx]
0x180010ce7  and     eax, 0FFFFFFFCh
0x180010cea  and     edx, 0FFFFFFFCh
0x180010ced  cmp     edx, eax
0x180010cef  jnz     short loc_180010CFB
0x180010cf1  lock inc dword ptr [rbx]
0x180010cf4  add     rsp, 20h
0x180010cf8  pop     rbx
0x180010cf9  retn
0x180010cfb  mov     rcx, rbx; this
0x180010cfe  add     rsp, 20h
0x180010d02  pop     rbx
0x180010d03  jmp     ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
```
