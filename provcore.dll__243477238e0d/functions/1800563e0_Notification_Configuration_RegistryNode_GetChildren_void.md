# Notification::Configuration::RegistryNode::GetChildren(void)

- ea: `0x1800563e0`
- end: `0x18005654b`
- name: `?GetChildren@RegistryNode@Configuration@Notification@@UEBA?AV?$vector@V?$shared_ptr@VNode@Configuration@Notification@@@std@@V?$allocator@V?$shared_ptr@VNode@Configuration@Notification@@@std@@@2@@std@@XZ`
- size: `363`
- prototype: `std::vector<std::shared_ptr<Notification::Configuration::Node>> *__fastcall(Notification::Configuration::RegistryNode *this, std::vector<std::shared_ptr<Notification::Configuration::Node>> *result)`
- caller_count: `0`
- callee_count: `10`
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
- `0x1800563e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056470`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056482`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
std::vector<_GUID> *__fastcall Notification::Configuration::RegistryNode::GetChildren(
        Notification::Configuration::RegistryNode *this,
        std::vector<_GUID> *result)
{
  std::_Tree_node<std::pair<std::wstring const ,std::wstring >,void *> *Left; // rcx
  const WCHAR *v5; // rax
  std::shared_ptr<Notification::Configuration::Node> *v6; // rax
  std::shared_ptr<Notification::Configuration::Node> *Mylast; // rcx
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const ,std::wstring > > >,std::_Iterator_base0> v9; // [rsp+38h] [rbp-1h] BYREF
  std::shared_ptr<Notification::Configuration::Node> v10; // [rsp+40h] [rbp+7h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+50h] [rbp+17h] BYREF
  std::vector<_GUID> *v12; // [rsp+68h] [rbp+2Fh]
  std::shared_ptr<Notification::Configuration::RegistryNode> resulta; // [rsp+70h] [rbp+37h] BYREF
  HKEY__ *childKey; // [rsp+80h] [rbp+47h] BYREF

  v12 = result;
  *(_OWORD *)&result->_Mypair._Myval2._Myfirst = 0;
  result->_Mypair._Myval2._Myend = 0;
  std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(result);
  Left = this->m_childNameCache._Mypair._Myval2._Myval2._Myhead->_Left;
  v9._Ptr = Left;
  while ( !Left->_Isnil )
  {
    childKey = 0;
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Left->_Myval.second._Mypair._Myval2);
    if ( !RegOpenKeyExW(this->m_key, v5, 0, 0x20019u, &childKey) )
    {
      j.dismissed_ = 0;
      j.fun_ = (void (__fastcall *)(void *))RegCloseKey;
      j.p1_ = (WWAN_INTERFACE_OBJECT *const)childKey;
      v6 = (std::shared_ptr<Notification::Configuration::Node> *)std::make_shared<Notification::Configuration::RegistryNode,HKEY__ * &>(
                                                                   &resulta,
                                                                   &childKey);
      v10 = *v6;
      v6->_Ptr = 0;
      v6->_Rep = 0;
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
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(&v9);
    Left = v9._Ptr;
  }
  return result;
}

```

## disassembly

```asm
0x1800563e0  mov     [rsp-8+arg_10], rbx
0x1800563e5  mov     [rsp-8+arg_18], rdi
0x1800563ea  push    rbp
0x1800563eb  lea     rbp, [rsp-57h]
0x1800563f0  sub     rsp, 90h
0x1800563f7  mov     rax, cs:__security_cookie
0x1800563fe  xor     rax, rsp
0x180056401  mov     [rbp+57h+var_8], rax
0x180056405  mov     rbx, rdx
0x180056408  mov     rdi, this
0x18005640b  mov     [rbp+57h+var_28], rdx
0x18005640f  mov     [rbp+57h+var_60], 0
0x180056416  xorps   xmm0, xmm0
0x180056419  xor     eax, eax
0x18005641b  movups  xmmword ptr [rdx], xmm0
0x18005641e  mov     [rdx+10h], rax
0x180056422  mov     this, rdx; this
0x180056425  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18005642a  mov     [rbp+57h+var_60], 1
0x180056431  mov     this, [rdi+30h]
0x180056435  mov     this, [this]
0x180056438  mov     [rbp+57h+var_58._Ptr], this
0x18005643c  cmp     byte ptr [this+19h], 0
0x180056440  jnz     loc_180056526
0x180056446  mov     [rbp+57h+childKey], 0
0x18005644e  add     this, 40h ; '@'; this
0x180056452  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056457  lea     this, [rbp+57h+childKey]
0x18005645b  mov     [rsp+90h+phkResult], this; phkResult
0x180056460  mov     r9d, 20019h; samDesired
0x180056466  xor     r8d, r8d; ulOptions
0x180056469  mov     rdx, rax; lpSubKey
0x18005646c  mov     this, [rdi+8]; hKey
0x180056470  call    cs:__imp_RegOpenKeyExW
0x180056476  test    eax, eax
0x180056478  jnz     loc_180056514
0x18005647e  mov     this, [rbp+57h+childKey]
0x180056482  mov     rax, cs:__imp_RegCloseKey
0x180056489  mov     [rbp+57h+j.dismissed_], 0
0x18005648d  mov     [rbp+57h+j.fun_], rax
0x180056491  mov     [rbp+57h+j.p1_], this
0x180056495  lea     rdx, [rbp+57h+childKey]; <_Args_0>
0x180056499  lea     this, [rbp+57h+result]; result
0x18005649d  call    ??$make_shared@VRegistryNode@Configuration@Notification@@AEAPEAUHKEY__@@@std@@YA?AV?$shared_ptr@VRegistryNode@Configuration@Notification@@@0@AEAPEAUHKEY__@@@Z; std::make_shared<Notification::Configuration::RegistryNode,HKEY__ * &>(HKEY__ * &)
0x1800564a2  mov     this, rax
0x1800564a5  mov     rax, [rax]
0x1800564a8  mov     [rbp+57h+var_50._Ptr], rax
0x1800564ac  mov     rax, [this+8]
0x1800564b0  mov     [rbp+57h+var_50._Rep], rax
0x1800564b4  mov     qword ptr [this], 0
0x1800564bb  mov     qword ptr [this+8], 0
0x1800564c3  mov     this, [rbx+8]; _Obj
0x1800564c7  cmp     this, [rbx+10h]
0x1800564cb  jz      short loc_1800564DD
0x1800564cd  lea     rdx, [rbp+57h+var_50]; <_Args_0>
0x1800564d1  call    ??$_Construct_in_place@V?$shared_ptr@VInterface@Handler@@@std@@V12@@std@@YAXAEAV?$shared_ptr@VInterface@Handler@@@0@$$QEAV10@@Z; std::_Construct_in_place<std::shared_ptr<Handler::Interface>,std::shared_ptr<Handler::Interface>>(std::shared_ptr<Handler::Interface> &,std::shared_ptr<Handler::Interface> &&)
0x1800564d6  add     qword ptr [rbx+8], 10h
0x1800564db  jmp     short loc_1800564ED
0x1800564dd  lea     r8, [rbp+57h+var_50]; <_Val_0>
0x1800564e1  mov     rdx, this; _Whereptr
0x1800564e4  mov     this, rbx; this
0x1800564e7  call    ??$_Emplace_reallocate@V?$shared_ptr@VInterface@Handler@@@std@@@?$vector@V?$shared_ptr@VInterface@Handler@@@std@@V?$allocator@V?$shared_ptr@VInterface@Handler@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VInterface@Handler@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<Handler::Interface>>::_Emplace_reallocate<std::shared_ptr<Handler::Interface>>(std::shared_ptr<Handler::Interface> * const,std::shared_ptr<Handler::Interface> &&)
0x1800564ec  nop
0x1800564ed  mov     this, [rbp+57h+var_50._Rep]; this
0x1800564f1  test    this, this
0x1800564f4  jz      short loc_1800564FC
0x1800564f6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800564fb  nop
0x1800564fc  mov     this, [rbp+57h+result._Rep]; this
0x180056500  test    this, this
0x180056503  jz      short loc_18005650B
0x180056505  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005650a  nop
0x18005650b  lea     this, [rbp+57h+j]; j
0x18005650f  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180056514  lea     this, [rbp+57h+var_58]; this
0x180056518  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x18005651d  mov     this, [rbp+57h+var_58._Ptr]
0x180056521  jmp     loc_18005643C
0x180056526  mov     rax, rbx
0x180056529  mov     this, [rbp+57h+var_8]
0x18005652d  xor     this, rsp; StackCookie
0x180056530  call    __security_check_cookie
0x180056535  lea     r11, [rsp+90h+var_s0]
0x18005653d  mov     rbx, [r11+20h]
0x180056541  mov     rdi, [r11+28h]
0x180056545  mov     rsp, r11
0x180056548  pop     rbp
0x180056549  retn
```
