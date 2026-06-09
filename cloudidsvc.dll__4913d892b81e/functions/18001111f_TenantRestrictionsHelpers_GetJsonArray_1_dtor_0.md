# _TenantRestrictionsHelpers::GetJsonArray_::_1_::dtor$0

- ea: `0x18001111f`
- end: `0x18001112b`
- name: `_TenantRestrictionsHelpers::GetJsonArray_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000dcdc`

## pseudocode

```c
__int64 __fastcall TenantRestrictionsHelpers::GetJsonArray_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>((__int64 *)(a2 + 40));
}

```

## disassembly

```asm
0x18001111f  lea     rcx, [rdx+28h]
0x180011126  jmp     ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
```
