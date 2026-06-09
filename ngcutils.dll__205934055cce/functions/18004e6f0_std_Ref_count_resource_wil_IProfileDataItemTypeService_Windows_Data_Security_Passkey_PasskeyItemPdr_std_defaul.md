# std::_Ref_count_resource<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::PasskeyItemPdr> *,std::default_delete<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Get_deleter(type_info const &)

- ea: `0x18004e6f0`
- end: `0x18004e71f`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAV?$IProfileDataItemTypeService@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@U?$default_delete@V?$IProfileDataItemTypeService@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e704`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e704`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::PasskeyItemPdr> *,std::default_delete<wil::IProfileDataItemTypeService<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_180075448);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18004e6f0  push    rbx
0x18004e6f2  sub     rsp, 20h
0x18004e6f6  mov     rbx, rcx
0x18004e6f9  lea     rcx, [rdx+8]
0x18004e6fd  lea     rdx, qword_180075448
0x18004e704  call    cs:__imp___std_type_info_compare
0x18004e70a  xor     ecx, ecx
0x18004e70c  lea     rdx, [rbx+10h]
0x18004e710  test    eax, eax
0x18004e712  cmovnz  rdx, rcx
0x18004e716  mov     rax, rdx
0x18004e719  add     rsp, 20h
0x18004e71d  pop     rbx
0x18004e71e  retn
```
