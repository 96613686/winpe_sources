# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800358b4`
- end: `0x1800359a2`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800523a0`

## callees

- `0x1800358b4`
- `0x180035a70`
- `0x180035a90`
- `0x180035ad4`
- `0x180035af4`
- `0x180035b18`
- `0x180035c40`
- `0x18004e28c`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800358f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800358f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180035953`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180035953`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  RTL_SRWLOCK *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = (RTL_SRWLOCK *)(pv + 40);
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v11, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x1800358b4  push    rbx
0x1800358b6  push    rbp
0x1800358b7  push    rsi
0x1800358b8  push    rdi
0x1800358b9  push    r14
0x1800358bb  sub     rsp, 50h
0x1800358bf  mov     rax, cs:__security_cookie
0x1800358c6  xor     rax, rsp
0x1800358c9  mov     [rsp+78h+var_38], rax
0x1800358ce  cmp     byte ptr [rcx], 0
0x1800358d1  mov     r14d, r9d
0x1800358d4  movzx   ebp, r8w
0x1800358d8  mov     esi, edx
0x1800358da  mov     rdi, rcx
0x1800358dd  jz      loc_18003598A
0x1800358e3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800358e8  test    al, al
0x1800358ea  jnz     loc_18003598A
0x1800358f0  lea     rbx, [rdi+28h]
0x1800358f4  mov     rcx, rbx; SRWLock
0x1800358f7  call    cs:__imp_AcquireSRWLockExclusive
0x1800358fd  xor     eax, eax
0x1800358ff  mov     [rsp+78h+var_50], rbx
0x180035904  lea     rcx, [rdi+0E8h]; this
0x18003590b  mov     [rsp+78h+var_42], ax
0x180035910  lea     rdx, [rsp+78h+var_48]; void *
0x180035915  mov     [rsp+78h+var_48], esi
0x180035919  mov     [rsp+78h+var_44], bp
0x18003591e  lea     r8d, [rax+0Ch]; unsigned __int64
0x180035922  mov     [rsp+78h+var_40], r14d
0x180035927  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003592c  cmp     byte ptr [rdi+40h], 0
0x180035930  jnz     short loc_180035980
0x180035932  lea     rbx, [rdi+38h]
0x180035936  cmp     qword ptr [rbx], 0
0x18003593a  jnz     short loc_18003596E
0x18003593c  lea     rcx, [rsp+78h+var_58]; this
0x180035941  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180035946  xor     r8d, r8d; pcbe
0x180035949  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180035950  mov     rdx, rdi; pv
0x180035953  call    cs:__imp_CreateThreadpoolTimer
0x180035959  mov     rdx, rax
0x18003595c  mov     rcx, rbx
0x18003595f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180035964  lea     rcx, [rsp+78h+var_58]; this
0x180035969  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003596e  mov     r8d, 1388h
0x180035974  lea     rdx, [rdi+40h]
0x180035978  mov     rcx, rbx
0x18003597b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180035980  lea     rcx, [rsp+78h+var_50]
0x180035985  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003598a  mov     rcx, [rsp+78h+var_38]
0x18003598f  xor     rcx, rsp; StackCookie
0x180035992  call    __security_check_cookie
0x180035997  add     rsp, 50h
0x18003599b  pop     r14
0x18003599d  pop     rdi
0x18003599e  pop     rsi
0x18003599f  pop     rbp
0x1800359a0  pop     rbx
0x1800359a1  retn
```
