# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x140005044`
- end: `0x14000505b`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x140005480`
- `0x14000b8cc`
- `0x14000bd74`
- `0x14000d390`

## callees

- `0x140005044`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140005050`
- `ole32!CoTaskMemFree` at `0x140005050`

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
0x140005044  sub     rsp, 28h
0x140005048  mov     rcx, [rcx]; pv
0x14000504b  test    rcx, rcx
0x14000504e  jz      short loc_140005056
0x140005050  call    cs:__imp_CoTaskMemFree
0x140005056  add     rsp, 28h
0x14000505a  retn
```
