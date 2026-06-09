# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::BatchedBinding,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180018a00`
- end: `0x180018b2d`
- name: `??$WriteXmlVoid@UBatchedBinding@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callees

- `0x18000bdc8`
- `0x180018a00`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180018ae7`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018b01`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180018b18`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::BatchedBinding,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::BatchedBinding_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<unsigned int,unsigned int>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::BatchedBinding_ClassData + 64LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x180018a00  mov     [rsp+arg_0], rbx
0x180018a05  mov     [rsp+arg_8], rsi
0x180018a0a  push    rdi
0x180018a0b  sub     rsp, 60h
0x180018a0f  mov     rsi, r9
0x180018a12  mov     rbx, rdx
0x180018a15  mov     rdi, rcx
0x180018a18  test    r8b, r8b
0x180018a1b  jnz     loc_180018AFC
0x180018a21  test    rdx, rdx
0x180018a24  jz      short loc_180018A48
0x180018a26  mov     rcx, [rcx]
0x180018a29  mov     r8, rdx
0x180018a2c  xor     r9d, r9d
0x180018a2f  xor     edx, edx
0x180018a31  mov     rax, [rcx]
0x180018a34  mov     rax, [rax+0D8h]
0x180018a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a40  test    eax, eax
0x180018a42  js      loc_180018B13
0x180018a48  mov     rax, cs:?BatchedBinding_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::BatchedBinding_ClassData
0x180018a4f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::XmlTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180018a56  mov     r8, [rsp+68h+arg_20]
0x180018a5e  lea     r9, [rsp+68h+var_18]
0x180018a63  mov     [rsp+68h+var_38], rcx
0x180018a68  mov     rdx, rsi
0x180018a6b  mov     [rsp+68h+var_18], rax
0x180018a70  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@II@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::XmlTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<uint,uint>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180018a77  mov     [rsp+68h+var_30], rcx
0x180018a7c  add     rax, 40h ; '@'
0x180018a80  mov     [rsp+68h+var_10], rax
0x180018a85  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018a8c  mov     qword ptr [rsp+68h+var_28], rcx
0x180018a91  lea     rax, [rsp+68h+var_38]
0x180018a96  mov     [rsp+68h+var_40], rax
0x180018a9b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4ObjectDirectoryShadow@Definition@Containers@Schema@@U?$ModifiedType@V?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@6@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::BaseTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180018aa2  mov     [rsp+68h+var_20], rcx
0x180018aa7  lea     rax, [rsp+68h+var_28]
0x180018aac  mov     rcx, rdi
0x180018aaf  mov     qword ptr [rsp+68h+var_48], rax; int
0x180018ab4  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180018ab9  test    rbx, rbx
0x180018abc  jz      short loc_180018AD1
0x180018abe  mov     rcx, [rdi]
0x180018ac1  mov     rax, [rcx]
0x180018ac4  mov     rax, [rax+78h]
0x180018ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018acd  test    eax, eax
0x180018acf  js      short loc_180018AE2
0x180018ad1  mov     rbx, [rsp+68h+arg_0]
0x180018ad6  mov     rsi, [rsp+68h+arg_8]
0x180018adb  add     rsp, 60h
0x180018adf  pop     rdi
0x180018ae0  retn
0x180018ae2  mov     rcx, [rsp+68h]; this
0x180018ae7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018aee  mov     r9d, eax; char *
0x180018af1  mov     edx, 1EFh; void *
0x180018af6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018afc  mov     rcx, [rsp+68h]; this
0x180018b01  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018b08  mov     edx, 1DFh; void *
0x180018b0d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180018b13  mov     rcx, [rsp+68h]; this
0x180018b18  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180018b1f  mov     r9d, eax; char *
0x180018b22  mov     edx, 1E3h; void *
0x180018b27  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
