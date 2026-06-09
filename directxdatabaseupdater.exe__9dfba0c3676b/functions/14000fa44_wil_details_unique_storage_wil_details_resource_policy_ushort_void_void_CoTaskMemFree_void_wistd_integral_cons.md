# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x14000fa44`
- end: `0x14000fa5b`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000f9f4`
- `0x1400100e0`
- `0x140010ce8`
- `0x140011674`

## callees

- `0x14000fa44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000fa50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000fa50`

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
0x14000fa44  sub     rsp, 28h
0x14000fa48  mov     rcx, [rcx]; pv
0x14000fa4b  test    rcx, rcx
0x14000fa4e  jz      short loc_14000FA56
0x14000fa50  call    cs:__imp_CoTaskMemFree
0x14000fa56  add     rsp, 28h
0x14000fa5a  retn
```
