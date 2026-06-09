# IPM_MESSAGE_PIPE::DecrementAcceptorInUse(void)

- ea: `0x18000d970`
- end: `0x18000daf9`
- name: `?DecrementAcceptorInUse@IPM_MESSAGE_PIPE@@AEAAXXZ`
- size: `393`
- prototype: `void __fastcall(IPM_MESSAGE_PIPE *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007180`
- `0x18000d970`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d9ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dabf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dad3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d9ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dabf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dad3`

## pseudocode

```c
void __fastcall IPM_MESSAGE_PIPE::DecrementAcceptorInUse(IPM_MESSAGE_PIPE *this)
{
  __int64 v1; // rsi
  signed __int32 v3; // edx
  signed __int32 v4; // edx
  signed __int32 v5; // edx
  signed __int32 v6; // edx

  v1 = 0;
  if ( *((_DWORD *)this + 3)
    || (v3 = *((_DWORD *)this + 2), (_WORD)v3)
    || v3 != _InterlockedCompareExchange((volatile signed __int32 *)this + 2, (v3 + 0x10000) | 0xFFFF, v3) )
  {
    if ( (*((_DWORD *)this + 3) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedIncrement((volatile signed __int32 *)this + 3);
    else
      CReaderWriterLock3::_WriteLockSpin((IPM_MESSAGE_PIPE *)((char *)this + 8));
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 3, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
  if ( *((_DWORD *)this + 15) == 1 && *((int *)this + 14) < 0 )
  {
    v1 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = 0;
  }
  if ( ((*((_BYTE *)this + 12) - 1) & 3) != 0 )
  {
    _InterlockedExchange((volatile __int32 *)this + 3, *((_DWORD *)this + 3) - 1);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 3, 0);
    while ( 1 )
    {
      v5 = *((_DWORD *)this + 2);
      if ( v5 == _InterlockedCompareExchange((volatile signed __int32 *)this + 2, (v5 - 0x10000) & 0xFFFF0000, v5) )
        break;
      _mm_pause();
    }
  }
  if ( v1 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v1 + 16LL))(v1, *((unsigned int *)this + 14));
  if ( *((_DWORD *)this + 3)
    || (v4 = *((_DWORD *)this + 2), (_WORD)v4)
    || v4 != _InterlockedCompareExchange((volatile signed __int32 *)this + 2, (v4 + 0x10000) | 0xFFFF, v4) )
  {
    if ( (*((_DWORD *)this + 3) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedIncrement((volatile signed __int32 *)this + 3);
    else
      CReaderWriterLock3::_WriteLockSpin((IPM_MESSAGE_PIPE *)((char *)this + 8));
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 3, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
  --*((_DWORD *)this + 15);
  if ( ((*((_BYTE *)this + 12) - 1) & 3) != 0 )
  {
    _InterlockedExchange((volatile __int32 *)this + 3, *((_DWORD *)this + 3) - 1);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 3, 0);
    while ( 1 )
    {
      v6 = *((_DWORD *)this + 2);
      if ( v6 == _InterlockedCompareExchange((volatile signed __int32 *)this + 2, (v6 - 0x10000) & 0xFFFF0000, v6) )
        break;
      _mm_pause();
    }
  }
}

```

## disassembly

```asm
0x18000d970  mov     [rsp+arg_0], rbx
0x18000d975  mov     [rsp+arg_8], rsi
0x18000d97a  push    rdi
0x18000d97b  sub     rsp, 20h
0x18000d97f  mov     eax, [rcx+0Ch]
0x18000d982  xor     esi, esi
0x18000d984  mov     rbx, rcx
0x18000d987  test    eax, eax
0x18000d989  jnz     short loc_18000D9AE
0x18000d98b  mov     edx, [rcx+8]
0x18000d98e  test    dx, dx
0x18000d991  jnz     short loc_18000D9AE
0x18000d993  lea     ecx, [rdx+10000h]
0x18000d999  mov     eax, edx
0x18000d99b  or      ecx, 0FFFFh
0x18000d9a1  lock cmpxchg [rbx+8], ecx
0x18000d9a6  cmp     edx, eax
0x18000d9a8  jz      loc_18000DABF
0x18000d9ae  call    cs:__imp_GetCurrentThreadId
0x18000d9b4  mov     ecx, [rbx+0Ch]
0x18000d9b7  and     eax, 0FFFFFFFCh
0x18000d9ba  and     ecx, 0FFFFFFFCh
0x18000d9bd  cmp     ecx, eax
0x18000d9bf  jz      loc_18000DAE7
0x18000d9c5  lea     rcx, [rbx+8]; this
0x18000d9c9  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000d9ce  cmp     dword ptr [rbx+3Ch], 1
0x18000d9d2  jnz     short loc_18000D9E5
0x18000d9d4  cmp     [rbx+38h], esi
0x18000d9d7  jge     short loc_18000D9E5
0x18000d9d9  mov     rsi, [rbx+18h]
0x18000d9dd  mov     qword ptr [rbx+18h], 0
0x18000d9e5  mov     eax, [rbx+0Ch]
0x18000d9e8  dec     eax
0x18000d9ea  test    al, 3
0x18000d9ec  jz      loc_18000DA75
0x18000d9f2  xchg    eax, [rbx+0Ch]
0x18000d9f5  test    rsi, rsi
0x18000d9f8  jz      short loc_18000DA0C
0x18000d9fa  mov     rax, [rsi]
0x18000d9fd  mov     rcx, rsi
0x18000da00  mov     edx, [rbx+38h]
0x18000da03  mov     rax, [rax+10h]
0x18000da07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da0c  mov     eax, [rbx+0Ch]
0x18000da0f  test    eax, eax
0x18000da11  jnz     short loc_18000DA36
0x18000da13  mov     edx, [rbx+8]
0x18000da16  test    dx, dx
0x18000da19  jnz     short loc_18000DA36
0x18000da1b  lea     ecx, [rdx+10000h]
0x18000da21  mov     eax, edx
0x18000da23  or      ecx, 0FFFFh
0x18000da29  lock cmpxchg [rbx+8], ecx
0x18000da2e  cmp     edx, eax
0x18000da30  jz      loc_18000DAD3
0x18000da36  call    cs:__imp_GetCurrentThreadId
0x18000da3c  mov     ecx, [rbx+0Ch]
0x18000da3f  and     eax, 0FFFFFFFCh
0x18000da42  and     ecx, 0FFFFFFFCh
0x18000da45  cmp     ecx, eax
0x18000da47  jz      loc_18000DAF0
0x18000da4d  lea     rcx, [rbx+8]; this
0x18000da51  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000da56  dec     dword ptr [rbx+3Ch]
0x18000da59  mov     eax, [rbx+0Ch]
0x18000da5c  dec     eax
0x18000da5e  test    al, 3
0x18000da60  jz      short loc_18000DA9C
0x18000da62  xchg    eax, [rbx+0Ch]
0x18000da65  mov     rbx, [rsp+28h+arg_0]
0x18000da6a  mov     rsi, [rsp+28h+arg_8]
0x18000da6f  add     rsp, 20h
0x18000da73  pop     rdi
0x18000da74  retn
0x18000da75  xor     eax, eax
0x18000da77  xchg    eax, [rbx+0Ch]
0x18000da7a  mov     edx, [rbx+8]
0x18000da7d  mov     eax, edx
0x18000da7f  lea     ecx, [rdx-10000h]
0x18000da85  and     ecx, 0FFFF0000h
0x18000da8b  lock cmpxchg [rbx+8], ecx
0x18000da90  cmp     edx, eax
0x18000da92  jz      loc_18000D9F5
0x18000da98  pause
0x18000da9a  jmp     short loc_18000DA7A
0x18000da9c  xor     eax, eax
0x18000da9e  xchg    eax, [rbx+0Ch]
0x18000daa1  mov     edx, [rbx+8]
0x18000daa4  mov     eax, edx
0x18000daa6  lea     ecx, [rdx-10000h]
0x18000daac  and     ecx, 0FFFF0000h
0x18000dab2  lock cmpxchg [rbx+8], ecx
0x18000dab7  cmp     edx, eax
0x18000dab9  jz      short loc_18000DA65
0x18000dabb  pause
0x18000dabd  jmp     short loc_18000DAA1
0x18000dabf  call    cs:__imp_GetCurrentThreadId
0x18000dac5  and     eax, 0FFFFFFFCh
0x18000dac8  or      eax, 1
0x18000dacb  xchg    eax, [rbx+0Ch]
0x18000dace  jmp     loc_18000D9CE
0x18000dad3  call    cs:__imp_GetCurrentThreadId
0x18000dad9  and     eax, 0FFFFFFFCh
0x18000dadc  or      eax, 1
0x18000dadf  xchg    eax, [rbx+0Ch]
0x18000dae2  jmp     loc_18000DA56
0x18000dae7  lock inc dword ptr [rbx+0Ch]
0x18000daeb  jmp     loc_18000D9CE
0x18000daf0  lock inc dword ptr [rbx+0Ch]
0x18000daf4  jmp     loc_18000DA56
```
