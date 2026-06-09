# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14002d5d0`
- end: `0x14002d6d0`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `256`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140031850`

## callees

- `0x1400276dc`
- `0x140027984`
- `0x140027c54`
- `0x140029f8c`
- `0x14002d598`
- `0x14002d5d0`
- `0x140031d7c`
- `0x140031eac`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002d618`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002d618`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14002d678`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14002d678`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-68h] BYREF
  char *v10; // [rsp+28h] [rbp-60h] BYREF
  int v11; // [rsp+30h] [rbp-58h] BYREF
  __int16 v12; // [rsp+34h] [rbp-54h]
  __int16 v13; // [rsp+36h] [rbp-52h]
  int v14; // [rsp+38h] [rbp-50h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = pv + 40;
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
0x14002d5d0  push    rbx
0x14002d5d2  push    rbp
0x14002d5d3  push    rsi
0x14002d5d4  push    rdi
0x14002d5d5  push    r14
0x14002d5d7  push    r15
0x14002d5d9  sub     rsp, 58h
0x14002d5dd  mov     rax, cs:__security_cookie
0x14002d5e4  xor     rax, rsp
0x14002d5e7  mov     [rsp+88h+var_48], rax
0x14002d5ec  xor     r15d, r15d
0x14002d5ef  mov     r14d, r9d
0x14002d5f2  movzx   ebp, r8w
0x14002d5f6  mov     esi, edx
0x14002d5f8  mov     rdi, rcx
0x14002d5fb  cmp     [rcx], r15b
0x14002d5fe  jz      loc_14002D6B5
0x14002d604  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14002d609  test    al, al
0x14002d60b  jnz     loc_14002D6B5
0x14002d611  lea     rbx, [rdi+28h]
0x14002d615  mov     rcx, rbx; SRWLock
0x14002d618  call    cs:__imp_AcquireSRWLockExclusive
0x14002d61f  nop     dword ptr [rax+rax+00h]
0x14002d624  lea     rcx, [rdi+0E8h]; this
0x14002d62b  mov     [rsp+88h+var_60], rbx
0x14002d630  lea     r8d, [r15+0Ch]; unsigned __int64
0x14002d634  mov     [rsp+88h+var_52], r15w
0x14002d63a  lea     rdx, [rsp+88h+var_58]; void *
0x14002d63f  mov     [rsp+88h+var_58], esi
0x14002d643  mov     [rsp+88h+var_54], bp
0x14002d648  mov     [rsp+88h+var_50], r14d
0x14002d64d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14002d652  lea     rbx, [rdi+38h]
0x14002d656  cmp     [rdi+40h], r15b
0x14002d65a  jnz     short loc_14002D6AB
0x14002d65c  cmp     [rbx], r15
0x14002d65f  jnz     short loc_14002D699
0x14002d661  lea     rcx, [rsp+88h+var_68]; this
0x14002d666  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14002d66b  xor     r8d, r8d; pcbe
0x14002d66e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14002d675  mov     rdx, rdi; pv
0x14002d678  call    cs:__imp_CreateThreadpoolTimer
0x14002d67f  nop     dword ptr [rax+rax+00h]
0x14002d684  mov     rdx, rax
0x14002d687  mov     rcx, rbx
0x14002d68a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14002d68f  lea     rcx, [rsp+88h+var_68]; this
0x14002d694  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14002d699  mov     r8d, 1388h
0x14002d69f  lea     rdx, [rdi+40h]
0x14002d6a3  mov     rcx, rbx
0x14002d6a6  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14002d6ab  lea     rcx, [rsp+88h+var_60]
0x14002d6b0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14002d6b5  mov     rcx, [rsp+88h+var_48]
0x14002d6ba  xor     rcx, rsp; StackCookie
0x14002d6bd  call    __security_check_cookie
0x14002d6c2  add     rsp, 58h
0x14002d6c6  pop     r15
0x14002d6c8  pop     r14
0x14002d6ca  pop     rdi
0x14002d6cb  pop     rsi
0x14002d6cc  pop     rbp
0x14002d6cd  pop     rbx
0x14002d6ce  retn
```
