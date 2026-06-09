# MapsBackgroundTransferService_SetMapJobProperty(std::function<void (void)>,std::function<long (std::shared_ptr<MapsBackgroundTransferJob>)>)

- ea: `0x180005354`
- end: `0x18000558e`
- name: `?MapsBackgroundTransferService_SetMapJobProperty@@YAJV?$function@$$A6AXXZ@std@@V?$function@$$A6AJV?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@Z@2@@Z`
- size: `570`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800055a0`
- `0x180005600`
- `0x180005660`

## callees

- `0x180003b44`
- `0x180004094`
- `0x180004134`
- `0x180004168`
- `0x180004408`
- `0x180004454`
- `0x180004730`
- `0x180005354`
- `0x180005b9c`
- `0x180005bf0`
- `0x180005e8c`
- `0x18000cf70`
- `0x180015010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800054e3`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800054e3`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800053a2`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180005587`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800053a2`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180005587`

## string_xrefs

- `0x1800054d9`: `MapsBackgroundTransferService_SetMapJobProperty`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferService_SetMapJobProperty(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned int v5; // r13d
  unsigned __int64 v6; // rax
  _QWORD *v7; // rdi
  _QWORD *i; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  __int64 v11; // rcx
  int v12; // r12d
  volatile signed __int32 *v13; // rsi
  std::_Ref_count_base *v14; // rsi
  std::_Ref_count_base *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v20; // [rsp+20h] [rbp-60h] BYREF
  std::_Ref_count_base *v21; // [rsp+28h] [rbp-58h]
  __int64 v22; // [rsp+30h] [rbp-50h] BYREF
  __int64 v23; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v24[7]; // [rsp+48h] [rbp-38h] BYREF
  __int64 *v25; // [rsp+D0h] [rbp+50h] BYREF

  std::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>((__int64)&v23);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)&v20,
    (struct _RTL_CRITICAL_SECTION *)qword_18001D860);
  v4 = *(_QWORD *)(a1 + 56);
  if ( !v4 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v5 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v25 = &v23;
  LODWORD(v23) = dword_18001D820;
  std::list<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>::_Assign_cast<std::pair<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>>(
    (__int64)v24,
    *(_QWORD **)qword_18001D828,
    (_QWORD *)qword_18001D828);
  v6 = std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Desired_grow_bucket_count(
         (__int64)&v23,
         v24[1]);
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(
    &v23,
    v6);
  v25 = 0;
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(&v25);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>((__int64)&v20);
  v7 = (_QWORD *)v24[0];
  for ( i = *(_QWORD **)v24[0]; i != v7; i = (_QWORD *)*i )
  {
    std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(&v20, i + 3);
    if ( (unsigned int)MapsBackgroundTransferJob::GetJobState(v20) != 4 )
    {
      v9 = std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(&v22, &v20);
      v10 = v9;
      v25 = v9;
      v11 = *(_QWORD *)(a2 + 56);
      if ( !v11 )
      {
        std::_Xbad_function_call();
        JUMPOUT(0x18000558ELL);
      }
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v11 + 16LL))(v11, v9);
      v13 = (volatile signed __int32 *)v10[1];
      if ( v13 && _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v13);
      }
      if ( v12 < 0 )
      {
        v5 = ZTraceReportOriginationNoThis(v12, "MapsBackgroundTransferService_SetMapJobProperty", 363);
        v15 = v21;
        if ( v21 && _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(std::_Ref_count_base *))v15)(v15);
          std::_Ref_count_base::_Decwref(v15);
        }
        break;
      }
    }
    v14 = v21;
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(std::_Ref_count_base *))v14)(v14);
        std::_Ref_count_base::_Decwref(v14);
      }
    }
  }
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::~_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>((__int64)&v23);
  v17 = *(_QWORD *)(a1 + 56);
  if ( v17 )
  {
    LOBYTE(v16) = v17 != a1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 32LL))(v17, v16);
    *(_QWORD *)(a1 + 56) = 0;
  }
  v18 = *(_QWORD *)(a2 + 56);
  if ( v18 )
  {
    LOBYTE(v16) = v18 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 32LL))(v18, v16);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180005354  mov     [rsp-38h+arg_18], rbx
0x180005359  mov     [rsp-38h+arg_8], rdx
0x18000535e  mov     [rsp-38h+arg_0], rcx
0x180005363  push    rbp
0x180005364  push    rsi
0x180005365  push    rdi
0x180005366  push    r12
0x180005368  push    r13
0x18000536a  push    r14
0x18000536c  push    r15
0x18000536e  mov     rbp, rsp
0x180005371  sub     rsp, 80h
0x180005378  mov     r14, rdx
0x18000537b  mov     r15, rcx
0x18000537e  lea     rcx, [rbp+var_40]
0x180005382  call    ??0?$unordered_map@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@U?$hash@PEAVMapsBackgroundTransferJob@@@3@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@@std@@QEAA@XZ; std::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>(void)
0x180005387  nop
0x180005388  lea     rdx, qword_18001D860
0x18000538f  lea     rcx, [rbp+var_60]
0x180005393  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x180005398  nop
0x180005399  mov     rcx, [r15+38h]
0x18000539d  test    rcx, rcx
0x1800053a0  jnz     short loc_1800053A9
0x1800053a2  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800053a8  int     3; Trap to Debugger
0x1800053a9  xor     r13d, r13d
0x1800053ac  mov     rax, [rcx]
0x1800053af  mov     rax, [rax+10h]
0x1800053b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b8  lea     rax, [rbp+var_40]
0x1800053bc  mov     [rbp+arg_10], rax
0x1800053c0  mov     eax, cs:dword_18001D820
0x1800053c6  mov     dword ptr [rbp+var_40], eax
0x1800053c9  mov     rdx, cs:qword_18001D828
0x1800053d0  mov     r8, rdx
0x1800053d3  mov     rdx, [rdx]
0x1800053d6  lea     rcx, [rbp+var_38]
0x1800053da  call    ??$_Assign_cast@AEAU?$pair@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$list@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@2@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>::_Assign_cast<std::pair<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>)
0x1800053df  mov     rdx, [rbp+var_30]
0x1800053e3  lea     rcx, [rbp+var_40]
0x1800053e7  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x1800053ec  mov     rdx, rax
0x1800053ef  lea     rcx, [rbp+var_40]
0x1800053f3  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(unsigned __int64)
0x1800053f8  mov     [rbp+arg_10], r13
0x1800053fc  lea     rcx, [rbp+arg_10]
0x180005400  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180005405  nop
0x180005406  lea     rcx, [rbp+var_60]
0x18000540a  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000540f  mov     rdi, [rbp+var_38]
0x180005413  mov     rbx, [rdi]
0x180005416  cmp     rbx, rdi
0x180005419  jz      loc_180005519
0x18000541f  lea     rdx, [rbx+18h]
0x180005423  lea     rcx, [rbp+var_60]
0x180005427  call    ??0?$shared_ptr@VMapsBackgroundTransferJob@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(std::shared_ptr<MapsBackgroundTransferJob> const &)
0x18000542c  nop
0x18000542d  mov     rcx, [rbp+var_60]
0x180005431  call    ?GetJobState@MapsBackgroundTransferJob@@UEAA?AW4MAPSBTSVC_JOB_STATE@@XZ; MapsBackgroundTransferJob::GetJobState(void)
0x180005436  cmp     eax, 4
0x180005439  jz      short loc_18000549F
0x18000543b  lea     rdx, [rbp+var_60]
0x18000543f  lea     rcx, [rbp+var_50]
0x180005443  call    ??0?$shared_ptr@VMapsBackgroundTransferJob@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(std::shared_ptr<MapsBackgroundTransferJob> const &)
0x180005448  mov     rsi, rax
0x18000544b  mov     [rbp+arg_10], rax
0x18000544f  mov     rcx, [r14+38h]
0x180005453  test    rcx, rcx
0x180005456  jz      loc_180005587
0x18000545c  mov     rax, [rcx]
0x18000545f  mov     rdx, rsi
0x180005462  mov     rax, [rax+10h]
0x180005466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000546b  mov     r12d, eax
0x18000546e  mov     rsi, [rsi+8]
0x180005472  test    rsi, rsi
0x180005475  jz      short loc_18000549A
0x180005477  or      eax, 0FFFFFFFFh
0x18000547a  lock xadd [rsi+8], eax
0x18000547f  cmp     eax, 1
0x180005482  jnz     short loc_18000549A
0x180005484  mov     rax, [rsi]
0x180005487  mov     rcx, rsi
0x18000548a  mov     rax, [rax]
0x18000548d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005492  mov     rcx, rsi; this
0x180005495  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000549a  test    r12d, r12d
0x18000549d  js      short loc_1800054D3
0x18000549f  mov     rsi, [rbp+var_58]
0x1800054a3  test    rsi, rsi
0x1800054a6  jz      short loc_1800054CB
0x1800054a8  or      eax, 0FFFFFFFFh
0x1800054ab  lock xadd [rsi+8], eax
0x1800054b0  cmp     eax, 1
0x1800054b3  jnz     short loc_1800054CB
0x1800054b5  mov     rax, [rsi]
0x1800054b8  mov     rcx, rsi
0x1800054bb  mov     rax, [rax]
0x1800054be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054c3  mov     rcx, rsi; this
0x1800054c6  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800054cb  mov     rbx, [rbx]
0x1800054ce  jmp     loc_180005416
0x1800054d3  mov     r8d, 16Bh
0x1800054d9  lea     rdx, aMapsbackground_12; "MapsBackgroundTransferService_SetMapJob"...
0x1800054e0  mov     ecx, r12d
0x1800054e3  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800054e9  mov     r13d, eax
0x1800054ec  mov     rbx, [rbp+var_58]
0x1800054f0  test    rbx, rbx
0x1800054f3  jz      short loc_180005519
0x1800054f5  or      edx, 0FFFFFFFFh
0x1800054f8  lock xadd [rbx+8], edx
0x1800054fd  cmp     edx, 1
0x180005500  jnz     short loc_180005519
0x180005502  mov     rdx, [rbx]
0x180005505  mov     rcx, rbx
0x180005508  mov     rax, [rdx]
0x18000550b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005510  mov     rcx, rbx; this
0x180005513  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180005518  nop
0x180005519  lea     rcx, [rbp+var_40]
0x18000551d  call    ??1?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::~_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>(void)
0x180005522  nop
0x180005523  mov     rcx, [r15+38h]
0x180005527  test    rcx, rcx
0x18000552a  jz      short loc_180005546
0x18000552c  mov     rax, [rcx]
0x18000552f  cmp     rcx, r15
0x180005532  setnz   dl
0x180005535  mov     rax, [rax+20h]
0x180005539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000553e  mov     qword ptr [r15+38h], 0
0x180005546  mov     rcx, [r14+38h]
0x18000554a  test    rcx, rcx
0x18000554d  jz      short loc_180005569
0x18000554f  mov     rax, [rcx]
0x180005552  cmp     rcx, r14
0x180005555  setnz   dl
0x180005558  mov     rax, [rax+20h]
0x18000555c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005561  mov     qword ptr [r14+38h], 0
0x180005569  mov     eax, r13d
0x18000556c  mov     rbx, [rsp+80h+arg_18]
0x180005574  add     rsp, 80h
0x18000557b  pop     r15
0x18000557d  pop     r14
0x18000557f  pop     r13
0x180005581  pop     r12
0x180005583  pop     rdi
0x180005584  pop     rsi
0x180005585  pop     rbp
0x180005586  retn
0x180005587  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18000558d  nop
```
