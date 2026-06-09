# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::NamedPipeSymlink,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180019180`
- end: `0x1800192ad`
- name: `??$WriteXmlVoid@UNamedPipeSymlink@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callees

- `0x18000bdc8`
- `0x180019180`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180019267`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019281`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019298`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::NamedPipeSymlink,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::NamedPipeSymlink_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::NamedPipeSymlink_ClassData + 64LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::MountManagerMountPoint>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
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
0x180019180  mov     [rsp+arg_0], rbx
0x180019185  mov     [rsp+arg_8], rsi
0x18001918a  push    rdi
0x18001918b  sub     rsp, 60h
0x18001918f  mov     rsi, r9
0x180019192  mov     rbx, rdx
0x180019195  mov     rdi, rcx
0x180019198  test    r8b, r8b
0x18001919b  jnz     loc_18001927C
0x1800191a1  test    rdx, rdx
0x1800191a4  jz      short loc_1800191C8
0x1800191a6  mov     rcx, [rcx]
0x1800191a9  mov     r8, rdx
0x1800191ac  xor     r9d, r9d
0x1800191af  xor     edx, edx
0x1800191b1  mov     rax, [rcx]
0x1800191b4  mov     rax, [rax+0D8h]
0x1800191bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191c0  test    eax, eax
0x1800191c2  js      loc_180019293
0x1800191c8  mov     rax, cs:?NamedPipeSymlink_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::NamedPipeSymlink_ClassData
0x1800191cf  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::XmlTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800191d6  mov     r8, [rsp+68h+arg_20]
0x1800191de  lea     r9, [rsp+68h+var_18]
0x1800191e3  mov     [rsp+68h+var_38], rcx
0x1800191e8  mov     rdx, rsi
0x1800191eb  mov     [rsp+68h+var_18], rax
0x1800191f0  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800191f7  mov     [rsp+68h+var_30], rcx
0x1800191fc  add     rax, 40h ; '@'
0x180019200  mov     [rsp+68h+var_10], rax
0x180019205  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x18001920c  mov     qword ptr [rsp+68h+var_28], rcx
0x180019211  lea     rax, [rsp+68h+var_38]
0x180019216  mov     [rsp+68h+var_40], rax
0x18001921b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::MountManagerMountPoint>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019222  mov     [rsp+68h+var_20], rcx
0x180019227  lea     rax, [rsp+68h+var_28]
0x18001922c  mov     rcx, rdi
0x18001922f  mov     qword ptr [rsp+68h+var_48], rax; int
0x180019234  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180019239  test    rbx, rbx
0x18001923c  jz      short loc_180019251
0x18001923e  mov     rcx, [rdi]
0x180019241  mov     rax, [rcx]
0x180019244  mov     rax, [rax+78h]
0x180019248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001924d  test    eax, eax
0x18001924f  js      short loc_180019262
0x180019251  mov     rbx, [rsp+68h+arg_0]
0x180019256  mov     rsi, [rsp+68h+arg_8]
0x18001925b  add     rsp, 60h
0x18001925f  pop     rdi
0x180019260  retn
0x180019262  mov     rcx, [rsp+68h]; this
0x180019267  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001926e  mov     r9d, eax; char *
0x180019271  mov     edx, 1EFh; void *
0x180019276  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001927c  mov     rcx, [rsp+68h]; this
0x180019281  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019288  mov     edx, 1DFh; void *
0x18001928d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180019293  mov     rcx, [rsp+68h]; this
0x180019298  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001929f  mov     r9d, eax; char *
0x1800192a2  mov     edx, 1E3h; void *
0x1800192a7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
