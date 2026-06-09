# ConnectionPoint::Notify<INotifyNetworkEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkEventsPrivate,wil::err_exception_policy> const &)>)

- ea: `0x18000de98`
- end: `0x18000e183`
- name: `??$Notify@UINotifyNetworkEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001805c`

## callees

- `0x18000c160`
- `0x18000d7bc`
- `0x18000de98`
- `0x18000e190`
- `0x18000e1e8`
- `0x180095e54`
- `0x1800a88a0`
- `0x1800be664`
- `0x1800be708`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dedd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e003`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dedd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e003`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e027`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e105`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e143`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e027`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e105`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e143`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000e158`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000e158`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ConnectionPoint::Notify<INotifyNetworkEventsPrivate>(__int64 a1, __int64 a2)
{
  __int64 v4; // r12
  __int64 v5; // rbx
  __int64 v6; // r12
  int v7; // esi
  __int64 v8; // rax
  __int64 v9; // r15
  std::_Ref_count_base *v10; // r14
  __int64 v11; // rdx
  signed __int32 v12; // eax
  signed __int32 v13; // ett
  __int64 v14; // rdi
  std::_Ref_count_base *v15; // r15
  __int64 (__fastcall ***v16)(_QWORD, _BYTE *); // rcx
  _QWORD *v17; // r14
  __int64 v18; // rdx
  _BYTE *v19; // rdx
  __int64 i; // rax
  std::_Ref_count_base *v23; // [rsp+20h] [rbp-E0h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+38h] [rbp-C8h]
  _DWORD v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h]
  _BYTE v27[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v28; // [rsp+A8h] [rbp-58h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  _BYTE v32[56]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v33; // [rsp+108h] [rbp+8h]
  __int64 v34; // [rsp+110h] [rbp+10h] BYREF

  v30 = a2;
  v4 = a1 + 40;
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(a1 + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v31 = v4;
  v5 = **(_QWORD **)(a1 + 80);
  v6 = a1;
  while ( !*(_BYTE *)(v5 + 25) )
  {
    v7 = *(_DWORD *)(v5 + 32);
    v8 = *(_QWORD *)(v5 + 48);
    if ( v8 )
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    v9 = *(_QWORD *)(v5 + 40);
    v10 = *(std::_Ref_count_base **)(v5 + 48);
    v23 = v10;
    v34 = 0;
    wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<INotifyNetworkEventsPrivate>(v9, &v34);
    v11 = *(_QWORD *)(v9 + 16);
    if ( v11 )
    {
      v12 = *(_DWORD *)(v11 + 8);
      while ( v12 )
      {
        v13 = v12;
        v12 = _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 8), v12 + 1, v12);
        if ( v13 == v12 )
        {
          v14 = *(_QWORD *)(v9 + 8);
          v15 = *(std::_Ref_count_base **)(v9 + 16);
          goto LABEL_10;
        }
      }
    }
    v15 = 0;
    v14 = 0;
LABEL_10:
    if ( v14 )
    {
      v25[0] = v7;
      v25[1] = *(_DWORD *)(v14 + 280);
      v26 = v6;
      v28 = 0;
      v16 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a2 + 56);
      if ( v16 )
        v28 = (_BYTE *)(**v16)(v16, v27);
      v29 = v34;
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
      v33 = 0;
      v17 = ____Global_new_V___Func_impl_no_alloc_V_lambda_1___8____Notify_UINotifyNetworkEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkEventsPrivate__Uerr_exception_policy_wil___wil___Z_std___Z_X__V_std__V_lambda_1___8____Notify_UINotifyNetworkEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkEventsPrivate__Uerr_exception_policy_wil___wil___Z_2__Z__std__YAPEAV___Func_impl_no_alloc_V_lambda_1___8____Notify_UINotifyNetworkEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkEventsPrivate__Uerr_exception_policy_wil___wil___Z_std___Z_X__V_0___QEAV_lambda_1___8____Notify_UINotifyNetworkEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkEventsPrivate__Uerr_exception_policy_wil___wil___Z_0__Z__Z((__int64)v25);
      v33 = v17;
      EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
      if ( *(_BYTE *)(v14 + 272) )
      {
        if ( v14 != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
      }
      else
      {
        if ( *(_DWORD *)v14 == 1 )
          std::deque<std::function<void (void)>>::emplace_back<std::function<void (void)>>(v14 + 152, v32);
        else
          std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<std::function<void (void)>>(
            v14 + 232,
            v32);
        if ( v14 != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
        _InterlockedIncrement64((volatile signed __int64 *)(v14 + 136));
        SubmitThreadpoolWork(*(PTP_WORK *)(v14 + 128));
        v17 = v33;
      }
      if ( v17 )
      {
        LOBYTE(v18) = v17 != (_QWORD *)v32;
        (*(void (__fastcall **)(_QWORD *, __int64))(*v17 + 32LL))(v17, v18);
      }
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v28 )
      {
        v19 = v27;
        LOBYTE(v19) = v28 != v27;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v28 + 32LL))(v28, v19);
      }
      v10 = v23;
    }
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
    if ( *(_BYTE *)(*(_QWORD *)(v5 + 16) + 25LL) )
    {
      for ( i = *(_QWORD *)(v5 + 8); !*(_BYTE *)(i + 25) && v5 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
        v5 = i;
    }
    else
    {
      i = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<ConnectedProcess>>>>::_Min();
    }
    v5 = i;
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return std::_Func_class<void,>::~_Func_class<void,>(a2);
}

```

## disassembly

```asm
0x18000de98  mov     [rsp-8+arg_10], rbx
0x18000de9d  push    rbp
0x18000de9e  push    rsi
0x18000de9f  push    rdi
0x18000dea0  push    r12
0x18000dea2  push    r13
0x18000dea4  push    r14
0x18000dea6  push    r15
0x18000dea8  lea     rbp, [rsp-20h]
0x18000dead  sub     rsp, 120h
0x18000deb4  mov     rax, cs:__security_cookie
0x18000debb  xor     rax, rsp
0x18000debe  mov     [rbp+50h+var_38], rax
0x18000dec2  mov     r13, rdx
0x18000dec5  mov     rbx, rcx
0x18000dec8  mov     [rsp+150h+var_130], rcx
0x18000decd  mov     [rbp+50h+var_90], rdx
0x18000ded1  lea     r12, [rcx+28h]
0x18000ded5  mov     [rsp+150h+lpCriticalSection], r12
0x18000deda  mov     rcx, r12; lpCriticalSection
0x18000dedd  call    cs:__imp_EnterCriticalSection
0x18000dee3  mov     [rbp+50h+var_88], r12
0x18000dee7  mov     rbx, [rbx+50h]
0x18000deeb  mov     rbx, [rbx]
0x18000deee  mov     r12, [rsp+150h+var_130]
0x18000def3  cmp     byte ptr [rbx+19h], 0
0x18000def7  jnz     loc_18000E0F8
0x18000defd  mov     esi, [rbx+20h]
0x18000df00  xorps   xmm0, xmm0
0x18000df03  movups  [rsp+150h+var_108], xmm0
0x18000df08  mov     rax, [rbx+30h]
0x18000df0c  test    rax, rax
0x18000df0f  jz      short loc_18000DF15
0x18000df11  lock inc dword ptr [rax+8]
0x18000df15  mov     r15, [rbx+28h]
0x18000df19  mov     qword ptr [rsp+150h+var_108], r15
0x18000df1e  mov     r14, [rbx+30h]
0x18000df22  mov     [rsp+150h+var_130], r14
0x18000df27  mov     qword ptr [rsp+150h+var_108+8], r14
0x18000df2c  mov     [rbp+50h+var_40], 0
0x18000df34  lea     rdx, [rbp+50h+var_40]
0x18000df38  mov     rcx, r15
0x18000df3b  call    ??$query@UINotifyNetworkEventsPrivate@@@?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UINotifyNetworkEventsPrivate@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<INotifyNetworkEventsPrivate>(void)
0x18000df40  nop
0x18000df41  xorps   xmm1, xmm1
0x18000df44  movdqu  [rsp+150h+var_128], xmm1
0x18000df4a  mov     rdx, [r15+10h]
0x18000df4e  test    rdx, rdx
0x18000df51  jz      loc_18000E0E9
0x18000df57  mov     eax, [rdx+8]
0x18000df5a  test    eax, eax
0x18000df5c  jz      loc_18000E0E9
0x18000df62  lea     ecx, [rax+1]
0x18000df65  lock cmpxchg [rdx+8], ecx
0x18000df6a  jnz     short loc_18000DF5A
0x18000df6c  mov     rdi, [r15+8]
0x18000df70  mov     qword ptr [rsp+150h+var_128], rdi
0x18000df75  mov     r15, [r15+10h]
0x18000df79  mov     qword ptr [rsp+150h+var_128+8], r15
0x18000df7e  test    rdi, rdi
0x18000df81  jz      loc_18000E088
0x18000df87  mov     [rsp+150h+var_F0], esi
0x18000df8b  mov     eax, [rdi+118h]
0x18000df91  mov     [rsp+150h+var_EC], eax
0x18000df95  mov     [rsp+150h+var_E8], r12
0x18000df9a  lea     rax, [rsp+150h+var_E0]
0x18000df9f  mov     [rsp+150h+var_110], rax
0x18000dfa4  mov     [rbp+50h+var_A8], 0
0x18000dfac  mov     rcx, [r13+38h]
0x18000dfb0  test    rcx, rcx
0x18000dfb3  jz      short loc_18000DFC9
0x18000dfb5  mov     rax, [rcx]
0x18000dfb8  lea     rdx, [rsp+150h+var_E0]
0x18000dfbd  mov     rax, [rax]
0x18000dfc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfc5  mov     [rbp+50h+var_A8], rax
0x18000dfc9  mov     rcx, [rbp+50h+var_40]
0x18000dfcd  mov     [rbp+50h+var_A0], rcx
0x18000dfd1  test    rcx, rcx
0x18000dfd4  jz      short loc_18000DFE3
0x18000dfd6  mov     rax, [rcx]
0x18000dfd9  mov     rax, [rax+8]
0x18000dfdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfe2  nop
0x18000dfe3  mov     [rbp+50h+var_48], 0
0x18000dfeb  lea     rcx, [rsp+150h+var_F0]
0x18000dff0  call    ??$_Global_new@V?$_Func_impl_no_alloc@V_lambda_1_@?8???$Notify@UINotifyNetworkEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z@X$$V@std@@V_lambda_1_@?8???$Notify@UINotifyNetworkEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@2@@Z@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_1_@?8???$Notify@UINotifyNetworkEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z@X$$V@0@$$QEAV_lambda_1_@?8???$Notify@UINotifyNetworkEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@0@@Z@@Z; std::_Global_new<std::_Func_impl_no_alloc<`ConnectionPoint::Notify<INotifyNetworkEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_,void,>,`ConnectionPoint::Notify<INotifyNetworkEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_>(`ConnectionPoint::Notify<INotifyNetworkEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_ &&)
0x18000dff5  mov     r14, rax
0x18000dff8  mov     [rbp+50h+var_48], rax
0x18000dffc  lea     rsi, [rdi+8]
0x18000e000  mov     rcx, rsi; lpCriticalSection
0x18000e003  call    cs:__imp_EnterCriticalSection
0x18000e009  mov     [rsp+150h+var_110], rsi
0x18000e00e  lea     rcx, [rdi+98h]
0x18000e015  cmp     byte ptr [rcx+78h], 0
0x18000e019  jz      loc_18000E167
0x18000e01f  test    rsi, rsi
0x18000e022  jz      short loc_18000E02E
0x18000e024  mov     rcx, rsi; lpCriticalSection
0x18000e027  call    cs:__imp_LeaveCriticalSection
0x18000e02d  nop
0x18000e02e  test    r14, r14
0x18000e031  jz      short loc_18000E04D
0x18000e033  mov     rax, [r14]
0x18000e036  lea     rcx, [rbp+50h+var_80]
0x18000e03a  cmp     r14, rcx
0x18000e03d  setnz   dl
0x18000e040  mov     rcx, r14
0x18000e043  mov     rax, [rax+20h]
0x18000e047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e04c  nop
0x18000e04d  mov     rcx, [rbp+50h+var_A0]
0x18000e051  test    rcx, rcx
0x18000e054  jz      short loc_18000E063
0x18000e056  mov     rax, [rcx]
0x18000e059  mov     rax, [rax+10h]
0x18000e05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e062  nop
0x18000e063  mov     rcx, [rbp+50h+var_A8]
0x18000e067  test    rcx, rcx
0x18000e06a  jz      short loc_18000E083
0x18000e06c  mov     rax, [rcx]
0x18000e06f  lea     rdx, [rsp+150h+var_E0]
0x18000e074  cmp     rcx, rdx
0x18000e077  setnz   dl
0x18000e07a  mov     rax, [rax+20h]
0x18000e07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e083  mov     r14, [rsp+150h+var_130]
0x18000e088  test    r15, r15
0x18000e08b  jz      short loc_18000E096
0x18000e08d  mov     rcx, r15; this
0x18000e090  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e095  nop
0x18000e096  mov     rcx, [rbp+50h+var_40]
0x18000e09a  test    rcx, rcx
0x18000e09d  jz      short loc_18000E0AC
0x18000e09f  mov     rax, [rcx]
0x18000e0a2  mov     rax, [rax+10h]
0x18000e0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0ab  nop
0x18000e0ac  test    r14, r14
0x18000e0af  jz      short loc_18000E0B9
0x18000e0b1  mov     rcx, r14; this
0x18000e0b4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e0b9  mov     rcx, [rbx+10h]
0x18000e0bd  cmp     byte ptr [rcx+19h], 0
0x18000e0c1  jnz     short loc_18000E0D0
0x18000e0c3  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VConnectedProcess@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VConnectedProcess@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<ConnectedProcess>>>>::_Min(std::_Tree_node<std::pair<ulong const,std::shared_ptr<ConnectedProcess>>,void *> *)
0x18000e0c8  mov     rbx, rax
0x18000e0cb  jmp     loc_18000DEF3
0x18000e0d0  mov     rax, [rbx+8]
0x18000e0d4  cmp     byte ptr [rax+19h], 0
0x18000e0d8  jnz     short loc_18000E0C8
0x18000e0da  cmp     rbx, [rax+10h]
0x18000e0de  jnz     short loc_18000E0C8
0x18000e0e0  mov     rbx, rax
0x18000e0e3  mov     rax, [rax+8]
0x18000e0e7  jmp     short loc_18000E0D4
0x18000e0e9  mov     r15, qword ptr [rsp+150h+var_128+8]
0x18000e0ee  mov     rdi, qword ptr [rsp+150h+var_128]
0x18000e0f3  jmp     loc_18000DF7E
0x18000e0f8  mov     r12, [rsp+150h+lpCriticalSection]
0x18000e0fd  test    r12, r12
0x18000e100  jz      short loc_18000E10C
0x18000e102  mov     rcx, r12; lpCriticalSection
0x18000e105  call    cs:__imp_LeaveCriticalSection
0x18000e10b  nop
0x18000e10c  mov     rcx, r13
0x18000e10f  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18000e114  mov     rcx, [rbp+50h+var_38]
0x18000e118  xor     rcx, rsp; StackCookie
0x18000e11b  call    __security_check_cookie
0x18000e120  mov     rbx, [rsp+150h+arg_10]
0x18000e128  add     rsp, 120h
0x18000e12f  pop     r15
0x18000e131  pop     r14
0x18000e133  pop     r13
0x18000e135  pop     r12
0x18000e137  pop     rdi
0x18000e138  pop     rsi
0x18000e139  pop     rbp
0x18000e13a  retn
0x18000e13b  test    rsi, rsi
0x18000e13e  jz      short loc_18000E149
0x18000e140  mov     rcx, rsi; lpCriticalSection
0x18000e143  call    cs:__imp_LeaveCriticalSection
0x18000e149  lock inc qword ptr [rdi+88h]
0x18000e151  mov     rcx, [rdi+80h]; pwk
0x18000e158  call    cs:__imp_SubmitThreadpoolWork
0x18000e15e  mov     r14, [rbp+50h+var_48]
0x18000e162  jmp     loc_18000E02E
0x18000e167  lea     rdx, [rbp+50h+var_80]
0x18000e16b  cmp     dword ptr [rdi], 1
0x18000e16e  jnz     short loc_18000E177
0x18000e170  call    ??$emplace_back@V?$function@$$A6AXXZ@std@@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::deque<std::function<void (void)>>::emplace_back<std::function<void (void)>>(std::function<void (void)> &&)
0x18000e175  jmp     short loc_18000E13B
0x18000e177  add     rcx, 50h ; 'P'
0x18000e17b  call    ??$emplace_back@V?$function@$$A6AXXZ@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV?$function@$$A6AXXZ@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<std::function<void (void)>>(std::function<void (void)> &&)
0x18000e180  jmp     short loc_18000E13B
```
