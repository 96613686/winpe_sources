# SiAcquireSpinLock(void * *)

- ea: `0x1800353e0`
- end: `0x18003540e`
- name: `?SiAcquireSpinLock@@YAXPEAPEAX@Z`
- size: `46`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003558c`
- `0x180035684`

## callees

- `0x1800353e0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800353e4`
- `KERNEL32!GetCurrentThreadId` at `0x1800353e4`

## pseudocode

```c
void __fastcall SiAcquireSpinLock(void **a1)
{
  signed __int64 CurrentThreadId; // rcx

  CurrentThreadId = GetCurrentThreadId();
  while ( _InterlockedCompareExchange64((volatile signed __int64 *)&Lock, CurrentThreadId, 0) )
  {
    do
      _mm_pause();
    while ( Lock );
  }
}

```

## disassembly

```asm
0x1800353e0  sub     rsp, 28h
0x1800353e4  call    cs:__imp_GetCurrentThreadId
0x1800353ea  mov     ecx, eax
0x1800353ec  jmp     short loc_1800353FC
0x1800353ee  pause
0x1800353f0  mov     rax, cs:?Lock@@3PEAXEA; void * Lock
0x1800353f7  test    rax, rax
0x1800353fa  jnz     short loc_1800353EE
0x1800353fc  xor     eax, eax
0x1800353fe  lock cmpxchg cs:?Lock@@3PEAXEA, rcx; void * Lock
0x180035407  jnz     short loc_1800353EE
0x180035409  add     rsp, 28h
0x18003540d  retn
```
