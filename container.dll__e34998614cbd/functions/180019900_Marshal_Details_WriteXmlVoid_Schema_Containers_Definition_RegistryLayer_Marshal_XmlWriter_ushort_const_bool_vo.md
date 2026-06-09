# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::RegistryLayer,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180019900`
- end: `0x180019a2f`
- name: `??$WriteXmlVoid@URegistryLayer@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callees

- `0x18000bdc8`
- `0x180019900`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x1800199e9`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019a03`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019a1a`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::RegistryLayer,>(
        _QWORD *a1,
        __int64 a2,
        char a3,
        const char *a4,
        __int64 a5)
{
  int v5; // esi
  int v8; // eax
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-48h]
  int v11; // [rsp+20h] [rbp-48h]
  _QWORD v12[2]; // [rsp+30h] [rbp-38h] BYREF
  int v13[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 (__fastcall ***v14)(int, int, int, int, __int64); // [rsp+48h] [rbp-20h]
  _QWORD v15[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = (int)a4;
  if ( a3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
      a4);
  if ( a2 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(*(_QWORD *)*a1 + 216LL))(*a1, 0, a2, 0);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1E3,
        (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
        (const char *)(unsigned int)v8,
        v10);
  }
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,_GUID,bool,bool,bool,bool,bool,unsigned __int64>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::RegistryLayer_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryDeleteKey>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::RegistryLayer_ClassData + 288LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,_GUID,bool,bool,bool,bool,bool,unsigned __int64>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,enum Schema::Containers::Definition::ObjectSymlinkScope,std::wstring,unsigned int>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  result = Marshal::Details::WriteObjectXml((_DWORD)a1, v5, a5, (unsigned int)v15, (__int64)v13, (__int64)v12);
  if ( a2 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 120LL))(*a1);
    if ( (int)result < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
        (const char *)(unsigned int)result,
        v11);
  }
  return result;
}

```

## disassembly

```asm
0x180019900  mov     [rsp+arg_0], rbx
0x180019905  mov     [rsp+arg_8], rsi
0x18001990a  push    rdi
0x18001990b  sub     rsp, 60h
0x18001990f  mov     rsi, r9
0x180019912  mov     rbx, rdx
0x180019915  mov     rdi, rcx
0x180019918  test    r8b, r8b
0x18001991b  jnz     loc_1800199FE
0x180019921  test    rdx, rdx
0x180019924  jz      short loc_180019948
0x180019926  mov     rcx, [rcx]
0x180019929  mov     r8, rdx
0x18001992c  xor     r9d, r9d
0x18001992f  xor     edx, edx
0x180019931  mov     rax, [rcx]
0x180019934  mov     rax, [rax+0D8h]
0x18001993b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019940  test    eax, eax
0x180019942  js      loc_180019A15
0x180019948  mov     rax, cs:?RegistryLayer_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::RegistryLayer_ClassData
0x18001994f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U_GUID@@_N_N_N_N_N_K@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$08@std@@A; std::array<Marshal::Details::XmlTypeData const *,9> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,_GUID,bool,bool,bool,bool,bool,unsigned __int64>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019956  mov     r8, [rsp+68h+arg_20]
0x18001995e  lea     r9, [rsp+68h+var_18]
0x180019963  mov     [rsp+68h+var_38], rcx
0x180019968  mov     rdx, rsi
0x18001996b  mov     [rsp+68h+var_18], rax
0x180019970  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@U?$ModifiedType@V?$vector@URegistryDeleteKey@Definition@Containers@Schema@@V?$allocator@URegistryDeleteKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::XmlTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryDeleteKey>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019977  mov     [rsp+68h+var_30], rcx
0x18001997c  add     rax, 120h
0x180019982  mov     [rsp+68h+var_10], rax
0x180019987  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U_GUID@@_N_N_N_N_N_K@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$08@std@@A; std::array<Marshal::Details::BaseTypeData const *,9> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,_GUID,bool,bool,bool,bool,bool,unsigned __int64>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x18001998e  mov     qword ptr [rsp+68h+var_28], rcx
0x180019993  lea     rax, [rsp+68h+var_38]
0x180019998  mov     [rsp+68h+var_40], rax
0x18001999d  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@W4ObjectSymlinkScope@Definition@Containers@Schema@@V12@I@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Schema::Containers::Definition::ObjectSymlinkScope,std::wstring,uint>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800199a4  mov     [rsp+68h+var_20], rcx
0x1800199a9  lea     rax, [rsp+68h+var_28]
0x1800199ae  mov     rcx, rdi
0x1800199b1  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800199b6  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x1800199bb  test    rbx, rbx
0x1800199be  jz      short loc_1800199D3
0x1800199c0  mov     rcx, [rdi]
0x1800199c3  mov     rax, [rcx]
0x1800199c6  mov     rax, [rax+78h]
0x1800199ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199cf  test    eax, eax
0x1800199d1  js      short loc_1800199E4
0x1800199d3  mov     rbx, [rsp+68h+arg_0]
0x1800199d8  mov     rsi, [rsp+68h+arg_8]
0x1800199dd  add     rsp, 60h
0x1800199e1  pop     rdi
0x1800199e2  retn
0x1800199e4  mov     rcx, [rsp+68h]; this
0x1800199e9  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800199f0  mov     r9d, eax; char *
0x1800199f3  mov     edx, 1EFh; void *
0x1800199f8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800199fe  mov     rcx, [rsp+68h]; this
0x180019a03  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019a0a  mov     edx, 1DFh; void *
0x180019a0f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180019a15  mov     rcx, [rsp+68h]; this
0x180019a1a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019a21  mov     r9d, eax; char *
0x180019a24  mov     edx, 1E3h; void *
0x180019a29  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
