# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180018824`
- end: `0x1800188b5`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007fc4`
- `0x1800081f8`
- `0x18000af64`
- `0x18000f090`
- `0x18000f42c`
- `0x18000f574`

## callees

- `0x180018824`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18001885f`
- `KERNEL32!SetThreadpoolTimer` at `0x18001885f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180018882`
- `KERNEL32!CloseThreadpoolTimer` at `0x180018882`
- `KERNEL32!GetLastError` at `0x180018846`
- `KERNEL32!GetLastError` at `0x180018846`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180018873`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180018873`
- `KERNEL32!SetLastError` at `0x180018890`
- `KERNEL32!SetLastError` at `0x180018890`

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
0x180018824  mov     [rsp+arg_0], rbx
0x180018829  mov     [rsp+arg_8], rbp
0x18001882e  mov     [rsp+arg_10], rsi
0x180018833  push    rdi
0x180018834  sub     rsp, 20h
0x180018838  mov     rsi, [rcx]
0x18001883b  mov     rbp, rdx
0x18001883e  mov     rdi, rcx
0x180018841  test    rsi, rsi
0x180018844  jz      short loc_18001889C
0x180018846  call    cs:__imp_GetLastError
0x18001884d  nop     dword ptr [rax+rax+00h]
0x180018852  xor     r9d, r9d; msWindowLength
0x180018855  xor     r8d, r8d; msPeriod
0x180018858  xor     edx, edx; pftDueTime
0x18001885a  mov     rcx, rsi; pti
0x18001885d  mov     ebx, eax
0x18001885f  call    cs:__imp_SetThreadpoolTimer
0x180018866  nop     dword ptr [rax+rax+00h]
0x18001886b  mov     edx, 1; fCancelPendingCallbacks
0x180018870  mov     rcx, rsi; pti
0x180018873  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001887a  nop     dword ptr [rax+rax+00h]
0x18001887f  mov     rcx, rsi; pti
0x180018882  call    cs:__imp_CloseThreadpoolTimer
0x180018889  nop     dword ptr [rax+rax+00h]
0x18001888e  mov     ecx, ebx; dwErrCode
0x180018890  call    cs:__imp_SetLastError
0x180018897  nop     dword ptr [rax+rax+00h]
0x18001889c  mov     rbx, [rsp+28h+arg_0]
0x1800188a1  mov     rsi, [rsp+28h+arg_10]
0x1800188a6  mov     [rdi], rbp
0x1800188a9  mov     rbp, [rsp+28h+arg_8]
0x1800188ae  add     rsp, 20h
0x1800188b2  pop     rdi
0x1800188b3  retn
```
