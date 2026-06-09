# std::_Ref_count_resource<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::ScenarioKeysItemPdr> *,std::default_delete<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>>>::_Get_deleter(type_info const &)

- ea: `0x18004e770`
- end: `0x18004e79f`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAV?$IProfileDataItemTypeService@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@U?$default_delete@V?$IProfileDataItemTypeService@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e784`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e784`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::ScenarioKeysItemPdr> *,std::default_delete<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_180075558);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18004e770  push    rbx
0x18004e772  sub     rsp, 20h
0x18004e776  mov     rbx, rcx
0x18004e779  lea     rcx, [rdx+8]
0x18004e77d  lea     rdx, qword_180075558
0x18004e784  call    cs:__imp___std_type_info_compare
0x18004e78a  xor     ecx, ecx
0x18004e78c  lea     rdx, [rbx+10h]
0x18004e790  test    eax, eax
0x18004e792  cmovnz  rdx, rcx
0x18004e796  mov     rax, rdx
0x18004e799  add     rsp, 20h
0x18004e79d  pop     rbx
0x18004e79e  retn
```
