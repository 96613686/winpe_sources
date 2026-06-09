# Marshal::WriteXml<Schema::Containers::Definition::NamedPipeNamespace,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::NamedPipeNamespace const &,Marshal::MarshalContext const &)

- ea: `0x180017f90`
- end: `0x1800180bd`
- name: `??$WriteXml@UNamedPipeNamespace@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUNamedPipeNamespace@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x180018890`

## callees

- `0x18000bdc8`
- `0x180017f90`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180018077`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018091`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800180a8`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::NamedPipeNamespace,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::NamedPipeSymlink>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::NamedPipeNamespace_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::NamedPipeNamespace_ClassData + 32;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::NamedPipeSymlink>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<unsigned int>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::vector<unsigned char>>,Marshal::ModifierList<Marshal::AsHexString>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x180017f90  mov     [rsp+arg_0], rbx
0x180017f95  mov     [rsp+arg_8], rsi
0x180017f9a  push    rdi
0x180017f9b  sub     rsp, 60h
0x180017f9f  mov     rsi, r9
0x180017fa2  mov     rbx, rdx
0x180017fa5  mov     rdi, rcx
0x180017fa8  test    r8b, r8b
0x180017fab  jnz     loc_18001808C
0x180017fb1  test    rdx, rdx
0x180017fb4  jz      short loc_180017FD8
0x180017fb6  mov     rcx, [rcx]
0x180017fb9  mov     r8, rdx
0x180017fbc  xor     r9d, r9d
0x180017fbf  xor     edx, edx
0x180017fc1  mov     rax, [rcx]
0x180017fc4  mov     rax, [rax+0D8h]
0x180017fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fd0  test    eax, eax
0x180017fd2  js      loc_1800180A3
0x180017fd8  mov     rax, cs:?NamedPipeNamespace_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::NamedPipeNamespace_ClassData
0x180017fdf  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UNamedPipeSymlink@Definition@Containers@Schema@@V?$allocator@UNamedPipeSymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::NamedPipeSymlink>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180017fe6  mov     r8, [rsp+68h+arg_20]
0x180017fee  lea     r9, [rsp+68h+var_18]
0x180017ff3  mov     [rsp+68h+var_38], rcx
0x180017ff8  mov     rdx, rsi
0x180017ffb  mov     [rsp+68h+var_18], rax
0x180018000  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180018007  mov     [rsp+68h+var_30], rcx
0x18001800c  add     rax, 20h ; ' '
0x180018010  mov     [rsp+68h+var_10], rax
0x180018015  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UNamedPipeSymlink@Definition@Containers@Schema@@V?$allocator@UNamedPipeSymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::NamedPipeSymlink>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x18001801c  mov     qword ptr [rsp+68h+var_28], rcx
0x180018021  lea     rax, [rsp+68h+var_38]
0x180018026  mov     [rsp+68h+var_40], rax
0x18001802b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@U?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@I@vmstd@@U?$ModifierList@$$V@Marshal@@@4@U34@U?$ModifiedType@U?$optional@V?$vector@EV?$allocator@E@std@@@std@@@vmstd@@U?$ModifierList@UAsHexString@Marshal@@@Marshal@@@4@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<uint>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::wstring>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<std::vector<uchar>>,Marshal::ModifierList<Marshal::AsHexString>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018032  mov     [rsp+68h+var_20], rcx
0x180018037  lea     rax, [rsp+68h+var_28]
0x18001803c  mov     rcx, rdi
0x18001803f  mov     qword ptr [rsp+68h+var_48], rax; int
0x180018044  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180018049  test    rbx, rbx
0x18001804c  jz      short loc_180018061
0x18001804e  mov     rcx, [rdi]
0x180018051  mov     rax, [rcx]
0x180018054  mov     rax, [rax+78h]
0x180018058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001805d  test    eax, eax
0x18001805f  js      short loc_180018072
0x180018061  mov     rbx, [rsp+68h+arg_0]
0x180018066  mov     rsi, [rsp+68h+arg_8]
0x18001806b  add     rsp, 60h
0x18001806f  pop     rdi
0x180018070  retn
0x180018072  mov     rcx, [rsp+68h]; this
0x180018077  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001807e  mov     r9d, eax; char *
0x180018081  mov     edx, 1EFh; void *
0x180018086  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001808c  mov     rcx, [rsp+68h]; this
0x180018091  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018098  mov     edx, 1DFh; void *
0x18001809d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800180a3  mov     rcx, [rsp+68h]; this
0x1800180a8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800180af  mov     r9d, eax; char *
0x1800180b2  mov     edx, 1E3h; void *
0x1800180b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
