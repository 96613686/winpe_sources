# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x14001bd6c`
- end: `0x14001bdb8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140017380`
- `0x140019638`
- `0x140019a0c`

## callees

- `0x140016e8c`
- `0x140017578`
- `0x140017b18`
- `0x14001bd6c`

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
0x14001bd6c  mov     [rsp+arg_8], rbx
0x14001bd71  mov     [rsp+arg_10], rsi
0x14001bd76  push    rdi
0x14001bd77  sub     rsp, 20h
0x14001bd7b  mov     rdi, [rcx]
0x14001bd7e  mov     rsi, rdx
0x14001bd81  mov     rbx, rcx
0x14001bd84  test    rdi, rdi
0x14001bd87  jz      short loc_14001BDA5
0x14001bd89  lea     rcx, [rsp+28h+arg_0]; this
0x14001bd8e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001bd93  mov     rcx, rdi; pti
0x14001bd96  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14001bd9b  lea     rcx, [rsp+28h+arg_0]; this
0x14001bda0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001bda5  mov     [rbx], rsi
0x14001bda8  mov     rbx, [rsp+28h+arg_8]
0x14001bdad  mov     rsi, [rsp+28h+arg_10]
0x14001bdb2  add     rsp, 20h
0x14001bdb6  pop     rdi
0x14001bdb7  retn
```
