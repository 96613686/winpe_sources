# ?_Init@?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@A6AJX_E@std@@@?$_Task_async_state@J@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@A6AJX_E@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z

- ea: `0x1800a821c`
- end: `0x1800a83b7`
- name: `?_Init@?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@A6AJX_E@std@@@?$_Task_async_state@J@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@A6AJX_E@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b8210`

## callees

- `0x18000c160`
- `0x180018424`
- `0x1800a821c`
- `0x1800a83c0`
- `0x1800a8dac`
- `0x1800b6b04`
- `0x1800b8844`
- `0x180149010`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800a830d`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800a830d`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800a82e5`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800a82e5`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800a82f5`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800a82f5`
- `msvcp_win!_Mtx_unlock` at `0x1800a8358`
- `msvcp_win!_Mtx_unlock` at `0x1800a8367`
- `msvcp_win!_Mtx_unlock` at `0x1800a839d`
- `msvcp_win!_Mtx_unlock` at `0x1800a8358`
- `msvcp_win!_Mtx_unlock` at `0x1800a8367`
- `msvcp_win!_Mtx_unlock` at `0x1800a839d`
- `msvcp_win!_Cnd_broadcast` at `0x1800a8393`
- `msvcp_win!_Cnd_broadcast` at `0x1800a8393`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall __Init____InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_A6AJX_E_std______Task_async_state_J_std__QEAA___QEAV___Fake_no_copy_callable_adapter_A6AJX_E_3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__QEBAXU_TypeSelectorNoAsync_details_3__Z(
        __int64 a1)
{
  __int64 v2; // rsi
  _QWORD *v3; // rbx
  Concurrency::details::_TaskEventLogger *v4; // rdi
  char v5; // bl
  _BYTE *v6; // rdx
  struct _Mtx_internal_imp_t *v7; // rcx
  _QWORD v8[8]; // [rsp+20h] [rbp-89h] BYREF
  _BYTE v9[56]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE *v10; // [rsp+98h] [rbp-11h]
  _BYTE v11[96]; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE *v12; // [rsp+110h] [rbp+67h] BYREF
  Concurrency::details::_TaskEventLogger *v13; // [rsp+120h] [rbp+77h]
  _QWORD *v14; // [rsp+128h] [rbp+7Fh]

  v2 = *(_QWORD *)(a1 + 8);
  v13 = (Concurrency::details::_TaskEventLogger *)v9;
  v8[0] = ___7___Func_impl_no_alloc_V_lambda_1___1_____0V___Fake_no_copy_callable_adapter_A6AJX_E_std______Task_async_state_J_std__QEAA___QEAV___Fake_no_copy_callable_adapter_A6AJX_E_3__Z_X__V_std__6B_;
  v8[1] = *(_QWORD *)(a1 + 24);
  v8[7] = v8;
  v14 = v8;
  std::function<long (wil::com_ptr_t<INotifyNetworkSignatureEventsPrivate,wil::err_exception_policy> const &)>::function<long (wil::com_ptr_t<INotifyNetworkSignatureEventsPrivate,wil::err_exception_policy> const &)>(
    v11,
    v8);
  v10 = 0;
  v3 = operator new(0x48u);
  v12 = v3;
  *v3 = ___7___Func_impl_no_alloc_V_lambda_1___1___MakeVoidToUnitFunc_details_Concurrency__YA_AV__function___A6AEXZ_std__AEBV__function___A6AXXZ_6__Z_E__V_std__6B_;
  std::function<long (wil::com_ptr_t<INotifyNetworkSignatureEventsPrivate,wil::err_exception_policy> const &)>::function<long (wil::com_ptr_t<INotifyNetworkSignatureEventsPrivate,wil::err_exception_policy> const &)>(
    v3 + 1,
    v11);
  v12 = 0;
  __1_Guard_type__1_____Global_new_V___Func_impl_no_alloc_V_lambda_1___1___MakeVoidToUnitFunc_details_Concurrency__YA_AV__function___A6AEXZ_std__AEBV__function___A6AXXZ_6__Z_E__V_std__V_lambda_1___1___MakeVoidToUnitFunc_details_Concurrency__YA_AV__function___A6AEXZ_2_AEBV__function___A6AXXZ_2__Z__std__YAPEAV___Func_impl_no_alloc_V_lambda_1___1___MakeVoidToUnitFunc_details_Concurrency__YA_AV__function___A6AEXZ_std__AEBV__function___A6AXXZ_6__Z_E__V_1___QEAV_lambda_1___1___MakeVoidToUnitFunc_details_Concurrency__YA_AV__function___A6AEXZ_1_AEBV__function___A6AXXZ_1__Z__Z_QEAA_XZ(&v12);
  v10 = v3;
  std::_Func_class<void,>::~_Func_class<void,>(v11);
  std::_Func_class<void,>::~_Func_class<void,>(v8);
  v12 = v9;
  v4 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  v13 = v4;
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v4);
  if ( !v10 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v5 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v10 + 16LL))(v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v4);
  if ( v10 )
  {
    v6 = v9;
    LOBYTE(v6) = v10 != v9;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v10 + 32LL))(v10, v6);
    v10 = 0;
  }
  *(_BYTE *)(v2 + 368) = v5;
  std::_Mutex_base::lock((std::_Mutex_base *)(v2 + 32));
  v7 = (struct _Mtx_internal_imp_t *)(v2 + 32);
  if ( *(_DWORD *)(v2 + 8) == 4 )
  {
    _Mtx_unlock(v7);
  }
  else
  {
    *(_DWORD *)(v2 + 8) = 3;
    _Mtx_unlock(v7);
    std::_Mutex_base::lock((std::_Mutex_base *)(v2 + 208));
    if ( *(int *)(v2 + 312) < 2 )
      *(_DWORD *)(v2 + 312) = 2;
    _Cnd_broadcast((_Cnd_t)(v2 + 136));
    _Mtx_unlock((_Mtx_t)(v2 + 208));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
  }
}

```

## disassembly

```asm
0x1800a821c  push    rbp
0x1800a821e  push    rbx
0x1800a821f  push    rsi
0x1800a8220  push    rdi
0x1800a8221  lea     rbp, [rsp-3Fh]
0x1800a8226  sub     rsp, 0E8h
0x1800a822d  mov     rdi, rcx
0x1800a8230  mov     rsi, [rcx+8]
0x1800a8234  lea     rax, [rbp+57h+var_A0]
0x1800a8238  mov     [rbp+57h+arg_10], rax
0x1800a823c  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@A6AJX_E@std@@@?$_Task_async_state@J@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@A6AJX_E@3@@Z@X$$V@std@@6B@
0x1800a8243  mov     [rsp+100h+var_E0], rax
0x1800a8248  mov     rax, [rcx+18h]
0x1800a824c  mov     [rsp+100h+var_D8], rax
0x1800a8251  lea     rax, [rsp+100h+var_E0]
0x1800a8256  mov     [rbp+57h+var_A8], rax
0x1800a825a  lea     rax, [rsp+100h+var_E0]
0x1800a825f  mov     [rbp+57h+arg_18], rax
0x1800a8263  lea     rdx, [rsp+100h+var_E0]
0x1800a8268  lea     rcx, [rbp+57h+var_60]
0x1800a826c  call    ??0?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkSignatureEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@QEAA@AEBV01@@Z; std::function<long (wil::com_ptr_t<INotifyNetworkSignatureEventsPrivate,wil::err_exception_policy> const &)>::function<long (wil::com_ptr_t<INotifyNetworkSignatureEventsPrivate,wil::err_exception_policy> const &)>(std::function<long (wil::com_ptr_t<INotifyNetworkSignatureEventsPrivate,wil::err_exception_policy> const &)> const &)
0x1800a8271  nop
0x1800a8272  mov     [rbp+57h+var_68], 0
0x1800a827a  mov     ecx, 48h ; 'H'; Size
0x1800a827f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a8284  mov     rbx, rax
0x1800a8287  mov     [rbp+57h+arg_0], rax
0x1800a828b  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@std@@AEBV?$function@$$A6AXXZ@6@@Z@E$$V@std@@6B@; const std::_Func_impl_no_alloc<`Concurrency::details::_MakeVoidToUnitFunc(std::function<void (void)> const &)'::`2'::_lambda_1_,uchar,>::`vftable'
0x1800a8292  mov     [rbx], rax
0x1800a8295  lea     rcx, [rbx+8]
0x1800a8299  lea     rdx, [rbp+57h+var_60]
0x1800a829d  call    ??0?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkSignatureEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@QEAA@AEBV01@@Z; std::function<long (wil::com_ptr_t<INotifyNetworkSignatureEventsPrivate,wil::err_exception_policy> const &)>::function<long (wil::com_ptr_t<INotifyNetworkSignatureEventsPrivate,wil::err_exception_policy> const &)>(std::function<long (wil::com_ptr_t<INotifyNetworkSignatureEventsPrivate,wil::err_exception_policy> const &)> const &)
0x1800a82a2  mov     [rbp+57h+arg_0], 0
0x1800a82aa  lea     rcx, [rbp+57h+arg_0]
0x1800a82ae  call    ??1_Guard_type@?1???$_Global_new@V?$_Func_impl_no_alloc@V_lambda_1_@?1??_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@std@@AEBV?$function@$$A6AXXZ@6@@Z@E$$V@std@@V_lambda_1_@?1??_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@2@AEBV?$function@$$A6AXXZ@2@@Z@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_1_@?1??_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@std@@AEBV?$function@$$A6AXXZ@6@@Z@E$$V@1@$$QEAV_lambda_1_@?1??_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@1@AEBV?$function@$$A6AXXZ@1@@Z@@Z@QEAA@XZ; `std::_Global_new<std::_Func_impl_no_alloc<`Concurrency::details::_MakeVoidToUnitFunc(std::function<void (void)> const &)'::`2'::_lambda_1_,uchar,>,`Concurrency::details::_MakeVoidToUnitFunc(std::function<void (void)> const &)'::`2'::_lambda_1_>(`Concurrency::details::_MakeVoidToUnitFunc(std::function<void (void)> const &)'::`2'::_lambda_1_ &&)'::`2'::_Guard_type::~_Guard_type(void)
0x1800a82b3  mov     [rbp+57h+var_68], rbx
0x1800a82b7  lea     rcx, [rbp+57h+var_60]
0x1800a82bb  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1800a82c0  nop
0x1800a82c1  lea     rcx, [rsp+100h+var_E0]
0x1800a82c6  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1800a82cb  lea     rax, [rbp+57h+var_A0]
0x1800a82cf  mov     [rbp+57h+arg_0], rax
0x1800a82d3  mov     rdi, [rdi+8]
0x1800a82d7  add     rdi, 160h
0x1800a82de  mov     [rbp+57h+arg_10], rdi
0x1800a82e2  mov     rcx, rdi
0x1800a82e5  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1800a82eb  nop
0x1800a82ec  mov     rcx, [rbp+57h+var_68]
0x1800a82f0  test    rcx, rcx
0x1800a82f3  jnz     short loc_1800A82FC
0x1800a82f5  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800a82fb  int     3; Trap to Debugger
0x1800a82fc  mov     rax, [rcx]
0x1800a82ff  mov     rax, [rax+10h]
0x1800a8303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8308  mov     bl, al
0x1800a830a  mov     rcx, rdi
0x1800a830d  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1800a8313  nop
0x1800a8314  mov     rcx, [rbp+57h+var_68]
0x1800a8318  test    rcx, rcx
0x1800a831b  jz      short loc_1800A833B
0x1800a831d  mov     rax, [rcx]
0x1800a8320  lea     rdx, [rbp+57h+var_A0]
0x1800a8324  cmp     rcx, rdx
0x1800a8327  setnz   dl
0x1800a832a  mov     rax, [rax+20h]
0x1800a832e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8333  mov     [rbp+57h+var_68], 0
0x1800a833b  mov     [rsi+170h], bl
0x1800a8341  lea     rbx, [rsi+20h]
0x1800a8345  mov     rcx, rbx; this
0x1800a8348  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a834d  mov     eax, [rsi+8]
0x1800a8350  mov     rcx, rbx; _Mtx_t
0x1800a8353  cmp     eax, 4
0x1800a8356  jnz     short loc_1800A8360
0x1800a8358  call    cs:__imp__Mtx_unlock
0x1800a835e  jmp     short loc_1800A83AB
0x1800a8360  mov     dword ptr [rsi+8], 3
0x1800a8367  call    cs:__imp__Mtx_unlock
0x1800a836d  lea     rbx, [rsi+88h]
0x1800a8374  lea     rcx, [rbx+48h]; this
0x1800a8378  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a837d  cmp     dword ptr [rbx+0B0h], 2
0x1800a8384  jge     short loc_1800A8390
0x1800a8386  mov     dword ptr [rbx+0B0h], 2
0x1800a8390  mov     rcx, rbx; _Cnd_t
0x1800a8393  call    cs:__imp__Cnd_broadcast
0x1800a8399  lea     rcx, [rbx+48h]; _Mtx_t
0x1800a839d  call    cs:__imp__Mtx_unlock
0x1800a83a3  mov     rcx, rsi; this
0x1800a83a6  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x1800a83ab  add     rsp, 0E8h
0x1800a83b2  pop     rdi
0x1800a83b3  pop     rsi
0x1800a83b4  pop     rbx
0x1800a83b5  pop     rbp
0x1800a83b6  retn
```
