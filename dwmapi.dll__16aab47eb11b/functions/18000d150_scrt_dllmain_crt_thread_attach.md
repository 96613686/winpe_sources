# __scrt_dllmain_crt_thread_attach

- ea: `0x18000d150`
- end: `0x18000d178`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d480`

## callees

- `0x1800035e0`
- `0x18000d150`

## pseudocode

```c
char __fastcall _scrt_dllmain_crt_thread_attach(__int64 a1)
{
  __int64 v1; // rcx
  __int64 v3; // rcx

  if ( !(unsigned __int8)_____not_null_V_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_34__Z____function_wistd__YA_NAEBV_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_45__Z__Z(a1) )
    return 0;
  if ( !(unsigned __int8)_____not_null_V_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_34__Z____function_wistd__YA_NAEBV_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_45__Z__Z(v1) )
  {
    _____not_null_V_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_34__Z____function_wistd__YA_NAEBV_lambda_1___3__RecordWnfUsageIndex_details_abi_wil__YAXPEBU__WIL__WNF_STATE_NAME___KAEBVRawUsageIndex_45__Z__Z(v3);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d150  sub     rsp, 28h
0x18000d154  call    ??$__not_null@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@@__function@wistd@@YA_NAEBV_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@45@@Z@@Z; wistd::__function::__not_null<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_>(`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_ const &)
0x18000d159  test    al, al
0x18000d15b  jnz     short loc_18000D161
0x18000d15d  xor     al, al
0x18000d15f  jmp     short loc_18000D173
0x18000d161  call    ??$__not_null@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@@__function@wistd@@YA_NAEBV_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@45@@Z@@Z; wistd::__function::__not_null<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_>(`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_ const &)
0x18000d166  test    al, al
0x18000d168  jnz     short loc_18000D171
0x18000d16a  call    ??$__not_null@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@@__function@wistd@@YA_NAEBV_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@45@@Z@@Z; wistd::__function::__not_null<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_>(`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_ const &)
0x18000d16f  jmp     short loc_18000D15D
0x18000d171  mov     al, 1
0x18000d173  add     rsp, 28h
0x18000d177  retn
```
