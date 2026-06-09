# ConnectionPoint::Notify<INotifyNetworkInterfaceEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkInterfaceEventsPrivate,wil::err_exception_policy> const &)>)

- ea: `0x18000dbbc`
- end: `0x18000de90`
- name: `??$Notify@UINotifyNetworkInterfaceEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkInterfaceEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z`
- size: `724`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017f1c`

## callees

- `0x18000c160`
- `0x18000d7bc`
- `0x18000dbbc`
- `0x18000e190`
- `0x18000e5c0`
- `0x18006e7d4`
- `0x1800a88a0`
- `0x1800be664`
- `0x1800be708`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dc02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dc02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ddea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ddea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de50`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000de65`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000de65`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ConnectionPoint::Notify<INotifyNetworkInterfaceEventsPrivate>(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // r12
  int v6; // esi
  __int64 v7; // rax
  __int64 v8; // r15
  std::_Ref_count_base *v9; // r14
  __int64 v10; // rdx
  signed __int32 v11; // eax
  signed __int32 v12; // ett
  __int64 v13; // rdi
  std::_Ref_count_base *v14; // r15
  __int64 (__fastcall ***v15)(_QWORD, _BYTE *); // rcx
  _DWORD *v16; // r14
  __int64 v17; // rdx
  __int64 i; // rax
  std::_Ref_count_base *v21; // [rsp+20h] [rbp-E0h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+38h] [rbp-C8h]
  _DWORD v23[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h]
  _BYTE v25[56]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+B8h] [rbp-48h]
  __int64 v27; // [rsp+C0h] [rbp-40h]
  _BYTE v28[56]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD *v29; // [rsp+108h] [rbp+8h]
  __int64 v30; // [rsp+110h] [rbp+10h] BYREF

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
    v21 = v9;
    v30 = 0;
    wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<INotifyNetworkInterfaceEventsPrivate>(v8, &v30);
    v10 = *(_QWORD *)(v8 + 16);
    if ( v10 )
    {
      v11 = *(_DWORD *)(v10 + 8);
      while ( v11 )
      {
        v12 = v11;
        v11 = _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 8), v11 + 1, v11);
        if ( v12 == v11 )
        {
          v13 = *(_QWORD *)(v8 + 8);
          v14 = *(std::_Ref_count_base **)(v8 + 16);
          goto LABEL_10;
        }
      }
    }
    v14 = 0;
    v13 = 0;
LABEL_10:
    if ( v13 )
    {
      v23[0] = v6;
      v23[1] = *(_DWORD *)(v13 + 280);
      v24 = v5;
      v26 = 0;
      v15 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a2 + 56);
      if ( v15 )
        v26 = (**v15)(v15, v25);
      v27 = v30;
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
      v29 = 0;
      v16 = ____Global_new_V___Func_impl_no_alloc_V_lambda_1___8____Notify_UINotifyNetworkInterfaceEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkInterfaceEventsPrivate__Uerr_exception_policy_wil___wil___Z_std___Z_X__V_std__V_lambda_1___8____Notify_UINotifyNetworkInterfaceEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkInterfaceEventsPrivate__Uerr_exception_policy_wil___wil___Z_2__Z__std__YAPEAV___Func_impl_no_alloc_V_lambda_1___8____Notify_UINotifyNetworkInterfaceEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkInterfaceEventsPrivate__Uerr_exception_policy_wil___wil___Z_std___Z_X__V_0___QEAV_lambda_1___8____Notify_UINotifyNetworkInterfaceEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkInterfaceEventsPrivate__Uerr_exception_policy_wil___wil___Z_0__Z__Z((__int64)v23);
      v29 = v16;
      EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
      if ( *(_BYTE *)(v13 + 272) )
      {
        if ( v13 != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
      }
      else
      {
        if ( *(_DWORD *)v13 == 1 )
          std::deque<std::function<void (void)>>::emplace_back<std::function<void (void)>>(v13 + 152, v28);
        else
          std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<std::function<void (void)>>(
            v13 + 232,
            v28);
        if ( v13 != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
        _InterlockedIncrement64((volatile signed __int64 *)(v13 + 136));
        SubmitThreadpoolWork(*(PTP_WORK *)(v13 + 128));
        v16 = v29;
      }
      if ( v16 )
      {
        LOBYTE(v17) = v16 != (_DWORD *)v28;
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v16 + 32LL))(v16, v17);
      }
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      std::_Func_class<void,>::~_Func_class<void,>(v25);
      v9 = v21;
    }
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
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
0x18000dbbc  mov     [rsp-8+arg_10], rbx
0x18000dbc1  push    rbp
0x18000dbc2  push    rsi
0x18000dbc3  push    rdi
0x18000dbc4  push    r12
0x18000dbc6  push    r13
0x18000dbc8  push    r14
0x18000dbca  push    r15
0x18000dbcc  lea     rbp, [rsp-20h]
0x18000dbd1  sub     rsp, 120h
0x18000dbd8  mov     rax, cs:__security_cookie
0x18000dbdf  xor     rax, rsp
0x18000dbe2  mov     [rbp+50h+var_38], rax
0x18000dbe6  mov     r13, rdx
0x18000dbe9  mov     rbx, rcx
0x18000dbec  mov     [rsp+150h+var_130], rcx
0x18000dbf1  mov     [rsp+150h+var_F8], rdx
0x18000dbf6  lea     r12, [rcx+28h]
0x18000dbfa  mov     [rsp+150h+lpCriticalSection], r12
0x18000dbff  mov     rcx, r12; lpCriticalSection
0x18000dc02  call    cs:__imp_EnterCriticalSection
0x18000dc08  mov     [rsp+150h+var_F0], r12
0x18000dc0d  mov     rbx, [rbx+50h]
0x18000dc11  mov     rbx, [rbx]
0x18000dc14  mov     r12, [rsp+150h+var_130]
0x18000dc19  cmp     byte ptr [rbx+19h], 0
0x18000dc1d  jnz     loc_18000DDDD
0x18000dc23  mov     esi, [rbx+20h]
0x18000dc26  xorps   xmm0, xmm0
0x18000dc29  movups  [rsp+150h+var_108], xmm0
0x18000dc2e  mov     rax, [rbx+30h]
0x18000dc32  test    rax, rax
0x18000dc35  jz      short loc_18000DC3B
0x18000dc37  lock inc dword ptr [rax+8]
0x18000dc3b  mov     r15, [rbx+28h]
0x18000dc3f  mov     qword ptr [rsp+150h+var_108], r15
0x18000dc44  mov     r14, [rbx+30h]
0x18000dc48  mov     [rsp+150h+var_130], r14
0x18000dc4d  mov     qword ptr [rsp+150h+var_108+8], r14
0x18000dc52  mov     [rbp+50h+var_40], 0
0x18000dc5a  lea     rdx, [rbp+50h+var_40]
0x18000dc5e  mov     rcx, r15
0x18000dc61  call    ??$query@UINotifyNetworkInterfaceEventsPrivate@@@?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UINotifyNetworkInterfaceEventsPrivate@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<INotifyNetworkInterfaceEventsPrivate>(void)
0x18000dc66  nop
0x18000dc67  xorps   xmm1, xmm1
0x18000dc6a  movdqu  [rsp+150h+var_128], xmm1
0x18000dc70  mov     rdx, [r15+10h]
0x18000dc74  test    rdx, rdx
0x18000dc77  jz      loc_18000DE39
0x18000dc7d  mov     eax, [rdx+8]
0x18000dc80  test    eax, eax
0x18000dc82  jz      loc_18000DE39
0x18000dc88  lea     ecx, [rax+1]
0x18000dc8b  lock cmpxchg [rdx+8], ecx
0x18000dc90  jnz     short loc_18000DC80
0x18000dc92  mov     rdi, [r15+8]
0x18000dc96  mov     qword ptr [rsp+150h+var_128], rdi
0x18000dc9b  mov     r15, [r15+10h]
0x18000dc9f  mov     qword ptr [rsp+150h+var_128+8], r15
0x18000dca4  test    rdi, rdi
0x18000dca7  jz      loc_18000DD95
0x18000dcad  mov     [rsp+150h+var_E0], esi
0x18000dcb1  mov     eax, [rdi+118h]
0x18000dcb7  mov     [rsp+150h+var_DC], eax
0x18000dcbb  mov     [rsp+150h+var_D8], r12
0x18000dcc0  lea     rax, [rbp+50h+var_D0]
0x18000dcc4  mov     [rsp+150h+var_110], rax
0x18000dcc9  mov     [rbp+50h+var_98], 0
0x18000dcd1  mov     rcx, [r13+38h]
0x18000dcd5  test    rcx, rcx
0x18000dcd8  jz      short loc_18000DCED
0x18000dcda  mov     rax, [rcx]
0x18000dcdd  lea     rdx, [rbp+50h+var_D0]
0x18000dce1  mov     rax, [rax]
0x18000dce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce9  mov     [rbp+50h+var_98], rax
0x18000dced  mov     rcx, [rbp+50h+var_40]
0x18000dcf1  mov     [rbp+50h+var_90], rcx
0x18000dcf5  test    rcx, rcx
0x18000dcf8  jz      short loc_18000DD07
0x18000dcfa  mov     rax, [rcx]
0x18000dcfd  mov     rax, [rax+8]
0x18000dd01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd06  nop
0x18000dd07  mov     [rbp+50h+var_48], 0
0x18000dd0f  lea     rcx, [rsp+150h+var_E0]
0x18000dd14  call    ??$_Global_new@V?$_Func_impl_no_alloc@V_lambda_1_@?8???$Notify@UINotifyNetworkInterfaceEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkInterfaceEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z@X$$V@std@@V_lambda_1_@?8???$Notify@UINotifyNetworkInterfaceEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkInterfaceEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@2@@Z@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_1_@?8???$Notify@UINotifyNetworkInterfaceEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkInterfaceEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z@X$$V@0@$$QEAV_lambda_1_@?8???$Notify@UINotifyNetworkInterfaceEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkInterfaceEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@0@@Z@@Z; std::_Global_new<std::_Func_impl_no_alloc<`ConnectionPoint::Notify<INotifyNetworkInterfaceEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkInterfaceEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_,void,>,`ConnectionPoint::Notify<INotifyNetworkInterfaceEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkInterfaceEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_>(`ConnectionPoint::Notify<INotifyNetworkInterfaceEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkInterfaceEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_ &&)
0x18000dd19  mov     r14, rax
0x18000dd1c  mov     [rbp+50h+var_48], rax
0x18000dd20  lea     rsi, [rdi+8]
0x18000dd24  mov     rcx, rsi; lpCriticalSection
0x18000dd27  call    cs:__imp_EnterCriticalSection
0x18000dd2d  mov     [rsp+150h+var_110], rsi
0x18000dd32  lea     rcx, [rdi+98h]
0x18000dd39  cmp     byte ptr [rcx+78h], 0
0x18000dd3d  jz      loc_18000DE74
0x18000dd43  test    rsi, rsi
0x18000dd46  jz      short loc_18000DD52
0x18000dd48  mov     rcx, rsi; lpCriticalSection
0x18000dd4b  call    cs:__imp_LeaveCriticalSection
0x18000dd51  nop
0x18000dd52  test    r14, r14
0x18000dd55  jz      short loc_18000DD71
0x18000dd57  mov     rax, [r14]
0x18000dd5a  lea     rcx, [rbp+50h+var_80]
0x18000dd5e  cmp     r14, rcx
0x18000dd61  setnz   dl
0x18000dd64  mov     rcx, r14
0x18000dd67  mov     rax, [rax+20h]
0x18000dd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd70  nop
0x18000dd71  mov     rcx, [rbp+50h+var_90]
0x18000dd75  test    rcx, rcx
0x18000dd78  jz      short loc_18000DD87
0x18000dd7a  mov     rax, [rcx]
0x18000dd7d  mov     rax, [rax+10h]
0x18000dd81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd86  nop
0x18000dd87  lea     rcx, [rbp+50h+var_D0]
0x18000dd8b  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18000dd90  mov     r14, [rsp+150h+var_130]
0x18000dd95  test    r15, r15
0x18000dd98  jz      short loc_18000DDA3
0x18000dd9a  mov     rcx, r15; this
0x18000dd9d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000dda2  nop
0x18000dda3  mov     rcx, [rbp+50h+var_40]
0x18000dda7  test    rcx, rcx
0x18000ddaa  jz      short loc_18000DDB9
0x18000ddac  mov     rax, [rcx]
0x18000ddaf  mov     rax, [rax+10h]
0x18000ddb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddb8  nop
0x18000ddb9  test    r14, r14
0x18000ddbc  jz      short loc_18000DDC6
0x18000ddbe  mov     rcx, r14; this
0x18000ddc1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ddc6  mov     rcx, [rbx+10h]
0x18000ddca  cmp     byte ptr [rcx+19h], 0
0x18000ddce  jnz     short loc_18000DE20
0x18000ddd0  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VConnectedProcess@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VConnectedProcess@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<ConnectedProcess>>>>::_Min(std::_Tree_node<std::pair<ulong const,std::shared_ptr<ConnectedProcess>>,void *> *)
0x18000ddd5  mov     rbx, rax
0x18000ddd8  jmp     loc_18000DC19
0x18000dddd  mov     r12, [rsp+150h+lpCriticalSection]
0x18000dde2  test    r12, r12
0x18000dde5  jz      short loc_18000DDF1
0x18000dde7  mov     rcx, r12; lpCriticalSection
0x18000ddea  call    cs:__imp_LeaveCriticalSection
0x18000ddf0  nop
0x18000ddf1  mov     rcx, r13
0x18000ddf4  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18000ddf9  mov     rcx, [rbp+50h+var_38]
0x18000ddfd  xor     rcx, rsp; StackCookie
0x18000de00  call    __security_check_cookie
0x18000de05  mov     rbx, [rsp+150h+arg_10]
0x18000de0d  add     rsp, 120h
0x18000de14  pop     r15
0x18000de16  pop     r14
0x18000de18  pop     r13
0x18000de1a  pop     r12
0x18000de1c  pop     rdi
0x18000de1d  pop     rsi
0x18000de1e  pop     rbp
0x18000de1f  retn
0x18000de20  mov     rax, [rbx+8]
0x18000de24  cmp     byte ptr [rax+19h], 0
0x18000de28  jnz     short loc_18000DDD5
0x18000de2a  cmp     rbx, [rax+10h]
0x18000de2e  jnz     short loc_18000DDD5
0x18000de30  mov     rbx, rax
0x18000de33  mov     rax, [rax+8]
0x18000de37  jmp     short loc_18000DE24
0x18000de39  mov     r15, qword ptr [rsp+150h+var_128+8]
0x18000de3e  mov     rdi, qword ptr [rsp+150h+var_128]
0x18000de43  jmp     loc_18000DCA4
0x18000de48  test    rsi, rsi
0x18000de4b  jz      short loc_18000DE56
0x18000de4d  mov     rcx, rsi; lpCriticalSection
0x18000de50  call    cs:__imp_LeaveCriticalSection
0x18000de56  lock inc qword ptr [rdi+88h]
0x18000de5e  mov     rcx, [rdi+80h]; pwk
0x18000de65  call    cs:__imp_SubmitThreadpoolWork
0x18000de6b  mov     r14, [rbp+50h+var_48]
0x18000de6f  jmp     loc_18000DD52
0x18000de74  lea     rdx, [rbp+50h+var_80]
0x18000de78  cmp     dword ptr [rdi], 1
0x18000de7b  jnz     short loc_18000DE84
0x18000de7d  call    ??$emplace_back@V?$function@$$A6AXXZ@std@@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::deque<std::function<void (void)>>::emplace_back<std::function<void (void)>>(std::function<void (void)> &&)
0x18000de82  jmp     short loc_18000DE48
0x18000de84  add     rcx, 50h ; 'P'
0x18000de88  call    ??$emplace_back@V?$function@$$A6AXXZ@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV?$function@$$A6AXXZ@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<std::function<void (void)>>(std::function<void (void)> &&)
0x18000de8d  jmp     short loc_18000DE48
```
