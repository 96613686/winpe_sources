# _Rpc::RpcClient::CreateAnonymousCustomBindingHandle_::_1_::dtor$1

- ea: `0x18000e386`
- end: `0x18000e3ac`
- name: `_Rpc::RpcClient::CreateAnonymousCustomBindingHandle_::_1_::dtor$1`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000b85c`
- `0x18000e386`

## pseudocode

```c
__int64 __fastcall Rpc::RpcClient::CreateAnonymousCustomBindingHandle_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(*(_QWORD *)(a2 + 104));
  }
  return result;
}

```

## disassembly

```asm
0x18000e386  push    rbp
0x18000e388  sub     rsp, 20h
0x18000e38c  mov     rbp, rdx
0x18000e38f  mov     eax, [rbp+30h]
0x18000e392  and     eax, 1
0x18000e395  test    eax, eax
0x18000e397  jz      short loc_18000E3A6
0x18000e399  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18000e39d  mov     rcx, [rbp+68h]
0x18000e3a1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x18000e3a6  add     rsp, 20h
0x18000e3aa  pop     rbp
0x18000e3ab  retn
```
