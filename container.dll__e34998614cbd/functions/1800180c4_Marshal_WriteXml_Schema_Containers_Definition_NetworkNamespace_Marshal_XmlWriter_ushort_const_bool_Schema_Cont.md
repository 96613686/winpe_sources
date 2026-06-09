# Marshal::WriteXml<Schema::Containers::Definition::NetworkNamespace,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::NetworkNamespace const &,Marshal::MarshalContext const &)

- ea: `0x1800180c4`
- end: `0x1800181f1`
- name: `??$WriteXml@UNetworkNamespace@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUNetworkNamespace@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800188c0`

## callees

- `0x18000bdc8`
- `0x1800180c4`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x1800181ab`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800181c5`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800181dc`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::NetworkNamespace,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::NetworkNamespace_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::NetworkNamespace_ClassData + 32;
  *(_QWORD *)v13 = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = &qword_180044118;
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
0x1800180c4  mov     [rsp+arg_0], rbx
0x1800180c9  mov     [rsp+arg_8], rsi
0x1800180ce  push    rdi
0x1800180cf  sub     rsp, 60h
0x1800180d3  mov     rsi, r9
0x1800180d6  mov     rbx, rdx
0x1800180d9  mov     rdi, rcx
0x1800180dc  test    r8b, r8b
0x1800180df  jnz     loc_1800181C0
0x1800180e5  test    rdx, rdx
0x1800180e8  jz      short loc_18001810C
0x1800180ea  mov     rcx, [rcx]
0x1800180ed  mov     r8, rdx
0x1800180f0  xor     r9d, r9d
0x1800180f3  xor     edx, edx
0x1800180f5  mov     rax, [rcx]
0x1800180f8  mov     rax, [rax+0D8h]
0x1800180ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018104  test    eax, eax
0x180018106  js      loc_1800181D7
0x18001810c  mov     rax, cs:?NetworkNamespace_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::NetworkNamespace_ClassData
0x180018113  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x18001811a  mov     r8, [rsp+68h+arg_20]
0x180018122  lea     r9, [rsp+68h+var_18]
0x180018127  mov     [rsp+68h+var_38], rcx
0x18001812c  mov     rdx, rsi
0x18001812f  mov     [rsp+68h+var_18], rax
0x180018134  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x18001813b  mov     [rsp+68h+var_30], rcx
0x180018140  add     rax, 20h ; ' '
0x180018144  mov     [rsp+68h+var_10], rax
0x180018149  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018150  mov     qword ptr [rsp+68h+var_28], rcx
0x180018155  lea     rax, [rsp+68h+var_38]
0x18001815a  mov     [rsp+68h+var_40], rax
0x18001815f  lea     rcx, qword_180044118
0x180018166  mov     [rsp+68h+var_20], rcx
0x18001816b  lea     rax, [rsp+68h+var_28]
0x180018170  mov     rcx, rdi
0x180018173  mov     qword ptr [rsp+68h+var_48], rax; int
0x180018178  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x18001817d  test    rbx, rbx
0x180018180  jz      short loc_180018195
0x180018182  mov     rcx, [rdi]
0x180018185  mov     rax, [rcx]
0x180018188  mov     rax, [rax+78h]
0x18001818c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018191  test    eax, eax
0x180018193  js      short loc_1800181A6
0x180018195  mov     rbx, [rsp+68h+arg_0]
0x18001819a  mov     rsi, [rsp+68h+arg_8]
0x18001819f  add     rsp, 60h
0x1800181a3  pop     rdi
0x1800181a4  retn
0x1800181a6  mov     rcx, [rsp+68h]; this
0x1800181ab  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800181b2  mov     r9d, eax; char *
0x1800181b5  mov     edx, 1EFh; void *
0x1800181ba  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800181c0  mov     rcx, [rsp+68h]; this
0x1800181c5  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800181cc  mov     edx, 1DFh; void *
0x1800181d1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800181d7  mov     rcx, [rsp+68h]; this
0x1800181dc  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800181e3  mov     r9d, eax; char *
0x1800181e6  mov     edx, 1E3h; void *
0x1800181eb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
