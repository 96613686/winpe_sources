# _PackageSecurity::CreateCatalog_::_1_::dtor$7

- ea: `0x18001880b`
- end: `0x180018817`
- name: `_PackageSecurity::CreateCatalog_::_1_::dtor$7`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a54c`

## pseudocode

```c
__int64 __fastcall PackageSecurity::CreateCatalog_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return wil::unique_struct<_PROCESS_INFORMATION,void (*)(_PROCESS_INFORMATION *),&void wil::details::CloseProcessInformation(_PROCESS_INFORMATION *),std::nullptr_t,0>::~unique_struct<_PROCESS_INFORMATION,void (*)(_PROCESS_INFORMATION *),&void wil::details::CloseProcessInformation(_PROCESS_INFORMATION *),std::nullptr_t,0>(a2 + 104);
}

```

## disassembly

```asm
0x18001880b  lea     rcx, [rdx+68h]
0x180018812  jmp     ??1?$unique_struct@U_PROCESS_INFORMATION@@P6AXPEAU1@@Z$1?CloseProcessInformation@details@wil@@YAX0@Z$$T$0A@@wil@@QEAA@XZ; wil::unique_struct<_PROCESS_INFORMATION,void (*)(_PROCESS_INFORMATION *),&wil::details::CloseProcessInformation(_PROCESS_INFORMATION *),std::nullptr_t,0>::~unique_struct<_PROCESS_INFORMATION,void (*)(_PROCESS_INFORMATION *),&wil::details::CloseProcessInformation(_PROCESS_INFORMATION *),std::nullptr_t,0>(void)
```
