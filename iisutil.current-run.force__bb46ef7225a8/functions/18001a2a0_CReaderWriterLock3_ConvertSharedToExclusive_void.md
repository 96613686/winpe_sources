# CReaderWriterLock3::ConvertSharedToExclusive(void)

- ea: `0x18001a2a0`
- end: `0x18001a2e5`
- name: `?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ`
- size: `69`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a250`
- `0x18001a290`

## callees

- `0x180007180`
- `0x18000e850`
- `0x18001a2a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a2bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a2bb`

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
0x18001a2a0  push    rbx
0x18001a2a2  sub     rsp, 20h
0x18001a2a6  mov     eax, [rcx]
0x18001a2a8  mov     rbx, rcx
0x18001a2ab  cmp     eax, 1
0x18001a2ae  jnz     short loc_18001A2D0
0x18001a2b0  mov     ecx, 1FFFFh
0x18001a2b5  lock cmpxchg [rbx], ecx
0x18001a2b9  jnz     short loc_18001A2D0
0x18001a2bb  call    cs:__imp_GetCurrentThreadId
0x18001a2c1  and     eax, 0FFFFFFFCh
0x18001a2c4  or      eax, 1
0x18001a2c7  xchg    eax, [rbx+4]
0x18001a2ca  add     rsp, 20h
0x18001a2ce  pop     rbx
0x18001a2cf  retn
0x18001a2d0  mov     rcx, rbx; this
0x18001a2d3  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001a2d8  mov     rcx, rbx; this
0x18001a2db  add     rsp, 20h
0x18001a2df  pop     rbx
0x18001a2e0  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
```
