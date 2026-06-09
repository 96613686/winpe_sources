# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800033b0`
- end: `0x1800033fc`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003140`
- `0x18000321c`

## callees

- `0x1800032ec`
- `0x18000338c`
- `0x1800033b0`
- `0x1800067f0`

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
0x1800033b0  mov     [rsp+arg_8], rbx
0x1800033b5  mov     [rsp+arg_10], rsi
0x1800033ba  push    rdi
0x1800033bb  sub     rsp, 20h
0x1800033bf  mov     rdi, [rcx]
0x1800033c2  mov     rsi, rdx
0x1800033c5  mov     rbx, rcx
0x1800033c8  test    rdi, rdi
0x1800033cb  jz      short loc_1800033E9
0x1800033cd  lea     rcx, [rsp+28h+arg_0]; this
0x1800033d2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800033d7  mov     rcx, rdi; pti
0x1800033da  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800033df  lea     rcx, [rsp+28h+arg_0]; this
0x1800033e4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800033e9  mov     [rbx], rsi
0x1800033ec  mov     rbx, [rsp+28h+arg_8]
0x1800033f1  mov     rsi, [rsp+28h+arg_10]
0x1800033f6  add     rsp, 20h
0x1800033fa  pop     rdi
0x1800033fb  retn
```
