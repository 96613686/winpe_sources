# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__NlmDomain::ResolveDnsSuffixes_::_11_::_lambda_1___

- ea: `0x180088218`
- end: `0x180088342`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__NlmDomain::ResolveDnsSuffixes_::_11_::_lambda_1___`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006c584`

## callees

- `0x18000e190`
- `0x180032c90`
- `0x18004c958`
- `0x18006d154`
- `0x180088218`
- `0x180088348`
- `0x1800883cc`
- `0x1800ffce8`
- `0x1801089d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180088247`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180088247`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088275`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088307`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088275`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088307`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008831c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008831c`

## pseudocode

```c
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__NlmDomain::ResolveDnsSuffixes_::_11_::_lambda_1___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int64 v7; // rax
  __int128 v9; // [rsp+20h] [rbp-49h] BYREF
  __int64 v10; // [rsp+30h] [rbp-39h] BYREF
  std::_Ref_count_base *v11; // [rsp+38h] [rbp-31h]
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+48h] [rbp-21h]
  _BYTE v13[112]; // [rsp+50h] [rbp-19h] BYREF

  v9 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v12 = v6;
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( v6 )
      LeaveCriticalSection(v6);
  }
  else
  {
    v7 = std::make_shared_WcmCommon::ThreadPoolWaitableResult_long___NlmDomain::ResolveDnsSuffixes_::_11_::_lambda_1___(
           &v10,
           a3);
    std::shared_ptr<KryptonManagement::Container>::operator=(&v9, v7);
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
    if ( *(_DWORD *)a1 == 1 )
    {
      std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(
        &v10,
        &v9);
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(a1 + 192, &v10);
      if ( v11 )
        std::_Ref_count_base::_Decref(v11);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
        (__int64)v13,
        (__int64)&v9);
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::push_back(
        a1 + 232,
        v13);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v13);
    }
    if ( v6 )
      LeaveCriticalSection(v6);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *(_OWORD *)a2 = v9;
  }
  return a2;
}

```

## disassembly

```asm
0x180088218  push    rbp
0x18008821a  push    rbx
0x18008821b  push    rsi
0x18008821c  push    rdi
0x18008821d  push    r14
0x18008821f  lea     rbp, [rsp-37h]
0x180088224  sub     rsp, 0A0h
0x18008822b  mov     r14, r8
0x18008822e  mov     rbx, rdx
0x180088231  mov     rdi, rcx
0x180088234  mov     [rbp+57h+var_78], rdx
0x180088238  xorps   xmm1, xmm1
0x18008823b  movdqu  [rbp+57h+var_A0], xmm1
0x180088240  lea     rsi, [rcx+8]
0x180088244  mov     rcx, rsi; lpCriticalSection
0x180088247  call    cs:__imp_EnterCriticalSection
0x18008824d  mov     [rbp+57h+var_78], rsi
0x180088251  cmp     byte ptr [rdi+110h], 0
0x180088258  jz      short loc_180088280
0x18008825a  mov     qword ptr [rbx], 0
0x180088261  mov     qword ptr [rbx+8], 0
0x180088269  test    rsi, rsi
0x18008826c  jz      loc_180088331
0x180088272  mov     rcx, rsi; lpCriticalSection
0x180088275  call    cs:__imp_LeaveCriticalSection
0x18008827b  jmp     loc_180088331
0x180088280  mov     rdx, r14
0x180088283  lea     rcx, [rbp+57h+var_90]
0x180088287  call    std__make_shared_WcmCommon__ThreadPoolWaitableResult_long___NlmDomain__ResolveDnsSuffixes____11____lambda_1___
0x18008828c  mov     rdx, rax
0x18008828f  lea     rcx, [rbp+57h+var_A0]
0x180088293  call    ??4?$shared_ptr@VContainer@KryptonManagement@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<KryptonManagement::Container>::operator=(std::shared_ptr<KryptonManagement::Container> &&)
0x180088298  mov     rcx, [rbp+57h+var_88]; this
0x18008829c  test    rcx, rcx
0x18008829f  jz      short loc_1800882A6
0x1800882a1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800882a6  lea     rdx, [rbp+57h+var_A0]
0x1800882aa  cmp     dword ptr [rdi], 1
0x1800882ad  jnz     short loc_1800882DA
0x1800882af  lea     rcx, [rbp+57h+var_90]
0x1800882b3  call    ??$?0V?$ThreadPoolWaitableResult@V?$vector@UWlanInterfaceInfo@Wlan@KryptonSchema@@V?$allocator@UWlanInterfaceInfo@Wlan@KryptonSchema@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$vector@UWlanInterfaceInfo@Wlan@KryptonSchema@@V?$allocator@UWlanInterfaceInfo@Wlan@KryptonSchema@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::vector<KryptonSchema::Wlan::WlanInterfaceInfo>>> const &)
0x1800882b8  nop
0x1800882b9  lea     rdx, [rbp+57h+var_90]
0x1800882bd  lea     rcx, [rdi+0C0h]
0x1800882c4  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x1800882c9  nop
0x1800882ca  mov     rcx, [rbp+57h+var_88]; this
0x1800882ce  test    rcx, rcx
0x1800882d1  jz      short loc_1800882FF
0x1800882d3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800882d8  jmp     short loc_1800882FF
0x1800882da  lea     rcx, [rbp+57h+var_70]
0x1800882de  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<long>> &)
0x1800882e3  nop
0x1800882e4  lea     rdx, [rbp+57h+var_70]
0x1800882e8  lea     rcx, [rdi+0E8h]
0x1800882ef  call    ?push_back@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@2@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::push_back(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x1800882f4  nop
0x1800882f5  lea     rcx, [rbp+57h+var_70]
0x1800882f9  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x1800882fe  nop
0x1800882ff  test    rsi, rsi
0x180088302  jz      short loc_18008830D
0x180088304  mov     rcx, rsi; lpCriticalSection
0x180088307  call    cs:__imp_LeaveCriticalSection
0x18008830d  lock inc qword ptr [rdi+88h]
0x180088315  mov     rcx, [rdi+80h]; pwk
0x18008831c  call    cs:__imp_SubmitThreadpoolWork
0x180088322  mov     rax, qword ptr [rbp+57h+var_A0]
0x180088326  mov     [rbx], rax
0x180088329  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x18008832d  mov     [rbx+8], rax
0x180088331  mov     rax, rbx
0x180088334  add     rsp, 0A0h
0x18008833b  pop     r14
0x18008833d  pop     rdi
0x18008833e  pop     rsi
0x18008833f  pop     rbx
0x180088340  pop     rbp
0x180088341  retn
```
