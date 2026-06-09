# wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)

- ea: `0x1800029a0`
- end: `0x180002a18`
- name: `??$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180005d50`

## callees

- `0x1800029a0`
- `0x180003504`
- `0x180003b60`
- `0x1800041b0`
- `0x180007f64`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1800029db`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800029db`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(
        _QWORD *a1,
        _BYTE *a2,
        void *a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a2 )
  {
    if ( !*a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, a3, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        a1,
        ThreadpoolTimer);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
    }
    wil::details::EnsureCoalescedTimer_SetTimer(a1, a2, 5000);
  }
}

```

## disassembly

```asm
0x1800029a0  mov     [rsp+arg_0], rbx
0x1800029a5  mov     [rsp+arg_10], rsi
0x1800029aa  push    rdi
0x1800029ab  sub     rsp, 20h
0x1800029af  mov     rsi, r8
0x1800029b2  mov     rdi, rdx
0x1800029b5  mov     rbx, rcx
0x1800029b8  cmp     byte ptr [rdx], 0
0x1800029bb  jnz     short loc_180002A08
0x1800029bd  cmp     qword ptr [rcx], 0
0x1800029c1  jnz     short loc_1800029F7
0x1800029c3  lea     rcx, [rsp+28h+arg_8]; this
0x1800029c8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800029cd  nop
0x1800029ce  xor     r8d, r8d; pcbe
0x1800029d1  mov     rdx, rsi; pv
0x1800029d4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800029db  call    cs:__imp_CreateThreadpoolTimer
0x1800029e1  mov     rdx, rax
0x1800029e4  mov     rcx, rbx
0x1800029e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800029ec  nop
0x1800029ed  lea     rcx, [rsp+28h+arg_8]; this
0x1800029f2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800029f7  mov     r8d, 1388h
0x1800029fd  mov     rdx, rdi
0x180002a00  mov     rcx, rbx
0x180002a03  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180002a08  mov     rbx, [rsp+28h+arg_0]
0x180002a0d  mov     rsi, [rsp+28h+arg_10]
0x180002a12  add     rsp, 20h
0x180002a16  pop     rdi
0x180002a17  retn
```
