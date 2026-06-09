# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000dcb0`
- end: `0x18000dcfd`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a800`
- `0x18000a884`
- `0x18000acb8`
- `0x18000ad68`
- `0x18000c378`
- `0x180028e60`

## callees

- `0x180004cc8`
- `0x1800050ec`
- `0x18000b7bc`
- `0x18000dcb0`

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
0x18000dcb0  mov     [rsp+arg_8], rbx
0x18000dcb5  mov     [rsp+arg_10], rsi
0x18000dcba  push    rdi
0x18000dcbb  sub     rsp, 20h
0x18000dcbf  mov     rdi, [rcx]
0x18000dcc2  mov     rsi, rdx
0x18000dcc5  mov     rbx, rcx
0x18000dcc8  test    rdi, rdi
0x18000dccb  jz      short loc_18000DCE9
0x18000dccd  lea     rcx, [rsp+28h+arg_0]; this
0x18000dcd2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000dcd7  mov     rcx, rdi; pti
0x18000dcda  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000dcdf  lea     rcx, [rsp+28h+arg_0]; this
0x18000dce4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000dce9  mov     [rbx], rsi
0x18000dcec  mov     rbx, [rsp+28h+arg_8]
0x18000dcf1  mov     rsi, [rsp+28h+arg_10]
0x18000dcf6  add     rsp, 20h
0x18000dcfa  pop     rdi
0x18000dcfb  retn
```
