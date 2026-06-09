# std::_Ref_count_resource<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>> *,std::default_delete<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>>::_Get_deleter(type_info const &)

- ea: `0x18004e7b0`
- end: `0x18004e7df`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAV?$IProfileDataItemTypeService@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@wil@@U?$default_delete@V?$IProfileDataItemTypeService@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@wil@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e7c4`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e7c4`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>> *,std::default_delete<wil::IProfileDataItemTypeService<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_1800755E8);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18004e7b0  push    rbx
0x18004e7b2  sub     rsp, 20h
0x18004e7b6  mov     rbx, rcx
0x18004e7b9  lea     rcx, [rdx+8]
0x18004e7bd  lea     rdx, qword_1800755E8
0x18004e7c4  call    cs:__imp___std_type_info_compare
0x18004e7ca  xor     ecx, ecx
0x18004e7cc  lea     rdx, [rbx+10h]
0x18004e7d0  test    eax, eax
0x18004e7d2  cmovnz  rdx, rcx
0x18004e7d6  mov     rax, rdx
0x18004e7d9  add     rsp, 20h
0x18004e7dd  pop     rbx
0x18004e7de  retn
```
