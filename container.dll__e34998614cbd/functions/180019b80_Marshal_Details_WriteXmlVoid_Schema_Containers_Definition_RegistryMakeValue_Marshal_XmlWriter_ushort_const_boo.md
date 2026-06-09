# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::RegistryMakeValue,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180019b80`
- end: `0x180019caf`
- name: `??$WriteXmlVoid@URegistryMakeValue@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000bdc8`
- `0x180019b80`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180019c69`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019c83`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019c9a`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::RegistryMakeValue,>(
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
  __int64 (__fastcall ***v14)(); // [rsp+48h] [rbp-20h]
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<unsigned int>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::vector<unsigned char>>,Marshal::ModifierList<Marshal::AsHexString>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::RegistryMakeValue_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::RegistryMakeValue_ClassData + 160LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<unsigned int>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::vector<unsigned char>>,Marshal::ModifierList<Marshal::AsHexString>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeValue>,Marshal::ModifierList<>>,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x180019b80  mov     [rsp+arg_0], rbx
0x180019b85  mov     [rsp+arg_8], rsi
0x180019b8a  push    rdi
0x180019b8b  sub     rsp, 60h
0x180019b8f  mov     rsi, r9
0x180019b92  mov     rbx, rdx
0x180019b95  mov     rdi, rcx
0x180019b98  test    r8b, r8b
0x180019b9b  jnz     loc_180019C7E
0x180019ba1  test    rdx, rdx
0x180019ba4  jz      short loc_180019BC8
0x180019ba6  mov     rcx, [rcx]
0x180019ba9  mov     r8, rdx
0x180019bac  xor     r9d, r9d
0x180019baf  xor     edx, edx
0x180019bb1  mov     rax, [rcx]
0x180019bb4  mov     rax, [rax+0D8h]
0x180019bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bc0  test    eax, eax
0x180019bc2  js      loc_180019C95
0x180019bc8  mov     rax, cs:?RegistryMakeValue_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::RegistryMakeValue_ClassData
0x180019bcf  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@U?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@I@vmstd@@U?$ModifierList@$$V@Marshal@@@4@U34@U?$ModifiedType@U?$optional@V?$vector@EV?$allocator@E@std@@@std@@@vmstd@@U?$ModifierList@UAsHexString@Marshal@@@Marshal@@@4@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<uint>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::vector<uchar>>,Marshal::ModifierList<Marshal::AsHexString>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019bd6  mov     r8, [rsp+68h+arg_20]
0x180019bde  lea     r9, [rsp+68h+var_18]
0x180019be3  mov     [rsp+68h+var_38], rcx
0x180019be8  mov     rdx, rsi
0x180019beb  mov     [rsp+68h+var_18], rax
0x180019bf0  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@UInterfaceClass@Definition@Containers@Schema@@V?$allocator@UInterfaceClass@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180019bf7  mov     [rsp+68h+var_30], rcx
0x180019bfc  add     rax, 0A0h
0x180019c02  mov     [rsp+68h+var_10], rax
0x180019c07  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@U?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@I@vmstd@@U?$ModifierList@$$V@Marshal@@@4@U34@U?$ModifiedType@U?$optional@V?$vector@EV?$allocator@E@std@@@std@@@vmstd@@U?$ModifierList@UAsHexString@Marshal@@@Marshal@@@4@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<uint>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::vector<uchar>>,Marshal::ModifierList<Marshal::AsHexString>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180019c0e  mov     qword ptr [rsp+68h+var_28], rcx
0x180019c13  lea     rax, [rsp+68h+var_38]
0x180019c18  mov     [rsp+68h+var_40], rax
0x180019c1d  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@_N@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeValue>,Marshal::ModifierList<>>,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180019c24  mov     [rsp+68h+var_20], rcx
0x180019c29  lea     rax, [rsp+68h+var_28]
0x180019c2e  mov     rcx, rdi
0x180019c31  mov     qword ptr [rsp+68h+var_48], rax; int
0x180019c36  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180019c3b  test    rbx, rbx
0x180019c3e  jz      short loc_180019C53
0x180019c40  mov     rcx, [rdi]
0x180019c43  mov     rax, [rcx]
0x180019c46  mov     rax, [rax+78h]
0x180019c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c4f  test    eax, eax
0x180019c51  js      short loc_180019C64
0x180019c53  mov     rbx, [rsp+68h+arg_0]
0x180019c58  mov     rsi, [rsp+68h+arg_8]
0x180019c5d  add     rsp, 60h
0x180019c61  pop     rdi
0x180019c62  retn
0x180019c64  mov     rcx, [rsp+68h]; this
0x180019c69  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019c70  mov     r9d, eax; char *
0x180019c73  mov     edx, 1EFh; void *
0x180019c78  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180019c7e  mov     rcx, [rsp+68h]; this
0x180019c83  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019c8a  mov     edx, 1DFh; void *
0x180019c8f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180019c95  mov     rcx, [rsp+68h]; this
0x180019c9a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019ca1  mov     r9d, eax; char *
0x180019ca4  mov     edx, 1E3h; void *
0x180019ca9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
