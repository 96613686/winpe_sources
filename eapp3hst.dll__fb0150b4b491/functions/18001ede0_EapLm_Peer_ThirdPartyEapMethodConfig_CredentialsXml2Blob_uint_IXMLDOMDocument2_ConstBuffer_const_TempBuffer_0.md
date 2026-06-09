# EapLm::Peer::ThirdPartyEapMethodConfig::CredentialsXml2Blob(uint,IXMLDOMDocument2 &,ConstBuffer const &,TempBuffer<0> &)

- ea: `0x18001ede0`
- end: `0x18001ef8e`
- name: `?CredentialsXml2Blob@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXIAEAUIXMLDOMDocument2@@AEBUConstBuffer@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(const struct _EAP_METHOD_TYPE *, unsigned int, __int64, __int64 *, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180005894`
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
- `0x18001b328`
- `0x18001ecf8`
- `0x18001ede0`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::CredentialsXml2Blob(
        const struct _EAP_METHOD_TYPE *a1,
        unsigned int a2,
        __int64 a3,
        __int64 *a4,
        __int64 a5)
{
  LPVOID *v9; // rax
  LPVOID v10; // rsi
  __int64 (__fastcall *v11)(LPVOID, const struct _EAP_METHOD_TYPE *, _QWORD, __int64, int, __int64, unsigned int *, void **, struct _EAP_ERROR **); // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  int v14; // r10d
  signed int v15; // ebx
  unsigned int v17; // [rsp+50h] [rbp-B0h] BYREF
  struct _EAP_ERROR *v18; // [rsp+58h] [rbp-A8h] BYREF
  void *v19; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v20; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v21[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[96]; // [rsp+90h] [rbp-70h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dP(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids, a2, a4[1]);
  EapHost::BaseXmlHelper::Document2String(v21, a3);
  v19 = 0;
  v17 = 0;
  v18 = 0;
  v9 = EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(a1, &v20);
  v10 = *v9;
  v11 = *(__int64 (__fastcall **)(LPVOID, const struct _EAP_METHOD_TYPE *, _QWORD, __int64, int, __int64, unsigned int *, void **, struct _EAP_ERROR **))(*(_QWORD *)*v9 + 88LL);
  v12 = *a4;
  wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v15 = v11(v10, a1 + 1, a2, v13, v14, v12, &v17, &v19, &v18);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v20);
  if ( v15 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v22, v18, v15);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v22);
  }
  TempBuffer<0>::Assign(a5, v17, v19);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids, v17);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)&v18);
  com_ptr<unsigned char>::Clear(&v19);
  return std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v21);
}

```

## disassembly

```asm
0x18001ede0  push    rbp
0x18001ede2  push    rbx
0x18001ede3  push    rsi
0x18001ede4  push    rdi
0x18001ede5  push    r12
0x18001ede7  push    r13
0x18001ede9  push    r14
0x18001edeb  push    r15
0x18001eded  lea     rbp, [rsp-8]
0x18001edf2  sub     rsp, 108h
0x18001edf9  mov     rax, cs:__security_cookie
0x18001ee00  xor     rax, rsp
0x18001ee03  mov     [rbp+40h+var_50], rax
0x18001ee07  mov     r14, r9
0x18001ee0a  mov     rbx, r8
0x18001ee0d  mov     r15d, edx
0x18001ee10  mov     r13, rcx
0x18001ee13  mov     r12, [rbp+40h+arg_20]
0x18001ee17  lea     rax, WPP_GLOBAL_Control
0x18001ee1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee25  cmp     rcx, rax
0x18001ee28  jz      short loc_18001EE51
0x18001ee2a  test    byte ptr [rcx+1Ch], 4
0x18001ee2e  jz      short loc_18001EE51
0x18001ee30  mov     edx, 18h
0x18001ee35  mov     rax, [r9+8]
0x18001ee39  mov     [rsp+140h+var_120], rax
0x18001ee3e  mov     r9d, r15d
0x18001ee41  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001ee48  mov     rcx, [rcx+10h]
0x18001ee4c  call    WPP_SF_dP
0x18001ee51  mov     rdx, rbx
0x18001ee54  lea     rcx, [rsp+140h+var_D0]
0x18001ee59  call    ?Document2String@BaseXmlHelper@EapHost@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAUIXMLDOMDocument2@@@Z; EapHost::BaseXmlHelper::Document2String(IXMLDOMDocument2 &)
0x18001ee5e  nop
0x18001ee5f  xor     eax, eax
0x18001ee61  mov     [rsp+140h+var_E0], rax
0x18001ee66  mov     [rsp+140h+var_F0], eax
0x18001ee6a  mov     [rsp+140h+var_E8], rax
0x18001ee6f  lea     rdx, [rsp+140h+var_D8]
0x18001ee74  mov     rcx, r13
0x18001ee77  call    ?CreateProxy@ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@XZ; EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(void)
0x18001ee7c  nop
0x18001ee7d  mov     rsi, [rax]
0x18001ee80  mov     rax, [rsi]
0x18001ee83  mov     rdi, [rax+58h]
0x18001ee87  mov     rbx, [r14]
0x18001ee8a  mov     rcx, [r14+8]
0x18001ee8e  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001ee93  mov     r10d, eax
0x18001ee96  lea     rcx, [rsp+140h+var_D0]
0x18001ee9b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001eea0  mov     r9, rax
0x18001eea3  lea     rdx, [r13+10h]
0x18001eea7  lea     rax, [rsp+140h+var_E8]
0x18001eeac  mov     [rsp+140h+var_100], rax
0x18001eeb1  lea     rax, [rsp+140h+var_E0]
0x18001eeb6  mov     [rsp+140h+var_108], rax
0x18001eebb  lea     rax, [rsp+140h+var_F0]
0x18001eec0  mov     [rsp+140h+var_110], rax
0x18001eec5  mov     [rsp+140h+var_118], rbx
0x18001eeca  mov     dword ptr [rsp+140h+var_120], r10d
0x18001eecf  mov     r8d, r15d
0x18001eed2  mov     rcx, rsi
0x18001eed5  mov     rax, rdi
0x18001eed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eedd  mov     ebx, eax
0x18001eedf  lea     rcx, [rsp+140h+var_D8]
0x18001eee4  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001eee9  test    ebx, ebx
0x18001eeeb  jns     short loc_18001EF09
0x18001eeed  mov     r8d, ebx; unsigned int
0x18001eef0  mov     rdx, [rsp+140h+var_E8]; struct _EAP_ERROR *
0x18001eef5  lea     rcx, [rbp+40h+var_B0]; this
0x18001eef9  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001eefe  nop
0x18001eeff  lea     rcx, [rbp+40h+var_B0]; struct EapHost::EapError *
0x18001ef03  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001ef09  mov     edx, [rsp+140h+var_F0]
0x18001ef0d  mov     r8, [rsp+140h+var_E0]
0x18001ef12  mov     rcx, r12
0x18001ef15  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001ef1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef21  lea     rax, WPP_GLOBAL_Control
0x18001ef28  cmp     rcx, rax
0x18001ef2b  jz      short loc_18001EF4E
0x18001ef2d  test    byte ptr [rcx+1Ch], 4
0x18001ef31  jz      short loc_18001EF4E
0x18001ef33  mov     edx, 19h
0x18001ef38  mov     r9d, [rsp+140h+var_F0]
0x18001ef3d  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001ef44  mov     rcx, [rcx+10h]
0x18001ef48  call    WPP_SF_d
0x18001ef4d  nop
0x18001ef4e  lea     rcx, [rsp+140h+var_E8]
0x18001ef53  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001ef58  nop
0x18001ef59  lea     rcx, [rsp+140h+var_E0]
0x18001ef5e  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18001ef63  nop
0x18001ef64  lea     rcx, [rsp+140h+var_D0]
0x18001ef69  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001ef6e  mov     rcx, [rbp+40h+var_50]
0x18001ef72  xor     rcx, rsp; StackCookie
0x18001ef75  call    __security_check_cookie
0x18001ef7a  add     rsp, 108h
0x18001ef81  pop     r15
0x18001ef83  pop     r14
0x18001ef85  pop     r13
0x18001ef87  pop     r12
0x18001ef89  pop     rdi
0x18001ef8a  pop     rsi
0x18001ef8b  pop     rbx
0x18001ef8c  pop     rbp
0x18001ef8d  retn
```
