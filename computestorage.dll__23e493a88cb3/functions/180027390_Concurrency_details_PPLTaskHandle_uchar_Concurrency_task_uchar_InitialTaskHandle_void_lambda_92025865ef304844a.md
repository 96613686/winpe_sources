# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x180027390`
- end: `0x18002747c`
- name: `?invoke@?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_92025865ef304844afd880c1a9e1f846_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEBAXXZ`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800263bc`
- `0x180027390`
- `0x180049010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800273c5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800273e7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800273c5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800273e7`
- `msvcp_win!_Mtx_lock` at `0x1800273b0`
- `msvcp_win!_Mtx_lock` at `0x1800273b0`
- `msvcp_win!_Mtx_unlock` at `0x1800273ff`
- `msvcp_win!_Mtx_unlock` at `0x18002743c`
- `msvcp_win!_Mtx_unlock` at `0x1800273ff`
- `msvcp_win!_Mtx_unlock` at `0x18002743c`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180027461`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180027461`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
        __int64 a1)
{
  _QWORD *v2; // r14
  __int64 v3; // rdi
  struct _Mtx_internal_imp_t *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  Concurrency::details::_Task_impl_base *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int128 v11; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v12; // [rsp+40h] [rbp-38h]

  *(_QWORD *)&v11 = a1;
  v2 = (_QWORD *)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 8);
  if ( _Mtx_lock((_Mtx_t)(v3 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v3 + 108) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v3 + 108) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v4 = (struct _Mtx_internal_imp_t *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 8) == 2 )
  {
    _Mtx_unlock(v4);
    LOBYTE(v5) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)*v2 + 8LL))(*v2, v5, 0, 0, *v2 + 16LL);
  }
  else
  {
    v12 = v2;
    *(_DWORD *)(v3 + 8) = 1;
    _Mtx_unlock(v4);
    try
    {
      Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
    }
    catch ( Concurrency::task_canceled )
    {
      v6 = *(_QWORD *)(v11 + 8);
      v7 = v6 + 16;
      LOBYTE(v7) = 1;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v6 + 8LL))(v6, v7, 0, 0, v6 + 16);
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v9 = *(_QWORD *)(v11 + 8);
      v10 = v9 + 16;
      LOBYTE(v10) = 1;
      guard_dispatch_icall_thunk_10345483385596137414(v9, v10, 0, 0, v9 + 16);
    }
    catch ( ... )
    {
      v8 = *(Concurrency::details::_Task_impl_base **)(v11 + 8);
      v11 = 0;
      __ExceptionPtrCreate(&v11);
      __ExceptionPtrCurrentException(&v11);
      Concurrency::details::_Task_impl_base::_CancelWithException(v8, (const struct std::exception_ptr *)&v11);
      __ExceptionPtrDestroy(&v11);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*v12 + 352LL));
  }
}

```

## disassembly

```asm
0x180027390  push    rbx
0x180027392  push    rsi
0x180027393  push    rdi
0x180027394  push    r14
0x180027396  sub     rsp, 58h
0x18002739a  mov     rsi, rcx
0x18002739d  mov     qword ptr [rsp+78h+var_48], rcx
0x1800273a2  lea     r14, [rcx+8]
0x1800273a6  mov     rdi, [r14]
0x1800273a9  lea     rbx, [rdi+20h]
0x1800273ad  mov     rcx, rbx; _Mtx_t
0x1800273b0  call    cs:__imp__Mtx_lock
0x1800273b7  nop     dword ptr [rax+rax+00h]
0x1800273bc  test    eax, eax
0x1800273be  jz      short loc_1800273D2
0x1800273c0  mov     ecx, 5
0x1800273c5  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800273cc  nop     dword ptr [rax+rax+00h]
0x1800273d1  int     3; Trap to Debugger
0x1800273d2  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800273d9  jnz     short loc_1800273F4
0x1800273db  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x1800273e2  mov     ecx, 6
0x1800273e7  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800273ee  nop     dword ptr [rax+rax+00h]
0x1800273f3  int     3; Trap to Debugger
0x1800273f4  mov     eax, [rdi+8]
0x1800273f7  mov     rcx, rbx; _Mtx_t
0x1800273fa  cmp     eax, 2
0x1800273fd  jnz     short loc_180027430
0x1800273ff  call    cs:__imp__Mtx_unlock
0x180027406  nop     dword ptr [rax+rax+00h]
0x18002740b  mov     r10, [r14]
0x18002740e  mov     rax, [r10]
0x180027411  lea     rcx, [r10+10h]
0x180027415  mov     [rsp+78h+var_58], rcx
0x18002741a  xor     r9d, r9d
0x18002741d  xor     r8d, r8d
0x180027420  mov     dl, 1
0x180027422  mov     rcx, r10
0x180027425  mov     rax, [rax+8]
0x180027429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002742e  jmp     short loc_18002746D
0x180027430  mov     [rsp+78h+var_38], r14
0x180027435  mov     dword ptr [rdi+8], 1
0x18002743c  call    cs:__imp__Mtx_unlock
0x180027443  nop     dword ptr [rax+rax+00h]
0x180027448  nop
0x180027449  mov     rcx, rsi
0x18002744c  call    ?_Init@?$_InitialTaskHandle@XV_lambda_92025865ef304844afd880c1a9e1f846_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x180027451  nop
0x180027452  mov     rax, [rsp+78h+var_38]
0x180027457  mov     rcx, [rax]
0x18002745a  add     rcx, 160h
0x180027461  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180027468  nop     dword ptr [rax+rax+00h]
0x18002746d  add     rsp, 58h
0x180027471  pop     r14
0x180027473  pop     rdi
0x180027474  pop     rsi
0x180027475  pop     rbx
0x180027476  retn
0x180027478  jmp     short loc_180027452
0x18002747a  jmp     short loc_180027452
```
