# NsiNotifications::NotificationTracking::StartNotifications(void)

- ea: `0x180035a84`
- end: `0x180035b1a`
- name: `?StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(NsiNotifications::NotificationTracking *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033ce8`

## callees

- `0x18000f094`
- `0x180031860`
- `0x180031918`
- `0x180035a84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035aa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035aa4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180035b00`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180035b00`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NsiNotifications::NotificationTracking::StartNotifications(
        NsiNotifications::NotificationTracking *this)
{
  NsiNotifications::NotificationTracking *v1; // rdi
  char *v2; // rbx
  const char *v3; // r9
  __int64 result; // rax
  NsiNotifications::NotificationTracking *v5; // [rsp+20h] [rbp-18h] BYREF
  _QWORD v6[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = DusmEthernet::s_pInstance;
  v5 = DusmEthernet::s_pInstance;
  v2 = (char *)DusmEthernet::s_pInstance + 1632;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)DusmEthernet::s_pInstance + 1632));
  try
  {
    v6[0] = v2;
    if ( *((_BYTE *)v1 + 1896) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v6);
    }
    else
    {
      if ( *((_DWORD *)v1 + 406) == 1 )
        ___emplace_back_V_lambda_1___2__StartNotifications_NotificationTracking_NsiNotifications__QEAAJXZ____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_1___2__StartNotifications_NotificationTracking_NsiNotifications__QEAAJXZ__Z(
          (char *)v1 + 1776,
          &v5);
      else
        ___emplace_back_V_lambda_1___2__StartNotifications_NotificationTracking_NsiNotifications__QEAAJXZ____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_1___2__StartNotifications_NotificationTracking_NsiNotifications__QEAAJXZ__Z(
          (_QWORD *)v1 + 232,
          &v5);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v6);
      _InterlockedIncrement64((volatile signed __int64 *)v1 + 220);
      SubmitThreadpoolWork(*((PTP_WORK *)v1 + 219));
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x36E,
                           (unsigned int)"OneCore\\Private\\Net\\inc\\nsinotificationtracking.h",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x180035a84  mov     [rsp+arg_0], rbx
0x180035a89  push    rdi
0x180035a8a  sub     rsp, 30h
0x180035a8e  mov     rdi, cs:?s_pInstance@DusmEthernet@@0PEAV1@EA; DusmEthernet * DusmEthernet::s_pInstance
0x180035a95  mov     [rsp+38h+var_18], rdi
0x180035a9a  lea     rbx, [rdi+660h]
0x180035aa1  mov     rcx, rbx; lpCriticalSection
0x180035aa4  call    cs:__imp_EnterCriticalSection
0x180035aaa  mov     [rsp+38h+var_10], rbx
0x180035aaf  lea     rcx, [rdi+6F0h]
0x180035ab6  cmp     byte ptr [rcx+78h], 0
0x180035aba  jz      short loc_180035AC8
0x180035abc  lea     rcx, [rsp+38h+var_10]
0x180035ac1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180035ac6  jmp     short loc_180035B06
0x180035ac8  lea     rdx, [rsp+38h+var_18]
0x180035acd  cmp     dword ptr [rdi+658h], 1
0x180035ad4  jnz     short loc_180035ADD
0x180035ad6  call    ??$emplace_back@V_lambda_1_@?2??StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_1_@?2??StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ@@Z; std::deque<std::function<void (void)>>::emplace_back<`NsiNotifications::NotificationTracking::StartNotifications(void)'::`3'::_lambda_1_>(`NsiNotifications::NotificationTracking::StartNotifications(void)'::`3'::_lambda_1_ &&)
0x180035adb  jmp     short loc_180035AE7
0x180035add  add     rcx, 50h ; 'P'
0x180035ae1  call    ??$emplace_back@V_lambda_1_@?2??StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_1_@?2??StartNotifications@NotificationTracking@NsiNotifications@@QEAAJXZ@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<`NsiNotifications::NotificationTracking::StartNotifications(void)'::`3'::_lambda_1_>(`NsiNotifications::NotificationTracking::StartNotifications(void)'::`3'::_lambda_1_ &&)
0x180035ae6  nop
0x180035ae7  lea     rcx, [rsp+38h+var_10]
0x180035aec  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180035af1  lock inc qword ptr [rdi+6E0h]
0x180035af9  mov     rcx, [rdi+6D8h]; pwk
0x180035b00  call    cs:__imp_SubmitThreadpoolWork
0x180035b06  xor     eax, eax
0x180035b08  jmp     short loc_180035B0E
0x180035b0a  mov     eax, dword ptr [rsp+38h+var_18]
0x180035b0e  mov     rbx, [rsp+38h+arg_0]
0x180035b13  add     rsp, 30h
0x180035b17  pop     rdi
0x180035b18  retn
```
