# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(void)

- ea: `0x18002314c`
- end: `0x1800231d0`
- name: `??1?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_92025865ef304844afd880c1a9e1f846_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEAA@XZ`
- size: `132`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023fc0`
- `0x180024010`

## callees

- `0x18002314c`
- `0x180049010`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002316e`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002316e`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rbx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(a1[1] + 352LL));
  v2 = (volatile signed __int32 *)a1[2];
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  result = &Concurrency::details::_TaskProcHandle::`vftable';
  *a1 = &Concurrency::details::_TaskProcHandle::`vftable';
  return result;
}

```

## disassembly

```asm
0x18002314c  mov     [rsp+arg_0], rbx
0x180023151  push    rdi
0x180023152  sub     rsp, 20h
0x180023156  mov     rdi, rcx
0x180023159  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_92025865ef304844afd880c1a9e1f846_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180023160  mov     [rcx], rax
0x180023163  mov     rcx, [rcx+8]
0x180023167  add     rcx, 160h
0x18002316e  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x180023175  nop     dword ptr [rax+rax+00h]
0x18002317a  mov     rbx, [rdi+10h]
0x18002317e  test    rbx, rbx
0x180023181  jz      short loc_1800231BA
0x180023183  or      eax, 0FFFFFFFFh
0x180023186  lock xadd [rbx+8], eax
0x18002318b  cmp     eax, 1
0x18002318e  jnz     short loc_1800231BA
0x180023190  mov     rax, [rbx]
0x180023193  mov     rcx, rbx
0x180023196  mov     rax, [rax]
0x180023199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002319e  or      eax, 0FFFFFFFFh
0x1800231a1  lock xadd [rbx+0Ch], eax
0x1800231a6  cmp     eax, 1
0x1800231a9  jnz     short loc_1800231BA
0x1800231ab  mov     rax, [rbx]
0x1800231ae  mov     rcx, rbx
0x1800231b1  mov     rax, [rax+8]
0x1800231b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231ba  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x1800231c1  mov     [rdi], rax
0x1800231c4  mov     rbx, [rsp+28h+arg_0]
0x1800231c9  add     rsp, 20h
0x1800231cd  pop     rdi
0x1800231ce  retn
```
