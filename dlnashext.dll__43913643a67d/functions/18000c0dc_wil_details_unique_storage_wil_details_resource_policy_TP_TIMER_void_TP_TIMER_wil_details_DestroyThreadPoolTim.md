# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000c0dc`
- end: `0x18000c129`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b670`
- `0x18000bd6c`
- `0x18000bf84`
- `0x1800309a0`

## callees

- `0x18000a760`
- `0x18000a784`
- `0x18000c0dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c106`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c106`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CloseThreadpoolTimer(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000c0dc  mov     [rsp+arg_8], rbx
0x18000c0e1  mov     [rsp+arg_10], rsi
0x18000c0e6  push    rdi
0x18000c0e7  sub     rsp, 20h
0x18000c0eb  mov     rdi, [rcx]
0x18000c0ee  mov     rsi, rdx
0x18000c0f1  mov     rbx, rcx
0x18000c0f4  test    rdi, rdi
0x18000c0f7  jz      short loc_18000C116
0x18000c0f9  lea     rcx, [rsp+28h+arg_0]; this
0x18000c0fe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000c103  mov     rcx, rdi; pti
0x18000c106  call    cs:__imp_CloseThreadpoolTimer
0x18000c10c  lea     rcx, [rsp+28h+arg_0]; this
0x18000c111  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000c116  mov     [rbx], rsi
0x18000c119  mov     rbx, [rsp+28h+arg_8]
0x18000c11e  mov     rsi, [rsp+28h+arg_10]
0x18000c123  add     rsp, 20h
0x18000c127  pop     rdi
0x18000c128  retn
```
