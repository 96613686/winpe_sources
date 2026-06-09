# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_std::vector_KryptonSchema::Wlan::WlanInterfaceInfo_std::allocator_KryptonSchema::Wlan::WlanInterfaceInfo_____HostStateWlan::GetData_::_3_::_lambda_1___

- ea: `0x180087f4c`
- end: `0x18008808e`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_std::vector_KryptonSchema::Wlan::WlanInterfaceInfo_std::allocator_KryptonSchema::Wlan::WlanInterfaceInfo_____HostStateWlan::GetData_::_3_::_lambda_1___`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006ccc8`

## callees

- `0x18000e190`
- `0x180032c90`
- `0x18004c958`
- `0x180087f4c`
- `0x180088348`
- `0x1800884b4`
- `0x1800ffce8`
- `0x1801089d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087f80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087f80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087fae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088052`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087fae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088052`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180088067`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180088067`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_std::vector_KryptonSchema::Wlan::WlanInterfaceInfo_std::allocator_KryptonSchema::Wlan::WlanInterfaceInfo_____HostStateWlan::GetData_::_3_::_lambda_1___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int64 *v7; // rax
  __int64 v8; // r14
  __int64 v9; // r15
  __int128 v11; // [rsp+20h] [rbp-49h] BYREF
  __int64 v12; // [rsp+30h] [rbp-39h] BYREF
  std::_Ref_count_base *v13; // [rsp+38h] [rbp-31h]
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+48h] [rbp-21h]
  _BYTE v15[112]; // [rsp+50h] [rbp-19h] BYREF

  v11 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v14 = v6;
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( v6 )
      LeaveCriticalSection(v6);
  }
  else
  {
    v7 = (__int64 *)std::make_shared_WcmCommon::ThreadPoolWaitableResult_std::vector_KryptonSchema::Wlan::WlanInterfaceInfo_std::allocator_KryptonSchema::Wlan::WlanInterfaceInfo_______HostStateWlan::GetData_::_3_::_lambda_1___(
                      &v12,
                      a3);
    v8 = *v7;
    v9 = v7[1];
    *v7 = 0;
    v7[1] = 0;
    *(_QWORD *)&v11 = v8;
    *((_QWORD *)&v11 + 1) = v9;
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( *(_DWORD *)a1 == 1 )
    {
      std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(
        &v12,
        &v11);
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(a1 + 192, &v12);
      if ( v13 )
        std::_Ref_count_base::_Decref(v13);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
        (__int64)v15,
        (__int64)&v11);
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::push_back(
        a1 + 232,
        v15);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v15);
    }
    if ( v6 )
      LeaveCriticalSection(v6);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *a2 = v8;
    a2[1] = v9;
  }
  return a2;
}

```

## disassembly

```asm
0x180087f4c  mov     [rsp-8+arg_18], rbx
0x180087f51  push    rbp
0x180087f52  push    rsi
0x180087f53  push    rdi
0x180087f54  push    r14
0x180087f56  push    r15
0x180087f58  lea     rbp, [rsp-37h]
0x180087f5d  sub     rsp, 0A0h
0x180087f64  mov     r14, r8
0x180087f67  mov     rbx, rdx
0x180087f6a  mov     rdi, rcx
0x180087f6d  mov     [rbp+57h+var_78], rdx
0x180087f71  xorps   xmm1, xmm1
0x180087f74  movdqu  [rbp+57h+var_A0], xmm1
0x180087f79  lea     rsi, [rcx+8]
0x180087f7d  mov     rcx, rsi; lpCriticalSection
0x180087f80  call    cs:__imp_EnterCriticalSection
0x180087f86  mov     [rbp+57h+var_78], rsi
0x180087f8a  cmp     byte ptr [rdi+110h], 0
0x180087f91  jz      short loc_180087FB9
0x180087f93  mov     qword ptr [rbx], 0
0x180087f9a  mov     qword ptr [rbx+8], 0
0x180087fa2  test    rsi, rsi
0x180087fa5  jz      loc_180088074
0x180087fab  mov     rcx, rsi; lpCriticalSection
0x180087fae  call    cs:__imp_LeaveCriticalSection
0x180087fb4  jmp     loc_180088074
0x180087fb9  mov     rdx, r14
0x180087fbc  lea     rcx, [rbp+57h+var_90]
0x180087fc0  call    std__make_shared_WcmCommon__ThreadPoolWaitableResult_std__vector_KryptonSchema__Wlan__WlanInterfaceInfo_std__allocator_KryptonSchema__Wlan__WlanInterfaceInfo_______HostStateWlan__GetData____3____lambda_1___
0x180087fc5  mov     r14, [rax]
0x180087fc8  mov     r15, [rax+8]
0x180087fcc  mov     qword ptr [rax], 0
0x180087fd3  mov     qword ptr [rax+8], 0
0x180087fdb  mov     qword ptr [rbp+57h+var_A0], r14
0x180087fdf  mov     qword ptr [rbp+57h+var_A0+8], r15
0x180087fe3  mov     rcx, [rbp+57h+var_88]; this
0x180087fe7  test    rcx, rcx
0x180087fea  jz      short loc_180087FF1
0x180087fec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180087ff1  lea     rdx, [rbp+57h+var_A0]
0x180087ff5  cmp     dword ptr [rdi], 1
0x180087ff8  jnz     short loc_180088025
0x180087ffa  lea     rcx, [rbp+57h+var_90]
0x180087ffe  call    ??$?0V?$ThreadPoolWaitableResult@V?$vector@UWlanInterfaceInfo@Wlan@KryptonSchema@@V?$allocator@UWlanInterfaceInfo@Wlan@KryptonSchema@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$vector@UWlanInterfaceInfo@Wlan@KryptonSchema@@V?$allocator@UWlanInterfaceInfo@Wlan@KryptonSchema@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::vector<KryptonSchema::Wlan::WlanInterfaceInfo>>> const &)
0x180088003  nop
0x180088004  lea     rdx, [rbp+57h+var_90]
0x180088008  lea     rcx, [rdi+0C0h]
0x18008800f  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x180088014  nop
0x180088015  mov     rcx, [rbp+57h+var_88]; this
0x180088019  test    rcx, rcx
0x18008801c  jz      short loc_18008804A
0x18008801e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180088023  jmp     short loc_18008804A
0x180088025  lea     rcx, [rbp+57h+var_70]
0x180088029  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<long>> &)
0x18008802e  nop
0x18008802f  lea     rdx, [rbp+57h+var_70]
0x180088033  lea     rcx, [rdi+0E8h]
0x18008803a  call    ?push_back@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@2@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::push_back(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18008803f  nop
0x180088040  lea     rcx, [rbp+57h+var_70]
0x180088044  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x180088049  nop
0x18008804a  test    rsi, rsi
0x18008804d  jz      short loc_180088058
0x18008804f  mov     rcx, rsi; lpCriticalSection
0x180088052  call    cs:__imp_LeaveCriticalSection
0x180088058  lock inc qword ptr [rdi+88h]
0x180088060  mov     rcx, [rdi+80h]; pwk
0x180088067  call    cs:__imp_SubmitThreadpoolWork
0x18008806d  mov     [rbx], r14
0x180088070  mov     [rbx+8], r15
0x180088074  mov     rax, rbx
0x180088077  mov     rbx, [rsp+0C0h+arg_18]
0x18008807f  add     rsp, 0A0h
0x180088086  pop     r15
0x180088088  pop     r14
0x18008808a  pop     rdi
0x18008808b  pop     rsi
0x18008808c  pop     rbp
0x18008808d  retn
```
