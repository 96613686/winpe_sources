# EapLm::Peer::EapMethodConfig::ConfigBlob2Xml(uint,ConstBuffer const &,ATL::CComPtr<IXMLDOMDocument2> &)

- ea: `0x18001b8f0`
- end: `0x18001bbf2`
- name: `?ConfigBlob2Xml@EapMethodConfig@Peer@EapLm@@UEAA_NIAEBUConstBuffer@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z`
- size: `770`
- prototype: `char __fastcall(__int64, unsigned int, _QWORD *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000d0e8`
- `0x18000d184`
- `0x1800154dc`
- `0x180015f10`
- `0x1800162a4`
- `0x180016400`
- `0x1800177bc`
- `0x18001b154`
- `0x18001b328`
- `0x18001b8f0`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001b940`
- `ntdll!EtwEventEnabled` at `0x18001bb58`
- `ntdll!EtwEventEnabled` at `0x18001b940`
- `ntdll!EtwEventEnabled` at `0x18001bb58`

## string_xrefs

- `0x18001ba00`: `ConfigBlob2Xml`
- `0x18001bac1`: `EapPeerConfigBlob2Xml`
- `0x18001b956`: `EapPeerConfigBlob2Xml Entry:\n flags(%d), config(%Id) bytes`
- `0x18001bb62`: `EapPeerConfigBlob2Xml Exit`

## pseudocode

```c
char __fastcall EapLm::Peer::EapMethodConfig::ConfigBlob2Xml(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        struct IUnknown **a4)
{
  char v8; // bl
  __int64 v9; // rax
  __int64 (__fastcall *v10)(_QWORD, struct IUnknown **, _QWORD, _QWORD, __int64 *, struct _EAP_ERROR **); // r12
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  void (__fastcall *v13)(struct _EAP_ERROR *); // r13
  unsigned int v14; // eax
  unsigned int v15; // eax
  const wchar_t *v16; // rdx
  struct IUnknown **v17; // rax
  struct _EAP_ERROR *v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v21[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v22[96]; // [rsp+70h] [rbp-90h] BYREF
  char v23[2048]; // [rsp+D0h] [rbp-30h] BYREF

  v20[0] = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v23, 0x800u, "EapPeerConfigBlob2Xml Entry:\n flags(%d), config(%Id) bytes", a2, a3[1]) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v23);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dP(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids, a2, a3[1]);
  v8 = 1;
  if ( !EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 200), 1) )
    goto LABEL_9;
  v9 = *(_QWORD *)(a1 + 200);
  v10 = *(__int64 (__fastcall **)(_QWORD, struct IUnknown **, _QWORD, _QWORD, __int64 *, struct _EAP_ERROR **))(v9 + 216);
  if ( !v10 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x40) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, PeerFunctionNotSupportedInfo, "ConfigBlob2Xml");
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_9;
    v12 = 35;
    goto LABEL_16;
  }
  v13 = *(void (__fastcall **)(struct _EAP_ERROR *))(v9 + 224);
  ATL::CComPtrBase<IXMLDOMDocument2>::Release(a4);
  v19 = 0;
  v14 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a3[1]);
  *(_OWORD *)v21 = *(_OWORD *)(a1 + 16);
  v15 = v10(a2, v21, *a3, v14, v20, &v19);
  if ( v15 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v22, v19, v15);
    v13(v19);
    EapHost::EapException::Throw(L"EapPeerConfigBlob2Xml", v16, (const struct EapHost::EapError *)v22);
  }
  if ( !v20[0] )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_9;
    v12 = 36;
LABEL_16:
    WPP_SF_(v11[2], v12, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
LABEL_9:
    v8 = 0;
    goto LABEL_26;
  }
  v20[1] = v20[0];
  (*(void (**)(void))(*(_QWORD *)v20[0] + 8LL))();
  v17 = (struct IUnknown **)EapHost::BaseXmlHelper::CopyXml(v21);
  if ( *a4 != *v17 )
    ATL::AtlComPtrAssign(a4, *v17);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)v21);
LABEL_26:
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v23, 0x800u, "EapPeerConfigBlob2Xml Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v23);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(v20);
  return v8;
}

```

## disassembly

```asm
0x18001b8f0  push    rbp
0x18001b8f2  push    rbx
0x18001b8f3  push    rsi
0x18001b8f4  push    rdi
0x18001b8f5  push    r12
0x18001b8f7  push    r13
0x18001b8f9  push    r14
0x18001b8fb  push    r15
0x18001b8fd  lea     rbp, [rsp-7E8h]
0x18001b905  sub     rsp, 8E8h
0x18001b90c  mov     rax, cs:__security_cookie
0x18001b913  xor     rax, rsp
0x18001b916  mov     [rbp+820h+var_50], rax
0x18001b91d  mov     r15, r9
0x18001b920  mov     rdi, r8
0x18001b923  mov     r14d, edx
0x18001b926  mov     rsi, rcx
0x18001b929  mov     [rsp+920h+var_8D8], 0
0x18001b932  lea     rdx, DebugInfoEvent
0x18001b939  mov     rcx, cs:eaphost_Context
0x18001b940  call    cs:__imp_EtwEventEnabled
0x18001b946  test    al, al
0x18001b948  jz      short loc_18001B98F
0x18001b94a  mov     rax, [rdi+8]
0x18001b94e  mov     [rsp+920h+var_900], rax
0x18001b953  mov     r9d, r14d
0x18001b956  lea     r8, aEappeerconfigb_1; "EapPeerConfigBlob2Xml Entry:\n flags(%d"...
0x18001b95d  mov     edx, 800h; unsigned __int64
0x18001b962  lea     rcx, [rbp+820h+var_850]; char *
0x18001b966  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001b96b  test    eax, eax
0x18001b96d  js      short loc_18001B98F
0x18001b96f  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001b976  jge     short loc_18001B98F
0x18001b978  lea     r8, [rbp+820h+var_850]
0x18001b97c  lea     rdx, DebugInfoEvent
0x18001b983  lea     rcx, eaphost_Context
0x18001b98a  call    McTemplateU0s_EtwEventWriteTransfer
0x18001b98f  lea     r13, WPP_GLOBAL_Control
0x18001b996  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b99d  cmp     rcx, r13
0x18001b9a0  jz      short loc_18001B9C9
0x18001b9a2  test    byte ptr [rcx+1Ch], 4
0x18001b9a6  jz      short loc_18001B9C9
0x18001b9a8  mov     edx, 22h ; '"'
0x18001b9ad  mov     rax, [rdi+8]
0x18001b9b1  mov     [rsp+920h+var_900], rax
0x18001b9b6  mov     r9d, r14d
0x18001b9b9  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001b9c0  mov     rcx, [rcx+10h]
0x18001b9c4  call    WPP_SF_dP
0x18001b9c9  mov     bl, 1
0x18001b9cb  mov     dl, bl; bool
0x18001b9cd  mov     rcx, [rsi+0C8h]; this
0x18001b9d4  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001b9d9  test    al, al
0x18001b9db  jnz     short loc_18001B9E4
0x18001b9dd  xor     bl, bl
0x18001b9df  jmp     loc_18001BB4A
0x18001b9e4  mov     rax, [rsi+0C8h]
0x18001b9eb  mov     r12, [rax+0D8h]
0x18001b9f2  test    r12, r12
0x18001b9f5  jnz     short loc_18001BA43
0x18001b9f7  test    cs:Microsoft_Windows_EapHostEnableBits, 40h
0x18001b9fe  jz      short loc_18001BA1A
0x18001ba00  lea     r8, aConfigblob2xml; "ConfigBlob2Xml"
0x18001ba07  lea     rdx, PeerFunctionNotSupportedInfo
0x18001ba0e  lea     rcx, eaphost_Context
0x18001ba15  call    McTemplateU0s_EtwEventWriteTransfer
0x18001ba1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba21  cmp     rcx, r13
0x18001ba24  jz      short loc_18001B9DD
0x18001ba26  test    byte ptr [rcx+1Ch], 4
0x18001ba2a  jz      short loc_18001B9DD
0x18001ba2c  mov     edx, 23h ; '#'
0x18001ba31  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001ba38  mov     rcx, [rcx+10h]
0x18001ba3c  call    WPP_SF_
0x18001ba41  jmp     short loc_18001B9DD
0x18001ba43  mov     r13, [rax+0E0h]
0x18001ba4a  mov     rcx, r15
0x18001ba4d  call    ?Release@?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMDocument2>::Release(void)
0x18001ba52  mov     [rsp+920h+var_8E0], 0
0x18001ba5b  mov     rcx, [rdi+8]
0x18001ba5f  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001ba64  movups  xmm0, xmmword ptr [rsi+10h]
0x18001ba68  movdqu  xmmword ptr [rsp+920h+var_8C0], xmm0
0x18001ba6e  lea     rcx, [rsp+920h+var_8E0]
0x18001ba73  mov     [rsp+920h+var_8F8], rcx
0x18001ba78  lea     rcx, [rsp+920h+var_8D8]
0x18001ba7d  mov     [rsp+920h+var_900], rcx
0x18001ba82  mov     r9d, eax
0x18001ba85  mov     r8, [rdi]
0x18001ba88  lea     rdx, [rsp+920h+var_8C0]
0x18001ba8d  mov     ecx, r14d
0x18001ba90  mov     rax, r12
0x18001ba93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba98  test    eax, eax
0x18001ba9a  jz      short loc_18001BACE
0x18001ba9c  mov     r8d, eax; unsigned int
0x18001ba9f  mov     rdx, [rsp+920h+var_8E0]; struct _EAP_ERROR *
0x18001baa4  lea     rcx, [rsp+920h+var_8B0]; this
0x18001baa9  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001baae  nop
0x18001baaf  mov     rcx, [rsp+920h+var_8E0]
0x18001bab4  mov     rax, r13
0x18001bab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001babc  lea     r8, [rsp+920h+var_8B0]; struct EapHost::EapError *
0x18001bac1  lea     rcx, aEappeerconfigb; "EapPeerConfigBlob2Xml"
0x18001bac8  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001bace  mov     rcx, [rsp+920h+var_8D8]
0x18001bad3  test    rcx, rcx
0x18001bad6  jnz     short loc_18001BB03
0x18001bad8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001badf  lea     r13, WPP_GLOBAL_Control
0x18001bae6  cmp     rcx, r13
0x18001bae9  jz      loc_18001B9DD
0x18001baef  test    byte ptr [rcx+1Ch], 4
0x18001baf3  jz      loc_18001B9DD
0x18001baf9  mov     edx, 24h ; '$'
0x18001bafe  jmp     loc_18001BA31
0x18001bb03  mov     [rsp+920h+var_8D0], rcx
0x18001bb08  test    rcx, rcx
0x18001bb0b  jz      short loc_18001BB1A
0x18001bb0d  mov     rax, [rcx]
0x18001bb10  mov     rax, [rax+8]
0x18001bb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb19  nop
0x18001bb1a  lea     rdx, [rsp+920h+var_8D0]
0x18001bb1f  lea     rcx, [rsp+920h+var_8C0]; struct IUnknown **
0x18001bb24  call    ?CopyXml@BaseXmlHelper@EapHost@@SA?AV?$CComPtr@UIXMLDOMDocument2@@@ATL@@V34@@Z; EapHost::BaseXmlHelper::CopyXml(ATL::CComPtr<IXMLDOMDocument2>)
0x18001bb29  mov     rdx, [rax]; struct IUnknown *
0x18001bb2c  cmp     [r15], rdx
0x18001bb2f  jz      short loc_18001BB39
0x18001bb31  mov     rcx, r15; struct IUnknown **
0x18001bb34  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001bb39  lea     rcx, [rsp+920h+var_8C0]
0x18001bb3e  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001bb43  lea     r13, WPP_GLOBAL_Control
0x18001bb4a  lea     rdx, DebugInfoEvent
0x18001bb51  mov     rcx, cs:eaphost_Context
0x18001bb58  call    cs:__imp_EtwEventEnabled
0x18001bb5e  test    al, al
0x18001bb60  jz      short loc_18001BB9B
0x18001bb62  lea     r8, aEappeerconfigb_0; "EapPeerConfigBlob2Xml Exit"
0x18001bb69  mov     edx, 800h; unsigned __int64
0x18001bb6e  lea     rcx, [rbp+820h+var_850]; char *
0x18001bb72  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001bb77  test    eax, eax
0x18001bb79  js      short loc_18001BB9B
0x18001bb7b  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001bb82  jge     short loc_18001BB9B
0x18001bb84  lea     r8, [rbp+820h+var_850]
0x18001bb88  lea     rdx, DebugInfoEvent
0x18001bb8f  lea     rcx, eaphost_Context
0x18001bb96  call    McTemplateU0s_EtwEventWriteTransfer
0x18001bb9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bba2  cmp     rcx, r13
0x18001bba5  jz      short loc_18001BBC3
0x18001bba7  test    byte ptr [rcx+1Ch], 4
0x18001bbab  jz      short loc_18001BBC3
0x18001bbad  mov     edx, 25h ; '%'
0x18001bbb2  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001bbb9  mov     rcx, [rcx+10h]
0x18001bbbd  call    WPP_SF_
0x18001bbc2  nop
0x18001bbc3  lea     rcx, [rsp+920h+var_8D8]
0x18001bbc8  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001bbcd  mov     al, bl
0x18001bbcf  mov     rcx, [rbp+820h+var_50]
0x18001bbd6  xor     rcx, rsp; StackCookie
0x18001bbd9  call    __security_check_cookie
0x18001bbde  add     rsp, 8E8h
0x18001bbe5  pop     r15
0x18001bbe7  pop     r14
0x18001bbe9  pop     r13
0x18001bbeb  pop     r12
0x18001bbed  pop     rdi
0x18001bbee  pop     rsi
0x18001bbef  pop     rbx
0x18001bbf0  pop     rbp
0x18001bbf1  retn
```
