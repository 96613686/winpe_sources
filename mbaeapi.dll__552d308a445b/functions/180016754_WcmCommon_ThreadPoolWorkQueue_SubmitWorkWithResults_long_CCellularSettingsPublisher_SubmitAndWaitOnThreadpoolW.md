# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1___

- ea: `0x180016754`
- end: `0x180016909`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1___`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d3a4`

## callees

- `0x1800028ec`
- `0x18001336c`
- `0x1800164f0`
- `0x180016754`
- `0x18001cdcc`
- `0x18001dbf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800168c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800168c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001678a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001678a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800168de`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800168de`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  char *v7; // rbx
  char *v8; // r12
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _OWORD v13[4]; // [rsp+48h] [rbp-21h] BYREF
  char v14; // [rsp+88h] [rbp+1Fh]
  __int64 v15; // [rsp+D0h] [rbp+67h]

  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( v6 )
      LeaveCriticalSection(v6);
  }
  else
  {
    v7 = (char *)operator new(0x78u);
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<long>>::`vftable';
    v8 = v7 + 16;
    WcmCommon::ThreadPoolWaitableResult_long_::ThreadPoolWaitableResult_long___CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1___(
      v7 + 16,
      a3);
    if ( *(_DWORD *)a1 == 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
      if ( *(_QWORD *)(a1 + 208) <= (unsigned __int64)(*(_QWORD *)(a1 + 224) + 1LL) )
        std::deque<std::shared_ptr<WaitableOperation>>::_Growmap(a1 + 192);
      v9 = *(_QWORD *)(a1 + 208) - 1LL;
      *(_QWORD *)(a1 + 216) &= v9;
      v15 = *(_QWORD *)(a1 + 216) + *(_QWORD *)(a1 + 224);
      if ( !*(_QWORD *)(*(_QWORD *)(a1 + 200) + 8 * (v9 & v15)) )
        *(_QWORD *)(*(_QWORD *)(a1 + 200) + 8 * (v9 & v15)) = operator new(0x10u);
      v10 = *(_QWORD **)(*(_QWORD *)(a1 + 200) + 8 * (v15 & (*(_QWORD *)(a1 + 208) - 1LL)));
      *v10 = v8;
      v10[1] = v7;
      ++*(_QWORD *)(a1 + 224);
    }
    else
    {
      v13[0] = 0;
      _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
      *(_QWORD *)&v13[0] = v7 + 16;
      *((_QWORD *)&v13[0] + 1) = v7;
      v14 = 1;
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::push_back(
        a1 + 232,
        v13);
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(
        (__int64)v13,
        v11);
    }
    if ( v6 )
      LeaveCriticalSection(v6);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *a2 = v8;
    a2[1] = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x180016754  mov     [rsp-8+arg_8], rbx
0x180016759  push    rbp
0x18001675a  push    rsi
0x18001675b  push    rdi
0x18001675c  push    r12
0x18001675e  push    r13
0x180016760  push    r14
0x180016762  push    r15
0x180016764  lea     rbp, [rsp-27h]
0x180016769  sub     rsp, 90h
0x180016770  mov     rsi, r8
0x180016773  mov     rdi, rdx
0x180016776  mov     r14, rcx
0x180016779  xor     ebx, ebx
0x18001677b  xorps   xmm0, xmm0
0x18001677e  movdqu  [rbp+57h+var_98], xmm0
0x180016783  lea     r15, [rcx+8]
0x180016787  mov     rcx, r15; lpCriticalSection
0x18001678a  call    cs:__imp_EnterCriticalSection
0x180016790  mov     [rbp+57h+arg_18], r15
0x180016794  cmp     [r14+110h], bl
0x18001679b  jz      short loc_1800167BB
0x18001679d  mov     [rdi], rbx
0x1800167a0  mov     [rdi+8], rbx
0x1800167a4  test    r15, r15
0x1800167a7  jz      loc_1800168EB
0x1800167ad  mov     rcx, r15; lpCriticalSection
0x1800167b0  call    cs:__imp_LeaveCriticalSection
0x1800167b6  jmp     loc_1800168EB
0x1800167bb  mov     ecx, 78h ; 'x'; Size
0x1800167c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800167c5  mov     rbx, rax
0x1800167c8  mov     [rbp+57h+arg_0], rax
0x1800167cc  xorps   xmm0, xmm0
0x1800167cf  movups  xmmword ptr [rax], xmm0
0x1800167d2  mov     dword ptr [rax+8], 1
0x1800167d9  mov     dword ptr [rax+0Ch], 1
0x1800167e0  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@J@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<long>>::`vftable'
0x1800167e7  mov     [rbx], rax
0x1800167ea  lea     r12, [rbx+10h]
0x1800167ee  mov     rdx, rsi
0x1800167f1  mov     rcx, r12
0x1800167f4  call    WcmCommon__ThreadPoolWaitableResult_long___ThreadPoolWaitableResult_long___CCellularSettingsPublisher___SubmitAndWaitOnThreadpoolWorkItem____13____lambda_1___
0x1800167f9  nop
0x1800167fa  mov     qword ptr [rbp+57h+var_98], r12
0x1800167fe  mov     qword ptr [rbp+57h+var_98+8], rbx
0x180016802  cmp     dword ptr [r14], 1
0x180016806  jnz     loc_18001688E
0x18001680c  lea     rsi, [r14+0C0h]
0x180016813  lock inc dword ptr [rbx+8]
0x180016817  mov     [rbp+57h+var_88], r12
0x18001681b  mov     [rbp+57h+var_80], rbx
0x18001681f  mov     rax, [rsi+20h]
0x180016823  inc     rax
0x180016826  cmp     [rsi+10h], rax
0x18001682a  ja      short loc_180016834
0x18001682c  mov     rcx, rsi
0x18001682f  call    ?_Growmap@?$deque@V?$shared_ptr@VWaitableOperation@@@std@@V?$allocator@V?$shared_ptr@VWaitableOperation@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::shared_ptr<WaitableOperation>>::_Growmap(unsigned __int64)
0x180016834  mov     rdx, [rsi+10h]
0x180016838  dec     rdx
0x18001683b  and     [rsi+18h], rdx
0x18001683f  mov     rax, [rsi+20h]
0x180016843  add     rax, [rsi+18h]
0x180016847  mov     [rbp+57h+arg_0], rax
0x18001684b  mov     r13, rax
0x18001684e  and     r13, rdx
0x180016851  mov     rax, [rsi+8]
0x180016855  cmp     qword ptr [rax+r13*8], 0
0x18001685a  jnz     short loc_18001686E
0x18001685c  mov     ecx, 10h; Size
0x180016861  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016866  mov     rcx, [rsi+8]
0x18001686a  mov     [rcx+r13*8], rax
0x18001686e  mov     rcx, [rsi+10h]
0x180016872  dec     rcx
0x180016875  and     rcx, [rbp+57h+arg_0]
0x180016879  mov     rax, [rsi+8]
0x18001687d  mov     rcx, [rax+rcx*8]
0x180016881  mov     [rcx], r12
0x180016884  mov     [rcx+8], rbx
0x180016888  inc     qword ptr [rsi+20h]
0x18001688c  jmp     short loc_1800168C1
0x18001688e  lea     rcx, [r14+0E8h]
0x180016895  xorps   xmm0, xmm0
0x180016898  movdqu  [rbp+57h+var_78], xmm0
0x18001689d  lock inc dword ptr [rbx+8]
0x1800168a1  mov     qword ptr [rbp+57h+var_78], r12
0x1800168a5  mov     qword ptr [rbp+57h+var_78+8], rbx
0x1800168a9  mov     [rbp+57h+var_38], 1
0x1800168ad  lea     rdx, [rbp+57h+var_78]
0x1800168b1  call    ?push_back@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@2@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::push_back(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x1800168b6  nop
0x1800168b7  lea     rcx, [rbp+57h+var_78]
0x1800168bb  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x1800168c0  nop
0x1800168c1  test    r15, r15
0x1800168c4  jz      short loc_1800168CF
0x1800168c6  mov     rcx, r15; lpCriticalSection
0x1800168c9  call    cs:__imp_LeaveCriticalSection
0x1800168cf  lock inc qword ptr [r14+88h]
0x1800168d7  mov     rcx, [r14+80h]; pwk
0x1800168de  call    cs:__imp_SubmitThreadpoolWork
0x1800168e4  mov     [rdi], r12
0x1800168e7  mov     [rdi+8], rbx
0x1800168eb  mov     rax, rdi
0x1800168ee  mov     rbx, [rsp+0C0h+arg_8]
0x1800168f6  add     rsp, 90h
0x1800168fd  pop     r15
0x1800168ff  pop     r14
0x180016901  pop     r13
0x180016903  pop     r12
0x180016905  pop     rdi
0x180016906  pop     rsi
0x180016907  pop     rbp
0x180016908  retn
```
