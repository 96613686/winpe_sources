# IPM_MESSAGE_PIPE::NotifyPipeDisconnected(long)

- ea: `0x180009420`
- end: `0x180009515`
- name: `?NotifyPipeDisconnected@IPM_MESSAGE_PIPE@@AEAAXJ@Z`
- size: `245`
- prototype: `void __fastcall(IPM_MESSAGE_PIPE *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180028950`

## callees

- `0x180007e60`
- `0x180009420`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000945a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800094f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000945a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800094f2`

## pseudocode

```c
void __fastcall IPM_MESSAGE_PIPE::NotifyPipeDisconnected(IPM_MESSAGE_PIPE *this, unsigned int a2)
{
  __int64 v2; // rdi
  signed __int32 v5; // edx
  signed __int32 v6; // edx

  v2 = 0;
  if ( *((_DWORD *)this + 3)
    || (v5 = *((_DWORD *)this + 2), (_WORD)v5)
    || v5 != _InterlockedCompareExchange((volatile signed __int32 *)this + 2, (v5 + 0x10000) | 0xFFFF, v5) )
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
  if ( *((_DWORD *)this + 15) )
  {
    if ( *((int *)this + 14) >= 0 )
      *((_DWORD *)this + 14) = a2;
  }
  else if ( *((_QWORD *)this + 3) )
  {
    v2 = *((_QWORD *)this + 3);
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
      v6 = *((_DWORD *)this + 2);
      if ( v6 == _InterlockedCompareExchange((volatile signed __int32 *)this + 2, (v6 - 0x10000) & 0xFFFF0000, v6) )
        break;
      _mm_pause();
    }
  }
  if ( v2 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 16LL))(v2, a2);
}

```

## disassembly

```asm
0x180009420  push    rbx
0x180009422  push    rbp
0x180009423  push    rsi
0x180009424  push    rdi
0x180009425  sub     rsp, 28h
0x180009429  mov     eax, [rcx+0Ch]
0x18000942c  xor     edi, edi
0x18000942e  mov     ebp, edx
0x180009430  mov     rbx, rcx
0x180009433  test    eax, eax
0x180009435  jnz     short loc_18000945A
0x180009437  mov     edx, [rcx+8]
0x18000943a  test    dx, dx
0x18000943d  jnz     short loc_18000945A
0x18000943f  lea     ecx, [rdx+10000h]
0x180009445  mov     eax, edx
0x180009447  or      ecx, 0FFFFh
0x18000944d  lock cmpxchg [rbx+8], ecx
0x180009452  cmp     edx, eax
0x180009454  jz      loc_1800094F2
0x18000945a  call    cs:__imp_GetCurrentThreadId
0x180009461  nop     dword ptr [rax+rax+00h]
0x180009466  mov     ecx, [rbx+0Ch]
0x180009469  and     eax, 0FFFFFFFCh
0x18000946c  and     ecx, 0FFFFFFFCh
0x18000946f  cmp     ecx, eax
0x180009471  jz      loc_18000950C
0x180009477  lea     rcx, [rbx+8]; this
0x18000947b  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180009480  cmp     [rbx+3Ch], edi
0x180009483  jnz     short loc_1800094C5
0x180009485  mov     rax, [rbx+18h]
0x180009489  test    rax, rax
0x18000948c  jz      short loc_180009499
0x18000948e  mov     rdi, rax
0x180009491  mov     qword ptr [rbx+18h], 0
0x180009499  mov     eax, [rbx+0Ch]
0x18000949c  dec     eax
0x18000949e  test    al, 3
0x1800094a0  jz      short loc_1800094CF
0x1800094a2  xchg    eax, [rbx+0Ch]
0x1800094a5  test    rdi, rdi
0x1800094a8  jz      short loc_1800094BB
0x1800094aa  mov     rax, [rdi]
0x1800094ad  mov     edx, ebp
0x1800094af  mov     rcx, rdi
0x1800094b2  mov     rax, [rax+10h]
0x1800094b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094bb  add     rsp, 28h
0x1800094bf  pop     rdi
0x1800094c0  pop     rsi
0x1800094c1  pop     rbp
0x1800094c2  pop     rbx
0x1800094c3  retn
0x1800094c5  cmp     [rbx+38h], edi
0x1800094c8  jl      short loc_180009499
0x1800094ca  mov     [rbx+38h], ebp
0x1800094cd  jmp     short loc_180009499
0x1800094cf  xor     eax, eax
0x1800094d1  xchg    eax, [rbx+0Ch]
0x1800094d4  mov     edx, [rbx+8]
0x1800094d7  mov     eax, edx
0x1800094d9  lea     ecx, [rdx-10000h]
0x1800094df  and     ecx, 0FFFF0000h
0x1800094e5  lock cmpxchg [rbx+8], ecx
0x1800094ea  cmp     edx, eax
0x1800094ec  jz      short loc_1800094A5
0x1800094ee  pause
0x1800094f0  jmp     short loc_1800094D4
0x1800094f2  call    cs:__imp_GetCurrentThreadId
0x1800094f9  nop     dword ptr [rax+rax+00h]
0x1800094fe  and     eax, 0FFFFFFFCh
0x180009501  or      eax, 1
0x180009504  xchg    eax, [rbx+0Ch]
0x180009507  jmp     loc_180009480
0x18000950c  lock inc dword ptr [rbx+0Ch]
0x180009510  jmp     loc_180009480
```
