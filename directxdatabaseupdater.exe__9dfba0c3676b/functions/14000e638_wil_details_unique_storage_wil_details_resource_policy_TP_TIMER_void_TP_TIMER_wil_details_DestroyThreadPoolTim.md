# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x14000e638`
- end: `0x14000e684`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140004094`
- `0x140004110`
- `0x140005fbc`

## callees

- `0x1400057cc`
- `0x140006320`
- `0x140006c1c`
- `0x14000e638`

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
0x14000e638  mov     [rsp+arg_8], rbx
0x14000e63d  mov     [rsp+arg_10], rsi
0x14000e642  push    rdi
0x14000e643  sub     rsp, 20h
0x14000e647  mov     rdi, [rcx]
0x14000e64a  mov     rsi, rdx
0x14000e64d  mov     rbx, rcx
0x14000e650  test    rdi, rdi
0x14000e653  jz      short loc_14000E671
0x14000e655  lea     rcx, [rsp+28h+arg_0]; this
0x14000e65a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000e65f  mov     rcx, rdi; pti
0x14000e662  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000e667  lea     rcx, [rsp+28h+arg_0]; this
0x14000e66c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000e671  mov     [rbx], rsi
0x14000e674  mov     rbx, [rsp+28h+arg_8]
0x14000e679  mov     rsi, [rsp+28h+arg_10]
0x14000e67e  add     rsp, 20h
0x14000e682  pop     rdi
0x14000e683  retn
```
