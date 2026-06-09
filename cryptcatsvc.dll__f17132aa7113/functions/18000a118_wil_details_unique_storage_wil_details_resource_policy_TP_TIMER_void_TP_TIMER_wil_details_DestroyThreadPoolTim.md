# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000a118`
- end: `0x18000a164`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a024`
- `0x18000a1cc`
- `0x18000a24c`
- `0x18000d0fc`
- `0x18000d178`
- `0x1800157d8`

## callees

- `0x18000a118`
- `0x18000dbf4`
- `0x18000df68`
- `0x18000e570`

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
0x18000a118  mov     [rsp+arg_8], rbx
0x18000a11d  mov     [rsp+arg_10], rsi
0x18000a122  push    rdi
0x18000a123  sub     rsp, 20h
0x18000a127  mov     rdi, [rcx]
0x18000a12a  mov     rsi, rdx
0x18000a12d  mov     rbx, rcx
0x18000a130  test    rdi, rdi
0x18000a133  jz      short loc_18000A151
0x18000a135  lea     rcx, [rsp+28h+arg_0]; this
0x18000a13a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a13f  mov     rcx, rdi; pti
0x18000a142  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000a147  lea     rcx, [rsp+28h+arg_0]; this
0x18000a14c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a151  mov     [rbx], rsi
0x18000a154  mov     rbx, [rsp+28h+arg_8]
0x18000a159  mov     rsi, [rsp+28h+arg_10]
0x18000a15e  add     rsp, 20h
0x18000a162  pop     rdi
0x18000a163  retn
```
