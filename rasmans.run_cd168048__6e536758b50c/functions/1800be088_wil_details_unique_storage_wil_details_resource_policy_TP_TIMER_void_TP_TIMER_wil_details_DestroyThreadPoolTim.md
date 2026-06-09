# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800be088`
- end: `0x1800be102`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800b4850`
- `0x1800b4a74`
- `0x1800b6a08`
- `0x1800baa68`
- `0x1800bade4`
- `0x1800baf58`

## callees

- `0x1800be088`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be09f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be09f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800be0e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800be0e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800be0b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800be0b8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800be0cc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800be0cc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800be0db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800be0db`

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
0x1800be088  push    rbx
0x1800be08a  push    rbp
0x1800be08b  push    rsi
0x1800be08c  push    rdi
0x1800be08d  sub     rsp, 28h
0x1800be091  mov     rsi, [rcx]
0x1800be094  mov     rbp, rdx
0x1800be097  mov     rdi, rcx
0x1800be09a  test    rsi, rsi
0x1800be09d  jz      short loc_1800BE0F5
0x1800be09f  call    cs:__imp_GetLastError
0x1800be0a6  nop     dword ptr [rax+rax+00h]
0x1800be0ab  xor     r9d, r9d; msWindowLength
0x1800be0ae  xor     r8d, r8d; msPeriod
0x1800be0b1  xor     edx, edx; pftDueTime
0x1800be0b3  mov     rcx, rsi; pti
0x1800be0b6  mov     ebx, eax
0x1800be0b8  call    cs:__imp_SetThreadpoolTimer
0x1800be0bf  nop     dword ptr [rax+rax+00h]
0x1800be0c4  mov     edx, 1; fCancelPendingCallbacks
0x1800be0c9  mov     rcx, rsi; pti
0x1800be0cc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800be0d3  nop     dword ptr [rax+rax+00h]
0x1800be0d8  mov     rcx, rsi; pti
0x1800be0db  call    cs:__imp_CloseThreadpoolTimer
0x1800be0e2  nop     dword ptr [rax+rax+00h]
0x1800be0e7  mov     ecx, ebx; dwErrCode
0x1800be0e9  call    cs:__imp_SetLastError
0x1800be0f0  nop     dword ptr [rax+rax+00h]
0x1800be0f5  mov     [rdi], rbp
0x1800be0f8  add     rsp, 28h
0x1800be0fc  pop     rdi
0x1800be0fd  pop     rsi
0x1800be0fe  pop     rbp
0x1800be0ff  pop     rbx
0x1800be100  retn
```
