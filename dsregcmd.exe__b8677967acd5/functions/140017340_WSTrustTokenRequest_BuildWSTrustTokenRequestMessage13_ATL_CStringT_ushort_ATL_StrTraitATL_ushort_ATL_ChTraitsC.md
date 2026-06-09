# WSTrustTokenRequest::BuildWSTrustTokenRequestMessage13(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CSecureString const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140017340`
- end: `0x140017494`
- name: `?BuildWSTrustTokenRequestMessage13@WSTrustTokenRequest@@AEAA?AVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEBV2@10@Z`
- size: `340`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140016a04`

## callees

- `0x14000579c`
- `0x14000813c`
- `0x1400081d8`
- `0x140012cb4`
- `0x140017104`
- `0x140017340`
- `0x140030010`

## string_xrefs

- `0x1400173d8`: `<trust:TokenType>%s</trust:TokenType>`
- `0x140017419`: `<s:Envelope xmlns:s='http://www.w3.org/2003/05/soap-envelope' xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd'><s:Header><a:Action s:mustUnderstand='1'>http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue</a:Action><a:MessageID>urn:uuid:%s</a:MessageID><a:ReplyTo><a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address></a:ReplyTo><a:To s:mustUnderstand='1'>%s</a:To>%s</s:Header><s:Body><`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall WSTrustTokenRequest::BuildWSTrustTokenRequestMessage13(
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
  WSTrustTokenRequest::BuildSecurityHeader13(v14, a5, a6);
  *a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v15 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( *(_DWORD *)(*a7 - 16) )
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &v15,
      L"<trust:TokenType>%s</trust:TokenType>",
      *a7);
  else
    ATL::CSimpleStringT<unsigned short,0>::Append(&v15, *a7, 0);
  StringUtility::CreateGuid(&v13);
  v10 = v15;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    a2,
    L"<s:Envelope xmlns:s='http://www.w3.org/2003/05/soap-envelope' xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:u"
     "='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd'><s:Header><a:Action s:mustUnd"
     "erstand='1'>http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue</a:Action><a:MessageID>urn:uuid:%s</a:Messag"
     "eID><a:ReplyTo><a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address></a:ReplyTo><a:To s:mustUnderst"
     "and='1'>%s</a:To>%s</s:Header><s:Body><trust:RequestSecurityToken xmlns:trust='http://docs.oasis-open.org/ws-sx/ws-"
     "trust/200512'><wsp:AppliesTo xmlns:wsp='http://schemas.xmlsoap.org/ws/2004/09/policy'><a:EndpointReference><a:Addre"
     "ss>%s</a:Address></a:EndpointReference></wsp:AppliesTo><trust:KeyType>http://docs.oasis-open.org/ws-sx/ws-trust/200"
     "512/Bearer</trust:KeyType><trust:RequestType>http://docs.oasis-open.org/ws-sx/ws-trust/200512/Issue</trust:RequestT"
     "ype>%s</trust:RequestSecurityToken></s:Body></s:Envelope>",
    v13,
    *a4,
    v14[0],
    *a3,
    v15);
  v11 = (_QWORD *)(v13 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v13 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v10 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 - 24) + 8LL))(*(_QWORD *)(v10 - 24));
  CSecureString::~CSecureString((CSecureString *)v14);
  return a2;
}

```

## disassembly

```asm
0x140017340  mov     rax, rsp
0x140017343  mov     [rax+18h], rbx
0x140017347  mov     [rax+20h], rsi
0x14001734b  mov     [rax+10h], rdx
0x14001734f  mov     [rax+8], rcx
0x140017353  push    rbp
0x140017354  push    rdi
0x140017355  push    r14
0x140017357  mov     rbp, rsp
0x14001735a  sub     rsp, 60h
0x14001735e  mov     rsi, r9
0x140017361  mov     r14, r8
0x140017364  mov     rdi, rdx
0x140017367  mov     [rbp+var_20], 0
0x14001736e  mov     r8, [rbp+arg_28]
0x140017372  mov     rdx, [rbp+arg_20]
0x140017376  lea     rcx, [rbp+var_10]
0x14001737a  call    ?BuildSecurityHeader13@WSTrustTokenRequest@@CA?AVCSecureString@@AEBV2@0@Z; WSTrustTokenRequest::BuildSecurityHeader13(CSecureString const &,CSecureString const &)
0x14001737f  nop
0x140017380  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140017387  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001738e  mov     rax, [rax+18h]
0x140017392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017397  add     rax, 18h
0x14001739b  mov     [rdi], rax
0x14001739e  mov     [rbp+var_20], 1
0x1400173a5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400173ac  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400173b3  mov     rax, [rax+18h]
0x1400173b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400173bc  add     rax, 18h
0x1400173c0  mov     [rbp+arg_0], rax
0x1400173c4  mov     rax, [rbp+arg_30]
0x1400173c8  mov     rdx, [rax]
0x1400173cb  lea     rcx, [rbp+arg_0]
0x1400173cf  cmp     dword ptr [rdx-10h], 0
0x1400173d3  jz      short loc_1400173E6
0x1400173d5  mov     r8, rdx
0x1400173d8  lea     rdx, aTrustTokentype; "<trust:TokenType>%s</trust:TokenType>"
0x1400173df  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1400173e4  jmp     short loc_1400173EE
0x1400173e6  xor     r8d, r8d
0x1400173e9  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400173ee  lea     rcx, [rbp+var_18]
0x1400173f2  call    ?CreateGuid@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; StringUtility::CreateGuid(void)
0x1400173f7  nop
0x1400173f8  mov     rbx, [rbp+arg_0]
0x1400173fc  mov     [rsp+60h+var_30], rbx
0x140017401  mov     rax, [r14]
0x140017404  mov     [rsp+60h+var_38], rax
0x140017409  mov     rax, [rbp+var_10]
0x14001740d  mov     [rsp+60h+var_40], rax
0x140017412  mov     r9, [rsi]
0x140017415  mov     r8, [rbp+var_18]
0x140017419  lea     rdx, aSEnvelopeXmlns; "<s:Envelope xmlns:s='http://www.w3.org/"...
0x140017420  mov     rcx, rdi
0x140017423  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x140017428  nop
0x140017429  mov     rdx, [rbp+var_18]
0x14001742d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017431  or      esi, 0FFFFFFFFh
0x140017434  mov     eax, esi
0x140017436  lock xadd [rdx+10h], eax
0x14001743b  add     eax, esi
0x14001743d  test    eax, eax
0x14001743f  jg      short loc_140017451
0x140017441  mov     rcx, [rdx]
0x140017444  mov     rax, [rcx]
0x140017447  mov     rax, [rax+8]
0x14001744b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017450  nop
0x140017451  lea     rdx, [rbx-18h]
0x140017455  mov     eax, esi
0x140017457  lock xadd [rdx+10h], eax
0x14001745c  add     eax, esi
0x14001745e  test    eax, eax
0x140017460  jg      short loc_140017472
0x140017462  mov     rcx, [rdx]
0x140017465  mov     rax, [rcx]
0x140017468  mov     rax, [rax+8]
0x14001746c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017471  nop
0x140017472  lea     rcx, [rbp+var_10]; this
0x140017476  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14001747b  mov     rax, rdi
0x14001747e  lea     r11, [rsp+60h+var_s0]
0x140017483  mov     rbx, [r11+30h]
0x140017487  mov     rsi, [r11+38h]
0x14001748b  mov     rsp, r11
0x14001748e  pop     r14
0x140017490  pop     rdi
0x140017491  pop     rbp
0x140017492  retn
```
