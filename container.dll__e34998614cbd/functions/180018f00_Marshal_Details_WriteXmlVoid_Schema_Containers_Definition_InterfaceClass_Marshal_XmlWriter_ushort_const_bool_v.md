# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::InterfaceClass,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180018f00`
- end: `0x18001902d`
- name: `??$WriteXmlVoid@UInterfaceClass@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callees

- `0x18000bdc8`
- `0x180018f00`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180018fe7`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019001`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019018`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::InterfaceClass,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Containers::Definition::InterfaceClassType,_GUID,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::InterfaceClass_ClassData;
  v12[1] = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::InterfaceClass_ClassData + 96LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Containers::Definition::InterfaceClassType,_GUID,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,enum Schema::Containers::Definition::ObjectSymlinkScope,std::wstring,unsigned int>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x180018f00  mov     [rsp+arg_0], rbx
0x180018f05  mov     [rsp+arg_8], rsi
0x180018f0a  push    rdi
0x180018f0b  sub     rsp, 60h
0x180018f0f  mov     rsi, r9
0x180018f12  mov     rbx, rdx
0x180018f15  mov     rdi, rcx
0x180018f18  test    r8b, r8b
0x180018f1b  jnz     loc_180018FFC
0x180018f21  test    rdx, rdx
0x180018f24  jz      short loc_180018F48
0x180018f26  mov     rcx, [rcx]
0x180018f29  mov     r8, rdx
0x180018f2c  xor     r9d, r9d
0x180018f2f  xor     edx, edx
0x180018f31  mov     rax, [rcx]
0x180018f34  mov     rax, [rax+0D8h]
0x180018f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f40  test    eax, eax
0x180018f42  js      loc_180019013
0x180018f48  mov     rax, cs:?InterfaceClass_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::InterfaceClass_ClassData
0x180018f4f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4InterfaceClassType@Definition@Containers@Schema@@U_GUID@@_N@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::InterfaceClassType,_GUID,bool>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180018f56  mov     r8, [rsp+68h+arg_20]
0x180018f5e  lea     r9, [rsp+68h+var_18]
0x180018f63  mov     [rsp+68h+var_38], rcx
0x180018f68  mov     rdx, rsi
0x180018f6b  mov     [rsp+68h+var_18], rax
0x180018f70  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018f77  mov     [rsp+68h+var_30], rcx
0x180018f7c  add     rax, 60h ; '`'
0x180018f80  mov     [rsp+68h+var_10], rax
0x180018f85  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4InterfaceClassType@Definition@Containers@Schema@@U_GUID@@_N@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::BaseTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::InterfaceClassType,_GUID,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018f8c  mov     qword ptr [rsp+68h+var_28], rcx
0x180018f91  lea     rax, [rsp+68h+var_38]
0x180018f96  mov     [rsp+68h+var_40], rax
0x180018f9b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@W4ObjectSymlinkScope@Definition@Containers@Schema@@V12@I@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Schema::Containers::Definition::ObjectSymlinkScope,std::wstring,uint>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018fa2  mov     [rsp+68h+var_20], rcx
0x180018fa7  lea     rax, [rsp+68h+var_28]
0x180018fac  mov     rcx, rdi
0x180018faf  mov     qword ptr [rsp+68h+var_48], rax; int
0x180018fb4  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180018fb9  test    rbx, rbx
0x180018fbc  jz      short loc_180018FD1
0x180018fbe  mov     rcx, [rdi]
0x180018fc1  mov     rax, [rcx]
0x180018fc4  mov     rax, [rax+78h]
0x180018fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fcd  test    eax, eax
0x180018fcf  js      short loc_180018FE2
0x180018fd1  mov     rbx, [rsp+68h+arg_0]
0x180018fd6  mov     rsi, [rsp+68h+arg_8]
0x180018fdb  add     rsp, 60h
0x180018fdf  pop     rdi
0x180018fe0  retn
0x180018fe2  mov     rcx, [rsp+68h]; this
0x180018fe7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018fee  mov     r9d, eax; char *
0x180018ff1  mov     edx, 1EFh; void *
0x180018ff6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018ffc  mov     rcx, [rsp+68h]; this
0x180019001  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019008  mov     edx, 1DFh; void *
0x18001900d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180019013  mov     rcx, [rsp+68h]; this
0x180019018  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001901f  mov     r9d, eax; char *
0x180019022  mov     edx, 1E3h; void *
0x180019027  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
