# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x18000ab5c`
- end: `0x18000ab73`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ab44`
- `0x18000acf4`
- `0x18000b3e8`
- `0x18000c390`
- `0x180010100`
- `0x180012790`
- `0x180015858`
- `0x180015a2c`
- `0x180015e98`

## callees

- `0x18000ab5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab68`

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
0x18000ab5c  sub     rsp, 28h
0x18000ab60  mov     rcx, [rcx]; pv
0x18000ab63  test    rcx, rcx
0x18000ab66  jz      short loc_18000AB6E
0x18000ab68  call    cs:__imp_CoTaskMemFree
0x18000ab6e  add     rsp, 28h
0x18000ab72  retn
```
