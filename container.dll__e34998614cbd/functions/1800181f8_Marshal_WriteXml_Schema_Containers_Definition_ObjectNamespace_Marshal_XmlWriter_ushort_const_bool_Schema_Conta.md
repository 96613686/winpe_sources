# Marshal::WriteXml<Schema::Containers::Definition::ObjectNamespace,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::ObjectNamespace const &,Marshal::MarshalContext const &)

- ea: `0x1800181f8`
- end: `0x180018325`
- name: `??$WriteXml@UObjectNamespace@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUObjectNamespace@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x1800188f0`

## callees

- `0x18000bdc8`
- `0x1800181f8`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x1800182df`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800182f9`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018310`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::ObjectNamespace,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::ObjectNamespace_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::ObjectNamespace_ClassData + 96;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x1800181f8  mov     [rsp+arg_0], rbx
0x1800181fd  mov     [rsp+arg_8], rsi
0x180018202  push    rdi
0x180018203  sub     rsp, 60h
0x180018207  mov     rsi, r9
0x18001820a  mov     rbx, rdx
0x18001820d  mov     rdi, rcx
0x180018210  test    r8b, r8b
0x180018213  jnz     loc_1800182F4
0x180018219  test    rdx, rdx
0x18001821c  jz      short loc_180018240
0x18001821e  mov     rcx, [rcx]
0x180018221  mov     r8, rdx
0x180018224  xor     r9d, r9d
0x180018227  xor     edx, edx
0x180018229  mov     rax, [rcx]
0x18001822c  mov     rax, [rax+0D8h]
0x180018233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018238  test    eax, eax
0x18001823a  js      loc_18001830B
0x180018240  mov     rax, cs:?ObjectNamespace_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::ObjectNamespace_ClassData
0x180018247  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4ObjectDirectoryShadow@Definition@Containers@Schema@@U?$ModifiedType@V?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@6@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x18001824e  mov     r8, [rsp+68h+arg_20]
0x180018256  lea     r9, [rsp+68h+var_18]
0x18001825b  mov     [rsp+68h+var_38], rcx
0x180018260  mov     rdx, rsi
0x180018263  mov     [rsp+68h+var_18], rax
0x180018268  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@U?$ModifiedType@V?$vector@UInterfaceClass@Definition@Containers@Schema@@V?$allocator@UInterfaceClass@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::XmlTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x18001826f  mov     [rsp+68h+var_30], rcx
0x180018274  add     rax, 60h ; '`'
0x180018278  mov     [rsp+68h+var_10], rax
0x18001827d  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4ObjectDirectoryShadow@Definition@Containers@Schema@@U?$ModifiedType@V?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@6@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::BaseTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018284  mov     qword ptr [rsp+68h+var_28], rcx
0x180018289  lea     rax, [rsp+68h+var_38]
0x18001828e  mov     [rsp+68h+var_40], rax
0x180018293  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@U?$ModifiedType@V?$vector@UInterfaceClass@Definition@Containers@Schema@@V?$allocator@UInterfaceClass@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::BaseTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x18001829a  mov     [rsp+68h+var_20], rcx
0x18001829f  lea     rax, [rsp+68h+var_28]
0x1800182a4  mov     rcx, rdi
0x1800182a7  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800182ac  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x1800182b1  test    rbx, rbx
0x1800182b4  jz      short loc_1800182C9
0x1800182b6  mov     rcx, [rdi]
0x1800182b9  mov     rax, [rcx]
0x1800182bc  mov     rax, [rax+78h]
0x1800182c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182c5  test    eax, eax
0x1800182c7  js      short loc_1800182DA
0x1800182c9  mov     rbx, [rsp+68h+arg_0]
0x1800182ce  mov     rsi, [rsp+68h+arg_8]
0x1800182d3  add     rsp, 60h
0x1800182d7  pop     rdi
0x1800182d8  retn
0x1800182da  mov     rcx, [rsp+68h]; this
0x1800182df  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800182e6  mov     r9d, eax; char *
0x1800182e9  mov     edx, 1EFh; void *
0x1800182ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800182f4  mov     rcx, [rsp+68h]; this
0x1800182f9  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018300  mov     edx, 1DFh; void *
0x180018305  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001830b  mov     rcx, [rsp+68h]; this
0x180018310  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018317  mov     r9d, eax; char *
0x18001831a  mov     edx, 1E3h; void *
0x18001831f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
