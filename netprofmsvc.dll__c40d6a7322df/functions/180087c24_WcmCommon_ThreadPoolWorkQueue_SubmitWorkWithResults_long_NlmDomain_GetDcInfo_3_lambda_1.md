# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__NlmDomain::GetDcInfo_::_3_::_lambda_1___

- ea: `0x180087c24`
- end: `0x180087d4e`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__NlmDomain::GetDcInfo_::_3_::_lambda_1___`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006ada0`

## callees

- `0x18000e190`
- `0x180032c90`
- `0x18004c958`
- `0x18006d154`
- `0x180087c24`
- `0x180087d54`
- `0x180088348`
- `0x1800ffce8`
- `0x1801089d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087c53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087c53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087c81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087d13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087c81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087d13`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180087d28`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180087d28`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__NlmDomain::GetDcInfo_::_3_::_lambda_1___(
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
    v7 = std::make_shared_WcmCommon::ThreadPoolWaitableResult_long___NlmDomain::GetDcInfo_::_3_::_lambda_1___(&v10, a3);
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
0x180087c24  push    rbp
0x180087c26  push    rbx
0x180087c27  push    rsi
0x180087c28  push    rdi
0x180087c29  push    r14
0x180087c2b  lea     rbp, [rsp-37h]
0x180087c30  sub     rsp, 0A0h
0x180087c37  mov     r14, r8
0x180087c3a  mov     rbx, rdx
0x180087c3d  mov     rdi, rcx
0x180087c40  mov     [rbp+57h+var_78], rdx
0x180087c44  xorps   xmm1, xmm1
0x180087c47  movdqu  [rbp+57h+var_A0], xmm1
0x180087c4c  lea     rsi, [rcx+8]
0x180087c50  mov     rcx, rsi; lpCriticalSection
0x180087c53  call    cs:__imp_EnterCriticalSection
0x180087c59  mov     [rbp+57h+var_78], rsi
0x180087c5d  cmp     byte ptr [rdi+110h], 0
0x180087c64  jz      short loc_180087C8C
0x180087c66  mov     qword ptr [rbx], 0
0x180087c6d  mov     qword ptr [rbx+8], 0
0x180087c75  test    rsi, rsi
0x180087c78  jz      loc_180087D3D
0x180087c7e  mov     rcx, rsi; lpCriticalSection
0x180087c81  call    cs:__imp_LeaveCriticalSection
0x180087c87  jmp     loc_180087D3D
0x180087c8c  mov     rdx, r14
0x180087c8f  lea     rcx, [rbp+57h+var_90]
0x180087c93  call    std__make_shared_WcmCommon__ThreadPoolWaitableResult_long___NlmDomain__GetDcInfo____3____lambda_1___
0x180087c98  mov     rdx, rax
0x180087c9b  lea     rcx, [rbp+57h+var_A0]
0x180087c9f  call    ??4?$shared_ptr@VContainer@KryptonManagement@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<KryptonManagement::Container>::operator=(std::shared_ptr<KryptonManagement::Container> &&)
0x180087ca4  mov     rcx, [rbp+57h+var_88]; this
0x180087ca8  test    rcx, rcx
0x180087cab  jz      short loc_180087CB2
0x180087cad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180087cb2  lea     rdx, [rbp+57h+var_A0]
0x180087cb6  cmp     dword ptr [rdi], 1
0x180087cb9  jnz     short loc_180087CE6
0x180087cbb  lea     rcx, [rbp+57h+var_90]
0x180087cbf  call    ??$?0V?$ThreadPoolWaitableResult@V?$vector@UWlanInterfaceInfo@Wlan@KryptonSchema@@V?$allocator@UWlanInterfaceInfo@Wlan@KryptonSchema@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$vector@UWlanInterfaceInfo@Wlan@KryptonSchema@@V?$allocator@UWlanInterfaceInfo@Wlan@KryptonSchema@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::vector<KryptonSchema::Wlan::WlanInterfaceInfo>>> const &)
0x180087cc4  nop
0x180087cc5  lea     rdx, [rbp+57h+var_90]
0x180087cc9  lea     rcx, [rdi+0C0h]
0x180087cd0  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x180087cd5  nop
0x180087cd6  mov     rcx, [rbp+57h+var_88]; this
0x180087cda  test    rcx, rcx
0x180087cdd  jz      short loc_180087D0B
0x180087cdf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180087ce4  jmp     short loc_180087D0B
0x180087ce6  lea     rcx, [rbp+57h+var_70]
0x180087cea  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<long>> &)
0x180087cef  nop
0x180087cf0  lea     rdx, [rbp+57h+var_70]
0x180087cf4  lea     rcx, [rdi+0E8h]
0x180087cfb  call    ?push_back@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@2@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::push_back(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x180087d00  nop
0x180087d01  lea     rcx, [rbp+57h+var_70]
0x180087d05  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x180087d0a  nop
0x180087d0b  test    rsi, rsi
0x180087d0e  jz      short loc_180087D19
0x180087d10  mov     rcx, rsi; lpCriticalSection
0x180087d13  call    cs:__imp_LeaveCriticalSection
0x180087d19  lock inc qword ptr [rdi+88h]
0x180087d21  mov     rcx, [rdi+80h]; pwk
0x180087d28  call    cs:__imp_SubmitThreadpoolWork
0x180087d2e  mov     rax, qword ptr [rbp+57h+var_A0]
0x180087d32  mov     [rbx], rax
0x180087d35  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x180087d39  mov     [rbx+8], rax
0x180087d3d  mov     rax, rbx
0x180087d40  add     rsp, 0A0h
0x180087d47  pop     r14
0x180087d49  pop     rdi
0x180087d4a  pop     rsi
0x180087d4b  pop     rbx
0x180087d4c  pop     rbp
0x180087d4d  retn
```
