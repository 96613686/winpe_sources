# _EapLm::Peer::ThirdPartyEapMethodRuntime::GetIdentity_::_1_::catch$3

- ea: `0x180032c4f`
- end: `0x180032c70`
- name: `_EapLm::Peer::ThirdPartyEapMethodRuntime::GetIdentity_::_1_::catch$3`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002f4a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c60`

## pseudocode

```c
void __fastcall __noreturn EapLm::Peer::ThirdPartyEapMethodRuntime::GetIdentity_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CoTaskMemFree(*(LPVOID *)(a2 + 120));
  throw;
}

```

## disassembly

```asm
0x180032c4f  mov     [rsp+arg_8], rdx
0x180032c54  push    rbp
0x180032c55  sub     rsp, 70h
0x180032c59  mov     rbp, rdx
0x180032c5c  mov     rcx, [rbp+78h]; pv
0x180032c60  call    cs:__imp_CoTaskMemFree
0x180032c66  xor     edx, edx; pThrowInfo
0x180032c68  xor     ecx, ecx; pExceptionObject
0x180032c6a  call    _CxxThrowException_0
```
