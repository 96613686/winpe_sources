# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000d138`
- end: `0x18000d18b`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `83`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ce44`
- `0x18000cf34`
- `0x18000dc38`
- `0x18000dcb8`
- `0x18001a218`

## callees

- `0x18000b4e0`
- `0x18000d138`
- `0x18000d354`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d172`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d172`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF
  DWORD dwErrCode; // [rsp+34h] [rbp+Ch]

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
    if ( !v5 )
      SetLastError(dwErrCode);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000d138  mov     [rsp+arg_8], rbx
0x18000d13d  mov     [rsp+arg_10], rsi
0x18000d142  push    rdi
0x18000d143  sub     rsp, 20h
0x18000d147  mov     rdi, [rcx]
0x18000d14a  mov     rsi, rdx
0x18000d14d  mov     rbx, rcx
0x18000d150  test    rdi, rdi
0x18000d153  jz      short loc_18000D178
0x18000d155  lea     rcx, [rsp+28h+arg_0]; this
0x18000d15a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000d15f  mov     rcx, rdi; pti
0x18000d162  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000d167  cmp     [rsp+28h+arg_0], 0
0x18000d16c  jnz     short loc_18000D178
0x18000d16e  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x18000d172  call    cs:__imp_SetLastError
0x18000d178  mov     [rbx], rsi
0x18000d17b  mov     rbx, [rsp+28h+arg_8]
0x18000d180  mov     rsi, [rsp+28h+arg_10]
0x18000d185  add     rsp, 20h
0x18000d189  pop     rdi
0x18000d18a  retn
```
