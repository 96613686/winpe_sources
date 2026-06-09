# _anonymous_namespace_::FieldBindingsConfigurator::BindEnumFieldValue_enum_Notification::PlanType_

- ea: `0x18004d5bc`
- end: `0x18004d8f2`
- name: `_anonymous_namespace_::FieldBindingsConfigurator::BindEnumFieldValue_enum_Notification::PlanType_`
- size: `822`
- prototype: `void __fastcall(std::reference_wrapper<enum Notification::PlanType> FieldValue, const Notification::Configuration::Node *FieldNode)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x180050de0`

## callees

- `0x180002790`
- `0x1800032f4`
- `0x1800084d0`
- `0x18000af94`
- `0x180011844`
- `0x180011cfc`
- `0x180016cf0`
- `0x18004bb00`
- `0x18004d5bc`
- `0x18004de70`
- `0x18004efbc`
- `0x18004f344`
- `0x18004f66c`
- `0x18004facc`
- `0x18004fc5c`
- `0x180051924`
- `0x180051b00`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004d642`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004d664`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004d686`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004d642`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004d664`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004d686`

## string_xrefs

- `0x18004d6f4`: `FixedTokens`
- `0x18004d6c5`: `UnrestrictedTokens`
- `0x18004d835`: `UnrestrictedTokens/FixedTokens/VariableTokens`
- `0x18004d726`: `VariableTokens`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall anonymous_namespace_::FieldBindingsConfigurator::BindEnumFieldValue_enum_Notification::PlanType_(
        std::reference_wrapper<enum Notification::PlanType> FieldValue,
        Notification::MissingAttributeException_vtbl *FieldNode,
        const Notification::Configuration::Node *a3)
{
  std::wstring *(__fastcall *GetAttribute)(Notification::Configuration::Node *, std::wstring *, const std::wstring *); // rdi
  Notification::PlanType v7; // edi
  const wchar_t *v8; // rax
  const wchar_t *v9; // rax
  const wchar_t *v10; // rax
  const Notification::Configuration::Node *v11; // rcx
  ValueSetter<enum Notification::PlanType> *GroupId; // r14
  _QWORD *v13; // rbx
  unsigned __int64 v14; // rax
  std::wstring *v15; // rax
  std::wstring *v16; // rbx
  std::wstring *v17; // rax
  std::wstring *v18; // rax
  std::_Global_new::__l2::_Guard_type v19; // [rsp+20h] [rbp-E0h] BYREF
  std::wstring v20; // [rsp+28h] [rbp-D8h] BYREF
  FieldBindingsConfigurator::BindEnumFieldValue::__l2::<lambda_1> FnAddTokenListToMapping; // [rsp+48h] [rbp-B8h] BYREF
  std::wstring v22; // [rsp+68h] [rbp-98h] BYREF
  Notification::MissingAttributeException pExceptionObject; // [rsp+90h] [rbp-70h] BYREF
  Notification::FieldParsers::TokenMatchParser<enum Notification::PlanType> planTypeParser; // [rsp+F0h] [rbp-10h] BYREF
  std::wstring defaultValue; // [rsp+108h] [rbp+8h] BYREF

  GetAttribute = a3->GetAttribute;
  std::wstring::wstring((std::wstring *)&FnAddTokenListToMapping, L"Default");
  GetAttribute((Notification::Configuration::Node *)a3, &defaultValue, (const std::wstring *)&FnAddTokenListToMapping);
  std::wstring::_Tidy_deallocate((std::wstring *)&FnAddTokenListToMapping);
  v7 = Unknown;
  if ( defaultValue._Mypair._Myval2._Mysize )
  {
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&defaultValue._Mypair._Myval2);
    if ( (unsigned int)_o__wcsicmp(v8, L"Unrestricted") )
    {
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&defaultValue._Mypair._Myval2);
      if ( (unsigned int)_o__wcsicmp(v9, L"Fixed") )
      {
        v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&defaultValue._Mypair._Myval2);
        if ( !(unsigned int)_o__wcsicmp(v10, L"Variable") )
          v7 = Variable;
      }
      else
      {
        v7 = Fixed;
      }
    }
    else
    {
      v7 = Unrestricted;
    }
  }
  memset(&planTypeParser, 0, sizeof(planTypeParser));
  std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Alloc_sentinel_and_proxy((std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring >,std::allocator<std::pair<std::wstring const ,bool> >,0> > *)&planTypeParser);
  planTypeParser.m_default = v7;
  FnAddTokenListToMapping.planTypeParser = &planTypeParser;
  FnAddTokenListToMapping.FieldNode = a3;
  std::wstring::wstring(&v20, L"UnrestrictedTokens");
  _anonymous_namespace_::FieldBindingsConfigurator::BindEnumFieldValue_enum_Notification::PlanType__::_2_::_lambda_1_::operator()(
    (const std::wstring *)&FnAddTokenListToMapping,
    (Notification::PlanType)&v20);
  std::wstring::_Tidy_deallocate(&v20);
  std::wstring::wstring(&v20, L"FixedTokens");
  _anonymous_namespace_::FieldBindingsConfigurator::BindEnumFieldValue_enum_Notification::PlanType__::_2_::_lambda_1_::operator()(
    (const std::wstring *)&FnAddTokenListToMapping,
    (Notification::PlanType)&v20);
  std::wstring::_Tidy_deallocate(&v20);
  std::wstring::wstring(&v20, L"VariableTokens");
  _anonymous_namespace_::FieldBindingsConfigurator::BindEnumFieldValue_enum_Notification::PlanType__::_2_::_lambda_1_::operator()(
    (const std::wstring *)&FnAddTokenListToMapping,
    (Notification::PlanType)&v20);
  std::wstring::_Tidy_deallocate(&v20);
  std::wstring::wstring(&v20, L"Group");
  GroupId = (ValueSetter<enum Notification::PlanType> *)anonymous_namespace_::FieldBindingsConfigurator::GetGroupId(
                                                          v11,
                                                          (const std::wstring *)a3);
  std::wstring::_Tidy_deallocate(&v20);
  if ( GroupId )
  {
    if ( !planTypeParser.m_mappings._Mypair._Myval2._Myval2._Mysize )
    {
      FnAddTokenListToMapping.planTypeParser = (Notification::FieldParsers::TokenMatchParser<enum Notification::PlanType> *)&v20;
      std::wstring::wstring(&v20, L"UnrestrictedTokens/FixedTokens/VariableTokens");
      v16 = v15;
      v17 = a3->GetName(a3, &v22);
      Notification::MissingAttributeException::MissingAttributeException(&pExceptionObject, v17, v16);
      throw &pExceptionObject;
    }
    pExceptionObject.__vftable = FieldNode;
    FnAddTokenListToMapping.planTypeParser = (Notification::FieldParsers::TokenMatchParser<enum Notification::PlanType> *)&pExceptionObject._Data;
    *(_QWORD *)&pExceptionObject.m_attribute._Mypair._Myval2._Bx._Alias[8] = 0;
    v13 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
    *v13 = std::_Func_impl_no_alloc<Notification::FieldParsers::TokenMatchParser<enum Notification::PlanType>,enum Notification::PlanType,std::wstring const &>::`vftable';
    Notification::FieldParsers::UnitParser::UnitParser(
      (Notification::FieldParsers::UnitParser *)(v13 + 1),
      (const Notification::FieldParsers::UnitParser *)&planTypeParser);
    v19._Result = 0;
    `std::_Global_new<std::_Func_impl_no_alloc<Notification::FieldParsers::TokenMatchParser<bool>,bool,std::wstring const &>,Notification::FieldParsers::TokenMatchParser<bool> const &>'::`2'::_Guard_type::~_Guard_type(&v19);
    *(_QWORD *)&pExceptionObject.m_attribute._Mypair._Myval2._Bx._Alias[8] = v13;
    v14 = (unsigned __int64)a3->GetName(a3, &v20);
    anonymous_namespace_::FieldBindingsConfigurator::ValidateAndBindGroupParserForField__anonymous_namespace_::ValueSetter_enum_Notification::PlanType___(
      (const std::wstring *)FieldValue._Ptr,
      v14,
      GroupId);
    std::wstring::_Tidy_deallocate(&v20);
    std::_Func_class<bool,std::wstring const &>::_Tidy((std::_Func_class<void,_WCM_DATAPLAN_STATUS &> *)&pExceptionObject._Data);
  }
  else
  {
    if ( planTypeParser.m_mappings._Mypair._Myval2._Myval2._Mysize )
    {
      v18 = a3->GetName(a3, &v22);
      Notification::GroupAttributeMissingException::GroupAttributeMissingException(
        (Notification::GroupAttributeMissingException *)&pExceptionObject,
        v18);
      throw (Notification::GroupAttributeMissingException *)&pExceptionObject;
    }
    LODWORD(FieldNode->~Notification::MissingAttributeException) = v7;
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,enum Notification::PlanType>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,enum Notification::PlanType>,void *>>>(
    (std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const ,bool> > > *)&planTypeParser,
    (std::allocator<std::_Tree_node<std::pair<std::wstring const ,bool>,void *> > *)&planTypeParser);
  std::wstring::_Tidy_deallocate(&defaultValue);
}

```

## disassembly

```asm
0x18004d5bc  mov     [rsp-8+arg_8], rbx
0x18004d5c1  push    rbp
0x18004d5c2  push    rsi
0x18004d5c3  push    rdi
0x18004d5c4  push    r14
0x18004d5c6  push    r15
0x18004d5c8  lea     rbp, [rsp-30h]
0x18004d5cd  sub     rsp, 130h
0x18004d5d4  mov     rax, cs:__security_cookie
0x18004d5db  xor     rax, rsp
0x18004d5de  mov     [rbp+50h+var_28], rax
0x18004d5e2  mov     rsi, FieldNode
0x18004d5e5  mov     rbx, FieldValue
0x18004d5e8  mov     r15, this
0x18004d5eb  mov     rax, [FieldNode]
0x18004d5ee  mov     rdi, [rax+38h]
0x18004d5f2  lea     FieldValue, aDefault_0; "Default"
0x18004d5f9  lea     this, [rsp+150h+FnAddTokenListToMapping]; this
0x18004d5fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004d603  nop
0x18004d604  lea     FieldNode, [rsp+150h+FnAddTokenListToMapping]
0x18004d609  lea     FieldValue, [rbp+50h+defaultValue]
0x18004d60d  mov     this, rsi
0x18004d610  mov     rax, rdi
0x18004d613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d618  nop
0x18004d619  lea     this, [rsp+150h+FnAddTokenListToMapping]; this
0x18004d61e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d623  xor     edi, edi
0x18004d625  lea     r14d, [rdi+1]
0x18004d629  cmp     [rbp+50h+defaultValue._Mypair._Myval2._Mysize], rdi
0x18004d62d  jz      short loc_18004D696
0x18004d62f  lea     this, [rbp+50h+defaultValue]; this
0x18004d633  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d638  mov     this, rax
0x18004d63b  lea     FieldValue, aUnrestricted; "Unrestricted"
0x18004d642  call    cs:__imp__o__wcsicmp
0x18004d648  test    eax, eax
0x18004d64a  jnz     short loc_18004D651
0x18004d64c  mov     edi, r14d
0x18004d64f  jmp     short loc_18004D696
0x18004d651  lea     this, [rbp+50h+defaultValue]; this
0x18004d655  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d65a  mov     this, rax
0x18004d65d  lea     FieldValue, aFixed; "Fixed"
0x18004d664  call    cs:__imp__o__wcsicmp
0x18004d66a  test    eax, eax
0x18004d66c  jnz     short loc_18004D673
0x18004d66e  lea     edi, [rax+2]
0x18004d671  jmp     short loc_18004D696
0x18004d673  lea     this, [rbp+50h+defaultValue]; this
0x18004d677  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d67c  mov     this, rax
0x18004d67f  lea     FieldValue, aVariable; "Variable"
0x18004d686  call    cs:__imp__o__wcsicmp
0x18004d68c  test    eax, eax
0x18004d68e  mov     eax, 3
0x18004d693  cmovz   edi, eax
0x18004d696  xorps   xmm0, xmm0
0x18004d699  xor     eax, eax
0x18004d69b  movups  xmmword ptr [rbp+50h+planTypeParser.m_mappings._Mypair._Myval2._Myval2._Myhead], xmm0
0x18004d69f  mov     qword ptr [rbp+50h+planTypeParser.m_default], rax
0x18004d6a3  mov     [rbp+50h+planTypeParser.m_mappings._Mypair._Myval2._Myval2._Myhead], rax
0x18004d6a7  mov     [rbp+50h+planTypeParser.m_mappings._Mypair._Myval2._Myval2._Mysize], rax
0x18004d6ab  lea     this, [rbp+50h+planTypeParser]; this
0x18004d6af  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18004d6b4  mov     [rbp+50h+planTypeParser.m_default], edi
0x18004d6b7  lea     rax, [rbp+50h+planTypeParser]
0x18004d6bb  mov     [rsp+150h+FnAddTokenListToMapping.planTypeParser], rax
0x18004d6c0  mov     [rsp+150h+FnAddTokenListToMapping.FieldNode], rsi
0x18004d6c5  lea     FieldValue, aUnrestrictedto_0; "UnrestrictedTokens"
0x18004d6cc  lea     this, [rsp+150h+var_128]; this
0x18004d6d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004d6d6  nop
0x18004d6d7  mov     r8d, r14d
0x18004d6da  lea     FieldValue, [rsp+150h+var_128]; Value
0x18004d6df  lea     this, [rsp+150h+FnAddTokenListToMapping]; AttributeName
0x18004d6e4  call    __anonymous_namespace___FieldBindingsConfigurator__BindEnumFieldValue_enum_Notification__PlanType_____2____lambda_1___operator__
0x18004d6e9  nop
0x18004d6ea  lea     this, [rsp+150h+var_128]; this
0x18004d6ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d6f4  lea     FieldValue, aFixedtokens; "FixedTokens"
0x18004d6fb  lea     this, [rsp+150h+var_128]; this
0x18004d700  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004d705  nop
0x18004d706  mov     r8d, 2
0x18004d70c  lea     FieldValue, [rsp+150h+var_128]; Value
0x18004d711  lea     this, [rsp+150h+FnAddTokenListToMapping]; AttributeName
0x18004d716  call    __anonymous_namespace___FieldBindingsConfigurator__BindEnumFieldValue_enum_Notification__PlanType_____2____lambda_1___operator__
0x18004d71b  nop
0x18004d71c  lea     this, [rsp+150h+var_128]; this
0x18004d721  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d726  lea     FieldValue, aVariabletokens; "VariableTokens"
0x18004d72d  lea     this, [rsp+150h+var_128]; this
0x18004d732  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004d737  nop
0x18004d738  mov     r8d, 3
0x18004d73e  lea     FieldValue, [rsp+150h+var_128]; Value
0x18004d743  lea     this, [rsp+150h+FnAddTokenListToMapping]; AttributeName
0x18004d748  call    __anonymous_namespace___FieldBindingsConfigurator__BindEnumFieldValue_enum_Notification__PlanType_____2____lambda_1___operator__
0x18004d74d  nop
0x18004d74e  lea     this, [rsp+150h+var_128]; this
0x18004d753  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d758  lea     FieldValue, aGroup; "Group"
0x18004d75f  lea     this, [rsp+150h+var_128]; this
0x18004d764  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004d769  nop
0x18004d76a  lea     FieldNode, [rsp+150h+var_128]
0x18004d76f  mov     FieldValue, rsi; GroupAttributeName
0x18004d772  call    _anonymous_namespace___FieldBindingsConfigurator__GetGroupId
0x18004d777  mov     r14, rax
0x18004d77a  lea     this, [rsp+150h+var_128]; this
0x18004d77f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d784  test    r14, r14
0x18004d787  jz      loc_18004D87E
0x18004d78d  cmp     [rbp+50h+planTypeParser.m_mappings._Mypair._Myval2._Myval2._Mysize], 0
0x18004d792  jz      loc_18004D82B
0x18004d798  mov     [rbp+50h+pExceptionObject], rbx
0x18004d79c  lea     rax, [rbp+50h+var_B8]
0x18004d7a0  mov     [rsp+150h+FnAddTokenListToMapping.planTypeParser], rax
0x18004d7a5  mov     qword ptr [rbp+50h+var_B8._Mystorage+38h], 0
0x18004d7ad  mov     ecx, 20h ; ' '; _Bytes
0x18004d7b2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18004d7b7  mov     rbx, rax
0x18004d7ba  mov     [rsp+150h+var_130._Result], rax
0x18004d7bf  lea     rax, ??_7?$_Func_impl_no_alloc@V?$TokenMatchParser@W4PlanType@Notification@@@FieldParsers@Notification@@W4PlanType@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@6B@; const std::_Func_impl_no_alloc<Notification::FieldParsers::TokenMatchParser<Notification::PlanType>,Notification::PlanType,std::wstring const &>::`vftable'
0x18004d7c6  mov     [rbx], rax
0x18004d7c9  lea     this, [rbx+8]; this
0x18004d7cd  lea     FieldValue, [rbp+50h+planTypeParser]; __that
0x18004d7d1  call    ??0UnitParser@FieldParsers@Notification@@QEAA@AEBV012@@Z; Notification::FieldParsers::UnitParser::UnitParser(Notification::FieldParsers::UnitParser const &)
0x18004d7d6  mov     [rsp+150h+var_130._Result], 0
0x18004d7df  lea     this, [rsp+150h+var_130]; this
0x18004d7e4  call    ??1_Guard_type@?1???$_Global_new@V?$_Func_impl_no_alloc@V?$TokenMatchParser@_N@FieldParsers@Notification@@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$TokenMatchParser@_N@FieldParsers@Notification@@@std@@YAPEAV?$_Func_impl_no_alloc@V?$TokenMatchParser@_N@FieldParsers@Notification@@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEBV?$TokenMatchParser@_N@FieldParsers@Notification@@@Z@QEAA@XZ; `std::_Global_new<std::_Func_impl_no_alloc<Notification::FieldParsers::TokenMatchParser<bool>,bool,std::wstring const &>,Notification::FieldParsers::TokenMatchParser<bool> const &>(Notification::FieldParsers::TokenMatchParser<bool> const &)'::`2'::_Guard_type::~_Guard_type(void)
0x18004d7e9  mov     qword ptr [rbp+50h+var_B8._Mystorage+38h], rbx
0x18004d7ed  mov     rax, [rsi]
0x18004d7f0  lea     FieldValue, [rsp+150h+var_128]
0x18004d7f5  mov     this, rsi
0x18004d7f8  mov     rax, [rax+8]
0x18004d7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d801  nop
0x18004d802  lea     r9, [rbp+50h+pExceptionObject]
0x18004d806  mov     FieldNode, r14; parser
0x18004d809  mov     FieldValue, rax; GroupId
0x18004d80c  mov     this, r15; Field
0x18004d80f  call    _anonymous_namespace___FieldBindingsConfigurator__ValidateAndBindGroupParserForField__anonymous_namespace___ValueSetter_enum_Notification__PlanType___
0x18004d814  nop
0x18004d815  lea     this, [rsp+150h+var_128]; this
0x18004d81a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d81f  nop
0x18004d820  lea     this, [rbp+50h+var_B8]; this
0x18004d824  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18004d829  jmp     short loc_18004D887
0x18004d82b  lea     rax, [rsp+150h+var_128]
0x18004d830  mov     [rsp+150h+FnAddTokenListToMapping.planTypeParser], rax
0x18004d835  lea     FieldValue, aUnrestrictedto; "UnrestrictedTokens/FixedTokens/Variable"...
0x18004d83c  lea     this, [rsp+150h+var_128]; this
0x18004d841  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004d846  mov     rbx, rax
0x18004d849  mov     this, [rsi]
0x18004d84c  mov     rax, [this+8]
0x18004d850  lea     FieldValue, [rsp+150h+var_E8]
0x18004d855  mov     this, rsi
0x18004d858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d85d  nop
0x18004d85e  mov     FieldNode, rbx
0x18004d861  mov     FieldValue, rax
0x18004d864  lea     this, [rbp+50h+pExceptionObject]
0x18004d868  call    ??0MissingAttributeException@Notification@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Notification::MissingAttributeException::MissingAttributeException(std::wstring,std::wstring)
0x18004d86d  lea     FieldValue, _TI3?AVMissingAttributeException@Notification@@; pThrowInfo
0x18004d874  lea     this, [rbp+50h+pExceptionObject]; pExceptionObject
0x18004d878  call    _CxxThrowException_0
0x18004d87e  cmp     [rbp+50h+planTypeParser.m_mappings._Mypair._Myval2._Myval2._Mysize], 0
0x18004d883  jnz     short loc_18004D8C1
0x18004d885  mov     [rbx], edi
0x18004d887  lea     FieldValue, [rbp+50h+planTypeParser]; _Al
0x18004d88b  lea     this, [rbp+50h+planTypeParser]; this
0x18004d88f  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PlanType@Notification@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PlanType@Notification@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PlanType@Notification@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Notification::PlanType>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,Notification::PlanType>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,Notification::PlanType>,void *>> &)
0x18004d894  nop
0x18004d895  lea     this, [rbp+50h+defaultValue]; this
0x18004d899  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d89e  mov     this, [rbp+50h+var_28]
0x18004d8a2  xor     this, rsp; StackCookie
0x18004d8a5  call    __security_check_cookie
0x18004d8aa  mov     rbx, [rsp+150h+arg_8]
0x18004d8b2  add     rsp, 130h
0x18004d8b9  pop     r15
0x18004d8bb  pop     r14
0x18004d8bd  pop     rdi
0x18004d8be  pop     rsi
0x18004d8bf  pop     rbp
0x18004d8c0  retn
0x18004d8c1  mov     rax, [rsi]
0x18004d8c4  lea     FieldValue, [rsp+150h+var_E8]
0x18004d8c9  mov     this, rsi
0x18004d8cc  mov     rax, [rax+8]
0x18004d8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8d5  mov     FieldValue, rax
0x18004d8d8  lea     this, [rbp+50h+pExceptionObject]
0x18004d8dc  call    ??0GroupAttributeMissingException@Notification@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Notification::GroupAttributeMissingException::GroupAttributeMissingException(std::wstring)
0x18004d8e1  lea     FieldValue, _TI4?AVGroupAttributeMissingException@Notification@@; pThrowInfo
0x18004d8e8  lea     this, [rbp+50h+pExceptionObject]; pExceptionObject
0x18004d8ec  call    _CxxThrowException_0
```
