# Notification::Configuration::RegistryNode::GetChild(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180056150`
- end: `0x18005625b`
- name: `?GetChild@RegistryNode@Configuration@Notification@@UEBA?AV?$shared_ptr@VNode@Configuration@Notification@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z`
- size: `267`
- prototype: `std::shared_ptr<Notification::Configuration::Node> *__fastcall(Notification::Configuration::RegistryNode *this, std::shared_ptr<Notification::Configuration::Node> *result, const std::wstring *Name)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180002790`
- `0x18000fa6c`
- `0x180011844`
- `0x180012bc8`
- `0x180055b58`
- `0x180056150`
- `0x180056a90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800561bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800561bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800561c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::shared_ptr<Notification::Configuration::RegistryNode> *__fastcall Notification::Configuration::RegistryNode::GetChild(
        Notification::Configuration::RegistryNode *this,
        std::shared_ptr<Notification::Configuration::RegistryNode> *result,
        const std::wstring *Name)
{
  std::_String_val<std::_Simple_types<unsigned short> > *v5; // rcx
  const WCHAR *v6; // rax
  std::shared_ptr<Notification::Configuration::RegistryNode> *v7; // rax
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+38h] [rbp-48h] BYREF
  std::shared_ptr<Notification::Configuration::RegistryNode> resulta; // [rsp+50h] [rbp-30h] BYREF
  HKEY__ *childKey[2]; // [rsp+60h] [rbp-20h] BYREF

  childKey[0] = (HKEY__ *)result;
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::equal_range(
    &this->m_childNameCache,
    (std::pair<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const ,std::wstring > > > >,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const ,std::wstring > > > > > *)childKey,
    Name);
  v5 = (std::_String_val<std::_Simple_types<unsigned short> > *)childKey[0];
  if ( childKey[0] == childKey[1]
    || (childKey[0] = 0,
        v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5 + 2),
        RegOpenKeyExW(this->m_key, v6, 0, 0x20019u, childKey)) )
  {
    result->_Ptr = 0;
    result->_Rep = 0;
  }
  else
  {
    j.dismissed_ = 0;
    j.fun_ = (void (__fastcall *)(void *))RegCloseKey;
    j.p1_ = (WWAN_INTERFACE_OBJECT *const)childKey[0];
    v7 = std::make_shared<Notification::Configuration::RegistryNode,HKEY__ * &>(&resulta, childKey);
    result->_Ptr = 0;
    result->_Rep = 0;
    *result = *v7;
    v7->_Ptr = 0;
    v7->_Rep = 0;
    if ( resulta._Rep )
      std::_Ref_count_base::_Decref(resulta._Rep);
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
  }
  return result;
}

```

## disassembly

```asm
0x180056150  push    rbp
0x180056152  push    rbx
0x180056153  push    rdi
0x180056154  mov     rbp, rsp
0x180056157  sub     rsp, 80h
0x18005615e  mov     rax, cs:__security_cookie
0x180056165  xor     rax, rsp
0x180056168  mov     [rbp+var_10], rax
0x18005616c  mov     rbx, rdx
0x18005616f  mov     rdi, this
0x180056172  mov     [rbp+childKey], rdx
0x180056176  add     this, 30h ; '0'; this
0x18005617a  lea     rdx, [rbp+childKey]; result
0x18005617e  call    ?equal_range@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$00@std@@@std@@QEBA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,1>>::equal_range(std::wstring const &)
0x180056183  mov     this, [rbp+childKey]
0x180056187  cmp     this, [rbp+var_18]
0x18005618b  jz      loc_180056232
0x180056191  mov     [rbp+childKey], 0
0x180056199  add     this, 40h ; '@'; this
0x18005619d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800561a2  lea     this, [rbp+childKey]
0x1800561a6  mov     [rsp+80h+phkResult], this; phkResult
0x1800561ab  mov     r9d, 20019h; samDesired
0x1800561b1  xor     r8d, r8d; ulOptions
0x1800561b4  mov     rdx, rax; lpSubKey
0x1800561b7  mov     this, [rdi+8]; hKey
0x1800561bb  call    cs:__imp_RegOpenKeyExW
0x1800561c1  test    eax, eax
0x1800561c3  jnz     short loc_180056232
0x1800561c5  mov     this, [rbp+childKey]
0x1800561c9  mov     rax, cs:__imp_RegCloseKey
0x1800561d0  mov     [rbp+j.dismissed_], 0
0x1800561d4  mov     [rbp+j.fun_], rax
0x1800561d8  mov     [rbp+j.p1_], this
0x1800561dc  lea     rdx, [rbp+childKey]; <_Args_0>
0x1800561e0  lea     this, [rbp+result]; result
0x1800561e4  call    ??$make_shared@VRegistryNode@Configuration@Notification@@AEAPEAUHKEY__@@@std@@YA?AV?$shared_ptr@VRegistryNode@Configuration@Notification@@@0@AEAPEAUHKEY__@@@Z; std::make_shared<Notification::Configuration::RegistryNode,HKEY__ * &>(HKEY__ * &)
0x1800561e9  mov     rdx, rax
0x1800561ec  mov     qword ptr [rbx], 0
0x1800561f3  mov     qword ptr [rbx+8], 0
0x1800561fb  mov     rax, [rax]
0x1800561fe  mov     [rbx], rax
0x180056201  mov     this, [rdx+8]
0x180056205  mov     [rbx+8], this
0x180056209  mov     qword ptr [rdx], 0
0x180056210  mov     qword ptr [rdx+8], 0
0x180056218  mov     this, [rbp+result._Rep]; this
0x18005621c  test    this, this
0x18005621f  jz      short loc_180056227
0x180056221  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180056226  nop
0x180056227  lea     this, [rbp+j]; j
0x18005622b  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180056230  jmp     short loc_180056241
0x180056232  mov     qword ptr [rbx], 0
0x180056239  mov     qword ptr [rbx+8], 0
0x180056241  mov     rax, rbx
0x180056244  mov     this, [rbp+var_10]
0x180056248  xor     this, rsp; StackCookie
0x18005624b  call    __security_check_cookie
0x180056250  add     rsp, 80h
0x180056257  pop     rdi
0x180056258  pop     rbx
0x180056259  pop     rbp
0x18005625a  retn
```
