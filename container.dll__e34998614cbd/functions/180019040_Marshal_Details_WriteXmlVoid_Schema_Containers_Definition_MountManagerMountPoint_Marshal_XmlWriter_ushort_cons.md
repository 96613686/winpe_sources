# Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::MountManagerMountPoint,>(Marshal::XmlWriter &,ushort const *,bool,void const *,Marshal::MarshalContext const &)

- ea: `0x180019040`
- end: `0x18001916d`
- name: `??$WriteXmlVoid@UMountManagerMountPoint@Definition@Containers@Schema@@$$V@Details@Marshal@@YAXAEAUXmlWriter@1@PEBG_NPEBXAEBVMarshalContext@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callees

- `0x18000bdc8`
- `0x180019040`
- `0x180021190`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180019127`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019141`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180019158`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteXmlVoid<Schema::Containers::Definition::MountManagerMountPoint,>(
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
  v15[0] = Schema::Containers::Definition::MountManagerMountPoint_ClassData;
  v12[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v15[1] = Schema::Containers::Definition::MountManagerMountPoint_ClassData + 64LL;
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
0x180019040  mov     [rsp+arg_0], rbx
0x180019045  mov     [rsp+arg_8], rsi
0x18001904a  push    rdi
0x18001904b  sub     rsp, 60h
0x18001904f  mov     rsi, r9
0x180019052  mov     rbx, rdx
0x180019055  mov     rdi, rcx
0x180019058  test    r8b, r8b
0x18001905b  jnz     loc_18001913C
0x180019061  test    rdx, rdx
0x180019064  jz      short loc_180019088
0x180019066  mov     rcx, [rcx]
0x180019069  mov     r8, rdx
0x18001906c  xor     r9d, r9d
0x18001906f  xor     edx, edx
0x180019071  mov     rax, [rcx]
0x180019074  mov     rax, [rax+0D8h]
0x18001907b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019080  test    eax, eax
0x180019082  js      loc_180019153
0x180019088  mov     rax, cs:?MountManagerMountPoint_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::MountManagerMountPoint_ClassData
0x18001908f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::XmlTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180019096  mov     r8, [rsp+68h+arg_20]
0x18001909e  lea     r9, [rsp+68h+var_18]
0x1800190a3  mov     [rsp+68h+var_38], rcx
0x1800190a8  mov     rdx, rsi
0x1800190ab  mov     [rsp+68h+var_18], rax
0x1800190b0  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$ModifiedType@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Marshal::ModifiedType<std::vector<std::wstring>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800190b7  mov     [rsp+68h+var_30], rcx
0x1800190bc  add     rax, 40h ; '@'
0x1800190c0  mov     [rsp+68h+var_10], rax
0x1800190c5  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,std::wstring>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800190cc  mov     qword ptr [rsp+68h+var_28], rcx
0x1800190d1  lea     rax, [rsp+68h+var_38]
0x1800190d6  mov     [rsp+68h+var_40], rax
0x1800190db  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::MountManagerMountPoint>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800190e2  mov     [rsp+68h+var_20], rcx
0x1800190e7  lea     rax, [rsp+68h+var_28]
0x1800190ec  mov     rcx, rdi
0x1800190ef  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800190f4  call    ?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x1800190f9  test    rbx, rbx
0x1800190fc  jz      short loc_180019111
0x1800190fe  mov     rcx, [rdi]
0x180019101  mov     rax, [rcx]
0x180019104  mov     rax, [rax+78h]
0x180019108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001910d  test    eax, eax
0x18001910f  js      short loc_180019122
0x180019111  mov     rbx, [rsp+68h+arg_0]
0x180019116  mov     rsi, [rsp+68h+arg_8]
0x18001911b  add     rsp, 60h
0x18001911f  pop     rdi
0x180019120  retn
0x180019122  mov     rcx, [rsp+68h]; this
0x180019127  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001912e  mov     r9d, eax; char *
0x180019131  mov     edx, 1EFh; void *
0x180019136  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001913c  mov     rcx, [rsp+68h]; this
0x180019141  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180019148  mov     edx, 1DFh; void *
0x18001914d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180019153  mov     rcx, [rsp+68h]; this
0x180019158  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001915f  mov     r9d, eax; char *
0x180019162  mov     edx, 1E3h; void *
0x180019167  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
