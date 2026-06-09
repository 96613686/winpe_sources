# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(void)

- ea: `0x180007618`
- end: `0x180007654`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800d0222`

## callees

- `0x180007618`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007631`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007631`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007648`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007648`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000763f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000763f`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(
        PTP_TIMER *a1)
{
  struct _TP_TIMER *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    SetThreadpoolTimer(*a1, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v1, 1);
    CloseThreadpoolTimer(v1);
  }
}

```

## disassembly

```asm
0x180007618  push    rbx
0x18000761a  sub     rsp, 20h
0x18000761e  mov     rbx, [rcx]
0x180007621  test    rbx, rbx
0x180007624  jz      short loc_18000764E
0x180007626  xor     r9d, r9d; msWindowLength
0x180007629  xor     r8d, r8d; msPeriod
0x18000762c  xor     edx, edx; pftDueTime
0x18000762e  mov     rcx, rbx; pti
0x180007631  call    cs:__imp_SetThreadpoolTimer
0x180007637  mov     edx, 1; fCancelPendingCallbacks
0x18000763c  mov     rcx, rbx; pti
0x18000763f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007645  mov     rcx, rbx; pti
0x180007648  call    cs:__imp_CloseThreadpoolTimer
0x18000764e  add     rsp, 20h
0x180007652  pop     rbx
0x180007653  retn
```
