# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x140018a8c`
- end: `0x140018b06`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140015c3c`
- `0x140016488`
- `0x140016d68`

## callees

- `0x140018a8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018aa3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018aed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018aed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140018ad0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140018ad0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140018abc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140018abc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140018adf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140018adf`

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
0x140018a8c  push    rbx
0x140018a8e  push    rbp
0x140018a8f  push    rsi
0x140018a90  push    rdi
0x140018a91  sub     rsp, 28h
0x140018a95  mov     rsi, [rcx]
0x140018a98  mov     rbp, rdx
0x140018a9b  mov     rdi, rcx
0x140018a9e  test    rsi, rsi
0x140018aa1  jz      short loc_140018AF9
0x140018aa3  call    cs:__imp_GetLastError
0x140018aaa  nop     dword ptr [rax+rax+00h]
0x140018aaf  xor     r9d, r9d; msWindowLength
0x140018ab2  xor     r8d, r8d; msPeriod
0x140018ab5  xor     edx, edx; pftDueTime
0x140018ab7  mov     rcx, rsi; pti
0x140018aba  mov     ebx, eax
0x140018abc  call    cs:__imp_SetThreadpoolTimer
0x140018ac3  nop     dword ptr [rax+rax+00h]
0x140018ac8  mov     edx, 1; fCancelPendingCallbacks
0x140018acd  mov     rcx, rsi; pti
0x140018ad0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140018ad7  nop     dword ptr [rax+rax+00h]
0x140018adc  mov     rcx, rsi; pti
0x140018adf  call    cs:__imp_CloseThreadpoolTimer
0x140018ae6  nop     dword ptr [rax+rax+00h]
0x140018aeb  mov     ecx, ebx; dwErrCode
0x140018aed  call    cs:__imp_SetLastError
0x140018af4  nop     dword ptr [rax+rax+00h]
0x140018af9  mov     [rdi], rbp
0x140018afc  add     rsp, 28h
0x140018b00  pop     rdi
0x140018b01  pop     rsi
0x140018b02  pop     rbp
0x140018b03  pop     rbx
0x140018b04  retn
```
