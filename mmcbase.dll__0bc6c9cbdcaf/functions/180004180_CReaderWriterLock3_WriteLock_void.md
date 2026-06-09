# CReaderWriterLock3::WriteLock(void)

- ea: `0x180004180`
- end: `0x1800041e9`
- name: `?WriteLock@CReaderWriterLock3@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800015e0`
- `0x180001f10`
- `0x180003890`

## callees

- `0x180004180`
- `0x180019a34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041c2`

## pseudocode

```c
void __fastcall CReaderWriterLock3::WriteLock(CReaderWriterLock3 *this)
{
  signed __int32 v2; // edx

  if ( *((_DWORD *)this + 1)
    || (unsigned __int16)*(_DWORD *)this
    || (v2 = *(_DWORD *)this,
        v2 != _InterlockedCompareExchange((volatile signed __int32 *)this, (v2 + 0x10000) | 0xFFFF, v2)) )
  {
    if ( (*((_DWORD *)this + 1) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedExchange((volatile __int32 *)this + 1, *((_DWORD *)this + 1) + 1);
    else
      CReaderWriterLock3::_WriteLockSpin(this);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
}

```

## disassembly

```asm
0x180004180  push    rbx
0x180004182  sub     rsp, 20h
0x180004186  mov     eax, [rcx+4]
0x180004189  mov     rbx, rcx
0x18000418c  test    eax, eax
0x18000418e  jnz     short loc_1800041C2
0x180004190  mov     edx, [rcx]
0x180004192  test    dx, dx
0x180004195  jnz     short loc_1800041C2
0x180004197  lea     ecx, [rdx+10000h]
0x18000419d  mov     eax, edx
0x18000419f  or      ecx, 0FFFFh
0x1800041a5  lock cmpxchg [rbx], ecx
0x1800041a9  cmp     edx, eax
0x1800041ab  jnz     short loc_1800041C2
0x1800041ad  call    cs:__imp_GetCurrentThreadId
0x1800041b3  and     eax, 0FFFFFFFCh
0x1800041b6  or      eax, 1
0x1800041b9  xchg    eax, [rbx+4]
0x1800041bc  add     rsp, 20h
0x1800041c0  pop     rbx
0x1800041c1  retn
0x1800041c2  call    cs:__imp_GetCurrentThreadId
0x1800041c8  mov     ecx, [rbx+4]
0x1800041cb  and     eax, 0FFFFFFFCh
0x1800041ce  and     ecx, 0FFFFFFFCh
0x1800041d1  cmp     ecx, eax
0x1800041d3  jnz     short loc_1800041DF
0x1800041d5  mov     eax, [rbx+4]
0x1800041d8  inc     eax
0x1800041da  xchg    eax, [rbx+4]
0x1800041dd  jmp     short loc_1800041BC
0x1800041df  mov     rcx, rbx; this
0x1800041e2  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x1800041e7  jmp     short loc_1800041BC
```
