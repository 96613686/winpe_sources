# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800087e4`
- end: `0x180008832`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `78`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008730`
- `0x18000886c`
- `0x180008980`
- `0x18000c84c`
- `0x18000c8c8`
- `0x18000c944`

## callees

- `0x1800087e4`
- `0x18000c9c0`
- `0x18000ca24`
- `0x18000ea30`

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
0x1800087e4  mov     [rsp+arg_8], rbx
0x1800087e9  mov     [rsp+arg_10], rsi
0x1800087ee  push    rdi
0x1800087ef  sub     rsp, 20h
0x1800087f3  mov     rdi, [rcx]
0x1800087f6  mov     rsi, rdx
0x1800087f9  mov     rbx, rcx
0x1800087fc  test    rdi, rdi
0x1800087ff  jnz     short loc_180008814
0x180008801  mov     [rbx], rsi
0x180008804  mov     rbx, [rsp+28h+arg_8]
0x180008809  mov     rsi, [rsp+28h+arg_10]
0x18000880e  add     rsp, 20h
0x180008812  pop     rdi
0x180008813  retn
0x180008814  lea     rcx, [rsp+28h+arg_0]; this
0x180008819  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000881e  mov     rcx, rdi; pti
0x180008821  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180008826  lea     rcx, [rsp+28h+arg_0]; this
0x18000882b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008830  jmp     short loc_180008801
```
