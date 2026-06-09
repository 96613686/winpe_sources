# EapLm::Peer::ThirdPartyEapMethodConfig::ConfigXml2Blob(uint,IXMLDOMDocument2 &,TempBuffer<0> &)

- ea: `0x18001eb30`
- end: `0x18001ec9e`
- name: `?ConfigXml2Blob@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXIAEAUIXMLDOMDocument2@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(const struct _EAP_METHOD_TYPE *, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180006c0c`
- `0x18000bf94`
- `0x18000d0e8`
- `0x18000eb74`
- `0x18000eb94`
- `0x1800126f8`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800160ac`
- `0x1800177bc`
- `0x18001eb30`
- `0x18001ecf8`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::ConfigXml2Blob(
        const struct _EAP_METHOD_TYPE *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rax
  __int64 v9; // r10
  __int64 v10; // r11
  signed int v11; // ebx
  unsigned int v13; // [rsp+40h] [rbp-89h] BYREF
  struct _EAP_ERROR *v14; // [rsp+48h] [rbp-81h] BYREF
  void *v15; // [rsp+50h] [rbp-79h] BYREF
  LPVOID v16; // [rsp+58h] [rbp-71h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v18[96]; // [rsp+80h] [rbp-49h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids, a2);
  EapHost::BaseXmlHelper::Document2String(v17, a3);
  v15 = 0;
  v13 = 0;
  v14 = 0;
  EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(a1, &v16);
  v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v11 = (*(__int64 (__fastcall **)(__int64, const struct _EAP_METHOD_TYPE *, _QWORD, __int64, unsigned int *, void **, struct _EAP_ERROR **))(v9 + 80))(
          v10,
          a1 + 1,
          a2,
          v8,
          &v13,
          &v15,
          &v14);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v16);
  if ( v11 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v18, v14, v11);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v18);
  }
  TempBuffer<0>::Assign(a4, v13, v15);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids, v13);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)&v14);
  com_ptr<unsigned char>::Clear(&v15);
  return std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v17);
}

```

## disassembly

```asm
0x18001eb30  push    rbp
0x18001eb32  push    rbx
0x18001eb33  push    rsi
0x18001eb34  push    rdi
0x18001eb35  push    r14
0x18001eb37  push    r15
0x18001eb39  lea     rbp, [rsp-2Fh]
0x18001eb3e  sub     rsp, 0F8h
0x18001eb45  mov     rax, cs:__security_cookie
0x18001eb4c  xor     rax, rsp
0x18001eb4f  mov     [rbp+57h+var_40], rax
0x18001eb53  mov     rdi, r9
0x18001eb56  mov     r14, r8
0x18001eb59  mov     ebx, edx
0x18001eb5b  mov     rsi, rcx
0x18001eb5e  lea     r15, WPP_GLOBAL_Control
0x18001eb65  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb6c  cmp     rcx, r15
0x18001eb6f  jz      short loc_18001EB8F
0x18001eb71  test    byte ptr [rcx+1Ch], 4
0x18001eb75  jz      short loc_18001EB8F
0x18001eb77  mov     edx, 16h
0x18001eb7c  mov     r9d, ebx
0x18001eb7f  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001eb86  mov     rcx, [rcx+10h]
0x18001eb8a  call    WPP_SF_d
0x18001eb8f  mov     rdx, r14
0x18001eb92  lea     rcx, [rbp+57h+var_C0]
0x18001eb96  call    ?Document2String@BaseXmlHelper@EapHost@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAUIXMLDOMDocument2@@@Z; EapHost::BaseXmlHelper::Document2String(IXMLDOMDocument2 &)
0x18001eb9b  nop
0x18001eb9c  xor     r14d, r14d
0x18001eb9f  mov     [rbp+57h+var_D0], r14
0x18001eba3  mov     [rsp+120h+var_E0], r14d
0x18001eba8  mov     [rsp+120h+var_D8], r14
0x18001ebad  lea     rdx, [rbp+57h+var_C8]
0x18001ebb1  mov     rcx, rsi
0x18001ebb4  call    ?CreateProxy@ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@XZ; EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(void)
0x18001ebb9  nop
0x18001ebba  mov     r11, [rax]
0x18001ebbd  mov     r10, [r11]
0x18001ebc0  lea     rcx, [rbp+57h+var_C0]
0x18001ebc4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ebc9  mov     r9, rax
0x18001ebcc  lea     rdx, [rsi+10h]
0x18001ebd0  lea     rax, [rsp+120h+var_D8]
0x18001ebd5  mov     [rsp+120h+var_F0], rax
0x18001ebda  lea     rax, [rbp+57h+var_D0]
0x18001ebde  mov     [rsp+120h+var_F8], rax
0x18001ebe3  lea     rax, [rsp+120h+var_E0]
0x18001ebe8  mov     [rsp+120h+var_100], rax
0x18001ebed  mov     r8d, ebx
0x18001ebf0  mov     rcx, r11
0x18001ebf3  mov     rax, [r10+50h]
0x18001ebf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebfc  mov     ebx, eax
0x18001ebfe  lea     rcx, [rbp+57h+var_C8]
0x18001ec02  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001ec07  test    ebx, ebx
0x18001ec09  jns     short loc_18001EC27
0x18001ec0b  mov     r8d, ebx; unsigned int
0x18001ec0e  mov     rdx, [rsp+120h+var_D8]; struct _EAP_ERROR *
0x18001ec13  lea     rcx, [rbp+57h+var_A0]; this
0x18001ec17  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001ec1c  nop
0x18001ec1d  lea     rcx, [rbp+57h+var_A0]; struct EapHost::EapError *
0x18001ec21  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001ec27  mov     edx, [rsp+120h+var_E0]
0x18001ec2b  mov     r8, [rbp+57h+var_D0]
0x18001ec2f  mov     rcx, rdi
0x18001ec32  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001ec37  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec3e  cmp     rcx, r15
0x18001ec41  jz      short loc_18001EC64
0x18001ec43  test    byte ptr [rcx+1Ch], 4
0x18001ec47  jz      short loc_18001EC64
0x18001ec49  mov     edx, 17h
0x18001ec4e  mov     r9d, [rsp+120h+var_E0]
0x18001ec53  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001ec5a  mov     rcx, [rcx+10h]
0x18001ec5e  call    WPP_SF_d
0x18001ec63  nop
0x18001ec64  lea     rcx, [rsp+120h+var_D8]
0x18001ec69  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001ec6e  nop
0x18001ec6f  lea     rcx, [rbp+57h+var_D0]
0x18001ec73  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18001ec78  nop
0x18001ec79  lea     rcx, [rbp+57h+var_C0]
0x18001ec7d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001ec82  mov     rcx, [rbp+57h+var_40]
0x18001ec86  xor     rcx, rsp; StackCookie
0x18001ec89  call    __security_check_cookie
0x18001ec8e  add     rsp, 0F8h
0x18001ec95  pop     r15
0x18001ec97  pop     r14
0x18001ec99  pop     rdi
0x18001ec9a  pop     rsi
0x18001ec9b  pop     rbx
0x18001ec9c  pop     rbp
0x18001ec9d  retn
```
