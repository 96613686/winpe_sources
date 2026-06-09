# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x180025e38`
- end: `0x180025fca`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `402`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023340`

## callees

- `0x180002b74`
- `0x180022994`
- `0x180025e38`
- `0x180049010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180025f4f`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180025f4f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180025e6f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180025e91`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180025e6f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180025e91`
- `msvcp_win!_Mtx_lock` at `0x180025e5a`
- `msvcp_win!_Mtx_lock` at `0x180025e5a`
- `msvcp_win!_Cnd_wait` at `0x180025f88`
- `msvcp_win!_Cnd_wait` at `0x180025f88`
- `msvcp_win!_Mtx_unlock` at `0x180025f19`
- `msvcp_win!_Mtx_unlock` at `0x180025fa9`
- `msvcp_win!_Mtx_unlock` at `0x180025f19`
- `msvcp_win!_Mtx_unlock` at `0x180025fa9`

## pseudocode

```c
void __fastcall Concurrency::details::_CancellationTokenState::_DeregisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  char *v4; // rbx
  _QWORD *v5; // rcx
  char v6; // r14
  _QWORD *v7; // rax
  __int64 v8; // rdx
  Concurrency::details::platform *v9; // rcx
  unsigned __int32 v10; // eax
  _Mtx_t v11[2]; // [rsp+20h] [rbp-48h] BYREF

  v4 = (char *)this + 24;
  v11[0] = (Concurrency::details::_CancellationTokenState *)((char *)this + 24);
  if ( _Mtx_lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v4 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v5 = (_QWORD *)*((_QWORD *)this + 13);
  if ( v5 )
  {
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      v8 = v5[1];
      if ( (struct Concurrency::details::_CancellationTokenRegistration *)*v5 == a2 )
        break;
      v7 = v5;
      v5 = (_QWORD *)v5[1];
      if ( !v8 )
        goto LABEL_17;
    }
    if ( v7 )
      v7[1] = v8;
    else
      *((_QWORD *)this + 13) = v8;
    if ( !v5[1] )
      *((_QWORD *)this + 14) = v7;
    operator delete(v5);
LABEL_17:
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  else
  {
    v6 = 1;
  }
  _Mtx_unlock((_Mtx_t)v4);
  if ( v6 )
  {
    v10 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    if ( v10 >= 2
      && v10 - 2 >= 2
      && v10 != Concurrency::details::platform::GetCurrentThreadId(v9)
      && _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
    {
      *(_OWORD *)v11 = 0;
      std::unique_lock<std::mutex>::unique_lock<std::mutex>(v11, (char *)a2 + 96);
      while ( !*((_BYTE *)a2 + 176) )
        _Cnd_wait((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24), v11[0]);
      if ( LOBYTE(v11[1]) )
        _Mtx_unlock(v11[0]);
    }
  }
}

```

## disassembly

```asm
0x180025e38  mov     [rsp+arg_10], rbx
0x180025e3d  push    rbp
0x180025e3e  push    rsi
0x180025e3f  push    rdi
0x180025e40  push    r12
0x180025e42  push    r14
0x180025e44  sub     rsp, 40h
0x180025e48  mov     rdi, rdx
0x180025e4b  mov     rsi, rcx
0x180025e4e  lea     rbx, [rcx+18h]
0x180025e52  mov     [rsp+68h+var_48], rbx
0x180025e57  mov     rcx, rbx; _Mtx_t
0x180025e5a  call    cs:__imp__Mtx_lock
0x180025e61  nop     dword ptr [rax+rax+00h]
0x180025e66  test    eax, eax
0x180025e68  jz      short loc_180025E7C
0x180025e6a  mov     ecx, 5
0x180025e6f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180025e76  nop     dword ptr [rax+rax+00h]
0x180025e7b  int     3; Trap to Debugger
0x180025e7c  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180025e83  jnz     short loc_180025E9E
0x180025e85  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180025e8c  mov     ecx, 6
0x180025e91  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180025e98  nop     dword ptr [rax+rax+00h]
0x180025e9d  nop
0x180025e9e  mov     rcx, [rsi+68h]; void *
0x180025ea2  mov     ebp, 2
0x180025ea7  lea     r12d, [rbp-1]
0x180025eab  test    rcx, rcx
0x180025eae  jnz     short loc_180025EB5
0x180025eb0  mov     r14b, r12b
0x180025eb3  jmp     short loc_180025F16
0x180025eb5  xor     r14b, r14b
0x180025eb8  xor     eax, eax
0x180025eba  mov     rdx, [rcx+8]
0x180025ebe  cmp     [rcx], rdi
0x180025ec1  jz      short loc_180025ED0
0x180025ec3  mov     rax, rcx
0x180025ec6  mov     rcx, rdx
0x180025ec9  test    rdx, rdx
0x180025ecc  jnz     short loc_180025EBA
0x180025ece  jmp     short loc_180025EF4
0x180025ed0  test    rax, rax
0x180025ed3  jnz     short loc_180025EDB
0x180025ed5  mov     [rsi+68h], rdx
0x180025ed9  jmp     short loc_180025EDF
0x180025edb  mov     [rax+8], rdx
0x180025edf  cmp     qword ptr [rcx+8], 0
0x180025ee4  jnz     short loc_180025EEA
0x180025ee6  mov     [rsi+70h], rax
0x180025eea  mov     edx, 10h; unsigned __int64
0x180025eef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025ef4  mov     eax, ebp
0x180025ef6  xchg    eax, [rdi+10h]
0x180025ef9  or      eax, 0FFFFFFFFh
0x180025efc  lock xadd [rdi+8], eax
0x180025f01  cmp     eax, r12d
0x180025f04  jnz     short loc_180025F16
0x180025f06  mov     rax, [rdi]
0x180025f09  mov     rcx, rdi
0x180025f0c  mov     rax, [rax+8]
0x180025f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f15  nop
0x180025f16  mov     rcx, rbx; _Mtx_t
0x180025f19  call    cs:__imp__Mtx_unlock
0x180025f20  nop     dword ptr [rax+rax+00h]
0x180025f25  test    r14b, r14b
0x180025f28  jz      loc_180025FB5
0x180025f2e  xor     eax, eax
0x180025f30  lock cmpxchg [rdi+10h], r12d
0x180025f36  mov     ebx, eax
0x180025f38  jz      short loc_180025FB5
0x180025f3a  mov     edx, eax
0x180025f3c  test    eax, eax
0x180025f3e  jz      short loc_180025FB5
0x180025f40  sub     edx, 1
0x180025f43  jz      short loc_180025FB5
0x180025f45  sub     edx, 1
0x180025f48  jz      short loc_180025FB5
0x180025f4a  cmp     edx, 1
0x180025f4d  jz      short loc_180025FB5
0x180025f4f  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180025f56  nop     dword ptr [rax+rax+00h]
0x180025f5b  cmp     ebx, eax
0x180025f5d  jz      short loc_180025FB5
0x180025f5f  xchg    ebp, [rdi+10h]
0x180025f62  cmp     ebp, 3
0x180025f65  jz      short loc_180025FB5
0x180025f67  xorps   xmm0, xmm0
0x180025f6a  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x180025f6f  lea     rdx, [rdi+60h]
0x180025f73  lea     rcx, [rsp+68h+var_48]
0x180025f78  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180025f7d  jmp     short loc_180025F94
0x180025f7f  mov     rdx, [rsp+68h+var_48]; _Mtx_t
0x180025f84  lea     rcx, [rdi+18h]; _Cnd_t
0x180025f88  call    cs:__imp__Cnd_wait
0x180025f8f  nop     dword ptr [rax+rax+00h]
0x180025f94  cmp     byte ptr [rdi+0B0h], 0
0x180025f9b  jz      short loc_180025F7F
0x180025f9d  cmp     byte ptr [rsp+68h+var_48+8], 0
0x180025fa2  jz      short loc_180025FB5
0x180025fa4  mov     rcx, [rsp+68h+var_48]; _Mtx_t
0x180025fa9  call    cs:__imp__Mtx_unlock
0x180025fb0  nop     dword ptr [rax+rax+00h]
0x180025fb5  mov     rbx, [rsp+68h+arg_10]
0x180025fbd  add     rsp, 40h
0x180025fc1  pop     r14
0x180025fc3  pop     r12
0x180025fc5  pop     rdi
0x180025fc6  pop     rsi
0x180025fc7  pop     rbp
0x180025fc8  retn
```
