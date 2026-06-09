# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000c444`
- end: `0x18000c45b`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `63`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c250`
- `0x180016a54`
- `0x180018c5c`
- `0x180018d88`
- `0x180018fc4`
- `0x180019d70`
- `0x18001b970`
- `0x18001bcec`
- `0x18001beec`
- `0x18001c15c`
- `0x18001c498`
- `0x18001c550`
- `0x180023ebc`
- `0x1800241c8`
- `0x180024984`
- `0x1800259ec`
- `0x18002f67c`
- `0x18003071c`
- `0x180031c60`
- `0x180031f1c`
- `0x1800324e0`
- `0x180032d4c`
- `0x18003a374`
- `0x18003b184`
- `0x18003cf98`
- `0x180042f2c`
- `0x18004f468`
- `0x180050ffc`
- `0x180066610`
- `0x180075bc4`
- `0x180079e20`
- `0x18007dd08`
- `0x18007dd6c`
- `0x18007ddac`
- `0x18007de10`
- `0x18007e140`
- `0x18007e4f0`
- `0x18007edb0`
- `0x18007f1b0`
- `0x18007f2a0`
- `0x180080aec`
- `0x180080cbc`
- `0x180081504`
- `0x1800815a8`
- `0x180083a7f`
- `0x180083a91`
- `0x180084004`
- `0x18008404c`
- `0x180084094`
- `0x1800847bd`

## callees

- `0x18000c444`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c450`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c450`

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
0x18000c444  sub     rsp, 28h
0x18000c448  mov     rcx, [rcx]; pv
0x18000c44b  test    rcx, rcx
0x18000c44e  jz      short loc_18000C456
0x18000c450  call    cs:__imp_CoTaskMemFree
0x18000c456  add     rsp, 28h
0x18000c45a  retn
```
