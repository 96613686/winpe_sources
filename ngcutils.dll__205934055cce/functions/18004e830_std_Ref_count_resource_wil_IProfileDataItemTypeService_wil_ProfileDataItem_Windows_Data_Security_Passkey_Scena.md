# std::_Ref_count_resource<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>> *,std::default_delete<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>>>>::_Get_deleter(type_info const &)

- ea: `0x18004e830`
- end: `0x18004e85f`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAV?$IProfileDataItemTypeService@V?$ProfileDataItem@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@@wil@@U?$default_delete@V?$IProfileDataItemTypeService@V?$ProfileDataItem@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@@wil@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e844`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e844`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>> *,std::default_delete<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>>>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_180075728);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18004e830  push    rbx
0x18004e832  sub     rsp, 20h
0x18004e836  mov     rbx, rcx
0x18004e839  lea     rcx, [rdx+8]
0x18004e83d  lea     rdx, qword_180075728
0x18004e844  call    cs:__imp___std_type_info_compare
0x18004e84a  xor     ecx, ecx
0x18004e84c  lea     rdx, [rbx+10h]
0x18004e850  test    eax, eax
0x18004e852  cmovnz  rdx, rcx
0x18004e856  mov     rax, rdx
0x18004e859  add     rsp, 20h
0x18004e85d  pop     rbx
0x18004e85e  retn
```
