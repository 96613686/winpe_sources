# CSpinLock::_Lock(void)

- ea: `0x18000f950`
- end: `0x18000f981`
- name: `?_Lock@CSpinLock@@AEAAXXZ`
- size: `49`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f300`

## callees

- `0x18000f950`
- `0x18000f990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f959`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f959`

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
0x18000f950  push    rbx
0x18000f952  sub     rsp, 20h
0x18000f956  mov     rbx, rcx
0x18000f959  call    cs:__imp_GetCurrentThreadId
0x18000f95f  mov     edx, [rbx]
0x18000f961  and     eax, 0FFFFFFFCh
0x18000f964  and     edx, 0FFFFFFFCh
0x18000f967  cmp     edx, eax
0x18000f969  jnz     short loc_18000F974
0x18000f96b  lock inc dword ptr [rbx]
0x18000f96e  add     rsp, 20h
0x18000f972  pop     rbx
0x18000f973  retn
0x18000f974  mov     rcx, rbx; this
0x18000f977  add     rsp, 20h
0x18000f97b  pop     rbx
0x18000f97c  jmp     ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
```
