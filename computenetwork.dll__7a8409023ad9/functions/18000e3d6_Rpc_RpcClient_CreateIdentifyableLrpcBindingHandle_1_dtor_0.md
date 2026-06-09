# _Rpc::RpcClient::CreateIdentifyableLrpcBindingHandle_::_1_::dtor$0

- ea: `0x18000e3d6`
- end: `0x18000e3ff`
- name: `_Rpc::RpcClient::CreateIdentifyableLrpcBindingHandle_::_1_::dtor$0`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000b85c`
- `0x18000e3d6`

## pseudocode

```c
__int64 __fastcall Rpc::RpcClient::CreateIdentifyableLrpcBindingHandle_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(*(_QWORD *)(a2 + 136));
  }
  return result;
}

```

## disassembly

```asm
0x18000e3d6  push    rbp
0x18000e3d8  sub     rsp, 20h
0x18000e3dc  mov     rbp, rdx
0x18000e3df  mov     eax, [rbp+20h]
0x18000e3e2  and     eax, 1
0x18000e3e5  test    eax, eax
0x18000e3e7  jz      short loc_18000E3F9
0x18000e3e9  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000e3ed  mov     rcx, [rbp+88h]
0x18000e3f4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x18000e3f9  add     rsp, 20h
0x18000e3fd  pop     rbp
0x18000e3fe  retn
```
