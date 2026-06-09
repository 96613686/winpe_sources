# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::RegistryRedirectionNode,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180019cc0`
- end: `0x180019def`
- name: `??$WriteXmlVoid@URegistryRedirectionNode@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000bdc8`
- `0x180019cc0`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180019da9`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019dc3`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019dda`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::RegistryRedirectionNode,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,unsigned int,bool,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::RegistryRedirectionNode_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Containers::Definition::InterfaceClassType,_GUID,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::RegistryRedirectionNode_ClassData + 192LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,unsigned int,bool,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x180019cc0  mov     [rsp+arg_0], rbx
0x180019cc5  mov     [rsp+arg_8], rsi
0x180019cca  push    rdi
0x180019ccb  sub     rsp, 60h
0x180019ccf  mov     rsi, r9
0x180019cd2  mov     rbx, rdx
0x180019cd5  mov     rdi, rcx
0x180019cd8  test    r8b, r8b
0x180019cdb  jnz     loc_180019DBE
0x180019ce1  test    rdx, rdx
0x180019ce4  jz      short loc_180019D08
0x180019ce6  mov     rcx, [rcx]
0x180019ce9  mov     r8, rdx
0x180019cec  xor     r9d, r9d
0x180019cef  xor     edx, edx
0x180019cf1  mov     rax, [rcx]
0x180019cf4  mov     rax, [rax+0D8h]
0x180019cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d00  test    eax, eax
0x180019d02  js      loc_180019DD5
0x180019d08  mov     rax, cs:?RegistryRedirectionNode_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::RegistryRedirectionNode_ClassData
0x180019d0f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@I_N_N@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$05@std@@A; std::array<Marshal::Details::XmlTypeData const *,6> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,uint,bool,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019d16  mov     r8, [rsp+68h+arg_20]
0x180019d1e  lea     r9, [rsp+68h+var_18]
0x180019d23  mov     [rsp+68h+var_38], rcx
0x180019d28  mov     rdx, rsi
0x180019d2b  mov     [rsp+68h+var_18], rax
0x180019d30  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4InterfaceClassType@Definition@Containers@Schema@@U_GUID@@_N@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::InterfaceClassType,_GUID,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019d37  mov     [rsp+68h+var_30], rcx
0x180019d3c  add     rax, 0C0h
0x180019d42  mov     [rsp+68h+var_10], rax
0x180019d47  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@I_N_N@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$05@std@@A; std::array<Marshal::Details::BaseTypeData const *,6> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,uint,bool,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180019d4e  mov     qword ptr [rsp+68h+var_28], rcx
0x180019d53  lea     rax, [rsp+68h+var_38]
0x180019d58  mov     [rsp+68h+var_40], rax
0x180019d5d  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::BaseTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180019d64  mov     [rsp+68h+var_20], rcx
0x180019d69  lea     rax, [rsp+68h+var_28]
0x180019d6e  mov     rcx, rdi
0x180019d71  mov     qword ptr [rsp+68h+var_48], rax; int
0x180019d76  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180019d7b  test    rbx, rbx
0x180019d7e  jz      short loc_180019D93
0x180019d80  mov     rcx, [rdi]
0x180019d83  mov     rax, [rcx]
0x180019d86  mov     rax, [rax+78h]
0x180019d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d8f  test    eax, eax
0x180019d91  js      short loc_180019DA4
0x180019d93  mov     rbx, [rsp+68h+arg_0]
0x180019d98  mov     rsi, [rsp+68h+arg_8]
0x180019d9d  add     rsp, 60h
0x180019da1  pop     rdi
0x180019da2  retn
0x180019da4  mov     rcx, [rsp+68h]; this
0x180019da9  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019db0  mov     r9d, eax; char *
0x180019db3  mov     edx, 1EFh; void *
0x180019db8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180019dbe  mov     rcx, [rsp+68h]; this
0x180019dc3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019dca  mov     edx, 1DFh; void *
0x180019dcf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180019dd5  mov     rcx, [rsp+68h]; this
0x180019dda  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019de1  mov     r9d, eax; char *
0x180019de4  mov     edx, 1E3h; void *
0x180019de9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
