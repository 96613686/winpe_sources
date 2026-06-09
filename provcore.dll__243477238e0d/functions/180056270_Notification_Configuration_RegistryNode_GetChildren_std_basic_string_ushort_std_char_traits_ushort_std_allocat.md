# Notification::Configuration::RegistryNode::GetChildren(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180056270`
- end: `0x1800563cc`
- name: `?GetChildren@RegistryNode@Configuration@Notification@@UEBA?AV?$vector@V?$shared_ptr@VNode@Configuration@Notification@@@std@@V?$allocator@V?$shared_ptr@VNode@Configuration@Notification@@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z`
- size: `348`
- prototype: `std::vector<std::shared_ptr<Notification::Configuration::Node>> *__fastcall(Notification::Configuration::RegistryNode *this, std::vector<std::shared_ptr<Notification::Configuration::Node>> *result, const std::wstring *Name)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002790`
- `0x18000b178`
- `0x18000fa6c`
- `0x180011844`
- `0x180012bc8`
- `0x18002784c`
- `0x18002797c`
- `0x180055b58`
- `0x180055ef8`
- `0x180056270`
- `0x180056a90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800562ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800562ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056311`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
std::vector<_GUID> *__fastcall Notification::Configuration::RegistryNode::GetChildren(
        Notification::Configuration::RegistryNode *this,
        std::vector<_GUID> *result,
        const std::wstring *Name)
{
  const std::wstring *v5; // r8
  const WCHAR *v6; // rax
  std::shared_ptr<Notification::Configuration::Node> *v7; // rax
  std::shared_ptr<Notification::Configuration::Node> *Mylast; // rcx
  std::shared_ptr<Notification::Configuration::Node> v10; // [rsp+38h] [rbp-21h] BYREF
  std::pair<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const ,std::wstring > > > >,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const ,std::wstring > > > > > range; // [rsp+48h] [rbp-11h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+58h] [rbp-1h] BYREF
  std::vector<_GUID> *v13; // [rsp+70h] [rbp+17h]
  std::shared_ptr<Notification::Configuration::RegistryNode> resulta; // [rsp+78h] [rbp+1Fh] BYREF
  HKEY__ *childKey; // [rsp+88h] [rbp+2Fh] BYREF

  v13 = result;
  *(_OWORD *)&result->_Mypair._Myval2._Myfirst = 0;
  result->_Mypair._Myval2._Myend = 0;
  std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(result);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::equal_range(
    &this->m_childNameCache,
    &range,
    v5);
  while ( range.first._Ptr != range.second._Ptr )
  {
    childKey = 0;
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&range.first._Ptr->_Myval.second._Mypair._Myval2);
    if ( !RegOpenKeyExW(this->m_key, v6, 0, 0x20019u, &childKey) )
    {
      j.dismissed_ = 0;
      j.fun_ = (void (__fastcall *)(void *))RegCloseKey;
      j.p1_ = (WWAN_INTERFACE_OBJECT *const)childKey;
      v7 = (std::shared_ptr<Notification::Configuration::Node> *)std::make_shared<Notification::Configuration::RegistryNode,HKEY__ * &>(
                                                                   &resulta,
                                                                   &childKey);
      v10 = *v7;
      v7->_Ptr = 0;
      v7->_Rep = 0;
      Mylast = (std::shared_ptr<Notification::Configuration::Node> *)result->_Mypair._Myval2._Mylast;
      if ( Mylast == (std::shared_ptr<Notification::Configuration::Node> *)result->_Mypair._Myval2._Myend )
      {
        std::vector<std::shared_ptr<Handler::Interface>>::_Emplace_reallocate<std::shared_ptr<Handler::Interface>>(
          (std::vector<std::shared_ptr<Notification::Configuration::Node>> *)result,
          (std::shared_ptr<Notification::Configuration::Node> *const)result->_Mypair._Myval2._Mylast,
          &v10);
      }
      else
      {
        std::_Construct_in_place<std::shared_ptr<Handler::Interface>,std::shared_ptr<Handler::Interface>>(Mylast, &v10);
        ++result->_Mypair._Myval2._Mylast;
      }
      if ( v10._Rep )
        std::_Ref_count_base::_Decref(v10._Rep);
      if ( resulta._Rep )
        std::_Ref_count_base::_Decref(resulta._Rep);
      ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(&range.first);
  }
  return result;
}

```

## disassembly

```asm
0x180056270  push    rbp
0x180056272  push    rbx
0x180056273  push    rdi
0x180056274  lea     rbp, [rsp-47h]
0x180056279  sub     rsp, 0A0h
0x180056280  mov     rax, cs:__security_cookie
0x180056287  xor     rax, rsp
0x18005628a  mov     [rbp+57h+var_20], rax
0x18005628e  mov     rbx, rdx
0x180056291  mov     rdi, this
0x180056294  mov     [rbp+57h+var_40], rdx
0x180056298  mov     [rbp+57h+var_80], 0
0x18005629f  xorps   xmm0, xmm0
0x1800562a2  xor     eax, eax
0x1800562a4  movups  xmmword ptr [rdx], xmm0
0x1800562a7  mov     [rdx+10h], rax
0x1800562ab  mov     this, rdx; this
0x1800562ae  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x1800562b3  mov     [rbp+57h+var_80], 1
0x1800562ba  lea     this, [rdi+30h]; this
0x1800562be  lea     rdx, [rbp+57h+range]; result
0x1800562c2  call    ?equal_range@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$00@std@@@std@@QEBA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::equal_range(std::wstring const &)
0x1800562c7  mov     this, [rbp+57h+range.first._Ptr]
0x1800562cb  cmp     this, [rbp+57h+range.second._Ptr]
0x1800562cf  jz      loc_1800563B1
0x1800562d5  mov     [rbp+57h+childKey], 0
0x1800562dd  add     this, 40h ; '@'; this
0x1800562e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800562e6  lea     this, [rbp+57h+childKey]
0x1800562ea  mov     [rsp+0B0h+phkResult], this; phkResult
0x1800562ef  mov     r9d, 20019h; samDesired
0x1800562f5  xor     r8d, r8d; ulOptions
0x1800562f8  mov     rdx, rax; lpSubKey
0x1800562fb  mov     this, [rdi+8]; hKey
0x1800562ff  call    cs:__imp_RegOpenKeyExW
0x180056305  test    eax, eax
0x180056307  jnz     loc_1800563A3
0x18005630d  mov     this, [rbp+57h+childKey]
0x180056311  mov     rax, cs:__imp_RegCloseKey
0x180056318  mov     [rbp+57h+j.dismissed_], 0
0x18005631c  mov     [rbp+57h+j.fun_], rax
0x180056320  mov     [rbp+57h+j.p1_], this
0x180056324  lea     rdx, [rbp+57h+childKey]; <_Args_0>
0x180056328  lea     this, [rbp+57h+result]; result
0x18005632c  call    ??$make_shared@VRegistryNode@Configuration@Notification@@AEAPEAUHKEY__@@@std@@YA?AV?$shared_ptr@VRegistryNode@Configuration@Notification@@@0@AEAPEAUHKEY__@@@Z; std::make_shared<Notification::Configuration::RegistryNode,HKEY__ * &>(HKEY__ * &)
0x180056331  mov     this, rax
0x180056334  mov     rax, [rax]
0x180056337  mov     [rbp+57h+var_78._Ptr], rax
0x18005633b  mov     rax, [this+8]
0x18005633f  mov     [rbp+57h+var_78._Rep], rax
0x180056343  mov     qword ptr [this], 0
0x18005634a  mov     qword ptr [this+8], 0
0x180056352  mov     this, [rbx+8]; _Obj
0x180056356  cmp     this, [rbx+10h]
0x18005635a  jz      short loc_18005636C
0x18005635c  lea     rdx, [rbp+57h+var_78]; <_Args_0>
0x180056360  call    ??$_Construct_in_place@V?$shared_ptr@VInterface@Handler@@@std@@V12@@std@@YAXAEAV?$shared_ptr@VInterface@Handler@@@0@$$QEAV10@@Z; std::_Construct_in_place<std::shared_ptr<Handler::Interface>,std::shared_ptr<Handler::Interface>>(std::shared_ptr<Handler::Interface> &,std::shared_ptr<Handler::Interface> &&)
0x180056365  add     qword ptr [rbx+8], 10h
0x18005636a  jmp     short loc_18005637C
0x18005636c  lea     Name, [rbp+57h+var_78]; <_Val_0>
0x180056370  mov     rdx, this; _Whereptr
0x180056373  mov     this, rbx; this
0x180056376  call    ??$_Emplace_reallocate@V?$shared_ptr@VInterface@Handler@@@std@@@?$vector@V?$shared_ptr@VInterface@Handler@@@std@@V?$allocator@V?$shared_ptr@VInterface@Handler@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VInterface@Handler@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<Handler::Interface>>::_Emplace_reallocate<std::shared_ptr<Handler::Interface>>(std::shared_ptr<Handler::Interface> * const,std::shared_ptr<Handler::Interface> &&)
0x18005637b  nop
0x18005637c  mov     this, [rbp+57h+var_78._Rep]; this
0x180056380  test    this, this
0x180056383  jz      short loc_18005638B
0x180056385  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005638a  nop
0x18005638b  mov     this, [rbp+57h+result._Rep]; this
0x18005638f  test    this, this
0x180056392  jz      short loc_18005639A
0x180056394  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180056399  nop
0x18005639a  lea     this, [rbp+57h+j]; j
0x18005639e  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x1800563a3  lea     this, [rbp+57h+range]; this
0x1800563a7  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x1800563ac  jmp     loc_1800562C7
0x1800563b1  mov     rax, rbx
0x1800563b4  mov     this, [rbp+57h+var_20]
0x1800563b8  xor     this, rsp; StackCookie
0x1800563bb  call    __security_check_cookie
0x1800563c0  add     rsp, 0A0h
0x1800563c7  pop     rdi
0x1800563c8  pop     rbx
0x1800563c9  pop     rbp
0x1800563ca  retn
```
