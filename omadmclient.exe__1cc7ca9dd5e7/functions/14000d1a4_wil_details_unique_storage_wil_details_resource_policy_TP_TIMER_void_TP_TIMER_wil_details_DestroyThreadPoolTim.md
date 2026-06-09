# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x14000d1a4`
- end: `0x14000d21e`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400068a4`
- `0x140006ad8`
- `0x140007d84`
- `0x140009888`
- `0x140009940`
- `0x140010d90`

## callees

- `0x14000d1a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d205`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d205`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d1d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d1d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000d1e8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000d1e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000d1f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000d1f7`

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
0x14000d1a4  push    rbx
0x14000d1a6  push    rbp
0x14000d1a7  push    rsi
0x14000d1a8  push    rdi
0x14000d1a9  sub     rsp, 28h
0x14000d1ad  mov     rsi, [rcx]
0x14000d1b0  mov     rbp, rdx
0x14000d1b3  mov     rdi, rcx
0x14000d1b6  test    rsi, rsi
0x14000d1b9  jz      short loc_14000D211
0x14000d1bb  call    cs:__imp_GetLastError
0x14000d1c2  nop     dword ptr [rax+rax+00h]
0x14000d1c7  xor     r9d, r9d; msWindowLength
0x14000d1ca  xor     r8d, r8d; msPeriod
0x14000d1cd  xor     edx, edx; pftDueTime
0x14000d1cf  mov     rcx, rsi; pti
0x14000d1d2  mov     ebx, eax
0x14000d1d4  call    cs:__imp_SetThreadpoolTimer
0x14000d1db  nop     dword ptr [rax+rax+00h]
0x14000d1e0  mov     edx, 1; fCancelPendingCallbacks
0x14000d1e5  mov     rcx, rsi; pti
0x14000d1e8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000d1ef  nop     dword ptr [rax+rax+00h]
0x14000d1f4  mov     rcx, rsi; pti
0x14000d1f7  call    cs:__imp_CloseThreadpoolTimer
0x14000d1fe  nop     dword ptr [rax+rax+00h]
0x14000d203  mov     ecx, ebx; dwErrCode
0x14000d205  call    cs:__imp_SetLastError
0x14000d20c  nop     dword ptr [rax+rax+00h]
0x14000d211  mov     [rdi], rbp
0x14000d214  add     rsp, 28h
0x14000d218  pop     rdi
0x14000d219  pop     rsi
0x14000d21a  pop     rbp
0x14000d21b  pop     rbx
0x14000d21c  retn
```
