# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000cfb4`
- end: `0x18000d000`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000afb0`
- `0x18000cd18`
- `0x18000cec0`
- `0x18000d30c`
- `0x18000d38c`
- `0x18001163c`

## callees

- `0x18000cfb4`
- `0x180011e6c`
- `0x1800120b4`
- `0x1800125e0`

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
0x18000cfb4  mov     [rsp+arg_8], rbx
0x18000cfb9  mov     [rsp+arg_10], rsi
0x18000cfbe  push    rdi
0x18000cfbf  sub     rsp, 20h
0x18000cfc3  mov     rdi, [rcx]
0x18000cfc6  mov     rsi, rdx
0x18000cfc9  mov     rbx, rcx
0x18000cfcc  test    rdi, rdi
0x18000cfcf  jz      short loc_18000CFED
0x18000cfd1  lea     rcx, [rsp+28h+arg_0]; this
0x18000cfd6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000cfdb  mov     rcx, rdi; pti
0x18000cfde  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000cfe3  lea     rcx, [rsp+28h+arg_0]; this
0x18000cfe8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000cfed  mov     [rbx], rsi
0x18000cff0  mov     rbx, [rsp+28h+arg_8]
0x18000cff5  mov     rsi, [rsp+28h+arg_10]
0x18000cffa  add     rsp, 20h
0x18000cffe  pop     rdi
0x18000cfff  retn
```
