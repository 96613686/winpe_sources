# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800033fc`
- end: `0x1800034eb`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009620`

## callees

- `0x1800033fc`
- `0x1800035bc`
- `0x1800035dc`
- `0x180003620`
- `0x180003640`
- `0x180003664`
- `0x18000378c`
- `0x180009e1c`
- `0x18000ad30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000343f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000343f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000349b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000349b`

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
0x1800033fc  push    rbx
0x1800033fe  push    rbp
0x1800033ff  push    rsi
0x180003400  push    rdi
0x180003401  push    r14
0x180003403  sub     rsp, 50h
0x180003407  mov     rax, cs:__security_cookie
0x18000340e  xor     rax, rsp
0x180003411  mov     [rsp+78h+var_38], rax
0x180003416  mov     r14d, r9d
0x180003419  movzx   ebp, r8w
0x18000341d  mov     esi, edx
0x18000341f  mov     rdi, rcx
0x180003422  cmp     byte ptr [rcx], 0
0x180003425  jz      loc_1800034D3
0x18000342b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180003430  test    al, al
0x180003432  jnz     loc_1800034D3
0x180003438  lea     rbx, [rdi+28h]
0x18000343c  mov     rcx, rbx; SRWLock
0x18000343f  call    cs:__imp_AcquireSRWLockExclusive
0x180003445  mov     [rsp+78h+var_50], rbx
0x18000344a  xor     eax, eax
0x18000344c  mov     [rsp+78h+var_42], ax
0x180003451  mov     [rsp+78h+var_48], esi
0x180003455  mov     [rsp+78h+var_44], bp
0x18000345a  mov     [rsp+78h+var_40], r14d
0x18000345f  lea     rcx, [rdi+0E8h]; this
0x180003466  lea     r8d, [rax+0Ch]; unsigned __int64
0x18000346a  lea     rdx, [rsp+78h+var_48]; void *
0x18000346f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180003474  cmp     byte ptr [rdi+40h], 0
0x180003478  jnz     short loc_1800034C8
0x18000347a  lea     rbx, [rdi+38h]
0x18000347e  cmp     qword ptr [rbx], 0
0x180003482  jnz     short loc_1800034B6
0x180003484  lea     rcx, [rsp+78h+var_58]; this
0x180003489  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000348e  xor     r8d, r8d; pcbe
0x180003491  mov     rdx, rdi; pv
0x180003494  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000349b  call    cs:__imp_CreateThreadpoolTimer
0x1800034a1  mov     rdx, rax
0x1800034a4  mov     rcx, rbx
0x1800034a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800034ac  lea     rcx, [rsp+78h+var_58]; this
0x1800034b1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800034b6  mov     r8d, 1388h
0x1800034bc  lea     rdx, [rdi+40h]
0x1800034c0  mov     rcx, rbx
0x1800034c3  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800034c8  lea     rcx, [rsp+78h+var_50]
0x1800034cd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800034d2  nop
0x1800034d3  mov     rcx, [rsp+78h+var_38]
0x1800034d8  xor     rcx, rsp; StackCookie
0x1800034db  call    __security_check_cookie
0x1800034e0  add     rsp, 50h
0x1800034e4  pop     r14
0x1800034e6  pop     rdi
0x1800034e7  pop     rsi
0x1800034e8  pop     rbp
0x1800034e9  pop     rbx
0x1800034ea  retn
```
