# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(void)

- ea: `0x180009f6c`
- end: `0x180009fa8`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18009e15d`

## callees

- `0x180009f6c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009f9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009f9c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009f93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009f93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009f85`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009f85`

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
0x180009f6c  push    rbx
0x180009f6e  sub     rsp, 20h
0x180009f72  mov     rbx, [rcx]
0x180009f75  test    rbx, rbx
0x180009f78  jz      short loc_180009FA2
0x180009f7a  xor     r9d, r9d; msWindowLength
0x180009f7d  xor     r8d, r8d; msPeriod
0x180009f80  xor     edx, edx; pftDueTime
0x180009f82  mov     rcx, rbx; pti
0x180009f85  call    cs:__imp_SetThreadpoolTimer
0x180009f8b  mov     edx, 1; fCancelPendingCallbacks
0x180009f90  mov     rcx, rbx; pti
0x180009f93  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009f99  mov     rcx, rbx; pti
0x180009f9c  call    cs:__imp_CloseThreadpoolTimer
0x180009fa2  add     rsp, 20h
0x180009fa6  pop     rbx
0x180009fa7  retn
```
