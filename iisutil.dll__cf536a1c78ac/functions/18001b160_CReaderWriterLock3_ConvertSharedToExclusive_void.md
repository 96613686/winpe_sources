# CReaderWriterLock3::ConvertSharedToExclusive(void)

- ea: `0x18001b160`
- end: `0x18001b1ac`
- name: `?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ`
- size: `76`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b110`
- `0x18001b150`

## callees

- `0x180007e60`
- `0x18000f810`
- `0x18001b160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b17b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b17b`

## pseudocode

```c
void __fastcall CReaderWriterLock3::ConvertSharedToExclusive(CReaderWriterLock3 *this)
{
  if ( *(_DWORD *)this == 1 && _InterlockedCompareExchange((volatile signed __int32 *)this, 0x1FFFF, 1) == 1 )
  {
    _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
  else
  {
    CReaderWriterLock3::ReadUnlock(this);
    CReaderWriterLock3::_WriteLockSpin(this);
  }
}

```

## disassembly

```asm
0x18001b160  push    rbx
0x18001b162  sub     rsp, 20h
0x18001b166  mov     eax, [rcx]
0x18001b168  mov     rbx, rcx
0x18001b16b  cmp     eax, 1
0x18001b16e  jnz     short loc_18001B197
0x18001b170  mov     ecx, 1FFFFh
0x18001b175  lock cmpxchg [rbx], ecx
0x18001b179  jnz     short loc_18001B197
0x18001b17b  call    cs:__imp_GetCurrentThreadId
0x18001b182  nop     dword ptr [rax+rax+00h]
0x18001b187  and     eax, 0FFFFFFFCh
0x18001b18a  or      eax, 1
0x18001b18d  xchg    eax, [rbx+4]
0x18001b190  add     rsp, 20h
0x18001b194  pop     rbx
0x18001b195  retn
0x18001b197  mov     rcx, rbx; this
0x18001b19a  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001b19f  mov     rcx, rbx; this
0x18001b1a2  add     rsp, 20h
0x18001b1a6  pop     rbx
0x18001b1a7  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
```
