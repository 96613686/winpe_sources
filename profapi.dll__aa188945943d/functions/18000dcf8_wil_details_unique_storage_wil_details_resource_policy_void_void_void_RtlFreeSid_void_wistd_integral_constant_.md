# wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000dcf8`
- end: `0x18000dd0f`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `PVOID __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180001d3c`
- `0x18001713e`

## callees

- `0x18000dcf8`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18000dd04`
- `ntdll!RtlFreeSid` at `0x18000dd04`

## pseudocode

```c
PVOID __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx
  PVOID result; // rax

  v1 = *a1;
  if ( v1 )
    return RtlFreeSid(v1);
  return result;
}

```

## disassembly

```asm
0x18000dcf8  sub     rsp, 28h
0x18000dcfc  mov     rcx, [rcx]; Sid
0x18000dcff  test    rcx, rcx
0x18000dd02  jz      short loc_18000DD0A
0x18000dd04  call    cs:__imp_RtlFreeSid
0x18000dd0a  add     rsp, 28h
0x18000dd0e  retn
```
