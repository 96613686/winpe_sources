# IPM_MESSAGE_PIPE::NotifyPipeDisconnected(long)

- ea: `0x1800086e0`
- end: `0x1800087c8`
- name: `?NotifyPipeDisconnected@IPM_MESSAGE_PIPE@@AEAAXJ@Z`
- size: `232`
- prototype: `void __fastcall(IPM_MESSAGE_PIPE *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180026d10`

## callees

- `0x180007180`
- `0x1800086e0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000871a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800087ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000871a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800087ab`

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
0x1800086e0  push    rbx
0x1800086e2  push    rbp
0x1800086e3  push    rsi
0x1800086e4  push    rdi
0x1800086e5  sub     rsp, 28h
0x1800086e9  mov     eax, [rcx+0Ch]
0x1800086ec  xor     edi, edi
0x1800086ee  mov     ebp, edx
0x1800086f0  mov     rbx, rcx
0x1800086f3  test    eax, eax
0x1800086f5  jnz     short loc_18000871A
0x1800086f7  mov     edx, [rcx+8]
0x1800086fa  test    dx, dx
0x1800086fd  jnz     short loc_18000871A
0x1800086ff  lea     ecx, [rdx+10000h]
0x180008705  mov     eax, edx
0x180008707  or      ecx, 0FFFFh
0x18000870d  lock cmpxchg [rbx+8], ecx
0x180008712  cmp     edx, eax
0x180008714  jz      loc_1800087AB
0x18000871a  call    cs:__imp_GetCurrentThreadId
0x180008720  mov     ecx, [rbx+0Ch]
0x180008723  and     eax, 0FFFFFFFCh
0x180008726  and     ecx, 0FFFFFFFCh
0x180008729  cmp     ecx, eax
0x18000872b  jz      loc_1800087BF
0x180008731  lea     rcx, [rbx+8]; this
0x180008735  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000873a  cmp     [rbx+3Ch], edi
0x18000873d  jnz     short loc_18000877E
0x18000873f  mov     rax, [rbx+18h]
0x180008743  test    rax, rax
0x180008746  jz      short loc_180008753
0x180008748  mov     rdi, rax
0x18000874b  mov     qword ptr [rbx+18h], 0
0x180008753  mov     eax, [rbx+0Ch]
0x180008756  dec     eax
0x180008758  test    al, 3
0x18000875a  jz      short loc_180008788
0x18000875c  xchg    eax, [rbx+0Ch]
0x18000875f  test    rdi, rdi
0x180008762  jz      short loc_180008775
0x180008764  mov     rax, [rdi]
0x180008767  mov     edx, ebp
0x180008769  mov     rcx, rdi
0x18000876c  mov     rax, [rax+10h]
0x180008770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008775  add     rsp, 28h
0x180008779  pop     rdi
0x18000877a  pop     rsi
0x18000877b  pop     rbp
0x18000877c  pop     rbx
0x18000877d  retn
0x18000877e  cmp     [rbx+38h], edi
0x180008781  jl      short loc_180008753
0x180008783  mov     [rbx+38h], ebp
0x180008786  jmp     short loc_180008753
0x180008788  xor     eax, eax
0x18000878a  xchg    eax, [rbx+0Ch]
0x18000878d  mov     edx, [rbx+8]
0x180008790  mov     eax, edx
0x180008792  lea     ecx, [rdx-10000h]
0x180008798  and     ecx, 0FFFF0000h
0x18000879e  lock cmpxchg [rbx+8], ecx
0x1800087a3  cmp     edx, eax
0x1800087a5  jz      short loc_18000875F
0x1800087a7  pause
0x1800087a9  jmp     short loc_18000878D
0x1800087ab  call    cs:__imp_GetCurrentThreadId
0x1800087b1  and     eax, 0FFFFFFFCh
0x1800087b4  or      eax, 1
0x1800087b7  xchg    eax, [rbx+0Ch]
0x1800087ba  jmp     loc_18000873A
0x1800087bf  lock inc dword ptr [rbx+0Ch]
0x1800087c3  jmp     loc_18000873A
```
