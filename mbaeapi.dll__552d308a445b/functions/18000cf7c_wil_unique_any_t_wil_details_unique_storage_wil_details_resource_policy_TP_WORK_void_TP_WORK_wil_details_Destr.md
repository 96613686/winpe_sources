# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(void)

- ea: `0x18000cf7c`
- end: `0x18000cfa7`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(PTP_WORK *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180058e5d`
- `0x180058ecd`

## callees

- `0x18000cf7c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000cf92`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000cf92`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000cf9b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000cf9b`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(
        PTP_WORK *a1)
{
  struct _TP_WORK *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    WaitForThreadpoolWorkCallbacks(*a1, 1);
    CloseThreadpoolWork(v1);
  }
}

```

## disassembly

```asm
0x18000cf7c  push    rbx
0x18000cf7e  sub     rsp, 20h
0x18000cf82  mov     rbx, [rcx]
0x18000cf85  test    rbx, rbx
0x18000cf88  jz      short loc_18000CFA1
0x18000cf8a  mov     edx, 1; fCancelPendingCallbacks
0x18000cf8f  mov     rcx, rbx; pwk
0x18000cf92  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000cf98  mov     rcx, rbx; pwk
0x18000cf9b  call    cs:__imp_CloseThreadpoolWork
0x18000cfa1  add     rsp, 20h
0x18000cfa5  pop     rbx
0x18000cfa6  retn
```
