# WSTrustTokenRequest::BuildWSTrustTokenRequestMessage2005(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CSecureString const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14001749c`
- end: `0x1400175f0`
- name: `?BuildWSTrustTokenRequestMessage2005@WSTrustTokenRequest@@AEAA?AVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEBV2@10@Z`
- size: `340`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140016a04`

## callees

- `0x14000579c`
- `0x14000813c`
- `0x1400081d8`
- `0x140008644`
- `0x140012cb4`
- `0x140017238`
- `0x14001749c`
- `0x140030010`

## string_xrefs

- `0x14001753e`: `<wst:TokenType>%s</wst:TokenType>`
- `0x140017575`: `<?xml version='1.0' encoding='UTF-8'?><s:Envelope xmlns:s='http://www.w3.org/2003/05/soap-envelope' xmlns:wsse='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:saml='urn:oasis:names:tc:SAML:1.0:assertion' xmlns:wsp='http://schemas.xmlsoap.org/ws/2004/09/policy' xmlns:wsu='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:wsa='http://www.w3.org/2005/08/addressing' xmlns:wssc='http://schemas.xmlsoap.org/ws/2005/02/sc'`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall WSTrustTokenRequest::BuildWSTrustTokenRequestMessage2005(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 *a7)
{
  __int64 v10; // rbx
  _QWORD *v11; // rdx
  __int64 v13; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v14[2]; // [rsp+50h] [rbp-10h] BYREF
  __int64 v15; // [rsp+80h] [rbp+20h] BYREF
  _QWORD *v16; // [rsp+88h] [rbp+28h]

  v16 = a2;
  v15 = a1;
  *a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  WSTrustTokenRequest::BuildSecurityHeader2005(v14, a5, a6);
  StringUtility::CreateGuid(&v13);
  v15 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( *(_DWORD *)(*a7 - 16) )
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &v15,
      L"<wst:TokenType>%s</wst:TokenType>",
      *a7);
  else
    ATL::CSimpleStringT<unsigned short,0>::Append(&v15, *a7, 0);
  v10 = v15;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    a2,
    L"<?xml version='1.0' encoding='UTF-8'?><s:Envelope xmlns:s='http://www.w3.org/2003/05/soap-envelope' xmlns:wsse='http"
     "://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:saml='urn:oasis:names:tc:SAML:"
     "1.0:assertion' xmlns:wsp='http://schemas.xmlsoap.org/ws/2004/09/policy' xmlns:wsu='http://docs.oasis-open.org/wss/2"
     "004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:wsa='http://www.w3.org/2005/08/addressing' xmlns:wssc='ht"
     "tp://schemas.xmlsoap.org/ws/2005/02/sc' xmlns:wst='http://schemas.xmlsoap.org/ws/2005/02/trust'><s:Header><wsa:Acti"
     "on s:mustUnderstand='1'>http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue</wsa:Action><wsa:To s:mustUnderstand="
     "'1'>%s</wsa:To><wsa:MessageID>urn:uuid:%s</wsa:MessageID>%s</s:Header><s:Body><wst:RequestSecurityToken Id='RST0'><"
     "wst:RequestType>http://schemas.xmlsoap.org/ws/2005/02/trust/Issue</wst:RequestType><wsp:AppliesTo><wsa:EndpointRefe"
     "rence><wsa:Address>%s</wsa:Address></wsa:EndpointReference></wsp:AppliesTo><wst:KeyType>http://schemas.xmlsoap.org/"
     "ws/2005/05/identity/NoProofKey</wst:KeyType>%s</wst:RequestSecurityToken></s:Body></s:Envelope>",
    *a4,
    v13,
    v14[0],
    *a3,
    v15);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v10 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 - 24) + 8LL))(*(_QWORD *)(v10 - 24));
  v11 = (_QWORD *)(v13 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v13 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  CSecureString::~CSecureString((CSecureString *)v14);
  return a2;
}

```

## disassembly

```asm
0x14001749c  mov     rax, rsp
0x14001749f  mov     [rax+18h], rbx
0x1400174a3  mov     [rax+20h], rsi
0x1400174a7  mov     [rax+10h], rdx
0x1400174ab  mov     [rax+8], rcx
0x1400174af  push    rbp
0x1400174b0  push    rdi
0x1400174b1  push    r14
0x1400174b3  mov     rbp, rsp
0x1400174b6  sub     rsp, 60h
0x1400174ba  mov     rsi, r9
0x1400174bd  mov     r14, r8
0x1400174c0  mov     rdi, rdx
0x1400174c3  mov     [rbp+var_20], 0
0x1400174ca  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400174d1  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400174d8  mov     rax, [rax+18h]
0x1400174dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400174e1  add     rax, 18h
0x1400174e5  mov     [rdi], rax
0x1400174e8  mov     [rbp+var_20], 1
0x1400174ef  mov     r8, [rbp+arg_28]
0x1400174f3  mov     rdx, [rbp+arg_20]
0x1400174f7  lea     rcx, [rbp+var_10]
0x1400174fb  call    ?BuildSecurityHeader2005@WSTrustTokenRequest@@CA?AVCSecureString@@AEBV2@0@Z; WSTrustTokenRequest::BuildSecurityHeader2005(CSecureString const &,CSecureString const &)
0x140017500  nop
0x140017501  lea     rcx, [rbp+var_18]
0x140017505  call    ?CreateGuid@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; StringUtility::CreateGuid(void)
0x14001750a  nop
0x14001750b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140017512  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140017519  mov     rax, [rax+18h]
0x14001751d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017522  add     rax, 18h
0x140017526  mov     [rbp+arg_0], rax
0x14001752a  mov     rax, [rbp+arg_30]
0x14001752e  mov     rdx, [rax]
0x140017531  lea     rcx, [rbp+arg_0]
0x140017535  cmp     dword ptr [rdx-10h], 0
0x140017539  jz      short loc_14001754C
0x14001753b  mov     r8, rdx
0x14001753e  lea     rdx, aWstTokentypeSW; "<wst:TokenType>%s</wst:TokenType>"
0x140017545  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14001754a  jmp     short loc_140017554
0x14001754c  xor     r8d, r8d
0x14001754f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140017554  mov     rbx, [rbp+arg_0]
0x140017558  mov     [rsp+60h+var_30], rbx
0x14001755d  mov     rax, [r14]
0x140017560  mov     [rsp+60h+var_38], rax
0x140017565  mov     rax, [rbp+var_10]
0x140017569  mov     [rsp+60h+var_40], rax
0x14001756e  mov     r9, [rbp+var_18]
0x140017572  mov     r8, [rsi]
0x140017575  lea     rdx, aXmlVersion10En; "<?xml version='1.0' encoding='UTF-8'?><"...
0x14001757c  mov     rcx, rdi
0x14001757f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140017584  nop
0x140017585  lea     rdx, [rbx-18h]
0x140017589  or      ebx, 0FFFFFFFFh
0x14001758c  mov     eax, ebx
0x14001758e  lock xadd [rdx+10h], eax
0x140017593  add     eax, ebx
0x140017595  test    eax, eax
0x140017597  jg      short loc_1400175A9
0x140017599  mov     rcx, [rdx]
0x14001759c  mov     rax, [rcx]
0x14001759f  mov     rax, [rax+8]
0x1400175a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400175a8  nop
0x1400175a9  mov     rdx, [rbp+var_18]
0x1400175ad  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400175b1  mov     eax, ebx
0x1400175b3  lock xadd [rdx+10h], eax
0x1400175b8  add     eax, ebx
0x1400175ba  test    eax, eax
0x1400175bc  jg      short loc_1400175CE
0x1400175be  mov     rcx, [rdx]
0x1400175c1  mov     rax, [rcx]
0x1400175c4  mov     rax, [rax+8]
0x1400175c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400175cd  nop
0x1400175ce  lea     rcx, [rbp+var_10]; this
0x1400175d2  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400175d7  mov     rax, rdi
0x1400175da  lea     r11, [rsp+60h+var_s0]
0x1400175df  mov     rbx, [r11+30h]
0x1400175e3  mov     rsi, [r11+38h]
0x1400175e7  mov     rsp, r11
0x1400175ea  pop     r14
0x1400175ec  pop     rdi
0x1400175ed  pop     rbp
0x1400175ee  retn
```
