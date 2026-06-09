# wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)

- ea: `0x1800132e4`
- end: `0x180013302`
- name: `??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800132d8`
- `0x180013bec`
- `0x180013e00`
- `0x1800175e4`

## callees

- `0x1800132e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800132f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800132f0`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(
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
0x1800132e4  sub     rsp, 28h
0x1800132e8  mov     rcx, [rcx]; pv
0x1800132eb  test    rcx, rcx
0x1800132ee  jz      short loc_1800132FC
0x1800132f0  call    cs:__imp_CoTaskMemFree
0x1800132f7  nop     dword ptr [rax+rax+00h]
0x1800132fc  add     rsp, 28h
0x180013300  retn
```
