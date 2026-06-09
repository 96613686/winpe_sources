# Concurrency::details::_CancellationTokenRegistration::_Invoke(void)

- ea: `0x180026604`
- end: `0x1800266ea`
- name: `?_Invoke@_CancellationTokenRegistration@details@Concurrency@@AEAAXXZ`
- size: `230`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenRegistration *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026780`

## callees

- `0x180026604`
- `0x180049010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180026611`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180026611`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180026666`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002668e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180026666`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002668e`
- `msvcp_win!_Mtx_lock` at `0x180026653`
- `msvcp_win!_Mtx_lock` at `0x180026653`
- `msvcp_win!_Mtx_unlock` at `0x1800266a6`
- `msvcp_win!_Mtx_unlock` at `0x1800266a6`
- `msvcp_win!_Cnd_broadcast` at `0x1800266b6`
- `msvcp_win!_Cnd_broadcast` at `0x1800266b6`

## pseudocode

```c
void __fastcall Concurrency::details::_CancellationTokenRegistration::_Invoke(
        Concurrency::details::_CancellationTokenRegistration *this)
{
  signed __int32 CurrentThreadId; // edi
  signed __int32 v3; // eax

  CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId(this);
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 4, CurrentThreadId, 0) )
  {
    (*(void (__fastcall **)(Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)this + 16LL))(this);
    v3 = _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 3, CurrentThreadId);
    if ( CurrentThreadId != v3 )
      CurrentThreadId = v3;
    if ( CurrentThreadId == 2 )
    {
      if ( _Mtx_lock((Concurrency::details::_CancellationTokenRegistration *)((char *)this + 96)) )
      {
        std::_Throw_Cpp_error(5);
        __debugbreak();
      }
      if ( *((_DWORD *)this + 43) == 0x7FFFFFFF )
      {
        *((_DWORD *)this + 43) = 2147483646;
        std::_Throw_Cpp_error(6);
        __debugbreak();
      }
      *((_BYTE *)this + 176) = 1;
      _Mtx_unlock((Concurrency::details::_CancellationTokenRegistration *)((char *)this + 96));
      _Cnd_broadcast((Concurrency::details::_CancellationTokenRegistration *)((char *)this + 24));
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)this + 8LL))(this);
}

```

## disassembly

```asm
0x180026604  mov     [rsp+arg_8], rbx
0x180026609  push    rdi
0x18002660a  sub     rsp, 20h
0x18002660e  mov     rbx, rcx
0x180026611  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180026618  nop     dword ptr [rax+rax+00h]
0x18002661d  mov     edi, eax
0x18002661f  xor     eax, eax
0x180026621  lock cmpxchg [rbx+10h], edi
0x180026626  jnz     loc_1800266C2
0x18002662c  mov     rax, [rbx]
0x18002662f  mov     rcx, rbx
0x180026632  mov     rax, [rax+10h]
0x180026636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002663b  mov     ecx, 3
0x180026640  mov     eax, edi
0x180026642  lock cmpxchg [rbx+10h], ecx
0x180026647  cmovnz  edi, eax
0x18002664a  cmp     edi, 2
0x18002664d  jnz     short loc_1800266C2
0x18002664f  lea     rcx, [rbx+60h]; _Mtx_t
0x180026653  call    cs:__imp__Mtx_lock
0x18002665a  nop     dword ptr [rax+rax+00h]
0x18002665f  test    eax, eax
0x180026661  jz      short loc_180026673
0x180026663  lea     ecx, [rdi+3]
0x180026666  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002666d  nop     dword ptr [rax+rax+00h]
0x180026672  int     3; Trap to Debugger
0x180026673  cmp     dword ptr [rbx+0ACh], 7FFFFFFFh
0x18002667d  jnz     short loc_18002669B
0x18002667f  mov     ecx, 6
0x180026684  mov     dword ptr [rbx+0ACh], 7FFFFFFEh
0x18002668e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180026695  nop     dword ptr [rax+rax+00h]
0x18002669a  int     3; Trap to Debugger
0x18002669b  lea     rcx, [rbx+60h]; _Mtx_t
0x18002669f  mov     byte ptr [rbx+0B0h], 1
0x1800266a6  call    cs:__imp__Mtx_unlock
0x1800266ad  nop     dword ptr [rax+rax+00h]
0x1800266b2  lea     rcx, [rbx+18h]; _Cnd_t
0x1800266b6  call    cs:__imp__Cnd_broadcast
0x1800266bd  nop     dword ptr [rax+rax+00h]
0x1800266c2  or      eax, 0FFFFFFFFh
0x1800266c5  lock xadd [rbx+8], eax
0x1800266ca  cmp     eax, 1
0x1800266cd  jnz     short loc_1800266DE
0x1800266cf  mov     rax, [rbx]
0x1800266d2  mov     rcx, rbx
0x1800266d5  mov     rax, [rax+8]
0x1800266d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266de  mov     rbx, [rsp+28h+arg_8]
0x1800266e3  add     rsp, 20h
0x1800266e7  pop     rdi
0x1800266e8  retn
```
