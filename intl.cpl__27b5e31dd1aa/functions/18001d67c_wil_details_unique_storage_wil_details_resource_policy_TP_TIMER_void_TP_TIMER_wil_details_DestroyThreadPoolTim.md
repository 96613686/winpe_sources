# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18001d67c`
- end: `0x18001d6c8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018d7c`
- `0x180018df8`
- `0x1800191ec`
- `0x18001929c`
- `0x18001bd54`
- `0x18001beb8`

## callees

- `0x180004328`
- `0x1800045d0`
- `0x18001966c`
- `0x18001d67c`

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
0x18001d67c  mov     [rsp+arg_8], rbx
0x18001d681  mov     [rsp+arg_10], rsi
0x18001d686  push    rdi
0x18001d687  sub     rsp, 20h
0x18001d68b  mov     rdi, [rcx]
0x18001d68e  mov     rsi, rdx
0x18001d691  mov     rbx, rcx
0x18001d694  test    rdi, rdi
0x18001d697  jz      short loc_18001D6B5
0x18001d699  lea     rcx, [rsp+28h+arg_0]; this
0x18001d69e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001d6a3  mov     rcx, rdi; pti
0x18001d6a6  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18001d6ab  lea     rcx, [rsp+28h+arg_0]; this
0x18001d6b0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001d6b5  mov     [rbx], rsi
0x18001d6b8  mov     rbx, [rsp+28h+arg_8]
0x18001d6bd  mov     rsi, [rsp+28h+arg_10]
0x18001d6c2  add     rsp, 20h
0x18001d6c6  pop     rdi
0x18001d6c7  retn
```
