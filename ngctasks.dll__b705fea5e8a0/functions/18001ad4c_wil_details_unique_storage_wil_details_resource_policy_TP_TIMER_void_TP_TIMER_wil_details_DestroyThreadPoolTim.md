# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18001ad4c`
- end: `0x18001ad98`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016f8c`
- `0x180017008`
- `0x180017968`
- `0x180017a18`
- `0x1800191b0`
- `0x1800192e0`

## callees

- `0x180008584`
- `0x18000910c`
- `0x180017ea0`
- `0x18001ad4c`

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
0x18001ad4c  mov     [rsp+arg_8], rbx
0x18001ad51  mov     [rsp+arg_10], rsi
0x18001ad56  push    rdi
0x18001ad57  sub     rsp, 20h
0x18001ad5b  mov     rdi, [rcx]
0x18001ad5e  mov     rsi, rdx
0x18001ad61  mov     rbx, rcx
0x18001ad64  test    rdi, rdi
0x18001ad67  jz      short loc_18001AD85
0x18001ad69  lea     rcx, [rsp+28h+arg_0]; this
0x18001ad6e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ad73  mov     rcx, rdi; pti
0x18001ad76  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18001ad7b  lea     rcx, [rsp+28h+arg_0]; this
0x18001ad80  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ad85  mov     [rbx], rsi
0x18001ad88  mov     rbx, [rsp+28h+arg_8]
0x18001ad8d  mov     rsi, [rsp+28h+arg_10]
0x18001ad92  add     rsp, 20h
0x18001ad96  pop     rdi
0x18001ad97  retn
```
