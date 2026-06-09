# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180022a84`
- end: `0x180022afe`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180013e98`
- `0x180016d24`
- `0x180020c50`

## callees

- `0x180022a84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022ae5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022ae5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022ac8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022ac8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022ad7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022ad7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022ab4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022ab4`

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
0x180022a84  push    rbx
0x180022a86  push    rbp
0x180022a87  push    rsi
0x180022a88  push    rdi
0x180022a89  sub     rsp, 28h
0x180022a8d  mov     rsi, [rcx]
0x180022a90  mov     rbp, rdx
0x180022a93  mov     rdi, rcx
0x180022a96  test    rsi, rsi
0x180022a99  jz      short loc_180022AF1
0x180022a9b  call    cs:__imp_GetLastError
0x180022aa2  nop     dword ptr [rax+rax+00h]
0x180022aa7  xor     r9d, r9d; msWindowLength
0x180022aaa  xor     r8d, r8d; msPeriod
0x180022aad  xor     edx, edx; pftDueTime
0x180022aaf  mov     rcx, rsi; pti
0x180022ab2  mov     ebx, eax
0x180022ab4  call    cs:__imp_SetThreadpoolTimer
0x180022abb  nop     dword ptr [rax+rax+00h]
0x180022ac0  mov     edx, 1; fCancelPendingCallbacks
0x180022ac5  mov     rcx, rsi; pti
0x180022ac8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180022acf  nop     dword ptr [rax+rax+00h]
0x180022ad4  mov     rcx, rsi; pti
0x180022ad7  call    cs:__imp_CloseThreadpoolTimer
0x180022ade  nop     dword ptr [rax+rax+00h]
0x180022ae3  mov     ecx, ebx; dwErrCode
0x180022ae5  call    cs:__imp_SetLastError
0x180022aec  nop     dword ptr [rax+rax+00h]
0x180022af1  mov     [rdi], rbp
0x180022af4  add     rsp, 28h
0x180022af8  pop     rdi
0x180022af9  pop     rsi
0x180022afa  pop     rbp
0x180022afb  pop     rbx
0x180022afc  retn
```
