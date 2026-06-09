# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)

- ea: `0x18000b85c`
- end: `0x18000b87d`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e2d9`
- `0x18000e386`
- `0x18000e3c4`
- `0x18000e3d6`

## callees

- `0x18000b85c`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000b872`
- `RPCRT4!RpcBindingFree` at `0x18000b872`

## pseudocode

```c
int __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(
        RPC_BINDING_HANDLE *a1)
{
  RPC_BINDING_HANDLE v1; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 )
  {
    Binding = *a1;
    LODWORD(v1) = RpcBindingFree(&Binding);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x18000b85c  sub     rsp, 28h
0x18000b860  mov     rax, [rcx]
0x18000b863  test    rax, rax
0x18000b866  jz      short loc_18000B878
0x18000b868  lea     rcx, [rsp+28h+Binding]; Binding
0x18000b86d  mov     [rsp+28h+Binding], rax
0x18000b872  call    cs:__imp_RpcBindingFree
0x18000b878  add     rsp, 28h
0x18000b87c  retn
```
