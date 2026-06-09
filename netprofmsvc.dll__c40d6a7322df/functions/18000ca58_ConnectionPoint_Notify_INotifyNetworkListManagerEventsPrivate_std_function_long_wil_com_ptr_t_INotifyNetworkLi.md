# ConnectionPoint::Notify<INotifyNetworkListManagerEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkListManagerEventsPrivate,wil::err_exception_policy> const &)>)

- ea: `0x18000ca58`
- end: `0x18000cd17`
- name: `??$Notify@UINotifyNetworkListManagerEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkListManagerEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018a40`

## callees

- `0x18000c160`
- `0x18000ca58`
- `0x18000d7bc`
- `0x18000e190`
- `0x18000e9c0`
- `0x18000e9e0`
- `0x18000eab0`
- `0x18006e880`
- `0x1800a88a0`
- `0x1800be664`
- `0x1800be708`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ca9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cbbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ca9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cbbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cbdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ccd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cbdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ccd7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ccec`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ccec`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ConnectionPoint::Notify<INotifyNetworkListManagerEventsPrivate>(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // r12
  int v6; // esi
  __int64 v7; // rax
  __int64 v8; // r15
  std::_Ref_count_base *v9; // r14
  std::_Ref_count_base *v10; // rcx
  __int64 v11; // rdi
  std::_Ref_count_base *v12; // r15
  __int64 (__fastcall ***v13)(_QWORD, _BYTE *); // rcx
  _DWORD *v14; // r14
  __int64 v15; // rdx
  __int64 i; // rax
  std::_Ref_count_base *v19; // [rsp+20h] [rbp-E0h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+38h] [rbp-C8h]
  _DWORD v21[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h]
  _BYTE v23[56]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+B8h] [rbp-48h]
  __int64 v25; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v26[56]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD *v27; // [rsp+108h] [rbp+8h]
  __int64 v28; // [rsp+110h] [rbp+10h] BYREF

  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(a1 + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v4 = **(_QWORD **)(a1 + 80);
  v5 = a1;
  while ( !*(_BYTE *)(v4 + 25) )
  {
    v6 = *(_DWORD *)(v4 + 32);
    v7 = *(_QWORD *)(v4 + 48);
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
    v8 = *(_QWORD *)(v4 + 40);
    v9 = *(std::_Ref_count_base **)(v4 + 48);
    v19 = v9;
    v28 = 0;
    wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<INotifyNetworkListManagerEventsPrivate>(v8, &v28);
    v10 = *(std::_Ref_count_base **)(v8 + 16);
    if ( v10 && std::_Ref_count_base::_Incref_nz(v10) )
    {
      v11 = *(_QWORD *)(v8 + 8);
      v12 = *(std::_Ref_count_base **)(v8 + 16);
    }
    else
    {
      v12 = 0;
      v11 = 0;
    }
    if ( v11 )
    {
      v21[0] = v6;
      v21[1] = *(_DWORD *)(v11 + 280);
      v22 = v5;
      v24 = 0;
      v13 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a2 + 56);
      if ( v13 )
        v24 = (**v13)(v13, v23);
      v25 = v28;
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
      v27 = 0;
      v14 = ____Global_new_V___Func_impl_no_alloc_V_lambda_1___8____Notify_UINotifyNetworkListManagerEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkListManagerEventsPrivate__Uerr_exception_policy_wil___wil___Z_std___Z_X__V_std__V_lambda_1___8____Notify_UINotifyNetworkListManagerEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkListManagerEventsPrivate__Uerr_exception_policy_wil___wil___Z_2__Z__std__YAPEAV___Func_impl_no_alloc_V_lambda_1___8____Notify_UINotifyNetworkListManagerEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkListManagerEventsPrivate__Uerr_exception_policy_wil___wil___Z_std___Z_X__V_0___QEAV_lambda_1___8____Notify_UINotifyNetworkListManagerEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkListManagerEventsPrivate__Uerr_exception_policy_wil___wil___Z_0__Z__Z((__int64)v21);
      v27 = v14;
      EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 8));
      if ( *(_BYTE *)(v11 + 272) )
      {
        if ( v11 != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 8));
      }
      else
      {
        if ( *(_DWORD *)v11 == 1 )
          std::deque<std::function<void (void)>>::emplace_back<std::function<void (void)>>(v11 + 152, v26);
        else
          std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<std::function<void (void)>>(
            v11 + 232,
            v26);
        if ( v11 != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 8));
        _InterlockedIncrement64((volatile signed __int64 *)(v11 + 136));
        SubmitThreadpoolWork(*(PTP_WORK *)(v11 + 128));
        v14 = v27;
      }
      if ( v14 )
      {
        LOBYTE(v15) = v14 != (_DWORD *)v26;
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v14 + 32LL))(v14, v15);
      }
      wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(&v25);
      std::_Func_class<void,>::~_Func_class<void,>(v23);
      v9 = v19;
    }
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    if ( *(_BYTE *)(*(_QWORD *)(v4 + 16) + 25LL) )
    {
      for ( i = *(_QWORD *)(v4 + 8); !*(_BYTE *)(i + 25) && v4 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
        v4 = i;
    }
    else
    {
      i = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<ConnectedProcess>>>>::_Min();
    }
    v4 = i;
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return std::_Func_class<void,>::~_Func_class<void,>(a2);
}

```

## disassembly

```asm
0x18000ca58  mov     [rsp-8+arg_10], rbx
0x18000ca5d  push    rbp
0x18000ca5e  push    rsi
0x18000ca5f  push    rdi
0x18000ca60  push    r12
0x18000ca62  push    r13
0x18000ca64  push    r14
0x18000ca66  push    r15
0x18000ca68  lea     rbp, [rsp-20h]
0x18000ca6d  sub     rsp, 120h
0x18000ca74  mov     rax, cs:__security_cookie
0x18000ca7b  xor     rax, rsp
0x18000ca7e  mov     [rbp+50h+var_38], rax
0x18000ca82  mov     r13, rdx
0x18000ca85  mov     rbx, rcx
0x18000ca88  mov     [rsp+150h+var_130], rcx
0x18000ca8d  mov     [rsp+150h+var_F8], rdx
0x18000ca92  lea     r12, [rcx+28h]
0x18000ca96  mov     [rsp+150h+lpCriticalSection], r12
0x18000ca9b  mov     rcx, r12; lpCriticalSection
0x18000ca9e  call    cs:__imp_EnterCriticalSection
0x18000caa4  mov     [rsp+150h+var_F0], r12
0x18000caa9  mov     rbx, [rbx+50h]
0x18000caad  mov     rbx, [rbx]
0x18000cab0  mov     r12, [rsp+150h+var_130]
0x18000cab5  cmp     byte ptr [rbx+19h], 0
0x18000cab9  jnz     loc_18000CC8C
0x18000cabf  mov     esi, [rbx+20h]
0x18000cac2  xorps   xmm0, xmm0
0x18000cac5  movups  [rsp+150h+var_108], xmm0
0x18000caca  mov     rax, [rbx+30h]
0x18000cace  test    rax, rax
0x18000cad1  jz      short loc_18000CAD7
0x18000cad3  lock inc dword ptr [rax+8]
0x18000cad7  mov     r15, [rbx+28h]
0x18000cadb  mov     qword ptr [rsp+150h+var_108], r15
0x18000cae0  mov     r14, [rbx+30h]
0x18000cae4  mov     [rsp+150h+var_130], r14
0x18000cae9  mov     qword ptr [rsp+150h+var_108+8], r14
0x18000caee  mov     [rbp+50h+var_40], 0
0x18000caf6  lea     rdx, [rbp+50h+var_40]
0x18000cafa  mov     rcx, r15
0x18000cafd  call    ??$query@UINotifyNetworkListManagerEventsPrivate@@@?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UINotifyNetworkListManagerEventsPrivate@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<INotifyNetworkListManagerEventsPrivate>(void)
0x18000cb02  nop
0x18000cb03  xorps   xmm1, xmm1
0x18000cb06  movdqu  [rsp+150h+var_128], xmm1
0x18000cb0c  mov     rcx, [r15+10h]; this
0x18000cb10  test    rcx, rcx
0x18000cb13  jz      loc_18000CC7D
0x18000cb19  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x18000cb1e  test    al, al
0x18000cb20  jz      loc_18000CC7D
0x18000cb26  mov     rdi, [r15+8]
0x18000cb2a  mov     qword ptr [rsp+150h+var_128], rdi
0x18000cb2f  mov     r15, [r15+10h]
0x18000cb33  mov     qword ptr [rsp+150h+var_128+8], r15
0x18000cb38  test    rdi, rdi
0x18000cb3b  jz      loc_18000CC1C
0x18000cb41  mov     [rsp+150h+var_E0], esi
0x18000cb45  mov     eax, [rdi+118h]
0x18000cb4b  mov     [rsp+150h+var_DC], eax
0x18000cb4f  mov     [rsp+150h+var_D8], r12
0x18000cb54  lea     rax, [rbp+50h+var_D0]
0x18000cb58  mov     [rsp+150h+var_110], rax
0x18000cb5d  mov     [rbp+50h+var_98], 0
0x18000cb65  mov     rcx, [r13+38h]
0x18000cb69  test    rcx, rcx
0x18000cb6c  jz      short loc_18000CB81
0x18000cb6e  mov     rax, [rcx]
0x18000cb71  lea     rdx, [rbp+50h+var_D0]
0x18000cb75  mov     rax, [rax]
0x18000cb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb7d  mov     [rbp+50h+var_98], rax
0x18000cb81  mov     rcx, [rbp+50h+var_40]
0x18000cb85  mov     [rbp+50h+var_90], rcx
0x18000cb89  test    rcx, rcx
0x18000cb8c  jz      short loc_18000CB9B
0x18000cb8e  mov     rax, [rcx]
0x18000cb91  mov     rax, [rax+8]
0x18000cb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb9a  nop
0x18000cb9b  mov     [rbp+50h+var_48], 0
0x18000cba3  lea     rcx, [rsp+150h+var_E0]
0x18000cba8  call    ??$_Global_new@V?$_Func_impl_no_alloc@V_lambda_1_@?8???$Notify@UINotifyNetworkListManagerEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkListManagerEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z@X$$V@std@@V_lambda_1_@?8???$Notify@UINotifyNetworkListManagerEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkListManagerEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@2@@Z@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_1_@?8???$Notify@UINotifyNetworkListManagerEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkListManagerEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z@X$$V@0@$$QEAV_lambda_1_@?8???$Notify@UINotifyNetworkListManagerEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkListManagerEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@0@@Z@@Z; std::_Global_new<std::_Func_impl_no_alloc<`ConnectionPoint::Notify<INotifyNetworkListManagerEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkListManagerEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_,void,>,`ConnectionPoint::Notify<INotifyNetworkListManagerEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkListManagerEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_>(`ConnectionPoint::Notify<INotifyNetworkListManagerEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkListManagerEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_ &&)
0x18000cbad  mov     r14, rax
0x18000cbb0  mov     [rbp+50h+var_48], rax
0x18000cbb4  lea     rsi, [rdi+8]
0x18000cbb8  mov     rcx, rsi; lpCriticalSection
0x18000cbbb  call    cs:__imp_EnterCriticalSection
0x18000cbc1  mov     [rsp+150h+var_110], rsi
0x18000cbc6  lea     rcx, [rdi+98h]
0x18000cbcd  cmp     byte ptr [rcx+78h], 0
0x18000cbd1  jz      loc_18000CCFB
0x18000cbd7  test    rsi, rsi
0x18000cbda  jz      short loc_18000CBE6
0x18000cbdc  mov     rcx, rsi; lpCriticalSection
0x18000cbdf  call    cs:__imp_LeaveCriticalSection
0x18000cbe5  nop
0x18000cbe6  test    r14, r14
0x18000cbe9  jz      short loc_18000CC05
0x18000cbeb  mov     rax, [r14]
0x18000cbee  lea     rcx, [rbp+50h+var_80]
0x18000cbf2  cmp     r14, rcx
0x18000cbf5  setnz   dl
0x18000cbf8  mov     rcx, r14
0x18000cbfb  mov     rax, [rax+20h]
0x18000cbff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc04  nop
0x18000cc05  lea     rcx, [rbp+50h+var_90]
0x18000cc09  call    ??1?$com_ptr_t@UINetworkInterfacePrivate@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(void)
0x18000cc0e  lea     rcx, [rbp+50h+var_D0]
0x18000cc12  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18000cc17  mov     r14, [rsp+150h+var_130]
0x18000cc1c  test    r15, r15
0x18000cc1f  jz      short loc_18000CC2A
0x18000cc21  mov     rcx, r15; this
0x18000cc24  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000cc29  nop
0x18000cc2a  mov     rcx, [rbp+50h+var_40]
0x18000cc2e  test    rcx, rcx
0x18000cc31  jz      short loc_18000CC40
0x18000cc33  mov     rax, [rcx]
0x18000cc36  mov     rax, [rax+10h]
0x18000cc3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc3f  nop
0x18000cc40  test    r14, r14
0x18000cc43  jz      short loc_18000CC4D
0x18000cc45  mov     rcx, r14; this
0x18000cc48  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000cc4d  mov     rcx, [rbx+10h]
0x18000cc51  cmp     byte ptr [rcx+19h], 0
0x18000cc55  jnz     short loc_18000CC64
0x18000cc57  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VConnectedProcess@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VConnectedProcess@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<ConnectedProcess>>>>::_Min(std::_Tree_node<std::pair<ulong const,std::shared_ptr<ConnectedProcess>>,void *> *)
0x18000cc5c  mov     rbx, rax
0x18000cc5f  jmp     loc_18000CAB5
0x18000cc64  mov     rax, [rbx+8]
0x18000cc68  cmp     byte ptr [rax+19h], 0
0x18000cc6c  jnz     short loc_18000CC5C
0x18000cc6e  cmp     rbx, [rax+10h]
0x18000cc72  jnz     short loc_18000CC5C
0x18000cc74  mov     rbx, rax
0x18000cc77  mov     rax, [rax+8]
0x18000cc7b  jmp     short loc_18000CC68
0x18000cc7d  mov     r15, qword ptr [rsp+150h+var_128+8]
0x18000cc82  mov     rdi, qword ptr [rsp+150h+var_128]
0x18000cc87  jmp     loc_18000CB38
0x18000cc8c  mov     r12, [rsp+150h+lpCriticalSection]
0x18000cc91  test    r12, r12
0x18000cc94  jz      short loc_18000CCA0
0x18000cc96  mov     rcx, r12; lpCriticalSection
0x18000cc99  call    cs:__imp_LeaveCriticalSection
0x18000cc9f  nop
0x18000cca0  mov     rcx, r13
0x18000cca3  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18000cca8  mov     rcx, [rbp+50h+var_38]
0x18000ccac  xor     rcx, rsp; StackCookie
0x18000ccaf  call    __security_check_cookie
0x18000ccb4  mov     rbx, [rsp+150h+arg_10]
0x18000ccbc  add     rsp, 120h
0x18000ccc3  pop     r15
0x18000ccc5  pop     r14
0x18000ccc7  pop     r13
0x18000ccc9  pop     r12
0x18000cccb  pop     rdi
0x18000cccc  pop     rsi
0x18000cccd  pop     rbp
0x18000ccce  retn
0x18000cccf  test    rsi, rsi
0x18000ccd2  jz      short loc_18000CCDD
0x18000ccd4  mov     rcx, rsi; lpCriticalSection
0x18000ccd7  call    cs:__imp_LeaveCriticalSection
0x18000ccdd  lock inc qword ptr [rdi+88h]
0x18000cce5  mov     rcx, [rdi+80h]; pwk
0x18000ccec  call    cs:__imp_SubmitThreadpoolWork
0x18000ccf2  mov     r14, [rbp+50h+var_48]
0x18000ccf6  jmp     loc_18000CBE6
0x18000ccfb  lea     rdx, [rbp+50h+var_80]
0x18000ccff  cmp     dword ptr [rdi], 1
0x18000cd02  jnz     short loc_18000CD0B
0x18000cd04  call    ??$emplace_back@V?$function@$$A6AXXZ@std@@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::deque<std::function<void (void)>>::emplace_back<std::function<void (void)>>(std::function<void (void)> &&)
0x18000cd09  jmp     short loc_18000CCCF
0x18000cd0b  add     rcx, 50h ; 'P'
0x18000cd0f  call    ??$emplace_back@V?$function@$$A6AXXZ@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV?$function@$$A6AXXZ@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<std::function<void (void)>>(std::function<void (void)> &&)
0x18000cd14  jmp     short loc_18000CCCF
```
