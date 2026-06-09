# wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)

- ea: `0x180021810`
- end: `0x1800218a3`
- name: `??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003cbec`

## callees

- `0x180021810`
- `0x1800218ac`
- `0x1800218cc`
- `0x1800218f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002188a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002188a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002184a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002184a`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
        struct _TP_TIMER **a1,
        _BYTE *a2,
        void *a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v7; // rcx
  _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a2 )
  {
    if ( !*a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&pftDueTime);
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_, a3, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        a1,
        ThreadpoolTimer);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&pftDueTime);
    }
    v7 = *a1;
    if ( *a1 )
    {
      pftDueTime = (_FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x180021810  mov     [rsp+arg_0], rbx
0x180021815  mov     [rsp+arg_10], rsi
0x18002181a  push    rdi
0x18002181b  sub     rsp, 20h
0x18002181f  cmp     byte ptr [rdx], 0
0x180021822  mov     rsi, r8
0x180021825  mov     rdi, rdx
0x180021828  mov     rbx, rcx
0x18002182b  jnz     short loc_180021893
0x18002182d  cmp     qword ptr [rcx], 0
0x180021831  jnz     short loc_180021865
0x180021833  lea     rcx, [rsp+28h+pftDueTime]; this
0x180021838  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002183d  xor     r8d, r8d; pcbe
0x180021840  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180021847  mov     rdx, rsi; pv
0x18002184a  call    cs:__imp_CreateThreadpoolTimer
0x180021850  mov     rdx, rax
0x180021853  mov     rcx, rbx
0x180021856  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002185b  lea     rcx, [rsp+28h+pftDueTime]; this
0x180021860  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180021865  mov     rcx, [rbx]; pti
0x180021868  test    rcx, rcx
0x18002186b  jz      short loc_180021893
0x18002186d  mov     rax, 0FFFFFFFF4D2FA200h
0x180021877  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18002187c  mov     r9d, 124F8h; msWindowLength
0x180021882  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180021887  xor     r8d, r8d; msPeriod
0x18002188a  call    cs:__imp_SetThreadpoolTimer
0x180021890  mov     byte ptr [rdi], 1
0x180021893  mov     rbx, [rsp+28h+arg_0]
0x180021898  mov     rsi, [rsp+28h+arg_10]
0x18002189d  add     rsp, 20h
0x1800218a1  pop     rdi
0x1800218a2  retn
```
