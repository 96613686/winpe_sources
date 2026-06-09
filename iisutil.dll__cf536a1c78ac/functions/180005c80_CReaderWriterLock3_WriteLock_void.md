# CReaderWriterLock3::WriteLock(void)

- ea: `0x180005c80`
- end: `0x180005cfa`
- name: `?WriteLock@CReaderWriterLock3@@QEAAXXZ`
- size: `122`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ec0`
- `0x180004c30`
- `0x180005d00`
- `0x180005f60`
- `0x180006730`
- `0x180008f60`
- `0x18000bd90`
- `0x180010f90`
- `0x180011210`
- `0x180012340`
- `0x180012930`
- `0x1800138b0`
- `0x180014df0`
- `0x180016620`
- `0x180017030`
- `0x1800172c0`
- `0x18001ad60`
- `0x18001afd0`
- `0x18001b1e0`
- `0x180028950`
- `0x1800298e0`
- `0x18002a2b0`
- `0x18002a370`
- `0x18002af70`
- `0x18002b570`
- `0x18002bb20`
- `0x18002dde0`

## callees

- `0x180005c80`
- `0x180007e60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cd3`

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
      _InterlockedIncrement((volatile signed __int32 *)this + 1);
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
0x180005c80  push    rbx
0x180005c82  sub     rsp, 20h
0x180005c86  mov     eax, [rcx+4]
0x180005c89  mov     rbx, rcx
0x180005c8c  test    eax, eax
0x180005c8e  jnz     short loc_180005CAD
0x180005c90  mov     edx, [rcx]
0x180005c92  test    dx, dx
0x180005c95  jnz     short loc_180005CAD
0x180005c97  lea     ecx, [rdx+10000h]
0x180005c9d  mov     eax, edx
0x180005c9f  or      ecx, 0FFFFh
0x180005ca5  lock cmpxchg [rbx], ecx
0x180005ca9  cmp     edx, eax
0x180005cab  jz      short loc_180005CD3
0x180005cad  call    cs:__imp_GetCurrentThreadId
0x180005cb4  nop     dword ptr [rax+rax+00h]
0x180005cb9  mov     ecx, [rbx+4]
0x180005cbc  and     eax, 0FFFFFFFCh
0x180005cbf  and     ecx, 0FFFFFFFCh
0x180005cc2  cmp     ecx, eax
0x180005cc4  jz      short loc_180005CEF
0x180005cc6  mov     rcx, rbx; this
0x180005cc9  add     rsp, 20h
0x180005ccd  pop     rbx
0x180005cce  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180005cd3  call    cs:__imp_GetCurrentThreadId
0x180005cda  nop     dword ptr [rax+rax+00h]
0x180005cdf  and     eax, 0FFFFFFFCh
0x180005ce2  or      eax, 1
0x180005ce5  xchg    eax, [rbx+4]
0x180005ce8  add     rsp, 20h
0x180005cec  pop     rbx
0x180005ced  retn
0x180005cef  lock inc dword ptr [rbx+4]
0x180005cf3  add     rsp, 20h
0x180005cf7  pop     rbx
0x180005cf8  retn
```
