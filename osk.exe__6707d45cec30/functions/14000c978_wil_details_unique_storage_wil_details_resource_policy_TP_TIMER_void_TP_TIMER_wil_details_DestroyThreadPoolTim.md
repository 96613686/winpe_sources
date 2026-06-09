# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x14000c978`
- end: `0x14000c9c4`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000380c`
- `0x140003888`
- `0x1400051d4`
- `0x140005284`
- `0x140008930`
- `0x1400129d0`

## callees

- `0x140004b80`
- `0x140005460`
- `0x140005e90`
- `0x14000c978`

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
0x14000c978  mov     [rsp+arg_8], rbx
0x14000c97d  mov     [rsp+arg_10], rsi
0x14000c982  push    rdi
0x14000c983  sub     rsp, 20h
0x14000c987  mov     rdi, [rcx]
0x14000c98a  mov     rsi, rdx
0x14000c98d  mov     rbx, rcx
0x14000c990  test    rdi, rdi
0x14000c993  jz      short loc_14000C9B1
0x14000c995  lea     rcx, [rsp+28h+arg_0]; this
0x14000c99a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000c99f  mov     rcx, rdi; pti
0x14000c9a2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000c9a7  lea     rcx, [rsp+28h+arg_0]; this
0x14000c9ac  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000c9b1  mov     [rbx], rsi
0x14000c9b4  mov     rbx, [rsp+28h+arg_8]
0x14000c9b9  mov     rsi, [rsp+28h+arg_10]
0x14000c9be  add     rsp, 20h
0x14000c9c2  pop     rdi
0x14000c9c3  retn
```
