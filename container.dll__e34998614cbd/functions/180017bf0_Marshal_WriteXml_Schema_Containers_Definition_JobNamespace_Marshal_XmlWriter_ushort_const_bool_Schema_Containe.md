# Marshal::WriteXml<Schema::Containers::Definition::JobNamespace,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::JobNamespace const &,Marshal::MarshalContext const &)

- ea: `0x180017bf0`
- end: `0x180017d1f`
- name: `??$WriteXml@UJobNamespace@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUJobNamespace@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018800`

## callees

- `0x18000bdc8`
- `0x180017bf0`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180017cd9`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017cf3`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017d0a`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::JobNamespace,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobCpu>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobMemory>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobSystemRoot>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<enum Schema::Containers::Definition::JobTerminationPolicy>,Marshal::ModifierList<>>,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::JobNamespace_ClassData;
  v12[1] = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::JobNamespace_ClassData + 160;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobCpu>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobMemory>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobSystemRoot>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<enum Schema::Containers::Definition::JobTerminationPolicy>,Marshal::ModifierList<>>,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
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
0x180017bf0  mov     [rsp+arg_0], rbx
0x180017bf5  mov     [rsp+arg_8], rsi
0x180017bfa  push    rdi
0x180017bfb  sub     rsp, 60h
0x180017bff  mov     rsi, r9
0x180017c02  mov     rbx, rdx
0x180017c05  mov     rdi, rcx
0x180017c08  test    r8b, r8b
0x180017c0b  jnz     loc_180017CEE
0x180017c11  test    rdx, rdx
0x180017c14  jz      short loc_180017C38
0x180017c16  mov     rcx, [rcx]
0x180017c19  mov     r8, rdx
0x180017c1c  xor     r9d, r9d
0x180017c1f  xor     edx, edx
0x180017c21  mov     rax, [rcx]
0x180017c24  mov     rax, [rax+0D8h]
0x180017c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c30  test    eax, eax
0x180017c32  js      loc_180017D05
0x180017c38  mov     rax, cs:?JobNamespace_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::JobNamespace_ClassData
0x180017c3f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@U?$optional@UJobCpu@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@UJobMemory@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UJobSystemRoot@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@W4JobTerminationPolicy@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@_N@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobCpu>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobMemory>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobSystemRoot>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobTerminationPolicy>,Marshal::ModifierList<>>,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180017c46  mov     r8, [rsp+68h+arg_20]
0x180017c4e  lea     r9, [rsp+68h+var_18]
0x180017c53  mov     [rsp+68h+var_38], rcx
0x180017c58  mov     rdx, rsi
0x180017c5b  mov     [rsp+68h+var_18], rax
0x180017c60  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@UNamespace@Definition@Containers@Schema@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017c67  mov     [rsp+68h+var_30], rcx
0x180017c6c  add     rax, 0A0h
0x180017c72  mov     [rsp+68h+var_10], rax
0x180017c77  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@U?$optional@UJobCpu@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@UJobMemory@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UJobSystemRoot@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@W4JobTerminationPolicy@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@_N@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobCpu>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobMemory>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobSystemRoot>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobTerminationPolicy>,Marshal::ModifierList<>>,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017c7e  mov     qword ptr [rsp+68h+var_28], rcx
0x180017c83  lea     rax, [rsp+68h+var_38]
0x180017c88  mov     [rsp+68h+var_40], rax
0x180017c8d  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::XmlTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180017c94  mov     [rsp+68h+var_20], rcx
0x180017c99  lea     rax, [rsp+68h+var_28]
0x180017c9e  mov     rcx, rdi
0x180017ca1  mov     qword ptr [rsp+68h+var_48], rax; int
0x180017ca6  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180017cab  test    rbx, rbx
0x180017cae  jz      short loc_180017CC3
0x180017cb0  mov     rcx, [rdi]
0x180017cb3  mov     rax, [rcx]
0x180017cb6  mov     rax, [rax+78h]
0x180017cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cbf  test    eax, eax
0x180017cc1  js      short loc_180017CD4
0x180017cc3  mov     rbx, [rsp+68h+arg_0]
0x180017cc8  mov     rsi, [rsp+68h+arg_8]
0x180017ccd  add     rsp, 60h
0x180017cd1  pop     rdi
0x180017cd2  retn
0x180017cd4  mov     rcx, [rsp+68h]; this
0x180017cd9  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017ce0  mov     r9d, eax; char *
0x180017ce3  mov     edx, 1EFh; void *
0x180017ce8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017cee  mov     rcx, [rsp+68h]; this
0x180017cf3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017cfa  mov     edx, 1DFh; void *
0x180017cff  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180017d05  mov     rcx, [rsp+68h]; this
0x180017d0a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017d11  mov     r9d, eax; char *
0x180017d14  mov     edx, 1E3h; void *
0x180017d19  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
