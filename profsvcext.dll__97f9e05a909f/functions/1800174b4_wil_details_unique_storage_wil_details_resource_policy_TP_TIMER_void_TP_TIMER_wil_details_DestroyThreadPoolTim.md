# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800174b4`
- end: `0x180017500`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800115c4`
- `0x180011674`
- `0x1800141f0`
- `0x1800142a8`
- `0x180014394`
- `0x1800147e8`

## callees

- `0x18000c534`
- `0x18000c7f4`
- `0x180013164`
- `0x1800174b4`

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
0x1800174b4  mov     [rsp+arg_8], rbx
0x1800174b9  mov     [rsp+arg_10], rsi
0x1800174be  push    rdi
0x1800174bf  sub     rsp, 20h
0x1800174c3  mov     rdi, [rcx]
0x1800174c6  mov     rsi, rdx
0x1800174c9  mov     rbx, rcx
0x1800174cc  test    rdi, rdi
0x1800174cf  jz      short loc_1800174ED
0x1800174d1  lea     rcx, [rsp+28h+arg_0]; this
0x1800174d6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800174db  mov     rcx, rdi; pti
0x1800174de  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800174e3  lea     rcx, [rsp+28h+arg_0]; this
0x1800174e8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800174ed  mov     [rbx], rsi
0x1800174f0  mov     rbx, [rsp+28h+arg_8]
0x1800174f5  mov     rsi, [rsp+28h+arg_10]
0x1800174fa  add     rsp, 20h
0x1800174fe  pop     rdi
0x1800174ff  retn
```
