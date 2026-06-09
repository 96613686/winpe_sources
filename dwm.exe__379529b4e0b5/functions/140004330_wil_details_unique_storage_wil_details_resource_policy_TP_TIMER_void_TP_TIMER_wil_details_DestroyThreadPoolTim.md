# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x140004330`
- end: `0x14000437c`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140003f50`
- `0x140004164`
- `0x1400041e4`
- `0x140006b6c`
- `0x140006be8`
- `0x14000d124`

## callees

- `0x140004330`
- `0x1400074b0`
- `0x14000782c`
- `0x140007f50`

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
0x140004330  mov     [rsp+arg_8], rbx
0x140004335  mov     [rsp+arg_10], rsi
0x14000433a  push    rdi
0x14000433b  sub     rsp, 20h
0x14000433f  mov     rdi, [rcx]
0x140004342  mov     rsi, rdx
0x140004345  mov     rbx, rcx
0x140004348  test    rdi, rdi
0x14000434b  jz      short loc_140004369
0x14000434d  lea     rcx, [rsp+28h+arg_0]; this
0x140004352  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140004357  mov     rcx, rdi; pti
0x14000435a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000435f  lea     rcx, [rsp+28h+arg_0]; this
0x140004364  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140004369  mov     [rbx], rsi
0x14000436c  mov     rbx, [rsp+28h+arg_8]
0x140004371  mov     rsi, [rsp+28h+arg_10]
0x140004376  add     rsp, 20h
0x14000437a  pop     rdi
0x14000437b  retn
```
