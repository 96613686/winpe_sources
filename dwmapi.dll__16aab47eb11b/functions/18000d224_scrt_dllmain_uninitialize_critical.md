# __scrt_dllmain_uninitialize_critical

- ea: `0x18000d224`
- end: `0x18000d238`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d5d8`

## callees

- `0x1800035e0`

## pseudocode

```c
__int64 _scrt_dllmain_uninitialize_critical()
{
  __int64 v0; // rcx

  _____not_null_V_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_34__Z____function_wistd__YA_NAEBV_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_45__Z__Z(0);
  return _____not_null_V_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_34__Z____function_wistd__YA_NAEBV_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_45__Z__Z(v0);
}

```

## disassembly

```asm
0x18000d224  sub     rsp, 28h
0x18000d228  xor     ecx, ecx
0x18000d22a  call    ??$__not_null@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@@__function@wistd@@YA_NAEBV_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@45@@Z@@Z; wistd::__function::__not_null<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_>(`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_ const &)
0x18000d22f  add     rsp, 28h
0x18000d233  jmp     ??$__not_null@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@@__function@wistd@@YA_NAEBV_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@45@@Z@@Z; wistd::__function::__not_null<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_>(`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_ const &)
```
