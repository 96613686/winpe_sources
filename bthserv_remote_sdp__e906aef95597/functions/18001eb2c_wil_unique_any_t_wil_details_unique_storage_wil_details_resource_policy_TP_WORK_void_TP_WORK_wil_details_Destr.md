# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(void)

- ea: `0x18001eb2c`
- end: `0x18001eb64`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180035290`

## callees

- `0x18001eb2c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001eb42`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001eb42`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001eb51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001eb51`

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
0x18001eb2c  push    rbx
0x18001eb2e  sub     rsp, 20h
0x18001eb32  mov     rbx, [rcx]
0x18001eb35  test    rbx, rbx
0x18001eb38  jz      short loc_18001EB5D
0x18001eb3a  mov     edx, 1; fCancelPendingCallbacks
0x18001eb3f  mov     rcx, rbx; pwk
0x18001eb42  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001eb49  nop     dword ptr [rax+rax+00h]
0x18001eb4e  mov     rcx, rbx; pwk
0x18001eb51  call    cs:__imp_CloseThreadpoolWork
0x18001eb58  nop     dword ptr [rax+rax+00h]
0x18001eb5d  add     rsp, 20h
0x18001eb61  pop     rbx
0x18001eb62  retn
```
