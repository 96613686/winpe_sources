# Marshal::WriteXml<Schema::Containers::Definition::RegistryNamespace,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::RegistryNamespace const &,Marshal::MarshalContext const &)

- ea: `0x18001832c`
- end: `0x180018459`
- name: `??$WriteXml@URegistryNamespace@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBURegistryNamespace@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x180018920`

## callees

- `0x18000bdc8`
- `0x18001832c`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180018413`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x18001842d`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018444`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::RegistryNamespace,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistrySymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryRedirectionNode>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryHiveStack>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::RegistryNamespace_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<unsigned int>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::vector<unsigned char>>,Marshal::ModifierList<Marshal::AsHexString>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::RegistryNamespace_ClassData + 96;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistrySymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryRedirectionNode>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryHiveStack>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
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
0x18001832c  mov     [rsp+arg_0], rbx
0x180018331  mov     [rsp+arg_8], rsi
0x180018336  push    rdi
0x180018337  sub     rsp, 60h
0x18001833b  mov     rsi, r9
0x18001833e  mov     rbx, rdx
0x180018341  mov     rdi, rcx
0x180018344  test    r8b, r8b
0x180018347  jnz     loc_180018428
0x18001834d  test    rdx, rdx
0x180018350  jz      short loc_180018374
0x180018352  mov     rcx, [rcx]
0x180018355  mov     r8, rdx
0x180018358  xor     r9d, r9d
0x18001835b  xor     edx, edx
0x18001835d  mov     rax, [rcx]
0x180018360  mov     rax, [rax+0D8h]
0x180018367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001836c  test    eax, eax
0x18001836e  js      loc_18001843F
0x180018374  mov     rax, cs:?RegistryNamespace_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::RegistryNamespace_ClassData
0x18001837b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@URegistrySymlink@Definition@Containers@Schema@@V?$allocator@URegistrySymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryRedirectionNode@Definition@Containers@Schema@@V?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@V?$vector@URegistryHiveStack@Definition@Containers@Schema@@V?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistrySymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryRedirectionNode>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryHiveStack>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180018382  mov     r8, [rsp+68h+arg_20]
0x18001838a  lea     r9, [rsp+68h+var_18]
0x18001838f  mov     [rsp+68h+var_38], rcx
0x180018394  mov     rdx, rsi
0x180018397  mov     [rsp+68h+var_18], rax
0x18001839c  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@U?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@I@vmstd@@U?$ModifierList@$$V@Marshal@@@4@U34@U?$ModifiedType@U?$optional@V?$vector@EV?$allocator@E@std@@@std@@@vmstd@@U?$ModifierList@UAsHexString@Marshal@@@Marshal@@@4@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<uint>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::vector<uchar>>,Marshal::ModifierList<Marshal::AsHexString>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800183a3  mov     [rsp+68h+var_30], rcx
0x1800183a8  add     rax, 60h ; '`'
0x1800183ac  mov     [rsp+68h+var_10], rax
0x1800183b1  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@URegistrySymlink@Definition@Containers@Schema@@V?$allocator@URegistrySymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryRedirectionNode@Definition@Containers@Schema@@V?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@V?$vector@URegistryHiveStack@Definition@Containers@Schema@@V?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::BaseTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistrySymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryRedirectionNode>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryHiveStack>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800183b8  mov     qword ptr [rsp+68h+var_28], rcx
0x1800183bd  lea     rax, [rsp+68h+var_38]
0x1800183c2  mov     [rsp+68h+var_40], rax
0x1800183c7  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4ObjectDirectoryShadow@Definition@Containers@Schema@@U?$ModifiedType@V?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@6@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800183ce  mov     [rsp+68h+var_20], rcx
0x1800183d3  lea     rax, [rsp+68h+var_28]
0x1800183d8  mov     rcx, rdi
0x1800183db  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800183e0  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x1800183e5  test    rbx, rbx
0x1800183e8  jz      short loc_1800183FD
0x1800183ea  mov     rcx, [rdi]
0x1800183ed  mov     rax, [rcx]
0x1800183f0  mov     rax, [rax+78h]
0x1800183f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183f9  test    eax, eax
0x1800183fb  js      short loc_18001840E
0x1800183fd  mov     rbx, [rsp+68h+arg_0]
0x180018402  mov     rsi, [rsp+68h+arg_8]
0x180018407  add     rsp, 60h
0x18001840b  pop     rdi
0x18001840c  retn
0x18001840e  mov     rcx, [rsp+68h]; this
0x180018413  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001841a  mov     r9d, eax; char *
0x18001841d  mov     edx, 1EFh; void *
0x180018422  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018428  mov     rcx, [rsp+68h]; this
0x18001842d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018434  mov     edx, 1DFh; void *
0x180018439  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001843f  mov     rcx, [rsp+68h]; this
0x180018444  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001844b  mov     r9d, eax; char *
0x18001844e  mov     edx, 1E3h; void *
0x180018453  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
