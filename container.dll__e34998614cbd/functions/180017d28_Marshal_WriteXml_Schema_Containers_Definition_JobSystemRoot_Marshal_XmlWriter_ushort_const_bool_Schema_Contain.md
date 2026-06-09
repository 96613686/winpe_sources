# Marshal::WriteXml<Schema::Containers::Definition::JobSystemRoot,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::JobSystemRoot const &,Marshal::MarshalContext const &)

- ea: `0x180017d28`
- end: `0x180017e55`
- name: `??$WriteXml@UJobSystemRoot@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUJobSystemRoot@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018830`

## callees

- `0x18000bdc8`
- `0x180017d28`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180017e0f`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017e29`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017e40`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::JobSystemRoot,>(
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
  v15[0] = Schema::Containers::Definition::JobSystemRoot_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::JobSystemRoot_ClassData + 32;
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
0x180017d28  mov     [rsp+arg_0], rbx
0x180017d2d  mov     [rsp+arg_8], rsi
0x180017d32  push    rdi
0x180017d33  sub     rsp, 60h
0x180017d37  mov     rsi, r9
0x180017d3a  mov     rbx, rdx
0x180017d3d  mov     rdi, rcx
0x180017d40  test    r8b, r8b
0x180017d43  jnz     loc_180017E24
0x180017d49  test    rdx, rdx
0x180017d4c  jz      short loc_180017D70
0x180017d4e  mov     rcx, [rcx]
0x180017d51  mov     r8, rdx
0x180017d54  xor     r9d, r9d
0x180017d57  xor     edx, edx
0x180017d59  mov     rax, [rcx]
0x180017d5c  mov     rax, [rax+0D8h]
0x180017d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d68  test    eax, eax
0x180017d6a  js      loc_180017E3B
0x180017d70  mov     rax, cs:?JobSystemRoot_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::JobSystemRoot_ClassData
0x180017d77  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180017d7e  mov     r8, [rsp+68h+arg_20]
0x180017d86  lea     r9, [rsp+68h+var_18]
0x180017d8b  mov     [rsp+68h+var_38], rcx
0x180017d90  mov     rdx, rsi
0x180017d93  mov     [rsp+68h+var_18], rax
0x180017d98  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180017d9f  mov     [rsp+68h+var_30], rcx
0x180017da4  add     rax, 20h ; ' '
0x180017da8  mov     [rsp+68h+var_10], rax
0x180017dad  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017db4  mov     qword ptr [rsp+68h+var_28], rcx
0x180017db9  lea     rax, [rsp+68h+var_38]
0x180017dbe  mov     [rsp+68h+var_40], rax
0x180017dc3  lea     rcx, qword_180044118
0x180017dca  mov     [rsp+68h+var_20], rcx
0x180017dcf  lea     rax, [rsp+68h+var_28]
0x180017dd4  mov     rcx, rdi
0x180017dd7  mov     qword ptr [rsp+68h+var_48], rax; int
0x180017ddc  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180017de1  test    rbx, rbx
0x180017de4  jz      short loc_180017DF9
0x180017de6  mov     rcx, [rdi]
0x180017de9  mov     rax, [rcx]
0x180017dec  mov     rax, [rax+78h]
0x180017df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017df5  test    eax, eax
0x180017df7  js      short loc_180017E0A
0x180017df9  mov     rbx, [rsp+68h+arg_0]
0x180017dfe  mov     rsi, [rsp+68h+arg_8]
0x180017e03  add     rsp, 60h
0x180017e07  pop     rdi
0x180017e08  retn
0x180017e0a  mov     rcx, [rsp+68h]; this
0x180017e0f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017e16  mov     r9d, eax; char *
0x180017e19  mov     edx, 1EFh; void *
0x180017e1e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017e24  mov     rcx, [rsp+68h]; this
0x180017e29  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017e30  mov     edx, 1DFh; void *
0x180017e35  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180017e3b  mov     rcx, [rsp+68h]; this
0x180017e40  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017e47  mov     r9d, eax; char *
0x180017e4a  mov     edx, 1E3h; void *
0x180017e4f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
