# CRDPENCConnectorStringDeserializer::XMLDeserialize(ushort *)

- ea: `0x140070200`
- end: `0x1400705b8`
- name: `?XMLDeserialize@CRDPENCConnectorStringDeserializer@@QEAAJPEAG@Z`
- size: `952`
- prototype: `__int64 __fastcall(CRDPENCConnectorStringDeserializer *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140065ca0`

## callees

- `0x1400019e8`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14000dcac`
- `0x140070200`
- `0x14007fc94`
- `0x14008031c`
- `0x140112010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140070256`
- `ole32!CoCreateInstance` at `0x140070256`
- `OLEAUT32!__imp_SysAllocString` at `0x1400703f8`
- `OLEAUT32!__imp_SysAllocString` at `0x1400703f8`
- `OLEAUT32!__imp_SysFreeString` at `0x14007056f`
- `OLEAUT32!__imp_SysFreeString` at `0x14007057d`
- `OLEAUT32!__imp_SysFreeString` at `0x14007056f`
- `OLEAUT32!__imp_SysFreeString` at `0x14007057d`

## string_xrefs

- `0x140070295`: `Failed to create the XML document`
- `0x14007030f`: `Failed to create the transport root node`
- `0x1400704f9`: `XMLDeserialize`

## pseudocode

```c
__int64 __fastcall CRDPENCConnectorStringDeserializer::XMLDeserialize(
        CRDPENCConnectorStringDeserializer *this,
        unsigned __int16 *a2)
{
  OLECHAR *v2; // rsi
  HRESULT Instance; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  struct IXMLDOMNode *v9; // rbx
  int v10; // r8d
  int v11; // r9d
  BSTR v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v16; // [rsp+50h] [rbp+7h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp+Fh] BYREF
  struct IXMLDOMNode *v18; // [rsp+60h] [rbp+17h] BYREF
  struct IXMLDOMNode *ppv; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v20; // [rsp+70h] [rbp+27h] BYREF
  const char *v21; // [rsp+78h] [rbp+2Fh] BYREF
  const char *v22; // [rsp+80h] [rbp+37h] BYREF
  unsigned int v23; // [rsp+C0h] [rbp+77h] BYREF
  int v24; // [rsp+C8h] [rbp+7Fh] BYREF

  v2 = 0;
  bstrString = 0;
  v23 = 0;
  v16 = 0;
  ppv = 0;
  v18 = 0;
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = RDPENCHLPXML_AddElementFromXMLString(ppv, a2, &v18);
    if ( Instance >= 0 )
    {
      v9 = v18;
      Instance = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v18->lpVtbl->get_baseName)(v18, &bstrString);
      if ( Instance >= 0 )
      {
        if ( *bstrString != 84 || bstrString[1] )
        {
          if ( (unsigned int)dword_140150118 > 2 )
          {
            v23 = 340;
            v20 = "XMLDeserialize";
            v24 = -2147467259;
            v21 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconser.cpp";
            v22 = "Expecting type T node";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              (_DWORD)bstrString,
              (unsigned int)qword_14013E478,
              v10,
              v11,
              (__int64)&v22,
              (__int64)&v24,
              (__int64)&v21,
              (__int64)&v23,
              (__int64)&v20);
          }
          Instance = -2147024809;
        }
        else
        {
          Instance = RDPENCHLPXML_GetUintAttribute(v9, L"SID", &v23);
          if ( Instance >= 0 )
          {
            v12 = SysAllocString(L"L[@N!='' and (@P!='' or @U!='')]");
            v2 = v12;
            if ( v12 )
            {
              Instance = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))v9->lpVtbl->selectNodes)(
                           v9,
                           v12,
                           &v16);
              if ( Instance >= 0 )
              {
                if ( v16 != *((_QWORD *)this + 1) )
                {
                  TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 8);
                  v14 = v16;
                  *((_QWORD *)this + 1) = v16;
                  if ( v14 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
                }
                *(_DWORD *)this = v23;
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v7 = 40;
                v8 = "Failed to query the nodes";
                goto LABEL_6;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  39,
                  WPP_c63511fa6e173da0847aa5c8f83f7746_Traceguids,
                  v13,
                  -2147024882);
              }
              Instance = -2147024882;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v7 = 38;
            v8 = "Failed to get the session id";
            goto LABEL_6;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 37;
        v8 = "Failed to get the base name";
        goto LABEL_6;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 36;
      v8 = "Failed to create the transport root node";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 35;
    v8 = "Failed to create the XML document";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_c63511fa6e173da0847aa5c8f83f7746_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v8,
      Instance);
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v2 )
    SysFreeString(v2);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v18);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&ppv);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v16);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140070200  mov     [rsp-8+arg_0], rbx
0x140070205  mov     [rsp-8+arg_8], rsi
0x14007020a  push    rbp
0x14007020b  push    rdi
0x14007020c  push    r14
0x14007020e  lea     rbp, [rsp-47h]
0x140070213  sub     rsp, 90h
0x14007021a  xor     esi, esi
0x14007021c  mov     [rbp+57h+bstrString], 0
0x140070224  mov     rbx, rdx
0x140070227  mov     [rbp+57h+arg_10], esi
0x14007022a  mov     r14, rcx
0x14007022d  mov     [rbp+57h+var_50], rsi
0x140070231  lea     rax, [rbp+57h+var_38]
0x140070235  mov     [rbp+57h+var_38], rsi
0x140070239  lea     r8d, [rsi+1]; dwClsContext
0x14007023d  mov     [rbp+57h+var_40], rsi
0x140070241  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x140070248  mov     [rsp+0A0h+ppv], rax; ppv
0x14007024d  xor     edx, edx; pUnkOuter
0x14007024f  lea     rcx, CLSID_DOMDocument60; rclsid
0x140070256  call    cs:__imp_CoCreateInstance
0x14007025c  mov     edi, eax
0x14007025e  test    eax, eax
0x140070260  jns     short loc_1400702C4
0x140070262  mov     rcx, cs:WPP_GLOBAL_Control
0x140070269  lea     rax, WPP_GLOBAL_Control
0x140070270  cmp     rcx, rax
0x140070273  jz      loc_140070566
0x140070279  test    byte ptr [rcx+1Ch], 8
0x14007027d  jz      loc_140070566
0x140070283  cmp     byte ptr [rcx+19h], 2
0x140070287  jb      loc_140070566
0x14007028d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140070292  lea     edx, [rsi+23h]
0x140070295  lea     rcx, aFailedToCreate_51; "Failed to create the XML document"
0x14007029c  mov     dword ptr [rsp+0A0h+var_78], edi
0x1400702a0  lea     r8, WPP_c63511fa6e173da0847aa5c8f83f7746_Traceguids
0x1400702a7  mov     [rsp+0A0h+ppv], rcx
0x1400702ac  mov     r9d, eax
0x1400702af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400702b6  mov     rcx, [rcx+10h]
0x1400702ba  call    WPP_SF_DsD
0x1400702bf  jmp     loc_140070566
0x1400702c4  mov     rcx, [rbp+57h+var_38]; struct IXMLDOMNode *
0x1400702c8  lea     r8, [rbp+57h+var_40]; struct IXMLDOMNode **
0x1400702cc  mov     rdx, rbx; unsigned __int16 *
0x1400702cf  call    ?RDPENCHLPXML_AddElementFromXMLString@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAU1@@Z; RDPENCHLPXML_AddElementFromXMLString(IXMLDOMNode *,ushort *,IXMLDOMNode * *)
0x1400702d4  mov     edi, eax
0x1400702d6  test    eax, eax
0x1400702d8  jns     short loc_140070318
0x1400702da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400702e1  lea     rax, WPP_GLOBAL_Control
0x1400702e8  cmp     rcx, rax
0x1400702eb  jz      loc_140070566
0x1400702f1  test    byte ptr [rcx+1Ch], 8
0x1400702f5  jz      loc_140070566
0x1400702fb  cmp     byte ptr [rcx+19h], 2
0x1400702ff  jb      loc_140070566
0x140070305  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007030a  mov     edx, 24h ; '$'
0x14007030f  lea     rcx, aFailedToCreate_53; "Failed to create the transport root nod"...
0x140070316  jmp     short loc_14007029C
0x140070318  mov     rbx, [rbp+57h+var_40]
0x14007031c  lea     rdx, [rbp+57h+bstrString]
0x140070320  mov     rcx, rbx
0x140070323  mov     rax, [rbx]
0x140070326  mov     rax, [rax+148h]
0x14007032d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070332  mov     edi, eax
0x140070334  test    eax, eax
0x140070336  jns     short loc_140070379
0x140070338  mov     rcx, cs:WPP_GLOBAL_Control
0x14007033f  lea     rax, WPP_GLOBAL_Control
0x140070346  cmp     rcx, rax
0x140070349  jz      loc_140070566
0x14007034f  test    byte ptr [rcx+1Ch], 8
0x140070353  jz      loc_140070566
0x140070359  cmp     byte ptr [rcx+19h], 2
0x14007035d  jb      loc_140070566
0x140070363  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140070368  mov     edx, 25h ; '%'
0x14007036d  lea     rcx, aFailedToGetThe_7; "Failed to get the base name"
0x140070374  jmp     loc_14007029C
0x140070379  mov     rcx, [rbp+57h+bstrString]
0x14007037d  mov     eax, 54h ; 'T'
0x140070382  cmp     ax, [rcx]
0x140070385  jnz     loc_1400704EE
0x14007038b  xor     eax, eax
0x14007038d  cmp     ax, [rcx+2]
0x140070391  jnz     loc_1400704EE
0x140070397  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x14007039b  mov     rcx, rbx; struct IXMLDOMNode *
0x14007039e  lea     rdx, aSid; "SID"
0x1400703a5  call    ?RDPENCHLPXML_GetUintAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAI@Z; RDPENCHLPXML_GetUintAttribute(IXMLDOMNode *,ushort const *,uint *)
0x1400703aa  mov     edi, eax
0x1400703ac  test    eax, eax
0x1400703ae  jns     short loc_1400703F1
0x1400703b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400703b7  lea     rax, WPP_GLOBAL_Control
0x1400703be  cmp     rcx, rax
0x1400703c1  jz      loc_140070566
0x1400703c7  test    byte ptr [rcx+1Ch], 8
0x1400703cb  jz      loc_140070566
0x1400703d1  cmp     byte ptr [rcx+19h], 2
0x1400703d5  jb      loc_140070566
0x1400703db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400703e0  mov     edx, 26h ; '&'
0x1400703e5  lea     rcx, aFailedToGetThe_18; "Failed to get the session id"
0x1400703ec  jmp     loc_14007029C
0x1400703f1  lea     rcx, psz; "L[@N!='' and (@P!='' or @U!='')]"
0x1400703f8  call    cs:__imp_SysAllocString
0x1400703fe  mov     rsi, rax
0x140070401  test    rax, rax
0x140070404  jnz     short loc_140070459
0x140070406  mov     rcx, cs:WPP_GLOBAL_Control
0x14007040d  lea     rax, WPP_GLOBAL_Control
0x140070414  cmp     rcx, rax
0x140070417  jz      short loc_14007044F
0x140070419  test    byte ptr [rcx+1Ch], 8
0x14007041d  jz      short loc_14007044F
0x14007041f  cmp     byte ptr [rcx+19h], 2
0x140070423  jb      short loc_14007044F
0x140070425  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007042a  mov     rcx, cs:WPP_GLOBAL_Control
0x140070431  lea     edx, [rsi+27h]
0x140070434  mov     r9d, eax
0x140070437  mov     dword ptr [rsp+0A0h+ppv], 8007000Eh
0x14007043f  lea     r8, WPP_c63511fa6e173da0847aa5c8f83f7746_Traceguids
0x140070446  mov     rcx, [rcx+10h]
0x14007044a  call    WPP_SF_Dd
0x14007044f  mov     edi, 8007000Eh
0x140070454  jmp     loc_140070566
0x140070459  mov     rax, [rbx]
0x14007045c  lea     r8, [rbp+57h+var_50]
0x140070460  mov     rdx, rsi
0x140070463  mov     rcx, rbx
0x140070466  mov     rax, [rax+120h]
0x14007046d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070472  mov     edi, eax
0x140070474  test    eax, eax
0x140070476  jns     short loc_1400704B9
0x140070478  mov     rcx, cs:WPP_GLOBAL_Control
0x14007047f  lea     rax, WPP_GLOBAL_Control
0x140070486  cmp     rcx, rax
0x140070489  jz      loc_140070566
0x14007048f  test    byte ptr [rcx+1Ch], 8
0x140070493  jz      loc_140070566
0x140070499  cmp     byte ptr [rcx+19h], 2
0x14007049d  jb      loc_140070566
0x1400704a3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400704a8  mov     edx, 28h ; '('
0x1400704ad  lea     rcx, aFailedToQueryT_0; "Failed to query the nodes"
0x1400704b4  jmp     loc_14007029C
0x1400704b9  lea     rbx, [r14+8]
0x1400704bd  mov     rax, [rbx]
0x1400704c0  cmp     [rbp+57h+var_50], rax
0x1400704c4  jz      short loc_1400704E6
0x1400704c6  mov     rcx, rbx
0x1400704c9  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1400704ce  mov     rcx, [rbp+57h+var_50]
0x1400704d2  mov     [rbx], rcx
0x1400704d5  test    rcx, rcx
0x1400704d8  jz      short loc_1400704E6
0x1400704da  mov     rax, [rcx]
0x1400704dd  mov     rax, [rax+8]
0x1400704e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400704e6  mov     eax, [rbp+57h+arg_10]
0x1400704e9  mov     [r14], eax
0x1400704ec  jmp     short loc_140070566
0x1400704ee  mov     eax, cs:dword_140150118
0x1400704f4  cmp     eax, 2
0x1400704f7  jbe     short loc_140070561
0x1400704f9  lea     rax, aXmldeserialize_0; "XMLDeserialize"
0x140070500  mov     [rbp+57h+arg_10], 154h
0x140070507  mov     [rbp+57h+var_30], rax
0x14007050b  lea     rdx, qword_14013E478
0x140070512  lea     rax, aOnecoreTermsrv_18; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140070519  mov     [rbp+57h+arg_18], 80004005h
0x140070520  mov     [rbp+57h+var_28], rax
0x140070524  lea     rax, aExpectingTypeT; "Expecting type T node"
0x14007052b  mov     [rbp+57h+var_20], rax
0x14007052f  lea     rax, [rbp+57h+var_30]
0x140070533  mov     [rsp+0A0h+var_60], rax
0x140070538  lea     rax, [rbp+57h+arg_10]
0x14007053c  mov     [rsp+0A0h+var_68], rax
0x140070541  lea     rax, [rbp+57h+var_28]
0x140070545  mov     [rsp+0A0h+var_70], rax
0x14007054a  lea     rax, [rbp+57h+arg_18]
0x14007054e  mov     [rsp+0A0h+var_78], rax
0x140070553  lea     rax, [rbp+57h+var_20]
0x140070557  mov     [rsp+0A0h+ppv], rax
0x14007055c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140070561  mov     edi, 80070057h
0x140070566  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14007056a  test    rcx, rcx
0x14007056d  jz      short loc_140070575
0x14007056f  call    cs:__imp_SysFreeString
0x140070575  test    rsi, rsi
0x140070578  jz      short loc_140070583
0x14007057a  mov     rcx, rsi; bstrString
0x14007057d  call    cs:__imp_SysFreeString
0x140070583  lea     rcx, [rbp+57h+var_40]
0x140070587  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14007058c  lea     rcx, [rbp+57h+var_38]
0x140070590  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140070595  lea     rcx, [rbp+57h+var_50]
0x140070599  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14007059e  lea     r11, [rsp+0A0h+var_10]
0x1400705a6  mov     eax, edi
0x1400705a8  mov     rbx, [r11+20h]
0x1400705ac  mov     rsi, [r11+28h]
0x1400705b0  mov     rsp, r11
0x1400705b3  pop     r14
0x1400705b5  pop     rdi
0x1400705b6  pop     rbp
0x1400705b7  retn
```
