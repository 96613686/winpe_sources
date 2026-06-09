# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180005738`
- end: `0x180005827`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180007270`

## callees

- `0x1800031c4`
- `0x180003484`
- `0x180003760`
- `0x180003da4`
- `0x180005704`
- `0x180005738`
- `0x180007eb0`
- `0x180007fbc`
- `0x18001a5e0`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1800057d7`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800057d7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000577b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000577b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180005738  push    rbx
0x18000573a  push    rbp
0x18000573b  push    rsi
0x18000573c  push    rdi
0x18000573d  push    r14
0x18000573f  sub     rsp, 50h
0x180005743  mov     rax, cs:__security_cookie
0x18000574a  xor     rax, rsp
0x18000574d  mov     [rsp+78h+var_38], rax
0x180005752  mov     r14d, r9d
0x180005755  movzx   ebp, r8w
0x180005759  mov     esi, edx
0x18000575b  mov     rdi, rcx
0x18000575e  cmp     byte ptr [rcx], 0
0x180005761  jz      loc_18000580F
0x180005767  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000576c  test    al, al
0x18000576e  jnz     loc_18000580F
0x180005774  lea     rbx, [rdi+28h]
0x180005778  mov     rcx, rbx; SRWLock
0x18000577b  call    cs:__imp_AcquireSRWLockExclusive
0x180005781  mov     [rsp+78h+var_50], rbx
0x180005786  xor     eax, eax
0x180005788  mov     [rsp+78h+var_42], ax
0x18000578d  mov     [rsp+78h+var_48], esi
0x180005791  mov     [rsp+78h+var_44], bp
0x180005796  mov     [rsp+78h+var_40], r14d
0x18000579b  lea     rcx, [rdi+0E8h]; this
0x1800057a2  lea     r8d, [rax+0Ch]; unsigned __int64
0x1800057a6  lea     rdx, [rsp+78h+var_48]; void *
0x1800057ab  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800057b0  cmp     byte ptr [rdi+40h], 0
0x1800057b4  jnz     short loc_180005804
0x1800057b6  lea     rbx, [rdi+38h]
0x1800057ba  cmp     qword ptr [rbx], 0
0x1800057be  jnz     short loc_1800057F2
0x1800057c0  lea     rcx, [rsp+78h+var_58]; this
0x1800057c5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800057ca  xor     r8d, r8d; pcbe
0x1800057cd  mov     rdx, rdi; pv
0x1800057d0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800057d7  call    cs:__imp_CreateThreadpoolTimer
0x1800057dd  mov     rdx, rax
0x1800057e0  mov     rcx, rbx
0x1800057e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800057e8  lea     rcx, [rsp+78h+var_58]; this
0x1800057ed  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800057f2  mov     r8d, 1388h
0x1800057f8  lea     rdx, [rdi+40h]
0x1800057fc  mov     rcx, rbx
0x1800057ff  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180005804  lea     rcx, [rsp+78h+var_50]
0x180005809  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000580e  nop
0x18000580f  mov     rcx, [rsp+78h+var_38]
0x180005814  xor     rcx, rsp; StackCookie
0x180005817  call    __security_check_cookie
0x18000581c  add     rsp, 50h
0x180005820  pop     r14
0x180005822  pop     rdi
0x180005823  pop     rsi
0x180005824  pop     rbp
0x180005825  pop     rbx
0x180005826  retn
```
