# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180017c50`
- end: `0x180017c9c`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017bac`
- `0x1800193ac`
- `0x1800199f4`
- `0x1800259fc`
- `0x180025a78`

## callees

- `0x180017c50`
- `0x180026330`
- `0x180026618`
- `0x180026b80`

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
0x180017c50  mov     [rsp+arg_8], rbx
0x180017c55  mov     [rsp+arg_10], rsi
0x180017c5a  push    rdi
0x180017c5b  sub     rsp, 20h
0x180017c5f  mov     rdi, [rcx]
0x180017c62  mov     rsi, rdx
0x180017c65  mov     rbx, rcx
0x180017c68  test    rdi, rdi
0x180017c6b  jz      short loc_180017C89
0x180017c6d  lea     rcx, [rsp+28h+arg_0]; this
0x180017c72  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017c77  mov     rcx, rdi; pti
0x180017c7a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180017c7f  lea     rcx, [rsp+28h+arg_0]; this
0x180017c84  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180017c89  mov     [rbx], rsi
0x180017c8c  mov     rbx, [rsp+28h+arg_8]
0x180017c91  mov     rsi, [rsp+28h+arg_10]
0x180017c96  add     rsp, 20h
0x180017c9a  pop     rdi
0x180017c9b  retn
```
