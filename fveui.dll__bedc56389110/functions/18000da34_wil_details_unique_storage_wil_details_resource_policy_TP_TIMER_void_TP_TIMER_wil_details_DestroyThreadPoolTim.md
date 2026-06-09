# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000da34`
- end: `0x18000da80`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004828`
- `0x1800048d8`
- `0x18000a394`
- `0x18000a510`
- `0x18000a93c`
- `0x18001844c`

## callees

- `0x180004388`
- `0x180004aec`
- `0x1800057e8`
- `0x18000da34`

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
0x18000da34  mov     [rsp+arg_8], rbx
0x18000da39  mov     [rsp+arg_10], rsi
0x18000da3e  push    rdi
0x18000da3f  sub     rsp, 20h
0x18000da43  mov     rdi, [rcx]
0x18000da46  mov     rsi, rdx
0x18000da49  mov     rbx, rcx
0x18000da4c  test    rdi, rdi
0x18000da4f  jz      short loc_18000DA6D
0x18000da51  lea     rcx, [rsp+28h+arg_0]; this
0x18000da56  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000da5b  mov     rcx, rdi; pti
0x18000da5e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000da63  lea     rcx, [rsp+28h+arg_0]; this
0x18000da68  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000da6d  mov     [rbx], rsi
0x18000da70  mov     rbx, [rsp+28h+arg_8]
0x18000da75  mov     rsi, [rsp+28h+arg_10]
0x18000da7a  add     rsp, 20h
0x18000da7e  pop     rdi
0x18000da7f  retn
```
