# __scrt_dllmain_crt_thread_detach

- ea: `0x18000d180`
- end: `0x18000d195`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d480`

## callees

- `0x1800035e0`

## pseudocode

```c
char __fastcall _scrt_dllmain_crt_thread_detach(__int64 a1)
{
  __int64 v1; // rcx

  _____not_null_V_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_34__Z____function_wistd__YA_NAEBV_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_45__Z__Z(a1);
  _____not_null_V_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_34__Z____function_wistd__YA_NAEBV_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_45__Z__Z(v1);
  return 1;
}

```

## disassembly

```asm
0x18000d180  sub     rsp, 28h
0x18000d184  call    ??$__not_null@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@@__function@wistd@@YA_NAEBV_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@45@@Z@@Z; wistd::__function::__not_null<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_>(`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_ const &)
0x18000d189  call    ??$__not_null@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@@__function@wistd@@YA_NAEBV_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@45@@Z@@Z; wistd::__function::__not_null<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_>(`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_ const &)
0x18000d18e  mov     al, 1
0x18000d190  add     rsp, 28h
0x18000d194  retn
```
