# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x14000a874`
- end: `0x14000a8c0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140006eac`
- `0x140006f5c`
- `0x1400084cc`
- `0x140008584`
- `0x140008670`
- `0x140008b28`

## callees

- `0x140003eb4`
- `0x14000418c`
- `0x1400073fc`
- `0x14000a874`

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
0x14000a874  mov     [rsp+arg_8], rbx
0x14000a879  mov     [rsp+arg_10], rsi
0x14000a87e  push    rdi
0x14000a87f  sub     rsp, 20h
0x14000a883  mov     rdi, [rcx]
0x14000a886  mov     rsi, rdx
0x14000a889  mov     rbx, rcx
0x14000a88c  test    rdi, rdi
0x14000a88f  jz      short loc_14000A8AD
0x14000a891  lea     rcx, [rsp+28h+arg_0]; this
0x14000a896  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000a89b  mov     rcx, rdi; pti
0x14000a89e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000a8a3  lea     rcx, [rsp+28h+arg_0]; this
0x14000a8a8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000a8ad  mov     [rbx], rsi
0x14000a8b0  mov     rbx, [rsp+28h+arg_8]
0x14000a8b5  mov     rsi, [rsp+28h+arg_10]
0x14000a8ba  add     rsp, 20h
0x14000a8be  pop     rdi
0x14000a8bf  retn
```
