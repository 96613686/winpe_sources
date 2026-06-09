# PublicNetworkListManager::ResetAddressInterfaceList(uint,NLM_SOCKADDR const *)

- ea: `0x1800293f0`
- end: `0x18002952d`
- name: `?ResetAddressInterfaceList@PublicNetworkListManager@@AEAAJIPEBUNLM_SOCKADDR@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, unsigned int, const struct NLM_SOCKADDR *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x1800299c0`
- `0x18002a294`

## callees

- `0x180009184`
- `0x180009d08`
- `0x18000c5d4`
- `0x18000c650`
- `0x1800120d0`
- `0x18001e678`
- `0x18001e968`
- `0x18001fb2c`
- `0x1800293f0`
- `0x18002a84c`

## string_xrefs

- `0x180029499`: `onecore\net\netprofiles\service\src\public\lib\networklistmanagerimpl.cpp`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::ResetAddressInterfaceList(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2,
        const struct NLM_SOCKADDR *a3)
{
  int v6; // eax
  __int64 v7; // r8
  int appended; // eax
  unsigned int v9; // ebx
  _QWORD v11[3]; // [rsp+20h] [rbp-40h] BYREF
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+38h] [rbp-28h] BYREF
  __int128 v13; // [rsp+40h] [rbp-20h] BYREF
  __int64 v14; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v14 = 0;
  v12 = 0;
  v13 = 0;
  wil::EnterCriticalSection(&v12, this + 14);
  if ( *(_QWORD *)&this[15].LockCount )
  {
    v11[0] = this;
    v11[1] = &v13;
    v11[2] = &v12;
    v6 = wil::ResultFromException__PublicNetworkListManager::ResetAddressInterfaceList_::_5_::_lambda_1___(v11);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x12A4, v7, (const char *)(unsigned int)v6);
  }
  if ( a2
    && a3
    && (appended = PublicNetworkListManager::AppendAddressInterfaceList((__int64)this, a2, (__int64)a3),
        v9 = appended,
        appended < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12A9,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\networklistmanagerimpl.cpp",
      (const char *)(unsigned int)appended,
      v11[0]);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v12);
    if ( (_QWORD)v13 )
    {
      ____Destroy_range_V__allocator_U__pair_V__unique_ptr_UADDRESS_INTERFACE_DATA__U__function_deleter_P6AXPEAX_Z_1_CoTaskMemFree__YAX0_Z_wil___wistd__V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseGetIPPhysicalInterfaceForDestination_PublicNetworkListManager__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___std___std___std__YAXPEAU__pair_V__unique_ptr_UADDRESS_INTERFACE_DATA__U__function_deleter_P6AXPEAX_Z_1_CoTaskMemFree__YAX0_Z_wil___wistd__V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseGetIPPhysicalInterfaceForDestination_PublicNetworkListManager__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___0_QEAU10_AEAV__allocator_U__pair_V__unique_ptr_UADDRESS_INTERFACE_DATA__U__function_deleter_P6AXPEAX_Z_1_CoTaskMemFree__YAX0_Z_wil___wistd__V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseGetIPPhysicalInterfaceForDestination_PublicNetworkListManager__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___std___0__Z(
        v13,
        *((__int64 *)&v13 + 1));
      std::_Deallocate<16>((void *)v13, (v14 - v13) & 0xFFFFFFFFFFFFFFF0uLL);
    }
    return v9;
  }
  else
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v12);
    if ( (_QWORD)v13 )
    {
      ____Destroy_range_V__allocator_U__pair_V__unique_ptr_UADDRESS_INTERFACE_DATA__U__function_deleter_P6AXPEAX_Z_1_CoTaskMemFree__YAX0_Z_wil___wistd__V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseGetIPPhysicalInterfaceForDestination_PublicNetworkListManager__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___std___std___std__YAXPEAU__pair_V__unique_ptr_UADDRESS_INTERFACE_DATA__U__function_deleter_P6AXPEAX_Z_1_CoTaskMemFree__YAX0_Z_wil___wistd__V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseGetIPPhysicalInterfaceForDestination_PublicNetworkListManager__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___0_QEAU10_AEAV__allocator_U__pair_V__unique_ptr_UADDRESS_INTERFACE_DATA__U__function_deleter_P6AXPEAX_Z_1_CoTaskMemFree__YAX0_Z_wil___wistd__V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseGetIPPhysicalInterfaceForDestination_PublicNetworkListManager__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___std___0__Z(
        v13,
        *((__int64 *)&v13 + 1));
      std::_Deallocate<16>((void *)v13, (v14 - v13) & 0xFFFFFFFFFFFFFFF0uLL);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800293f0  mov     [rsp-18h+arg_18], rbx
0x1800293f5  push    rbp
0x1800293f6  push    rsi
0x1800293f7  push    rdi
0x1800293f8  mov     rbp, rsp
0x1800293fb  sub     rsp, 60h
0x1800293ff  mov     rax, cs:__security_cookie
0x180029406  xor     rax, rsp
0x180029409  mov     [rbp+var_8], rax
0x18002940d  mov     edi, edx
0x18002940f  mov     [rbp+var_10], 0
0x180029417  lea     rdx, [rcx+230h]
0x18002941e  mov     [rbp+var_28], 0
0x180029426  mov     rbx, rcx
0x180029429  xorps   xmm0, xmm0
0x18002942c  lea     rcx, [rbp+var_28]
0x180029430  mov     rsi, r8
0x180029433  movdqu  [rbp+var_20], xmm0
0x180029438  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002943d  cmp     qword ptr [rbx+260h], 0
0x180029445  jz      short loc_180029479
0x180029447  lea     rax, [rbp+var_20]
0x18002944b  mov     [rbp+var_40], rbx
0x18002944f  mov     [rbp+var_38], rax
0x180029453  lea     rcx, [rbp+var_40]
0x180029457  lea     rax, [rbp+var_28]
0x18002945b  mov     [rbp+var_30], rax
0x18002945f  call    wil__ResultFromException__PublicNetworkListManager__ResetAddressInterfaceList____5____lambda_1___
0x180029464  test    eax, eax
0x180029466  jns     short loc_180029479
0x180029468  mov     rcx, [rbp+18h]; this
0x18002946c  mov     r9d, eax; char *
0x18002946f  mov     edx, 12A4h; void *
0x180029474  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029479  test    edi, edi
0x18002947b  jz      short loc_1800294E0
0x18002947d  test    rsi, rsi
0x180029480  jz      short loc_1800294E0
0x180029482  mov     r8, rsi
0x180029485  mov     edx, edi
0x180029487  mov     rcx, rbx
0x18002948a  call    ?AppendAddressInterfaceList@PublicNetworkListManager@@AEAAJIPEBUNLM_SOCKADDR@@Uwrite_lock_required@wil@@@Z; PublicNetworkListManager::AppendAddressInterfaceList(uint,NLM_SOCKADDR const *,wil::write_lock_required)
0x18002948f  mov     ebx, eax
0x180029491  test    eax, eax
0x180029493  jns     short loc_1800294E0
0x180029495  mov     rcx, [rbp+18h]; this
0x180029499  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x1800294a0  mov     r9d, eax; char *
0x1800294a3  mov     edx, 12A9h; void *
0x1800294a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800294ad  lea     rcx, [rbp+var_28]
0x1800294b1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800294b6  mov     rcx, qword ptr [rbp+var_20]
0x1800294ba  test    rcx, rcx
0x1800294bd  jz      short loc_1800294DC
0x1800294bf  mov     rdx, qword ptr [rbp+var_20+8]
0x1800294c3  call    ??$_Destroy_range@V?$allocator@U?$pair@V?$unique_ptr@UADDRESS_INTERFACE_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseGetIPPhysicalInterfaceForDestination@PublicNetworkListManager@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@@std@@YAXPEAU?$pair@V?$unique_ptr@UADDRESS_INTERFACE_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseGetIPPhysicalInterfaceForDestination@PublicNetworkListManager@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@QEAU10@AEAV?$allocator@U?$pair@V?$unique_ptr@UADDRESS_INTERFACE_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseGetIPPhysicalInterfaceForDestination@PublicNetworkListManager@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@0@@Z
0x1800294c8  mov     rcx, qword ptr [rbp+var_20]
0x1800294cc  mov     rdx, [rbp+var_10]
0x1800294d0  sub     rdx, rcx
0x1800294d3  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800294d7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800294dc  mov     eax, ebx
0x1800294de  jmp     short loc_180029511
0x1800294e0  lea     rcx, [rbp+var_28]
0x1800294e4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800294e9  mov     rcx, qword ptr [rbp+var_20]
0x1800294ed  test    rcx, rcx
0x1800294f0  jz      short loc_18002950F
0x1800294f2  mov     rdx, qword ptr [rbp+var_20+8]
0x1800294f6  call    ??$_Destroy_range@V?$allocator@U?$pair@V?$unique_ptr@UADDRESS_INTERFACE_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseGetIPPhysicalInterfaceForDestination@PublicNetworkListManager@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@@std@@YAXPEAU?$pair@V?$unique_ptr@UADDRESS_INTERFACE_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseGetIPPhysicalInterfaceForDestination@PublicNetworkListManager@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@QEAU10@AEAV?$allocator@U?$pair@V?$unique_ptr@UADDRESS_INTERFACE_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseGetIPPhysicalInterfaceForDestination@PublicNetworkListManager@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@0@@Z
0x1800294fb  mov     rcx, qword ptr [rbp+var_20]
0x1800294ff  mov     rdx, [rbp+var_10]
0x180029503  sub     rdx, rcx
0x180029506  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18002950a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002950f  xor     eax, eax
0x180029511  mov     rcx, [rbp+var_8]
0x180029515  xor     rcx, rsp; StackCookie
0x180029518  call    __security_check_cookie
0x18002951d  mov     rbx, [rsp+60h+arg_18]
0x180029525  add     rsp, 60h
0x180029529  pop     rdi
0x18002952a  pop     rsi
0x18002952b  pop     rbp
0x18002952c  retn
```
