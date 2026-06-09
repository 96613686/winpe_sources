# wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(void)

- ea: `0x18002efdc`
- end: `0x18002eff3`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002efc4`
- `0x18002f088`
- `0x18002f098`

## callees

- `0x18002efdc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002efe8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002efe8`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(
        struct _TP_POOL **a1)
{
  struct _TP_POOL *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpool(v1);
}

```

## disassembly

```asm
0x18002efdc  sub     rsp, 28h
0x18002efe0  mov     rcx, [rcx]; ptpp
0x18002efe3  test    rcx, rcx
0x18002efe6  jz      short loc_18002EFEE
0x18002efe8  call    cs:__imp_CloseThreadpool
0x18002efee  add     rsp, 28h
0x18002eff2  retn
```
