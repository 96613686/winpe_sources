# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180009c50`
- end: `0x180009ce1`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003b34`
- `0x180003d68`
- `0x180004f94`
- `0x180006824`
- `0x1800068d8`
- `0x18000ad90`
- `0x18000b194`
- `0x18000d498`
- `0x18000f9e4`
- `0x1800106a0`
- `0x18002ea48`

## callees

- `0x180009c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cbc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009cae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009cae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009c9f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009c9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009c8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009c8b`

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
0x180009c50  mov     [rsp+arg_0], rbx
0x180009c55  mov     [rsp+arg_8], rbp
0x180009c5a  mov     [rsp+arg_10], rsi
0x180009c5f  push    rdi
0x180009c60  sub     rsp, 20h
0x180009c64  mov     rsi, [rcx]
0x180009c67  mov     rbp, rdx
0x180009c6a  mov     rdi, rcx
0x180009c6d  test    rsi, rsi
0x180009c70  jz      short loc_180009CC8
0x180009c72  call    cs:__imp_GetLastError
0x180009c79  nop     dword ptr [rax+rax+00h]
0x180009c7e  xor     r9d, r9d; msWindowLength
0x180009c81  xor     r8d, r8d; msPeriod
0x180009c84  xor     edx, edx; pftDueTime
0x180009c86  mov     rcx, rsi; pti
0x180009c89  mov     ebx, eax
0x180009c8b  call    cs:__imp_SetThreadpoolTimer
0x180009c92  nop     dword ptr [rax+rax+00h]
0x180009c97  mov     edx, 1; fCancelPendingCallbacks
0x180009c9c  mov     rcx, rsi; pti
0x180009c9f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009ca6  nop     dword ptr [rax+rax+00h]
0x180009cab  mov     rcx, rsi; pti
0x180009cae  call    cs:__imp_CloseThreadpoolTimer
0x180009cb5  nop     dword ptr [rax+rax+00h]
0x180009cba  mov     ecx, ebx; dwErrCode
0x180009cbc  call    cs:__imp_SetLastError
0x180009cc3  nop     dword ptr [rax+rax+00h]
0x180009cc8  mov     rbx, [rsp+28h+arg_0]
0x180009ccd  mov     rsi, [rsp+28h+arg_10]
0x180009cd2  mov     [rdi], rbp
0x180009cd5  mov     rbp, [rsp+28h+arg_8]
0x180009cda  add     rsp, 20h
0x180009cde  pop     rdi
0x180009cdf  retn
```
