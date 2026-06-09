# Marshal::WriteXml<Schema::Containers::Definition::JobMemory,>(Marshal::XmlWriter &,ushort const *,bool,Schema::Containers::Definition::JobMemory const &,Marshal::MarshalContext const &)

- ea: `0x180017abc`
- end: `0x180017be9`
- name: `??$WriteXml@UJobMemory@Definition@Containers@Schema@@$$V@Marshal@@YAXAEAUXmlWriter@0@PEBG_NAEBUJobMemory@Definition@Containers@Schema@@AEBVMarshalContext@0@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x1800187d0`

## callees

- `0x18000bdc8`
- `0x180017abc`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180017ba3`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017bbd`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180017bd4`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::WriteXml<Schema::Containers::Definition::JobMemory,>(
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
  v12[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<unsigned __int64>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[0] = Schema::Containers::Definition::JobMemory_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,enum Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::JobMemory_ClassData + 32LL;
  *(_QWORD *)v13 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<unsigned __int64>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v14 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,unsigned int,bool,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
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
0x180017abc  mov     [rsp+arg_0], rbx
0x180017ac1  mov     [rsp+arg_8], rsi
0x180017ac6  push    rdi
0x180017ac7  sub     rsp, 60h
0x180017acb  mov     rsi, r9
0x180017ace  mov     rbx, rdx
0x180017ad1  mov     rdi, rcx
0x180017ad4  test    r8b, r8b
0x180017ad7  jnz     loc_180017BB8
0x180017add  test    rdx, rdx
0x180017ae0  jz      short loc_180017B04
0x180017ae2  mov     rcx, [rcx]
0x180017ae5  mov     r8, rdx
0x180017ae8  xor     r9d, r9d
0x180017aeb  xor     edx, edx
0x180017aed  mov     rax, [rcx]
0x180017af0  mov     rax, [rax+0D8h]
0x180017af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017afc  test    eax, eax
0x180017afe  js      loc_180017BCF
0x180017b04  mov     rax, cs:?JobMemory_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::JobMemory_ClassData
0x180017b0b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@_K@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<unsigned __int64>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180017b12  mov     r8, [rsp+68h+arg_20]
0x180017b1a  lea     r9, [rsp+68h+var_18]
0x180017b1f  mov     [rsp+68h+var_38], rcx
0x180017b24  mov     rdx, rsi
0x180017b27  mov     [rsp+68h+var_18], rax
0x180017b2c  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@W4ObjectDirectoryShadow@Definition@Containers@Schema@@U?$ModifiedType@V?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@8@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,Schema::Containers::Definition::ObjectDirectoryShadow,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectSymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::ObjectDirectory>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180017b33  mov     [rsp+68h+var_30], rcx
0x180017b38  add     rax, 20h ; ' '
0x180017b3c  mov     [rsp+68h+var_10], rax
0x180017b41  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@_K@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<unsigned __int64>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017b48  mov     qword ptr [rsp+68h+var_28], rcx
0x180017b4d  lea     rax, [rsp+68h+var_38]
0x180017b52  mov     [rsp+68h+var_40], rax
0x180017b57  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@I_N_N@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$05@std@@A; std::array<Marshal::Details::BaseTypeData const *,6> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring,std::wstring,uint,bool,bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180017b5e  mov     [rsp+68h+var_20], rcx
0x180017b63  lea     rax, [rsp+68h+var_28]
0x180017b68  mov     rcx, rdi
0x180017b6b  mov     qword ptr [rsp+68h+var_48], rax; int
0x180017b70  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180017b75  test    rbx, rbx
0x180017b78  jz      short loc_180017B8D
0x180017b7a  mov     rcx, [rdi]
0x180017b7d  mov     rax, [rcx]
0x180017b80  mov     rax, [rax+78h]
0x180017b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b89  test    eax, eax
0x180017b8b  js      short loc_180017B9E
0x180017b8d  mov     rbx, [rsp+68h+arg_0]
0x180017b92  mov     rsi, [rsp+68h+arg_8]
0x180017b97  add     rsp, 60h
0x180017b9b  pop     rdi
0x180017b9c  retn
0x180017b9e  mov     rcx, [rsp+68h]; this
0x180017ba3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017baa  mov     r9d, eax; char *
0x180017bad  mov     edx, 1EFh; void *
0x180017bb2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017bb8  mov     rcx, [rsp+68h]; this
0x180017bbd  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017bc4  mov     edx, 1DFh; void *
0x180017bc9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180017bcf  mov     rcx, [rsp+68h]; this
0x180017bd4  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180017bdb  mov     r9d, eax; char *
0x180017bde  mov     edx, 1E3h; void *
0x180017be3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
