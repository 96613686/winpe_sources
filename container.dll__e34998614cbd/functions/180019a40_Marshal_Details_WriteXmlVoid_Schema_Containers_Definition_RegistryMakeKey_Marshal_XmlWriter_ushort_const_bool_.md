# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::RegistryMakeKey,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180019a40`
- end: `0x180019b6f`
- name: `??$WriteXmlVoid@URegistryMakeKey@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000bdc8`
- `0x180019a40`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180019b29`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019b43`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019b5a`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::RegistryMakeKey,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeValue>,Marshal::ModifierList<>>,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::RegistryMakeKey_ClassData;
  v12[1] = &wil::details::g_featureStateManager;
  v15[1] = Schema::Containers::Definition::RegistryMakeKey_ClassData + 160LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeValue>,Marshal::ModifierList<>>,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<bool,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceCategory>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceInstance>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
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
0x180019a40  mov     [rsp+arg_0], rbx
0x180019a45  mov     [rsp+arg_8], rsi
0x180019a4a  push    rdi
0x180019a4b  sub     rsp, 60h
0x180019a4f  mov     rsi, r9
0x180019a52  mov     rbx, rdx
0x180019a55  mov     rdi, rcx
0x180019a58  test    r8b, r8b
0x180019a5b  jnz     loc_180019B3E
0x180019a61  test    rdx, rdx
0x180019a64  jz      short loc_180019A88
0x180019a66  mov     rcx, [rcx]
0x180019a69  mov     r8, rdx
0x180019a6c  xor     r9d, r9d
0x180019a6f  xor     edx, edx
0x180019a71  mov     rax, [rcx]
0x180019a74  mov     rax, [rax+0D8h]
0x180019a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a80  test    eax, eax
0x180019a82  js      loc_180019B55
0x180019a88  mov     rax, cs:?RegistryMakeKey_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::RegistryMakeKey_ClassData
0x180019a8f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@_N@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeValue>,Marshal::ModifierList<>>,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019a96  mov     r8, [rsp+68h+arg_20]
0x180019a9e  lea     r9, [rsp+68h+var_18]
0x180019aa3  mov     [rsp+68h+var_38], rcx
0x180019aa8  mov     rdx, rsi
0x180019aab  mov     [rsp+68h+var_18], rax
0x180019ab0  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180019ab7  mov     [rsp+68h+var_30], rcx
0x180019abc  add     rax, 0A0h
0x180019ac2  mov     [rsp+68h+var_10], rax
0x180019ac7  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@_N@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeValue>,Marshal::ModifierList<>>,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180019ace  mov     qword ptr [rsp+68h+var_28], rcx
0x180019ad3  lea     rax, [rsp+68h+var_38]
0x180019ad8  mov     [rsp+68h+var_40], rax
0x180019add  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@_NU?$ModifiedType@V?$vector@UDeviceCategory@Definition@Containers@Schema@@V?$allocator@UDeviceCategory@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UDeviceInstance@Definition@Containers@Schema@@V?$allocator@UDeviceInstance@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<bool,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceCategory>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceInstance>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019ae4  mov     [rsp+68h+var_20], rcx
0x180019ae9  lea     rax, [rsp+68h+var_28]
0x180019aee  mov     rcx, rdi
0x180019af1  mov     qword ptr [rsp+68h+var_48], rax; int
0x180019af6  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180019afb  test    rbx, rbx
0x180019afe  jz      short loc_180019B13
0x180019b00  mov     rcx, [rdi]
0x180019b03  mov     rax, [rcx]
0x180019b06  mov     rax, [rax+78h]
0x180019b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b0f  test    eax, eax
0x180019b11  js      short loc_180019B24
0x180019b13  mov     rbx, [rsp+68h+arg_0]
0x180019b18  mov     rsi, [rsp+68h+arg_8]
0x180019b1d  add     rsp, 60h
0x180019b21  pop     rdi
0x180019b22  retn
0x180019b24  mov     rcx, [rsp+68h]; this
0x180019b29  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019b30  mov     r9d, eax; char *
0x180019b33  mov     edx, 1EFh; void *
0x180019b38  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180019b3e  mov     rcx, [rsp+68h]; this
0x180019b43  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019b4a  mov     edx, 1DFh; void *
0x180019b4f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180019b55  mov     rcx, [rsp+68h]; this
0x180019b5a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019b61  mov     r9d, eax; char *
0x180019b64  mov     edx, 1E3h; void *
0x180019b69  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
