# ConnectionPoint::Notify<INotifyNetworkGlobalStateEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkGlobalStateEventsPrivate,wil::err_exception_policy> const &)>)

- ea: `0x180017954`
- end: `0x180017caa`
- name: `??$Notify@UINotifyNetworkGlobalStateEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkGlobalStateEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z`
- size: `854`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017db4`

## callees

- `0x18000c160`
- `0x180015ae8`
- `0x180017954`
- `0x180017cb0`
- `0x18006e02c`
- `0x1800a88a0`
- `0x1800be664`
- `0x1800be708`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001799e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ac1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001799e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ac1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017ae5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017bf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017ae5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017bf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c6a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180017c7f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180017c7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ConnectionPoint::Notify<INotifyNetworkGlobalStateEventsPrivate>(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 v4; // r13
  __int64 *v5; // rbx
  int v6; // r14d
  __int64 v7; // rax
  __int64 v8; // rsi
  volatile signed __int32 *v9; // r12
  __int64 v10; // rdx
  signed __int32 v11; // eax
  signed __int32 v12; // ett
  __int128 v13; // rdi
  __int64 (__fastcall ***v14)(_QWORD, _BYTE *); // rcx
  _DWORD *v15; // r15
  __int64 v16; // rdx
  _BYTE *v17; // rdx
  __int64 **v18; // rcx
  __int64 *j; // rcx
  __int64 *i; // rax
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+40h] [rbp-C0h]
  _DWORD v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h]
  _BYTE v27[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v28; // [rsp+A8h] [rbp-58h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  _BYTE v32[56]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD *v33; // [rsp+108h] [rbp+8h]
  __int64 v34; // [rsp+110h] [rbp+10h] BYREF

  v2 = a2;
  v30 = a2;
  v4 = a1 + 40;
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(a1 + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v31 = v4;
  v5 = **(__int64 ***)(a1 + 80);
  while ( !*((_BYTE *)v5 + 25) )
  {
    v6 = *((_DWORD *)v5 + 8);
    v7 = v5[6];
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
    v8 = v5[5];
    v9 = (volatile signed __int32 *)v5[6];
    v34 = 0;
    wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<INotifyNetworkGlobalStateEventsPrivate>(v8, &v34);
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
          v13 = *(_OWORD *)(v8 + 8);
          goto LABEL_10;
        }
      }
    }
    v13 = 0;
LABEL_10:
    if ( (_QWORD)v13 )
    {
      v25[0] = v6;
      v25[1] = *(_DWORD *)(v13 + 280);
      v26 = a1;
      v28 = 0;
      v14 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(v2 + 56);
      if ( v14 )
        v28 = (_BYTE *)(**v14)(v14, v27);
      v29 = v34;
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
      v33 = 0;
      v15 = ____Global_new_V___Func_impl_no_alloc_V_lambda_1___8____Notify_UINotifyNetworkGlobalStateEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkGlobalStateEventsPrivate__Uerr_exception_policy_wil___wil___Z_std___Z_X__V_std__V_lambda_1___8____Notify_UINotifyNetworkGlobalStateEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkGlobalStateEventsPrivate__Uerr_exception_policy_wil___wil___Z_2__Z__std__YAPEAV___Func_impl_no_alloc_V_lambda_1___8____Notify_UINotifyNetworkGlobalStateEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkGlobalStateEventsPrivate__Uerr_exception_policy_wil___wil___Z_std___Z_X__V_0___QEAV_lambda_1___8____Notify_UINotifyNetworkGlobalStateEventsPrivate___ConnectionPoint__QEAAXV__function___A6AJAEBV__com_ptr_t_UINotifyNetworkGlobalStateEventsPrivate__Uerr_exception_policy_wil___wil___Z_0__Z__Z((__int64)v25);
      v33 = v15;
      EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
      if ( *(_BYTE *)(v13 + 272) )
      {
        if ( (_QWORD)v13 != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
      }
      else
      {
        if ( *(_DWORD *)v13 == 1 )
          std::deque<std::function<void (void)>>::emplace_back<std::function<void (void)>>(v13 + 152, v32);
        else
          std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<std::function<void (void)>>(
            v13 + 232,
            v32);
        if ( (_QWORD)v13 != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
        _InterlockedIncrement64((volatile signed __int64 *)(v13 + 136));
        SubmitThreadpoolWork(*(PTP_WORK *)(v13 + 128));
        v15 = v33;
      }
      if ( v15 )
      {
        LOBYTE(v16) = v15 != (_DWORD *)v32;
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v15 + 32LL))(v15, v16);
      }
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v28 )
      {
        v17 = v27;
        LOBYTE(v17) = v28 != v27;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v28 + 32LL))(v28, v17);
      }
      v2 = a2;
    }
    if ( *((_QWORD *)&v13 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v13 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v13 + 1))(*((_QWORD *)&v13 + 1));
      std::_Ref_count_base::_Decwref(*((std::_Ref_count_base **)&v13 + 1));
    }
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( v9 && _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v9);
    }
    v18 = (__int64 **)v5[2];
    if ( *((_BYTE *)v18 + 25) )
    {
      for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25) && v5 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v5 = i;
      v5 = i;
    }
    else
    {
      v5 = (__int64 *)v5[2];
      for ( j = *v18; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v5 = j;
    }
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return std::_Func_class<void,>::~_Func_class<void,>(v2);
}

```

## disassembly

```asm
0x180017954  mov     [rsp-8+arg_10], rbx
0x180017959  push    rbp
0x18001795a  push    rsi
0x18001795b  push    rdi
0x18001795c  push    r12
0x18001795e  push    r13
0x180017960  push    r14
0x180017962  push    r15
0x180017964  lea     rbp, [rsp-20h]
0x180017969  sub     rsp, 120h
0x180017970  mov     rax, cs:__security_cookie
0x180017977  xor     rax, rsp
0x18001797a  mov     [rbp+50h+var_38], rax
0x18001797e  mov     r15, rdx
0x180017981  mov     [rsp+150h+var_128], rdx
0x180017986  mov     rbx, rcx
0x180017989  mov     [rsp+150h+var_130], rcx
0x18001798e  mov     [rbp+50h+var_90], rdx
0x180017992  lea     r13, [rcx+28h]
0x180017996  mov     [rsp+150h+lpCriticalSection], r13
0x18001799b  mov     rcx, r13; lpCriticalSection
0x18001799e  call    cs:__imp_EnterCriticalSection
0x1800179a4  mov     [rbp+50h+var_88], r13
0x1800179a8  mov     rbx, [rbx+50h]
0x1800179ac  mov     rbx, [rbx]
0x1800179af  mov     r13, [rsp+150h+var_130]
0x1800179b4  cmp     byte ptr [rbx+19h], 0
0x1800179b8  jnz     loc_180017BE8
0x1800179be  mov     r14d, [rbx+20h]
0x1800179c2  xorps   xmm0, xmm0
0x1800179c5  movups  [rsp+150h+var_108], xmm0
0x1800179ca  mov     rax, [rbx+30h]
0x1800179ce  test    rax, rax
0x1800179d1  jz      short loc_1800179D7
0x1800179d3  lock inc dword ptr [rax+8]
0x1800179d7  mov     rsi, [rbx+28h]
0x1800179db  mov     qword ptr [rsp+150h+var_108], rsi
0x1800179e0  mov     r12, [rbx+30h]
0x1800179e4  mov     qword ptr [rsp+150h+var_108+8], r12
0x1800179e9  mov     [rbp+50h+var_40], 0
0x1800179f1  lea     rdx, [rbp+50h+var_40]
0x1800179f5  mov     rcx, rsi
0x1800179f8  call    ??$query@UINotifyNetworkGlobalStateEventsPrivate@@@?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UINotifyNetworkGlobalStateEventsPrivate@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<INotifyNetworkGlobalStateEventsPrivate>(void)
0x1800179fd  nop
0x1800179fe  xorps   xmm1, xmm1
0x180017a01  movdqu  [rsp+150h+var_120], xmm1
0x180017a07  mov     rdx, [rsi+10h]
0x180017a0b  test    rdx, rdx
0x180017a0e  jz      loc_180017BD9
0x180017a14  mov     eax, [rdx+8]
0x180017a17  test    eax, eax
0x180017a19  jz      loc_180017BD9
0x180017a1f  lea     ecx, [rax+1]
0x180017a22  lock cmpxchg [rdx+8], ecx
0x180017a27  jnz     short loc_180017A17
0x180017a29  mov     rdi, [rsi+8]
0x180017a2d  mov     qword ptr [rsp+150h+var_120], rdi
0x180017a32  mov     rsi, [rsi+10h]
0x180017a36  mov     qword ptr [rsp+150h+var_120+8], rsi
0x180017a3b  test    rdi, rdi
0x180017a3e  jz      loc_180017B46
0x180017a44  mov     [rsp+150h+var_F0], r14d
0x180017a49  mov     eax, [rdi+118h]
0x180017a4f  mov     [rsp+150h+var_EC], eax
0x180017a53  mov     [rsp+150h+var_E8], r13
0x180017a58  lea     rax, [rsp+150h+var_E0]
0x180017a5d  mov     [rsp+150h+var_130], rax
0x180017a62  mov     [rbp+50h+var_A8], 0
0x180017a6a  mov     rcx, [r15+38h]
0x180017a6e  test    rcx, rcx
0x180017a71  jz      short loc_180017A87
0x180017a73  mov     rax, [rcx]
0x180017a76  lea     rdx, [rsp+150h+var_E0]
0x180017a7b  mov     rax, [rax]
0x180017a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a83  mov     [rbp+50h+var_A8], rax
0x180017a87  mov     rcx, [rbp+50h+var_40]
0x180017a8b  mov     [rbp+50h+var_A0], rcx
0x180017a8f  test    rcx, rcx
0x180017a92  jz      short loc_180017AA1
0x180017a94  mov     rax, [rcx]
0x180017a97  mov     rax, [rax+8]
0x180017a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aa0  nop
0x180017aa1  mov     [rbp+50h+var_48], 0
0x180017aa9  lea     rcx, [rsp+150h+var_F0]
0x180017aae  call    ??$_Global_new@V?$_Func_impl_no_alloc@V_lambda_1_@?8???$Notify@UINotifyNetworkGlobalStateEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkGlobalStateEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z@X$$V@std@@V_lambda_1_@?8???$Notify@UINotifyNetworkGlobalStateEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkGlobalStateEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@2@@Z@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_1_@?8???$Notify@UINotifyNetworkGlobalStateEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkGlobalStateEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@std@@@Z@X$$V@0@$$QEAV_lambda_1_@?8???$Notify@UINotifyNetworkGlobalStateEventsPrivate@@@ConnectionPoint@@QEAAXV?$function@$$A6AJAEBV?$com_ptr_t@UINotifyNetworkGlobalStateEventsPrivate@@Uerr_exception_policy@wil@@@wil@@@Z@0@@Z@@Z; std::_Global_new<std::_Func_impl_no_alloc<`ConnectionPoint::Notify<INotifyNetworkGlobalStateEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkGlobalStateEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_,void,>,`ConnectionPoint::Notify<INotifyNetworkGlobalStateEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkGlobalStateEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_>(`ConnectionPoint::Notify<INotifyNetworkGlobalStateEventsPrivate>(std::function<long (wil::com_ptr_t<INotifyNetworkGlobalStateEventsPrivate,wil::err_exception_policy> const &)>)'::`9'::_lambda_1_ &&)
0x180017ab3  mov     r15, rax
0x180017ab6  mov     [rbp+50h+var_48], rax
0x180017aba  lea     r14, [rdi+8]
0x180017abe  mov     rcx, r14; lpCriticalSection
0x180017ac1  call    cs:__imp_EnterCriticalSection
0x180017ac7  mov     [rsp+150h+var_130], r14
0x180017acc  lea     rcx, [rdi+98h]
0x180017ad3  cmp     byte ptr [rcx+78h], 0
0x180017ad7  jz      loc_180017C8E
0x180017add  test    r14, r14
0x180017ae0  jz      short loc_180017AEC
0x180017ae2  mov     rcx, r14; lpCriticalSection
0x180017ae5  call    cs:__imp_LeaveCriticalSection
0x180017aeb  nop
0x180017aec  test    r15, r15
0x180017aef  jz      short loc_180017B0B
0x180017af1  mov     rax, [r15]
0x180017af4  lea     rcx, [rbp+50h+var_80]
0x180017af8  cmp     r15, rcx
0x180017afb  setnz   dl
0x180017afe  mov     rcx, r15
0x180017b01  mov     rax, [rax+20h]
0x180017b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b0a  nop
0x180017b0b  mov     rcx, [rbp+50h+var_A0]
0x180017b0f  test    rcx, rcx
0x180017b12  jz      short loc_180017B21
0x180017b14  mov     rax, [rcx]
0x180017b17  mov     rax, [rax+10h]
0x180017b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b20  nop
0x180017b21  mov     rcx, [rbp+50h+var_A8]
0x180017b25  test    rcx, rcx
0x180017b28  jz      short loc_180017B41
0x180017b2a  mov     rax, [rcx]
0x180017b2d  lea     rdx, [rsp+150h+var_E0]
0x180017b32  cmp     rcx, rdx
0x180017b35  setnz   dl
0x180017b38  mov     rax, [rax+20h]
0x180017b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b41  mov     r15, [rsp+150h+var_128]
0x180017b46  test    rsi, rsi
0x180017b49  jz      short loc_180017B5C
0x180017b4b  or      eax, 0FFFFFFFFh
0x180017b4e  lock xadd [rsi+8], eax
0x180017b53  cmp     eax, 1
0x180017b56  jz      loc_180017C2B
0x180017b5c  mov     rcx, [rbp+50h+var_40]
0x180017b60  test    rcx, rcx
0x180017b63  jz      short loc_180017B72
0x180017b65  mov     rax, [rcx]
0x180017b68  mov     rax, [rax+10h]
0x180017b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b71  nop
0x180017b72  test    r12, r12
0x180017b75  jz      short loc_180017B8A
0x180017b77  or      eax, 0FFFFFFFFh
0x180017b7a  lock xadd [r12+8], eax
0x180017b81  cmp     eax, 1
0x180017b84  jz      loc_180017C46
0x180017b8a  mov     rcx, [rbx+10h]
0x180017b8e  cmp     byte ptr [rcx+19h], 0
0x180017b92  jnz     short loc_180017BB8
0x180017b94  mov     rbx, rcx
0x180017b97  mov     rcx, [rcx]
0x180017b9a  cmp     byte ptr [rcx+19h], 0
0x180017b9e  jnz     loc_1800179B4
0x180017ba4  mov     rbx, rcx
0x180017ba7  mov     rax, [rcx]
0x180017baa  mov     rcx, rax
0x180017bad  cmp     byte ptr [rax+19h], 0
0x180017bb1  jz      short loc_180017BA4
0x180017bb3  jmp     loc_1800179B4
0x180017bb8  mov     rax, [rbx+8]
0x180017bbc  cmp     byte ptr [rax+19h], 0
0x180017bc0  jnz     short loc_180017BD1
0x180017bc2  cmp     rbx, [rax+10h]
0x180017bc6  jnz     short loc_180017BD1
0x180017bc8  mov     rbx, rax
0x180017bcb  mov     rax, [rax+8]
0x180017bcf  jmp     short loc_180017BBC
0x180017bd1  mov     rbx, rax
0x180017bd4  jmp     loc_1800179B4
0x180017bd9  mov     rsi, qword ptr [rsp+150h+var_120+8]
0x180017bde  mov     rdi, qword ptr [rsp+150h+var_120]
0x180017be3  jmp     loc_180017A3B
0x180017be8  mov     r13, [rsp+150h+lpCriticalSection]
0x180017bed  test    r13, r13
0x180017bf0  jz      short loc_180017BFC
0x180017bf2  mov     rcx, r13; lpCriticalSection
0x180017bf5  call    cs:__imp_LeaveCriticalSection
0x180017bfb  nop
0x180017bfc  mov     rcx, r15
0x180017bff  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180017c04  mov     rcx, [rbp+50h+var_38]
0x180017c08  xor     rcx, rsp; StackCookie
0x180017c0b  call    __security_check_cookie
0x180017c10  mov     rbx, [rsp+150h+arg_10]
0x180017c18  add     rsp, 120h
0x180017c1f  pop     r15
0x180017c21  pop     r14
0x180017c23  pop     r13
0x180017c25  pop     r12
0x180017c27  pop     rdi
0x180017c28  pop     rsi
0x180017c29  pop     rbp
0x180017c2a  retn
0x180017c2b  mov     rax, [rsi]
0x180017c2e  mov     rcx, rsi
0x180017c31  mov     rax, [rax]
0x180017c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c39  mov     rcx, rsi; this
0x180017c3c  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180017c41  jmp     loc_180017B5C
0x180017c46  mov     rax, [r12]
0x180017c4a  mov     rcx, r12
0x180017c4d  mov     rax, [rax]
0x180017c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c55  mov     rcx, r12; this
0x180017c58  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180017c5d  jmp     loc_180017B8A
0x180017c62  test    r14, r14
0x180017c65  jz      short loc_180017C70
0x180017c67  mov     rcx, r14; lpCriticalSection
0x180017c6a  call    cs:__imp_LeaveCriticalSection
0x180017c70  lock inc qword ptr [rdi+88h]
0x180017c78  mov     rcx, [rdi+80h]; pwk
0x180017c7f  call    cs:__imp_SubmitThreadpoolWork
0x180017c85  mov     r15, [rbp+50h+var_48]
0x180017c89  jmp     loc_180017AEC
0x180017c8e  lea     rdx, [rbp+50h+var_80]
0x180017c92  cmp     dword ptr [rdi], 1
0x180017c95  jnz     short loc_180017C9E
0x180017c97  call    ??$emplace_back@V?$function@$$A6AXXZ@std@@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::deque<std::function<void (void)>>::emplace_back<std::function<void (void)>>(std::function<void (void)> &&)
0x180017c9c  jmp     short loc_180017C62
0x180017c9e  add     rcx, 50h ; 'P'
0x180017ca2  call    ??$emplace_back@V?$function@$$A6AXXZ@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV?$function@$$A6AXXZ@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<std::function<void (void)>>(std::function<void (void)> &&)
0x180017ca7  jmp     short loc_180017C62
```
