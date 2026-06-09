# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180004758`
- end: `0x180004793`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `59`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002d2c`
- `0x180002f80`
- `0x180003160`
- `0x180004838`
- `0x180004970`
- `0x1800086dc`

## callees

- `0x180004758`
- `0x18000479c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000476f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000476f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004781`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004781`

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
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180004758  push    rbx
0x18000475a  push    rbp
0x18000475b  push    rsi
0x18000475c  push    rdi
0x18000475d  sub     rsp, 28h
0x180004761  mov     rsi, [rcx]
0x180004764  mov     rbp, rdx
0x180004767  mov     rdi, rcx
0x18000476a  test    rsi, rsi
0x18000476d  jz      short loc_180004787
0x18000476f  call    cs:__imp_GetLastError
0x180004775  mov     rcx, rsi; pti
0x180004778  mov     ebx, eax
0x18000477a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000477f  mov     ecx, ebx; dwErrCode
0x180004781  call    cs:__imp_SetLastError
0x180004787  mov     [rdi], rbp
0x18000478a  add     rsp, 28h
0x18000478e  pop     rdi
0x18000478f  pop     rsi
0x180004790  pop     rbp
0x180004791  pop     rbx
0x180004792  retn
```
