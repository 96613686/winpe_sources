# _EapLm::Peer::ThirdPartyEapMethodConfig::InvokeIdentityUi_::_1_::catch$3

- ea: `0x180031f35`
- end: `0x180031f5a`
- name: `_EapLm::Peer::ThirdPartyEapMethodConfig::InvokeIdentityUi_::_1_::catch$3`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002f4a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031f4a`

## pseudocode

```c
void __fastcall __noreturn EapLm::Peer::ThirdPartyEapMethodConfig::InvokeIdentityUi_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(a2 + 56) + 64LL));
  throw;
}

```

## disassembly

```asm
0x180031f35  mov     [rsp+arg_8], rdx
0x180031f3a  push    rbp
0x180031f3b  sub     rsp, 30h
0x180031f3f  mov     rbp, rdx
0x180031f42  mov     rcx, [rbp+38h]
0x180031f46  mov     rcx, [rcx+40h]; pv
0x180031f4a  call    cs:__imp_CoTaskMemFree
0x180031f50  xor     edx, edx; pThrowInfo
0x180031f52  xor     ecx, ecx; pExceptionObject
0x180031f54  call    _CxxThrowException_0
```
