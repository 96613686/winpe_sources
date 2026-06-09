# Marshal::WriteXml<Schema::Containers::Definition::HostFiles,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::HostFiles const &,Marshal::MarshalContext const &)

- ea: `0x180017854`
- end: `0x180017981`
- name: `??$WriteXml@UHostFiles@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUHostFiles@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018770`

## callees

- `0x18000bdc8`
- `0x180017854`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x18001793b`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017955`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x18001796c`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::HostFiles,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::HostFiles_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,unsigned int,bool,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::HostFiles_ClassData + 96;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<bool,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceCategory>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceInstance>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x180017854  mov     [rsp+arg_0], rbx
0x180017859  mov     [rsp+arg_8], rsi
0x18001785e  push    rdi
0x18001785f  sub     rsp, 60h
0x180017863  mov     rsi, r9
0x180017866  mov     rbx, rdx
0x180017869  mov     rdi, rcx
0x18001786c  test    r8b, r8b
0x18001786f  jnz     loc_180017950
0x180017875  test    rdx, rdx
0x180017878  jz      short loc_18001789C
0x18001787a  mov     rcx, [rcx]
0x18001787d  mov     r8, rdx
0x180017880  xor     r9d, r9d
0x180017883  xor     edx, edx
0x180017885  mov     rax, [rcx]
0x180017888  mov     rax, [rax+0D8h]
0x18001788f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017894  test    eax, eax
0x180017896  js      loc_180017967
0x18001789c  mov     rax, cs:?HostFiles_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::HostFiles_ClassData
0x1800178a3  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800178aa  mov     r8, [rsp+68h+arg_20]
0x1800178b2  lea     r9, [rsp+68h+var_18]
0x1800178b7  mov     [rsp+68h+var_38], rcx
0x1800178bc  mov     rdx, rsi
0x1800178bf  mov     [rsp+68h+var_18], rax
0x1800178c4  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@I_N_N@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$05@std@@A; std::array<Marshal::Details::XmlTypeData const *,6> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,uint,bool,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800178cb  mov     [rsp+68h+var_30], rcx
0x1800178d0  add     rax, 60h ; '`'
0x1800178d4  mov     [rsp+68h+var_10], rax
0x1800178d9  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::BaseTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800178e0  mov     qword ptr [rsp+68h+var_28], rcx
0x1800178e5  lea     rax, [rsp+68h+var_38]
0x1800178ea  mov     [rsp+68h+var_40], rax
0x1800178ef  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@_NU?$ModifiedType@V?$vector@UDeviceCategory@Definition@Containers@Schema@@V?$allocator@UDeviceCategory@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UDeviceInstance@Definition@Containers@Schema@@V?$allocator@UDeviceInstance@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::BaseTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<bool,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceCategory>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceInstance>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800178f6  mov     [rsp+68h+var_20], rcx
0x1800178fb  lea     rax, [rsp+68h+var_28]
0x180017900  mov     rcx, rdi
0x180017903  mov     qword ptr [rsp+68h+var_48], rax; int
0x180017908  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x18001790d  test    rbx, rbx
0x180017910  jz      short loc_180017925
0x180017912  mov     rcx, [rdi]
0x180017915  mov     rax, [rcx]
0x180017918  mov     rax, [rax+78h]
0x18001791c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017921  test    eax, eax
0x180017923  js      short loc_180017936
0x180017925  mov     rbx, [rsp+68h+arg_0]
0x18001792a  mov     rsi, [rsp+68h+arg_8]
0x18001792f  add     rsp, 60h
0x180017933  pop     rdi
0x180017934  retn
0x180017936  mov     rcx, [rsp+68h]; this
0x18001793b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017942  mov     r9d, eax; char *
0x180017945  mov     edx, 1EFh; void *
0x18001794a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017950  mov     rcx, [rsp+68h]; this
0x180017955  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001795c  mov     edx, 1DFh; void *
0x180017961  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180017967  mov     rcx, [rsp+68h]; this
0x18001796c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017973  mov     r9d, eax; char *
0x180017976  mov     edx, 1E3h; void *
0x18001797b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
