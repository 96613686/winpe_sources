# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x180008c54`
- end: `0x180008c6c`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(void **)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008b64`
- `0x18000f0f4`
- `0x18001b934`
- `0x18001ba8c`
- `0x18001baf4`
- `0x18001f013`
- `0x18001fab8`
- `0x18001fadc`
- `0x18001faee`
- `0x18001fb12`

## callees

- `0x180008c54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c60`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
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
0x180008c54  sub     rsp, 28h
0x180008c58  mov     rcx, [rcx]; pv
0x180008c5b  test    rcx, rcx
0x180008c5e  jz      short loc_180008C67
0x180008c60  call    cs:__imp_CoTaskMemFree
0x180008c66  nop
0x180008c67  add     rsp, 28h
0x180008c6b  retn
```
