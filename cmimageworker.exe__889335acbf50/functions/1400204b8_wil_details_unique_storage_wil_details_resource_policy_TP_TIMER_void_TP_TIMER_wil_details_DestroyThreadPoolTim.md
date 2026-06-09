# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1400204b8`
- end: `0x140020532`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140015b98`
- `0x140015dcc`
- `0x14001967c`
- `0x14001bf5c`
- `0x14001c1c4`

## callees

- `0x1400204b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140020519`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140020519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400204cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400204cf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400204e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400204e8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400204fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400204fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14002050b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14002050b`

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
0x1400204b8  push    rbx
0x1400204ba  push    rbp
0x1400204bb  push    rsi
0x1400204bc  push    rdi
0x1400204bd  sub     rsp, 28h
0x1400204c1  mov     rsi, [rcx]
0x1400204c4  mov     rbp, rdx
0x1400204c7  mov     rdi, rcx
0x1400204ca  test    rsi, rsi
0x1400204cd  jz      short loc_140020525
0x1400204cf  call    cs:__imp_GetLastError
0x1400204d6  nop     dword ptr [rax+rax+00h]
0x1400204db  xor     r9d, r9d; msWindowLength
0x1400204de  xor     r8d, r8d; msPeriod
0x1400204e1  xor     edx, edx; pftDueTime
0x1400204e3  mov     rcx, rsi; pti
0x1400204e6  mov     ebx, eax
0x1400204e8  call    cs:__imp_SetThreadpoolTimer
0x1400204ef  nop     dword ptr [rax+rax+00h]
0x1400204f4  mov     edx, 1; fCancelPendingCallbacks
0x1400204f9  mov     rcx, rsi; pti
0x1400204fc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140020503  nop     dword ptr [rax+rax+00h]
0x140020508  mov     rcx, rsi; pti
0x14002050b  call    cs:__imp_CloseThreadpoolTimer
0x140020512  nop     dword ptr [rax+rax+00h]
0x140020517  mov     ecx, ebx; dwErrCode
0x140020519  call    cs:__imp_SetLastError
0x140020520  nop     dword ptr [rax+rax+00h]
0x140020525  mov     [rdi], rbp
0x140020528  add     rsp, 28h
0x14002052c  pop     rdi
0x14002052d  pop     rsi
0x14002052e  pop     rbp
0x14002052f  pop     rbx
0x140020530  retn
```
