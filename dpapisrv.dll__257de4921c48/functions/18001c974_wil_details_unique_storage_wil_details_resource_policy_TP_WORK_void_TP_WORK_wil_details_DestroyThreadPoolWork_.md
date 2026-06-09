# wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)

- ea: `0x18001c974`
- end: `0x18001c992`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(struct _TP_WORK **)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001ac4c`
- `0x18001af90`
- `0x18001b234`

## callees

- `0x18001c974`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001c980`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001c980`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(
        struct _TP_WORK **a1)
{
  struct _TP_WORK *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpoolWork(v1);
}

```

## disassembly

```asm
0x18001c974  sub     rsp, 28h
0x18001c978  mov     rcx, [rcx]; pwk
0x18001c97b  test    rcx, rcx
0x18001c97e  jz      short loc_18001C98C
0x18001c980  call    cs:__imp_CloseThreadpoolWork
0x18001c987  nop     dword ptr [rax+rax+00h]
0x18001c98c  add     rsp, 28h
0x18001c990  retn
```
