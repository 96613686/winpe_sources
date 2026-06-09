# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)

- ea: `0x18000f178`
- end: `0x18000f18f`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000f0ac`
- `0x18000f110`
- `0x1800309a0`

## callees

- `0x18000f178`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f184`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f184`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(
        struct _TP_TIMER **a1)
{
  struct _TP_TIMER *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpoolTimer(v1);
}

```

## disassembly

```asm
0x18000f178  sub     rsp, 28h
0x18000f17c  mov     rcx, [rcx]; pti
0x18000f17f  test    rcx, rcx
0x18000f182  jz      short loc_18000F18A
0x18000f184  call    cs:__imp_CloseThreadpoolTimer
0x18000f18a  add     rsp, 28h
0x18000f18e  retn
```
