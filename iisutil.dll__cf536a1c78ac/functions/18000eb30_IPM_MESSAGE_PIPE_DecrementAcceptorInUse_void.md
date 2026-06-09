# IPM_MESSAGE_PIPE::DecrementAcceptorInUse(void)

- ea: `0x18000eb30`
- end: `0x18000ecd2`
- name: `?DecrementAcceptorInUse@IPM_MESSAGE_PIPE@@AEAAXXZ`
- size: `418`
- prototype: `void __fastcall(IPM_MESSAGE_PIPE *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007e60`
- `0x18000eb30`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eb6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ebfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ec8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eca6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eb6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ebfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ec8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eca6`

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
0x18000eb30  mov     [rsp+arg_0], rbx
0x18000eb35  mov     [rsp+arg_8], rsi
0x18000eb3a  push    rdi
0x18000eb3b  sub     rsp, 20h
0x18000eb3f  mov     eax, [rcx+0Ch]
0x18000eb42  xor     esi, esi
0x18000eb44  mov     rbx, rcx
0x18000eb47  test    eax, eax
0x18000eb49  jnz     short loc_18000EB6E
0x18000eb4b  mov     edx, [rcx+8]
0x18000eb4e  test    dx, dx
0x18000eb51  jnz     short loc_18000EB6E
0x18000eb53  lea     ecx, [rdx+10000h]
0x18000eb59  mov     eax, edx
0x18000eb5b  or      ecx, 0FFFFh
0x18000eb61  lock cmpxchg [rbx+8], ecx
0x18000eb66  cmp     edx, eax
0x18000eb68  jz      loc_18000EC8C
0x18000eb6e  call    cs:__imp_GetCurrentThreadId
0x18000eb75  nop     dword ptr [rax+rax+00h]
0x18000eb7a  mov     ecx, [rbx+0Ch]
0x18000eb7d  and     eax, 0FFFFFFFCh
0x18000eb80  and     ecx, 0FFFFFFFCh
0x18000eb83  cmp     ecx, eax
0x18000eb85  jz      loc_18000ECC0
0x18000eb8b  lea     rcx, [rbx+8]; this
0x18000eb8f  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000eb94  cmp     dword ptr [rbx+3Ch], 1
0x18000eb98  jnz     short loc_18000EBAB
0x18000eb9a  cmp     [rbx+38h], esi
0x18000eb9d  jge     short loc_18000EBAB
0x18000eb9f  mov     rsi, [rbx+18h]
0x18000eba3  mov     qword ptr [rbx+18h], 0
0x18000ebab  mov     eax, [rbx+0Ch]
0x18000ebae  dec     eax
0x18000ebb0  test    al, 3
0x18000ebb2  jz      loc_18000EC42
0x18000ebb8  xchg    eax, [rbx+0Ch]
0x18000ebbb  test    rsi, rsi
0x18000ebbe  jz      short loc_18000EBD2
0x18000ebc0  mov     rax, [rsi]
0x18000ebc3  mov     rcx, rsi
0x18000ebc6  mov     edx, [rbx+38h]
0x18000ebc9  mov     rax, [rax+10h]
0x18000ebcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebd2  mov     eax, [rbx+0Ch]
0x18000ebd5  test    eax, eax
0x18000ebd7  jnz     short loc_18000EBFC
0x18000ebd9  mov     edx, [rbx+8]
0x18000ebdc  test    dx, dx
0x18000ebdf  jnz     short loc_18000EBFC
0x18000ebe1  lea     ecx, [rdx+10000h]
0x18000ebe7  mov     eax, edx
0x18000ebe9  or      ecx, 0FFFFh
0x18000ebef  lock cmpxchg [rbx+8], ecx
0x18000ebf4  cmp     edx, eax
0x18000ebf6  jz      loc_18000ECA6
0x18000ebfc  call    cs:__imp_GetCurrentThreadId
0x18000ec03  nop     dword ptr [rax+rax+00h]
0x18000ec08  mov     ecx, [rbx+0Ch]
0x18000ec0b  and     eax, 0FFFFFFFCh
0x18000ec0e  and     ecx, 0FFFFFFFCh
0x18000ec11  cmp     ecx, eax
0x18000ec13  jz      loc_18000ECC9
0x18000ec19  lea     rcx, [rbx+8]; this
0x18000ec1d  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000ec22  dec     dword ptr [rbx+3Ch]
0x18000ec25  mov     eax, [rbx+0Ch]
0x18000ec28  dec     eax
0x18000ec2a  test    al, 3
0x18000ec2c  jz      short loc_18000EC69
0x18000ec2e  xchg    eax, [rbx+0Ch]
0x18000ec31  mov     rbx, [rsp+28h+arg_0]
0x18000ec36  mov     rsi, [rsp+28h+arg_8]
0x18000ec3b  add     rsp, 20h
0x18000ec3f  pop     rdi
0x18000ec40  retn
0x18000ec42  xor     eax, eax
0x18000ec44  xchg    eax, [rbx+0Ch]
0x18000ec47  mov     edx, [rbx+8]
0x18000ec4a  mov     eax, edx
0x18000ec4c  lea     ecx, [rdx-10000h]
0x18000ec52  and     ecx, 0FFFF0000h
0x18000ec58  lock cmpxchg [rbx+8], ecx
0x18000ec5d  cmp     edx, eax
0x18000ec5f  jz      loc_18000EBBB
0x18000ec65  pause
0x18000ec67  jmp     short loc_18000EC47
0x18000ec69  xor     eax, eax
0x18000ec6b  xchg    eax, [rbx+0Ch]
0x18000ec6e  mov     edx, [rbx+8]
0x18000ec71  mov     eax, edx
0x18000ec73  lea     ecx, [rdx-10000h]
0x18000ec79  and     ecx, 0FFFF0000h
0x18000ec7f  lock cmpxchg [rbx+8], ecx
0x18000ec84  cmp     edx, eax
0x18000ec86  jz      short loc_18000EC31
0x18000ec88  pause
0x18000ec8a  jmp     short loc_18000EC6E
0x18000ec8c  call    cs:__imp_GetCurrentThreadId
0x18000ec93  nop     dword ptr [rax+rax+00h]
0x18000ec98  and     eax, 0FFFFFFFCh
0x18000ec9b  or      eax, 1
0x18000ec9e  xchg    eax, [rbx+0Ch]
0x18000eca1  jmp     loc_18000EB94
0x18000eca6  call    cs:__imp_GetCurrentThreadId
0x18000ecad  nop     dword ptr [rax+rax+00h]
0x18000ecb2  and     eax, 0FFFFFFFCh
0x18000ecb5  or      eax, 1
0x18000ecb8  xchg    eax, [rbx+0Ch]
0x18000ecbb  jmp     loc_18000EC22
0x18000ecc0  lock inc dword ptr [rbx+0Ch]
0x18000ecc4  jmp     loc_18000EB94
0x18000ecc9  lock inc dword ptr [rbx+0Ch]
0x18000eccd  jmp     loc_18000EC22
```
