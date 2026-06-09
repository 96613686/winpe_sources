# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::ObjectSymlink,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180019540`
- end: `0x18001966f`
- name: `??$WriteXmlVoid@UObjectSymlink@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callees

- `0x18000bdc8`
- `0x180019540`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180019629`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019643`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x18001965a`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::ObjectSymlink,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,enum Schema::Containers::Definition::ObjectSymlinkScope,std::wstring,unsigned int>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::ObjectSymlink_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobCpu>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobMemory>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobSystemRoot>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<enum Schema::Containers::Definition::JobTerminationPolicy>,Marshal::ModifierList<>>,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::ObjectSymlink_ClassData + 160LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,enum Schema::Containers::Definition::ObjectSymlinkScope,std::wstring,unsigned int>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<unsigned __int64>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x180019540  mov     [rsp+arg_0], rbx
0x180019545  mov     [rsp+arg_8], rsi
0x18001954a  push    rdi
0x18001954b  sub     rsp, 60h
0x18001954f  mov     rsi, r9
0x180019552  mov     rbx, rdx
0x180019555  mov     rdi, rcx
0x180019558  test    r8b, r8b
0x18001955b  jnz     loc_18001963E
0x180019561  test    rdx, rdx
0x180019564  jz      short loc_180019588
0x180019566  mov     rcx, [rcx]
0x180019569  mov     r8, rdx
0x18001956c  xor     r9d, r9d
0x18001956f  xor     edx, edx
0x180019571  mov     rax, [rcx]
0x180019574  mov     rax, [rax+0D8h]
0x18001957b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019580  test    eax, eax
0x180019582  js      loc_180019655
0x180019588  mov     rax, cs:?ObjectSymlink_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::ObjectSymlink_ClassData
0x18001958f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@W4ObjectSymlinkScope@Definition@Containers@Schema@@V12@I@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Schema::Containers::Definition::ObjectSymlinkScope,std::wstring,uint>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019596  mov     r8, [rsp+68h+arg_20]
0x18001959e  lea     r9, [rsp+68h+var_18]
0x1800195a3  mov     [rsp+68h+var_38], rcx
0x1800195a8  mov     rdx, rsi
0x1800195ab  mov     [rsp+68h+var_18], rax
0x1800195b0  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@U?$optional@UJobCpu@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@UJobMemory@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UJobSystemRoot@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@W4JobTerminationPolicy@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@_N@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobCpu>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobMemory>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobSystemRoot>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobTerminationPolicy>,Marshal::ModifierList<>>,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800195b7  mov     [rsp+68h+var_30], rcx
0x1800195bc  add     rax, 0A0h
0x1800195c2  mov     [rsp+68h+var_10], rax
0x1800195c7  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@W4ObjectSymlinkScope@Definition@Containers@Schema@@V12@I@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Schema::Containers::Definition::ObjectSymlinkScope,std::wstring,uint>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800195ce  mov     qword ptr [rsp+68h+var_28], rcx
0x1800195d3  lea     rax, [rsp+68h+var_38]
0x1800195d8  mov     [rsp+68h+var_40], rax
0x1800195dd  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@_K@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<unsigned __int64>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800195e4  mov     [rsp+68h+var_20], rcx
0x1800195e9  lea     rax, [rsp+68h+var_28]
0x1800195ee  mov     rcx, rdi
0x1800195f1  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800195f6  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x1800195fb  test    rbx, rbx
0x1800195fe  jz      short loc_180019613
0x180019600  mov     rcx, [rdi]
0x180019603  mov     rax, [rcx]
0x180019606  mov     rax, [rax+78h]
0x18001960a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001960f  test    eax, eax
0x180019611  js      short loc_180019624
0x180019613  mov     rbx, [rsp+68h+arg_0]
0x180019618  mov     rsi, [rsp+68h+arg_8]
0x18001961d  add     rsp, 60h
0x180019621  pop     rdi
0x180019622  retn
0x180019624  mov     rcx, [rsp+68h]; this
0x180019629  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019630  mov     r9d, eax; char *
0x180019633  mov     edx, 1EFh; void *
0x180019638  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001963e  mov     rcx, [rsp+68h]; this
0x180019643  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001964a  mov     edx, 1DFh; void *
0x18001964f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180019655  mov     rcx, [rsp+68h]; this
0x18001965a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019661  mov     r9d, eax; char *
0x180019664  mov     edx, 1E3h; void *
0x180019669  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
