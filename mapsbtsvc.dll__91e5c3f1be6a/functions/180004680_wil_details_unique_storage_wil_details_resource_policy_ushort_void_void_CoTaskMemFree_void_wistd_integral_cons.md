# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x180004680`
- end: `0x180004697`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000463c`
- `0x180004940`
- `0x18000bb70`
- `0x18000c4dc`
- `0x18000cba4`
- `0x18000cd7c`
- `0x18000dd10`
- `0x1800119b0`
- `0x1800119e0`
- `0x18001240c`
- `0x180012904`

## callees

- `0x180004680`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000468c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000468c`

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
0x180004680  sub     rsp, 28h
0x180004684  mov     rcx, [rcx]; pv
0x180004687  test    rcx, rcx
0x18000468a  jz      short loc_180004692
0x18000468c  call    cs:__imp_CoTaskMemFree
0x180004692  add     rsp, 28h
0x180004696  retn
```
