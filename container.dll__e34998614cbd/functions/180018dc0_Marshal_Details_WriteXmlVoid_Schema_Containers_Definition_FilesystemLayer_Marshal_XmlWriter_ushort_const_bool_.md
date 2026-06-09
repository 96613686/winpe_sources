# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::FilesystemLayer,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180018dc0`
- end: `0x180018eed`
- name: `??$WriteXmlVoid@UFilesystemLayer@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callees

- `0x18000bdc8`
- `0x180018dc0`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180018ea7`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018ec1`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018ed8`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::FilesystemLayer,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<_GUID,std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::FilesystemLayer_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Containers::Definition::InterfaceClassType,_GUID,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::FilesystemLayer_ClassData + 64LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<_GUID,std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,enum Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x180018dc0  mov     [rsp+arg_0], rbx
0x180018dc5  mov     [rsp+arg_8], rsi
0x180018dca  push    rdi
0x180018dcb  sub     rsp, 60h
0x180018dcf  mov     rsi, r9
0x180018dd2  mov     rbx, rdx
0x180018dd5  mov     rdi, rcx
0x180018dd8  test    r8b, r8b
0x180018ddb  jnz     loc_180018EBC
0x180018de1  test    rdx, rdx
0x180018de4  jz      short loc_180018E08
0x180018de6  mov     rcx, [rcx]
0x180018de9  mov     r8, rdx
0x180018dec  xor     r9d, r9d
0x180018def  xor     edx, edx
0x180018df1  mov     rax, [rcx]
0x180018df4  mov     rax, [rax+0D8h]
0x180018dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e00  test    eax, eax
0x180018e02  js      loc_180018ED3
0x180018e08  mov     rax, cs:?FilesystemLayer_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::FilesystemLayer_ClassData
0x180018e0f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::XmlTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<_GUID,std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180018e16  mov     r8, [rsp+68h+arg_20]
0x180018e1e  lea     r9, [rsp+68h+var_18]
0x180018e23  mov     [rsp+68h+var_38], rcx
0x180018e28  mov     rdx, rsi
0x180018e2b  mov     [rsp+68h+var_18], rax
0x180018e30  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4InterfaceClassType@Definition@Containers@Schema@@U_GUID@@_N@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::BaseTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::InterfaceClassType,_GUID,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018e37  mov     [rsp+68h+var_30], rcx
0x180018e3c  add     rax, 40h ; '@'
0x180018e40  mov     [rsp+68h+var_10], rax
0x180018e45  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<_GUID,std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018e4c  mov     qword ptr [rsp+68h+var_28], rcx
0x180018e51  lea     rax, [rsp+68h+var_38]
0x180018e56  mov     [rsp+68h+var_40], rax
0x180018e5b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@W4ObjectDirectoryShadow@Definition@Containers@Schema@@U?$ModifiedType@V?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@8@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018e62  mov     [rsp+68h+var_20], rcx
0x180018e67  lea     rax, [rsp+68h+var_28]
0x180018e6c  mov     rcx, rdi
0x180018e6f  mov     qword ptr [rsp+68h+var_48], rax; int
0x180018e74  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180018e79  test    rbx, rbx
0x180018e7c  jz      short loc_180018E91
0x180018e7e  mov     rcx, [rdi]
0x180018e81  mov     rax, [rcx]
0x180018e84  mov     rax, [rax+78h]
0x180018e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e8d  test    eax, eax
0x180018e8f  js      short loc_180018EA2
0x180018e91  mov     rbx, [rsp+68h+arg_0]
0x180018e96  mov     rsi, [rsp+68h+arg_8]
0x180018e9b  add     rsp, 60h
0x180018e9f  pop     rdi
0x180018ea0  retn
0x180018ea2  mov     rcx, [rsp+68h]; this
0x180018ea7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018eae  mov     r9d, eax; char *
0x180018eb1  mov     edx, 1EFh; void *
0x180018eb6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018ebc  mov     rcx, [rsp+68h]; this
0x180018ec1  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018ec8  mov     edx, 1DFh; void *
0x180018ecd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180018ed3  mov     rcx, [rsp+68h]; this
0x180018ed8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018edf  mov     r9d, eax; char *
0x180018ee2  mov     edx, 1E3h; void *
0x180018ee7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
