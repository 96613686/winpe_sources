# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800142b8`
- end: `0x180014332`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a0d8`
- `0x18000a30c`
- `0x18000beb4`
- `0x180010168`
- `0x180010220`
- `0x180010384`

## callees

- `0x1800142b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014319`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800142fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800142fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800142e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800142e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001430b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001430b`

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
0x1800142b8  push    rbx
0x1800142ba  push    rbp
0x1800142bb  push    rsi
0x1800142bc  push    rdi
0x1800142bd  sub     rsp, 28h
0x1800142c1  mov     rsi, [rcx]
0x1800142c4  mov     rbp, rdx
0x1800142c7  mov     rdi, rcx
0x1800142ca  test    rsi, rsi
0x1800142cd  jz      short loc_180014325
0x1800142cf  call    cs:__imp_GetLastError
0x1800142d6  nop     dword ptr [rax+rax+00h]
0x1800142db  xor     r9d, r9d; msWindowLength
0x1800142de  xor     r8d, r8d; msPeriod
0x1800142e1  xor     edx, edx; pftDueTime
0x1800142e3  mov     rcx, rsi; pti
0x1800142e6  mov     ebx, eax
0x1800142e8  call    cs:__imp_SetThreadpoolTimer
0x1800142ef  nop     dword ptr [rax+rax+00h]
0x1800142f4  mov     edx, 1; fCancelPendingCallbacks
0x1800142f9  mov     rcx, rsi; pti
0x1800142fc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014303  nop     dword ptr [rax+rax+00h]
0x180014308  mov     rcx, rsi; pti
0x18001430b  call    cs:__imp_CloseThreadpoolTimer
0x180014312  nop     dword ptr [rax+rax+00h]
0x180014317  mov     ecx, ebx; dwErrCode
0x180014319  call    cs:__imp_SetLastError
0x180014320  nop     dword ptr [rax+rax+00h]
0x180014325  mov     [rdi], rbp
0x180014328  add     rsp, 28h
0x18001432c  pop     rdi
0x18001432d  pop     rsi
0x18001432e  pop     rbp
0x18001432f  pop     rbx
0x180014330  retn
```
