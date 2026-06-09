# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::DeviceCategory,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180018b40`
- end: `0x180018c6d`
- name: `??$WriteXmlVoid@UDeviceCategory@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000bdc8`
- `0x180018b40`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180018c27`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018c41`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018c58`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::DeviceCategory,>(
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
  __int64 *v14; // [rsp+48h] [rbp-20h]
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::DeviceCategory_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryDeleteKey>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::DeviceCategory_ClassData + 64LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = &qword_180044518;
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
0x180018b40  mov     [rsp+arg_0], rbx
0x180018b45  mov     [rsp+arg_8], rsi
0x180018b4a  push    rdi
0x180018b4b  sub     rsp, 60h
0x180018b4f  mov     rsi, r9
0x180018b52  mov     rbx, rdx
0x180018b55  mov     rdi, rcx
0x180018b58  test    r8b, r8b
0x180018b5b  jnz     loc_180018C3C
0x180018b61  test    rdx, rdx
0x180018b64  jz      short loc_180018B88
0x180018b66  mov     rcx, [rcx]
0x180018b69  mov     r8, rdx
0x180018b6c  xor     r9d, r9d
0x180018b6f  xor     edx, edx
0x180018b71  mov     rax, [rcx]
0x180018b74  mov     rax, [rax+0D8h]
0x180018b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b80  test    eax, eax
0x180018b82  js      loc_180018C53
0x180018b88  mov     rax, cs:?DeviceCategory_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::DeviceCategory_ClassData
0x180018b8f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@UInterfaceClass@Definition@Containers@Schema@@V?$allocator@UInterfaceClass@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::XmlTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180018b96  mov     r8, [rsp+68h+arg_20]
0x180018b9e  lea     r9, [rsp+68h+var_18]
0x180018ba3  mov     [rsp+68h+var_38], rcx
0x180018ba8  mov     rdx, rsi
0x180018bab  mov     [rsp+68h+var_18], rax
0x180018bb0  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@U?$ModifiedType@V?$vector@URegistryDeleteKey@Definition@Containers@Schema@@V?$allocator@URegistryDeleteKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::BaseTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryDeleteKey>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018bb7  mov     [rsp+68h+var_30], rcx
0x180018bbc  add     rax, 40h ; '@'
0x180018bc0  mov     [rsp+68h+var_10], rax
0x180018bc5  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@UInterfaceClass@Definition@Containers@Schema@@V?$allocator@UInterfaceClass@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018bcc  mov     qword ptr [rsp+68h+var_28], rcx
0x180018bd1  lea     rax, [rsp+68h+var_38]
0x180018bd6  mov     [rsp+68h+var_40], rax
0x180018bdb  lea     rcx, qword_180044518
0x180018be2  mov     [rsp+68h+var_20], rcx
0x180018be7  lea     rax, [rsp+68h+var_28]
0x180018bec  mov     rcx, rdi
0x180018bef  mov     qword ptr [rsp+68h+var_48], rax; int
0x180018bf4  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180018bf9  test    rbx, rbx
0x180018bfc  jz      short loc_180018C11
0x180018bfe  mov     rcx, [rdi]
0x180018c01  mov     rax, [rcx]
0x180018c04  mov     rax, [rax+78h]
0x180018c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c0d  test    eax, eax
0x180018c0f  js      short loc_180018C22
0x180018c11  mov     rbx, [rsp+68h+arg_0]
0x180018c16  mov     rsi, [rsp+68h+arg_8]
0x180018c1b  add     rsp, 60h
0x180018c1f  pop     rdi
0x180018c20  retn
0x180018c22  mov     rcx, [rsp+68h]; this
0x180018c27  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018c2e  mov     r9d, eax; char *
0x180018c31  mov     edx, 1EFh; void *
0x180018c36  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018c3c  mov     rcx, [rsp+68h]; this
0x180018c41  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018c48  mov     edx, 1DFh; void *
0x180018c4d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180018c53  mov     rcx, [rsp+68h]; this
0x180018c58  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018c5f  mov     r9d, eax; char *
0x180018c62  mov     edx, 1E3h; void *
0x180018c67  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
