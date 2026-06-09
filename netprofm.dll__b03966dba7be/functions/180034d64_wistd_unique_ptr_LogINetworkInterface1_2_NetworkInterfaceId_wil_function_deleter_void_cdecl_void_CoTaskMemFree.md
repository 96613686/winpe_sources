# wistd::unique_ptr__LogINetworkInterface1_::_2_::NetworkInterfaceId_wil::function_deleter_void_(__cdecl_)(void__)_&CoTaskMemFree___::_unique_ptr__LogINetworkInterface1_::_2_::NetworkInterfaceId_wil::function_deleter_void_(__cdecl_)(void__)_&CoTaskMemFree___

- ea: `0x180034d64`
- end: `0x180034d85`
- name: `wistd::unique_ptr__LogINetworkInterface1_::_2_::NetworkInterfaceId_wil::function_deleter_void_(__cdecl_)(void__)_&CoTaskMemFree___::_unique_ptr__LogINetworkInterface1_::_2_::NetworkInterfaceId_wil::function_deleter_void_(__cdecl_)(void__)_&CoTaskMemFree___`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800416d0`

## callees

- `0x180034d64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d7a`

## pseudocode

```c
void __fastcall wistd::unique_ptr__LogINetworkInterface1_::_2_::NetworkInterfaceId_wil::function_deleter_void____cdecl___void_____CoTaskMemFree___::_unique_ptr__LogINetworkInterface1_::_2_::NetworkInterfaceId_wil::function_deleter_void____cdecl___void_____CoTaskMemFree___(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x180034d64  sub     rsp, 28h
0x180034d68  mov     rax, [rcx]
0x180034d6b  mov     qword ptr [rcx], 0
0x180034d72  test    rax, rax
0x180034d75  jz      short loc_180034D80
0x180034d77  mov     rcx, rax; pv
0x180034d7a  call    cs:__imp_CoTaskMemFree
0x180034d80  add     rsp, 28h
0x180034d84  retn
```
