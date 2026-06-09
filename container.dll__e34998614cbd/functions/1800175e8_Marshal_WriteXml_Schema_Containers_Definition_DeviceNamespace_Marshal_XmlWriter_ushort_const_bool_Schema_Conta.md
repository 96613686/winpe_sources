# Marshal::WriteXml<Schema::Containers::Definition::DeviceNamespace,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::DeviceNamespace const &,Marshal::MarshalContext const &)

- ea: `0x1800175e8`
- end: `0x180017715`
- name: `??$WriteXml@UDeviceNamespace@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUDeviceNamespace@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x180018710`

## callees

- `0x18000bdc8`
- `0x1800175e8`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x1800176cf`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x1800176e9`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017700`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::DeviceNamespace,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<bool,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceCategory>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceInstance>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::DeviceNamespace_ClassData;
  v12[1] = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::MountManagerMountPoint>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::DeviceNamespace_ClassData + 96;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<bool,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceCategory>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceInstance>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,_GUID,bool,bool,bool,bool,bool,unsigned __int64>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x1800175e8  mov     [rsp+arg_0], rbx
0x1800175ed  mov     [rsp+arg_8], rsi
0x1800175f2  push    rdi
0x1800175f3  sub     rsp, 60h
0x1800175f7  mov     rsi, r9
0x1800175fa  mov     rbx, rdx
0x1800175fd  mov     rdi, rcx
0x180017600  test    r8b, r8b
0x180017603  jnz     loc_1800176E4
0x180017609  test    rdx, rdx
0x18001760c  jz      short loc_180017630
0x18001760e  mov     rcx, [rcx]
0x180017611  mov     r8, rdx
0x180017614  xor     r9d, r9d
0x180017617  xor     edx, edx
0x180017619  mov     rax, [rcx]
0x18001761c  mov     rax, [rax+0D8h]
0x180017623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017628  test    eax, eax
0x18001762a  js      loc_1800176FB
0x180017630  mov     rax, cs:?DeviceNamespace_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::DeviceNamespace_ClassData
0x180017637  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@_NU?$ModifiedType@V?$vector@UDeviceCategory@Definition@Containers@Schema@@V?$allocator@UDeviceCategory@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UDeviceInstance@Definition@Containers@Schema@@V?$allocator@UDeviceInstance@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<bool,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceCategory>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceInstance>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x18001763e  mov     r8, [rsp+68h+arg_20]
0x180017646  lea     r9, [rsp+68h+var_18]
0x18001764b  mov     [rsp+68h+var_38], rcx
0x180017650  mov     rdx, rsi
0x180017653  mov     [rsp+68h+var_18], rax
0x180017658  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::MountManagerMountPoint>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x18001765f  mov     [rsp+68h+var_30], rcx
0x180017664  add     rax, 60h ; '`'
0x180017668  mov     [rsp+68h+var_10], rax
0x18001766d  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@_NU?$ModifiedType@V?$vector@UDeviceCategory@Definition@Containers@Schema@@V?$allocator@UDeviceCategory@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UDeviceInstance@Definition@Containers@Schema@@V?$allocator@UDeviceInstance@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::BaseTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<bool,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceCategory>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::DeviceInstance>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017674  mov     qword ptr [rsp+68h+var_28], rcx
0x180017679  lea     rax, [rsp+68h+var_38]
0x18001767e  mov     [rsp+68h+var_40], rax
0x180017683  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U_GUID@@_N_N_N_N_N_K@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$08@std@@A; std::array<Marshal::Details::BaseTypeData const *,9> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,_GUID,bool,bool,bool,bool,bool,unsigned __int64>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x18001768a  mov     [rsp+68h+var_20], rcx
0x18001768f  lea     rax, [rsp+68h+var_28]
0x180017694  mov     rcx, rdi
0x180017697  mov     qword ptr [rsp+68h+var_48], rax; int
0x18001769c  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x1800176a1  test    rbx, rbx
0x1800176a4  jz      short loc_1800176B9
0x1800176a6  mov     rcx, [rdi]
0x1800176a9  mov     rax, [rcx]
0x1800176ac  mov     rax, [rax+78h]
0x1800176b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176b5  test    eax, eax
0x1800176b7  js      short loc_1800176CA
0x1800176b9  mov     rbx, [rsp+68h+arg_0]
0x1800176be  mov     rsi, [rsp+68h+arg_8]
0x1800176c3  add     rsp, 60h
0x1800176c7  pop     rdi
0x1800176c8  retn
0x1800176ca  mov     rcx, [rsp+68h]; this
0x1800176cf  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800176d6  mov     r9d, eax; char *
0x1800176d9  mov     edx, 1EFh; void *
0x1800176de  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800176e4  mov     rcx, [rsp+68h]; this
0x1800176e9  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800176f0  mov     edx, 1DFh; void *
0x1800176f5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800176fb  mov     rcx, [rsp+68h]; this
0x180017700  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017707  mov     r9d, eax; char *
0x18001770a  mov     edx, 1E3h; void *
0x18001770f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
