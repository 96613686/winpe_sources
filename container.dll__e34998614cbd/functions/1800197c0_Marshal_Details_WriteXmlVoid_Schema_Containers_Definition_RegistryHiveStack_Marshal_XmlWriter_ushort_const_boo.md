# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::RegistryHiveStack,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x1800197c0`
- end: `0x1800198ed`
- name: `??$WriteXmlVoid@URegistryHiveStack@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000bdc8`
- `0x1800197c0`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x1800198a7`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800198c1`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800198d8`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::RegistryHiveStack,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryDeleteKey>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::RegistryHiveStack_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,enum Schema::Containers::Definition::FilesystemIsolationMode,enum Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::RegistryHiveStack_ClassData + 128LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryDeleteKey>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
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
0x1800197c0  mov     [rsp+arg_0], rbx
0x1800197c5  mov     [rsp+arg_8], rsi
0x1800197ca  push    rdi
0x1800197cb  sub     rsp, 60h
0x1800197cf  mov     rsi, r9
0x1800197d2  mov     rbx, rdx
0x1800197d5  mov     rdi, rcx
0x1800197d8  test    r8b, r8b
0x1800197db  jnz     loc_1800198BC
0x1800197e1  test    rdx, rdx
0x1800197e4  jz      short loc_180019808
0x1800197e6  mov     rcx, [rcx]
0x1800197e9  mov     r8, rdx
0x1800197ec  xor     r9d, r9d
0x1800197ef  xor     edx, edx
0x1800197f1  mov     rax, [rcx]
0x1800197f4  mov     rax, [rax+0D8h]
0x1800197fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019800  test    eax, eax
0x180019802  js      loc_1800198D3
0x180019808  mov     rax, cs:?RegistryHiveStack_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::RegistryHiveStack_ClassData
0x18001980f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@U?$ModifiedType@V?$vector@URegistryDeleteKey@Definition@Containers@Schema@@V?$allocator@URegistryDeleteKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::XmlTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryDeleteKey>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019816  mov     r8, [rsp+68h+arg_20]
0x18001981e  lea     r9, [rsp+68h+var_18]
0x180019823  mov     [rsp+68h+var_38], rcx
0x180019828  mov     rdx, rsi
0x18001982b  mov     [rsp+68h+var_18], rax
0x180019830  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FilesystemIsolationMode@Definition@Containers@Schema@@W4FilesystemNestingMode@456@U?$ModifiedType@V?$vector@UFilesystemLayer@Definition@Containers@Schema@@V?$allocator@UFilesystemLayer@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UBatchedBinding@Definition@Containers@Schema@@V?$allocator@UBatchedBinding@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@9@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Schema::Containers::Definition::FilesystemIsolationMode,Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019837  mov     [rsp+68h+var_30], rcx
0x18001983c  sub     rax, 0FFFFFFFFFFFFFF80h
0x180019840  mov     [rsp+68h+var_10], rax
0x180019845  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@U?$ModifiedType@V?$vector@URegistryDeleteKey@Definition@Containers@Schema@@V?$allocator@URegistryDeleteKey@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@4@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::BaseTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryMakeKey>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryDeleteKey>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x18001984c  mov     qword ptr [rsp+68h+var_28], rcx
0x180019851  lea     rax, [rsp+68h+var_38]
0x180019856  mov     [rsp+68h+var_40], rax
0x18001985b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::XmlTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019862  mov     [rsp+68h+var_20], rcx
0x180019867  lea     rax, [rsp+68h+var_28]
0x18001986c  mov     rcx, rdi
0x18001986f  mov     qword ptr [rsp+68h+var_48], rax; int
0x180019874  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180019879  test    rbx, rbx
0x18001987c  jz      short loc_180019891
0x18001987e  mov     rcx, [rdi]
0x180019881  mov     rax, [rcx]
0x180019884  mov     rax, [rax+78h]
0x180019888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001988d  test    eax, eax
0x18001988f  js      short loc_1800198A2
0x180019891  mov     rbx, [rsp+68h+arg_0]
0x180019896  mov     rsi, [rsp+68h+arg_8]
0x18001989b  add     rsp, 60h
0x18001989f  pop     rdi
0x1800198a0  retn
0x1800198a2  mov     rcx, [rsp+68h]; this
0x1800198a7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800198ae  mov     r9d, eax; char *
0x1800198b1  mov     edx, 1EFh; void *
0x1800198b6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800198bc  mov     rcx, [rsp+68h]; this
0x1800198c1  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800198c8  mov     edx, 1DFh; void *
0x1800198cd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800198d3  mov     rcx, [rsp+68h]; this
0x1800198d8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800198df  mov     r9d, eax; char *
0x1800198e2  mov     edx, 1E3h; void *
0x1800198e7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
