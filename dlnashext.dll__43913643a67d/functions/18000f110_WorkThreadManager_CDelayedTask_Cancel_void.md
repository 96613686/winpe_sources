# WorkThreadManager::CDelayedTask::Cancel(void)

- ea: `0x18000f110`
- end: `0x18000f16f`
- name: `?Cancel@CDelayedTask@WorkThreadManager@@UEAAXXZ`
- size: `95`
- prototype: `void __fastcall(WorkThreadManager::CDelayedTask *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005f60`
- `0x18000f110`
- `0x18000f178`
- `0x18001272e`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f146`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f146`

## pseudocode

```c
void __fastcall WorkThreadManager::CDelayedTask::Cancel(WorkThreadManager::CDelayedTask *this)
{
  struct _TP_TIMER *v2; // rbx
  int v3; // edi
  struct _TP_TIMER *v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _TP_TIMER *)_InterlockedExchange64((volatile __int64 *)this + 3, 0);
  v4 = v2;
  if ( v2 )
  {
    v3 = *((_DWORD *)this + 12);
    if ( v3 != GetCurrentThreadId_0() )
      WaitForThreadpoolTimerCallbacks(v2, 1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 40);
  }
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&v4);
}

```

## disassembly

```asm
0x18000f110  mov     [rsp+arg_8], rbx
0x18000f115  mov     [rsp+arg_10], rsi
0x18000f11a  push    rdi
0x18000f11b  sub     rsp, 20h
0x18000f11f  xor     ebx, ebx
0x18000f121  mov     rsi, rcx
0x18000f124  xchg    rbx, [rcx+18h]
0x18000f128  mov     [rsp+28h+arg_0], rbx
0x18000f12d  test    rbx, rbx
0x18000f130  jz      short loc_18000F155
0x18000f132  mov     edi, [rcx+30h]
0x18000f135  call    GetCurrentThreadId_0
0x18000f13a  cmp     edi, eax
0x18000f13c  jz      short loc_18000F14C
0x18000f13e  mov     edx, 1; fCancelPendingCallbacks
0x18000f143  mov     rcx, rbx; pti
0x18000f146  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f14c  lea     rcx, [rsi+28h]
0x18000f150  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f155  lea     rcx, [rsp+28h+arg_0]
0x18000f15a  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x18000f15f  mov     rbx, [rsp+28h+arg_8]
0x18000f164  mov     rsi, [rsp+28h+arg_10]
0x18000f169  add     rsp, 20h
0x18000f16d  pop     rdi
0x18000f16e  retn
```
