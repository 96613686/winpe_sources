# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x180025430`
- end: `0x180025632`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `514`
- prototype: `char __fastcall(__int64, char, char, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180025430`
- `0x1800258a8`
- `0x180026c14`
- `0x180049010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180025568`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180025568`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002546c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002548e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002546c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002548e`
- `msvcp_win!_Mtx_lock` at `0x180025457`
- `msvcp_win!_Mtx_lock` at `0x180025457`
- `msvcp_win!_Mtx_unlock` at `0x180025578`
- `msvcp_win!_Mtx_unlock` at `0x18002560e`
- `msvcp_win!_Mtx_unlock` at `0x180025578`
- `msvcp_win!_Mtx_unlock` at `0x18002560e`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl<unsigned char>::_CancelAndRunContinuations(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v8; // rsi
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rdi
  int v13; // edi
  int v14; // edi
  __int64 v15; // rcx
  _QWORD *v16; // rdx
  _QWORD v18[7]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v19; // [rsp+58h] [rbp-20h]

  v8 = a1 + 32;
  if ( _Mtx_lock((_Mtx_t)(a1 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v8 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v8 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v9 = *(_DWORD *)(a1 + 8);
  if ( a3 )
  {
    if ( v9 != 4 )
    {
      v10 = a5[1];
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
      v11 = a5[1];
      *(_QWORD *)(a1 + 16) = *a5;
      v12 = *(volatile signed __int32 **)(a1 + 24);
      *(_QWORD *)(a1 + 24) = v11;
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      goto LABEL_17;
    }
LABEL_30:
    _Mtx_unlock((_Mtx_t)v8);
    return 0;
  }
  if ( v9 == 3 || *(_DWORD *)(a1 + 8) == 4 || *(_DWORD *)(a1 + 8) == 2 && !a2 )
    goto LABEL_30;
LABEL_17:
  if ( a2 )
  {
    *(_DWORD *)(a1 + 8) = 4;
    v13 = 1;
  }
  else
  {
    v13 = 0;
    if ( *(_DWORD *)(a1 + 8) == 1 )
      v13 = 2;
    *(_DWORD *)(a1 + 8) = 2;
    Concurrency::details::_TaskEventLogger::_LogCancelTask((Concurrency::details::_TaskEventLogger *)(a1 + 352));
  }
  _Mtx_unlock((_Mtx_t)v8);
  v14 = v13 - 1;
  if ( v14 )
  {
    if ( v14 == 1 )
    {
      v15 = *(_QWORD *)(a1 + 432);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  else
  {
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(a1 + 136));
    if ( *(_QWORD *)(a1 + 112) )
    {
      v18[0] = &std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable';
      v18[1] = a1;
      v19 = v18;
      Concurrency::details::_ScheduleFuncWithAutoInline(v18, 16);
      if ( v19 )
      {
        v16 = v18;
        LOBYTE(v16) = v19 != v18;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v19 + 32LL))(v19, v16);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180025430  mov     rax, rsp
0x180025433  mov     [rax+10h], rbx
0x180025437  mov     [rax+18h], rbp
0x18002543b  push    rsi
0x18002543c  push    rdi
0x18002543d  push    r15
0x18002543f  sub     rsp, 60h
0x180025443  mov     dil, r8b
0x180025446  mov     bpl, dl
0x180025449  mov     rbx, rcx
0x18002544c  lea     rsi, [rcx+20h]
0x180025450  mov     [rax+8], rsi
0x180025454  mov     rcx, rsi; _Mtx_t
0x180025457  call    cs:__imp__Mtx_lock
0x18002545e  nop     dword ptr [rax+rax+00h]
0x180025463  test    eax, eax
0x180025465  jz      short loc_180025479
0x180025467  mov     ecx, 5
0x18002546c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180025473  nop     dword ptr [rax+rax+00h]
0x180025478  int     3; Trap to Debugger
0x180025479  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x180025480  jnz     short loc_18002549B
0x180025482  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x180025489  mov     ecx, 6
0x18002548e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180025495  nop     dword ptr [rax+rax+00h]
0x18002549a  nop
0x18002549b  mov     r15d, 2
0x1800254a1  mov     eax, [rbx+8]
0x1800254a4  test    dil, dil
0x1800254a7  jz      short loc_180025518
0x1800254a9  cmp     eax, 4
0x1800254ac  jz      loc_18002560B
0x1800254b2  mov     rdx, [rsp+78h+arg_20]
0x1800254ba  mov     rax, [rdx+8]
0x1800254be  test    rax, rax
0x1800254c1  jz      short loc_1800254C7
0x1800254c3  lock inc dword ptr [rax+8]
0x1800254c7  mov     rcx, [rdx+8]
0x1800254cb  mov     rax, [rdx]
0x1800254ce  mov     [rbx+10h], rax
0x1800254d2  mov     rdi, [rbx+18h]
0x1800254d6  mov     [rbx+18h], rcx
0x1800254da  test    rdi, rdi
0x1800254dd  jz      short loc_18002553E
0x1800254df  or      eax, 0FFFFFFFFh
0x1800254e2  lock xadd [rdi+8], eax
0x1800254e7  cmp     eax, 1
0x1800254ea  jnz     short loc_18002553E
0x1800254ec  mov     rax, [rdi]
0x1800254ef  mov     rcx, rdi
0x1800254f2  mov     rax, [rax]
0x1800254f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254fa  or      eax, 0FFFFFFFFh
0x1800254fd  lock xadd [rdi+0Ch], eax
0x180025502  cmp     eax, 1
0x180025505  jnz     short loc_18002553E
0x180025507  mov     rax, [rdi]
0x18002550a  mov     rcx, rdi
0x18002550d  mov     rax, [rax+8]
0x180025511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025516  jmp     short loc_18002553E
0x180025518  cmp     eax, 3
0x18002551b  jz      loc_18002560B
0x180025521  mov     eax, [rbx+8]
0x180025524  cmp     eax, 4
0x180025527  jz      loc_18002560B
0x18002552d  mov     eax, [rbx+8]
0x180025530  cmp     eax, r15d
0x180025533  jnz     short loc_18002553E
0x180025535  test    bpl, bpl
0x180025538  jz      loc_18002560B
0x18002553e  test    bpl, bpl
0x180025541  jz      short loc_180025551
0x180025543  mov     dword ptr [rbx+8], 4
0x18002554a  mov     edi, 1
0x18002554f  jmp     short loc_180025575
0x180025551  mov     eax, [rbx+8]
0x180025554  xor     edi, edi
0x180025556  cmp     eax, 1
0x180025559  cmovz   edi, r15d
0x18002555d  mov     [rbx+8], r15d
0x180025561  lea     rcx, [rbx+160h]
0x180025568  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18002556f  nop     dword ptr [rax+rax+00h]
0x180025574  nop
0x180025575  mov     rcx, rsi; _Mtx_t
0x180025578  call    cs:__imp__Mtx_unlock
0x18002557f  nop     dword ptr [rax+rax+00h]
0x180025584  sub     edi, 1
0x180025587  jz      short loc_1800255A8
0x180025589  cmp     edi, 1
0x18002558c  jnz     short loc_180025607
0x18002558e  mov     rcx, [rbx+1B0h]
0x180025595  test    rcx, rcx
0x180025598  jz      short loc_180025607
0x18002559a  mov     rax, [rcx]
0x18002559d  mov     rax, [rax+10h]
0x1800255a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255a6  jmp     short loc_180025607
0x1800255a8  lea     rcx, [rbx+88h]; this
0x1800255af  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x1800255b4  cmp     qword ptr [rbx+70h], 0
0x1800255b9  jz      short loc_180025607
0x1800255bb  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x1800255c2  mov     [rsp+78h+var_58], rax
0x1800255c7  mov     [rsp+78h+var_50], rbx
0x1800255cc  lea     rax, [rsp+78h+var_58]
0x1800255d1  mov     [rsp+78h+var_20], rax
0x1800255d6  mov     edx, 10h
0x1800255db  lea     rcx, [rsp+78h+var_58]
0x1800255e0  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x1800255e5  nop
0x1800255e6  mov     rcx, [rsp+78h+var_20]
0x1800255eb  test    rcx, rcx
0x1800255ee  jz      short loc_180025607
0x1800255f0  mov     rax, [rcx]
0x1800255f3  lea     rdx, [rsp+78h+var_58]
0x1800255f8  cmp     rcx, rdx
0x1800255fb  setnz   dl
0x1800255fe  mov     rax, [rax+20h]
0x180025602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025607  mov     al, 1
0x180025609  jmp     short loc_18002561C
0x18002560b  mov     rcx, rsi; _Mtx_t
0x18002560e  call    cs:__imp__Mtx_unlock
0x180025615  nop     dword ptr [rax+rax+00h]
0x18002561a  xor     al, al
0x18002561c  lea     r11, [rsp+78h+var_18]
0x180025621  mov     rbx, [r11+28h]
0x180025625  mov     rbp, [r11+30h]
0x180025629  mov     rsp, r11
0x18002562c  pop     r15
0x18002562e  pop     rdi
0x18002562f  pop     rsi
0x180025630  retn
```
