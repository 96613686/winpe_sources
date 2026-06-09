# wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)

- ea: `0x180002920`
- end: `0x180002998`
- name: `??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800060dc`

## callees

- `0x180002920`
- `0x180003504`
- `0x180003b60`
- `0x1800041b0`
- `0x180007f64`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18000295b`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000295b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(_QWORD *a1, _BYTE *a2, void *a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a2 )
  {
    if ( !*a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, a3, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        a1,
        ThreadpoolTimer);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
    }
    wil::details::EnsureCoalescedTimer_SetTimer(a1, a2, 300000);
  }
}

```

## disassembly

```asm
0x180002920  mov     [rsp+arg_0], rbx
0x180002925  mov     [rsp+arg_10], rsi
0x18000292a  push    rdi
0x18000292b  sub     rsp, 20h
0x18000292f  mov     rsi, r8
0x180002932  mov     rdi, rdx
0x180002935  mov     rbx, rcx
0x180002938  cmp     byte ptr [rdx], 0
0x18000293b  jnz     short loc_180002988
0x18000293d  cmp     qword ptr [rcx], 0
0x180002941  jnz     short loc_180002977
0x180002943  lea     rcx, [rsp+28h+arg_8]; this
0x180002948  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000294d  nop
0x18000294e  xor     r8d, r8d; pcbe
0x180002951  mov     rdx, rsi; pv
0x180002954  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000295b  call    cs:__imp_CreateThreadpoolTimer
0x180002961  mov     rdx, rax
0x180002964  mov     rcx, rbx
0x180002967  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000296c  nop
0x18000296d  lea     rcx, [rsp+28h+arg_8]; this
0x180002972  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180002977  mov     r8d, 493E0h
0x18000297d  mov     rdx, rdi
0x180002980  mov     rcx, rbx
0x180002983  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180002988  mov     rbx, [rsp+28h+arg_0]
0x18000298d  mov     rsi, [rsp+28h+arg_10]
0x180002992  add     rsp, 20h
0x180002996  pop     rdi
0x180002997  retn
```
