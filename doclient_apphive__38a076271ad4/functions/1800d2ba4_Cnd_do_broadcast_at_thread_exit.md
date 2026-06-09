# _Cnd_do_broadcast_at_thread_exit

- ea: `0x1800d2ba4`
- end: `0x1800d2ccb`
- name: `_Cnd_do_broadcast_at_thread_exit`
- size: `295`
- prototype: `void __cdecl()`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180048150`
- `0x180052410`
- `0x1800a4990`
- `0x1800be670`
- `0x1800beb10`
- `0x1800ede80`

## callees

- `0x1800199b4`
- `0x180019c5c`
- `0x1800d2ba4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d2bbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d2bbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d2c31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d2c8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d2c31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d2c8f`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800d2c3f`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800d2c3f`

## pseudocode

```c
void __cdecl Cnd_do_broadcast_at_thread_exit()
{
  __int64 *v0; // rbx
  DWORD CurrentThreadId; // ebp
  __int64 v2; // rsi
  int v3; // eax
  _QWORD *v4; // rdi
  int v5; // ecx
  _DWORD *v6; // rax
  __int64 v7; // rcx

  v0 = qword_180195720;
  CurrentThreadId = GetCurrentThreadId();
  if ( (unsigned int)mtx_do_lock(qword_18017E290) )
    std::_Throw_Cpp_error(5);
  if ( dword_18017E2DC == 0x7FFFFFFF )
  {
    dword_18017E2DC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  do
  {
    v2 = 0;
    v3 = *((_DWORD *)v0 + 200);
    if ( v3 )
    {
      v4 = v0 + 2;
      do
      {
        if ( v2 >= 20 )
          break;
        v5 = v3;
        if ( *v4 && *((_DWORD *)v4 - 2) == CurrentThreadId )
        {
          v6 = (_DWORD *)v4[2];
          if ( v6 )
            *v6 = 1;
          v7 = *v4;
          if ( (*(_DWORD *)(*v4 + 76LL))-- == 1 )
          {
            *(_DWORD *)(v7 + 72) = -1;
            ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 16));
          }
          WakeAllConditionVariable((PCONDITION_VARIABLE)(v4[1] + 8LL));
          *v4 = 0;
          v5 = --*((_DWORD *)v0 + 200);
        }
        ++v2;
        v4 += 5;
        v3 = v5;
      }
      while ( v5 );
    }
    v0 = (__int64 *)v0[101];
  }
  while ( v0 );
  if ( !--dword_18017E2DC )
  {
    dword_18017E2D8 = -1;
    ReleaseSRWLockExclusive(&stru_18017E2A0);
  }
}

```

## disassembly

```asm
0x1800d2ba4  mov     [rsp+arg_8], rbx
0x1800d2ba9  mov     [rsp+arg_10], rbp
0x1800d2bae  mov     [rsp+arg_18], rsi
0x1800d2bb3  push    rdi
0x1800d2bb4  sub     rsp, 20h
0x1800d2bb8  lea     rbx, qword_180195720
0x1800d2bbf  call    cs:__imp_GetCurrentThreadId
0x1800d2bc5  mov     ebp, eax
0x1800d2bc7  lea     rcx, qword_18017E290
0x1800d2bce  call    mtx_do_lock
0x1800d2bd3  test    eax, eax
0x1800d2bd5  jnz     loc_1800D2CC0
0x1800d2bdb  cmp     cs:dword_18017E2DC, 7FFFFFFFh
0x1800d2be5  jz      loc_1800D2CAB
0x1800d2beb  xor     esi, esi
0x1800d2bed  mov     eax, [rbx+320h]
0x1800d2bf3  test    eax, eax
0x1800d2bf5  jz      short loc_1800D2C65
0x1800d2bf7  lea     rdi, [rbx+10h]
0x1800d2bfb  cmp     rsi, 14h
0x1800d2bff  jge     short loc_1800D2C65
0x1800d2c01  mov     ecx, eax
0x1800d2c03  cmp     qword ptr [rdi], 0
0x1800d2c07  jz      short loc_1800D2C58
0x1800d2c09  cmp     [rdi-8], ebp
0x1800d2c0c  jnz     short loc_1800D2C58
0x1800d2c0e  mov     rax, [rdi+10h]
0x1800d2c12  test    rax, rax
0x1800d2c15  jz      short loc_1800D2C1D
0x1800d2c17  mov     dword ptr [rax], 1
0x1800d2c1d  mov     rcx, [rdi]
0x1800d2c20  sub     dword ptr [rcx+4Ch], 1
0x1800d2c24  jnz     short loc_1800D2C37
0x1800d2c26  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x1800d2c2d  add     rcx, 10h; SRWLock
0x1800d2c31  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d2c37  mov     rcx, [rdi+8]
0x1800d2c3b  add     rcx, 8; ConditionVariable
0x1800d2c3f  call    cs:__imp_WakeAllConditionVariable
0x1800d2c45  mov     qword ptr [rdi], 0
0x1800d2c4c  dec     dword ptr [rbx+320h]
0x1800d2c52  mov     ecx, [rbx+320h]
0x1800d2c58  inc     rsi
0x1800d2c5b  add     rdi, 28h ; '('
0x1800d2c5f  mov     eax, ecx
0x1800d2c61  test    ecx, ecx
0x1800d2c63  jnz     short loc_1800D2BFB
0x1800d2c65  mov     rbx, [rbx+328h]
0x1800d2c6c  test    rbx, rbx
0x1800d2c6f  jnz     loc_1800D2BEB
0x1800d2c75  sub     cs:dword_18017E2DC, 1
0x1800d2c7c  jnz     short loc_1800D2C96
0x1800d2c7e  mov     cs:dword_18017E2D8, 0FFFFFFFFh
0x1800d2c88  lea     rcx, stru_18017E2A0; SRWLock
0x1800d2c8f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d2c95  nop
0x1800d2c96  mov     rbx, [rsp+28h+arg_8]
0x1800d2c9b  mov     rbp, [rsp+28h+arg_10]
0x1800d2ca0  mov     rsi, [rsp+28h+arg_18]
0x1800d2ca5  add     rsp, 20h
0x1800d2ca9  pop     rdi
0x1800d2caa  retn
0x1800d2cab  mov     cs:dword_18017E2DC, 7FFFFFFEh
0x1800d2cb5  mov     ecx, 6; int
0x1800d2cba  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800d2cc0  mov     ecx, 5; int
0x1800d2cc5  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
