# CRDPENCConnectorStringDeserializer::XMLDeserialize(ushort *)

- ea: `0x140072370`
- end: `0x140072728`
- name: `?XMLDeserialize@CRDPENCConnectorStringDeserializer@@QEAAJPEAG@Z`
- size: `952`
- prototype: `int(CRDPENCConnectorStringDeserializer *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140067e10`

## callees

- `0x1400019e8`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14000dcac`
- `0x140072370`
- `0x140081e04`
- `0x14008248c`
- `0x140114010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1400723c6`
- `ole32!CoCreateInstance` at `0x1400723c6`
- `OLEAUT32!__imp_SysAllocString` at `0x140072568`
- `OLEAUT32!__imp_SysAllocString` at `0x140072568`
- `OLEAUT32!__imp_SysFreeString` at `0x1400726df`
- `OLEAUT32!__imp_SysFreeString` at `0x1400726ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1400726df`
- `OLEAUT32!__imp_SysFreeString` at `0x1400726ed`

## string_xrefs

- `0x140072405`: `Failed to create the XML document`
- `0x14007247f`: `Failed to create the transport root node`
- `0x140072669`: `XMLDeserialize`

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
          if ( (unsigned int)dword_140152118 > 2 )
          {
            v23 = 340;
            v20 = "XMLDeserialize";
            v24 = -2147467259;
            v21 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconser.cpp";
            v22 = "Expecting type T node";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              (_DWORD)bstrString,
              (unsigned int)qword_1401405B0,
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
0x140072370  mov     [rsp-8+arg_0], rbx
0x140072375  mov     [rsp-8+arg_8], rsi
0x14007237a  push    rbp
0x14007237b  push    rdi
0x14007237c  push    r14
0x14007237e  lea     rbp, [rsp-47h]
0x140072383  sub     rsp, 90h
0x14007238a  xor     esi, esi
0x14007238c  mov     [rbp+57h+bstrString], 0
0x140072394  mov     rbx, rdx
0x140072397  mov     [rbp+57h+arg_10], esi
0x14007239a  mov     r14, rcx
0x14007239d  mov     [rbp+57h+var_50], rsi
0x1400723a1  lea     rax, [rbp+57h+var_38]
0x1400723a5  mov     [rbp+57h+var_38], rsi
0x1400723a9  lea     r8d, [rsi+1]; dwClsContext
0x1400723ad  mov     [rbp+57h+var_40], rsi
0x1400723b1  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1400723b8  mov     [rsp+0A0h+ppv], rax; ppv
0x1400723bd  xor     edx, edx; pUnkOuter
0x1400723bf  lea     rcx, CLSID_DOMDocument60; rclsid
0x1400723c6  call    cs:__imp_CoCreateInstance
0x1400723cc  mov     edi, eax
0x1400723ce  test    eax, eax
0x1400723d0  jns     short loc_140072434
0x1400723d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400723d9  lea     rax, WPP_GLOBAL_Control
0x1400723e0  cmp     rcx, rax
0x1400723e3  jz      loc_1400726D6
0x1400723e9  test    byte ptr [rcx+1Ch], 8
0x1400723ed  jz      loc_1400726D6
0x1400723f3  cmp     byte ptr [rcx+19h], 2
0x1400723f7  jb      loc_1400726D6
0x1400723fd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140072402  lea     edx, [rsi+23h]
0x140072405  lea     rcx, aFailedToCreate_51; "Failed to create the XML document"
0x14007240c  mov     dword ptr [rsp+0A0h+var_78], edi
0x140072410  lea     r8, WPP_c63511fa6e173da0847aa5c8f83f7746_Traceguids
0x140072417  mov     [rsp+0A0h+ppv], rcx
0x14007241c  mov     r9d, eax
0x14007241f  mov     rcx, cs:WPP_GLOBAL_Control
0x140072426  mov     rcx, [rcx+10h]
0x14007242a  call    WPP_SF_DsD
0x14007242f  jmp     loc_1400726D6
0x140072434  mov     rcx, [rbp+57h+var_38]; struct IXMLDOMNode *
0x140072438  lea     r8, [rbp+57h+var_40]; struct IXMLDOMNode **
0x14007243c  mov     rdx, rbx; unsigned __int16 *
0x14007243f  call    ?RDPENCHLPXML_AddElementFromXMLString@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAU1@@Z; RDPENCHLPXML_AddElementFromXMLString(IXMLDOMNode *,ushort *,IXMLDOMNode * *)
0x140072444  mov     edi, eax
0x140072446  test    eax, eax
0x140072448  jns     short loc_140072488
0x14007244a  mov     rcx, cs:WPP_GLOBAL_Control
0x140072451  lea     rax, WPP_GLOBAL_Control
0x140072458  cmp     rcx, rax
0x14007245b  jz      loc_1400726D6
0x140072461  test    byte ptr [rcx+1Ch], 8
0x140072465  jz      loc_1400726D6
0x14007246b  cmp     byte ptr [rcx+19h], 2
0x14007246f  jb      loc_1400726D6
0x140072475  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007247a  mov     edx, 24h ; '$'
0x14007247f  lea     rcx, aFailedToCreate_53; "Failed to create the transport root nod"...
0x140072486  jmp     short loc_14007240C
0x140072488  mov     rbx, [rbp+57h+var_40]
0x14007248c  lea     rdx, [rbp+57h+bstrString]
0x140072490  mov     rcx, rbx
0x140072493  mov     rax, [rbx]
0x140072496  mov     rax, [rax+148h]
0x14007249d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400724a2  mov     edi, eax
0x1400724a4  test    eax, eax
0x1400724a6  jns     short loc_1400724E9
0x1400724a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400724af  lea     rax, WPP_GLOBAL_Control
0x1400724b6  cmp     rcx, rax
0x1400724b9  jz      loc_1400726D6
0x1400724bf  test    byte ptr [rcx+1Ch], 8
0x1400724c3  jz      loc_1400726D6
0x1400724c9  cmp     byte ptr [rcx+19h], 2
0x1400724cd  jb      loc_1400726D6
0x1400724d3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400724d8  mov     edx, 25h ; '%'
0x1400724dd  lea     rcx, aFailedToGetThe_7; "Failed to get the base name"
0x1400724e4  jmp     loc_14007240C
0x1400724e9  mov     rcx, [rbp+57h+bstrString]
0x1400724ed  mov     eax, 54h ; 'T'
0x1400724f2  cmp     ax, [rcx]
0x1400724f5  jnz     loc_14007265E
0x1400724fb  xor     eax, eax
0x1400724fd  cmp     ax, [rcx+2]
0x140072501  jnz     loc_14007265E
0x140072507  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x14007250b  mov     rcx, rbx; struct IXMLDOMNode *
0x14007250e  lea     rdx, aSid; "SID"
0x140072515  call    ?RDPENCHLPXML_GetUintAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAI@Z; RDPENCHLPXML_GetUintAttribute(IXMLDOMNode *,ushort const *,uint *)
0x14007251a  mov     edi, eax
0x14007251c  test    eax, eax
0x14007251e  jns     short loc_140072561
0x140072520  mov     rcx, cs:WPP_GLOBAL_Control
0x140072527  lea     rax, WPP_GLOBAL_Control
0x14007252e  cmp     rcx, rax
0x140072531  jz      loc_1400726D6
0x140072537  test    byte ptr [rcx+1Ch], 8
0x14007253b  jz      loc_1400726D6
0x140072541  cmp     byte ptr [rcx+19h], 2
0x140072545  jb      loc_1400726D6
0x14007254b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140072550  mov     edx, 26h ; '&'
0x140072555  lea     rcx, aFailedToGetThe_18; "Failed to get the session id"
0x14007255c  jmp     loc_14007240C
0x140072561  lea     rcx, psz; "L[@N!='' and (@P!='' or @U!='')]"
0x140072568  call    cs:__imp_SysAllocString
0x14007256e  mov     rsi, rax
0x140072571  test    rax, rax
0x140072574  jnz     short loc_1400725C9
0x140072576  mov     rcx, cs:WPP_GLOBAL_Control
0x14007257d  lea     rax, WPP_GLOBAL_Control
0x140072584  cmp     rcx, rax
0x140072587  jz      short loc_1400725BF
0x140072589  test    byte ptr [rcx+1Ch], 8
0x14007258d  jz      short loc_1400725BF
0x14007258f  cmp     byte ptr [rcx+19h], 2
0x140072593  jb      short loc_1400725BF
0x140072595  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007259a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400725a1  lea     edx, [rsi+27h]
0x1400725a4  mov     r9d, eax
0x1400725a7  mov     dword ptr [rsp+0A0h+ppv], 8007000Eh
0x1400725af  lea     r8, WPP_c63511fa6e173da0847aa5c8f83f7746_Traceguids
0x1400725b6  mov     rcx, [rcx+10h]
0x1400725ba  call    WPP_SF_Dd
0x1400725bf  mov     edi, 8007000Eh
0x1400725c4  jmp     loc_1400726D6
0x1400725c9  mov     rax, [rbx]
0x1400725cc  lea     r8, [rbp+57h+var_50]
0x1400725d0  mov     rdx, rsi
0x1400725d3  mov     rcx, rbx
0x1400725d6  mov     rax, [rax+120h]
0x1400725dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400725e2  mov     edi, eax
0x1400725e4  test    eax, eax
0x1400725e6  jns     short loc_140072629
0x1400725e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400725ef  lea     rax, WPP_GLOBAL_Control
0x1400725f6  cmp     rcx, rax
0x1400725f9  jz      loc_1400726D6
0x1400725ff  test    byte ptr [rcx+1Ch], 8
0x140072603  jz      loc_1400726D6
0x140072609  cmp     byte ptr [rcx+19h], 2
0x14007260d  jb      loc_1400726D6
0x140072613  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140072618  mov     edx, 28h ; '('
0x14007261d  lea     rcx, aFailedToQueryT_0; "Failed to query the nodes"
0x140072624  jmp     loc_14007240C
0x140072629  lea     rbx, [r14+8]
0x14007262d  mov     rax, [rbx]
0x140072630  cmp     [rbp+57h+var_50], rax
0x140072634  jz      short loc_140072656
0x140072636  mov     rcx, rbx
0x140072639  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14007263e  mov     rcx, [rbp+57h+var_50]
0x140072642  mov     [rbx], rcx
0x140072645  test    rcx, rcx
0x140072648  jz      short loc_140072656
0x14007264a  mov     rax, [rcx]
0x14007264d  mov     rax, [rax+8]
0x140072651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072656  mov     eax, [rbp+57h+arg_10]
0x140072659  mov     [r14], eax
0x14007265c  jmp     short loc_1400726D6
0x14007265e  mov     eax, cs:dword_140152118
0x140072664  cmp     eax, 2
0x140072667  jbe     short loc_1400726D1
0x140072669  lea     rax, aXmldeserialize_0; "XMLDeserialize"
0x140072670  mov     [rbp+57h+arg_10], 154h
0x140072677  mov     [rbp+57h+var_30], rax
0x14007267b  lea     rdx, qword_1401405B0
0x140072682  lea     rax, aOnecoreTermsrv_18; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140072689  mov     [rbp+57h+arg_18], 80004005h
0x140072690  mov     [rbp+57h+var_28], rax
0x140072694  lea     rax, aExpectingTypeT; "Expecting type T node"
0x14007269b  mov     [rbp+57h+var_20], rax
0x14007269f  lea     rax, [rbp+57h+var_30]
0x1400726a3  mov     [rsp+0A0h+var_60], rax
0x1400726a8  lea     rax, [rbp+57h+arg_10]
0x1400726ac  mov     [rsp+0A0h+var_68], rax
0x1400726b1  lea     rax, [rbp+57h+var_28]
0x1400726b5  mov     [rsp+0A0h+var_70], rax
0x1400726ba  lea     rax, [rbp+57h+arg_18]
0x1400726be  mov     [rsp+0A0h+var_78], rax
0x1400726c3  lea     rax, [rbp+57h+var_20]
0x1400726c7  mov     [rsp+0A0h+ppv], rax
0x1400726cc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400726d1  mov     edi, 80070057h
0x1400726d6  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1400726da  test    rcx, rcx
0x1400726dd  jz      short loc_1400726E5
0x1400726df  call    cs:__imp_SysFreeString
0x1400726e5  test    rsi, rsi
0x1400726e8  jz      short loc_1400726F3
0x1400726ea  mov     rcx, rsi; bstrString
0x1400726ed  call    cs:__imp_SysFreeString
0x1400726f3  lea     rcx, [rbp+57h+var_40]
0x1400726f7  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1400726fc  lea     rcx, [rbp+57h+var_38]
0x140072700  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140072705  lea     rcx, [rbp+57h+var_50]
0x140072709  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14007270e  lea     r11, [rsp+0A0h+var_10]
0x140072716  mov     eax, edi
0x140072718  mov     rbx, [r11+20h]
0x14007271c  mov     rsi, [r11+28h]
0x140072720  mov     rsp, r11
0x140072723  pop     r14
0x140072725  pop     rdi
0x140072726  pop     rbp
0x140072727  retn
```
