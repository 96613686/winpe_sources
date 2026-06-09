# `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x14000d2c0`
- end: `0x14000d341`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `129`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x14000d2c0`
- `0x14000f594`
- `0x140010d34`
- `0x140011720`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d2eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d2eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d2d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d2d9`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rdi

  if ( *Context )
  {
    v4 = (RTL_SRWLOCK *)(Context + 32);
    AcquireSRWLockExclusive((PSRWLOCK)Context + 4);
    Context[65] = 0;
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
      && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)Context) )
    {
      wil::details_abi::SubscriptionList::OnSignaled(
        (LPCRITICAL_SECTION)(*((_QWORD *)Context + 3) + 200LL),
        *((PSRWLOCK *)Context + 3));
      wil::details_abi::FeatureStateData::RecordUsage(*((PSRWLOCK *)Context + 3));
    }
  }
}

```

## disassembly

```asm
0x14000d2c0  mov     [rsp+arg_0], rbx
0x14000d2c5  push    rdi
0x14000d2c6  sub     rsp, 20h
0x14000d2ca  mov     rbx, rdx
0x14000d2cd  cmp     byte ptr [rdx], 0
0x14000d2d0  jz      short loc_14000D336
0x14000d2d2  lea     rdi, [rdx+20h]
0x14000d2d6  mov     rcx, rdi; SRWLock
0x14000d2d9  call    cs:__imp_AcquireSRWLockExclusive
0x14000d2df  mov     byte ptr [rbx+41h], 0
0x14000d2e3  test    rdi, rdi
0x14000d2e6  jz      short loc_14000D2F2
0x14000d2e8  mov     rcx, rdi; SRWLock
0x14000d2eb  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d2f1  nop
0x14000d2f2  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000d2f9  jnz     short loc_14000D336
0x14000d2fb  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000d302  test    rax, rax
0x14000d305  jz      short loc_14000D310
0x14000d307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d30c  test    al, al
0x14000d30e  jnz     short loc_14000D336
0x14000d310  mov     rcx, rbx; this
0x14000d313  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000d318  test    al, al
0x14000d31a  jz      short loc_14000D336
0x14000d31c  mov     rdx, [rbx+18h]; SRWLock
0x14000d320  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000d327  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000d32c  mov     rcx, [rbx+18h]; SRWLock
0x14000d330  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000d335  nop
0x14000d336  mov     rbx, [rsp+28h+arg_0]
0x14000d33b  add     rsp, 20h
0x14000d33f  pop     rdi
0x14000d340  retn
```
