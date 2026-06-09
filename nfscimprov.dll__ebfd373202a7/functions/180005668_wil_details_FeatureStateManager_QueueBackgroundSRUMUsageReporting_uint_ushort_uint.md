# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180005668`
- end: `0x180005757`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180007250`

## callees

- `0x180003118`
- `0x180003374`
- `0x180003640`
- `0x180003c74`
- `0x180005634`
- `0x180005668`
- `0x180007e30`
- `0x180007f3c`
- `0x180035b40`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800056ab`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800056ab`
- `KERNEL32!CreateThreadpoolTimer` at `0x180005707`
- `KERNEL32!CreateThreadpoolTimer` at `0x180005707`

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
  char *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

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
0x180005668  push    rbx
0x18000566a  push    rbp
0x18000566b  push    rsi
0x18000566c  push    rdi
0x18000566d  push    r14
0x18000566f  sub     rsp, 50h
0x180005673  mov     rax, cs:__security_cookie
0x18000567a  xor     rax, rsp
0x18000567d  mov     [rsp+78h+var_38], rax
0x180005682  mov     r14d, r9d
0x180005685  movzx   ebp, r8w
0x180005689  mov     esi, edx
0x18000568b  mov     rdi, rcx
0x18000568e  cmp     byte ptr [rcx], 0
0x180005691  jz      loc_18000573F
0x180005697  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000569c  test    al, al
0x18000569e  jnz     loc_18000573F
0x1800056a4  lea     rbx, [rdi+28h]
0x1800056a8  mov     rcx, rbx; SRWLock
0x1800056ab  call    cs:__imp_AcquireSRWLockExclusive
0x1800056b1  mov     [rsp+78h+var_50], rbx
0x1800056b6  xor     eax, eax
0x1800056b8  mov     [rsp+78h+var_42], ax
0x1800056bd  mov     [rsp+78h+var_48], esi
0x1800056c1  mov     [rsp+78h+var_44], bp
0x1800056c6  mov     [rsp+78h+var_40], r14d
0x1800056cb  lea     rcx, [rdi+0E8h]; this
0x1800056d2  lea     r8d, [rax+0Ch]; unsigned __int64
0x1800056d6  lea     rdx, [rsp+78h+var_48]; void *
0x1800056db  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800056e0  cmp     byte ptr [rdi+40h], 0
0x1800056e4  jnz     short loc_180005734
0x1800056e6  lea     rbx, [rdi+38h]
0x1800056ea  cmp     qword ptr [rbx], 0
0x1800056ee  jnz     short loc_180005722
0x1800056f0  lea     rcx, [rsp+78h+var_58]; this
0x1800056f5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800056fa  xor     r8d, r8d; pcbe
0x1800056fd  mov     rdx, rdi; pv
0x180005700  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005707  call    cs:__imp_CreateThreadpoolTimer
0x18000570d  mov     rdx, rax
0x180005710  mov     rcx, rbx
0x180005713  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005718  lea     rcx, [rsp+78h+var_58]; this
0x18000571d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180005722  mov     r8d, 1388h
0x180005728  lea     rdx, [rdi+40h]
0x18000572c  mov     rcx, rbx
0x18000572f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180005734  lea     rcx, [rsp+78h+var_50]
0x180005739  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000573e  nop
0x18000573f  mov     rcx, [rsp+78h+var_38]
0x180005744  xor     rcx, rsp; StackCookie
0x180005747  call    __security_check_cookie
0x18000574c  add     rsp, 50h
0x180005750  pop     r14
0x180005752  pop     rdi
0x180005753  pop     rsi
0x180005754  pop     rbp
0x180005755  pop     rbx
0x180005756  retn
```
