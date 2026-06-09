# Marshal::WriteXml<Schema::Containers::Definition::MountManagerNamespace,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::MountManagerNamespace const &,Marshal::MarshalContext const &)

- ea: `0x180017e5c`
- end: `0x180017f89`
- name: `??$WriteXml@UMountManagerNamespace@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUMountManagerNamespace@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x180018860`

## callees

- `0x18000bdc8`
- `0x180017e5c`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180017f43`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017f5d`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017f74`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::MountManagerNamespace,>(
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
  v12[0] = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::MountManagerMountPoint>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::MountManagerNamespace_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistrySymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryRedirectionNode>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryHiveStack>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::MountManagerNamespace_ClassData + 32;
  *(_QWORD *)v13 = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::MountManagerMountPoint>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
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
0x180017e5c  mov     [rsp+arg_0], rbx
0x180017e61  mov     [rsp+arg_8], rsi
0x180017e66  push    rdi
0x180017e67  sub     rsp, 60h
0x180017e6b  mov     rsi, r9
0x180017e6e  mov     rbx, rdx
0x180017e71  mov     rdi, rcx
0x180017e74  test    r8b, r8b
0x180017e77  jnz     loc_180017F58
0x180017e7d  test    rdx, rdx
0x180017e80  jz      short loc_180017EA4
0x180017e82  mov     rcx, [rcx]
0x180017e85  mov     r8, rdx
0x180017e88  xor     r9d, r9d
0x180017e8b  xor     edx, edx
0x180017e8d  mov     rax, [rcx]
0x180017e90  mov     rax, [rax+0D8h]
0x180017e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e9c  test    eax, eax
0x180017e9e  js      loc_180017F6F
0x180017ea4  mov     rax, cs:?MountManagerNamespace_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::MountManagerNamespace_ClassData
0x180017eab  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::MountManagerMountPoint>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180017eb2  mov     r8, [rsp+68h+arg_20]
0x180017eba  lea     r9, [rsp+68h+var_18]
0x180017ebf  mov     [rsp+68h+var_38], rcx
0x180017ec4  mov     rdx, rsi
0x180017ec7  mov     [rsp+68h+var_18], rax
0x180017ecc  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@URegistrySymlink@Definition@Containers@Schema@@V?$allocator@URegistrySymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryRedirectionNode@Definition@Containers@Schema@@V?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@V?$vector@URegistryHiveStack@Definition@Containers@Schema@@V?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::BaseTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistrySymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryRedirectionNode>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryHiveStack>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017ed3  mov     [rsp+68h+var_30], rcx
0x180017ed8  add     rax, 20h ; ' '
0x180017edc  mov     [rsp+68h+var_10], rax
0x180017ee1  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::MountManagerMountPoint>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017ee8  mov     qword ptr [rsp+68h+var_28], rcx
0x180017eed  lea     rax, [rsp+68h+var_38]
0x180017ef2  mov     [rsp+68h+var_40], rax
0x180017ef7  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@UInterfaceClass@Definition@Containers@Schema@@V?$allocator@UInterfaceClass@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::XmlTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::InterfaceClass>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180017efe  mov     [rsp+68h+var_20], rcx
0x180017f03  lea     rax, [rsp+68h+var_28]
0x180017f08  mov     rcx, rdi
0x180017f0b  mov     qword ptr [rsp+68h+var_48], rax; int
0x180017f10  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180017f15  test    rbx, rbx
0x180017f18  jz      short loc_180017F2D
0x180017f1a  mov     rcx, [rdi]
0x180017f1d  mov     rax, [rcx]
0x180017f20  mov     rax, [rax+78h]
0x180017f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f29  test    eax, eax
0x180017f2b  js      short loc_180017F3E
0x180017f2d  mov     rbx, [rsp+68h+arg_0]
0x180017f32  mov     rsi, [rsp+68h+arg_8]
0x180017f37  add     rsp, 60h
0x180017f3b  pop     rdi
0x180017f3c  retn
0x180017f3e  mov     rcx, [rsp+68h]; this
0x180017f43  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017f4a  mov     r9d, eax; char *
0x180017f4d  mov     edx, 1EFh; void *
0x180017f52  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017f58  mov     rcx, [rsp+68h]; this
0x180017f5d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017f64  mov     edx, 1DFh; void *
0x180017f69  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180017f6f  mov     rcx, [rsp+68h]; this
0x180017f74  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017f7b  mov     r9d, eax; char *
0x180017f7e  mov     edx, 1E3h; void *
0x180017f83  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
