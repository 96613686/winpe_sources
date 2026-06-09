# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000b8a0`
- end: `0x18000b91a`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800050b4`
- `0x1800052e8`
- `0x1800065ec`
- `0x180008198`
- `0x180008250`
- `0x18001715c`

## callees

- `0x18000b8a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b8d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b8d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b8e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b8e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b8f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b8f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
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
0x18000b8a0  push    rbx
0x18000b8a2  push    rbp
0x18000b8a3  push    rsi
0x18000b8a4  push    rdi
0x18000b8a5  sub     rsp, 28h
0x18000b8a9  mov     rsi, [rcx]
0x18000b8ac  mov     rbp, rdx
0x18000b8af  mov     rdi, rcx
0x18000b8b2  test    rsi, rsi
0x18000b8b5  jz      short loc_18000B90D
0x18000b8b7  call    cs:__imp_GetLastError
0x18000b8be  nop     dword ptr [rax+rax+00h]
0x18000b8c3  xor     r9d, r9d; msWindowLength
0x18000b8c6  xor     r8d, r8d; msPeriod
0x18000b8c9  xor     edx, edx; pftDueTime
0x18000b8cb  mov     rcx, rsi; pti
0x18000b8ce  mov     ebx, eax
0x18000b8d0  call    cs:__imp_SetThreadpoolTimer
0x18000b8d7  nop     dword ptr [rax+rax+00h]
0x18000b8dc  mov     edx, 1; fCancelPendingCallbacks
0x18000b8e1  mov     rcx, rsi; pti
0x18000b8e4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b8eb  nop     dword ptr [rax+rax+00h]
0x18000b8f0  mov     rcx, rsi; pti
0x18000b8f3  call    cs:__imp_CloseThreadpoolTimer
0x18000b8fa  nop     dword ptr [rax+rax+00h]
0x18000b8ff  mov     ecx, ebx; dwErrCode
0x18000b901  call    cs:__imp_SetLastError
0x18000b908  nop     dword ptr [rax+rax+00h]
0x18000b90d  mov     [rdi], rbp
0x18000b910  add     rsp, 28h
0x18000b914  pop     rdi
0x18000b915  pop     rsi
0x18000b916  pop     rbp
0x18000b917  pop     rbx
0x18000b918  retn
```
