# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x1800238d8`
- end: `0x1800238f6`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021920`
- `0x180023b48`
- `0x18002c128`
- `0x18002c650`
- `0x18002ca94`
- `0x18002d168`
- `0x18002ddfc`
- `0x18002edb4`

## callees

- `0x1800238d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800238e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800238e4`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x1800238d8  sub     rsp, 28h
0x1800238dc  mov     rcx, [rcx]; pv
0x1800238df  test    rcx, rcx
0x1800238e2  jz      short loc_1800238F0
0x1800238e4  call    cs:__imp_CoTaskMemFree
0x1800238eb  nop     dword ptr [rax+rax+00h]
0x1800238f0  add     rsp, 28h
0x1800238f4  retn
```
