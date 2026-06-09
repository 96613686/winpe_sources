# std::_Ref_count_resource<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::RecoveryItemPdr> *,std::default_delete<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::RecoveryItemPdr>>>::_Get_deleter(type_info const &)

- ea: `0x18004e730`
- end: `0x18004e75f`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAV?$IProfileDataItemTypeService@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@U?$default_delete@V?$IProfileDataItemTypeService@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e744`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e744`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::RecoveryItemPdr> *,std::default_delete<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::RecoveryItemPdr>>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_1800754C8);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18004e730  push    rbx
0x18004e732  sub     rsp, 20h
0x18004e736  mov     rbx, rcx
0x18004e739  lea     rcx, [rdx+8]
0x18004e73d  lea     rdx, qword_1800754C8
0x18004e744  call    cs:__imp___std_type_info_compare
0x18004e74a  xor     ecx, ecx
0x18004e74c  lea     rdx, [rbx+10h]
0x18004e750  test    eax, eax
0x18004e752  cmovnz  rdx, rcx
0x18004e756  mov     rax, rdx
0x18004e759  add     rsp, 20h
0x18004e75d  pop     rbx
0x18004e75e  retn
```
