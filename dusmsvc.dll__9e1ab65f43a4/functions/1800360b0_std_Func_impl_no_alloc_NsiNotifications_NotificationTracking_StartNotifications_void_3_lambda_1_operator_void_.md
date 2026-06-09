# std::_Func_impl_no_alloc<``NsiNotifications::NotificationTracking::StartNotifications(void)'::`3'::_lambda_1_::operator()(void)'::`3'::_lambda_1_,void,>::_Do_call(void)

- ea: `0x1800360b0`
- end: `0x18003613a`
- name: `?_Do_call@?$_Func_impl_no_alloc@V_lambda_1_@?2???R1?2??StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ@QEBA@XZ@X$$V@std@@EEAAXXZ`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f094`
- `0x180031578`
- `0x180031630`
- `0x1800360b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800360cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800360cd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180036129`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180036129`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __Do_call____Func_impl_no_alloc_V_lambda_1___2___R1_2__StartNotifications_NotificationTracking_NsiNotifications__QEAAJXZ_QEBA_XZ_X__V_std__EEAAXXZ(
        __int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // [rsp+20h] [rbp-18h] BYREF
  _QWORD v3[2]; // [rsp+28h] [rbp-10h] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  v2 = v1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 1632));
  v3[0] = v1 + 1632;
  if ( *(_BYTE *)(v1 + 1896) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v3);
  }
  else
  {
    if ( *(_DWORD *)(v1 + 1624) == 1 )
      ___emplace_back_V_lambda_1___1___R1_2___R1_2__StartNotifications_NotificationTracking_NsiNotifications__QEAAJXZ_QEBA_XZ_QEBA_XZ____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_1___1___R3_2___R3_2__StartNotifications_NotificationTracking_NsiNotifications__QEAAJXZ_QEBA_XZ_QEBA_XZ__Z(
        v1 + 1776,
        &v2);
    else
      ___emplace_back_V_lambda_1___1___R1_2___R1_2__StartNotifications_NotificationTracking_NsiNotifications__QEAAJXZ_QEBA_XZ_QEBA_XZ____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_1___1___R3_2___R3_2__StartNotifications_NotificationTracking_NsiNotifications__QEAAJXZ_QEBA_XZ_QEBA_XZ__Z(
        (_QWORD *)(v1 + 1856),
        &v2);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v3);
    _InterlockedIncrement64((volatile signed __int64 *)(v1 + 1760));
    SubmitThreadpoolWork(*(PTP_WORK *)(v1 + 1752));
  }
}

```

## disassembly

```asm
0x1800360b0  mov     [rsp+arg_8], rbx
0x1800360b5  push    rdi
0x1800360b6  sub     rsp, 30h
0x1800360ba  mov     rdi, [rcx+8]
0x1800360be  mov     [rsp+38h+var_18], rdi
0x1800360c3  lea     rbx, [rdi+660h]
0x1800360ca  mov     rcx, rbx; lpCriticalSection
0x1800360cd  call    cs:__imp_EnterCriticalSection
0x1800360d3  mov     [rsp+38h+var_10], rbx
0x1800360d8  lea     rcx, [rdi+6F0h]
0x1800360df  cmp     byte ptr [rcx+78h], 0
0x1800360e3  jz      short loc_1800360F1
0x1800360e5  lea     rcx, [rsp+38h+var_10]
0x1800360ea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800360ef  jmp     short loc_18003612F
0x1800360f1  lea     rdx, [rsp+38h+var_18]
0x1800360f6  cmp     dword ptr [rdi+658h], 1
0x1800360fd  jnz     short loc_180036106
0x1800360ff  call    ??$emplace_back@V_lambda_1_@?1???R1?2???R1?2??StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ@QEBA@XZ@QEBA@XZ@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_1_@?1???R3?2???R3?2??StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ@QEBA@XZ@QEBA@XZ@@Z; std::deque<std::function<void (void)>>::emplace_back<```NsiNotifications::NotificationTracking::StartNotifications(void)'::`3'::_lambda_1_::operator()(void)'::`3'::_lambda_1_::operator()(void)'::`2'::_lambda_1_>(```NsiNotifications::NotificationTracking::StartNotifications(void)'::`3'::_lambda_1_::operator()(void)'::`3'::_lambda_1_::operator()(void)'::`2'::_lambda_1_ &&)
0x180036104  jmp     short loc_180036110
0x180036106  add     rcx, 50h ; 'P'
0x18003610a  call    ??$emplace_back@V_lambda_1_@?1???R1?2???R1?2??StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ@QEBA@XZ@QEBA@XZ@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_1_@?1???R3?2???R3?2??StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ@QEBA@XZ@QEBA@XZ@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<```NsiNotifications::NotificationTracking::StartNotifications(void)'::`3'::_lambda_1_::operator()(void)'::`3'::_lambda_1_::operator()(void)'::`2'::_lambda_1_>(```NsiNotifications::NotificationTracking::StartNotifications(void)'::`3'::_lambda_1_::operator()(void)'::`3'::_lambda_1_::operator()(void)'::`2'::_lambda_1_ &&)
0x18003610f  nop
0x180036110  lea     rcx, [rsp+38h+var_10]
0x180036115  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003611a  lock inc qword ptr [rdi+6E0h]
0x180036122  mov     rcx, [rdi+6D8h]; pwk
0x180036129  call    cs:__imp_SubmitThreadpoolWork
0x18003612f  mov     rbx, [rsp+38h+arg_8]
0x180036134  add     rsp, 30h
0x180036138  pop     rdi
0x180036139  retn
```
