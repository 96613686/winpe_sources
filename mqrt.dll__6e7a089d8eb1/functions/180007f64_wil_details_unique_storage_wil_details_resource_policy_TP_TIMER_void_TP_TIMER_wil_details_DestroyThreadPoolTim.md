# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180007f64`
- end: `0x180007fb0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002920`
- `0x1800029a0`
- `0x180003968`

## callees

- `0x180003504`
- `0x180003b60`
- `0x180004148`
- `0x180007f64`

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
0x180007f64  mov     [rsp+arg_8], rbx
0x180007f69  mov     [rsp+arg_10], rsi
0x180007f6e  push    rdi
0x180007f6f  sub     rsp, 20h
0x180007f73  mov     rdi, [rcx]
0x180007f76  mov     rsi, rdx
0x180007f79  mov     rbx, rcx
0x180007f7c  test    rdi, rdi
0x180007f7f  jz      short loc_180007F9D
0x180007f81  lea     rcx, [rsp+28h+arg_0]; this
0x180007f86  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007f8b  mov     rcx, rdi; pti
0x180007f8e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180007f93  lea     rcx, [rsp+28h+arg_0]; this
0x180007f98  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180007f9d  mov     [rbx], rsi
0x180007fa0  mov     rbx, [rsp+28h+arg_8]
0x180007fa5  mov     rsi, [rsp+28h+arg_10]
0x180007faa  add     rsp, 20h
0x180007fae  pop     rdi
0x180007faf  retn
```
