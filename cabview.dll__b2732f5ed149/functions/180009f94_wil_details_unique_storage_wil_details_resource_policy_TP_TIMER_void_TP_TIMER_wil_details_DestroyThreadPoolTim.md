# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180009f94`
- end: `0x180009fe0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800031ac`
- `0x180003228`
- `0x180004088`
- `0x180004138`
- `0x1800074fc`
- `0x180007694`

## callees

- `0x180003c6c`
- `0x180004298`
- `0x1800053c0`
- `0x180009f94`

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
0x180009f94  mov     [rsp+arg_8], rbx
0x180009f99  mov     [rsp+arg_10], rsi
0x180009f9e  push    rdi
0x180009f9f  sub     rsp, 20h
0x180009fa3  mov     rdi, [rcx]
0x180009fa6  mov     rsi, rdx
0x180009fa9  mov     rbx, rcx
0x180009fac  test    rdi, rdi
0x180009faf  jz      short loc_180009FCD
0x180009fb1  lea     rcx, [rsp+28h+arg_0]; this
0x180009fb6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009fbb  mov     rcx, rdi; pti
0x180009fbe  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180009fc3  lea     rcx, [rsp+28h+arg_0]; this
0x180009fc8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009fcd  mov     [rbx], rsi
0x180009fd0  mov     rbx, [rsp+28h+arg_8]
0x180009fd5  mov     rsi, [rsp+28h+arg_10]
0x180009fda  add     rsp, 20h
0x180009fde  pop     rdi
0x180009fdf  retn
```
