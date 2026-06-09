# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180019f1c`
- end: `0x180019f96`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001630c`
- `0x180016d54`
- `0x180017908`

## callees

- `0x180019f1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019f7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019f7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f33`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019f60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019f60`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019f4c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019f4c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019f6f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019f6f`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180019f1c  push    rbx
0x180019f1e  push    rbp
0x180019f1f  push    rsi
0x180019f20  push    rdi
0x180019f21  sub     rsp, 28h
0x180019f25  mov     rsi, [rcx]
0x180019f28  mov     rbp, rdx
0x180019f2b  mov     rdi, rcx
0x180019f2e  test    rsi, rsi
0x180019f31  jz      short loc_180019F89
0x180019f33  call    cs:__imp_GetLastError
0x180019f3a  nop     dword ptr [rax+rax+00h]
0x180019f3f  xor     r9d, r9d; msWindowLength
0x180019f42  xor     r8d, r8d; msPeriod
0x180019f45  xor     edx, edx; pftDueTime
0x180019f47  mov     rcx, rsi; pti
0x180019f4a  mov     ebx, eax
0x180019f4c  call    cs:__imp_SetThreadpoolTimer
0x180019f53  nop     dword ptr [rax+rax+00h]
0x180019f58  mov     edx, 1; fCancelPendingCallbacks
0x180019f5d  mov     rcx, rsi; pti
0x180019f60  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180019f67  nop     dword ptr [rax+rax+00h]
0x180019f6c  mov     rcx, rsi; pti
0x180019f6f  call    cs:__imp_CloseThreadpoolTimer
0x180019f76  nop     dword ptr [rax+rax+00h]
0x180019f7b  mov     ecx, ebx; dwErrCode
0x180019f7d  call    cs:__imp_SetLastError
0x180019f84  nop     dword ptr [rax+rax+00h]
0x180019f89  mov     [rdi], rbp
0x180019f8c  add     rsp, 28h
0x180019f90  pop     rdi
0x180019f91  pop     rsi
0x180019f92  pop     rbp
0x180019f93  pop     rbx
0x180019f94  retn
```
