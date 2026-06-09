# Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18004e8a8`
- end: `0x18004ea08`
- name: `?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `352`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180042ba8`
- `0x180042cb8`
- `0x180042dc8`
- `0x180042ed8`

## callees

- `0x180003568`
- `0x18004e8a8`
- `0x180061010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18004e959`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18004e959`
- `msvcp_win!_Cnd_broadcast` at `0x18004e9dd`
- `msvcp_win!_Cnd_broadcast` at `0x18004e9dd`
- `msvcp_win!_Mtx_unlock` at `0x18004e94a`
- `msvcp_win!_Mtx_unlock` at `0x18004e9d3`
- `msvcp_win!_Mtx_unlock` at `0x18004e94a`
- `msvcp_win!_Mtx_unlock` at `0x18004e9d3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004e9a0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004e9c1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004e9a0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004e9c1`
- `msvcp_win!_Mtx_lock` at `0x18004e8df`
- `msvcp_win!_Mtx_lock` at `0x18004e991`
- `msvcp_win!_Mtx_lock` at `0x18004e8df`
- `msvcp_win!_Mtx_lock` at `0x18004e991`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_RegisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  char *v4; // rsi
  char v5; // bp
  _QWORD *v6; // rax
  signed __int32 CurrentThreadId; // edi
  signed __int32 v8; // eax

  _InterlockedExchange((volatile __int32 *)a2 + 4, 0);
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_QWORD *)a2 + 23) = this;
  if ( *((_DWORD *)this + 4) )
    goto LABEL_12;
  v4 = (char *)this + 24;
  if ( _Mtx_lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24)) )
    goto LABEL_17;
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v4 + 19) = 2147483646;
    goto LABEL_20;
  }
  if ( *((_DWORD *)this + 4) )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    v6 = operator new(0x10u);
    *v6 = a2;
    v6[1] = 0;
    if ( *((_QWORD *)this + 13) )
      *(_QWORD *)(*((_QWORD *)this + 14) + 8LL) = v6;
    else
      *((_QWORD *)this + 13) = v6;
    *((_QWORD *)this + 14) = v6;
  }
  _Mtx_unlock((_Mtx_t)v4);
  if ( v5 )
  {
LABEL_12:
    CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId(this);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, CurrentThreadId, 0) )
    {
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 16LL))(a2);
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 3, CurrentThreadId);
      if ( CurrentThreadId != v8 )
        CurrentThreadId = v8;
      if ( CurrentThreadId == 2 )
      {
        if ( _Mtx_lock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96)) )
        {
LABEL_17:
          std::_Throw_Cpp_error(5);
          __debugbreak();
        }
        if ( *((_DWORD *)a2 + 43) == 0x7FFFFFFF )
        {
          *((_DWORD *)a2 + 43) = 2147483646;
LABEL_20:
          std::_Throw_Cpp_error(6);
          __debugbreak();
        }
        *((_BYTE *)a2 + 176) = 1;
        _Mtx_unlock((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 96));
        _Cnd_broadcast((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24));
      }
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 8LL))(a2);
  }
}

```

## disassembly

```asm
0x18004e8a8  push    rbx
0x18004e8aa  push    rbp
0x18004e8ab  push    rsi
0x18004e8ac  push    rdi
0x18004e8ad  sub     rsp, 28h
0x18004e8b1  mov     rbx, rdx
0x18004e8b4  mov     rdi, rcx
0x18004e8b7  xor     eax, eax
0x18004e8b9  xchg    eax, [rdx+10h]
0x18004e8bc  lock inc dword ptr [rdx+8]
0x18004e8c0  mov     [rdx+0B8h], rcx
0x18004e8c7  mov     eax, [rcx+10h]
0x18004e8ca  nop
0x18004e8cb  test    eax, eax
0x18004e8cd  jnz     loc_18004E959
0x18004e8d3  lea     rsi, [rcx+18h]
0x18004e8d7  mov     [rsp+48h+arg_0], rsi
0x18004e8dc  mov     rcx, rsi; _Mtx_t
0x18004e8df  call    cs:__imp__Mtx_lock
0x18004e8e5  test    eax, eax
0x18004e8e7  jnz     loc_18004E99B
0x18004e8ed  mov     eax, [rsi+4Ch]
0x18004e8f0  cmp     eax, 7FFFFFFFh
0x18004e8f5  jnz     short loc_18004E901
0x18004e8f7  dec     eax
0x18004e8f9  mov     [rsi+4Ch], eax
0x18004e8fc  jmp     loc_18004E9BC
0x18004e901  mov     eax, [rdi+10h]
0x18004e904  nop
0x18004e905  test    eax, eax
0x18004e907  jz      short loc_18004E90E
0x18004e909  mov     bpl, 1
0x18004e90c  jmp     short loc_18004E947
0x18004e90e  xor     bpl, bpl
0x18004e911  mov     ecx, 10h; Size
0x18004e916  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e91b  mov     rcx, rax
0x18004e91e  mov     [rsp+48h+arg_0], rax
0x18004e923  mov     [rax], rbx
0x18004e926  mov     qword ptr [rax+8], 0
0x18004e92e  cmp     qword ptr [rdi+68h], 0
0x18004e933  jnz     short loc_18004E93B
0x18004e935  mov     [rdi+68h], rax
0x18004e939  jmp     short loc_18004E943
0x18004e93b  mov     rax, [rdi+70h]
0x18004e93f  mov     [rax+8], rcx
0x18004e943  mov     [rdi+70h], rcx
0x18004e947  mov     rcx, rsi; _Mtx_t
0x18004e94a  call    cs:__imp__Mtx_unlock
0x18004e950  test    bpl, bpl
0x18004e953  jz      loc_18004E9FF
0x18004e959  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x18004e95f  mov     edi, eax
0x18004e961  xor     eax, eax
0x18004e963  lock cmpxchg [rbx+10h], edi
0x18004e968  jnz     short loc_18004E9E3
0x18004e96a  mov     rcx, [rbx]
0x18004e96d  mov     rax, [rcx+10h]
0x18004e971  mov     rcx, rbx
0x18004e974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e979  mov     ecx, 3
0x18004e97e  mov     eax, edi
0x18004e980  lock cmpxchg [rbx+10h], ecx
0x18004e985  cmovnz  edi, eax
0x18004e988  cmp     edi, 2
0x18004e98b  jnz     short loc_18004E9E3
0x18004e98d  lea     rcx, [rbx+60h]; _Mtx_t
0x18004e991  call    cs:__imp__Mtx_lock
0x18004e997  test    eax, eax
0x18004e999  jz      short loc_18004E9A7
0x18004e99b  mov     ecx, 5
0x18004e9a0  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004e9a6  int     3; Trap to Debugger
0x18004e9a7  mov     eax, [rbx+0ACh]
0x18004e9ad  cmp     eax, 7FFFFFFFh
0x18004e9b2  jnz     short loc_18004E9C8
0x18004e9b4  dec     eax
0x18004e9b6  mov     [rbx+0ACh], eax
0x18004e9bc  mov     ecx, 6
0x18004e9c1  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004e9c7  int     3; Trap to Debugger
0x18004e9c8  mov     byte ptr [rbx+0B0h], 1
0x18004e9cf  lea     rcx, [rbx+60h]; _Mtx_t
0x18004e9d3  call    cs:__imp__Mtx_unlock
0x18004e9d9  lea     rcx, [rbx+18h]; _Cnd_t
0x18004e9dd  call    cs:__imp__Cnd_broadcast
0x18004e9e3  or      eax, 0FFFFFFFFh
0x18004e9e6  lock xadd [rbx+8], eax
0x18004e9eb  cmp     eax, 1
0x18004e9ee  jnz     short loc_18004E9FF
0x18004e9f0  mov     rax, [rbx]
0x18004e9f3  mov     rcx, rbx
0x18004e9f6  mov     rax, [rax+8]
0x18004e9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9ff  add     rsp, 28h
0x18004ea03  pop     rdi
0x18004ea04  pop     rsi
0x18004ea05  pop     rbp
0x18004ea06  pop     rbx
0x18004ea07  retn
```
