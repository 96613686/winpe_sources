# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800364f8`
- end: `0x180036544`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180031530`
- `0x1800315ac`
- `0x1800323a4`

## callees

- `0x180031f54`
- `0x180032504`
- `0x180032a60`
- `0x1800364f8`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x1800364f8  mov     [rsp+arg_8], rbx
0x1800364fd  mov     [rsp+arg_10], rsi
0x180036502  push    rdi
0x180036503  sub     rsp, 20h
0x180036507  mov     rdi, [rcx]
0x18003650a  mov     rsi, rdx
0x18003650d  mov     rbx, rcx
0x180036510  test    rdi, rdi
0x180036513  jz      short loc_180036531
0x180036515  lea     rcx, [rsp+28h+arg_0]; this
0x18003651a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003651f  mov     rcx, rdi; pti
0x180036522  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180036527  lea     rcx, [rsp+28h+arg_0]; this
0x18003652c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036531  mov     [rbx], rsi
0x180036534  mov     rbx, [rsp+28h+arg_8]
0x180036539  mov     rsi, [rsp+28h+arg_10]
0x18003653e  add     rsp, 20h
0x180036542  pop     rdi
0x180036543  retn
```
