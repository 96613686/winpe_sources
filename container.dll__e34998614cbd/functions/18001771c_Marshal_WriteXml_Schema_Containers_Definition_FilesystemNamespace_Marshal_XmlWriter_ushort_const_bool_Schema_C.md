# Marshal::WriteXml<Schema::Containers::Definition::FilesystemNamespace,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::FilesystemNamespace const &,Marshal::MarshalContext const &)

- ea: `0x18001771c`
- end: `0x18001784b`
- name: `??$WriteXml@UFilesystemNamespace@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUFilesystemNamespace@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x180018740`

## callees

- `0x18000bdc8`
- `0x18001771c`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180017805`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x18001781f`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017836`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::FilesystemNamespace,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,enum Schema::Containers::Definition::FilesystemIsolationMode,enum Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::FilesystemNamespace_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::NamedPipeSymlink>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::FilesystemNamespace_ClassData + 160;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,enum Schema::Containers::Definition::FilesystemIsolationMode,enum Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::FilesystemNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::MountManagerNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::NamedPipeNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::ObjectNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::RegistryNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::NetworkNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::DeviceNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::HostFiles>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
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
0x18001771c  mov     [rsp+arg_0], rbx
0x180017721  mov     [rsp+arg_8], rsi
0x180017726  push    rdi
0x180017727  sub     rsp, 60h
0x18001772b  mov     rsi, r9
0x18001772e  mov     rbx, rdx
0x180017731  mov     rdi, rcx
0x180017734  test    r8b, r8b
0x180017737  jnz     loc_18001781A
0x18001773d  test    rdx, rdx
0x180017740  jz      short loc_180017764
0x180017742  mov     rcx, [rcx]
0x180017745  mov     r8, rdx
0x180017748  xor     r9d, r9d
0x18001774b  xor     edx, edx
0x18001774d  mov     rax, [rcx]
0x180017750  mov     rax, [rax+0D8h]
0x180017757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001775c  test    eax, eax
0x18001775e  js      loc_180017831
0x180017764  mov     rax, cs:?FilesystemNamespace_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::FilesystemNamespace_ClassData
0x18001776b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FilesystemIsolationMode@Definition@Containers@Schema@@W4FilesystemNestingMode@456@U?$ModifiedType@V?$vector@UFilesystemLayer@Definition@Containers@Schema@@V?$allocator@UFilesystemLayer@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UBatchedBinding@Definition@Containers@Schema@@V?$allocator@UBatchedBinding@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@9@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Schema::Containers::Definition::FilesystemIsolationMode,Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180017772  mov     r8, [rsp+68h+arg_20]
0x18001777a  lea     r9, [rsp+68h+var_18]
0x18001777f  mov     [rsp+68h+var_38], rcx
0x180017784  mov     rdx, rsi
0x180017787  mov     [rsp+68h+var_18], rax
0x18001778c  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UNamedPipeSymlink@Definition@Containers@Schema@@V?$allocator@UNamedPipeSymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::NamedPipeSymlink>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017793  mov     [rsp+68h+var_30], rcx
0x180017798  add     rax, 0A0h
0x18001779e  mov     [rsp+68h+var_10], rax
0x1800177a3  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FilesystemIsolationMode@Definition@Containers@Schema@@W4FilesystemNestingMode@456@U?$ModifiedType@V?$vector@UFilesystemLayer@Definition@Containers@Schema@@V?$allocator@UFilesystemLayer@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UBatchedBinding@Definition@Containers@Schema@@V?$allocator@UBatchedBinding@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@9@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Schema::Containers::Definition::FilesystemIsolationMode,Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800177aa  mov     qword ptr [rsp+68h+var_28], rcx
0x1800177af  lea     rax, [rsp+68h+var_38]
0x1800177b4  mov     [rsp+68h+var_40], rax
0x1800177b9  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@U?$optional@UJobNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@UFilesystemNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UMountManagerNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UNamedPipeNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UObjectNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@URegistryNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UNetworkNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UDeviceNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UHostFiles@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$08@std@@A; std::array<Marshal::Details::XmlTypeData const *,9> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::FilesystemNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::MountManagerNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::NamedPipeNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::ObjectNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::RegistryNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::NetworkNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::DeviceNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::HostFiles>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800177c0  mov     [rsp+68h+var_20], rcx
0x1800177c5  lea     rax, [rsp+68h+var_28]
0x1800177ca  mov     rcx, rdi
0x1800177cd  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800177d2  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x1800177d7  test    rbx, rbx
0x1800177da  jz      short loc_1800177EF
0x1800177dc  mov     rcx, [rdi]
0x1800177df  mov     rax, [rcx]
0x1800177e2  mov     rax, [rax+78h]
0x1800177e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177eb  test    eax, eax
0x1800177ed  js      short loc_180017800
0x1800177ef  mov     rbx, [rsp+68h+arg_0]
0x1800177f4  mov     rsi, [rsp+68h+arg_8]
0x1800177f9  add     rsp, 60h
0x1800177fd  pop     rdi
0x1800177fe  retn
0x180017800  mov     rcx, [rsp+68h]; this
0x180017805  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001780c  mov     r9d, eax; char *
0x18001780f  mov     edx, 1EFh; void *
0x180017814  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001781a  mov     rcx, [rsp+68h]; this
0x18001781f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017826  mov     edx, 1DFh; void *
0x18001782b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180017831  mov     rcx, [rsp+68h]; this
0x180017836  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001783d  mov     r9d, eax; char *
0x180017840  mov     edx, 1E3h; void *
0x180017845  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
