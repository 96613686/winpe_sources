# _anonymous_namespace_::FieldBindingsConfigurator::BindBooleanFieldValue

- ea: `0x18004ff04`
- end: `0x1800502da`
- name: `_anonymous_namespace_::FieldBindingsConfigurator::BindBooleanFieldValue`
- size: `982`
- prototype: `void __fastcall(std::reference_wrapper<bool> FieldValue, const Notification::Configuration::Node *FieldNode)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x180050de0`

## callees

- `0x180002790`
- `0x1800032f4`
- `0x1800084d0`
- `0x18000af94`
- `0x180011cfc`
- `0x180016cf0`
- `0x18001c07c`
- `0x18004bb00`
- `0x18004df64`
- `0x18004efec`
- `0x18004f1f0`
- `0x18004f344`
- `0x18004f66c`
- `0x18004facc`
- `0x18004feac`
- `0x18004ff04`
- `0x1800517e0`
- `0x180051924`
- `0x180051b00`
- `0x18006f010`

## string_xrefs

- `0x18004ff66`: `TrueToken`
- `0x180050085`: `TrueToken`
- `0x18004ff9e`: `FalseToken`
- `0x180050115`: `FalseToken`
- `0x180050212`: `TrueToken/FalseToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall anonymous_namespace_::FieldBindingsConfigurator::BindBooleanFieldValue(
        std::reference_wrapper<bool> FieldValue,
        Notification::DuplicateMappingException_vtbl *FieldNode,
        const std::wstring *a3)
{
  const Notification::Configuration::Node *v6; // rcx
  ValueSetter<bool> *GroupId; // r14
  void (__fastcall *v8)(const std::wstring *, std::wstring *, std::wstring *); // rdi
  void (__fastcall *v9)(const std::wstring *, std::wstring *, std::wstring *); // rdi
  __int64 (__fastcall *v10)(const std::wstring *, std::wstring *, std::wstring *); // rdi
  const std::wstring *v11; // rax
  bool BooleanValue; // di
  std::wstring *v13; // rax
  std::wstring *v14; // rdi
  std::wstring *v15; // rax
  std::wstring *v16; // rbx
  std::wstring *v17; // rax
  std::wstring *v18; // rax
  std::wstring *v19; // rdi
  std::wstring *v20; // rax
  std::wstring *v21; // rbx
  std::wstring *v22; // rax
  _QWORD *v23; // rbx
  std::allocator<std::_Tree_node<std::pair<std::wstring const ,bool>,void *> > *v24; // r8
  unsigned __int64 v25; // rax
  std::wstring *v26; // rax
  std::wstring *v27; // rbx
  std::wstring *v28; // rax
  std::wstring *v29; // rax
  std::_Global_new::__l2::_Guard_type v30; // [rsp+20h] [rbp-E0h] BYREF
  void *p_Data; // [rsp+28h] [rbp-D8h]
  std::wstring v32; // [rsp+30h] [rbp-D0h] BYREF
  std::wstring *v33; // [rsp+50h] [rbp-B0h]
  std::wstring v34; // [rsp+58h] [rbp-A8h] BYREF
  std::wstring v35; // [rsp+78h] [rbp-88h] BYREF
  Notification::DuplicateMappingException pExceptionObject; // [rsp+A0h] [rbp-60h] BYREF
  Notification::FieldParsers::TokenMatchParser<bool> booleanParser; // [rsp+120h] [rbp+20h] BYREF
  std::wstring falseToken; // [rsp+138h] [rbp+38h] BYREF
  std::wstring trueToken; // [rsp+158h] [rbp+58h] BYREF

  std::wstring::wstring(&v32, L"Group");
  GroupId = (ValueSetter<bool> *)anonymous_namespace_::FieldBindingsConfigurator::GetGroupId(v6, a3);
  std::wstring::_Tidy_deallocate(&v32);
  v8 = (void (__fastcall *)(const std::wstring *, std::wstring *, std::wstring *))*((_QWORD *)a3->_Mypair._Myval2._Bx._Ptr
                                                                                  + 7);
  std::wstring::wstring(&v32, L"TrueToken");
  v8(a3, &trueToken, &v32);
  std::wstring::_Tidy_deallocate(&v32);
  v9 = (void (__fastcall *)(const std::wstring *, std::wstring *, std::wstring *))*((_QWORD *)a3->_Mypair._Myval2._Bx._Ptr
                                                                                  + 7);
  std::wstring::wstring(&v35, L"FalseToken");
  v9(a3, &falseToken, &v35);
  std::wstring::_Tidy_deallocate(&v35);
  v10 = (__int64 (__fastcall *)(const std::wstring *, std::wstring *, std::wstring *))*((_QWORD *)a3->_Mypair._Myval2._Bx._Ptr
                                                                                      + 7);
  std::wstring::wstring(&v32, L"Default");
  v11 = (const std::wstring *)v10(a3, &v34, &v32);
  BooleanValue = anonymous_namespace_::GetBooleanValue(v11, 0);
  std::wstring::_Tidy_deallocate(&v34);
  std::wstring::_Tidy_deallocate(&v32);
  memset(&booleanParser, 0, sizeof(booleanParser));
  std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Alloc_sentinel_and_proxy(&booleanParser.m_mappings);
  booleanParser.m_default = BooleanValue;
  if ( trueToken._Mypair._Myval2._Mysize
    && !Notification::FieldParsers::TokenMatchParser<bool>::AddMapping(&booleanParser, &trueToken, 1) )
  {
    v30._Result = &v34;
    std::wstring::wstring(&v34, &trueToken);
    v14 = v13;
    v33 = &v35;
    std::wstring::wstring(&v35, L"TrueToken");
    v16 = v15;
    v17 = (std::wstring *)(*((__int64 (__fastcall **)(const std::wstring *, std::wstring *))a3->_Mypair._Myval2._Bx._Ptr
                           + 1))(
                            a3,
                            &v32);
    Notification::DuplicateMappingException::DuplicateMappingException(&pExceptionObject, v17, v16, v14);
    throw &pExceptionObject;
  }
  if ( falseToken._Mypair._Myval2._Mysize
    && !Notification::FieldParsers::TokenMatchParser<bool>::AddMapping(&booleanParser, &falseToken, 0) )
  {
    p_Data = &v34;
    std::wstring::wstring(&v34, &falseToken);
    v19 = v18;
    v33 = &v35;
    std::wstring::wstring(&v35, L"FalseToken");
    v21 = v20;
    v22 = (std::wstring *)(*((__int64 (__fastcall **)(const std::wstring *, std::wstring *))a3->_Mypair._Myval2._Bx._Ptr
                           + 1))(
                            a3,
                            &v32);
    Notification::DuplicateMappingException::DuplicateMappingException(&pExceptionObject, v22, v21, v19);
    throw &pExceptionObject;
  }
  if ( GroupId )
  {
    if ( !booleanParser.m_mappings._Mypair._Myval2._Myval2._Mysize )
    {
      p_Data = &v34;
      std::wstring::wstring(&v34, L"TrueToken/FalseToken");
      v27 = v26;
      v28 = (std::wstring *)(*((__int64 (__fastcall **)(const std::wstring *, std::wstring *))a3->_Mypair._Myval2._Bx._Ptr
                             + 1))(
                              a3,
                              &v35);
      Notification::MissingAttributeException::MissingAttributeException(
        (Notification::MissingAttributeException *)&pExceptionObject,
        v28,
        v27);
      throw (Notification::MissingAttributeException *)&pExceptionObject;
    }
    pExceptionObject.__vftable = FieldNode;
    p_Data = &pExceptionObject._Data;
    *(_QWORD *)&pExceptionObject.m_attribute._Mypair._Myval2._Bx._Alias[8] = 0;
    v23 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
    *v23 = std::_Func_impl_no_alloc<Notification::FieldParsers::TokenMatchParser<bool>,bool,std::wstring const &>::`vftable';
    Notification::FieldParsers::TokenMatchParser<bool>::TokenMatchParser<bool>(
      (Notification::FieldParsers::TokenMatchParser<bool> *)(v23 + 1),
      &booleanParser,
      v24);
    v30._Result = 0;
    `std::_Global_new<std::_Func_impl_no_alloc<Notification::FieldParsers::TokenMatchParser<bool>,bool,std::wstring const &>,Notification::FieldParsers::TokenMatchParser<bool> const &>'::`2'::_Guard_type::~_Guard_type(&v30);
    *(_QWORD *)&pExceptionObject.m_attribute._Mypair._Myval2._Bx._Alias[8] = v23;
    v25 = (*((__int64 (__fastcall **)(const std::wstring *, std::wstring *))a3->_Mypair._Myval2._Bx._Ptr + 1))(a3, &v34);
    anonymous_namespace_::FieldBindingsConfigurator::ValidateAndBindGroupParserForField__anonymous_namespace_::ValueSetter_bool___(
      (const std::wstring *)FieldValue._Ptr,
      v25,
      GroupId);
    std::wstring::_Tidy_deallocate(&v34);
    std::_Func_class<bool,std::wstring const &>::_Tidy((std::_Func_class<void,_WCM_DATAPLAN_STATUS &> *)&pExceptionObject._Data);
  }
  else
  {
    if ( booleanParser.m_mappings._Mypair._Myval2._Myval2._Mysize )
    {
      v29 = (std::wstring *)(*((__int64 (__fastcall **)(const std::wstring *, std::wstring *))a3->_Mypair._Myval2._Bx._Ptr
                             + 1))(
                              a3,
                              &v34);
      Notification::GroupAttributeMissingException::GroupAttributeMissingException(
        (Notification::GroupAttributeMissingException *)&pExceptionObject,
        v29);
      throw (Notification::GroupAttributeMissingException *)&pExceptionObject;
    }
    LOBYTE(FieldNode->~Notification::DuplicateMappingException) = BooleanValue;
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,enum Notification::PlanType>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,enum Notification::PlanType>,void *>>>(
    &booleanParser.m_mappings._Mypair._Myval2._Myval2,
    (std::allocator<std::_Tree_node<std::pair<std::wstring const ,bool>,void *> > *)&booleanParser);
  std::wstring::_Tidy_deallocate(&falseToken);
  std::wstring::_Tidy_deallocate(&trueToken);
}

```

## disassembly

```asm
0x18004ff04  mov     [rsp-8+arg_8], rbx
0x18004ff09  push    rbp
0x18004ff0a  push    rsi
0x18004ff0b  push    rdi
0x18004ff0c  push    r14
0x18004ff0e  push    r15
0x18004ff10  lea     rbp, [rsp-80h]
0x18004ff15  sub     rsp, 180h
0x18004ff1c  mov     rax, cs:__security_cookie
0x18004ff23  xor     rax, rsp
0x18004ff26  mov     [rbp+0A0h+var_28], rax
0x18004ff2a  mov     rsi, FieldNode
0x18004ff2d  mov     rbx, FieldValue
0x18004ff30  mov     r15, this
0x18004ff33  lea     FieldValue, aGroup; "Group"
0x18004ff3a  lea     this, [rsp+1A0h+var_170]; this
0x18004ff3f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ff44  nop
0x18004ff45  lea     FieldNode, [rsp+1A0h+var_170]
0x18004ff4a  mov     FieldValue, rsi; GroupAttributeName
0x18004ff4d  call    _anonymous_namespace___FieldBindingsConfigurator__GetGroupId
0x18004ff52  mov     r14, rax
0x18004ff55  lea     this, [rsp+1A0h+var_170]; this
0x18004ff5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ff5f  mov     this, [rsi]
0x18004ff62  mov     rdi, [this+38h]
0x18004ff66  lea     FieldValue, aTruetoken; "TrueToken"
0x18004ff6d  lea     this, [rsp+1A0h+var_170]; this
0x18004ff72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ff77  nop
0x18004ff78  lea     FieldNode, [rsp+1A0h+var_170]
0x18004ff7d  lea     FieldValue, [rbp+0A0h+trueToken]
0x18004ff81  mov     this, rsi
0x18004ff84  mov     rax, rdi
0x18004ff87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff8c  nop
0x18004ff8d  lea     this, [rsp+1A0h+var_170]; this
0x18004ff92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ff97  mov     rax, [rsi]
0x18004ff9a  mov     rdi, [rax+38h]
0x18004ff9e  lea     FieldValue, aFalsetoken; "FalseToken"
0x18004ffa5  lea     this, [rsp+1A0h+var_128]; this
0x18004ffaa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ffaf  nop
0x18004ffb0  lea     FieldNode, [rsp+1A0h+var_128]
0x18004ffb5  lea     FieldValue, [rbp+0A0h+falseToken]
0x18004ffb9  mov     this, rsi
0x18004ffbc  mov     rax, rdi
0x18004ffbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffc4  nop
0x18004ffc5  lea     this, [rsp+1A0h+var_128]; this
0x18004ffca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ffcf  mov     rax, [rsi]
0x18004ffd2  mov     rdi, [rax+38h]
0x18004ffd6  lea     FieldValue, aDefault_0; "Default"
0x18004ffdd  lea     this, [rsp+1A0h+var_170]; this
0x18004ffe2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ffe7  nop
0x18004ffe8  lea     FieldNode, [rsp+1A0h+var_170]
0x18004ffed  lea     FieldValue, [rsp+1A0h+var_148]
0x18004fff2  mov     this, rsi
0x18004fff5  mov     rax, rdi
0x18004fff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fffd  xor     edx, edx; defaultOnEmpty
0x18004ffff  mov     this, rax; s
0x180050002  call    _anonymous_namespace___GetBooleanValue
0x180050007  mov     dil, al
0x18005000a  lea     this, [rsp+1A0h+var_148]; this
0x18005000f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050014  nop
0x180050015  lea     this, [rsp+1A0h+var_170]; this
0x18005001a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005001f  xorps   xmm0, xmm0
0x180050022  xor     eax, eax
0x180050024  movups  xmmword ptr [rbp+0A0h+booleanParser.m_mappings._Mypair._Myval2._Myval2._Myhead], xmm0
0x180050028  mov     qword ptr [rbp+0A0h+booleanParser.m_default], rax
0x18005002c  mov     [rbp+0A0h+booleanParser.m_mappings._Mypair._Myval2._Myval2._Myhead], rax
0x180050030  mov     [rbp+0A0h+booleanParser.m_mappings._Mypair._Myval2._Myval2._Mysize], rax
0x180050034  lea     this, [rbp+0A0h+booleanParser]; this
0x180050038  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18005003d  mov     [rbp+0A0h+booleanParser.m_default], dil
0x180050041  cmp     [rbp+0A0h+trueToken._Mypair._Myval2._Mysize], 0
0x180050046  jz      loc_1800500D1
0x18005004c  mov     r8b, 1; Value
0x18005004f  lea     FieldValue, [rbp+0A0h+trueToken]; Token
0x180050053  lea     this, [rbp+0A0h+booleanParser]; this
0x180050057  call    ?AddMapping@?$TokenMatchParser@_N@FieldParsers@Notification@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Notification::FieldParsers::TokenMatchParser<bool>::AddMapping(std::wstring const &,bool)
0x18005005c  test    al, al
0x18005005e  jnz     short loc_1800500D1
0x180050060  lea     rax, [rsp+1A0h+var_148]
0x180050065  mov     [rsp+1A0h+var_180._Result], rax
0x18005006a  lea     FieldValue, [rbp+0A0h+trueToken]; _Right
0x18005006e  lea     this, [rsp+1A0h+var_148]; this
0x180050073  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180050078  mov     rdi, rax
0x18005007b  lea     rax, [rsp+1A0h+var_128]
0x180050080  mov     [rsp+1A0h+var_150], rax
0x180050085  lea     FieldValue, aTruetoken; "TrueToken"
0x18005008c  lea     this, [rsp+1A0h+var_128]; this
0x180050091  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180050096  mov     rbx, rax
0x180050099  mov     this, [rsi]
0x18005009c  mov     rax, [this+8]
0x1800500a0  lea     FieldValue, [rsp+1A0h+var_170]
0x1800500a5  mov     this, rsi
0x1800500a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500ad  nop
0x1800500ae  mov     r9, rdi
0x1800500b1  mov     FieldNode, rbx
0x1800500b4  mov     FieldValue, rax
0x1800500b7  lea     this, [rbp+0A0h+pExceptionObject]
0x1800500bb  call    ??0DuplicateMappingException@Notification@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; Notification::DuplicateMappingException::DuplicateMappingException(std::wstring,std::wstring,std::wstring)
0x1800500c0  lea     FieldValue, _TI3?AVDuplicateMappingException@Notification@@; pThrowInfo
0x1800500c7  lea     this, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800500cb  call    _CxxThrowException_0
0x1800500d1  cmp     [rbp+0A0h+falseToken._Mypair._Myval2._Mysize], 0
0x1800500d6  jz      loc_180050161
0x1800500dc  xor     r8d, r8d; Value
0x1800500df  lea     FieldValue, [rbp+0A0h+falseToken]; Token
0x1800500e3  lea     this, [rbp+0A0h+booleanParser]; this
0x1800500e7  call    ?AddMapping@?$TokenMatchParser@_N@FieldParsers@Notification@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Notification::FieldParsers::TokenMatchParser<bool>::AddMapping(std::wstring const &,bool)
0x1800500ec  test    al, al
0x1800500ee  jnz     short loc_180050161
0x1800500f0  lea     rax, [rsp+1A0h+var_148]
0x1800500f5  mov     [rsp+1A0h+var_178], rax
0x1800500fa  lea     FieldValue, [rbp+0A0h+falseToken]; _Right
0x1800500fe  lea     this, [rsp+1A0h+var_148]; this
0x180050103  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180050108  mov     rdi, rax
0x18005010b  lea     rax, [rsp+1A0h+var_128]
0x180050110  mov     [rsp+1A0h+var_150], rax
0x180050115  lea     FieldValue, aFalsetoken; "FalseToken"
0x18005011c  lea     this, [rsp+1A0h+var_128]; this
0x180050121  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180050126  mov     rbx, rax
0x180050129  mov     this, [rsi]
0x18005012c  mov     rax, [this+8]
0x180050130  lea     FieldValue, [rsp+1A0h+var_170]
0x180050135  mov     this, rsi
0x180050138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005013d  nop
0x18005013e  mov     r9, rdi
0x180050141  mov     FieldNode, rbx
0x180050144  mov     FieldValue, rax
0x180050147  lea     this, [rbp+0A0h+pExceptionObject]
0x18005014b  call    ??0DuplicateMappingException@Notification@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; Notification::DuplicateMappingException::DuplicateMappingException(std::wstring,std::wstring,std::wstring)
0x180050150  lea     FieldValue, _TI3?AVDuplicateMappingException@Notification@@; pThrowInfo
0x180050157  lea     this, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18005015b  call    _CxxThrowException_0
0x180050161  test    r14, r14
0x180050164  jz      loc_18005025B
0x18005016a  cmp     [rbp+0A0h+booleanParser.m_mappings._Mypair._Myval2._Myval2._Mysize], 0
0x18005016f  jz      loc_180050208
0x180050175  mov     [rbp+0A0h+pExceptionObject], rbx
0x180050179  lea     rax, [rbp+0A0h+var_F8]
0x18005017d  mov     [rsp+1A0h+var_178], rax
0x180050182  mov     qword ptr [rbp+0A0h+var_F8._Mystorage+38h], 0
0x18005018a  mov     ecx, 20h ; ' '; _Bytes
0x18005018f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180050194  mov     rbx, rax
0x180050197  mov     [rsp+1A0h+var_180._Result], rax
0x18005019c  lea     rax, ??_7?$_Func_impl_no_alloc@V?$TokenMatchParser@_N@FieldParsers@Notification@@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@6B@; const std::_Func_impl_no_alloc<Notification::FieldParsers::TokenMatchParser<bool>,bool,std::wstring const &>::`vftable'
0x1800501a3  mov     [rbx], rax
0x1800501a6  lea     this, [rbx+8]; this
0x1800501aa  lea     FieldValue, [rbp+0A0h+booleanParser]; __that
0x1800501ae  call    ??0?$TokenMatchParser@_N@FieldParsers@Notification@@QEAA@AEBV012@@Z; Notification::FieldParsers::TokenMatchParser<bool>::TokenMatchParser<bool>(Notification::FieldParsers::TokenMatchParser<bool> const &)
0x1800501b3  mov     [rsp+1A0h+var_180._Result], 0
0x1800501bc  lea     this, [rsp+1A0h+var_180]; this
0x1800501c1  call    ??1_Guard_type@?1???$_Global_new@V?$_Func_impl_no_alloc@V?$TokenMatchParser@_N@FieldParsers@Notification@@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$TokenMatchParser@_N@FieldParsers@Notification@@@std@@YAPEAV?$_Func_impl_no_alloc@V?$TokenMatchParser@_N@FieldParsers@Notification@@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEBV?$TokenMatchParser@_N@FieldParsers@Notification@@@Z@QEAA@XZ; `std::_Global_new<std::_Func_impl_no_alloc<Notification::FieldParsers::TokenMatchParser<bool>,bool,std::wstring const &>,Notification::FieldParsers::TokenMatchParser<bool> const &>(Notification::FieldParsers::TokenMatchParser<bool> const &)'::`2'::_Guard_type::~_Guard_type(void)
0x1800501c6  mov     qword ptr [rbp+0A0h+var_F8._Mystorage+38h], rbx
0x1800501ca  mov     rax, [rsi]
0x1800501cd  lea     FieldValue, [rsp+1A0h+var_148]
0x1800501d2  mov     this, rsi
0x1800501d5  mov     rax, [rax+8]
0x1800501d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501de  nop
0x1800501df  lea     r9, [rbp+0A0h+pExceptionObject]
0x1800501e3  mov     FieldNode, r14; parser
0x1800501e6  mov     FieldValue, rax; GroupId
0x1800501e9  mov     this, r15; Field
0x1800501ec  call    _anonymous_namespace___FieldBindingsConfigurator__ValidateAndBindGroupParserForField__anonymous_namespace___ValueSetter_bool___
0x1800501f1  nop
0x1800501f2  lea     this, [rsp+1A0h+var_148]; this
0x1800501f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800501fc  nop
0x1800501fd  lea     this, [rbp+0A0h+var_F8]; this
0x180050201  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180050206  jmp     short loc_180050265
0x180050208  lea     rax, [rsp+1A0h+var_148]
0x18005020d  mov     [rsp+1A0h+var_178], rax
0x180050212  lea     FieldValue, aTruetokenFalse; "TrueToken/FalseToken"
0x180050219  lea     this, [rsp+1A0h+var_148]; this
0x18005021e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180050223  mov     rbx, rax
0x180050226  mov     this, [rsi]
0x180050229  mov     rax, [this+8]
0x18005022d  lea     FieldValue, [rsp+1A0h+var_128]
0x180050232  mov     this, rsi
0x180050235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005023a  nop
0x18005023b  mov     FieldNode, rbx
0x18005023e  mov     FieldValue, rax
0x180050241  lea     this, [rbp+0A0h+pExceptionObject]
0x180050245  call    ??0MissingAttributeException@Notification@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Notification::MissingAttributeException::MissingAttributeException(std::wstring,std::wstring)
0x18005024a  lea     FieldValue, _TI3?AVMissingAttributeException@Notification@@; pThrowInfo
0x180050251  lea     this, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x180050255  call    _CxxThrowException_0
0x18005025b  cmp     [rbp+0A0h+booleanParser.m_mappings._Mypair._Myval2._Myval2._Mysize], 0
0x180050260  jnz     short loc_1800502A9
0x180050262  mov     [rbx], dil
0x180050265  lea     FieldValue, [rbp+0A0h+booleanParser]; _Al
0x180050269  lea     this, [rbp+0A0h+booleanParser]; this
0x18005026d  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PlanType@Notification@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PlanType@Notification@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PlanType@Notification@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Notification::PlanType>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,Notification::PlanType>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,Notification::PlanType>,void *>> &)
0x180050272  nop
0x180050273  lea     this, [rbp+0A0h+falseToken]; this
0x180050277  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005027c  nop
0x18005027d  lea     this, [rbp+0A0h+trueToken]; this
0x180050281  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050286  mov     this, [rbp+0A0h+var_28]
0x18005028a  xor     this, rsp; StackCookie
0x18005028d  call    __security_check_cookie
0x180050292  mov     rbx, [rsp+1A0h+arg_8]
0x18005029a  add     rsp, 180h
0x1800502a1  pop     r15
0x1800502a3  pop     r14
0x1800502a5  pop     rdi
0x1800502a6  pop     rsi
0x1800502a7  pop     rbp
0x1800502a8  retn
0x1800502a9  mov     rax, [rsi]
0x1800502ac  lea     FieldValue, [rsp+1A0h+var_148]
0x1800502b1  mov     this, rsi
0x1800502b4  mov     rax, [rax+8]
0x1800502b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502bd  mov     FieldValue, rax
0x1800502c0  lea     this, [rbp+0A0h+pExceptionObject]
0x1800502c4  call    ??0GroupAttributeMissingException@Notification@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Notification::GroupAttributeMissingException::GroupAttributeMissingException(std::wstring)
0x1800502c9  lea     FieldValue, _TI4?AVGroupAttributeMissingException@Notification@@; pThrowInfo
0x1800502d0  lea     this, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800502d4  call    _CxxThrowException_0
```
