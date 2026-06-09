# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::DeviceInstance,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180018c80`
- end: `0x180018dad`
- name: `??$WriteXmlVoid@UDeviceInstance@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000bdc8`
- `0x180018c80`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180018d67`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018d81`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018d98`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::DeviceInstance,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::DeviceInstance_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeValue>,Marshal::ModifierList<>>,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::DeviceInstance_ClassData + 128LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
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
0x180018c80  mov     [rsp+arg_0], rbx
0x180018c85  mov     [rsp+arg_8], rsi
0x180018c8a  push    rdi
0x180018c8b  sub     rsp, 60h
0x180018c8f  mov     rsi, r9
0x180018c92  mov     rbx, rdx
0x180018c95  mov     rdi, rcx
0x180018c98  test    r8b, r8b
0x180018c9b  jnz     loc_180018D7C
0x180018ca1  test    rdx, rdx
0x180018ca4  jz      short loc_180018CC8
0x180018ca6  mov     rcx, [rcx]
0x180018ca9  mov     r8, rdx
0x180018cac  xor     r9d, r9d
0x180018caf  xor     edx, edx
0x180018cb1  mov     rax, [rcx]
0x180018cb4  mov     rax, [rax+0D8h]
0x180018cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cc0  test    eax, eax
0x180018cc2  js      loc_180018D93
0x180018cc8  mov     rax, cs:?DeviceInstance_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::DeviceInstance_ClassData
0x180018ccf  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@U?$ModifiedType@V?$vector@UInterfaceClass@Definition@Containers@Schema@@V?$allocator@UInterfaceClass@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::XmlTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180018cd6  mov     r8, [rsp+68h+arg_20]
0x180018cde  lea     r9, [rsp+68h+var_18]
0x180018ce3  mov     [rsp+68h+var_38], rcx
0x180018ce8  mov     rdx, rsi
0x180018ceb  mov     [rsp+68h+var_18], rax
0x180018cf0  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@_N@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeValue>,Marshal::ModifierList<>>,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180018cf7  mov     [rsp+68h+var_30], rcx
0x180018cfc  sub     rax, 0FFFFFFFFFFFFFF80h
0x180018d00  mov     [rsp+68h+var_10], rax
0x180018d05  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@U?$ModifiedType@V?$vector@UInterfaceClass@Definition@Containers@Schema@@V?$allocator@UInterfaceClass@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::BaseTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018d0c  mov     qword ptr [rsp+68h+var_28], rcx
0x180018d11  lea     rax, [rsp+68h+var_38]
0x180018d16  mov     [rsp+68h+var_40], rax
0x180018d1b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@UNamespace@Definition@Containers@Schema@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180018d22  mov     [rsp+68h+var_20], rcx
0x180018d27  lea     rax, [rsp+68h+var_28]
0x180018d2c  mov     rcx, rdi
0x180018d2f  mov     qword ptr [rsp+68h+var_48], rax; int
0x180018d34  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180018d39  test    rbx, rbx
0x180018d3c  jz      short loc_180018D51
0x180018d3e  mov     rcx, [rdi]
0x180018d41  mov     rax, [rcx]
0x180018d44  mov     rax, [rax+78h]
0x180018d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d4d  test    eax, eax
0x180018d4f  js      short loc_180018D62
0x180018d51  mov     rbx, [rsp+68h+arg_0]
0x180018d56  mov     rsi, [rsp+68h+arg_8]
0x180018d5b  add     rsp, 60h
0x180018d5f  pop     rdi
0x180018d60  retn
0x180018d62  mov     rcx, [rsp+68h]; this
0x180018d67  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018d6e  mov     r9d, eax; char *
0x180018d71  mov     edx, 1EFh; void *
0x180018d76  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018d7c  mov     rcx, [rsp+68h]; this
0x180018d81  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018d88  mov     edx, 1DFh; void *
0x180018d8d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180018d93  mov     rcx, [rsp+68h]; this
0x180018d98  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018d9f  mov     r9d, eax; char *
0x180018da2  mov     edx, 1E3h; void *
0x180018da7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
