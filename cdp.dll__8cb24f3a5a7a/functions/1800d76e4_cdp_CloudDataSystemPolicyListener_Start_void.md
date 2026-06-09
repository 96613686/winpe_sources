# cdp::CloudDataSystemPolicyListener::Start(void)

- ea: `0x1800d76e4`
- end: `0x1800d7b07`
- name: `?Start@CloudDataSystemPolicyListener@cdp@@QEAAXXZ`
- size: `1059`
- prototype: `void __fastcall(cdp::CloudDataSystemPolicyListener *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180038154`

## callees

- `0x180013da0`
- `0x18003b3ec`
- `0x18003fd00`
- `0x18008dbc0`
- `0x1800d76e4`
- `0x1800da19c`
- `0x180129e18`
- `0x180149448`
- `0x180171098`
- `0x1801765bc`
- `0x180187658`
- `0x1801e3320`
- `0x1801f6fb0`
- `0x1801fc5a4`
- `0x1801fc9fc`
- `0x180223200`
- `0x1802fc4d4`
- `0x1802fc534`
- `0x1802fc720`
- `0x1802fd0a4`
- `0x1802fd280`
- `0x180354010`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800d782e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800d782e`
- `ntdll!NtQueryWnfStateData` at `0x1800d7a04`
- `ntdll!NtQueryWnfStateData` at `0x1800d7a04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d790f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d790f`

## string_xrefs

- `0x1800d79c9`: `{"text":"Could not create CloudData MDM policy listener"}`
- `0x1800d7964`: `{"text":"Could not create CloudData Group Policy listener"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall cdp::CloudDataSystemPolicyListener::Start(cdp::CloudDataSystemPolicyListener *this)
{
  _QWORD *v2; // rax
  volatile signed __int32 *v3; // rsi
  __int64 v4; // rax
  void (__fastcall ***v5)(_QWORD, __int64); // r15
  _QWORD *v6; // rax
  void (__fastcall ***v7)(_QWORD, __int64); // rbx
  __int64 v8; // r8
  int v9; // edi
  int v10; // edi
  void (__fastcall ***v11)(_QWORD, __int64); // rbx
  HKEY v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rbx
  LSTATUS v16; // eax
  __int64 v17; // r8
  bool v18; // sf
  int dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  void (__fastcall ***v21)(_QWORD, __int64); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+68h] [rbp-98h] BYREF
  void (__fastcall ***v24)(_QWORD, _QWORD); // [rsp+78h] [rbp-88h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h] BYREF
  char v26; // [rsp+88h] [rbp-78h]
  _BYTE v27[16]; // [rsp+90h] [rbp-70h] BYREF
  char v28[8]; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v29; // [rsp+A8h] [rbp-58h]
  _BYTE v30[112]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v2 = (_QWORD *)std::enable_shared_from_this<shared::WebAccountCache>::shared_from_this(this, v28);
  v23 = 0;
  v3 = (volatile signed __int32 *)v2[1];
  if ( v3 )
  {
    *(_QWORD *)&v23 = *v2;
    *((_QWORD *)&v23 + 1) = v3;
    _InterlockedIncrement(v3 + 3);
  }
  else
  {
    v3 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
  }
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
  lambda_65b23ae27b23af6c85e9959f71c0e351_::_lambda_65b23ae27b23af6c85e9959f71c0e351_(v28, &v23);
  v4 = lambda_65b23ae27b23af6c85e9959f71c0e351_::_lambda_65b23ae27b23af6c85e9959f71c0e351__0(v27, v28);
  wistd::function_void___cdecl_void__::function_void___cdecl_void____lambda_65b23ae27b23af6c85e9959f71c0e351__void_(
    v30,
    v4);
  LODWORD(v21) = 0;
  v5 = 0;
  v6 = operator new(0x88u, (const struct std::nothrow_t *)std::nothrow);
  v7 = (void (__fastcall ***)(_QWORD, __int64))v6;
  if ( v6 )
  {
    v6[1] = 0;
    *v6 = &wil::details::wnf_subscription_state<wil::details::empty_wnf_state>::`vftable';
    if ( v31 )
    {
      v6[16] = v6 + 3;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 24LL))(v31);
      v31 = 0;
    }
    else
    {
      v6[16] = 0;
    }
    v8 = (unsigned int)v21;
    if ( (_DWORD)v21 == -1 )
    {
      LODWORD(phkResult) = 0;
      v10 = NtQueryWnfStateData(&WNF_ENTR_EXPERIENCE_POLICY_VALUE_CHANGED, 0, 0, &v21) | 0x10000000;
      if ( (int)(v10 + 0x80000000) >= 0 && v10 != -805306333 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
          (const char *)(unsigned int)v10,
          0);
LABEL_41:
        (**v7)(v7, 1);
        goto LABEL_13;
      }
      v8 = (unsigned int)v21;
    }
    v24 = v7 + 1;
    v25 = 0;
    v26 = 1;
    v9 = RtlSubscribeWnfStateChangeNotification(
           &v25,
           WNF_ENTR_EXPERIENCE_POLICY_VALUE_CHANGED,
           v8,
           _lambda_d93655bd33d44513d4ad201382c30aa7_::_lambda_invoker_cdecl_);
    if ( v26 )
      wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>::reset(
        v24,
        v25);
    if ( v9 >= 0 )
    {
      v5 = v7;
      v10 = 0;
      goto LABEL_13;
    }
    v10 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x3C7,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
            (const char *)(unsigned int)v9,
            (int)v7);
    goto LABEL_41;
  }
  v10 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B1,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
    (const char *)0x8007000ELL,
    dwOptions);
LABEL_13:
  v11 = 0;
  if ( v10 >= 0 )
    v11 = v5;
  v21 = v11;
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 24LL))(v31);
  if ( v11 )
  {
    v12 = (HKEY)operator new(8u);
    phkResult = v12;
    v21 = 0;
    *(_QWORD *)v12 = v11;
    v13 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = v12;
    if ( v13 )
      std::default_delete<cdp::ServiceUserInstance::WilWnfSubscriptionWrapper>::operator()();
  }
  else
  {
    Log<>(1, "{\"text\":\"Could not create CloudData MDM policy listener\"}");
  }
  lambda_65b23ae27b23af6c85e9959f71c0e351_::_lambda_65b23ae27b23af6c85e9959f71c0e351_(v27, &v23);
  v14 = lambda_65b23ae27b23af6c85e9959f71c0e351_::_lambda_65b23ae27b23af6c85e9959f71c0e351__0(&v24, v27);
  wistd::function_void___cdecl_enum_wil::RegistryChangeKind__::function_void___cdecl_enum_wil::RegistryChangeKind____lambda_3bcf890c7ed24f21f4b70fb5e721c6c9__void_(
    v30,
    v14);
  v15 = 0;
  v22 = 0;
  phkResult = 0;
  v16 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Policies\\Microsoft\\Windows\\SettingSync",
          0,
          0,
          0,
          0x10u,
          0,
          &phkResult,
          0);
  v18 = v16 < 0;
  if ( v16 > 0 )
    v18 = 1;
  if ( v18 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&phkResult);
  }
  else
  {
    wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
      (__int64)&v22,
      (__int64)&phkResult,
      v17,
      (__int64)v30);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&phkResult);
    v15 = v22;
  }
  if ( (__int64 *)((char *)this + 24) != &v22 )
  {
    wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
      (char *)this + 24,
      v15);
    v22 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v22);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 24LL))(v31);
  if ( !*((_QWORD *)this + 3) )
    Log<>(1, "{\"text\":\"Could not create CloudData Group Policy listener\"}");
  lambda_dad3880547138f226461bcdc588c35a6_::__lambda_dad3880547138f226461bcdc588c35a6_(v27);
  lambda_dad3880547138f226461bcdc588c35a6_::__lambda_dad3880547138f226461bcdc588c35a6_(v28);
  if ( v3 )
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v3);
}

```

## disassembly

```asm
0x1800d76e4  mov     [rsp-8+arg_8], rbx
0x1800d76e9  mov     [rsp-8+arg_10], rsi
0x1800d76ee  push    rbp
0x1800d76ef  push    rdi
0x1800d76f0  push    r12
0x1800d76f2  push    r14
0x1800d76f4  push    r15
0x1800d76f6  lea     rbp, [rsp-30h]
0x1800d76fb  sub     rsp, 130h
0x1800d7702  mov     rax, cs:__security_cookie
0x1800d7709  xor     rax, rsp
0x1800d770c  mov     [rbp+50h+var_28], rax
0x1800d7710  mov     r14, rcx
0x1800d7713  xor     r12d, r12d
0x1800d7716  lea     rdx, [rbp+50h+var_B0]
0x1800d771a  call    ?shared_from_this@?$enable_shared_from_this@VWebAccountCache@shared@@@std@@QEAA?AV?$shared_ptr@VWebAccountCache@shared@@@2@XZ; std::enable_shared_from_this<shared::WebAccountCache>::shared_from_this(void)
0x1800d771f  xorps   xmm0, xmm0
0x1800d7722  movdqu  [rsp+150h+var_E8], xmm0
0x1800d7728  mov     rsi, [rax+8]
0x1800d772c  test    rsi, rsi
0x1800d772f  jz      loc_1800D79BF
0x1800d7735  mov     rax, [rax]
0x1800d7738  mov     qword ptr [rsp+150h+var_E8], rax
0x1800d773d  mov     qword ptr [rsp+150h+var_E8+8], rsi
0x1800d7742  lock inc dword ptr [rsi+0Ch]
0x1800d7746  mov     rcx, [rbp+50h+var_A8]; this
0x1800d774a  test    rcx, rcx
0x1800d774d  jz      short loc_1800D7754
0x1800d774f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d7754  lea     rdx, [rsp+150h+var_E8]
0x1800d7759  lea     rcx, [rbp+50h+var_B0]
0x1800d775d  call    _lambda_65b23ae27b23af6c85e9959f71c0e351____lambda_65b23ae27b23af6c85e9959f71c0e351_
0x1800d7762  nop
0x1800d7763  lea     rdx, [rbp+50h+var_B0]
0x1800d7767  lea     rcx, [rbp+50h+var_C0]
0x1800d776b  call    _lambda_65b23ae27b23af6c85e9959f71c0e351____lambda_65b23ae27b23af6c85e9959f71c0e351__0
0x1800d7770  mov     rdx, rax
0x1800d7773  lea     rcx, [rbp+50h+var_A0]
0x1800d7777  call    wistd__function_void___cdecl_void____function_void___cdecl_void____lambda_65b23ae27b23af6c85e9959f71c0e351__void_
0x1800d777c  mov     dword ptr [rsp+150h+var_F8], r12d
0x1800d7781  mov     r15, r12
0x1800d7784  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d778b  mov     ecx, 88h; unsigned __int64
0x1800d7790  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d7795  mov     rbx, rax
0x1800d7798  test    rax, rax
0x1800d779b  jz      loc_1800D7A99
0x1800d77a1  mov     [rax+8], r12
0x1800d77a5  lea     rax, ??_7?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@6B@; const wil::details::wnf_subscription_state<wil::details::empty_wnf_state>::`vftable'
0x1800d77ac  mov     [rbx], rax
0x1800d77af  cmp     [rbp+50h+var_30], r12
0x1800d77b3  jz      loc_1800D7A48
0x1800d77b9  lea     rdx, [rbx+18h]
0x1800d77bd  mov     [rbx+80h], rdx
0x1800d77c4  mov     rcx, [rbp+50h+var_30]
0x1800d77c8  mov     rax, [rcx]
0x1800d77cb  mov     rax, [rax+10h]
0x1800d77cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d77d4  mov     rcx, [rbp+50h+var_30]
0x1800d77d8  mov     rax, [rcx]
0x1800d77db  mov     rax, [rax+18h]
0x1800d77df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d77e4  mov     [rbp+50h+var_30], r12
0x1800d77e8  mov     r8d, dword ptr [rsp+150h+var_F8]
0x1800d77ed  cmp     r8d, 0FFFFFFFFh
0x1800d77f1  jz      loc_1800D79DF
0x1800d77f7  lea     rax, [rbx+8]
0x1800d77fb  mov     [rsp+150h+var_D8], rax
0x1800d7800  mov     [rbp+50h+var_D0], r12
0x1800d7804  mov     [rbp+50h+var_C8], 1
0x1800d7808  mov     dword ptr [rsp+150h+phkResult], r12d
0x1800d780d  mov     dword ptr [rsp+150h+lpSecurityAttributes], r12d
0x1800d7812  mov     qword ptr [rsp+150h+samDesired], r12
0x1800d7817  mov     qword ptr [rsp+150h+dwOptions], rbx; int
0x1800d781c  lea     r9, ?_lambda_invoker_cdecl_@_lambda_d93655bd33d44513d4ad201382c30aa7_@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; _lambda_d93655bd33d44513d4ad201382c30aa7_::_lambda_invoker_cdecl_(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800d7823  mov     rdx, cs:WNF_ENTR_EXPERIENCE_POLICY_VALUE_CHANGED
0x1800d782a  lea     rcx, [rbp+50h+var_D0]
0x1800d782e  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800d7834  mov     edi, eax
0x1800d7836  cmp     [rbp+50h+var_C8], r12b
0x1800d783a  jnz     loc_1800D7A86
0x1800d7840  test    edi, edi
0x1800d7842  js      loc_1800D7A54
0x1800d7848  mov     r15, rbx
0x1800d784b  mov     edi, r12d
0x1800d784e  mov     rbx, r12
0x1800d7851  test    edi, edi
0x1800d7853  cmovns  rbx, r15
0x1800d7857  mov     [rsp+150h+var_F8], rbx
0x1800d785c  mov     rcx, [rbp+50h+var_30]
0x1800d7860  test    rcx, rcx
0x1800d7863  jz      short loc_1800D7871
0x1800d7865  mov     rax, [rcx]
0x1800d7868  mov     rax, [rax+18h]
0x1800d786c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7871  test    rbx, rbx
0x1800d7874  jz      loc_1800D79C9
0x1800d787a  mov     ecx, 8; Size
0x1800d787f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d7884  mov     [rsp+150h+var_100], rax
0x1800d7889  mov     [rsp+150h+var_F8], r12
0x1800d788e  mov     [rax], rbx
0x1800d7891  mov     rdx, [r14+10h]
0x1800d7895  mov     [r14+10h], rax
0x1800d7899  test    rdx, rdx
0x1800d789c  jz      short loc_1800D78A3
0x1800d789e  call    ??R?$default_delete@VWilWnfSubscriptionWrapper@ServiceUserInstance@cdp@@@std@@QEBAXPEAVWilWnfSubscriptionWrapper@ServiceUserInstance@cdp@@@Z; std::default_delete<cdp::ServiceUserInstance::WilWnfSubscriptionWrapper>::operator()(cdp::ServiceUserInstance::WilWnfSubscriptionWrapper *)
0x1800d78a3  lea     rdx, [rsp+150h+var_E8]
0x1800d78a8  lea     rcx, [rbp+50h+var_C0]
0x1800d78ac  call    _lambda_65b23ae27b23af6c85e9959f71c0e351____lambda_65b23ae27b23af6c85e9959f71c0e351_
0x1800d78b1  nop
0x1800d78b2  lea     rdx, [rbp+50h+var_C0]
0x1800d78b6  lea     rcx, [rsp+150h+var_D8]
0x1800d78bb  call    _lambda_65b23ae27b23af6c85e9959f71c0e351____lambda_65b23ae27b23af6c85e9959f71c0e351__0
0x1800d78c0  mov     rdx, rax
0x1800d78c3  lea     rcx, [rbp+50h+var_A0]
0x1800d78c7  call    wistd__function_void___cdecl_enum_wil__RegistryChangeKind____function_void___cdecl_enum_wil__RegistryChangeKind____lambda_3bcf890c7ed24f21f4b70fb5e721c6c9__void_
0x1800d78cc  nop
0x1800d78cd  mov     rbx, r12
0x1800d78d0  mov     [rsp+150h+var_F0], rbx
0x1800d78d5  mov     [rsp+150h+var_100], r12
0x1800d78da  mov     [rsp+150h+lpdwDisposition], r12; lpdwDisposition
0x1800d78df  lea     rax, [rsp+150h+var_100]
0x1800d78e4  mov     [rsp+150h+phkResult], rax; phkResult
0x1800d78e9  mov     [rsp+150h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800d78ee  mov     [rsp+150h+samDesired], 10h; samDesired
0x1800d78f6  mov     [rsp+150h+dwOptions], r12d; dwOptions
0x1800d78fb  xor     r9d, r9d; lpClass
0x1800d78fe  xor     r8d, r8d; Reserved
0x1800d7901  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800d7908  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d790f  call    cs:__imp_RegCreateKeyExW
0x1800d7915  test    eax, eax
0x1800d7917  jg      loc_1800D7ABB
0x1800d791d  jns     loc_1800D7ACA
0x1800d7923  lea     rcx, [rsp+150h+var_100]
0x1800d7928  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x1800d792d  nop
0x1800d792e  lea     rdi, [r14+18h]
0x1800d7932  lea     rax, [rsp+150h+var_F0]
0x1800d7937  cmp     rdi, rax
0x1800d793a  jnz     loc_1800D7AF1
0x1800d7940  lea     rcx, [rsp+150h+var_F0]
0x1800d7945  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x1800d794a  mov     rcx, [rbp+50h+var_30]
0x1800d794e  test    rcx, rcx
0x1800d7951  jz      short loc_1800D795F
0x1800d7953  mov     rax, [rcx]
0x1800d7956  mov     rax, [rax+18h]
0x1800d795a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d795f  cmp     [rdi], r12
0x1800d7962  jnz     short loc_1800D7976
0x1800d7964  lea     rdx, aTextCouldNotCr_0; "{\"text\":\"Could not create CloudData "...
0x1800d796b  mov     ecx, 1
0x1800d7970  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x1800d7975  nop
0x1800d7976  lea     rcx, [rbp+50h+var_C0]
0x1800d797a  call    _lambda_dad3880547138f226461bcdc588c35a6_____lambda_dad3880547138f226461bcdc588c35a6_
0x1800d797f  nop
0x1800d7980  lea     rcx, [rbp+50h+var_B0]
0x1800d7984  call    _lambda_dad3880547138f226461bcdc588c35a6_____lambda_dad3880547138f226461bcdc588c35a6_
0x1800d7989  nop
0x1800d798a  test    rsi, rsi
0x1800d798d  jz      short loc_1800D7997
0x1800d798f  mov     rcx, rsi; this
0x1800d7992  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800d7997  mov     rcx, [rbp+50h+var_28]
0x1800d799b  xor     rcx, rsp; StackCookie
0x1800d799e  call    __security_check_cookie
0x1800d79a3  lea     r11, [rsp+150h+var_20]
0x1800d79ab  mov     rbx, [r11+38h]
0x1800d79af  mov     rsi, [r11+40h]
0x1800d79b3  mov     rsp, r11
0x1800d79b6  pop     r15
0x1800d79b8  pop     r14
0x1800d79ba  pop     r12
0x1800d79bc  pop     rdi
0x1800d79bd  pop     rbp
0x1800d79be  retn
0x1800d79bf  mov     rsi, qword ptr [rsp+150h+var_E8+8]
0x1800d79c4  jmp     loc_1800D7746
0x1800d79c9  lea     rdx, aTextCouldNotCr; "{\"text\":\"Could not create CloudData "...
0x1800d79d0  mov     ecx, 1
0x1800d79d5  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x1800d79da  jmp     loc_1800D78A3
0x1800d79df  mov     dword ptr [rsp+150h+var_100], r12d
0x1800d79e4  lea     rax, [rsp+150h+var_100]
0x1800d79e9  mov     qword ptr [rsp+150h+samDesired], rax
0x1800d79ee  mov     qword ptr [rsp+150h+dwOptions], r12; int
0x1800d79f3  lea     r9, [rsp+150h+var_F8]
0x1800d79f8  xor     r8d, r8d
0x1800d79fb  xor     edx, edx
0x1800d79fd  lea     rcx, WNF_ENTR_EXPERIENCE_POLICY_VALUE_CHANGED
0x1800d7a04  call    cs:__imp_NtQueryWnfStateData
0x1800d7a0a  mov     edi, eax
0x1800d7a0c  bts     edi, 1Ch
0x1800d7a10  mov     eax, 80000000h
0x1800d7a15  lea     ecx, [rdi+rax]
0x1800d7a18  test    eax, ecx
0x1800d7a1a  jz      short loc_1800D7A26
0x1800d7a1c  mov     r8d, dword ptr [rsp+150h+var_F8]
0x1800d7a21  jmp     loc_1800D77F7
0x1800d7a26  cmp     edi, 0D0000023h
0x1800d7a2c  jz      short loc_1800D7A1C
0x1800d7a2e  mov     rcx, [rbp+58h]; this
0x1800d7a32  mov     r9d, edi; char *
0x1800d7a35  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x1800d7a3c  mov     edx, 3B8h; void *
0x1800d7a41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d7a46  jmp     short loc_1800D7A6E
0x1800d7a48  mov     [rbx+80h], r12
0x1800d7a4f  jmp     loc_1800D77E8
0x1800d7a54  mov     rcx, [rbp+58h]; this
0x1800d7a58  mov     r9d, edi; char *
0x1800d7a5b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x1800d7a62  mov     edx, 3C7h; void *
0x1800d7a67  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800d7a6c  mov     edi, eax
0x1800d7a6e  mov     rax, [rbx]
0x1800d7a71  mov     edx, 1
0x1800d7a76  mov     rcx, rbx
0x1800d7a79  mov     rax, [rax]
0x1800d7a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7a81  jmp     loc_1800D784E
0x1800d7a86  mov     rdx, [rbp+50h+var_D0]
0x1800d7a8a  mov     rcx, [rsp+150h+var_D8]
0x1800d7a8f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_WNF_USER_SUBSCRIPTION@@P6AJPEAU1@@Z$1?RtlUnsubscribeWnfStateChangeNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_WNF_USER_SUBSCRIPTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>::reset(_WNF_USER_SUBSCRIPTION *)
0x1800d7a94  jmp     loc_1800D7840
0x1800d7a99  mov     rcx, [rbp+58h]; this
0x1800d7a9d  mov     edi, 8007000Eh
0x1800d7aa2  mov     r9d, edi; char *
0x1800d7aa5  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x1800d7aac  mov     edx, 3B1h; void *
0x1800d7ab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d7ab6  jmp     loc_1800D784E
0x1800d7abb  movzx   eax, ax
0x1800d7abe  or      eax, 80070000h
0x1800d7ac3  test    eax, eax
0x1800d7ac5  jmp     loc_1800D791D
0x1800d7aca  lea     r9, [rbp+50h+var_A0]
0x1800d7ace  lea     rdx, [rsp+150h+var_100]
0x1800d7ad3  lea     rcx, [rsp+150h+var_F0]
0x1800d7ad8  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800d7add  lea     rcx, [rsp+150h+var_100]
0x1800d7ae2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x1800d7ae7  mov     rbx, [rsp+150h+var_F0]
0x1800d7aec  jmp     loc_1800D792E
0x1800d7af1  mov     rdx, rbx
0x1800d7af4  mov     rcx, rdi
0x1800d7af7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x1800d7afc  mov     [rsp+150h+var_F0], r12
0x1800d7b01  jmp     loc_1800D7940
```
