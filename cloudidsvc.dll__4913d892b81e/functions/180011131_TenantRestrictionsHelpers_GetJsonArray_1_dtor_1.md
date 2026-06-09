# _TenantRestrictionsHelpers::GetJsonArray_::_1_::dtor$1

- ea: `0x180011131`
- end: `0x180011157`
- name: `_TenantRestrictionsHelpers::GetJsonArray_::_1_::dtor$1`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000dcdc`
- `0x180011131`

## pseudocode

```c
__int64 __fastcall TenantRestrictionsHelpers::GetJsonArray_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(*(__int64 **)(a2 + 56));
  }
  return result;
}

```

## disassembly

```asm
0x180011131  push    rbp
0x180011133  sub     rsp, 20h
0x180011137  mov     rbp, rdx
0x18001113a  mov     eax, [rbp+20h]
0x18001113d  and     eax, 1
0x180011140  test    eax, eax
0x180011142  jz      short loc_180011151
0x180011144  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x180011148  mov     rcx, [rbp+38h]
0x18001114c  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x180011151  add     rsp, 20h
0x180011155  pop     rbp
0x180011156  retn
```
