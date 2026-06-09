# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180022ca0`
- end: `0x180022cb7`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020d20`
- `0x180022ee0`
- `0x18002b1d8`
- `0x18002b6dc`
- `0x18002bb04`
- `0x18002c1c4`
- `0x18002cdd4`
- `0x18002dd44`

## callees

- `0x180022ca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022cac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022cac`

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
0x180022ca0  sub     rsp, 28h
0x180022ca4  mov     rcx, [rcx]; pv
0x180022ca7  test    rcx, rcx
0x180022caa  jz      short loc_180022CB2
0x180022cac  call    cs:__imp_CoTaskMemFree
0x180022cb2  add     rsp, 28h
0x180022cb6  retn
```
