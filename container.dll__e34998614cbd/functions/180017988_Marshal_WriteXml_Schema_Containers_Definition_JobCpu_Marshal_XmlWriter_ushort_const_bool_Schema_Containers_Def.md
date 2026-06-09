# Marshal::WriteXml<Schema::Containers::Definition::JobCpu,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::JobCpu const &,Marshal::MarshalContext const &)

- ea: `0x180017988`
- end: `0x180017ab5`
- name: `??$WriteXml@UJobCpu@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUJobCpu@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800187a0`

## callees

- `0x18000bdc8`
- `0x180017988`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180017a6f`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017a89`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017aa0`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::JobCpu,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<unsigned int,unsigned int>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::JobCpu_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobCpu>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobMemory>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobSystemRoot>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<enum Schema::Containers::Definition::JobTerminationPolicy>,Marshal::ModifierList<>>,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::JobCpu_ClassData + 64LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<unsigned int,unsigned int>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x180017988  mov     [rsp+arg_0], rbx
0x18001798d  mov     [rsp+arg_8], rsi
0x180017992  push    rdi
0x180017993  sub     rsp, 60h
0x180017997  mov     rsi, r9
0x18001799a  mov     rbx, rdx
0x18001799d  mov     rdi, rcx
0x1800179a0  test    r8b, r8b
0x1800179a3  jnz     loc_180017A84
0x1800179a9  test    rdx, rdx
0x1800179ac  jz      short loc_1800179D0
0x1800179ae  mov     rcx, [rcx]
0x1800179b1  mov     r8, rdx
0x1800179b4  xor     r9d, r9d
0x1800179b7  xor     edx, edx
0x1800179b9  mov     rax, [rcx]
0x1800179bc  mov     rax, [rax+0D8h]
0x1800179c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179c8  test    eax, eax
0x1800179ca  js      loc_180017A9B
0x1800179d0  mov     rax, cs:?JobCpu_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::JobCpu_ClassData
0x1800179d7  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@II@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::XmlTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<uint,uint>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800179de  mov     r8, [rsp+68h+arg_20]
0x1800179e6  lea     r9, [rsp+68h+var_18]
0x1800179eb  mov     [rsp+68h+var_38], rcx
0x1800179f0  mov     rdx, rsi
0x1800179f3  mov     [rsp+68h+var_18], rax
0x1800179f8  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@U?$optional@UJobCpu@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@UJobMemory@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UJobSystemRoot@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@W4JobTerminationPolicy@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@_N@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobCpu>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobMemory>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobSystemRoot>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobTerminationPolicy>,Marshal::ModifierList<>>,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800179ff  mov     [rsp+68h+var_30], rcx
0x180017a04  add     rax, 40h ; '@'
0x180017a08  mov     [rsp+68h+var_10], rax
0x180017a0d  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@II@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<uint,uint>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017a14  mov     qword ptr [rsp+68h+var_28], rcx
0x180017a19  lea     rax, [rsp+68h+var_38]
0x180017a1e  mov     [rsp+68h+var_40], rax
0x180017a23  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017a2a  mov     [rsp+68h+var_20], rcx
0x180017a2f  lea     rax, [rsp+68h+var_28]
0x180017a34  mov     rcx, rdi
0x180017a37  mov     qword ptr [rsp+68h+var_48], rax; int
0x180017a3c  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180017a41  test    rbx, rbx
0x180017a44  jz      short loc_180017A59
0x180017a46  mov     rcx, [rdi]
0x180017a49  mov     rax, [rcx]
0x180017a4c  mov     rax, [rax+78h]
0x180017a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a55  test    eax, eax
0x180017a57  js      short loc_180017A6A
0x180017a59  mov     rbx, [rsp+68h+arg_0]
0x180017a5e  mov     rsi, [rsp+68h+arg_8]
0x180017a63  add     rsp, 60h
0x180017a67  pop     rdi
0x180017a68  retn
0x180017a6a  mov     rcx, [rsp+68h]; this
0x180017a6f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017a76  mov     r9d, eax; char *
0x180017a79  mov     edx, 1EFh; void *
0x180017a7e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017a84  mov     rcx, [rsp+68h]; this
0x180017a89  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017a90  mov     edx, 1DFh; void *
0x180017a95  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180017a9b  mov     rcx, [rsp+68h]; this
0x180017aa0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017aa7  mov     r9d, eax; char *
0x180017aaa  mov     edx, 1E3h; void *
0x180017aaf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
