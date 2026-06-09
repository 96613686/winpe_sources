# CheckProfileExistenceAndGetConnectionMode(void *,_GUID const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180041e3c`
- end: `0x180042047`
- name: `?CheckProfileExistenceAndGetConnectionMode@@YAHPEAXPEBU_GUID@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `523`
- prototype: `int __fastcall(void *hClientHandle, const _GUID *pInterfaceGuid, const wchar_t *strProfileName, std::wstring *ConnectionModeStr)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041a34`

## callees

- `0x180002790`
- `0x18000af94`
- `0x18000b8c0`
- `0x18000fa6c`
- `0x180010984`
- `0x180011cfc`
- `0x180012748`
- `0x180012bc8`
- `0x180020c48`
- `0x180041e3c`
- `0x180048194`
- `0x180048f28`
- `0x1800498dc`
- `0x180049d4c`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfile` at `0x180041e98`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfile` at `0x180041e98`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180041ee7`

## string_xrefs

- `0x180041f26`: `http://www.microsoft.com/networking/WWAN/profile/v1`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CheckProfileExistenceAndGetConnectionMode(
        void *hClientHandle,
        const _GUID *pInterfaceGuid,
        const wchar_t *strProfileName,
        std::wstring *ConnectionModeStr)
{
  unsigned int _a3; // eax
  WcmCommon::Xml::Document *Ptr; // rbx
  WcmCommon::Xml::Document *v10; // rbx
  std::wstring *Text; // rax
  std::shared_ptr<WcmCommon::Xml::Document> xmlDoc; // [rsp+40h] [rbp-69h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> connectionModeNode; // [rsp+50h] [rbp-59h] BYREF
  std::wstring ns; // [rsp+70h] [rbp-39h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+90h] [rbp-19h] BYREF
  std::wstring Xml; // [rsp+A8h] [rbp-1h] BYREF
  wchar_t *ProfileXml; // [rsp+C8h] [rbp+1Fh] BYREF
  unsigned int pdwFlags; // [rsp+D0h] [rbp+27h] BYREF

  ProfileXml = 0;
  pdwFlags = 0;
  _a3 = WwanGetProfile(hClientHandle, &GUID_NULL, strProfileName, 0, &ProfileXml, &pdwFlags, 0);
  if ( _a3 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
    {
      WPP_SF_S_guid_D(
        WPP_GLOBAL_Control->Control.Logger,
        0xAu,
        WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids,
        strProfileName,
        pInterfaceGuid,
        _a3);
    }
    return 0;
  }
  else
  {
    j.dismissed_ = 0;
    j.fun_ = (void (__fastcall *)(void *))WwanFreeMemory;
    j.p1_ = (WWAN_INTERFACE_OBJECT *const)ProfileXml;
    xmlDoc = 0;
    std::wstring::wstring(&Xml, ProfileXml);
    WcmCommon::Xml::Document::LoadFromString(&xmlDoc, &Xml);
    std::wstring::_Tidy_deallocate(&Xml);
    Ptr = xmlDoc._Ptr;
    std::wstring::wstring(&ns, L"http://www.microsoft.com/networking/WWAN/profile/v1");
    std::wstring::wstring((std::wstring *)&connectionModeNode, L"default");
    WcmCommon::Xml::Document::AddSelectionNamespace(Ptr, (const std::wstring *)&connectionModeNode, &ns);
    std::wstring::_Tidy_deallocate((std::wstring *)&connectionModeNode);
    std::wstring::_Tidy_deallocate(&ns);
    connectionModeNode = 0;
    v10 = xmlDoc._Ptr;
    std::wstring::wstring(&ns, L"./default:ConnectionMode");
    WcmCommon::Xml::Document::SelectSingle(v10, &connectionModeNode, &ns);
    std::wstring::_Tidy_deallocate(&ns);
    if ( connectionModeNode._Ptr )
    {
      Text = WcmCommon::Xml::Node::GetText(connectionModeNode._Ptr, &Xml);
      std::wstring::operator=(ConnectionModeStr, Text);
      std::wstring::_Tidy_deallocate(&Xml);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids);
      }
      std::wstring::_Eos(ConnectionModeStr, 0);
    }
    if ( connectionModeNode._Rep )
      std::_Ref_count_base::_Decref(connectionModeNode._Rep);
    if ( xmlDoc._Rep )
      std::_Ref_count_base::_Decref(xmlDoc._Rep);
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
    return 1;
  }
}

```

## disassembly

```asm
0x180041e3c  push    rbp
0x180041e3e  push    rbx
0x180041e3f  push    rsi
0x180041e40  push    rdi
0x180041e41  lea     rbp, [rsp-3Fh]
0x180041e46  sub     rsp, 0E8h
0x180041e4d  mov     rax, cs:__security_cookie
0x180041e54  xor     rax, rsp
0x180041e57  mov     [rbp+57h+var_28], rax
0x180041e5b  mov     rdi, ConnectionModeStr
0x180041e5e  mov     rbx, strProfileName
0x180041e61  mov     rsi, pInterfaceGuid
0x180041e64  mov     [rbp+57h+ProfileXml], 0
0x180041e6c  mov     [rbp+57h+pdwFlags], 0
0x180041e73  mov     [rsp+100h+var_D0], 0
0x180041e7c  lea     rax, [rbp+57h+pdwFlags]
0x180041e80  mov     qword ptr [rsp+100h+_a3], rax
0x180041e85  lea     rax, [rbp+57h+ProfileXml]
0x180041e89  mov     [rsp+100h+_a2], rax
0x180041e8e  xor     r9d, r9d
0x180041e91  lea     pInterfaceGuid, GUID_NULL
0x180041e98  call    cs:__imp_WwanGetProfile
0x180041e9e  test    eax, eax
0x180041ea0  jz      short loc_180041EE3
0x180041ea2  lea     pInterfaceGuid, WPP_GLOBAL_Control; __annotation("TMF:",
0x180041ea9  mov     hClientHandle, cs:WPP_GLOBAL_Control
0x180041eb0  cmp     hClientHandle, pInterfaceGuid
0x180041eb3  jz      short loc_180041EDC
0x180041eb5  test    byte ptr [hClientHandle+1Ch], 8
0x180041eb9  jz      short loc_180041EDC
0x180041ebb  mov     edx, 0Ah; id
0x180041ec0  mov     [rsp+100h+_a3], eax; _a3
0x180041ec4  mov     [rsp+100h+_a2], rsi; _a2
0x180041ec9  mov     ConnectionModeStr, rbx; _a1
0x180041ecc  lea     strProfileName, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180041ed3  mov     hClientHandle, [hClientHandle+10h]; Logger
0x180041ed7  call    WPP_SF_S_guid_D
0x180041edc  xor     eax, eax
0x180041ede  jmp     loc_18004202F
0x180041ee3  mov     pInterfaceGuid, [rbp+57h+ProfileXml]; _Ptr
0x180041ee7  mov     rax, cs:__imp_WwanFreeMemory
0x180041eee  mov     [rbp+57h+j.dismissed_], 0
0x180041ef2  mov     [rbp+57h+j.fun_], rax
0x180041ef6  mov     [rbp+57h+j.p1_], pInterfaceGuid
0x180041efa  xorps   xmm0, xmm0
0x180041efd  movups  xmmword ptr [rbp+57h+xmlDoc._Ptr], xmm0
0x180041f01  lea     hClientHandle, [rbp+57h+Xml]; this
0x180041f05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041f0a  nop
0x180041f0b  lea     pInterfaceGuid, [rbp+57h+Xml]; Xml
0x180041f0f  lea     hClientHandle, [rbp+57h+xmlDoc]; result
0x180041f13  call    ?LoadFromString@Document@Xml@WcmCommon@@SA?AV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::LoadFromString(std::wstring const &)
0x180041f18  nop
0x180041f19  lea     hClientHandle, [rbp+57h+Xml]; this
0x180041f1d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041f22  mov     rbx, [rbp+57h+xmlDoc._Ptr]
0x180041f26  lea     pInterfaceGuid, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x180041f2d  lea     hClientHandle, [rbp+57h+ns]; this
0x180041f31  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041f36  nop
0x180041f37  lea     pInterfaceGuid, aDefault; "default"
0x180041f3e  lea     hClientHandle, [rbp+57h+connectionModeNode]; this
0x180041f42  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041f47  nop
0x180041f48  lea     strProfileName, [rbp+57h+ns]; ns
0x180041f4c  lea     pInterfaceGuid, [rbp+57h+connectionModeNode]; key
0x180041f50  mov     hClientHandle, rbx; this
0x180041f53  call    ?AddSelectionNamespace@Document@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WcmCommon::Xml::Document::AddSelectionNamespace(std::wstring const &,std::wstring const &)
0x180041f58  nop
0x180041f59  lea     hClientHandle, [rbp+57h+connectionModeNode]; this
0x180041f5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041f62  nop
0x180041f63  lea     hClientHandle, [rbp+57h+ns]; this
0x180041f67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041f6c  xorps   xmm0, xmm0
0x180041f6f  movups  xmmword ptr [rbp+57h+connectionModeNode._Ptr], xmm0
0x180041f73  mov     rbx, [rbp+57h+xmlDoc._Ptr]
0x180041f77  lea     pInterfaceGuid, aDefaultConnect; "./default:ConnectionMode"
0x180041f7e  lea     hClientHandle, [rbp+57h+ns]; this
0x180041f82  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041f87  nop
0x180041f88  lea     strProfileName, [rbp+57h+ns]; Path
0x180041f8c  lea     pInterfaceGuid, [rbp+57h+connectionModeNode]; result
0x180041f90  mov     hClientHandle, rbx; this
0x180041f93  call    ?SelectSingle@Document@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::SelectSingle(std::wstring const &)
0x180041f98  nop
0x180041f99  lea     hClientHandle, [rbp+57h+ns]; this
0x180041f9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041fa2  mov     hClientHandle, [rbp+57h+connectionModeNode._Ptr]; this
0x180041fa6  test    hClientHandle, hClientHandle
0x180041fa9  jnz     short loc_180041FE5
0x180041fab  lea     pInterfaceGuid, WPP_GLOBAL_Control; __annotation("TMF:",
0x180041fb2  mov     hClientHandle, cs:WPP_GLOBAL_Control
0x180041fb9  cmp     hClientHandle, pInterfaceGuid
0x180041fbc  jz      short loc_180041FD9
0x180041fbe  test    byte ptr [hClientHandle+1Ch], 8
0x180041fc2  jz      short loc_180041FD9
0x180041fc4  mov     edx, 0Bh; id
0x180041fc9  lea     strProfileName, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180041fd0  mov     hClientHandle, [hClientHandle+10h]; Logger
0x180041fd4  call    WPP_SF_
0x180041fd9  xor     edx, edx; _New_size
0x180041fdb  mov     hClientHandle, rdi; this
0x180041fde  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x180041fe3  jmp     short loc_180042003
0x180041fe5  lea     pInterfaceGuid, [rbp+57h+Xml]; result
0x180041fe9  call    ?GetText@Node@Xml@WcmCommon@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WcmCommon::Xml::Node::GetText(void)
0x180041fee  mov     pInterfaceGuid, rax; _Right
0x180041ff1  mov     hClientHandle, rdi; this
0x180041ff4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180041ff9  lea     hClientHandle, [rbp+57h+Xml]; this
0x180041ffd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042002  nop
0x180042003  mov     hClientHandle, [rbp+57h+connectionModeNode._Rep]; this
0x180042007  test    hClientHandle, hClientHandle
0x18004200a  jz      short loc_180042012
0x18004200c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042011  nop
0x180042012  mov     hClientHandle, [rbp+57h+xmlDoc._Rep]; this
0x180042016  test    hClientHandle, hClientHandle
0x180042019  jz      short loc_180042021
0x18004201b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042020  nop
0x180042021  lea     hClientHandle, [rbp+57h+j]; j
0x180042025  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18004202a  mov     eax, 1
0x18004202f  mov     hClientHandle, [rbp+57h+var_28]
0x180042033  xor     hClientHandle, rsp; StackCookie
0x180042036  call    __security_check_cookie
0x18004203b  add     rsp, 0E8h
0x180042042  pop     rdi
0x180042043  pop     rsi
0x180042044  pop     rbx
0x180042045  pop     rbp
0x180042046  retn
```
