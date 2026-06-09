# Concurrency::cancellation_token::deregister_callback(Concurrency::cancellation_token_registration const &)

- ea: `0x18004ef18`
- end: `0x18004f075`
- name: `?deregister_callback@cancellation_token@Concurrency@@QEBAXAEBVcancellation_token_registration@2@@Z`
- size: `349`
- prototype: `void __fastcall(Concurrency::cancellation_token *__hidden this, const struct Concurrency::cancellation_token_registration *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180045914`

## callees

- `0x180003520`
- `0x18004ef18`
- `0x180061010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18004effa`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18004effa`
- `msvcp_win!_Cnd_wait` at `0x18004f040`
- `msvcp_win!_Cnd_wait` at `0x18004f040`
- `msvcp_win!_Mtx_unlock` at `0x18004efce`
- `msvcp_win!_Mtx_unlock` at `0x18004f052`
- `msvcp_win!_Mtx_unlock` at `0x18004efce`
- `msvcp_win!_Mtx_unlock` at `0x18004f052`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004f032`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004f06e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004f032`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004f06e`
- `msvcp_win!_Mtx_lock` at `0x18004ef3a`
- `msvcp_win!_Mtx_lock` at `0x18004f013`
- `msvcp_win!_Mtx_lock` at `0x18004ef3a`
- `msvcp_win!_Mtx_lock` at `0x18004f013`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::cancellation_token::deregister_callback(
        Concurrency::cancellation_token *this,
        const struct Concurrency::cancellation_token_registration *a2)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // rbx
  _QWORD *v5; // rcx
  char v6; // r14
  _QWORD *v7; // rax
  __int64 v8; // rdx
  Concurrency::details::platform *v9; // rcx
  unsigned __int32 v10; // eax

  v2 = *(_QWORD *)this;
  v3 = *(_QWORD *)a2;
  v4 = *(_QWORD *)this + 24LL;
  if ( _Mtx_lock((_Mtx_t)v4) )
    goto LABEL_29;
  if ( *(_DWORD *)(v4 + 76) == 0x7FFFFFFF )
    goto LABEL_24;
  v5 = *(_QWORD **)(v2 + 104);
  if ( v5 )
  {
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      v8 = v5[1];
      if ( *v5 == v3 )
        break;
      v7 = v5;
      v5 = (_QWORD *)v5[1];
      if ( !v8 )
        goto LABEL_15;
    }
    if ( v7 )
      v7[1] = v8;
    else
      *(_QWORD *)(v2 + 104) = v8;
    if ( !v5[1] )
      *(_QWORD *)(v2 + 112) = v7;
    operator delete(v5, 0x10u);
LABEL_15:
    _InterlockedExchange((volatile __int32 *)(v3 + 16), 2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  }
  else
  {
    v6 = 1;
  }
  _Mtx_unlock((_Mtx_t)v4);
  if ( !v6 )
    return;
  v10 = _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 16), 1, 0);
  if ( v10 < 2
    || v10 - 2 < 2
    || v10 == Concurrency::details::platform::GetCurrentThreadId(v9)
    || _InterlockedExchange((volatile __int32 *)(v3 + 16), 2) == 3 )
  {
    return;
  }
  v4 = v3 + 96;
  if ( _Mtx_lock((_Mtx_t)(v3 + 96)) )
  {
LABEL_29:
    std::_Throw_Cpp_error(5);
    JUMPOUT(0x18004F074LL);
  }
  if ( *(_DWORD *)(v3 + 172) == 0x7FFFFFFF )
  {
LABEL_24:
    *(_DWORD *)(v4 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  while ( !*(_BYTE *)(v3 + 176) )
    _Cnd_wait((_Cnd_t)(v3 + 24), (_Mtx_t)(v3 + 96));
  _Mtx_unlock((_Mtx_t)(v3 + 96));
}

```

## disassembly

```asm
0x18004ef18  mov     [rsp+arg_10], rbx
0x18004ef1d  push    rbp
0x18004ef1e  push    rsi
0x18004ef1f  push    rdi
0x18004ef20  push    r13
0x18004ef22  push    r14
0x18004ef24  sub     rsp, 20h
0x18004ef28  mov     rsi, [rcx]
0x18004ef2b  mov     rdi, [rdx]
0x18004ef2e  lea     rbx, [rsi+18h]
0x18004ef32  mov     [rsp+48h+arg_8], rbx
0x18004ef37  mov     rcx, rbx; _Mtx_t
0x18004ef3a  call    cs:__imp__Mtx_lock
0x18004ef40  test    eax, eax
0x18004ef42  jnz     loc_18004F069
0x18004ef48  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18004ef4f  jz      loc_18004F026
0x18004ef55  mov     rcx, [rsi+68h]; void *
0x18004ef59  lea     ebp, [rax+2]
0x18004ef5c  lea     r13d, [rax+1]
0x18004ef60  test    rcx, rcx
0x18004ef63  jnz     short loc_18004EF6A
0x18004ef65  mov     r14b, r13b
0x18004ef68  jmp     short loc_18004EFCB
0x18004ef6a  xor     r14b, r14b
0x18004ef6d  xor     eax, eax
0x18004ef6f  mov     rdx, [rcx+8]
0x18004ef73  cmp     [rcx], rdi
0x18004ef76  jz      short loc_18004EF85
0x18004ef78  mov     rax, rcx
0x18004ef7b  mov     rcx, rdx
0x18004ef7e  test    rdx, rdx
0x18004ef81  jnz     short loc_18004EF6F
0x18004ef83  jmp     short loc_18004EFA9
0x18004ef85  test    rax, rax
0x18004ef88  jnz     short loc_18004EF90
0x18004ef8a  mov     [rsi+68h], rdx
0x18004ef8e  jmp     short loc_18004EF94
0x18004ef90  mov     [rax+8], rdx
0x18004ef94  cmp     qword ptr [rcx+8], 0
0x18004ef99  jnz     short loc_18004EF9F
0x18004ef9b  mov     [rsi+70h], rax
0x18004ef9f  mov     edx, 10h; unsigned __int64
0x18004efa4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004efa9  mov     eax, ebp
0x18004efab  xchg    eax, [rdi+10h]
0x18004efae  or      eax, 0FFFFFFFFh
0x18004efb1  lock xadd [rdi+8], eax
0x18004efb6  cmp     eax, r13d
0x18004efb9  jnz     short loc_18004EFCB
0x18004efbb  mov     rax, [rdi]
0x18004efbe  mov     rcx, rdi
0x18004efc1  mov     rax, [rax+8]
0x18004efc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efca  nop
0x18004efcb  mov     rcx, rbx; _Mtx_t
0x18004efce  call    cs:__imp__Mtx_unlock
0x18004efd4  test    r14b, r14b
0x18004efd7  jz      short loc_18004F058
0x18004efd9  xor     eax, eax
0x18004efdb  lock cmpxchg [rdi+10h], r13d
0x18004efe1  mov     ebx, eax
0x18004efe3  jz      short loc_18004F058
0x18004efe5  mov     edx, eax
0x18004efe7  test    eax, eax
0x18004efe9  jz      short loc_18004F058
0x18004efeb  sub     edx, 1
0x18004efee  jz      short loc_18004F058
0x18004eff0  sub     edx, 1
0x18004eff3  jz      short loc_18004F058
0x18004eff5  cmp     edx, 1
0x18004eff8  jz      short loc_18004F058
0x18004effa  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18004f000  cmp     ebx, eax
0x18004f002  jz      short loc_18004F058
0x18004f004  xchg    ebp, [rdi+10h]
0x18004f007  cmp     ebp, 3
0x18004f00a  jz      short loc_18004F058
0x18004f00c  lea     rbx, [rdi+60h]
0x18004f010  mov     rcx, rbx; _Mtx_t
0x18004f013  call    cs:__imp__Mtx_lock
0x18004f019  test    eax, eax
0x18004f01b  jnz     short loc_18004F069
0x18004f01d  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18004f024  jnz     short loc_18004F046
0x18004f026  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18004f02d  mov     ecx, 6
0x18004f032  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004f038  int     3; Trap to Debugger
0x18004f039  mov     rdx, rbx; _Mtx_t
0x18004f03c  lea     rcx, [rdi+18h]; _Cnd_t
0x18004f040  call    cs:__imp__Cnd_wait
0x18004f046  cmp     byte ptr [rdi+0B0h], 0
0x18004f04d  jz      short loc_18004F039
0x18004f04f  mov     rcx, rbx; _Mtx_t
0x18004f052  call    cs:__imp__Mtx_unlock
0x18004f058  mov     rbx, [rsp+48h+arg_10]
0x18004f05d  add     rsp, 20h
0x18004f061  pop     r14
0x18004f063  pop     r13
0x18004f065  pop     rdi
0x18004f066  pop     rsi
0x18004f067  pop     rbp
0x18004f068  retn
0x18004f069  mov     ecx, 5
0x18004f06e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
