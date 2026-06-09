# WcmCommon::ThreadPoolWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18002f6f0`
- end: `0x18002f90f`
- name: `?WorkCallback@ThreadPoolWorkQueue@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `543`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007c90`
- `0x180008710`
- `0x18000f094`
- `0x18001db50`
- `0x18002e4d8`
- `0x18002e510`
- `0x18002e534`
- `0x18002e554`
- `0x18002e668`
- `0x18002f1bc`
- `0x18002f6f0`
- `0x18002facc`
- `0x1800301a0`
- `0x1800301bc`
- `0x180030200`
- `0x180030244`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f725`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f725`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002f87c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002f87c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f873`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f873`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::WorkCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WORK Work)
{
  char *v4; // rbx
  _QWORD *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rdx
  HANDLE CurrentThread; // rax
  void **pExceptionObject; // [rsp+20h] [rbp-49h] BYREF
  __int128 v14; // [rsp+28h] [rbp-41h]
  char *v15; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v16[8]; // [rsp+40h] [rbp-29h] BYREF
  char v17; // [rsp+80h] [rbp+17h]

  v16[7] = 0;
  v17 = 0;
  v4 = Context + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 8));
  v15 = v4;
  if ( *(_DWORD *)Context != 1 )
  {
    if ( *((_QWORD *)Context + 33) )
    {
      v9 = std::deque<std::function<void (void)>>::front(Context + 232);
      if ( v17 == -1 )
      {
        if ( *(char *)(v9 + 64) != -1 )
        {
          if ( *(_BYTE *)(v9 + 64) )
          {
            std::_Construct_in_place<std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::integral_constant<unsigned __int64,1>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
              v16,
              v8,
              (_QWORD *)v9);
            v17 = 1;
            std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Reset<1>(v9);
          }
          else
          {
            std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(
              (__int64)v16,
              v9);
            std::function<long (void)>::~function<long (void)>(v9, v11);
            *(_BYTE *)(v9 + 64) = -1;
          }
        }
      }
      else
      {
        *(_QWORD *)&v14 = v9;
        v10 = *(char *)(v9 + 64) + 1LL;
        pExceptionObject = (void **)v16;
        *((_QWORD *)&v14 + 1) = v16;
        ____Visit_V_lambda_1___1_____RU___Tagged_AEAV__function___A6AXXZ_std___0A__std___1_2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__QEAAXAEAV34__Z_QEBA_A_PU___Tagged_AEAV__function___A6AXXZ_std___0A__4__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__4_____Variant_raw_visit1__00_std__SAX_K__QEAV_lambda_1___1_____RU___Tagged_AEAV__function___A6AXXZ_std___0A__std___2_2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1_QEAAXAEAV41__Z_QEBA_A_PU___Tagged_AEAV__function___A6AXXZ_std___0A__1__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1__Z(
          v10,
          &pExceptionObject,
          (_QWORD *)v9);
      }
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::pop_front(Context + 232);
      goto LABEL_15;
    }
    goto LABEL_7;
  }
  if ( !*((_QWORD *)Context + 28) )
  {
    if ( *((_QWORD *)Context + 23) )
    {
      v7 = std::deque<std::function<void (void)>>::front(Context + 152);
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(v16);
      v17 = -1;
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(
        (__int64)v16,
        v7);
      std::deque<std::function<void (void)>>::pop_front(Context + 152);
      goto LABEL_15;
    }
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
    goto LABEL_21;
  }
  v5 = (_QWORD *)std::deque<std::function<void (void)>>::front(Context + 192);
  std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(v16);
  v17 = -1;
  std::_Construct_in_place<std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::integral_constant<unsigned __int64,1>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
    v16,
    v6,
    v5);
  v17 = 1;
  std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::pop_front(Context + 192);
LABEL_15:
  CurrentThread = GetCurrentThread();
  _InterlockedExchange((volatile __int32 *)Context + 36, GetThreadId(CurrentThread));
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
  if ( v17 == 1 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v16[0] + 8LL))(v16[0]);
  }
  else
  {
    if ( v17 )
    {
      v14 = 0;
      pExceptionObject = &std::bad_variant_access::`vftable';
      throw (std::bad_variant_access *)&pExceptionObject;
    }
    std::_Func_class<void,>::operator()(v16);
  }
  _InterlockedDecrement64((volatile signed __int64 *)Context + 17);
  _InterlockedExchange((volatile __int32 *)Context + 36, 0);
LABEL_21:
  std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(v16);
}

```

## disassembly

```asm
0x18002f6f0  push    rbp
0x18002f6f2  push    rbx
0x18002f6f3  push    rsi
0x18002f6f4  push    rdi
0x18002f6f5  lea     rbp, [rsp-3Fh]
0x18002f6fa  sub     rsp, 0A8h
0x18002f701  mov     rax, cs:__security_cookie
0x18002f708  xor     rax, rsp
0x18002f70b  mov     [rbp+57h+var_30], rax
0x18002f70f  mov     rsi, rdx
0x18002f712  mov     [rbp+57h+var_48], 0
0x18002f71a  mov     [rbp+57h+var_40], 0
0x18002f71e  lea     rbx, [rdx+8]
0x18002f722  mov     rcx, rbx; lpCriticalSection
0x18002f725  call    cs:__imp_EnterCriticalSection
0x18002f72b  mov     [rbp+57h+var_88], rbx
0x18002f72f  cmp     dword ptr [rsi], 1
0x18002f732  jnz     loc_18002F7C0
0x18002f738  cmp     qword ptr [rsi+0E0h], 0
0x18002f740  jz      short loc_18002F77E
0x18002f742  lea     rdi, [rsi+0C0h]
0x18002f749  mov     rcx, rdi
0x18002f74c  call    ?front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@2@XZ; std::deque<std::function<void (void)>>::front(void)
0x18002f751  mov     rbx, rax
0x18002f754  lea     rcx, [rbp+57h+var_80]
0x18002f758  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x18002f75d  mov     [rbp+57h+var_40], 0FFh
0x18002f761  mov     r8, rbx
0x18002f764  lea     rcx, [rbp+57h+var_80]
0x18002f768  call    ??$_Construct_in_place@V?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@U?$integral_constant@_K$00@2@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@YAXAEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@0@$$QEAU?$integral_constant@_K$00@0@$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@0@@Z; std::_Construct_in_place<std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::integral_constant<unsigned __int64,1>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &,std::integral_constant<unsigned __int64,1> &&,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18002f76d  mov     [rbp+57h+var_40], 1
0x18002f771  mov     rcx, rdi
0x18002f774  call    ?pop_front@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAXXZ; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::pop_front(void)
0x18002f779  jmp     loc_18002F873
0x18002f77e  cmp     qword ptr [rsi+0B8h], 0
0x18002f786  jz      short loc_18002F7CA
0x18002f788  lea     rdi, [rsi+98h]
0x18002f78f  mov     rcx, rdi
0x18002f792  call    ?front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@2@XZ; std::deque<std::function<void (void)>>::front(void)
0x18002f797  mov     rbx, rax
0x18002f79a  lea     rcx, [rbp+57h+var_80]
0x18002f79e  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x18002f7a3  mov     [rbp+57h+var_40], 0FFh
0x18002f7a7  mov     rdx, rbx
0x18002f7aa  lea     rcx, [rbp+57h+var_80]
0x18002f7ae  call    ??$_Emplace_valueless@$0A@V?$function@$$A6AXXZ@std@@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@AEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(std::function<void (void)> &&)
0x18002f7b3  mov     rcx, rdi
0x18002f7b6  call    ?pop_front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAXXZ; std::deque<std::function<void (void)>>::pop_front(void)
0x18002f7bb  jmp     loc_18002F873
0x18002f7c0  cmp     qword ptr [rsi+108h], 0
0x18002f7c8  jnz     short loc_18002F7D8
0x18002f7ca  lea     rcx, [rbp+57h+var_88]
0x18002f7ce  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002f7d3  jmp     loc_18002F8ED
0x18002f7d8  lea     rdi, [rsi+0E8h]
0x18002f7df  mov     rcx, rdi
0x18002f7e2  call    ?front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@2@XZ; std::deque<std::function<void (void)>>::front(void)
0x18002f7e7  mov     rbx, rax
0x18002f7ea  movsx   rax, [rbp+57h+var_40]
0x18002f7ef  add     rax, 1
0x18002f7f3  jz      short loc_18002F82C
0x18002f7f5  mov     qword ptr [rbp+57h+var_98], rbx
0x18002f7f9  movsx   rcx, byte ptr [rbx+40h]
0x18002f7fe  mov     r8, rbx
0x18002f801  lea     rdx, [rbp+57h+pExceptionObject]
0x18002f805  inc     rcx
0x18002f808  cmp     rax, 1
0x18002f80c  lea     rax, [rbp+57h+var_80]
0x18002f810  mov     [rbp+57h+pExceptionObject], rax
0x18002f814  lea     rax, [rbp+57h+var_80]
0x18002f818  mov     qword ptr [rbp+57h+var_98+8], rax
0x18002f81c  jz      short loc_18002F825
0x18002f81e  call    ??$_Visit@V_lambda_1_@?1???$?RU?$_Tagged@AEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@$00@std@@@1?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV34@@Z@QEBA?A_PU?$_Tagged@AEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@$00@4@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@4@@?$_Variant_raw_visit1@$00@std@@SAX_K$$QEAV_lambda_1_@?1???$?RU?$_Tagged@AEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@$00@std@@@2?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@QEAAXAEAV41@@Z@QEBA?A_PU?$_Tagged@AEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@$00@1@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z
0x18002f823  jmp     short loc_18002F86B
0x18002f825  call    ??$_Visit@V_lambda_1_@?1???$?RU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@std@@@1?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV34@@Z@QEBA?A_PU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@4@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@4@@?$_Variant_raw_visit1@$00@std@@SAX_K$$QEAV_lambda_1_@?1???$?RU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@std@@@2?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@QEAAXAEAV41@@Z@QEBA?A_PU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@1@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z
0x18002f82a  jmp     short loc_18002F86B
0x18002f82c  movsx   rax, byte ptr [rbx+40h]
0x18002f831  add     rax, 1
0x18002f835  jz      short loc_18002F86B
0x18002f837  lea     rcx, [rbp+57h+var_80]
0x18002f83b  cmp     rax, 1
0x18002f83f  jz      short loc_18002F857
0x18002f841  mov     r8, rbx
0x18002f844  call    ??$_Construct_in_place@V?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@U?$integral_constant@_K$00@2@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@YAXAEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@0@$$QEAU?$integral_constant@_K$00@0@$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@0@@Z; std::_Construct_in_place<std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::integral_constant<unsigned __int64,1>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &,std::integral_constant<unsigned __int64,1> &&,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18002f849  mov     [rbp+57h+var_40], 1
0x18002f84d  mov     rcx, rbx
0x18002f850  call    ??$_Reset@$00@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Reset<1>(void)
0x18002f855  jmp     short loc_18002F86B
0x18002f857  mov     rdx, rbx
0x18002f85a  call    ??$_Emplace_valueless@$0A@V?$function@$$A6AXXZ@std@@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@AEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(std::function<void (void)> &&)
0x18002f85f  mov     rcx, rbx
0x18002f862  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18002f867  mov     byte ptr [rbx+40h], 0FFh
0x18002f86b  mov     rcx, rdi
0x18002f86e  call    ?pop_front@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAXXZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::pop_front(void)
0x18002f873  call    cs:__imp_GetCurrentThread
0x18002f879  mov     rcx, rax; Thread
0x18002f87c  call    cs:__imp_GetThreadId
0x18002f882  xchg    eax, [rsi+90h]
0x18002f888  lea     rcx, [rbp+57h+var_88]
0x18002f88c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002f891  mov     al, [rbp+57h+var_40]
0x18002f894  cmp     al, 1
0x18002f896  jnz     short loc_18002F8AD
0x18002f898  lea     rcx, [rbp+57h+var_80]
0x18002f89c  mov     rcx, [rcx]
0x18002f89f  mov     rax, [rcx]
0x18002f8a2  mov     rax, [rax+8]
0x18002f8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8ab  jmp     short loc_18002F8DD
0x18002f8ad  test    al, al
0x18002f8af  jz      short loc_18002F8D4
0x18002f8b1  xorps   xmm0, xmm0
0x18002f8b4  movups  [rbp+57h+var_98], xmm0
0x18002f8b8  lea     rax, ??_7bad_variant_access@std@@6B@; const std::bad_variant_access::`vftable'
0x18002f8bf  mov     [rbp+57h+pExceptionObject], rax
0x18002f8c3  lea     rdx, _TI2?AVbad_variant_access@std@@; pThrowInfo
0x18002f8ca  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f8ce  call    _CxxThrowException_0
0x18002f8d4  lea     rcx, [rbp+57h+var_80]
0x18002f8d8  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18002f8dd  lock dec qword ptr [rsi+88h]
0x18002f8e5  xor     eax, eax
0x18002f8e7  xchg    eax, [rsi+90h]
0x18002f8ed  lea     rcx, [rbp+57h+var_80]
0x18002f8f1  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x18002f8f6  nop
0x18002f8f7  mov     rcx, [rbp+57h+var_30]
0x18002f8fb  xor     rcx, rsp; StackCookie
0x18002f8fe  call    __security_check_cookie
0x18002f903  add     rsp, 0A8h
0x18002f90a  pop     rdi
0x18002f90b  pop     rsi
0x18002f90c  pop     rbx
0x18002f90d  pop     rbp
0x18002f90e  retn
```
