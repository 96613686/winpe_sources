# std::_Ref_count_resource<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>> *,std::default_delete<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>>::_Get_deleter(type_info const &)

- ea: `0x18004e7f0`
- end: `0x18004e81f`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAV?$IProfileDataItemTypeService@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@wil@@U?$default_delete@V?$IProfileDataItemTypeService@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@wil@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e804`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e804`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>> *,std::default_delete<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_180075688);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18004e7f0  push    rbx
0x18004e7f2  sub     rsp, 20h
0x18004e7f6  mov     rbx, rcx
0x18004e7f9  lea     rcx, [rdx+8]
0x18004e7fd  lea     rdx, qword_180075688
0x18004e804  call    cs:__imp___std_type_info_compare
0x18004e80a  xor     ecx, ecx
0x18004e80c  lea     rdx, [rbx+10h]
0x18004e810  test    eax, eax
0x18004e812  cmovnz  rdx, rcx
0x18004e816  mov     rax, rdx
0x18004e819  add     rsp, 20h
0x18004e81d  pop     rbx
0x18004e81e  retn
```
