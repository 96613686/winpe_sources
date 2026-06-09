# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000aa8c`
- end: `0x18000aad8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007a6c`
- `0x180007ae8`
- `0x180007ef8`
- `0x180007fa8`
- `0x180009168`
- `0x1800092c8`

## callees

- `0x1800041bc`
- `0x1800044f0`
- `0x180008440`
- `0x18000aa8c`

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
0x18000aa8c  mov     [rsp+arg_8], rbx
0x18000aa91  mov     [rsp+arg_10], rsi
0x18000aa96  push    rdi
0x18000aa97  sub     rsp, 20h
0x18000aa9b  mov     rdi, [rcx]
0x18000aa9e  mov     rsi, rdx
0x18000aaa1  mov     rbx, rcx
0x18000aaa4  test    rdi, rdi
0x18000aaa7  jz      short loc_18000AAC5
0x18000aaa9  lea     rcx, [rsp+28h+arg_0]; this
0x18000aaae  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000aab3  mov     rcx, rdi; pti
0x18000aab6  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000aabb  lea     rcx, [rsp+28h+arg_0]; this
0x18000aac0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000aac5  mov     [rbx], rsi
0x18000aac8  mov     rbx, [rsp+28h+arg_8]
0x18000aacd  mov     rsi, [rsp+28h+arg_10]
0x18000aad2  add     rsp, 20h
0x18000aad6  pop     rdi
0x18000aad7  retn
```
