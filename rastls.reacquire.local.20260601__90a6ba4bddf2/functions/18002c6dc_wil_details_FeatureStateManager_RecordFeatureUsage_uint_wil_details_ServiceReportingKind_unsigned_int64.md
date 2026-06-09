# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18002c6dc`
- end: `0x18002c7af`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18001fca0`

## callees

- `0x18001fdf4`
- `0x180020d40`
- `0x18002c6dc`
- `0x18002c88c`
- `0x18002c8b0`
- `0x18002c8f8`
- `0x18002c91c`
- `0x18003b60c`
- `0x18003cda4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c72f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c72f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002c767`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002c767`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v10; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    v10 = a1 + 4;
    if ( !BYTE1(a1[8].Ptr) )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18002c6dc  push    rbx
0x18002c6de  push    rbp
0x18002c6df  push    rsi
0x18002c6e0  push    rdi
0x18002c6e1  sub     rsp, 38h
0x18002c6e5  mov     rbx, r9
0x18002c6e8  mov     esi, r8d
0x18002c6eb  mov     ebp, edx
0x18002c6ed  mov     rdi, rcx
0x18002c6f0  cmp     byte ptr [rcx], 0
0x18002c6f3  jz      loc_18002C7A5
0x18002c6f9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002c6fe  test    al, al
0x18002c700  jz      loc_18002C7A5
0x18002c706  mov     r9, rbx
0x18002c709  mov     r8d, esi
0x18002c70c  mov     edx, ebp
0x18002c70e  mov     rcx, [rdi+18h]
0x18002c712  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18002c717  test    al, al
0x18002c719  jz      loc_18002C7A5
0x18002c71f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002c724  test    al, al
0x18002c726  jnz     short loc_18002C7A5
0x18002c728  lea     rbx, [rdi+20h]
0x18002c72c  mov     rcx, rbx; SRWLock
0x18002c72f  call    cs:__imp_AcquireSRWLockExclusive
0x18002c736  nop     dword ptr [rax+rax+00h]
0x18002c73b  mov     [rsp+58h+var_38], rbx
0x18002c740  cmp     byte ptr [rdi+41h], 0
0x18002c744  jnz     short loc_18002C79A
0x18002c746  lea     rbx, [rdi+30h]
0x18002c74a  cmp     qword ptr [rbx], 0
0x18002c74e  jnz     short loc_18002C788
0x18002c750  lea     rcx, [rsp+58h+arg_0]; this
0x18002c755  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002c75a  xor     r8d, r8d; pcbe
0x18002c75d  mov     rdx, rdi; pv
0x18002c760  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002c767  call    cs:__imp_CreateThreadpoolTimer
0x18002c76e  nop     dword ptr [rax+rax+00h]
0x18002c773  mov     rdx, rax
0x18002c776  mov     rcx, rbx
0x18002c779  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002c77e  lea     rcx, [rsp+58h+arg_0]; this
0x18002c783  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002c788  mov     r8d, 493E0h
0x18002c78e  lea     rdx, [rdi+41h]
0x18002c792  mov     rcx, rbx
0x18002c795  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002c79a  lea     rcx, [rsp+58h+var_38]
0x18002c79f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002c7a4  nop
0x18002c7a5  add     rsp, 38h
0x18002c7a9  pop     rdi
0x18002c7aa  pop     rsi
0x18002c7ab  pop     rbp
0x18002c7ac  pop     rbx
0x18002c7ad  retn
```
