# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults<long,`NsiNotifications::NotificationTracking::StopNotifications(void)'::`2'::_lambda_1_>(`NsiNotifications::NotificationTracking::StopNotifications(void)'::`2'::_lambda_1_ &&)

- ea: `0x1800311c4`
- end: `0x1800313dd`
- name: `??$SubmitWorkWithResults@JV_lambda_1_@?1??StopNotifications@NotificationTracking@NsiNotifications@@QEAAXXZ@@ThreadPoolWorkQueue@WcmCommon@@QEAA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@std@@$$QEAV_lambda_1_@?1??StopNotifications@NotificationTracking@NsiNotifications@@QEAAXXZ@@Z`
- size: `537`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800313e4`

## callees

- `0x18000809c`
- `0x18000da4c`
- `0x18000f094`
- `0x180012a90`
- `0x18001aed4`
- `0x18001e420`
- `0x18002f918`
- `0x18002facc`
- `0x18002fb30`
- `0x18002fca0`
- `0x180030d60`
- `0x1800311c4`
- `0x180031488`
- `0x180031518`
- `0x180036390`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800311ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800311ff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800313b2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800313b2`

## pseudocode

```c
_QWORD *__fastcall ___SubmitWorkWithResults_JV_lambda_1___1__StopNotifications_NotificationTracking_NsiNotifications__QEAAXXZ__ThreadPoolWorkQueue_WcmCommon__QEAA_AV__shared_ptr_V__ThreadPoolWaitableResult_J_WcmCommon___std____QEAV_lambda_1___1__StopNotifications_NotificationTracking_NsiNotifications__QEAAXXZ__Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // rbx
  _DWORD *v7; // r14
  __int64 v8; // r13
  __int64 v9; // r12
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r13
  __int64 v13; // r12
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v17; // [rsp+20h] [rbp-59h] BYREF
  __int128 v18; // [rsp+28h] [rbp-51h] BYREF
  _DWORD *v19; // [rsp+40h] [rbp-39h] BYREF
  std::_Ref_count_base *v20; // [rsp+48h] [rbp-31h]
  _BYTE v21[128]; // [rsp+50h] [rbp-29h] BYREF

  v18 = 0;
  v6 = a1 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v17 = v6;
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
  }
  else
  {
    v7 = operator new(0x78u);
    v19 = v7;
    *(_OWORD *)v7 = 0;
    v7[2] = 1;
    v7[3] = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<long>>::`vftable';
    ____Construct_in_place_V__ThreadPoolWaitableResult_J_WcmCommon__V_lambda_1___1__StopNotifications_NotificationTracking_NsiNotifications__QEAAXXZ__std__YAXAEAV__ThreadPoolWaitableResult_J_WcmCommon____QEAV_lambda_1___1__StopNotifications_NotificationTracking_NsiNotifications__QEAAXXZ__Z(
      (_QWORD *)v7 + 2,
      a3);
    *(_QWORD *)&v18 = v7 + 4;
    *((_QWORD *)&v18 + 1) = v7;
    if ( *(_DWORD *)a1 == 1 )
    {
      std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(
        &v19,
        &v18);
      if ( *(_QWORD *)(a1 + 208) <= (unsigned __int64)(*(_QWORD *)(a1 + 224) + 1LL) )
        std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Growmap(a1 + 192);
      *(_QWORD *)(a1 + 216) &= *(_QWORD *)(a1 + 208) - 1LL;
      v8 = *(_QWORD *)(a1 + 224) + *(_QWORD *)(a1 + 216);
      v9 = std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Getblock(a1 + 192, v8);
      if ( !*(_QWORD *)(*(_QWORD *)(a1 + 200) + 8 * v9) )
        *(_QWORD *)(*(_QWORD *)(a1 + 200) + 8 * v9) = std::_Allocate<16,std::_Default_allocate_traits>(0x10u);
      v10 = std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>::_Address_subscript(
              a1 + 192,
              v8);
      std::_Default_allocator_traits<std::allocator<std::shared_ptr<DusmConnection>>>::construct<std::shared_ptr<DusmConnection>,std::shared_ptr<DusmConnection>>(
        v11,
        v10,
        &v19);
      ++*(_QWORD *)(a1 + 224);
      if ( v20 )
        std::_Ref_count_base::_Decref(v20);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>((__int64)v21);
      if ( *(_QWORD *)(a1 + 248) <= (unsigned __int64)(*(_QWORD *)(a1 + 264) + 1LL) )
        std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Growmap(a1 + 232);
      *(_QWORD *)(a1 + 256) &= *(_QWORD *)(a1 + 248) - 1LL;
      v12 = *(_QWORD *)(a1 + 264) + *(_QWORD *)(a1 + 256);
      v13 = std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Getblock(a1 + 232, v12);
      if ( !*(_QWORD *)(*(_QWORD *)(a1 + 240) + 8 * v13) )
        *(_QWORD *)(*(_QWORD *)(a1 + 240) + 8 * v13) = std::_Allocate<16,std::_Default_allocate_traits>(0x48u);
      v14 = std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>::_Address_subscript(
              a1 + 232,
              v12);
      std::_Default_allocator_traits<std::allocator<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>::construct<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(
        v15,
        v14,
        (__int64)v21);
      ++*(_QWORD *)(a1 + 264);
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(v21);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *a2 = v7 + 4;
    a2[1] = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x1800311c4  mov     [rsp-8+arg_10], rbx
0x1800311c9  push    rbp
0x1800311ca  push    rsi
0x1800311cb  push    rdi
0x1800311cc  push    r12
0x1800311ce  push    r13
0x1800311d0  push    r14
0x1800311d2  push    r15
0x1800311d4  lea     rbp, [rsp-27h]
0x1800311d9  sub     rsp, 0A0h
0x1800311e0  mov     r12, r8
0x1800311e3  mov     rdi, rdx
0x1800311e6  mov     rsi, rcx
0x1800311e9  mov     [rbp+57h+var_B0], rdx
0x1800311ed  xor     r14d, r14d
0x1800311f0  xorps   xmm1, xmm1
0x1800311f3  movdqu  [rbp+57h+var_A8], xmm1
0x1800311f8  lea     rbx, [rcx+8]
0x1800311fc  mov     rcx, rbx; lpCriticalSection
0x1800311ff  call    cs:__imp_EnterCriticalSection
0x180031205  mov     [rbp+57h+var_B0], rbx
0x180031209  cmp     [rsi+110h], r14b
0x180031210  jz      short loc_180031227
0x180031212  mov     [rdi], r14
0x180031215  mov     [rdi+8], r14
0x180031219  lea     rcx, [rbp+57h+var_B0]
0x18003121d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180031222  jmp     loc_1800313BF
0x180031227  mov     ecx, 78h ; 'x'; Size
0x18003122c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031231  mov     r14, rax
0x180031234  mov     [rbp+57h+var_90], rax
0x180031238  xorps   xmm0, xmm0
0x18003123b  movups  xmmword ptr [rax], xmm0
0x18003123e  mov     r13d, 1
0x180031244  mov     [rax+8], r13d
0x180031248  mov     [rax+0Ch], r13d
0x18003124c  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@J@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<long>>::`vftable'
0x180031253  mov     [r14], rax
0x180031256  lea     r15, [r14+10h]
0x18003125a  mov     rdx, r12
0x18003125d  mov     rcx, r15
0x180031260  call    ??$_Construct_in_place@V?$ThreadPoolWaitableResult@J@WcmCommon@@V_lambda_1_@?1??StopNotifications@NotificationTracking@NsiNotifications@@QEAAXXZ@@std@@YAXAEAV?$ThreadPoolWaitableResult@J@WcmCommon@@$$QEAV_lambda_1_@?1??StopNotifications@NotificationTracking@NsiNotifications@@QEAAXXZ@@Z; std::_Construct_in_place<WcmCommon::ThreadPoolWaitableResult<long>,`NsiNotifications::NotificationTracking::StopNotifications(void)'::`2'::_lambda_1_>(WcmCommon::ThreadPoolWaitableResult<long> &,`NsiNotifications::NotificationTracking::StopNotifications(void)'::`2'::_lambda_1_ &&)
0x180031265  nop
0x180031266  mov     qword ptr [rbp+57h+var_A8], r15
0x18003126a  mov     qword ptr [rbp+57h+var_A8+8], r14
0x18003126e  lea     rdx, [rbp+57h+var_A8]
0x180031272  cmp     [rsi], r13d
0x180031275  jnz     loc_180031311
0x18003127b  lea     rbx, [rsi+0C0h]
0x180031282  lea     rcx, [rbp+57h+var_90]
0x180031286  call    ??$?0V?$ThreadPoolWaitableResult@J@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<long>> const &)
0x18003128b  nop
0x18003128c  mov     rax, [rbx+20h]
0x180031290  add     rax, r13
0x180031293  cmp     [rbx+10h], rax
0x180031297  ja      short loc_1800312A1
0x180031299  mov     rcx, rbx
0x18003129c  call    ?_Growmap@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Growmap(unsigned __int64)
0x1800312a1  mov     rax, [rbx+10h]
0x1800312a5  sub     rax, r13
0x1800312a8  and     [rbx+18h], rax
0x1800312ac  mov     r13, [rbx+18h]
0x1800312b0  add     r13, [rbx+20h]
0x1800312b4  mov     rdx, r13
0x1800312b7  mov     rcx, rbx
0x1800312ba  call    ?_Getblock@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@AEBA_J_K@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Getblock(unsigned __int64)
0x1800312bf  mov     r12, rax
0x1800312c2  mov     rcx, [rbx+8]
0x1800312c6  cmp     qword ptr [rcx+rax*8], 0
0x1800312cb  jnz     short loc_1800312DF
0x1800312cd  mov     ecx, 10h
0x1800312d2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800312d7  mov     rcx, [rbx+8]
0x1800312db  mov     [rcx+r12*8], rax
0x1800312df  mov     rdx, r13
0x1800312e2  mov     rcx, rbx
0x1800312e5  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@std@@@std@@QEAAPEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@2@_K@Z; std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>::_Address_subscript(unsigned __int64)
0x1800312ea  lea     r8, [rbp+57h+var_90]
0x1800312ee  mov     rdx, rax
0x1800312f1  call    ??$construct@V?$shared_ptr@VDusmConnection@@@std@@V12@@?$_Default_allocator_traits@V?$allocator@V?$shared_ptr@VDusmConnection@@@std@@@std@@@std@@SAXAEAV?$allocator@V?$shared_ptr@VDusmConnection@@@std@@@1@QEAV?$shared_ptr@VDusmConnection@@@1@$$QEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::shared_ptr<DusmConnection>>>::construct<std::shared_ptr<DusmConnection>,std::shared_ptr<DusmConnection>>(std::allocator<std::shared_ptr<DusmConnection>> &,std::shared_ptr<DusmConnection> * const,std::shared_ptr<DusmConnection> &&)
0x1800312f6  inc     qword ptr [rbx+20h]
0x1800312fa  mov     rcx, [rbp+57h+var_88]; this
0x1800312fe  test    rcx, rcx
0x180031301  jz      loc_18003139A
0x180031307  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003130c  jmp     loc_18003139A
0x180031311  lea     rbx, [rsi+0E8h]
0x180031318  lea     rcx, [rbp+57h+var_80]
0x18003131c  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<long>> &)
0x180031321  nop
0x180031322  mov     rax, [rbx+20h]
0x180031326  add     rax, r13
0x180031329  cmp     [rbx+10h], rax
0x18003132d  ja      short loc_180031337
0x18003132f  mov     rcx, rbx
0x180031332  call    ?_Growmap@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Growmap(unsigned __int64)
0x180031337  mov     rax, [rbx+10h]
0x18003133b  sub     rax, r13
0x18003133e  and     [rbx+18h], rax
0x180031342  mov     r13, [rbx+18h]
0x180031346  add     r13, [rbx+20h]
0x18003134a  mov     rdx, r13
0x18003134d  mov     rcx, rbx
0x180031350  call    ?_Getblock@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@AEBA_J_K@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Getblock(unsigned __int64)
0x180031355  mov     r12, rax
0x180031358  mov     rcx, [rbx+8]
0x18003135c  cmp     qword ptr [rcx+rax*8], 0
0x180031361  jnz     short loc_180031375
0x180031363  mov     ecx, 48h ; 'H'
0x180031368  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003136d  mov     rcx, [rbx+8]
0x180031371  mov     [rcx+r12*8], rax
0x180031375  mov     rdx, r13
0x180031378  mov     rcx, rbx
0x18003137b  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@std@@@std@@QEAAPEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@2@_K@Z; std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>::_Address_subscript(unsigned __int64)
0x180031380  lea     r8, [rbp+57h+var_80]
0x180031384  mov     rdx, rax
0x180031387  call    ??$construct@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V12@@?$_Default_allocator_traits@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@1@QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>::construct<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::allocator<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>> &,std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> * const,std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18003138c  inc     qword ptr [rbx+20h]
0x180031390  lea     rcx, [rbp+57h+var_80]
0x180031394  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x180031399  nop
0x18003139a  lea     rcx, [rbp+57h+var_B0]
0x18003139e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800313a3  lock inc qword ptr [rsi+88h]
0x1800313ab  mov     rcx, [rsi+80h]; pwk
0x1800313b2  call    cs:__imp_SubmitThreadpoolWork
0x1800313b8  mov     [rdi], r15
0x1800313bb  mov     [rdi+8], r14
0x1800313bf  mov     rax, rdi
0x1800313c2  mov     rbx, [rsp+0D0h+arg_10]
0x1800313ca  add     rsp, 0A0h
0x1800313d1  pop     r15
0x1800313d3  pop     r14
0x1800313d5  pop     r13
0x1800313d7  pop     r12
0x1800313d9  pop     rdi
0x1800313da  pop     rsi
0x1800313db  pop     rbp
0x1800313dc  retn
```
