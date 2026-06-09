# std::unique_ptr<LocalCorePerformanceTelemetryCollector,std::default_delete<LocalCorePerformanceTelemetryCollector>>::~unique_ptr<LocalCorePerformanceTelemetryCollector,std::default_delete<LocalCorePerformanceTelemetryCollector>>(void)

- ea: `0x18000b194`
- end: `0x18000b20d`
- name: `??1?$unique_ptr@VLocalCorePerformanceTelemetryCollector@@U?$default_delete@VLocalCorePerformanceTelemetryCollector@@@std@@@std@@QEAA@XZ`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000b214`
- `0x18000d498`

## callees

- `0x180001b94`
- `0x180009c50`
- `0x18000b194`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b1e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b1e8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b1d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b1d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b1c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b1c5`

## pseudocode

```c
void __fastcall std::unique_ptr<LocalCorePerformanceTelemetryCollector>::~unique_ptr<LocalCorePerformanceTelemetryCollector>(
        struct _TP_TIMER ***a1)
{
  struct _TP_TIMER **v1; // rdi
  struct _TP_TIMER *v2; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      v1 + 1,
      0);
    v2 = v1[1];
    if ( v2 )
    {
      SetThreadpoolTimer(v1[1], 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v2, 1);
      CloseThreadpoolTimer(v2);
    }
    operator delete(v1, (const struct std::nothrow_t *)0x10);
  }
}

```

## disassembly

```asm
0x18000b194  mov     [rsp+arg_0], rbx
0x18000b199  push    rdi
0x18000b19a  sub     rsp, 20h
0x18000b19e  mov     rdi, [rcx]
0x18000b1a1  test    rdi, rdi
0x18000b1a4  jz      short loc_18000B201
0x18000b1a6  xor     edx, edx
0x18000b1a8  lea     rcx, [rdi+8]
0x18000b1ac  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000b1b1  mov     rbx, [rdi+8]
0x18000b1b5  test    rbx, rbx
0x18000b1b8  jz      short loc_18000B1F4
0x18000b1ba  xor     r9d, r9d; msWindowLength
0x18000b1bd  xor     r8d, r8d; msPeriod
0x18000b1c0  xor     edx, edx; pftDueTime
0x18000b1c2  mov     rcx, rbx; pti
0x18000b1c5  call    cs:__imp_SetThreadpoolTimer
0x18000b1cc  nop     dword ptr [rax+rax+00h]
0x18000b1d1  mov     edx, 1; fCancelPendingCallbacks
0x18000b1d6  mov     rcx, rbx; pti
0x18000b1d9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b1e0  nop     dword ptr [rax+rax+00h]
0x18000b1e5  mov     rcx, rbx; pti
0x18000b1e8  call    cs:__imp_CloseThreadpoolTimer
0x18000b1ef  nop     dword ptr [rax+rax+00h]
0x18000b1f4  mov     edx, 10h; struct std::nothrow_t *
0x18000b1f9  mov     rcx, rdi; void *
0x18000b1fc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b201  mov     rbx, [rsp+28h+arg_0]
0x18000b206  add     rsp, 20h
0x18000b20a  pop     rdi
0x18000b20b  retn
```
